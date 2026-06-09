# _alloca_probe

- ea: `0x180006f20`
- end: `0x180006f6d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000337c`

## callees

- `0x180006f20`

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
0x180006f20  sub     rsp, 10h
0x180006f24  mov     [rsp+10h+var_10], r10
0x180006f28  mov     [rsp+10h+var_8], r11
0x180006f2d  xor     r11, r11
0x180006f30  lea     r10, [rsp+10h+arg_0]
0x180006f35  sub     r10, rax
0x180006f38  cmovb   r10, r11
0x180006f3c  mov     r11, gs:10h
0x180006f45  cmp     r10, r11
0x180006f48  jnb     short loc_180006F5F
0x180006f4a  and     r10w, 0F000h
0x180006f50  lea     r11, [r11-1000h]
0x180006f57  test    [r11], r11b
0x180006f5a  cmp     r10, r11
0x180006f5d  jb      short loc_180006F50
0x180006f5f  mov     r10, [rsp+10h+var_10]
0x180006f63  mov     r11, [rsp+10h+var_8]
0x180006f68  add     rsp, 10h
0x180006f6c  retn
```
