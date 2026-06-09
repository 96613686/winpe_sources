# EaLibConvertLockSharedToExclusive

- ea: `0x180004480`
- end: `0x1800044b1`
- name: `EaLibConvertLockSharedToExclusive`
- size: `49`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001c80`
- `0x1800026f0`
- `0x1800089c0`
- `0x180008af0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004498`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004498`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000448b`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000448b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000449e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000449e`

## pseudocode

```c
char EaLibConvertLockSharedToExclusive()
{
  RtlReleaseSRWLockShared(&BrokerBindingTableLock);
  RtlAcquireSRWLockExclusive(&BrokerBindingTableLock);
  dword_180012198 = GetCurrentThreadId();
  return 0;
}

```

## disassembly

```asm
0x180004480  sub     rsp, 28h
0x180004484  lea     rcx, BrokerBindingTableLock
0x18000448b  call    cs:__imp_RtlReleaseSRWLockShared
0x180004491  lea     rcx, BrokerBindingTableLock
0x180004498  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000449e  call    cs:__imp_GetCurrentThreadId
0x1800044a4  mov     cs:dword_180012198, eax
0x1800044aa  xor     al, al
0x1800044ac  add     rsp, 28h
0x1800044b0  retn
```
