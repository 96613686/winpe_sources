# FTP_HOST_MONITOR::RecycleFtpHostProcess(void)

- ea: `0x18001a35c`
- end: `0x18001a626`
- name: `?RecycleFtpHostProcess@FTP_HOST_MONITOR@@AEAAJXZ`
- size: `714`
- prototype: `__int64 __fastcall(FTP_HOST_MONITOR *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18001a290`

## callees

- `0x18001a35c`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `KERNEL32!OpenProcess` at `0x18001a431`
- `KERNEL32!OpenProcess` at `0x18001a431`
- `KERNEL32!CheckRemoteDebuggerPresent` at `0x18001a477`
- `KERNEL32!CheckRemoteDebuggerPresent` at `0x18001a477`
- `KERNEL32!TerminateProcess` at `0x18001a497`
- `KERNEL32!TerminateProcess` at `0x18001a497`
- `KERNEL32!GetLastError` at `0x18001a43f`
- `KERNEL32!GetLastError` at `0x18001a4a1`
- `KERNEL32!GetLastError` at `0x18001a43f`
- `KERNEL32!GetLastError` at `0x18001a4a1`
- `KERNEL32!CloseHandle` at `0x18001a5fa`
- `KERNEL32!CloseHandle` at `0x18001a5fa`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18001a56a`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18001a56a`
- `iisutil!PuDbgPrintError` at `0x18001a5cf`
- `iisutil!PuDbgPrintError` at `0x18001a5cf`

## string_xrefs

- `0x18001a3fe`: `pFtpHost->GetProcessId() failed)`
- `0x18001a5a4`: `UpdateFtpHost() failed`

## pseudocode

