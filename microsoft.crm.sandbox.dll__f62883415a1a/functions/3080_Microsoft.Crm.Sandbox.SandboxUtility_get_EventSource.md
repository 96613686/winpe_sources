# Microsoft.Crm.Sandbox.SandboxUtility::get_EventSource

- ea: `0x3080`
- end: `0x30dc`
- name: `Microsoft.Crm.Sandbox.SandboxUtility::get_EventSource`
- size: `92`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x30e0`
- `0x5680`
- `0x5d10`
- `0x7630`

## callees

- `0x14d0`
- `0x3080`

## string_xrefs

- `0x308e`: `MSCRMSandboxService`

## pseudocode

```c

```

## disassembly

```asm
0x3080  ldsfld   string Microsoft.Crm.Sandbox.SandboxUtility::_eventSource
0x3085  brtrue.s loc_30D6
0x3087  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInSandboxHostContext()
0x308c  brfalse.s loc_309A
0x308e  ldstr    aMscrmsandboxse// "MSCRMSandboxService"
0x3093  stsfld   string Microsoft.Crm.Sandbox.SandboxUtility::_eventSource
0x3098  br.s     loc_30B7
0x309a  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInSandboxWorkerContext()
0x309f  brfalse.s loc_30AD
0x30a1  ldstr    aMscrmsandboxwo// "MSCRMSandboxWorker"
0x30a6  stsfld   string Microsoft.Crm.Sandbox.SandboxUtility::_eventSource
0x30ab  br.s     loc_30B7
0x30ad  ldstr    aMscrmsandboxcl// "MSCRMSandboxClient"
0x30b2  stsfld   string Microsoft.Crm.Sandbox.SandboxUtility::_eventSource
0x30b7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x30bc  ldc.i4.s 0x26
0x30be  ldstr    aSandboxutility// "SandboxUtility.EventSource: _eventSourc"...
0x30c3  ldc.i4.1
0x30c4  newarr   [mscorlib]System.Object
0x30c9  dup
0x30ca  ldc.i4.0
0x30cb  ldsfld   string Microsoft.Crm.Sandbox.SandboxUtility::_eventSource
0x30d0  stelem.ref
0x30d1  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x30d6  ldsfld   string Microsoft.Crm.Sandbox.SandboxUtility::_eventSource
0x30db  ret
```
