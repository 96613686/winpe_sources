# WPP_SF_qDD

- ea: `0x180007dd0`
- end: `0x180007e25`
- name: `WPP_SF_qDD`
- size: `85`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180006c20`
- `0x180006d30`
- `0x18000a620`
- `0x18000a6e0`
- `0x18000a7a0`
- `0x18000a860`
- `0x18000d830`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180007e1a`
- `ADVAPI32!TraceMessage` at `0x180007e1a`

## pseudocode

```c
ULONG WPP_SF_qDD(TRACEHANDLE a1, USHORT a2, const GUID *a3, ...)
{
  __int64 v4; // [rsp+88h] [rbp+20h] BYREF
  va_list va; // [rsp+88h] [rbp+20h]
  __int64 v6; // [rsp+90h] [rbp+28h] BYREF
  va_list va1; // [rsp+90h] [rbp+28h]
  va_list va2; // [rsp+98h] [rbp+30h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v4 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v6 = va_arg(va2, _QWORD);
  return TraceMessage(a1, 0x2Bu, a3, a2, va, 8, va1, 4, va2, 4, 0);
}

```

## disassembly

```asm
0x180007dd0  mov     r11, rsp
0x180007dd3  mov     [r11+20h], r9
0x180007dd7  sub     rsp, 68h
0x180007ddb  mov     qword ptr [r11-18h], 0
0x180007de3  lea     rax, [r11+30h]
0x180007de7  mov     r9d, 4
0x180007ded  mov     [r11-20h], r9
0x180007df1  mov     [r11-28h], rax
0x180007df5  lea     rax, [r11+28h]
0x180007df9  mov     [r11-30h], r9
0x180007dfd  mov     [r11-38h], rax
0x180007e01  lea     rax, [r11+20h]
0x180007e05  movzx   r9d, dx; MessageNumber
0x180007e09  mov     edx, 2Bh ; '+'; MessageFlags
0x180007e0e  mov     qword ptr [r11-40h], 8
0x180007e16  mov     [r11-48h], rax
0x180007e1a  call    cs:__imp_TraceMessage
0x180007e20  add     rsp, 68h
0x180007e24  retn
```
