# SDTIMetaDataRegisterServer

- ea: `0x1800400dc`
- end: `0x1800402f0`
- name: `SDTIMetaDataRegisterServer`
- size: `532`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800155d0`

## callees

- `0x18003f894`
- `0x1800400dc`
- `0x180055880`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18004015f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18004015f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800401c1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800401fd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800401c1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800401fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040139`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040139`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040245`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040288`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040245`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040288`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18004017f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18004017f`

## string_xrefs

- `0x180040121`: `SOFTWARE\Classes\CLSID`
- `0x180040274`: `ThreadingModel`

## pseudocode

```c
__int64 SDTIMetaDataRegisterServer()
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
    v1 = RegDeleteTreeW(hKey[0], L"{22EE26E5-2289-11d2-8F43-00C04FC2E0C7}");
    if ( v1 < 0 )
      goto LABEL_14;
    if ( !RegCreateKeyExW(hKey[0], L"{22EE26E5-2289-11d2-8F43-00C04FC2E0C7}", 0, 0, 0, 0xF003Fu, 0, &v5, 0)
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
0x1800400dc  mov     [rsp-8+arg_0], rbx
0x1800400e1  mov     [rsp-8+arg_8], rdi
0x1800400e6  push    rbp
0x1800400e7  lea     rbp, [rsp-190h]
0x1800400ef  sub     rsp, 290h
0x1800400f6  mov     rax, cs:__security_cookie
0x1800400fd  xor     rax, rsp
0x180040100  mov     [rbp+190h+var_10], rax
0x180040107  xor     edi, edi
0x180040109  lea     rax, [rsp+290h+hKey]
0x18004010e  mov     r9d, 0F003Fh; samDesired
0x180040114  mov     [rsp+290h+hKey], rdi
0x180040119  xor     r8d, r8d; ulOptions
0x18004011c  mov     [rsp+290h+var_238], rdi
0x180040121  lea     rdx, ?g_wszRP_COMCLSIDS@@3PAGA; "SOFTWARE\\Classes\\CLSID"
0x180040128  mov     [rsp+290h+var_240], rdi
0x18004012d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180040134  mov     [rsp+290h+phkResult], rax; phkResult
0x180040139  call    cs:__imp_RegOpenKeyExW
0x18004013f  test    eax, eax
0x180040141  jz      short loc_18004014D
0x180040143  mov     eax, 8000FFFFh
0x180040148  jmp     loc_1800402CC
0x18004014d  mov     rcx, cs:?g_hModule@@3PEAUHINSTANCE__@@EA; hModule
0x180040154  lea     rdx, [rsp+290h+Filename]; lpFilename
0x180040159  mov     r8d, 105h; nSize
0x18004015f  call    cs:__imp_GetModuleFileNameW
0x180040165  test    eax, eax
0x180040167  jnz     short loc_180040173
0x180040169  mov     ebx, 8000FFFFh
0x18004016e  jmp     loc_1800402AC
0x180040173  mov     rcx, [rsp+290h+hKey]; hKey
0x180040178  lea     rdx, a22ee26e5228911; "{22EE26E5-2289-11d2-8F43-00C04FC2E0C7}"
0x18004017f  call    cs:__imp_RegDeleteTreeW
0x180040185  mov     ebx, eax
0x180040187  test    eax, eax
0x180040189  js      loc_1800402AC
0x18004018f  mov     rcx, [rsp+290h+hKey]; hKey
0x180040194  lea     rax, [rsp+290h+var_238]
0x180040199  mov     [rsp+290h+lpdwDisposition], rdi; lpdwDisposition
0x18004019e  lea     rdx, a22ee26e5228911; "{22EE26E5-2289-11d2-8F43-00C04FC2E0C7}"
0x1800401a5  mov     [rsp+290h+var_258], rax; phkResult
0x1800401aa  xor     r9d, r9d; lpClass
0x1800401ad  mov     [rsp+290h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800401b2  xor     r8d, r8d; Reserved
0x1800401b5  mov     [rsp+290h+samDesired], 0F003Fh; samDesired
0x1800401bd  mov     dword ptr [rsp+290h+phkResult], edi; dwOptions
0x1800401c1  call    cs:__imp_RegCreateKeyExW
0x1800401c7  test    eax, eax
0x1800401c9  jnz     short loc_180040169
0x1800401cb  mov     rcx, [rsp+290h+var_238]; hKey
0x1800401d0  lea     rax, [rsp+290h+var_240]
0x1800401d5  mov     [rsp+290h+lpdwDisposition], rdi; lpdwDisposition
0x1800401da  lea     rdx, ?g_wszRK_IPS32@@3PAGA; "InprocServer32"
0x1800401e1  mov     [rsp+290h+var_258], rax; phkResult
0x1800401e6  xor     r9d, r9d; lpClass
0x1800401e9  mov     [rsp+290h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800401ee  xor     r8d, r8d; Reserved
0x1800401f1  mov     [rsp+290h+samDesired], 0F003Fh; samDesired
0x1800401f9  mov     dword ptr [rsp+290h+phkResult], edi; dwOptions
0x1800401fd  call    cs:__imp_RegCreateKeyExW
0x180040203  test    eax, eax
0x180040205  jnz     loc_180040169
0x18004020b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004020f  lea     rcx, [rsp+290h+Filename]
0x180040214  mov     rax, rbx
0x180040217  inc     rax
0x18004021a  cmp     [rcx+rax*2], di
0x18004021e  jnz     short loc_180040217
0x180040220  mov     rcx, [rsp+290h+var_240]; hKey
0x180040225  lea     eax, ds:2[rax*2]
0x18004022c  mov     [rsp+290h+samDesired], eax; cbData
0x180040230  mov     r9d, 1; dwType
0x180040236  lea     rax, [rsp+290h+Filename]
0x18004023b  xor     r8d, r8d; Reserved
0x18004023e  xor     edx, edx; lpValueName
0x180040240  mov     [rsp+290h+phkResult], rax; lpData
0x180040245  call    cs:__imp_RegSetValueExW
0x18004024b  test    eax, eax
0x18004024d  jnz     loc_180040169
0x180040253  lea     rcx, ?g_wszRV_THREADING@@3PAGA; "Both"
0x18004025a  inc     rbx
0x18004025d  cmp     [rcx+rbx*2], di
0x180040261  jnz     short loc_18004025A
0x180040263  lea     eax, ds:2[rbx*2]
0x18004026a  mov     r9d, 1; dwType
0x180040270  mov     [rsp+290h+samDesired], eax; cbData
0x180040274  lea     rdx, ?g_wszRN_THREADING@@3PAGA; "ThreadingModel"
0x18004027b  mov     [rsp+290h+phkResult], rcx; lpData
0x180040280  xor     r8d, r8d; Reserved
0x180040283  mov     rcx, [rsp+290h+var_240]; hKey
0x180040288  call    cs:__imp_RegSetValueExW
0x18004028e  test    eax, eax
0x180040290  jnz     loc_180040169
0x180040296  lea     rcx, [rsp+290h+var_240]; HKEY *
0x18004029b  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x1800402a0  lea     rcx, [rsp+290h+var_238]; HKEY *
0x1800402a5  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x1800402aa  mov     ebx, edi
0x1800402ac  lea     rcx, [rsp+290h+var_240]; HKEY *
0x1800402b1  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x1800402b6  lea     rcx, [rsp+290h+var_238]; HKEY *
0x1800402bb  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x1800402c0  lea     rcx, [rsp+290h+hKey]; HKEY *
0x1800402c5  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x1800402ca  mov     eax, ebx
0x1800402cc  mov     rcx, [rbp+190h+var_10]
0x1800402d3  xor     rcx, rsp; StackCookie
0x1800402d6  call    __security_check_cookie
0x1800402db  lea     r11, [rsp+290h+var_s0]
0x1800402e3  mov     rbx, [r11+10h]
0x1800402e7  mov     rdi, [r11+18h]
0x1800402eb  mov     rsp, r11
0x1800402ee  pop     rbp
0x1800402ef  retn
```
