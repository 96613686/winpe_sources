# Microsoft.Crm.Common.Web.Controls.EmailBody.MessageBodyPage::.cctor

- ea: `0xfc50`
- end: `0xfc84`
- name: `Microsoft.Crm.Common.Web.Controls.EmailBody.MessageBodyPage::.cctor`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0xfc61`: `&?(amp;)?CRMWRPCToken=[A-Za-z0-9%/]+`
- `0xfc72`: `&?(amp;)?CRMWRPCTokenTimeStamp=[0-9]+`

## pseudocode

```c

```

## disassembly

```asm
0xfc50  ldstr    aSrcActivitiesA// "src=\".*?\\/Activities\\/Attachment\\/d"...
0xfc55  ldc.i4.s 9
0xfc57  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0xfc5c  stsfld   class [System]System.Text.RegularExpressions.Regex Microsoft.Crm.Common.Web.Controls.EmailBody.MessageBodyPage::_wrpcInjectionRegEx
0xfc61  ldstr    aAmpCrmwrpctoke// "&?(amp;)?CRMWRPCToken=[A-Za-z0-9%/]+"
0xfc66  ldc.i4.s 9
0xfc68  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0xfc6d  stsfld   class [System]System.Text.RegularExpressions.Regex Microsoft.Crm.Common.Web.Controls.EmailBody.MessageBodyPage::_wrpcTokenRegEx
0xfc72  ldstr    aAmpCrmwrpctoke_0// "&?(amp;)?CRMWRPCTokenTimeStamp=[0-9]+"
0xfc77  ldc.i4.s 9
0xfc79  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0xfc7e  stsfld   class [System]System.Text.RegularExpressions.Regex Microsoft.Crm.Common.Web.Controls.EmailBody.MessageBodyPage::_wrpcTokenTimeStampRegEx
0xfc83  ret
```
