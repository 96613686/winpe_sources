# sub_30CA0C9

- ea: `0x30ca0c9`
- end: `0x30ca0e6`
- name: `sub_30CA0C9`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall __noreturn sub_30CA0C9(__int64 a1, __int64 a2, __int16 _DX, __int64 a4)
{
  _BYTE *v4; // rax

  LOBYTE(v4) = (unsigned __int8)v4 & 0x24;
  *(_BYTE *)(a4 + 103) &= HIBYTE(_DX);
  __asm { insd }
  *v4 |= (unsigned __int8)v4;
  __halt();
}

```

## disassembly

```asm
0x30ca0c9  and     al, 24h
0x30ca0cc  and     [rcx+67h], dh
0x30ca0d0  push    rdi
0x30ca0d1  push    r11
0x30ca0d7  push    rbx
0x30ca0d8  pop     r8
0x30ca0da  push    rdi
0x30ca0db  push    6E6F6349h
0x30ca0e1  push    rbx
0x30ca0e2  insd
0x30ca0e3  or      [rax], al
0x30ca0e5  hlt
```
