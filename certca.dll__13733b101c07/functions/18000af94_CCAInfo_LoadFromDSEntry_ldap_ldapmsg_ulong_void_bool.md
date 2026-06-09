# CCAInfo::_LoadFromDSEntry(ldap *,ldapmsg *,ulong,void *,bool *)

- ea: `0x18000af94`
- end: `0x18000b3e7`
- name: `?_LoadFromDSEntry@CCAInfo@@IEAAJPEAUldap@@PEAUldapmsg@@KPEAXPEA_N@Z`
- size: `1107`
- prototype: `__int64 __fastcall(CCAInfo *this, struct ldap *, struct ldapmsg *, unsigned int, AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext, struct CCAProperty *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800370fc`

## callees

- `0x180008400`
- `0x18000af94`
- `0x18000ce90`
- `0x18000cfc0`
- `0x18000fac0`
- `0x1800115cc`
- `0x180012114`
- `0x180013a86`
- `0x180014fac`
- `0x180029ddc`

## import_xrefs

- `msvcrt!wcstoul` at `0x18000b006`
- `msvcrt!wcstoul` at `0x18000b006`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b1c1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b347`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b1c1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b347`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b16a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b16a`
- `CRYPT32!CertFreeCertificateContext` at `0x18000b3c7`
- `CRYPT32!CertFreeCertificateContext` at `0x18000b3c7`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18000b35b`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18000b382`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18000b35b`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18000b382`
- `WLDAP32!__imp_ldap_get_dnW` at `0x18000b09a`
- `WLDAP32!__imp_ldap_get_dnW` at `0x18000b09a`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000afe9`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000b156`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000afe9`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000b156`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x18000b332`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x18000b332`
- `WLDAP32!__imp_ldap_memfreeW` at `0x18000b0ca`
- `WLDAP32!__imp_ldap_memfreeW` at `0x18000b0ca`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000b019`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000b29e`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000b019`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000b29e`

## string_xrefs

- `0x18000b325`: `nTSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall CCAInfo::_LoadFromDSEntry(
        CCAInfo *this,
        struct ldap *a2,
        struct ldapmsg *a3,
        unsigned int a4,
        AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext,
        struct CCAProperty *a6)
{
  struct ldapmsg *v7; // rbp
  unsigned int v10; // r15d
  struct CCAProperty *v11; // rsi
  const wchar_t **valuesW; // rax
  PWCHAR *v13; // rbx
  char v14; // cl
  PWCHAR *v15; // r15
  unsigned int Error; // ebx
  unsigned int v17; // ecx
  int v18; // edx
  int v19; // eax
  const unsigned __int16 *dnW; // rax
  unsigned __int16 **v21; // rdx
  WCHAR *v22; // rbx
  const PWSTR *i; // r12
  PWCHAR **v24; // rax
  PWCHAR **v25; // rsi
  const unsigned __int16 *v26; // rcx
  unsigned __int64 v27; // rbx
  unsigned int v28; // r8d
  PWCHAR v29; // rax
  PWCHAR *v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // rbp
  PWCHAR *v33; // rax
  WCHAR *v34; // rdx
  int v35; // r11d
  unsigned __int64 v36; // rbx
  PWCHAR *j; // rbp
  __int64 v38; // rcx
  PWCHAR v39; // r9
  unsigned __int64 v40; // r8
  WCHAR *v41; // rax
  WCHAR v42; // r10
  WCHAR *v43; // rcx
  __int64 v44; // rax
  __int64 v45; // rax
  int v46; // eax
  struct berval **values_lenW; // rax
  struct berval **v48; // rsi
  HLOCAL v49; // rax
  PCCERT_CONTEXT pCertContext; // [rsp+20h] [rbp-58h] BYREF
  __int64 v52; // [rsp+28h] [rbp-50h]
  PWCHAR **v53; // [rsp+30h] [rbp-48h]
  unsigned int v55; // [rsp+98h] [rbp+20h]

