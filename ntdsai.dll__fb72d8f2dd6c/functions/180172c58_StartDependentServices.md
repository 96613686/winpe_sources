# StartDependentServices

- ea: `0x180172c58`
- end: `0x180172de3`
- name: `StartDependentServices`
- size: `395`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800b52f0`

## callees

- `0x1801723ec`
- `0x180172c58`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180172dc8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180172dc8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180172d2b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180172d2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180172c96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180172cc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180172d0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180172d69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180172c96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180172cc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180172d0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180172d69`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x180172cb3`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x180172cb3`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x180172c88`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x180172c88`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180172dac`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180172dba`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180172dac`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180172dba`
- `ADVAPI32!EnumDependentServicesA` at `0x180172cf9`
- `ADVAPI32!EnumDependentServicesA` at `0x180172d5f`
- `ADVAPI32!EnumDependentServicesA` at `0x180172cf9`
- `ADVAPI32!EnumDependentServicesA` at `0x180172d5f`

## pseudocode

```c
__int64 __fastcall StartDependentServices(__int64 a1)
{
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // r14
  DWORD LastError; // ebx
  struct _ENUM_SERVICE_STATUSA *v4; // rdi
  SC_HANDLE v5; // rbp
  DWORD v6; // eax
  struct _ENUM_SERVICE_STATUSA *v7; // rax
  __int64 i; // rsi
  DWORD v9; // eax
  DWORD ServicesReturned; // [rsp+50h] [rbp+8h] BYREF
  int v12; // [rsp+54h] [rbp+Ch]
  DWORD cbBufSize; // [rsp+58h] [rbp+10h] BYREF

  v12 = HIDWORD(a1);
  cbBufSize = 0;
  ServicesReturned = 0;
  v1 = OpenSCManagerA(0, 0, 1u);
  v2 = v1;
  if ( v1 )
  {
    v4 = 0;
    v5 = OpenServiceA(v1, "NTDS", 8u);
    if ( v5 )
    {
      if ( EnumDependentServicesA(v5, 2u, 0, 0, &cbBufSize, &ServicesReturned) )
      {
        LastError = 0;
      }
      else
      {
        LastError = GetLastError();
        if ( LastError == 234 && cbBufSize )
        {
          v7 = (struct _ENUM_SERVICE_STATUSA *)malloc(cbBufSize);
          v4 = v7;
          if ( v7 )
          {
            if ( EnumDependentServicesA(v5, 2u, v7, cbBufSize, &cbBufSize, &ServicesReturned) )
            {
              for ( i = 0; (unsigned int)i < ServicesReturned; i = (unsigned int)(i + 1) )
              {
                v9 = DsControlService(v4[i].lpServiceName, 1, 0);
                LastError = v9;
                if ( !v9 || v9 == 1058 )
                  LastError = 0;
              }
            }
            else
            {
              LastError = GetLastError();
            }
          }
          else
          {
            LastError = 14;
          }
        }
      }
    }
    else
    {
      v6 = GetLastError();
      LastError = 0;
      if ( v6 != 1060 )
        LastError = v6;
    }
    CloseServiceHandle(v2);
    if ( v5 )
      CloseServiceHandle(v5);
    if ( v4 )
      free(v4);
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x180172c58  mov     rax, rsp
0x180172c5b  mov     [rax+18h], rbx
0x180172c5f  mov     [rax+20h], rbp
0x180172c63  mov     [rax+10h], edx
0x180172c66  mov     [rax+8], rcx
0x180172c6a  push    rsi
0x180172c6b  push    rdi
0x180172c6c  push    r14
0x180172c6e  sub     rsp, 30h
0x180172c72  xor     edx, edx; lpDatabaseName
0x180172c74  mov     dword ptr [rax+10h], 0
0x180172c7b  xor     ecx, ecx; lpMachineName
0x180172c7d  mov     dword ptr [rax+8], 0
0x180172c84  lea     r8d, [rdx+1]; dwDesiredAccess
0x180172c88  call    cs:__imp_OpenSCManagerA
0x180172c8e  mov     r14, rax
0x180172c91  test    rax, rax
0x180172c94  jnz     short loc_180172CA3
0x180172c96  call    cs:__imp_GetLastError
0x180172c9c  mov     ebx, eax
0x180172c9e  jmp     loc_180172DCE
0x180172ca3  xor     edi, edi
0x180172ca5  lea     rdx, ServerPrincName; "NTDS"
0x180172cac  mov     rcx, r14; hSCManager
0x180172caf  lea     r8d, [rdi+8]; dwDesiredAccess
0x180172cb3  call    cs:__imp_OpenServiceA
0x180172cb9  mov     rbp, rax
0x180172cbc  test    rax, rax
0x180172cbf  jnz     short loc_180172CD6
0x180172cc1  call    cs:__imp_GetLastError
0x180172cc7  xor     ebx, ebx
0x180172cc9  cmp     eax, 424h
0x180172cce  cmovnz  ebx, eax
0x180172cd1  jmp     loc_180172DA9
0x180172cd6  xor     r9d, r9d; cbBufSize
0x180172cd9  lea     rax, [rsp+48h+ServicesReturned]
0x180172cde  mov     [rsp+48h+lpServicesReturned], rax; lpServicesReturned
0x180172ce3  xor     r8d, r8d; lpServices
0x180172ce6  lea     rax, [rsp+48h+cbBufSize]
0x180172ceb  mov     rcx, rbp; hService
0x180172cee  mov     [rsp+48h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180172cf3  lea     esi, [r9+2]
0x180172cf7  mov     edx, esi; dwServiceState
0x180172cf9  call    cs:__imp_EnumDependentServicesA
0x180172cff  test    eax, eax
0x180172d01  jz      short loc_180172D0A
0x180172d03  xor     ebx, ebx
0x180172d05  jmp     loc_180172DA9
0x180172d0a  call    cs:__imp_GetLastError
0x180172d10  mov     ebx, eax
0x180172d12  cmp     eax, 0EAh
0x180172d17  jnz     loc_180172DA9
0x180172d1d  mov     eax, [rsp+48h+cbBufSize]
0x180172d21  test    eax, eax
0x180172d23  jz      loc_180172DA9
0x180172d29  mov     ecx, eax; Size
0x180172d2b  call    cs:__imp_malloc
0x180172d31  mov     rdi, rax
0x180172d34  test    rax, rax
0x180172d37  jnz     short loc_180172D3E
0x180172d39  lea     ebx, [rax+0Eh]
0x180172d3c  jmp     short loc_180172DA9
0x180172d3e  mov     r9d, [rsp+48h+cbBufSize]; cbBufSize
0x180172d43  lea     rax, [rsp+48h+ServicesReturned]
0x180172d48  mov     [rsp+48h+lpServicesReturned], rax; lpServicesReturned
0x180172d4d  mov     r8, rdi; lpServices
0x180172d50  lea     rax, [rsp+48h+cbBufSize]
0x180172d55  mov     edx, esi; dwServiceState
0x180172d57  mov     rcx, rbp; hService
0x180172d5a  mov     [rsp+48h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180172d5f  call    cs:__imp_EnumDependentServicesA
0x180172d65  test    eax, eax
0x180172d67  jnz     short loc_180172D73
0x180172d69  call    cs:__imp_GetLastError
0x180172d6f  mov     ebx, eax
0x180172d71  jmp     short loc_180172DA9
0x180172d73  xor     esi, esi
0x180172d75  cmp     [rsp+48h+ServicesReturned], esi
0x180172d79  jbe     short loc_180172DA9
0x180172d7b  xor     r8d, r8d
0x180172d7e  lea     rcx, [rsi+rsi*2]
0x180172d82  add     rcx, rcx
0x180172d85  lea     edx, [r8+1]
0x180172d89  mov     rcx, [rdi+rcx*8]
0x180172d8d  call    DsControlService
0x180172d92  mov     ebx, eax
0x180172d94  test    eax, eax
0x180172d96  jz      short loc_180172D9F
0x180172d98  cmp     eax, 422h
0x180172d9d  jnz     short loc_180172DA1
0x180172d9f  xor     ebx, ebx
0x180172da1  inc     esi
0x180172da3  cmp     esi, [rsp+48h+ServicesReturned]
0x180172da7  jb      short loc_180172D7B
0x180172da9  mov     rcx, r14; hSCObject
0x180172dac  call    cs:__imp_CloseServiceHandle
0x180172db2  test    rbp, rbp
0x180172db5  jz      short loc_180172DC0
0x180172db7  mov     rcx, rbp; hSCObject
0x180172dba  call    cs:__imp_CloseServiceHandle
0x180172dc0  test    rdi, rdi
0x180172dc3  jz      short loc_180172DCE
0x180172dc5  mov     rcx, rdi; Block
0x180172dc8  call    cs:__imp_free
0x180172dce  mov     rbp, [rsp+48h+arg_18]
0x180172dd3  mov     eax, ebx
0x180172dd5  mov     rbx, [rsp+48h+arg_10]
0x180172dda  add     rsp, 30h
0x180172dde  pop     r14
0x180172de0  pop     rdi
0x180172de1  pop     rsi
0x180172de2  retn
```
