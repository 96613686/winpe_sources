# Microsoft::WRL::Details::MakeAndInitialize<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *>(Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *>(Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,>(`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *>(Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate * *)

- ea: `0x180106198`
- end: `0x1801062f4`
- name: `??$MakeAndInitialize@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperationWithProgress@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@V1?1???$WaitForCompletion@PEAU?$IAsyncOperationWithProgress@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@Foundation@Windows@@@23@YAJ01K2@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperationWithProgress@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Z`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180106464`

## callees

- `0x1800190e8`
- `0x1800eaa50`
- `0x1800eb1ac`
- `0x1800ed46c`
- `0x1800f1c18`
- `0x180106198`
- `0x180108b5c`
- `0x180108d64`
- `0x180193010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18010625e`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18010625e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106272`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106272`

## string_xrefs

- `0x1801062d7`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ___MakeAndInitialize_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperationWithProgress_PEAUIDiagnosticAnalysisResult_Core_Autopilot_ModernDeployment__UDiagnosticAnalysisProgress_234__Foundation_Windows___details_wil__YAJPEAU__IAsyncOperationWithProgress_PEAUIDiagnosticAnalysisResult_Core_Autopilot_ModernDeployment__UDiagnosticAnalysisProgress_234__Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z_V1_1____WaitForCompletion_PEAU__IAsyncOperationWithProgress_PEAUIDiagnosticAnalysisResult_Core_Autopilot_ModernDeployment__UDiagnosticAnalysisProgress_234__Foundation_Windows___23_YAJ01K2_Z___V_Details_WRL_Microsoft__YAJPEAPEAVCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperationWithProgress_PEAUIDiagnosticAnalysisResult_Core_Autopilot_ModernDeployment__UDiagnosticAnalysisProgress_234__Foundation_Windows___details_wil__YAJPEAU__IAsyncOperationWithProgress_PEAUIDiagnosticAnalysisResult_Core_Autopilot_ModernDeployment__UDiagnosticAnalysisProgress_234__Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__Z(
        _QWORD *a1)
{
  _DWORD *v2; // rbx
  unsigned int v3; // edi
  wil::details *v4; // rcx
  HANDLE Event; // rbp
  int LastErrorFailHr; // eax
  int v8; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  _DWORD *v10; // [rsp+40h] [rbp+8h] BYREF
  _DWORD *v11; // [rsp+48h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  v11 = v2;
  if ( v2 )
  {
    *(_QWORD *)v2 = &Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 2));
    v2[11] = 1;
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress>'};
    *((_QWORD *)v2 + 1) = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *>'::`2'::CompletionDelegate::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = &`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *>'::`2'::CompletionDelegate::`vftable';
    *((_QWORD *)v2 + 1) = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *>'::`2'::CompletionDelegate::`vftable';
    v2[12] = 0;
    *((_QWORD *)v2 + 7) = 0;
    v10 = v2;
    v11 = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    if ( Event )
    {
      GetLastError();
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        v2 + 14,
        Event);
    }
    else
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v4);
      v3 = LastErrorFailHr;
      if ( LastErrorFailHr < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x62B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
          (const char *)(unsigned int)LastErrorFailHr,
          v8);
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v10);
        goto LABEL_8;
      }
    }
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v2 + 8LL))(v2);
    *a1 = v2;
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v10);
    v3 = 0;
  }
  else
  {
    v3 = -2147024882;
  }
LABEL_8:
  Microsoft::WRL::Details::MakeAllocator<CMockEngine>::~MakeAllocator<CMockEngine>(&v11);
  return v3;
}

```

## disassembly

```asm
0x180106198  mov     [rsp+arg_10], rbx
0x18010619d  push    rbp
0x18010619e  push    rsi
0x18010619f  push    rdi; int
0x1801061a0  sub     rsp, 20h
0x1801061a4  mov     rsi, rcx
0x1801061a7  mov     qword ptr [rcx], 0
0x1801061ae  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801061b5  mov     ecx, 40h ; '@'; unsigned __int64
0x1801061ba  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1801061bf  mov     rbx, rax
0x1801061c2  mov     [rsp+38h+arg_8], rax
0x1801061c7  test    rax, rax
0x1801061ca  jnz     short loc_1801061D6
0x1801061cc  mov     edi, 8007000Eh
0x1801061d1  jmp     loc_1801062AA
0x1801061d6  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>::`vftable'
0x1801061dd  mov     [rbx], rax
0x1801061e0  lea     rdi, [rbx+8]
0x1801061e4  mov     rcx, rdi; this
0x1801061e7  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1801061ec  mov     dword ptr [rbx+2Ch], 1
0x1801061f3  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationWithProgressCompletedHandler@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress>'}
0x1801061fa  mov     [rbx], rax
0x1801061fd  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperationWithProgress@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *>(Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180106204  mov     [rdi], rax
0x180106207  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18010620e  test    rcx, rcx
0x180106211  jz      short loc_180106220
0x180106213  mov     rax, [rcx]
0x180106216  mov     rax, [rax+8]
0x18010621a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010621f  nop
0x180106220  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperationWithProgress@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationWithProgressCompletedHandler@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *>(Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress>'}
0x180106227  mov     [rbx], rax
0x18010622a  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperationWithProgress@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *>(Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180106231  mov     [rdi], rax
0x180106234  mov     dword ptr [rbx+30h], 0
0x18010623b  mov     qword ptr [rbx+38h], 0
0x180106243  mov     [rsp+38h+arg_0], rbx
0x180106248  mov     [rsp+38h+arg_8], 0
0x180106251  mov     r9d, 1F0003h; dwDesiredAccess
0x180106257  xor     r8d, r8d; dwFlags
0x18010625a  xor     edx, edx; lpName
0x18010625c  xor     ecx, ecx; lpEventAttributes
0x18010625e  call    cs:__imp_CreateEventExW
0x180106265  nop     dword ptr [rax+rax+00h]
0x18010626a  mov     rbp, rax
0x18010626d  test    rax, rax
0x180106270  jz      short loc_1801062C4
0x180106272  call    cs:__imp_GetLastError
0x180106279  nop     dword ptr [rax+rax+00h]
0x18010627e  mov     rdx, rbp
0x180106281  lea     rcx, [rbx+38h]
0x180106285  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18010628a  nop
0x18010628b  mov     rax, [rbx]
0x18010628e  mov     rcx, rbx
0x180106291  mov     rax, [rax+8]
0x180106295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010629a  nop
0x18010629b  mov     [rsi], rbx
0x18010629e  lea     rcx, [rsp+38h+arg_0]
0x1801062a3  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801062a8  xor     edi, edi
0x1801062aa  lea     rcx, [rsp+38h+arg_8]
0x1801062af  call    ??1?$MakeAllocator@VCMockEngine@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CMockEngine>::~MakeAllocator<CMockEngine>(void)
0x1801062b4  mov     eax, edi
0x1801062b6  mov     rbx, [rsp+38h+arg_10]
0x1801062bb  add     rsp, 20h
0x1801062bf  pop     rdi
0x1801062c0  pop     rsi
0x1801062c1  pop     rbp
0x1801062c2  retn
0x1801062c4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1801062c9  mov     edi, eax
0x1801062cb  test    eax, eax
0x1801062cd  jns     short loc_18010628B
0x1801062cf  mov     rcx, [rsp+38h]; this
0x1801062d4  mov     r9d, eax; char *
0x1801062d7  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1801062de  mov     edx, 62Bh; void *
0x1801062e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801062e8  lea     rcx, [rsp+38h+arg_0]
0x1801062ed  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801062f2  jmp     short loc_1801062AA
```
