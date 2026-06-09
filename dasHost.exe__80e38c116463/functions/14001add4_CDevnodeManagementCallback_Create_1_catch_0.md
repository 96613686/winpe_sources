# _CDevnodeManagementCallback::Create_::_1_::catch$0

- ea: `0x14001add4`
- end: `0x14001adf9`
- name: `_CDevnodeManagementCallback::Create_::_1_::catch$0`
- size: `37`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CDevnodeManagementCallback::Create_::_1_::catch_0(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 112) = -2147024882;
  return 0;
}

```

## disassembly

```asm
0x14001add4  mov     [rsp+arg_8], rdx
0x14001add9  push    rbp
0x14001adda  sub     rsp, 20h
0x14001adde  mov     rbp, rdx
0x14001ade1  mov     dword ptr [rbp+70h], 8007000Eh
0x14001ade8  mov     rax, 0
0x14001adf2  add     rsp, 20h
0x14001adf6  pop     rbp
0x14001adf7  retn
```
