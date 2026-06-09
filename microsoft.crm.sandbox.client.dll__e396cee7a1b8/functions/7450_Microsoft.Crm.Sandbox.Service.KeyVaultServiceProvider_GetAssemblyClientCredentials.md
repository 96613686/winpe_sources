# Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::GetAssemblyClientCredentials

- ea: `0x7450`
- end: `0x74ae`
- name: `Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::GetAssemblyClientCredentials`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x7450`
- `0x74b0`

## string_xrefs

- `0x745c`: `keyVaultUri`

## pseudocode

```c

```

## disassembly

```asm
0x7450  ldarg.1
0x7451  ldstr    aAssemblyname// "assemblyName"
0x7456  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x745b  ldarg.2
0x745c  ldstr    aKeyvaulturi// "keyVaultUri"
0x7461  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7466  ldarg.0
0x7467  ldarg.1
0x7468  call     instance object Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::RemoveInvalidCharactersFromAssemblyName(string assemblyName)
0x746d  dup
0x746e  ldstr    aAppid// "-AppId"
0x7473  call     string [mscorlib]System.String::Concat(object, object)
0x7478  stloc.0
0x7479  ldstr    aSecret// "-Secret"
0x747e  call     string [mscorlib]System.String::Concat(object, object)
0x7483  stloc.1
0x7484  ldarg.0
0x7485  ldarg.2
0x7486  ldarg.3
0x7487  ldloc.0
0x7488  ldloc.1
0x7489  ldsfld   class [mscorlib]System.Func`3<string, string, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.Service.ObjectModel.AssemblyCredentials> <>c::<>9__9_0
0x748e  dup
0x748f  brtrue.s loc_74A8
0x7491  pop
0x7492  ldsfld   class <>c <>c::<>9
0x7497  ldftn    instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.Service.ObjectModel.AssemblyCredentials <>c::<GetAssemblyClientCredentials>b__9_0(string appId, string appSecret)
0x749d  newobj   instance void class [mscorlib]System.Func`3<string, string, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.Service.ObjectModel.AssemblyCredentials>::.ctor(object, native int)
0x74a2  dup
0x74a3  stsfld   class [mscorlib]System.Func`3<string, string, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.Service.ObjectModel.AssemblyCredentials> <>c::<>9__9_0
0x74a8  call     T0x2B000019
0x74ad  ret
```
