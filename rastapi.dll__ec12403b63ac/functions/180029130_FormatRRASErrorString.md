# FormatRRASErrorString

- ea: `0x180029130`
- end: `0x18002917d`
- name: `FormatRRASErrorString`
- size: `77`
- prototype: `__int64(_QWORD, _QWORD, ...)`
- caller_count: `38`
- callee_count: `1`
- tags: ``

## callers

- `0x180020c98`
- `0x180020f80`
- `0x180021820`
- `0x180021b94`
- `0x180022314`
- `0x18002251c`
- `0x1800226f0`
- `0x1800231f8`
- `0x180023404`
- `0x180023610`
- `0x180023a14`
- `0x180023e24`
- `0x1800240a8`
- `0x1800244ec`
- `0x180024b38`
- `0x180024e60`
- `0x180025244`
- `0x1800257e4`
- `0x180025e40`
- `0x18002619c`
- `0x180026a2c`
- `0x180026c4c`
- `0x180027140`
- `0x180027270`
- `0x180027414`
- `0x1800275b8`
- `0x180027888`
- `0x180027a10`
- `0x180027ba4`
- `0x180027e38`
- `0x180027f2c`
- `0x180028078`
- `0x1800281f0`
- `0x180028398`
- `0x1800284fc`
- `0x1800287d8`
- `0x180028b5c`
- `0x180028c70`

## callees

- `0x180029130`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18002915b`
- `msvcrt!_vsnwprintf` at `0x18002915b`

## pseudocode

```c
unsigned int FormatRRASErrorString(wchar_t *a1, const wchar_t *a2, ...)
{
  unsigned int result; // eax
  va_list va; // [rsp+50h] [rbp+18h] BYREF

  va_start(va, a2);
  result = _vsnwprintf(a1, 0x3FFu, a2, va);
  if ( result > 0x3FE )
  {
    result = 0;
    a1[1023] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180029130  mov     rax, rsp
0x180029133  mov     [rax+10h], rdx
0x180029137  mov     [rax+18h], r8
0x18002913b  mov     [rax+20h], r9
0x18002913f  push    rbx
0x180029140  sub     rsp, 30h
0x180029144  mov     r8, rdx; Format
0x180029147  mov     qword ptr [rax-18h], 0
0x18002914f  mov     edx, 3FFh; BufferCount
0x180029154  lea     r9, [rax+18h]; Args
0x180029158  mov     rbx, rcx
0x18002915b  call    cs:__imp__vsnwprintf
0x180029161  test    eax, eax
0x180029163  js      short loc_18002916E
0x180029165  cmp     eax, 3FFh
0x18002916a  ja      short loc_18002916E
0x18002916c  jnz     short loc_180029177
0x18002916e  xor     eax, eax
0x180029170  mov     [rbx+7FEh], ax
0x180029177  add     rsp, 30h
0x18002917b  pop     rbx
0x18002917c  retn
```
