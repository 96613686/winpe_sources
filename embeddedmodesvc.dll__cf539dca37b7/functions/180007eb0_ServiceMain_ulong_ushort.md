# ServiceMain(ulong,ushort * *)

- ea: `0x180007eb0`
- end: `0x18000800f`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `351`
- prototype: `void __fastcall(__int64, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180007b34`
- `0x180007eb0`
- `0x180008018`
- `0x1800081c4`
- `0x1800082d8`
- `0x180008358`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007f41`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007f41`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180007f91`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180007f91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ee9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ee9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007fda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007fda`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180007ed7`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180007ed7`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180007ec0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180007ec0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180007feb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180007feb`

## string_xrefs

- `0x180007fb9`: `onecoreuap\shell\embedded\shell\embeddedmode\svc\servicemain.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ServiceMain(__int64 a1, unsigned __int16 **a2)
{
  int v2; // edi
  signed int LastError; // eax
  int v4; // ebx
  int v5; // ecx
  int v6; // eax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = 0;
  CoInitializeEx(0, 0);
  g_hStatus = RegisterServiceCtrlHandlerExW(ServiceName, ServiceControlHandler, 0);
  if ( g_hStatus
    && (*(_QWORD *)&g_status.dwServiceType = 32,
        g_status.dwControlsAccepted = 4224,
        *(_OWORD *)&g_status.dwWin32ExitCode = 0,
        SvcUpdateServiceStatus(2u, 0, 0x2710u),
        (g_hStopEvent = CreateEventW(0, 0, 0, 0)) != 0) )
  {
    v4 = SvcInitialize();
    if ( v4 >= 0 )
    {
      if ( g_fAllowEmbeddedMode )
        EnableServiceAutoStart();
      v2 = 1;
      SvcUpdateServiceStatus(4u, 0, 0);
      if ( g_fAllowEmbeddedMode )
        WaitForSingleObject(g_hStopEvent, 0xFFFFFFFF);
    }
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
  }
  SvcUpdateServiceStatus(3u, 0, 0x2710u);
  if ( v2 )
  {
    v6 = SvcUninitialize(v5);
    if ( v6 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x1A1,
        (unsigned int)"onecoreuap\\shell\\embedded\\shell\\embeddedmode\\svc\\servicemain.cpp",
        (const char *)(unsigned int)v6,
        v7);
  }
  if ( g_hStopEvent )
  {
    CloseHandle(g_hStopEvent);
    g_hStopEvent = 0;
  }
  CoUninitialize();
  if ( v4 >= 0 )
    v4 = 0;
  SvcUpdateServiceStatus(1u, v4, 0);
}

