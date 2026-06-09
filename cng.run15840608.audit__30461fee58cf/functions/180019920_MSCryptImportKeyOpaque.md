# MSCryptImportKeyOpaque

- ea: `0x180019920`
- end: `0x180019dc1`
- name: `MSCryptImportKeyOpaque`
- size: `1185`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, int, _DWORD *Src, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180017cf0`

## callees

- `0x180006410`
- `0x18000743c`
- `0x1800082b0`
- `0x180019920`
- `0x180019dd0`
- `0x1800947d0`
- `0x18009da40`
- `0x18009dd40`

## string_xrefs

- `0x180019b87`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\opaqueblob.c`
- `0x180019c38`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\opaqueblob.c`
- `0x180019c90`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\opaqueblob.c`
- `0x18009fc5a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\opaqueblob.c`
- `0x18009fc7d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\opaqueblob.c`

## pseudocode

```c
__int64 __fastcall MSCryptImportKeyOpaque(__int64 a1, _QWORD *a2, __int64 a3, int a4, _DWORD *Src, unsigned int a6)
{
  int v7; // r8d
  __int64 v8; // r13
  unsigned int v9; // ecx
  int v10; // esi
  unsigned int v11; // eax
  int v12; // r8d
  unsigned int v13; // ecx
  unsigned int v14; // r12d
  unsigned int v15; // r8d
  unsigned int v16; // ebx
  int v17; // eax
  _DWORD *v18; // rcx
  __int64 v19; // rsi
  int v20; // edx
  unsigned int SymmetricKey; // edi
  int v22; // r8d
  int v23; // eax
  __int64 v25; // r9
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // esi
  int v30; // r9d
  _BYTE *v31; // rbx
  __int64 v32; // r9
  size_t Size; // [rsp+28h] [rbp-D8h]
  bool v34; // [rsp+40h] [rbp-C0h]
  int v35[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v36; // [rsp+50h] [rbp-B0h]
  unsigned int v37; // [rsp+54h] [rbp-ACh]
  int v38[2]; // [rsp+58h] [rbp-A8h]
  _QWORD *v39; // [rsp+60h] [rbp-A0h]
  __int64 v40; // [rsp+70h] [rbp-90h] BYREF
  int v41; // [rsp+78h] [rbp-88h]
  unsigned int v42; // [rsp+7Ch] [rbp-84h]
  int v43; // [rsp+80h] [rbp-80h]
  int v44; // [rsp+84h] [rbp-7Ch]
  unsigned int v45; // [rsp+88h] [rbp-78h]
  _DWORD v46[135]; // [rsp+8Ch] [rbp-74h] BYREF

  *(_QWORD *)v38 = a3;
  v39 = a2;
  v36 = a4;
  memset(v46, 0, 0x214u);
  v8 = 0;
  *(_QWORD *)v35 = 0;
  if ( a6 < 0x1C )
  {
    SymmetricKey = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)WPP_GLOBAL_Control,
        v7,
        (unsigned int)"status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\opaqueblob.c",
        13);
  }
  else
  {
    v9 = Src[6];
    v40 = *(_QWORD *)Src;
    v41 = Src[2];
    v42 = Src[3];
    v10 = *(_DWORD *)(a1 + 8);
    v43 = Src[4];
    v44 = Src[5];
    v34 = 0;
    v45 = v9;
    if ( v10 != 65538 )
    {
      switch ( v10 )
      {
        case 65537:
          v11 = 552;
          if ( v9 <= 0x40 )
            v11 = 360;
          v34 = v9 > 0x40;
          goto LABEL_4;
        case 65539:
          v11 = 172;
          goto LABEL_4;
        case 65540:
          v11 = 204;
          goto LABEL_4;
        case 65541:
          v11 = 444;
          goto LABEL_4;
        case 65542:
          v11 = 436;
          goto LABEL_4;
        case 65543:
          v11 = 312;
          goto LABEL_4;
        case 65544:
          v11 = 92;
          goto LABEL_4;
        case 65545:
          v11 = 60;
          goto LABEL_4;
        default:
          return (unsigned int)-1073741595;
      }
    }
    v11 = 560;
LABEL_4:
    if ( a6 != v11 )
    {
      v25 = 299;
      goto LABEL_77;
    }
    memmove(&v40, Src, v11);
    if ( v40 == (a6 | 0x4D53534B00000000LL) && v41 == v10 )
    {
      v13 = *(_DWORD *)(a1 + 16);
      if ( v43 == v13 )
      {
        v14 = v42;
        v15 = HIBYTE(v42) + 1;
        v16 = v42 & 0xFFFFFF;
        v37 = v15;
        if ( v10 != 65544 )
        {
          if ( v16 < 6 )
          {
            if ( v16 == 3 )
            {
              if ( v15 <= v13 )
                goto LABEL_12;
            }
            else if ( !HIBYTE(v42) )
            {
LABEL_12:
              if ( !v16 || (v17 = qword_1800A5090[14 * (unsigned int)(unsigned __int16)v10 - 14], _bittest(&v17, v16)) )
              {
                if ( v10 == 65543 )
                {
                  SymmetricKey = 0;
                  v18 = &v46[1];
                  v29 = 6;
                  goto LABEL_73;
                }
LABEL_15:
                v18 = v46;
                if ( v10 == 65545 )
                {
LABEL_16:
                  v19 = *(_QWORD *)v38;
                  LODWORD(Size) = v45;
                  SymmetricKey = MSCryptGenerateSymmetricKey(a1, (int)v35, v38[0], v36, v18, Size, 128);
                  if ( (SymmetricKey & 0x80000000) != 0 )
                  {
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
                    {
                      WPP_SF_sDsd(
                        *((_QWORD *)WPP_GLOBAL_Control + 3),
                        v20,
                        v22,
                        (unsigned int)"status",
                        SymmetricKey,
                        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\opaqueblob.c",
                        123);
                    }
                    v8 = *(_QWORD *)v35;
                    goto LABEL_33;
                  }
                  v14 = v42;
                  v8 = *(_QWORD *)v35;
                  v15 = v37;
LABEL_18:
                  *(_DWORD *)(v19 + 12) = v16;
                  if ( v16 == 3 )
                    *(_DWORD *)(v19 + 20) = v15;
                  v23 = *(_DWORD *)(a1 + 8);
                  if ( v23 == 65543
                    || (v26 = v23 - 65538) == 0
                    || (v27 = v26 - 1) == 0
                    || (v28 = v27 - 1) == 0
                    || (unsigned int)(v28 - 1) <= 1 )
                  {
                    memmove(
                      (void *)(v19 + 40),
                      (char *)&v40 + a6 - (unsigned __int64)*(unsigned int *)(v19 + 16),
                      *(unsigned int *)(v19 + 16));
                  }
                  switch ( *(_DWORD *)(a1 + 8) )
                  {
                    case 0x10001:
                      v31 = &v46[17];
                      if ( v34 )
                        v31 = &v46[65];
                      memmove((void *)(v19 + 320), v31, 0x100u);
                      *(_BYTE *)(v19 + 576) = v31[256];
                      *(_BYTE *)(v19 + 577) = v31[257];
                      break;
                    case 0x10007:
                      v30 = v46[0];
                      if ( (unsigned int)(v46[0] - 16) > 0x3F0 || v46[0] != v44 )
                      {
                        v32 = 458;
LABEL_76:
                        SymmetricKey = -1073741811;
                        DebugTraceError(
                          3221225485LL,
                          "status",
                          "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\opaqueblob.c",
                          v32);
LABEL_33:
                        if ( v8 )
                          MSCryptDestroyKey(v8);
                        return SymmetricKey;
                      }
                      *(_DWORD *)(v19 + 336) = v46[0];
                      *(_DWORD *)(v19 + 24) = v30;
                      if ( (unsigned int)SymCryptRc2ExpandKeyEx((void *)(v19 + 192)) )
                      {
                        SymmetricKey = -1073741811;
                        goto LABEL_33;
                      }
                      break;
                    case 0x10008:
                      *(_DWORD *)(v19 + 12) = 0;
                      *(_DWORD *)(v19 + 20) = v14;
                      break;
                  }
                  if ( *(_DWORD *)(v19 + 24) == v44 )
                  {
                    *v39 = v8;
                    return SymmetricKey;
                  }
                  v32 = 487;
                  goto LABEL_76;
                }
                SymmetricKey = 0;
                v29 = v10 - 65537;
LABEL_73:
                switch ( v29 )
                {
                  case 0:
                  case 1:
                  case 2:
                  case 3:
                  case 4:
                  case 5:
                  case 6:
                  case 7:
                    goto LABEL_16;
                  default:
                    v19 = *(_QWORD *)v38;
                    goto LABEL_18;
                }
              }
            }
          }
          v25 = 345;
          goto LABEL_77;
        }
        if ( !(v42 % v13) )
          goto LABEL_15;
        v25 = 330;
LABEL_77:
        SymmetricKey = -1073741811;
        DebugTraceError(
          3221225485LL,
          "status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\opaqueblob.c",
          v25);
        return SymmetricKey;
      }
    }
    SymmetricKey = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)WPP_GLOBAL_Control,
        v12,
        (unsigned int)"status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\opaqueblob.c",
        58);
  }
  return SymmetricKey;
}

```

