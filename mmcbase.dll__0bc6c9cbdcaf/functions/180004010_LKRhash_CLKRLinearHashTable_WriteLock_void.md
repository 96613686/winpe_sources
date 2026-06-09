# LKRhash::CLKRLinearHashTable::WriteLock(void)

- ea: `0x180004010`
- end: `0x18000408a`
- name: `?WriteLock@CLKRLinearHashTable@LKRhash@@QEAAXXZ`
- size: `122`
- prototype: `void __fastcall(LKRhash::CLKRLinearHashTable *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180019de8`
- `0x18001a07c`

## callees

- `0x180004010`
- `0x180019a34`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000404a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004063`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000404a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004063`

## pseudocode

```c
void __fastcall LKRhash::CLKRLinearHashTable::WriteLock(LKRhash::CLKRLinearHashTable *this)
{
  volatile __int32 *v1; // rbx
  signed __int32 v2; // edx

  if ( *((_BYTE *)this + 153) )
  {
    v1 = (volatile __int32 *)((char *)this + 24);
    if ( *((_DWORD *)this + 7)
      || (unsigned __int16)*v1
      || (v2 = *v1, v2 != _InterlockedCompareExchange(v1, (v2 + 0x10000) | 0xFFFF, v2)) )
    {
      if ( (*((_DWORD *)this + 7) & 0xFFFFFFFC) == (GetCurrentThreadId() & 0xFFFFFFFC) )
        _InterlockedExchange(v1 + 1, *((_DWORD *)v1 + 1) + 1);
      else
        CReaderWriterLock3::_WriteLockSpin((CReaderWriterLock3 *)v1);
    }
    else
    {
      _InterlockedExchange((volatile __int32 *)this + 7, GetCurrentThreadId() & 0xFFFFFFFC | 1);
    }
  }
}

```

## disassembly

```asm
0x180004010  sub     rsp, 28h
0x180004014  cmp     byte ptr [rcx+99h], 0
0x18000401b  jz      short loc_18000405E
0x18000401d  mov     eax, [rcx+1Ch]
0x180004020  mov     [rsp+28h+var_8], rbx
0x180004025  lea     rbx, [rcx+18h]
0x180004029  test    eax, eax
0x18000402b  jnz     short loc_180004063
0x18000402d  mov     edx, [rbx]
0x18000402f  test    dx, dx
0x180004032  jnz     short loc_180004063
0x180004034  lea     ecx, [rdx+10000h]
0x18000403a  mov     eax, edx
0x18000403c  or      ecx, 0FFFFh
0x180004042  lock cmpxchg [rbx], ecx
0x180004046  cmp     edx, eax
0x180004048  jnz     short loc_180004063
0x18000404a  call    cs:__imp_GetCurrentThreadId
0x180004050  and     eax, 0FFFFFFFCh
0x180004053  or      eax, 1
0x180004056  xchg    eax, [rbx+4]
0x180004059  mov     rbx, [rsp+28h+var_8]
0x18000405e  add     rsp, 28h
0x180004062  retn
0x180004063  call    cs:__imp_GetCurrentThreadId
0x180004069  mov     ecx, [rbx+4]
0x18000406c  and     eax, 0FFFFFFFCh
0x18000406f  and     ecx, 0FFFFFFFCh
0x180004072  cmp     ecx, eax
0x180004074  jnz     short loc_180004080
0x180004076  mov     eax, [rbx+4]
0x180004079  inc     eax
0x18000407b  xchg    eax, [rbx+4]
0x18000407e  jmp     short loc_180004059
0x180004080  mov     rcx, rbx; this
0x180004083  call    ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x180004088  jmp     short loc_180004059
```
