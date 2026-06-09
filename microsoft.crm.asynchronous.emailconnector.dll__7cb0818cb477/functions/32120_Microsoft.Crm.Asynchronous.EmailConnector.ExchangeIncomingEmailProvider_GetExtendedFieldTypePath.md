# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProvider::GetExtendedFieldTypePath

- ea: `0x32120`
- end: `0x3228c`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProvider::GetExtendedFieldTypePath`
- size: `364`
- prototype: ``
- caller_count: `9`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x32040`
- `0x32050`
- `0x32060`
- `0x32070`
- `0x32080`
- `0x32090`
- `0x320a0`
- `0x320b0`
- `0x320c0`

## callees

- `0xabc0`
- `0x158c0`
- `0x158e0`
- `0x15940`
- `0x159a0`
- `0x159b0`
- `0x32120`
- `0x32680`
- `0x417a0`
- `0x81700`

## string_xrefs

- `0x3222f`: `crmLinkState`
- `0x3223e`: `crmLinkStateTracker`

## pseudocode

```c

```

## disassembly

```asm
0x32120  ldarg.1
0x32121  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x32126  brfalse.s loc_3212A
0x32128  ldnull
0x32129  ret
0x3212a  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType::.ctor()
0x3212f  stloc.0
0x32130  ldloc.0
0x32131  ldc.i4.3
0x32132  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType::set_DistinguishedPropertySetId(valuetype Microsoft.Crm.Asynchronous.EmailConnector.DistinguishedPropertySetType value)
0x32137  ldloc.0
0x32138  ldc.i4.1
0x32139  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType::set_DistinguishedPropertySetIdSpecified(bool value)
0x3213e  ldloc.0
0x3213f  ldarg.1
0x32140  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType::set_PropertyName(string value)
0x32145  ldarg.0
0x32146  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x3214b  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x32150  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x32155  call     bool Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::IsSSSCustomPropertyFCBEnabled(valuetype [mscorlib]System.Guid organizationId)
0x3215a  brfalse.s loc_32173
0x3215c  ldarg.1
0x3215d  ldstr    aCecp// "cecp"
0x32162  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0x32167  brfalse.s loc_32173
0x32169  ldloc.0
0x3216a  ldc.i4.s 0x19
0x3216c  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType::set_PropertyType(valuetype Microsoft.Crm.Asynchronous.EmailConnector.MapiPropertyTypeType value)
0x32171  ldloc.0
0x32172  ret
0x32173  ldarg.1
0x32174  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x32179  stloc.1
0x3217a  ldloc.1
0x3217b  ldc.i4   0x3E6B5E3F
0x32180  bgt.un.s loc_321BD
0x32182  ldloc.1
0x32183  ldc.i4   0x2B9C97CC
0x32188  bgt.un.s loc_321A2
0x3218a  ldloc.1
0x3218b  ldc.i4   0x1033BBD5
0x32190  beq.s    loc_32201
0x32192  ldloc.1
0x32193  ldc.i4   0x2B9C97CC
0x32198  beq      loc_3222E
0x3219d  br       loc_32288
0x321a2  ldloc.1
0x321a3  ldc.i4   0x395AF4FD
0x321a8  beq      loc_3225B
0x321ad  ldloc.1
0x321ae  ldc.i4   0x3E6B5E3F
0x321b3  beq      loc_3224C
0x321b8  br       loc_32288
0x321bd  ldloc.1
0x321be  ldc.i4   0xCACA87A0
0x321c3  bgt.un.s loc_321DA
0x321c5  ldloc.1
0x321c6  ldc.i4   0x638256FA
0x321cb  beq.s    loc_321EF
0x321cd  ldloc.1
0x321ce  ldc.i4   0xCACA87A0
0x321d3  beq.s    loc_3223D
0x321d5  br       loc_32288
0x321da  ldloc.1
0x321db  ldc.i4   0xF3B6BC27
0x321e0  beq.s    loc_32210
0x321e2  ldloc.1
0x321e3  ldc.i4   0xF93751D6
0x321e8  beq.s    loc_3221F
0x321ea  br       loc_32288
0x321ef  ldarg.1
0x321f0  ldstr    aCrmid// "crmid"
0x321f5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x321fa  brtrue.s loc_3226A
0x321fc  br       loc_32288
0x32201  ldarg.1
0x32202  ldstr    aCrmregardingid// "crmRegardingId"
0x32207  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3220c  brtrue.s loc_3226A
0x3220e  br.s     loc_32288
0x32210  ldarg.1
0x32211  ldstr    aCrmregardingob// "crmRegardingObjectType"
0x32216  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3221b  brtrue.s loc_3226A
0x3221d  br.s     loc_32288
0x3221f  ldarg.1
0x32220  ldstr    aRegarding// "Regarding"
0x32225  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3222a  brtrue.s loc_3226A
0x3222c  br.s     loc_32288
0x3222e  ldarg.1
0x3222f  ldstr    aCrmlinkstate// "crmLinkState"
0x32234  call     bool [mscorlib]System.String::op_Equality(string, string)
0x32239  brtrue.s loc_32274
0x3223b  br.s     loc_32288
0x3223d  ldarg.1
0x3223e  ldstr    aCrmlinkstatetr// "crmLinkStateTracker"
0x32243  call     bool [mscorlib]System.String::op_Equality(string, string)
0x32248  brtrue.s loc_3227E
0x3224a  br.s     loc_32288
0x3224c  ldarg.1
0x3224d  ldstr    aCrmisfollowed// "crmIsFollowed"
0x32252  call     bool [mscorlib]System.String::op_Equality(string, string)
0x32257  brtrue.s loc_3227E
0x32259  br.s     loc_32288
0x3225b  ldarg.1
0x3225c  ldstr    aCrmcategorytra// "crmCategoryTracker"
0x32261  call     bool [mscorlib]System.String::op_Equality(string, string)
0x32266  brtrue.s loc_3227E
0x32268  br.s     loc_32288
0x3226a  ldloc.0
0x3226b  ldc.i4.s 0x19
0x3226d  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType::set_PropertyType(valuetype Microsoft.Crm.Asynchronous.EmailConnector.MapiPropertyTypeType value)
0x32272  br.s     loc_3228A
0x32274  ldloc.0
0x32275  ldc.i4.s 9
0x32277  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType::set_PropertyType(valuetype Microsoft.Crm.Asynchronous.EmailConnector.MapiPropertyTypeType value)
0x3227c  br.s     loc_3228A
0x3227e  ldloc.0
0x3227f  ldc.i4.s 0xE
0x32281  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType::set_PropertyType(valuetype Microsoft.Crm.Asynchronous.EmailConnector.MapiPropertyTypeType value)
0x32286  br.s     loc_3228A
0x32288  ldnull
0x32289  ret
0x3228a  ldloc.0
0x3228b  ret
```
