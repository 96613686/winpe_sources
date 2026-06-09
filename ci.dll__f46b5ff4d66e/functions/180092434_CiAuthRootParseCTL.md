# CiAuthRootParseCTL

- ea: `0x180092434`
- end: `0x180092918`
- name: `CiAuthRootParseCTL`
- size: `1252`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800dc034`

## callees

- `0x18002bef0`
- `0x18002c040`
- `0x18002c340`
- `0x18005fd8c`
- `0x18008d6e0`
- `0x18008de28`
- `0x180090584`
- `0x180091134`
- `0x180091898`
- `0x180092434`
- `0x180093e18`
- `0x180096fa4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180092496`
- `ntoskrnl!ExAllocatePool2` at `0x180092839`
- `ntoskrnl!ExAllocatePool2` at `0x18009285d`
- `ntoskrnl!ExAllocatePool2` at `0x180092496`
- `ntoskrnl!ExAllocatePool2` at `0x180092839`
- `ntoskrnl!ExAllocatePool2` at `0x18009285d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800928a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800928c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800928d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800928a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800928c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800928d3`
- `ntoskrnl!RtlCompareMemory` at `0x180092562`
- `ntoskrnl!RtlCompareMemory` at `0x180092562`

## pseudocode

```c
__int64 __fastcall CiAuthRootParseCTL(char a1, int a2, int a3, unsigned int **a4, __int64 a5, __int64 a6)
{
  __int64 v6; // r14
  char *Pool2; // rax
  int v11; // edi
  unsigned int *v12; // rsi
  int v13; // eax
  unsigned int i; // ebx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rax
  unsigned int v21; // r12d
  unsigned int v22; // r13d
  unsigned int v23; // r15d
  __int64 v24; // rcx
  const void **v25; // r14
  unsigned int v26; // ebx
  size_t v27; // rcx
  __int64 j; // r8
  __int64 v29; // rdx
  __int64 v30; // r9
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rdx
  _OWORD *v36; // rax
  __int64 v37; // rbx
  unsigned int *v38; // rax
  __int64 v39; // rax
  void *v40; // rcx
  int v43; // [rsp+54h] [rbp-ACh] BYREF
  char *v44; // [rsp+58h] [rbp-A8h]
  __int64 v45; // [rsp+60h] [rbp-A0h]
  unsigned int v46; // [rsp+68h] [rbp-98h] BYREF
  PVOID P; // [rsp+70h] [rbp-90h]
  __int64 v48; // [rsp+78h] [rbp-88h] BYREF
  __int64 v49; // [rsp+80h] [rbp-80h] BYREF
  _OWORD *v50; // [rsp+88h] [rbp-78h] BYREF
  __int64 v51; // [rsp+90h] [rbp-70h]
  unsigned int **v52; // [rsp+98h] [rbp-68h]
  _QWORD v53[100]; // [rsp+A0h] [rbp-60h] BYREF

  v6 = a5;
  v52 = a4;
  v45 = a5;
  Pool2 = (char *)ExAllocatePool2(256, 320, 1668499779);
  P = Pool2;
  if ( !Pool2 )
  {
    v11 = -1073741801;
LABEL_65:
    MincryptFreePolicyInfo(v6);
    return (unsigned int)v11;
  }
  v12 = 0;
  v44 = Pool2 + 80;
  v11 = MinCrypK_VerifySignedDataKModeEx(a2, a3, 0, 0, 0, a5, Pool2, 0, 0);
  if ( v11 >= 0 )
  {
    if ( !*(_DWORD *)a5 )
      goto LABEL_8;
    if ( !*(_QWORD *)(a5 + 16) )
      goto LABEL_8;
    v13 = *(_DWORD *)(a5 + 8);
    if ( (v13 & 0xFFFF0000) != 0 || (v13 & 0x802) == 0 )
      goto LABEL_8;
    for ( i = 0; ; ++i )
    {
      v15 = *(_QWORD *)(a5 + 16);
      if ( i >= *(_DWORD *)(v15 + 48) )
        break;
      if ( !(unsigned __int8)CipValidateCertAgainstEKU(*(_QWORD *)(v15 + 40) + 104LL + 120LL * i) )
        goto LABEL_8;
    }
    if ( *(_DWORD *)P != 9
      || RtlCompareMemory(qword_180031E40, *((const void **)P + 1), 9u) != 9
      || (int)MinAsn1ParseCTL((char *)P + 16, v44) < 0 )
    {
      goto LABEL_8;
    }
    if ( a1 )
    {
      if ( *((_DWORD *)v44 + 12) != 14 )
        goto LABEL_8;
      v16 = *((_QWORD *)v44 + 7);
      v17 = 0x401062B0A060C30LL - *(_QWORD *)v16;
      if ( *(_QWORD *)v16 != 0x401062B0A060C30LL
        || (v18 = *(unsigned int *)(v16 + 8), v17 = 171409921 - v18, v18 != 171409921) )
      {
LABEL_22:
        if ( !v17 )
        {
          if ( (unsigned __int8)MinAsn1DecodeTime(v44 + 96, a6) )
          {
            LODWORD(v49) = 0;
            v48 = 0;
            if ( (int)MinAsn1ExtractContent(*((_QWORD *)v44 + 19), *((unsigned int *)v44 + 36), &v48, &v49) >= 0 )
            {
              v21 = 0;
              while ( 2 )
              {
                if ( v21 >= 2 )
                {
                  *v52 = v12;
                  v12 = 0;
                }
                else
                {
                  v22 = v48;
                  v23 = 0;
                  v24 = v49;
                  while ( 1 )
                  {
                    v51 = v24;
                    if ( !v22 )
                      break;
                    v25 = (const void **)v44;
                    v43 = MinAsn1ParseCTLSubject(v24, v22, v44 + 176);
                    v26 = v43;
                    if ( v43 < 0 )
                      goto LABEL_56;
                    v27 = *((unsigned int *)v25 + 52);
                    if ( (unsigned int)v27 > 0x40 )
                      goto LABEL_56;
                    if ( v21 )
                    {
                      if ( a1 )
                      {
                        v46 = 10;
                        memset(v53, 0, sizeof(v53));
                        v50 = 0;
                        v43 = 0;
                        if ( (int)MinAsn1ParseAttributes(v25 + 28, &v46, v53) > 0 )
                        {
                          for ( j = 0; (unsigned int)j < v46; j = (unsigned int)(j + 1) )
                          {
                            v29 = 10 * j;
                            if ( LODWORD(v53[10 * j + 4]) == 10 )
                            {
                              v30 = v53[10 * j + 5];
                              v31 = 0xA3782010401062BLL - *(_QWORD *)v30;
                              if ( *(_QWORD *)v30 == 0xA3782010401062BLL )
                                v31 = 25099LL - *(unsigned __int16 *)(v30 + 8);
                              if ( !v31 )
                              {
                                if ( &v53[v29]
                                  && (int)MinAsn1ExtractContent(v53[v29 + 9], LODWORD(v53[v29 + 8]), &v43, &v50) >= 0
                                  && v43 == 32 )
                                {
                                  v34 = *((_QWORD *)v12 + 1);
                                  v35 = 68LL * v23;
                                  v36 = v50;
                                  *(_OWORD *)(v35 + v34 + 4) = *v50;
                                  *(_OWORD *)(v35 + v34 + 20) = v36[1];
                                  *(_DWORD *)(v35 + *((_QWORD *)v12 + 1)) = 32;
                                  goto LABEL_50;
                                }
                                break;
                              }
                            }
                          }
                        }
LABEL_56:
                        v11 = -1073740760;
                        goto LABEL_59;
                      }
                      v37 = 68LL * v23;
                      memmove((void *)(v37 + *((_QWORD *)v12 + 1) + 4LL), v25[27], v27);
                      *(_DWORD *)(v37 + *((_QWORD *)v12 + 1)) = *((_DWORD *)v25 + 52);
                      v26 = v43;
                    }
LABEL_50:
                    v22 -= v26;
                    v24 = v26 + v51;
                    ++v23;
                  }
                  if ( v21 )
                    goto LABEL_55;
                  if ( !v23 )
                    break;
                  v38 = (unsigned int *)ExAllocatePool2(256, 16, 1668499779);
                  v12 = v38;
                  if ( v38 )
                  {
                    *v38 = v23;
                    v39 = ExAllocatePool2(256, 68LL * v23, 1668499779);
                    *((_QWORD *)v12 + 1) = v39;
                    if ( v39 )
                    {
LABEL_55:
                      ++v21;
                      continue;
                    }
                  }
                  v11 = -1073741801;
                }
                break;
              }
LABEL_59:
              v6 = v45;
              goto LABEL_60;
            }
          }
        }
LABEL_8:
        v11 = -1073740760;
        goto LABEL_60;
      }
      v19 = 2307;
      v20 = *(unsigned __int16 *)(v16 + 12);
    }
    else
    {
      if ( *((_DWORD *)v44 + 12) != 14 )
        goto LABEL_8;
      v32 = *((_QWORD *)v44 + 7);
      v17 = 0x401062B0A060C30LL - *(_QWORD *)v32;
      if ( *(_QWORD *)v32 != 0x401062B0A060C30LL )
        goto LABEL_22;
      v33 = *(unsigned int *)(v32 + 8);
      v17 = 171409921 - v33;
      if ( v33 != 171409921 )
        goto LABEL_22;
      v19 = 7683;
      v20 = *(unsigned __int16 *)(v32 + 12);
    }
    v17 = v19 - v20;
    goto LABEL_22;
  }
LABEL_60:
  ExFreePoolWithTag(P, 0x63734943u);
  if ( v12 )
  {
    v40 = (void *)*((_QWORD *)v12 + 1);
    if ( v40 )
      ExFreePoolWithTag(v40, 0x63734943u);
    ExFreePoolWithTag(v12, 0x63734943u);
  }
  if ( v11 < 0 )
    goto LABEL_65;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180092434  mov     [rsp-8+arg_0], rbx
0x180092439  push    rbp
0x18009243a  push    rsi
0x18009243b  push    rdi
0x18009243c  push    r12
0x18009243e  push    r13
0x180092440  push    r14
0x180092442  push    r15
0x180092444  lea     rbp, [rsp-2D0h]
0x18009244c  sub     rsp, 3D0h
0x180092453  mov     rax, cs:__security_cookie
0x18009245a  xor     rax, rsp
0x18009245d  mov     [rbp+300h+var_40], rax
0x180092464  mov     r14, [rbp+300h+arg_20]
0x18009246b  mov     rbx, rdx
0x18009246e  mov     r15, [rbp+300h+arg_28]
0x180092475  mov     edx, 140h
0x18009247a  mov     edi, r8d
0x18009247d  mov     [rsp+400h+var_3B0], cl
0x180092481  mov     r12b, cl
0x180092484  mov     [rbp+300h+var_368], r9
0x180092488  mov     r8d, 63734943h
0x18009248e  mov     [rsp+400h+var_3A0], r14
0x180092493  lea     ecx, [rdx-40h]
0x180092496  call    cs:__imp_ExAllocatePool2
0x18009249d  nop     dword ptr [rax+rax+00h]
0x1800924a2  mov     [rsp+400h+P], rax
0x1800924a7  mov     rcx, rax
0x1800924aa  test    rax, rax
0x1800924ad  jnz     short loc_1800924B9
0x1800924af  mov     edi, 0C0000017h
0x1800924b4  jmp     loc_1800928E3
0x1800924b9  xor     esi, esi
0x1800924bb  add     rax, 50h ; 'P'
0x1800924bf  mov     [rsp+400h+var_3C0], rsi; __int64
0x1800924c4  xor     r9d, r9d; int
0x1800924c7  mov     [rsp+400h+var_3C8], rsi; __int64
0x1800924cc  xor     r8d, r8d; int
0x1800924cf  mov     [rsp+400h+var_3D0], rcx; void *
0x1800924d4  mov     edx, edi; int
0x1800924d6  mov     qword ptr [rsp+400h+var_3D8], r14; int
0x1800924db  mov     rcx, rbx; int
0x1800924de  mov     [rsp+400h+var_3E0], rsi; __int64
0x1800924e3  mov     [rsp+400h+var_3A8], rax
0x1800924e8  call    MinCrypK_VerifySignedDataKModeEx
0x1800924ed  mov     edi, eax
0x1800924ef  test    eax, eax
0x1800924f1  js      loc_180092896
0x1800924f7  cmp     [r14], esi
0x1800924fa  jz      short loc_180092514
0x1800924fc  cmp     [r14+10h], rsi
0x180092500  jz      short loc_180092514
0x180092502  mov     eax, [r14+8]
0x180092506  test    eax, 0FFFF0000h
0x18009250b  jnz     short loc_180092514
0x18009250d  test    eax, 802h
0x180092512  jnz     short loc_18009251E
0x180092514  mov     edi, 0C0000428h
0x180092519  jmp     loc_180092896
0x18009251e  xor     ebx, ebx
0x180092520  mov     rdx, [r14+10h]
0x180092524  cmp     ebx, [rdx+30h]
0x180092527  jnb     short loc_180092547
0x180092529  mov     eax, ebx
0x18009252b  imul    rcx, rax, 78h ; 'x'
0x18009252f  mov     rax, [rdx+28h]
0x180092533  add     rax, 68h ; 'h'
0x180092537  add     rcx, rax
0x18009253a  call    CipValidateCertAgainstEKU
0x18009253f  test    al, al
0x180092541  jz      short loc_180092514
0x180092543  inc     ebx
0x180092545  jmp     short loc_180092520
0x180092547  mov     rax, [rsp+400h+P]
0x18009254c  cmp     dword ptr [rax], 9
0x18009254f  jnz     short loc_180092514
0x180092551  mov     rdx, [rax+8]; Source2
0x180092555  lea     rcx, qword_180031E40; Source1
0x18009255c  mov     r8d, 9; Length
0x180092562  call    cs:__imp_RtlCompareMemory
0x180092569  nop     dword ptr [rax+rax+00h]
0x18009256e  cmp     rax, 9
0x180092572  jnz     short loc_180092514
0x180092574  mov     rcx, [rsp+400h+P]
0x180092579  mov     rdx, [rsp+400h+var_3A8]
0x18009257e  add     rcx, 10h
0x180092582  call    MinAsn1ParseCTL
0x180092587  test    eax, eax
0x180092589  js      short loc_180092514
0x18009258b  mov     rax, [rsp+400h+var_3A8]
0x180092590  test    r12b, r12b
0x180092593  jz      loc_180092729
0x180092599  cmp     dword ptr [rax+30h], 0Eh
0x18009259d  jnz     loc_180092514
0x1800925a3  mov     rax, [rsp+400h+var_3A8]
0x1800925a8  mov     rcx, cs:qword_180031E30
0x1800925af  mov     rdx, [rax+38h]
0x1800925b3  sub     rcx, [rdx]
0x1800925b6  jnz     short loc_1800925D4
0x1800925b8  mov     ecx, cs:dword_180031E38
0x1800925be  mov     eax, [rdx+8]
0x1800925c1  sub     rcx, rax
0x1800925c4  jnz     short loc_1800925D4
0x1800925c6  movzx   ecx, cs:word_180031E3C
0x1800925cd  movzx   eax, word ptr [rdx+0Ch]
0x1800925d1  sub     rcx, rax
0x1800925d4  test    rcx, rcx
0x1800925d7  jnz     loc_180092514
0x1800925dd  mov     rcx, [rsp+400h+var_3A8]
0x1800925e2  mov     rdx, r15
0x1800925e5  add     rcx, 60h ; '`'
0x1800925e9  call    MinAsn1DecodeTime
0x1800925ee  test    al, al
0x1800925f0  jz      loc_180092514
0x1800925f6  xor     eax, eax
0x1800925f8  lea     r9, [rbp+300h+var_380]
0x1800925fc  mov     [rsp+7Ch], rax
0x180092601  lea     r8, [rsp+400h+var_388]
0x180092606  mov     [rsp+400h+var_388], rax
0x18009260b  mov     rax, [rsp+400h+var_3A8]
0x180092610  mov     rcx, [rsp+400h+var_3A8]
0x180092615  mov     edx, [rax+90h]
0x18009261b  mov     rcx, [rcx+98h]
0x180092622  call    MinAsn1ExtractContent
0x180092627  test    eax, eax
0x180092629  js      loc_180092514
0x18009262f  xor     r12d, r12d
0x180092632  cmp     r12d, 2
0x180092636  jnb     loc_180092888
0x18009263c  mov     r13d, dword ptr [rsp+400h+var_388]
0x180092641  xor     r15d, r15d
0x180092644  mov     rcx, [rbp+300h+var_380]
0x180092648  mov     [rbp+300h+var_370], rcx
0x18009264c  test    r13d, r13d
0x18009264f  jz      loc_180092819
0x180092655  mov     r14, [rsp+400h+var_3A8]
0x18009265a  mov     edx, r13d
0x18009265d  lea     r8, [r14+0B0h]
0x180092664  call    MinAsn1ParseCTLSubject
0x180092669  mov     [rsp+400h+var_3AC], eax
0x18009266d  mov     ebx, eax
0x18009266f  test    eax, eax
0x180092671  js      loc_18009287A
0x180092677  mov     ecx, [r14+0D0h]
0x18009267e  cmp     ecx, 40h ; '@'
0x180092681  ja      loc_18009287A
0x180092687  test    r12d, r12d
0x18009268a  jz      loc_180092805
0x180092690  cmp     [rsp+400h+var_3B0], 0
0x180092695  jz      loc_1800927D2
0x18009269b  xor     edx, edx; Val
0x18009269d  mov     [rsp+400h+var_398], 0Ah
0x1800926a5  mov     r8d, 320h; Size
0x1800926ab  lea     rcx, [rbp+300h+var_360]; void *
0x1800926af  call    memset
0x1800926b4  lea     rcx, [r14+0E0h]
0x1800926bb  mov     [rbp+300h+var_378], 0
0x1800926c3  lea     r8, [rbp+300h+var_360]
0x1800926c7  mov     [rsp+400h+var_3AC], 0
0x1800926cf  lea     rdx, [rsp+400h+var_398]
0x1800926d4  call    MinAsn1ParseAttributes
0x1800926d9  test    eax, eax
0x1800926db  jle     loc_18009287A
0x1800926e1  mov     r10, cs:off_18002EE18
0x1800926e8  xor     r8d, r8d
0x1800926eb  cmp     r8d, [rsp+400h+var_398]
0x1800926f0  jnb     loc_18009287A
0x1800926f6  lea     rdx, [r8+r8*4]
0x1800926fa  shl     rdx, 4
0x1800926fe  cmp     [rbp+rdx+300h+var_340], 0Ah
0x180092703  jnz     short loc_180092724
0x180092705  mov     r9, [rbp+rdx+300h+var_338]
0x18009270a  mov     rcx, [r10]
0x18009270d  sub     rcx, [r9]
0x180092710  jnz     short loc_18009271F
0x180092712  movzx   ecx, word ptr [r10+8]
0x180092717  movzx   eax, word ptr [r9+8]
0x18009271c  sub     rcx, rax
0x18009271f  test    rcx, rcx
0x180092722  jz      short loc_180092770
0x180092724  inc     r8d
0x180092727  jmp     short loc_1800926EB
0x180092729  cmp     dword ptr [rax+30h], 0Eh
0x18009272d  jnz     loc_180092514
0x180092733  mov     rax, [rsp+400h+var_3A8]
0x180092738  mov     rcx, cs:qword_180034A78
0x18009273f  mov     r8, [rax+38h]
0x180092743  sub     rcx, [r8]
0x180092746  jnz     loc_1800925D4
0x18009274c  mov     ecx, cs:dword_180034A80
0x180092752  mov     eax, [r8+8]
0x180092756  sub     rcx, rax
0x180092759  jnz     loc_1800925D4
0x18009275f  movzx   ecx, cs:word_180034A84
0x180092766  movzx   eax, word ptr [r8+0Ch]
0x18009276b  jmp     loc_1800925D1
0x180092770  lea     rcx, [rbp+300h+var_360]
0x180092774  add     rcx, rdx
0x180092777  jz      loc_18009287A
0x18009277d  mov     edx, [rcx+40h]
0x180092780  lea     r9, [rbp+300h+var_378]
0x180092784  mov     rcx, [rcx+48h]
0x180092788  lea     r8, [rsp+400h+var_3AC]
0x18009278d  call    MinAsn1ExtractContent
0x180092792  test    eax, eax
0x180092794  js      loc_18009287A
0x18009279a  cmp     [rsp+400h+var_3AC], 20h ; ' '
0x18009279f  jnz     loc_18009287A
0x1800927a5  mov     rcx, [rsi+8]
0x1800927a9  mov     eax, r15d
0x1800927ac  imul    rdx, rax, 44h ; 'D'
0x1800927b0  mov     rax, [rbp+300h+var_378]
0x1800927b4  movups  xmm0, xmmword ptr [rax]
0x1800927b7  movups  xmmword ptr [rdx+rcx+4], xmm0
0x1800927bc  movups  xmm1, xmmword ptr [rax+10h]
0x1800927c0  movups  xmmword ptr [rdx+rcx+14h], xmm1
0x1800927c5  mov     rax, [rsi+8]
0x1800927c9  mov     dword ptr [rdx+rax], 20h ; ' '
0x1800927d0  jmp     short loc_180092805
0x1800927d2  mov     rdx, [r14+0D8h]; Src
0x1800927d9  mov     r8, rcx; Size
0x1800927dc  mov     rcx, [rsi+8]
0x1800927e0  mov     eax, r15d
0x1800927e3  add     rcx, 4
0x1800927e7  imul    rbx, rax, 44h ; 'D'
0x1800927eb  add     rcx, rbx; void *
0x1800927ee  call    memmove
0x1800927f3  mov     rcx, [rsi+8]
0x1800927f7  mov     eax, [r14+0D0h]
0x1800927fe  mov     [rbx+rcx], eax
0x180092801  mov     ebx, [rsp+400h+var_3AC]
0x180092805  mov     rcx, [rbp+300h+var_370]
0x180092809  sub     r13d, ebx
0x18009280c  mov     eax, ebx
0x18009280e  add     rcx, rax
0x180092811  inc     r15d
0x180092814  jmp     loc_180092648
0x180092819  test    r12d, r12d
0x18009281c  jnz     short loc_180092872
0x18009281e  test    r15d, r15d
0x180092821  jz      short loc_180092891
0x180092823  mov     ebx, 63734943h
0x180092828  lea     edx, [r12+10h]
0x18009282d  mov     r13d, 100h
0x180092833  mov     r8d, ebx
0x180092836  mov     ecx, r13d
0x180092839  call    cs:__imp_ExAllocatePool2
0x180092840  nop     dword ptr [rax+rax+00h]
0x180092845  mov     rsi, rax
0x180092848  test    rax, rax
0x18009284b  jz      short loc_180092881
0x18009284d  mov     [rax], r15d
0x180092850  mov     r8d, ebx
0x180092853  mov     eax, r15d
0x180092856  mov     ecx, r13d
0x180092859  imul    rdx, rax, 44h ; 'D'
0x18009285d  call    cs:__imp_ExAllocatePool2
0x180092864  nop     dword ptr [rax+rax+00h]
0x180092869  mov     [rsi+8], rax
0x18009286d  test    rax, rax
0x180092870  jz      short loc_180092881
0x180092872  inc     r12d
0x180092875  jmp     loc_180092632
0x18009287a  mov     edi, 0C0000428h
0x18009287f  jmp     short loc_180092891
0x180092881  mov     edi, 0C0000017h
0x180092886  jmp     short loc_180092891
0x180092888  mov     rax, [rbp+300h+var_368]
0x18009288c  mov     [rax], rsi
0x18009288f  xor     esi, esi
0x180092891  mov     r14, [rsp+400h+var_3A0]
0x180092896  mov     rcx, [rsp+400h+P]; P
0x18009289b  mov     r12d, 63734943h
0x1800928a1  mov     edx, r12d; Tag
0x1800928a4  call    cs:__imp_ExFreePoolWithTag
0x1800928ab  nop     dword ptr [rax+rax+00h]
0x1800928b0  test    rsi, rsi
0x1800928b3  jz      short loc_1800928DF
0x1800928b5  mov     rcx, [rsi+8]; P
0x1800928b9  test    rcx, rcx
0x1800928bc  jz      short loc_1800928CD
0x1800928be  mov     edx, r12d; Tag
0x1800928c1  call    cs:__imp_ExFreePoolWithTag
0x1800928c8  nop     dword ptr [rax+rax+00h]
0x1800928cd  mov     edx, r12d; Tag
0x1800928d0  mov     rcx, rsi; P
0x1800928d3  call    cs:__imp_ExFreePoolWithTag
0x1800928da  nop     dword ptr [rax+rax+00h]
0x1800928df  test    edi, edi
0x1800928e1  jns     short loc_1800928EB
0x1800928e3  mov     rcx, r14
0x1800928e6  call    MincryptFreePolicyInfo
0x1800928eb  mov     eax, edi
0x1800928ed  mov     rcx, [rbp+300h+var_40]
0x1800928f4  xor     rcx, rsp; StackCookie
0x1800928f7  call    __security_check_cookie
0x1800928fc  mov     rbx, [rsp+400h+arg_0]
0x180092904  add     rsp, 3D0h
0x18009290b  pop     r15
0x18009290d  pop     r14
  ... truncated ...
```
