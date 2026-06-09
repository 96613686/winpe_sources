# _alloca_probe

- ea: `0x140004d60`
- end: `0x140004dad`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140001d5c`
- `0x140002334`
- `0x1400025a4`
- `0x140002840`

## callees

- `0x140004d60`

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
0x140004d60  sub     rsp, 10h
0x140004d64  mov     [rsp+10h+var_10], r10
0x140004d68  mov     [rsp+10h+var_8], r11
0x140004d6d  xor     r11, r11
0x140004d70  lea     r10, [rsp+10h+arg_0]
0x140004d75  sub     r10, rax
0x140004d78  cmovb   r10, r11
0x140004d7c  mov     r11, gs:10h
0x140004d85  cmp     r10, r11
0x140004d88  jnb     short loc_140004D9F
0x140004d8a  and     r10w, 0F000h
0x140004d90  lea     r11, [r11-1000h]
0x140004d97  test    [r11], r11b
0x140004d9a  cmp     r10, r11
0x140004d9d  jb      short loc_140004D90
0x140004d9f  mov     r10, [rsp+10h+var_10]
0x140004da3  mov     r11, [rsp+10h+var_8]
0x140004da8  add     rsp, 10h
0x140004dac  retn
```
