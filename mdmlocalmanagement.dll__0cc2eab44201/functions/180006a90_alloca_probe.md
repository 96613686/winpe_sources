# _alloca_probe

- ea: `0x180006a90`
- end: `0x180006ade`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800023a0`
- `0x180002624`
- `0x1800028d4`
- `0x1800057a0`

## callees

- `0x180006a90`

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
0x180006a90  sub     rsp, 10h
0x180006a94  mov     [rsp+10h+var_10], r10
0x180006a98  mov     [rsp+10h+var_8], r11
0x180006a9d  xor     r11, r11
0x180006aa0  lea     r10, [rsp+10h+arg_0]
0x180006aa5  sub     r10, rax
0x180006aa8  cmovb   r10, r11
0x180006aac  mov     r11, gs:10h
0x180006ab5  cmp     r10, r11
0x180006ab8  jnb     short cs20
0x180006aba  and     r10w, 0F000h
0x180006ac0  lea     r11, [r11-1000h]
0x180006ac7  mov     byte ptr [r11], 0
0x180006acb  cmp     r10, r11
0x180006ace  jnz     short cs10
0x180006ad0  mov     r10, [rsp+10h+var_10]
0x180006ad4  mov     r11, [rsp+10h+var_8]
0x180006ad9  add     rsp, 10h
0x180006add  retn
```
