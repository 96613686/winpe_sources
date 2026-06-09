# Microsoft.Crm.Sdk.InProcessCrmService::get_RequestSerializer

- ea: `0x3430`
- end: `0x347b`
- name: `Microsoft.Crm.Sdk.InProcessCrmService::get_RequestSerializer`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x30f0`

## callees

- `0x3430`

## pseudocode

```c

```

## disassembly

```asm
0x3430  ldsfld   class [System.Xml]System.Xml.Serialization.XmlSerializer Microsoft.Crm.Sdk.InProcessCrmService::_requestSerializer
0x3435  brtrue.s loc_3475
0x3437  ldsfld   object Microsoft.Crm.Sdk.InProcessCrmService::_lockSerializer
0x343c  stloc.0
0x343d  ldc.i4.0
0x343e  stloc.1
0x343f  ldloc.0
0x3440  ldloca.s 1
0x3442  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x3447  ldsfld   class [System.Xml]System.Xml.Serialization.XmlSerializer Microsoft.Crm.Sdk.InProcessCrmService::_requestSerializer
0x344c  brtrue.s loc_3469
0x344e  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SerializerCache [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SerializerCache::get_Instance()
0x3453  ldtoken  Microsoft.Crm.Sdk.Crm2007.Request
0x3458  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x345d  ldnull
0x345e  ldnull
0x345f  callvirt instance class [System.Xml]System.Xml.Serialization.XmlSerializer [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SerializerCache::GetSerializer(class [mscorlib]System.Type, string, string)
0x3464  stsfld   class [System.Xml]System.Xml.Serialization.XmlSerializer Microsoft.Crm.Sdk.InProcessCrmService::_requestSerializer
0x3469  leave.s  loc_3475
0x346b  ldloc.1
0x346c  brfalse.s loc_3474
0x346e  ldloc.0
0x346f  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x3474  endfinally
0x3475  ldsfld   class [System.Xml]System.Xml.Serialization.XmlSerializer Microsoft.Crm.Sdk.InProcessCrmService::_requestSerializer
0x347a  ret
```
