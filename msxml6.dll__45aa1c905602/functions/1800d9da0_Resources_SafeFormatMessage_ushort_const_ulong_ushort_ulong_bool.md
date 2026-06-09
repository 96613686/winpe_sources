# Resources::SafeFormatMessage(ushort const *,ulong,ushort *,ulong,bool)

- ea: `0x1800d9da0`
- end: `0x1800d9f1f`
- name: `?SafeFormatMessage@Resources@@KAKPEBGKPEAGK_N@Z`
- size: `383`
- prototype: `unsigned int __fastcall(const wchar_t *pszModule, unsigned int errorid, wchar_t *buffer, unsigned int fCheckBeforeLoad, bool pszModule)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800d9bbc`

## callees

- `0x1800c12f4`
- `0x1800cc6c0`
- `0x1800d9da0`
- `0x1800d9f28`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d9e8c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d9e8c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800d9e69`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800d9e69`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800d9eec`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800d9eec`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800d9ecc`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800d9ecc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800d9df3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800d9df3`

## pseudocode

```c
__int64 __fastcall Resources::SafeFormatMessage(
        const wchar_t *pszModule,
        DWORD errorid,
        wchar_t *buffer,
        unsigned int fCheckBeforeLoad,
        bool pszModule_0)
{
  DWORD v8; // edi
  HMODULE v9; // rbx
  DWORD v10; // r8d
  DWORD nSize; // [rsp+28h] [rbp-270h]
  unsigned __int64 cchRemaining; // [rsp+40h] [rbp-258h] BYREF
  unsigned int rc; // [rsp+48h] [rbp-250h]
  wchar_t *pszDestEnd; // [rsp+50h] [rbp-248h] BYREF
  wchar_t szModuleFullPath[264]; // [rsp+60h] [rbp-238h] BYREF

  pszDestEnd = 0;
  cchRemaining = 0;
  v8 = 0;
  rc = 0;
  szModuleFullPath[0] = 0;
  if ( GetSystemDirectoryW(szModuleFullPath, 0x104u) - 1 > 0x102
    || StringCchCatExW(szModuleFullPath, 0x104u, L"\\", &pszDestEnd, &cchRemaining, nSize) < 0
    || StringCchCopyW(pszDestEnd, cchRemaining, pszModule) < 0 )
  {
    return v8;
  }
  if ( pszModule_0 )
  {
    v9 = 0;
    cchRemaining = 0;
    if ( !GetModuleHandleW(szModuleFullPath) )
      goto LABEL_9;
    v10 = 0;
  }
  else
  {
    v10 = 2;
  }
  cchRemaining = (unsigned __int64)LoadLibraryExW(szModuleFullPath, 0, v10);
  v9 = (HMODULE)cchRemaining;
LABEL_9:
  if ( v9 )
  {
    v8 = FormatMessageW(0x800u, v9, errorid, 0x400u, buffer, 0x1000u, 0);
    rc = v8;
    FreeLibrary(v9);
  }
  return v8;
}

```

## disassembly

