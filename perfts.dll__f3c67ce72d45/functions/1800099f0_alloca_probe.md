# _alloca_probe

- ea: `0x1800099f0`
- end: `0x180009a3d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003c74`
- `0x180003e3c`
- `0x1800040c4`
- `0x1800096e0`

## callees

- `0x1800099f0`

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
0x1800099f0  sub     rsp, 10h
0x1800099f4  mov     [rsp+10h+var_10], r10
0x1800099f8  mov     [rsp+10h+var_8], r11
0x1800099fd  xor     r11, r11
0x180009a00  lea     r10, [rsp+10h+arg_0]
0x180009a05  sub     r10, rax
0x180009a08  cmovb   r10, r11
0x180009a0c  mov     r11, gs:10h
0x180009a15  cmp     r10, r11
0x180009a18  jnb     short loc_180009A2F
0x180009a1a  and     r10w, 0F000h
0x180009a20  lea     r11, [r11-1000h]
0x180009a27  test    [r11], r11b
0x180009a2a  cmp     r10, r11
0x180009a2d  jb      short loc_180009A20
0x180009a2f  mov     r10, [rsp+10h+var_10]
0x180009a33  mov     r11, [rsp+10h+var_8]
0x180009a38  add     rsp, 10h
0x180009a3c  retn
```
