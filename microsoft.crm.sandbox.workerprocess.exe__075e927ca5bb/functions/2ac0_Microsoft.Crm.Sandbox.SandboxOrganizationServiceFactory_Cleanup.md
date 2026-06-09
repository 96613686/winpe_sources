# Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::Cleanup

- ea: `0x2ac0`
- end: `0x2b2d`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::Cleanup`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2b30`

## callees

- `0x2880`
- `0x2ac0`

## string_xrefs

- `0x2ac7`: `SandboxOrganizationServiceFactory.Cleanup`

## pseudocode

```c

```

## disassembly

```asm
0x2ac0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2ac5  ldc.i4.s 0x26
0x2ac7  ldstr    aSandboxorganiz_18// "SandboxOrganizationServiceFactory.Clean"...
0x2acc  ldc.i4.0
0x2acd  newarr   [mscorlib]System.Object
0x2ad2  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2ad7  ldarg.0
0x2ad8  ldfld    object Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::_xrmServicesLock
0x2add  stloc.0
0x2ade  ldc.i4.0
0x2adf  stloc.1
0x2ae0  ldloc.0
0x2ae1  ldloca.s 1
0x2ae3  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x2ae8  ldarg.0
0x2ae9  ldc.i4.1
0x2aea  stfld    bool Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::_blocked
0x2aef  ldarg.0
0x2af0  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.SandboxOrganizationService> Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::_xrmServices
0x2af5  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.SandboxOrganizationService>::GetEnumerator()
0x2afa  stloc.2
0x2afb  br.s     loc_2B09
0x2afd  ldloca.s 2
0x2aff  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Sandbox.SandboxOrganizationService>::get_Current()
0x2b04  callvirt instance void Microsoft.Crm.Sandbox.SandboxOrganizationService::Cleanup()
0x2b09  ldloca.s 2
0x2b0b  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Sandbox.SandboxOrganizationService>::MoveNext()
0x2b10  brtrue.s loc_2AFD
0x2b12  leave.s  loc_2B2C
0x2b14  ldloca.s 2
0x2b16  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Sandbox.SandboxOrganizationService>
0x2b1c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b21  endfinally
0x2b22  ldloc.1
0x2b23  brfalse.s loc_2B2B
0x2b25  ldloc.0
0x2b26  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x2b2b  endfinally
0x2b2c  ret
```
