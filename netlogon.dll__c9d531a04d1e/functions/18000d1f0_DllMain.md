# DllMain

- ea: `0x18000d1f0`
- end: `0x18000d411`
- name: `DllMain`
- size: `545`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x18000e0e4`

## callees

- `0x18000122c`
- `0x18000d1f0`
- `0x18000d418`
- `0x18000d5bc`
- `0x18000d710`
- `0x1800161bc`
- `0x180018414`
- `0x180074218`
- `0x180074250`
- `0x180074308`
- `0x180080710`
- `0x180088a20`
- `0x18008972c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000d287`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000d287`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d334`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d334`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000d2c0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000d2c0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d38a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d38a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d37d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d37d`
- `ntdll!EtwUnregisterTraceGuids` at `0x18000d3e0`
- `ntdll!EtwUnregisterTraceGuids` at `0x18000d3e0`
- `ntdll!RtlDeleteCriticalSection` at `0x18000d31f`
- `ntdll!RtlDeleteCriticalSection` at `0x18000d31f`
- `ntdll!RtlInitializeCriticalSection` at `0x18000d2a9`
- `ntdll!RtlInitializeCriticalSection` at `0x18000d2a9`

## string_xrefs

- `0x18000d359`: `onecore\ds\netapi\svcdlls\logonsrv\coreloc\loccache.cxx`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  int v4; // esi
  __int64 v5; // rax
  char *v6; // r9
  struct _NL_DC_DOMAIN_ENTRY ***v7; // rbp
  ScannerInfoNameMappings *v8; // rdi

  if ( fdwReason == 1 )
  {
    McGenEventRegister_EtwEventRegister(hinstDLL, fdwReason, lpvReserved);
    qword_1800F1CB0 = 1;
    qword_1800F1CA8 = 0;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_NETLOGON;
    WPP_GLOBAL_Control = (ScannerInfoNameMappings *)&WPP_MAIN_CB;
    WPP_MAIN_CB = 0;
    WppInitUm();
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_65daa35750393fc29f9029adaaa07f67_Traceguids);
    SafeAllocaInitialize();
    NlGlobalMsvEnabled = 0;
    NlGlobalMsvThreadCount = 0;
    NlGlobalMsvTerminateEvent = 0;
    DisableThreadLibraryCalls(hinstDLL);
    v4 = NlInitChangeLog();
    if ( v4 >= 0 )
    {
      dword_1800F2030 = 1;
      RtlInitializeCriticalSection(&NlGlobalMsvCritSect);
      dword_1800F202C = 1;
      InitializeCriticalSection(&NlDcCritSect);
      NlDcDomainCount = 0;
      qword_1800F1D18 = (struct _NL_DC_DOMAIN_ENTRY *)&NlDcDomainList;
      NlDcDomainList = (struct _NL_DC_DOMAIN_ENTRY *)&NlDcDomainList;
      dword_1800F2028 = 1;
    }
    v5 = TlgRegisterAggregateProviderEx();
  }
  else
  {
    v4 = 0;
    if ( !fdwReason )
    {
      if ( dword_1800F2030 )
        v4 = NlCloseChangeLog();
      if ( dword_1800F202C )
        RtlDeleteCriticalSection(&NlGlobalMsvCritSect);
      if ( dword_1800F2028 )
      {
        EnterCriticalSection(&NlDcCritSect);
        while ( 1 )
        {
          v7 = (struct _NL_DC_DOMAIN_ENTRY ***)NlDcDomainList;
          if ( NlDcDomainList == (struct _NL_DC_DOMAIN_ENTRY *)&NlDcDomainList )
            break;
          if ( *((_DWORD *)NlDcDomainList + 4) != 1 )
            NlAssertFailed(
              "NlDcDomainEntry->ReferenceCount == 1",
              "onecore\\ds\\netapi\\svcdlls\\logonsrv\\coreloc\\loccache.cxx",
              2291,
              v6);
          NetpDcDeleteDomainEntry(v7);
        }
        LeaveCriticalSection(&NlDcCritSect);
        DeleteCriticalSection(&NlDcCritSect);
      }
      NlUninitializeLocatorConnectionCache();
      McGenEventUnregister_EtwEventUnregister();
      v8 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_65daa35750393fc29f9029adaaa07f67_Traceguids);
        v8 = WPP_GLOBAL_Control;
      }
      if ( v8 != (ScannerInfoNameMappings *)&WPP_GLOBAL_Control )
      {
        while ( v8 )
        {
          if ( *((_QWORD *)v8 + 1) )
          {
            EtwUnregisterTraceGuids();
            *((_QWORD *)v8 + 1) = 0;
          }
          v8 = *(ScannerInfoNameMappings **)v8;
        }
        WPP_GLOBAL_Control = (ScannerInfoNameMappings *)&WPP_GLOBAL_Control;
      }
      v5 = TraceLoggingUnregister_EtwEventUnregister();
    }
  }
  LOBYTE(v5) = v4 >= 0;
  return v5;
}

```

