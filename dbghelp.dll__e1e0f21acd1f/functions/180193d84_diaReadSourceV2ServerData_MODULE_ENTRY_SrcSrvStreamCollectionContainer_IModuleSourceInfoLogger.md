# diaReadSourceV2ServerData(_MODULE_ENTRY *,SrcSrvStreamCollectionContainer *,IModuleSourceInfoLogger *)

- ea: `0x180193d84`
- end: `0x1801940eb`
- name: `?diaReadSourceV2ServerData@@YAHPEAU_MODULE_ENTRY@@PEAVSrcSrvStreamCollectionContainer@@PEAVIModuleSourceInfoLogger@@@Z`
- size: `871`
- prototype: `__int64 __fastcall(struct _MODULE_ENTRY *, struct SrcSrvStreamCollectionContainer *, struct IModuleSourceInfoLogger *)`
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18019b240`
- `0x18019f648`

## callees

- `0x180016da4`
- `0x180022bb0`
- `0x180189cf4`
- `0x18018b378`
- `0x18018b9e4`
- `0x18018bba4`
- `0x18018bee4`
- `0x18018bfb4`
- `0x180193b28`
- `0x180193d84`
- `0x1801d6350`
- `0x180205010`

## string_xrefs

- `0x180193e94`: `Succeeded reading SourceLink stream via consolidated API.\n`
- `0x180193eb0`: `SourceStream_SourceLink`
- `0x18019407b`: `SourceStream_SourceLink`
- `0x180193ee5`: `Succeeded reading SourceLink stream.\n`
- `0x180193f76`: `Failed reading SourceLink stream via ISvcLegacySourceLinkV2Index.\n`
- `0x180193fd1`: `Failed reading SourceLink stream via ISvcLegacySourceLinkV2Index - failed to read stream data for index %d.\n`
- `0x180194062`: `Succeeded reading SourceLink stream via ISvcLegacySourceLinkV2Index.\n`
- `0x1801940a5`: `Failed reading SourceLink stream via ISvcLegacySourceLinkV2Index - error reading number of streams.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall diaReadSourceV2ServerData(
        struct _MODULE_ENTRY *a1,
        struct SrcSrvStreamCollectionContainer *a2,
        struct IModuleSourceInfoLogger *a3)
{
  struct IModuleSourceInfoLogger *v3; // rdi
  struct _MODULE_ENTRY *v4; // rsi
  struct SrcSrvStreamCollectionContainer *v5; // r13
  _QWORD *v6; // r15
  unsigned int v7; // ebx
  _QWORD *v9; // r12
  const wchar_t *v10; // r8
  unsigned int SourceStreamV2; // r14d
  int (__fastcall ***v12)(_QWORD, GUID *, struct ISvcLegacySourceLinkV2Index **); // rcx
  unsigned int i; // r14d
  _QWORD *v14; // r8
  struct SrcSrvStreamCollectionContainer *v15; // rax
  unsigned int v16; // [rsp+20h] [rbp-D8h] BYREF
  unsigned int v17; // [rsp+24h] [rbp-D4h]
  struct ISvcLegacySourceLinkV2Index *v18; // [rsp+28h] [rbp-D0h] BYREF
  __int128 v19; // [rsp+30h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+40h] [rbp-B8h]
  struct IModuleSourceInfoLogger *v21; // [rsp+48h] [rbp-B0h]
  struct _MODULE_ENTRY *v22; // [rsp+50h] [rbp-A8h]
  struct SrcSrvStreamCollectionContainer *v23; // [rsp+58h] [rbp-A0h]
  struct SrcSrvStreamCollectionContainer *v24; // [rsp+60h] [rbp-98h] BYREF
  struct _MODULE_ENTRY *v25; // [rsp+68h] [rbp-90h] BYREF
  struct SrcSrvStreamCollectionContainer *v26; // [rsp+70h] [rbp-88h]
  _QWORD *v27; // [rsp+80h] [rbp-78h]
  _QWORD *v28; // [rsp+88h] [rbp-70h]
  __int64 v29; // [rsp+90h] [rbp-68h]
  _QWORD v30[4]; // [rsp+98h] [rbp-60h] BYREF

