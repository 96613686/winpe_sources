# CAppInfoV2::GetInventorySvcStartType(void)

- ea: `0x1800994a0`
- end: `0x18009964f`
- name: `?GetInventorySvcStartType@CAppInfoV2@@QEBAIXZ`
- size: `431`
- prototype: `unsigned int __fastcall(CAppInfoV2 *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x1800994a0`
- `0x18016796c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800994d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099526`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009956f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800995f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800994d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099526`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009956f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800995f8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180099550`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009959e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180099632`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009963c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180099550`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009959e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180099632`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009963c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180099510`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180099510`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800994c0`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800994c0`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180099565`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800995ee`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180099565`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800995ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099628`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099628`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800995ae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800995ae`

## string_xrefs

- `0x1800994e0`: `OpenSCManager failed [%d]`
- `0x180099530`: `OpenService failed [%d]`
- `0x18009957e`: `QueryServiceConfig failed [%d]`
- `0x180099602`: `QueryServiceConfig failed [%d]`

## pseudocode

```c
__int64 __fastcall CAppInfoV2::GetInventorySvcStartType(CAppInfoV2 *this)
{
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rbx
  DWORD LastError; // eax
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rdi
  DWORD v7; // eax
  DWORD v8; // eax
  DWORD v9; // ebp
  struct _QUERY_SERVICE_CONFIGW *v10; // rax
  struct _QUERY_SERVICE_CONFIGW *v11; // rsi
  DWORD v12; // eax
  unsigned int dwServiceType; // ebp
  DWORD pcbBytesNeeded; // [rsp+78h] [rbp+10h] BYREF
  SC_HANDLE v15; // [rsp+80h] [rbp+18h]
  SC_HANDLE v16; // [rsp+88h] [rbp+20h]

  pcbBytesNeeded = 0;
  v1 = OpenSCManagerW(0, 0, 1u);
  v2 = v1;
  v15 = v1;
  if ( !v1 )
  {
    LastError = GetLastError();
    AslLogCallPrintf(1, "CAppInfoV2::GetInventorySvcStartType", 124, "OpenSCManager failed [%d]", LastError);
    return 0xFFFFFFFFLL;
  }
  v5 = OpenServiceW(v1, L"InventorySvc", 1u);
  v6 = v5;
  v16 = v5;
  if ( !v5 )
  {
    v7 = GetLastError();
    AslLogCallPrintf(1, "CAppInfoV2::GetInventorySvcStartType", 132, "OpenService failed [%d]", v7);
LABEL_6:
    CloseServiceHandle(v2);
    return 0xFFFFFFFFLL;
  }
  if ( !QueryServiceConfigW(v5, 0, 0, &pcbBytesNeeded) )
  {
    v8 = GetLastError();
    if ( v8 != 122 )
    {
      AslLogCallPrintf(1, "CAppInfoV2::GetInventorySvcStartType", 141, "QueryServiceConfig failed [%d]", v8);
LABEL_10:
      CloseServiceHandle(v6);
      goto LABEL_6;
    }
  }
  v9 = pcbBytesNeeded;
  v10 = (struct _QUERY_SERVICE_CONFIGW *)LocalAlloc(0, pcbBytesNeeded);
  v11 = v10;
  if ( !v10 )
  {
    AslLogCallPrintf(1, "CAppInfoV2::GetInventorySvcStartType", 150, "LocalAlloc failed");
    goto LABEL_10;
  }
  if ( QueryServiceConfigW(v6, v10, v9, &pcbBytesNeeded) )
  {
    dwServiceType = v11->dwServiceType;
  }
  else
  {
    v12 = GetLastError();
    AslLogCallPrintf(1, "CAppInfoV2::GetInventorySvcStartType", 156, "QueryServiceConfig failed [%d]", v12);
    dwServiceType = -1;
  }
  LocalFree(v11);
  CloseServiceHandle(v6);
  CloseServiceHandle(v2);
  return dwServiceType;
}

