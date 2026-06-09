# RpcGetActivityId

- ea: `0x18005c770`
- end: `0x18005cadd`
- name: `RpcGetActivityId`
- size: `877`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800074c0`
- `0x180008f64`
- `0x180014c00`
- `0x180014f40`
- `0x18001d320`
- `0x18001fd70`
- `0x18004b460`
- `0x18004b830`
- `0x18004b910`
- `0x180052dbc`
- `0x180055764`
- `0x180056fc0`
- `0x180058dec`
- `0x180058e44`
- `0x180058e7c`
- `0x180058f98`
- `0x18005b700`
- `0x18005b838`
- `0x18005c770`
- `0x180097010`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x18005c8ef`
- `ntdll!NtQueryInformationProcess` at `0x18005c92a`
- `ntdll!NtQueryInformationProcess` at `0x18005c8ef`
- `ntdll!NtQueryInformationProcess` at `0x18005c92a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c95a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c95a`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18005c898`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18005c898`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18005c8be`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18005c8be`

## string_xrefs

- `0x18005c99e`: `CheckAccessToSession(WINSTATION_QUERY) failed: 0x%x in %s`

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
    v19 = (**(__int64 (__fastcall ***)(struct ITSSession *, __int64 *, __int64 *))v17)(v17, qword_1800A9370, &v26);
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
0x18005c770  mov     [rsp-8+arg_10], rbx
0x18005c775  mov     [rsp-8+arg_18], rsi
0x18005c77a  push    rbp
0x18005c77b  push    rdi
0x18005c77c  push    r13
0x18005c77e  push    r14
0x18005c780  push    r15
0x18005c782  lea     rbp, [rsp-200h]
0x18005c78a  sub     rsp, 300h
0x18005c791  mov     rax, cs:__security_cookie
0x18005c798  xor     rax, rsp
0x18005c79b  mov     [rbp+220h+var_30], rax
0x18005c7a2  mov     r13, rcx
0x18005c7a5  mov     qword ptr [rsp+320h+ProcessInformationLength], 0
0x18005c7ae  lea     rcx, [rsp+320h+ProcessInformationLength]
0x18005c7b3  mov     r15, rdx
0x18005c7b6  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::ensure_data(void)
0x18005c7bb  lea     rdx, [rsp+320h+var_2D0]
0x18005c7c0  mov     rcx, [rax]
0x18005c7c3  add     rcx, 8
0x18005c7c7  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18005c7cc  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::`vftable'
0x18005c7d3  lea     rdx, [rsp+320h+var_2C0]; struct wil::details::IFailureCallback *
0x18005c7d8  mov     [rsp+320h+var_2C0], rax
0x18005c7dd  lea     rcx, [rsp+320h+var_2B8]; this
0x18005c7e2  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x18005c7e7  mov     rax, qword ptr [rsp+320h+ProcessInformationLength]
0x18005c7ec  mov     esi, 1
0x18005c7f1  mov     [rbp+220h+var_288], rax
0x18005c7f5  test    rax, rax
0x18005c7f8  jz      short loc_18005C801
0x18005c7fa  lock add [rax+118h], esi
0x18005c801  lea     rcx, [rsp+320h+ProcessInformationLength]
0x18005c806  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>,wil::err_returncode_policy>(void)
0x18005c80b  mov     rax, [rbp+220h+var_288]
0x18005c80f  mov     [rsp+320h+var_2E8], rax
0x18005c814  test    rax, rax
0x18005c817  jz      short loc_18005C820
0x18005c819  lock add [rax+118h], esi
0x18005c820  lea     rcx, [rsp+320h+var_2C0]
0x18005c825  call    ??1?$test_watcher@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::~test_watcher<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>(void)
0x18005c82a  lea     r14, aRpcgetactivity; "RpcGetActivityId"
0x18005c831  mov     [rsp+320h+var_2D0], 0
0x18005c83a  mov     r8, r14; char *
0x18005c83d  mov     [rsp+320h+var_2D8], 0
0x18005c846  xor     edx, edx; int
0x18005c848  mov     [rsp+320h+Pid], 0
0x18005c850  lea     rcx, [rbp+220h+var_280]; this
0x18005c854  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x18005c859  test    r13, r13
0x18005c85c  jnz     short loc_18005C883
0x18005c85e  lea     r8, aHsession; "hSession"
0x18005c865  mov     r9, r14
0x18005c868  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18005c86f  mov     ecx, 8; int
0x18005c874  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005c879  mov     edi, 80070057h
0x18005c87e  jmp     loc_18005CA15
0x18005c883  test    r15, r15
0x18005c886  jnz     short loc_18005C891
0x18005c888  lea     r8, aPactivityid; "pActivityId"
0x18005c88f  jmp     short loc_18005C865
0x18005c891  lea     rdx, [rsp+320h+Pid]; Pid
0x18005c896  xor     ecx, ecx; Binding
0x18005c898  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18005c89e  test    eax, eax
0x18005c8a0  jle     short loc_18005C8AC
0x18005c8a2  movzx   eax, ax
0x18005c8a5  or      eax, 80070000h
0x18005c8aa  test    eax, eax
0x18005c8ac  js      loc_18005C964
0x18005c8b2  mov     r8d, [rsp+320h+Pid]; dwProcessId
0x18005c8b7  xor     edx, edx; bInheritHandle
0x18005c8b9  mov     ecx, 1000h; dwDesiredAccess
0x18005c8be  call    cs:__imp_OpenProcess
0x18005c8c4  mov     rbx, rax
0x18005c8c7  test    rax, rax
0x18005c8ca  jz      loc_18005C964
0x18005c8d0  xor     r9d, r9d; ProcessInformationLength
0x18005c8d3  mov     [rsp+320h+ProcessInformationLength], 0
0x18005c8db  lea     rax, [rsp+320h+ProcessInformationLength]
0x18005c8e0  xor     r8d, r8d; ProcessInformation
0x18005c8e3  mov     rcx, rbx; ProcessHandle
0x18005c8e6  mov     [rsp+320h+ReturnLength], rax; ReturnLength
0x18005c8eb  lea     edx, [r9+3Ch]; ProcessInformationClass
0x18005c8ef  call    cs:__imp_NtQueryInformationProcess
0x18005c8f5  mov     edi, eax
0x18005c8f7  cmp     eax, 0C0000004h
0x18005c8fc  jnz     short loc_18005C957
0x18005c8fe  cmp     [rsp+320h+ProcessInformationLength], 10h
0x18005c903  jbe     short loc_18005C957
0x18005c905  mov     ecx, [rsp+320h+ProcessInformationLength]; unsigned __int64
0x18005c909  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18005c90e  mov     r9d, [rsp+320h+ProcessInformationLength]; ProcessInformationLength
0x18005c913  mov     r8, rax; ProcessInformation
0x18005c916  mov     edx, 3Ch ; '<'; ProcessInformationClass
0x18005c91b  mov     [rsp+320h+ReturnLength], 0; ReturnLength
0x18005c924  mov     rcx, rbx; ProcessHandle
0x18005c927  mov     r14, rax
0x18005c92a  call    cs:__imp_NtQueryInformationProcess
0x18005c930  mov     edi, eax
0x18005c932  or      edi, 10000000h
0x18005c938  jl      short loc_18005C948
0x18005c93a  mov     rdx, [r14+8]
0x18005c93e  lea     rcx, [rsp+320h+var_2E8]
0x18005c943  call    ?log@?$tip_test@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@@tip2@@QEAAXPEBG@Z; tip2::tip_test<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::log(ushort const *)
0x18005c948  mov     rcx, r14; void *
0x18005c94b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005c950  lea     r14, aRpcgetactivity; "RpcGetActivityId"
0x18005c957  mov     rcx, rbx; hObject
0x18005c95a  call    cs:__imp_CloseHandle
0x18005c960  test    edi, edi
0x18005c962  jns     short loc_18005C975
0x18005c964  lea     rdx, aCouldNotGetRpc; "Could not get RPC caller's cmdline"
0x18005c96b  lea     rcx, [rsp+320h+var_2E8]
0x18005c970  call    ?log@?$tip_test@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@@tip2@@QEAAXPEBG@Z; tip2::tip_test<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::log(ushort const *)
0x18005c975  mov     rdx, [r13+638h]
0x18005c97c  lea     rcx, [rsp+320h+var_2D0]
0x18005c981  call    ??4?$SmartPtr@UITSSession@@@@QEAAAEAV0@PEAUITSSession@@@Z; SmartPtr<ITSSession>::operator=(ITSSession *)
0x18005c986  mov     rbx, [rsp+320h+var_2D0]
0x18005c98b  xor     r8d, r8d; int
0x18005c98e  mov     rcx, rbx; struct ITSSession *
0x18005c991  mov     edx, esi; unsigned int
0x18005c993  call    ?CheckAccessToSession@@YAJPEAUITSSession@@KH@Z; CheckAccessToSession(ITSSession *,ulong,int)
0x18005c998  mov     edi, eax
0x18005c99a  test    eax, eax
0x18005c99c  jns     short loc_18005C9B7
0x18005c99e  lea     rdx, aCheckaccesstos_5; "CheckAccessToSession(WINSTATION_QUERY) "...
0x18005c9a5  mov     r9, r14
0x18005c9a8  mov     r8d, eax
0x18005c9ab  mov     ecx, 8; int
0x18005c9b0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005c9b5  jmp     short loc_18005CA15
0x18005c9b7  mov     rax, [rbx]
0x18005c9ba  lea     r8, [rsp+320h+var_2D8]
0x18005c9bf  lea     rdx, qword_1800A9370
0x18005c9c6  mov     rcx, rbx
0x18005c9c9  mov     rax, [rax]
0x18005c9cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c9d1  mov     edi, eax
0x18005c9d3  test    eax, eax
0x18005c9d5  jns     short loc_18005C9E5
0x18005c9d7  mov     esi, 2
0x18005c9dc  lea     rdx, aGettingIidItss_1; "Getting IID_ITSSessionPrivate for sessi"...
0x18005c9e3  jmp     short loc_18005C9A5
0x18005c9e5  mov     rcx, [rsp+320h+var_2D8]
0x18005c9ea  mov     rdx, r15
0x18005c9ed  mov     rax, [rcx]
0x18005c9f0  mov     rax, [rax+248h]
0x18005c9f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c9fc  mov     edi, eax
0x18005c9fe  test    eax, eax
0x18005ca00  jns     short loc_18005CA10
0x18005ca02  mov     esi, 3
0x18005ca07  lea     rdx, aSessionprivate; "SessionPrivate->GetActivityId failed: 0"...
0x18005ca0e  jmp     short loc_18005C9A5
0x18005ca10  mov     esi, 4
0x18005ca15  lea     rdx, [rsp+320h+ProcessInformationLength]
0x18005ca1a  lea     rcx, [rsp+320h+var_2E8]
0x18005ca1f  call    ??C?$tip_test@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::operator->(void)
0x18005ca24  mov     rcx, [rax]
0x18005ca27  mov     [rcx+110h], edi
0x18005ca2d  lea     rcx, [rsp+320h+ProcessInformationLength]
0x18005ca32  call    ??1?$test_data_control@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::~test_data_control<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>(void)
0x18005ca37  lea     rdx, [rsp+320h+ProcessInformationLength]
0x18005ca3c  lea     rcx, [rsp+320h+var_2E8]
0x18005ca41  call    ??C?$tip_test@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::operator->(void)
0x18005ca46  mov     rcx, [rax]
0x18005ca49  mov     [rcx+114h], esi
0x18005ca4f  lea     rcx, [rsp+320h+ProcessInformationLength]
0x18005ca54  call    ??1?$test_data_control@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::~test_data_control<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>(void)
0x18005ca59  lea     rdx, [rsp+320h+ProcessInformationLength]
0x18005ca5e  lea     rcx, [rsp+320h+var_2E8]
0x18005ca63  call    ??C?$tip_test@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::operator->(void)
0x18005ca68  mov     edx, 800h
0x18005ca6d  mov     r8d, 0Ah
0x18005ca73  mov     rcx, [rax]
0x18005ca76  add     rcx, 8
0x18005ca7a  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestFlags@@W4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestFlags,TestQueryOptions)
0x18005ca7f  lea     rcx, [rsp+320h+ProcessInformationLength]
0x18005ca84  call    ??1?$test_data_control@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>::~test_data_control<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>>(void)
0x18005ca89  lea     rcx, [rbp+220h+var_280]; this
0x18005ca8d  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x18005ca92  lea     rcx, [rsp+320h+var_2D8]
0x18005ca97  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005ca9c  lea     rcx, [rsp+320h+var_2D0]
0x18005caa1  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005caa6  lea     rcx, [rsp+320h+var_2E8]
0x18005caab  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SessionActivityIdRpcTip@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SessionActivityIdRpcTip,_tip_SessionActivityIdRpcTip>,wil::err_returncode_policy>(void)
0x18005cab0  mov     eax, edi
0x18005cab2  mov     rcx, [rbp+220h+var_30]
0x18005cab9  xor     rcx, rsp; StackCookie
0x18005cabc  call    __security_check_cookie
0x18005cac1  lea     r11, [rsp+320h+var_20]
0x18005cac9  mov     rbx, [r11+40h]
0x18005cacd  mov     rsi, [r11+48h]
0x18005cad1  mov     rsp, r11
0x18005cad4  pop     r15
0x18005cad6  pop     r14
0x18005cad8  pop     r13
0x18005cada  pop     rdi
0x18005cadb  pop     rbp
0x18005cadc  retn
```
