# LKRhash::CLKRLinearHashTable::_ReadOrWriteLock(void)

- ea: `0x180001f10`
- end: `0x180001f81`
- name: `?_ReadOrWriteLock@CLKRLinearHashTable@LKRhash@@AEBA_NXZ`
- size: `113`
- prototype: `bool __fastcall(LKRhash::CLKRLinearHashTable *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001940`
- `0x180001c00`

## callees

- `0x180001f10`
- `0x180004180`
- `0x18001971c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001f2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001f2e`

## pseudocode

```c
char __fastcall LKRhash::CLKRLinearHashTable::_ReadOrWriteLock(LKRhash::CLKRLinearHashTable *this)
{
  volatile signed __int32 *v1; // rbx
  int v2; // edi
  signed __int32 v3; // edx

  if ( !*((_BYTE *)this + 153) )
    return 1;
  v1 = (volatile signed __int32 *)((char *)this + 24);
  v2 = *((_DWORD *)this + 7);
  if ( ((v2 ^ GetCurrentThreadId()) & 0xFFFFFFFC) != 0 )
  {
    if ( (unsigned __int16)*v1 == 0xFFFF || (v3 = *v1, v3 != _InterlockedCompareExchange(v1, v3 + 1, v3)) )
      CReaderWriterLock3::_LockSpin(v1, 3);
    return 1;
  }
  else
  {
    CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)v1);
    return 0;
  }
}

```

## disassembly

```asm
0x180001f10  sub     rsp, 28h
0x180001f14  cmp     byte ptr [rcx+99h], 0
0x180001f1b  jz      short loc_180001F71
0x180001f1d  mov     [rsp+28h+arg_0], rbx
0x180001f22  lea     rbx, [rcx+18h]
0x180001f26  mov     [rsp+28h+var_8], rdi
0x180001f2b  mov     edi, [rbx+4]
0x180001f2e  call    cs:__imp_GetCurrentThreadId
0x180001f34  xor     eax, edi
0x180001f36  mov     rdi, [rsp+28h+var_8]
0x180001f3b  test    eax, 0FFFFFFFCh
0x180001f40  jz      short loc_180001F75
0x180001f42  mov     edx, [rbx]
0x180001f44  cmp     dx, 0FFFFh
0x180001f49  jz      short loc_180001F58
0x180001f4b  lea     ecx, [rdx+1]
0x180001f4e  mov     eax, edx
0x180001f50  lock cmpxchg [rbx], ecx
0x180001f54  cmp     edx, eax
0x180001f56  jz      short loc_180001F65
0x180001f58  mov     edx, 3
0x180001f5d  mov     rcx, rbx
0x180001f60  call    ?_LockSpin@CReaderWriterLock3@@AEAAXW4SPIN_TYPE@1@@Z; CReaderWriterLock3::_LockSpin(CReaderWriterLock3::SPIN_TYPE)
0x180001f65  mov     al, 1
0x180001f67  mov     rbx, [rsp+28h+arg_0]
0x180001f6c  add     rsp, 28h
0x180001f70  retn
0x180001f71  mov     al, 1
0x180001f73  jmp     short loc_180001F6C
0x180001f75  mov     rcx, rbx; this
0x180001f78  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180001f7d  xor     al, al
0x180001f7f  jmp     short loc_180001F67
```
