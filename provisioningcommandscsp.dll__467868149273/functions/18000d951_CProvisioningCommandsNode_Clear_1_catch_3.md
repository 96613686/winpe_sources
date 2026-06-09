# _CProvisioningCommandsNode::Clear_::_1_::catch$3

- ea: `0x18000d951`
- end: `0x18000d98a`
- name: `_CProvisioningCommandsNode::Clear_::_1_::catch$3`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800079c0`

## pseudocode

```c
__int64 __fastcall CProvisioningCommandsNode::Clear_::_1_::catch_3(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 136),
                           (void *)0x1B,
                           (unsigned int)"admin\\prov\\launch\\csp\\clear.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000d951  mov     [rsp+arg_8], rdx
0x18000d956  push    rbp
0x18000d957  sub     rsp, 30h
0x18000d95b  mov     rbp, rdx
0x18000d95e  mov     rcx, [rbp+88h]; this
0x18000d965  lea     r8, aAdminProvLaunc_2; "admin\\prov\\launch\\csp\\clear.cpp"
0x18000d96c  mov     edx, 1Bh; void *
0x18000d971  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000d976  mov     [rbp+30h], eax
0x18000d979  mov     rax, 0
0x18000d983  add     rsp, 30h
0x18000d987  pop     rbp
0x18000d988  retn
```
