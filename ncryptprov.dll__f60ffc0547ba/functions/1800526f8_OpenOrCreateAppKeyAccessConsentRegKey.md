# OpenOrCreateAppKeyAccessConsentRegKey

- ea: `0x1800526f8`
- end: `0x180052836`
- name: `OpenOrCreateAppKeyAccessConsentRegKey`
- size: `318`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180050eb8`
- `0x180052480`

## callees

- `0x18000af80`
- `0x180038970`
- `0x1800517bc`
- `0x1800526f8`
- `0x180062310`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800527d1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800527d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052804`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052804`

## string_xrefs

- `0x180052780`: `onecore\ds\security\cryptoapi\ncrypt\storage\appcontainer.c`
- `0x18005273f`: `%s\Software\Classes\Local Settings\Software\Microsoft\Windows\CurrentVersion\AppContainer\Mappings\%s\Broker\%s`

## pseudocode

```c
__int64 __fastcall OpenOrCreateAppKeyAccessConsentRegKey(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  unsigned int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rcx
  LSTATUS v12; // eax
  DWORD dwDisposition; // [rsp+50h] [rbp-658h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-650h] BYREF
  wchar_t pszDest[784]; // [rsp+60h] [rbp-648h] BYREF

  memset_0(pszDest, 0, 0x618u);
  dwDisposition = 0;
  hKey = 0;
  v8 = StringCbPrintfW(
         pszDest,
         0x618u,
         L"%s\\Software\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppContainer\\Mappings\\%s\\Broker\\%s",
         a1,
         a2,
         a3);
  v9 = v8;
  if ( v8 )
  {
    v10 = 172;
    v11 = v8;
LABEL_3:
    DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\appcontainer.c", v10);
    goto LABEL_10;
  }
  if ( a4 )
  {
    v12 = RegCreateKeyExW(HKEY_USERS, pszDest, 0, 0, 0, 0x3001Fu, 0, &hKey, &dwDisposition);
    v9 = v12;
    if ( v12 )
    {
      if ( v12 > 0 )
        v9 = (unsigned __int16)v12 | 0x80070000;
      v10 = 199;
      v11 = v9;
      goto LABEL_3;
    }
  }
  v9 = 0;
LABEL_10:
  if ( hKey )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x1800526f8  mov     [rsp+arg_18], rbx
0x1800526fd  push    rbp
0x1800526fe  push    rsi
0x1800526ff  push    rdi
0x180052700  sub     rsp, 690h
0x180052707  mov     rax, cs:__security_cookie
0x18005270e  xor     rax, rsp
0x180052711  mov     [rsp+6A8h+var_28], rax
0x180052719  mov     rsi, r8
0x18005271c  mov     rdi, rdx
0x18005271f  mov     rbx, rcx
0x180052722  xor     edx, edx; Val
0x180052724  mov     r8d, 618h; Size
0x18005272a  lea     rcx, [rsp+6A8h+pszDest]; void *
0x18005272f  mov     ebp, r9d
0x180052732  call    memset_0
0x180052737  mov     r9, rbx
0x18005273a  mov     qword ptr [rsp+6A8h+samDesired], rsi
0x18005273f  lea     r8, aSSoftwareClass; "%s\\Software\\Classes\\Local Settings\\"...
0x180052746  mov     [rsp+6A8h+dwDisposition], 0
0x18005274e  mov     edx, 618h; cbDest
0x180052753  mov     [rsp+6A8h+hKey], 0
0x18005275c  lea     rcx, [rsp+6A8h+pszDest]; pszDest
0x180052761  mov     qword ptr [rsp+6A8h+dwOptions], rdi
0x180052766  call    StringCbPrintfW
0x18005276b  mov     ebx, eax
0x18005276d  test    eax, eax
0x18005276f  jz      short loc_18005278E
0x180052771  mov     r9d, 0ACh
0x180052777  mov     ecx, eax
0x180052779  lea     rdx, aStatus; "Status"
0x180052780  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180052787  call    DebugTraceError
0x18005278c  jmp     short loc_1800527FA
0x18005278e  test    ebp, ebp
0x180052790  jz      short loc_1800527F8
0x180052792  lea     rax, [rsp+6A8h+dwDisposition]
0x180052797  xor     r9d, r9d; lpClass
0x18005279a  mov     [rsp+6A8h+lpdwDisposition], rax; lpdwDisposition
0x18005279f  lea     rdx, [rsp+6A8h+pszDest]; lpSubKey
0x1800527a4  lea     rax, [rsp+6A8h+hKey]
0x1800527a9  xor     r8d, r8d; Reserved
0x1800527ac  mov     [rsp+6A8h+phkResult], rax; phkResult
0x1800527b1  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800527b8  mov     [rsp+6A8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800527c1  mov     [rsp+6A8h+samDesired], 3001Fh; samDesired
0x1800527c9  mov     [rsp+6A8h+dwOptions], 0; dwOptions
0x1800527d1  call    cs:__imp_RegCreateKeyExW
0x1800527d8  nop     dword ptr [rax+rax+00h]
0x1800527dd  mov     ebx, eax
0x1800527df  test    eax, eax
0x1800527e1  jz      short loc_1800527F8
0x1800527e3  jle     short loc_1800527EE
0x1800527e5  movzx   ebx, ax
0x1800527e8  or      ebx, 80070000h
0x1800527ee  mov     r9d, 0C7h
0x1800527f4  mov     ecx, ebx
0x1800527f6  jmp     short loc_180052779
0x1800527f8  xor     ebx, ebx
0x1800527fa  mov     rcx, [rsp+6A8h+hKey]; hKey
0x1800527ff  test    rcx, rcx
0x180052802  jz      short loc_180052810
0x180052804  call    cs:__imp_RegCloseKey
0x18005280b  nop     dword ptr [rax+rax+00h]
0x180052810  mov     eax, ebx
0x180052812  mov     rcx, [rsp+6A8h+var_28]
0x18005281a  xor     rcx, rsp; StackCookie
0x18005281d  call    __security_check_cookie
0x180052822  mov     rbx, [rsp+6A8h+arg_18]
0x18005282a  add     rsp, 690h
0x180052831  pop     rdi
0x180052832  pop     rsi
0x180052833  pop     rbp
0x180052834  retn
```
