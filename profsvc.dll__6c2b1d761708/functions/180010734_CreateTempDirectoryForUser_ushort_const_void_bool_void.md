# CreateTempDirectoryForUser(ushort const *,void *,bool,void *)

- ea: `0x180010734`
- end: `0x180010afd`
- name: `?CreateTempDirectoryForUser@@YAJPEBGPEAX_N1@Z`
- size: `969`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, void *, bool, void *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180030744`

## callees

- `0x180005330`
- `0x180005dd0`
- `0x180007b58`
- `0x18000b060`
- `0x18000e1a0`
- `0x180010524`
- `0x180010734`
- `0x180010b10`
- `0x180010c70`
- `0x1800130d0`
- `0x180013770`
- `0x18002793c`
- `0x180030ad0`
- `0x180034374`
- `0x180035860`
- `0x1800537bc`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800108cb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800108cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010786`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010786`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010ada`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010ada`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010945`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010945`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x180010869`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x180010869`

## string_xrefs

- `0x1800107ae`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180010973`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18001099e`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x1800109b8`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180010a22`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180010a5a`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180010a74`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180010a8e`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180010aa8`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18001079f`: `Failed to open user key for SID <%ls>.`
- `0x180010a0e`: `TEMP directory <%ls> is not under user profile.`
- `0x18001098f`: `Failed to create directory <%ws>> for user`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CreateTempDirectoryForUser(LPCWSTR lpSubKey, void *a2, char a3, void *a4)
{
  unsigned int v8; // eax
  unsigned int v9; // ebx
  unsigned int i; // esi
  int v11; // eax
  int v12; // eax
  unsigned __int16 *v13; // r14
  HRESULT v14; // eax
  int v15; // eax
  PCNZWCH v16; // rbx
  __int64 cchCount2; // r9
  int v18; // eax
  int NestedDirectory; // edi
  const unsigned __int16 *v20; // rdx
  enum _STORAGE_RESERVE_ID v21; // r8d
  unsigned int v22; // r9d
  int v23; // eax
  int phkResult; // [rsp+20h] [rbp-69h]
  PWSTR ppszPathOut; // [rsp+30h] [rbp-59h] BYREF
  PCNZWCH lpString1; // [rsp+38h] [rbp-51h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-49h] BYREF
  PCWSTR pszPathIn; // [rsp+48h] [rbp-41h] BYREF
  __int64 v30; // [rsp+50h] [rbp-39h]
  __int64 v31; // [rsp+58h] [rbp-31h]
  unsigned __int16 *v32[3]; // [rsp+60h] [rbp-29h] BYREF
  __int64 v33; // [rsp+78h] [rbp-11h] BYREF
  char v34; // [rsp+80h] [rbp-9h]
  _QWORD v35[11]; // [rsp+88h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

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
LABEL_35:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v9;
  }
  else
  {
    v35[0] = L"TEMP";
    v35[1] = L"TMP";
    for ( i = 0; i < 2; ++i )
    {
      memset(v32, 0, sizeof(v32));
      v11 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeNoExpand(
              v32,
              hKey,
              L"Environment",
              v35[i]);
      v9 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x479,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
          (const char *)(unsigned int)v11,
          phkResult);
        goto LABEL_34;
      }
      pszPathIn = 0;
      v30 = 0;
      v31 = 0;
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&pszPathIn);
      v30 = -1;
      v31 = -1;
      v12 = ExpandEnvStringAlloc(a2, v32[0], (unsigned __int16 **)&pszPathIn);
      v9 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x47C,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
          (const char *)(unsigned int)v12,
          phkResult);
        goto LABEL_29;
      }
      ppszPathOut = 0;
      v13 = (unsigned __int16 *)pszPathIn;
      v14 = PathAllocCanonicalize(pszPathIn, 0, &ppszPathOut);
      v9 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x47F,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
          (const char *)(unsigned int)v14,
          phkResult);
        goto LABEL_28;
      }
      lpString1 = 0;
      v15 = ExpandEnvStringAlloc(a2, L"%USERPROFILE%", (unsigned __int16 **)&lpString1);
      v9 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x482,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
          (const char *)(unsigned int)v15,
          phkResult);
LABEL_27:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
LABEL_28:
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&ppszPathOut);
LABEL_29:
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&pszPathIn);
LABEL_34:
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v32);
        goto LABEL_35;
      }
      v16 = lpString1;
      cchCount2 = -1;
      do
        ++cchCount2;
      while ( lpString1[cchCount2] );
      if ( CompareStringW(0x7Fu, 1u, lpString1, cchCount2, ppszPathOut, cchCount2) != 2 )
      {
        v9 = -2147024891;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x485,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
          (const char *)0x80070005LL,
          (int)"TEMP directory <%ls> is not under user profile.",
          (const char *)ppszPathOut);
        goto LABEL_27;
      }
      v33 = 0;
      v34 = 0;
      v18 = CAutoImpersonate::ImpersonateUser((CAutoImpersonate *)&v33, a4);
      NestedDirectory = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x48B,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
          (const char *)(unsigned int)v18,
          phkResult);
