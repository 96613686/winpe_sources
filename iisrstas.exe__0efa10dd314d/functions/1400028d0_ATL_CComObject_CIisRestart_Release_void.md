# ATL::CComObject<CIisRestart>::Release(void)

- ea: `0x1400028d0`
- end: `0x140002953`
- name: `?Release@?$CComObject@VCIisRestart@@@ATL@@UEAAKXZ`
- size: `131`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001054`
- `0x1400028d0`
- `0x1400029d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140002933`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140002933`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CIisRestart>::Release(unsigned int *Block)
{
  CExeModule *i; // rcx
  unsigned int v3; // edi

  for ( i = (CExeModule *)Block[2];
        (_DWORD)i != 0x7FFFFFFF
     && (_DWORD)i != _InterlockedCompareExchange((volatile signed __int32 *)Block + 2, (_DWORD)i - 1, (signed __int32)i);
        i = (CExeModule *)Block[2] )
  {
    ;
  }
  v3 = (_DWORD)i - 1;
  if ( (_DWORD)i == 1 )
  {
    _InterlockedIncrement(&dword_14000A798);
    if ( Block )
    {
      Block[2] = 1;
      *(_QWORD *)Block = &ATL::CComObject<CIisRestart>::`vftable';
      CExeModule::Unlock(i);
      if ( *((_BYTE *)Block + 56) != (_BYTE)v3 )
      {
        *((_BYTE *)Block + 56) = v3;
        DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 4));
      }
      operator delete(Block);
    }
    CExeModule::Unlock(i);
  }
  return v3;
}

```

## disassembly

```asm
0x1400028d0  mov     [rsp+arg_0], rbx
0x1400028d5  push    rdi
0x1400028d6  sub     rsp, 20h
0x1400028da  mov     rbx, rcx
0x1400028dd  mov     r8d, 7FFFFFFFh
0x1400028e3  mov     ecx, [rcx+8]
0x1400028e6  jmp     short loc_1400028F7
0x1400028e8  lea     edx, [rcx-1]
0x1400028eb  mov     eax, ecx
0x1400028ed  lock cmpxchg [rbx+8], edx
0x1400028f2  jz      short loc_1400028FC
0x1400028f4  mov     ecx, [rbx+8]; this
0x1400028f7  cmp     ecx, r8d
0x1400028fa  jnz     short loc_1400028E8
0x1400028fc  lea     edi, [rcx-1]
0x1400028ff  test    edi, edi
0x140002901  jnz     short loc_140002946
0x140002903  lock inc cs:dword_14000A798
0x14000290a  test    rbx, rbx
0x14000290d  jz      short loc_140002941
0x14000290f  lea     rax, ??_7?$CComObject@VCIisRestart@@@ATL@@6B@; const ATL::CComObject<CIisRestart>::`vftable'
0x140002916  mov     dword ptr [rbx+8], 1
0x14000291d  mov     [rbx], rax
0x140002920  call    ?Unlock@CExeModule@@QEAAJXZ; CExeModule::Unlock(void)
0x140002925  lea     rcx, [rbx+10h]; lpCriticalSection
0x140002929  cmp     [rcx+28h], dil
0x14000292d  jz      short loc_140002939
0x14000292f  mov     [rcx+28h], dil
0x140002933  call    cs:__imp_DeleteCriticalSection
0x140002939  mov     rcx, rbx; Block
0x14000293c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002941  call    ?Unlock@CExeModule@@QEAAJXZ; CExeModule::Unlock(void)
0x140002946  mov     rbx, [rsp+28h+arg_0]
0x14000294b  mov     eax, edi
0x14000294d  add     rsp, 20h
0x140002951  pop     rdi
0x140002952  retn
```
