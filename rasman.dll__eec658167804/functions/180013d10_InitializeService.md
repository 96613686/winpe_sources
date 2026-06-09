# InitializeService

- ea: `0x180013d10`
- end: `0x1800141cf`
- name: `InitializeService`
- size: `1215`
- prototype: `DWORD __fastcall(SC_HANDLE hSCManager, LPCSTR lpServiceName, unsigned int, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b010`

## callees

- `0x180013d10`
- `0x180020fd8`
- `0x180021000`
- `0x180021c3c`
- `0x180026400`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180013f0d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180013f0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ea6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800140a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ea6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800140a3`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x180013d8b`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x180013d8b`
- `api-ms-win-service-winsvc-l1-1-0!StartServiceA` at `0x180014099`
- `api-ms-win-service-winsvc-l1-1-0!StartServiceA` at `0x180014099`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180013dc1`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180013dc1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180013ded`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180013ded`
- `rtutils!TracePrintfExA` at `0x180013d79`
- `rtutils!TracePrintfExA` at `0x180013fc4`
- `rtutils!TracePrintfExA` at `0x18001408b`
- `rtutils!TracePrintfExA` at `0x1800140c5`
- `rtutils!TracePrintfExA` at `0x180014134`
- `rtutils!TracePrintfExA` at `0x180014183`
- `rtutils!TracePrintfExA` at `0x180013d79`
- `rtutils!TracePrintfExA` at `0x180013fc4`
- `rtutils!TracePrintfExA` at `0x18001408b`
- `rtutils!TracePrintfExA` at `0x1800140c5`
- `rtutils!TracePrintfExA` at `0x180014134`
- `rtutils!TracePrintfExA` at `0x180014183`

## string_xrefs

- `0x180013d6d`: `InitializeService: Initializing %s service\n`
- `0x180014128`: `InitializeService: SERVICE_STOPPED!\n`
- `0x18001407f`: `InitializeService: Starting the service`
- `0x1800140b9`: `InitializeService: StartService returned 0x%x\n`
- `0x180013fb6`: `InitializeService: Invalid service.status=%d\n`
- `0x180014175`: `InitializeService: service is not coming out of START PENDING state\n`

## pseudocode