```asm
0x1800d9da0  mov     [rsp+arg_18], rbx
0x1800d9da5  push    rsi
0x1800d9da6  push    rdi
0x1800d9da7  push    r14
0x1800d9da9  sub     rsp, 280h
0x1800d9db0  mov     rax, cs:__security_cookie
0x1800d9db7  xor     rax, rsp
0x1800d9dba  mov     [rsp+298h+var_28], rax
0x1800d9dc2  mov     r14, buffer
0x1800d9dc5  mov     esi, errorid
0x1800d9dc7  mov     rbx, pszModule
0x1800d9dca  mov     [rsp+298h+pszDestEnd], 0
0x1800d9dd3  mov     [rsp+298h+cchRemaining], 0
0x1800d9ddc  xor     edi, edi
0x1800d9dde  mov     [rsp+298h+rc], edi
0x1800d9de2  xor     eax, eax
0x1800d9de4  mov     [rsp+298h+szModuleFullPath], ax
0x1800d9de9  mov     errorid, 104h; uSize
0x1800d9dee  lea     pszModule, [rsp+298h+szModuleFullPath]; lpBuffer
0x1800d9df3  call    cs:__imp_GetSystemDirectoryW
0x1800d9dfa  nop     dword ptr [rax+rax+00h]
0x1800d9dff  dec     eax
0x1800d9e01  cmp     eax, 102h
0x1800d9e06  ja      $exit_1
0x1800d9e0c  lea     rax, [rsp+298h+cchRemaining]
0x1800d9e11  mov     [rsp+298h+pcchRemaining], rax; pcchRemaining
0x1800d9e16  lea     r9, [rsp+298h+pszDestEnd]; ppszDestEnd
0x1800d9e1b  lea     buffer, asc_1801C88A0; "\\"
0x1800d9e22  mov     errorid, 104h; cchDest
0x1800d9e27  lea     pszModule, [rsp+298h+szModuleFullPath]; pszDest
0x1800d9e2c  call    ?StringCchCatExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCatExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800d9e31  test    eax, eax
0x1800d9e33  js      $exit_1
0x1800d9e39  mov     buffer, rbx; pszSrc
0x1800d9e3c  mov     rdx, [rsp+298h+cchRemaining]; cchDest
0x1800d9e41  mov     pszModule, [rsp+298h+pszDestEnd]; pszDest
0x1800d9e46  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800d9e4b  test    eax, eax
0x1800d9e4d  js      $exit_1
0x1800d9e53  lea     pszModule, [rsp+298h+szModuleFullPath]; lpLibFileName
0x1800d9e58  cmp     [rsp+298h+pszModule_0], dil
0x1800d9e60  jz      short loc_1800D9E84
0x1800d9e62  xor     ebx, ebx
0x1800d9e64  mov     [rsp+298h+cchRemaining], rbx
0x1800d9e69  call    cs:__imp_GetModuleHandleW
0x1800d9e70  nop     dword ptr [rax+rax+00h]
0x1800d9e75  test    rax, rax
0x1800d9e78  jz      short loc_1800D9EA0
0x1800d9e7a  xor     r8d, r8d
0x1800d9e7d  lea     pszModule, [rsp+298h+szModuleFullPath]
0x1800d9e82  jmp     short loc_1800D9E8A
0x1800d9e84  mov     r8d, 2; dwFlags
0x1800d9e8a  xor     errorid, errorid; hFile
0x1800d9e8c  call    cs:__imp_LoadLibraryExW
0x1800d9e93  nop     dword ptr [rax+rax+00h]
0x1800d9e98  mov     [rsp+298h+cchRemaining], rax
0x1800d9e9d  mov     rbx, rax
0x1800d9ea0  test    rbx, rbx
0x1800d9ea3  jz      short $exit_1
0x1800d9ea5  mov     [rsp+298h+Arguments], 0; Arguments
0x1800d9eae  mov     [rsp+298h+nSize], 1000h; nSize
0x1800d9eb6  mov     [rsp+298h+pcchRemaining], r14; lpBuffer
0x1800d9ebb  mov     r9d, 400h; dwLanguageId
0x1800d9ec1  mov     r8d, esi; dwMessageId
0x1800d9ec4  mov     rdx, rbx; lpSource
0x1800d9ec7  mov     ecx, 800h; dwFlags
0x1800d9ecc  call    cs:__imp_FormatMessageW
0x1800d9ed3  nop     dword ptr [rax+rax+00h]
0x1800d9ed8  mov     edi, eax
0x1800d9eda  mov     [rsp+298h+rc], eax
0x1800d9ede  jmp     short loc_1800D9EE9
0x1800d9ee0  mov     edi, [rsp+298h+rc]
0x1800d9ee4  mov     rbx, [rsp+298h+cchRemaining]
0x1800d9ee9  mov     pszModule, rbx; hLibModule
0x1800d9eec  call    cs:__imp_FreeLibrary
0x1800d9ef3  nop     dword ptr [rax+rax+00h]
0x1800d9ef8  mov     eax, edi
0x1800d9efa  mov     pszModule, [rsp+298h+var_28]
0x1800d9f02  xor     pszModule, rsp; StackCookie
0x1800d9f05  call    __security_check_cookie
0x1800d9f0a  mov     rbx, [rsp+298h+arg_18]
0x1800d9f12  add     rsp, 280h
0x1800d9f19  pop     r14
0x1800d9f1b  pop     rdi
0x1800d9f1c  pop     rsi
0x1800d9f1d  retn
```
