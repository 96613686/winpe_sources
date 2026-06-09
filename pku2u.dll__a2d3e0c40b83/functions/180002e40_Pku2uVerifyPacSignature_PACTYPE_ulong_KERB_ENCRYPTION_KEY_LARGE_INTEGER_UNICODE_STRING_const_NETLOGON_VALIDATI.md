# Pku2uVerifyPacSignature(_PACTYPE *,ulong,KERB_ENCRYPTION_KEY *,_LARGE_INTEGER *,_UNICODE_STRING const *,_NETLOGON_VALIDATION_SAM_INFO4 * *)

- ea: `0x180002e40`
- end: `0x1800036f8`
- name: `?Pku2uVerifyPacSignature@@YAJPEAU_PACTYPE@@KPEAUKERB_ENCRYPTION_KEY@@PEAT_LARGE_INTEGER@@PEBU_UNICODE_STRING@@PEAPEAU_NETLOGON_VALIDATION_SAM_INFO4@@@Z`
- size: `2232`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned int, struct KERB_ENCRYPTION_KEY *, union _LARGE_INTEGER *, const struct _UNICODE_STRING *, struct _NETLOGON_VALIDATION_SAM_INFO4 **)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001bf0`

## callees

- `0x180002e40`
- `0x180004270`
- `0x180004440`
- `0x1800057f0`
- `0x180018870`
- `0x18001e870`
- `0x1800210f0`
- `0x180021a54`
- `0x180023cb8`
- `0x18002b454`
- `0x18002b744`
- `0x18003af20`
- `0x18004466c`
- `0x1800449bc`
- `0x180044f8c`
- `0x180046010`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x180003418`
- `ntdll!RtlEqualUnicodeString` at `0x180003418`
- `cryptdll!CDLocateCheckSum` at `0x18000303e`
- `cryptdll!CDLocateCheckSum` at `0x18000303e`

## string_xrefs

- `0x180002ef5`: `onecore\ds\security\protocols\pku2u\token.cxx`
- `0x18000308c`: `onecore\ds\security\protocols\pku2u\token.cxx`
- `0x1800031f9`: `onecore\ds\security\protocols\pku2u\token.cxx`
- `0x18000335c`: `onecore\ds\security\protocols\pku2u\token.cxx`

## pseudocode

