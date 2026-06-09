# DisableAutoTracing

- ea: `0x1800aa18c`
- end: `0x1800aa313`
- name: `DisableAutoTracing`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800210e0`

## callees

- `0x1800aa18c`
- `0x1800aa31c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800aa1d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800aa1d0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800aa253`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800aa281`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800aa253`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800aa281`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800aa2d1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800aa2d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800aa2fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800aa2fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800aa20a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800aa20a`

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
0x1800aa18c  push    rbp
0x1800aa18e  push    rbx
0x1800aa18f  push    rsi
0x1800aa190  push    rdi
0x1800aa191  mov     rbp, rsp
0x1800aa194  sub     rsp, 78h
0x1800aa198  xor     edi, edi
0x1800aa19a  lea     rax, [rbp+hKey]
0x1800aa19e  mov     r9d, 2011Fh; samDesired
0x1800aa1a4  mov     [rbp+hKey], rdi
0x1800aa1a8  xor     r8d, r8d; ulOptions
0x1800aa1ab  mov     [rbp+Data], edi
0x1800aa1ae  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Tracing"
0x1800aa1b5  mov     [rbp+arg_18], edi
0x1800aa1b8  lea     esi, [rdi+4]
0x1800aa1bb  mov     [rbp+cSubKeys], edi
0x1800aa1be  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800aa1c5  mov     [rbp+cbData], esi
0x1800aa1c8  mov     [rbp+cbMaxSubKeyLen], edi
0x1800aa1cb  mov     [rsp+78h+phkResult], rax; phkResult
0x1800aa1d0  call    cs:__imp_RegOpenKeyExW
0x1800aa1d7  nop     dword ptr [rax+rax+00h]
0x1800aa1dc  test    eax, eax
0x1800aa1de  jnz     loc_1800AA309
0x1800aa1e4  mov     rcx, [rbp+hKey]; hKey
0x1800aa1e8  lea     rax, [rbp+cbData]
0x1800aa1ec  mov     [rsp+78h+lpcbData], rax; lpcbData
0x1800aa1f1  lea     rdx, aEnableautofile; "EnableAutoFileTracing"
0x1800aa1f8  lea     rax, [rbp+Data]
0x1800aa1fc  mov     [rbp+cbData], esi
0x1800aa1ff  xor     r9d, r9d; lpType
0x1800aa202  mov     [rsp+78h+phkResult], rax; lpData
0x1800aa207  xor     r8d, r8d; lpReserved
0x1800aa20a  call    cs:__imp_RegQueryValueExW
0x1800aa211  nop     dword ptr [rax+rax+00h]
0x1800aa216  mov     ebx, eax
0x1800aa218  cmp     eax, 2
0x1800aa21b  jz      loc_1800AA2F5
0x1800aa221  test    eax, eax
0x1800aa223  jnz     loc_1800AA2F7
0x1800aa229  cmp     [rbp+Data], 1
0x1800aa22d  jnz     short loc_1800AA295
0x1800aa22f  mov     rcx, [rbp+hKey]; hKey
0x1800aa233  lea     rax, [rbp+Data]
0x1800aa237  mov     dword ptr [rsp+78h+lpcbData], esi; cbData
0x1800aa23b  lea     rdx, aEnableautofile; "EnableAutoFileTracing"
0x1800aa242  mov     r9d, esi; dwType
0x1800aa245  mov     [rsp+78h+phkResult], rax; lpData
0x1800aa24a  xor     r8d, r8d; Reserved
0x1800aa24d  mov     [rbp+arg_18], edi
0x1800aa250  mov     [rbp+Data], edi
0x1800aa253  call    cs:__imp_RegSetValueExW
0x1800aa25a  nop     dword ptr [rax+rax+00h]
0x1800aa25f  test    eax, eax
0x1800aa261  jnz     short loc_1800AA291
0x1800aa263  mov     rcx, [rbp+hKey]; hKey
0x1800aa267  lea     rax, [rbp+arg_18]
0x1800aa26b  mov     dword ptr [rsp+78h+lpcbData], esi; cbData
0x1800aa26f  lea     rdx, aEnablefiletrac; "EnableFileTracing"
0x1800aa276  mov     r9d, esi; dwType
0x1800aa279  mov     [rsp+78h+phkResult], rax; lpData
0x1800aa27e  xor     r8d, r8d; Reserved
0x1800aa281  call    cs:__imp_RegSetValueExW
0x1800aa288  nop     dword ptr [rax+rax+00h]
0x1800aa28d  test    eax, eax
0x1800aa28f  jz      short loc_1800AA295
0x1800aa291  mov     ebx, eax
0x1800aa293  jmp     short loc_1800AA2F7
0x1800aa295  mov     rcx, [rbp+hKey]; hKey
0x1800aa299  lea     rax, [rbp+cbMaxSubKeyLen]
0x1800aa29d  mov     [rsp+78h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x1800aa2a2  xor     r9d, r9d; lpReserved
0x1800aa2a5  mov     [rsp+78h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x1800aa2aa  xor     r8d, r8d; lpcchClass
0x1800aa2ad  mov     [rsp+78h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x1800aa2b2  xor     edx, edx; lpClass
0x1800aa2b4  mov     [rsp+78h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x1800aa2b9  mov     [rsp+78h+lpcValues], rdi; lpcValues
0x1800aa2be  mov     [rsp+78h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x1800aa2c3  mov     [rsp+78h+lpcbData], rax; lpcbMaxSubKeyLen
0x1800aa2c8  lea     rax, [rbp+cSubKeys]
0x1800aa2cc  mov     [rsp+78h+phkResult], rax; lpcSubKeys
0x1800aa2d1  call    cs:__imp_RegQueryInfoKeyW
0x1800aa2d8  nop     dword ptr [rax+rax+00h]
0x1800aa2dd  test    eax, eax
0x1800aa2df  jnz     short loc_1800AA291
0x1800aa2e1  mov     edx, [rbp+cbMaxSubKeyLen]
0x1800aa2e4  mov     r8, [rbp+hKey]
0x1800aa2e8  inc     edx
0x1800aa2ea  mov     ecx, [rbp+cSubKeys]
0x1800aa2ed  mov     [rbp+cbMaxSubKeyLen], edx
0x1800aa2f0  call    DisableAutoTracingForSubkeys
0x1800aa2f5  mov     ebx, edi
0x1800aa2f7  mov     rcx, [rbp+hKey]; hKey
0x1800aa2fb  call    cs:__imp_RegCloseKey
0x1800aa302  nop     dword ptr [rax+rax+00h]
0x1800aa307  mov     eax, ebx
0x1800aa309  add     rsp, 78h
0x1800aa30d  pop     rdi
0x1800aa30e  pop     rsi
0x1800aa30f  pop     rbx
0x1800aa310  pop     rbp
0x1800aa311  retn
```
