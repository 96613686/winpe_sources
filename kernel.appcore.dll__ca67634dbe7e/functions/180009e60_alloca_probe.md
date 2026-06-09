# _alloca_probe

- ea: `0x180009e60`
- end: `0x180009ead`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000595c`
- `0x1800092b0`
- `0x180009360`

## callees

- `0x180009e60`

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
0x180009e60  sub     rsp, 10h
0x180009e64  mov     [rsp+10h+var_10], r10
0x180009e68  mov     [rsp+10h+var_8], r11
0x180009e6d  xor     r11, r11
0x180009e70  lea     r10, [rsp+10h+arg_0]
0x180009e75  sub     r10, rax
0x180009e78  cmovb   r10, r11
0x180009e7c  mov     r11, gs:10h
0x180009e85  cmp     r10, r11
0x180009e88  jnb     short loc_180009E9F
0x180009e8a  and     r10w, 0F000h
0x180009e90  lea     r11, [r11-1000h]
0x180009e97  test    [r11], r11b
0x180009e9a  cmp     r10, r11
0x180009e9d  jb      short loc_180009E90
0x180009e9f  mov     r10, [rsp+10h+var_10]
0x180009ea3  mov     r11, [rsp+10h+var_8]
0x180009ea8  add     rsp, 10h
0x180009eac  retn
```
