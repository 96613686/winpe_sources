# _alloca_probe

- ea: `0x1400196d0`
- end: `0x14001971d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140003608`
- `0x140003884`
- `0x140003b48`
- `0x140003df0`
- `0x140005bd4`
- `0x14000c800`
- `0x1400178ac`
- `0x140018b0c`

## callees

- `0x1400196d0`

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
0x1400196d0  sub     rsp, 10h
0x1400196d4  mov     [rsp+10h+var_10], r10
0x1400196d8  mov     [rsp+10h+var_8], r11
0x1400196dd  xor     r11, r11
0x1400196e0  lea     r10, [rsp+10h+arg_0]
0x1400196e5  sub     r10, rax
0x1400196e8  cmovb   r10, r11
0x1400196ec  mov     r11, gs:10h
0x1400196f5  cmp     r10, r11
0x1400196f8  jnb     short loc_14001970F
0x1400196fa  and     r10w, 0F000h
0x140019700  lea     r11, [r11-1000h]
0x140019707  test    [r11], r11b
0x14001970a  cmp     r10, r11
0x14001970d  jb      short loc_140019700
0x14001970f  mov     r10, [rsp+10h+var_10]
0x140019713  mov     r11, [rsp+10h+var_8]
0x140019718  add     rsp, 10h
0x14001971c  retn
```
