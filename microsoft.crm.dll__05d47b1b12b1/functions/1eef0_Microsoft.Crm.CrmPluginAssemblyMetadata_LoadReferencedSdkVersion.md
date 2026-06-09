# Microsoft.Crm.CrmPluginAssemblyMetadata::LoadReferencedSdkVersion

- ea: `0x1eef0`
- end: `0x1f08c`
- name: `Microsoft.Crm.CrmPluginAssemblyMetadata::LoadReferencedSdkVersion`
- size: `412`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1df70`

## callees

- `0x19200`
- `0x196b0`
- `0x196f0`
- `0x19790`
- `0x19860`
- `0x1eef0`
- `0x1f090`
- `0x1f220`

## string_xrefs

- `0x1ef28`: `Could not enumerate the assembly references of the plugin assembly "{0}" while checking for the targeted version of Microsoft.Xrm.Sdk`

## pseudocode

```c

```

## disassembly

```asm
0x1eef0  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1eef5  stloc.0
0x1eef6  ldc.i4   0x1000
0x1eefb  newarr   [mscorlib]System.UInt32
0x1ef00  stloc.1
0x1ef01  ldc.i4   0x1000
0x1ef06  stloc.2
0x1ef07  ldarg.0
0x1ef08  newobj   instance void [mscorlib]System.Version::.ctor()
0x1ef0d  call     instance void Microsoft.Crm.CrmPluginAssemblyMetadata::set_ReferencedSdkVersion(class [mscorlib]System.Version value)
0x1ef12  ldarg.0
0x1ef13  ldfld    class Microsoft.Crm.IMetaDataAssemblyImport Microsoft.Crm.CrmPluginAssemblyMetadata::_mdaAssemblyImport
0x1ef18  ldloc.0
0x1ef19  stloc.s  4
0x1ef1b  ldloca.s 4
0x1ef1d  ldloc.1
0x1ef1e  ldloc.2
0x1ef1f  ldloca.s 2
0x1ef21  callvirt instance void Microsoft.Crm.IMetaDataAssemblyImport::EnumAssemblyRefs([in] [out] native int& phEnum, [out] [hasfieldmarshal] unsigned int32[] asmRefs, unsigned int32 asmRefCount, [out] unsigned int32& iFetched)
0x1ef26  leave.s  loc_1EF46
0x1ef28  ldstr    aCouldNotEnumer// "Could not enumerate the assembly refere"...
0x1ef2d  ldc.i4.1
0x1ef2e  newarr   [mscorlib]System.Object
0x1ef33  dup
0x1ef34  ldc.i4.0
0x1ef35  ldarg.0
0x1ef36  call     instance string Microsoft.Crm.CrmPluginAssemblyMetadata::get_FullName()
0x1ef3b  stelem.ref
0x1ef3c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception, string, object[])
0x1ef41  leave    loc_1F08B
0x1ef46  ldc.i4.0
0x1ef47  stloc.3
0x1ef48  ldc.i4.0
0x1ef49  stloc.s  5
0x1ef4b  br       loc_1F07E
0x1ef50  nop
0x1ef51  ldarg.0
0x1ef52  ldfld    class Microsoft.Crm.IMetaDataAssemblyImport Microsoft.Crm.CrmPluginAssemblyMetadata::_mdaAssemblyImport
0x1ef57  ldloc.1
0x1ef58  ldloc.s  5
0x1ef5a  ldelem.u4
0x1ef5b  ldloca.s 6
0x1ef5d  ldloca.s 7
0x1ef5f  ldnull
0x1ef60  ldc.i4.0
0x1ef61  ldloca.s 8
0x1ef63  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1ef68  ldloca.s 9
0x1ef6a  ldloca.s 0xA
0x1ef6c  ldloca.s 0xB
0x1ef6e  callvirt instance void Microsoft.Crm.IMetaDataAssemblyImport::GetAssemblyRefProps(unsigned int32 mdAsmRef, [out] native int& ppbPublicKeyOrToken, [out] unsigned int32& pcbPublicKeyOrToken, [hasfieldmarshal] char[] strName, unsigned int32 cchNameIn, [out] unsigned int32& pchNameOut, native int amdInfo, [out] native int& ppbHashValue, [out] unsigned int32& pcbHashValue, [out] unsigned int32& pdwAssemblyRefFlags)
0x1ef73  leave.s  loc_1EF9D
0x1ef75  ldstr    aAnErrorOccurre// "An error occurred while getting the pro"...
0x1ef7a  ldc.i4.2
0x1ef7b  newarr   [mscorlib]System.Object
0x1ef80  dup
0x1ef81  ldc.i4.0
0x1ef82  ldloc.s  5
0x1ef84  box      [mscorlib]System.Int32
0x1ef89  stelem.ref
0x1ef8a  dup
0x1ef8b  ldc.i4.1
0x1ef8c  ldarg.0
0x1ef8d  call     instance string Microsoft.Crm.CrmPluginAssemblyMetadata::get_FullName()
0x1ef92  stelem.ref
0x1ef93  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception, string, object[])
0x1ef98  leave    loc_1F078
0x1ef9d  ldloc.s  8
0x1ef9f  newarr   [mscorlib]System.Char
0x1efa4  stloc.s  0xC
0x1efa6  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1efab  stloc.s  0xD
0x1efad  call     native int Microsoft.Crm.MetaDataInterop::AllocAsmMeta()
0x1efb2  stloc.s  0xD
0x1efb4  ldarg.0
0x1efb5  ldfld    class Microsoft.Crm.IMetaDataAssemblyImport Microsoft.Crm.CrmPluginAssemblyMetadata::_mdaAssemblyImport
0x1efba  ldloc.1
0x1efbb  ldloc.s  5
0x1efbd  ldelem.u4
0x1efbe  ldloca.s 6
0x1efc0  ldloca.s 7
0x1efc2  ldloc.s  0xC
0x1efc4  ldloc.s  8
0x1efc6  ldloca.s 8
0x1efc8  ldloc.s  0xD
0x1efca  ldloca.s 9
0x1efcc  ldloca.s 0xA
0x1efce  ldloca.s 0xB
0x1efd0  callvirt instance void Microsoft.Crm.IMetaDataAssemblyImport::GetAssemblyRefProps(unsigned int32 mdAsmRef, [out] native int& ppbPublicKeyOrToken, [out] unsigned int32& pcbPublicKeyOrToken, [hasfieldmarshal] char[] strName, unsigned int32 cchNameIn, [out] unsigned int32& pchNameOut, native int amdInfo, [out] native int& ppbHashValue, [out] unsigned int32& pcbHashValue, [out] unsigned int32& pdwAssemblyRefFlags)
0x1efd5  ldloc.s  0xD
0x1efd7  ldtoken  Microsoft.Crm.ASSEMBLYMETADATA
0x1efdc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1efe1  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x1efe6  unbox.any Microsoft.Crm.ASSEMBLYMETADATA
0x1efeb  stloc.s  0xE
0x1efed  ldloc.s  0xC
0x1efef  newobj   instance void [mscorlib]System.String::.ctor(char[])
0x1eff4  ldc.i4.1
0x1eff5  newarr   [mscorlib]System.Char
0x1effa  call     instance string [mscorlib]System.String::TrimEnd(char[])
0x1efff  ldstr    aMicrosoftXrmSd_0// "Microsoft.Xrm.Sdk"
0x1f004  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1f009  brfalse.s loc_1F034
0x1f00b  ldarg.0
0x1f00c  ldloc.s  0xE
0x1f00e  ldfld    unsigned int16 Microsoft.Crm.ASSEMBLYMETADATA::usMajorVersion
0x1f013  ldloc.s  0xE
0x1f015  ldfld    unsigned int16 Microsoft.Crm.ASSEMBLYMETADATA::usMinorVersion
0x1f01a  ldloc.s  0xE
0x1f01c  ldfld    unsigned int16 Microsoft.Crm.ASSEMBLYMETADATA::usBuildNumber
0x1f021  ldloc.s  0xE
0x1f023  ldfld    unsigned int16 Microsoft.Crm.ASSEMBLYMETADATA::usRevisionNumber
0x1f028  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x1f02d  call     instance void Microsoft.Crm.CrmPluginAssemblyMetadata::set_ReferencedSdkVersion(class [mscorlib]System.Version value)
0x1f032  ldc.i4.1
0x1f033  stloc.3
0x1f034  ldloca.s 0xE
0x1f036  call     instance void Microsoft.Crm.ASSEMBLYMETADATA::Dispose()
0x1f03b  leave.s  loc_1F078
0x1f03d  ldstr    aAnErrorOccurre_0// "An error occurred while getting the ver"...
0x1f042  ldc.i4.2
0x1f043  newarr   [mscorlib]System.Object
0x1f048  dup
0x1f049  ldc.i4.0
0x1f04a  ldloc.s  5
0x1f04c  box      [mscorlib]System.Int32
0x1f051  stelem.ref
0x1f052  dup
0x1f053  ldc.i4.1
0x1f054  ldarg.0
0x1f055  call     instance string Microsoft.Crm.CrmPluginAssemblyMetadata::get_FullName()
0x1f05a  stelem.ref
0x1f05b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception, string, object[])
0x1f060  leave.s  loc_1F078
0x1f062  ldloc.s  0xD
0x1f064  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1f069  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x1f06e  brfalse.s loc_1F077
0x1f070  ldloc.s  0xD
0x1f072  call     void Microsoft.Crm.MetaDataInterop::FreeAsmMeta(native int asmMetaPtr)
0x1f077  endfinally
0x1f078  ldloc.s  5
0x1f07a  ldc.i4.1
0x1f07b  add
0x1f07c  stloc.s  5
0x1f07e  ldloc.3
0x1f07f  brtrue.s loc_1F08B
0x1f081  ldloc.s  5
0x1f083  conv.i8
0x1f084  ldloc.2
0x1f085  conv.u8
0x1f086  blt      loc_1EF50
0x1f08b  ret
```
