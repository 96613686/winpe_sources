# DsControlService

- ea: `0x1801723ec`
- end: `0x18017260b`
- name: `DsControlService`
- size: `543`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800b5290`
- `0x1801723ec`
- `0x180172c58`

## callees

- `0x18001e090`
- `0x1801723ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801724a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801724db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017251e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801724a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801724db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017251e`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x1801724cd`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x1801724cd`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x180172496`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x180172496`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18017256d`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18017256d`
- `api-ms-win-service-winsvc-l1-1-0!StartServiceA` at `0x180172514`
- `api-ms-win-service-winsvc-l1-1-0!StartServiceA` at `0x180172514`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1801724f5`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18017259a`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1801724f5`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18017259a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18017252b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180172539`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18017252b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180172539`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18017258c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18017258c`

## pseudocode

```c
__int64 __fastcall DsControlService(const CHAR *a1, int a2, unsigned int a3)
{
  int v5; // edx
  __int64 result; // rax
  int v7; // ebp
  int v8; // r15d
  SC_HANDLE v9; // rax
  DWORD dwServiceSpecificExitCode; // ebx
  SC_HANDLE v11; // rax
  SC_HANDLE v12; // rsi
  DWORD LastError; // eax
  int v15; // r14d
  int v16; // ebp
  int v17; // r12d
  int v18; // [rsp+20h] [rbp-78h]
  SC_HANDLE hSCObject; // [rsp+28h] [rbp-70h]
  struct _SERVICE_STATUS ServiceStatus; // [rsp+30h] [rbp-68h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( !a2 )
  {
    v18 = 3;
    v8 = 1;
    v7 = 0;
    goto LABEL_9;
  }
  v5 = a2 - 1;
  if ( !v5 )
  {
    v18 = 2;
    v7 = 1;
    v8 = 4;
LABEL_9:
    v9 = OpenSCManagerA(0, 0, 1u);
    hSCObject = v9;
    if ( !v9 )
      return GetLastError();
    v11 = OpenServiceA(v9, a1, (16 * ((v7 ^ 1) + 1)) | 0x85u);
    v12 = v11;
    if ( !v11 )
    {
      LastError = GetLastError();
      dwServiceSpecificExitCode = 0;
      if ( LastError != 1060 )
        dwServiceSpecificExitCode = LastError;
      goto LABEL_21;
    }
    if ( QueryServiceStatus(v11, &ServiceStatus) )
    {
      dwServiceSpecificExitCode = 0;
      if ( ServiceStatus.dwCurrentState == v8 )
        goto LABEL_21;
      if ( v7 ? StartServiceA(v12, 0, 0) : ControlService(v12, 1u, &ServiceStatus) )
      {
        v15 = 0;
        v16 = 0;
        v17 = 1;
        if ( !a3 )
        {
LABEL_21:
          CloseServiceHandle(hSCObject);
          if ( v12 )
            CloseServiceHandle(v12);
          return dwServiceSpecificExitCode;
        }
        while ( 1 )
        {
          Sleep(0x3E8u);
          if ( !QueryServiceStatus(v12, &ServiceStatus) )
            break;
          if ( (unsigned int)++v15 > 0x384 )
          {
            dwServiceSpecificExitCode = 1070;
            goto LABEL_21;
          }
          if ( ServiceStatus.dwCurrentState != v18 )
          {
            if ( ServiceStatus.dwCurrentState != v8 )
            {
              dwServiceSpecificExitCode = ServiceStatus.dwServiceSpecificExitCode;
              if ( !ServiceStatus.dwServiceSpecificExitCode )
                dwServiceSpecificExitCode = 1066;
            }
            goto LABEL_21;
          }
          if ( ServiceStatus.dwCheckPoint == -1 )
          {
            if ( (unsigned int)++v16 > 0x1E )
            {
              dwServiceSpecificExitCode = 1053;
              v17 = 0;
            }
          }
          else
          {
            v16 = 0;
          }
          if ( !v17 )
            goto LABEL_21;
        }
      }
    }
    dwServiceSpecificExitCode = GetLastError();
    goto LABEL_21;
  }
  if ( v5 != 1 )
    return 1359;
  result = DsControlService(a1, 0, 1);
  if ( !(_DWORD)result )
    return DsControlService(a1, 1, a3);
  return result;
}

