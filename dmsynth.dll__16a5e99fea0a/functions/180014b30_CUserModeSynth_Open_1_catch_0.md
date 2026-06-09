# _CUserModeSynth::Open_::_1_::catch$0

- ea: `0x180014b30`
- end: `0x180014b5d`
- name: `_CUserModeSynth::Open_::_1_::catch$0`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CUserModeSynth::Open_::_1_::catch_0(__int64 a1, __int64 a2)
{
  *(_QWORD *)(*(_QWORD *)(a2 + 160) + 56LL) = 0;
  return 0;
}

```

## disassembly

```asm
0x180014b30  mov     [rsp+arg_8], rdx
0x180014b35  push    rbp
0x180014b36  sub     rsp, 20h
0x180014b3a  mov     rbp, rdx
0x180014b3d  mov     rax, [rbp+0A0h]
0x180014b44  mov     qword ptr [rax+38h], 0
0x180014b4c  mov     rax, 0
0x180014b56  add     rsp, 20h
0x180014b5a  pop     rbp
0x180014b5b  retn
```