## disassembly

```asm
0x180019920  push    rbp
0x180019922  push    rbx
0x180019923  push    rdi
0x180019924  push    r12
0x180019926  push    r13
0x180019928  push    r14
0x18001992a  push    r15
0x18001992c  lea     rbp, [rsp-1B0h]
0x180019934  sub     rsp, 2B0h
0x18001993b  mov     rbx, [rbp+1E0h+Src]
0x180019942  mov     r14, rcx
0x180019945  mov     r15d, [rbp+1E0h+arg_28]
0x18001994c  lea     rcx, [rbp+1E0h+var_258+4]; void *
0x180019950  mov     qword ptr [rsp+2E0h+var_288], r8
0x180019955  mov     r8d, 214h; Size
0x18001995b  mov     [rsp+2E0h+var_280], rdx
0x180019960  xor     edx, edx; Val
0x180019962  mov     [rsp+2E0h+var_290], r9d
0x180019967  call    memset
0x18001996c  xor     r13d, r13d
0x18001996f  mov     qword ptr [rsp+2E0h+var_298], r13
0x180019974  cmp     r15d, 1Ch
0x180019978  jb      loc_180019C11
0x18001997e  mov     eax, [rbx]
0x180019980  lea     rdi, cs:180000000h
0x180019987  mov     ecx, [rbx+18h]
0x18001998a  mov     dword ptr [rsp+2E0h+var_270], eax
0x18001998e  mov     eax, [rbx+4]
0x180019991  mov     dword ptr [rsp+2E0h+var_270+4], eax
0x180019995  mov     eax, [rbx+8]
0x180019998  mov     [rsp+2E0h+var_268], eax
0x18001999c  mov     eax, [rbx+0Ch]
0x18001999f  mov     [rsp+2E0h+var_264], eax
0x1800199a3  mov     eax, [rbx+10h]
0x1800199a6  mov     [rsp+2E0h+var_38], rsi
0x1800199ae  mov     esi, [r14+8]
0x1800199b2  mov     [rbp+1E0h+var_260], eax
0x1800199b5  mov     eax, [rbx+14h]
0x1800199b8  mov     [rbp+1E0h+var_25C], eax
0x1800199bb  mov     [rsp+2E0h+var_2A0], r13b
0x1800199c0  mov     dword ptr [rbp+1E0h+var_258], ecx
0x1800199c3  cmp     esi, 10002h
0x1800199c9  jnz     loc_18009FBAE
0x1800199cf  mov     eax, 230h
0x1800199d4  cmp     r15d, eax
0x1800199d7  jnz     loc_180019CC1
0x1800199dd  mov     r8d, eax; Size
0x1800199e0  lea     rcx, [rsp+2E0h+var_270]; void *
0x1800199e5  mov     rdx, rbx; Src
0x1800199e8  call    memmove
0x1800199ed  cmp     dword ptr [rsp+2E0h+var_270], r15d
0x1800199f2  jnz     loc_180019C69
0x1800199f8  cmp     dword ptr [rsp+2E0h+var_270+4], 4D53534Bh
0x180019a00  jnz     loc_180019C69
0x180019a06  cmp     [rsp+2E0h+var_268], esi
0x180019a0a  jnz     loc_180019C69
0x180019a10  mov     ecx, [r14+10h]
0x180019a14  cmp     [rbp+1E0h+var_260], ecx
0x180019a17  jnz     loc_180019C69
0x180019a1d  mov     r12d, [rsp+2E0h+var_264]
0x180019a22  mov     r8d, r12d
0x180019a25  shr     r8d, 18h
0x180019a29  mov     ebx, r12d
0x180019a2c  inc     r8d
0x180019a2f  and     ebx, 0FFFFFFh
0x180019a35  mov     [rsp+2E0h+var_28C], r8d
0x180019a3a  cmp     esi, 10008h
0x180019a40  jz      loc_180019BC3
0x180019a46  cmp     ebx, 6
0x180019a49  jnb     loc_180019CD5
0x180019a4f  cmp     ebx, 3
0x180019a52  jz      loc_180019CCC
0x180019a58  cmp     r8d, 1
0x180019a5c  jnz     loc_180019CD5
0x180019a62  test    ebx, ebx
0x180019a64  jz      short loc_180019A7F
0x180019a66  movzx   eax, si
0x180019a69  dec     eax
0x180019a6b  imul    rax, 70h ; 'p'
0x180019a6f  mov     eax, [rax+rdi+0A5090h]
0x180019a76  bt      eax, ebx
0x180019a79  jnb     loc_180019CD5
0x180019a7f  cmp     esi, 10007h
0x180019a85  jz      loc_180019CE0
0x180019a8b  lea     rcx, [rbp+1E0h+var_258+4]
0x180019a8f  cmp     esi, 10009h
0x180019a95  jnz     loc_180019CF1
0x180019a9b  mov     eax, dword ptr [rbp+1E0h+var_258]; jumptable 000000018009FC44 cases 65537-65544
0x180019a9e  lea     rdx, [rsp+2E0h+var_298]; int
0x180019aa3  mov     rsi, qword ptr [rsp+2E0h+var_288]
0x180019aa8  mov     r9d, [rsp+2E0h+var_290]; int
0x180019aad  mov     r8, rsi; int
0x180019ab0  mov     [rsp+2E0h+var_2B0], 80h; int
0x180019ab8  mov     dword ptr [rsp+2E0h+Size], eax; Size
0x180019abc  mov     [rsp+2E0h+var_2C0], rcx; Src
0x180019ac1  mov     rcx, r14; int
0x180019ac4  call    MSCryptGenerateSymmetricKey
0x180019ac9  mov     edi, eax
0x180019acb  test    eax, eax
0x180019acd  js      loc_180019B6C
0x180019ad3  mov     r12d, [rsp+2E0h+var_264]
0x180019ad8  mov     r13, qword ptr [rsp+2E0h+var_298]
0x180019add  mov     r8d, [rsp+2E0h+var_28C]
0x180019ae2  mov     [rsi+0Ch], ebx
0x180019ae5  cmp     ebx, 3
0x180019ae8  jz      loc_180019D07
0x180019aee  mov     eax, [r14+8]
0x180019af2  cmp     eax, 10007h
0x180019af7  jnz     loc_180019BDD
0x180019afd  mov     r8d, [rsi+10h]; Size
0x180019b01  lea     rdx, [rsp+2E0h+var_270]
0x180019b06  mov     rax, r15
0x180019b09  lea     rcx, [rsi+28h]; void *
0x180019b0d  sub     rax, r8
0x180019b10  add     rdx, rax; Src
0x180019b13  call    memmove
0x180019b18  mov     ecx, [r14+8]
0x180019b1c  sub     ecx, 10001h
0x180019b22  jz      loc_180019D6E
0x180019b28  sub     ecx, 6
0x180019b2b  jz      loc_180019D20
0x180019b31  cmp     ecx, 1
0x180019b34  jz      loc_180019D10
0x180019b3a  mov     eax, [rbp+1E0h+var_25C]
0x180019b3d  cmp     [rsi+18h], eax
0x180019b40  jnz     loc_180019DB6
0x180019b46  mov     rax, [rsp+2E0h+var_280]
0x180019b4b  mov     [rax], r13
0x180019b4e  mov     rsi, [rsp+2E0h+var_38]
0x180019b56  mov     eax, edi
0x180019b58  add     rsp, 2B0h
0x180019b5f  pop     r15
0x180019b61  pop     r14
0x180019b63  pop     r13
0x180019b65  pop     r12
0x180019b67  pop     rdi
0x180019b68  pop     rbx
0x180019b69  pop     rbp
0x180019b6a  retn
0x180019b6c  mov     rax, cs:WPP_GLOBAL_Control
0x180019b73  lea     rcx, WPP_GLOBAL_Control
0x180019b7a  cmp     rax, rcx
0x180019b7d  jz      short loc_180019BAF
0x180019b7f  mov     ecx, [rax+2Ch]
0x180019b82  test    cl, 1
0x180019b85  jz      short loc_180019BAF
0x180019b87  lea     rcx, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180019b8e  mov     [rsp+2E0h+var_2B0], 17Bh
0x180019b96  mov     [rsp+2E0h+Size], rcx
0x180019b9b  lea     r9, aStatus_0; "status"
0x180019ba2  mov     rcx, [rax+18h]
0x180019ba6  mov     dword ptr [rsp+2E0h+var_2C0], edi
0x180019baa  call    WPP_SF_sDsd
0x180019baf  mov     r13, qword ptr [rsp+2E0h+var_298]
0x180019bb4  test    r13, r13
0x180019bb7  jz      short loc_180019B4E
0x180019bb9  mov     rcx, r13
0x180019bbc  call    MSCryptDestroyKey
0x180019bc1  jmp     short loc_180019B4E
0x180019bc3  xor     edx, edx
0x180019bc5  mov     eax, r12d
0x180019bc8  div     ecx
0x180019bca  test    edx, edx
0x180019bcc  jz      loc_180019A8B
0x180019bd2  mov     r9d, 14Ah
0x180019bd8  jmp     loc_18009FC7D
0x180019bdd  sub     eax, 10002h
0x180019be2  jz      loc_180019AFD
0x180019be8  sub     eax, 1
0x180019beb  jz      loc_180019AFD
0x180019bf1  sub     eax, 1
0x180019bf4  jz      loc_180019AFD
0x180019bfa  sub     eax, 1
0x180019bfd  jz      loc_180019AFD
0x180019c03  cmp     eax, 1
0x180019c06  jnz     loc_180019B18
0x180019c0c  jmp     loc_180019AFD
0x180019c11  mov     edi, 0C000000Dh
0x180019c16  mov     rdx, cs:WPP_GLOBAL_Control
0x180019c1d  lea     rcx, WPP_GLOBAL_Control
0x180019c24  cmp     rdx, rcx
0x180019c27  jz      loc_180019B56
0x180019c2d  mov     eax, [rdx+2Ch]
0x180019c30  test    al, 1
0x180019c32  jz      loc_180019B56
0x180019c38  lea     rcx, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180019c3f  mov     [rsp+2E0h+var_2B0], 10Dh
0x180019c47  mov     [rsp+2E0h+Size], rcx
0x180019c4c  lea     r9, aStatus_0; "status"
0x180019c53  mov     rcx, [rdx+18h]
0x180019c57  mov     dword ptr [rsp+2E0h+var_2C0], 0C000000Dh
0x180019c5f  call    WPP_SF_sDsd
0x180019c64  jmp     loc_180019B56
0x180019c69  mov     edi, 0C000000Dh
0x180019c6e  mov     rdx, cs:WPP_GLOBAL_Control
0x180019c75  lea     rcx, WPP_GLOBAL_Control
0x180019c7c  cmp     rdx, rcx
0x180019c7f  jz      loc_180019B4E
0x180019c85  mov     eax, [rdx+2Ch]
0x180019c88  test    al, 1
0x180019c8a  jz      loc_180019B4E
0x180019c90  lea     rcx, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180019c97  mov     [rsp+2E0h+var_2B0], 13Ah
0x180019c9f  mov     [rsp+2E0h+Size], rcx
0x180019ca4  lea     r9, aStatus_0; "status"
0x180019cab  mov     rcx, [rdx+18h]
0x180019caf  mov     dword ptr [rsp+2E0h+var_2C0], 0C000000Dh
0x180019cb7  call    WPP_SF_sDsd
0x180019cbc  jmp     loc_180019B4E
0x180019cc1  mov     r9d, 12Bh
0x180019cc7  jmp     loc_18009FC7D
0x180019ccc  cmp     r8d, ecx
0x180019ccf  jbe     loc_180019A62
0x180019cd5  mov     r9d, 159h
0x180019cdb  jmp     loc_18009FC7D
0x180019ce0  xor     edi, edi
0x180019ce2  lea     rcx, [rbp+1E0h+var_250]
0x180019ce6  add     esi, 0FFFEFFFFh
0x180019cec  jmp     loc_18009FC33
0x180019cf1  xor     edi, edi
0x180019cf3  add     esi, 0FFFEFFFFh; switch 8 cases
0x180019cf9  cmp     esi, 7
0x180019cfc  jbe     loc_18009FC33
0x180019d02  jmp     def_18009FC44; jumptable 000000018009FC44 default case
0x180019d07  mov     [rsi+14h], r8d
0x180019d0b  jmp     loc_180019AEE
0x180019d10  mov     dword ptr [rsi+0Ch], 0
0x180019d17  mov     [rsi+14h], r12d
0x180019d1b  jmp     loc_180019B3A
0x180019d20  mov     r9d, dword ptr [rbp+1E0h+var_258+4]
0x180019d24  lea     eax, [r9-10h]
0x180019d28  cmp     eax, 3F0h
0x180019d2d  ja      loc_18009FC54
0x180019d33  cmp     r9d, [rbp+1E0h+var_25C]
0x180019d37  jnz     loc_18009FC54
0x180019d3d  mov     r8d, [rsi+38h]
0x180019d41  lea     rdx, [rsi+3Ch]
0x180019d45  lea     rcx, [rsi+0C0h]; void *
0x180019d4c  mov     [rsi+150h], r9d
0x180019d53  mov     [rsi+18h], r9d
0x180019d57  call    SymCryptRc2ExpandKeyEx
0x180019d5c  test    eax, eax
0x180019d5e  jz      loc_180019B3A
0x180019d64  mov     edi, 0C000000Dh
0x180019d69  jmp     loc_180019BB4
0x180019d6e  cmp     [rsp+2E0h+var_2A0], 0
0x180019d73  lea     rax, [rbp+1E0h+var_150]
0x180019d7a  lea     rbx, [rbp+1E0h+var_210]
0x180019d7e  mov     r8d, 100h; Size
0x180019d84  cmovnz  rbx, rax
0x180019d88  lea     rcx, [rsi+140h]; void *
0x180019d8f  mov     rdx, rbx; Src
0x180019d92  call    memmove
0x180019d97  movzx   eax, byte ptr [rbx+100h]
0x180019d9e  mov     [rsi+240h], al
0x180019da4  movzx   eax, byte ptr [rbx+101h]
0x180019dab  mov     [rsi+241h], al
0x180019db1  jmp     loc_180019B3A
0x180019db6  mov     r9d, 1E7h
0x180019dbc  jmp     loc_18009FC5A
0x18009fbae  lea     eax, [rsi-10001h]; switch 9 cases
0x18009fbb4  cmp     eax, 8
0x18009fbb7  ja      short def_18009FBC3; jumptable 000000018009FBC3 default case, case 65538
0x18009fbb9  mov     eax, ds:(jpt_18009FBC3 - 180000000h)[rdi+rax*4]
0x18009fbc0  add     rax, rdi
0x18009fbc3  jmp     rax; switch jump
0x18009fbc9  mov     eax, 0ACh; jumptable 000000018009FBC3 case 65539
0x18009fbce  jmp     loc_1800199D4
0x18009fbd3  mov     eax, 0CCh; jumptable 000000018009FBC3 case 65540
0x18009fbd8  jmp     loc_1800199D4
0x18009fbdd  mov     eax, 1BCh; jumptable 000000018009FBC3 case 65541
0x18009fbe2  jmp     loc_1800199D4
0x18009fbe7  mov     eax, 1B4h; jumptable 000000018009FBC3 case 65542
0x18009fbec  jmp     loc_1800199D4
0x18009fbf1  mov     eax, 138h; jumptable 000000018009FBC3 case 65543
0x18009fbf6  jmp     loc_1800199D4
0x18009fbfb  mov     eax, 5Ch ; '\'; jumptable 000000018009FBC3 case 65544
0x18009fc00  jmp     loc_1800199D4
0x18009fc05  mov     eax, 3Ch ; '<'; jumptable 000000018009FBC3 case 65545
0x18009fc0a  jmp     loc_1800199D4
0x18009fc0f  cmp     ecx, 40h ; '@'; jumptable 000000018009FBC3 case 65537
0x18009fc12  mov     eax, 228h
0x18009fc17  mov     edx, 168h
0x18009fc1c  cmovbe  eax, edx
0x18009fc1f  setnbe  [rsp+2E0h+var_2A0]
0x18009fc24  jmp     loc_1800199D4
0x18009fc29  mov     edi, 0C00000E5h; jumptable 000000018009FBC3 default case, case 65538
0x18009fc2e  jmp     loc_180019B4E
0x18009fc33  lea     rdx, cs:180000000h
0x18009fc3a  mov     eax, ds:(jpt_18009FC44 - 180000000h)[rdx+rsi*4]
0x18009fc41  add     rax, rdx
0x18009fc44  jmp     rax; switch jump
0x18009fc4a  mov     rsi, qword ptr [rsp+2E0h+var_288]; jumptable 000000018009FC44 default case
0x18009fc4f  jmp     loc_180019AE2
0x18009fc54  mov     r9d, 1CAh
0x18009fc5a  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18009fc61  mov     ecx, 0C000000Dh
0x18009fc66  lea     rdx, aStatus_0; "status"
0x18009fc6d  mov     edi, 0C000000Dh
0x18009fc72  call    DebugTraceError
  ... truncated ...
```
