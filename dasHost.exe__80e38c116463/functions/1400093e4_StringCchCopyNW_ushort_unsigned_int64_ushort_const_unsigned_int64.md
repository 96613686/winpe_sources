# StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x1400093e4`
- end: `0x140009461`
- name: `?StringCchCopyNW@@YAJPEAG_KPEBG1@Z`
- size: `125`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140009850`
- `0x14000bf80`
- `0x14000fea4`
- `0x14001211c`
- `0x14001a3a8`

## callees

- `0x1400093e4`

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
0x1400093e4  mov     [rsp+arg_0], rbx
0x1400093e9  xor     ebx, ebx
0x1400093eb  mov     r10, rdx
0x1400093ee  mov     r11, rcx
0x1400093f1  test    rdx, rdx
0x1400093f4  jz      short loc_14000944C
0x1400093f6  cmp     rdx, 7FFFFFFFh
0x1400093fd  jbe     short loc_140009406
0x1400093ff  mov     edx, 80070057h
0x140009404  jmp     short loc_140009456
0x140009406  cmp     r9, 7FFFFFFEh
0x14000940d  ja      short loc_1400093FF
0x14000940f  test    r9, r9
0x140009412  jz      short loc_140009432
0x140009414  movzx   eax, word ptr [r8]
0x140009418  test    ax, ax
0x14000941b  jz      short loc_140009432
0x14000941d  mov     [r11], ax
0x140009421  add     r8, 2
0x140009425  add     r11, 2
0x140009429  dec     r9
0x14000942c  sub     r10, 1
0x140009430  jnz     short loc_14000940F
0x140009432  test    r10, r10
0x140009435  lea     rcx, [r11-2]
0x140009439  cmovnz  rcx, r11
0x14000943d  neg     r10
0x140009440  sbb     edx, edx
0x140009442  not     edx
0x140009444  and     edx, 8007007Ah
0x14000944a  jmp     short loc_140009456
0x14000944c  mov     edx, 80070057h
0x140009451  test    r10, r10
0x140009454  jz      short loc_140009459
0x140009456  mov     [rcx], bx
0x140009459  mov     rbx, [rsp+arg_0]
0x14000945e  mov     eax, edx
0x140009460  retn
```
