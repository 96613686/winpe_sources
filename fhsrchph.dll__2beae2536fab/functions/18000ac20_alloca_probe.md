# _alloca_probe

- ea: `0x18000ac20`
- end: `0x18000ac6d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800037ac`
- `0x1800052f8`
- `0x18000566c`
- `0x180006074`

## callees

- `0x18000ac20`

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
0x18000ac20  sub     rsp, 10h
0x18000ac24  mov     [rsp+10h+var_10], r10
0x18000ac28  mov     [rsp+10h+var_8], r11
0x18000ac2d  xor     r11, r11
0x18000ac30  lea     r10, [rsp+10h+arg_0]
0x18000ac35  sub     r10, rax
0x18000ac38  cmovb   r10, r11
0x18000ac3c  mov     r11, gs:10h
0x18000ac45  cmp     r10, r11
0x18000ac48  jnb     short loc_18000AC5F
0x18000ac4a  and     r10w, 0F000h
0x18000ac50  lea     r11, [r11-1000h]
0x18000ac57  test    [r11], r11b
0x18000ac5a  cmp     r10, r11
0x18000ac5d  jb      short loc_18000AC50
0x18000ac5f  mov     r10, [rsp+10h+var_10]
0x18000ac63  mov     r11, [rsp+10h+var_8]
0x18000ac68  add     rsp, 10h
0x18000ac6c  retn
```
