# __alloca_probe

- ea: `0x180136780`
- end: `0x1801367ce`
- name: `__alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `20`
- callee_count: `1`
- tags: ``

## callers

- `0x180003070`
- `0x1800162e0`
- `0x180018ba0`
- `0x180018ce0`
- `0x1800430b4`
- `0x18005b770`
- `0x180060380`
- `0x180076e20`
- `0x180077020`
- `0x1800771a0`
- `0x180077ac0`
- `0x180077c40`
- `0x180078cb0`
- `0x180078f80`
- `0x18007abb0`
- `0x18007b350`
- `0x18007b910`
- `0x18007bf00`
- `0x18007c020`
- `0x180096920`

## callees

- `0x180136780`

## pseudocode

```c
unsigned __int64 __fastcall _alloca_probe()
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
0x180136780  sub     rsp, 10h
0x180136784  mov     [rsp+10h+var_10], r10
0x180136788  mov     [rsp+10h+var_8], r11
0x18013678d  xor     r11, r11
0x180136790  lea     r10, [rsp+10h+arg_0]
0x180136795  sub     r10, rax
0x180136798  cmovb   r10, r11
0x18013679c  mov     r11, gs:10h
0x1801367a5  cmp     r10, r11
0x1801367a8  jnb     short cs20
0x1801367aa  and     r10w, 0F000h
0x1801367b0  lea     r11, [r11-1000h]
0x1801367b7  mov     byte ptr [r11], 0
0x1801367bb  cmp     r10, r11
0x1801367be  jnz     short cs10
0x1801367c0  mov     r10, [rsp+10h+var_10]
0x1801367c4  mov     r11, [rsp+10h+var_8]
0x1801367c9  add     rsp, 10h
0x1801367cd  retn
```
