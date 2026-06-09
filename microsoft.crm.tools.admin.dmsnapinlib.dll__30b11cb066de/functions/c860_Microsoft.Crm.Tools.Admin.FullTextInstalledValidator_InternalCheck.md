# Microsoft.Crm.Tools.Admin.FullTextInstalledValidator::InternalCheck

- ea: `0xc860`
- end: `0xc8a1`
- name: `Microsoft.Crm.Tools.Admin.FullTextInstalledValidator::InternalCheck`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x84f0`
- `0x8bf0`
- `0xc860`

## string_xrefs

- `0xc879`: `FullTextInstalledValidator.Failure.NotInstalled`

## pseudocode

```c

```

## disassembly

```asm
0xc860  ldarg.1
0xc861  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0xc866  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerName()
0xc86b  call     bool [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.SqlUtility::IsFullTextInstalled(string)
0xc870  brtrue.s loc_C89A
0xc872  ldc.i4.2
0xc873  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0xc878  ldarg.0
0xc879  ldstr    aFulltextinstal// "FullTextInstalledValidator.Failure.NotI"...
0xc87e  ldc.i4.0
0xc87f  newarr   [mscorlib]System.Object
0xc884  call     instance string [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.Validator::GetResourceString(string, object[])
0xc889  ldc.i4.0
0xc88a  newarr   [mscorlib]System.Object
0xc88f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xc894  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0xc899  ret
0xc89a  ldc.i4.0
0xc89b  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult)
0xc8a0  ret
```
