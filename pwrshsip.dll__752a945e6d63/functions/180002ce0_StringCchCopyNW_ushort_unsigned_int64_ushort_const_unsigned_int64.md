# StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x180002ce0`
- end: `0x180002d5d`
- name: `?StringCchCopyNW@@YAJPEAG_KPEBG1@Z`
- size: `125`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800019c0`
- `0x180004918`

## callees

- `0x180002ce0`

## pseudocode

```c
__int64 __fastcall StringCchCopyNW(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int16 *a3,
        unsigned __int64 a4)
{
  unsigned __int64 v4; // r10
  unsigned __int16 *v5; // r11
  unsigned int v6; // edx

  v4 = a2;
  v5 = a1;
  if ( a2 )
  {
    if ( a2 > 0x7FFFFFFF || a4 > 0x7FFFFFFE )
    {
      v6 = -2147024809;
    }
    else
    {
      do
      {
        if ( !a4 )
          break;
        if ( !*a3 )
          break;
        *v5++ = *a3++;
        --a4;
        --v4;
      }
      while ( v4 );
      a1 = v5 - 1;
      if ( v4 )
        a1 = v5;
      v6 = v4 == 0 ? 0x8007007A : 0;
    }
    *a1 = 0;
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x180002ce0  mov     [rsp+arg_0], rbx
0x180002ce5  xor     ebx, ebx
0x180002ce7  mov     r10, rdx
0x180002cea  mov     r11, rcx
0x180002ced  test    rdx, rdx
0x180002cf0  jz      short loc_180002D48
0x180002cf2  cmp     rdx, 7FFFFFFFh
0x180002cf9  jbe     short loc_180002D02
0x180002cfb  mov     edx, 80070057h
0x180002d00  jmp     short loc_180002D52
0x180002d02  cmp     r9, 7FFFFFFEh
0x180002d09  ja      short loc_180002CFB
0x180002d0b  test    r9, r9
0x180002d0e  jz      short loc_180002D2E
0x180002d10  movzx   eax, word ptr [r8]
0x180002d14  test    ax, ax
0x180002d17  jz      short loc_180002D2E
0x180002d19  mov     [r11], ax
0x180002d1d  add     r8, 2
0x180002d21  add     r11, 2
0x180002d25  dec     r9
0x180002d28  sub     r10, 1
0x180002d2c  jnz     short loc_180002D0B
0x180002d2e  test    r10, r10
0x180002d31  lea     rcx, [r11-2]
0x180002d35  cmovnz  rcx, r11
0x180002d39  neg     r10
0x180002d3c  sbb     edx, edx
0x180002d3e  not     edx
0x180002d40  and     edx, 8007007Ah
0x180002d46  jmp     short loc_180002D52
0x180002d48  mov     edx, 80070057h
0x180002d4d  test    r10, r10
0x180002d50  jz      short loc_180002D55
0x180002d52  mov     [rcx], bx
0x180002d55  mov     rbx, [rsp+arg_0]
0x180002d5a  mov     eax, edx
0x180002d5c  retn
```
