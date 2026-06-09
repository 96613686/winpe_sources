# CPkgDefToRegistry::OnEnteringSection(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x140050940`
- end: `0x140050e4c`
- name: `?OnEnteringSection@CPkgDefToRegistry@@MEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `1292`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140002650`
- `0x140002c10`
- `0x140002dd0`
- `0x140004950`
- `0x14000fe10`
- `0x140010138`
- `0x1400102a0`
- `0x140014d1c`
- `0x140023824`
- `0x14002fa90`
- `0x140032ea4`
- `0x140033ab0`
- `0x140034b7c`
- `0x140050940`
- `0x140063d70`
- `0x140063d76`

## import_xrefs

- `ADVAPI32!ImpersonateLoggedOnUser` at `0x140050cae`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x140050cae`
- `ADVAPI32!RevertToSelf` at `0x140050cfa`
- `ADVAPI32!RevertToSelf` at `0x140050d67`
- `ADVAPI32!RevertToSelf` at `0x140050cfa`
- `ADVAPI32!RevertToSelf` at `0x140050d67`
- `VCRUNTIME140!wcsstr` at `0x140050a06`
- `VCRUNTIME140!wcsstr` at `0x140050a06`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CPkgDefToRegistry::OnEnteringSection(__int64 a1, const wchar_t **a2)
{
  unsigned int v4; // r15d
  unsigned __int16 **v5; // rax
  unsigned __int16 *v6; // rax
  __int64 v7; // r8
  unsigned __int16 v8; // cx
  int v9; // ebx
  _QWORD *v10; // rdx
  signed int v12; // ebx
  wchar_t *v13; // rax
  __int64 v14; // rax
  struct ATL::IAtlStringMgr *Instance; // rax
  struct ATL::IAtlStringMgr *v16; // rax
  __int64 v17; // rsi
  int v18; // r15d
  __int64 v19; // rax
  __int64 v20; // rdi
  int v21; // r14d
  _QWORD *v22; // rdx
  _QWORD *v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rcx
  struct ATL::IAtlStringMgr *v26; // rax
  int v27; // r15d
  __int64 v28; // rbx
  _QWORD *v29; // r15
  _WORD *v30; // rax
  _WORD *v31; // rbx
  __int64 v32; // rbx
  __int64 v33; // rdx
  _WORD *v34; // rcx
  const void *v35; // rdx
  int v36; // r14d
  size_t v37; // r8
  unsigned int v38; // ebx
  BOOL v39; // r14d
  unsigned __int16 *v40; // r9
  int v41; // eax
  __int64 v42; // rax
  _QWORD *v43; // rdx
  unsigned __int16 *v44; // rdx
  struct _SECURITY_ATTRIBUTES *v45; // [rsp+30h] [rbp-39h]
  unsigned __int16 *v46; // [rsp+40h] [rbp-29h] BYREF
  int v47; // [rsp+48h] [rbp-21h] BYREF
  __int64 v48; // [rsp+50h] [rbp-19h] BYREF
  __int64 v49; // [rsp+58h] [rbp-11h] BYREF
  __int64 v50; // [rsp+60h] [rbp-9h] BYREF
  __int64 v51; // [rsp+68h] [rbp-1h] BYREF
  __int64 v52; // [rsp+70h] [rbp+7h] BYREF
  HKEY v53; // [rsp+78h] [rbp+Fh]
  _QWORD v54[8]; // [rsp+80h] [rbp+17h] BYREF
  __int64 v55; // [rsp+E0h] [rbp+77h] BYREF
  unsigned int v56; // [rsp+E8h] [rbp+7Fh]

  v4 = 0;
  v56 = 0;
  v5 = (unsigned __int16 **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
                              a2,
                              &v55,
                              *(unsigned int *)(qword_14009D608 - 16));
  if ( !qword_14009D608 )
    ATL::AtlThrowImpl(-2147467259);
  v6 = *v5;
  v7 = qword_14009D608 - (_QWORD)v6;
  while ( 1 )
  {
    v8 = *v6;
    if ( *v6 != *(unsigned __int16 *)((char *)v6 + v7) )
      break;
    ++v6;
    if ( !v8 )
    {
      v9 = 0;
      goto LABEL_7;
    }
  }
  v9 = v8 < *(unsigned __int16 *)((char *)v6 + v7) ? -1 : 1;
LABEL_7:
  v10 = (_QWORD *)(v55 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v55 - 24 + 16)) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 8LL))(*v10);
  }
  if ( v9 )
    return 2147942487LL;
  v12 = 0;
  v53 = *(HKEY *)(a1 + 208);
  v49 = 0;
  if ( *((int *)*a2 - 4) >= 0 && (v13 = wcsstr(*a2, L"\\")) != 0 )
    v14 = v13 - *a2;
  else
    LODWORD(v14) = -1;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
    a2,
    &v49,
    (unsigned int)(v14 + 1));
  v46 = 0;
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  v46 = (unsigned __int16 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                           + 24);
  v47 = 0;
  v16 = ATL::CAtlStringMgr::GetInstance();
  if ( !v16 )
    ATL::AtlThrowImpl(-2147467259);
  v50 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v16 + 24LL))(v16) + 24;
  v17 = v49;
  while ( 1 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
      a2,
      &v51,
      *(unsigned int *)(v17 - 16),
      (unsigned int)(*((_DWORD *)*a2 - 4) - *(_DWORD *)(v17 - 16)));
    v18 = v4 | 1;
    v56 = v18;
    v19 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
            &v51,
            &v52,
            L"\\",
            &v47);
    ATL::CSimpleStringT<unsigned short,0>::operator=(&v50, v19);
    v20 = v50;
    v21 = *(_DWORD *)(v50 - 16);
    v22 = (_QWORD *)(v52 - 24);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v52 - 24 + 16), 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v22 + 8LL))(*v22);
    }
    v23 = (_QWORD *)(v51 - 24);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v51 - 24 + 16), 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v23 + 8LL))(*v23);
    }
    if ( !v21 )
      goto LABEL_54;
    v48 = 0;
    v24 = *(_QWORD *)(v20 - 24);
    if ( !v24 || (v25 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 32LL))(v24)) == 0 )
    {
      v26 = ATL::CAtlStringMgr::GetInstance();
      v25 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v26 + 32LL))(v26);
      if ( !v25 )
        ATL::AtlThrowImpl(-2147467259);
    }
    v48 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 24LL))(v25) + 24;
    v27 = v18 | 2;
    v56 = v27;
    LOWORD(v55) = 92;
    ATL::CSimpleStringT<unsigned short,0>::Concatenate(&v48, &v55, 1, v20, *(_DWORD *)(v20 - 16));
    v28 = v48;
    ATL::CSimpleStringT<unsigned short,0>::Append(&v46, v48, *(unsigned int *)(v48 - 16));
    v56 = v27 & 0xFFFFFFFD;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v28 - 24 + 16), 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v28 - 24) + 8LL))(*(_QWORD *)(v28 - 24));
    }
    v29 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::TrimRight(&v46);
    v30 = (_WORD *)*v29;
    v31 = (_WORD *)*v29;
    if ( *(_WORD *)*v29 == 92 )
    {
      do
        ++v31;
      while ( *v31 == 92 );
      if ( v31 != v30 )
      {
        v32 = v31 - v30;
        v33 = *((unsigned int *)v30 - 4);
        if ( (int)v33 < 0 )
          goto LABEL_64;
        if ( ((1 - *((_DWORD *)v30 - 2)) | (*((_DWORD *)v30 - 3) - (int)v33)) < 0 )
        {
          _mm_lfence();
          ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(v29, v33);
        }
        v34 = (_WORD *)*v29;
        v35 = (const void *)(*v29 + 2LL * (int)v32);
        v36 = *(_DWORD *)(*v29 - 16LL) - v32;
        v37 = 2LL * (v36 + 1);
        if ( !v37 )
          goto LABEL_39;
        if ( v34 && v35 )
        {
          if ( 2LL * (*(_DWORD *)(*v29 - 16LL) + 1) >= v37 )
          {
            memmove_0(v34, v35, v37);
LABEL_39:
            if ( v36 < 0 || v36 > *(_DWORD *)(*v29 - 12LL) )
              goto LABEL_64;
            *(_DWORD *)(*v29 - 16LL) = v36;
            *(_WORD *)(*v29 + 2LL * v36) = 0;
            goto LABEL_42;
          }
          *errno_0() = 34;
        }
        else
        {
          *errno_0() = 22;
        }
        invalid_parameter_noinfo_0();
LABEL_64:
        ATL::AtlThrowImpl(-2147024809);
      }
    }
LABEL_42:
    LODWORD(v55) = 0;
    v38 = CLogger::ms_bLoggingOn ? 131103 : 131078;
    v39 = ImpersonateLoggedOnUser(*(HANDLE *)(a1 + 176));
    v41 = ATL::CRegKey::Create(
            (ATL::CRegKey *)(a1 + 216),
            v53,
            v46,
            v40,
            *(_DWORD *)(a1 + 240),
            v38,
            v45,
            (unsigned int *)&v55);
    v12 = (unsigned __int16)v41 | 0x80070000;
    if ( v41 <= 0 )
      v12 = v41;
    if ( v12 < 0 )
      break;
    if ( v39 )
      RevertToSelf();
    v4 = v56;
    if ( (_DWORD)v55 == 1 )
    {
      _mm_lfence();
      v42 = ATL::operator+(v54, &v49, &v46);
      v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 64LL))(a1, v42);
      v43 = (_QWORD *)(v54[0] - 24LL);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v54[0] - 24LL + 16), 0xFFFFFFFF) <= 1 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v43 + 8LL))(*v43);
      }
      if ( v12 < 0 )
        goto LABEL_54;
      v4 = v56;
    }
  }
  if ( v39 )
    RevertToSelf();
LABEL_54:
  if ( _InterlockedDecrement((volatile signed __int32 *)(v20 - 24 + 16)) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v20 - 24) + 8LL))(*(_QWORD *)(v20 - 24));
  }
  v44 = v46 - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)v46 - 2) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v44 + 8LL))(*(_QWORD *)v44);
  }
  if ( _InterlockedDecrement((volatile signed __int32 *)(v17 - 24 + 16)) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v17 - 24) + 8LL))(*(_QWORD *)(v17 - 24));
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140050940  mov     [rsp-8+arg_0], rbx
0x140050945  push    rbp
0x140050946  push    rsi
0x140050947  push    rdi
0x140050948  push    r12
0x14005094a  push    r13
0x14005094c  push    r14
0x14005094e  push    r15
0x140050950  lea     rbp, [rsp-27h]
0x140050955  sub     rsp, 90h
0x14005095c  mov     r12, rdx
0x14005095f  mov     r13, rcx
0x140050962  xor     edi, edi
0x140050964  mov     r15d, edi
0x140050967  mov     [rbp+57h+arg_18], edi
0x14005096a  mov     r8, cs:qword_14009D608
0x140050971  mov     r8d, [r8-10h]
0x140050975  lea     rdx, [rbp+57h+arg_10]
0x140050979  mov     rcx, r12
0x14005097c  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x140050981  mov     r8, cs:qword_14009D608
0x140050988  test    r8, r8
0x14005098b  jz      loc_140050E25
0x140050991  mov     rax, [rax]
0x140050994  sub     r8, rax
0x140050997  movzx   ecx, word ptr [rax]
0x14005099a  cmp     cx, [rax+r8]
0x14005099f  jnz     short loc_1400509AE
0x1400509a1  add     rax, 2
0x1400509a5  test    cx, cx
0x1400509a8  jnz     short loc_140050997
0x1400509aa  mov     ebx, edi
0x1400509ac  jmp     short loc_1400509B3
0x1400509ae  sbb     ebx, ebx
0x1400509b0  or      ebx, 1
0x1400509b3  mov     rdx, [rbp+57h+arg_10]
0x1400509b7  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400509bb  or      esi, 0FFFFFFFFh
0x1400509be  mov     eax, esi
0x1400509c0  lock xadd [rdx+10h], eax
0x1400509c5  add     eax, esi
0x1400509c7  test    eax, eax
0x1400509c9  jg      short loc_1400509D7
0x1400509cb  lfence
0x1400509ce  mov     rcx, [rdx]
0x1400509d1  mov     rax, [rcx]
0x1400509d4  call    qword ptr [rax+8]
0x1400509d7  test    ebx, ebx
0x1400509d9  jz      short loc_1400509E5
0x1400509db  mov     eax, 80070057h
0x1400509e0  jmp     loc_140050DD0
0x1400509e5  mov     ebx, edi
0x1400509e7  mov     rax, [r13+0D0h]
0x1400509ee  mov     [rbp+57h+var_48], rax
0x1400509f2  mov     [rbp+57h+var_68], rdi
0x1400509f6  mov     rcx, [r12]; Str
0x1400509fa  cmp     [rcx-10h], edi
0x1400509fd  jl      short loc_140050A11
0x1400509ff  lea     rdx, SubBlock; "\\"
0x140050a06  call    cs:__imp_wcsstr
0x140050a0c  test    rax, rax
0x140050a0f  jnz     short loc_140050A15
0x140050a11  mov     eax, esi
0x140050a13  jmp     short loc_140050A1C
0x140050a15  sub     rax, [r12]
0x140050a19  sar     rax, 1
0x140050a1c  lea     r8d, [rax+1]
0x140050a20  lea     rdx, [rbp+57h+var_68]
0x140050a24  mov     rcx, r12
0x140050a27  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x140050a2c  nop
0x140050a2d  mov     [rbp+57h+var_80], rdi
0x140050a31  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140050a36  mov     rcx, rax
0x140050a39  test    rax, rax
0x140050a3c  jz      loc_140050E33
0x140050a42  mov     rax, [rax]
0x140050a45  call    qword ptr [rax+18h]
0x140050a48  add     rax, 18h
0x140050a4c  mov     [rbp+57h+var_80], rax
0x140050a50  mov     [rbp+57h+var_78], edi
0x140050a53  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140050a58  mov     rcx, rax
0x140050a5b  test    rax, rax
0x140050a5e  jz      loc_140050E41
0x140050a64  mov     rax, [rax]
0x140050a67  call    qword ptr [rax+18h]
0x140050a6a  add     rax, 18h
0x140050a6e  mov     [rbp+57h+var_60], rax
0x140050a72  mov     rsi, [rbp+57h+var_68]
0x140050a76  mov     r8d, [rsi-10h]
0x140050a7a  mov     rax, [r12]
0x140050a7e  mov     r9d, [rax-10h]
0x140050a82  sub     r9d, r8d
0x140050a85  lea     rdx, [rbp+57h+var_58]
0x140050a89  mov     rcx, r12
0x140050a8c  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x140050a91  or      r15d, 1
0x140050a95  mov     [rbp+57h+arg_18], r15d
0x140050a99  lea     r9, [rbp+57h+var_78]
0x140050a9d  lea     r8, SubBlock; "\\"
0x140050aa4  lea     rdx, [rbp+57h+var_50]
0x140050aa8  lea     rcx, [rbp+57h+var_58]
0x140050aac  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x140050ab1  nop
0x140050ab2  mov     rdx, rax
0x140050ab5  lea     rcx, [rbp+57h+var_60]
0x140050ab9  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140050abe  mov     rdi, [rbp+57h+var_60]
0x140050ac2  mov     r14d, [rdi-10h]
0x140050ac6  mov     rdx, [rbp+57h+var_50]
0x140050aca  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140050ace  or      eax, 0FFFFFFFFh
0x140050ad1  lock xadd [rdx+10h], eax
0x140050ad6  sub     eax, 1
0x140050ad9  jg      short loc_140050AE8
0x140050adb  lfence
0x140050ade  mov     rcx, [rdx]
0x140050ae1  mov     rax, [rcx]
0x140050ae4  call    qword ptr [rax+8]
0x140050ae7  nop
0x140050ae8  mov     rdx, [rbp+57h+var_58]
0x140050aec  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140050af0  or      eax, 0FFFFFFFFh
0x140050af3  lock xadd [rdx+10h], eax
0x140050af8  sub     eax, 1
0x140050afb  jg      short loc_140050B09
0x140050afd  lfence
0x140050b00  mov     rcx, [rdx]
0x140050b03  mov     rax, [rcx]
0x140050b06  call    qword ptr [rax+8]
0x140050b09  test    r14d, r14d
0x140050b0c  jz      loc_140050D6E
0x140050b12  xor     r14d, r14d
0x140050b15  mov     [rbp+57h+var_70], r14
0x140050b19  mov     rcx, [rdi-18h]
0x140050b1d  test    rcx, rcx
0x140050b20  jz      short loc_140050B30
0x140050b22  mov     rax, [rcx]
0x140050b25  call    qword ptr [rax+20h]
0x140050b28  mov     rcx, rax
0x140050b2b  test    rax, rax
0x140050b2e  jnz     short loc_140050B4A
0x140050b30  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140050b35  mov     rdx, [rax]
0x140050b38  mov     rcx, rax
0x140050b3b  call    qword ptr [rdx+20h]
0x140050b3e  mov     rcx, rax
0x140050b41  test    rax, rax
0x140050b44  jz      loc_140050E16
0x140050b4a  mov     rax, [rcx]
0x140050b4d  call    qword ptr [rax+18h]
0x140050b50  add     rax, 18h
0x140050b54  mov     [rbp+57h+var_70], rax
0x140050b58  or      r15d, 2
0x140050b5c  mov     [rbp+57h+arg_18], r15d
0x140050b60  mov     eax, 5Ch ; '\'
0x140050b65  mov     word ptr [rbp+57h+arg_10], ax
0x140050b69  mov     eax, [rdi-10h]
0x140050b6c  mov     [rsp+0C0h+var_A0], eax
0x140050b70  mov     r9, rdi
0x140050b73  mov     r8d, 1
0x140050b79  lea     rdx, [rbp+57h+arg_10]
0x140050b7d  lea     rcx, [rbp+57h+var_70]
0x140050b81  call    ?Concatenate@?$CSimpleStringT@G$0A@@ATL@@KAXAEAV12@PEBGH1H@Z; ATL::CSimpleStringT<ushort,0>::Concatenate(ATL::CSimpleStringT<ushort,0> &,ushort const *,int,ushort const *,int)
0x140050b86  mov     rbx, [rbp+57h+var_70]
0x140050b8a  mov     r8d, [rbx-10h]
0x140050b8e  mov     rdx, rbx
0x140050b91  lea     rcx, [rbp+57h+var_80]
0x140050b95  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x140050b9a  and     r15d, 0FFFFFFFDh
0x140050b9e  mov     [rbp+57h+arg_18], r15d
0x140050ba2  lea     rdx, [rbx-18h]
0x140050ba6  or      eax, 0FFFFFFFFh
0x140050ba9  lock xadd [rdx+10h], eax
0x140050bae  sub     eax, 1
0x140050bb1  jg      short loc_140050BBF
0x140050bb3  lfence
0x140050bb6  mov     rcx, [rdx]
0x140050bb9  mov     rax, [rcx]
0x140050bbc  call    qword ptr [rax+8]
0x140050bbf  lea     rcx, [rbp+57h+var_80]
0x140050bc3  call    ?TrimRight@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@G@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::TrimRight(ushort)
0x140050bc8  mov     r15, rax
0x140050bcb  mov     rax, [rax]
0x140050bce  mov     rbx, rax
0x140050bd1  mov     ecx, 5Ch ; '\'
0x140050bd6  cmp     cx, [rax]
0x140050bd9  jnz     loc_140050C90
0x140050bdf  add     rbx, 2
0x140050be3  cmp     cx, [rbx]
0x140050be6  jz      short loc_140050BDF
0x140050be8  cmp     rbx, rax
0x140050beb  jz      loc_140050C90
0x140050bf1  sub     rbx, rax
0x140050bf4  sar     rbx, 1
0x140050bf7  mov     edx, [rax-10h]
0x140050bfa  test    edx, edx
0x140050bfc  js      loc_140050E08
0x140050c02  mov     ecx, 1
0x140050c07  sub     ecx, [rax-8]
0x140050c0a  mov     eax, [rax-0Ch]
0x140050c0d  sub     eax, edx
0x140050c0f  or      eax, ecx
0x140050c11  jge     short loc_140050C1E
0x140050c13  lfence
0x140050c16  mov     rcx, r15
0x140050c19  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x140050c1e  mov     rcx, [r15]; void *
0x140050c21  movsxd  rax, ebx
0x140050c24  lea     rdx, [rcx+rax*2]; Src
0x140050c28  mov     r9d, [rcx-10h]
0x140050c2c  mov     r14d, r9d
0x140050c2f  sub     r14d, ebx
0x140050c32  lea     eax, [r14+1]
0x140050c36  movsxd  r8, eax
0x140050c39  add     r8, r8; Size
0x140050c3c  jz      short loc_140050C68
0x140050c3e  test    rcx, rcx
0x140050c41  jz      loc_140050DF8
0x140050c47  test    rdx, rdx
0x140050c4a  jz      loc_140050DF8
0x140050c50  lea     eax, [r9+1]
0x140050c54  movsxd  r9, eax
0x140050c57  add     r9, r9
0x140050c5a  cmp     r9, r8
0x140050c5d  jb      loc_140050DEB
0x140050c63  call    memmove_0
0x140050c68  test    r14d, r14d
0x140050c6b  js      loc_140050E08
0x140050c71  mov     rax, [r15]
0x140050c74  cmp     r14d, [rax-0Ch]
0x140050c78  jg      loc_140050E08
0x140050c7e  mov     [rax-10h], r14d
0x140050c82  movsxd  rcx, r14d
0x140050c85  mov     rax, [r15]
0x140050c88  xor     r14d, r14d
0x140050c8b  mov     [rax+rcx*2], r14w
0x140050c90  mov     dword ptr [rbp+57h+arg_10], r14d
0x140050c94  mov     al, cs:?ms_bLoggingOn@CLogger@@0_NA; bool CLogger::ms_bLoggingOn
0x140050c9a  neg     al
0x140050c9c  sbb     ebx, ebx
0x140050c9e  and     ebx, 19h
0x140050ca1  add     ebx, 20006h
0x140050ca7  mov     rcx, [r13+0B0h]; hToken
0x140050cae  call    cs:__imp_ImpersonateLoggedOnUser
0x140050cb4  mov     r14d, eax
0x140050cb7  lea     rcx, [r13+0D8h]; this
0x140050cbe  lea     rax, [rbp+57h+arg_10]
0x140050cc2  mov     [rsp+0C0h+var_88], rax; unsigned int *
0x140050cc7  mov     [rsp+0C0h+var_98], ebx; unsigned int
0x140050ccb  mov     edx, [r13+0F0h]
0x140050cd2  mov     [rsp+0C0h+var_A0], edx; unsigned int
0x140050cd6  mov     r8, [rbp+57h+var_80]; unsigned __int16 *
0x140050cda  mov     rdx, [rbp+57h+var_48]; HKEY
0x140050cde  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x140050ce3  movzx   ebx, ax
0x140050ce6  or      ebx, 80070000h
0x140050cec  test    eax, eax
0x140050cee  cmovle  ebx, eax
0x140050cf1  test    ebx, ebx
0x140050cf3  js      short loc_140050D62
0x140050cf5  test    r14d, r14d
0x140050cf8  jz      short loc_140050D00
0x140050cfa  call    cs:__imp_RevertToSelf
0x140050d00  cmp     dword ptr [rbp+57h+arg_10], 1
0x140050d04  mov     r15d, [rbp+57h+arg_18]
0x140050d08  jnz     loc_140050A76
0x140050d0e  lfence
0x140050d11  lea     r8, [rbp+57h+var_80]
0x140050d15  lea     rdx, [rbp+57h+var_68]
0x140050d19  lea     rcx, [rbp+57h+var_40]
0x140050d1d  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@0@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140050d22  nop
0x140050d23  mov     r8, [r13+0]
0x140050d27  mov     rdx, rax
0x140050d2a  mov     rcx, r13
0x140050d2d  call    qword ptr [r8+40h]
0x140050d31  mov     ebx, eax
0x140050d33  mov     rdx, [rbp+57h+var_40]
0x140050d37  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140050d3b  or      ecx, 0FFFFFFFFh
0x140050d3e  lock xadd [rdx+10h], ecx
0x140050d43  sub     ecx, 1
0x140050d46  jg      short loc_140050D55
0x140050d48  lfence
0x140050d4b  mov     rcx, [rdx]
0x140050d4e  mov     r8, [rcx]
0x140050d51  call    qword ptr [r8+8]
0x140050d55  test    ebx, ebx
0x140050d57  js      short loc_140050D6E
0x140050d59  mov     r15d, [rbp+57h+arg_18]
0x140050d5d  jmp     loc_140050A76
0x140050d62  test    r14d, r14d
0x140050d65  jz      short loc_140050D6E
0x140050d67  call    cs:__imp_RevertToSelf
0x140050d6d  nop
0x140050d6e  lea     rdx, [rdi-18h]
0x140050d72  or      edi, 0FFFFFFFFh
0x140050d75  mov     eax, edi
  ... truncated ...
```
