# WPP_SF_q

- ea: `0x140001bc8`
- end: `0x140001c06`
- name: `WPP_SF_q`
- size: `62`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `34`
- callee_count: `1`
- tags: ``

## callers

- `0x140001e40`
- `0x140001fb0`
- `0x140002100`
- `0x1400024b0`
- `0x140002670`
- `0x140002fd0`
- `0x140003730`
- `0x140003940`
- `0x140004a40`
- `0x140004ad0`
- `0x1400062c0`
- `0x140007940`
- `0x1400079c0`
- `0x140007a74`
- `0x140007b44`
- `0x140007bf8`
- `0x140007c50`
- `0x14000f020`
- `0x14000f250`
- `0x14000f490`
- `0x14000f630`
- `0x14000f830`
- `0x14000fbb0`
- `0x14000fcb0`
- `0x140010240`
- `0x1400103c0`
- `0x140010b60`
- `0x140010c30`
- `0x140010f64`
- `0x140011c00`
- `0x140011d30`
- `0x140012a00`
- `0x140015b50`
- `0x140017010`

## callees

- `0x140008000`

## pseudocode

```c
__int64 WPP_SF_q(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, __int64 *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           (__int64 *)va,
           8,
           0);
}

```

## disassembly

```asm
0x140001bc8  mov     r11, rsp
0x140001bcb  mov     [r11+20h], r9
0x140001bcf  sub     rsp, 48h
0x140001bd3  mov     rax, cs:pfnWppTraceMessage
0x140001bda  lea     r9, [r11+20h]
0x140001bde  mov     qword ptr [r11-18h], 0
0x140001be6  mov     qword ptr [r11-20h], 8
0x140001bee  mov     [r11-28h], r9
0x140001bf2  movzx   r9d, dx
0x140001bf6  mov     edx, 2Bh ; '+'
0x140001bfb  call    _guard_dispatch_icall
0x140001c00  add     rsp, 48h
0x140001c04  retn
```
