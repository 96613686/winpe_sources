# _anonymous_namespace_::ShowMessageDialogAndGetUserSelection_Worker

- ea: `0x1800656a8`
- end: `0x180065bdb`
- name: `_anonymous_namespace_::ShowMessageDialogAndGetUserSelection_Worker`
- size: `1331`
- prototype: `HRESULT __fastcall(HWND__ *ParentWindow, const wchar_t *Content, const wchar_t *AllowCommandText, const wchar_t *DenyCommandText, bool *UserSelection)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800655e0`

## callees

- `0x180002790`
- `0x180012748`
- `0x180012770`
- `0x1800127cc`
- `0x1800128a4`
- `0x18005b4a4`
- `0x18005cd80`
- `0x1800644a0`
- `0x180064530`
- `0x180064700`
- `0x180064a5c`
- `0x1800656a8`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006577b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180065807`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800658a4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006577b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180065807`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800658a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180065762`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800657ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800658b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180065762`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800657ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800658b7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180065790`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180065790`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall anonymous_namespace_::ShowMessageDialogAndGetUserSelection_Worker(
        HWND__ *ParentWindow,
        const wchar_t *Content,
        const wchar_t *AllowCommandText,
        const wchar_t *DenyCommandText,
        Windows::UI::Popups::IUICommandInvokedHandler *UserSelection)
{
  WPP_PROJECT_CONTROL_BLOCK *v9; // rcx
  int ActivationFactory; // edi
  Windows::UI::Popups::IMessageDialogFactory *ptr; // rdi
  HRESULT (__fastcall *Create)(Windows::UI::Popups::IMessageDialogFactory *, HSTRING__ *, Windows::UI::Popups::IMessageDialog **); // rbx
  unsigned __int64 v13; // rbx
  Windows::UI::Popups::IMessageDialog *v14; // rbx
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rdi
  Windows::UI::Popups::IMessageDialog *v16; // rbx
  HRESULT (__fastcall *v17)(IUnknown *, const _GUID *, void **); // rdi
  Windows::UI::Popups::IMessageDialog *v18; // rdi
  HRESULT (__fastcall *get_Commands)(Windows::UI::Popups::IMessageDialog *, Windows::Foundation::Collections::IVector<Windows::UI::Popups::IUICommand *> **); // rbx
  Microsoft::WRL::ComPtr<Microsoft::WRL::Details::DelegateArgTraits<long (__cdecl Windows::UI::Popups::IUICommandInvokedHandler::*)(Windows::UI::Popups::IUICommand *)>::DelegateInvokeHelper<Windows::UI::Popups::IUICommandInvokedHandler,`ShowMessageDialogAndGetUserSelection_Worker'::`29'::<lambda_1>,-1,Windows::UI::Popups::IUICommand *> > *v20; // rax
  Windows::UI::Popups::IUICommandInvokedHandler *v21; // rbx
  IInitializeWithPopupPersonality *v22; // rcx
  Microsoft::WRL::ComPtr<Microsoft::WRL::Details::DelegateArgTraits<long (__cdecl Windows::UI::Popups::IUICommandInvokedHandler::*)(Windows::UI::Popups::IUICommand *)>::DelegateInvokeHelper<Windows::UI::Popups::IUICommandInvokedHandler,`ShowMessageDialogAndGetUserSelection_Worker'::`32'::<lambda_2>,-1,Windows::UI::Popups::IUICommand *> > *v23; // rax
  Windows::UI::Popups::IUICommandInvokedHandler *v24; // rbx
  IInitializeWithPopupPersonality *v25; // rcx
  Windows::UI::Popups::IMessageDialog *v26; // rdi
  HRESULT (__fastcall *ShowAsync)(Windows::UI::Popups::IMessageDialog *, Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> **); // rbx
  __int64 v28; // rdx
  void *v29; // r8
  Microsoft::WRL::ComPtr<Windows::UI::Popups::IUICommandInvokedHandler> spCallback; // [rsp+30h] [rbp-51h] BYREF
  Microsoft::WRL::ComPtr<IInitializeWithPopupPersonality> spIWPPMessageDialog; // [rsp+38h] [rbp-49h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Popups::IMessageDialog> spMessageDialog; // [rsp+40h] [rbp-41h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::UI::Popups::IUICommand *> > spCommands; // [rsp+48h] [rbp-39h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> > spMessageDialogAsyncOperation; // [rsp+50h] [rbp-31h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Popups::IMessageDialogFactory> spMessageDialogFactory; // [rsp+58h] [rbp-29h] BYREF
  Windows::Internal::StringReference messageContent; // [rsp+60h] [rbp-21h] BYREF

  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_SSS(
      WPP_GLOBAL_Control->Control.Logger,
      0xBu,
      WPP_58016a1fb6c83b3d634d8292d1366b43_Traceguids,
      Content,
      AllowCommandText,
      DenyCommandText);
    v9 = WPP_GLOBAL_Control;
  }
  spMessageDialogFactory.ptr_ = 0;
  if ( v9 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v9->ReserveSpace[28] & 0x10) != 0 )
    WPP_SF_(v9->Control.Logger, 0xCu, WPP_58016a1fb6c83b3d634d8292d1366b43_Traceguids);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)&spMessageDialogFactory);
  if ( WindowsCreateStringReference(
         RuntimeClass_Windows_UI_Popups_MessageDialog,
         0x1Fu,
         &messageContent._header,
         &messageContent._hstring) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(
                        messageContent._hstring,
                        &GUID_2d161777_a66f_4ea5_bb87_793ffa4941f2,
                        &spMessageDialogFactory);
  spMessageDialog.ptr_ = 0;
  if ( ActivationFactory >= 0 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xDu, WPP_58016a1fb6c83b3d634d8292d1366b43_Traceguids);
    }
    memset(&messageContent, 0, sizeof(messageContent));
    if ( WindowsCreateStringReference(&sourceString, 0, &messageContent._header, &messageContent._hstring) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    ptr = spMessageDialogFactory.ptr_;
    Create = spMessageDialogFactory.ptr_->Create;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)&spMessageDialog);
    ActivationFactory = Create(ptr, messageContent._hstring, &spMessageDialog.ptr_);
    if ( ActivationFactory >= 0 )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
      {
        WPP_SF_S(WPP_GLOBAL_Control->Control.Logger, 0xEu, WPP_58016a1fb6c83b3d634d8292d1366b43_Traceguids, Content);
      }
      memset(&messageContent, 0, sizeof(messageContent));
      v13 = -1;
      do
        ++v13;
      while ( Content[v13] );
      if ( v13 > 0xFFFFFFFF )
      {
        LODWORD(v13) = -1;
        RaiseException(0xC000000D, 1u, 0, 0);
      }
      WindowsCreateStringReference(Content, v13, &messageContent._header, &messageContent._hstring);
      ActivationFactory = spMessageDialog.ptr_->put_Content(spMessageDialog.ptr_, messageContent._hstring);
      if ( ActivationFactory >= 0 )
      {
        if ( !ParentWindow )
          goto LABEL_31;
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xFu, WPP_58016a1fb6c83b3d634d8292d1366b43_Traceguids);
        }
        spIWPPMessageDialog.ptr_ = 0;
        v14 = spMessageDialog.ptr_;
        QueryInterface = spMessageDialog.ptr_->QueryInterface;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)&spIWPPMessageDialog);
        ActivationFactory = QueryInterface(
                              v14,
                              &GUID_3e68d4bd_7135_4d10_8018_9fb6d9f33fa1,
                              (void **)&spIWPPMessageDialog.ptr_);
        if ( ActivationFactory >= 0 )
          ActivationFactory = spIWPPMessageDialog.ptr_->Initialize(
                                spIWPPMessageDialog.ptr_,
                                (POPUP_PERSONALITY)ParentWindow);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)&spIWPPMessageDialog);
        if ( ActivationFactory >= 0 )
        {
LABEL_31:
          spIWPPMessageDialog.ptr_ = 0;
          v16 = spMessageDialog.ptr_;
          v17 = spMessageDialog.ptr_->QueryInterface;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)&spIWPPMessageDialog);
          ActivationFactory = v17(v16, &GUID_6a193f22_6d3e_4803_b595_a581906c929b, (void **)&spIWPPMessageDialog.ptr_);
          if ( ActivationFactory >= 0 )
            ActivationFactory = spIWPPMessageDialog.ptr_->Initialize(spIWPPMessageDialog.ptr_, POPUP_PERSONALITY_SYSTEM);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)&spIWPPMessageDialog);
        }
      }
    }
  }
  spCommands.ptr_ = 0;
  if ( ActivationFactory >= 0 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x10u, WPP_58016a1fb6c83b3d634d8292d1366b43_Traceguids);
    }
    v18 = spMessageDialog.ptr_;
    get_Commands = spMessageDialog.ptr_->get_Commands;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)&spCommands);
    ActivationFactory = get_Commands(v18, &spCommands.ptr_);
  }
  LOBYTE(UserSelection->__vftable) = 0;
  if ( ActivationFactory >= 0 )
  {
    spCallback.ptr_ = UserSelection;
    v20 = Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::UI::Popups::IUICommandInvokedHandler::___Windows::UI::Popups::IUICommand____::DelegateInvokeHelper_Windows::UI::Popups::IUICommandInvokedHandler___anonymous_namespace_::ShowMessageDialogAndGetUserSelection_Worker_::_29_::_lambda_1___1_Windows::UI::Popups::IUICommand______anonymous_namespace_::ShowMessageDialogAndGetUserSelection_Worker_::_29_::_lambda_1___(
            (Microsoft::WRL::ComPtr<Microsoft::WRL::Details::DelegateArgTraits<long (__cdecl Windows::UI::Popups::IUICommandInvokedHandler::*)(Windows::UI::Popups::IUICommand *)>::DelegateInvokeHelper<Windows::UI::Popups::IUICommandInvokedHandler,`ShowMessageDialogAndGetUserSelection_Worker'::`29'::<lambda_1>,-1,Windows::UI::Popups::IUICommand *> > *)&spIWPPMessageDialog,
            (ShowMessageDialogAndGetUserSelection_Worker::__l29::<lambda_1> *)&spCallback);
    v21 = v20->ptr_;
    spCallback.ptr_ = v20->ptr_;
    v20->ptr_ = 0;
    v22 = spIWPPMessageDialog.ptr_;
    if ( spIWPPMessageDialog.ptr_ )
    {
      spIWPPMessageDialog.ptr_ = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::UI::Popups::IUICommandInvokedHandler>::Release((Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::UI::Popups::IUICommandInvokedHandler> *)v22);
    }
    ActivationFactory = anonymous_namespace_::AddDialogCommand(spCommands.ptr_, AllowCommandText, v21);
    if ( v21 )
      v21->Release(v21);
    if ( ActivationFactory >= 0 )
    {
      spCallback.ptr_ = UserSelection;
      v23 = Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::UI::Popups::IUICommandInvokedHandler::___Windows::UI::Popups::IUICommand____::DelegateInvokeHelper_Windows::UI::Popups::IUICommandInvokedHandler___anonymous_namespace_::ShowMessageDialogAndGetUserSelection_Worker_::_32_::_lambda_2___1_Windows::UI::Popups::IUICommand______anonymous_namespace_::ShowMessageDialogAndGetUserSelection_Worker_::_32_::_lambda_2___(
              (Microsoft::WRL::ComPtr<Microsoft::WRL::Details::DelegateArgTraits<long (__cdecl Windows::UI::Popups::IUICommandInvokedHandler::*)(Windows::UI::Popups::IUICommand *)>::DelegateInvokeHelper<Windows::UI::Popups::IUICommandInvokedHandler,`ShowMessageDialogAndGetUserSelection_Worker'::`32'::<lambda_2>,-1,Windows::UI::Popups::IUICommand *> > *)&spIWPPMessageDialog,
              (ShowMessageDialogAndGetUserSelection_Worker::__l32::<lambda_2> *)&spCallback);
      v24 = v23->ptr_;
      spCallback.ptr_ = v23->ptr_;
      v23->ptr_ = 0;
      v25 = spIWPPMessageDialog.ptr_;
      if ( spIWPPMessageDialog.ptr_ )
      {
        spIWPPMessageDialog.ptr_ = 0;
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::UI::Popups::IUICommandInvokedHandler>::Release((Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::UI::Popups::IUICommandInvokedHandler> *)v25);
      }
      ActivationFactory = anonymous_namespace_::AddDialogCommand(spCommands.ptr_, DenyCommandText, v24);
      if ( v24 )
        v24->Release(v24);
    }
  }
  spMessageDialogAsyncOperation.ptr_ = 0;
  if ( ActivationFactory >= 0 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x13u, WPP_58016a1fb6c83b3d634d8292d1366b43_Traceguids);
    }
    v26 = spMessageDialog.ptr_;
    ShowAsync = spMessageDialog.ptr_->ShowAsync;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)&spMessageDialogAsyncOperation);
    ActivationFactory = ShowAsync(v26, &spMessageDialogAsyncOperation.ptr_);
    if ( ActivationFactory >= 0 )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x14u, WPP_58016a1fb6c83b3d634d8292d1366b43_Traceguids);
      }
      ActivationFactory = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *>>(
                            spMessageDialogAsyncOperation.ptr_,
                            v28,
                            v29);
    }
  }
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->Control.Logger,
      0x15u,
      WPP_58016a1fb6c83b3d634d8292d1366b43_Traceguids,
      ActivationFactory);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)&spMessageDialogAsyncOperation);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)&spCommands);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)&spMessageDialog);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)&spMessageDialogFactory);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x1800656a8  push    rbp
