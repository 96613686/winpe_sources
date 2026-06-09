# ThreadProcHelper::ThreadProc(void *)

- ea: `0x1800119f0`
- end: `0x180011c10`
- name: `?ThreadProc@ThreadProcHelper@@CAKPEAX@Z`
- size: `544`
- prototype: `__int64 __fastcall(_DWORD *Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180007b14`
- `0x1800081e4`
- `0x1800119f0`
- `0x18001222c`
- `0x180013170`
- `0x180042b4c`
- `0x180042e3c`
- `0x18004370c`
- `0x180043738`
- `0x180045010`

## import_xrefs

- `ole32!CoUninitialize` at `0x180011be7`
- `ole32!CoUninitialize` at `0x180011be7`
- `ole32!CoInitializeEx` at `0x180011a01`
- `ole32!CoInitializeEx` at `0x180011a01`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180011ba4`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180011ba4`

## string_xrefs

- `0x180011aad`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\threadprochelper.cpp`
- `0x180011b58`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\threadprochelper.cpp`

## pseudocode

```c
__int64 __fastcall ThreadProcHelper::ThreadProc(_DWORD *Parameter)
{
  HRESULT v2; // eax
  void *v3; // rdx
  unsigned int v4; // r8d
  const char *v5; // r9
  __int64 v6; // rcx
  int v7; // eax
  unsigned int v8; // ebx
  _DWORD *v9; // rax
  __int64 v10; // rcx
  int v11; // eax
  _DWORD *v13; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v14[4]; // [rsp+28h] [rbp-30h] BYREF
  char v15; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+10h]
  int v17; // [rsp+70h] [rbp+18h] BYREF
  _DWORD *v18; // [rsp+78h] [rbp+20h] BYREF
  __int64 v19; // [rsp+80h] [rbp+28h] BYREF
  __int64 v20; // [rsp+88h] [rbp+30h] BYREF

  v2 = CoInitializeEx(0, 0);
  if ( v2 < 0 )
    wil::details::in1diag3::_FailFast_Hr(retaddr, v3, v4, (const char *)(unsigned int)v2, (int)v13);
  v17 = 0;
  v20 = 0;
  v19 = 0;
  v18 = Parameter;
  if ( Parameter )
  {
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)Parameter + 8LL))(Parameter);
    Parameter = v18;
  }
  if ( !Parameter )
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, v3, v4, v5);
  v6 = v20;
  v14[0] = &v17;
  v14[1] = &v18;
  v14[2] = &v19;
  v14[3] = &v20;
  v13 = Parameter;
  v20 = 0;
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = Microsoft::WRL::Details::MakeAndInitialize<AudioStateMonitorHelper,IAudioStateMonitorHelper,ThreadProcHelper *>(
         &v20,
         &v13);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v9 = v18;
    if ( v18[23] == 1 )
    {
      v10 = v19;
      v13 = v18;
      v19 = 0;
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      v11 = Microsoft::WRL::Details::MakeAndInitialize<CapabilityAccessHelper,ICapabilityAccessHelper,ThreadProcHelper *>(
              &v19,
              &v13);
      v8 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x115,
          (int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\threadprochelper.cpp",
          (const char *)(unsigned int)v11);
        v15 = 0;
        lambda_20b5af4dffa3f4a3de54ec131ae09372_::operator()(v14);
        wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>((__int64 *)&v18);
        wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(&v19);
        wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(&v20);
        goto LABEL_21;
      }
      v9 = v18;
    }
    v9[3] = 1;
    WakeByAddressAll(v9 + 3);
    wil::slim_event_t<0>::wait(v18 + 4);
    v15 = 0;
    lambda_20b5af4dffa3f4a3de54ec131ae09372_::operator()(v14);
    wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>((__int64 *)&v18);
    wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(&v19);
    wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(&v20);
    v8 = 0;
    goto LABEL_21;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x110,
    (int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\threadprochelper.cpp",
    (const char *)(unsigned int)v7);
  v15 = 0;
  lambda_20b5af4dffa3f4a3de54ec131ae09372_::operator()(v14);
  if ( v18 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v18 + 16LL))(v18);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
LABEL_21:
  CoUninitialize();
  return v8;
}

```

