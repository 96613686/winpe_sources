# WfpServiceMain

- ea: `0x180052684`
- end: `0x18005282e`
- name: `WfpServiceMain`
- size: `426`
- prototype: `__int64 __fastcall(LPVOID lpContext)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800580d0`

## callees

- `0x1800061ec`
- `0x180010c50`
- `0x180010db0`
- `0x1800524e4`
- `0x180052534`
- `0x1800525f0`
- `0x180052684`
- `0x180119010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800526cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052704`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800526cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052704`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800526f6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800526f6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180052803`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180052803`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800526bc`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800526bc`

## string_xrefs

- `0x180052779`: `WfpComponentsStart`
- `0x1800526d5`: `RegisterServiceCtrlHandlerExW`
- `0x18005270a`: `CreateEventW`

## pseudocode

```c
int __fastcall WfpServiceMain(HANDLE *lpContext)
{
  _DWORD *v1; // r14
  int v2; // r15d
  SERVICE_STATUS_HANDLE v4; // rax
  HANDLE *v5; // rdi
  DWORD LastError; // eax
  __int64 v7; // rcx
  const char *v8; // rdx
  __int64 v9; // rax
  HANDLE EventW; // rax
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // r8
  __int64 v14; // rax
  HANDLE v15; // r8
  HANDLE v16; // rdx
  int v17; // eax
  __int64 v19; // [rsp+70h] [rbp+8h] BYREF

  v1 = (_DWORD *)lpContext + 11;
  v2 = 0;
  *((_DWORD *)lpContext + 11) = 0;
  *((_DWORD *)lpContext + 15) = 1;
  v4 = RegisterServiceCtrlHandlerExW((LPCWSTR)*lpContext, WfpServiceHandlerEx, lpContext);
  lpContext[3] = v4;
  v5 = lpContext + 8;
  if ( !v4 )
  {
    LastError = GetLastError();
    v8 = "RegisterServiceCtrlHandlerExW";
    goto LABEL_3;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  *v5 = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v8 = "CreateEventW";
    goto LABEL_3;
  }
  v11 = WfpServiceChangeState(lpContext, 2);
  if ( !v11 )
  {
    v19 = 0;
    v12 = WfpComponentsDispatchForward(lpContext + 1, 0, 0, &v19);
    v11 = v12;
    if ( v1 )
    {
      LODWORD(v12) = (unsigned __int16)v12;
      if ( (v11 & 0x1FFF0000) != 0x70000 )
        LODWORD(v12) = v11;
      *v1 = v12;
    }
    if ( !v11 )
    {
      v14 = gWfpSvcHostGlobalData;
      v15 = *v5;
      v16 = *lpContext;
      *((_DWORD *)lpContext + 22) = 1;
      LastError = (*(__int64 (__fastcall **)(char *, HANDLE, HANDLE, __int64 (__fastcall *)(_QWORD, _QWORD), HANDLE *, _DWORD))(v14 + 192))(
                    (char *)lpContext + 72,
                    v16,
                    v15,
                    WfpServiceExit,
                    lpContext,
                    0);
      if ( !LastError )
      {
        v2 = 1;
        v9 = WfpServiceChangeState(lpContext, 4);
LABEL_16:
        LODWORD(v11) = v9;
        if ( !v9 )
          return v9;
        goto LABEL_17;
      }
      v8 = "RegisterStopCallback";
LABEL_3:
      v9 = WfpReportSysErrorAsWinError(v7, v8, LastError, 1);
      goto LABEL_16;
    }
    WfpComponentsDispatchReverse(lpContext + 1, 1, v13, v19);
    WfpReportError(v11, "WfpComponentsStart");
  }
LABEL_17:
  v17 = (unsigned __int16)v11;
  if ( (v11 & 0x1FFF0000) != 0x70000 )
    v17 = v11;
  *v1 = v17;
  if ( v2 )
    LODWORD(v9) = SetEvent(*v5);
  else
    LODWORD(v9) = WfpServiceExit(lpContext, 0);
  return v9;
}

