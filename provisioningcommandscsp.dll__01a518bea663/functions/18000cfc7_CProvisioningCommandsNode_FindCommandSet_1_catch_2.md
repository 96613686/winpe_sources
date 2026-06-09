# _CProvisioningCommandsNode::FindCommandSet_::_1_::catch$2

- ea: `0x18000cfc7`
- end: `0x18000d000`
- name: `_CProvisioningCommandsNode::FindCommandSet_::_1_::catch$2`
- size: `57`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007650`

## string_xrefs

- `0x18000cfdb`: `admin\prov\launch\csp\provisioningcommandsnode.cpp`

## pseudocode

```c
__int64 __fastcall CProvisioningCommandsNode::FindCommandSet_::_1_::catch_2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 136),
                           (void *)0x10E,
                           (int)"admin\\prov\\launch\\csp\\provisioningcommandsnode.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000cfc7  mov     [rsp+arg_8], rdx
0x18000cfcc  push    rbp
0x18000cfcd  sub     rsp, 20h
0x18000cfd1  mov     rbp, rdx
0x18000cfd4  mov     rcx, [rbp+88h]; this
0x18000cfdb  lea     r8, aAdminProvLaunc_3; "admin\\prov\\launch\\csp\\provisioningc"...
0x18000cfe2  mov     edx, 10Eh; void *
0x18000cfe7  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000cfec  mov     [rbp+20h], eax
0x18000cfef  mov     rax, 0
0x18000cff9  add     rsp, 20h
0x18000cffd  pop     rbp
0x18000cffe  retn
```
