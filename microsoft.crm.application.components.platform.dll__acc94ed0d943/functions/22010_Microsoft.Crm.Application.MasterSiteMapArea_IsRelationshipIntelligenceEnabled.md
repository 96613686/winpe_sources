# Microsoft.Crm.Application.MasterSiteMapArea::IsRelationshipIntelligenceEnabled

- ea: `0x22010`
- end: `0x220e1`
- name: `Microsoft.Crm.Application.MasterSiteMapArea::IsRelationshipIntelligenceEnabled`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x218f0`

## callees

- `0x22010`
- `0x43d60`
- `0x43e10`
- `0x43eb0`
- `0x44040`
- `0x44940`
- `0x44a90`
- `0x44f40`
- `0x47920`
- `0x47940`

## string_xrefs

- `0x22034`: `SICommon`
- `0x22070`: `isSalesSolutionAvailable = {0}, isSICommonSolutionAvailable = {1}, isCRMOrg = {2}, isRAnalyitcFeatureEnabled = {3}, isRAssitantFeatureEnabled = {4}, isEEFeatureEnabled = {5}, isADCFeatureEnabled = {6}, isOnline={7}`

## pseudocode

```c

```

## disassembly

```asm
0x22010  call     bool Microsoft.Crm.Application.Utility.Util::IsLive()
0x22015  stloc.0
0x22016  ldc.i4.0
0x22017  dup
0x22018  stloc.s  7
0x2201a  dup
0x2201b  stloc.s  6
0x2201d  dup
0x2201e  stloc.s  5
0x22020  dup
0x22021  stloc.s  4
0x22023  dup
0x22024  stloc.3
0x22025  dup
0x22026  stloc.2
0x22027  stloc.1
0x22028  ldstr    aMsdynceSales// "msdynce_Sales"
0x2202d  ldarg.1
0x2202e  call     bool Microsoft.Crm.Application.Utility.Util::IsSolutionAvailable(string uniqueName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x22033  stloc.1
0x22034  ldstr    aSicommon// "SICommon"
0x22039  ldarg.1
0x2203a  call     bool Microsoft.Crm.Application.Utility.Util::IsSolutionAvailable(string uniqueName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x2203f  stloc.2
0x22040  call     bool Microsoft.Crm.Application.Utility.Util::IsCRMOrganization()
0x22045  stloc.3
0x22046  ldarg.1
0x22047  call     bool Microsoft.Crm.Application.Utility.Util::IsRelationshipAnalyticsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x2204c  stloc.s  4
0x2204e  ldarg.1
0x2204f  call     bool Microsoft.Crm.Application.Utility.Util::IsRelationshipAssistanceFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x22054  stloc.s  5
0x22056  ldarg.1
0x22057  call     bool Microsoft.Crm.Application.Utility.Util::IsEmailEngagementFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x2205c  stloc.s  6
0x2205e  ldarg.1
0x2205f  call     bool Microsoft.Crm.Application.Utility.Util::IsAutoDataCaptureFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x22064  stloc.s  7
0x22066  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x2206b  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x22070  ldstr    aIssalessolutio// "isSalesSolutionAvailable = {0}, isSICom"...
0x22075  ldc.i4.8
0x22076  newarr   [mscorlib]System.Object
0x2207b  dup
0x2207c  ldc.i4.0
0x2207d  ldloc.1
0x2207e  box      [mscorlib]System.Boolean
0x22083  stelem.ref
0x22084  dup
0x22085  ldc.i4.1
0x22086  ldloc.2
0x22087  box      [mscorlib]System.Boolean
0x2208c  stelem.ref
0x2208d  dup
0x2208e  ldc.i4.2
0x2208f  ldloc.3
0x22090  box      [mscorlib]System.Boolean
0x22095  stelem.ref
0x22096  dup
0x22097  ldc.i4.3
0x22098  ldloc.s  4
0x2209a  box      [mscorlib]System.Boolean
0x2209f  stelem.ref
0x220a0  dup
0x220a1  ldc.i4.4
0x220a2  ldloc.s  5
0x220a4  box      [mscorlib]System.Boolean
0x220a9  stelem.ref
0x220aa  dup
0x220ab  ldc.i4.5
0x220ac  ldloc.s  6
0x220ae  box      [mscorlib]System.Boolean
0x220b3  stelem.ref
0x220b4  dup
0x220b5  ldc.i4.6
0x220b6  ldloc.s  7
0x220b8  box      [mscorlib]System.Boolean
0x220bd  stelem.ref
0x220be  dup
0x220bf  ldc.i4.7
0x220c0  ldloc.0
0x220c1  box      [mscorlib]System.Boolean
0x220c6  stelem.ref
0x220c7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x220cc  ldloc.1
0x220cd  ldloc.2
0x220ce  and
0x220cf  ldloc.3
0x220d0  and
0x220d1  brfalse.s loc_220DF
0x220d3  ldloc.s  4
0x220d5  ldloc.s  5
0x220d7  or
0x220d8  ldloc.s  6
0x220da  or
0x220db  ldloc.s  7
0x220dd  or
0x220de  ret
0x220df  ldc.i4.0
0x220e0  ret
```
