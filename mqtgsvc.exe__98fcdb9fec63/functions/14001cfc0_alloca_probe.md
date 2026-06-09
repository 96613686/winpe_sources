# _alloca_probe

- ea: `0x14001cfc0`
- end: `0x14001d00d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f0a4`
- `0x14000f308`
- `0x140016730`
- `0x1400167e0`
- `0x1400168d4`
- `0x140019eb8`
- `0x14001bec0`
- `0x14001c0b0`
- `0x14001cc9c`

## callees

- `0x14001cfc0`

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
0x14001cfc0  sub     rsp, 10h
0x14001cfc4  mov     [rsp+10h+var_10], r10
0x14001cfc8  mov     [rsp+10h+var_8], r11
0x14001cfcd  xor     r11, r11
0x14001cfd0  lea     r10, [rsp+10h+arg_0]
0x14001cfd5  sub     r10, rax
0x14001cfd8  cmovb   r10, r11
0x14001cfdc  mov     r11, gs:10h
0x14001cfe5  cmp     r10, r11
0x14001cfe8  jnb     short loc_14001CFFF
0x14001cfea  and     r10w, 0F000h
0x14001cff0  lea     r11, [r11-1000h]
0x14001cff7  test    [r11], r11b
0x14001cffa  cmp     r10, r11
0x14001cffd  jb      short loc_14001CFF0
0x14001cfff  mov     r10, [rsp+10h+var_10]
0x14001d003  mov     r11, [rsp+10h+var_8]
0x14001d008  add     rsp, 10h
0x14001d00c  retn
```
