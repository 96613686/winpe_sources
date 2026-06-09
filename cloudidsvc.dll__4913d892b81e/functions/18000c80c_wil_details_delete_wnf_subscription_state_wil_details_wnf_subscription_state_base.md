# wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *)

- ea: `0x18000c80c`
- end: `0x18000c82a`
- name: `?delete_wnf_subscription_state@details@wil@@YAXPEAUwnf_subscription_state_base@12@@Z`
- size: `30`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::details::wnf_subscription_state_base *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a8c4`
- `0x18000cb1c`

## callees

- `0x18000c80c`
- `0x180012010`

## pseudocode

```c
void __fastcall wil::details::delete_wnf_subscription_state(
        wil::details *this,
        struct wil::details::wnf_subscription_state_base *a2)
{
  if ( this )
    (**(void (__fastcall ***)(wil::details *, __int64))this)(this, 1);
}

```

## disassembly

```asm
0x18000c80c  sub     rsp, 28h
0x18000c810  test    rcx, rcx
0x18000c813  jz      short loc_18000C825
0x18000c815  mov     rax, [rcx]
0x18000c818  mov     edx, 1
0x18000c81d  mov     rax, [rax]
0x18000c820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c825  add     rsp, 28h
0x18000c829  retn
```
