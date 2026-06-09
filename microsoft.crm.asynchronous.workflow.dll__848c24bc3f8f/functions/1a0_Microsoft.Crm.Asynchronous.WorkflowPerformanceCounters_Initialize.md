# Microsoft.Crm.Asynchronous.WorkflowPerformanceCounters::Initialize

- ea: `0x1a0`
- end: `0x1e2`
- name: `Microsoft.Crm.Asynchronous.WorkflowPerformanceCounters::Initialize`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xa0`

## string_xrefs

- `0x1c1`: `Total Workflow state writes`
- `0x1cc`: `Total Workflow state writes`

## pseudocode

```c

```

## disassembly

```asm
0x1a0  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Diagnostics.PerformanceCounter> Microsoft.Crm.Asynchronous.WorkflowPerformanceCounters::_performanceCounters
0x1a5  ldnull
0x1a6  ceq
0x1a8  ldstr    aWorkflowperfor// "WorkflowPerformanceCounters should not "...
0x1ad  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1b2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Diagnostics.PerformanceCounter>::.ctor()
0x1b7  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Diagnostics.PerformanceCounter> Microsoft.Crm.Asynchronous.WorkflowPerformanceCounters::_performanceCounters
0x1bc  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Diagnostics.PerformanceCounter> Microsoft.Crm.Asynchronous.WorkflowPerformanceCounters::_performanceCounters
0x1c1  ldstr    aTotalWorkflowS// "Total Workflow state writes"
0x1c6  ldarg.0
0x1c7  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncServicePerformanceCounters [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncService::get_PerformanceCounters()
0x1cc  ldstr    aTotalWorkflowS// "Total Workflow state writes"
0x1d1  ldarg.0
0x1d2  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncService::get_ServiceName()
0x1d7  callvirt instance class [System]System.Diagnostics.PerformanceCounter [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncServicePerformanceCounters::InitializeCounter(string, string)
0x1dc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Diagnostics.PerformanceCounter>::Add(var<u1>, !!T0)
0x1e1  ret
```
