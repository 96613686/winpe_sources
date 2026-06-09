# Microsoft.Crm.WebServices.ImportXmlService::UpdateImportCounter

- ea: `0xe5e0`
- end: `0xe612`
- name: `Microsoft.Crm.WebServices.ImportXmlService::UpdateImportCounter`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0xde20`

## callees

- `0xe5e0`
- `0xe620`

## pseudocode

```c

```

## disassembly

```asm
0xe5e0  ldsfld   object Microsoft.Crm.WebServices.ImportXmlService::_lockerObject
0xe5e5  stloc.0
0xe5e6  ldc.i4.0
0xe5e7  stloc.1
0xe5e8  ldloc.0
0xe5e9  ldloca.s 1
0xe5eb  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xe5f0  ldsfld   class [System]System.Collections.Generic.LinkedList`1<valuetype [mscorlib]System.DateTime> Microsoft.Crm.WebServices.ImportXmlService::_importHistory
0xe5f5  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xe5fa  callvirt instance class [System]System.Collections.Generic.LinkedListNode`1<var<u1>> class [System]System.Collections.Generic.LinkedList`1<valuetype [mscorlib]System.DateTime>::AddLast(!!T0)
0xe5ff  pop
0xe600  leave.s  loc_E60C
0xe602  ldloc.1
0xe603  brfalse.s loc_E60B
0xe605  ldloc.0
0xe606  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xe60b  endfinally
0xe60c  call     void Microsoft.Crm.WebServices.ImportXmlService::ComputeRollingAverageOfImportCounter()
0xe611  ret
```