LABEL_24:
        CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v33);
LABEL_25:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&ppszPathOut);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&pszPathIn);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v32);
        v9 = NestedDirectory;
        goto LABEL_35;
      }
      NestedDirectory = CreateNestedDirectory(v13, 0);
      if ( NestedDirectory < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x48C,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
          (const char *)(unsigned int)NestedDirectory,
          (int)"Failed to create directory <%ws>> for user",
          (const char *)v13);
        goto LABEL_24;
      }
      CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v33);
      if ( !a3 )
      {
        v23 = StorageReserveHelper::SetReserveAreaOnFileTreeEx((StorageReserveHelper *)v13, v20, v21, v22);
        NestedDirectory = v23;
        if ( v23 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x492,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
            (const char *)(unsigned int)v23,
            phkResult);
          goto LABEL_25;
        }
      }
      if ( v16 )
        Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v16);
      if ( ppszPathOut )
        LocalFree(ppszPathOut);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&pszPathIn);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v32);
    }
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
}

```

## disassembly

```asm
0x180010734  push    rbp
0x180010736  push    rbx
0x180010737  push    rsi
0x180010738  push    rdi
0x180010739  push    r12
0x18001073b  push    r13
0x18001073d  push    r14
0x18001073f  push    r15
0x180010741  lea     rbp, [rsp-1Fh]
0x180010746  sub     rsp, 0A8h
0x18001074d  mov     r13, r9
0x180010750  mov     r12b, r8b
0x180010753  mov     r15, rdx
0x180010756  mov     rbx, rcx
0x180010759  xor     edi, edi
0x18001075b  mov     [rbp+57h+hKey], rdi
0x18001075f  xor     edx, edx
0x180010761  lea     rcx, [rbp+57h+hKey]
0x180010765  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001076a  lea     rax, [rbp+57h+hKey]
0x18001076e  mov     [rsp+0E0h+phkResult], rax; int
0x180010773  mov     r9d, 2001Fh; samDesired
0x180010779  xor     r8d, r8d; ulOptions
0x18001077c  mov     rdx, rbx; lpSubKey
0x18001077f  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180010786  call    cs:__imp_RegOpenKeyExW
0x18001078d  nop     dword ptr [rax+rax+00h]
0x180010792  test    eax, eax
0x180010794  jz      short loc_1800107C6
0x180010796  mov     rcx, [rbp+5Fh]; this
0x18001079a  mov     qword ptr [rsp+0E0h+cchCount2], rbx; char *
0x18001079f  lea     rdx, aFailedToOpenUs; "Failed to open user key for SID <%ls>."
0x1800107a6  mov     [rsp+0E0h+phkResult], rdx; unsigned int
0x1800107ab  mov     r9d, eax; char *
0x1800107ae  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800107b5  mov     edx, 470h; void *
0x1800107ba  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800107bf  mov     ebx, eax
0x1800107c1  jmp     loc_180010AC4
0x1800107c6  lea     rax, aTemp; "TEMP"
0x1800107cd  mov     [rbp+57h+var_58], rax
0x1800107d1  lea     rax, aTmp; "TMP"
0x1800107d8  mov     [rbp+57h+var_50], rax
0x1800107dc  mov     esi, edi
0x1800107de  cmp     esi, 2
0x1800107e1  jnb     loc_180010AD1
0x1800107e7  mov     [rbp+57h+var_80], rdi
0x1800107eb  mov     [rbp+57h+var_78], rdi
0x1800107ef  mov     [rbp+57h+var_70], rdi
0x1800107f3  movsxd  r9, esi
0x1800107f6  mov     r9, [rbp+r9*8+57h+var_58]
0x1800107fb  lea     r8, aEnvironment; "Environment"
0x180010802  mov     rdx, [rbp+57h+hKey]
0x180010806  lea     rcx, [rbp+57h+var_80]
0x18001080a  call    ?InitializeNoExpand@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeNoExpand(HKEY__ *,ushort const *,ushort const *)
0x18001080f  mov     ebx, eax
0x180010811  test    eax, eax
0x180010813  js      loc_180010AA1
0x180010819  mov     [rbp+57h+pszPathIn], rdi
0x18001081d  mov     [rbp+57h+var_90], rdi
0x180010821  mov     [rbp+57h+var_88], rdi
0x180010825  lea     rcx, [rbp+57h+pszPathIn]
0x180010829  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001082e  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFFh
0x180010836  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFFh
0x18001083e  lea     r8, [rbp+57h+pszPathIn]; unsigned __int16 **
0x180010842  mov     rdx, [rbp+57h+var_80]; unsigned __int16 *
0x180010846  mov     rcx, r15; void *
0x180010849  call    ?ExpandEnvStringAlloc@@YAJQEAXPEBGPEAPEAG@Z; ExpandEnvStringAlloc(void * const,ushort const *,ushort * *)
0x18001084e  mov     ebx, eax
0x180010850  test    eax, eax
0x180010852  js      loc_180010A87
0x180010858  mov     [rbp+57h+ppszPathOut], rdi
0x18001085c  lea     r8, [rbp+57h+ppszPathOut]; ppszPathOut
0x180010860  xor     edx, edx; dwFlags
0x180010862  mov     r14, [rbp+57h+pszPathIn]
0x180010866  mov     rcx, r14; pszPathIn
0x180010869  call    cs:__imp_PathAllocCanonicalize
0x180010870  nop     dword ptr [rax+rax+00h]
0x180010875  mov     ebx, eax
0x180010877  test    eax, eax
0x180010879  js      loc_180010A6D
0x18001087f  mov     [rbp+57h+lpString1], rdi
0x180010883  lea     r8, [rbp+57h+lpString1]; unsigned __int16 **
0x180010887  lea     rdx, aUserprofile_0; "%USERPROFILE%"
0x18001088e  mov     rcx, r15; void *
0x180010891  call    ?ExpandEnvStringAlloc@@YAJQEAXPEBGPEAPEAG@Z; ExpandEnvStringAlloc(void * const,ushort const *,ushort * *)
0x180010896  mov     ebx, eax
0x180010898  test    eax, eax
0x18001089a  js      loc_180010A53
0x1800108a0  mov     rbx, [rbp+57h+lpString1]
0x1800108a4  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800108a8  inc     r9; cchCount1
0x1800108ab  cmp     [rbx+r9*2], di
0x1800108b0  jnz     short loc_1800108A8
0x1800108b2  mov     rax, [rbp+57h+ppszPathOut]
0x1800108b6  mov     [rsp+0E0h+cchCount2], r9d; cchCount2
0x1800108bb  mov     [rsp+0E0h+phkResult], rax; int
0x1800108c0  mov     r8, rbx; lpString1
0x1800108c3  mov     edx, 1; dwCmpFlags
0x1800108c8  lea     ecx, [rdx+7Eh]; Locale
0x1800108cb  call    cs:__imp_CompareStringW
0x1800108d2  nop     dword ptr [rax+rax+00h]
0x1800108d7  cmp     eax, 2
0x1800108da  jnz     loc_180010A01
0x1800108e0  mov     [rbp+57h+var_68], rdi
0x1800108e4  mov     [rbp+57h+var_60], dil
0x1800108e8  mov     rdx, r13; void *
0x1800108eb  lea     rcx, [rbp+57h+var_68]; this
0x1800108ef  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x1800108f4  mov     edi, eax
0x1800108f6  test    eax, eax
0x1800108f8  js      loc_1800109B1
0x1800108fe  xor     edx, edx; lpSecurityAttributes
0x180010900  mov     rcx, r14; unsigned __int16 *
0x180010903  call    ?CreateNestedDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CreateNestedDirectory(ushort const *,_SECURITY_ATTRIBUTES *)
0x180010908  mov     edi, eax
0x18001090a  test    eax, eax
0x18001090c  js      short loc_180010986
0x18001090e  lea     rcx, [rbp+57h+var_68]; this
0x180010912  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x180010917  xor     edi, edi
0x180010919  test    r12b, r12b
0x18001091c  jnz     short loc_18001092E
0x18001091e  mov     rcx, r14; this
0x180010921  call    ?SetReserveAreaOnFileTreeEx@StorageReserveHelper@@YAJPEBGW4_STORAGE_RESERVE_ID@@K@Z; StorageReserveHelper::SetReserveAreaOnFileTreeEx(ushort const *,_STORAGE_RESERVE_ID,ulong)
0x180010926  mov     edi, eax
0x180010928  test    eax, eax
0x18001092a  js      short loc_18001096C
0x18001092c  xor     edi, edi
0x18001092e  test    rbx, rbx
0x180010931  jz      short loc_18001093C
0x180010933  mov     rcx, rbx
0x180010936  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x18001093b  nop
0x18001093c  mov     rcx, [rbp+57h+ppszPathOut]; hMem
0x180010940  test    rcx, rcx
0x180010943  jz      short loc_180010952
0x180010945  call    cs:__imp_LocalFree
0x18001094c  nop     dword ptr [rax+rax+00h]
0x180010951  nop
0x180010952  lea     rcx, [rbp+57h+pszPathIn]
0x180010956  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001095b  nop
0x18001095c  lea     rcx, [rbp+57h+var_80]
0x180010960  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180010965  inc     esi
0x180010967  jmp     loc_1800107DE
0x18001096c  mov     rcx, [rbp+5Fh]; this
0x180010970  mov     r9d, edi; char *
0x180010973  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001097a  mov     edx, 492h; void *
0x18001097f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010984  jmp     short loc_1800109D3
0x180010986  mov     rcx, [rbp+5Fh]; this
0x18001098a  mov     qword ptr [rsp+0E0h+cchCount2], r14; char *
0x18001098f  lea     rax, aFailedToCreate; "Failed to create directory <%ws>> for u"...
0x180010996  mov     [rsp+0E0h+phkResult], rax; int
0x18001099b  mov     r9d, edi; char *
0x18001099e  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800109a5  mov     edx, 48Ch; void *
0x1800109aa  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800109af  jmp     short loc_1800109C9
0x1800109b1  mov     rcx, [rbp+5Fh]; this
0x1800109b5  mov     r9d, edi; char *
0x1800109b8  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800109bf  mov     edx, 48Bh; void *
0x1800109c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800109c9  lea     rcx, [rbp+57h+var_68]; this
0x1800109cd  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x1800109d2  nop
0x1800109d3  lea     rcx, [rbp+57h+lpString1]
0x1800109d7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800109dc  nop
0x1800109dd  lea     rcx, [rbp+57h+ppszPathOut]
0x1800109e1  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800109e6  nop
0x1800109e7  lea     rcx, [rbp+57h+pszPathIn]
0x1800109eb  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800109f0  nop
0x1800109f1  lea     rcx, [rbp+57h+var_80]
0x1800109f5  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800109fa  mov     ebx, edi
0x1800109fc  jmp     loc_180010AC4
0x180010a01  mov     rcx, [rbp+5Fh]; this
0x180010a05  mov     rax, [rbp+57h+ppszPathOut]
0x180010a09  mov     qword ptr [rsp+0E0h+cchCount2], rax; char *
0x180010a0e  lea     rax, aTempDirectoryL; "TEMP directory <%ls> is not under user "...
0x180010a15  mov     [rsp+0E0h+phkResult], rax; int
0x180010a1a  mov     ebx, 80070005h
0x180010a1f  mov     r9d, ebx; char *
0x180010a22  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180010a29  mov     edx, 485h; void *
0x180010a2e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180010a33  nop
0x180010a34  lea     rcx, [rbp+57h+lpString1]
0x180010a38  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180010a3d  nop
0x180010a3e  lea     rcx, [rbp+57h+ppszPathOut]
0x180010a42  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180010a47  nop
0x180010a48  lea     rcx, [rbp+57h+pszPathIn]
0x180010a4c  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180010a51  jmp     short loc_180010ABA
0x180010a53  mov     rcx, [rbp+5Fh]; this
0x180010a57  mov     r9d, eax; char *
0x180010a5a  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180010a61  mov     edx, 482h; void *
0x180010a66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010a6b  jmp     short loc_180010A34
0x180010a6d  mov     rcx, [rbp+5Fh]; this
0x180010a71  mov     r9d, eax; char *
0x180010a74  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180010a7b  mov     edx, 47Fh; void *
0x180010a80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010a85  jmp     short loc_180010A3E
0x180010a87  mov     rcx, [rbp+5Fh]; this
0x180010a8b  mov     r9d, eax; char *
0x180010a8e  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180010a95  mov     edx, 47Ch; void *
0x180010a9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010a9f  jmp     short loc_180010A48
0x180010aa1  mov     rcx, [rbp+5Fh]; this
0x180010aa5  mov     r9d, eax; char *
0x180010aa8  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180010aaf  mov     edx, 479h; void *
0x180010ab4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010ab9  nop
0x180010aba  lea     rcx, [rbp+57h+var_80]
0x180010abe  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180010ac3  nop
0x180010ac4  lea     rcx, [rbp+57h+hKey]
0x180010ac8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180010acd  mov     eax, ebx
0x180010acf  jmp     short loc_180010AE8
0x180010ad1  mov     rcx, [rbp+57h+hKey]; hKey
0x180010ad5  test    rcx, rcx
0x180010ad8  jz      short loc_180010AE6
0x180010ada  call    cs:__imp_RegCloseKey
0x180010ae1  nop     dword ptr [rax+rax+00h]
0x180010ae6  xor     eax, eax
0x180010ae8  add     rsp, 0A8h
0x180010aef  pop     r15
0x180010af1  pop     r14
0x180010af3  pop     r13
0x180010af5  pop     r12
0x180010af7  pop     rdi
0x180010af8  pop     rsi
0x180010af9  pop     rbx
0x180010afa  pop     rbp
0x180010afb  retn
```
