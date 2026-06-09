# _alloca_probe

- ea: `0x180009ac0`
- end: `0x180009b0d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000296c`
- `0x180004298`
- `0x18000460c`
- `0x180004f84`

## callees

- `0x180009ac0`

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
0x180009ac0  sub     rsp, 10h
0x180009ac4  mov     [rsp+10h+var_10], r10
0x180009ac8  mov     [rsp+10h+var_8], r11
0x180009acd  xor     r11, r11
0x180009ad0  lea     r10, [rsp+10h+arg_0]
0x180009ad5  sub     r10, rax
0x180009ad8  cmovb   r10, r11
0x180009adc  mov     r11, gs:10h
0x180009ae5  cmp     r10, r11
0x180009ae8  jnb     short loc_180009AFF
0x180009aea  and     r10w, 0F000h
0x180009af0  lea     r11, [r11-1000h]
0x180009af7  test    [r11], r11b
0x180009afa  cmp     r10, r11
0x180009afd  jb      short loc_180009AF0
0x180009aff  mov     r10, [rsp+10h+var_10]
0x180009b03  mov     r11, [rsp+10h+var_8]
0x180009b08  add     rsp, 10h
0x180009b0c  retn
```
