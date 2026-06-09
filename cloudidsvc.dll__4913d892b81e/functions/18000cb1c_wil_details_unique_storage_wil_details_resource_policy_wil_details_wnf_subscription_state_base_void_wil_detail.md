# wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset(wil::details::wnf_subscription_state_base *)

- ea: `0x18000cb1c`
- end: `0x18000cb68`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUwnf_subscription_state_base@23@@Z`
- size: `76`
- prototype: `void __fastcall(wil::details **, wil::details *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180009e80`
- `0x18000a93c`

## callees

- `0x1800040f4`
- `0x180004740`
- `0x18000c80c`
- `0x18000cb1c`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset(
        wil::details **a1,
        wil::details *a2)
{
  wil::details *v2; // rdi
  struct wil::details::wnf_subscription_state_base *v5; // rdx
  char v6; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v6);
    wil::details::delete_wnf_subscription_state(v2, v5);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v6);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x18000cb1c  mov     [rsp+arg_8], rbx
0x18000cb21  mov     [rsp+arg_10], rsi
0x18000cb26  push    rdi
0x18000cb27  sub     rsp, 20h
0x18000cb2b  mov     rdi, [rcx]
0x18000cb2e  mov     rsi, rdx
0x18000cb31  mov     rbx, rcx
0x18000cb34  test    rdi, rdi
0x18000cb37  jz      short loc_18000CB55
0x18000cb39  lea     rcx, [rsp+28h+arg_0]; this
0x18000cb3e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000cb43  mov     rcx, rdi; this
0x18000cb46  call    ?delete_wnf_subscription_state@details@wil@@YAXPEAUwnf_subscription_state_base@12@@Z; wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *)
0x18000cb4b  lea     rcx, [rsp+28h+arg_0]; this
0x18000cb50  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000cb55  mov     [rbx], rsi
0x18000cb58  mov     rbx, [rsp+28h+arg_8]
0x18000cb5d  mov     rsi, [rsp+28h+arg_10]
0x18000cb62  add     rsp, 20h
0x18000cb66  pop     rdi
0x18000cb67  retn
```
