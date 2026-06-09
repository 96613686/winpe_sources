# Microsoft.Crm.Sandbox.SandboxWorker::HandleException

- ea: `0x2f30`
- end: `0x3081`
- name: `Microsoft.Crm.Sandbox.SandboxWorker::HandleException`
- size: `337`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x2d80`
- `0x3090`
- `0x32d0`
- `0x3630`

## callees

- `0x2f30`

## string_xrefs

- `0x2f5f`: `ExceptionFromPluginExecute`
- `0x2f71`: `ExceptionFromPluginExecute`

## pseudocode

```c

```

## disassembly

```asm
0x2f30  ldsfld   string [mscorlib]System.String::Empty
0x2f35  stloc.0
0x2f36  ldstr    aSandbox// "Sandbox"
0x2f3b  ldarg.s  4
0x2f3d  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_OrgTraceCategory()
0x2f42  call     valuetype [System]System.Diagnostics.TraceLevel [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceSettings::GetHighestTraceLevel(string, string)
0x2f47  ldc.i4.3
0x2f48  ceq
0x2f4a  stloc.1
0x2f4b  ldloc.1
0x2f4c  brtrue.s loc_2F95
0x2f4e  ldarg.1
0x2f4f  brfalse.s loc_2F95
0x2f51  ldarg.1
0x2f52  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x2f57  brfalse.s loc_2F95
0x2f59  ldarg.1
0x2f5a  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x2f5f  ldstr    aExceptionfromp// "ExceptionFromPluginExecute"
0x2f64  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x2f69  brfalse.s loc_2F95
0x2f6b  ldarg.1
0x2f6c  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x2f71  ldstr    aExceptionfromp// "ExceptionFromPluginExecute"
0x2f76  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x2f7b  castclass [mscorlib]System.String
0x2f80  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2f85  brtrue.s loc_2F95
0x2f87  ldarg.1
0x2f88  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x2f8d  callvirt instance string [mscorlib]System.Object::ToString()
0x2f92  stloc.0
0x2f93  br.s     loc_2F9C
0x2f95  ldarg.1
0x2f96  callvirt instance string [mscorlib]System.Object::ToString()
0x2f9b  stloc.0
0x2f9c  ldnull
0x2f9d  ldarg.3
0x2f9e  ldc.i4.s 0x21
0x2fa0  ldstr    aSandboxworkerE// "SandboxWorker: Execute failed for host "...
0x2fa5  ldc.i4.4
0x2fa6  newarr   [mscorlib]System.Object
0x2fab  dup
0x2fac  ldc.i4.0
0x2fad  ldarg.s  4
0x2faf  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ProcessId()
0x2fb4  box      [mscorlib]System.Int32
0x2fb9  stelem.ref
0x2fba  dup
0x2fbb  ldc.i4.1
0x2fbc  ldarg.3
0x2fbd  box      [mscorlib]System.Guid
0x2fc2  stelem.ref
0x2fc3  dup
0x2fc4  ldc.i4.2
0x2fc5  ldloc.0
0x2fc6  stelem.ref
0x2fc7  dup
0x2fc8  ldc.i4.3
0x2fc9  ldarg.s  4
0x2fcb  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::GetCallInfoHierarchy(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo)
0x2fd0  stelem.ref
0x2fd1  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2fd6  ldarg.2
0x2fd7  brfalse.s loc_2FE0
0x2fd9  ldarg.2
0x2fda  ldarg.1
0x2fdb  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::BadExit(class [mscorlib]System.Exception)
0x2fe0  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExceptionConverter Microsoft.Crm.Sandbox.SandboxWorker::_exceptionConverter
0x2fe5  ldarg.1
0x2fe6  ldc.i4.1
0x2fe7  ldloca.s 2
0x2fe9  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter::TryConvertToFaultException(class [mscorlib]System.Exception, bool, class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>&)
0x2fee  brfalse.s loc_306C
0x2ff0  ldloc.2
0x2ff1  ldarg.1
0x2ff2  call     void [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxExceptionCategoryHelper::SaveExceptionInnerException(class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>, class [mscorlib]System.Exception)
0x2ff7  ldarg.1
0x2ff8  isinst   [mscorlib]System.TimeoutException
0x2ffd  ldnull
0x2ffe  cgt.un
0x3000  ldloc.1
0x3001  or
0x3002  brfalse.s loc_300D
0x3004  ldarg.1
0x3005  callvirt instance string [mscorlib]System.Object::ToString()
0x300a  stloc.3
0x300b  br.s     loc_3024
0x300d  ldarg.1
0x300e  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x3013  ldstr    asc_A2A6// "\r\n"
0x3018  ldarg.1
0x3019  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x301e  call     string [mscorlib]System.String::Concat(object, object, object)
0x3023  stloc.3
0x3024  ldarg.1
0x3025  isinst   [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.UnhandledPluginException
0x302a  brfalse.s loc_3046
0x302c  ldloc.2
0x302d  ldloc.3
0x302e  ldc.i4.s 0xA
0x3030  stloc.s  4
0x3032  ldloca.s 4
0x3034  constrained. [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxExceptionCategory
0x303a  callvirt instance string [mscorlib]System.Object::ToString()
0x303f  call     void [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxExceptionCategoryHelper::SaveOriginalException(class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>, string, string)
0x3044  br.s     loc_305D
0x3046  ldloc.2
0x3047  ldloc.3
0x3048  ldc.i4.2
0x3049  stloc.s  4
0x304b  ldloca.s 4
0x304d  constrained. [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxExceptionCategory
0x3053  callvirt instance string [mscorlib]System.Object::ToString()
0x3058  call     void [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxExceptionCategoryHelper::SaveOriginalException(class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>, string, string)
0x305d  ldloc.2
0x305e  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x3063  ldarg.s  5
0x3065  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault::set_ExceptionRetriable(bool)
0x306a  ldloc.2
0x306b  throw
0x306c  ldnull
0x306d  ldarg.3
0x306e  ldc.i4.s 0x21
0x3070  ldstr    aUnexpectedExce// "UNEXPECTED: exception not converted"
0x3075  ldc.i4.0
0x3076  newarr   [mscorlib]System.Object
0x307b  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3080  ret
```
