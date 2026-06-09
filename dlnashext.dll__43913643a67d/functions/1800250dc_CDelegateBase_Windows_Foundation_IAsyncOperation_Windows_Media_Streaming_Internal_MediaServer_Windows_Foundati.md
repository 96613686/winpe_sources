# CDelegateBase<Windows::Foundation::IAsyncOperation<Windows::Media::Streaming::Internal::MediaServer *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::Streaming::Internal::MediaServer *>>::CDelegateBase<Windows::Foundation::IAsyncOperation<Windows::Media::Streaming::Internal::MediaServer *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::Streaming::Internal::MediaServer *>>(long *)

- ea: `0x1800250dc`
- end: `0x180025193`
- name: `??0?$CDelegateBase@U?$IAsyncOperation@PEAVMediaServer@Internal@Streaming@Media@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVMediaServer@Internal@Streaming@Media@Windows@@@23@@@QEAA@PEAJ@Z`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025860`

## callees

- `0x180001b40`
- `0x1800250dc`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180025159`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180025159`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002516c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002516c`

## pseudocode

```c
__int64 __fastcall CDelegateBase<Windows::Foundation::IAsyncOperation<Windows::Media::Streaming::Internal::MediaServer *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::Streaming::Internal::MediaServer *>>::CDelegateBase<Windows::Foundation::IAsyncOperation<Windows::Media::Streaming::Internal::MediaServer *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::Streaming::Internal::MediaServer *>>(
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
  *(_QWORD *)a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::Streaming::Internal::MediaServer *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::Streaming::Internal::MediaServer *>'};
  *v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::Streaming::Internal::MediaServer *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)a1 = &CDelegateBase<Windows::Foundation::IAsyncOperation<Windows::Media::Streaming::Internal::MediaServer *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::Streaming::Internal::MediaServer *>>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::Streaming::Internal::MediaServer *>'};
  *v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::Streaming::Internal::MediaServer *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
0x1800250dc  mov     [rsp+arg_0], rbx
0x1800250e1  mov     [rsp+arg_8], rsi
0x1800250e6  push    rdi
0x1800250e7  sub     rsp, 20h
0x1800250eb  mov     rsi, rdx
0x1800250ee  mov     rbx, rcx
0x1800250f1  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVMediaServer@Internal@Streaming@Media@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::Streaming::Internal::MediaServer *>::`vftable'
0x1800250f8  mov     [rcx], rax
0x1800250fb  lea     rdi, [rcx+8]
0x1800250ff  mov     rcx, rdi; this
0x180025102  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180025107  mov     dword ptr [rbx+2Ch], 1
0x18002510e  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVMediaServer@Internal@Streaming@Media@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVMediaServer@Internal@Streaming@Media@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::Streaming::Internal::MediaServer *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::Streaming::Internal::MediaServer *>'}
0x180025115  mov     [rbx], rax
0x180025118  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVMediaServer@Internal@Streaming@Media@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::Streaming::Internal::MediaServer *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18002511f  mov     [rdi], rax
0x180025122  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180025129  test    rcx, rcx
0x18002512c  jz      short loc_18002513B
0x18002512e  mov     rax, [rcx]
0x180025131  mov     rax, [rax+8]
0x180025135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002513a  nop
0x18002513b  lea     rax, ??_7?$CDelegateBase@U?$IAsyncOperation@PEAVMediaServer@Internal@Streaming@Media@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVMediaServer@Internal@Streaming@Media@Windows@@@23@@@6B?$IAsyncOperationCompletedHandler@PEAVMediaServer@Internal@Streaming@Media@Windows@@@Foundation@Windows@@@; const CDelegateBase<Windows::Foundation::IAsyncOperation<Windows::Media::Streaming::Internal::MediaServer *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::Streaming::Internal::MediaServer *>>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::Streaming::Internal::MediaServer *>'}
0x180025142  mov     [rbx], rax
0x180025145  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVMediaServer@Internal@Streaming@Media@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::Streaming::Internal::MediaServer *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18002514c  mov     [rdi], rax
0x18002514f  xor     r9d, r9d; lpName
0x180025152  xor     r8d, r8d; bInitialState
0x180025155  xor     edx, edx; bManualReset
0x180025157  xor     ecx, ecx; lpEventAttributes
0x180025159  call    cs:__imp_CreateEventW
0x18002515f  mov     [rbx+30h], rax
0x180025163  test    rax, rax
0x180025166  jz      short loc_18002516C
0x180025168  xor     eax, eax
0x18002516a  jmp     short loc_18002517E
0x18002516c  call    cs:__imp_GetLastError
0x180025172  test    eax, eax
0x180025174  jle     short loc_18002517E
0x180025176  movzx   eax, ax
0x180025179  or      eax, 80070000h
0x18002517e  mov     [rsi], eax
0x180025180  mov     rax, rbx
0x180025183  mov     rbx, [rsp+28h+arg_0]
0x180025188  mov     rsi, [rsp+28h+arg_8]
0x18002518d  add     rsp, 20h
0x180025191  pop     rdi
0x180025192  retn
```
