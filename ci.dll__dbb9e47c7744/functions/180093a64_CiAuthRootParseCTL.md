# CiAuthRootParseCTL

- ea: `0x180093a64`
- end: `0x180093f48`
- name: `CiAuthRootParseCTL`
- size: `1252`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800dd2fc`

## callees

- `0x18002bf20`
- `0x18002c080`
- `0x18002c380`
- `0x180060540`
- `0x18008ed10`
- `0x18008f458`
- `0x180091bb4`
- `0x180092764`
- `0x180092ec8`
- `0x180093a64`
- `0x180095448`
- `0x1800985d4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180093ac6`
- `ntoskrnl!ExAllocatePool2` at `0x180093e69`
- `ntoskrnl!ExAllocatePool2` at `0x180093e8d`
- `ntoskrnl!ExAllocatePool2` at `0x180093ac6`
- `ntoskrnl!ExAllocatePool2` at `0x180093e69`
- `ntoskrnl!ExAllocatePool2` at `0x180093e8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x180093ed4`
- `ntoskrnl!ExFreePoolWithTag` at `0x180093ef1`
- `ntoskrnl!ExFreePoolWithTag` at `0x180093f03`
- `ntoskrnl!ExFreePoolWithTag` at `0x180093ed4`
- `ntoskrnl!ExFreePoolWithTag` at `0x180093ef1`
- `ntoskrnl!ExFreePoolWithTag` at `0x180093f03`
- `ntoskrnl!RtlCompareMemory` at `0x180093b92`
- `ntoskrnl!RtlCompareMemory` at `0x180093b92`

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
      || RtlCompareMemory(qword_180031F40, *((const void **)P + 1), 9u) != 9
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
0x180093a64  mov     [rsp-8+arg_0], rbx
0x180093a69  push    rbp
0x180093a6a  push    rsi
0x180093a6b  push    rdi
0x180093a6c  push    r12
0x180093a6e  push    r13
0x180093a70  push    r14
0x180093a72  push    r15
0x180093a74  lea     rbp, [rsp-2D0h]
0x180093a7c  sub     rsp, 3D0h
0x180093a83  mov     rax, cs:__security_cookie
0x180093a8a  xor     rax, rsp
0x180093a8d  mov     [rbp+300h+var_40], rax
0x180093a94  mov     r14, [rbp+300h+arg_20]
0x180093a9b  mov     rbx, rdx
0x180093a9e  mov     r15, [rbp+300h+arg_28]
0x180093aa5  mov     edx, 140h
0x180093aaa  mov     edi, r8d
0x180093aad  mov     [rsp+400h+var_3B0], cl
0x180093ab1  mov     r12b, cl
0x180093ab4  mov     [rbp+300h+var_368], r9
0x180093ab8  mov     r8d, 63734943h
0x180093abe  mov     [rsp+400h+var_3A0], r14
0x180093ac3  lea     ecx, [rdx-40h]
0x180093ac6  call    cs:__imp_ExAllocatePool2
0x180093acd  nop     dword ptr [rax+rax+00h]
0x180093ad2  mov     [rsp+400h+P], rax
0x180093ad7  mov     rcx, rax
0x180093ada  test    rax, rax
0x180093add  jnz     short loc_180093AE9
0x180093adf  mov     edi, 0C0000017h
0x180093ae4  jmp     loc_180093F13
0x180093ae9  xor     esi, esi
0x180093aeb  add     rax, 50h ; 'P'
0x180093aef  mov     [rsp+400h+var_3C0], rsi; __int64
0x180093af4  xor     r9d, r9d; int
0x180093af7  mov     [rsp+400h+var_3C8], rsi; __int64
0x180093afc  xor     r8d, r8d; int
0x180093aff  mov     [rsp+400h+var_3D0], rcx; void *
0x180093b04  mov     edx, edi; int
0x180093b06  mov     qword ptr [rsp+400h+var_3D8], r14; int
0x180093b0b  mov     rcx, rbx; int
0x180093b0e  mov     [rsp+400h+var_3E0], rsi; __int64
0x180093b13  mov     [rsp+400h+var_3A8], rax
0x180093b18  call    MinCrypK_VerifySignedDataKModeEx
0x180093b1d  mov     edi, eax
0x180093b1f  test    eax, eax
0x180093b21  js      loc_180093EC6
0x180093b27  cmp     [r14], esi
0x180093b2a  jz      short loc_180093B44
0x180093b2c  cmp     [r14+10h], rsi
0x180093b30  jz      short loc_180093B44
0x180093b32  mov     eax, [r14+8]
0x180093b36  test    eax, 0FFFF0000h
0x180093b3b  jnz     short loc_180093B44
0x180093b3d  test    eax, 802h
0x180093b42  jnz     short loc_180093B4E
0x180093b44  mov     edi, 0C0000428h
0x180093b49  jmp     loc_180093EC6
0x180093b4e  xor     ebx, ebx
0x180093b50  mov     rdx, [r14+10h]
0x180093b54  cmp     ebx, [rdx+30h]
0x180093b57  jnb     short loc_180093B77
0x180093b59  mov     eax, ebx
0x180093b5b  imul    rcx, rax, 78h ; 'x'
0x180093b5f  mov     rax, [rdx+28h]
0x180093b63  add     rax, 68h ; 'h'
0x180093b67  add     rcx, rax
0x180093b6a  call    CipValidateCertAgainstEKU
0x180093b6f  test    al, al
0x180093b71  jz      short loc_180093B44
0x180093b73  inc     ebx
0x180093b75  jmp     short loc_180093B50
0x180093b77  mov     rax, [rsp+400h+P]
0x180093b7c  cmp     dword ptr [rax], 9
0x180093b7f  jnz     short loc_180093B44
0x180093b81  mov     rdx, [rax+8]; Source2
0x180093b85  lea     rcx, qword_180031F40; Source1
0x180093b8c  mov     r8d, 9; Length
0x180093b92  call    cs:__imp_RtlCompareMemory
0x180093b99  nop     dword ptr [rax+rax+00h]
0x180093b9e  cmp     rax, 9
0x180093ba2  jnz     short loc_180093B44
0x180093ba4  mov     rcx, [rsp+400h+P]
0x180093ba9  mov     rdx, [rsp+400h+var_3A8]
0x180093bae  add     rcx, 10h
0x180093bb2  call    MinAsn1ParseCTL
0x180093bb7  test    eax, eax
0x180093bb9  js      short loc_180093B44
0x180093bbb  mov     rax, [rsp+400h+var_3A8]
0x180093bc0  test    r12b, r12b
0x180093bc3  jz      loc_180093D59
0x180093bc9  cmp     dword ptr [rax+30h], 0Eh
0x180093bcd  jnz     loc_180093B44
0x180093bd3  mov     rax, [rsp+400h+var_3A8]
0x180093bd8  mov     rcx, cs:qword_180031F30
0x180093bdf  mov     rdx, [rax+38h]
0x180093be3  sub     rcx, [rdx]
0x180093be6  jnz     short loc_180093C04
0x180093be8  mov     ecx, cs:dword_180031F38
0x180093bee  mov     eax, [rdx+8]
0x180093bf1  sub     rcx, rax
0x180093bf4  jnz     short loc_180093C04
0x180093bf6  movzx   ecx, cs:word_180031F3C
0x180093bfd  movzx   eax, word ptr [rdx+0Ch]
0x180093c01  sub     rcx, rax
0x180093c04  test    rcx, rcx
0x180093c07  jnz     loc_180093B44
0x180093c0d  mov     rcx, [rsp+400h+var_3A8]
0x180093c12  mov     rdx, r15
0x180093c15  add     rcx, 60h ; '`'
0x180093c19  call    MinAsn1DecodeTime
0x180093c1e  test    al, al
0x180093c20  jz      loc_180093B44
0x180093c26  xor     eax, eax
0x180093c28  lea     r9, [rbp+300h+var_380]
0x180093c2c  mov     [rsp+7Ch], rax
0x180093c31  lea     r8, [rsp+400h+var_388]
0x180093c36  mov     [rsp+400h+var_388], rax
0x180093c3b  mov     rax, [rsp+400h+var_3A8]
0x180093c40  mov     rcx, [rsp+400h+var_3A8]
0x180093c45  mov     edx, [rax+90h]
0x180093c4b  mov     rcx, [rcx+98h]
0x180093c52  call    MinAsn1ExtractContent
0x180093c57  test    eax, eax
0x180093c59  js      loc_180093B44
0x180093c5f  xor     r12d, r12d
0x180093c62  cmp     r12d, 2
0x180093c66  jnb     loc_180093EB8
0x180093c6c  mov     r13d, dword ptr [rsp+400h+var_388]
0x180093c71  xor     r15d, r15d
0x180093c74  mov     rcx, [rbp+300h+var_380]
0x180093c78  mov     [rbp+300h+var_370], rcx
0x180093c7c  test    r13d, r13d
0x180093c7f  jz      loc_180093E49
0x180093c85  mov     r14, [rsp+400h+var_3A8]
0x180093c8a  mov     edx, r13d
0x180093c8d  lea     r8, [r14+0B0h]
0x180093c94  call    MinAsn1ParseCTLSubject
0x180093c99  mov     [rsp+400h+var_3AC], eax
0x180093c9d  mov     ebx, eax
0x180093c9f  test    eax, eax
0x180093ca1  js      loc_180093EAA
0x180093ca7  mov     ecx, [r14+0D0h]
0x180093cae  cmp     ecx, 40h ; '@'
0x180093cb1  ja      loc_180093EAA
0x180093cb7  test    r12d, r12d
0x180093cba  jz      loc_180093E35
0x180093cc0  cmp     [rsp+400h+var_3B0], 0
0x180093cc5  jz      loc_180093E02
0x180093ccb  xor     edx, edx; Val
0x180093ccd  mov     [rsp+400h+var_398], 0Ah
0x180093cd5  mov     r8d, 320h; Size
0x180093cdb  lea     rcx, [rbp+300h+var_360]; void *
0x180093cdf  call    memset
0x180093ce4  lea     rcx, [r14+0E0h]
0x180093ceb  mov     [rbp+300h+var_378], 0
0x180093cf3  lea     r8, [rbp+300h+var_360]
0x180093cf7  mov     [rsp+400h+var_3AC], 0
0x180093cff  lea     rdx, [rsp+400h+var_398]
0x180093d04  call    MinAsn1ParseAttributes
0x180093d09  test    eax, eax
0x180093d0b  jle     loc_180093EAA
0x180093d11  mov     r10, cs:off_18002EE18
0x180093d18  xor     r8d, r8d
0x180093d1b  cmp     r8d, [rsp+400h+var_398]
0x180093d20  jnb     loc_180093EAA
0x180093d26  lea     rdx, [r8+r8*4]
0x180093d2a  shl     rdx, 4
0x180093d2e  cmp     [rbp+rdx+300h+var_340], 0Ah
0x180093d33  jnz     short loc_180093D54
0x180093d35  mov     r9, [rbp+rdx+300h+var_338]
0x180093d3a  mov     rcx, [r10]
0x180093d3d  sub     rcx, [r9]
0x180093d40  jnz     short loc_180093D4F
0x180093d42  movzx   ecx, word ptr [r10+8]
0x180093d47  movzx   eax, word ptr [r9+8]
0x180093d4c  sub     rcx, rax
0x180093d4f  test    rcx, rcx
0x180093d52  jz      short loc_180093DA0
0x180093d54  inc     r8d
0x180093d57  jmp     short loc_180093D1B
0x180093d59  cmp     dword ptr [rax+30h], 0Eh
0x180093d5d  jnz     loc_180093B44
0x180093d63  mov     rax, [rsp+400h+var_3A8]
0x180093d68  mov     rcx, cs:qword_180034C48
0x180093d6f  mov     r8, [rax+38h]
0x180093d73  sub     rcx, [r8]
0x180093d76  jnz     loc_180093C04
0x180093d7c  mov     ecx, cs:dword_180034C50
0x180093d82  mov     eax, [r8+8]
0x180093d86  sub     rcx, rax
0x180093d89  jnz     loc_180093C04
0x180093d8f  movzx   ecx, cs:word_180034C54
0x180093d96  movzx   eax, word ptr [r8+0Ch]
0x180093d9b  jmp     loc_180093C01
0x180093da0  lea     rcx, [rbp+300h+var_360]
0x180093da4  add     rcx, rdx
0x180093da7  jz      loc_180093EAA
0x180093dad  mov     edx, [rcx+40h]
0x180093db0  lea     r9, [rbp+300h+var_378]
0x180093db4  mov     rcx, [rcx+48h]
0x180093db8  lea     r8, [rsp+400h+var_3AC]
0x180093dbd  call    MinAsn1ExtractContent
0x180093dc2  test    eax, eax
0x180093dc4  js      loc_180093EAA
0x180093dca  cmp     [rsp+400h+var_3AC], 20h ; ' '
0x180093dcf  jnz     loc_180093EAA
0x180093dd5  mov     rcx, [rsi+8]
0x180093dd9  mov     eax, r15d
0x180093ddc  imul    rdx, rax, 44h ; 'D'
0x180093de0  mov     rax, [rbp+300h+var_378]
0x180093de4  movups  xmm0, xmmword ptr [rax]
0x180093de7  movups  xmmword ptr [rdx+rcx+4], xmm0
0x180093dec  movups  xmm1, xmmword ptr [rax+10h]
0x180093df0  movups  xmmword ptr [rdx+rcx+14h], xmm1
0x180093df5  mov     rax, [rsi+8]
0x180093df9  mov     dword ptr [rdx+rax], 20h ; ' '
0x180093e00  jmp     short loc_180093E35
0x180093e02  mov     rdx, [r14+0D8h]; Src
0x180093e09  mov     r8, rcx; Size
0x180093e0c  mov     rcx, [rsi+8]
0x180093e10  mov     eax, r15d
0x180093e13  add     rcx, 4
0x180093e17  imul    rbx, rax, 44h ; 'D'
0x180093e1b  add     rcx, rbx; void *
0x180093e1e  call    memmove
0x180093e23  mov     rcx, [rsi+8]
0x180093e27  mov     eax, [r14+0D0h]
0x180093e2e  mov     [rbx+rcx], eax
0x180093e31  mov     ebx, [rsp+400h+var_3AC]
0x180093e35  mov     rcx, [rbp+300h+var_370]
0x180093e39  sub     r13d, ebx
0x180093e3c  mov     eax, ebx
0x180093e3e  add     rcx, rax
0x180093e41  inc     r15d
0x180093e44  jmp     loc_180093C78
0x180093e49  test    r12d, r12d
0x180093e4c  jnz     short loc_180093EA2
0x180093e4e  test    r15d, r15d
0x180093e51  jz      short loc_180093EC1
0x180093e53  mov     ebx, 63734943h
0x180093e58  lea     edx, [r12+10h]
0x180093e5d  mov     r13d, 100h
0x180093e63  mov     r8d, ebx
0x180093e66  mov     ecx, r13d
0x180093e69  call    cs:__imp_ExAllocatePool2
0x180093e70  nop     dword ptr [rax+rax+00h]
0x180093e75  mov     rsi, rax
0x180093e78  test    rax, rax
0x180093e7b  jz      short loc_180093EB1
0x180093e7d  mov     [rax], r15d
0x180093e80  mov     r8d, ebx
0x180093e83  mov     eax, r15d
0x180093e86  mov     ecx, r13d
0x180093e89  imul    rdx, rax, 44h ; 'D'
0x180093e8d  call    cs:__imp_ExAllocatePool2
0x180093e94  nop     dword ptr [rax+rax+00h]
0x180093e99  mov     [rsi+8], rax
0x180093e9d  test    rax, rax
0x180093ea0  jz      short loc_180093EB1
0x180093ea2  inc     r12d
0x180093ea5  jmp     loc_180093C62
0x180093eaa  mov     edi, 0C0000428h
0x180093eaf  jmp     short loc_180093EC1
0x180093eb1  mov     edi, 0C0000017h
0x180093eb6  jmp     short loc_180093EC1
0x180093eb8  mov     rax, [rbp+300h+var_368]
0x180093ebc  mov     [rax], rsi
0x180093ebf  xor     esi, esi
0x180093ec1  mov     r14, [rsp+400h+var_3A0]
0x180093ec6  mov     rcx, [rsp+400h+P]; P
0x180093ecb  mov     r12d, 63734943h
0x180093ed1  mov     edx, r12d; Tag
0x180093ed4  call    cs:__imp_ExFreePoolWithTag
0x180093edb  nop     dword ptr [rax+rax+00h]
0x180093ee0  test    rsi, rsi
0x180093ee3  jz      short loc_180093F0F
0x180093ee5  mov     rcx, [rsi+8]; P
0x180093ee9  test    rcx, rcx
0x180093eec  jz      short loc_180093EFD
0x180093eee  mov     edx, r12d; Tag
0x180093ef1  call    cs:__imp_ExFreePoolWithTag
0x180093ef8  nop     dword ptr [rax+rax+00h]
0x180093efd  mov     edx, r12d; Tag
0x180093f00  mov     rcx, rsi; P
0x180093f03  call    cs:__imp_ExFreePoolWithTag
0x180093f0a  nop     dword ptr [rax+rax+00h]
0x180093f0f  test    edi, edi
0x180093f11  jns     short loc_180093F1B
0x180093f13  mov     rcx, r14
0x180093f16  call    MincryptFreePolicyInfo
0x180093f1b  mov     eax, edi
0x180093f1d  mov     rcx, [rbp+300h+var_40]
0x180093f24  xor     rcx, rsp; StackCookie
0x180093f27  call    __security_check_cookie
0x180093f2c  mov     rbx, [rsp+400h+arg_0]
0x180093f34  add     rsp, 3D0h
0x180093f3b  pop     r15
0x180093f3d  pop     r14
  ... truncated ...
```
