# RasStartRasAutoIfRequired

- ea: `0x180020d30`
- end: `0x180021234`
- name: `RasStartRasAutoIfRequired`
- size: `1284`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180020d30`
- `0x180021ae4`
- `0x180021b14`
- `0x18002491c`
- `0x180024954`
- `0x1800273d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020db9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020dda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020e3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020e70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020e91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020db9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020dda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020e3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020e70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020e91`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180020f75`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180020f75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020fd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021126`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002116e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020fd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021126`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002116e`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x180020ecd`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x180020ecd`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x180020ea5`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x180020ea5`
- `api-ms-win-service-winsvc-l1-1-0!StartServiceA` at `0x180020fc3`
- `api-ms-win-service-winsvc-l1-1-0!StartServiceA` at `0x180020fc3`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180020eed`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180020eed`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800211bf`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800211da`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800211bf`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800211da`

## pseudocode

```c
__int64 RasStartRasAutoIfRequired()
{
  PVOID *v0; // rbx
  unsigned int v1; // edi
  PVOID v2; // rbx
  DWORD CurrentProcessId; // eax
  __int64 v4; // rdx
  SC_HANDLE v5; // rbp
  __int64 v6; // rbx
  DWORD v7; // eax
  SC_HANDLE v8; // rax
  SC_HANDLE v9; // r14
  int v10; // ebx
  PVOID *v11; // rcx
  DWORD v12; // eax
  __int64 v13; // r9
  __int64 v14; // rdx
  DWORD v15; // eax
  DWORD LastError; // eax
  PVOID *v17; // rcx
  int v19; // [rsp+20h] [rbp-68h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+28h] [rbp-60h] BYREF

  v0 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
    v0 = (PVOID *)WPP_GLOBAL_Control;
  }
  v1 = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( g_fRasAutoStarted )
  {
    if ( v0 == &WPP_GLOBAL_Control || (*((_BYTE *)v0 + 28) & 0x40) == 0 || *((_BYTE *)v0 + 25) < 5u )
      goto LABEL_11;
    v2 = v0[2];
    CurrentProcessId = GetCurrentProcessId();
    v4 = 33;
LABEL_10:
    WPP_SF_d(v2, v4, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, CurrentProcessId);
LABEL_11:
    GetCurrentProcessId();
    goto LABEL_91;
  }
  v19 = 0;
  if ( ((unsigned int)GetComputerSuiteMask(&v19) || (v19 & 0x200) == 0)
    && (!dword_180031950 && (unsigned int)LoadSkuAndRole() || dword_180031924) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
    {
      goto LABEL_11;
    }
    v2 = (PVOID)*((_QWORD *)WPP_GLOBAL_Control + 2);
    CurrentProcessId = GetCurrentProcessId();
    v4 = 34;
    goto LABEL_10;
  }
  v5 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v6 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v7 = GetCurrentProcessId();
    WPP_SF_d(v6, 35, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v7);
  }
  GetCurrentProcessId();
  v8 = OpenSCManagerA(0, 0, 1u);
  v9 = v8;
  if ( !v8 || (v10 = 0, (v5 = OpenServiceA(v8, "RasAuto", 0x14u)) == 0) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError )
    {
      v17 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_87:
        if ( v9 )
          goto LABEL_88;
        goto LABEL_89;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, LastError);
    }
    v17 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_87;
  }
  while ( 1 )
  {
    while ( 1 )
    {
      if ( !QueryServiceStatus(v5, &ServiceStatus) )
      {
        v15 = GetLastError();
        v1 = v15;
        if ( v15 )
        {
          v11 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v14 = 37;
            v13 = v15;
            goto LABEL_80;
          }
        }
        goto LABEL_88;
      }
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          38,
          &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids,
          ServiceStatus.dwCurrentState);
        v11 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( ServiceStatus.dwCurrentState == 1 )
        break;
      if ( ServiceStatus.dwCurrentState != 2 )
      {
        if ( ServiceStatus.dwCurrentState == 4 )
        {
          if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x40) != 0 && *((_BYTE *)v11 + 25) >= 5u )
            WPP_SF_(v11[2], 44, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
          g_fRasAutoStarted = 1;
          goto LABEL_88;
        }
        if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x40) != 0 && *((_BYTE *)v11 + 25) >= 5u )
        {
          WPP_SF_(v11[2], 45, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
          v11 = (PVOID *)WPP_GLOBAL_Control;
        }
        v13 = 757;
        v1 = 757;
        if ( v11 == &WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 0x40) == 0 || *((_BYTE *)v11 + 25) < 2u )
          goto LABEL_88;
        v14 = 46;
        goto LABEL_80;
      }
      if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x40) != 0 && *((_BYTE *)v11 + 25) >= 5u )
        WPP_SF_(v11[2], 43, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
      Sleep(0x1F4u);
    }
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x40) != 0 && *((_BYTE *)v11 + 25) >= 5u )
    {
      WPP_SF_(v11[2], 39, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10 )
      break;
    if ( !StartServiceA(v5, 0, 0) )
    {
      v12 = GetLastError();
      v1 = v12;
      if ( v12 == 1056 )
      {
        v1 = 0;
      }
      else if ( v12 )
      {
        v11 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v12);
          v11 = (PVOID *)WPP_GLOBAL_Control;
        }
        v13 = 757;
        v1 = 757;
        if ( v11 == &WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 0x40) == 0 || *((_BYTE *)v11 + 25) < 2u )
          goto LABEL_88;
        v14 = 42;
