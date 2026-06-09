# _alloca_probe

- ea: `0x18000c6c0`
- end: `0x18000c70e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002c90`
- `0x180002ef8`
- `0x180003194`
- `0x180006190`

## callees

- `0x18000c6c0`

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
0x18000c6c0  sub     rsp, 10h
0x18000c6c4  mov     [rsp+10h+var_10], r10
0x18000c6c8  mov     [rsp+10h+var_8], r11
0x18000c6cd  xor     r11, r11
0x18000c6d0  lea     r10, [rsp+10h+arg_0]
0x18000c6d5  sub     r10, rax
0x18000c6d8  cmovb   r10, r11
0x18000c6dc  mov     r11, gs:10h
0x18000c6e5  cmp     r10, r11
0x18000c6e8  jnb     short cs20
0x18000c6ea  and     r10w, 0F000h
0x18000c6f0  lea     r11, [r11-1000h]
0x18000c6f7  mov     byte ptr [r11], 0
0x18000c6fb  cmp     r10, r11
0x18000c6fe  jnz     short cs10
0x18000c700  mov     r10, [rsp+10h+var_10]
0x18000c704  mov     r11, [rsp+10h+var_8]
0x18000c709  add     rsp, 10h
0x18000c70d  retn
```
