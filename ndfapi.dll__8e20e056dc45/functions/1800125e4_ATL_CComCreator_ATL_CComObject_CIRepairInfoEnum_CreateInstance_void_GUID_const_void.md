# ATL::CComCreator<ATL::CComObject<CIRepairInfoEnum>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800125e4`
- end: `0x1800126fc`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCIRepairInfoEnum@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `280`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180016c40`

## callees

- `0x1800018c0`
- `0x1800058fc`
- `0x1800125e4`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CIRepairInfoEnum>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  unsigned int v5; // esi
  _BYTE *v6; // rax
  _BYTE *v7; // rdi
  int v8; // ecx
  int v9; // eax
  _BYTE *v10; // [rsp+40h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v5 = -2147024882;
    v6 = operator new(0x60u);
    v7 = v6;
    if ( v6 )
    {
      *((_DWORD *)v6 + 2) = 0;
      *((_OWORD *)v6 + 1) = 0;
      *((_OWORD *)v6 + 2) = 0;
      *((_QWORD *)v6 + 6) = 0;
      v6[56] = 0;
      *((_QWORD *)v6 + 8) = 0;
      *((_QWORD *)v6 + 9) = 0;
      *((_QWORD *)v6 + 10) = 0;
      *((_QWORD *)v6 + 11) = 0;
      *(_QWORD *)v6 = &ATL::CComObject<CIRepairInfoEnum>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
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
    v8 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v7 + 16));
    if ( v8 >= 0 )
      v7[56] = 1;
    v9 = 0;
    if ( v8 < 0 )
      v9 = v8;
    v5 = 0;
    if ( v9 < 0 )
      v5 = v9;
    if ( v5
      || (v5 = (**(__int64 (__fastcall ***)(_BYTE *, GUID *, _QWORD *))v7)(
                 v7,
                 &GUID_cbfdf96c_fb17_43dd_bc0f_03ca57914435,
                 v3)) != 0 )
    {
      (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v7 + 80LL))(v7, 1);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800125e4  mov     [rsp+arg_10], r8
0x1800125e9  mov     [rsp+arg_8], rdx
0x1800125ee  mov     [rsp+arg_0], rcx
0x1800125f3  push    rsi
0x1800125f4  push    rdi
0x1800125f5  push    r14
0x1800125f7  sub     rsp, 20h
0x1800125fb  mov     r14, r8
0x1800125fe  test    r8, r8
0x180012601  jnz     short loc_18001260D
0x180012603  mov     eax, 80004003h
0x180012608  jmp     loc_1800126F3
0x18001260d  mov     qword ptr [r8], 0
0x180012614  mov     esi, 8007000Eh
0x180012619  mov     dword ptr [rsp+38h+arg_8], esi
0x18001261d  mov     [rsp+38h+arg_0], 0
0x180012626  mov     ecx, 60h ; '`'; Size
0x18001262b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012630  mov     rdi, rax
0x180012633  test    rdi, rdi
0x180012636  jz      short loc_180012680
0x180012638  mov     dword ptr [rax+8], 0
0x18001263f  xorps   xmm0, xmm0
0x180012642  xor     eax, eax
0x180012644  movups  xmmword ptr [rdi+10h], xmm0
0x180012648  movups  xmmword ptr [rdi+20h], xmm0
0x18001264c  mov     [rdi+30h], rax
0x180012650  mov     [rdi+38h], al
0x180012653  mov     [rdi+40h], rax
0x180012657  mov     [rdi+48h], rax
0x18001265b  mov     [rdi+50h], rax
0x18001265f  mov     [rdi+58h], rax
0x180012663  lea     rax, ??_7?$CComObject@VCIRepairInfoEnum@@@ATL@@6B@; const ATL::CComObject<CIRepairInfoEnum>::`vftable'
0x18001266a  mov     [rdi], rax
0x18001266d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180012674  mov     rax, [rcx]
0x180012677  mov     rax, [rax+8]
0x18001267b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012680  mov     [rsp+38h+arg_0], rdi
0x180012685  jmp     short loc_180012695
0x180012687  mov     r14, [rsp+38h+arg_10]
0x18001268c  mov     esi, dword ptr [rsp+38h+arg_8]
0x180012690  mov     rdi, [rsp+38h+arg_0]
0x180012695  test    rdi, rdi
0x180012698  jz      short loc_1800126F1
0x18001269a  lea     rcx, [rdi+10h]; this
0x18001269e  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800126a3  mov     ecx, eax
0x1800126a5  test    eax, eax
0x1800126a7  js      short loc_1800126AD
0x1800126a9  mov     byte ptr [rdi+38h], 1
0x1800126ad  xor     eax, eax
0x1800126af  test    ecx, ecx
0x1800126b1  cmovs   eax, ecx
0x1800126b4  xor     esi, esi
0x1800126b6  test    eax, eax
0x1800126b8  cmovs   esi, eax
0x1800126bb  test    esi, esi
0x1800126bd  jnz     short loc_1800126DD
0x1800126bf  mov     rax, [rdi]
0x1800126c2  mov     r8, r14
0x1800126c5  lea     rdx, _GUID_cbfdf96c_fb17_43dd_bc0f_03ca57914435
0x1800126cc  mov     rcx, rdi
0x1800126cf  mov     rax, [rax]
0x1800126d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126d7  mov     esi, eax
0x1800126d9  test    eax, eax
0x1800126db  jz      short loc_1800126F1
0x1800126dd  mov     r8, [rdi]
0x1800126e0  mov     edx, 1
0x1800126e5  mov     rcx, rdi
0x1800126e8  mov     rax, [r8+50h]
0x1800126ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126f1  mov     eax, esi
0x1800126f3  add     rsp, 20h
0x1800126f7  pop     r14
0x1800126f9  pop     rdi
0x1800126fa  pop     rsi
0x1800126fb  retn
```
