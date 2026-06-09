# UndetectedInstallerIsPathInteresting(int *,ushort *,unsigned __int64,void *)

- ea: `0x1800b6938`
- end: `0x1800b6cf3`
- name: `?UndetectedInstallerIsPathInteresting@@YAKPEAHPEAG_KPEAX@Z`
- size: `955`
- prototype: `unsigned int(int *, unsigned __int16 *, unsigned __int64, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800b6cfc`

## callees

- `0x18000dc08`
- `0x180012920`
- `0x1800b6938`
- `0x1800ee188`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!_wcslwr` at `0x1800b6c4c`
- `msvcrt!_wcslwr` at `0x1800b6c55`
- `msvcrt!_wcslwr` at `0x1800b6c4c`
- `msvcrt!_wcslwr` at `0x1800b6c55`
- `msvcrt!wcsrchr` at `0x1800b6b08`
- `msvcrt!wcsrchr` at `0x1800b6b08`
- `msvcrt!_wcsnicmp` at `0x1800b6aa6`
- `msvcrt!_wcsnicmp` at `0x1800b6aa6`
- `msvcrt!wcsstr` at `0x1800b6c62`
- `msvcrt!wcsstr` at `0x1800b6c62`
- `msvcrt!wcschr` at `0x1800b6aba`
- `msvcrt!wcschr` at `0x1800b6aba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6a1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6a70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6c1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6a1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6a70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6c1e`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x1800b6a4a`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x1800b6a4a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800b6bf4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800b6bf4`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800b6a10`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800b6c14`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800b6a10`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800b6c14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b6cac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b6cac`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x1800b6c3f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x1800b6c3f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800b6b3b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800b6b3b`

## string_xrefs

- `0x1800b69ef`: `Bypassing scenario for path %S`
- `0x1800b69bc`: `UndetectedInstallerIsPathInteresting`
- `0x1800b6a61`: `UndetectedInstallerIsPathInteresting`
- `0x1800b6ada`: `UndetectedInstallerIsPathInteresting`
- `0x1800b6b52`: `UndetectedInstallerIsPathInteresting`
- `0x1800b6bd8`: `UndetectedInstallerIsPathInteresting`
- `0x1800b6c68`: `UndetectedInstallerIsPathInteresting`
- `0x1800b69a5`: `Bypassing scenario - Path %S does not contain leading backslash.`
- `0x1800b6c24`: `Failed to get Windows directory path [%d]`
- `0x1800b6bcb`: `Could not construct virtual directory path.`
- `0x1800b6acd`: `Invalid file path %S`
- `0x1800b6b80`: `Error getting local appdata path [%d]`
- `0x1800b6b45`: `Error converting user sid to string.`
- `0x1800b6b20`: `Invalid file name path %S`

## pseudocode

