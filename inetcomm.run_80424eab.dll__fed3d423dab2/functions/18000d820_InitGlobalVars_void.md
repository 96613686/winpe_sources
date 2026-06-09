# InitGlobalVars(void)

- ea: `0x18000d820`
- end: `0x18000db9b`
- name: `?InitGlobalVars@@YAXXZ`
- size: `891`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800212e0`

## callees

- `0x18000d820`
- `0x18000dba4`
- `0x18000dc38`
- `0x180015a80`
- `0x180021eb8`
- `0x1800228d4`
- `0x1800235a8`
- `0x1800239ec`
- `0x180023b80`
- `0x1800299d0`
- `0x1800c7778`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!MessageBoxInstW` at `0x18000db75`
- `MSOERT2!MessageBoxInstW` at `0x18000db75`
- `SHLWAPI!StrToIntA` at `0x18000da00`
- `SHLWAPI!StrToIntA` at `0x18000da00`
- `ADVAPI32!RegOpenKeyExA` at `0x18000d9b6`
- `ADVAPI32!RegOpenKeyExA` at `0x18000d9b6`
- `ADVAPI32!RegQueryValueExA` at `0x18000d9f1`
- `ADVAPI32!RegQueryValueExA` at `0x18000d9f1`
- `ADVAPI32!RegCloseKey` at `0x18000da11`
- `ADVAPI32!RegCloseKey` at `0x18000da11`
- `KERNEL32!CreateMutexA` at `0x18000d899`
- `KERNEL32!CreateMutexA` at `0x18000d899`
- `KERNEL32!InitializeCriticalSection` at `0x18000d858`
- `KERNEL32!InitializeCriticalSection` at `0x18000d865`
- `KERNEL32!InitializeCriticalSection` at `0x18000d872`
- `KERNEL32!InitializeCriticalSection` at `0x18000d87f`
- `KERNEL32!InitializeCriticalSection` at `0x18000d88c`
- `KERNEL32!InitializeCriticalSection` at `0x18000d8ed`
- `KERNEL32!InitializeCriticalSection` at `0x18000d858`
- `KERNEL32!InitializeCriticalSection` at `0x18000d865`
- `KERNEL32!InitializeCriticalSection` at `0x18000d872`
- `KERNEL32!InitializeCriticalSection` at `0x18000d87f`
- `KERNEL32!InitializeCriticalSection` at `0x18000d88c`
- `KERNEL32!InitializeCriticalSection` at `0x18000d8ed`
- `USER32!RegisterClipboardFormatA` at `0x18000d969`
- `USER32!RegisterClipboardFormatA` at `0x18000d97c`
- `USER32!RegisterClipboardFormatA` at `0x18000d98f`
- `USER32!RegisterClipboardFormatA` at `0x18000d969`
- `USER32!RegisterClipboardFormatA` at `0x18000d97c`
- `USER32!RegisterClipboardFormatA` at `0x18000d98f`
- `USER32!MessageBoxW` at `0x18000db2a`
- `USER32!LoadStringW` at `0x18000db5c`
- `ole32!CoGetMalloc` at `0x18000d8bf`
- `ole32!CoGetMalloc` at `0x18000d8bf`

## pseudocode

