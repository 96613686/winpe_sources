# _alloca_probe

- ea: `0x14001a7d0`
- end: `0x14001a81e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x14000268c`
- `0x14000290c`
- `0x140002bb8`
- `0x1400064cc`
- `0x1400085e0`
- `0x140008708`
- `0x140010dfc`
- `0x140010f4c`
- `0x140011080`
- `0x140011148`
- `0x140012b58`
- `0x140015a90`

## callees

- `0x14001a7d0`

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
0x14001a7d0  sub     rsp, 10h
0x14001a7d4  mov     [rsp+10h+var_10], r10
0x14001a7d8  mov     [rsp+10h+var_8], r11
0x14001a7dd  xor     r11, r11
0x14001a7e0  lea     r10, [rsp+10h+arg_0]
0x14001a7e5  sub     r10, rax
0x14001a7e8  cmovb   r10, r11
0x14001a7ec  mov     r11, gs:10h
0x14001a7f5  cmp     r10, r11
0x14001a7f8  jnb     short loc_14001A810
0x14001a7fa  and     r10w, 0F000h
0x14001a800  lea     r11, [r11-1000h]
0x14001a807  mov     byte ptr [r11], 0
0x14001a80b  cmp     r10, r11
0x14001a80e  jnz     short loc_14001A800
0x14001a810  mov     r10, [rsp+10h+var_10]
0x14001a814  mov     r11, [rsp+10h+var_8]
0x14001a819  add     rsp, 10h
0x14001a81d  retn
```
