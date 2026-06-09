# WEB_ADMIN_SERVICE::TerminateServiceAndReportFinalStatus(long)

- ea: `0x180006b88`
- end: `0x180006cda`
- name: `?TerminateServiceAndReportFinalStatus@WEB_ADMIN_SERVICE@@AEAAXJ@Z`
- size: `338`
- prototype: `void __fastcall(WEB_ADMIN_SERVICE *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180004b80`

## callees

- `0x180005878`
- `0x180006880`
- `0x180006b88`
- `0x180006e6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006ccb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006ccb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006c5d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006c5d`
- `iisutil!PuDbgPrintError` at `0x180006be0`
- `iisutil!PuDbgPrintError` at `0x180006cc2`
- `iisutil!PuDbgPrintError` at `0x180006be0`
- `iisutil!PuDbgPrintError` at `0x180006cc2`
- `iisutil!ReadDwordParameterValueFromAnyService` at `0x180006bff`
- `iisutil!ReadDwordParameterValueFromAnyService` at `0x180006bff`

## string_xrefs

- `0x180006bd9`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\web_admin_service.cxx`
- `0x180006cb7`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\web_admin_service.cxx`
- `0x180006bf8`: `System\CurrentControlSet\Services\WAS\Parameters`
- `0x180006bbc`: `Fatal service error, shutting down\n`
- `0x180006bc8`: `WEB_ADMIN_SERVICE::TerminateServiceAndReportFinalStatus`
- `0x180006ca9`: `WEB_ADMIN_SERVICE::TerminateServiceAndReportFinalStatus`
- `0x180006c97`: `couldn't update service status\n`

## pseudocode

```c
void __fastcall WEB_ADMIN_SERVICE::TerminateServiceAndReportFinalStatus(struct _RTL_CRITICAL_SECTION *this, int a2)
{
  unsigned int v2; // ebp
  signed int DebugInfo; // ebx
  unsigned int v5; // esi
  int updated; // eax

  v2 = 0;
  DebugInfo = a2;
  if ( a2 < 0 || (DebugInfo = (signed int)this[39].DebugInfo, v5 = 0, DebugInfo < 0) )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
        3202,
        "WEB_ADMIN_SERVICE::TerminateServiceAndReportFinalStatus",
        DebugInfo,
        "Fatal service error, shutting down\n");
    if ( !this[41].LockCount )
      ReadDwordParameterValueFromAnyService(
        L"System\\CurrentControlSet\\Services\\WAS\\Parameters",
        L"BreakOnFailureCausingShutdown",
        0);
    WEB_ADMIN_SERVICE::LogEvent(g_pWebAdminService, 0xC000138D, 0, 0, DebugInfo);
    if ( (DebugInfo & 0x1FFF0000) == 0x70000 )
    {
      if ( DebugInfo >= 0 )
        v5 = DebugInfo;
      else
        v5 = (unsigned __int16)DebugInfo;
    }
    else
    {
      v5 = 1066;
      v2 = DebugInfo;
    }
  }
  WEB_ADMIN_SERVICE::Terminate((WEB_ADMIN_SERVICE *)this);
  if ( this[40].RecursionCount )
  {
    EnterCriticalSection(this + 27);
    updated = WEB_ADMIN_SERVICE::UpdateServiceStatus((WEB_ADMIN_SERVICE *)this, 1u, v5, v2, 0, 0, 1);
    if ( updated < 0 && (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
        3276,
        "WEB_ADMIN_SERVICE::TerminateServiceAndReportFinalStatus",
        updated,
        "couldn't update service status\n");
    LeaveCriticalSection(this + 27);
  }
}

```

## disassembly