  v7 = a3;
  v52 = 0;
  pCertContext = 0;
  LOBYTE(v10) = 0;
  v55 = 0;
  v11 = a6;
  *(_BYTE *)a6 = 0;
  valuesW = (const wchar_t **)ldap_get_valuesW(a2, a3, (const PWSTR)L"flags");
  v13 = (PWCHAR *)valuesW;
  if ( valuesW )
  {
    if ( *valuesW )
    {
      v10 = wcstoul(*valuesW, 0, 10);
      v55 = v10;
    }
    ldap_value_freeW(v13);
  }
  if ( (a4 & 0x40) != 0 )
  {
    v15 = 0;
  }
  else
  {
    v14 = v10;
    v15 = 0;
    if ( (v14 & 1) != 0 )
    {
      Error = -2147023727;
      v17 = 29623077;
LABEL_8:
      v18 = Error;
      goto LABEL_9;
    }
  }
  v19 = CCAInfo::_ValidateCaCertificate(a2, a4, v7, &pCertContext);
  Error = v19;
  if ( !v19 || (CSPrintErrorLineFile(0x1C80325u, v19), (a4 & 0x10) != 0) )
  {
    *(_QWORD *)this = pCertContext;
    pCertContext = 0;
    dnW = ldap_get_dnW(a2, v7);
    v22 = (WCHAR *)dnW;
    if ( dnW )
    {
      *((_QWORD *)this + 4) = CertAllocString(dnW);
      ldap_memfreeW(v22);
      if ( *((_QWORD *)this + 4) )
      {
        for ( i = (const PWSTR *)&g_awszCANamedProps; *(PWCHAR **)i != v15; ++i )
        {
          v24 = (PWCHAR **)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
          v25 = v24;
          v53 = v24;
          if ( v24 )
          {
            v26 = *i;
            *v24 = v15;
            v24[2] = v15;
            v24[1] = (PWCHAR *)CertAllocString(v26);
          }
          else
          {
            v25 = (PWCHAR **)v15;
          }
          a6 = (struct CCAProperty *)v25;
          if ( !v25 )
          {
            Error = -2147024882;
            v18 = -2147024882;
            v17 = 32768805;
            goto LABEL_9;
          }
          if ( v25[1] == v15 )
          {
            CCAProperty::DeleteChain(&a6);
            Error = -2147024882;
            v18 = -2147024882;
            v17 = 33293093;
            goto LABEL_9;
          }
          v15 = ldap_get_valuesW(a2, v7, *i);
          if ( *v25 )
          {
            LocalFree(*v25);
            *v25 = 0;
          }
          if ( v15 )
          {
            v27 = 0;
            v28 = 1;
            v29 = *v15;
            if ( *v15 )
            {
              v30 = v15;
              do
              {
                ++v28;
                v31 = -1;
                do
                  ++v31;
                while ( v29[v31] );
                v27 += 2 * v31 + 2;
                v29 = *++v30;
              }
              while ( *v30 );
            }
            v32 = v28;
            v33 = (PWCHAR *)LocalAlloc(0, v27 + 8LL * v28);
            *v25 = v33;
            if ( v33 )
            {
              v34 = (WCHAR *)&v33[v32];
              v35 = 0;
              v36 = v27 >> 1;
              for ( j = v15; *j; ++j )
              {
                (*v25)[v35] = v34;
                if ( v36 )
                {
                  if ( v36 <= 0x7FFFFFFF )
                  {
                    v38 = 2147483646;
                    v39 = *j;
                    v40 = v36;
                    v41 = v34;
                    do
                    {
                      if ( !v38 )
                        break;
                      v42 = *v39;
                      if ( *v39 == (_WORD)v52 )
                        break;
                      ++v39;
                      *v41++ = v42;
                      --v38;
                      --v40;
                    }
                    while ( v40 );
                    v43 = v41 - 1;
                    if ( v40 )
                      v43 = v41;
                    *v43 = 0;
                  }
                  else
                  {
                    *v34 = 0;
                  }
                }
                v44 = -1;
                do
                  ++v44;
                while ( v34[v44] );
                v45 = v44 + 1;
                v34 += v45;
                v36 -= v45;
                ++v35;
              }
              (*v25)[v35] = 0;
              Error = 0;
            }
            else
            {
              Error = -2147024882;
              CSPrintErrorLineFile(0x2010325u, -2147024882);
            }
            ldap_value_freeW(v15);
            v15 = 0;
            if ( Error )
              goto LABEL_55;
            v7 = a3;
          }
          v46 = CCAProperty::Append((struct CCAProperty **)this + 1, (struct CCAProperty *)v25);
          Error = v46;
          if ( v46 )
          {
            CSPrintErrorLineFile(0x20A0325u, v46);
LABEL_55:
            CCAProperty::DeleteChain(&a6);
            v17 = 34538277;
            goto LABEL_8;
          }
        }
        *((_DWORD *)this + 13) = v55;
        values_lenW = ldap_get_values_lenW(a2, v7, (const PWSTR)L"nTSecurityDescriptor");
        v48 = values_lenW;
        if ( values_lenW )
        {
          v49 = LocalAlloc(0, (*values_lenW)->bv_len);
          *((_QWORD *)this + 7) = v49;
          if ( !v49 )
          {
            Error = -2147024882;
            ldap_value_free_len(v48);
            v18 = -2147024882;
            v17 = 35652389;
            goto LABEL_9;
          }
          memcpy_0(v49, (*v48)->bv_val, (*v48)->bv_len);
          ldap_value_free_len(v48);
        }
        *((_DWORD *)this + 10) = (_DWORD)v15;
        *((_DWORD *)this + 18) = 1;
        if ( !(unsigned int)CAAccessCheckpEx(hAuthzClientContext, *((PSECURITY_DESCRIPTOR *)this + 7), 0x10001u, 0) )
          *((_DWORD *)this + 18) |= 2u;
        Error = (unsigned int)v15;
        goto LABEL_65;
      }
      Error = -2147024882;
      v18 = -2147024882;
      v17 = 31916837;
    }
    else
    {
      Error = myHLdapLastError(a2, v21);
      v18 = Error;
      v17 = 31130405;
    }
LABEL_9:
    CSPrintErrorLineFile(v17, v18);
    return Error;
  }
  *(_BYTE *)v11 = 1;
  CSPrintErrorLineFile(0x1CD0325u, Error);
LABEL_65:
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
  return Error;
}

