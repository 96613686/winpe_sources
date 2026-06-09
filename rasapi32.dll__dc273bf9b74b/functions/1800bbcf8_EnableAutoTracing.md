# EnableAutoTracing

- ea: `0x1800bbcf8`
- end: `0x1800bbedc`
- name: `EnableAutoTracing`
- size: `484`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008a200`
- `0x18008b360`

## callees

- `0x1800bb588`
- `0x1800bbcf8`
- `0x1800bbee4`
- `0x1800bce34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bbd49`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bbd49`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bbdab`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bbdec`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bbe4e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bbdab`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bbdec`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bbe4e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800bbe96`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800bbe96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bbecb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bbecb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bbd7d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bbe20`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bbd7d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bbe20`

## pseudocode

```c
LSTATUS EnableAutoTracing()
{
  LSTATUS result; // eax
  LSTATUS v1; // ebx
  DWORD cSubKeys; // [rsp+60h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-10h] BYREF
  int Data; // [rsp+A0h] [rbp+28h] BYREF
  int v5; // [rsp+A8h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+B0h] [rbp+38h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+B8h] [rbp+40h] BYREF

  hKey = 0;
  v5 = 0;
  Data = 0;
  cSubKeys = 0;
  cbData = 4;
  cbMaxSubKeyLen = 0;
  result = IsDefaultTracingEnabled();
  if ( result )
  {
    result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Tracing", 0, 0x2011Fu, &hKey);
    if ( !result )
    {
      cbData = 4;
      v1 = RegQueryValueExW(hKey, L"EnableFileTracing", 0, 0, (LPBYTE)&Data, &cbData);
      if ( v1 == 2 )
      {
        Data = 0;
        v1 = RegSetValueExW(hKey, L"EnableFileTracing", 0, 4u, (const BYTE *)&Data, 4u);
      }
      if ( v1 )
        goto LABEL_15;
      if ( Data )
      {
        cbData = 4;
        v1 = RegQueryValueExW(hKey, L"EnableAutoFileTracing", 0, 0, (LPBYTE)&v5, &cbData);
        if ( v1 != 2 )
          goto LABEL_12;
        v5 = 0;
      }
      else
      {
        Data = 1;
        v5 = 1;
        v1 = RegSetValueExW(hKey, L"EnableFileTracing", 0, 4u, (const BYTE *)&Data, 4u);
        if ( v1 )
        {
LABEL_15:
          RegCloseKey(hKey);
          return v1;
        }
      }
      v1 = RegSetValueExW(hKey, L"EnableAutoFileTracing", 0, 4u, (const BYTE *)&v5, 4u);
LABEL_12:
      if ( !v1 )
      {
        v1 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
        if ( !v1 )
        {
          ClearFiles(cSubKeys, ++cbMaxSubKeyLen, hKey);
          EnableAutoTracingForSubkeys(cSubKeys, cbMaxSubKeyLen, hKey);
          v1 = 0;
        }
      }
      goto LABEL_15;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800bbcf8  push    rbp
0x1800bbcfa  push    rbx
0x1800bbcfb  push    rsi
0x1800bbcfc  push    rdi
0x1800bbcfd  mov     rbp, rsp
0x1800bbd00  sub     rsp, 78h
0x1800bbd04  xor     edi, edi
0x1800bbd06  mov     [rbp+hKey], rdi
0x1800bbd0a  mov     [rbp+arg_8], edi
0x1800bbd0d  mov     [rbp+Data], edi
0x1800bbd10  lea     esi, [rdi+4]
0x1800bbd13  mov     [rbp+cSubKeys], edi
0x1800bbd16  mov     [rbp+cbData], esi
0x1800bbd19  mov     [rbp+cbMaxSubKeyLen], edi
0x1800bbd1c  call    IsDefaultTracingEnabled
0x1800bbd21  test    eax, eax
0x1800bbd23  jz      loc_1800BBED3
0x1800bbd29  lea     rax, [rbp+hKey]
0x1800bbd2d  mov     r9d, 2011Fh; samDesired
0x1800bbd33  xor     r8d, r8d; ulOptions
0x1800bbd36  mov     [rsp+78h+phkResult], rax; phkResult
0x1800bbd3b  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Tracing"
0x1800bbd42  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800bbd49  call    cs:__imp_RegOpenKeyExW
0x1800bbd4f  test    eax, eax
0x1800bbd51  jnz     loc_1800BBED3
0x1800bbd57  mov     rcx, [rbp+hKey]; hKey
0x1800bbd5b  lea     rax, [rbp+cbData]
0x1800bbd5f  mov     [rsp+78h+lpcbData], rax; lpcbData
0x1800bbd64  lea     rdx, aEnablefiletrac; "EnableFileTracing"
0x1800bbd6b  lea     rax, [rbp+Data]
0x1800bbd6f  mov     [rbp+cbData], esi
0x1800bbd72  xor     r9d, r9d; lpType
0x1800bbd75  mov     [rsp+78h+phkResult], rax; lpData
0x1800bbd7a  xor     r8d, r8d; lpReserved
0x1800bbd7d  call    cs:__imp_RegQueryValueExW
0x1800bbd83  mov     ebx, eax
0x1800bbd85  cmp     eax, 2
0x1800bbd88  jnz     short loc_1800BBDB3
0x1800bbd8a  mov     rcx, [rbp+hKey]; hKey
0x1800bbd8e  lea     rax, [rbp+Data]
0x1800bbd92  mov     dword ptr [rsp+78h+lpcbData], esi; cbData
0x1800bbd96  lea     rdx, aEnablefiletrac; "EnableFileTracing"
0x1800bbd9d  mov     r9d, esi; dwType
0x1800bbda0  mov     [rsp+78h+phkResult], rax; lpData
0x1800bbda5  xor     r8d, r8d; Reserved
0x1800bbda8  mov     [rbp+Data], edi
0x1800bbdab  call    cs:__imp_RegSetValueExW
0x1800bbdb1  mov     ebx, eax
0x1800bbdb3  test    ebx, ebx
0x1800bbdb5  jnz     loc_1800BBEC7
0x1800bbdbb  mov     rcx, [rbp+hKey]; hKey
0x1800bbdbf  cmp     [rbp+Data], edi
0x1800bbdc2  jnz     short loc_1800BBDFE
0x1800bbdc4  lea     rax, [rbp+Data]
0x1800bbdc8  mov     dword ptr [rsp+78h+lpcbData], esi; cbData
0x1800bbdcc  mov     r9d, esi; dwType
0x1800bbdcf  mov     [rsp+78h+phkResult], rax; lpData
0x1800bbdd4  xor     r8d, r8d; Reserved
0x1800bbdd7  mov     [rbp+Data], 1
0x1800bbdde  lea     rdx, aEnablefiletrac; "EnableFileTracing"
0x1800bbde5  mov     [rbp+arg_8], 1
0x1800bbdec  call    cs:__imp_RegSetValueExW
0x1800bbdf2  mov     ebx, eax
0x1800bbdf4  test    eax, eax
0x1800bbdf6  jnz     loc_1800BBEC7
0x1800bbdfc  jmp     short loc_1800BBE30
0x1800bbdfe  lea     rax, [rbp+cbData]
0x1800bbe02  mov     [rbp+cbData], esi
0x1800bbe05  mov     [rsp+78h+lpcbData], rax; lpcbData
0x1800bbe0a  lea     rdx, aEnableautofile; "EnableAutoFileTracing"
0x1800bbe11  lea     rax, [rbp+arg_8]
0x1800bbe15  xor     r9d, r9d; lpType
0x1800bbe18  xor     r8d, r8d; lpReserved
0x1800bbe1b  mov     [rsp+78h+phkResult], rax; lpData
0x1800bbe20  call    cs:__imp_RegQueryValueExW
0x1800bbe26  mov     ebx, eax
0x1800bbe28  cmp     eax, 2
0x1800bbe2b  jnz     short loc_1800BBE56
0x1800bbe2d  mov     [rbp+arg_8], edi
0x1800bbe30  mov     rcx, [rbp+hKey]; hKey
0x1800bbe34  lea     rax, [rbp+arg_8]
0x1800bbe38  mov     dword ptr [rsp+78h+lpcbData], esi; cbData
0x1800bbe3c  lea     rdx, aEnableautofile; "EnableAutoFileTracing"
0x1800bbe43  mov     r9d, esi; dwType
0x1800bbe46  mov     [rsp+78h+phkResult], rax; lpData
0x1800bbe4b  xor     r8d, r8d; Reserved
0x1800bbe4e  call    cs:__imp_RegSetValueExW
0x1800bbe54  mov     ebx, eax
0x1800bbe56  test    ebx, ebx
0x1800bbe58  jnz     short loc_1800BBEC7
0x1800bbe5a  mov     rcx, [rbp+hKey]; hKey
0x1800bbe5e  lea     rax, [rbp+cbMaxSubKeyLen]
0x1800bbe62  mov     [rsp+78h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x1800bbe67  xor     r9d, r9d; lpReserved
0x1800bbe6a  mov     [rsp+78h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x1800bbe6f  xor     r8d, r8d; lpcchClass
0x1800bbe72  mov     [rsp+78h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x1800bbe77  xor     edx, edx; lpClass
0x1800bbe79  mov     [rsp+78h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x1800bbe7e  mov     [rsp+78h+lpcValues], rdi; lpcValues
0x1800bbe83  mov     [rsp+78h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x1800bbe88  mov     [rsp+78h+lpcbData], rax; lpcbMaxSubKeyLen
0x1800bbe8d  lea     rax, [rbp+cSubKeys]
0x1800bbe91  mov     [rsp+78h+phkResult], rax; lpcSubKeys
0x1800bbe96  call    cs:__imp_RegQueryInfoKeyW
0x1800bbe9c  mov     ebx, eax
0x1800bbe9e  test    eax, eax
0x1800bbea0  jnz     short loc_1800BBEC7
0x1800bbea2  mov     edx, [rbp+cbMaxSubKeyLen]
0x1800bbea5  mov     r8, [rbp+hKey]
0x1800bbea9  inc     edx
0x1800bbeab  mov     ecx, [rbp+cSubKeys]
0x1800bbeae  mov     [rbp+cbMaxSubKeyLen], edx
0x1800bbeb1  call    ClearFiles
0x1800bbeb6  mov     r8, [rbp+hKey]
0x1800bbeba  mov     edx, [rbp+cbMaxSubKeyLen]
0x1800bbebd  mov     ecx, [rbp+cSubKeys]
0x1800bbec0  call    EnableAutoTracingForSubkeys
0x1800bbec5  mov     ebx, edi
0x1800bbec7  mov     rcx, [rbp+hKey]; hKey
0x1800bbecb  call    cs:__imp_RegCloseKey
0x1800bbed1  mov     eax, ebx
0x1800bbed3  add     rsp, 78h
0x1800bbed7  pop     rdi
0x1800bbed8  pop     rsi
0x1800bbed9  pop     rbx
0x1800bbeda  pop     rbp
0x1800bbedb  retn
```