```

## disassembly

```asm
0x1800994a0  push    rbx
0x1800994a2  push    rbp
0x1800994a3  push    rsi
0x1800994a4  push    rdi
0x1800994a5  push    r14
0x1800994a7  sub     rsp, 40h
0x1800994ab  mov     [rsp+68h+pcbBytesNeeded], 0
0x1800994b3  mov     r14d, 1
0x1800994b9  mov     r8d, r14d; dwDesiredAccess
0x1800994bc  xor     edx, edx; lpDatabaseName
0x1800994be  xor     ecx, ecx; lpMachineName
0x1800994c0  call    cs:__imp_OpenSCManagerW
0x1800994c6  mov     rbx, rax
0x1800994c9  mov     [rsp+68h+arg_10], rax
0x1800994d1  test    rax, rax
0x1800994d4  jnz     short loc_180099503
0x1800994d6  call    cs:__imp_GetLastError
0x1800994dc  mov     [rsp+68h+var_48], eax
0x1800994e0  lea     r9, aOpenscmanagerF; "OpenSCManager failed [%d]"
0x1800994e7  lea     r8d, [r14+7Bh]
0x1800994eb  lea     rdx, aCappinfov2Geti; "CAppInfoV2::GetInventorySvcStartType"
0x1800994f2  mov     ecx, r14d
0x1800994f5  call    AslLogCallPrintf
0x1800994fa  nop
0x1800994fb  or      eax, 0FFFFFFFFh
0x1800994fe  jmp     loc_180099644
0x180099503  mov     r8d, r14d; dwDesiredAccess
0x180099506  lea     rdx, ServiceName; "InventorySvc"
0x18009950d  mov     rcx, rbx; hSCManager
0x180099510  call    cs:__imp_OpenServiceW
0x180099516  mov     rdi, rax
0x180099519  mov     [rsp+68h+arg_18], rax
0x180099521  test    rax, rax
0x180099524  jnz     short loc_180099558
0x180099526  call    cs:__imp_GetLastError
0x18009952c  mov     [rsp+68h+var_48], eax
0x180099530  lea     r9, aOpenserviceFai; "OpenService failed [%d]"
0x180099537  mov     r8d, 84h
0x18009953d  lea     rdx, aCappinfov2Geti; "CAppInfoV2::GetInventorySvcStartType"
0x180099544  mov     ecx, r14d
0x180099547  call    AslLogCallPrintf
0x18009954c  nop
0x18009954d  mov     rcx, rbx; hSCObject
0x180099550  call    cs:__imp_CloseServiceHandle
0x180099556  jmp     short loc_1800994FB
0x180099558  lea     r9, [rsp+68h+pcbBytesNeeded]; pcbBytesNeeded
0x18009955d  xor     r8d, r8d; cbBufSize
0x180099560  xor     edx, edx; lpServiceConfig
0x180099562  mov     rcx, rdi; hService
0x180099565  call    cs:__imp_QueryServiceConfigW
0x18009956b  test    eax, eax
0x18009956d  jnz     short loc_1800995A6
0x18009956f  call    cs:__imp_GetLastError
0x180099575  cmp     eax, 7Ah ; 'z'
0x180099578  jz      short loc_1800995A6
0x18009957a  mov     [rsp+68h+var_48], eax
0x18009957e  lea     r9, aQueryserviceco; "QueryServiceConfig failed [%d]"
0x180099585  mov     r8d, 8Dh
0x18009958b  lea     rdx, aCappinfov2Geti; "CAppInfoV2::GetInventorySvcStartType"
0x180099592  mov     ecx, r14d
0x180099595  call    AslLogCallPrintf
0x18009959a  nop
0x18009959b  mov     rcx, rdi; hSCObject
0x18009959e  call    cs:__imp_CloseServiceHandle
0x1800995a4  jmp     short loc_18009954D
0x1800995a6  mov     ebp, [rsp+68h+pcbBytesNeeded]
0x1800995aa  mov     edx, ebp; uBytes
0x1800995ac  xor     ecx, ecx; uFlags
0x1800995ae  call    cs:__imp_LocalAlloc
0x1800995b4  mov     rsi, rax
0x1800995b7  mov     [rsp+68h+var_38], rax
0x1800995bc  test    rax, rax
0x1800995bf  jnz     short loc_1800995E0
0x1800995c1  lea     r9, aLocalallocFail; "LocalAlloc failed"
0x1800995c8  mov     r8d, 96h
0x1800995ce  lea     rdx, aCappinfov2Geti; "CAppInfoV2::GetInventorySvcStartType"
0x1800995d5  mov     ecx, r14d
0x1800995d8  call    AslLogCallPrintf
0x1800995dd  nop
0x1800995de  jmp     short loc_18009959B
0x1800995e0  lea     r9, [rsp+68h+pcbBytesNeeded]; pcbBytesNeeded
0x1800995e5  mov     r8d, ebp; cbBufSize
0x1800995e8  mov     rdx, rsi; lpServiceConfig
0x1800995eb  mov     rcx, rdi; hService
0x1800995ee  call    cs:__imp_QueryServiceConfigW
0x1800995f4  test    eax, eax
0x1800995f6  jnz     short loc_180099623
0x1800995f8  call    cs:__imp_GetLastError
0x1800995fe  mov     [rsp+68h+var_48], eax
0x180099602  lea     r9, aQueryserviceco; "QueryServiceConfig failed [%d]"
0x180099609  mov     r8d, 9Ch
0x18009960f  lea     rdx, aCappinfov2Geti; "CAppInfoV2::GetInventorySvcStartType"
0x180099616  mov     ecx, r14d
0x180099619  call    AslLogCallPrintf
0x18009961e  or      ebp, 0FFFFFFFFh
0x180099621  jmp     short loc_180099625
0x180099623  mov     ebp, [rsi]
0x180099625  mov     rcx, rsi; hMem
0x180099628  call    cs:__imp_LocalFree
0x18009962e  nop
0x18009962f  mov     rcx, rdi; hSCObject
0x180099632  call    cs:__imp_CloseServiceHandle
0x180099638  nop
0x180099639  mov     rcx, rbx; hSCObject
0x18009963c  call    cs:__imp_CloseServiceHandle
0x180099642  mov     eax, ebp
0x180099644  add     rsp, 40h
0x180099648  pop     r14
0x18009964a  pop     rdi
0x18009964b  pop     rsi
0x18009964c  pop     rbp
0x18009964d  pop     rbx
0x18009964e  retn
```
