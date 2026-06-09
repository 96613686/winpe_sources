# _alloca_probe

- ea: `0x18001cb00`
- end: `0x18001cb4d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002710`
- `0x180002978`
- `0x180002c14`
- `0x1800063d0`
- `0x180008110`
- `0x180008220`

## callees

- `0x18001cb00`

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
      StackLimit -= 4096;
    while ( v1 < StackLimit );
  }
  return result;
}

```

## disassembly

```asm
0x18001cb00  sub     rsp, 10h
0x18001cb04  mov     [rsp+10h+var_10], r10
0x18001cb08  mov     [rsp+10h+var_8], r11
0x18001cb0d  xor     r11, r11
0x18001cb10  lea     r10, [rsp+10h+arg_0]
0x18001cb15  sub     r10, rax
0x18001cb18  cmovb   r10, r11
0x18001cb1c  mov     r11, gs:10h
0x18001cb25  cmp     r10, r11
0x18001cb28  jnb     short loc_18001CB3F
0x18001cb2a  and     r10w, 0F000h
0x18001cb30  lea     r11, [r11-1000h]
0x18001cb37  test    [r11], r11b
0x18001cb3a  cmp     r10, r11
0x18001cb3d  jb      short loc_18001CB30
0x18001cb3f  mov     r10, [rsp+10h+var_10]
0x18001cb43  mov     r11, [rsp+10h+var_8]
0x18001cb48  add     rsp, 10h
0x18001cb4c  retn
```
