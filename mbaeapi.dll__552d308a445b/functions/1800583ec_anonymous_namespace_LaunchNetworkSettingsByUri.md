# _anonymous_namespace_::LaunchNetworkSettingsByUri

- ea: `0x1800583ec`
- end: `0x180058728`
- name: `_anonymous_namespace_::LaunchNetworkSettingsByUri`
- size: `828`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800295d0`

## callees

- `0x1800024e0`
- `0x18000401c`
- `0x180013354`
- `0x1800583ec`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18005857e`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18005857e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058590`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058590`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180058669`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180058669`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180058658`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180058658`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180058460`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180058513`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180058460`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180058513`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180058427`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800584da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180058427`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800584da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180058490`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180058490`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058476`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800586db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058476`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800586db`

## string_xrefs

- `0x180058419`: `Windows.Foundation.Uri`

## pseudocode

```c
__int64 anonymous_namespace_::LaunchNetworkSettingsByUri()
{
  HRESULT v0; // eax
  int v1; // edx
  unsigned int v2; // r8d
  int ActivationFactory; // eax
  int v4; // ebx
  HRESULT v5; // eax
  int v6; // edx
  unsigned int v7; // r8d
  HANDLE v8; // rbx
  signed int LastError; // eax
  _QWORD *v10; // rax
  _QWORD *v11; // rdi
  struct Microsoft::WRL::Details::ModuleBase *v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 (__fastcall ***v15)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 (__fastcall ***v19)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-39h] BYREF
  __int64 v20; // [rsp+38h] [rbp-31h] BYREF
  HANDLE pHandles; // [rsp+40h] [rbp-29h] BYREF
  HSTRING v22; // [rsp+48h] [rbp-21h] BYREF
  __int64 v23; // [rsp+50h] [rbp-19h] BYREF
  __int64 v24; // [rsp+58h] [rbp-11h] BYREF
  __int64 v25; // [rsp+60h] [rbp-9h] BYREF
  DWORD dwindex; // [rsp+68h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+7h] BYREF
  HSTRING string; // [rsp+88h] [rbp+1Fh] BYREF

  v20 = 0;
  string = 0;
  v0 = WindowsCreateStringReference(L"Windows.Foundation.Uri", 0x16u, &hstringHeader, &string);
  if ( v0 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v0, v1, v2);
    JUMPOUT(0x180058727LL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v20);
  string = 0;
  v4 = ActivationFactory;
  v22 = 0;
  if ( ActivationFactory >= 0 )
  {
    WindowsDeleteString(0);
    v22 = 0;
    v4 = WindowsCreateString(L"ms-settings:network-cellular", 0x1Cu, &v22);
  }
  v25 = 0;
  if ( v4 >= 0 )
    v4 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v20 + 48LL))(v20, v22, &v25);
  v19 = 0;
  if ( v4 >= 0 )
  {
    string = 0;
    v5 = WindowsCreateStringReference(L"Windows.System.Launcher", 0x17u, &hstringHeader, &string);
    if ( v5 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v5, v6, v7);
      __debugbreak();
    }
    v4 = RoGetActivationFactory(string, &GUID_00000035_0000_0000_c000_000000000046, &v19);
    string = 0;
  }
  v24 = 0;
  if ( v4 >= 0 )
    v4 = (**v19)(v19, &GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451, &v24);
  v23 = 0;
  if ( v4 >= 0 )
    v4 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v24 + 64LL))(v24, v25, &v23);
  pHandles = 0;
  if ( v4 >= 0 )
  {
    pHandles = CreateEventExW(0, 0, 0, 0x1F0003u);
    v8 = pHandles;
    if ( !pHandles )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( v4 < 0 )
        goto LABEL_28;
      v8 = pHandles;
    }
    v10 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
    v11 = v10;
    if ( v10 )
    {
      v12 = Microsoft::WRL::Details::ModuleBase::module_;
      *v10 = &Windows::Foundation::IAsyncOperationCompletedHandler<bool>::`vftable';
      *v10 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::`vftable';
      *((_DWORD *)v10 + 3) = 1;
      if ( v12 )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v12 + 8LL))(v12);
      v11[2] = v8;
      *v11 = off_18005F7C8;
    }
    else
    {
      v11 = 0;
    }
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v23 + 48LL))(v23, v11);
    if ( v11 )
      (*(void (__fastcall **)(_QWORD *))(*v11 + 16LL))(v11);
    if ( v4 >= 0 )
    {
      dwindex = 0;
      v4 = CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
    }
