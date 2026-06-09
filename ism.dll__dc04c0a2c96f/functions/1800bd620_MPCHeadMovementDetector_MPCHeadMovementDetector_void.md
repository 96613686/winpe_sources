# MPCHeadMovementDetector::MPCHeadMovementDetector(void)

- ea: `0x1800bd620`
- end: `0x1800bd7d6`
- name: `??0MPCHeadMovementDetector@@QEAA@XZ`
- size: `438`
- prototype: `MPCHeadMovementDetector *__fastcall(MPCHeadMovementDetector *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180116410`

## callees

- `0x180055c04`
- `0x180069f90`
- `0x18006c2c0`
- `0x18006de30`
- `0x18008dcac`
- `0x18008e194`
- `0x180098128`
- `0x1800bd620`
- `0x18010af78`
- `0x180116cf0`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800bd740`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800bd740`
- `CoreMessaging!CoreUICreate` at `0x1800bd6ef`
- `CoreMessaging!CoreUICreate` at `0x1800bd6ef`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x1800bd793`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x1800bd793`

## string_xrefs

- `0x1800bd701`: `onecoreuap\windows\moderncore\inputv2\rawinputproviders\mpc\lib\mpcheadmovementdetector.cpp`
- `0x1800bd75b`: `onecoreuap\windows\moderncore\inputv2\rawinputproviders\mpc\lib\mpcheadmovementdetector.cpp`
- `0x1800bd7a5`: `onecoreuap\windows\moderncore\inputv2\rawinputproviders\mpc\lib\mpcheadmovementdetector.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
MPCHeadMovementDetector *__fastcall MPCHeadMovementDetector::MPCHeadMovementDetector(MPCHeadMovementDetector *this)
{
  _QWORD *v2; // rsi
  __int64 v3; // rcx
  int v4; // eax
  __int64 v5; // rax
  PTP_TIMER ThreadpoolTimer; // rax
  const char *v7; // r9
  DWORD v8; // eax
  _QWORD Recipient[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  char v12; // [rsp+58h] [rbp+10h] BYREF

  *(_QWORD *)this = 0;
  v2 = (_QWORD *)((char *)this + 8);
  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 4) = 17;
  *((_DWORD *)this + 5) = 3;
  *((_QWORD *)this + 3) = -170000;
  *((_QWORD *)this + 4) = Microsoft::BamoImpl::BamoPrincipalImpl::AsPrincipal((Microsoft::BamoImpl::BamoPrincipalImpl *)0xFFFFFFFFDC3CBA00LL);
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_BYTE *)this + 64) = 1;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_DWORD *)this + 34) = 1023410176;
  *((_DWORD *)this + 35) = 10000;
  *((_OWORD *)this + 9) = 0;
  *((_DWORD *)this + 40) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_DWORD *)this + 44) = 60000;
  v3 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = CoreUICreate(this);
  if ( v4 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\mpc\\lib\\mpcheadmovementdetector.cpp",
      (const char *)(unsigned int)v4,
      Recipient[0]);
  v5 = wil::GetActivationFactory<Windows::Perception::Internal::IPerceptionTimestampHelperStaticsInternal>(&v12);
  wil::com_ptr_t<Windows::Perception::Internal::IPerceptionTimestampHelperStaticsInternal,wil::err_exception_policy>::operator=(
    (char *)this + 96,
    v5);
  wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(&v12);
  ThreadpoolTimer = CreateThreadpoolTimer(lambda_aa0eaa0d8a3377c6799a200e781869ec_::_lambda_invoker_cdecl_, this, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    v2,
    ThreadpoolTimer);
  if ( !*v2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x38,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\mpc\\lib\\mpcheadmovementdetector.cpp",
      v7);
  Recipient[0] = MPCHeadMovementDetector::DisplayStateNotification;
  Recipient[1] = this;
  v8 = PowerSettingRegisterNotification(&GUID_CONSOLE_DISPLAY_STATE, 2u, Recipient, (PHPOWERNOTIFY)this + 7);
  if ( v8 )
    wil::details::in1diag3::_FailFast_Win32(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\mpc\\lib\\mpcheadmovementdetector.cpp",
      (const char *)v8,
      Recipient[0]);
  MPCHeadMovementDetector::ScheduleNextTimerCallback(this);
  return this;
}

```

## disassembly

