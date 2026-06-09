# ASN1BEREncRemoveZeroBits2

- ea: `0x180008aa0`
- end: `0x180008b3d`
- name: `ASN1BEREncRemoveZeroBits2`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800089b0`

## callees

- `0x180008aa0`

## pseudocode

```c
__int64 __fastcall ASN1BEREncRemoveZeroBits2(unsigned int *a1, __int64 a2, unsigned int a3)
{
  unsigned int v3; // r9d
  _BYTE *v5; // rdx
  bool v6; // cf
  int i; // ecx

  v3 = *a1;
  if ( *a1 + 7 >= *a1 )
  {
    if ( v3 <= a3 )
      return 1;
    v5 = (_BYTE *)(((unsigned __int64)(v3 - 1) >> 3) + a2);
    if ( (v3 & 7) == 0 )
      goto LABEL_16;
    if ( (*((_BYTE *)&qword_18000C618 + (v3 & 7)) & *v5) == 0 )
    {
      v3 &= 0xFFFFFFF8;
      --v5;
    }
    if ( (v3 & 7) != 0 )
    {
LABEL_7:
      v6 = v3 < a3;
      if ( v3 > a3 )
      {
LABEL_8:
        for ( i = ((_BYTE)v3 - 1) & 7; i >= 0; --i )
        {
          if ( ((128 >> i) & (unsigned __int8)*v5) != 0 )
            break;
          --v3;
        }
        v6 = v3 < a3;
      }
    }
    else
    {
LABEL_16:
      v6 = v3 < a3;
      if ( v3 > a3 )
      {
        while ( !*v5 )
        {
          v3 -= 8;
          --v5;
          if ( v3 <= a3 )
            goto LABEL_7;
        }
        goto LABEL_8;
      }
    }
    if ( v6 )
      v3 = a3;
    *a1 = v3;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180008aa0  mov     r9d, [rcx]
0x180008aa3  mov     r11, rcx
0x180008aa6  lea     eax, [r9+7]
0x180008aaa  cmp     eax, r9d
0x180008aad  jb      short loc_180008B11
0x180008aaf  cmp     r9d, r8d
0x180008ab2  jbe     short loc_180008B0B
0x180008ab4  lea     ecx, [r9-1]
0x180008ab8  mov     r10d, 0FFFFFFF8h
0x180008abe  shr     rcx, 3
0x180008ac2  add     rdx, rcx
0x180008ac5  test    r9b, 7
0x180008ac9  jz      short loc_180008B1C
0x180008acb  mov     eax, r9d
0x180008ace  lea     rcx, qword_18000C618
0x180008ad5  and     eax, 7
0x180008ad8  mov     al, [rax+rcx]
0x180008adb  test    [rdx], al
0x180008add  jz      short loc_180008B14
0x180008adf  test    r9b, 7
0x180008ae3  jz      short loc_180008B1C
0x180008ae5  cmp     r9d, r8d
0x180008ae8  jbe     short loc_180008B04
0x180008aea  movzx   r10d, byte ptr [rdx]
0x180008aee  lea     ecx, [r9-1]
0x180008af2  and     ecx, 7
0x180008af5  mov     eax, 80h
0x180008afa  sar     eax, cl
0x180008afc  test    r10d, eax
0x180008aff  jz      short loc_180008B33
0x180008b01  cmp     r9d, r8d
0x180008b04  cmovb   r9d, r8d
0x180008b08  mov     [r11], r9d
0x180008b0b  mov     eax, 1
0x180008b10  retn
0x180008b11  xor     eax, eax
0x180008b13  retn
0x180008b14  and     r9d, r10d
0x180008b17  dec     rdx
0x180008b1a  jmp     short loc_180008ADF
0x180008b1c  cmp     r9d, r8d
0x180008b1f  jbe     short loc_180008B04
0x180008b21  cmp     byte ptr [rdx], 0
0x180008b24  jnz     short loc_180008AEA
0x180008b26  add     r9d, r10d
0x180008b29  dec     rdx
0x180008b2c  cmp     r9d, r8d
0x180008b2f  ja      short loc_180008B21
0x180008b31  jmp     short loc_180008AE5
0x180008b33  dec     r9d
0x180008b36  sub     ecx, 1
0x180008b39  jns     short loc_180008AF5
0x180008b3b  jmp     short loc_180008B01
```
