# RpcUnRegisterAsyncNotificationEx

- ea: `0x18001b0f0`
- end: `0x18001b4ff`
- name: `RpcUnRegisterAsyncNotificationEx`
- size: `1039`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800077a0`
- `0x180009580`
- `0x1800101b0`
- `0x180010260`
- `0x18001b0f0`
- `0x18001b510`
- `0x180029158`
- `0x18004e850`
- `0x18004f354`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001b491`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001b491`
- `ntdll!NtQueryInformationProcess` at `0x18001b46f`
- `ntdll!NtQueryInformationProcess` at `0x18001b46f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b284`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b284`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4ed`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001b270`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001b4d9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001b270`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001b4d9`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18001b1f1`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18001b1f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b4c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b4c0`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001b156`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001b156`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001b1ce`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001b1ce`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001b43d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001b43d`

## string_xrefs

- `0x18001b2e7`: `%s with Trace ID 0x%x Completed`
- `0x18001b3a5`: `TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC`
- `0x18001b321`: `RPC Caller: PID %d, SessID %d, Process Name: <%S>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RpcUnRegisterAsyncNotificationEx(_QWORD **a1)
{
  unsigned int v2; // edi
  RPC_STATUS v3; // eax
  int v4; // ebx
  unsigned int v5; // ebx
  HANDLE v7; // rax
  void *v8; // r14
  NTSTATUS InformationProcess; // eax
  wchar_t *v10; // rax
  wchar_t *v11; // rax
  struct CTraceBase *v12; // [rsp+30h] [rbp-D0h] BYREF
  void **v13; // [rsp+40h] [rbp-C0h] BYREF
  GUID pguid; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v15[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct CTraceBase *v16; // [rsp+60h] [rbp-A0h] BYREF
  int v17; // [rsp+68h] [rbp-98h]
  const char *v18; // [rsp+70h] [rbp-90h]
  unsigned int Pid[2]; // [rsp+78h] [rbp-88h] BYREF
  int v20; // [rsp+80h] [rbp-80h]
  unsigned __int16 v21[262]; // [rsp+84h] [rbp-7Ch] BYREF
  _BYTE ProcessInformation[8]; // [rsp+290h] [rbp+190h] BYREF
  wchar_t *Str; // [rsp+298h] [rbp+198h]

  v13 = &CTraceBase::`vftable';
  v15[1] = 1;
  v16 = 0;
  if ( CTraceBase::g_bEnabled )
  {
    if ( (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(2, "Adding trace %p, %d, %s", &v13, 1, "RpcUnRegisterAsyncNotificationEx");
    v12 = 0;
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v12) >= 0 && v12 && (g_DebugTraceComponent & 1) != 0 )
      _DbgPrintMessage(
        2,
        "TraceComponent %d: Warning TLS should be empty, this is OK if RPC function call another RPC",
        1);
    CTraceBase::ResetThreadCurrentOperationTrace(0, 0);
    if ( (int)CTraceBase::GetThreadCurrentOperationTrace(&v16) >= 0 && v16 )
    {
      (*(void (__fastcall **)(struct CTraceBase *, GUID *))(*(_QWORD *)v16 + 32LL))(v16, &pguid);
      v15[0] = (*(__int64 (__fastcall **)(struct CTraceBase *))(*(_QWORD *)v16 + 24LL))(v16);
      v17 = 1;
      goto LABEL_4;
    }
    CTraceBase::ResetThreadCurrentOperationTrace((struct CTraceBase *)&v13, "RpcUnRegisterAsyncNotificationEx");
    CTraceBase::GenerateTraceID(&pguid, v15);
  }
  else
  {
    CoCreateGuid(&pguid);
    v15[0] = _InterlockedIncrement((volatile signed __int32 *)&CTraceBase::g_NextShortActivityID);
  }
  v17 = 0;
LABEL_4:
  v13 = &CRpcCallTrace::`vftable';
  v18 = "RpcUnRegisterAsyncNotificationEx";
  *(_QWORD *)Pid = -1;
  v20 = 0;
  memset_0(v21, 0, 0x208u);
  if ( v20 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "TRACE RPC %s with Trace ID 0x%x", v18, v15[0]);
  v2 = 0;
  if ( (g_DebugTraceComponent & 1) != 0 )
    v2 = 260;
  *(_QWORD *)Pid = -1;
  v3 = I_RpcBindingInqLocalClientPID(0, &Pid[1]);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 >= 0 )
  {
    ProcessIdToSessionId(Pid[1], Pid);
    if ( v2 )
    {
      v7 = OpenProcess(0x400u, 0, Pid[1]);
      v8 = v7;
      if ( v7 )
      {
        InformationProcess = NtQueryInformationProcess(v7, ProcessImageFileName, ProcessInformation, 0x110u, 0);
        v4 = InformationProcess | 0x10000000;
        if ( InformationProcess >= 0 )
        {
          v10 = wcsrchr(Str, 0x5Cu);
          if ( v10 )
            v11 = v10 + 1;
          else
            v11 = Str;
          StringCchCopyW(v21, v2, v11);
        }
        CloseHandle(v8);
      }
    }
  }
  if ( v20 )
  {
    if ( v4 < 0 )
    {
      if ( (g_DebugTraceComponent & 1) != 0 )
        _DbgPrintMessage(2, "RPC Caller: Unknown");
    }
    else if ( (g_DebugTraceComponent & 1) != 0 )
    {
      _DbgPrintMessage(2, "RPC Caller: PID %d, SessID %d, Process Name: <%S>", Pid[1], Pid[0], v21);
    }
  }
  v5 = RpcUnRegisterAsyncNotification(a1);
  v13 = &CRpcCallTrace::`vftable';
  if ( v20 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "%s with Trace ID 0x%x Completed", v18, v15[0]);
  v13 = &CTraceBase::`vftable';
  if ( CTraceBase::g_bEnabled && !v17 && CTraceBase::g_TLSIndex != -1 )
  {
    if ( !TlsSetValue(CTraceBase::g_TLSIndex, 0) )
    {
      GetLastError();
LABEL_46:
      GetLastError();
      return v5;
    }
    if ( !TlsSetValue(CTraceBase::g_CreatorFunctionTLSIndex, 0) )
      goto LABEL_46;
  }
  return v5;
}

