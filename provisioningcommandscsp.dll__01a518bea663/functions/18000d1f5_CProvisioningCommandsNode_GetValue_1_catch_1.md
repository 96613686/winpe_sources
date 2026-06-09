# _CProvisioningCommandsNode::GetValue_::_1_::catch$1

- ea: `0x18000d1f5`
- end: `0x18000d22e`
- name: `_CProvisioningCommandsNode::GetValue_::_1_::catch$1`
- size: `57`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007650`

## pseudocode

```c
__int64 __fastcall CProvisioningCommandsNode::GetValue_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 280),
                           (void *)0x43,
                           (int)"admin\\prov\\launch\\csp\\getvalue.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000d1f5  mov     [rsp+arg_8], rdx
0x18000d1fa  push    rbp
0x18000d1fb  sub     rsp, 30h
0x18000d1ff  mov     rbp, rdx
0x18000d202  mov     rcx, [rbp+118h]; this
0x18000d209  lea     r8, aAdminProvLaunc; "admin\\prov\\launch\\csp\\getvalue.cpp"
0x18000d210  mov     edx, 43h ; 'C'; void *
0x18000d215  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000d21a  mov     [rbp+30h], eax
0x18000d21d  mov     rax, 0
0x18000d227  add     rsp, 30h
0x18000d22b  pop     rbp
0x18000d22c  retn
```
