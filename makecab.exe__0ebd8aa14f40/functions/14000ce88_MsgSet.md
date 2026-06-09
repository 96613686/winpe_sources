# MsgSet

- ea: `0x14000ce88`
- end: `0x14000ceb9`
- name: `MsgSet`
- size: `49`
- prototype: ``
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x140003310`
- `0x140003748`
- `0x1400038b8`
- `0x140003f68`
- `0x14000488c`
- `0x140005770`
- `0x140006030`
- `0x1400062e0`
- `0x140006a6c`
- `0x140007934`
- `0x14000b128`
- `0x14000bbe0`
- `0x14000cdec`
- `0x14000dcf8`
- `0x14000e1f4`

## callees

- `0x14000cec0`

## pseudocode

```c
__int64 MsgSet(char *a1, int a2, const char *a3, char *a4, ...)
{
  va_list va; // [rsp+70h] [rbp+28h] BYREF

  va_start(va, a4);
  return MsgSetWorker(a1, a2, a3, a4, (__int64 *)va);
}

```

## disassembly

```asm
0x14000ce88  mov     rax, rsp
0x14000ce8b  mov     [rax+18h], r8
0x14000ce8f  mov     [rax+20h], r9
0x14000ce93  sub     rsp, 48h
0x14000ce97  lea     r9, [rax+20h]
0x14000ce9b  mov     qword ptr [rax-18h], 0
0x14000cea3  add     r9, 8
0x14000cea7  mov     [rax-28h], r9
0x14000ceab  mov     r9, [r9-8]
0x14000ceaf  call    MsgSetWorker
0x14000ceb4  add     rsp, 48h
0x14000ceb8  retn
```
