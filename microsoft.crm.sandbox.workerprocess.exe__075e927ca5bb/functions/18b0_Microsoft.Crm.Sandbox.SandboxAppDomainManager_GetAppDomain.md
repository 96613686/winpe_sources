# Microsoft.Crm.Sandbox.SandboxAppDomainManager::GetAppDomain

- ea: `0x18b0`
- end: `0x18d9`
- name: `Microsoft.Crm.Sandbox.SandboxAppDomainManager::GetAppDomain`
- size: `41`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x32d0`
- `0x3470`

## callees

- `0x18b0`
- `0x18e0`

## pseudocode

```c

```

## disassembly

```asm
0x18b0  ldsfld   bool Microsoft.Crm.Sandbox.SandboxAppDomainManager::WarmUpInProgress
0x18b5  brfalse.s loc_18C8
0x18b7  ldarg.0
0x18b8  ldsfld   class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.SandboxAppDomainManager::_nextAppDomainLock
0x18bd  ldsflda  class Microsoft.Crm.Sandbox.SandboxAppDomain Microsoft.Crm.Sandbox.SandboxAppDomainManager::_nextAppDomain
0x18c2  call     class Microsoft.Crm.Sandbox.SandboxAppDomain Microsoft.Crm.Sandbox.SandboxAppDomainManager::GetOrInitializeAppDomain(valuetype [mscorlib]System.Guid organizationId, class [System.Core]System.Threading.ReaderWriterLockSlim appDomainLock, class Microsoft.Crm.Sandbox.SandboxAppDomain& appDomain)
0x18c7  ret
0x18c8  ldarg.0
0x18c9  ldsfld   class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.SandboxAppDomainManager::_appDomainLock
0x18ce  ldsflda  class Microsoft.Crm.Sandbox.SandboxAppDomain Microsoft.Crm.Sandbox.SandboxAppDomainManager::_singleAppDomain
0x18d3  call     class Microsoft.Crm.Sandbox.SandboxAppDomain Microsoft.Crm.Sandbox.SandboxAppDomainManager::GetOrInitializeAppDomain(valuetype [mscorlib]System.Guid organizationId, class [System.Core]System.Threading.ReaderWriterLockSlim appDomainLock, class Microsoft.Crm.Sandbox.SandboxAppDomain& appDomain)
0x18d8  ret
```
