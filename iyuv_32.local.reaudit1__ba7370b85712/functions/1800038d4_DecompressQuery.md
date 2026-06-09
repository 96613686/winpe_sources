# DecompressQuery

- ea: `0x1800038d4`
- end: `0x180003a2c`
- name: `DecompressQuery`
- size: `344`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002710`
- `0x180003648`
- `0x1800036d0`
- `0x1800037c4`

## callees

- `0x1800038d4`
- `0x180003a34`

## pseudocode

```c
__int64 __fastcall DecompressQuery(_DWORD *a1, __int64 a2)
{
  unsigned int v5; // eax
  int v6; // r10d
  unsigned __int8 v7; // r14
  int v8; // r9d
  unsigned __int8 v9; // bp
  int v10; // r8d
  unsigned __int8 v11; // si
  int v12; // edx
  unsigned __int8 v13; // r11
  int v14; // eax
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // eax
  int v19; // ecx
  int v20; // ecx
  int v21; // eax
  int v22; // ecx
  int v23; // eax
  int v24; // ecx
  int v25; // ecx
  int v26; // eax
  int v27; // ecx
  int v28; // ecx
  int v29; // eax
  unsigned int v30; // eax
  int v31; // eax

  if ( !a1 )
    return 4294967196LL;
  if ( (unsigned int)ValidateBitmapInfoHeader() )
  {
    v5 = a1[4];
    v6 = (unsigned __int8)v5;
    v5 >>= 8;
    v7 = v6 - 97;
    v8 = (unsigned __int8)v5;
    v5 >>= 8;
    v9 = v8 - 97;
    v10 = (unsigned __int8)v5;
    v11 = v5 - 97;
    v12 = BYTE1(v5);
    v13 = BYTE1(v5) - 97;
    v14 = (unsigned __int8)v5 - 32;
    v15 = v12 - 32;
    if ( v13 > 0x19u )
      v15 = v12;
    v16 = v15 << 8;
    if ( v11 > 0x19u )
      v14 = v10;
    v17 = v14 + v16;
    v18 = v8 - 32;
    v19 = v17 << 16;
    if ( v9 > 0x19u )
      v18 = v8;
    v20 = (v18 << 8) + v19;
    v21 = v6 - 32;
    if ( v7 > 0x19u )
      v21 = v6;
    if ( v21 + v20 == 1448433993 )
      goto LABEL_35;
    v22 = v12 - 32;
    v23 = v10 - 32;
    if ( v13 > 0x19u )
      v22 = v12;
    v24 = v22 << 8;
    if ( v11 > 0x19u )
      v23 = v10;
    v25 = v23 + v24;
    v26 = v8 - 32;
    v27 = v25 << 16;
    if ( v9 > 0x19u )
      v26 = v8;
    v28 = (v26 << 8) + v27;
    v29 = v6 - 32;
    if ( v7 > 0x19u )
      v29 = v6;
    if ( v29 + v28 == 808596553 )
    {
LABEL_35:
      v30 = a1[1];
      if ( v30 <= 0x800 && a1[2] <= 0x800u && v30 >= 0x10 && a1[2] >= 0x10u )
      {
        if ( !a2 )
          return 0;
        if ( *(_DWORD *)(a2 + 4) == v30 )
        {
          v31 = -*(_DWORD *)(a2 + 8);
          if ( *(int *)(a2 + 8) > 0 )
            v31 = *(_DWORD *)(a2 + 8);
          if ( v31 == a1[2]
            && ((*(_WORD *)(a2 + 14) - 8) & 0xFFE7) == 0
            && *(_WORD *)(a2 + 14) != 32
            && !*(_DWORD *)(a2 + 16)
            && *(int *)(a2 + 8) >= 0 )
          {
            return 0;
          }
        }
      }
    }
  }
  return 4294967294LL;
}

