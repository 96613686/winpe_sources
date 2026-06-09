# Microsoft.Crm.Sdk.BuildTimeServiceDescriptionFactory::Create

- ea: `0x8620`
- end: `0x8665`
- name: `Microsoft.Crm.Sdk.BuildTimeServiceDescriptionFactory::Create`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xa440`

## callees

- `0x8620`
- `0x8850`
- `0x9f90`
- `0xa020`

## pseudocode

```c

```

## disassembly

```asm
0x8620  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Sdk.ServiceDescription> Microsoft.Crm.Sdk.BuildTimeServiceDescriptionFactory::_sdCache
0x8625  stloc.0
0x8626  ldc.i4.0
0x8627  stloc.1
0x8628  ldloc.0
0x8629  ldloca.s 1
0x862b  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x8630  ldarg.1
0x8631  newobj   instance void Microsoft.Crm.Sdk.SdkMessagesLoader::.ctor(string targetNamespace)
0x8636  ldarg.2
0x8637  callvirt instance class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessages Microsoft.Crm.Sdk.SdkMessagesLoader::GetSdkMessages(string xml)
0x863c  stloc.2
0x863d  ldarg.0
0x863e  ldarg.1
0x863f  ldloc.2
0x8640  ldarg.3
0x8641  newobj   instance void Microsoft.Crm.Sdk.ServiceDescription::.ctor(valuetype [mscorlib]System.Guid organizationId, string targetNamespace, class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessages sdkMessages, class Microsoft.Crm.Sdk.EntityMetadatas entityMetadatas)
0x8646  stloc.3
0x8647  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Sdk.ServiceDescription> Microsoft.Crm.Sdk.BuildTimeServiceDescriptionFactory::_sdCache
0x864c  ldarg.1
0x864d  ldloc.3
0x864e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Sdk.ServiceDescription>::set_Item(var<u1>, !!T0)
0x8653  ldloc.3
0x8654  stloc.s  4
0x8656  leave.s  loc_8662
0x8658  ldloc.1
0x8659  brfalse.s loc_8661
0x865b  ldloc.0
0x865c  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x8661  endfinally
0x8662  ldloc.s  4
0x8664  ret
```
