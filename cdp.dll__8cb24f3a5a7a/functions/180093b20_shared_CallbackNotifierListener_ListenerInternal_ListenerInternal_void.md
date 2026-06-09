# shared::CallbackNotifierListener::ListenerInternal::ListenerInternal(void)

- ea: `0x180093b20`
- end: `0x180093d7f`
- name: `??0ListenerInternal@CallbackNotifierListener@shared@@QEAA@XZ`
- size: `607`
- prototype: `__int64 __fastcall(shared::CallbackNotifierListener::ListenerInternal *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x180093a54`

## callees

- `0x180013da0`
- `0x1800573e8`
- `0x180092854`
- `0x180092d84`
- `0x180093628`
- `0x180093b20`
- `0x180093d88`
- `0x180093e18`
- `0x180093e40`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x180143248`
- `0x1801fcb36`
- `0x18023a258`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180093cdf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180093cdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093ba8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093ba8`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180093b96`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180093b96`

## string_xrefs

- `0x180093d05`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
shared::CallbackNotifierListener::ListenerInternal *__fastcall shared::CallbackNotifierListener::ListenerInternal::ListenerInternal(
        shared::CallbackNotifierListener::ListenerInternal *this)
{
  _QWORD *v2; // rdi
  char *v3; // rsi
  void *v4; // rdx
  unsigned int v5; // r8d
  const char *v6; // r9
  HANDLE Event; // r14
  shared *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdx
  std::_Ref_count_base *v14; // rcx
  int v16; // ecx
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rax
  HLOCAL *SemaphoreInternal; // rax
  void *v22; // rdx
  const char *v23; // [rsp+30h] [rbp-49h] BYREF
  std::_Ref_count_base *v24; // [rsp+38h] [rbp-41h] BYREF
  __int64 v25; // [rsp+40h] [rbp-39h] BYREF
  std::_Ref_count_base *v26; // [rsp+48h] [rbp-31h]
  _BYTE v27[24]; // [rsp+50h] [rbp-29h] BYREF
  _BYTE pExceptionObject[104]; // [rsp+68h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  wil::details *v30; // [rsp+E8h] [rbp+6Fh] BYREF
  __int64 CurrentThreadId; // [rsp+F0h] [rbp+77h] BYREF

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *(_OWORD *)((char *)this + 40) = 0;
  *(_OWORD *)((char *)this + 56) = 0;
  *(_OWORD *)((char *)this + 72) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 22) = -1;
  *((_DWORD *)this + 4) = 2;
  *((_DWORD *)this + 23) = 0;
  v2 = (_QWORD *)((char *)this + 96);
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  v3 = (char *)this + 112;
  v30 = (shared::CallbackNotifierListener::ListenerInternal *)((char *)this + 112);
  *((_QWORD *)this + 14) = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v4, v5, v6);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    v3,
    Event);
  *(_OWORD *)((char *)this + 120) = 0;
  *(_OWORD *)((char *)this + 136) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 15;
  *((_BYTE *)this + 136) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_BYTE *)this + 200) = 0;
  *((_BYTE *)this + 201) = shared::IsRunningInContainerOS(v8);
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 0;
  shared::SharedInstanceManager::GetInstanceThrowIfNull<shared::ISharedPALFactory>(&v25, v9, v10);
  shared::CallbackNotifierListener::ListenerInternal::GenerateTitle(this);
  if ( !*((_BYTE *)this + 201) && !*v2 )
  {
    SemaphoreInternal = shared::CallbackNotifierListener::ListenerInternal::CreateSemaphoreInternal(
                          (HLOCAL *)&v30,
                          (_QWORD *)this + 17);
    __4__unique_any_t_V__semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01___QEAV01__Z(
      v2,
      SemaphoreInternal);
    if ( v30 )
      wil::details::CloseHandle(v30, v22);
  }
  v11 = (__int64 *)(*(__int64 (__fastcall **)(__int64, const char **))(*(_QWORD *)v25 + 80LL))(v25, &v23);
  v12 = *v11;
  v13 = v11[1];
  *v11 = 0;
  v11[1] = 0;
  *((_QWORD *)this + 21) = v12;
  v14 = (std::_Ref_count_base *)*((_QWORD *)this + 22);
  *((_QWORD *)this + 22) = v13;
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  if ( v24 )
    std::_Ref_count_base::_Decref(v24);
  if ( !*((_QWORD *)this + 21) )
  {
    v23 = ".\\callbacknotifierlistener.cpp";
    LODWORD(v24) = 64;
    LODWORD(v30) = -2147418113;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v16,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v30,
      (unsigned int)&v23,
      (__int64)&v24,
      (__int64)&CurrentThreadId);
    v17 = cdp::ExceptionStackFromSourceLocationInfo(v27, &v23);
    v20 = cdp::ErrorCodeToString(2147549183LL, v18, v19, v17);
    ConnectedDevices::Exception::Exception(pExceptionObject, 2147549183LL, v20);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  if ( v26 )
    std::_Ref_count_base::_Decref(v26);
  return this;
}

