# Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsageRetriever::CreateDataFromReader

- ea: `0xa5e0`
- end: `0xa6c2`
- name: `Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsageRetriever::CreateDataFromReader`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0xa570`

## callees

- `0xa450`
- `0xa470`
- `0xa490`
- `0xa4b0`
- `0xa4d0`
- `0xa4f0`
- `0xa510`
- `0xa530`
- `0xa540`
- `0xa5e0`

## pseudocode

```c

```

## disassembly

```asm
0xa5e0  newobj   instance void Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsage::.ctor()
0xa5e5  dup
0xa5e6  ldarg.0
0xa5e7  ldstr    aCurrentsizeinm// "CurrentSizeInMB"
0xa5ec  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xa5f1  unbox.any [mscorlib]System.Decimal
0xa5f6  call     float64 [mscorlib]System.Decimal::ToDouble(valuetype [mscorlib]System.Decimal)
0xa5fb  callvirt instance void Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsage::set_CurrentSizeInMB(float64 value)
0xa600  dup
0xa601  ldarg.0
0xa602  ldstr    aFilesizeinmb// "FileSizeInMB"
0xa607  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xa60c  unbox.any [mscorlib]System.Decimal
0xa611  call     float64 [mscorlib]System.Decimal::ToDouble(valuetype [mscorlib]System.Decimal)
0xa616  callvirt instance void Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsage::set_FileSizeInMB(float64 value)
0xa61b  dup
0xa61c  ldarg.0
0xa61d  ldstr    aTlogusage// "TLogUsage"
0xa622  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xa627  unbox.any [mscorlib]System.Decimal
0xa62c  call     float64 [mscorlib]System.Decimal::ToDouble(valuetype [mscorlib]System.Decimal)
0xa631  callvirt instance void Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsage::set_TLogUsage(float64 value)
0xa636  dup
0xa637  ldarg.0
0xa638  ldstr    aDatabasename// "DatabaseName"
0xa63d  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xa642  castclass [mscorlib]System.String
0xa647  callvirt instance void Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsage::set_DatabaseName(string value)
0xa64c  dup
0xa64d  ldarg.0
0xa64e  ldstr    aAvailabledrive// "AvailableDriveBytes"
0xa653  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xa658  unbox.any [mscorlib]System.Int64
0xa65d  callvirt instance void Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsage::set_FreeDriveBytes(int64 value)
0xa662  dup
0xa663  ldarg.0
0xa664  ldstr    aTotaldrivebyte// "TotalDriveBytes"
0xa669  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xa66e  unbox.any [mscorlib]System.Int64
0xa673  callvirt instance void Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsage::set_TotalDriveBytes(int64 value)
0xa678  dup
0xa679  ldarg.0
0xa67a  ldstr    aVolumeid// "VolumeId"
0xa67f  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xa684  castclass [mscorlib]System.String
0xa689  callvirt instance void Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsage::set_VolumeId(string value)
0xa68e  dup
0xa68f  ldarg.0
0xa690  ldstr    aLastlogbackup// "LastLogBackup"
0xa695  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xa69a  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xa69f  beq.s    loc_A6B3
0xa6a1  ldarg.0
0xa6a2  ldstr    aLastlogbackup// "LastLogBackup"
0xa6a7  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xa6ac  unbox.any valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0xa6b1  br.s     loc_A6BC
0xa6b3  ldloca.s 0
0xa6b5  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0xa6bb  ldloc.0
0xa6bc  callvirt instance void Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsage::set_LastBackup(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> value)
0xa6c1  ret
```
