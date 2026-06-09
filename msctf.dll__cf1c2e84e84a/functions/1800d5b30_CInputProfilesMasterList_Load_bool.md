# CInputProfilesMasterList::Load(bool)

- ea: `0x1800d5b30`
- end: `0x1800d71bf`
- name: `?Load@CInputProfilesMasterList@@UEAAJ_N@Z`
- size: `5775`
- prototype: `__int64 __fastcall(CInputProfilesMasterList *__hidden this, bool)`
- caller_count: `0`
- callee_count: `49`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002084`
- `0x180002b8c`
- `0x18000aa00`
- `0x18000ac48`
- `0x18000fac0`
- `0x180011000`
- `0x1800250fc`
- `0x180049e10`
- `0x18004a490`
- `0x1800526b0`
- `0x1800539d8`
- `0x180053a08`
- `0x180053cb0`
- `0x18005a80c`
- `0x18005b0d8`
- `0x18005d0f0`
- `0x18005daf4`
- `0x18005dc14`
- `0x180068f74`
- `0x180069160`
- `0x18006c2a0`
- `0x180080430`
- `0x180088504`
- `0x180092b48`
- `0x18009c9a0`
- `0x18009eaea`
- `0x18009eb02`
- `0x1800b8440`
- `0x1800d1d78`
- `0x1800d22c0`
- `0x1800d3544`
- `0x1800d3578`
- `0x1800d4afc`
- `0x1800d4b70`
- `0x1800d4ccc`
- `0x1800d4f70`
- `0x1800d5148`
- `0x1800d53ec`
- `0x1800d5700`
- `0x1800d5858`
- `0x1800d5ad8`
- `0x1800d5b30`
- `0x1800d7620`
- `0x1800d7690`
- `0x1800d78c4`
- `0x1800d7a24`
- `0x1800d8d1c`
- `0x180106a60`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d718b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d718b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d6309`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d63bc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d64c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d68e8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d6b67`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d6309`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d63bc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d64c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d68e8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d6b67`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800d5c14`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800d5c2b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800d5c52`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800d5c14`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800d5c2b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800d5c52`
- `USER32!LoadKeyboardLayoutW` at `0x1800d6bef`
- `USER32!LoadKeyboardLayoutW` at `0x1800d6bef`
- `USER32!UnloadKeyboardLayout` at `0x1800d6628`
- `USER32!UnloadKeyboardLayout` at `0x1800d6628`
- `USER32!GetSystemMetrics` at `0x1800d6a41`
- `USER32!GetSystemMetrics` at `0x1800d6c69`
- `USER32!GetSystemMetrics` at `0x1800d6a41`
- `USER32!GetSystemMetrics` at `0x1800d6c69`

## string_xrefs

- `0x1800d6abe`: `CLSID`

## pseudocode

```c
__int64 __fastcall CInputProfilesMasterList::Load(CInputProfilesMasterList *this, char a2)
{
  char v2; // r15
  int v3; // esi
  CInputProfileAssembly *v5; // r13
  int v6; // r12d
  int v7; // r8d
  unsigned int v8; // edx
  unsigned int v9; // ebx
  int v10; // ebx
  unsigned int i; // edx
  int v12; // edx
  struct _GUID *v13; // rax
  int v14; // edx
  int v15; // r14d
  GUID *v16; // rax
  int v17; // r12d
  int v18; // ebx
  int v19; // esi
  int j; // eax
  int v21; // edx
  unsigned int v22; // edx
  int v23; // r14d
  unsigned __int16 v24; // ax
  unsigned __int16 v25; // r13
  int v26; // esi
  const unsigned __int16 *v27; // r8
  BOOL v28; // r15d
  HKL SubstituteHKLfromKey; // r12
  int v30; // esi
  const unsigned __int16 *v31; // r8
  const unsigned __int16 *v32; // rdx
  Tsf3OverrideUtil *v33; // rcx
  int v34; // r14d
  __int64 v35; // rax
  __int64 *v36; // rcx
  __int64 v37; // rax
  int v38; // r14d
  __int64 v39; // rax
  unsigned __int16 **v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  __int64 *v43; // rcx
  __int64 v44; // rax
  struct CInputProfile *EnabledProfile; // rax
  unsigned int v46; // edx
  unsigned int v47; // edx
  unsigned int v48; // edx
  int v49; // eax
  int v50; // r14d
  unsigned __int16 v51; // ax
  CInputLanguage *InputLanguage; // rbx
  int v53; // esi
  HKL v54; // rdx
  GUID *v55; // r9
  GUID *v56; // r8
  struct CInputProfile *InputProfile; // rax
  unsigned int v58; // edx
  unsigned int v59; // edx
  HKL v60; // rsi
  unsigned int v61; // ebx
  int v62; // eax
  CInputLanguage *v63; // rax
  struct CInputProfile *v64; // rax
  char v65; // cl
  int v66; // r12d
  int v67; // edx
  __int64 v68; // rbx
  char v69; // r15
  int v70; // r14d
  CInputProfile *v71; // rcx
  int v72; // r8d
  __int64 v73; // r9
  CInputProfile *v74; // rcx
  int v75; // eax
  __int64 v76; // r10
  char v77; // r11
  int IsSystemKeyboardTIPorIME; // eax
  int v79; // r15d
  unsigned __int16 *v80; // r10
  __int64 v81; // rsi
  unsigned __int16 *v82; // r14
  __int64 v83; // r9
  int v84; // r8d
  unsigned __int16 *v85; // rbx
  CInputProfile *v86; // rcx
  int v87; // r8d
  BOOL v88; // eax
  int v89; // ecx
  int v90; // r8d
  int v91; // r9d
  int k; // ebx
  CInputProfile *v93; // rcx
  CInputProfile *v94; // rcx
  __int64 v95; // r8
  char v96; // al
  int v97; // ecx
  __int64 v98; // r8
  int v99; // r9d
  int v100; // ecx
  unsigned __int16 *v101; // r8
  int v102; // r9d
  bool v103; // bl
  int m; // ebx
  unsigned __int16 *v105; // rsi
  __int64 v106; // rax
  char v107; // al
  __int64 v108; // rcx
  char v110; // [rsp+50h] [rbp-B0h]
  DWORD Type; // [rsp+54h] [rbp-ACh] BYREF
  char v112[4]; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cbData; // [rsp+5Ch] [rbp-A4h] BYREF
  BYTE lpData[4]; // [rsp+60h] [rbp-A0h] BYREF
  char v115; // [rsp+64h] [rbp-9Ch]
  unsigned __int16 *v116; // [rsp+68h] [rbp-98h] BYREF
  BYTE Data[8]; // [rsp+70h] [rbp-90h] BYREF
  void **v118; // [rsp+78h] [rbp-88h] BYREF
  HKEY v119; // [rsp+80h] [rbp-80h]
  __int64 v120; // [rsp+88h] [rbp-78h] BYREF
  struct _GUID Buf1; // [rsp+90h] [rbp-70h] BYREF
  int updated; // [rsp+A0h] [rbp-60h]
  void **v123; // [rsp+A8h] [rbp-58h] BYREF
  HKEY v124; // [rsp+B0h] [rbp-50h]
  _QWORD Buf2[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v126; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 *v127; // [rsp+D0h] [rbp-30h] BYREF
  void **v128; // [rsp+D8h] [rbp-28h] BYREF
  HKEY v129; // [rsp+E0h] [rbp-20h]
  void **v130; // [rsp+E8h] [rbp-18h] BYREF
  HKEY v131; // [rsp+F0h] [rbp-10h]
  int v132; // [rsp+F8h] [rbp-8h]
  int v133; // [rsp+FCh] [rbp-4h]
  void **v134; // [rsp+100h] [rbp+0h] BYREF
  HKEY hKey; // [rsp+108h] [rbp+8h]
  __int64 v136; // [rsp+110h] [rbp+10h] BYREF
  void **v137; // [rsp+118h] [rbp+18h] BYREF
  HKEY v138; // [rsp+120h] [rbp+20h]
  struct _GUID v139; // [rsp+130h] [rbp+30h] BYREF
  void **v140; // [rsp+140h] [rbp+40h] BYREF
  LPVOID lpMem; // [rsp+148h] [rbp+48h]
  int v142; // [rsp+150h] [rbp+50h]
  int v143; // [rsp+154h] [rbp+54h]
  HANDLE hHeap; // [rsp+160h] [rbp+60h]
  struct _GUID v145; // [rsp+170h] [rbp+70h] BYREF
  struct _GUID v146; // [rsp+180h] [rbp+80h] BYREF
  struct _GUID pwszKLID; // [rsp+190h] [rbp+90h] BYREF
  __int16 v148; // [rsp+1A4h] [rbp+A4h]
  unsigned __int16 v149[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  wchar_t String[14]; // [rsp+1B4h] [rbp+B4h] BYREF
  unsigned __int16 v151[40]; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int16 v152[40]; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int16 v153[34]; // [rsp+270h] [rbp+170h] BYREF
  int v154; // [rsp+2B4h] [rbp+1B4h]
  unsigned __int16 v155[104]; // [rsp+2D0h] [rbp+1D0h] BYREF
  unsigned __int16 v156[264]; // [rsp+3A0h] [rbp+2A0h] BYREF

  v2 = *((_BYTE *)this + 72);
  v3 = 0;
  v115 = a2;
  v110 = v2;
  *((_BYTE *)this + 72) = 0;
  v120 = 0;
  if ( v2 )
    tip2::tip_test<tip2::details::merged_data<_tip_InputProfilesInitializationTipTest,_tip_InputProfilesInitializationTipTest>>::open_helper(&v120);
  v5 = (CInputProfilesMasterList *)((char *)this + 16);
  updated = CInputProfilesMasterList::UpdateKeyboardLayoutProfiles(this);
  v6 = updated;
  CInputProfileAssembly::InvalidateProfiles((CInputProfilesMasterList *)((char *)this + 16), 0, 1, 0);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 20) + 80LL))(*((_QWORD *)this + 20));
  COneCoreVoidStructArray::COneCoreVoidStructArray((COneCoreVoidStructArray *)&v140, 16, v7);
  v131 = 0;
  v140 = &COneCoreStructArray<CInputProfile>::`vftable';
  v130 = &CPreloadRegKey::`vftable';
  v137 = &CPreloadRegKey::`vftable';
  v138 = 0;
  CCurrentUserKey::CCurrentUserKey((CCurrentUserKey *)&v134, v8);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputSupportForBcp47>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_InputSupportForBcp47>::GetImpl'::`2'::impl) )
  {
    RegDeleteKeyExW(hKey, L"Keyboard Layout\\Custom", 0, 0);
    RegDeleteKeyExW(hKey, L"Software\\Microsoft\\CTF\\CustomProfiles", 0, 0);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_59291947_58995668>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Bugfix_59291947_58995668>::GetImpl'::`2'::impl) )
      RegDeleteKeyExW(hKey, L"Keyboard Layout\\DirectSwitchHotKeys", 0, 0);
  }
  if ( CMyRegKey::Open(
         (CMyRegKey *)&v130,
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\CTF\\TIP\\{78CB5B0E-26ED-4FCC-854C-77E8F3D1AA80}\\Category\\Category\\{534C48C1-0607-4098-"
          "A521-4FC899C73E90}",
         0x20019u)
    && *((_BYTE *)this + 156) )
  {
    if ( v2 )
    {
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_InputProfilesInitializationTipTest,_tip_InputProfilesInitializationTipTest>>::operator->(
                              &v120,
                              &Buf1)
               + 305LL) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_InputProfilesInitializationTipTest,_tip_InputProfilesInitializationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_InputProfilesInitializationTipTest,_tip_InputProfilesInitializationTipTest>>(&Buf1);
    }
    v134 = &CPreloadRegKey::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)&v134);
    v9 = -2147467259;
    goto LABEL_253;
  }
  v10 = 1;
  for ( i = 0; !(unsigned int)CMyRegKey::EnumKey((CMyRegKey *)&v130, i, v152, 0x27u); i = v10++ )
  {
    v145 = 0;
    if ( (unsigned int)StringToCLSID(v152, &v145) )
    {
      v13 = (struct _GUID *)COneCoreVoidStructArray::Append((COneCoreVoidStructArray *)&v140, v12);
      if ( v13 )
        *v13 = v145;
    }
  }
  v15 = v142;
  if ( !v142 )
  {
    v16 = (GUID *)COneCoreVoidStructArray::Append((COneCoreVoidStructArray *)&v140, v14);
    v15 = v142;
    if ( v16 )
      *v16 = GUID_TFCAT_TIP_KEYBOARD;
  }
  CMyRegKey::Open((CMyRegKey *)&v130, HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\CTF\\TIP\\", 0x20019u);
  CMyRegKey::Open((CMyRegKey *)&v137, hKey, L"SOFTWARE\\Microsoft\\CTF\\TIP\\", 0x20019u);
  if ( v131 && v138 )
  {
    v17 = 1;
    *(_DWORD *)lpData = 1;
    if ( !(unsigned int)CMyRegKey::EnumKey((CMyRegKey *)&v130, 0, v152, 0x27u) )
    {
      do
      {
        v139 = GUID_NULL;
        v145 = 0;
        if ( (unsigned int)StringToCLSID(v152, &v145)
          && !(unsigned int)StringCchPrintfW(v155, 0x61u, L"%s%s%s", v152, L"\\Category\\Item\\", v152) )
        {
          v128 = &CPreloadRegKey::`vftable';
          v129 = 0;
          v18 = 0;
          if ( !CMyRegKey::Open((CMyRegKey *)&v128, v131, v155, 0x20019u) )
          {
            memset(Buf2, 68, sizeof(Buf2));
            v19 = 1;
            for ( j = CMyRegKey::EnumKey((CMyRegKey *)&v128, 0, v151, 0x27u);
                  !j;
                  j = CMyRegKey::EnumKey((CMyRegKey *)&v128, v22, v151, 0x27u) )
            {
              Buf1 = 0;
              if ( (unsigned int)StringToCLSID(v151, &Buf1) )
              {
                if ( (v18 & 2) != 0 || memcmp_0(&Buf1, &GUID_TFCAT_TIPCAP_SECUREMODE, 0x10u) )
                {
                  if ( (v18 & 8) != 0 || memcmp_0(&Buf1, &GUID_TFCAT_TIPCAP_COMLESS, 0x10u) )
                  {
                    if ( (v18 & 4) != 0 || memcmp_0(&Buf1, &GUID_TFCAT_TIPCAP_UIELEMENTENABLED, 0x10u) )
                    {
                      if ( (v18 & 0x10) != 0 || memcmp_0(&Buf1, &GUID_TFCAT_TIPCAP_WOW16, 0x10u) )
                      {
                        if ( (v18 & 0x20) != 0 || memcmp_0(&Buf1, &GUID_TFCAT_TIPCAP_INPUTMODECOMPARTMENT, 0x10u) )
                        {
                          if ( (v18 & 0x10000) != 0 || memcmp_0(&Buf1, &GUID_TFCAT_TIPCAP_IMMERSIVESUPPORT, 0x10u) )
                          {
                            if ( (v18 & 0x20000) != 0 || memcmp_0(&Buf1, &GUID_TFCAT_TIPCAP_SYSTRAYSUPPORT, 0x10u) )
                            {
                              if ( (v18 & 0x40000) != 0 || memcmp_0(&Buf1, &GUID_TFCAT_TIPCAP_IMMERSIVEONLY, 0x10u) )
                              {
                                if ( (v18 & 0x10000000) != 0 || memcmp_0(&Buf1, &GUID_TFCAT_TIPCAP_LOCALSERVER, 0x10u) )
                                {
                                  if ( (v18 & 0x40000000) != 0 || memcmp_0(&Buf1, &GUID_TFCAT_TIPCAP_TSF3, 0x10u) )
                                  {
                                    if ( v18 >= 0 && !memcmp_0(&Buf1, &GUID_TFCAT_TIPCAP_DUALMODE, 0x10u) )
                                    {
                                      v18 |= 0x80010000;
                                    }
                                    else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_55037899>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Bugfix_55037899>::GetImpl'::`2'::impl)
                                           && (v18 & 0x80000) == 0
                                           && !memcmp_0(&Buf1, Buf2, 0x10u) )
                                    {
                                      v18 |= 0x90002u;
                                    }
                                    else if ( !memcmp_0(&v139, &GUID_NULL, 0x10u) )
                                    {
                                      v21 = 0;
                                      if ( v15 > 0 )
                                      {
                                        while ( *(_OWORD *)&Buf1 != *(_OWORD *)((char *)lpMem + v143 * v21) )
                                        {
                                          if ( ++v21 >= v15 )
                                            goto LABEL_71;
                                        }
                                        v139 = Buf1;
                                      }
                                    }
                                  }
                                  else
                                  {
                                    v18 |= 0x40010000u;
                                  }
                                }
                                else
                                {
                                  v18 |= 0x10010000u;
                                }
                              }
                              else
                              {
                                v18 |= 0x50000u;
                              }
                            }
                            else
                            {
                              v18 |= 0x20000u;
                            }
                          }
                          else
                          {
                            v18 |= 0x10000u;
                          }
                        }
                        else
                        {
                          v18 |= 0x20u;
                        }
                      }
                      else
                      {
                        v18 |= 0x10u;
                      }
                    }
                    else
                    {
                      v18 |= 4u;
                    }
                  }
                  else
                  {
                    v18 |= 8u;
                  }
                }
                else
                {
                  v18 |= 2u;
                }
              }
