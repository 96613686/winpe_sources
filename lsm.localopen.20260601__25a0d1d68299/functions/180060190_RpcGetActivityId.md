# RpcGetActivityId

- ea: `0x180060190`
- end: `0x18006051c`
- name: `RpcGetActivityId`
- size: `908`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800077a0`
- `0x18000c684`
- `0x18000e8b0`
- `0x18000f260`
- `0x18001e6f0`
- `0x180022200`
- `0x18004e850`
- `0x18004ec20`
- `0x18004ed00`
- `0x180056538`
- `0x180058fc8`
- `0x18005a890`
- `0x18005c760`
- `0x18005c7bc`
- `0x18005c7f4`
- `0x18005c918`
- `0x18005f10c`
- `0x18005f258`
- `0x180060190`
- `0x18009c010`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x18006031b`
- `ntdll!NtQueryInformationProcess` at `0x18006035c`
- `ntdll!NtQueryInformationProcess` at `0x18006031b`
- `ntdll!NtQueryInformationProcess` at `0x18006035c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180060392`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180060392`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800602b8`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800602b8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800602e4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800602e4`

## string_xrefs

- `0x1800603dc`: `CheckAccessToSession(WINSTATION_QUERY) failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall RpcGetActivityId(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rax
  struct wil::CallContextInfo *v5; // r8
  bool v6; // r9
  int v7; // esi
  const char *v8; // r8
  unsigned int v9; // edi
  RPC_STATUS v10; // eax
  bool v11; // sf
  HANDLE v12; // rbx
  NTSTATUS InformationProcess; // edi
  _QWORD *v14; // r14
  NTSTATUS v15; // eax
  const struct std::nothrow_t *v16; // rdx
  struct ITSSession *v17; // rbx
  int v18; // eax
  int v19; // eax
  int v20; // eax
  _QWORD *v21; // rax
  ULONG ProcessInformationLength[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int Pid; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v26; // [rsp+48h] [rbp-B8h] BYREF
  struct ITSSession *v27[2]; // [rsp+50h] [rbp-B0h] BYREF
  void **v28; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v29[48]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v30; // [rsp+98h] [rbp-68h]
  _BYTE v31[592]; // [rsp+A0h] [rbp-60h] BYREF

  *(_QWORD *)ProcessInformationLength = 0;
  v4 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::ensure_data(ProcessInformationLength);
  tip2::details::shared_data<0,0,0>::start(*v4 + 8LL, v27);
  v28 = &tip2::test_watcher<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::`vftable';
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v29,
    (struct wil::details::IFailureCallback *)&v28,
    v5,
    v6);
  v7 = 1;
  v30 = *(_QWORD *)ProcessInformationLength;
  if ( *(_QWORD *)ProcessInformationLength )
    _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)ProcessInformationLength + 280LL), 1u);
  wil::com_ptr_t<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>,wil::err_returncode_policy>(ProcessInformationLength);
  v24 = v30;
  if ( v30 )
    _InterlockedAdd((volatile signed __int32 *)(v30 + 280), 1u);
  tip2::test_watcher<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::~test_watcher<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>(&v28);
  v27[0] = 0;
  v26 = 0;
  Pid = 0;
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v31, 0, "RpcGetActivityId");
  if ( !a1 )
  {
    v8 = "hSession";
LABEL_7:
    _DbgPrintMessage(8, "Missing paramter %s in %s", v8, "RpcGetActivityId");
    v9 = -2147024809;
    goto LABEL_29;
  }
  if ( !a2 )
  {
    v8 = "pActivityId";
    goto LABEL_7;
  }
  v10 = I_RpcBindingInqLocalClientPID(0, &Pid);
  v11 = v10 < 0;
  if ( v10 > 0 )
    v11 = 1;
  if ( v11 )
    goto LABEL_20;
  v12 = OpenProcess(0x1000u, 0, Pid);
  if ( !v12 )
    goto LABEL_20;
  ProcessInformationLength[0] = 0;
  InformationProcess = NtQueryInformationProcess(
                         v12,
                         ProcessImageFileMapping|ProcessUserModeIOPL,
                         0,
                         0,
                         ProcessInformationLength);
  if ( InformationProcess == -1073741820 && ProcessInformationLength[0] > 0x10 )
  {
    v14 = operator new[](ProcessInformationLength[0]);
    v15 = NtQueryInformationProcess(
            v12,
            ProcessImageFileMapping|ProcessUserModeIOPL,
            v14,
            ProcessInformationLength[0],
            0);
    InformationProcess = v15 | 0x10000000;
    if ( v15 >= 0 )
      tip2::tip_test<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::log(
        &v24,
        v14[1]);
    operator delete(v14, v16);
  }
  CloseHandle(v12);
  if ( InformationProcess < 0 )
LABEL_20:
    tip2::tip_test<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::log(
      &v24,
      L"Could not get RPC caller's cmdline");
  SmartPtr<ITSSession>::operator=(v27, *(_QWORD *)(a1 + 1592));
  v17 = v27[0];
  v18 = CheckAccessToSession(v27[0], 1u, 0);
  v9 = v18;
  if ( v18 >= 0 )
  {
    v19 = (**(__int64 (__fastcall ***)(struct ITSSession *, __int64 *, __int64 *))v17)(v17, qword_1800AE500, &v26);
    v9 = v19;
    if ( v19 >= 0 )
    {
      v20 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 584LL))(v26, a2);
      v9 = v20;
      if ( v20 >= 0 )
      {
        v7 = 4;
      }
      else
      {
        v7 = 3;
        _DbgPrintMessage(8, "SessionPrivate->GetActivityId failed: 0x%x in %s", (unsigned int)v20, "RpcGetActivityId");
      }
    }
    else
    {
      v7 = 2;
      _DbgPrintMessage(
        8,
        "Getting IID_ITSSessionPrivate for session failed: 0x%x in %s",
        (unsigned int)v19,
        "RpcGetActivityId");
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "CheckAccessToSession(WINSTATION_QUERY) failed: 0x%x in %s",
      (unsigned int)v18,
      "RpcGetActivityId");
  }
LABEL_29:
  *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::operator->(
                           &v24,
                           ProcessInformationLength)
            + 272LL) = v9;
  tip2::test_data_control<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::~test_data_control<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>(ProcessInformationLength);
  *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::operator->(
                           &v24,
                           ProcessInformationLength)
            + 276LL) = v7;
  tip2::test_data_control<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::~test_data_control<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>(ProcessInformationLength);
  v21 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::operator->(
                    &v24,
                    ProcessInformationLength);
  tip2::details::shared_data<0,0,0>::complete_helper(*v21 + 8LL, 2048, 10);
  tip2::test_data_control<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::~test_data_control<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>(ProcessInformationLength);
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v31);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v26);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(v27);
  wil::com_ptr_t<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>,wil::err_returncode_policy>(&v24);
  return v9;
}

```

## disassembly

```asm
0x180060190  mov     [rsp-8+arg_10], rbx
0x180060195  mov     [rsp-8+arg_18], rsi
0x18006019a  push    rbp
0x18006019b  push    rdi
0x18006019c  push    r13
0x18006019e  push    r14
0x1800601a0  push    r15
0x1800601a2  lea     rbp, [rsp-200h]
0x1800601aa  sub     rsp, 300h
0x1800601b1  mov     rax, cs:__security_cookie
0x1800601b8  xor     rax, rsp
0x1800601bb  mov     [rbp+220h+var_30], rax
0x1800601c2  mov     r13, rcx
0x1800601c5  mov     qword ptr [rsp+320h+ProcessInformationLength], 0
0x1800601ce  lea     rcx, [rsp+320h+ProcessInformationLength]
0x1800601d3  mov     r15, rdx
0x1800601d6  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::ensure_data(void)
0x1800601db  lea     rdx, [rsp+320h+var_2D0]
0x1800601e0  mov     rcx, [rax]
0x1800601e3  add     rcx, 8
0x1800601e7  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x1800601ec  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::`vftable'
0x1800601f3  lea     rdx, [rsp+320h+var_2C0]; struct wil::details::IFailureCallback *
0x1800601f8  mov     [rsp+320h+var_2C0], rax
0x1800601fd  lea     rcx, [rsp+320h+var_2B8]; this
0x180060202  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x180060207  mov     rax, qword ptr [rsp+320h+ProcessInformationLength]
0x18006020c  mov     esi, 1
0x180060211  mov     [rbp+220h+var_288], rax
0x180060215  test    rax, rax
0x180060218  jz      short loc_180060221
0x18006021a  lock add [rax+118h], esi
0x180060221  lea     rcx, [rsp+320h+ProcessInformationLength]
0x180060226  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>,wil::err_returncode_policy>(void)
0x18006022b  mov     rax, [rbp+220h+var_288]
0x18006022f  mov     [rsp+320h+var_2E8], rax
0x180060234  test    rax, rax
0x180060237  jz      short loc_180060240
0x180060239  lock add [rax+118h], esi
0x180060240  lea     rcx, [rsp+320h+var_2C0]
0x180060245  call    ??1?$test_watcher@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::~test_watcher<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>(void)
0x18006024a  lea     r14, aRpcgetactivity; "RpcGetActivityId"
0x180060251  mov     [rsp+320h+var_2D0], 0
0x18006025a  mov     r8, r14; char *
0x18006025d  mov     [rsp+320h+var_2D8], 0
0x180060266  xor     edx, edx; int
0x180060268  mov     [rsp+320h+Pid], 0
0x180060270  lea     rcx, [rbp+220h+var_280]; this
0x180060274  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x180060279  test    r13, r13
0x18006027c  jnz     short loc_1800602A3
0x18006027e  lea     r8, aHsession; "hSession"
0x180060285  mov     r9, r14
0x180060288  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18006028f  mov     ecx, 8; int
0x180060294  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180060299  mov     edi, 80070057h
0x18006029e  jmp     loc_180060453
0x1800602a3  test    r15, r15
0x1800602a6  jnz     short loc_1800602B1
0x1800602a8  lea     r8, aPactivityid; "pActivityId"
0x1800602af  jmp     short loc_180060285
0x1800602b1  lea     rdx, [rsp+320h+Pid]; Pid
0x1800602b6  xor     ecx, ecx; Binding
0x1800602b8  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x1800602bf  nop     dword ptr [rax+rax+00h]
0x1800602c4  test    eax, eax
0x1800602c6  jle     short loc_1800602D2
0x1800602c8  movzx   eax, ax
0x1800602cb  or      eax, 80070000h
0x1800602d0  test    eax, eax
0x1800602d2  js      loc_1800603A2
0x1800602d8  mov     r8d, [rsp+320h+Pid]; dwProcessId
0x1800602dd  xor     edx, edx; bInheritHandle
0x1800602df  mov     ecx, 1000h; dwDesiredAccess
0x1800602e4  call    cs:__imp_OpenProcess
0x1800602eb  nop     dword ptr [rax+rax+00h]
0x1800602f0  mov     rbx, rax
0x1800602f3  test    rax, rax
0x1800602f6  jz      loc_1800603A2
0x1800602fc  xor     r9d, r9d; ProcessInformationLength
0x1800602ff  mov     [rsp+320h+ProcessInformationLength], 0
0x180060307  lea     rax, [rsp+320h+ProcessInformationLength]
0x18006030c  xor     r8d, r8d; ProcessInformation
0x18006030f  mov     rcx, rbx; ProcessHandle
0x180060312  mov     [rsp+320h+ReturnLength], rax; ReturnLength
0x180060317  lea     edx, [r9+3Ch]; ProcessInformationClass
0x18006031b  call    cs:__imp_NtQueryInformationProcess
0x180060322  nop     dword ptr [rax+rax+00h]
0x180060327  mov     edi, eax
0x180060329  cmp     eax, 0C0000004h
0x18006032e  jnz     short loc_18006038F
0x180060330  cmp     [rsp+320h+ProcessInformationLength], 10h
0x180060335  jbe     short loc_18006038F
0x180060337  mov     ecx, [rsp+320h+ProcessInformationLength]; unsigned __int64
0x18006033b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180060340  mov     r9d, [rsp+320h+ProcessInformationLength]; ProcessInformationLength
0x180060345  mov     r8, rax; ProcessInformation
0x180060348  mov     edx, 3Ch ; '<'; ProcessInformationClass
0x18006034d  mov     [rsp+320h+ReturnLength], 0; ReturnLength
0x180060356  mov     rcx, rbx; ProcessHandle
0x180060359  mov     r14, rax
0x18006035c  call    cs:__imp_NtQueryInformationProcess
0x180060363  nop     dword ptr [rax+rax+00h]
0x180060368  mov     edi, eax
0x18006036a  or      edi, 10000000h
0x180060370  jl      short loc_180060380
0x180060372  mov     rdx, [r14+8]
0x180060376  lea     rcx, [rsp+320h+var_2E8]
0x18006037b  call    ?log@?$tip_test@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@@tip2@@QEAAXPEBG@Z; tip2::tip_test<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::log(ushort const *)
0x180060380  mov     rcx, r14; void *
0x180060383  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180060388  lea     r14, aRpcgetactivity; "RpcGetActivityId"
0x18006038f  mov     rcx, rbx; hObject
0x180060392  call    cs:__imp_CloseHandle
0x180060399  nop     dword ptr [rax+rax+00h]
0x18006039e  test    edi, edi
0x1800603a0  jns     short loc_1800603B3
0x1800603a2  lea     rdx, aCouldNotGetRpc; "Could not get RPC caller's cmdline"
0x1800603a9  lea     rcx, [rsp+320h+var_2E8]
0x1800603ae  call    ?log@?$tip_test@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@@tip2@@QEAAXPEBG@Z; tip2::tip_test<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::log(ushort const *)
0x1800603b3  mov     rdx, [r13+638h]
0x1800603ba  lea     rcx, [rsp+320h+var_2D0]
0x1800603bf  call    ??4?$SmartPtr@UITSSession@@@@QEAAAEAV0@PEAUITSSession@@@Z; SmartPtr<ITSSession>::operator=(ITSSession *)
0x1800603c4  mov     rbx, [rsp+320h+var_2D0]
0x1800603c9  xor     r8d, r8d; int
0x1800603cc  mov     rcx, rbx; struct ITSSession *
0x1800603cf  mov     edx, esi; unsigned int
0x1800603d1  call    ?CheckAccessToSession@@YAJPEAUITSSession@@KH@Z; CheckAccessToSession(ITSSession *,ulong,int)
0x1800603d6  mov     edi, eax
0x1800603d8  test    eax, eax
0x1800603da  jns     short loc_1800603F5
0x1800603dc  lea     rdx, aCheckaccesstos_5; "CheckAccessToSession(WINSTATION_QUERY) "...
0x1800603e3  mov     r9, r14
0x1800603e6  mov     r8d, eax
0x1800603e9  mov     ecx, 8; int
0x1800603ee  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800603f3  jmp     short loc_180060453
0x1800603f5  mov     rax, [rbx]
0x1800603f8  lea     r8, [rsp+320h+var_2D8]
0x1800603fd  lea     rdx, qword_1800AE500
0x180060404  mov     rcx, rbx
0x180060407  mov     rax, [rax]
0x18006040a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006040f  mov     edi, eax
0x180060411  test    eax, eax
0x180060413  jns     short loc_180060423
0x180060415  mov     esi, 2
0x18006041a  lea     rdx, aGettingIidItss_1; "Getting IID_ITSSessionPrivate for sessi"...
0x180060421  jmp     short loc_1800603E3
0x180060423  mov     rcx, [rsp+320h+var_2D8]
0x180060428  mov     rdx, r15
0x18006042b  mov     rax, [rcx]
0x18006042e  mov     rax, [rax+248h]
0x180060435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006043a  mov     edi, eax
0x18006043c  test    eax, eax
0x18006043e  jns     short loc_18006044E
0x180060440  mov     esi, 3
0x180060445  lea     rdx, aSessionprivate; "SessionPrivate->GetActivityId failed: 0"...
0x18006044c  jmp     short loc_1800603E3
0x18006044e  mov     esi, 4
0x180060453  lea     rdx, [rsp+320h+ProcessInformationLength]
0x180060458  lea     rcx, [rsp+320h+var_2E8]
0x18006045d  call    ??C?$tip_test@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::operator->(void)
0x180060462  mov     rcx, [rax]
0x180060465  mov     [rcx+110h], edi
0x18006046b  lea     rcx, [rsp+320h+ProcessInformationLength]
0x180060470  call    ??1?$test_data_control@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::~test_data_control<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>(void)
0x180060475  lea     rdx, [rsp+320h+ProcessInformationLength]
0x18006047a  lea     rcx, [rsp+320h+var_2E8]
0x18006047f  call    ??C?$tip_test@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::operator->(void)
0x180060484  mov     rcx, [rax]
0x180060487  mov     [rcx+114h], esi
0x18006048d  lea     rcx, [rsp+320h+ProcessInformationLength]
0x180060492  call    ??1?$test_data_control@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::~test_data_control<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>(void)
0x180060497  lea     rdx, [rsp+320h+ProcessInformationLength]
0x18006049c  lea     rcx, [rsp+320h+var_2E8]
0x1800604a1  call    ??C?$tip_test@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::operator->(void)
0x1800604a6  mov     edx, 800h
0x1800604ab  mov     r8d, 0Ah
0x1800604b1  mov     rcx, [rax]
0x1800604b4  add     rcx, 8
0x1800604b8  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestFlags@@W4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestFlags,TestQueryOptions)
0x1800604bd  lea     rcx, [rsp+320h+ProcessInformationLength]
0x1800604c2  call    ??1?$test_data_control@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::~test_data_control<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>(void)
0x1800604c7  lea     rcx, [rbp+220h+var_280]; this
0x1800604cb  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x1800604d0  lea     rcx, [rsp+320h+var_2D8]
0x1800604d5  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x1800604da  lea     rcx, [rsp+320h+var_2D0]
0x1800604df  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x1800604e4  lea     rcx, [rsp+320h+var_2E8]
0x1800604e9  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>,wil::err_returncode_policy>(void)
0x1800604ee  mov     eax, edi
0x1800604f0  mov     rcx, [rbp+220h+var_30]
0x1800604f7  xor     rcx, rsp; StackCookie
0x1800604fa  call    __security_check_cookie
0x1800604ff  lea     r11, [rsp+320h+var_20]
0x180060507  mov     rbx, [r11+40h]
0x18006050b  mov     rsi, [r11+48h]
0x18006050f  mov     rsp, r11
0x180060512  pop     r15
0x180060514  pop     r14
0x180060516  pop     r13
0x180060518  pop     rdi
0x180060519  pop     rbp
0x18006051a  retn
```
