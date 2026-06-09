# _alloca_probe

- ea: `0x1800134d0`
- end: `0x18001351d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003288`
- `0x1800034f0`
- `0x180003784`
- `0x180006e20`
- `0x18000fdb0`
- `0x180012588`

## callees

- `0x1800134d0`

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
0x1800134d0  sub     rsp, 10h
0x1800134d4  mov     [rsp+10h+var_10], r10
0x1800134d8  mov     [rsp+10h+var_8], r11
0x1800134dd  xor     r11, r11
0x1800134e0  lea     r10, [rsp+10h+arg_0]
0x1800134e5  sub     r10, rax
0x1800134e8  cmovb   r10, r11
0x1800134ec  mov     r11, gs:10h
0x1800134f5  cmp     r10, r11
0x1800134f8  jnb     short loc_18001350F
0x1800134fa  and     r10w, 0F000h
0x180013500  lea     r11, [r11-1000h]
0x180013507  test    [r11], r11b
0x18001350a  cmp     r10, r11
0x18001350d  jb      short loc_180013500
0x18001350f  mov     r10, [rsp+10h+var_10]
0x180013513  mov     r11, [rsp+10h+var_8]
0x180013518  add     rsp, 10h
0x18001351c  retn
```
