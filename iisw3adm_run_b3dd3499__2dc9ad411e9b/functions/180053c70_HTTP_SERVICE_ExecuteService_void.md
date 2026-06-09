# HTTP_SERVICE::ExecuteService(void)

- ea: `0x180053c70`
- end: `0x180053e5f`
- name: `?ExecuteService@HTTP_SERVICE@@QEAAJXZ`
- size: `495`
- prototype: `__int64 __fastcall(HTTP_SERVICE *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800033e0`
- `0x180054638`

## callees

- `0x1800073fc`
- `0x180053abc`
- `0x180053c70`
- `0x180054324`

## import_xrefs

- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x180053cc2`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x180053cc2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180053dda`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180053dda`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180053c8f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180053c8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053e4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053e4a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180053d95`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180053d95`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180053e1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180053e1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053cd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053d01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053da4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053cd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053d01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053da4`
- `iisutil!PuDbgPrintError` at `0x180053d4e`
- `iisutil!PuDbgPrintError` at `0x180053d4e`

## string_xrefs

- `0x180053d7c`: `couldn't transition to service start pending\n`
- `0x180053d43`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\http_service.cxx`
- `0x180053d37`: `HTTP_SERVICE::ExecuteService`
- `0x180053cf2`: `Could not register the service control handler\n`

## pseudocode

```c
__int64 __fastcall HTTP_SERVICE::ExecuteService(HTTP_SERVICE *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbp
  unsigned int v3; // r14d
  SERVICE_STATUS_HANDLE v4; // rax
  signed int v5; // eax
  signed int v6; // ebx
  signed int LastError; // eax
  HANDLE EventW; // rax
  signed int v9; // eax
  int v10; // edi
  unsigned int v11; // ebx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 72);
  v3 = 0;
  if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 72), 0x800003E8) )
  {
    *((_DWORD *)this + 17) = 1;
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\http_service.cxx",
          413,
          "HTTP_SERVICE::ExecuteService",
          v6,
          "Lock initialization failed\n");
      goto LABEL_24;
    }
  }
  *((_DWORD *)this + 28) = 1;
  if ( !*((_DWORD *)this + 9) )
  {
    v4 = RegisterServiceCtrlHandlerW(L"w3svc", HTTP_SERVICE::W3SvcControlHandler);
    *(_QWORD *)this = v4;
    if ( !v4 )
    {
      v5 = GetLastError();
      v6 = v5;
      if ( v5 > 0 )
        v6 = (unsigned __int16)v5 | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\http_service.cxx",
          438,
          "HTTP_SERVICE::ExecuteService",
          v6,
          "Could not register the service control handler\n");
      goto LABEL_24;
    }
    g_W3SVCRegisterServiceCalled = 1;
  }
  v6 = HTTP_SERVICE::BeginStateTransition(this, 2u);
  if ( v6 >= 0 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 5) = EventW;
    if ( EventW )
    {
      v6 = WORK_QUEUE::GetAndQueueWorkItem(
             (WEB_ADMIN_SERVICE *)((char *)g_pWebAdminService + 16),
             g_pWebAdminService,
             6u);
      if ( v6 >= 0 )
        WaitForSingleObject(*((HANDLE *)this + 5), 0xFFFFFFFF);
    }
    else
    {
      v9 = GetLastError();
      v6 = v9;
      if ( v9 > 0 )
        v6 = (unsigned __int16)v9 | 0x80070000;
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\http_service.cxx",
      454,
      "HTTP_SERVICE::ExecuteService",
      v6,
      "couldn't transition to service start pending\n");
  }
LABEL_24:
  v10 = *((_DWORD *)this + 12);
  if ( v10 >= 0 )
  {
    v10 = v6;
    if ( v6 >= 0 )
    {
      v11 = 0;
      goto LABEL_31;
    }
  }
  else
  {
    *((_DWORD *)this + 12) = 0;
  }
  if ( (v10 & 0x1FFF0000) == 0x70000 )
  {
    v11 = (unsigned __int16)v10;
  }
  else
  {
    v11 = 1066;
    v3 = v10;
  }
