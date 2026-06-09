# _alloca_probe

- ea: `0x18000a670`
- end: `0x18000a6bd`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002fe8`
- `0x180004ed4`
- `0x180006510`

## callees

- `0x18000a670`

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
0x18000a670  sub     rsp, 10h
0x18000a674  mov     [rsp+10h+var_10], r10
0x18000a678  mov     [rsp+10h+var_8], r11
0x18000a67d  xor     r11, r11
0x18000a680  lea     r10, [rsp+10h+arg_0]
0x18000a685  sub     r10, rax
0x18000a688  cmovb   r10, r11
0x18000a68c  mov     r11, gs:10h
0x18000a695  cmp     r10, r11
0x18000a698  jnb     short loc_18000A6AF
0x18000a69a  and     r10w, 0F000h
0x18000a6a0  lea     r11, [r11-1000h]
0x18000a6a7  test    [r11], r11b
0x18000a6aa  cmp     r10, r11
0x18000a6ad  jb      short loc_18000A6A0
0x18000a6af  mov     r10, [rsp+10h+var_10]
0x18000a6b3  mov     r11, [rsp+10h+var_8]
0x18000a6b8  add     rsp, 10h
0x18000a6bc  retn
```