```c
__int64 __fastcall Pku2uVerifyPacSignature(
        unsigned __int64 a1,
        unsigned int a2,
        struct KERB_ENCRYPTION_KEY *a3,
        union _LARGE_INTEGER *a4,
        const struct _UNICODE_STRING *a5,
        struct _NETLOGON_VALIDATION_SAM_INFO4 **a6)
{
  __int64 v8; // r14
  char *v9; // rdx
  __int64 v10; // rax
  char *v11; // rcx
  int v12; // edi
  char *v14; // rdx
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int *v17; // r12
  unsigned int v18; // edi
  unsigned int i; // ecx
  unsigned __int64 v20; // rax
  __int64 (__fastcall *v21)(_QWORD, _QWORD, _BYTE *, __int64, __int64 *); // rax
  int v22; // eax
  __int64 (__fastcall *v23)(_QWORD, _QWORD, __int64, __int64 *); // rax
  int v24; // ecx
  char v25; // dl
  unsigned int v26; // r8d
  __int64 v27; // rax
  unsigned int v28; // r8d
  unsigned __int64 v29; // rax
  unsigned int v30; // r9d
  char *v31; // rcx
  unsigned int j; // edx
  char *v33; // r10
  unsigned int v34; // r11d
  unsigned int v35; // ecx
  __int64 v36; // rax
  char *v37; // rdx
  char *v38; // rcx
  unsigned __int64 v39; // rax
  __int64 v40; // rdx
  PCUNICODE_STRING v41; // rbx
  __int64 v42; // rsi
  __int128 *v43; // rax
  __int128 *v44; // rcx
  __int64 v45; // rdx
  unsigned int v46; // r15d
  _DWORD *v47; // r14
  __int128 v48; // xmm0
  __int128 v49; // xmm1
  __int128 v50; // xmm0
  __int128 v51; // xmm1
  __int128 v52; // xmm0
  __int128 v53; // xmm1
  __int128 v54; // xmm0
  __int128 v55; // xmm1
  bool v56; // zf
  __int128 v57; // xmm1
  int v58; // ecx
  _DWORD *v59; // rax
  int v60; // r12d
  __int64 k; // rdi
  void *DomainRelativeSid; // rax
  int v63; // eax
  int v64; // eax
  unsigned __int8 *v65; // rbx
  unsigned int m; // ebx
  void *v67; // rcx
  __int64 v68; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v69; // [rsp+48h] [rbp-B8h] BYREF
  UNICODE_STRING String2; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v71[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int8 *v72; // [rsp+68h] [rbp-98h] BYREF
  PCUNICODE_STRING String1; // [rsp+70h] [rbp-90h]
  _BYTE v74[4]; // [rsp+80h] [rbp-80h] BYREF
  char v75[164]; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v76; // [rsp+128h] [rbp+28h]
  unsigned int v77; // [rsp+190h] [rbp+90h]
  _DWORD *v78; // [rsp+198h] [rbp+98h]
  _BYTE v79[24]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v80[24]; // [rsp+278h] [rbp+178h] BYREF

  String1 = a5;
  v72 = (unsigned __int8 *)a4;
  v8 = a2;
  v68 = 0;
  v69 = 0;
  *a6 = 0;
  if ( !a1
    || (v9 = (char *)(a1 + 8),
        v10 = 16LL * *(unsigned int *)a1,
        v11 = (char *)(v10 + a1 + 8),
        *(_QWORD *)v71 = a1 + 8,
        a1 + 8 >= (unsigned __int64)v11) )
  {
LABEL_5:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)&WPP_c43b604716f332f766453d0e055ebcf6_Traceguids,
        (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\token.cxx",
        153);
    goto LABEL_8;
  }
  while ( *(_DWORD *)v9 != 1 )
  {
    v9 += 16;
    *(_QWORD *)v71 = v9;
    if ( v9 >= v11 )
      goto LABEL_5;
  }
  v14 = (char *)(a1 + 8);
  *(_QWORD *)&String2.Length = a1 + 8;
  do
  {
    if ( *(_DWORD *)v14 == 6 )
    {
      v15 = *((_DWORD *)v14 + 1);
      if ( v15 < 5 )
        return (unsigned int)-1073741811;
      v16 = v15 - 4;
      if ( v16 > 0x14 )
        return (unsigned int)-1073741811;
      v17 = (unsigned int *)*((_QWORD *)v14 + 1);
      v18 = v16;
      memcpy_0(v79, v17 + 1, v16);
      memset_0(v17 + 1, 0, v18);
      for ( i = 0; i < *(_DWORD *)a1; ++i )
      {
        v20 = *(_QWORD *)(a1 + 16 * (i + 1LL));
        if ( v20 > a1 + v8 || a1 > a1 + v8 )
          goto LABEL_76;
        *(_QWORD *)(a1 + 16 * (i + 1LL)) = (unsigned int)(v20 - a1);
      }
      v12 = CDLocateCheckSum(*v17, &v68);
      if ( v12 < 0 )
        goto LABEL_9;
      if ( *(_DWORD *)(v68 + 4) <= 0x14u )
      {
        if ( (unsigned int)(*(_DWORD *)v68 - 15) > 1 && *(_DWORD *)v68 != -138 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              15,
              (unsigned int)&WPP_c43b604716f332f766453d0e055ebcf6_Traceguids,
              (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\token.cxx",
              238);
          goto LABEL_34;
        }
        v21 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _BYTE *, __int64, __int64 *))(v68 + 56);
        if ( v21 )
        {
          v22 = v21(*((_QWORD *)a3 + 2), *((unsigned int *)a3 + 2), v79, 17, &v69);
        }
        else
        {
          v23 = *(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64 *))(v68 + 48);
          if ( !v23 )
          {
LABEL_34:
            v12 = -2146958526;
            goto LABEL_9;
          }
          v22 = v23(*((_QWORD *)a3 + 2), *((unsigned int *)a3 + 2), 17, &v69);
        }
        v12 = v22;
        if ( v22 < 0 )
          goto LABEL_9;
        v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int64))(v68 + 24))(v69, (unsigned int)v8, a1);
        if ( v12 < 0 )
          goto LABEL_9;
        v12 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(v68 + 32))(v69, v80);
        if ( v12 < 0 )
          goto LABEL_9;
        (*(void (__fastcall **)(__int64 *))(v68 + 40))(&v69);
        v69 = 0;
        v24 = *(_DWORD *)(v68 + 4);
        if ( v24 != *(_DWORD *)(*(_QWORD *)&String2.Length + 4LL) - 4 )
          return (unsigned int)-1073741715;
        v25 = 0;
        v26 = 0;
        if ( v24 )
        {
          do
          {
            v27 = v26++;
            v25 |= v79[v27] ^ v80[v27];
          }
          while ( v26 < *(_DWORD *)(v68 + 4) );
          if ( v25 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                16,
                (unsigned int)&WPP_c43b604716f332f766453d0e055ebcf6_Traceguids,
                (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\token.cxx",
                64);
LABEL_50:
            v12 = -1073741715;
            goto LABEL_9;
          }
        }
        if ( (unsigned int)v8 < 0x18 )
          goto LABEL_76;
        v28 = *(_DWORD *)a1;
        v29 = 16LL * *(unsigned int *)a1;
        if ( v29 > 0xFFFFFFFF
          || (int)v29 + 24 < (unsigned int)v29
          || (int)v29 + 24 > (unsigned int)v8
          || *(_DWORD *)(a1 + 4) )
        {
          goto LABEL_76;
        }
        v30 = 0;
        v31 = (char *)(a1 + v8);
        for ( j = 0; j < v28; ++j )
        {
          v33 = (char *)(a1 + *(_QWORD *)(a1 + 16LL * j + 16));
          if ( v33 > v31 )
            goto LABEL_76;
          if ( (unsigned __int64)v33 < a1 )
            goto LABEL_76;
          v34 = *(_DWORD *)(a1 + 16LL * j + 12);
          if ( v34 > (int)v31 - (int)v33 || v34 + v30 < v30 )
            goto LABEL_76;
          v30 += v34;
        }
        v35 = 0;
        if ( v28 )
        {
          do
          {
            v36 = v35++;
            *(_QWORD *)(16 * (v36 + 1) + a1) += a1;
          }
          while ( v35 < *(_DWORD *)a1 );
        }
        if ( !v30 )
          goto LABEL_76;
        v37 = (char *)(a1 + 8);
        v38 = (char *)(a1 + 16LL * *(unsigned int *)a1 + 8);
        if ( a1 + 8 >= (unsigned __int64)v38 )
        {
LABEL_69:
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_c43b604716f332f766453d0e055ebcf6_Traceguids);
          goto LABEL_50;
        }
        while ( *(_DWORD *)v37 != 10 )
        {
          v37 += 16;
          if ( v37 >= v38 )
            goto LABEL_69;
        }
        v39 = *((unsigned int *)v37 + 1);
        String2 = 0;
        if ( (unsigned int)v39 < 0xC )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_ddsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              17,
              (unsigned int)&WPP_c43b604716f332f766453d0e055ebcf6_Traceguids,
              v39,
              12,
              (__int64)"onecore\\ds\\security\\protocols\\pku2u\\token.cxx",
              97);
LABEL_76:
          v12 = -1073741595;
          goto LABEL_9;
        }
        v40 = *((_QWORD *)v37 + 1);
        if ( (unsigned __int64)*(unsigned __int16 *)(v40 + 8) + 6 > v39 )
        {
          v12 = -1073741595;
LABEL_9:
          if ( v69 )
          {
            if ( v68 )
              (*(void (__fastcall **)(__int64 *))(v68 + 40))(&v69);
          }
          return (unsigned int)v12;
        }
        if ( *(_QWORD *)v72 != *(_QWORD *)v40 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              18,
              (unsigned int)&WPP_c43b604716f332f766453d0e055ebcf6_Traceguids,
              (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\token.cxx",
              115);
          goto LABEL_50;
        }
        v41 = String1;
        String2.Buffer = (PWSTR)(v40 + 10);
        String2.MaximumLength = *(_WORD *)(v40 + 8);
        String2.Length = String2.MaximumLength;
        if ( !RtlEqualUnicodeString(String1, &String2, 1u) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_ZZsd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v41);
          goto LABEL_50;
        }
        *(_QWORD *)&String2.Length = 0;
        v12 = PAC_DecodeValidationInformation(
                *(unsigned __int8 **)(*(_QWORD *)v71 + 8LL),
                *(_DWORD *)(*(_QWORD *)v71 + 4LL),
                (struct _NETLOGON_VALIDATION_SAM_INFO3 **)&String2);
        if ( v12 >= 0 )
        {
          v12 = PacValidateInfo3(*(struct _NETLOGON_VALIDATION_SAM_INFO3 *const *)&String2.Length);
          if ( v12 < 0 )
          {
            Pku2uFree(*(void **)&String2.Length);
            *(_QWORD *)&String2.Length = 0;
            goto LABEL_114;
          }
        }
        if ( v12 >= 0 )
        {
          *(_DWORD *)(*(_QWORD *)&String2.Length + 168LL) &= ~0x40000u;
          v42 = *(_QWORD *)&String2.Length;
          memset_0(v75, 0, 0x1DCu);
          v43 = (__int128 *)v42;
          v44 = (__int128 *)v74;
          v45 = 2;
          v46 = 0;
          v47 = 0;
          do
          {
            v44 += 8;
            v48 = *v43;
            v49 = v43[1];
            v43 += 8;
            *(v44 - 8) = v48;
            v50 = *(v43 - 6);
            *(v44 - 7) = v49;
            v51 = *(v43 - 5);
            *(v44 - 6) = v50;
            v52 = *(v43 - 4);
            *(v44 - 5) = v51;
            v53 = *(v43 - 3);
            *(v44 - 4) = v52;
            v54 = *(v43 - 2);
            *(v44 - 3) = v53;
            v55 = *(v43 - 1);
            *(v44 - 2) = v54;
            *(v44 - 1) = v55;
            --v45;
          }
          while ( v45 );
          v56 = (*(_DWORD *)(v42 + 168) & 0x200) == 0;
          v57 = v43[1];
          *v44 = *v43;
          v44[1] = v57;
          if ( v56 || (v58 = *(_DWORD *)(v42 + 296)) == 0 )
          {
            v63 = v76;
          }
          else
          {
            v46 = v58 + *(_DWORD *)(v42 + 272);
            v59 = basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, 16LL * v46);
            v47 = v59;
            if ( !v59 )
            {
              v12 = -1073741670;
              goto LABEL_114;
            }
            memcpy_0(v59, *(const void **)(v42 + 280), 16LL * *(unsigned int *)(v42 + 272));
            v60 = *(_DWORD *)(v42 + 272);
            for ( k = 0; (unsigned int)k < *(_DWORD *)(v42 + 296); k = (unsigned int)(k + 1) )
            {
              v47[4 * v60 + 2] = *(_DWORD *)(8 * k + *(_QWORD *)(v42 + 304) + 4);
              DomainRelativeSid = PAC_MakeDomainRelativeSid(
                                    *(PSID *)(v42 + 288),
                                    *(_DWORD *)(8 * k + *(_QWORD *)(v42 + 304)));
              *(_QWORD *)&v47[4 * v60] = DomainRelativeSid;
              if ( !DomainRelativeSid )
              {
                v12 = -1073741670;
                goto LABEL_109;
              }
              ++v60;
            }
            v63 = v76 | 0x20;
            v77 = v46;
            v78 = v47;
          }
          v72 = 0;
          v76 = v63 & 0xFFFFFDFF;
          v71[0] = 0;
          v64 = PAC_EncodeValidationInformationEx((struct _NETLOGON_VALIDATION_SAM_INFO4 *)v74, &v72, v71);
          v65 = v72;
          v12 = v64;
          if ( v64 >= 0 )
            v12 = PAC_DecodeValidationInformationEx(v72, v71[0], a6);
          if ( v65 )
            Pku2uFree(v65);
          if ( v47 )
          {
LABEL_109:
            for ( m = *(_DWORD *)(v42 + 272); m < v46; ++m )
            {
              v67 = *(void **)&v47[4 * m];
              if ( v67 )
                Pku2uFree(v67);
            }
            Pku2uFree(v47);
          }
        }
LABEL_114:
        if ( *(_QWORD *)&String2.Length )
        {
          if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
            (*(void (**)(void))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 392LL))();
          else
            (*(void (**)(void))(*((_QWORD *)Pku2uGlobalBaseSSP + 31) + 8LL))();
        }
        goto LABEL_9;
      }
LABEL_8:
      v12 = -1073741811;
      goto LABEL_9;
    }
    v14 += 16;
    *(_QWORD *)&String2.Length = v14;
  }
  while ( (unsigned __int64)v14 < v10 + a1 + 8 );
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_c43b604716f332f766453d0e055ebcf6_Traceguids);
  return 3221225581LL;
}

```

