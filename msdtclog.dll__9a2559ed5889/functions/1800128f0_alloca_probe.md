# _alloca_probe

- ea: `0x1800128f0`
- end: `0x18001293d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180002150`
- `0x180002400`
- `0x1800025e0`
- `0x18000f744`
- `0x1800108bc`

## callees

- `0x1800128f0`

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
0x1800128f0  sub     rsp, 10h
0x1800128f4  mov     [rsp+10h+var_10], r10
0x1800128f8  mov     [rsp+10h+var_8], r11
0x1800128fd  xor     r11, r11
0x180012900  lea     r10, [rsp+10h+arg_0]
0x180012905  sub     r10, rax
0x180012908  cmovb   r10, r11
0x18001290c  mov     r11, gs:10h
0x180012915  cmp     r10, r11
0x180012918  jnb     short loc_18001292F
0x18001291a  and     r10w, 0F000h
0x180012920  lea     r11, [r11-1000h]
0x180012927  test    [r11], r11b
0x18001292a  cmp     r10, r11
0x18001292d  jb      short loc_180012920
0x18001292f  mov     r10, [rsp+10h+var_10]
0x180012933  mov     r11, [rsp+10h+var_8]
0x180012938  add     rsp, 10h
0x18001293c  retn
```
