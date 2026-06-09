# TOKEN_CACHE::Initialize(int,int,ulong,int,int)

- ea: `0x18005eab0`
- end: `0x18005eefe`
- name: `?Initialize@TOKEN_CACHE@@QEAAJHHKHH@Z`
- size: `1102`
- prototype: `__int64 __fastcall(TOKEN_CACHE *__hidden this, int, int, unsigned int, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000479c`

## callees

- `0x180001234`
- `0x180001274`
- `0x18005eab0`
- `0x18005f448`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005ecdd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005ecdd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005eebb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005eed6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005eebb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005eed6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eb73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ebb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ecec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ed91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005edf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eb73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ebb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ecec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ed91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005edf3`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18005ed32`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18005ed32`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005ec81`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005ecc1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005ec81`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005ecc1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ec49`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ec49`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18005ee65`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18005ee65`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18005ede9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18005ede9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18005ed87`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18005ed87`
- `iisutil!PuDbgPrint` at `0x18005ebfb`
- `iisutil!PuDbgPrint` at `0x18005ee4a`
- `iisutil!PuDbgPrint` at `0x18005ebfb`
- `iisutil!PuDbgPrint` at `0x18005ee4a`
- `iisutil!PuDbgPrintError` at `0x18005eea7`
- `iisutil!PuDbgPrintError` at `0x18005eea7`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x18005eba0`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x18005eba0`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x18005eb20`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x18005eb20`
- `W3TP!ThreadPoolInitialize` at `0x18005ee0e`
- `W3TP!ThreadPoolInitialize` at `0x18005ee0e`
- `CRYPTSP!CryptAcquireContextW` at `0x18005eb65`
- `CRYPTSP!CryptAcquireContextW` at `0x18005eb65`

## string_xrefs

- `0x18005eb16`: `TOKEN_CACHE_ENTRY`
- `0x18005ebd4`: `Error initializing sm_pachTokenCacheEntry. hr = 0x%x\n`
- `0x18005ebea`: `TOKEN_CACHE_ENTRY::Initialize`
- `0x18005eb3a`: `servercommon\inetsrv\iis\iisrearc\iisplus\tokencache\tokencache.cxx`
- `0x18005ec12`: `Token cache entry init failed. hr = 0x%x\n`
- `0x18005ee39`: `TOKEN_CACHE::Initialize`
- `0x18005ee90`: `TOKEN_CACHE::Initialize`
- `0x18005ec3b`: `System\CurrentControlSet\Services\inetinfo\Parameters`
- `0x18005ecb7`: `UserTokenTTL`
- `0x18005ed0b`: `CreateEvent() failed. hr = 0x%x\n`
- `0x18005ee23`: `ThreadPoolInitialize failed. hr = 0x%x\n`
- `0x18005ee5e`: `secur32.dll`
- `0x18005ee80`: `Error loading secur32.dll.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TOKEN_CACHE::Initialize(TOKEN_CACHE *this)
{
  ALLOC_CACHE_HANDLER *v2; // rax
  ALLOC_CACHE_HANDLER *v3; // rbx
  signed int LastError; // eax
  signed int v5; // ebx
  const char *v6; // rax
  __int64 v7; // r8
  signed int v8; // eax
  const char *v9; // rax
  __int64 v10; // r8
  int v11; // esi
  HKEY *v12; // rbx
  HANDLE EventW; // rax
  signed int v14; // eax
  LSTATUS v15; // eax
  signed int v16; // eax
  signed int v17; // eax
  HMODULE LibraryW; // rax
  LPDWORD lpcbData; // [rsp+28h] [rbp-50h]
  DWORD cbData; // [rsp+40h] [rbp-38h] BYREF
  DWORD Type; // [rsp+44h] [rbp-34h] BYREF
  BYTE Data[8]; // [rsp+48h] [rbp-30h] BYREF
  ALLOC_CACHE_HANDLER *v24; // [rsp+50h] [rbp-28h]
  _DWORD v25[4]; // [rsp+58h] [rbp-20h] BYREF

  *(_DWORD *)Data = 0;
  Type = 0;
  cbData = 0;
  v25[0] = 1;
  v25[1] = 100;
  v25[2] = 456;
  v2 = (ALLOC_CACHE_HANDLER *)operator new(0x100u);
  v24 = v2;
  if ( v2 )
    v3 = ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(
           v2,
           "TOKEN_CACHE_ENTRY",
           (const struct ALLOC_CACHE_CONFIGURATION *)v25,
           1);
  else
    v3 = 0;
  TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry = v3;
  if ( v3 )
  {
    if ( *(_DWORD *)v3 )
    {
      if ( CryptAcquireContextW(&TOKEN_CACHE_ENTRY::sm_hCryptProv, 0, 0, 0x18u, 0xF0000000) )
        goto LABEL_20;
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        v6 = "CryptAcquireContext() failed. hr = 0x%x\n";
        v7 = 414;
LABEL_16:
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\tokencache\\tokencache.cxx",
          v7,
          "TOKEN_CACHE_ENTRY::Initialize",
          v6,
          v5);
        goto LABEL_17;
      }
      goto LABEL_17;
    }
    ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(v3);
    operator delete(v3);
    TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry = 0;
  }
  v8 = GetLastError();
  v5 = v8;
  if ( v8 > 0 )
    v5 = (unsigned __int16)v8 | 0x80070000;
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    v6 = "Error initializing sm_pachTokenCacheEntry. hr = 0x%x\n";
    v7 = 395;
    goto LABEL_16;
  }
