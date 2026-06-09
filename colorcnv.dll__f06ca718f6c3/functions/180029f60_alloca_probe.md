# _alloca_probe

- ea: `0x180029f60`
- end: `0x180029fae`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f47c`
- `0x18000f530`
- `0x18000f7cc`
- `0x180014a30`
- `0x180014b70`

## callees

- `0x180029f60`

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
0x180029f60  sub     rsp, 10h
0x180029f64  mov     [rsp+10h+var_10], r10
0x180029f68  mov     [rsp+10h+var_8], r11
0x180029f6d  xor     r11, r11
0x180029f70  lea     r10, [rsp+10h+arg_0]
0x180029f75  sub     r10, rax
0x180029f78  cmovb   r10, r11
0x180029f7c  mov     r11, gs:10h
0x180029f85  cmp     r10, r11
0x180029f88  jnb     short cs20
0x180029f8a  and     r10w, 0F000h
0x180029f90  lea     r11, [r11-1000h]
0x180029f97  mov     byte ptr [r11], 0
0x180029f9b  cmp     r10, r11
0x180029f9e  jnz     short cs10
0x180029fa0  mov     r10, [rsp+10h+var_10]
0x180029fa4  mov     r11, [rsp+10h+var_8]
0x180029fa9  add     rsp, 10h
0x180029fad  retn
```
