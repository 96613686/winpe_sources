# CdFindActiveVolDescriptor

- ea: `0x140013c0c`
- end: `0x140013e26`
- name: `CdFindActiveVolDescriptor`
- size: `538`
- prototype: `char __fastcall(__int64, __int64, _BYTE *, char)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400142d8`
- `0x140015090`

## callees

- `0x140003000`
- `0x140010c38`
- `0x140013c0c`
- `0x140015fac`

## import_xrefs

- `ntoskrnl!RtlOemToUnicodeN` at `0x140013d86`
- `ntoskrnl!RtlOemToUnicodeN` at `0x140013d86`

## pseudocode

```c
char __fastcall CdFindActiveVolDescriptor(__int64 a1, __int64 a2, _BYTE *a3, char a4)
{
  __int64 v4; // rax
  __int64 v8; // r15
  int v9; // esi
  int v10; // edx
  int i; // r14d
  char *v12; // rdx
  char v13; // al
  int v14; // eax
  __int64 v15; // r9
  unsigned int v16; // eax
  __int64 v17; // r8
  int v18; // edx
  __int64 v19; // r9
  ULONG BytesInUnicodeString; // [rsp+68h] [rbp+10h] BYREF
  int v22; // [rsp+78h] [rbp+20h]

  LODWORD(v4) = *(_DWORD *)(a2 + 48);
  BytesInUnicodeString = 0;
  v8 = a1;
  v9 = 2048;
  if ( (v4 & 2) == 0 && !a4 )
    goto LABEL_19;
  if ( CdNoJoliet )
  {
LABEL_18:
    if ( a4 )
      return v4;
    goto LABEL_19;
  }
  v10 = *(_DWORD *)(a2 + 96);
  for ( i = 16; ; ++i )
  {
    CdReadSectors(a1, (i + v10) << 11, (int)a3, 0, a3, *(PDEVICE_OBJECT *)(a2 + 16));
    if ( CdIsoId != *(_DWORD *)(a3 + 1) || byte_140007154 != a3[5] || a3[6] != 1 || *a3 == 0xFF )
    {
      LOBYTE(v4) = (unsigned __int8)memmove(a3, a3 + 2048, 0x800u);
      goto LABEL_18;
    }
    if ( *a3 == 2 )
    {
      if ( *((_WORD *)a3 + 44) == *(_WORD *)CdJolietEscape[0] )
      {
        LOBYTE(v4) = a3[90];
        if ( (_BYTE)v4 == CdJolietEscape[0][2] )
          break;
      }
      if ( *((_WORD *)a3 + 44) == *(_WORD *)"%/C" )
      {
        LOBYTE(v4) = a3[90];
        if ( (_BYTE)v4 == aC[2] )
          break;
      }
      if ( *((_WORD *)a3 + 44) == *(_WORD *)"%/E" )
      {
        LOBYTE(v4) = a3[90];
        if ( (_BYTE)v4 == aE[2] )
          break;
      }
    }
    v10 = *(_DWORD *)(a2 + 96);
    LODWORD(a1) = v8;
  }
  if ( !a4 )
  {
    v16 = *(_DWORD *)(a2 + 48) & 0xFFFFFFFD;
    *(_DWORD *)(a2 + 100) = i;
    *(_DWORD *)(a2 + 48) = v16 | 4;
LABEL_19:
    v12 = a3;
    v22 = 0;
    do
    {
      v13 = *v12;
      --v9;
      ++v12;
      *((_BYTE *)&v22 + (v9 & 3)) += v13;
    }
    while ( v9 );
    *(_DWORD *)(*(_QWORD *)(a2 + 8) + 24LL) = v22;
    v14 = *(_DWORD *)(a2 + 48);
    v15 = *(_QWORD *)(a2 + 8);
    if ( (v14 & 4) != 0 )
    {
      CdConvertBigToLittleEndian(v8, &a3[8 * (v14 & 1) + 40], 32, v15 + 32);
      v4 = *(_QWORD *)(a2 + 8);
      *(_WORD *)(v4 + 6) = 64;
    }
    else
    {
      *(_WORD *)(v15 + 6) = 0;
      LODWORD(v4) = RtlOemToUnicodeN(
                      (PWCH)(*(_QWORD *)(a2 + 8) + 32LL),
                      0x40u,
                      &BytesInUnicodeString,
                      &a3[8 * (*(_DWORD *)(a2 + 48) & 1) + 40],
                      0x20u);
      if ( (int)v4 >= 0 )
      {
        LOBYTE(v4) = BytesInUnicodeString;
        *(_WORD *)(*(_QWORD *)(a2 + 8) + 6LL) = BytesInUnicodeString;
      }
    }
    v17 = *(_QWORD *)(a2 + 8);
    v18 = *(unsigned __int16 *)(v17 + 6) >> 1;
    if ( v18 )
    {
      do
      {
        v19 = (unsigned int)(v18 - 1);
        LOBYTE(v4) = -33;
        if ( (*(_WORD *)(v17 + 2 * v19 + 32) & 0xFFDF) != 0 )
          break;
        --v18;
      }
      while ( (_DWORD)v19 );
    }
    *(_WORD *)(v17 + 6) = 2 * v18;
  }
  return v4;
}

```

