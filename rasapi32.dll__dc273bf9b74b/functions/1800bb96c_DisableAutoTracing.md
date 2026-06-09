# DisableAutoTracing

- ea: `0x1800bb96c`
- end: `0x1800bbace`
- name: `DisableAutoTracing`
- size: `354`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008fec0`
- `0x180090f60`

## callees

- `0x1800bb96c`
- `0x1800bbad4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bb9b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bb9b0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bba27`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bba4f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bba27`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bba4f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800bba99`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800bba99`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bbabd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bbabd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bb9e4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bb9e4`

## pseudocode

```c
LSTATUS DisableAutoTracing()
{
  LSTATUS result; // eax
  LSTATUS v1; // eax
  LSTATUS v2; // ebx
  LSTATUS v3; // eax
  DWORD cSubKeys; // [rsp+60h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-10h] BYREF
  int Data; // [rsp+A0h] [rbp+28h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+A8h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+B0h] [rbp+38h] BYREF
  int v9; // [rsp+B8h] [rbp+40h] BYREF

  hKey = 0;
  Data = 0;
  v9 = 0;
  cSubKeys = 0;
  cbData = 4;
  cbMaxSubKeyLen = 0;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Tracing", 0, 0x2011Fu, &hKey);
  if ( !result )
  {
    cbData = 4;
    v1 = RegQueryValueExW(hKey, L"EnableAutoFileTracing", 0, 0, (LPBYTE)&Data, &cbData);
    v2 = v1;
    if ( v1 != 2 )
    {
      if ( !v1 )
      {
        if ( Data != 1
          || (v9 = 0,
              Data = 0,
              (v3 = RegSetValueExW(hKey, L"EnableAutoFileTracing", 0, 4u, (const BYTE *)&Data, 4u)) == 0)
          && (v3 = RegSetValueExW(hKey, L"EnableFileTracing", 0, 4u, (const BYTE *)&v9, 4u)) == 0 )
        {
          v3 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
          if ( !v3 )
          {
            DisableAutoTracingForSubkeys(cSubKeys, ++cbMaxSubKeyLen, hKey);
            goto LABEL_10;
          }
        }
        v2 = v3;
      }
LABEL_11:
      RegCloseKey(hKey);
      return v2;
    }
LABEL_10:
    v2 = 0;
    goto LABEL_11;
  }
  return result;
}

