<script lang="ts">
	import logo2 from './logo.png';
	import { auth } from '../../firebase';
	import { signOut } from 'firebase/auth';
	//import { user } from '../../store/user';

	function signOutUser() {
		console.log('LOGING OUT');
		signOut(auth).then(() => {
			//user.set({});
		});
	}
</script>

<div class="navbar bg-base-100">
	<div class="flex-1">
		<a href="/" class="btn btn-ghost normal-case text-xl text-gray-400 px-0 pr-2"
			><img src={logo2} class="scale-50" alt="" />Ammo Cache</a
		>
	</div>
	<div class="flex-none gap-2">
		<div class="dropdown dropdown-end">
			<label tabindex="0" class="btn btn-ghost btn-circle avatar">
				<div class="w-10 rounded-full">
					<img src="user.png" alt="ammo cache logo" />
				</div>
			</label>
			<ul
				tabindex="0"
				class="mt-3 p-2 shadow menu menu-compact dropdown-content bg-base-100 rounded-box w-52"
			>
				<li>
					<a href="/profile" class="justify-between">
						Profile
						<span class="badge">New</span>
					</a>
				</li>
				<li><a href="/settings">Settings</a></li>
				<li on:click={signOutUser}><a>Logout</a></li>
			</ul>
		</div>
	</div>
</div>
