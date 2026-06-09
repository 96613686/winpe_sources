# Microsoft::WRL::Details::MakeAndInitialize<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *>(Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *>(Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,>(`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *>(Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate * *)

- ea: `0x180104edc`
- end: `0x18010501f`
- name: `??$MakeAndInitialize@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperationWithProgress@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@V1?1???$WaitForCompletion@PEAU?$IAsyncOperationWithProgress@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@Foundation@Windows@@@23@YAJ01K2@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperationWithProgress@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Z`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180105180`

## callees

- `0x180019068`
- `0x1800ea608`
- `0x1800ead14`
- `0x1800ece5c`
- `0x1800f12c0`
- `0x180104edc`
- `0x180107448`
- `0x180107a94`
- `0x180191010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180104f96`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180104f96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180104fa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180104fa4`

## string_xrefs

- `0x180105002`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ___MakeAndInitialize_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperationWithProgress_PEAUIDiagnosticAnalysisResult_Core_Autopilot_ModernDeployment__UDiagnosticAnalysisProgress_234__Foundation_Windows___details_wil__YAJPEAU__IAsyncOperationWithProgress_PEAUIDiagnosticAnalysisResult_Core_Autopilot_ModernDeployment__UDiagnosticAnalysisProgress_234__Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z_V1_1____WaitForCompletion_PEAU__IAsyncOperationWithProgress_PEAUIDiagnosticAnalysisResult_Core_Autopilot_ModernDeployment__UDiagnosticAnalysisProgress_234__Foundation_Windows___23_YAJ01K2_Z___V_Details_WRL_Microsoft__YAJPEAPEAVCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperationWithProgress_PEAUIDiagnosticAnalysisResult_Core_Autopilot_ModernDeployment__UDiagnosticAnalysisProgress_234__Foundation_Windows___details_wil__YAJPEAU__IAsyncOperationWithProgress_PEAUIDiagnosticAnalysisResult_Core_Autopilot_ModernDeployment__UDiagnosticAnalysisProgress_234__Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__Z(
        _QWORD *a1)
{
  _DWORD *v2; // rax
  _DWORD *v3; // rbx
  unsigned int v4; // edi
  wil::details *v5; // rcx
  HANDLE Event; // rbp
  int LastErrorFailHr; // eax
  int v9; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  _DWORD *v11; // [rsp+40h] [rbp+8h] BYREF
  void *v12; // [rsp+48h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  v3 = v2;
  v12 = v2;
  if ( v2 )
  {
    Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::FtmBase>(v2);
    v3[11] = 1;
    *(_QWORD *)v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress>'};
    *((_QWORD *)v3 + 1) = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *>'::`2'::CompletionDelegate::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v3 = &`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *>'::`2'::CompletionDelegate::`vftable';
    *((_QWORD *)v3 + 1) = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *>'::`2'::CompletionDelegate::`vftable';
    v3[12] = 0;
    *((_QWORD *)v3 + 7) = 0;
    v11 = v3;
    v12 = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    if ( Event )
    {
      GetLastError();
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        v3 + 14,
        Event);
    }
    else
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
      v4 = LastErrorFailHr;
      if ( LastErrorFailHr < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x62B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
          (const char *)(unsigned int)LastErrorFailHr,
          v9);
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v11);
        goto LABEL_8;
      }
    }
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v3 + 8LL))(v3);
    *a1 = v3;
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v11);
    v4 = 0;
  }
  else
  {
    v4 = -2147024882;
  }
LABEL_8:
  Microsoft::WRL::Details::MakeAllocator<CMockEngine>::~MakeAllocator<CMockEngine>(&v12);
  return v4;
}

```

## disassembly

```asm
0x180104edc  mov     [rsp+arg_10], rbx
0x180104ee1  push    rbp
0x180104ee2  push    rsi
0x180104ee3  push    rdi; int
0x180104ee4  sub     rsp, 20h
0x180104ee8  mov     rsi, rcx
0x180104eeb  mov     qword ptr [rcx], 0
0x180104ef2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180104ef9  mov     ecx, 40h ; '@'; unsigned __int64
0x180104efe  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180104f03  mov     rbx, rax
0x180104f06  mov     [rsp+38h+arg_8], rax
0x180104f0b  test    rax, rax
0x180104f0e  jnz     short loc_180104F1A
0x180104f10  mov     edi, 8007000Eh
0x180104f15  jmp     loc_180104FD6
0x180104f1a  mov     rcx, rbx
0x180104f1d  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::FtmBase>(void)
0x180104f22  mov     dword ptr [rbx+2Ch], 1
0x180104f29  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationWithProgressCompletedHandler@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress>'}
0x180104f30  mov     [rbx], rax
0x180104f33  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperationWithProgress@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *>(Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180104f3a  mov     [rbx+8], rax
0x180104f3e  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180104f45  test    rcx, rcx
0x180104f48  jz      short loc_180104F57
0x180104f4a  mov     rax, [rcx]
0x180104f4d  mov     rax, [rax+8]
0x180104f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180104f56  nop
0x180104f57  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperationWithProgress@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationWithProgressCompletedHandler@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *>(Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress>'}
0x180104f5e  mov     [rbx], rax
0x180104f61  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperationWithProgress@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *>(Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180104f68  mov     [rbx+8], rax
0x180104f6c  mov     dword ptr [rbx+30h], 0
0x180104f73  mov     qword ptr [rbx+38h], 0
0x180104f7b  mov     [rsp+38h+arg_0], rbx
0x180104f80  mov     [rsp+38h+arg_8], 0
0x180104f89  mov     r9d, 1F0003h; dwDesiredAccess
0x180104f8f  xor     r8d, r8d; dwFlags
0x180104f92  xor     edx, edx; lpName
0x180104f94  xor     ecx, ecx; lpEventAttributes
0x180104f96  call    cs:__imp_CreateEventExW
0x180104f9c  mov     rbp, rax
0x180104f9f  test    rax, rax
0x180104fa2  jz      short loc_180104FEF
0x180104fa4  call    cs:__imp_GetLastError
0x180104faa  mov     rdx, rbp
0x180104fad  lea     rcx, [rbx+38h]
0x180104fb1  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180104fb6  nop
0x180104fb7  mov     rax, [rbx]
0x180104fba  mov     rcx, rbx
0x180104fbd  mov     rax, [rax+8]
0x180104fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180104fc6  nop
0x180104fc7  mov     [rsi], rbx
0x180104fca  lea     rcx, [rsp+38h+arg_0]
0x180104fcf  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180104fd4  xor     edi, edi
0x180104fd6  lea     rcx, [rsp+38h+arg_8]
0x180104fdb  call    ??1?$MakeAllocator@VCMockEngine@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CMockEngine>::~MakeAllocator<CMockEngine>(void)
0x180104fe0  mov     eax, edi
0x180104fe2  mov     rbx, [rsp+38h+arg_10]
0x180104fe7  add     rsp, 20h
0x180104feb  pop     rdi
0x180104fec  pop     rsi
0x180104fed  pop     rbp
0x180104fee  retn
0x180104fef  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180104ff4  mov     edi, eax
0x180104ff6  test    eax, eax
0x180104ff8  jns     short loc_180104FB7
0x180104ffa  mov     rcx, [rsp+38h]; this
0x180104fff  mov     r9d, eax; char *
0x180105002  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180105009  mov     edx, 62Bh; void *
0x18010500e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180105013  lea     rcx, [rsp+38h+arg_0]
0x180105018  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18010501d  jmp     short loc_180104FD6
```
