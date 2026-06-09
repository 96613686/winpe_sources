# WPP_SF_DDD

- ea: `0x1400052a0`
- end: `0x1400052f7`
- name: `WPP_SF_DDD`
- size: `87`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140002b38`
- `0x140008a54`
- `0x14001308c`
- `0x140022320`
- `0x140042670`
- `0x140042740`
- `0x1400429c0`

## callees

- `0x14002c710`

## pseudocode

```c
__int64 WPP_SF_DDD(__int64 a1, unsigned __int16 a2, __int64 a3, int a4, ...)
{
  int v5; // [rsp+88h] [rbp+20h] BYREF
  __int64 v6; // [rsp+90h] [rbp+28h] BYREF
  va_list va; // [rsp+90h] [rbp+28h]
  va_list va1; // [rsp+98h] [rbp+30h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v6 = va_arg(va1, _QWORD);
  v5 = a4;
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, int *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           &v5,
           4,
           (__int64 *)va,
           4,
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x1400052a0  mov     r11, rsp
0x1400052a3  mov     [r11+20h], r9d
0x1400052a7  sub     rsp, 68h
0x1400052ab  mov     rax, cs:pfnWppTraceMessage
0x1400052b2  lea     r9, [r11+30h]
0x1400052b6  mov     qword ptr [r11-18h], 0
0x1400052be  mov     r10d, 4
0x1400052c4  mov     [r11-20h], r10
0x1400052c8  mov     [r11-28h], r9
0x1400052cc  lea     r9, [r11+28h]
0x1400052d0  mov     [r11-30h], r10
0x1400052d4  mov     [r11-38h], r9
0x1400052d8  lea     r9, [r11+20h]
0x1400052dc  mov     [r11-40h], r10
0x1400052e0  mov     [r11-48h], r9
0x1400052e4  movzx   r9d, dx
0x1400052e8  lea     edx, [r10+27h]
0x1400052ec  call    _guard_dispatch_icall
0x1400052f1  add     rsp, 68h
0x1400052f5  retn
```
