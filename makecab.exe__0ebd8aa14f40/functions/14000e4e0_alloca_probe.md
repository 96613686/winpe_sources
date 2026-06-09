# _alloca_probe

- ea: `0x14000e4e0`
- end: `0x14000e52d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140001de0`
- `0x14000488c`
- `0x140005c80`
- `0x140007504`
- `0x14000895c`
- `0x140008a78`
- `0x140008b90`
- `0x140009454`

## callees

- `0x14000e4e0`

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
0x14000e4e0  sub     rsp, 10h
0x14000e4e4  mov     [rsp+10h+var_10], r10
0x14000e4e8  mov     [rsp+10h+var_8], r11
0x14000e4ed  xor     r11, r11
0x14000e4f0  lea     r10, [rsp+10h+arg_0]
0x14000e4f5  sub     r10, rax
0x14000e4f8  cmovb   r10, r11
0x14000e4fc  mov     r11, gs:10h
0x14000e505  cmp     r10, r11
0x14000e508  jnb     short loc_14000E51F
0x14000e50a  and     r10w, 0F000h
0x14000e510  lea     r11, [r11-1000h]
0x14000e517  test    [r11], r11b
0x14000e51a  cmp     r10, r11
0x14000e51d  jb      short loc_14000E510
0x14000e51f  mov     r10, [rsp+10h+var_10]
0x14000e523  mov     r11, [rsp+10h+var_8]
0x14000e528  add     rsp, 10h
0x14000e52c  retn
```
