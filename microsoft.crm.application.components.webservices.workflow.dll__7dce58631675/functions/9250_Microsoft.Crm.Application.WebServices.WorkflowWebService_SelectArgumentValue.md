# Microsoft.Crm.Application.WebServices.WorkflowWebService::SelectArgumentValue

- ea: `0x9250`
- end: `0x9276`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::SelectArgumentValue`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x35d0`

## callees

- `0x9250`

## pseudocode

```c

```

## disassembly

```asm
0x9250  ldarg.1
0x9251  brfalse.s loc_925B
0x9253  ldarg.2
0x9254  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9259  brfalse.s loc_925D
0x925b  ldnull
0x925c  ret
0x925d  ldarg.1
0x925e  ldarg.2
0x925f  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x9264  stloc.0
0x9265  ldloc.0
0x9266  brtrue.s loc_9274
0x9268  ldarg.1
0x9269  ldstr    aArgumentvalued_1// "ArgumentValueData"
0x926e  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::SelectSingleNode(string)
0x9273  stloc.0
0x9274  ldloc.0
0x9275  ret
```
