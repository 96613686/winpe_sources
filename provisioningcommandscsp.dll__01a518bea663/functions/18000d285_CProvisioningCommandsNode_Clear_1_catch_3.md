# _CProvisioningCommandsNode::Clear_::_1_::catch$3

- ea: `0x18000d285`
- end: `0x18000d2be`
- name: `_CProvisioningCommandsNode::Clear_::_1_::catch$3`
- size: `57`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007650`

## pseudocode

```c
__int64 __fastcall CProvisioningCommandsNode::Clear_::_1_::catch_3(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 136),
                           (void *)0x1B,
                           (int)"admin\\prov\\launch\\csp\\clear.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000d285  mov     [rsp+arg_8], rdx
0x18000d28a  push    rbp
0x18000d28b  sub     rsp, 30h
0x18000d28f  mov     rbp, rdx
0x18000d292  mov     rcx, [rbp+88h]; this
0x18000d299  lea     r8, aAdminProvLaunc_2; "admin\\prov\\launch\\csp\\clear.cpp"
0x18000d2a0  mov     edx, 1Bh; void *
0x18000d2a5  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000d2aa  mov     [rbp+30h], eax
0x18000d2ad  mov     rax, 0
0x18000d2b7  add     rsp, 30h
0x18000d2bb  pop     rbp
0x18000d2bc  retn
```
