# Microsoft.Crm.Asynchronous.AsyncEventAdapter::get_OwningExtensionTypeCode

- ea: `0x370`
- end: `0x3a0`
- name: `Microsoft.Crm.Asynchronous.AsyncEventAdapter::get_OwningExtensionTypeCode`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x370`
- `0x2d60`
- `0x5f20`

## pseudocode

```c

```

## disassembly

```asm
0x370  ldarg.0
0x371  ldfld    class Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.AsyncEventAdapter::instance
0x376  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Asynchronous.AsyncEvent::get_OwningExtension()
0x37b  brfalse.s loc_39E
0x37d  ldarg.0
0x37e  ldfld    class Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.AsyncEventAdapter::instance
0x383  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x388  ldarg.0
0x389  ldfld    class Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.AsyncEventAdapter::instance
0x38e  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Asynchronous.AsyncEvent::get_OwningExtension()
0x393  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_type()
0x398  call     int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.SdkSerializationCommon::EntityNameToObjectTypeCode(valuetype [mscorlib]System.Guid, string)
0x39d  ret
0x39e  ldc.i4.m1
0x39f  ret
```
