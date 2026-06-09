# _CreateBucket_::_1_::catch$18

- ea: `0x14000c9f5`
- end: `0x14000ca1a`
- name: `_CreateBucket_::_1_::catch$18`
- size: `37`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CreateBucket_::_1_::catch_18(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 56) = -2147024882;
  return 0;
}

```

## disassembly

```asm
0x14000c9f5  mov     [rsp+arg_8], rdx
0x14000c9fa  push    rbp
0x14000c9fb  sub     rsp, 30h
0x14000c9ff  mov     rbp, rdx
0x14000ca02  mov     dword ptr [rbp+38h], 8007000Eh
0x14000ca09  mov     rax, 0
0x14000ca13  add     rsp, 30h
0x14000ca17  pop     rbp
0x14000ca18  retn
```
