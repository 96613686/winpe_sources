# CreateTempDirectoryForUser(ushort const *,void *,bool,void *)

- ea: `0x18000659c`
- end: `0x1800069ca`
- name: `?CreateTempDirectoryForUser@@YAJPEBGPEAX_N1@Z`
- size: `1070`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, void *, char, void *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002bf94`

## callees

- `0x1800053a0`
- `0x18000659c`
- `0x1800069d0`
- `0x180006b10`
- `0x180006d44`
- `0x180007978`
- `0x180008200`
- `0x180009b70`
- `0x18000a320`
- `0x1800111a0`
- `0x18001f060`
- `0x180025254`
- `0x18002d2d8`
- `0x18002f8e0`
- `0x180033e88`
- `0x1800507c8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000677a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000677a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800065f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006692`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800065f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006692`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006635`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800066cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800068c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800069a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006635`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800066cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800068c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800069a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800067ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800067ff`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18000671a`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18000671a`

## string_xrefs

- `0x180006854`: `Failed to create directory <%ws>> for user`
- `0x18000660a`: `Failed to open user key for SID <%ls>.`
- `0x1800068e3`: `TEMP directory <%ls> is not under user profile.`
- `0x180006619`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180006838`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180006863`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18000687d`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x1800068f7`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180006911`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180006935`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180006959`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18000697d`: `onecore\ds\security\gina\profile\profsvc\util.cpp`

## pseudocode

```c
__int64 __fastcall CreateTempDirectoryForUser(LPCWSTR lpSubKey, void *a2, char a3, void *a4)
{
  void *v4; // rsi
  unsigned int v8; // eax
  int v9; // ebx
  unsigned int i; // r14d
  LSTATUS v12; // eax
  int v13; // eax
  unsigned __int16 *v14; // rdi
  HKEY v15; // rbx
  __int64 cchCount2; // r9
  int v17; // eax
  int NestedDirectory; // esi
  const unsigned __int16 *v19; // rdx
  enum _STORAGE_RESERVE_ID v20; // r8d
  unsigned int v21; // r9d
  int v22; // eax
  int phkResult; // [rsp+28h] [rbp-49h]
  int phkResulta; // [rsp+28h] [rbp-49h]
  HKEY hKey; // [rsp+38h] [rbp-39h] BYREF
  HKEY v26; // [rsp+40h] [rbp-31h] BYREF
  PWSTR ppszPathOut; // [rsp+48h] [rbp-29h] BYREF
  unsigned __int16 *v28[3]; // [rsp+50h] [rbp-21h] BYREF
  void *v29; // [rsp+68h] [rbp-9h] BYREF
  char v30; // [rsp+70h] [rbp-1h]
  PCWSTR pszPathIn[3]; // [rsp+78h] [rbp+7h] BYREF
  _QWORD v32[3]; // [rsp+90h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]

  v4 = a4;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v8 = RegOpenKeyExW(HKEY_USERS, lpSubKey, 0, 0x2001Fu, &hKey);
  if ( v8 )
  {
    v9 = wil::details::in1diag3::Return_Win32Msg(
           retaddr,
           (void *)0x470,
           (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
           (const char *)v8,
           (unsigned int)"Failed to open user key for SID <%ls>.",
           (const char *)lpSubKey);
LABEL_3:
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v9;
  }
  else
  {
    v32[0] = L"TEMP";
    v32[1] = L"TMP";
    for ( i = 0; i < 2; ++i )
    {
      memset(v28, 0, sizeof(v28));
      v26 = 0;
      v12 = RegOpenKeyExW(hKey, L"Environment", 0, 0x20019u, &v26);
      v9 = v12;
      if ( v12 > 0 )
        v9 = (unsigned __int16)v12 | 0x80070000;
      if ( v9 < 0
        || (v9 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_InitializeFromRegistry(
                   v28,
                   v26,
                   v32[i],
                   0),
            RegCloseKey(v26),
            v9 < 0) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x479,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
          (const char *)(unsigned int)v9,
          phkResult);
        goto LABEL_48;
      }
      pszPathIn[0] = 0;
      pszPathIn[1] = (PCWSTR)-1LL;
      pszPathIn[2] = (PCWSTR)-1LL;
      v13 = ExpandEnvStringAlloc(a2, v28[0], (unsigned __int16 **)pszPathIn);
      v9 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x47C,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
          (const char *)(unsigned int)v13,
          phkResult);
        goto LABEL_46;
      }
      ppszPathOut = 0;
      v14 = (unsigned __int16 *)pszPathIn[0];
      v9 = PathAllocCanonicalize(pszPathIn[0], 0, &ppszPathOut);
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x47F,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
          (const char *)(unsigned int)v9,
          phkResult);
        goto LABEL_44;
      }
      v26 = 0;
      v9 = ExpandEnvStringAlloc(a2, L"%USERPROFILE%", (unsigned __int16 **)&v26);
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x482,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
          (const char *)(unsigned int)v9,
          phkResult);
        goto LABEL_42;
      }
      v15 = v26;
      cchCount2 = -1;
      do
        ++cchCount2;
      while ( *((_WORD *)v26 + cchCount2) );
      if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)v26, cchCount2, ppszPathOut, cchCount2) != 2 )
      {
        v9 = -2147024891;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x485,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
          (const char *)0x80070005LL,
          (int)"TEMP directory <%ls> is not under user profile.",
          (const char *)ppszPathOut);
