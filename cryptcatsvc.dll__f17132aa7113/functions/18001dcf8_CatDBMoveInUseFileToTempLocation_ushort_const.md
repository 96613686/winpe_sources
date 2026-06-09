# _CatDBMoveInUseFileToTempLocation(ushort const *)

- ea: `0x18001dcf8`
- end: `0x18001dea5`
- name: `?_CatDBMoveInUseFileToTempLocation@@YAHPEBG@Z`
- size: `429`
- prototype: `__int64 __fastcall(LPCWSTR lpExistingFileName)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180017a04`
- `0x180019314`

## callees

- `0x18000a59c`
- `0x18000be40`
- `0x18001dcf8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001dd63`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001dd63`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18001dd4c`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18001dd4c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001de69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001de79`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001de69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001de79`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001ddd2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001de5a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001ddd2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001de5a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18001dd71`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18001dd71`

## string_xrefs

- `0x18001dda1`: `Software\Microsoft\Cryptography\CatDBTempFiles`

## pseudocode

```c
__int64 __fastcall _CatDBMoveInUseFileToTempLocation(LPCWSTR lpExistingFileName)
{
  unsigned int v2; // edx
  unsigned __int16 *v3; // rcx
  unsigned int v4; // r8d
  unsigned int v5; // ebx
  __int64 v6; // rax
  unsigned int v7; // edx
  unsigned __int64 v8; // rcx
  REGSAM samDesired; // [rsp+28h] [rbp-D8h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition[4]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR TempFileName[264]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  phkResult = 0;
  dwDisposition[0] = 0;
  if ( !GetTempFileNameW(g_pwszCatalogFileBaseDirectory, L"TMP", 0, TempFileName) )
  {
    v4 = 1332;
LABEL_5:
    ErrLog_LogError(v3, v2, v4, 0, 0, samDesired);
    v5 = 0;
    goto LABEL_17;
  }
  DeleteFileW(TempFileName);
  if ( !MoveFileW(lpExistingFileName, TempFileName) )
  {
    v4 = 1347;
    goto LABEL_5;
  }
  v5 = 1;
  if ( !RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Cryptography\\CatDBTempFiles",
          0,
          0,
          0,
          0x2001Fu,
          0,
          &hKey,
          dwDisposition) )
  {
    v6 = -1;
    v7 = 0;
    do
      ++v6;
    while ( TempFileName[v6] );
    if ( v6 )
    {
      do
      {
        if ( TempFileName[v7] == 92 )
          TempFileName[v7] = 42;
        ++v7;
        v8 = -1;
        do
          ++v8;
        while ( TempFileName[v8] );
      }
      while ( v7 < v8 );
    }
    if ( !RegCreateKeyExW(hKey, TempFileName, 0, 0, 0, 0x2000000u, 0, &phkResult, 0) )
      RegCloseKey(phkResult);
  }
LABEL_17:
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x18001dcf8  mov     [rsp-8+arg_8], rbx
0x18001dcfd  mov     [rsp-8+arg_10], rdi
0x18001dd02  push    rbp
0x18001dd03  lea     rbp, [rsp-190h]
0x18001dd0b  sub     rsp, 290h
0x18001dd12  mov     rax, cs:__security_cookie
0x18001dd19  xor     rax, rsp
0x18001dd1c  mov     [rbp+190h+var_10], rax
0x18001dd23  xor     edi, edi
0x18001dd25  lea     r9, [rsp+290h+TempFileName]; lpTempFileName
0x18001dd2a  mov     rbx, rcx
0x18001dd2d  mov     [rsp+290h+hKey], rdi
0x18001dd32  mov     rcx, cs:?g_pwszCatalogFileBaseDirectory@@3PEAGEA; lpPathName
0x18001dd39  lea     rdx, PrefixString; "TMP"
0x18001dd40  xor     r8d, r8d; uUnique
0x18001dd43  mov     [rsp+290h+var_238], rdi
0x18001dd48  mov     [rsp+290h+dwDisposition], edi
0x18001dd4c  call    cs:__imp_GetTempFileNameW
0x18001dd52  test    eax, eax
0x18001dd54  jnz     short loc_18001DD5E
0x18001dd56  mov     r8d, 534h
0x18001dd5c  jmp     short loc_18001DD81
0x18001dd5e  lea     rcx, [rsp+290h+TempFileName]; lpFileName
0x18001dd63  call    cs:__imp_DeleteFileW
0x18001dd69  lea     rdx, [rsp+290h+TempFileName]; lpNewFileName
0x18001dd6e  mov     rcx, rbx; lpExistingFileName
0x18001dd71  call    cs:__imp_MoveFileW
0x18001dd77  test    eax, eax
0x18001dd79  jnz     short loc_18001DD94
0x18001dd7b  mov     r8d, 543h; unsigned int
0x18001dd81  xor     r9d, r9d; unsigned int
0x18001dd84  mov     [rsp+290h+dwOptions], edi; int
0x18001dd88  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001dd8d  mov     ebx, edi
0x18001dd8f  jmp     loc_18001DE6F
0x18001dd94  lea     rax, [rsp+290h+dwDisposition]
0x18001dd99  xor     r9d, r9d; lpClass
0x18001dd9c  mov     [rsp+290h+lpdwDisposition], rax; lpdwDisposition
0x18001dda1  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Cryptography\\CatD"...
0x18001dda8  lea     rax, [rsp+290h+hKey]
0x18001ddad  xor     r8d, r8d; Reserved
0x18001ddb0  mov     [rsp+290h+phkResult], rax; phkResult
0x18001ddb5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001ddbc  mov     [rsp+290h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18001ddc1  mov     ebx, 1
0x18001ddc6  mov     [rsp+290h+samDesired], 2001Fh; samDesired
0x18001ddce  mov     [rsp+290h+dwOptions], edi; dwOptions
0x18001ddd2  call    cs:__imp_RegCreateKeyExW
0x18001ddd8  test    eax, eax
0x18001ddda  jnz     loc_18001DE6F
0x18001dde0  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001dde4  lea     rcx, [rsp+290h+TempFileName]
0x18001dde9  mov     rax, r8
0x18001ddec  mov     edx, edi
0x18001ddee  inc     rax
0x18001ddf1  cmp     [rcx+rax*2], di
0x18001ddf5  jnz     short loc_18001DDEE
0x18001ddf7  test    rax, rax
0x18001ddfa  jz      short loc_18001DE2A
0x18001ddfc  mov     eax, edx
0x18001ddfe  cmp     [rsp+rax*2+290h+TempFileName], 5Ch ; '\'
0x18001de04  jnz     short loc_18001DE10
0x18001de06  mov     ecx, 2Ah ; '*'
0x18001de0b  mov     [rsp+rax*2+290h+TempFileName], cx
0x18001de10  add     edx, ebx
0x18001de12  lea     rax, [rsp+290h+TempFileName]
0x18001de17  mov     rcx, r8
0x18001de1a  inc     rcx
0x18001de1d  cmp     [rax+rcx*2], di
0x18001de21  jnz     short loc_18001DE1A
0x18001de23  mov     eax, edx
0x18001de25  cmp     rax, rcx
0x18001de28  jb      short loc_18001DDFC
0x18001de2a  mov     rcx, [rsp+290h+hKey]; hKey
0x18001de2f  lea     rax, [rsp+290h+var_238]
0x18001de34  mov     [rsp+290h+lpdwDisposition], rdi; lpdwDisposition
0x18001de39  lea     rdx, [rsp+290h+TempFileName]; lpSubKey
0x18001de3e  mov     [rsp+290h+phkResult], rax; phkResult
0x18001de43  xor     r9d, r9d; lpClass
0x18001de46  mov     [rsp+290h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18001de4b  xor     r8d, r8d; Reserved
0x18001de4e  mov     [rsp+290h+samDesired], 2000000h; samDesired
0x18001de56  mov     [rsp+290h+dwOptions], edi; dwOptions
0x18001de5a  call    cs:__imp_RegCreateKeyExW
0x18001de60  test    eax, eax
0x18001de62  jnz     short loc_18001DE6F
0x18001de64  mov     rcx, [rsp+290h+var_238]; hKey
0x18001de69  call    cs:__imp_RegCloseKey
0x18001de6f  mov     rcx, [rsp+290h+hKey]; hKey
0x18001de74  test    rcx, rcx
0x18001de77  jz      short loc_18001DE7F
0x18001de79  call    cs:__imp_RegCloseKey
0x18001de7f  mov     eax, ebx
0x18001de81  mov     rcx, [rbp+190h+var_10]
0x18001de88  xor     rcx, rsp; StackCookie
0x18001de8b  call    __security_check_cookie
0x18001de90  lea     r11, [rsp+290h+var_s0]
0x18001de98  mov     rbx, [r11+18h]
0x18001de9c  mov     rdi, [r11+20h]
0x18001dea0  mov     rsp, r11
0x18001dea3  pop     rbp
0x18001dea4  retn
```
