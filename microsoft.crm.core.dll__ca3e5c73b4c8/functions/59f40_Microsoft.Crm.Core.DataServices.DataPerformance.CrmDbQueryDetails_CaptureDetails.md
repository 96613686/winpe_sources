# Microsoft.Crm.Core.DataServices.DataPerformance.CrmDbQueryDetails::CaptureDetails

- ea: `0x59f40`
- end: `0x5a314`
- name: `Microsoft.Crm.Core.DataServices.DataPerformance.CrmDbQueryDetails::CaptureDetails`
- size: `980`
- prototype: ``
- caller_count: `0`
- callee_count: `30`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x59e40`
- `0x59f40`
- `0x5a370`
- `0x5a380`
- `0x5a390`
- `0x5a3a0`
- `0x5a3b0`
- `0x5a3c0`
- `0x5a3d0`
- `0x5a3e0`
- `0x5a3f0`
- `0x5a400`
- `0x5a410`
- `0x5a420`
- `0x5a440`
- `0x5a460`
- `0x5a480`
- `0x5a4a0`
- `0x5a4c0`
- `0x5a4e0`
- `0x5a500`
- `0x5a520`
- `0x5a540`
- `0x5a560`
- `0x5a580`
- `0x5a5a0`
- `0x5a5c0`
- `0x5a5e0`
- `0x5a600`
- `0x5a620`

## string_xrefs

- `0x5a078`: `securityOption`
- `0x5a08d`: `securityOption`
- `0x5a101`: `businessUnitReadPrivilegeLength`
- `0x5a112`: `businessUnitReadPrivilegeLength`

## pseudocode

```c

