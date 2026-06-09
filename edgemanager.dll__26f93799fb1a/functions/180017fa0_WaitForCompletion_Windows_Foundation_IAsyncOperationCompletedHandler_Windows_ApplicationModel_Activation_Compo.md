# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Activation::ComponentActivationResultPrivate *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Activation::ComponentActivationResultPrivate *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Activation::ComponentActivationResultPrivate *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x180017fa0`
- end: `0x180018191`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVComponentActivationResultPrivate@Activation@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVComponentActivationResultPrivate@Activation@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVComponentActivationResultPrivate@Activation@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `497`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800051c0`
- `0x180017f44`

## callees

- `0x18000b0ec`
- `0x18000f5d4`
- `0x180017fa0`
- `0x18002b5e4`
- `0x1800345f8`
- `0x1800358e0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180018040`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180018040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001804f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001804f`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Activation::ComponentActivationResultPrivate *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Activation::ComponentActivationResultPrivate *>>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        int a2,
        void **a3)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  signed int v6; // edi
  HANDLE Event; // rax
  signed int LastError; // eax
  unsigned int v9; // r9d
  int v10; // eax
  int (__fastcall *v11)(_QWORD, GUID *, __int64 *); // rbx
  void **v12; // rcx
  unsigned int v14; // [rsp+20h] [rbp-38h]
  unsigned int v15; // [rsp+28h] [rbp-30h]
  void *v16[4]; // [rsp+38h] [rbp-20h] BYREF
  __int64 v17; // [rsp+80h] [rbp+28h] BYREF
  int v18; // [rsp+88h] [rbp+30h] BYREF
  void **v19; // [rsp+90h] [rbp+38h]
  _QWORD *v20; // [rsp+98h] [rbp+40h] BYREF

  v19 = a3;
  v18 = a2;
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[1])(a1);
  v19 = 0;
  v4 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  if ( v4 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Activation::ComponentActivationResultPrivate *>,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Activation::ComponentActivationResultPrivate *>,Microsoft::WRL::FtmBase>(v4);
    *v5 = &`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Activation::ComponentActivationResultPrivate *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Activation::ComponentActivationResultPrivate *>>'::`2'::FTMEventDelegate::`vftable';
    v5[1] = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Activation::ComponentActivationResultPrivate *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Activation::ComponentActivationResultPrivate *>>'::`2'::FTMEventDelegate::`vftable';
    *((_DWORD *)v5 + 12) = 0;
    v5[7] = 0;
    v20 = v5;
    v17 = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    v5[7] = Event;
    if ( Event )
      goto LABEL_9;
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 >= 0 )
    {
LABEL_9:
      (*(void (__fastcall **)(_QWORD *))(*v5 + 8LL))(v5);
      v19 = (void **)v5;
      v6 = 0;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(&v17);
    v18 = v6;
    if ( v6 >= 0 )
    {
      v6 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), void **))(*a1)[6])(a1, v19);
      v18 = v6;
      if ( v6 >= 0 )
      {
        v16[0] = v19[7];
        v16[1] = 0;
        if ( SHProcessMessagesUntilEventsEx((HWND)v16[0], v16, 1u, v9, v14, v15) == -1 )
        {
          v10 = -2147467259;
          v18 = -2147467259;
        }
        else
        {
          v10 = v18;
        }
        v17 = 0;
        if ( v10 >= 0 && *((_DWORD *)v19 + 12) != 1 )
        {
          v11 = **a1;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
          if ( v11(a1, &GUID_00000036_0000_0000_c000_000000000046, &v17) >= 0 )
            (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v17 + 64LL))(v17, &v18);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
        v6 = v18;
      }
    }
  }
  else
  {
    v6 = -2147024882;
    v18 = -2147024882;
  }
  v12 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*((void (__fastcall **)(void **))*v12 + 2))(v12);
  }
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[2])(a1);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180017fa0  mov     [rsp-20h+arg_10], r8
0x180017fa5  mov     [rsp-20h+arg_8], edx
0x180017fa9  push    rbp
0x180017faa  push    rbx
0x180017fab  push    rsi
0x180017fac  push    rdi
0x180017fad  mov     rbp, rsp
0x180017fb0  sub     rsp, 58h
0x180017fb4  mov     rsi, rcx
0x180017fb7  mov     [rbp+var_28], rcx
0x180017fbb  test    rcx, rcx
0x180017fbe  jz      short loc_180017FCD
0x180017fc0  mov     rax, [rcx]
0x180017fc3  mov     rax, [rax+8]
0x180017fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fcc  nop
0x180017fcd  mov     [rbp+arg_10], 0
0x180017fd5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017fdc  mov     ecx, 40h ; '@'; unsigned __int64
0x180017fe1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180017fe6  mov     rbx, rax
0x180017fe9  test    rax, rax
0x180017fec  jnz     short loc_180017FFB
0x180017fee  mov     edi, 8007000Eh
0x180017ff3  mov     [rbp+arg_8], edi
0x180017ff6  jmp     loc_180018153
0x180017ffb  mov     rcx, rbx
0x180017ffe  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVComponentActivationResultPrivate@Activation@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Activation::ComponentActivationResultPrivate *>,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Activation::ComponentActivationResultPrivate *>,Microsoft::WRL::FtmBase>(void)
0x180018003  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVComponentActivationResultPrivate@Activation@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVComponentActivationResultPrivate@Activation@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVComponentActivationResultPrivate@Activation@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVComponentActivationResultPrivate@Activation@ApplicationModel@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Activation::ComponentActivationResultPrivate *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Activation::ComponentActivationResultPrivate *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Activation::ComponentActivationResultPrivate *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Activation::ComponentActivationResultPrivate *>'}
0x18001800a  mov     [rbx], rax
0x18001800d  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVComponentActivationResultPrivate@Activation@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVComponentActivationResultPrivate@Activation@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVComponentActivationResultPrivate@Activation@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Activation::ComponentActivationResultPrivate *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Activation::ComponentActivationResultPrivate *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Activation::ComponentActivationResultPrivate *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180018014  mov     [rbx+8], rax
0x180018018  mov     dword ptr [rbx+30h], 0
0x18001801f  mov     qword ptr [rbx+38h], 0
0x180018027  mov     [rbp+arg_18], rbx
0x18001802b  mov     [rbp+arg_0], 0
0x180018033  mov     r9d, 1F0003h; dwDesiredAccess
0x180018039  xor     r8d, r8d; dwFlags
0x18001803c  xor     edx, edx; lpName
0x18001803e  xor     ecx, ecx; lpEventAttributes
0x180018040  call    cs:__imp_CreateEventExW
0x180018046  mov     [rbx+38h], rax
0x18001804a  test    rax, rax
0x18001804d  jnz     short loc_180018068
0x18001804f  call    cs:__imp_GetLastError
0x180018055  mov     edi, eax
0x180018057  test    eax, eax
0x180018059  jle     short loc_180018064
0x18001805b  movzx   edi, ax
0x18001805e  or      edi, 80070000h
0x180018064  test    edi, edi
0x180018066  js      short loc_18001807E
0x180018068  mov     rax, [rbx]
0x18001806b  mov     rcx, rbx
0x18001806e  mov     rax, [rax+8]
0x180018072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018077  nop
0x180018078  mov     [rbp+arg_10], rbx
0x18001807c  xor     edi, edi
0x18001807e  lea     rcx, [rbp+arg_18]
0x180018082  lea     rbx, [rbp+arg_0]
0x180018086  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001808b  mov     rcx, rbx
0x18001808e  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)
0x180018093  mov     [rbp+arg_8], edi
0x180018096  test    edi, edi
0x180018098  js      loc_180018153
0x18001809e  mov     rax, [rsi]
0x1800180a1  mov     rdx, [rbp+arg_10]
0x1800180a5  mov     rcx, rsi
0x1800180a8  mov     rax, [rax+30h]
0x1800180ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180b1  mov     edi, eax
0x1800180b3  mov     [rbp+arg_8], eax
0x1800180b6  test    eax, eax
0x1800180b8  js      loc_180018153
0x1800180be  mov     rax, [rbp+arg_10]
0x1800180c2  mov     rcx, [rax+38h]; HWND
0x1800180c6  mov     [rbp+var_20], rcx
0x1800180ca  mov     [rbp+var_18], 0
0x1800180d2  mov     r8d, 1; unsigned int
0x1800180d8  lea     rdx, [rbp+var_20]; void **
0x1800180dc  call    ?SHProcessMessagesUntilEventsEx@@YAKPEAUHWND__@@PEAPEAXKKKK@Z; SHProcessMessagesUntilEventsEx(HWND__ *,void * *,ulong,ulong,ulong,ulong)
0x1800180e1  cmp     eax, 0FFFFFFFFh
0x1800180e4  jnz     short loc_1800180F0
0x1800180e6  mov     eax, 80004005h
0x1800180eb  mov     [rbp+arg_8], eax
0x1800180ee  jmp     short loc_1800180F3
0x1800180f0  mov     eax, [rbp+arg_8]
0x1800180f3  mov     [rbp+arg_0], 0
0x1800180fb  test    eax, eax
0x1800180fd  js      short loc_180018147
0x1800180ff  mov     rax, [rbp+arg_10]
0x180018103  cmp     dword ptr [rax+30h], 1
0x180018107  jz      short loc_180018147
0x180018109  mov     rax, [rsi]
0x18001810c  mov     rbx, [rax]
0x18001810f  lea     rcx, [rbp+arg_0]
0x180018113  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180018118  lea     r8, [rbp+arg_0]
0x18001811c  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180018123  mov     rcx, rsi
0x180018126  mov     rax, rbx
0x180018129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001812e  test    eax, eax
0x180018130  js      short loc_180018147
0x180018132  mov     rcx, [rbp+arg_0]
0x180018136  mov     rax, [rcx]
0x180018139  lea     rdx, [rbp+arg_8]
0x18001813d  mov     rax, [rax+40h]
0x180018141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018146  nop
0x180018147  lea     rcx, [rbp+arg_0]
0x18001814b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180018150  mov     edi, [rbp+arg_8]
0x180018153  mov     rcx, [rbp+arg_10]
0x180018157  test    rcx, rcx
0x18001815a  jz      short loc_180018171
0x18001815c  mov     [rbp+arg_10], 0
0x180018164  mov     rax, [rcx]
0x180018167  mov     rax, [rax+10h]
0x18001816b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018170  nop
0x180018171  test    rsi, rsi
0x180018174  jz      short loc_180018186
0x180018176  mov     rcx, [rsi]
0x180018179  mov     rax, [rcx+10h]
0x18001817d  mov     rcx, rsi
0x180018180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018185  nop
0x180018186  mov     eax, edi
0x180018188  add     rsp, 58h
0x18001818c  pop     rdi
0x18001818d  pop     rsi
0x18001818e  pop     rbx
0x18001818f  pop     rbp
0x180018190  retn
```
