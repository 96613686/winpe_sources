# Microsoft.Crm.Sandbox.SandboxAppDomainManager::RecycleAppDomain

- ea: `0x1a30`
- end: `0x1ae1`
- name: `Microsoft.Crm.Sandbox.SandboxAppDomainManager::RecycleAppDomain`
- size: `177`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x3aa0`
- `0x4170`

## callees

- `0xeb0`
- `0x18e0`
- `0x1a30`
- `0x39f0`

## string_xrefs

- `0x1abd`: `Appdomain was recycle in the midle of the operation by another thread.`

## pseudocode

```c

```

## disassembly

```asm
0x1a30  ldnull
0x1a31  stloc.0
0x1a32  ldsfld   class Microsoft.Crm.Sandbox.SandboxAppDomain Microsoft.Crm.Sandbox.SandboxAppDomainManager::_nextAppDomain
0x1a37  brtrue   loc_1ACE
0x1a3c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1a41  ldsfld   class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.SandboxAppDomainManager::_nextAppDomainLock
0x1a46  ldsflda  class Microsoft.Crm.Sandbox.SandboxAppDomain Microsoft.Crm.Sandbox.SandboxAppDomainManager::_nextAppDomain
0x1a4b  call     class Microsoft.Crm.Sandbox.SandboxAppDomain Microsoft.Crm.Sandbox.SandboxAppDomainManager::GetOrInitializeAppDomain(valuetype [mscorlib]System.Guid organizationId, class [System.Core]System.Threading.ReaderWriterLockSlim appDomainLock, class Microsoft.Crm.Sandbox.SandboxAppDomain& appDomain)
0x1a50  pop
0x1a51  ldsfld   class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.SandboxAppDomainManager::_appDomainLock
0x1a56  callvirt instance void [System.Core]System.Threading.ReaderWriterLockSlim::EnterWriteLock()
0x1a5b  ldsfld   class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.SandboxAppDomainManager::_nextAppDomainLock
0x1a60  callvirt instance void [System.Core]System.Threading.ReaderWriterLockSlim::EnterWriteLock()
0x1a65  ldsfld   class Microsoft.Crm.Sandbox.SandboxAppDomain Microsoft.Crm.Sandbox.SandboxAppDomainManager::_nextAppDomain
0x1a6a  brfalse.s loc_1A82
0x1a6c  ldsfld   class Microsoft.Crm.Sandbox.SandboxAppDomain Microsoft.Crm.Sandbox.SandboxAppDomainManager::_singleAppDomain
0x1a71  stloc.0
0x1a72  ldsfld   class Microsoft.Crm.Sandbox.SandboxAppDomain Microsoft.Crm.Sandbox.SandboxAppDomainManager::_nextAppDomain
0x1a77  stsfld   class Microsoft.Crm.Sandbox.SandboxAppDomain Microsoft.Crm.Sandbox.SandboxAppDomainManager::_singleAppDomain
0x1a7c  ldnull
0x1a7d  stsfld   class Microsoft.Crm.Sandbox.SandboxAppDomain Microsoft.Crm.Sandbox.SandboxAppDomainManager::_nextAppDomain
0x1a82  leave.s  loc_1A99
0x1a84  ldsfld   class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.SandboxAppDomainManager::_appDomainLock
0x1a89  callvirt instance void [System.Core]System.Threading.ReaderWriterLockSlim::ExitWriteLock()
0x1a8e  ldsfld   class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.SandboxAppDomainManager::_nextAppDomainLock
0x1a93  callvirt instance void [System.Core]System.Threading.ReaderWriterLockSlim::ExitWriteLock()
0x1a98  endfinally
0x1a99  ldloc.0
0x1a9a  brfalse.s loc_1ABB
0x1a9c  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration Microsoft.Crm.Sandbox.SandboxWorker::get_WorkerConfiguration()
0x1aa1  ldc.i4.5
0x1aa2  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerProperty)
0x1aa7  conv.r8
0x1aa8  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x1aad  call     void [mscorlib]System.Threading.Thread::Sleep(valuetype [mscorlib]System.TimeSpan)
0x1ab2  leave.s  loc_1AE0
0x1ab4  ldloc.0
0x1ab5  callvirt instance void Microsoft.Crm.Sandbox.SandboxAppDomain::Dispose()
0x1aba  endfinally
0x1abb  ldc.i4.s 0x26
0x1abd  ldstr    aAppdomainWasRe// "Appdomain was recycle in the midle of t"...
0x1ac2  ldc.i4.0
0x1ac3  newarr   [mscorlib]System.Object
0x1ac8  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1acd  ret
0x1ace  ldc.i4.s 0x26
0x1ad0  ldstr    aSkippingAppdom// "Skipping appDomain recycle"
0x1ad5  ldc.i4.0
0x1ad6  newarr   [mscorlib]System.Object
0x1adb  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1ae0  ret
```
