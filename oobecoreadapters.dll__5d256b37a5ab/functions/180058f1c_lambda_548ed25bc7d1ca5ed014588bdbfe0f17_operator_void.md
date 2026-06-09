# _lambda_548ed25bc7d1ca5ed014588bdbfe0f17_::operator()(void)

- ea: `0x180058f1c`
- end: `0x18005900c`
- name: `??R_lambda_548ed25bc7d1ca5ed014588bdbfe0f17_@@QEBA@XZ`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800592e0`

## callees

- `0x18000aa20`
- `0x18000b098`
- `0x18004a858`
- `0x180057bbc`
- `0x180058764`
- `0x180058f1c`
- `0x18005a570`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180058f6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180058f6c`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180058f8a`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180058f8a`

## string_xrefs

- `0x180058fbd`: `shellcommon\shell\oobe\core\components\winrt\oobezdpcore.cpp`
- `0x180058feb`: `shellcommon\shell\oobe\core\components\winrt\oobezdpcore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall _lambda_548ed25bc7d1ca5ed014588bdbfe0f17_::operator()(_QWORD *a1)
{
  __int64 *v2; // rax
  __int64 v3; // rbx
  DWORD CurrentThreadId; // eax
  int v5; // edi
  int v6; // eax
  int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v9; // [rsp+40h] [rbp+8h] BYREF
  char v10; // [rsp+48h] [rbp+10h] BYREF

  wil::com_ptr_t<CloudExperienceHostAPI::OobeZdpManagerStaticsCore,wil::err_exception_policy>::com_ptr_t<CloudExperienceHostAPI::OobeZdpManagerStaticsCore,wil::err_exception_policy>(
    &v10,
    *a1);
  v2 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_9a320120607a3e35ae13c2c3682bd6a6_>,_lambda_9a320120607a3e35ae13c2c3682bd6a6_>(
                    &v9,
                    &v10);
  v3 = *v2;
  *v2 = 0;
  if ( v9 )
  {
    v9 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  CurrentThreadId = GetCurrentThreadId();
  v5 = SHTaskPoolQueueTask(0, 0, CurrentThreadId, 0);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  wil::com_ptr_t<CloudExperienceHostAPI::OobeRegionManagerStaticsCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::OobeRegionManagerStaticsCore,wil::err_exception_policy>(&v10);
  if ( v5 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobezdpcore.cpp",
      (const char *)(unsigned int)v5,
      v3);
    v6 = CloudExperienceHostAPI::OobeZdpManagerStaticsCore::StatusChanged(*a1 + 56LL, 4);
    if ( v6 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x45,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobezdpcore.cpp",
        (const char *)(unsigned int)v6,
        v7);
  }
}

```

## disassembly

```asm
0x180058f1c  mov     [rsp+arg_10], rbx
0x180058f21  mov     [rsp+arg_18], rsi
0x180058f26  push    rdi
0x180058f27  sub     rsp, 30h
0x180058f2b  mov     rsi, rcx
0x180058f2e  mov     rdx, [rcx]
0x180058f31  lea     rcx, [rsp+38h+arg_8]
0x180058f36  call    ??0?$com_ptr_t@VOobeZdpManagerStaticsCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVOobeZdpManagerStaticsCore@CloudExperienceHostAPI@@@Z; wil::com_ptr_t<CloudExperienceHostAPI::OobeZdpManagerStaticsCore,wil::err_exception_policy>::com_ptr_t<CloudExperienceHostAPI::OobeZdpManagerStaticsCore,wil::err_exception_policy>(CloudExperienceHostAPI::OobeZdpManagerStaticsCore *)
0x180058f3b  lea     rdx, [rsp+38h+arg_8]
0x180058f40  lea     rcx, [rsp+38h+arg_0]
0x180058f45  call    ??$Make@V?$CTaskWrapper@V_lambda_9a320120607a3e35ae13c2c3682bd6a6_@@@ComTaskPool@Internal@Windows@@V_lambda_9a320120607a3e35ae13c2c3682bd6a6_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_9a320120607a3e35ae13c2c3682bd6a6_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_9a320120607a3e35ae13c2c3682bd6a6_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_9a320120607a3e35ae13c2c3682bd6a6_>,_lambda_9a320120607a3e35ae13c2c3682bd6a6_>(_lambda_9a320120607a3e35ae13c2c3682bd6a6_ &&)
0x180058f4a  mov     rbx, [rax]
0x180058f4d  mov     qword ptr [rax], 0
0x180058f54  mov     rcx, [rsp+38h+arg_0]
0x180058f59  test    rcx, rcx
0x180058f5c  jz      short loc_180058F6C
0x180058f5e  mov     [rsp+38h+arg_0], 0
0x180058f67  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180058f6c  call    cs:__imp_GetCurrentThreadId
0x180058f72  mov     [rsp+38h+var_10], 0
0x180058f7b  mov     qword ptr [rsp+38h+var_18], rbx; int
0x180058f80  xor     r9d, r9d
0x180058f83  mov     r8d, eax
0x180058f86  xor     edx, edx
0x180058f88  xor     ecx, ecx
0x180058f8a  call    cs:__imp_SHTaskPoolQueueTask
0x180058f90  mov     edi, eax
0x180058f92  test    rbx, rbx
0x180058f95  jz      short loc_180058FA7
0x180058f97  mov     rdx, [rbx]
0x180058f9a  mov     rcx, rbx
0x180058f9d  mov     rax, [rdx+10h]
0x180058fa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058fa6  nop
0x180058fa7  lea     rcx, [rsp+38h+arg_8]
0x180058fac  call    ??1?$com_ptr_t@VOobeRegionManagerStaticsCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::OobeRegionManagerStaticsCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::OobeRegionManagerStaticsCore,wil::err_exception_policy>(void)
0x180058fb1  test    edi, edi
0x180058fb3  jns     short loc_180058FFC
0x180058fb5  mov     rcx, [rsp+38h]; this
0x180058fba  mov     r9d, edi; char *
0x180058fbd  lea     r8, aShellcommonShe_23; "shellcommon\\shell\\oobe\\core\\compone"...
0x180058fc4  mov     edx, 43h ; 'C'; void *
0x180058fc9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180058fce  mov     rcx, [rsi]
0x180058fd1  add     rcx, 38h ; '8'
0x180058fd5  mov     edx, 4
0x180058fda  call    ?StatusChanged@OobeZdpManagerStaticsCore@CloudExperienceHostAPI@@UEAAJW4OobeZdpStatus@2@@Z; CloudExperienceHostAPI::OobeZdpManagerStaticsCore::StatusChanged(CloudExperienceHostAPI::OobeZdpStatus)
0x180058fdf  test    eax, eax
0x180058fe1  jns     short loc_180058FFC
0x180058fe3  mov     rcx, [rsp+38h]; this
0x180058fe8  mov     r9d, eax; char *
0x180058feb  lea     r8, aShellcommonShe_23; "shellcommon\\shell\\oobe\\core\\compone"...
0x180058ff2  mov     edx, 45h ; 'E'; void *
0x180058ff7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180058ffc  mov     rbx, [rsp+38h+arg_10]
0x180059001  mov     rsi, [rsp+38h+arg_18]
0x180059006  add     rsp, 30h
0x18005900a  pop     rdi
0x18005900b  retn
```
