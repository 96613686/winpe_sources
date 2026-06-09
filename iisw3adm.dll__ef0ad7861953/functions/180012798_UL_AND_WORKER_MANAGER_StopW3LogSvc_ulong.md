# UL_AND_WORKER_MANAGER::StopW3LogSvc(ulong)

- ea: `0x180012798`
- end: `0x180012941`
- name: `?StopW3LogSvc@UL_AND_WORKER_MANAGER@@QEAAJK@Z`
- size: `425`
- prototype: `__int64 __fastcall(UL_AND_WORKER_MANAGER *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180004cf0`
- `0x180012ac4`

## callees

- `0x180004290`
- `0x180012798`
- `0x180061060`

## import_xrefs

- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18001285d`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800128ae`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18001285d`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800128ae`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180012896`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180012896`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180012829`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180012829`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800128dc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800128e5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800128dc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800128e5`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800127ed`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800127ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800127fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012867`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800127fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012867`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800128c4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800128c4`
- `iisutil!PuDbgPrintError` at `0x180012923`
- `iisutil!PuDbgPrintError` at `0x180012923`

## string_xrefs

- `0x18001291c`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`

## pseudocode

```c
__int64 __fastcall UL_AND_WORKER_MANAGER::StopW3LogSvc(struct _TP_TIMER **this, unsigned int a2)
{
  unsigned int v4; // ebx
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rbp
  signed int LastError; // eax
  SC_HANDLE v8; // rax
  SC_HANDLE v9; // rdi
  signed int v10; // eax
  signed int v11; // eax
  _BYTE ServiceStatus[32]; // [rsp+30h] [rbp-58h] BYREF

  memset(ServiceStatus, 0, 28);
  if ( this[61] )
    WEB_ADMIN_SERVICE::CancelTimer((WEB_ADMIN_SERVICE *)this, this + 61);
  if ( *((_DWORD *)this + 104) )
    return 0;
  v5 = OpenSCManagerW(0, 0, 0x20u);
  v6 = v5;
  if ( !v5 )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_24;
  }
  v8 = OpenServiceW(v5, L"w3logsvc", 0x24u);
  v9 = v8;
  if ( !v8 )
  {
    v10 = GetLastError();
    v4 = v10;
    if ( v10 > 0 )
      v4 = (unsigned __int16)v10 | 0x80070000;
    goto LABEL_23;
  }
  if ( !QueryServiceStatus(v8, (LPSERVICE_STATUS)ServiceStatus) )
    goto LABEL_12;
  if ( *(_DWORD *)&ServiceStatus[4] != 1 )
  {
    if ( ControlService(v9, 1u, (LPSERVICE_STATUS)ServiceStatus) )
    {
      v4 = 0;
      if ( !a2 )
        goto LABEL_22;
      while ( QueryServiceStatus(v9, (LPSERVICE_STATUS)ServiceStatus) )
      {
        if ( *(_DWORD *)&ServiceStatus[4] == 1 )
          goto LABEL_15;
        Sleep(0x3E8u);
        v4 += 1000;
        if ( v4 >= a2 )
        {
          v4 = -2147023843;
          goto LABEL_22;
        }
      }
    }
LABEL_12:
    v11 = GetLastError();
    v4 = v11;
    if ( v11 > 0 )
      v4 = (unsigned __int16)v11 | 0x80070000;
    goto LABEL_22;
  }
LABEL_15:
  v4 = 0;
LABEL_22:
  CloseServiceHandle(v9);
LABEL_23:
  CloseServiceHandle(v6);
LABEL_24:
  if ( (v4 & 0x80000000) != 0 && (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
      6591,
      "UL_AND_WORKER_MANAGER::StopW3LogSvc",
      v4,
      "Stopping w3logsvc failed\n",
      *(_OWORD *)ServiceStatus,
      *(_OWORD *)&ServiceStatus[16]);
  return v4;
}

```

## disassembly

