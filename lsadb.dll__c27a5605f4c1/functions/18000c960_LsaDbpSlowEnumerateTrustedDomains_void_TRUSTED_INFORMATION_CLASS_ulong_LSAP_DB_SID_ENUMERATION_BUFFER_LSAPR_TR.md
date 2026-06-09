# LsaDbpSlowEnumerateTrustedDomains(void *,_TRUSTED_INFORMATION_CLASS,ulong,_LSAP_DB_SID_ENUMERATION_BUFFER *,_LSAPR_TRUST_INFORMATION * *)

- ea: `0x18000c960`
- end: `0x18000cc9c`
- name: `?LsaDbpSlowEnumerateTrustedDomains@@YAJPEAXW4_TRUSTED_INFORMATION_CLASS@@KPEAU_LSAP_DB_SID_ENUMERATION_BUFFER@@PEAPEAU_LSAPR_TRUST_INFORMATION@@@Z`
- size: `828`
- prototype: `__int64 __fastcall(void *, enum _TRUSTED_INFORMATION_CLASS, unsigned int, struct _LSAP_DB_SID_ENUMERATION_BUFFER *, struct _LSAPR_TRUST_INFORMATION **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x180001fb8`
- `0x18000c1ac`
- `0x18000c960`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c9f1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c9f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cbe9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cbe9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc85`
- `LSASRV!LsapDbCloseObject` at `0x18000caa4`
- `LSASRV!LsapDbCloseObject` at `0x18000caa4`
- `LSASRV!LsapDbReadAttribute` at `0x18000ca90`
- `LSASRV!LsapDbReadAttribute` at `0x18000ca90`
- `LSASRV!LsapDbCopyUnicodeAttribute` at `0x18000caf4`
- `LSASRV!LsapDbCopyUnicodeAttribute` at `0x18000cb0f`
- `LSASRV!LsapDbCopyUnicodeAttribute` at `0x18000cb63`
- `LSASRV!LsapDbCopyUnicodeAttribute` at `0x18000cb7e`
- `LSASRV!LsapDbCopyUnicodeAttribute` at `0x18000cbbe`
- `LSASRV!LsapDbCopyUnicodeAttribute` at `0x18000caf4`
- `LSASRV!LsapDbCopyUnicodeAttribute` at `0x18000cb0f`
- `LSASRV!LsapDbCopyUnicodeAttribute` at `0x18000cb63`
- `LSASRV!LsapDbCopyUnicodeAttribute` at `0x18000cb7e`
- `LSASRV!LsapDbCopyUnicodeAttribute` at `0x18000cbbe`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000ca69`
- `LSASRV!LsapDbInitializeAttribute` at `0x18000ca69`

## pseudocode

