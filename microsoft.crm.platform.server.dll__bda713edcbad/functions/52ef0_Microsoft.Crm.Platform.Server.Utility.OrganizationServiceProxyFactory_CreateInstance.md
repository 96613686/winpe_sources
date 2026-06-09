# Microsoft.Crm.Platform.Server.Utility.OrganizationServiceProxyFactory::CreateInstance

- ea: `0x52ef0`
- end: `0x52f2a`
- name: `Microsoft.Crm.Platform.Server.Utility.OrganizationServiceProxyFactory::CreateInstance`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x8a120`
- `0x8a140`
- `0x8a150`

## string_xrefs

- `0x52efa`: `Microsoft.Crm.Extensibility.InprocessServiceFactory`
- `0x52f0b`: `CreateInstance`

## pseudocode

```c

```

## disassembly

```asm
0x52ef0  ldstr    aMicrosoftCrmEx// "Microsoft.Crm.Extensibility"
0x52ef5  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0x52efa  ldstr    aMicrosoftCrmEx_0// "Microsoft.Crm.Extensibility.InprocessSe"...
0x52eff  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x52f04  dup
0x52f05  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x52f0a  stloc.0
0x52f0b  ldstr    aCreateinstance// "CreateInstance"
0x52f10  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string)
0x52f15  stloc.1
0x52f16  newobj   instance void InprocessServiceFactoryCache::.ctor()
0x52f1b  dup
0x52f1c  ldloc.1
0x52f1d  callvirt instance void InprocessServiceFactoryCache::set_CreateOrgProxyMethod(class [mscorlib]System.Reflection.MethodInfo value)
0x52f22  dup
0x52f23  ldloc.0
0x52f24  callvirt instance void InprocessServiceFactoryCache::set_Instance(object value)
0x52f29  ret
```
