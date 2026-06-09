# GPMHelper::GetServiceInfo(GPMServiceInfo *,char *)

- ea: `0x18005ed84`
- end: `0x18005ef4d`
- name: `?GetServiceInfo@GPMHelper@@AEAAJPEAUGPMServiceInfo@@PEAD@Z`
- size: `457`
- prototype: `int(GPMHelper *__hidden this, struct GPMServiceInfo *, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18005d720`

## callees

- `0x18005ed84`
- `0x180075fa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005edd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ee09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ee3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ee5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ee8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eecb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005edd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ee09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ee3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ee5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ee8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eecb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ef03`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ef03`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005ee4f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005ee4f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005ef11`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005ef1f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005ef11`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005ef1f`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x18005edfb`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x18005edfb`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceConfigA` at `0x18005ee32`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceConfigA` at `0x18005ee85`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceConfigA` at `0x18005ee32`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceConfigA` at `0x18005ee85`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x18005edbf`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x18005edbf`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18005eec1`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18005eec1`

## pseudocode

```c
__int64 __fastcall GPMHelper::GetServiceInfo(GPMHelper *this, struct GPMServiceInfo *a2, char *a3)
{
  signed int v3; // ebx
  struct _QUERY_SERVICE_CONFIGA *v6; // rbp
  SC_HANDLE v7; // r15
  SC_HANDLE v8; // rdi
  signed int LastError; // eax
  signed int v10; // eax
  DWORD v11; // esi
  signed int v12; // eax
  signed int v13; // eax
  signed int v14; // eax
  DWORD pcbBytesNeeded; // [rsp+20h] [rbp-58h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+28h] [rbp-50h] BYREF

  v3 = 0;
  pcbBytesNeeded = 0;
  v6 = 0;
  v7 = OpenSCManagerA(0, 0, 1u);
  if ( v7 )
    goto LABEL_5;
  v8 = 0;
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
  if ( v3 >= 0 )
  {
LABEL_5:
    v8 = OpenServiceA(v7, a3, 5u);
    if ( v8 )
      goto LABEL_9;
    v10 = GetLastError();
    v3 = v10;
    if ( v10 > 0 )
      v3 = (unsigned __int16)v10 | 0x80070000;
    if ( v3 >= 0 )
    {
LABEL_9:
      v11 = 0;
      if ( QueryServiceConfigA(v8, 0, 0, &pcbBytesNeeded) )
        goto LABEL_18;
      if ( GetLastError() == 122 )
      {
        v11 = pcbBytesNeeded;
        v6 = (struct _QUERY_SERVICE_CONFIGA *)LocalAlloc(0, pcbBytesNeeded);
        if ( v6 )
          goto LABEL_18;
      }
      v12 = GetLastError();
      v3 = v12;
      if ( v12 > 0 )
        v3 = (unsigned __int16)v12 | 0x80070000;
      if ( v3 >= 0 )
      {
LABEL_18:
        if ( QueryServiceConfigA(v8, v6, v11, &pcbBytesNeeded) )
          goto LABEL_19;
        v13 = GetLastError();
        v3 = v13;
        if ( v13 > 0 )
          v3 = (unsigned __int16)v13 | 0x80070000;
        if ( v3 >= 0 )
        {
LABEL_19:
          *((_DWORD *)a2 + 1) = v6->dwStartType;
          memset(&ServiceStatus, 0, sizeof(ServiceStatus));
          if ( QueryServiceStatus(v8, &ServiceStatus) )
            goto LABEL_23;
          v14 = GetLastError();
          v3 = v14;
          if ( v14 > 0 )
            v3 = (unsigned __int16)v14 | 0x80070000;
          if ( v3 >= 0 )
          {
LABEL_23:
            *(_DWORD *)a2 = ServiceStatus.dwServiceType;
            *((_DWORD *)a2 + 2) = ServiceStatus.dwCurrentState;
            *((_DWORD *)a2 + 3) = ServiceStatus.dwWin32ExitCode;
            *((_DWORD *)a2 + 4) = ServiceStatus.dwServiceSpecificExitCode;
          }
        }
      }
    }
  }
  LocalFree(v6);
  if ( v8 )
    CloseServiceHandle(v8);
  if ( v7 )
    CloseServiceHandle(v7);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18005ed84  mov     [rsp+arg_0], rbx
0x18005ed89  mov     [rsp+arg_18], rbp
0x18005ed8e  push    rsi
0x18005ed8f  push    rdi
0x18005ed90  push    r12
0x18005ed92  push    r14
0x18005ed94  push    r15
0x18005ed96  sub     rsp, 50h
0x18005ed9a  mov     rax, cs:__security_cookie
0x18005eda1  xor     rax, rsp
0x18005eda4  mov     [rsp+78h+var_30], rax
0x18005eda9  xor     ebx, ebx
0x18005edab  mov     rsi, r8
0x18005edae  mov     r14, rdx
0x18005edb1  mov     [rsp+78h+pcbBytesNeeded], ebx
0x18005edb5  xor     edx, edx; lpDatabaseName
0x18005edb7  xor     ecx, ecx; lpMachineName
0x18005edb9  xor     ebp, ebp
0x18005edbb  lea     r8d, [rbx+1]; dwDesiredAccess
0x18005edbf  call    cs:__imp_OpenSCManagerA
0x18005edc5  mov     r15, rax
0x18005edc8  mov     r12d, 80070000h
0x18005edce  test    rax, rax
0x18005edd1  jnz     short loc_18005EDEF
0x18005edd3  xor     edi, edi
0x18005edd5  call    cs:__imp_GetLastError
0x18005eddb  mov     ebx, eax
0x18005eddd  test    eax, eax
0x18005eddf  jle     short loc_18005EDE7
0x18005ede1  movzx   ebx, ax
0x18005ede4  or      ebx, r12d
0x18005ede7  test    ebx, ebx
0x18005ede9  js      loc_18005EF00
0x18005edef  mov     r8d, 5; dwDesiredAccess
0x18005edf5  mov     rdx, rsi; lpServiceName
0x18005edf8  mov     rcx, r15; hSCManager
0x18005edfb  call    cs:__imp_OpenServiceA
0x18005ee01  mov     rdi, rax
0x18005ee04  test    rax, rax
0x18005ee07  jnz     short loc_18005EE23
0x18005ee09  call    cs:__imp_GetLastError
0x18005ee0f  mov     ebx, eax
0x18005ee11  test    eax, eax
0x18005ee13  jle     short loc_18005EE1B
0x18005ee15  movzx   ebx, ax
0x18005ee18  or      ebx, r12d
0x18005ee1b  test    ebx, ebx
0x18005ee1d  js      loc_18005EF00
0x18005ee23  lea     r9, [rsp+78h+pcbBytesNeeded]; pcbBytesNeeded
0x18005ee28  xor     r8d, r8d; cbBufSize
0x18005ee2b  xor     edx, edx; lpServiceConfig
0x18005ee2d  mov     rcx, rdi; hService
0x18005ee30  xor     esi, esi
0x18005ee32  call    cs:__imp_QueryServiceConfigA
0x18005ee38  test    eax, eax
0x18005ee3a  jnz     short loc_18005EE77
0x18005ee3c  call    cs:__imp_GetLastError
0x18005ee42  cmp     eax, 7Ah ; 'z'
0x18005ee45  jnz     short loc_18005EE5D
0x18005ee47  mov     esi, [rsp+78h+pcbBytesNeeded]
0x18005ee4b  xor     ecx, ecx; uFlags
0x18005ee4d  mov     edx, esi; uBytes
0x18005ee4f  call    cs:__imp_LocalAlloc
0x18005ee55  mov     rbp, rax
0x18005ee58  test    rax, rax
0x18005ee5b  jnz     short loc_18005EE77
0x18005ee5d  call    cs:__imp_GetLastError
0x18005ee63  mov     ebx, eax
0x18005ee65  test    eax, eax
0x18005ee67  jle     short loc_18005EE6F
0x18005ee69  movzx   ebx, ax
0x18005ee6c  or      ebx, r12d
0x18005ee6f  test    ebx, ebx
0x18005ee71  js      loc_18005EF00
0x18005ee77  lea     r9, [rsp+78h+pcbBytesNeeded]; pcbBytesNeeded
0x18005ee7c  mov     r8d, esi; cbBufSize
0x18005ee7f  mov     rdx, rbp; lpServiceConfig
0x18005ee82  mov     rcx, rdi; hService
0x18005ee85  call    cs:__imp_QueryServiceConfigA
0x18005ee8b  test    eax, eax
0x18005ee8d  jnz     short loc_18005EEA5
0x18005ee8f  call    cs:__imp_GetLastError
0x18005ee95  mov     ebx, eax
0x18005ee97  test    eax, eax
0x18005ee99  jle     short loc_18005EEA1
0x18005ee9b  movzx   ebx, ax
0x18005ee9e  or      ebx, r12d
0x18005eea1  test    ebx, ebx
0x18005eea3  js      short loc_18005EF00
0x18005eea5  mov     eax, [rbp+4]
0x18005eea8  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x18005eead  xorps   xmm0, xmm0
0x18005eeb0  mov     [r14+4], eax
0x18005eeb4  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x18005eeb9  mov     rcx, rdi; hService
0x18005eebc  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x18005eec1  call    cs:__imp_QueryServiceStatus
0x18005eec7  test    eax, eax
0x18005eec9  jnz     short loc_18005EEE1
0x18005eecb  call    cs:__imp_GetLastError
0x18005eed1  mov     ebx, eax
0x18005eed3  test    eax, eax
0x18005eed5  jle     short loc_18005EEDD
0x18005eed7  movzx   ebx, ax
0x18005eeda  or      ebx, r12d
0x18005eedd  test    ebx, ebx
0x18005eedf  js      short loc_18005EF00
0x18005eee1  mov     eax, [rsp+78h+ServiceStatus.dwServiceType]
0x18005eee5  mov     [r14], eax
0x18005eee8  mov     eax, [rsp+78h+ServiceStatus.dwCurrentState]
0x18005eeec  mov     [r14+8], eax
0x18005eef0  mov     eax, [rsp+78h+ServiceStatus.dwWin32ExitCode]
0x18005eef4  mov     [r14+0Ch], eax
0x18005eef8  mov     eax, [rsp+78h+ServiceStatus.dwServiceSpecificExitCode]
0x18005eefc  mov     [r14+10h], eax
0x18005ef00  mov     rcx, rbp; hMem
0x18005ef03  call    cs:__imp_LocalFree
0x18005ef09  test    rdi, rdi
0x18005ef0c  jz      short loc_18005EF17
0x18005ef0e  mov     rcx, rdi; hSCObject
0x18005ef11  call    cs:__imp_CloseServiceHandle
0x18005ef17  test    r15, r15
0x18005ef1a  jz      short loc_18005EF25
0x18005ef1c  mov     rcx, r15; hSCObject
0x18005ef1f  call    cs:__imp_CloseServiceHandle
0x18005ef25  mov     eax, ebx
0x18005ef27  mov     rcx, [rsp+78h+var_30]
0x18005ef2c  xor     rcx, rsp; StackCookie
0x18005ef2f  call    __security_check_cookie
0x18005ef34  lea     r11, [rsp+78h+var_28]
0x18005ef39  mov     rbx, [r11+30h]
0x18005ef3d  mov     rbp, [r11+48h]
0x18005ef41  mov     rsp, r11
0x18005ef44  pop     r15
0x18005ef46  pop     r14
0x18005ef48  pop     r12
0x18005ef4a  pop     rdi
0x18005ef4b  pop     rsi
0x18005ef4c  retn
```