LABEL_42:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v26);
LABEL_44:
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&ppszPathOut);
LABEL_46:
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(pszPathIn);
LABEL_48:
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v28);
        goto LABEL_3;
      }
      v29 = 0;
      v30 = 0;
      v17 = CAutoImpersonate::ImpersonateUser((CAutoImpersonate *)&v29, v4);
      NestedDirectory = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x48B,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
          (const char *)(unsigned int)v17,
          phkResulta);
LABEL_36:
        CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v29);
LABEL_37:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v26);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&ppszPathOut);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(pszPathIn);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v28);
        if ( hKey )
          RegCloseKey(hKey);
        return (unsigned int)NestedDirectory;
      }
      NestedDirectory = CreateNestedDirectory(v14, 0);
      if ( NestedDirectory < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x48C,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
          (const char *)(unsigned int)NestedDirectory,
          (int)"Failed to create directory <%ws>> for user",
          (const char *)v14);
        goto LABEL_36;
      }
      if ( v30 )
      {
        RevertToUser(&v29);
        v29 = 0;
        v30 = 0;
      }
      if ( !a3 )
      {
        v22 = StorageReserveHelper::SetReserveAreaOnFileTreeEx((StorageReserveHelper *)v14, v19, v20, v21);
        NestedDirectory = v22;
        if ( v22 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x492,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
            (const char *)(unsigned int)v22,
            phkResulta);
          goto LABEL_37;
        }
      }
      if ( v15 )
        Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v15);
      if ( ppszPathOut )
        LocalFree(ppszPathOut);
      if ( v14 )
        Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v14);
      if ( v28[0] )
        Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v28[0]);
      v4 = a4;
    }
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
}