```c
void InitGlobalVars(void)
{
  CMimeAllocator *v0; // rax
  struct CMimeAllocator *v1; // rax
  CPropertySymbolCache *v2; // rax
  CPropertySymbolCache *v3; // rcx
  CPropertySymbolCache *v4; // rax
  CMimeActiveUrlCacheForwarder *v5; // rax
  CMimeActiveUrlCacheForwarder *v6; // rax
  CFontCache *v7; // rax
  CFontCache *v8; // rax
  struct IFontCache *v9; // r10
  const char *v10; // r9
  __int64 v11; // r8
  char *v12; // rcx
  __int64 v13; // rax
  bool v14; // zf
  char *v15; // rax
  __int64 v16; // r8
  char *v17; // rax
  __int64 v18; // r9
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  BYTE Data[32]; // [rsp+70h] [rbp-90h] BYREF
  char v23[272]; // [rsp+90h] [rbp-70h] BYREF

  hKey = 0;
  cbData = 0;
  InitializeCriticalSection(&g_csDllMain);
  InitializeCriticalSection(&g_csRAS);
  InitializeCriticalSection(&g_csCounter);
  InitializeCriticalSection(&g_csMLANG);
  InitializeCriticalSection(&g_csCSAPI3T1);
  g_hRootPropsMutex = CreateMutexA(0, 0, 0);
  g_fAttached = 1;
  InitLookupCache();
  CoGetMalloc(1u, &g_pMalloc);
  v0 = (CMimeAllocator *)operator new(0x10u);
  if ( v0 )
    v1 = CMimeAllocator::CMimeAllocator(v0);
  else
    v1 = 0;
  g_pMoleAlloc = v1;
  InitializeCriticalSection(&CriticalSection);
  v2 = (CPropertySymbolCache *)operator new(0x2E8u);
  if ( v2 )
    v4 = CPropertySymbolCache::CPropertySymbolCache(v2);
  else
    v4 = 0;
  g_pSymCache = v4;
  CPropertySymbolCache::Init(v3);
  CMimeInternational::InitInternational();
  v5 = (CMimeActiveUrlCacheForwarder *)operator new(0x68u);
  if ( v5 )
    v6 = CMimeActiveUrlCacheForwarder::CMimeActiveUrlCacheForwarder(v5);
  else
    v6 = 0;
  qword_1800F30E0 = (__int64)v6;
  g_pUrlCache = (struct IMimeActiveUrlCache *)(((unsigned __int64)v6 + 32) & -(__int64)(v6 != 0));
  g_fCanEditBiDi = CanEditBiDi();
  CF_HTML = RegisterClipboardFormatA("HTML Format");
  CF_INETMSG = RegisterClipboardFormatA("Internet Message (rfc822/rfc1522)");
  RegisterClipboardFormatA("message/rfc822");
  if ( !RegOpenKeyExA(HKEY_CURRENT_USER, "Control Panel\\International\\Calendars\\TwoDigitYearMax", 0, 0x20019u, &hKey) )
  {
    cbData = 16;
    Data[16] = 0;
    if ( !RegQueryValueExA(hKey, "1", 0, 0, Data, &cbData) )
      g_ulY2kThreshold = StrToIntA((PCSTR)Data);
    RegCloseKey(hKey);
  }
  g_ulUpperCentury = g_ulY2kThreshold / 0x64;
  g_ulY2kThreshold %= 0x64u;
  if ( !g_lpIFontCache )
  {
    g_lpIFontCache = 0;
    v7 = (CFontCache *)operator new(0x4B0u);
    if ( !v7 )
      goto LABEL_29;
    v8 = CFontCache::CFontCache(v7, 0);
    if ( !v8 )
      goto LABEL_29;
    v9 = (CFontCache *)((char *)v8 + 32);
    g_lpIFontCache = (CFontCache *)((char *)v8 + 32);
    v10 = "Software\\Microsoft\\Internet Explorer";
    v11 = 260;
    v12 = v23;
    v13 = 2147483646;
    do
    {
      if ( !v13 )
        break;
      if ( !*v10 )
        break;
      *v12++ = *v10++;
      --v13;
      --v11;
    }
    while ( v11 );
    v14 = v11 == 0;
    v15 = v12 - 1;
    v16 = 260;
    if ( !v14 )
      v15 = v12;
    *v15 = 0;
    v17 = v23;
    do
    {
      if ( !*v17 )
        break;
      ++v17;
      --v16;
    }
    while ( v16 );
    if ( v16 )
    {
      v18 = (260 - v16) & -(__int64)(v16 != 0);
      StringCopyWorkerA(&v23[v18], 260 - v18, (size_t *)v16, "\\International", (size_t)phkResult);
      v9 = g_lpIFontCache;
    }
    if ( (*(int (__fastcall **)(struct IFontCache *, __int64, char *, _QWORD))(*(_QWORD *)v9 + 24LL))(
           v9,
           -2147483647,
           v23,
           0) < 0 )
LABEL_29:
      MessageBoxInstW(g_hLocRes, 0, 101, 1247, 0, 16, LoadStringW, MessageBoxW, 0, 0, 0, 0);
  }
}

```

## disassembly

