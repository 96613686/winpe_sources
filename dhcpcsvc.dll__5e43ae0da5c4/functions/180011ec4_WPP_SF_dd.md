# WPP_SF_dd

- ea: `0x180011ec4`
- end: `0x180011f01`
- name: `WPP_SF_dd`
- size: `61`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ac50`
- `0x18000d660`
- `0x18000fdc4`
- `0x180010198`

## callees

- `0x180003e70`

## pseudocode

```c
ULONG WPP_SF_dd(__int16 a1, USHORT a2, ULONGLONG a3, int a4, ...)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF
  va_list va; // [rsp+70h] [rbp+28h] BYREF

  va_start(va, a4);
  v5 = a4;
  return FastWppTraceMessage(a1, a2, a3, &v5, 4, va, 4, 0);
}

```

## disassembly

```asm
0x180011ec4  mov     r11, rsp
0x180011ec7  mov     [r11+20h], r9d
0x180011ecb  sub     rsp, 48h
0x180011ecf  mov     qword ptr [r11-10h], 0
0x180011ed7  lea     rax, [r11+28h]
0x180011edb  mov     r9d, 4
0x180011ee1  movzx   edx, dx
0x180011ee4  mov     [r11-18h], r9
0x180011ee8  mov     [r11-20h], rax
0x180011eec  mov     [r11-28h], r9
0x180011ef0  lea     r9, [r11+20h]
0x180011ef4  movzx   ecx, cx
0x180011ef7  call    FastWppTraceMessage
0x180011efc  add     rsp, 48h
0x180011f00  retn
```