LABEL_71:
              v22 = v19++;
            }
            v3 = 0;
          }
          if ( (*((_DWORD *)this + 20) & 0x100) == 0 )
          {
            if ( (v18 & 0x40000000) != 0 )
              goto LABEL_135;
            v18 &= ~0x80000000;
          }
          if ( !(unsigned int)StringCchPrintfW(v156, 0x104u, L"%s\\%s", v152, L"LanguageProfile\\")
            && !CMyRegKey::Open((CMyRegKey *)&v128, v131, v156, 0x20019u) )
          {
            *(_QWORD *)&Buf1.Data1 = 0;
            StringCchLengthW(v156, 0x104u, (unsigned __int64 *)&Buf1.Data1);
            v23 = 1;
            v132 = 1;
            if ( !(unsigned int)CMyRegKey::EnumKey((CMyRegKey *)&v128, 0, v149, 0x10u) )
            {
              while ( 1 )
              {
                if ( v149[0] != 48 || ((v149[1] - 88) & 0xFFDF) != 0 )
                  goto LABEL_133;
                v24 = wcstoul_0(String, 0, 16);
                v118 = &CPreloadRegKey::`vftable';
                v25 = v24;
                v119 = 0;
                if ( !v24 || CMyRegKey::Open((CMyRegKey *)&v118, v129, v149, 0x20019u) )
                {
                  v118 = &CPreloadRegKey::`vftable';
                  CInputDllRegKey::Close((CInputDllRegKey *)&v118);
                  goto LABEL_133;
                }
                v26 = 1;
                v133 = 1;
                if ( (unsigned int)CMyRegKey::EnumKey((CMyRegKey *)&v118, 0, v151, 0x27u) )
                  goto LABEL_131;
                do
                {
                  *(_DWORD *)Data = 0;
                  v146 = 0;
                  if ( !(unsigned int)StringToCLSID(v151, &v146) )
                    goto LABEL_129;
                  v123 = &CPreloadRegKey::`vftable';
                  v124 = 0;
                  if ( CMyRegKey::Open((CMyRegKey *)&v123, v119, v151, 0x20019u) )
                  {
                    v123 = &CPreloadRegKey::`vftable';
                    CInputDllRegKey::Close((CInputDllRegKey *)&v123);
                    goto LABEL_129;
                  }
                  v28 = 1;
                  if ( v25 == 0xFFFF )
                  {
                    SubstituteHKLfromKey = 0;
                    v25 = 0;
                  }
                  else
                  {
                    SubstituteHKLfromKey = GetSubstituteHKLfromKey((struct CMyRegKey *)&v123, v25);
                  }
                  v30 = v18;
                  if ( (v18 & 0x10000) != 0 )
                  {
                    Type = 0;
                    cbData = 4;
                    if ( !RegQueryValueExW(v124, L"ProfileFlags", 0, &Type, Data, &cbData) )
                    {
                      v30 = v18 & 0xFFFEFFFF;
                      if ( (Data[0] & 1) == 0 )
                        v30 = v18;
                      if ( (v30 & 0x10000000) != 0 )
                      {
                        if ( (Data[0] & 2) != 0 )
                        {
                          v30 &= ~0x10000000u;
                        }
                        else if ( (Data[0] & 4) != 0 )
                        {
                          v30 |= 0x20000000u;
                        }
                      }
                    }
                  }
                  if ( (*((_DWORD *)this + 20) & 0x100) != 0
                    && Tsf3OverrideUtil::IsTsf3OverrideEnabled((Tsf3OverrideUtil *)v152, 0, v27)
                    && Tsf3OverrideUtil::IsTsf3OverrideEnabled((Tsf3OverrideUtil *)v152, v151, v31) )
                  {
                    if ( v30 >= 0 )
                    {
                      if ( !Tsf3OverrideUtil::IsTsf3TableTextProfileSupported(v33, v32) )
                        goto LABEL_106;
                    }
                    else
                    {
                      v30 &= 0x3FFEFFFFu;
                    }
                    v30 |= 0x40010000u;
                  }
LABEL_106:
                  cbData = 0;
                  Type = 4;
                  if ( !RegQueryValueExW(v124, L"Enable", 0, &cbData, Data, &Type) )
                  {
                    v34 = *(_DWORD *)Data;
                    v28 = *(_DWORD *)Data != 0;
                    if ( v110 )
                    {
                      if ( !memcmp_0(&v139, &GUID_TFCAT_TIP_KEYBOARD, 0x10u) )
                      {
                        if ( v34 )
                        {
                          v37 = tip2::tip_test<tip2::details::merged_data<_tip_InputProfilesInitializationTipTest,_tip_InputProfilesInitializationTipTest>>::operator->(
                                  &v120,
                                  &v126);
                          ++*(_DWORD *)(*(_QWORD *)v37 + 312LL);
                          v36 = &v126;
                        }
                        else
                        {
                          v35 = tip2::tip_test<tip2::details::merged_data<_tip_InputProfilesInitializationTipTest,_tip_InputProfilesInitializationTipTest>>::operator->(
                                  &v120,
                                  &v136);
                          ++*(_DWORD *)(*(_QWORD *)v35 + 316LL);
                          v36 = &v136;
                        }
                        tip2::test_data_control<tip2::details::merged_data<_tip_InputProfilesInitializationTipTest,_tip_InputProfilesInitializationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_InputProfilesInitializationTipTest,_tip_InputProfilesInitializationTipTest>>(v36);
                      }
                    }
                  }
                  if ( !(unsigned int)StringCchPrintfW(
                                        &v156[*(_QWORD *)&Buf1.Data1],
                                        260LL - *(_QWORD *)&Buf1.Data1,
                                        L"\\%s\\%s",
                                        v149,
                                        v151)
                    && !CMyRegKey::Open((CMyRegKey *)&v123, v138, v156, 0x20019u) )
                  {
                    cbData = 0;
                    Type = 4;
                    if ( !RegQueryValueExW(v124, L"Enable", 0, &cbData, Data, &Type) )
                    {
                      v38 = *(_DWORD *)Data;
                      v28 = *(_DWORD *)Data != 0;
                      if ( v110 )
                      {
                        if ( !memcmp_0(&v139, &GUID_TFCAT_TIP_KEYBOARD, 0x10u) )
                        {
                          if ( v38 )
                          {
                            v41 = tip2::tip_test<tip2::details::merged_data<_tip_InputProfilesInitializationTipTest,_tip_InputProfilesInitializationTipTest>>::operator->(
                                    &v120,
                                    &v116);
                            ++*(_DWORD *)(*(_QWORD *)v41 + 320LL);
                            v40 = &v116;
                          }
                          else
                          {
                            v39 = tip2::tip_test<tip2::details::merged_data<_tip_InputProfilesInitializationTipTest,_tip_InputProfilesInitializationTipTest>>::operator->(
                                    &v120,
                                    &v127);
                            ++*(_DWORD *)(*(_QWORD *)v39 + 324LL);
                            v40 = &v127;
                          }
                          tip2::test_data_control<tip2::details::merged_data<_tip_InputProfilesInitializationTipTest,_tip_InputProfilesInitializationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_InputProfilesInitializationTipTest,_tip_InputProfilesInitializationTipTest>>(v40);
                        }
                      }
                    }
                  }
                  v42 = CInputProfileAssembly::AddProfile(
                          (CInputProfilesMasterList *)((char *)this + 16),
                          v25,
                          &v145,
                          &v146,
                          0,
                          &v139,
                          SubstituteHKLfromKey,
                          v28 ? 2 : 0,
                          v30,
                          0);
                  updated |= v42 == 0;
                  if ( v28 )
                  {
                    if ( (v30 & 0x10000000) != 0 )
                    {
                      v43 = (__int64 *)*((_QWORD *)this + 20);
                      v44 = *v43;
                      pwszKLID = v145;
                      (*(void (__fastcall **)(__int64 *, struct _GUID *, _QWORD, struct _GUID *))(v44 + 72))(
                        v43,
                        &pwszKLID,
                        v25,
                        &v146);
                    }
                    if ( SubstituteHKLfromKey )
                    {
                      memset_0(v153, 0, 0x58u);
                      v153[8] = v25;
                      v154 = (int)SubstituteHKLfromKey;
                      EnabledProfile = CInputProfileAssembly::FindEnabledProfile(
                                         (CInputProfilesMasterList *)((char *)this + 16),
                                         (struct CoreInputProfile *)v153);
                      if ( EnabledProfile )
                      {
                        *((_BYTE *)EnabledProfile + 70) |= 8u;
                        ++*((_DWORD *)this + 21);
                        UnloadKeyboardLayout(SubstituteHKLfromKey);
                        --*((_DWORD *)this + 21);
                      }
                    }
                  }
                  v123 = &CPreloadRegKey::`vftable';
                  CInputDllRegKey::Close((CInputDllRegKey *)&v123);
                  v26 = v133;
LABEL_129:
                  v46 = v26++;
                  v133 = v26;
                }
                while ( !(unsigned int)CMyRegKey::EnumKey((CMyRegKey *)&v118, v46, v151, 0x27u) );
                v23 = v132;
LABEL_131:
                v118 = &CPreloadRegKey::`vftable';
                CInputDllRegKey::Close((CInputDllRegKey *)&v118);
                v3 = 0;
LABEL_133:
                v47 = v23++;
                v132 = v23;
                if ( (unsigned int)CMyRegKey::EnumKey((CMyRegKey *)&v128, v47, v149, 0x10u) )
                {
                  v17 = *(_DWORD *)lpData;
                  break;
                }
              }
            }
          }
