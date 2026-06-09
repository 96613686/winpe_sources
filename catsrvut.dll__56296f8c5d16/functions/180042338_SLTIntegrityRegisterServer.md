# SLTIntegrityRegisterServer

- ea: `0x180042338`
- end: `0x18004254c`
- name: `SLTIntegrityRegisterServer`
- size: `532`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800155d0`

## callees

- `0x18003f894`
- `0x180042338`
- `0x180055880`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800423bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800423bb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004241d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180042459`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004241d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180042459`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042395`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042395`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800424a1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800424e4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800424a1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800424e4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800423db`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800423db`

## string_xrefs

- `0x18004237d`: `SOFTWARE\Classes\CLSID`
- `0x1800424d0`: `ThreadingModel`

## pseudocode

```c
__int64 SLTIntegrityRegisterServer()
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
    v1 = RegDeleteTreeW(hKey[0], L"{75C9378A-7E89-11d2-B116-00805FC73204}");
    if ( v1 < 0 )
      goto LABEL_14;
    if ( !RegCreateKeyExW(hKey[0], L"{75C9378A-7E89-11d2-B116-00805FC73204}", 0, 0, 0, 0xF003Fu, 0, &v5, 0)
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
0x180042338  mov     [rsp-8+arg_0], rbx
0x18004233d  mov     [rsp-8+arg_8], rdi
0x180042342  push    rbp
0x180042343  lea     rbp, [rsp-190h]
0x18004234b  sub     rsp, 290h
0x180042352  mov     rax, cs:__security_cookie
0x180042359  xor     rax, rsp
0x18004235c  mov     [rbp+190h+var_10], rax
0x180042363  xor     edi, edi
0x180042365  lea     rax, [rsp+290h+hKey]
0x18004236a  mov     r9d, 0F003Fh; samDesired
0x180042370  mov     [rsp+290h+hKey], rdi
0x180042375  xor     r8d, r8d; ulOptions
0x180042378  mov     [rsp+290h+var_238], rdi
0x18004237d  lea     rdx, ?g_wszRP_COMCLSIDS@@3PAGA; "SOFTWARE\\Classes\\CLSID"
0x180042384  mov     [rsp+290h+var_240], rdi
0x180042389  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180042390  mov     [rsp+290h+phkResult], rax; phkResult
0x180042395  call    cs:__imp_RegOpenKeyExW
0x18004239b  test    eax, eax
0x18004239d  jz      short loc_1800423A9
0x18004239f  mov     eax, 8000FFFFh
0x1800423a4  jmp     loc_180042528
0x1800423a9  mov     rcx, cs:?g_hModule@@3PEAUHINSTANCE__@@EA; hModule
0x1800423b0  lea     rdx, [rsp+290h+Filename]; lpFilename
0x1800423b5  mov     r8d, 105h; nSize
0x1800423bb  call    cs:__imp_GetModuleFileNameW
0x1800423c1  test    eax, eax
0x1800423c3  jnz     short loc_1800423CF
0x1800423c5  mov     ebx, 8000FFFFh
0x1800423ca  jmp     loc_180042508
0x1800423cf  mov     rcx, [rsp+290h+hKey]; hKey
0x1800423d4  lea     rdx, a75c9378a7e8911; "{75C9378A-7E89-11d2-B116-00805FC73204}"
0x1800423db  call    cs:__imp_RegDeleteTreeW
0x1800423e1  mov     ebx, eax
0x1800423e3  test    eax, eax
0x1800423e5  js      loc_180042508
0x1800423eb  mov     rcx, [rsp+290h+hKey]; hKey
0x1800423f0  lea     rax, [rsp+290h+var_238]
0x1800423f5  mov     [rsp+290h+lpdwDisposition], rdi; lpdwDisposition
0x1800423fa  lea     rdx, a75c9378a7e8911; "{75C9378A-7E89-11d2-B116-00805FC73204}"
0x180042401  mov     [rsp+290h+var_258], rax; phkResult
0x180042406  xor     r9d, r9d; lpClass
0x180042409  mov     [rsp+290h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18004240e  xor     r8d, r8d; Reserved
0x180042411  mov     [rsp+290h+samDesired], 0F003Fh; samDesired
0x180042419  mov     dword ptr [rsp+290h+phkResult], edi; dwOptions
0x18004241d  call    cs:__imp_RegCreateKeyExW
0x180042423  test    eax, eax
0x180042425  jnz     short loc_1800423C5
0x180042427  mov     rcx, [rsp+290h+var_238]; hKey
0x18004242c  lea     rax, [rsp+290h+var_240]
0x180042431  mov     [rsp+290h+lpdwDisposition], rdi; lpdwDisposition
0x180042436  lea     rdx, ?g_wszRK_IPS32@@3PAGA; "InprocServer32"
0x18004243d  mov     [rsp+290h+var_258], rax; phkResult
0x180042442  xor     r9d, r9d; lpClass
0x180042445  mov     [rsp+290h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18004244a  xor     r8d, r8d; Reserved
0x18004244d  mov     [rsp+290h+samDesired], 0F003Fh; samDesired
0x180042455  mov     dword ptr [rsp+290h+phkResult], edi; dwOptions
0x180042459  call    cs:__imp_RegCreateKeyExW
0x18004245f  test    eax, eax
0x180042461  jnz     loc_1800423C5
0x180042467  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004246b  lea     rcx, [rsp+290h+Filename]
0x180042470  mov     rax, rbx
0x180042473  inc     rax
0x180042476  cmp     [rcx+rax*2], di
0x18004247a  jnz     short loc_180042473
0x18004247c  mov     rcx, [rsp+290h+var_240]; hKey
0x180042481  lea     eax, ds:2[rax*2]
0x180042488  mov     [rsp+290h+samDesired], eax; cbData
0x18004248c  mov     r9d, 1; dwType
0x180042492  lea     rax, [rsp+290h+Filename]
0x180042497  xor     r8d, r8d; Reserved
0x18004249a  xor     edx, edx; lpValueName
0x18004249c  mov     [rsp+290h+phkResult], rax; lpData
0x1800424a1  call    cs:__imp_RegSetValueExW
0x1800424a7  test    eax, eax
0x1800424a9  jnz     loc_1800423C5
0x1800424af  lea     rcx, ?g_wszRV_THREADING@@3PAGA; "Both"
0x1800424b6  inc     rbx
0x1800424b9  cmp     [rcx+rbx*2], di
0x1800424bd  jnz     short loc_1800424B6
0x1800424bf  lea     eax, ds:2[rbx*2]
0x1800424c6  mov     r9d, 1; dwType
0x1800424cc  mov     [rsp+290h+samDesired], eax; cbData
0x1800424d0  lea     rdx, ?g_wszRN_THREADING@@3PAGA; "ThreadingModel"
0x1800424d7  mov     [rsp+290h+phkResult], rcx; lpData
0x1800424dc  xor     r8d, r8d; Reserved
0x1800424df  mov     rcx, [rsp+290h+var_240]; hKey
0x1800424e4  call    cs:__imp_RegSetValueExW
0x1800424ea  test    eax, eax
0x1800424ec  jnz     loc_1800423C5
0x1800424f2  lea     rcx, [rsp+290h+var_240]; HKEY *
0x1800424f7  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x1800424fc  lea     rcx, [rsp+290h+var_238]; HKEY *
0x180042501  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x180042506  mov     ebx, edi
0x180042508  lea     rcx, [rsp+290h+var_240]; HKEY *
0x18004250d  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x180042512  lea     rcx, [rsp+290h+var_238]; HKEY *
0x180042517  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x18004251c  lea     rcx, [rsp+290h+hKey]; HKEY *
0x180042521  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x180042526  mov     eax, ebx
0x180042528  mov     rcx, [rbp+190h+var_10]
0x18004252f  xor     rcx, rsp; StackCookie
0x180042532  call    __security_check_cookie
0x180042537  lea     r11, [rsp+290h+var_s0]
0x18004253f  mov     rbx, [r11+10h]
0x180042543  mov     rdi, [r11+18h]
0x180042547  mov     rsp, r11
0x18004254a  pop     rbp
0x18004254b  retn
```
