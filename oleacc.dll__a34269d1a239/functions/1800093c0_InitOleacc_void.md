# InitOleacc(void)

- ea: `0x1800093c0`
- end: `0x18000962b`
- name: `?InitOleacc@@YAHXZ`
- size: `619`
- prototype: `__int64(void)`
- caller_count: `18`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180006720`
- `0x180007870`
- `0x1800079d0`
- `0x18000aa10`
- `0x18000b360`
- `0x1800127b0`
- `0x180014480`
- `0x180015320`
- `0x180017360`
- `0x1800188d0`
- `0x1800465d0`
- `0x180046650`
- `0x1800466a0`
- `0x1800466f0`
- `0x180046740`
- `0x180046790`
- `0x1800467e0`
- `0x180046830`

## callees

- `0x1800093c0`
- `0x180009634`
- `0x18001e4c0`
- `0x18001e610`
- `0x180046880`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000941a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000942c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009446`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009460`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800095f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009608`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000941a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000942c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009446`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009460`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800095f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009608`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180009588`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800095bb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180009588`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800095bb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000954a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000954a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800095cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800095e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800095cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800095e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800094e5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800094e5`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000947b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000947b`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x1800094ad`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x1800094ad`

## string_xrefs

- `0x1800094d7`: `Interface\{618736E0-3C3D-11CF-810C-00AA00389B71}\ProxyStubClsid32`
- `0x180009459`: `NTDLL.DLL`
- `0x180009474`: `OLEAUT32.DLL`
- `0x180009409`: `USER32.DLL`
- `0x18000943f`: `api-ms-win-core-memory-l1-1-2.DLL`
- `0x180009420`: `api-ms-win-core-libraryloader-l1-2-0.DLL`
- `0x1800095eb`: `KERNEL32.DLL`
- `0x180009601`: `KERNEL32.DLL`

## pseudocode

```c
__int64 InitOleacc(void)
{
  const struct ImportInfo *v1; // rdx
  int v2; // r8d
  unsigned int i; // ebx
  const WCHAR *v4; // rcx
  unsigned __int64 v5; // rdi
  ATOM v6; // ax
  DWORD Type; // [rsp+30h] [rbp-99h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-91h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-89h] BYREF
  HINSTANCE ModuleHandleW; // [rsp+48h] [rbp-81h] BYREF
  HMODULE v11; // [rsp+50h] [rbp-79h]
  HMODULE v12; // [rsp+58h] [rbp-71h]
  HMODULE v13; // [rsp+60h] [rbp-69h]
  BYTE Data[2]; // [rsp+70h] [rbp-59h] BYREF
  __int128 v15; // [rsp+72h] [rbp-57h]
  __int128 v16; // [rsp+82h] [rbp-47h]
  __int128 v17; // [rsp+92h] [rbp-37h]
  __int128 v18; // [rsp+A2h] [rbp-27h]
  __int128 v19; // [rsp+B2h] [rbp-17h]
  __int128 v20; // [rsp+C2h] [rbp-7h]
  _BYTE v21[30]; // [rsp+D2h] [rbp+9h] BYREF

  if ( !g_fInitedOleacc )
  {
    g_fInitedOleacc = 1;
    ModuleHandleW = GetModuleHandleW(L"USER32.DLL");
    v11 = GetModuleHandleW(L"api-ms-win-core-libraryloader-l1-2-0.DLL");
    if ( !v11 )
      v11 = GetModuleHandleW(L"KERNEL32.DLL");
    v12 = GetModuleHandleW(L"api-ms-win-core-memory-l1-1-2.DLL");
    if ( !v12 )
      v12 = GetModuleHandleW(L"KERNEL32.DLL");
    v13 = GetModuleHandleW(L"NTDLL.DLL");
    ImportFromModule(&ModuleHandleW, v1, v2);
    LoadLibraryW(L"OLEAUT32.DLL");
    for ( i = 0; i < 0x20; ++i )
    {
      v4 = off_180052380[i];
      v5 = 2LL * (int)i;
      if ( v4 )
      {
        v6 = GlobalAddAtomW(v4);
      }
      else
      {
        if ( v5 >= 0x40 )
          _report_rangecheckfailure();
        v6 = 0;
      }
      *(_WORD *)((char *)&rgAtomClasses + v5) = v6;
    }
    hKey = 0;
    if ( !RegOpenKeyExW(
            HKEY_CLASSES_ROOT,
            L"Interface\\{618736E0-3C3D-11CF-810C-00AA00389B71}\\ProxyStubClsid32",
            0,
            0x20019u,
            &hKey) )
    {
      Type = 0;
      memset(v21, 0, sizeof(v21));
      *(_WORD *)Data = 0;
      cbData = 128;
      v15 = 0;
      v16 = 0;
      v17 = 0;
      v18 = 0;
      v19 = 0;
      v20 = 0;
      if ( !RegQueryValueExW(hKey, 0, 0, &Type, Data, &cbData) && Type == 1 )
      {
        *(_WORD *)&v21[28] = 0;
        if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)Data, -1, L"{00020424-0000-0000-C000-000000000046}", -1) == 2
          || CompareStringW(0x7Fu, 1u, (PCNZWCH)Data, -1, L"{03022430-ABC4-11D0-BDE2-00AA001A1953}", -1) == 2 )
        {
          RegCloseKey(hKey);
          return 1;
        }
      }
      RegCloseKey(hKey);
    }
    Oleacc_DllRegisterServer();
  }
  return 1;
}