LABEL_17:
  if ( v5 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      v9 = "Token cache entry init failed. hr = 0x%x\n";
      v10 = 896;
LABEL_48:
      LODWORD(lpcbData) = v5;
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\tokencache\\tokencache.cxx",
        v10,
        "TOKEN_CACHE::Initialize",
        v9,
        lpcbData);
      goto LABEL_49;
    }
    goto LABEL_49;
  }
LABEL_20:
  v11 = 900;
  v12 = (HKEY *)((char *)this + 72);
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\inetinfo\\Parameters",
          0,
          0x20019u,
          (PHKEY)this + 9) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(*v12, L"LastPriorityUPNLogon", 0, &Type, Data, &cbData) && Type == 4 )
      *((_DWORD *)this + 27) = *(_DWORD *)Data;
    cbData = 4;
    if ( !RegQueryValueExW(*v12, L"UserTokenTTL", 0, &Type, Data, &cbData) && Type == 4 )
      v11 = *(_DWORD *)Data;
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 10) = EventW;
    if ( !EventW )
    {
      v14 = GetLastError();
      v5 = v14;
      if ( v14 > 0 )
        v5 = (unsigned __int16)v14 | 0x80070000;
      if ( (g_dwDebugFlags & 3) == 0 )
        goto LABEL_49;
      v9 = "CreateEvent() failed. hr = 0x%x\n";
      v10 = 951;
      goto LABEL_48;
    }
    v15 = RegNotifyChangeKeyValue(*v12, 1, 4u, EventW, 1);
    v5 = v15;
    if ( v15 )
    {
      if ( v15 > 0 )
        v5 = (unsigned __int16)v15 | 0x80070000;
      if ( (g_dwDebugFlags & 3) == 0 )
        goto LABEL_49;
      v9 = "RegNotifyChangeKeyValue failed. hr = 0x%x\n";
      v10 = 973;
      goto LABEL_48;
    }
    if ( !RegisterWaitForSingleObject(
            (PHANDLE)this + 11,
            *((HANDLE *)this + 10),
            TOKEN_CACHE::FlushTokenCacheWaitCallback,
            this,
            0xFFFFFFFF,
            0x80u) )
    {
      v16 = GetLastError();
      v5 = v16;
      if ( v16 > 0 )
        v5 = (unsigned __int16)v16 | 0x80070000;
      if ( (g_dwDebugFlags & 3) == 0 )
        goto LABEL_49;
      v9 = "RegisterWaitForSingleObject failed. hr = 0x%x\n";
      v10 = 996;
      goto LABEL_48;
    }
  }
  *((_DWORD *)this + 26) |= 2u;
  if ( !CreateTimerQueueTimer(
          (PHANDLE)this + 12,
          0,
          TOKEN_CACHE::ScavengerCallback,
          this,
          1000 * v11,
          1000 * v11,
          0x10u) )
  {
    v17 = GetLastError();
    v5 = v17;
    if ( v17 > 0 )
      v5 = (unsigned __int16)v17 | 0x80070000;
    goto LABEL_49;
  }
  v5 = ThreadPoolInitialize(0, 0, 0);
  if ( v5 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      v9 = "ThreadPoolInitialize failed. hr = 0x%x\n";
      v10 = 1039;
      goto LABEL_48;
    }
