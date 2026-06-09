# _alloca_probe

- ea: `0x18000a230`
- end: `0x18000a27d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000892c`
- `0x180008d80`
- `0x180009ca0`

## callees

- `0x18000a230`

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
0x18000a230  sub     rsp, 10h
0x18000a234  mov     [rsp+10h+var_10], r10
0x18000a238  mov     [rsp+10h+var_8], r11
0x18000a23d  xor     r11, r11
0x18000a240  lea     r10, [rsp+10h+arg_0]
0x18000a245  sub     r10, rax
0x18000a248  cmovb   r10, r11
0x18000a24c  mov     r11, gs:10h
0x18000a255  cmp     r10, r11
0x18000a258  jnb     short loc_18000A26F
0x18000a25a  and     r10w, 0F000h
0x18000a260  lea     r11, [r11-1000h]
0x18000a267  test    [r11], r11b
0x18000a26a  cmp     r10, r11
0x18000a26d  jb      short loc_18000A260
0x18000a26f  mov     r10, [rsp+10h+var_10]
0x18000a273  mov     r11, [rsp+10h+var_8]
0x18000a278  add     rsp, 10h
0x18000a27c  retn
```