LABEL_28:
    if ( pHandles )
    {
      CloseHandle(pHandles);
      pHandles = 0;
    }
  }
  v13 = v23;
  if ( v23 )
  {
    v23 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  v14 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  v15 = v19;
  if ( v19 )
  {
    v19 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v15)[2])(v15);
  }
  v16 = v25;
  if ( v25 )
  {
    v25 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  WindowsDeleteString(v22);
  v17 = v20;
  v22 = 0;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800583ec  push    rbp
0x1800583ee  push    rbx
0x1800583ef  push    rsi
0x1800583f0  push    rdi
0x1800583f1  lea     rbp, [rsp-3Fh]
0x1800583f6  sub     rsp, 0A8h
0x1800583fd  mov     rax, cs:__security_cookie
0x180058404  xor     rax, rsp
0x180058407  mov     [rbp+57h+var_30], rax
0x18005840b  xor     esi, esi
0x18005840d  lea     r9, [rbp+57h+string]; string
0x180058411  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180058415  mov     [rbp+57h+var_88], rsi
0x180058419  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x180058420  mov     [rbp+57h+string], rsi
0x180058424  lea     edx, [rsi+16h]; length
0x180058427  call    cs:__imp_WindowsCreateStringReference
0x18005842d  test    eax, eax
0x18005842f  js      loc_180058720
0x180058435  mov     rcx, [rbp+57h+var_88]
0x180058439  mov     rbx, [rbp+57h+string]
0x18005843d  test    rcx, rcx
0x180058440  jz      short loc_180058452
0x180058442  mov     [rbp+57h+var_88], rsi
0x180058446  mov     rax, [rcx]
0x180058449  mov     rax, [rax+10h]
0x18005844d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058452  lea     r8, [rbp+57h+var_88]
0x180058456  mov     rcx, rbx
0x180058459  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x180058460  call    cs:__imp_RoGetActivationFactory
0x180058466  mov     [rbp+57h+string], rsi
0x18005846a  mov     ebx, eax
0x18005846c  mov     [rbp+57h+var_78], rsi
0x180058470  test    eax, eax
0x180058472  js      short loc_180058498
0x180058474  xor     ecx, ecx; string
0x180058476  call    cs:__imp_WindowsDeleteString
0x18005847c  lea     r8, [rbp+57h+var_78]; string
0x180058480  mov     [rbp+57h+var_78], rsi
0x180058484  mov     edx, 1Ch; length
0x180058489  lea     rcx, sourceString; "ms-settings:network-cellular"
0x180058490  call    cs:__imp_WindowsCreateString
0x180058496  mov     ebx, eax
0x180058498  mov     [rbp+57h+var_60], rsi
0x18005849c  test    ebx, ebx
0x18005849e  js      short loc_1800584BA
0x1800584a0  mov     rcx, [rbp+57h+var_88]
0x1800584a4  lea     r8, [rbp+57h+var_60]
0x1800584a8  mov     rdx, [rbp+57h+var_78]
0x1800584ac  mov     rax, [rcx]
0x1800584af  mov     rax, [rax+30h]
0x1800584b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800584b8  mov     ebx, eax
0x1800584ba  mov     [rbp+57h+var_90], rsi
0x1800584be  test    ebx, ebx
0x1800584c0  js      short loc_18005851F
0x1800584c2  lea     r9, [rbp+57h+string]; string
0x1800584c6  mov     [rbp+57h+string], rsi
0x1800584ca  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800584ce  mov     edx, 17h; length
0x1800584d3  lea     rcx, ?RuntimeClass_Windows_System_Launcher@@3QBGB; "Windows.System.Launcher"
0x1800584da  call    cs:__imp_WindowsCreateStringReference
0x1800584e0  test    eax, eax
0x1800584e2  js      loc_180058718
0x1800584e8  mov     rcx, [rbp+57h+var_90]
0x1800584ec  mov     rbx, [rbp+57h+string]
0x1800584f0  test    rcx, rcx
0x1800584f3  jz      short loc_180058505
0x1800584f5  mov     [rbp+57h+var_90], rsi
0x1800584f9  mov     rax, [rcx]
0x1800584fc  mov     rax, [rax+10h]
0x180058500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058505  lea     r8, [rbp+57h+var_90]
0x180058509  mov     rcx, rbx
0x18005850c  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x180058513  call    cs:__imp_RoGetActivationFactory
0x180058519  mov     ebx, eax
0x18005851b  mov     [rbp+57h+string], rsi
0x18005851f  mov     [rbp+57h+var_68], rsi
0x180058523  test    ebx, ebx
0x180058525  js      short loc_180058543
0x180058527  mov     rcx, [rbp+57h+var_90]
0x18005852b  lea     r8, [rbp+57h+var_68]
0x18005852f  lea     rdx, _GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451
0x180058536  mov     rax, [rcx]
0x180058539  mov     rax, [rax]
0x18005853c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058541  mov     ebx, eax
0x180058543  mov     [rbp+57h+var_70], rsi
0x180058547  test    ebx, ebx
0x180058549  js      short loc_180058565
0x18005854b  mov     rcx, [rbp+57h+var_68]
0x18005854f  lea     r8, [rbp+57h+var_70]
0x180058553  mov     rdx, [rbp+57h+var_60]
0x180058557  mov     rax, [rcx]
0x18005855a  mov     rax, [rax+40h]
0x18005855e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058563  mov     ebx, eax
0x180058565  mov     [rbp+57h+pHandles], rsi
0x180058569  test    ebx, ebx
0x18005856b  js      loc_180058673
0x180058571  mov     r9d, 1F0003h; dwDesiredAccess
0x180058577  xor     r8d, r8d; dwFlags
0x18005857a  xor     edx, edx; lpName
0x18005857c  xor     ecx, ecx; lpEventAttributes
0x18005857e  call    cs:__imp_CreateEventExW
0x180058584  mov     [rbp+57h+pHandles], rax
0x180058588  mov     rbx, rax
0x18005858b  test    rax, rax
0x18005858e  jnz     short loc_1800585B1
0x180058590  call    cs:__imp_GetLastError
0x180058596  mov     ebx, eax
0x180058598  test    eax, eax
0x18005859a  jle     short loc_1800585A5
0x18005859c  movzx   ebx, ax
0x18005859f  or      ebx, 80070000h
0x1800585a5  test    ebx, ebx
0x1800585a7  js      loc_180058660
0x1800585ad  mov     rbx, [rbp+57h+pHandles]
0x1800585b1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800585b8  mov     ecx, 18h; unsigned __int64
0x1800585bd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800585c2  mov     rdi, rax
0x1800585c5  test    rax, rax
0x1800585c8  jz      short loc_18005860D
0x1800585ca  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800585d1  lea     rax, ??_7?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<bool>::`vftable'
0x1800585d8  mov     [rdi], rax
0x1800585db  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::`vftable'
0x1800585e2  mov     [rdi], rax
0x1800585e5  mov     dword ptr [rdi+0Ch], 1
0x1800585ec  test    rcx, rcx
0x1800585ef  jz      short loc_1800585FD
0x1800585f1  mov     rax, [rcx]
0x1800585f4  mov     rax, [rax+8]
0x1800585f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800585fd  lea     rax, off_18005F7C8
0x180058604  mov     [rdi+10h], rbx
0x180058608  mov     [rdi], rax
0x18005860b  jmp     short loc_180058610
0x18005860d  mov     rdi, rsi
0x180058610  mov     rcx, [rbp+57h+var_70]
0x180058614  mov     rdx, rdi
0x180058617  mov     rax, [rcx]
0x18005861a  mov     rax, [rax+30h]
0x18005861e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058623  mov     ebx, eax
0x180058625  test    rdi, rdi
0x180058628  jz      short loc_180058639
0x18005862a  mov     rax, [rdi]
0x18005862d  mov     rcx, rdi
0x180058630  mov     rax, [rax+10h]
0x180058634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058639  test    ebx, ebx
0x18005863b  js      short loc_180058660
0x18005863d  lea     rax, [rbp+57h+dwindex]
0x180058641  mov     [rbp+57h+dwindex], esi
0x180058644  lea     r9, [rbp+57h+pHandles]; pHandles
0x180058648  mov     [rsp+0C0h+lpdwindex], rax; lpdwindex
0x18005864d  mov     r8d, 1; cHandles
0x180058653  or      edx, 0FFFFFFFFh; dwTimeout
0x180058656  xor     ecx, ecx; dwFlags
0x180058658  call    cs:__imp_CoWaitForMultipleHandles
0x18005865e  mov     ebx, eax
0x180058660  mov     rcx, [rbp+57h+pHandles]; hObject
0x180058664  test    rcx, rcx
0x180058667  jz      short loc_180058673
0x180058669  call    cs:__imp_CloseHandle
0x18005866f  mov     [rbp+57h+pHandles], rsi
0x180058673  mov     rcx, [rbp+57h+var_70]
0x180058677  test    rcx, rcx
0x18005867a  jz      short loc_18005868C
0x18005867c  mov     [rbp+57h+var_70], rsi
0x180058680  mov     rax, [rcx]
0x180058683  mov     rax, [rax+10h]
0x180058687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005868c  mov     rcx, [rbp+57h+var_68]
0x180058690  test    rcx, rcx
0x180058693  jz      short loc_1800586A5
0x180058695  mov     [rbp+57h+var_68], rsi
0x180058699  mov     rax, [rcx]
0x18005869c  mov     rax, [rax+10h]
0x1800586a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800586a5  mov     rcx, [rbp+57h+var_90]
0x1800586a9  test    rcx, rcx
0x1800586ac  jz      short loc_1800586BE
0x1800586ae  mov     [rbp+57h+var_90], rsi
0x1800586b2  mov     rax, [rcx]
0x1800586b5  mov     rax, [rax+10h]
0x1800586b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800586be  mov     rcx, [rbp+57h+var_60]
0x1800586c2  test    rcx, rcx
0x1800586c5  jz      short loc_1800586D7
0x1800586c7  mov     [rbp+57h+var_60], rsi
0x1800586cb  mov     rax, [rcx]
0x1800586ce  mov     rax, [rax+10h]
0x1800586d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800586d7  mov     rcx, [rbp+57h+var_78]; string
0x1800586db  call    cs:__imp_WindowsDeleteString
0x1800586e1  mov     rcx, [rbp+57h+var_88]
0x1800586e5  mov     [rbp+57h+var_78], rsi
0x1800586e9  test    rcx, rcx
0x1800586ec  jz      short loc_1800586FE
0x1800586ee  mov     [rbp+57h+var_88], rsi
0x1800586f2  mov     rax, [rcx]
0x1800586f5  mov     rax, [rax+10h]
0x1800586f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800586fe  mov     eax, ebx
0x180058700  mov     rcx, [rbp+57h+var_30]
0x180058704  xor     rcx, rsp; StackCookie
0x180058707  call    __security_check_cookie
0x18005870c  add     rsp, 0A8h
0x180058713  pop     rdi
0x180058714  pop     rsi
0x180058715  pop     rbx
0x180058716  pop     rbp
0x180058717  retn
0x180058718  mov     ecx, eax; this
0x18005871a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18005871f  int     3; Trap to Debugger
0x180058720  mov     ecx, eax; this
0x180058722  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
