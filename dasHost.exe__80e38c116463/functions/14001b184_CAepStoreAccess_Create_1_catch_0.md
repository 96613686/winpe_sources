# _CAepStoreAccess::Create_::_1_::catch$0

- ea: `0x14001b184`
- end: `0x14001b1a9`
- name: `_CAepStoreAccess::Create_::_1_::catch$0`
- size: `37`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CAepStoreAccess::Create_::_1_::catch_0(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 104) = -2147024882;
  return 0;
}

```

## disassembly

```asm
0x14001b184  mov     [rsp+arg_8], rdx
0x14001b189  push    rbp
0x14001b18a  sub     rsp, 20h
0x14001b18e  mov     rbp, rdx
0x14001b191  mov     dword ptr [rbp+68h], 8007000Eh
0x14001b198  mov     rax, 0
0x14001b1a2  add     rsp, 20h
0x14001b1a6  pop     rbp
0x14001b1a7  retn
```
