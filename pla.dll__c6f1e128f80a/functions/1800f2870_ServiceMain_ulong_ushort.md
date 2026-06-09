# ServiceMain(ulong,ushort * *)

- ea: `0x1800f2870`
- end: `0x1800f2cd8`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `1128`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18002b3a0`
- `0x1800f2870`
- `0x1800f2ce0`
- `0x1800f2f2c`
- `0x18010e338`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f2968`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f2968`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800f294c`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800f294c`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800f2b12`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800f2cb1`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800f2b12`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800f2cb1`

## string_xrefs

- `0x1800f2a08`: `ServiceMain`
- `0x1800f2ad6`: `ServiceMain`
- `0x1800f2be5`: `ServiceMain`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, unsigned __int16 **a2)
{
  signed int LastError; // eax
  signed int v3; // ebx
  unsigned __int64 v4; // rcx
  __int64 v5; // rax
  int v6; // eax
  __int64 v7; // rax
  unsigned int v8; // eax
  __int64 v9; // rax
  __int64 v10; // [rsp+28h] [rbp-D8h]
  __int64 v11; // [rsp+30h] [rbp-D0h]
  __int64 v12; // [rsp+38h] [rbp-C8h]
  __int64 v13; // [rsp+40h] [rbp-C0h]
  __int64 v14; // [rsp+48h] [rbp-B8h]
  __int64 v15; // [rsp+50h] [rbp-B0h]
  int v16; // [rsp+70h] [rbp-90h] BYREF
  signed int v17; // [rsp+78h] [rbp-88h] BYREF
  int v18; // [rsp+80h] [rbp-80h] BYREF
  int v19; // [rsp+88h] [rbp-78h] BYREF
  int v20; // [rsp+90h] [rbp-70h] BYREF
  signed int v21; // [rsp+98h] [rbp-68h] BYREF
  signed int v22; // [rsp+A0h] [rbp-60h] BYREF
  int v23; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 v24[64]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v25[64]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v26[64]; // [rsp+1B0h] [rbp+B0h] BYREF

  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000100LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000100LL) )
  {
    EventingWriteEvent(&g_Eventing, PLA_EVENT_SVC_START, 2, "shp", 4, v10, v11, v12, v13, v14, v15);
  }
  WaitHandle = 0;
  hObject = 0;
  *(_OWORD *)&ServiceStatus.dwControlsAccepted = 0;
  dword_180169B84 = 0;
  hServiceStatus = 0;
  ServiceStatus.dwWaitHint = 0;
  ServiceStatus.dwServiceType = 32;
  ServiceStatus.dwCurrentState = 2;
  PlaiBreakForDebugger();
  hServiceStatus = RegisterServiceCtrlHandlerExW(L"PLA", PlaiServiceCtrlHandler, 0);
  if ( hServiceStatus )
  {
    v6 = PlaiServiceStartup();
    v3 = v6;
    if ( v6 >= 0 )
    {
      ServiceStatus.dwCurrentState = 4;
      ServiceStatus.dwControlsAccepted = 5;
      SetServiceStatus(hServiceStatus, &ServiceStatus);
      v8 = (*(__int64 (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, int))(qword_180169B98 + 192))(
             &WaitHandle,
             L"PLA",
             hObject,
             PlaiEventSetCallback,
             0,
             8);
      v3 = PlaiHResultFromWin32(v8);
      if ( v3 >= 0 )
        return;
      PlaiServiceCleanup();
      v4 = qword_180169748;
      v20 = 0;
      v21 = v3;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_31;
      }
      PlaiWhoAmI(v26, 0x4000000000000800uLL);
      v9 = -1;
      do
        ++v9;
      while ( v26[v9] );
      EventingWriteEvent(&g_Eventing, PLA_EVENT_ERROR, 5, &v21, 4, qword_180147320, 1, &v20, 4, "ServiceMain", 12);
    }
    else
    {
      v4 = qword_180169748;
      v18 = 0;
      v19 = v6;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_31;
      }
      PlaiWhoAmI(v25, 0x4000000000000800uLL);
      v7 = -1;
      do
        ++v7;
      while ( v25[v7] );
      EventingWriteEvent(&g_Eventing, PLA_EVENT_ERROR, 5, &v19, 4, qword_180147320, 1, &v18, 4, "ServiceMain", 12);
    }
    v4 = qword_180169748;
LABEL_31:
    ServiceStatus.dwWin32ExitCode = (unsigned __int16)v3;
    ServiceStatus.dwCurrentState = 1;
    ServiceStatus.dwServiceSpecificExitCode = v3;
    v22 = v3;
    v23 = 0;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000100LL) != 0
      && v4 == (v4 & 0x4000000000000100LL) )
    {
      EventingWriteEvent(&g_Eventing, PLA_EVENT_SVC_STOP, 2, &v23, 4, &v22, 4, v12, v13, v14, v15);
    }
    if ( hServiceStatus )
      SetServiceStatus(hServiceStatus, &ServiceStatus);
    return;
  }
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
  v4 = qword_180169748;
  v16 = 0;
  v17 = v3;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v24, 0x4000000000000800uLL);
    v5 = -1;
    do
      ++v5;
    while ( v24[v5] );
    EventingWriteEvent(&g_Eventing, PLA_EVENT_ERROR, 5, &v17, 4, qword_180147320, 1, &v16, 4, "ServiceMain", 12);
    v4 = qword_180169748;
  }
  if ( v3 < 0 )
    goto LABEL_31;
}

```

