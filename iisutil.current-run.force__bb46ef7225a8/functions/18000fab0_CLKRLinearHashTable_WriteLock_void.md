# CLKRLinearHashTable::WriteLock(void)

- ea: `0x18000fab0`
- end: `0x18000fb1d`
- name: `?WriteLock@CLKRLinearHashTable@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(CLKRLinearHashTable *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007180`
- `0x18000fab0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fade`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fafe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fade`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fafe`

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
0x18000fab0  push    rbx
0x18000fab2  sub     rsp, 20h
0x18000fab6  lea     rbx, [rcx+18h]
0x18000faba  mov     eax, [rbx+4]
0x18000fabd  test    eax, eax
0x18000fabf  jnz     short loc_18000FADE
0x18000fac1  mov     edx, [rbx]
0x18000fac3  test    dx, dx
0x18000fac6  jnz     short loc_18000FADE
0x18000fac8  lea     ecx, [rdx+10000h]
0x18000face  mov     eax, edx
0x18000fad0  or      ecx, 0FFFFh
0x18000fad6  lock cmpxchg [rbx], ecx
0x18000fada  cmp     edx, eax
0x18000fadc  jz      short loc_18000FAFE
0x18000fade  call    cs:__imp_GetCurrentThreadId
0x18000fae4  mov     ecx, [rbx+4]
0x18000fae7  and     eax, 0FFFFFFFCh
0x18000faea  and     ecx, 0FFFFFFFCh
0x18000faed  cmp     ecx, eax
0x18000faef  jz      short loc_18000FB13
0x18000faf1  mov     rcx, rbx; this
0x18000faf4  add     rsp, 20h
0x18000faf8  pop     rbx
0x18000faf9  jmp     ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x18000fafe  call    cs:__imp_GetCurrentThreadId
0x18000fb04  and     eax, 0FFFFFFFCh
0x18000fb07  or      eax, 1
0x18000fb0a  xchg    eax, [rbx+4]
0x18000fb0d  add     rsp, 20h
0x18000fb11  pop     rbx
0x18000fb12  retn
0x18000fb13  lock inc dword ptr [rbx+4]
0x18000fb17  add     rsp, 20h
0x18000fb1b  pop     rbx
0x18000fb1c  retn
```
