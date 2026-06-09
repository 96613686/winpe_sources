# CleanupPixEtwThread(void)

- ea: `0x1800050c4`
- end: `0x18000510d`
- name: `?CleanupPixEtwThread@@YAXXZ`
- size: `73`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004ba8`

## callees

- `0x1800119f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005106`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800050cf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800050cf`

## pseudocode

```c
void CleanupPixEtwThread(void)
{
  AcquireSRWLockExclusive(&SRWLock);
  std::list_PIXEventsThreadInfo_std::allocator_PIXEventsThreadInfo___::remove_if__lambda_a8e5f25957f51ab29bb4e744553e99f1___();
  *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 24LL) = 0;
  ReleaseSRWLockExclusive(&SRWLock);
}

```

## disassembly

```asm
0x1800050c4  sub     rsp, 28h
0x1800050c8  lea     rcx, SRWLock; SRWLock
0x1800050cf  call    cs:__imp_AcquireSRWLockExclusive
0x1800050d5  call    std__list_PIXEventsThreadInfo_std__allocator_PIXEventsThreadInfo_____remove_if__lambda_a8e5f25957f51ab29bb4e744553e99f1___
0x1800050da  mov     edx, cs:_tls_index
0x1800050e0  lea     rcx, SRWLock
0x1800050e7  mov     rax, gs:58h
0x1800050f0  mov     r8d, 18h
0x1800050f6  mov     rax, [rax+rdx*8]
0x1800050fa  mov     qword ptr [r8+rax], 0
0x180005102  add     rsp, 28h
0x180005106  jmp     cs:__imp_ReleaseSRWLockExclusive
```
