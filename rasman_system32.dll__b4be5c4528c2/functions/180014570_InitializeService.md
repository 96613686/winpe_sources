# InitializeService

- ea: `0x180014570`
- end: `0x180014a88`
- name: `InitializeService`
- size: `1304`
- prototype: `__int64 __fastcall(SC_HANDLE hSCManager, LPCSTR lpServiceName)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b230`

## callees

- `0x180014570`
- `0x180021ae4`
- `0x180021b14`
- `0x180022818`
- `0x1800273d0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180014790`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180014790`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001471f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800147aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001471f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800147aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014944`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x1800145f1`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x1800145f1`
- `api-ms-win-service-winsvc-l1-1-0!StartServiceA` at `0x180014934`
- `api-ms-win-service-winsvc-l1-1-0!StartServiceA` at `0x180014934`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18001462d`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18001462d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001465f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001465f`
- `rtutils!TracePrintfExA` at `0x1800145d9`
- `rtutils!TracePrintfExA` at `0x180014853`
- `rtutils!TracePrintfExA` at `0x180014920`
- `rtutils!TracePrintfExA` at `0x18001496c`
- `rtutils!TracePrintfExA` at `0x1800149e1`
- `rtutils!TracePrintfExA` at `0x180014a36`
- `rtutils!TracePrintfExA` at `0x1800145d9`
- `rtutils!TracePrintfExA` at `0x180014853`
- `rtutils!TracePrintfExA` at `0x180014920`
- `rtutils!TracePrintfExA` at `0x18001496c`
- `rtutils!TracePrintfExA` at `0x1800149e1`
- `rtutils!TracePrintfExA` at `0x180014a36`

## string_xrefs

