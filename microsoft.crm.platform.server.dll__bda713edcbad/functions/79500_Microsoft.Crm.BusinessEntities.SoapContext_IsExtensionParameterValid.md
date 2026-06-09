# Microsoft.Crm.BusinessEntities.SoapContext::IsExtensionParameterValid

- ea: `0x79500`
- end: `0x79540`
- name: `Microsoft.Crm.BusinessEntities.SoapContext::IsExtensionParameterValid`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x79540`

## callees

- `0x79500`

## string_xrefs

- `0x7951b`: `Update`
- `0x79508`: `Create`

## pseudocode

```c

```

## disassembly

```asm
0x79500  ldc.i4.1
0x79501  stloc.0
0x79502  ldarg.0
0x79503  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_RequestName()
0x79508  ldstr    aCreate// "Create"
0x7950d  ldc.i4.5
0x7950e  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x79513  brtrue.s loc_7953E
0x79515  ldarg.0
0x79516  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_RequestName()
0x7951b  ldstr    aUpdate// "Update"
0x79520  ldc.i4.5
0x79521  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x79526  brtrue.s loc_7953E
0x79528  ldarga.s 1
0x7952a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x7952f  ldstr    aSuppressduplic// "SuppressDuplicateDetection"
0x79534  ldc.i4.5
0x79535  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x7953a  brfalse.s loc_7953E
0x7953c  ldc.i4.0
0x7953d  stloc.0
0x7953e  ldloc.0
0x7953f  ret
```
