# CReaderWriterLock3::_TryWriteLock(long)

- ea: `0x18000d120`
- end: `0x18000d18d`
- name: `?_TryWriteLock@CReaderWriterLock3@@AEAA_NJ@Z`
- size: `109`
- prototype: `bool __fastcall(CReaderWriterLock3 *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000d120`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d14f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d16a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d14f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d16a`

## pseudocode

```c
char __fastcall CReaderWriterLock3::_TryWriteLock(CReaderWriterLock3 *this, int a2)
{
  signed __int32 v3; // r8d

  if ( *((_DWORD *)this + 1)
    || (unsigned __int16)*(_DWORD *)this
    || (v3 = *(_DWORD *)this, v3 != _InterlockedCompareExchange((volatile signed __int32 *)this, (v3 + a2) | 0xFFFF, v3)) )
  {
    if ( (*((_DWORD *)this + 1) & 0xFFFFFFFC) == (GetCurrentThreadId() & 0xFFFFFFFC) )
    {
      _InterlockedIncrement((volatile signed __int32 *)this + 1);
      return 1;
    }
    else
    {
      return 0;
    }
  }
  else
  {
    _InterlockedExchange((volatile __int32 *)this + 1, GetCurrentThreadId() & 0xFFFFFFFC | 1);
    return 1;
  }
}

```

## disassembly

```asm
0x18000d120  push    rbx
0x18000d122  sub     rsp, 20h
0x18000d126  mov     eax, [rcx+4]
0x18000d129  mov     rbx, rcx
0x18000d12c  test    eax, eax
0x18000d12e  jnz     short loc_18000D14F
0x18000d130  mov     r8d, [rcx]
0x18000d133  test    r8w, r8w
0x18000d137  jnz     short loc_18000D14F
0x18000d139  lea     ecx, [r8+rdx]
0x18000d13d  mov     eax, r8d
0x18000d140  or      ecx, 0FFFFh
0x18000d146  lock cmpxchg [rbx], ecx
0x18000d14a  cmp     r8d, eax
0x18000d14d  jz      short loc_18000D16A
0x18000d14f  call    cs:__imp_GetCurrentThreadId
0x18000d155  mov     ecx, [rbx+4]
0x18000d158  and     eax, 0FFFFFFFCh
0x18000d15b  and     ecx, 0FFFFFFFCh
0x18000d15e  cmp     ecx, eax
0x18000d160  jz      short loc_18000D181
0x18000d162  xor     al, al
0x18000d164  add     rsp, 20h
0x18000d168  pop     rbx
0x18000d169  retn
0x18000d16a  call    cs:__imp_GetCurrentThreadId
0x18000d170  and     eax, 0FFFFFFFCh
0x18000d173  or      eax, 1
0x18000d176  xchg    eax, [rbx+4]
0x18000d179  mov     al, 1
0x18000d17b  add     rsp, 20h
0x18000d17f  pop     rbx
0x18000d180  retn
0x18000d181  lock inc dword ptr [rbx+4]
0x18000d185  mov     al, 1
0x18000d187  add     rsp, 20h
0x18000d18b  pop     rbx
0x18000d18c  retn
```
