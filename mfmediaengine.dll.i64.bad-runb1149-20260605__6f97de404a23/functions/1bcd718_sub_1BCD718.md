# sub_1BCD718

- ea: `0x1bcd718`
- end: `0x1bcd743`
- name: `sub_1BCD718`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall sub_1BCD718(__int64 a1, __int64 _RSI)
{
  __asm { outsb }
  __asm { outsb }
  __asm { retnq }
}

```

## disassembly

```asm
0x1bcd718  push    rbp
0x1bcd719  push    rax
0x1bcd71e  push    r13
0x1bcd721  push    r13
0x1bcd723  outsb
0x1bcd724  imul    ebp, [rsi+6Fh], 77h ; 'w'
0x1bcd728  outsb
0x1bcd729  push    rbp
0x1bcd72f  pop     rdi
0x1bcd730  push    r13
0x1bcd732  push    rax
0x1bcd737  push    r8
0x1bcd73a  pop     r8
0x1bcd73d  pop     rdx
0x1bcd73f  add     eax, [rax]
0x1bcd741  retnq
```
