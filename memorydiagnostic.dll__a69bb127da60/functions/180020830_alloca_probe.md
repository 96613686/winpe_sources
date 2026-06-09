# _alloca_probe

- ea: `0x180020830`
- end: `0x18002087e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180004db0`
- `0x180004ef4`
- `0x180005454`
- `0x180005570`
- `0x1800057f0`
- `0x180005aa4`
- `0x180005d50`
- `0x18000faac`
- `0x180018fa0`
- `0x1800190c8`

## callees

- `0x180020830`

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
0x180020830  sub     rsp, 10h
0x180020834  mov     [rsp+10h+var_10], r10
0x180020838  mov     [rsp+10h+var_8], r11
0x18002083d  xor     r11, r11
0x180020840  lea     r10, [rsp+10h+arg_0]
0x180020845  sub     r10, rax
0x180020848  cmovb   r10, r11
0x18002084c  mov     r11, gs:10h
0x180020855  cmp     r10, r11
0x180020858  jnb     short cs20
0x18002085a  and     r10w, 0F000h
0x180020860  lea     r11, [r11-1000h]
0x180020867  mov     byte ptr [r11], 0
0x18002086b  cmp     r10, r11
0x18002086e  jnz     short cs10
0x180020870  mov     r10, [rsp+10h+var_10]
0x180020874  mov     r11, [rsp+10h+var_8]
0x180020879  add     rsp, 10h
0x18002087d  retn
```
