# CsrLocateServerThread

- ea: `0x180001a60`
- end: `0x180001a8d`
- name: `CsrLocateServerThread`
- size: `45`
- prototype: `_QWORD *__fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800019b0`

## callees

- `0x180001a60`

## pseudocode

```c
_QWORD *__fastcall CsrLocateServerThread(__int64 a1)
{
  _QWORD *i; // rax

  for ( i = *(_QWORD **)(CsrRootProcess + 32); i != (_QWORD *)(CsrRootProcess + 32); i = (_QWORD *)*i )
  {
    if ( i[5] == *(_QWORD *)(a1 + 8) )
      return i - 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180001a60  mov     r9, cs:CsrRootProcess
0x180001a67  add     r9, 20h ; ' '
0x180001a6b  mov     rax, [r9]
0x180001a6e  xchg    ax, ax
0x180001a70  cmp     rax, r9
0x180001a73  jz      short loc_180001A8A
0x180001a75  mov     rdx, [rcx+8]
0x180001a79  cmp     [rax+28h], rdx
0x180001a7d  jz      short loc_180001A84
0x180001a7f  mov     rax, [rax]
0x180001a82  jmp     short loc_180001A70
0x180001a84  add     rax, 0FFFFFFFFFFFFFFF8h
0x180001a88  retn
0x180001a8a  xor     eax, eax
0x180001a8c  retn
```
