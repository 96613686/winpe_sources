# Microsoft::WRL::Details::DelegateArgTraits_long_(__cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_HSTRING_____::_)(Windows::Foundation::IAsyncOperation_HSTRING________enum_ABI::Windows::Foundation::AsyncStatus)_::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::Foundation::IAsyncOperationCompletedHandler_HSTRING______Microsoft::WRL::FtmBase___lambda_3e59cf71de9fa25b6f7d6f3697c38bba__&__1_Windows::Foundation::IAsyncOperation_HSTRING________enum_ABI::Windows::Foundation::AsyncStatus_::Invoke

- ea: `0x1801faf90`
- end: `0x1801fb007`
- name: `Microsoft::WRL::Details::DelegateArgTraits_long_(__cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_HSTRING_____::_)(Windows::Foundation::IAsyncOperation_HSTRING________enum_ABI::Windows::Foundation::AsyncStatus)_::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::Foundation::IAsyncOperationCompletedHandler_HSTRING______Microsoft::WRL::FtmBase___lambda_3e59cf71de9fa25b6f7d6f3697c38bba__&__1_Windows::Foundation::IAsyncOperation_HSTRING________enum_ABI::Windows::Foundation::AsyncStatus_::Invoke`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1801f83e0`
- `0x1801faf90`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1801fafe3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1801fafe3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fafb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fafb9`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_HSTRING_____::___Windows::Foundation::IAsyncOperation_HSTRING________enum_ABI::Windows::Foundation::AsyncStatus__::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::Foundation::IAsyncOperationCompletedHandler_HSTRING______Microsoft::WRL::FtmBase___lambda_3e59cf71de9fa25b6f7d6f3697c38bba_____1_Windows::Foundation::IAsyncOperation_HSTRING________enum_ABI::Windows::Foundation::AsyncStatus_::Invoke(
        __int64 a1,
        __int64 a2,
        int a3)
{
  int v5; // ebx
  HSTRING *v6; // rbx
  __int64 (__fastcall *v7)(__int64, HSTRING *); // rdi

  v5 = -2147467259;
  if ( a3 == 1 )
  {
    v6 = *(HSTRING **)(a1 + 72);
    v7 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 64LL);
    WindowsDeleteString(*v6);
    *v6 = 0;
    v5 = v7(a2, v6);
  }
  SetEvent(**(HANDLE **)(a1 + 64));
  if ( v5 < 0 )
    Microsoft::WRL::DelegateTraits<-1>::EnsureStackSnapshot((unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1801faf90  push    rbx
0x1801faf92  push    rsi
0x1801faf93  push    rdi
0x1801faf94  push    r14
0x1801faf96  sub     rsp, 28h
0x1801faf9a  mov     r14, rdx
0x1801faf9d  mov     rsi, rcx
0x1801fafa0  mov     ebx, 80004005h
0x1801fafa5  cmp     r8d, 1
0x1801fafa9  jnz     short loc_1801FAFDC
0x1801fafab  mov     rbx, [rcx+48h]
0x1801fafaf  mov     rax, [rdx]
0x1801fafb2  mov     rcx, [rbx]; string
0x1801fafb5  mov     rdi, [rax+40h]
0x1801fafb9  call    cs:__imp_WindowsDeleteString
0x1801fafc0  nop     dword ptr [rax+rax+00h]
0x1801fafc5  mov     rdx, rbx
0x1801fafc8  mov     qword ptr [rbx], 0
0x1801fafcf  mov     rcx, r14
0x1801fafd2  mov     rax, rdi
0x1801fafd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fafda  mov     ebx, eax
0x1801fafdc  mov     rcx, [rsi+40h]
0x1801fafe0  mov     rcx, [rcx]; hEvent
0x1801fafe3  call    cs:__imp_SetEvent
0x1801fafea  nop     dword ptr [rax+rax+00h]
0x1801fafef  test    ebx, ebx
0x1801faff1  jns     short loc_1801FAFFA
0x1801faff3  mov     ecx, ebx
0x1801faff5  call    ?EnsureStackSnapshot@?$DelegateTraits@$0?0@WRL@Microsoft@@SAXJ@Z; Microsoft::WRL::DelegateTraits<-1>::EnsureStackSnapshot(long)
0x1801faffa  mov     eax, ebx
0x1801faffc  add     rsp, 28h
0x1801fb000  pop     r14
0x1801fb002  pop     rdi
0x1801fb003  pop     rsi
0x1801fb004  pop     rbx
0x1801fb005  retn
```
