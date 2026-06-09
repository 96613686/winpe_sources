# EnsurePathCreated(ushort const *,ushort const *)

- ea: `0x1800115c0`
- end: `0x180011bf0`
- name: `?EnsurePathCreated@@YAJPEBG0@Z`
- size: `1584`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR StringSecurityDescriptor)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180021eec`

## callees

- `0x1800115c0`
- `0x180011c00`
- `0x1800172e0`
- `0x180024540`
- `0x18002df48`
- `0x180030ad0`
- `0x180032e94`
- `0x1800336f4`
- `0x18003bc70`
- `0x180043800`
- `0x18004fa60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011890`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011890`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180011792`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180011973`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180011792`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180011973`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18001187c`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800118df`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18001187c`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800118df`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800117fe`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800117fe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800118ab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800118ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001164d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001190c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800119a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011a0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011a3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011a65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011af2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011b82`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011bbf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001164d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001190c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800119a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011a0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011a3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011a65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011af2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011b82`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011bbf`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180011696`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180011722`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180011696`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180011722`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180011612`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180011612`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18001193f`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800119d7`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180011abd`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180011b4d`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18001193f`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800119d7`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180011abd`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180011b4d`

## string_xrefs

- `0x180011629`: `Failed to convert security descriptor.`
- `0x180011630`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x1800117a9`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180011815`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x1800118f6`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18001198e`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x1800119ee`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180011a7f`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180011ad4`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180011b0f`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180011b64`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180011ba1`: `onecore\ds\security\gina\profile\profsvc\util.cpp`

## pseudocode