```

## disassembly

```asm
0x59f40  call     class Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails Microsoft.Crm.Core.DataServices.DataPerformance.CrmDbQueryDetails::get_QueryDetails()
0x59f45  stloc.0
0x59f46  ldloc.0
0x59f47  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_OrganizationId()
0x59f4c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x59f51  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x59f56  brfalse  loc_59FE3
0x59f5b  ldarga.s 1
0x59f5d  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x59f62  brfalse.s loc_59FE3
0x59f64  ldarg.1
0x59f65  stloc.1
0x59f66  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x59f6b  stloc.2
0x59f6c  ldloca.s 1
0x59f6e  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x59f73  brtrue.s loc_59F78
0x59f75  ldc.i4.1
0x59f76  br.s     loc_59F91
0x59f78  ldloca.s 1
0x59f7a  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x59f7f  brtrue.s loc_59F84
0x59f81  ldc.i4.0
0x59f82  br.s     loc_59F91
0x59f84  ldloca.s 1
0x59f86  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x59f8b  ldloc.2
0x59f8c  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x59f91  brfalse.s loc_59FE3
0x59f93  ldloc.0
0x59f94  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_OrganizationId()
0x59f99  stloc.2
0x59f9a  ldarg.1
0x59f9b  stloc.1
0x59f9c  ldloca.s 1
0x59f9e  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x59fa3  brtrue.s loc_59FA8
0x59fa5  ldc.i4.1
0x59fa6  br.s     loc_59FB5
0x59fa8  ldloc.2
0x59fa9  ldloca.s 1
0x59fab  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x59fb0  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x59fb5  brfalse.s loc_59FE3
0x59fb7  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Core.DataServices.DataPerformance.CrmDbQueryDetails::logger
0x59fbc  ldstr    aMismatchedOrgI// "Mismatched Org Ids between input: {0} a"...
0x59fc1  ldc.i4.2
0x59fc2  newarr   [mscorlib]System.Object
0x59fc7  dup
0x59fc8  ldc.i4.0
0x59fc9  ldarg.1
0x59fca  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x59fcf  stelem.ref
0x59fd0  dup
0x59fd1  ldc.i4.1
0x59fd2  ldloc.0
0x59fd3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_OrganizationId()
0x59fd8  box      [mscorlib]System.Guid
0x59fdd  stelem.ref
0x59fde  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogWarning(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x59fe3  ldloc.0
0x59fe4  ldarg.0
0x59fe5  stloc.3
0x59fe6  ldloca.s 3
0x59fe8  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Crm.Core.DataServices.DataPerformance.InitiatorType>::get_HasValue()
0x59fed  brtrue.s loc_59FF7
0x59fef  ldloc.0
0x59ff0  callvirt instance valuetype Microsoft.Crm.Core.DataServices.DataPerformance.InitiatorType Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_Initiator()
0x59ff5  br.s     loc_59FFE
0x59ff7  ldloca.s 3
0x59ff9  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Crm.Core.DataServices.DataPerformance.InitiatorType>::GetValueOrDefault()
0x59ffe  callvirt instance void Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::set_Initiator(valuetype Microsoft.Crm.Core.DataServices.DataPerformance.InitiatorType value)
0x5a003  ldloc.0
0x5a004  ldarg.1
0x5a005  stloc.1
0x5a006  ldloca.s 1
0x5a008  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x5a00d  brtrue.s loc_5A017
0x5a00f  ldloc.0
0x5a010  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_OrganizationId()
0x5a015  br.s     loc_5A01E
0x5a017  ldloca.s 1
0x5a019  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x5a01e  callvirt instance void Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::set_OrganizationId(valuetype [mscorlib]System.Guid value)
0x5a023  ldloc.0
0x5a024  ldarg.2
0x5a025  dup
0x5a026  brtrue.s loc_5A02F
0x5a028  pop
0x5a029  ldloc.0
0x5a02a  callvirt instance string Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_ComponentName()
0x5a02f  callvirt instance void Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::set_ComponentName(string value)
0x5a034  ldloc.0
0x5a035  ldarg.3
0x5a036  dup
0x5a037  brtrue.s loc_5A040
0x5a039  pop
0x5a03a  ldloc.0
0x5a03b  callvirt instance string Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_SolutionName()
0x5a040  callvirt instance void Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::set_SolutionName(string value)
0x5a045  ldloc.0
0x5a046  ldarg.s  4
0x5a048  dup
0x5a049  brtrue.s loc_5A052
0x5a04b  pop
0x5a04c  ldloc.0
0x5a04d  callvirt instance string Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_EntityName()
0x5a052  callvirt instance void Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::set_EntityName(string value)
0x5a057  ldloc.0
0x5a058  ldarg.s  5
0x5a05a  dup
0x5a05b  brtrue.s loc_5A064
0x5a05d  pop
0x5a05e  ldloc.0
0x5a05f  callvirt instance string Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_OperationName()
0x5a064  callvirt instance void Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::set_OperationName(string value)
0x5a069  ldloc.0
0x5a06a  ldarg.s  6
0x5a06c  callvirt instance void Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::set_IsLeadingWildCardQuery(bool value)
0x5a071  ldloc.0
0x5a072  ldarg.s  7
0x5a074  brfalse.s loc_5A084
0x5a076  ldarg.s  7
0x5a078  ldstr    aSecurityoption// "securityOption"
0x5a07d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5a082  brtrue.s loc_5A08B
0x5a084  ldstr    aUnidentified_0// "unidentified"
0x5a089  br.s     loc_5A09C
0x5a08b  ldarg.s  7
0x5a08d  ldstr    aSecurityoption// "securityOption"
0x5a092  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5a097  castclass [mscorlib]System.String
0x5a09c  callvirt instance void Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::set_SecurityOption(string value)
0x5a0a1  ldloc.0
0x5a0a2  ldarg.s  7
0x5a0a4  brfalse.s loc_5A0B4
0x5a0a6  ldarg.s  7
0x5a0a8  ldstr    aRecordcount// "recordCount"
0x5a0ad  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5a0b2  brtrue.s loc_5A0B8
0x5a0b4  ldc.i4.m1
0x5a0b5  conv.i8
0x5a0b6  br.s     loc_5A0C9
0x5a0b8  ldarg.s  7
0x5a0ba  ldstr    aRecordcount// "recordCount"
0x5a0bf  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5a0c4  unbox.any [mscorlib]System.Int64
0x5a0c9  callvirt instance void Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::set_RecordCount(int64 value)
0x5a0ce  ldloc.0
0x5a0cf  ldarg.s  7
0x5a0d1  brfalse.s loc_5A0E1
0x5a0d3  ldarg.s  7
0x5a0d5  ldstr    aOwnerprincipal// "ownerPrincipalsCount"
0x5a0da  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5a0df  brtrue.s loc_5A0E4
0x5a0e1  ldc.i4.m1
0x5a0e2  br.s     loc_5A0F5
0x5a0e4  ldarg.s  7
0x5a0e6  ldstr    aOwnerprincipal// "ownerPrincipalsCount"
0x5a0eb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5a0f0  unbox.any [mscorlib]System.Int32
0x5a0f5  callvirt instance void Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::set_OwnerPrincipalsCount(int32 value)
0x5a0fa  ldloc.0
0x5a0fb  ldarg.s  7
0x5a0fd  brfalse.s loc_5A10D
0x5a0ff  ldarg.s  7
0x5a101  ldstr    aBusinessunitre// "businessUnitReadPrivilegeLength"
0x5a106  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5a10b  brtrue.s loc_5A110
0x5a10d  ldc.i4.m1
0x5a10e  br.s     loc_5A121
0x5a110  ldarg.s  7
0x5a112  ldstr    aBusinessunitre// "businessUnitReadPrivilegeLength"
0x5a117  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5a11c  unbox.any [mscorlib]System.Int32
0x5a121  callvirt instance void Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::set_BusinessUnitReadPrivilegeLength(int32 value)
0x5a126  ldloc.0
0x5a127  ldarg.s  7
0x5a129  brfalse.s loc_5A139
0x5a12b  ldarg.s  7
0x5a12d  ldstr    aBusinessunitco// "businessUnitCount"
0x5a132  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5a137  brtrue.s loc_5A13C
0x5a139  ldc.i4.m1
0x5a13a  br.s     loc_5A14D
0x5a13c  ldarg.s  7
0x5a13e  ldstr    aBusinessunitco// "businessUnitCount"
0x5a143  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5a148  unbox.any [mscorlib]System.Int32
0x5a14d  callvirt instance void Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::set_BusinessUnitCount(int32 value)
0x5a152  ldloc.0
0x5a153  ldarg.s  7
0x5a155  brfalse.s loc_5A165
0x5a157  ldarg.s  7
0x5a159  ldstr    aPoachildusersc// "poaChildUsersCount"
0x5a15e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5a163  brtrue.s loc_5A169
0x5a165  ldc.i4.m1
0x5a166  conv.i8
0x5a167  br.s     loc_5A17A
0x5a169  ldarg.s  7
0x5a16b  ldstr    aPoachildusersc// "poaChildUsersCount"
0x5a170  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5a175  unbox.any [mscorlib]System.Int64
0x5a17a  callvirt instance void Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::set_POAChildUsersCount(int64 value)
0x5a17f  ldloc.0
0x5a180  ldarg.s  7
0x5a182  brfalse.s loc_5A192
0x5a184  ldarg.s  7
0x5a186  ldstr    aPoateamprincip// "poaTeamPrincipalsCount"
0x5a18b  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5a190  brtrue.s loc_5A196
0x5a192  ldc.i4.m1
0x5a193  conv.i8
0x5a194  br.s     loc_5A1A7
0x5a196  ldarg.s  7
0x5a198  ldstr    aPoateamprincip// "poaTeamPrincipalsCount"
0x5a19d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5a1a2  unbox.any [mscorlib]System.Int64
0x5a1a7  callvirt instance void Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::set_POATeamPrincipalsCount(int64 value)
0x5a1ac  ldloc.0
0x5a1ad  ldarg.s  7
0x5a1af  brfalse.s loc_5A1BF
0x5a1b1  ldarg.s  7
0x5a1b3  ldstr    aPoasharecount// "poaShareCount"
0x5a1b8  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5a1bd  brtrue.s loc_5A1C3
0x5a1bf  ldc.i4.m1
0x5a1c0  conv.i8
0x5a1c1  br.s     loc_5A1D4
0x5a1c3  ldarg.s  7
0x5a1c5  ldstr    aPoasharecount// "poaShareCount"
0x5a1ca  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5a1cf  unbox.any [mscorlib]System.Int64
0x5a1d4  callvirt instance void Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::set_POAShareCount(int64 value)
0x5a1d9  ldloc.0
0x5a1da  ldarg.s  7
0x5a1dc  brfalse.s loc_5A1EC
0x5a1de  ldarg.s  7
0x5a1e0  ldstr    aPoasharecountp// "poaShareCountPercentOfTotalRows"
0x5a1e5  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5a1ea  brtrue.s loc_5A1EF
0x5a1ec  ldc.i4.m1
0x5a1ed  br.s     loc_5A200
0x5a1ef  ldarg.s  7
0x5a1f1  ldstr    aPoasharecountp// "poaShareCountPercentOfTotalRows"
0x5a1f6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5a1fb  unbox.any [mscorlib]System.Int32
0x5a200  callvirt instance void Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::set_POAShareCountPercentOfTotalRows(int32 value)
0x5a205  ldloc.0
0x5a206  ldarg.s  7
0x5a208  brfalse.s loc_5A218
0x5a20a  ldarg.s  7
0x5a20c  ldstr    aPoarecordcount// "poaRecordCountForOwnerID"
0x5a211  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5a216  brtrue.s loc_5A21C
0x5a218  ldc.i4.m1
0x5a219  conv.i8
0x5a21a  br.s     loc_5A22D
0x5a21c  ldarg.s  7
0x5a21e  ldstr    aPoarecordcount// "poaRecordCountForOwnerID"
0x5a223  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5a228  unbox.any [mscorlib]System.Int64
0x5a22d  callvirt instance void Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::set_POARecordCountForOwnerID(int64 value)
0x5a232  ldloc.0
0x5a233  ldarg.s  7
0x5a235  brfalse.s loc_5A245
0x5a237  ldarg.s  7
0x5a239  ldstr    aPoarecordcount_0// "poaRecordCountForOwnerIDPercentOfTotalR"...
0x5a23e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5a243  brtrue.s loc_5A248
0x5a245  ldc.i4.m1
0x5a246  br.s     loc_5A259
0x5a248  ldarg.s  7
0x5a24a  ldstr    aPoarecordcount_0// "poaRecordCountForOwnerIDPercentOfTotalR"...
0x5a24f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5a254  unbox.any [mscorlib]System.Int32
0x5a259  callvirt instance void Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::set_POARecordCountForOwnerIDPercentOfTotalRows(int32 value)
0x5a25e  ldloc.0
0x5a25f  ldarg.s  7
0x5a261  brfalse.s loc_5A271
0x5a263  ldarg.s  7
0x5a265  ldstr    aPoarecordcount_1// "poaRecordCountForOwningBU"
0x5a26a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5a26f  brtrue.s loc_5A275
0x5a271  ldc.i4.m1
0x5a272  conv.i8
0x5a273  br.s     loc_5A286
0x5a275  ldarg.s  7
0x5a277  ldstr    aPoarecordcount_1// "poaRecordCountForOwningBU"
0x5a27c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5a281  unbox.any [mscorlib]System.Int64
0x5a286  callvirt instance void Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::set_POARecordCountForOwningBU(int64 value)
0x5a28b  ldloc.0
0x5a28c  ldarg.s  7
0x5a28e  brfalse.s loc_5A29E
0x5a290  ldarg.s  7
0x5a292  ldstr    aPoarecordcount_2// "poaRecordCountForOwningBUPercentOfTotal"...
0x5a297  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5a29c  brtrue.s loc_5A2A1
  ... truncated ...
```
