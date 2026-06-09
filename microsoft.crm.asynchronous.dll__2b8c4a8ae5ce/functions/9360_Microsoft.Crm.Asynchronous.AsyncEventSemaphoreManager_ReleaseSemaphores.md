# Microsoft.Crm.Asynchronous.AsyncEventSemaphoreManager::ReleaseSemaphores

- ea: `0x9360`
- end: `0x93c4`
- name: `Microsoft.Crm.Asynchronous.AsyncEventSemaphoreManager::ReleaseSemaphores`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x9360`
- `0x93d0`
- `0x9480`
- `0x9490`
- `0x94a0`
- `0x94b0`
- `0x94c0`
- `0x94d0`

## string_xrefs

- `0x938f`: `OrgThreadCountSemaphore`

## pseudocode

```c

```

## disassembly

```asm
0x9360  ldarg.0
0x9361  call     instance class [mscorlib]System.Threading.SemaphoreSlim Microsoft.Crm.Asynchronous.AsyncEventSemaphoreManager::get_LockedDownOrgsSemaphore()
0x9366  brfalse.s loc_9381
0x9368  ldarg.0
0x9369  call     instance class [mscorlib]System.Threading.SemaphoreSlim Microsoft.Crm.Asynchronous.AsyncEventSemaphoreManager::get_LockedDownOrgsSemaphore()
0x936e  ldstr    aLockeddownorgs// "LockedDownOrgsSemaphore"
0x9373  ldc.i4.1
0x9374  call     bool Microsoft.Crm.Asynchronous.AsyncEventSemaphoreManager::SafeReleaseSemaphore(class [mscorlib]System.Threading.SemaphoreSlim semaphore, string semaphoreName, [opt] int32 count)
0x9379  pop
0x937a  ldarg.0
0x937b  ldnull
0x937c  call     instance void Microsoft.Crm.Asynchronous.AsyncEventSemaphoreManager::set_LockedDownOrgsSemaphore(class [mscorlib]System.Threading.SemaphoreSlim value)
0x9381  ldarg.0
0x9382  call     instance class [mscorlib]System.Threading.SemaphoreSlim Microsoft.Crm.Asynchronous.AsyncEventSemaphoreManager::get_OrgThreadCountSemaphore()
0x9387  brfalse.s loc_93A2
0x9389  ldarg.0
0x938a  call     instance class [mscorlib]System.Threading.SemaphoreSlim Microsoft.Crm.Asynchronous.AsyncEventSemaphoreManager::get_OrgThreadCountSemaphore()
0x938f  ldstr    aOrgthreadcount// "OrgThreadCountSemaphore"
0x9394  ldc.i4.1
0x9395  call     bool Microsoft.Crm.Asynchronous.AsyncEventSemaphoreManager::SafeReleaseSemaphore(class [mscorlib]System.Threading.SemaphoreSlim semaphore, string semaphoreName, [opt] int32 count)
0x939a  pop
0x939b  ldarg.0
0x939c  ldnull
0x939d  call     instance void Microsoft.Crm.Asynchronous.AsyncEventSemaphoreManager::set_OrgThreadCountSemaphore(class [mscorlib]System.Threading.SemaphoreSlim value)
0x93a2  ldarg.0
0x93a3  call     instance class [mscorlib]System.Threading.SemaphoreSlim Microsoft.Crm.Asynchronous.AsyncEventSemaphoreManager::get_OperationTypeSemaphore()
0x93a8  brfalse.s loc_93C3
0x93aa  ldarg.0
0x93ab  call     instance class [mscorlib]System.Threading.SemaphoreSlim Microsoft.Crm.Asynchronous.AsyncEventSemaphoreManager::get_OperationTypeSemaphore()
0x93b0  ldstr    aOperationtypes// "OperationTypeSemaphore"
0x93b5  ldc.i4.1
0x93b6  call     bool Microsoft.Crm.Asynchronous.AsyncEventSemaphoreManager::SafeReleaseSemaphore(class [mscorlib]System.Threading.SemaphoreSlim semaphore, string semaphoreName, [opt] int32 count)
0x93bb  pop
0x93bc  ldarg.0
0x93bd  ldnull
0x93be  call     instance void Microsoft.Crm.Asynchronous.AsyncEventSemaphoreManager::set_OperationTypeSemaphore(class [mscorlib]System.Threading.SemaphoreSlim value)
0x93c3  ret
```
