# _alloca_probe

- ea: `0x140029b70`
- end: `0x140029bbe`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140003590`
- `0x140003640`
- `0x1400038dc`
- `0x1400064d0`
- `0x14000fca4`
- `0x14001096c`

## callees

- `0x140029b70`

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
0x140029b70  sub     rsp, 10h
0x140029b74  mov     [rsp+10h+var_10], r10
0x140029b78  mov     [rsp+10h+var_8], r11
0x140029b7d  xor     r11, r11
0x140029b80  lea     r10, [rsp+10h+arg_0]
0x140029b85  sub     r10, rax
0x140029b88  cmovb   r10, r11
0x140029b8c  mov     r11, gs:10h
0x140029b95  cmp     r10, r11
0x140029b98  jnb     short loc_140029BB0
0x140029b9a  and     r10w, 0F000h
0x140029ba0  lea     r11, [r11-1000h]
0x140029ba7  mov     byte ptr [r11], 0
0x140029bab  cmp     r10, r11
0x140029bae  jnz     short loc_140029BA0
0x140029bb0  mov     r10, [rsp+10h+var_10]
0x140029bb4  mov     r11, [rsp+10h+var_8]
0x140029bb9  add     rsp, 10h
0x140029bbd  retn
```
