# ServiceMain(ulong,ushort * * const)

- ea: `0x180006000`
- end: `0x1800061bc`
- name: `?ServiceMain@@YAXKQEAPEAG@Z`
- size: `444`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **const)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180006000`
- `0x180006890`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000602b`
- `msvcrt!_wcsicmp` at `0x18000602b`
- `KERNEL32!GetExitCodeThread` at `0x180006125`
- `KERNEL32!GetExitCodeThread` at `0x180006125`
- `KERNEL32!CreateThread` at `0x18000605c`
- `KERNEL32!CreateThread` at `0x18000605c`
- `KERNEL32!WaitForSingleObject` at `0x1800060dc`
- `KERNEL32!WaitForSingleObject` at `0x1800060dc`
- `KERNEL32!GetLastError` at `0x18000606a`
- `KERNEL32!GetLastError` at `0x1800060e7`
- `KERNEL32!GetLastError` at `0x18000612f`
- `KERNEL32!GetLastError` at `0x18000606a`
- `KERNEL32!GetLastError` at `0x1800060e7`
- `KERNEL32!GetLastError` at `0x18000612f`
- `KERNEL32!CloseHandle` at `0x1800061b0`
- `KERNEL32!CloseHandle` at `0x1800061b0`
- `iisutil!PuDbgPrint` at `0x1800060b9`
- `iisutil!PuDbgPrint` at `0x1800061a7`
- `iisutil!PuDbgPrint` at `0x1800060b9`
- `iisutil!PuDbgPrint` at `0x1800061a7`

## string_xrefs

- `0x180006092`: `CreateThread() failed.  hr = %x\n`
- `0x1800060a0`: `ServiceMain`
- `0x180006194`: `ServiceMain`
- `0x1800060b2`: `inetsrv\iis\iisrearc\ftp\server\core\ftp_service.cxx`
- `0x18000619b`: `inetsrv\iis\iisrearc\ftp\server\core\ftp_service.cxx`
- `0x180006158`: `GetExitCodeThread() failed.  hr = %x\n`
- `0x180006186`: `FTPServiceThreadProc() failed.  hr = %x\n`

## pseudocode

```c
void __fastcall ServiceMain(int a1, const wchar_t **a2)
{
  HANDLE v2; // rax
  void *v3; // rbx
  int v4; // eax
  unsigned int v5; // ecx
  int LastError; // eax
  int v7; // eax
  DWORD v8; // eax
  LPDWORD lpThreadId; // [rsp+28h] [rbp-10h]
  DWORD ExitCode; // [rsp+40h] [rbp+8h] BYREF
  DWORD ThreadId; // [rsp+50h] [rbp+18h] BYREF

  if ( a1 == 1 )
  {
    ExitCode = 0;
    ThreadId = 0;
    if ( !_wcsicmp(*a2, L"FTPSVC") )
    {
      v2 = CreateThread(0, 0x8000u, (LPTHREAD_START_ROUTINE)FTPServiceThreadProc, 0, 0, &ThreadId);
      v3 = v2;
      if ( v2 )
      {
        if ( WaitForSingleObject(v2, 0xFFFFFFFF) == -1 )
        {
          LastError = GetLastError();
          ExitCode = LastError;
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          if ( (g_dwDebugFlags & 3) != 0 )
          {
            LODWORD(lpThreadId) = LastError;
            PuDbgPrint(
              g_pDebug,
              "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_service.cxx",
              412,
              "ServiceMain",
              "WaitForSingleObject() failed.  hr = %x\n",
              lpThreadId);
          }
        }
        else if ( GetExitCodeThread(v3, &ExitCode) )
        {
          v8 = ExitCode;
          if ( ExitCode )
          {
            if ( (int)ExitCode > 0 )
              v8 = (unsigned __int16)ExitCode | 0x80070000;
            if ( (g_dwDebugFlags & 3) != 0 )
            {
              LODWORD(lpThreadId) = v8;
              PuDbgPrint(
                g_pDebug,
                "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_service.cxx",
                439,
                "ServiceMain",
                "FTPServiceThreadProc() failed.  hr = %x\n",
                lpThreadId);
            }
          }
        }
        else
        {
          v7 = GetLastError();
          ExitCode = v7;
          if ( v7 > 0 )
            v7 = (unsigned __int16)v7 | 0x80070000;
          if ( (g_dwDebugFlags & 3) != 0 )
          {
            LODWORD(lpThreadId) = v7;
            PuDbgPrint(
              g_pDebug,
              "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_service.cxx",
              425,
              "ServiceMain",
              "GetExitCodeThread() failed.  hr = %x\n",
              lpThreadId);
          }
        }
        CloseHandle(v3);
      }
      else
      {
        v4 = GetLastError();
        ExitCode = v4;
        if ( v4 > 0 )
          v5 = (unsigned __int16)v4 | 0x80070000;
        else
          v5 = v4;
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_service.cxx",
            386,
            "ServiceMain",
            "CreateThread() failed.  hr = %x\n",
            v5);
          v4 = ExitCode;
        }
        NT_SERVICE::ReportFatalServiceStartupError(L"FTPSVC", v4);
      }
    }
  }
}

```

## disassembly

