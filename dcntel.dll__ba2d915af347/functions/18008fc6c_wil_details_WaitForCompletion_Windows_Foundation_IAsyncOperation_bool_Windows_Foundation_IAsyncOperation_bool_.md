# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x18008fc6c`
- end: `0x18008ff6e`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@_N@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `770`
- prototype: `__int64 __fastcall(__int64, DWORD, int, _BYTE *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180094550`
- `0x1800d7190`

## callees

- `0x1800097d0`
- `0x18000f378`
- `0x180011ce4`
- `0x180013708`
- `0x18003517c`
- `0x18008fc6c`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18008fd32`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18008fd32`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008fd74`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008fd74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fd44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fd53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fd44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fd53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008fd5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008fd5f`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18008fe5f`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18008fe5f`

## string_xrefs

- `0x18008fdbd`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18008fdf3`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18008fe1c`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`
- `0x18008fe96`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(
        __int64 a1,
        DWORD a2,
        int a3,
        _BYTE *a4)
{
  char *v6; // rbx
  unsigned int v7; // edi
  wil::details *v8; // rcx
  HANDLE Event; // r15
  void *v10; // rdi
  DWORD LastError; // r12d
  unsigned int v12; // r8d
  const char *v13; // r9
  int v14; // eax
  int LastErrorFailHr; // eax
  HRESULT v17; // eax
  __int64 v18; // rcx
  int lpdwindex; // [rsp+20h] [rbp-20h]
  int lpdwindexa; // [rsp+20h] [rbp-20h]
  HANDLE pHandles; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  DWORD dwindex; // [rsp+88h] [rbp+48h] BYREF
  int v24; // [rsp+90h] [rbp+50h] BYREF
  __int64 v25; // [rsp+98h] [rbp+58h] BYREF

  v24 = a3;
  dwindex = a2;
  if ( a4 )
    *a4 = 0;
  v6 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v6 )
  {
    v7 = -2147024882;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x648,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)v7,
      lpdwindex);
    return v7;
  }
  *(_QWORD *)v6 = &Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManager *,Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManagerEnabledProfilesChangedEventArgs *>::`vftable';
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(v6 + 8);
  *((_DWORD *)v6 + 11) = 1;
  *(_QWORD *)v6 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<bool>'};
  *((_QWORD *)v6 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v6 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>'::`2'::CompletionDelegate::`vftable';
  *((_QWORD *)v6 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_DWORD *)v6 + 12) = 0;
  *((_QWORD *)v6 + 7) = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    v10 = (void *)*((_QWORD *)v6 + 7);
    if ( v10 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v10) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v12, v13);
      SetLastError(LastError);
    }
    *((_QWORD *)v6 + 7) = Event;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v8);
    v7 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x62B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
        (const char *)(unsigned int)LastErrorFailHr,
        lpdwindex);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
      goto LABEL_16;
    }
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
  v14 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)a1 + 48LL))(a1, v6);
  v7 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x649,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v14,
      lpdwindex);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
    return v7;
  }
  pHandles = (HANDLE)*((_QWORD *)v6 + 7);
  dwindex = 0;
  v17 = CoWaitForMultipleHandles(8u, 0x2710u, 1u, &pHandles, &dwindex);
  v7 = v17;
  if ( a4 && v17 == -2147417835 )
  {
    *a4 = 1;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
  }
  else
  {
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x655,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
        (const char *)(unsigned int)v17,
        lpdwindexa);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
      return v7;
    }
    if ( *((_DWORD *)v6 + 12) != 1 )
    {
      v25 = 0;
      v7 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))a1)(
             a1,
             &GUID_00000036_0000_0000_c000_000000000046,
             &v25);
      if ( (v7 & 0x80000000) == 0 )
      {
        v24 = -2147418113;
        v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v25 + 64LL))(v25, &v24);
        if ( (v7 & 0x80000000) == 0 )
          v7 = v24;
      }
      v18 = v25;
      if ( v25 )
      {
        v25 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      }
      (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
      return v7;
    }
    (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return 0;
}

```

## disassembly

```asm
0x18008fc6c  mov     [rsp-38h+arg_10], r8d
0x18008fc71  mov     [rsp-38h+dwindex], edx
0x18008fc75  push    rbp
0x18008fc76  push    rbx
0x18008fc77  push    rsi
0x18008fc78  push    rdi
0x18008fc79  push    r12
0x18008fc7b  push    r14
0x18008fc7d  push    r15
0x18008fc7f  mov     rbp, rsp
0x18008fc82  sub     rsp, 40h
0x18008fc86  mov     rsi, r9
0x18008fc89  mov     r14, rcx
0x18008fc8c  test    r9, r9
0x18008fc8f  jz      short loc_18008FC95
0x18008fc91  mov     byte ptr [r9], 0
0x18008fc95  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008fc9c  mov     ecx, 40h ; '@'; unsigned __int64
0x18008fca1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18008fca6  mov     rbx, rax
0x18008fca9  test    rax, rax
0x18008fcac  jnz     short loc_18008FCB8
0x18008fcae  mov     edi, 8007000Eh
0x18008fcb3  jmp     loc_18008FE15
0x18008fcb8  lea     rax, ??_7?$ITypedEventHandler@PEAVCoreKeyboardInputProfileManager@Core@Text@Internal@UI@Windows@@PEAVCoreKeyboardInputProfileManagerEnabledProfilesChangedEventArgs@23456@@Foundation@Windows@@6B@; const Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManager *,Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManagerEnabledProfilesChangedEventArgs *>::`vftable'
0x18008fcbf  mov     [rbx], rax
0x18008fcc2  lea     rdi, [rbx+8]
0x18008fcc6  mov     rcx, rdi
0x18008fcc9  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x18008fcce  mov     dword ptr [rbx+2Ch], 1
0x18008fcd5  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<bool>'}
0x18008fcdc  mov     [rbx], rax
0x18008fcdf  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18008fce6  mov     [rdi], rax
0x18008fce9  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18008fcf0  test    rcx, rcx
0x18008fcf3  jz      short loc_18008FD02
0x18008fcf5  mov     rax, [rcx]
0x18008fcf8  mov     rax, [rax+8]
0x18008fcfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fd01  nop
0x18008fd02  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@_N@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@_N@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<bool>'}
0x18008fd09  mov     [rbx], rax
0x18008fd0c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18008fd13  mov     [rdi], rax
0x18008fd16  mov     dword ptr [rbx+30h], 0
0x18008fd1d  mov     qword ptr [rbx+38h], 0
0x18008fd25  mov     r9d, 1F0003h; dwDesiredAccess
0x18008fd2b  xor     r8d, r8d; dwFlags
0x18008fd2e  xor     edx, edx; lpName
0x18008fd30  xor     ecx, ecx; lpEventAttributes
0x18008fd32  call    cs:__imp_CreateEventExW
0x18008fd38  mov     r15, rax
0x18008fd3b  test    rax, rax
0x18008fd3e  jz      loc_18008FDE1
0x18008fd44  call    cs:__imp_GetLastError
0x18008fd4a  mov     rdi, [rbx+38h]
0x18008fd4e  test    rdi, rdi
0x18008fd51  jz      short loc_18008FD7A
0x18008fd53  call    cs:__imp_GetLastError
0x18008fd59  mov     r12d, eax
0x18008fd5c  mov     rcx, rdi; hObject
0x18008fd5f  call    cs:__imp_CloseHandle
0x18008fd65  mov     rcx, [rbp+38h]; this
0x18008fd69  test    eax, eax
0x18008fd6b  jz      loc_18008FF63
0x18008fd71  mov     ecx, r12d; dwErrCode
0x18008fd74  call    cs:__imp_SetLastError
0x18008fd7a  mov     [rbx+38h], r15
0x18008fd7e  mov     rax, [rbx]
0x18008fd81  mov     rcx, rbx
0x18008fd84  mov     rax, [rax+8]
0x18008fd88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fd8d  nop
0x18008fd8e  mov     rax, [rbx]
0x18008fd91  mov     rcx, rbx
0x18008fd94  mov     rax, [rax+10h]
0x18008fd98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fd9d  nop
0x18008fd9e  mov     rax, [r14]
0x18008fda1  mov     rdx, rbx
0x18008fda4  mov     rcx, r14
0x18008fda7  mov     rax, [rax+30h]
0x18008fdab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fdb0  mov     edi, eax
0x18008fdb2  test    eax, eax
0x18008fdb4  jns     short loc_18008FE35
0x18008fdb6  mov     rcx, [rbp+38h]; this
0x18008fdba  mov     r9d, eax; char *
0x18008fdbd  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18008fdc4  mov     edx, 649h; void *
0x18008fdc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008fdce  nop
0x18008fdcf  mov     rcx, [rbx]
0x18008fdd2  mov     rax, [rcx+10h]
0x18008fdd6  mov     rcx, rbx
0x18008fdd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fdde  nop
0x18008fddf  jmp     short loc_18008FE2E
0x18008fde1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18008fde6  mov     edi, eax
0x18008fde8  test    eax, eax
0x18008fdea  jns     short loc_18008FD7E
0x18008fdec  mov     rcx, [rbp+38h]; this
0x18008fdf0  mov     r9d, eax; char *
0x18008fdf3  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18008fdfa  mov     edx, 62Bh; void *
0x18008fdff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008fe04  nop
0x18008fe05  mov     rax, [rbx]
0x18008fe08  mov     rcx, rbx
0x18008fe0b  mov     rax, [rax+10h]
0x18008fe0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fe14  nop
0x18008fe15  mov     rcx, [rbp+38h]; this
0x18008fe19  mov     r9d, edi; char *
0x18008fe1c  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18008fe23  mov     edx, 648h; void *
0x18008fe28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008fe2d  nop
0x18008fe2e  mov     eax, edi
0x18008fe30  jmp     loc_18008FF54
0x18008fe35  mov     rax, [rbx+38h]
0x18008fe39  mov     [rbp+pHandles], rax
0x18008fe3d  mov     [rbp+dwindex], 0
0x18008fe44  lea     rax, [rbp+dwindex]
0x18008fe48  mov     qword ptr [rsp+40h+lpdwindex], rax; int
0x18008fe4d  lea     r9, [rbp+pHandles]; pHandles
0x18008fe51  mov     edx, 2710h; dwTimeout
0x18008fe56  mov     ecx, 8; dwFlags
0x18008fe5b  lea     r8d, [rcx-7]; cHandles
0x18008fe5f  call    cs:__imp_CoWaitForMultipleHandles
0x18008fe65  mov     edi, eax
0x18008fe67  test    rsi, rsi
0x18008fe6a  jz      short loc_18008FE8B
0x18008fe6c  cmp     eax, 80010115h
0x18008fe71  jnz     short loc_18008FE8B
0x18008fe73  mov     byte ptr [rsi], 1
0x18008fe76  mov     rax, [rbx]
0x18008fe79  mov     rcx, rbx
0x18008fe7c  mov     rax, [rax+10h]
0x18008fe80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fe85  nop
0x18008fe86  jmp     loc_18008FF52
0x18008fe8b  test    edi, edi
0x18008fe8d  jns     short loc_18008FEBD
0x18008fe8f  mov     rcx, [rbp+38h]; this
0x18008fe93  mov     r9d, edi; char *
0x18008fe96  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18008fe9d  mov     edx, 655h; void *
0x18008fea2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008fea7  nop
0x18008fea8  mov     rax, [rbx]
0x18008feab  mov     rcx, rbx
0x18008feae  mov     rax, [rax+10h]
0x18008feb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008feb7  nop
0x18008feb8  jmp     loc_18008FE2E
0x18008febd  mov     eax, [rbx+30h]
0x18008fec0  cmp     eax, 1
0x18008fec3  jz      short loc_18008FF42
0x18008fec5  mov     [rbp+arg_18], 0
0x18008fecd  mov     rax, [r14]
0x18008fed0  lea     r8, [rbp+arg_18]
0x18008fed4  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18008fedb  mov     rcx, r14
0x18008fede  mov     rax, [rax]
0x18008fee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fee6  mov     edi, eax
0x18008fee8  test    eax, eax
0x18008feea  js      short loc_18008FF0F
0x18008feec  mov     [rbp+arg_10], 8000FFFFh
0x18008fef3  mov     rcx, [rbp+arg_18]
0x18008fef7  mov     rax, [rcx]
0x18008fefa  lea     rdx, [rbp+arg_10]
0x18008fefe  mov     rax, [rax+40h]
0x18008ff02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ff07  mov     edi, eax
0x18008ff09  test    eax, eax
0x18008ff0b  cmovns  edi, [rbp+arg_10]
0x18008ff0f  mov     rcx, [rbp+arg_18]
0x18008ff13  test    rcx, rcx
0x18008ff16  jz      short loc_18008FF2D
0x18008ff18  mov     [rbp+arg_18], 0
0x18008ff20  mov     rax, [rcx]
0x18008ff23  mov     rax, [rax+10h]
0x18008ff27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ff2c  nop
0x18008ff2d  mov     rax, [rbx]
0x18008ff30  mov     rcx, rbx
0x18008ff33  mov     rax, [rax+10h]
0x18008ff37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ff3c  nop
0x18008ff3d  jmp     loc_18008FE2E
0x18008ff42  mov     rax, [rbx]
0x18008ff45  mov     rcx, rbx
0x18008ff48  mov     rax, [rax+10h]
0x18008ff4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ff51  nop
0x18008ff52  xor     eax, eax
0x18008ff54  add     rsp, 40h
0x18008ff58  pop     r15
0x18008ff5a  pop     r14
0x18008ff5c  pop     r12
0x18008ff5e  pop     rdi
0x18008ff5f  pop     rsi
0x18008ff60  pop     rbx
0x18008ff61  pop     rbp
0x18008ff62  retn
0x18008ff63  mov     edx, 0A0Bh; void *
0x18008ff68  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
