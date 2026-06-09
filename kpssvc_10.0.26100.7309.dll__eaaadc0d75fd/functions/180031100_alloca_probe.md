# _alloca_probe

- ea: `0x180031100`
- end: `0x18003114d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b800`
- `0x18001ba78`
- `0x18001bd28`
- `0x180024484`
- `0x1800266fc`

## callees

- `0x180031100`

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
0x180031100  sub     rsp, 10h
0x180031104  mov     [rsp+10h+var_10], r10
0x180031108  mov     [rsp+10h+var_8], r11
0x18003110d  xor     r11, r11
0x180031110  lea     r10, [rsp+10h+arg_0]
0x180031115  sub     r10, rax
0x180031118  cmovb   r10, r11
0x18003111c  mov     r11, gs:10h
0x180031125  cmp     r10, r11
0x180031128  jnb     short loc_18003113F
0x18003112a  and     r10w, 0F000h
0x180031130  lea     r11, [r11-1000h]
0x180031137  test    [r11], r11b
0x18003113a  cmp     r10, r11
0x18003113d  jb      short loc_180031130
0x18003113f  mov     r10, [rsp+10h+var_10]
0x180031143  mov     r11, [rsp+10h+var_8]
0x180031148  add     rsp, 10h
0x18003114c  retn
```
