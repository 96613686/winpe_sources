# IsatapUpdateRouterAddressAsyncCallback

- ea: `0x180034d90`
- end: `0x180034f21`
- name: `IsatapUpdateRouterAddressAsyncCallback`
- size: `401`
- prototype: `void __stdcall(DWORD dwError, DWORD dwBytes, LPWSAOVERLAPPED lpOverlapped)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180009010`
- `0x18000cea0`
- `0x18000d7c0`
- `0x180022b40`
- `0x180034d90`
- `0x180034f28`
- `0x180037a98`
- `0x180042f70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034de0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034de0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034e17`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034e17`
- `WS2_32!FreeAddrInfoExW` at `0x180034ed3`
- `WS2_32!FreeAddrInfoExW` at `0x180034ed3`

## string_xrefs

- `0x180034e5d`: `onecoreuap\net\netio\iphlpsvc\service\isatap.c`
- `0x180034eac`: `onecoreuap\net\netio\iphlpsvc\service\isatap.c`
- `0x180034eba`: `IsatapUpdateRouterAddressAsyncCallback received error %d`
- `0x180034db5`: `Entered: IsatapUpdateRouterAddressAsyncCallback`
- `0x180034e50`: `IsatapUpdateRouterAddressAsyncCallback`
- `0x180034e9f`: `IsatapUpdateRouterAddressAsyncCallback`
- `0x180034ef9`: `Leaving: IsatapUpdateRouterAddressAsyncCallback`

## pseudocode

```c
void __fastcall IsatapUpdateRouterAddressAsyncCallback(DWORD dwError, DWORD dwBytes, LPWSAOVERLAPPED lpOverlapped)
{
  LPWSAOVERLAPPED v5; // rsi
  struct addrinfoexW *hEvent; // rbp
  char v7; // di
  ULONG_PTR InternalHigh; // r15
  __int64 v9; // r8

  if ( IpHlpSvcEtwEnabled && (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800000) != 0 )
    McTemplateU0z_EventWriteTransfer(
      MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
      EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE,
      L"Entered: IsatapUpdateRouterAddressAsyncCallback");
  v5 = lpOverlapped - 150;
  EnterCriticalSection((LPCRITICAL_SECTION)&v5[148]);
  hEvent = (struct addrinfoexW *)v5[149].hEvent;
  v7 = BYTE1(v5[149].InternalHigh);
  InternalHigh = v5[151].InternalHigh;
  v5[149].hEvent = 0;
  IsatapUpdateRouterAddressAsyncCleanupAndSetEvent(v5);
  LeaveCriticalSection((LPCRITICAL_SECTION)&v5[148]);
  v9 = 0;
  if ( dwError != 11001 )
    v9 = dwError;
  if ( v7 || (_DWORD)v9 )
  {
    EventWrite0(0x2000000, L"IsatapUpdateRouterAddressAsyncCallback received error %d", v9);
  }
  else if ( (v5->InternalHigh & 0x100000000LL) == 0
         && (unsigned int)GetAndTraceLock(
                            "onecoreuap\\net\\netio\\iphlpsvc\\service\\isatap.c",
                            "IsatapUpdateRouterAddressAsyncCallback",
                            1441,
                            g_IsatapLock) )
  {
    if ( (int)v5[83].OffsetHigh <= 0
      && LODWORD(v5->InternalHigh)
      && (v5->InternalHigh & 0x100000000LL) == 0
      && InternalHigh == v5[151].InternalHigh )
    {
      IsatapUpdatePotentialRouterList(v5, hEvent);
      hEvent = 0;
    }
    ReleaseAndTraceLock(
      "onecoreuap\\net\\netio\\iphlpsvc\\service\\isatap.c",
      "IsatapUpdateRouterAddressAsyncCallback",
      1474,
      g_IsatapLock);
  }
  if ( hEvent )
    FreeAddrInfoExW(hEvent);
  IsatapDereferenceInterfaceForAsyncCall(v5);
  if ( IpHlpSvcEtwEnabled )
  {
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800000) != 0 )
      McTemplateU0z_EventWriteTransfer(
        MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
        EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE,
        L"Leaving: IsatapUpdateRouterAddressAsyncCallback");
  }
}

