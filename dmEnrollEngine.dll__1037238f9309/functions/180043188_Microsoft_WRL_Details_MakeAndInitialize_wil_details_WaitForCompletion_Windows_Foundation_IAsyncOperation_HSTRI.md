# Microsoft::WRL::Details::MakeAndInitialize<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,>(`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate * *)

- ea: `0x180043188`
- end: `0x1800432cb`
- name: `??$MakeAndInitialize@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@V1?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@23@YAJ01K2@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Z`
- size: `323`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800432d4`

## callees

- `0x18000fd8c`
- `0x180011938`
- `0x18001d3ec`
- `0x1800212dc`
- `0x18002e5ac`
- `0x18003c968`
- `0x180043188`
- `0x180043438`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180043242`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180043242`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043250`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043250`

## string_xrefs

- `0x1800432ae`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ___MakeAndInitialize_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAUHSTRING_____Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAUHSTRING_____Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z_V1_1____WaitForCompletion_PEAU__IAsyncOperation_PEAUHSTRING_____Foundation_Windows___23_YAJ01K2_Z___V_Details_WRL_Microsoft__YAJPEAPEAVCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAUHSTRING_____Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAUHSTRING_____Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__Z(
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
  v2 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  v12 = v2;
  if ( v2 )
  {
    Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::FtmBase>(v2);
    v3[11] = 1;
    *(_QWORD *)v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>'};
    *((_QWORD *)v3 + 1) = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>'::`2'::CompletionDelegate::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v3 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>'::`2'::CompletionDelegate::`vftable';
    *((_QWORD *)v3 + 1) = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>'::`2'::CompletionDelegate::`vftable';
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
        Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v11);
        goto LABEL_8;
      }
    }
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v3 + 8LL))(v3);
    *a1 = v3;
    Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v11);
    v4 = 0;
  }
  else
  {
    v4 = -2147024882;
  }
LABEL_8:
  __1__MakeAllocator_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAUHSTRING_____Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAUHSTRING_____Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__Details_WRL_Microsoft__QEAA_XZ(&v12);
  return v4;
}

```

## disassembly

```asm
0x180043188  mov     [rsp+arg_10], rbx
0x18004318d  push    rbp
0x18004318e  push    rsi
0x18004318f  push    rdi; int
0x180043190  sub     rsp, 20h
0x180043194  mov     rsi, rcx
0x180043197  mov     qword ptr [rcx], 0
0x18004319e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800431a5  mov     ecx, 40h ; '@'; unsigned __int64
0x1800431aa  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800431af  mov     rbx, rax
0x1800431b2  mov     [rsp+38h+arg_8], rax
0x1800431b7  test    rax, rax
0x1800431ba  jnz     short loc_1800431C6
0x1800431bc  mov     edi, 8007000Eh
0x1800431c1  jmp     loc_180043282
0x1800431c6  mov     rcx, rbx
0x1800431c9  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::FtmBase>(void)
0x1800431ce  mov     dword ptr [rbx+2Ch], 1
0x1800431d5  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>'}
0x1800431dc  mov     [rbx], rax
0x1800431df  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800431e6  mov     [rbx+8], rax
0x1800431ea  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800431f1  test    rcx, rcx
0x1800431f4  jz      short loc_180043203
0x1800431f6  mov     rax, [rcx]
0x1800431f9  mov     rax, [rax+8]
0x1800431fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043202  nop
0x180043203  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>'}
0x18004320a  mov     [rbx], rax
0x18004320d  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180043214  mov     [rbx+8], rax
0x180043218  mov     dword ptr [rbx+30h], 0
0x18004321f  mov     qword ptr [rbx+38h], 0
0x180043227  mov     [rsp+38h+arg_0], rbx
0x18004322c  mov     [rsp+38h+arg_8], 0
0x180043235  mov     r9d, 1F0003h; dwDesiredAccess
0x18004323b  xor     r8d, r8d; dwFlags
0x18004323e  xor     edx, edx; lpName
0x180043240  xor     ecx, ecx; lpEventAttributes
0x180043242  call    cs:__imp_CreateEventExW
0x180043248  mov     rbp, rax
0x18004324b  test    rax, rax
0x18004324e  jz      short loc_18004329B
0x180043250  call    cs:__imp_GetLastError
0x180043256  mov     rdx, rbp
0x180043259  lea     rcx, [rbx+38h]
0x18004325d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180043262  nop
0x180043263  mov     rax, [rbx]
0x180043266  mov     rcx, rbx
0x180043269  mov     rax, [rax+8]
0x18004326d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043272  nop
0x180043273  mov     [rsi], rbx
0x180043276  lea     rcx, [rsp+38h+arg_0]
0x18004327b  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x180043280  xor     edi, edi
0x180043282  lea     rcx, [rsp+38h+arg_8]
0x180043287  call    ??1?$MakeAllocator@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate>::~MakeAllocator<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate>(void)
0x18004328c  mov     eax, edi
0x18004328e  mov     rbx, [rsp+38h+arg_10]
0x180043293  add     rsp, 20h
0x180043297  pop     rdi
0x180043298  pop     rsi
0x180043299  pop     rbp
0x18004329a  retn
0x18004329b  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800432a0  mov     edi, eax
0x1800432a2  test    eax, eax
0x1800432a4  jns     short loc_180043263
0x1800432a6  mov     rcx, [rsp+38h]; this
0x1800432ab  mov     r9d, eax; char *
0x1800432ae  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800432b5  mov     edx, 62Bh; void *
0x1800432ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800432bf  lea     rcx, [rsp+38h+arg_0]
0x1800432c4  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x1800432c9  jmp     short loc_180043282
```
