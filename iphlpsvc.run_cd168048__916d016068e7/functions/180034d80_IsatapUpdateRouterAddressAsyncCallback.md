# IsatapUpdateRouterAddressAsyncCallback

- ea: `0x180034d80`
- end: `0x180034f11`
- name: `IsatapUpdateRouterAddressAsyncCallback`
- size: `401`
- prototype: `void __stdcall(DWORD dwError, DWORD dwBytes, LPWSAOVERLAPPED lpOverlapped)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180009000`
- `0x18000ce90`
- `0x18000d7b0`
- `0x180022b30`
- `0x180034d80`
- `0x180034f18`
- `0x180037a88`
- `0x180042fb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034dd0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034dd0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034e07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034e07`
- `WS2_32!FreeAddrInfoExW` at `0x180034ec3`
- `WS2_32!FreeAddrInfoExW` at `0x180034ec3`

## string_xrefs

- `0x180034e4d`: `onecoreuap\net\netio\iphlpsvc\service\isatap.c`
- `0x180034e9c`: `onecoreuap\net\netio\iphlpsvc\service\isatap.c`
- `0x180034eaa`: `IsatapUpdateRouterAddressAsyncCallback received error %d`
- `0x180034da5`: `Entered: IsatapUpdateRouterAddressAsyncCallback`
- `0x180034e40`: `IsatapUpdateRouterAddressAsyncCallback`
- `0x180034e8f`: `IsatapUpdateRouterAddressAsyncCallback`
- `0x180034ee9`: `Leaving: IsatapUpdateRouterAddressAsyncCallback`

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
0x180034d80  push    rbx
0x180034d82  push    rbp
0x180034d83  push    rsi
0x180034d84  push    rdi
0x180034d85  push    r14
0x180034d87  push    r15
0x180034d89  sub     rsp, 28h
0x180034d8d  cmp     cs:IpHlpSvcEtwEnabled, 0
0x180034d94  mov     rsi, r8
0x180034d97  mov     r14d, ecx
0x180034d9a  jz      short loc_180034DBF
0x180034d9c  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 0
0x180034da3  jge     short loc_180034DBF
0x180034da5  lea     r8, aEnteredIsatapu_0; "Entered: IsatapUpdateRouterAddressAsync"...
0x180034dac  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x180034db3  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180034dba  call    McTemplateU0z_EventWriteTransfer
0x180034dbf  add     rsi, 0FFFFFFFFFFFFED40h
0x180034dc6  lea     rbx, [rsi+1280h]
0x180034dcd  mov     rcx, rbx; lpCriticalSection
0x180034dd0  call    cs:__imp_EnterCriticalSection
0x180034dd7  nop     dword ptr [rax+rax+00h]
0x180034ddc  mov     rbp, [rsi+12B8h]
0x180034de3  mov     rcx, rsi
0x180034de6  mov     dil, [rsi+12A9h]
0x180034ded  mov     r15, [rsi+12E8h]
0x180034df4  mov     qword ptr [rsi+12B8h], 0
0x180034dff  call    IsatapUpdateRouterAddressAsyncCleanupAndSetEvent
0x180034e04  mov     rcx, rbx; lpCriticalSection
0x180034e07  call    cs:__imp_LeaveCriticalSection
0x180034e0e  nop     dword ptr [rax+rax+00h]
0x180034e13  xor     r8d, r8d
0x180034e16  cmp     r14d, 2AF9h
0x180034e1d  cmovnz  r8d, r14d
0x180034e21  test    dil, dil
0x180034e24  jnz     loc_180034EAA
0x180034e2a  test    r8d, r8d
0x180034e2d  jnz     short loc_180034EAA
0x180034e2f  test    byte ptr [rsi+0Ch], 1
0x180034e33  jnz     loc_180034EBB
0x180034e39  mov     r9, cs:g_IsatapLock
0x180034e40  lea     rdx, aIsatapupdatero_0; "IsatapUpdateRouterAddressAsyncCallback"
0x180034e47  mov     r8d, 5A1h
0x180034e4d  lea     rcx, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180034e54  call    GetAndTraceLock
0x180034e59  test    eax, eax
0x180034e5b  jz      short loc_180034EBB
0x180034e5d  cmp     dword ptr [rsi+0A74h], 0
0x180034e64  jg      short loc_180034E88
0x180034e66  cmp     dword ptr [rsi+8], 0
0x180034e6a  jz      short loc_180034E88
0x180034e6c  test    byte ptr [rsi+0Ch], 1
0x180034e70  jnz     short loc_180034E88
0x180034e72  cmp     r15, [rsi+12E8h]
0x180034e79  jnz     short loc_180034E88
0x180034e7b  mov     rdx, rbp
0x180034e7e  mov     rcx, rsi
0x180034e81  call    IsatapUpdatePotentialRouterList
0x180034e86  xor     ebp, ebp
0x180034e88  mov     r9, cs:g_IsatapLock
0x180034e8f  lea     rdx, aIsatapupdatero_0; "IsatapUpdateRouterAddressAsyncCallback"
0x180034e96  mov     r8d, 5C2h
0x180034e9c  lea     rcx, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180034ea3  call    ReleaseAndTraceLock
0x180034ea8  jmp     short loc_180034EBB
0x180034eaa  lea     rdx, aIsatapupdatero_1; "IsatapUpdateRouterAddressAsyncCallback "...
0x180034eb1  mov     ecx, 2000000h
0x180034eb6  call    EventWrite0
0x180034ebb  test    rbp, rbp
0x180034ebe  jz      short loc_180034ECF
0x180034ec0  mov     rcx, rbp; pAddrInfoEx
0x180034ec3  call    cs:__imp_FreeAddrInfoExW
0x180034eca  nop     dword ptr [rax+rax+00h]
0x180034ecf  mov     rcx, rsi
0x180034ed2  call    IsatapDereferenceInterfaceForAsyncCall
0x180034ed7  cmp     cs:IpHlpSvcEtwEnabled, 0
0x180034ede  jz      short loc_180034F03
0x180034ee0  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 0
0x180034ee7  jge     short loc_180034F03
0x180034ee9  lea     r8, aLeavingIsatapu_4; "Leaving: IsatapUpdateRouterAddressAsync"...
0x180034ef0  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x180034ef7  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180034efe  call    McTemplateU0z_EventWriteTransfer
0x180034f03  add     rsp, 28h
0x180034f07  pop     r15
0x180034f09  pop     r14
0x180034f0b  pop     rdi
0x180034f0c  pop     rsi
0x180034f0d  pop     rbp
0x180034f0e  pop     rbx
0x180034f0f  retn
```