```

## disassembly

```asm
0x18000af94  mov     [rsp+arg_0], rbx
0x18000af99  mov     [rsp+arg_10], r8
0x18000af9e  push    rbp
0x18000af9f  push    rsi
0x18000afa0  push    rdi
0x18000afa1  push    r12
0x18000afa3  push    r13
0x18000afa5  push    r14
0x18000afa7  push    r15
0x18000afa9  sub     rsp, 40h
0x18000afad  mov     edi, r9d
0x18000afb0  mov     rbp, r8
0x18000afb3  mov     r13, rdx
0x18000afb6  mov     r14, rcx
0x18000afb9  xor     r12d, r12d
0x18000afbc  mov     [rsp+78h+var_50], r12
0x18000afc1  mov     [rsp+78h+pCertContext], r12
0x18000afc6  mov     r15d, r12d
0x18000afc9  mov     [rsp+78h+arg_18], r12d
0x18000afd1  mov     rsi, [rsp+78h+arg_28]
0x18000afd9  mov     [rsi], r12b
0x18000afdc  lea     r8, attr; "flags"
0x18000afe3  mov     rdx, rbp; entry
0x18000afe6  mov     rcx, r13; ld
0x18000afe9  call    cs:__imp_ldap_get_valuesW
0x18000afef  mov     rbx, rax
0x18000aff2  test    rax, rax
0x18000aff5  jz      short loc_18000B01F
0x18000aff7  mov     rcx, [rax]; String
0x18000affa  test    rcx, rcx
0x18000affd  jz      short loc_18000B016
0x18000afff  xor     edx, edx; EndPtr
0x18000b001  lea     r8d, [r12+0Ah]; Radix
0x18000b006  call    cs:__imp_wcstoul
0x18000b00c  mov     r15d, eax
0x18000b00f  mov     [rsp+78h+arg_18], eax
0x18000b016  mov     rcx, rbx; vals
0x18000b019  call    cs:__imp_ldap_value_freeW
0x18000b01f  test    dil, 40h
0x18000b023  jnz     short loc_18000B046
0x18000b025  mov     ecx, r15d
0x18000b028  xor     r15d, r15d
0x18000b02b  test    cl, 1
0x18000b02e  jz      short loc_18000B049
0x18000b030  mov     ebx, 80070491h
0x18000b035  mov     ecx, 1C40325h; unsigned int
0x18000b03a  mov     edx, ebx; int
0x18000b03c  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000b041  jmp     loc_18000B3CD
0x18000b046  xor     r15d, r15d
0x18000b049  lea     r9, [rsp+78h+pCertContext]; struct _CERT_CONTEXT **
0x18000b04e  mov     r8, rbp; struct ldapmsg *
0x18000b051  mov     edx, edi; unsigned int
0x18000b053  mov     rcx, r13; struct ldap *
0x18000b056  call    ?_ValidateCaCertificate@CCAInfo@@KAJPEAUldap@@KPEAUldapmsg@@PEAPEBU_CERT_CONTEXT@@@Z; CCAInfo::_ValidateCaCertificate(ldap *,ulong,ldapmsg *,_CERT_CONTEXT const * *)
0x18000b05b  mov     ebx, eax
0x18000b05d  test    eax, eax
0x18000b05f  jz      short loc_18000B087
0x18000b061  mov     edx, eax; int
0x18000b063  mov     ecx, 1C80325h; unsigned int
0x18000b068  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000b06d  test    dil, 10h
0x18000b071  jnz     short loc_18000B087
0x18000b073  mov     byte ptr [rsi], 1
0x18000b076  mov     edx, ebx; int
0x18000b078  mov     ecx, 1CD0325h; unsigned int
0x18000b07d  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000b082  jmp     loc_18000B3BA
0x18000b087  mov     rax, [rsp+78h+pCertContext]
0x18000b08c  mov     [r14], rax
0x18000b08f  mov     [rsp+78h+pCertContext], r15
0x18000b094  mov     rdx, rbp; entry
0x18000b097  mov     rcx, r13; ld
0x18000b09a  call    cs:__imp_ldap_get_dnW
0x18000b0a0  mov     rbx, rax
0x18000b0a3  test    rax, rax
0x18000b0a6  jnz     short loc_18000B0BB
0x18000b0a8  mov     rcx, r13; struct ldap *
0x18000b0ab  call    ?myHLdapLastError@@YAJPEAUldap@@PEAPEAG@Z; myHLdapLastError(ldap *,ushort * *)
0x18000b0b0  mov     ebx, eax
0x18000b0b2  mov     edx, eax
0x18000b0b4  mov     ecx, 1DB0325h
0x18000b0b9  jmp     short loc_18000B03C
0x18000b0bb  mov     rcx, rbx; Src
0x18000b0be  call    ?CertAllocString@@YAPEAGPEBG@Z; CertAllocString(ushort const *)
0x18000b0c3  mov     [r14+20h], rax
0x18000b0c7  mov     rcx, rbx; Block
0x18000b0ca  call    cs:__imp_ldap_memfreeW
0x18000b0d0  mov     edi, 8007000Eh
0x18000b0d5  cmp     [r14+20h], r15
0x18000b0d9  jnz     short loc_18000B0E9
0x18000b0db  mov     ebx, edi
0x18000b0dd  mov     edx, edi
0x18000b0df  mov     ecx, 1E70325h
0x18000b0e4  jmp     loc_18000B03C
0x18000b0e9  lea     r12, ?g_awszCANamedProps@@3PAPEAGA; ushort * near * g_awszCANamedProps
0x18000b0f0  cmp     [r12], r15
0x18000b0f4  jz      loc_18000B31A
0x18000b0fa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b101  mov     ecx, 18h; unsigned __int64
0x18000b106  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b10b  mov     rsi, rax
0x18000b10e  mov     [rsp+78h+var_48], rax
0x18000b113  test    rax, rax
0x18000b116  jz      short loc_18000B12E
0x18000b118  mov     rcx, [r12]; Src
0x18000b11c  mov     [rax], r15
0x18000b11f  mov     [rax+10h], r15
0x18000b123  call    ?CertAllocString@@YAPEAGPEBG@Z; CertAllocString(ushort const *)
0x18000b128  mov     [rsi+8], rax
0x18000b12c  jmp     short loc_18000B131
0x18000b12e  mov     rsi, r15
0x18000b131  mov     [rsp+78h+arg_28], rsi
0x18000b139  test    rsi, rsi
0x18000b13c  jz      loc_18000B30C
0x18000b142  cmp     [rsi+8], r15
0x18000b146  jz      loc_18000B2F1
0x18000b14c  mov     r8, [r12]; attr
0x18000b150  mov     rdx, rbp; entry
0x18000b153  mov     rcx, r13; ld
0x18000b156  call    cs:__imp_ldap_get_valuesW
0x18000b15c  mov     r15, rax
0x18000b15f  mov     rcx, [rsi]; hMem
0x18000b162  xor     r9d, r9d
0x18000b165  test    rcx, rcx
0x18000b168  jz      short loc_18000B176
0x18000b16a  call    cs:__imp_LocalFree
0x18000b170  xor     r9d, r9d
0x18000b173  mov     [rsi], r9
0x18000b176  test    r15, r15
0x18000b179  jz      loc_18000B2B3
0x18000b17f  mov     rbx, r9
0x18000b182  mov     r8d, 1
0x18000b188  mov     rax, [r15]
0x18000b18b  test    rax, rax
0x18000b18e  jz      short loc_18000B1B8
0x18000b190  mov     rdx, r15
0x18000b193  inc     r8d
0x18000b196  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000b19a  inc     rcx
0x18000b19d  cmp     [rax+rcx*2], r9w
0x18000b1a2  jnz     short loc_18000B19A
0x18000b1a4  lea     rbx, [rbx+rcx*2]
0x18000b1a8  add     rbx, 2
0x18000b1ac  add     rdx, 8
0x18000b1b0  mov     rax, [rdx]
0x18000b1b3  test    rax, rax
0x18000b1b6  jnz     short loc_18000B193
0x18000b1b8  mov     ebp, r8d
0x18000b1bb  lea     rdx, [rbx+rbp*8]; uBytes
0x18000b1bf  xor     ecx, ecx; uFlags
0x18000b1c1  call    cs:__imp_LocalAlloc
0x18000b1c7  mov     [rsi], rax
0x18000b1ca  xor     r10d, r10d
0x18000b1cd  test    rax, rax
0x18000b1d0  jnz     short loc_18000B1E5
0x18000b1d2  mov     ebx, edi
0x18000b1d4  mov     edx, edi; int
0x18000b1d6  mov     ecx, 2010325h; unsigned int
0x18000b1db  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000b1e0  jmp     loc_18000B29B
0x18000b1e5  lea     rdx, [rax+rbp*8]
0x18000b1e9  mov     r11d, r10d
0x18000b1ec  shr     rbx, 1
0x18000b1ef  mov     rbp, r15
0x18000b1f2  cmp     [r15], r10
0x18000b1f5  jz      loc_18000B28E
0x18000b1fb  mov     ecx, r11d
0x18000b1fe  mov     rax, [rsi]
0x18000b201  mov     [rax+rcx*8], rdx
0x18000b205  test    rbx, rbx
0x18000b208  jz      short loc_18000B265
0x18000b20a  cmp     rbx, 7FFFFFFFh
0x18000b211  jbe     short loc_18000B219
0x18000b213  mov     [rdx], r10w
0x18000b217  jmp     short loc_18000B265
0x18000b219  mov     ecx, 7FFFFFFEh
0x18000b21e  mov     r9, [rbp+0]
0x18000b222  mov     r8, rbx
0x18000b225  mov     rax, rdx
0x18000b228  test    rcx, rcx
0x18000b22b  jz      short loc_18000B256
0x18000b22d  movzx   r10d, word ptr [r9]
0x18000b231  cmp     r10w, word ptr [rsp+78h+var_50]
0x18000b237  jz      short loc_18000B253
0x18000b239  add     r9, 2
0x18000b23d  mov     [rax], r10w
0x18000b241  add     rax, 2
0x18000b245  dec     rcx
0x18000b248  xor     r10d, r10d
0x18000b24b  sub     r8, 1
0x18000b24f  jnz     short loc_18000B228
0x18000b251  jmp     short loc_18000B256
0x18000b253  xor     r10d, r10d
0x18000b256  lea     rcx, [rax-2]
0x18000b25a  test    r8, r8
0x18000b25d  cmovnz  rcx, rax
0x18000b261  mov     [rcx], r10w
0x18000b265  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b269  inc     rax
0x18000b26c  cmp     [rdx+rax*2], r10w
0x18000b271  jnz     short loc_18000B269
0x18000b273  inc     rax
0x18000b276  lea     rdx, [rdx+rax*2]
0x18000b27a  sub     rbx, rax
0x18000b27d  inc     r11d
0x18000b280  add     rbp, 8
0x18000b284  cmp     [rbp+0], r10
0x18000b288  jnz     loc_18000B1FB
0x18000b28e  mov     ecx, r11d
0x18000b291  mov     rax, [rsi]
0x18000b294  mov     [rax+rcx*8], r10
0x18000b298  mov     ebx, r10d
0x18000b29b  mov     rcx, r15; vals
0x18000b29e  call    cs:__imp_ldap_value_freeW
0x18000b2a4  xor     r15d, r15d
0x18000b2a7  test    ebx, ebx
0x18000b2a9  jnz     short loc_18000B2DA
0x18000b2ab  mov     rbp, [rsp+78h+arg_10]
0x18000b2b3  lea     rcx, [r14+8]; struct CCAProperty **
0x18000b2b7  mov     rdx, rsi; struct CCAProperty *
0x18000b2ba  call    ?Append@CCAProperty@@SAJPEAPEAV1@PEAV1@@Z; CCAProperty::Append(CCAProperty * *,CCAProperty *)
0x18000b2bf  mov     ebx, eax
0x18000b2c1  test    eax, eax
0x18000b2c3  jnz     short loc_18000B2CE
0x18000b2c5  add     r12, 8
0x18000b2c9  jmp     loc_18000B0F0
0x18000b2ce  mov     edx, eax; int
0x18000b2d0  mov     ecx, 20A0325h; unsigned int
0x18000b2d5  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000b2da  lea     rcx, [rsp+78h+arg_28]; struct CCAProperty **
0x18000b2e2  call    ?DeleteChain@CCAProperty@@SAJPEAPEAV1@@Z; CCAProperty::DeleteChain(CCAProperty * *)
0x18000b2e7  mov     ecx, 20F0325h
0x18000b2ec  jmp     loc_18000B03A
0x18000b2f1  lea     rcx, [rsp+78h+arg_28]; struct CCAProperty **
0x18000b2f9  call    ?DeleteChain@CCAProperty@@SAJPEAPEAV1@@Z; CCAProperty::DeleteChain(CCAProperty * *)
0x18000b2fe  mov     ebx, edi
0x18000b300  mov     edx, edi
0x18000b302  mov     ecx, 1FC0325h
0x18000b307  jmp     loc_18000B03C
0x18000b30c  mov     ebx, edi
0x18000b30e  mov     edx, edi
0x18000b310  mov     ecx, 1F40325h
0x18000b315  jmp     loc_18000B03C
0x18000b31a  mov     eax, [rsp+78h+arg_18]
0x18000b321  mov     [r14+34h], eax
0x18000b325  lea     r8, aNtsecuritydesc; "nTSecurityDescriptor"
0x18000b32c  mov     rdx, rbp; Message
0x18000b32f  mov     rcx, r13; ExternalHandle
0x18000b332  call    cs:__imp_ldap_get_values_lenW
0x18000b338  mov     rsi, rax
0x18000b33b  test    rax, rax
0x18000b33e  jz      short loc_18000B388
0x18000b340  mov     rcx, [rax]
0x18000b343  mov     edx, [rcx]; uBytes
0x18000b345  xor     ecx, ecx; uFlags
0x18000b347  call    cs:__imp_LocalAlloc
0x18000b34d  mov     [r14+38h], rax
0x18000b351  test    rax, rax
0x18000b354  jnz     short loc_18000B36D
0x18000b356  mov     ebx, edi
0x18000b358  mov     rcx, rsi; vals
0x18000b35b  call    cs:__imp_ldap_value_free_len
0x18000b361  mov     edx, edi
0x18000b363  mov     ecx, 2200325h
0x18000b368  jmp     loc_18000B03C
0x18000b36d  mov     rdx, [rsi]
0x18000b370  mov     r8d, [rdx]; Size
0x18000b373  mov     rdx, [rdx+8]; Src
0x18000b377  mov     rcx, rax; void *
0x18000b37a  call    memcpy_0
0x18000b37f  mov     rcx, rsi; vals
0x18000b382  call    cs:__imp_ldap_value_free_len
0x18000b388  mov     [r14+28h], r15d
0x18000b38c  mov     dword ptr [r14+48h], 1
0x18000b394  xor     r9d, r9d; int
0x18000b397  mov     r8d, 10001h; unsigned int
0x18000b39d  mov     rdx, [r14+38h]; pSecurityDescriptor
0x18000b3a1  mov     rcx, [rsp+78h+hAuthzClientContext]; hAuthzClientContext
0x18000b3a9  call    ?CAAccessCheckpEx@@YAJPEAX0KH@Z; CAAccessCheckpEx(void *,void *,ulong,int)
0x18000b3ae  test    eax, eax
0x18000b3b0  jnz     short loc_18000B3B7
0x18000b3b2  or      dword ptr [r14+48h], 2
0x18000b3b7  mov     ebx, r15d
0x18000b3ba  mov     rbp, [rsp+78h+pCertContext]
0x18000b3bf  test    rbp, rbp
0x18000b3c2  jz      short loc_18000B3CD
0x18000b3c4  mov     rcx, rbp; pCertContext
0x18000b3c7  call    cs:__imp_CertFreeCertificateContext
0x18000b3cd  mov     eax, ebx
0x18000b3cf  mov     rbx, [rsp+78h+arg_0]
0x18000b3d7  add     rsp, 40h
0x18000b3db  pop     r15
0x18000b3dd  pop     r14
0x18000b3df  pop     r13
0x18000b3e1  pop     r12
0x18000b3e3  pop     rdi
0x18000b3e4  pop     rsi
0x18000b3e5  pop     rbp
0x18000b3e6  retn
  ... truncated ...
```
