# _alloca_probe

- ea: `0x18000a850`
- end: `0x18000a89e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180002374`
- `0x1800025f4`
- `0x1800028a0`
- `0x180005920`
- `0x180006e90`
- `0x180007080`
- `0x180007234`
- `0x1800072f0`
- `0x180007bd0`
- `0x180009aa4`
- `0x180009c70`

## callees

- `0x18000a850`

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
0x18000a850  sub     rsp, 10h
0x18000a854  mov     [rsp+10h+var_10], r10
0x18000a858  mov     [rsp+10h+var_8], r11
0x18000a85d  xor     r11, r11
0x18000a860  lea     r10, [rsp+10h+arg_0]
0x18000a865  sub     r10, rax
0x18000a868  cmovb   r10, r11
0x18000a86c  mov     r11, gs:10h
0x18000a875  cmp     r10, r11
0x18000a878  jnb     short cs20
0x18000a87a  and     r10w, 0F000h
0x18000a880  lea     r11, [r11-1000h]
0x18000a887  mov     byte ptr [r11], 0
0x18000a88b  cmp     r10, r11
0x18000a88e  jnz     short cs10
0x18000a890  mov     r10, [rsp+10h+var_10]
0x18000a894  mov     r11, [rsp+10h+var_8]
0x18000a899  add     rsp, 10h
0x18000a89d  retn
```
