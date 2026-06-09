# ?CreateCrossVmEventInternal@CallbackNotifier@shared@@AEAA?AV?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@PEBD@Z

- ea: `0x180092490`
- end: `0x18009278f`
- name: `?CreateCrossVmEventInternal@CallbackNotifier@shared@@AEAA?AV?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@PEBD@Z`
- size: `767`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180091c90`

## callees

- `0x18003d0e0`
- `0x180041b5c`
- `0x1800624cc`
- `0x180086434`
- `0x180092490`
- `0x180093e40`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x18011d8c4`
- `0x180143248`
- `0x18019ec40`
- `0x18019ec84`
- `0x1801a020c`
- `0x1801f6fb0`
- `0x1801fcb36`
- `0x180209770`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180092574`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180092574`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800925cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800925cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800926f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800926f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009257f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800925da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009257f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800925da`
- `ntdll!RtlNtStatusToDosError` at `0x1800926c1`
- `ntdll!RtlNtStatusToDosError` at `0x1800926c1`
- `ext-ms-win-containers-policymanagercli-l1-1-0!CpmcGetContainerIdForUser` at `0x18009253a`
- `ext-ms-win-containers-policymanagercli-l1-1-0!CpmcGetContainerIdForUser` at `0x18009253a`

## string_xrefs

- `0x18009271e`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1800925c2`: `NtCreateCrossVmEvent`
- `0x18009256d`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall shared::CallbackNotifier::CreateCrossVmEventInternal(__int64 a1, _QWORD *a2, const char *a3)
{
  __int64 v4; // rbx
  char ContainerIdForUserPresent; // al
  unsigned int ContainerIdForUser; // eax
  HMODULE ModuleHandleA; // rax
  signed int LastError; // eax
  __int64 v9; // rax
  FARPROC ProcAddress; // rax
  __int64 (__fastcall *v11)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // rbx
  signed int v12; // eax
  __int64 v13; // rax
  unsigned int v14; // esi
  NTSTATUS v15; // eax
  signed int v16; // eax
  unsigned int v17; // ebx
  int v18; // ecx
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rax
  char *v24; // [rsp+28h] [rbp-D8h]
  const char *v25; // [rsp+30h] [rbp-D0h]
  unsigned int v26; // [rsp+44h] [rbp-BCh] BYREF
  _QWORD v27[2]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v28[3]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v30[24]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v31; // [rsp+C0h] [rbp-40h] BYREF
  char v32; // [rsp+D0h] [rbp-30h]
  __int128 v33; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v34; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+28h]

  v27[1] = a2;
  v31 = 0;
  cdp::CDP_UUID::FromString((cdp::CDP_UUID *)&v31, a3);
  v34 = v31;
  shared::GetCallerSid(v28, 0);
  v4 = v28[0];
  ContainerIdForUserPresent = IsCpmcGetContainerIdForUserPresent();
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x2F,
    (unsigned int)"onecore\\internal\\base\\inc\\ContainerPolicyManagerClient.h",
    (const char *)0x80004001LL,
    ContainerIdForUserPresent == 0,
    (bool)"The container policy manager APIs are not available.",
    v25);
  v31 = 0;
  ContainerIdForUser = CpmcGetContainerIdForUser(v4, &v31);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x34,
    (unsigned int)"onecore\\internal\\base\\inc\\ContainerPolicyManagerClient.h",
    (const char *)ContainerIdForUser,
    (int)"Failed to get the VAIL container ID for user from Container Policy Manager.",
    v24);
  v33 = v31;
  ModuleHandleA = GetModuleHandleA("ntdll.dll");
  if ( !ModuleHandleA )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    *(_QWORD *)&v31 = ".\\callbacknotifier.cpp";
    DWORD2(v31) = 76;
    v9 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, &v31, (unsigned int)LastError);
    cdp::CdpThrow<cdp::hresult_exception>(&v31, v9);
  }
  ProcAddress = GetProcAddress(ModuleHandleA, "NtCreateCrossVmEvent");
  v11 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))ProcAddress;
  if ( !ProcAddress )
  {
    v12 = GetLastError();
    if ( v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
    *(_QWORD *)&v31 = ".\\callbacknotifier.cpp";
    DWORD2(v31) = 78;
    v13 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, &v31, (unsigned int)v12);
    cdp::CdpThrow<cdp::hresult_exception>(&v31, v13);
  }
  *a2 = 0;
  v31 = (unsigned __int64)a2;
  v32 = 1;
  v14 = ((unsigned int (__fastcall *)(char *, __int64, _QWORD, _QWORD, __int128 *, __int128 *))ProcAddress)(
          (char *)&v31 + 8,
          2031619,
          0,
          0,
          &v34,
          &v33) >> 31;
  if ( v32 )
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      v31,
      *((_QWORD *)&v31 + 1));
  if ( (_BYTE)v14 )
  {
    v31 = (unsigned __int64)a2;
    v32 = 1;
    v15 = v11((char *)&v31 + 8, 2031619, 0, 0, &v34, &v33);
    v16 = RtlNtStatusToDosError(v15);
    v17 = v16;
    if ( v16 > 0 )
      v17 = (unsigned __int16)v16 | 0x80070000;
    __1__out_param_t_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAA_XZ(&v31);
    *(_QWORD *)&v31 = ".\\callbacknotifier.cpp";
    DWORD2(v31) = 82;
    v26 = v17;
    v27[0] = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v18,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v26,
      (unsigned int)&v31,
      (__int64)&v31 + 8,
      (__int64)v27);
    v19 = cdp::ExceptionStackFromSourceLocationInfo(v30, &v31);
    v22 = cdp::ErrorCodeToString(v17, v20, v21, v19);
    ConnectedDevices::Exception::Exception(pExceptionObject, v17, v22);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  std::vector<unsigned char>::_Tidy(v28);
  return a2;
}

