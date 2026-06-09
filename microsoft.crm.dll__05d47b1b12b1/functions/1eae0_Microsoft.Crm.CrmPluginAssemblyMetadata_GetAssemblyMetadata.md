# Microsoft.Crm.CrmPluginAssemblyMetadata::GetAssemblyMetadata

- ea: `0x1eae0`
- end: `0x1edd4`
- name: `Microsoft.Crm.CrmPluginAssemblyMetadata::GetAssemblyMetadata`
- size: `756`
- prototype: ``
- caller_count: `3`
- callee_count: `21`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1df70`
- `0x1e160`
- `0x1ea80`

## callees

- `0x19200`
- `0x196a0`
- `0x196b0`
- `0x19790`
- `0x19860`
- `0x19890`
- `0x1d820`
- `0x1d880`
- `0x1e020`
- `0x1e030`
- `0x1e140`
- `0x1eae0`
- `0x1f0a0`
- `0x1f0c0`
- `0x1f0e0`
- `0x1f100`
- `0x1f120`
- `0x1f140`
- `0x1f160`
- `0x1f180`
- `0x1f1a0`

## string_xrefs

- `0x1eaed`: `GetAssemblyMetadata: token: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1eae0  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1eae5  stloc.0
0x1eae6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1eaeb  ldc.i4.s 0x14
0x1eaed  ldstr    aGetassemblymet// "GetAssemblyMetadata: token: {0}"
0x1eaf2  ldc.i4.1
0x1eaf3  newarr   [mscorlib]System.Object
0x1eaf8  dup
0x1eaf9  ldc.i4.0
0x1eafa  ldarg.0
0x1eafb  ldarg.1
0x1eafc  call     instance string Microsoft.Crm.CrmPluginAssemblyMetadata::Hex(unsigned int32 value)
0x1eb01  stelem.ref
0x1eb02  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1eb07  ldarg.1
0x1eb08  call     valuetype Microsoft.Crm.CorTokenType Microsoft.Crm.CrmPluginAssemblyMetadata::TokenType(unsigned int32 token)
0x1eb0d  ldc.i4   0x23000000
0x1eb12  beq.s    loc_1EB23
0x1eb14  ldarg.1
0x1eb15  call     valuetype Microsoft.Crm.CorTokenType Microsoft.Crm.CrmPluginAssemblyMetadata::TokenType(unsigned int32 token)
0x1eb1a  ldc.i4   0x20000000
0x1eb1f  ceq
0x1eb21  br.s     loc_1EB24
0x1eb23  ldc.i4.1
0x1eb24  ldstr    aGetassemblymet_0// "GetAssemblyMetadata: expected mdtAssemb"...
0x1eb29  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1eb2e  ldarg.1
0x1eb2f  call     bool Microsoft.Crm.CrmPluginAssemblyMetadata::IsNullToken(unsigned int32 token)
0x1eb34  brfalse.s loc_1EB3E
0x1eb36  ldnull
0x1eb37  stloc.s  0xE
0x1eb39  leave    loc_1EDD1
0x1eb3e  ldarg.0
0x1eb3f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<unsigned int32, class Microsoft.Crm.CrmPluginAssemblyMetadata> Microsoft.Crm.CrmPluginAssemblyMetadata::_processedModules
0x1eb44  ldarg.1
0x1eb45  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<unsigned int32, class Microsoft.Crm.CrmPluginAssemblyMetadata>::ContainsKey(var<u1>)
0x1eb4a  brfalse.s loc_1EB5F
0x1eb4c  ldarg.0
0x1eb4d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<unsigned int32, class Microsoft.Crm.CrmPluginAssemblyMetadata> Microsoft.Crm.CrmPluginAssemblyMetadata::_processedModules
0x1eb52  ldarg.1
0x1eb53  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<unsigned int32, class Microsoft.Crm.CrmPluginAssemblyMetadata>::get_Item(void)
0x1eb58  stloc.s  0xE
0x1eb5a  leave    loc_1EDD1
0x1eb5f  ldarg.1
0x1eb60  call     valuetype Microsoft.Crm.CorTokenType Microsoft.Crm.CrmPluginAssemblyMetadata::TokenType(unsigned int32 token)
0x1eb65  ldc.i4   0x23000000
0x1eb6a  bne.un.s loc_1EB8D
0x1eb6c  ldarg.0
0x1eb6d  ldfld    class Microsoft.Crm.IMetaDataAssemblyImport Microsoft.Crm.CrmPluginAssemblyMetadata::_mdaAssemblyImport
0x1eb72  ldarg.1
0x1eb73  ldloca.s 1
0x1eb75  ldloca.s 2
0x1eb77  ldnull
0x1eb78  ldc.i4.0
0x1eb79  ldloca.s 3
0x1eb7b  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1eb80  ldloca.s 6
0x1eb82  ldloca.s 5
0x1eb84  ldloca.s 4
0x1eb86  callvirt instance void Microsoft.Crm.IMetaDataAssemblyImport::GetAssemblyRefProps(unsigned int32 mdAsmRef, [out] native int& ppbPublicKeyOrToken, [out] unsigned int32& pcbPublicKeyOrToken, [hasfieldmarshal] char[] strName, unsigned int32 cchNameIn, [out] unsigned int32& pchNameOut, native int amdInfo, [out] native int& ppbHashValue, [out] unsigned int32& pcbHashValue, [out] unsigned int32& pdwAssemblyRefFlags)
0x1eb8b  br.s     loc_1EBAA
0x1eb8d  ldarg.0
0x1eb8e  ldfld    class Microsoft.Crm.IMetaDataAssemblyImport Microsoft.Crm.CrmPluginAssemblyMetadata::_mdaAssemblyImport
0x1eb93  ldarg.1
0x1eb94  ldloca.s 1
0x1eb96  ldloca.s 2
0x1eb98  ldloca.s 5
0x1eb9a  ldnull
0x1eb9b  ldc.i4.0
0x1eb9c  ldloca.s 3
0x1eb9e  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1eba3  ldloca.s 4
0x1eba5  callvirt instance void Microsoft.Crm.IMetaDataAssemblyImport::GetAssemblyProps(unsigned int32 mdAsm, [out] native int& pPublicKeyPtr, [out] unsigned int32& ucbPublicKeyPtr, [out] unsigned int32& uHashAlg, [hasfieldmarshal] char[] strName, unsigned int32 cchNameIn, [out] unsigned int32& cchNameRequired, native int amdInfo, [out] unsigned int32& dwFlags)
0x1ebaa  ldloc.3
0x1ebab  ldc.i4.1
0x1ebac  add
0x1ebad  newarr   [mscorlib]System.Char
0x1ebb2  stloc.s  7
0x1ebb4  call     native int Microsoft.Crm.MetaDataInterop::AllocAsmMeta()
0x1ebb9  stloc.0
0x1ebba  ldarg.1
0x1ebbb  call     valuetype Microsoft.Crm.CorTokenType Microsoft.Crm.CrmPluginAssemblyMetadata::TokenType(unsigned int32 token)
0x1ebc0  ldc.i4   0x23000000
0x1ebc5  bne.un.s loc_1EBE5
0x1ebc7  ldarg.0
0x1ebc8  ldfld    class Microsoft.Crm.IMetaDataAssemblyImport Microsoft.Crm.CrmPluginAssemblyMetadata::_mdaAssemblyImport
0x1ebcd  ldarg.1
0x1ebce  ldloca.s 1
0x1ebd0  ldloca.s 2
0x1ebd2  ldloc.s  7
0x1ebd4  ldloc.3
0x1ebd5  ldloca.s 3
0x1ebd7  ldloc.0
0x1ebd8  ldloca.s 6
0x1ebda  ldloca.s 5
0x1ebdc  ldloca.s 4
0x1ebde  callvirt instance void Microsoft.Crm.IMetaDataAssemblyImport::GetAssemblyRefProps(unsigned int32 mdAsmRef, [out] native int& ppbPublicKeyOrToken, [out] unsigned int32& pcbPublicKeyOrToken, [hasfieldmarshal] char[] strName, unsigned int32 cchNameIn, [out] unsigned int32& pchNameOut, native int amdInfo, [out] native int& ppbHashValue, [out] unsigned int32& pcbHashValue, [out] unsigned int32& pdwAssemblyRefFlags)
0x1ebe3  br.s     loc_1EBFF
0x1ebe5  ldarg.0
0x1ebe6  ldfld    class Microsoft.Crm.IMetaDataAssemblyImport Microsoft.Crm.CrmPluginAssemblyMetadata::_mdaAssemblyImport
0x1ebeb  ldarg.1
0x1ebec  ldloca.s 1
0x1ebee  ldloca.s 2
0x1ebf0  ldloca.s 5
0x1ebf2  ldloc.s  7
0x1ebf4  ldloc.3
0x1ebf5  ldloca.s 3
0x1ebf7  ldloc.0
0x1ebf8  ldloca.s 4
0x1ebfa  callvirt instance void Microsoft.Crm.IMetaDataAssemblyImport::GetAssemblyProps(unsigned int32 mdAsm, [out] native int& pPublicKeyPtr, [out] unsigned int32& ucbPublicKeyPtr, [out] unsigned int32& uHashAlg, [hasfieldmarshal] char[] strName, unsigned int32 cchNameIn, [out] unsigned int32& cchNameRequired, native int amdInfo, [out] unsigned int32& dwFlags)
0x1ebff  ldloc.s  7
0x1ec01  newobj   instance void [mscorlib]System.String::.ctor(char[])
0x1ec06  stloc.s  8
0x1ec08  ldloc.s  8
0x1ec0a  ldc.i4.1
0x1ec0b  newarr   [mscorlib]System.Char
0x1ec10  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x1ec15  stloc.s  8
0x1ec17  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1ec1c  ldc.i4.s 0x14
0x1ec1e  ldstr    aGetassemblymet_1// "GetAssemblyMetadata: moduleName: {0}"
0x1ec23  ldc.i4.1
0x1ec24  newarr   [mscorlib]System.Object
0x1ec29  dup
0x1ec2a  ldc.i4.0
0x1ec2b  ldloc.s  8
0x1ec2d  stelem.ref
0x1ec2e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1ec33  ldloc.0
0x1ec34  ldloc.s  7
0x1ec36  ldloc.3
0x1ec37  ldloc.1
0x1ec38  ldloc.2
0x1ec39  ldloc.s  4
0x1ec3b  call     class [mscorlib]System.Reflection.AssemblyName Microsoft.Crm.MetaDataInterop::ConstructAssemblyName(native int asmMetaPtr, char[] asmNameBuf, unsigned int32 asmNameLength, native int pubKeyPtr, unsigned int32 pubKeyBytes, unsigned int32 flags)
0x1ec40  stloc.s  9
0x1ec42  ldarg.0
0x1ec43  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object[]> Microsoft.Crm.CrmPluginAssemblyMetadata::get_Cache()
0x1ec48  newobj   instance void Microsoft.Crm.CrmPluginAssemblyMetadata::.ctor(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object[]> cacheToUse)
0x1ec4d  stloc.s  0xA
0x1ec4f  ldloc.s  0xA
0x1ec51  ldloc.s  8
0x1ec53  callvirt instance void Microsoft.Crm.CrmPluginAssemblyMetadata::set_ShortName(string value)
0x1ec58  ldloc.s  0xA
0x1ec5a  ldloc.s  9
0x1ec5c  callvirt instance string [mscorlib]System.Reflection.AssemblyName::get_FullName()
0x1ec61  callvirt instance void Microsoft.Crm.CrmPluginAssemblyMetadata::set_FullName(string value)
0x1ec66  ldloc.s  9
0x1ec68  callvirt instance string [mscorlib]System.Reflection.AssemblyName::get_FullName()
0x1ec6d  ldc.i4.1
0x1ec6e  newarr   [mscorlib]System.Char
0x1ec73  dup
0x1ec74  ldc.i4.0
0x1ec75  ldc.i4.s 0x2C
0x1ec77  stelem.i2
0x1ec78  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x1ec7d  stloc.s  0xB
0x1ec7f  ldloc.s  0xB
0x1ec81  ldlen
0x1ec82  conv.i4
0x1ec83  ldc.i4.4
0x1ec84  ceq
0x1ec86  ldstr    aParts// "parts"
0x1ec8b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1ec90  ldloc.s  0xB
0x1ec92  ldc.i4.2
0x1ec93  ldelem.ref
0x1ec94  ldc.i4.1
0x1ec95  newarr   [mscorlib]System.Char
0x1ec9a  dup
0x1ec9b  ldc.i4.0
0x1ec9c  ldc.i4.s 0x3D
0x1ec9e  stelem.i2
0x1ec9f  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x1eca4  stloc.s  0xC
0x1eca6  ldloc.s  0xC
0x1eca8  ldlen
0x1eca9  conv.i4
0x1ecaa  ldc.i4.2
0x1ecab  ceq
0x1ecad  ldstr    aCultureparts// "cultureParts"
0x1ecb2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1ecb7  ldloc.s  0xA
0x1ecb9  ldloc.s  0xC
0x1ecbb  ldc.i4.1
0x1ecbc  ldelem.ref
0x1ecbd  callvirt instance void Microsoft.Crm.CrmPluginAssemblyMetadata::set_Culture(string value)
0x1ecc2  ldloc.s  0xB
0x1ecc4  ldc.i4.3
0x1ecc5  ldelem.ref
0x1ecc6  ldc.i4.1
0x1ecc7  newarr   [mscorlib]System.Char
0x1eccc  dup
0x1eccd  ldc.i4.0
0x1ecce  ldc.i4.s 0x3D
0x1ecd0  stelem.i2
0x1ecd1  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x1ecd6  stloc.s  0xD
0x1ecd8  ldloc.s  0xD
0x1ecda  ldlen
0x1ecdb  conv.i4
0x1ecdc  ldc.i4.2
0x1ecdd  ceq
0x1ecdf  ldstr    aPkparts// "pkParts"
0x1ece4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1ece9  ldloc.s  0xA
0x1eceb  ldloc.s  0xD
0x1eced  ldc.i4.1
0x1ecee  ldelem.ref
0x1ecef  callvirt instance void Microsoft.Crm.CrmPluginAssemblyMetadata::set_PublicKeyToken(string value)
0x1ecf4  ldloc.s  0xA
0x1ecf6  ldloc.s  9
0x1ecf8  callvirt instance class [mscorlib]System.Version [mscorlib]System.Reflection.AssemblyName::get_Version()
0x1ecfd  callvirt instance string [mscorlib]System.Object::ToString()
0x1ed02  callvirt instance void Microsoft.Crm.CrmPluginAssemblyMetadata::set_Version(string value)
0x1ed07  ldloc.s  0xA
0x1ed09  ldloc.s  9
0x1ed0b  callvirt instance class [mscorlib]System.Version [mscorlib]System.Reflection.AssemblyName::get_Version()
0x1ed10  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x1ed15  stloc.s  0xF
0x1ed17  ldloca.s 0xF
0x1ed19  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1ed1e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1ed23  callvirt instance void Microsoft.Crm.CrmPluginAssemblyMetadata::set_VersionMajor(string value)
0x1ed28  ldloc.s  0xA
0x1ed2a  ldloc.s  9
0x1ed2c  callvirt instance class [mscorlib]System.Version [mscorlib]System.Reflection.AssemblyName::get_Version()
0x1ed31  callvirt instance int32 [mscorlib]System.Version::get_Minor()
0x1ed36  stloc.s  0xF
0x1ed38  ldloca.s 0xF
0x1ed3a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1ed3f  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1ed44  callvirt instance void Microsoft.Crm.CrmPluginAssemblyMetadata::set_VersionMinor(string value)
0x1ed49  ldloc.s  0xA
0x1ed4b  ldloc.s  9
0x1ed4d  callvirt instance class [mscorlib]System.Version [mscorlib]System.Reflection.AssemblyName::get_Version()
0x1ed52  callvirt instance int32 [mscorlib]System.Version::get_Build()
0x1ed57  stloc.s  0xF
0x1ed59  ldloca.s 0xF
0x1ed5b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1ed60  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1ed65  callvirt instance void Microsoft.Crm.CrmPluginAssemblyMetadata::set_VersionBuild(string value)
0x1ed6a  ldloc.s  0xA
0x1ed6c  ldloc.s  9
0x1ed6e  callvirt instance class [mscorlib]System.Version [mscorlib]System.Reflection.AssemblyName::get_Version()
0x1ed73  callvirt instance int32 [mscorlib]System.Version::get_Revision()
0x1ed78  stloc.s  0xF
0x1ed7a  ldloca.s 0xF
0x1ed7c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1ed81  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1ed86  callvirt instance void Microsoft.Crm.CrmPluginAssemblyMetadata::set_VersionRevision(string value)
0x1ed8b  ldarg.0
0x1ed8c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<unsigned int32, class Microsoft.Crm.CrmPluginAssemblyMetadata> Microsoft.Crm.CrmPluginAssemblyMetadata::_processedModules
0x1ed91  ldarg.1
0x1ed92  ldloc.s  0xA
0x1ed94  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<unsigned int32, class Microsoft.Crm.CrmPluginAssemblyMetadata>::Add(var<u1>, !!T0)
0x1ed99  ldloc.s  0xA
0x1ed9b  stloc.s  0xE
0x1ed9d  leave.s  loc_1EDD1
0x1ed9f  ldloc.0
0x1eda0  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1eda5  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x1edaa  brfalse.s loc_1EDD0
0x1edac  ldloc.0
0x1edad  ldtoken  Microsoft.Crm.ASSEMBLYMETADATA
0x1edb2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1edb7  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x1edbc  unbox.any Microsoft.Crm.ASSEMBLYMETADATA
0x1edc1  stloc.s  0x10
0x1edc3  ldloca.s 0x10
0x1edc5  call     instance void Microsoft.Crm.ASSEMBLYMETADATA::Dispose()
0x1edca  ldloc.0
0x1edcb  call     void Microsoft.Crm.MetaDataInterop::FreeAsmMeta(native int asmMetaPtr)
0x1edd0  endfinally
0x1edd1  ldloc.s  0xE
0x1edd3  ret
```
