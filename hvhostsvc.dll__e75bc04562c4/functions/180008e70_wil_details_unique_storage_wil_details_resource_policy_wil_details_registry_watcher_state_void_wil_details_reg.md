# wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)

- ea: `0x180008e70`
- end: `0x180008e9b`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z`
- size: `43`
- prototype: `void __fastcall(wil::details::registry_watcher_state **, wil::details::registry_watcher_state *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800084f4`
- `0x180008818`
- `0x180008c58`

## callees

- `0x180008afc`
- `0x180008e70`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(
        wil::details::registry_watcher_state **a1,
        wil::details::registry_watcher_state *a2)
{
  wil::details::registry_watcher_state *v4; // rcx

  v4 = *a1;
  if ( v4 )
    wil::details::close_invoke_helper<1,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wil::details::registry_watcher_state *>::close_reset(v4);
  *a1 = a2;
}

```

## disassembly

```asm
0x180008e70  mov     [rsp+arg_0], rbx
0x180008e75  push    rdi
0x180008e76  sub     rsp, 20h
0x180008e7a  mov     rbx, rcx
0x180008e7d  mov     rdi, rdx
0x180008e80  mov     rcx, [rcx]; this
0x180008e83  test    rcx, rcx
0x180008e86  jz      short loc_180008E8D
0x180008e88  call    ?close_reset@?$close_invoke_helper@$00P6AXPEAUregistry_watcher_state@details@wil@@@Z$1?delete_registry_watcher_state@23@YAX0@ZPEAU123@@details@wil@@SAXPEAUregistry_watcher_state@23@@Z; wil::details::close_invoke_helper<1,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wil::details::registry_watcher_state *>::close_reset(wil::details::registry_watcher_state *)
0x180008e8d  mov     [rbx], rdi
0x180008e90  mov     rbx, [rsp+28h+arg_0]
0x180008e95  add     rsp, 20h
0x180008e99  pop     rdi
0x180008e9a  retn
```