## disassembly

```asm
0x140013c0c  mov     [rsp+arg_0], rbx
0x140013c11  push    rbp
0x140013c12  push    rsi
0x140013c13  push    rdi
0x140013c14  push    r14
0x140013c16  push    r15
0x140013c18  sub     rsp, 30h
0x140013c1c  mov     eax, [rdx+30h]
0x140013c1f  mov     bpl, r9b
0x140013c22  mov     [rsp+58h+BytesInUnicodeString], 0
0x140013c2a  mov     rbx, r8
0x140013c2d  mov     rdi, rdx
0x140013c30  mov     r15, rcx
0x140013c33  mov     esi, 800h
0x140013c38  test    al, 2
0x140013c3a  jnz     short loc_140013C45
0x140013c3c  test    r9b, r9b
0x140013c3f  jz      loc_140013D24
0x140013c45  cmp     cs:CdNoJoliet, 0
0x140013c4c  jnz     loc_140013D1B
0x140013c52  mov     edx, [rdx+60h]
0x140013c55  mov     r14d, 10h
0x140013c5b  jmp     short loc_140013CD2
0x140013c5d  cmp     byte ptr [rbx+6], 1
0x140013c61  jnz     loc_140013D09
0x140013c67  mov     al, [rbx]
0x140013c69  cmp     al, 0FFh
0x140013c6b  jz      loc_140013D09
0x140013c71  cmp     al, 2
0x140013c73  jnz     short loc_140013CC9
0x140013c75  mov     rcx, cs:CdJolietEscape
0x140013c7c  movzx   eax, word ptr [rbx+58h]
0x140013c80  cmp     ax, [rcx]
0x140013c83  jnz     short loc_140013C91
0x140013c85  mov     al, [rbx+5Ah]
0x140013c88  cmp     al, [rcx+2]
0x140013c8b  jz      loc_140013DA5
0x140013c91  mov     rcx, cs:off_140005008; "%/C"
0x140013c98  movzx   eax, word ptr [rbx+58h]
0x140013c9c  cmp     ax, [rcx]
0x140013c9f  jnz     short loc_140013CAD
0x140013ca1  mov     al, [rbx+5Ah]
0x140013ca4  cmp     al, [rcx+2]
0x140013ca7  jz      loc_140013DA5
0x140013cad  mov     rcx, cs:off_140005010; "%/E"
0x140013cb4  movzx   eax, word ptr [rbx+58h]
0x140013cb8  cmp     ax, [rcx]
0x140013cbb  jnz     short loc_140013CC9
0x140013cbd  mov     al, [rbx+5Ah]
0x140013cc0  cmp     al, [rcx+2]
0x140013cc3  jz      loc_140013DA5
0x140013cc9  mov     edx, [rdi+60h]
0x140013ccc  inc     r14d
0x140013ccf  mov     rcx, r15; int
0x140013cd2  mov     rax, [rdi+10h]
0x140013cd6  add     edx, r14d
0x140013cd9  mov     [rsp+58h+DeviceObject], rax; DeviceObject
0x140013cde  xor     r9d, r9d; int
0x140013ce1  shl     rdx, 0Bh; int
0x140013ce5  mov     qword ptr [rsp+58h+BytesInOemString], rbx; Buffer
0x140013cea  call    CdReadSectors
0x140013cef  mov     eax, cs:CdIsoId
0x140013cf5  cmp     eax, [rbx+1]
0x140013cf8  jnz     short loc_140013D09
0x140013cfa  mov     al, cs:byte_140007154
0x140013d00  cmp     al, [rbx+5]
0x140013d03  jz      loc_140013C5D
0x140013d09  mov     rcx, rbx; void *
0x140013d0c  lea     rdx, [rbx+800h]; Src
0x140013d13  mov     r8, rsi; Size
0x140013d16  call    memmove
0x140013d1b  test    bpl, bpl
0x140013d1e  jnz     loc_140013E14
0x140013d24  mov     rdx, rbx
0x140013d27  mov     [rsp+58h+arg_18], 0
0x140013d2f  mov     al, [rdx]
0x140013d31  dec     esi
0x140013d33  mov     ecx, esi
0x140013d35  inc     rdx
0x140013d38  and     ecx, 3
0x140013d3b  add     byte ptr [rsp+rcx+58h+arg_18], al
0x140013d3f  test    esi, esi
0x140013d41  jnz     short loc_140013D2F
0x140013d43  mov     eax, [rsp+58h+arg_18]
0x140013d47  mov     rcx, [rdi+8]
0x140013d4b  mov     [rcx+18h], eax
0x140013d4e  mov     eax, [rdi+30h]
0x140013d51  mov     r9, [rdi+8]
0x140013d55  test    al, 4
0x140013d57  jnz     short loc_140013DBF
0x140013d59  xor     eax, eax
0x140013d5b  mov     [rsp+58h+BytesInOemString], 20h ; ' '; BytesInOemString
0x140013d63  mov     [r9+6], ax
0x140013d68  lea     r8, [rsp+58h+BytesInUnicodeString]; BytesInUnicodeString
0x140013d6d  mov     eax, [rdi+30h]
0x140013d70  lea     edx, [rsi+40h]; MaxBytesInUnicodeString
0x140013d73  mov     rcx, [rdi+8]
0x140013d77  and     eax, 1
0x140013d7a  add     rcx, 20h ; ' '; UnicodeString
0x140013d7e  lea     rax, [rax+5]
0x140013d82  lea     r9, [rbx+rax*8]; OemString
0x140013d86  call    cs:__imp_RtlOemToUnicodeN
0x140013d8d  nop     dword ptr [rax+rax+00h]
0x140013d92  test    eax, eax
0x140013d94  js      short loc_140013DE6
0x140013d96  mov     rcx, [rdi+8]
0x140013d9a  movzx   eax, word ptr [rsp+58h+BytesInUnicodeString]
0x140013d9f  mov     [rcx+6], ax
0x140013da3  jmp     short loc_140013DE6
0x140013da5  test    bpl, bpl
0x140013da8  jnz     short loc_140013E14
0x140013daa  mov     eax, [rdi+30h]
0x140013dad  and     eax, 0FFFFFFFDh
0x140013db0  mov     [rdi+64h], r14d
0x140013db4  or      eax, 4
0x140013db7  mov     [rdi+30h], eax
0x140013dba  jmp     loc_140013D24
0x140013dbf  and     eax, 1
0x140013dc2  add     r9, 20h ; ' '
0x140013dc6  mov     r8d, 20h ; ' '
0x140013dcc  mov     rcx, r15
0x140013dcf  lea     rax, [rax+5]
0x140013dd3  lea     rdx, [rbx+rax*8]
0x140013dd7  call    CdConvertBigToLittleEndian
0x140013ddc  mov     rax, [rdi+8]
0x140013de0  mov     word ptr [rax+6], 40h ; '@'
0x140013de6  mov     r8, [rdi+8]
0x140013dea  movzx   edx, word ptr [r8+6]
0x140013def  shr     edx, 1
0x140013df1  jz      short loc_140013E0C
0x140013df3  lea     r9d, [rdx-1]
0x140013df7  mov     eax, 0FFDFh
0x140013dfc  test    [r8+r9*2+20h], ax
0x140013e02  jnz     short loc_140013E0C
0x140013e04  mov     edx, r9d
0x140013e07  test    r9d, r9d
0x140013e0a  jnz     short loc_140013DF3
0x140013e0c  add     dx, dx
0x140013e0f  mov     [r8+6], dx
0x140013e14  mov     rbx, [rsp+58h+arg_0]
0x140013e19  add     rsp, 30h
0x140013e1d  pop     r15
0x140013e1f  pop     r14
0x140013e21  pop     rdi
0x140013e22  pop     rsi
0x140013e23  pop     rbp
0x140013e24  retn
```
