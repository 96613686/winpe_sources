# _alloca_probe

- ea: `0x140005b00`
- end: `0x140005b4e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000215c`
- `0x1400023cc`
- `0x140002668`

## callees

- `0x140005b00`

## pseudocode

```c
unsigned __int64 __fastcall alloca_probe()
{
  unsigned __int64 result; // rax
  char *v1; // r10
  char *StackLimit; // r11
  char v3; // [rsp+18h] [rbp+8h] BYREF

  v1 = &v3 - result;
  if ( (unsigned __int64)&v3 < result )
    v1 = 0;
  StackLimit = (char *)NtCurrentTeb()->NtTib.StackLimit;
  if ( v1 < StackLimit )
  {
    LOWORD(v1) = (unsigned __int16)v1 & 0xF000;
    do
    {
      StackLimit -= 4096;
      *StackLimit = 0;
    }
    while ( v1 != StackLimit );
  }
  return result;
}

```

## disassembly

```asm
0x140005b00  sub     rsp, 10h
0x140005b04  mov     [rsp+10h+var_10], r10
0x140005b08  mov     [rsp+10h+var_8], r11
0x140005b0d  xor     r11, r11
0x140005b10  lea     r10, [rsp+10h+arg_0]
0x140005b15  sub     r10, rax
0x140005b18  cmovb   r10, r11
0x140005b1c  mov     r11, gs:10h
0x140005b25  cmp     r10, r11
0x140005b28  jnb     short loc_140005B40
0x140005b2a  and     r10w, 0F000h
0x140005b30  lea     r11, [r11-1000h]
0x140005b37  mov     byte ptr [r11], 0
0x140005b3b  cmp     r10, r11
0x140005b3e  jnz     short loc_140005B30
0x140005b40  mov     r10, [rsp+10h+var_10]
0x140005b44  mov     r11, [rsp+10h+var_8]
0x140005b49  add     rsp, 10h
0x140005b4d  retn
```
