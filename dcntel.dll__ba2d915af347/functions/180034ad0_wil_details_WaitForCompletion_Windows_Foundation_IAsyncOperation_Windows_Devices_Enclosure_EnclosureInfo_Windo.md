# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Enclosure::EnclosureInfo *> *>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enclosure::EnclosureInfo *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x180034ad0`
- end: `0x180034da6`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVEnclosureInfo@Enclosure@Devices@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVEnclosureInfo@Enclosure@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `726`
- prototype: `__int64(__int64, DWORD, int, ...)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180034dac`

## callees

- `0x1800097d0`
- `0x18000f378`
- `0x180011ce4`
- `0x180013708`
- `0x180034ad0`
- `0x18003517c`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180034b90`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180034b90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034bd2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034bd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034ba2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034bb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034ba2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034bb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034bbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034bbd`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180034cbc`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180034cbc`

## string_xrefs

- `0x180034c1b`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x180034c51`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x180034c7a`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x180034ccf`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Enclosure::EnclosureInfo *> *>(
        __int64 a1,
        DWORD a2,
        int a3,
        ...)
{
  char *v4; // rbx
  unsigned int v5; // edi
  wil::details *v6; // rcx
  HANDLE Event; // rsi
  void *v8; // rdi
  DWORD LastError; // r15d
  unsigned int v10; // r8d
  const char *v11; // r9
  int v12; // eax
  int LastErrorFailHr; // eax
  HRESULT v15; // eax
  __int64 v16; // rcx
  int lpdwindex; // [rsp+20h] [rbp-20h]
  int lpdwindexa; // [rsp+20h] [rbp-20h]
  HANDLE pHandles; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  DWORD dwindex; // [rsp+78h] [rbp+38h] BYREF
  int v22; // [rsp+80h] [rbp+40h] BYREF
  __int64 v23; // [rsp+88h] [rbp+48h] BYREF
  va_list va; // [rsp+88h] [rbp+48h]
  va_list va1; // [rsp+90h] [rbp+50h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v23 = va_arg(va1, _QWORD);
  v22 = a3;
  dwindex = a2;
  v4 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
  {
    v5 = -2147024882;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x648,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)v5,
      lpdwindex);
    return v5;
  }
  *(_QWORD *)v4 = &Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManager *,Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManagerEnabledProfilesChangedEventArgs *>::`vftable';
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(v4 + 8);
  *((_DWORD *)v4 + 11) = 1;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enclosure::EnclosureInfo *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enclosure::EnclosureInfo *>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enclosure::EnclosureInfo *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Enclosure::EnclosureInfo *> *>'::`2'::CompletionDelegate::`vftable';
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enclosure::EnclosureInfo *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_DWORD *)v4 + 12) = 0;
  *((_QWORD *)v4 + 7) = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    v8 = (void *)*((_QWORD *)v4 + 7);
    if ( v8 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v8) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v10, v11);
      SetLastError(LastError);
    }
    *((_QWORD *)v4 + 7) = Event;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v6);
    v5 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x62B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
        (const char *)(unsigned int)LastErrorFailHr,
        lpdwindex);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
      goto LABEL_14;
    }
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
  v12 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)a1 + 48LL))(a1, v4);
  v5 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x649,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v12,
      lpdwindex);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
    return v5;
  }
  pHandles = (HANDLE)*((_QWORD *)v4 + 7);
  dwindex = 0;
  v15 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
  v5 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x655,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v15,
      lpdwindexa);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
    return v5;
  }
  if ( *((_DWORD *)v4 + 12) != 1 )
  {
    v23 = 0;
    v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))a1)(
           a1,
           &GUID_00000036_0000_0000_c000_000000000046,
           (__int64 *)va);
    if ( (v5 & 0x80000000) == 0 )
    {
      v22 = -2147418113;
      v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v23 + 64LL))(v23, &v22);
      if ( (v5 & 0x80000000) == 0 )
        v5 = v22;
    }
    v16 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
    return v5;
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
  return 0;
}

```

## disassembly

