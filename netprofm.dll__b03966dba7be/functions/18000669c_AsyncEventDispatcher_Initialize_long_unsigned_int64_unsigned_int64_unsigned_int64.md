# AsyncEventDispatcher::Initialize(long (*)(unsigned __int64,unsigned __int64,unsigned __int64))

- ea: `0x18000669c`
- end: `0x18000675c`
- name: `?Initialize@AsyncEventDispatcher@@QEAAJP6AJ_K00@Z@Z`
- size: `192`
- prototype: `__int64 __fastcall(PVOID pv, int (*)(unsigned __int64, unsigned __int64, unsigned __int64))`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002a158`

## callees

- `0x18000669c`
- `0x180006770`
- `0x180033a1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800066e5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800066e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006722`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006722`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180006701`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180006701`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000674c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000674c`

## pseudocode

```c
signed int __fastcall AsyncEventDispatcher::Initialize(
        PVOID pv,
        int (*a2)(unsigned __int64, unsigned __int64, unsigned __int64))
{
  PVOID v3; // rcx
  HANDLE EventW; // rax
  PTP_WORK ThreadpoolWork; // rax
  signed int result; // eax

  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_dc6f70dd1fe8303392f5113b356694e8_Traceguids);
  if ( *(_QWORD *)pv )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v3, a2);
    if ( *(_QWORD *)pv )
      return -2147023649;
  }
  EventW = CreateEventW(0, 1, 1, 0);
  *((_QWORD *)pv + 2) = EventW;
  if ( EventW )
  {
    ThreadpoolWork = CreateThreadpoolWork(AsyncEventDispatcher::EventDispatcher, pv, 0);
    *((_QWORD *)pv + 1) = ThreadpoolWork;
    if ( ThreadpoolWork )
    {
      *(_QWORD *)pv = PublicNetworkListManager::AsyncEventHandler;
      return 0;
    }
    CloseHandle(*((HANDLE *)pv + 2));
    *((_QWORD *)pv + 2) = 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000669c  push    rbx
0x18000669e  sub     rsp, 20h
0x1800066a2  mov     rbx, rcx
0x1800066a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066ac  lea     rax, WPP_GLOBAL_Control
0x1800066b3  cmp     rcx, rax
0x1800066b6  jz      short loc_1800066D3
0x1800066b8  test    byte ptr [rcx+1Ch], 8
0x1800066bc  jz      short loc_1800066D3
0x1800066be  mov     rcx, [rcx+10h]
0x1800066c2  lea     r8, WPP_dc6f70dd1fe8303392f5113b356694e8_Traceguids
0x1800066c9  mov     edx, 0Ah
0x1800066ce  call    WPP_SF_
0x1800066d3  cmp     qword ptr [rbx], 0
0x1800066d7  jnz     short loc_180006736
0x1800066d9  xor     r9d, r9d; lpName
0x1800066dc  xor     ecx, ecx; lpEventAttributes
0x1800066de  lea     edx, [r9+1]; bManualReset
0x1800066e2  mov     r8d, edx; bInitialState
0x1800066e5  call    cs:__imp_CreateEventW
0x1800066eb  mov     [rbx+10h], rax
0x1800066ef  test    rax, rax
0x1800066f2  jz      short loc_180006722
0x1800066f4  xor     r8d, r8d; pcbe
0x1800066f7  lea     rcx, ?EventDispatcher@AsyncEventDispatcher@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800066fe  mov     rdx, rbx; pv
0x180006701  call    cs:__imp_CreateThreadpoolWork
0x180006707  mov     [rbx+8], rax
0x18000670b  test    rax, rax
0x18000670e  jz      short loc_180006748
0x180006710  lea     rax, ?AsyncEventHandler@PublicNetworkListManager@@CAJ_K00@Z; PublicNetworkListManager::AsyncEventHandler(unsigned __int64,unsigned __int64,unsigned __int64)
0x180006717  mov     [rbx], rax
0x18000671a  xor     eax, eax
0x18000671c  add     rsp, 20h
0x180006720  pop     rbx
0x180006721  retn
0x180006722  call    cs:__imp_GetLastError
0x180006728  test    eax, eax
0x18000672a  jle     short loc_18000671C
0x18000672c  movzx   eax, ax
0x18000672f  or      eax, 80070000h
0x180006734  jmp     short loc_18000671C
0x180006736  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "m_eventHandler == nullptr")
0x18000673b  cmp     qword ptr [rbx], 0
0x18000673f  jz      short loc_1800066D9
0x180006741  mov     eax, 800704DFh
0x180006746  jmp     short loc_18000671C
0x180006748  mov     rcx, [rbx+10h]; hObject
0x18000674c  call    cs:__imp_CloseHandle
0x180006752  mov     qword ptr [rbx+10h], 0
0x18000675a  jmp     short loc_180006722
```
