# MPCRawInputProvider::RuntimeClassInitialize(IRawInputClient *)

- ea: `0x180056734`
- end: `0x1800568b8`
- name: `?RuntimeClassInitialize@MPCRawInputProvider@@QEAAJPEAUIRawInputClient@@@Z`
- size: `388`
- prototype: `__int64 __fastcall(MPCRawInputProvider *__hidden this, struct IRawInputClient *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a7d00`

## callees

- `0x180012b74`
- `0x180056734`
- `0x180056e2c`
- `0x180056efc`
- `0x180056f64`
- `0x180057a9c`
- `0x18008dcac`
- `0x18008e194`
- `0x180093f68`
- `0x1800a852c`
- `0x1800ab80c`
- `0x180116410`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180056782`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180056782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056770`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056770`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18005675e`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18005675e`
- `CoreMessaging!CoreUICreate` at `0x18005679a`
- `CoreMessaging!CoreUICreate` at `0x18005679a`

## pseudocode

```c
__int64 __fastcall MPCRawInputProvider::RuntimeClassInitialize(MPCRawInputProvider *this, struct IRawInputClient *a2)
{
  void *v3; // rdx
  HANDLE Event; // rdi
  unsigned int v5; // r8d
  const char *v6; // r9
  _QWORD *v7; // rdi
  int v8; // eax
  const char *v9; // r9
  int v10; // eax
  __int64 v11; // rdx
  PSRWLOCK v12; // r11
  RTL_SRWLOCK *Instance; // rax
  int v15; // [rsp+20h] [rbp-49h]
  void (__fastcall *v16)(MPCRawInputProvider *__hidden, bool); // [rsp+30h] [rbp-39h] BYREF
  int v17; // [rsp+38h] [rbp-31h]
  __int128 v18; // [rsp+40h] [rbp-29h] BYREF
  char v19; // [rsp+50h] [rbp-19h]
  __int64 v20; // [rsp+58h] [rbp-11h]
  void **v21; // [rsp+60h] [rbp-9h] BYREF
  __int128 v22; // [rsp+68h] [rbp-1h]
  char v23; // [rsp+78h] [rbp+Fh]
  __int64 v24; // [rsp+80h] [rbp+17h]
  void ***v25; // [rsp+98h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  MPCRawInputProvider *v27; // [rsp+D0h] [rbp+67h] BYREF

  Microsoft::WRL::ComPtr<DWMCursorBroker>::operator=((char *)this + 16, a2);
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::FailFast_GetLastError(retaddr, v3, v5, v6);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    (char *)this + 72,
    Event);
  v7 = (_QWORD *)((char *)this + 64);
  *((_DWORD *)this + 22) = GetCurrentThreadId();
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 64);
  v8 = CoreUICreate((char *)this + 64);
  if ( v8 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x21,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\mpc\\lib\\mpcrawinputprovider.cpp",
      (const char *)(unsigned int)v8,
      v15);
  if ( !*v7 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x23,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\mpc\\lib\\mpcrawinputprovider.cpp",
      v9);
  v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 (__fastcall *)(void *, unsigned int, void *), MPCRawInputProvider *))(*(_QWORD *)*v7 + 272LL))(
          *v7,
          *((_QWORD *)this + 9),
          MPCRawInputProvider::InputReceivedStatic,
          this);
  if ( v10 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\mpc\\lib\\mpcrawinputprovider.cpp",
      (const char *)(unsigned int)v10,
      v15);
  MPC3DStateHelper::GetInstance();
  v27 = this;
  v16 = MPCRawInputProvider::OnCompositorRunningStateChanged;
  v17 = 0;
  std::_Compressed_pair<void (MPCInputRouter::*)(bool),std::tuple<MPCInputRouter *,std::_Ph<1>>,0>::_Compressed_pair<void (MPCInputRouter::*)(bool),std::tuple<MPCInputRouter *,std::_Ph<1>>,0>(
    &v18,
    v11,
    &v16,
    &v27);
  v23 = v19;
  v24 = v20;
  v21 = &std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (MPCRawInputProvider::*)(bool),MPCRawInputProvider *,std::_Ph<1> const &>,void,bool>::`vftable';
  v25 = &v21;
  v22 = v18;
  MPC3DStateHelper::RegisterFor3DCompositorRunningChanged(v12);
  Instance = (RTL_SRWLOCK *)MPC3DStateHelper::GetInstance();
  if ( MPC3DStateHelper::Is3DCompositorRunning(Instance) )
    MPCRawInputProvider::OnCompositorRunningStateChanged(this, 1);
  return 0;
}

```

