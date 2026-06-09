# _alloca_probe

- ea: `0x180011c30`
- end: `0x180011c7d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000222c`
- `0x180004720`
- `0x18000be24`
- `0x18000cf74`

## callees

- `0x180011c30`

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
0x180011c30  sub     rsp, 10h
0x180011c34  mov     [rsp+10h+var_10], r10
0x180011c38  mov     [rsp+10h+var_8], r11
0x180011c3d  xor     r11, r11
0x180011c40  lea     r10, [rsp+10h+arg_0]
0x180011c45  sub     r10, rax
0x180011c48  cmovb   r10, r11
0x180011c4c  mov     r11, gs:10h
0x180011c55  cmp     r10, r11
0x180011c58  jnb     short loc_180011C6F
0x180011c5a  and     r10w, 0F000h
0x180011c60  lea     r11, [r11-1000h]
0x180011c67  test    [r11], r11b
0x180011c6a  cmp     r10, r11
0x180011c6d  jb      short loc_180011C60
0x180011c6f  mov     r10, [rsp+10h+var_10]
0x180011c73  mov     r11, [rsp+10h+var_8]
0x180011c78  add     rsp, 10h
0x180011c7c  retn
```