```

## disassembly

```asm
0x180052684  mov     [rsp+arg_8], rbx
0x180052689  mov     [rsp+arg_10], rbp
0x18005268e  push    rsi
0x18005268f  push    rdi
0x180052690  push    r13
0x180052692  push    r14
0x180052694  push    r15
0x180052696  sub     rsp, 40h
0x18005269a  lea     r14, [rcx+2Ch]
0x18005269e  xor     r15d, r15d
0x1800526a1  mov     rsi, rcx
0x1800526a4  mov     [r14], r15d
0x1800526a7  mov     r8, rcx; lpContext
0x1800526aa  lea     rdx, WfpServiceHandlerEx; lpHandlerProc
0x1800526b1  lea     r13d, [r15+1]
0x1800526b5  mov     [rcx+3Ch], r13d
0x1800526b9  mov     rcx, [rcx]; lpServiceName
0x1800526bc  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800526c2  mov     [rsi+18h], rax
0x1800526c6  lea     rdi, [rsi+40h]
0x1800526ca  test    rax, rax
0x1800526cd  jnz     short loc_1800526EC
0x1800526cf  call    cs:__imp_GetLastError
0x1800526d5  lea     rdx, aRegisterservic_0; "RegisterServiceCtrlHandlerExW"
0x1800526dc  mov     r8d, eax
0x1800526df  mov     r9d, r13d
0x1800526e2  call    WfpReportSysErrorAsWinError
0x1800526e7  jmp     loc_1800527DC
0x1800526ec  xor     r9d, r9d; lpName
0x1800526ef  xor     r8d, r8d; bInitialState
0x1800526f2  xor     edx, edx; bManualReset
0x1800526f4  xor     ecx, ecx; lpEventAttributes
0x1800526f6  call    cs:__imp_CreateEventW
0x1800526fc  mov     [rdi], rax
0x1800526ff  test    rax, rax
0x180052702  jnz     short loc_180052713
0x180052704  call    cs:__imp_GetLastError
0x18005270a  lea     rdx, aCreateeventw; "CreateEventW"
0x180052711  jmp     short loc_1800526DC
0x180052713  mov     edx, 2
0x180052718  mov     rcx, rsi
0x18005271b  call    WfpServiceChangeState
0x180052720  mov     rbx, rax
0x180052723  test    rax, rax
0x180052726  jnz     loc_1800527E4
0x18005272c  lea     r9, [rsp+68h+arg_0]
0x180052731  mov     [rsp+68h+arg_0], r15
0x180052736  xor     r8d, r8d
0x180052739  lea     rcx, [rsi+8]
0x18005273d  xor     edx, edx
0x18005273f  call    WfpComponentsDispatchForward
0x180052744  mov     rbx, rax
0x180052747  test    r14, r14
0x18005274a  jz      short loc_180052763
0x18005274c  mov     edx, ebx
0x18005274e  movzx   eax, bx
0x180052751  and     edx, 1FFF0000h
0x180052757  cmp     edx, 70000h
0x18005275d  cmovnz  eax, ebx
0x180052760  mov     [r14], eax
0x180052763  test    rbx, rbx
0x180052766  jz      short loc_18005278A
0x180052768  mov     r9, [rsp+68h+arg_0]
0x18005276d  lea     rcx, [rsi+8]
0x180052771  mov     edx, r13d
0x180052774  call    WfpComponentsDispatchReverse
0x180052779  lea     rdx, aWfpcomponentss; "WfpComponentsStart"
0x180052780  mov     rcx, rbx
0x180052783  call    WfpReportError
0x180052788  jmp     short loc_1800527E4
0x18005278a  mov     rax, cs:gWfpSvcHostGlobalData
0x180052791  lea     rcx, [rsi+48h]
0x180052795  mov     r8, [rdi]
0x180052798  lea     r9, WfpServiceExit
0x18005279f  mov     rdx, [rsi]
0x1800527a2  mov     [rsi+58h], r13d
0x1800527a6  mov     rax, [rax+0C0h]
0x1800527ad  mov     [rsp+68h+var_40], r15d
0x1800527b2  mov     [rsp+68h+var_48], rsi
0x1800527b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800527bc  test    eax, eax
0x1800527be  jz      short loc_1800527CC
0x1800527c0  lea     rdx, aRegisterstopca; "RegisterStopCallback"
0x1800527c7  jmp     loc_1800526DC
0x1800527cc  mov     edx, 4
0x1800527d1  mov     rcx, rsi
0x1800527d4  mov     r15d, r13d
0x1800527d7  call    WfpServiceChangeState
0x1800527dc  mov     rbx, rax
0x1800527df  test    rax, rax
0x1800527e2  jz      short loc_180052815
0x1800527e4  mov     edx, ebx
0x1800527e6  movzx   eax, bx
0x1800527e9  and     edx, 1FFF0000h
0x1800527ef  cmp     edx, 70000h
0x1800527f5  cmovnz  eax, ebx
0x1800527f8  mov     [r14], eax
0x1800527fb  test    r15d, r15d
0x1800527fe  jz      short loc_18005280B
0x180052800  mov     rcx, [rdi]; hEvent
0x180052803  call    cs:__imp_SetEvent
0x180052809  jmp     short loc_180052815
0x18005280b  xor     edx, edx
0x18005280d  mov     rcx, rsi
0x180052810  call    WfpServiceExit
0x180052815  lea     r11, [rsp+68h+var_28]
0x18005281a  mov     rbx, [r11+38h]
0x18005281e  mov     rbp, [r11+40h]
0x180052822  mov     rsp, r11
0x180052825  pop     r15
0x180052827  pop     r14
0x180052829  pop     r13
0x18005282b  pop     rdi
0x18005282c  pop     rsi
0x18005282d  retn
```
