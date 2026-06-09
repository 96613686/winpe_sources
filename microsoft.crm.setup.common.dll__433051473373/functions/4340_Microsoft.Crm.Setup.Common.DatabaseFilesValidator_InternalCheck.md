# Microsoft.Crm.Setup.Common.DatabaseFilesValidator::InternalCheck

- ea: `0x4340`
- end: `0x4553`
- name: `Microsoft.Crm.Setup.Common.DatabaseFilesValidator::InternalCheck`
- size: `531`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x2cd0`
- `0x4340`
- `0x4560`
- `0x45f0`

## pseudocode

```c

```

## disassembly

```asm
0x4340  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x4345  stloc.0
0x4346  ldarg.0
0x4347  ldfld    string Microsoft.Crm.Setup.Common.DatabaseFilesValidator::_sqlServerName
0x434c  ldarg.0
0x434d  ldfld    string Microsoft.Crm.Setup.Common.DatabaseFilesValidator::_databaseName
0x4352  call     bool Microsoft.Crm.Setup.Common.DatabaseFilesValidator::DatabaseExists(string serverName, string databaseName)
0x4357  brfalse.s loc_4372
0x4359  ldloc.0
0x435a  call     string [mscorlib]System.Environment::get_NewLine()
0x435f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4364  pop
0x4365  ldloc.0
0x4366  ldarg.0
0x4367  ldfld    string Microsoft.Crm.Setup.Common.DatabaseFilesValidator::_databaseName
0x436c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4371  pop
0x4372  ldloc.0
0x4373  callvirt instance string [mscorlib]System.Object::ToString()
0x4378  stloc.1
0x4379  ldloc.1
0x437a  callvirt instance int32 [mscorlib]System.String::get_Length()
0x437f  ldc.i4.0
0x4380  ble.s    loc_439E
0x4382  ldc.i4.2
0x4383  ldarg.0
0x4384  ldstr    aDatabasefilesv// "DatabaseFilesValidator.Failure.Existing"...
0x4389  ldc.i4.1
0x438a  newarr   [mscorlib]System.Object
0x438f  dup
0x4390  ldc.i4.0
0x4391  ldloc.1
0x4392  stelem.ref
0x4393  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x4398  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x439d  ret
0x439e  ldc.i4.2
0x439f  newarr   [mscorlib]System.String
0x43a4  stloc.2
0x43a5  ldloc.2
0x43a6  ldc.i4.0
0x43a7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x43ac  ldstr    a0Mdf// "{0}.mdf"
0x43b1  ldc.i4.1
0x43b2  newarr   [mscorlib]System.Object
0x43b7  dup
0x43b8  ldc.i4.0
0x43b9  ldarg.0
0x43ba  ldfld    string Microsoft.Crm.Setup.Common.DatabaseFilesValidator::_databaseName
0x43bf  stelem.ref
0x43c0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x43c5  stelem.ref
0x43c6  ldloc.2
0x43c7  ldc.i4.1
0x43c8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x43cd  ldstr    a0LogLdf// "{0}_log.ldf"
0x43d2  ldc.i4.1
0x43d3  newarr   [mscorlib]System.Object
0x43d8  dup
0x43d9  ldc.i4.0
0x43da  ldarg.0
0x43db  ldfld    string Microsoft.Crm.Setup.Common.DatabaseFilesValidator::_databaseName
0x43e0  stelem.ref
0x43e1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x43e6  stelem.ref
0x43e7  ldnull
0x43e8  stloc.3
0x43e9  ldarg.0
0x43ea  ldfld    string Microsoft.Crm.Setup.Common.DatabaseFilesValidator::_sqlServerName
0x43ef  call     string [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.Helpers::GetSqlDBFilesPath(string)
0x43f4  stloc.3
0x43f5  leave    loc_4486
0x43fa  stloc.s  8
0x43fc  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x4401  stloc.s  9
0x4403  ldloc.s  9
0x4405  ldarg.0
0x4406  ldloc.s  8
0x4408  call     instance string [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ConditionBase::BuildExceptionMessage(class [mscorlib]System.Exception)
0x440d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4412  pop
0x4413  ldloc.s  9
0x4415  call     string [mscorlib]System.Environment::get_NewLine()
0x441a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x441f  pop
0x4420  ldloc.s  9
0x4422  ldarg.0
0x4423  ldstr    aDatabasefilesv_0// "DatabaseFilesValidator.Warning.UnableTo"...
0x4428  ldc.i4.0
0x4429  newarr   [mscorlib]System.Object
0x442e  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x4433  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4438  pop
0x4439  ldloc.2
0x443a  stloc.s  0xA
0x443c  ldc.i4.0
0x443d  stloc.s  0xB
0x443f  br.s     loc_446A
0x4441  ldloc.s  0xA
0x4443  ldloc.s  0xB
0x4445  ldelem.ref
0x4446  stloc.s  0xC
0x4448  ldloc.s  9
0x444a  call     string [mscorlib]System.Environment::get_NewLine()
0x444f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4454  pop
0x4455  ldloc.s  9
0x4457  ldloc.s  0xC
0x4459  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x445e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4463  pop
0x4464  ldloc.s  0xB
0x4466  ldc.i4.1
0x4467  add
0x4468  stloc.s  0xB
0x446a  ldloc.s  0xB
0x446c  ldloc.s  0xA
0x446e  ldlen
0x446f  conv.i4
0x4470  blt.s    loc_4441
0x4472  ldc.i4.1
0x4473  ldloc.s  9
0x4475  callvirt instance string [mscorlib]System.Object::ToString()
0x447a  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x447f  stloc.s  0xD
0x4481  leave    loc_4550
0x4486  ldloc.3
0x4487  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x448c  ldstr    a0Mdf// "{0}.mdf"
0x4491  ldc.i4.1
0x4492  newarr   [mscorlib]System.Object
0x4497  dup
0x4498  ldc.i4.0
0x4499  ldarg.0
0x449a  ldfld    string Microsoft.Crm.Setup.Common.DatabaseFilesValidator::_databaseName
0x449f  stelem.ref
0x44a0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x44a5  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x44aa  stloc.s  4
0x44ac  ldloc.3
0x44ad  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x44b2  ldstr    a0LogLdf// "{0}_log.ldf"
0x44b7  ldc.i4.1
0x44b8  newarr   [mscorlib]System.Object
0x44bd  dup
0x44be  ldc.i4.0
0x44bf  ldarg.0
0x44c0  ldfld    string Microsoft.Crm.Setup.Common.DatabaseFilesValidator::_databaseName
0x44c5  stelem.ref
0x44c6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x44cb  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x44d0  stloc.s  5
0x44d2  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x44d7  stloc.s  6
0x44d9  ldarg.0
0x44da  ldarg.0
0x44db  ldfld    string Microsoft.Crm.Setup.Common.DatabaseFilesValidator::_sqlServerName
0x44e0  ldloc.s  4
0x44e2  ldloc.s  5
0x44e4  call     instance bool Microsoft.Crm.Setup.Common.DatabaseFilesValidator::DoDatabaseFilesExist(string serverName, string databaseFile, string logFile)
0x44e9  brfalse.s loc_4519
0x44eb  ldloc.s  6
0x44ed  call     string [mscorlib]System.Environment::get_NewLine()
0x44f2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x44f7  pop
0x44f8  ldloc.s  6
0x44fa  ldloc.s  4
0x44fc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4501  pop
0x4502  ldloc.s  6
0x4504  call     string [mscorlib]System.Environment::get_NewLine()
0x4509  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x450e  pop
0x450f  ldloc.s  6
0x4511  ldloc.s  5
0x4513  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4518  pop
0x4519  ldloc.s  6
0x451b  callvirt instance string [mscorlib]System.Object::ToString()
0x4520  stloc.s  7
0x4522  ldloc.s  7
0x4524  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4529  ldc.i4.0
0x452a  ble.s    loc_4549
0x452c  ldc.i4.2
0x452d  ldarg.0
0x452e  ldstr    aDatabasefilesv_1// "DatabaseFilesValidator.Failure.Existing"...
0x4533  ldc.i4.1
0x4534  newarr   [mscorlib]System.Object
0x4539  dup
0x453a  ldc.i4.0
0x453b  ldloc.s  7
0x453d  stelem.ref
0x453e  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x4543  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x4548  ret
0x4549  ldc.i4.0
0x454a  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult)
0x454f  ret
0x4550  ldloc.s  0xD
0x4552  ret
```
