# FDResPub_Startup(void)

- ea: `0x180004cd4`
- end: `0x180004ddc`
- name: `?FDResPub_Startup@@YAJXZ`
- size: `264`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180004f30`

## callees

- `0x180004770`
- `0x1800047f8`
- `0x180004cd4`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d26`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004d14`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004d14`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180004dce`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180004dce`

## pseudocode

```c
__int64 FDResPub_Startup(void)
{
  signed int LastError; // eax
  unsigned int v1; // ebx
  int v2; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_db7cc9e2c33f3bbb1ab807d3dbe66b7d_Traceguids);
  g_hShutdownEvent = CreateEventW(0, 1, 0, 0);
  if ( g_hShutdownEvent )
    goto LABEL_8;
  LastError = GetLastError();
  v1 = LastError;
  if ( LastError > 0 )
    v1 = (unsigned __int16)LastError | 0x80070000;
  if ( !v1 )
  {
LABEL_8:
    v1 = FDResPub_InitializeHost();
    if ( !v1 )
    {
      if ( g_pSvchostGlobalData
        && (v2 = (*((__int64 (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *), _QWORD, int))g_pSvchostGlobalData
                  + 24))(
                   &g_hShutdownWait,
                   L"FDResPub",
                   g_hShutdownEvent,
                   FDResPub_ShutdownCallback,
                   0,
                   8)) != 0 )
      {
        if ( v2 > 0 )
          return (unsigned __int16)v2 | 0x80070000;
        else
          return (unsigned int)v2;
      }
      else
      {
        ServiceStatus.dwControlsAccepted = 69;
        ServiceStatus.dwCurrentState = 4;
        SetServiceStatus(hServiceStatus, &ServiceStatus);
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180004cd4  push    rbx
0x180004cd6  sub     rsp, 40h
0x180004cda  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ce1  lea     rax, WPP_GLOBAL_Control
0x180004ce8  cmp     rcx, rax
0x180004ceb  jz      short loc_180004D08
0x180004ced  cmp     byte ptr [rcx+19h], 4
0x180004cf1  jb      short loc_180004D08
0x180004cf3  mov     rcx, [rcx+10h]
0x180004cf7  lea     r8, WPP_db7cc9e2c33f3bbb1ab807d3dbe66b7d_Traceguids
0x180004cfe  mov     edx, 0Eh
0x180004d03  call    WPP_SF_s
0x180004d08  xor     r9d, r9d; lpName
0x180004d0b  xor     r8d, r8d; bInitialState
0x180004d0e  xor     ecx, ecx; lpEventAttributes
0x180004d10  lea     edx, [r9+1]; bManualReset
0x180004d14  call    cs:__imp_CreateEventW
0x180004d1a  mov     cs:?g_hShutdownEvent@@3PEAXEA, rax; void * g_hShutdownEvent
0x180004d21  test    rax, rax
0x180004d24  jnz     short loc_180004D43
0x180004d26  call    cs:__imp_GetLastError
0x180004d2c  mov     ebx, eax
0x180004d2e  test    eax, eax
0x180004d30  jle     short loc_180004D3B
0x180004d32  movzx   ebx, ax
0x180004d35  or      ebx, 80070000h
0x180004d3b  test    ebx, ebx
0x180004d3d  jnz     loc_180004DD4
0x180004d43  call    ?FDResPub_InitializeHost@@YAJXZ; FDResPub_InitializeHost(void)
0x180004d48  mov     ebx, eax
0x180004d4a  test    eax, eax
0x180004d4c  jnz     loc_180004DD4
0x180004d52  mov     rax, cs:?g_pSvchostGlobalData@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_pSvchostGlobalData
0x180004d59  test    rax, rax
0x180004d5c  jz      short loc_180004DAC
0x180004d5e  mov     r8, cs:?g_hShutdownEvent@@3PEAXEA; void * g_hShutdownEvent
0x180004d65  lea     r9, ?FDResPub_ShutdownCallback@@YAXPEAXE@Z; FDResPub_ShutdownCallback(void *,uchar)
0x180004d6c  mov     rax, [rax+0C0h]
0x180004d73  lea     rdx, ServiceName; "FDResPub"
0x180004d7a  mov     [rsp+48h+var_20], 8
0x180004d82  lea     rcx, ?g_hShutdownWait@@3PEAXEA; void * g_hShutdownWait
0x180004d89  mov     [rsp+48h+var_28], 0
0x180004d92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d97  test    eax, eax
0x180004d99  jz      short loc_180004DAC
0x180004d9b  jg      short loc_180004DA1
0x180004d9d  mov     ebx, eax
0x180004d9f  jmp     short loc_180004DD4
0x180004da1  movzx   ebx, ax
0x180004da4  or      ebx, 80070000h
0x180004daa  jmp     short loc_180004DD4
0x180004dac  mov     rcx, cs:hServiceStatus; hServiceStatus
0x180004db3  lea     rdx, ServiceStatus; lpServiceStatus
0x180004dba  mov     cs:ServiceStatus.dwControlsAccepted, 45h ; 'E'
0x180004dc4  mov     cs:ServiceStatus.dwCurrentState, 4
0x180004dce  call    cs:__imp_SetServiceStatus
0x180004dd4  mov     eax, ebx
0x180004dd6  add     rsp, 40h
0x180004dda  pop     rbx
0x180004ddb  retn
```
