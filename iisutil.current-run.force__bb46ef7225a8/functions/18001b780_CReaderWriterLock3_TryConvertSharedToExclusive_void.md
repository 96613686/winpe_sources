# CReaderWriterLock3::TryConvertSharedToExclusive(void)

- ea: `0x18001b780`
- end: `0x18001b7b6`
- name: `?TryConvertSharedToExclusive@CReaderWriterLock3@@QEAA_NXZ`
- size: `54`
- prototype: `bool __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001b780`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b79b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b79b`

## pseudocode

```c
char __fastcall CReaderWriterLock3::TryConvertSharedToExclusive(CReaderWriterLock3 *this)
{
  if ( *(_DWORD *)this != 1 || _InterlockedCompareExchange((volatile signed __int32 *)this, 0x1FFFF, 1) != 1 )
    return 0;
  _InterlockedExchange((volatile __int32 *)this + 1, GetCurrentThreadId() & 0xFFFFFFFC | 1);
  return 1;
}

```

## disassembly

```asm
0x18001b780  push    rbx
0x18001b782  sub     rsp, 20h
0x18001b786  mov     eax, [rcx]
0x18001b788  mov     rbx, rcx
0x18001b78b  cmp     eax, 1
0x18001b78e  jnz     short loc_18001B7AE
0x18001b790  mov     ecx, 1FFFFh
0x18001b795  lock cmpxchg [rbx], ecx
0x18001b799  jnz     short loc_18001B7AE
0x18001b79b  call    cs:__imp_GetCurrentThreadId
0x18001b7a1  and     eax, 0FFFFFFFCh
0x18001b7a4  or      eax, 1
0x18001b7a7  xchg    eax, [rbx+4]
0x18001b7aa  mov     al, 1
0x18001b7ac  jmp     short loc_18001B7B0
0x18001b7ae  xor     al, al
0x18001b7b0  add     rsp, 20h
0x18001b7b4  pop     rbx
0x18001b7b5  retn
```
