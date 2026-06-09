# _alloca_probe

- ea: `0x14001e110`
- end: `0x14001e15d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1400111a8`
- `0x140011258`
- `0x1400114ec`
- `0x1400137f0`
- `0x140016e24`
- `0x140018030`
- `0x140018a80`

## callees

- `0x14001e110`

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
0x14001e110  sub     rsp, 10h
0x14001e114  mov     [rsp+10h+var_10], r10
0x14001e118  mov     [rsp+10h+var_8], r11
0x14001e11d  xor     r11, r11
0x14001e120  lea     r10, [rsp+10h+arg_0]
0x14001e125  sub     r10, rax
0x14001e128  cmovb   r10, r11
0x14001e12c  mov     r11, gs:10h
0x14001e135  cmp     r10, r11
0x14001e138  jnb     short loc_14001E14F
0x14001e13a  and     r10w, 0F000h
0x14001e140  lea     r11, [r11-1000h]
0x14001e147  test    [r11], r11b
0x14001e14a  cmp     r10, r11
0x14001e14d  jb      short loc_14001E140
0x14001e14f  mov     r10, [rsp+10h+var_10]
0x14001e153  mov     r11, [rsp+10h+var_8]
0x14001e158  add     rsp, 10h
0x14001e15c  retn
```
