# CDelegateBase<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::CDelegateBase<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>(long *)

- ea: `0x1800221f8`
- end: `0x1800222af`
- name: `??0?$CDelegateBase@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@@@QEAA@PEAJ@Z`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180023730`

## callees

- `0x180001b40`
- `0x1800221f8`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180022275`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180022275`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022288`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022288`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDelegateBase<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::CDelegateBase<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>(
        __int64 a1,
        signed int *a2)
{
  _QWORD *v4; // rdi
  HANDLE EventW; // rax
  signed int LastError; // eax

  *(_QWORD *)a1 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::Streaming::Internal::MediaServer *>::`vftable';
  v4 = (_QWORD *)(a1 + 8);
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(a1 + 8));
  *(_DWORD *)(a1 + 44) = 1;
  *(_QWORD *)a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<bool>'};
  *v4 = &CDelegateBase<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)a1 = &CDelegateBase<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<bool>'};
  *v4 = &CDelegateBase<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  EventW = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 48) = EventW;
  if ( EventW )
  {
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
  }
  *a2 = LastError;
  return a1;
}

```

## disassembly

```asm
0x1800221f8  mov     [rsp+arg_0], rbx
0x1800221fd  mov     [rsp+arg_8], rsi
0x180022202  push    rdi
0x180022203  sub     rsp, 20h
0x180022207  mov     rsi, rdx
0x18002220a  mov     rbx, rcx
0x18002220d  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVMediaServer@Internal@Streaming@Media@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::Streaming::Internal::MediaServer *>::`vftable'
0x180022214  mov     [rcx], rax
0x180022217  lea     rdi, [rcx+8]
0x18002221b  mov     rcx, rdi; this
0x18002221e  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180022223  mov     dword ptr [rbx+2Ch], 1
0x18002222a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<bool>'}
0x180022231  mov     [rbx], rax
0x180022234  lea     rax, ??_7?$CDelegateBase@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CDelegateBase<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18002223b  mov     [rdi], rax
0x18002223e  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180022245  test    rcx, rcx
0x180022248  jz      short loc_180022257
0x18002224a  mov     rax, [rcx]
0x18002224d  mov     rax, [rax+8]
0x180022251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022256  nop
0x180022257  lea     rax, ??_7?$CDelegateBase@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@@@6B?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@; const CDelegateBase<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<bool>'}
0x18002225e  mov     [rbx], rax
0x180022261  lea     rax, ??_7?$CDelegateBase@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CDelegateBase<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180022268  mov     [rdi], rax
0x18002226b  xor     r9d, r9d; lpName
0x18002226e  xor     r8d, r8d; bInitialState
0x180022271  xor     edx, edx; bManualReset
0x180022273  xor     ecx, ecx; lpEventAttributes
0x180022275  call    cs:__imp_CreateEventW
0x18002227b  mov     [rbx+30h], rax
0x18002227f  test    rax, rax
0x180022282  jz      short loc_180022288
0x180022284  xor     eax, eax
0x180022286  jmp     short loc_18002229A
0x180022288  call    cs:__imp_GetLastError
0x18002228e  test    eax, eax
0x180022290  jle     short loc_18002229A
0x180022292  movzx   eax, ax
0x180022295  or      eax, 80070000h
0x18002229a  mov     [rsi], eax
0x18002229c  mov     rax, rbx
0x18002229f  mov     rbx, [rsp+28h+arg_0]
0x1800222a4  mov     rsi, [rsp+28h+arg_8]
0x1800222a9  add     rsp, 20h
0x1800222ad  pop     rdi
0x1800222ae  retn
```
