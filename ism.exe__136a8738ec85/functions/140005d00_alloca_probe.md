# _alloca_probe

- ea: `0x140005d00`
- end: `0x140005d4e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140002164`
- `0x140002280`
- `0x140002568`
- `0x140002804`
- `0x1400058c0`

## callees

- `0x140005d00`

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
0x140005d00  sub     rsp, 10h
0x140005d04  mov     [rsp+10h+var_10], r10
0x140005d08  mov     [rsp+10h+var_8], r11
0x140005d0d  xor     r11, r11
0x140005d10  lea     r10, [rsp+10h+arg_0]
0x140005d15  sub     r10, rax
0x140005d18  cmovb   r10, r11
0x140005d1c  mov     r11, gs:10h
0x140005d25  cmp     r10, r11
0x140005d28  jnb     short loc_140005D40
0x140005d2a  and     r10w, 0F000h
0x140005d30  lea     r11, [r11-1000h]
0x140005d37  mov     byte ptr [r11], 0
0x140005d3b  cmp     r10, r11
0x140005d3e  jnz     short loc_140005D30
0x140005d40  mov     r10, [rsp+10h+var_10]
0x140005d44  mov     r11, [rsp+10h+var_8]
0x140005d49  add     rsp, 10h
0x140005d4d  retn
```
