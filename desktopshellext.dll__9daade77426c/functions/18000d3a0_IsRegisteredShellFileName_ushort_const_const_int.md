# IsRegisteredShellFileName(ushort const * const *,int)

- ea: `0x18000d3a0`
- end: `0x18000d5c7`
- name: `?IsRegisteredShellFileName@@YA_NPEBQEBGH@Z`
- size: `551`
- prototype: `bool __fastcall(const unsigned __int16 *const *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800187dc`
- `0x1800236bc`

## callees

- `0x18000d3a0`
- `0x18002a3d0`
- `0x18007fbd0`
- `0x18007fd34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d5b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d5b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d3fb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d3fb`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksW` at `0x18000d479`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksW` at `0x18000d479`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18000d483`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18000d483`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!PathRemoveArgsW` at `0x18000d46f`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!PathRemoveArgsW` at `0x18000d46f`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x18000d44c`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x18000d44c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18000d4de`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18000d4de`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18000d4a9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18000d4a9`

## string_xrefs

- `0x18000d49f`: `install.exe`

## pseudocode

```c
char __fastcall IsRegisteredShellFileName(const unsigned __int16 *const *a1, int a2)
{
  int v4; // edx
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  int v8; // edi
  LPWSTR FileNameW; // rax
  const WCHAR *v11; // r14
  char v12; // bl
  __int64 v13; // r8
  const WCHAR *v14; // rdx
  int HighestValue; // ebx
  int phkResult; // [rsp+20h] [rbp-E0h]
  DWORD pvData; // [rsp+28h] [rbp-D8h]
  DWORD Type; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v19; // [rsp+64h] [rbp-9Ch] BYREF
  __int128 v20; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszPath[264]; // [rsp+80h] [rbp-80h] BYREF
  BYTE v22[528]; // [rsp+290h] [rbp+190h] BYREF

  v20 = 0;
  v8 = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\AlternateShells\\AvailableShells",
         0,
         0x20019u,
         (PHKEY)&v20 + 1) )
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
  else
  {
    LODWORD(v20) = 1;
    v19 = 520;
    Type = 0;
    HighestValue = RegValChoice_GetAndCompareRegValues(
                     v5,
                     v4,
                     v6,
                     v7,
                     phkResult,
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
      HighestValue = RegValChoice_GetHighestValue(&v20, &Type, pszPath, &v19);
    }
    if ( (_DWORD)v20 )
    {
      RegCloseKey(*((HKEY *)&v20 + 1));
      LODWORD(v20) = 0;
    }
    if ( HighestValue )
      return 1;
  }
  PathRemoveArgsW(pszPath);
  PathRemoveBlanksW(pszPath);
  FileNameW = PathFindFileNameW(pszPath);
  v11 = L"explorer.exe";
  if ( *FileNameW )
    v11 = FileNameW;
  v12 = 0;
  if ( a2 > 0 )
  {
    while ( !v12 )
    {
      v13 = -1;
      v14 = a1[v8];
      do
        ++v13;
      while ( v14[v13] );
      if ( !StrCmpNIW(v11, v14, v13) )
        v12 = 1;
      if ( ++v8 >= a2 )
      {
        if ( !v12 )
          goto LABEL_8;
        return 1;
      }
    }
  }
  else
  {
LABEL_8:
    if ( StrCmpICW(v11, L"install.exe") )
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18000d3a0  mov     [rsp-8+arg_10], rbx
0x18000d3a5  push    rbp
0x18000d3a6  push    rsi
0x18000d3a7  push    rdi
0x18000d3a8  push    r12
0x18000d3aa  push    r15
0x18000d3ac  lea     rbp, [rsp-3B0h]
0x18000d3b4  sub     rsp, 4B0h
0x18000d3bb  mov     rax, cs:__security_cookie
0x18000d3c2  xor     rax, rsp
0x18000d3c5  mov     [rbp+3D0h+var_30], rax
0x18000d3cc  mov     r15d, edx
0x18000d3cf  lea     rax, [rsp+4D0h+hKey]
0x18000d3d4  mov     rsi, rcx
0x18000d3d7  mov     [rsp+4D0h+phkResult], rax; int
0x18000d3dc  xorps   xmm0, xmm0
0x18000d3df  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows NT\\Curren"...
0x18000d3e6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d3ed  mov     r9d, 20019h; samDesired
0x18000d3f3  xor     r8d, r8d; ulOptions
0x18000d3f6  movups  xmmword ptr [rsp+70h], xmm0
0x18000d3fb  call    cs:__imp_RegOpenKeyExW
0x18000d401  xor     edi, edi
0x18000d403  mov     r12d, 1
0x18000d409  test    eax, eax
0x18000d40b  jz      loc_18000D52A
0x18000d411  lea     rax, [rsp+4D0h+Type]
0x18000d416  mov     [rsp+4D0h+Type], 208h
0x18000d41e  mov     [rsp+4D0h+pcbData], rax; pcbData
0x18000d423  lea     r8, pszValue; "Shell"
0x18000d42a  lea     rax, [rbp+3D0h+pszPath]
0x18000d42e  mov     r9d, 2; srrfFlags
0x18000d434  mov     [rsp+4D0h+pvData], rax; pvData
0x18000d439  lea     rdx, pszSubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x18000d440  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000d447  mov     [rsp+4D0h+phkResult], rdi; pdwType
0x18000d44c  call    cs:__imp_SHRegGetValueW
0x18000d452  test    eax, eax
0x18000d454  jz      short loc_18000D463
0x18000d456  movzx   eax, r12b
0x18000d45a  jmp     loc_18000D504
0x18000d45f  test    ebx, ebx
0x18000d461  jnz     short loc_18000D456
0x18000d463  lea     rcx, [rbp+3D0h+pszPath]; pszPath
0x18000d467  mov     [rsp+4D0h+arg_8], r14
0x18000d46f  call    cs:__imp_PathRemoveArgsW
0x18000d475  lea     rcx, [rbp+3D0h+pszPath]; pszPath
0x18000d479  call    cs:__imp_PathRemoveBlanksW
0x18000d47f  lea     rcx, [rbp+3D0h+pszPath]; pszPath
0x18000d483  call    cs:__imp_PathFindFileNameW
0x18000d489  lea     r14, aExplorerExe; "explorer.exe"
0x18000d490  cmp     word ptr [rax], 0
0x18000d494  cmovnz  r14, rax
0x18000d498  xor     bl, bl
0x18000d49a  test    r15d, r15d
0x18000d49d  jg      short loc_18000D4B7
0x18000d49f  lea     rdx, pszStr2; "install.exe"
0x18000d4a6  mov     rcx, r14; pszStr1
0x18000d4a9  call    cs:__imp_StrCmpICW
0x18000d4af  test    eax, eax
0x18000d4b1  jz      short loc_18000D4F8
0x18000d4b3  xor     al, al
0x18000d4b5  jmp     short loc_18000D4FC
0x18000d4b7  test    bl, bl
0x18000d4b9  jnz     short loc_18000D4F8
0x18000d4bb  mov     eax, edi
0x18000d4bd  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000d4c4  mov     rdx, [rsi+rax*8]; psz2
0x18000d4c8  nop     dword ptr [rax+rax+00000000h]
0x18000d4d0  inc     r8; nChar
0x18000d4d3  cmp     word ptr [rdx+r8*2], 0
0x18000d4d9  jnz     short loc_18000D4D0
0x18000d4db  mov     rcx, r14; psz1
0x18000d4de  call    cs:__imp_StrCmpNIW
0x18000d4e4  test    eax, eax
0x18000d4e6  movzx   ebx, bl
0x18000d4e9  cmovz   ebx, r12d
0x18000d4ed  inc     edi
0x18000d4ef  cmp     edi, r15d
0x18000d4f2  jl      short loc_18000D4B7
0x18000d4f4  test    bl, bl
0x18000d4f6  jz      short loc_18000D49F
0x18000d4f8  movzx   eax, r12b
0x18000d4fc  mov     r14, [rsp+4D0h+arg_8]
0x18000d504  mov     rcx, [rbp+3D0h+var_30]
0x18000d50b  xor     rcx, rsp; StackCookie
0x18000d50e  call    __security_check_cookie
0x18000d513  mov     rbx, [rsp+4D0h+arg_10]
0x18000d51b  add     rsp, 4B0h
0x18000d522  pop     r15
0x18000d524  pop     r12
0x18000d526  pop     rdi
0x18000d527  pop     rsi
0x18000d528  pop     rbp
0x18000d529  retn
0x18000d52a  lea     rax, [rsp+4D0h+var_46C+4]
0x18000d52f  mov     [rsp+4D0h+var_460], r12d
0x18000d534  mov     [rsp+4D0h+var_480], rax; __int64
0x18000d539  lea     rax, [rsp+4D0h+var_46C]
0x18000d53e  mov     [rsp+4D0h+var_488], rax; __int64
0x18000d543  lea     rax, [rbp+3D0h+var_240]
0x18000d54a  mov     [rsp+4D0h+var_490], rax; LPBYTE
0x18000d54f  lea     rax, [rbp+3D0h+pszPath]
0x18000d553  mov     [rsp+4D0h+lpData], rax; lpData
0x18000d558  lea     rax, [rsp+4D0h+Type]
0x18000d55d  mov     [rsp+4D0h+pcbData], rax; lpType
0x18000d562  mov     dword ptr [rsp+4D0h+var_46C+4], edi
0x18000d566  mov     dword ptr [rsp+4D0h+var_46C], 208h
0x18000d56e  mov     [rsp+4D0h+Type], edi
0x18000d572  call    RegValChoice_GetAndCompareRegValues
0x18000d577  mov     ebx, eax
0x18000d579  test    eax, eax
0x18000d57b  jnz     short loc_18000D5A9
0x18000d57d  cmp     dword ptr [rsp+4D0h+var_46C+4], edi
0x18000d581  jz      short loc_18000D5A9
0x18000d583  lea     r9, [rsp+4D0h+var_46C]
0x18000d588  mov     dword ptr [rsp+4D0h+var_46C], 208h
0x18000d590  lea     r8, [rbp+3D0h+pszPath]
0x18000d594  mov     [rsp+4D0h+Type], edi
0x18000d598  lea     rdx, [rsp+4D0h+Type]
0x18000d59d  lea     rcx, [rsp+4D0h+var_460]
0x18000d5a2  call    RegValChoice_GetHighestValue
0x18000d5a7  mov     ebx, eax
0x18000d5a9  cmp     [rsp+4D0h+var_460], edi
0x18000d5ad  jz      loc_18000D45F
0x18000d5b3  mov     rcx, [rsp+4D0h+hKey]; hKey
0x18000d5b8  call    cs:__imp_RegCloseKey
0x18000d5be  mov     [rsp+4D0h+var_460], edi
0x18000d5c2  jmp     loc_18000D45F
```
