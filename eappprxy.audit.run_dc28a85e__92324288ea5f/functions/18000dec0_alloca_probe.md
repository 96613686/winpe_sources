# _alloca_probe

- ea: `0x18000dec0`
- end: `0x18000df0e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x18000259c`
- `0x180002820`
- `0x180002ad0`
- `0x180005f40`
- `0x180006100`
- `0x1800069e0`
- `0x180006d20`
- `0x1800075c0`
- `0x180007a80`
- `0x180008850`
- `0x180008cf0`
- `0x180009230`
- `0x1800096e0`
- `0x180009e10`
- `0x18000a1b0`
- `0x18000a550`

## callees

- `0x18000dec0`

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
0x18000dec0  sub     rsp, 10h
0x18000dec4  mov     [rsp+10h+var_10], r10
0x18000dec8  mov     [rsp+10h+var_8], r11
0x18000decd  xor     r11, r11
0x18000ded0  lea     r10, [rsp+10h+arg_0]
0x18000ded5  sub     r10, rax
0x18000ded8  cmovb   r10, r11
0x18000dedc  mov     r11, gs:10h
0x18000dee5  cmp     r10, r11
0x18000dee8  jnb     short cs20
0x18000deea  and     r10w, 0F000h
0x18000def0  lea     r11, [r11-1000h]
0x18000def7  mov     byte ptr [r11], 0
0x18000defb  cmp     r10, r11
0x18000defe  jnz     short cs10
0x18000df00  mov     r10, [rsp+10h+var_10]
0x18000df04  mov     r11, [rsp+10h+var_8]
0x18000df09  add     rsp, 10h
0x18000df0d  retn
```