```

## disassembly

```asm
0x180034d90  push    rbx
0x180034d92  push    rbp
0x180034d93  push    rsi
0x180034d94  push    rdi
0x180034d95  push    r14
0x180034d97  push    r15
0x180034d99  sub     rsp, 28h
0x180034d9d  cmp     cs:IpHlpSvcEtwEnabled, 0
0x180034da4  mov     rsi, r8
0x180034da7  mov     r14d, ecx
0x180034daa  jz      short loc_180034DCF
0x180034dac  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 0
0x180034db3  jge     short loc_180034DCF
0x180034db5  lea     r8, aEnteredIsatapu_0; "Entered: IsatapUpdateRouterAddressAsync"...
0x180034dbc  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x180034dc3  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180034dca  call    McTemplateU0z_EventWriteTransfer
0x180034dcf  add     rsi, 0FFFFFFFFFFFFED40h
0x180034dd6  lea     rbx, [rsi+1280h]
0x180034ddd  mov     rcx, rbx; lpCriticalSection
0x180034de0  call    cs:__imp_EnterCriticalSection
0x180034de7  nop     dword ptr [rax+rax+00h]
0x180034dec  mov     rbp, [rsi+12B8h]
0x180034df3  mov     rcx, rsi
0x180034df6  mov     dil, [rsi+12A9h]
0x180034dfd  mov     r15, [rsi+12E8h]
0x180034e04  mov     qword ptr [rsi+12B8h], 0
0x180034e0f  call    IsatapUpdateRouterAddressAsyncCleanupAndSetEvent
0x180034e14  mov     rcx, rbx; lpCriticalSection
0x180034e17  call    cs:__imp_LeaveCriticalSection
0x180034e1e  nop     dword ptr [rax+rax+00h]
0x180034e23  xor     r8d, r8d
0x180034e26  cmp     r14d, 2AF9h
0x180034e2d  cmovnz  r8d, r14d
0x180034e31  test    dil, dil
0x180034e34  jnz     loc_180034EBA
0x180034e3a  test    r8d, r8d
0x180034e3d  jnz     short loc_180034EBA
0x180034e3f  test    byte ptr [rsi+0Ch], 1
0x180034e43  jnz     loc_180034ECB
0x180034e49  mov     r9, cs:g_IsatapLock
0x180034e50  lea     rdx, aIsatapupdatero_0; "IsatapUpdateRouterAddressAsyncCallback"
0x180034e57  mov     r8d, 5A1h
0x180034e5d  lea     rcx, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180034e64  call    GetAndTraceLock
0x180034e69  test    eax, eax
0x180034e6b  jz      short loc_180034ECB
0x180034e6d  cmp     dword ptr [rsi+0A74h], 0
0x180034e74  jg      short loc_180034E98
0x180034e76  cmp     dword ptr [rsi+8], 0
0x180034e7a  jz      short loc_180034E98
0x180034e7c  test    byte ptr [rsi+0Ch], 1
0x180034e80  jnz     short loc_180034E98
0x180034e82  cmp     r15, [rsi+12E8h]
0x180034e89  jnz     short loc_180034E98
0x180034e8b  mov     rdx, rbp
0x180034e8e  mov     rcx, rsi
0x180034e91  call    IsatapUpdatePotentialRouterList
0x180034e96  xor     ebp, ebp
0x180034e98  mov     r9, cs:g_IsatapLock
0x180034e9f  lea     rdx, aIsatapupdatero_0; "IsatapUpdateRouterAddressAsyncCallback"
0x180034ea6  mov     r8d, 5C2h
0x180034eac  lea     rcx, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180034eb3  call    ReleaseAndTraceLock
0x180034eb8  jmp     short loc_180034ECB
0x180034eba  lea     rdx, aIsatapupdatero_1; "IsatapUpdateRouterAddressAsyncCallback "...
0x180034ec1  mov     ecx, 2000000h
0x180034ec6  call    EventWrite0
0x180034ecb  test    rbp, rbp
0x180034ece  jz      short loc_180034EDF
0x180034ed0  mov     rcx, rbp; pAddrInfoEx
0x180034ed3  call    cs:__imp_FreeAddrInfoExW
0x180034eda  nop     dword ptr [rax+rax+00h]
0x180034edf  mov     rcx, rsi
0x180034ee2  call    IsatapDereferenceInterfaceForAsyncCall
0x180034ee7  cmp     cs:IpHlpSvcEtwEnabled, 0
0x180034eee  jz      short loc_180034F13
0x180034ef0  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 0
0x180034ef7  jge     short loc_180034F13
0x180034ef9  lea     r8, aLeavingIsatapu_4; "Leaving: IsatapUpdateRouterAddressAsync"...
0x180034f00  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x180034f07  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180034f0e  call    McTemplateU0z_EventWriteTransfer
0x180034f13  add     rsp, 28h
0x180034f17  pop     r15
0x180034f19  pop     r14
0x180034f1b  pop     rdi
0x180034f1c  pop     rsi
0x180034f1d  pop     rbp
0x180034f1e  pop     rbx
0x180034f1f  retn
```
