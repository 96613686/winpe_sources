# Pku2uHandlePeer2PeerAsReply(_PKU2U_CONTEXT *,ulong,uchar *)

- ea: `0x1800355cc`
- end: `0x180035db8`
- name: `?Pku2uHandlePeer2PeerAsReply@@YAJPEAU_PKU2U_CONTEXT@@KPEAE@Z`
- size: `2028`
- prototype: `__int64 __fastcall(struct _PKU2U_CONTEXT *, DWORD, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `23`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001cc90`

## callees

- `0x1800057f0`
- `0x180007800`
- `0x180007dc8`
- `0x180014e30`
- `0x180015190`
- `0x1800160e0`
- `0x180016a10`
- `0x180018f50`
- `0x18001a1d0`
- `0x1800210f0`
- `0x180023cb8`
- `0x180023ce0`
- `0x180023d9c`
- `0x18002b454`
- `0x180030548`
- `0x1800313c8`
- `0x180031968`
- `0x180031ea0`
- `0x1800355cc`
- `0x1800370d0`
- `0x180037468`
- `0x18003b28c`
- `0x180046010`

## import_xrefs

- `ntdll!NtQuerySystemTime` at `0x180035ab7`
- `ntdll!NtQuerySystemTime` at `0x180035ab7`
- `CRYPT32!CertFreeCertificateContext` at `0x180035cdc`
- `CRYPT32!CertFreeCertificateContext` at `0x180035cdc`
- `CRYPT32!CertCloseStore` at `0x180035cce`
- `CRYPT32!CertCloseStore` at `0x180035cce`
- `ext-ms-win-security-certpoleng-l1-1-0!IntPstValidate` at `0x1800358aa`
- `ext-ms-win-security-certpoleng-l1-1-0!IntPstValidate` at `0x1800358aa`

## string_xrefs

- `0x1800359fe`: `onecore\ds\security\protocols\pku2u\pkauth.cxx`
- `0x180035bea`: `onecore\ds\security\protocols\pku2u\pkauth.cxx`

## pseudocode

