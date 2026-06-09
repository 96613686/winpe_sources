# Microsoft.Crm.Application.WebServices.WorkflowWebService::IsDateTimeSlug

- ea: `0x44e0`
- end: `0x44f1`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::IsDateTimeSlug`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x41d0`

## pseudocode

```c

```

## disassembly

```asm
0x44e0  ldarg.1
0x44e1  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_InnerXml()
0x44e6  ldstr    aSlugbody// "slugbody"
0x44eb  callvirt instance bool [mscorlib]System.String::Contains(string)
0x44f0  ret
```
