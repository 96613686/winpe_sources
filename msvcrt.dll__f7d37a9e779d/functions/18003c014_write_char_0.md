# write_char_0

- ea: `0x18003c014`
- end: `0x18003c05b`
- name: `write_char_0`
- size: `71`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18003b204`
- `0x18003c064`

## callees

- `0x18003c014`
- `0x18003d404`

## pseudocode

```c
void __fastcall write_char_0(unsigned __int8 a1, __int64 a2, _DWORD *a3)
{
  int v5; // eax

  if ( (*(_BYTE *)(a2 + 24) & 0x40) == 0 || *(_QWORD *)(a2 + 16) )
  {
    if ( --*(_DWORD *)(a2 + 8) < 0 )
    {
      v5 = flsbuf_s((unsigned int)(char)a1);
    }
    else
    {
      *(_BYTE *)(*(_QWORD *)a2)++ = a1;
      v5 = a1;
    }
    if ( v5 == -1 )
      *a3 = -1;
    else
      ++*a3;
  }
  else
  {
    ++*a3;
  }
}

```

## disassembly

```asm
0x18003c014  push    rbx
0x18003c016  sub     rsp, 20h
0x18003c01a  test    byte ptr [rdx+18h], 40h
0x18003c01e  mov     rbx, r8
0x18003c021  jz      short loc_18003C02F
0x18003c023  cmp     qword ptr [rdx+10h], 0
0x18003c028  jnz     short loc_18003C02F
0x18003c02a  inc     dword ptr [r8]
0x18003c02d  jmp     short loc_18003C055
0x18003c02f  sub     dword ptr [rdx+8], 1
0x18003c033  js      short loc_18003C042
0x18003c035  mov     rax, [rdx]
0x18003c038  mov     [rax], cl
0x18003c03a  inc     qword ptr [rdx]
0x18003c03d  movzx   eax, cl
0x18003c040  jmp     short loc_18003C04A
0x18003c042  movsx   ecx, cl
0x18003c045  call    _flsbuf_s
0x18003c04a  cmp     eax, 0FFFFFFFFh
0x18003c04d  jnz     short loc_18003C053
0x18003c04f  mov     [rbx], eax
0x18003c051  jmp     short loc_18003C055
0x18003c053  inc     dword ptr [rbx]
0x18003c055  add     rsp, 20h
0x18003c059  pop     rbx
0x18003c05a  retn
```