```

## disassembly

```asm
0x180092490  mov     [rsp-8+arg_0], rbx
0x180092495  push    rbp
0x180092496  push    rsi
0x180092497  push    rdi
0x180092498  lea     rbp, [rsp-10h]
0x18009249d  sub     rsp, 110h
0x1800924a4  mov     rax, cs:__security_cookie
0x1800924ab  xor     rax, rsp
0x1800924ae  mov     [rbp+20h+var_20], rax
0x1800924b2  mov     rdi, rdx
0x1800924b5  mov     [rsp+120h+var_D0], rdx
0x1800924ba  mov     [rsp+120h+var_E0], 0
0x1800924c2  xorps   xmm0, xmm0
0x1800924c5  movups  [rbp+20h+var_60], xmm0
0x1800924c9  mov     rdx, r8; char *
0x1800924cc  lea     rcx, [rbp+20h+var_60]; this
0x1800924d0  call    ?FromString@CDP_UUID@cdp@@QEAAXPEBD@Z; cdp::CDP_UUID::FromString(char const *)
0x1800924d5  movaps  xmm0, [rbp+20h+var_60]
0x1800924d9  movdqa  [rbp+20h+var_30], xmm0
0x1800924de  xor     edx, edx
0x1800924e0  lea     rcx, [rsp+120h+var_C8]
0x1800924e5  call    ?GetCallerSid@shared@@YA?AV?$vector@EV?$allocator@E@std@@@std@@W4SIDType@1@@Z; shared::GetCallerSid(shared::SIDType)
0x1800924ea  mov     [rsp+120h+var_E0], 2
0x1800924f2  mov     rbx, [rsp+120h+var_C8]
0x1800924f7  call    IsCpmcGetContainerIdForUserPresent
0x1800924fc  test    al, al
0x1800924fe  setz    al
0x180092501  mov     rcx, [rbp+28h]; this
0x180092505  lea     rdx, aTheContainerPo; "The container policy manager APIs are n"...
0x18009250c  mov     [rsp+120h+var_F8], rdx; char *
0x180092511  mov     [rsp+120h+var_100], al; char
0x180092515  mov     r9d, 80004001h; char *
0x18009251b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\base\\inc\\Container"...
0x180092522  mov     edx, 2Fh ; '/'; void *
0x180092527  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18009252c  xorps   xmm0, xmm0
0x18009252f  movups  [rbp+20h+var_60], xmm0
0x180092533  lea     rdx, [rbp+20h+var_60]
0x180092537  mov     rcx, rbx
0x18009253a  call    cs:__imp_CpmcGetContainerIdForUser
0x180092540  mov     rcx, [rbp+28h]; this
0x180092544  lea     rdx, aFailedToGetThe_6; "Failed to get the VAIL container ID for"...
0x18009254b  mov     qword ptr [rsp+120h+var_100], rdx; int
0x180092550  mov     r9d, eax; char *
0x180092553  lea     r8, aOnecoreInterna_0; "onecore\\internal\\base\\inc\\Container"...
0x18009255a  mov     edx, 34h ; '4'; void *
0x18009255f  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180092564  movaps  xmm0, [rbp+20h+var_60]
0x180092568  movdqa  [rbp+20h+var_40], xmm0
0x18009256d  lea     rcx, ModuleName; "ntdll.dll"
0x180092574  call    cs:__imp_GetModuleHandleA
0x18009257a  test    rax, rax
0x18009257d  jnz     short loc_1800925C2
0x18009257f  call    cs:__imp_GetLastError
0x180092585  test    eax, eax
0x180092587  jle     short loc_180092591
0x180092589  movzx   eax, ax
0x18009258c  or      eax, 80070000h
0x180092591  lea     rcx, aCallbacknotifi_0; ".\\callbacknotifier.cpp"
0x180092598  mov     qword ptr [rbp+20h+var_60], rcx
0x18009259c  mov     dword ptr [rbp+20h+var_60+8], 4Ch ; 'L'
0x1800925a3  mov     r8d, eax
0x1800925a6  lea     rdx, [rbp+20h+var_60]
0x1800925aa  lea     rcx, [rsp+120h+pExceptionObject]
0x1800925af  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1800925b4  nop
0x1800925b5  mov     rdx, rax
0x1800925b8  lea     rcx, [rbp+20h+var_60]
0x1800925bc  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800925c2  lea     rdx, ProcName; "NtCreateCrossVmEvent"
0x1800925c9  mov     rcx, rax; hModule
0x1800925cc  call    cs:__imp_GetProcAddress
0x1800925d2  mov     rbx, rax
0x1800925d5  test    rax, rax
0x1800925d8  jnz     short loc_18009261D
0x1800925da  call    cs:__imp_GetLastError
0x1800925e0  test    eax, eax
0x1800925e2  jle     short loc_1800925EC
0x1800925e4  movzx   eax, ax
0x1800925e7  or      eax, 80070000h
0x1800925ec  lea     rcx, aCallbacknotifi_0; ".\\callbacknotifier.cpp"
0x1800925f3  mov     qword ptr [rbp+20h+var_60], rcx
0x1800925f7  mov     dword ptr [rbp+20h+var_60+8], 4Eh ; 'N'
0x1800925fe  mov     r8d, eax
0x180092601  lea     rdx, [rbp+20h+var_60]
0x180092605  lea     rcx, [rsp+120h+pExceptionObject]
0x18009260a  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x18009260f  nop
0x180092610  mov     rdx, rax
0x180092613  lea     rcx, [rbp+20h+var_60]
0x180092617  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x18009261d  mov     qword ptr [rdi], 0
0x180092624  mov     [rsp+120h+var_E0], 3
0x18009262c  mov     qword ptr [rbp+20h+var_60], rdi
0x180092630  mov     qword ptr [rbp+20h+var_60+8], 0
0x180092638  mov     [rbp+20h+var_50], 1
0x18009263c  lea     rax, [rbp+20h+var_40]
0x180092640  mov     [rsp+120h+var_F8], rax
0x180092645  lea     rax, [rbp+20h+var_30]
0x180092649  mov     qword ptr [rsp+120h+var_100], rax
0x18009264e  xor     r9d, r9d
0x180092651  xor     r8d, r8d
0x180092654  mov     edx, 1F0003h
0x180092659  lea     rcx, [rbp+20h+var_60+8]
0x18009265d  mov     rax, rbx
0x180092660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092665  mov     esi, eax
0x180092667  shr     esi, 1Fh
0x18009266a  cmp     [rbp+20h+var_50], 0
0x18009266e  jz      short loc_18009267D
0x180092670  mov     rdx, qword ptr [rbp+20h+var_60+8]
0x180092674  mov     rcx, qword ptr [rbp+20h+var_60]
0x180092678  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18009267d  test    sil, sil
0x180092680  jz      loc_180092762
0x180092686  mov     qword ptr [rbp+20h+var_60], rdi
0x18009268a  mov     qword ptr [rbp+20h+var_60+8], 0
0x180092692  mov     [rbp+20h+var_50], 1
0x180092696  lea     rax, [rbp+20h+var_40]
0x18009269a  mov     [rsp+120h+var_F8], rax
0x18009269f  lea     rax, [rbp+20h+var_30]
0x1800926a3  mov     qword ptr [rsp+120h+var_100], rax
0x1800926a8  xor     r9d, r9d
0x1800926ab  xor     r8d, r8d
0x1800926ae  mov     edx, 1F0003h
0x1800926b3  lea     rcx, [rbp+20h+var_60+8]
0x1800926b7  mov     rax, rbx
0x1800926ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800926bf  mov     ecx, eax; Status
0x1800926c1  call    cs:__imp_RtlNtStatusToDosError
0x1800926c7  mov     ebx, eax
0x1800926c9  test    eax, eax
0x1800926cb  jle     short loc_1800926D6
0x1800926cd  movzx   ebx, ax
0x1800926d0  or      ebx, 80070000h
0x1800926d6  lea     rcx, [rbp+20h+var_60]
0x1800926da  call    ??1?$out_param_t@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAA@XZ
0x1800926df  lea     rcx, aCallbacknotifi_0; ".\\callbacknotifier.cpp"
0x1800926e6  mov     qword ptr [rbp+20h+var_60], rcx
0x1800926ea  mov     dword ptr [rbp+20h+var_60+8], 52h ; 'R'
0x1800926f1  mov     [rsp+120h+var_DC], ebx
0x1800926f5  call    cs:__imp_GetCurrentThreadId
0x1800926fb  mov     eax, eax
0x1800926fd  mov     [rsp+120h+var_D8], rax
0x180092702  lea     rax, [rsp+120h+var_D8]
0x180092707  mov     [rsp+120h+var_F8], rax
0x18009270c  lea     rax, [rbp+20h+var_60+8]
0x180092710  mov     qword ptr [rsp+120h+var_100], rax
0x180092715  lea     r9, [rbp+20h+var_60]
0x180092719  lea     r8, [rsp+120h+var_DC]
0x18009271e  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180092725  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18009272a  lea     rdx, [rbp+20h+var_60]
0x18009272e  lea     rcx, [rbp+20h+var_78]
0x180092732  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180092737  mov     r9, rax
0x18009273a  mov     ecx, ebx
0x18009273c  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180092741  mov     r8, rax
0x180092744  mov     edx, ebx
0x180092746  lea     rcx, [rsp+120h+pExceptionObject]
0x18009274b  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180092750  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180092757  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18009275c  call    _CxxThrowException_0
0x180092762  lea     rcx, [rsp+120h+var_C8]
0x180092767  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18009276c  mov     rax, rdi
0x18009276f  mov     rcx, [rbp+20h+var_20]
0x180092773  xor     rcx, rsp; StackCookie
0x180092776  call    __security_check_cookie
0x18009277b  mov     rbx, [rsp+120h+arg_0]
0x180092783  add     rsp, 110h
0x18009278a  pop     rdi
0x18009278b  pop     rsi
0x18009278c  pop     rbp
0x18009278d  retn
```