```asm
0x180006000  cmp     ecx, 1
0x180006003  jnz     locret_1800061BB
0x180006009  push    rbx
0x18000600a  sub     rsp, 30h
0x18000600e  mov     rax, rdx
0x180006011  mov     [rsp+38h+ExitCode], 0
0x180006019  lea     rdx, aFtpsvc; "FTPSVC"
0x180006020  mov     [rsp+38h+ThreadId], 0
0x180006028  mov     rcx, [rax]; String1
0x18000602b  call    cs:__imp__wcsicmp
0x180006031  test    eax, eax
0x180006033  jnz     loc_1800061B6
0x180006039  lea     rax, [rsp+38h+ThreadId]
0x18000603e  xor     r9d, r9d; lpParameter
0x180006041  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180006046  lea     r8, ?FTPServiceThreadProc@@YAKPEAX@Z; lpStartAddress
0x18000604d  mov     edx, 8000h; dwStackSize
0x180006052  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18000605a  xor     ecx, ecx; lpThreadAttributes
0x18000605c  call    cs:__imp_CreateThread
0x180006062  mov     rbx, rax
0x180006065  test    rax, rax
0x180006068  jnz     short loc_1800060D6
0x18000606a  call    cs:__imp_GetLastError
0x180006070  mov     [rsp+38h+ExitCode], eax
0x180006074  test    eax, eax
0x180006076  jg      short loc_18000607C
0x180006078  mov     ecx, eax
0x18000607a  jmp     short loc_180006085
0x18000607c  movzx   ecx, ax
0x18000607f  or      ecx, 80070000h
0x180006085  test    byte ptr cs:g_dwDebugFlags, 3
0x18000608c  jz      short loc_1800060C3
0x18000608e  mov     dword ptr [rsp+38h+lpThreadId], ecx
0x180006092  lea     rax, aCreatethreadFa_0; "CreateThread() failed.  hr = %x\n"
0x180006099  mov     rcx, cs:g_pDebug
0x1800060a0  lea     r9, aServicemain_0; "ServiceMain"
0x1800060a7  mov     r8d, 182h
0x1800060ad  mov     qword ptr [rsp+38h+dwCreationFlags], rax
0x1800060b2  lea     rdx, aInetsrvIisIisr_29; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x1800060b9  call    cs:__imp_PuDbgPrint
0x1800060bf  mov     eax, [rsp+38h+ExitCode]
0x1800060c3  mov     edx, eax; unsigned int
0x1800060c5  lea     rcx, aFtpsvc; "FTPSVC"
0x1800060cc  call    ?ReportFatalServiceStartupError@NT_SERVICE@@SAXPEBGK@Z; NT_SERVICE::ReportFatalServiceStartupError(ushort const *,ulong)
0x1800060d1  jmp     loc_1800061B6
0x1800060d6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800060d9  mov     rcx, rbx; hHandle
0x1800060dc  call    cs:__imp_WaitForSingleObject
0x1800060e2  cmp     eax, 0FFFFFFFFh
0x1800060e5  jnz     short loc_18000611D
0x1800060e7  call    cs:__imp_GetLastError
0x1800060ed  mov     [rsp+38h+ExitCode], eax
0x1800060f1  test    eax, eax
0x1800060f3  jle     short loc_1800060FD
0x1800060f5  movzx   eax, ax
0x1800060f8  or      eax, 80070000h
0x1800060fd  test    byte ptr cs:g_dwDebugFlags, 3
0x180006104  jz      loc_1800061AD
0x18000610a  mov     dword ptr [rsp+38h+lpThreadId], eax
0x18000610e  mov     r8d, 19Ch
0x180006114  lea     rax, aWaitforsingleo; "WaitForSingleObject() failed.  hr = %x"...
0x18000611b  jmp     short loc_18000618D
0x18000611d  lea     rdx, [rsp+38h+ExitCode]; lpExitCode
0x180006122  mov     rcx, rbx; hThread
0x180006125  call    cs:__imp_GetExitCodeThread
0x18000612b  test    eax, eax
0x18000612d  jnz     short loc_180006161
0x18000612f  call    cs:__imp_GetLastError
0x180006135  mov     [rsp+38h+ExitCode], eax
0x180006139  test    eax, eax
0x18000613b  jle     short loc_180006145
0x18000613d  movzx   eax, ax
0x180006140  or      eax, 80070000h
0x180006145  test    byte ptr cs:g_dwDebugFlags, 3
0x18000614c  jz      short loc_1800061AD
0x18000614e  mov     dword ptr [rsp+38h+lpThreadId], eax
0x180006152  mov     r8d, 1A9h
0x180006158  lea     rax, aGetexitcodethr; "GetExitCodeThread() failed.  hr = %x\n"
0x18000615f  jmp     short loc_18000618D
0x180006161  mov     eax, [rsp+38h+ExitCode]
0x180006165  test    eax, eax
0x180006167  jz      short loc_1800061AD
0x180006169  jle     short loc_180006173
0x18000616b  movzx   eax, ax
0x18000616e  or      eax, 80070000h
0x180006173  test    byte ptr cs:g_dwDebugFlags, 3
0x18000617a  jz      short loc_1800061AD
0x18000617c  mov     dword ptr [rsp+38h+lpThreadId], eax
0x180006180  mov     r8d, 1B7h
0x180006186  lea     rax, aFtpservicethre; "FTPServiceThreadProc() failed.  hr = %x"...
0x18000618d  mov     rcx, cs:g_pDebug
0x180006194  lea     r9, aServicemain_0; "ServiceMain"
0x18000619b  lea     rdx, aInetsrvIisIisr_29; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x1800061a2  mov     qword ptr [rsp+38h+dwCreationFlags], rax
0x1800061a7  call    cs:__imp_PuDbgPrint
0x1800061ad  mov     rcx, rbx; hObject
0x1800061b0  call    cs:__imp_CloseHandle
0x1800061b6  add     rsp, 30h
0x1800061ba  pop     rbx
0x1800061bb  retn
```
