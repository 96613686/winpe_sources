# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x180105028`
- end: `0x1801050f8`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperation@PEAUHSTRING__@@@23@@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperation@PEAUHSTRING__@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperation@PEAUHSTRING__@@@23@@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801052e4`

## callees

- `0x180019068`
- `0x1800ead14`
- `0x180105028`
- `0x1801078b4`
- `0x180107a94`
- `0x180191010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180105089`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180105089`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180105098`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180105098`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAUHSTRING_____Foundation_Windows__U__IAsyncOperation_PEAUHSTRING_____23___YAJPEAU__IAsyncOperation_PEAUHSTRING_____Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAUHSTRING_____Foundation_Windows__U__IAsyncOperation_PEAUHSTRING_____23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAUHSTRING_____Foundation_Windows__U__IAsyncOperation_PEAUHSTRING_____23___YAJPEAU__IAsyncOperation_PEAUHSTRING_____Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        _QWORD *a1)
{
  void *v2; // rax
  signed int v3; // ebx
  _QWORD *v4; // rdi
  HANDLE Event; // rax
  signed int LastError; // eax
  _QWORD *v8; // [rsp+30h] [rbp+8h] BYREF
  void *v9; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  v9 = v2;
  if ( v2 )
  {
    v4 = (_QWORD *)`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>'::`2'::FTMEventDelegate::FTMEventDelegate(v2);
    v8 = v4;
    v9 = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    v4[7] = Event;
    if ( Event )
      goto LABEL_8;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
    {
LABEL_8:
      (*(void (__fastcall **)(_QWORD *))(*v4 + 8LL))(v4);
      *a1 = v4;
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v8);
      v3 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v8);
    }
  }
  else
  {
    v3 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<CMockEngine>::~MakeAllocator<CMockEngine>(&v9);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180105028  mov     [rsp+arg_10], rbx
0x18010502d  mov     [rsp+arg_18], rsi
0x180105032  push    rdi
0x180105033  sub     rsp, 20h
0x180105037  mov     rsi, rcx
0x18010503a  mov     qword ptr [rcx], 0
0x180105041  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180105048  mov     ecx, 40h ; '@'; unsigned __int64
0x18010504d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180105052  mov     [rsp+28h+arg_8], rax
0x180105057  test    rax, rax
0x18010505a  jnz     short loc_180105063
0x18010505c  mov     ebx, 8007000Eh
0x180105061  jmp     short loc_1801050DC
0x180105063  mov     rcx, rax
0x180105066  call    ??0FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperation@PEAUHSTRING__@@@23@@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@QEAA@XZ; `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::FTMEventDelegate(void)
0x18010506b  mov     rdi, rax
0x18010506e  mov     [rsp+28h+arg_0], rax
0x180105073  mov     [rsp+28h+arg_8], 0
0x18010507c  mov     r9d, 1F0003h; dwDesiredAccess
0x180105082  xor     r8d, r8d; dwFlags
0x180105085  xor     edx, edx; lpName
0x180105087  xor     ecx, ecx; lpEventAttributes
0x180105089  call    cs:__imp_CreateEventExW
0x18010508f  mov     [rdi+38h], rax
0x180105093  test    rax, rax
0x180105096  jnz     short loc_1801050BD
0x180105098  call    cs:__imp_GetLastError
0x18010509e  mov     ebx, eax
0x1801050a0  test    eax, eax
0x1801050a2  jle     short loc_1801050AD
0x1801050a4  movzx   ebx, ax
0x1801050a7  or      ebx, 80070000h
0x1801050ad  test    ebx, ebx
0x1801050af  jns     short loc_1801050BD
0x1801050b1  lea     rcx, [rsp+28h+arg_0]
0x1801050b6  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801050bb  jmp     short loc_1801050DC
0x1801050bd  mov     rax, [rdi]
0x1801050c0  mov     rcx, rdi
0x1801050c3  mov     rax, [rax+8]
0x1801050c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801050cc  nop
0x1801050cd  mov     [rsi], rdi
0x1801050d0  lea     rcx, [rsp+28h+arg_0]
0x1801050d5  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801050da  xor     ebx, ebx
0x1801050dc  lea     rcx, [rsp+28h+arg_8]
0x1801050e1  call    ??1?$MakeAllocator@VCMockEngine@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CMockEngine>::~MakeAllocator<CMockEngine>(void)
0x1801050e6  mov     eax, ebx
0x1801050e8  mov     rbx, [rsp+28h+arg_10]
0x1801050ed  mov     rsi, [rsp+28h+arg_18]
0x1801050f2  add     rsp, 20h
0x1801050f6  pop     rdi
0x1801050f7  retn
```
