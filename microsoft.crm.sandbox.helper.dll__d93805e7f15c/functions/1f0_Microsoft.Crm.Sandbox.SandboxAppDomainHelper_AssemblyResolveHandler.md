# Microsoft.Crm.Sandbox.SandboxAppDomainHelper::AssemblyResolveHandler

- ea: `0x1f0`
- end: `0x33c`
- name: `Microsoft.Crm.Sandbox.SandboxAppDomainHelper::AssemblyResolveHandler`
- size: `332`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1f0`
- `0x340`
- `0x610`

## pseudocode

```c

```

## disassembly

```asm
0x1f0  ldarg.1
0x1f1  callvirt instance string [mscorlib]System.ResolveEventArgs::get_Name()
0x1f6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1fb  brtrue   loc_33A
0x200  ldarg.1
0x201  callvirt instance string [mscorlib]System.ResolveEventArgs::get_Name()
0x206  newobj   instance void [mscorlib]System.Reflection.AssemblyName::.ctor(string)
0x20b  stloc.0
0x20c  call     class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Sandbox.SandboxAppDomainHelper::get_TrustedAssemblies()
0x211  ldloc.0
0x212  callvirt instance string [mscorlib]System.Reflection.AssemblyName::get_Name()
0x217  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x21c  brfalse.s loc_24C
0x21e  ldloc.0
0x21f  callvirt instance class [mscorlib]System.Version [mscorlib]System.Reflection.AssemblyName::get_Version()
0x224  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x229  ldc.i4.5
0x22a  bne.un.s loc_24C
0x22c  ldarg.1
0x22d  callvirt instance string [mscorlib]System.ResolveEventArgs::get_Name()
0x232  ldstr    a5000// "5.0.0.0"
0x237  ldstr    a9000// "9.0.0.0"
0x23c  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x241  newobj   instance void [mscorlib]System.Reflection.AssemblyName::.ctor(string)
0x246  stloc.0
0x247  br       loc_301
0x24c  call     class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Sandbox.SandboxAppDomainHelper::get_TrustedAssemblies()
0x251  ldloc.0
0x252  callvirt instance string [mscorlib]System.Reflection.AssemblyName::get_Name()
0x257  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x25c  brfalse.s loc_289
0x25e  ldloc.0
0x25f  callvirt instance class [mscorlib]System.Version [mscorlib]System.Reflection.AssemblyName::get_Version()
0x264  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x269  ldc.i4.6
0x26a  bne.un.s loc_289
0x26c  ldarg.1
0x26d  callvirt instance string [mscorlib]System.ResolveEventArgs::get_Name()
0x272  ldstr    a6000// "6.0.0.0"
0x277  ldstr    a9000// "9.0.0.0"
0x27c  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x281  newobj   instance void [mscorlib]System.Reflection.AssemblyName::.ctor(string)
0x286  stloc.0
0x287  br.s     loc_301
0x289  call     class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Sandbox.SandboxAppDomainHelper::get_TrustedAssemblies()
0x28e  ldloc.0
0x28f  callvirt instance string [mscorlib]System.Reflection.AssemblyName::get_Name()
0x294  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x299  brfalse.s loc_2C6
0x29b  ldloc.0
0x29c  callvirt instance class [mscorlib]System.Version [mscorlib]System.Reflection.AssemblyName::get_Version()
0x2a1  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x2a6  ldc.i4.7
0x2a7  bne.un.s loc_2C6
0x2a9  ldarg.1
0x2aa  callvirt instance string [mscorlib]System.ResolveEventArgs::get_Name()
0x2af  ldstr    a7000// "7.0.0.0"
0x2b4  ldstr    a9000// "9.0.0.0"
0x2b9  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x2be  newobj   instance void [mscorlib]System.Reflection.AssemblyName::.ctor(string)
0x2c3  stloc.0
0x2c4  br.s     loc_301
0x2c6  call     class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Sandbox.SandboxAppDomainHelper::get_TrustedAssemblies()
0x2cb  ldloc.0
0x2cc  callvirt instance string [mscorlib]System.Reflection.AssemblyName::get_Name()
0x2d1  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x2d6  brfalse.s loc_301
0x2d8  ldloc.0
0x2d9  callvirt instance class [mscorlib]System.Version [mscorlib]System.Reflection.AssemblyName::get_Version()
0x2de  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x2e3  ldc.i4.8
0x2e4  bne.un.s loc_301
0x2e6  ldarg.1
0x2e7  callvirt instance string [mscorlib]System.ResolveEventArgs::get_Name()
0x2ec  ldstr    a8000// "8.0.0.0"
0x2f1  ldstr    a9000// "9.0.0.0"
0x2f6  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x2fb  newobj   instance void [mscorlib]System.Reflection.AssemblyName::.ctor(string)
0x300  stloc.0
0x301  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x306  callvirt instance class [mscorlib]System.Reflection.Assembly[] [mscorlib]System.AppDomain::GetAssemblies()
0x30b  stloc.1
0x30c  ldc.i4.0
0x30d  stloc.2
0x30e  br.s     loc_32D
0x310  ldloc.1
0x311  ldloc.2
0x312  ldelem.ref
0x313  stloc.3
0x314  ldloc.3
0x315  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x31a  ldarg.1
0x31b  callvirt instance string [mscorlib]System.ResolveEventArgs::get_Name()
0x320  call     bool [mscorlib]System.String::op_Equality(string, string)
0x325  brfalse.s loc_329
0x327  ldloc.3
0x328  ret
0x329  ldloc.2
0x32a  ldc.i4.1
0x32b  add
0x32c  stloc.2
0x32d  ldloc.2
0x32e  ldloc.1
0x32f  ldlen
0x330  conv.i4
0x331  blt.s    loc_310
0x333  ldloc.0
0x334  call     class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Sandbox.SandboxAppDomainHelper::LoadTrustedAssembly(class [mscorlib]System.Reflection.AssemblyName assemblyName)
0x339  ret
0x33a  ldnull
0x33b  ret
```
