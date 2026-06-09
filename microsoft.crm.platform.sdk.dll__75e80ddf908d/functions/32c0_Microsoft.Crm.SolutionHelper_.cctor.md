# Microsoft.Crm.SolutionHelper::.cctor

- ea: `0x32c0`
- end: `0x3443`
- name: `Microsoft.Crm.SolutionHelper::.cctor`
- size: `387`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x2e30`

## string_xrefs

- `0x341a`: `msdynce_CRMExtensions`
- `0x3423`: `msdynce_CRMExtensions`
- `0x32c9`: `msdynce_AppCommon`
- `0x32d1`: `msdynce_AppCommon`
- `0x3308`: `msdynce_ServiceLevelAgreement`
- `0x3310`: `msdynce_ServiceLevelAgreement`
- `0x33a7`: `msdynce_Service`
- `0x33b0`: `msdynce_Service`
- `0x33d5`: `msdynce_SalesService`
- `0x33de`: `msdynce_SalesService`
- `0x3403`: `msdynce_MarketingService`
- `0x340c`: `msdynce_MarketingService`

## pseudocode

```c

```

## disassembly

```asm
0x32c0  ldc.i4.s 0x20
0x32c2  newarr   [mscorlib]System.String
0x32c7  dup
0x32c8  ldc.i4.0
0x32c9  ldstr    aMsdynceAppcomm// "msdynce_AppCommon"
0x32ce  stelem.ref
0x32cf  dup
0x32d0  ldc.i4.1
0x32d1  ldstr    aMsdynceAppcomm// "msdynce_AppCommon"
0x32d6  call     string Microsoft.Crm.SolutionHelper::GetHoldingSolutionName(string solutionName)
0x32db  stelem.ref
0x32dc  dup
0x32dd  ldc.i4.2
0x32de  ldstr    aMsdynceSocialp// "msdynce_SocialProfile"
0x32e3  stelem.ref
0x32e4  dup
0x32e5  ldc.i4.3
0x32e6  ldstr    aMsdynceSocialp// "msdynce_SocialProfile"
0x32eb  call     string Microsoft.Crm.SolutionHelper::GetHoldingSolutionName(string solutionName)
0x32f0  stelem.ref
0x32f1  dup
0x32f2  ldc.i4.4
0x32f3  ldstr    aMsdynceActivit// "msdynce_Activities"
0x32f8  stelem.ref
0x32f9  dup
0x32fa  ldc.i4.5
0x32fb  ldstr    aMsdynceActivit// "msdynce_Activities"
0x3300  call     string Microsoft.Crm.SolutionHelper::GetHoldingSolutionName(string solutionName)
0x3305  stelem.ref
0x3306  dup
0x3307  ldc.i4.6
0x3308  ldstr    aMsdynceService// "msdynce_ServiceLevelAgreement"
0x330d  stelem.ref
0x330e  dup
0x330f  ldc.i4.7
0x3310  ldstr    aMsdynceService// "msdynce_ServiceLevelAgreement"
0x3315  call     string Microsoft.Crm.SolutionHelper::GetHoldingSolutionName(string solutionName)
0x331a  stelem.ref
0x331b  dup
0x331c  ldc.i4.8
0x331d  ldstr    aMsdynceKnowled// "msdynce_KnowledgeManagement"
0x3322  stelem.ref
0x3323  dup
0x3324  ldc.i4.s 9
0x3326  ldstr    aMsdynceKnowled// "msdynce_KnowledgeManagement"
0x332b  call     string Microsoft.Crm.SolutionHelper::GetHoldingSolutionName(string solutionName)
0x3330  stelem.ref
0x3331  dup
0x3332  ldc.i4.s 0xA
0x3334  ldstr    aMsdynceClientu// "msdynce_ClientUtility"
0x3339  stelem.ref
0x333a  dup
0x333b  ldc.i4.s 0xB
0x333d  ldstr    aMsdynceClientu// "msdynce_ClientUtility"
0x3342  call     string Microsoft.Crm.SolutionHelper::GetHoldingSolutionName(string solutionName)
0x3347  stelem.ref
0x3348  dup
0x3349  ldc.i4.s 0xC
0x334b  ldstr    aMsdynceLeadman// "msdynce_LeadManagement"
0x3350  stelem.ref
0x3351  dup
0x3352  ldc.i4.s 0xD
0x3354  ldstr    aMsdynceLeadman// "msdynce_LeadManagement"
0x3359  call     string Microsoft.Crm.SolutionHelper::GetHoldingSolutionName(string solutionName)
0x335e  stelem.ref
0x335f  dup
0x3360  ldc.i4.s 0xE
0x3362  ldstr    aMsdynceProduct// "msdynce_ProductManagement"
0x3367  stelem.ref
0x3368  dup
0x3369  ldc.i4.s 0xF
0x336b  ldstr    aMsdynceProduct// "msdynce_ProductManagement"
0x3370  call     string Microsoft.Crm.SolutionHelper::GetHoldingSolutionName(string solutionName)
0x3375  stelem.ref
0x3376  dup
0x3377  ldc.i4.s 0x10
0x3379  ldstr    aMsdynceSchedul// "msdynce_Scheduling"
0x337e  stelem.ref
0x337f  dup
0x3380  ldc.i4.s 0x11
0x3382  ldstr    aMsdynceSchedul// "msdynce_Scheduling"
0x3387  call     string Microsoft.Crm.SolutionHelper::GetHoldingSolutionName(string solutionName)
0x338c  stelem.ref
0x338d  dup
0x338e  ldc.i4.s 0x12
0x3390  ldstr    aMsdynceSales// "msdynce_Sales"
0x3395  stelem.ref
0x3396  dup
0x3397  ldc.i4.s 0x13
0x3399  ldstr    aMsdynceSales// "msdynce_Sales"
0x339e  call     string Microsoft.Crm.SolutionHelper::GetHoldingSolutionName(string solutionName)
0x33a3  stelem.ref
0x33a4  dup
0x33a5  ldc.i4.s 0x14
0x33a7  ldstr    aMsdynceService_0// "msdynce_Service"
0x33ac  stelem.ref
0x33ad  dup
0x33ae  ldc.i4.s 0x15
0x33b0  ldstr    aMsdynceService_0// "msdynce_Service"
0x33b5  call     string Microsoft.Crm.SolutionHelper::GetHoldingSolutionName(string solutionName)
0x33ba  stelem.ref
0x33bb  dup
0x33bc  ldc.i4.s 0x16
0x33be  ldstr    aMsdynceMarketi// "msdynce_Marketing"
0x33c3  stelem.ref
0x33c4  dup
0x33c5  ldc.i4.s 0x17
0x33c7  ldstr    aMsdynceMarketi// "msdynce_Marketing"
0x33cc  call     string Microsoft.Crm.SolutionHelper::GetHoldingSolutionName(string solutionName)
0x33d1  stelem.ref
0x33d2  dup
0x33d3  ldc.i4.s 0x18
0x33d5  ldstr    aMsdynceSalesse// "msdynce_SalesService"
0x33da  stelem.ref
0x33db  dup
0x33dc  ldc.i4.s 0x19
0x33de  ldstr    aMsdynceSalesse// "msdynce_SalesService"
0x33e3  call     string Microsoft.Crm.SolutionHelper::GetHoldingSolutionName(string solutionName)
0x33e8  stelem.ref
0x33e9  dup
0x33ea  ldc.i4.s 0x1A
0x33ec  ldstr    aMsdynceMarketi_0// "msdynce_MarketingSales"
0x33f1  stelem.ref
0x33f2  dup
0x33f3  ldc.i4.s 0x1B
0x33f5  ldstr    aMsdynceMarketi_0// "msdynce_MarketingSales"
0x33fa  call     string Microsoft.Crm.SolutionHelper::GetHoldingSolutionName(string solutionName)
0x33ff  stelem.ref
0x3400  dup
0x3401  ldc.i4.s 0x1C
0x3403  ldstr    aMsdynceMarketi_1// "msdynce_MarketingService"
0x3408  stelem.ref
0x3409  dup
0x340a  ldc.i4.s 0x1D
0x340c  ldstr    aMsdynceMarketi_1// "msdynce_MarketingService"
0x3411  call     string Microsoft.Crm.SolutionHelper::GetHoldingSolutionName(string solutionName)
0x3416  stelem.ref
0x3417  dup
0x3418  ldc.i4.s 0x1E
0x341a  ldstr    aMsdynceCrmexte// "msdynce_CRMExtensions"
0x341f  stelem.ref
0x3420  dup
0x3421  ldc.i4.s 0x1F
0x3423  ldstr    aMsdynceCrmexte// "msdynce_CRMExtensions"
0x3428  call     string Microsoft.Crm.SolutionHelper::GetHoldingSolutionName(string solutionName)
0x342d  stelem.ref
0x342e  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x3433  stsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.Crm.SolutionHelper::CrmAppsSolutionUniqueNames
0x3438  ldsfld   string [mscorlib]System.String::Empty
0x343d  stsfld   string Microsoft.Crm.SolutionHelper::_crmAppsSolutionUniqueNamesForSqlQuery
0x3442  ret
```