## disassembly

```asm
0x1800f2870  push    rbp
0x1800f2872  push    rbx
0x1800f2873  push    rsi
0x1800f2874  push    rdi
0x1800f2875  push    r12
0x1800f2877  push    r13
0x1800f2879  push    r14
0x1800f287b  lea     rbp, [rsp-140h]
0x1800f2883  sub     rsp, 240h
0x1800f288a  mov     rax, cs:__security_cookie
0x1800f2891  xor     rax, rsp
0x1800f2894  mov     [rbp+170h+var_40], rax
0x1800f289b  xor     edi, edi
0x1800f289d  lea     r12, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800f28a4  cmp     dword ptr cs:xmmword_180169738, edi
0x1800f28aa  mov     esi, 4
0x1800f28af  mov     r14, 4000000000000100h
0x1800f28b9  jz      short loc_1800F28F6
0x1800f28bb  test    qword ptr cs:xmmword_180169738+8, r14
0x1800f28c2  jz      short loc_1800F28F6
0x1800f28c4  mov     rax, cs:qword_180169748
0x1800f28cb  and     rax, r14
0x1800f28ce  cmp     cs:qword_180169748, rax
0x1800f28d5  jnz     short loc_1800F28F6
0x1800f28d7  lea     r9, aShp; "shp"
0x1800f28de  mov     [rsp+270h+var_250], rsi
0x1800f28e3  lea     r8d, [rsi-2]
0x1800f28e7  mov     rcx, r12
0x1800f28ea  lea     rdx, PLA_EVENT_SVC_START
0x1800f28f1  call    EventingWriteEvent
0x1800f28f6  xorps   xmm0, xmm0
0x1800f28f9  mov     cs:WaitHandle, rdi
0x1800f2900  mov     cs:hObject, rdi
0x1800f2907  movdqu  xmmword ptr cs:ServiceStatus.dwControlsAccepted, xmm0
0x1800f290f  mov     cs:dword_180169B84, edi
0x1800f2915  mov     cs:hServiceStatus, rdi
0x1800f291c  mov     cs:ServiceStatus.dwWaitHint, edi
0x1800f2922  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x1800f292c  mov     cs:ServiceStatus.dwCurrentState, 2
0x1800f2936  call    ?PlaiBreakForDebugger@@YAXXZ; PlaiBreakForDebugger(void)
0x1800f293b  xor     r8d, r8d; lpContext
0x1800f293e  lea     rdx, ?PlaiServiceCtrlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x1800f2945  lea     rcx, aPla_0; "PLA"
0x1800f294c  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800f2952  mov     cs:hServiceStatus, rax
0x1800f2959  mov     r13d, 1
0x1800f295f  test    rax, rax
0x1800f2962  jnz     loc_1800F2A55
0x1800f2968  call    cs:__imp_GetLastError
0x1800f296e  mov     ebx, eax
0x1800f2970  test    eax, eax
0x1800f2972  jle     short loc_1800F297D
0x1800f2974  movzx   ebx, ax
0x1800f2977  or      ebx, 80070000h
0x1800f297d  cmp     dword ptr cs:xmmword_180169738, edi
0x1800f2983  mov     rcx, cs:qword_180169748
0x1800f298a  mov     [rsp+270h+var_200], edi
0x1800f298e  mov     [rsp+270h+var_1F8], ebx
0x1800f2992  jz      loc_1800F2A48
0x1800f2998  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f29a2  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f29a9  jz      loc_1800F2A48
0x1800f29af  mov     rax, rcx
0x1800f29b2  and     rax, rdx
0x1800f29b5  cmp     rcx, rax
0x1800f29b8  jnz     loc_1800F2A48
0x1800f29be  lea     rcx, [rbp+170h+var_1C0]; unsigned __int16 *
0x1800f29c2  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f29c7  lea     rcx, [rbp+170h+var_1C0]
0x1800f29cb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f29cf  inc     rax
0x1800f29d2  cmp     [rcx+rax*2], di
0x1800f29d6  jnz     short loc_1800F29CF
0x1800f29d8  lea     ecx, [rax+rax]
0x1800f29db  mov     r8d, 5
0x1800f29e1  add     rcx, 2
0x1800f29e5  lea     rax, [rbp+170h+var_1C0]
0x1800f29e9  mov     [rsp+270h+var_210], rcx
0x1800f29ee  lea     r9, [rsp+270h+var_1F8]
0x1800f29f3  mov     [rsp+270h+var_218], rax
0x1800f29f8  lea     rdx, PLA_EVENT_ERROR
0x1800f29ff  mov     [rsp+270h+var_220], 0Ch
0x1800f2a08  lea     rax, aServicemain_0; "ServiceMain"
0x1800f2a0f  mov     [rsp+270h+var_228], rax
0x1800f2a14  mov     rcx, r12
0x1800f2a17  mov     [rsp+270h+var_230], rsi
0x1800f2a1c  lea     rax, [rsp+270h+var_200]
0x1800f2a21  mov     [rsp+270h+var_238], rax
0x1800f2a26  lea     rax, qword_180147320
0x1800f2a2d  mov     [rsp+270h+var_240], r13
0x1800f2a32  mov     [rsp+270h+var_248], rax
0x1800f2a37  mov     [rsp+270h+var_250], rsi
0x1800f2a3c  call    EventingWriteEvent
0x1800f2a41  mov     rcx, cs:qword_180169748
0x1800f2a48  test    ebx, ebx
0x1800f2a4a  jns     loc_1800F2CB7
0x1800f2a50  jmp     loc_1800F2C3A
0x1800f2a55  call    ?PlaiServiceStartup@@YAJXZ; PlaiServiceStartup(void)
0x1800f2a5a  mov     ebx, eax
0x1800f2a5c  test    eax, eax
0x1800f2a5e  jns     loc_1800F2AF4
0x1800f2a64  cmp     dword ptr cs:xmmword_180169738, edi
0x1800f2a6a  mov     rcx, cs:qword_180169748
0x1800f2a71  mov     [rbp+170h+var_1F0], edi
0x1800f2a74  mov     [rbp+170h+var_1E8], eax
0x1800f2a77  jz      loc_1800F2C3A
0x1800f2a7d  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f2a87  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f2a8e  jz      loc_1800F2C3A
0x1800f2a94  mov     rax, rcx
0x1800f2a97  and     rax, rdx
0x1800f2a9a  cmp     rcx, rax
0x1800f2a9d  jnz     loc_1800F2C3A
0x1800f2aa3  lea     rcx, [rbp+170h+var_140]; unsigned __int16 *
0x1800f2aa7  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f2aac  lea     rcx, [rbp+170h+var_140]
0x1800f2ab0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f2ab4  inc     rax
0x1800f2ab7  cmp     [rcx+rax*2], di
0x1800f2abb  jnz     short loc_1800F2AB4
0x1800f2abd  lea     ecx, [rax+rax]
0x1800f2ac0  lea     rax, [rbp+170h+var_140]
0x1800f2ac4  add     rcx, 2
0x1800f2ac8  mov     [rsp+270h+var_210], rcx
0x1800f2acd  lea     r9, [rbp+170h+var_1E8]
0x1800f2ad1  mov     [rsp+270h+var_218], rax
0x1800f2ad6  lea     rax, aServicemain_0; "ServiceMain"
0x1800f2add  mov     [rsp+270h+var_220], 0Ch
0x1800f2ae6  mov     [rsp+270h+var_228], rax
0x1800f2aeb  lea     rax, [rbp+170h+var_1F0]
0x1800f2aef  jmp     loc_1800F2BFE
0x1800f2af4  mov     rcx, cs:hServiceStatus; hServiceStatus
0x1800f2afb  lea     rdx, ServiceStatus; lpServiceStatus
0x1800f2b02  mov     cs:ServiceStatus.dwCurrentState, esi
0x1800f2b08  mov     cs:ServiceStatus.dwControlsAccepted, 5
0x1800f2b12  call    cs:__imp_SetServiceStatus
0x1800f2b18  mov     rax, cs:qword_180169B98
0x1800f2b1f  lea     r9, ?PlaiEventSetCallback@@YAXPEAXE@Z; PlaiEventSetCallback(void *,uchar)
0x1800f2b26  mov     r8, cs:hObject
0x1800f2b2d  lea     rdx, aPla_0; "PLA"
0x1800f2b34  mov     dword ptr [rsp+270h+var_248], 8
0x1800f2b3c  lea     rcx, WaitHandle
0x1800f2b43  mov     [rsp+270h+var_250], rdi
0x1800f2b48  mov     rax, [rax+0C0h]
0x1800f2b4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2b54  mov     ecx, eax; unsigned int
0x1800f2b56  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800f2b5b  mov     ebx, eax
0x1800f2b5d  test    eax, eax
0x1800f2b5f  jns     loc_1800F2CB7
0x1800f2b65  call    ?PlaiServiceCleanup@@YAXXZ; PlaiServiceCleanup(void)
0x1800f2b6a  cmp     dword ptr cs:xmmword_180169738, edi
0x1800f2b70  mov     rcx, cs:qword_180169748
0x1800f2b77  mov     [rbp+170h+var_1E0], edi
0x1800f2b7a  mov     [rbp+170h+var_1D8], ebx
0x1800f2b7d  jz      loc_1800F2C3A
0x1800f2b83  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f2b8d  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f2b94  jz      loc_1800F2C3A
0x1800f2b9a  mov     rax, rcx
0x1800f2b9d  and     rax, rdx
0x1800f2ba0  cmp     rcx, rax
0x1800f2ba3  jnz     loc_1800F2C3A
0x1800f2ba9  lea     rcx, [rbp+170h+var_C0]; unsigned __int16 *
0x1800f2bb0  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f2bb5  lea     rcx, [rbp+170h+var_C0]
0x1800f2bbc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f2bc0  inc     rax
0x1800f2bc3  cmp     [rcx+rax*2], di
0x1800f2bc7  jnz     short loc_1800F2BC0
0x1800f2bc9  lea     ecx, [rax+rax]
0x1800f2bcc  lea     rax, [rbp+170h+var_C0]
0x1800f2bd3  add     rcx, 2
0x1800f2bd7  mov     [rsp+270h+var_210], rcx
0x1800f2bdc  lea     r9, [rbp+170h+var_1D8]
0x1800f2be0  mov     [rsp+270h+var_218], rax
0x1800f2be5  lea     rax, aServicemain_0; "ServiceMain"
0x1800f2bec  mov     [rsp+270h+var_220], 0Ch
0x1800f2bf5  mov     [rsp+270h+var_228], rax
0x1800f2bfa  lea     rax, [rbp+170h+var_1E0]
0x1800f2bfe  mov     [rsp+270h+var_230], rsi
0x1800f2c03  lea     rdx, PLA_EVENT_ERROR
0x1800f2c0a  mov     [rsp+270h+var_238], rax
0x1800f2c0f  mov     r8d, 5
0x1800f2c15  lea     rax, qword_180147320
0x1800f2c1c  mov     [rsp+270h+var_240], r13
0x1800f2c21  mov     [rsp+270h+var_248], rax
0x1800f2c26  mov     rcx, r12
0x1800f2c29  mov     [rsp+270h+var_250], rsi
0x1800f2c2e  call    EventingWriteEvent
0x1800f2c33  mov     rcx, cs:qword_180169748
0x1800f2c3a  cmp     dword ptr cs:xmmword_180169738, edi
0x1800f2c40  movzx   eax, bx
0x1800f2c43  mov     cs:ServiceStatus.dwWin32ExitCode, eax
0x1800f2c49  mov     cs:ServiceStatus.dwCurrentState, r13d
0x1800f2c50  mov     cs:ServiceStatus.dwServiceSpecificExitCode, ebx
0x1800f2c56  mov     [rbp+170h+var_1D0], ebx
0x1800f2c59  mov     [rbp+170h+var_1C8], edi
0x1800f2c5c  jz      short loc_1800F2C9E
0x1800f2c5e  test    qword ptr cs:xmmword_180169738+8, r14
0x1800f2c65  jz      short loc_1800F2C9E
0x1800f2c67  mov     rax, rcx
0x1800f2c6a  and     rax, r14
0x1800f2c6d  cmp     rcx, rax
0x1800f2c70  jnz     short loc_1800F2C9E
0x1800f2c72  lea     rax, [rbp+170h+var_1D0]
0x1800f2c76  mov     [rsp+270h+var_240], rsi
0x1800f2c7b  mov     [rsp+270h+var_248], rax
0x1800f2c80  lea     r9, [rbp+170h+var_1C8]
0x1800f2c84  mov     r8d, 2
0x1800f2c8a  mov     [rsp+270h+var_250], rsi
0x1800f2c8f  lea     rdx, PLA_EVENT_SVC_STOP
0x1800f2c96  mov     rcx, r12
0x1800f2c99  call    EventingWriteEvent
0x1800f2c9e  mov     rcx, cs:hServiceStatus; hServiceStatus
0x1800f2ca5  test    rcx, rcx
0x1800f2ca8  jz      short loc_1800F2CB7
0x1800f2caa  lea     rdx, ServiceStatus; lpServiceStatus
0x1800f2cb1  call    cs:__imp_SetServiceStatus
0x1800f2cb7  mov     rcx, [rbp+170h+var_40]
0x1800f2cbe  xor     rcx, rsp; StackCookie
0x1800f2cc1  call    __security_check_cookie
0x1800f2cc6  add     rsp, 240h
0x1800f2ccd  pop     r14
0x1800f2ccf  pop     r13
0x1800f2cd1  pop     r12
0x1800f2cd3  pop     rdi
0x1800f2cd4  pop     rsi
0x1800f2cd5  pop     rbx
0x1800f2cd6  pop     rbp
0x1800f2cd7  retn
```