```asm
0x180012798  push    rbx
0x18001279a  push    rbp
0x18001279b  push    rsi
0x18001279c  push    rdi
0x18001279d  sub     rsp, 68h
0x1800127a1  mov     rax, cs:__security_cookie
0x1800127a8  xor     rax, rsp
0x1800127ab  mov     [rsp+88h+var_38], rax
0x1800127b0  xorps   xmm0, xmm0
0x1800127b3  mov     esi, edx
0x1800127b5  lea     rdx, [rcx+1E8h]; struct _TP_TIMER **
0x1800127bc  xor     eax, eax
0x1800127be  mov     rbx, rcx
0x1800127c1  movups  xmmword ptr [rsp+88h+ServiceStatus], xmm0
0x1800127c6  movups  xmmword ptr [rsp+88h+ServiceStatus+0Ch], xmm0
0x1800127cb  cmp     [rdx], rax
0x1800127ce  jz      short loc_1800127D5
0x1800127d0  call    ?CancelTimer@WEB_ADMIN_SERVICE@@QEAAJPEAPEAU_TP_TIMER@@@Z; WEB_ADMIN_SERVICE::CancelTimer(_TP_TIMER * *)
0x1800127d5  cmp     dword ptr [rbx+1A0h], 0
0x1800127dc  jbe     short loc_1800127E5
0x1800127de  xor     ebx, ebx
0x1800127e0  jmp     loc_180012929
0x1800127e5  xor     edx, edx; lpDatabaseName
0x1800127e7  xor     ecx, ecx; lpMachineName
0x1800127e9  lea     r8d, [rdx+20h]; dwDesiredAccess
0x1800127ed  call    cs:__imp_OpenSCManagerW
0x1800127f3  mov     rbp, rax
0x1800127f6  test    rax, rax
0x1800127f9  jnz     short loc_180012819
0x1800127fb  call    cs:__imp_GetLastError
0x180012801  mov     ebx, eax
0x180012803  test    eax, eax
0x180012805  jle     loc_1800128EB
0x18001280b  movzx   ebx, ax
0x18001280e  or      ebx, 80070000h
0x180012814  jmp     loc_1800128EB
0x180012819  mov     r8d, 24h ; '$'; dwDesiredAccess
0x18001281f  lea     rdx, aW3logsvc; "w3logsvc"
0x180012826  mov     rcx, rbp; hSCManager
0x180012829  call    cs:__imp_OpenServiceW
0x18001282f  mov     rdi, rax
0x180012832  test    rax, rax
0x180012835  jnz     short loc_180012855
0x180012837  call    cs:__imp_GetLastError
0x18001283d  mov     ebx, eax
0x18001283f  test    eax, eax
0x180012841  jle     loc_1800128E2
0x180012847  movzx   ebx, ax
0x18001284a  or      ebx, 80070000h
0x180012850  jmp     loc_1800128E2
0x180012855  lea     rdx, [rsp+88h+ServiceStatus]; lpServiceStatus
0x18001285a  mov     rcx, rdi; hService
0x18001285d  call    cs:__imp_QueryServiceStatus
0x180012863  test    eax, eax
0x180012865  jnz     short loc_18001287E
0x180012867  call    cs:__imp_GetLastError
0x18001286d  mov     ebx, eax
0x18001286f  test    eax, eax
0x180012871  jle     short loc_1800128D9
0x180012873  movzx   ebx, ax
0x180012876  or      ebx, 80070000h
0x18001287c  jmp     short loc_1800128D9
0x18001287e  cmp     dword ptr [rsp+88h+ServiceStatus+4], 1
0x180012883  jnz     short loc_180012889
0x180012885  xor     ebx, ebx
0x180012887  jmp     short loc_1800128D9
0x180012889  lea     r8, [rsp+88h+ServiceStatus]; lpServiceStatus
0x18001288e  mov     edx, 1; dwControl
0x180012893  mov     rcx, rdi; hService
0x180012896  call    cs:__imp_ControlService
0x18001289c  test    eax, eax
0x18001289e  jz      short loc_180012867
0x1800128a0  xor     ebx, ebx
0x1800128a2  test    esi, esi
0x1800128a4  jz      short loc_1800128D9
0x1800128a6  lea     rdx, [rsp+88h+ServiceStatus]; lpServiceStatus
0x1800128ab  mov     rcx, rdi; hService
0x1800128ae  call    cs:__imp_QueryServiceStatus
0x1800128b4  test    eax, eax
0x1800128b6  jz      short loc_180012867
0x1800128b8  cmp     dword ptr [rsp+88h+ServiceStatus+4], 1
0x1800128bd  jz      short loc_180012885
0x1800128bf  mov     ecx, 3E8h; dwMilliseconds
0x1800128c4  call    cs:__imp_Sleep
0x1800128ca  add     ebx, 3E8h
0x1800128d0  cmp     ebx, esi
0x1800128d2  jb      short loc_1800128A6
0x1800128d4  mov     ebx, 8007041Dh
0x1800128d9  mov     rcx, rdi; hSCObject
0x1800128dc  call    cs:__imp_CloseServiceHandle
0x1800128e2  mov     rcx, rbp; hSCObject
0x1800128e5  call    cs:__imp_CloseServiceHandle
0x1800128eb  test    ebx, ebx
0x1800128ed  jns     short loc_180012929
0x1800128ef  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800128f6  jz      short loc_180012929
0x1800128f8  mov     rcx, cs:g_pDebug
0x1800128ff  lea     rax, aStoppingW3logs; "Stopping w3logsvc failed\n"
0x180012906  mov     [rsp+88h+var_60], rax
0x18001290b  lea     r9, aUlAndWorkerMan_6; "UL_AND_WORKER_MANAGER::StopW3LogSvc"
0x180012912  mov     r8d, 19BFh
0x180012918  mov     [rsp+88h+var_68], ebx
0x18001291c  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180012923  call    cs:__imp_PuDbgPrintError
0x180012929  mov     eax, ebx
0x18001292b  mov     rcx, [rsp+88h+var_38]
0x180012930  xor     rcx, rsp; StackCookie
0x180012933  call    __security_check_cookie
0x180012938  add     rsp, 68h
0x18001293c  pop     rdi
0x18001293d  pop     rsi
0x18001293e  pop     rbp
0x18001293f  pop     rbx
0x180012940  retn
```
