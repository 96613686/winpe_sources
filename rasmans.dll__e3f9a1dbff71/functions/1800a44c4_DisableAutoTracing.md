# DisableAutoTracing

- ea: `0x1800a44c4`
- end: `0x1800a4626`
- name: `DisableAutoTracing`
- size: `354`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002040c`

## callees

- `0x1800a44c4`
- `0x1800a462c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a453c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a453c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a4508`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a4508`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a4615`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a4615`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a457f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a45a7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a457f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a45a7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800a45f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800a45f1`

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
0x1800a44c4  push    rbp
0x1800a44c6  push    rbx
0x1800a44c7  push    rsi
0x1800a44c8  push    rdi
0x1800a44c9  mov     rbp, rsp
0x1800a44cc  sub     rsp, 78h
0x1800a44d0  xor     edi, edi
0x1800a44d2  lea     rax, [rbp+hKey]
0x1800a44d6  mov     r9d, 2011Fh; samDesired
0x1800a44dc  mov     [rbp+hKey], rdi
0x1800a44e0  xor     r8d, r8d; ulOptions
0x1800a44e3  mov     [rbp+Data], edi
0x1800a44e6  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Tracing"
0x1800a44ed  mov     [rbp+arg_18], edi
0x1800a44f0  lea     esi, [rdi+4]
0x1800a44f3  mov     [rbp+cSubKeys], edi
0x1800a44f6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a44fd  mov     [rbp+cbData], esi
0x1800a4500  mov     [rbp+cbMaxSubKeyLen], edi
0x1800a4503  mov     [rsp+78h+phkResult], rax; phkResult
0x1800a4508  call    cs:__imp_RegOpenKeyExW
0x1800a450e  test    eax, eax
0x1800a4510  jnz     loc_1800A461D
0x1800a4516  mov     rcx, [rbp+hKey]; hKey
0x1800a451a  lea     rax, [rbp+cbData]
0x1800a451e  mov     [rsp+78h+lpcbData], rax; lpcbData
0x1800a4523  lea     rdx, aEnableautofile; "EnableAutoFileTracing"
0x1800a452a  lea     rax, [rbp+Data]
0x1800a452e  mov     [rbp+cbData], esi
0x1800a4531  xor     r9d, r9d; lpType
0x1800a4534  mov     [rsp+78h+phkResult], rax; lpData
0x1800a4539  xor     r8d, r8d; lpReserved
0x1800a453c  call    cs:__imp_RegQueryValueExW
0x1800a4542  mov     ebx, eax
0x1800a4544  cmp     eax, 2
0x1800a4547  jz      loc_1800A460F
0x1800a454d  test    eax, eax
0x1800a454f  jnz     loc_1800A4611
0x1800a4555  cmp     [rbp+Data], 1
0x1800a4559  jnz     short loc_1800A45B5
0x1800a455b  mov     rcx, [rbp+hKey]; hKey
0x1800a455f  lea     rax, [rbp+Data]
0x1800a4563  mov     dword ptr [rsp+78h+lpcbData], esi; cbData
0x1800a4567  lea     rdx, aEnableautofile; "EnableAutoFileTracing"
0x1800a456e  mov     r9d, esi; dwType
0x1800a4571  mov     [rsp+78h+phkResult], rax; lpData
0x1800a4576  xor     r8d, r8d; Reserved
0x1800a4579  mov     [rbp+arg_18], edi
0x1800a457c  mov     [rbp+Data], edi
0x1800a457f  call    cs:__imp_RegSetValueExW
0x1800a4585  test    eax, eax
0x1800a4587  jnz     short loc_1800A45B1
0x1800a4589  mov     rcx, [rbp+hKey]; hKey
0x1800a458d  lea     rax, [rbp+arg_18]
0x1800a4591  mov     dword ptr [rsp+78h+lpcbData], esi; cbData
0x1800a4595  lea     rdx, aEnablefiletrac; "EnableFileTracing"
0x1800a459c  mov     r9d, esi; dwType
0x1800a459f  mov     [rsp+78h+phkResult], rax; lpData
0x1800a45a4  xor     r8d, r8d; Reserved
0x1800a45a7  call    cs:__imp_RegSetValueExW
0x1800a45ad  test    eax, eax
0x1800a45af  jz      short loc_1800A45B5
0x1800a45b1  mov     ebx, eax
0x1800a45b3  jmp     short loc_1800A4611
0x1800a45b5  mov     rcx, [rbp+hKey]; hKey
0x1800a45b9  lea     rax, [rbp+cbMaxSubKeyLen]
0x1800a45bd  mov     [rsp+78h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x1800a45c2  xor     r9d, r9d; lpReserved
0x1800a45c5  mov     [rsp+78h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x1800a45ca  xor     r8d, r8d; lpcchClass
0x1800a45cd  mov     [rsp+78h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x1800a45d2  xor     edx, edx; lpClass
0x1800a45d4  mov     [rsp+78h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x1800a45d9  mov     [rsp+78h+lpcValues], rdi; lpcValues
0x1800a45de  mov     [rsp+78h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x1800a45e3  mov     [rsp+78h+lpcbData], rax; lpcbMaxSubKeyLen
0x1800a45e8  lea     rax, [rbp+cSubKeys]
0x1800a45ec  mov     [rsp+78h+phkResult], rax; lpcSubKeys
0x1800a45f1  call    cs:__imp_RegQueryInfoKeyW
0x1800a45f7  test    eax, eax
0x1800a45f9  jnz     short loc_1800A45B1
0x1800a45fb  mov     edx, [rbp+cbMaxSubKeyLen]
0x1800a45fe  mov     r8, [rbp+hKey]
0x1800a4602  inc     edx
0x1800a4604  mov     ecx, [rbp+cSubKeys]
0x1800a4607  mov     [rbp+cbMaxSubKeyLen], edx
0x1800a460a  call    DisableAutoTracingForSubkeys
0x1800a460f  mov     ebx, edi
0x1800a4611  mov     rcx, [rbp+hKey]; hKey
0x1800a4615  call    cs:__imp_RegCloseKey
0x1800a461b  mov     eax, ebx
0x1800a461d  add     rsp, 78h
0x1800a4621  pop     rdi
0x1800a4622  pop     rsi
0x1800a4623  pop     rbx
0x1800a4624  pop     rbp
0x1800a4625  retn
```
