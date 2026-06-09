# CReaderWriterLock3::TryWriteLock(void)

- ea: `0x18001b8b0`
- end: `0x18001b903`
- name: `?TryWriteLock@CReaderWriterLock3@@QEAA_NXZ`
- size: `83`
- prototype: `bool __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800039d0`
- `0x18001b8b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b8dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b8dd`

## pseudocode

```c
char __fastcall CReaderWriterLock3::TryWriteLock(CReaderWriterLock3 *this)
{
  signed __int32 v2; // ecx

  if ( *((_DWORD *)this + 1) )
    return CReaderWriterLock3::_TryWriteLock2(this) != 0;
  v2 = *(_DWORD *)this;
  if ( (_WORD)v2 || v2 != _InterlockedCompareExchange((volatile signed __int32 *)this, (v2 + 0x10000) | 0xFFFF, v2) )
    return CReaderWriterLock3::_TryWriteLock2(this) != 0;
  _InterlockedExchange((volatile __int32 *)this + 1, GetCurrentThreadId() & 0xFFFFFFFC | 1);
  return 1;
}

```

## disassembly

```asm
0x18001b8b0  push    rbx
0x18001b8b2  sub     rsp, 20h
0x18001b8b6  mov     eax, [rcx+4]
0x18001b8b9  mov     rbx, rcx
0x18001b8bc  test    eax, eax
0x18001b8be  jnz     short loc_18001B8F0
0x18001b8c0  mov     ecx, [rcx]
0x18001b8c2  test    cx, cx
0x18001b8c5  jnz     short loc_18001B8F0
0x18001b8c7  lea     edx, [rcx+10000h]
0x18001b8cd  mov     eax, ecx
0x18001b8cf  or      edx, 0FFFFh
0x18001b8d5  lock cmpxchg [rbx], edx
0x18001b8d9  cmp     ecx, eax
0x18001b8db  jnz     short loc_18001B8F0
0x18001b8dd  call    cs:__imp_GetCurrentThreadId
0x18001b8e3  and     eax, 0FFFFFFFCh
0x18001b8e6  or      eax, 1
0x18001b8e9  xchg    eax, [rbx+4]
0x18001b8ec  mov     al, 1
0x18001b8ee  jmp     short loc_18001B8FD
0x18001b8f0  mov     rcx, rbx; this
0x18001b8f3  call    ?_TryWriteLock2@CReaderWriterLock3@@AEAA_NXZ; CReaderWriterLock3::_TryWriteLock2(void)
0x18001b8f8  test    al, al
0x18001b8fa  setnz   al
0x18001b8fd  add     rsp, 20h
0x18001b901  pop     rbx
0x18001b902  retn
```
