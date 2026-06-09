# ATL::CComCreator<ATL::CComObject<CIDiagnosticsWaitHandle>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180012384`
- end: `0x18001249b`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCIDiagnosticsWaitHandle@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `279`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180012e60`
- `0x180014b10`
- `0x1800157e0`

## callees

- `0x1800018c0`
- `0x1800058fc`
- `0x180012384`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CIDiagnosticsWaitHandle>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  unsigned int v5; // esi
  char *v6; // rax
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
    v6 = (char *)operator new(0x50u);
    v7 = v6;
    if ( v6 )
    {
      *((_DWORD *)v6 + 4) = 0;
      *(_OWORD *)(v6 + 24) = 0;
      *(_OWORD *)(v6 + 40) = 0;
      *((_QWORD *)v6 + 7) = 0;
      v6[64] = 0;
      *((_QWORD *)v6 + 9) = 0;
      *(_QWORD *)v6 = &ATL::CComObject<CIDiagnosticsWaitHandle>::`vftable'{for `ATL::IDispatchImpl<IDiagnosticsWaitHandle,&__s_GUID const _GUID_4758e4a5_6f20_4615_bc2c_27580cc00e67,&public: static _GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>'};
      *((_QWORD *)v6 + 1) = &ATL::CComObject<CIDiagnosticsWaitHandle>::`vftable'{for `ISynchronize'};
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
    v8 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v7 + 24));
    if ( v8 >= 0 )
      v7[64] = 1;
    v9 = 0;
    if ( v8 < 0 )
      v9 = v8;
    v5 = 0;
    if ( v9 < 0 )
      v5 = v9;
    if ( v5
      || (v5 = (**(__int64 (__fastcall ***)(_BYTE *, GUID *, _QWORD *))v7)(
                 v7,
                 &GUID_4758e4a5_6f20_4615_bc2c_27580cc00e67,
                 v3)) != 0 )
    {
      (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v7 + 64LL))(v7, 1);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180012384  mov     [rsp+arg_10], r8
0x180012389  mov     [rsp+arg_8], rdx
0x18001238e  mov     [rsp+arg_0], rcx
0x180012393  push    rsi
0x180012394  push    rdi
0x180012395  push    r14
0x180012397  sub     rsp, 20h
0x18001239b  mov     r14, r8
0x18001239e  test    r8, r8
0x1800123a1  jnz     short loc_1800123AD
0x1800123a3  mov     eax, 80004003h
0x1800123a8  jmp     loc_180012492
0x1800123ad  mov     qword ptr [r8], 0
0x1800123b4  mov     esi, 8007000Eh
0x1800123b9  mov     dword ptr [rsp+38h+arg_8], esi
0x1800123bd  mov     [rsp+38h+arg_0], 0
0x1800123c6  mov     ecx, 50h ; 'P'; Size
0x1800123cb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800123d0  mov     rdi, rax
0x1800123d3  test    rdi, rdi
0x1800123d6  jz      short loc_18001241F
0x1800123d8  mov     dword ptr [rax+10h], 0
0x1800123df  xorps   xmm0, xmm0
0x1800123e2  xor     eax, eax
0x1800123e4  movups  xmmword ptr [rdi+18h], xmm0
0x1800123e8  movups  xmmword ptr [rdi+28h], xmm0
0x1800123ec  mov     [rdi+38h], rax
0x1800123f0  mov     [rdi+40h], al
0x1800123f3  mov     [rdi+48h], rax
0x1800123f7  lea     rax, ??_7?$CComObject@VCIDiagnosticsWaitHandle@@@ATL@@6B?$IDispatchImpl@UIDiagnosticsWaitHandle@@$1?_GUID_4758e4a5_6f20_4615_bc2c_27580cc00e67@@3U__s_GUID@@B$1?m_libid@CAtlModule@ATL@@2U_GUID@@A$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CIDiagnosticsWaitHandle>::`vftable'{for `ATL::IDispatchImpl<IDiagnosticsWaitHandle,&__s_GUID const _GUID_4758e4a5_6f20_4615_bc2c_27580cc00e67,&_GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>'}
0x1800123fe  mov     [rdi], rax
0x180012401  lea     rax, ??_7?$CComObject@VCIDiagnosticsWaitHandle@@@ATL@@6BISynchronize@@@; const ATL::CComObject<CIDiagnosticsWaitHandle>::`vftable'{for `ISynchronize'}
0x180012408  mov     [rdi+8], rax
0x18001240c  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180012413  mov     rax, [rcx]
0x180012416  mov     rax, [rax+8]
0x18001241a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001241f  mov     [rsp+38h+arg_0], rdi
0x180012424  jmp     short loc_180012434
0x180012426  mov     r14, [rsp+38h+arg_10]
0x18001242b  mov     esi, dword ptr [rsp+38h+arg_8]
0x18001242f  mov     rdi, [rsp+38h+arg_0]
0x180012434  test    rdi, rdi
0x180012437  jz      short loc_180012490
0x180012439  lea     rcx, [rdi+18h]; this
0x18001243d  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180012442  mov     ecx, eax
0x180012444  test    eax, eax
0x180012446  js      short loc_18001244C
0x180012448  mov     byte ptr [rdi+40h], 1
0x18001244c  xor     eax, eax
0x18001244e  test    ecx, ecx
0x180012450  cmovs   eax, ecx
0x180012453  xor     esi, esi
0x180012455  test    eax, eax
0x180012457  cmovs   esi, eax
0x18001245a  test    esi, esi
0x18001245c  jnz     short loc_18001247C
0x18001245e  mov     rax, [rdi]
0x180012461  mov     r8, r14
0x180012464  lea     rdx, _GUID_4758e4a5_6f20_4615_bc2c_27580cc00e67
0x18001246b  mov     rcx, rdi
0x18001246e  mov     rax, [rax]
0x180012471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012476  mov     esi, eax
0x180012478  test    eax, eax
0x18001247a  jz      short loc_180012490
0x18001247c  mov     r8, [rdi]
0x18001247f  mov     edx, 1
0x180012484  mov     rcx, rdi
0x180012487  mov     rax, [r8+40h]
0x18001248b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012490  mov     eax, esi
0x180012492  add     rsp, 20h
0x180012496  pop     r14
0x180012498  pop     rdi
0x180012499  pop     rsi
0x18001249a  retn
```
