# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180009690`
- end: `0x18000971c`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `140`
- prototype: `__int64 __fastcall(char *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001334`
- `0x180009690`
- `0x180019010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800096e7`
- `KERNEL32!DeleteCriticalSection` at `0x1800096e7`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::Release(char *Block)
{
  signed __int32 i; // ecx
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)Block + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange((volatile signed __int32 *)Block + 2, i - 1, i);
        i = *((_DWORD *)Block + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    if ( Block )
    {
      *((_DWORD *)Block + 2) = -1073741823;
      *(_QWORD *)Block = &ATL::CComClassFactory::`vftable';
      if ( Block[56] != (_BYTE)v3 )
      {
        Block[56] = v3;
        DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 16));
      }
      operator delete(Block);
    }
  }
  else if ( i == 2 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *, _QWORD, __int64))(*(_QWORD *)ATL::_pAtlModule + 16LL))(
      ATL::_pAtlModule,
      *(_QWORD *)ATL::_pAtlModule,
      0x7FFFFFFF);
  }
  return v3;
}

```

## disassembly

```asm
0x180009690  mov     [rsp+arg_0], rbx
0x180009695  push    rdi
0x180009696  sub     rsp, 20h
0x18000969a  mov     rbx, rcx
0x18000969d  mov     r8d, 7FFFFFFFh
0x1800096a3  mov     ecx, [rcx+8]
0x1800096a6  jmp     short loc_1800096B7
0x1800096a8  lea     edx, [rcx-1]
0x1800096ab  mov     eax, ecx
0x1800096ad  lock cmpxchg [rbx+8], edx
0x1800096b2  jz      short loc_1800096BC
0x1800096b4  mov     ecx, [rbx+8]
0x1800096b7  cmp     ecx, r8d
0x1800096ba  jnz     short loc_1800096A8
0x1800096bc  lea     edi, [rcx-1]
0x1800096bf  test    edi, edi
0x1800096c1  jnz     short loc_1800096F7
0x1800096c3  test    rbx, rbx
0x1800096c6  jz      short loc_18000970F
0x1800096c8  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x1800096cf  mov     dword ptr [rbx+8], 0C0000001h
0x1800096d6  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800096da  mov     [rbx], rax
0x1800096dd  cmp     [rcx+28h], dil
0x1800096e1  jz      short loc_1800096ED
0x1800096e3  mov     [rcx+28h], dil
0x1800096e7  call    cs:__imp_DeleteCriticalSection
0x1800096ed  mov     rcx, rbx; Block
0x1800096f0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800096f5  jmp     short loc_18000970F
0x1800096f7  cmp     edi, 1
0x1800096fa  jnz     short loc_18000970F
0x1800096fc  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009703  mov     rdx, [rcx]
0x180009706  mov     rax, [rdx+10h]
0x18000970a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000970f  mov     rbx, [rsp+28h+arg_0]
0x180009714  mov     eax, edi
0x180009716  add     rsp, 20h
0x18000971a  pop     rdi
0x18000971b  retn
```
