# _alloca_probe

- ea: `0x18000d960`
- end: `0x18000d9ad`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800079d0`
- `0x180007c38`
- `0x180007ed4`
- `0x18000b3e8`
- `0x18000cba8`

## callees

- `0x18000d960`

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
0x18000d960  sub     rsp, 10h
0x18000d964  mov     [rsp+10h+var_10], r10
0x18000d968  mov     [rsp+10h+var_8], r11
0x18000d96d  xor     r11, r11
0x18000d970  lea     r10, [rsp+10h+arg_0]
0x18000d975  sub     r10, rax
0x18000d978  cmovb   r10, r11
0x18000d97c  mov     r11, gs:10h
0x18000d985  cmp     r10, r11
0x18000d988  jnb     short loc_18000D99F
0x18000d98a  and     r10w, 0F000h
0x18000d990  lea     r11, [r11-1000h]
0x18000d997  test    [r11], r11b
0x18000d99a  cmp     r10, r11
0x18000d99d  jb      short loc_18000D990
0x18000d99f  mov     r10, [rsp+10h+var_10]
0x18000d9a3  mov     r11, [rsp+10h+var_8]
0x18000d9a8  add     rsp, 10h
0x18000d9ac  retn
```
