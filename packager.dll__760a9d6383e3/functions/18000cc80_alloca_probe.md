# _alloca_probe

- ea: `0x18000cc80`
- end: `0x18000cccd`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001d50`
- `0x180001fc0`
- `0x18000225c`

## callees

- `0x18000cc80`

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
0x18000cc80  sub     rsp, 10h
0x18000cc84  mov     [rsp+10h+var_10], r10
0x18000cc88  mov     [rsp+10h+var_8], r11
0x18000cc8d  xor     r11, r11
0x18000cc90  lea     r10, [rsp+10h+arg_0]
0x18000cc95  sub     r10, rax
0x18000cc98  cmovb   r10, r11
0x18000cc9c  mov     r11, gs:10h
0x18000cca5  cmp     r10, r11
0x18000cca8  jnb     short loc_18000CCBF
0x18000ccaa  and     r10w, 0F000h
0x18000ccb0  lea     r11, [r11-1000h]
0x18000ccb7  test    [r11], r11b
0x18000ccba  cmp     r10, r11
0x18000ccbd  jb      short loc_18000CCB0
0x18000ccbf  mov     r10, [rsp+10h+var_10]
0x18000ccc3  mov     r11, [rsp+10h+var_8]
0x18000ccc8  add     rsp, 10h
0x18000cccc  retn
```
