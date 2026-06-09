# _alloca_probe

- ea: `0x140009030`
- end: `0x14000907e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140002504`
- `0x140002788`
- `0x140002a38`
- `0x1400058a0`
- `0x1400061bc`
- `0x1400076dc`
- `0x140007a88`
- `0x14000836c`

## callees

- `0x140009030`

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
0x140009030  sub     rsp, 10h
0x140009034  mov     [rsp+10h+var_10], r10
0x140009038  mov     [rsp+10h+var_8], r11
0x14000903d  xor     r11, r11
0x140009040  lea     r10, [rsp+10h+arg_0]
0x140009045  sub     r10, rax
0x140009048  cmovb   r10, r11
0x14000904c  mov     r11, gs:10h
0x140009055  cmp     r10, r11
0x140009058  jnb     short loc_140009070
0x14000905a  and     r10w, 0F000h
0x140009060  lea     r11, [r11-1000h]
0x140009067  mov     byte ptr [r11], 0
0x14000906b  cmp     r10, r11
0x14000906e  jnz     short loc_140009060
0x140009070  mov     r10, [rsp+10h+var_10]
0x140009074  mov     r11, [rsp+10h+var_8]
0x140009079  add     rsp, 10h
0x14000907d  retn
```
