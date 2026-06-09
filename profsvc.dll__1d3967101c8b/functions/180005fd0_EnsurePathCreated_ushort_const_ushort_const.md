# EnsurePathCreated(ushort const *,ushort const *)

- ea: `0x180005fd0`
- end: `0x180006575`
- name: `?EnsurePathCreated@@YAJPEBG0@Z`
- size: `1445`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR StringSecurityDescriptor)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001de34`

## callees

- `0x180005fd0`
- `0x180006580`
- `0x180012290`
- `0x180021980`
- `0x18002d2d8`
- `0x18002db38`
- `0x180032228`
- `0x180032aa8`
- `0x18003a730`
- `0x180041e18`
- `0x18004ca38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006276`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006276`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18000618a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18000633b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18000618a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18000633b`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180006268`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800062b9`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180006268`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800062b9`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800061f0`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800061f0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000628b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000628b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006057`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800062e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006366`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800063c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800063ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000640f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006490`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006514`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000654b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006057`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800062e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006366`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800063c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800063ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000640f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006490`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006514`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000654b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000609a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180006120`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000609a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180006120`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180006022`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180006022`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18000630d`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180006393`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180006461`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800064e5`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18000630d`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180006393`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180006461`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800064e5`

## string_xrefs

- `0x180006033`: `Failed to convert security descriptor.`
- `0x18000603a`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18000619b`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180006201`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x1800062ca`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180006350`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x1800063a4`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180006423`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180006472`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x1800064a7`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x1800064f6`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18000652d`: `onecore\ds\security\gina\profile\profsvc\util.cpp`

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
0x180005fd0  push    rbp
0x180005fd2  push    rbx
0x180005fd3  push    rsi
0x180005fd4  lea     rbp, [rsp-1D0h]
0x180005fdc  sub     rsp, 2D0h
0x180005fe3  mov     rax, cs:__security_cookie
0x180005fea  xor     rax, rsp
0x180005fed  mov     [rbp+1E0h+var_20], rax
0x180005ff4  xor     esi, esi
0x180005ff6  mov     [rsp+2E0h+lpFileName], rcx
0x180005ffb  mov     eax, esi
0x180005ffd  mov     r10, rdx
0x180006000  mov     [rsp+2E0h+SecurityDescriptor], rax
0x180006005  mov     rbx, rcx
0x180006008  test    rdx, rdx
0x18000600b  jz      short loc_18000606E
0x18000600d  cmp     [rdx], ax
0x180006010  jz      short loc_18000606E
0x180006012  xor     r9d, r9d; SecurityDescriptorSize
0x180006015  lea     r8, [rsp+2E0h+SecurityDescriptor]; SecurityDescriptor
0x18000601a  mov     edx, 1; StringSDRevision
0x18000601f  mov     rcx, r10; StringSecurityDescriptor
0x180006022  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180006028  test    eax, eax
0x18000602a  jnz     short loc_180006064
0x18000602c  mov     rcx, [rbp+1E8h]; this
0x180006033  lea     r9, aFailedToConver; "Failed to convert security descriptor."
0x18000603a  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180006041  mov     edx, 3C2h; void *
0x180006046  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18000604b  mov     rcx, [rsp+2E0h+SecurityDescriptor]; hMem
0x180006050  mov     ebx, eax
0x180006052  test    rcx, rcx
0x180006055  jz      short loc_18000605D
0x180006057  call    cs:__imp_LocalFree
0x18000605d  mov     eax, ebx
0x18000605f  jmp     loc_18000655B
0x180006064  mov     rax, [rsp+2E0h+SecurityDescriptor]
0x180006069  mov     rbx, [rsp+2E0h+lpFileName]
0x18000606e  mov     rcx, rbx; unsigned __int16 *
0x180006071  mov     [rsp+2E0h+arg_10], rdi
0x180006079  mov     qword ptr [rbp+1E0h+SecurityAttributes.nLength], 18h
0x180006081  mov     qword ptr [rbp+1E0h+SecurityAttributes.bInheritHandle], rsi
0x180006085  mov     [rbp+1E0h+SecurityAttributes.lpSecurityDescriptor], rax
0x180006089  call    ?IsFullPath@@YAHPEBG@Z; IsFullPath(ushort const *)
0x18000608e  test    eax, eax
0x180006090  jz      loc_180006521
0x180006096  lea     rdx, [rbp+1E0h+SecurityAttributes]; lpSecurityAttributes
0x18000609a  call    cs:__imp_CreateDirectoryW
0x1800060a0  mov     ecx, eax; int
0x1800060a2  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800060a7  cmp     eax, 80070003h
0x1800060ac  jnz     loc_18000614E
0x1800060b2  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800060b9  cmp     [rbx+rax*2+2], si
0x1800060be  lea     rax, [rax+1]
0x1800060c2  jnz     short loc_1800060B9
0x1800060c4  cmp     word ptr [rbx+rax*2-2], 5Ch ; '\'
0x1800060ca  lea     rcx, [rbp+1E0h+PathName]; unsigned __int16 *
0x1800060ce  mov     edx, 104h; unsigned __int64
0x1800060d3  jnz     short loc_1800060DF
0x1800060d5  mov     r8, rbx; unsigned __int16 *
0x1800060d8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800060dd  jmp     short loc_1800060EE
0x1800060df  mov     r9, rbx
0x1800060e2  lea     r8, aS_0; "%s\\"
0x1800060e9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800060ee  test    eax, eax
0x1800060f0  js      short loc_180006149
0x1800060f2  movzx   ecx, [rbp+1E0h+var_22A]
0x1800060f6  test    cx, cx
0x1800060f9  jz      short loc_18000614E
0x1800060fb  mov     [rsp+2E0h+arg_18], r14
0x180006103  lea     rbx, [rbp+1E0h+var_22A]
0x180006107  cmp     cx, 5Ch ; '\'
0x18000610b  jnz     short loc_180006132
0x18000610d  cmp     [rbx+2], si
0x180006111  lea     rdx, [rbp+1E0h+SecurityAttributes]
0x180006115  lea     rcx, [rbp+1E0h+PathName]; lpPathName
0x180006119  mov     [rbx], si
0x18000611c  cmovnz  rdx, rsi; lpSecurityAttributes
0x180006120  call    cs:__imp_CreateDirectoryW
0x180006126  mov     ecx, eax; int
0x180006128  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18000612d  mov     word ptr [rbx], 5Ch ; '\'
0x180006132  movzx   ecx, word ptr [rbx+2]
0x180006136  add     rbx, 2
0x18000613a  test    cx, cx
0x18000613d  jnz     short loc_180006107
0x18000613f  mov     r14, [rsp+2E0h+arg_18]
0x180006147  jmp     short loc_18000614E
0x180006149  mov     eax, 800700CEh
0x18000614e  cmp     eax, 800700B7h
0x180006153  mov     ebx, esi
0x180006155  cmovnz  ebx, eax
0x180006158  test    ebx, ebx
0x18000615a  js      loc_180006526
0x180006160  mov     rcx, [rsp+2E0h+SecurityDescriptor]; pSecurityDescriptor
0x180006165  test    rcx, rcx
0x180006168  jz      loc_180006415
0x18000616e  lea     r9, [rsp+2E0h+bSaclDefaulted]; lpbSaclDefaulted
0x180006173  mov     [rsp+2E0h+pSacl], rsi
0x180006178  lea     r8, [rsp+2E0h+pSacl]; pSacl
0x18000617d  mov     [rsp+2E0h+bSaclPresent], esi
0x180006181  lea     rdx, [rsp+2E0h+bSaclPresent]; lpbSaclPresent
0x180006186  mov     [rsp+2E0h+bSaclDefaulted], esi
0x18000618a  call    cs:__imp_GetSecurityDescriptorSacl
0x180006190  test    eax, eax
0x180006192  jnz     short loc_1800061C1
0x180006194  mov     rcx, [rbp+1E8h]; this
0x18000619b  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800061a2  mov     edx, 3D2h; void *
0x1800061a7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800061ac  mov     rcx, [rsp+2E0h+SecurityDescriptor]
0x1800061b1  mov     ebx, eax
0x1800061b3  test    rcx, rcx
0x1800061b6  jnz     loc_18000654B
0x1800061bc  jmp     loc_180006551
0x1800061c1  cmp     [rsp+2E0h+bSaclPresent], esi
0x1800061c5  jz      loc_180006405
0x1800061cb  mov     rcx, [rsp+2E0h+pSacl]; pAcl
0x1800061d0  test    rcx, rcx
0x1800061d3  jz      loc_180006405
0x1800061d9  cmp     word ptr [rcx+4], 1
0x1800061de  jnz     loc_180006405
0x1800061e4  lea     r8, [rsp+2E0h+pAce]; pAce
0x1800061e9  mov     [rsp+2E0h+pAce], rsi
0x1800061ee  xor     edx, edx; dwAceIndex
0x1800061f0  call    cs:__imp_GetAce
0x1800061f6  test    eax, eax
0x1800061f8  jnz     short loc_180006227
0x1800061fa  mov     rcx, [rbp+1E8h]; this
0x180006201  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180006208  mov     edx, 3D8h; void *
0x18000620d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006212  mov     rcx, [rsp+2E0h+SecurityDescriptor]
0x180006217  mov     ebx, eax
0x180006219  test    rcx, rcx
0x18000621c  jnz     loc_18000654B
0x180006222  jmp     loc_180006551
0x180006227  mov     rax, [rsp+2E0h+pAce]
0x18000622c  cmp     byte ptr [rax], 11h
0x18000622f  jnz     loc_180006405
0x180006235  mov     rcx, [rsp+2E0h+lpFileName]; lpFileName
0x18000623a  lea     rax, [rsp+2E0h+lpFileName]
0x18000623f  mov     [rbp+1E0h+var_248], rax
0x180006243  xor     r9d, r9d; nLength
0x180006246  lea     rax, [rsp+2E0h+pSacl]
0x18000624b  mov     [rsp+2E0h+nLengthNeeded], esi
0x18000624f  mov     [rbp+1E0h+var_240], rax
0x180006253  xor     r8d, r8d; pSecurityDescriptor
0x180006256  lea     rax, [rsp+2E0h+nLengthNeeded]
0x18000625b  mov     edx, 10h; RequestedInformation
0x180006260  mov     [rsp+2E0h+lpnLengthNeeded], rax; int
0x180006265  mov     dil, 1
0x180006268  call    cs:__imp_GetFileSecurityW
0x18000626e  test    eax, eax
0x180006270  jnz     loc_1800064A0
0x180006276  call    cs:__imp_GetLastError
0x18000627c  cmp     eax, 7Ah ; 'z'
0x18000627f  jnz     loc_1800064A0
0x180006285  mov     edx, [rsp+2E0h+nLengthNeeded]; uBytes
0x180006289  xor     ecx, ecx; uFlags
0x18000628b  call    cs:__imp_LocalAlloc
0x180006291  mov     rbx, rax
0x180006294  test    rax, rax
0x180006297  jz      loc_18000641C
0x18000629d  mov     r9d, [rsp+2E0h+nLengthNeeded]; nLength
0x1800062a2  lea     rax, [rsp+2E0h+nLengthNeeded]
0x1800062a7  mov     rcx, [rsp+2E0h+lpFileName]; lpFileName
0x1800062ac  mov     r8, rbx; pSecurityDescriptor
0x1800062af  mov     edx, 10h; RequestedInformation
0x1800062b4  mov     [rsp+2E0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1800062b9  call    cs:__imp_GetFileSecurityW
0x1800062bf  test    eax, eax
0x1800062c1  jnz     short loc_180006320
0x1800062c3  mov     rcx, [rbp+1E8h]; this
0x1800062ca  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800062d1  mov     edx, 3E5h; void *
0x1800062d6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800062db  mov     rcx, rbx; hMem
0x1800062de  mov     edi, eax
0x1800062e0  call    cs:__imp_LocalFree
0x1800062e6  mov     rcx, [rsp+2E0h+pSacl]
0x1800062eb  xor     r9d, r9d; psidOwner
0x1800062ee  mov     [rsp+2E0h+var_2B0], rcx; pSacl
0x1800062f3  mov     edx, 1; ObjectType
0x1800062f8  mov     rcx, [rsp+2E0h+lpFileName]; pObjectName
0x1800062fd  mov     r8d, 10h; SecurityInfo
0x180006303  mov     [rsp+2E0h+pDacl], rsi; pDacl
0x180006308  mov     [rsp+2E0h+lpnLengthNeeded], rsi; psidGroup
0x18000630d  call    cs:__imp_SetNamedSecurityInfoW
0x180006313  test    eax, eax
0x180006315  jnz     loc_18000639D
0x18000631b  jmp     loc_1800063B8
0x180006320  lea     r9, [rsp+2E0h+bSaclDefaulted]; lpbSaclDefaulted
0x180006325  mov     [rsp+2E0h+var_278], esi
0x180006329  lea     r8, [rsp+2E0h+var_268]; pSacl
0x18000632e  mov     [rsp+2E0h+var_268], rsi
0x180006333  lea     rdx, [rsp+2E0h+var_278]; lpbSaclPresent
0x180006338  mov     rcx, rbx; pSecurityDescriptor
0x18000633b  call    cs:__imp_GetSecurityDescriptorSacl
0x180006341  test    eax, eax
0x180006343  jnz     loc_1800063CF
0x180006349  mov     rcx, [rbp+1E8h]; this
0x180006350  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180006357  mov     edx, 3E9h; void *
0x18000635c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006361  mov     rcx, rbx; hMem
0x180006364  mov     edi, eax
0x180006366  call    cs:__imp_LocalFree
0x18000636c  mov     rcx, [rsp+2E0h+pSacl]
0x180006371  xor     r9d, r9d; psidOwner
0x180006374  mov     [rsp+2E0h+var_2B0], rcx; pSacl
0x180006379  mov     edx, 1; ObjectType
0x18000637e  mov     rcx, [rsp+2E0h+lpFileName]; pObjectName
0x180006383  mov     r8d, 10h; SecurityInfo
0x180006389  mov     [rsp+2E0h+pDacl], rsi; pDacl
0x18000638e  mov     [rsp+2E0h+lpnLengthNeeded], rsi; unsigned int
0x180006393  call    cs:__imp_SetNamedSecurityInfoW
0x180006399  test    eax, eax
0x18000639b  jz      short loc_1800063B8
0x18000639d  mov     rcx, [rbp+1E8h]; this
0x1800063a4  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800063ab  mov     r9d, eax; char *
0x1800063ae  mov     edx, 3DDh; void *
0x1800063b3  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800063b8  mov     rcx, [rsp+2E0h+SecurityDescriptor]; hMem
0x1800063bd  test    rcx, rcx
0x1800063c0  jz      short loc_1800063C8
0x1800063c2  call    cs:__imp_LocalFree
0x1800063c8  mov     eax, edi
0x1800063ca  jmp     loc_180006553
0x1800063cf  cmp     [rsp+2E0h+var_278], esi
0x1800063d3  jz      short loc_1800063EA
0x1800063d5  mov     rcx, [rsp+2E0h+var_268]
0x1800063da  test    rcx, rcx
0x1800063dd  jz      short loc_1800063EA
0x1800063df  cmp     [rcx+4], si
0x1800063e3  movzx   edi, dil
0x1800063e7  cmova   edi, esi
0x1800063ea  mov     rcx, rbx; hMem
0x1800063ed  call    cs:__imp_LocalFree
0x1800063f3  test    dil, dil
0x1800063f6  jz      short loc_180006405
0x1800063f8  lea     rcx, [rbp+1E0h+var_248]
0x1800063fc  mov     [rbp+1E0h+var_238], sil
0x180006400  call    _lambda_a5b93218b9bb554c04d7f94a3fa7c23e___operator__
0x180006405  mov     rcx, [rsp+2E0h+SecurityDescriptor]; hMem
0x18000640a  test    rcx, rcx
0x18000640d  jz      short loc_180006415
0x18000640f  call    cs:__imp_LocalFree
0x180006415  xor     eax, eax
0x180006417  jmp     loc_180006553
0x18000641c  mov     rcx, [rbp+1E8h]; this
0x180006423  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000642a  mov     r9d, 8007000Eh; char *
0x180006430  mov     edx, 3E4h; void *
0x180006435  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000643a  mov     rax, [rsp+2E0h+pSacl]
0x18000643f  xor     r9d, r9d; psidOwner
0x180006442  mov     rcx, [rsp+2E0h+lpFileName]; pObjectName
0x180006447  mov     edx, 1; ObjectType
0x18000644c  mov     [rsp+2E0h+var_2B0], rax; pSacl
0x180006451  mov     r8d, 10h; SecurityInfo
0x180006457  mov     [rsp+2E0h+pDacl], rsi; pDacl
0x18000645c  mov     [rsp+2E0h+lpnLengthNeeded], rsi; unsigned int
0x180006461  call    cs:__imp_SetNamedSecurityInfoW
0x180006467  test    eax, eax
0x180006469  jz      short loc_180006486
0x18000646b  mov     rcx, [rbp+1E8h]; this
0x180006472  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180006479  mov     r9d, eax; char *
0x18000647c  mov     edx, 3DDh; void *
0x180006481  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180006486  mov     rcx, [rsp+2E0h+SecurityDescriptor]; hMem
0x18000648b  test    rcx, rcx
0x18000648e  jz      short loc_180006496
0x180006490  call    cs:__imp_LocalFree
0x180006496  mov     eax, 8007000Eh
0x18000649b  jmp     loc_180006553
0x1800064a0  mov     rcx, [rbp+1E8h]; this
0x1800064a7  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800064ae  mov     r9d, 8007053Ah; char *
0x1800064b4  mov     edx, 3E1h; void *
0x1800064b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800064be  mov     rax, [rsp+2E0h+pSacl]
0x1800064c3  xor     r9d, r9d; psidOwner
0x1800064c6  mov     rcx, [rsp+2E0h+lpFileName]; pObjectName
0x1800064cb  mov     edx, 1; ObjectType
0x1800064d0  mov     [rsp+2E0h+var_2B0], rax; pSacl
0x1800064d5  mov     r8d, 10h; SecurityInfo
0x1800064db  mov     [rsp+2E0h+pDacl], rsi; pDacl
0x1800064e0  mov     [rsp+2E0h+lpnLengthNeeded], rsi; unsigned int
0x1800064e5  call    cs:__imp_SetNamedSecurityInfoW
0x1800064eb  test    eax, eax
0x1800064ed  jz      short loc_18000650A
0x1800064ef  mov     rcx, [rbp+1E8h]; this
0x1800064f6  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800064fd  mov     r9d, eax; char *
  ... truncated ...
```
