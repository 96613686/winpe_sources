# _alloca_probe

- ea: `0x180013d80`
- end: `0x180013dce`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800027a4`
- `0x180002a18`
- `0x180002cb4`
- `0x180006890`

## callees

- `0x180013d80`

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
0x180013d80  sub     rsp, 10h
0x180013d84  mov     [rsp+10h+var_10], r10
0x180013d88  mov     [rsp+10h+var_8], r11
0x180013d8d  xor     r11, r11
0x180013d90  lea     r10, [rsp+10h+arg_0]
0x180013d95  sub     r10, rax
0x180013d98  cmovb   r10, r11
0x180013d9c  mov     r11, gs:10h
0x180013da5  cmp     r10, r11
0x180013da8  jnb     short cs20
0x180013daa  and     r10w, 0F000h
0x180013db0  lea     r11, [r11-1000h]
0x180013db7  mov     byte ptr [r11], 0
0x180013dbb  cmp     r10, r11
0x180013dbe  jnz     short cs10
0x180013dc0  mov     r10, [rsp+10h+var_10]
0x180013dc4  mov     r11, [rsp+10h+var_8]
0x180013dc9  add     rsp, 10h
0x180013dcd  retn
```
