# _alloca_probe

- ea: `0x1800182a0`
- end: `0x1800182ed`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180002900`
- `0x18000e0bc`
- `0x180010f18`
- `0x180011384`
- `0x180011eb0`
- `0x180013b2c`
- `0x180014128`
- `0x18001792c`

## callees

- `0x1800182a0`

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
0x1800182a0  sub     rsp, 10h
0x1800182a4  mov     [rsp+10h+var_10], r10
0x1800182a8  mov     [rsp+10h+var_8], r11
0x1800182ad  xor     r11, r11
0x1800182b0  lea     r10, [rsp+10h+arg_0]
0x1800182b5  sub     r10, rax
0x1800182b8  cmovb   r10, r11
0x1800182bc  mov     r11, gs:10h
0x1800182c5  cmp     r10, r11
0x1800182c8  jnb     short loc_1800182DF
0x1800182ca  and     r10w, 0F000h
0x1800182d0  lea     r11, [r11-1000h]
0x1800182d7  test    [r11], r11b
0x1800182da  cmp     r10, r11
0x1800182dd  jb      short loc_1800182D0
0x1800182df  mov     r10, [rsp+10h+var_10]
0x1800182e3  mov     r11, [rsp+10h+var_8]
0x1800182e8  add     rsp, 10h
0x1800182ec  retn
```
