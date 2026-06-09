# _alloca_probe

- ea: `0x180015650`
- end: `0x18001569e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x180003a68`
- `0x180003ce8`
- `0x180003f94`
- `0x18000830c`
- `0x18000a8a0`
- `0x18000a9c8`
- `0x18000bd2c`
- `0x18000ec38`
- `0x18000efac`
- `0x18000ff04`
- `0x180010db0`
- `0x180011b6c`
- `0x180013ad8`
- `0x180013bf4`

## callees

- `0x180015650`

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
0x180015650  sub     rsp, 10h
0x180015654  mov     [rsp+10h+var_10], r10
0x180015658  mov     [rsp+10h+var_8], r11
0x18001565d  xor     r11, r11
0x180015660  lea     r10, [rsp+10h+arg_0]
0x180015665  sub     r10, rax
0x180015668  cmovb   r10, r11
0x18001566c  mov     r11, gs:10h
0x180015675  cmp     r10, r11
0x180015678  jnb     short cs20
0x18001567a  and     r10w, 0F000h
0x180015680  lea     r11, [r11-1000h]
0x180015687  mov     byte ptr [r11], 0
0x18001568b  cmp     r10, r11
0x18001568e  jnz     short cs10
0x180015690  mov     r10, [rsp+10h+var_10]
0x180015694  mov     r11, [rsp+10h+var_8]
0x180015699  add     rsp, 10h
0x18001569d  retn
```
