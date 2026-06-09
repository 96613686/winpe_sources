# Microsoft::HostGuardian::Client::HgService::Start(void)

- ea: `0x18000a068`
- end: `0x18000a4b2`
- name: `?Start@HgService@Client@HostGuardian@Microsoft@@QEAAXXZ`
- size: `1098`
- prototype: `void __fastcall(Microsoft::HostGuardian::Client::HgService *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180007920`

## callees

- `0x180001770`
- `0x18000734c`
- `0x1800077a0`
- `0x180008760`
- `0x1800087a4`
- `0x180009fc8`
- `0x18000a068`
- `0x18000a7bc`
- `0x180017010`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000a0af`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000a0cb`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000a0af`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000a0cb`
- `msvcp_win!_Mtx_lock` at `0x18000a0a0`
- `msvcp_win!_Mtx_lock` at `0x18000a0a0`
- `msvcp_win!_Mtx_unlock` at `0x18000a3f4`
- `msvcp_win!_Mtx_unlock` at `0x18000a3f4`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000a0e0`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000a0e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a126`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a1d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a25b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a126`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a1d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a25b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a101`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a248`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a101`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a248`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000a3ea`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000a3ea`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000a3cc`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000a3cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a10d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a10d`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000a144`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000a144`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x18000a253`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x18000a253`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x18000a267`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x18000a267`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a2ba`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a2ba`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18000a1cb`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18000a1cb`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x18000a223`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x18000a223`

## string_xrefs

- `0x18000a441`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18000a427`: `servercommon\base\securehostingservice\common\service\lib\hgservice.cpp`
- `0x18000a461`: `servercommon\base\securehostingservice\common\service\lib\hgservice.cpp`
- `0x18000a476`: `servercommon\base\securehostingservice\common\service\lib\hgservice.cpp`
- `0x18000a48b`: `servercommon\base\securehostingservice\common\service\lib\hgservice.cpp`
- `0x18000a4a0`: `servercommon\base\securehostingservice\common\service\lib\hgservice.cpp`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::HgService::Start(Microsoft::HostGuardian::Client::HgService *this)
{
  char *v2; // rsi
  const char *v3; // r9
  HANDLE Event; // r14
  void *v5; // rbx
  DWORD LastError; // r15d
  __int64 v7; // r8
  const char *v8; // r9
  __int64 v9; // r13
  Microsoft::HostGuardian::Client::HgService *v10; // r12
  char *v11; // r14
  DWORD v12; // ebx
  unsigned int v13; // eax
  int v14; // eax
  __int64 v15; // r15
  DWORD v16; // ebx
  int v17; // eax
  __int64 v18; // rcx
  HRESULT Instance; // eax
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // r8
  char v23; // al
  int ppv; // [rsp+20h] [rbp-88h]
  _QWORD v25[2]; // [rsp+40h] [rbp-68h] BYREF
  GUID ProviderId; // [rsp+50h] [rbp-58h] BYREF
  const wchar_t *v27; // [rsp+60h] [rbp-48h]
  __int64 v28; // [rsp+68h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v2 = (char *)this + 96;
  *(_QWORD *)&ProviderId.Data1 = (char *)this + 96;
  if ( _Mtx_lock((Microsoft::HostGuardian::Client::HgService *)((char *)this + 96)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *((_DWORD *)v2 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v2 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CC8,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      v3);
  GetLastError();
  v5 = (void *)*((_QWORD *)this + 11);
  if ( v5 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v5) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v7, v8);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 11) = Event;
  InitOnceExecuteOnce(
    &Microsoft::WRL::Details::OutOfProcModuleBase<HgServiceModule>::initOnceOutOfProc_,
    (PINIT_ONCE_FN)_lambda_ea3f45fb70643df847a3ec5af9abdeb0_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_1800205E8 = 1;
  if ( !qword_1800205D8 )
  {
    byte_180020608 = 1;
    byte_1800205F8 = 0;
    qword_1800205F0 = (__int64)off_180018260;
    qword_180020600 = (__int64)this;
    qword_1800205D8 = (__int64)&qword_1800205F0;
  }
  v25[0] = *(_QWORD *)(*((_QWORD *)this + 9) + 192LL);
  v9 = *((_QWORD *)this + 11);
  if ( *((_QWORD *)this + 3) <= 7u )
    v10 = this;
  else
    v10 = *(Microsoft::HostGuardian::Client::HgService **)this;
  v11 = (char *)*((_QWORD *)this + 10);
  if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v12 = GetLastError();
    UnregisterWait(v11);
    SetLastError(v12);
  }
  *((_QWORD *)this + 10) = 0;
  v13 = ((__int64 (__fastcall *)(char *, Microsoft::HostGuardian::Client::HgService *, __int64, void (__fastcall *)(Microsoft::HostGuardian::Client::HgService *, unsigned __int8)))v25[0])(
          (char *)this + 80,
          v10,
          v9,
          Microsoft::HostGuardian::Client::HgService::ServiceStopCallback);
  if ( v13 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x6E,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservice.cpp",
      (const char *)v13,
      (unsigned int)this);
  v14 = CoRegisterServerShutdownDelay(*((_QWORD *)this + 11), 28800000);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x70,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservice.cpp",
      (const char *)(unsigned int)v14,
      (int)this);
  v15 = *((_QWORD *)this + 22);
  if ( v15 )
  {
    v16 = GetLastError();
    CoDecrementMTAUsage(v15);
    SetLastError(v16);
  }
  *((_QWORD *)this + 22) = 0;
  v17 = CoIncrementMTAUsage((char *)this + 176);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xED,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservice.cpp",
      (const char *)(unsigned int)v17,
      (int)this);
  v18 = *((_QWORD *)this + 23);
  *((_QWORD *)this + 23) = 0;
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  Instance = CoCreateInstance(
               &CLSID_ContextSwitcher,
               0,
               1u,
               &GUID_000001da_0000_0000_c000_000000000046,
               (LPVOID *)this + 23);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF2,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservice.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
  v25[0] = 0;
  v25[1] = this;
  v20 = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall *)(), _QWORD *, GUID *))(**((_QWORD **)this + 23) + 24LL))(
          *((_QWORD *)this + 23),
          lambda_7661a4ab4884d071d929af4ebb48bce8_::_lambda_invoker_cdecl_,
          v25,
          &IID_IContextCallback);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xFE,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservice.cpp",
      (const char *)(unsigned int)v20,
      5);
  Microsoft::HostGuardian::Client::HgService::SetStatus(this, 4);
  v23 = Microsoft_Windows_HostGuardianClient_ServiceEnableBits;
  if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 1) != 0 )
  {
    McGenEventWrite_EventWriteTransfer(v21, ServiceStart, v22, 1, &ProviderId);
    v23 = Microsoft_Windows_HostGuardianClient_ServiceEnableBits;
  }
  if ( (v23 & 2) != 0 )
  {
    v27 = L"Registering HGS quality provider";
    v28 = 66;
    McGenEventWrite_EventWriteTransfer(v21, ServiceDebugInformational, v22, 2, &ProviderId);
  }
  ProviderId = *(GUID *)&(*off_180020050)[-8];
  if ( RegHandle )
    __fastfail(5u);
  xmmword_180020070 = 0;
  if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_180020048, &RegHandle) )
    EventSetInformation(RegHandle, 2, (__int16 *)off_180020050, *(unsigned __int16 *)off_180020050);
  _Mtx_unlock((_Mtx_t)v2);
}

