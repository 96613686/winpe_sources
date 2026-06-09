# _alloca_probe

- ea: `0x14000fe00`
- end: `0x14000fe4e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1400036d8`
- `0x14000381c`
- `0x140003bd8`
- `0x140003e58`
- `0x140004104`
- `0x140009dac`
- `0x14000d240`
- `0x14000d368`

## callees

- `0x14000fe00`

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
0x14000fe00  sub     rsp, 10h
0x14000fe04  mov     [rsp+10h+var_10], r10
0x14000fe08  mov     [rsp+10h+var_8], r11
0x14000fe0d  xor     r11, r11
0x14000fe10  lea     r10, [rsp+10h+arg_0]
0x14000fe15  sub     r10, rax
0x14000fe18  cmovb   r10, r11
0x14000fe1c  mov     r11, gs:10h
0x14000fe25  cmp     r10, r11
0x14000fe28  jnb     short loc_14000FE40
0x14000fe2a  and     r10w, 0F000h
0x14000fe30  lea     r11, [r11-1000h]
0x14000fe37  mov     byte ptr [r11], 0
0x14000fe3b  cmp     r10, r11
0x14000fe3e  jnz     short loc_14000FE30
0x14000fe40  mov     r10, [rsp+10h+var_10]
0x14000fe44  mov     r11, [rsp+10h+var_8]
0x14000fe49  add     rsp, 10h
0x14000fe4d  retn
```
