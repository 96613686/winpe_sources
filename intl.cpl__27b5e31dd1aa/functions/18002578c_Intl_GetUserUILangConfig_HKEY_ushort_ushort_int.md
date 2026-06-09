# Intl_GetUserUILangConfig(HKEY__ *,ushort *,ushort *,int)

- ea: `0x18002578c`
- end: `0x1800258c2`
- name: `?Intl_GetUserUILangConfig@@YAKPEAUHKEY__@@PEAG1H@Z`
- size: `310`
- prototype: `unsigned int __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned __int16 *Destination, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180026304`
- `0x180026994`

## callees

- `0x18002578c`
- `0x18002a112`
- `0x18002a150`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18002588b`
- `msvcrt!memcpy_s` at `0x18002588b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002580b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025832`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002580b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025832`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025868`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025868`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002589d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002589d`

## string_xrefs

- `0x180025828`: `Control Panel\Desktop\LanguageConfiguration`
- `0x1800257eb`: `Control Panel\Desktop\LanguageConfigurationPending`

## pseudocode

```c
__int64 __fastcall Intl_GetUserUILangConfig(HKEY hKey, LPCWSTR lpValueName, unsigned __int16 *Destination)
{
  DWORD v6; // ebx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKeya; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[704]; // [rsp+40h] [rbp-C0h] BYREF

  hKeya = 0;
  Type = 0;
  cbData = 0;
  v6 = 0;
  memset_0(Data, 0, 0x2BCu);
  *Destination = 0;
  if ( !RegOpenKeyExW(hKey, L"Control Panel\\Desktop\\LanguageConfigurationPending", 0, 0x20019u, &hKeya)
    || !RegOpenKeyExW(hKey, L"Control Panel\\Desktop\\LanguageConfiguration", 0, 0x20019u, &hKeya) )
  {
    cbData = 700;
    if ( !RegQueryValueExW(hKeya, lpValueName, 0, &Type, Data, &cbData)
      && Type == 7
      && !memcpy_s(Destination, 0x2BCu, Data, cbData) )
    {
      v6 = cbData;
    }
    RegCloseKey(hKeya);
  }
  return v6;
}

```

## disassembly

```asm
0x18002578c  push    rbp
0x18002578e  push    rbx
0x18002578f  push    rsi
0x180025790  push    rdi
0x180025791  push    r14
0x180025793  lea     rbp, [rsp-210h]
0x18002579b  sub     rsp, 310h
0x1800257a2  mov     rax, cs:__security_cookie
0x1800257a9  xor     rax, rsp
0x1800257ac  mov     [rbp+230h+var_30], rax
0x1800257b3  mov     rsi, r8
0x1800257b6  mov     [rsp+330h+hKey], 0
0x1800257bf  mov     r14, rdx
0x1800257c2  mov     [rsp+330h+Type], 0
0x1800257ca  mov     rdi, rcx
0x1800257cd  mov     [rsp+330h+cbData], 0
0x1800257d5  xor     edx, edx; Val
0x1800257d7  lea     rcx, [rsp+330h+Data]; void *
0x1800257dc  mov     r8d, 2BCh; Size
0x1800257e2  xor     ebx, ebx
0x1800257e4  call    memset_0
0x1800257e9  xor     eax, eax
0x1800257eb  lea     rdx, aControlPanelDe; "Control Panel\\Desktop\\LanguageConfigu"...
0x1800257f2  mov     [rsi], ax
0x1800257f5  mov     r9d, 20019h; samDesired
0x1800257fb  lea     rax, [rsp+330h+hKey]
0x180025800  xor     r8d, r8d; ulOptions
0x180025803  mov     rcx, rdi; hKey
0x180025806  mov     [rsp+330h+phkResult], rax; phkResult
0x18002580b  call    cs:__imp_RegOpenKeyExW
0x180025811  test    eax, eax
0x180025813  jz      short loc_18002583C
0x180025815  lea     rax, [rsp+330h+hKey]
0x18002581a  mov     r9d, 20019h; samDesired
0x180025820  xor     r8d, r8d; ulOptions
0x180025823  mov     [rsp+330h+phkResult], rax; phkResult
0x180025828  lea     rdx, ?c_szUILanguageConfig@@3QBGB; "Control Panel\\Desktop\\LanguageConfigu"...
0x18002582f  mov     rcx, rdi; hKey
0x180025832  call    cs:__imp_RegOpenKeyExW
0x180025838  test    eax, eax
0x18002583a  jnz     short loc_1800258A3
0x18002583c  mov     rcx, [rsp+330h+hKey]; hKey
0x180025841  lea     rax, [rsp+330h+cbData]
0x180025846  mov     [rsp+330h+lpcbData], rax; lpcbData
0x18002584b  lea     r9, [rsp+330h+Type]; lpType
0x180025850  lea     rax, [rsp+330h+Data]
0x180025855  mov     [rsp+330h+cbData], 2BCh
0x18002585d  xor     r8d, r8d; lpReserved
0x180025860  mov     [rsp+330h+phkResult], rax; lpData
0x180025865  mov     rdx, r14; lpValueName
0x180025868  call    cs:__imp_RegQueryValueExW
0x18002586e  test    eax, eax
0x180025870  jnz     short loc_180025898
0x180025872  cmp     [rsp+330h+Type], 7
0x180025877  jnz     short loc_180025898
0x180025879  mov     r9d, [rsp+330h+cbData]; SourceSize
0x18002587e  lea     r8, [rsp+330h+Data]; Source
0x180025883  mov     edx, 2BCh; DestinationSize
0x180025888  mov     rcx, rsi; Destination
0x18002588b  call    cs:__imp_memcpy_s
0x180025891  test    eax, eax
0x180025893  cmovz   ebx, [rsp+330h+cbData]
0x180025898  mov     rcx, [rsp+330h+hKey]; hKey
0x18002589d  call    cs:__imp_RegCloseKey
0x1800258a3  mov     eax, ebx
0x1800258a5  mov     rcx, [rbp+230h+var_30]
0x1800258ac  xor     rcx, rsp; StackCookie
0x1800258af  call    __security_check_cookie
0x1800258b4  add     rsp, 310h
0x1800258bb  pop     r14
0x1800258bd  pop     rdi
0x1800258be  pop     rsi
0x1800258bf  pop     rbx
0x1800258c0  pop     rbp
0x1800258c1  retn
```
