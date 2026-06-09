# Microsoft.Crm.Asynchronous.YammerPostOperation::InternalExecute

- ea: `0x8ea0`
- end: `0x905d`
- name: `Microsoft.Crm.Asynchronous.YammerPostOperation::InternalExecute`
- size: `445`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x8d20`
- `0x8d50`
- `0x8ea0`
- `0x9060`
- `0x9220`

## string_xrefs

- `0x8f3b`: `UpdateYammerPost`
- `0x9039`: `AsyncHandler::YammerPostOperation could not complete because of exception {0}`

## pseudocode

```c

```

## disassembly

```asm
0x8ea0  ldarg.1
0x8ea1  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0x8ea6  ldc.i4.s 0x31
0x8ea8  ceq
0x8eaa  ldstr    aOperationTypeM_5// "Operation type must be 'PostToYammer'"
0x8eaf  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x8eb4  ldarg.0
0x8eb5  ldarg.1
0x8eb6  stfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.YammerPostOperation::_asyncEvent
0x8ebb  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x8ec0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x8ec5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_YammerPosts()
0x8eca  ldarg.0
0x8ecb  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.YammerPostOperation::_asyncEvent
0x8ed0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x8ed5  ldnull
0x8ed6  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::IsEnabled(valuetype [mscorlib]System.Guid, class [mscorlib]System.Version)
0x8edb  brtrue.s loc_8EE5
0x8edd  ldc.i4.s 0x1E
0x8edf  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRemoveEventResult::.ctor(int32)
0x8ee4  ret
0x8ee5  ldarg.0
0x8ee6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Asynchronous.YammerPostOperation::_userIdToOauthTokenDictionary
0x8eeb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Clear()
0x8ef0  ldarg.0
0x8ef1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int64, bool>::.ctor()
0x8ef6  dup
0x8ef7  ldc.i4   0xC0006302
0x8efc  conv.u8
0x8efd  ldc.i4.0
0x8efe  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int64, bool>::Add(var<u1>, !!T0)
0x8f03  dup
0x8f04  ldc.i4   0xC0006303
0x8f09  conv.u8
0x8f0a  ldc.i4.0
0x8f0b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int64, bool>::Add(var<u1>, !!T0)
0x8f10  dup
0x8f11  ldc.i4   0xC0006300
0x8f16  conv.u8
0x8f17  ldc.i4.0
0x8f18  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int64, bool>::Add(var<u1>, !!T0)
0x8f1d  dup
0x8f1e  ldc.i4   0xC0006301
0x8f23  conv.u8
0x8f24  ldc.i4.0
0x8f25  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int64, bool>::Add(var<u1>, !!T0)
0x8f2a  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int64, bool> Microsoft.Crm.Asynchronous.YammerPostOperation::_eventLogIdToEventLogWrittenDictionary
0x8f2f  ldarg.0
0x8f30  call     instance void Microsoft.Crm.Asynchronous.YammerPostOperation::PopulateYammerConfigurationSettings()
0x8f35  ldarg.0
0x8f36  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x8f3b  ldstr    aUpdateyammerpo// "UpdateYammerPost"
0x8f40  newobj   instance void Microsoft.Crm.Asynchronous.UpdateAsyncJobDataAccess::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration config, string name)
0x8f45  stloc.0
0x8f46  ldc.i4.0
0x8f47  stloc.2
0x8f48  ldc.i4.0
0x8f49  stloc.3
0x8f4a  ldc.i4.0
0x8f4b  stloc.s  4
0x8f4d  ldc.i4.0
0x8f4e  stloc.s  4
0x8f50  ldarg.0
0x8f51  call     instance valuetype SendToYammerJobState Microsoft.Crm.Asynchronous.YammerPostOperation::DoYammerPostOperation()
0x8f56  stloc.s  5
0x8f58  ldloc.s  5
0x8f5a  ldc.i4.1
0x8f5b  sub
0x8f5c  switch   loc_8FAB, loc_8F7B, loc_8FB0, loc_8F7B, loc_8FB0
0x8f75  ldloc.s  5
0x8f77  ldc.i4.s 0x63
0x8f79  bne.un.s loc_8FB2
0x8f7b  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x8f80  stloc.s  6
0x8f82  ldloca.s 6
0x8f84  ldarg.0
0x8f85  ldfld    valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.YammerPostOperation::YammerMinWaitTimeForPostsInSec
0x8f8a  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Add(valuetype [mscorlib]System.TimeSpan)
0x8f8f  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime)
0x8f94  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UniversalTime()
0x8f99  stloc.1
0x8f9a  ldloc.0
0x8f9b  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.YammerPostOperation::YammerRecurringJobId
0x8fa0  ldloc.1
0x8fa1  ldc.i4.1
0x8fa2  callvirt instance void Microsoft.Crm.Asynchronous.UpdateAsyncJobDataAccess::PostponeOrPrepone(valuetype [mscorlib]System.Guid jobId, valuetype [mscorlib]System.DateTime postPoneUntil, [opt] bool unconditionalUpdate)
0x8fa7  ldc.i4.1
0x8fa8  stloc.3
0x8fa9  br.s     loc_8FB2
0x8fab  ldc.i4.1
0x8fac  stloc.s  4
0x8fae  br.s     loc_8FB2
0x8fb0  ldc.i4.1
0x8fb1  stloc.3
0x8fb2  ldloc.2
0x8fb3  ldarg.0
0x8fb4  ldfld    int32 Microsoft.Crm.Asynchronous.YammerPostOperation::_maxYammerPostsInBatch
0x8fb9  add
0x8fba  stloc.2
0x8fbb  ldloc.3
0x8fbc  ldc.i4.0
0x8fbd  ceq
0x8fbf  ldloc.s  4
0x8fc1  and
0x8fc2  brfalse.s loc_8FCD
0x8fc4  ldloc.2
0x8fc5  ldarg.0
0x8fc6  ldfld    int32 Microsoft.Crm.Asynchronous.YammerPostOperation::_maxYammerPostsToProcessByAsyncJob
0x8fcb  blt.s    loc_8F4D
0x8fcd  ldloc.s  4
0x8fcf  brfalse.s loc_8FFD
0x8fd1  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x8fd6  stloc.s  6
0x8fd8  ldloca.s 6
0x8fda  ldarg.0
0x8fdb  ldfld    valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.YammerPostOperation::YammerMinWaitTimeForAsyncJobToRecurInSec
0x8fe0  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Add(valuetype [mscorlib]System.TimeSpan)
0x8fe5  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime)
0x8fea  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UniversalTime()
0x8fef  stloc.1
0x8ff0  ldloc.0
0x8ff1  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.YammerPostOperation::YammerRecurringJobId
0x8ff6  ldloc.1
0x8ff7  ldc.i4.1
0x8ff8  callvirt instance void Microsoft.Crm.Asynchronous.UpdateAsyncJobDataAccess::PostponeOrPrepone(valuetype [mscorlib]System.Guid jobId, valuetype [mscorlib]System.DateTime postPoneUntil, [opt] bool unconditionalUpdate)
0x8ffd  leave.s  loc_9055
0x8fff  stloc.s  7
0x9001  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x9006  stloc.s  6
0x9008  ldloca.s 6
0x900a  ldarg.0
0x900b  ldfld    valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.YammerPostOperation::YammerMinWaitTimeForPostsInSec
0x9010  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Add(valuetype [mscorlib]System.TimeSpan)
0x9015  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime)
0x901a  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UniversalTime()
0x901f  stloc.s  8
0x9021  ldloc.0
0x9022  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.YammerPostOperation::YammerRecurringJobId
0x9027  ldloc.s  8
0x9029  ldc.i4.1
0x902a  callvirt instance void Microsoft.Crm.Asynchronous.UpdateAsyncJobDataAccess::PostponeOrPrepone(valuetype [mscorlib]System.Guid jobId, valuetype [mscorlib]System.DateTime postPoneUntil, [opt] bool unconditionalUpdate)
0x902f  ldloc.s  7
0x9031  ldarg.0
0x9032  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.YammerPostOperation::_organizationId
0x9037  ldc.i4.s 0x15
0x9039  ldstr    aAsynchandlerYa// "AsyncHandler::YammerPostOperation could"...
0x903e  ldc.i4.1
0x903f  newarr   [mscorlib]System.Object
0x9044  dup
0x9045  ldc.i4.0
0x9046  ldloc.s  7
0x9048  callvirt instance string [mscorlib]System.Exception::get_Message()
0x904d  stelem.ref
0x904e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9053  rethrow
0x9055  ldc.i4.s 0x1E
0x9057  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRemoveEventResult::.ctor(int32)
0x905c  ret
```
