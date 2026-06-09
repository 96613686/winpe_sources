# <ImportDatabaseAsync>d__31::MoveNext

- ea: `0x440d0`
- end: `0x44846`
- name: `<ImportDatabaseAsync>d__31::MoveNext`
- size: `1910`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x22ae0`
- `0x38ea0`
- `0x38ed0`
- `0x38ef0`
- `0x38f10`
- `0x38f30`
- `0x39520`
- `0x395e0`
- `0x3a6f0`
- `0x3a8a0`
- `0x3f450`
- `0x440d0`

## string_xrefs

- `0x446df`: `SpartanTraceCompleted`
- `0x4410b`: `storageUri`
- `0x4411b`: `sasToken`
- `0x441cc`: `StorageUri`
- `0x443d3`: `SharedAccessKey`

## pseudocode

```c

```

## disassembly

```asm
0x440d0  ldarg.0
0x440d1  ldfld    int32 <ImportDatabaseAsync>d__31::<>1__state
0x440d6  stloc.0
0x440d7  ldarg.0
0x440d8  ldfld    class Microsoft.Crm.Admin.AdminService.Spartan.SpartanService <ImportDatabaseAsync>d__31::<>4__this
0x440dd  stloc.1
0x440de  ldloc.0
0x440df  ldc.i4.1
0x440e0  ble.un   loc_44348
0x440e5  ldarg.0
0x440e6  ldfld    string <ImportDatabaseAsync>d__31::operationId
0x440eb  ldstr    aOperationid// "operationId"
0x440f0  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x440f5  ldarg.0
0x440f6  ldfld    string <ImportDatabaseAsync>d__31::azureRegion
0x440fb  ldstr    aAzureregion_1// "azureRegion"
0x44100  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x44105  ldarg.0
0x44106  ldfld    string <ImportDatabaseAsync>d__31::storageUri
0x4410b  ldstr    aStorageuri// "storageUri"
0x44110  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x44115  ldarg.0
0x44116  ldfld    string <ImportDatabaseAsync>d__31::sasToken
0x4411b  ldstr    aSastoken// "sasToken"
0x44120  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x44125  ldarg.0
0x44126  ldflda   valuetype [mscorlib]System.Guid <ImportDatabaseAsync>d__31::scalegroupId
0x4412b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x44130  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x44135  brtrue.s loc_44148
0x44137  ldarg.0
0x44138  ldarg.0
0x44139  ldfld    valuetype [mscorlib]System.Guid <ImportDatabaseAsync>d__31::scalegroupId
0x4413e  call     string Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::RetrieveTierGroupName(valuetype [mscorlib]System.Guid scaleGroupId)
0x44143  stfld    string <ImportDatabaseAsync>d__31::tierGroup
0x44148  ldarg.0
0x44149  ldstr    aImportdatabase// "ImportDatabaseAsync"
0x4414e  newobj   instance void SpartanFunctionLogger::.ctor(string methodName)
0x44153  stfld    class SpartanFunctionLogger <ImportDatabaseAsync>d__31::<logger>5__2
0x44158  ldarg.0
0x44159  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::.ctor()
0x4415e  stfld    object <ImportDatabaseAsync>d__31::<inputData>5__3
0x44163  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__31::<>p__0
0x44168  brtrue.s loc_441A3
0x4416a  ldc.i4.0
0x4416b  ldstr    aTargetazurereg// "TargetAzureRegion"
0x44170  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x44175  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4417a  ldc.i4.2
0x4417b  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x44180  dup
0x44181  ldc.i4.0
0x44182  ldc.i4.0
0x44183  ldnull
0x44184  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x44189  stelem.ref
0x4418a  dup
0x4418b  ldc.i4.1
0x4418c  ldc.i4.1
0x4418d  ldnull
0x4418e  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x44193  stelem.ref
0x44194  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x44199  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x4419e  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__31::<>p__0
0x441a3  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__31::<>p__0
0x441a8  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x441ad  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__31::<>p__0
0x441b2  ldarg.0
0x441b3  ldfld    object <ImportDatabaseAsync>d__31::<inputData>5__3
0x441b8  ldarg.0
0x441b9  ldfld    string <ImportDatabaseAsync>d__31::azureRegion
0x441be  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x441c3  pop
0x441c4  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__31::<>p__1
0x441c9  brtrue.s loc_44204
0x441cb  ldc.i4.0
0x441cc  ldstr    aStorageuri_0// "StorageUri"
0x441d1  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x441d6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x441db  ldc.i4.2
0x441dc  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x441e1  dup
0x441e2  ldc.i4.0
0x441e3  ldc.i4.0
0x441e4  ldnull
0x441e5  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x441ea  stelem.ref
0x441eb  dup
0x441ec  ldc.i4.1
0x441ed  ldc.i4.1
0x441ee  ldnull
0x441ef  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x441f4  stelem.ref
0x441f5  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x441fa  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x441ff  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__31::<>p__1
0x44204  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__31::<>p__1
0x44209  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x4420e  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__31::<>p__1
0x44213  ldarg.0
0x44214  ldfld    object <ImportDatabaseAsync>d__31::<inputData>5__3
0x44219  ldarg.0
0x4421a  ldfld    string <ImportDatabaseAsync>d__31::storageUri
0x4421f  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x44224  pop
0x44225  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__31::<>p__2
0x4422a  brtrue.s loc_44265
0x4422c  ldc.i4.0
0x4422d  ldstr    aScalegroupid_0// "ScaleGroupId"
0x44232  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x44237  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4423c  ldc.i4.2
0x4423d  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x44242  dup
0x44243  ldc.i4.0
0x44244  ldc.i4.0
0x44245  ldnull
0x44246  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x4424b  stelem.ref
0x4424c  dup
0x4424d  ldc.i4.1
0x4424e  ldc.i4.1
0x4424f  ldnull
0x44250  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x44255  stelem.ref
0x44256  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x4425b  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>>::Create(!!T0)
0x44260  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__31::<>p__2
0x44265  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__31::<>p__2
0x4426a  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>>::Target
0x4426f  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__31::<>p__2
0x44274  ldarg.0
0x44275  ldfld    object <ImportDatabaseAsync>d__31::<inputData>5__3
0x4427a  ldarg.0
0x4427b  ldfld    valuetype [mscorlib]System.Guid <ImportDatabaseAsync>d__31::scalegroupId
0x44280  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>::Invoke(char, var<u1>, !!T0)
0x44285  pop
0x44286  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__31::<>p__3
0x4428b  brtrue.s loc_442C6
0x4428d  ldc.i4.0
0x4428e  ldstr    aTiergroup_1// "TierGroup"
0x44293  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x44298  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4429d  ldc.i4.2
0x4429e  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x442a3  dup
0x442a4  ldc.i4.0
0x442a5  ldc.i4.0
0x442a6  ldnull
0x442a7  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x442ac  stelem.ref
0x442ad  dup
0x442ae  ldc.i4.1
0x442af  ldc.i4.1
0x442b0  ldnull
0x442b1  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x442b6  stelem.ref
0x442b7  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x442bc  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Create(!!T0)
0x442c1  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__31::<>p__3
0x442c6  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__31::<>p__3
0x442cb  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>>::Target
0x442d0  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>> <>o__31::<>p__3
0x442d5  ldarg.0
0x442d6  ldfld    object <ImportDatabaseAsync>d__31::<inputData>5__3
0x442db  ldarg.0
0x442dc  ldfld    string <ImportDatabaseAsync>d__31::tierGroup
0x442e1  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string, object>::Invoke(char, var<u1>, !!T0)
0x442e6  pop
0x442e7  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__31::<>p__4
0x442ec  brtrue.s loc_44327
0x442ee  ldc.i4.0
0x442ef  ldstr    aOrganizationid_0// "OrganizationId"
0x442f4  ldtoken  Microsoft.Crm.Admin.AdminService.Spartan.SpartanService
0x442f9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x442fe  ldc.i4.2
0x442ff  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x44304  dup
0x44305  ldc.i4.0
0x44306  ldc.i4.0
0x44307  ldnull
0x44308  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x4430d  stelem.ref
0x4430e  dup
0x4430f  ldc.i4.1
0x44310  ldc.i4.1
0x44311  ldnull
0x44312  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x44317  stelem.ref
0x44318  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::SetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x4431d  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>>::Create(!!T0)
0x44322  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__31::<>p__4
0x44327  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__31::<>p__4
0x4432c  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>>::Target
0x44331  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>> <>o__31::<>p__4
0x44336  ldarg.0
0x44337  ldfld    object <ImportDatabaseAsync>d__31::<inputData>5__3
0x4433c  ldarg.0
0x4433d  ldfld    valuetype [mscorlib]System.Guid <ImportDatabaseAsync>d__31::organizationId
0x44342  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, valuetype [mscorlib]System.Guid, object>::Invoke(char, var<u1>, !!T0)
0x44347  pop
0x44348  nop
0x44349  ldloc.0
0x4434a  brfalse  loc_44435
0x4434f  ldloc.0
0x44350  ldc.i4.1
0x44351  beq      loc_446AF
0x44356  ldarg.0
0x44357  ldarg.0
0x44358  ldfld    valuetype [mscorlib]System.Guid <ImportDatabaseAsync>d__31::scalegroupId
0x4435d  call     string Microsoft.Crm.Admin.AdminService.LogicalGroupKeyProvider::CreateLogicalServerGroupKey(valuetype [mscorlib]System.Guid scalegroupId)
0x44362  stfld    string <ImportDatabaseAsync>d__31::<logicalServerGroupKey>5__4
0x44367  ldsfld   class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ISpartanClient Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::_client
0x4436c  newobj   instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.ImportDatabaseRequestProperty::.ctor()
0x44371  dup
0x44372  ldarg.0
0x44373  ldfld    string <ImportDatabaseAsync>d__31::operationId
0x44378  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.ImportDatabaseRequestProperty::set_OperationId(string)
0x4437d  dup
0x4437e  ldarg.0
0x4437f  ldfld    string <ImportDatabaseAsync>d__31::azureRegion
0x44384  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CommunicationRequestProperty::set_Location(string)
0x44389  dup
0x4438a  ldarg.0
0x4438b  ldfld    string <ImportDatabaseAsync>d__31::<logicalServerGroupKey>5__4
0x44390  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.ImportDatabaseRequestProperty::set_LogicalServerGroupKey(string)
0x44395  dup
0x44396  ldarg.0
0x44397  ldfld    string <ImportDatabaseAsync>d__31::tierGroup
0x4439c  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x443a1  brtrue.s loc_443AB
0x443a3  ldarg.0
0x443a4  ldfld    string <ImportDatabaseAsync>d__31::tierGroup
0x443a9  br.s     loc_443B0
0x443ab  ldsfld   string Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::SpartanDefaultTierGroup
0x443b0  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.ImportDatabaseRequestProperty::set_TargetDatabaseTierGroup(string)
0x443b5  dup
0x443b6  ldarg.0
0x443b7  ldfld    string <ImportDatabaseAsync>d__31::storageUri
0x443bc  newobj   instance void [System]System.Uri::.ctor(string)
0x443c1  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.ImportDatabaseRequestProperty::set_StorageUri(class [System]System.Uri)
0x443c6  dup
0x443c7  ldarg.0
0x443c8  ldfld    string <ImportDatabaseAsync>d__31::sasToken
0x443cd  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.ImportDatabaseRequestProperty::set_StorageKey(string)
0x443d2  dup
0x443d3  ldstr    aSharedaccesske// "SharedAccessKey"
0x443d8  callvirt instance void [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.ImportDatabaseRequestProperty::set_StorageKeyType(string)
0x443dd  ldloca.s 5
0x443df  initobj  [mscorlib]System.TimeSpan
0x443e5  ldloc.s  5
0x443e7  newobj   instance void [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ImportDatabaseParameter::.ctor(class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.ImportDatabaseRequestProperty, valuetype [mscorlib]System.TimeSpan)
0x443ec  ldarg.0
0x443ed  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <ImportDatabaseAsync>d__31::cancellationToken
0x443f2  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse> [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ISpartanClient::ImportDatabaseAsync(class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.ImportDatabaseParameter, valuetype [mscorlib]System.Threading.CancellationToken)
0x443f7  ldc.i4.0
0x443f8  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse>::ConfigureAwait(!!T0)
0x443fd  stloc.s  6
0x443ff  ldloca.s 6
0x44401  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse>::GetAwaiter()
0x44406  stloc.s  4
0x44408  ldloca.s 4
0x4440a  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse>::get_IsCompleted()
0x4440f  brtrue.s loc_44452
0x44411  ldarg.0
0x44412  ldc.i4.0
0x44413  dup
0x44414  stloc.0
0x44415  stfld    int32 <ImportDatabaseAsync>d__31::<>1__state
0x4441a  ldarg.0
0x4441b  ldloc.s  4
0x4441d  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse> <ImportDatabaseAsync>d__31::<>u__1
0x44422  ldarg.0
0x44423  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier> <ImportDatabaseAsync>d__31::<>t__builder
0x44428  ldloca.s 4
0x4442a  ldarg.0
0x4442b  call     T0x2B0000FC
0x44430  leave    loc_44845
0x44435  ldarg.0
0x44436  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse> <ImportDatabaseAsync>d__31::<>u__1
0x4443b  stloc.s  4
0x4443d  ldarg.0
0x4443e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse> <ImportDatabaseAsync>d__31::<>u__1
0x44443  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse>
0x44449  ldarg.0
0x4444a  ldc.i4.m1
0x4444b  dup
0x4444c  stloc.0
0x4444d  stfld    int32 <ImportDatabaseAsync>d__31::<>1__state
0x44452  ldloca.s 4
0x44454  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse>::GetResult()
0x44459  stloc.3
0x4445a  ldloc.3
0x4445b  call     void Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::ThrowExceptionOnFailure(class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.CommunicationResponseProperty response)
0x44460  ldloc.3
0x44461  callvirt instance class [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.DatabaseCreateResponseProperty [Spartan.Client]Microsoft.Dynamics.DataServices.Spartan.Client.DatabaseCreateResponse::get_ResponseProperty()
0x44466  callvirt instance string [Spartan.Common]Microsoft.Dynamics.DataServices.Spartan.Common.Communication.DatabaseCreateResponseProperty::get_ConnectionString()
0x4446b  call     void Microsoft.Crm.Admin.AdminService.Spartan.SpartanService::AddDevTestPrincipalToDatabase(string connectionstring)
0x44470  ldarg.0
  ... truncated ...
```
