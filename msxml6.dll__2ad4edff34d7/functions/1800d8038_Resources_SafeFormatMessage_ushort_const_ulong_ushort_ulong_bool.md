# Resources::SafeFormatMessage(ushort const *,ulong,ushort *,ulong,bool)

- ea: `0x1800d8038`
- end: `0x1800d8198`
- name: `?SafeFormatMessage@Resources@@KAKPEBGKPEAGK_N@Z`
- size: `352`
- prototype: `unsigned int __fastcall(const wchar_t *pszModule, unsigned int errorid, wchar_t *buffer, unsigned int fCheckBeforeLoad, bool pszModule)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800d7e5c`

## callees

- `0x1800bfc70`
- `0x1800cada0`
- `0x1800d8038`
- `0x1800d81a0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d8118`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d8118`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800d80fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800d80fb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800d816c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800d816c`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800d8152`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800d8152`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800d808b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800d808b`

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
0x1800d8038  mov     [rsp+arg_18], rbx
0x1800d803d  push    rsi
0x1800d803e  push    rdi
0x1800d803f  push    r14
0x1800d8041  sub     rsp, 280h
0x1800d8048  mov     rax, cs:__security_cookie
0x1800d804f  xor     rax, rsp
0x1800d8052  mov     [rsp+298h+var_28], rax
0x1800d805a  mov     r14, buffer
0x1800d805d  mov     esi, errorid
0x1800d805f  mov     rbx, pszModule
0x1800d8062  mov     [rsp+298h+pszDestEnd], 0
0x1800d806b  mov     [rsp+298h+cchRemaining], 0
0x1800d8074  xor     edi, edi
0x1800d8076  mov     [rsp+298h+rc], edi
0x1800d807a  xor     eax, eax
0x1800d807c  mov     [rsp+298h+szModuleFullPath], ax
0x1800d8081  mov     errorid, 104h; uSize
0x1800d8086  lea     pszModule, [rsp+298h+szModuleFullPath]; lpBuffer
0x1800d808b  call    cs:__imp_GetSystemDirectoryW
0x1800d8091  dec     eax
0x1800d8093  cmp     eax, 102h
0x1800d8098  ja      $exit_1
0x1800d809e  lea     rax, [rsp+298h+cchRemaining]
0x1800d80a3  mov     [rsp+298h+pcchRemaining], rax; pcchRemaining
0x1800d80a8  lea     r9, [rsp+298h+pszDestEnd]; ppszDestEnd
0x1800d80ad  lea     buffer, asc_1801C48A0; "\\"
0x1800d80b4  mov     errorid, 104h; cchDest
0x1800d80b9  lea     pszModule, [rsp+298h+szModuleFullPath]; pszDest
0x1800d80be  call    ?StringCchCatExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCatExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800d80c3  test    eax, eax
0x1800d80c5  js      $exit_1
0x1800d80cb  mov     buffer, rbx; pszSrc
0x1800d80ce  mov     rdx, [rsp+298h+cchRemaining]; cchDest
0x1800d80d3  mov     pszModule, [rsp+298h+pszDestEnd]; pszDest
0x1800d80d8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800d80dd  test    eax, eax
0x1800d80df  js      $exit_1
0x1800d80e5  lea     pszModule, [rsp+298h+szModuleFullPath]; lpLibFileName
0x1800d80ea  cmp     [rsp+298h+pszModule_0], dil
0x1800d80f2  jz      short loc_1800D8110
0x1800d80f4  xor     ebx, ebx
0x1800d80f6  mov     [rsp+298h+cchRemaining], rbx
0x1800d80fb  call    cs:__imp_GetModuleHandleW
0x1800d8101  test    rax, rax
0x1800d8104  jz      short loc_1800D8126
0x1800d8106  xor     r8d, r8d
0x1800d8109  lea     pszModule, [rsp+298h+szModuleFullPath]
0x1800d810e  jmp     short loc_1800D8116
0x1800d8110  mov     r8d, 2; dwFlags
0x1800d8116  xor     errorid, errorid; hFile
0x1800d8118  call    cs:__imp_LoadLibraryExW
0x1800d811e  mov     [rsp+298h+cchRemaining], rax
0x1800d8123  mov     rbx, rax
0x1800d8126  test    rbx, rbx
0x1800d8129  jz      short $exit_1
0x1800d812b  mov     [rsp+298h+Arguments], 0; Arguments
0x1800d8134  mov     [rsp+298h+nSize], 1000h; nSize
0x1800d813c  mov     [rsp+298h+pcchRemaining], r14; lpBuffer
0x1800d8141  mov     r9d, 400h; dwLanguageId
0x1800d8147  mov     r8d, esi; dwMessageId
0x1800d814a  mov     rdx, rbx; lpSource
0x1800d814d  mov     ecx, 800h; dwFlags
0x1800d8152  call    cs:__imp_FormatMessageW
0x1800d8158  mov     edi, eax
0x1800d815a  mov     [rsp+298h+rc], eax
0x1800d815e  jmp     short loc_1800D8169
0x1800d8160  mov     edi, [rsp+298h+rc]
0x1800d8164  mov     rbx, [rsp+298h+cchRemaining]
0x1800d8169  mov     pszModule, rbx; hLibModule
0x1800d816c  call    cs:__imp_FreeLibrary
0x1800d8172  mov     eax, edi
0x1800d8174  mov     pszModule, [rsp+298h+var_28]
0x1800d817c  xor     pszModule, rsp; StackCookie
0x1800d817f  call    __security_check_cookie
0x1800d8184  mov     rbx, [rsp+298h+arg_18]
0x1800d818c  add     rsp, 280h
0x1800d8193  pop     r14
0x1800d8195  pop     rdi
0x1800d8196  pop     rsi
0x1800d8197  retn
```
