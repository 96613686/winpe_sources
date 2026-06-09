# PrepareCombiLUTs

- ea: `0x1800023c8`
- end: `0x18000299c`
- name: `PrepareCombiLUTs`
- size: `1492`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180005974`

## callees

- `0x18000190c`
- `0x180001c0c`
- `0x1800023c8`
- `0x1800029a4`
- `0x1800042e0`
- `0x18003d00e`
- `0x18003d040`

## import_xrefs

- `mscms!GetColorProfileHeader` at `0x180002444`
- `mscms!GetColorProfileHeader` at `0x180002471`
- `mscms!GetColorProfileHeader` at `0x180002444`
- `mscms!GetColorProfileHeader` at `0x180002471`

## pseudocode

```c
__int64 __fastcall PrepareCombiLUTs(__int64 a1, __int64 a2)
{
  __int64 v4; // rdi
  BOOL ColorProfileHeader; // eax
  BOOL v6; // eax
  DWORD phClass; // ecx
  DWORD phDataColorSpace; // edx
  DWORD phConnectionSpace; // eax
  char v10; // al
  char v11; // si
  int v12; // eax
  unsigned int v13; // edi
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // rdx
  int v17; // r9d
  __int64 v18; // r8
  __int64 v19; // rax
  int v20; // ecx
  int v21; // eax
  __int64 v22; // rdx
  int v23; // ecx
  int v24; // eax
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v34; // [rsp+30h] [rbp-D0h] BYREF
  int v35; // [rsp+40h] [rbp-C0h] BYREF
  int v36; // [rsp+44h] [rbp-BCh]
  int v37; // [rsp+48h] [rbp-B8h]
  __int64 v38; // [rsp+50h] [rbp-B0h]
  __int64 v39; // [rsp+58h] [rbp-A8h]
  int v40; // [rsp+60h] [rbp-A0h]
  int v41; // [rsp+64h] [rbp-9Ch]
  __int64 v42; // [rsp+68h] [rbp-98h]
  int v43; // [rsp+70h] [rbp-90h]
  int v44; // [rsp+74h] [rbp-8Ch]
  int v45; // [rsp+78h] [rbp-88h]
  int v46; // [rsp+7Ch] [rbp-84h]
  __int64 v47; // [rsp+80h] [rbp-80h]
  __int64 v48; // [rsp+98h] [rbp-68h]
  __int128 v49; // [rsp+A0h] [rbp-60h]
  int v50; // [rsp+B0h] [rbp-50h]
  int v51; // [rsp+B4h] [rbp-4Ch]
  __int64 v52; // [rsp+B8h] [rbp-48h]
  PROFILEHEADER v53; // [rsp+D0h] [rbp-30h] BYREF
  PROFILEHEADER pHeader; // [rsp+150h] [rbp+50h] BYREF

  memset_0(&pHeader, 0, sizeof(pHeader));
  memset_0(&v53, 0, sizeof(v53));
  v34 = 0;
  memset_0(&v35, 0, 0x90u);
  v4 = *(unsigned __int16 *)(a2 + 2);
  ColorProfileHeader = GetColorProfileHeader(*(HPROFILE *)(a2 + 8), &pHeader);
  if ( pHeader.phSignature == 1633907568
    && ColorProfileHeader
    && (*(_DWORD *)(a1 + 292) = pHeader.phDataColorSpace,
        v6 = GetColorProfileHeader(*(HPROFILE *)(a2 + 8 * v4), &v53),
        v53.phSignature == 1633907568)
    && v6 )
  {
    phClass = v53.phClass;
    phDataColorSpace = v53.phDataColorSpace;
    phConnectionSpace = v53.phDataColorSpace;
    if ( v53.phClass == 1818848875 )
      phConnectionSpace = v53.phConnectionSpace;
    *(_DWORD *)(a1 + 296) = phConnectionSpace;
    if ( (unsigned __int16)v4 > 1u && phClass == 1818848875 )
    {
      *(_BYTE *)(a1 + 368) = 1;
      *(_DWORD *)(a1 + 372) = phDataColorSpace;
      --*(_WORD *)(a2 + 2);
      v10 = 0;
    }
    else
    {
      *(_BYTE *)(a1 + 368) = 0;
      if ( phClass == 1886549106 || (v10 = 0, phClass == 1835955314) )
        v10 = 1;
    }
    v11 = 0;
    if ( (pHeader.phProfileFlags & 0x80000) == 0 )
      v11 = v10;
    v12 = *(_DWORD *)(a1 + 364);
    if ( v12 != -1 )
    {
      if ( (v12 & 0x80000) != 0 )
      {
        v11 = 0;
      }
      else if ( phClass == 1886549106 || phClass == 1835955314 )
      {
        v11 = 1;
      }
    }
    v13 = Create_LH_ProfileSet(a1, a2, &v34, 1886549106);
    if ( !v13 )
    {
      if ( ((*(_DWORD *)(a1 + 328) - 1) & 0xFFFFFFFD) != 0 && v11 )
      {
        if ( v53.phConnectionSpace != 1482250784 && v53.phClass == 1835955314 && v53.phDataColorSpace == 1380401696 )
        {
          v14 = v34;
          v15 = 3LL * *(unsigned __int16 *)(v34 + 2);
          *(_OWORD *)(v34 + 8 * v15 + 8) = *(_OWORD *)(v34 + 24LL * *(unsigned __int16 *)(v34 + 2) - 16);
          *(_QWORD *)(v14 + 8 * v15 + 24) = *(_QWORD *)(v14 + 8 * v15);
          *(_WORD *)(v34 + 24LL * *(unsigned __int16 *)(v34 + 2) - 8) = 2;
          *(_QWORD *)(v34 + 24LL * *(unsigned __int16 *)(v34 + 2) - 16) = 0;
          *(_DWORD *)(v34 + 24LL * (unsigned __int16)(*(_WORD *)(v34 + 2))++ - 4) = 0;
        }
        v17 = CreateCombi(a1, a2, v34, &v35, 1);
        if ( v53.phConnectionSpace != 1482250784 && v53.phClass == 1835955314 && v53.phDataColorSpace == 1380401696 )
        {
          --*(_WORD *)(v34 + 2);
          v18 = v34;
          v19 = *(unsigned __int16 *)(v34 + 2);
          v16 = 3 * v19;
          *(_OWORD *)(v34 + 8 * v16 - 16) = *(_OWORD *)(v34 + 24 * v19 + 8);
          *(_QWORD *)(v18 + 8 * v16) = *(_QWORD *)(v18 + 24 * v19 + 24);
        }
        if ( v17 || (unsigned int)FillDescaledInputLut(&v35, v16) )
        {
          v38 = DisposeIfPtr(v38);
          v39 = DisposeIfPtr(v39);
          v42 = DisposeIfPtr(v42);
          v47 = DisposeIfPtr(v47);
          v48 = DisposeIfPtr(v48);
          v52 = DisposeIfPtr(v52);
        }
        else
        {
          if ( v38 )
          {
            *(_QWORD *)(a1 + 160) = v38;
            v38 = 0;
          }
          if ( v39 )
          {
            *(_QWORD *)(a1 + 168) = v39;
            v39 = 0;
          }
          if ( v42 )
          {
            *(_QWORD *)(a1 + 184) = v42;
            v42 = 0;
          }
          if ( v47 )
          {
            *(_QWORD *)(a1 + 208) = v47;
            v47 = 0;
          }
          v20 = v35;
          *(_DWORD *)(a1 + 192) = v43;
          *(_DWORD *)(a1 + 196) = v44;
          *(_DWORD *)(a1 + 200) = v45;
          *(_DWORD *)(a1 + 204) = v46;
          *(_DWORD *)(a1 + 152) = v37;
          *(_DWORD *)(a1 + 180) = v41;
          *(_DWORD *)(a1 + 148) = v36;
          *(_DWORD *)(a1 + 176) = v40;
          *(_DWORD *)(a1 + 144) = v20;
          if ( (unsigned int)(v20 - 3) <= 1 )
          {
            v21 = v50;
            *(_OWORD *)(a1 + 240) = v49;
            *(_DWORD *)(a1 + 256) = v21;
            *(_DWORD *)(a1 + 260) = v51;
            *(_QWORD *)(a1 + 232) = v48;
            *(_QWORD *)(a1 + 264) = v52;
            v48 = 0;
            v52 = 0;
          }
        }
      }
      v13 = CreateCombi(a1, a2, v34, &v35, 0);
      if ( v13 || (v13 = FillDescaledInputLut(&v35, v22)) != 0 )
      {
        v25 = DisposeIfPtr(*(_QWORD *)(a1 + 344));
        v26 = *(_QWORD *)(a1 + 160);
        *(_QWORD *)(a1 + 344) = v25;
        v27 = DisposeIfPtr(v26);
        v28 = *(_QWORD *)(a1 + 168);
        *(_QWORD *)(a1 + 160) = v27;
        v29 = DisposeIfPtr(v28);
        v30 = *(_QWORD *)(a1 + 184);
        *(_QWORD *)(a1 + 168) = v29;
        v31 = DisposeIfPtr(v30);
        v32 = *(_QWORD *)(a1 + 208);
        *(_QWORD *)(a1 + 184) = v31;
        *(_QWORD *)(a1 + 208) = DisposeIfPtr(v32);
      }
      else
      {
        if ( v38 )
        {
          *(_QWORD *)(a1 + 16) = v38;
          v38 = 0;
        }
        if ( v39 )
        {
          *(_QWORD *)(a1 + 24) = v39;
          v39 = 0;
        }
        if ( v42 )
        {
          *(_QWORD *)(a1 + 40) = v42;
          v42 = 0;
        }
        if ( v47 )
        {
          *(_QWORD *)(a1 + 64) = v47;
          v47 = 0;
        }
        v23 = v35;
        *(_DWORD *)(a1 + 48) = v43;
        *(_DWORD *)(a1 + 52) = v44;
        *(_DWORD *)(a1 + 56) = v45;
        *(_DWORD *)(a1 + 60) = v46;
        *(_DWORD *)(a1 + 8) = v37;
        *(_DWORD *)(a1 + 36) = v41;
        *(_DWORD *)(a1 + 4) = v36;
        *(_DWORD *)(a1 + 32) = v40;
        *(_DWORD *)a1 = v23;
        if ( (unsigned int)(v23 - 3) <= 1 )
        {
          v24 = v50;
          *(_OWORD *)(a1 + 96) = v49;
          *(_DWORD *)(a1 + 112) = v24;
          *(_DWORD *)(a1 + 116) = v51;
          *(_QWORD *)(a1 + 88) = v48;
          *(_QWORD *)(a1 + 120) = v52;
          v48 = 0;
          v52 = 0;
        }
      }
    }
  }
  else
  {
    v13 = 2011;
  }
  v34 = DisposeIfPtr(v34);
  v38 = DisposeIfPtr(v38);
  v39 = DisposeIfPtr(v39);
  v42 = DisposeIfPtr(v42);
  v47 = DisposeIfPtr(v47);
  v48 = DisposeIfPtr(v48);
  DisposeIfPtr(v52);
  return v13;
}

