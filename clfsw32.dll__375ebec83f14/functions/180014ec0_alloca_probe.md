# _alloca_probe

- ea: `0x180014ec0`
- end: `0x180014f0d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180002b54`
- `0x180002dcc`
- `0x18000307c`
- `0x18000658c`
- `0x1800080bc`

## callees

- `0x180014ec0`

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
0x180014ec0  sub     rsp, 10h
0x180014ec4  mov     [rsp+10h+var_10], r10
0x180014ec8  mov     [rsp+10h+var_8], r11
0x180014ecd  xor     r11, r11
0x180014ed0  lea     r10, [rsp+10h+arg_0]
0x180014ed5  sub     r10, rax
0x180014ed8  cmovb   r10, r11
0x180014edc  mov     r11, gs:10h
0x180014ee5  cmp     r10, r11
0x180014ee8  jnb     short loc_180014EFF
0x180014eea  and     r10w, 0F000h
0x180014ef0  lea     r11, [r11-1000h]
0x180014ef7  test    [r11], r11b
0x180014efa  cmp     r10, r11
0x180014efd  jb      short loc_180014EF0
0x180014eff  mov     r10, [rsp+10h+var_10]
0x180014f03  mov     r11, [rsp+10h+var_8]
0x180014f08  add     rsp, 10h
0x180014f0c  retn
```
