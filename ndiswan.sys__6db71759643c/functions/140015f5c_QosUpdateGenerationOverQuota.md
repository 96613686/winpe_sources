# QosUpdateGenerationOverQuota

- ea: `0x140015f5c`
- end: `0x140015f94`
- name: `QosUpdateGenerationOverQuota`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400097f8`

## callees

- `0x140015f5c`

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
0x140015f5c  mov     r10, [r8]
0x140015f5f  mov     rax, 0DFB23B0979B4B02Fh
0x140015f69  movzx   r11d, dl
0x140015f6d  mul     rcx
0x140015f70  shr     rdx, 13h
0x140015f74  mov     rcx, rdx
0x140015f77  sub     rcx, [r9]
0x140015f7a  jz      short loc_140015F8D
0x140015f7c  cmp     rcx, 40h ; '@'
0x140015f80  jnb     short loc_140015F87
0x140015f82  shl     r10, cl
0x140015f85  jmp     short loc_140015F8A
0x140015f87  xor     r10d, r10d
0x140015f8a  mov     [r9], rdx
0x140015f8d  or      r11, r10
0x140015f90  mov     [r8], r11
0x140015f93  retn
```
