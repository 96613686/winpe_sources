# WEB_ADMIN_SERVICE::ReportServiceStatus(void)

- ea: `0x180005d0c`
- end: `0x180005e40`
- name: `?ReportServiceStatus@WEB_ADMIN_SERVICE@@AEAAJXZ`
- size: `308`
- prototype: `__int64 __fastcall(WEB_ADMIN_SERVICE *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180005e50`
- `0x180006ce0`
- `0x180006e6c`

## callees

- `0x180005d0c`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005dd5`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005dd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ddf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ddf`
- `iisutil!PuDbgPrint` at `0x180005d68`
- `iisutil!PuDbgPrint` at `0x180005dc5`
- `iisutil!PuDbgPrint` at `0x180005d68`
- `iisutil!PuDbgPrint` at `0x180005dc5`
- `iisutil!PuDbgPrintError` at `0x180005e28`
- `iisutil!PuDbgPrintError` at `0x180005e28`

## string_xrefs

- `0x180005d61`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\web_admin_service.cxx`
- `0x180005dbe`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\web_admin_service.cxx`
- `0x180005e21`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\web_admin_service.cxx`
- `0x180005d48`: `Can't report service status because m_ServiceStatusHandle is null\n`
- `0x180005d4f`: `WEB_ADMIN_SERVICE::ReportServiceStatus`
- `0x180005dac`: `WEB_ADMIN_SERVICE::ReportServiceStatus`
- `0x180005e10`: `WEB_ADMIN_SERVICE::ReportServiceStatus`
- `0x180005da5`: `Setting SERVICE_STOPPED state, process may now exit at will\n`
- `0x180005e04`: `Setting service state failed\n`

## pseudocode

```c
__int64 __fastcall WEB_ADMIN_SERVICE::ReportServiceStatus(WEB_ADMIN_SERVICE *this)
{
  unsigned int v3; // ebx
  struct _SERVICE_STATUS *v4; // rsi
  signed int LastError; // eax

  if ( *((_DWORD *)this + 412) )
    return 0;
  if ( *((_QWORD *)this + 140) )
  {
    v3 = 0;
    v4 = (struct _SERVICE_STATUS *)((char *)this + 1128);
    if ( *((_DWORD *)this + 283) == 1 && (g_dwDebugFlags & 0x30000) != 0 && (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
        2183,
        "WEB_ADMIN_SERVICE::ReportServiceStatus",
        "Setting SERVICE_STOPPED state, process may now exit at will\n");
    if ( !SetServiceStatus(*((SERVICE_STATUS_HANDLE *)this + 140), v4) )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
          2201,
          "WEB_ADMIN_SERVICE::ReportServiceStatus",
          v3,
          "Setting service state failed\n");
    }
  }
  else
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
        2156,
        "WEB_ADMIN_SERVICE::ReportServiceStatus",
        "Can't report service status because m_ServiceStatusHandle is null\n");
    return (unsigned int)-2147024890;
  }
  return v3;
}

```

## disassembly

```asm
0x180005d0c  mov     [rsp+arg_0], rbx
0x180005d11  mov     [rsp+arg_8], rsi
0x180005d16  push    rdi
0x180005d17  sub     rsp, 30h
0x180005d1b  cmp     dword ptr [rcx+670h], 0
0x180005d22  mov     rdi, rcx
0x180005d25  jz      short loc_180005D2E
0x180005d27  xor     eax, eax
0x180005d29  jmp     loc_180005E30
0x180005d2e  cmp     qword ptr [rcx+460h], 0
0x180005d36  jnz     short loc_180005D78
0x180005d38  test    byte ptr cs:g_dwDebugFlags, 3
0x180005d3f  jz      short loc_180005D6E
0x180005d41  mov     rcx, cs:g_pDebug
0x180005d48  lea     rax, aCanTReportServ; "Can't report service status because m_S"...
0x180005d4f  lea     r9, aWebAdminServic_19; "WEB_ADMIN_SERVICE::ReportServiceStatus"
0x180005d56  mov     [rsp+38h+var_18], rax
0x180005d5b  mov     r8d, 86Ch
0x180005d61  lea     rdx, aServercommonIn_44; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180005d68  call    cs:__imp_PuDbgPrint
0x180005d6e  mov     ebx, 80070006h
0x180005d73  jmp     loc_180005E2E
0x180005d78  xor     ebx, ebx
0x180005d7a  lea     rsi, [rcx+468h]
0x180005d81  cmp     dword ptr [rsi+4], 1
0x180005d85  jnz     short loc_180005DCB
0x180005d87  mov     eax, cs:g_dwDebugFlags
0x180005d8d  test    eax, 30000h
0x180005d92  setnz   cl
0x180005d95  test    al, 3
0x180005d97  setnz   al
0x180005d9a  test    al, cl
0x180005d9c  jz      short loc_180005DCB
0x180005d9e  mov     rcx, cs:g_pDebug
0x180005da5  lea     rax, aSettingService; "Setting SERVICE_STOPPED state, process "...
0x180005dac  lea     r9, aWebAdminServic_19; "WEB_ADMIN_SERVICE::ReportServiceStatus"
0x180005db3  mov     [rsp+38h+var_18], rax
0x180005db8  mov     r8d, 887h
0x180005dbe  lea     rdx, aServercommonIn_44; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180005dc5  call    cs:__imp_PuDbgPrint
0x180005dcb  mov     rcx, [rdi+460h]; hServiceStatus
0x180005dd2  mov     rdx, rsi; lpServiceStatus
0x180005dd5  call    cs:__imp_SetServiceStatus
0x180005ddb  test    eax, eax
0x180005ddd  jnz     short loc_180005E2E
0x180005ddf  call    cs:__imp_GetLastError
0x180005de5  mov     ebx, eax
0x180005de7  test    eax, eax
0x180005de9  jle     short loc_180005DF4
0x180005deb  movzx   ebx, ax
0x180005dee  or      ebx, 80070000h
0x180005df4  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005dfb  jz      short loc_180005E2E
0x180005dfd  mov     rcx, cs:g_pDebug
0x180005e04  lea     rax, aSettingService_0; "Setting service state failed\n"
0x180005e0b  mov     [rsp+38h+var_10], rax
0x180005e10  lea     r9, aWebAdminServic_19; "WEB_ADMIN_SERVICE::ReportServiceStatus"
0x180005e17  mov     r8d, 899h
0x180005e1d  mov     dword ptr [rsp+38h+var_18], ebx
0x180005e21  lea     rdx, aServercommonIn_44; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180005e28  call    cs:__imp_PuDbgPrintError
0x180005e2e  mov     eax, ebx
0x180005e30  mov     rbx, [rsp+38h+arg_0]
0x180005e35  mov     rsi, [rsp+38h+arg_8]
0x180005e3a  add     rsp, 30h
0x180005e3e  pop     rdi
0x180005e3f  retn
```
