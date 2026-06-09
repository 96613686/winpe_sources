# _alloca_probe

- ea: `0x1800099e0`
- end: `0x180009a2d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180004048`
- `0x1800040f8`
- `0x180004394`
- `0x180007520`
- `0x180008f68`

## callees

- `0x1800099e0`

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
0x1800099e0  sub     rsp, 10h
0x1800099e4  mov     [rsp+10h+var_10], r10
0x1800099e8  mov     [rsp+10h+var_8], r11
0x1800099ed  xor     r11, r11
0x1800099f0  lea     r10, [rsp+10h+arg_0]
0x1800099f5  sub     r10, rax
0x1800099f8  cmovb   r10, r11
0x1800099fc  mov     r11, gs:10h
0x180009a05  cmp     r10, r11
0x180009a08  jnb     short loc_180009A1F
0x180009a0a  and     r10w, 0F000h
0x180009a10  lea     r11, [r11-1000h]
0x180009a17  test    [r11], r11b
0x180009a1a  cmp     r10, r11
0x180009a1d  jb      short loc_180009A10
0x180009a1f  mov     r10, [rsp+10h+var_10]
0x180009a23  mov     r11, [rsp+10h+var_8]
0x180009a28  add     rsp, 10h
0x180009a2c  retn
```
