# _alloca_probe

- ea: `0x180014e20`
- end: `0x180014e6e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180003024`
- `0x18000328c`
- `0x180003528`
- `0x18000778c`
- `0x180009c80`
- `0x180009da8`
- `0x18000a380`

## callees

- `0x180014e20`

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
    {
      StackLimit -= 4096;
      *StackLimit = 0;
    }
    while ( v1 != StackLimit );
  }
  return result;
}

```

## disassembly

```asm
0x180014e20  sub     rsp, 10h
0x180014e24  mov     [rsp+10h+var_10], r10
0x180014e28  mov     [rsp+10h+var_8], r11
0x180014e2d  xor     r11, r11
0x180014e30  lea     r10, [rsp+10h+arg_0]
0x180014e35  sub     r10, rax
0x180014e38  cmovb   r10, r11
0x180014e3c  mov     r11, gs:10h
0x180014e45  cmp     r10, r11
0x180014e48  jnb     short cs20
0x180014e4a  and     r10w, 0F000h
0x180014e50  lea     r11, [r11-1000h]
0x180014e57  mov     byte ptr [r11], 0
0x180014e5b  cmp     r10, r11
0x180014e5e  jnz     short cs10
0x180014e60  mov     r10, [rsp+10h+var_10]
0x180014e64  mov     r11, [rsp+10h+var_8]
0x180014e69  add     rsp, 10h
0x180014e6d  retn
```