0x1800656aa  push    rbx
0x1800656ab  push    rsi
0x1800656ac  push    rdi
0x1800656ad  push    r12
0x1800656af  push    r13
0x1800656b1  push    r14
0x1800656b3  push    r15
0x1800656b5  lea     rbp, [rsp-17h]
0x1800656ba  sub     rsp, 98h
0x1800656c1  mov     rax, cs:__security_cookie
0x1800656c8  xor     rax, rsp
0x1800656cb  mov     [rbp+4Fh+var_50], rax
0x1800656cf  mov     r13, DenyCommandText
0x1800656d2  mov     r12, AllowCommandText
0x1800656d5  mov     rsi, Content
0x1800656d8  mov     r14, ParentWindow
0x1800656db  mov     r15, [rbp+4Fh+arg_20]
0x1800656df  lea     rdi, WPP_GLOBAL_Control; __annotation("TMF:",
0x1800656e6  mov     ParentWindow, cs:WPP_GLOBAL_Control
0x1800656ed  cmp     ParentWindow, rdi
0x1800656f0  jz      short loc_180065721
0x1800656f2  test    byte ptr [ParentWindow+1Ch], 10h
0x1800656f6  jz      short loc_180065721
0x1800656f8  mov     edx, 0Bh; id
0x1800656fd  mov     [rsp+0D0h+_a3], DenyCommandText; _a3
0x180065702  mov     [rsp+0D0h+_a2], AllowCommandText; _a2
0x180065707  mov     DenyCommandText, rsi; _a1
0x18006570a  lea     AllowCommandText, WPP_58016a1fb6c83b3d634d8292d1366b43_Traceguids; TraceGuid
0x180065711  mov     ParentWindow, [ParentWindow+10h]; Logger
0x180065715  call    WPP_SF_SSS
0x18006571a  mov     ParentWindow, cs:WPP_GLOBAL_Control
0x180065721  xor     ebx, ebx
0x180065723  mov     [rbp+4Fh+spMessageDialogFactory.ptr_], rbx
0x180065727  cmp     ParentWindow, rdi; __annotation("TMF:",
0x18006572a  jz      short loc_180065745
0x18006572c  test    byte ptr [ParentWindow+1Ch], 10h
0x180065730  jz      short loc_180065745
0x180065732  lea     edx, [rbx+0Ch]; id
0x180065735  lea     AllowCommandText, WPP_58016a1fb6c83b3d634d8292d1366b43_Traceguids; TraceGuid
0x18006573c  mov     ParentWindow, [ParentWindow+10h]; Logger
0x180065740  call    WPP_SF_
0x180065745  lea     ParentWindow, [rbp+4Fh+spMessageDialogFactory]; this
0x180065749  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006574e  lea     DenyCommandText, [rbp+4Fh+messageContent]; string
0x180065752  lea     AllowCommandText, [rbp+4Fh+messageContent._header]; hstringHeader
0x180065756  mov     edx, 1Fh; length
0x18006575b  lea     ParentWindow, ?RuntimeClass_Windows_UI_Popups_MessageDialog@@3QBGB; sourceString
0x180065762  call    cs:__imp_WindowsCreateStringReference
0x180065768  test    eax, eax
0x18006576a  jns     short loc_180065781
0x18006576c  xor     r9d, r9d; lpArguments
0x18006576f  xor     r8d, r8d; nNumberOfArguments
0x180065772  lea     edx, [DenyCommandText+1]; dwExceptionFlags
0x180065776  mov     ecx, 0C000000Dh; dwExceptionCode
0x18006577b  call    cs:__imp_RaiseException
0x180065781  lea     AllowCommandText, [rbp+4Fh+spMessageDialogFactory]
0x180065785  lea     Content, _GUID_2d161777_a66f_4ea5_bb87_793ffa4941f2
0x18006578c  mov     ParentWindow, [rbp+4Fh+messageContent._hstring]
0x180065790  call    cs:__imp_RoGetActivationFactory
0x180065796  mov     edi, eax
0x180065798  mov     [rbp+4Fh+spMessageDialog.ptr_], rbx
0x18006579c  test    eax, eax
0x18006579e  js      loc_1800659BC
0x1800657a4  mov     ParentWindow, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800657ab  lea     rax, WPP_GLOBAL_Control
0x1800657b2  cmp     ParentWindow, rax
0x1800657b5  jz      short loc_1800657D2
0x1800657b7  test    byte ptr [ParentWindow+1Ch], 10h
0x1800657bb  jz      short loc_1800657D2
0x1800657bd  mov     edx, 0Dh; id
0x1800657c2  lea     AllowCommandText, WPP_58016a1fb6c83b3d634d8292d1366b43_Traceguids; TraceGuid
0x1800657c9  mov     ParentWindow, [ParentWindow+10h]; Logger
0x1800657cd  call    WPP_SF_
0x1800657d2  xorps   xmm0, xmm0
0x1800657d5  movups  xmmword ptr [rbp+4Fh+messageContent._hstring], xmm0
0x1800657d9  movups  xmmword ptr [rbp+4Fh+messageContent._header.Reserved+8], xmm0
0x1800657dd  lea     DenyCommandText, [rbp+4Fh+messageContent]; string
0x1800657e1  lea     AllowCommandText, [rbp+4Fh+messageContent._header]; hstringHeader
0x1800657e5  xor     edx, edx; length
0x1800657e7  lea     ParentWindow, sourceString; sourceString
0x1800657ee  call    cs:__imp_WindowsCreateStringReference
0x1800657f4  test    eax, eax
0x1800657f6  jns     short loc_18006580D
0x1800657f8  xor     r9d, r9d; lpArguments
0x1800657fb  xor     r8d, r8d; nNumberOfArguments
0x1800657fe  lea     edx, [DenyCommandText+1]; dwExceptionFlags
0x180065802  mov     ecx, 0C000000Dh; dwExceptionCode
0x180065807  call    cs:__imp_RaiseException
0x18006580d  mov     rdi, [rbp+4Fh+spMessageDialogFactory.ptr_]
0x180065811  mov     rax, [rdi]
0x180065814  mov     rbx, [rax+30h]
0x180065818  lea     ParentWindow, [rbp+4Fh+spMessageDialog]; this
0x18006581c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180065821  lea     AllowCommandText, [rbp+4Fh+spMessageDialog]
0x180065825  mov     Content, [rbp+4Fh+messageContent._hstring]
0x180065829  mov     ParentWindow, rdi
0x18006582c  mov     rax, rbx
0x18006582f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065834  mov     edi, eax
0x180065836  xor     eax, eax
0x180065838  test    edi, edi
0x18006583a  js      loc_1800659BC
0x180065840  mov     ParentWindow, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180065847  lea     Content, WPP_GLOBAL_Control
0x18006584e  cmp     ParentWindow, Content
0x180065851  jz      short loc_180065871
0x180065853  test    byte ptr [ParentWindow+1Ch], 10h
0x180065857  jz      short loc_180065871
0x180065859  lea     edx, [rax+0Eh]; id
0x18006585c  mov     DenyCommandText, rsi; _a1
0x18006585f  lea     AllowCommandText, WPP_58016a1fb6c83b3d634d8292d1366b43_Traceguids; TraceGuid
0x180065866  mov     ParentWindow, [ParentWindow+10h]; Logger
0x18006586a  call    WPP_SF_S
0x18006586f  xor     eax, eax
0x180065871  xorps   xmm0, xmm0
0x180065874  movups  xmmword ptr [rbp+4Fh+messageContent._hstring], xmm0
0x180065878  movups  xmmword ptr [rbp+4Fh+messageContent._header.Reserved+8], xmm0
0x18006587c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180065880  inc     rbx
0x180065883  cmp     [rsi+rbx*2], ax
0x180065887  jnz     short loc_180065880
0x180065889  mov     eax, 0FFFFFFFFh
0x18006588e  cmp     rbx, rax
0x180065891  jbe     short loc_1800658AA
0x180065893  mov     ebx, eax
0x180065895  xor     r9d, r9d; lpArguments
0x180065898  xor     r8d, r8d; nNumberOfArguments
0x18006589b  lea     edx, [DenyCommandText+1]; dwExceptionFlags
0x18006589f  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800658a4  call    cs:__imp_RaiseException
0x1800658aa  lea     DenyCommandText, [rbp+4Fh+messageContent]; string
0x1800658ae  lea     AllowCommandText, [rbp+4Fh+messageContent._header]; hstringHeader
0x1800658b2  mov     edx, ebx; length
0x1800658b4  mov     ParentWindow, rsi; sourceString
0x1800658b7  call    cs:__imp_WindowsCreateStringReference
0x1800658bd  mov     ParentWindow, [rbp+4Fh+spMessageDialog.ptr_]
0x1800658c1  mov     rax, [ParentWindow]
0x1800658c4  mov     Content, [rbp+4Fh+messageContent._hstring]
0x1800658c8  mov     rax, [rax+70h]
0x1800658cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800658d1  mov     edi, eax
0x1800658d3  xor     esi, esi
0x1800658d5  test    eax, eax
0x1800658d7  js      loc_1800659BE
0x1800658dd  test    r14, r14
0x1800658e0  jz      loc_180065967
0x1800658e6  mov     ParentWindow, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800658ed  lea     rax, WPP_GLOBAL_Control
0x1800658f4  cmp     ParentWindow, rax
0x1800658f7  jz      short loc_180065912
0x1800658f9  test    byte ptr [ParentWindow+1Ch], 10h
0x1800658fd  jz      short loc_180065912
0x1800658ff  lea     edx, [rsi+0Fh]; id
0x180065902  lea     AllowCommandText, WPP_58016a1fb6c83b3d634d8292d1366b43_Traceguids; TraceGuid
0x180065909  mov     ParentWindow, [ParentWindow+10h]; Logger
0x18006590d  call    WPP_SF_
0x180065912  mov     [rbp+4Fh+spIWPPMessageDialog.ptr_], rsi
0x180065916  mov     rbx, [rbp+4Fh+spMessageDialog.ptr_]
0x18006591a  mov     rax, [rbx]
0x18006591d  mov     rdi, [rax]
0x180065920  lea     ParentWindow, [rbp+4Fh+spIWPPMessageDialog]; this
0x180065924  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180065929  lea     AllowCommandText, [rbp+4Fh+spIWPPMessageDialog]
0x18006592d  lea     Content, _GUID_3e68d4bd_7135_4d10_8018_9fb6d9f33fa1
0x180065934  mov     ParentWindow, rbx
0x180065937  mov     rax, rdi
0x18006593a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006593f  mov     edi, eax
0x180065941  test    eax, eax
0x180065943  js      short loc_18006595A
0x180065945  mov     ParentWindow, [rbp+4Fh+spIWPPMessageDialog.ptr_]
0x180065949  mov     rax, [ParentWindow]
0x18006594c  mov     Content, r14
0x18006594f  mov     rax, [rax+18h]
0x180065953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065958  mov     edi, eax
0x18006595a  lea     ParentWindow, [rbp+4Fh+spIWPPMessageDialog]; this
0x18006595e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180065963  test    edi, edi
0x180065965  js      short loc_1800659BE
0x180065967  mov     [rbp+4Fh+spIWPPMessageDialog.ptr_], rsi
0x18006596b  mov     rbx, [rbp+4Fh+spMessageDialog.ptr_]
0x18006596f  mov     rax, [rbx]
0x180065972  mov     rdi, [rax]
0x180065975  lea     ParentWindow, [rbp+4Fh+spIWPPMessageDialog]; this
0x180065979  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006597e  lea     AllowCommandText, [rbp+4Fh+spIWPPMessageDialog]
0x180065982  lea     Content, _GUID_6a193f22_6d3e_4803_b595_a581906c929b
0x180065989  mov     ParentWindow, rbx
0x18006598c  mov     rax, rdi
0x18006598f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065994  mov     edi, eax
0x180065996  test    eax, eax
0x180065998  js      short loc_1800659B1
0x18006599a  mov     ParentWindow, [rbp+4Fh+spIWPPMessageDialog.ptr_]
0x18006599e  mov     rax, [ParentWindow]
0x1800659a1  mov     edx, 1
0x1800659a6  mov     rax, [rax+18h]
0x1800659aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800659af  mov     edi, eax
0x1800659b1  lea     ParentWindow, [rbp+4Fh+spIWPPMessageDialog]; this
0x1800659b5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800659ba  jmp     short loc_1800659BE
0x1800659bc  xor     esi, esi
0x1800659be  mov     [rbp+4Fh+spCommands.ptr_], rsi
0x1800659c2  test    edi, edi
0x1800659c4  js      short loc_180065A1B
0x1800659c6  mov     ParentWindow, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800659cd  lea     r14, WPP_GLOBAL_Control
0x1800659d4  cmp     ParentWindow, r14
0x1800659d7  jz      short loc_1800659F4
0x1800659d9  test    byte ptr [ParentWindow+1Ch], 10h
0x1800659dd  jz      short loc_1800659F4
0x1800659df  mov     edx, 10h; id
0x1800659e4  lea     AllowCommandText, WPP_58016a1fb6c83b3d634d8292d1366b43_Traceguids; TraceGuid
0x1800659eb  mov     ParentWindow, [ParentWindow+10h]; Logger
0x1800659ef  call    WPP_SF_
0x1800659f4  mov     rdi, [rbp+4Fh+spMessageDialog.ptr_]
0x1800659f8  mov     rax, [rdi]
0x1800659fb  mov     rbx, [rax+40h]
0x1800659ff  lea     ParentWindow, [rbp+4Fh+spCommands]; this
0x180065a03  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180065a08  lea     Content, [rbp+4Fh+spCommands]
0x180065a0c  mov     ParentWindow, rdi
0x180065a0f  mov     rax, rbx
0x180065a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065a17  mov     edi, eax
0x180065a19  jmp     short loc_180065A22
0x180065a1b  lea     r14, WPP_GLOBAL_Control
0x180065a22  mov     [r15], sil
0x180065a25  test    edi, edi
0x180065a27  js      loc_180065AD9
0x180065a2d  mov     [rbp+4Fh+spCallback.ptr_], r15
0x180065a31  lea     Content, [rbp+4Fh+spCallback]; <args_0>
0x180065a35  lea     ParentWindow, [rbp+4Fh+spIWPPMessageDialog]; result
0x180065a39  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__UI__Popups__IUICommandInvokedHandler_____Windows__UI__Popups__IUICommand______DelegateInvokeHelper_Windows__UI__Popups__IUICommandInvokedHandler___anonymous_namespace___ShowMessageDialogAndGetUserSelection_Worker____29____lambda_1___1_Windows__UI__Popups__IUICommand______anonymous_namespace___ShowMessageDialogAndGetUserSelection_Worker____29____lambda_1___
0x180065a3e  mov     rbx, [rax]
0x180065a41  mov     [rbp+4Fh+spCallback.ptr_], rbx
0x180065a45  mov     [rax], rsi
0x180065a48  mov     ParentWindow, [rbp+4Fh+spIWPPMessageDialog.ptr_]; this
0x180065a4c  test    ParentWindow, ParentWindow
0x180065a4f  jz      short loc_180065A5B
0x180065a51  mov     [rbp+4Fh+spIWPPMessageDialog.ptr_], rsi
0x180065a55  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUICommandInvokedHandler@Popups@UI@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::UI::Popups::IUICommandInvokedHandler>::Release(void)
0x180065a5a  nop
0x180065a5b  mov     AllowCommandText, rbx; CommandHandler
0x180065a5e  mov     Content, r12; Label
0x180065a61  mov     ParentWindow, [rbp+4Fh+spCommands.ptr_]; Commands
0x180065a65  call    _anonymous_namespace___AddDialogCommand
0x180065a6a  mov     edi, eax
0x180065a6c  test    rbx, rbx
0x180065a6f  jz      short loc_180065A81
0x180065a71  mov     rax, [rbx]
0x180065a74  mov     ParentWindow, rbx
0x180065a77  mov     rax, [rax+10h]
0x180065a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065a80  nop
0x180065a81  test    edi, edi
0x180065a83  js      short loc_180065AD9
0x180065a85  mov     [rbp+4Fh+spCallback.ptr_], r15
0x180065a89  lea     Content, [rbp+4Fh+spCallback]; <args_0>
0x180065a8d  lea     ParentWindow, [rbp+4Fh+spIWPPMessageDialog]; result
0x180065a91  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__UI__Popups__IUICommandInvokedHandler_____Windows__UI__Popups__IUICommand______DelegateInvokeHelper_Windows__UI__Popups__IUICommandInvokedHandler___anonymous_namespace___ShowMessageDialogAndGetUserSelection_Worker____32____lambda_2___1_Windows__UI__Popups__IUICommand______anonymous_namespace___ShowMessageDialogAndGetUserSelection_Worker____32____lambda_2___
0x180065a96  mov     rbx, [rax]
0x180065a99  mov     [rbp+4Fh+spCallback.ptr_], rbx
0x180065a9d  mov     [rax], rsi
0x180065aa0  mov     ParentWindow, [rbp+4Fh+spIWPPMessageDialog.ptr_]; this
0x180065aa4  test    ParentWindow, ParentWindow
0x180065aa7  jz      short loc_180065AB3
0x180065aa9  mov     [rbp+4Fh+spIWPPMessageDialog.ptr_], rsi
0x180065aad  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUICommandInvokedHandler@Popups@UI@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::UI::Popups::IUICommandInvokedHandler>::Release(void)
0x180065ab2  nop
0x180065ab3  mov     AllowCommandText, rbx; CommandHandler
0x180065ab6  mov     Content, r13; Label
0x180065ab9  mov     ParentWindow, [rbp+4Fh+spCommands.ptr_]; Commands
0x180065abd  call    _anonymous_namespace___AddDialogCommand
0x180065ac2  mov     edi, eax
0x180065ac4  test    rbx, rbx
0x180065ac7  jz      short loc_180065AD9
0x180065ac9  mov     rax, [rbx]
0x180065acc  mov     ParentWindow, rbx
0x180065acf  mov     rax, [rax+10h]
0x180065ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065ad8  nop
0x180065ad9  mov     [rbp+4Fh+spMessageDialogAsyncOperation.ptr_], rsi
0x180065add  test    edi, edi
0x180065adf  js      loc_180065B67
0x180065ae5  mov     ParentWindow, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180065aec  cmp     ParentWindow, r14
0x180065aef  jz      short loc_180065B0C
0x180065af1  test    byte ptr [ParentWindow+1Ch], 10h
0x180065af5  jz      short loc_180065B0C
0x180065af7  mov     edx, 13h; id
0x180065afc  lea     AllowCommandText, WPP_58016a1fb6c83b3d634d8292d1366b43_Traceguids; TraceGuid
0x180065b03  mov     ParentWindow, [ParentWindow+10h]; Logger
0x180065b07  call    WPP_SF_
0x180065b0c  mov     rdi, [rbp+4Fh+spMessageDialog.ptr_]
0x180065b10  mov     rax, [rdi]
0x180065b13  mov     rbx, [rax+78h]
  ... truncated ...
```
