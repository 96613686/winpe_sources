# Microsoft.Crm.Platform.SolutionAwareComponents.BaseComponentInstanceUpgraderFactory::.cctor

- ea: `0x34b20`
- end: `0x34b63`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.BaseComponentInstanceUpgraderFactory::.cctor`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## string_xrefs

- `0x34b34`: `Creating instance of CrmSecurityExtensionFactory`
- `0x34b49`: `Microsoft.Crm.ObjectModel.ComponentInstanceUpgraderFactory`

## pseudocode

```c

```

## disassembly

```asm
0x34b20  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x34b25  ldc.i4.s 0x14
0x34b27  ldstr    a0// "{0}"
0x34b2c  ldc.i4.1
0x34b2d  newarr   [mscorlib]System.Object
0x34b32  dup
0x34b33  ldc.i4.0
0x34b34  ldstr    aCreatingInstan_1// "Creating instance of CrmSecurityExtensi"...
0x34b39  stelem.ref
0x34b3a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x34b3f  ldstr    aMicrosoftCrmOb_0// "Microsoft.Crm.ObjectModel"
0x34b44  call     string [Microsoft.Crm.Core]Microsoft.Crm.ProductVersion::GetFullyQualifiedTypeName(string)
0x34b49  ldstr    aMicrosoftCrmOb_1// "Microsoft.Crm.ObjectModel.ComponentInst"...
0x34b4e  call     class [mscorlib]System.Runtime.Remoting.ObjectHandle [mscorlib]System.Activator::CreateInstance(string, string)
0x34b53  callvirt instance object [mscorlib]System.Runtime.Remoting.ObjectHandle::Unwrap()
0x34b58  castclass Microsoft.Crm.Platform.SolutionAwareComponents.IComponentInstanceUpgraderFactory
0x34b5d  stsfld   class Microsoft.Crm.Platform.SolutionAwareComponents.IComponentInstanceUpgraderFactory Microsoft.Crm.Platform.SolutionAwareComponents.BaseComponentInstanceUpgraderFactory::_instance
0x34b62  ret
```
