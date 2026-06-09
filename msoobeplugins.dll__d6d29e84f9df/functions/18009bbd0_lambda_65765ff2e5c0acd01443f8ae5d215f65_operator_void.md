# _lambda_65765ff2e5c0acd01443f8ae5d215f65_::operator()(void)

- ea: `0x18009bbd0`
- end: `0x18009bcc0`
- name: `??R_lambda_65765ff2e5c0acd01443f8ae5d215f65_@@QEBA@XZ`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18009bfb0`

## callees

- `0x1800230b0`
- `0x180059030`
- `0x180093630`
- `0x180093a00`
- `0x18009aba4`
- `0x18009bbd0`
- `0x18009ca20`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009bc20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009bc20`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18009bc3e`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18009bc3e`

## string_xrefs

- `0x18009bc71`: `shell\oobe\machine\plugins\adapters\winrt\oobezdp.cpp`
- `0x18009bc9f`: `shell\oobe\machine\plugins\adapters\winrt\oobezdp.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall _lambda_65765ff2e5c0acd01443f8ae5d215f65_::operator()(_QWORD *a1)
{
  __int64 *v2; // rax
  __int64 v3; // rbx
  DWORD CurrentThreadId; // eax
  int v5; // edi
  int v6; // eax
  int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v9; // [rsp+40h] [rbp+8h] BYREF
  __int64 v10; // [rsp+48h] [rbp+10h] BYREF

  wil::com_ptr_t<CloudExperienceHostAPI::OobeRegionManagerStatics,wil::err_exception_policy>::com_ptr_t<CloudExperienceHostAPI::OobeRegionManagerStatics,wil::err_exception_policy>(
    &v10,
    *a1);
  v2 = Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c14477f473232fc8d3b94379a337ce37_>,_lambda_c14477f473232fc8d3b94379a337ce37_>(
         &v9,
         &v10);
  v3 = *v2;
  *v2 = 0;
  if ( v9 )
  {
    v9 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IConciergeSettingProvider>::Release();
  }
  CurrentThreadId = GetCurrentThreadId();
  v5 = SHTaskPoolQueueTask(0, 0, CurrentThreadId, 0);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  wil::com_ptr_t<CloudExperienceHostAPI::OobeZdpManagerStatics,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::OobeZdpManagerStatics,wil::err_exception_policy>(&v10);
  if ( v5 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobezdp.cpp",
      (const char *)(unsigned int)v5,
      v3);
    v6 = CloudExperienceHostAPI::OobeZdpManagerStatics::StatusChanged(*a1 + 56LL, 4);
    if ( v6 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x43,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobezdp.cpp",
        (const char *)(unsigned int)v6,
        v7);
  }
}

```

## disassembly

```asm
0x18009bbd0  mov     [rsp+arg_10], rbx
0x18009bbd5  mov     [rsp+arg_18], rsi
0x18009bbda  push    rdi
0x18009bbdb  sub     rsp, 30h
0x18009bbdf  mov     rsi, rcx
0x18009bbe2  mov     rdx, [rcx]
0x18009bbe5  lea     rcx, [rsp+38h+arg_8]
0x18009bbea  call    ??0?$com_ptr_t@VOobeRegionManagerStatics@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVOobeRegionManagerStatics@CloudExperienceHostAPI@@@Z; wil::com_ptr_t<CloudExperienceHostAPI::OobeRegionManagerStatics,wil::err_exception_policy>::com_ptr_t<CloudExperienceHostAPI::OobeRegionManagerStatics,wil::err_exception_policy>(CloudExperienceHostAPI::OobeRegionManagerStatics *)
0x18009bbef  lea     rdx, [rsp+38h+arg_8]
0x18009bbf4  lea     rcx, [rsp+38h+arg_0]
0x18009bbf9  call    ??$Make@V?$CTaskWrapper@V_lambda_c14477f473232fc8d3b94379a337ce37_@@@ComTaskPool@Internal@Windows@@V_lambda_c14477f473232fc8d3b94379a337ce37_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_c14477f473232fc8d3b94379a337ce37_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_c14477f473232fc8d3b94379a337ce37_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c14477f473232fc8d3b94379a337ce37_>,_lambda_c14477f473232fc8d3b94379a337ce37_>(_lambda_c14477f473232fc8d3b94379a337ce37_ &&)
0x18009bbfe  mov     rbx, [rax]
0x18009bc01  mov     qword ptr [rax], 0
0x18009bc08  mov     rcx, [rsp+38h+arg_0]
0x18009bc0d  test    rcx, rcx
0x18009bc10  jz      short loc_18009BC20
0x18009bc12  mov     [rsp+38h+arg_0], 0
0x18009bc1b  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIConciergeSettingProvider@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IConciergeSettingProvider>::Release(void)
0x18009bc20  call    cs:__imp_GetCurrentThreadId
0x18009bc26  mov     [rsp+38h+var_10], 0
0x18009bc2f  mov     qword ptr [rsp+38h+var_18], rbx; int
0x18009bc34  xor     r9d, r9d
0x18009bc37  mov     r8d, eax
0x18009bc3a  xor     edx, edx
0x18009bc3c  xor     ecx, ecx
0x18009bc3e  call    cs:__imp_SHTaskPoolQueueTask
0x18009bc44  mov     edi, eax
0x18009bc46  test    rbx, rbx
0x18009bc49  jz      short loc_18009BC5B
0x18009bc4b  mov     rdx, [rbx]
0x18009bc4e  mov     rcx, rbx
0x18009bc51  mov     rax, [rdx+10h]
0x18009bc55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bc5a  nop
0x18009bc5b  lea     rcx, [rsp+38h+arg_8]
0x18009bc60  call    ??1?$com_ptr_t@VOobeZdpManagerStatics@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::OobeZdpManagerStatics,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::OobeZdpManagerStatics,wil::err_exception_policy>(void)
0x18009bc65  test    edi, edi
0x18009bc67  jns     short loc_18009BCB0
0x18009bc69  mov     rcx, [rsp+38h]; this
0x18009bc6e  mov     r9d, edi; char *
0x18009bc71  lea     r8, aShellOobeMachi_11; "shell\\oobe\\machine\\plugins\\adapters"...
0x18009bc78  mov     edx, 41h ; 'A'; void *
0x18009bc7d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009bc82  mov     rcx, [rsi]
0x18009bc85  add     rcx, 38h ; '8'
0x18009bc89  mov     edx, 4
0x18009bc8e  call    ?StatusChanged@OobeZdpManagerStatics@CloudExperienceHostAPI@@UEAAJW4OobeZdpStatus@2@@Z; CloudExperienceHostAPI::OobeZdpManagerStatics::StatusChanged(CloudExperienceHostAPI::OobeZdpStatus)
0x18009bc93  test    eax, eax
0x18009bc95  jns     short loc_18009BCB0
0x18009bc97  mov     rcx, [rsp+38h]; this
0x18009bc9c  mov     r9d, eax; char *
0x18009bc9f  lea     r8, aShellOobeMachi_11; "shell\\oobe\\machine\\plugins\\adapters"...
0x18009bca6  mov     edx, 43h ; 'C'; void *
0x18009bcab  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009bcb0  mov     rbx, [rsp+38h+arg_10]
0x18009bcb5  mov     rsi, [rsp+38h+arg_18]
0x18009bcba  add     rsp, 30h
0x18009bcbe  pop     rdi
0x18009bcbf  retn
```