```asm
0x1800bd620  mov     [rsp+arg_10], rbx
0x1800bd625  mov     [rsp+arg_18], rbp
0x1800bd62a  mov     [rsp+arg_0], rcx
0x1800bd62f  push    rsi
0x1800bd630  push    rdi
0x1800bd631  push    r14
0x1800bd633  sub     rsp, 30h
0x1800bd637  mov     rbx, rcx
0x1800bd63a  xor     ebp, ebp
0x1800bd63c  mov     [rcx], rbp
0x1800bd63f  lea     rsi, [rcx+8]
0x1800bd643  mov     [rsi], rbp
0x1800bd646  mov     dword ptr [rcx+10h], 11h
0x1800bd64d  mov     dword ptr [rcx+14h], 3
0x1800bd654  mov     qword ptr [rcx+18h], 0FFFFFFFFFFFD67F0h
0x1800bd65c  mov     rcx, 0FFFFFFFFDC3CBA00h; this
0x1800bd663  call    ?AsPrincipal@BamoPrincipalImpl@BamoImpl@Microsoft@@UEAAPEAV123@XZ; Microsoft::BamoImpl::BamoPrincipalImpl::AsPrincipal(void)
0x1800bd668  mov     [rbx+20h], rax
0x1800bd66c  mov     [rbx+28h], rbp
0x1800bd670  mov     [rbx+30h], rbp
0x1800bd674  mov     [rbx+38h], rbp
0x1800bd678  mov     byte ptr [rbx+40h], 1
0x1800bd67c  mov     [rbx+48h], rbp
0x1800bd680  mov     [rbx+50h], rbp
0x1800bd684  mov     [rbx+58h], rbp
0x1800bd688  mov     [rbx+60h], rbp
0x1800bd68c  mov     [rbx+68h], rbp
0x1800bd690  mov     [rbx+70h], rbp
0x1800bd694  mov     [rbx+78h], rbp
0x1800bd698  mov     [rbx+80h], rbp
0x1800bd69f  mov     dword ptr [rbx+88h], 3D000000h
0x1800bd6a9  mov     dword ptr [rbx+8Ch], 2710h
0x1800bd6b3  xorps   xmm0, xmm0
0x1800bd6b6  movups  xmmword ptr [rbx+90h], xmm0
0x1800bd6bd  mov     [rbx+0A0h], ebp
0x1800bd6c3  mov     [rbx+0A8h], rbp
0x1800bd6ca  mov     dword ptr [rbx+0B0h], 0EA60h
0x1800bd6d4  mov     rcx, [rbx]
0x1800bd6d7  mov     [rbx], rbp
0x1800bd6da  test    rcx, rcx
0x1800bd6dd  jz      short loc_1800BD6EC
0x1800bd6df  mov     rax, [rcx]
0x1800bd6e2  mov     rax, [rax+10h]
0x1800bd6e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd6eb  nop
0x1800bd6ec  mov     rcx, rbx
0x1800bd6ef  call    cs:__imp_CoreUICreate
0x1800bd6f5  mov     rcx, [rsp+48h]; this
0x1800bd6fa  test    eax, eax
0x1800bd6fc  jns     short loc_1800BD713
0x1800bd6fe  mov     r9d, eax; char *
0x1800bd701  lea     r8, aOnecoreuapWind_175; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800bd708  mov     edx, 2Dh ; '-'; void *
0x1800bd70d  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800bd713  lea     rcx, [rsp+48h+arg_8]
0x1800bd718  call    ??$GetActivationFactory@UIPerceptionTimestampHelperStaticsInternal@Internal@Perception@Windows@@@wil@@YA?AV?$com_ptr_t@UIPerceptionTimestampHelperStaticsInternal@Internal@Perception@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Perception::Internal::IPerceptionTimestampHelperStaticsInternal>(ushort const *)
0x1800bd71d  mov     rdx, rax
0x1800bd720  lea     rcx, [rbx+60h]
0x1800bd724  call    ??4?$com_ptr_t@UIPerceptionTimestampHelperStaticsInternal@Internal@Perception@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<Windows::Perception::Internal::IPerceptionTimestampHelperStaticsInternal,wil::err_exception_policy>::operator=(wil::com_ptr_t<Windows::Perception::Internal::IPerceptionTimestampHelperStaticsInternal,wil::err_exception_policy> &&)
0x1800bd729  lea     rcx, [rsp+48h+arg_8]
0x1800bd72e  call    ??1?$com_ptr_t@UIMPCInputProviderBase@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(void)
0x1800bd733  xor     r8d, r8d; pcbe
0x1800bd736  mov     rdx, rbx; pv
0x1800bd739  lea     rcx, _lambda_aa0eaa0d8a3377c6799a200e781869ec____lambda_invoker_cdecl_; pfnti
0x1800bd740  call    cs:__imp_CreateThreadpoolTimer
0x1800bd746  mov     rdx, rax
0x1800bd749  mov     rcx, rsi
0x1800bd74c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800bd751  mov     rcx, [rsp+48h]; this
0x1800bd756  cmp     [rsi], rbp
0x1800bd759  jnz     short loc_1800BD76D
0x1800bd75b  lea     r8, aOnecoreuapWind_175; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800bd762  mov     edx, 38h ; '8'; void *
0x1800bd767  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800bd76d  lea     rax, ?DisplayStateNotification@MPCHeadMovementDetector@@CAKPEAXK0@Z; MPCHeadMovementDetector::DisplayStateNotification(void *,ulong,void *)
0x1800bd774  mov     [rsp+48h+Recipient], rax; unsigned int
0x1800bd779  mov     [rsp+48h+var_20], rbx
0x1800bd77e  lea     r9, [rbx+38h]; RegistrationHandle
0x1800bd782  lea     r8, [rsp+48h+Recipient]; Recipient
0x1800bd787  mov     edx, 2; Flags
0x1800bd78c  lea     rcx, GUID_CONSOLE_DISPLAY_STATE; SettingGuid
0x1800bd793  call    cs:__imp_PowerSettingRegisterNotification
0x1800bd799  mov     rcx, [rsp+48h]; this
0x1800bd79e  test    eax, eax
0x1800bd7a0  jz      short loc_1800BD7B7
0x1800bd7a2  mov     r9d, eax; char *
0x1800bd7a5  lea     r8, aOnecoreuapWind_175; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800bd7ac  mov     edx, 3Fh ; '?'; void *
0x1800bd7b1  call    ?_FailFast_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_FailFast_Win32(void *,uint,char const *,ulong)
0x1800bd7b7  mov     rcx, rbx; this
0x1800bd7ba  call    ?ScheduleNextTimerCallback@MPCHeadMovementDetector@@AEAAXXZ; MPCHeadMovementDetector::ScheduleNextTimerCallback(void)
0x1800bd7bf  nop
0x1800bd7c0  mov     rax, rbx
0x1800bd7c3  mov     rbx, [rsp+48h+arg_10]
0x1800bd7c8  mov     rbp, [rsp+48h+arg_18]
0x1800bd7cd  add     rsp, 30h
0x1800bd7d1  pop     r14
0x1800bd7d3  pop     rdi
0x1800bd7d4  pop     rsi
0x1800bd7d5  retn
```
