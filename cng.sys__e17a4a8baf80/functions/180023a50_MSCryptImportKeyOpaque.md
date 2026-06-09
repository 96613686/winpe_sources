# MSCryptImportKeyOpaque

- ea: `0x180023a50`
- end: `0x180023ef1`
- name: `MSCryptImportKeyOpaque`
- size: `1185`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, void *Src, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180021e20`

## callees

- `0x180010530`
- `0x18001155c`
- `0x1800123d0`
- `0x180023a50`
- `0x180023f00`
- `0x18009ca80`
- `0x1800a4380`
- `0x1800a45c0`

## string_xrefs

- `0x180023cb7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\opaqueblob.c`
- `0x180023d68`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\opaqueblob.c`
- `0x180023dc0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\opaqueblob.c`
- `0x1800a69f8`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\opaqueblob.c`
- `0x1800a6a1b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\opaqueblob.c`

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
              if ( !v16 || (v17 = qword_1800AC090[14 * (unsigned int)(unsigned __int16)v10 - 14], _bittest(&v17, v16)) )
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
0x180023a50  push    rbp
0x180023a52  push    rbx
0x180023a53  push    rdi
0x180023a54  push    r12
0x180023a56  push    r13
0x180023a58  push    r14
0x180023a5a  push    r15
0x180023a5c  lea     rbp, [rsp-1B0h]
0x180023a64  sub     rsp, 2B0h
0x180023a6b  mov     rbx, [rbp+1E0h+Src]
0x180023a72  mov     r14, rcx
0x180023a75  mov     r15d, [rbp+1E0h+arg_28]
0x180023a7c  lea     rcx, [rbp+1E0h+var_258+4]; void *
0x180023a80  mov     qword ptr [rsp+2E0h+var_288], r8
0x180023a85  mov     r8d, 214h; Size
0x180023a8b  mov     [rsp+2E0h+var_280], rdx
0x180023a90  xor     edx, edx; Val
0x180023a92  mov     [rsp+2E0h+var_290], r9d
0x180023a97  call    memset
0x180023a9c  xor     r13d, r13d
0x180023a9f  mov     qword ptr [rsp+2E0h+var_298], r13
0x180023aa4  cmp     r15d, 1Ch
0x180023aa8  jb      loc_180023D41
0x180023aae  mov     eax, [rbx]
0x180023ab0  lea     rdi, cs:180000000h
0x180023ab7  mov     ecx, [rbx+18h]
0x180023aba  mov     dword ptr [rsp+2E0h+var_270], eax
0x180023abe  mov     eax, [rbx+4]
0x180023ac1  mov     dword ptr [rsp+2E0h+var_270+4], eax
0x180023ac5  mov     eax, [rbx+8]
0x180023ac8  mov     [rsp+2E0h+var_268], eax
0x180023acc  mov     eax, [rbx+0Ch]
0x180023acf  mov     [rsp+2E0h+var_264], eax
0x180023ad3  mov     eax, [rbx+10h]
0x180023ad6  mov     [rsp+2E0h+var_38], rsi
0x180023ade  mov     esi, [r14+8]
0x180023ae2  mov     [rbp+1E0h+var_260], eax
0x180023ae5  mov     eax, [rbx+14h]
0x180023ae8  mov     [rbp+1E0h+var_25C], eax
0x180023aeb  mov     [rsp+2E0h+var_2A0], r13b
0x180023af0  mov     dword ptr [rbp+1E0h+var_258], ecx
0x180023af3  cmp     esi, 10002h
0x180023af9  jnz     loc_1800A694C
0x180023aff  mov     eax, 230h
0x180023b04  cmp     r15d, eax
0x180023b07  jnz     loc_180023DF1
0x180023b0d  mov     r8d, eax; Size
0x180023b10  lea     rcx, [rsp+2E0h+var_270]; void *
0x180023b15  mov     rdx, rbx; Src
0x180023b18  call    memmove
0x180023b1d  cmp     dword ptr [rsp+2E0h+var_270], r15d
0x180023b22  jnz     loc_180023D99
0x180023b28  cmp     dword ptr [rsp+2E0h+var_270+4], 4D53534Bh
0x180023b30  jnz     loc_180023D99
0x180023b36  cmp     [rsp+2E0h+var_268], esi
0x180023b3a  jnz     loc_180023D99
0x180023b40  mov     ecx, [r14+10h]
0x180023b44  cmp     [rbp+1E0h+var_260], ecx
0x180023b47  jnz     loc_180023D99
0x180023b4d  mov     r12d, [rsp+2E0h+var_264]
0x180023b52  mov     r8d, r12d
0x180023b55  shr     r8d, 18h
0x180023b59  mov     ebx, r12d
0x180023b5c  inc     r8d
0x180023b5f  and     ebx, 0FFFFFFh
0x180023b65  mov     [rsp+2E0h+var_28C], r8d
0x180023b6a  cmp     esi, 10008h
0x180023b70  jz      loc_180023CF3
0x180023b76  cmp     ebx, 6
0x180023b79  jnb     loc_180023E05
0x180023b7f  cmp     ebx, 3
0x180023b82  jz      loc_180023DFC
0x180023b88  cmp     r8d, 1
0x180023b8c  jnz     loc_180023E05
0x180023b92  test    ebx, ebx
0x180023b94  jz      short loc_180023BAF
0x180023b96  movzx   eax, si
0x180023b99  dec     eax
0x180023b9b  imul    rax, 70h ; 'p'
0x180023b9f  mov     eax, [rax+rdi+0AC090h]
0x180023ba6  bt      eax, ebx
0x180023ba9  jnb     loc_180023E05
0x180023baf  cmp     esi, 10007h
0x180023bb5  jz      loc_180023E10
0x180023bbb  lea     rcx, [rbp+1E0h+var_258+4]
0x180023bbf  cmp     esi, 10009h
0x180023bc5  jnz     loc_180023E21
0x180023bcb  mov     eax, dword ptr [rbp+1E0h+var_258]; jumptable 00000001800A69E2 cases 65537-65544
0x180023bce  lea     rdx, [rsp+2E0h+var_298]; int
0x180023bd3  mov     rsi, qword ptr [rsp+2E0h+var_288]
0x180023bd8  mov     r9d, [rsp+2E0h+var_290]; int
0x180023bdd  mov     r8, rsi; int
0x180023be0  mov     [rsp+2E0h+var_2B0], 80h; int
0x180023be8  mov     dword ptr [rsp+2E0h+Size], eax; Size
0x180023bec  mov     [rsp+2E0h+var_2C0], rcx; Src
0x180023bf1  mov     rcx, r14; int
0x180023bf4  call    MSCryptGenerateSymmetricKey
0x180023bf9  mov     edi, eax
0x180023bfb  test    eax, eax
0x180023bfd  js      loc_180023C9C
0x180023c03  mov     r12d, [rsp+2E0h+var_264]
0x180023c08  mov     r13, qword ptr [rsp+2E0h+var_298]
0x180023c0d  mov     r8d, [rsp+2E0h+var_28C]
0x180023c12  mov     [rsi+0Ch], ebx
0x180023c15  cmp     ebx, 3
0x180023c18  jz      loc_180023E37
0x180023c1e  mov     eax, [r14+8]
0x180023c22  cmp     eax, 10007h
0x180023c27  jnz     loc_180023D0D
0x180023c2d  mov     r8d, [rsi+10h]; Size
0x180023c31  lea     rdx, [rsp+2E0h+var_270]
0x180023c36  mov     rax, r15
0x180023c39  lea     rcx, [rsi+28h]; void *
0x180023c3d  sub     rax, r8
0x180023c40  add     rdx, rax; Src
0x180023c43  call    memmove
0x180023c48  mov     ecx, [r14+8]
0x180023c4c  sub     ecx, 10001h
0x180023c52  jz      loc_180023E9E
0x180023c58  sub     ecx, 6
0x180023c5b  jz      loc_180023E50
0x180023c61  cmp     ecx, 1
0x180023c64  jz      loc_180023E40
0x180023c6a  mov     eax, [rbp+1E0h+var_25C]
0x180023c6d  cmp     [rsi+18h], eax
0x180023c70  jnz     loc_180023EE6
0x180023c76  mov     rax, [rsp+2E0h+var_280]
0x180023c7b  mov     [rax], r13
0x180023c7e  mov     rsi, [rsp+2E0h+var_38]
0x180023c86  mov     eax, edi
0x180023c88  add     rsp, 2B0h
0x180023c8f  pop     r15
0x180023c91  pop     r14
0x180023c93  pop     r13
0x180023c95  pop     r12
0x180023c97  pop     rdi
0x180023c98  pop     rbx
0x180023c99  pop     rbp
0x180023c9a  retn
0x180023c9c  mov     rax, cs:WPP_GLOBAL_Control
0x180023ca3  lea     rcx, WPP_GLOBAL_Control
0x180023caa  cmp     rax, rcx
0x180023cad  jz      short loc_180023CDF
0x180023caf  mov     ecx, [rax+2Ch]
0x180023cb2  test    cl, 1
0x180023cb5  jz      short loc_180023CDF
0x180023cb7  lea     rcx, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180023cbe  mov     [rsp+2E0h+var_2B0], 17Bh
0x180023cc6  mov     [rsp+2E0h+Size], rcx
0x180023ccb  lea     r9, aStatus_0; "status"
0x180023cd2  mov     rcx, [rax+18h]
0x180023cd6  mov     dword ptr [rsp+2E0h+var_2C0], edi
0x180023cda  call    WPP_SF_sDsd
0x180023cdf  mov     r13, qword ptr [rsp+2E0h+var_298]
0x180023ce4  test    r13, r13
0x180023ce7  jz      short loc_180023C7E
0x180023ce9  mov     rcx, r13
0x180023cec  call    MSCryptDestroyKey
0x180023cf1  jmp     short loc_180023C7E
0x180023cf3  xor     edx, edx
0x180023cf5  mov     eax, r12d
0x180023cf8  div     ecx
0x180023cfa  test    edx, edx
0x180023cfc  jz      loc_180023BBB
0x180023d02  mov     r9d, 14Ah
0x180023d08  jmp     loc_1800A6A1B
0x180023d0d  sub     eax, 10002h
0x180023d12  jz      loc_180023C2D
0x180023d18  sub     eax, 1
0x180023d1b  jz      loc_180023C2D
0x180023d21  sub     eax, 1
0x180023d24  jz      loc_180023C2D
0x180023d2a  sub     eax, 1
0x180023d2d  jz      loc_180023C2D
0x180023d33  cmp     eax, 1
0x180023d36  jnz     loc_180023C48
0x180023d3c  jmp     loc_180023C2D
0x180023d41  mov     edi, 0C000000Dh
0x180023d46  mov     rdx, cs:WPP_GLOBAL_Control
0x180023d4d  lea     rcx, WPP_GLOBAL_Control
0x180023d54  cmp     rdx, rcx
0x180023d57  jz      loc_180023C86
0x180023d5d  mov     eax, [rdx+2Ch]
0x180023d60  test    al, 1
0x180023d62  jz      loc_180023C86
0x180023d68  lea     rcx, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180023d6f  mov     [rsp+2E0h+var_2B0], 10Dh
0x180023d77  mov     [rsp+2E0h+Size], rcx
0x180023d7c  lea     r9, aStatus_0; "status"
0x180023d83  mov     rcx, [rdx+18h]
0x180023d87  mov     dword ptr [rsp+2E0h+var_2C0], 0C000000Dh
0x180023d8f  call    WPP_SF_sDsd
0x180023d94  jmp     loc_180023C86
0x180023d99  mov     edi, 0C000000Dh
0x180023d9e  mov     rdx, cs:WPP_GLOBAL_Control
0x180023da5  lea     rcx, WPP_GLOBAL_Control
0x180023dac  cmp     rdx, rcx
0x180023daf  jz      loc_180023C7E
0x180023db5  mov     eax, [rdx+2Ch]
0x180023db8  test    al, 1
0x180023dba  jz      loc_180023C7E
0x180023dc0  lea     rcx, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180023dc7  mov     [rsp+2E0h+var_2B0], 13Ah
0x180023dcf  mov     [rsp+2E0h+Size], rcx
0x180023dd4  lea     r9, aStatus_0; "status"
0x180023ddb  mov     rcx, [rdx+18h]
0x180023ddf  mov     dword ptr [rsp+2E0h+var_2C0], 0C000000Dh
0x180023de7  call    WPP_SF_sDsd
0x180023dec  jmp     loc_180023C7E
0x180023df1  mov     r9d, 12Bh
0x180023df7  jmp     loc_1800A6A1B
0x180023dfc  cmp     r8d, ecx
0x180023dff  jbe     loc_180023B92
0x180023e05  mov     r9d, 159h
0x180023e0b  jmp     loc_1800A6A1B
0x180023e10  xor     edi, edi
0x180023e12  lea     rcx, [rbp+1E0h+var_250]
0x180023e16  add     esi, 0FFFEFFFFh
0x180023e1c  jmp     loc_1800A69D1
0x180023e21  xor     edi, edi
0x180023e23  add     esi, 0FFFEFFFFh; switch 8 cases
0x180023e29  cmp     esi, 7
0x180023e2c  jbe     loc_1800A69D1
0x180023e32  jmp     def_1800A69E2; jumptable 00000001800A69E2 default case
0x180023e37  mov     [rsi+14h], r8d
0x180023e3b  jmp     loc_180023C1E
0x180023e40  mov     dword ptr [rsi+0Ch], 0
0x180023e47  mov     [rsi+14h], r12d
0x180023e4b  jmp     loc_180023C6A
0x180023e50  mov     r9d, dword ptr [rbp+1E0h+var_258+4]
0x180023e54  lea     eax, [r9-10h]
0x180023e58  cmp     eax, 3F0h
0x180023e5d  ja      loc_1800A69F2
0x180023e63  cmp     r9d, [rbp+1E0h+var_25C]
0x180023e67  jnz     loc_1800A69F2
0x180023e6d  mov     r8d, [rsi+38h]
0x180023e71  lea     rdx, [rsi+3Ch]
0x180023e75  lea     rcx, [rsi+0C0h]; void *
0x180023e7c  mov     [rsi+150h], r9d
0x180023e83  mov     [rsi+18h], r9d
0x180023e87  call    SymCryptRc2ExpandKeyEx
0x180023e8c  test    eax, eax
0x180023e8e  jz      loc_180023C6A
0x180023e94  mov     edi, 0C000000Dh
0x180023e99  jmp     loc_180023CE4
0x180023e9e  cmp     [rsp+2E0h+var_2A0], 0
0x180023ea3  lea     rax, [rbp+1E0h+var_150]
0x180023eaa  lea     rbx, [rbp+1E0h+var_210]
0x180023eae  mov     r8d, 100h; Size
0x180023eb4  cmovnz  rbx, rax
0x180023eb8  lea     rcx, [rsi+140h]; void *
0x180023ebf  mov     rdx, rbx; Src
0x180023ec2  call    memmove
0x180023ec7  movzx   eax, byte ptr [rbx+100h]
0x180023ece  mov     [rsi+240h], al
0x180023ed4  movzx   eax, byte ptr [rbx+101h]
0x180023edb  mov     [rsi+241h], al
0x180023ee1  jmp     loc_180023C6A
0x180023ee6  mov     r9d, 1E7h
0x180023eec  jmp     loc_1800A69F8
0x1800a694c  lea     eax, [rsi-10001h]; switch 9 cases
0x1800a6952  cmp     eax, 8
0x1800a6955  ja      short def_1800A6961; jumptable 00000001800A6961 default case, case 65538
0x1800a6957  mov     eax, ds:(jpt_1800A6961 - 180000000h)[rdi+rax*4]
0x1800a695e  add     rax, rdi
0x1800a6961  jmp     rax; switch jump
0x1800a6967  mov     eax, 0ACh; jumptable 00000001800A6961 case 65539
0x1800a696c  jmp     loc_180023B04
0x1800a6971  mov     eax, 0CCh; jumptable 00000001800A6961 case 65540
0x1800a6976  jmp     loc_180023B04
0x1800a697b  mov     eax, 1BCh; jumptable 00000001800A6961 case 65541
0x1800a6980  jmp     loc_180023B04
0x1800a6985  mov     eax, 1B4h; jumptable 00000001800A6961 case 65542
0x1800a698a  jmp     loc_180023B04
0x1800a698f  mov     eax, 138h; jumptable 00000001800A6961 case 65543
0x1800a6994  jmp     loc_180023B04
0x1800a6999  mov     eax, 5Ch ; '\'; jumptable 00000001800A6961 case 65544
0x1800a699e  jmp     loc_180023B04
0x1800a69a3  mov     eax, 3Ch ; '<'; jumptable 00000001800A6961 case 65545
0x1800a69a8  jmp     loc_180023B04
0x1800a69ad  cmp     ecx, 40h ; '@'; jumptable 00000001800A6961 case 65537
0x1800a69b0  mov     eax, 228h
0x1800a69b5  mov     edx, 168h
0x1800a69ba  cmovbe  eax, edx
0x1800a69bd  setnbe  [rsp+2E0h+var_2A0]
0x1800a69c2  jmp     loc_180023B04
0x1800a69c7  mov     edi, 0C00000E5h; jumptable 00000001800A6961 default case, case 65538
0x1800a69cc  jmp     loc_180023C7E
0x1800a69d1  lea     rdx, cs:180000000h
0x1800a69d8  mov     eax, ds:(jpt_1800A69E2 - 180000000h)[rdx+rsi*4]
0x1800a69df  add     rax, rdx
0x1800a69e2  jmp     rax; switch jump
0x1800a69e8  mov     rsi, qword ptr [rsp+2E0h+var_288]; jumptable 00000001800A69E2 default case
0x1800a69ed  jmp     loc_180023C12
0x1800a69f2  mov     r9d, 1CAh
0x1800a69f8  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a69ff  mov     ecx, 0C000000Dh
0x1800a6a04  lea     rdx, aStatus_0; "status"
0x1800a6a0b  mov     edi, 0C000000Dh
0x1800a6a10  call    DebugTraceError
  ... truncated ...
```
