# PcaTracePrintf(char const *,uint,ulong,char const *,...)

- ea: `0x180002ee8`
- end: `0x180002f1a`
- name: `?PcaTracePrintf@@YAXPEBDIK0ZZ`
- size: `50`
- prototype: `void(const char *, unsigned int, unsigned int, const char *, ...)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1800012c0`
- `0x180001430`
- `0x180001870`
- `0x180001bd0`
- `0x180002210`
- `0x180007040`
- `0x1800082c0`
- `0x180008480`

## callees

- `0x180002f7c`

## pseudocode

```c
void PcaTracePrintf(const char *a1, int a2, int a3, char *a4, ...)
{
  va_list va; // [rsp+70h] [rbp+28h] BYREF

  va_start(va, a4);
  PcapTraceVPrintf(a1, a1, a2, a3, a4, va);
}

```

## disassembly

```asm
0x180002ee8  mov     r11, rsp
0x180002eeb  mov     [r11+20h], r9
0x180002eef  sub     rsp, 48h
0x180002ef3  lea     rax, [r11+28h]
0x180002ef7  mov     qword ptr [r11-18h], 0
0x180002eff  mov     [r11-20h], rax
0x180002f03  mov     [r11-28h], r9
0x180002f07  mov     r9d, r8d; unsigned int
0x180002f0a  mov     r8d, edx; unsigned int
0x180002f0d  mov     rdx, rcx; char *
0x180002f10  call    ?PcapTraceVPrintf@@YAXPEBD0IK0PEAD@Z; PcapTraceVPrintf(char const *,char const *,uint,ulong,char const *,char *)
0x180002f15  add     rsp, 48h
0x180002f19  retn
```
