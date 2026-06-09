# CoreDispatcherInterop::~CoreDispatcherInterop(void)

- ea: `0x180063ea0`
- end: `0x180063f1e`
- name: `??1CoreDispatcherInterop@@UEAA@XZ`
- size: `126`
- prototype: `void __fastcall(CoreDispatcherInterop *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180063f70`

## callees

- `0x180011028`
- `0x180018b30`
- `0x180063e40`
- `0x180063ea0`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180063eda`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180063eda`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x180063ec2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x180063ec2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180063f0b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180063f0b`

## pseudocode

```c
void __fastcall CoreDispatcherInterop::~CoreDispatcherInterop(CoreDispatcherInterop *this)
{
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_QWORD *)this = &CoreDispatcherInterop::`vftable'{for `Windows::UI::Core::ICoreDispatcher'};
  *((_QWORD *)this + 1) = &CoreDispatcherInterop::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'};
  if ( IsWindow(*((HWND *)this + 4)) )
    SendMessageW(*((HWND *)this + 4), 0x10u, 0, 0);
  if ( *((_QWORD *)this + 4) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webviewcontrol\\coredispatcherinterop.cpp",
      v2);
  std::deque<Microsoft::WRL::ComPtr<CoreDispatcherInterop::AsyncActionInterop>>::~deque<Microsoft::WRL::ComPtr<CoreDispatcherInterop::AsyncActionInterop>>((char *)this + 80);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::ApplicationModel::Core::IFrameworkViewSource>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::ApplicationModel::Core::IFrameworkViewSource>(this);
}

```

## disassembly

```asm
0x180063ea0  push    rbx
0x180063ea2  sub     rsp, 20h
0x180063ea6  lea     rax, ??_7CoreDispatcherInterop@@6BICoreDispatcher@Core@UI@Windows@@@; const CoreDispatcherInterop::`vftable'{for `Windows::UI::Core::ICoreDispatcher'}
0x180063ead  mov     rbx, rcx
0x180063eb0  mov     [rcx], rax
0x180063eb3  lea     rax, ??_7CoreDispatcherInterop@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@WRL@Microsoft@@@; const CoreDispatcherInterop::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'}
0x180063eba  mov     [rcx+8], rax
0x180063ebe  mov     rcx, [rcx+20h]; hWnd
0x180063ec2  call    cs:__imp_IsWindow
0x180063ec8  test    eax, eax
0x180063eca  jz      short loc_180063EE0
0x180063ecc  mov     rcx, [rbx+20h]; hWnd
0x180063ed0  xor     r9d, r9d; lParam
0x180063ed3  xor     r8d, r8d; wParam
0x180063ed6  lea     edx, [r9+10h]; Msg
0x180063eda  call    cs:__imp_SendMessageW
0x180063ee0  cmp     qword ptr [rbx+20h], 0
0x180063ee5  jz      short loc_180063EFE
0x180063ee7  mov     rcx, [rsp+28h]; this
0x180063eec  lea     r8, aOnecoreuapInet_22; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180063ef3  mov     edx, 1Bh; void *
0x180063ef8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180063efe  lea     rcx, [rbx+50h]
0x180063f02  call    ??1?$deque@V?$ComPtr@VAsyncActionInterop@CoreDispatcherInterop@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VAsyncActionInterop@CoreDispatcherInterop@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::deque<Microsoft::WRL::ComPtr<CoreDispatcherInterop::AsyncActionInterop>>::~deque<Microsoft::WRL::ComPtr<CoreDispatcherInterop::AsyncActionInterop>>(void)
0x180063f07  lea     rcx, [rbx+28h]; lpCriticalSection
0x180063f0b  call    cs:__imp_DeleteCriticalSection
0x180063f11  mov     rcx, rbx
0x180063f14  add     rsp, 20h
0x180063f18  pop     rbx
0x180063f19  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIFrameworkViewSource@Core@ApplicationModel@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::ApplicationModel::Core::IFrameworkViewSource>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::ApplicationModel::Core::IFrameworkViewSource>(void)
```
