# _CDevnodeInterface::Create_::_1_::catch$0

- ea: `0x14001ada9`
- end: `0x14001adce`
- name: `_CDevnodeInterface::Create_::_1_::catch$0`
- size: `37`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CDevnodeInterface::Create_::_1_::catch_0(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 56) = -2147024882;
  return 0;
}

```

## disassembly

```asm
0x14001ada9  mov     [rsp+arg_8], rdx
0x14001adae  push    rbp
0x14001adaf  sub     rsp, 20h
0x14001adb3  mov     rbp, rdx
0x14001adb6  mov     dword ptr [rbp+38h], 8007000Eh
0x14001adbd  mov     rax, 0
0x14001adc7  add     rsp, 20h
0x14001adcb  pop     rbp
0x14001adcc  retn
```
