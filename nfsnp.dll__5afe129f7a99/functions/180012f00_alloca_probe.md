# _alloca_probe

- ea: `0x180012f00`
- end: `0x180012f4d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002320`
- `0x180004a40`
- `0x18000c738`
- `0x18000da44`

## callees

- `0x180012f00`

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
0x180012f00  sub     rsp, 10h
0x180012f04  mov     [rsp+10h+var_10], r10
0x180012f08  mov     [rsp+10h+var_8], r11
0x180012f0d  xor     r11, r11
0x180012f10  lea     r10, [rsp+10h+arg_0]
0x180012f15  sub     r10, rax
0x180012f18  cmovb   r10, r11
0x180012f1c  mov     r11, gs:10h
0x180012f25  cmp     r10, r11
0x180012f28  jnb     short loc_180012F3F
0x180012f2a  and     r10w, 0F000h
0x180012f30  lea     r11, [r11-1000h]
0x180012f37  test    [r11], r11b
0x180012f3a  cmp     r10, r11
0x180012f3d  jb      short loc_180012F30
0x180012f3f  mov     r10, [rsp+10h+var_10]
0x180012f43  mov     r11, [rsp+10h+var_8]
0x180012f48  add     rsp, 10h
0x180012f4c  retn
```