## disassembly

```asm
0x18000d1f0  push    rbx
0x18000d1f2  push    rbp
0x18000d1f3  push    rsi
0x18000d1f4  push    rdi
0x18000d1f5  sub     rsp, 28h
0x18000d1f9  mov     rdi, rcx
0x18000d1fc  cmp     edx, 1
0x18000d1ff  jnz     loc_18000D2F5
0x18000d205  call    McGenEventRegister_EtwEventRegister
0x18000d20a  xor     ebx, ebx
0x18000d20c  mov     cs:qword_1800F1CB0, 1
0x18000d217  lea     rax, WPP_ThisDir_CTLGUID_NETLOGON
0x18000d21e  mov     cs:qword_1800F1CA8, rbx
0x18000d225  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18000d22c  lea     rax, WPP_MAIN_CB
0x18000d233  mov     cs:WPP_GLOBAL_Control, rax
0x18000d23a  mov     cs:WPP_MAIN_CB, rbx
0x18000d241  call    WppInitUm
0x18000d246  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d24d  test    byte ptr [rcx+1Ch], 2
0x18000d251  jz      short loc_18000D26C
0x18000d253  cmp     byte ptr [rcx+19h], 5
0x18000d257  jb      short loc_18000D26C
0x18000d259  mov     rcx, [rcx+10h]
0x18000d25d  lea     edx, [rbx+0Ah]
0x18000d260  lea     r8, WPP_65daa35750393fc29f9029adaaa07f67_Traceguids
0x18000d267  call    WPP_SF_
0x18000d26c  call    SafeAllocaInitialize
0x18000d271  mov     rcx, rdi; hLibModule
0x18000d274  mov     cs:?NlGlobalMsvEnabled@@3HA, ebx; int NlGlobalMsvEnabled
0x18000d27a  mov     cs:?NlGlobalMsvThreadCount@@3KA, ebx; ulong NlGlobalMsvThreadCount
0x18000d280  mov     cs:?NlGlobalMsvTerminateEvent@@3PEAXEA, rbx; void * NlGlobalMsvTerminateEvent
0x18000d287  call    cs:__imp_DisableThreadLibraryCalls
0x18000d28d  call    ?NlInitChangeLog@@YAJXZ; NlInitChangeLog(void)
0x18000d292  mov     esi, eax
0x18000d294  test    eax, eax
0x18000d296  js      short loc_18000D2EB
0x18000d298  lea     rcx, ?NlGlobalMsvCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18000d29f  mov     cs:dword_1800F2030, 1
0x18000d2a9  call    cs:__imp_RtlInitializeCriticalSection
0x18000d2af  lea     rcx, ?NlDcCritSect@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d2b6  mov     cs:dword_1800F202C, 1
0x18000d2c0  call    cs:__imp_InitializeCriticalSection
0x18000d2c6  lea     rdi, ?NlDcDomainList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlDcDomainList
0x18000d2cd  mov     cs:?NlDcDomainCount@@3KA, ebx; ulong NlDcDomainCount
0x18000d2d3  mov     cs:qword_1800F1D18, rdi
0x18000d2da  mov     cs:?NlDcDomainList@@3U_LIST_ENTRY@@A, rdi; _LIST_ENTRY NlDcDomainList
0x18000d2e1  mov     cs:dword_1800F2028, 1
0x18000d2eb  call    TlgRegisterAggregateProviderEx
0x18000d2f0  jmp     loc_18000D3FE
0x18000d2f5  xor     ebx, ebx
0x18000d2f7  mov     esi, ebx
0x18000d2f9  test    edx, edx
0x18000d2fb  jnz     loc_18000D3FE
0x18000d301  cmp     cs:dword_1800F2030, ebx
0x18000d307  jz      short loc_18000D310
0x18000d309  call    ?NlCloseChangeLog@@YAJXZ; NlCloseChangeLog(void)
0x18000d30e  mov     esi, eax
0x18000d310  cmp     cs:dword_1800F202C, ebx
0x18000d316  jz      short loc_18000D325
0x18000d318  lea     rcx, ?NlGlobalMsvCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18000d31f  call    cs:__imp_RtlDeleteCriticalSection
0x18000d325  cmp     cs:dword_1800F2028, ebx
0x18000d32b  jz      short loc_18000D390
0x18000d32d  lea     rcx, ?NlDcCritSect@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d334  call    cs:__imp_EnterCriticalSection
0x18000d33a  lea     rdi, ?NlDcDomainList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlDcDomainList
0x18000d341  mov     rbp, cs:?NlDcDomainList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlDcDomainList
0x18000d348  cmp     rbp, rdi
0x18000d34b  jz      short loc_18000D376
0x18000d34d  cmp     dword ptr [rbp+10h], 1
0x18000d351  jz      short loc_18000D36C
0x18000d353  mov     r8d, 8F3h; unsigned int
0x18000d359  lea     rdx, aOnecoreDsNetap_21; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18000d360  lea     rcx, aNldcdomainentr; "NlDcDomainEntry->ReferenceCount == 1"
0x18000d367  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18000d36c  mov     rcx, rbp; struct _NL_DC_DOMAIN_ENTRY *
0x18000d36f  call    ?NetpDcDeleteDomainEntry@@YAXPEAU_NL_DC_DOMAIN_ENTRY@@@Z; NetpDcDeleteDomainEntry(_NL_DC_DOMAIN_ENTRY *)
0x18000d374  jmp     short loc_18000D341
0x18000d376  lea     rcx, ?NlDcCritSect@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d37d  call    cs:__imp_LeaveCriticalSection
0x18000d383  lea     rcx, ?NlDcCritSect@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d38a  call    cs:__imp_DeleteCriticalSection
0x18000d390  call    ?NlUninitializeLocatorConnectionCache@@YAXXZ; NlUninitializeLocatorConnectionCache(void)
0x18000d395  call    McGenEventUnregister_EtwEventUnregister
0x18000d39a  mov     rdi, cs:WPP_GLOBAL_Control
0x18000d3a1  test    byte ptr [rdi+1Ch], 2
0x18000d3a5  jz      short loc_18000D3C9
0x18000d3a7  cmp     byte ptr [rdi+19h], 5
0x18000d3ab  jb      short loc_18000D3C9
0x18000d3ad  mov     rcx, [rdi+10h]
0x18000d3b1  lea     r8, WPP_65daa35750393fc29f9029adaaa07f67_Traceguids
0x18000d3b8  mov     edx, 0Bh
0x18000d3bd  call    WPP_SF_
0x18000d3c2  mov     rdi, cs:WPP_GLOBAL_Control
0x18000d3c9  lea     rbp, WPP_GLOBAL_Control
0x18000d3d0  cmp     rdi, rbp
0x18000d3d3  jz      short loc_18000D3F9
0x18000d3d5  jmp     short loc_18000D3ED
0x18000d3d7  mov     rcx, [rdi+8]
0x18000d3db  test    rcx, rcx
0x18000d3de  jz      short loc_18000D3EA
0x18000d3e0  call    cs:__imp_EtwUnregisterTraceGuids
0x18000d3e6  mov     [rdi+8], rbx
0x18000d3ea  mov     rdi, [rdi]
0x18000d3ed  test    rdi, rdi
0x18000d3f0  jnz     short loc_18000D3D7
0x18000d3f2  mov     cs:WPP_GLOBAL_Control, rbp
0x18000d3f9  call    TraceLoggingUnregister_EtwEventUnregister
0x18000d3fe  shr     esi, 1Fh
0x18000d401  xor     sil, 1
0x18000d405  mov     al, sil
0x18000d408  add     rsp, 28h
0x18000d40c  pop     rdi
0x18000d40d  pop     rsi
0x18000d40e  pop     rbp
0x18000d40f  pop     rbx
0x18000d410  retn
```
