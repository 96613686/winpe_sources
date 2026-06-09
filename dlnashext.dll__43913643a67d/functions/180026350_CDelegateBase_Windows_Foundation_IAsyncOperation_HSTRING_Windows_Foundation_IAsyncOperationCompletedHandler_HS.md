# CDelegateBase<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>>::CDelegateBase<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>>(long *)

- ea: `0x180026350`
- end: `0x180026407`
- name: `??0?$CDelegateBase@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@23@@@QEAA@PEAJ@Z`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026da0`

## callees

- `0x180001b40`
- `0x180026350`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800263cd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800263cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800263e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800263e0`

## pseudocode

```c
__int64 __fastcall CDelegateBase<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>>::CDelegateBase<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>>(
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
  *(_QWORD *)a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>'};
  *v4 = &CDelegateBase<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)a1 = &CDelegateBase<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>'};
  *v4 = &CDelegateBase<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
0x180026350  mov     [rsp+arg_0], rbx
0x180026355  mov     [rsp+arg_8], rsi
0x18002635a  push    rdi
0x18002635b  sub     rsp, 20h
0x18002635f  mov     rsi, rdx
0x180026362  mov     rbx, rcx
0x180026365  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVMediaServer@Internal@Streaming@Media@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::Streaming::Internal::MediaServer *>::`vftable'
0x18002636c  mov     [rcx], rax
0x18002636f  lea     rdi, [rcx+8]
0x180026373  mov     rcx, rdi; this
0x180026376  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18002637b  mov     dword ptr [rbx+2Ch], 1
0x180026382  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>'}
0x180026389  mov     [rbx], rax
0x18002638c  lea     rax, ??_7?$CDelegateBase@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@23@@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CDelegateBase<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180026393  mov     [rdi], rax
0x180026396  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18002639d  test    rcx, rcx
0x1800263a0  jz      short loc_1800263AF
0x1800263a2  mov     rax, [rcx]
0x1800263a5  mov     rax, [rax+8]
0x1800263a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800263ae  nop
0x1800263af  lea     rax, ??_7?$CDelegateBase@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@23@@@6B?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@@; const CDelegateBase<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>'}
0x1800263b6  mov     [rbx], rax
0x1800263b9  lea     rax, ??_7?$CDelegateBase@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@23@@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CDelegateBase<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800263c0  mov     [rdi], rax
0x1800263c3  xor     r9d, r9d; lpName
0x1800263c6  xor     r8d, r8d; bInitialState
0x1800263c9  xor     edx, edx; bManualReset
0x1800263cb  xor     ecx, ecx; lpEventAttributes
0x1800263cd  call    cs:__imp_CreateEventW
0x1800263d3  mov     [rbx+30h], rax
0x1800263d7  test    rax, rax
0x1800263da  jz      short loc_1800263E0
0x1800263dc  xor     eax, eax
0x1800263de  jmp     short loc_1800263F2
0x1800263e0  call    cs:__imp_GetLastError
0x1800263e6  test    eax, eax
0x1800263e8  jle     short loc_1800263F2
0x1800263ea  movzx   eax, ax
0x1800263ed  or      eax, 80070000h
0x1800263f2  mov     [rsi], eax
0x1800263f4  mov     rax, rbx
0x1800263f7  mov     rbx, [rsp+28h+arg_0]
0x1800263fc  mov     rsi, [rsp+28h+arg_8]
0x180026401  add     rsp, 20h
0x180026405  pop     rdi
0x180026406  retn
```