```

## disassembly

```asm
0x1801723ec  mov     [rsp+arg_8], rbx
0x1801723f1  push    rbp
0x1801723f2  push    rsi
0x1801723f3  push    rdi
0x1801723f4  push    r12
0x1801723f6  push    r13
0x1801723f8  push    r14
0x1801723fa  push    r15
0x1801723fc  sub     rsp, 60h
0x180172400  mov     rax, cs:__security_cookie
0x180172407  xor     rax, rsp
0x18017240a  mov     [rsp+98h+var_48], rax
0x18017240f  xorps   xmm0, xmm0
0x180172412  mov     r13d, r8d
0x180172415  mov     rbx, rcx
0x180172418  movups  xmmword ptr [rsp+98h+ServiceStatus.dwServiceType], xmm0
0x18017241d  movups  xmmword ptr [rsp+98h+ServiceStatus.dwWin32ExitCode], xmm0
0x180172422  test    edx, edx
0x180172424  jz      short loc_18017247D
0x180172426  sub     edx, 1
0x180172429  jz      short loc_180172468
0x18017242b  cmp     edx, 1
0x18017242e  jz      short loc_18017243A
0x180172430  mov     eax, 54Fh
0x180172435  jmp     loc_180172541
0x18017243a  xor     r9d, r9d
0x18017243d  xor     edx, edx
0x18017243f  lea     edi, [r9+1]
0x180172443  mov     r8d, edi
0x180172446  call    DsControlService
0x18017244b  test    eax, eax
0x18017244d  jnz     loc_180172541
0x180172453  xor     r9d, r9d
0x180172456  mov     r8d, r13d
0x180172459  mov     edx, edi
0x18017245b  mov     rcx, rbx
0x18017245e  call    DsControlService
0x180172463  jmp     loc_180172541
0x180172468  mov     edi, 1
0x18017246d  mov     [rsp+98h+var_78], 2
0x180172475  mov     ebp, edi
0x180172477  lea     r15d, [rdi+3]
0x18017247b  jmp     short loc_18017248F
0x18017247d  mov     edi, 1
0x180172482  mov     [rsp+98h+var_78], 3
0x18017248a  mov     r15d, edi
0x18017248d  xor     ebp, ebp
0x18017248f  mov     r8d, edi; dwDesiredAccess
0x180172492  xor     edx, edx; lpDatabaseName
0x180172494  xor     ecx, ecx; lpMachineName
0x180172496  call    cs:__imp_OpenSCManagerA
0x18017249c  mov     [rsp+98h+hSCObject], rax
0x1801724a1  test    rax, rax
0x1801724a4  jnz     short loc_1801724B3
0x1801724a6  call    cs:__imp_GetLastError
0x1801724ac  mov     ebx, eax
0x1801724ae  jmp     loc_18017253F
0x1801724b3  mov     r8d, ebp
0x1801724b6  mov     rdx, rbx; lpServiceName
0x1801724b9  xor     r8d, edi
0x1801724bc  mov     rcx, rax; hSCManager
0x1801724bf  add     r8d, edi
0x1801724c2  shl     r8d, 4
0x1801724c6  or      r8d, 85h; dwDesiredAccess
0x1801724cd  call    cs:__imp_OpenServiceA
0x1801724d3  mov     rsi, rax
0x1801724d6  test    rax, rax
0x1801724d9  jnz     short loc_1801724ED
0x1801724db  call    cs:__imp_GetLastError
0x1801724e1  xor     ebx, ebx
0x1801724e3  cmp     eax, 424h
0x1801724e8  cmovnz  ebx, eax
0x1801724eb  jmp     short loc_180172526
0x1801724ed  lea     rdx, [rsp+98h+ServiceStatus]; lpServiceStatus
0x1801724f2  mov     rcx, rsi; hService
0x1801724f5  call    cs:__imp_QueryServiceStatus
0x1801724fb  test    eax, eax
0x1801724fd  jz      short loc_18017251E
0x1801724ff  xor     ebx, ebx
0x180172501  cmp     [rsp+98h+ServiceStatus.dwCurrentState], r15d
0x180172506  jz      short loc_180172526
0x180172508  mov     rcx, rsi; hService
0x18017250b  test    ebp, ebp
0x18017250d  jz      short loc_180172566
0x18017250f  xor     r8d, r8d; lpServiceArgVectors
0x180172512  xor     edx, edx; dwNumServiceArgs
0x180172514  call    cs:__imp_StartServiceA
0x18017251a  test    eax, eax
0x18017251c  jnz     short loc_180172575
0x18017251e  call    cs:__imp_GetLastError
0x180172524  mov     ebx, eax
0x180172526  mov     rcx, [rsp+98h+hSCObject]; hSCObject
0x18017252b  call    cs:__imp_CloseServiceHandle
0x180172531  test    rsi, rsi
0x180172534  jz      short loc_18017253F
0x180172536  mov     rcx, rsi; hSCObject
0x180172539  call    cs:__imp_CloseServiceHandle
0x18017253f  mov     eax, ebx
0x180172541  mov     rcx, [rsp+98h+var_48]
0x180172546  xor     rcx, rsp; StackCookie
0x180172549  call    __security_check_cookie
0x18017254e  mov     rbx, [rsp+98h+arg_8]
0x180172556  add     rsp, 60h
0x18017255a  pop     r15
0x18017255c  pop     r14
0x18017255e  pop     r13
0x180172560  pop     r12
0x180172562  pop     rdi
0x180172563  pop     rsi
0x180172564  pop     rbp
0x180172565  retn
0x180172566  lea     r8, [rsp+98h+ServiceStatus]; lpServiceStatus
0x18017256b  mov     edx, edi; dwControl
0x18017256d  call    cs:__imp_ControlService
0x180172573  jmp     short loc_18017251A
0x180172575  xor     r14d, r14d
0x180172578  xor     ebp, ebp
0x18017257a  mov     r12d, edi
0x18017257d  test    r13d, r13d
0x180172580  jz      short loc_180172526
0x180172582  mov     r13d, [rsp+98h+var_78]
0x180172587  mov     ecx, 3E8h; dwMilliseconds
0x18017258c  call    cs:__imp_Sleep
0x180172592  lea     rdx, [rsp+98h+ServiceStatus]; lpServiceStatus
0x180172597  mov     rcx, rsi; hService
0x18017259a  call    cs:__imp_QueryServiceStatus
0x1801725a0  test    eax, eax
0x1801725a2  jz      loc_18017251E
0x1801725a8  add     r14d, edi
0x1801725ab  cmp     r14d, 384h
0x1801725b2  ja      short loc_180172601
0x1801725b4  cmp     [rsp+98h+ServiceStatus.dwCurrentState], r13d
0x1801725b9  jnz     short loc_1801725E0
0x1801725bb  cmp     [rsp+98h+ServiceStatus.dwCheckPoint], 0FFFFFFFFh
0x1801725c0  jnz     short loc_1801725D3
0x1801725c2  add     ebp, edi
0x1801725c4  cmp     ebp, 1Eh
0x1801725c7  jbe     short loc_1801725D5
0x1801725c9  mov     ebx, 41Dh
0x1801725ce  xor     r12d, r12d
0x1801725d1  jmp     short loc_1801725D5
0x1801725d3  xor     ebp, ebp
0x1801725d5  test    r12d, r12d
0x1801725d8  jz      loc_180172526
0x1801725de  jmp     short loc_180172587
0x1801725e0  cmp     [rsp+98h+ServiceStatus.dwCurrentState], r15d
0x1801725e5  jz      loc_180172526
0x1801725eb  mov     ebx, [rsp+98h+ServiceStatus.dwServiceSpecificExitCode]
0x1801725ef  test    ebx, ebx
0x1801725f1  jnz     loc_180172526
0x1801725f7  mov     ebx, 42Ah
0x1801725fc  jmp     loc_180172526
0x180172601  mov     ebx, 42Eh
0x180172606  jmp     loc_180172526
```
