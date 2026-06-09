# Microsoft::WRL::Details::MakeAndInitialize<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate>>)

- ea: `0x180039f74`
- end: `0x18003a125`
- name: `??$MakeAndInitialize@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@V1?1???$WaitForCompletion@PEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@@23@YAJ01K2@Z@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@WRL@Microsoft@@@012@@Z`
- size: `433`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003a12c`

## callees

- `0x18000aecc`
- `0x18000f1a0`
- `0x18000ff24`
- `0x180010d94`
- `0x180039f74`
- `0x18003a918`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18003a042`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18003a042`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a099`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a099`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a05a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a06f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a05a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a06f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a081`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a081`

## string_xrefs

- `0x18003a113`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18003a0ef`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ___MakeAndInitialize_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperationWithProgress_PEAVDeploymentResult_Deployment_Management_Windows__UDeploymentProgress_234__Foundation_Windows___details_wil__YAJPEAU__IAsyncOperationWithProgress_PEAVDeploymentResult_Deployment_Management_Windows__UDeploymentProgress_234__Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z_V1_1____WaitForCompletion_PEAU__IAsyncOperationWithProgress_PEAVDeploymentResult_Deployment_Management_Windows__UDeploymentProgress_234__Foundation_Windows___23_YAJ01K2_Z___V_Details_WRL_Microsoft__YAJV__ComPtrRef_V__ComPtr_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperationWithProgress_PEAVDeploymentResult_Deployment_Management_Windows__UDeploymentProgress_234__Foundation_Windows___details_wil__YAJPEAU__IAsyncOperationWithProgress_PEAVDeploymentResult_Deployment_Management_Windows__UDeploymentProgress_234__Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__WRL_Microsoft___012__Z(
        __int64 *a1)
{
  __int64 v2; // rcx
  _DWORD *v3; // rdi
  unsigned int v4; // esi
  wil::details *v5; // rcx
  HANDLE Event; // rbp
  void *v7; // rsi
  DWORD LastError; // r14d
  const char *v9; // r9
  int LastErrorFailHr; // eax
  int v12; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = *a1;
  if ( v2 )
  {
    *a1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  *a1 = 0;
  v3 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v3 )
  {
    *(_QWORD *)v3 = &Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v3 + 2));
    v3[11] = 1;
    *(_QWORD *)v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>'};
    *((_QWORD *)v3 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v3 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *>'::`2'::CompletionDelegate::`vftable';
    *((_QWORD *)v3 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    v3[12] = 0;
    *((_QWORD *)v3 + 7) = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    if ( Event )
    {
      GetLastError();
      v7 = (void *)*((_QWORD *)v3 + 7);
      if ( v7 )
      {
        LastError = GetLastError();
        if ( !CloseHandle(v7) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0xA0B,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v9);
        SetLastError(LastError);
      }
      *((_QWORD *)v3 + 7) = Event;
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
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
          (const char *)(unsigned int)LastErrorFailHr,
          v12);
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v3 + 16LL))(v3);
        return v4;
      }
    }
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v3 + 8LL))(v3);
    *a1 = (__int64)v3;
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v3 + 16LL))(v3);
    return 0;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
}

```

## disassembly

```asm
0x180039f74  push    rbx
0x180039f76  push    rbp
0x180039f77  push    rsi
0x180039f78  push    rdi
0x180039f79  push    r14; int
0x180039f7b  sub     rsp, 20h
0x180039f7f  mov     rbx, rcx
0x180039f82  mov     rcx, [rcx]
0x180039f85  test    rcx, rcx
0x180039f88  jz      short loc_180039F9E
0x180039f8a  mov     qword ptr [rbx], 0
0x180039f91  mov     rax, [rcx]
0x180039f94  mov     rax, [rax+10h]
0x180039f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039f9d  nop
0x180039f9e  mov     qword ptr [rbx], 0
0x180039fa5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180039fac  mov     ecx, 40h ; '@'; unsigned __int64
0x180039fb1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180039fb6  mov     rdi, rax
0x180039fb9  test    rax, rax
0x180039fbc  jnz     short loc_180039FC8
0x180039fbe  mov     esi, 8007000Eh
0x180039fc3  jmp     loc_18003A0CE
0x180039fc8  lea     rax, ??_7?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>::`vftable'
0x180039fcf  mov     [rdi], rax
0x180039fd2  lea     rsi, [rdi+8]
0x180039fd6  mov     rcx, rsi; this
0x180039fd9  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180039fde  mov     dword ptr [rdi+2Ch], 1
0x180039fe5  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>'}
0x180039fec  mov     [rdi], rax
0x180039fef  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180039ff6  mov     [rsi], rax
0x180039ff9  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18003a000  test    rcx, rcx
0x18003a003  jz      short loc_18003A012
0x18003a005  mov     rax, [rcx]
0x18003a008  mov     rax, [rax+8]
0x18003a00c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a011  nop
0x18003a012  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>'}
0x18003a019  mov     [rdi], rax
0x18003a01c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18003a023  mov     [rsi], rax
0x18003a026  mov     dword ptr [rdi+30h], 0
0x18003a02d  mov     qword ptr [rdi+38h], 0
0x18003a035  mov     r9d, 1F0003h; dwDesiredAccess
0x18003a03b  xor     r8d, r8d; dwFlags
0x18003a03e  xor     edx, edx; lpName
0x18003a040  xor     ecx, ecx; lpEventAttributes
0x18003a042  call    cs:__imp_CreateEventExW
0x18003a049  nop     dword ptr [rax+rax+00h]
0x18003a04e  mov     rbp, rax
0x18003a051  test    rax, rax
0x18003a054  jz      loc_18003A0DC
0x18003a05a  call    cs:__imp_GetLastError
0x18003a061  nop     dword ptr [rax+rax+00h]
0x18003a066  mov     rsi, [rdi+38h]
0x18003a06a  test    rsi, rsi
0x18003a06d  jz      short loc_18003A0A5
0x18003a06f  call    cs:__imp_GetLastError
0x18003a076  nop     dword ptr [rax+rax+00h]
0x18003a07b  mov     r14d, eax
0x18003a07e  mov     rcx, rsi; hObject
0x18003a081  call    cs:__imp_CloseHandle
0x18003a088  nop     dword ptr [rax+rax+00h]
0x18003a08d  mov     rcx, [rsp+48h]; this
0x18003a092  test    eax, eax
0x18003a094  jz      short loc_18003A113
0x18003a096  mov     ecx, r14d; dwErrCode
0x18003a099  call    cs:__imp_SetLastError
0x18003a0a0  nop     dword ptr [rax+rax+00h]
0x18003a0a5  mov     [rdi+38h], rbp
0x18003a0a9  mov     rax, [rdi]
0x18003a0ac  mov     rcx, rdi
0x18003a0af  mov     rax, [rax+8]
0x18003a0b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a0b8  nop
0x18003a0b9  mov     [rbx], rdi
0x18003a0bc  mov     rax, [rdi]
0x18003a0bf  mov     rcx, rdi
0x18003a0c2  mov     rax, [rax+10h]
0x18003a0c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a0cb  nop
0x18003a0cc  xor     esi, esi
0x18003a0ce  mov     eax, esi
0x18003a0d0  add     rsp, 20h
0x18003a0d4  pop     r14
0x18003a0d6  pop     rdi
0x18003a0d7  pop     rsi
0x18003a0d8  pop     rbp
0x18003a0d9  pop     rbx
0x18003a0da  retn
0x18003a0dc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18003a0e1  mov     esi, eax
0x18003a0e3  test    eax, eax
0x18003a0e5  jns     short loc_18003A0A9
0x18003a0e7  mov     rcx, [rsp+48h]; this
0x18003a0ec  mov     r9d, eax; char *
0x18003a0ef  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003a0f6  mov     edx, 62Bh; void *
0x18003a0fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a100  nop
0x18003a101  mov     rax, [rdi]
0x18003a104  mov     rcx, rdi
0x18003a107  mov     rax, [rax+10h]
0x18003a10b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a110  nop
0x18003a111  jmp     short loc_18003A0CE
0x18003a113  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003a11a  mov     edx, 0A0Bh; void *
0x18003a11f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
