# SetupRpcListener

- ea: `0x140199ed0`
- end: `0x14019a37c`
- name: `SetupRpcListener`
- size: `1196`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1400036a0`
- `0x14000e34c`
- `0x140014df4`
- `0x140024964`
- `0x140024c84`
- `0x14004485c`
- `0x140196b58`
- `0x1401976c0`
- `0x1401979c8`
- `0x140197d18`
- `0x140197d6c`
- `0x140199ed0`
- `0x1401af7c0`
- `0x1401b8fb0`
- `0x1401b9494`
- `0x1401ba178`
- `0x1401bda10`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140199fbd`
- `KERNEL32!GetCurrentThreadId` at `0x14019a034`
- `KERNEL32!GetCurrentThreadId` at `0x14019a096`
- `KERNEL32!GetCurrentThreadId` at `0x14019a0f4`
- `KERNEL32!GetCurrentThreadId` at `0x14019a150`
- `KERNEL32!GetCurrentThreadId` at `0x14019a1d3`
- `KERNEL32!GetCurrentThreadId` at `0x14019a24d`
- `KERNEL32!GetCurrentThreadId` at `0x140199fbd`
- `KERNEL32!GetCurrentThreadId` at `0x14019a034`
- `KERNEL32!GetCurrentThreadId` at `0x14019a096`
- `KERNEL32!GetCurrentThreadId` at `0x14019a0f4`
- `KERNEL32!GetCurrentThreadId` at `0x14019a150`
- `KERNEL32!GetCurrentThreadId` at `0x14019a1d3`
- `KERNEL32!GetCurrentThreadId` at `0x14019a24d`
- `RPCRT4!RpcServerListen` at `0x14019a23f`
- `RPCRT4!RpcServerListen` at `0x14019a23f`
- `RPCRT4!RpcServerRegisterIfEx` at `0x14019a1bd`
- `RPCRT4!RpcServerRegisterIfEx` at `0x14019a1bd`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x14019a142`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x14019a142`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x14019a0e6`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x14019a0e6`
- `RPCRT4!RpcServerUseProtseqEpExW` at `0x140199faf`
- `RPCRT4!RpcServerUseProtseqEpExW` at `0x140199faf`
- `RPCRT4!RpcServerInqBindings` at `0x14019a026`
- `RPCRT4!RpcServerInqBindings` at `0x14019a026`
- `RPCRT4!RpcEpRegisterW` at `0x14019a088`
- `RPCRT4!RpcEpRegisterW` at `0x14019a088`

## string_xrefs

