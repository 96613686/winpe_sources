# RPORDllMain(HINSTANCE__ *,ulong,void *)

- ea: `0x180016770`
- end: `0x180016a5d`
- name: `?RPORDllMain@@YAHPEAUHINSTANCE__@@KPEAX@Z`
- size: `749`
- prototype: `__int64 __fastcall(HINSTANCE hModule, int, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001c594`

## callees

- `0x18000a990`
- `0x1800165e0`
- `0x180016770`
- `0x180016a64`
- `0x18001ac80`
- `0x18001ccfc`
- `0x18001dd5c`

## import_xrefs

- `CRYPT32!I_CryptDetachTls` at `0x18001678b`
- `CRYPT32!I_CryptDetachTls` at `0x18001678b`
- `CRYPT32!I_CryptFreeTls` at `0x1800169c4`
- `CRYPT32!I_CryptFreeTls` at `0x1800169f6`
- `CRYPT32!I_CryptFreeTls` at `0x1800169c4`
- `CRYPT32!I_CryptFreeTls` at `0x1800169f6`
- `CRYPT32!I_CryptAllocTls` at `0x180016963`
- `CRYPT32!I_CryptAllocTls` at `0x180016963`
- `CRYPT32!CryptInstallOIDFunctionAddress` at `0x18001688d`
- `CRYPT32!CryptInstallOIDFunctionAddress` at `0x1800168c0`
- `CRYPT32!CryptInstallOIDFunctionAddress` at `0x1800168f3`
- `CRYPT32!CryptInstallOIDFunctionAddress` at `0x180016926`
- `CRYPT32!CryptInstallOIDFunctionAddress` at `0x180016959`
- `CRYPT32!CryptInstallOIDFunctionAddress` at `0x18001688d`
- `CRYPT32!CryptInstallOIDFunctionAddress` at `0x1800168c0`
- `CRYPT32!CryptInstallOIDFunctionAddress` at `0x1800168f3`
- `CRYPT32!CryptInstallOIDFunctionAddress` at `0x180016926`
- `CRYPT32!CryptInstallOIDFunctionAddress` at `0x180016959`
- `CRYPT32!CryptInitOIDFunctionSet` at `0x1800167c0`
- `CRYPT32!CryptInitOIDFunctionSet` at `0x1800167d6`
- `CRYPT32!CryptInitOIDFunctionSet` at `0x1800167ec`
- `CRYPT32!CryptInitOIDFunctionSet` at `0x180016802`
- `CRYPT32!CryptInitOIDFunctionSet` at `0x180016818`
- `CRYPT32!CryptInitOIDFunctionSet` at `0x1800167c0`
- `CRYPT32!CryptInitOIDFunctionSet` at `0x1800167d6`
- `CRYPT32!CryptInitOIDFunctionSet` at `0x1800167ec`
- `CRYPT32!CryptInitOIDFunctionSet` at `0x180016802`
- `CRYPT32!CryptInitOIDFunctionSet` at `0x180016818`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800169d1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016a2e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016a45`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800169d1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016a2e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016a45`

## string_xrefs

- `0x1800167f4`: `TimeValidDllGetObject`
- `0x180016917`: `TimeValidDllGetObject`
- `0x1800167c8`: `ContextDllCreateObjectContext`
- `0x1800168b1`: `ContextDllCreateObjectContext`
- `0x1800167b9`: `SchemeDllRetrieveEncodedObjectW`
- `0x180016873`: `SchemeDllRetrieveEncodedObjectW`
- `0x1800167de`: `UrlDllGetObjectUrl`
- `0x1800168e4`: `UrlDllGetObjectUrl`
- `0x18001680a`: `TimeValidDllFlushObject`
- `0x18001694a`: `TimeValidDllFlushObject`

## pseudocode

