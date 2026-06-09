# RasStartRasAutoIfRequired

- ea: `0x1800202a0`
- end: `0x180020742`
- name: `RasStartRasAutoIfRequired`
- size: `1186`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800202a0`
- `0x180020fd8`
- `0x180021000`
- `0x180023c30`
- `0x180023c64`
- `0x180026400`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020329`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020344`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800203a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800203cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800203e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020329`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020344`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800203a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800203cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800203e6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800204b2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800204b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020504`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020651`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002068f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020504`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020651`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002068f`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x180020416`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x180020416`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x1800203f4`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x1800203f4`
- `api-ms-win-service-winsvc-l1-1-0!StartServiceA` at `0x1800204fa`
- `api-ms-win-service-winsvc-l1-1-0!StartServiceA` at `0x1800204fa`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180020430`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180020430`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800206da`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800206ef`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800206da`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800206ef`

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
    && (!dword_180030950 && (unsigned int)LoadSkuAndRole() || dword_180030924) )
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
0x1800202a0  push    rbx
0x1800202a2  push    rbp
0x1800202a3  push    rdi
0x1800202a4  push    r12
0x1800202a6  push    r13
0x1800202a8  push    r14
0x1800202aa  sub     rsp, 58h
0x1800202ae  mov     rax, cs:__security_cookie
0x1800202b5  xor     rax, rsp
0x1800202b8  mov     [rsp+88h+var_40], rax
0x1800202bd  mov     rbx, cs:WPP_GLOBAL_Control
0x1800202c4  lea     r13, WPP_GLOBAL_Control
0x1800202cb  mov     r12b, 40h ; '@'
0x1800202ce  cmp     rbx, r13
0x1800202d1  jz      short loc_1800202FB
0x1800202d3  test    [rbx+1Ch], r12b
0x1800202d7  jz      short loc_1800202FB
0x1800202d9  cmp     byte ptr [rbx+19h], 6
0x1800202dd  jb      short loc_1800202FB
0x1800202df  mov     rcx, [rbx+10h]
0x1800202e3  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800202ea  mov     edx, 20h ; ' '
0x1800202ef  call    WPP_SF_
0x1800202f4  mov     rbx, cs:WPP_GLOBAL_Control
0x1800202fb  xorps   xmm0, xmm0
0x1800202fe  xor     eax, eax
0x180020300  xor     edi, edi
0x180020302  cmp     cs:g_fRasAutoStarted, eax
0x180020308  movups  xmmword ptr [rsp+88h+ServiceStatus.dwServiceType], xmm0
0x18002030d  movups  xmmword ptr [rsp+88h+ServiceStatus.dwWin32ExitCode], xmm0
0x180020312  jz      short loc_18002034F
0x180020314  cmp     rbx, r13
0x180020317  jz      short loc_180020344
0x180020319  test    [rbx+1Ch], r12b
0x18002031d  jz      short loc_180020344
0x18002031f  cmp     byte ptr [rbx+19h], 5
0x180020323  jb      short loc_180020344
0x180020325  mov     rbx, [rbx+10h]
0x180020329  call    cs:__imp_GetCurrentProcessId
0x18002032f  lea     edx, [rdi+21h]
0x180020332  mov     r9d, eax
0x180020335  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18002033c  mov     rcx, rbx
0x18002033f  call    WPP_SF_d
0x180020344  call    cs:__imp_GetCurrentProcessId
0x18002034a  jmp     loc_1800206F5
0x18002034f  lea     rcx, [rsp+88h+var_68]
0x180020354  mov     [rsp+88h+var_68], eax
0x180020358  call    GetComputerSuiteMask
0x18002035d  test    eax, eax
0x18002035f  jnz     short loc_18002036B
0x180020361  test    [rsp+88h+var_68], 200h
0x180020369  jnz     short loc_1800203AD
0x18002036b  cmp     cs:dword_180030950, edi
0x180020371  jnz     short loc_18002037C
0x180020373  call    LoadSkuAndRole
0x180020378  test    eax, eax
0x18002037a  jnz     short loc_180020384
0x18002037c  cmp     cs:dword_180030924, edi
0x180020382  jz      short loc_1800203AD
0x180020384  mov     rbx, cs:WPP_GLOBAL_Control
0x18002038b  cmp     rbx, r13
0x18002038e  jz      short loc_180020344
0x180020390  test    [rbx+1Ch], r12b
0x180020394  jz      short loc_180020344
0x180020396  cmp     byte ptr [rbx+19h], 5
0x18002039a  jb      short loc_180020344
0x18002039c  mov     rbx, [rbx+10h]
0x1800203a0  call    cs:__imp_GetCurrentProcessId
0x1800203a6  mov     edx, 22h ; '"'
0x1800203ab  jmp     short loc_180020332
0x1800203ad  mov     rbx, cs:WPP_GLOBAL_Control
0x1800203b4  xor     ebp, ebp
0x1800203b6  cmp     rbx, r13
0x1800203b9  jz      short loc_1800203E6
0x1800203bb  test    [rbx+1Ch], r12b
0x1800203bf  jz      short loc_1800203E6
0x1800203c1  cmp     byte ptr [rbx+19h], 5
0x1800203c5  jb      short loc_1800203E6
0x1800203c7  mov     rbx, [rbx+10h]
0x1800203cb  call    cs:__imp_GetCurrentProcessId
0x1800203d1  lea     edx, [rbp+23h]
0x1800203d4  mov     rcx, rbx
0x1800203d7  mov     r9d, eax
0x1800203da  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800203e1  call    WPP_SF_d
0x1800203e6  call    cs:__imp_GetCurrentProcessId
0x1800203ec  xor     edx, edx; lpDatabaseName
0x1800203ee  xor     ecx, ecx; lpMachineName
0x1800203f0  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800203f4  call    cs:__imp_OpenSCManagerA
0x1800203fa  mov     r14, rax
0x1800203fd  test    rax, rax
0x180020400  jz      loc_18002068F
0x180020406  xor     ebx, ebx
0x180020408  lea     rdx, aRasauto; "RasAuto"
0x18002040f  mov     rcx, rax; hSCManager
0x180020412  lea     r8d, [rbx+14h]; dwDesiredAccess
0x180020416  call    cs:__imp_OpenServiceA
0x18002041c  mov     rbp, rax
0x18002041f  test    rax, rax
0x180020422  jz      loc_18002068F
0x180020428  lea     rdx, [rsp+88h+ServiceStatus]; lpServiceStatus
0x18002042d  mov     rcx, rbp; hService
0x180020430  call    cs:__imp_QueryServiceStatus
0x180020436  test    eax, eax
0x180020438  jz      loc_180020651
0x18002043e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020445  cmp     rcx, r13
0x180020448  jz      short loc_180020477
0x18002044a  test    [rcx+1Ch], r12b
0x18002044e  jz      short loc_180020477
0x180020450  cmp     byte ptr [rcx+19h], 5
0x180020454  jb      short loc_180020477
0x180020456  mov     r9d, [rsp+88h+ServiceStatus.dwCurrentState]
0x18002045b  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180020462  mov     rcx, [rcx+10h]
0x180020466  mov     edx, 26h ; '&'
0x18002046b  call    WPP_SF_d
0x180020470  mov     rcx, cs:WPP_GLOBAL_Control
0x180020477  mov     eax, [rsp+88h+ServiceStatus.dwCurrentState]
0x18002047b  sub     eax, 1
0x18002047e  jz      short loc_1800204BD
0x180020480  sub     eax, 1
0x180020483  jnz     loc_180020529
0x180020489  cmp     rcx, r13
0x18002048c  jz      short loc_1800204AD
0x18002048e  test    [rcx+1Ch], r12b
0x180020492  jz      short loc_1800204AD
0x180020494  cmp     byte ptr [rcx+19h], 5
0x180020498  jb      short loc_1800204AD
0x18002049a  mov     rcx, [rcx+10h]
0x18002049e  lea     edx, [rax+2Bh]
0x1800204a1  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800204a8  call    WPP_SF_
0x1800204ad  mov     ecx, 1F4h; dwMilliseconds
0x1800204b2  call    cs:__imp_Sleep
0x1800204b8  jmp     loc_180020428
0x1800204bd  cmp     rcx, r13
0x1800204c0  jz      short loc_1800204EA
0x1800204c2  test    [rcx+1Ch], r12b
0x1800204c6  jz      short loc_1800204EA
0x1800204c8  cmp     byte ptr [rcx+19h], 5
0x1800204cc  jb      short loc_1800204EA
0x1800204ce  mov     rcx, [rcx+10h]
0x1800204d2  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800204d9  mov     edx, 27h ; '''
0x1800204de  call    WPP_SF_
0x1800204e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800204ea  test    ebx, ebx
0x1800204ec  jnz     loc_180020624
0x1800204f2  xor     r8d, r8d; lpServiceArgVectors
0x1800204f5  xor     edx, edx; dwNumServiceArgs
0x1800204f7  mov     rcx, rbp; hService
0x1800204fa  call    cs:__imp_StartServiceA
0x180020500  test    eax, eax
0x180020502  jnz     short loc_18002051F
0x180020504  call    cs:__imp_GetLastError
0x18002050a  mov     edi, eax
0x18002050c  cmp     eax, 420h
0x180020511  jnz     short loc_180020517
0x180020513  xor     edi, edi
0x180020515  jmp     short loc_18002051F
0x180020517  test    eax, eax
0x180020519  jnz     loc_1800205C0
0x18002051f  mov     ebx, 1
0x180020524  jmp     loc_180020428
0x180020529  cmp     eax, 2
0x18002052c  jz      short loc_18002058B
0x18002052e  cmp     rcx, r13
0x180020531  jz      short loc_18002055B
0x180020533  test    [rcx+1Ch], r12b
0x180020537  jz      short loc_18002055B
0x180020539  cmp     byte ptr [rcx+19h], 5
0x18002053d  jb      short loc_18002055B
0x18002053f  mov     rcx, [rcx+10h]
0x180020543  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18002054a  mov     edx, 2Dh ; '-'
0x18002054f  call    WPP_SF_
0x180020554  mov     rcx, cs:WPP_GLOBAL_Control
0x18002055b  mov     r9d, 2F5h
0x180020561  mov     edi, r9d
0x180020564  cmp     rcx, r13
0x180020567  jz      loc_1800206D7
0x18002056d  test    [rcx+1Ch], r12b
0x180020571  jz      loc_1800206D7
0x180020577  cmp     byte ptr [rcx+19h], 2
0x18002057b  jb      loc_1800206D7
0x180020581  mov     edx, 2Eh ; '.'
0x180020586  jmp     loc_18002067D
0x18002058b  cmp     rcx, r13
0x18002058e  jz      short loc_1800205B1
0x180020590  test    [rcx+1Ch], r12b
0x180020594  jz      short loc_1800205B1
0x180020596  cmp     byte ptr [rcx+19h], 5
0x18002059a  jb      short loc_1800205B1
0x18002059c  mov     rcx, [rcx+10h]
0x1800205a0  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800205a7  mov     edx, 2Ch ; ','
0x1800205ac  call    WPP_SF_
0x1800205b1  mov     cs:g_fRasAutoStarted, 1
0x1800205bb  jmp     loc_1800206D7
0x1800205c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800205c7  cmp     rcx, r13
0x1800205ca  jz      short loc_1800205F7
0x1800205cc  test    [rcx+1Ch], r12b
0x1800205d0  jz      short loc_1800205F7
0x1800205d2  cmp     byte ptr [rcx+19h], 2
0x1800205d6  jb      short loc_1800205F7
0x1800205d8  mov     rcx, [rcx+10h]
0x1800205dc  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800205e3  mov     edx, 29h ; ')'
0x1800205e8  mov     r9d, eax
0x1800205eb  call    WPP_SF_d
0x1800205f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800205f7  mov     r9d, 2F5h
0x1800205fd  mov     edi, r9d
0x180020600  cmp     rcx, r13
0x180020603  jz      loc_1800206D7
0x180020609  test    [rcx+1Ch], r12b
0x18002060d  jz      loc_1800206D7
0x180020613  cmp     byte ptr [rcx+19h], 2
0x180020617  jb      loc_1800206D7
0x18002061d  mov     edx, 2Ah ; '*'
0x180020622  jmp     short loc_18002067D
0x180020624  mov     r9d, 2F5h
0x18002062a  mov     edi, r9d
0x18002062d  cmp     rcx, r13
0x180020630  jz      loc_1800206D7
0x180020636  test    [rcx+1Ch], r12b
0x18002063a  jz      loc_1800206D7
0x180020640  cmp     byte ptr [rcx+19h], 2
0x180020644  jb      loc_1800206D7
0x18002064a  mov     edx, 28h ; '('
0x18002064f  jmp     short loc_18002067D
0x180020651  call    cs:__imp_GetLastError
0x180020657  mov     edi, eax
0x180020659  test    eax, eax
0x18002065b  jz      short loc_1800206D7
0x18002065d  mov     rcx, cs:WPP_GLOBAL_Control
0x180020664  cmp     rcx, r13
0x180020667  jz      short loc_1800206D7
0x180020669  test    [rcx+1Ch], r12b
0x18002066d  jz      short loc_1800206D7
0x18002066f  cmp     byte ptr [rcx+19h], 2
0x180020673  jb      short loc_1800206D7
0x180020675  mov     edx, 25h ; '%'
0x18002067a  mov     r9d, eax
0x18002067d  mov     rcx, [rcx+10h]
0x180020681  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180020688  call    WPP_SF_d
0x18002068d  jmp     short loc_1800206D7
0x18002068f  call    cs:__imp_GetLastError
0x180020695  mov     edi, eax
0x180020697  test    eax, eax
0x180020699  jz      short loc_1800206CB
0x18002069b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800206a2  cmp     rcx, r13
0x1800206a5  jz      short loc_1800206D2
0x1800206a7  test    [rcx+1Ch], r12b
0x1800206ab  jz      short loc_1800206D2
0x1800206ad  cmp     byte ptr [rcx+19h], 2
0x1800206b1  jb      short loc_1800206D2
0x1800206b3  mov     rcx, [rcx+10h]
0x1800206b7  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800206be  mov     edx, 24h ; '$'
0x1800206c3  mov     r9d, eax
0x1800206c6  call    WPP_SF_d
0x1800206cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800206d2  test    r14, r14
0x1800206d5  jz      short loc_1800206E7
0x1800206d7  mov     rcx, r14; hSCObject
0x1800206da  call    cs:__imp_CloseServiceHandle
0x1800206e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800206e7  test    rbp, rbp
0x1800206ea  jz      short loc_1800206FC
0x1800206ec  mov     rcx, rbp; hSCObject
0x1800206ef  call    cs:__imp_CloseServiceHandle
0x1800206f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800206fc  cmp     rcx, r13
0x1800206ff  jz      short loc_180020725
0x180020701  test    [rcx+1Ch], r12b
0x180020705  jz      short loc_180020725
0x180020707  cmp     byte ptr [rcx+19h], 6
0x18002070b  jb      short loc_180020725
0x18002070d  mov     rcx, [rcx+10h]
0x180020711  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180020718  mov     edx, 2Fh ; '/'
0x18002071d  mov     r9d, edi
0x180020720  call    WPP_SF_d
0x180020725  mov     eax, edi
0x180020727  mov     rcx, [rsp+88h+var_40]
0x18002072c  xor     rcx, rsp; StackCookie
0x18002072f  call    __security_check_cookie
0x180020734  add     rsp, 58h
0x180020738  pop     r14
0x18002073a  pop     r13
0x18002073c  pop     r12
0x18002073e  pop     rdi
0x18002073f  pop     rbp
  ... truncated ...
```
