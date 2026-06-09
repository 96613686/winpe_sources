# _alloca_probe

- ea: `0x180009ed0`
- end: `0x180009f1d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005ec0`
- `0x180005f74`
- `0x180006224`

## callees

- `0x180009ed0`

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
0x180009ed0  sub     rsp, 10h
0x180009ed4  mov     [rsp+10h+var_10], r10
0x180009ed8  mov     [rsp+10h+var_8], r11
0x180009edd  xor     r11, r11
0x180009ee0  lea     r10, [rsp+10h+arg_0]
0x180009ee5  sub     r10, rax
0x180009ee8  cmovb   r10, r11
0x180009eec  mov     r11, gs:10h
0x180009ef5  cmp     r10, r11
0x180009ef8  jnb     short loc_180009F0F
0x180009efa  and     r10w, 0F000h
0x180009f00  lea     r11, [r11-1000h]
0x180009f07  test    [r11], r11b
0x180009f0a  cmp     r10, r11
0x180009f0d  jb      short loc_180009F00
0x180009f0f  mov     r10, [rsp+10h+var_10]
0x180009f13  mov     r11, [rsp+10h+var_8]
0x180009f18  add     rsp, 10h
0x180009f1c  retn
```
