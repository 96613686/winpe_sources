# _alloca_probe

- ea: `0x1400188a0`
- end: `0x1400188ed`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1400035c0`
- `0x140003828`
- `0x140003adc`
- `0x140003d70`
- `0x140005b34`
- `0x14000c360`
- `0x14001556c`
- `0x140016c98`

## callees

- `0x1400188a0`

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
0x1400188a0  sub     rsp, 10h
0x1400188a4  mov     [rsp+10h+var_10], r10
0x1400188a8  mov     [rsp+10h+var_8], r11
0x1400188ad  xor     r11, r11
0x1400188b0  lea     r10, [rsp+10h+arg_0]
0x1400188b5  sub     r10, rax
0x1400188b8  cmovb   r10, r11
0x1400188bc  mov     r11, gs:10h
0x1400188c5  cmp     r10, r11
0x1400188c8  jnb     short loc_1400188DF
0x1400188ca  and     r10w, 0F000h
0x1400188d0  lea     r11, [r11-1000h]
0x1400188d7  test    [r11], r11b
0x1400188da  cmp     r10, r11
0x1400188dd  jb      short loc_1400188D0
0x1400188df  mov     r10, [rsp+10h+var_10]
0x1400188e3  mov     r11, [rsp+10h+var_8]
0x1400188e8  add     rsp, 10h
0x1400188ec  retn
```
