# bDoFontChange

- ea: `0x18005c640`
- end: `0x18005cba1`
- name: `bDoFontChange`
- size: `1377`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180014680`

## callees

- `0x180051e5c`
- `0x18005c640`
- `0x18005cba8`
- `0x180061594`
- `0x18007e238`
- `0x18007f800`
- `0x180080604`
- `0x180084a94`
- `0x180084b3c`
- `0x180084edc`
- `0x1800850c8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005c8aa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005c93a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005c8aa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005c93a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ca10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ca24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ca10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ca24`
- `GDI32!pldcGet` at `0x18005c6ba`
- `GDI32!pldcGet` at `0x18005c6ba`
- `win32u!NtGdiGetFontData` at `0x18005cb1a`
- `win32u!NtGdiGetFontData` at `0x18005cb1a`
- `win32u!NtGdiGetGlyphIndicesW` at `0x18005c841`
- `win32u!NtGdiGetGlyphIndicesW` at `0x18005caf6`
- `win32u!NtGdiGetGlyphIndicesW` at `0x18005c841`
- `win32u!NtGdiGetGlyphIndicesW` at `0x18005caf6`
- `win32u!NtGdiGetLinkedUFIs` at `0x18005c767`
- `win32u!NtGdiGetLinkedUFIs` at `0x18005c8c7`
- `win32u!NtGdiGetLinkedUFIs` at `0x18005c767`
- `win32u!NtGdiGetLinkedUFIs` at `0x18005c8c7`
- `win32u!NtGdiGetUFI` at `0x18005c6fc`
- `win32u!NtGdiGetUFI` at `0x18005c6fc`
- `win32u!NtGdiAnyLinkedFonts` at `0x18005c74f`
- `win32u!NtGdiAnyLinkedFonts` at `0x18005c74f`

## pseudocode

```c
__int64 __fastcall bDoFontChange(__int64 a1, __int64 a2, unsigned int a3, int a4)
{
  unsigned int v4; // edi
  __int64 v5; // r15
  int v6; // r14d
  __int64 v7; // r13
  char v8; // r12
  __int64 v9; // rax
  __int64 v10; // rbx
  unsigned int v11; // esi
  __int64 v12; // rax
  int LinkedUFIs; // eax
  unsigned int v14; // r14d
  int v15; // edx
  __int64 v16; // r11
  char v17; // al
  __int64 j; // rcx
  bool v19; // zf
  _BYTE *v21; // r14
  _BYTE *v22; // r15
  int i; // ecx
  unsigned int v24; // eax
  _BYTE *v25; // r12
  __int64 v26; // r15
  int v27; // r13d
  __int64 v28; // rcx
  int v29; // r8d
  int v30; // r10d
  int v31; // r8d
  __int64 UFIEntry; // rax
  int v34; // ecx
  int GlyphIndicesW; // edi
  int FontData; // eax
  unsigned int v37; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v38; // [rsp+38h] [rbp-C8h] BYREF
  int v39; // [rsp+40h] [rbp-C0h]
  unsigned int v40; // [rsp+44h] [rbp-BCh]
  int v41; // [rsp+48h] [rbp-B8h]
  __int64 v42; // [rsp+50h] [rbp-B0h] BYREF
  int v43; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v44; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v45; // [rsp+60h] [rbp-A0h]
  _BYTE *v46; // [rsp+68h] [rbp-98h]
  __int64 v47; // [rsp+70h] [rbp-90h]
  _BYTE v48[80]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v49[64]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE hMem[160]; // [rsp+110h] [rbp+10h] BYREF

  v4 = 0;
  v5 = (int)a3;
  v6 = a2;
  v45 = a2;
  v7 = a1;
  v47 = a1;
  v41 = a4;
  v40 = a3;
  v38 = 0;
  v8 = a4;
  v42 = 0;
  memset_0(v48, 0, 0x48u);
  v44 = 0;
  v43 = 0;
  v37 = 0;
  v9 = pldcGet(v7);
  v10 = v9;
  if ( !v9 )
    return 0;
  *(_DWORD *)(v9 + 8) &= ~0x8000u;
  if ( !(unsigned int)NtGdiGetUFI(v7, &v38, v48, &v44, &v43, &v37) )
    return 0;
  v11 = 1;
  if ( (*(_DWORD *)(v10 + 8) & 0x400000) == 0 )
    goto LABEL_11;
  v12 = v38;
  if ( *(_QWORD *)(v10 + 120) != v38 )
  {
LABEL_5:
    if ( !(unsigned int)MF_ForceUFIMapping(v7, &v38) )
      return 0;
    *(_QWORD *)(v10 + 120) = v38;
LABEL_8:
    if ( (unsigned int)NtGdiAnyLinkedFonts() )
    {
      LinkedUFIs = NtGdiGetLinkedUFIs(v7, 0, 0);
      v14 = LinkedUFIs;
      if ( LinkedUFIs <= 0 )
      {
LABEL_10:
        v6 = v45;
        goto LABEL_11;
      }
      *(_DWORD *)(v10 + 8) |= 0x800000u;
      if ( LinkedUFIs > 8 )
      {
        v25 = LocalAlloc(0, 8LL * LinkedUFIs);
        if ( !v25 )
        {
LABEL_44:
          v8 = v41;
          goto LABEL_10;
        }
      }
      else
      {
        v25 = v49;
      }
      v24 = NtGdiGetLinkedUFIs(v7, v25, v14);
      v39 = v24;
      if ( !v24 )
        goto LABEL_40;
      if ( (*(_DWORD *)(v10 + 8) & 0x100000) == 0 || !(_DWORD)v5 || !v45 || (v41 & 0x10) != 0 )
        goto LABEL_37;
      v4 = 1;
      if ( (int)v5 <= 80 )
      {
        v21 = hMem;
        v22 = hMem;
      }
      else
      {
        v22 = LocalAlloc(0x40u, 2 * v5);
        v21 = v22;
        if ( !v22 )
          goto LABEL_51;
      }
      if ( (unsigned int)NtGdiGetGlyphIndicesW(v7, v45, v40, v21, 1) != -1 )
      {
        for ( i = 0; i < (int)v40; ++i )
        {
          if ( *(_WORD *)&v22[2 * i] == 0xFFFF )
            goto LABEL_51;
        }
LABEL_33:
        if ( v21 != hMem )
          LocalFree(v21);
LABEL_35:
        if ( !v4 )
          goto LABEL_40;
        v24 = v39;
LABEL_37:
        v4 = MF_SetLinkedUFIs(v7, v25, v24);
LABEL_40:
        if ( v25 != v49 )
          LocalFree(v25);
        if ( v4 )
        {
          LODWORD(v5) = v40;
          goto LABEL_44;
        }
        return 0;
      }
LABEL_51:
      v26 = 0;
      if ( v39 <= 0 )
        goto LABEL_59;
      v27 = v39;
      do
      {
        v28 = *(_QWORD *)(v10 + 88);
        v46 = &v25[8 * v26];
        if ( !pufihFindUFIEntry(v28, v46, 0)
          && (!pufihAddUFIEntry(*(_QWORD *)(v10 + 88), v30, v29, 0, v29)
           || !(unsigned int)WriteFontToSpoolFile(v10, v46, 0)) )
        {
          v4 = 0;
        }
        v26 = (unsigned int)(v26 + 1);
      }
      while ( (int)v26 < v27 );
      v7 = v47;
      if ( v4 )
LABEL_59:
        *(_DWORD *)(v10 + 8) &= ~0x800000u;
      if ( !v21 )
        goto LABEL_35;
      goto LABEL_33;
    }
LABEL_11:
    v12 = v38;
    goto LABEL_12;
  }
  if ( (*(_DWORD *)(v10 + 8) & 0x800000) != 0 )
  {
    if ( *(_DWORD *)(v10 + 124) == HIDWORD(v38) )
      goto LABEL_8;
    goto LABEL_5;
  }
LABEL_12:
  if ( !(_DWORD)v12 || (*(_DWORD *)(v10 + 8) & 0x100000) == 0 )
    return 1;
  v15 = v12;
  v42 = v12;
  if ( (v37 & 2) != 0 )
    v15 = v43;
  LODWORD(v42) = v15;
  v16 = *(_QWORD *)(v10 + 88);
  v17 = v15;
  if ( v15 == 1 )
    v17 = BYTE4(v12);
  for ( j = *(_QWORD *)(v16 + 8LL * (v17 & 0x1F)); j; j = *(_QWORD *)(j + 8) )
  {
    if ( *(_DWORD *)j == 1 )
    {
      if ( v15 != 1 )
        continue;
      v19 = *(_DWORD *)(j + 4) == HIDWORD(v12);
    }
    else
    {
      v19 = *(_DWORD *)j == v15;
    }
    if ( v19 )
      return v4;
  }
  if ( (v37 & 2) != 0 )
  {
    pufihAddUFIEntry(v16, (unsigned int)&v42, 0, 0, v37);
    v4 = WriteFontToSpoolFile(v10, &v42, v37);
    if ( v4 && !pufihFindUFIEntry(*(_QWORD *)(v10 + 96), &v38, 0) )
    {
      pufihAddUFIEntry(*(_QWORD *)(v10 + 96), (unsigned int)&v38, v31, 0, v37);
      return (unsigned int)WriteDesignVectorToSpoolFile(v10, &v42, v48, v44);
    }
    return v4;
  }
  UFIEntry = pufihFindUFIEntry(*(_QWORD *)(v10 + 104), &v38, 1);
  v34 = v7;
  if ( UFIEntry )
  {
LABEL_76:
    v4 = bAddGlyphIndices(v34, UFIEntry, v6, v5, v8);
    if ( v4 )
    {
      *(_DWORD *)(v10 + 8) |= 0x4000u;
      return v4;
    }
  }
  else
  {
    GlyphIndicesW = NtGdiGetGlyphIndicesW(v7, 0, 0, 0, 0);
    FontData = NtGdiGetFontData(v7, 1719233639, 0, 0, 0);
    if ( (unsigned int)(GlyphIndicesW - 3001) > 0xFFFFF445 || (unsigned int)(FontData - 1) > 0xFFFFFFFD )
    {
      v11 = 0;
    }
    else
    {
      UFIEntry = pufihAddUFIEntry(*(_QWORD *)(v10 + 104), (unsigned int)&v38, GlyphIndicesW, 1, v37);
      if ( UFIEntry )
      {
        v34 = v7;
        goto LABEL_76;
      }
    }
  }
  return (unsigned int)bAddUFIandWriteSpool(v7, &v38, v11, v37);
}

