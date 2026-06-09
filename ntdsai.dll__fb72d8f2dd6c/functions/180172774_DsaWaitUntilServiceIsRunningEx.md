# DsaWaitUntilServiceIsRunningEx

- ea: `0x180172774`
- end: `0x180172a02`
- name: `DsaWaitUntilServiceIsRunningEx`
- size: `654`
- prototype: `__int64 __fastcall(LPCSTR lpServiceName)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800341d4`
- `0x180086740`
- `0x18008d610`
- `0x1800a94a0`
- `0x1800b4a90`

## callees

- `0x18001e090`
- `0x18001ea60`
- `0x180172774`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801729c4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180461e76`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801729c4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180461e76`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18017286a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18017286a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801729cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801729cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180172855`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180172998`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180172855`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180172998`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x18017281c`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x18017281c`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x1801727f9`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x1801727f9`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180172924`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180172924`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1801728c8`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1801728c8`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceConfigA` at `0x180172844`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceConfigA` at `0x180172895`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceConfigA` at `0x180172844`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceConfigA` at `0x180172895`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1801729a8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1801729b6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180461e56`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180461e66`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1801729a8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1801729b6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180461e56`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180461e66`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180172974`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180172974`

## pseudocode

```c
char __fastcall DsaWaitUntilServiceIsRunningEx(LPCSTR lpServiceName, __int64 a2, int a3)
{
  char v4; // di
  char v5; // r13
  SC_HANDLE v6; // r14
  unsigned int v7; // r12d
  _QUERY_SERVICE_CONFIGA *v8; // rsi
  SC_HANDLE v9; // rax
  SC_HANDLE v10; // r15
  SC_HANDLE v11; // rax
  _QUERY_SERVICE_CONFIGA *p_ServiceConfig; // rcx
  DWORD LastError; // ebx
  struct _QUERY_SERVICE_CONFIGA *v14; // rax
  int v15; // ecx
  char v17; // [rsp+21h] [rbp-C7h]
  DWORD pcbBytesNeeded; // [rsp+24h] [rbp-C4h] BYREF
  int v19; // [rsp+28h] [rbp-C0h]
  SC_HANDLE v20; // [rsp+30h] [rbp-B8h]
  SC_HANDLE v21; // [rsp+38h] [rbp-B0h]
  struct _QUERY_SERVICE_CONFIGA *v22; // [rsp+40h] [rbp-A8h]
  unsigned int v23; // [rsp+48h] [rbp-A0h]
  _QUERY_SERVICE_CONFIGA ServiceConfig; // [rsp+50h] [rbp-98h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+90h] [rbp-58h] BYREF

  v19 = a3;
  v4 = 0;
  v17 = 0;
  v5 = 0;
  v6 = 0;
  v21 = 0;
  v7 = 1;
  v8 = 0;
  v22 = 0;
  pcbBytesNeeded = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  memset_0(&ServiceConfig, 0, sizeof(ServiceConfig));
  v9 = OpenSCManagerA(0, 0, 1u);
  v10 = v9;
  v20 = v9;
  if ( !v9 || (v11 = OpenServiceA(v9, lpServiceName, 0x85u), v6 = v11, (v21 = v11) == 0) )
  {
LABEL_36:
    LastError = GetLastError();
    goto LABEL_37;
  }
  if ( QueryServiceConfigA(v11, &ServiceConfig, 0x40u, &pcbBytesNeeded) )
  {
    p_ServiceConfig = &ServiceConfig;
    goto LABEL_10;
  }
  LastError = GetLastError();
  if ( LastError == 122 )
  {
    v14 = (struct _QUERY_SERVICE_CONFIGA *)malloc(pcbBytesNeeded);
    v8 = v14;
    v22 = v14;
    if ( !v14 )
    {
      LastError = 8;
      goto LABEL_37;
    }
    if ( QueryServiceConfigA(v6, v14, pcbBytesNeeded, &pcbBytesNeeded) )
    {
      p_ServiceConfig = v8;
LABEL_10:
      v15 = p_ServiceConfig->dwStartType - 2;
      if ( v15 )
      {
        if ( v15 == 1 )
          v5 = 1;
      }
      else
      {
        v17 = 1;
      }
      while ( 1 )
      {
        if ( !QueryServiceStatus(v6, &ServiceStatus) )
          goto LABEL_36;
        if ( ServiceStatus.dwCurrentState == 1 )
        {
          LastError = ServiceStatus.dwWin32ExitCode;
          if ( ServiceStatus.dwWin32ExitCode != 1077 )
          {
            if ( ServiceStatus.dwWin32ExitCode == 1066 )
              LastError = ServiceStatus.dwServiceSpecificExitCode;
            if ( !LastError )
            {
LABEL_35:
              LastError = 1062;
              goto LABEL_37;
            }
            goto LABEL_37;
          }
          if ( !v17 && !v5 )
            goto LABEL_35;
        }
        else
        {
          if ( ServiceStatus.dwCurrentState != 2 )
          {
            if ( ServiceStatus.dwCurrentState != 4
              && (ServiceStatus.dwCurrentState != 5 && ServiceStatus.dwCurrentState - 6 > 1 || !v19) )
            {
              goto LABEL_35;
            }
LABEL_21:
            v4 = 1;
            goto LABEL_28;
          }
          if ( ControlService(v6, 4u, &ServiceStatus) && ServiceStatus.dwCurrentState == 4 )
            goto LABEL_21;
        }
LABEL_28:
        LastError = 0;
        if ( v4 )
          goto LABEL_37;
        if ( v5 && v7 > 0x12 )
          goto LABEL_35;
        v23 = ++v7;
        Sleep(0x2710u);
      }
    }
    goto LABEL_36;
  }
LABEL_37:
  if ( v10 )
    CloseServiceHandle(v10);
  if ( v6 )
    CloseServiceHandle(v6);
  if ( v8 )
    free(v8);
  SetLastError(LastError);
  return v4;
}

```

