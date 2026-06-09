# UninstallRemainingUnusedLanguageResources(void)

- ea: `0x14000c36c`
- end: `0x14000c713`
- name: `?UninstallRemainingUnusedLanguageResources@@YAJXZ`
- size: `935`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000d8b8`

## callees

- `0x140002190`
- `0x140002d78`
- `0x140002dcc`
- `0x140003578`
- `0x140004718`
- `0x140004924`
- `0x140005020`
- `0x14000513c`
- `0x140007eac`
- `0x1400081a8`
- `0x140008558`
- `0x14000a914`
- `0x14000c36c`
- `0x14000ce40`
- `0x14000ee3c`
- `0x14000eeb8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000c6d8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000c6d8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000c3ab`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000c3ab`
- `AppXDeploymentClient!__imp_AppxRemovePackageForAllUsers` at `0x14000c676`
- `AppXDeploymentClient!__imp_AppxRemovePackageForAllUsers` at `0x14000c676`
- `ext-ms-win-resources-languageoverlay-l1-1-1!EnumerateInstalledLocalExperiencePacks` at `0x14000c5aa`
- `ext-ms-win-resources-languageoverlay-l1-1-1!EnumerateInstalledLocalExperiencePacks` at `0x14000c5aa`

## string_xrefs

- `0x14000c3c2`: `shell\osshell\cpls\lpksetup\lpremove\launchlpksetup.cpp`
- `0x14000c49d`: `LpRemove cleans up language packs: `
- `0x14000c635`: `LpRemove cleans up LXPs: `

## pseudocode

