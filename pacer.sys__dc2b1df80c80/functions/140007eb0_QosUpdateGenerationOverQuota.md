# QosUpdateGenerationOverQuota

- ea: `0x140007eb0`
- end: `0x140007ee8`
- name: `QosUpdateGenerationOverQuota`
- size: `56`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140007260`
- `0x1400101c0`

## callees

- `0x140007eb0`

## pseudocode

```c
unsigned __int64 __fastcall QosUpdateGenerationOverQuota(
        unsigned __int64 a1,
        unsigned __int8 a2,
        __int64 *a3,
        unsigned __int64 *a4)
{
  __int64 v4; // r10
  __int64 v5; // r11
  unsigned __int64 result; // rax
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rcx

  v4 = *a3;
  v5 = a2;
  result = 0xDFB23B0979B4B02FuLL * a1;
  v7 = a1 / 0x927C0;
  v8 = a1 / 0x927C0 - *a4;
  if ( v8 )
  {
    if ( v8 >= 0x40 )
      v4 = 0;
    else
      v4 <<= v8;
    *a4 = v7;
  }
  *a3 = v4 | v5;
  return result;
}

```

## disassembly

```asm
0x140007eb0  mov     r10, [r8]
0x140007eb3  mov     rax, 0DFB23B0979B4B02Fh
0x140007ebd  movzx   r11d, dl
0x140007ec1  mul     rcx
0x140007ec4  shr     rdx, 13h
0x140007ec8  mov     rcx, rdx
0x140007ecb  sub     rcx, [r9]
0x140007ece  jz      short loc_140007EE1
0x140007ed0  cmp     rcx, 40h ; '@'
0x140007ed4  jnb     short loc_140007EDB
0x140007ed6  shl     r10, cl
0x140007ed9  jmp     short loc_140007EDE
0x140007edb  xor     r10d, r10d
0x140007ede  mov     [r9], rdx
0x140007ee1  or      r11, r10
0x140007ee4  mov     [r8], r11
0x140007ee7  retn
```
