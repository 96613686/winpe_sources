# TraceHlp

- ea: `0x18003230c`
- end: `0x18003234f`
- name: `TraceHlp`
- size: `67`
- prototype: `__int64 __fastcall(LPCSTR lpszFormat)`
- caller_count: `25`
- callee_count: `0`
- tags: ``

## callers

- `0x18002e2a4`
- `0x18002e3cc`
- `0x18002ebd0`
- `0x18002ef0c`
- `0x18002f22c`
- `0x18002f6b8`
- `0x18002f864`
- `0x18002f9c4`
- `0x18002fab4`
- `0x18002fce0`
- `0x18002ffa4`
- `0x180030434`
- `0x1800306d4`
- `0x180030bec`
- `0x180031120`
- `0x180031cd0`
- `0x180031dec`
- `0x180032024`
- `0x18003216c`
- `0x180032358`
- `0x180032738`
- `0x180032b1c`
- `0x180032fa4`
- `0x180033304`
- `0x180033724`

## import_xrefs

- `rtutils!TraceVprintfExA` at `0x18003233d`
- `rtutils!TraceVprintfExA` at `0x18003233d`

## pseudocode

```c
DWORD TraceHlp(LPCSTR lpszFormat, ...)
{
  va_list va; // [rsp+48h] [rbp+10h] BYREF

  va_start(va, lpszFormat);
  return TraceVprintfExA(HelperTraceId, 0x1000Eu, lpszFormat, va);
}

```

## disassembly

```asm
0x18003230c  mov     rax, rsp
0x18003230f  mov     [rax+8], rcx
0x180032313  mov     [rax+10h], rdx
0x180032317  mov     [rax+18h], r8
0x18003231b  mov     [rax+20h], r9
0x18003231f  sub     rsp, 38h
0x180032323  mov     r8, rcx; lpszFormat
0x180032326  mov     qword ptr [rax-18h], 0
0x18003232e  mov     ecx, cs:HelperTraceId; dwTraceID
0x180032334  lea     r9, [rax+10h]; arglist
0x180032338  mov     edx, 1000Eh; dwFlags
0x18003233d  call    cs:__imp_TraceVprintfExA
0x180032344  nop     dword ptr [rax+rax+00h]
0x180032349  add     rsp, 38h
0x18003234d  retn
```
