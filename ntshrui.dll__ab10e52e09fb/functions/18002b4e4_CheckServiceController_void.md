# CheckServiceController(void)

- ea: `0x18002b4e4`
- end: `0x18002b67f`
- name: `?CheckServiceController@@YAHXZ`
- size: `411`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18002b730`

## callees

- `0x1800254e0`
- `0x18002b4e4`
- `0x18002b688`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002b5a9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002b62f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002b5a9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002b62f`
- `SHELL32!SHChangeNotify` at `0x18002b677`
- `SHELL32!SHChangeNotify` at `0x18002b677`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002b538`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002b538`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002b51c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002b51c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002b549`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002b5f7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002b600`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002b651`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002b65a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002b549`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002b5f7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002b600`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002b651`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002b65a`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002b573`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002b5b6`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002b63c`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002b573`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002b5b6`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002b63c`

## pseudocode

```c
__int64 CheckServiceController(void)
{
  unsigned int v0; // r14d
  SC_HANDLE v1; // rax
  struct SC_HANDLE__ *v2; // rbx
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rdi
  DWORD dwCurrentState; // ecx
  unsigned int i; // esi
  DWORD dwCheckPoint; // eax
  int v9; // esi
  DWORD v10; // r15d
  DWORD v11; // ecx
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-30h] BYREF

  v0 = 1;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v1 = OpenSCManagerW(0, 0, 1u);
  v2 = v1;
  if ( !v1 )
    return 0;
  v3 = OpenServiceW(v1, L"LanmanServer", 4u);
  v4 = v3;
  if ( !v3 )
  {
    CloseServiceHandle(v2);
    return 0;
  }
  if ( !QueryServiceStatus(v3, &ServiceStatus) )
    goto LABEL_18;
  dwCurrentState = ServiceStatus.dwCurrentState;
  if ( ServiceStatus.dwCurrentState == 4 )
  {
LABEL_19:
    CloseServiceHandle(v2);
    CloseServiceHandle(v4);
    return v0;
  }
  if ( ServiceStatus.dwCurrentState != 2 )
  {
    if ( (unsigned int)ServerConfiguredToStart(v2) )
    {
      for ( i = 0; i < 0x15F90; i += 4000 )
      {
        Sleep(0xFA0u);
        if ( !QueryServiceStatus(v4, &ServiceStatus) )
          break;
        dwCurrentState = ServiceStatus.dwCurrentState;
        if ( ((ServiceStatus.dwCurrentState - 2) & 0xFFFFFFFD) == 0 )
          goto LABEL_14;
      }
    }
LABEL_18:
    v0 = 0;
    goto LABEL_19;
  }
LABEL_14:
  dwCheckPoint = ServiceStatus.dwCheckPoint;
  v9 = 0;
  v10 = ServiceStatus.dwCheckPoint;
  while ( dwCurrentState == 2 )
  {
    if ( v10 == dwCheckPoint )
    {
      if ( (unsigned int)++v9 > 0x14 )
        goto LABEL_18;
    }
    else
    {
      v9 = 0;
      v10 = dwCheckPoint;
    }
    v11 = ServiceStatus.dwWaitHint >> 2;
    if ( ServiceStatus.dwWaitHint >> 2 <= 0x3A98 )
    {
      if ( v11 < 0x3E8 )
        v11 = 1000;
    }
    else
    {
      v11 = 15000;
    }
    Sleep(v11);
    if ( !QueryServiceStatus(v4, &ServiceStatus) )
      goto LABEL_18;
    dwCheckPoint = ServiceStatus.dwCheckPoint;
    dwCurrentState = ServiceStatus.dwCurrentState;
  }
  CloseServiceHandle(v2);
  CloseServiceHandle(v4);
  if ( ServiceStatus.dwCurrentState != 4 )
    return 0;
  SHChangeNotify(0x8000000, 0, 0, 0);
  return v0;
}

