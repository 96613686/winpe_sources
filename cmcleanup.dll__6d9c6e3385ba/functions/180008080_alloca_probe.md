# _alloca_probe

- ea: `0x180008080`
- end: `0x1800080ce`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800024e0`
- `0x180002750`
- `0x1800029e4`
- `0x1800079b0`

## callees

- `0x180008080`

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
0x180008080  sub     rsp, 10h
0x180008084  mov     [rsp+10h+var_10], r10
0x180008088  mov     [rsp+10h+var_8], r11
0x18000808d  xor     r11, r11
0x180008090  lea     r10, [rsp+10h+arg_0]
0x180008095  sub     r10, rax
0x180008098  cmovb   r10, r11
0x18000809c  mov     r11, gs:10h
0x1800080a5  cmp     r10, r11
0x1800080a8  jnb     short cs20
0x1800080aa  and     r10w, 0F000h
0x1800080b0  lea     r11, [r11-1000h]
0x1800080b7  mov     byte ptr [r11], 0
0x1800080bb  cmp     r10, r11
0x1800080be  jnz     short cs10
0x1800080c0  mov     r10, [rsp+10h+var_10]
0x1800080c4  mov     r11, [rsp+10h+var_8]
0x1800080c9  add     rsp, 10h
0x1800080cd  retn
```
