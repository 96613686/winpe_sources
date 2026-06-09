# _alloca_probe

- ea: `0x180011400`
- end: `0x18001144d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800030ac`
- `0x1800048f8`
- `0x180004c68`
- `0x18000541c`

## callees

- `0x180011400`

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
0x180011400  sub     rsp, 10h
0x180011404  mov     [rsp+10h+var_10], r10
0x180011408  mov     [rsp+10h+var_8], r11
0x18001140d  xor     r11, r11
0x180011410  lea     r10, [rsp+10h+arg_0]
0x180011415  sub     r10, rax
0x180011418  cmovb   r10, r11
0x18001141c  mov     r11, gs:10h
0x180011425  cmp     r10, r11
0x180011428  jnb     short loc_18001143F
0x18001142a  and     r10w, 0F000h
0x180011430  lea     r11, [r11-1000h]
0x180011437  test    [r11], r11b
0x18001143a  cmp     r10, r11
0x18001143d  jb      short loc_180011430
0x18001143f  mov     r10, [rsp+10h+var_10]
0x180011443  mov     r11, [rsp+10h+var_8]
0x180011448  add     rsp, 10h
0x18001144c  retn
```
