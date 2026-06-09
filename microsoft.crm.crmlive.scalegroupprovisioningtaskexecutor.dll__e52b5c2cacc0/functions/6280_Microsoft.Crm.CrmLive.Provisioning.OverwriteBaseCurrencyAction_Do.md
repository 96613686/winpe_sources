# Microsoft.Crm.CrmLive.Provisioning.OverwriteBaseCurrencyAction::Do

- ea: `0x6280`
- end: `0x6370`
- name: `Microsoft.Crm.CrmLive.Provisioning.OverwriteBaseCurrencyAction::Do`
- size: `240`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x6280`
- `0x6380`
- `0x64b0`
- `0x91b0`
- `0x9310`
- `0x9330`
- `0x9350`
- `0x9370`

## string_xrefs

- `0x62b0`: `\n\nIF EXISTS(SELECT * FROM TransactionCurrencyBase WHERE ISOCurrencyCode=@Code)\nBEGIN\n   -- Currency code already exists\n   -- Update it with correct value\n   UPDATE TransactionCurrencyBase \n       SET CurrencySymbol=@Symbol,CurrencyName=@Name,CurrencyPrecision=@Precision,ExchangeRate=1\n       WHERE ISOCurrencyCode=@Code\n\n   -- And make sure this is the base currency\n   UPDATE OrganizationBase SET BaseCurrencyId=(SELECT TransactionCurrencyId FROM TransactionCurrencyBase WHER`

## pseudocode

```c

```

## disassembly

```asm
0x6280  ldarg.0
0x6281  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x6286  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_CurrencyCode()
0x628b  brfalse  loc_6364
0x6290  ldarg.0
0x6291  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x6296  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_CurrencyName()
0x629b  brfalse  loc_6364
0x62a0  ldarg.0
0x62a1  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x62a6  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_CurrencySymbol()
0x62ab  brfalse  loc_6364
0x62b0  ldstr    aIfExistsSelect// "\r\n\r\nIF EXISTS(SELECT * FROM Transac"...
0x62b5  stloc.0
0x62b6  ldarg.0
0x62b7  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x62bc  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x62c1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x62c6  ldc.i4.0
0x62c7  ldc.i4.0
0x62c8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x62cd  stloc.1
0x62ce  ldloc.1
0x62cf  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x62d4  ldloc.1
0x62d5  ldloc.0
0x62d6  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x62db  stloc.2
0x62dc  ldloc.2
0x62dd  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x62e2  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x62e7  dup
0x62e8  ldstr    aSymbol// "@Symbol"
0x62ed  ldarg.0
0x62ee  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x62f3  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_CurrencySymbol()
0x62f8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x62fd  pop
0x62fe  dup
0x62ff  ldstr    aName_1// "@Name"
0x6304  ldarg.0
0x6305  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x630a  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_CurrencyName()
0x630f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6314  pop
0x6315  dup
0x6316  ldstr    aCode// "@Code"
0x631b  ldarg.0
0x631c  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x6321  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_CurrencyCode()
0x6326  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x632b  pop
0x632c  ldstr    aPrecision// "@Precision"
0x6331  ldarg.0
0x6332  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x6337  callvirt instance int32 Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_CurrencyPrecision()
0x633c  box      [mscorlib]System.Int32
0x6341  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6346  pop
0x6347  ldloc.2
0x6348  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x634d  pop
0x634e  leave.s  loc_6364
0x6350  ldloc.2
0x6351  brfalse.s loc_6359
0x6353  ldloc.2
0x6354  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6359  endfinally
0x635a  ldloc.1
0x635b  brfalse.s loc_6363
0x635d  ldloc.1
0x635e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6363  endfinally
0x6364  ldarg.0
0x6365  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x636a  call     void Microsoft.Crm.CrmLive.Provisioning.OverwriteBaseCurrencyActionHelper::TryUpdateLocaleIdForOrganizationAndInitialUsers(class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties organizationProperties)
0x636f  ret
```
