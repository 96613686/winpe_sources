# Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::get_ResourceManager

- ea: `0xa6b0`
- end: `0xa6f9`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::get_ResourceManager`
- size: `73`
- prototype: ``
- caller_count: `17`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x31910`
- `0x32f50`
- `0x492c0`
- `0x49330`
- `0x4b100`
- `0x4f610`
- `0x4f830`
- `0x4fa30`
- `0x4fbc0`
- `0x4fd60`
- `0x50230`
- `0x507f0`
- `0x75db0`
- `0x76100`
- `0x76160`
- `0x76390`
- `0x76790`

## callees

- `0xa6b0`

## string_xrefs

- `0xa6ce`: `Microsoft.Crm.Application.Components.crm.application`
- `0xa6d3`: `Microsoft.Crm.Application.Components.Strings`

## pseudocode

```c

```

## disassembly

```asm
0xa6b0  ldsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::_resourceManager
0xa6b5  brtrue.s loc_A6F3
0xa6b7  ldsfld   object Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::_lockObject
0xa6bc  stloc.0
0xa6bd  ldc.i4.0
0xa6be  stloc.1
0xa6bf  ldloc.0
0xa6c0  ldloca.s 1
0xa6c2  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xa6c7  ldsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::_resourceManager
0xa6cc  brtrue.s loc_A6E7
0xa6ce  ldstr    aMicrosoftCrmAp// "Microsoft.Crm.Application.Components.cr"...
0xa6d3  ldstr    aMicrosoftCrmAp_0// "Microsoft.Crm.Application.Components.St"...
0xa6d8  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0xa6dd  newobj   instance void [mscorlib]System.Resources.ResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0xa6e2  stsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::_resourceManager
0xa6e7  leave.s  loc_A6F3
0xa6e9  ldloc.1
0xa6ea  brfalse.s loc_A6F2
0xa6ec  ldloc.0
0xa6ed  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xa6f2  endfinally
0xa6f3  ldsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::_resourceManager
0xa6f8  ret
```
