# _alloca_probe

- ea: `0x18000c6c0`
- end: `0x18000c70d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002598`
- `0x180002818`
- `0x180002ac4`
- `0x180005e40`
- `0x18000630c`
- `0x1800064ac`

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
      StackLimit -= 4096;
    while ( v1 < StackLimit );
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
0x18000c6e8  jnb     short loc_18000C6FF
0x18000c6ea  and     r10w, 0F000h
0x18000c6f0  lea     r11, [r11-1000h]
0x18000c6f7  test    [r11], r11b
0x18000c6fa  cmp     r10, r11
0x18000c6fd  jb      short loc_18000C6F0
0x18000c6ff  mov     r10, [rsp+10h+var_10]
0x18000c703  mov     r11, [rsp+10h+var_8]
0x18000c708  add     rsp, 10h
0x18000c70c  retn
```
