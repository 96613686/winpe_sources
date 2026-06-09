# ATL::CComCreator<ATL::CComObject<CIRepairUiInfo>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180012704`
- end: `0x180012814`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCIRepairUiInfo@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `272`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800170b0`

## callees

- `0x1800018c0`
- `0x1800058fc`
- `0x180012704`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CIRepairUiInfo>>::CreateInstance(
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
    v6 = operator new(0x50u);
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
      *(_QWORD *)v6 = &ATL::CComObject<CIRepairUiInfo>::`vftable';
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
                 &GUID_9d07e91e_03e1_4786_a38d_9b4f11ac9d1d,
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
0x180012704  mov     [rsp+arg_10], r8
0x180012709  mov     [rsp+arg_8], rdx
0x18001270e  mov     [rsp+arg_0], rcx
0x180012713  push    rsi
0x180012714  push    rdi
0x180012715  push    r14
0x180012717  sub     rsp, 20h
0x18001271b  mov     r14, r8
0x18001271e  test    r8, r8
0x180012721  jnz     short loc_18001272D
0x180012723  mov     eax, 80004003h
0x180012728  jmp     loc_18001280B
0x18001272d  mov     qword ptr [r8], 0
0x180012734  mov     esi, 8007000Eh
0x180012739  mov     dword ptr [rsp+38h+arg_8], esi
0x18001273d  mov     [rsp+38h+arg_0], 0
0x180012746  mov     ecx, 50h ; 'P'; Size
0x18001274b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012750  mov     rdi, rax
0x180012753  test    rdi, rdi
0x180012756  jz      short loc_180012798
0x180012758  mov     dword ptr [rax+8], 0
0x18001275f  xorps   xmm0, xmm0
0x180012762  xor     eax, eax
0x180012764  movups  xmmword ptr [rdi+10h], xmm0
0x180012768  movups  xmmword ptr [rdi+20h], xmm0
0x18001276c  mov     [rdi+30h], rax
0x180012770  mov     [rdi+38h], al
0x180012773  mov     [rdi+40h], rax
0x180012777  mov     [rdi+48h], rax
0x18001277b  lea     rax, ??_7?$CComObject@VCIRepairUiInfo@@@ATL@@6B@; const ATL::CComObject<CIRepairUiInfo>::`vftable'
0x180012782  mov     [rdi], rax
0x180012785  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001278c  mov     rax, [rcx]
0x18001278f  mov     rax, [rax+8]
0x180012793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012798  mov     [rsp+38h+arg_0], rdi
0x18001279d  jmp     short loc_1800127AD
0x18001279f  mov     r14, [rsp+38h+arg_10]
0x1800127a4  mov     esi, dword ptr [rsp+38h+arg_8]
0x1800127a8  mov     rdi, [rsp+38h+arg_0]
0x1800127ad  test    rdi, rdi
0x1800127b0  jz      short loc_180012809
0x1800127b2  lea     rcx, [rdi+10h]; this
0x1800127b6  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800127bb  mov     ecx, eax
0x1800127bd  test    eax, eax
0x1800127bf  js      short loc_1800127C5
0x1800127c1  mov     byte ptr [rdi+38h], 1
0x1800127c5  xor     eax, eax
0x1800127c7  test    ecx, ecx
0x1800127c9  cmovs   eax, ecx
0x1800127cc  xor     esi, esi
0x1800127ce  test    eax, eax
0x1800127d0  cmovs   esi, eax
0x1800127d3  test    esi, esi
0x1800127d5  jnz     short loc_1800127F5
0x1800127d7  mov     rax, [rdi]
0x1800127da  mov     r8, r14
0x1800127dd  lea     rdx, _GUID_9d07e91e_03e1_4786_a38d_9b4f11ac9d1d
0x1800127e4  mov     rcx, rdi
0x1800127e7  mov     rax, [rax]
0x1800127ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127ef  mov     esi, eax
0x1800127f1  test    eax, eax
0x1800127f3  jz      short loc_180012809
0x1800127f5  mov     r8, [rdi]
0x1800127f8  mov     edx, 1
0x1800127fd  mov     rcx, rdi
0x180012800  mov     rax, [r8+50h]
0x180012804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012809  mov     eax, esi
0x18001280b  add     rsp, 20h
0x18001280f  pop     r14
0x180012811  pop     rdi
0x180012812  pop     rsi
0x180012813  retn
```