```c
__int64 __fastcall FTP_HOST_MONITOR::RecycleFtpHostProcess(FTP_HOST_MONITOR *this)
{
  void *v2; // rdi
  signed int v3; // ebx
  HANDLE v4; // rax
  int v5; // eax
  signed int LastError; // eax
  __int64 v7; // rax
  CEtwTracer *v8; // rax
  FTP_SERVERP *v9; // rcx
  __int64 v10; // rdx
  __int64 v12; // [rsp+30h] [rbp-29h] BYREF
  WINBOOL pbDebuggerPresent; // [rsp+38h] [rbp-21h] BYREF
  DWORD dwProcessId; // [rsp+3Ch] [rbp-1Dh] BYREF
  DWORD v15; // [rsp+40h] [rbp-19h] BYREF
  __int16 v16; // [rsp+50h] [rbp-9h] BYREF
  __int128 v17; // [rsp+52h] [rbp-7h]
  __int128 v18; // [rsp+62h] [rbp+9h]
  _BYTE v19[22]; // [rsp+72h] [rbp+19h]
  int v20; // [rsp+88h] [rbp+2Fh]
  int v21; // [rsp+8Ch] [rbp+33h]

  v12 = 0;
  v2 = 0;
  dwProcessId = 0;
  pbDebuggerPresent = 0;
  v3 = (*(__int64 (__fastcall **)(FTP_SERVERP *, __int64 *))(*(_QWORD *)g_pFtpServer + 112LL))(g_pFtpServer, &v12);
  if ( v3 >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(__int64, DWORD *))(*(_QWORD *)v12 + 40LL))(v12, &dwProcessId);
    if ( v3 >= 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      v12 = 0;
      v4 = OpenProcess(1u, 0, dwProcessId);
      v2 = v4;
      if ( v4 )
      {
        v5 = CheckRemoteDebuggerPresent(v4, &pbDebuggerPresent);
        if ( v5 )
          v5 = pbDebuggerPresent;
        else
          pbDebuggerPresent = 0;
        if ( !v5 )
        {
          if ( TerminateProcess(v2, 0xFFFFFFFF)
            || (LastError = GetLastError(), v3 = LastError, LastError == 5)
            || LastError == 87 )
          {
            v7 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
            if ( *(_DWORD *)(v7 + 8) && (*(_BYTE *)(v7 + 40) & 0x12) != 0 && *(_DWORD *)(v7 + 44) >= 3u )
            {
              v15 = dwProcessId;
              v8 = (CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
              *(_OWORD *)v19 = 0;
              *(_DWORD *)&v19[10] = 1703936;
              v16 = 64;
              v21 = 0;
              v20 = 4;
              v17 = 0;
              WORD2(v17) = 1;
              v18 = 0;
              *(_QWORD *)((char *)&v18 + 6) = &`FtpExtensibilityEvents::GetAreaGuid'::`2'::AreaGuid;
              *(_QWORD *)&v19[14] = &v15;
              BYTE2(v17) = 10;
              CEtwTracer::EtwTraceEvent(v8, (struct _EVENT_TRACE_HEADER *)&v16);
            }
            v9 = g_pFtpServer;
            v10 = v12;
            *((_DWORD *)this + 12) = 0;
            *((_DWORD *)this + 18) = 0;
            v3 = (*(__int64 (__fastcall **)(FTP_SERVERP *, __int64))(*(_QWORD *)v9 + 120LL))(v9, v10);
            if ( v3 < 0 && (g_dwDebugFlags & 0xF) != 0 )
              PuDbgPrintError(
                g_pDebug,
                "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftphost_monitor.cxx",
                330,
                "FTP_HOST_MONITOR::RecycleFtpHostProcess",
                v3,
                "UpdateFtpHost() failed");
          }
          else
          {
            if ( LastError > 0 )
              v3 = (unsigned __int16)LastError | 0x80070000;
            if ( (g_dwDebugFlags & 0xF) != 0 )
              PuDbgPrintError(
                g_pDebug,
                "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftphost_monitor.cxx",
                301,
                "FTP_HOST_MONITOR::RecycleFtpHostProcess",
                v3,
                "TerminateProcess() failed\n");
          }
        }
      }
      else if ( GetLastError() == 87 )
      {
        v3 = -2147024809;
      }
      else
      {
        (*(void (__fastcall **)(FTP_SERVERP *, __int64))(*(_QWORD *)g_pFtpServer + 120LL))(g_pFtpServer, v12);
      }
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftphost_monitor.cxx",
        223,
        "FTP_HOST_MONITOR::RecycleFtpHostProcess",
        v3,
        "pFtpHost->GetProcessId() failed)");
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    PuDbgPrintError(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftphost_monitor.cxx",
      208,
      "FTP_HOST_MONITOR::RecycleFtpHostProcess",
      v3,
      "GetReferencedProcessHost() failed");
  }
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  if ( v2 )
    CloseHandle(v2);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001a35c  mov     [rsp-8+arg_8], rbx
