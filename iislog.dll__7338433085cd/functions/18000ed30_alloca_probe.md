# _alloca_probe

- ea: `0x18000ed30`
- end: `0x18000ed7d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180003d48`
- `0x180005020`
- `0x180006870`
- `0x180007ff0`
- `0x180008720`
- `0x18000bf7c`
- `0x18000cb70`

## callees

- `0x18000ed30`

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
0x18000ed30  sub     rsp, 10h
0x18000ed34  mov     [rsp+10h+var_10], r10
0x18000ed38  mov     [rsp+10h+var_8], r11
0x18000ed3d  xor     r11, r11
0x18000ed40  lea     r10, [rsp+10h+arg_0]
0x18000ed45  sub     r10, rax
0x18000ed48  cmovb   r10, r11
0x18000ed4c  mov     r11, gs:10h
0x18000ed55  cmp     r10, r11
0x18000ed58  jnb     short loc_18000ED6F
0x18000ed5a  and     r10w, 0F000h
0x18000ed60  lea     r11, [r11-1000h]
0x18000ed67  test    [r11], r11b
0x18000ed6a  cmp     r10, r11
0x18000ed6d  jb      short loc_18000ED60
0x18000ed6f  mov     r10, [rsp+10h+var_10]
0x18000ed73  mov     r11, [rsp+10h+var_8]
0x18000ed78  add     rsp, 10h
0x18000ed7c  retn
```
