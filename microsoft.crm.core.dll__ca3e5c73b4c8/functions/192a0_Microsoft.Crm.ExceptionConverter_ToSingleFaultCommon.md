# Microsoft.Crm.ExceptionConverter::ToSingleFaultCommon

- ea: `0x192a0`
- end: `0x19509`
- name: `Microsoft.Crm.ExceptionConverter::ToSingleFaultCommon`
- size: `617`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x190d0`
- `0x19150`
- `0x19510`

## callees

- `0x18910`
- `0x18950`
- `0x19190`
- `0x191a0`
- `0x191c0`
- `0x19250`
- `0x192a0`
- `0x1a5b0`
- `0x1f4b0`
- `0x1f510`
- `0x66b80`

## string_xrefs

- `0x192fb`: `PluginTrace`
- `0x1930d`: `PluginTrace`
- `0x192b8`: `ToSingleFaultCommon: enter`
- `0x1935d`: `no PluginTrace`
- `0x1941f`: `ValidationPath`
- `0x19431`: `ValidationPath`
- `0x19451`: `ValidationPath`

## pseudocode

```c

```

## disassembly

```asm
0x192a0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x192a5  ldarg.0
0x192a6  call     instance valuetype Microsoft.Crm.TraceCategory Microsoft.Crm.ExceptionConverter::get_TraceCategory()
0x192ab  ldstr    a0// "{0}"
0x192b0  ldc.i4.1
0x192b1  newarr   [mscorlib]System.Object
0x192b6  dup
0x192b7  ldc.i4.0
0x192b8  ldstr    aTosinglefaultc// "ToSingleFaultCommon: enter"
0x192bd  stelem.ref
0x192be  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x192c3  ldarg.1
0x192c4  brtrue.s loc_192C8
0x192c6  ldnull
0x192c7  ret
0x192c8  ldc.i4.1
0x192c9  stsfld   bool Microsoft.Crm.ExceptionConverter::_conversionDone
0x192ce  ldarg.0
0x192cf  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault Microsoft.Crm.ExceptionConverter::get_GetNewFault()
0x192d4  stloc.0
0x192d5  ldloc.0
0x192d6  ldarg.2
0x192d7  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::set_ErrorCode(int32)
0x192dc  ldloc.0
0x192dd  ldarg.3
0x192de  dup
0x192df  brtrue.s loc_192E8
0x192e1  pop
0x192e2  ldarg.1
0x192e3  callvirt instance string [mscorlib]System.Exception::get_Message()
0x192e8  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::set_Message(string)
0x192ed  ldarg.1
0x192ee  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x192f3  brfalse.s loc_19345
0x192f5  ldarg.1
0x192f6  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x192fb  ldstr    aPlugintrace// "PluginTrace"
0x19300  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x19305  brfalse.s loc_19345
0x19307  ldarg.1
0x19308  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x1930d  ldstr    aPlugintrace// "PluginTrace"
0x19312  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x19317  isinst   [mscorlib]System.String
0x1931c  stloc.2
0x1931d  ldloc.2
0x1931e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x19323  brtrue.s loc_19368
0x19325  ldarg.0
0x19326  ldloc.0
0x19327  call     string [mscorlib]System.Environment::get_NewLine()
0x1932c  ldloc.2
0x1932d  call     string [mscorlib]System.Environment::get_NewLine()
0x19332  call     string [mscorlib]System.String::Concat(string, string, string)
0x19337  callvirt instance void Microsoft.Crm.ExceptionConverter::SetTraceText(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault fault, string trace)
0x1933c  ldarg.0
0x1933d  ldloc.0
0x1933e  callvirt instance void Microsoft.Crm.ExceptionConverter::WriteTraceText(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault fault)
0x19343  br.s     loc_19368
0x19345  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1934a  ldarg.0
0x1934b  call     instance valuetype Microsoft.Crm.TraceCategory Microsoft.Crm.ExceptionConverter::get_TraceCategory()
0x19350  ldstr    a0// "{0}"
0x19355  ldc.i4.1
0x19356  newarr   [mscorlib]System.Object
0x1935b  dup
0x1935c  ldc.i4.0
0x1935d  ldstr    aNoPlugintrace// "no PluginTrace"
0x19362  stelem.ref
0x19363  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x19368  ldarg.1
0x19369  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x1936e  brfalse.s loc_193EE
0x19370  ldarg.1
0x19371  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x19376  ldstr    aCrmexceptionfa// "CrmExceptionFaults"
0x1937b  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x19380  brfalse.s loc_193EE
0x19382  ldarg.1
0x19383  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x19388  ldstr    aCrmexceptionfa// "CrmExceptionFaults"
0x1938d  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x19392  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault
0x19397  stloc.3
0x19398  ldloc.3
0x19399  brfalse.s loc_193C8
0x1939b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x193a0  ldarg.0
0x193a1  call     instance valuetype Microsoft.Crm.TraceCategory Microsoft.Crm.ExceptionConverter::get_TraceCategory()
0x193a6  ldstr    a0// "{0}"
0x193ab  ldc.i4.1
0x193ac  newarr   [mscorlib]System.Object
0x193b1  dup
0x193b2  ldc.i4.0
0x193b3  ldstr    aCrmexceptionfa_0// "CrmExceptionFaults returned"
0x193b8  stelem.ref
0x193b9  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x193be  ldarg.0
0x193bf  ldloc.0
0x193c0  ldloc.3
0x193c1  callvirt instance void Microsoft.Crm.ExceptionConverter::CopyTraceText(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault sourceFault, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault targetFault)
0x193c6  ldloc.3
0x193c7  ret
0x193c8  ldnull
0x193c9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x193ce  ldarg.0
0x193cf  call     instance valuetype Microsoft.Crm.TraceCategory Microsoft.Crm.ExceptionConverter::get_TraceCategory()
0x193d4  ldstr    a0// "{0}"
0x193d9  ldc.i4.1
0x193da  newarr   [mscorlib]System.Object
0x193df  dup
0x193e0  ldc.i4.0
0x193e1  ldstr    aUnexpectedCrme// "UNEXPECTED: CrmExceptionFaults present "...
0x193e6  stelem.ref
0x193e7  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x193ec  br.s     loc_19411
0x193ee  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x193f3  ldarg.0
0x193f4  call     instance valuetype Microsoft.Crm.TraceCategory Microsoft.Crm.ExceptionConverter::get_TraceCategory()
0x193f9  ldstr    a0// "{0}"
0x193fe  ldc.i4.1
0x193ff  newarr   [mscorlib]System.Object
0x19404  dup
0x19405  ldc.i4.0
0x19406  ldstr    aNoCrmexception// "no CrmExceptionFaults"
0x1940b  stelem.ref
0x1940c  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x19411  ldarg.1
0x19412  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x19417  brfalse.s loc_1945D
0x19419  ldarg.1
0x1941a  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x1941f  ldstr    aValidationpath// "ValidationPath"
0x19424  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x19429  brfalse.s loc_1945D
0x1942b  ldarg.1
0x1942c  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x19431  ldstr    aValidationpath// "ValidationPath"
0x19436  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x1943b  isinst   [mscorlib]System.String
0x19440  stloc.s  4
0x19442  ldloc.s  4
0x19444  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x19449  brtrue.s loc_1945D
0x1944b  ldloc.0
0x1944c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ErrorDetailCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorDetails()
0x19451  ldstr    aValidationpath// "ValidationPath"
0x19456  ldloc.s  4
0x19458  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x1945d  ldloc.0
0x1945e  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x19463  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::set_Timestamp(valuetype [mscorlib]System.DateTime)
0x19468  ldarg.0
0x19469  callvirt instance bool Microsoft.Crm.ExceptionConverter::get_IncludeCallStack()
0x1946e  brfalse.s loc_19486
0x19470  ldloc.0
0x19471  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ErrorDetailCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorDetails()
0x19476  ldstr    aCallstack// "CallStack"
0x1947b  ldarg.1
0x1947c  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x19481  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x19486  ldarg.0
0x19487  ldfld    class FaultExceptionCreatedHandler Microsoft.Crm.ExceptionConverter::FaultExceptionCreated
0x1948c  brfalse.s loc_194A1
0x1948e  ldarg.0
0x1948f  ldfld    class FaultExceptionCreatedHandler Microsoft.Crm.ExceptionConverter::FaultExceptionCreated
0x19494  ldarg.0
0x19495  ldloc.0
0x19496  ldarg.1
0x19497  newobj   instance void Microsoft.Crm.FaultExceptionCreated::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault faultException, class [mscorlib]System.Exception originalException)
0x1949c  callvirt instance void FaultExceptionCreatedHandler::Invoke(object sender, class Microsoft.Crm.FaultExceptionCreated e)
0x194a1  call     valuetype [mscorlib]System.Guid [mscorlib]System.Diagnostics.Tracing.EventSource::get_CurrentThreadActivityId()
0x194a6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x194ab  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x194b0  brfalse.s loc_194BC
0x194b2  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x194b7  call     void [mscorlib]System.Diagnostics.Tracing.EventSource::SetCurrentThreadActivityId(valuetype [mscorlib]System.Guid)
0x194bc  ldloc.0
0x194bd  call     valuetype [mscorlib]System.Guid [mscorlib]System.Diagnostics.Tracing.EventSource::get_CurrentThreadActivityId()
0x194c2  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::set_ActivityId(valuetype [mscorlib]System.Guid)
0x194c7  ldarg.1
0x194c8  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.InvalidPluginExecutionException
0x194cd  stloc.1
0x194ce  ldloc.1
0x194cf  brfalse.s loc_19507
0x194d1  ldloc.0
0x194d2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ErrorDetailCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorDetails()
0x194d7  ldstr    aOperationstatu// "OperationStatus"
0x194dc  ldloc.1
0x194dd  callvirt instance valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OperationStatus [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.InvalidPluginExecutionException::get_Status()
0x194e2  box      [mscorlib]System.Int32
0x194e7  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x194ec  ldloc.0
0x194ed  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ErrorDetailCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorDetails()
0x194f2  ldstr    aSuberrorcode// "SubErrorCode"
0x194f7  ldloc.1
0x194f8  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.InvalidPluginExecutionException::get_ErrorCode()
0x194fd  box      [mscorlib]System.Int32
0x19502  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x19507  ldloc.0
0x19508  ret
```
