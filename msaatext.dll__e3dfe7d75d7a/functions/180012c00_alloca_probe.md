# _alloca_probe

- ea: `0x180012c00`
- end: `0x180012c4d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180007810`
- `0x18000ab80`
- `0x18000e3f4`
- `0x180010dd4`
- `0x1800124b0`

## callees

- `0x180012c00`

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
0x180012c00  sub     rsp, 10h
0x180012c04  mov     [rsp+10h+var_10], r10
0x180012c08  mov     [rsp+10h+var_8], r11
0x180012c0d  xor     r11, r11
0x180012c10  lea     r10, [rsp+10h+arg_0]
0x180012c15  sub     r10, rax
0x180012c18  cmovb   r10, r11
0x180012c1c  mov     r11, gs:10h
0x180012c25  cmp     r10, r11
0x180012c28  jnb     short loc_180012C3F
0x180012c2a  and     r10w, 0F000h
0x180012c30  lea     r11, [r11-1000h]
0x180012c37  test    [r11], r11b
0x180012c3a  cmp     r10, r11
0x180012c3d  jb      short loc_180012C30
0x180012c3f  mov     r10, [rsp+10h+var_10]
0x180012c43  mov     r11, [rsp+10h+var_8]
0x180012c48  add     rsp, 10h
0x180012c4c  retn
```