```

## disassembly

```asm
0x18001b0f0  push    rbp
0x18001b0f2  push    rbx
0x18001b0f3  push    rsi
0x18001b0f4  push    rdi
0x18001b0f5  push    r12
0x18001b0f7  push    r13
0x18001b0f9  push    r14
0x18001b0fb  push    r15
0x18001b0fd  lea     rbp, [rsp-2B8h]
0x18001b105  sub     rsp, 3B8h
0x18001b10c  mov     rax, cs:__security_cookie
0x18001b113  xor     rax, rsp
0x18001b116  mov     [rbp+2F0h+var_50], rax
0x18001b11d  mov     rsi, rcx
0x18001b120  lea     r12, ??_7CTraceBase@@6B@; const CTraceBase::`vftable'
0x18001b127  mov     [rsp+3F0h+var_3B0], r12
0x18001b12c  mov     ebx, 1
0x18001b131  mov     [rsp+3F0h+var_394], ebx
0x18001b135  xor     r15d, r15d
0x18001b138  mov     [rsp+3F0h+var_390], r15
0x18001b13d  lea     rdi, aRpcunregistera_0; "RpcUnRegisterAsyncNotificationEx"
0x18001b144  cmp     cs:?g_bEnabled@CTraceBase@@0HA, r15d; int CTraceBase::g_bEnabled
0x18001b14b  jnz     loc_18001B35A
0x18001b151  lea     rcx, [rsp+3F0h+pguid]; pguid
0x18001b156  call    cs:__imp_CoCreateGuid
0x18001b15d  nop     dword ptr [rax+rax+00h]
0x18001b162  lock xadd cs:?g_NextShortActivityID@CTraceBase@@0KA, ebx; ulong CTraceBase::g_NextShortActivityID
0x18001b16a  inc     ebx
0x18001b16c  mov     [rsp+3F0h+var_398], ebx
0x18001b170  mov     [rsp+3F0h+var_388], r15d
0x18001b175  lea     r13, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x18001b17c  mov     [rsp+3F0h+var_3B0], r13
0x18001b181  mov     [rsp+3F0h+var_380], rdi
0x18001b186  mov     qword ptr [rsp+3F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18001b18f  mov     [rbp+2F0h+var_370], r15d
0x18001b193  xor     edx, edx; Val
0x18001b195  mov     r8d, 208h; Size
0x18001b19b  lea     rcx, [rbp+2F0h+var_36C]; void *
0x18001b19f  call    memset_0
0x18001b1a4  cmp     [rbp+2F0h+var_370], r15d
0x18001b1a8  jnz     loc_18001B2A3
0x18001b1ae  mov     edi, r15d
0x18001b1b1  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18001b1b8  jnz     loc_18001B427
0x18001b1be  mov     qword ptr [rsp+3F0h+Pid], 0FFFFFFFFFFFFFFFFh
0x18001b1c7  lea     rdx, [rsp+3F0h+Pid+4]; Pid
0x18001b1cc  xor     ecx, ecx; Binding
0x18001b1ce  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18001b1d5  nop     dword ptr [rax+rax+00h]
0x18001b1da  mov     ebx, eax
0x18001b1dc  test    eax, eax
0x18001b1de  jg      loc_18001B295
0x18001b1e4  test    ebx, ebx
0x18001b1e6  js      short loc_18001B205
0x18001b1e8  lea     rdx, [rsp+3F0h+Pid]; pSessionId
0x18001b1ed  mov     ecx, [rsp+3F0h+Pid+4]; dwProcessId
0x18001b1f1  call    cs:__imp_ProcessIdToSessionId
0x18001b1f8  nop     dword ptr [rax+rax+00h]
0x18001b1fd  test    edi, edi
0x18001b1ff  jnz     loc_18001B431
0x18001b205  cmp     [rbp+2F0h+var_370], r15d
0x18001b209  jnz     loc_18001B2FD
0x18001b20f  mov     rcx, rsi
0x18001b212  call    RpcUnRegisterAsyncNotification
0x18001b217  mov     ebx, eax
0x18001b219  mov     [rsp+3F0h+var_3B0], r13
0x18001b21e  cmp     [rbp+2F0h+var_370], 0
0x18001b222  jnz     loc_18001B2D0
0x18001b228  mov     [rsp+3F0h+var_3B0], r12
0x18001b22d  cmp     cs:?g_bEnabled@CTraceBase@@0HA, 0; int CTraceBase::g_bEnabled
0x18001b234  jnz     short loc_18001B25C
0x18001b236  mov     eax, ebx
0x18001b238  mov     rcx, [rbp+2F0h+var_50]
0x18001b23f  xor     rcx, rsp; StackCookie
0x18001b242  call    __security_check_cookie
0x18001b247  add     rsp, 3B8h
0x18001b24e  pop     r15
0x18001b250  pop     r14
0x18001b252  pop     r13
0x18001b254  pop     r12
0x18001b256  pop     rdi
0x18001b257  pop     rsi
0x18001b258  pop     rbx
0x18001b259  pop     rbp
0x18001b25a  retn
0x18001b25c  cmp     [rsp+3F0h+var_388], 0
0x18001b261  jnz     short loc_18001B236
0x18001b263  mov     ecx, cs:?g_TLSIndex@CTraceBase@@0KA; dwTlsIndex
0x18001b269  cmp     ecx, 0FFFFFFFFh
0x18001b26c  jz      short loc_18001B236
0x18001b26e  xor     edx, edx; lpTlsValue
0x18001b270  call    cs:__imp_TlsSetValue
0x18001b277  nop     dword ptr [rax+rax+00h]
0x18001b27c  test    eax, eax
0x18001b27e  jnz     loc_18001B4D1
0x18001b284  call    cs:__imp_GetLastError
0x18001b28b  nop     dword ptr [rax+rax+00h]
0x18001b290  jmp     loc_18001B4ED
0x18001b295  movzx   ebx, ax
0x18001b298  or      ebx, 80070000h
0x18001b29e  jmp     loc_18001B1E4
0x18001b2a3  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18001b2aa  jz      loc_18001B1AE
0x18001b2b0  mov     r9d, [rsp+3F0h+var_398]
0x18001b2b5  mov     r8, [rsp+3F0h+var_380]
0x18001b2ba  lea     rdx, aTraceRpcSWithT; "TRACE RPC %s with Trace ID 0x%x"
0x18001b2c1  mov     ecx, 2; int
0x18001b2c6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001b2cb  jmp     loc_18001B1AE
0x18001b2d0  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18001b2d7  jz      loc_18001B228
0x18001b2dd  mov     r9d, [rsp+3F0h+var_398]
0x18001b2e2  mov     r8, [rsp+3F0h+var_380]
0x18001b2e7  lea     rdx, aSWithTraceId0x; "%s with Trace ID 0x%x Completed"
0x18001b2ee  mov     ecx, 2; int
0x18001b2f3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001b2f8  jmp     loc_18001B228
0x18001b2fd  test    ebx, ebx
0x18001b2ff  js      short loc_18001B337
0x18001b301  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18001b308  jz      loc_18001B20F
0x18001b30e  lea     rax, [rbp+2F0h+var_36C]
0x18001b312  mov     [rsp+3F0h+ReturnLength], rax
0x18001b317  mov     r9d, [rsp+3F0h+Pid]
0x18001b31c  mov     r8d, [rsp+3F0h+Pid+4]
0x18001b321  lea     rdx, aRpcCallerPidDS; "RPC Caller: PID %d, SessID %d, Process "...
0x18001b328  mov     ecx, 2; int
0x18001b32d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001b332  jmp     loc_18001B20F
0x18001b337  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x18001b33e  jz      loc_18001B20F
0x18001b344  lea     rdx, aRpcCallerUnkno; "RPC Caller: Unknown"
0x18001b34b  mov     ecx, 2; int
0x18001b350  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001b355  jmp     loc_18001B20F
0x18001b35a  test    byte ptr cs:?g_DebugTraceComponent@@3KA, bl; ulong g_DebugTraceComponent
0x18001b360  jz      short loc_18001B380
0x18001b362  mov     [rsp+3F0h+ReturnLength], rdi
0x18001b367  mov     r9d, ebx
0x18001b36a  lea     r8, [rsp+3F0h+var_3B0]
0x18001b36f  lea     rdx, aAddingTracePDS; "Adding trace %p, %d, %s"
0x18001b376  mov     ecx, 2; int
0x18001b37b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001b380  mov     [rsp+3F0h+var_3C0], r15
0x18001b385  lea     rcx, [rsp+3F0h+var_3C0]; struct CTraceBase **
0x18001b38a  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18001b38f  test    eax, eax
0x18001b391  js      short loc_18001B3B6
0x18001b393  cmp     [rsp+3F0h+var_3C0], r15
0x18001b398  jz      short loc_18001B3B6
0x18001b39a  test    byte ptr cs:?g_DebugTraceComponent@@3KA, bl; ulong g_DebugTraceComponent
0x18001b3a0  jz      short loc_18001B3B6
0x18001b3a2  mov     r8d, ebx
0x18001b3a5  lea     rdx, aTracecomponent; "TraceComponent %d: Warning TLS should b"...
0x18001b3ac  mov     ecx, 2; int
0x18001b3b1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001b3b6  xor     edx, edx; char *
0x18001b3b8  xor     ecx, ecx; lpTlsValue
0x18001b3ba  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18001b3bf  lea     rcx, [rsp+3F0h+var_390]; struct CTraceBase **
0x18001b3c4  call    ?GetThreadCurrentOperationTrace@CTraceBase@@SAJPEAPEAV1@@Z; CTraceBase::GetThreadCurrentOperationTrace(CTraceBase * *)
0x18001b3c9  test    eax, eax
0x18001b3cb  js      short loc_18001B406
0x18001b3cd  mov     rcx, [rsp+3F0h+var_390]
0x18001b3d2  test    rcx, rcx
0x18001b3d5  jz      short loc_18001B406
0x18001b3d7  mov     rax, [rcx]
0x18001b3da  lea     rdx, [rsp+3F0h+pguid]
0x18001b3df  mov     rax, [rax+20h]
0x18001b3e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3e8  mov     rcx, [rsp+3F0h+var_390]
0x18001b3ed  mov     rax, [rcx]
0x18001b3f0  mov     rax, [rax+18h]
0x18001b3f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3f9  mov     [rsp+3F0h+var_398], eax
0x18001b3fd  mov     [rsp+3F0h+var_388], ebx
0x18001b401  jmp     loc_18001B175
0x18001b406  mov     rdx, rdi; char *
0x18001b409  lea     rcx, [rsp+3F0h+var_3B0]; lpTlsValue
0x18001b40e  call    ?ResetThreadCurrentOperationTrace@CTraceBase@@SAJPEAV1@PEBD@Z; CTraceBase::ResetThreadCurrentOperationTrace(CTraceBase *,char const *)
0x18001b413  lea     rdx, [rsp+3F0h+var_398]; unsigned int *
0x18001b418  lea     rcx, [rsp+3F0h+pguid]; struct _GUID *
0x18001b41d  call    ?GenerateTraceID@CTraceBase@@KAJPEAU_GUID@@PEAK@Z; CTraceBase::GenerateTraceID(_GUID *,ulong *)
0x18001b422  jmp     loc_18001B170
0x18001b427  mov     edi, 104h
0x18001b42c  jmp     loc_18001B1BE
0x18001b431  mov     r8d, [rsp+3F0h+Pid+4]; dwProcessId
0x18001b436  xor     edx, edx; bInheritHandle
0x18001b438  mov     ecx, 400h; dwDesiredAccess
0x18001b43d  call    cs:__imp_OpenProcess
0x18001b444  nop     dword ptr [rax+rax+00h]
0x18001b449  mov     r14, rax
0x18001b44c  test    rax, rax
0x18001b44f  jz      loc_18001B205
0x18001b455  mov     [rsp+3F0h+ReturnLength], r15; ReturnLength
0x18001b45a  mov     r9d, 110h; ProcessInformationLength
0x18001b460  lea     r8, [rbp+2F0h+ProcessInformation]; ProcessInformation
0x18001b467  mov     edx, 1Bh; ProcessInformationClass
0x18001b46c  mov     rcx, rax; ProcessHandle
0x18001b46f  call    cs:__imp_NtQueryInformationProcess
0x18001b476  nop     dword ptr [rax+rax+00h]
0x18001b47b  mov     ebx, eax
0x18001b47d  or      ebx, 10000000h
0x18001b483  jl      short loc_18001B4BD
0x18001b485  mov     edx, 5Ch ; '\'; Ch
0x18001b48a  mov     rcx, [rbp+2F0h+Str]; Str
0x18001b491  call    cs:__imp_wcsrchr
0x18001b498  nop     dword ptr [rax+rax+00h]
0x18001b49d  test    rax, rax
0x18001b4a0  jnz     short loc_18001B4AB
0x18001b4a2  mov     rax, [rbp+2F0h+Str]
0x18001b4a9  jmp     short loc_18001B4AF
0x18001b4ab  add     rax, 2
0x18001b4af  mov     edx, edi; unsigned __int64
0x18001b4b1  mov     r8, rax; unsigned __int16 *
0x18001b4b4  lea     rcx, [rbp+2F0h+var_36C]; unsigned __int16 *
0x18001b4b8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b4bd  mov     rcx, r14; hObject
0x18001b4c0  call    cs:__imp_CloseHandle
0x18001b4c7  nop     dword ptr [rax+rax+00h]
0x18001b4cc  jmp     loc_18001B205
0x18001b4d1  xor     edx, edx; lpTlsValue
0x18001b4d3  mov     ecx, cs:?g_CreatorFunctionTLSIndex@CTraceBase@@0KA; dwTlsIndex
0x18001b4d9  call    cs:__imp_TlsSetValue
0x18001b4e0  nop     dword ptr [rax+rax+00h]
0x18001b4e5  test    eax, eax
0x18001b4e7  jnz     loc_18001B236
0x18001b4ed  call    cs:__imp_GetLastError
0x18001b4f4  nop     dword ptr [rax+rax+00h]
0x18001b4f9  jmp     loc_18001B236
```
