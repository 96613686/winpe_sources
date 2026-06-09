# CReadWriteLock::AcquireExclusive(void)

- ea: `0x140002964`
- end: `0x140002982`
- name: `?AcquireExclusive@CReadWriteLock@@QEAAXXZ`
- size: `30`
- prototype: `void __fastcall(CReadWriteLock *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140002850`
- `0x1400028cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000296d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000296d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002973`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002973`

## pseudocode

```c
void __fastcall CReadWriteLock::AcquireExclusive(RTL_SRWLOCK *this)
{
  AcquireSRWLockExclusive(this);
  LODWORD(this[1].Ptr) = GetCurrentThreadId();
}

```

## disassembly

```asm
0x140002964  push    rbx
0x140002966  sub     rsp, 20h
0x14000296a  mov     rbx, rcx
0x14000296d  call    cs:__imp_AcquireSRWLockExclusive
0x140002973  call    cs:__imp_GetCurrentThreadId
0x140002979  mov     [rbx+8], eax
0x14000297c  add     rsp, 20h
0x140002980  pop     rbx
0x140002981  retn
```
