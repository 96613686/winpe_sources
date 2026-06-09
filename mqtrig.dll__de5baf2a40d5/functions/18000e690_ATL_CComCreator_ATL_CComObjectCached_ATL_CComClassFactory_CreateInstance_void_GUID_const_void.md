# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000e690`
- end: `0x18000e778`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `232`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000dce4`
- `0x18000e690`
- `0x18000ed1c`
- `0x180014ae8`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // edi
  char *v8; // rax
  __int64 (__fastcall ***v9)(_QWORD, __int64, _QWORD *); // rbx
  int v10; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = (char *)MmAllocate(0x78u);
  v9 = (__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *))v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *((_OWORD *)v8 + 1) = 0;
    *((_OWORD *)v8 + 2) = 0;
    *((_QWORD *)v8 + 6) = 0;
    v8[56] = 0;
    *(_QWORD *)v8 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
    *(_OWORD *)(v8 + 72) = 0;
    *(_OWORD *)(v8 + 88) = 0;
    *((_QWORD *)v8 + 13) = 0;
    v8[112] = 0;
    *((_QWORD *)v8 + 8) = a1;
    v10 = ATL::CComAutoDeleteCriticalSection::Init((ATL::CComAutoDeleteCriticalSection *)(v8 + 16));
    if ( v10 >= 0 )
      v10 = ATL::CComAutoDeleteCriticalSection::Init((ATL::CComAutoDeleteCriticalSection *)(v9 + 9));
    v7 = 0;
    if ( v10 < 0 )
      v7 = v10;
    if ( v7 || (v7 = (**v9)(v9, a2, a3)) != 0 )
      ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x18000e690  mov     [rsp+arg_0], rbx
0x18000e695  mov     [rsp+arg_8], rbp
0x18000e69a  push    rsi
0x18000e69b  push    rdi
0x18000e69c  push    r14
0x18000e69e  sub     rsp, 20h
0x18000e6a2  mov     rsi, r8
0x18000e6a5  mov     r14, rdx
0x18000e6a8  mov     rbp, rcx
0x18000e6ab  test    r8, r8
0x18000e6ae  jnz     short loc_18000E6BA
0x18000e6b0  mov     eax, 80004003h
0x18000e6b5  jmp     loc_18000E765
0x18000e6ba  mov     ecx, 78h ; 'x'; unsigned __int64
0x18000e6bf  mov     qword ptr [r8], 0
0x18000e6c6  mov     edi, 8007000Eh
0x18000e6cb  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18000e6d0  mov     [rsp+38h+arg_10], rax
0x18000e6d5  mov     rbx, rax
0x18000e6d8  test    rax, rax
0x18000e6db  jz      loc_18000E763
0x18000e6e1  mov     dword ptr [rax+8], 0
0x18000e6e8  xorps   xmm0, xmm0
0x18000e6eb  movups  xmmword ptr [rbx+10h], xmm0
0x18000e6ef  xor     eax, eax
0x18000e6f1  movups  xmmword ptr [rbx+20h], xmm0
0x18000e6f5  mov     [rbx+30h], rax
0x18000e6f9  mov     [rbx+38h], al
0x18000e6fc  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x18000e703  mov     [rbx], rax
0x18000e706  xor     eax, eax
0x18000e708  movups  xmmword ptr [rbx+48h], xmm0
0x18000e70c  movups  xmmword ptr [rbx+58h], xmm0
0x18000e710  mov     [rbx+68h], rax
0x18000e714  mov     [rbx+70h], al
0x18000e717  test    rbx, rbx
0x18000e71a  jz      short loc_18000E763
0x18000e71c  lea     rcx, [rbx+10h]; this
0x18000e720  mov     [rbx+40h], rbp
0x18000e724  call    ?Init@CComAutoDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComAutoDeleteCriticalSection::Init(void)
0x18000e729  test    eax, eax
0x18000e72b  js      short loc_18000E736
0x18000e72d  lea     rcx, [rbx+48h]; this
0x18000e731  call    ?Init@CComAutoDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComAutoDeleteCriticalSection::Init(void)
0x18000e736  xor     edi, edi
0x18000e738  test    eax, eax
0x18000e73a  cmovs   edi, eax
0x18000e73d  test    edi, edi
0x18000e73f  jnz     short loc_18000E75B
0x18000e741  mov     rax, [rbx]
0x18000e744  mov     r8, rsi
0x18000e747  mov     rdx, r14
0x18000e74a  mov     rcx, rbx
0x18000e74d  mov     rax, [rax]
0x18000e750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e755  mov     edi, eax
0x18000e757  test    eax, eax
0x18000e759  jz      short loc_18000E763
0x18000e75b  mov     rcx, rbx; Block
0x18000e75e  call    ??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x18000e763  mov     eax, edi
0x18000e765  mov     rbx, [rsp+38h+arg_0]
0x18000e76a  mov     rbp, [rsp+38h+arg_8]
0x18000e76f  add     rsp, 20h
0x18000e773  pop     r14
0x18000e775  pop     rdi
0x18000e776  pop     rsi
0x18000e777  retn
```
