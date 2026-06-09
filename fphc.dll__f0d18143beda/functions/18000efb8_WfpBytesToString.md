# WfpBytesToString

- ea: `0x18000efb8`
- end: `0x18000f019`
- name: `WfpBytesToString`
- size: `97`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f0b4`
- `0x18000f2d8`
- `0x180010830`

## callees

- `0x18000efb8`

## pseudocode

```c
__int64 __fastcall WfpBytesToString(unsigned __int64 a1, __int64 a2, __int64 a3)
{
  unsigned __int64 i; // r9
  unsigned __int8 v5; // dl

  for ( i = 0; i < a1; ++i )
  {
    v5 = *(_BYTE *)(a2 + i) & 0xF;
    *(_WORD *)(a3 + 4 * i) = (*(_BYTE *)(a2 + i) >> 4) + ((unsigned __int8)(*(_BYTE *)(a2 + i) >> 4) < 0xAu ? 48 : 87);
    *(_WORD *)(a3 + 4 * i + 2) = v5 + (v5 < 0xAu ? 48 : 87);
    *(_WORD *)(a3 + 4 * i + 4) = 0;
  }
  return a3;
}

```

## disassembly

```asm
0x18000efb8  xor     r9d, r9d
0x18000efbb  mov     r11, rdx
0x18000efbe  mov     r10, rcx
0x18000efc1  test    rcx, rcx
0x18000efc4  jz      short loc_18000F015
0x18000efc6  mov     dl, [r11+r9]
0x18000efca  mov     al, dl
0x18000efcc  shr     al, 4
0x18000efcf  movzx   ecx, al
0x18000efd2  cmp     cl, 0Ah
0x18000efd5  sbb     ax, ax
0x18000efd8  and     dl, 0Fh
0x18000efdb  and     ax, 0FFD9h
0x18000efdf  add     ax, 57h ; 'W'
0x18000efe3  add     ax, cx
0x18000efe6  movzx   ecx, dl
0x18000efe9  mov     [r8+r9*4], ax
0x18000efee  cmp     cl, 0Ah
0x18000eff1  sbb     ax, ax
0x18000eff4  and     ax, 0FFD9h
0x18000eff8  add     ax, 57h ; 'W'
0x18000effc  add     ax, cx
0x18000efff  mov     [r8+r9*4+2], ax
0x18000f005  xor     eax, eax
0x18000f007  mov     [r8+r9*4+4], ax
0x18000f00d  inc     r9
0x18000f010  cmp     r9, r10
0x18000f013  jb      short loc_18000EFC6
0x18000f015  mov     rax, r8
0x18000f018  retn
```