  v29 = -2;
  v3 = a3;
  v23 = a2;
  v4 = a1;
  v26 = a2;
  v22 = a1;
  v5 = a2;
  v21 = a3;
  SrcSrvStreamCollectionContainer::Clear(a2);
  v6 = (_QWORD *)*((_QWORD *)v4 + 2434);
  v27 = v6;
  v7 = 0;
  if ( !v6 )
  {
    (*(void (__fastcall **)(struct IModuleSourceInfoLogger *, struct _MODULE_ENTRY *, const wchar_t *))(*(_QWORD *)v3 + 16LL))(
      v3,
      v4,
      L"Error: DIA is not initialized.\n");
    return 0;
  }
  v9 = v6 + 1;
  v28 = v6 + 1;
  if ( v6[1] )
  {
    try
    {
      v24 = v5;
      v25 = v4;
      *(_QWORD *)&v19 = &v24;
      *((_QWORD *)&v19 + 1) = &v25;
      SourceStreamV2 = (int)Debugger::Utils::ConvertException__lambda_d97637272c11efd477a86e84c18ac832___(&v19) >= 0;
      v17 = SourceStreamV2;
    }
    catch ( ... )
    {
      (*(void (__fastcall **)(struct IModuleSourceInfoLogger *, struct _MODULE_ENTRY *, const wchar_t *))(*(_QWORD *)v21 + 16LL))(
        v21,
        v22,
        L"Error: Exception when diaReadSourceStreamV2ViaConsolidatedEnumApi.\n");
      v7 = 0;
      SourceStreamV2 = v17;
      v23 = v26;
      v4 = v22;
      v5 = v26;
      v3 = v21;
      v6 = v27;
      v9 = v28;
    }
    if ( SourceStreamV2 )
    {
      v10 = L"Succeeded reading SourceLink stream via consolidated API.\n";
LABEL_8:
      (*(void (__fastcall **)(struct IModuleSourceInfoLogger *, struct _MODULE_ENTRY *, const wchar_t *))(*(_QWORD *)v3 + 8LL))(
        v3,
        v4,
        v10);
      (*(void (__fastcall **)(struct IModuleSourceInfoLogger *, struct _MODULE_ENTRY *, const wchar_t *))(*(_QWORD *)v3 + 24LL))(
        v3,
        v4,
        L"SourceStream_SourceLink");
      return SourceStreamV2;
    }
  }
  if ( *v6 )
  {
    SourceStreamV2 = diaReadSourceStreamV2(v4, v5);
    if ( SourceStreamV2 )
    {
      v10 = L"Succeeded reading SourceLink stream.\n";
      goto LABEL_8;
    }
  }
  if ( !*v9 )
    return 0;
  v18 = 0;
  v16 = 0;
  v12 = (int (__fastcall ***)(_QWORD, GUID *, struct ISvcLegacySourceLinkV2Index **))v6[2];
  if ( v12 && (**v12)(v12, &GUID_2946e095_f0d2_42d0_ae3e_8eeaffc7ee39, &v18) >= 0 )
  {
    if ( (*(int (__fastcall **)(struct ISvcLegacySourceLinkV2Index *, unsigned int *))(*(_QWORD *)v18 + 24LL))(
           v18,
           &v16) >= 0
      && v16 )
    {
      DWORD2(v19) = 0;
      *(_QWORD *)&v19 = 0;
      v20 = 0;
      if ( !(unsigned int)SrcSrvStreamCollectionContainer::InitializeCollection(
                            (SrcSrvStreamCollectionContainer *)&v19,
                            v16) )
      {
        (*(void (__fastcall **)(struct IModuleSourceInfoLogger *, struct _MODULE_ENTRY *, const wchar_t *))(*(_QWORD *)v3 + 16LL))(
          v3,
          v4,
          L"Failed reading SourceLink stream via ISvcLegacySourceLinkV2Index.\n");
        SrcSrvStreamCollectionContainer::Clear((SrcSrvStreamCollectionContainer *)&v19);
        ATL::CComPtr<IDiaSymbol>::~CComPtr<IDiaSymbol>(&v18);
        return 0;
      }
      for ( i = 0; ; ++i )
      {
        if ( i >= v16 )
        {
          SrcSrvStreamCollectionContainer::UpdateTotalStreamSize((SrcSrvStreamCollectionContainer *)&v19);
          v15 = v23;
          *(_OWORD *)v23 = v19;
          *((_QWORD *)v15 + 2) = v20;
          *(_QWORD *)&v19 = 0;
          DWORD2(v19) = 0;
          v20 = 0;
          (*(void (__fastcall **)(struct IModuleSourceInfoLogger *, struct _MODULE_ENTRY *, const wchar_t *))(*(_QWORD *)v3 + 8LL))(
            v3,
            v4,
            L"Succeeded reading SourceLink stream via ISvcLegacySourceLinkV2Index.\n");
          (*(void (__fastcall **)(struct IModuleSourceInfoLogger *, struct _MODULE_ENTRY *, const wchar_t *))(*(_QWORD *)v3 + 24LL))(
            v3,
            v4,
            L"SourceStream_SourceLink");
          v7 = 1;
          goto LABEL_28;
        }
        if ( (int)ReadStreamData(v18, i, (struct SrcSrvSrcStreamT *const)(v19 + 16LL * i)) < 0 )
          break;
      }
      try
      {
        FormatStdWString(
          v30,
          L"Failed reading SourceLink stream via ISvcLegacySourceLinkV2Index - failed to read stream data for index %d.\n",
          i);
        v14 = v30;
        if ( v30[3] > 7u )
          v14 = (_QWORD *)v30[0];
        (*(void (__fastcall **)(struct IModuleSourceInfoLogger *, struct _MODULE_ENTRY *, _QWORD *))(*(_QWORD *)v3 + 16LL))(
          v3,
          v4,
          v14);
        std::wstring::_Tidy_deallocate(v30);
      }
      catch ( ... )
      {
        (*(void (__fastcall **)(struct IModuleSourceInfoLogger *, struct _MODULE_ENTRY *, const wchar_t *))(*(_QWORD *)v21 + 16LL))(
          v21,
          v22,
          L"Failed reading SourceLink stream via ISvcLegacySourceLinkV2Index - failed to read stream data for current index.\n");
        v7 = 0;
      }
LABEL_28:
      SrcSrvStreamCollectionContainer::Clear((SrcSrvStreamCollectionContainer *)&v19);
    }
    else
    {
      (*(void (__fastcall **)(struct IModuleSourceInfoLogger *, struct _MODULE_ENTRY *, const wchar_t *))(*(_QWORD *)v3 + 16LL))(
        v3,
        v4,
        L"Failed reading SourceLink stream via ISvcLegacySourceLinkV2Index - error reading number of streams.\n");
    }
  }
  ATL::CComPtr<IDiaSymbol>::~CComPtr<IDiaSymbol>(&v18);
  return v7;
}

