# GetProcessHandleForInetinfo(void * *)

- ea: `0x180023760`
- end: `0x180023a6e`
- name: `?GetProcessHandleForInetinfo@@YAJPEAPEAX@Z`
- size: `782`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180023c98`

## callees

- `0x180007300`
- `0x180023760`
- `0x18002c4c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800237be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002380d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023863`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800239a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800239ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800237be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002380d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023863`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800239a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800239ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023954`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023a2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023954`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023a2a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800238d4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800238d4`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180023859`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800238fe`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180023859`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800238fe`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800237ff`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800237ff`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180023a38`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180023a46`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180023a38`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180023a46`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800237ae`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800237ae`

## string_xrefs

- `0x18002389c`: `servercommon\inetsrv\iis\iisrearc\core\common\util\adminmonitor.cxx`
- `0x180023945`: `servercommon\inetsrv\iis\iisrearc\core\common\util\adminmonitor.cxx`
- `0x18002398b`: `servercommon\inetsrv\iis\iisrearc\core\common\util\adminmonitor.cxx`
- `0x180023a07`: `servercommon\inetsrv\iis\iisrearc\core\common\util\adminmonitor.cxx`
- `0x1800237e0`: `Could not open the scm manager, hr = %08x\n`
- `0x18002382f`: `Could not open the iisadmin service,hr = %08x\n`
- `0x1800238a7`: `Failed querying the iisadmin service for it's process info, hr = %08x, BytesNeeded = %d\n`
- `0x1800239e8`: `Could not open the inetinfo process, hr = %08x\n`

## pseudocode

