# Microsoft.Crm.Asynchronous.AsyncHandlerFactory::CreateHandlerGroups

- ea: `0x860`
- end: `0x90b`
- name: `Microsoft.Crm.Asynchronous.AsyncHandlerFactory::CreateHandlerGroups`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xe20`

## callees

- `0x860`
- `0x910`
- `0xc40`

## pseudocode

```c

```

## disassembly

```asm
0x860  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup>::.ctor()
0x865  stloc.0
0x866  ldarg.0
0x867  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceContext Microsoft.Crm.Asynchronous.AsyncService::get_Context()
0x86c  stloc.1
0x86d  ldloc.1
0x86e  switch   loc_8B9, loc_885, loc_8B9, loc_8A7
0x883  br.s     loc_8B9
0x885  ldloc.0
0x886  ldstr    aSystem// "System"
0x88b  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup Microsoft.Crm.Asynchronous.AsyncHandlerFactory::CreateHandlerGroup(string name)
0x890  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup>::Add(var<u1>)
0x895  ldloc.0
0x896  ldstr    aDatamanagement// "DataManagement"
0x89b  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup Microsoft.Crm.Asynchronous.AsyncHandlerFactory::CreateHandlerGroup(string name)
0x8a0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup>::Add(var<u1>)
0x8a5  br.s     loc_909
0x8a7  ldloc.0
0x8a8  ldstr    aEmailconnector// "EmailConnector"
0x8ad  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup Microsoft.Crm.Asynchronous.AsyncHandlerFactory::CreateHandlerGroup(string name)
0x8b2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup>::Add(var<u1>)
0x8b7  br.s     loc_909
0x8b9  ldloc.0
0x8ba  ldstr    aDatamanagement// "DataManagement"
0x8bf  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup Microsoft.Crm.Asynchronous.AsyncHandlerFactory::CreateHandlerGroup(string name)
0x8c4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup>::Add(var<u1>)
0x8c9  ldloc.0
0x8ca  ldstr    aSystem// "System"
0x8cf  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup Microsoft.Crm.Asynchronous.AsyncHandlerFactory::CreateHandlerGroup(string name)
0x8d4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup>::Add(var<u1>)
0x8d9  ldloc.0
0x8da  ldstr    aWorkflow// "Workflow"
0x8df  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup Microsoft.Crm.Asynchronous.AsyncHandlerFactory::CreateHandlerGroup(string name)
0x8e4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup>::Add(var<u1>)
0x8e9  ldloc.0
0x8ea  ldstr    aBusinessmanage// "BusinessManagement"
0x8ef  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup Microsoft.Crm.Asynchronous.AsyncHandlerFactory::CreateHandlerGroup(string name)
0x8f4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup>::Add(var<u1>)
0x8f9  ldloc.0
0x8fa  ldstr    aEmailconnector// "EmailConnector"
0x8ff  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup Microsoft.Crm.Asynchronous.AsyncHandlerFactory::CreateHandlerGroup(string name)
0x904  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup>::Add(var<u1>)
0x909  ldloc.0
0x90a  ret
```
