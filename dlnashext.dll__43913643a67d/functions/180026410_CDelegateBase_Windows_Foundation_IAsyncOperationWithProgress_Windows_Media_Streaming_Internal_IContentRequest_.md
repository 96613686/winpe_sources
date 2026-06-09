# CDelegateBase<Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Streaming::Internal::IContentRequest *,uint>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Streaming::Internal::IContentRequest *,uint>>::CDelegateBase<Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Streaming::Internal::IContentRequest *,uint>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Streaming::Internal::IContentRequest *,uint>>(long *)

- ea: `0x180026410`
- end: `0x1800264c7`
- name: `??0?$CDelegateBase@U?$IAsyncOperationWithProgress@PEAUIContentRequest@Internal@Streaming@Media@Windows@@I@Foundation@Windows@@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIContentRequest@Internal@Streaming@Media@Windows@@I@23@@@QEAA@PEAJ@Z`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180027840`

## callees

- `0x180001b40`
- `0x180026410`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002648d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002648d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800264a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800264a0`

## pseudocode

```c
__int64 __fastcall CDelegateBase<Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Streaming::Internal::IContentRequest *,unsigned int>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Streaming::Internal::IContentRequest *,unsigned int>>::CDelegateBase<Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Streaming::Internal::IContentRequest *,unsigned int>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Streaming::Internal::IContentRequest *,unsigned int>>(
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
  *(_QWORD *)a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Streaming::Internal::IContentRequest *,unsigned int>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Streaming::Internal::IContentRequest *,unsigned int>'};
  *v4 = &CDelegateBase<Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Streaming::Internal::IContentRequest *,unsigned int>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Streaming::Internal::IContentRequest *,unsigned int>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)a1 = &CDelegateBase<Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Streaming::Internal::IContentRequest *,unsigned int>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Streaming::Internal::IContentRequest *,unsigned int>>::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Streaming::Internal::IContentRequest *,unsigned int>'};
  *v4 = &CDelegateBase<Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Streaming::Internal::IContentRequest *,unsigned int>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Streaming::Internal::IContentRequest *,unsigned int>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
0x180026410  mov     [rsp+arg_0], rbx
0x180026415  mov     [rsp+arg_8], rsi
0x18002641a  push    rdi
0x18002641b  sub     rsp, 20h
0x18002641f  mov     rsi, rdx
0x180026422  mov     rbx, rcx
0x180026425  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVMediaServer@Internal@Streaming@Media@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::Streaming::Internal::MediaServer *>::`vftable'
0x18002642c  mov     [rcx], rax
0x18002642f  lea     rdi, [rcx+8]
0x180026433  mov     rcx, rdi; this
0x180026436  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18002643b  mov     dword ptr [rbx+2Ch], 1
0x180026442  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIContentRequest@Internal@Streaming@Media@Windows@@I@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationWithProgressCompletedHandler@PEAUIContentRequest@Internal@Streaming@Media@Windows@@I@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Streaming::Internal::IContentRequest *,uint>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Streaming::Internal::IContentRequest *,uint>'}
0x180026449  mov     [rbx], rax
0x18002644c  lea     rax, ??_7?$CDelegateBase@U?$IAsyncOperationWithProgress@PEAUIContentRequest@Internal@Streaming@Media@Windows@@I@Foundation@Windows@@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIContentRequest@Internal@Streaming@Media@Windows@@I@23@@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CDelegateBase<Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Streaming::Internal::IContentRequest *,uint>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Streaming::Internal::IContentRequest *,uint>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180026453  mov     [rdi], rax
0x180026456  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18002645d  test    rcx, rcx
0x180026460  jz      short loc_18002646F
0x180026462  mov     rax, [rcx]
0x180026465  mov     rax, [rax+8]
0x180026469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002646e  nop
0x18002646f  lea     rax, ??_7?$CDelegateBase@U?$IAsyncOperationWithProgress@PEAUIContentRequest@Internal@Streaming@Media@Windows@@I@Foundation@Windows@@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIContentRequest@Internal@Streaming@Media@Windows@@I@23@@@6B?$IAsyncOperationWithProgressCompletedHandler@PEAUIContentRequest@Internal@Streaming@Media@Windows@@I@Foundation@Windows@@@; const CDelegateBase<Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Streaming::Internal::IContentRequest *,uint>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Streaming::Internal::IContentRequest *,uint>>::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Streaming::Internal::IContentRequest *,uint>'}
0x180026476  mov     [rbx], rax
0x180026479  lea     rax, ??_7?$CDelegateBase@U?$IAsyncOperationWithProgress@PEAUIContentRequest@Internal@Streaming@Media@Windows@@I@Foundation@Windows@@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIContentRequest@Internal@Streaming@Media@Windows@@I@23@@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CDelegateBase<Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Streaming::Internal::IContentRequest *,uint>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Streaming::Internal::IContentRequest *,uint>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180026480  mov     [rdi], rax
0x180026483  xor     r9d, r9d; lpName
0x180026486  xor     r8d, r8d; bInitialState
0x180026489  xor     edx, edx; bManualReset
0x18002648b  xor     ecx, ecx; lpEventAttributes
0x18002648d  call    cs:__imp_CreateEventW
0x180026493  mov     [rbx+30h], rax
0x180026497  test    rax, rax
0x18002649a  jz      short loc_1800264A0
0x18002649c  xor     eax, eax
0x18002649e  jmp     short loc_1800264B2
0x1800264a0  call    cs:__imp_GetLastError
0x1800264a6  test    eax, eax
0x1800264a8  jle     short loc_1800264B2
0x1800264aa  movzx   eax, ax
0x1800264ad  or      eax, 80070000h
0x1800264b2  mov     [rsi], eax
0x1800264b4  mov     rax, rbx
0x1800264b7  mov     rbx, [rsp+28h+arg_0]
0x1800264bc  mov     rsi, [rsp+28h+arg_8]
0x1800264c1  add     rsp, 20h
0x1800264c5  pop     rdi
0x1800264c6  retn
```
