# _alloca_probe

- ea: `0x18001ea10`
- end: `0x18001ea5e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180003bd0`
- `0x180003e50`
- `0x1800040fc`
- `0x180007250`
- `0x18000797c`
- `0x180009a00`
- `0x1800186d8`
- `0x18001d064`
- `0x18001e79c`

## callees

- `0x18001ea10`

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
0x18001ea10  sub     rsp, 10h
0x18001ea14  mov     [rsp+10h+var_10], r10
0x18001ea18  mov     [rsp+10h+var_8], r11
0x18001ea1d  xor     r11, r11
0x18001ea20  lea     r10, [rsp+10h+arg_0]
0x18001ea25  sub     r10, rax
0x18001ea28  cmovb   r10, r11
0x18001ea2c  mov     r11, gs:10h
0x18001ea35  cmp     r10, r11
0x18001ea38  jnb     short cs20
0x18001ea3a  and     r10w, 0F000h
0x18001ea40  lea     r11, [r11-1000h]
0x18001ea47  mov     byte ptr [r11], 0
0x18001ea4b  cmp     r10, r11
0x18001ea4e  jnz     short cs10
0x18001ea50  mov     r10, [rsp+10h+var_10]
0x18001ea54  mov     r11, [rsp+10h+var_8]
0x18001ea59  add     rsp, 10h
0x18001ea5d  retn
```
