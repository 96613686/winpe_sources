# DllRegisterServer

- ea: `0x1800111b0`
- end: `0x180011465`
- name: `DllRegisterServer`
- size: `693`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800024a0`
- `0x1800095d8`
- `0x18000dd2c`
- `0x18001085c`
- `0x1800111b0`
- `0x180013eb0`
- `0x1800142d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001126f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001126f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800112e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800112e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800112cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800112cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800112f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800112f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800112ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001142c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800112ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001142c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011392`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800113c2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800113ee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001141a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011392`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800113c2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800113ee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001141a`
- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x18001133c`
- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x18001133c`

## string_xrefs

- `0x1800111f2`: `"onecoreuap\\base\\appmodel\\search\\common\\pkmcntrs\\pkmcntrs.cxx"`
- `0x1800112c5`: `msscntrs.dll`
- `0x1800111e6`: `[UtilCommon] MSSCNTRS: DllRegisterServer().`
- `0x180011315`: `SYSTEM\CurrentControlSet\Services\MSSCNTRS\Performance`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  const wchar_t *v0; // r9
  __int64 v1; // rbx
  wchar_t *v2; // rcx
  __int64 v3; // rdx
  wchar_t *v4; // rax
  wchar_t v5; // r8
  wchar_t *v6; // rcx
  const wchar_t *v7; // rcx
  __int64 v8; // r8
  wchar_t *v9; // r9
  HMODULE ModuleHandleW; // rax
  const wchar_t *v11; // rcx
  __int64 v12; // r8
  wchar_t *v13; // r9
  HRESULT ShortPathNameW; // ebx
  __int64 v15; // rax
  unsigned int lpData; // [rsp+20h] [rbp-E0h]
  unsigned int lpDataa; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+28h] [rbp-D8h]
  DWORD cbDataa; // [rsp+28h] [rbp-D8h]
  struct _SECURITY_ATTRIBUTES *v21; // [rsp+30h] [rbp-D0h]
  struct _SECURITY_ATTRIBUTES *v22; // [rsp+30h] [rbp-D0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v24; // [rsp+58h] [rbp-A8h] BYREF
  void **v25; // [rsp+60h] [rbp-A0h] BYREF
  void *Block; // [rsp+68h] [rbp-98h]
  char v27; // [rsp+78h] [rbp-88h] BYREF
  WCHAR szShortPath[264]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t v29[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  WCHAR Filename[264]; // [rsp+4E0h] [rbp+3E0h] BYREF

  hKey = 0;
  v24 = 0;
  SearchIndexerTrace::Information(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmcntrs\\\\pkmcntrs.cxx\"",
    (const wchar_t *)0x276,
    (unsigned int)L"[UtilCommon] MSSCNTRS: DllRegisterServer().",
    v0);
  v1 = 2147483646;
  v2 = *(wchar_t **)(GetRootRegistryKeyName((__int64)&v25) + 8);
  v3 = 260;
  v4 = v29;
  do
  {
    if ( !v1 )
      break;
    v5 = *v2;
    if ( !*v2 )
      break;
    ++v2;
    *v4++ = v5;
    --v1;
    --v3;
  }
  while ( v3 );
  v6 = v4 - 1;
  if ( v3 )
    v6 = v4;
  *v6 = 0;
  v25 = &TLMString<32,32,1024>::`vftable';
  if ( Block && Block != &v27 )
  {
    free(Block);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_56494824>::GetImpl'::`2'::impl);
  }
  StringCchCatW(v29, v3, (wchar_t *)L"\\PerformanceCounters");
  WSearchRegCreateKey(v7, v29, v8, v9, lpData, cbData, v21, &hKey, &v24);
  RegCloseKey(hKey);
  hKey = 0;
  ModuleHandleW = GetModuleHandleW(L"msscntrs.dll");
  if ( ModuleHandleW && GetModuleFileNameW(ModuleHandleW, Filename, 0x104u) || (ShortPathNameW = GetLastError()) == 0 )
  {
    ShortPathNameW = WSearchRegCreateKey(
                       v11,
                       (wchar_t *)L"SYSTEM\\CurrentControlSet\\Services\\MSSCNTRS\\Performance",
                       v12,
                       v13,
                       lpDataa,
                       cbDataa,
                       v22,
                       &hKey,
                       &v24);
    if ( !ShortPathNameW )
    {
      ShortPathNameW = GetShortPathNameW(Filename, szShortPath, 0x104u);
      if ( (unsigned int)(ShortPathNameW - 1) <= 0x103 )
      {
        szShortPath[260] = 0;
        v15 = -1;
        do
          ++v15;
        while ( szShortPath[v15] );
        ShortPathNameW = RegSetValueExW(hKey, L"Library", 0, 1u, (const BYTE *)szShortPath, 2 * v15 + 2);
        if ( !ShortPathNameW )
        {
          ShortPathNameW = RegSetValueExW(hKey, (LPCWSTR)L"Open", 0, 1u, L"Open", 0xAu);
          if ( !ShortPathNameW )
          {
            ShortPathNameW = RegSetValueExW(hKey, (LPCWSTR)L"Close", 0, 1u, L"Close", 0xCu);
            if ( !ShortPathNameW )
              ShortPathNameW = RegSetValueExW(hKey, (LPCWSTR)L"Collect", 0, 1u, L"Collect", 0x10u);
          }
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( ShortPathNameW > 0 )
    return (unsigned __int16)ShortPathNameW | 0x80070000;
  return ShortPathNameW;
}

```

## disassembly

```asm
0x1800111b0  mov     [rsp-8+arg_0], rbx
0x1800111b5  mov     [rsp-8+arg_8], rdi
0x1800111ba  push    rbp
0x1800111bb  lea     rbp, [rsp-600h]
0x1800111c3  sub     rsp, 700h
0x1800111ca  mov     rax, cs:__security_cookie
0x1800111d1  xor     rax, rsp
0x1800111d4  mov     [rbp+600h+var_10], rax
0x1800111db  xor     edi, edi
0x1800111dd  mov     [rsp+700h+hKey], rdi
0x1800111e2  mov     [rsp+700h+var_6A8], edi
0x1800111e6  lea     r8, aUtilcommonMssc_2; "[UtilCommon] MSSCNTRS: DllRegisterServe"...
0x1800111ed  mov     edx, 276h; wchar_t *
0x1800111f2  lea     rcx, aOnecoreuapBase_1; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1800111f9  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x1800111fe  mov     ebx, 7FFFFFFEh
0x180011203  lea     rcx, [rsp+700h+var_6A0]
0x180011208  call    ?GetRootRegistryKeyName@@YA?AV?$TLMString@$0CA@$0CA@$0EAA@@@XZ; GetRootRegistryKeyName(void)
0x18001120d  mov     rcx, [rax+8]
0x180011211  mov     edx, 104h
0x180011216  lea     rax, [rbp+600h+var_430]
0x18001121d  test    rbx, rbx
0x180011220  jz      short loc_180011241
0x180011222  movzx   r8d, word ptr [rcx]
0x180011226  test    r8w, r8w
0x18001122a  jz      short loc_180011241
0x18001122c  add     rcx, 2
0x180011230  mov     [rax], r8w
0x180011234  add     rax, 2
0x180011238  dec     rbx
0x18001123b  sub     rdx, 1
0x18001123f  jnz     short loc_18001121D
0x180011241  lea     rcx, [rax-2]
0x180011245  test    rdx, rdx
0x180011248  cmovnz  rcx, rax
0x18001124c  mov     [rcx], di
0x18001124f  lea     rax, ??_7?$TLMString@$0CA@$0CA@$0EAA@@@6B@; const TLMString<32,32,1024>::`vftable'
0x180011256  mov     [rsp+700h+var_6A0], rax
0x18001125b  mov     rcx, [rsp+700h+Block]; Block
0x180011260  test    rcx, rcx
0x180011263  jz      short loc_180011282
0x180011265  lea     rax, [rsp+700h+var_688]
0x18001126a  cmp     rcx, rax
0x18001126d  jz      short loc_180011282
0x18001126f  call    cs:__imp_free
0x180011275  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56494824@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824> `wil::Feature<__WilFeatureTraits_Feature_56494824>::GetImpl(void)'::`2'::impl
0x18001127c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled(void)
0x180011281  nop
0x180011282  lea     r8, aPerformancecou; "\\PerformanceCounters"
0x180011289  lea     rcx, [rbp+600h+var_430]; wchar_t *
0x180011290  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180011295  lea     rax, [rsp+700h+var_6A8]
0x18001129a  mov     [rsp+700h+var_6C0], rax; unsigned int *
0x18001129f  lea     rax, [rsp+700h+hKey]
0x1800112a4  mov     [rsp+700h+var_6C8], rax; HKEY *
0x1800112a9  lea     rdx, [rbp+600h+var_430]; wchar_t *
0x1800112b0  call    ?WSearchRegCreateKey@@YAJPEAUHKEY__@@PEB_WKPEA_WKKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; WSearchRegCreateKey(HKEY__ *,wchar_t const *,ulong,wchar_t *,ulong,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *)
0x1800112b5  mov     rcx, [rsp+700h+hKey]; hKey
0x1800112ba  call    cs:__imp_RegCloseKey
0x1800112c0  mov     [rsp+700h+hKey], rdi
0x1800112c5  lea     rcx, aMsscntrsDll; "msscntrs.dll"
0x1800112cc  call    cs:__imp_GetModuleHandleW
0x1800112d2  test    rax, rax
0x1800112d5  jz      short loc_1800112F1
0x1800112d7  mov     r8d, 104h; nSize
0x1800112dd  lea     rdx, [rbp+600h+Filename]; lpFilename
0x1800112e4  mov     rcx, rax; hModule
0x1800112e7  call    cs:__imp_GetModuleFileNameW
0x1800112ed  test    eax, eax
0x1800112ef  jnz     short loc_180011301
0x1800112f1  call    cs:__imp_GetLastError
0x1800112f7  mov     ebx, eax
0x1800112f9  test    eax, eax
0x1800112fb  jnz     loc_180011422
0x180011301  lea     rax, [rsp+700h+var_6A8]
0x180011306  mov     [rsp+700h+var_6C0], rax; unsigned int *
0x18001130b  lea     rax, [rsp+700h+hKey]
0x180011310  mov     [rsp+700h+var_6C8], rax; HKEY *
0x180011315  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\MS"...
0x18001131c  call    ?WSearchRegCreateKey@@YAJPEAUHKEY__@@PEB_WKPEA_WKKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; WSearchRegCreateKey(HKEY__ *,wchar_t const *,ulong,wchar_t *,ulong,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *)
0x180011321  mov     ebx, eax
0x180011323  test    eax, eax
0x180011325  jnz     loc_180011422
0x18001132b  mov     r8d, 104h; cchBuffer
0x180011331  lea     rdx, [rbp+600h+szShortPath]; lpszShortPath
0x180011335  lea     rcx, [rbp+600h+Filename]; lpszLongPath
0x18001133c  call    cs:__imp_GetShortPathNameW
0x180011342  mov     ebx, eax
0x180011344  dec     eax
0x180011346  cmp     eax, 103h
0x18001134b  ja      loc_180011422
0x180011351  mov     [rbp+600h+var_438], di
0x180011358  lea     rcx, [rbp+600h+szShortPath]
0x18001135c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011360  inc     rax
0x180011363  cmp     [rcx+rax*2], di
0x180011367  jnz     short loc_180011360
0x180011369  lea     eax, ds:2[rax*2]
0x180011370  mov     [rsp+700h+cbData], eax; cbData
0x180011374  lea     rax, [rbp+600h+szShortPath]
0x180011378  mov     [rsp+700h+lpData], rax; lpData
0x18001137d  mov     r9d, 1; dwType
0x180011383  xor     r8d, r8d; Reserved
0x180011386  lea     rdx, ValueName; "Library"
0x18001138d  mov     rcx, [rsp+700h+hKey]; hKey
0x180011392  call    cs:__imp_RegSetValueExW
0x180011398  mov     ebx, eax
0x18001139a  test    eax, eax
0x18001139c  jnz     loc_180011422
0x1800113a2  mov     [rsp+700h+cbData], 0Ah; cbData
0x1800113aa  lea     rdx, Data; "Open"
0x1800113b1  mov     [rsp+700h+lpData], rdx; lpData
0x1800113b6  lea     r9d, [rax+1]; dwType
0x1800113ba  xor     r8d, r8d; Reserved
0x1800113bd  mov     rcx, [rsp+700h+hKey]; hKey
0x1800113c2  call    cs:__imp_RegSetValueExW
0x1800113c8  mov     ebx, eax
0x1800113ca  test    eax, eax
0x1800113cc  jnz     short loc_180011422
0x1800113ce  mov     [rsp+700h+cbData], 0Ch; cbData
0x1800113d6  lea     rdx, aClose_0; "Close"
0x1800113dd  mov     [rsp+700h+lpData], rdx; lpData
0x1800113e2  lea     r9d, [rax+1]; dwType
0x1800113e6  xor     r8d, r8d; Reserved
0x1800113e9  mov     rcx, [rsp+700h+hKey]; hKey
0x1800113ee  call    cs:__imp_RegSetValueExW
0x1800113f4  mov     ebx, eax
0x1800113f6  test    eax, eax
0x1800113f8  jnz     short loc_180011422
0x1800113fa  mov     [rsp+700h+cbData], 10h; cbData
0x180011402  lea     rdx, aCollect_0; "Collect"
0x180011409  mov     [rsp+700h+lpData], rdx; lpData
0x18001140e  lea     r9d, [rax+1]; dwType
0x180011412  xor     r8d, r8d; Reserved
0x180011415  mov     rcx, [rsp+700h+hKey]; hKey
0x18001141a  call    cs:__imp_RegSetValueExW
0x180011420  mov     ebx, eax
0x180011422  mov     rcx, [rsp+700h+hKey]; hKey
0x180011427  test    rcx, rcx
0x18001142a  jz      short loc_180011432
0x18001142c  call    cs:__imp_RegCloseKey
0x180011432  test    ebx, ebx
0x180011434  jle     short loc_18001143F
0x180011436  movzx   ebx, bx
0x180011439  or      ebx, 80070000h
0x18001143f  mov     eax, ebx
0x180011441  mov     rcx, [rbp+600h+var_10]
0x180011448  xor     rcx, rsp; StackCookie
0x18001144b  call    __security_check_cookie
0x180011450  lea     r11, [rsp+700h+var_s0]
0x180011458  mov     rbx, [r11+10h]
0x18001145c  mov     rdi, [r11+18h]
0x180011460  mov     rsp, r11
0x180011463  pop     rbp
0x180011464  retn
```