```

## disassembly

```asm
0x180007eb0  mov     [rsp+arg_0], rbx
0x180007eb5  push    rdi; int
0x180007eb6  sub     rsp, 20h
0x180007eba  xor     edx, edx; dwCoInit
0x180007ebc  xor     ecx, ecx; pvReserved
0x180007ebe  xor     edi, edi
0x180007ec0  call    cs:__imp_CoInitializeEx
0x180007ec6  xor     r8d, r8d; lpContext
0x180007ec9  lea     rdx, ?ServiceControlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x180007ed0  lea     rcx, ServiceName; "EmbeddedMode"
0x180007ed7  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180007edd  mov     cs:?g_hStatus@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_hStatus
0x180007ee4  test    rax, rax
0x180007ee7  jnz     short loc_180007F07
0x180007ee9  call    cs:__imp_GetLastError
0x180007eef  mov     ebx, eax
0x180007ef1  test    eax, eax
0x180007ef3  jle     loc_180007F97
0x180007ef9  movzx   ebx, ax
0x180007efc  or      ebx, 80070000h
0x180007f02  jmp     loc_180007F97
0x180007f07  xor     edx, edx; unsigned int
0x180007f09  mov     qword ptr cs:?g_status@@3U_SERVICE_STATUS@@A.dwServiceType, 20h ; ' '; _SERVICE_STATUS g_status ...
0x180007f14  xorps   xmm0, xmm0
0x180007f17  mov     cs:?g_status@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 1080h; _SERVICE_STATUS g_status ...
0x180007f21  mov     r8d, 2710h; unsigned int
0x180007f27  movdqu  xmmword ptr cs:?g_status@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, xmm0; _SERVICE_STATUS g_status ...
0x180007f2f  lea     ecx, [rdx+2]; unsigned int
0x180007f32  call    ?SvcUpdateServiceStatus@@YAXKKK@Z; SvcUpdateServiceStatus(ulong,ulong,ulong)
0x180007f37  xor     r9d, r9d; lpName
0x180007f3a  xor     r8d, r8d; bInitialState
0x180007f3d  xor     edx, edx; bManualReset
0x180007f3f  xor     ecx, ecx; lpEventAttributes
0x180007f41  call    cs:__imp_CreateEventW
0x180007f47  mov     cs:?g_hStopEvent@@3PEAXEA, rax; void * g_hStopEvent
0x180007f4e  test    rax, rax
0x180007f51  jz      short loc_180007EE9
0x180007f53  call    ?SvcInitialize@@YAJXZ; SvcInitialize(void)
0x180007f58  mov     ebx, eax
0x180007f5a  test    eax, eax
0x180007f5c  js      short loc_180007F97
0x180007f5e  cmp     cs:?g_fAllowEmbeddedMode@@3_NA, dil; bool g_fAllowEmbeddedMode
0x180007f65  jz      short loc_180007F6C
0x180007f67  call    ?EnableServiceAutoStart@@YAXXZ; EnableServiceAutoStart(void)
0x180007f6c  mov     edi, 1
0x180007f71  xor     r8d, r8d; unsigned int
0x180007f74  xor     edx, edx; unsigned int
0x180007f76  lea     ecx, [rdi+3]; unsigned int
0x180007f79  call    ?SvcUpdateServiceStatus@@YAXKKK@Z; SvcUpdateServiceStatus(ulong,ulong,ulong)
0x180007f7e  cmp     cs:?g_fAllowEmbeddedMode@@3_NA, 0; bool g_fAllowEmbeddedMode
0x180007f85  jz      short loc_180007F97
0x180007f87  mov     rcx, cs:?g_hStopEvent@@3PEAXEA; hHandle
0x180007f8e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007f91  call    cs:__imp_WaitForSingleObject
0x180007f97  xor     edx, edx; unsigned int
0x180007f99  mov     r8d, 2710h; unsigned int
0x180007f9f  lea     ecx, [rdx+3]; unsigned int
0x180007fa2  call    ?SvcUpdateServiceStatus@@YAXKKK@Z; SvcUpdateServiceStatus(ulong,ulong,ulong)
0x180007fa7  test    edi, edi
0x180007fa9  jz      short loc_180007FCE
0x180007fab  call    ?SvcUninitialize@@YAJJ@Z; SvcUninitialize(long)
0x180007fb0  test    eax, eax
0x180007fb2  jns     short loc_180007FCE
0x180007fb4  mov     rcx, [rsp+28h]; this
0x180007fb9  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\embedded\\shell\\emb"...
0x180007fc0  mov     r9d, eax; char *
0x180007fc3  mov     edx, 1A1h; void *
0x180007fc8  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180007fce  mov     rcx, cs:?g_hStopEvent@@3PEAXEA; hObject
0x180007fd5  test    rcx, rcx
0x180007fd8  jz      short loc_180007FEB
0x180007fda  call    cs:__imp_CloseHandle
0x180007fe0  mov     cs:?g_hStopEvent@@3PEAXEA, 0; void * g_hStopEvent
0x180007feb  call    cs:__imp_CoUninitialize
0x180007ff1  xor     eax, eax
0x180007ff3  test    ebx, ebx
0x180007ff5  cmovns  ebx, eax
0x180007ff8  xor     r8d, r8d; unsigned int
0x180007ffb  mov     edx, ebx; unsigned int
0x180007ffd  lea     ecx, [rax+1]; unsigned int
0x180008000  mov     rbx, [rsp+28h+arg_0]
0x180008005  add     rsp, 20h
0x180008009  pop     rdi
0x18000800a  jmp     ?SvcUpdateServiceStatus@@YAXKKK@Z; SvcUpdateServiceStatus(ulong,ulong,ulong)
```
