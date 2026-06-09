# Microsoft.Crm.Sandbox.SandboxAppDomainHelper::HandleException

- ea: `0x10d0`
- end: `0x123d`
- name: `Microsoft.Crm.Sandbox.SandboxAppDomainHelper::HandleException`
- size: `365`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x7b0`
- `0x1240`

## callees

- `0x10d0`
- `0x1990`
- `0x1e00`
- `0x1e80`

## string_xrefs

- `0x1126`: `tracingService`
- `0x112b`: `SandboxAppDomainHelper.Execute: CRM Sandbox Internal Error: tracingService`
- `0x1143`: `PluginTrace`
- `0x122c`: `PluginTrace`
- `0x115d`: `SandboxAppDomainHelper.Execute: no PluginTrace`
- `0x1175`: `SandboxAppDomainHelper.Execute: copy TraceText to child trace info`
- `0x11a2`: `SandboxAppDomainHelper.Execute: trace child trace info to tracing service`
- `0x11fc`: `SandboxAppDomainHelper.Execute: copy from tracing service to TraceText`
- `0x121b`: `SandboxAppDomainHelper.Execute: copy from tracing service to PluginTrace`

## pseudocode

```c

```

## disassembly

```asm
0x10d0  ldarg.s  4
0x10d2  brfalse.s loc_10EE
0x10d4  ldarg.2
0x10d5  ldc.i4.3
0x10d6  ldstr    aSandboxappdoma_30// "SandboxAppDomainHelper.Execute: process"...
0x10db  ldarg.1
0x10dc  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x10e1  call     string [mscorlib]System.String::Concat(object, object)
0x10e6  ldnull
0x10e7  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x10ec  br.s     loc_1123
0x10ee  ldarg.2
0x10ef  ldc.i4.3
0x10f0  ldc.i4.4
0x10f1  newarr   [mscorlib]System.Object
0x10f6  dup
0x10f7  ldc.i4.0
0x10f8  ldstr    aSandboxappdoma_30// "SandboxAppDomainHelper.Execute: process"...
0x10fd  stelem.ref
0x10fe  dup
0x10ff  ldc.i4.1
0x1100  ldarg.1
0x1101  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x1106  stelem.ref
0x1107  dup
0x1108  ldc.i4.2
0x1109  ldstr    asc_38FC// ": "
0x110e  stelem.ref
0x110f  dup
0x1110  ldc.i4.3
0x1111  ldarg.1
0x1112  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1117  stelem.ref
0x1118  call     string [mscorlib]System.String::Concat(object[])
0x111d  ldnull
0x111e  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x1123  ldarg.3
0x1124  brtrue.s loc_1136
0x1126  ldstr    aTracingservice// "tracingService"
0x112b  ldstr    aSandboxappdoma_31// "SandboxAppDomainHelper.Execute: CRM San"...
0x1130  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string, string)
0x1135  throw
0x1136  ldarg.1
0x1137  isinst   class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>
0x113c  stloc.0
0x113d  ldarg.1
0x113e  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x1143  ldstr    aPlugintrace// "PluginTrace"
0x1148  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x114d  isinst   [mscorlib]System.String
0x1152  stloc.1
0x1153  ldloc.1
0x1154  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1159  brfalse.s loc_1198
0x115b  ldarg.2
0x115c  ldc.i4.3
0x115d  ldstr    aSandboxappdoma_32// "SandboxAppDomainHelper.Execute: no Plug"...
0x1162  ldnull
0x1163  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x1168  ldloc.0
0x1169  brfalse.s loc_1198
0x116b  ldloc.0
0x116c  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1171  brfalse.s loc_1198
0x1173  ldarg.2
0x1174  ldc.i4.3
0x1175  ldstr    aSandboxappdoma_33// "SandboxAppDomainHelper.Execute: copy Tr"...
0x117a  ldnull
0x117b  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x1180  ldloc.0
0x1181  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1186  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault::get_TraceText()
0x118b  stloc.1
0x118c  ldloc.0
0x118d  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1192  ldnull
0x1193  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault::set_TraceText(string)
0x1198  ldloc.1
0x1199  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x119e  brtrue.s loc_11E2
0x11a0  ldarg.2
0x11a1  ldc.i4.3
0x11a2  ldstr    aSandboxappdoma_34// "SandboxAppDomainHelper.Execute: trace c"...
0x11a7  ldnull
0x11a8  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x11ad  ldarg.3
0x11ae  call     string [mscorlib]System.Environment::get_NewLine()
0x11b3  ldstr    asc_4F06// "\t"
0x11b8  ldloc.1
0x11b9  call     string [mscorlib]System.Environment::get_NewLine()
0x11be  call     string [mscorlib]System.Environment::get_NewLine()
0x11c3  ldstr    asc_4F06// "\t"
0x11c8  call     string [mscorlib]System.String::Concat(string, string)
0x11cd  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11d2  call     string [mscorlib]System.String::Concat(string, string, string)
0x11d7  ldc.i4.0
0x11d8  newarr   [mscorlib]System.Object
0x11dd  callvirt instance void Microsoft.Crm.Sandbox.SandboxTracingService::Trace(string format, object[] args)
0x11e2  ldarg.3
0x11e3  callvirt instance string Microsoft.Crm.Sandbox.SandboxTracingService::get_TraceInfo()
0x11e8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11ed  brtrue.s loc_123C
0x11ef  ldloc.0
0x11f0  brfalse.s loc_1219
0x11f2  ldloc.0
0x11f3  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x11f8  brfalse.s loc_1219
0x11fa  ldarg.2
0x11fb  ldc.i4.3
0x11fc  ldstr    aSandboxappdoma_35// "SandboxAppDomainHelper.Execute: copy fr"...
0x1201  ldnull
0x1202  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x1207  ldloc.0
0x1208  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x120d  ldarg.3
0x120e  callvirt instance string Microsoft.Crm.Sandbox.SandboxTracingService::get_TraceInfo()
0x1213  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault::set_TraceText(string)
0x1218  ret
0x1219  ldarg.2
0x121a  ldc.i4.3
0x121b  ldstr    aSandboxappdoma_36// "SandboxAppDomainHelper.Execute: copy fr"...
0x1220  ldnull
0x1221  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x1226  ldarg.1
0x1227  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x122c  ldstr    aPlugintrace// "PluginTrace"
0x1231  ldarg.3
0x1232  callvirt instance string Microsoft.Crm.Sandbox.SandboxTracingService::get_TraceInfo()
0x1237  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x123c  ret
```
