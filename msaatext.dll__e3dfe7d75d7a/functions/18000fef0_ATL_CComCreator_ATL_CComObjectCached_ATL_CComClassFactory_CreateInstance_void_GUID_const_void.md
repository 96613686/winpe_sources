# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000fef0`
- end: `0x180010030`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `320`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001370`
- `0x18000fef0`
- `0x18001017c`
- `0x180014010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180010011`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010011`
- `KERNEL32!DeleteCriticalSection` at `0x18000fff4`
- `KERNEL32!DeleteCriticalSection` at `0x180010008`
- `KERNEL32!DeleteCriticalSection` at `0x18000fff4`
- `KERNEL32!DeleteCriticalSection` at `0x180010008`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // esi
  char *v8; // rax
  char *v9; // rbx
  int v10; // eax
  _BYTE *v11; // r14

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = (char *)operator new(0x78u);
  v9 = v8;
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
    v10 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 16));
    v11 = v9 + 56;
    if ( v10 >= 0 )
    {
      *v11 = 1;
      v10 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 72));
      if ( v10 >= 0 )
        v9[112] = 1;
    }
    v7 = 0;
    if ( v10 < 0 )
      v7 = v10;
    if ( v7 || (v7 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v9)(v9, a2, a3)) != 0 )
    {
      *((_DWORD *)v9 + 2) = 1;
      *(_QWORD *)v9 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
      if ( v9[112] )
      {
        v9[112] = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 72));
      }
      if ( *v11 )
      {
        *v11 = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
      }
      operator delete(v9);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18000fef0  mov     [rsp+arg_0], rbx
0x18000fef5  mov     [rsp+arg_8], rbp
0x18000fefa  push    rsi
0x18000fefb  push    rdi
0x18000fefc  push    r12
0x18000fefe  push    r14
0x18000ff00  push    r15
0x18000ff02  sub     rsp, 20h
0x18000ff06  mov     r15, r8
0x18000ff09  mov     r12, rdx
0x18000ff0c  mov     rdi, rcx
0x18000ff0f  test    r8, r8
0x18000ff12  jnz     short loc_18000FF1E
0x18000ff14  mov     eax, 80004003h
0x18000ff19  jmp     loc_180010019
0x18000ff1e  mov     ecx, 78h ; 'x'; Size
0x18000ff23  mov     qword ptr [r8], 0
0x18000ff2a  mov     esi, 8007000Eh
0x18000ff2f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ff34  mov     [rsp+48h+arg_10], rax
0x18000ff39  mov     rbx, rax
0x18000ff3c  test    rax, rax
0x18000ff3f  jz      loc_180010017
0x18000ff45  mov     dword ptr [rax+8], 0
0x18000ff4c  xorps   xmm0, xmm0
0x18000ff4f  movups  xmmword ptr [rbx+10h], xmm0
0x18000ff53  xor     eax, eax
0x18000ff55  movups  xmmword ptr [rbx+20h], xmm0
0x18000ff59  mov     [rbx+30h], rax
0x18000ff5d  mov     [rbx+38h], al
0x18000ff60  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x18000ff67  mov     [rbx], rax
0x18000ff6a  xor     eax, eax
0x18000ff6c  movups  xmmword ptr [rbx+48h], xmm0
0x18000ff70  movups  xmmword ptr [rbx+58h], xmm0
0x18000ff74  mov     [rbx+68h], rax
0x18000ff78  mov     [rbx+70h], al
0x18000ff7b  test    rbx, rbx
0x18000ff7e  jz      loc_180010017
0x18000ff84  lea     rcx, [rbx+10h]; this
0x18000ff88  mov     [rbx+40h], rdi
0x18000ff8c  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000ff91  lea     r14, [rbx+38h]
0x18000ff95  lea     rdi, [rbx+48h]
0x18000ff99  test    eax, eax
0x18000ff9b  js      short loc_18000FFB1
0x18000ff9d  mov     rcx, rdi; this
0x18000ffa0  mov     byte ptr [r14], 1
0x18000ffa4  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000ffa9  test    eax, eax
0x18000ffab  js      short loc_18000FFB1
0x18000ffad  mov     byte ptr [rdi+28h], 1
0x18000ffb1  xor     esi, esi
0x18000ffb3  test    eax, eax
0x18000ffb5  cmovs   esi, eax
0x18000ffb8  test    esi, esi
0x18000ffba  jnz     short loc_18000FFD6
0x18000ffbc  mov     rax, [rbx]
0x18000ffbf  mov     r8, r15
0x18000ffc2  mov     rdx, r12
0x18000ffc5  mov     rcx, rbx
0x18000ffc8  mov     rax, [rax]
0x18000ffcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffd0  mov     esi, eax
0x18000ffd2  test    eax, eax
0x18000ffd4  jz      short loc_180010017
0x18000ffd6  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x18000ffdd  mov     dword ptr [rbx+8], 1
0x18000ffe4  mov     [rbx], rax
0x18000ffe7  cmp     byte ptr [rdi+28h], 0
0x18000ffeb  jz      short loc_18000FFFA
0x18000ffed  mov     rcx, rdi; lpCriticalSection
0x18000fff0  mov     byte ptr [rdi+28h], 0
0x18000fff4  call    cs:__imp_DeleteCriticalSection
0x18000fffa  cmp     byte ptr [r14], 0
0x18000fffe  jz      short loc_18001000E
0x180010000  lea     rcx, [rbx+10h]; lpCriticalSection
0x180010004  mov     byte ptr [r14], 0
0x180010008  call    cs:__imp_DeleteCriticalSection
0x18001000e  mov     rcx, rbx
0x180010011  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180010017  mov     eax, esi
0x180010019  mov     rbx, [rsp+48h+arg_0]
0x18001001e  mov     rbp, [rsp+48h+arg_8]
0x180010023  add     rsp, 20h
0x180010027  pop     r15
0x180010029  pop     r14
0x18001002b  pop     r12
0x18001002d  pop     rdi
0x18001002e  pop     rsi
0x18001002f  retn
```
