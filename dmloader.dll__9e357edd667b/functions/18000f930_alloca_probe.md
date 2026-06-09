# _alloca_probe

- ea: `0x18000f930`
- end: `0x18000f97e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180002390`
- `0x1800025f8`
- `0x180002894`
- `0x1800060b4`
- `0x180007994`

## callees

- `0x18000f930`

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
0x18000f930  sub     rsp, 10h
0x18000f934  mov     [rsp+10h+var_10], r10
0x18000f938  mov     [rsp+10h+var_8], r11
0x18000f93d  xor     r11, r11
0x18000f940  lea     r10, [rsp+10h+arg_0]
0x18000f945  sub     r10, rax
0x18000f948  cmovb   r10, r11
0x18000f94c  mov     r11, gs:10h
0x18000f955  cmp     r10, r11
0x18000f958  jnb     short cs20
0x18000f95a  and     r10w, 0F000h
0x18000f960  lea     r11, [r11-1000h]
0x18000f967  mov     byte ptr [r11], 0
0x18000f96b  cmp     r10, r11
0x18000f96e  jnz     short cs10
0x18000f970  mov     r10, [rsp+10h+var_10]
0x18000f974  mov     r11, [rsp+10h+var_8]
0x18000f979  add     rsp, 10h
0x18000f97d  retn
```