```c
__int64 __fastcall Pku2uHandlePeer2PeerAsReply(struct _PKU2U_CONTEXT *a1, DWORD a2, unsigned __int8 *a3)
{
  const CERT_CONTEXT *QuadPart; // r12
  int inited; // ebx
  int v7; // eax
  int v8; // ecx
  int TicketCacheEntry; // eax
  __int64 v10; // r15
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  struct KERB_PA_DATA *PreAuthDataEntry; // rax
  int v16; // r8d
  int v17; // r14d
  unsigned int v18; // r14d
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9
  int v22; // ebx
  int v23; // r8d
  int v24; // r9d
  HCRYPTKEY v25; // rcx
  void *v26; // r9
  unsigned int v27; // ebx
  bool v28; // zf
  int Key; // eax
  unsigned int v30; // r8d
  int v31; // r9d
  int v32; // r8d
  __int64 v33; // rcx
  union _LARGE_INTEGER SystemTime; // [rsp+50h] [rbp-89h] BYREF
  union _LARGE_INTEGER Time; // [rsp+58h] [rbp-81h] BYREF
  void *v37; // [rsp+60h] [rbp-79h] BYREF
  struct KERB_KDC_REPLY *v38; // [rsp+68h] [rbp-71h] BYREF
  int v39; // [rsp+70h] [rbp-69h] BYREF
  void *v40; // [rsp+78h] [rbp-61h] BYREF
  struct KERB_ENCRYPTED_KDC_REPLY *v41; // [rsp+80h] [rbp-59h] BYREF
  __int64 v42; // [rsp+88h] [rbp-51h] BYREF
  HCERTSTORE hCertStore; // [rsp+90h] [rbp-49h] BYREF
  struct _CRYPTOAPI_BLOB v44; // [rsp+98h] [rbp-41h] BYREF
  unsigned __int8 *v45; // [rsp+A8h] [rbp-31h] BYREF
  unsigned __int8 *v46[2]; // [rsp+B0h] [rbp-29h] BYREF
  __int128 v47; // [rsp+C0h] [rbp-19h] BYREF
  __int64 v48; // [rsp+D0h] [rbp-9h]
  struct _CRYPTOAPI_BLOB v49; // [rsp+D8h] [rbp-1h] BYREF
  __int128 v50; // [rsp+E8h] [rbp+Fh] BYREF

  Time.LowPart = a2;
  v45 = a3;
  v39 = 0;
  v37 = 0;
  v41 = 0;
  SystemTime.QuadPart = 0;
  QuadPart = 0;
  v40 = 0;
  *(_OWORD *)v46 = 0;
  v38 = 0;
  v44 = 0;
  *(&v49.cbData + 1) = 0;
  v47 = 0;
  v48 = 0;
  hCertStore = 0;
  v50 = 0;
  v42 = 0;
  if ( !Pku2uGlobalDHInitialized )
  {
    inited = Pku2uInitDH();
    if ( inited < 0 )
      goto LABEL_87;
  }
  if ( !(unsigned int)g_verify_token_header(a1, (int *)&Time, &v45, 1536, a2) )
  {
    inited = 280;
    goto LABEL_87;
  }
  v7 = KerbUnpackData(v45, Time.LowPart, 0x2Bu, (void **)&v38);
  if ( v7 )
    goto LABEL_6;
  v10 = *((_QWORD *)a1 + 2);
  if ( *(_DWORD *)(v10 + 32) )
  {
    v10 = *((_QWORD *)a1 + 4);
    if ( !v10 )
    {
      inited = -2146893042;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 39;
LABEL_13:
        WPP_SF_(v11[2], v12, &WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids);
        goto LABEL_87;
      }
      goto LABEL_87;
    }
  }
  if ( *(char *)v38 >= 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_19;
    v14 = 40;
    goto LABEL_18;
  }
  PreAuthDataEntry = KerbFindPreAuthDataEntry(0x11u, *((struct KERB_KDC_REQUEST_preauth_data **)v38 + 2));
  if ( !PreAuthDataEntry )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_19;
    v14 = 41;
    goto LABEL_18;
  }
  v7 = KerbUnpackData(*((unsigned __int8 **)PreAuthDataEntry + 2), *((_DWORD *)PreAuthDataEntry + 2), 0x26u, &v37);
  if ( v7 )
  {
LABEL_6:
    v8 = v7;
LABEL_7:
    TicketCacheEntry = KerbMapKerbError(v8);
LABEL_86:
    inited = TicketCacheEntry;
    goto LABEL_87;
  }
  if ( *(_WORD *)v37 != 1 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_19;
    v14 = 42;
    goto LABEL_18;
  }
  inited = ScHelperVerifyPkcsMessage(
             *((BYTE **)v37 + 3),
             *((_DWORD *)v37 + 4),
             v16,
             "1.3.6.1.5.2.3.2",
             &v46[1],
             (unsigned int *)v46,
             (const struct _CERT_CONTEXT **)&SystemTime,
             &hCertStore,
             0);
  if ( inited < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        &WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids,
        (unsigned int)inited);
    QuadPart = (const CERT_CONTEXT *)SystemTime.QuadPart;
    goto LABEL_87;
  }
  QuadPart = (const CERT_CONTEXT *)SystemTime.QuadPart;
  if ( SystemTime.QuadPart )
  {
    inited = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))IntPstValidate)(
               (char *)a1 + 88,
               0,
               &hCertStore,
               (union _LARGE_INTEGER)SystemTime.QuadPart,
               &v50,
               &v39);
    if ( inited < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_DZ(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a1 + 88);
      goto LABEL_87;
    }
    v17 = *((_DWORD *)a1 + 16);
    if ( v39 )
      v18 = v17 & 0xFFFFFFFD;
    else
      v18 = v17 | 2;
    inited = (*((__int64 (__fastcall **)(__int128 *, __int64, const CERT_CONTEXT *, __int64 *))Pku2uGlobalIdpExtTable + 1))(
               &v50,
               1,
               QuadPart,
               &v42);
    if ( inited < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_87;
      v20 = 46;
      v21 = (unsigned int)inited;
      goto LABEL_49;
    }
    v22 = KerbUnpackData(v46[1], (unsigned int)v46[0], 0xFu, &v40);
    if ( v22 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids);
      goto LABEL_54;
    }
    v23 = *((_DWORD *)a1 + 42);
    v24 = *((_DWORD *)v40 + 6);
    if ( v23 != v24 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_ddsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          48,
          (unsigned int)&WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids,
          v24,
          v23,
          (__int64)"onecore\\ds\\security\\protocols\\pku2u\\pkauth.cxx",
          118);
      goto LABEL_19;
    }
    v25 = *((_QWORD *)a1 + 15);
    v49.cbData = *((_DWORD *)v40 + 2) >> 3;
    v49.pbData = (BYTE *)*((_QWORD *)v40 + 2);
    if ( !(unsigned int)Pku2uGetSharedKey(v25, &v49, &v44) )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_19;
      v14 = 49;
      goto LABEL_18;
    }
    v26 = v37;
    v27 = *((_DWORD *)v38 + 31);
    v28 = *((_BYTE *)v37 + 8) >= 0;
    LODWORD(v47) = v27;
    if ( v28 )
    {
      Key = KerbMakeKeyEx(v27, 0, 0, 0, 0, v44.cbData, v44.pbData, (struct KERB_ENCRYPTION_KEY *)&v47);
    }
    else
    {
      if ( *(char *)v40 < 0 )
      {
        Time.QuadPart = 0;
        SystemTime.QuadPart = 0;
        KerbConvertGeneralizedTimeToLargeInt(&Time, (struct tagASN1generalizedtime_t *)((char *)v40 + 28), 0);
        NtQuerySystemTime(&SystemTime);
        SystemTime.QuadPart += *((_QWORD *)a1 + 20);
        if ( Time.QuadPart + Pku2uGlobalSkewTime.QuadPart < SystemTime.QuadPart )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_19;
          v14 = 50;
LABEL_18:
          WPP_SF_(v13[2], v14, &WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids);
          goto LABEL_19;
        }
        v26 = v37;
      }
      Key = KerbMakeKeyEx(
              v27,
              0x20u,
              (unsigned __int8 *)a1 + 128,
              *((_DWORD *)v26 + 8),
              *((unsigned __int8 **)v26 + 5),
              v44.cbData,
              v44.pbData,
              (struct KERB_ENCRYPTION_KEY *)&v47);
    }
    if ( Key )
    {
      inited = KerbMapKerbError(Key);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_87;
      v20 = 51;
LABEL_49:
      WPP_SF_d(v19[2], v20, &WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids, v21);
      goto LABEL_87;
    }
    v22 = KerbUnpackKdcReplyBody(
            (struct KERB_KDC_REPLY *)((char *)v38 + 120),
            (struct KERB_ENCRYPTION_KEY *)&v47,
            v30,
            &v41);
    if ( !v22 )
    {
      v31 = *((_DWORD *)a1 + 42);
      v32 = *((_DWORD *)v41 + 10);
      if ( v31 == v32 )
      {
        TicketCacheEntry = Pku2uCreateTicketCacheEntry(
                             v38,
                             v41,
                             (int)*((_QWORD *)a1 + 20) / 10000000,
                             v18,
                             (PRTL_CRITICAL_SECTION)(v10 + 40),
                             (union _LARGE_INTEGER)((char *)a1 + 176));
        goto LABEL_86;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_ddsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          53,
          (unsigned int)&WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids,
          v31,
          v32,
          (__int64)"onecore\\ds\\security\\protocols\\pku2u\\pkauth.cxx",
          231);
LABEL_19:
      inited = -1073741715;
      goto LABEL_87;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52,
        (unsigned int)&WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids,
        v22,
        (__int64)"onecore\\ds\\security\\protocols\\pku2u\\pkauth.cxx",
        217);
LABEL_54:
    v8 = v22;
    goto LABEL_7;
  }
  inited = -1073741715;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v12 = SystemTime.LowPart + 44;
    goto LABEL_13;
  }
LABEL_87:
  if ( v37 )
    KerbFreeData(0x26u, v37);
  if ( hCertStore )
    CertCloseStore(hCertStore, 0);
  if ( QuadPart )
    CertFreeCertificateContext(QuadPart);
  if ( v40 )
    KerbFreeData(0xFu, v40);
  if ( v44.pbData )
    Pku2uFree(v44.pbData);
  if ( v46[1] )
    ScHelperFree(v46[1]);
  KerbFreeData(0x2Eu, v41);
  KerbFreeData(0x2Bu, v38);
  KerbFreeKey((struct KERB_ENCRYPTION_KEY *)&v47);
  v33 = v42;
  if ( v42 )
  {
    if ( *(_QWORD *)(v42 + 8) )
    {
      ((void (__fastcall *)(_QWORD))Pku2uGlobalLsaFunctions->FreeLsaHeap)(*(_QWORD *)(v42 + 8));
      v33 = v42;
    }
    if ( *(_QWORD *)(v33 + 16) )
    {
      ((void (__fastcall *)(_QWORD))Pku2uGlobalLsaFunctions->FreeLsaHeap)(*(_QWORD *)(v33 + 16));
      v33 = v42;
    }
    ((void (__fastcall *)(__int64))Pku2uGlobalLsaFunctions->FreeLsaHeap)(v33);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800355cc  mov     [rsp-8+arg_18], rbx
0x1800355d1  push    rbp
0x1800355d2  push    rsi
0x1800355d3  push    rdi
0x1800355d4  push    r12
0x1800355d6  push    r13
0x1800355d8  push    r14
0x1800355da  push    r15
0x1800355dc  lea     rbp, [rsp-27h]
0x1800355e1  sub     rsp, 100h
0x1800355e8  mov     rax, cs:__security_cookie
0x1800355ef  xor     rax, rsp
0x1800355f2  mov     [rbp+57h+var_38], rax
0x1800355f6  xor     r13d, r13d
0x1800355f9  mov     dword ptr [rsp+130h+Time], edx
0x1800355fd  xorps   xmm0, xmm0
0x180035600  mov     [rbp+57h+var_88], r8
0x180035604  xor     eax, eax
0x180035606  mov     [rbp+57h+var_C0], r13d
0x18003560a  cmp     cs:?Pku2uGlobalDHInitialized@@3HA, r13d; int Pku2uGlobalDHInitialized
0x180035611  xorps   xmm1, xmm1
0x180035614  lea     r14d, [r13+2Bh]
0x180035618  mov     [rbp+57h+var_D0], r13
0x18003561c  mov     edi, edx
0x18003561e  mov     [rbp+57h+var_B0], r13
0x180035622  mov     rsi, rcx
0x180035625  mov     qword ptr [rsp+130h+SystemTime], r13
0x18003562a  mov     r12d, r13d
0x18003562d  mov     [rbp+57h+var_B8], r13
0x180035631  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x180035635  mov     [rbp+57h+var_C8], r13
0x180035639  movups  xmmword ptr [rbp+57h+var_98.cbData], xmm1
0x18003563d  mov     dword ptr [rbp+57h+var_58+4], r13d
0x180035641  movups  [rbp+57h+var_70], xmm0
0x180035645  mov     [rbp+57h+var_60], rax
0x180035649  mov     [rbp+57h+hCertStore], r13
0x18003564d  movups  [rbp+57h+var_48], xmm0
0x180035651  mov     [rbp+57h+var_A8], r13
0x180035655  jnz     short loc_180035666
0x180035657  call    ?Pku2uInitDH@@YAJXZ; Pku2uInitDH(void)
0x18003565c  mov     ebx, eax
0x18003565e  test    eax, eax
0x180035660  js      loc_180035CAD
0x180035666  mov     r9d, 600h; int
0x18003566c  mov     dword ptr [rsp+130h+CriticalSection], edi; int
0x180035670  lea     r8, [rbp+57h+var_88]; unsigned __int8 **
0x180035674  lea     rdx, [rsp+130h+Time]; int *
0x180035679  call    ?g_verify_token_header@@YAHPEAUgss_OID_desc_struct@@PEAHPEAPEAEHH@Z; g_verify_token_header(gss_OID_desc_struct *,int *,uchar * *,int,int)
0x18003567e  test    eax, eax
0x180035680  jnz     short loc_18003568C
0x180035682  mov     ebx, 118h
0x180035687  jmp     loc_180035CAD
0x18003568c  mov     edx, dword ptr [rsp+130h+Time]; unsigned int
0x180035690  lea     r9, [rbp+57h+var_C8]; void **
0x180035694  mov     rcx, [rbp+57h+var_88]; unsigned __int8 *
0x180035698  mov     r8d, r14d; unsigned int
0x18003569b  call    ?KerbUnpackData@@YAJPEAEKKPEAPEAX@Z; KerbUnpackData(uchar *,ulong,ulong,void * *)
0x1800356a0  test    eax, eax
0x1800356a2  jz      short loc_1800356B0
0x1800356a4  mov     ecx, eax; int
0x1800356a6  call    ?KerbMapKerbError@@YAJJ@Z; KerbMapKerbError(long)
0x1800356ab  jmp     loc_180035CAB
0x1800356b0  mov     r15, [rsi+10h]
0x1800356b4  cmp     [r15+20h], r13d
0x1800356b8  jz      short loc_180035705
0x1800356ba  mov     r15, [rsi+20h]
0x1800356be  test    r15, r15
0x1800356c1  jnz     short loc_180035705
0x1800356c3  mov     ebx, 8009030Eh
0x1800356c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800356cf  lea     rax, WPP_GLOBAL_Control
0x1800356d6  cmp     rcx, rax
0x1800356d9  jz      loc_180035CAD
0x1800356df  lea     edi, [r15+1]
0x1800356e3  test    [rcx+1Ch], dil
0x1800356e7  jz      loc_180035CAD
0x1800356ed  lea     edx, [rdi+26h]
0x1800356f0  mov     rcx, [rcx+10h]
0x1800356f4  lea     r8, WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids
0x1800356fb  call    WPP_SF_
0x180035700  jmp     loc_180035CAD
0x180035705  mov     rdx, [rbp+57h+var_C8]
0x180035709  test    byte ptr [rdx], 80h
0x18003570c  jnz     short loc_180035749
0x18003570e  mov     rcx, cs:WPP_GLOBAL_Control
0x180035715  lea     rax, WPP_GLOBAL_Control
0x18003571c  cmp     rcx, rax
0x18003571f  jz      short loc_18003573F
0x180035721  mov     edi, 1
0x180035726  test    [rcx+1Ch], dil
0x18003572a  jz      short loc_18003573F
0x18003572c  lea     edx, [rdi+27h]
0x18003572f  mov     rcx, [rcx+10h]
0x180035733  lea     r8, WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids
0x18003573a  call    WPP_SF_
0x18003573f  mov     ebx, 0C000006Dh
0x180035744  jmp     loc_180035CAD
0x180035749  mov     rdx, [rdx+10h]; struct KERB_KDC_REQUEST_preauth_data *
0x18003574d  mov     ecx, 11h; unsigned int
0x180035752  call    ?KerbFindPreAuthDataEntry@@YAPEAUKERB_PA_DATA@@KPEAUKERB_KDC_REQUEST_preauth_data@@@Z; KerbFindPreAuthDataEntry(ulong,KERB_KDC_REQUEST_preauth_data *)
0x180035757  test    rax, rax
0x18003575a  jnz     short loc_18003577F
0x18003575c  mov     rcx, cs:WPP_GLOBAL_Control
0x180035763  lea     rax, WPP_GLOBAL_Control
0x18003576a  cmp     rcx, rax
0x18003576d  jz      short loc_18003573F
0x18003576f  mov     edi, 1
0x180035774  test    [rcx+1Ch], dil
0x180035778  jz      short loc_18003573F
0x18003577a  lea     edx, [rdi+28h]
0x18003577d  jmp     short loc_18003572F
0x18003577f  mov     edx, [rax+8]; unsigned int
0x180035782  lea     r9, [rbp+57h+var_D0]; void **
0x180035786  mov     rcx, [rax+10h]; unsigned __int8 *
0x18003578a  mov     r8d, 26h ; '&'; unsigned int
0x180035790  call    ?KerbUnpackData@@YAJPEAEKKPEAPEAX@Z; KerbUnpackData(uchar *,ulong,ulong,void * *)
0x180035795  test    eax, eax
0x180035797  jnz     loc_1800356A4
0x18003579d  lea     edi, [rax+1]
0x1800357a0  mov     rax, [rbp+57h+var_D0]
0x1800357a4  cmp     [rax], di
0x1800357a7  jz      short loc_1800357CE
0x1800357a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800357b0  lea     rax, WPP_GLOBAL_Control
0x1800357b7  cmp     rcx, rax
0x1800357ba  jz      short loc_18003573F
0x1800357bc  test    [rcx+1Ch], dil
0x1800357c0  jz      loc_18003573F
0x1800357c6  lea     edx, [rdi+29h]
0x1800357c9  jmp     loc_18003572F
0x1800357ce  mov     [rsp+130h+var_F0], r13; struct _CRYPT_ALGORITHM_IDENTIFIER **
0x1800357d3  lea     rax, [rbp+57h+hCertStore]
0x1800357d7  mov     [rsp+130h+var_F8], rax; void **
0x1800357dc  lea     r9, a13615232; "1.3.6.1.5.2.3.2"
0x1800357e3  lea     rax, [rsp+130h+SystemTime]
0x1800357e8  mov     [rsp+130h+var_100], rax; struct _CERT_CONTEXT **
0x1800357ed  lea     rax, [rbp+57h+var_80]
0x1800357f1  mov     qword ptr [rsp+130h+var_108], rax; unsigned int *
0x1800357f6  lea     rax, [rbp+57h+var_80+8]
0x1800357fa  mov     [rsp+130h+CriticalSection], rax; unsigned __int8 **
0x1800357ff  mov     rax, [rbp+57h+var_D0]
0x180035803  mov     edx, [rax+10h]; cbSignedBlob
0x180035806  mov     rcx, [rax+18h]; pbSignedBlob
0x18003580a  call    ?ScHelperVerifyPkcsMessage@@YAJPEAEKHPEADPEAPEAEPEAKPEAPEBU_CERT_CONTEXT@@PEAPEAXPEAPEAU_CRYPT_ALGORITHM_IDENTIFIER@@@Z; ScHelperVerifyPkcsMessage(uchar *,ulong,int,char *,uchar * *,ulong *,_CERT_CONTEXT const * *,void * *,_CRYPT_ALGORITHM_IDENTIFIER * *)
0x18003580f  mov     ebx, eax
0x180035811  test    eax, eax
0x180035813  jns     short loc_18003584E
0x180035815  mov     rcx, cs:WPP_GLOBAL_Control
0x18003581c  lea     rax, WPP_GLOBAL_Control
0x180035823  cmp     rcx, rax
0x180035826  jz      short loc_180035844
0x180035828  test    [rcx+1Ch], dil
0x18003582c  jz      short loc_180035844
0x18003582e  mov     rcx, [rcx+10h]
0x180035832  lea     r8, WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids
0x180035839  mov     edx, r14d
0x18003583c  mov     r9d, ebx
0x18003583f  call    WPP_SF_d
0x180035844  mov     r12, qword ptr [rsp+130h+SystemTime]
0x180035849  jmp     loc_180035CAD
0x18003584e  mov     r12, qword ptr [rsp+130h+SystemTime]
0x180035853  test    r12, r12
0x180035856  jnz     short loc_180035888
0x180035858  mov     ebx, 0C000006Dh
0x18003585d  mov     rcx, cs:WPP_GLOBAL_Control
0x180035864  lea     rax, WPP_GLOBAL_Control
0x18003586b  cmp     rcx, rax
0x18003586e  jz      loc_180035CAD
0x180035874  test    [rcx+1Ch], dil
0x180035878  jz      loc_180035CAD
0x18003587e  lea     edx, [r12+2Ch]
0x180035883  jmp     loc_1800356F0
0x180035888  lea     rax, [rbp+57h+var_C0]
0x18003588c  mov     r9, r12
0x18003588f  mov     qword ptr [rsp+130h+var_108], rax
0x180035894  lea     r14, [rsi+58h]
0x180035898  lea     rax, [rbp+57h+var_48]
0x18003589c  xor     edx, edx
0x18003589e  lea     r8, [rbp+57h+hCertStore]
0x1800358a2  mov     [rsp+130h+CriticalSection], rax
0x1800358a7  mov     rcx, r14
0x1800358aa  call    cs:__imp_IntPstValidate
0x1800358b0  mov     ebx, eax
0x1800358b2  test    eax, eax
0x1800358b4  jns     short loc_1800358F2
0x1800358b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800358bd  lea     rax, WPP_GLOBAL_Control
0x1800358c4  cmp     rcx, rax
0x1800358c7  jz      loc_180035CAD
0x1800358cd  test    [rcx+1Ch], dil
0x1800358d1  jz      loc_180035CAD
0x1800358d7  mov     rcx, [rcx+10h]; LoggerHandle
0x1800358db  mov     edx, 2Dh ; '-'
0x1800358e0  mov     r9d, ebx
0x1800358e3  mov     [rsp+130h+CriticalSection], r14; __int64
0x1800358e8  call    WPP_SF_DZ
0x1800358ed  jmp     loc_180035CAD
0x1800358f2  mov     r14d, [rsi+40h]
0x1800358f6  cmp     [rbp+57h+var_C0], r13d
0x1800358fa  jz      short loc_180035902
0x1800358fc  and     r14d, 0FFFFFFFDh
0x180035900  jmp     short loc_180035906
0x180035902  or      r14d, 2
0x180035906  mov     rax, cs:?Pku2uGlobalIdpExtTable@@3PEAU_LSA_IF_IDPROVEXT_FUNCTION_TABLE@@EA; _LSA_IF_IDPROVEXT_FUNCTION_TABLE * Pku2uGlobalIdpExtTable
0x18003590d  lea     r9, [rbp+57h+var_A8]
0x180035911  mov     r8, r12
0x180035914  lea     rcx, [rbp+57h+var_48]
0x180035918  mov     edx, edi
0x18003591a  mov     rax, [rax+8]
0x18003591e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035923  mov     ebx, eax
0x180035925  test    eax, eax
0x180035927  jns     short loc_180035967
0x180035929  mov     rcx, cs:WPP_GLOBAL_Control
0x180035930  lea     rax, WPP_GLOBAL_Control
0x180035937  cmp     rcx, rax
0x18003593a  jz      loc_180035CAD
0x180035940  test    [rcx+1Ch], dil
0x180035944  jz      loc_180035CAD
0x18003594a  mov     edx, 2Eh ; '.'
0x18003594f  mov     r9d, ebx
0x180035952  mov     rcx, [rcx+10h]
0x180035956  lea     r8, WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids
0x18003595d  call    WPP_SF_d
0x180035962  jmp     loc_180035CAD
0x180035967  mov     edx, dword ptr [rbp+57h+var_80]; unsigned int
0x18003596a  lea     r9, [rbp+57h+var_B8]; void **
0x18003596e  mov     rcx, [rbp+57h+var_80+8]; unsigned __int8 *
0x180035972  mov     r8d, 0Fh; unsigned int
0x180035978  call    ?KerbUnpackData@@YAJPEAEKKPEAPEAX@Z; KerbUnpackData(uchar *,ulong,ulong,void * *)
0x18003597d  mov     ebx, eax
0x18003597f  test    eax, eax
0x180035981  jz      short loc_1800359B8
0x180035983  mov     rcx, cs:WPP_GLOBAL_Control
0x18003598a  lea     rax, WPP_GLOBAL_Control
0x180035991  cmp     rcx, rax
0x180035994  jz      short loc_1800359B1
0x180035996  test    [rcx+1Ch], dil
0x18003599a  jz      short loc_1800359B1
0x18003599c  mov     rcx, [rcx+10h]
0x1800359a0  lea     r8, WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids
0x1800359a7  mov     edx, 2Fh ; '/'
0x1800359ac  call    WPP_SF_
0x1800359b1  mov     ecx, ebx
0x1800359b3  jmp     loc_1800356A6
0x1800359b8  mov     rax, [rbp+57h+var_B8]
0x1800359bc  mov     r8d, [rsi+0A8h]
0x1800359c3  mov     r9d, [rax+18h]
0x1800359c7  cmp     r8d, r9d
0x1800359ca  jz      short loc_180035A20
0x1800359cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800359d3  lea     rax, WPP_GLOBAL_Control
0x1800359da  cmp     rcx, rax
0x1800359dd  jz      loc_18003573F
0x1800359e3  test    [rcx+1Ch], dil
0x1800359e7  jz      loc_18003573F
0x1800359ed  mov     edx, 30h ; '0'
0x1800359f2  mov     dword ptr [rsp+130h+var_100], 0B76h
0x1800359fa  mov     rcx, [rcx+10h]
0x1800359fe  lea     rax, aOnecoreDsSecur_9; "onecore\\ds\\security\\protocols\\pku2u"...
0x180035a05  mov     qword ptr [rsp+130h+var_108], rax
0x180035a0a  mov     dword ptr [rsp+130h+CriticalSection], r8d
0x180035a0f  lea     r8, WPP_d581ad8d697432c6379fff16d19b2fc6_Traceguids
0x180035a16  call    WPP_SF_ddsd
0x180035a1b  jmp     loc_18003573F
0x180035a20  mov     rdx, [rbp+57h+var_B8]
0x180035a24  lea     r8, [rbp+57h+var_98]; struct _CRYPTOAPI_BLOB *
0x180035a28  mov     rcx, [rsi+78h]; hPubKey
0x180035a2c  mov     eax, [rdx+8]
0x180035a2f  shr     eax, 3
0x180035a32  mov     [rbp+57h+var_58.cbData], eax
0x180035a35  mov     rax, [rdx+10h]
0x180035a39  lea     rdx, [rbp+57h+var_58]; struct _CRYPTOAPI_BLOB *
0x180035a3d  mov     [rbp+57h+var_58.pbData], rax
0x180035a41  call    ?Pku2uGetSharedKey@@YAH_KPEAU_CRYPTOAPI_BLOB@@1@Z; Pku2uGetSharedKey(unsigned __int64,_CRYPTOAPI_BLOB *,_CRYPTOAPI_BLOB *)
0x180035a46  test    eax, eax
0x180035a48  jnz     short loc_180035A75
0x180035a4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180035a51  lea     rax, WPP_GLOBAL_Control
0x180035a58  cmp     rcx, rax
0x180035a5b  jz      loc_18003573F
0x180035a61  test    [rcx+1Ch], dil
0x180035a65  jz      loc_18003573F
0x180035a6b  mov     edx, 31h ; '1'
0x180035a70  jmp     loc_18003572F
0x180035a75  mov     rax, [rbp+57h+var_C8]
0x180035a79  mov     r9, [rbp+57h+var_D0]
0x180035a7d  mov     ebx, [rax+7Ch]
0x180035a80  test    byte ptr [r9+8], 80h
0x180035a85  mov     dword ptr [rbp+57h+var_70], ebx
0x180035a88  jz      loc_180035B42
0x180035a8e  mov     rdx, [rbp+57h+var_B8]
0x180035a92  test    byte ptr [rdx], 80h
0x180035a95  jz      short loc_180035B0E
0x180035a97  add     rdx, 1Ch; struct tagASN1generalizedtime_t *
0x180035a9b  mov     qword ptr [rsp+130h+Time], r13
0x180035aa0  xor     r8d, r8d; int
0x180035aa3  mov     qword ptr [rsp+130h+SystemTime], r13
0x180035aa8  lea     rcx, [rsp+130h+Time]; Time
0x180035aad  call    ?KerbConvertGeneralizedTimeToLargeInt@@YAXPEAT_LARGE_INTEGER@@PEAUtagASN1generalizedtime_t@@H@Z; KerbConvertGeneralizedTimeToLargeInt(_LARGE_INTEGER *,tagASN1generalizedtime_t *,int)
  ... truncated ...
```