```c
__int64 UninstallRemainingUnusedLanguageResources(void)
{
  HRESULT v0; // eax
  unsigned int v1; // ebx
  int LanguagePacksToUninstall; // eax
  unsigned int v4; // r8d
  __int64 v5; // rbx
  _DWORD *v6; // rcx
  __int64 v7; // rcx
  const unsigned __int16 *p_Src; // rcx
  int v9; // eax
  unsigned int v10; // r8d
  __int64 v11; // rbx
  _DWORD *v12; // rcx
  __int64 v13; // rcx
  _QWORD *i; // rbx
  _QWORD *v15; // rdi
  _QWORD *v16; // rcx
  int v17; // eax
  unsigned int v18; // r8d
  int v19; // [rsp+20h] [rbp-E8h]
  int v20; // [rsp+30h] [rbp-D8h] BYREF
  __int128 v21; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+48h] [rbp-C0h]
  __int128 v23; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A8h]
  int v25[4]; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+78h] [rbp-90h]
  _QWORD v27[2]; // [rsp+80h] [rbp-88h] BYREF
  __int128 v28; // [rsp+90h] [rbp-78h] BYREF
  __int128 v29; // [rsp+A0h] [rbp-68h]
  _BYTE v30[8]; // [rsp+B0h] [rbp-58h] BYREF
  __int128 Src; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v32; // [rsp+C8h] [rbp-40h]
  unsigned __int64 v33; // [rsp+D0h] [rbp-38h]
  _BYTE v34[32]; // [rsp+D8h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  *(_OWORD *)v25 = 0;
  v26 = 0;
  GetLanguagesInUse(v25);
  v0 = CoInitializeEx(0, 0);
  v1 = v0;
  if ( v0 >= 0 )
  {
    BYTE1(v20) = 1;
    v21 = 0;
    v22 = 0;
    if ( (unsigned __int8)IsEnumerateInstalledSystemLanguagePacksPresent() )
    {
      LanguagePacksToUninstall = GetLanguagePacksToUninstall((int)v25);
      if ( LanguagePacksToUninstall >= 0 )
      {
        v5 = DelimitedStringFromItems<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>>(v34);
        v6 = (_DWORD *)*((_QWORD *)LanguagePackDiskCleanupTraceProvider::Instance() + 1);
        if ( v6 && *v6 )
        {
          LanguagePackDiskCleanupTraceProvider::Instance();
          v28 = *(_OWORD *)v5;
          v29 = *(_OWORD *)(v5 + 16);
          *(_QWORD *)(v5 + 16) = 0;
          *(_QWORD *)(v5 + 24) = 7;
          *(_WORD *)v5 = 0;
          LanguagePackDiskCleanupTraceProvider::LogCleanupActionInfo_(v7, L"LpRemove cleans up language packs: ", &v28);
        }
        std::wstring::~wstring(v34);
        Src = 0;
        v32 = 0;
        v33 = 7;
        LOWORD(Src) = 0;
        if ( (__int64)(*((_QWORD *)&v21 + 1) - v21) >> 5 )
        {
          std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
            &Src,
            9);
          std::for_each_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___________lambda_1116c007ac1a4d080bc9556b8c65e5b1___(
            v30,
            v21,
            *((_QWORD *)&v21 + 1),
            &Src);
          p_Src = (const unsigned __int16 *)&Src;
          if ( v33 > 7 )
            p_Src = (const unsigned __int16 *)Src;
          LaunchLpkSetup(p_Src);
        }
        std::wstring::~wstring(&Src);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1A3,
          v4,
          (const char *)(unsigned int)LanguagePacksToUninstall,
          v19);
      }
    }
    v23 = 0;
    v24 = 0;
    v27[0] = v25;
    v27[1] = &v23;
    if ( (unsigned __int8)IsEnumerateInstalledLocalExperiencePacksPresent() )
    {
      v9 = EnumerateInstalledLocalExperiencePacks(
             &lambda_18fa8810506416c7e8e7d1b5f325261f_::_lambda_invoker_cdecl_,
             0,
             v27);
      if ( v9 >= 0 )
      {
        v11 = DelimitedStringFromItems<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>>(v34);
        v12 = (_DWORD *)*((_QWORD *)LanguagePackDiskCleanupTraceProvider::Instance() + 1);
        if ( v12 && *v12 )
        {
          LanguagePackDiskCleanupTraceProvider::Instance();
          v28 = *(_OWORD *)v11;
          v29 = *(_OWORD *)(v11 + 16);
          *(_QWORD *)(v11 + 16) = 0;
          *(_QWORD *)(v11 + 24) = 7;
          *(_WORD *)v11 = 0;
          LanguagePackDiskCleanupTraceProvider::LogCleanupActionInfo_(v13, L"LpRemove cleans up LXPs: ", &v28);
        }
        std::wstring::~wstring(v34);
        v15 = (_QWORD *)*((_QWORD *)&v23 + 1);
        for ( i = (_QWORD *)v23; i != v15; i += 4 )
        {
          v20 = 0;
          if ( i[3] <= 7u )
            v16 = i;
          else
            v16 = (_QWORD *)*i;
          v17 = AppxRemovePackageForAllUsers(v16, &v20);
          if ( v17 < 0 )
            wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x1E0, v18, (const char *)(unsigned int)v17, v19);
          if ( v20 )
            wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x1E1, v18, (const char *)0x80073CFALL, v19);
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x1D7, v10, (const char *)(unsigned int)v9, v19);
      }
    }
    std::vector<std::wstring>::~vector<std::wstring>(&v23);
    std::vector<std::wstring>::~vector<std::wstring>(&v21);
    CoUninitialize();
    std::vector<std::wstring>::~vector<std::wstring>(v25);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19A,
      (unsigned int)"shell\\osshell\\cpls\\lpksetup\\lpremove\\launchlpksetup.cpp",
      (const char *)(unsigned int)v0,
      v19);
    std::vector<std::wstring>::~vector<std::wstring>(v25);
    return v1;
  }
}

```

## disassembly

