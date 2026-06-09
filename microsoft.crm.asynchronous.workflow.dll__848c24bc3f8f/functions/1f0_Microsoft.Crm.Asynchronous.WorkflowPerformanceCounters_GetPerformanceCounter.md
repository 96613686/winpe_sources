# Microsoft.Crm.Asynchronous.WorkflowPerformanceCounters::GetPerformanceCounter

- ea: `0x1f0`
- end: `0x237`
- name: `Microsoft.Crm.Asynchronous.WorkflowPerformanceCounters::GetPerformanceCounter`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x2870`

## pseudocode

```c

```

## disassembly

```asm
0x1f0  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Diagnostics.PerformanceCounter> Microsoft.Crm.Asynchronous.WorkflowPerformanceCounters::_performanceCounters
0x1f5  ldnull
0x1f6  cgt.un
0x1f8  ldstr    aWorkflowperfor_0// "WorkflowPerformanceCounters must be ini"...
0x1fd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x202  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Diagnostics.PerformanceCounter> Microsoft.Crm.Asynchronous.WorkflowPerformanceCounters::_performanceCounters
0x207  ldarg.0
0x208  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Diagnostics.PerformanceCounter>::ContainsKey(var<u1>)
0x20d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x212  ldstr    aWorkflowPerfor// "Workflow performance counter: {0} canno"...
0x217  ldc.i4.1
0x218  newarr   [mscorlib]System.Object
0x21d  dup
0x21e  ldc.i4.0
0x21f  ldarg.0
0x220  stelem.ref
0x221  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x226  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x22b  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Diagnostics.PerformanceCounter> Microsoft.Crm.Asynchronous.WorkflowPerformanceCounters::_performanceCounters
0x230  ldarg.0
0x231  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Diagnostics.PerformanceCounter>::get_Item(void)
0x236  ret
```
