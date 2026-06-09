# Microsoft.Crm.CrmTemporaryFile::.ctor

- ea: `0x1d1e0`
- end: `0x1d2b5`
- name: `Microsoft.Crm.CrmTemporaryFile::.ctor`
- size: `213`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1d1e0`
- `0x1d350`
- `0x1d3a0`
- `0x1d580`
- `0x1d5e0`
- `0x1d5f0`
- `0x1d600`
- `0x1d610`
- `0x1d620`
- `0x1d630`

## string_xrefs

- `0x1d1fe`: `directoryName`

## pseudocode

```c

```

## disassembly

```asm
0x1d1e0  ldarg.0
0x1d1e1  ldc.i4.4
0x1d1e2  newarr   [mscorlib]System.Byte
0x1d1e7  stfld    unsigned int8[] Microsoft.Crm.CrmTemporaryFile::fileSignatureHeader
0x1d1ec  ldarg.0
0x1d1ed  call     instance void [mscorlib]System.Object::.ctor()
0x1d1f2  ldarg.1
0x1d1f3  ldstr    aFiledata// "fileData"
0x1d1f8  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1d1fd  ldarg.2
0x1d1fe  ldstr    aDirectoryname// "directoryName"
0x1d203  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1d208  ldarg.1
0x1d209  ldlen
0x1d20a  conv.i4
0x1d20b  ldc.i4.4
0x1d20c  blt.s    loc_1D21D
0x1d20e  ldarg.1
0x1d20f  ldc.i4.0
0x1d210  ldarg.0
0x1d211  ldfld    unsigned int8[] Microsoft.Crm.CrmTemporaryFile::fileSignatureHeader
0x1d216  ldc.i4.0
0x1d217  ldc.i4.4
0x1d218  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0x1d21d  ldarg.0
0x1d21e  ldarg.0
0x1d21f  ldarg.2
0x1d220  call     instance string Microsoft.Crm.CrmTemporaryFile::BuildDirectoryName(string directoryName)
0x1d225  call     instance void Microsoft.Crm.CrmTemporaryFile::set_DirectoryName(string value)
0x1d22a  ldarg.0
0x1d22b  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x1d230  stloc.0
0x1d231  ldloca.s 0
0x1d233  ldstr    aN// "N"
0x1d238  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d23d  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x1d242  call     instance void Microsoft.Crm.CrmTemporaryFile::set_FileName(string value)
0x1d247  ldarg.0
0x1d248  ldarg.0
0x1d249  call     instance string Microsoft.Crm.CrmTemporaryFile::get_DirectoryName()
0x1d24e  ldarg.0
0x1d24f  call     instance string Microsoft.Crm.CrmTemporaryFile::get_FileName()
0x1d254  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1d259  call     instance void Microsoft.Crm.CrmTemporaryFile::set_FileFullyQualifiedName(string value)
0x1d25e  ldarg.2
0x1d25f  ldstr    aCustomizationi// "CustomizationImport"
0x1d264  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d269  brfalse.s loc_1D277
0x1d26b  ldarg.0
0x1d26c  ldarg.0
0x1d26d  call     instance string Microsoft.Crm.CrmTemporaryFile::get_DirectoryName()
0x1d272  call     instance void Microsoft.Crm.CrmTemporaryFile::CleanUpFilesInDirectory(string directory)
0x1d277  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0x1d27c  stloc.1
0x1d27d  ldarg.0
0x1d27e  call     instance string Microsoft.Crm.CrmTemporaryFile::get_FileFullyQualifiedName()
0x1d283  ldc.i4.2
0x1d284  newobj   instance void [mscorlib]System.IO.FileStream::.ctor(string, valuetype [mscorlib]System.IO.FileMode)
0x1d289  stloc.2
0x1d28a  ldloc.2
0x1d28b  ldarg.1
0x1d28c  ldc.i4.0
0x1d28d  ldarg.1
0x1d28e  ldlen
0x1d28f  conv.i4
0x1d290  callvirt instance void [mscorlib]System.IO.Stream::Write(unsigned int8[], int32, int32)
0x1d295  leave.s  loc_1D2B4
0x1d297  pop
0x1d298  ldarg.0
0x1d299  call     instance void Microsoft.Crm.CrmTemporaryFile::Dispose()
0x1d29e  rethrow
0x1d2a0  ldloc.2
0x1d2a1  brfalse.s loc_1D2A9
0x1d2a3  ldloc.2
0x1d2a4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d2a9  endfinally
0x1d2aa  ldloc.1
0x1d2ab  brfalse.s loc_1D2B3
0x1d2ad  ldloc.1
0x1d2ae  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d2b3  endfinally
0x1d2b4  ret
```