LABEL_49:
    TOKEN_CACHE::Terminate(this);
    return (unsigned int)v5;
  }
  *((_DWORD *)this + 26) |= 1u;
  LibraryW = LoadLibraryW(L"secur32.dll");
  *((_QWORD *)this + 18) = LibraryW;
  if ( !LibraryW )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\tokencache\\tokencache.cxx",
        1057,
        "TOKEN_CACHE::Initialize",
        v5,
        "Error loading secur32.dll.\n");
    return (unsigned int)v5;
  }
  *((_QWORD *)this + 16) = GetProcAddress(LibraryW, "SeciAllocateAndSetIPAddress");
  *((_QWORD *)this + 17) = GetProcAddress(*((HMODULE *)this + 18), "SeciFreeCallContext");
  return 0;
}

```

## disassembly

```asm
0x18005eab0  push    rbp
0x18005eab2  push    rbx
0x18005eab3  push    rsi
0x18005eab4  push    rdi
0x18005eab5  push    r12
0x18005eab7  push    r13
0x18005eab9  mov     rbp, rsp
0x18005eabc  sub     rsp, 78h
0x18005eac0  mov     rax, cs:__security_cookie
0x18005eac7  xor     rax, rsp
0x18005eaca  mov     [rbp+var_10], rax
0x18005eace  mov     rdi, rcx
0x18005ead1  mov     dword ptr [rbp+Data], 0
0x18005ead8  mov     [rbp+Type], 0
0x18005eadf  mov     [rbp+cbData], 0
0x18005eae6  mov     ebx, 1
0x18005eaeb  mov     [rbp+var_20], ebx
0x18005eaee  mov     [rbp+var_1C], 64h ; 'd'
0x18005eaf5  mov     [rbp+var_18], 1C8h
0x18005eafc  mov     ecx, 100h; Size
0x18005eb01  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005eb06  mov     [rbp+var_28], rax
0x18005eb0a  test    rax, rax
0x18005eb0d  jz      short loc_18005EB2B
0x18005eb0f  mov     r9d, ebx
0x18005eb12  lea     r8, [rbp+var_20]
0x18005eb16  lea     rdx, aTokenCacheEntr_0; "TOKEN_CACHE_ENTRY"
0x18005eb1d  mov     rcx, rax
0x18005eb20  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x18005eb26  mov     rbx, rax
0x18005eb29  jmp     short loc_18005EB2D
0x18005eb2b  xor     ebx, ebx
0x18005eb2d  mov     cs:?sm_pachTokenCacheEntry@TOKEN_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA, rbx; ALLOC_CACHE_HANDLER * TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry
0x18005eb34  mov     r12d, 80070000h
0x18005eb3a  lea     r13, aServercommonIn_45; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18005eb41  test    rbx, rbx
0x18005eb44  jz      short loc_18005EBB9
0x18005eb46  cmp     dword ptr [rbx], 0
0x18005eb49  jz      short loc_18005EB9D
0x18005eb4b  mov     [rsp+78h+dwFlags], 0F0000000h; dwFlags
0x18005eb53  mov     r9d, 18h; dwProvType
0x18005eb59  xor     r8d, r8d; szProvider
0x18005eb5c  xor     edx, edx; szContainer
0x18005eb5e  lea     rcx, ?sm_hCryptProv@TOKEN_CACHE_ENTRY@@0_KA; phProv
0x18005eb65  call    cs:__imp_CryptAcquireContextW
0x18005eb6b  test    eax, eax
0x18005eb6d  jnz     loc_18005EC24
0x18005eb73  call    cs:__imp_GetLastError
0x18005eb79  mov     ebx, eax
0x18005eb7b  test    eax, eax
0x18005eb7d  jle     short loc_18005EB85
0x18005eb7f  movzx   ebx, ax
0x18005eb82  or      ebx, r12d
0x18005eb85  test    byte ptr cs:g_dwDebugFlags, 3
0x18005eb8c  jz      short loc_18005EC01
0x18005eb8e  lea     rax, aCryptacquireco_0; "CryptAcquireContext() failed. hr = 0x%x"...
0x18005eb95  mov     r8d, 19Eh
0x18005eb9b  jmp     short loc_18005EBE1
0x18005eb9d  mov     rcx, rbx
0x18005eba0  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x18005eba6  mov     rcx, rbx; Block
0x18005eba9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005ebae  mov     cs:?sm_pachTokenCacheEntry@TOKEN_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry
0x18005ebb9  call    cs:__imp_GetLastError
0x18005ebbf  mov     ebx, eax
0x18005ebc1  test    eax, eax
0x18005ebc3  jle     short loc_18005EBCB
0x18005ebc5  movzx   ebx, ax
0x18005ebc8  or      ebx, r12d
0x18005ebcb  test    byte ptr cs:g_dwDebugFlags, 3
0x18005ebd2  jz      short loc_18005EC01
0x18005ebd4  lea     rax, aErrorInitializ_0; "Error initializing sm_pachTokenCacheEnt"...
0x18005ebdb  mov     r8d, 18Bh
0x18005ebe1  mov     dword ptr [rsp+78h+lpcbData], ebx
0x18005ebe5  mov     qword ptr [rsp+78h+dwFlags], rax
0x18005ebea  lea     r9, aTokenCacheEntr_2; "TOKEN_CACHE_ENTRY::Initialize"
0x18005ebf1  mov     rdx, r13
0x18005ebf4  mov     rcx, cs:g_pDebug
0x18005ebfb  call    cs:__imp_PuDbgPrint
0x18005ec01  test    ebx, ebx
0x18005ec03  jns     short loc_18005EC24
0x18005ec05  test    byte ptr cs:g_dwDebugFlags, 3
0x18005ec0c  jz      loc_18005EE50
0x18005ec12  lea     rax, aTokenCacheEntr_1; "Token cache entry init failed. hr = 0x%"...
0x18005ec19  mov     r8d, 380h
0x18005ec1f  jmp     loc_18005EE30
0x18005ec24  mov     esi, 384h
0x18005ec29  lea     rbx, [rdi+48h]
0x18005ec2d  mov     qword ptr [rsp+78h+dwFlags], rbx; phkResult
0x18005ec32  mov     r9d, 20019h; samDesired
0x18005ec38  xor     r8d, r8d; ulOptions
0x18005ec3b  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\in"...
0x18005ec42  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005ec49  call    cs:__imp_RegOpenKeyExW
0x18005ec4f  test    eax, eax
0x18005ec51  jnz     loc_18005EDBF
0x18005ec57  mov     [rbp+cbData], 4
0x18005ec5e  lea     rax, [rbp+cbData]
0x18005ec62  mov     [rsp+78h+lpcbData], rax; lpcbData
0x18005ec67  lea     rax, [rbp+Data]
0x18005ec6b  mov     qword ptr [rsp+78h+dwFlags], rax; lpData
0x18005ec70  lea     r9, [rbp+Type]; lpType
0x18005ec74  xor     r8d, r8d; lpReserved
0x18005ec77  lea     rdx, aLastpriorityup; "LastPriorityUPNLogon"
0x18005ec7e  mov     rcx, [rbx]; hKey
0x18005ec81  call    cs:__imp_RegQueryValueExW
0x18005ec87  test    eax, eax
0x18005ec89  jnz     short loc_18005EC97
0x18005ec8b  cmp     [rbp+Type], 4
0x18005ec8f  jnz     short loc_18005EC97
0x18005ec91  mov     eax, dword ptr [rbp+Data]
0x18005ec94  mov     [rdi+6Ch], eax
0x18005ec97  mov     [rbp+cbData], 4
0x18005ec9e  lea     rax, [rbp+cbData]
0x18005eca2  mov     [rsp+78h+lpcbData], rax; lpcbData
0x18005eca7  lea     rax, [rbp+Data]
0x18005ecab  mov     qword ptr [rsp+78h+dwFlags], rax; lpData
0x18005ecb0  lea     r9, [rbp+Type]; lpType
0x18005ecb4  xor     r8d, r8d; lpReserved
0x18005ecb7  lea     rdx, aUsertokenttl; "UserTokenTTL"
0x18005ecbe  mov     rcx, [rbx]; hKey
0x18005ecc1  call    cs:__imp_RegQueryValueExW
0x18005ecc7  test    eax, eax
0x18005ecc9  jnz     short loc_18005ECD3
0x18005eccb  cmp     [rbp+Type], 4
0x18005eccf  cmovz   esi, dword ptr [rbp+Data]
0x18005ecd3  xor     r9d, r9d; lpName
0x18005ecd6  xor     r8d, r8d; bInitialState
0x18005ecd9  xor     edx, edx; bManualReset
0x18005ecdb  xor     ecx, ecx; lpEventAttributes
0x18005ecdd  call    cs:__imp_CreateEventW
0x18005ece3  mov     [rdi+50h], rax
0x18005ece7  test    rax, rax
0x18005ecea  jnz     short loc_18005ED1D
0x18005ecec  call    cs:__imp_GetLastError
0x18005ecf2  mov     ebx, eax
0x18005ecf4  test    eax, eax
0x18005ecf6  jle     short loc_18005ECFE
0x18005ecf8  movzx   ebx, ax
0x18005ecfb  or      ebx, r12d
0x18005ecfe  test    byte ptr cs:g_dwDebugFlags, 3
0x18005ed05  jz      loc_18005EE50
0x18005ed0b  lea     rax, aCreateeventFai; "CreateEvent() failed. hr = 0x%x\n"
0x18005ed12  mov     r8d, 3B7h
0x18005ed18  jmp     loc_18005EE30
0x18005ed1d  mov     ecx, 1
0x18005ed22  mov     [rsp+78h+dwFlags], ecx; fAsynchronous
0x18005ed26  mov     r9, rax; hEvent
0x18005ed29  lea     r8d, [rcx+3]; dwNotifyFilter
0x18005ed2d  mov     edx, ecx; bWatchSubtree
0x18005ed2f  mov     rcx, [rbx]; hKey
0x18005ed32  call    cs:__imp_RegNotifyChangeKeyValue
0x18005ed38  mov     ebx, eax
0x18005ed3a  test    eax, eax
0x18005ed3c  jz      short loc_18005ED65
0x18005ed3e  jle     short loc_18005ED46
0x18005ed40  movzx   ebx, ax
0x18005ed43  or      ebx, r12d
0x18005ed46  test    byte ptr cs:g_dwDebugFlags, 3
0x18005ed4d  jz      loc_18005EE50
0x18005ed53  lea     rax, aRegnotifychang; "RegNotifyChangeKeyValue failed. hr = 0x"...
0x18005ed5a  mov     r8d, 3CDh
0x18005ed60  jmp     loc_18005EE30
0x18005ed65  lea     rcx, [rdi+58h]; phNewWaitObject
0x18005ed69  mov     dword ptr [rsp+78h+lpcbData], 80h; dwFlags
0x18005ed71  mov     [rsp+78h+dwFlags], 0FFFFFFFFh; dwMilliseconds
0x18005ed79  mov     r9, rdi; Context
0x18005ed7c  lea     r8, ?FlushTokenCacheWaitCallback@TOKEN_CACHE@@SAXPEAXH@Z; Callback
0x18005ed83  mov     rdx, [rdi+50h]; hObject
0x18005ed87  call    cs:__imp_RegisterWaitForSingleObject
0x18005ed8d  test    eax, eax
0x18005ed8f  jnz     short loc_18005EDBF
0x18005ed91  call    cs:__imp_GetLastError
0x18005ed97  mov     ebx, eax
0x18005ed99  test    eax, eax
0x18005ed9b  jle     short loc_18005EDA3
0x18005ed9d  movzx   ebx, ax
0x18005eda0  or      ebx, r12d
0x18005eda3  test    byte ptr cs:g_dwDebugFlags, 3
0x18005edaa  jz      loc_18005EE50
0x18005edb0  lea     rax, aRegisterwaitfo; "RegisterWaitForSingleObject failed. hr "...
0x18005edb7  mov     r8d, 3E4h
0x18005edbd  jmp     short loc_18005EE30
0x18005edbf  or      dword ptr [rdi+68h], 2
0x18005edc3  imul    eax, esi, 3E8h
0x18005edc9  lea     rcx, [rdi+60h]; phNewTimer
0x18005edcd  mov     [rsp+78h+Flags], 10h; Flags
0x18005edd5  mov     dword ptr [rsp+78h+lpcbData], eax; Period
0x18005edd9  mov     [rsp+78h+dwFlags], eax; DueTime
0x18005eddd  mov     r9, rdi; Parameter
0x18005ede0  lea     r8, ?ScavengerCallback@TOKEN_CACHE@@CAXPEAXE@Z; Callback
0x18005ede7  xor     edx, edx; TimerQueue
0x18005ede9  call    cs:__imp_CreateTimerQueueTimer
0x18005edef  test    eax, eax
0x18005edf1  jnz     short loc_18005EE07
0x18005edf3  call    cs:__imp_GetLastError
0x18005edf9  mov     ebx, eax
0x18005edfb  test    eax, eax
0x18005edfd  jle     short loc_18005EE50
0x18005edff  movzx   ebx, ax
0x18005ee02  or      ebx, r12d
0x18005ee05  jmp     short loc_18005EE50
0x18005ee07  xor     r8d, r8d
0x18005ee0a  xor     edx, edx
0x18005ee0c  xor     ecx, ecx
0x18005ee0e  call    cs:__imp_?ThreadPoolInitialize@@YAJKKK@Z; ThreadPoolInitialize(ulong,ulong,ulong)
0x18005ee14  mov     ebx, eax
0x18005ee16  test    eax, eax
0x18005ee18  jns     short loc_18005EE5A
0x18005ee1a  test    byte ptr cs:g_dwDebugFlags, 3
0x18005ee21  jz      short loc_18005EE50
0x18005ee23  lea     rax, aThreadpoolinit; "ThreadPoolInitialize failed. hr = 0x%x"...
0x18005ee2a  mov     r8d, 40Fh
0x18005ee30  mov     dword ptr [rsp+78h+lpcbData], ebx
0x18005ee34  mov     qword ptr [rsp+78h+dwFlags], rax
0x18005ee39  lea     r9, aTokenCacheInit; "TOKEN_CACHE::Initialize"
0x18005ee40  mov     rdx, r13
0x18005ee43  mov     rcx, cs:g_pDebug
0x18005ee4a  call    cs:__imp_PuDbgPrint
0x18005ee50  mov     rcx, rdi; this
0x18005ee53  call    ?Terminate@TOKEN_CACHE@@QEAAXXZ; TOKEN_CACHE::Terminate(void)
0x18005ee58  jmp     short loc_18005EEAD
0x18005ee5a  or      dword ptr [rdi+68h], 1
0x18005ee5e  lea     rcx, aSecur32Dll; "secur32.dll"
0x18005ee65  call    cs:__imp_LoadLibraryW
0x18005ee6b  mov     [rdi+90h], rax
0x18005ee72  test    rax, rax
0x18005ee75  jnz     short loc_18005EEB1
0x18005ee77  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005ee7e  jz      short loc_18005EEAD
0x18005ee80  lea     rax, aErrorLoadingSe; "Error loading secur32.dll.\n"
0x18005ee87  mov     [rsp+78h+lpcbData], rax
0x18005ee8c  mov     [rsp+78h+dwFlags], ebx
0x18005ee90  lea     r9, aTokenCacheInit; "TOKEN_CACHE::Initialize"
0x18005ee97  mov     r8d, 421h
0x18005ee9d  mov     rdx, r13
0x18005eea0  mov     rcx, cs:g_pDebug
0x18005eea7  call    cs:__imp_PuDbgPrintError
0x18005eead  mov     eax, ebx
0x18005eeaf  jmp     short loc_18005EEE5
0x18005eeb1  lea     rdx, aSeciallocatean; "SeciAllocateAndSetIPAddress"
0x18005eeb8  mov     rcx, rax; hModule
0x18005eebb  call    cs:__imp_GetProcAddress
0x18005eec1  mov     [rdi+80h], rax
0x18005eec8  lea     rdx, aSecifreecallco; "SeciFreeCallContext"
0x18005eecf  mov     rcx, [rdi+90h]; hModule
0x18005eed6  call    cs:__imp_GetProcAddress
0x18005eedc  mov     [rdi+88h], rax
0x18005eee3  xor     eax, eax
0x18005eee5  mov     rcx, [rbp+var_10]
0x18005eee9  xor     rcx, rsp; StackCookie
0x18005eeec  call    __security_check_cookie
0x18005eef1  add     rsp, 78h
0x18005eef5  pop     r13
0x18005eef7  pop     r12
0x18005eef9  pop     rdi
0x18005eefa  pop     rsi
0x18005eefb  pop     rbx
0x18005eefc  pop     rbp
0x18005eefd  retn
```