```c
__int64 __fastcall GetProcessHandleForInetinfo(void **a1)
{
  HANDLE v2; // rdi
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // r12
  SC_HANDLE v5; // rsi
  signed int v6; // eax
  signed int v7; // ebx
  char *v8; // rax
  unsigned int v9; // r8d
  signed int v10; // eax
  signed int v11; // eax
  unsigned int v12; // r8d
  unsigned int i; // r14d
  DWORD v14; // r15d
  signed int LastError; // eax
  signed int v16; // eax
  char v18; // [rsp+28h] [rbp-41h]
  DWORD pcbBytesNeeded; // [rsp+40h] [rbp-29h] BYREF
  BYTE Buffer[16]; // [rsp+48h] [rbp-21h] BYREF
  DWORD dwProcessId[4]; // [rsp+58h] [rbp-11h]
  int v22; // [rsp+68h] [rbp-1h]

  *a1 = 0;
  v22 = 0;
  pcbBytesNeeded = 0;
  *(_OWORD *)Buffer = 0;
  v2 = 0;
  *(_OWORD *)dwProcessId = 0;
  v3 = OpenSCManagerW(0, 0, 0x80000000);
  v4 = v3;
  if ( v3 )
  {
    v5 = OpenServiceW(v3, L"IISADMIN", 0x80000000);
    if ( v5 )
    {
      if ( QueryServiceStatusEx(v5, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
      {
        v7 = 0;
        for ( i = 0; ; ++i )
        {
          v14 = dwProcessId[3];
          v2 = OpenProcess(0x100000u, 0, dwProcessId[3]);
          if ( !v2 )
            break;
          if ( !QueryServiceStatusEx(v5, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
          {
            LastError = GetLastError();
            v7 = LastError;
            if ( LastError > 0 )
              v7 = (unsigned __int16)LastError | 0x80070000;
            if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
            {
              v12 = 841;
              goto LABEL_16;
            }
            goto LABEL_37;
          }
          if ( v14 == dwProcessId[3] )
            goto LABEL_38;
          if ( i > 5 )
          {
            if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
              PuDbgPrint(
                (struct _DEBUG_PRINTS *)g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\adminmonitor.cxx",
                0x35Au,
                "GetProcessHandleForInetinfo",
                "Process id for the process we got and the current inetinfo process don't match, failing the hookup \n ",
                v18);
            v7 = -2147418113;
            goto LABEL_40;
          }
          if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
            PuDbgPrint(
              (struct _DEBUG_PRINTS *)g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\adminmonitor.cxx",
              0x364u,
              "GetProcessHandleForInetinfo",
              "Process id for the process we got and the current inetinfo process don't match, trying again \n ",
              v18);
          CloseHandle(v2);
        }
        v16 = GetLastError();
        v7 = v16;
        if ( v16 > 0 )
          v7 = (unsigned __int16)v16 | 0x80070000;
        if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
        {
          v8 = "Could not open the inetinfo process, hr = %08x\n";
          v9 = 821;
          goto LABEL_36;
        }
      }
      else
      {
        v11 = GetLastError();
        v7 = v11;
        if ( v11 > 0 )
          v7 = (unsigned __int16)v11 | 0x80070000;
        if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
        {
          v12 = 793;
LABEL_16:
          PuDbgPrint(
            (struct _DEBUG_PRINTS *)g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\adminmonitor.cxx",
            v12,
            "GetProcessHandleForInetinfo",
            "Failed querying the iisadmin service for it's process info, hr = %08x, BytesNeeded = %d\n",
            v7);
        }
      }
    }
    else
    {
      v10 = GetLastError();
      v7 = v10;
      if ( v10 > 0 )
        v7 = (unsigned __int16)v10 | 0x80070000;
      if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
      {
        v8 = "Could not open the iisadmin service,hr = %08x\n";
        v9 = 776;
        goto LABEL_36;
      }
    }
  }
  else
  {
    v5 = 0;
    v6 = GetLastError();
    v7 = v6;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
    {
      v8 = "Could not open the scm manager, hr = %08x\n";
      v9 = 764;
LABEL_36:
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\adminmonitor.cxx",
        v9,
        "GetProcessHandleForInetinfo",
        v8,
        v7);
    }
  }
LABEL_37:
  if ( v7 < 0 )
  {
    if ( v2 )
LABEL_40:
      CloseHandle(v2);
  }
  else
  {
LABEL_38:
    *a1 = v2;
  }
  if ( v5 )
    CloseServiceHandle(v5);
  if ( v4 )
    CloseServiceHandle(v4);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180023760  push    rbp
0x180023762  push    rbx
0x180023763  push    rsi
0x180023764  push    rdi
0x180023765  push    r12
0x180023767  push    r13
0x180023769  push    r14
0x18002376b  push    r15
0x18002376d  lea     rbp, [rsp-1Fh]
0x180023772  sub     rsp, 88h
0x180023779  mov     rax, cs:__security_cookie
0x180023780  xor     rax, rsp
0x180023783  mov     [rbp+57h+var_50], rax
0x180023787  xor     eax, eax
0x180023789  xorps   xmm0, xmm0
0x18002378c  mov     [rcx], rax
0x18002378f  mov     r13, rcx
0x180023792  mov     ebx, 80000000h
0x180023797  mov     [rbp+57h+var_58], eax
0x18002379a  xor     ecx, ecx; lpMachineName
0x18002379c  mov     [rbp+57h+var_80], eax
0x18002379f  mov     r8d, ebx; dwDesiredAccess
0x1800237a2  xor     edx, edx; lpDatabaseName
0x1800237a4  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x1800237a8  xor     edi, edi
0x1800237aa  movups  xmmword ptr [rbp+57h+dwProcessId], xmm0
0x1800237ae  call    cs:__imp_OpenSCManagerW
0x1800237b4  mov     r12, rax
0x1800237b7  test    rax, rax
0x1800237ba  jnz     short loc_1800237F2
0x1800237bc  xor     esi, esi
0x1800237be  call    cs:__imp_GetLastError
0x1800237c4  mov     ebx, eax
0x1800237c6  test    eax, eax
0x1800237c8  jle     short loc_1800237D3
0x1800237ca  movzx   ebx, ax
0x1800237cd  or      ebx, 80070000h
0x1800237d3  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800237da  jz      loc_180023A18
0x1800237e0  lea     rax, aCouldNotOpenTh_0; "Could not open the scm manager, hr = %0"...
0x1800237e7  mov     r8d, 2FCh
0x1800237ed  jmp     loc_1800239F5
0x1800237f2  mov     r8d, ebx; dwDesiredAccess
0x1800237f5  lea     rdx, ServiceName; "IISADMIN"
0x1800237fc  mov     rcx, r12; hSCManager
0x1800237ff  call    cs:__imp_OpenServiceW
0x180023805  mov     rsi, rax
0x180023808  test    rax, rax
0x18002380b  jnz     short loc_180023841
0x18002380d  call    cs:__imp_GetLastError
0x180023813  mov     ebx, eax
0x180023815  test    eax, eax
0x180023817  jle     short loc_180023822
0x180023819  movzx   ebx, ax
0x18002381c  or      ebx, 80070000h
0x180023822  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180023829  jz      loc_180023A18
0x18002382f  lea     rax, aCouldNotOpenTh_1; "Could not open the iisadmin service,hr "...
0x180023836  mov     r8d, 308h
0x18002383c  jmp     loc_1800239F5
0x180023841  lea     rax, [rbp+57h+var_80]
0x180023845  mov     r9d, 24h ; '$'; cbBufSize
0x18002384b  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x18002384f  mov     [rsp+0C0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180023854  xor     edx, edx; InfoLevel
0x180023856  mov     rcx, rsi; hService
0x180023859  call    cs:__imp_QueryServiceStatusEx
0x18002385f  test    eax, eax
0x180023861  jnz     short loc_1800238C1
0x180023863  call    cs:__imp_GetLastError
0x180023869  mov     ebx, eax
0x18002386b  test    eax, eax
0x18002386d  jle     short loc_180023878
0x18002386f  movzx   ebx, ax
0x180023872  or      ebx, 80070000h
0x180023878  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x18002387f  jz      loc_180023A18
0x180023885  mov     r8d, 319h; unsigned int
0x18002388b  mov     eax, [rbp+57h+var_80]
0x18002388e  lea     r9, aGetprocesshand; "GetProcessHandleForInetinfo"
0x180023895  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002389c  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800238a3  mov     [rsp+0C0h+var_90], eax
0x1800238a7  lea     rax, aFailedQuerying; "Failed querying the iisadmin service fo"...
0x1800238ae  mov     dword ptr [rsp+0C0h+var_98], ebx; char
0x1800238b2  mov     [rsp+0C0h+pcbBytesNeeded], rax; char *
0x1800238b7  call    PuDbgPrint
0x1800238bc  jmp     loc_180023A18
0x1800238c1  xor     ebx, ebx
0x1800238c3  xor     r14d, r14d
0x1800238c6  mov     r15d, [rbp+57h+dwProcessId+0Ch]
0x1800238ca  xor     edx, edx; bInheritHandle
0x1800238cc  mov     r8d, r15d; dwProcessId
0x1800238cf  mov     ecx, 100000h; dwDesiredAccess
0x1800238d4  call    cs:__imp_OpenProcess
0x1800238da  mov     rdi, rax
0x1800238dd  test    rax, rax
0x1800238e0  jz      loc_1800239CA
0x1800238e6  lea     rax, [rbp+57h+var_80]
0x1800238ea  mov     r9d, 24h ; '$'; cbBufSize
0x1800238f0  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x1800238f4  mov     [rsp+0C0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800238f9  xor     edx, edx; InfoLevel
0x1800238fb  mov     rcx, rsi; hService
0x1800238fe  call    cs:__imp_QueryServiceStatusEx
0x180023904  test    eax, eax
0x180023906  jz      loc_1800239A1
0x18002390c  cmp     r15d, [rbp+57h+dwProcessId+0Ch]
0x180023910  jz      loc_180023A1C
0x180023916  cmp     r14d, 5
0x18002391a  ja      short loc_180023962
0x18002391c  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180023923  jz      short loc_180023951
0x180023925  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002392c  lea     rax, aProcessIdForTh; "Process id for the process we got and t"...
0x180023933  lea     r9, aGetprocesshand; "GetProcessHandleForInetinfo"
0x18002393a  mov     [rsp+0C0h+pcbBytesNeeded], rax; char *
0x18002393f  mov     r8d, 364h; unsigned int
0x180023945  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002394c  call    PuDbgPrint
0x180023951  mov     rcx, rdi; hObject
0x180023954  call    cs:__imp_CloseHandle
0x18002395a  inc     r14d
0x18002395d  jmp     loc_1800238C6
0x180023962  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180023969  jz      short loc_180023997
0x18002396b  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180023972  lea     rax, aProcessIdForTh_0; "Process id for the process we got and t"...
0x180023979  lea     r9, aGetprocesshand; "GetProcessHandleForInetinfo"
0x180023980  mov     [rsp+0C0h+pcbBytesNeeded], rax; char *
0x180023985  mov     r8d, 35Ah; unsigned int
0x18002398b  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180023992  call    PuDbgPrint
0x180023997  mov     ebx, 8000FFFFh
0x18002399c  jmp     loc_180023A27
0x1800239a1  call    cs:__imp_GetLastError
0x1800239a7  mov     ebx, eax
0x1800239a9  test    eax, eax
0x1800239ab  jle     short loc_1800239B6
0x1800239ad  movzx   ebx, ax
0x1800239b0  or      ebx, 80070000h
0x1800239b6  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800239bd  jz      short loc_180023A18
0x1800239bf  mov     r8d, 349h
0x1800239c5  jmp     loc_18002388B
0x1800239ca  call    cs:__imp_GetLastError
0x1800239d0  mov     ebx, eax
0x1800239d2  test    eax, eax
0x1800239d4  jle     short loc_1800239DF
0x1800239d6  movzx   ebx, ax
0x1800239d9  or      ebx, 80070000h
0x1800239df  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800239e6  jz      short loc_180023A18
0x1800239e8  lea     rax, aCouldNotOpenTh; "Could not open the inetinfo process, hr"...
0x1800239ef  mov     r8d, 335h; unsigned int
0x1800239f5  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800239fc  lea     r9, aGetprocesshand; "GetProcessHandleForInetinfo"
0x180023a03  mov     dword ptr [rsp+0C0h+var_98], ebx; char
0x180023a07  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180023a0e  mov     [rsp+0C0h+pcbBytesNeeded], rax; char *
0x180023a13  call    PuDbgPrint
0x180023a18  test    ebx, ebx
0x180023a1a  js      short loc_180023A22
0x180023a1c  mov     [r13+0], rdi
0x180023a20  jmp     short loc_180023A30
0x180023a22  test    rdi, rdi
0x180023a25  jz      short loc_180023A30
0x180023a27  mov     rcx, rdi; hObject
0x180023a2a  call    cs:__imp_CloseHandle
0x180023a30  test    rsi, rsi
0x180023a33  jz      short loc_180023A3E
0x180023a35  mov     rcx, rsi; hSCObject
0x180023a38  call    cs:__imp_CloseServiceHandle
0x180023a3e  test    r12, r12
0x180023a41  jz      short loc_180023A4C
0x180023a43  mov     rcx, r12; hSCObject
0x180023a46  call    cs:__imp_CloseServiceHandle
0x180023a4c  mov     eax, ebx
0x180023a4e  mov     rcx, [rbp+57h+var_50]
0x180023a52  xor     rcx, rsp; StackCookie
0x180023a55  call    __security_check_cookie
0x180023a5a  add     rsp, 88h
0x180023a61  pop     r15
0x180023a63  pop     r14
0x180023a65  pop     r13
0x180023a67  pop     r12
0x180023a69  pop     rdi
0x180023a6a  pop     rsi
0x180023a6b  pop     rbx
0x180023a6c  pop     rbp
0x180023a6d  retn
```
