# _alloca_probe

- ea: `0x18000c450`
- end: `0x18000c49d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800087e4`
- `0x180008a54`
- `0x180008cf0`

## callees

- `0x18000c450`

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
0x18000c450  sub     rsp, 10h
0x18000c454  mov     [rsp+10h+var_10], r10
0x18000c458  mov     [rsp+10h+var_8], r11
0x18000c45d  xor     r11, r11
0x18000c460  lea     r10, [rsp+10h+arg_0]
0x18000c465  sub     r10, rax
0x18000c468  cmovb   r10, r11
0x18000c46c  mov     r11, gs:10h
0x18000c475  cmp     r10, r11
0x18000c478  jnb     short loc_18000C48F
0x18000c47a  and     r10w, 0F000h
0x18000c480  lea     r11, [r11-1000h]
0x18000c487  test    [r11], r11b
0x18000c48a  cmp     r10, r11
0x18000c48d  jb      short loc_18000C480
0x18000c48f  mov     r10, [rsp+10h+var_10]
0x18000c493  mov     r11, [rsp+10h+var_8]
0x18000c498  add     rsp, 10h
0x18000c49c  retn
```