```c
__int64 __fastcall UndetectedInstallerIsPathInteresting(int *a1, unsigned __int16 *a2, size_t a3, void *a4)
{
  DWORD VolatileEnvForUser; // ebx
  int v8; // r12d
  const char *v9; // r9
  int v10; // r8d
  int v11; // ecx
  const wchar_t *v12; // rsi
  unsigned __int16 v13; // cx
  unsigned __int16 *v14; // rax
  size_t v15; // rbx
  wchar_t *v16; // rax
  const char *v17; // r9
  int v18; // r8d
  int v19; // ebx
  wchar_t *v20; // rax
  unsigned int v21; // edx
  DWORD v22; // eax
  wchar_t *v23; // rbx
  wchar_t *v24; // rax
  LPWSTR v25; // rcx
  DWORD LastError; // [rsp+20h] [rbp-E0h]
  LPWSTR StringSid; // [rsp+30h] [rbp-D0h] BYREF
  int *v29; // [rsp+38h] [rbp-C8h]
  WCHAR Dst[8]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t TargetPath[64]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR FileName[264]; // [rsp+D0h] [rbp-30h] BYREF
  _WORD pvData[264]; // [rsp+2E0h] [rbp+1E0h] BYREF
  WCHAR pszPath[264]; // [rsp+4F0h] [rbp+3F0h] BYREF

  VolatileEnvForUser = 0;
  v29 = a1;
  FileName[0] = 0;
  pvData[0] = 0;
  pszPath[0] = 0;
  Dst[0] = 0;
  v8 = 0;
  TargetPath[0] = 0;
  StringSid = 0;
  if ( *a2 != 92 )
  {
    v9 = "Bypassing scenario - Path %S does not contain leading backslash.";
    v10 = 491;
LABEL_3:
    v11 = 3;
LABEL_4:
    AslLogCallPrintf(v11, (unsigned int)"UndetectedInstallerIsPathInteresting", v10, (_DWORD)v9);
    goto LABEL_41;
  }
  v12 = a2 + 1;
  v13 = a2[1];
  v14 = a2 + 1;
  while ( v13 && v13 != 92 )
    v13 = *++v14;
  if ( !*v14 )
  {
    v9 = "Bypassing scenario for path %S";
    v10 = 511;
    goto LABEL_3;
  }
  if ( !ExpandEnvironmentStringsW(L"%SystemDrive%", Dst, 3u) )
  {
    LastError = GetLastError();
    v9 = "Failed to get system drive prefix [%d]";
    VolatileEnvForUser = LastError;
    v10 = 525;
    v11 = 1;
    goto LABEL_4;
  }
  if ( !QueryDosDeviceW(Dst, TargetPath, 0x40u) )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"UndetectedInstallerIsPathInteresting",
      532,
      (unsigned int)"Failed to get system drive device name.");
    VolatileEnvForUser = GetLastError();
    goto LABEL_41;
  }
  v15 = -1;
  do
    ++v15;
  while ( TargetPath[v15] );
  if ( a3 <= v15 || _wcsnicmp(a2, TargetPath, v15) )
  {
    v19 = 0;
  }
  else
  {
    v16 = wcschr(&a2[v15], 0x5Cu);
    if ( !v16 )
    {
      v17 = "Invalid file path %S";
      v18 = 565;
LABEL_21:
      AslLogCallPrintf(1, (unsigned int)"UndetectedInstallerIsPathInteresting", v18, (_DWORD)v17);
LABEL_22:
      VolatileEnvForUser = 1359;
      goto LABEL_41;
    }
    v19 = 1;
    v12 = v16 + 1;
  }
  v20 = wcsrchr(v12, 0x5Cu);
  if ( !v20 )
  {
    if ( !v19 )
    {
      v17 = "Invalid file name path %S";
      v18 = 598;
      goto LABEL_21;
    }
    goto LABEL_40;
  }
  *v20 = 0;
  if ( !ConvertSidToStringSidW(a4, &StringSid) )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"UndetectedInstallerIsPathInteresting",
      611,
      (unsigned int)"Error converting user sid to string.");
    goto LABEL_22;
  }
  VolatileEnvForUser = PcaUtilityGetVolatileEnvForUser(pvData, v21, StringSid, L"LOCALAPPDATA");
  if ( VolatileEnvForUser )
  {
    v9 = "Error getting local appdata path [%d]";
    v10 = 625;
LABEL_32:
    v11 = 1;
    goto LABEL_4;
  }
  if ( StringCchPrintfW(FileName, 0x104u, L"%s\\%s\\%s", pvData, L"VirtualStore", v12) < 0 )
  {
    VolatileEnvForUser = 122;
    AslLogCallPrintf(
      1,
      (unsigned int)"UndetectedInstallerIsPathInteresting",
      636,
      (unsigned int)"Could not construct virtual directory path.");
    goto LABEL_41;
  }
  if ( GetFileAttributesW(FileName) == -1 )
  {
    if ( !ExpandEnvironmentStringsW(L"%windir%", pszPath, 0x104u) )
    {
      v22 = GetLastError();
      v9 = "Failed to get Windows directory path [%d]";
      v10 = 657;
      VolatileEnvForUser = v22;
      goto LABEL_32;
    }
    v23 = PathSkipRootW(pszPath);
    _wcslwr(FileName);
    _wcslwr(v23);
    v24 = wcsstr(FileName, v23);
    v11 = 3;
    if ( !v24 )
    {
      VolatileEnvForUser = 0;
      v9 = "Bypassing scenario - %S not found.";
      v10 = 676;
      goto LABEL_4;
    }
    AslLogCallPrintf(
      3,
      (unsigned int)"UndetectedInstallerIsPathInteresting",
      673,
      (unsigned int)"Including scenario - %S is in Windows.");
  }
LABEL_40:
  v8 = 1;
  VolatileEnvForUser = 0;
LABEL_41:
  v25 = StringSid;
  *v29 = v8;
  if ( v25 )
    LocalFree(v25);
  return VolatileEnvForUser;
}

```