- `0x14019a071`: `Frs2 Service`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall SetupRpcListener(char *Parameter, const unsigned __int16 *a2)
{
  unsigned __int16 *v3; // rbx
  unsigned int v4; // eax
  unsigned int v5; // edi
  DWORD CurrentThreadId; // eax
  __int64 v7; // rcx
  struct FrsStatus *v8; // rax
  __int64 v9; // rdx
  DWORD v10; // eax
  __int64 v11; // rcx
  DWORD v12; // eax
  __int64 v13; // rcx
  DWORD v14; // eax
  __int64 v15; // rcx
  DWORD v16; // eax
  __int64 v17; // rcx
  unsigned int v18; // eax
  RPC_STATUS v19; // eax
  DWORD v20; // eax
  __int64 v21; // rcx
  unsigned int v22; // ebx
  unsigned int v23; // eax
  DWORD v24; // eax
  __int64 v25; // rcx
  const wchar_t **v26; // rax
  const wchar_t *v27; // rbx
  Dword *v28; // rax
  struct FrsStatus *v29; // [rsp+50h] [rbp-B0h] BYREF
  RPC_WSTR PrincName; // [rsp+58h] [rbp-A8h] BYREF
  RPC_BINDING_VECTOR *BindingVector; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v32[2]; // [rsp+68h] [rbp-98h] BYREF
  void *Block; // [rsp+78h] [rbp-88h] BYREF
  UUID_VECTOR UuidVector; // [rsp+80h] [rbp-80h] BYREF
  struct _RPC_POLICY Policy; // [rsp+90h] [rbp-70h] BYREF
  const wchar_t *v36; // [rsp+A0h] [rbp-60h] BYREF
  int v37; // [rsp+A8h] [rbp-58h]
  int v38; // [rsp+ACh] [rbp-54h]
  const wchar_t *v39; // [rsp+B0h] [rbp-50h]
  _BYTE v40[32]; // [rsp+D0h] [rbp-30h] BYREF
  char v41; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v42[64]; // [rsp+150h] [rbp+50h] BYREF

  *(&UuidVector.Count + 1) = 0;
  Config::GuidParam::GuidParam((Config::GuidParam *)v40, a2);
  LODWORD(v29) = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)Parameter + 24LL))(Parameter);
  v32[0] = &v29;
  v32[1] = JPrintf::FormatValue<unsigned short,unsigned long>;
  jsprintf_body<unsigned short,1,32>(v32, v42, L"%?");
  ScopedCrewLock::ScopedCrewLock(v32, Parameter + 8);
  Policy.Length = 12;
  *(_QWORD *)&Policy.EndpointFlags = 4;
  v3 = (unsigned __int16 *)((unsigned __int64)v42
                          & -(__int64)((*(unsigned int (__fastcall **)(char *))(*(_QWORD *)Parameter + 24LL))(Parameter) != 0));
  v4 = Settings::GenericDwordSetting::operator()(&Settings::RpcProtseqMaxCalls);
  v5 = RpcServerUseProtseqEpExW((RPC_WSTR)L"ncacn_ip_tcp", v4, v3, 0, &Policy);
  CurrentThreadId = GetCurrentThreadId();
  v8 = (struct FrsStatus *)FrsStatusList::PushNewError(
                             v7,
                             v5,
                             0,
                             1,
                             "base\\fs\\remotefs\\frs\\src\\transport\\rpcnetwork.cpp",
                             "SetupRpcListener",
                             2283,
                             CurrentThreadId,
                             0);
  v29 = v8;
  BindingVector = 0;
  UuidVector.Count = 1;
  UuidVector.Uuid[0] = (UUID *)&v41;
  if ( !v5 )
  {
    v5 = RpcServerInqBindings(&BindingVector);
    v10 = GetCurrentThreadId();
    v8 = (struct FrsStatus *)FrsStatusList::PushNewError(
                               v11,
                               v5,
                               0,
                               1,
                               "base\\fs\\remotefs\\frs\\src\\transport\\rpcnetwork.cpp",
                               "SetupRpcListener",
                               2301,
                               v10,
                               0);
    v29 = v8;
    if ( !v5 )
    {
      v5 = RpcEpRegisterW(qword_14022DEE0, BindingVector, &UuidVector, (RPC_WSTR)L"Frs2 Service");
      v12 = GetCurrentThreadId();
      v8 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v13,
                                 v5,
                                 0,
                                 1,
                                 "base\\fs\\remotefs\\frs\\src\\transport\\rpcnetwork.cpp",
                                 "SetupRpcListener",
                                 2312,
                                 v12,
                                 0);
      v29 = v8;
    }
  }
  PrincName = 0;
  if ( v5 )
    goto LABEL_13;
  v5 = RpcServerInqDefaultPrincNameW(9u, &PrincName);
  v14 = GetCurrentThreadId();
  v8 = (struct FrsStatus *)FrsStatusList::PushNewError(
                             v15,
                             v5,
                             0,
                             1,
                             "base\\fs\\remotefs\\frs\\src\\transport\\rpcnetwork.cpp",
                             "SetupRpcListener",
                             2320,
                             v14,
                             0);
  v29 = v8;
  if ( v5 )
    goto LABEL_13;
  v5 = RpcServerRegisterAuthInfoW(PrincName, 9u, 0, 0);
  v16 = GetCurrentThreadId();
  v8 = (struct FrsStatus *)FrsStatusList::PushNewError(
                             v17,
                             v5,
                             0,
                             1,
                             "base\\fs\\remotefs\\frs\\src\\transport\\rpcnetwork.cpp",
                             "SetupRpcListener",
                             2328,
                             v16,
                             0);
  v29 = v8;
  if ( v5 )
    goto LABEL_13;
  v18 = Settings::GenericDwordSetting::operator()(&Settings::RpcProtseqMaxCalls);
  v19 = RpcServerRegisterIfEx(qword_14022DEE0, 0, 0, 8u, v18, FrsRpcSecurityCallback);
  v5 = 0;
  if ( v19 != 1712 )
    v5 = v19;
  v20 = GetCurrentThreadId();
  v8 = (struct FrsStatus *)FrsStatusList::PushNewError(
                             v21,
                             v5,
                             0,
                             1,
                             "base\\fs\\remotefs\\frs\\src\\transport\\rpcnetwork.cpp",
                             "SetupRpcListener",
                             2351,
                             v20,
                             0);
  v29 = v8;
  if ( v5
    || (FrsEvent::Log(1073743034, v42),
        v22 = Settings::GenericDwordSetting::operator()(&Settings::RpcListenMaxCalls),
        v23 = Settings::GenericDwordSetting::operator()(&Settings::RpcListenMinCalls),
        v5 = RpcServerListen(v23, v22, 0),
        v24 = GetCurrentThreadId(),
        v8 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                   v25,
                                   v5,
                                   0,
                                   1,
                                   "base\\fs\\remotefs\\frs\\src\\transport\\rpcnetwork.cpp",
                                   "SetupRpcListener",
                                   2361,
                                   v24,
                                   0),
        v29 = v8,
        v5) )
  {
LABEL_13:
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v36 = L"SetupRpcListener";
      v37 = 2366;
      v38 = 2;
      v39 = L"RPCN";
      dbgobj::DbgPrint<unsigned short,unsigned short [32],FrsStatus>(&v36, v9, v42, v8);
    }
    v26 = (const wchar_t **)W32ErrorString::W32ErrorString((W32ErrorString *)&Block, v5);
    v27 = &pServiceName;
    if ( *v26 )
      v27 = *v26;
    v28 = Dword::Dword((Dword *)&v36, v5, 10);
    FrsEvent::Log(3221226680LL, v42, v28, v27);
    operator delete[](Block);
  }
  CLEAR_ERROR(&v29);
  scoped_any<unsigned short *,close_rpc_string,null_t,0>::~scoped_any<unsigned short *,close_rpc_string,null_t,0>(&PrincName);
  scoped_any<_RPC_BINDING_VECTOR *,close_rpc_vector,null_t,0>::~scoped_any<_RPC_BINDING_VECTOR *,close_rpc_vector,null_t,0>(&BindingVector);
  ScopedCrewLock::~ScopedCrewLock((ScopedCrewLock *)v32);
}

