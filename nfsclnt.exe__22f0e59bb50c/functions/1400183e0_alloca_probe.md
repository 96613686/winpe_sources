# _alloca_probe

- ea: `0x1400183e0`
- end: `0x14001842d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400051c0`
- `0x140012660`
- `0x1400128c8`
- `0x140012b64`
- `0x140016078`
- `0x140017820`

## callees

- `0x1400183e0`

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
0x1400183e0  sub     rsp, 10h
0x1400183e4  mov     [rsp+10h+var_10], r10
0x1400183e8  mov     [rsp+10h+var_8], r11
0x1400183ed  xor     r11, r11
0x1400183f0  lea     r10, [rsp+10h+arg_0]
0x1400183f5  sub     r10, rax
0x1400183f8  cmovb   r10, r11
0x1400183fc  mov     r11, gs:10h
0x140018405  cmp     r10, r11
0x140018408  jnb     short loc_14001841F
0x14001840a  and     r10w, 0F000h
0x140018410  lea     r11, [r11-1000h]
0x140018417  test    [r11], r11b
0x14001841a  cmp     r10, r11
0x14001841d  jb      short loc_140018410
0x14001841f  mov     r10, [rsp+10h+var_10]
0x140018423  mov     r11, [rsp+10h+var_8]
0x140018428  add     rsp, 10h
0x14001842c  retn
```
