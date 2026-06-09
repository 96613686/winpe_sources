# ASN1BEREncRemoveZeroBits

- ea: `0x180008bb0`
- end: `0x180008c3e`
- name: `ASN1BEREncRemoveZeroBits`
- size: `142`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008bb0`

## pseudocode

```c
__int64 __fastcall ASN1BEREncRemoveZeroBits(int *a1, __int64 a2)
{
  int v2; // r8d
  _BYTE *v4; // rdx
  int i; // ecx

  v2 = *a1;
  if ( *a1 + 7 >= (unsigned int)*a1 )
  {
    v4 = (_BYTE *)(((unsigned __int64)(unsigned int)(v2 - 1) >> 3) + a2);
    if ( (v2 & 7) == 0 )
      goto LABEL_13;
    if ( (*((_BYTE *)&qword_18000C618 + (v2 & 7)) & *v4) == 0 )
    {
      v2 &= 0xFFFFFFF8;
      --v4;
    }
    if ( (v2 & 7) != 0 )
    {
LABEL_6:
      if ( v2 )
      {
LABEL_7:
        for ( i = ((_BYTE)v2 - 1) & 7; i >= 0; --i )
        {
          if ( ((128 >> i) & (unsigned __int8)*v4) != 0 )
            break;
          --v2;
        }
      }
    }
    else
    {
LABEL_13:
      if ( v2 )
      {
        while ( !*v4 )
        {
          --v4;
          v2 -= 8;
          if ( !v2 )
            goto LABEL_6;
        }
        goto LABEL_7;
      }
    }
    *a1 = v2;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180008bb0  mov     r8d, [rcx]
0x180008bb3  mov     r9, rcx
0x180008bb6  lea     eax, [r8+7]
0x180008bba  cmp     eax, r8d
0x180008bbd  jb      short loc_180008C15
0x180008bbf  lea     ecx, [r8-1]
0x180008bc3  mov     r10d, 0FFFFFFF8h
0x180008bc9  shr     rcx, 3
0x180008bcd  add     rdx, rcx
0x180008bd0  test    r8b, 7
0x180008bd4  jz      short loc_180008C2A
0x180008bd6  mov     eax, r8d
0x180008bd9  lea     rcx, qword_18000C618
0x180008be0  and     eax, 7
0x180008be3  mov     al, [rax+rcx]
0x180008be6  test    [rdx], al
0x180008be8  jz      short loc_180008C22
0x180008bea  test    r8b, 7
0x180008bee  jz      short loc_180008C2A
0x180008bf0  test    r8d, r8d
0x180008bf3  jz      short loc_180008C0C
0x180008bf5  movzx   r10d, byte ptr [rdx]
0x180008bf9  lea     ecx, [r8-1]
0x180008bfd  and     ecx, 7
0x180008c00  mov     edx, 80h
0x180008c05  sar     edx, cl
0x180008c07  test    r10d, edx
0x180008c0a  jz      short loc_180008C18
0x180008c0c  mov     [r9], r8d
0x180008c0f  mov     eax, 1
0x180008c14  retn
0x180008c15  xor     eax, eax
0x180008c17  retn
0x180008c18  dec     r8d
0x180008c1b  sub     ecx, 1
0x180008c1e  js      short loc_180008C0C
0x180008c20  jmp     short loc_180008C00
0x180008c22  and     r8d, r10d
0x180008c25  dec     rdx
0x180008c28  jmp     short loc_180008BEA
0x180008c2a  test    r8d, r8d
0x180008c2d  jz      short loc_180008C0C
0x180008c2f  cmp     byte ptr [rdx], 0
0x180008c32  jnz     short loc_180008BF5
0x180008c34  dec     rdx
0x180008c37  add     r8d, r10d
0x180008c3a  jnz     short loc_180008C2F
0x180008c3c  jmp     short loc_180008BF0
```
