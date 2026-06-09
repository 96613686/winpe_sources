# _alloca_probe

- ea: `0x14000f6e0`
- end: `0x14000f72e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140003054`
- `0x1400032c4`
- `0x140003560`
- `0x14000af38`
- `0x14000c654`
- `0x14000d578`
- `0x14000d8cc`
- `0x14000e07c`

## callees

- `0x14000f6e0`

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
0x14000f6e0  sub     rsp, 10h
0x14000f6e4  mov     [rsp+10h+var_10], r10
0x14000f6e8  mov     [rsp+10h+var_8], r11
0x14000f6ed  xor     r11, r11
0x14000f6f0  lea     r10, [rsp+10h+arg_0]
0x14000f6f5  sub     r10, rax
0x14000f6f8  cmovb   r10, r11
0x14000f6fc  mov     r11, gs:10h
0x14000f705  cmp     r10, r11
0x14000f708  jnb     short loc_14000F720
0x14000f70a  and     r10w, 0F000h
0x14000f710  lea     r11, [r11-1000h]
0x14000f717  mov     byte ptr [r11], 0
0x14000f71b  cmp     r10, r11
0x14000f71e  jnz     short loc_14000F710
0x14000f720  mov     r10, [rsp+10h+var_10]
0x14000f724  mov     r11, [rsp+10h+var_8]
0x14000f729  add     rsp, 10h
0x14000f72d  retn
```
