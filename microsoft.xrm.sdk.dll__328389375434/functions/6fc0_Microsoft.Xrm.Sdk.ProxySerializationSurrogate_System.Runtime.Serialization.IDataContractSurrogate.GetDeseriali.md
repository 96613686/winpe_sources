# Microsoft.Xrm.Sdk.ProxySerializationSurrogate::System.Runtime.Serialization.IDataContractSurrogate.GetDeserializedObject

- ea: `0x6fc0`
- end: `0x7068`
- name: `Microsoft.Xrm.Sdk.ProxySerializationSurrogate::System.Runtime.Serialization.IDataContractSurrogate.GetDeserializedObject`
- size: `168`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3750`
- `0x3760`
- `0x3790`
- `0x37b0`
- `0x3b90`
- `0x3f20`
- `0x4e30`
- `0x4e80`
- `0x6fc0`

## pseudocode

```c

```

## disassembly

```asm
0x6fc0  ldarg.0
0x6fc1  ldfld    class [mscorlib]System.Reflection.Assembly Microsoft.Xrm.Sdk.ProxySerializationSurrogate::_proxyTypesAssembly
0x6fc6  ldnull
0x6fc7  call     bool [mscorlib]System.Reflection.Assembly::op_Inequality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0x6fcc  stloc.0
0x6fcd  ldarg.1
0x6fce  isinst   Microsoft.Xrm.Sdk.OrganizationResponse
0x6fd3  stloc.1
0x6fd4  ldloc.1
0x6fd5  brfalse.s loc_701E
0x6fd7  ldloc.0
0x6fd8  call     class Microsoft.Xrm.Sdk.KnownProxyTypesProvider Microsoft.Xrm.Sdk.KnownProxyTypesProvider::GetInstance(bool supportIndividualAssemblies)
0x6fdd  ldloc.1
0x6fde  callvirt instance string Microsoft.Xrm.Sdk.OrganizationResponse::get_ResponseName()
0x6fe3  ldarg.0
0x6fe4  ldfld    class [mscorlib]System.Reflection.Assembly Microsoft.Xrm.Sdk.ProxySerializationSurrogate::_proxyTypesAssembly
0x6fe9  callvirt instance class [mscorlib]System.Type Microsoft.Xrm.Sdk.KnownProxyTypesProvider::GetTypeForName(string name, class [mscorlib]System.Reflection.Assembly proxyTypesAssembly)
0x6fee  stloc.3
0x6fef  ldloc.3
0x6ff0  ldnull
0x6ff1  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6ff6  brfalse.s loc_6FFA
0x6ff8  ldarg.1
0x6ff9  ret
0x6ffa  ldloc.3
0x6ffb  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x7000  castclass Microsoft.Xrm.Sdk.OrganizationResponse
0x7005  dup
0x7006  ldloc.1
0x7007  callvirt instance string Microsoft.Xrm.Sdk.OrganizationResponse::get_ResponseName()
0x700c  callvirt instance void Microsoft.Xrm.Sdk.OrganizationResponse::set_ResponseName(string value)
0x7011  dup
0x7012  ldloc.1
0x7013  callvirt instance class Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x7018  callvirt instance void Microsoft.Xrm.Sdk.OrganizationResponse::set_Results(class Microsoft.Xrm.Sdk.ParameterCollection value)
0x701d  ret
0x701e  ldarg.1
0x701f  isinst   Microsoft.Xrm.Sdk.Entity
0x7024  stloc.2
0x7025  ldloc.2
0x7026  brfalse.s loc_7066
0x7028  ldloc.0
0x7029  call     class Microsoft.Xrm.Sdk.KnownProxyTypesProvider Microsoft.Xrm.Sdk.KnownProxyTypesProvider::GetInstance(bool supportIndividualAssemblies)
0x702e  ldloc.2
0x702f  callvirt instance string Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x7034  ldarg.0
0x7035  ldfld    class [mscorlib]System.Reflection.Assembly Microsoft.Xrm.Sdk.ProxySerializationSurrogate::_proxyTypesAssembly
0x703a  callvirt instance class [mscorlib]System.Type Microsoft.Xrm.Sdk.KnownProxyTypesProvider::GetTypeForName(string name, class [mscorlib]System.Reflection.Assembly proxyTypesAssembly)
0x703f  stloc.s  4
0x7041  ldloc.s  4
0x7043  ldnull
0x7044  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x7049  brfalse.s loc_704D
0x704b  ldarg.1
0x704c  ret
0x704d  ldloc.s  4
0x704f  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x7054  castclass Microsoft.Xrm.Sdk.Entity
0x7059  stloc.s  5
0x705b  ldloc.2
0x705c  ldloc.s  5
0x705e  callvirt instance void Microsoft.Xrm.Sdk.Entity::ShallowCopyTo(class Microsoft.Xrm.Sdk.Entity target)
0x7063  ldloc.s  5
0x7065  ret
0x7066  ldarg.1
0x7067  ret
```
