# _alloca_probe

- ea: `0x14000df90`
- end: `0x14000dfdd`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400023bc`
- `0x1400027b4`
- `0x140002a34`
- `0x140002ce8`
- `0x140002f94`
- `0x140009230`

## callees

- `0x14000df90`

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
      StackLimit -= 4096;
    while ( v1 < StackLimit );
  }
  return result;
}

```

## disassembly

```asm
0x14000df90  sub     rsp, 10h
0x14000df94  mov     [rsp+10h+var_10], r10
0x14000df98  mov     [rsp+10h+var_8], r11
0x14000df9d  xor     r11, r11
0x14000dfa0  lea     r10, [rsp+10h+arg_0]
0x14000dfa5  sub     r10, rax
0x14000dfa8  cmovb   r10, r11
0x14000dfac  mov     r11, gs:10h
0x14000dfb5  cmp     r10, r11
0x14000dfb8  jnb     short loc_14000DFCF
0x14000dfba  and     r10w, 0F000h
0x14000dfc0  lea     r11, [r11-1000h]
0x14000dfc7  test    [r11], r11b
0x14000dfca  cmp     r10, r11
0x14000dfcd  jb      short loc_14000DFC0
0x14000dfcf  mov     r10, [rsp+10h+var_10]
0x14000dfd3  mov     r11, [rsp+10h+var_8]
0x14000dfd8  add     rsp, 10h
0x14000dfdc  retn
```
