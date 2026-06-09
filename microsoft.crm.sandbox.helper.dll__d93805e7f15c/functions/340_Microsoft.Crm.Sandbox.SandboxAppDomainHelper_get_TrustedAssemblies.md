# Microsoft.Crm.Sandbox.SandboxAppDomainHelper::get_TrustedAssemblies

- ea: `0x340`
- end: `0x399`
- name: `Microsoft.Crm.Sandbox.SandboxAppDomainHelper::get_TrustedAssemblies`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1f0`
- `0x610`

## callees

- `0x340`

## pseudocode

```c

```

## disassembly

```asm
0x340  ldsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_trustedAssemblies
0x345  brtrue.s loc_393
0x347  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x34c  dup
0x34d  ldstr    aMicrosoftCrmSa// "Microsoft.Crm.Sandbox"
0x352  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x357  dup
0x358  ldstr    aMicrosoftXrmSd// "Microsoft.Xrm.Sdk"
0x35d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x362  dup
0x363  ldstr    aMicrosoftCrmSd// "Microsoft.Crm.Sdk"
0x368  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x36d  dup
0x36e  ldstr    aMicrosoftCrmSd_0// "Microsoft.Crm.Sdk.Proxy"
0x373  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x378  dup
0x379  ldstr    aMicrosoftXrmSd_0// "Microsoft.Xrm.Sdk.Workflow"
0x37e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x383  dup
0x384  ldstr    aMicrosoftXrmSd_1// "Microsoft.Xrm.Sdk.Data"
0x389  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x38e  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_trustedAssemblies
0x393  ldsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_trustedAssemblies
0x398  ret
```
