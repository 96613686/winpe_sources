# ASN1BEREncTag

- ea: `0x180007b80`
- end: `0x180007c68`
- name: `ASN1BEREncTag`
- size: `232`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x180006aa0`
- `0x180006b80`
- `0x180006c50`
- `0x180006d00`
- `0x180006df0`
- `0x180006e80`
- `0x1800072a0`
- `0x180007310`
- `0x1800074e0`
- `0x1800075e0`
- `0x180007b10`
- `0x18000a070`
- `0x18000a160`

## callees

- `0x180007b80`
- `0x180007c70`

## pseudocode

```c
__int64 __fastcall ASN1BEREncTag(__int64 a1, unsigned int a2)
{
  unsigned int v3; // esi
  unsigned int i; // eax
  unsigned int v6; // edi
  _BYTE *v7; // rax
  int v8; // ebx
  _BYTE *v10; // rcx
  unsigned int v11; // edi
  unsigned int v12; // edi
  unsigned int v13; // edi
  unsigned int v14; // edi

  v3 = a2 & 0x1FFFFFFF;
  for ( i = 0; i < 5; ++i )
  {
    v6 = i + 1;
    if ( v3 < *((_DWORD *)qword_18000C660 + i) )
      goto LABEL_6;
  }
  v6 = 6;
LABEL_6:
  if ( (unsigned int)ASN1EncCheck(a1, v6) )
  {
    v7 = *(_BYTE **)(a1 + 40);
    v8 = HIBYTE(a2) & 0xE0;
    if ( v6 == 1 )
    {
      *v7 = v3 | v8;
    }
    else
    {
      *v7 = v8 | 0x1F;
      v10 = (_BYTE *)++*(_QWORD *)(a1 + 40);
      v11 = v6 - 2;
      if ( v11 )
      {
        v12 = v11 - 1;
        if ( v12 )
        {
          v13 = v12 - 1;
          if ( v13 )
          {
            v14 = v13 - 1;
            if ( v14 )
            {
              if ( v14 != 1 )
                return 1;
              *v10 = (v3 >> 28) | 0x80;
              v10 = (_BYTE *)++*(_QWORD *)(a1 + 40);
            }
            *v10 = (v3 >> 21) | 0x80;
            v10 = (_BYTE *)++*(_QWORD *)(a1 + 40);
          }
          *v10 = (v3 >> 14) | 0x80;
          v10 = (_BYTE *)++*(_QWORD *)(a1 + 40);
        }
        *v10 = (v3 >> 7) | 0x80;
        v10 = (_BYTE *)++*(_QWORD *)(a1 + 40);
      }
      *v10 = v3 & 0x7F;
    }
    ++*(_QWORD *)(a1 + 40);
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180007b80  push    rbx
0x180007b82  push    rbp
0x180007b83  push    rsi
0x180007b84  push    rdi
0x180007b85  sub     rsp, 28h
0x180007b89  mov     esi, edx
0x180007b8b  mov     ebx, edx
0x180007b8d  and     esi, 1FFFFFFFh
0x180007b93  lea     rdx, qword_18000C660
0x180007b9a  xor     eax, eax
0x180007b9c  mov     rbp, rcx
0x180007b9f  cmp     eax, 5
0x180007ba2  jnb     short loc_180007BB2
0x180007ba4  mov     ecx, eax
0x180007ba6  lea     edi, [rax+1]
0x180007ba9  cmp     esi, [rdx+rcx*4]
0x180007bac  jb      short loc_180007BB7
0x180007bae  mov     eax, edi
0x180007bb0  jmp     short loc_180007B9F
0x180007bb2  mov     edi, 6
0x180007bb7  mov     edx, edi
0x180007bb9  mov     rcx, rbp
0x180007bbc  call    ASN1EncCheck
0x180007bc1  test    eax, eax
0x180007bc3  jz      short loc_180007BEE
0x180007bc5  mov     rax, [rbp+28h]
0x180007bc9  shr     ebx, 18h
0x180007bcc  and     ebx, 0E0h
0x180007bd2  cmp     edi, 1
0x180007bd5  jnz     short loc_180007BF2
0x180007bd7  or      bl, sil
0x180007bda  mov     [rax], bl
0x180007bdc  inc     qword ptr [rbp+28h]
0x180007be0  mov     eax, 1
0x180007be5  add     rsp, 28h
0x180007be9  pop     rdi
0x180007bea  pop     rsi
0x180007beb  pop     rbp
0x180007bec  pop     rbx
0x180007bed  retn
0x180007bee  xor     eax, eax
0x180007bf0  jmp     short loc_180007BE5
0x180007bf2  or      bl, 1Fh
0x180007bf5  mov     [rax], bl
0x180007bf7  inc     qword ptr [rbp+28h]
0x180007bfb  mov     rcx, [rbp+28h]
0x180007bff  sub     edi, 2
0x180007c02  jz      short loc_180007C5C
0x180007c04  sub     edi, 1
0x180007c07  jz      short loc_180007C4B
0x180007c09  sub     edi, 1
0x180007c0c  jz      short loc_180007C3A
0x180007c0e  sub     edi, 1
0x180007c11  jz      short loc_180007C29
0x180007c13  cmp     edi, 1
0x180007c16  jnz     short loc_180007BE0
0x180007c18  mov     eax, esi
0x180007c1a  shr     eax, 1Ch
0x180007c1d  or      al, 80h
0x180007c1f  mov     [rcx], al
0x180007c21  inc     qword ptr [rbp+28h]
0x180007c25  mov     rcx, [rbp+28h]
0x180007c29  mov     eax, esi
0x180007c2b  shr     eax, 15h
0x180007c2e  or      al, 80h
0x180007c30  mov     [rcx], al
0x180007c32  inc     qword ptr [rbp+28h]
0x180007c36  mov     rcx, [rbp+28h]
0x180007c3a  mov     eax, esi
0x180007c3c  shr     eax, 0Eh
0x180007c3f  or      al, 80h
0x180007c41  mov     [rcx], al
0x180007c43  inc     qword ptr [rbp+28h]
0x180007c47  mov     rcx, [rbp+28h]
0x180007c4b  mov     eax, esi
0x180007c4d  shr     eax, 7
0x180007c50  or      al, 80h
0x180007c52  mov     [rcx], al
0x180007c54  inc     qword ptr [rbp+28h]
0x180007c58  mov     rcx, [rbp+28h]
0x180007c5c  and     sil, 7Fh
0x180007c60  mov     [rcx], sil
0x180007c63  jmp     loc_180007BDC
```