```

## disassembly

```asm
0x18000659c  mov     rax, rsp
0x18000659f  mov     [rax+8], rbx
0x1800065a3  mov     [rax+10h], rsi
0x1800065a7  mov     [rax+20h], r9
0x1800065ab  push    rbp
0x1800065ac  push    rdi
0x1800065ad  push    r12
0x1800065af  push    r13
0x1800065b1  push    r14
0x1800065b3  lea     rbp, [rax-5Fh]
0x1800065b7  sub     rsp, 0A0h
0x1800065be  mov     rsi, r9
0x1800065c1  mov     r13b, r8b
0x1800065c4  mov     r12, rdx
0x1800065c7  mov     rbx, rcx
0x1800065ca  xor     edi, edi
0x1800065cc  mov     [rbp+57h+hKey], rdi
0x1800065d0  xor     edx, edx
0x1800065d2  lea     rcx, [rbp+57h+hKey]
0x1800065d6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800065db  lea     rax, [rbp+57h+hKey]
0x1800065df  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800065e4  mov     r9d, 2001Fh; samDesired
0x1800065ea  xor     r8d, r8d; ulOptions
0x1800065ed  mov     rdx, rbx; lpSubKey
0x1800065f0  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800065f7  call    cs:__imp_RegOpenKeyExW
0x1800065fd  test    eax, eax
0x1800065ff  jz      short loc_180006642
0x180006601  mov     rcx, [rbp+5Fh]; this
0x180006605  mov     qword ptr [rsp+0C0h+cchCount2], rbx; char *
0x18000660a  lea     rdx, aFailedToOpenUs; "Failed to open user key for SID <%ls>."
0x180006611  mov     [rsp+0C0h+phkResult], rdx; unsigned int
0x180006616  mov     r9d, eax; char *
0x180006619  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180006620  mov     edx, 470h; void *
0x180006625  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18000662a  mov     ebx, eax
0x18000662c  mov     rcx, [rbp+57h+hKey]; hKey
0x180006630  test    rcx, rcx
0x180006633  jz      short loc_18000663B
0x180006635  call    cs:__imp_RegCloseKey
0x18000663b  mov     eax, ebx
0x18000663d  jmp     loc_1800069AE
0x180006642  lea     rax, aTemp; "TEMP"
0x180006649  mov     [rbp+57h+var_38], rax
0x18000664d  lea     rax, aTmp; "TMP"
0x180006654  mov     [rbp+57h+var_30], rax
0x180006658  mov     r14d, edi
0x18000665b  cmp     r14d, 2
0x18000665f  jnb     loc_18000699D
0x180006665  mov     [rbp+57h+var_78], rdi
0x180006669  mov     [rbp+57h+var_70], rdi
0x18000666d  mov     [rbp+57h+var_68], rdi
0x180006671  mov     [rbp+57h+var_88], rdi
0x180006675  lea     rax, [rbp+57h+var_88]
0x180006679  mov     [rsp+0C0h+phkResult], rax; int
0x18000667e  mov     r9d, 20019h; samDesired
0x180006684  xor     r8d, r8d; ulOptions
0x180006687  lea     rdx, aEnvironment; "Environment"
0x18000668e  mov     rcx, [rbp+57h+hKey]; hKey
0x180006692  call    cs:__imp_RegOpenKeyExW
0x180006698  mov     ebx, eax
0x18000669a  test    eax, eax
0x18000669c  jle     short loc_1800066A7
0x18000669e  movzx   ebx, ax
0x1800066a1  or      ebx, 80070000h
0x1800066a7  test    ebx, ebx
0x1800066a9  js      loc_180006976
0x1800066af  movsxd  r8, r14d
0x1800066b2  xor     r9d, r9d
0x1800066b5  mov     r8, [rbp+r8*8+57h+var_38]
0x1800066ba  mov     rdx, [rbp+57h+var_88]
0x1800066be  lea     rcx, [rbp+57h+var_78]
0x1800066c2  call    ?_InitializeFromRegistry@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x1800066c7  mov     ebx, eax
0x1800066c9  mov     rcx, [rbp+57h+var_88]; hKey
0x1800066cd  call    cs:__imp_RegCloseKey
0x1800066d3  test    ebx, ebx
0x1800066d5  js      loc_180006976
0x1800066db  mov     [rbp+57h+pszPathIn], rdi
0x1800066df  mov     [rbp+57h+var_48], 0FFFFFFFFFFFFFFFFh
0x1800066e7  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFFh
0x1800066ef  lea     r8, [rbp+57h+pszPathIn]; unsigned __int16 **
0x1800066f3  mov     rdx, [rbp+57h+var_78]; unsigned __int16 *
0x1800066f7  mov     rcx, r12; void *
0x1800066fa  call    ?ExpandEnvStringAlloc@@YAJQEAXPEBGPEAPEAG@Z; ExpandEnvStringAlloc(void * const,ushort const *,ushort * *)
0x1800066ff  mov     ebx, eax
0x180006701  test    eax, eax
0x180006703  js      loc_180006952
0x180006709  mov     [rbp+57h+ppszPathOut], rdi
0x18000670d  lea     r8, [rbp+57h+ppszPathOut]; ppszPathOut
0x180006711  xor     edx, edx; dwFlags
0x180006713  mov     rdi, [rbp+57h+pszPathIn]
0x180006717  mov     rcx, rdi; pszPathIn
0x18000671a  call    cs:__imp_PathAllocCanonicalize
0x180006720  mov     ebx, eax
0x180006722  xor     eax, eax
0x180006724  test    ebx, ebx
0x180006726  js      loc_18000692E
0x18000672c  mov     [rbp+57h+var_88], rax
0x180006730  lea     r8, [rbp+57h+var_88]; unsigned __int16 **
0x180006734  lea     rdx, aUserprofile_0; "%USERPROFILE%"
0x18000673b  mov     rcx, r12; void *
0x18000673e  call    ?ExpandEnvStringAlloc@@YAJQEAXPEBGPEAPEAG@Z; ExpandEnvStringAlloc(void * const,ushort const *,ushort * *)
0x180006743  mov     ebx, eax
0x180006745  xor     eax, eax
0x180006747  test    ebx, ebx
0x180006749  js      loc_18000690A
0x18000674f  mov     rbx, [rbp+57h+var_88]
0x180006753  or      r9, 0FFFFFFFFFFFFFFFFh
0x180006757  inc     r9; cchCount1
0x18000675a  cmp     [rbx+r9*2], ax
0x18000675f  jnz     short loc_180006757
0x180006761  mov     rax, [rbp+57h+ppszPathOut]
0x180006765  mov     [rsp+0C0h+cchCount2], r9d; cchCount2
0x18000676a  mov     [rsp+0C0h+phkResult], rax; int
0x18000676f  mov     r8, rbx; lpString1
0x180006772  mov     edx, 1; dwCmpFlags
0x180006777  lea     ecx, [rdx+7Eh]; Locale
0x18000677a  call    cs:__imp_CompareStringW
0x180006780  cmp     eax, 2
0x180006783  jnz     loc_1800068D6
0x180006789  xor     eax, eax
0x18000678b  mov     [rbp+57h+var_60], rax
0x18000678f  mov     [rbp+57h+var_58], al
0x180006792  mov     rdx, rsi; void *
0x180006795  lea     rcx, [rbp+57h+var_60]; this
0x180006799  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x18000679e  mov     esi, eax
0x1800067a0  test    eax, eax
0x1800067a2  js      loc_180006876
0x1800067a8  xor     edx, edx; lpSecurityAttributes
0x1800067aa  mov     rcx, rdi; unsigned __int16 *
0x1800067ad  call    ?CreateNestedDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CreateNestedDirectory(ushort const *,_SECURITY_ATTRIBUTES *)
0x1800067b2  mov     esi, eax
0x1800067b4  test    eax, eax
0x1800067b6  js      loc_18000684B
0x1800067bc  xor     esi, esi
0x1800067be  cmp     [rbp+57h+var_58], sil
0x1800067c2  jz      short loc_1800067D5
0x1800067c4  lea     rcx, [rbp+57h+var_60]; void **
0x1800067c8  call    ?RevertToUser@@YAJPEAPEAX@Z; RevertToUser(void * *)
0x1800067cd  mov     [rbp+57h+var_60], rsi
0x1800067d1  mov     [rbp+57h+var_58], sil
0x1800067d5  test    r13b, r13b
0x1800067d8  jnz     short loc_1800067E8
0x1800067da  mov     rcx, rdi; this
0x1800067dd  call    ?SetReserveAreaOnFileTreeEx@StorageReserveHelper@@YAJPEBGW4_STORAGE_RESERVE_ID@@K@Z; StorageReserveHelper::SetReserveAreaOnFileTreeEx(ushort const *,_STORAGE_RESERVE_ID,ulong)
0x1800067e2  mov     esi, eax
0x1800067e4  test    eax, eax
0x1800067e6  js      short loc_180006831
0x1800067e8  test    rbx, rbx
0x1800067eb  jz      short loc_1800067F6
0x1800067ed  mov     rcx, rbx
0x1800067f0  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x1800067f5  nop
0x1800067f6  mov     rcx, [rbp+57h+ppszPathOut]; hMem
0x1800067fa  test    rcx, rcx
0x1800067fd  jz      short loc_180006806
0x1800067ff  call    cs:__imp_LocalFree
0x180006805  nop
0x180006806  test    rdi, rdi
0x180006809  jz      short loc_180006814
0x18000680b  mov     rcx, rdi
0x18000680e  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x180006813  nop
0x180006814  xor     edi, edi
0x180006816  cmp     [rbp+57h+var_78], rdi
0x18000681a  jz      short loc_180006825
0x18000681c  mov     rcx, [rbp+57h+var_78]
0x180006820  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x180006825  inc     r14d
0x180006828  mov     rsi, [rbp+57h+arg_18]
0x18000682c  jmp     loc_18000665B
0x180006831  mov     rcx, [rbp+5Fh]; this
0x180006835  mov     r9d, esi; char *
0x180006838  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000683f  mov     edx, 492h; void *
0x180006844  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006849  jmp     short loc_180006898
0x18000684b  mov     rcx, [rbp+5Fh]; this
0x18000684f  mov     qword ptr [rsp+0C0h+cchCount2], rdi; char *
0x180006854  lea     rax, aFailedToCreate; "Failed to create directory <%ws>> for u"...
0x18000685b  mov     [rsp+0C0h+phkResult], rax; int
0x180006860  mov     r9d, esi; char *
0x180006863  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000686a  mov     edx, 48Ch; void *
0x18000686f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180006874  jmp     short loc_18000688E
0x180006876  mov     rcx, [rbp+5Fh]; this
0x18000687a  mov     r9d, esi; char *
0x18000687d  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180006884  mov     edx, 48Bh; void *
0x180006889  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000688e  lea     rcx, [rbp+57h+var_60]; this
0x180006892  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x180006897  nop
0x180006898  lea     rcx, [rbp+57h+var_88]
0x18000689c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800068a1  nop
0x1800068a2  lea     rcx, [rbp+57h+ppszPathOut]
0x1800068a6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800068ab  nop
0x1800068ac  lea     rcx, [rbp+57h+pszPathIn]
0x1800068b0  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800068b5  nop
0x1800068b6  lea     rcx, [rbp+57h+var_78]
0x1800068ba  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800068bf  nop
0x1800068c0  mov     rcx, [rbp+57h+hKey]; hKey
0x1800068c4  test    rcx, rcx
0x1800068c7  jz      short loc_1800068CF
0x1800068c9  call    cs:__imp_RegCloseKey
0x1800068cf  mov     eax, esi
0x1800068d1  jmp     loc_1800069AE
0x1800068d6  mov     rcx, [rbp+5Fh]; this
0x1800068da  mov     rax, [rbp+57h+ppszPathOut]
0x1800068de  mov     qword ptr [rsp+0C0h+cchCount2], rax; char *
0x1800068e3  lea     rax, aTempDirectoryL; "TEMP directory <%ls> is not under user "...
0x1800068ea  mov     [rsp+0C0h+phkResult], rax; int
0x1800068ef  mov     ebx, 80070005h
0x1800068f4  mov     r9d, ebx; char *
0x1800068f7  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800068fe  mov     edx, 485h; void *
0x180006903  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180006908  jmp     short loc_180006923
0x18000690a  mov     rcx, [rbp+5Fh]; this
0x18000690e  mov     r9d, ebx; char *
0x180006911  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180006918  mov     edx, 482h; void *
0x18000691d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006922  nop
0x180006923  lea     rcx, [rbp+57h+var_88]
0x180006927  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000692c  jmp     short loc_180006947
0x18000692e  mov     rcx, [rbp+5Fh]; this
0x180006932  mov     r9d, ebx; char *
0x180006935  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000693c  mov     edx, 47Fh; void *
0x180006941  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006946  nop
0x180006947  lea     rcx, [rbp+57h+ppszPathOut]
0x18000694b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180006950  jmp     short loc_18000696B
0x180006952  mov     rcx, [rbp+5Fh]; this
0x180006956  mov     r9d, ebx; char *
0x180006959  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180006960  mov     edx, 47Ch; void *
0x180006965  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000696a  nop
0x18000696b  lea     rcx, [rbp+57h+pszPathIn]
0x18000696f  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180006974  jmp     short loc_18000698F
0x180006976  mov     rcx, [rbp+5Fh]; this
0x18000697a  mov     r9d, ebx; char *
0x18000697d  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180006984  mov     edx, 479h; void *
0x180006989  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000698e  nop
0x18000698f  lea     rcx, [rbp+57h+var_78]
0x180006993  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180006998  jmp     loc_18000662C
0x18000699d  mov     rcx, [rbp+57h+hKey]; hKey
0x1800069a1  test    rcx, rcx
0x1800069a4  jz      short loc_1800069AC
0x1800069a6  call    cs:__imp_RegCloseKey
0x1800069ac  xor     eax, eax
0x1800069ae  lea     r11, [rsp+0C0h+var_20]
0x1800069b6  mov     rbx, [r11+30h]
0x1800069ba  mov     rsi, [r11+38h]
0x1800069be  mov     rsp, r11
0x1800069c1  pop     r14
0x1800069c3  pop     r13
0x1800069c5  pop     r12
0x1800069c7  pop     rdi
0x1800069c8  pop     rbp
0x1800069c9  retn
```