```asm
0x14000c36c  mov     [rsp+arg_0], rbx
0x14000c371  push    rdi
0x14000c372  sub     rsp, 100h
0x14000c379  mov     rax, cs:__security_cookie
0x14000c380  xor     rax, rsp
0x14000c383  mov     [rsp+108h+var_10], rax
0x14000c38b  xorps   xmm0, xmm0
0x14000c38e  movdqu  xmmword ptr [rsp+108h+var_A0], xmm0
0x14000c394  mov     [rsp+108h+var_90], 0
0x14000c39d  lea     rcx, [rsp+108h+var_A0]
0x14000c3a2  call    ?GetLanguagesInUse@@YAXAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; GetLanguagesInUse(std::vector<std::wstring> &)
0x14000c3a7  xor     edx, edx; dwCoInit
0x14000c3a9  xor     ecx, ecx; pvReserved
0x14000c3ab  call    cs:__imp_CoInitializeEx
0x14000c3b1  mov     ebx, eax
0x14000c3b3  test    eax, eax
0x14000c3b5  jns     short loc_14000C3E5
0x14000c3b7  mov     rcx, [rsp+108h]; this
0x14000c3bf  mov     r9d, eax; char *
0x14000c3c2  lea     r8, aShellOsshellCp_0; "shell\\osshell\\cpls\\lpksetup\\lpremov"...
0x14000c3c9  mov     edx, 19Ah; void *
0x14000c3ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c3d3  nop
0x14000c3d4  lea     rcx, [rsp+108h+var_A0]
0x14000c3d9  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x14000c3de  mov     eax, ebx
0x14000c3e0  jmp     loc_14000C6F1
0x14000c3e5  mov     byte ptr [rsp+108h+var_D8+1], 1
0x14000c3ea  xorps   xmm0, xmm0
0x14000c3ed  movdqu  [rsp+108h+var_D0], xmm0
0x14000c3f3  mov     [rsp+108h+var_C0], 0
0x14000c3fc  call    IsEnumerateInstalledSystemLanguagePacksPresent
0x14000c401  test    al, al
0x14000c403  jz      loc_14000C560
0x14000c409  lea     rdx, [rsp+108h+var_D0]
0x14000c40e  lea     rcx, [rsp+108h+var_A0]; int
0x14000c413  call    ?GetLanguagePacksToUninstall@@YAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@0@Z; GetLanguagePacksToUninstall(std::vector<std::wstring> &,std::vector<std::wstring> &)
0x14000c418  mov     rcx, [rsp+108h]; this
0x14000c420  test    eax, eax
0x14000c422  jns     short loc_14000C436
0x14000c424  mov     r9d, eax; char *
0x14000c427  mov     edx, 1A3h; void *
0x14000c42c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000c431  jmp     loc_14000C560
0x14000c436  mov     r8, qword ptr [rsp+108h+var_D0+8]
0x14000c43b  mov     rdx, qword ptr [rsp+108h+var_D0]
0x14000c440  lea     rcx, [rsp+108h+var_30]; Src
0x14000c448  call    ??$DelimitedStringFromItems@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@0G@Z; DelimitedStringFromItems<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,ushort)
0x14000c44d  mov     rbx, rax
0x14000c450  call    ?Instance@LanguagePackDiskCleanupTraceProvider@@KAPEAV1@XZ; LanguagePackDiskCleanupTraceProvider::Instance(void)
0x14000c455  mov     rcx, [rax+8]
0x14000c459  test    rcx, rcx
0x14000c45c  jz      short loc_14000C4A9
0x14000c45e  mov     ecx, [rcx]
0x14000c460  test    ecx, ecx
0x14000c462  jz      short loc_14000C4A9
0x14000c464  call    ?Instance@LanguagePackDiskCleanupTraceProvider@@KAPEAV1@XZ; LanguagePackDiskCleanupTraceProvider::Instance(void)
0x14000c469  movups  xmm0, xmmword ptr [rbx]
0x14000c46c  movups  [rsp+108h+var_78], xmm0
0x14000c474  movups  xmm1, xmmword ptr [rbx+10h]
0x14000c478  movups  [rsp+108h+var_68], xmm1
0x14000c480  mov     qword ptr [rbx+10h], 0
0x14000c488  mov     qword ptr [rbx+18h], 7
0x14000c490  xor     eax, eax
0x14000c492  mov     [rbx], ax
0x14000c495  lea     r8, [rsp+108h+var_78]
0x14000c49d  lea     rdx, aLpremoveCleans_0; "LpRemove cleans up language packs: "
0x14000c4a4  call    ?LogCleanupActionInfo_@LanguagePackDiskCleanupTraceProvider@@QEAAXPEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LanguagePackDiskCleanupTraceProvider::LogCleanupActionInfo_(ushort const *,std::wstring)
0x14000c4a9  lea     rcx, [rsp+108h+var_30]
0x14000c4b1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000c4b6  xorps   xmm0, xmm0
0x14000c4b9  movups  [rsp+108h+Src], xmm0
0x14000c4c1  mov     [rsp+108h+var_40], 0
0x14000c4cd  mov     [rsp+108h+var_38], 7
0x14000c4d9  xor     eax, eax
0x14000c4db  mov     word ptr [rsp+108h+Src], ax
0x14000c4e3  mov     rax, qword ptr [rsp+108h+var_D0+8]
0x14000c4e8  sub     rax, qword ptr [rsp+108h+var_D0]
0x14000c4ed  sar     rax, 5
0x14000c4f1  test    rax, rax
0x14000c4f4  jz      short loc_14000C553
0x14000c4f6  mov     edx, 9
0x14000c4fb  mov     qword ptr [rsp+108h+var_E8], rdx; int
0x14000c500  lea     r9, aSRU; " /s /r /u"
0x14000c507  lea     rcx, [rsp+108h+Src]; Src
0x14000c50f  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x14000c514  lea     r9, [rsp+108h+Src]
0x14000c51c  mov     r8, qword ptr [rsp+108h+var_D0+8]
0x14000c521  mov     rdx, qword ptr [rsp+108h+var_D0]
0x14000c526  lea     rcx, [rsp+108h+var_58]
0x14000c52e  call    std__for_each_std___Vector_iterator_std___Vector_val_std___Simple_types_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short___________lambda_1116c007ac1a4d080bc9556b8c65e5b1___
0x14000c533  lea     rcx, [rsp+108h+Src]
0x14000c53b  cmp     [rsp+108h+var_38], 7
0x14000c544  cmova   rcx, qword ptr [rsp+108h+Src]; unsigned __int16 *
0x14000c54d  call    ?LaunchLpkSetup@@YAXPEBG@Z; LaunchLpkSetup(ushort const *)
0x14000c552  nop
0x14000c553  lea     rcx, [rsp+108h+Src]
0x14000c55b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000c560  xorps   xmm0, xmm0
0x14000c563  movdqu  [rsp+108h+var_B8], xmm0
0x14000c569  mov     [rsp+108h+var_A8], 0
0x14000c572  lea     rax, [rsp+108h+var_A0]
0x14000c577  mov     [rsp+108h+var_88], rax
0x14000c57f  lea     rax, [rsp+108h+var_B8]
0x14000c584  mov     [rsp+108h+var_80], rax
0x14000c58c  call    IsEnumerateInstalledLocalExperiencePacksPresent
0x14000c591  test    al, al
0x14000c593  jz      loc_14000C6C2
0x14000c599  lea     r8, [rsp+108h+var_88]
0x14000c5a1  xor     edx, edx
0x14000c5a3  lea     rcx, _lambda_18fa8810506416c7e8e7d1b5f325261f____lambda_invoker_cdecl_
0x14000c5aa  call    cs:__imp_EnumerateInstalledLocalExperiencePacks
0x14000c5b0  mov     rcx, [rsp+108h]; this
0x14000c5b8  test    eax, eax
0x14000c5ba  jns     short loc_14000C5CE
0x14000c5bc  mov     r9d, eax; char *
0x14000c5bf  mov     edx, 1D7h; void *
0x14000c5c4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000c5c9  jmp     loc_14000C6C2
0x14000c5ce  mov     r8, qword ptr [rsp+108h+var_B8+8]
0x14000c5d3  mov     rdx, qword ptr [rsp+108h+var_B8]
0x14000c5d8  lea     rcx, [rsp+108h+var_30]; Src
0x14000c5e0  call    ??$DelimitedStringFromItems@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@0G@Z; DelimitedStringFromItems<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,ushort)
0x14000c5e5  mov     rbx, rax
0x14000c5e8  call    ?Instance@LanguagePackDiskCleanupTraceProvider@@KAPEAV1@XZ; LanguagePackDiskCleanupTraceProvider::Instance(void)
0x14000c5ed  mov     rcx, [rax+8]
0x14000c5f1  test    rcx, rcx
0x14000c5f4  jz      short loc_14000C641
0x14000c5f6  mov     ecx, [rcx]
0x14000c5f8  test    ecx, ecx
0x14000c5fa  jz      short loc_14000C641
0x14000c5fc  call    ?Instance@LanguagePackDiskCleanupTraceProvider@@KAPEAV1@XZ; LanguagePackDiskCleanupTraceProvider::Instance(void)
0x14000c601  movups  xmm0, xmmword ptr [rbx]
0x14000c604  movups  [rsp+108h+var_78], xmm0
0x14000c60c  movups  xmm1, xmmword ptr [rbx+10h]
0x14000c610  movups  [rsp+108h+var_68], xmm1
0x14000c618  mov     qword ptr [rbx+10h], 0
0x14000c620  mov     qword ptr [rbx+18h], 7
0x14000c628  xor     eax, eax
0x14000c62a  mov     [rbx], ax
0x14000c62d  lea     r8, [rsp+108h+var_78]
0x14000c635  lea     rdx, aLpremoveCleans; "LpRemove cleans up LXPs: "
0x14000c63c  call    ?LogCleanupActionInfo_@LanguagePackDiskCleanupTraceProvider@@QEAAXPEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LanguagePackDiskCleanupTraceProvider::LogCleanupActionInfo_(ushort const *,std::wstring)
0x14000c641  lea     rcx, [rsp+108h+var_30]
0x14000c649  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000c64e  mov     rbx, qword ptr [rsp+108h+var_B8]
0x14000c653  mov     rdi, qword ptr [rsp+108h+var_B8+8]
0x14000c658  jmp     short loc_14000C6BD
0x14000c65a  mov     dword ptr [rsp+30h], 0
0x14000c662  cmp     qword ptr [rbx+18h], 7
0x14000c667  jbe     short loc_14000C66E
0x14000c669  mov     rcx, [rbx]
0x14000c66c  jmp     short loc_14000C671
0x14000c66e  mov     rcx, rbx
0x14000c671  lea     rdx, [rsp+108h+var_D8]
0x14000c676  call    cs:__imp_AppxRemovePackageForAllUsers
0x14000c67c  mov     rcx, [rsp+108h]; this
0x14000c684  test    eax, eax
0x14000c686  jns     short loc_14000C695
0x14000c688  mov     r9d, eax; char *
0x14000c68b  mov     edx, 1E0h; void *
0x14000c690  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000c695  cmp     [rsp+108h+var_D8], 0
0x14000c69a  setnz   al
0x14000c69d  mov     rcx, [rsp+108h]; this
0x14000c6a5  test    al, al
0x14000c6a7  jz      short loc_14000C6B9
0x14000c6a9  mov     edx, 1E1h; void *
0x14000c6ae  mov     r9d, 80073CFAh; char *
0x14000c6b4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000c6b9  add     rbx, 20h ; ' '
0x14000c6bd  cmp     rbx, rdi
0x14000c6c0  jnz     short loc_14000C65A
0x14000c6c2  lea     rcx, [rsp+108h+var_B8]
0x14000c6c7  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x14000c6cc  nop
0x14000c6cd  lea     rcx, [rsp+108h+var_D0]
0x14000c6d2  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x14000c6d7  nop
0x14000c6d8  call    cs:__imp_CoUninitialize
0x14000c6de  nop
0x14000c6df  lea     rcx, [rsp+108h+var_A0]
0x14000c6e4  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x14000c6e9  xor     eax, eax
0x14000c6eb  jmp     short loc_14000C6F1
0x14000c6ed  mov     eax, [rsp+108h+var_D8]
0x14000c6f1  mov     rcx, [rsp+108h+var_10]
0x14000c6f9  xor     rcx, rsp; StackCookie
0x14000c6fc  call    __security_check_cookie
0x14000c701  mov     rbx, [rsp+108h+arg_0]
0x14000c709  add     rsp, 100h
0x14000c710  pop     rdi
0x14000c711  retn
```
