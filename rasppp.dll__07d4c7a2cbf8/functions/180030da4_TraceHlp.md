# TraceHlp

- ea: `0x180030da4`
- end: `0x180030de0`
- name: `TraceHlp`
- size: `60`
- prototype: `__int64 __fastcall(LPCSTR lpszFormat)`
- caller_count: `25`
- callee_count: `0`
- tags: ``

## callers

- `0x18002d08c`
- `0x18002d194`
- `0x18002d904`
- `0x18002dc14`
- `0x18002defc`
- `0x18002e34c`
- `0x18002e4ec`
- `0x18002e63c`
- `0x18002e720`
- `0x18002e92c`
- `0x18002ebd8`
- `0x18002f038`
- `0x18002f2bc`
- `0x18002f784`
- `0x18002fc60`
- `0x18003078c`
- `0x1800308a0`
- `0x180030acc`
- `0x180030c0c`
- `0x180030de8`
- `0x180031190`
- `0x18003153c`
- `0x1800319ac`
- `0x180031d0c`
- `0x180032110`

## import_xrefs

- `rtutils!TraceVprintfExA` at `0x180030dd5`
- `rtutils!TraceVprintfExA` at `0x180030dd5`

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
0x180030da4  mov     rax, rsp
0x180030da7  mov     [rax+8], rcx
0x180030dab  mov     [rax+10h], rdx
0x180030daf  mov     [rax+18h], r8
0x180030db3  mov     [rax+20h], r9
0x180030db7  sub     rsp, 38h
0x180030dbb  mov     r8, rcx; lpszFormat
0x180030dbe  mov     qword ptr [rax-18h], 0
0x180030dc6  mov     ecx, cs:HelperTraceId; dwTraceID
0x180030dcc  lea     r9, [rax+10h]; arglist
0x180030dd0  mov     edx, 1000Eh; dwFlags
0x180030dd5  call    cs:__imp_TraceVprintfExA
0x180030ddb  add     rsp, 38h
0x180030ddf  retn
```
