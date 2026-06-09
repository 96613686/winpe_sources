# winrt::impl::await_adapter_winrt::Windows::Foundation::IAsyncOperation_enum_winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus__1_::cancel_asynchronously$_ResumeCoro$1

- ea: `0x1800155f0`
- end: `0x1800156b0`
- name: `winrt::impl::await_adapter_winrt::Windows::Foundation::IAsyncOperation_enum_winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus__1_::cancel_asynchronously$_ResumeCoro$1`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180013310`

## callees

- `0x18000214c`
- `0x180003580`
- `0x18001465c`
- `0x1800154e8`
- `0x1800155f0`

## pseudocode

```c
void __fastcall winrt::impl::await_adapter_winrt::Windows::Foundation::IAsyncOperation_enum_winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus__1_::cancel_asynchronously__ResumeCoro_1(
        _WORD *a1)
{
  _WORD *v2; // rbx

  v2 = a1 + 4;
  switch ( a1[4] )
  {
    case 0xFFFF:
    case 3:
    case 5:
      goto LABEL_4;
    case 2:
      *v2 = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(a1, a1);
      break;
    case 4:
      winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncAction>::Cancel(a1 + 12);
LABEL_4:
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>((_QWORD *)v2 + 2);
      if ( a1[5] )
        operator delete(a1);
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x1800155f0  mov     [rsp+arg_10], rbx
0x1800155f5  mov     [rsp+arg_0], rcx
0x1800155fa  push    rdi
0x1800155fb  sub     rsp, 30h
0x1800155ff  mov     rdi, [rsp+38h+arg_0]
0x180015604  lea     rbx, [rdi+8]
0x180015608  mov     [rsp+38h+arg_8], rbx
0x18001560d  movzx   eax, word ptr [rbx]
0x180015610  mov     [rsp+38h+var_18], ax
0x180015615  inc     ax; switch 7 cases
0x180015618  cmp     ax, 6
0x18001561c  ja      short def_180015633; jumptable 0000000180015633 default case, cases 0,1
0x18001561e  movsx   rax, ax
0x180015622  lea     rdx, cs:180000000h
0x180015629  mov     ecx, ds:(jpt_180015633 - 180000000h)[rdx+rax*4]
0x180015630  add     rcx, rdx
0x180015633  jmp     rcx; switch jump
0x180015635  jmp     short loc_180015666; jumptable 0000000180015633 case 3
0x180015637  mov     byte ptr [rsp+38h+arg_8], 0; jumptable 0000000180015633 case 2
0x18001563c  mov     eax, 4
0x180015641  mov     [rbx], ax
0x180015644  mov     rdx, rdi
0x180015647  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@experimental@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::experimental::coroutine_handle<void>)
0x18001564c  jmp     short loc_180015686
0x18001564e  jmp     short loc_180015666; jumptable 0000000180015633 case 5
0x180015650  lea     rcx, [rbx+10h]; jumptable 0000000180015633 case 4
0x180015654  call    ?Cancel@?$consume_Windows_Foundation_IAsyncInfo@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncAction>::Cancel(void)
0x180015659  nop
0x18001565a  jmp     short loc_180015666; jumptable 0000000180015633 case -1
0x18001565c  mov     rdi, [rsp+38h+arg_0]
0x180015661  mov     rbx, [rsp+38h+arg_8]
0x180015666  lea     rcx, [rbx+10h]; jumptable 0000000180015633 case -1
0x18001566a  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18001566f  cmp     word ptr [rdi+0Ah], 0
0x180015674  jz      short loc_180015686
0x180015676  mov     edx, 20h ; ' '; unsigned __int64
0x18001567b  mov     rcx, rdi; void *
0x18001567e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015683  jmp     short loc_180015686
0x180015685  int     3; Trap to Debugger
0x180015686  mov     rbx, [rsp+38h+arg_10]
0x18001568b  add     rsp, 30h
0x18001568f  pop     rdi
0x180015690  retn
```
