# _alloca_probe

- ea: `0x18000fed0`
- end: `0x18000ff1d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002b3c`
- `0x180004118`
- `0x18000448c`
- `0x180004c3c`

## callees

- `0x18000fed0`

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
0x18000fed0  sub     rsp, 10h
0x18000fed4  mov     [rsp+10h+var_10], r10
0x18000fed8  mov     [rsp+10h+var_8], r11
0x18000fedd  xor     r11, r11
0x18000fee0  lea     r10, [rsp+10h+arg_0]
0x18000fee5  sub     r10, rax
0x18000fee8  cmovb   r10, r11
0x18000feec  mov     r11, gs:10h
0x18000fef5  cmp     r10, r11
0x18000fef8  jnb     short loc_18000FF0F
0x18000fefa  and     r10w, 0F000h
0x18000ff00  lea     r11, [r11-1000h]
0x18000ff07  test    [r11], r11b
0x18000ff0a  cmp     r10, r11
0x18000ff0d  jb      short loc_18000FF00
0x18000ff0f  mov     r10, [rsp+10h+var_10]
0x18000ff13  mov     r11, [rsp+10h+var_8]
0x18000ff18  add     rsp, 10h
0x18000ff1c  retn
```
