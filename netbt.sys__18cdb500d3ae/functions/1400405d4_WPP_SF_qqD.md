# WPP_SF_qqD

- ea: `0x1400405d4`
- end: `0x140040622`
- name: `WPP_SF_qqD`
- size: `78`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x14000efd4`
- `0x1400104d8`
- `0x14001c600`
- `0x14001dc00`
- `0x14001de0c`
- `0x140023e40`
- `0x140047f20`
- `0x14004bf14`
- `0x14004f81c`

## callees

- `0x140030bc8`

## pseudocode

```c
void WPP_SF_qqD(__int16 a1, USHORT a2, ULONGLONG a3, ...)
{
  __int64 v3; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+78h] [rbp+20h]
  __int64 v5; // [rsp+80h] [rbp+28h] BYREF
  va_list va1; // [rsp+80h] [rbp+28h]
  va_list va2; // [rsp+88h] [rbp+30h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v3 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v5 = va_arg(va2, _QWORD);
  FastWppTraceMessage(a1, a2, a3, va, 8, va1, 8, va2, 4, 0);
}

```

## disassembly

```asm
0x1400405d4  mov     r11, rsp
0x1400405d7  mov     [r11+20h], r9
0x1400405db  sub     rsp, 58h
0x1400405df  mov     qword ptr [r11-10h], 0
0x1400405e7  lea     rax, [r11+30h]
0x1400405eb  mov     qword ptr [r11-18h], 4
0x1400405f3  mov     r9d, 8
0x1400405f9  mov     [r11-20h], rax
0x1400405fd  lea     rax, [r11+28h]
0x140040601  mov     [r11-28h], r9
0x140040605  mov     [r11-30h], rax
0x140040609  mov     [r11-38h], r9
0x14004060d  lea     r9, [r11+20h]
0x140040611  movzx   edx, dx
0x140040614  movzx   ecx, cx
0x140040617  call    FastWppTraceMessage
0x14004061c  add     rsp, 58h
0x140040620  retn
```