```

## disassembly

```asm
0x1800bb96c  push    rbp
0x1800bb96e  push    rbx
0x1800bb96f  push    rsi
0x1800bb970  push    rdi
0x1800bb971  mov     rbp, rsp
0x1800bb974  sub     rsp, 78h
0x1800bb978  xor     edi, edi
0x1800bb97a  lea     rax, [rbp+hKey]
0x1800bb97e  mov     r9d, 2011Fh; samDesired
0x1800bb984  mov     [rbp+hKey], rdi
0x1800bb988  xor     r8d, r8d; ulOptions
0x1800bb98b  mov     [rbp+Data], edi
0x1800bb98e  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Tracing"
0x1800bb995  mov     [rbp+arg_18], edi
0x1800bb998  lea     esi, [rdi+4]
0x1800bb99b  mov     [rbp+cSubKeys], edi
0x1800bb99e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800bb9a5  mov     [rbp+cbData], esi
0x1800bb9a8  mov     [rbp+cbMaxSubKeyLen], edi
0x1800bb9ab  mov     [rsp+78h+phkResult], rax; phkResult
0x1800bb9b0  call    cs:__imp_RegOpenKeyExW
0x1800bb9b6  test    eax, eax
0x1800bb9b8  jnz     loc_1800BBAC5
0x1800bb9be  mov     rcx, [rbp+hKey]; hKey
0x1800bb9c2  lea     rax, [rbp+cbData]
0x1800bb9c6  mov     [rsp+78h+lpcbData], rax; lpcbData
0x1800bb9cb  lea     rdx, aEnableautofile; "EnableAutoFileTracing"
0x1800bb9d2  lea     rax, [rbp+Data]
0x1800bb9d6  mov     [rbp+cbData], esi
0x1800bb9d9  xor     r9d, r9d; lpType
0x1800bb9dc  mov     [rsp+78h+phkResult], rax; lpData
0x1800bb9e1  xor     r8d, r8d; lpReserved
0x1800bb9e4  call    cs:__imp_RegQueryValueExW
0x1800bb9ea  mov     ebx, eax
0x1800bb9ec  cmp     eax, 2
0x1800bb9ef  jz      loc_1800BBAB7
0x1800bb9f5  test    eax, eax
0x1800bb9f7  jnz     loc_1800BBAB9
0x1800bb9fd  cmp     [rbp+Data], 1
0x1800bba01  jnz     short loc_1800BBA5D
0x1800bba03  mov     rcx, [rbp+hKey]; hKey
0x1800bba07  lea     rax, [rbp+Data]
0x1800bba0b  mov     dword ptr [rsp+78h+lpcbData], esi; cbData
0x1800bba0f  lea     rdx, aEnableautofile; "EnableAutoFileTracing"
0x1800bba16  mov     r9d, esi; dwType
0x1800bba19  mov     [rsp+78h+phkResult], rax; lpData
0x1800bba1e  xor     r8d, r8d; Reserved
0x1800bba21  mov     [rbp+arg_18], edi
0x1800bba24  mov     [rbp+Data], edi
0x1800bba27  call    cs:__imp_RegSetValueExW
0x1800bba2d  test    eax, eax
0x1800bba2f  jnz     short loc_1800BBA59
0x1800bba31  mov     rcx, [rbp+hKey]; hKey
0x1800bba35  lea     rax, [rbp+arg_18]
0x1800bba39  mov     dword ptr [rsp+78h+lpcbData], esi; cbData
0x1800bba3d  lea     rdx, aEnablefiletrac; "EnableFileTracing"
0x1800bba44  mov     r9d, esi; dwType
0x1800bba47  mov     [rsp+78h+phkResult], rax; lpData
0x1800bba4c  xor     r8d, r8d; Reserved
0x1800bba4f  call    cs:__imp_RegSetValueExW
0x1800bba55  test    eax, eax
0x1800bba57  jz      short loc_1800BBA5D
0x1800bba59  mov     ebx, eax
0x1800bba5b  jmp     short loc_1800BBAB9
0x1800bba5d  mov     rcx, [rbp+hKey]; hKey
0x1800bba61  lea     rax, [rbp+cbMaxSubKeyLen]
0x1800bba65  mov     [rsp+78h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x1800bba6a  xor     r9d, r9d; lpReserved
0x1800bba6d  mov     [rsp+78h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x1800bba72  xor     r8d, r8d; lpcchClass
0x1800bba75  mov     [rsp+78h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x1800bba7a  xor     edx, edx; lpClass
0x1800bba7c  mov     [rsp+78h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x1800bba81  mov     [rsp+78h+lpcValues], rdi; lpcValues
0x1800bba86  mov     [rsp+78h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x1800bba8b  mov     [rsp+78h+lpcbData], rax; lpcbMaxSubKeyLen
0x1800bba90  lea     rax, [rbp+cSubKeys]
0x1800bba94  mov     [rsp+78h+phkResult], rax; lpcSubKeys
0x1800bba99  call    cs:__imp_RegQueryInfoKeyW
0x1800bba9f  test    eax, eax
0x1800bbaa1  jnz     short loc_1800BBA59
0x1800bbaa3  mov     edx, [rbp+cbMaxSubKeyLen]
0x1800bbaa6  mov     r8, [rbp+hKey]
0x1800bbaaa  inc     edx
0x1800bbaac  mov     ecx, [rbp+cSubKeys]
0x1800bbaaf  mov     [rbp+cbMaxSubKeyLen], edx
0x1800bbab2  call    DisableAutoTracingForSubkeys
0x1800bbab7  mov     ebx, edi
0x1800bbab9  mov     rcx, [rbp+hKey]; hKey
0x1800bbabd  call    cs:__imp_RegCloseKey
0x1800bbac3  mov     eax, ebx
0x1800bbac5  add     rsp, 78h
0x1800bbac9  pop     rdi
0x1800bbaca  pop     rsi
0x1800bbacb  pop     rbx
0x1800bbacc  pop     rbp
0x1800bbacd  retn
```