## disassembly

```asm
0x180056734  push    rbp
0x180056736  push    rbx
0x180056737  push    rsi
0x180056738  push    rdi
0x180056739  lea     rbp, [rsp-3Fh]
0x18005673e  sub     rsp, 0A8h
0x180056745  mov     rbx, rcx
0x180056748  add     rcx, 10h
0x18005674c  call    ??4?$ComPtr@VDWMCursorBroker@@@WRL@Microsoft@@QEAAAEAV012@PEAVDWMCursorBroker@@@Z; Microsoft::WRL::ComPtr<DWMCursorBroker>::operator=(DWMCursorBroker *)
0x180056751  mov     r9d, 1F0003h; dwDesiredAccess
0x180056757  xor     r8d, r8d; dwFlags
0x18005675a  xor     edx, edx; lpName
0x18005675c  xor     ecx, ecx; lpEventAttributes
0x18005675e  call    cs:__imp_CreateEventExW
0x180056764  mov     rdi, rax
0x180056767  test    rax, rax
0x18005676a  jz      loc_1800568AE
0x180056770  call    cs:__imp_GetLastError
0x180056776  mov     rdx, rdi
0x180056779  lea     rcx, [rbx+48h]
0x18005677d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180056782  call    cs:__imp_GetCurrentThreadId
0x180056788  lea     rdi, [rbx+40h]
0x18005678c  mov     [rbx+58h], eax
0x18005678f  mov     rcx, rdi
0x180056792  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180056797  mov     rcx, rdi
0x18005679a  call    cs:__imp_CoreUICreate
0x1800567a0  test    eax, eax
0x1800567a2  jns     short loc_1800567BD
0x1800567a4  mov     rcx, [rbp+5Fh]; this
0x1800567a8  lea     r8, aOnecoreuapWind_66; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800567af  mov     r9d, eax; char *
0x1800567b2  mov     edx, 21h ; '!'; void *
0x1800567b7  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800567bd  mov     rcx, [rdi]
0x1800567c0  mov     rax, [rbp+5Fh]
0x1800567c4  test    rcx, rcx
0x1800567c7  jnz     short loc_1800567DC
0x1800567c9  lea     edx, [rcx+23h]; void *
0x1800567cc  mov     rcx, rax; this
0x1800567cf  lea     r8, aOnecoreuapWind_66; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800567d6  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800567dc  mov     rax, [rcx]
0x1800567df  lea     r8, ?InputReceivedStatic@MPCRawInputProvider@@KAJPEAXK0@Z; MPCRawInputProvider::InputReceivedStatic(void *,ulong,void *)
0x1800567e6  mov     rdx, [rbx+48h]
0x1800567ea  mov     r9, rbx
0x1800567ed  mov     rax, [rax+110h]
0x1800567f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800567f9  test    eax, eax
0x1800567fb  jns     short loc_180056816
0x1800567fd  mov     rcx, [rbp+5Fh]; this
0x180056801  lea     r8, aOnecoreuapWind_66; "onecoreuap\\windows\\moderncore\\inputv"...
0x180056808  mov     r9d, eax; char *
0x18005680b  mov     edx, 29h ; ')'; void *
0x180056810  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180056816  call    ?GetInstance@MPC3DStateHelper@@SAPEAV1@XZ; MPC3DStateHelper::GetInstance(void)
0x18005681b  mov     ecx, [rbp+57h+var_84]
0x18005681e  lea     r9, [rbp+57h+arg_0]
0x180056822  mov     r11, rax
0x180056825  mov     [rbp+57h+var_84], ecx
0x180056828  lea     rax, ?OnCompositorRunningStateChanged@MPCRawInputProvider@@AEAAX_N@Z; MPCRawInputProvider::OnCompositorRunningStateChanged(bool)
0x18005682f  mov     [rbp+57h+arg_0], rbx
0x180056833  lea     rcx, [rbp+57h+var_80]
0x180056837  mov     [rbp+57h+var_90], rax
0x18005683b  lea     r8, [rbp+57h+var_90]
0x18005683f  mov     [rbp+57h+var_88], 0
0x180056846  call    ??$?0P8MPCInputRouter@@EAAX_N@ZPEAV0@AEBU?$_Ph@$00@std@@@?$_Compressed_pair@P8MPCInputRouter@@EAAX_N@ZV?$tuple@PEAVMPCInputRouter@@U?$_Ph@$00@std@@@std@@$0A@@std@@QEAA@U_One_then_variadic_args_t@1@$$QEAP8MPCInputRouter@@EAAX_N@Z$$QEAPEAV3@AEBU?$_Ph@$00@1@@Z; std::_Compressed_pair<void (MPCInputRouter::*)(bool),std::tuple<MPCInputRouter *,std::_Ph<1>>,0>::_Compressed_pair<void (MPCInputRouter::*)(bool),std::tuple<MPCInputRouter *,std::_Ph<1>>,0>(std::_One_then_variadic_args_t,void (MPCInputRouter::*&&)(bool),MPCInputRouter * &&,std::_Ph<1> const &)
0x18005684b  mov     al, [rbp+57h+var_70]
0x18005684e  lea     r9, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8MPCRawInputProvider@@EAAX_N@ZPEAV3@AEBU?$_Ph@$00@2@@std@@X_N@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (MPCRawInputProvider::*)(bool),MPCRawInputProvider *,std::_Ph<1> const &>,void,bool>::`vftable'
0x180056855  movups  xmm1, [rbp+57h+var_80]
0x180056859  mov     [rbp+57h+var_48], al
0x18005685c  lea     r8, [rbx+54h]
0x180056860  mov     rax, [rbp+57h+var_68]
0x180056864  lea     rdx, [rbp+57h+var_60]
0x180056868  mov     [rbp+57h+var_40], rax
0x18005686c  mov     rcx, r11; SRWLock
0x18005686f  lea     rax, [rbp+57h+var_60]
0x180056873  mov     [rbp+57h+var_60], r9
0x180056877  mov     [rbp+57h+var_28], rax
0x18005687b  movdqu  [rbp+57h+var_58], xmm1
0x180056880  call    ?RegisterFor3DCompositorRunningChanged@MPC3DStateHelper@@QEAAXV?$function@$$A6AX_N@Z@std@@PEAI@Z; MPC3DStateHelper::RegisterFor3DCompositorRunningChanged(std::function<void (bool)>,uint *)
0x180056885  call    ?GetInstance@MPC3DStateHelper@@SAPEAV1@XZ; MPC3DStateHelper::GetInstance(void)
0x18005688a  mov     rcx, rax; SRWLock
0x18005688d  call    ?Is3DCompositorRunning@MPC3DStateHelper@@QEAA_NXZ; MPC3DStateHelper::Is3DCompositorRunning(void)
0x180056892  test    al, al
0x180056894  jz      short loc_1800568A0
0x180056896  mov     dl, 1; bool
0x180056898  mov     rcx, rbx; this
0x18005689b  call    ?OnCompositorRunningStateChanged@MPCRawInputProvider@@AEAAX_N@Z; MPCRawInputProvider::OnCompositorRunningStateChanged(bool)
0x1800568a0  xor     eax, eax
0x1800568a2  add     rsp, 0A8h
0x1800568a9  pop     rdi
0x1800568aa  pop     rsi
0x1800568ab  pop     rbx
0x1800568ac  pop     rbp
0x1800568ad  retn
0x1800568ae  mov     rcx, [rbp+5Fh]; this
0x1800568b2  call    ?FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_GetLastError(void *,uint,char const *)
```
