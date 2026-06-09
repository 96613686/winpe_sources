# CReaderWriterLock3::_TryWriteLock(long)

- ea: `0x18000e1f0`
- end: `0x18000e26c`
- name: `?_TryWriteLock@CReaderWriterLock3@@AEAA_NJ@Z`
- size: `124`
- prototype: `bool __fastcall(CReaderWriterLock3 *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000e1f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e21f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e241`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e21f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e241`

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
0x18000e1f0  push    rbx
0x18000e1f2  sub     rsp, 20h
0x18000e1f6  mov     eax, [rcx+4]
0x18000e1f9  mov     rbx, rcx
0x18000e1fc  test    eax, eax
0x18000e1fe  jnz     short loc_18000E21F
0x18000e200  mov     r8d, [rcx]
0x18000e203  test    r8w, r8w
0x18000e207  jnz     short loc_18000E21F
0x18000e209  lea     ecx, [r8+rdx]
0x18000e20d  mov     eax, r8d
0x18000e210  or      ecx, 0FFFFh
0x18000e216  lock cmpxchg [rbx], ecx
0x18000e21a  cmp     r8d, eax
0x18000e21d  jz      short loc_18000E241
0x18000e21f  call    cs:__imp_GetCurrentThreadId
0x18000e226  nop     dword ptr [rax+rax+00h]
0x18000e22b  mov     ecx, [rbx+4]
0x18000e22e  and     eax, 0FFFFFFFCh
0x18000e231  and     ecx, 0FFFFFFFCh
0x18000e234  cmp     ecx, eax
0x18000e236  jz      short loc_18000E25F
0x18000e238  xor     al, al
0x18000e23a  add     rsp, 20h
0x18000e23e  pop     rbx
0x18000e23f  retn
0x18000e241  call    cs:__imp_GetCurrentThreadId
0x18000e248  nop     dword ptr [rax+rax+00h]
0x18000e24d  and     eax, 0FFFFFFFCh
0x18000e250  or      eax, 1
0x18000e253  xchg    eax, [rbx+4]
0x18000e256  mov     al, 1
0x18000e258  add     rsp, 20h
0x18000e25c  pop     rbx
0x18000e25d  retn
0x18000e25f  lock inc dword ptr [rbx+4]
0x18000e263  mov     al, 1
0x18000e265  add     rsp, 20h
0x18000e269  pop     rbx
0x18000e26a  retn
```
