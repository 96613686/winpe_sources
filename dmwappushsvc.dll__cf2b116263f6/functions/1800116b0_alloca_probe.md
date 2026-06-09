# _alloca_probe

- ea: `0x1800116b0`
- end: `0x1800116fe`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180005ea0`
- `0x180006bf4`
- `0x180006ca4`
- `0x180006d94`
- `0x18000aaec`
- `0x18000d20c`

## callees

- `0x1800116b0`

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
0x1800116b0  sub     rsp, 10h
0x1800116b4  mov     [rsp+10h+var_10], r10
0x1800116b8  mov     [rsp+10h+var_8], r11
0x1800116bd  xor     r11, r11
0x1800116c0  lea     r10, [rsp+10h+arg_0]
0x1800116c5  sub     r10, rax
0x1800116c8  cmovb   r10, r11
0x1800116cc  mov     r11, gs:10h
0x1800116d5  cmp     r10, r11
0x1800116d8  jnb     short cs20
0x1800116da  and     r10w, 0F000h
0x1800116e0  lea     r11, [r11-1000h]
0x1800116e7  mov     byte ptr [r11], 0
0x1800116eb  cmp     r10, r11
0x1800116ee  jnz     short cs10
0x1800116f0  mov     r10, [rsp+10h+var_10]
0x1800116f4  mov     r11, [rsp+10h+var_8]
0x1800116f9  add     rsp, 10h
0x1800116fd  retn
```