```

## disassembly

```asm
0x18002b4e4  push    rbp
0x18002b4e6  push    rbx
0x18002b4e7  push    rsi
0x18002b4e8  push    rdi
0x18002b4e9  push    r13
0x18002b4eb  push    r14
0x18002b4ed  push    r15
0x18002b4ef  mov     rbp, rsp
0x18002b4f2  sub     rsp, 50h
0x18002b4f6  mov     rax, cs:__security_cookie
0x18002b4fd  xor     rax, rsp
0x18002b500  mov     [rbp+var_10], rax
0x18002b504  xorps   xmm0, xmm0
0x18002b507  mov     r14d, 1
0x18002b50d  movups  xmmword ptr [rbp+ServiceStatus.dwServiceType], xmm0
0x18002b511  mov     r8d, r14d; dwDesiredAccess
0x18002b514  xor     edx, edx; lpDatabaseName
0x18002b516  xor     ecx, ecx; lpMachineName
0x18002b518  movups  xmmword ptr [rbp+ServiceStatus.dwWin32ExitCode], xmm0
0x18002b51c  call    cs:__imp_OpenSCManagerW
0x18002b522  mov     rbx, rax
0x18002b525  test    rax, rax
0x18002b528  jz      short loc_18002B54F
0x18002b52a  lea     r8d, [r14+3]; dwDesiredAccess
0x18002b52e  mov     rcx, rax; hSCManager
0x18002b531  lea     rdx, ServiceName; "LanmanServer"
0x18002b538  call    cs:__imp_OpenServiceW
0x18002b53e  mov     rdi, rax
0x18002b541  test    rax, rax
0x18002b544  jnz     short loc_18002B56C
0x18002b546  mov     rcx, rbx; hSCObject
0x18002b549  call    cs:__imp_CloseServiceHandle
0x18002b54f  xor     eax, eax
0x18002b551  mov     rcx, [rbp+var_10]
0x18002b555  xor     rcx, rsp; StackCookie
0x18002b558  call    __security_check_cookie
0x18002b55d  add     rsp, 50h
0x18002b561  pop     r15
0x18002b563  pop     r14
0x18002b565  pop     r13
0x18002b567  pop     rdi
0x18002b568  pop     rsi
0x18002b569  pop     rbx
0x18002b56a  pop     rbp
0x18002b56b  retn
0x18002b56c  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x18002b570  mov     rcx, rdi; hService
0x18002b573  call    cs:__imp_QueryServiceStatus
0x18002b579  test    eax, eax
0x18002b57b  jz      short loc_18002B5F1
0x18002b57d  mov     ecx, [rbp+ServiceStatus.dwCurrentState]
0x18002b580  cmp     ecx, 4
0x18002b583  jz      short loc_18002B5F4
0x18002b585  cmp     ecx, 2
0x18002b588  jz      short loc_18002B5D2
0x18002b58a  mov     rcx, rbx; struct SC_HANDLE__ *
0x18002b58d  call    ?ServerConfiguredToStart@@YAHPEAUSC_HANDLE__@@@Z; ServerConfiguredToStart(SC_HANDLE__ *)
0x18002b592  test    eax, eax
0x18002b594  jz      short loc_18002B5F1
0x18002b596  xor     esi, esi
0x18002b598  mov     r15d, 0FA0h
0x18002b59e  cmp     esi, 15F90h
0x18002b5a4  jnb     short loc_18002B5F1
0x18002b5a6  mov     ecx, r15d; dwMilliseconds
0x18002b5a9  call    cs:__imp_Sleep
0x18002b5af  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x18002b5b3  mov     rcx, rdi; hService
0x18002b5b6  call    cs:__imp_QueryServiceStatus
0x18002b5bc  test    eax, eax
0x18002b5be  jz      short loc_18002B5F1
0x18002b5c0  mov     ecx, [rbp+ServiceStatus.dwCurrentState]
0x18002b5c3  lea     eax, [rcx-2]
0x18002b5c6  test    eax, 0FFFFFFFDh
0x18002b5cb  jz      short loc_18002B5D2
0x18002b5cd  add     esi, r15d
0x18002b5d0  jmp     short loc_18002B59E
0x18002b5d2  mov     eax, [rbp+ServiceStatus.dwCheckPoint]
0x18002b5d5  xor     esi, esi
0x18002b5d7  mov     r15d, eax
0x18002b5da  mov     r13d, 3E8h
0x18002b5e0  cmp     ecx, 2
0x18002b5e3  jnz     short loc_18002B64E
0x18002b5e5  cmp     r15d, eax
0x18002b5e8  jnz     short loc_18002B60E
0x18002b5ea  inc     esi
0x18002b5ec  cmp     esi, 14h
0x18002b5ef  jbe     short loc_18002B613
0x18002b5f1  xor     r14d, r14d
0x18002b5f4  mov     rcx, rbx; hSCObject
0x18002b5f7  call    cs:__imp_CloseServiceHandle
0x18002b5fd  mov     rcx, rdi; hSCObject
0x18002b600  call    cs:__imp_CloseServiceHandle
0x18002b606  mov     eax, r14d
0x18002b609  jmp     loc_18002B551
0x18002b60e  xor     esi, esi
0x18002b610  mov     r15d, eax
0x18002b613  mov     ecx, [rbp+ServiceStatus.dwWaitHint]
0x18002b616  shr     ecx, 2
0x18002b619  cmp     ecx, 3A98h
0x18002b61f  jbe     short loc_18002B628
0x18002b621  mov     ecx, 3A98h
0x18002b626  jmp     short loc_18002B62F
0x18002b628  cmp     ecx, r13d
0x18002b62b  cmovb   ecx, r13d; dwMilliseconds
0x18002b62f  call    cs:__imp_Sleep
0x18002b635  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x18002b639  mov     rcx, rdi; hService
0x18002b63c  call    cs:__imp_QueryServiceStatus
0x18002b642  test    eax, eax
0x18002b644  jz      short loc_18002B5F1
0x18002b646  mov     eax, [rbp+ServiceStatus.dwCheckPoint]
0x18002b649  mov     ecx, [rbp+ServiceStatus.dwCurrentState]
0x18002b64c  jmp     short loc_18002B5E0
0x18002b64e  mov     rcx, rbx; hSCObject
0x18002b651  call    cs:__imp_CloseServiceHandle
0x18002b657  mov     rcx, rdi; hSCObject
0x18002b65a  call    cs:__imp_CloseServiceHandle
0x18002b660  cmp     [rbp+ServiceStatus.dwCurrentState], 4
0x18002b664  jnz     loc_18002B54F
0x18002b66a  xor     r9d, r9d; dwItem2
0x18002b66d  xor     r8d, r8d; dwItem1
0x18002b670  xor     edx, edx; uFlags
0x18002b672  mov     ecx, 8000000h; wEventId
0x18002b677  call    cs:__imp_SHChangeNotify
0x18002b67d  jmp     short loc_18002B606
```
