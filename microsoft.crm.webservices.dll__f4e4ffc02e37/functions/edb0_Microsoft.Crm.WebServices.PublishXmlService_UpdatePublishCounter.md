# Microsoft.Crm.WebServices.PublishXmlService::UpdatePublishCounter

- ea: `0xedb0`
- end: `0xede2`
- name: `Microsoft.Crm.WebServices.PublishXmlService::UpdatePublishCounter`
- size: `50`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0xeb70`
- `0xebc0`

## callees

- `0xedb0`
- `0xedf0`

## pseudocode

```c

```

## disassembly

```asm
0xedb0  ldsfld   object Microsoft.Crm.WebServices.PublishXmlService::_lockerObject
0xedb5  stloc.0
0xedb6  ldc.i4.0
0xedb7  stloc.1
0xedb8  ldloc.0
0xedb9  ldloca.s 1
0xedbb  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xedc0  ldsfld   class [System]System.Collections.Generic.LinkedList`1<valuetype [mscorlib]System.DateTime> Microsoft.Crm.WebServices.PublishXmlService::_publishHistory
0xedc5  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xedca  callvirt instance class [System]System.Collections.Generic.LinkedListNode`1<var<u1>> class [System]System.Collections.Generic.LinkedList`1<valuetype [mscorlib]System.DateTime>::AddLast(!!T0)
0xedcf  pop
0xedd0  leave.s  loc_EDDC
0xedd2  ldloc.1
0xedd3  brfalse.s loc_EDDB
0xedd5  ldloc.0
0xedd6  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xeddb  endfinally
0xeddc  call     void Microsoft.Crm.WebServices.PublishXmlService::ComputeRollingAverageOfPublishCounter()
0xede1  ret
```