```

## disassembly

```asm
0x18005c640  mov     [rsp-8+arg_18], rbx
0x18005c645  push    rbp
0x18005c646  push    rsi
0x18005c647  push    rdi
0x18005c648  push    r12
0x18005c64a  push    r13
0x18005c64c  push    r14
0x18005c64e  push    r15
0x18005c650  lea     rbp, [rsp-0C0h]
0x18005c658  sub     rsp, 1C0h
0x18005c65f  mov     rax, cs:__security_cookie
0x18005c666  xor     rax, rsp
0x18005c669  mov     [rbp+0F0h+var_40], rax
0x18005c670  xor     edi, edi
0x18005c672  movsxd  r15, r8d
0x18005c675  mov     r14, rdx
0x18005c678  mov     [rsp+1F0h+var_190], rdx
0x18005c67d  mov     r13, rcx
0x18005c680  mov     [rsp+1F0h+var_180], rcx
0x18005c685  xor     edx, edx; Val
0x18005c687  mov     [rsp+1F0h+var_1A8], r9d
0x18005c68c  lea     r8d, [rdi+48h]; Size
0x18005c690  mov     [rsp+1F0h+var_1AC], r15d
0x18005c695  lea     rcx, [rbp+0F0h+var_170]; void *
0x18005c699  mov     [rsp+1F0h+var_1B8], rdi
0x18005c69e  mov     r12d, r9d
0x18005c6a1  mov     [rsp+1F0h+var_1A0], rdi
0x18005c6a6  call    memset_0
0x18005c6ab  mov     rcx, r13
0x18005c6ae  mov     [rsp+1F0h+var_194], edi
0x18005c6b2  mov     [rsp+1F0h+var_198], edi
0x18005c6b6  mov     [rsp+1F0h+var_1C0], edi
0x18005c6ba  call    cs:__imp_pldcGet
0x18005c6c1  nop     dword ptr [rax+rax+00h]
0x18005c6c6  mov     rbx, rax
0x18005c6c9  test    rax, rax
0x18005c6cc  jz      loc_18005C9CF
0x18005c6d2  btr     dword ptr [rax+8], 0Fh
0x18005c6d7  lea     r9, [rsp+1F0h+var_194]
0x18005c6dc  lea     rax, [rsp+1F0h+var_1C0]
0x18005c6e1  mov     rcx, r13
0x18005c6e4  mov     [rsp+1F0h+var_1C8], rax
0x18005c6e9  lea     r8, [rbp+0F0h+var_170]
0x18005c6ed  lea     rax, [rsp+1F0h+var_198]
0x18005c6f2  lea     rdx, [rsp+1F0h+var_1B8]
0x18005c6f7  mov     [rsp+1F0h+var_1D0], rax
0x18005c6fc  call    cs:__imp_NtGdiGetUFI
0x18005c703  nop     dword ptr [rax+rax+00h]
0x18005c708  test    eax, eax
0x18005c70a  jz      loc_18005C9CF
0x18005c710  test    dword ptr [rbx+8], 400000h
0x18005c717  lea     esi, [rdi+1]
0x18005c71a  jz      short loc_18005C783
0x18005c71c  mov     rax, [rsp+1F0h+var_1B8]
0x18005c721  cmp     [rbx+78h], eax
0x18005c724  jz      loc_18005C9EE
0x18005c72a  lea     rdx, [rsp+1F0h+var_1B8]
0x18005c72f  mov     rcx, r13
0x18005c732  call    MF_ForceUFIMapping
0x18005c737  test    eax, eax
0x18005c739  jz      loc_18005C9CF
0x18005c73f  mov     rax, [rsp+1F0h+var_1B8]
0x18005c744  mov     [rbx+78h], rax
0x18005c748  jmp     short loc_18005C74F
0x18005c74a  cmp     [rbx+7Ch], ecx
0x18005c74d  jnz     short loc_18005C72A
0x18005c74f  call    cs:__imp_NtGdiAnyLinkedFonts
0x18005c756  nop     dword ptr [rax+rax+00h]
0x18005c75b  test    eax, eax
0x18005c75d  jz      short loc_18005C783
0x18005c75f  xor     r8d, r8d
0x18005c762  xor     edx, edx
0x18005c764  mov     rcx, r13
0x18005c767  call    cs:__imp_NtGdiGetLinkedUFIs
0x18005c76e  nop     dword ptr [rax+rax+00h]
0x18005c773  movsxd  r14, eax
0x18005c776  test    eax, eax
0x18005c778  jg      loc_18005C9D6
0x18005c77e  mov     r14, [rsp+1F0h+var_190]
0x18005c783  mov     rax, [rsp+1F0h+var_1B8]
0x18005c788  test    eax, eax
0x18005c78a  jz      loc_18005C822
0x18005c790  test    dword ptr [rbx+8], 100000h
0x18005c797  jz      loc_18005C822
0x18005c79d  mov     r10d, [rsp+1F0h+var_1C0]
0x18005c7a2  mov     edx, eax
0x18005c7a4  mov     [rsp+1F0h+var_1A0], rax
0x18005c7a9  mov     r8d, r10d
0x18005c7ac  mov     r9d, dword ptr [rsp+1F0h+var_1A0+4]
0x18005c7b1  and     r8d, 2
0x18005c7b5  cmovnz  edx, [rsp+1F0h+var_198]
0x18005c7ba  cmp     edx, esi
0x18005c7bc  mov     dword ptr [rsp+1F0h+var_1A0], edx
0x18005c7c0  mov     r11, [rbx+58h]
0x18005c7c4  mov     eax, edx
0x18005c7c6  cmovz   eax, r9d
0x18005c7ca  and     eax, 1Fh
0x18005c7cd  mov     rcx, [r11+rax*8]
0x18005c7d1  test    rcx, rcx
0x18005c7d4  jz      loc_18005CA46
0x18005c7da  cmp     [rcx], esi
0x18005c7dc  jz      loc_18005CA35
0x18005c7e2  cmp     [rcx], edx
0x18005c7e4  jz      short loc_18005C7EC
0x18005c7e6  mov     rcx, [rcx+8]
0x18005c7ea  jmp     short loc_18005C7D1
0x18005c7ec  test    rcx, rcx
0x18005c7ef  jz      loc_18005CA46
0x18005c7f5  mov     eax, edi
0x18005c7f7  mov     rcx, [rbp+0F0h+var_40]
0x18005c7fe  xor     rcx, rsp; StackCookie
0x18005c801  call    __security_check_cookie
0x18005c806  mov     rbx, [rsp+1F0h+arg_18]
0x18005c80e  add     rsp, 1C0h
0x18005c815  pop     r15
0x18005c817  pop     r14
0x18005c819  pop     r13
0x18005c81b  pop     r12
0x18005c81d  pop     rdi
0x18005c81e  pop     rsi
0x18005c81f  pop     rbp
0x18005c820  retn
0x18005c822  mov     eax, esi
0x18005c824  jmp     short loc_18005C7F7
0x18005c826  lea     r14, [rbp+0F0h+hMem]
0x18005c82a  mov     r15, r14
0x18005c82d  mov     r8d, [rsp+1F0h+var_1AC]
0x18005c832  mov     r9, r14
0x18005c835  mov     rdx, [rsp+1F0h+var_190]
0x18005c83a  mov     rcx, r13
0x18005c83d  mov     dword ptr [rsp+1F0h+var_1D0], esi
0x18005c841  call    cs:__imp_NtGdiGetGlyphIndicesW
0x18005c848  nop     dword ptr [rax+rax+00h]
0x18005c84d  cmp     eax, 0FFFFFFFFh
0x18005c850  jz      loc_18005C955
0x18005c856  xor     ecx, ecx
0x18005c858  cmp     ecx, [rsp+1F0h+var_1AC]
0x18005c85c  jge     short loc_18005C87A
0x18005c85e  movsxd  rax, ecx
0x18005c861  mov     edx, 0FFFFh
0x18005c866  cmp     [r15+rax*2], dx
0x18005c86b  jz      loc_18005C955
0x18005c871  add     ecx, esi
0x18005c873  jmp     short loc_18005C858
0x18005c875  test    r14, r14
0x18005c878  jz      short loc_18005C887
0x18005c87a  lea     rax, [rbp+0F0h+hMem]
0x18005c87e  cmp     r14, rax
0x18005c881  jnz     loc_18005CA0D
0x18005c887  test    edi, edi
0x18005c889  jz      short loc_18005C8DB
0x18005c88b  mov     eax, [rsp+1F0h+var_1B0]
0x18005c88f  mov     r8d, eax
0x18005c892  mov     rdx, r12
0x18005c895  mov     rcx, r13
0x18005c898  call    MF_SetLinkedUFIs
0x18005c89d  mov     edi, eax
0x18005c89f  jmp     short loc_18005C8DB
0x18005c8a1  mov     rdx, r14
0x18005c8a4  xor     ecx, ecx; uFlags
0x18005c8a6  shl     rdx, 3; uBytes
0x18005c8aa  call    cs:__imp_LocalAlloc
0x18005c8b1  nop     dword ptr [rax+rax+00h]
0x18005c8b6  mov     r12, rax
0x18005c8b9  test    rax, rax
0x18005c8bc  jz      short loc_18005C8F5
0x18005c8be  mov     r8d, r14d
0x18005c8c1  mov     rdx, r12
0x18005c8c4  mov     rcx, r13
0x18005c8c7  call    cs:__imp_NtGdiGetLinkedUFIs
0x18005c8ce  nop     dword ptr [rax+rax+00h]
0x18005c8d3  mov     [rsp+1F0h+var_1B0], eax
0x18005c8d7  test    eax, eax
0x18005c8d9  jnz     short loc_18005C8FF
0x18005c8db  lea     rax, [rbp+0F0h+var_120]
0x18005c8df  cmp     r12, rax
0x18005c8e2  jnz     loc_18005CA21
0x18005c8e8  test    edi, edi
0x18005c8ea  jz      loc_18005C9CF
0x18005c8f0  mov     r15d, [rsp+1F0h+var_1AC]
0x18005c8f5  mov     r12d, [rsp+1F0h+var_1A8]
0x18005c8fa  jmp     loc_18005C77E
0x18005c8ff  test    dword ptr [rbx+8], 100000h
0x18005c906  jz      short loc_18005C88F
0x18005c908  test    r15d, r15d
0x18005c90b  jz      short loc_18005C88F
0x18005c90d  cmp     [rsp+1F0h+var_190], rdi
0x18005c912  jz      loc_18005C88F
0x18005c918  test    byte ptr [rsp+1F0h+var_1A8], 10h
0x18005c91d  jnz     loc_18005C88F
0x18005c923  mov     edi, esi
0x18005c925  cmp     r15d, 50h ; 'P'
0x18005c929  jle     loc_18005C826
0x18005c92f  mov     rdx, r15
0x18005c932  mov     ecx, 40h ; '@'; uFlags
0x18005c937  add     rdx, rdx; uBytes
0x18005c93a  call    cs:__imp_LocalAlloc
0x18005c941  nop     dword ptr [rax+rax+00h]
0x18005c946  mov     r15, rax
0x18005c949  mov     r14, rax
0x18005c94c  test    rax, rax
0x18005c94f  jnz     loc_18005C82D
0x18005c955  xor     r15d, r15d
0x18005c958  cmp     [rsp+1F0h+var_1B0], r15d
0x18005c95d  jle     short loc_18005C9C5
0x18005c95f  mov     r13d, [rsp+1F0h+var_1B0]
0x18005c964  mov     rcx, [rbx+58h]
0x18005c968  lea     r10, [r12+r15*8]
0x18005c96c  mov     rdx, r10
0x18005c96f  mov     [rsp+1F0h+var_188], r10
0x18005c974  xor     r8d, r8d
0x18005c977  call    pufihFindUFIEntry
0x18005c97c  test    rax, rax
0x18005c97f  jnz     short loc_18005C9B0
0x18005c981  mov     rcx, [rbx+58h]
0x18005c985  xor     r9d, r9d
0x18005c988  mov     rdx, r10
0x18005c98b  mov     dword ptr [rsp+1F0h+var_1D0], r8d
0x18005c990  call    pufihAddUFIEntry
0x18005c995  test    rax, rax
0x18005c998  jz      short loc_18005C9AE
0x18005c99a  mov     rdx, [rsp+1F0h+var_188]
0x18005c99f  xor     r8d, r8d
0x18005c9a2  mov     rcx, rbx
0x18005c9a5  call    WriteFontToSpoolFile
0x18005c9aa  test    eax, eax
0x18005c9ac  jnz     short loc_18005C9B0
0x18005c9ae  xor     edi, edi
0x18005c9b0  add     r15d, esi
0x18005c9b3  cmp     r15d, r13d
0x18005c9b6  jl      short loc_18005C964
0x18005c9b8  mov     r13, [rsp+1F0h+var_180]
0x18005c9bd  test    edi, edi
0x18005c9bf  jz      loc_18005C875
0x18005c9c5  btr     dword ptr [rbx+8], 17h
0x18005c9ca  jmp     loc_18005C875
0x18005c9cf  xor     eax, eax
0x18005c9d1  jmp     loc_18005C7F7
0x18005c9d6  bts     dword ptr [rbx+8], 17h
0x18005c9db  cmp     r14d, 8
0x18005c9df  jg      loc_18005C8A1
0x18005c9e5  lea     r12, [rbp+0F0h+var_120]
0x18005c9e9  jmp     loc_18005C8BE
0x18005c9ee  mov     ecx, dword ptr [rsp+1F0h+var_1B8+4]
0x18005c9f2  cmp     [rbx+7Ch], ecx
0x18005c9f5  jnz     loc_18005C72A
0x18005c9fb  test    dword ptr [rbx+8], 800000h
0x18005ca02  jz      loc_18005C788
0x18005ca08  jmp     loc_18005C74A
0x18005ca0d  mov     rcx, r14; hMem
0x18005ca10  call    cs:__imp_LocalFree
0x18005ca17  nop     dword ptr [rax+rax+00h]
0x18005ca1c  jmp     loc_18005C887
0x18005ca21  mov     rcx, r12; hMem
0x18005ca24  call    cs:__imp_LocalFree
0x18005ca2b  nop     dword ptr [rax+rax+00h]
0x18005ca30  jmp     loc_18005C8E8
0x18005ca35  cmp     edx, esi
0x18005ca37  jnz     loc_18005C7E6
0x18005ca3d  cmp     [rcx+4], r9d
0x18005ca41  jmp     loc_18005C7E4
0x18005ca46  test    r8d, r8d
0x18005ca49  jz      loc_18005CAD1
0x18005ca4f  xor     r9d, r9d
0x18005ca52  mov     dword ptr [rsp+1F0h+var_1D0], r10d
0x18005ca57  xor     r8d, r8d
0x18005ca5a  lea     rdx, [rsp+1F0h+var_1A0]
0x18005ca5f  mov     rcx, r11
0x18005ca62  call    pufihAddUFIEntry
0x18005ca67  mov     r8d, [rsp+1F0h+var_1C0]
0x18005ca6c  lea     rdx, [rsp+1F0h+var_1A0]
0x18005ca71  mov     rcx, rbx
0x18005ca74  call    WriteFontToSpoolFile
0x18005ca79  mov     edi, eax
0x18005ca7b  test    eax, eax
0x18005ca7d  jz      loc_18005C7F5
0x18005ca83  mov     rcx, [rbx+60h]
0x18005ca87  lea     rdx, [rsp+1F0h+var_1B8]
0x18005ca8c  xor     r8d, r8d
0x18005ca8f  call    pufihFindUFIEntry
0x18005ca94  test    rax, rax
0x18005ca97  jnz     loc_18005C7F5
0x18005ca9d  mov     eax, [rsp+1F0h+var_1C0]
0x18005caa1  lea     rdx, [rsp+1F0h+var_1B8]
0x18005caa6  mov     rcx, [rbx+60h]
0x18005caaa  xor     r9d, r9d
0x18005caad  mov     dword ptr [rsp+1F0h+var_1D0], eax
0x18005cab1  call    pufihAddUFIEntry
0x18005cab6  mov     r9d, [rsp+1F0h+var_194]
0x18005cabb  lea     r8, [rbp+0F0h+var_170]
0x18005cabf  lea     rdx, [rsp+1F0h+var_1A0]
0x18005cac4  mov     rcx, rbx
0x18005cac7  call    WriteDesignVectorToSpoolFile
0x18005cacc  jmp     loc_18005CB9A
0x18005cad1  mov     rcx, [rbx+68h]
0x18005cad5  lea     rdx, [rsp+1F0h+var_1B8]
0x18005cada  mov     r8d, esi
0x18005cadd  call    pufihFindUFIEntry
0x18005cae2  mov     rcx, r13
0x18005cae5  test    rax, rax
  ... truncated ...
```
