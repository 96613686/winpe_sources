# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006490`
- end: `0x1800065b6`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `294`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001250`
- `0x1800042bc`
- `0x180006490`
- `0x180012010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000659f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000659f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006596`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006596`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r15
  __int64 v4; // r12
  __int64 v5; // r14
  int v7; // esi
  char *v8; // rax
  char *v9; // rbx
  _BYTE *v10; // r14
  char *v11; // [rsp+20h] [rbp-48h]

  v3 = a3;
  v4 = a2;
  v5 = a1;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = (char *)operator new(0x48u);
    v9 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *((_OWORD *)v8 + 1) = 0;
      *((_OWORD *)v8 + 2) = 0;
      *((_QWORD *)v8 + 6) = 0;
      v8[56] = 0;
      *(_QWORD *)v8 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
    }
    v11 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v5 = a1;
    v7 = -2147024882;
    v9 = v11;
  }
  if ( v9 )
  {
    *((_QWORD *)v9 + 8) = v5;
    v7 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 16));
    v10 = v9 + 56;
    if ( v7 < 0 || (*v10 = 1, (v7 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v9)(v9, v4, v3)) != 0) )
    {
      *((_DWORD *)v9 + 2) = -1073741823;
      *(_QWORD *)v9 = &ATL::CComClassFactory::`vftable';
      if ( *v10 )
      {
        *v10 = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
      }
      operator delete(v9);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180006490  mov     [rsp+arg_10], r8
0x180006495  mov     [rsp+arg_8], rdx
0x18000649a  mov     [rsp+arg_0], rcx
0x18000649f  push    rbx
0x1800064a0  push    rsi
0x1800064a1  push    r12
0x1800064a3  push    r13
0x1800064a5  push    r14
0x1800064a7  push    r15
0x1800064a9  sub     rsp, 38h
0x1800064ad  mov     r15, r8
0x1800064b0  mov     r12, rdx
0x1800064b3  mov     r14, rcx
0x1800064b6  test    r8, r8
0x1800064b9  jnz     short loc_1800064C5
0x1800064bb  mov     eax, 80004003h
0x1800064c0  jmp     loc_1800065A7
0x1800064c5  mov     qword ptr [r8], 0
0x1800064cc  mov     esi, 8007000Eh
0x1800064d1  mov     [rsp+68h+arg_18], esi
0x1800064d8  mov     [rsp+68h+var_48], 0
0x1800064e1  mov     ecx, 48h ; 'H'; Size
0x1800064e6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800064eb  mov     rbx, rax
0x1800064ee  test    rbx, rbx
0x1800064f1  jz      short loc_180006518
0x1800064f3  mov     dword ptr [rax+8], 0
0x1800064fa  xorps   xmm0, xmm0
0x1800064fd  xor     eax, eax
0x1800064ff  movups  xmmword ptr [rbx+10h], xmm0
0x180006503  movups  xmmword ptr [rbx+20h], xmm0
0x180006507  mov     [rbx+30h], rax
0x18000650b  mov     [rbx+38h], al
0x18000650e  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180006515  mov     [rbx], rax
0x180006518  mov     [rsp+68h+var_48], rbx
0x18000651d  jmp     short loc_18000653D
0x18000651f  mov     r15, [rsp+68h+arg_10]
0x180006527  mov     r12, [rsp+68h+arg_8]
0x18000652c  mov     r14, [rsp+68h+arg_0]
0x180006531  mov     esi, [rsp+68h+arg_18]
0x180006538  mov     rbx, [rsp+68h+var_48]
0x18000653d  test    rbx, rbx
0x180006540  jz      short loc_1800065A5
0x180006542  mov     [rbx+40h], r14
0x180006546  lea     rcx, [rbx+10h]; this
0x18000654a  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000654f  mov     esi, eax
0x180006551  lea     r14, [rbx+38h]
0x180006555  test    eax, eax
0x180006557  js      short loc_180006577
0x180006559  mov     byte ptr [r14], 1
0x18000655d  mov     rax, [rbx]
0x180006560  mov     r8, r15
0x180006563  mov     rdx, r12
0x180006566  mov     rcx, rbx
0x180006569  mov     rax, [rax]
0x18000656c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006571  mov     esi, eax
0x180006573  test    eax, eax
0x180006575  jz      short loc_1800065A5
0x180006577  mov     dword ptr [rbx+8], 0C0000001h
0x18000657e  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180006585  mov     [rbx], rax
0x180006588  cmp     byte ptr [r14], 0
0x18000658c  jz      short loc_18000659C
0x18000658e  mov     byte ptr [r14], 0
0x180006592  lea     rcx, [rbx+10h]; lpCriticalSection
0x180006596  call    cs:__imp_DeleteCriticalSection
0x18000659c  mov     rcx, rbx
0x18000659f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800065a5  mov     eax, esi
0x1800065a7  add     rsp, 38h
0x1800065ab  pop     r15
0x1800065ad  pop     r14
0x1800065af  pop     r13
0x1800065b1  pop     r12
0x1800065b3  pop     rsi
0x1800065b4  pop     rbx
0x1800065b5  retn
```
