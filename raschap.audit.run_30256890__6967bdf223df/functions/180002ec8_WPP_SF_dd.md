# WPP_SF_dd

- ea: `0x180002ec8`
- end: `0x180002f0d`
- name: `WPP_SF_dd`
- size: `69`
- prototype: ``
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x1800019b0`
- `0x1800042f0`
- `0x180007370`
- `0x180008938`
- `0x18000b9b4`
- `0x18000cd68`
- `0x18000e120`
- `0x18000ead0`
- `0x1800106f4`
- `0x18001b9c8`
- `0x18001be60`
- `0x18001e494`
- `0x180023d74`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180002f02`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180002f02`

## pseudocode

```c
ULONG WPP_SF_dd(TRACEHANDLE a1, USHORT a2, const GUID *a3, int a4, ...)
{
  int v5; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
  v5 = a4;
  return TraceMessage(a1, 0x2Bu, a3, a2, &v5, 4, va, 4, 0);
}

```

## disassembly

```asm
0x180002ec8  mov     r11, rsp
0x180002ecb  mov     [r11+20h], r9d
0x180002ecf  sub     rsp, 58h
0x180002ed3  mov     qword ptr [r11-18h], 0
0x180002edb  lea     rax, [r11+28h]
0x180002edf  mov     r9d, 4
0x180002ee5  mov     [r11-20h], r9
0x180002ee9  mov     [r11-28h], rax
0x180002eed  lea     rax, [r11+20h]
0x180002ef1  mov     [r11-30h], r9
0x180002ef5  movzx   r9d, dx; MessageNumber
0x180002ef9  mov     edx, 2Bh ; '+'; MessageFlags
0x180002efe  mov     [r11-38h], rax
0x180002f02  call    cs:__imp_TraceMessage
0x180002f08  add     rsp, 58h
0x180002f0c  retn
```
