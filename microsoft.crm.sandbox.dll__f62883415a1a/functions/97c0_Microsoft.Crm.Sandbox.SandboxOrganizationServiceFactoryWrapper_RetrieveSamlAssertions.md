# Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactoryWrapper::RetrieveSamlAssertions

- ea: `0x97c0`
- end: `0x9838`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactoryWrapper::RetrieveSamlAssertions`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ea0`
- `0x1ec0`
- `0x97c0`

## pseudocode

```c

```

## disassembly

```asm
0x97c0  ldarg.0
0x97c1  ldfld    class Microsoft.Crm.Sandbox.ISandboxOrganizationServiceFactory Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactoryWrapper::_fullTrustFactory
0x97c6  ldloca.s 2
0x97c8  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x97ce  ldloc.2
0x97cf  callvirt instance class Microsoft.Crm.Sandbox.ISandboxOrganizationService Microsoft.Crm.Sandbox.ISandboxOrganizationServiceFactory::CreateOrganizationService(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> userId)
0x97d4  stloc.0
0x97d5  ldnull
0x97d6  stloc.1
0x97d7  ldarg.2
0x97d8  brfalse.s loc_9829
0x97da  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x97df  stloc.1
0x97e0  ldarg.2
0x97e1  callvirt instance class [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection [System]System.Collections.Specialized.NameObjectCollectionBase::get_Keys()
0x97e6  callvirt instance class [mscorlib]System.Collections.IEnumerator [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection::GetEnumerator()
0x97eb  stloc.3
0x97ec  br.s     loc_980B
0x97ee  ldloc.3
0x97ef  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x97f4  castclass [mscorlib]System.String
0x97f9  stloc.s  4
0x97fb  ldloc.1
0x97fc  ldloc.s  4
0x97fe  ldarg.2
0x97ff  ldloc.s  4
0x9801  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x9806  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x980b  ldloc.3
0x980c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9811  brtrue.s loc_97EE
0x9813  leave.s  loc_9829
0x9815  ldloc.3
0x9816  isinst   [mscorlib]System.IDisposable
0x981b  stloc.s  5
0x981d  ldloc.s  5
0x981f  brfalse.s loc_9828
0x9821  ldloc.s  5
0x9823  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9828  endfinally
0x9829  ldloc.0
0x982a  ldarg.1
0x982b  ldloc.1
0x982c  ldarg.0
0x982d  ldfld    object Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactoryWrapper::_traceSettings
0x9832  callvirt instance string Microsoft.Crm.Sandbox.ISandboxOrganizationService::RetrieveClaimAssertions(class [System]System.Uri scope, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> claimCollection, object traceSettings)
0x9837  ret
```
