# SLTConvertRegisterServer

- ea: `0x180049fc8`
- end: `0x18004a1dc`
- name: `SLTConvertRegisterServer`
- size: `532`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800155d0`

## callees

- `0x18003f894`
- `0x180049fc8`
- `0x180055880`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18004a04b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18004a04b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004a0ad`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004a0e9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004a0ad`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004a0e9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a025`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a025`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004a131`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004a174`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004a131`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004a174`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18004a06b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18004a06b`

## string_xrefs

- `0x18004a00d`: `SOFTWARE\Classes\CLSID`
- `0x18004a160`: `ThreadingModel`

## pseudocode

```c
__int64 SLTConvertRegisterServer()
{
  LSTATUS v1; // ebx
  __int64 v2; // rbx
  __int64 v3; // rax
  HKEY v4; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v5; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey[2]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Filename[264]; // [rsp+70h] [rbp-90h] BYREF

  hKey[0] = 0;
  v5 = 0;
  v4 = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, g_wszRP_COMCLSIDS, 0, 0xF003Fu, hKey) )
    return 2147549183LL;
  if ( GetModuleFileNameW(g_hModule, Filename, 0x105u) )
  {
    v1 = RegDeleteTreeW(hKey[0], L"{1FCE6123-B675-4790-A629-F3E8AC06F839}");
    if ( v1 < 0 )
      goto LABEL_14;
    if ( !RegCreateKeyExW(hKey[0], L"{1FCE6123-B675-4790-A629-F3E8AC06F839}", 0, 0, 0, 0xF003Fu, 0, &v5, 0)
      && !RegCreateKeyExW(v5, g_wszRK_IPS32, 0, 0, 0, 0xF003Fu, 0, &v4, 0) )
    {
      v2 = -1;
      v3 = -1;
      do
        ++v3;
      while ( Filename[v3] );
      if ( !RegSetValueExW(v4, 0, 0, 1u, (const BYTE *)Filename, 2 * v3 + 2) )
      {
        do
          ++v2;
        while ( *(_WORD *)&g_wszRV_THREADING[2 * v2] );
        if ( !RegSetValueExW(v4, g_wszRN_THREADING, 0, 1u, g_wszRV_THREADING, 2 * v2 + 2) )
        {
          RegSafeCloseKey(&v4);
          RegSafeCloseKey(&v5);
          v1 = 0;
          goto LABEL_14;
        }
      }
    }
  }
  v1 = -2147418113;
LABEL_14:
  RegSafeCloseKey(&v4);
  RegSafeCloseKey(&v5);
  RegSafeCloseKey(hKey);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180049fc8  mov     [rsp-8+arg_0], rbx
0x180049fcd  mov     [rsp-8+arg_8], rdi
0x180049fd2  push    rbp
0x180049fd3  lea     rbp, [rsp-190h]
0x180049fdb  sub     rsp, 290h
0x180049fe2  mov     rax, cs:__security_cookie
0x180049fe9  xor     rax, rsp
0x180049fec  mov     [rbp+190h+var_10], rax
0x180049ff3  xor     edi, edi
0x180049ff5  lea     rax, [rsp+290h+hKey]
0x180049ffa  mov     r9d, 0F003Fh; samDesired
0x18004a000  mov     [rsp+290h+hKey], rdi
0x18004a005  xor     r8d, r8d; ulOptions
0x18004a008  mov     [rsp+290h+var_238], rdi
0x18004a00d  lea     rdx, ?g_wszRP_COMCLSIDS@@3PAGA; "SOFTWARE\\Classes\\CLSID"
0x18004a014  mov     [rsp+290h+var_240], rdi
0x18004a019  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004a020  mov     [rsp+290h+phkResult], rax; phkResult
0x18004a025  call    cs:__imp_RegOpenKeyExW
0x18004a02b  test    eax, eax
0x18004a02d  jz      short loc_18004A039
0x18004a02f  mov     eax, 8000FFFFh
0x18004a034  jmp     loc_18004A1B8
0x18004a039  mov     rcx, cs:?g_hModule@@3PEAUHINSTANCE__@@EA; hModule
0x18004a040  lea     rdx, [rsp+290h+Filename]; lpFilename
0x18004a045  mov     r8d, 105h; nSize
0x18004a04b  call    cs:__imp_GetModuleFileNameW
0x18004a051  test    eax, eax
0x18004a053  jnz     short loc_18004A05F
0x18004a055  mov     ebx, 8000FFFFh
0x18004a05a  jmp     loc_18004A198
0x18004a05f  mov     rcx, [rsp+290h+hKey]; hKey
0x18004a064  lea     rdx, a1fce6123B67547; "{1FCE6123-B675-4790-A629-F3E8AC06F839}"
0x18004a06b  call    cs:__imp_RegDeleteTreeW
0x18004a071  mov     ebx, eax
0x18004a073  test    eax, eax
0x18004a075  js      loc_18004A198
0x18004a07b  mov     rcx, [rsp+290h+hKey]; hKey
0x18004a080  lea     rax, [rsp+290h+var_238]
0x18004a085  mov     [rsp+290h+lpdwDisposition], rdi; lpdwDisposition
0x18004a08a  lea     rdx, a1fce6123B67547; "{1FCE6123-B675-4790-A629-F3E8AC06F839}"
0x18004a091  mov     [rsp+290h+var_258], rax; phkResult
0x18004a096  xor     r9d, r9d; lpClass
0x18004a099  mov     [rsp+290h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18004a09e  xor     r8d, r8d; Reserved
0x18004a0a1  mov     [rsp+290h+samDesired], 0F003Fh; samDesired
0x18004a0a9  mov     dword ptr [rsp+290h+phkResult], edi; dwOptions
0x18004a0ad  call    cs:__imp_RegCreateKeyExW
0x18004a0b3  test    eax, eax
0x18004a0b5  jnz     short loc_18004A055
0x18004a0b7  mov     rcx, [rsp+290h+var_238]; hKey
0x18004a0bc  lea     rax, [rsp+290h+var_240]
0x18004a0c1  mov     [rsp+290h+lpdwDisposition], rdi; lpdwDisposition
0x18004a0c6  lea     rdx, ?g_wszRK_IPS32@@3PAGA; "InprocServer32"
0x18004a0cd  mov     [rsp+290h+var_258], rax; phkResult
0x18004a0d2  xor     r9d, r9d; lpClass
0x18004a0d5  mov     [rsp+290h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18004a0da  xor     r8d, r8d; Reserved
0x18004a0dd  mov     [rsp+290h+samDesired], 0F003Fh; samDesired
0x18004a0e5  mov     dword ptr [rsp+290h+phkResult], edi; dwOptions
0x18004a0e9  call    cs:__imp_RegCreateKeyExW
0x18004a0ef  test    eax, eax
0x18004a0f1  jnz     loc_18004A055
0x18004a0f7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004a0fb  lea     rcx, [rsp+290h+Filename]
0x18004a100  mov     rax, rbx
0x18004a103  inc     rax
0x18004a106  cmp     [rcx+rax*2], di
0x18004a10a  jnz     short loc_18004A103
0x18004a10c  mov     rcx, [rsp+290h+var_240]; hKey
0x18004a111  lea     eax, ds:2[rax*2]
0x18004a118  mov     [rsp+290h+samDesired], eax; cbData
0x18004a11c  mov     r9d, 1; dwType
0x18004a122  lea     rax, [rsp+290h+Filename]
0x18004a127  xor     r8d, r8d; Reserved
0x18004a12a  xor     edx, edx; lpValueName
0x18004a12c  mov     [rsp+290h+phkResult], rax; lpData
0x18004a131  call    cs:__imp_RegSetValueExW
0x18004a137  test    eax, eax
0x18004a139  jnz     loc_18004A055
0x18004a13f  lea     rcx, ?g_wszRV_THREADING@@3PAGA; "Both"
0x18004a146  inc     rbx
0x18004a149  cmp     [rcx+rbx*2], di
0x18004a14d  jnz     short loc_18004A146
0x18004a14f  lea     eax, ds:2[rbx*2]
0x18004a156  mov     r9d, 1; dwType
0x18004a15c  mov     [rsp+290h+samDesired], eax; cbData
0x18004a160  lea     rdx, ?g_wszRN_THREADING@@3PAGA; "ThreadingModel"
0x18004a167  mov     [rsp+290h+phkResult], rcx; lpData
0x18004a16c  xor     r8d, r8d; Reserved
0x18004a16f  mov     rcx, [rsp+290h+var_240]; hKey
0x18004a174  call    cs:__imp_RegSetValueExW
0x18004a17a  test    eax, eax
0x18004a17c  jnz     loc_18004A055
0x18004a182  lea     rcx, [rsp+290h+var_240]; HKEY *
0x18004a187  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x18004a18c  lea     rcx, [rsp+290h+var_238]; HKEY *
0x18004a191  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x18004a196  mov     ebx, edi
0x18004a198  lea     rcx, [rsp+290h+var_240]; HKEY *
0x18004a19d  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x18004a1a2  lea     rcx, [rsp+290h+var_238]; HKEY *
0x18004a1a7  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x18004a1ac  lea     rcx, [rsp+290h+hKey]; HKEY *
0x18004a1b1  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x18004a1b6  mov     eax, ebx
0x18004a1b8  mov     rcx, [rbp+190h+var_10]
0x18004a1bf  xor     rcx, rsp; StackCookie
0x18004a1c2  call    __security_check_cookie
0x18004a1c7  lea     r11, [rsp+290h+var_s0]
0x18004a1cf  mov     rbx, [r11+10h]
0x18004a1d3  mov     rdi, [r11+18h]
0x18004a1d7  mov     rsp, r11
0x18004a1da  pop     rbp
0x18004a1db  retn
```
