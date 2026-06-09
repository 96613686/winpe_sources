# Microsoft.Crm.Sandbox.SandboxCallbackService::ProcessException

- ea: `0x2030`
- end: `0x21e7`
- name: `Microsoft.Crm.Sandbox.SandboxCallbackService::ProcessException`
- size: `439`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1f70`
- `0x2480`
- `0x2680`
- `0x2780`

## callees

- `0x2030`
- `0x21f0`
- `0x22d0`

## string_xrefs

- `0x207a`: `SandboxCallbackService.ProcessException: ProcessException for client: {0} : {1}`
- `0x20ab`: `SandboxCallbackService.ProcessException: ProcessException for client: {0} : {1}: {2}`
- `0x20e3`: `SandboxCallbackService.ProcessException: Fault exception - client OK`
- `0x2102`: `SandboxCallbackService.ProcessException: ProcessException for client: {0}: {1}: {2}`
- `0x2188`: `SandboxCallbackService.ProcessException: Error, aborting channel for clientId: {0} Failed with Exception: {1}`
- `0x21bb`: `SandboxCallbackService.ProcessException: Other exception - discard client: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x2030  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExceptionConverter Microsoft.Crm.Sandbox.SandboxCallbackService::exceptionConverter
0x2035  ldarg.1
0x2036  ldloca.s 0
0x2038  call     bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ExceptionConverterExtension::SafeTryConvertToFaultException(class [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter, class [mscorlib]System.Exception, class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>&)
0x203d  ldloc.0
0x203e  ldarg.1
0x203f  ldc.i4.1
0x2040  stloc.3
0x2041  ldloca.s 3
0x2043  constrained. [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxExceptionCategory
0x2049  callvirt instance string [mscorlib]System.Object::ToString()
0x204e  call     void [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxExceptionCategoryHelper::SaveOriginalException(class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>, class [mscorlib]System.Exception, string)
0x2053  brtrue   loc_20F5
0x2058  ldarg.1
0x2059  isinst   class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>
0x205e  stloc.s  4
0x2060  ldloc.s  4
0x2062  brfalse.s loc_209E
0x2064  ldloc.s  4
0x2066  call     bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::ShouldSkipFaultExceptionDetails(class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>)
0x206b  brfalse.s loc_209E
0x206d  ldarg.0
0x206e  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxCallbackService::get_Context()
0x2073  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x2078  ldc.i4.s 0x21
0x207a  ldstr    aSandboxcallbac_1// "SandboxCallbackService.ProcessException"...
0x207f  ldc.i4.2
0x2080  newarr   [mscorlib]System.Object
0x2085  dup
0x2086  ldc.i4.0
0x2087  ldarg.2
0x2088  callvirt instance string class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxSdkListener>::get_ClientId()
0x208d  stelem.ref
0x208e  dup
0x208f  ldc.i4.1
0x2090  ldarg.1
0x2091  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x2096  stelem.ref
0x2097  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x209c  br.s     loc_20D6
0x209e  ldarg.0
0x209f  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxCallbackService::get_Context()
0x20a4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x20a9  ldc.i4.s 0x21
0x20ab  ldstr    aSandboxcallbac_2// "SandboxCallbackService.ProcessException"...
0x20b0  ldc.i4.3
0x20b1  newarr   [mscorlib]System.Object
0x20b6  dup
0x20b7  ldc.i4.0
0x20b8  ldarg.2
0x20b9  callvirt instance string class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxSdkListener>::get_ClientId()
0x20be  stelem.ref
0x20bf  dup
0x20c0  ldc.i4.1
0x20c1  ldarg.1
0x20c2  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x20c7  stelem.ref
0x20c8  dup
0x20c9  ldc.i4.2
0x20ca  ldarg.1
0x20cb  callvirt instance string [mscorlib]System.Exception::get_Message()
0x20d0  stelem.ref
0x20d1  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x20d6  ldarg.0
0x20d7  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxCallbackService::get_Context()
0x20dc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x20e1  ldc.i4.s 0x21
0x20e3  ldstr    aSandboxcallbac_3// "SandboxCallbackService.ProcessException"...
0x20e8  ldc.i4.0
0x20e9  newarr   [mscorlib]System.Object
0x20ee  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x20f3  ldarg.1
0x20f4  ret
0x20f5  ldarg.0
0x20f6  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxCallbackService::get_Context()
0x20fb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x2100  ldc.i4.s 0x21
0x2102  ldstr    aSandboxcallbac_4// "SandboxCallbackService.ProcessException"...
0x2107  ldc.i4.3
0x2108  newarr   [mscorlib]System.Object
0x210d  dup
0x210e  ldc.i4.0
0x210f  ldarg.2
0x2110  callvirt instance string class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxSdkListener>::get_ClientId()
0x2115  stelem.ref
0x2116  dup
0x2117  ldc.i4.1
0x2118  ldarg.1
0x2119  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x211e  stelem.ref
0x211f  dup
0x2120  ldc.i4.2
0x2121  ldarg.1
0x2122  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2127  stelem.ref
0x2128  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x212d  ldarg.1
0x212e  isinst   [System.ServiceModel]System.ServiceModel.CommunicationException
0x2133  stloc.1
0x2134  ldnull
0x2135  stloc.2
0x2136  ldloc.1
0x2137  brtrue.s loc_2141
0x2139  ldarg.1
0x213a  isinst   [Microsoft.Crm.Core]Microsoft.Crm.TimeoutException
0x213f  brfalse.s loc_21AD
0x2141  ldloc.1
0x2142  brfalse.s loc_2154
0x2144  ldloc.0
0x2145  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x214a  ldc.i4   0x80044307
0x214f  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::set_ErrorCode(int32)
0x2154  nop
0x2155  ldarg.2
0x2156  callvirt instance void class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxSdkListener>::Abort()
0x215b  leave.s  loc_21AD
0x215d  stloc.s  5
0x215f  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Exception>::.ctor()
0x2164  dup
0x2165  ldloc.0
0x2166  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Exception>::Add(var<u1>)
0x216b  dup
0x216c  ldloc.s  5
0x216e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Exception>::Add(var<u1>)
0x2173  newobj   instance void [mscorlib]System.AggregateException::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Exception>)
0x2178  stloc.2
0x2179  ldloc.s  5
0x217b  ldarg.0
0x217c  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxCallbackService::get_Context()
0x2181  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x2186  ldc.i4.s 0x21
0x2188  ldstr    aSandboxcallbac_5// "SandboxCallbackService.ProcessException"...
0x218d  ldc.i4.2
0x218e  newarr   [mscorlib]System.Object
0x2193  dup
0x2194  ldc.i4.0
0x2195  ldarg.2
0x2196  callvirt instance string class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxSdkListener>::get_ClientId()
0x219b  stelem.ref
0x219c  dup
0x219d  ldc.i4.1
0x219e  ldloc.s  5
0x21a0  callvirt instance string [mscorlib]System.Object::ToString()
0x21a5  stelem.ref
0x21a6  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x21ab  leave.s  loc_21AD
0x21ad  ldnull
0x21ae  ldarg.0
0x21af  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxCallbackService::get_Context()
0x21b4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x21b9  ldc.i4.s 0x21
0x21bb  ldstr    aSandboxcallbac_6// "SandboxCallbackService.ProcessException"...
0x21c0  ldc.i4.1
0x21c1  newarr   [mscorlib]System.Object
0x21c6  dup
0x21c7  ldc.i4.0
0x21c8  ldarg.2
0x21c9  callvirt instance string class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxSdkListener>::get_ClientId()
0x21ce  stelem.ref
0x21cf  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x21d4  ldarg.0
0x21d5  ldarg.2
0x21d6  call     instance void Microsoft.Crm.Sandbox.SandboxCallbackService::DiscardClient(class Microsoft.Crm.Sandbox.SandboxSdkClient client)
0x21db  ldloc.2
0x21dc  brtrue.s loc_21E0
0x21de  ldloc.0
0x21df  ret
0x21e0  ldloc.2
0x21e1  callvirt instance class [mscorlib]System.AggregateException [mscorlib]System.AggregateException::Flatten()
0x21e6  ret
```