```c
__int64 __fastcall LsaDbpSlowEnumerateTrustedDomains(
        void *a1,
        enum _TRUSTED_INFORMATION_CLASS a2,
        unsigned int a3,
        struct _LSAP_DB_SID_ENUMERATION_BUFFER *a4,
        struct _LSAPR_TRUST_INFORMATION **a5)
{
  int Attribute; // edi
  int v9; // eax
  SIZE_T v10; // rdi
  char *v11; // rax
  char *v12; // rbx
  __int64 v13; // r12
  __int64 v14; // r14
  __int64 v15; // r8
  char *v16; // rsi
  __int64 v17; // r8
  char *v18; // rsi
  __int64 v19; // r8
  char *v20; // rcx
  __int64 v22; // rsi
  unsigned __int64 v23; // r14
  void *v24; // rcx
  void *v25; // rcx
  void *v26; // rcx
  void *v27; // rcx
  void *v28; // [rsp+30h] [rbp-30h] BYREF
  _QWORD v29[2]; // [rsp+38h] [rbp-28h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-18h]
  __int128 v31; // [rsp+50h] [rbp-10h]

  v28 = 0;
  v29[0] = 0;
  v29[1] = 0;
  hMem = 0;
  v31 = 0;
  switch ( a2 )
  {
    case TrustedDomainInformationBasic:
      v9 = 24;
      break;
    case TrustedDomainInformationEx:
      v9 = 56;
      break;
    case TrustedDomainInformationEx2Internal:
      v9 = 64;
      break;
    default:
      return (unsigned int)-1073741811;
  }
  v10 = a3 * v9;
  v11 = (char *)LocalAlloc(0x40u, v10);
  v12 = v11;
  if ( !v11 )
  {
    Attribute = -1073741670;
    goto LABEL_25;
  }
  memset_0(v11, 0, v10);
  v13 = 0;
  if ( a3 )
  {
    while ( 1 )
    {
      v14 = 8 * v13;
      Attribute = LsaDbpOpenTrustedDomain(a1, *(PSID *)(8 * v13 + *((_QWORD *)a4 + 1)), 0, &v28, 0x40u);
      if ( Attribute < 0 )
        break;
      LsapDbInitializeAttribute(v29, 31, 0);
      *((_QWORD *)&v31 + 1) = *(_QWORD *)((char *)LsaDbpDsAttInfo + 372);
      Attribute = LsapDbReadAttribute(v28, v29);
      LsapDbCloseObject(&v28, 256, (unsigned int)Attribute);
      v15 = 0;
      if ( Attribute < 0 )
        break;
      switch ( a2 )
      {
        case TrustedDomainInformationBasic:
          v20 = &v12[24 * v13];
          *((_QWORD *)v20 + 2) = *(_QWORD *)(v14 + *((_QWORD *)a4 + 1));
          *(_QWORD *)(v14 + *((_QWORD *)a4 + 1)) = 0;
          LOBYTE(v15) = 1;
          Attribute = LsapDbCopyUnicodeAttribute(v20, v29, v15);
          if ( Attribute < 0 )
            goto LABEL_28;
          break;
        case TrustedDomainInformationEx:
          v18 = &v12[56 * (unsigned int)v13];
          *((_QWORD *)v18 + 4) = *(_QWORD *)(v14 + *((_QWORD *)a4 + 1));
          *(_QWORD *)(v14 + *((_QWORD *)a4 + 1)) = 0;
          LOBYTE(v15) = 1;
          Attribute = LsapDbCopyUnicodeAttribute(v18, v29, v15);
          if ( Attribute < 0 )
            goto LABEL_28;
          LOBYTE(v19) = 1;
          Attribute = LsapDbCopyUnicodeAttribute(v18 + 16, v29, v19);
          if ( Attribute < 0 )
            goto LABEL_28;
          *((_DWORD *)v18 + 10) = 2;
          *(_QWORD *)(v18 + 44) = 1;
          break;
        case TrustedDomainInformationEx2Internal:
          v16 = &v12[64 * (unsigned __int64)(unsigned int)v13];
          *((_QWORD *)v16 + 4) = *(_QWORD *)(v14 + *((_QWORD *)a4 + 1));
          *(_QWORD *)(v14 + *((_QWORD *)a4 + 1)) = 0;
          LOBYTE(v15) = 1;
          Attribute = LsapDbCopyUnicodeAttribute(v16, v29, v15);
          if ( Attribute < 0 )
            goto LABEL_28;
          LOBYTE(v17) = 1;
          Attribute = LsapDbCopyUnicodeAttribute(v16 + 16, v29, v17);
          if ( Attribute < 0 )
            goto LABEL_28;
          *((_DWORD *)v16 + 10) = 2;
          *(_QWORD *)(v16 + 44) = 1;
          *((_DWORD *)v16 + 13) = 0;
          *((_QWORD *)v16 + 7) = 0;
          break;
      }
      v13 = (unsigned int)(v13 + 1);
      if ( (unsigned int)v13 >= a3 )
        goto LABEL_24;
    }
LABEL_28:
    v22 = 0;
    while ( a2 != TrustedDomainInformationBasic )
    {
      if ( a2 == TrustedDomainInformationEx )
      {
        v23 = 56LL * (unsigned int)v22;
LABEL_33:
        v24 = *(void **)&v12[v23 + 32];
        if ( v24 )
          LocalFree(v24);
        v25 = *(void **)&v12[v23 + 8];
        if ( v25 )
          LocalFree(v25);
        v26 = *(void **)&v12[v23 + 24];
LABEL_42:
        if ( v26 )
          LocalFree(v26);
        goto LABEL_44;
      }
      if ( a2 == TrustedDomainInformationEx2Internal )
      {
        v23 = (unsigned __int64)(unsigned int)v22 << 6;
        goto LABEL_33;
      }
LABEL_44:
      v22 = (unsigned int)(v22 + 1);
      if ( (unsigned int)v22 >= a3 )
      {
        LocalFree(v12);
        *(_DWORD *)a4 = 0;
        goto LABEL_25;
      }
    }
    v27 = *(void **)&v12[24 * v22 + 16];
    if ( v27 )
      LocalFree(v27);
    v26 = *(void **)&v12[24 * v22 + 8];
    goto LABEL_42;
  }
LABEL_24:
  Attribute = 0;
  *a5 = (struct _LSAPR_TRUST_INFORMATION *)v12;
LABEL_25:
  if ( hMem )
    LocalFree(hMem);
  return (unsigned int)Attribute;
}

```

