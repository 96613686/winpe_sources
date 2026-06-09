# Microsoft.Crm.StorageNotificationUtility::get_ResourceManager

- ea: `0x247e0`
- end: `0x24829`
- name: `Microsoft.Crm.StorageNotificationUtility::get_ResourceManager`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x24ca0`

## callees

- `0x247e0`

## string_xrefs

- `0x247fe`: `Microsoft.Crm.Application.Components.crm.application`
- `0x24803`: `Microsoft.Crm.Application.Components.Strings`

## pseudocode

```c

```

## disassembly

```asm
0x247e0  ldsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.StorageNotificationUtility::_resourceManager
0x247e5  brtrue.s loc_24823
0x247e7  ldsfld   object Microsoft.Crm.StorageNotificationUtility::_lockObject
0x247ec  stloc.0
0x247ed  ldc.i4.0
0x247ee  stloc.1
0x247ef  ldloc.0
0x247f0  ldloca.s 1
0x247f2  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x247f7  ldsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.StorageNotificationUtility::_resourceManager
0x247fc  brtrue.s loc_24817
0x247fe  ldstr    aMicrosoftCrmAp// "Microsoft.Crm.Application.Components.cr"...
0x24803  ldstr    aMicrosoftCrmAp_0// "Microsoft.Crm.Application.Components.St"...
0x24808  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0x2480d  newobj   instance void [mscorlib]System.Resources.ResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0x24812  stsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.StorageNotificationUtility::_resourceManager
0x24817  leave.s  loc_24823
0x24819  ldloc.1
0x2481a  brfalse.s loc_24822
0x2481c  ldloc.0
0x2481d  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x24822  endfinally
0x24823  ldsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.StorageNotificationUtility::_resourceManager
0x24828  ret
```
