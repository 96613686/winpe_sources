# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,wil::details::apartment_variable_base<1,wil::apartment_variable_platform> *>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::Cancel(void)

- ea: `0x18008ae4c`
- end: `0x18008af40`
- name: `?Cancel@?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@QEAAXXZ`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18008ae20`

## callees

- `0x18005f46c`
- `0x180070f30`
- `0x1800719cc`
- `0x18007ac48`
- `0x18007ac54`
- `0x180089ff8`
- `0x18008ae4c`
- `0x1800cb010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18008aed8`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18008aed8`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18008aea2`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18008aea2`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18008aece`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18008aece`
- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x18008aeb7`
- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x18008aeb7`

## pseudocode

```c
void __fastcall winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,wil::details::apartment_variable_base<1,wil::apartment_variable_platform> *>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::Cancel(
        __int64 a1)
{
  __int64 v2; // rbx
  void (__fastcall *v3)(_QWORD); // rax
  __int128 v4; // [rsp+20h] [rbp-48h] BYREF
  int v5; // [rsp+30h] [rbp-38h] BYREF
  __int128 v6; // [rsp+38h] [rbp-30h]
  _BYTE v7[32]; // [rsp+48h] [rbp-20h] BYREF
  __int64 v8; // [rsp+90h] [rbp+28h] BYREF

  v2 = 0;
  v8 = 0;
  WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)(a1 + 72));
  if ( !*(_DWORD *)(a1 + 96) )
  {
    *(_DWORD *)(a1 + 96) = 2;
    v5 = 0;
    v6 = 0;
    winrt::hresult_error::hresult_error(v7, winrt::impl::error_canceled, &v5);
    v4 = 0;
    __ExceptionPtrCreate(&v4);
    __ExceptionPtrCopyException(&v4, v7, &TI2_AUhresult_canceled_winrt__);
    winrt::hresult_error::~hresult_error((winrt::hresult_error *)v7);
    __ExceptionPtrAssign((void *)(a1 + 56), &v4);
    __ExceptionPtrDestroy(&v4);
    winrt::Windows::Foundation::IUnknown::operator=(&v8, a1 + 88);
    v2 = v8;
  }
  ReleaseSRWLockExclusive_0((PSRWLOCK)(a1 + 72));
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 24LL))(v2);
  v3 = (void (__fastcall *)(_QWORD))_InterlockedExchange64((volatile __int64 *)(a1 + 32), 1);
  if ( (unsigned __int64)v3 >= 2 )
    v3(*(_QWORD *)(a1 + 40));
  *(_QWORD *)(a1 + 32) = 0;
  winrt::Windows::Foundation::Handles::Internal::IProcessHandle::~IProcessHandle((winrt::Windows::Foundation::Handles::Internal::IProcessHandle *)&v8);
}

```

## disassembly

```asm
0x18008ae4c  push    rbp
0x18008ae4e  push    rbx
0x18008ae4f  push    rsi
0x18008ae50  push    rdi
0x18008ae51  mov     rbp, rsp
0x18008ae54  sub     rsp, 68h
0x18008ae58  mov     rdi, rcx
0x18008ae5b  xor     ebx, ebx
0x18008ae5d  mov     [rbp+arg_0], rbx
0x18008ae61  add     rcx, 48h ; 'H'; SRWLock
0x18008ae65  call    WINRT_IMPL_AcquireSRWLockExclusive
0x18008ae6a  mov     eax, [rdi+60h]
0x18008ae6d  test    eax, eax
0x18008ae6f  jnz     short loc_18008AEEF
0x18008ae71  mov     dword ptr [rdi+60h], 2
0x18008ae78  mov     [rbp+var_38], ebx
0x18008ae7b  xorps   xmm0, xmm0
0x18008ae7e  movdqu  [rbp+var_30], xmm0
0x18008ae83  lea     r8, [rbp+var_38]
0x18008ae87  mov     edx, cs:?error_canceled@impl@winrt@@3Uhresult@2@B; winrt::hresult const winrt::impl::error_canceled
0x18008ae8d  lea     rcx, [rbp+var_20]
0x18008ae91  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::impl::slim_source_location const &)
0x18008ae96  xorps   xmm0, xmm0
0x18008ae99  movdqu  [rbp+var_48], xmm0
0x18008ae9e  lea     rcx, [rbp+var_48]
0x18008aea2  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18008aea8  lea     r8, _TI2?AUhresult_canceled@winrt@@; throw info for 'struct winrt::hresult_canceled'
0x18008aeaf  lea     rdx, [rbp+var_20]
0x18008aeb3  lea     rcx, [rbp+var_48]
0x18008aeb7  call    cs:__imp_?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z; __ExceptionPtrCopyException(void *,void const *,void const *)
0x18008aebd  lea     rcx, [rbp+var_20]; this
0x18008aec1  call    ??1hresult_error@winrt@@QEAA@XZ; winrt::hresult_error::~hresult_error(void)
0x18008aec6  lea     rcx, [rdi+38h]
0x18008aeca  lea     rdx, [rbp+var_48]
0x18008aece  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18008aed4  lea     rcx, [rbp+var_48]
0x18008aed8  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18008aede  lea     rdx, [rdi+58h]
0x18008aee2  lea     rcx, [rbp+arg_0]
0x18008aee6  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x18008aeeb  mov     rbx, [rbp+arg_0]
0x18008aeef  lea     rcx, [rdi+48h]; SRWLock
0x18008aef3  call    ReleaseSRWLockExclusive_0
0x18008aef8  test    rbx, rbx
0x18008aefb  jz      short loc_18008AF0C
0x18008aefd  mov     rax, [rbx]
0x18008af00  mov     rcx, rbx
0x18008af03  mov     rax, [rax+18h]
0x18008af07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008af0c  mov     eax, 1
0x18008af11  xchg    rax, [rdi+20h]
0x18008af15  cmp     rax, 2
0x18008af19  jb      short loc_18008AF24
0x18008af1b  mov     rcx, [rdi+28h]
0x18008af1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008af24  nop
0x18008af25  mov     qword ptr [rdi+20h], 0
0x18008af2d  lea     rcx, [rbp+arg_0]; this
0x18008af31  call    ??1IProcessHandle@Internal@Handles@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::Handles::Internal::IProcessHandle::~IProcessHandle(void)
0x18008af36  nop
0x18008af37  add     rsp, 68h
0x18008af3b  pop     rdi
0x18008af3c  pop     rsi
0x18008af3d  pop     rbx
0x18008af3e  pop     rbp
0x18008af3f  retn
```
