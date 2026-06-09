# _alloca_probe

- ea: `0x180005810`
- end: `0x18000585d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000474c`

## callees

- `0x180005810`

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
0x180005810  sub     rsp, 10h
0x180005814  mov     [rsp+10h+var_10], r10
0x180005818  mov     [rsp+10h+var_8], r11
0x18000581d  xor     r11, r11
0x180005820  lea     r10, [rsp+10h+arg_0]
0x180005825  sub     r10, rax
0x180005828  cmovb   r10, r11
0x18000582c  mov     r11, gs:10h
0x180005835  cmp     r10, r11
0x180005838  jnb     short loc_18000584F
0x18000583a  and     r10w, 0F000h
0x180005840  lea     r11, [r11-1000h]
0x180005847  test    [r11], r11b
0x18000584a  cmp     r10, r11
0x18000584d  jb      short loc_180005840
0x18000584f  mov     r10, [rsp+10h+var_10]
0x180005853  mov     r11, [rsp+10h+var_8]
0x180005858  add     rsp, 10h
0x18000585c  retn
```
