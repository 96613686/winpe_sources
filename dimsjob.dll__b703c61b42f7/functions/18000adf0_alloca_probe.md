# _alloca_probe

- ea: `0x18000adf0`
- end: `0x18000ae3d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800052c0`
- `0x180005370`
- `0x180005464`
- `0x1800083d8`
- `0x180009f80`
- `0x18000a168`

## callees

- `0x18000adf0`

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
0x18000adf0  sub     rsp, 10h
0x18000adf4  mov     [rsp+10h+var_10], r10
0x18000adf8  mov     [rsp+10h+var_8], r11
0x18000adfd  xor     r11, r11
0x18000ae00  lea     r10, [rsp+10h+arg_0]
0x18000ae05  sub     r10, rax
0x18000ae08  cmovb   r10, r11
0x18000ae0c  mov     r11, gs:10h
0x18000ae15  cmp     r10, r11
0x18000ae18  jnb     short loc_18000AE2F
0x18000ae1a  and     r10w, 0F000h
0x18000ae20  lea     r11, [r11-1000h]
0x18000ae27  test    [r11], r11b
0x18000ae2a  cmp     r10, r11
0x18000ae2d  jb      short loc_18000AE20
0x18000ae2f  mov     r10, [rsp+10h+var_10]
0x18000ae33  mov     r11, [rsp+10h+var_8]
0x18000ae38  add     rsp, 10h
0x18000ae3c  retn
```
