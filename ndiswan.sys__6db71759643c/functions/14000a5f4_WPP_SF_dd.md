# WPP_SF_dd

- ea: `0x14000a5f4`
- end: `0x14000a63f`
- name: `WPP_SF_dd`
- size: `75`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `28`
- callee_count: `1`
- tags: ``

## callers

- `0x140003c30`
- `0x140007fb0`
- `0x14000c6e0`
- `0x140010a1c`
- `0x140010b40`
- `0x140026c80`
- `0x1400274e0`
- `0x140027a50`
- `0x140027da0`
- `0x140027fe0`
- `0x140028610`
- `0x1400288a0`
- `0x140028dc0`
- `0x140028f60`
- `0x1400296d0`
- `0x140029850`
- `0x140029a50`
- `0x140029b70`
- `0x14002a0f0`
- `0x14002a4e0`
- `0x14002aa40`
- `0x14002b270`
- `0x14002bab0`
- `0x14002bd20`
- `0x14002c7c0`
- `0x14002d7dc`
- `0x14002eed4`
- `0x1400330a0`

## callees

- `0x140016230`

## pseudocode

```c
__int64 WPP_SF_dd(__int64 a1, unsigned __int16 a2, __int64 a3, int a4, ...)
{
  int v5; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
  v5 = a4;
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, int *, __int64, __int64 *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           &v5,
           4,
           (__int64 *)va,
           4,
           0);
}

```

## disassembly

```asm
0x14000a5f4  mov     r11, rsp
0x14000a5f7  mov     [r11+20h], r9d
0x14000a5fb  sub     rsp, 58h
0x14000a5ff  mov     rax, cs:pfnWppTraceMessage
0x14000a606  lea     r9, [r11+28h]
0x14000a60a  mov     qword ptr [r11-18h], 0
0x14000a612  mov     r10d, 4
0x14000a618  mov     [r11-20h], r10
0x14000a61c  mov     [r11-28h], r9
0x14000a620  lea     r9, [r11+20h]
0x14000a624  mov     [r11-30h], r10
0x14000a628  mov     [r11-38h], r9
0x14000a62c  movzx   r9d, dx
0x14000a630  lea     edx, [r10+27h]
0x14000a634  call    _guard_dispatch_icall
0x14000a639  add     rsp, 58h
0x14000a63d  retn
```
