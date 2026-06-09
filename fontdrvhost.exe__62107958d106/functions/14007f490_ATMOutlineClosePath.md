# ATMOutlineClosePath

- ea: `0x14007f490`
- end: `0x14007f4ba`
- name: `ATMOutlineClosePath`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14007f630`

## callees

- `0x140051ed4`
- `0x14007f490`

## pseudocode

```c
void __fastcall ATMOutlineClosePath(__int64 a1)
{
  if ( (*(_BYTE *)(a1 + 40) & 1) != 0 )
  {
    if ( !PATHOBJ_bCloseFigure(*(PATHOBJ **)(a1 + 32)) )
      *(_BYTE *)(a1 + 40) |= 2u;
    *(_BYTE *)(a1 + 40) &= ~1u;
  }
}

```

## disassembly

```asm
0x14007f490  push    rbx
0x14007f492  sub     rsp, 20h
0x14007f496  mov     rbx, rcx
0x14007f499  test    byte ptr [rcx+28h], 1
0x14007f49d  jz      short loc_14007F4B4
0x14007f49f  mov     rcx, [rcx+20h]; ppo
0x14007f4a3  call    PATHOBJ_bCloseFigure
0x14007f4a8  test    eax, eax
0x14007f4aa  jnz     short loc_14007F4B0
0x14007f4ac  or      byte ptr [rbx+28h], 2
0x14007f4b0  and     byte ptr [rbx+28h], 0FEh
0x14007f4b4  add     rsp, 20h
0x14007f4b8  pop     rbx
0x14007f4b9  retn
0x140097687  push    rbp
0x140097689  sub     rsp, 20h
0x14009768d  mov     rbp, rdx
0x140097690  add     rsp, 20h
0x140097694  pop     rbp
0x140097695  retn
```
