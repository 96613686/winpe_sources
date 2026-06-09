# _alloca_probe

- ea: `0x18000dfd0`
- end: `0x18000e01d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800030ec`
- `0x180004b4c`
- `0x180004ef8`
- `0x18000574c`

## callees

- `0x18000dfd0`

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
0x18000dfd0  sub     rsp, 10h
0x18000dfd4  mov     [rsp+10h+var_10], r10
0x18000dfd8  mov     [rsp+10h+var_8], r11
0x18000dfdd  xor     r11, r11
0x18000dfe0  lea     r10, [rsp+10h+arg_0]
0x18000dfe5  sub     r10, rax
0x18000dfe8  cmovb   r10, r11
0x18000dfec  mov     r11, gs:10h
0x18000dff5  cmp     r10, r11
0x18000dff8  jnb     short loc_18000E00F
0x18000dffa  and     r10w, 0F000h
0x18000e000  lea     r11, [r11-1000h]
0x18000e007  test    [r11], r11b
0x18000e00a  cmp     r10, r11
0x18000e00d  jb      short loc_18000E000
0x18000e00f  mov     r10, [rsp+10h+var_10]
0x18000e013  mov     r11, [rsp+10h+var_8]
0x18000e018  add     rsp, 10h
0x18000e01c  retn
```
