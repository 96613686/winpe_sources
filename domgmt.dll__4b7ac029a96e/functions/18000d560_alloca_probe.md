# _alloca_probe

- ea: `0x18000d560`
- end: `0x18000d5ae`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1800032e8`
- `0x180003568`
- `0x180003814`
- `0x1800068b0`
- `0x180007060`
- `0x1800070d0`
- `0x18000a0b8`
- `0x18000bf1c`

## callees

- `0x18000d560`

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
0x18000d560  sub     rsp, 10h
0x18000d564  mov     [rsp+10h+var_10], r10
0x18000d568  mov     [rsp+10h+var_8], r11
0x18000d56d  xor     r11, r11
0x18000d570  lea     r10, [rsp+10h+arg_0]
0x18000d575  sub     r10, rax
0x18000d578  cmovb   r10, r11
0x18000d57c  mov     r11, gs:10h
0x18000d585  cmp     r10, r11
0x18000d588  jnb     short cs20
0x18000d58a  and     r10w, 0F000h
0x18000d590  lea     r11, [r11-1000h]
0x18000d597  mov     byte ptr [r11], 0
0x18000d59b  cmp     r10, r11
0x18000d59e  jnz     short cs10
0x18000d5a0  mov     r10, [rsp+10h+var_10]
0x18000d5a4  mov     r11, [rsp+10h+var_8]
0x18000d5a9  add     rsp, 10h
0x18000d5ad  retn
```