```

## disassembly

```asm
0x1800038d4  push    rbx
0x1800038d6  push    rbp
0x1800038d7  push    rsi
0x1800038d8  push    rdi
0x1800038d9  push    r14
0x1800038db  sub     rsp, 20h
0x1800038df  mov     rbx, rdx
0x1800038e2  mov     rdi, rcx
0x1800038e5  test    rcx, rcx
0x1800038e8  jnz     short loc_1800038F4
0x1800038ea  mov     eax, 0FFFFFF9Ch
0x1800038ef  jmp     loc_180003A21
0x1800038f4  call    ValidateBitmapInfoHeader
0x1800038f9  test    eax, eax
0x1800038fb  jz      loc_180003A1C
0x180003901  mov     eax, [rdi+10h]
0x180003904  mov     cl, 61h ; 'a'
0x180003906  movzx   r10d, al
0x18000390a  shr     eax, 8
0x18000390d  mov     r14b, r10b
0x180003910  sub     r14b, cl
0x180003913  movzx   r9d, al
0x180003917  shr     eax, 8
0x18000391a  mov     bpl, r9b
0x18000391d  sub     bpl, cl
0x180003920  movzx   r8d, al
0x180003924  shr     eax, 8
0x180003927  mov     sil, r8b
0x18000392a  sub     sil, cl
0x18000392d  movzx   edx, al
0x180003930  mov     r11b, dl
0x180003933  sub     r11b, cl
0x180003936  lea     eax, [r8-20h]
0x18000393a  cmp     r11b, 19h
0x18000393e  lea     ecx, [rdx-20h]
0x180003941  cmova   ecx, edx
0x180003944  shl     ecx, 8
0x180003947  cmp     sil, 19h
0x18000394b  cmova   eax, r8d
0x18000394f  add     ecx, eax
0x180003951  lea     eax, [r9-20h]
0x180003955  shl     ecx, 10h
0x180003958  cmp     bpl, 19h
0x18000395c  cmova   eax, r9d
0x180003960  shl     eax, 8
0x180003963  add     ecx, eax
0x180003965  lea     eax, [r10-20h]
0x180003969  cmp     r14b, 19h
0x18000396d  cmova   eax, r10d
0x180003971  add     ecx, eax
0x180003973  cmp     ecx, 56555949h
0x180003979  jz      short loc_1800039C0
0x18000397b  cmp     r11b, 19h
0x18000397f  lea     ecx, [rdx-20h]
0x180003982  lea     eax, [r8-20h]
0x180003986  cmova   ecx, edx
0x180003989  shl     ecx, 8
0x18000398c  cmp     sil, 19h
0x180003990  cmova   eax, r8d
0x180003994  add     ecx, eax
0x180003996  lea     eax, [r9-20h]
0x18000399a  shl     ecx, 10h
0x18000399d  cmp     bpl, 19h
0x1800039a1  cmova   eax, r9d
0x1800039a5  shl     eax, 8
0x1800039a8  add     ecx, eax
0x1800039aa  lea     eax, [r10-20h]
0x1800039ae  cmp     r14b, 19h
0x1800039b2  cmova   eax, r10d
0x1800039b6  add     ecx, eax
0x1800039b8  cmp     ecx, 30323449h
0x1800039be  jnz     short loc_180003A1C
0x1800039c0  mov     eax, [rdi+4]
0x1800039c3  mov     ecx, 800h
0x1800039c8  cmp     eax, ecx
0x1800039ca  ja      short loc_180003A1C
0x1800039cc  cmp     [rdi+8], ecx
0x1800039cf  ja      short loc_180003A1C
0x1800039d1  cmp     eax, 10h
0x1800039d4  jb      short loc_180003A1C
0x1800039d6  cmp     dword ptr [rdi+8], 10h
0x1800039da  jb      short loc_180003A1C
0x1800039dc  test    rbx, rbx
0x1800039df  jnz     short loc_1800039E5
0x1800039e1  xor     eax, eax
0x1800039e3  jmp     short loc_180003A21
0x1800039e5  cmp     [rbx+4], eax
0x1800039e8  jnz     short loc_180003A1C
0x1800039ea  mov     ecx, [rbx+8]
0x1800039ed  mov     eax, ecx
0x1800039ef  neg     eax
0x1800039f1  cmovs   eax, ecx
0x1800039f4  cmp     eax, [rdi+8]
0x1800039f7  jnz     short loc_180003A1C
0x1800039f9  movzx   eax, word ptr [rbx+0Eh]
0x1800039fd  mov     edx, 0FFE7h
0x180003a02  sub     ax, 8
0x180003a06  test    dx, ax
0x180003a09  jnz     short loc_180003A1C
0x180003a0b  cmp     word ptr [rbx+0Eh], 20h ; ' '
0x180003a10  jz      short loc_180003A1C
0x180003a12  cmp     dword ptr [rbx+10h], 0
0x180003a16  jnz     short loc_180003A1C
0x180003a18  test    ecx, ecx
0x180003a1a  jns     short loc_1800039E1
0x180003a1c  mov     eax, 0FFFFFFFEh
0x180003a21  add     rsp, 20h
0x180003a25  pop     r14
0x180003a27  pop     rdi
0x180003a28  pop     rsi
0x180003a29  pop     rbp
0x180003a2a  pop     rbx
0x180003a2b  retn
```
