# _alloca_probe

- ea: `0x18000b390`
- end: `0x18000b3de`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180002c88`
- `0x180002ef8`
- `0x180003194`
- `0x18000a9c4`
- `0x18000b1fc`

## callees

- `0x18000b390`

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
0x18000b390  sub     rsp, 10h
0x18000b394  mov     [rsp+10h+var_10], r10
0x18000b398  mov     [rsp+10h+var_8], r11
0x18000b39d  xor     r11, r11
0x18000b3a0  lea     r10, [rsp+10h+arg_0]
0x18000b3a5  sub     r10, rax
0x18000b3a8  cmovb   r10, r11
0x18000b3ac  mov     r11, gs:10h
0x18000b3b5  cmp     r10, r11
0x18000b3b8  jnb     short loc_18000B3D0
0x18000b3ba  and     r10w, 0F000h
0x18000b3c0  lea     r11, [r11-1000h]
0x18000b3c7  mov     byte ptr [r11], 0
0x18000b3cb  cmp     r10, r11
0x18000b3ce  jnz     short loc_18000B3C0
0x18000b3d0  mov     r10, [rsp+10h+var_10]
0x18000b3d4  mov     r11, [rsp+10h+var_8]
0x18000b3d9  add     rsp, 10h
0x18000b3dd  retn
```