```

## disassembly

```asm
0x140199ed0  mov     [rsp-8+arg_8], rbx
0x140199ed5  mov     [rsp-8+arg_10], rsi
0x140199eda  push    rbp
0x140199edb  push    rdi
0x140199edc  push    r12
0x140199ede  push    r14
0x140199ee0  push    r15
0x140199ee2  lea     rbp, [rsp-0A0h]
0x140199eea  sub     rsp, 1A0h
0x140199ef1  mov     rax, cs:__security_cookie
0x140199ef8  xor     rax, rsp
0x140199efb  mov     [rbp+0C0h+var_30], rax
0x140199f02  mov     rbx, rcx
0x140199f05  xor     esi, esi
0x140199f07  mov     dword ptr [rbp+0C0h+UuidVector+4], esi
0x140199f0a  lea     rcx, [rbp+0C0h+var_F0]; this
0x140199f0e  call    ??0GuidParam@Config@@QEAA@PEBG@Z; Config::GuidParam::GuidParam(ushort const *)
0x140199f13  nop
0x140199f14  mov     rax, [rbx]
0x140199f17  mov     rcx, rbx
0x140199f1a  mov     rax, [rax+18h]
0x140199f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140199f23  mov     dword ptr [rsp+1C0h+var_170], eax
0x140199f27  lea     rax, [rsp+1C0h+var_170]
0x140199f2c  mov     [rsp+1C0h+var_158], rax
0x140199f31  lea     rax, ??$FormatValue@GK@JPrintf@@YA_NAEAV?$OutputStream@G@0@AEBV?$ValueInfo@G@0@PEBK@Z; JPrintf::FormatValue<ushort,ulong>(JPrintf::OutputStream<ushort> &,JPrintf::ValueInfo<ushort> const &,ulong const *)
0x140199f38  mov     [rsp+1C0h+var_150], rax
0x140199f3d  lea     r8, asc_1402529CC; "%?"
0x140199f44  lea     rdx, [rbp+0C0h+var_70]
0x140199f48  lea     rcx, [rsp+1C0h+var_158]
0x140199f4d  call    ??$jsprintf_body@G$00$0CA@@@YA_KAEAY00$$CBV?$ArgumentWrapper@G@JPrintf@@AEAY0CA@GPEBG@Z; jsprintf_body<ushort,1,32>(JPrintf::ArgumentWrapper<ushort> const (&)[1],ushort (&)[32],ushort const *)
0x140199f52  lea     rdx, [rbx+8]
0x140199f56  lea     rcx, [rsp+1C0h+var_158]
0x140199f5b  call    ??0ScopedCrewLock@@QEAA@AEAVCREWLock@@UWrite@0@@Z; ScopedCrewLock::ScopedCrewLock(CREWLock &,ScopedCrewLock::Write)
0x140199f60  nop
0x140199f61  mov     [rbp+0C0h+var_130.Length], 0Ch
0x140199f68  mov     qword ptr [rbp+0C0h+var_130.EndpointFlags], 4
0x140199f70  mov     rax, [rbx]
0x140199f73  mov     rcx, rbx
0x140199f76  mov     rax, [rax+18h]
0x140199f7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140199f7f  neg     eax
0x140199f81  sbb     rbx, rbx
0x140199f84  lea     rax, [rbp+0C0h+var_70]
0x140199f88  and     rbx, rax
0x140199f8b  lea     rcx, ?RpcProtseqMaxCalls@Settings@@3VCRpcProtseqMaxCalls@1@A; Settings::CRpcProtseqMaxCalls Settings::RpcProtseqMaxCalls
0x140199f92  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x140199f97  mov     edx, eax; MaxCalls
0x140199f99  lea     rax, [rbp+0C0h+var_130]
0x140199f9d  mov     [rsp+1C0h+Policy], rax; Policy
0x140199fa2  xor     r9d, r9d; SecurityDescriptor
0x140199fa5  mov     r8, rbx; Endpoint
0x140199fa8  lea     rcx, ProtSeq; "ncacn_ip_tcp"
0x140199faf  call    cs:__imp_RpcServerUseProtseqEpExW
0x140199fb6  nop     dword ptr [rax+rax+00h]
0x140199fbb  mov     edi, eax
0x140199fbd  call    cs:__imp_GetCurrentThreadId
0x140199fc4  nop     dword ptr [rax+rax+00h]
0x140199fc9  mov     [rsp+1C0h+var_180], rsi
0x140199fce  mov     [rsp+1C0h+var_188], eax
0x140199fd2  mov     [rsp+1C0h+var_190], 8EBh
0x140199fda  lea     r15, aSetuprpclisten_0; "SetupRpcListener"
0x140199fe1  mov     [rsp+1C0h+IfCallback], r15
0x140199fe6  lea     r12, aBaseFsRemotefs_16; "base\\fs\\remotefs\\frs\\src\\transport"...
0x140199fed  mov     [rsp+1C0h+Policy], r12
0x140199ff2  lea     r14d, [rsi+1]
0x140199ff6  mov     r9d, r14d
0x140199ff9  xor     r8d, r8d
0x140199ffc  mov     edx, edi
0x140199ffe  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14019a003  mov     [rsp+1C0h+var_170], rax
0x14019a008  mov     [rsp+1C0h+BindingVector], rsi
0x14019a00d  mov     [rbp+0C0h+UuidVector.Count], r14d
0x14019a011  lea     rcx, [rbp+0C0h+var_D0]
0x14019a015  mov     [rbp+0C0h+UuidVector.Uuid], rcx
0x14019a019  test    edi, edi
0x14019a01b  jnz     loc_14019A0CF
0x14019a021  lea     rcx, [rsp+1C0h+BindingVector]; BindingVector
0x14019a026  call    cs:__imp_RpcServerInqBindings
0x14019a02d  nop     dword ptr [rax+rax+00h]
0x14019a032  mov     edi, eax
0x14019a034  call    cs:__imp_GetCurrentThreadId
0x14019a03b  nop     dword ptr [rax+rax+00h]
0x14019a040  mov     [rsp+1C0h+var_180], rsi
0x14019a045  mov     [rsp+1C0h+var_188], eax
0x14019a049  mov     [rsp+1C0h+var_190], 8FDh
0x14019a051  mov     [rsp+1C0h+IfCallback], r15
0x14019a056  mov     [rsp+1C0h+Policy], r12
0x14019a05b  mov     r9d, r14d
0x14019a05e  xor     r8d, r8d
0x14019a061  mov     edx, edi
0x14019a063  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14019a068  mov     [rsp+1C0h+var_170], rax
0x14019a06d  test    edi, edi
0x14019a06f  jnz     short loc_14019A0CF
0x14019a071  lea     r9, Annotation; "Frs2 Service"
0x14019a078  lea     r8, [rbp+0C0h+UuidVector]; UuidVector
0x14019a07c  mov     rdx, [rsp+1C0h+BindingVector]; BindingVector
0x14019a081  lea     rcx, qword_14022DEE0; IfSpec
0x14019a088  call    cs:__imp_RpcEpRegisterW
0x14019a08f  nop     dword ptr [rax+rax+00h]
0x14019a094  mov     edi, eax
0x14019a096  call    cs:__imp_GetCurrentThreadId
0x14019a09d  nop     dword ptr [rax+rax+00h]
0x14019a0a2  mov     [rsp+1C0h+var_180], rsi
0x14019a0a7  mov     [rsp+1C0h+var_188], eax
0x14019a0ab  mov     [rsp+1C0h+var_190], 908h
0x14019a0b3  mov     [rsp+1C0h+IfCallback], r15
0x14019a0b8  mov     [rsp+1C0h+Policy], r12
0x14019a0bd  mov     r9d, r14d
0x14019a0c0  xor     r8d, r8d
0x14019a0c3  mov     edx, edi
0x14019a0c5  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14019a0ca  mov     [rsp+1C0h+var_170], rax
0x14019a0cf  mov     [rsp+1C0h+PrincName], rsi
0x14019a0d4  test    edi, edi
0x14019a0d6  jnz     loc_14019A28E
0x14019a0dc  lea     rdx, [rsp+1C0h+PrincName]; PrincName
0x14019a0e1  lea     ebx, [rdi+9]
0x14019a0e4  mov     ecx, ebx; AuthnSvc
0x14019a0e6  call    cs:__imp_RpcServerInqDefaultPrincNameW
0x14019a0ed  nop     dword ptr [rax+rax+00h]
0x14019a0f2  mov     edi, eax
0x14019a0f4  call    cs:__imp_GetCurrentThreadId
0x14019a0fb  nop     dword ptr [rax+rax+00h]
0x14019a100  mov     [rsp+1C0h+var_180], rsi
0x14019a105  mov     [rsp+1C0h+var_188], eax
0x14019a109  mov     [rsp+1C0h+var_190], 910h
0x14019a111  mov     [rsp+1C0h+IfCallback], r15
0x14019a116  mov     [rsp+1C0h+Policy], r12
0x14019a11b  mov     r9d, r14d
0x14019a11e  xor     r8d, r8d
0x14019a121  mov     edx, edi
0x14019a123  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14019a128  mov     [rsp+1C0h+var_170], rax
0x14019a12d  test    edi, edi
0x14019a12f  jnz     loc_14019A28E
0x14019a135  xor     r9d, r9d; Arg
0x14019a138  xor     r8d, r8d; GetKeyFn
0x14019a13b  mov     edx, ebx; AuthnSvc
0x14019a13d  mov     rcx, [rsp+1C0h+PrincName]; ServerPrincName
0x14019a142  call    cs:__imp_RpcServerRegisterAuthInfoW
0x14019a149  nop     dword ptr [rax+rax+00h]
0x14019a14e  mov     edi, eax
0x14019a150  call    cs:__imp_GetCurrentThreadId
0x14019a157  nop     dword ptr [rax+rax+00h]
0x14019a15c  mov     [rsp+1C0h+var_180], rsi
0x14019a161  mov     [rsp+1C0h+var_188], eax
0x14019a165  mov     [rsp+1C0h+var_190], 918h
0x14019a16d  mov     [rsp+1C0h+IfCallback], r15
0x14019a172  mov     [rsp+1C0h+Policy], r12
0x14019a177  mov     r9d, r14d
0x14019a17a  xor     r8d, r8d
0x14019a17d  mov     edx, edi
0x14019a17f  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14019a184  mov     [rsp+1C0h+var_170], rax
0x14019a189  test    edi, edi
0x14019a18b  jnz     loc_14019A28E
0x14019a191  lea     rcx, ?RpcProtseqMaxCalls@Settings@@3VCRpcProtseqMaxCalls@1@A; Settings::CRpcProtseqMaxCalls Settings::RpcProtseqMaxCalls
0x14019a198  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x14019a19d  lea     rdx, ?FrsRpcSecurityCallback@@YAJPEAX0@Z; FrsRpcSecurityCallback(void *,void *)
0x14019a1a4  mov     [rsp+1C0h+IfCallback], rdx; IfCallback
0x14019a1a9  mov     dword ptr [rsp+1C0h+Policy], eax; MaxCalls
0x14019a1ad  lea     r9d, [rbx-1]; Flags
0x14019a1b1  xor     r8d, r8d; MgrEpv
0x14019a1b4  xor     edx, edx; MgrTypeUuid
0x14019a1b6  lea     rcx, qword_14022DEE0; IfSpec
0x14019a1bd  call    cs:__imp_RpcServerRegisterIfEx
0x14019a1c4  nop     dword ptr [rax+rax+00h]
0x14019a1c9  mov     edi, esi
0x14019a1cb  cmp     eax, 6B0h
0x14019a1d0  cmovnz  edi, eax
0x14019a1d3  call    cs:__imp_GetCurrentThreadId
0x14019a1da  nop     dword ptr [rax+rax+00h]
0x14019a1df  mov     [rsp+1C0h+var_180], rsi
0x14019a1e4  mov     [rsp+1C0h+var_188], eax
0x14019a1e8  mov     [rsp+1C0h+var_190], 92Fh
0x14019a1f0  mov     [rsp+1C0h+IfCallback], r15
0x14019a1f5  mov     [rsp+1C0h+Policy], r12
0x14019a1fa  mov     r9d, r14d
0x14019a1fd  xor     r8d, r8d
0x14019a200  mov     edx, edi
0x14019a202  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14019a207  mov     [rsp+1C0h+var_170], rax
0x14019a20c  test    edi, edi
0x14019a20e  jnz     short loc_14019A28E
0x14019a210  lea     rdx, [rbp+0C0h+var_70]
0x14019a214  mov     ecx, 400004BAh
0x14019a219  call    ?Log@FrsEvent@@SAXW4FrsEventsEnum1@@PEBG@Z; FrsEvent::Log(FrsEventsEnum1,ushort const *)
0x14019a21e  lea     rcx, ?RpcListenMaxCalls@Settings@@3VCRpcListenMaxCalls@1@A; Settings::CRpcListenMaxCalls Settings::RpcListenMaxCalls
0x14019a225  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x14019a22a  mov     ebx, eax
0x14019a22c  lea     rcx, ?RpcListenMinCalls@Settings@@3VCRpcListenMinCalls@1@A; Settings::CRpcListenMinCalls Settings::RpcListenMinCalls
0x14019a233  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x14019a238  xor     r8d, r8d; DontWait
0x14019a23b  mov     edx, ebx; MaxCalls
0x14019a23d  mov     ecx, eax; MinimumCallThreads
0x14019a23f  call    cs:__imp_RpcServerListen
0x14019a246  nop     dword ptr [rax+rax+00h]
0x14019a24b  mov     edi, eax
0x14019a24d  call    cs:__imp_GetCurrentThreadId
0x14019a254  nop     dword ptr [rax+rax+00h]
0x14019a259  mov     [rsp+1C0h+var_180], rsi
0x14019a25e  mov     [rsp+1C0h+var_188], eax
0x14019a262  mov     [rsp+1C0h+var_190], 939h
0x14019a26a  mov     [rsp+1C0h+IfCallback], r15
0x14019a26f  mov     [rsp+1C0h+Policy], r12
0x14019a274  mov     r9d, r14d
0x14019a277  xor     r8d, r8d
0x14019a27a  mov     edx, edi
0x14019a27c  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14019a281  mov     [rsp+1C0h+var_170], rax
0x14019a286  test    edi, edi
0x14019a288  jz      loc_14019A324
0x14019a28e  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019a295  test    rcx, rcx
0x14019a298  jz      short loc_14019A2D9
0x14019a29a  cmp     [rcx+40h], esi
0x14019a29d  jz      short loc_14019A2D9
0x14019a29f  cmp     dword ptr [rcx+38h], 2
0x14019a2a3  jl      short loc_14019A2D9
0x14019a2a5  lea     rcx, aSetuprpclisten; "SetupRpcListener"
0x14019a2ac  mov     [rbp+0C0h+var_120], rcx
0x14019a2b0  mov     [rbp+0C0h+var_118], 93Eh
0x14019a2b7  mov     [rbp+0C0h+var_114], 2
0x14019a2be  lea     rcx, aRpcn; "RPCN"
0x14019a2c5  mov     [rbp+0C0h+var_110], rcx
0x14019a2c9  mov     r9, rax
0x14019a2cc  lea     r8, [rbp+0C0h+var_70]
0x14019a2d0  lea     rcx, [rbp+0C0h+var_120]
0x14019a2d4  call    ??$DbgPrint@G$$BY0CA@GVFrsStatus@@@dbgobj@@QEAA_KPEBGAEAY0CA@$$CBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,ushort [32],FrsStatus>(ushort const *,ushort const (&)[32],FrsStatus const &)
0x14019a2d9  mov     edx, edi; unsigned int
0x14019a2db  lea     rcx, [rsp+1C0h+Block]; this
0x14019a2e0  call    ??0W32ErrorString@@QEAA@K@Z; W32ErrorString::W32ErrorString(ulong)
0x14019a2e5  nop
0x14019a2e6  lea     rbx, pServiceName
0x14019a2ed  cmp     [rax], rsi
0x14019a2f0  cmovnz  rbx, [rax]
0x14019a2f4  mov     r8d, 0Ah; int
0x14019a2fa  mov     edx, edi; unsigned int
0x14019a2fc  lea     rcx, [rbp+0C0h+var_120]; this
0x14019a300  call    ??0Dword@@QEAA@KH@Z; Dword::Dword(ulong,int)
0x14019a305  mov     r9, rbx
0x14019a308  mov     r8, rax
0x14019a30b  lea     rdx, [rbp+0C0h+var_70]
0x14019a30f  mov     ecx, 0C00004B8h
0x14019a314  call    ?Log@FrsEvent@@SAXW4FrsEventsEnum3@@PEBG11@Z; FrsEvent::Log(FrsEventsEnum3,ushort const *,ushort const *,ushort const *)
0x14019a319  nop
0x14019a31a  mov     rcx, [rsp+1C0h+Block]; Block
0x14019a31f  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x14019a324  lea     rcx, [rsp+1C0h+var_170]; struct FrsStatus **
0x14019a329  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x14019a32e  nop
0x14019a32f  lea     rcx, [rsp+1C0h+PrincName]
0x14019a334  call    ??1?$scoped_any@PEAGUclose_rpc_string@@Unull_t@@$0A@@@QEAA@XZ; scoped_any<ushort *,close_rpc_string,null_t,0>::~scoped_any<ushort *,close_rpc_string,null_t,0>(void)
0x14019a339  nop
0x14019a33a  lea     rcx, [rsp+1C0h+BindingVector]
0x14019a33f  call    ??1?$scoped_any@PEAU_RPC_BINDING_VECTOR@@Uclose_rpc_vector@@Unull_t@@$0A@@@QEAA@XZ; scoped_any<_RPC_BINDING_VECTOR *,close_rpc_vector,null_t,0>::~scoped_any<_RPC_BINDING_VECTOR *,close_rpc_vector,null_t,0>(void)
0x14019a344  nop
0x14019a345  lea     rcx, [rsp+1C0h+var_158]; this
0x14019a34a  call    ??1ScopedCrewLock@@QEAA@XZ; ScopedCrewLock::~ScopedCrewLock(void)
0x14019a34f  nop
0x14019a350  mov     rcx, [rbp+0C0h+var_30]
0x14019a357  xor     rcx, rsp; StackCookie
0x14019a35a  call    __security_check_cookie
0x14019a35f  lea     r11, [rsp+1C0h+var_20]
0x14019a367  mov     rbx, [r11+38h]
0x14019a36b  mov     rsi, [r11+40h]
0x14019a36f  mov     rsp, r11
0x14019a372  pop     r15
0x14019a374  pop     r14
0x14019a376  pop     r12
0x14019a378  pop     rdi
0x14019a379  pop     rbp
0x14019a37a  retn
```
