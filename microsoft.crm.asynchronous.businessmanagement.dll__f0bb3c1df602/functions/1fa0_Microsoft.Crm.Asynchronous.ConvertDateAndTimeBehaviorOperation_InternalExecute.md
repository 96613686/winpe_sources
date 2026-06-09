# Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::InternalExecute

- ea: `0x1fa0`
- end: `0x21b2`
- name: `Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::InternalExecute`
- size: `530`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1fa0`
- `0x21c0`
- `0x2400`
- `0x2760`
- `0x36b0`
- `0x3b90`
- `0x3c30`

## string_xrefs

- `0x204b`: `AsyncHandler::ConvertDateAndTimeBehaviorOperation could not complete because all the specified entities and attributes are invalid. Please check log for more details.`
- `0x2155`: `AsyncHandler::ConvertDateAndTimeBehaviorOperation could not complete because of exception {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1fa0  ldarg.1
0x1fa1  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0x1fa6  ldc.i4.s 0x3E
0x1fa8  ceq
0x1faa  ldstr    aOperationTypeM_1// "Operation type must be 'ConvertDateAndT"...
0x1faf  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1fb4  ldc.i4.0
0x1fb5  stloc.0
0x1fb6  ldarg.0
0x1fb7  ldarg.1
0x1fb8  stfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::_asyncEvent
0x1fbd  ldarg.0
0x1fbe  ldc.i4.0
0x1fbf  stfld    bool Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::_errorOccured
0x1fc4  ldarg.0
0x1fc5  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::_organizationId
0x1fca  ldc.i4.0
0x1fcb  ldc.i4.0
0x1fcc  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1fd1  stloc.1
0x1fd2  ldc.i4.1
0x1fd3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor(bool)
0x1fd8  stloc.2
0x1fd9  ldloc.1
0x1fda  ldarg.0
0x1fdb  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::_asyncEvent
0x1fe0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_OwnerId()
0x1fe5  ldc.i4.0
0x1fe6  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool)
0x1feb  ldarg.0
0x1fec  ldarg.0
0x1fed  ldstr    aJobsummaryhead// "JobSummaryHeader"
0x1ff2  ldloc.1
0x1ff3  call     instance string Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::GetResourceString(string resourceStringKey, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1ff8  stfld    string Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::_jobSummaryHeader
0x1ffd  ldarg.0
0x1ffe  ldarg.1
0x1fff  call     instance class [Microsoft.Crm]Microsoft.Crm.DateTimeConversionData Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::GetConvertDateAndTimeBehaviorOperationData(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent)
0x2004  stloc.3
0x2005  ldarg.0
0x2006  ldfld    bool Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::_errorOccured
0x200b  brfalse.s loc_201F
0x200d  ldarg.0
0x200e  ldstr    aGenericerrorme// "GenericErrorMessage"
0x2013  ldloc.1
0x2014  call     instance string Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::GetResourceString(string resourceStringKey, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2019  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x201e  throw
0x201f  ldarg.0
0x2020  ldloc.3
0x2021  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityAttributeCollection [Microsoft.Crm]Microsoft.Crm.DateTimeConversionData::get_Attributes()
0x2026  ldloc.3
0x2027  callvirt instance string [Microsoft.Crm]Microsoft.Crm.DateTimeConversionData::get_ConversionRule()
0x202c  ldloc.1
0x202d  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class EntityAttributeMetadataMap> Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::RetrieveValidDateAndTimeConversionAttributes(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityAttributeCollection entityAttributeCollection, string conversionRule, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2032  stloc.s  4
0x2034  ldloc.s  4
0x2036  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class EntityAttributeMetadataMap>::get_Count()
0x203b  brtrue.s loc_205D
0x203d  ldnull
0x203e  ldarg.0
0x203f  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::_asyncEvent
0x2044  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x2049  ldc.i4.s 0x15
0x204b  ldstr    aAsynchandlerCo// "AsyncHandler::ConvertDateAndTimeBehavio"...
0x2050  ldc.i4.0
0x2051  newarr   [mscorlib]System.Object
0x2056  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x205b  br.s     loc_207E
0x205d  ldarg.0
0x205e  ldloc.s  4
0x2060  ldloc.3
0x2061  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm]Microsoft.Crm.DateTimeConversionData::get_TimeZoneCode()
0x2066  ldloc.3
0x2067  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.DateTimeConversionData::get_AutoConvert()
0x206c  ldloc.3
0x206d  callvirt instance string [Microsoft.Crm]Microsoft.Crm.DateTimeConversionData::get_ConversionRule()
0x2072  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule::op_Implicit(string)
0x2077  ldloc.1
0x2078  call     instance bool Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::ProcessAttributesForConversion(class [mscorlib]System.Collections.ObjectModel.Collection`1<class EntityAttributeMetadataMap> entityAttributeMetadataMaps, valuetype [mscorlib]System.Nullable`1<int32> timeZoneCode, bool autoConvert, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DateTimeBehaviorConversionRule conversionRule, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x207d  stloc.0
0x207e  ldarg.0
0x207f  ldloc.s  4
0x2081  ldloc.1
0x2082  call     instance void Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::UpdateDateTimeConversionTracker(class [mscorlib]System.Collections.ObjectModel.Collection`1<class EntityAttributeMetadataMap> validEntityAttributes, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2087  ldarg.0
0x2088  ldarg.0
0x2089  ldloc.3
0x208a  callvirt instance string [Microsoft.Crm]Microsoft.Crm.DateTimeConversionData::get_ConversionRule()
0x208f  ldloc.3
0x2090  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.DateTimeConversionData::get_AutoConvert()
0x2095  ldloc.3
0x2096  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm]Microsoft.Crm.DateTimeConversionData::get_TimeZoneCode()
0x209b  ldloc.1
0x209c  call     instance string Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::PrintJobSummaryDetails(string conversionRule, bool autoConvert, valuetype [mscorlib]System.Nullable`1<int32> timeZoneCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x20a1  stfld    string Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::_jobSummary
0x20a6  ldloc.1
0x20a7  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x20ac  leave    loc_218B
0x20b1  stloc.s  5
0x20b3  ldarg.0
0x20b4  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::_asyncEvent
0x20b9  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_OrganizationConfiguration()
0x20be  stloc.s  6
0x20c0  ldstr    aMscrmplatform// "MSCRMPlatform"
0x20c5  ldc.i4   0xC0004410
0x20ca  conv.u8
0x20cb  ldc.i4.6
0x20cc  newarr   [mscorlib]System.String
0x20d1  dup
0x20d2  ldc.i4.0
0x20d3  call     string [mscorlib]System.Environment::get_MachineName()
0x20d8  stelem.ref
0x20d9  dup
0x20da  ldc.i4.1
0x20db  ldarg.0
0x20dc  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::_asyncEvent
0x20e1  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0x20e6  stloc.s  7
0x20e8  ldloca.s 7
0x20ea  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x20ef  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x20f4  stelem.ref
0x20f5  dup
0x20f6  ldc.i4.2
0x20f7  ldarg.0
0x20f8  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::_asyncEvent
0x20fd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x2102  stloc.s  8
0x2104  ldloca.s 8
0x2106  constrained. [mscorlib]System.Guid
0x210c  callvirt instance string [mscorlib]System.Object::ToString()
0x2111  stelem.ref
0x2112  dup
0x2113  ldc.i4.3
0x2114  ldloc.s  6
0x2116  callvirt instance string [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationName()
0x211b  stelem.ref
0x211c  dup
0x211d  ldc.i4.4
0x211e  ldc.i4   0x80040216
0x2123  stloc.s  7
0x2125  ldloca.s 7
0x2127  ldstr    aX// "x"
0x212c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2131  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x2136  stelem.ref
0x2137  dup
0x2138  ldc.i4.5
0x2139  ldloc.s  5
0x213b  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2140  stelem.ref
0x2141  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::WriteEventError(string, int64, string[])
0x2146  ldloc.s  5
0x2148  ldarg.0
0x2149  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::_asyncEvent
0x214e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x2153  ldc.i4.s 0x15
0x2155  ldstr    aAsynchandlerCo_0// "AsyncHandler::ConvertDateAndTimeBehavio"...
0x215a  ldc.i4.1
0x215b  newarr   [mscorlib]System.Object
0x2160  dup
0x2161  ldc.i4.0
0x2162  ldloc.s  5
0x2164  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2169  stelem.ref
0x216a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x216f  ldloc.1
0x2170  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0x2175  rethrow
0x2177  ldloc.2
0x2178  brfalse.s loc_2180
0x217a  ldloc.2
0x217b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2180  endfinally
0x2181  ldloc.1
0x2182  brfalse.s loc_218A
0x2184  ldloc.1
0x2185  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x218a  endfinally
0x218b  ldloc.0
0x218c  brfalse.s loc_21A0
0x218e  ldarg.0
0x218f  ldfld    string Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::_jobSummaryHeader
0x2194  ldarg.0
0x2195  ldfld    string Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::_jobSummary
0x219a  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncCanceledResult::.ctor(string, string)
0x219f  ret
0x21a0  ldarg.0
0x21a1  ldfld    string Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::_jobSummaryHeader
0x21a6  ldarg.0
0x21a7  ldfld    string Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::_jobSummary
0x21ac  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor(string, string)
0x21b1  ret
```
