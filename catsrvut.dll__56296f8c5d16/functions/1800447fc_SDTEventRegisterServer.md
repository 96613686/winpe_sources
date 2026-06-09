# SDTEventRegisterServer

- ea: `0x1800447fc`
- end: `0x180044a10`
- name: `SDTEventRegisterServer`
- size: `532`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800155d0`

## callees

- `0x18003f894`
- `0x1800447fc`
- `0x180055880`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18004487f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18004487f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800448e1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004491d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800448e1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004491d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044859`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044859`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180044965`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800449a8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180044965`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800449a8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18004489f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18004489f`

## string_xrefs

- `0x180044841`: `SOFTWARE\Classes\CLSID`
- `0x180044994`: `ThreadingModel`

## pseudocode

```c
__int64 SDTEventRegisterServer()
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
    v1 = RegDeleteTreeW(hKey[0], L"{6131A8EC-78CE-11d2-A3F2-3078302C2030}");
    if ( v1 < 0 )
      goto LABEL_14;
    if ( !RegCreateKeyExW(hKey[0], L"{6131A8EC-78CE-11d2-A3F2-3078302C2030}", 0, 0, 0, 0xF003Fu, 0, &v5, 0)
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
0x1800447fc  mov     [rsp-8+arg_0], rbx
0x180044801  mov     [rsp-8+arg_8], rdi
0x180044806  push    rbp
0x180044807  lea     rbp, [rsp-190h]
0x18004480f  sub     rsp, 290h
0x180044816  mov     rax, cs:__security_cookie
0x18004481d  xor     rax, rsp
0x180044820  mov     [rbp+190h+var_10], rax
0x180044827  xor     edi, edi
0x180044829  lea     rax, [rsp+290h+hKey]
0x18004482e  mov     r9d, 0F003Fh; samDesired
0x180044834  mov     [rsp+290h+hKey], rdi
0x180044839  xor     r8d, r8d; ulOptions
0x18004483c  mov     [rsp+290h+var_238], rdi
0x180044841  lea     rdx, ?g_wszRP_COMCLSIDS@@3PAGA; "SOFTWARE\\Classes\\CLSID"
0x180044848  mov     [rsp+290h+var_240], rdi
0x18004484d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180044854  mov     [rsp+290h+phkResult], rax; phkResult
0x180044859  call    cs:__imp_RegOpenKeyExW
0x18004485f  test    eax, eax
0x180044861  jz      short loc_18004486D
0x180044863  mov     eax, 8000FFFFh
0x180044868  jmp     loc_1800449EC
0x18004486d  mov     rcx, cs:?g_hModule@@3PEAUHINSTANCE__@@EA; hModule
0x180044874  lea     rdx, [rsp+290h+Filename]; lpFilename
0x180044879  mov     r8d, 105h; nSize
0x18004487f  call    cs:__imp_GetModuleFileNameW
0x180044885  test    eax, eax
0x180044887  jnz     short loc_180044893
0x180044889  mov     ebx, 8000FFFFh
0x18004488e  jmp     loc_1800449CC
0x180044893  mov     rcx, [rsp+290h+hKey]; hKey
0x180044898  lea     rdx, a6131a8ec78ce11; "{6131A8EC-78CE-11d2-A3F2-3078302C2030}"
0x18004489f  call    cs:__imp_RegDeleteTreeW
0x1800448a5  mov     ebx, eax
0x1800448a7  test    eax, eax
0x1800448a9  js      loc_1800449CC
0x1800448af  mov     rcx, [rsp+290h+hKey]; hKey
0x1800448b4  lea     rax, [rsp+290h+var_238]
0x1800448b9  mov     [rsp+290h+lpdwDisposition], rdi; lpdwDisposition
0x1800448be  lea     rdx, a6131a8ec78ce11; "{6131A8EC-78CE-11d2-A3F2-3078302C2030}"
0x1800448c5  mov     [rsp+290h+var_258], rax; phkResult
0x1800448ca  xor     r9d, r9d; lpClass
0x1800448cd  mov     [rsp+290h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800448d2  xor     r8d, r8d; Reserved
0x1800448d5  mov     [rsp+290h+samDesired], 0F003Fh; samDesired
0x1800448dd  mov     dword ptr [rsp+290h+phkResult], edi; dwOptions
0x1800448e1  call    cs:__imp_RegCreateKeyExW
0x1800448e7  test    eax, eax
0x1800448e9  jnz     short loc_180044889
0x1800448eb  mov     rcx, [rsp+290h+var_238]; hKey
0x1800448f0  lea     rax, [rsp+290h+var_240]
0x1800448f5  mov     [rsp+290h+lpdwDisposition], rdi; lpdwDisposition
0x1800448fa  lea     rdx, ?g_wszRK_IPS32@@3PAGA; "InprocServer32"
0x180044901  mov     [rsp+290h+var_258], rax; phkResult
0x180044906  xor     r9d, r9d; lpClass
0x180044909  mov     [rsp+290h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18004490e  xor     r8d, r8d; Reserved
0x180044911  mov     [rsp+290h+samDesired], 0F003Fh; samDesired
0x180044919  mov     dword ptr [rsp+290h+phkResult], edi; dwOptions
0x18004491d  call    cs:__imp_RegCreateKeyExW
0x180044923  test    eax, eax
0x180044925  jnz     loc_180044889
0x18004492b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004492f  lea     rcx, [rsp+290h+Filename]
0x180044934  mov     rax, rbx
0x180044937  inc     rax
0x18004493a  cmp     [rcx+rax*2], di
0x18004493e  jnz     short loc_180044937
0x180044940  mov     rcx, [rsp+290h+var_240]; hKey
0x180044945  lea     eax, ds:2[rax*2]
0x18004494c  mov     [rsp+290h+samDesired], eax; cbData
0x180044950  mov     r9d, 1; dwType
0x180044956  lea     rax, [rsp+290h+Filename]
0x18004495b  xor     r8d, r8d; Reserved
0x18004495e  xor     edx, edx; lpValueName
0x180044960  mov     [rsp+290h+phkResult], rax; lpData
0x180044965  call    cs:__imp_RegSetValueExW
0x18004496b  test    eax, eax
0x18004496d  jnz     loc_180044889
0x180044973  lea     rcx, ?g_wszRV_THREADING@@3PAGA; "Both"
0x18004497a  inc     rbx
0x18004497d  cmp     [rcx+rbx*2], di
0x180044981  jnz     short loc_18004497A
0x180044983  lea     eax, ds:2[rbx*2]
0x18004498a  mov     r9d, 1; dwType
0x180044990  mov     [rsp+290h+samDesired], eax; cbData
0x180044994  lea     rdx, ?g_wszRN_THREADING@@3PAGA; "ThreadingModel"
0x18004499b  mov     [rsp+290h+phkResult], rcx; lpData
0x1800449a0  xor     r8d, r8d; Reserved
0x1800449a3  mov     rcx, [rsp+290h+var_240]; hKey
0x1800449a8  call    cs:__imp_RegSetValueExW
0x1800449ae  test    eax, eax
0x1800449b0  jnz     loc_180044889
0x1800449b6  lea     rcx, [rsp+290h+var_240]; HKEY *
0x1800449bb  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x1800449c0  lea     rcx, [rsp+290h+var_238]; HKEY *
0x1800449c5  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x1800449ca  mov     ebx, edi
0x1800449cc  lea     rcx, [rsp+290h+var_240]; HKEY *
0x1800449d1  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x1800449d6  lea     rcx, [rsp+290h+var_238]; HKEY *
0x1800449db  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x1800449e0  lea     rcx, [rsp+290h+hKey]; HKEY *
0x1800449e5  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x1800449ea  mov     eax, ebx
0x1800449ec  mov     rcx, [rbp+190h+var_10]
0x1800449f3  xor     rcx, rsp; StackCookie
0x1800449f6  call    __security_check_cookie
0x1800449fb  lea     r11, [rsp+290h+var_s0]
0x180044a03  mov     rbx, [r11+10h]
0x180044a07  mov     rdi, [r11+18h]
0x180044a0b  mov     rsp, r11
0x180044a0e  pop     rbp
0x180044a0f  retn
```