LABEL_31:
  if ( *((_DWORD *)this + 28) )
  {
    EnterCriticalSection(v1);
    HTTP_SERVICE::UpdateServiceStatus(this, 1u, v11, v3, 0, 0, 1);
    LeaveCriticalSection(v1);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180053c70  push    rbx
0x180053c72  push    rbp
0x180053c73  push    rsi
0x180053c74  push    rdi
0x180053c75  push    r12
0x180053c77  push    r14
0x180053c79  sub     rsp, 48h
0x180053c7d  lea     rbp, [rcx+48h]
0x180053c81  mov     rsi, rcx
0x180053c84  mov     rcx, rbp; lpCriticalSection
0x180053c87  mov     edx, 800003E8h; dwSpinCount
0x180053c8c  xor     r14d, r14d
0x180053c8f  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180053c95  mov     edi, 80070000h
0x180053c9a  lea     r12d, [r14+1]
0x180053c9e  test    eax, eax
0x180053ca0  jz      short loc_180053D01
0x180053ca2  mov     [rsi+44h], r12d
0x180053ca6  mov     [rsi+70h], r12d
0x180053caa  cmp     [rsi+24h], r14d
0x180053cae  jnz     loc_180053D60
0x180053cb4  lea     rdx, ?W3SvcControlHandler@HTTP_SERVICE@@SAXK@Z; lpHandlerProc
0x180053cbb  lea     rcx, aW3svc_0; "w3svc"
0x180053cc2  call    cs:__imp_RegisterServiceCtrlHandlerW
0x180053cc8  mov     [rsi], rax
0x180053ccb  test    rax, rax
0x180053cce  jnz     loc_180053D59
0x180053cd4  call    cs:__imp_GetLastError
0x180053cda  mov     ebx, eax
0x180053cdc  test    eax, eax
0x180053cde  jle     short loc_180053CE5
0x180053ce0  movzx   ebx, ax
0x180053ce3  or      ebx, edi
0x180053ce5  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180053cec  jz      loc_180053DE0
0x180053cf2  lea     rax, aCouldNotRegist; "Could not register the service control "...
0x180053cf9  mov     r8d, 1B6h
0x180053cff  jmp     short loc_180053D30
0x180053d01  call    cs:__imp_GetLastError
0x180053d07  mov     ebx, eax
0x180053d09  test    eax, eax
0x180053d0b  jle     short loc_180053D12
0x180053d0d  movzx   ebx, ax
0x180053d10  or      ebx, edi
0x180053d12  test    ebx, ebx
0x180053d14  jns     short loc_180053CA6
0x180053d16  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180053d1d  jz      loc_180053DE0
0x180053d23  lea     rax, aLockInitializa; "Lock initialization failed\n"
0x180053d2a  mov     r8d, 19Dh
0x180053d30  mov     rcx, cs:g_pDebug
0x180053d37  lea     r9, aHttpServiceExe; "HTTP_SERVICE::ExecuteService"
0x180053d3e  mov     qword ptr [rsp+78h+var_50], rax
0x180053d43  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180053d4a  mov     [rsp+78h+var_58], ebx
0x180053d4e  call    cs:__imp_PuDbgPrintError
0x180053d54  jmp     loc_180053DE0
0x180053d59  mov     cs:?g_W3SVCRegisterServiceCalled@@3HA, r12d; int g_W3SVCRegisterServiceCalled
0x180053d60  mov     edx, 2; unsigned int
0x180053d65  mov     rcx, rsi; this
0x180053d68  call    ?BeginStateTransition@HTTP_SERVICE@@AEAAJK@Z; HTTP_SERVICE::BeginStateTransition(ulong)
0x180053d6d  mov     ebx, eax
0x180053d6f  test    eax, eax
0x180053d71  jns     short loc_180053D8B
0x180053d73  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180053d7a  jz      short loc_180053DE0
0x180053d7c  lea     rax, aCouldnTTransit_1; "couldn't transition to service start pe"...
0x180053d83  mov     r8d, 1C6h
0x180053d89  jmp     short loc_180053D30
0x180053d8b  xor     r9d, r9d; lpName
0x180053d8e  xor     r8d, r8d; bInitialState
0x180053d91  xor     edx, edx; bManualReset
0x180053d93  xor     ecx, ecx; lpEventAttributes
0x180053d95  call    cs:__imp_CreateEventW
0x180053d9b  mov     [rsi+28h], rax
0x180053d9f  test    rax, rax
0x180053da2  jnz     short loc_180053DB7
0x180053da4  call    cs:__imp_GetLastError
0x180053daa  mov     ebx, eax
0x180053dac  test    eax, eax
0x180053dae  jle     short loc_180053DE0
0x180053db0  movzx   ebx, ax
0x180053db3  or      ebx, edi
0x180053db5  jmp     short loc_180053DE0
0x180053db7  mov     rdx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; struct WORK_DISPATCH *
0x180053dbe  mov     r8d, 6; unsigned __int64
0x180053dc4  lea     rcx, [rdx+10h]; this
0x180053dc8  call    ?GetAndQueueWorkItem@WORK_QUEUE@@QEAAJPEAVWORK_DISPATCH@@_K@Z; WORK_QUEUE::GetAndQueueWorkItem(WORK_DISPATCH *,unsigned __int64)
0x180053dcd  mov     ebx, eax
0x180053dcf  test    eax, eax
0x180053dd1  js      short loc_180053DE0
0x180053dd3  mov     rcx, [rsi+28h]; hHandle
0x180053dd7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180053dda  call    cs:__imp_WaitForSingleObject
0x180053de0  mov     edi, [rsi+30h]
0x180053de3  test    edi, edi
0x180053de5  jns     short loc_180053DED
0x180053de7  mov     [rsi+30h], r14d
0x180053deb  jmp     short loc_180053DF3
0x180053ded  mov     edi, ebx
0x180053def  test    ebx, ebx
0x180053df1  jns     short loc_180053E10
0x180053df3  mov     eax, edi
0x180053df5  and     eax, 1FFF0000h
0x180053dfa  cmp     eax, 70000h
0x180053dff  jnz     short loc_180053E06
0x180053e01  movzx   ebx, di
0x180053e04  jmp     short loc_180053E12
0x180053e06  mov     ebx, 42Ah
0x180053e0b  mov     r14d, edi
0x180053e0e  jmp     short loc_180053E12
0x180053e10  xor     ebx, ebx
0x180053e12  cmp     dword ptr [rsi+70h], 0
0x180053e16  jz      short loc_180053E50
0x180053e18  mov     rcx, rbp; lpCriticalSection
0x180053e1b  call    cs:__imp_EnterCriticalSection
0x180053e21  mov     [rsp+78h+var_48], r12d; int
0x180053e26  mov     r9d, r14d; unsigned int
0x180053e29  mov     [rsp+78h+var_50], 0; unsigned int
0x180053e31  mov     r8d, ebx; unsigned int
0x180053e34  mov     edx, r12d; unsigned int
0x180053e37  mov     [rsp+78h+var_58], 0; unsigned int
0x180053e3f  mov     rcx, rsi; this
0x180053e42  call    ?UpdateServiceStatus@HTTP_SERVICE@@AEAAJKKKKKH@Z; HTTP_SERVICE::UpdateServiceStatus(ulong,ulong,ulong,ulong,ulong,int)
0x180053e47  mov     rcx, rbp; lpCriticalSection
0x180053e4a  call    cs:__imp_LeaveCriticalSection
0x180053e50  mov     eax, edi
0x180053e52  add     rsp, 48h
0x180053e56  pop     r14
0x180053e58  pop     r12
0x180053e5a  pop     rdi
0x180053e5b  pop     rsi
0x180053e5c  pop     rbp
0x180053e5d  pop     rbx
0x180053e5e  retn
```
