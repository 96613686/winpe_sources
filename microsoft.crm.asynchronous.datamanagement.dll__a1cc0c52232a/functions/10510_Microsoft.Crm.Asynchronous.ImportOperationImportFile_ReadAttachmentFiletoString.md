# Microsoft.Crm.Asynchronous.ImportOperationImportFile::ReadAttachmentFiletoString

- ea: `0x10510`
- end: `0x10620`
- name: `Microsoft.Crm.Asynchronous.ImportOperationImportFile::ReadAttachmentFiletoString`
- size: `272`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x10510`

## pseudocode

```c

```

## disassembly

```asm
0x10510  ldarg.s  4
0x10512  ldc.i4.0
0x10513  stind.i1
0x10514  ldc.i4.0
0x10515  stloc.0
0x10516  ldarg.1
0x10517  ldarg.2
0x10518  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1051d  stloc.1
0x1051e  ldarg.1
0x1051f  ldstr    aAttachments// "Attachments"
0x10524  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x10529  ldarg.2
0x1052a  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1052f  stloc.2
0x10530  ldarg.1
0x10531  ldstr    aDocuments// "Documents"
0x10536  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1053b  ldarg.2
0x1053c  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x10541  stloc.3
0x10542  ldsfld   string [mscorlib]System.String::Empty
0x10547  stloc.s  4
0x10549  ldloc.1
0x1054a  call     bool [mscorlib]System.IO.File::Exists(string)
0x1054f  ldloc.2
0x10550  call     bool [mscorlib]System.IO.File::Exists(string)
0x10555  stloc.s  5
0x10557  ldloc.3
0x10558  call     bool [mscorlib]System.IO.File::Exists(string)
0x1055d  stloc.s  6
0x1055f  brfalse.s loc_10577
0x10561  ldc.i4.1
0x10562  stloc.0
0x10563  ldloc.1
0x10564  stloc.s  4
0x10566  ldloc.s  5
0x10568  ldloc.s  6
0x1056a  or
0x1056b  brfalse.s loc_10597
0x1056d  ldarg.s  4
0x1056f  ldc.i4.1
0x10570  stind.i1
0x10571  ldsfld   string [mscorlib]System.String::Empty
0x10576  ret
0x10577  ldloc.s  5
0x10579  brfalse.s loc_1058E
0x1057b  ldc.i4.1
0x1057c  stloc.0
0x1057d  ldloc.2
0x1057e  stloc.s  4
0x10580  ldloc.s  6
0x10582  brfalse.s loc_10597
0x10584  ldarg.s  4
0x10586  ldc.i4.1
0x10587  stind.i1
0x10588  ldsfld   string [mscorlib]System.String::Empty
0x1058d  ret
0x1058e  ldloc.s  6
0x10590  brfalse.s loc_10597
0x10592  ldc.i4.1
0x10593  stloc.0
0x10594  ldloc.3
0x10595  stloc.s  4
0x10597  ldloc.0
0x10598  brfalse.s loc_10617
0x1059a  ldloc.s  4
0x1059c  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x105a1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x105a6  ldarg.3
0x105a7  ldarg.3
0x105a8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x105ad  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x105b2  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_MaxUploadFileSize()
0x105b7  stloc.s  7
0x105b9  callvirt instance int64 [mscorlib]System.IO.FileInfo::get_Length()
0x105be  ldloc.s  7
0x105c0  conv.i8
0x105c1  ble.s    loc_105D4
0x105c3  ldc.i4   0x80044A02
0x105c8  ldc.i4.0
0x105c9  newarr   [mscorlib]System.Object
0x105ce  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x105d3  throw
0x105d4  ldloc.s  4
0x105d6  call     class [mscorlib]System.IO.FileStream [mscorlib]System.IO.File::OpenRead(string)
0x105db  stloc.s  8
0x105dd  ldloc.s  8
0x105df  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x105e4  conv.ovf.i
0x105e5  newarr   [mscorlib]System.Byte
0x105ea  stloc.s  9
0x105ec  ldloc.s  8
0x105ee  ldloc.s  9
0x105f0  ldc.i4.0
0x105f1  ldloc.s  9
0x105f3  ldlen
0x105f4  conv.i4
0x105f5  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x105fa  pop
0x105fb  ldloc.s  9
0x105fd  ldc.i4.0
0x105fe  ldloc.s  9
0x10600  ldlen
0x10601  conv.i4
0x10602  call     string [mscorlib]System.Convert::ToBase64String(unsigned int8[], int32, int32)
0x10607  stloc.s  0xA
0x10609  leave.s  loc_1061D
0x1060b  ldloc.s  8
0x1060d  brfalse.s loc_10616
0x1060f  ldloc.s  8
0x10611  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10616  endfinally
0x10617  newobj   instance void [mscorlib]System.IO.FileNotFoundException::.ctor()
0x1061c  throw
0x1061d  ldloc.s  0xA
0x1061f  ret
```
