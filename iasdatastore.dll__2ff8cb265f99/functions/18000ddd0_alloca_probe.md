# _alloca_probe

- ea: `0x18000ddd0`
- end: `0x18000de1d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800028fc`
- `0x180004b88`
- `0x180004efc`
- `0x180005928`

## callees

- `0x18000ddd0`

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
0x18000ddd0  sub     rsp, 10h
0x18000ddd4  mov     [rsp+10h+var_10], r10
0x18000ddd8  mov     [rsp+10h+var_8], r11
0x18000dddd  xor     r11, r11
0x18000dde0  lea     r10, [rsp+10h+arg_0]
0x18000dde5  sub     r10, rax
0x18000dde8  cmovb   r10, r11
0x18000ddec  mov     r11, gs:10h
0x18000ddf5  cmp     r10, r11
0x18000ddf8  jnb     short loc_18000DE0F
0x18000ddfa  and     r10w, 0F000h
0x18000de00  lea     r11, [r11-1000h]
0x18000de07  test    [r11], r11b
0x18000de0a  cmp     r10, r11
0x18000de0d  jb      short loc_18000DE00
0x18000de0f  mov     r10, [rsp+10h+var_10]
0x18000de13  mov     r11, [rsp+10h+var_8]
0x18000de18  add     rsp, 10h
0x18000de1c  retn
```
