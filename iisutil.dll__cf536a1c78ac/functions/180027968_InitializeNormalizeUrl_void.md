# InitializeNormalizeUrl(void)

- ea: `0x180027968`
- end: `0x180027b2b`
- name: `?InitializeNormalizeUrl@@YAJXZ`
- size: `451`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x18001fbd0`

## callees

- `0x180027968`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x180027af6`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x180027af6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800279cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800279cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027aea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027aea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027a0d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027a61`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027ab9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027a0d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027a61`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027ab9`

## string_xrefs

- `0x18002799f`: `System\CurrentControlSet\Services\http\Parameters`

## pseudocode

```c
__int64 InitializeNormalizeUrl(void)
{
  int v0; // ebx
  LSTATUS v1; // eax
  LSTATUS v2; // eax
  LSTATUS v3; // eax
  __int16 v4; // ax
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  DWORD Type; // [rsp+58h] [rbp+28h] BYREF
  int Data; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  hKey = 0;
  v0 = 1;
  g_fEnableNonUTF8 = 1;
  Type = 0;
  Data = 0;
  cbData = 0;
  g_fEnableDBCS = 0;
  dword_1800505F0 = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\http\\Parameters", 0, 0x20019u, &hKey) )
    goto LABEL_19;
  cbData = 4;
  v1 = RegQueryValueExW(hKey, L"EnableNonUTF8", 0, &Type, (LPBYTE)&Data, &cbData);
  if ( v1 || Type != 4 )
  {
    v1 = g_fEnableNonUTF8;
  }
  else
  {
    LOBYTE(v1) = Data != 0;
    g_fEnableNonUTF8 = v1;
  }
  if ( !v1 )
  {
    v2 = 0;
    goto LABEL_12;
  }
  cbData = 4;
  v2 = RegQueryValueExW(hKey, L"EnableDBCS", 0, &Type, (LPBYTE)&Data, &cbData);
  if ( !v2 && Type == 4 )
  {
    LOBYTE(v2) = Data != 0;
LABEL_12:
    g_fEnableDBCS = v2;
    goto LABEL_13;
  }
  v2 = g_fEnableDBCS;
LABEL_13:
  if ( v2 )
  {
    cbData = 4;
    v3 = RegQueryValueExW(hKey, L"FavorDBCS", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( !v3 && Type == 4 )
    {
      LOBYTE(v3) = Data != 0;
      dword_1800505F0 = v3;
    }
  }
  else
  {
    dword_1800505F0 = 0;
  }
  RegCloseKey(hKey);
LABEL_19:
  v4 = GetSystemDefaultLangID() & 0x3FF;
  if ( v4 != 4 && (unsigned __int16)(v4 - 17) > 1u )
    v0 = 0;
  g_fIsSystemDBCS = v0;
  return 0;
}

```

## disassembly

```asm
0x180027968  push    rbp
0x18002796a  push    rbx
0x18002796b  push    rsi
0x18002796c  mov     rbp, rsp
0x18002796f  sub     rsp, 30h
0x180027973  lea     rax, [rbp+hKey]
0x180027977  mov     [rbp+hKey], 0
0x18002797f  mov     ebx, 1
0x180027984  mov     [rsp+30h+phkResult], rax; phkResult
0x180027989  mov     r9d, 20019h; samDesired
0x18002798f  mov     cs:?g_fEnableNonUTF8@@3HA, ebx; int g_fEnableNonUTF8
0x180027995  xor     r8d, r8d; ulOptions
0x180027998  mov     [rbp+Type], 0
0x18002799f  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\ht"...
0x1800279a6  mov     [rbp+Data], 0
0x1800279ad  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800279b4  mov     [rbp+cbData], 0
0x1800279bb  mov     cs:?g_fEnableDBCS@@3HA, 0; int g_fEnableDBCS
0x1800279c5  mov     cs:dword_1800505F0, 0
0x1800279cf  call    cs:__imp_RegOpenKeyExW
0x1800279d6  nop     dword ptr [rax+rax+00h]
0x1800279db  lea     esi, [rbx+3]
0x1800279de  test    eax, eax
0x1800279e0  jnz     loc_180027AF6
0x1800279e6  mov     rcx, [rbp+hKey]; hKey
0x1800279ea  lea     rax, [rbp+cbData]
0x1800279ee  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800279f3  lea     r9, [rbp+Type]; lpType
0x1800279f7  lea     rax, [rbp+Data]
0x1800279fb  mov     [rbp+cbData], esi
0x1800279fe  xor     r8d, r8d; lpReserved
0x180027a01  mov     [rsp+30h+phkResult], rax; lpData
0x180027a06  lea     rdx, aEnablenonutf8; "EnableNonUTF8"
0x180027a0d  call    cs:__imp_RegQueryValueExW
0x180027a14  nop     dword ptr [rax+rax+00h]
0x180027a19  test    eax, eax
0x180027a1b  jnz     short loc_180027A30
0x180027a1d  cmp     [rbp+Type], esi
0x180027a20  jnz     short loc_180027A30
0x180027a22  cmp     [rbp+Data], eax
0x180027a25  setnz   al
0x180027a28  mov     cs:?g_fEnableNonUTF8@@3HA, eax; int g_fEnableNonUTF8
0x180027a2e  jmp     short loc_180027A36
0x180027a30  mov     eax, cs:?g_fEnableNonUTF8@@3HA; int g_fEnableNonUTF8
0x180027a36  test    eax, eax
0x180027a38  jz      short loc_180027A86
0x180027a3a  mov     rcx, [rbp+hKey]; hKey
0x180027a3e  lea     rax, [rbp+cbData]
0x180027a42  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180027a47  lea     r9, [rbp+Type]; lpType
0x180027a4b  lea     rax, [rbp+Data]
0x180027a4f  mov     [rbp+cbData], esi
0x180027a52  xor     r8d, r8d; lpReserved
0x180027a55  mov     [rsp+30h+phkResult], rax; lpData
0x180027a5a  lea     rdx, aEnabledbcs; "EnableDBCS"
0x180027a61  call    cs:__imp_RegQueryValueExW
0x180027a68  nop     dword ptr [rax+rax+00h]
0x180027a6d  test    eax, eax
0x180027a6f  jnz     short loc_180027A7E
0x180027a71  cmp     [rbp+Type], esi
0x180027a74  jnz     short loc_180027A7E
0x180027a76  cmp     [rbp+Data], eax
0x180027a79  setnz   al
0x180027a7c  jmp     short loc_180027A88
0x180027a7e  mov     eax, cs:?g_fEnableDBCS@@3HA; int g_fEnableDBCS
0x180027a84  jmp     short loc_180027A8E
0x180027a86  xor     eax, eax
0x180027a88  mov     cs:?g_fEnableDBCS@@3HA, eax; int g_fEnableDBCS
0x180027a8e  test    eax, eax
0x180027a90  jz      short loc_180027ADC
0x180027a92  mov     rcx, [rbp+hKey]; hKey
0x180027a96  lea     rax, [rbp+cbData]
0x180027a9a  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180027a9f  lea     r9, [rbp+Type]; lpType
0x180027aa3  lea     rax, [rbp+Data]
0x180027aa7  mov     [rbp+cbData], esi
0x180027aaa  xor     r8d, r8d; lpReserved
0x180027aad  mov     [rsp+30h+phkResult], rax; lpData
0x180027ab2  lea     rdx, aFavordbcs; "FavorDBCS"
0x180027ab9  call    cs:__imp_RegQueryValueExW
0x180027ac0  nop     dword ptr [rax+rax+00h]
0x180027ac5  test    eax, eax
0x180027ac7  jnz     short loc_180027AE6
0x180027ac9  cmp     [rbp+Type], esi
0x180027acc  jnz     short loc_180027AE6
0x180027ace  cmp     [rbp+Data], eax
0x180027ad1  setnz   al
0x180027ad4  mov     cs:dword_1800505F0, eax
0x180027ada  jmp     short loc_180027AE6
0x180027adc  mov     cs:dword_1800505F0, 0
0x180027ae6  mov     rcx, [rbp+hKey]; hKey
0x180027aea  call    cs:__imp_RegCloseKey
0x180027af1  nop     dword ptr [rax+rax+00h]
0x180027af6  call    cs:__imp_GetSystemDefaultLangID
0x180027afd  nop     dword ptr [rax+rax+00h]
0x180027b02  mov     ecx, 3FFh
0x180027b07  and     ax, cx
0x180027b0a  cmp     ax, si
0x180027b0d  jz      short loc_180027B1A
0x180027b0f  sub     ax, 11h
0x180027b13  cmp     ax, bx
0x180027b16  jbe     short loc_180027B1A
0x180027b18  xor     ebx, ebx
0x180027b1a  mov     cs:?g_fIsSystemDBCS@@3HA, ebx; int g_fIsSystemDBCS
0x180027b20  xor     eax, eax
0x180027b22  add     rsp, 30h
0x180027b26  pop     rsi
0x180027b27  pop     rbx
0x180027b28  pop     rbp
0x180027b29  retn
```
