# ReportServiceStatus(void)

- ea: `0x180001a0c`
- end: `0x180001bfe`
- name: `?ReportServiceStatus@@YAKXZ`
- size: `498`
- prototype: `unsigned int(void)`
- caller_count: `5`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180001cf0`
- `0x180001e60`
- `0x180002730`
- `0x180002760`
- `0x1800027a4`

## callees

- `0x180001a0c`

## import_xrefs

- `ADVAPI32!SetServiceStatus` at `0x180001bdf`
- `ADVAPI32!SetServiceStatus` at `0x180001bdf`
- `KERNEL32!GetLastError` at `0x180001be9`
- `KERNEL32!GetLastError` at `0x180001be9`
- `IisRTL!PuDbgPrint` at `0x180001a65`
- `IisRTL!PuDbgPrint` at `0x180001aa2`
- `IisRTL!PuDbgPrint` at `0x180001adf`
- `IisRTL!PuDbgPrint` at `0x180001b1c`
- `IisRTL!PuDbgPrint` at `0x180001b59`
- `IisRTL!PuDbgPrint` at `0x180001b92`
- `IisRTL!PuDbgPrint` at `0x180001bcb`
- `IisRTL!PuDbgPrint` at `0x180001a65`
- `IisRTL!PuDbgPrint` at `0x180001aa2`
- `IisRTL!PuDbgPrint` at `0x180001adf`
- `IisRTL!PuDbgPrint` at `0x180001b1c`
- `IisRTL!PuDbgPrint` at `0x180001b59`
- `IisRTL!PuDbgPrint` at `0x180001b92`
- `IisRTL!PuDbgPrint` at `0x180001bcb`

## string_xrefs

- `0x180001a59`: `dwServiceType             = %08lX\n`
- `0x180001a26`: `ReportServiceStatus`
- `0x180001b4d`: `dwServiceSpecificExitCode = %08lX\n`

## pseudocode

```c
DWORD ReportServiceStatus(void)
{
  if ( (g_dwDebugFlags & 0x200000) != 0 && (g_dwDebugFlags & 3) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\iisadmin\\main.cxx",
      185,
      "ReportServiceStatus",
      "dwServiceType             = %08lX\n",
      g_svcStatus.dwServiceType);
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\iisadmin\\main.cxx",
        188,
        "ReportServiceStatus",
        "dwCurrentState            = %08lX\n",
        g_svcStatus.dwCurrentState);
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\iisadmin\\main.cxx",
          191,
          "ReportServiceStatus",
          "dwControlsAccepted        = %08lX\n",
          g_svcStatus.dwControlsAccepted);
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\mb\\iisadmin\\main.cxx",
            194,
            "ReportServiceStatus",
            "dwWin32ExitCode           = %08lX\n",
            g_svcStatus.dwWin32ExitCode);
          if ( (g_dwDebugFlags & 3) != 0 )
          {
            PuDbgPrint(
              g_pDebug,
              "inetsrv\\iis\\mb\\iisadmin\\main.cxx",
              197,
              "ReportServiceStatus",
              "dwServiceSpecificExitCode = %08lX\n",
              g_svcStatus.dwServiceSpecificExitCode);
            if ( (g_dwDebugFlags & 3) != 0 )
            {
              PuDbgPrint(
                g_pDebug,
                "inetsrv\\iis\\mb\\iisadmin\\main.cxx",
                200,
                "ReportServiceStatus",
                "dwCheckPoint              = %08lX\n",
                g_svcStatus.dwCheckPoint);
              if ( (g_dwDebugFlags & 3) != 0 )
                PuDbgPrint(
                  g_pDebug,
                  "inetsrv\\iis\\mb\\iisadmin\\main.cxx",
                  203,
                  "ReportServiceStatus",
                  "dwWaitHint                = %08lX\n",
                  g_svcStatus.dwWaitHint);
            }
          }
        }
      }
    }
  }
  if ( SetServiceStatus(g_hsvcStatus, &g_svcStatus) )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x180001a0c  mov     [rsp+arg_0], rsi
