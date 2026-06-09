# Microsoft.Crm.Sandbox.SandboxRestrictedTrace::TraceExceptionTraceData

- ea: `0x1a20`
- end: `0x1b2c`
- name: `Microsoft.Crm.Sandbox.SandboxRestrictedTrace::TraceExceptionTraceData`
- size: `268`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x7b0`
- `0x1240`

## callees

- `0x1990`
- `0x1a20`

## string_xrefs

- `0x1a30`: `PluginTrace`
- `0x1a4f`: `: no PluginTrace data`
- `0x1a68`: `: exception PluginTrace data: `

## pseudocode

```c

```

## disassembly

```asm
0x1a20  ldarg.0
0x1a21  brtrue.s loc_1A2A
0x1a23  ldstr    aSandboxrestric// "SandboxRestrictedTrace.TraceExceptionTr"...
0x1a28  starg.s  0
0x1a2a  ldarg.1
0x1a2b  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x1a30  ldstr    aPlugintrace// "PluginTrace"
0x1a35  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x1a3a  isinst   [mscorlib]System.String
0x1a3f  stloc.0
0x1a40  ldloc.0
0x1a41  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1a46  brfalse.s loc_1A61
0x1a48  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1a4d  ldc.i4.3
0x1a4e  ldarg.0
0x1a4f  ldstr    aNoPlugintraceD// ": no PluginTrace data"
0x1a54  call     string [mscorlib]System.String::Concat(string, string)
0x1a59  ldnull
0x1a5a  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x1a5f  br.s     loc_1A83
0x1a61  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1a66  ldc.i4.3
0x1a67  ldarg.0
0x1a68  ldstr    aExceptionPlugi// ": exception PluginTrace data: "
0x1a6d  ldloc.0
0x1a6e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1a73  box      [mscorlib]System.Int32
0x1a78  call     string [mscorlib]System.String::Concat(object, object, object)
0x1a7d  ldnull
0x1a7e  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x1a83  ldarg.1
0x1a84  isinst   class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>
0x1a89  stloc.1
0x1a8a  ldloc.1
0x1a8b  brfalse  loc_1B26
0x1a90  ldloc.1
0x1a91  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1a96  brfalse  loc_1B26
0x1a9b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1aa0  ldc.i4.3
0x1aa1  ldarg.0
0x1aa2  ldstr    aErrorcode_0// ": ErrorCode: "
0x1aa7  ldloc.1
0x1aa8  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1aad  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x1ab2  stloc.2
0x1ab3  ldloca.s 2
0x1ab5  ldstr    aX8// "X8"
0x1aba  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1abf  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x1ac4  call     string [mscorlib]System.String::Concat(string, string, string)
0x1ac9  ldnull
0x1aca  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x1acf  ldloc.1
0x1ad0  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1ad5  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault::get_TraceText()
0x1ada  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1adf  brfalse.s loc_1AFA
0x1ae1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1ae6  ldc.i4.3
0x1ae7  ldarg.0
0x1ae8  ldstr    aNoTracetext// ": no TraceText"
0x1aed  call     string [mscorlib]System.String::Concat(string, string)
0x1af2  ldnull
0x1af3  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x1af8  br.s     loc_1B26
0x1afa  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1aff  ldc.i4.3
0x1b00  ldarg.0
0x1b01  ldstr    aExceptionTrace// ": exception TraceText: "
0x1b06  ldloc.1
0x1b07  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1b0c  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault::get_TraceText()
0x1b11  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1b16  box      [mscorlib]System.Int32
0x1b1b  call     string [mscorlib]System.String::Concat(object, object, object)
0x1b20  ldnull
0x1b21  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x1b26  leave.s  loc_1B2B
0x1b28  pop
0x1b29  leave.s  loc_1B2B
0x1b2b  ret
```