## disassembly

```asm
0x1800119f0  push    rbp
0x1800119f2  push    rbx
0x1800119f3  mov     rbp, rsp
0x1800119f6  sub     rsp, 58h
0x1800119fa  mov     rbx, rcx
0x1800119fd  xor     edx, edx; dwCoInit
0x1800119ff  xor     ecx, ecx; pvReserved
0x180011a01  call    cs:__imp_CoInitializeEx
0x180011a08  nop     dword ptr [rax+rax+00h]
0x180011a0d  test    eax, eax
0x180011a0f  js      loc_180011C03
0x180011a15  mov     [rbp+arg_0], 0
0x180011a1c  mov     [rbp+arg_18], 0
0x180011a24  mov     [rbp+arg_10], 0
0x180011a2c  mov     [rbp+arg_8], rbx
0x180011a30  test    rbx, rbx
0x180011a33  jz      short loc_180011A48
0x180011a35  mov     rax, [rbx]
0x180011a38  mov     rcx, rbx
0x180011a3b  mov     rax, [rax+8]
0x180011a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a44  mov     rbx, [rbp+arg_8]
0x180011a48  mov     rcx, [rbp+10h]; this
0x180011a4c  test    rbx, rbx
0x180011a4f  jz      loc_180011BFD
0x180011a55  mov     rcx, [rbp+arg_18]
0x180011a59  lea     rax, [rbp+arg_0]
0x180011a5d  mov     [rbp+var_30], rax
0x180011a61  lea     rax, [rbp+arg_8]
0x180011a65  mov     [rbp+var_28], rax
0x180011a69  lea     rax, [rbp+arg_10]
0x180011a6d  mov     [rbp+var_20], rax
0x180011a71  lea     rax, [rbp+arg_18]
0x180011a75  mov     [rbp+var_18], rax
0x180011a79  mov     [rbp+var_38], rbx
0x180011a7d  mov     [rbp+arg_18], 0
0x180011a85  test    rcx, rcx
0x180011a88  jz      short loc_180011A96
0x180011a8a  mov     rax, [rcx]
0x180011a8d  mov     rax, [rax+10h]
0x180011a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a96  lea     rdx, [rbp+var_38]
0x180011a9a  lea     rcx, [rbp+arg_18]
0x180011a9e  call    ??$MakeAndInitialize@VAudioStateMonitorHelper@@UIAudioStateMonitorHelper@@PEAVThreadProcHelper@@@Details@WRL@Microsoft@@YAJPEAPEAUIAudioStateMonitorHelper@@$$QEAPEAVThreadProcHelper@@@Z; Microsoft::WRL::Details::MakeAndInitialize<AudioStateMonitorHelper,IAudioStateMonitorHelper,ThreadProcHelper *>(IAudioStateMonitorHelper * *,ThreadProcHelper * &&)
0x180011aa3  mov     ebx, eax
0x180011aa5  test    eax, eax
0x180011aa7  jns     short loc_180011B16
0x180011aa9  mov     rcx, [rbp+10h]; this
0x180011aad  lea     r8, aMultimediaDsho_3; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x180011ab4  mov     r9d, eax; char *
0x180011ab7  mov     edx, 110h; void *
0x180011abc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011ac1  lea     rcx, [rbp+var_30]
0x180011ac5  mov     [rbp+var_10], 0
0x180011ac9  call    _lambda_20b5af4dffa3f4a3de54ec131ae09372___operator__
0x180011ace  mov     rcx, [rbp+arg_8]
0x180011ad2  test    rcx, rcx
0x180011ad5  jz      short loc_180011AE3
0x180011ad7  mov     rax, [rcx]
0x180011ada  mov     rax, [rax+10h]
0x180011ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ae3  mov     rcx, [rbp+arg_10]
0x180011ae7  test    rcx, rcx
0x180011aea  jz      short loc_180011AF8
0x180011aec  mov     rax, [rcx]
0x180011aef  mov     rax, [rax+10h]
0x180011af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011af8  mov     rcx, [rbp+arg_18]
0x180011afc  test    rcx, rcx
0x180011aff  jz      loc_180011BE7
0x180011b05  mov     rax, [rcx]
0x180011b08  mov     rax, [rax+10h]
0x180011b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b11  jmp     loc_180011BE7
0x180011b16  mov     rax, [rbp+arg_8]
0x180011b1a  cmp     dword ptr [rax+5Ch], 1
0x180011b1e  jnz     short loc_180011B9A
0x180011b20  mov     rcx, [rbp+arg_10]
0x180011b24  mov     [rbp+var_38], rax
0x180011b28  mov     [rbp+arg_10], 0
0x180011b30  test    rcx, rcx
0x180011b33  jz      short loc_180011B41
0x180011b35  mov     rax, [rcx]
0x180011b38  mov     rax, [rax+10h]
0x180011b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b41  lea     rdx, [rbp+var_38]
0x180011b45  lea     rcx, [rbp+arg_10]
0x180011b49  call    ??$MakeAndInitialize@VCapabilityAccessHelper@@UICapabilityAccessHelper@@PEAVThreadProcHelper@@@Details@WRL@Microsoft@@YAJPEAPEAUICapabilityAccessHelper@@$$QEAPEAVThreadProcHelper@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CapabilityAccessHelper,ICapabilityAccessHelper,ThreadProcHelper *>(ICapabilityAccessHelper * *,ThreadProcHelper * &&)
0x180011b4e  mov     ebx, eax
0x180011b50  test    eax, eax
0x180011b52  jns     short loc_180011B96
0x180011b54  mov     rcx, [rbp+10h]; this
0x180011b58  lea     r8, aMultimediaDsho_3; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x180011b5f  mov     r9d, eax; char *
0x180011b62  mov     edx, 115h; void *
0x180011b67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011b6c  lea     rcx, [rbp+var_30]
0x180011b70  mov     [rbp+var_10], 0
0x180011b74  call    _lambda_20b5af4dffa3f4a3de54ec131ae09372___operator__
0x180011b79  lea     rcx, [rbp+arg_8]
0x180011b7d  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x180011b82  lea     rcx, [rbp+arg_10]
0x180011b86  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x180011b8b  lea     rcx, [rbp+arg_18]
0x180011b8f  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x180011b94  jmp     short loc_180011BE7
0x180011b96  mov     rax, [rbp+arg_8]
0x180011b9a  lea     rcx, [rax+0Ch]; Address
0x180011b9e  mov     dword ptr [rcx], 1
0x180011ba4  call    cs:__imp_WakeByAddressAll
0x180011bab  nop     dword ptr [rax+rax+00h]
0x180011bb0  mov     rcx, [rbp+arg_8]
0x180011bb4  add     rcx, 10h
0x180011bb8  call    ?wait@?$slim_event_t@$0A@@wil@@QEAA_NXZ; wil::slim_event_t<0>::wait(void)
0x180011bbd  lea     rcx, [rbp+var_30]
0x180011bc1  mov     [rbp+var_10], 0
0x180011bc5  call    _lambda_20b5af4dffa3f4a3de54ec131ae09372___operator__
0x180011bca  lea     rcx, [rbp+arg_8]
0x180011bce  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x180011bd3  lea     rcx, [rbp+arg_10]
0x180011bd7  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x180011bdc  lea     rcx, [rbp+arg_18]
0x180011be0  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x180011be5  xor     ebx, ebx
0x180011be7  call    cs:__imp_CoUninitialize
0x180011bee  nop     dword ptr [rax+rax+00h]
0x180011bf3  mov     eax, ebx
0x180011bf5  add     rsp, 58h
0x180011bf9  pop     rbx
0x180011bfa  pop     rbp
0x180011bfb  retn
0x180011bfd  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180011c03  mov     rcx, [rbp+10h]; this
0x180011c07  mov     r9d, eax; char *
0x180011c0a  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
