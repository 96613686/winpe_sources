# Microsoft.Crm.Watson.ExceptionManager::RetrieveVersionFromAssembly

- ea: `0x41ae0`
- end: `0x41b66`
- name: `Microsoft.Crm.Watson.ExceptionManager::RetrieveVersionFromAssembly`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x41490`

## callees

- `0x41ae0`

## string_xrefs

- `0x41ae8`: `Microsoft.Crm.dll`
- `0x41af0`: `Microsoft.Crm.DiscoveryService.dll`
- `0x41af8`: `Microsoft.Crm.Site.Core.dll`

## pseudocode

```c

```

## disassembly

```asm
0x41ae0  ldc.i4.3
0x41ae1  newarr   [mscorlib]System.String
0x41ae6  dup
0x41ae7  ldc.i4.0
0x41ae8  ldstr    aMicrosoftCrmDl// "Microsoft.Crm.dll"
0x41aed  stelem.ref
0x41aee  dup
0x41aef  ldc.i4.1
0x41af0  ldstr    aMicrosoftCrmDi// "Microsoft.Crm.DiscoveryService.dll"
0x41af5  stelem.ref
0x41af6  dup
0x41af7  ldc.i4.2
0x41af8  ldstr    aMicrosoftCrmSi// "Microsoft.Crm.Site.Core.dll"
0x41afd  stelem.ref
0x41afe  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x41b03  callvirt instance class [mscorlib]System.Reflection.Assembly[] [mscorlib]System.AppDomain::GetAssemblies()
0x41b08  stloc.0
0x41b09  stloc.1
0x41b0a  ldc.i4.0
0x41b0b  stloc.2
0x41b0c  br.s     loc_41B5A
0x41b0e  ldloc.1
0x41b0f  ldloc.2
0x41b10  ldelem.ref
0x41b11  stloc.3
0x41b12  ldloc.0
0x41b13  stloc.s  4
0x41b15  ldc.i4.0
0x41b16  stloc.s  5
0x41b18  br.s     loc_41B4E
0x41b1a  ldloc.s  4
0x41b1c  ldloc.s  5
0x41b1e  ldelem.ref
0x41b1f  stloc.s  6
0x41b21  ldloc.s  6
0x41b23  callvirt instance class [mscorlib]System.Reflection.Module [mscorlib]System.Reflection.Assembly::get_ManifestModule()
0x41b28  callvirt instance string [mscorlib]System.Reflection.Module::get_Name()
0x41b2d  ldloc.3
0x41b2e  ldc.i4.5
0x41b2f  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x41b34  brfalse.s loc_41B48
0x41b36  ldloc.s  6
0x41b38  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x41b3d  call     class [System]System.Diagnostics.FileVersionInfo [System]System.Diagnostics.FileVersionInfo::GetVersionInfo(string)
0x41b42  callvirt instance string [System]System.Diagnostics.FileVersionInfo::get_FileVersion()
0x41b47  ret
0x41b48  ldloc.s  5
0x41b4a  ldc.i4.1
0x41b4b  add
0x41b4c  stloc.s  5
0x41b4e  ldloc.s  5
0x41b50  ldloc.s  4
0x41b52  ldlen
0x41b53  conv.i4
0x41b54  blt.s    loc_41B1A
0x41b56  ldloc.2
0x41b57  ldc.i4.1
0x41b58  add
0x41b59  stloc.2
0x41b5a  ldloc.2
0x41b5b  ldloc.1
0x41b5c  ldlen
0x41b5d  conv.i4
0x41b5e  blt.s    loc_41B0E
0x41b60  ldsfld   string [mscorlib]System.String::Empty
0x41b65  ret
```