- `0x1800145cd`: `InitializeService: Initializing %s service\n`
- `0x1800149d5`: `InitializeService: SERVICE_STOPPED!\n`
- `0x180014914`: `InitializeService: Starting the service`
- `0x180014960`: `InitializeService: StartService returned 0x%x\n`
- `0x180014845`: `InitializeService: Invalid service.status=%d\n`
- `0x180014a28`: `InitializeService: service is not coming out of START PENDING state\n`

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
0x180014570  push    rbx
0x180014572  push    rsi
0x180014573  push    rdi
0x180014574  push    r14
0x180014576  push    r15
0x180014578  sub     rsp, 60h
0x18001457c  mov     rax, cs:__security_cookie
0x180014583  xor     rax, rsp
0x180014586  mov     [rsp+88h+var_38], rax
0x18001458b  mov     rsi, r9
0x18001458e  mov     r14d, r8d
0x180014591  mov     rbx, rdx
0x180014594  mov     rdi, rcx
0x180014597  mov     rcx, cs:WPP_GLOBAL_Control
0x18001459e  lea     r15, WPP_GLOBAL_Control
0x1800145a5  cmp     rcx, r15
0x1800145a8  jnz     loc_1800146E7
0x1800145ae  xor     eax, eax
0x1800145b0  xorps   xmm0, xmm0
0x1800145b3  mov     [rsi], eax
0x1800145b5  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800145bb  movups  xmmword ptr [rsp+88h+ServiceStatus.dwServiceType], xmm0
0x1800145c0  movups  xmmword ptr [rsp+88h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800145c5  cmp     ecx, 0FFFFFFFFh
0x1800145c8  jz      short loc_1800145E5
0x1800145ca  mov     r9, rbx
0x1800145cd  lea     r8, aInitializeserv_4; "InitializeService: Initializing %s serv"...
0x1800145d4  mov     edx, 0Ch; dwFlags
0x1800145d9  call    cs:__imp_TracePrintfExA
0x1800145e0  nop     dword ptr [rax+rax+00h]
0x1800145e5  mov     r8d, 14h; dwDesiredAccess
0x1800145eb  mov     rdx, rbx; lpServiceName
0x1800145ee  mov     rcx, rdi; hSCManager
0x1800145f1  call    cs:__imp_OpenServiceA
0x1800145f8  nop     dword ptr [rax+rax+00h]
0x1800145fd  mov     rbx, rax
0x180014600  test    rax, rax
0x180014603  jz      loc_1800147AA
0x180014609  mov     rcx, cs:WPP_GLOBAL_Control
0x180014610  xor     edi, edi
0x180014612  mov     [rsp+88h+arg_10], rbp
0x18001461a  xor     ebp, ebp
0x18001461c  cmp     ebp, r14d
0x18001461f  jnb     loc_180014A1D
0x180014625  lea     rdx, [rsp+88h+ServiceStatus]; lpServiceStatus
0x18001462a  mov     rcx, rbx; hService
0x18001462d  call    cs:__imp_QueryServiceStatus
0x180014634  nop     dword ptr [rax+rax+00h]
0x180014639  test    eax, eax
0x18001463b  jz      loc_18001471F
0x180014641  mov     r9d, [rsp+88h+ServiceStatus.dwCurrentState]
0x180014646  cmp     r9d, 4
0x18001464a  jnz     loc_180014766
0x180014650  mov     rcx, cs:WPP_GLOBAL_Control
0x180014657  cmp     rcx, r15
0x18001465a  jnz     short loc_1800146C1
0x18001465c  mov     rcx, rbx; hSCObject
0x18001465f  call    cs:__imp_CloseServiceHandle
0x180014666  nop     dword ptr [rax+rax+00h]
0x18001466b  mov     rbp, [rsp+88h+arg_10]
0x180014673  mov     rcx, cs:WPP_GLOBAL_Control
0x18001467a  cmp     rcx, r15
0x18001467d  jnz     short loc_18001469B
0x18001467f  mov     eax, edi
0x180014681  mov     rcx, [rsp+88h+var_38]
0x180014686  xor     rcx, rsp; StackCookie
0x180014689  call    __security_check_cookie
0x18001468e  add     rsp, 60h
0x180014692  pop     r15
0x180014694  pop     r14
0x180014696  pop     rdi
0x180014697  pop     rsi
0x180014698  pop     rbx
0x180014699  retn
0x18001469b  test    byte ptr [rcx+1Ch], 40h
0x18001469f  jz      short loc_18001467F
0x1800146a1  cmp     byte ptr [rcx+19h], 6
0x1800146a5  jb      short loc_18001467F
0x1800146a7  mov     rcx, [rcx+10h]
0x1800146ab  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800146b2  mov     edx, 4Eh ; 'N'
0x1800146b7  mov     r9d, edi
0x1800146ba  call    WPP_SF_d
0x1800146bf  jmp     short loc_18001467F
0x1800146c1  test    byte ptr [rcx+1Ch], 40h
0x1800146c5  jz      short loc_18001465C
0x1800146c7  cmp     byte ptr [rcx+19h], 5
0x1800146cb  jb      short loc_18001465C
0x1800146cd  mov     rcx, [rcx+10h]
0x1800146d1  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800146d8  mov     edx, 4Ah ; 'J'
0x1800146dd  call    WPP_SF_
0x1800146e2  jmp     loc_18001465C
0x1800146e7  test    byte ptr [rcx+1Ch], 40h
0x1800146eb  jz      loc_1800145AE
0x1800146f1  cmp     byte ptr [rcx+19h], 6
0x1800146f5  jb      loc_1800145AE
0x1800146fb  mov     rcx, [rcx+10h]
0x1800146ff  lea     rax, aNull; "<NULL>"
0x180014706  test    rbx, rbx
0x180014709  mov     [rsp+88h+var_68], r14d
0x18001470e  mov     r9, rbx
0x180014711  cmovz   r9, rax
0x180014715  call    WPP_SF_sd
0x18001471a  jmp     loc_1800145AE
0x18001471f  call    cs:__imp_GetLastError
0x180014726  nop     dword ptr [rax+rax+00h]
0x18001472b  mov     edi, eax
0x18001472d  test    eax, eax
0x18001472f  jz      loc_18001465C
0x180014735  mov     rcx, cs:WPP_GLOBAL_Control
0x18001473c  cmp     rcx, r15
0x18001473f  jz      loc_18001465C
0x180014745  test    byte ptr [rcx+1Ch], 40h
0x180014749  jz      loc_18001465C
0x18001474f  cmp     byte ptr [rcx+19h], 2
0x180014753  jb      loc_18001465C
0x180014759  mov     edx, 45h ; 'E'
0x18001475e  mov     r9d, eax
0x180014761  jmp     loc_180014A73
0x180014766  mov     eax, r9d
0x180014769  sub     eax, 1
0x18001476c  jz      loc_1800148D3
0x180014772  cmp     eax, 1
0x180014775  jnz     loc_180014801
0x18001477b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014782  cmp     rcx, r15
0x180014785  jnz     loc_1800148A5
0x18001478b  mov     ecx, 3E8h; dwMilliseconds
0x180014790  call    cs:__imp_Sleep
0x180014797  nop     dword ptr [rax+rax+00h]
0x18001479c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800147a3  inc     ebp
0x1800147a5  jmp     loc_18001461C
0x1800147aa  call    cs:__imp_GetLastError
0x1800147b1  nop     dword ptr [rax+rax+00h]
0x1800147b6  mov     edi, eax
0x1800147b8  test    eax, eax
0x1800147ba  jz      loc_180014673
0x1800147c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800147c7  cmp     rcx, r15
0x1800147ca  jz      loc_180014681
0x1800147d0  test    byte ptr [rcx+1Ch], 40h
0x1800147d4  jz      loc_18001467A
0x1800147da  cmp     byte ptr [rcx+19h], 2
0x1800147de  jb      loc_18001467A
0x1800147e4  mov     rcx, [rcx+10h]
0x1800147e8  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800147ef  mov     edx, 44h ; 'D'
0x1800147f4  mov     r9d, eax
0x1800147f7  call    WPP_SF_d
0x1800147fc  jmp     loc_180014673
0x180014801  mov     rcx, cs:WPP_GLOBAL_Control
0x180014808  cmp     rcx, r15
0x18001480b  jz      short loc_18001483A
0x18001480d  test    byte ptr [rcx+1Ch], 40h
0x180014811  jz      short loc_18001483A
0x180014813  cmp     byte ptr [rcx+19h], 5
0x180014817  jb      short loc_18001483A
0x180014819  mov     rcx, [rcx+10h]
0x18001481d  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180014824  mov     edx, 4Bh ; 'K'
0x180014829  call    WPP_SF_
0x18001482e  mov     r9d, [rsp+88h+ServiceStatus.dwCurrentState]
0x180014833  mov     rcx, cs:WPP_GLOBAL_Control
0x18001483a  mov     eax, cs:g_dwTraceId
0x180014840  cmp     eax, 0FFFFFFFFh
0x180014843  jz      short loc_180014866
0x180014845  lea     r8, aInitializeserv_2; "InitializeService: Invalid service.stat"...
0x18001484c  mov     edx, 0Ch; dwFlags
0x180014851  mov     ecx, eax; dwTraceID
0x180014853  call    cs:__imp_TracePrintfExA
0x18001485a  nop     dword ptr [rax+rax+00h]
0x18001485f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014866  mov     edi, 139Fh
0x18001486b  cmp     rcx, r15
0x18001486e  jz      loc_1800147A3
0x180014874  test    byte ptr [rcx+1Ch], 40h
0x180014878  jz      loc_1800147A3
0x18001487e  cmp     byte ptr [rcx+19h], 2
0x180014882  jb      loc_1800147A3
0x180014888  mov     rcx, [rcx+10h]
0x18001488c  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180014893  mov     edx, 4Ch ; 'L'
0x180014898  mov     r9d, edi
0x18001489b  call    WPP_SF_d
0x1800148a0  jmp     loc_18001479C
0x1800148a5  test    byte ptr [rcx+1Ch], 40h
0x1800148a9  jz      loc_18001478B
0x1800148af  cmp     byte ptr [rcx+19h], 5
0x1800148b3  jb      loc_18001478B
0x1800148b9  mov     rcx, [rcx+10h]
0x1800148bd  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800148c4  mov     edx, 49h ; 'I'
0x1800148c9  call    WPP_SF_
0x1800148ce  jmp     loc_18001478B
0x1800148d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800148da  cmp     rcx, r15
0x1800148dd  jz      short loc_180014900
0x1800148df  test    byte ptr [rcx+1Ch], 40h
0x1800148e3  jz      short loc_180014900
0x1800148e5  cmp     byte ptr [rcx+19h], 5
0x1800148e9  jb      short loc_180014900
0x1800148eb  mov     rcx, [rcx+10h]
0x1800148ef  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800148f6  mov     edx, 46h ; 'F'
0x1800148fb  call    WPP_SF_
0x180014900  cmp     dword ptr [rsi], 0
0x180014903  jnz     loc_1800149C4
0x180014909  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001490f  cmp     ecx, 0FFFFFFFFh
0x180014912  jz      short loc_18001492C
0x180014914  lea     r8, aInitializeserv_0; "InitializeService: Starting the service"
0x18001491b  mov     edx, 0Ch; dwFlags
0x180014920  call    cs:__imp_TracePrintfExA
0x180014927  nop     dword ptr [rax+rax+00h]
0x18001492c  xor     r8d, r8d; lpServiceArgVectors
0x18001492f  xor     edx, edx; dwNumServiceArgs
0x180014931  mov     rcx, rbx; hService
0x180014934  call    cs:__imp_StartServiceA
0x18001493b  nop     dword ptr [rax+rax+00h]
0x180014940  test    eax, eax
0x180014942  jnz     short loc_1800149B2
0x180014944  call    cs:__imp_GetLastError
0x18001494b  nop     dword ptr [rax+rax+00h]
0x180014950  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180014956  mov     edi, eax
0x180014958  cmp     ecx, 0FFFFFFFFh
0x18001495b  jz      short loc_180014978
0x18001495d  mov     r9d, eax
0x180014960  lea     r8, aInitializeserv_1; "InitializeService: StartService returne"...
0x180014967  mov     edx, 0Ch; dwFlags
0x18001496c  call    cs:__imp_TracePrintfExA
0x180014973  nop     dword ptr [rax+rax+00h]
0x180014978  cmp     edi, 420h
0x18001497e  jz      short loc_1800149BD
0x180014980  test    edi, edi
0x180014982  jz      short loc_1800149B2
0x180014984  mov     rcx, cs:WPP_GLOBAL_Control
0x18001498b  cmp     rcx, r15
0x18001498e  jz      loc_18001465C
0x180014994  test    byte ptr [rcx+1Ch], 40h
0x180014998  jz      loc_18001465C
0x18001499e  cmp     byte ptr [rcx+19h], 2
0x1800149a2  jb      loc_18001465C
0x1800149a8  mov     edx, 48h ; 'H'
0x1800149ad  jmp     loc_180014A70
0x1800149b2  mov     dword ptr [rsi], 1
0x1800149b8  jmp     loc_18001479C
0x1800149bd  xor     edi, edi
0x1800149bf  jmp     loc_18001465C
0x1800149c4  mov     dword ptr [rsi], 0
0x1800149ca  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800149d0  cmp     ecx, 0FFFFFFFFh
0x1800149d3  jz      short loc_1800149ED
0x1800149d5  lea     r8, aInitializeserv_3; "InitializeService: SERVICE_STOPPED!\n"
0x1800149dc  mov     edx, 0Ch; dwFlags
0x1800149e1  call    cs:__imp_TracePrintfExA
0x1800149e8  nop     dword ptr [rax+rax+00h]
0x1800149ed  mov     edi, 426h
0x1800149f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800149f9  cmp     rcx, r15
0x1800149fc  jz      loc_18001465C
0x180014a02  test    byte ptr [rcx+1Ch], 40h
0x180014a06  jz      loc_18001465C
0x180014a0c  cmp     byte ptr [rcx+19h], 2
0x180014a10  jb      loc_18001465C
0x180014a16  mov     edx, 47h ; 'G'
0x180014a1b  jmp     short loc_180014A70
0x180014a1d  mov     eax, cs:g_dwTraceId
0x180014a23  cmp     eax, 0FFFFFFFFh
0x180014a26  jz      short loc_180014A49
0x180014a28  lea     r8, aInitializeserv; "InitializeService: service is not comin"...
0x180014a2f  mov     edx, 0Ch; dwFlags
0x180014a34  mov     ecx, eax; dwTraceID
0x180014a36  call    cs:__imp_TracePrintfExA
0x180014a3d  nop     dword ptr [rax+rax+00h]
0x180014a42  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a49  mov     edi, 42Eh
0x180014a4e  cmp     rcx, r15
0x180014a51  jz      loc_18001465C
0x180014a57  test    byte ptr [rcx+1Ch], 40h
0x180014a5b  jz      loc_18001465C
0x180014a61  cmp     byte ptr [rcx+19h], 2
0x180014a65  jb      loc_18001465C
0x180014a6b  mov     edx, 4Dh ; 'M'
0x180014a70  mov     r9d, edi
0x180014a73  mov     rcx, [rcx+10h]
0x180014a77  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180014a7e  call    WPP_SF_d
0x180014a83  jmp     loc_18001465C
```
