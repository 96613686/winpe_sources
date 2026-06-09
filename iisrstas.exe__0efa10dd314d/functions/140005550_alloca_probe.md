# _alloca_probe

- ea: `0x140005550`
- end: `0x14000559d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400042d8`

## callees

- `0x140005550`

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
0x140005550  sub     rsp, 10h
0x140005554  mov     [rsp+10h+var_10], r10
0x140005558  mov     [rsp+10h+var_8], r11
0x14000555d  xor     r11, r11
0x140005560  lea     r10, [rsp+10h+arg_0]
0x140005565  sub     r10, rax
0x140005568  cmovb   r10, r11
0x14000556c  mov     r11, gs:10h
0x140005575  cmp     r10, r11
0x140005578  jnb     short loc_14000558F
0x14000557a  and     r10w, 0F000h
0x140005580  lea     r11, [r11-1000h]
0x140005587  test    [r11], r11b
0x14000558a  cmp     r10, r11
0x14000558d  jb      short loc_140005580
0x14000558f  mov     r10, [rsp+10h+var_10]
0x140005593  mov     r11, [rsp+10h+var_8]
0x140005598  add     rsp, 10h
0x14000559c  retn
```