```asm
0x180006b88  push    rbx
0x180006b8a  push    rbp
0x180006b8b  push    rsi
0x180006b8c  push    rdi
0x180006b8d  sub     rsp, 48h
0x180006b91  xor     ebp, ebp
0x180006b93  mov     ebx, edx
0x180006b95  mov     rdi, rcx
0x180006b98  test    edx, edx
0x180006b9a  js      short loc_180006BAC
0x180006b9c  mov     ebx, [rcx+618h]
0x180006ba2  xor     esi, esi
0x180006ba4  test    ebx, ebx
0x180006ba6  jns     loc_180006C42
0x180006bac  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006bb3  jz      short loc_180006BE6
0x180006bb5  mov     rcx, cs:g_pDebug
0x180006bbc  lea     rax, aFatalServiceEr; "Fatal service error, shutting down\n"
0x180006bc3  mov     qword ptr [rsp+68h+var_40], rax
0x180006bc8  lea     r9, aWebAdminServic_27; "WEB_ADMIN_SERVICE::TerminateServiceAndR"...
0x180006bcf  mov     r8d, 0C82h
0x180006bd5  mov     [rsp+68h+var_48], ebx
0x180006bd9  lea     rdx, aServercommonIn_44; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180006be0  call    cs:__imp_PuDbgPrintError
0x180006be6  cmp     [rdi+670h], ebp
0x180006bec  jnz     short loc_180006C05
0x180006bee  xor     r8d, r8d
0x180006bf1  lea     rdx, aBreakonfailure; "BreakOnFailureCausingShutdown"
0x180006bf8  lea     rcx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\WA"...
0x180006bff  call    cs:__imp_?ReadDwordParameterValueFromAnyService@@YAKPEBG0K@Z; ReadDwordParameterValueFromAnyService(ushort const *,ushort const *,ulong)
0x180006c05  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; this
0x180006c0c  xor     r8d, r8d; unsigned __int16
0x180006c0f  xor     r9d, r9d; unsigned __int16 **
0x180006c12  mov     [rsp+68h+var_48], ebx; unsigned int
0x180006c16  mov     edx, 0C000138Dh; unsigned int
0x180006c1b  call    ?LogEvent@WEB_ADMIN_SERVICE@@QEAAXKGQEAPEBGK@Z; WEB_ADMIN_SERVICE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180006c20  mov     eax, ebx
0x180006c22  and     eax, 1FFF0000h
0x180006c27  cmp     eax, 70000h
0x180006c2c  jnz     short loc_180006C3B
0x180006c2e  test    ebx, ebx
0x180006c30  jns     short loc_180006C37
0x180006c32  movzx   esi, bx
0x180006c35  jmp     short loc_180006C42
0x180006c37  mov     esi, ebx
0x180006c39  jmp     short loc_180006C42
0x180006c3b  mov     esi, 42Ah
0x180006c40  mov     ebp, ebx
0x180006c42  mov     rcx, rdi; this
0x180006c45  call    ?Terminate@WEB_ADMIN_SERVICE@@AEAAXXZ; WEB_ADMIN_SERVICE::Terminate(void)
0x180006c4a  cmp     dword ptr [rdi+64Ch], 0
0x180006c51  jz      short loc_180006CD1
0x180006c53  lea     rbx, [rdi+438h]
0x180006c5a  mov     rcx, rbx; lpCriticalSection
0x180006c5d  call    cs:__imp_EnterCriticalSection
0x180006c63  mov     edx, 1; unsigned int
0x180006c68  mov     r9d, ebp; unsigned int
0x180006c6b  mov     [rsp+68h+var_38], edx; int
0x180006c6f  mov     r8d, esi; unsigned int
0x180006c72  mov     [rsp+68h+var_40], 0; unsigned int
0x180006c7a  mov     rcx, rdi; this
0x180006c7d  mov     [rsp+68h+var_48], 0; unsigned int
0x180006c85  call    ?UpdateServiceStatus@WEB_ADMIN_SERVICE@@AEAAJKKKKKH@Z; WEB_ADMIN_SERVICE::UpdateServiceStatus(ulong,ulong,ulong,ulong,ulong,int)
0x180006c8a  test    eax, eax
0x180006c8c  jns     short loc_180006CC8
0x180006c8e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006c95  jz      short loc_180006CC8
0x180006c97  lea     rcx, aCouldnTUpdateS; "couldn't update service status\n"
0x180006c9e  mov     r8d, 0CCCh
0x180006ca4  mov     qword ptr [rsp+68h+var_40], rcx
0x180006ca9  lea     r9, aWebAdminServic_27; "WEB_ADMIN_SERVICE::TerminateServiceAndR"...
0x180006cb0  mov     rcx, cs:g_pDebug
0x180006cb7  lea     rdx, aServercommonIn_44; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180006cbe  mov     [rsp+68h+var_48], eax
0x180006cc2  call    cs:__imp_PuDbgPrintError
0x180006cc8  mov     rcx, rbx; lpCriticalSection
0x180006ccb  call    cs:__imp_LeaveCriticalSection
0x180006cd1  add     rsp, 48h
0x180006cd5  pop     rdi
0x180006cd6  pop     rsi
0x180006cd7  pop     rbp
0x180006cd8  pop     rbx
0x180006cd9  retn
```