## disassembly

```asm
0x180172774  mov     r11, rsp
0x180172777  mov     [r11+10h], rbx
0x18017277b  mov     [r11+18h], rsi
0x18017277f  push    rdi
0x180172780  push    r12
0x180172782  push    r13
0x180172784  push    r14
0x180172786  push    r15
0x180172788  sub     rsp, 0C0h
0x18017278f  mov     rax, cs:__security_cookie
0x180172796  xor     rax, rsp
0x180172799  mov     [rsp+0E8h+var_38], rax
0x1801727a1  mov     [rsp+0E8h+var_C0], r8d
0x1801727a6  mov     rbx, rcx
0x1801727a9  xor     eax, eax
0x1801727ab  mov     dil, al
0x1801727ae  mov     [rsp+0E8h+var_C7], al
0x1801727b2  mov     r13b, al
0x1801727b5  mov     [rsp+0E8h+var_B8], rax
0x1801727ba  mov     r14d, eax
0x1801727bd  mov     [rsp+0E8h+var_B0], rax
0x1801727c2  lea     r15d, [rax+1]
0x1801727c6  mov     r12d, r15d
0x1801727c9  mov     esi, eax
0x1801727cb  mov     [rsp+0E8h+var_A8], rax
0x1801727d0  mov     [rsp+0E8h+pcbBytesNeeded], eax
0x1801727d4  xorps   xmm0, xmm0
0x1801727d7  movups  xmmword ptr [r11-58h], xmm0
0x1801727dc  movups  xmmword ptr [r11-4Ch], xmm0
0x1801727e1  xor     edx, edx; Val
0x1801727e3  lea     r8d, [rax+40h]; Size
0x1801727e7  lea     rcx, [rsp+0E8h+ServiceConfig]; void *
0x1801727ec  call    memset_0
0x1801727f1  nop
0x1801727f2  mov     r8d, r15d; dwDesiredAccess
0x1801727f5  xor     edx, edx; lpDatabaseName
0x1801727f7  xor     ecx, ecx; lpMachineName
0x1801727f9  call    cs:__imp_OpenSCManagerA
0x1801727ff  mov     r15, rax
0x180172802  mov     [rsp+0E8h+var_B8], rax
0x180172807  test    rax, rax
0x18017280a  jz      loc_180172998
0x180172810  mov     r8d, 85h; dwDesiredAccess
0x180172816  mov     rdx, rbx; lpServiceName
0x180172819  mov     rcx, rax; hSCManager
0x18017281c  call    cs:__imp_OpenServiceA
0x180172822  mov     r14, rax
0x180172825  mov     [rsp+0E8h+var_B0], rax
0x18017282a  test    rax, rax
0x18017282d  jz      loc_180172998
0x180172833  lea     r9, [rsp+0E8h+pcbBytesNeeded]; pcbBytesNeeded
0x180172838  lea     r8d, [rsi+40h]; cbBufSize
0x18017283c  lea     rdx, [rsp+0E8h+ServiceConfig]; lpServiceConfig
0x180172841  mov     rcx, rax; hService
0x180172844  call    cs:__imp_QueryServiceConfigA
0x18017284a  test    eax, eax
0x18017284c  jz      short loc_180172855
0x18017284e  lea     rcx, [rsp+0E8h+ServiceConfig]
0x180172853  jmp     short loc_1801728A6
0x180172855  call    cs:__imp_GetLastError
0x18017285b  mov     ebx, eax
0x18017285d  cmp     eax, 7Ah ; 'z'
0x180172860  jnz     loc_1801729A0
0x180172866  mov     ecx, [rsp+0E8h+pcbBytesNeeded]; Size
0x18017286a  call    cs:__imp_malloc
0x180172870  mov     rsi, rax
0x180172873  mov     [rsp+0E8h+var_A8], rax
0x180172878  test    rax, rax
0x18017287b  jnz     short loc_180172885
0x18017287d  lea     ebx, [rax+8]
0x180172880  jmp     loc_1801729A0
0x180172885  lea     r9, [rsp+0E8h+pcbBytesNeeded]; pcbBytesNeeded
0x18017288a  mov     r8d, [rsp+0E8h+pcbBytesNeeded]; cbBufSize
0x18017288f  mov     rdx, rsi; lpServiceConfig
0x180172892  mov     rcx, r14; hService
0x180172895  call    cs:__imp_QueryServiceConfigA
0x18017289b  test    eax, eax
0x18017289d  jz      loc_180172998
0x1801728a3  mov     rcx, rsi
0x1801728a6  mov     ecx, [rcx+4]
0x1801728a9  sub     ecx, 2
0x1801728ac  jz      short loc_1801728B8
0x1801728ae  cmp     ecx, 1
0x1801728b1  jnz     short loc_1801728BD
0x1801728b3  mov     r13b, cl
0x1801728b6  jmp     short loc_1801728BD
0x1801728b8  mov     [rsp+0E8h+var_C7], 1
0x1801728bd  lea     rdx, [rsp+0E8h+ServiceStatus]; lpServiceStatus
0x1801728c5  mov     rcx, r14; hService
0x1801728c8  call    cs:__imp_QueryServiceStatus
0x1801728ce  test    eax, eax
0x1801728d0  jz      loc_180172998
0x1801728d6  mov     eax, [rsp+0E8h+ServiceStatus.dwCurrentState]
0x1801728dd  sub     eax, 1
0x1801728e0  jz      short loc_18017293A
0x1801728e2  sub     eax, 1
0x1801728e5  jz      short loc_180172914
0x1801728e7  sub     eax, 2
0x1801728ea  jz      short loc_18017290A
0x1801728ec  sub     eax, 1
0x1801728ef  jz      short loc_1801728FF
0x1801728f1  sub     eax, 1
0x1801728f4  jz      short loc_1801728FF
0x1801728f6  sub     eax, 1
0x1801728f9  jnz     loc_180172991
0x1801728ff  cmp     [rsp+0E8h+var_C0], 0
0x180172904  jz      loc_180172991
0x18017290a  mov     dil, 1
0x18017290d  mov     [rsp+0E8h+var_C8], dil
0x180172912  jmp     short loc_180172955
0x180172914  lea     r8, [rsp+0E8h+ServiceStatus]; lpServiceStatus
0x18017291c  mov     edx, 4; dwControl
0x180172921  mov     rcx, r14; hService
0x180172924  call    cs:__imp_ControlService
0x18017292a  test    eax, eax
0x18017292c  jz      short loc_180172955
0x18017292e  cmp     [rsp+0E8h+ServiceStatus.dwCurrentState], 4
0x180172936  jnz     short loc_180172955
0x180172938  jmp     short loc_18017290A
0x18017293a  mov     ebx, [rsp+0E8h+ServiceStatus.dwWin32ExitCode]
0x180172941  cmp     ebx, 435h
0x180172947  jnz     short loc_18017297F
0x180172949  cmp     [rsp+0E8h+var_C7], 0
0x18017294e  jnz     short loc_180172955
0x180172950  test    r13b, r13b
0x180172953  jz      short loc_180172991
0x180172955  xor     ebx, ebx
0x180172957  test    dil, dil
0x18017295a  jnz     short loc_1801729A0
0x18017295c  test    r13b, r13b
0x18017295f  jz      short loc_180172967
0x180172961  cmp     r12d, 12h
0x180172965  ja      short loc_180172991
0x180172967  inc     r12d
0x18017296a  mov     [rsp+0E8h+var_A0], r12d
0x18017296f  mov     ecx, 2710h; dwMilliseconds
0x180172974  call    cs:__imp_Sleep
0x18017297a  jmp     loc_1801728BD
0x18017297f  cmp     ebx, 42Ah
0x180172985  cmovz   ebx, [rsp+0E8h+ServiceStatus.dwServiceSpecificExitCode]
0x18017298d  test    ebx, ebx
0x18017298f  jnz     short loc_1801729A0
0x180172991  mov     ebx, 426h
0x180172996  jmp     short loc_1801729A0
0x180172998  call    cs:__imp_GetLastError
0x18017299e  mov     ebx, eax
0x1801729a0  test    r15, r15
0x1801729a3  jz      short loc_1801729AE
0x1801729a5  mov     rcx, r15; hSCObject
0x1801729a8  call    cs:__imp_CloseServiceHandle
0x1801729ae  test    r14, r14
0x1801729b1  jz      short loc_1801729BC
0x1801729b3  mov     rcx, r14; hSCObject
0x1801729b6  call    cs:__imp_CloseServiceHandle
0x1801729bc  test    rsi, rsi
0x1801729bf  jz      short loc_1801729CA
0x1801729c1  mov     rcx, rsi; Block
0x1801729c4  call    cs:__imp_free
0x1801729ca  mov     ecx, ebx; dwErrCode
0x1801729cc  call    cs:__imp_SetLastError
0x1801729d2  mov     al, dil
0x1801729d5  mov     rcx, [rsp+0E8h+var_38]
0x1801729dd  xor     rcx, rsp; StackCookie
0x1801729e0  call    __security_check_cookie
0x1801729e5  lea     r11, [rsp+0E8h+var_28]
0x1801729ed  mov     rbx, [r11+38h]
0x1801729f1  mov     rsi, [r11+40h]
0x1801729f5  mov     rsp, r11
0x1801729f8  pop     r15
0x1801729fa  pop     r14
0x1801729fc  pop     r13
0x1801729fe  pop     r12
0x180172a00  pop     rdi
0x180172a01  retn
0x180461e44  push    rbp
0x180461e46  sub     rsp, 20h
0x180461e4a  mov     rbp, rdx
0x180461e4d  mov     rcx, [rbp+30h]; hSCObject
0x180461e51  test    rcx, rcx
0x180461e54  jz      short loc_180461E5D
0x180461e56  call    cs:__imp_CloseServiceHandle
0x180461e5c  nop
0x180461e5d  mov     rcx, [rbp+38h]; hSCObject
0x180461e61  test    rcx, rcx
0x180461e64  jz      short loc_180461E6D
0x180461e66  call    cs:__imp_CloseServiceHandle
0x180461e6c  nop
0x180461e6d  mov     rcx, [rbp+40h]; Block
0x180461e71  test    rcx, rcx
0x180461e74  jz      short loc_180461E7D
0x180461e76  call    cs:__imp_free
0x180461e7c  nop
0x180461e7d  add     rsp, 20h
0x180461e81  pop     rbp
0x180461e82  retn
```
