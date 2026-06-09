# QueryCurrentPolicyFromRoot(Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsPolicy &,LAPS_POLICY_ROOT const *)

- ea: `0x18013e1ac`
- end: `0x18013e663`
- name: `?QueryCurrentPolicyFromRoot@@YAJAEAVLapsPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@PEBULAPS_POLICY_ROOT@@@Z`
- size: `1207`
- prototype: `int(struct Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsPolicy *, const struct LAPS_POLICY_ROOT *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18013e118`

## callees

- `0x1800e4408`
- `0x1800e5744`
- `0x1800e734c`
- `0x1800e7de8`
- `0x1800e8508`
- `0x1800ed46c`
- `0x18011273c`
- `0x18013d660`
- `0x18013d7a8`
- `0x18013da78`
- `0x18013e1ac`
- `0x18013e66c`
- `0x18013e814`
- `0x18013ea10`
- `0x18013ec14`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18013e23c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18013e23c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18013e206`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18013e206`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall QueryCurrentPolicyFromRoot(
        struct Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsPolicy *a1,
        LPCWSTR *a2)
{
  Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsPolicy *v3; // rdx
  HKEY v4; // rbx
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rcx
  BOOL v10; // r15d
  unsigned int v11; // edi
  _DWORD *v12; // r12
  __int64 v13; // rcx
  bool v14; // zf
  int v15; // eax
  unsigned int i; // edi
  __int64 v17; // rax
  bool v18; // zf
  int v19; // eax
  unsigned int j; // edi
  __int64 v21; // rcx
  bool v22; // zf
  int v23; // eax
  unsigned int v24; // edi
  unsigned int k; // esi
  _QWORD *v26; // r8
  unsigned int m; // esi
  _QWORD *v28; // r8
  int phkResult; // [rsp+20h] [rbp-48h]
  __int128 v31; // [rsp+30h] [rbp-38h] BYREF
  __int64 v32; // [rsp+40h] [rbp-28h]
  __int64 v33; // [rsp+48h] [rbp-20h] BYREF
  __int128 v34; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting *v37; // [rsp+B8h] [rbp+50h] BYREF
  HKEY hKey; // [rsp+C0h] [rbp+58h] BYREF
  char v39; // [rsp+C8h] [rbp+60h] BYREF

  hKey = 0;
  v37 = 0;
  std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(&v31);
  std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(&v33);
  Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsPolicy::Clear(v3);
  v4 = hKey;
  if ( hKey )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v39);
    RegCloseKey(v4);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v39);
  }
  hKey = 0;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, *a2, 0, 0x20019u, &hKey);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( (v6 & 0x80000000) == 0 )
  {
    v10 = 0;
    v11 = 0;
    v12 = a2 + 2;
    while ( v11 < 7 )
    {
      v12 = a2 + 2;
      v13 = 3LL * v11;
      if ( *((_DWORD *)a2 + 4) )
        v14 = (qword_18019CF78[v13] & 0x100000000LL) == 0;
      else
        v14 = (qword_18019CF78[v13] & 0x200000000LL) == 0;
      if ( v14 )
      {
        v15 = QueryPolicyDwordValue(
                hKey,
                (const struct LAPS_POLICY_ROOT *)a2,
                (const struct LAPS_DWORD_SETTING *)&(&off_18019CF70)[v13],
                &v37);
        v6 = v15;
        if ( v15 < 0 )
        {
          v7 = (unsigned int)v15;
          v8 = 797;
          goto LABEL_7;
        }
        if ( !v10 )
          v10 = *((_DWORD *)v37 + 32) == 0;
        if ( *((_QWORD *)&v31 + 1) == v32 )
        {
          std::vector<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting *>::_Emplace_reallocate<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * const &>(
            &v31,
            *((_QWORD *)&v31 + 1),
            &v37);
        }
        else
        {
          **((_QWORD **)&v31 + 1) = v37;
          *((_QWORD *)&v31 + 1) += 8LL;
        }
      }
      ++v11;
    }
    for ( i = 0; i < 3; ++i )
    {
      v17 = 4LL * i;
      if ( *v12 )
        v18 = (qword_18019CF20[v17] & 1) == 0;
      else
        v18 = (qword_18019CF20[v17] & 2) == 0;
      if ( v18 )
      {
        v19 = QueryPolicySzValue(
                hKey,
                (const struct LAPS_POLICY_ROOT *)a2,
                (const struct LAPS_SZ_SETTING *)&(&off_18019CF10)[v17],
                &v37);
        v6 = v19;
        if ( v19 < 0 )
        {
          v7 = (unsigned int)v19;
          v8 = 817;
          goto LABEL_7;
        }
        if ( !v10 )
          v10 = *((_DWORD *)v37 + 32) == 0;
        if ( *((_QWORD *)&v31 + 1) == v32 )
        {
          std::vector<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting *>::_Emplace_reallocate<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * const &>(
            &v31,
            *((_QWORD *)&v31 + 1),
            &v37);
        }
        else
        {
          **((_QWORD **)&v31 + 1) = v37;
          *((_QWORD *)&v31 + 1) += 8LL;
        }
      }
      v12 = a2 + 2;
    }
    for ( j = 0; j < 5; ++j )
    {
      v21 = 3LL * j;
      if ( *v12 )
        v22 = (qword_18019CE98[v21] & 0x100000000LL) == 0;
      else
        v22 = (qword_18019CE98[v21] & 0x200000000LL) == 0;
      if ( v22 )
      {
        v23 = QueryPolicyBoolValue(
                hKey,
                (const struct LAPS_POLICY_ROOT *)a2,
                (const struct LAPS_BOOL_SETTING *)&(&off_18019CE90)[v21],
                &v37);
        v6 = v23;
        if ( v23 < 0 )
        {
          v7 = (unsigned int)v23;
          v8 = 837;
          goto LABEL_7;
        }
        if ( !v10 )
          v10 = *((_DWORD *)v37 + 32) == 0;
        if ( *((_QWORD *)&v31 + 1) == v32 )
        {
          std::vector<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting *>::_Emplace_reallocate<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * const &>(
            &v31,
            *((_QWORD *)&v31 + 1),
            &v37);
        }
        else
        {
          **((_QWORD **)&v31 + 1) = v37;
          *((_QWORD *)&v31 + 1) += 8LL;
        }
      }
    }
    v24 = 0;
    if ( *v12 )
    {
      do
      {
        for ( k = 0; k < (unsigned __int64)((__int64)(*((_QWORD *)&v31 + 1) - v31) >> 3); ++k )
        {
          if ( (unsigned __int8)std::wstring::_Equal(*(_QWORD *)(v31 + 8LL * k), off_18019DC20[v24]) )
          {
            v26 = (_QWORD *)(v31 + 8LL * k);
            if ( (_QWORD)v34 == *((_QWORD *)&v34 + 1) )
            {
              std::vector<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting *>::_Emplace_reallocate<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * const &>(
                &v33,
                v34,
                v26);
            }
            else
            {
              *(_QWORD *)v34 = *v26;
              *(_QWORD *)&v34 = v34 + 8;
            }
            break;
          }
        }
        ++v24;
      }
      while ( v24 < 0xC );
    }
    else
    {
      do
      {
        for ( m = 0; m < (unsigned __int64)((__int64)(*((_QWORD *)&v31 + 1) - v31) >> 3); ++m )
        {
          if ( (unsigned __int8)std::wstring::_Equal(*(_QWORD *)(v31 + 8LL * m), off_18019DC20[v24]) )
          {
            v28 = (_QWORD *)(v31 + 8LL * m);
            if ( (_QWORD)v34 == *((_QWORD *)&v34 + 1) )
            {
              std::vector<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting *>::_Emplace_reallocate<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * const &>(
                &v33,
                v34,
                v28);
            }
            else
            {
              *(_QWORD *)v34 = *v28;
              *(_QWORD *)&v34 = v34 + 8;
            }
            break;
          }
        }
        ++v24;
      }
      while ( v24 < 6 );
    }
    std::wstring::assign(a1, a2[1]);
    *((_DWORD *)a1 + 8) = *v12;
    *((_DWORD *)a1 + 9) = v10;
    if ( (__int64 *)((char *)a1 + 40) != &v33 )
      std::vector<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting *>::_Assign_counted_range<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * *>(
        (char *)a1 + 40,
        v33,
        ((__int64)v34 - v33) >> 3);
    if ( v33 )
    {
      std::_Deallocate<16>(v33, (*((_QWORD *)&v34 + 1) - v33) & 0xFFFFFFFFFFFFFFF8uLL);
      v33 = 0;
      v34 = 0;
    }
    v9 = v31;
    if ( (_QWORD)v31 )
      goto LABEL_76;
  }
  else
  {
    v7 = v6;
    v8 = 780;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\laps.cpp",
      (const char *)v7,
      phkResult);
    if ( v33 )
    {
      std::_Deallocate<16>(v33, (*((_QWORD *)&v34 + 1) - v33) & 0xFFFFFFFFFFFFFFF8uLL);
      v33 = 0;
      v34 = 0;
    }
    v9 = v31;
    if ( (_QWORD)v31 )
    {
LABEL_76:
      std::_Deallocate<16>(v9, (v32 - v31) & 0xFFFFFFFFFFFFFFF8uLL);
      v32 = 0;
      v31 = 0;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v6;
}