## disassembly

```asm
0x18000c960  mov     rax, rsp
0x18000c963  mov     [rax+10h], rbx
0x18000c967  mov     [rax+20h], r9
0x18000c96b  mov     [rax+18h], r8d
0x18000c96f  mov     [rax+8], rcx
0x18000c973  push    rbp
0x18000c974  push    rsi
0x18000c975  push    rdi
0x18000c976  push    r12
0x18000c978  push    r13
0x18000c97a  push    r14
0x18000c97c  push    r15
0x18000c97e  mov     rbp, rsp
0x18000c981  sub     rsp, 60h
0x18000c985  mov     r13, r9
0x18000c988  mov     [rbp+var_30], 0
0x18000c990  mov     r9d, edx
0x18000c993  mov     [rbp+var_28], 0
0x18000c99b  mov     [rbp+var_20], 0
0x18000c9a3  xorps   xmm0, xmm0
0x18000c9a6  mov     [rbp+hMem], 0
0x18000c9ae  mov     esi, r8d
0x18000c9b1  mov     r15d, edx
0x18000c9b4  mov     ecx, 40h ; '@'; uFlags
0x18000c9b9  movdqu  [rbp+var_10], xmm0
0x18000c9be  sub     r9d, 5
0x18000c9c2  jz      short loc_18000C9E5
0x18000c9c4  sub     r9d, 1
0x18000c9c8  jz      short loc_18000C9DE
0x18000c9ca  cmp     r9d, 5
0x18000c9ce  jz      short loc_18000C9DA
0x18000c9d0  mov     edi, 0C000000Dh
0x18000c9d5  jmp     loc_18000CBEF
0x18000c9da  mov     eax, ecx
0x18000c9dc  jmp     short loc_18000C9EA
0x18000c9de  mov     eax, 38h ; '8'
0x18000c9e3  jmp     short loc_18000C9EA
0x18000c9e5  mov     eax, 18h
0x18000c9ea  imul    eax, esi
0x18000c9ed  mov     edx, eax; uBytes
0x18000c9ef  mov     edi, eax
0x18000c9f1  call    cs:__imp_LocalAlloc
0x18000c9f7  mov     rbx, rax
0x18000c9fa  test    rax, rax
0x18000c9fd  jnz     short loc_18000CA09
0x18000c9ff  mov     edi, 0C000009Ah
0x18000ca04  jmp     loc_18000CBE0
0x18000ca09  mov     r8, rdi; Size
0x18000ca0c  xor     edx, edx; Val
0x18000ca0e  mov     rcx, rbx; void *
0x18000ca11  call    memset_0
0x18000ca16  xor     r12d, r12d
0x18000ca19  test    esi, esi
0x18000ca1b  jz      loc_18000CBD7
0x18000ca21  mov     rdx, [r13+8]
0x18000ca25  lea     r14, ds:0[r12*8]
0x18000ca2d  mov     rcx, [rbp+arg_0]; void *
0x18000ca31  lea     r9, [rbp+var_30]; void **
0x18000ca35  xor     r8d, r8d; unsigned int
0x18000ca38  mov     esi, r12d
0x18000ca3b  mov     [rsp+60h+var_40], 40h ; '@'; unsigned int
0x18000ca43  mov     rdx, [r14+rdx]; Sid
0x18000ca47  call    ?LsaDbpOpenTrustedDomain@@YAJPEAX0KPEAPEAXK@Z; LsaDbpOpenTrustedDomain(void *,void *,ulong,void * *,ulong)
0x18000ca4c  mov     edi, eax
0x18000ca4e  test    eax, eax
0x18000ca50  js      loc_18000CC09
0x18000ca56  xor     r9d, r9d
0x18000ca59  mov     byte ptr [rsp+60h+var_40], 0
0x18000ca5e  xor     r8d, r8d
0x18000ca61  lea     rcx, [rbp+var_28]
0x18000ca65  lea     edx, [r9+1Fh]
0x18000ca69  call    cs:__imp_LsapDbInitializeAttribute
0x18000ca6f  mov     rcx, cs:?LsaDbpDsAttInfo@@3PEAU_LSAP_DB_DS_INFO@@EA; _LSAP_DB_DS_INFO * LsaDbpDsAttInfo
0x18000ca76  lea     rdx, [rbp+var_28]
0x18000ca7a  mov     eax, [rcx+174h]
0x18000ca80  mov     dword ptr [rbp+var_10+8], eax
0x18000ca83  mov     eax, [rcx+178h]
0x18000ca89  mov     rcx, [rbp+var_30]
0x18000ca8d  mov     dword ptr [rbp+var_10+0Ch], eax
0x18000ca90  call    cs:__imp_LsapDbReadAttribute
0x18000ca96  mov     edx, 100h
0x18000ca9b  lea     rcx, [rbp+var_30]
0x18000ca9f  mov     r8d, eax
0x18000caa2  mov     edi, eax
0x18000caa4  call    cs:__imp_LsapDbCloseObject
0x18000caaa  xor     r8d, r8d
0x18000caad  test    edi, edi
0x18000caaf  js      loc_18000CC09
0x18000cab5  mov     ecx, r15d
0x18000cab8  sub     ecx, 5
0x18000cabb  jz      loc_18000CB9B
0x18000cac1  sub     ecx, 1
0x18000cac4  jz      short loc_18000CB3E
0x18000cac6  cmp     ecx, 5
0x18000cac9  jnz     loc_18000CBCA
0x18000cacf  mov     rax, [r13+8]
0x18000cad3  lea     rdx, [rbp+var_28]
0x18000cad7  shl     rsi, 6
0x18000cadb  add     rsi, rbx
0x18000cade  mov     rcx, [r14+rax]
0x18000cae2  mov     [rsi+20h], rcx
0x18000cae6  mov     rcx, rsi
0x18000cae9  mov     rax, [r13+8]
0x18000caed  mov     [r14+rax], r8
0x18000caf1  mov     r8b, 1
0x18000caf4  call    cs:__imp_LsapDbCopyUnicodeAttribute
0x18000cafa  mov     edi, eax
0x18000cafc  test    eax, eax
0x18000cafe  js      loc_18000CC09
0x18000cb04  lea     rcx, [rsi+10h]
0x18000cb08  mov     r8b, 1
0x18000cb0b  lea     rdx, [rbp+var_28]
0x18000cb0f  call    cs:__imp_LsapDbCopyUnicodeAttribute
0x18000cb15  xor     r8d, r8d
0x18000cb18  mov     edi, eax
0x18000cb1a  test    eax, eax
0x18000cb1c  js      loc_18000CC09
0x18000cb22  mov     dword ptr [rsi+28h], 2
0x18000cb29  mov     qword ptr [rsi+2Ch], 1
0x18000cb31  mov     [rsi+34h], r8d
0x18000cb35  mov     [rsi+38h], r8
0x18000cb39  jmp     loc_18000CBCA
0x18000cb3e  mov     rax, [r13+8]
0x18000cb42  lea     rdx, [rbp+var_28]
0x18000cb46  imul    rsi, 38h ; '8'
0x18000cb4a  mov     rcx, [r14+rax]
0x18000cb4e  add     rsi, rbx
0x18000cb51  mov     [rsi+20h], rcx
0x18000cb55  mov     rcx, rsi
0x18000cb58  mov     rax, [r13+8]
0x18000cb5c  mov     [r14+rax], r8
0x18000cb60  mov     r8b, 1
0x18000cb63  call    cs:__imp_LsapDbCopyUnicodeAttribute
0x18000cb69  mov     edi, eax
0x18000cb6b  test    eax, eax
0x18000cb6d  js      loc_18000CC09
0x18000cb73  lea     rcx, [rsi+10h]
0x18000cb77  mov     r8b, 1
0x18000cb7a  lea     rdx, [rbp+var_28]
0x18000cb7e  call    cs:__imp_LsapDbCopyUnicodeAttribute
0x18000cb84  mov     edi, eax
0x18000cb86  test    eax, eax
0x18000cb88  js      short loc_18000CC09
0x18000cb8a  mov     dword ptr [rsi+28h], 2
0x18000cb91  mov     qword ptr [rsi+2Ch], 1
0x18000cb99  jmp     short loc_18000CBCA
0x18000cb9b  lea     rax, [r12+r12*2]
0x18000cb9f  lea     rcx, [rbx+rax*8]
0x18000cba3  mov     rax, [r13+8]
0x18000cba7  mov     rdx, [r14+rax]
0x18000cbab  mov     [rcx+10h], rdx
0x18000cbaf  lea     rdx, [rbp+var_28]
0x18000cbb3  mov     rax, [r13+8]
0x18000cbb7  mov     [r14+rax], r8
0x18000cbbb  mov     r8b, 1
0x18000cbbe  call    cs:__imp_LsapDbCopyUnicodeAttribute
0x18000cbc4  mov     edi, eax
0x18000cbc6  test    eax, eax
0x18000cbc8  js      short loc_18000CC09
0x18000cbca  inc     r12d
0x18000cbcd  cmp     r12d, [rbp+arg_10]
0x18000cbd1  jb      loc_18000CA21
0x18000cbd7  mov     rax, [rbp+arg_20]
0x18000cbdb  xor     edi, edi
0x18000cbdd  mov     [rax], rbx
0x18000cbe0  mov     rcx, [rbp+hMem]; hMem
0x18000cbe4  test    rcx, rcx
0x18000cbe7  jz      short loc_18000CBEF
0x18000cbe9  call    cs:__imp_LocalFree
0x18000cbef  mov     rbx, [rsp+60h+arg_8]
0x18000cbf7  mov     eax, edi
0x18000cbf9  add     rsp, 60h
0x18000cbfd  pop     r15
0x18000cbff  pop     r14
0x18000cc01  pop     r13
0x18000cc03  pop     r12
0x18000cc05  pop     rdi
0x18000cc06  pop     rsi
0x18000cc07  pop     rbp
0x18000cc08  retn
0x18000cc09  mov     r13d, [rbp+arg_10]
0x18000cc0d  xor     esi, esi
0x18000cc0f  mov     ecx, r15d
0x18000cc12  sub     ecx, 5
0x18000cc15  jz      short loc_18000CC57
0x18000cc17  sub     ecx, 1
0x18000cc1a  jz      short loc_18000CC4F
0x18000cc1c  cmp     ecx, 5
0x18000cc1f  jnz     short loc_18000CC7B
0x18000cc21  mov     r14d, esi
0x18000cc24  shl     r14, 6
0x18000cc28  mov     rcx, [r14+rbx+20h]; hMem
0x18000cc2d  test    rcx, rcx
0x18000cc30  jz      short loc_18000CC38
0x18000cc32  call    cs:__imp_LocalFree
0x18000cc38  mov     rcx, [r14+rbx+8]; hMem
0x18000cc3d  test    rcx, rcx
0x18000cc40  jz      short loc_18000CC48
0x18000cc42  call    cs:__imp_LocalFree
0x18000cc48  mov     rcx, [r14+rbx+18h]
0x18000cc4d  jmp     short loc_18000CC70
0x18000cc4f  mov     eax, esi
0x18000cc51  imul    r14, rax, 38h ; '8'
0x18000cc55  jmp     short loc_18000CC28
0x18000cc57  lea     r14, [rsi+rsi*2]
0x18000cc5b  mov     rcx, [rbx+r14*8+10h]; hMem
0x18000cc60  test    rcx, rcx
0x18000cc63  jz      short loc_18000CC6B
0x18000cc65  call    cs:__imp_LocalFree
0x18000cc6b  mov     rcx, [rbx+r14*8+8]; hMem
0x18000cc70  test    rcx, rcx
0x18000cc73  jz      short loc_18000CC7B
0x18000cc75  call    cs:__imp_LocalFree
0x18000cc7b  inc     esi
0x18000cc7d  cmp     esi, r13d
0x18000cc80  jb      short loc_18000CC0F
0x18000cc82  mov     rcx, rbx; hMem
0x18000cc85  call    cs:__imp_LocalFree
0x18000cc8b  mov     r13, [rbp+arg_18]
0x18000cc8f  mov     dword ptr [r13+0], 0
0x18000cc97  jmp     loc_18000CBE0
```