LABEL_135:
          v128 = &CPreloadRegKey::`vftable';
          CInputDllRegKey::Close((CInputDllRegKey *)&v128);
        }
        v48 = v17++;
        *(_DWORD *)lpData = v17;
        v49 = CMyRegKey::EnumKey((CMyRegKey *)&v130, v48, v152, 0x27u);
        v15 = v142;
      }
      while ( !v49 );
      v2 = v110;
      v5 = (CInputProfilesMasterList *)((char *)this + 16);
    }
    v6 = updated;
  }
  else if ( v2 )
  {
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_InputProfilesInitializationTipTest,_tip_InputProfilesInitializationTipTest>>::operator->(
                            &v120,
                            &v116)
             + 306LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_InputProfilesInitializationTipTest,_tip_InputProfilesInitializationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_InputProfilesInitializationTipTest,_tip_InputProfilesInitializationTipTest>>(&v116);
  }
  Buf2[0] = &CPreloadRegKey::`vftable';
  Buf2[1] = 0;
  if ( CMyRegKey::Open((CMyRegKey *)Buf2, hKey, L"SOFTWARE\\Microsoft\\CTF\\Assemblies", 0x20019u) )
    goto LABEL_169;
  v50 = 1;
  if ( (unsigned int)CMyRegKey::EnumKey((CMyRegKey *)Buf2, 0, (unsigned __int16 *)&pwszKLID, 0xBu) )
    goto LABEL_169;
  do
  {
    if ( LOWORD(pwszKLID.Data1) != 48 )
      goto LABEL_167;
    if ( ((HIWORD(pwszKLID.Data1) - 88) & 0xFFDF) != 0 )
      goto LABEL_167;
    v148 = 0;
    v51 = wcstoul_0(&pwszKLID.Data2, 0, 16);
    if ( !v51 )
      goto LABEL_167;
    InputLanguage = CInputProfileAssembly::GetInputLanguage(v5, v51, 0);
    if ( !InputLanguage )
      goto LABEL_167;
    v123 = &CPreloadRegKey::`vftable';
    v124 = 0;
    if ( CMyRegKey::Open((CMyRegKey *)&v123, (HKEY)Buf2[1], (const unsigned __int16 *)&pwszKLID, 0x20019u) )
      goto LABEL_166;
    v53 = 1;
    if ( (unsigned int)CMyRegKey::EnumKey((CMyRegKey *)&v123, 0, v153, 0x27u) )
      goto LABEL_165;
    do
    {
      *(_DWORD *)lpData = 0;
      v118 = &CPreloadRegKey::`vftable';
      v119 = 0;
      v145 = 0;
      v146 = 0;
      if ( !CMyRegKey::Open((CMyRegKey *)&v118, v124, v153, 0x20019u)
        && !CMyRegKey::QueryValueCch((CMyRegKey *)&v118, v151, L"Default", 0x27u)
        && (unsigned int)StringToCLSID(v151, &v145) )
      {
        if ( !memcmp_0(&v145, &GUID_NULL, 0x10u) )
        {
          cbData = 0;
          Type = 4;
          if ( RegQueryValueExW(v119, L"KeyboardLayout", 0, &cbData, lpData, &Type) )
            goto LABEL_163;
          v54 = (HKL)*(int *)lpData;
          v55 = &GUID_NULL;
          v56 = &GUID_NULL;
        }
        else
        {
          if ( CMyRegKey::QueryValueCch((CMyRegKey *)&v118, v151, L"Profile", 0x27u)
            || !(unsigned int)StringToCLSID(v151, &v146) )
          {
            goto LABEL_163;
          }
          v55 = &v146;
          v54 = 0;
          v56 = &v145;
        }
        InputProfile = CInputLanguage::GetInputProfile(InputLanguage, v54, v56, v55);
        if ( InputProfile
          && (*((_QWORD *)InputProfile + 3) != *(_QWORD *)&GUID_NULL.Data1
           || *((_QWORD *)InputProfile + 4) != *(_QWORD *)GUID_NULL.Data4)
          && (*((_BYTE *)InputProfile + 68) & 4) == 0 )
        {
          CInputLanguage::SetDefaultProfileFlag(InputLanguage, InputProfile);
          v6 = 1;
        }
      }
LABEL_163:
      v118 = &CPreloadRegKey::`vftable';
      CInputDllRegKey::Close((CInputDllRegKey *)&v118);
      v58 = v53++;
    }
    while ( !(unsigned int)CMyRegKey::EnumKey((CMyRegKey *)&v123, v58, v153, 0x27u) );
    v5 = (CInputProfilesMasterList *)((char *)this + 16);
LABEL_165:
    v3 = 0;
LABEL_166:
    v123 = &CPreloadRegKey::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)&v123);
LABEL_167:
    v59 = v50++;
  }
  while ( !(unsigned int)CMyRegKey::EnumKey((CMyRegKey *)Buf2, v59, (unsigned __int16 *)&pwszKLID, 0xBu) );
  v2 = v110;
LABEL_169:
  if ( GetSystemMetrics(4096) )
  {
    if ( v2 )
    {
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_InputProfilesInitializationTipTest,_tip_InputProfilesInitializationTipTest>>::operator->(
                              &v120,
                              &v116)
               + 308LL) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_InputProfilesInitializationTipTest,_tip_InputProfilesInitializationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_InputProfilesInitializationTipTest,_tip_InputProfilesInitializationTipTest>>(&v116);
    }
    *(_DWORD *)lpData = 0;
    v118 = &CPreloadRegKey::`vftable';
    v119 = 0;
    v145 = 0;
    v146 = 0;
    if ( !CMyRegKey::Open((CMyRegKey *)&v118, hKey, L"Software\\Microsoft\\CTF\\RemoteSession", 0x20019u)
      && !CMyRegKey::QueryValueCch((CMyRegKey *)&v118, v153, L"CLSID", 0x27u) )
    {
      if ( (unsigned int)StringToCLSID(v153, &v145) )
      {
        if ( !CMyRegKey::QueryValueCch((CMyRegKey *)&v118, v151, L"Profile", 0x27u) )
        {
          if ( (unsigned int)StringToCLSID(v151, &v146) )
          {
            cbData = 0;
            Type = 4;
            if ( !RegQueryValueExW(v119, L"KeyboardLayout", 0, &cbData, lpData, &Type) )
            {
              v60 = (HKL)*(int *)lpData;
              if ( !memcmp_0(&v145, &GUID_NULL, 0x10u) )
              {
                v61 = CLayoutIDs::ConvertFromHKLToLayout((CInputProfilesMasterList *)((char *)this + 88), v60);
                v62 = CInputProfileAssembly::AddProfile(v5, v60, v61, 0xFFFFFFFF, 0);
                v3 = 0;
                ++*((_DWORD *)this + 21);
                v6 |= v62 == 0;
                StringCchPrintfW((unsigned __int16 *)&pwszKLID, 0xAu, L"%08x", v61);
                LoadKeyboardLayoutW((LPCWSTR)&pwszKLID, 2u);
                --*((_DWORD *)this + 21);
              }
              else
              {
                v63 = CInputProfileAssembly::GetInputLanguage(v5, (unsigned __int16)v60, 0);
                v3 = 0;
                if ( v63 )
                {
                  v64 = CInputLanguage::GetInputProfile(v63, 0, &v145, &v146);
                  if ( v64 )
                  {
                    v65 = *((_BYTE *)v64 + 68);
                    if ( (v65 & 8) == 0 )
                    {
                      v6 = 1;
                      *((_BYTE *)v64 + 68) = v65 | 8;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    v118 = &CPreloadRegKey::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)&v118);
  }
  v66 = CInputProfileAssembly::ClearRemovedProfiles(v5, 1, 0) | v6;
  if ( !GetSystemMetrics(67) )
    goto LABEL_210;
  if ( v2 )
  {
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_InputProfilesInitializationTipTest,_tip_InputProfilesInitializationTipTest>>::operator->(
                            &v120,
                            &v116)
             + 307LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_InputProfilesInitializationTipTest,_tip_InputProfilesInitializationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_InputProfilesInitializationTipTest,_tip_InputProfilesInitializationTipTest>>(&v116);
  }
  v67 = 0;
  if ( *((int *)this + 10) <= 0 )
    goto LABEL_210;
  while ( 2 )
  {
    v68 = *(_QWORD *)(*((_QWORD *)this + 4) + 8LL * v3);
    if ( *(_WORD *)v68 == (_WORD)v67 || *(int *)(v68 + 40) <= 0 )
      goto LABEL_209;
    v69 = v67;
    v70 = v67;
    while ( 2 )
    {
      if ( !(unsigned int)CInputProfile::IsEnabled((CInputProfile *)(*(_QWORD *)(v68 + 32) + *(_DWORD *)(v68 + 44) * v70)) )
      {
        if ( !v73 )
        {
          IsSystemKeyboardTIPorIME = CInputProfile::IsSystemKeyboardTIPorIME(v71);
          v67 = 0;
          if ( IsSystemKeyboardTIPorIME )
LABEL_202:
            v73 = v76;
        }
LABEL_203:
        if ( ++v70 >= v72 )
          goto LABEL_206;
        continue;
      }
      break;
    }
    if ( !(unsigned int)CInputProfile::IsKeyboardTIPorIME(v71) )
      goto LABEL_203;
    v75 = CInputProfile::IsSystemKeyboardTIPorIME(v74);
    v67 = 0;
    if ( !v75 )
    {
      v69 = 1;
      *(_BYTE *)(v76 + 68) = v77 & 0xFB;
      v72 = *(_DWORD *)(v68 + 40);
      goto LABEL_203;
    }
    if ( (v77 & 4) == 0 )
    {
      if ( !v73 || (*(_BYTE *)(v73 + 68) & 4) == 0 )
        goto LABEL_202;
      goto LABEL_203;
    }
    v73 = 0;
LABEL_206:
    if ( v69 && v73 )
      *(_BYTE *)(v73 + 68) |= 0xCu;
LABEL_209:
    if ( ++v3 < *((_DWORD *)this + 10) )
      continue;
    break;
  }
LABEL_210:
  if ( IsUserSystem() )
  {
    v79 = 0;
    if ( *((int *)this + 10) > 0 )
    {
      v80 = 0;
      do
      {
        v81 = *(_QWORD *)(*((_QWORD *)this + 4) + 8LL * v79);
        if ( *(_WORD *)v81 != (_WORD)v80 )
        {
          v82 = v80;
          if ( *(_DWORD *)(v81 + 40) > (int)v80 )
          {
            v83 = *(_QWORD *)(v81 + 32);
            v84 = (int)v80;
            while ( 1 )
            {
              v85 = (unsigned __int16 *)(v83 + *(_DWORD *)(v81 + 44) * v84);
              if ( (unsigned int)CInputProfile::IsEnabled((CInputProfile *)v85) )
              {
                if ( (unsigned int)CInputProfile::IsSystemKeyboardTIPorIME(v86) )
                  break;
              }
              v84 = v87 + 1;
              if ( v84 >= *(_DWORD *)(v81 + 40) )
                goto LABEL_225;
            }
            v88 = IsDictionaryReady(v85[1]);
            v80 = 0;
            if ( v88 )
            {
              v82 = v85;
            }
            else if ( (unsigned int)dword_18013D0D8 > 4
                   && (unsigned __int8)tlgKeywordOn(&dword_18013D0D8, 0x400000080000LL) )
            {
              v126 = 0x2000000;
              v116 = v85 + 20;
              v127 = v85 + 4;
              Type = v85[1];
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(
                v89,
                (unsigned int)byte_180128F93,
                v90,
                v91,
                (__int64)&v126,
                (__int64)&Type,
                (__int64)&v127,
                (__int64)&v116);
              v80 = 0;
            }
          }
LABEL_225:
          for ( k = (int)v80; k < *(_DWORD *)(v81 + 40); v80 = 0 )
          {
            if ( (unsigned int)CInputProfile::IsEnabled((CInputProfile *)(*(_QWORD *)(v81 + 32)
                                                                        + *(_DWORD *)(v81 + 44) * k))
              && (unsigned int)CInputProfile::IsKeyboardTIPorIME(v93)
              && !(unsigned int)CInputProfile::IsSystemKeyboardTIPorIME(v94) )
            {
              if ( v82 )
              {
                *(_BYTE *)(v95 + 68) &= ~0x40u;
                v96 = *(_BYTE *)(v95 + 68);
                if ( (v96 & 4) != 0 )
                {
                  *(_BYTE *)(v95 + 68) = v96 & 0xFB;
                  *((_BYTE *)v82 + 68) |= 4u;
                }
                v66 = 1;
                if ( (unsigned int)dword_18013D0D8 > 4
                  && (unsigned __int8)tlgKeywordOn(&dword_18013D0D8, 0x400000080000LL) )
                {
                  *(_QWORD *)&Buf1.Data1 = 0x2000000;
                  v116 = v82 + 20;
                  v127 = v82 + 4;
                  v126 = v98 + 40;
                  v136 = v98 + 8;
                  Type = *(unsigned __int16 *)(v98 + 2);
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(
                    v97,
                    (unsigned int)&dword_180128EA4,
                    v98,
                    v99,
                    (__int64)&Buf1,
                    (__int64)&Type,
                    (__int64)&v136,
                    (__int64)&v126,
                    (__int64)&v127,
                    (__int64)&v116);
                }
              }
              else if ( (unsigned int)dword_18013D0D8 > 4
                     && (unsigned __int8)tlgKeywordOn(&dword_18013D0D8, 0x400000080000LL) )
              {
                v126 = 0x2000000;
                v116 = v101 + 20;
                v127 = v101 + 4;
                Type = v101[1];
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(
                  v100,
                  (unsigned int)&byte_180128F27,
                  (_DWORD)v101,
                  v102,
                  (__int64)&v126,
                  (__int64)&Type,
                  (__int64)&v127,
                  (__int64)&v116);
              }
            }
            ++k;
          }
        }
        ++v79;
      }
      while ( v79 < *((_DWORD *)this + 10) );
      v5 = (CInputProfilesMasterList *)((char *)this + 16);
    }
  }
  ++*((_DWORD *)this + 21);
  v103 = CInputProfilesMasterList::EnsureEnabledLanguage(this);
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_InputProfilesInitializationTipTest,_tip_InputProfilesInitializationTipTest>>::operator->(
                          &v120,
                          &v116)
           + 310LL) = v103;
  tip2::test_data_control<tip2::details::merged_data<_tip_InputProfilesInitializationTipTest,_tip_InputProfilesInitializationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_InputProfilesInitializationTipTest,_tip_InputProfilesInitializationTipTest>>(&v116);
  CInputProfilesMasterList::EnsurePrimaryLayouts(this);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 20) + 88LL))(*((_QWORD *)this + 20));
  --*((_DWORD *)this + 21);
  CInputProfilesMasterList::UpdateSortOrder(this);
  if ( v66 | (unsigned int)CInputProfileAssembly::Sort(v5) )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 20) + 32LL))(*((_QWORD *)this + 20));
  CInputProfilesMasterList::UpdateCache(this, 1);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 20) + 64LL))(*((_QWORD *)this + 20));
  if ( v115 )
  {
    for ( m = 0; m < *((_DWORD *)this + 10); ++m )
    {
      v105 = *(unsigned __int16 **)(*((_QWORD *)this + 4) + 8LL * m);
      if ( *((_BYTE *)v105 + 20) )
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 20) + 40LL))(*((_QWORD *)this + 20), *v105);
      if ( *((_BYTE *)v105 + 21) )
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 20) + 48LL))(*((_QWORD *)this + 20), *v105);
    }
  }
  v106 = *(_QWORD *)this;
  v112[0] = 0;
  (*(void (__fastcall **)(CInputProfilesMasterList *, char *))(v106 + 56))(this, v112);
  v107 = *((_BYTE *)this + 136);
  if ( v107 != v112[0] )
  {
    v108 = *((_QWORD *)this + 20);
    *((_BYTE *)this + 136) = v107 == 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v108 + 56LL))(v108);
  }
  Buf2[0] = &CPreloadRegKey::`vftable';
  CInputDllRegKey::Close((CInputDllRegKey *)Buf2);
  v134 = &CPreloadRegKey::`vftable';
  CInputDllRegKey::Close((CInputDllRegKey *)&v134);
  v137 = &CPreloadRegKey::`vftable';
  v9 = 0;
LABEL_253:
  CInputDllRegKey::Close((CInputDllRegKey *)&v137);
  v130 = &CPreloadRegKey::`vftable';
  CInputDllRegKey::Close((CInputDllRegKey *)&v130);
  HeapFree(hHeap, 8u, lpMem);
  wil::com_ptr_t<tip2::details::merged_data<_tip_InputProfilesInitializationTipTest,_tip_InputProfilesInitializationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_InputProfilesInitializationTipTest,_tip_InputProfilesInitializationTipTest>,wil::err_returncode_policy>(&v120);
  return v9;
}

