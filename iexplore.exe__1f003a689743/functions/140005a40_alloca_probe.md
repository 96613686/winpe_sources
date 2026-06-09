# _alloca_probe

- ea: `0x140005a40`
- end: `0x140005a8d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140002858`
- `0x140002908`
- `0x140002ba4`

## callees

- `0x140005a40`

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
0x140005a40  sub     rsp, 10h
0x140005a44  mov     [rsp+10h+var_10], r10
0x140005a48  mov     [rsp+10h+var_8], r11
0x140005a4d  xor     r11, r11
0x140005a50  lea     r10, [rsp+10h+arg_0]
0x140005a55  sub     r10, rax
0x140005a58  cmovb   r10, r11
0x140005a5c  mov     r11, gs:10h
0x140005a65  cmp     r10, r11
0x140005a68  jnb     short loc_140005A7F
0x140005a6a  and     r10w, 0F000h
0x140005a70  lea     r11, [r11-1000h]
0x140005a77  test    [r11], r11b
0x140005a7a  cmp     r10, r11
0x140005a7d  jb      short loc_140005A70
0x140005a7f  mov     r10, [rsp+10h+var_10]
0x140005a83  mov     r11, [rsp+10h+var_8]
0x140005a88  add     rsp, 10h
0x140005a8c  retn
```
