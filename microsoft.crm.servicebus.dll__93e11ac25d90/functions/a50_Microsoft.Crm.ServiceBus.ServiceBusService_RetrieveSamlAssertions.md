# Microsoft.Crm.ServiceBus.ServiceBusService::RetrieveSamlAssertions

- ea: `0xa50`
- end: `0xacb`
- name: `Microsoft.Crm.ServiceBus.ServiceBusService::RetrieveSamlAssertions`
- size: `123`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xa50`
- `0x1970`
- `0x26b0`

## string_xrefs

- `0xa56`: `internalService`

## pseudocode

```c

```

## disassembly

```asm
0xa50  ldarg.0
0xa51  ldfld    class Microsoft.Crm.ServiceBus.IInternalServiceEndpointService Microsoft.Crm.ServiceBus.ServiceBusService::internalService
0xa56  ldstr    aInternalservic// "internalService"
0xa5b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xa60  ldnull
0xa61  stloc.0
0xa62  ldarg.2
0xa63  brfalse.s loc_AB1
0xa65  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0xa6a  stloc.0
0xa6b  ldarg.2
0xa6c  callvirt instance class [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection [System]System.Collections.Specialized.NameObjectCollectionBase::get_Keys()
0xa71  callvirt instance class [mscorlib]System.Collections.IEnumerator [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection::GetEnumerator()
0xa76  stloc.2
0xa77  br.s     loc_A93
0xa79  ldloc.2
0xa7a  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa7f  castclass [mscorlib]System.String
0xa84  stloc.3
0xa85  ldloc.0
0xa86  ldloc.3
0xa87  ldarg.2
0xa88  ldloc.3
0xa89  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xa8e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa93  ldloc.2
0xa94  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa99  brtrue.s loc_A79
0xa9b  leave.s  loc_AB1
0xa9d  ldloc.2
0xa9e  isinst   [mscorlib]System.IDisposable
0xaa3  stloc.s  4
0xaa5  ldloc.s  4
0xaa7  brfalse.s loc_AB0
0xaa9  ldloc.s  4
0xaab  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xab0  endfinally
0xab1  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetCallingAssembly()
0xab6  stloc.1
0xab7  ldarg.0
0xab8  ldfld    class Microsoft.Crm.ServiceBus.IInternalAuthenticationTokenService Microsoft.Crm.ServiceBus.ServiceBusService::internalAuthService
0xabd  ldloc.1
0xabe  call     string Microsoft.Crm.ServiceBus.ServiceBusUtility::RetrieveAssemblyName(class [mscorlib]System.Reflection.Assembly assembly)
0xac3  ldarg.1
0xac4  ldloc.0
0xac5  callvirt instance string Microsoft.Crm.ServiceBus.IInternalAuthenticationTokenService::RetrieveClaimAssertions(string assemblyName, class [System]System.Uri scope, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> claimCollection)
0xaca  ret
```
