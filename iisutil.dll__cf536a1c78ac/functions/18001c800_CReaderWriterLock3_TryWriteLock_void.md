# CReaderWriterLock3::TryWriteLock(void)

- ea: `0x18001c800`
- end: `0x18001c85a`
- name: `?TryWriteLock@CReaderWriterLock3@@QEAA_NXZ`
- size: `90`
- prototype: `bool __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004450`
- `0x18001c800`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c82d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c82d`

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
0x18001c800  push    rbx
0x18001c802  sub     rsp, 20h
0x18001c806  mov     eax, [rcx+4]
0x18001c809  mov     rbx, rcx
0x18001c80c  test    eax, eax
0x18001c80e  jnz     short loc_18001C846
0x18001c810  mov     ecx, [rcx]
0x18001c812  test    cx, cx
0x18001c815  jnz     short loc_18001C846
0x18001c817  lea     edx, [rcx+10000h]
0x18001c81d  mov     eax, ecx
0x18001c81f  or      edx, 0FFFFh
0x18001c825  lock cmpxchg [rbx], edx
0x18001c829  cmp     ecx, eax
0x18001c82b  jnz     short loc_18001C846
0x18001c82d  call    cs:__imp_GetCurrentThreadId
0x18001c834  nop     dword ptr [rax+rax+00h]
0x18001c839  and     eax, 0FFFFFFFCh
0x18001c83c  or      eax, 1
0x18001c83f  xchg    eax, [rbx+4]
0x18001c842  mov     al, 1
0x18001c844  jmp     short loc_18001C853
0x18001c846  mov     rcx, rbx; this
0x18001c849  call    ?_TryWriteLock2@CReaderWriterLock3@@AEAA_NXZ; CReaderWriterLock3::_TryWriteLock2(void)
0x18001c84e  test    al, al
0x18001c850  setnz   al
0x18001c853  add     rsp, 20h
0x18001c857  pop     rbx
0x18001c858  retn
```
