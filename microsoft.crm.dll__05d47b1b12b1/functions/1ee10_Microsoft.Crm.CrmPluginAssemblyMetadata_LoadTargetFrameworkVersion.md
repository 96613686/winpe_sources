# Microsoft.Crm.CrmPluginAssemblyMetadata::LoadTargetFrameworkVersion

- ea: `0x1ee10`
- end: `0x1eee9`
- name: `Microsoft.Crm.CrmPluginAssemblyMetadata::LoadTargetFrameworkVersion`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1df70`

## callees

- `0x19620`
- `0x1ee10`
- `0x1f090`
- `0x1f200`

## string_xrefs

- `0x1ee45`: `CrmPluginAssemblyMetadata could not get a TargetFrameworkAttribute from "{0}"`

## pseudocode

```c

```

## disassembly

```asm
0x1ee10  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1ee15  stloc.0
0x1ee16  ldc.i4.0
0x1ee17  stloc.1
0x1ee18  ldarg.0
0x1ee19  newobj   instance void [mscorlib]System.Version::.ctor()
0x1ee1e  call     instance void Microsoft.Crm.CrmPluginAssemblyMetadata::set_TargetFrameworkVersion(class [mscorlib]System.Version value)
0x1ee23  ldarg.0
0x1ee24  ldfld    class Microsoft.Crm.IMetaDataImport Microsoft.Crm.CrmPluginAssemblyMetadata::_mdaImport
0x1ee29  ldarg.1
0x1ee2a  ldtoken  [mscorlib]System.Runtime.Versioning.TargetFrameworkAttribute
0x1ee2f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ee34  callvirt instance string [mscorlib]System.Type::get_FullName()
0x1ee39  ldloca.s 0
0x1ee3b  ldloca.s 1
0x1ee3d  callvirt instance int32 Microsoft.Crm.IMetaDataImport::GetCustomAttributeByName(unsigned int32 mdToken, [hasfieldmarshal] string szName, [out] native int& data, [out] unsigned int32& dataSize)
0x1ee42  pop
0x1ee43  leave.s  loc_1EE63
0x1ee45  ldstr    aCrmpluginassem// "CrmPluginAssemblyMetadata could not get"...
0x1ee4a  ldc.i4.1
0x1ee4b  newarr   [mscorlib]System.Object
0x1ee50  dup
0x1ee51  ldc.i4.0
0x1ee52  ldarg.0
0x1ee53  call     instance string Microsoft.Crm.CrmPluginAssemblyMetadata::get_FullName()
0x1ee58  stelem.ref
0x1ee59  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception, string, object[])
0x1ee5e  leave    loc_1EEE8
0x1ee63  ldloc.1
0x1ee64  newarr   [mscorlib]System.Byte
0x1ee69  stloc.2
0x1ee6a  ldloc.0
0x1ee6b  ldloc.2
0x1ee6c  ldc.i4.0
0x1ee6d  ldloc.1
0x1ee6e  call     int32 [mscorlib]System.Convert::ToInt32(unsigned int32)
0x1ee73  call     void [mscorlib]System.Runtime.InteropServices.Marshal::Copy(native int, unsigned int8[], int32, int32)
0x1ee78  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_ASCII()
0x1ee7d  ldloc.2
0x1ee7e  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x1ee83  stloc.3
0x1ee84  ldloc.3
0x1ee85  ldstr    aNetframeworkVe// ".NETFramework,Version=v"
0x1ee8a  callvirt instance int32 [mscorlib]System.String::IndexOf(string)
0x1ee8f  stloc.s  4
0x1ee91  ldloc.s  4
0x1ee93  ldc.i4.m1
0x1ee94  beq.s    loc_1EEE8
0x1ee96  ldloc.s  4
0x1ee98  ldstr    aNetframeworkVe// ".NETFramework,Version=v"
0x1ee9d  call     instance int32 [mscorlib]System.String::get_Length()
0x1eea2  add
0x1eea3  stloc.s  5
0x1eea5  ldstr    a00// "0.0"
0x1eeaa  stloc.s  6
0x1eeac  ldloc.3
0x1eead  ldloc.s  5
0x1eeaf  ldloc.3
0x1eeb0  ldc.i4.1
0x1eeb1  ldloc.s  5
0x1eeb3  callvirt instance int32 [mscorlib]System.String::IndexOf(char, int32)
0x1eeb8  ldloc.s  5
0x1eeba  sub
0x1eebb  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x1eec0  stloc.s  6
0x1eec2  ldarg.0
0x1eec3  ldloc.s  6
0x1eec5  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x1eeca  call     instance void Microsoft.Crm.CrmPluginAssemblyMetadata::set_TargetFrameworkVersion(class [mscorlib]System.Version value)
0x1eecf  leave.s  loc_1EEE8
0x1eed1  ldstr    aCouldNotParseT// "Could not parse the target .NET Framewo"...
0x1eed6  ldc.i4.1
0x1eed7  newarr   [mscorlib]System.Object
0x1eedc  dup
0x1eedd  ldc.i4.0
0x1eede  ldloc.s  6
0x1eee0  stelem.ref
0x1eee1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception, string, object[])
0x1eee6  leave.s  loc_1EEE8
0x1eee8  ret
```
