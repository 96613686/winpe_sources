# _anonymous_namespace_::AddDialogCommand

- ea: `0x180064a5c`
- end: `0x180064bd7`
- name: `_anonymous_namespace_::AddDialogCommand`
- size: `379`
- prototype: `HRESULT __fastcall(Windows::Foundation::Collections::IVector<Windows::UI::Popups::IUICommand *> *Commands, const wchar_t *Label, Windows::UI::Popups::IUICommandInvokedHandler *CommandHandler)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800656a8`

## callees

- `0x180002790`
- `0x180012770`
- `0x18005b4a4`
- `0x180064354`
- `0x180064a5c`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180064abd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180064b1a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180064abd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180064b1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180064aa4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180064b2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180064aa4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180064b2d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall anonymous_namespace_::AddDialogCommand(
        Windows::Foundation::Collections::IVector<Windows::UI::Popups::IUICommand *> *Commands,
        const wchar_t *Label,
        Windows::UI::Popups::IUICommandInvokedHandler *CommandHandler)
{
  HSTRING v6; // rbx
  int v7; // ebx
  Windows::UI::Popups::IUICommand *ptr; // rdi
  HRESULT (__fastcall *put_Label)(Windows::UI::Popups::IUICommand *, HSTRING__ *); // r15
  unsigned __int64 v10; // rbx
  HSTRING string; // [rsp+20h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-28h] BYREF
  Microsoft::WRL::ComPtr<Windows::UI::Popups::IUICommand> spCommand; // [rsp+40h] [rbp-10h] BYREF

  spCommand.ptr_ = 0;
  if ( WindowsCreateStringReference(RuntimeClass_Windows_UI_Popups_UICommand, 0x1Bu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v6 = string;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)&spCommand);
  v7 = Windows::Foundation::ActivateInstance<Windows::UI::Popups::IUICommand>(v6, &spCommand.ptr_);
  if ( v7 >= 0 )
  {
    ptr = spCommand.ptr_;
    put_Label = spCommand.ptr_->put_Label;
    v10 = -1;
    do
      ++v10;
    while ( Label[v10] );
    if ( v10 > 0xFFFFFFFF )
    {
      LODWORD(v10) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference(Label, v10, &hstringHeader, &string);
    v7 = put_Label(ptr, string);
    if ( v7 >= 0 )
    {
      v7 = spCommand.ptr_->put_Invoked(spCommand.ptr_, CommandHandler);
      if ( v7 >= 0 )
        v7 = Commands->Append(Commands, spCommand.ptr_);
    }
  }
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0xAu, WPP_58016a1fb6c83b3d634d8292d1366b43_Traceguids, v7);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)&spCommand);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180064a5c  mov     [rsp-38h+arg_18], rbx
0x180064a61  push    rbp
0x180064a62  push    rsi
0x180064a63  push    rdi
0x180064a64  push    r12
0x180064a66  push    r13
0x180064a68  push    r14
0x180064a6a  push    r15
0x180064a6c  mov     rbp, rsp
0x180064a6f  sub     rsp, 50h
0x180064a73  mov     rax, cs:__security_cookie
0x180064a7a  xor     rax, rsp
0x180064a7d  mov     [rbp+var_8], rax
0x180064a81  mov     r12, CommandHandler
0x180064a84  mov     r14, Label
0x180064a87  mov     rsi, Commands
0x180064a8a  xor     r13d, r13d
0x180064a8d  mov     [rbp+spCommand.ptr_], r13
0x180064a91  lea     r9, [rbp+string]; string
0x180064a95  lea     CommandHandler, [rbp+hstringHeader]; hstringHeader
0x180064a99  lea     edx, [r13+1Bh]; length
0x180064a9d  lea     Commands, ?RuntimeClass_Windows_UI_Popups_UICommand@@3QBGB; sourceString
0x180064aa4  call    cs:__imp_WindowsCreateStringReference
0x180064aaa  test    eax, eax
0x180064aac  jns     short loc_180064AC3
0x180064aae  xor     r9d, r9d; lpArguments
0x180064ab1  xor     r8d, r8d; nNumberOfArguments
0x180064ab4  lea     edx, [r13+1]; dwExceptionFlags
0x180064ab8  mov     ecx, 0C000000Dh; dwExceptionCode
0x180064abd  call    cs:__imp_RaiseException
0x180064ac3  mov     rbx, [rbp+string]
0x180064ac7  lea     Commands, [rbp+spCommand]; this
0x180064acb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180064ad0  lea     Label, [rbp+spCommand]; instance
0x180064ad4  mov     Commands, rbx; activatableClassId
0x180064ad7  call    ??$ActivateInstance@UIUICommand@Popups@UI@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIUICommand@Popups@UI@1@@Z; Windows::Foundation::ActivateInstance<Windows::UI::Popups::IUICommand>(HSTRING__ *,Windows::UI::Popups::IUICommand * *)
0x180064adc  mov     ebx, eax
0x180064ade  test    eax, eax
0x180064ae0  js      loc_180064B76
0x180064ae6  mov     rdi, [rbp+spCommand.ptr_]
0x180064aea  mov     rax, [rdi]
0x180064aed  mov     r15, [rax+38h]
0x180064af1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180064af5  inc     rbx
0x180064af8  cmp     [r14+rbx*2], r13w
0x180064afd  jnz     short loc_180064AF5
0x180064aff  mov     eax, 0FFFFFFFFh
0x180064b04  cmp     rbx, rax
0x180064b07  jbe     short loc_180064B20
0x180064b09  mov     ebx, eax
0x180064b0b  xor     r9d, r9d; lpArguments
0x180064b0e  xor     r8d, r8d; nNumberOfArguments
0x180064b11  lea     edx, [r9+1]; dwExceptionFlags
0x180064b15  mov     ecx, 0C000000Dh; dwExceptionCode
0x180064b1a  call    cs:__imp_RaiseException
0x180064b20  lea     r9, [rbp+string]; string
0x180064b24  lea     CommandHandler, [rbp+hstringHeader]; hstringHeader
0x180064b28  mov     edx, ebx; length
0x180064b2a  mov     Commands, r14; sourceString
0x180064b2d  call    cs:__imp_WindowsCreateStringReference
0x180064b33  mov     Label, [rbp+string]
0x180064b37  mov     Commands, rdi
0x180064b3a  mov     rax, r15
0x180064b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064b42  mov     ebx, eax
0x180064b44  test    eax, eax
0x180064b46  js      short loc_180064B76
0x180064b48  mov     Commands, [rbp+spCommand.ptr_]
0x180064b4c  mov     rax, [Commands]
0x180064b4f  mov     Label, r12
0x180064b52  mov     rax, [rax+48h]
0x180064b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064b5b  mov     ebx, eax
0x180064b5d  test    eax, eax
0x180064b5f  js      short loc_180064B76
0x180064b61  mov     rax, [rsi]
0x180064b64  mov     Label, [rbp+spCommand.ptr_]
0x180064b68  mov     Commands, rsi
0x180064b6b  mov     rax, [rax+68h]
0x180064b6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064b74  mov     ebx, eax
0x180064b76  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x180064b7d  mov     Commands, cs:WPP_GLOBAL_Control
0x180064b84  cmp     Commands, rax
0x180064b87  jz      short loc_180064BA8
0x180064b89  test    byte ptr [Commands+1Ch], 10h
0x180064b8d  jz      short loc_180064BA8
0x180064b8f  mov     edx, 0Ah; id
0x180064b94  mov     r9d, ebx; _a1
0x180064b97  lea     CommandHandler, WPP_58016a1fb6c83b3d634d8292d1366b43_Traceguids; TraceGuid
0x180064b9e  mov     Commands, [Commands+10h]; Logger
0x180064ba2  call    WPP_SF_d
0x180064ba7  nop
0x180064ba8  lea     Commands, [rbp+spCommand]; this
0x180064bac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180064bb1  mov     eax, ebx
0x180064bb3  mov     Commands, [rbp+var_8]
0x180064bb7  xor     Commands, rsp; StackCookie
0x180064bba  call    __security_check_cookie
0x180064bbf  mov     rbx, [rsp+50h+arg_18]
0x180064bc7  add     rsp, 50h
0x180064bcb  pop     r15
0x180064bcd  pop     r14
0x180064bcf  pop     r13
0x180064bd1  pop     r12
0x180064bd3  pop     rdi
0x180064bd4  pop     rsi
0x180064bd5  pop     rbp
0x180064bd6  retn
```
