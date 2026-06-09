# Microsoft.Crm.Transformations.ResourceProvider::InitResourceManager

- ea: `0x2680`
- end: `0x2727`
- name: `Microsoft.Crm.Transformations.ResourceProvider::InitResourceManager`
- size: `167`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x2650`
- `0x2730`

## callees

- `0x2680`

## string_xrefs

- `0x26ba`: `CRM_Server_InstallDir`
- `0x26f3`: `Microsoft.Crm.Transformations.Strings.dll`

## pseudocode

```c

```

## disassembly

```asm
0x2680  ldsfld   class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager Microsoft.Crm.Transformations.ResourceProvider::_resourceManager
0x2685  brtrue   loc_2726
0x268a  ldsfld   object Microsoft.Crm.Transformations.ResourceProvider::_lockRoot
0x268f  stloc.0
0x2690  ldc.i4.0
0x2691  stloc.1
0x2692  ldloc.0
0x2693  ldloca.s 1
0x2695  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x269a  ldsfld   class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager Microsoft.Crm.Transformations.ResourceProvider::_resourceManager
0x269f  brtrue.s loc_271A
0x26a1  ldsfld   string [mscorlib]System.String::Empty
0x26a6  stloc.3
0x26a7  call     class [mscorlib]Microsoft.Win32.RegistryKey [Microsoft.Crm.Core]Microsoft.Crm.RegControl::get_CrmServerKeyHive()
0x26ac  call     string [Microsoft.Crm.Core]Microsoft.Crm.RegControl::get_CrmServerKeyPath()
0x26b1  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x26b6  stloc.s  4
0x26b8  ldloc.s  4
0x26ba  ldstr    aCrmServerInsta// "CRM_Server_InstallDir"
0x26bf  ldsfld   string [mscorlib]System.String::Empty
0x26c4  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string, object)
0x26c9  castclass [mscorlib]System.String
0x26ce  stloc.3
0x26cf  leave.s  loc_26DD
0x26d1  ldloc.s  4
0x26d3  brfalse.s loc_26DC
0x26d5  ldloc.s  4
0x26d7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26dc  endfinally
0x26dd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x26e2  ldstr    a0ServerBin1// "{0}\\Server\\bin\\{1}"
0x26e7  ldc.i4.2
0x26e8  newarr   [mscorlib]System.Object
0x26ed  dup
0x26ee  ldc.i4.0
0x26ef  ldloc.3
0x26f0  stelem.ref
0x26f1  dup
0x26f2  ldc.i4.1
0x26f3  ldstr    aMicrosoftCrmTr_130// "Microsoft.Crm.Transformations.Strings.d"...
0x26f8  stelem.ref
0x26f9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x26fe  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::LoadFrom(string)
0x2703  stloc.2
0x2704  ldc.i4.1
0x2705  call     void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::SetLanguageIdFromProductType(valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager/ProductType)
0x270a  ldstr    aMicrosoftCrmTr_131// "Microsoft.Crm.Transformations"
0x270f  ldloc.2
0x2710  newobj   instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0x2715  stsfld   class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager Microsoft.Crm.Transformations.ResourceProvider::_resourceManager
0x271a  leave.s  loc_2726
0x271c  ldloc.1
0x271d  brfalse.s loc_2725
0x271f  ldloc.0
0x2720  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x2725  endfinally
0x2726  ret
```
