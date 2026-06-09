# Microsoft.Crm.Authentication.CrmAuthorizationUtility::.cctor

- ea: `0x1500`
- end: `0x1530`
- name: `Microsoft.Crm.Authentication.CrmAuthorizationUtility::.cctor`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, service_task, broker_com_uri`

## string_xrefs

- `0x1510`: `/MSCRMServices/Test/CrmTest.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x1500  ldc.i4.3
0x1501  newarr   [mscorlib]System.String
0x1506  dup
0x1507  ldc.i4.0
0x1508  ldstr    aTestCrmtestAsp// "/Test/CrmTest.aspx"
0x150d  stelem.ref
0x150e  dup
0x150f  ldc.i4.1
0x1510  ldstr    aMscrmservicesT// "/MSCRMServices/Test/CrmTest.aspx"
0x1515  stelem.ref
0x1516  dup
0x1517  ldc.i4.2
0x1518  ldstr    aPortalTestCrmt// "/Portal/Test/CrmTest.aspx"
0x151d  stelem.ref
0x151e  stsfld   string[] Microsoft.Crm.Authentication.CrmAuthorizationUtility::_testPages
0x1523  ldnull
0x1524  stsfld   class [mscorlib]System.Func`1<class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail> Microsoft.Crm.Authentication.CrmAuthorizationUtility::_allowCustomSessionDurationFeatureDetailFactory
0x1529  ldnull
0x152a  stsfld   class [mscorlib]System.Func`1<class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail> Microsoft.Crm.Authentication.CrmAuthorizationUtility::_allowCustomInactivityDurationFeatureDetailFactory
0x152f  ret
```