```

## disassembly

```asm
0x1800093c0  push    rbp
0x1800093c2  push    rbx
0x1800093c3  push    rsi
0x1800093c4  push    rdi
0x1800093c5  push    r14
0x1800093c7  lea     rbp, [rsp-37h]
0x1800093cc  sub     rsp, 100h
0x1800093d3  mov     rax, cs:__security_cookie
0x1800093da  xor     rax, rsp
0x1800093dd  mov     [rbp+57h+var_30], rax
0x1800093e1  cmp     cs:?g_fInitedOleacc@@3HA, 0; int g_fInitedOleacc
0x1800093e8  jz      short loc_180009409
0x1800093ea  mov     eax, 1
0x1800093ef  mov     rcx, [rbp+57h+var_30]
0x1800093f3  xor     rcx, rsp; StackCookie
0x1800093f6  call    __security_check_cookie
0x1800093fb  add     rsp, 100h
0x180009402  pop     r14
0x180009404  pop     rdi
0x180009405  pop     rsi
0x180009406  pop     rbx
0x180009407  pop     rbp
0x180009408  retn
0x180009409  lea     rcx, aUser32Dll_0; "USER32.DLL"
0x180009410  mov     cs:?g_fInitedOleacc@@3HA, 1; int g_fInitedOleacc
0x18000941a  call    cs:__imp_GetModuleHandleW
0x180009420  lea     rcx, aApiMsWinCoreLi_1; "api-ms-win-core-libraryloader-l1-2-0.DL"...
0x180009427  mov     [rsp+120h+var_D8], rax
0x18000942c  call    cs:__imp_GetModuleHandleW
0x180009432  mov     [rbp+57h+var_D0], rax
0x180009436  test    rax, rax
0x180009439  jz      loc_1800095EB
0x18000943f  lea     rcx, aApiMsWinCoreMe_0; "api-ms-win-core-memory-l1-1-2.DLL"
0x180009446  call    cs:__imp_GetModuleHandleW
0x18000944c  mov     [rbp+57h+var_C8], rax
0x180009450  test    rax, rax
0x180009453  jz      loc_180009601
0x180009459  lea     rcx, aNtdllDll_0; "NTDLL.DLL"
0x180009460  call    cs:__imp_GetModuleHandleW
0x180009466  lea     rcx, [rsp+120h+var_D8]; HINSTANCE *
0x18000946b  mov     [rbp+57h+var_C0], rax
0x18000946f  call    ?ImportFromModule@@YAXPEAPEAUHINSTANCE__@@PEBUImportInfo@@H@Z; ImportFromModule(HINSTANCE__ * *,ImportInfo const *,int)
0x180009474  lea     rcx, LibFileName; "OLEAUT32.DLL"
0x18000947b  call    cs:__imp_LoadLibraryW
0x180009481  xor     r14d, r14d
0x180009484  lea     rsi, __ImageBase
0x18000948b  mov     ebx, r14d
0x18000948e  xchg    ax, ax
0x180009490  cmp     ebx, 20h ; ' '
0x180009493  jnb     short loc_1800094BF
0x180009495  movsxd  rax, ebx
0x180009498  mov     rcx, ds:rva off_180052380[rsi+rax*8]; lpString
0x1800094a0  lea     rdi, [rax+rax]
0x1800094a4  test    rcx, rcx
0x1800094a7  jz      loc_180009617
0x1800094ad  call    cs:__imp_GlobalAddAtomW
0x1800094b3  mov     [rdi+rsi+61C60h], ax
0x1800094bb  inc     ebx
0x1800094bd  jmp     short loc_180009490
0x1800094bf  lea     rax, [rsp+120h+hKey]
0x1800094c4  mov     [rsp+120h+hKey], r14
0x1800094c9  mov     r9d, 20019h; samDesired
0x1800094cf  mov     [rsp+120h+phkResult], rax; phkResult
0x1800094d4  xor     r8d, r8d; ulOptions
0x1800094d7  lea     rdx, SubKey; "Interface\\{618736E0-3C3D-11CF-810C-00A"...
0x1800094de  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800094e5  call    cs:__imp_RegOpenKeyExW
0x1800094eb  test    eax, eax
0x1800094ed  jnz     loc_1800095D1
0x1800094f3  mov     rcx, [rsp+120h+hKey]; hKey
0x1800094f8  lea     rax, [rsp+120h+cbData]
0x1800094fd  xorps   xmm0, xmm0
0x180009500  mov     [rsp+120h+lpcbData], rax; lpcbData
0x180009505  lea     rax, [rbp+57h+Data]
0x180009509  mov     [rsp+120h+Type], r14d
0x18000950e  movups  [rbp+57h+var_4E], xmm0
0x180009512  lea     r9, [rsp+120h+Type]; lpType
0x180009517  mov     [rsp+120h+phkResult], rax; lpData
0x18000951c  xor     r8d, r8d; lpReserved
0x18000951f  mov     word ptr [rbp+57h+Data], r14w
0x180009524  xor     edx, edx; lpValueName
0x180009526  mov     [rsp+120h+cbData], 80h
0x18000952e  movups  [rbp+57h+var_AE], xmm0
0x180009532  movups  [rbp+57h+var_9E], xmm0
0x180009536  movups  [rbp+57h+var_8E], xmm0
0x18000953a  movups  [rbp+57h+var_7E], xmm0
0x18000953e  movups  [rbp+57h+var_6E], xmm0
0x180009542  movups  [rbp+57h+var_5E], xmm0
0x180009546  movups  [rbp+57h+var_4E+0Eh], xmm0
0x18000954a  call    cs:__imp_RegQueryValueExW
0x180009550  test    eax, eax
0x180009552  jnz     short loc_1800095C6
0x180009554  cmp     [rsp+120h+Type], 1
0x180009559  jnz     short loc_1800095C6
0x18000955b  lea     rax, a00020424000000; "{00020424-0000-0000-C000-000000000046}"
0x180009562  mov     dword ptr [rsp+120h+lpcbData], 0FFFFFFFFh; cchCount2
0x18000956a  mov     r9d, 0FFFFFFFFh; cchCount1
0x180009570  mov     [rsp+120h+phkResult], rax; lpString2
0x180009575  lea     r8, [rbp+57h+Data]; lpString1
0x180009579  mov     [rbp+57h+var_32], r14w
0x18000957e  mov     edx, 1; dwCmpFlags
0x180009583  mov     ecx, 7Fh; Locale
0x180009588  call    cs:__imp_CompareStringW
0x18000958e  cmp     eax, 2
0x180009591  jz      short loc_1800095DB
0x180009593  lea     rax, a03022430Abc411; "{03022430-ABC4-11D0-BDE2-00AA001A1953}"
0x18000959a  mov     dword ptr [rsp+120h+lpcbData], 0FFFFFFFFh; cchCount2
0x1800095a2  mov     r9d, 0FFFFFFFFh; cchCount1
0x1800095a8  mov     [rsp+120h+phkResult], rax; lpString2
0x1800095ad  lea     r8, [rbp+57h+Data]; lpString1
0x1800095b1  mov     edx, 1; dwCmpFlags
0x1800095b6  mov     ecx, 7Fh; Locale
0x1800095bb  call    cs:__imp_CompareStringW
0x1800095c1  cmp     eax, 2
0x1800095c4  jz      short loc_1800095DB
0x1800095c6  mov     rcx, [rsp+120h+hKey]; hKey
0x1800095cb  call    cs:__imp_RegCloseKey
0x1800095d1  call    Oleacc_DllRegisterServer
0x1800095d6  jmp     loc_1800093EA
0x1800095db  mov     rcx, [rsp+120h+hKey]; hKey
0x1800095e0  call    cs:__imp_RegCloseKey
0x1800095e6  jmp     loc_1800093EA
0x1800095eb  lea     rcx, aKernel32Dll; "KERNEL32.DLL"
0x1800095f2  call    cs:__imp_GetModuleHandleW
0x1800095f8  mov     [rbp+57h+var_D0], rax
0x1800095fc  jmp     loc_18000943F
0x180009601  lea     rcx, aKernel32Dll; "KERNEL32.DLL"
0x180009608  call    cs:__imp_GetModuleHandleW
0x18000960e  mov     [rbp+57h+var_C8], rax
0x180009612  jmp     loc_180009459
0x180009617  cmp     rdi, 40h ; '@'
0x18000961b  jnb     short loc_180009625
0x18000961d  mov     eax, r14d
0x180009620  jmp     loc_1800094B3
0x180009625  call    __report_rangecheckfailure
```
