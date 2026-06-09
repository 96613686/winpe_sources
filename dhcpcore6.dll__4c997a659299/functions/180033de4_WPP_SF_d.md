# WPP_SF_d

- ea: `0x180033de4`
- end: `0x180033e14`
- name: `WPP_SF_d`
- size: `48`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `44`
- callee_count: `1`
- tags: ``

## callers

- `0x180003cc0`
- `0x180005368`
- `0x1800062e8`
- `0x180006468`
- `0x180006ed8`
- `0x180007a80`
- `0x180008440`
- `0x18000890c`
- `0x18000c264`
- `0x18000ce60`
- `0x18000d340`
- `0x180010fd4`
- `0x180013028`
- `0x180014590`
- `0x1800152b8`
- `0x1800173fc`
- `0x180018934`
- `0x180018ac0`
- `0x180018c6c`
- `0x180018cb8`
- `0x180018e7c`
- `0x180019250`
- `0x18001be30`
- `0x18001cb0c`
- `0x18001d4c4`
- `0x18001d640`
- `0x18001dc84`
- `0x18001e5c0`
- `0x18001f0d8`
- `0x180020610`
- `0x1800206ac`
- `0x180020d50`
- `0x180021150`
- `0x180028764`
- `0x180029104`
- `0x18002a454`
- `0x18002d79c`
- `0x18002e32c`
- `0x18002e500`
- `0x18002e6d4`
- `0x18002e800`
- `0x18002ec28`
- `0x18002ecb0`
- `0x18002ed94`

## callees

- `0x180017a20`

## pseudocode

```c
ULONG __fastcall WPP_SF_d(__int16 a1, USHORT a2, ULONGLONG a3, int a4)
{
  int v5; // [rsp+58h] [rbp+20h] BYREF

  v5 = a4;
  return FastWppTraceMessage(a1, a2, a3, &v5, 4, 0);
}

```

## disassembly

```asm
0x180033de4  mov     rax, rsp
0x180033de7  mov     [rax+20h], r9d
0x180033deb  sub     rsp, 38h
0x180033def  mov     qword ptr [rax-10h], 0
0x180033df7  lea     r9, [rax+20h]
0x180033dfb  movzx   edx, dx
0x180033dfe  movzx   ecx, cx
0x180033e01  mov     qword ptr [rax-18h], 4
0x180033e09  call    FastWppTraceMessage
0x180033e0e  add     rsp, 38h
0x180033e12  retn
```
