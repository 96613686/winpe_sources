# _alloca_probe

- ea: `0x18000d7e0`
- end: `0x18000d82e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a89c`
- `0x18000a9a4`
- `0x18000ae18`
- `0x18000b088`
- `0x18000b324`

## callees

- `0x18000d7e0`

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
0x18000d7e0  sub     rsp, 10h
0x18000d7e4  mov     [rsp+10h+var_10], r10
0x18000d7e8  mov     [rsp+10h+var_8], r11
0x18000d7ed  xor     r11, r11
0x18000d7f0  lea     r10, [rsp+10h+arg_0]
0x18000d7f5  sub     r10, rax
0x18000d7f8  cmovb   r10, r11
0x18000d7fc  mov     r11, gs:10h
0x18000d805  cmp     r10, r11
0x18000d808  jnb     short cs20
0x18000d80a  and     r10w, 0F000h
0x18000d810  lea     r11, [r11-1000h]
0x18000d817  mov     byte ptr [r11], 0
0x18000d81b  cmp     r10, r11
0x18000d81e  jnz     short cs10
0x18000d820  mov     r10, [rsp+10h+var_10]
0x18000d824  mov     r11, [rsp+10h+var_8]
0x18000d829  add     rsp, 10h
0x18000d82d  retn
```
