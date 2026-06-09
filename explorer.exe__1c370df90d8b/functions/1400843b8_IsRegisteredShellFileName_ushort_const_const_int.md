# IsRegisteredShellFileName(ushort const * const *,int)

- ea: `0x1400843b8`
- end: `0x1400845b3`
- name: `?IsRegisteredShellFileName@@YA_NPEBQEBGH@Z`
- size: `507`
- prototype: `bool __fastcall(const unsigned __int16 *const *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400b3194`

## callees

- `0x1400843b8`
- `0x1400845bc`
- `0x1401040e0`
- `0x14012c5f0`
- `0x14012c754`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14008459d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14008459d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x140084573`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x140084573`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140084494`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140084494`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x140084532`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x140084532`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksW` at `0x140084528`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksW` at `0x140084528`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x140084510`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x140084510`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!PathRemoveArgsW` at `0x14008451e`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!PathRemoveArgsW` at `0x14008451e`

## string_xrefs

- `0x140084593`: `install.exe`

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
0x1400843b8  mov     [rsp-8+arg_8], rbx
0x1400843bd  mov     [rsp-8+arg_10], rsi
0x1400843c2  push    rbp
0x1400843c3  push    rdi
0x1400843c4  push    r12
0x1400843c6  push    r14
0x1400843c8  push    r15
0x1400843ca  lea     rbp, [rsp-3B0h]
0x1400843d2  sub     rsp, 4B0h
0x1400843d9  mov     rax, cs:__security_cookie
0x1400843e0  xor     rax, rsp
0x1400843e3  mov     [rbp+3D0h+var_30], rax
0x1400843ea  xorps   xmm0, xmm0
0x1400843ed  lea     r8, [rsp+4D0h+hKey]
0x1400843f2  movups  xmmword ptr [rsp+4D0h+hKey], xmm0
0x1400843f7  mov     r15, rcx
0x1400843fa  call    RegValChoice_Open
0x1400843ff  xor     r12d, r12d
0x140084402  test    eax, eax
0x140084404  jz      loc_1400844D5
0x14008440a  lea     rax, [rsp+4D0h+var_46C+4]
0x14008440f  mov     dword ptr [rsp+4D0h+var_46C+4], r12d
0x140084414  mov     [rsp+4D0h+var_480], rax; __int64
0x140084419  lea     rax, [rsp+4D0h+var_46C]
0x14008441e  mov     [rsp+4D0h+var_488], rax; __int64
0x140084423  lea     rax, [rbp+3D0h+var_240]
0x14008442a  mov     [rsp+4D0h+var_490], rax; LPBYTE
0x14008442f  lea     rax, [rbp+3D0h+pszPath]
0x140084433  mov     [rsp+4D0h+lpData], rax; lpData
0x140084438  lea     rax, [rsp+4D0h+Type]
0x14008443d  mov     [rsp+4D0h+pcbData], rax; lpType
0x140084442  mov     dword ptr [rsp+4D0h+var_46C], 208h
0x14008444a  mov     [rsp+4D0h+Type], r12d
0x14008444f  call    RegValChoice_GetAndCompareRegValues
0x140084454  mov     ebx, eax
0x140084456  test    eax, eax
0x140084458  jnz     short loc_140084488
0x14008445a  cmp     dword ptr [rsp+4D0h+var_46C+4], r12d
0x14008445f  jz      short loc_140084488
0x140084461  lea     r9, [rsp+4D0h+var_46C]
0x140084466  mov     dword ptr [rsp+4D0h+var_46C], 208h
0x14008446e  lea     r8, [rbp+3D0h+pszPath]
0x140084472  mov     [rsp+4D0h+Type], r12d
0x140084477  lea     rdx, [rsp+4D0h+Type]
0x14008447c  lea     rcx, [rsp+4D0h+hKey]
0x140084481  call    RegValChoice_GetHighestValue
0x140084486  mov     ebx, eax
0x140084488  cmp     dword ptr [rsp+4D0h+hKey], r12d
0x14008448d  jz      short loc_14008449F
0x14008448f  mov     rcx, [rsp+4D0h+hKey+8]; hKey
0x140084494  call    cs:__imp_RegCloseKey
0x14008449a  mov     dword ptr [rsp+4D0h+hKey], r12d
0x14008449f  test    ebx, ebx
0x1400844a1  jz      short loc_14008451A
0x1400844a3  mov     ebx, 1
0x1400844a8  mov     al, bl
0x1400844aa  mov     rcx, [rbp+3D0h+var_30]
0x1400844b1  xor     rcx, rsp; StackCookie
0x1400844b4  call    __security_check_cookie
0x1400844b9  lea     r11, [rsp+4D0h+var_20]
0x1400844c1  mov     rbx, [r11+38h]
0x1400844c5  mov     rsi, [r11+40h]
0x1400844c9  mov     rsp, r11
0x1400844cc  pop     r15
0x1400844ce  pop     r14
0x1400844d0  pop     r12
0x1400844d2  pop     rdi
0x1400844d3  pop     rbp
0x1400844d4  retn
0x1400844d5  lea     rax, [rsp+4D0h+Type]
0x1400844da  mov     [rsp+4D0h+Type], 208h
0x1400844e2  mov     [rsp+4D0h+pcbData], rax; pcbData
0x1400844e7  lea     r8, aShell; "Shell"
0x1400844ee  lea     rax, [rbp+3D0h+pszPath]
0x1400844f2  mov     r9d, 2; srrfFlags
0x1400844f8  mov     [rsp+4D0h+pvData], rax; pvData
0x1400844fd  lea     rdx, aSoftwareMicros_142; "Software\\Microsoft\\Windows NT\\Curren"...
0x140084504  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14008450b  mov     [rsp+4D0h+pdwType], r12; pdwType
0x140084510  call    cs:__imp_SHRegGetValueW
0x140084516  test    eax, eax
0x140084518  jnz     short loc_1400844A3
0x14008451a  lea     rcx, [rbp+3D0h+pszPath]; pszPath
0x14008451e  call    cs:__imp_PathRemoveArgsW
0x140084524  lea     rcx, [rbp+3D0h+pszPath]; pszPath
0x140084528  call    cs:__imp_PathRemoveBlanksW
0x14008452e  lea     rcx, [rbp+3D0h+pszPath]; pszPath
0x140084532  call    cs:__imp_PathFindFileNameW
0x140084538  lea     rsi, aExplorerExe_0; "explorer.exe"
0x14008453f  mov     dil, r12b
0x140084542  mov     r14d, r12d
0x140084545  mov     ebx, 1
0x14008454a  cmp     [rax], r12w
0x14008454e  cmovnz  rsi, rax
0x140084552  test    dil, dil
0x140084555  jnz     loc_1400844A8
0x14008455b  mov     eax, r14d
0x14008455e  or      r8, 0FFFFFFFFFFFFFFFFh
0x140084562  mov     rdx, [r15+rax*8]; psz2
0x140084566  inc     r8; nChar
0x140084569  cmp     [rdx+r8*2], r12w
0x14008456e  jnz     short loc_140084566
0x140084570  mov     rcx, rsi; psz1
0x140084573  call    cs:__imp_StrCmpNIW
0x140084579  test    eax, eax
0x14008457b  movzx   edi, dil
0x14008457f  cmovz   edi, ebx
0x140084582  add     r14d, ebx
0x140084585  cmp     r14d, ebx
0x140084588  jl      short loc_140084552
0x14008458a  test    dil, dil
0x14008458d  jnz     loc_1400844A8
0x140084593  lea     rdx, aInstallExe; "install.exe"
0x14008459a  mov     rcx, rsi; pszStr1
0x14008459d  call    cs:__imp_StrCmpICW
0x1400845a3  test    eax, eax
0x1400845a5  jz      loc_1400844A8
0x1400845ab  mov     bl, r12b
0x1400845ae  jmp     loc_1400844A8
```
