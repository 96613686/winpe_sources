# IsRegisteredShellFileName(ushort const * const *,int)

- ea: `0x14008a290`
- end: `0x14008a4b6`
- name: `?IsRegisteredShellFileName@@YA_NPEBQEBGH@Z`
- size: `550`
- prototype: `bool __fastcall(const unsigned __int16 *const *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400b9294`

## callees

- `0x14008a290`
- `0x14008a4bc`
- `0x14010e160`
- `0x140138190`
- `0x140138318`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x14008a46a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x14008a46a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14008a49a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14008a49a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14008a36c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14008a36c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x14008a423`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x14008a423`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksW` at `0x14008a413`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksW` at `0x14008a413`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x14008a3ef`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x14008a3ef`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!PathRemoveArgsW` at `0x14008a403`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!PathRemoveArgsW` at `0x14008a403`

## string_xrefs

- `0x14008a490`: `install.exe`

## pseudocode

```c
char __fastcall IsRegisteredShellFileName(const unsigned __int16 *const *a1, __int64 a2)
{
  int v3; // edx
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  int HighestValue; // ebx
  char v8; // bl
  LPWSTR FileNameW; // rax
  const WCHAR *v11; // rsi
  char v12; // di
  int v13; // r14d
  __int64 v14; // r8
  const WCHAR *v15; // rdx
  int pdwType; // [rsp+20h] [rbp-E0h]
  DWORD pvData; // [rsp+28h] [rbp-D8h]
  DWORD Type; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v19; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey[2]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszPath[264]; // [rsp+80h] [rbp-80h] BYREF
  BYTE v22[528]; // [rsp+290h] [rbp+190h] BYREF

  *(_OWORD *)hKey = 0;
  if ( (unsigned int)RegValChoice_Open(a1, a2, hKey) )
  {
    v19 = 520;
    Type = 0;
    HighestValue = RegValChoice_GetAndCompareRegValues(
                     v4,
                     v3,
                     v5,
                     v6,
                     pdwType,
                     pvData,
                     &Type,
                     (LPBYTE)pszPath,
                     v22,
                     (__int64)&v19,
                     (__int64)&v19 + 4);
    if ( !HighestValue && HIDWORD(v19) )
    {
      LODWORD(v19) = 520;
      Type = 0;
      HighestValue = RegValChoice_GetHighestValue(hKey, &Type, pszPath, &v19);
    }
    if ( LODWORD(hKey[0]) )
    {
      RegCloseKey(hKey[1]);
      LODWORD(hKey[0]) = 0;
    }
    if ( HighestValue )
      return 1;
  }
  else
  {
    Type = 520;
    if ( SHRegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
           L"Shell",
           2,
           0,
           pszPath,
           &Type) )
    {
      return 1;
    }
  }
  PathRemoveArgsW(pszPath);
  PathRemoveBlanksW(pszPath);
  FileNameW = PathFindFileNameW(pszPath);
  v11 = L"explorer.exe";
  v12 = 0;
  v13 = 0;
  v8 = 1;
  if ( *FileNameW )
    v11 = FileNameW;
  while ( !v12 )
  {
    v14 = -1;
    v15 = a1[v13];
    do
      ++v14;
    while ( v15[v14] );
    if ( !StrCmpNIW(v11, v15, v14) )
      v12 = 1;
    if ( ++v13 >= 1 )
    {
      if ( !v12 && StrCmpICW(v11, L"install.exe") )
        return 0;
      return v8;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x14008a290  mov     [rsp-8+arg_8], rbx
0x14008a295  mov     [rsp-8+arg_10], rsi
0x14008a29a  push    rbp
0x14008a29b  push    rdi
0x14008a29c  push    r12
0x14008a29e  push    r14
0x14008a2a0  push    r15
0x14008a2a2  lea     rbp, [rsp-3B0h]
0x14008a2aa  sub     rsp, 4B0h
0x14008a2b1  mov     rax, cs:__security_cookie
0x14008a2b8  xor     rax, rsp
0x14008a2bb  mov     [rbp+3D0h+var_30], rax
0x14008a2c2  xorps   xmm0, xmm0
0x14008a2c5  lea     r8, [rsp+4D0h+hKey]
0x14008a2ca  movups  xmmword ptr [rsp+4D0h+hKey], xmm0
0x14008a2cf  mov     r15, rcx
0x14008a2d2  call    RegValChoice_Open
0x14008a2d7  xor     r12d, r12d
0x14008a2da  test    eax, eax
0x14008a2dc  jz      loc_14008A3B4
0x14008a2e2  lea     rax, [rsp+4D0h+var_46C+4]
0x14008a2e7  mov     dword ptr [rsp+4D0h+var_46C+4], r12d
0x14008a2ec  mov     [rsp+4D0h+var_480], rax; __int64
0x14008a2f1  lea     rax, [rsp+4D0h+var_46C]
0x14008a2f6  mov     [rsp+4D0h+var_488], rax; __int64
0x14008a2fb  lea     rax, [rbp+3D0h+var_240]
0x14008a302  mov     [rsp+4D0h+var_490], rax; LPBYTE
0x14008a307  lea     rax, [rbp+3D0h+pszPath]
0x14008a30b  mov     [rsp+4D0h+lpData], rax; lpData
0x14008a310  lea     rax, [rsp+4D0h+Type]
0x14008a315  mov     [rsp+4D0h+pcbData], rax; lpType
0x14008a31a  mov     dword ptr [rsp+4D0h+var_46C], 208h
0x14008a322  mov     [rsp+4D0h+Type], r12d
0x14008a327  call    RegValChoice_GetAndCompareRegValues
0x14008a32c  mov     ebx, eax
0x14008a32e  test    eax, eax
0x14008a330  jnz     short loc_14008A360
0x14008a332  cmp     dword ptr [rsp+4D0h+var_46C+4], r12d
0x14008a337  jz      short loc_14008A360
0x14008a339  lea     r9, [rsp+4D0h+var_46C]
0x14008a33e  mov     dword ptr [rsp+4D0h+var_46C], 208h
0x14008a346  lea     r8, [rbp+3D0h+pszPath]
0x14008a34a  mov     [rsp+4D0h+Type], r12d
0x14008a34f  lea     rdx, [rsp+4D0h+Type]
0x14008a354  lea     rcx, [rsp+4D0h+hKey]
0x14008a359  call    RegValChoice_GetHighestValue
0x14008a35e  mov     ebx, eax
0x14008a360  cmp     dword ptr [rsp+4D0h+hKey], r12d
0x14008a365  jz      short loc_14008A37D
0x14008a367  mov     rcx, [rsp+4D0h+hKey+8]; hKey
0x14008a36c  call    cs:__imp_RegCloseKey
0x14008a373  nop     dword ptr [rax+rax+00h]
0x14008a378  mov     dword ptr [rsp+4D0h+hKey], r12d
0x14008a37d  test    ebx, ebx
0x14008a37f  jz      short loc_14008A3FF
0x14008a381  mov     ebx, 1
0x14008a386  mov     al, bl
0x14008a388  mov     rcx, [rbp+3D0h+var_30]
0x14008a38f  xor     rcx, rsp; StackCookie
0x14008a392  call    __security_check_cookie
0x14008a397  lea     r11, [rsp+4D0h+var_20]
0x14008a39f  mov     rbx, [r11+38h]
0x14008a3a3  mov     rsi, [r11+40h]
0x14008a3a7  mov     rsp, r11
0x14008a3aa  pop     r15
0x14008a3ac  pop     r14
0x14008a3ae  pop     r12
0x14008a3b0  pop     rdi
0x14008a3b1  pop     rbp
0x14008a3b2  retn
0x14008a3b4  lea     rax, [rsp+4D0h+Type]
0x14008a3b9  mov     [rsp+4D0h+Type], 208h
0x14008a3c1  mov     [rsp+4D0h+pcbData], rax; pcbData
0x14008a3c6  lea     r8, aShell; "Shell"
0x14008a3cd  lea     rax, [rbp+3D0h+pszPath]
0x14008a3d1  mov     r9d, 2; srrfFlags
0x14008a3d7  mov     [rsp+4D0h+pvData], rax; pvData
0x14008a3dc  lea     rdx, aSoftwareMicros_143; "Software\\Microsoft\\Windows NT\\Curren"...
0x14008a3e3  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14008a3ea  mov     [rsp+4D0h+pdwType], r12; pdwType
0x14008a3ef  call    cs:__imp_SHRegGetValueW
0x14008a3f6  nop     dword ptr [rax+rax+00h]
0x14008a3fb  test    eax, eax
0x14008a3fd  jnz     short loc_14008A381
0x14008a3ff  lea     rcx, [rbp+3D0h+pszPath]; pszPath
0x14008a403  call    cs:__imp_PathRemoveArgsW
0x14008a40a  nop     dword ptr [rax+rax+00h]
0x14008a40f  lea     rcx, [rbp+3D0h+pszPath]; pszPath
0x14008a413  call    cs:__imp_PathRemoveBlanksW
0x14008a41a  nop     dword ptr [rax+rax+00h]
0x14008a41f  lea     rcx, [rbp+3D0h+pszPath]; pszPath
0x14008a423  call    cs:__imp_PathFindFileNameW
0x14008a42a  nop     dword ptr [rax+rax+00h]
0x14008a42f  lea     rsi, aExplorerExe_0; "explorer.exe"
0x14008a436  mov     dil, r12b
0x14008a439  mov     r14d, r12d
0x14008a43c  mov     ebx, 1
0x14008a441  cmp     [rax], r12w
0x14008a445  cmovnz  rsi, rax
0x14008a449  test    dil, dil
0x14008a44c  jnz     loc_14008A386
0x14008a452  mov     eax, r14d
0x14008a455  or      r8, 0FFFFFFFFFFFFFFFFh
0x14008a459  mov     rdx, [r15+rax*8]; psz2
0x14008a45d  inc     r8; nChar
0x14008a460  cmp     [rdx+r8*2], r12w
0x14008a465  jnz     short loc_14008A45D
0x14008a467  mov     rcx, rsi; psz1
0x14008a46a  call    cs:__imp_StrCmpNIW
0x14008a471  nop     dword ptr [rax+rax+00h]
0x14008a476  test    eax, eax
0x14008a478  movzx   edi, dil
0x14008a47c  cmovz   edi, ebx
0x14008a47f  add     r14d, ebx
0x14008a482  cmp     r14d, ebx
0x14008a485  jl      short loc_14008A449
0x14008a487  test    dil, dil
0x14008a48a  jnz     loc_14008A386
0x14008a490  lea     rdx, aInstallExe; "install.exe"
0x14008a497  mov     rcx, rsi; pszStr1
0x14008a49a  call    cs:__imp_StrCmpICW
0x14008a4a1  nop     dword ptr [rax+rax+00h]
0x14008a4a6  test    eax, eax
0x14008a4a8  jz      loc_14008A386
0x14008a4ae  mov     bl, r12b
0x14008a4b1  jmp     loc_14008A386
```
