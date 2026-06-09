# FormatRRASErrorString

- ea: `0x18002a138`
- end: `0x18002a168`
- name: `FormatRRASErrorString`
- size: `48`
- prototype: `__int64(_QWORD, _QWORD, ...)`
- caller_count: `157`
- callee_count: `1`
- tags: ``

## callers

- `0x180001e00`
- `0x1800023a8`
- `0x180003308`
- `0x1800034d4`
- `0x180003660`
- `0x180003770`
- `0x18000419c`
- `0x180004388`
- `0x1800048e8`
- `0x180004eac`
- `0x1800051a0`
- `0x1800053c0`
- `0x1800054a8`
- `0x180005704`
- `0x180006118`
- `0x1800066d0`
- `0x1800078e0`
- `0x180008320`
- `0x1800089b0`
- `0x180009560`
- `0x1800096e8`
- `0x180009900`
- `0x180009c00`
- `0x180009eb0`
- `0x18000a0f0`
- `0x18000a310`
- `0x18000a3c0`
- `0x18000a4f0`
- `0x18000a610`
- `0x18000aed4`
- `0x18000b170`
- `0x18000b310`
- `0x18000b834`
- `0x18000ba40`
- `0x18000bc28`
- `0x18000be0c`
- `0x18000c4ac`
- `0x18000c854`
- `0x18000c9a0`
- `0x18000cb10`
- `0x18000d020`
- `0x18000d284`
- `0x18000d480`
- `0x18000d8e4`
- `0x18000db70`
- `0x18000df18`
- `0x18000e100`
- `0x18000e364`
- `0x18000e750`
- `0x18000e86c`

## callees

- `0x18002a0e8`

## pseudocode

```c
HRESULT FormatRRASErrorString(wchar_t *a1, const wchar_t *a2, ...)
{
  size_t *v3; // [rsp+60h] [rbp+18h] BYREF
  va_list va; // [rsp+60h] [rbp+18h]
  va_list va1; // [rsp+68h] [rbp+20h] BYREF

  va_start(va1, a2);
  va_start(va, a2);
  v3 = va_arg(va1, size_t *);
  return StringVPrintfWorkerW(a1, (size_t)a2, v3, a2, va);
}

```

## disassembly

```asm
0x18002a138  mov     r11, rsp
0x18002a13b  mov     [r11+10h], rdx
0x18002a13f  mov     [r11+18h], r8
0x18002a143  mov     [r11+20h], r9
0x18002a147  sub     rsp, 48h
0x18002a14b  lea     rax, [r11+18h]
0x18002a14f  mov     qword ptr [r11-18h], 0
0x18002a157  mov     r9, rdx; pszFormat
0x18002a15a  mov     [r11-28h], rax
0x18002a15e  call    StringVPrintfWorkerW
0x18002a163  add     rsp, 48h
0x18002a167  retn
```