```

## disassembly

```asm
0x18000a068  mov     [rsp+arg_8], rbx
0x18000a06d  mov     [rsp+arg_10], rsi
0x18000a072  push    rdi
0x18000a073  push    r12
0x18000a075  push    r13
0x18000a077  push    r14
0x18000a079  push    r15
0x18000a07b  sub     rsp, 80h
0x18000a082  mov     rax, cs:__security_cookie
0x18000a089  xor     rax, rsp
0x18000a08c  mov     [rsp+0A8h+var_38], rax
0x18000a091  mov     rdi, rcx
0x18000a094  lea     rsi, [rcx+60h]
0x18000a098  mov     qword ptr [rsp+0A8h+ProviderId.Data1], rsi
0x18000a09d  mov     rcx, rsi; _Mtx_t
0x18000a0a0  call    cs:__imp__Mtx_lock
0x18000a0a6  test    eax, eax
0x18000a0a8  jz      short loc_18000A0B6
0x18000a0aa  mov     ecx, 5
0x18000a0af  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000a0b5  int     3; Trap to Debugger
0x18000a0b6  cmp     dword ptr [rsi+4Ch], 7FFFFFFFh
0x18000a0bd  jnz     short loc_18000A0D2
0x18000a0bf  mov     dword ptr [rsi+4Ch], 7FFFFFFEh
0x18000a0c6  mov     ecx, 6
0x18000a0cb  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000a0d1  nop
0x18000a0d2  xor     edx, edx; lpName
0x18000a0d4  xor     ecx, ecx; lpEventAttributes
0x18000a0d6  mov     r9d, 1F0003h; dwDesiredAccess
0x18000a0dc  lea     r8d, [rdx+1]; dwFlags
0x18000a0e0  call    cs:__imp_CreateEventExW
0x18000a0e6  mov     r14, rax
0x18000a0e9  test    rax, rax
0x18000a0ec  jz      loc_18000A439
0x18000a0f2  call    cs:__imp_GetLastError
0x18000a0f8  mov     rbx, [rdi+58h]
0x18000a0fc  test    rbx, rbx
0x18000a0ff  jz      short loc_18000A12C
0x18000a101  call    cs:__imp_GetLastError
0x18000a107  mov     r15d, eax
0x18000a10a  mov     rcx, rbx; hObject
0x18000a10d  call    cs:__imp_CloseHandle
0x18000a113  mov     rcx, [rsp+0A8h]; this
0x18000a11b  test    eax, eax
0x18000a11d  jz      loc_18000A453
0x18000a123  mov     ecx, r15d; dwErrCode
0x18000a126  call    cs:__imp_SetLastError
0x18000a12c  mov     [rdi+58h], r14
0x18000a130  xor     r9d, r9d; Context
0x18000a133  xor     r8d, r8d; Parameter
0x18000a136  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_ea3f45fb70643df847a3ec5af9abdeb0_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000a13d  lea     rcx, ?initOnceOutOfProc_@?$OutOfProcModuleBase@VHgServiceModule@@@Details@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18000a144  call    cs:__imp_InitOnceExecuteOnce
0x18000a14a  mov     cs:byte_1800205E8, 1
0x18000a151  cmp     cs:qword_1800205D8, 0
0x18000a159  jnz     short loc_18000A18C
0x18000a15b  mov     cs:byte_180020608, 1
0x18000a162  mov     cs:byte_1800205F8, 0
0x18000a169  lea     rax, off_180018260
0x18000a170  mov     cs:qword_1800205F0, rax
0x18000a177  mov     cs:qword_180020600, rdi
0x18000a17e  lea     rax, qword_1800205F0
0x18000a185  mov     cs:qword_1800205D8, rax
0x18000a18c  mov     rax, [rdi+48h]
0x18000a190  mov     rax, [rax+0C0h]
0x18000a197  mov     [rsp+0A8h+var_68], rax
0x18000a19c  mov     r13, [rdi+58h]
0x18000a1a0  cmp     qword ptr [rdi+18h], 7
0x18000a1a5  jbe     short loc_18000A1AC
0x18000a1a7  mov     r12, [rdi]
0x18000a1aa  jmp     short loc_18000A1AF
0x18000a1ac  mov     r12, rdi
0x18000a1af  lea     r15, [rdi+50h]
0x18000a1b3  mov     r14, [r15]
0x18000a1b6  lea     rax, [r14-1]
0x18000a1ba  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a1be  ja      short loc_18000A1D9
0x18000a1c0  call    cs:__imp_GetLastError
0x18000a1c6  mov     ebx, eax
0x18000a1c8  mov     rcx, r14; WaitHandle
0x18000a1cb  call    cs:__imp_UnregisterWait
0x18000a1d1  mov     ecx, ebx; dwErrCode
0x18000a1d3  call    cs:__imp_SetLastError
0x18000a1d9  mov     qword ptr [r15], 0
0x18000a1e0  mov     dword ptr [rsp+0A8h+var_80], 18h
0x18000a1e8  mov     [rsp+0A8h+ppv], rdi; int
0x18000a1ed  lea     r9, ?ServiceStopCallback@HgService@Client@HostGuardian@Microsoft@@KAXPEAXE@Z; Microsoft::HostGuardian::Client::HgService::ServiceStopCallback(void *,uchar)
0x18000a1f4  mov     r8, r13
0x18000a1f7  mov     rdx, r12
0x18000a1fa  mov     rcx, r15
0x18000a1fd  mov     rax, [rsp+0A8h+var_68]
0x18000a202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a207  mov     rcx, [rsp+0A8h]; this
0x18000a20f  xor     r12d, r12d
0x18000a212  test    eax, eax
0x18000a214  jnz     loc_18000A45E
0x18000a21a  mov     edx, 1B77400h
0x18000a21f  mov     rcx, [rdi+58h]
0x18000a223  call    cs:__imp_CoRegisterServerShutdownDelay
0x18000a229  mov     rcx, [rsp+0A8h]; this
0x18000a231  test    eax, eax
0x18000a233  js      loc_18000A473
0x18000a239  lea     r14, [rdi+0B0h]
0x18000a240  mov     r15, [r14]
0x18000a243  test    r15, r15
0x18000a246  jz      short loc_18000A261
0x18000a248  call    cs:__imp_GetLastError
0x18000a24e  mov     ebx, eax
0x18000a250  mov     rcx, r15
0x18000a253  call    cs:__imp_CoDecrementMTAUsage
0x18000a259  mov     ecx, ebx; dwErrCode
0x18000a25b  call    cs:__imp_SetLastError
0x18000a261  mov     [r14], r12
0x18000a264  mov     rcx, r14
0x18000a267  call    cs:__imp_CoIncrementMTAUsage
0x18000a26d  mov     rcx, [rsp+0A8h]; this
0x18000a275  test    eax, eax
0x18000a277  js      loc_18000A488
0x18000a27d  lea     rbx, [rdi+0B8h]
0x18000a284  mov     rcx, [rbx]
0x18000a287  mov     [rbx], r12
0x18000a28a  test    rcx, rcx
0x18000a28d  jz      short loc_18000A29C
0x18000a28f  mov     rax, [rcx]
0x18000a292  mov     rax, [rax+10h]
0x18000a296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a29b  nop
0x18000a29c  mov     [rsp+0A8h+ppv], rbx; int
0x18000a2a1  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x18000a2a8  mov     r14d, 1
0x18000a2ae  mov     r8d, r14d; dwClsContext
0x18000a2b1  xor     edx, edx; pUnkOuter
0x18000a2b3  lea     rcx, CLSID_ContextSwitcher; rclsid
0x18000a2ba  call    cs:__imp_CoCreateInstance
0x18000a2c0  mov     rcx, [rsp+0A8h]; this
0x18000a2c8  test    eax, eax
0x18000a2ca  js      loc_18000A49D
0x18000a2d0  mov     [rsp+0A8h+var_68], r12
0x18000a2d5  mov     [rsp+0A8h+var_60], rdi
0x18000a2da  mov     rcx, [rbx]
0x18000a2dd  mov     rax, [rcx]
0x18000a2e0  mov     [rsp+0A8h+var_80], r12
0x18000a2e5  mov     dword ptr [rsp+0A8h+ppv], 5; int
0x18000a2ed  lea     r9, IID_IContextCallback
0x18000a2f4  lea     r8, [rsp+0A8h+var_68]
0x18000a2f9  lea     rdx, _lambda_7661a4ab4884d071d929af4ebb48bce8____lambda_invoker_cdecl_
0x18000a300  mov     rax, [rax+18h]
0x18000a304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a309  mov     rcx, [rsp+0A8h]; this
0x18000a311  test    eax, eax
0x18000a313  js      loc_18000A424
0x18000a319  lea     edx, [r14+3]; unsigned int
0x18000a31d  mov     rcx, rdi; this
0x18000a320  call    ?SetStatus@HgService@Client@HostGuardian@Microsoft@@IEAAXK@Z; Microsoft::HostGuardian::Client::HgService::SetStatus(ulong)
0x18000a325  mov     eax, cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits
0x18000a32b  test    r14b, al
0x18000a32e  jz      short loc_18000A34F
0x18000a330  lea     rax, [rsp+0A8h+ProviderId]
0x18000a335  mov     [rsp+0A8h+ppv], rax
0x18000a33a  mov     r9d, r14d
0x18000a33d  lea     rdx, ServiceStart
0x18000a344  call    McGenEventWrite_EventWriteTransfer
0x18000a349  mov     eax, cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits
0x18000a34f  mov     ebx, 2
0x18000a354  test    bl, al
0x18000a356  jz      short loc_18000A386
0x18000a358  lea     rax, aRegisteringHgs; "Registering HGS quality provider"
0x18000a35f  mov     [rsp+0A8h+var_48], rax
0x18000a364  mov     [rsp+0A8h+var_40], 42h ; 'B'
0x18000a36d  lea     rax, [rsp+0A8h+ProviderId]
0x18000a372  mov     [rsp+0A8h+ppv], rax
0x18000a377  mov     r9d, ebx
0x18000a37a  lea     rdx, ServiceDebugInformational
0x18000a381  call    McGenEventWrite_EventWriteTransfer
0x18000a386  mov     rax, cs:off_180020050
0x18000a38d  movups  xmm0, xmmword ptr [rax-10h]
0x18000a391  movdqu  xmmword ptr [rsp+0A8h+ProviderId.Data1], xmm0
0x18000a397  cmp     cs:RegHandle, r12
0x18000a39e  jz      short loc_18000A3A7
0x18000a3a0  mov     ecx, 5
0x18000a3a5  int     29h; Win8: RtlFailFast(ecx)
0x18000a3a7  xorps   xmm0, xmm0
0x18000a3aa  movdqu  cs:xmmword_180020070, xmm0
0x18000a3b2  lea     r9, RegHandle; RegHandle
0x18000a3b9  lea     r8, dword_180020048; CallbackContext
0x18000a3c0  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000a3c7  lea     rcx, [rsp+0A8h+ProviderId]; ProviderId
0x18000a3cc  call    cs:__imp_EventRegister
0x18000a3d2  test    eax, eax
0x18000a3d4  jnz     short loc_18000A3F1
0x18000a3d6  mov     r8, cs:off_180020050
0x18000a3dd  movzx   r9d, word ptr [r8]
0x18000a3e1  mov     edx, ebx
0x18000a3e3  mov     rcx, cs:RegHandle
0x18000a3ea  call    cs:__imp_EventSetInformation
0x18000a3f0  nop
0x18000a3f1  mov     rcx, rsi; _Mtx_t
0x18000a3f4  call    cs:__imp__Mtx_unlock
0x18000a3fa  mov     rcx, [rsp+0A8h+var_38]
0x18000a3ff  xor     rcx, rsp; StackCookie
0x18000a402  call    __security_check_cookie
0x18000a407  lea     r11, [rsp+0A8h+var_28]
0x18000a40f  mov     rbx, [r11+38h]
0x18000a413  mov     rsi, [r11+40h]
0x18000a417  mov     rsp, r11
0x18000a41a  pop     r15
0x18000a41c  pop     r14
0x18000a41e  pop     r13
0x18000a420  pop     r12
0x18000a422  pop     rdi
0x18000a423  retn
0x18000a424  mov     r9d, eax; char *
0x18000a427  lea     r8, aServercommonBa_0; "servercommon\\base\\securehostingservic"...
0x18000a42e  mov     edx, 0FEh; void *
0x18000a433  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000a439  mov     rcx, [rsp+0A8h]; this
0x18000a441  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a448  mov     edx, 1CC8h; void *
0x18000a44d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18000a453  mov     edx, 0A0Bh; void *
0x18000a458  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a45e  mov     r9d, eax; char *
0x18000a461  lea     r8, aServercommonBa_0; "servercommon\\base\\securehostingservic"...
0x18000a468  mov     edx, 6Eh ; 'n'; void *
0x18000a46d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000a473  mov     r9d, eax; char *
0x18000a476  lea     r8, aServercommonBa_0; "servercommon\\base\\securehostingservic"...
0x18000a47d  mov     edx, 70h ; 'p'; void *
0x18000a482  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000a488  mov     r9d, eax; char *
0x18000a48b  lea     r8, aServercommonBa_0; "servercommon\\base\\securehostingservic"...
0x18000a492  mov     edx, 0EDh; void *
0x18000a497  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000a49d  mov     r9d, eax; char *
0x18000a4a0  lea     r8, aServercommonBa_0; "servercommon\\base\\securehostingservic"...
0x18000a4a7  mov     edx, 0F2h; void *
0x18000a4ac  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
