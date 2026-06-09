# Microsoft.Crm.Extensibility.OrganizationDataService::LoadEntitySetRights

- ea: `0x71a0`
- end: `0x72a9`
- name: `Microsoft.Crm.Extensibility.OrganizationDataService::LoadEntitySetRights`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x70e0`

## callees

- `0x71a0`

## string_xrefs

- `0x71ca`: `Update`
- `0x71a6`: `Create`
- `0x71d7`: `Delete`
- `0x720a`: `\nwith m (SdkMessageId,Name)\nas \n(\nselect SdkMessageId, Name \nfrom SdkMessageBase\nwhere Name in ('Create','Retrieve','RetrieveMultiple','Update','Delete')\n)\nselect f.PrimaryObjectTypeCode, m.Name, f.IsVisible\nfrom SdkMessageFilterBase f \njoin m on (f.SdkMessageId = m.SdkMessageId)\nand f.CustomizationLevel = 0\n`
- `0x7220`: `D:\a\1\s\src\Extensibility\Sdk\OrganizationDataService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x71a0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [System.Data.Services]System.Data.Services.EntitySetRights>::.ctor()
0x71a5  dup
0x71a6  ldstr    aCreate// "Create"
0x71ab  ldc.i4.4
0x71ac  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [System.Data.Services]System.Data.Services.EntitySetRights>::Add(var<u1>, !!T0)
0x71b1  dup
0x71b2  ldstr    aRetrieve// "Retrieve"
0x71b7  ldc.i4.1
0x71b8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [System.Data.Services]System.Data.Services.EntitySetRights>::Add(var<u1>, !!T0)
0x71bd  dup
0x71be  ldstr    aRetrievemultip// "RetrieveMultiple"
0x71c3  ldc.i4.2
0x71c4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [System.Data.Services]System.Data.Services.EntitySetRights>::Add(var<u1>, !!T0)
0x71c9  dup
0x71ca  ldstr    aUpdate// "Update"
0x71cf  ldc.i4.s 0x28
0x71d1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [System.Data.Services]System.Data.Services.EntitySetRights>::Add(var<u1>, !!T0)
0x71d6  dup
0x71d7  ldstr    aDelete// "Delete"
0x71dc  ldc.i4.s 0x10
0x71de  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [System.Data.Services]System.Data.Services.EntitySetRights>::Add(var<u1>, !!T0)
0x71e3  stloc.0
0x71e4  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System.Data.Services]System.Data.Services.EntitySetRights>::.ctor()
0x71e9  stloc.1
0x71ea  ldc.i4.0
0x71eb  stloc.2
0x71ec  ldarg.0
0x71ed  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x71f2  ldc.i4.0
0x71f3  ldc.i4.0
0x71f4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x71f9  stloc.3
0x71fa  ldloc.3
0x71fb  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x7200  ldloc.3
0x7201  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x7206  stloc.s  4
0x7208  ldloc.s  4
0x720a  ldstr    aWithMSdkmessag// "\r\nwith m (SdkMessageId,Name)\r\nas \r"...
0x720f  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x7214  ldloc.s  4
0x7216  ldc.i4   0x127
0x721b  ldstr    aLoadentitysetr// "LoadEntitySetRights"
0x7220  ldstr    aDA1SSrcExtensi_0// "D:\\a\\1\\s\\src\\Extensibility\\Sdk\\O"...
0x7225  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x722a  stloc.s  5
0x722c  br.s     loc_727A
0x722e  ldloc.s  5
0x7230  ldc.i4.0
0x7231  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(int32)
0x7236  unbox.any [mscorlib]System.Int32
0x723b  stloc.s  6
0x723d  ldloc.s  5
0x723f  ldc.i4.1
0x7240  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(int32)
0x7245  isinst   [mscorlib]System.String
0x724a  stloc.s  7
0x724c  ldloc.s  5
0x724e  ldc.i4.2
0x724f  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(int32)
0x7254  unbox.any [mscorlib]System.Boolean
0x7259  brfalse.s loc_727A
0x725b  ldloc.1
0x725c  ldloc.s  6
0x725e  ldloca.s 2
0x7260  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System.Data.Services]System.Data.Services.EntitySetRights>::TryGetValue(var<u1>, !!T0)
0x7265  pop
0x7266  ldloc.2
0x7267  ldloc.0
0x7268  ldloc.s  7
0x726a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [System.Data.Services]System.Data.Services.EntitySetRights>::get_Item(void)
0x726f  or
0x7270  stloc.2
0x7271  ldloc.1
0x7272  ldloc.s  6
0x7274  ldloc.2
0x7275  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [System.Data.Services]System.Data.Services.EntitySetRights>::set_Item(var<u1>, !!T0)
0x727a  ldloc.s  5
0x727c  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x7281  brtrue.s loc_722E
0x7283  leave.s  loc_72A7
0x7285  ldloc.s  5
0x7287  brfalse.s loc_7290
0x7289  ldloc.s  5
0x728b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7290  endfinally
0x7291  ldloc.s  4
0x7293  brfalse.s loc_729C
0x7295  ldloc.s  4
0x7297  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x729c  endfinally
0x729d  ldloc.3
0x729e  brfalse.s loc_72A6
0x72a0  ldloc.3
0x72a1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x72a6  endfinally
0x72a7  ldloc.1
0x72a8  ret
```