```asm
0x18000d820  mov     [rsp-8+arg_0], rbx
0x18000d825  push    rbp
0x18000d826  lea     rbp, [rsp-0B0h]
0x18000d82e  sub     rsp, 1B0h
0x18000d835  mov     rax, cs:__security_cookie
0x18000d83c  xor     rax, rsp
0x18000d83f  mov     [rbp+0B0h+var_10], rax
0x18000d846  xor     ebx, ebx
0x18000d848  lea     rcx, ?g_csDllMain@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d84f  mov     [rsp+1B0h+hKey], rbx
0x18000d854  mov     [rsp+1B0h+cbData], ebx
0x18000d858  call    cs:__imp_InitializeCriticalSection
0x18000d85e  lea     rcx, ?g_csRAS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d865  call    cs:__imp_InitializeCriticalSection
0x18000d86b  lea     rcx, ?g_csCounter@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d872  call    cs:__imp_InitializeCriticalSection
0x18000d878  lea     rcx, ?g_csMLANG@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d87f  call    cs:__imp_InitializeCriticalSection
0x18000d885  lea     rcx, ?g_csCSAPI3T1@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d88c  call    cs:__imp_InitializeCriticalSection
0x18000d892  xor     r8d, r8d; lpName
0x18000d895  xor     edx, edx; bInitialOwner
0x18000d897  xor     ecx, ecx; lpMutexAttributes
0x18000d899  call    cs:__imp_CreateMutexA
0x18000d89f  mov     cs:?g_hRootPropsMutex@@3PEAXEA, rax; void * g_hRootPropsMutex
0x18000d8a6  mov     cs:?g_fAttached@@3HA, 1; int g_fAttached
0x18000d8b0  call    ?InitLookupCache@@YAXXZ; InitLookupCache(void)
0x18000d8b5  lea     rdx, ?g_pMalloc@@3PEAUIMalloc@@EA; ppMalloc
0x18000d8bc  lea     ecx, [rbx+1]; dwMemContext
0x18000d8bf  call    cs:__imp_CoGetMalloc
0x18000d8c5  lea     ecx, [rbx+10h]; Size
0x18000d8c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d8cd  test    rax, rax
0x18000d8d0  jz      short loc_18000D8DC
0x18000d8d2  mov     rcx, rax; this
0x18000d8d5  call    ??0CMimeAllocator@@QEAA@XZ; CMimeAllocator::CMimeAllocator(void)
0x18000d8da  jmp     short loc_18000D8DF
0x18000d8dc  mov     rax, rbx
0x18000d8df  lea     rcx, CriticalSection; lpCriticalSection
0x18000d8e6  mov     cs:?g_pMoleAlloc@@3PEAVCMimeAllocator@@EA, rax; CMimeAllocator * g_pMoleAlloc
0x18000d8ed  call    cs:__imp_InitializeCriticalSection
0x18000d8f3  mov     ecx, 2E8h; Size
0x18000d8f8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d8fd  test    rax, rax
0x18000d900  jz      short loc_18000D90C
0x18000d902  mov     rcx, rax; this
0x18000d905  call    ??0CPropertySymbolCache@@QEAA@XZ; CPropertySymbolCache::CPropertySymbolCache(void)
0x18000d90a  jmp     short loc_18000D90F
0x18000d90c  mov     rax, rbx
0x18000d90f  mov     cs:?g_pSymCache@@3PEAVCPropertySymbolCache@@EA, rax; CPropertySymbolCache * g_pSymCache
0x18000d916  call    ?Init@CPropertySymbolCache@@QEAAJXZ; CPropertySymbolCache::Init(void)
0x18000d91b  call    ?InitInternational@CMimeInternational@@SAXXZ; CMimeInternational::InitInternational(void)
0x18000d920  mov     ecx, 68h ; 'h'; Size
0x18000d925  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d92a  test    rax, rax
0x18000d92d  jz      short loc_18000D939
0x18000d92f  mov     rcx, rax; this
0x18000d932  call    ??0CMimeActiveUrlCacheForwarder@@QEAA@XZ; CMimeActiveUrlCacheForwarder::CMimeActiveUrlCacheForwarder(void)
0x18000d937  jmp     short loc_18000D93C
0x18000d939  mov     rax, rbx
0x18000d93c  mov     cs:qword_1800F30E0, rax
0x18000d943  lea     rcx, [rax+20h]
0x18000d947  neg     rax
0x18000d94a  sbb     rax, rax
0x18000d94d  and     rax, rcx
0x18000d950  mov     cs:?g_pUrlCache@@3PEAUIMimeActiveUrlCache@@EA, rax; IMimeActiveUrlCache * g_pUrlCache
0x18000d957  call    ?CanEditBiDi@@YAHXZ; CanEditBiDi(void)
0x18000d95c  lea     rcx, STR_CF_HTML; "HTML Format"
0x18000d963  mov     cs:?g_fCanEditBiDi@@3HA, eax; int g_fCanEditBiDi
0x18000d969  call    cs:__imp_RegisterClipboardFormatA
0x18000d96f  lea     rcx, STR_CF_INETMSG; "Internet Message (rfc822/rfc1522)"
0x18000d976  mov     cs:?CF_HTML@@3IA, eax; uint CF_HTML
0x18000d97c  call    cs:__imp_RegisterClipboardFormatA
0x18000d982  lea     rcx, STR_CF_RFC822; "message/rfc822"
0x18000d989  mov     cs:?CF_INETMSG@@3IA, eax; uint CF_INETMSG
0x18000d98f  call    cs:__imp_RegisterClipboardFormatA
0x18000d995  lea     rax, [rsp+1B0h+hKey]
0x18000d99a  mov     r9d, 20019h; samDesired
0x18000d9a0  xor     r8d, r8d; ulOptions
0x18000d9a3  mov     [rsp+1B0h+phkResult], rax; phkResult
0x18000d9a8  lea     rdx, REG_Y2K_THRESHOLD; "Control Panel\\International\\Calendars"...
0x18000d9af  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000d9b6  call    cs:__imp_RegOpenKeyExA
0x18000d9bc  test    eax, eax
0x18000d9be  jnz     short loc_18000DA17
0x18000d9c0  mov     rcx, [rsp+1B0h+hKey]; hKey
0x18000d9c5  lea     rax, [rsp+1B0h+cbData]
0x18000d9ca  mov     [rsp+1B0h+lpcbData], rax; lpcbData
0x18000d9cf  lea     rdx, ValueName; "1"
0x18000d9d6  lea     rax, [rsp+1B0h+Data]
0x18000d9db  mov     [rsp+1B0h+cbData], 10h
0x18000d9e3  xor     r9d, r9d; lpType
0x18000d9e6  mov     [rsp+1B0h+phkResult], rax; cchToCopy
0x18000d9eb  xor     r8d, r8d; lpReserved
0x18000d9ee  mov     [rbp+0B0h+var_130], bl
0x18000d9f1  call    cs:__imp_RegQueryValueExA
0x18000d9f7  test    eax, eax
0x18000d9f9  jnz     short loc_18000DA0C
0x18000d9fb  lea     rcx, [rsp+1B0h+Data]; pszSrc
0x18000da00  call    cs:__imp_StrToIntA
0x18000da06  mov     cs:?g_ulY2kThreshold@@3KA, eax; ulong g_ulY2kThreshold
0x18000da0c  mov     rcx, [rsp+1B0h+hKey]; hKey
0x18000da11  call    cs:__imp_RegCloseKey
0x18000da17  mov     ecx, cs:?g_ulY2kThreshold@@3KA; ulong g_ulY2kThreshold
0x18000da1d  mov     eax, 51EB851Fh
0x18000da22  mul     ecx
0x18000da24  shr     edx, 5
0x18000da27  imul    eax, edx, -64h
0x18000da2a  mov     cs:?g_ulUpperCentury@@3KA, edx; ulong g_ulUpperCentury
0x18000da30  add     ecx, eax
0x18000da32  cmp     cs:?g_lpIFontCache@@3PEAUIFontCache@@EA, rbx; IFontCache * g_lpIFontCache
0x18000da39  mov     cs:?g_ulY2kThreshold@@3KA, ecx; ulong g_ulY2kThreshold
0x18000da3f  jnz     loc_18000DB7B
0x18000da45  mov     ecx, 4B0h; Size
0x18000da4a  mov     cs:?g_lpIFontCache@@3PEAUIFontCache@@EA, rbx; IFontCache * g_lpIFontCache
0x18000da51  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000da56  test    rax, rax
0x18000da59  jz      loc_18000DB2A
0x18000da5f  xor     edx, edx; struct IUnknown *
0x18000da61  mov     rcx, rax; this
0x18000da64  call    ??0CFontCache@@AEAA@PEAUIUnknown@@@Z; CFontCache::CFontCache(IUnknown *)
0x18000da69  test    rax, rax
0x18000da6c  jz      loc_18000DB2A
0x18000da72  lea     r10, [rax+20h]
0x18000da76  mov     edx, 104h
0x18000da7b  mov     cs:?g_lpIFontCache@@3PEAUIFontCache@@EA, r10; IFontCache * g_lpIFontCache
0x18000da82  lea     r9, c_szExplorerRegPath; "Software\\Microsoft\\Internet Explorer"
0x18000da89  mov     r8d, edx
0x18000da8c  lea     rcx, [rbp+0B0h+var_120]
0x18000da90  mov     eax, 7FFFFFFEh
0x18000da95  test    rax, rax
0x18000da98  jz      short loc_18000DAB4
0x18000da9a  mov     r11b, [r9]
0x18000da9d  test    r11b, r11b
0x18000daa0  jz      short loc_18000DAB4
0x18000daa2  mov     [rcx], r11b
0x18000daa5  inc     r9
0x18000daa8  inc     rcx
0x18000daab  dec     rax
0x18000daae  sub     r8, 1
0x18000dab2  jnz     short loc_18000DA95
0x18000dab4  test    r8, r8
0x18000dab7  lea     rax, [rcx-1]
0x18000dabb  mov     r8, rdx
0x18000dabe  cmovnz  rax, rcx
0x18000dac2  mov     [rax], bl
0x18000dac4  lea     rax, [rbp+0B0h+var_120]
0x18000dac8  cmp     [rax], bl
0x18000daca  jz      short loc_18000DAD5
0x18000dacc  inc     rax
0x18000dacf  sub     r8, 1; pcchNewDestLength
0x18000dad3  jnz     short loc_18000DAC8
0x18000dad5  mov     rcx, rdx
0x18000dad8  mov     rax, r8
0x18000dadb  sub     rcx, r8
0x18000dade  neg     rax
0x18000dae1  sbb     r9, r9
0x18000dae4  and     r9, rcx
0x18000dae7  test    r8, r8
0x18000daea  jz      short loc_18000DB09
0x18000daec  sub     rdx, r9; cchDest
0x18000daef  lea     rcx, [rbp+0B0h+var_120]
0x18000daf3  add     rcx, r9; pszDest
0x18000daf6  lea     r9, aInternational; "\\International"
0x18000dafd  call    StringCopyWorkerA
0x18000db02  mov     r10, cs:?g_lpIFontCache@@3PEAUIFontCache@@EA; IFontCache * g_lpIFontCache
0x18000db09  mov     rax, [r10]
0x18000db0c  lea     r8, [rbp+0B0h+var_120]
0x18000db10  xor     r9d, r9d
0x18000db13  mov     rdx, 0FFFFFFFF80000001h
0x18000db1a  mov     rcx, r10
0x18000db1d  mov     rax, [rax+18h]
0x18000db21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db26  test    eax, eax
0x18000db28  jns     short loc_18000DB7B
0x18000db2a  mov     rax, cs:__imp_MessageBoxW
0x18000db31  xor     edx, edx
0x18000db33  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hLocRes
0x18000db3a  mov     r9d, 4DFh
0x18000db40  mov     [rsp+1B0h+var_158], ebx
0x18000db44  mov     [rsp+1B0h+var_160], rbx
0x18000db49  mov     [rsp+1B0h+var_168], rbx
0x18000db4e  lea     r8d, [rdx+65h]
0x18000db52  mov     [rsp+1B0h+var_170], rbx
0x18000db57  mov     [rsp+1B0h+var_178], rax
0x18000db5c  mov     rax, cs:__imp_LoadStringW
0x18000db63  mov     [rsp+1B0h+var_180], rax
0x18000db68  mov     dword ptr [rsp+1B0h+lpcbData], 10h
0x18000db70  mov     [rsp+1B0h+phkResult], rbx
0x18000db75  call    cs:__imp_MessageBoxInstW
0x18000db7b  mov     rcx, [rbp+0B0h+var_10]
0x18000db82  xor     rcx, rsp; StackCookie
0x18000db85  call    __security_check_cookie
0x18000db8a  mov     rbx, [rsp+1B0h+arg_0]
0x18000db92  add     rsp, 1B0h
0x18000db99  pop     rbp
0x18000db9a  retn
```
