# Create_LH_ProfileSet

- ea: `0x180001c0c`
- end: `0x18000227e`
- name: `Create_LH_ProfileSet`
- size: `1650`
- prototype: `__int64 __fastcall(__int64, _WORD *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800023c8`

## callees

- `0x180001a20`
- `0x180001a64`
- `0x180001c0c`
- `0x1800042e0`
- `0x18000604c`
- `0x180018abc`
- `0x18001c4a0`
- `0x18001d15d`
- `0x18003d00e`
- `0x18003d040`

## import_xrefs

- `mscms!GetColorProfileHeader` at `0x180001cf3`
- `mscms!GetColorProfileHeader` at `0x180001cf3`

## pseudocode

```c
__int64 __fastcall Create_LH_ProfileSet(__int64 a1, _WORD *a2, unsigned __int16 **a3)
{
  size_t v5; // rsi
  unsigned __int16 *v6; // rbx
  unsigned int inited; // edi
  _WORD *v8; // r11
  unsigned __int16 v9; // r8
  DWORD phDataColorSpace; // r12d
  DWORD ActualRenderingIntent; // esi
  __int16 v12; // r14
  char v13; // r13
  int v14; // r9d
  BOOL ColorProfileHeader; // eax
  int v16; // ecx
  DWORD phRenderingIntent; // edx
  int v18; // edx
  __int64 v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // rax
  __int64 v26; // rcx
  unsigned int v27; // eax
  void *v28; // r10
  DWORD phClass; // ecx
  char v30; // al
  DWORD v31; // esi
  DWORD v32; // esi
  TAGTYPE v33; // edx
  unsigned int v34; // eax
  __int64 v35; // rcx
  unsigned __int16 *v36; // rsi
  __int64 v37; // rcx
  unsigned int v38; // eax
  int v39; // eax
  __int64 v40; // rax
  __int64 v41; // rdx
  __int64 v42; // xmm1_8
  char v44; // [rsp+30h] [rbp-A9h]
  DWORD phConnectionSpace; // [rsp+34h] [rbp-A5h]
  __int16 v46; // [rsp+34h] [rbp-A5h]
  int v47; // [rsp+38h] [rbp-A1h]
  int v48; // [rsp+3Ch] [rbp-9Dh]
  DWORD pcbElement; // [rsp+48h] [rbp-91h] BYREF
  int v51; // [rsp+4Ch] [rbp-8Dh] BYREF
  __int64 v52; // [rsp+50h] [rbp-89h]
  unsigned __int16 **v53; // [rsp+68h] [rbp-71h]
  PROFILEHEADER pHeader; // [rsp+70h] [rbp-69h] BYREF

  v53 = a3;
  memset_0(&pHeader, 0, sizeof(pHeader));
  v5 = 72LL * (unsigned __int16)a2[1] + 32;
  v6 = (unsigned __int16 *)malloc_0(v5);
  inited = v6 == 0 ? 8 : 0;
  if ( !v6 )
    goto LABEL_90;
  memset_0(v6, 0, v5);
  v8 = a2;
  v9 = 0;
  phDataColorSpace = 538976288;
  v48 = 0;
  phConnectionSpace = 538976288;
  ActualRenderingIntent = 0;
  v12 = 0;
  v44 = 0;
  *v6 = *a2;
  v13 = 0;
  *(_DWORD *)(a1 + 328) = 0;
  LOWORD(v14) = 0;
  v47 = 0;
  while ( (unsigned __int16)v14 < v8[1] )
  {
    v52 = (unsigned __int16)v14;
    inited = 2011;
    ColorProfileHeader = GetColorProfileHeader(*(HPROFILE *)&v8[4 * (unsigned __int16)v14 + 4], &pHeader);
    if ( pHeader.phSignature != 1633907568 )
      goto LABEL_90;
    v9 = 0;
    if ( !ColorProfileHeader )
      goto LABEL_90;
    v14 = v47;
    v16 = *(_DWORD *)(a1 + 364);
    if ( (_WORD)v47 )
    {
      if ( v16 != -1 )
      {
        ActualRenderingIntent = GetActualRenderingIntent(a1, (unsigned __int16)v47, 0);
        pHeader.phRenderingIntent = ActualRenderingIntent;
        v9 = 0;
      }
      *(_DWORD *)&v6[12 * v12 + 10] = ActualRenderingIntent;
    }
    else
    {
      if ( v16 == -1 )
      {
        phRenderingIntent = pHeader.phRenderingIntent;
      }
      else
      {
        phRenderingIntent = GetActualRenderingIntent(a1, 0, 0);
        pHeader.phRenderingIntent = phRenderingIntent;
        v9 = 0;
      }
      *(_DWORD *)&v6[12 * v12 + 10] = phRenderingIntent;
    }
    v8 = a2;
    pcbElement = (unsigned __int16)v14;
    v18 = (unsigned __int16)a2[1] - 1;
    if ( (unsigned __int16)v14 < v18 && pHeader.phClass == 1818848875 )
      goto LABEL_76;
    if ( (_WORD)v14 && (unsigned __int16)v14 < v18 )
    {
      inited = 0;
      if ( pHeader.phClass == 1936744803 )
        goto LABEL_75;
      if ( pHeader.phClass == 1852662636 )
        goto LABEL_76;
    }
    if ( pHeader.phClass == 1852662636 )
    {
      v51 = 0;
      inited = InitNamedColorProfileData(
                 a1,
                 *(void **)&a2[4 * (unsigned __int16)v14 + 4],
                 pHeader.phConnectionSpace,
                 &v51);
      if ( inited )
        goto LABEL_90;
      v8 = a2;
      LOWORD(v14) = v47;
      pHeader.phConnectionSpace = 1281450528;
      if ( a2[1] == 1 )
      {
        *(_DWORD *)(a1 + 328) = 1;
      }
      else
      {
        v19 = v12;
        if ( (_WORD)v47 )
        {
          if ( (unsigned __int16)v47 == (unsigned __int16)a2[1] - 1 )
          {
            *(_DWORD *)(a1 + 328) = 3;
            *(_DWORD *)(a1 + 296) = 1852662636;
            pHeader.phDataColorSpace = 1852662636;
            v22 = v12++;
            v23 = 3 * v22;
            v6[4 * v23 + 8] = 0;
            *(_QWORD *)&v6[4 * v23 + 4] = 0;
            *(_DWORD *)&v6[12 * v19 + 22] = ActualRenderingIntent;
          }
        }
        else
        {
          *(_DWORD *)(a1 + 328) = 2;
          pHeader.phDataColorSpace = 1852662636;
          *(_DWORD *)(a1 + 292) = 1852662636;
          v20 = v12++;
          v21 = 3 * v20;
          v6[4 * v21 + 8] = 0;
          *(_QWORD *)&v6[4 * v21 + 4] = 0;
          *(_DWORD *)&v6[12 * v19 + 22] = ActualRenderingIntent;
          phDataColorSpace = pHeader.phDataColorSpace;
        }
      }
    }
    v24 = v12;
    if ( v13 )
    {
      if ( phConnectionSpace != pHeader.phConnectionSpace )
      {
        v6[12 * v12++ + 8] = (phConnectionSpace == 1281450528) + 1;
        *(_DWORD *)&v6[12 * v24 + 22] = ActualRenderingIntent;
      }
    }
    else if ( v12 > 0 && phDataColorSpace != pHeader.phDataColorSpace )
    {
      v25 = v12++;
      *(_QWORD *)&v6[12 * v25 + 4] = *(_QWORD *)&v6[12 * v25 - 8];
      v6[1] = v12;
      if ( phConnectionSpace != pHeader.phConnectionSpace )
      {
        v26 = 3 * (v24 + 1);
        v6[4 * v26 + 8] = (phConnectionSpace == 1281450528) + 1;
        ++v12;
        *(_DWORD *)&v6[4 * v26 + 10] = ActualRenderingIntent;
      }
      v44 = 1;
    }
    v46 = v12;
    v27 = ProfileRequiresChromaticAdaptation(*(HPROFILE *)&v8[4 * (unsigned __int16)v14 + 4]);
    v9 = 0;
    inited = v27;
    if ( v27 )
    {
      inited = 0;
    }
    else if ( LOBYTE(v6[12 * v12 + 14]) )
    {
      ++v48;
    }
    v14 = v47;
    v8 = a2;
    v28 = *(void **)&a2[4 * (unsigned __int16)v47 + 4];
    *(_QWORD *)&v6[12 * v12 + 4] = v28;
    phClass = pHeader.phClass;
    if ( pHeader.phClass == 1852662636 )
    {
      *(_QWORD *)&v6[12 * v12 + 4] = 0;
      v28 = 0;
      phClass = pHeader.phClass;
    }
    v30 = v44;
    v13 = 1;
    ++v12;
    if ( v44 && (_WORD)v47 )
    {
      if ( (int)pcbElement >= (unsigned __int16)a2[1] - 1 )
        goto LABEL_47;
      if ( phClass == 1936744803 )
      {
        v12 = v46;
LABEL_47:
        v30 = v44;
        goto LABEL_48;
      }
      pcbElement = 0;
      if ( ActualRenderingIntent )
      {
        v31 = ActualRenderingIntent - 1;
        if ( !v31 )
          goto LABEL_56;
        v32 = v31 - 1;
        if ( v32 )
        {
          if ( v32 != 1 )
          {
            inited = 2011;
            goto LABEL_90;
          }
LABEL_56:
          v33 = 1886545201;
        }
        else
        {
          v33 = 1886545202;
        }
      }
      else
      {
        v33 = 1886545200;
      }
      v34 = CMGetPartialProfileElement(v28, v33, 0, &pcbElement, 0);
      v9 = 0;
      inited = v34;
      if ( !v34 )
      {
        v6[12 * v46 + 9] = 1;
        *(_DWORD *)&v6[12 * v46 + 10] = pHeader.phRenderingIntent;
        goto LABEL_60;
      }
      if ( pHeader.phClass == 1633842036 || pHeader.phClass == 1818848875 || pHeader.phClass == 1852662636 )
      {
LABEL_60:
        v8 = a2;
      }
      else
      {
        if ( *(_DWORD *)(a1 + 364) != -1 )
        {
          pHeader.phRenderingIntent = GetActualRenderingIntent(a1, 0xFFFFFFFFLL, 0);
          v9 = 0;
        }
        v8 = a2;
        v35 = 3LL * v12;
        *(_QWORD *)&v6[12 * v12 + 4] = *(_QWORD *)&a2[4 * v52 + 4];
        if ( LOBYTE(v6[12 * v46 + 14]) )
        {
          --v48;
          LOBYTE(v6[12 * v46 + 14]) = 0;
        }
        LOBYTE(v6[12 * v12 + 14]) = 0;
        v12 = v46 + 2;
        *(_DWORD *)&v6[4 * v35 + 10] = pHeader.phRenderingIntent;
      }
      v14 = v47;
      v30 = 0;
    }
LABEL_48:
    v6[1] = v12;
    ActualRenderingIntent = pHeader.phRenderingIntent;
    phConnectionSpace = pHeader.phConnectionSpace;
    if ( pHeader.phClass == 1818848875 )
    {
      phDataColorSpace = pHeader.phConnectionSpace;
    }
    else
    {
      phDataColorSpace = pHeader.phDataColorSpace;
      if ( !v30 )
        goto LABEL_74;
    }
    if ( phDataColorSpace != 1281450528 && phDataColorSpace != 1482250784 )
    {
      v13 = 0;
      v44 = 0;
      goto LABEL_75;
    }
LABEL_74:
    v44 = 1;
LABEL_75:
    LOWORD(v14) = v14 + 1;
    v47 = v14;
  }
  if ( !*(_BYTE *)(a1 + 368) )
  {
    v36 = v6 + 1;
    goto LABEL_83;
  }
  if ( v13 || phDataColorSpace != *(_DWORD *)(a1 + 372) )
  {
LABEL_76:
    inited = 2020;
    goto LABEL_90;
  }
  v36 = v6 + 1;
  v37 = 3LL * v12;
  *(_QWORD *)&v6[4 * v37 + 4] = *(_QWORD *)&v8[4 * (unsigned __int16)v14 + 4];
  *(_DWORD *)&v6[4 * v37 + 10] = 0;
  v6[1] = v12 + 1;
  v38 = CMGetProfileHeader(*(_QWORD *)&v8[4 * (unsigned __int16)v14 + 4], &pHeader);
  v9 = 0;
  inited = v38;
  if ( !v38 )
  {
    *(_DWORD *)(a1 + 296) = pHeader.phConnectionSpace;
LABEL_83:
    v39 = *(_DWORD *)(a1 + 328);
    if ( v39 == 3 || v39 == 1 )
    {
      v36 = v6 + 1;
      --v6[1];
    }
    if ( *(_DWORD *)(a1 + 328) == 2 )
    {
      if ( --*v36 )
      {
        do
        {
          v40 = v9++;
          v41 = 3 * v40;
          v42 = *(_QWORD *)&v6[12 * v40 + 24];
          *(_OWORD *)&v6[4 * v41 + 4] = *(_OWORD *)&v6[12 * v40 + 16];
          *(_QWORD *)&v6[4 * v41 + 12] = v42;
        }
        while ( v9 < *v36 );
      }
    }
    *v53 = v6;
    v6 = 0;
  }
LABEL_90:
  DisposeIfPtr(v6);
  return inited;
}

```

