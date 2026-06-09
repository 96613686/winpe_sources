# Microsoft.Crm.Asynchronous.TransactionLogBackupDataRetriever::CreateDataFromReader

- ea: `0xb270`
- end: `0xb30e`
- name: `Microsoft.Crm.Asynchronous.TransactionLogBackupDataRetriever::CreateDataFromReader`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0xb160`

## callees

- `0xac70`
- `0xacc0`
- `0xace0`
- `0xad00`
- `0xad20`
- `0xb270`
- `0xfbd0`

## pseudocode

```c

```

## disassembly

```asm
0xb270  newobj   instance void <>c__DisplayClass1_0::.ctor()
0xb275  stloc.0
0xb276  ldloc.0
0xb277  ldarg.0
0xb278  stfld    class [System.Data]System.Data.IDataReader <>c__DisplayClass1_0::reader
0xb27d  ldarg.1
0xb27e  ldloc.0
0xb27f  ldftn    instance bool <>c__DisplayClass1_0::<CreateDataFromReader>b__0(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData db)
0xb285  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData, bool>::.ctor(object, native int)
0xb28a  call     T0x2B000024
0xb28f  stloc.1
0xb290  newobj   instance void Microsoft.Crm.Asynchronous.TransactionLogBackupData::.ctor()
0xb295  dup
0xb296  ldloc.1
0xb297  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0xb29c  callvirt instance void Microsoft.Crm.Asynchronous.TransactionLogBackupData::set_OrganizationId(valuetype [mscorlib]System.Guid value)
0xb2a1  dup
0xb2a2  ldloc.1
0xb2a3  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_DatabaseName()
0xb2a8  callvirt instance void Microsoft.Crm.Asynchronous.TransactionLogBackupData::set_DatabaseName(string value)
0xb2ad  dup
0xb2ae  ldloc.0
0xb2af  ldfld    class [System.Data]System.Data.IDataReader <>c__DisplayClass1_0::reader
0xb2b4  ldstr    aBackupfinishda// "BackupFinishDate"
0xb2b9  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xb2be  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xb2c3  beq.s    loc_B2DC
0xb2c5  ldloc.0
0xb2c6  ldfld    class [System.Data]System.Data.IDataReader <>c__DisplayClass1_0::reader
0xb2cb  ldstr    aBackupfinishda// "BackupFinishDate"
0xb2d0  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xb2d5  unbox.any valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0xb2da  br.s     loc_B2E5
0xb2dc  ldloca.s 2
0xb2de  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0xb2e4  ldloc.2
0xb2e5  callvirt instance void Microsoft.Crm.Asynchronous.TransactionLogBackupData::set_LastBackupDateTime(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> value)
0xb2ea  dup
0xb2eb  ldloc.1
0xb2ec  callvirt instance int32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_MajorVersion()
0xb2f1  ldloc.1
0xb2f2  callvirt instance int32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_MinorVersion()
0xb2f7  ldloc.1
0xb2f8  callvirt instance int32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_BuildNumber()
0xb2fd  ldloc.1
0xb2fe  callvirt instance int32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Revision()
0xb303  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0xb308  callvirt instance void Microsoft.Crm.Asynchronous.TransactionLogBackupData::set_OrganizationVersion(class [mscorlib]System.Version value)
0xb30d  ret
```
