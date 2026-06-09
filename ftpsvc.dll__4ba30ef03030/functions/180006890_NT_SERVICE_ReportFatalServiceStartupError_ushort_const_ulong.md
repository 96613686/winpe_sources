# NT_SERVICE::ReportFatalServiceStartupError(ushort const *,ulong)

- ea: `0x180006890`
- end: `0x180006971`
- name: `?ReportFatalServiceStartupError@NT_SERVICE@@SAXPEBGK@Z`
- size: `225`
- prototype: `void __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180005940`
- `0x180006000`
- `0x1800064c8`

## callees

- `0x180006890`
- `0x180047050`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800068d6`
- `KERNEL32!GetLastError` at `0x180006927`
- `KERNEL32!GetLastError` at `0x1800068d6`
- `KERNEL32!GetLastError` at `0x180006927`
- `ADVAPI32!RegisterServiceCtrlHandlerExW` at `0x1800068be`
- `ADVAPI32!RegisterServiceCtrlHandlerExW` at `0x1800068be`
- `ADVAPI32!SetServiceStatus` at `0x180006914`
- `ADVAPI32!SetServiceStatus` at `0x180006914`
- `iisutil!PuDbgPrint` at `0x180006958`
- `iisutil!PuDbgPrint` at `0x180006958`

## string_xrefs

- `0x18000694c`: `inetsrv\iis\iisrearc\ftp\server\core\nt_service.cxx`
- `0x1800068e6`: `Failed to get Service Ctrl Handler Win32 = %d\n`
- `0x180006945`: `NT_SERVICE::ReportFatalServiceStartupError`
- `0x180006937`: `Failed to set service status Win32 = %d\n`

## pseudocode

```c
void __fastcall NT_SERVICE::ReportFatalServiceStartupError(const unsigned __int16 *a1, DWORD a2)
{
  SERVICE_STATUS_HANDLE v3; // rax
  DWORD v4; // [rsp+28h] [rbp-40h]
  DWORD LastError; // [rsp+28h] [rbp-40h]
  _SERVICE_STATUS ServiceStatus; // [rsp+30h] [rbp-38h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v3 = RegisterServiceCtrlHandlerExW(a1, (LPHANDLER_FUNCTION_EX)NT_SERVICE::GlobalServiceControlHandler, 0);
  if ( v3 )
  {
    ServiceStatus.dwCurrentState = 1;
    ServiceStatus.dwServiceType = 32;
    ServiceStatus.dwWin32ExitCode = a2;
    *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
    if ( !SetServiceStatus(v3, &ServiceStatus) && (g_dwDebugFlags & 3) != 0 )
    {
      LastError = GetLastError();
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\nt_service.cxx",
        748,
        "NT_SERVICE::ReportFatalServiceStartupError",
        "Failed to set service status Win32 = %d\n",
        LastError);
    }
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    v4 = GetLastError();
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\nt_service.cxx",
      733,
      "NT_SERVICE::ReportFatalServiceStartupError",
      "Failed to get Service Ctrl Handler Win32 = %d\n",
      v4);
  }
}

```

## disassembly

```asm
0x180006890  push    rbx
0x180006892  sub     rsp, 60h
0x180006896  mov     rax, cs:__security_cookie
0x18000689d  xor     rax, rsp
0x1800068a0  mov     [rsp+68h+var_18], rax
0x1800068a5  xorps   xmm0, xmm0
0x1800068a8  mov     ebx, edx
0x1800068aa  movups  xmmword ptr [rsp+68h+ServiceStatus.dwServiceType], xmm0
0x1800068af  xor     r8d, r8d; lpContext
0x1800068b2  lea     rdx, ?GlobalServiceControlHandler@NT_SERVICE@@CAKKKPEAX0@Z; lpHandlerProc
0x1800068b9  movups  xmmword ptr [rsp+68h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800068be  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800068c4  test    rax, rax
0x1800068c7  jnz     short loc_1800068EF
0x1800068c9  test    byte ptr cs:g_dwDebugFlags, 3
0x1800068d0  jz      loc_18000695E
0x1800068d6  call    cs:__imp_GetLastError
0x1800068dc  mov     [rsp+68h+var_40], eax
0x1800068e0  mov     r8d, 2DDh
0x1800068e6  lea     rax, aFailedToGetSer; "Failed to get Service Ctrl Handler Win3"...
0x1800068ed  jmp     short loc_18000693E
0x1800068ef  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x1800068f4  mov     [rsp+68h+ServiceStatus.dwCurrentState], 1
0x1800068fc  mov     rcx, rax; hServiceStatus
0x1800068ff  mov     [rsp+68h+ServiceStatus.dwServiceType], 20h ; ' '
0x180006907  mov     [rsp+68h+ServiceStatus.dwWin32ExitCode], ebx
0x18000690b  mov     qword ptr [rsp+68h+ServiceStatus.dwCheckPoint], 0
0x180006914  call    cs:__imp_SetServiceStatus
0x18000691a  test    eax, eax
0x18000691c  jnz     short loc_18000695E
0x18000691e  test    byte ptr cs:g_dwDebugFlags, 3
0x180006925  jz      short loc_18000695E
0x180006927  call    cs:__imp_GetLastError
0x18000692d  mov     [rsp+68h+var_40], eax
0x180006931  mov     r8d, 2ECh
0x180006937  lea     rax, aFailedToSetSer; "Failed to set service status Win32 = %d"...
0x18000693e  mov     rcx, cs:g_pDebug
0x180006945  lea     r9, aNtServiceRepor; "NT_SERVICE::ReportFatalServiceStartupEr"...
0x18000694c  lea     rdx, aInetsrvIisIisr_38; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x180006953  mov     [rsp+68h+var_48], rax
0x180006958  call    cs:__imp_PuDbgPrint
0x18000695e  mov     rcx, [rsp+68h+var_18]
0x180006963  xor     rcx, rsp; StackCookie
0x180006966  call    __security_check_cookie
0x18000696b  add     rsp, 60h
0x18000696f  pop     rbx
0x180006970  retn
```