```c
__int64 __fastcall EnsurePathCreated(const unsigned __int16 *a1, LPCWSTR StringSecurityDescriptor)
{
  PSECURITY_DESCRIPTOR v2; // rax
  const unsigned __int16 *v3; // rbx
  unsigned int LastErrorMsg; // ebx
  const WCHAR *v6; // rcx
  BOOL v7; // eax
  int v8; // eax
  __int64 v9; // rax
  bool v10; // zf
  __int16 v11; // cx
  __int16 *v12; // rbx
  struct _SECURITY_ATTRIBUTES *p_SecurityAttributes; // rdx
  BOOL DirectoryW; // eax
  unsigned int v15; // ebx
  const char *v16; // r9
  unsigned int LastError; // eax
  PSECURITY_DESCRIPTOR v18; // rcx
  const char *v19; // r9
  unsigned int v20; // eax
  bool v21; // di
  HLOCAL v22; // rbx
  const char *v23; // r9
  unsigned int v24; // edi
  DWORD v25; // eax
  const char *v26; // r9
  DWORD v27; // eax
  DWORD v28; // eax
  const char *lpnLengthNeeded; // [rsp+20h] [rbp-E0h]
  int lpnLengthNeededa; // [rsp+20h] [rbp-E0h]
  unsigned int lpnLengthNeededb; // [rsp+20h] [rbp-E0h]
  unsigned int lpnLengthNeededc; // [rsp+20h] [rbp-E0h]
  unsigned int lpnLengthNeededd; // [rsp+20h] [rbp-E0h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-C0h] BYREF
  DWORD nLengthNeeded; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpFileName; // [rsp+50h] [rbp-B0h] BYREF
  PACL pSacl; // [rsp+58h] [rbp-A8h] BYREF
  WINBOOL bSaclPresent; // [rsp+60h] [rbp-A0h] BYREF
  WINBOOL bSaclDefaulted; // [rsp+64h] [rbp-9Ch] BYREF
  WINBOOL v40; // [rsp+68h] [rbp-98h] BYREF
  LPVOID pAce; // [rsp+70h] [rbp-90h] BYREF
  PACL v42; // [rsp+78h] [rbp-88h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v44[2]; // [rsp+98h] [rbp-68h] BYREF
  char v45; // [rsp+A8h] [rbp-58h]
  WCHAR PathName[3]; // [rsp+B0h] [rbp-50h] BYREF
  __int16 v47; // [rsp+B6h] [rbp-4Ah] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  lpFileName = a1;
  v2 = 0;
  SecurityDescriptor = 0;
  v3 = a1;
  if ( StringSecurityDescriptor && *StringSecurityDescriptor )
  {
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
    {
      LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                       retaddr,
                       (void *)0x3C2,
                       (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
                       "Failed to convert security descriptor.",
                       lpnLengthNeeded);
      if ( SecurityDescriptor )
        LocalFree(SecurityDescriptor);
      return LastErrorMsg;
    }
    v2 = SecurityDescriptor;
    v3 = lpFileName;
  }
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  SecurityAttributes.lpSecurityDescriptor = v2;
  if ( !(unsigned int)IsFullPath(v3) )
  {
    v15 = -2147024735;
    goto LABEL_70;
  }
  v7 = CreateDirectoryW(v6, &SecurityAttributes);
  v8 = ResultFromWin32Bool(v7);
  if ( v8 == -2147024893 )
  {
    v9 = -1;
    do
      v10 = v3[++v9] == 0;
    while ( !v10 );
    if ( v3[v9 - 1] == 92 )
      v8 = StringCchCopyW(PathName, 0x104u, v3);
    else
      v8 = StringCchPrintfW(PathName, 0x104u, L"%s\\", v3);
    if ( v8 < 0 )
    {
      v8 = -2147024690;
    }
    else
    {
      v11 = v47;
      if ( v47 )
      {
        v12 = &v47;
        do
        {
          if ( v11 == 92 )
          {
            v10 = v12[1] == 0;
            p_SecurityAttributes = &SecurityAttributes;
            *v12 = 0;
            if ( !v10 )
              p_SecurityAttributes = 0;
            DirectoryW = CreateDirectoryW(PathName, p_SecurityAttributes);
            v8 = ResultFromWin32Bool(DirectoryW);
            *v12 = 92;
          }
          v11 = v12[1];
          ++v12;
        }
        while ( v11 );
      }
    }
  }
  v15 = 0;
  if ( v8 != -2147024713 )
    v15 = v8;
  if ( (v15 & 0x80000000) != 0 )
  {
LABEL_70:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3CA,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
      (const char *)v15,
      (int)lpnLengthNeeded);
    v18 = SecurityDescriptor;
    if ( !SecurityDescriptor )
      return v15;
LABEL_71:
    LocalFree(v18);
    return v15;
  }
  if ( !SecurityDescriptor )
    return 0;
  pSacl = 0;
  bSaclPresent = 0;
  bSaclDefaulted = 0;
  if ( !GetSecurityDescriptorSacl(SecurityDescriptor, &bSaclPresent, &pSacl, &bSaclDefaulted) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x3D2,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
                  v16);
    v18 = SecurityDescriptor;
    v15 = LastError;
    if ( !SecurityDescriptor )
      return v15;
    goto LABEL_71;
  }
  if ( !bSaclPresent || !pSacl || pSacl->AceCount != 1 )
    goto LABEL_56;
  pAce = 0;
  if ( !GetAce(pSacl, 0, &pAce) )
  {
    v20 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x3D8,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
            v19);
    v18 = SecurityDescriptor;
    v15 = v20;
    if ( !SecurityDescriptor )
      return v15;
    goto LABEL_71;
  }
  if ( *(_BYTE *)pAce != 17 )
  {
LABEL_56:
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    return 0;
  }
  v44[0] = &lpFileName;
  nLengthNeeded = 0;
  v44[1] = &pSacl;
  v21 = 1;
  if ( GetFileSecurityW(lpFileName, 0x10u, 0, 0, &nLengthNeeded) || GetLastError() != 122 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E1,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
      (const char *)0x8007053ALL,
      lpnLengthNeededa);
    v28 = SetNamedSecurityInfoW((LPWSTR)lpFileName, SE_FILE_OBJECT, 0x10u, 0, 0, 0, pSacl);
    if ( v28 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x3DD,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
        (const char *)v28,
        lpnLengthNeededd);
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    return 2147943738LL;
  }
  else
  {
    v22 = LocalAlloc(0, nLengthNeeded);
    if ( v22 )
    {
      if ( !GetFileSecurityW(lpFileName, 0x10u, v22, nLengthNeeded, &nLengthNeeded) )
      {
        v24 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x3E5,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
                v23);
        LocalFree(v22);
        v25 = SetNamedSecurityInfoW((LPWSTR)lpFileName, SE_FILE_OBJECT, 0x10u, 0, 0, 0, pSacl);
        if ( !v25 )
          goto LABEL_48;
        goto LABEL_47;
      }
      v40 = 0;
      v42 = 0;
      if ( !GetSecurityDescriptorSacl(v22, &v40, &v42, &bSaclDefaulted) )
      {
        v24 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x3E9,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
                v26);
        LocalFree(v22);
        v25 = SetNamedSecurityInfoW((LPWSTR)lpFileName, SE_FILE_OBJECT, 0x10u, 0, 0, 0, pSacl);
        if ( !v25 )
        {
LABEL_48:
          if ( SecurityDescriptor )
            LocalFree(SecurityDescriptor);
          return v24;
        }
LABEL_47:
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x3DD,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
          (const char *)v25,
          lpnLengthNeededb);
        goto LABEL_48;
      }
      if ( v40 && v42 )
        v21 = v42->AceCount == 0;
      LocalFree(v22);
      if ( v21 )
      {
        v45 = 0;
        lambda_a5b93218b9bb554c04d7f94a3fa7c23e_::operator()(v44);
      }
      goto LABEL_56;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E4,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
      (const char *)0x8007000ELL,
      lpnLengthNeededa);
    v27 = SetNamedSecurityInfoW((LPWSTR)lpFileName, SE_FILE_OBJECT, 0x10u, 0, 0, 0, pSacl);
    if ( v27 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x3DD,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
        (const char *)v27,
        lpnLengthNeededc);
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1800115c0  push    rbp
0x1800115c2  push    rbx
0x1800115c3  push    rsi
0x1800115c4  lea     rbp, [rsp-1D0h]
0x1800115cc  sub     rsp, 2D0h
0x1800115d3  mov     rax, cs:__security_cookie
0x1800115da  xor     rax, rsp
0x1800115dd  mov     [rbp+1E0h+var_20], rax
0x1800115e4  xor     esi, esi
0x1800115e6  mov     [rsp+2E0h+lpFileName], rcx
0x1800115eb  mov     eax, esi
0x1800115ed  mov     r10, rdx
0x1800115f0  mov     [rsp+2E0h+SecurityDescriptor], rax
0x1800115f5  mov     rbx, rcx
0x1800115f8  test    rdx, rdx
0x1800115fb  jz      short loc_18001166A
0x1800115fd  cmp     [rdx], ax
0x180011600  jz      short loc_18001166A
0x180011602  xor     r9d, r9d; SecurityDescriptorSize
0x180011605  lea     r8, [rsp+2E0h+SecurityDescriptor]; SecurityDescriptor
0x18001160a  mov     edx, 1; StringSDRevision
0x18001160f  mov     rcx, r10; StringSecurityDescriptor
0x180011612  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180011619  nop     dword ptr [rax+rax+00h]
0x18001161e  test    eax, eax
0x180011620  jnz     short loc_180011660
0x180011622  mov     rcx, [rbp+1E8h]; this
0x180011629  lea     r9, aFailedToConver; "Failed to convert security descriptor."
0x180011630  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180011637  mov     edx, 3C2h; void *
0x18001163c  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180011641  mov     rcx, [rsp+2E0h+SecurityDescriptor]; hMem
0x180011646  mov     ebx, eax
0x180011648  test    rcx, rcx
0x18001164b  jz      short loc_180011659
0x18001164d  call    cs:__imp_LocalFree
0x180011654  nop     dword ptr [rax+rax+00h]
0x180011659  mov     eax, ebx
0x18001165b  jmp     loc_180011BD5
0x180011660  mov     rax, [rsp+2E0h+SecurityDescriptor]
0x180011665  mov     rbx, [rsp+2E0h+lpFileName]
0x18001166a  mov     rcx, rbx; unsigned __int16 *
0x18001166d  mov     [rsp+2E0h+arg_10], rdi
0x180011675  mov     qword ptr [rbp+1E0h+SecurityAttributes.nLength], 18h
0x18001167d  mov     qword ptr [rbp+1E0h+SecurityAttributes.bInheritHandle], rsi
0x180011681  mov     [rbp+1E0h+SecurityAttributes.lpSecurityDescriptor], rax
0x180011685  call    ?IsFullPath@@YAHPEBG@Z; IsFullPath(ushort const *)
0x18001168a  test    eax, eax
0x18001168c  jz      loc_180011B95
0x180011692  lea     rdx, [rbp+1E0h+SecurityAttributes]; lpSecurityAttributes
0x180011696  call    cs:__imp_CreateDirectoryW
0x18001169d  nop     dword ptr [rax+rax+00h]
0x1800116a2  mov     ecx, eax; int
0x1800116a4  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800116a9  cmp     eax, 80070003h
0x1800116ae  jnz     loc_180011756
0x1800116b4  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800116bb  cmp     [rbx+rax*2+2], si
0x1800116c0  lea     rax, [rax+1]
0x1800116c4  jnz     short loc_1800116BB
0x1800116c6  cmp     word ptr [rbx+rax*2-2], 5Ch ; '\'
0x1800116cc  lea     rcx, [rbp+1E0h+PathName]; unsigned __int16 *
0x1800116d0  mov     edx, 104h; unsigned __int64
0x1800116d5  jnz     short loc_1800116E1
0x1800116d7  mov     r8, rbx; unsigned __int16 *
0x1800116da  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800116df  jmp     short loc_1800116F0
0x1800116e1  mov     r9, rbx
0x1800116e4  lea     r8, aS_0; "%s\\"
0x1800116eb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800116f0  test    eax, eax
0x1800116f2  js      short loc_180011751
0x1800116f4  movzx   ecx, [rbp+1E0h+var_22A]
0x1800116f8  test    cx, cx
0x1800116fb  jz      short loc_180011756
0x1800116fd  mov     [rsp+2E0h+arg_18], r14
0x180011705  lea     rbx, [rbp+1E0h+var_22A]
0x180011709  cmp     cx, 5Ch ; '\'
0x18001170d  jnz     short loc_18001173A
0x18001170f  cmp     [rbx+2], si
0x180011713  lea     rdx, [rbp+1E0h+SecurityAttributes]
0x180011717  lea     rcx, [rbp+1E0h+PathName]; lpPathName
0x18001171b  mov     [rbx], si
0x18001171e  cmovnz  rdx, rsi; lpSecurityAttributes
0x180011722  call    cs:__imp_CreateDirectoryW
0x180011729  nop     dword ptr [rax+rax+00h]
0x18001172e  mov     ecx, eax; int
0x180011730  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180011735  mov     word ptr [rbx], 5Ch ; '\'
0x18001173a  movzx   ecx, word ptr [rbx+2]
0x18001173e  add     rbx, 2
0x180011742  test    cx, cx
0x180011745  jnz     short loc_180011709
0x180011747  mov     r14, [rsp+2E0h+arg_18]
0x18001174f  jmp     short loc_180011756
0x180011751  mov     eax, 800700CEh
0x180011756  cmp     eax, 800700B7h
0x18001175b  mov     ebx, esi
0x18001175d  cmovnz  ebx, eax
0x180011760  test    ebx, ebx
0x180011762  js      loc_180011B9A
0x180011768  mov     rcx, [rsp+2E0h+SecurityDescriptor]; pSecurityDescriptor
0x18001176d  test    rcx, rcx
0x180011770  jz      loc_180011A71
0x180011776  lea     r9, [rsp+2E0h+bSaclDefaulted]; lpbSaclDefaulted
0x18001177b  mov     [rsp+2E0h+pSacl], rsi
0x180011780  lea     r8, [rsp+2E0h+pSacl]; pSacl
0x180011785  mov     [rsp+2E0h+bSaclPresent], esi
0x180011789  lea     rdx, [rsp+2E0h+bSaclPresent]; lpbSaclPresent
0x18001178e  mov     [rsp+2E0h+bSaclDefaulted], esi
0x180011792  call    cs:__imp_GetSecurityDescriptorSacl
0x180011799  nop     dword ptr [rax+rax+00h]
0x18001179e  test    eax, eax
0x1800117a0  jnz     short loc_1800117CF
0x1800117a2  mov     rcx, [rbp+1E8h]; this
0x1800117a9  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800117b0  mov     edx, 3D2h; void *
0x1800117b5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800117ba  mov     rcx, [rsp+2E0h+SecurityDescriptor]
0x1800117bf  mov     ebx, eax
0x1800117c1  test    rcx, rcx
0x1800117c4  jnz     loc_180011BBF
0x1800117ca  jmp     loc_180011BCB
0x1800117cf  cmp     [rsp+2E0h+bSaclPresent], esi
0x1800117d3  jz      loc_180011A5B
0x1800117d9  mov     rcx, [rsp+2E0h+pSacl]; pAcl
0x1800117de  test    rcx, rcx
0x1800117e1  jz      loc_180011A5B
0x1800117e7  cmp     word ptr [rcx+4], 1
0x1800117ec  jnz     loc_180011A5B
0x1800117f2  lea     r8, [rsp+2E0h+pAce]; pAce
0x1800117f7  mov     [rsp+2E0h+pAce], rsi
0x1800117fc  xor     edx, edx; dwAceIndex
0x1800117fe  call    cs:__imp_GetAce
0x180011805  nop     dword ptr [rax+rax+00h]
0x18001180a  test    eax, eax
0x18001180c  jnz     short loc_18001183B
0x18001180e  mov     rcx, [rbp+1E8h]; this
0x180011815  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001181c  mov     edx, 3D8h; void *
0x180011821  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011826  mov     rcx, [rsp+2E0h+SecurityDescriptor]
0x18001182b  mov     ebx, eax
0x18001182d  test    rcx, rcx
0x180011830  jnz     loc_180011BBF
0x180011836  jmp     loc_180011BCB
0x18001183b  mov     rax, [rsp+2E0h+pAce]
0x180011840  cmp     byte ptr [rax], 11h
0x180011843  jnz     loc_180011A5B
0x180011849  mov     rcx, [rsp+2E0h+lpFileName]; lpFileName
0x18001184e  lea     rax, [rsp+2E0h+lpFileName]
0x180011853  mov     [rbp+1E0h+var_248], rax
0x180011857  xor     r9d, r9d; nLength
0x18001185a  lea     rax, [rsp+2E0h+pSacl]
0x18001185f  mov     [rsp+2E0h+nLengthNeeded], esi
0x180011863  mov     [rbp+1E0h+var_240], rax
0x180011867  xor     r8d, r8d; pSecurityDescriptor
0x18001186a  lea     rax, [rsp+2E0h+nLengthNeeded]
0x18001186f  mov     edx, 10h; RequestedInformation
0x180011874  mov     [rsp+2E0h+lpnLengthNeeded], rax; int
0x180011879  mov     dil, 1
0x18001187c  call    cs:__imp_GetFileSecurityW
0x180011883  nop     dword ptr [rax+rax+00h]
0x180011888  test    eax, eax
0x18001188a  jnz     loc_180011B08
0x180011890  call    cs:__imp_GetLastError
0x180011897  nop     dword ptr [rax+rax+00h]
0x18001189c  cmp     eax, 7Ah ; 'z'
0x18001189f  jnz     loc_180011B08
0x1800118a5  mov     edx, [rsp+2E0h+nLengthNeeded]; uBytes
0x1800118a9  xor     ecx, ecx; uFlags
0x1800118ab  call    cs:__imp_LocalAlloc
0x1800118b2  nop     dword ptr [rax+rax+00h]
0x1800118b7  mov     rbx, rax
0x1800118ba  test    rax, rax
0x1800118bd  jz      loc_180011A78
0x1800118c3  mov     r9d, [rsp+2E0h+nLengthNeeded]; nLength
0x1800118c8  lea     rax, [rsp+2E0h+nLengthNeeded]
0x1800118cd  mov     rcx, [rsp+2E0h+lpFileName]; lpFileName
0x1800118d2  mov     r8, rbx; pSecurityDescriptor
0x1800118d5  mov     edx, 10h; RequestedInformation
0x1800118da  mov     [rsp+2E0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1800118df  call    cs:__imp_GetFileSecurityW
0x1800118e6  nop     dword ptr [rax+rax+00h]
0x1800118eb  test    eax, eax
0x1800118ed  jnz     short loc_180011958
0x1800118ef  mov     rcx, [rbp+1E8h]; this
0x1800118f6  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800118fd  mov     edx, 3E5h; void *
0x180011902  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011907  mov     rcx, rbx; hMem
0x18001190a  mov     edi, eax
0x18001190c  call    cs:__imp_LocalFree
0x180011913  nop     dword ptr [rax+rax+00h]
0x180011918  mov     rcx, [rsp+2E0h+pSacl]
0x18001191d  xor     r9d, r9d; psidOwner
0x180011920  mov     [rsp+2E0h+var_2B0], rcx; pSacl
0x180011925  mov     edx, 1; ObjectType
0x18001192a  mov     rcx, [rsp+2E0h+lpFileName]; pObjectName
0x18001192f  mov     r8d, 10h; SecurityInfo
0x180011935  mov     [rsp+2E0h+pDacl], rsi; pDacl
0x18001193a  mov     [rsp+2E0h+lpnLengthNeeded], rsi; psidGroup
0x18001193f  call    cs:__imp_SetNamedSecurityInfoW
0x180011946  nop     dword ptr [rax+rax+00h]
0x18001194b  test    eax, eax
0x18001194d  jnz     loc_1800119E7
0x180011953  jmp     loc_180011A02
0x180011958  lea     r9, [rsp+2E0h+bSaclDefaulted]; lpbSaclDefaulted
0x18001195d  mov     [rsp+2E0h+var_278], esi
0x180011961  lea     r8, [rsp+2E0h+var_268]; pSacl
0x180011966  mov     [rsp+2E0h+var_268], rsi
0x18001196b  lea     rdx, [rsp+2E0h+var_278]; lpbSaclPresent
0x180011970  mov     rcx, rbx; pSecurityDescriptor
0x180011973  call    cs:__imp_GetSecurityDescriptorSacl
0x18001197a  nop     dword ptr [rax+rax+00h]
0x18001197f  test    eax, eax
0x180011981  jnz     loc_180011A1F
0x180011987  mov     rcx, [rbp+1E8h]; this
0x18001198e  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180011995  mov     edx, 3E9h; void *
0x18001199a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001199f  mov     rcx, rbx; hMem
0x1800119a2  mov     edi, eax
0x1800119a4  call    cs:__imp_LocalFree
0x1800119ab  nop     dword ptr [rax+rax+00h]
0x1800119b0  mov     rcx, [rsp+2E0h+pSacl]
0x1800119b5  xor     r9d, r9d; psidOwner
0x1800119b8  mov     [rsp+2E0h+var_2B0], rcx; pSacl
0x1800119bd  mov     edx, 1; ObjectType
0x1800119c2  mov     rcx, [rsp+2E0h+lpFileName]; pObjectName
0x1800119c7  mov     r8d, 10h; SecurityInfo
0x1800119cd  mov     [rsp+2E0h+pDacl], rsi; pDacl
0x1800119d2  mov     [rsp+2E0h+lpnLengthNeeded], rsi; unsigned int
0x1800119d7  call    cs:__imp_SetNamedSecurityInfoW
0x1800119de  nop     dword ptr [rax+rax+00h]
0x1800119e3  test    eax, eax
0x1800119e5  jz      short loc_180011A02
0x1800119e7  mov     rcx, [rbp+1E8h]; this
0x1800119ee  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800119f5  mov     r9d, eax; char *
0x1800119f8  mov     edx, 3DDh; void *
0x1800119fd  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180011a02  mov     rcx, [rsp+2E0h+SecurityDescriptor]; hMem
0x180011a07  test    rcx, rcx
0x180011a0a  jz      short loc_180011A18
0x180011a0c  call    cs:__imp_LocalFree
0x180011a13  nop     dword ptr [rax+rax+00h]
0x180011a18  mov     eax, edi
0x180011a1a  jmp     loc_180011BCD
0x180011a1f  cmp     [rsp+2E0h+var_278], esi
0x180011a23  jz      short loc_180011A3A
0x180011a25  mov     rcx, [rsp+2E0h+var_268]
0x180011a2a  test    rcx, rcx
0x180011a2d  jz      short loc_180011A3A
0x180011a2f  cmp     [rcx+4], si
0x180011a33  movzx   edi, dil
0x180011a37  cmova   edi, esi
0x180011a3a  mov     rcx, rbx; hMem
0x180011a3d  call    cs:__imp_LocalFree
0x180011a44  nop     dword ptr [rax+rax+00h]
0x180011a49  test    dil, dil
0x180011a4c  jz      short loc_180011A5B
0x180011a4e  lea     rcx, [rbp+1E0h+var_248]
0x180011a52  mov     [rbp+1E0h+var_238], sil
0x180011a56  call    _lambda_a5b93218b9bb554c04d7f94a3fa7c23e___operator__
0x180011a5b  mov     rcx, [rsp+2E0h+SecurityDescriptor]; hMem
0x180011a60  test    rcx, rcx
0x180011a63  jz      short loc_180011A71
0x180011a65  call    cs:__imp_LocalFree
0x180011a6c  nop     dword ptr [rax+rax+00h]
0x180011a71  xor     eax, eax
0x180011a73  jmp     loc_180011BCD
0x180011a78  mov     rcx, [rbp+1E8h]; this
0x180011a7f  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180011a86  mov     r9d, 8007000Eh; char *
0x180011a8c  mov     edx, 3E4h; void *
0x180011a91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011a96  mov     rax, [rsp+2E0h+pSacl]
0x180011a9b  xor     r9d, r9d; psidOwner
0x180011a9e  mov     rcx, [rsp+2E0h+lpFileName]; pObjectName
0x180011aa3  mov     edx, 1; ObjectType
0x180011aa8  mov     [rsp+2E0h+var_2B0], rax; pSacl
0x180011aad  mov     r8d, 10h; SecurityInfo
0x180011ab3  mov     [rsp+2E0h+pDacl], rsi; pDacl
0x180011ab8  mov     [rsp+2E0h+lpnLengthNeeded], rsi; unsigned int
0x180011abd  call    cs:__imp_SetNamedSecurityInfoW
0x180011ac4  nop     dword ptr [rax+rax+00h]
0x180011ac9  test    eax, eax
0x180011acb  jz      short loc_180011AE8
0x180011acd  mov     rcx, [rbp+1E8h]; this
0x180011ad4  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180011adb  mov     r9d, eax; char *
0x180011ade  mov     edx, 3DDh; void *
0x180011ae3  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180011ae8  mov     rcx, [rsp+2E0h+SecurityDescriptor]; hMem
0x180011aed  test    rcx, rcx
0x180011af0  jz      short loc_180011AFE
0x180011af2  call    cs:__imp_LocalFree
0x180011af9  nop     dword ptr [rax+rax+00h]
0x180011afe  mov     eax, 8007000Eh
  ... truncated ...
```
