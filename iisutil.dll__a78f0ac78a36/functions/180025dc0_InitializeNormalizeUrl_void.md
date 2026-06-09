# InitializeNormalizeUrl(void)

- ea: `0x180025dc0`
- end: `0x180025f5e`
- name: `?InitializeNormalizeUrl@@YAJXZ`
- size: `414`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x18001ea00`

## callees

- `0x180025dc0`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x180025f30`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x180025f30`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025e27`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025e27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025f2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025f2a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025e5f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025ead`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025eff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025e5f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025ead`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025eff`

## string_xrefs

- `0x180025df7`: `System\CurrentControlSet\Services\http\Parameters`

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
  dword_18004E558 = 0;
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
      dword_18004E558 = v3;
    }
  }
  else
  {
    dword_18004E558 = 0;
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
0x180025dc0  push    rbp
0x180025dc2  push    rbx
0x180025dc3  push    rsi
0x180025dc4  mov     rbp, rsp
0x180025dc7  sub     rsp, 30h
0x180025dcb  lea     rax, [rbp+hKey]
0x180025dcf  mov     [rbp+hKey], 0
0x180025dd7  mov     ebx, 1
0x180025ddc  mov     [rsp+30h+phkResult], rax; phkResult
0x180025de1  mov     r9d, 20019h; samDesired
0x180025de7  mov     cs:?g_fEnableNonUTF8@@3HA, ebx; int g_fEnableNonUTF8
0x180025ded  xor     r8d, r8d; ulOptions
0x180025df0  mov     [rbp+Type], 0
0x180025df7  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\ht"...
0x180025dfe  mov     [rbp+Data], 0
0x180025e05  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180025e0c  mov     [rbp+cbData], 0
0x180025e13  mov     cs:?g_fEnableDBCS@@3HA, 0; int g_fEnableDBCS
0x180025e1d  mov     cs:dword_18004E558, 0
0x180025e27  call    cs:__imp_RegOpenKeyExW
0x180025e2d  lea     esi, [rbx+3]
0x180025e30  test    eax, eax
0x180025e32  jnz     loc_180025F30
0x180025e38  mov     rcx, [rbp+hKey]; hKey
0x180025e3c  lea     rax, [rbp+cbData]
0x180025e40  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180025e45  lea     r9, [rbp+Type]; lpType
0x180025e49  lea     rax, [rbp+Data]
0x180025e4d  mov     [rbp+cbData], esi
0x180025e50  xor     r8d, r8d; lpReserved
0x180025e53  mov     [rsp+30h+phkResult], rax; lpData
0x180025e58  lea     rdx, aEnablenonutf8; "EnableNonUTF8"
0x180025e5f  call    cs:__imp_RegQueryValueExW
0x180025e65  test    eax, eax
0x180025e67  jnz     short loc_180025E7C
0x180025e69  cmp     [rbp+Type], esi
0x180025e6c  jnz     short loc_180025E7C
0x180025e6e  cmp     [rbp+Data], eax
0x180025e71  setnz   al
0x180025e74  mov     cs:?g_fEnableNonUTF8@@3HA, eax; int g_fEnableNonUTF8
0x180025e7a  jmp     short loc_180025E82
0x180025e7c  mov     eax, cs:?g_fEnableNonUTF8@@3HA; int g_fEnableNonUTF8
0x180025e82  test    eax, eax
0x180025e84  jz      short loc_180025ECC
0x180025e86  mov     rcx, [rbp+hKey]; hKey
0x180025e8a  lea     rax, [rbp+cbData]
0x180025e8e  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180025e93  lea     r9, [rbp+Type]; lpType
0x180025e97  lea     rax, [rbp+Data]
0x180025e9b  mov     [rbp+cbData], esi
0x180025e9e  xor     r8d, r8d; lpReserved
0x180025ea1  mov     [rsp+30h+phkResult], rax; lpData
0x180025ea6  lea     rdx, aEnabledbcs; "EnableDBCS"
0x180025ead  call    cs:__imp_RegQueryValueExW
0x180025eb3  test    eax, eax
0x180025eb5  jnz     short loc_180025EC4
0x180025eb7  cmp     [rbp+Type], esi
0x180025eba  jnz     short loc_180025EC4
0x180025ebc  cmp     [rbp+Data], eax
0x180025ebf  setnz   al
0x180025ec2  jmp     short loc_180025ECE
0x180025ec4  mov     eax, cs:?g_fEnableDBCS@@3HA; int g_fEnableDBCS
0x180025eca  jmp     short loc_180025ED4
0x180025ecc  xor     eax, eax
0x180025ece  mov     cs:?g_fEnableDBCS@@3HA, eax; int g_fEnableDBCS
0x180025ed4  test    eax, eax
0x180025ed6  jz      short loc_180025F1C
0x180025ed8  mov     rcx, [rbp+hKey]; hKey
0x180025edc  lea     rax, [rbp+cbData]
0x180025ee0  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180025ee5  lea     r9, [rbp+Type]; lpType
0x180025ee9  lea     rax, [rbp+Data]
0x180025eed  mov     [rbp+cbData], esi
0x180025ef0  xor     r8d, r8d; lpReserved
0x180025ef3  mov     [rsp+30h+phkResult], rax; lpData
0x180025ef8  lea     rdx, aFavordbcs; "FavorDBCS"
0x180025eff  call    cs:__imp_RegQueryValueExW
0x180025f05  test    eax, eax
0x180025f07  jnz     short loc_180025F26
0x180025f09  cmp     [rbp+Type], esi
0x180025f0c  jnz     short loc_180025F26
0x180025f0e  cmp     [rbp+Data], eax
0x180025f11  setnz   al
0x180025f14  mov     cs:dword_18004E558, eax
0x180025f1a  jmp     short loc_180025F26
0x180025f1c  mov     cs:dword_18004E558, 0
0x180025f26  mov     rcx, [rbp+hKey]; hKey
0x180025f2a  call    cs:__imp_RegCloseKey
0x180025f30  call    cs:__imp_GetSystemDefaultLangID
0x180025f36  mov     ecx, 3FFh
0x180025f3b  and     ax, cx
0x180025f3e  cmp     ax, si
0x180025f41  jz      short loc_180025F4E
0x180025f43  sub     ax, 11h
0x180025f47  cmp     ax, bx
0x180025f4a  jbe     short loc_180025F4E
0x180025f4c  xor     ebx, ebx
0x180025f4e  mov     cs:?g_fIsSystemDBCS@@3HA, ebx; int g_fIsSystemDBCS
0x180025f54  xor     eax, eax
0x180025f56  add     rsp, 30h
0x180025f5a  pop     rsi
0x180025f5b  pop     rbx
0x180025f5c  pop     rbp
0x180025f5d  retn
```
