# CiAuthRootParseCTL

- ea: `0x1800993c4`
- end: `0x1800998a8`
- name: `CiAuthRootParseCTL`
- size: `1252`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800dd30c`

## callees

- `0x18002c0d0`
- `0x18002c200`
- `0x18002c500`
- `0x1800604e0`
- `0x18008eda4`
- `0x180094670`
- `0x180094db8`
- `0x180097514`
- `0x1800980c4`
- `0x180098828`
- `0x1800993c4`
- `0x18009ada8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180099426`
- `ntoskrnl!ExAllocatePool2` at `0x1800997c9`
- `ntoskrnl!ExAllocatePool2` at `0x1800997ed`
- `ntoskrnl!ExAllocatePool2` at `0x180099426`
- `ntoskrnl!ExAllocatePool2` at `0x1800997c9`
- `ntoskrnl!ExAllocatePool2` at `0x1800997ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x180099834`
- `ntoskrnl!ExFreePoolWithTag` at `0x180099851`
- `ntoskrnl!ExFreePoolWithTag` at `0x180099863`
- `ntoskrnl!ExFreePoolWithTag` at `0x180099834`
- `ntoskrnl!ExFreePoolWithTag` at `0x180099851`
- `ntoskrnl!ExFreePoolWithTag` at `0x180099863`
- `ntoskrnl!RtlCompareMemory` at `0x1800994f2`
- `ntoskrnl!RtlCompareMemory` at `0x1800994f2`

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
      || RtlCompareMemory(qword_1800320A0, *((const void **)P + 1), 9u) != 9
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
0x1800993c4  mov     [rsp-8+arg_0], rbx
0x1800993c9  push    rbp
0x1800993ca  push    rsi
0x1800993cb  push    rdi
0x1800993cc  push    r12
0x1800993ce  push    r13
0x1800993d0  push    r14
0x1800993d2  push    r15
0x1800993d4  lea     rbp, [rsp-2D0h]
0x1800993dc  sub     rsp, 3D0h
0x1800993e3  mov     rax, cs:__security_cookie
0x1800993ea  xor     rax, rsp
0x1800993ed  mov     [rbp+300h+var_40], rax
0x1800993f4  mov     r14, [rbp+300h+arg_20]
0x1800993fb  mov     rbx, rdx
0x1800993fe  mov     r15, [rbp+300h+arg_28]
0x180099405  mov     edx, 140h
0x18009940a  mov     edi, r8d
0x18009940d  mov     [rsp+400h+var_3B0], cl
0x180099411  mov     r12b, cl
0x180099414  mov     [rbp+300h+var_368], r9
0x180099418  mov     r8d, 63734943h
0x18009941e  mov     [rsp+400h+var_3A0], r14
0x180099423  lea     ecx, [rdx-40h]
0x180099426  call    cs:__imp_ExAllocatePool2
0x18009942d  nop     dword ptr [rax+rax+00h]
0x180099432  mov     [rsp+400h+P], rax
0x180099437  mov     rcx, rax
0x18009943a  test    rax, rax
0x18009943d  jnz     short loc_180099449
0x18009943f  mov     edi, 0C0000017h
0x180099444  jmp     loc_180099873
0x180099449  xor     esi, esi
0x18009944b  add     rax, 50h ; 'P'
0x18009944f  mov     [rsp+400h+var_3C0], rsi; __int64
0x180099454  xor     r9d, r9d; int
0x180099457  mov     [rsp+400h+var_3C8], rsi; __int64
0x18009945c  xor     r8d, r8d; int
0x18009945f  mov     [rsp+400h+var_3D0], rcx; void *
0x180099464  mov     edx, edi; int
0x180099466  mov     qword ptr [rsp+400h+var_3D8], r14; int
0x18009946b  mov     rcx, rbx; int
0x18009946e  mov     [rsp+400h+var_3E0], rsi; __int64
0x180099473  mov     [rsp+400h+var_3A8], rax
0x180099478  call    MinCrypK_VerifySignedDataKModeEx
0x18009947d  mov     edi, eax
0x18009947f  test    eax, eax
0x180099481  js      loc_180099826
0x180099487  cmp     [r14], esi
0x18009948a  jz      short loc_1800994A4
0x18009948c  cmp     [r14+10h], rsi
0x180099490  jz      short loc_1800994A4
0x180099492  mov     eax, [r14+8]
0x180099496  test    eax, 0FFFF0000h
0x18009949b  jnz     short loc_1800994A4
0x18009949d  test    eax, 802h
0x1800994a2  jnz     short loc_1800994AE
0x1800994a4  mov     edi, 0C0000428h
0x1800994a9  jmp     loc_180099826
0x1800994ae  xor     ebx, ebx
0x1800994b0  mov     rdx, [r14+10h]
0x1800994b4  cmp     ebx, [rdx+30h]
0x1800994b7  jnb     short loc_1800994D7
0x1800994b9  mov     eax, ebx
0x1800994bb  imul    rcx, rax, 78h ; 'x'
0x1800994bf  mov     rax, [rdx+28h]
0x1800994c3  add     rax, 68h ; 'h'
0x1800994c7  add     rcx, rax
0x1800994ca  call    CipValidateCertAgainstEKU
0x1800994cf  test    al, al
0x1800994d1  jz      short loc_1800994A4
0x1800994d3  inc     ebx
0x1800994d5  jmp     short loc_1800994B0
0x1800994d7  mov     rax, [rsp+400h+P]
0x1800994dc  cmp     dword ptr [rax], 9
0x1800994df  jnz     short loc_1800994A4
0x1800994e1  mov     rdx, [rax+8]; Source2
0x1800994e5  lea     rcx, qword_1800320A0; Source1
0x1800994ec  mov     r8d, 9; Length
0x1800994f2  call    cs:__imp_RtlCompareMemory
0x1800994f9  nop     dword ptr [rax+rax+00h]
0x1800994fe  cmp     rax, 9
0x180099502  jnz     short loc_1800994A4
0x180099504  mov     rcx, [rsp+400h+P]
0x180099509  mov     rdx, [rsp+400h+var_3A8]
0x18009950e  add     rcx, 10h
0x180099512  call    MinAsn1ParseCTL
0x180099517  test    eax, eax
0x180099519  js      short loc_1800994A4
0x18009951b  mov     rax, [rsp+400h+var_3A8]
0x180099520  test    r12b, r12b
0x180099523  jz      loc_1800996B9
0x180099529  cmp     dword ptr [rax+30h], 0Eh
0x18009952d  jnz     loc_1800994A4
0x180099533  mov     rax, [rsp+400h+var_3A8]
0x180099538  mov     rcx, cs:qword_180032090
0x18009953f  mov     rdx, [rax+38h]
0x180099543  sub     rcx, [rdx]
0x180099546  jnz     short loc_180099564
0x180099548  mov     ecx, cs:dword_180032098
0x18009954e  mov     eax, [rdx+8]
0x180099551  sub     rcx, rax
0x180099554  jnz     short loc_180099564
0x180099556  movzx   ecx, cs:word_18003209C
0x18009955d  movzx   eax, word ptr [rdx+0Ch]
0x180099561  sub     rcx, rax
0x180099564  test    rcx, rcx
0x180099567  jnz     loc_1800994A4
0x18009956d  mov     rcx, [rsp+400h+var_3A8]
0x180099572  mov     rdx, r15
0x180099575  add     rcx, 60h ; '`'
0x180099579  call    MinAsn1DecodeTime
0x18009957e  test    al, al
0x180099580  jz      loc_1800994A4
0x180099586  xor     eax, eax
0x180099588  lea     r9, [rbp+300h+var_380]
0x18009958c  mov     [rsp+7Ch], rax
0x180099591  lea     r8, [rsp+400h+var_388]
0x180099596  mov     [rsp+400h+var_388], rax
0x18009959b  mov     rax, [rsp+400h+var_3A8]
0x1800995a0  mov     rcx, [rsp+400h+var_3A8]
0x1800995a5  mov     edx, [rax+90h]
0x1800995ab  mov     rcx, [rcx+98h]
0x1800995b2  call    MinAsn1ExtractContent
0x1800995b7  test    eax, eax
0x1800995b9  js      loc_1800994A4
0x1800995bf  xor     r12d, r12d
0x1800995c2  cmp     r12d, 2
0x1800995c6  jnb     loc_180099818
0x1800995cc  mov     r13d, dword ptr [rsp+400h+var_388]
0x1800995d1  xor     r15d, r15d
0x1800995d4  mov     rcx, [rbp+300h+var_380]
0x1800995d8  mov     [rbp+300h+var_370], rcx
0x1800995dc  test    r13d, r13d
0x1800995df  jz      loc_1800997A9
0x1800995e5  mov     r14, [rsp+400h+var_3A8]
0x1800995ea  mov     edx, r13d
0x1800995ed  lea     r8, [r14+0B0h]
0x1800995f4  call    MinAsn1ParseCTLSubject
0x1800995f9  mov     [rsp+400h+var_3AC], eax
0x1800995fd  mov     ebx, eax
0x1800995ff  test    eax, eax
0x180099601  js      loc_18009980A
0x180099607  mov     ecx, [r14+0D0h]
0x18009960e  cmp     ecx, 40h ; '@'
0x180099611  ja      loc_18009980A
0x180099617  test    r12d, r12d
0x18009961a  jz      loc_180099795
0x180099620  cmp     [rsp+400h+var_3B0], 0
0x180099625  jz      loc_180099762
0x18009962b  xor     edx, edx; Val
0x18009962d  mov     [rsp+400h+var_398], 0Ah
0x180099635  mov     r8d, 320h; Size
0x18009963b  lea     rcx, [rbp+300h+var_360]; void *
0x18009963f  call    memset
0x180099644  lea     rcx, [r14+0E0h]
0x18009964b  mov     [rbp+300h+var_378], 0
0x180099653  lea     r8, [rbp+300h+var_360]
0x180099657  mov     [rsp+400h+var_3AC], 0
0x18009965f  lea     rdx, [rsp+400h+var_398]
0x180099664  call    MinAsn1ParseAttributes
0x180099669  test    eax, eax
0x18009966b  jle     loc_18009980A
0x180099671  mov     r10, cs:off_18002EDC8
0x180099678  xor     r8d, r8d
0x18009967b  cmp     r8d, [rsp+400h+var_398]
0x180099680  jnb     loc_18009980A
0x180099686  lea     rdx, [r8+r8*4]
0x18009968a  shl     rdx, 4
0x18009968e  cmp     [rbp+rdx+300h+var_340], 0Ah
0x180099693  jnz     short loc_1800996B4
0x180099695  mov     r9, [rbp+rdx+300h+var_338]
0x18009969a  mov     rcx, [r10]
0x18009969d  sub     rcx, [r9]
0x1800996a0  jnz     short loc_1800996AF
0x1800996a2  movzx   ecx, word ptr [r10+8]
0x1800996a7  movzx   eax, word ptr [r9+8]
0x1800996ac  sub     rcx, rax
0x1800996af  test    rcx, rcx
0x1800996b2  jz      short loc_180099700
0x1800996b4  inc     r8d
0x1800996b7  jmp     short loc_18009967B
0x1800996b9  cmp     dword ptr [rax+30h], 0Eh
0x1800996bd  jnz     loc_1800994A4
0x1800996c3  mov     rax, [rsp+400h+var_3A8]
0x1800996c8  mov     rcx, cs:qword_180034AB8
0x1800996cf  mov     r8, [rax+38h]
0x1800996d3  sub     rcx, [r8]
0x1800996d6  jnz     loc_180099564
0x1800996dc  mov     ecx, cs:dword_180034AC0
0x1800996e2  mov     eax, [r8+8]
0x1800996e6  sub     rcx, rax
0x1800996e9  jnz     loc_180099564
0x1800996ef  movzx   ecx, cs:word_180034AC4
0x1800996f6  movzx   eax, word ptr [r8+0Ch]
0x1800996fb  jmp     loc_180099561
0x180099700  lea     rcx, [rbp+300h+var_360]
0x180099704  add     rcx, rdx
0x180099707  jz      loc_18009980A
0x18009970d  mov     edx, [rcx+40h]
0x180099710  lea     r9, [rbp+300h+var_378]
0x180099714  mov     rcx, [rcx+48h]
0x180099718  lea     r8, [rsp+400h+var_3AC]
0x18009971d  call    MinAsn1ExtractContent
0x180099722  test    eax, eax
0x180099724  js      loc_18009980A
0x18009972a  cmp     [rsp+400h+var_3AC], 20h ; ' '
0x18009972f  jnz     loc_18009980A
0x180099735  mov     rcx, [rsi+8]
0x180099739  mov     eax, r15d
0x18009973c  imul    rdx, rax, 44h ; 'D'
0x180099740  mov     rax, [rbp+300h+var_378]
0x180099744  movups  xmm0, xmmword ptr [rax]
0x180099747  movups  xmmword ptr [rdx+rcx+4], xmm0
0x18009974c  movups  xmm1, xmmword ptr [rax+10h]
0x180099750  movups  xmmword ptr [rdx+rcx+14h], xmm1
0x180099755  mov     rax, [rsi+8]
0x180099759  mov     dword ptr [rdx+rax], 20h ; ' '
0x180099760  jmp     short loc_180099795
0x180099762  mov     rdx, [r14+0D8h]; Src
0x180099769  mov     r8, rcx; Size
0x18009976c  mov     rcx, [rsi+8]
0x180099770  mov     eax, r15d
0x180099773  add     rcx, 4
0x180099777  imul    rbx, rax, 44h ; 'D'
0x18009977b  add     rcx, rbx; void *
0x18009977e  call    memmove
0x180099783  mov     rcx, [rsi+8]
0x180099787  mov     eax, [r14+0D0h]
0x18009978e  mov     [rbx+rcx], eax
0x180099791  mov     ebx, [rsp+400h+var_3AC]
0x180099795  mov     rcx, [rbp+300h+var_370]
0x180099799  sub     r13d, ebx
0x18009979c  mov     eax, ebx
0x18009979e  add     rcx, rax
0x1800997a1  inc     r15d
0x1800997a4  jmp     loc_1800995D8
0x1800997a9  test    r12d, r12d
0x1800997ac  jnz     short loc_180099802
0x1800997ae  test    r15d, r15d
0x1800997b1  jz      short loc_180099821
0x1800997b3  mov     ebx, 63734943h
0x1800997b8  lea     edx, [r12+10h]
0x1800997bd  mov     r13d, 100h
0x1800997c3  mov     r8d, ebx
0x1800997c6  mov     ecx, r13d
0x1800997c9  call    cs:__imp_ExAllocatePool2
0x1800997d0  nop     dword ptr [rax+rax+00h]
0x1800997d5  mov     rsi, rax
0x1800997d8  test    rax, rax
0x1800997db  jz      short loc_180099811
0x1800997dd  mov     [rax], r15d
0x1800997e0  mov     r8d, ebx
0x1800997e3  mov     eax, r15d
0x1800997e6  mov     ecx, r13d
0x1800997e9  imul    rdx, rax, 44h ; 'D'
0x1800997ed  call    cs:__imp_ExAllocatePool2
0x1800997f4  nop     dword ptr [rax+rax+00h]
0x1800997f9  mov     [rsi+8], rax
0x1800997fd  test    rax, rax
0x180099800  jz      short loc_180099811
0x180099802  inc     r12d
0x180099805  jmp     loc_1800995C2
0x18009980a  mov     edi, 0C0000428h
0x18009980f  jmp     short loc_180099821
0x180099811  mov     edi, 0C0000017h
0x180099816  jmp     short loc_180099821
0x180099818  mov     rax, [rbp+300h+var_368]
0x18009981c  mov     [rax], rsi
0x18009981f  xor     esi, esi
0x180099821  mov     r14, [rsp+400h+var_3A0]
0x180099826  mov     rcx, [rsp+400h+P]; P
0x18009982b  mov     r12d, 63734943h
0x180099831  mov     edx, r12d; Tag
0x180099834  call    cs:__imp_ExFreePoolWithTag
0x18009983b  nop     dword ptr [rax+rax+00h]
0x180099840  test    rsi, rsi
0x180099843  jz      short loc_18009986F
0x180099845  mov     rcx, [rsi+8]; P
0x180099849  test    rcx, rcx
0x18009984c  jz      short loc_18009985D
0x18009984e  mov     edx, r12d; Tag
0x180099851  call    cs:__imp_ExFreePoolWithTag
0x180099858  nop     dword ptr [rax+rax+00h]
0x18009985d  mov     edx, r12d; Tag
0x180099860  mov     rcx, rsi; P
0x180099863  call    cs:__imp_ExFreePoolWithTag
0x18009986a  nop     dword ptr [rax+rax+00h]
0x18009986f  test    edi, edi
0x180099871  jns     short loc_18009987B
0x180099873  mov     rcx, r14
0x180099876  call    MincryptFreePolicyInfo
0x18009987b  mov     eax, edi
0x18009987d  mov     rcx, [rbp+300h+var_40]
0x180099884  xor     rcx, rsp; StackCookie
0x180099887  call    __security_check_cookie
0x18009988c  mov     rbx, [rsp+400h+arg_0]
0x180099894  add     rsp, 3D0h
0x18009989b  pop     r15
0x18009989d  pop     r14
  ... truncated ...
```
