# _alloca_probe

- ea: `0x140010a80`
- end: `0x140010acd`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000de30`
- `0x14000e0b0`
- `0x14000e360`

## callees

- `0x140010a80`

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
0x140010a80  sub     rsp, 10h
0x140010a84  mov     [rsp+10h+var_10], r10
0x140010a88  mov     [rsp+10h+var_8], r11
0x140010a8d  xor     r11, r11
0x140010a90  lea     r10, [rsp+10h+arg_0]
0x140010a95  sub     r10, rax
0x140010a98  cmovb   r10, r11
0x140010a9c  mov     r11, gs:10h
0x140010aa5  cmp     r10, r11
0x140010aa8  jnb     short loc_140010ABF
0x140010aaa  and     r10w, 0F000h
0x140010ab0  lea     r11, [r11-1000h]
0x140010ab7  test    [r11], r11b
0x140010aba  cmp     r10, r11
0x140010abd  jb      short loc_140010AB0
0x140010abf  mov     r10, [rsp+10h+var_10]
0x140010ac3  mov     r11, [rsp+10h+var_8]
0x140010ac8  add     rsp, 10h
0x140010acc  retn
```
