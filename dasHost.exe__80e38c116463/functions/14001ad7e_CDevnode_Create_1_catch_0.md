# _CDevnode::Create_::_1_::catch$0

- ea: `0x14001ad7e`
- end: `0x14001ada3`
- name: `_CDevnode::Create_::_1_::catch$0`
- size: `37`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CDevnode::Create_::_1_::catch_0(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 48) = -2147024882;
  return 0;
}

```

## disassembly

```asm
0x14001ad7e  mov     [rsp+arg_8], rdx
0x14001ad83  push    rbp
0x14001ad84  sub     rsp, 20h
0x14001ad88  mov     rbp, rdx
0x14001ad8b  mov     dword ptr [rbp+30h], 8007000Eh
0x14001ad92  mov     rax, 0
0x14001ad9c  add     rsp, 20h
0x14001ada0  pop     rbp
0x14001ada1  retn
```
