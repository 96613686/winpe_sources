# bDoFontChange

- ea: `0x180057840`
- end: `0x180057d50`
- name: `bDoFontChange`
- size: `1296`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18003122c`

## callees

- `0x18004be38`
- `0x180057840`
- `0x180057d58`
- `0x18005d3a0`
- `0x180079648`
- `0x18007ac50`
- `0x18007ba24`
- `0x18007fc68`
- `0x18007fd0c`
- `0x180080088`
- `0x18008025c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180057a8b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180057b07`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180057a8b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180057b07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180057bd7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180057be5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180057bd7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180057be5`
- `GDI32!pldcGet` at `0x1800578ba`
- `GDI32!pldcGet` at `0x1800578ba`
- `win32u!NtGdiGetFontData` at `0x180057ccf`
- `win32u!NtGdiGetFontData` at `0x180057ccf`
- `win32u!NtGdiGetGlyphIndicesW` at `0x180057a28`
- `win32u!NtGdiGetGlyphIndicesW` at `0x180057cb1`
- `win32u!NtGdiGetGlyphIndicesW` at `0x180057a28`
- `win32u!NtGdiGetGlyphIndicesW` at `0x180057cb1`
- `win32u!NtGdiGetLinkedUFIs` at `0x180057955`
- `win32u!NtGdiGetLinkedUFIs` at `0x180057aa2`
- `win32u!NtGdiGetLinkedUFIs` at `0x180057955`
- `win32u!NtGdiGetLinkedUFIs` at `0x180057aa2`
- `win32u!NtGdiGetUFI` at `0x1800578f6`
- `win32u!NtGdiGetUFI` at `0x1800578f6`
- `win32u!NtGdiAnyLinkedFonts` at `0x180057943`
- `win32u!NtGdiAnyLinkedFonts` at `0x180057943`

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
0x180057840  mov     [rsp-8+arg_18], rbx
0x180057845  push    rbp
0x180057846  push    rsi
0x180057847  push    rdi
0x180057848  push    r12
0x18005784a  push    r13
0x18005784c  push    r14
0x18005784e  push    r15
0x180057850  lea     rbp, [rsp-0C0h]
0x180057858  sub     rsp, 1C0h
0x18005785f  mov     rax, cs:__security_cookie
0x180057866  xor     rax, rsp
0x180057869  mov     [rbp+0F0h+var_40], rax
0x180057870  xor     edi, edi
0x180057872  movsxd  r15, r8d
0x180057875  mov     r14, rdx
0x180057878  mov     [rsp+1F0h+var_190], rdx
0x18005787d  mov     r13, rcx
0x180057880  mov     [rsp+1F0h+var_180], rcx
0x180057885  xor     edx, edx; Val
0x180057887  mov     [rsp+1F0h+var_1A8], r9d
0x18005788c  lea     r8d, [rdi+48h]; Size
0x180057890  mov     [rsp+1F0h+var_1AC], r15d
0x180057895  lea     rcx, [rbp+0F0h+var_170]; void *
0x180057899  mov     [rsp+1F0h+var_1B8], rdi
0x18005789e  mov     r12d, r9d
0x1800578a1  mov     [rsp+1F0h+var_1A0], rdi
0x1800578a6  call    memset_0
0x1800578ab  mov     rcx, r13
0x1800578ae  mov     [rsp+1F0h+var_194], edi
0x1800578b2  mov     [rsp+1F0h+var_198], edi
0x1800578b6  mov     [rsp+1F0h+var_1C0], edi
0x1800578ba  call    cs:__imp_pldcGet
0x1800578c0  mov     rbx, rax
0x1800578c3  test    rax, rax
0x1800578c6  jz      loc_180057B96
0x1800578cc  btr     dword ptr [rax+8], 0Fh
0x1800578d1  lea     r9, [rsp+1F0h+var_194]
0x1800578d6  lea     rax, [rsp+1F0h+var_1C0]
0x1800578db  mov     rcx, r13
0x1800578de  mov     [rsp+1F0h+var_1C8], rax
0x1800578e3  lea     r8, [rbp+0F0h+var_170]
0x1800578e7  lea     rax, [rsp+1F0h+var_198]
0x1800578ec  lea     rdx, [rsp+1F0h+var_1B8]
0x1800578f1  mov     [rsp+1F0h+var_1D0], rax
0x1800578f6  call    cs:__imp_NtGdiGetUFI
0x1800578fc  test    eax, eax
0x1800578fe  jz      loc_180057B96
0x180057904  test    dword ptr [rbx+8], 400000h
0x18005790b  lea     esi, [rdi+1]
0x18005790e  jz      short loc_18005796B
0x180057910  mov     rax, [rsp+1F0h+var_1B8]
0x180057915  cmp     [rbx+78h], eax
0x180057918  jz      loc_180057BB5
0x18005791e  lea     rdx, [rsp+1F0h+var_1B8]
0x180057923  mov     rcx, r13
0x180057926  call    MF_ForceUFIMapping
0x18005792b  test    eax, eax
0x18005792d  jz      loc_180057B96
0x180057933  mov     rax, [rsp+1F0h+var_1B8]
0x180057938  mov     [rbx+78h], rax
0x18005793c  jmp     short loc_180057943
0x18005793e  cmp     [rbx+7Ch], ecx
0x180057941  jnz     short loc_18005791E
0x180057943  call    cs:__imp_NtGdiAnyLinkedFonts
0x180057949  test    eax, eax
0x18005794b  jz      short loc_18005796B
0x18005794d  xor     r8d, r8d
0x180057950  xor     edx, edx
0x180057952  mov     rcx, r13
0x180057955  call    cs:__imp_NtGdiGetLinkedUFIs
0x18005795b  movsxd  r14, eax
0x18005795e  test    eax, eax
0x180057960  jg      loc_180057B9D
0x180057966  mov     r14, [rsp+1F0h+var_190]
0x18005796b  mov     rax, [rsp+1F0h+var_1B8]
0x180057970  test    eax, eax
0x180057972  jz      loc_180057A09
0x180057978  test    dword ptr [rbx+8], 100000h
0x18005797f  jz      loc_180057A09
0x180057985  mov     r10d, [rsp+1F0h+var_1C0]
0x18005798a  mov     edx, eax
0x18005798c  mov     [rsp+1F0h+var_1A0], rax
0x180057991  mov     r8d, r10d
0x180057994  mov     r9d, dword ptr [rsp+1F0h+var_1A0+4]
0x180057999  and     r8d, 2
0x18005799d  cmovnz  edx, [rsp+1F0h+var_198]
0x1800579a2  cmp     edx, esi
0x1800579a4  mov     dword ptr [rsp+1F0h+var_1A0], edx
0x1800579a8  mov     r11, [rbx+58h]
0x1800579ac  mov     eax, edx
0x1800579ae  cmovz   eax, r9d
0x1800579b2  and     eax, 1Fh
0x1800579b5  mov     rcx, [r11+rax*8]
0x1800579b9  test    rcx, rcx
0x1800579bc  jz      loc_180057C01
0x1800579c2  cmp     [rcx], esi
0x1800579c4  jz      loc_180057BF0
0x1800579ca  cmp     [rcx], edx
0x1800579cc  jz      short loc_1800579D4
0x1800579ce  mov     rcx, [rcx+8]
0x1800579d2  jmp     short loc_1800579B9
0x1800579d4  test    rcx, rcx
0x1800579d7  jz      loc_180057C01
0x1800579dd  mov     eax, edi
0x1800579df  mov     rcx, [rbp+0F0h+var_40]
0x1800579e6  xor     rcx, rsp; StackCookie
0x1800579e9  call    __security_check_cookie
0x1800579ee  mov     rbx, [rsp+1F0h+arg_18]
0x1800579f6  add     rsp, 1C0h
0x1800579fd  pop     r15
0x1800579ff  pop     r14
0x180057a01  pop     r13
0x180057a03  pop     r12
0x180057a05  pop     rdi
0x180057a06  pop     rsi
0x180057a07  pop     rbp
0x180057a08  retn
0x180057a09  mov     eax, esi
0x180057a0b  jmp     short loc_1800579DF
0x180057a0d  lea     r14, [rbp+0F0h+hMem]
0x180057a11  mov     r15, r14
0x180057a14  mov     r8d, [rsp+1F0h+var_1AC]
0x180057a19  mov     r9, r14
0x180057a1c  mov     rdx, [rsp+1F0h+var_190]
0x180057a21  mov     rcx, r13
0x180057a24  mov     dword ptr [rsp+1F0h+var_1D0], esi
0x180057a28  call    cs:__imp_NtGdiGetGlyphIndicesW
0x180057a2e  cmp     eax, 0FFFFFFFFh
0x180057a31  jz      loc_180057B1C
0x180057a37  xor     ecx, ecx
0x180057a39  cmp     ecx, [rsp+1F0h+var_1AC]
0x180057a3d  jge     short loc_180057A5B
0x180057a3f  movsxd  rax, ecx
0x180057a42  mov     edx, 0FFFFh
0x180057a47  cmp     [r15+rax*2], dx
0x180057a4c  jz      loc_180057B1C
0x180057a52  add     ecx, esi
0x180057a54  jmp     short loc_180057A39
0x180057a56  test    r14, r14
0x180057a59  jz      short loc_180057A68
0x180057a5b  lea     rax, [rbp+0F0h+hMem]
0x180057a5f  cmp     r14, rax
0x180057a62  jnz     loc_180057BD4
0x180057a68  test    edi, edi
0x180057a6a  jz      short loc_180057AB0
0x180057a6c  mov     eax, [rsp+1F0h+var_1B0]
0x180057a70  mov     r8d, eax
0x180057a73  mov     rdx, r12
0x180057a76  mov     rcx, r13
0x180057a79  call    MF_SetLinkedUFIs
0x180057a7e  mov     edi, eax
0x180057a80  jmp     short loc_180057AB0
0x180057a82  mov     rdx, r14
0x180057a85  xor     ecx, ecx; uFlags
0x180057a87  shl     rdx, 3; uBytes
0x180057a8b  call    cs:__imp_LocalAlloc
0x180057a91  mov     r12, rax
0x180057a94  test    rax, rax
0x180057a97  jz      short loc_180057ACA
0x180057a99  mov     r8d, r14d
0x180057a9c  mov     rdx, r12
0x180057a9f  mov     rcx, r13
0x180057aa2  call    cs:__imp_NtGdiGetLinkedUFIs
0x180057aa8  mov     [rsp+1F0h+var_1B0], eax
0x180057aac  test    eax, eax
0x180057aae  jnz     short loc_180057AD4
0x180057ab0  lea     rax, [rbp+0F0h+var_120]
0x180057ab4  cmp     r12, rax
0x180057ab7  jnz     loc_180057BE2
0x180057abd  test    edi, edi
0x180057abf  jz      loc_180057B96
0x180057ac5  mov     r15d, [rsp+1F0h+var_1AC]
0x180057aca  mov     r12d, [rsp+1F0h+var_1A8]
0x180057acf  jmp     loc_180057966
0x180057ad4  test    dword ptr [rbx+8], 100000h
0x180057adb  jz      short loc_180057A70
0x180057add  test    r15d, r15d
0x180057ae0  jz      short loc_180057A70
0x180057ae2  cmp     [rsp+1F0h+var_190], rdi
0x180057ae7  jz      short loc_180057A70
0x180057ae9  test    byte ptr [rsp+1F0h+var_1A8], 10h
0x180057aee  jnz     short loc_180057A70
0x180057af0  mov     edi, esi
0x180057af2  cmp     r15d, 50h ; 'P'
0x180057af6  jle     loc_180057A0D
0x180057afc  mov     rdx, r15
0x180057aff  mov     ecx, 40h ; '@'; uFlags
0x180057b04  add     rdx, rdx; uBytes
0x180057b07  call    cs:__imp_LocalAlloc
0x180057b0d  mov     r15, rax
0x180057b10  mov     r14, rax
0x180057b13  test    rax, rax
0x180057b16  jnz     loc_180057A14
0x180057b1c  xor     r15d, r15d
0x180057b1f  cmp     [rsp+1F0h+var_1B0], r15d
0x180057b24  jle     short loc_180057B8C
0x180057b26  mov     r13d, [rsp+1F0h+var_1B0]
0x180057b2b  mov     rcx, [rbx+58h]
0x180057b2f  lea     r10, [r12+r15*8]
0x180057b33  mov     rdx, r10
0x180057b36  mov     [rsp+1F0h+var_188], r10
0x180057b3b  xor     r8d, r8d
0x180057b3e  call    pufihFindUFIEntry
0x180057b43  test    rax, rax
0x180057b46  jnz     short loc_180057B77
0x180057b48  mov     rcx, [rbx+58h]
0x180057b4c  xor     r9d, r9d
0x180057b4f  mov     rdx, r10
0x180057b52  mov     dword ptr [rsp+1F0h+var_1D0], r8d
0x180057b57  call    pufihAddUFIEntry
0x180057b5c  test    rax, rax
0x180057b5f  jz      short loc_180057B75
0x180057b61  mov     rdx, [rsp+1F0h+var_188]
0x180057b66  xor     r8d, r8d
0x180057b69  mov     rcx, rbx
0x180057b6c  call    WriteFontToSpoolFile
0x180057b71  test    eax, eax
0x180057b73  jnz     short loc_180057B77
0x180057b75  xor     edi, edi
0x180057b77  add     r15d, esi
0x180057b7a  cmp     r15d, r13d
0x180057b7d  jl      short loc_180057B2B
0x180057b7f  mov     r13, [rsp+1F0h+var_180]
0x180057b84  test    edi, edi
0x180057b86  jz      loc_180057A56
0x180057b8c  btr     dword ptr [rbx+8], 17h
0x180057b91  jmp     loc_180057A56
0x180057b96  xor     eax, eax
0x180057b98  jmp     loc_1800579DF
0x180057b9d  bts     dword ptr [rbx+8], 17h
0x180057ba2  cmp     r14d, 8
0x180057ba6  jg      loc_180057A82
0x180057bac  lea     r12, [rbp+0F0h+var_120]
0x180057bb0  jmp     loc_180057A99
0x180057bb5  mov     ecx, dword ptr [rsp+1F0h+var_1B8+4]
0x180057bb9  cmp     [rbx+7Ch], ecx
0x180057bbc  jnz     loc_18005791E
0x180057bc2  test    dword ptr [rbx+8], 800000h
0x180057bc9  jz      loc_180057970
0x180057bcf  jmp     loc_18005793E
0x180057bd4  mov     rcx, r14; hMem
0x180057bd7  call    cs:__imp_LocalFree
0x180057bdd  jmp     loc_180057A68
0x180057be2  mov     rcx, r12; hMem
0x180057be5  call    cs:__imp_LocalFree
0x180057beb  jmp     loc_180057ABD
0x180057bf0  cmp     edx, esi
0x180057bf2  jnz     loc_1800579CE
0x180057bf8  cmp     [rcx+4], r9d
0x180057bfc  jmp     loc_1800579CC
0x180057c01  test    r8d, r8d
0x180057c04  jz      loc_180057C8C
0x180057c0a  xor     r9d, r9d
0x180057c0d  mov     dword ptr [rsp+1F0h+var_1D0], r10d
0x180057c12  xor     r8d, r8d
0x180057c15  lea     rdx, [rsp+1F0h+var_1A0]
0x180057c1a  mov     rcx, r11
0x180057c1d  call    pufihAddUFIEntry
0x180057c22  mov     r8d, [rsp+1F0h+var_1C0]
0x180057c27  lea     rdx, [rsp+1F0h+var_1A0]
0x180057c2c  mov     rcx, rbx
0x180057c2f  call    WriteFontToSpoolFile
0x180057c34  mov     edi, eax
0x180057c36  test    eax, eax
0x180057c38  jz      loc_1800579DD
0x180057c3e  mov     rcx, [rbx+60h]
0x180057c42  lea     rdx, [rsp+1F0h+var_1B8]
0x180057c47  xor     r8d, r8d
0x180057c4a  call    pufihFindUFIEntry
0x180057c4f  test    rax, rax
0x180057c52  jnz     loc_1800579DD
0x180057c58  mov     eax, [rsp+1F0h+var_1C0]
0x180057c5c  lea     rdx, [rsp+1F0h+var_1B8]
0x180057c61  mov     rcx, [rbx+60h]
0x180057c65  xor     r9d, r9d
0x180057c68  mov     dword ptr [rsp+1F0h+var_1D0], eax
0x180057c6c  call    pufihAddUFIEntry
0x180057c71  mov     r9d, [rsp+1F0h+var_194]
0x180057c76  lea     r8, [rbp+0F0h+var_170]
0x180057c7a  lea     rdx, [rsp+1F0h+var_1A0]
0x180057c7f  mov     rcx, rbx
0x180057c82  call    WriteDesignVectorToSpoolFile
0x180057c87  jmp     loc_180057D49
0x180057c8c  mov     rcx, [rbx+68h]
0x180057c90  lea     rdx, [rsp+1F0h+var_1B8]
0x180057c95  mov     r8d, esi
0x180057c98  call    pufihFindUFIEntry
0x180057c9d  mov     rcx, r13
0x180057ca0  test    rax, rax
0x180057ca3  jnz     short loc_180057D0F
0x180057ca5  xor     r9d, r9d
0x180057ca8  mov     dword ptr [rsp+1F0h+var_1D0], eax
0x180057cac  xor     r8d, r8d
0x180057caf  xor     edx, edx
0x180057cb1  call    cs:__imp_NtGdiGetGlyphIndicesW
0x180057cb7  xor     r9d, r9d
0x180057cba  mov     dword ptr [rsp+1F0h+var_1D0], 0
0x180057cc2  xor     r8d, r8d
0x180057cc5  mov     edx, 66796C67h
  ... truncated ...
```
