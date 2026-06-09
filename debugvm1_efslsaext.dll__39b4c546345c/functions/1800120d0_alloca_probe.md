# _alloca_probe

- ea: `0x1800120d0`
- end: `0x18001211d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800032d4`
- `0x18000353c`
- `0x1800037d8`
- `0x1800107dc`
- `0x18001172c`

## callees

- `0x1800120d0`

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
0x1800120d0  sub     rsp, 10h
0x1800120d4  mov     [rsp+10h+var_10], r10
0x1800120d8  mov     [rsp+10h+var_8], r11
0x1800120dd  xor     r11, r11
0x1800120e0  lea     r10, [rsp+10h+arg_0]
0x1800120e5  sub     r10, rax
0x1800120e8  cmovb   r10, r11
0x1800120ec  mov     r11, gs:10h
0x1800120f5  cmp     r10, r11
0x1800120f8  jnb     short loc_18001210F
0x1800120fa  and     r10w, 0F000h
0x180012100  lea     r11, [r11-1000h]
0x180012107  test    [r11], r11b
0x18001210a  cmp     r10, r11
0x18001210d  jb      short loc_180012100
0x18001210f  mov     r10, [rsp+10h+var_10]
0x180012113  mov     r11, [rsp+10h+var_8]
0x180012118  add     rsp, 10h
0x18001211c  retn
```
