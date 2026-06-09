# Microsoft.Crm.OfflineQueuePrimaryKeyPlugin::.cctor

- ea: `0x6ea0`
- end: `0x6f9b`
- name: `Microsoft.Crm.OfflineQueuePrimaryKeyPlugin::.cctor`
- size: `251`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x6eaf`: `Create`
- `0x6ef5`: `Create`
- `0x6f4f`: `Create`
- `0x6ebe`: `Update`
- `0x6f31`: `Update`
- `0x6f8b`: `Update`
- `0x6efa`: `CreateRequest`
- `0x6f36`: `UpdateRequest`
- `0x6f54`: `TargetCreateDynamic`
- `0x6f68`: `TargetScheduleDynamic`
- `0x6f7c`: `TargetScheduleDynamic`
- `0x6f90`: `TargetUpdateDynamic`

## pseudocode

```c

```

## disassembly

```asm
0x6ea0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x6ea5  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.OfflineQueuePrimaryKeyPlugin::_allowedMessageNames
0x6eaa  ldsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.OfflineQueuePrimaryKeyPlugin::_allowedMessageNames
0x6eaf  ldstr    aCreate// "Create"
0x6eb4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6eb9  ldsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.OfflineQueuePrimaryKeyPlugin::_allowedMessageNames
0x6ebe  ldstr    aUpdate// "Update"
0x6ec3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6ec8  ldsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.OfflineQueuePrimaryKeyPlugin::_allowedMessageNames
0x6ecd  ldstr    aBook// "Book"
0x6ed2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6ed7  ldsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.OfflineQueuePrimaryKeyPlugin::_allowedMessageNames
0x6edc  ldstr    aReschedule// "Reschedule"
0x6ee1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6ee6  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x6eeb  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.OfflineQueuePrimaryKeyPlugin::_requestNamesMap
0x6ef0  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.OfflineQueuePrimaryKeyPlugin::_requestNamesMap
0x6ef5  ldstr    aCreate// "Create"
0x6efa  ldstr    aCreaterequest// "CreateRequest"
0x6eff  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6f04  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.OfflineQueuePrimaryKeyPlugin::_requestNamesMap
0x6f09  ldstr    aBook// "Book"
0x6f0e  ldstr    aBookrequest// "BookRequest"
0x6f13  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6f18  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.OfflineQueuePrimaryKeyPlugin::_requestNamesMap
0x6f1d  ldstr    aReschedule// "Reschedule"
0x6f22  ldstr    aReschedulerequ// "RescheduleRequest"
0x6f27  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6f2c  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.OfflineQueuePrimaryKeyPlugin::_requestNamesMap
0x6f31  ldstr    aUpdate// "Update"
0x6f36  ldstr    aUpdaterequest// "UpdateRequest"
0x6f3b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6f40  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x6f45  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.OfflineQueuePrimaryKeyPlugin::_targetNamesMap
0x6f4a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.OfflineQueuePrimaryKeyPlugin::_targetNamesMap
0x6f4f  ldstr    aCreate// "Create"
0x6f54  ldstr    aTargetcreatedy// "TargetCreateDynamic"
0x6f59  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6f5e  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.OfflineQueuePrimaryKeyPlugin::_targetNamesMap
0x6f63  ldstr    aBook// "Book"
0x6f68  ldstr    aTargetschedule// "TargetScheduleDynamic"
0x6f6d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6f72  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.OfflineQueuePrimaryKeyPlugin::_targetNamesMap
0x6f77  ldstr    aReschedule// "Reschedule"
0x6f7c  ldstr    aTargetschedule// "TargetScheduleDynamic"
0x6f81  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6f86  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.OfflineQueuePrimaryKeyPlugin::_targetNamesMap
0x6f8b  ldstr    aUpdate// "Update"
0x6f90  ldstr    aTargetupdatedy// "TargetUpdateDynamic"
0x6f95  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6f9a  ret
```