## disassembly

```asm
0x1800b6938  mov     [rsp-8+arg_10], rbx
0x1800b693d  push    rbp
0x1800b693e  push    rsi
0x1800b693f  push    rdi
0x1800b6940  push    r12
0x1800b6942  push    r13
0x1800b6944  push    r14
0x1800b6946  push    r15
0x1800b6948  lea     rbp, [rsp-610h]
0x1800b6950  sub     rsp, 710h
0x1800b6957  mov     rax, cs:__security_cookie
0x1800b695e  xor     rax, rsp
0x1800b6961  mov     [rbp+640h+var_40], rax
0x1800b6968  xor     ebx, ebx
0x1800b696a  mov     [rsp+740h+var_708], rcx
0x1800b696f  mov     r14, rdx
0x1800b6972  mov     [rbp+640h+FileName], bx
0x1800b6976  mov     r13, r9
0x1800b6979  mov     [rbp+640h+pvData], bx
0x1800b6980  mov     r15, r8
0x1800b6983  mov     [rbp+640h+pszPath], bx
0x1800b698a  lea     edx, [rbx+5Ch]
0x1800b698d  mov     [rsp+740h+Dst], bx
0x1800b6992  mov     r12d, ebx
0x1800b6995  mov     [rsp+740h+TargetPath], bx
0x1800b699a  mov     [rsp+740h+StringSid], rbx
0x1800b699f  cmp     [r14], dx
0x1800b69a3  jz      short loc_1800B69CD
0x1800b69a5  lea     r9, aBypassingScena_0; "Bypassing scenario - Path %S does not c"...
0x1800b69ac  mov     r8d, 1EBh
0x1800b69b2  mov     [rsp+740h+var_720], r14
0x1800b69b7  mov     ecx, 3
0x1800b69bc  lea     rdx, aUndetectedinst_4; "UndetectedInstallerIsPathInteresting"
0x1800b69c3  call    AslLogCallPrintf
0x1800b69c8  jmp     loc_1800B6C9A
0x1800b69cd  lea     rsi, [r14+2]
0x1800b69d1  movzx   ecx, word ptr [rsi]
0x1800b69d4  mov     rax, rsi
0x1800b69d7  jmp     short loc_1800B69E5
0x1800b69d9  cmp     cx, dx
0x1800b69dc  jz      short loc_1800B69EA
0x1800b69de  add     rax, 2
0x1800b69e2  movzx   ecx, word ptr [rax]
0x1800b69e5  test    cx, cx
0x1800b69e8  jnz     short loc_1800B69D9
0x1800b69ea  cmp     [rax], bx
0x1800b69ed  jnz     short loc_1800B69FE
0x1800b69ef  lea     r9, aBypassingScena_1; "Bypassing scenario for path %S"
0x1800b69f6  mov     r8d, 1FFh
0x1800b69fc  jmp     short loc_1800B69B2
0x1800b69fe  mov     r8d, 3; nSize
0x1800b6a04  lea     rdx, [rsp+740h+Dst]; lpDst
0x1800b6a09  lea     rcx, aSystemdrive; "%SystemDrive%"
0x1800b6a10  call    cs:__imp_ExpandEnvironmentStringsW
0x1800b6a16  test    eax, eax
0x1800b6a18  jnz     short loc_1800B6A3A
0x1800b6a1a  call    cs:__imp_GetLastError
0x1800b6a20  mov     dword ptr [rsp+740h+var_720], eax
0x1800b6a24  lea     r9, aFailedToGetSys_0; "Failed to get system drive prefix [%d]"
0x1800b6a2b  mov     ebx, eax
0x1800b6a2d  mov     r8d, 20Dh
0x1800b6a33  mov     ecx, 1
0x1800b6a38  jmp     short loc_1800B69BC
0x1800b6a3a  mov     r8d, 40h ; '@'; ucchMax
0x1800b6a40  lea     rdx, [rsp+740h+TargetPath]; lpTargetPath
0x1800b6a45  lea     rcx, [rsp+740h+Dst]; lpDeviceName
0x1800b6a4a  call    cs:__imp_QueryDosDeviceW
0x1800b6a50  test    eax, eax
0x1800b6a52  jnz     short loc_1800B6A7D
0x1800b6a54  lea     r9, aFailedToGetSys_1; "Failed to get system drive device name."
0x1800b6a5b  mov     r8d, 214h
0x1800b6a61  lea     rdx, aUndetectedinst_4; "UndetectedInstallerIsPathInteresting"
0x1800b6a68  lea     ecx, [rax+1]
0x1800b6a6b  call    AslLogCallPrintf
0x1800b6a70  call    cs:__imp_GetLastError
0x1800b6a76  mov     ebx, eax
0x1800b6a78  jmp     loc_1800B6C9A
0x1800b6a7d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800b6a81  lea     rcx, [rsp+740h+TargetPath]
0x1800b6a86  xor     eax, eax
0x1800b6a88  inc     rbx
0x1800b6a8b  cmp     [rcx+rbx*2], ax
0x1800b6a8f  jnz     short loc_1800B6A88
0x1800b6a91  mov     edi, 1
0x1800b6a96  cmp     r15, rbx
0x1800b6a99  jbe     short loc_1800B6AFA
0x1800b6a9b  mov     r8, rbx; MaxCount
0x1800b6a9e  lea     rdx, [rsp+740h+TargetPath]; String2
0x1800b6aa3  mov     rcx, r14; String1
0x1800b6aa6  call    cs:__imp__wcsnicmp
0x1800b6aac  xor     r15d, r15d
0x1800b6aaf  test    eax, eax
0x1800b6ab1  jnz     short loc_1800B6AFD
0x1800b6ab3  lea     edx, [rdi+5Bh]; Ch
0x1800b6ab6  lea     rcx, [r14+rbx*2]; Str
0x1800b6aba  call    cs:__imp_wcschr
0x1800b6ac0  mov     rsi, rax
0x1800b6ac3  test    rax, rax
0x1800b6ac6  jnz     short loc_1800B6AF2
0x1800b6ac8  mov     [rsp+740h+var_720], r14
0x1800b6acd  lea     r9, aInvalidFilePat; "Invalid file path %S"
0x1800b6ad4  mov     r8d, 235h
0x1800b6ada  lea     rdx, aUndetectedinst_4; "UndetectedInstallerIsPathInteresting"
0x1800b6ae1  mov     ecx, edi
0x1800b6ae3  call    AslLogCallPrintf
0x1800b6ae8  mov     ebx, 54Fh
0x1800b6aed  jmp     loc_1800B6C9A
0x1800b6af2  mov     ebx, edi
0x1800b6af4  add     rsi, 2
0x1800b6af8  jmp     short loc_1800B6B00
0x1800b6afa  xor     r15d, r15d
0x1800b6afd  mov     ebx, r15d
0x1800b6b00  mov     edx, 5Ch ; '\'; Ch
0x1800b6b05  mov     rcx, rsi; Str
0x1800b6b08  call    cs:__imp_wcsrchr
0x1800b6b0e  test    rax, rax
0x1800b6b11  jnz     short loc_1800B6B2F
0x1800b6b13  test    ebx, ebx
0x1800b6b15  jnz     loc_1800B6C94
0x1800b6b1b  mov     [rsp+740h+var_720], rsi
0x1800b6b20  lea     r9, aInvalidFileNam; "Invalid file name path %S"
0x1800b6b27  mov     r8d, 256h
0x1800b6b2d  jmp     short loc_1800B6ADA
0x1800b6b2f  lea     rdx, [rsp+740h+StringSid]; StringSid
0x1800b6b34  mov     [rax], r15w
0x1800b6b38  mov     rcx, r13; Sid
0x1800b6b3b  call    cs:__imp_ConvertSidToStringSidW
0x1800b6b41  test    eax, eax
0x1800b6b43  jnz     short loc_1800B6B62
0x1800b6b45  lea     r9, aErrorConvertin; "Error converting user sid to string."
0x1800b6b4c  mov     r8d, 263h
0x1800b6b52  lea     rdx, aUndetectedinst_4; "UndetectedInstallerIsPathInteresting"
0x1800b6b59  mov     ecx, edi
0x1800b6b5b  call    AslLogCallPrintf
0x1800b6b60  jmp     short loc_1800B6AE8
0x1800b6b62  mov     r8, [rsp+740h+StringSid]; unsigned __int16 *
0x1800b6b67  lea     r9, aLocalappdata; "LOCALAPPDATA"
0x1800b6b6e  lea     rcx, [rbp+640h+pvData]; pvData
0x1800b6b75  call    ?PcaUtilityGetVolatileEnvForUser@@YAKPEAGIPEBG1@Z; PcaUtilityGetVolatileEnvForUser(ushort *,uint,ushort const *,ushort const *)
0x1800b6b7a  mov     ebx, eax
0x1800b6b7c  test    eax, eax
0x1800b6b7e  jz      short loc_1800B6B98
0x1800b6b80  lea     r9, aErrorGettingLo; "Error getting local appdata path [%d]"
0x1800b6b87  mov     r8d, 271h
0x1800b6b8d  mov     dword ptr [rsp+740h+var_720], eax
0x1800b6b91  mov     ecx, edi
0x1800b6b93  jmp     loc_1800B69BC
0x1800b6b98  lea     rax, aVirtualstore; "VirtualStore"
0x1800b6b9f  mov     [rsp+740h+var_718], rsi
0x1800b6ba4  mov     ebx, 104h
0x1800b6ba9  mov     [rsp+740h+var_720], rax
0x1800b6bae  mov     edx, ebx; unsigned __int64
0x1800b6bb0  lea     r9, [rbp+640h+pvData]
0x1800b6bb7  lea     r8, aSSS; "%s\\%s\\%s"
0x1800b6bbe  lea     rcx, [rbp+640h+FileName]; unsigned __int16 *
0x1800b6bc2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b6bc7  test    eax, eax
0x1800b6bc9  jns     short loc_1800B6BF0
0x1800b6bcb  lea     r9, aCouldNotConstr; "Could not construct virtual directory p"...
0x1800b6bd2  mov     r8d, 27Ch
0x1800b6bd8  lea     rdx, aUndetectedinst_4; "UndetectedInstallerIsPathInteresting"
0x1800b6bdf  mov     ecx, edi
0x1800b6be1  mov     ebx, 7Ah ; 'z'
0x1800b6be6  call    AslLogCallPrintf
0x1800b6beb  jmp     loc_1800B6C9A
0x1800b6bf0  lea     rcx, [rbp+640h+FileName]; lpFileName
0x1800b6bf4  call    cs:__imp_GetFileAttributesW
0x1800b6bfa  cmp     eax, 0FFFFFFFFh
0x1800b6bfd  jnz     loc_1800B6C94
0x1800b6c03  mov     r8d, ebx; nSize
0x1800b6c06  lea     rdx, [rbp+640h+pszPath]; lpDst
0x1800b6c0d  lea     rcx, aWindir; "%windir%"
0x1800b6c14  call    cs:__imp_ExpandEnvironmentStringsW
0x1800b6c1a  test    eax, eax
0x1800b6c1c  jnz     short loc_1800B6C38
0x1800b6c1e  call    cs:__imp_GetLastError
0x1800b6c24  lea     r9, aFailedToGetWin; "Failed to get Windows directory path [%"...
0x1800b6c2b  mov     r8d, 291h
0x1800b6c31  mov     ebx, eax
0x1800b6c33  jmp     loc_1800B6B8D
0x1800b6c38  lea     rcx, [rbp+640h+pszPath]; pszPath
0x1800b6c3f  call    cs:__imp_PathSkipRootW
0x1800b6c45  lea     rcx, [rbp+640h+FileName]; String
0x1800b6c49  mov     rbx, rax
0x1800b6c4c  call    cs:__imp__wcslwr
0x1800b6c52  mov     rcx, rbx; String
0x1800b6c55  call    cs:__imp__wcslwr
0x1800b6c5b  mov     rdx, rbx; SubStr
0x1800b6c5e  lea     rcx, [rbp+640h+FileName]; Str
0x1800b6c62  call    cs:__imp_wcsstr
0x1800b6c68  lea     rdx, aUndetectedinst_4; "UndetectedInstallerIsPathInteresting"
0x1800b6c6f  mov     ecx, 3
0x1800b6c74  test    rax, rax
0x1800b6c77  lea     rax, [rbp+640h+FileName]
0x1800b6c7b  mov     [rsp+740h+var_720], rax
0x1800b6c80  jz      short loc_1800B6CDE
0x1800b6c82  lea     r9, aIncludingScena; "Including scenario - %S is in Windows."
0x1800b6c89  mov     r8d, 2A1h
0x1800b6c8f  call    AslLogCallPrintf
0x1800b6c94  mov     r12d, edi
0x1800b6c97  mov     ebx, r15d
0x1800b6c9a  mov     rax, [rsp+740h+var_708]
0x1800b6c9f  mov     rcx, [rsp+740h+StringSid]; hMem
0x1800b6ca4  mov     [rax], r12d
0x1800b6ca7  test    rcx, rcx
0x1800b6caa  jz      short loc_1800B6CB2
0x1800b6cac  call    cs:__imp_LocalFree
0x1800b6cb2  mov     eax, ebx
0x1800b6cb4  mov     rcx, [rbp+640h+var_40]
0x1800b6cbb  xor     rcx, rsp; StackCookie
0x1800b6cbe  call    __security_check_cookie
0x1800b6cc3  mov     rbx, [rsp+740h+arg_10]
0x1800b6ccb  add     rsp, 710h
0x1800b6cd2  pop     r15
0x1800b6cd4  pop     r14
0x1800b6cd6  pop     r13
0x1800b6cd8  pop     r12
0x1800b6cda  pop     rdi
0x1800b6cdb  pop     rsi
0x1800b6cdc  pop     rbp
0x1800b6cdd  retn
0x1800b6cde  mov     ebx, r15d
0x1800b6ce1  lea     r9, aBypassingScena; "Bypassing scenario - %S not found."
0x1800b6ce8  mov     r8d, 2A4h
0x1800b6cee  jmp     loc_1800B69C3
```