0x18001a361  mov     [rsp-8+arg_10], rsi
0x18001a366  push    rbp
0x18001a367  push    rdi
0x18001a368  push    r15
0x18001a36a  lea     rbp, [rsp-47h]
0x18001a36f  sub     rsp, 0A0h
0x18001a376  mov     rax, cs:__security_cookie
0x18001a37d  xor     rax, rsp
0x18001a380  mov     [rbp+57h+var_20], rax
0x18001a384  mov     rsi, rcx
0x18001a387  mov     [rbp+57h+var_80], 0
0x18001a38f  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001a396  lea     rdx, [rbp+57h+var_80]
0x18001a39a  xor     edi, edi
0x18001a39c  mov     [rbp+57h+dwProcessId], 0
0x18001a3a3  mov     [rbp+57h+pbDebuggerPresent], edi
0x18001a3a6  mov     rax, [rcx]
0x18001a3a9  mov     rax, [rax+70h]
0x18001a3ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3b2  mov     ebx, eax
0x18001a3b4  test    eax, eax
0x18001a3b6  jns     short loc_18001A3D7
0x18001a3b8  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001a3bf  jz      loc_18001A5D5
0x18001a3c5  lea     rax, aGetreferencedp; "GetReferencedProcessHost() failed"
0x18001a3cc  mov     r8d, 0D0h
0x18001a3d2  jmp     loc_18001A5B1
0x18001a3d7  mov     rcx, [rbp+57h+var_80]
0x18001a3db  lea     rdx, [rbp+57h+dwProcessId]
0x18001a3df  mov     rax, [rcx]
0x18001a3e2  mov     rax, [rax+28h]
0x18001a3e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3eb  mov     ebx, eax
0x18001a3ed  test    eax, eax
0x18001a3ef  jns     short loc_18001A410
0x18001a3f1  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001a3f8  jz      loc_18001A5D5
0x18001a3fe  lea     rax, aPftphostGetpro; "pFtpHost->GetProcessId() failed)"
0x18001a405  mov     r8d, 0DFh
0x18001a40b  jmp     loc_18001A5B1
0x18001a410  mov     rcx, [rbp+57h+var_80]
0x18001a414  mov     rax, [rcx]
0x18001a417  mov     rax, [rax+10h]
0x18001a41b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a420  mov     r8d, [rbp+57h+dwProcessId]; dwProcessId
0x18001a424  xor     edx, edx; bInheritHandle
0x18001a426  mov     [rbp+57h+var_80], rdi
0x18001a42a  lea     r15d, [rdx+1]
0x18001a42e  mov     ecx, r15d; dwDesiredAccess
0x18001a431  call    cs:__imp_OpenProcess
0x18001a437  mov     rdi, rax
0x18001a43a  test    rax, rax
0x18001a43d  jnz     short loc_18001A470
0x18001a43f  call    cs:__imp_GetLastError
0x18001a445  cmp     eax, 57h ; 'W'
0x18001a448  jz      short loc_18001A466
0x18001a44a  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001a451  mov     rdx, [rcx]
0x18001a454  mov     rax, [rdx+78h]
0x18001a458  mov     rdx, [rbp+57h+var_80]
0x18001a45c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a461  jmp     loc_18001A5D5
0x18001a466  mov     ebx, 80070057h
0x18001a46b  jmp     loc_18001A5D5
0x18001a470  lea     rdx, [rbp+57h+pbDebuggerPresent]; pbDebuggerPresent
0x18001a474  mov     rcx, rdi; hProcess
0x18001a477  call    cs:__imp_CheckRemoteDebuggerPresent
0x18001a47d  test    eax, eax
0x18001a47f  jnz     short loc_18001A486
0x18001a481  mov     [rbp+57h+pbDebuggerPresent], eax
0x18001a484  jmp     short loc_18001A489
0x18001a486  mov     eax, [rbp+57h+pbDebuggerPresent]
0x18001a489  test    eax, eax
0x18001a48b  jnz     loc_18001A5D5
0x18001a491  or      edx, 0FFFFFFFFh; uExitCode
0x18001a494  mov     rcx, rdi; hProcess
0x18001a497  call    cs:__imp_TerminateProcess
0x18001a49d  test    eax, eax
0x18001a49f  jnz     short loc_18001A4DF
0x18001a4a1  call    cs:__imp_GetLastError
0x18001a4a7  mov     ebx, eax
0x18001a4a9  cmp     eax, 5
0x18001a4ac  jz      short loc_18001A4DF
0x18001a4ae  cmp     eax, 57h ; 'W'
0x18001a4b1  jz      short loc_18001A4DF
0x18001a4b3  test    eax, eax
0x18001a4b5  jle     short loc_18001A4C0
0x18001a4b7  movzx   ebx, ax
0x18001a4ba  or      ebx, 80070000h
0x18001a4c0  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001a4c7  jz      loc_18001A5D5
0x18001a4cd  lea     rax, aTerminateproce; "TerminateProcess() failed\n"
0x18001a4d4  mov     r8d, 12Dh
0x18001a4da  jmp     loc_18001A5B1
0x18001a4df  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001a4e6  mov     rax, [rcx]
0x18001a4e9  mov     rax, [rax+20h]
0x18001a4ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4f2  cmp     dword ptr [rax+8], 0
0x18001a4f6  jz      short loc_18001A570
0x18001a4f8  test    byte ptr [rax+28h], 12h
0x18001a4fc  jz      short loc_18001A570
0x18001a4fe  cmp     dword ptr [rax+2Ch], 3
0x18001a502  jb      short loc_18001A570
0x18001a504  mov     eax, [rbp+57h+dwProcessId]
0x18001a507  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001a50e  mov     [rbp+57h+var_70], eax
0x18001a511  mov     rax, [rcx]
0x18001a514  mov     rax, [rax+20h]
0x18001a518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a51d  xorps   xmm0, xmm0
0x18001a520  lea     rdx, [rbp+57h+var_60]
0x18001a524  movups  xmmword ptr [rbp+57h+var_3E], xmm0
0x18001a528  mov     ecx, 40h ; '@'
0x18001a52d  mov     dword ptr [rbp+57h+var_3E+0Ah], 1A0000h
0x18001a534  mov     [rbp+57h+var_60], cx
0x18001a538  lea     rcx, ?AreaGuid@?1??GetAreaGuid@FtpExtensibilityEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `FtpExtensibilityEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18001a53f  movups  xmmword ptr [rbp+57h+var_3E+0Eh], xmm0
0x18001a543  mov     [rbp+57h+var_28], 4
0x18001a54a  movups  [rbp+57h+var_5E], xmm0
0x18001a54e  mov     word ptr [rbp+57h+var_5E+4], r15w
0x18001a553  movups  [rbp+57h+var_4E], xmm0
0x18001a557  mov     qword ptr [rbp+57h+var_4E+6], rcx
0x18001a55b  lea     rcx, [rbp+57h+var_70]
0x18001a55f  mov     qword ptr [rbp+57h+var_3E+0Eh], rcx
0x18001a563  mov     rcx, rax
0x18001a566  mov     byte ptr [rbp+57h+var_5E+2], 0Ah
0x18001a56a  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z; CEtwTracer::EtwTraceEvent(_EVENT_TRACE_HEADER *)
0x18001a570  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001a577  mov     rdx, [rbp+57h+var_80]
0x18001a57b  mov     dword ptr [rsi+30h], 0
0x18001a582  mov     dword ptr [rsi+48h], 0
0x18001a589  mov     rax, [rcx]
0x18001a58c  mov     rax, [rax+78h]
0x18001a590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a595  mov     ebx, eax
0x18001a597  test    eax, eax
0x18001a599  jns     short loc_18001A5D5
0x18001a59b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001a5a2  jz      short loc_18001A5D5
0x18001a5a4  lea     rax, aUpdateftphostF; "UpdateFtpHost() failed"
0x18001a5ab  mov     r8d, 14Ah
0x18001a5b1  mov     rcx, cs:g_pDebug
0x18001a5b8  lea     r9, aFtpHostMonitor; "FTP_HOST_MONITOR::RecycleFtpHostProcess"
0x18001a5bf  mov     [rsp+0B0h+var_88], rax
0x18001a5c4  lea     rdx, aInetsrvIisIisr_25; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18001a5cb  mov     [rsp+0B0h+var_90], ebx
0x18001a5cf  call    cs:__imp_PuDbgPrintError
0x18001a5d5  mov     rcx, [rbp+57h+var_80]
0x18001a5d9  test    rcx, rcx
0x18001a5dc  jz      short loc_18001A5F2
0x18001a5de  mov     rax, [rcx]
0x18001a5e1  mov     rax, [rax+10h]
0x18001a5e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5ea  mov     [rbp+57h+var_80], 0
0x18001a5f2  test    rdi, rdi
0x18001a5f5  jz      short loc_18001A600
0x18001a5f7  mov     rcx, rdi; hObject
0x18001a5fa  call    cs:__imp_CloseHandle
0x18001a600  mov     eax, ebx
0x18001a602  mov     rcx, [rbp+57h+var_20]
0x18001a606  xor     rcx, rsp; StackCookie
0x18001a609  call    __security_check_cookie
0x18001a60e  lea     r11, [rsp+0B0h+var_10]
0x18001a616  mov     rbx, [r11+28h]
0x18001a61a  mov     rsi, [r11+30h]
0x18001a61e  mov     rsp, r11
0x18001a621  pop     r15
0x18001a623  pop     rdi
0x18001a624  pop     rbp
0x18001a625  retn
```
