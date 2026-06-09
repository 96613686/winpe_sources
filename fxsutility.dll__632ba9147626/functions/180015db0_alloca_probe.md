# _alloca_probe

- ea: `0x180015db0`
- end: `0x180015dfd`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180002274`
- `0x180003794`
- `0x180004808`
- `0x180007790`
- `0x1800079f8`
- `0x180007c94`
- `0x18000b500`
- `0x18000d100`
- `0x18000d210`

## callees

- `0x180015db0`

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
0x180015db0  sub     rsp, 10h
0x180015db4  mov     [rsp+10h+var_10], r10
0x180015db8  mov     [rsp+10h+var_8], r11
0x180015dbd  xor     r11, r11
0x180015dc0  lea     r10, [rsp+10h+arg_0]
0x180015dc5  sub     r10, rax
0x180015dc8  cmovb   r10, r11
0x180015dcc  mov     r11, gs:10h
0x180015dd5  cmp     r10, r11
0x180015dd8  jnb     short loc_180015DEF
0x180015dda  and     r10w, 0F000h
0x180015de0  lea     r11, [r11-1000h]
0x180015de7  test    [r11], r11b
0x180015dea  cmp     r10, r11
0x180015ded  jb      short loc_180015DE0
0x180015def  mov     r10, [rsp+10h+var_10]
0x180015df3  mov     r11, [rsp+10h+var_8]
0x180015df8  add     rsp, 10h
0x180015dfc  retn
```
