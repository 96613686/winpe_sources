# FormatRRASErrorString

- ea: `0x18002b0dc`
- end: `0x18002b10d`
- name: `FormatRRASErrorString`
- size: `49`
- prototype: ``
- caller_count: `157`
- callee_count: `1`
- tags: ``

## callers

- `0x180001e0c`
- `0x1800023c0`
- `0x18000339c`
- `0x180003568`
- `0x1800036f8`
- `0x18000380c`
- `0x18000423c`
- `0x18000442c`
- `0x1800049e4`
- `0x180005054`
- `0x180005380`
- `0x1800055b0`
- `0x180005698`
- `0x180005908`
- `0x18000638c`
- `0x180006970`
- `0x180007bd0`
- `0x180008630`
- `0x180008d10`
- `0x180009920`
- `0x180009aac`
- `0x180009cd0`
- `0x180009fd0`
- `0x18000a280`
- `0x18000a4c0`
- `0x18000a6e0`
- `0x18000a790`
- `0x18000a8c0`
- `0x18000a9f0`
- `0x18000b2e8`
- `0x18000b580`
- `0x18000b720`
- `0x18000bc54`
- `0x18000be68`
- `0x18000c050`
- `0x18000c234`
- `0x18000c8d4`
- `0x18000cc7c`
- `0x18000cdc8`
- `0x18000cf3c`
- `0x18000d450`
- `0x18000d6b4`
- `0x18000d8b4`
- `0x18000dd20`
- `0x18000dfac`
- `0x18000e358`
- `0x18000e540`
- `0x18000e7a4`
- `0x18000eb90`
- `0x18000ecac`

## callees

- `0x18002b08c`

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
0x18002b0dc  mov     r11, rsp
0x18002b0df  mov     [r11+10h], rdx
0x18002b0e3  mov     [r11+18h], r8
0x18002b0e7  mov     [r11+20h], r9
0x18002b0eb  sub     rsp, 48h
0x18002b0ef  lea     rax, [r11+18h]
0x18002b0f3  mov     qword ptr [r11-18h], 0
0x18002b0fb  mov     r9, rdx; pszFormat
0x18002b0fe  mov     [r11-28h], rax
0x18002b102  call    StringVPrintfWorkerW
0x18002b107  add     rsp, 48h
0x18002b10b  retn
```
