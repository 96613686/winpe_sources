# GetProcessHandleForInetinfo(void * *)

- ea: `0x1800250ac`
- end: `0x18002540f`
- name: `?GetProcessHandleForInetinfo@@YAJPEAPEAX@Z`
- size: `867`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002566c`

## callees

- `0x180008000`
- `0x1800250ac`
- `0x18002e560`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025110`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002516b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800251cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025323`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025352`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025110`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002516b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800251cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025323`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025352`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800252d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800253b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800252d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800253b8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180025244`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180025244`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800251bd`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180025274`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800251bd`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180025274`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180025157`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180025157`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800253cc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800253e0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800253cc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800253e0`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800250fa`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800250fa`

## string_xrefs

- `0x18002520c`: `servercommon\inetsrv\iis\iisrearc\core\common\util\adminmonitor.cxx`
- `0x1800252c1`: `servercommon\inetsrv\iis\iisrearc\core\common\util\adminmonitor.cxx`
- `0x18002530d`: `servercommon\inetsrv\iis\iisrearc\core\common\util\adminmonitor.cxx`
- `0x180025395`: `servercommon\inetsrv\iis\iisrearc\core\common\util\adminmonitor.cxx`
- `0x180025138`: `Could not open the scm manager, hr = %08x\n`
- `0x180025193`: `Could not open the iisadmin service,hr = %08x\n`
- `0x180025217`: `Failed querying the iisadmin service for it's process info, hr = %08x, BytesNeeded = %d\n`
- `0x180025376`: `Could not open the inetinfo process, hr = %08x\n`

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
0x1800250ac  push    rbp
0x1800250ae  push    rbx
0x1800250af  push    rsi
0x1800250b0  push    rdi
0x1800250b1  push    r12
0x1800250b3  push    r13
0x1800250b5  push    r14
0x1800250b7  push    r15
0x1800250b9  lea     rbp, [rsp-1Fh]
0x1800250be  sub     rsp, 88h
0x1800250c5  mov     rax, cs:__security_cookie
0x1800250cc  xor     rax, rsp
0x1800250cf  mov     [rbp+57h+var_50], rax
0x1800250d3  xor     eax, eax
0x1800250d5  xorps   xmm0, xmm0
0x1800250d8  mov     [rcx], rax
0x1800250db  mov     r13, rcx
0x1800250de  mov     ebx, 80000000h
0x1800250e3  mov     [rbp+57h+var_58], eax
0x1800250e6  xor     ecx, ecx; lpMachineName
0x1800250e8  mov     [rbp+57h+var_80], eax
0x1800250eb  mov     r8d, ebx; dwDesiredAccess
0x1800250ee  xor     edx, edx; lpDatabaseName
0x1800250f0  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x1800250f4  xor     edi, edi
0x1800250f6  movups  xmmword ptr [rbp+57h+dwProcessId], xmm0
0x1800250fa  call    cs:__imp_OpenSCManagerW
0x180025101  nop     dword ptr [rax+rax+00h]
0x180025106  mov     r12, rax
0x180025109  test    rax, rax
0x18002510c  jnz     short loc_18002514A
0x18002510e  xor     esi, esi
0x180025110  call    cs:__imp_GetLastError
0x180025117  nop     dword ptr [rax+rax+00h]
0x18002511c  mov     ebx, eax
0x18002511e  test    eax, eax
0x180025120  jle     short loc_18002512B
0x180025122  movzx   ebx, ax
0x180025125  or      ebx, 80070000h
0x18002512b  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180025132  jz      loc_1800253A6
0x180025138  lea     rax, aCouldNotOpenTh_0; "Could not open the scm manager, hr = %0"...
0x18002513f  mov     r8d, 2FCh
0x180025145  jmp     loc_180025383
0x18002514a  mov     r8d, ebx; dwDesiredAccess
0x18002514d  lea     rdx, ServiceName; "IISADMIN"
0x180025154  mov     rcx, r12; hSCManager
0x180025157  call    cs:__imp_OpenServiceW
0x18002515e  nop     dword ptr [rax+rax+00h]
0x180025163  mov     rsi, rax
0x180025166  test    rax, rax
0x180025169  jnz     short loc_1800251A5
0x18002516b  call    cs:__imp_GetLastError
0x180025172  nop     dword ptr [rax+rax+00h]
0x180025177  mov     ebx, eax
0x180025179  test    eax, eax
0x18002517b  jle     short loc_180025186
0x18002517d  movzx   ebx, ax
0x180025180  or      ebx, 80070000h
0x180025186  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x18002518d  jz      loc_1800253A6
0x180025193  lea     rax, aCouldNotOpenTh_1; "Could not open the iisadmin service,hr "...
0x18002519a  mov     r8d, 308h
0x1800251a0  jmp     loc_180025383
0x1800251a5  lea     rax, [rbp+57h+var_80]
0x1800251a9  mov     r9d, 24h ; '$'; cbBufSize
0x1800251af  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x1800251b3  mov     [rsp+0C0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800251b8  xor     edx, edx; InfoLevel
0x1800251ba  mov     rcx, rsi; hService
0x1800251bd  call    cs:__imp_QueryServiceStatusEx
0x1800251c4  nop     dword ptr [rax+rax+00h]
0x1800251c9  test    eax, eax
0x1800251cb  jnz     short loc_180025231
0x1800251cd  call    cs:__imp_GetLastError
0x1800251d4  nop     dword ptr [rax+rax+00h]
0x1800251d9  mov     ebx, eax
0x1800251db  test    eax, eax
0x1800251dd  jle     short loc_1800251E8
0x1800251df  movzx   ebx, ax
0x1800251e2  or      ebx, 80070000h
0x1800251e8  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800251ef  jz      loc_1800253A6
0x1800251f5  mov     r8d, 319h; unsigned int
0x1800251fb  mov     eax, [rbp+57h+var_80]
0x1800251fe  lea     r9, aGetprocesshand; "GetProcessHandleForInetinfo"
0x180025205  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002520c  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180025213  mov     [rsp+0C0h+var_90], eax
0x180025217  lea     rax, aFailedQuerying; "Failed querying the iisadmin service fo"...
0x18002521e  mov     dword ptr [rsp+0C0h+var_98], ebx; char
0x180025222  mov     [rsp+0C0h+pcbBytesNeeded], rax; char *
0x180025227  call    PuDbgPrint
0x18002522c  jmp     loc_1800253A6
0x180025231  xor     ebx, ebx
0x180025233  xor     r14d, r14d
0x180025236  mov     r15d, [rbp+57h+dwProcessId+0Ch]
0x18002523a  xor     edx, edx; bInheritHandle
0x18002523c  mov     r8d, r15d; dwProcessId
0x18002523f  mov     ecx, 100000h; dwDesiredAccess
0x180025244  call    cs:__imp_OpenProcess
0x18002524b  nop     dword ptr [rax+rax+00h]
0x180025250  mov     rdi, rax
0x180025253  test    rax, rax
0x180025256  jz      loc_180025352
0x18002525c  lea     rax, [rbp+57h+var_80]
0x180025260  mov     r9d, 24h ; '$'; cbBufSize
0x180025266  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x18002526a  mov     [rsp+0C0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18002526f  xor     edx, edx; InfoLevel
0x180025271  mov     rcx, rsi; hService
0x180025274  call    cs:__imp_QueryServiceStatusEx
0x18002527b  nop     dword ptr [rax+rax+00h]
0x180025280  test    eax, eax
0x180025282  jz      loc_180025323
0x180025288  cmp     r15d, [rbp+57h+dwProcessId+0Ch]
0x18002528c  jz      loc_1800253AA
0x180025292  cmp     r14d, 5
0x180025296  ja      short loc_1800252E4
0x180025298  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x18002529f  jz      short loc_1800252CD
0x1800252a1  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800252a8  lea     rax, aProcessIdForTh; "Process id for the process we got and t"...
0x1800252af  lea     r9, aGetprocesshand; "GetProcessHandleForInetinfo"
0x1800252b6  mov     [rsp+0C0h+pcbBytesNeeded], rax; char *
0x1800252bb  mov     r8d, 364h; unsigned int
0x1800252c1  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800252c8  call    PuDbgPrint
0x1800252cd  mov     rcx, rdi; hObject
0x1800252d0  call    cs:__imp_CloseHandle
0x1800252d7  nop     dword ptr [rax+rax+00h]
0x1800252dc  inc     r14d
0x1800252df  jmp     loc_180025236
0x1800252e4  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800252eb  jz      short loc_180025319
0x1800252ed  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800252f4  lea     rax, aProcessIdForTh_0; "Process id for the process we got and t"...
0x1800252fb  lea     r9, aGetprocesshand; "GetProcessHandleForInetinfo"
0x180025302  mov     [rsp+0C0h+pcbBytesNeeded], rax; char *
0x180025307  mov     r8d, 35Ah; unsigned int
0x18002530d  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180025314  call    PuDbgPrint
0x180025319  mov     ebx, 8000FFFFh
0x18002531e  jmp     loc_1800253B5
0x180025323  call    cs:__imp_GetLastError
0x18002532a  nop     dword ptr [rax+rax+00h]
0x18002532f  mov     ebx, eax
0x180025331  test    eax, eax
0x180025333  jle     short loc_18002533E
0x180025335  movzx   ebx, ax
0x180025338  or      ebx, 80070000h
0x18002533e  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180025345  jz      short loc_1800253A6
0x180025347  mov     r8d, 349h
0x18002534d  jmp     loc_1800251FB
0x180025352  call    cs:__imp_GetLastError
0x180025359  nop     dword ptr [rax+rax+00h]
0x18002535e  mov     ebx, eax
0x180025360  test    eax, eax
0x180025362  jle     short loc_18002536D
0x180025364  movzx   ebx, ax
0x180025367  or      ebx, 80070000h
0x18002536d  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180025374  jz      short loc_1800253A6
0x180025376  lea     rax, aCouldNotOpenTh; "Could not open the inetinfo process, hr"...
0x18002537d  mov     r8d, 335h; unsigned int
0x180025383  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002538a  lea     r9, aGetprocesshand; "GetProcessHandleForInetinfo"
0x180025391  mov     dword ptr [rsp+0C0h+var_98], ebx; char
0x180025395  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002539c  mov     [rsp+0C0h+pcbBytesNeeded], rax; char *
0x1800253a1  call    PuDbgPrint
0x1800253a6  test    ebx, ebx
0x1800253a8  js      short loc_1800253B0
0x1800253aa  mov     [r13+0], rdi
0x1800253ae  jmp     short loc_1800253C4
0x1800253b0  test    rdi, rdi
0x1800253b3  jz      short loc_1800253C4
0x1800253b5  mov     rcx, rdi; hObject
0x1800253b8  call    cs:__imp_CloseHandle
0x1800253bf  nop     dword ptr [rax+rax+00h]
0x1800253c4  test    rsi, rsi
0x1800253c7  jz      short loc_1800253D8
0x1800253c9  mov     rcx, rsi; hSCObject
0x1800253cc  call    cs:__imp_CloseServiceHandle
0x1800253d3  nop     dword ptr [rax+rax+00h]
0x1800253d8  test    r12, r12
0x1800253db  jz      short loc_1800253EC
0x1800253dd  mov     rcx, r12; hSCObject
0x1800253e0  call    cs:__imp_CloseServiceHandle
0x1800253e7  nop     dword ptr [rax+rax+00h]
0x1800253ec  mov     eax, ebx
0x1800253ee  mov     rcx, [rbp+57h+var_50]
0x1800253f2  xor     rcx, rsp; StackCookie
0x1800253f5  call    __security_check_cookie
0x1800253fa  add     rsp, 88h
0x180025401  pop     r15
0x180025403  pop     r14
0x180025405  pop     r13
0x180025407  pop     r12
0x180025409  pop     rdi
0x18002540a  pop     rsi
0x18002540b  pop     rbx
0x18002540c  pop     rbp
0x18002540d  retn
```
