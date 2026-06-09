# ATL::CComCreator<ATL::CComObject<CNDFHelperClassEnum>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006b84`
- end: `0x180006c95`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCNDFHelperClassEnum@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800071d0`

## callees

- `0x1800012e0`
- `0x180006b84`
- `0x1800079f0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CNDFHelperClassEnum>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  unsigned int v5; // esi
  _DWORD *v6; // rax
  _DWORD *v7; // rdi
  int v8; // ecx
  int v9; // eax
  _DWORD *v10; // [rsp+40h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v5 = -2147024882;
    v6 = operator new(0x50u);
    v7 = v6;
    if ( v6 )
    {
      v6[2] = 0;
      *((_OWORD *)v6 + 1) = 0;
      *((_OWORD *)v6 + 2) = 0;
      *((_QWORD *)v6 + 6) = 0;
      *((_BYTE *)v6 + 56) = 0;
      *((_QWORD *)v6 + 8) = 0;
      *((_QWORD *)v6 + 9) = 0;
      *(_QWORD *)v6 = &ATL::CComObject<CNDFHelperClassEnum>::`vftable';
      (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v10 = v7;
  }
  catch ( ... )
  {
    v3 = a3;
    v5 = -2147024882;
    v7 = v10;
  }
  if ( v7 )
  {
    v8 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v7 + 4));
    if ( v8 >= 0 )
      *((_BYTE *)v7 + 56) = 1;
    v9 = 0;
    if ( v8 < 0 )
      v9 = v8;
    v5 = 0;
    if ( v9 < 0 )
      v5 = v9;
    if ( v5
      || (v5 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, _QWORD *))v7)(
                 v7,
                 &GUID_56fc7717_381c_4119_a9e6_8a37b7138d6a,
                 v3)) != 0 )
    {
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v7 + 40LL))(v7, 1);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180006b84  mov     [rsp+arg_10], r8
0x180006b89  mov     [rsp+arg_8], rdx
0x180006b8e  mov     [rsp+arg_0], rcx
0x180006b93  push    rsi
0x180006b94  push    rdi
0x180006b95  push    r14
0x180006b97  sub     rsp, 20h
0x180006b9b  mov     r14, r8
0x180006b9e  test    r8, r8
0x180006ba1  jnz     short loc_180006BAD
0x180006ba3  mov     eax, 80004003h
0x180006ba8  jmp     loc_180006C8B
0x180006bad  mov     qword ptr [r8], 0
0x180006bb4  mov     esi, 8007000Eh
0x180006bb9  mov     dword ptr [rsp+38h+arg_8], esi
0x180006bbd  mov     [rsp+38h+arg_0], 0
0x180006bc6  mov     ecx, 50h ; 'P'; Size
0x180006bcb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006bd0  mov     rdi, rax
0x180006bd3  test    rdi, rdi
0x180006bd6  jz      short loc_180006C18
0x180006bd8  mov     dword ptr [rax+8], 0
0x180006bdf  xorps   xmm0, xmm0
0x180006be2  xor     eax, eax
0x180006be4  movups  xmmword ptr [rdi+10h], xmm0
0x180006be8  movups  xmmword ptr [rdi+20h], xmm0
0x180006bec  mov     [rdi+30h], rax
0x180006bf0  mov     [rdi+38h], al
0x180006bf3  mov     [rdi+40h], rax
0x180006bf7  mov     [rdi+48h], rax
0x180006bfb  lea     rax, ??_7?$CComObject@VCNDFHelperClassEnum@@@ATL@@6B@; const ATL::CComObject<CNDFHelperClassEnum>::`vftable'
0x180006c02  mov     [rdi], rax
0x180006c05  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006c0c  mov     rax, [rcx]
0x180006c0f  mov     rax, [rax+8]
0x180006c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c18  mov     [rsp+38h+arg_0], rdi
0x180006c1d  jmp     short loc_180006C2D
0x180006c1f  mov     r14, [rsp+38h+arg_10]
0x180006c24  mov     esi, dword ptr [rsp+38h+arg_8]
0x180006c28  mov     rdi, [rsp+38h+arg_0]
0x180006c2d  test    rdi, rdi
0x180006c30  jz      short loc_180006C89
0x180006c32  lea     rcx, [rdi+10h]; this
0x180006c36  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180006c3b  mov     ecx, eax
0x180006c3d  test    eax, eax
0x180006c3f  js      short loc_180006C45
0x180006c41  mov     byte ptr [rdi+38h], 1
0x180006c45  xor     eax, eax
0x180006c47  test    ecx, ecx
0x180006c49  cmovs   eax, ecx
0x180006c4c  xor     esi, esi
0x180006c4e  test    eax, eax
0x180006c50  cmovs   esi, eax
0x180006c53  test    esi, esi
0x180006c55  jnz     short loc_180006C75
0x180006c57  mov     rax, [rdi]
0x180006c5a  mov     r8, r14
0x180006c5d  lea     rdx, _GUID_56fc7717_381c_4119_a9e6_8a37b7138d6a
0x180006c64  mov     rcx, rdi
0x180006c67  mov     rax, [rax]
0x180006c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c6f  mov     esi, eax
0x180006c71  test    eax, eax
0x180006c73  jz      short loc_180006C89
0x180006c75  mov     r8, [rdi]
0x180006c78  mov     edx, 1
0x180006c7d  mov     rcx, rdi
0x180006c80  mov     rax, [r8+28h]
0x180006c84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c89  mov     eax, esi
0x180006c8b  add     rsp, 20h
0x180006c8f  pop     r14
0x180006c91  pop     rdi
0x180006c92  pop     rsi
0x180006c93  retn
```
