# _CProvisioningNode::RemoveRequestByName_::_1_::catch$5

- ea: `0x18003633d`
- end: `0x180036373`
- name: `_CProvisioningNode::RemoveRequestByName_::_1_::catch$5`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008d30`

## string_xrefs

- `0x18003634e`: `onecoreuap\admin\prov\provcsp\deletechild.cpp`

## pseudocode

```c
__int64 __fastcall CProvisioningNode::RemoveRequestByName_::_1_::catch_5(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 120),
                           (void *)0x4F,
                           (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\deletechild.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18003633d  mov     [rsp+arg_8], rdx
0x180036342  push    rbp
0x180036343  sub     rsp, 20h
0x180036347  mov     rbp, rdx
0x18003634a  mov     rcx, [rbp+78h]; this
0x18003634e  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\provcsp\\delet"...
0x180036355  mov     edx, 4Fh ; 'O'; void *
0x18003635a  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18003635f  mov     [rbp+30h], eax
0x180036362  mov     rax, 0
0x18003636c  add     rsp, 20h
0x180036370  pop     rbp
0x180036371  retn
```
