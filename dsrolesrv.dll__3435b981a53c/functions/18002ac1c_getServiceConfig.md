# getServiceConfig

- ea: `0x18002ac1c`
- end: `0x18002ad3a`
- name: `getServiceConfig`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18002a9c0`

## callees

- `0x18002ac1c`
- `0x18002b79c`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002acb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002acf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002acb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002acf4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002ad0e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002ad0e`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceConfigA` at `0x18002acab`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceConfigA` at `0x18002acea`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceConfigA` at `0x18002acab`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceConfigA` at `0x18002acea`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x18002ac70`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x18002ac70`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002ac86`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002ac86`

## pseudocode

```c
__int64 __fastcall getServiceConfig(
        SC_HANDLE a1,
        const CHAR *a2,
        SC_HANDLE *a3,
        struct _QUERY_SERVICE_CONFIGA **a4,
        DWORD *a5)
{
  DWORD dwCurrentState; // r12d
  SC_HANDLE v8; // rax
  SC_HANDLE v9; // rdi
  DWORD LastError; // ebx
  DWORD v11; // ebp
  struct _QUERY_SERVICE_CONFIGA *v12; // rax
  DWORD pcbBytesNeeded; // [rsp+20h] [rbp-68h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+28h] [rbp-60h] BYREF

  dwCurrentState = 0;
  pcbBytesNeeded = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( a4 )
    *a4 = 0;
  v8 = OpenServiceA(a1, a2, 0xC0000000);
  v9 = v8;
  if ( !v8 || !QueryServiceStatus(v8, &ServiceStatus) )
    goto LABEL_12;
  dwCurrentState = ServiceStatus.dwCurrentState;
  LastError = 0;
  if ( !a4 )
    goto LABEL_13;
  v11 = 0;
  if ( !QueryServiceConfigA(v9, 0, 0, &pcbBytesNeeded) )
  {
    LastError = GetLastError();
    if ( LastError != 122 )
      goto LABEL_13;
    v11 = pcbBytesNeeded;
  }
  v12 = (struct _QUERY_SERVICE_CONFIGA *)Dns_AllocZero(v11);
  *a4 = v12;
  if ( !v12 )
  {
    LastError = 14;
    goto LABEL_13;
  }
  LastError = 0;
  if ( !QueryServiceConfigA(v9, v12, v11, &pcbBytesNeeded) )
LABEL_12:
    LastError = GetLastError();
LABEL_13:
  if ( a3 )
  {
    *a3 = v9;
  }
  else if ( v9 )
  {
    CloseServiceHandle(v9);
  }
  if ( a5 )
    *a5 = dwCurrentState;
  return LastError;
}

```

## disassembly

