# MSCryptImportKeyOpaque

- ea: `0x1800169d0`
- end: `0x180016e71`
- name: `MSCryptImportKeyOpaque`
- size: `1185`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, void *Src, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180014da0`

## callees

- `0x180006410`
- `0x18000743c`
- `0x1800082b0`
- `0x1800169d0`
- `0x180016e80`
- `0x180096230`
- `0x18009f780`
- `0x18009fa80`

## string_xrefs

- `0x180016c37`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\opaqueblob.c`
- `0x180016ce8`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\opaqueblob.c`
- `0x180016d40`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\opaqueblob.c`
- `0x1800a1810`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\opaqueblob.c`
- `0x1800a1833`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\opaqueblob.c`

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
              if ( !v16 || (v17 = qword_1800A7090[14 * (unsigned int)(unsigned __int16)v10 - 14], _bittest(&v17, v16)) )
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
0x1800169d0  push    rbp
0x1800169d2  push    rbx
0x1800169d3  push    rdi
0x1800169d4  push    r12
0x1800169d6  push    r13
0x1800169d8  push    r14
0x1800169da  push    r15
0x1800169dc  lea     rbp, [rsp-1B0h]
0x1800169e4  sub     rsp, 2B0h
0x1800169eb  mov     rbx, [rbp+1E0h+Src]
0x1800169f2  mov     r14, rcx
0x1800169f5  mov     r15d, [rbp+1E0h+arg_28]
0x1800169fc  lea     rcx, [rbp+1E0h+var_258+4]; void *
0x180016a00  mov     qword ptr [rsp+2E0h+var_288], r8
0x180016a05  mov     r8d, 214h; Size
0x180016a0b  mov     [rsp+2E0h+var_280], rdx
0x180016a10  xor     edx, edx; Val
0x180016a12  mov     [rsp+2E0h+var_290], r9d
0x180016a17  call    memset
0x180016a1c  xor     r13d, r13d
0x180016a1f  mov     qword ptr [rsp+2E0h+var_298], r13
0x180016a24  cmp     r15d, 1Ch
0x180016a28  jb      loc_180016CC1
0x180016a2e  mov     eax, [rbx]
0x180016a30  lea     rdi, cs:180000000h
0x180016a37  mov     ecx, [rbx+18h]
0x180016a3a  mov     dword ptr [rsp+2E0h+var_270], eax
0x180016a3e  mov     eax, [rbx+4]
0x180016a41  mov     dword ptr [rsp+2E0h+var_270+4], eax
0x180016a45  mov     eax, [rbx+8]
0x180016a48  mov     [rsp+2E0h+var_268], eax
0x180016a4c  mov     eax, [rbx+0Ch]
0x180016a4f  mov     [rsp+2E0h+var_264], eax
0x180016a53  mov     eax, [rbx+10h]
0x180016a56  mov     [rsp+2E0h+var_38], rsi
0x180016a5e  mov     esi, [r14+8]
0x180016a62  mov     [rbp+1E0h+var_260], eax
0x180016a65  mov     eax, [rbx+14h]
0x180016a68  mov     [rbp+1E0h+var_25C], eax
0x180016a6b  mov     [rsp+2E0h+var_2A0], r13b
0x180016a70  mov     dword ptr [rbp+1E0h+var_258], ecx
0x180016a73  cmp     esi, 10002h
0x180016a79  jnz     loc_1800A1764
0x180016a7f  mov     eax, 230h
0x180016a84  cmp     r15d, eax
0x180016a87  jnz     loc_180016D71
0x180016a8d  mov     r8d, eax; Size
0x180016a90  lea     rcx, [rsp+2E0h+var_270]; void *
0x180016a95  mov     rdx, rbx; Src
0x180016a98  call    memmove
0x180016a9d  cmp     dword ptr [rsp+2E0h+var_270], r15d
0x180016aa2  jnz     loc_180016D19
0x180016aa8  cmp     dword ptr [rsp+2E0h+var_270+4], 4D53534Bh
0x180016ab0  jnz     loc_180016D19
0x180016ab6  cmp     [rsp+2E0h+var_268], esi
0x180016aba  jnz     loc_180016D19
0x180016ac0  mov     ecx, [r14+10h]
0x180016ac4  cmp     [rbp+1E0h+var_260], ecx
0x180016ac7  jnz     loc_180016D19
0x180016acd  mov     r12d, [rsp+2E0h+var_264]
0x180016ad2  mov     r8d, r12d
0x180016ad5  shr     r8d, 18h
0x180016ad9  mov     ebx, r12d
0x180016adc  inc     r8d
0x180016adf  and     ebx, 0FFFFFFh
0x180016ae5  mov     [rsp+2E0h+var_28C], r8d
0x180016aea  cmp     esi, 10008h
0x180016af0  jz      loc_180016C73
0x180016af6  cmp     ebx, 6
0x180016af9  jnb     loc_180016D85
0x180016aff  cmp     ebx, 3
0x180016b02  jz      loc_180016D7C
0x180016b08  cmp     r8d, 1
0x180016b0c  jnz     loc_180016D85
0x180016b12  test    ebx, ebx
0x180016b14  jz      short loc_180016B2F
0x180016b16  movzx   eax, si
0x180016b19  dec     eax
0x180016b1b  imul    rax, 70h ; 'p'
0x180016b1f  mov     eax, [rax+rdi+0A7090h]
0x180016b26  bt      eax, ebx
0x180016b29  jnb     loc_180016D85
0x180016b2f  cmp     esi, 10007h
0x180016b35  jz      loc_180016D90
0x180016b3b  lea     rcx, [rbp+1E0h+var_258+4]
0x180016b3f  cmp     esi, 10009h
0x180016b45  jnz     loc_180016DA1
0x180016b4b  mov     eax, dword ptr [rbp+1E0h+var_258]; jumptable 00000001800A17FA cases 65537-65544
0x180016b4e  lea     rdx, [rsp+2E0h+var_298]; int
0x180016b53  mov     rsi, qword ptr [rsp+2E0h+var_288]
0x180016b58  mov     r9d, [rsp+2E0h+var_290]; int
0x180016b5d  mov     r8, rsi; int
0x180016b60  mov     [rsp+2E0h+var_2B0], 80h; int
0x180016b68  mov     dword ptr [rsp+2E0h+Size], eax; Size
0x180016b6c  mov     [rsp+2E0h+var_2C0], rcx; Src
0x180016b71  mov     rcx, r14; int
0x180016b74  call    MSCryptGenerateSymmetricKey
0x180016b79  mov     edi, eax
0x180016b7b  test    eax, eax
0x180016b7d  js      loc_180016C1C
0x180016b83  mov     r12d, [rsp+2E0h+var_264]
0x180016b88  mov     r13, qword ptr [rsp+2E0h+var_298]
0x180016b8d  mov     r8d, [rsp+2E0h+var_28C]
0x180016b92  mov     [rsi+0Ch], ebx
0x180016b95  cmp     ebx, 3
0x180016b98  jz      loc_180016DB7
0x180016b9e  mov     eax, [r14+8]
0x180016ba2  cmp     eax, 10007h
0x180016ba7  jnz     loc_180016C8D
0x180016bad  mov     r8d, [rsi+10h]; Size
0x180016bb1  lea     rdx, [rsp+2E0h+var_270]
0x180016bb6  mov     rax, r15
0x180016bb9  lea     rcx, [rsi+28h]; void *
0x180016bbd  sub     rax, r8
0x180016bc0  add     rdx, rax; Src
0x180016bc3  call    memmove
0x180016bc8  mov     ecx, [r14+8]
0x180016bcc  sub     ecx, 10001h
0x180016bd2  jz      loc_180016E1E
0x180016bd8  sub     ecx, 6
0x180016bdb  jz      loc_180016DD0
0x180016be1  cmp     ecx, 1
0x180016be4  jz      loc_180016DC0
0x180016bea  mov     eax, [rbp+1E0h+var_25C]
0x180016bed  cmp     [rsi+18h], eax
0x180016bf0  jnz     loc_180016E66
0x180016bf6  mov     rax, [rsp+2E0h+var_280]
0x180016bfb  mov     [rax], r13
0x180016bfe  mov     rsi, [rsp+2E0h+var_38]
0x180016c06  mov     eax, edi
0x180016c08  add     rsp, 2B0h
0x180016c0f  pop     r15
0x180016c11  pop     r14
0x180016c13  pop     r13
0x180016c15  pop     r12
0x180016c17  pop     rdi
0x180016c18  pop     rbx
0x180016c19  pop     rbp
0x180016c1a  retn
0x180016c1c  mov     rax, cs:WPP_GLOBAL_Control
0x180016c23  lea     rcx, WPP_GLOBAL_Control
0x180016c2a  cmp     rax, rcx
0x180016c2d  jz      short loc_180016C5F
0x180016c2f  mov     ecx, [rax+2Ch]
0x180016c32  test    cl, 1
0x180016c35  jz      short loc_180016C5F
0x180016c37  lea     rcx, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180016c3e  mov     [rsp+2E0h+var_2B0], 17Bh
0x180016c46  mov     [rsp+2E0h+Size], rcx
0x180016c4b  lea     r9, aStatus_0; "status"
0x180016c52  mov     rcx, [rax+18h]
0x180016c56  mov     dword ptr [rsp+2E0h+var_2C0], edi
0x180016c5a  call    WPP_SF_sDsd
0x180016c5f  mov     r13, qword ptr [rsp+2E0h+var_298]
0x180016c64  test    r13, r13
0x180016c67  jz      short loc_180016BFE
0x180016c69  mov     rcx, r13
0x180016c6c  call    MSCryptDestroyKey
0x180016c71  jmp     short loc_180016BFE
0x180016c73  xor     edx, edx
0x180016c75  mov     eax, r12d
0x180016c78  div     ecx
0x180016c7a  test    edx, edx
0x180016c7c  jz      loc_180016B3B
0x180016c82  mov     r9d, 14Ah
0x180016c88  jmp     loc_1800A1833
0x180016c8d  sub     eax, 10002h
0x180016c92  jz      loc_180016BAD
0x180016c98  sub     eax, 1
0x180016c9b  jz      loc_180016BAD
0x180016ca1  sub     eax, 1
0x180016ca4  jz      loc_180016BAD
0x180016caa  sub     eax, 1
0x180016cad  jz      loc_180016BAD
0x180016cb3  cmp     eax, 1
0x180016cb6  jnz     loc_180016BC8
0x180016cbc  jmp     loc_180016BAD
0x180016cc1  mov     edi, 0C000000Dh
0x180016cc6  mov     rdx, cs:WPP_GLOBAL_Control
0x180016ccd  lea     rcx, WPP_GLOBAL_Control
0x180016cd4  cmp     rdx, rcx
0x180016cd7  jz      loc_180016C06
0x180016cdd  mov     eax, [rdx+2Ch]
0x180016ce0  test    al, 1
0x180016ce2  jz      loc_180016C06
0x180016ce8  lea     rcx, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180016cef  mov     [rsp+2E0h+var_2B0], 10Dh
0x180016cf7  mov     [rsp+2E0h+Size], rcx
0x180016cfc  lea     r9, aStatus_0; "status"
0x180016d03  mov     rcx, [rdx+18h]
0x180016d07  mov     dword ptr [rsp+2E0h+var_2C0], 0C000000Dh
0x180016d0f  call    WPP_SF_sDsd
0x180016d14  jmp     loc_180016C06
0x180016d19  mov     edi, 0C000000Dh
0x180016d1e  mov     rdx, cs:WPP_GLOBAL_Control
0x180016d25  lea     rcx, WPP_GLOBAL_Control
0x180016d2c  cmp     rdx, rcx
0x180016d2f  jz      loc_180016BFE
0x180016d35  mov     eax, [rdx+2Ch]
0x180016d38  test    al, 1
0x180016d3a  jz      loc_180016BFE
0x180016d40  lea     rcx, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180016d47  mov     [rsp+2E0h+var_2B0], 13Ah
0x180016d4f  mov     [rsp+2E0h+Size], rcx
0x180016d54  lea     r9, aStatus_0; "status"
0x180016d5b  mov     rcx, [rdx+18h]
0x180016d5f  mov     dword ptr [rsp+2E0h+var_2C0], 0C000000Dh
0x180016d67  call    WPP_SF_sDsd
0x180016d6c  jmp     loc_180016BFE
0x180016d71  mov     r9d, 12Bh
0x180016d77  jmp     loc_1800A1833
0x180016d7c  cmp     r8d, ecx
0x180016d7f  jbe     loc_180016B12
0x180016d85  mov     r9d, 159h
0x180016d8b  jmp     loc_1800A1833
0x180016d90  xor     edi, edi
0x180016d92  lea     rcx, [rbp+1E0h+var_250]
0x180016d96  add     esi, 0FFFEFFFFh
0x180016d9c  jmp     loc_1800A17E9
0x180016da1  xor     edi, edi
0x180016da3  add     esi, 0FFFEFFFFh; switch 8 cases
0x180016da9  cmp     esi, 7
0x180016dac  jbe     loc_1800A17E9
0x180016db2  jmp     def_1800A17FA; jumptable 00000001800A17FA default case
0x180016db7  mov     [rsi+14h], r8d
0x180016dbb  jmp     loc_180016B9E
0x180016dc0  mov     dword ptr [rsi+0Ch], 0
0x180016dc7  mov     [rsi+14h], r12d
0x180016dcb  jmp     loc_180016BEA
0x180016dd0  mov     r9d, dword ptr [rbp+1E0h+var_258+4]
0x180016dd4  lea     eax, [r9-10h]
0x180016dd8  cmp     eax, 3F0h
0x180016ddd  ja      loc_1800A180A
0x180016de3  cmp     r9d, [rbp+1E0h+var_25C]
0x180016de7  jnz     loc_1800A180A
0x180016ded  mov     r8d, [rsi+38h]
0x180016df1  lea     rdx, [rsi+3Ch]
0x180016df5  lea     rcx, [rsi+0C0h]; void *
0x180016dfc  mov     [rsi+150h], r9d
0x180016e03  mov     [rsi+18h], r9d
0x180016e07  call    SymCryptRc2ExpandKeyEx
0x180016e0c  test    eax, eax
0x180016e0e  jz      loc_180016BEA
0x180016e14  mov     edi, 0C000000Dh
0x180016e19  jmp     loc_180016C64
0x180016e1e  cmp     [rsp+2E0h+var_2A0], 0
0x180016e23  lea     rax, [rbp+1E0h+var_150]
0x180016e2a  lea     rbx, [rbp+1E0h+var_210]
0x180016e2e  mov     r8d, 100h; Size
0x180016e34  cmovnz  rbx, rax
0x180016e38  lea     rcx, [rsi+140h]; void *
0x180016e3f  mov     rdx, rbx; Src
0x180016e42  call    memmove
0x180016e47  movzx   eax, byte ptr [rbx+100h]
0x180016e4e  mov     [rsi+240h], al
0x180016e54  movzx   eax, byte ptr [rbx+101h]
0x180016e5b  mov     [rsi+241h], al
0x180016e61  jmp     loc_180016BEA
0x180016e66  mov     r9d, 1E7h
0x180016e6c  jmp     loc_1800A1810
0x1800a1764  lea     eax, [rsi-10001h]; switch 9 cases
0x1800a176a  cmp     eax, 8
0x1800a176d  ja      short def_1800A1779; jumptable 00000001800A1779 default case, case 65538
0x1800a176f  mov     eax, ds:(jpt_1800A1779 - 180000000h)[rdi+rax*4]
0x1800a1776  add     rax, rdi
0x1800a1779  jmp     rax; switch jump
0x1800a177f  mov     eax, 0ACh; jumptable 00000001800A1779 case 65539
0x1800a1784  jmp     loc_180016A84
0x1800a1789  mov     eax, 0CCh; jumptable 00000001800A1779 case 65540
0x1800a178e  jmp     loc_180016A84
0x1800a1793  mov     eax, 1BCh; jumptable 00000001800A1779 case 65541
0x1800a1798  jmp     loc_180016A84
0x1800a179d  mov     eax, 1B4h; jumptable 00000001800A1779 case 65542
0x1800a17a2  jmp     loc_180016A84
0x1800a17a7  mov     eax, 138h; jumptable 00000001800A1779 case 65543
0x1800a17ac  jmp     loc_180016A84
0x1800a17b1  mov     eax, 5Ch ; '\'; jumptable 00000001800A1779 case 65544
0x1800a17b6  jmp     loc_180016A84
0x1800a17bb  mov     eax, 3Ch ; '<'; jumptable 00000001800A1779 case 65545
0x1800a17c0  jmp     loc_180016A84
0x1800a17c5  cmp     ecx, 40h ; '@'; jumptable 00000001800A1779 case 65537
0x1800a17c8  mov     eax, 228h
0x1800a17cd  mov     edx, 168h
0x1800a17d2  cmovbe  eax, edx
0x1800a17d5  setnbe  [rsp+2E0h+var_2A0]
0x1800a17da  jmp     loc_180016A84
0x1800a17df  mov     edi, 0C00000E5h; jumptable 00000001800A1779 default case, case 65538
0x1800a17e4  jmp     loc_180016BFE
0x1800a17e9  lea     rdx, cs:180000000h
0x1800a17f0  mov     eax, ds:(jpt_1800A17FA - 180000000h)[rdx+rsi*4]
0x1800a17f7  add     rax, rdx
0x1800a17fa  jmp     rax; switch jump
0x1800a1800  mov     rsi, qword ptr [rsp+2E0h+var_288]; jumptable 00000001800A17FA default case
0x1800a1805  jmp     loc_180016B92
0x1800a180a  mov     r9d, 1CAh
0x1800a1810  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a1817  mov     ecx, 0C000000Dh
0x1800a181c  lea     rdx, aStatus_0; "status"
0x1800a1823  mov     edi, 0C000000Dh
0x1800a1828  call    DebugTraceError
  ... truncated ...
```
