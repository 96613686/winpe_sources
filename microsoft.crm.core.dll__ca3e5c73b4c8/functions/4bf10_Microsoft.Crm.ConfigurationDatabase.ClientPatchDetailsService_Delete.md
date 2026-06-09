# Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::Delete

- ea: `0x4bf10`
- end: `0x4c000`
- name: `Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::Delete`
- size: `240`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1be90`
- `0x44400`
- `0x44510`
- `0x4bf10`
- `0x625b0`

## string_xrefs

- `0x4bfe5`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\ClientPatchDetails.cs`
- `0x4bfe0`: `Delete`

## pseudocode

```c

```

## disassembly

```asm
0x4bf10  ldarg.1
0x4bf11  ldstr    aPatchid_0// "patchId"
0x4bf16  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0x4bf1b  ldc.i4.3
0x4bf1c  newarr   [mscorlib]System.String
0x4bf21  dup
0x4bf22  ldc.i4.0
0x4bf23  ldstr    aClientpatchdet// "ClientPatchDetails"
0x4bf28  stelem.ref
0x4bf29  dup
0x4bf2a  ldc.i4.1
0x4bf2b  ldstr    aClientpatchreq// "ClientPatchRequiredInfo"
0x4bf30  stelem.ref
0x4bf31  dup
0x4bf32  ldc.i4.2
0x4bf33  ldstr    aClientpatchcon// "ClientPatchContainedInfo"
0x4bf38  stelem.ref
0x4bf39  stloc.0
0x4bf3a  ldc.i4.3
0x4bf3b  newarr   string[]
0x4bf40  dup
0x4bf41  ldc.i4.0
0x4bf42  ldc.i4.1
0x4bf43  newarr   [mscorlib]System.String
0x4bf48  dup
0x4bf49  ldc.i4.0
0x4bf4a  ldstr    aPatchid// "PatchId"
0x4bf4f  stelem.ref
0x4bf50  stelem.ref
0x4bf51  dup
0x4bf52  ldc.i4.1
0x4bf53  ldc.i4.2
0x4bf54  newarr   [mscorlib]System.String
0x4bf59  dup
0x4bf5a  ldc.i4.0
0x4bf5b  ldstr    aPatchid// "PatchId"
0x4bf60  stelem.ref
0x4bf61  dup
0x4bf62  ldc.i4.1
0x4bf63  ldstr    aRequiredpatchi// "RequiredPatchId"
0x4bf68  stelem.ref
0x4bf69  stelem.ref
0x4bf6a  dup
0x4bf6b  ldc.i4.2
0x4bf6c  ldc.i4.2
0x4bf6d  newarr   [mscorlib]System.String
0x4bf72  dup
0x4bf73  ldc.i4.0
0x4bf74  ldstr    aPatchid// "PatchId"
0x4bf79  stelem.ref
0x4bf7a  dup
0x4bf7b  ldc.i4.1
0x4bf7c  ldstr    aContainedpatch// "ContainedPatchId"
0x4bf81  stelem.ref
0x4bf82  stelem.ref
0x4bf83  stloc.1
0x4bf84  ldc.i4.0
0x4bf85  stloc.2
0x4bf86  br.s     loc_4BFF9
0x4bf88  nop
0x4bf89  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Data.PropertyBag>::.ctor()
0x4bf8e  stloc.3
0x4bf8f  ldloc.1
0x4bf90  ldloc.2
0x4bf91  ldelem.ref
0x4bf92  stloc.s  4
0x4bf94  ldc.i4.0
0x4bf95  stloc.s  5
0x4bf97  br.s     loc_4BFC4
0x4bf99  ldloc.s  4
0x4bf9b  ldloc.s  5
0x4bf9d  ldelem.ref
0x4bf9e  stloc.s  6
0x4bfa0  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x4bfa5  stloc.s  7
0x4bfa7  ldloc.s  7
0x4bfa9  ldloc.s  6
0x4bfab  ldarg.1
0x4bfac  box      [mscorlib]System.Guid
0x4bfb1  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4bfb6  ldloc.3
0x4bfb7  ldloc.s  7
0x4bfb9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Data.PropertyBag>::Add(var<u1>)
0x4bfbe  ldloc.s  5
0x4bfc0  ldc.i4.1
0x4bfc1  add
0x4bfc2  stloc.s  5
0x4bfc4  ldloc.s  5
0x4bfc6  ldloc.s  4
0x4bfc8  ldlen
0x4bfc9  conv.i4
0x4bfca  blt.s    loc_4BF99
0x4bfcc  ldarg.0
0x4bfcd  ldfld    class Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::_configService
0x4bfd2  ldloc.0
0x4bfd3  ldloc.2
0x4bfd4  ldelem.ref
0x4bfd5  ldloc.3
0x4bfd6  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Data.PropertyBag>::ToArray()
0x4bfdb  ldc.i4   0x19C
0x4bfe0  ldstr    aDelete_0// "Delete"
0x4bfe5  ldstr    aDA1SSrcPlatfor_35// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4bfea  callvirt instance int32 Microsoft.Crm.SharedDatabase.DatabaseService::Delete(string tableName, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4bfef  pop
0x4bff0  leave.s  loc_4BFF5
0x4bff2  pop
0x4bff3  leave.s  loc_4BFF5
0x4bff5  ldloc.2
0x4bff6  ldc.i4.1
0x4bff7  add
0x4bff8  stloc.2
0x4bff9  ldloc.2
0x4bffa  ldloc.0
0x4bffb  ldlen
0x4bffc  conv.i4
0x4bffd  blt.s    loc_4BF88
0x4bfff  ret
```