LABEL_80:
        WPP_SF_d(v11[2], v14, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v13);
        goto LABEL_88;
      }
    }
    v10 = 1;
  }
  v13 = 757;
  v1 = 757;
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x40) != 0 && *((_BYTE *)v11 + 25) >= 2u )
  {
    v14 = 40;
    goto LABEL_80;
  }
LABEL_88:
  CloseServiceHandle(v9);
  v17 = (PVOID *)WPP_GLOBAL_Control;
LABEL_89:
  if ( v5 )
  {
    CloseServiceHandle(v5);
LABEL_91:
    v17 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 0x40) != 0 && *((_BYTE *)v17 + 25) >= 6u )
    WPP_SF_d(v17[2], 47, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x180020d30  push    rbx
0x180020d32  push    rbp
0x180020d33  push    rdi
0x180020d34  push    r12
0x180020d36  push    r13
0x180020d38  push    r14
0x180020d3a  sub     rsp, 58h
0x180020d3e  mov     rax, cs:__security_cookie
0x180020d45  xor     rax, rsp
0x180020d48  mov     [rsp+88h+var_40], rax
0x180020d4d  mov     rbx, cs:WPP_GLOBAL_Control
0x180020d54  lea     r13, WPP_GLOBAL_Control
0x180020d5b  mov     r12b, 40h ; '@'
0x180020d5e  cmp     rbx, r13
0x180020d61  jz      short loc_180020D8B
0x180020d63  test    [rbx+1Ch], r12b
0x180020d67  jz      short loc_180020D8B
0x180020d69  cmp     byte ptr [rbx+19h], 6
0x180020d6d  jb      short loc_180020D8B
0x180020d6f  mov     rcx, [rbx+10h]
0x180020d73  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180020d7a  mov     edx, 20h ; ' '
0x180020d7f  call    WPP_SF_
0x180020d84  mov     rbx, cs:WPP_GLOBAL_Control
0x180020d8b  xorps   xmm0, xmm0
0x180020d8e  xor     eax, eax
0x180020d90  xor     edi, edi
0x180020d92  cmp     cs:g_fRasAutoStarted, eax
0x180020d98  movups  xmmword ptr [rsp+88h+ServiceStatus.dwServiceType], xmm0
0x180020d9d  movups  xmmword ptr [rsp+88h+ServiceStatus.dwWin32ExitCode], xmm0
0x180020da2  jz      short loc_180020DEB
0x180020da4  cmp     rbx, r13
0x180020da7  jz      short loc_180020DDA
0x180020da9  test    [rbx+1Ch], r12b
0x180020dad  jz      short loc_180020DDA
0x180020daf  cmp     byte ptr [rbx+19h], 5
0x180020db3  jb      short loc_180020DDA
0x180020db5  mov     rbx, [rbx+10h]
0x180020db9  call    cs:__imp_GetCurrentProcessId
0x180020dc0  nop     dword ptr [rax+rax+00h]
0x180020dc5  lea     edx, [rdi+21h]
0x180020dc8  mov     r9d, eax
0x180020dcb  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180020dd2  mov     rcx, rbx
0x180020dd5  call    WPP_SF_d
0x180020dda  call    cs:__imp_GetCurrentProcessId
0x180020de1  nop     dword ptr [rax+rax+00h]
0x180020de6  jmp     loc_1800211E6
0x180020deb  lea     rcx, [rsp+88h+var_68]
0x180020df0  mov     [rsp+88h+var_68], eax
0x180020df4  call    GetComputerSuiteMask
0x180020df9  test    eax, eax
0x180020dfb  jnz     short loc_180020E07
0x180020dfd  test    [rsp+88h+var_68], 200h
0x180020e05  jnz     short loc_180020E52
0x180020e07  cmp     cs:dword_180031950, edi
0x180020e0d  jnz     short loc_180020E18
0x180020e0f  call    LoadSkuAndRole
0x180020e14  test    eax, eax
0x180020e16  jnz     short loc_180020E20
0x180020e18  cmp     cs:dword_180031924, edi
0x180020e1e  jz      short loc_180020E52
0x180020e20  mov     rbx, cs:WPP_GLOBAL_Control
0x180020e27  cmp     rbx, r13
0x180020e2a  jz      short loc_180020DDA
0x180020e2c  test    [rbx+1Ch], r12b
0x180020e30  jz      short loc_180020DDA
0x180020e32  cmp     byte ptr [rbx+19h], 5
0x180020e36  jb      short loc_180020DDA
0x180020e38  mov     rbx, [rbx+10h]
0x180020e3c  call    cs:__imp_GetCurrentProcessId
0x180020e43  nop     dword ptr [rax+rax+00h]
0x180020e48  mov     edx, 22h ; '"'
0x180020e4d  jmp     loc_180020DC8
0x180020e52  mov     rbx, cs:WPP_GLOBAL_Control
0x180020e59  xor     ebp, ebp
0x180020e5b  cmp     rbx, r13
0x180020e5e  jz      short loc_180020E91
0x180020e60  test    [rbx+1Ch], r12b
0x180020e64  jz      short loc_180020E91
0x180020e66  cmp     byte ptr [rbx+19h], 5
0x180020e6a  jb      short loc_180020E91
0x180020e6c  mov     rbx, [rbx+10h]
0x180020e70  call    cs:__imp_GetCurrentProcessId
0x180020e77  nop     dword ptr [rax+rax+00h]
0x180020e7c  lea     edx, [rbp+23h]
0x180020e7f  mov     rcx, rbx
0x180020e82  mov     r9d, eax
0x180020e85  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180020e8c  call    WPP_SF_d
0x180020e91  call    cs:__imp_GetCurrentProcessId
0x180020e98  nop     dword ptr [rax+rax+00h]
0x180020e9d  xor     edx, edx; lpDatabaseName
0x180020e9f  xor     ecx, ecx; lpMachineName
0x180020ea1  lea     r8d, [rdx+1]; dwDesiredAccess
0x180020ea5  call    cs:__imp_OpenSCManagerA
0x180020eac  nop     dword ptr [rax+rax+00h]
0x180020eb1  mov     r14, rax
0x180020eb4  test    rax, rax
0x180020eb7  jz      loc_18002116E
0x180020ebd  xor     ebx, ebx
0x180020ebf  lea     rdx, aRasauto; "RasAuto"
0x180020ec6  mov     rcx, rax; hSCManager
0x180020ec9  lea     r8d, [rbx+14h]; dwDesiredAccess
0x180020ecd  call    cs:__imp_OpenServiceA
0x180020ed4  nop     dword ptr [rax+rax+00h]
0x180020ed9  mov     rbp, rax
0x180020edc  test    rax, rax
0x180020edf  jz      loc_18002116E
0x180020ee5  lea     rdx, [rsp+88h+ServiceStatus]; lpServiceStatus
0x180020eea  mov     rcx, rbp; hService
0x180020eed  call    cs:__imp_QueryServiceStatus
0x180020ef4  nop     dword ptr [rax+rax+00h]
0x180020ef9  test    eax, eax
0x180020efb  jz      loc_180021126
0x180020f01  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f08  cmp     rcx, r13
0x180020f0b  jz      short loc_180020F3A
0x180020f0d  test    [rcx+1Ch], r12b
0x180020f11  jz      short loc_180020F3A
0x180020f13  cmp     byte ptr [rcx+19h], 5
0x180020f17  jb      short loc_180020F3A
0x180020f19  mov     r9d, [rsp+88h+ServiceStatus.dwCurrentState]
0x180020f1e  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180020f25  mov     rcx, [rcx+10h]
0x180020f29  mov     edx, 26h ; '&'
0x180020f2e  call    WPP_SF_d
0x180020f33  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f3a  mov     eax, [rsp+88h+ServiceStatus.dwCurrentState]
0x180020f3e  sub     eax, 1
0x180020f41  jz      short loc_180020F86
0x180020f43  sub     eax, 1
0x180020f46  jnz     loc_180020FFE
0x180020f4c  cmp     rcx, r13
0x180020f4f  jz      short loc_180020F70
0x180020f51  test    [rcx+1Ch], r12b
0x180020f55  jz      short loc_180020F70
0x180020f57  cmp     byte ptr [rcx+19h], 5
0x180020f5b  jb      short loc_180020F70
0x180020f5d  mov     rcx, [rcx+10h]
0x180020f61  lea     edx, [rax+2Bh]
0x180020f64  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180020f6b  call    WPP_SF_
0x180020f70  mov     ecx, 1F4h; dwMilliseconds
0x180020f75  call    cs:__imp_Sleep
0x180020f7c  nop     dword ptr [rax+rax+00h]
0x180020f81  jmp     loc_180020EE5
0x180020f86  cmp     rcx, r13
0x180020f89  jz      short loc_180020FB3
0x180020f8b  test    [rcx+1Ch], r12b
0x180020f8f  jz      short loc_180020FB3
0x180020f91  cmp     byte ptr [rcx+19h], 5
0x180020f95  jb      short loc_180020FB3
0x180020f97  mov     rcx, [rcx+10h]
0x180020f9b  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180020fa2  mov     edx, 27h ; '''
0x180020fa7  call    WPP_SF_
0x180020fac  mov     rcx, cs:WPP_GLOBAL_Control
0x180020fb3  test    ebx, ebx
0x180020fb5  jnz     loc_1800210F9
0x180020fbb  xor     r8d, r8d; lpServiceArgVectors
0x180020fbe  xor     edx, edx; dwNumServiceArgs
0x180020fc0  mov     rcx, rbp; hService
0x180020fc3  call    cs:__imp_StartServiceA
0x180020fca  nop     dword ptr [rax+rax+00h]
0x180020fcf  test    eax, eax
0x180020fd1  jnz     short loc_180020FF4
0x180020fd3  call    cs:__imp_GetLastError
0x180020fda  nop     dword ptr [rax+rax+00h]
0x180020fdf  mov     edi, eax
0x180020fe1  cmp     eax, 420h
0x180020fe6  jnz     short loc_180020FEC
0x180020fe8  xor     edi, edi
0x180020fea  jmp     short loc_180020FF4
0x180020fec  test    eax, eax
0x180020fee  jnz     loc_180021095
0x180020ff4  mov     ebx, 1
0x180020ff9  jmp     loc_180020EE5
0x180020ffe  cmp     eax, 2
0x180021001  jz      short loc_180021060
0x180021003  cmp     rcx, r13
0x180021006  jz      short loc_180021030
0x180021008  test    [rcx+1Ch], r12b
0x18002100c  jz      short loc_180021030
0x18002100e  cmp     byte ptr [rcx+19h], 5
0x180021012  jb      short loc_180021030
0x180021014  mov     rcx, [rcx+10h]
0x180021018  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18002101f  mov     edx, 2Dh ; '-'
0x180021024  call    WPP_SF_
0x180021029  mov     rcx, cs:WPP_GLOBAL_Control
0x180021030  mov     r9d, 2F5h
0x180021036  mov     edi, r9d
0x180021039  cmp     rcx, r13
0x18002103c  jz      loc_1800211BC
0x180021042  test    [rcx+1Ch], r12b
0x180021046  jz      loc_1800211BC
0x18002104c  cmp     byte ptr [rcx+19h], 2
0x180021050  jb      loc_1800211BC
0x180021056  mov     edx, 2Eh ; '.'
0x18002105b  jmp     loc_18002115C
0x180021060  cmp     rcx, r13
0x180021063  jz      short loc_180021086
0x180021065  test    [rcx+1Ch], r12b
0x180021069  jz      short loc_180021086
0x18002106b  cmp     byte ptr [rcx+19h], 5
0x18002106f  jb      short loc_180021086
0x180021071  mov     rcx, [rcx+10h]
0x180021075  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18002107c  mov     edx, 2Ch ; ','
0x180021081  call    WPP_SF_
0x180021086  mov     cs:g_fRasAutoStarted, 1
0x180021090  jmp     loc_1800211BC
0x180021095  mov     rcx, cs:WPP_GLOBAL_Control
0x18002109c  cmp     rcx, r13
0x18002109f  jz      short loc_1800210CC
0x1800210a1  test    [rcx+1Ch], r12b
0x1800210a5  jz      short loc_1800210CC
0x1800210a7  cmp     byte ptr [rcx+19h], 2
0x1800210ab  jb      short loc_1800210CC
0x1800210ad  mov     rcx, [rcx+10h]
0x1800210b1  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800210b8  mov     edx, 29h ; ')'
0x1800210bd  mov     r9d, eax
0x1800210c0  call    WPP_SF_d
0x1800210c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800210cc  mov     r9d, 2F5h
0x1800210d2  mov     edi, r9d
0x1800210d5  cmp     rcx, r13
0x1800210d8  jz      loc_1800211BC
0x1800210de  test    [rcx+1Ch], r12b
0x1800210e2  jz      loc_1800211BC
0x1800210e8  cmp     byte ptr [rcx+19h], 2
0x1800210ec  jb      loc_1800211BC
0x1800210f2  mov     edx, 2Ah ; '*'
0x1800210f7  jmp     short loc_18002115C
0x1800210f9  mov     r9d, 2F5h
0x1800210ff  mov     edi, r9d
0x180021102  cmp     rcx, r13
0x180021105  jz      loc_1800211BC
0x18002110b  test    [rcx+1Ch], r12b
0x18002110f  jz      loc_1800211BC
0x180021115  cmp     byte ptr [rcx+19h], 2
0x180021119  jb      loc_1800211BC
0x18002111f  mov     edx, 28h ; '('
0x180021124  jmp     short loc_18002115C
0x180021126  call    cs:__imp_GetLastError
0x18002112d  nop     dword ptr [rax+rax+00h]
0x180021132  mov     edi, eax
0x180021134  test    eax, eax
0x180021136  jz      loc_1800211BC
0x18002113c  mov     rcx, cs:WPP_GLOBAL_Control
0x180021143  cmp     rcx, r13
0x180021146  jz      short loc_1800211BC
0x180021148  test    [rcx+1Ch], r12b
0x18002114c  jz      short loc_1800211BC
0x18002114e  cmp     byte ptr [rcx+19h], 2
0x180021152  jb      short loc_1800211BC
0x180021154  mov     edx, 25h ; '%'
0x180021159  mov     r9d, eax
0x18002115c  mov     rcx, [rcx+10h]
0x180021160  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180021167  call    WPP_SF_d
0x18002116c  jmp     short loc_1800211BC
0x18002116e  call    cs:__imp_GetLastError
0x180021175  nop     dword ptr [rax+rax+00h]
0x18002117a  mov     edi, eax
0x18002117c  test    eax, eax
0x18002117e  jz      short loc_1800211B0
0x180021180  mov     rcx, cs:WPP_GLOBAL_Control
0x180021187  cmp     rcx, r13
0x18002118a  jz      short loc_1800211B7
0x18002118c  test    [rcx+1Ch], r12b
0x180021190  jz      short loc_1800211B7
0x180021192  cmp     byte ptr [rcx+19h], 2
0x180021196  jb      short loc_1800211B7
0x180021198  mov     rcx, [rcx+10h]
0x18002119c  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800211a3  mov     edx, 24h ; '$'
0x1800211a8  mov     r9d, eax
0x1800211ab  call    WPP_SF_d
0x1800211b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800211b7  test    r14, r14
0x1800211ba  jz      short loc_1800211D2
0x1800211bc  mov     rcx, r14; hSCObject
0x1800211bf  call    cs:__imp_CloseServiceHandle
0x1800211c6  nop     dword ptr [rax+rax+00h]
0x1800211cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800211d2  test    rbp, rbp
0x1800211d5  jz      short loc_1800211ED
0x1800211d7  mov     rcx, rbp; hSCObject
0x1800211da  call    cs:__imp_CloseServiceHandle
0x1800211e1  nop     dword ptr [rax+rax+00h]
0x1800211e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800211ed  cmp     rcx, r13
0x1800211f0  jz      short loc_180021216
0x1800211f2  test    [rcx+1Ch], r12b
0x1800211f6  jz      short loc_180021216
0x1800211f8  cmp     byte ptr [rcx+19h], 6
0x1800211fc  jb      short loc_180021216
  ... truncated ...
```
