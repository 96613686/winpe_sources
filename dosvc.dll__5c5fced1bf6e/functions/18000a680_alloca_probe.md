# _alloca_probe

- ea: `0x18000a680`
- end: `0x18000a6ce`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002670`
- `0x1800061cc`
- `0x180006280`
- `0x180008610`
- `0x180008a6c`
- `0x180008b38`

## callees

- `0x18000a680`

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
0x18000a680  sub     rsp, 10h
0x18000a684  mov     [rsp+10h+var_10], r10
0x18000a688  mov     [rsp+10h+var_8], r11
0x18000a68d  xor     r11, r11
0x18000a690  lea     r10, [rsp+10h+arg_0]
0x18000a695  sub     r10, rax
0x18000a698  cmovb   r10, r11
0x18000a69c  mov     r11, gs:10h
0x18000a6a5  cmp     r10, r11
0x18000a6a8  jnb     short cs20
0x18000a6aa  and     r10w, 0F000h
0x18000a6b0  lea     r11, [r11-1000h]
0x18000a6b7  mov     byte ptr [r11], 0
0x18000a6bb  cmp     r10, r11
0x18000a6be  jnz     short cs10
0x18000a6c0  mov     r10, [rsp+10h+var_10]
0x18000a6c4  mov     r11, [rsp+10h+var_8]
0x18000a6c9  add     rsp, 10h
0x18000a6cd  retn
```
