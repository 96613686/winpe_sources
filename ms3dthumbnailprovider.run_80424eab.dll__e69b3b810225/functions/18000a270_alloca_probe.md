# _alloca_probe

- ea: `0x18000a270`
- end: `0x18000a2be`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800047a4`
- `0x180004a14`
- `0x180004cb0`
- `0x180009ae0`

## callees

- `0x18000a270`

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
0x18000a270  sub     rsp, 10h
0x18000a274  mov     [rsp+10h+var_10], r10
0x18000a278  mov     [rsp+10h+var_8], r11
0x18000a27d  xor     r11, r11
0x18000a280  lea     r10, [rsp+10h+arg_0]
0x18000a285  sub     r10, rax
0x18000a288  cmovb   r10, r11
0x18000a28c  mov     r11, gs:10h
0x18000a295  cmp     r10, r11
0x18000a298  jnb     short cs20
0x18000a29a  and     r10w, 0F000h
0x18000a2a0  lea     r11, [r11-1000h]
0x18000a2a7  mov     byte ptr [r11], 0
0x18000a2ab  cmp     r10, r11
0x18000a2ae  jnz     short cs10
0x18000a2b0  mov     r10, [rsp+10h+var_10]
0x18000a2b4  mov     r11, [rsp+10h+var_8]
0x18000a2b9  add     rsp, 10h
0x18000a2bd  retn
```
