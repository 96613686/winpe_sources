# UL_AND_WORKER_MANAGER::StartW3LogSvc(ulong)

- ea: `0x180012614`
- end: `0x180012790`
- name: `?StartW3LogSvc@UL_AND_WORKER_MANAGER@@QEAAJK@Z`
- size: `380`
- prototype: `__int64 __fastcall(UL_AND_WORKER_MANAGER *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180004ed4`
- `0x180014730`
- `0x180017040`

## callees

- `0x180012614`
- `0x180061060`

## import_xrefs

- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800126db`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800126db`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180012683`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180012683`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800126b4`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800126b4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180012724`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001272d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180012724`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001272d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180012647`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180012647`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012655`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012691`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800126be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001270c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012655`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012691`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800126be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001270c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800126f1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800126f1`
- `iisutil!PuDbgPrintError` at `0x18001276b`
- `iisutil!PuDbgPrintError` at `0x18001276b`

## string_xrefs

- `0x180012764`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`

## pseudocode

```c
__int64 __fastcall UL_AND_WORKER_MANAGER::StartW3LogSvc(UL_AND_WORKER_MANAGER *this)
{
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rsi
  signed int v3; // eax
  signed int v4; // ebx
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rdi
  signed int LastError; // eax
  signed int v8; // eax
  unsigned int v9; // ebx
  _BYTE ServiceStatus[32]; // [rsp+30h] [rbp-38h] BYREF

  memset(ServiceStatus, 0, 28);
  v1 = OpenSCManagerW(0, 0, 0x10u);
  v2 = v1;
  if ( v1 )
  {
    v5 = OpenServiceW(v1, L"w3logsvc", 0x14u);
    v6 = v5;
    if ( !v5 )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_19;
    }
    if ( StartServiceW(v5, 0, 0) )
    {
      v9 = 0;
      while ( QueryServiceStatus(v6, (LPSERVICE_STATUS)ServiceStatus) )
      {
        if ( *(_DWORD *)&ServiceStatus[4] == 4 )
          goto LABEL_9;
        Sleep(0x3E8u);
        v9 += 1000;
        if ( v9 >= 0xEA60 )
        {
          v4 = -2147023843;
          goto LABEL_18;
        }
      }
      v8 = GetLastError();
      v4 = v8;
    }
    else
    {
      v8 = GetLastError();
      v4 = v8;
      if ( v8 == 1056 )
      {
LABEL_9:
        v4 = 0;
LABEL_18:
        CloseServiceHandle(v6);
LABEL_19:
        CloseServiceHandle(v2);
        goto LABEL_20;
      }
    }
    if ( v8 > 0 )
      v4 = (unsigned __int16)v8 | 0x80070000;
    goto LABEL_18;
  }
  v3 = GetLastError();
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
LABEL_20:
  if ( v4 < 0 && (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
      6450,
      "UL_AND_WORKER_MANAGER::StartW3LogSvc",
      v4,
      "Starting w3logsvc failed\n",
      *(_OWORD *)ServiceStatus,
      *(_OWORD *)&ServiceStatus[16]);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180012614  mov     [rsp+arg_0], rbx
0x180012619  mov     [rsp+arg_8], rsi
0x18001261e  push    rdi
0x18001261f  sub     rsp, 60h
0x180012623  mov     rax, cs:__security_cookie
0x18001262a  xor     rax, rsp
0x18001262d  mov     [rsp+68h+var_18], rax
0x180012632  xorps   xmm0, xmm0
0x180012635  xor     edx, edx; lpDatabaseName
0x180012637  movups  xmmword ptr [rsp+68h+ServiceStatus], xmm0
0x18001263c  xor     ecx, ecx; lpMachineName
0x18001263e  movups  xmmword ptr [rsp+68h+ServiceStatus+0Ch], xmm0
0x180012643  lea     r8d, [rdx+10h]; dwDesiredAccess
0x180012647  call    cs:__imp_OpenSCManagerW
0x18001264d  mov     rsi, rax
0x180012650  test    rax, rax
0x180012653  jnz     short loc_180012673
0x180012655  call    cs:__imp_GetLastError
0x18001265b  mov     ebx, eax
0x18001265d  test    eax, eax
0x18001265f  jle     loc_180012733
0x180012665  movzx   ebx, ax
0x180012668  or      ebx, 80070000h
0x18001266e  jmp     loc_180012733
0x180012673  mov     r8d, 14h; dwDesiredAccess
0x180012679  lea     rdx, aW3logsvc; "w3logsvc"
0x180012680  mov     rcx, rsi; hSCManager
0x180012683  call    cs:__imp_OpenServiceW
0x180012689  mov     rdi, rax
0x18001268c  test    rax, rax
0x18001268f  jnz     short loc_1800126AC
0x180012691  call    cs:__imp_GetLastError
0x180012697  mov     ebx, eax
0x180012699  test    eax, eax
0x18001269b  jle     loc_18001272A
0x1800126a1  movzx   ebx, ax
0x1800126a4  or      ebx, 80070000h
0x1800126aa  jmp     short loc_18001272A
0x1800126ac  xor     r8d, r8d; lpServiceArgVectors
0x1800126af  xor     edx, edx; dwNumServiceArgs
0x1800126b1  mov     rcx, rdi; hService
0x1800126b4  call    cs:__imp_StartServiceW
0x1800126ba  test    eax, eax
0x1800126bc  jnz     short loc_1800126D1
0x1800126be  call    cs:__imp_GetLastError
0x1800126c4  mov     ebx, eax
0x1800126c6  cmp     eax, 420h
0x1800126cb  jnz     short loc_180012714
0x1800126cd  xor     ebx, ebx
0x1800126cf  jmp     short loc_180012721
0x1800126d1  xor     ebx, ebx
0x1800126d3  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x1800126d8  mov     rcx, rdi; hService
0x1800126db  call    cs:__imp_QueryServiceStatus
0x1800126e1  test    eax, eax
0x1800126e3  jz      short loc_18001270C
0x1800126e5  cmp     dword ptr [rsp+68h+ServiceStatus+4], 4
0x1800126ea  jz      short loc_1800126CD
0x1800126ec  mov     ecx, 3E8h; dwMilliseconds
0x1800126f1  call    cs:__imp_Sleep
0x1800126f7  add     ebx, 3E8h
0x1800126fd  cmp     ebx, 0EA60h
0x180012703  jb      short loc_1800126D3
0x180012705  mov     ebx, 8007041Dh
0x18001270a  jmp     short loc_180012721
0x18001270c  call    cs:__imp_GetLastError
0x180012712  mov     ebx, eax
0x180012714  test    eax, eax
0x180012716  jle     short loc_180012721
0x180012718  movzx   ebx, ax
0x18001271b  or      ebx, 80070000h
0x180012721  mov     rcx, rdi; hSCObject
0x180012724  call    cs:__imp_CloseServiceHandle
0x18001272a  mov     rcx, rsi; hSCObject
0x18001272d  call    cs:__imp_CloseServiceHandle
0x180012733  test    ebx, ebx
0x180012735  jns     short loc_180012771
0x180012737  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001273e  jz      short loc_180012771
0x180012740  mov     rcx, cs:g_pDebug
0x180012747  lea     rax, aStartingW3logs; "Starting w3logsvc failed\n"
0x18001274e  mov     [rsp+68h+var_40], rax
0x180012753  lea     r9, aUlAndWorkerMan_14; "UL_AND_WORKER_MANAGER::StartW3LogSvc"
0x18001275a  mov     r8d, 1932h
0x180012760  mov     [rsp+68h+var_48], ebx
0x180012764  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001276b  call    cs:__imp_PuDbgPrintError
0x180012771  mov     eax, ebx
0x180012773  mov     rcx, [rsp+68h+var_18]
0x180012778  xor     rcx, rsp; StackCookie
0x18001277b  call    __security_check_cookie
0x180012780  mov     rbx, [rsp+68h+arg_0]
0x180012785  mov     rsi, [rsp+68h+arg_8]
0x18001278a  add     rsp, 60h
0x18001278e  pop     rdi
0x18001278f  retn
```