```

## disassembly

```asm
0x1800d5b30  push    rbp
0x1800d5b32  push    rbx
0x1800d5b33  push    rsi
0x1800d5b34  push    rdi
0x1800d5b35  push    r12
0x1800d5b37  push    r13
0x1800d5b39  push    r14
0x1800d5b3b  push    r15
0x1800d5b3d  lea     rbp, [rsp-4C8h]
0x1800d5b45  sub     rsp, 5C8h
0x1800d5b4c  mov     rax, cs:__security_cookie
0x1800d5b53  xor     rax, rsp
0x1800d5b56  mov     [rbp+500h+var_50], rax
0x1800d5b5d  mov     r15b, [rcx+48h]
0x1800d5b61  xor     esi, esi
0x1800d5b63  mov     [rsp+600h+var_59C], dl
0x1800d5b67  mov     rdi, rcx
0x1800d5b6a  mov     [rsp+600h+var_5B0], r15b
0x1800d5b6f  mov     [rcx+48h], sil
0x1800d5b73  mov     [rbp+500h+var_578], rsi
0x1800d5b77  test    r15b, r15b
0x1800d5b7a  jz      short loc_1800D5B85
0x1800d5b7c  lea     rcx, [rbp+500h+var_578]
0x1800d5b80  call    ?open_helper@?$tip_test@V?$merged_data@U_tip_InputProfilesInitializationTipTest@@U1@@details@tip2@@@tip2@@AEAA_NPEAU_GUID@@@Z; tip2::tip_test<tip2::details::merged_data<_tip_InputProfilesInitializationTipTest,_tip_InputProfilesInitializationTipTest>>::open_helper(_GUID *)
0x1800d5b85  mov     rcx, rdi; this
0x1800d5b88  call    ?UpdateKeyboardLayoutProfiles@CInputProfilesMasterList@@AEAAHXZ; CInputProfilesMasterList::UpdateKeyboardLayoutProfiles(void)
0x1800d5b8d  lea     r13, [rdi+10h]
0x1800d5b91  mov     [rbp+500h+var_560], eax
0x1800d5b94  mov     rcx, r13; this
0x1800d5b97  xor     r9d, r9d; bool
0x1800d5b9a  mov     r8b, 1; bool
0x1800d5b9d  xor     edx, edx; bool
0x1800d5b9f  mov     r12d, eax
0x1800d5ba2  call    ?InvalidateProfiles@CInputProfileAssembly@@IEAAX_N00@Z; CInputProfileAssembly::InvalidateProfiles(bool,bool,bool)
0x1800d5ba7  mov     rcx, [rdi+0A0h]
0x1800d5bae  mov     rax, [rcx]
0x1800d5bb1  mov     rax, [rax+50h]
0x1800d5bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5bba  mov     edx, 10h; int
0x1800d5bbf  lea     rcx, [rbp+500h+var_4C0]; this
0x1800d5bc3  call    ??0COneCoreVoidStructArray@@QEAA@HH@Z; COneCoreVoidStructArray::COneCoreVoidStructArray(int,int)
0x1800d5bc8  lea     rax, ??_7?$COneCoreStructArray@UCInputProfile@@@@6B@; const COneCoreStructArray<CInputProfile>::`vftable'
0x1800d5bcf  mov     [rbp+500h+var_510], rsi
0x1800d5bd3  lea     r14, ??_7CPreloadRegKey@@6B@; const CPreloadRegKey::`vftable'
0x1800d5bda  mov     [rbp+500h+var_4C0], rax
0x1800d5bde  lea     rcx, [rbp+500h+var_500]; this
0x1800d5be2  mov     [rbp+500h+var_518], r14
0x1800d5be6  mov     [rbp+500h+var_4E8], r14
0x1800d5bea  mov     [rbp+500h+var_4E0], rsi
0x1800d5bee  call    ??0CCurrentUserKey@@QEAA@K@Z; CCurrentUserKey::CCurrentUserKey(ulong)
0x1800d5bf3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InputSupportForBcp47@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InputSupportForBcp47@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputSupportForBcp47> `wil::Feature<__WilFeatureTraits_Feature_InputSupportForBcp47>::GetImpl(void)'::`2'::impl
0x1800d5bfa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InputSupportForBcp47@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputSupportForBcp47>::__private_IsEnabled(void)
0x1800d5bff  test    al, al
0x1800d5c01  jnz     short loc_1800D5C58
0x1800d5c03  mov     rcx, [rbp+500h+hKey]; hKey
0x1800d5c07  lea     rdx, aKeyboardLayout; "Keyboard Layout\\Custom"
0x1800d5c0e  xor     r9d, r9d; Reserved
0x1800d5c11  xor     r8d, r8d; samDesired
0x1800d5c14  call    cs:__imp_RegDeleteKeyExW
0x1800d5c1a  mov     rcx, [rbp+500h+hKey]; hKey
0x1800d5c1e  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\CTF\\CustomProfile"...
0x1800d5c25  xor     r9d, r9d; Reserved
0x1800d5c28  xor     r8d, r8d; samDesired
0x1800d5c2b  call    cs:__imp_RegDeleteKeyExW
0x1800d5c31  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Bugfix_59291947_58995668@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_59291947_58995668@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_59291947_58995668> `wil::Feature<__WilFeatureTraits_Feature_Bugfix_59291947_58995668>::GetImpl(void)'::`2'::impl
0x1800d5c38  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_59291947_58995668@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_59291947_58995668>::__private_IsEnabled(void)
0x1800d5c3d  test    al, al
0x1800d5c3f  jz      short loc_1800D5C58
0x1800d5c41  mov     rcx, [rbp+500h+hKey]; hKey
0x1800d5c45  lea     rdx, aKeyboardLayout_0; "Keyboard Layout\\DirectSwitchHotKeys"
0x1800d5c4c  xor     r9d, r9d; Reserved
0x1800d5c4f  xor     r8d, r8d; samDesired
0x1800d5c52  call    cs:__imp_RegDeleteKeyExW
0x1800d5c58  mov     r9d, 20019h; unsigned int
0x1800d5c5e  lea     r8, ?c_szCTFSystemCategoryKey@@3QBGB; "SOFTWARE\\Microsoft\\CTF\\TIP\\{78CB5B0"...
0x1800d5c65  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1800d5c6c  lea     rcx, [rbp+500h+var_518]; this
0x1800d5c70  call    ?Open@CMyRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CMyRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800d5c75  test    eax, eax
0x1800d5c77  jz      short loc_1800D5CBE
0x1800d5c79  cmp     [rdi+9Ch], sil
0x1800d5c80  jz      short loc_1800D5CBE
0x1800d5c82  test    r15b, r15b
0x1800d5c85  jz      short loc_1800D5CA7
0x1800d5c87  lea     rdx, [rbp+500h+Buf1]
0x1800d5c8b  lea     rcx, [rbp+500h+var_578]
0x1800d5c8f  call    ??C?$tip_test@V?$merged_data@U_tip_InputProfilesInitializationTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_InputProfilesInitializationTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_InputProfilesInitializationTipTest,_tip_InputProfilesInitializationTipTest>>::operator->(void)
0x1800d5c94  mov     rcx, [rax]
0x1800d5c97  mov     byte ptr [rcx+131h], 1
0x1800d5c9e  lea     rcx, [rbp+500h+Buf1]
0x1800d5ca2  call    ??1?$test_data_control@V?$merged_data@U_tip_InputProfilesInitializationTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_InputProfilesInitializationTipTest,_tip_InputProfilesInitializationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_InputProfilesInitializationTipTest,_tip_InputProfilesInitializationTipTest>>(void)
0x1800d5ca7  lea     rcx, [rbp+500h+var_500]; this
0x1800d5cab  mov     [rbp+500h+var_500], r14
0x1800d5caf  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x1800d5cb4  mov     ebx, 80004005h
0x1800d5cb9  jmp     loc_1800D7168
0x1800d5cbe  mov     ebx, 1
0x1800d5cc3  xor     edx, edx
0x1800d5cc5  lea     r14d, [rbx+26h]
0x1800d5cc9  jmp     short loc_1800D5D00
0x1800d5ccb  xorps   xmm0, xmm0
0x1800d5cce  lea     rdx, [rbp+500h+var_490]; struct _GUID *
0x1800d5cd2  lea     rcx, [rbp+500h+var_3E0]; unsigned __int16 *
0x1800d5cd9  movups  xmmword ptr [rbp+500h+var_490.Data1], xmm0
0x1800d5cdd  call    ?StringToCLSID@@YAHPEBGPEAU_GUID@@@Z; StringToCLSID(ushort const *,_GUID *)
0x1800d5ce2  test    eax, eax
0x1800d5ce4  jz      short loc_1800D5CFC
0x1800d5ce6  lea     rcx, [rbp+500h+var_4C0]; this
0x1800d5cea  call    ?Append@COneCoreVoidStructArray@@QEAAPEAXH@Z; COneCoreVoidStructArray::Append(int)
0x1800d5cef  test    rax, rax
0x1800d5cf2  jz      short loc_1800D5CFC
0x1800d5cf4  movups  xmm0, xmmword ptr [rbp+500h+var_490.Data1]
0x1800d5cf8  movdqu  xmmword ptr [rax], xmm0
0x1800d5cfc  mov     edx, ebx; unsigned int
0x1800d5cfe  inc     ebx
0x1800d5d00  mov     r9d, r14d; unsigned int
0x1800d5d03  lea     r8, [rbp+500h+var_3E0]; unsigned __int16 *
0x1800d5d0a  lea     rcx, [rbp+500h+var_518]; this
0x1800d5d0e  call    ?EnumKey@CMyRegKey@@QEAAJKPEAGK@Z; CMyRegKey::EnumKey(ulong,ushort *,ulong)
0x1800d5d13  test    eax, eax
0x1800d5d15  jz      short loc_1800D5CCB
0x1800d5d17  mov     r14, [rbp+500h+var_4B0]
0x1800d5d1b  test    r14d, r14d
0x1800d5d1e  jnz     short loc_1800D5D3D
0x1800d5d20  lea     rcx, [rbp+500h+var_4C0]; this
0x1800d5d24  call    ?Append@COneCoreVoidStructArray@@QEAAPEAXH@Z; COneCoreVoidStructArray::Append(int)
0x1800d5d29  mov     r14, [rbp+500h+var_4B0]
0x1800d5d2d  test    rax, rax
0x1800d5d30  jz      short loc_1800D5D3D
0x1800d5d32  movups  xmm0, xmmword ptr cs:GUID_TFCAT_TIP_KEYBOARD.Data1
0x1800d5d39  movdqu  xmmword ptr [rax], xmm0
0x1800d5d3d  mov     ebx, 20019h
0x1800d5d42  lea     r8, ?c_szCTFTIPKey@@3QBGB; "SOFTWARE\\Microsoft\\CTF\\TIP\\"
0x1800d5d49  mov     r9d, ebx; unsigned int
0x1800d5d4c  lea     rcx, [rbp+500h+var_518]; this
0x1800d5d50  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1800d5d57  call    ?Open@CMyRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CMyRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800d5d5c  mov     rdx, [rbp+500h+hKey]; HKEY
0x1800d5d60  lea     r8, ?c_szCTFTIPKey@@3QBGB; "SOFTWARE\\Microsoft\\CTF\\TIP\\"
0x1800d5d67  mov     r9d, ebx; unsigned int
0x1800d5d6a  lea     rcx, [rbp+500h+var_4E8]; this
0x1800d5d6e  call    ?Open@CMyRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CMyRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800d5d73  cmp     [rbp+500h+var_510], rsi
0x1800d5d77  jz      loc_1800D690B
0x1800d5d7d  cmp     [rbp+500h+var_4E0], rsi
0x1800d5d81  jz      loc_1800D690B
0x1800d5d87  mov     r12d, 1
0x1800d5d8d  lea     r8, [rbp+500h+var_3E0]; unsigned __int16 *
0x1800d5d94  xor     edx, edx; unsigned int
0x1800d5d96  mov     dword ptr [rsp+600h+var_5A0], r12d
0x1800d5d9b  lea     rcx, [rbp+500h+var_518]; this
0x1800d5d9f  lea     r9d, [r12+26h]; unsigned int
0x1800d5da4  call    ?EnumKey@CMyRegKey@@QEAAJKPEAGK@Z; CMyRegKey::EnumKey(ulong,ushort *,ulong)
0x1800d5da9  test    eax, eax
0x1800d5dab  jnz     loc_1800D6709
0x1800d5db1  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x1800d5db8  lea     rdx, [rbp+500h+var_490]; struct _GUID *
0x1800d5dbc  xorps   xmm0, xmm0
0x1800d5dbf  lea     rcx, [rbp+500h+var_3E0]; unsigned __int16 *
0x1800d5dc6  movdqu  xmmword ptr [rbp+500h+var_4D0.Data1], xmm1
0x1800d5dcb  movups  xmmword ptr [rbp+500h+var_490.Data1], xmm0
0x1800d5dcf  call    ?StringToCLSID@@YAHPEBGPEAU_GUID@@@Z; StringToCLSID(ushort const *,_GUID *)
0x1800d5dd4  test    eax, eax
0x1800d5dd6  jz      loc_1800D66D3
0x1800d5ddc  lea     rax, [rbp+500h+var_3E0]
0x1800d5de3  mov     edx, 61h ; 'a'; unsigned __int64
0x1800d5de8  mov     [rsp+600h+lpcbData], rax
0x1800d5ded  lea     r9, [rbp+500h+var_3E0]
0x1800d5df4  lea     rax, ?c_szCategoryItem@@3QBGB; "\\Category\\Item\\"
0x1800d5dfb  lea     r8, aSSS; "%s%s%s"
0x1800d5e02  mov     [rsp+600h+lpData], rax
0x1800d5e07  lea     rcx, [rbp+500h+var_330]; unsigned __int16 *
0x1800d5e0e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800d5e13  test    eax, eax
0x1800d5e15  jnz     loc_1800D66D3
0x1800d5e1b  mov     rdx, [rbp+500h+var_510]; HKEY
0x1800d5e1f  lea     r15, ??_7CPreloadRegKey@@6B@; const CPreloadRegKey::`vftable'
0x1800d5e26  mov     r9d, 20019h; unsigned int
0x1800d5e2c  mov     [rbp+500h+var_528], r15
0x1800d5e30  lea     r8, [rbp+500h+var_330]; unsigned __int16 *
0x1800d5e37  mov     [rbp+500h+var_520], rsi
0x1800d5e3b  lea     rcx, [rbp+500h+var_528]; this
0x1800d5e3f  mov     ebx, esi
0x1800d5e41  call    ?Open@CMyRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CMyRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800d5e46  test    eax, eax
0x1800d5e48  jnz     loc_1800D60FC
0x1800d5e4e  lea     r9d, [rax+27h]; unsigned int
0x1800d5e52  mov     dword ptr [rbp+500h+Buf2], 44444444h
0x1800d5e59  lea     r8, [rbp+500h+var_430]; unsigned __int16 *
0x1800d5e60  mov     dword ptr [rbp+500h+Buf2+4], 44444444h
0x1800d5e67  xor     edx, edx; unsigned int
0x1800d5e69  mov     dword ptr [rbp+500h+var_540], 44444444h
0x1800d5e70  lea     rcx, [rbp+500h+var_528]; this
0x1800d5e74  mov     dword ptr [rbp+500h+var_540+4], 44444444h
0x1800d5e7b  lea     esi, [rax+1]
0x1800d5e7e  call    ?EnumKey@CMyRegKey@@QEAAJKPEAGK@Z; CMyRegKey::EnumKey(ulong,ushort *,ulong)
0x1800d5e83  xor     r15d, r15d
0x1800d5e86  test    eax, eax
0x1800d5e88  jnz     loc_1800D60F3
0x1800d5e8e  xorps   xmm0, xmm0
0x1800d5e91  lea     rdx, [rbp+500h+Buf1]; struct _GUID *
0x1800d5e95  lea     rcx, [rbp+500h+var_430]; unsigned __int16 *
0x1800d5e9c  movups  [rbp+500h+Buf1], xmm0
0x1800d5ea0  call    ?StringToCLSID@@YAHPEBGPEAU_GUID@@@Z; StringToCLSID(ushort const *,_GUID *)
0x1800d5ea5  test    eax, eax
0x1800d5ea7  jz      loc_1800D60D4
0x1800d5ead  mov     r13d, 10h
0x1800d5eb3  test    bl, 2
0x1800d5eb6  jnz     short loc_1800D5ED7
0x1800d5eb8  mov     r8d, r13d; Size
0x1800d5ebb  lea     rdx, GUID_TFCAT_TIPCAP_SECUREMODE; Buf2
0x1800d5ec2  lea     rcx, [rbp+500h+Buf1]; Buf1
0x1800d5ec6  call    memcmp_0
0x1800d5ecb  test    eax, eax
0x1800d5ecd  jnz     short loc_1800D5ED7
0x1800d5ecf  or      ebx, 2
0x1800d5ed2  jmp     loc_1800D60D4
0x1800d5ed7  test    bl, 8
0x1800d5eda  jnz     short loc_1800D5EFB
0x1800d5edc  mov     r8, r13; Size
0x1800d5edf  lea     rdx, GUID_TFCAT_TIPCAP_COMLESS; Buf2
0x1800d5ee6  lea     rcx, [rbp+500h+Buf1]; Buf1
0x1800d5eea  call    memcmp_0
0x1800d5eef  test    eax, eax
0x1800d5ef1  jnz     short loc_1800D5EFB
0x1800d5ef3  or      ebx, 8
0x1800d5ef6  jmp     loc_1800D60D4
0x1800d5efb  test    bl, 4
0x1800d5efe  jnz     short loc_1800D5F1F
0x1800d5f00  mov     r8, r13; Size
0x1800d5f03  lea     rdx, GUID_TFCAT_TIPCAP_UIELEMENTENABLED; Buf2
0x1800d5f0a  lea     rcx, [rbp+500h+Buf1]; Buf1
0x1800d5f0e  call    memcmp_0
0x1800d5f13  test    eax, eax
0x1800d5f15  jnz     short loc_1800D5F1F
0x1800d5f17  or      ebx, 4
0x1800d5f1a  jmp     loc_1800D60D4
0x1800d5f1f  test    r13b, bl
0x1800d5f22  jnz     short loc_1800D5F43
0x1800d5f24  mov     r8, r13; Size
0x1800d5f27  lea     rdx, GUID_TFCAT_TIPCAP_WOW16; Buf2
0x1800d5f2e  lea     rcx, [rbp+500h+Buf1]; Buf1
0x1800d5f32  call    memcmp_0
0x1800d5f37  test    eax, eax
0x1800d5f39  jnz     short loc_1800D5F43
0x1800d5f3b  or      ebx, r13d
0x1800d5f3e  jmp     loc_1800D60D4
0x1800d5f43  test    bl, 20h
0x1800d5f46  jnz     short loc_1800D5F67
0x1800d5f48  mov     r8, r13; Size
0x1800d5f4b  lea     rdx, GUID_TFCAT_TIPCAP_INPUTMODECOMPARTMENT; Buf2
0x1800d5f52  lea     rcx, [rbp+500h+Buf1]; Buf1
0x1800d5f56  call    memcmp_0
0x1800d5f5b  test    eax, eax
0x1800d5f5d  jnz     short loc_1800D5F67
0x1800d5f5f  or      ebx, 20h
0x1800d5f62  jmp     loc_1800D60D4
0x1800d5f67  bt      ebx, 10h
0x1800d5f6b  jb      short loc_1800D5F8D
0x1800d5f6d  mov     r8, r13; Size
0x1800d5f70  lea     rdx, GUID_TFCAT_TIPCAP_IMMERSIVESUPPORT; Buf2
0x1800d5f77  lea     rcx, [rbp+500h+Buf1]; Buf1
0x1800d5f7b  call    memcmp_0
0x1800d5f80  test    eax, eax
0x1800d5f82  jnz     short loc_1800D5F8D
0x1800d5f84  bts     ebx, 10h
0x1800d5f88  jmp     loc_1800D60D4
0x1800d5f8d  bt      ebx, 11h
0x1800d5f91  jb      short loc_1800D5FB3
0x1800d5f93  mov     r8, r13; Size
0x1800d5f96  lea     rdx, GUID_TFCAT_TIPCAP_SYSTRAYSUPPORT; Buf2
0x1800d5f9d  lea     rcx, [rbp+500h+Buf1]; Buf1
0x1800d5fa1  call    memcmp_0
0x1800d5fa6  test    eax, eax
0x1800d5fa8  jnz     short loc_1800D5FB3
0x1800d5faa  bts     ebx, 11h
0x1800d5fae  jmp     loc_1800D60D4
0x1800d5fb3  bt      ebx, 12h
0x1800d5fb7  jb      short loc_1800D5FDB
0x1800d5fb9  mov     r8, r13; Size
0x1800d5fbc  lea     rdx, GUID_TFCAT_TIPCAP_IMMERSIVEONLY; Buf2
0x1800d5fc3  lea     rcx, [rbp+500h+Buf1]; Buf1
0x1800d5fc7  call    memcmp_0
0x1800d5fcc  test    eax, eax
0x1800d5fce  jnz     short loc_1800D5FDB
0x1800d5fd0  or      ebx, 50000h
0x1800d5fd6  jmp     loc_1800D60D4
0x1800d5fdb  bt      ebx, 1Ch
0x1800d5fdf  jb      short loc_1800D6003
0x1800d5fe1  mov     r8, r13; Size
0x1800d5fe4  lea     rdx, GUID_TFCAT_TIPCAP_LOCALSERVER; Buf2
0x1800d5feb  lea     rcx, [rbp+500h+Buf1]; Buf1
0x1800d5fef  call    memcmp_0
0x1800d5ff4  test    eax, eax
0x1800d5ff6  jnz     short loc_1800D6003
0x1800d5ff8  or      ebx, 10010000h
0x1800d5ffe  jmp     loc_1800D60D4
0x1800d6003  bt      ebx, 1Eh
0x1800d6007  jb      short loc_1800D602B
0x1800d6009  mov     r8, r13; Size
  ... truncated ...
```
