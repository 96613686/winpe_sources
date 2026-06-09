# Microsoft.Crm.Application.Platform.CommunicationListeners.CommunicationListenerFactory::AddSolutionListenerBySolutionComponents

- ea: `0x88710`
- end: `0x88a76`
- name: `Microsoft.Crm.Application.Platform.CommunicationListeners.CommunicationListenerFactory::AddSolutionListenerBySolutionComponents`
- size: `870`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x88a80`

## callees

- `0x88710`
- `0x890b0`
- `0x9ca50`

## string_xrefs

- `0x88a4f`: `channelaccessprofilerule`
- `0x888be`: `template`
- `0x888cf`: `contracttemplate`
- `0x888e0`: `mailmergetemplate`
- `0x88924`: `kbarticletemplate`
- `0x88a17`: `fieldsecurityprofile`
- `0x88a5d`: `channelaccessprofile`

## pseudocode

```c

```

## disassembly

```asm
0x88710  ldarg.1
0x88711  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x88716  stloc.0
0x88717  ldloc.0
0x88718  ldc.i4   0x77614483
0x8871d  bgt.un   loc_887EA
0x88722  ldloc.0
0x88723  ldc.i4   0x391C1186
0x88728  bgt.un.s loc_8878A
0x8872a  ldloc.0
0x8872b  ldc.i4   0x19BB34EB
0x88730  bgt.un.s loc_88754
0x88732  ldloc.0
0x88733  ldc.i4   0x6B75FD1
0x88738  beq      loc_888CE
0x8873d  ldloc.0
0x8873e  ldc.i4   0xFFF3219
0x88743  beq      loc_88967
0x88748  ldloc.0
0x88749  ldc.i4   0x19BB34EB
0x8874e  beq      loc_88934
0x88753  ret
0x88754  ldloc.0
0x88755  ldc.i4   0x2492CBDF
0x8875a  bgt.un.s loc_88773
0x8875c  ldloc.0
0x8875d  ldc.i4   0x1BE1DC84
0x88762  beq      loc_8899A
0x88767  ldloc.0
0x88768  ldc.i4   0x2492CBDF
0x8876d  beq      loc_88956
0x88772  ret
0x88773  ldloc.0
0x88774  ldc.i4   0x313A105F
0x88779  beq      loc_88945
0x8877e  ldloc.0
0x8877f  ldc.i4   0x391C1186
0x88784  beq      loc_88A32
0x88789  ret
0x8878a  ldloc.0
0x8878b  ldc.i4   0x694AAA0B
0x88790  bgt.un.s loc_887B4
0x88792  ldloc.0
0x88793  ldc.i4   0x3F97BCF4
0x88798  beq      loc_88989
0x8879d  ldloc.0
0x8879e  ldc.i4   0x5861CAD1
0x887a3  beq      loc_889FA
0x887a8  ldloc.0
0x887a9  ldc.i4   0x694AAA0B
0x887ae  beq      loc_888BD
0x887b3  ret
0x887b4  ldloc.0
0x887b5  ldc.i4   0x6C897E3D
0x887ba  bgt.un.s loc_887D3
0x887bc  ldloc.0
0x887bd  ldc.i4   0x6BCDCA5A
0x887c2  beq      loc_889BC
0x887c7  ldloc.0
0x887c8  ldc.i4   0x6C897E3D
0x887cd  beq      loc_88A4E
0x887d2  ret
0x887d3  ldloc.0
0x887d4  ldc.i4   0x733C356F
0x887d9  beq      loc_88A24
0x887de  ldloc.0
0x887df  ldc.i4   0x77614483
0x887e4  beq      loc_88912
0x887e9  ret
0x887ea  ldloc.0
0x887eb  ldc.i4   0xA363AFB6
0x887f0  bgt.un.s loc_88852
0x887f2  ldloc.0
0x887f3  ldc.i4   0x7E18321C
0x887f8  bgt.un.s loc_8881C
0x887fa  ldloc.0
0x887fb  ldc.i4   0x78B322A0
0x88800  beq      loc_88978
0x88805  ldloc.0
0x88806  ldc.i4   0x7B6E47C3
0x8880b  beq      loc_88A5C
0x88810  ldloc.0
0x88811  ldc.i4   0x7E18321C
0x88816  beq      loc_88901
0x8881b  ret
0x8881c  ldloc.0
0x8881d  ldc.i4   0x89A02C48
0x88822  bgt.un.s loc_8883B
0x88824  ldloc.0
0x88825  ldc.i4   0x82598BC5
0x8882a  beq      loc_88A08
0x8882f  ldloc.0
0x88830  ldc.i4   0x89A02C48
0x88835  beq      loc_889CD
0x8883a  ret
0x8883b  ldloc.0
0x8883c  ldc.i4   0x9030D9BB
0x88841  beq      loc_888F0
0x88846  ldloc.0
0x88847  ldc.i4   0xA363AFB6
0x8884c  beq      loc_889EC
0x88851  ret
0x88852  ldloc.0
0x88853  ldc.i4   0xACDB5734
0x88858  bgt.un.s loc_88879
0x8885a  ldloc.0
0x8885b  ldc.i4   0xA698F29A
0x88860  beq      loc_889DE
0x88865  ldloc.0
0x88866  ldc.i4   0xAC96A470
0x8886b  beq.s    loc_888DF
0x8886d  ldloc.0
0x8886e  ldc.i4   0xACDB5734
0x88873  beq      loc_88923
0x88878  ret
0x88879  ldloc.0
0x8887a  ldc.i4   0xC5384E91
0x8887f  bgt.un.s loc_88898
0x88881  ldloc.0
0x88882  ldc.i4   0xC2A1106F
0x88887  beq      loc_889AB
0x8888c  ldloc.0
0x8888d  ldc.i4   0xC5384E91
0x88892  beq      loc_88A40
0x88897  ret
0x88898  ldloc.0
0x88899  ldc.i4   0xF16D5CA8
0x8889e  beq.s    loc_888AC
0x888a0  ldloc.0
0x888a1  ldc.i4   0xF2999C62
0x888a6  beq      loc_88A16
0x888ab  ret
0x888ac  ldarg.1
0x888ad  ldstr    aWorkflow// "workflow"
0x888b2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x888b7  brtrue   loc_88A69
0x888bc  ret
0x888bd  ldarg.1
0x888be  ldstr    aTemplate// "template"
0x888c3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x888c8  brtrue   loc_88A69
0x888cd  ret
0x888ce  ldarg.1
0x888cf  ldstr    aContracttempla// "contracttemplate"
0x888d4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x888d9  brtrue   loc_88A69
0x888de  ret
0x888df  ldarg.1
0x888e0  ldstr    aMailmergetempl_0// "mailmergetemplate"
0x888e5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x888ea  brtrue   loc_88A69
0x888ef  ret
0x888f0  ldarg.1
0x888f1  ldstr    aMobileofflinep_1// "mobileofflineprofile"
0x888f6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x888fb  brtrue   loc_88A69
0x88900  ret
0x88901  ldarg.1
0x88902  ldstr    aMobileofflinep// "mobileofflineprofileitem"
0x88907  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8890c  brtrue   loc_88A69
0x88911  ret
0x88912  ldarg.1
0x88913  ldstr    aMobileofflinep_2// "mobileofflineprofileitemassociation"
0x88918  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8891d  brtrue   loc_88A69
0x88922  ret
0x88923  ldarg.1
0x88924  ldstr    aKbarticletempl// "kbarticletemplate"
0x88929  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8892e  brtrue   loc_88A69
0x88933  ret
0x88934  ldarg.1
0x88935  ldstr    aReport// "report"
0x8893a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8893f  brtrue   loc_88A69
0x88944  ret
0x88945  ldarg.1
0x88946  ldstr    aRelationshipro_0// "relationshiprole"
0x8894b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88950  brtrue   loc_88A69
0x88955  ret
0x88956  ldarg.1
0x88957  ldstr    aRelationshipro_1// "relationshiprolemap"
0x8895c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88961  brtrue   loc_88A69
0x88966  ret
0x88967  ldarg.1
0x88968  ldstr    aRole_0// "role"
0x8896d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88972  brtrue   loc_88A69
0x88977  ret
0x88978  ldarg.1
0x88979  ldstr    aSavedquery// "savedquery"
0x8897e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88983  brtrue   loc_88A69
0x88988  ret
0x88989  ldarg.1
0x8898a  ldstr    aSavedqueryvisu// "savedqueryvisualization"
0x8898f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88994  brtrue   loc_88A69
0x88999  ret
0x8899a  ldarg.1
0x8899b  ldstr    aEntitymap// "entitymap"
0x889a0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x889a5  brtrue   loc_88A69
0x889aa  ret
0x889ab  ldarg.1
0x889ac  ldstr    aAttributemap// "attributemap"
0x889b1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x889b6  brtrue   loc_88A69
0x889bb  ret
0x889bc  ldarg.1
0x889bd  ldstr    aRibboncustomiz// "ribboncustomization"
0x889c2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x889c7  brtrue   loc_88A69
0x889cc  ret
0x889cd  ldarg.1
0x889ce  ldstr    aSitemap_0// "sitemap"
0x889d3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x889d8  brtrue   loc_88A69
0x889dd  ret
0x889de  ldarg.1
0x889df  ldstr    aSystemform// "systemform"
0x889e4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x889e9  brtrue.s loc_88A69
0x889eb  ret
0x889ec  ldarg.1
0x889ed  ldstr    aHierarchyrule// "hierarchyrule"
0x889f2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x889f7  brtrue.s loc_88A69
0x889f9  ret
0x889fa  ldarg.1
0x889fb  ldstr    aWebresource_0// "webresource"
0x88a00  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88a05  brtrue.s loc_88A69
0x88a07  ret
0x88a08  ldarg.1
0x88a09  ldstr    aConnectionrole_2// "connectionrole"
0x88a0e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88a13  brtrue.s loc_88A69
0x88a15  ret
0x88a16  ldarg.1
0x88a17  ldstr    aFieldsecurityp// "fieldsecurityprofile"
0x88a1c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88a21  brtrue.s loc_88A69
0x88a23  ret
0x88a24  ldarg.1
0x88a25  ldstr    aRoutingrule// "routingrule"
0x88a2a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88a2f  brtrue.s loc_88A69
0x88a31  ret
0x88a32  ldarg.1
0x88a33  ldstr    aConvertrule// "convertrule"
0x88a38  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88a3d  brtrue.s loc_88A69
0x88a3f  ret
0x88a40  ldarg.1
0x88a41  ldstr    aSla// "sla"
0x88a46  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88a4b  brtrue.s loc_88A69
0x88a4d  ret
0x88a4e  ldarg.1
0x88a4f  ldstr    aChannelaccessp// "channelaccessprofilerule"
0x88a54  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88a59  brtrue.s loc_88A69
0x88a5b  ret
0x88a5c  ldarg.1
0x88a5d  ldstr    aChannelaccessp_1// "channelaccessprofile"
0x88a62  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88a67  brfalse.s loc_88A75
0x88a69  ldarg.0
0x88a6a  newobj   instance void Microsoft.Crm.Application.Platform.CommunicationListeners.SolutionListener::.ctor()
0x88a6f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.CommunicationListeners.EventListener>::Add(var<u1>)
0x88a74  ret
0x88a75  ret
```
