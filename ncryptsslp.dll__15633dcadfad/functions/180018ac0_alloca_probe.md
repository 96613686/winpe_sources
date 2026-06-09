# _alloca_probe

- ea: `0x180018ac0`
- end: `0x180018b0e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x180006b60`
- `0x180008b80`
- `0x180009190`
- `0x1800091e0`
- `0x18000d6cc`
- `0x18000da9c`
- `0x18000fc08`
- `0x1800105e0`
- `0x180011630`
- `0x1800173e4`
- `0x180017bf8`
- `0x18001c764`
- `0x18001c878`
- `0x18001c9a0`
- `0x18001edb0`
- `0x18001f5cc`
- `0x18001fb58`
- `0x18001fd90`
- `0x18002032c`

## callees

- `0x180018ac0`

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
0x180018ac0  sub     rsp, 10h
0x180018ac4  mov     [rsp+10h+var_10], r10
0x180018ac8  mov     [rsp+10h+var_8], r11
0x180018acd  xor     r11, r11
0x180018ad0  lea     r10, [rsp+10h+arg_0]
0x180018ad5  sub     r10, rax
0x180018ad8  cmovb   r10, r11
0x180018adc  mov     r11, gs:10h
0x180018ae5  cmp     r10, r11
0x180018ae8  jnb     short loc_180018B00
0x180018aea  and     r10w, 0F000h
0x180018af0  lea     r11, [r11-1000h]
0x180018af7  mov     byte ptr [r11], 0
0x180018afb  cmp     r10, r11
0x180018afe  jnz     short loc_180018AF0
0x180018b00  mov     r10, [rsp+10h+var_10]
0x180018b04  mov     r11, [rsp+10h+var_8]
0x180018b09  add     rsp, 10h
0x180018b0d  retn
```
