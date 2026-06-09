# Microsoft.Crm.Tools.Admin.SqlEncryptionActivationValidator::InternalCheck

- ea: `0xd1e0`
- end: `0xd217`
- name: `Microsoft.Crm.Tools.Admin.SqlEncryptionActivationValidator::InternalCheck`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x22e0`
- `0xd1e0`
- `0xd220`

## string_xrefs

- `0xd1e9`: `Data encryption will be active after the install or upgrade. We strongly recommend that you copy the organization encryption key and store it in a safe place. For more information, see http://go.microsoft.com/fwlink/?LinkId=316366.`

## pseudocode

```c

```

## disassembly

```asm
0xd1e0  ldarg.0
0xd1e1  ldarg.1
0xd1e2  call     instance bool Microsoft.Crm.Tools.Admin.SqlEncryptionActivationValidator::WillSqlEncryptionGetActived(class [mscorlib]System.Collections.IDictionary parameters)
0xd1e7  brfalse.s loc_D210
0xd1e9  ldstr    aDataEncryption// "Data encryption will be active after th"...
0xd1ee  ldc.i4.0
0xd1ef  newarr   [mscorlib]System.Object
0xd1f4  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarning(string, object[])
0xd1f9  ldc.i4.1
0xd1fa  ldstr    aSqlencryptiona// "SqlEncryptionActivationValidator.Warnin"...
0xd1ff  ldc.i4.0
0xd200  newarr   [mscorlib]System.Object
0xd205  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0xd20a  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0xd20f  ret
0xd210  ldc.i4.0
0xd211  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult)
0xd216  ret
```