```

## disassembly

```asm
0x1800023c8  mov     [rsp-8+arg_10], rbx
0x1800023cd  push    rbp
0x1800023ce  push    rsi
0x1800023cf  push    rdi
0x1800023d0  push    r12
0x1800023d2  push    r13
0x1800023d4  push    r14
0x1800023d6  push    r15
0x1800023d8  lea     rbp, [rsp-0E0h]
0x1800023e0  sub     rsp, 1E0h
0x1800023e7  mov     rax, cs:__security_cookie
0x1800023ee  xor     rax, rsp
0x1800023f1  mov     [rbp+110h+var_40], rax
0x1800023f8  mov     r14, rdx
0x1800023fb  mov     rbx, rcx
0x1800023fe  mov     edi, 80h
0x180002403  lea     rcx, [rbp+110h+pHeader]; void *
0x180002407  mov     r8d, edi; Size
0x18000240a  xor     edx, edx; Val
0x18000240c  call    memset_0
0x180002411  mov     r8d, edi; Size
0x180002414  lea     rcx, [rbp+110h+var_140]; void *
0x180002418  xor     edx, edx; Val
0x18000241a  call    memset_0
0x18000241f  xor     r15d, r15d
0x180002422  lea     r8d, [rdi+10h]; Size
0x180002426  xor     edx, edx; Val
0x180002428  mov     [rsp+210h+var_1E0], r15
0x18000242d  lea     rcx, [rsp+210h+var_1D0]; void *
0x180002432  call    memset_0
0x180002437  mov     rcx, [r14+8]; hProfile
0x18000243b  lea     rdx, [rbp+110h+pHeader]; pHeader
0x18000243f  movzx   edi, word ptr [r14+2]
0x180002444  call    cs:__imp_GetColorProfileHeader
0x18000244a  mov     esi, 61637370h
0x18000244f  cmp     [rbp+110h+pHeader.phSignature], esi
0x180002452  jnz     loc_18000290C
0x180002458  test    eax, eax
0x18000245a  jz      loc_18000290C
0x180002460  mov     eax, [rbp+110h+pHeader.phDataColorSpace]
0x180002463  lea     rdx, [rbp+110h+var_140]; pHeader
0x180002467  mov     [rbx+124h], eax
0x18000246d  mov     rcx, [r14+rdi*8]; hProfile
0x180002471  call    cs:__imp_GetColorProfileHeader
0x180002477  cmp     [rbp+110h+var_140.phSignature], esi
0x18000247a  jnz     loc_18000290C
0x180002480  test    eax, eax
0x180002482  jz      loc_18000290C
0x180002488  mov     ecx, [rbp+110h+var_140.phClass]
0x18000248b  lea     r12d, [r15+1]
0x18000248f  mov     edx, [rbp+110h+var_140.phDataColorSpace]
0x180002492  mov     r8d, 6C696E6Bh
0x180002498  cmp     ecx, r8d
0x18000249b  mov     eax, edx
0x18000249d  mov     r9d, 70727472h
0x1800024a3  mov     r13d, 6D6E7472h
0x1800024a9  cmovz   eax, [rbp+110h+var_140.phConnectionSpace]
0x1800024ad  mov     [rbx+128h], eax
0x1800024b3  mov     eax, 0FFFFh
0x1800024b8  cmp     di, r12w
0x1800024bc  jbe     short loc_1800024DA
0x1800024be  cmp     ecx, r8d
0x1800024c1  jnz     short loc_1800024DA
0x1800024c3  mov     [rbx+170h], r12b
0x1800024ca  mov     [rbx+174h], edx
0x1800024d0  add     [r14+2], ax
0x1800024d5  mov     al, r15b
0x1800024d8  jmp     short loc_1800024F1
0x1800024da  mov     [rbx+170h], r15b
0x1800024e1  cmp     ecx, r9d
0x1800024e4  jz      short loc_1800024EE
0x1800024e6  mov     al, r15b
0x1800024e9  cmp     ecx, r13d
0x1800024ec  jnz     short loc_1800024F1
0x1800024ee  mov     al, r12b
0x1800024f1  movzx   eax, al
0x1800024f4  mov     edx, 80000h
0x1800024f9  test    [rbp+110h+pHeader.phProfileFlags], edx
0x1800024fc  mov     esi, r15d
0x1800024ff  cmovz   esi, eax
0x180002502  mov     eax, [rbx+16Ch]
0x180002508  cmp     eax, 0FFFFFFFFh
0x18000250b  jz      short loc_180002523
0x18000250d  test    edx, eax
0x18000250f  jz      short loc_180002516
0x180002511  mov     sil, r15b
0x180002514  jmp     short loc_180002523
0x180002516  cmp     ecx, r9d
0x180002519  jz      short loc_180002520
0x18000251b  cmp     ecx, r13d
0x18000251e  jnz     short loc_180002523
0x180002520  mov     sil, r12b
0x180002523  lea     r8, [rsp+210h+var_1E0]
0x180002528  mov     rdx, r14
0x18000252b  mov     rcx, rbx
0x18000252e  call    Create_LH_ProfileSet
0x180002533  mov     edi, eax
0x180002535  test    eax, eax
0x180002537  jnz     loc_180002911
0x18000253d  mov     eax, [rbx+148h]
0x180002543  sub     eax, r12d
0x180002546  test    eax, 0FFFFFFFDh
0x18000254b  jz      loc_1800027B0
0x180002551  test    sil, sil
0x180002554  jz      loc_1800027B0
0x18000255a  mov     esi, 58595A20h
0x18000255f  mov     edi, 52474220h
0x180002564  cmp     [rbp+110h+var_140.phConnectionSpace], esi
0x180002567  jz      short loc_1800025E1
0x180002569  cmp     [rbp+110h+var_140.phClass], r13d
0x18000256d  jnz     short loc_1800025E1
0x18000256f  cmp     [rbp+110h+var_140.phDataColorSpace], edi
0x180002572  jnz     short loc_1800025E1
0x180002574  mov     r8, [rsp+210h+var_1E0]
0x180002579  movzx   eax, word ptr [r8+2]
0x18000257e  lea     rcx, [rax+rax*2]
0x180002582  movups  xmm0, xmmword ptr [r8+rcx*8-10h]
0x180002588  lea     rdx, [rax+rax*2]
0x18000258c  movups  xmmword ptr [r8+rdx*8+8], xmm0
0x180002592  movsd   xmm1, qword ptr [r8+rcx*8]
0x180002598  movsd   qword ptr [r8+rdx*8+18h], xmm1
0x18000259f  mov     rdx, [rsp+210h+var_1E0]
0x1800025a4  movzx   eax, word ptr [rdx+2]
0x1800025a8  lea     rcx, [rax+rax*2]
0x1800025ac  mov     word ptr [rdx+rcx*8-8], 2
0x1800025b3  mov     rdx, [rsp+210h+var_1E0]
0x1800025b8  movzx   eax, word ptr [rdx+2]
0x1800025bc  lea     rcx, [rax+rax*2]
0x1800025c0  mov     [rdx+rcx*8-10h], r15
0x1800025c5  mov     rdx, [rsp+210h+var_1E0]
0x1800025ca  movzx   eax, word ptr [rdx+2]
0x1800025ce  lea     rcx, [rax+rax*2]
0x1800025d2  mov     [rdx+rcx*8-4], r15d
0x1800025d7  mov     rax, [rsp+210h+var_1E0]
0x1800025dc  add     [rax+2], r12w
0x1800025e1  mov     r8, [rsp+210h+var_1E0]
0x1800025e6  lea     r9, [rsp+210h+var_1D0]
0x1800025eb  mov     rdx, r14
0x1800025ee  mov     [rsp+210h+var_1F0], r12b
0x1800025f3  mov     rcx, rbx
0x1800025f6  call    CreateCombi
0x1800025fb  mov     r9d, eax
0x1800025fe  cmp     [rbp+110h+var_140.phConnectionSpace], esi
0x180002601  jz      short loc_180002647
0x180002603  cmp     [rbp+110h+var_140.phClass], r13d
0x180002607  jnz     short loc_180002647
0x180002609  cmp     [rbp+110h+var_140.phDataColorSpace], edi
0x18000260c  jnz     short loc_180002647
0x18000260e  mov     rcx, [rsp+210h+var_1E0]
0x180002613  mov     eax, 0FFFFh
0x180002618  add     [rcx+2], ax
0x18000261c  mov     r8, [rsp+210h+var_1E0]
0x180002621  movzx   eax, word ptr [r8+2]
0x180002626  lea     rcx, [rax+rax*2]
0x18000262a  movups  xmm0, xmmword ptr [r8+rcx*8+8]
0x180002630  lea     rdx, [rax+rax*2]
0x180002634  movups  xmmword ptr [r8+rdx*8-10h], xmm0
0x18000263a  movsd   xmm1, qword ptr [r8+rcx*8+18h]
0x180002641  movsd   qword ptr [r8+rdx*8], xmm1
0x180002647  test    r9d, r9d
0x18000264a  jnz     loc_18000275C
0x180002650  lea     rcx, [rsp+210h+var_1D0]
0x180002655  call    FillDescaledInputLut
0x18000265a  test    eax, eax
0x18000265c  jnz     loc_18000275C
0x180002662  mov     rax, [rsp+210h+var_1C0]
0x180002667  test    rax, rax
0x18000266a  jz      short loc_180002678
0x18000266c  mov     [rbx+0A0h], rax
0x180002673  mov     [rsp+210h+var_1C0], r15
0x180002678  mov     rax, [rsp+210h+var_1B8]
0x18000267d  test    rax, rax
0x180002680  jz      short loc_18000268E
0x180002682  mov     [rbx+0A8h], rax
0x180002689  mov     [rsp+210h+var_1B8], r15
0x18000268e  mov     rax, [rsp+210h+var_1A8]
0x180002693  test    rax, rax
0x180002696  jz      short loc_1800026A4
0x180002698  mov     [rbx+0B8h], rax
0x18000269f  mov     [rsp+210h+var_1A8], r15
0x1800026a4  mov     rax, [rbp+110h+var_190]
0x1800026a8  test    rax, rax
0x1800026ab  jz      short loc_1800026B8
0x1800026ad  mov     [rbx+0D0h], rax
0x1800026b4  mov     [rbp+110h+var_190], r15
0x1800026b8  mov     eax, [rsp+210h+var_1A0]
0x1800026bc  mov     rcx, [rsp+210h+var_1D0]
0x1800026c1  mov     [rbx+0C0h], eax
0x1800026c7  mov     eax, [rsp+210h+var_19C]
0x1800026cb  mov     [rbx+0C4h], eax
0x1800026d1  mov     eax, [rsp+210h+var_198]
0x1800026d5  mov     [rbx+0C8h], eax
0x1800026db  mov     eax, [rsp+210h+var_194]
0x1800026df  mov     [rbx+0CCh], eax
0x1800026e5  mov     eax, [rsp+210h+var_1C8]
0x1800026e9  mov     [rbx+98h], eax
0x1800026ef  mov     eax, [rsp+210h+var_1AC]
0x1800026f3  mov     [rbx+0B4h], eax
0x1800026f9  mov     eax, dword ptr [rsp+210h+var_1D0+4]
0x1800026fd  mov     [rbx+94h], eax
0x180002703  mov     eax, [rsp+210h+var_1B0]
0x180002707  mov     [rbx+0B0h], eax
0x18000270d  lea     eax, [rcx-3]
0x180002710  mov     [rbx+90h], ecx
0x180002716  cmp     eax, r12d
0x180002719  ja      loc_1800027B0
0x18000271f  mov     eax, [rbp+110h+var_160]
0x180002722  movaps  xmm0, [rbp+110h+var_170]
0x180002726  movups  xmmword ptr [rbx+0F0h], xmm0
0x18000272d  mov     [rbx+100h], eax
0x180002733  mov     eax, [rbp+110h+var_15C]
0x180002736  mov     [rbx+104h], eax
0x18000273c  mov     rax, [rbp+110h+var_178]
0x180002740  mov     [rbx+0E8h], rax
0x180002747  mov     rax, [rbp+110h+var_158]
0x18000274b  mov     [rbx+108h], rax
0x180002752  mov     [rbp+110h+var_178], r15
0x180002756  mov     [rbp+110h+var_158], r15
0x18000275a  jmp     short loc_1800027B0
0x18000275c  mov     rcx, [rsp+210h+var_1C0]
0x180002761  call    DisposeIfPtr
0x180002766  mov     rcx, [rsp+210h+var_1B8]
0x18000276b  mov     [rsp+210h+var_1C0], rax
0x180002770  call    DisposeIfPtr
0x180002775  mov     rcx, [rsp+210h+var_1A8]
0x18000277a  mov     [rsp+210h+var_1B8], rax
0x18000277f  call    DisposeIfPtr
0x180002784  mov     rcx, [rbp+110h+var_190]
0x180002788  mov     [rsp+210h+var_1A8], rax
0x18000278d  call    DisposeIfPtr
0x180002792  mov     rcx, [rbp+110h+var_178]
0x180002796  mov     [rbp+110h+var_190], rax
0x18000279a  call    DisposeIfPtr
0x18000279f  mov     rcx, [rbp+110h+var_158]
0x1800027a3  mov     [rbp+110h+var_178], rax
0x1800027a7  call    DisposeIfPtr
0x1800027ac  mov     [rbp+110h+var_158], rax
0x1800027b0  mov     r8, [rsp+210h+var_1E0]
0x1800027b5  lea     r9, [rsp+210h+var_1D0]
0x1800027ba  mov     rdx, r14
0x1800027bd  mov     [rsp+210h+var_1F0], r15b
0x1800027c2  mov     rcx, rbx
0x1800027c5  call    CreateCombi
0x1800027ca  mov     edi, eax
0x1800027cc  test    eax, eax
0x1800027ce  jnz     loc_1800028AB
0x1800027d4  lea     rcx, [rsp+210h+var_1D0]
0x1800027d9  call    FillDescaledInputLut
0x1800027de  mov     edi, eax
0x1800027e0  test    eax, eax
0x1800027e2  jnz     loc_1800028AB
0x1800027e8  mov     rax, [rsp+210h+var_1C0]
0x1800027ed  test    rax, rax
0x1800027f0  jz      short loc_1800027FB
0x1800027f2  mov     [rbx+10h], rax
0x1800027f6  mov     [rsp+210h+var_1C0], r15
0x1800027fb  mov     rax, [rsp+210h+var_1B8]
0x180002800  test    rax, rax
0x180002803  jz      short loc_18000280E
0x180002805  mov     [rbx+18h], rax
0x180002809  mov     [rsp+210h+var_1B8], r15
0x18000280e  mov     rax, [rsp+210h+var_1A8]
0x180002813  test    rax, rax
0x180002816  jz      short loc_180002821
0x180002818  mov     [rbx+28h], rax
0x18000281c  mov     [rsp+210h+var_1A8], r15
0x180002821  mov     rax, [rbp+110h+var_190]
0x180002825  test    rax, rax
0x180002828  jz      short loc_180002832
0x18000282a  mov     [rbx+40h], rax
0x18000282e  mov     [rbp+110h+var_190], r15
0x180002832  mov     eax, [rsp+210h+var_1A0]
0x180002836  mov     rcx, [rsp+210h+var_1D0]
0x18000283b  mov     [rbx+30h], eax
0x18000283e  mov     eax, [rsp+210h+var_19C]
0x180002842  mov     [rbx+34h], eax
0x180002845  mov     eax, [rsp+210h+var_198]
0x180002849  mov     [rbx+38h], eax
0x18000284c  mov     eax, [rsp+210h+var_194]
0x180002850  mov     [rbx+3Ch], eax
0x180002853  mov     eax, [rsp+210h+var_1C8]
0x180002857  mov     [rbx+8], eax
0x18000285a  mov     eax, [rsp+210h+var_1AC]
0x18000285e  mov     [rbx+24h], eax
0x180002861  mov     eax, dword ptr [rsp+210h+var_1D0+4]
0x180002865  mov     [rbx+4], eax
0x180002868  mov     eax, [rsp+210h+var_1B0]
0x18000286c  mov     [rbx+20h], eax
0x18000286f  lea     eax, [rcx-3]
0x180002872  mov     [rbx], ecx
0x180002874  cmp     eax, r12d
0x180002877  ja      loc_180002911
0x18000287d  mov     eax, [rbp+110h+var_160]
0x180002880  movaps  xmm0, [rbp+110h+var_170]
0x180002884  movups  xmmword ptr [rbx+60h], xmm0
0x180002888  mov     [rbx+70h], eax
0x18000288b  mov     eax, [rbp+110h+var_15C]
0x18000288e  mov     [rbx+74h], eax
0x180002891  mov     rax, [rbp+110h+var_178]
0x180002895  mov     [rbx+58h], rax
  ... truncated ...
```
