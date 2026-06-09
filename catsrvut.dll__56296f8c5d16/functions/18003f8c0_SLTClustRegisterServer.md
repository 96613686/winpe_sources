# SLTClustRegisterServer

- ea: `0x18003f8c0`
- end: `0x18003fad4`
- name: `SLTClustRegisterServer`
- size: `532`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800155d0`

## callees

- `0x18003f894`
- `0x18003f8c0`
- `0x180055880`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18003f943`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18003f943`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003f9a5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003f9e1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003f9a5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003f9e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f91d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f91d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003fa29`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003fa6c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003fa29`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003fa6c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003f963`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003f963`

## string_xrefs

- `0x18003f905`: `SOFTWARE\Classes\CLSID`
- `0x18003fa58`: `ThreadingModel`

## pseudocode

```c
__int64 SLTClustRegisterServer()
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
    v1 = RegDeleteTreeW(hKey[0], L"{94426DE2-3211-11d2-A0DB-00C04F8EDCEE}");
    if ( v1 < 0 )
      goto LABEL_14;
    if ( !RegCreateKeyExW(hKey[0], L"{94426DE2-3211-11d2-A0DB-00C04F8EDCEE}", 0, 0, 0, 0xF003Fu, 0, &v5, 0)
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
0x18003f8c0  mov     [rsp-8+arg_0], rbx
0x18003f8c5  mov     [rsp-8+arg_8], rdi
0x18003f8ca  push    rbp
0x18003f8cb  lea     rbp, [rsp-190h]
0x18003f8d3  sub     rsp, 290h
0x18003f8da  mov     rax, cs:__security_cookie
0x18003f8e1  xor     rax, rsp
0x18003f8e4  mov     [rbp+190h+var_10], rax
0x18003f8eb  xor     edi, edi
0x18003f8ed  lea     rax, [rsp+290h+hKey]
0x18003f8f2  mov     r9d, 0F003Fh; samDesired
0x18003f8f8  mov     [rsp+290h+hKey], rdi
0x18003f8fd  xor     r8d, r8d; ulOptions
0x18003f900  mov     [rsp+290h+var_238], rdi
0x18003f905  lea     rdx, ?g_wszRP_COMCLSIDS@@3PAGA; "SOFTWARE\\Classes\\CLSID"
0x18003f90c  mov     [rsp+290h+var_240], rdi
0x18003f911  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003f918  mov     [rsp+290h+phkResult], rax; phkResult
0x18003f91d  call    cs:__imp_RegOpenKeyExW
0x18003f923  test    eax, eax
0x18003f925  jz      short loc_18003F931
0x18003f927  mov     eax, 8000FFFFh
0x18003f92c  jmp     loc_18003FAB0
0x18003f931  mov     rcx, cs:?g_hModule@@3PEAUHINSTANCE__@@EA; hModule
0x18003f938  lea     rdx, [rsp+290h+Filename]; lpFilename
0x18003f93d  mov     r8d, 105h; nSize
0x18003f943  call    cs:__imp_GetModuleFileNameW
0x18003f949  test    eax, eax
0x18003f94b  jnz     short loc_18003F957
0x18003f94d  mov     ebx, 8000FFFFh
0x18003f952  jmp     loc_18003FA90
0x18003f957  mov     rcx, [rsp+290h+hKey]; hKey
0x18003f95c  lea     rdx, a94426de2321111; "{94426DE2-3211-11d2-A0DB-00C04F8EDCEE}"
0x18003f963  call    cs:__imp_RegDeleteTreeW
0x18003f969  mov     ebx, eax
0x18003f96b  test    eax, eax
0x18003f96d  js      loc_18003FA90
0x18003f973  mov     rcx, [rsp+290h+hKey]; hKey
0x18003f978  lea     rax, [rsp+290h+var_238]
0x18003f97d  mov     [rsp+290h+lpdwDisposition], rdi; lpdwDisposition
0x18003f982  lea     rdx, a94426de2321111; "{94426DE2-3211-11d2-A0DB-00C04F8EDCEE}"
0x18003f989  mov     [rsp+290h+var_258], rax; phkResult
0x18003f98e  xor     r9d, r9d; lpClass
0x18003f991  mov     [rsp+290h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18003f996  xor     r8d, r8d; Reserved
0x18003f999  mov     [rsp+290h+samDesired], 0F003Fh; samDesired
0x18003f9a1  mov     dword ptr [rsp+290h+phkResult], edi; dwOptions
0x18003f9a5  call    cs:__imp_RegCreateKeyExW
0x18003f9ab  test    eax, eax
0x18003f9ad  jnz     short loc_18003F94D
0x18003f9af  mov     rcx, [rsp+290h+var_238]; hKey
0x18003f9b4  lea     rax, [rsp+290h+var_240]
0x18003f9b9  mov     [rsp+290h+lpdwDisposition], rdi; lpdwDisposition
0x18003f9be  lea     rdx, ?g_wszRK_IPS32@@3PAGA; "InprocServer32"
0x18003f9c5  mov     [rsp+290h+var_258], rax; phkResult
0x18003f9ca  xor     r9d, r9d; lpClass
0x18003f9cd  mov     [rsp+290h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18003f9d2  xor     r8d, r8d; Reserved
0x18003f9d5  mov     [rsp+290h+samDesired], 0F003Fh; samDesired
0x18003f9dd  mov     dword ptr [rsp+290h+phkResult], edi; dwOptions
0x18003f9e1  call    cs:__imp_RegCreateKeyExW
0x18003f9e7  test    eax, eax
0x18003f9e9  jnz     loc_18003F94D
0x18003f9ef  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003f9f3  lea     rcx, [rsp+290h+Filename]
0x18003f9f8  mov     rax, rbx
0x18003f9fb  inc     rax
0x18003f9fe  cmp     [rcx+rax*2], di
0x18003fa02  jnz     short loc_18003F9FB
0x18003fa04  mov     rcx, [rsp+290h+var_240]; hKey
0x18003fa09  lea     eax, ds:2[rax*2]
0x18003fa10  mov     [rsp+290h+samDesired], eax; cbData
0x18003fa14  mov     r9d, 1; dwType
0x18003fa1a  lea     rax, [rsp+290h+Filename]
0x18003fa1f  xor     r8d, r8d; Reserved
0x18003fa22  xor     edx, edx; lpValueName
0x18003fa24  mov     [rsp+290h+phkResult], rax; lpData
0x18003fa29  call    cs:__imp_RegSetValueExW
0x18003fa2f  test    eax, eax
0x18003fa31  jnz     loc_18003F94D
0x18003fa37  lea     rcx, ?g_wszRV_THREADING@@3PAGA; "Both"
0x18003fa3e  inc     rbx
0x18003fa41  cmp     [rcx+rbx*2], di
0x18003fa45  jnz     short loc_18003FA3E
0x18003fa47  lea     eax, ds:2[rbx*2]
0x18003fa4e  mov     r9d, 1; dwType
0x18003fa54  mov     [rsp+290h+samDesired], eax; cbData
0x18003fa58  lea     rdx, ?g_wszRN_THREADING@@3PAGA; "ThreadingModel"
0x18003fa5f  mov     [rsp+290h+phkResult], rcx; lpData
0x18003fa64  xor     r8d, r8d; Reserved
0x18003fa67  mov     rcx, [rsp+290h+var_240]; hKey
0x18003fa6c  call    cs:__imp_RegSetValueExW
0x18003fa72  test    eax, eax
0x18003fa74  jnz     loc_18003F94D
0x18003fa7a  lea     rcx, [rsp+290h+var_240]; HKEY *
0x18003fa7f  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x18003fa84  lea     rcx, [rsp+290h+var_238]; HKEY *
0x18003fa89  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x18003fa8e  mov     ebx, edi
0x18003fa90  lea     rcx, [rsp+290h+var_240]; HKEY *
0x18003fa95  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x18003fa9a  lea     rcx, [rsp+290h+var_238]; HKEY *
0x18003fa9f  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x18003faa4  lea     rcx, [rsp+290h+hKey]; HKEY *
0x18003faa9  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x18003faae  mov     eax, ebx
0x18003fab0  mov     rcx, [rbp+190h+var_10]
0x18003fab7  xor     rcx, rsp; StackCookie
0x18003faba  call    __security_check_cookie
0x18003fabf  lea     r11, [rsp+290h+var_s0]
0x18003fac7  mov     rbx, [r11+10h]
0x18003facb  mov     rdi, [r11+18h]
0x18003facf  mov     rsp, r11
0x18003fad2  pop     rbp
0x18003fad3  retn
```
