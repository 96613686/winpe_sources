# Microsoft.Crm.Asynchronous.ImportOperation::SetupForSampleData

- ea: `0xb9e0`
- end: `0xba35`
- name: `Microsoft.Crm.Asynchronous.ImportOperation::SetupForSampleData`
- size: `85`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0xbe60`
- `0xe0e0`
- `0x14350`
- `0x16550`

## callees

- `0xadf0`

## pseudocode

```c

```

## disassembly

```asm
0xb9e0  ldarg.0
0xb9e1  ldarg.1
0xb9e2  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.ImportOperation::_crmService
0xb9e7  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.ImportOperation::_crmService
0xb9ec  ldarg.0
0xb9ed  ldarg.1
0xb9ee  ldfld    int32 Microsoft.Crm.Asynchronous.ImportOperation::_languageCode
0xb9f3  stfld    int32 Microsoft.Crm.Asynchronous.ImportOperation::_languageCode
0xb9f8  ldarg.0
0xb9f9  ldarg.1
0xb9fa  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0xb9ff  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0xba04  ldarg.0
0xba05  ldarg.1
0xba06  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0xba0b  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0xba10  ldarg.0
0xba11  ldarg.1
0xba12  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0xba17  stfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0xba1c  ldarg.0
0xba1d  ldarg.1
0xba1e  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ImportOperation::_asyncEvent
0xba23  stfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ImportOperation::_asyncEvent
0xba28  ldarg.0
0xba29  ldarg.0
0xba2a  call     instance class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Asynchronous.ImportOperation::GetUserLocale()
0xba2f  stfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Asynchronous.ImportOperation::_userCultureInfo
0xba34  ret
```