```c
DWORD __fastcall InitializeService(SC_HANDLE hSCManager, LPCSTR lpServiceName, unsigned int a3, _DWORD *a4)
{
  SC_HANDLE v8; // rbx
  PVOID *v9; // rcx
  unsigned int v10; // edi
  unsigned int i; // ebp
  DWORD dwCurrentState; // r9d
  PVOID *v13; // rcx
  DWORD result; // eax
  const char *v15; // r9
  DWORD LastError; // eax
  __int64 v17; // rdx
  __int64 v18; // r9
  DWORD v19; // eax
  struct _SERVICE_STATUS ServiceStatus; // [rsp+30h] [rbp-58h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LODWORD(v15) = (_DWORD)lpServiceName;
    if ( !lpServiceName )
      v15 = "<NULL>";
    WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)lpServiceName, a3, (_DWORD)v15, a3);
  }
  *a4 = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "InitializeService: Initializing %s service\n", lpServiceName);
  v8 = OpenServiceA(hSCManager, lpServiceName, 0x14u);
  if ( v8 )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    v10 = 0;
    for ( i = 0; ; ++i )
    {
      if ( i >= a3 )
      {
        if ( g_dwTraceId != -1 )
        {
          TracePrintfExA(g_dwTraceId, 0xCu, "InitializeService: service is not coming out of START PENDING state\n");
          v9 = (PVOID *)WPP_GLOBAL_Control;
        }
        v10 = 1070;
        if ( v9 == &WPP_GLOBAL_Control || (*((_BYTE *)v9 + 28) & 0x40) == 0 || *((_BYTE *)v9 + 25) < 2u )
          goto LABEL_10;
        v17 = 77;
LABEL_85:
        v18 = v10;
LABEL_86:
        WPP_SF_d(v9[2], v17, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v18);
        goto LABEL_10;
      }
      if ( !QueryServiceStatus(v8, &ServiceStatus) )
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( !LastError )
          goto LABEL_10;
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_10;
        }
        v17 = 69;
        v18 = LastError;
        goto LABEL_86;
      }
      dwCurrentState = ServiceStatus.dwCurrentState;
      if ( ServiceStatus.dwCurrentState == 4 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
        }
        goto LABEL_10;
      }
      if ( ServiceStatus.dwCurrentState == 1 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
        }
        if ( *a4 )
        {
          *a4 = 0;
          if ( g_dwTraceId != -1 )
            TracePrintfExA(g_dwTraceId, 0xCu, "InitializeService: SERVICE_STOPPED!\n");
          v10 = 1062;
          v9 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_10;
          }
          v17 = 71;
          goto LABEL_85;
        }
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "InitializeService: Starting the service");
        if ( !StartServiceA(v8, 0, 0) )
        {
          v19 = GetLastError();
          v10 = v19;
          if ( g_dwTraceId != -1 )
            TracePrintfExA(g_dwTraceId, 0xCu, "InitializeService: StartService returned 0x%x\n", v19);
          if ( v10 == 1056 )
          {
            v10 = 0;
            goto LABEL_10;
          }
          if ( v10 )
          {
            v9 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v17 = 72;
              goto LABEL_85;
            }
LABEL_10:
            CloseServiceHandle(v8);
LABEL_11:
            v13 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_12;
          }
        }
        *a4 = 1;
        goto LABEL_35;
      }
      if ( ServiceStatus.dwCurrentState == 2 )
        break;
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
        dwCurrentState = ServiceStatus.dwCurrentState;
        v9 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( g_dwTraceId != -1 )
      {
        TracePrintfExA(g_dwTraceId, 0xCu, "InitializeService: Invalid service.status=%d\n", dwCurrentState);
        v9 = (PVOID *)WPP_GLOBAL_Control;
      }
      v10 = 5023;
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x40) != 0 && *((_BYTE *)v9 + 25) >= 2u )
      {
        WPP_SF_d(v9[2], 76, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 5023);
LABEL_35:
        v9 = (PVOID *)WPP_GLOBAL_Control;
        continue;
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
    }
    Sleep(0x3E8u);
    goto LABEL_35;
  }
  result = GetLastError();
  v10 = result;
  if ( !result )
    goto LABEL_11;
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, result);
      goto LABEL_11;
    }
LABEL_12:
    if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 0x40) != 0 && *((_BYTE *)v13 + 25) >= 6u )
      WPP_SF_d(v13[2], 78, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v10);
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x180013d10  push    rbx
0x180013d12  push    rsi
0x180013d13  push    rdi
0x180013d14  push    r14
0x180013d16  push    r15
0x180013d18  sub     rsp, 60h
0x180013d1c  mov     rax, cs:__security_cookie
0x180013d23  xor     rax, rsp
0x180013d26  mov     [rsp+88h+var_38], rax
0x180013d2b  mov     rsi, r9
0x180013d2e  mov     r14d, r8d
0x180013d31  mov     rbx, rdx
0x180013d34  mov     rdi, rcx
0x180013d37  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d3e  lea     r15, WPP_GLOBAL_Control
0x180013d45  cmp     rcx, r15
0x180013d48  jnz     loc_180013E6E
0x180013d4e  xor     eax, eax
0x180013d50  xorps   xmm0, xmm0
0x180013d53  mov     [rsi], eax
0x180013d55  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180013d5b  movups  xmmword ptr [rsp+88h+ServiceStatus.dwServiceType], xmm0
0x180013d60  movups  xmmword ptr [rsp+88h+ServiceStatus.dwWin32ExitCode], xmm0
0x180013d65  cmp     ecx, 0FFFFFFFFh
0x180013d68  jz      short loc_180013D7F
0x180013d6a  mov     r9, rbx
0x180013d6d  lea     r8, aInitializeserv_4; "InitializeService: Initializing %s serv"...
0x180013d74  mov     edx, 0Ch; dwFlags
0x180013d79  call    cs:__imp_TracePrintfExA
0x180013d7f  mov     r8d, 14h; dwDesiredAccess
0x180013d85  mov     rdx, rbx; lpServiceName
0x180013d88  mov     rcx, rdi; hSCManager
0x180013d8b  call    cs:__imp_OpenServiceA
0x180013d91  mov     rbx, rax
0x180013d94  test    rax, rax
0x180013d97  jz      loc_180013F21
0x180013d9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013da4  xor     edi, edi
0x180013da6  mov     [rsp+88h+arg_10], rbp
0x180013dae  xor     ebp, ebp
0x180013db0  cmp     ebp, r14d
0x180013db3  jnb     loc_18001416A
0x180013db9  lea     rdx, [rsp+88h+ServiceStatus]; lpServiceStatus
0x180013dbe  mov     rcx, rbx; hService
0x180013dc1  call    cs:__imp_QueryServiceStatus
0x180013dc7  test    eax, eax
0x180013dc9  jz      loc_180013EA6
0x180013dcf  mov     r9d, [rsp+88h+ServiceStatus.dwCurrentState]
0x180013dd4  cmp     r9d, 4
0x180013dd8  jnz     loc_180013EE7
0x180013dde  mov     rcx, cs:WPP_GLOBAL_Control
0x180013de5  cmp     rcx, r15
0x180013de8  jnz     short loc_180013E48
0x180013dea  mov     rcx, rbx; hSCObject
0x180013ded  call    cs:__imp_CloseServiceHandle
0x180013df3  mov     rbp, [rsp+88h+arg_10]
0x180013dfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e02  cmp     rcx, r15
0x180013e05  jnz     short loc_180013E22
0x180013e07  mov     eax, edi
0x180013e09  mov     rcx, [rsp+88h+var_38]
0x180013e0e  xor     rcx, rsp; StackCookie
0x180013e11  call    __security_check_cookie
0x180013e16  add     rsp, 60h
0x180013e1a  pop     r15
0x180013e1c  pop     r14
0x180013e1e  pop     rdi
0x180013e1f  pop     rsi
0x180013e20  pop     rbx
0x180013e21  retn
0x180013e22  test    byte ptr [rcx+1Ch], 40h
0x180013e26  jz      short loc_180013E07
0x180013e28  cmp     byte ptr [rcx+19h], 6
0x180013e2c  jb      short loc_180013E07
0x180013e2e  mov     rcx, [rcx+10h]
0x180013e32  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180013e39  mov     edx, 4Eh ; 'N'
0x180013e3e  mov     r9d, edi
0x180013e41  call    WPP_SF_d
0x180013e46  jmp     short loc_180013E07
0x180013e48  test    byte ptr [rcx+1Ch], 40h
0x180013e4c  jz      short loc_180013DEA
0x180013e4e  cmp     byte ptr [rcx+19h], 5
0x180013e52  jb      short loc_180013DEA
0x180013e54  mov     rcx, [rcx+10h]
0x180013e58  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180013e5f  mov     edx, 4Ah ; 'J'
0x180013e64  call    WPP_SF_
0x180013e69  jmp     loc_180013DEA
0x180013e6e  test    byte ptr [rcx+1Ch], 40h
0x180013e72  jz      loc_180013D4E
0x180013e78  cmp     byte ptr [rcx+19h], 6
0x180013e7c  jb      loc_180013D4E
0x180013e82  mov     rcx, [rcx+10h]
0x180013e86  lea     rax, aNull; "<NULL>"
0x180013e8d  test    rbx, rbx
0x180013e90  mov     [rsp+88h+var_68], r14d
0x180013e95  mov     r9, rbx
0x180013e98  cmovz   r9, rax
0x180013e9c  call    WPP_SF_sd
0x180013ea1  jmp     loc_180013D4E
0x180013ea6  call    cs:__imp_GetLastError
0x180013eac  mov     edi, eax
0x180013eae  test    eax, eax
0x180013eb0  jz      loc_180013DEA
0x180013eb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ebd  cmp     rcx, r15
0x180013ec0  jz      loc_180013DEA
0x180013ec6  test    byte ptr [rcx+1Ch], 40h
0x180013eca  jz      loc_180013DEA
0x180013ed0  cmp     byte ptr [rcx+19h], 2
0x180013ed4  jb      loc_180013DEA
0x180013eda  mov     edx, 45h ; 'E'
0x180013edf  mov     r9d, eax
0x180013ee2  jmp     loc_1800141BA
0x180013ee7  mov     eax, r9d
0x180013eea  sub     eax, 1
0x180013eed  jz      loc_18001403E
0x180013ef3  cmp     eax, 1
0x180013ef6  jnz     short loc_180013F72
0x180013ef8  mov     rcx, cs:WPP_GLOBAL_Control
0x180013eff  cmp     rcx, r15
0x180013f02  jnz     loc_180014010
0x180013f08  mov     ecx, 3E8h; dwMilliseconds
0x180013f0d  call    cs:__imp_Sleep
0x180013f13  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f1a  inc     ebp
0x180013f1c  jmp     loc_180013DB0
0x180013f21  call    cs:__imp_GetLastError
0x180013f27  mov     edi, eax
0x180013f29  test    eax, eax
0x180013f2b  jz      loc_180013DFB
0x180013f31  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f38  cmp     rcx, r15
0x180013f3b  jz      loc_180013E09
0x180013f41  test    byte ptr [rcx+1Ch], 40h
0x180013f45  jz      loc_180013E02
0x180013f4b  cmp     byte ptr [rcx+19h], 2
0x180013f4f  jb      loc_180013E02
0x180013f55  mov     rcx, [rcx+10h]
0x180013f59  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180013f60  mov     edx, 44h ; 'D'
0x180013f65  mov     r9d, eax
0x180013f68  call    WPP_SF_d
0x180013f6d  jmp     loc_180013DFB
0x180013f72  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f79  cmp     rcx, r15
0x180013f7c  jz      short loc_180013FAB
0x180013f7e  test    byte ptr [rcx+1Ch], 40h
0x180013f82  jz      short loc_180013FAB
0x180013f84  cmp     byte ptr [rcx+19h], 5
0x180013f88  jb      short loc_180013FAB
0x180013f8a  mov     rcx, [rcx+10h]
0x180013f8e  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180013f95  mov     edx, 4Bh ; 'K'
0x180013f9a  call    WPP_SF_
0x180013f9f  mov     r9d, [rsp+88h+ServiceStatus.dwCurrentState]
0x180013fa4  mov     rcx, cs:WPP_GLOBAL_Control
0x180013fab  mov     eax, cs:g_dwTraceId
0x180013fb1  cmp     eax, 0FFFFFFFFh
0x180013fb4  jz      short loc_180013FD1
0x180013fb6  lea     r8, aInitializeserv_2; "InitializeService: Invalid service.stat"...
0x180013fbd  mov     edx, 0Ch; dwFlags
0x180013fc2  mov     ecx, eax; dwTraceID
0x180013fc4  call    cs:__imp_TracePrintfExA
0x180013fca  mov     rcx, cs:WPP_GLOBAL_Control
0x180013fd1  mov     edi, 139Fh
0x180013fd6  cmp     rcx, r15
0x180013fd9  jz      loc_180013F1A
0x180013fdf  test    byte ptr [rcx+1Ch], 40h
0x180013fe3  jz      loc_180013F1A
0x180013fe9  cmp     byte ptr [rcx+19h], 2
0x180013fed  jb      loc_180013F1A
0x180013ff3  mov     rcx, [rcx+10h]
0x180013ff7  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180013ffe  mov     edx, 4Ch ; 'L'
0x180014003  mov     r9d, edi
0x180014006  call    WPP_SF_d
0x18001400b  jmp     loc_180013F13
0x180014010  test    byte ptr [rcx+1Ch], 40h
0x180014014  jz      loc_180013F08
0x18001401a  cmp     byte ptr [rcx+19h], 5
0x18001401e  jb      loc_180013F08
0x180014024  mov     rcx, [rcx+10h]
0x180014028  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001402f  mov     edx, 49h ; 'I'
0x180014034  call    WPP_SF_
0x180014039  jmp     loc_180013F08
0x18001403e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014045  cmp     rcx, r15
0x180014048  jz      short loc_18001406B
0x18001404a  test    byte ptr [rcx+1Ch], 40h
0x18001404e  jz      short loc_18001406B
0x180014050  cmp     byte ptr [rcx+19h], 5
0x180014054  jb      short loc_18001406B
0x180014056  mov     rcx, [rcx+10h]
0x18001405a  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180014061  mov     edx, 46h ; 'F'
0x180014066  call    WPP_SF_
0x18001406b  cmp     dword ptr [rsi], 0
0x18001406e  jnz     loc_180014117
0x180014074  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001407a  cmp     ecx, 0FFFFFFFFh
0x18001407d  jz      short loc_180014091
0x18001407f  lea     r8, aInitializeserv_0; "InitializeService: Starting the service"
0x180014086  mov     edx, 0Ch; dwFlags
0x18001408b  call    cs:__imp_TracePrintfExA
0x180014091  xor     r8d, r8d; lpServiceArgVectors
0x180014094  xor     edx, edx; dwNumServiceArgs
0x180014096  mov     rcx, rbx; hService
0x180014099  call    cs:__imp_StartServiceA
0x18001409f  test    eax, eax
0x1800140a1  jnz     short loc_180014105
0x1800140a3  call    cs:__imp_GetLastError
0x1800140a9  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800140af  mov     edi, eax
0x1800140b1  cmp     ecx, 0FFFFFFFFh
0x1800140b4  jz      short loc_1800140CB
0x1800140b6  mov     r9d, eax
0x1800140b9  lea     r8, aInitializeserv_1; "InitializeService: StartService returne"...
0x1800140c0  mov     edx, 0Ch; dwFlags
0x1800140c5  call    cs:__imp_TracePrintfExA
0x1800140cb  cmp     edi, 420h
0x1800140d1  jz      short loc_180014110
0x1800140d3  test    edi, edi
0x1800140d5  jz      short loc_180014105
0x1800140d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800140de  cmp     rcx, r15
0x1800140e1  jz      loc_180013DEA
0x1800140e7  test    byte ptr [rcx+1Ch], 40h
0x1800140eb  jz      loc_180013DEA
0x1800140f1  cmp     byte ptr [rcx+19h], 2
0x1800140f5  jb      loc_180013DEA
0x1800140fb  mov     edx, 48h ; 'H'
0x180014100  jmp     loc_1800141B7
0x180014105  mov     dword ptr [rsi], 1
0x18001410b  jmp     loc_180013F13
0x180014110  xor     edi, edi
0x180014112  jmp     loc_180013DEA
0x180014117  mov     dword ptr [rsi], 0
0x18001411d  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180014123  cmp     ecx, 0FFFFFFFFh
0x180014126  jz      short loc_18001413A
0x180014128  lea     r8, aInitializeserv_3; "InitializeService: SERVICE_STOPPED!\n"
0x18001412f  mov     edx, 0Ch; dwFlags
0x180014134  call    cs:__imp_TracePrintfExA
0x18001413a  mov     edi, 426h
0x18001413f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014146  cmp     rcx, r15
0x180014149  jz      loc_180013DEA
0x18001414f  test    byte ptr [rcx+1Ch], 40h
0x180014153  jz      loc_180013DEA
0x180014159  cmp     byte ptr [rcx+19h], 2
0x18001415d  jb      loc_180013DEA
0x180014163  mov     edx, 47h ; 'G'
0x180014168  jmp     short loc_1800141B7
0x18001416a  mov     eax, cs:g_dwTraceId
0x180014170  cmp     eax, 0FFFFFFFFh
0x180014173  jz      short loc_180014190
0x180014175  lea     r8, aInitializeserv; "InitializeService: service is not comin"...
0x18001417c  mov     edx, 0Ch; dwFlags
0x180014181  mov     ecx, eax; dwTraceID
0x180014183  call    cs:__imp_TracePrintfExA
0x180014189  mov     rcx, cs:WPP_GLOBAL_Control
0x180014190  mov     edi, 42Eh
0x180014195  cmp     rcx, r15
0x180014198  jz      loc_180013DEA
0x18001419e  test    byte ptr [rcx+1Ch], 40h
0x1800141a2  jz      loc_180013DEA
0x1800141a8  cmp     byte ptr [rcx+19h], 2
0x1800141ac  jb      loc_180013DEA
0x1800141b2  mov     edx, 4Dh ; 'M'
0x1800141b7  mov     r9d, edi
0x1800141ba  mov     rcx, [rcx+10h]
0x1800141be  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800141c5  call    WPP_SF_d
0x1800141ca  jmp     loc_180013DEA
```