```c
__int64 __fastcall RPORDllMain(HINSTANCE hModule, int a2, void *a3)
{
  void *v5; // rax
  HCRYPTOIDFUNCSET inited; // rax
  struct CTVOAgent **v8; // rcx
  LPCRITICAL_SECTION v9; // rbx

  if ( a2 == 3 )
  {
    v5 = (void *)I_CryptDetachTls((unsigned int)hCryptNetCancelTls);
    if ( v5 )
      operator delete(v5);
    return 1;
  }
  if ( !a2 )
  {
    I_CryptFreeTls((unsigned int)hCryptNetCancelTls, CancelRetrievalFree);
    if ( a3 )
      g_fTVOAgentProcessExit = 1;
    v9 = g_pProcessTVOAgent;
    if ( g_pProcessTVOAgent )
    {
      CTVOAgent::~CTVOAgent(g_pProcessTVOAgent);
      operator delete(v9);
    }
    DeleteCriticalSection(&CrobuCriticalSection);
    DeleteOfflineUrlCache();
    MSCtlCloseDefaultStores();
    DeleteCriticalSection(&MSCtlDefaultStoresCriticalSection);
    return 1;
  }
  if ( a2 != 1 )
    return 1;
  hSchemeRetrieveFuncSet = CryptInitOIDFunctionSet("SchemeDllRetrieveEncodedObjectW", 0);
  hContextCreateFuncSet = CryptInitOIDFunctionSet("ContextDllCreateObjectContext", 0);
  hGetObjectUrlFuncSet = CryptInitOIDFunctionSet("UrlDllGetObjectUrl", 0);
  hGetTimeValidObjectFuncSet = CryptInitOIDFunctionSet("TimeValidDllGetObject", 0);
  inited = CryptInitOIDFunctionSet("TimeValidDllFlushObject", 0);
  hFlushTimeValidObjectFuncSet = inited;
  if ( hSchemeRetrieveFuncSet )
  {
    if ( hContextCreateFuncSet )
    {
      if ( hGetObjectUrlFuncSet )
      {
        if ( hGetTimeValidObjectFuncSet )
        {
          if ( inited )
          {
            if ( CryptInstallOIDFunctionAddress(hModule, 1u, "SchemeDllRetrieveEncodedObjectW", 4u, &rgFuncEntry, 0) )
            {
              if ( CryptInstallOIDFunctionAddress(hModule, 1u, "ContextDllCreateObjectContext", 5u, &stru_180028010, 0) )
              {
                if ( CryptInstallOIDFunctionAddress(hModule, 1u, "UrlDllGetObjectUrl", 0xDu, &stru_180028060, 0) )
                {
                  if ( CryptInstallOIDFunctionAddress(hModule, 1u, "TimeValidDllGetObject", 5u, &stru_180028170, 0) )
                  {
                    if ( CryptInstallOIDFunctionAddress(hModule, 1u, "TimeValidDllFlushObject", 5u, &stru_1800281C0, 0) )
                    {
                      hCryptNetCancelTls = I_CryptAllocTls();
                      if ( hCryptNetCancelTls )
                      {
                        Pki_InitializeCriticalSection(&OfflineUrlCacheCriticalSection);
                        Pki_InitializeCriticalSection(&CrobuCriticalSection);
                        hCrobuModule = hModule;
                        if ( (unsigned int)CreateProcessTVOAgent(v8) )
                        {
                          Pki_InitializeCriticalSection(&MSCtlDefaultStoresCriticalSection);
                          return 1;
                        }
                        I_CryptFreeTls((unsigned int)hCryptNetCancelTls, CancelRetrievalFree);
                        DeleteCriticalSection(&CrobuCriticalSection);
                        DeleteOfflineUrlCache();
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180016770  mov     [rsp+arg_0], rbx
0x180016775  push    rdi
0x180016776  sub     rsp, 30h
0x18001677a  mov     rdi, r8
0x18001677d  mov     rbx, rcx
0x180016780  cmp     edx, 3
0x180016783  jnz     short loc_1800167AA
0x180016785  mov     ecx, cs:hCryptNetCancelTls
0x18001678b  call    cs:__imp_I_CryptDetachTls
0x180016791  test    rax, rax
0x180016794  jnz     loc_180016A50
0x18001679a  mov     eax, 1
0x18001679f  mov     rbx, [rsp+38h+arg_0]
0x1800167a4  add     rsp, 30h
0x1800167a8  pop     rdi
0x1800167a9  retn
0x1800167aa  test    edx, edx
0x1800167ac  jz      loc_1800169E9
0x1800167b2  cmp     edx, 1
0x1800167b5  jnz     short loc_18001679A
0x1800167b7  xor     edx, edx; dwFlags
0x1800167b9  lea     rcx, aSchemedllretri; "SchemeDllRetrieveEncodedObjectW"
0x1800167c0  call    cs:__imp_CryptInitOIDFunctionSet
0x1800167c6  xor     edx, edx; dwFlags
0x1800167c8  lea     rcx, aContextdllcrea; "ContextDllCreateObjectContext"
0x1800167cf  mov     cs:hSchemeRetrieveFuncSet, rax
0x1800167d6  call    cs:__imp_CryptInitOIDFunctionSet
0x1800167dc  xor     edx, edx; dwFlags
0x1800167de  lea     rcx, pszFuncName; "UrlDllGetObjectUrl"
0x1800167e5  mov     cs:hContextCreateFuncSet, rax
0x1800167ec  call    cs:__imp_CryptInitOIDFunctionSet
0x1800167f2  xor     edx, edx; dwFlags
0x1800167f4  lea     rcx, aTimevaliddllge; "TimeValidDllGetObject"
0x1800167fb  mov     cs:hGetObjectUrlFuncSet, rax
0x180016802  call    cs:__imp_CryptInitOIDFunctionSet
0x180016808  xor     edx, edx; dwFlags
0x18001680a  lea     rcx, aTimevaliddllfl; "TimeValidDllFlushObject"
0x180016811  mov     cs:?hGetTimeValidObjectFuncSet@@3PEAXEA, rax; void * hGetTimeValidObjectFuncSet
0x180016818  call    cs:__imp_CryptInitOIDFunctionSet
0x18001681e  cmp     cs:hSchemeRetrieveFuncSet, 0
0x180016826  mov     cs:?hFlushTimeValidObjectFuncSet@@3PEAXEA, rax; void * hFlushTimeValidObjectFuncSet
0x18001682d  jz      loc_1800169DC
0x180016833  cmp     cs:hContextCreateFuncSet, 0
0x18001683b  jz      loc_1800169DC
0x180016841  cmp     cs:hGetObjectUrlFuncSet, 0
0x180016849  jz      loc_1800169DC
0x18001684f  cmp     cs:?hGetTimeValidObjectFuncSet@@3PEAXEA, 0; void * hGetTimeValidObjectFuncSet
0x180016857  jz      loc_1800169DC
0x18001685d  test    rax, rax
0x180016860  jz      loc_1800169DC
0x180016866  lea     rax, rgFuncEntry
0x18001686d  xor     edi, edi
0x18001686f  mov     [rsp+38h+dwFlags], edi; dwFlags
0x180016873  lea     r8, aSchemedllretri; "SchemeDllRetrieveEncodedObjectW"
0x18001687a  mov     r9d, 4; cFuncEntry
0x180016880  mov     [rsp+38h+rgFuncEntry], rax; rgFuncEntry
0x180016885  mov     edx, 1; dwEncodingType
0x18001688a  mov     rcx, rbx; hModule
0x18001688d  call    cs:__imp_CryptInstallOIDFunctionAddress
0x180016893  test    eax, eax
0x180016895  jz      loc_1800169DC
0x18001689b  lea     rax, stru_180028010
0x1800168a2  mov     [rsp+38h+dwFlags], edi; dwFlags
0x1800168a6  mov     r9d, 5; cFuncEntry
0x1800168ac  mov     [rsp+38h+rgFuncEntry], rax; rgFuncEntry
0x1800168b1  lea     r8, aContextdllcrea; "ContextDllCreateObjectContext"
0x1800168b8  mov     edx, 1; dwEncodingType
0x1800168bd  mov     rcx, rbx; hModule
0x1800168c0  call    cs:__imp_CryptInstallOIDFunctionAddress
0x1800168c6  test    eax, eax
0x1800168c8  jz      loc_1800169DC
0x1800168ce  lea     rax, stru_180028060
0x1800168d5  mov     [rsp+38h+dwFlags], edi; dwFlags
0x1800168d9  mov     r9d, 0Dh; cFuncEntry
0x1800168df  mov     [rsp+38h+rgFuncEntry], rax; rgFuncEntry
0x1800168e4  lea     r8, pszFuncName; "UrlDllGetObjectUrl"
0x1800168eb  mov     edx, 1; dwEncodingType
0x1800168f0  mov     rcx, rbx; hModule
0x1800168f3  call    cs:__imp_CryptInstallOIDFunctionAddress
0x1800168f9  test    eax, eax
0x1800168fb  jz      loc_1800169DC
0x180016901  lea     rax, stru_180028170
0x180016908  mov     [rsp+38h+dwFlags], edi; dwFlags
0x18001690c  mov     r9d, 5; cFuncEntry
0x180016912  mov     [rsp+38h+rgFuncEntry], rax; rgFuncEntry
0x180016917  lea     r8, aTimevaliddllge; "TimeValidDllGetObject"
0x18001691e  mov     edx, 1; dwEncodingType
0x180016923  mov     rcx, rbx; hModule
0x180016926  call    cs:__imp_CryptInstallOIDFunctionAddress
0x18001692c  test    eax, eax
0x18001692e  jz      loc_1800169DC
0x180016934  lea     rax, stru_1800281C0
0x18001693b  mov     [rsp+38h+dwFlags], edi; dwFlags
0x18001693f  mov     r9d, 5; cFuncEntry
0x180016945  mov     [rsp+38h+rgFuncEntry], rax; rgFuncEntry
0x18001694a  lea     r8, aTimevaliddllfl; "TimeValidDllFlushObject"
0x180016951  mov     edx, 1; dwEncodingType
0x180016956  mov     rcx, rbx; hModule
0x180016959  call    cs:__imp_CryptInstallOIDFunctionAddress
0x18001695f  test    eax, eax
0x180016961  jz      short loc_1800169DC
0x180016963  call    cs:__imp_I_CryptAllocTls
0x180016969  mov     cs:hCryptNetCancelTls, eax
0x18001696f  test    eax, eax
0x180016971  jz      short loc_1800169DC
0x180016973  lea     rcx, ?OfflineUrlCacheCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION OfflineUrlCacheCriticalSection
0x18001697a  call    Pki_InitializeCriticalSection
0x18001697f  lea     rcx, ?CrobuCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION CrobuCriticalSection
0x180016986  call    Pki_InitializeCriticalSection
0x18001698b  mov     cs:?hCrobuModule@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * hCrobuModule
0x180016992  call    ?CreateProcessTVOAgent@@YAHPEAPEAVCTVOAgent@@@Z; CreateProcessTVOAgent(CTVOAgent * *)
0x180016997  test    eax, eax
0x180016999  jz      short loc_1800169B7
0x18001699b  lea     rcx, ?MSCtlDefaultStoresCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION MSCtlDefaultStoresCriticalSection
0x1800169a2  call    Pki_InitializeCriticalSection
0x1800169a7  mov     eax, 1
0x1800169ac  mov     rbx, [rsp+38h+arg_0]
0x1800169b1  add     rsp, 30h
0x1800169b5  pop     rdi
0x1800169b6  retn
0x1800169b7  mov     ecx, cs:hCryptNetCancelTls
0x1800169bd  lea     rdx, CancelRetrievalFree
0x1800169c4  call    cs:__imp_I_CryptFreeTls
0x1800169ca  lea     rcx, ?CrobuCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800169d1  call    cs:__imp_DeleteCriticalSection
0x1800169d7  call    ?DeleteOfflineUrlCache@@YAXXZ; DeleteOfflineUrlCache(void)
0x1800169dc  mov     rbx, [rsp+38h+arg_0]
0x1800169e1  xor     eax, eax
0x1800169e3  add     rsp, 30h
0x1800169e7  pop     rdi
0x1800169e8  retn
0x1800169e9  mov     ecx, cs:hCryptNetCancelTls
0x1800169ef  lea     rdx, CancelRetrievalFree
0x1800169f6  call    cs:__imp_I_CryptFreeTls
0x1800169fc  test    rdi, rdi
0x1800169ff  jz      short loc_180016A0B
0x180016a01  mov     cs:?g_fTVOAgentProcessExit@@3HA, 1; int g_fTVOAgentProcessExit
0x180016a0b  mov     rbx, cs:?g_pProcessTVOAgent@@3PEAVCTVOAgent@@EA; CTVOAgent * g_pProcessTVOAgent
0x180016a12  test    rbx, rbx
0x180016a15  jz      short loc_180016A27
0x180016a17  mov     rcx, rbx; lpCriticalSection
0x180016a1a  call    ??1CTVOAgent@@QEAA@XZ; CTVOAgent::~CTVOAgent(void)
0x180016a1f  mov     rcx, rbx; hMem
0x180016a22  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016a27  lea     rcx, ?CrobuCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180016a2e  call    cs:__imp_DeleteCriticalSection
0x180016a34  call    ?DeleteOfflineUrlCache@@YAXXZ; DeleteOfflineUrlCache(void)
0x180016a39  call    ?MSCtlCloseDefaultStores@@YAXXZ; MSCtlCloseDefaultStores(void)
0x180016a3e  lea     rcx, ?MSCtlDefaultStoresCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180016a45  call    cs:__imp_DeleteCriticalSection
0x180016a4b  jmp     loc_18001679A
0x180016a50  mov     rcx, rax; hMem
0x180016a53  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016a58  jmp     loc_18001679A
```