```asm
0x180034ad0  mov     rax, rsp
0x180034ad3  mov     [rax+8], rbx
0x180034ad7  mov     [rax+20h], r9
0x180034adb  mov     [rax+18h], r8d
0x180034adf  mov     [rax+10h], edx
0x180034ae2  push    rbp
0x180034ae3  push    rsi
0x180034ae4  push    rdi
0x180034ae5  push    r14
0x180034ae7  push    r15
0x180034ae9  mov     rbp, rsp
0x180034aec  sub     rsp, 40h
0x180034af0  mov     r14, rcx
0x180034af3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180034afa  mov     ecx, 40h ; '@'; unsigned __int64
0x180034aff  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180034b04  mov     rbx, rax
0x180034b07  test    rax, rax
0x180034b0a  jnz     short loc_180034B16
0x180034b0c  mov     edi, 8007000Eh
0x180034b11  jmp     loc_180034C73
0x180034b16  lea     rax, ??_7?$ITypedEventHandler@PEAVCoreKeyboardInputProfileManager@Core@Text@Internal@UI@Windows@@PEAVCoreKeyboardInputProfileManagerEnabledProfilesChangedEventArgs@23456@@Foundation@Windows@@6B@; const Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManager *,Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManagerEnabledProfilesChangedEventArgs *>::`vftable'
0x180034b1d  mov     [rbx], rax
0x180034b20  lea     rdi, [rbx+8]
0x180034b24  mov     rcx, rdi
0x180034b27  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x180034b2c  mov     dword ptr [rbx+2Ch], 1
0x180034b33  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVEnclosureInfo@Enclosure@Devices@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVEnclosureInfo@Enclosure@Devices@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enclosure::EnclosureInfo *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enclosure::EnclosureInfo *>'}
0x180034b3a  mov     [rbx], rax
0x180034b3d  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVEnclosureInfo@Enclosure@Devices@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enclosure::EnclosureInfo *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180034b44  mov     [rdi], rax
0x180034b47  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180034b4e  test    rcx, rcx
0x180034b51  jz      short loc_180034B60
0x180034b53  mov     rax, [rcx]
0x180034b56  mov     rax, [rax+8]
0x180034b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b5f  nop
0x180034b60  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVEnclosureInfo@Enclosure@Devices@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVEnclosureInfo@Enclosure@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@PEAVEnclosureInfo@Enclosure@Devices@Windows@@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Enclosure::EnclosureInfo *> *>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enclosure::EnclosureInfo *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enclosure::EnclosureInfo *>'}
0x180034b67  mov     [rbx], rax
0x180034b6a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVEnclosureInfo@Enclosure@Devices@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enclosure::EnclosureInfo *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180034b71  mov     [rdi], rax
0x180034b74  mov     dword ptr [rbx+30h], 0
0x180034b7b  mov     qword ptr [rbx+38h], 0
0x180034b83  mov     r9d, 1F0003h; dwDesiredAccess
0x180034b89  xor     r8d, r8d; dwFlags
0x180034b8c  xor     edx, edx; lpName
0x180034b8e  xor     ecx, ecx; lpEventAttributes
0x180034b90  call    cs:__imp_CreateEventExW
0x180034b96  mov     rsi, rax
0x180034b99  test    rax, rax
0x180034b9c  jz      loc_180034C3F
0x180034ba2  call    cs:__imp_GetLastError
0x180034ba8  mov     rdi, [rbx+38h]
0x180034bac  test    rdi, rdi
0x180034baf  jz      short loc_180034BD8
0x180034bb1  call    cs:__imp_GetLastError
0x180034bb7  mov     r15d, eax
0x180034bba  mov     rcx, rdi; hObject
0x180034bbd  call    cs:__imp_CloseHandle
0x180034bc3  mov     rcx, [rbp+28h]; this
0x180034bc7  test    eax, eax
0x180034bc9  jz      loc_180034D9B
0x180034bcf  mov     ecx, r15d; dwErrCode
0x180034bd2  call    cs:__imp_SetLastError
0x180034bd8  mov     [rbx+38h], rsi
0x180034bdc  mov     rax, [rbx]
0x180034bdf  mov     rcx, rbx
0x180034be2  mov     rax, [rax+8]
0x180034be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034beb  nop
0x180034bec  mov     rax, [rbx]
0x180034bef  mov     rcx, rbx
0x180034bf2  mov     rax, [rax+10h]
0x180034bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034bfb  nop
0x180034bfc  mov     rax, [r14]
0x180034bff  mov     rdx, rbx
0x180034c02  mov     rcx, r14
0x180034c05  mov     rax, [rax+30h]
0x180034c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034c0e  mov     edi, eax
0x180034c10  test    eax, eax
0x180034c12  jns     short loc_180034C93
0x180034c14  mov     rcx, [rbp+28h]; this
0x180034c18  mov     r9d, eax; char *
0x180034c1b  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180034c22  mov     edx, 649h; void *
0x180034c27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034c2c  nop
0x180034c2d  mov     rcx, [rbx]
0x180034c30  mov     rax, [rcx+10h]
0x180034c34  mov     rcx, rbx
0x180034c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034c3c  nop
0x180034c3d  jmp     short loc_180034C8C
0x180034c3f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180034c44  mov     edi, eax
0x180034c46  test    eax, eax
0x180034c48  jns     short loc_180034BDC
0x180034c4a  mov     rcx, [rbp+28h]; this
0x180034c4e  mov     r9d, eax; char *
0x180034c51  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180034c58  mov     edx, 62Bh; void *
0x180034c5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034c62  nop
0x180034c63  mov     rax, [rbx]
0x180034c66  mov     rcx, rbx
0x180034c69  mov     rax, [rax+10h]
0x180034c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034c72  nop
0x180034c73  mov     rcx, [rbp+28h]; this
0x180034c77  mov     r9d, edi; char *
0x180034c7a  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180034c81  mov     edx, 648h; void *
0x180034c86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034c8b  nop
0x180034c8c  mov     eax, edi
0x180034c8e  jmp     loc_180034D8A
0x180034c93  mov     rax, [rbx+38h]
0x180034c97  mov     [rbp+pHandles], rax
0x180034c9b  mov     [rbp+dwindex], 0
0x180034ca2  lea     rax, [rbp+dwindex]
0x180034ca6  mov     qword ptr [rsp+40h+lpdwindex], rax; int
0x180034cab  lea     r9, [rbp+pHandles]; pHandles
0x180034caf  mov     r8d, 1; cHandles
0x180034cb5  or      edx, 0FFFFFFFFh; dwTimeout
0x180034cb8  lea     ecx, [r8+7]; dwFlags
0x180034cbc  call    cs:__imp_CoWaitForMultipleHandles
0x180034cc2  mov     edi, eax
0x180034cc4  test    eax, eax
0x180034cc6  jns     short loc_180034CF3
0x180034cc8  mov     rcx, [rbp+28h]; this
0x180034ccc  mov     r9d, eax; char *
0x180034ccf  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180034cd6  mov     edx, 655h; void *
0x180034cdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034ce0  nop
0x180034ce1  mov     rcx, [rbx]
0x180034ce4  mov     rax, [rcx+10h]
0x180034ce8  mov     rcx, rbx
0x180034ceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034cf0  nop
0x180034cf1  jmp     short loc_180034C8C
0x180034cf3  mov     eax, [rbx+30h]
0x180034cf6  cmp     eax, 1
0x180034cf9  jz      short loc_180034D78
0x180034cfb  mov     [rbp+arg_18], 0
0x180034d03  mov     rax, [r14]
0x180034d06  lea     r8, [rbp+arg_18]
0x180034d0a  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180034d11  mov     rcx, r14
0x180034d14  mov     rax, [rax]
0x180034d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034d1c  mov     edi, eax
0x180034d1e  test    eax, eax
0x180034d20  js      short loc_180034D45
0x180034d22  mov     [rbp+arg_10], 8000FFFFh
0x180034d29  mov     rcx, [rbp+arg_18]
0x180034d2d  mov     rax, [rcx]
0x180034d30  lea     rdx, [rbp+arg_10]
0x180034d34  mov     rax, [rax+40h]
0x180034d38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034d3d  mov     edi, eax
0x180034d3f  test    eax, eax
0x180034d41  cmovns  edi, [rbp+arg_10]
0x180034d45  mov     rcx, [rbp+arg_18]
0x180034d49  test    rcx, rcx
0x180034d4c  jz      short loc_180034D63
0x180034d4e  mov     [rbp+arg_18], 0
0x180034d56  mov     rax, [rcx]
0x180034d59  mov     rax, [rax+10h]
0x180034d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034d62  nop
0x180034d63  mov     rax, [rbx]
0x180034d66  mov     rcx, rbx
0x180034d69  mov     rax, [rax+10h]
0x180034d6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034d72  nop
0x180034d73  jmp     loc_180034C8C
0x180034d78  mov     rax, [rbx]
0x180034d7b  mov     rcx, rbx
0x180034d7e  mov     rax, [rax+10h]
0x180034d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034d87  nop
0x180034d88  xor     eax, eax
0x180034d8a  mov     rbx, [rsp+40h+arg_0]
0x180034d8f  add     rsp, 40h
0x180034d93  pop     r15
0x180034d95  pop     r14
0x180034d97  pop     rdi
0x180034d98  pop     rsi
0x180034d99  pop     rbp
0x180034d9a  retn
0x180034d9b  mov     edx, 0A0Bh; void *
0x180034da0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