## disassembly

```asm
0x180002e40  mov     [rsp-8+arg_18], rbx
0x180002e45  push    rbp
0x180002e46  push    rsi
0x180002e47  push    rdi
0x180002e48  push    r12
0x180002e4a  push    r13
0x180002e4c  push    r14
0x180002e4e  push    r15
0x180002e50  lea     rbp, [rsp-1A0h]
0x180002e58  sub     rsp, 2A0h
0x180002e5f  mov     rax, cs:__security_cookie
0x180002e66  xor     rax, rsp
0x180002e69  mov     [rbp+1D0h+var_40], rax
0x180002e70  mov     rax, [rbp+1D0h+arg_20]
0x180002e77  mov     r15, r8
0x180002e7a  mov     r13, [rbp+1D0h+arg_28]
0x180002e81  mov     rbx, rcx
0x180002e84  mov     [rsp+2D0h+String1], rax
0x180002e89  xor     eax, eax
0x180002e8b  mov     [rsp+2D0h+var_268], r9
0x180002e90  mov     r14d, edx
0x180002e93  mov     [rsp+2D0h+var_290], rax
0x180002e98  mov     [rsp+2D0h+var_288], rax
0x180002e9d  mov     [r13+0], rax
0x180002ea1  test    rcx, rcx
0x180002ea4  jz      short loc_180002ED8
0x180002ea6  mov     eax, [rcx]
0x180002ea8  lea     rdx, [rbx+8]
0x180002eac  shl     rax, 4
0x180002eb0  add     rcx, 8
0x180002eb4  add     rcx, rax
0x180002eb7  mov     qword ptr [rsp+2D0h+var_270], rdx
0x180002ebc  cmp     rdx, rcx
0x180002ebf  jnb     short loc_180002ED8
0x180002ec1  cmp     dword ptr [rdx], 1
0x180002ec4  jz      loc_180002F66
0x180002eca  add     rdx, 10h
0x180002ece  mov     qword ptr [rsp+2D0h+var_270], rdx
0x180002ed3  cmp     rdx, rcx
0x180002ed6  jb      short loc_180002EC1
0x180002ed8  mov     rcx, cs:WPP_GLOBAL_Control
0x180002edf  lea     rdx, WPP_GLOBAL_Control
0x180002ee6  cmp     rcx, rdx
0x180002ee9  jz      short loc_180002F15
0x180002eeb  test    byte ptr [rcx+1Ch], 1
0x180002eef  jz      short loc_180002F15
0x180002ef1  mov     rcx, [rcx+10h]
0x180002ef5  lea     r9, aOnecoreDsSecur_3; "onecore\\ds\\security\\protocols\\pku2u"...
0x180002efc  mov     edx, 0Dh
0x180002f01  mov     dword ptr [rsp+2D0h+var_2B0], 199h
0x180002f09  lea     r8, WPP_c43b604716f332f766453d0e055ebcf6_Traceguids
0x180002f10  call    WPP_SF_sd
0x180002f15  mov     edi, 0C000000Dh
0x180002f1a  cmp     [rsp+2D0h+var_288], 0
0x180002f20  jz      short loc_180002F3A
0x180002f22  mov     rax, [rsp+2D0h+var_290]
0x180002f27  test    rax, rax
0x180002f2a  jz      short loc_180002F3A
0x180002f2c  mov     rax, [rax+28h]
0x180002f30  lea     rcx, [rsp+2D0h+var_288]
0x180002f35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f3a  mov     eax, edi
0x180002f3c  mov     rcx, [rbp+1D0h+var_40]
0x180002f43  xor     rcx, rsp; StackCookie
0x180002f46  call    __security_check_cookie
0x180002f4b  mov     rbx, [rsp+2D0h+arg_18]
0x180002f53  add     rsp, 2A0h
0x180002f5a  pop     r15
0x180002f5c  pop     r14
0x180002f5e  pop     r13
0x180002f60  pop     r12
0x180002f62  pop     rdi
0x180002f63  pop     rsi
0x180002f64  pop     rbp
0x180002f65  retn
0x180002f66  lea     rcx, [rbx+8]
0x180002f6a  lea     rdx, [rbx+8]
0x180002f6e  add     rcx, rax
0x180002f71  mov     qword ptr [rsp+2D0h+String2.Length], rdx
0x180002f76  cmp     dword ptr [rdx], 6
0x180002f79  jz      short loc_180002FC1
0x180002f7b  add     rdx, 10h
0x180002f7f  mov     qword ptr [rsp+2D0h+String2.Length], rdx
0x180002f84  cmp     rdx, rcx
0x180002f87  jb      short loc_180002F76
0x180002f89  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f90  lea     rdx, WPP_GLOBAL_Control
0x180002f97  cmp     rcx, rdx
0x180002f9a  jz      short loc_180002FB7
0x180002f9c  test    byte ptr [rcx+1Ch], 1
0x180002fa0  jz      short loc_180002FB7
0x180002fa2  mov     rcx, [rcx+10h]
0x180002fa6  lea     r8, WPP_c43b604716f332f766453d0e055ebcf6_Traceguids
0x180002fad  mov     edx, 0Eh
0x180002fb2  call    WPP_SF_
0x180002fb7  mov     eax, 0C000006Dh
0x180002fbc  jmp     loc_180002F3C
0x180002fc1  mov     eax, [rdx+4]
0x180002fc4  cmp     eax, 5
0x180002fc7  jb      loc_1800036EE
0x180002fcd  add     eax, 0FFFFFFFCh
0x180002fd0  cmp     eax, 14h
0x180002fd3  ja      loc_1800036EE
0x180002fd9  mov     r12, [rdx+8]
0x180002fdd  lea     rcx, [rbp+1D0h+var_70]; void *
0x180002fe4  mov     r8d, eax; Size
0x180002fe7  mov     edi, eax
0x180002fe9  lea     rdx, [r12+4]; Src
0x180002fee  call    memcpy_0
0x180002ff3  mov     r8d, edi; Size
0x180002ff6  lea     rcx, [r12+4]; void *
0x180002ffb  xor     edx, edx; Val
0x180002ffd  call    memset_0
0x180003002  xor     ecx, ecx
0x180003004  cmp     ecx, [rbx]
0x180003006  jnb     short loc_180003035
0x180003008  mov     r8d, ecx
0x18000300b  lea     rdx, [rbx+r14]
0x18000300f  inc     r8
0x180003012  add     r8, r8
0x180003015  mov     rax, [rbx+r8*8]
0x180003019  cmp     rax, rdx
0x18000301c  ja      loc_18000338C
0x180003022  cmp     rbx, rdx
0x180003025  ja      loc_18000338C
0x18000302b  sub     eax, ebx
0x18000302d  mov     [rbx+r8*8], rax
0x180003031  inc     ecx
0x180003033  jmp     short loc_180003004
0x180003035  mov     ecx, [r12]
0x180003039  lea     rdx, [rsp+2D0h+var_290]
0x18000303e  call    cs:__imp_CDLocateCheckSum
0x180003044  mov     edi, eax
0x180003046  test    eax, eax
0x180003048  js      loc_180002F1A
0x18000304e  mov     rax, [rsp+2D0h+var_290]
0x180003053  cmp     dword ptr [rax+4], 14h
0x180003057  ja      loc_180002F15
0x18000305d  mov     ecx, [rax]
0x18000305f  lea     eax, [rcx-0Fh]
0x180003062  cmp     eax, 1
0x180003065  jbe     short loc_1800030B6
0x180003067  cmp     ecx, 0FFFFFF76h
0x18000306d  jz      short loc_1800030B6
0x18000306f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003076  lea     rdx, WPP_GLOBAL_Control
0x18000307d  cmp     rcx, rdx
0x180003080  jz      short loc_1800030AC
0x180003082  test    byte ptr [rcx+1Ch], 1
0x180003086  jz      short loc_1800030AC
0x180003088  mov     rcx, [rcx+10h]
0x18000308c  lea     r9, aOnecoreDsSecur_3; "onecore\\ds\\security\\protocols\\pku2u"...
0x180003093  mov     edx, 0Fh
0x180003098  mov     dword ptr [rsp+2D0h+var_2B0], 1EEh
0x1800030a0  lea     r8, WPP_c43b604716f332f766453d0e055ebcf6_Traceguids
0x1800030a7  call    WPP_SF_sd
0x1800030ac  mov     edi, 80080342h
0x1800030b1  jmp     loc_180002F1A
0x1800030b6  mov     rax, [rsp+2D0h+var_290]
0x1800030bb  mov     rax, [rax+38h]
0x1800030bf  test    rax, rax
0x1800030c2  jz      short loc_1800030EA
0x1800030c4  mov     edx, [r15+8]
0x1800030c8  lea     rcx, [rsp+2D0h+var_288]
0x1800030cd  mov     [rsp+2D0h+var_2B0], rcx
0x1800030d2  lea     r8, [rbp+1D0h+var_70]
0x1800030d9  mov     rcx, [r15+10h]
0x1800030dd  mov     r9d, 11h
0x1800030e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030e8  jmp     short loc_180003110
0x1800030ea  mov     rax, [rsp+2D0h+var_290]
0x1800030ef  mov     rax, [rax+30h]
0x1800030f3  test    rax, rax
0x1800030f6  jz      short loc_1800030AC
0x1800030f8  mov     edx, [r15+8]
0x1800030fc  lea     r9, [rsp+2D0h+var_288]
0x180003101  mov     rcx, [r15+10h]
0x180003105  mov     r8d, 11h
0x18000310b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003110  mov     edi, eax
0x180003112  test    eax, eax
0x180003114  js      loc_180002F1A
0x18000311a  mov     rax, [rsp+2D0h+var_290]
0x18000311f  mov     r8, rbx
0x180003122  mov     rcx, [rsp+2D0h+var_288]
0x180003127  mov     edx, r14d
0x18000312a  mov     rax, [rax+18h]
0x18000312e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003133  mov     edi, eax
0x180003135  test    eax, eax
0x180003137  js      loc_180002F1A
0x18000313d  mov     rax, [rsp+2D0h+var_290]
0x180003142  lea     rdx, [rbp+1D0h+var_58]
0x180003149  mov     rcx, [rsp+2D0h+var_288]
0x18000314e  mov     rax, [rax+20h]
0x180003152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003157  mov     edi, eax
0x180003159  test    eax, eax
0x18000315b  js      loc_180002F1A
0x180003161  mov     rax, [rsp+2D0h+var_290]
0x180003166  lea     rcx, [rsp+2D0h+var_288]
0x18000316b  mov     rax, [rax+28h]
0x18000316f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003174  mov     rax, [rsp+2D0h+var_290]
0x180003179  xor     r12d, r12d
0x18000317c  mov     [rsp+2D0h+var_288], r12
0x180003181  mov     ecx, [rax+4]
0x180003184  mov     rax, qword ptr [rsp+2D0h+String2.Length]
0x180003189  mov     eax, [rax+4]
0x18000318c  sub     eax, 4
0x18000318f  cmp     ecx, eax
0x180003191  jz      short loc_18000319D
0x180003193  mov     edi, 0C000006Dh
0x180003198  jmp     loc_180002F3A
0x18000319d  xor     dl, dl
0x18000319f  mov     r8d, r12d
0x1800031a2  test    ecx, ecx
0x1800031a4  jz      short loc_180003216
0x1800031a6  mov     eax, r8d
0x1800031a9  inc     r8d
0x1800031ac  movzx   ecx, [rbp+rax+1D0h+var_58]
0x1800031b4  movzx   eax, [rbp+rax+1D0h+var_70]
0x1800031bc  xor     cl, al
0x1800031be  mov     rax, [rsp+2D0h+var_290]
0x1800031c3  or      dl, cl
0x1800031c5  cmp     r8d, [rax+4]
0x1800031c9  jb      short loc_1800031A6
0x1800031cb  test    dl, dl
0x1800031cd  jz      short loc_180003216
0x1800031cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031d6  lea     rdx, WPP_GLOBAL_Control
0x1800031dd  cmp     rcx, rdx
0x1800031e0  jz      short loc_18000320C
0x1800031e2  test    byte ptr [rcx+1Ch], 1
0x1800031e6  jz      short loc_18000320C
0x1800031e8  mov     edx, 10h
0x1800031ed  mov     dword ptr [rsp+2D0h+var_2B0], 240h
0x1800031f5  mov     rcx, [rcx+10h]
0x1800031f9  lea     r9, aOnecoreDsSecur_3; "onecore\\ds\\security\\protocols\\pku2u"...
0x180003200  lea     r8, WPP_c43b604716f332f766453d0e055ebcf6_Traceguids
0x180003207  call    WPP_SF_sd
0x18000320c  mov     edi, 0C000006Dh
0x180003211  jmp     loc_180002F1A
0x180003216  cmp     r14d, 18h
0x18000321a  jb      loc_18000338C
0x180003220  mov     r8d, [rbx]
0x180003223  mov     ecx, 0FFFFFFFFh
0x180003228  mov     eax, r8d
0x18000322b  shl     rax, 4
0x18000322f  cmp     rax, rcx
0x180003232  ja      loc_18000338C
0x180003238  lea     ecx, [rax+18h]
0x18000323b  cmp     ecx, eax
0x18000323d  jb      loc_18000338C
0x180003243  cmp     ecx, r14d
0x180003246  ja      loc_18000338C
0x18000324c  cmp     [rbx+4], r12d
0x180003250  jnz     loc_18000338C
0x180003256  mov     r9d, r12d
0x180003259  lea     rcx, [rbx+r14]
0x18000325d  mov     edx, r12d
0x180003260  cmp     edx, r8d
0x180003263  jnb     short loc_1800032AC
0x180003265  mov     r11d, edx
0x180003268  add     r11, r11
0x18000326b  mov     r10, [rbx+r11*8+10h]
0x180003270  add     r10, rbx
0x180003273  cmp     r10, rcx
0x180003276  ja      loc_18000338C
0x18000327c  cmp     r10, rbx
0x18000327f  jb      loc_18000338C
0x180003285  mov     r11d, [rbx+r11*8+0Ch]
0x18000328a  mov     eax, ecx
0x18000328c  sub     eax, r10d
0x18000328f  cmp     r11d, eax
0x180003292  ja      loc_18000338C
0x180003298  lea     eax, [r11+r9]
0x18000329c  cmp     eax, r9d
0x18000329f  jb      loc_18000338C
0x1800032a5  mov     r9d, eax
0x1800032a8  inc     edx
0x1800032aa  jmp     short loc_180003260
0x1800032ac  mov     ecx, r12d
0x1800032af  test    r8d, r8d
0x1800032b2  jz      short loc_1800032C7
0x1800032b4  mov     eax, ecx
0x1800032b6  inc     ecx
0x1800032b8  inc     rax
0x1800032bb  shl     rax, 4
0x1800032bf  add     [rax+rbx], rbx
0x1800032c3  cmp     ecx, [rbx]
0x1800032c5  jb      short loc_1800032B4
0x1800032c7  test    r9d, r9d
0x1800032ca  jz      loc_18000338C
0x1800032d0  mov     ecx, [rbx]
0x1800032d2  lea     rdx, [rbx+8]
0x1800032d6  shl     rcx, 4
0x1800032da  add     rcx, 8
0x1800032de  add     rcx, rbx
0x1800032e1  cmp     rdx, rcx
  ... truncated ...
```