## disassembly

```asm
0x180001c0c  mov     [rsp-8+arg_18], rbx
0x180001c11  push    rbp
0x180001c12  push    rsi
0x180001c13  push    rdi
0x180001c14  push    r12
0x180001c16  push    r13
0x180001c18  push    r14
0x180001c1a  push    r15
0x180001c1c  lea     rbp, [rsp-27h]
0x180001c21  sub     rsp, 100h
0x180001c28  mov     rax, cs:__security_cookie
0x180001c2f  xor     rax, rsp
0x180001c32  mov     [rbp+57h+var_40], rax
0x180001c36  mov     [rbp+57h+var_C8], r8
0x180001c3a  mov     rbx, rdx
0x180001c3d  mov     [rsp+130h+var_F0], rdx
0x180001c42  mov     r15, rcx
0x180001c45  xor     edx, edx; Val
0x180001c47  lea     rcx, [rbp+57h+pHeader]; void *
0x180001c4b  mov     r8d, 80h; Size
0x180001c51  call    memset_0
0x180001c56  movzx   eax, word ptr [rbx+2]
0x180001c5a  lea     rcx, [rax+rax*8]
0x180001c5e  lea     rsi, ds:20h[rcx*8]
0x180001c66  mov     rcx, rsi; Size
0x180001c69  call    malloc_0
0x180001c6e  mov     rbx, rax
0x180001c71  neg     rax
0x180001c74  sbb     edi, edi
0x180001c76  not     edi
0x180001c78  and     edi, 8
0x180001c7b  test    rbx, rbx
0x180001c7e  jz      loc_18000224D
0x180001c84  mov     r8, rsi; Size
0x180001c87  xor     edx, edx; Val
0x180001c89  mov     rcx, rbx; void *
0x180001c8c  call    memset_0
0x180001c91  mov     r11, [rsp+130h+var_F0]
0x180001c96  xor     r8d, r8d
0x180001c99  mov     r12d, 20202020h
0x180001c9f  mov     [rsp+130h+var_F4], r8d
0x180001ca4  mov     [rsp+130h+var_FC], r12d
0x180001ca9  mov     esi, r8d
0x180001cac  mov     r14d, r8d
0x180001caf  mov     [rsp+130h+var_100], r8b
0x180001cb4  movzx   eax, word ptr [r11]
0x180001cb8  lea     edx, [r8+1]
0x180001cbc  mov     [rbx], ax
0x180001cbf  mov     r13b, r8b
0x180001cc2  mov     [r15+148h], r8d
0x180001cc9  mov     r9d, r8d
0x180001ccc  mov     [rsp+130h+var_F8], r8d
0x180001cd1  cmp     r9w, [r11+2]
0x180001cd6  jnb     loc_180002171
0x180001cdc  movzx   eax, r9w
0x180001ce0  lea     rdx, [rbp+57h+pHeader]; pHeader
0x180001ce4  mov     [rsp+130h+var_E0], rax
0x180001ce9  mov     edi, 7DBh
0x180001cee  mov     rcx, [r11+rax*8+8]; hProfile
0x180001cf3  call    cs:__imp_GetColorProfileHeader
0x180001cf9  cmp     [rbp+57h+pHeader.phSignature], 61637370h
0x180001d00  jnz     loc_18000224D
0x180001d06  xor     r8d, r8d
0x180001d09  test    eax, eax
0x180001d0b  jz      loc_18000224D
0x180001d11  mov     r9d, [rsp+130h+var_F8]
0x180001d16  mov     ecx, [r15+16Ch]
0x180001d1d  cmp     r8w, r9w
0x180001d21  jnz     short loc_180001D4D
0x180001d23  cmp     ecx, 0FFFFFFFFh
0x180001d26  jz      short loc_180001D3C
0x180001d28  xor     edx, edx
0x180001d2a  mov     rcx, r15
0x180001d2d  call    GetActualRenderingIntent
0x180001d32  mov     edx, eax
0x180001d34  mov     [rbp+57h+pHeader.phRenderingIntent], eax
0x180001d37  xor     r8d, r8d
0x180001d3a  jmp     short loc_180001D3F
0x180001d3c  mov     edx, [rbp+57h+pHeader.phRenderingIntent]
0x180001d3f  movsx   rax, r14w
0x180001d43  lea     rcx, [rax+rax*2]
0x180001d47  mov     [rbx+rcx*8+14h], edx
0x180001d4b  jmp     short loc_180001D72
0x180001d4d  cmp     ecx, 0FFFFFFFFh
0x180001d50  jz      short loc_180001D66
0x180001d52  movzx   edx, r9w
0x180001d56  mov     rcx, r15
0x180001d59  call    GetActualRenderingIntent
0x180001d5e  mov     esi, eax
0x180001d60  mov     [rbp+57h+pHeader.phRenderingIntent], eax
0x180001d63  xor     r8d, r8d
0x180001d66  movsx   rcx, r14w
0x180001d6a  lea     rdx, [rcx+rcx*2]
0x180001d6e  mov     [rbx+rdx*8+14h], esi
0x180001d72  mov     r11, [rsp+130h+var_F0]
0x180001d77  mov     ecx, [rbp+57h+pHeader.phClass]
0x180001d7a  movzx   eax, r9w
0x180001d7e  mov     [rsp+130h+pcbElement], eax
0x180001d82  movzx   edx, word ptr [r11+2]
0x180001d87  dec     edx
0x180001d89  cmp     eax, edx
0x180001d8b  jge     short loc_180001D99
0x180001d8d  cmp     ecx, 6C696E6Bh
0x180001d93  jz      loc_180002167
0x180001d99  test    r9w, r9w
0x180001d9d  jz      short loc_180001DBE
0x180001d9f  cmp     eax, edx
0x180001da1  jge     short loc_180001DBE
0x180001da3  mov     edi, r8d
0x180001da6  cmp     ecx, 73706163h
0x180001dac  jz      loc_180002154
0x180001db2  cmp     ecx, 6E6D636Ch
0x180001db8  jz      loc_180002167
0x180001dbe  cmp     ecx, 6E6D636Ch
0x180001dc4  jnz     loc_180001EB0
0x180001dca  movzx   edx, r9w
0x180001dce  mov     rcx, r15
0x180001dd1  mov     [rsp+130h+var_E4], r8d
0x180001dd6  lea     r9, [rsp+130h+var_E4]
0x180001ddb  mov     r8d, [rbp+57h+pHeader.phConnectionSpace]
0x180001ddf  mov     rdx, [r11+rdx*8+8]
0x180001de4  call    InitNamedColorProfileData
0x180001de9  xor     r10d, r10d
0x180001dec  mov     edi, eax
0x180001dee  test    eax, eax
0x180001df0  jnz     loc_18000224D
0x180001df6  mov     r11, [rsp+130h+var_F0]
0x180001dfb  lea     edi, [rax+1]
0x180001dfe  mov     r9d, [rsp+130h+var_F8]
0x180001e03  mov     [rbp+57h+pHeader.phConnectionSpace], 4C616220h
0x180001e0a  cmp     di, [r11+2]
0x180001e0f  jnz     short loc_180001E1D
0x180001e11  mov     [r15+148h], edi
0x180001e18  jmp     loc_180001EB5
0x180001e1d  movsx   rdx, r14w
0x180001e21  cmp     r10w, r9w
0x180001e25  jnz     short loc_180001E66
0x180001e27  mov     eax, 6E6D636Ch
0x180001e2c  mov     dword ptr [r15+148h], 2
0x180001e37  mov     [rbp+57h+pHeader.phDataColorSpace], eax
0x180001e3a  mov     [r15+124h], eax
0x180001e41  movsx   rax, r14w
0x180001e45  add     r14w, di
0x180001e49  lea     rcx, [rax+rax*2]
0x180001e4d  mov     [rbx+rcx*8+10h], r10w
0x180001e53  mov     [rbx+rcx*8+8], r10
0x180001e58  lea     rcx, [rdx+rdx*2]
0x180001e5c  mov     [rbx+rcx*8+2Ch], esi
0x180001e60  mov     r12d, [rbp+57h+pHeader.phDataColorSpace]
0x180001e64  jmp     short loc_180001EB5
0x180001e66  movzx   ecx, word ptr [r11+2]
0x180001e6b  sub     ecx, edi
0x180001e6d  movzx   eax, r9w
0x180001e71  cmp     eax, ecx
0x180001e73  jnz     short loc_180001EB5
0x180001e75  mov     eax, 6E6D636Ch
0x180001e7a  mov     dword ptr [r15+148h], 3
0x180001e85  mov     [r15+128h], eax
0x180001e8c  mov     [rbp+57h+pHeader.phDataColorSpace], eax
0x180001e8f  movsx   rax, r14w
0x180001e93  add     r14w, di
0x180001e97  lea     rcx, [rax+rax*2]
0x180001e9b  mov     [rbx+rcx*8+10h], r10w
0x180001ea1  mov     [rbx+rcx*8+8], r10
0x180001ea6  lea     rcx, [rdx+rdx*2]
0x180001eaa  mov     [rbx+rcx*8+2Ch], esi
0x180001eae  jmp     short loc_180001EB5
0x180001eb0  mov     edi, 1
0x180001eb5  movsx   r8, r14w
0x180001eb9  test    r13b, r13b
0x180001ebc  jz      short loc_180001EFB
0x180001ebe  mov     r10d, [rsp+130h+var_FC]
0x180001ec3  cmp     r10d, [rbp+57h+pHeader.phConnectionSpace]
0x180001ec7  jz      loc_180001F5E
0x180001ecd  xor     r12d, r12d
0x180001ed0  movsx   rax, r14w
0x180001ed4  cmp     r10d, 4C616220h
0x180001edb  mov     edx, r12d
0x180001ede  setz    dl
0x180001ee1  add     dx, di
0x180001ee4  lea     rcx, [rax+rax*2]
0x180001ee8  mov     [rbx+rcx*8+10h], dx
0x180001eed  add     r14w, di
0x180001ef1  lea     rcx, [r8+r8*2]
0x180001ef5  mov     [rbx+rcx*8+2Ch], esi
0x180001ef9  jmp     short loc_180001F5E
0x180001efb  test    r14w, r14w
0x180001eff  jle     short loc_180001F5E
0x180001f01  cmp     r12d, [rbp+57h+pHeader.phDataColorSpace]
0x180001f05  jz      short loc_180001F5E
0x180001f07  mov     r10d, [rsp+130h+var_FC]
0x180001f0c  movsx   rax, r14w
0x180001f10  add     r14w, di
0x180001f14  lea     rdx, [rax+rax*2]
0x180001f18  lea     rcx, [rax+rax*2]
0x180001f1c  mov     rax, [rbx+rcx*8-10h]
0x180001f21  mov     [rbx+rdx*8+8], rax
0x180001f26  mov     [rbx+2], r14w
0x180001f2b  cmp     r10d, [rbp+57h+pHeader.phConnectionSpace]
0x180001f2f  jz      short loc_180001F59
0x180001f31  xor     r12d, r12d
0x180001f34  lea     rax, [rdi+r8]
0x180001f38  lea     rcx, [rax+rax*2]
0x180001f3c  cmp     r10d, 4C616220h
0x180001f43  mov     eax, r12d
0x180001f46  setz    al
0x180001f49  add     ax, di
0x180001f4c  mov     [rbx+rcx*8+10h], ax
0x180001f51  add     r14w, di
0x180001f55  mov     [rbx+rcx*8+14h], esi
0x180001f59  mov     [rsp+130h+var_100], dil
0x180001f5e  movsx   rax, r14w
0x180001f62  lea     rdx, [rbp+57h+pHeader]
0x180001f66  movzx   ecx, r9w
0x180001f6a  mov     word ptr [rsp+130h+var_FC], r14w
0x180001f70  lea     r13, [rax+rax*2]
0x180001f74  mov     rcx, [r11+rcx*8+8]; hProfile
0x180001f79  lea     r12, [rbx+r13*8]
0x180001f7d  lea     r8, [r12+1Ch]
0x180001f82  call    ProfileRequiresChromaticAdaptation
0x180001f87  xor     r8d, r8d; dwOffset
0x180001f8a  mov     edi, eax
0x180001f8c  test    eax, eax
0x180001f8e  jnz     short loc_180001F9D
0x180001f90  cmp     [r12+1Ch], r8b
0x180001f95  jz      short loc_180001FA0
0x180001f97  inc     [rsp+130h+var_F4]
0x180001f9b  jmp     short loc_180001FA0
0x180001f9d  mov     edi, r8d
0x180001fa0  mov     r9d, [rsp+130h+var_F8]
0x180001fa5  mov     r11, [rsp+130h+var_F0]
0x180001faa  movzx   eax, r9w
0x180001fae  mov     r10, [r11+rax*8+8]
0x180001fb3  mov     [rbx+r13*8+8], r10
0x180001fb8  mov     ecx, [rbp+57h+pHeader.phClass]
0x180001fbb  cmp     ecx, 6E6D636Ch
0x180001fc1  jnz     short loc_180001FCE
0x180001fc3  mov     [rbx+r13*8+8], r8
0x180001fc8  mov     r10, r8
0x180001fcb  mov     ecx, [rbp+57h+pHeader.phClass]
0x180001fce  mov     al, [rsp+130h+var_100]
0x180001fd2  mov     r13d, 1
0x180001fd8  add     r14w, r13w
0x180001fdc  test    al, al
0x180001fde  jz      short loc_180002006
0x180001fe0  test    r9w, r9w
0x180001fe4  jz      short loc_180002006
0x180001fe6  movzx   eax, word ptr [r11+2]
0x180001feb  sub     eax, r13d
0x180001fee  cmp     [rsp+130h+pcbElement], eax
0x180001ff2  jge     short loc_180002002
0x180001ff4  cmp     ecx, 73706163h
0x180001ffa  jnz     short loc_18000202A
0x180001ffc  movzx   r14d, word ptr [rsp+130h+var_FC]
0x180002002  mov     al, [rsp+130h+var_100]
0x180002006  mov     [rbx+2], r14w
0x18000200b  cmp     [rbp+57h+pHeader.phClass], 6C696E6Bh
0x180002012  mov     ecx, [rbp+57h+pHeader.phConnectionSpace]
0x180002015  mov     esi, [rbp+57h+pHeader.phRenderingIntent]
0x180002018  mov     [rsp+130h+var_FC], ecx
0x18000201c  jnz     loc_18000212B
0x180002022  mov     r12d, ecx
0x180002025  jmp     loc_180002133
0x18000202a  mov     [rsp+130h+pcbElement], r8d
0x18000202f  test    esi, esi
0x180002031  jz      short loc_18000205A
0x180002033  sub     esi, r13d
0x180002036  jz      short loc_180002053
0x180002038  sub     esi, r13d
0x18000203b  jz      short loc_18000204C
0x18000203d  cmp     esi, r13d
0x180002040  jz      short loc_180002053
0x180002042  mov     edi, 7DBh
0x180002047  jmp     loc_18000224D
0x18000204c  mov     edx, 70726532h
0x180002051  jmp     short loc_18000205F
0x180002053  mov     edx, 70726531h
0x180002058  jmp     short loc_18000205F
0x18000205a  mov     edx, 70726530h; tag
0x18000205f  movsx   r12, word ptr [rsp+130h+var_FC]
0x180002065  lea     r9, [rsp+130h+pcbElement]; pcbElement
0x18000206a  mov     rcx, r10; hProfile
0x18000206d  mov     [rsp+130h+var_110], r8; PVOID
0x180002072  call    CMGetPartialProfileElement
0x180002077  xor     r8d, r8d
0x18000207a  mov     edi, eax
0x18000207c  test    eax, eax
0x18000207e  jnz     short loc_1800020A7
0x180002080  lea     rax, [r12+r12*2]
0x180002084  mov     [rbx+rax*8+12h], r13w
0x18000208a  lea     rcx, [r12+r12*2]
0x18000208e  mov     eax, [rbp+57h+pHeader.phRenderingIntent]
0x180002091  mov     [rbx+rcx*8+14h], eax
0x180002095  mov     r11, [rsp+130h+var_F0]
0x18000209a  mov     r9d, [rsp+130h+var_F8]
0x18000209f  mov     al, r8b
0x1800020a2  jmp     loc_180002006
0x1800020a7  mov     eax, [rbp+57h+pHeader.phClass]
0x1800020aa  cmp     eax, 61627374h
0x1800020af  jz      short loc_180002095
  ... truncated ...
```