0x180001a11  push    rdi
0x180001a12  sub     rsp, 30h
0x180001a16  mov     eax, cs:g_dwDebugFlags
0x180001a1c  bt      eax, 15h
0x180001a20  jnb     loc_180001BD1
0x180001a26  lea     rdi, aReportservices; "ReportServiceStatus"
0x180001a2d  lea     rsi, aInetsrvIisMbIi_0; "inetsrv\\iis\\mb\\iisadmin\\main.cxx"
0x180001a34  test    al, 3
0x180001a36  jz      loc_180001BD1
0x180001a3c  mov     eax, cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwServiceType; _SERVICE_STATUS g_svcStatus ...
0x180001a42  mov     r9, rdi
0x180001a45  mov     rcx, cs:g_pDebug
0x180001a4c  mov     r8d, 0B9h
0x180001a52  mov     [rsp+38h+var_10], eax
0x180001a56  mov     rdx, rsi
0x180001a59  lea     rax, aDwservicetype0; "dwServiceType             = %08lX\n"
0x180001a60  mov     [rsp+38h+var_18], rax
0x180001a65  call    cs:__imp_PuDbgPrint
0x180001a6b  mov     eax, cs:g_dwDebugFlags
0x180001a71  test    al, 3
0x180001a73  jz      loc_180001BD1
0x180001a79  mov     eax, cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwCurrentState; _SERVICE_STATUS g_svcStatus ...
0x180001a7f  mov     r9, rdi
0x180001a82  mov     rcx, cs:g_pDebug
0x180001a89  mov     r8d, 0BCh
0x180001a8f  mov     [rsp+38h+var_10], eax
0x180001a93  mov     rdx, rsi
0x180001a96  lea     rax, aDwcurrentstate; "dwCurrentState            = %08lX\n"
0x180001a9d  mov     [rsp+38h+var_18], rax
0x180001aa2  call    cs:__imp_PuDbgPrint
0x180001aa8  mov     eax, cs:g_dwDebugFlags
0x180001aae  test    al, 3
0x180001ab0  jz      loc_180001BD1
0x180001ab6  mov     eax, cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted; _SERVICE_STATUS g_svcStatus ...
0x180001abc  mov     r9, rdi
0x180001abf  mov     rcx, cs:g_pDebug
0x180001ac6  mov     r8d, 0BFh
0x180001acc  mov     [rsp+38h+var_10], eax
0x180001ad0  mov     rdx, rsi
0x180001ad3  lea     rax, aDwcontrolsacce; "dwControlsAccepted        = %08lX\n"
0x180001ada  mov     [rsp+38h+var_18], rax
0x180001adf  call    cs:__imp_PuDbgPrint
0x180001ae5  mov     eax, cs:g_dwDebugFlags
0x180001aeb  test    al, 3
0x180001aed  jz      loc_180001BD1
0x180001af3  mov     eax, cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode; _SERVICE_STATUS g_svcStatus ...
0x180001af9  mov     r9, rdi
0x180001afc  mov     rcx, cs:g_pDebug
0x180001b03  mov     r8d, 0C2h
0x180001b09  mov     [rsp+38h+var_10], eax
0x180001b0d  mov     rdx, rsi
0x180001b10  lea     rax, aDwwin32exitcod; "dwWin32ExitCode           = %08lX\n"
0x180001b17  mov     [rsp+38h+var_18], rax
0x180001b1c  call    cs:__imp_PuDbgPrint
0x180001b22  mov     eax, cs:g_dwDebugFlags
0x180001b28  test    al, 3
0x180001b2a  jz      loc_180001BD1
0x180001b30  mov     eax, cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwServiceSpecificExitCode; _SERVICE_STATUS g_svcStatus ...
0x180001b36  mov     r9, rdi
0x180001b39  mov     rcx, cs:g_pDebug
0x180001b40  mov     r8d, 0C5h
0x180001b46  mov     [rsp+38h+var_10], eax
0x180001b4a  mov     rdx, rsi
0x180001b4d  lea     rax, aDwservicespeci; "dwServiceSpecificExitCode = %08lX\n"
0x180001b54  mov     [rsp+38h+var_18], rax
0x180001b59  call    cs:__imp_PuDbgPrint
0x180001b5f  mov     eax, cs:g_dwDebugFlags
0x180001b65  test    al, 3
0x180001b67  jz      short loc_180001BD1
0x180001b69  mov     eax, cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint; _SERVICE_STATUS g_svcStatus ...
0x180001b6f  mov     r9, rdi
0x180001b72  mov     rcx, cs:g_pDebug
0x180001b79  mov     r8d, 0C8h
0x180001b7f  mov     [rsp+38h+var_10], eax
0x180001b83  mov     rdx, rsi
0x180001b86  lea     rax, aDwcheckpoint08; "dwCheckPoint              = %08lX\n"
0x180001b8d  mov     [rsp+38h+var_18], rax
0x180001b92  call    cs:__imp_PuDbgPrint
0x180001b98  mov     eax, cs:g_dwDebugFlags
0x180001b9e  test    al, 3
0x180001ba0  jz      short loc_180001BD1
0x180001ba2  mov     eax, cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwWaitHint; _SERVICE_STATUS g_svcStatus ...
0x180001ba8  mov     r9, rdi
0x180001bab  mov     rcx, cs:g_pDebug
0x180001bb2  mov     r8d, 0CBh
0x180001bb8  mov     [rsp+38h+var_10], eax
0x180001bbc  mov     rdx, rsi
0x180001bbf  lea     rax, aDwwaithint08lx; "dwWaitHint                = %08lX\n"
0x180001bc6  mov     [rsp+38h+var_18], rax
0x180001bcb  call    cs:__imp_PuDbgPrint
0x180001bd1  mov     rcx, cs:?g_hsvcStatus@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180001bd8  lea     rdx, ?g_svcStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180001bdf  call    cs:__imp_SetServiceStatus
0x180001be5  test    eax, eax
0x180001be7  jnz     short loc_180001BF1
0x180001be9  call    cs:__imp_GetLastError
0x180001bef  jmp     short loc_180001BF3
0x180001bf1  xor     eax, eax
0x180001bf3  mov     rsi, [rsp+38h+arg_0]
0x180001bf8  add     rsp, 30h
0x180001bfc  pop     rdi
0x180001bfd  retn
```
