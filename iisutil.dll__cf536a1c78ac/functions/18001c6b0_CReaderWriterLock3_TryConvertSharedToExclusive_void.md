# CReaderWriterLock3::TryConvertSharedToExclusive(void)

- ea: `0x18001c6b0`
- end: `0x18001c6ed`
- name: `?TryConvertSharedToExclusive@CReaderWriterLock3@@QEAA_NXZ`
- size: `61`
- prototype: `bool __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001c6b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c6cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c6cb`

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
0x18001c6b0  push    rbx
0x18001c6b2  sub     rsp, 20h
0x18001c6b6  mov     eax, [rcx]
0x18001c6b8  mov     rbx, rcx
0x18001c6bb  cmp     eax, 1
0x18001c6be  jnz     short loc_18001C6E4
0x18001c6c0  mov     ecx, 1FFFFh
0x18001c6c5  lock cmpxchg [rbx], ecx
0x18001c6c9  jnz     short loc_18001C6E4
0x18001c6cb  call    cs:__imp_GetCurrentThreadId
0x18001c6d2  nop     dword ptr [rax+rax+00h]
0x18001c6d7  and     eax, 0FFFFFFFCh
0x18001c6da  or      eax, 1
0x18001c6dd  xchg    eax, [rbx+4]
0x18001c6e0  mov     al, 1
0x18001c6e2  jmp     short loc_18001C6E6
0x18001c6e4  xor     al, al
0x18001c6e6  add     rsp, 20h
0x18001c6ea  pop     rbx
0x18001c6eb  retn
```
