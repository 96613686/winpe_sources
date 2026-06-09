# CLKRLinearHashTable::WriteLock(void)

- ea: `0x180010e80`
- end: `0x180010efb`
- name: `?WriteLock@CLKRLinearHashTable@@QEAAXXZ`
- size: `123`
- prototype: `void __fastcall(CLKRLinearHashTable *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007e60`
- `0x180010e80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010eae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010ed4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010eae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010ed4`

## pseudocode

```c
void __fastcall CLKRLinearHashTable::WriteLock(CLKRLinearHashTable *this)
{
  volatile signed __int32 *v1; // rbx
  signed __int32 v2; // edx

  v1 = (volatile signed __int32 *)((char *)this + 24);
  if ( *((_DWORD *)this + 7)
    || (unsigned __int16)*v1
    || (v2 = *v1, v2 != _InterlockedCompareExchange(v1, (v2 + 0x10000) | 0xFFFF, v2)) )
  {
    if ( (*((_DWORD *)this + 7) & 0xFFFFFFFC) == (GetCurrentThreadId() & 0xFFFFFFFC) )
      _InterlockedIncrement(v1 + 1);
    else
      CReaderWriterLock3::_WriteLockSpin((CReaderWriterLock3 *)v1);
  }
  else
  {
    _InterlockedExchange((volatile __int32 *)this + 7, GetCurrentThreadId() & 0xFFFFFFFC | 1);
  }
}

```

## disassembly

```asm
0x180010e80  push    rbx
0x180010e82  sub     rsp, 20h
0x180010e86  lea     rbx, [rcx+18h]
0x180010e8a  mov     eax, [rbx+4]
0x180010e8d  test    eax, eax
0x180010e8f  jnz     short loc_180010EAE
0x180010e91  mov     edx, [rbx]
0x180010e93  test    dx, dx
0x180010e96  jnz     short loc_180010EAE
0x180010e98  lea     ecx, [rdx+10000h]
0x180010e9e  mov     eax, edx
0x180010ea0  or      ecx, 0FFFFh
0x180010ea6  lock cmpxchg [rbx], ecx
0x180010eaa  cmp     edx, eax
0x180010eac  jz      short loc_180010ED4
0x180010eae  call    cs:__imp_GetCurrentThreadId
0x180010eb5  nop     dword ptr [rax+rax+00h]
0x180010eba  mov     ecx, [rbx+4]
0x180010ebd  and     eax, 0FFFFFFFCh
0x180010ec0  and     ecx, 0FFFFFFFCh
0x180010ec3  cmp     ecx, eax
0x180010ec5  jz      short loc_180010EF0
0x180010ec7  mov     rcx, rbx; this
0x180010eca  add     rsp, 20h
0x180010ece  pop     rbx
0x180010ecf  jmp     ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x180010ed4  call    cs:__imp_GetCurrentThreadId
0x180010edb  nop     dword ptr [rax+rax+00h]
0x180010ee0  and     eax, 0FFFFFFFCh
0x180010ee3  or      eax, 1
0x180010ee6  xchg    eax, [rbx+4]
0x180010ee9  add     rsp, 20h
0x180010eed  pop     rbx
0x180010eee  retn
0x180010ef0  lock inc dword ptr [rbx+4]
0x180010ef4  add     rsp, 20h
0x180010ef8  pop     rbx
0x180010ef9  retn
```
