# _alloca_probe

- ea: `0x18000c5b0`
- end: `0x18000c5fd`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000919c`
- `0x18000ab0c`
- `0x18000ae30`
- `0x18000b524`

## callees

- `0x18000c5b0`

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
0x18000c5b0  sub     rsp, 10h
0x18000c5b4  mov     [rsp+10h+var_10], r10
0x18000c5b8  mov     [rsp+10h+var_8], r11
0x18000c5bd  xor     r11, r11
0x18000c5c0  lea     r10, [rsp+10h+arg_0]
0x18000c5c5  sub     r10, rax
0x18000c5c8  cmovb   r10, r11
0x18000c5cc  mov     r11, gs:10h
0x18000c5d5  cmp     r10, r11
0x18000c5d8  jnb     short loc_18000C5EF
0x18000c5da  and     r10w, 0F000h
0x18000c5e0  lea     r11, [r11-1000h]
0x18000c5e7  test    [r11], r11b
0x18000c5ea  cmp     r10, r11
0x18000c5ed  jb      short loc_18000C5E0
0x18000c5ef  mov     r10, [rsp+10h+var_10]
0x18000c5f3  mov     r11, [rsp+10h+var_8]
0x18000c5f8  add     rsp, 10h
0x18000c5fc  retn
```
