# _alloca_probe

- ea: `0x140017670`
- end: `0x1400176be`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1400037b8`
- `0x140003868`
- `0x140003b04`
- `0x1400067a0`
- `0x140008ff8`
- `0x140009d34`
- `0x14000a8c8`

## callees

- `0x140017670`

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
0x140017670  sub     rsp, 10h
0x140017674  mov     [rsp+10h+var_10], r10
0x140017678  mov     [rsp+10h+var_8], r11
0x14001767d  xor     r11, r11
0x140017680  lea     r10, [rsp+10h+arg_0]
0x140017685  sub     r10, rax
0x140017688  cmovb   r10, r11
0x14001768c  mov     r11, gs:10h
0x140017695  cmp     r10, r11
0x140017698  jnb     short loc_1400176B0
0x14001769a  and     r10w, 0F000h
0x1400176a0  lea     r11, [r11-1000h]
0x1400176a7  mov     byte ptr [r11], 0
0x1400176ab  cmp     r10, r11
0x1400176ae  jnz     short loc_1400176A0
0x1400176b0  mov     r10, [rsp+10h+var_10]
0x1400176b4  mov     r11, [rsp+10h+var_8]
0x1400176b9  add     rsp, 10h
0x1400176bd  retn
```
