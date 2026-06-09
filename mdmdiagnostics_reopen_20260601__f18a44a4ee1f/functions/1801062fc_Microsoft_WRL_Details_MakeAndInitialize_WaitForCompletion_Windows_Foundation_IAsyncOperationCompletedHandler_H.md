# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x1801062fc`
- end: `0x1801063dc`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperation@PEAUHSTRING__@@@23@@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperation@PEAUHSTRING__@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperation@PEAUHSTRING__@@@23@@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801065d0`

## callees

- `0x1800190e8`
- `0x1800eb1ac`
- `0x1801062fc`
- `0x180108acc`
- `0x180108d64`
- `0x180193010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180106360`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180106360`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106375`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106375`

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
0x1801062fc  mov     [rsp+arg_10], rbx
0x180106301  mov     [rsp+arg_18], rsi
0x180106306  push    rdi
0x180106307  sub     rsp, 20h
0x18010630b  mov     rsi, rcx
0x18010630e  mov     qword ptr [rcx], 0
0x180106315  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18010631c  mov     ecx, 40h ; '@'; unsigned __int64
0x180106321  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180106326  mov     [rsp+28h+arg_8], rax
0x18010632b  test    rax, rax
0x18010632e  jnz     short loc_18010633A
0x180106330  mov     ebx, 8007000Eh
0x180106335  jmp     loc_1801063BF
0x18010633a  mov     rcx, rax
0x18010633d  call    ??0FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperation@PEAUHSTRING__@@@23@@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@QEAA@XZ; `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::FTMEventDelegate(void)
0x180106342  mov     rdi, rax
0x180106345  mov     [rsp+28h+arg_0], rax
0x18010634a  mov     [rsp+28h+arg_8], 0
0x180106353  mov     r9d, 1F0003h; dwDesiredAccess
0x180106359  xor     r8d, r8d; dwFlags
0x18010635c  xor     edx, edx; lpName
0x18010635e  xor     ecx, ecx; lpEventAttributes
0x180106360  call    cs:__imp_CreateEventExW
0x180106367  nop     dword ptr [rax+rax+00h]
0x18010636c  mov     [rdi+38h], rax
0x180106370  test    rax, rax
0x180106373  jnz     short loc_1801063A0
0x180106375  call    cs:__imp_GetLastError
0x18010637c  nop     dword ptr [rax+rax+00h]
0x180106381  mov     ebx, eax
0x180106383  test    eax, eax
0x180106385  jle     short loc_180106390
0x180106387  movzx   ebx, ax
0x18010638a  or      ebx, 80070000h
0x180106390  test    ebx, ebx
0x180106392  jns     short loc_1801063A0
0x180106394  lea     rcx, [rsp+28h+arg_0]
0x180106399  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18010639e  jmp     short loc_1801063BF
0x1801063a0  mov     rax, [rdi]
0x1801063a3  mov     rcx, rdi
0x1801063a6  mov     rax, [rax+8]
0x1801063aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801063af  nop
0x1801063b0  mov     [rsi], rdi
0x1801063b3  lea     rcx, [rsp+28h+arg_0]
0x1801063b8  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801063bd  xor     ebx, ebx
0x1801063bf  lea     rcx, [rsp+28h+arg_8]
0x1801063c4  call    ??1?$MakeAllocator@VCMockEngine@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CMockEngine>::~MakeAllocator<CMockEngine>(void)
0x1801063c9  mov     eax, ebx
0x1801063cb  mov     rbx, [rsp+28h+arg_10]
0x1801063d0  mov     rsi, [rsp+28h+arg_18]
0x1801063d5  add     rsp, 20h
0x1801063d9  pop     rdi
0x1801063da  retn
```