```

## disassembly

```asm
0x18013e1ac  mov     [rsp-40h+arg_0], rcx
0x18013e1b1  push    rbp
0x18013e1b2  push    rbx
0x18013e1b3  push    rsi
0x18013e1b4  push    rdi
0x18013e1b5  push    r12
0x18013e1b7  push    r13
0x18013e1b9  push    r14
0x18013e1bb  push    r15
0x18013e1bd  mov     rbp, rsp
0x18013e1c0  sub     rsp, 68h
0x18013e1c4  mov     r13, rdx
0x18013e1c7  mov     rdx, rcx
0x18013e1ca  xor     r14d, r14d
0x18013e1cd  mov     [rbp+hKey], r14
0x18013e1d1  mov     [rbp+arg_8], r14
0x18013e1d5  lea     rcx, [rbp+var_38]
0x18013e1d9  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x18013e1de  nop
0x18013e1df  lea     rcx, [rbp+var_20]
0x18013e1e3  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x18013e1e8  nop
0x18013e1e9  mov     rcx, rdx; this
0x18013e1ec  call    ?Clear@LapsPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXXZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsPolicy::Clear(void)
0x18013e1f1  mov     rbx, [rbp+hKey]
0x18013e1f5  test    rbx, rbx
0x18013e1f8  jz      short loc_18013E21B
0x18013e1fa  lea     rcx, [rbp+arg_18]; this
0x18013e1fe  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18013e203  mov     rcx, rbx; hKey
0x18013e206  call    cs:__imp_RegCloseKey
0x18013e20d  nop     dword ptr [rax+rax+00h]
0x18013e212  lea     rcx, [rbp+arg_18]; this
0x18013e216  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18013e21b  mov     [rbp+hKey], r14
0x18013e21f  lea     rax, [rbp+hKey]
0x18013e223  mov     qword ptr [rsp+68h+phkResult], rax; int
0x18013e228  mov     r9d, 20019h; samDesired
0x18013e22e  xor     r8d, r8d; ulOptions
0x18013e231  mov     rdx, [r13+0]; lpSubKey
0x18013e235  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18013e23c  call    cs:__imp_RegOpenKeyExW
0x18013e243  nop     dword ptr [rax+rax+00h]
0x18013e248  mov     ebx, eax
0x18013e24a  test    eax, eax
0x18013e24c  jle     short loc_18013E257
0x18013e24e  movzx   ebx, ax
0x18013e251  or      ebx, 80070000h
0x18013e257  test    ebx, ebx
0x18013e259  jns     short loc_18013E2BF
0x18013e25b  mov     r9d, ebx; char *
0x18013e25e  mov     edx, 30Ch; void *
0x18013e263  mov     rcx, [rbp+40h]; this
0x18013e267  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013e26e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013e273  nop
0x18013e274  mov     rcx, [rbp+var_20]
0x18013e278  test    rcx, rcx
0x18013e27b  jz      short loc_18013E299
0x18013e27d  mov     rdx, qword ptr [rbp+var_18+8]
0x18013e281  sub     rdx, rcx
0x18013e284  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18013e288  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18013e28d  mov     [rbp+var_20], r14
0x18013e291  xorps   xmm0, xmm0
0x18013e294  movdqu  xmmword ptr [rbp-18h], xmm0
0x18013e299  mov     rcx, qword ptr [rbp+var_38]
0x18013e29d  test    rcx, rcx
0x18013e2a0  jz      loc_18013E646
0x18013e2a6  mov     rdx, [rbp+var_28]
0x18013e2aa  sub     rdx, rcx
0x18013e2ad  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18013e2b1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18013e2b6  mov     [rbp+var_28], r14
0x18013e2ba  jmp     loc_18013E63E
0x18013e2bf  mov     r15d, r14d
0x18013e2c2  mov     edi, r14d
0x18013e2c5  lea     r12, [r13+10h]
0x18013e2c9  lea     r8, __ImageBase
0x18013e2d0  cmp     edi, 7
0x18013e2d3  jnb     loc_18013E376
0x18013e2d9  lea     r12, [r13+10h]
0x18013e2dd  mov     eax, edi
0x18013e2df  lea     rcx, [rax+rax*2]
0x18013e2e3  shl     rcx, 3
0x18013e2e7  cmp     [r12], r14d
0x18013e2eb  jz      short loc_18013E2F8
0x18013e2ed  test    byte ptr [rcx+r8+19CF7Ch], 1
0x18013e2f6  jmp     short loc_18013E301
0x18013e2f8  test    byte ptr [rcx+r8+19CF7Ch], 2
0x18013e301  jnz     short loc_18013E362
0x18013e303  lea     r8, rva off_18019CF70[r8]; "BackupDirectory" ...
0x18013e30a  add     r8, rcx; struct LAPS_DWORD_SETTING *
0x18013e30d  lea     r9, [rbp+arg_8]; struct Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting **
0x18013e311  mov     rdx, r13; struct LAPS_POLICY_ROOT *
0x18013e314  mov     rcx, [rbp+hKey]; HKEY
0x18013e318  call    ?QueryPolicyDwordValue@@YAJPEAUHKEY__@@PEBULAPS_POLICY_ROOT@@PEBULAPS_DWORD_SETTING@@PEAPEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@Z; QueryPolicyDwordValue(HKEY__ *,LAPS_POLICY_ROOT const *,LAPS_DWORD_SETTING const *,Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * *)
0x18013e31d  mov     ebx, eax
0x18013e31f  test    eax, eax
0x18013e321  js      short loc_18013E369
0x18013e323  mov     rax, [rbp+arg_8]
0x18013e327  test    r15d, r15d
0x18013e32a  jnz     short loc_18013E33A
0x18013e32c  mov     r15d, r14d
0x18013e32f  cmp     [rax+80h], r14d
0x18013e336  setz    r15b
0x18013e33a  mov     rdx, qword ptr [rbp+var_38+8]
0x18013e33e  cmp     rdx, [rbp+var_28]
0x18013e342  jz      short loc_18013E34E
0x18013e344  mov     [rdx], rax
0x18013e347  add     qword ptr [rbp+var_38+8], 8
0x18013e34c  jmp     short loc_18013E35B
0x18013e34e  lea     r8, [rbp+arg_8]
0x18013e352  lea     rcx, [rbp+var_38]
0x18013e356  call    ??$_Emplace_reallocate@AEBQEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@?$vector@PEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@PEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@AEAAPEAPEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAPEAV23456@AEBQEAV23456@@Z; std::vector<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting *>::_Emplace_reallocate<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * const &>(Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * * const,Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * const &)
0x18013e35b  lea     r8, __ImageBase
0x18013e362  inc     edi
0x18013e364  jmp     loc_18013E2D0
0x18013e369  mov     r9d, eax
0x18013e36c  mov     edx, 31Dh
0x18013e371  jmp     loc_18013E263
0x18013e376  mov     edi, r14d
0x18013e379  cmp     edi, 3
0x18013e37c  jnb     loc_18013E41B
0x18013e382  mov     eax, edi
0x18013e384  shl     rax, 5
0x18013e388  cmp     [r12], r14d
0x18013e38c  jz      short loc_18013E399
0x18013e38e  test    byte ptr [rax+r8+19CF20h], 1
0x18013e397  jmp     short loc_18013E3A2
0x18013e399  test    byte ptr [rax+r8+19CF20h], 2
0x18013e3a2  jnz     short loc_18013E403
0x18013e3a4  lea     r8, rva off_18019CF10[r8]; "AdministratorAccountName" ...
0x18013e3ab  add     r8, rax; struct LAPS_SZ_SETTING *
0x18013e3ae  lea     r9, [rbp+arg_8]; struct Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting **
0x18013e3b2  mov     rdx, r13; struct LAPS_POLICY_ROOT *
0x18013e3b5  mov     rcx, [rbp+hKey]; HKEY
0x18013e3b9  call    ?QueryPolicySzValue@@YAJPEAUHKEY__@@PEBULAPS_POLICY_ROOT@@PEBULAPS_SZ_SETTING@@PEAPEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@Z; QueryPolicySzValue(HKEY__ *,LAPS_POLICY_ROOT const *,LAPS_SZ_SETTING const *,Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * *)
0x18013e3be  mov     ebx, eax
0x18013e3c0  test    eax, eax
0x18013e3c2  js      short loc_18013E40E
0x18013e3c4  mov     rax, [rbp+arg_8]
0x18013e3c8  test    r15d, r15d
0x18013e3cb  jnz     short loc_18013E3DB
0x18013e3cd  mov     r15d, r14d
0x18013e3d0  cmp     [rax+80h], r14d
0x18013e3d7  setz    r15b
0x18013e3db  mov     rdx, qword ptr [rbp+var_38+8]
0x18013e3df  cmp     rdx, [rbp+var_28]
0x18013e3e3  jz      short loc_18013E3EF
0x18013e3e5  mov     [rdx], rax
0x18013e3e8  add     qword ptr [rbp+var_38+8], 8
0x18013e3ed  jmp     short loc_18013E3FC
0x18013e3ef  lea     r8, [rbp+arg_8]
0x18013e3f3  lea     rcx, [rbp+var_38]
0x18013e3f7  call    ??$_Emplace_reallocate@AEBQEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@?$vector@PEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@PEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@AEAAPEAPEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAPEAV23456@AEBQEAV23456@@Z; std::vector<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting *>::_Emplace_reallocate<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * const &>(Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * * const,Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * const &)
0x18013e3fc  lea     r8, __ImageBase
0x18013e403  inc     edi
0x18013e405  lea     r12, [r13+10h]
0x18013e409  jmp     loc_18013E379
0x18013e40e  mov     r9d, eax
0x18013e411  mov     edx, 331h
0x18013e416  jmp     loc_18013E263
0x18013e41b  mov     edi, r14d
0x18013e41e  cmp     edi, 5
0x18013e421  jnb     loc_18013E4C0
0x18013e427  mov     eax, edi
0x18013e429  lea     rcx, [rax+rax*2]
0x18013e42d  shl     rcx, 3
0x18013e431  cmp     [r12], r14d
0x18013e435  jz      short loc_18013E442
0x18013e437  test    byte ptr [rcx+r8+19CE9Ch], 1
0x18013e440  jmp     short loc_18013E44B
0x18013e442  test    byte ptr [rcx+r8+19CE9Ch], 2
0x18013e44b  jnz     short loc_18013E4AC
0x18013e44d  lea     r8, rva off_18019CE90[r8]; "PasswordExpirationProtectionEnabled" ...
0x18013e454  add     r8, rcx; struct LAPS_BOOL_SETTING *
0x18013e457  lea     r9, [rbp+arg_8]; struct Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting **
0x18013e45b  mov     rdx, r13; struct LAPS_POLICY_ROOT *
0x18013e45e  mov     rcx, [rbp+hKey]; HKEY
0x18013e462  call    ?QueryPolicyBoolValue@@YAJPEAUHKEY__@@PEBULAPS_POLICY_ROOT@@PEBULAPS_BOOL_SETTING@@PEAPEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@Z; QueryPolicyBoolValue(HKEY__ *,LAPS_POLICY_ROOT const *,LAPS_BOOL_SETTING const *,Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * *)
0x18013e467  mov     ebx, eax
0x18013e469  test    eax, eax
0x18013e46b  js      short loc_18013E4B3
0x18013e46d  mov     rax, [rbp+arg_8]
0x18013e471  test    r15d, r15d
0x18013e474  jnz     short loc_18013E484
0x18013e476  mov     r15d, r14d
0x18013e479  cmp     [rax+80h], r14d
0x18013e480  setz    r15b
0x18013e484  mov     rdx, qword ptr [rbp+var_38+8]
0x18013e488  cmp     rdx, [rbp+var_28]
0x18013e48c  jz      short loc_18013E498
0x18013e48e  mov     [rdx], rax
0x18013e491  add     qword ptr [rbp+var_38+8], 8
0x18013e496  jmp     short loc_18013E4A5
0x18013e498  lea     r8, [rbp+arg_8]
0x18013e49c  lea     rcx, [rbp+var_38]
0x18013e4a0  call    ??$_Emplace_reallocate@AEBQEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@?$vector@PEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@PEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@AEAAPEAPEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAPEAV23456@AEBQEAV23456@@Z; std::vector<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting *>::_Emplace_reallocate<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * const &>(Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * * const,Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * const &)
0x18013e4a5  lea     r8, __ImageBase
0x18013e4ac  inc     edi
0x18013e4ae  jmp     loc_18013E41E
0x18013e4b3  mov     r9d, eax
0x18013e4b6  mov     edx, 345h
0x18013e4bb  jmp     loc_18013E263
0x18013e4c0  mov     edi, r14d
0x18013e4c3  cmp     [r12], r14d
0x18013e4c7  jz      short loc_18013E545
0x18013e4c9  jmp     short loc_18013E4CE
0x18013e4cb  xor     r14d, r14d
0x18013e4ce  mov     esi, r14d
0x18013e4d1  mov     r14d, esi
0x18013e4d4  mov     rax, qword ptr [rbp+var_38+8]
0x18013e4d8  mov     rcx, qword ptr [rbp+var_38]
0x18013e4dc  sub     rax, rcx
0x18013e4df  sar     rax, 3
0x18013e4e3  cmp     r14, rax
0x18013e4e6  jnb     short loc_18013E539
0x18013e4e8  mov     edx, edi
0x18013e4ea  mov     rdx, ds:rva off_18019DC20[r8+rdx*8]; "BackupDirectory" ...
0x18013e4f2  mov     rcx, [rcx+r14*8]
0x18013e4f6  call    ?_Equal@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_NQEBG@Z; std::wstring::_Equal(ushort const * const)
0x18013e4fb  test    al, al
0x18013e4fd  jnz     short loc_18013E50A
0x18013e4ff  inc     esi
0x18013e501  lea     r8, __ImageBase
0x18013e508  jmp     short loc_18013E4D1
0x18013e50a  mov     rax, qword ptr [rbp+var_38]
0x18013e50e  lea     r8, [rax+r14*8]
0x18013e512  mov     rdx, qword ptr [rbp+var_18]
0x18013e516  cmp     rdx, qword ptr [rbp+var_18+8]
0x18013e51a  jz      short loc_18013E529
0x18013e51c  mov     rax, [r8]
0x18013e51f  mov     [rdx], rax
0x18013e522  add     qword ptr [rbp+var_18], 8
0x18013e527  jmp     short loc_18013E532
0x18013e529  lea     rcx, [rbp+var_20]
0x18013e52d  call    ??$_Emplace_reallocate@AEBQEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@?$vector@PEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@PEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@AEAAPEAPEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAPEAV23456@AEBQEAV23456@@Z; std::vector<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting *>::_Emplace_reallocate<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * const &>(Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * * const,Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * const &)
0x18013e532  lea     r8, __ImageBase
0x18013e539  inc     edi
0x18013e53b  cmp     edi, 0Ch
0x18013e53e  jb      short loc_18013E4CB
0x18013e540  jmp     short loc_18013E5B7
0x18013e542  xor     r14d, r14d
0x18013e545  mov     esi, r14d
0x18013e548  mov     r14d, esi
0x18013e54b  mov     rax, qword ptr [rbp+var_38+8]
0x18013e54f  mov     rcx, qword ptr [rbp+var_38]
0x18013e553  sub     rax, rcx
0x18013e556  sar     rax, 3
0x18013e55a  cmp     r14, rax
0x18013e55d  jnb     short loc_18013E5B0
0x18013e55f  mov     edx, edi
0x18013e561  mov     rdx, ds:rva off_18019DC20[r8+rdx*8]; "BackupDirectory" ...
0x18013e569  mov     rcx, [rcx+r14*8]
0x18013e56d  call    ?_Equal@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_NQEBG@Z; std::wstring::_Equal(ushort const * const)
0x18013e572  test    al, al
0x18013e574  jnz     short loc_18013E581
0x18013e576  inc     esi
0x18013e578  lea     r8, __ImageBase
0x18013e57f  jmp     short loc_18013E548
0x18013e581  mov     rax, qword ptr [rbp+var_38]
0x18013e585  lea     r8, [rax+r14*8]
0x18013e589  mov     rdx, qword ptr [rbp+var_18]
0x18013e58d  cmp     rdx, qword ptr [rbp+var_18+8]
0x18013e591  jz      short loc_18013E5A0
0x18013e593  mov     rax, [r8]
0x18013e596  mov     [rdx], rax
0x18013e599  add     qword ptr [rbp+var_18], 8
0x18013e59e  jmp     short loc_18013E5A9
0x18013e5a0  lea     rcx, [rbp+var_20]
0x18013e5a4  call    ??$_Emplace_reallocate@AEBQEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@?$vector@PEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@PEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@AEAAPEAPEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAPEAV23456@AEBQEAV23456@@Z; std::vector<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting *>::_Emplace_reallocate<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * const &>(Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * * const,Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * const &)
0x18013e5a9  lea     r8, __ImageBase
0x18013e5b0  inc     edi
0x18013e5b2  cmp     edi, 6
0x18013e5b5  jb      short loc_18013E542
0x18013e5b7  mov     rdx, [r13+8]
0x18013e5bb  mov     rdi, [rbp+arg_0]
0x18013e5bf  mov     rcx, rdi
0x18013e5c2  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18013e5c7  mov     eax, [r12]
0x18013e5cb  mov     [rdi+20h], eax
0x18013e5ce  mov     [rdi+24h], r15d
0x18013e5d2  lea     rcx, [rdi+28h]
0x18013e5d6  lea     rax, [rbp+var_20]
0x18013e5da  cmp     rcx, rax
0x18013e5dd  jz      short loc_18013E5F4
0x18013e5df  mov     rdx, [rbp+var_20]
0x18013e5e3  mov     r8, qword ptr [rbp+var_18]
0x18013e5e7  sub     r8, rdx
0x18013e5ea  sar     r8, 3
0x18013e5ee  call    ??$_Assign_counted_range@PEAPEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@?$vector@PEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@PEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@AEAAXPEAPEAVLapsSetting@MdmDiagnosticSource@Mdm@Windows@Microsoft@@_K@Z; std::vector<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting *>::_Assign_counted_range<Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * *>(Microsoft::Windows::Mdm::MdmDiagnosticSource::LapsSetting * *,unsigned __int64)
0x18013e5f3  nop
0x18013e5f4  mov     rcx, [rbp+var_20]
0x18013e5f8  test    rcx, rcx
0x18013e5fb  jz      short loc_18013E61D
0x18013e5fd  mov     rdx, qword ptr [rbp+var_18+8]
0x18013e601  sub     rdx, rcx
0x18013e604  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18013e608  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
  ... truncated ...
```
