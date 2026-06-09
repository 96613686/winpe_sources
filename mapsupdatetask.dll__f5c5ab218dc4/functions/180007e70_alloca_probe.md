# _alloca_probe

- ea: `0x180007e70`
- end: `0x180007ebe`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002ab4`
- `0x180002d24`
- `0x180002fc0`
- `0x1800076d0`

## callees

- `0x180007e70`

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
0x180007e70  sub     rsp, 10h
0x180007e74  mov     [rsp+10h+var_10], r10
0x180007e78  mov     [rsp+10h+var_8], r11
0x180007e7d  xor     r11, r11
0x180007e80  lea     r10, [rsp+10h+arg_0]
0x180007e85  sub     r10, rax
0x180007e88  cmovb   r10, r11
0x180007e8c  mov     r11, gs:10h
0x180007e95  cmp     r10, r11
0x180007e98  jnb     short cs20
0x180007e9a  and     r10w, 0F000h
0x180007ea0  lea     r11, [r11-1000h]
0x180007ea7  mov     byte ptr [r11], 0
0x180007eab  cmp     r10, r11
0x180007eae  jnz     short cs10
0x180007eb0  mov     r10, [rsp+10h+var_10]
0x180007eb4  mov     r11, [rsp+10h+var_8]
0x180007eb9  add     rsp, 10h
0x180007ebd  retn
```
