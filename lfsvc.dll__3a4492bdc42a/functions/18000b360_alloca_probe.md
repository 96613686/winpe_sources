# _alloca_probe

- ea: `0x18000b360`
- end: `0x18000b3ae`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800051d8`
- `0x1800052f0`
- `0x1800053b4`
- `0x180005670`
- `0x1800086dc`
- `0x18000a1a0`
- `0x18000a3a8`

## callees

- `0x18000b360`

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
0x18000b360  sub     rsp, 10h
0x18000b364  mov     [rsp+10h+var_10], r10
0x18000b368  mov     [rsp+10h+var_8], r11
0x18000b36d  xor     r11, r11
0x18000b370  lea     r10, [rsp+10h+arg_0]
0x18000b375  sub     r10, rax
0x18000b378  cmovb   r10, r11
0x18000b37c  mov     r11, gs:10h
0x18000b385  cmp     r10, r11
0x18000b388  jnb     short cs20
0x18000b38a  and     r10w, 0F000h
0x18000b390  lea     r11, [r11-1000h]
0x18000b397  mov     byte ptr [r11], 0
0x18000b39b  cmp     r10, r11
0x18000b39e  jnz     short cs10
0x18000b3a0  mov     r10, [rsp+10h+var_10]
0x18000b3a4  mov     r11, [rsp+10h+var_8]
0x18000b3a9  add     rsp, 10h
0x18000b3ad  retn
```