```

## disassembly

```asm
0x180093b20  mov     [rsp-8+arg_18], rbx
0x180093b25  mov     [rsp-8+arg_0], rcx
0x180093b2a  push    rbp
0x180093b2b  push    rsi
0x180093b2c  push    rdi
0x180093b2d  push    r14
0x180093b2f  push    r15
0x180093b31  lea     rbp, [rsp-37h]
0x180093b36  sub     rsp, 0B0h
0x180093b3d  mov     rbx, rcx
0x180093b40  xor     r15d, r15d
0x180093b43  mov     [rcx], r15
0x180093b46  mov     [rcx+8], r15
0x180093b4a  xorps   xmm0, xmm0
0x180093b4d  movups  xmmword ptr [rcx+28h], xmm0
0x180093b51  movups  xmmword ptr [rcx+38h], xmm0
0x180093b55  movups  xmmword ptr [rcx+48h], xmm0
0x180093b59  mov     [rcx+18h], r15
0x180093b5d  mov     [rcx+20h], r15
0x180093b61  mov     dword ptr [rcx+58h], 0FFFFFFFFh
0x180093b68  mov     dword ptr [rcx+10h], 2
0x180093b6f  mov     [rcx+5Ch], r15d
0x180093b73  lea     rdi, [rcx+60h]
0x180093b77  mov     [rdi], r15
0x180093b7a  mov     [rcx+68h], r15
0x180093b7e  lea     rsi, [rcx+70h]
0x180093b82  mov     [rbp+57h+arg_8], rsi
0x180093b86  mov     [rsi], r15
0x180093b89  mov     r9d, 1F0003h; dwDesiredAccess
0x180093b8f  xor     r8d, r8d; dwFlags
0x180093b92  xor     edx, edx; lpName
0x180093b94  xor     ecx, ecx; lpEventAttributes
0x180093b96  call    cs:__imp_CreateEventExW
0x180093b9c  mov     r14, rax
0x180093b9f  test    rax, rax
0x180093ba2  jz      loc_180093D75
0x180093ba8  call    cs:__imp_GetLastError
0x180093bae  mov     rdx, r14
0x180093bb1  mov     rcx, rsi
0x180093bb4  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180093bb9  nop
0x180093bba  xorps   xmm0, xmm0
0x180093bbd  movups  xmmword ptr [rbx+78h], xmm0
0x180093bc1  lea     rsi, [rbx+88h]
0x180093bc8  xorps   xmm1, xmm1
0x180093bcb  movups  xmmword ptr [rsi], xmm1
0x180093bce  mov     [rsi+10h], r15
0x180093bd2  mov     qword ptr [rsi+18h], 0Fh
0x180093bda  mov     [rsi], r15b
0x180093bdd  mov     [rbx+0A8h], r15
0x180093be4  mov     [rbx+0B0h], r15
0x180093beb  mov     [rbx+0B8h], r15
0x180093bf2  mov     [rbx+0C0h], r15
0x180093bf9  mov     [rbx+0C8h], r15b
0x180093c00  call    ?IsRunningInContainerOS@shared@@YA_NXZ; shared::IsRunningInContainerOS(void)
0x180093c05  mov     [rbx+0C9h], al
0x180093c0b  mov     [rbx+0D0h], r15
0x180093c12  mov     [rbx+0D8h], r15
0x180093c19  mov     [rbx+0E0h], r15
0x180093c20  lea     rcx, [rbp+57h+var_90]
0x180093c24  call    ??$GetInstanceThrowIfNull@VISharedPALFactory@shared@@@SharedInstanceManager@shared@@SA?AV?$shared_ptr@VISharedPALFactory@shared@@@std@@H@Z; shared::SharedInstanceManager::GetInstanceThrowIfNull<shared::ISharedPALFactory>(int)
0x180093c29  nop
0x180093c2a  mov     rcx, rbx; this
0x180093c2d  call    ?GenerateTitle@ListenerInternal@CallbackNotifierListener@shared@@AEAAXXZ; shared::CallbackNotifierListener::ListenerInternal::GenerateTitle(void)
0x180093c32  cmp     [rbx+0C9h], r15b
0x180093c39  jnz     short loc_180093C44
0x180093c3b  cmp     [rdi], r15
0x180093c3e  jz      loc_180093D47
0x180093c44  mov     rcx, [rbp+57h+var_90]
0x180093c48  mov     rax, [rcx]
0x180093c4b  lea     rdx, [rbp+57h+var_A0]
0x180093c4f  mov     rax, [rax+50h]
0x180093c53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093c58  mov     rcx, [rax]
0x180093c5b  mov     rdx, [rax+8]
0x180093c5f  mov     [rax], r15
0x180093c62  mov     [rax+8], r15
0x180093c66  mov     [rbx+0A8h], rcx
0x180093c6d  mov     rcx, [rbx+0B0h]; this
0x180093c74  mov     [rbx+0B0h], rdx
0x180093c7b  test    rcx, rcx
0x180093c7e  jz      short loc_180093C85
0x180093c80  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180093c85  mov     rcx, [rbp+57h+var_98]; this
0x180093c89  test    rcx, rcx
0x180093c8c  jz      short loc_180093C93
0x180093c8e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180093c93  cmp     [rbx+0A8h], r15
0x180093c9a  jz      short loc_180093CC5
0x180093c9c  mov     rcx, [rbp+57h+var_88]; this
0x180093ca0  test    rcx, rcx
0x180093ca3  jz      short loc_180093CAB
0x180093ca5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180093caa  nop
0x180093cab  mov     rax, rbx
0x180093cae  mov     rbx, [rsp+0D0h+arg_18]
0x180093cb6  add     rsp, 0B0h
0x180093cbd  pop     r15
0x180093cbf  pop     r14
0x180093cc1  pop     rdi
0x180093cc2  pop     rsi
0x180093cc3  pop     rbp
0x180093cc4  retn
0x180093cc5  lea     rax, aCallbacknotifi; ".\\callbacknotifierlistener.cpp"
0x180093ccc  mov     [rbp+57h+var_A0], rax
0x180093cd0  mov     dword ptr [rbp+57h+var_98], 40h ; '@'
0x180093cd7  mov     ebx, 8000FFFFh
0x180093cdc  mov     dword ptr [rbp+57h+arg_8], ebx
0x180093cdf  call    cs:__imp_GetCurrentThreadId
0x180093ce5  mov     eax, eax
0x180093ce7  mov     [rbp+57h+arg_10], rax
0x180093ceb  lea     rax, [rbp+57h+arg_10]
0x180093cef  mov     [rsp+0D0h+var_A8], rax
0x180093cf4  lea     rax, [rbp+57h+var_98]
0x180093cf8  mov     [rsp+0D0h+var_B0], rax
0x180093cfd  lea     r9, [rbp+57h+var_A0]
0x180093d01  lea     r8, [rbp+57h+arg_8]
0x180093d05  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180093d0c  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180093d11  lea     rdx, [rbp+57h+var_A0]
0x180093d15  lea     rcx, [rbp+57h+var_80]
0x180093d19  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180093d1e  mov     r9, rax
0x180093d21  mov     ecx, ebx
0x180093d23  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180093d28  mov     r8, rax
0x180093d2b  mov     edx, ebx
0x180093d2d  lea     rcx, [rbp+57h+pExceptionObject]
0x180093d31  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180093d36  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180093d3d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180093d41  call    _CxxThrowException_0
0x180093d47  mov     rdx, rsi
0x180093d4a  lea     rcx, [rbp+57h+arg_8]
0x180093d4e  call    ?CreateSemaphoreInternal@ListenerInternal@CallbackNotifierListener@shared@@CA?AV?$unique_any_t@V?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z
0x180093d53  mov     rdx, rax
0x180093d56  mov     rcx, rdi
0x180093d59  call    ??4?$unique_any_t@V?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x180093d5e  mov     rcx, [rbp+57h+arg_8]; this
0x180093d62  test    rcx, rcx
0x180093d65  jz      loc_180093C44
0x180093d6b  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180093d70  jmp     loc_180093C44
0x180093d75  mov     rcx, [rbp+5Fh]; this
0x180093d79  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