```

## disassembly

```asm
0x180193d84  mov     rax, rsp
0x180193d87  push    rbx
0x180193d88  push    rsi
0x180193d89  push    rdi
0x180193d8a  push    r12
0x180193d8c  push    r13
0x180193d8e  push    r14
0x180193d90  push    r15
0x180193d92  sub     rsp, 0C0h
0x180193d99  mov     qword ptr [rax-68h], 0FFFFFFFFFFFFFFFEh
0x180193da1  mov     rax, cs:__security_cookie
0x180193da8  xor     rax, rsp
0x180193dab  mov     [rsp+0F8h+var_40], rax
0x180193db3  mov     rdi, r8
0x180193db6  mov     [rsp+0F8h+var_A0], rdx
0x180193dbb  mov     rsi, rcx
0x180193dbe  mov     [rsp+0F8h+var_88], rdx
0x180193dc3  mov     [rsp+0F8h+var_A8], rcx
0x180193dc8  mov     r13, rdx
0x180193dcb  mov     [rsp+0F8h+var_B0], r8
0x180193dd0  mov     rcx, rdx; this
0x180193dd3  call    ?Clear@SrcSrvStreamCollectionContainer@@QEAAXXZ; SrcSrvStreamCollectionContainer::Clear(void)
0x180193dd8  mov     r15, [rsi+4C10h]
0x180193ddf  mov     [rsp+0F8h+var_78], r15
0x180193de7  xor     ebx, ebx
0x180193de9  test    r15, r15
0x180193dec  jnz     short loc_180193E0E
0x180193dee  mov     rax, [rdi]
0x180193df1  lea     r8, aErrorDiaIsNotI; "Error: DIA is not initialized.\n"
0x180193df8  mov     rdx, rsi
0x180193dfb  mov     rcx, rdi
0x180193dfe  mov     rax, [rax+10h]
0x180193e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193e07  xor     eax, eax
0x180193e09  jmp     loc_1801940C8
0x180193e0e  lea     r12, [r15+8]
0x180193e12  mov     [rsp+0F8h+var_70], r12
0x180193e1a  cmp     [r12], rbx
0x180193e1e  jz      loc_180193ECE
0x180193e24  mov     [rsp+0F8h+var_D4], ebx
0x180193e28  mov     [rsp+0F8h+var_98], r13
0x180193e2d  mov     [rsp+0F8h+var_90], rsi
0x180193e32  lea     rax, [rsp+0F8h+var_98]
0x180193e37  mov     qword ptr [rsp+0F8h+var_C8], rax
0x180193e3c  lea     rax, [rsp+0F8h+var_90]
0x180193e41  mov     qword ptr [rsp+0F8h+var_C8+8], rax
0x180193e46  lea     rcx, [rsp+0F8h+var_C8]
0x180193e4b  call    Debugger__Utils__ConvertException__lambda_d97637272c11efd477a86e84c18ac832___
0x180193e50  mov     r14d, eax
0x180193e53  not     r14d
0x180193e56  shr     r14d, 1Fh
0x180193e5a  mov     [rsp+0F8h+var_D4], r14d
0x180193e5f  jmp     short loc_180193E8F
0x180193e61  xor     ebx, ebx
0x180193e63  mov     r14d, [rsp+0F8h+var_D4]
0x180193e68  mov     rax, [rsp+0F8h+var_88]
0x180193e6d  mov     [rsp+0F8h+var_A0], rax
0x180193e72  mov     rsi, [rsp+0F8h+var_A8]
0x180193e77  mov     r13, rax
0x180193e7a  mov     rdi, [rsp+0F8h+var_B0]
0x180193e7f  mov     r15, [rsp+0F8h+var_78]
0x180193e87  mov     r12, [rsp+0F8h+var_70]
0x180193e8f  test    r14d, r14d
0x180193e92  jz      short loc_180193ECE
0x180193e94  lea     r8, aSucceededReadi; "Succeeded reading SourceLink stream via"...
0x180193e9b  mov     rax, [rdi]
0x180193e9e  mov     rdx, rsi
0x180193ea1  mov     rcx, rdi
0x180193ea4  mov     rax, [rax+8]
0x180193ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193ead  mov     rax, [rdi]
0x180193eb0  lea     r8, aSourcestreamSo; "SourceStream_SourceLink"
0x180193eb7  mov     rdx, rsi
0x180193eba  mov     rcx, rdi
0x180193ebd  mov     rax, [rax+18h]
0x180193ec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193ec6  mov     eax, r14d
0x180193ec9  jmp     loc_1801940C8
0x180193ece  cmp     [r15], rbx
0x180193ed1  jz      short loc_180193EEE
0x180193ed3  mov     rdx, r13; struct SrcSrvStreamCollectionContainer *
0x180193ed6  mov     rcx, rsi; struct _MODULE_ENTRY *
0x180193ed9  call    ?diaReadSourceStreamV2@@YAHPEAU_MODULE_ENTRY@@QEAVSrcSrvStreamCollectionContainer@@@Z; diaReadSourceStreamV2(_MODULE_ENTRY *,SrcSrvStreamCollectionContainer * const)
0x180193ede  mov     r14d, eax
0x180193ee1  test    eax, eax
0x180193ee3  jz      short loc_180193EEE
0x180193ee5  lea     r8, aSucceededReadi_3; "Succeeded reading SourceLink stream.\n"
0x180193eec  jmp     short loc_180193E9B
0x180193eee  cmp     [r12], rbx
0x180193ef2  jz      loc_180193E07
0x180193ef8  mov     [rsp+0F8h+var_D0], rbx
0x180193efd  mov     [rsp+0F8h+var_D8], ebx
0x180193f01  mov     rcx, [r15+10h]
0x180193f05  test    rcx, rcx
0x180193f08  jz      loc_1801940BC
0x180193f0e  mov     rax, [rcx]
0x180193f11  lea     r8, [rsp+0F8h+var_D0]
0x180193f16  lea     rdx, _GUID_2946e095_f0d2_42d0_ae3e_8eeaffc7ee39
0x180193f1d  mov     rax, [rax]
0x180193f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193f25  test    eax, eax
0x180193f27  js      loc_1801940BC
0x180193f2d  mov     rcx, [rsp+0F8h+var_D0]
0x180193f32  mov     rax, [rcx]
0x180193f35  lea     rdx, [rsp+0F8h+var_D8]
0x180193f3a  mov     rax, [rax+18h]
0x180193f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193f43  test    eax, eax
0x180193f45  js      loc_1801940A2
0x180193f4b  mov     edx, [rsp+0F8h+var_D8]; unsigned int
0x180193f4f  test    edx, edx
0x180193f51  jz      loc_1801940A2
0x180193f57  mov     dword ptr [rsp+0F8h+var_C8+8], ebx
0x180193f5b  mov     qword ptr [rsp+0F8h+var_C8], rbx
0x180193f60  mov     [rsp+0F8h+var_B8], rbx
0x180193f65  lea     rcx, [rsp+0F8h+var_C8]; this
0x180193f6a  call    ?InitializeCollection@SrcSrvStreamCollectionContainer@@QEAAHI@Z; SrcSrvStreamCollectionContainer::InitializeCollection(uint)
0x180193f6f  test    eax, eax
0x180193f71  jnz     short loc_180193FA7
0x180193f73  mov     rax, [rdi]
0x180193f76  lea     r8, aFailedReadingS_2; "Failed reading SourceLink stream via IS"...
0x180193f7d  mov     rdx, rsi
0x180193f80  mov     rcx, rdi
0x180193f83  mov     rax, [rax+10h]
0x180193f87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193f8c  nop
0x180193f8d  lea     rcx, [rsp+0F8h+var_C8]; this
0x180193f92  call    ?Clear@SrcSrvStreamCollectionContainer@@QEAAXXZ; SrcSrvStreamCollectionContainer::Clear(void)
0x180193f97  nop
0x180193f98  lea     rcx, [rsp+0F8h+var_D0]
0x180193f9d  call    ??1?$CComPtr@UIDiaSymbol@@@ATL@@QEAA@XZ; ATL::CComPtr<IDiaSymbol>::~CComPtr<IDiaSymbol>(void)
0x180193fa2  jmp     loc_180193E07
0x180193fa7  mov     r14d, ebx
0x180193faa  cmp     r14d, [rsp+0F8h+var_D8]
0x180193faf  jnb     short loc_18019402F
0x180193fb1  mov     r8d, r14d
0x180193fb4  shl     r8, 4
0x180193fb8  add     r8, qword ptr [rsp+0F8h+var_C8]; struct SrcSrvSrcStreamT *
0x180193fbd  mov     edx, r14d; unsigned int
0x180193fc0  mov     rcx, [rsp+0F8h+var_D0]; struct ISvcLegacySourceLinkV2Index *
0x180193fc5  call    ?ReadStreamData@@YAJQEAUISvcLegacySourceLinkV2Index@@KQEAUSrcSrvSrcStreamT@@@Z; ReadStreamData(ISvcLegacySourceLinkV2Index * const,ulong,SrcSrvSrcStreamT * const)
0x180193fca  test    eax, eax
0x180193fcc  jns     short loc_180194027
0x180193fce  mov     r8d, r14d
0x180193fd1  lea     rdx, aFailedReadingS_4; "Failed reading SourceLink stream via IS"...
0x180193fd8  lea     rcx, [rsp+0F8h+var_60]
0x180193fe0  call    ?FormatStdWString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBGZZ; FormatStdWString(ushort const * const,...)
0x180193fe5  nop
0x180193fe6  mov     rax, [rdi]
0x180193fe9  lea     r8, [rsp+0F8h+var_60]
0x180193ff1  cmp     [rsp+0F8h+var_48], 7
0x180193ffa  cmova   r8, [rsp+0F8h+var_60]
0x180194003  mov     rdx, rsi
0x180194006  mov     rcx, rdi
0x180194009  mov     rax, [rax+10h]
0x18019400d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180194012  nop
0x180194013  lea     rcx, [rsp+0F8h+var_60]
0x18019401b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180194020  nop
0x180194021  jmp     short loc_180194096
0x180194023  xor     ebx, ebx
0x180194025  jmp     short loc_180194096
0x180194027  inc     r14d
0x18019402a  jmp     loc_180193FAA
0x18019402f  lea     rcx, [rsp+0F8h+var_C8]; this
0x180194034  call    ?UpdateTotalStreamSize@SrcSrvStreamCollectionContainer@@QEAAXXZ; SrcSrvStreamCollectionContainer::UpdateTotalStreamSize(void)
0x180194039  movups  xmm0, [rsp+0F8h+var_C8]
0x18019403e  mov     rax, [rsp+0F8h+var_A0]
0x180194043  movups  xmmword ptr [rax], xmm0
0x180194046  movsd   xmm1, [rsp+0F8h+var_B8]
0x18019404c  movsd   qword ptr [rax+10h], xmm1
0x180194051  mov     qword ptr [rsp+0F8h+var_C8], rbx
0x180194056  mov     dword ptr [rsp+0F8h+var_C8+8], ebx
0x18019405a  mov     [rsp+0F8h+var_B8], rbx
0x18019405f  mov     rax, [rdi]
0x180194062  lea     r8, aSucceededReadi_2; "Succeeded reading SourceLink stream via"...
0x180194069  mov     rdx, rsi
0x18019406c  mov     rcx, rdi
0x18019406f  mov     rax, [rax+8]
0x180194073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180194078  mov     rax, [rdi]
0x18019407b  lea     r8, aSourcestreamSo; "SourceStream_SourceLink"
0x180194082  mov     rdx, rsi
0x180194085  mov     rcx, rdi
0x180194088  mov     rax, [rax+18h]
0x18019408c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180194091  mov     ebx, 1
0x180194096  lea     rcx, [rsp+0F8h+var_C8]; this
0x18019409b  call    ?Clear@SrcSrvStreamCollectionContainer@@QEAAXXZ; SrcSrvStreamCollectionContainer::Clear(void)
0x1801940a0  jmp     short loc_1801940BC
0x1801940a2  mov     rax, [rdi]
0x1801940a5  lea     r8, aFailedReadingS_5; "Failed reading SourceLink stream via IS"...
0x1801940ac  mov     rdx, rsi
0x1801940af  mov     rcx, rdi
0x1801940b2  mov     rax, [rax+10h]
0x1801940b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801940bb  nop
0x1801940bc  lea     rcx, [rsp+0F8h+var_D0]
0x1801940c1  call    ??1?$CComPtr@UIDiaSymbol@@@ATL@@QEAA@XZ; ATL::CComPtr<IDiaSymbol>::~CComPtr<IDiaSymbol>(void)
0x1801940c6  mov     eax, ebx
0x1801940c8  mov     rcx, [rsp+0F8h+var_40]
0x1801940d0  xor     rcx, rsp; StackCookie
0x1801940d3  call    __security_check_cookie
0x1801940d8  add     rsp, 0C0h
0x1801940df  pop     r15
0x1801940e1  pop     r14
0x1801940e3  pop     r13
0x1801940e5  pop     r12
0x1801940e7  pop     rdi
0x1801940e8  pop     rsi
0x1801940e9  pop     rbx
0x1801940ea  retn
```