```asm
0x18002ac1c  push    rbx
0x18002ac1e  push    rbp
0x18002ac1f  push    rsi
0x18002ac20  push    rdi
0x18002ac21  push    r12
0x18002ac23  push    r14
0x18002ac25  push    r15
0x18002ac27  sub     rsp, 50h
0x18002ac2b  mov     rax, cs:__security_cookie
0x18002ac32  xor     rax, rsp
0x18002ac35  mov     [rsp+88h+var_40], rax
0x18002ac3a  mov     r14, [rsp+88h+arg_20]
0x18002ac42  xorps   xmm0, xmm0
0x18002ac45  xor     r12d, r12d
0x18002ac48  mov     [rsp+88h+pcbBytesNeeded], 0
0x18002ac50  xor     eax, eax
0x18002ac52  mov     rsi, r9
0x18002ac55  mov     r15, r8
0x18002ac58  movups  xmmword ptr [rsp+88h+ServiceStatus.dwServiceType], xmm0
0x18002ac5d  movups  xmmword ptr [rsp+88h+ServiceStatus.dwWin32ExitCode], xmm0
0x18002ac62  test    r9, r9
0x18002ac65  jz      short loc_18002AC6A
0x18002ac67  mov     [r9], rax
0x18002ac6a  mov     r8d, 0C0000000h; dwDesiredAccess
0x18002ac70  call    cs:__imp_OpenServiceA
0x18002ac76  mov     rdi, rax
0x18002ac79  test    rax, rax
0x18002ac7c  jz      short loc_18002ACF4
0x18002ac7e  lea     rdx, [rsp+88h+ServiceStatus]; lpServiceStatus
0x18002ac83  mov     rcx, rax; hService
0x18002ac86  call    cs:__imp_QueryServiceStatus
0x18002ac8c  test    eax, eax
0x18002ac8e  jz      short loc_18002ACF4
0x18002ac90  mov     r12d, [rsp+88h+ServiceStatus.dwCurrentState]
0x18002ac95  xor     ebx, ebx
0x18002ac97  test    rsi, rsi
0x18002ac9a  jz      short loc_18002ACFC
0x18002ac9c  lea     r9, [rsp+88h+pcbBytesNeeded]; pcbBytesNeeded
0x18002aca1  xor     r8d, r8d; cbBufSize
0x18002aca4  xor     edx, edx; lpServiceConfig
0x18002aca6  mov     rcx, rdi; hService
0x18002aca9  xor     ebp, ebp
0x18002acab  call    cs:__imp_QueryServiceConfigA
0x18002acb1  test    eax, eax
0x18002acb3  jnz     short loc_18002ACC6
0x18002acb5  call    cs:__imp_GetLastError
0x18002acbb  mov     ebx, eax
0x18002acbd  cmp     eax, 7Ah ; 'z'
0x18002acc0  jnz     short loc_18002ACFC
0x18002acc2  mov     ebp, [rsp+88h+pcbBytesNeeded]
0x18002acc6  mov     ecx, ebp; Size
0x18002acc8  call    Dns_AllocZero
0x18002accd  mov     [rsi], rax
0x18002acd0  test    rax, rax
0x18002acd3  jnz     short loc_18002ACDA
0x18002acd5  lea     ebx, [rax+0Eh]
0x18002acd8  jmp     short loc_18002ACFC
0x18002acda  lea     r9, [rsp+88h+pcbBytesNeeded]; pcbBytesNeeded
0x18002acdf  mov     r8d, ebp; cbBufSize
0x18002ace2  mov     rdx, rax; lpServiceConfig
0x18002ace5  mov     rcx, rdi; hService
0x18002ace8  xor     ebx, ebx
0x18002acea  call    cs:__imp_QueryServiceConfigA
0x18002acf0  test    eax, eax
0x18002acf2  jnz     short loc_18002ACFC
0x18002acf4  call    cs:__imp_GetLastError
0x18002acfa  mov     ebx, eax
0x18002acfc  test    r15, r15
0x18002acff  jz      short loc_18002AD06
0x18002ad01  mov     [r15], rdi
0x18002ad04  jmp     short loc_18002AD14
0x18002ad06  test    rdi, rdi
0x18002ad09  jz      short loc_18002AD14
0x18002ad0b  mov     rcx, rdi; hSCObject
0x18002ad0e  call    cs:__imp_CloseServiceHandle
0x18002ad14  test    r14, r14
0x18002ad17  jz      short loc_18002AD1C
0x18002ad19  mov     [r14], r12d
0x18002ad1c  mov     eax, ebx
0x18002ad1e  mov     rcx, [rsp+88h+var_40]
0x18002ad23  xor     rcx, rsp; StackCookie
0x18002ad26  call    __security_check_cookie
0x18002ad2b  add     rsp, 50h
0x18002ad2f  pop     r15
0x18002ad31  pop     r14
0x18002ad33  pop     r12
0x18002ad35  pop     rdi
0x18002ad36  pop     rsi
0x18002ad37  pop     rbp
0x18002ad38  pop     rbx
0x18002ad39  retn
```
