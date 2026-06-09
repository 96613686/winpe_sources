# Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileHandler::RetrieveChannelAccessProfiles

- ea: `0x2c100`
- end: `0x2c1e3`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileHandler::RetrieveChannelAccessProfiles`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x2bf80`

## string_xrefs

- `0x2c127`: `channelaccessprofileid`
- `0x2c1b7`: `channelaccessprofileid`
- `0x2c147`: `emailaccess`
- `0x2c14f`: `facebookaccess`
- `0x2c157`: `phoneaccess`
- `0x2c15f`: `twitteraccess`
- `0x2c167`: `webaccess`
- `0x2c100`: `ChannelAccessProfile`
- `0x2c10c`: `ChannelAccessProfile`

## pseudocode

```c

```

## disassembly

```asm
0x2c100  ldstr    aChannelaccessp_4// "ChannelAccessProfile"
0x2c105  ldarg.2
0x2c106  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2c10b  stloc.0
0x2c10c  ldstr    aChannelaccessp_4// "ChannelAccessProfile"
0x2c111  ldarg.2
0x2c112  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x2c117  stloc.1
0x2c118  ldloc.1
0x2c119  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x2c11e  ldc.i4.s 0x10
0x2c120  newarr   [mscorlib]System.String
0x2c125  dup
0x2c126  ldc.i4.0
0x2c127  ldstr    aChannelaccessp_1// "channelaccessprofileid"
0x2c12c  stelem.ref
0x2c12d  dup
0x2c12e  ldc.i4.1
0x2c12f  ldstr    aName// "name"
0x2c134  stelem.ref
0x2c135  dup
0x2c136  ldc.i4.2
0x2c137  ldstr    aSolutionid// "solutionid"
0x2c13c  stelem.ref
0x2c13d  dup
0x2c13e  ldc.i4.3
0x2c13f  ldstr    aIsmanaged// "ismanaged"
0x2c144  stelem.ref
0x2c145  dup
0x2c146  ldc.i4.4
0x2c147  ldstr    aEmailaccess_0// "emailaccess"
0x2c14c  stelem.ref
0x2c14d  dup
0x2c14e  ldc.i4.5
0x2c14f  ldstr    aFacebookaccess_0// "facebookaccess"
0x2c154  stelem.ref
0x2c155  dup
0x2c156  ldc.i4.6
0x2c157  ldstr    aPhoneaccess_0// "phoneaccess"
0x2c15c  stelem.ref
0x2c15d  dup
0x2c15e  ldc.i4.7
0x2c15f  ldstr    aTwitteraccess_0// "twitteraccess"
0x2c164  stelem.ref
0x2c165  dup
0x2c166  ldc.i4.8
0x2c167  ldstr    aWebaccess_0// "webaccess"
0x2c16c  stelem.ref
0x2c16d  dup
0x2c16e  ldc.i4.s 9
0x2c170  ldstr    aViewknowledgea_0// "viewknowledgearticles"
0x2c175  stelem.ref
0x2c176  dup
0x2c177  ldc.i4.s 0xA
0x2c179  ldstr    aViewarticlerat_0// "viewarticlerating"
0x2c17e  stelem.ref
0x2c17f  dup
0x2c180  ldc.i4.s 0xB
0x2c182  ldstr    aRateknowledgea_0// "rateknowledgearticles"
0x2c187  stelem.ref
0x2c188  dup
0x2c189  ldc.i4.s 0xC
0x2c18b  ldstr    aSubmitfeedback_0// "submitfeedback"
0x2c190  stelem.ref
0x2c191  dup
0x2c192  ldc.i4.s 0xD
0x2c194  ldstr    aStatecode// "statecode"
0x2c199  stelem.ref
0x2c19a  dup
0x2c19b  ldc.i4.s 0xE
0x2c19d  ldstr    aStatuscode// "statuscode"
0x2c1a2  stelem.ref
0x2c1a3  dup
0x2c1a4  ldc.i4.s 0xF
0x2c1a6  ldstr    aIsguestprofile_0// "isguestprofile"
0x2c1ab  stelem.ref
0x2c1ac  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x2c1b1  ldloc.1
0x2c1b2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x2c1b7  ldstr    aChannelaccessp_1// "channelaccessprofileid"
0x2c1bc  ldc.i4.8
0x2c1bd  ldarg.1
0x2c1be  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ToArray()
0x2c1c3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x2c1c8  pop
0x2c1c9  ldloc.1
0x2c1ca  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Order()
0x2c1cf  ldstr    aName// "name"
0x2c1d4  ldc.i4.0
0x2c1d5  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression::AddOrder(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderType)
0x2c1da  ldloc.0
0x2c1db  ldloc.1
0x2c1dc  ldarg.2
0x2c1dd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2c1e2  ret
```
