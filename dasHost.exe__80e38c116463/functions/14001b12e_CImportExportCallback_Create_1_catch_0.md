# _CImportExportCallback::Create_::_1_::catch$0

- ea: `0x14001b12e`
- end: `0x14001b153`
- name: `_CImportExportCallback::Create_::_1_::catch$0`
- size: `37`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CImportExportCallback::Create_::_1_::catch_0(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 32) = -2147024882;
  return 0;
}

```

## disassembly

```asm
0x14001b12e  mov     [rsp+arg_8], rdx
0x14001b133  push    rbp
0x14001b134  sub     rsp, 20h
0x14001b138  mov     rbp, rdx
0x14001b13b  mov     dword ptr [rbp+20h], 8007000Eh
0x14001b142  mov     rax, 0
0x14001b14c  add     rsp, 20h
0x14001b150  pop     rbp
0x14001b151  retn
```
