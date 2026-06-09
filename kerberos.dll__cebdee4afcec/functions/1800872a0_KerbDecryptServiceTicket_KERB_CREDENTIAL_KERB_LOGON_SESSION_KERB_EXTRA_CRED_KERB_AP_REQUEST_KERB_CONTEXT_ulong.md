# KerbDecryptServiceTicket(_KERB_CREDENTIAL *,_KERB_LOGON_SESSION *,_KERB_EXTRA_CRED *,KERB_AP_REQUEST *,_KERB_CONTEXT *,ulong *,KERB_ENCRYPTED_TICKET * *,KERB_AUTHENTICATOR * *,_KERB_ENCRYPTION_KEY *,_KERB_ENCRYPTION_KEY *,_KERB_ENCRYPTION_KEY *,long *)

- ea: `0x1800872a0`
- end: `0x180087d74`
- name: `?KerbDecryptServiceTicket@@YAJPEAU_KERB_CREDENTIAL@@PEAU_KERB_LOGON_SESSION@@PEAU_KERB_EXTRA_CRED@@PEAUKERB_AP_REQUEST@@PEAU_KERB_CONTEXT@@PEAKPEAPEAUKERB_ENCRYPTED_TICKET@@PEAPEAUKERB_AUTHENTICATOR@@PEAU_KERB_ENCRYPTION_KEY@@88PEAJ@Z`
- size: `2772`
- prototype: `__int64 __fastcall(struct _KERB_CREDENTIAL *, struct _KERB_LOGON_SESSION *, struct _KERB_EXTRA_CRED *, struct KERB_AP_REQUEST *, struct _KERB_CONTEXT *, unsigned int *, struct KERB_ENCRYPTED_TICKET **, struct KERB_AUTHENTICATOR **, struct _KERB_ENCRYPTION_KEY *, struct _KERB_ENCRYPTION_KEY *, struct _KERB_ENCRYPTION_KEY *, int *)`
- caller_count: `2`
- callee_count: `24`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180087d7c`
- `0x18008868c`

## callees

- `0x180004a20`
- `0x1800063e8`
- `0x1800068d0`
- `0x180006920`
- `0x180007e80`
- `0x180010e90`
- `0x1800113f0`
- `0x180016550`
- `0x18002abd8`
- `0x18002b740`
- `0x180030ea8`
- `0x180033de0`
- `0x180037aa0`
- `0x18003a044`
- `0x180049f98`
- `0x180070680`
- `0x18007108c`
- `0x180086a64`
- `0x1800872a0`
- `0x18008a464`
- `0x18008b70c`
- `0x1800dd594`
- `0x1800f1ea0`
- `0x1800f5010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180087c56`
- `ntdll!RtlInitUnicodeString` at `0x180087c6a`
- `ntdll!RtlInitUnicodeString` at `0x180087c56`
- `ntdll!RtlInitUnicodeString` at `0x180087c6a`
- `ntdll!RtlReleaseResource` at `0x1800876a8`
- `ntdll!RtlReleaseResource` at `0x180087741`
- `ntdll!RtlReleaseResource` at `0x1800876a8`
- `ntdll!RtlReleaseResource` at `0x180087741`
- `ntdll!RtlAcquireResourceShared` at `0x180087683`
- `ntdll!RtlAcquireResourceShared` at `0x180087683`
- `ntdll!RtlAcquireResourceExclusive` at `0x18008771f`
- `ntdll!RtlAcquireResourceExclusive` at `0x18008771f`
- `ntdll!RtlEnterCriticalSection` at `0x180087480`
- `ntdll!RtlEnterCriticalSection` at `0x1800874dd`
- `ntdll!RtlEnterCriticalSection` at `0x180087480`
- `ntdll!RtlEnterCriticalSection` at `0x1800874dd`
- `ntdll!RtlLeaveCriticalSection` at `0x180087b6a`
- `ntdll!RtlLeaveCriticalSection` at `0x180087b6a`
- `LSASRV!LsaIAuditReplay` at `0x180087c9b`
- `LSASRV!LsaIAuditReplay` at `0x180087c9b`

## string_xrefs

- `0x180087542`: `reject DES service ticket: %#x, %#x\n`
- `0x18008752a`: `KerbDecryptServiceTicket`
- `0x18008760f`: `KerbDecryptServiceTicket`
- `0x180087639`: `KerbDecryptServiceTicket U2U requests require a context to store the TGT`
- `0x18008765c`: `KerbDecryptServiceTicket verifying ticket with TGT session key\n`
- `0x1800876b3`: `KerbDecryptServiceTicket tried to request TGT on credential without a TGT\n`
- `0x1800876eb`: `KerbDecryptServiceTicket tried to request TGT on credential without a TGT\n`
- `0x180087906`: `KerbDecryptServiceTicket couldn't find server key of type 0x%x`
- `0x180087a69`: `KerbDecryptServiceTicket ticket check succeeded using key %x\n`
- `0x180087b02`: `KerbUpdateDecryptingCredential failed %#x, PrimaryCred = %p\n`
- `0x180087b2c`: `KerbDecryptServiceTicket failed to decrypt service ticket\n`

## pseudocode

```c
__int64 __fastcall KerbDecryptServiceTicket(
        struct _KERB_CREDENTIAL *a1,
        unsigned __int64 a2,
        struct _KERB_EXTRA_CRED *a3,
        struct KERB_AP_REQUEST *a4,
        struct _KERB_CONTEXT *a5,
        unsigned int *a6,
        struct KERB_ENCRYPTED_TICKET **a7,
        struct KERB_AUTHENTICATOR **a8,
        struct _KERB_ENCRYPTION_KEY *a9,
        struct _KERB_ENCRYPTION_KEY *a10,
        struct _KERB_ENCRYPTION_KEY *a11,
        int *a12)
{
  __int64 v14; // rbx
  struct _KERB_EXTRA_CRED **v15; // r15
  struct _KERB_TICKET_CACHE_ENTRY *v16; // r13
  unsigned int v17; // esi
  __m128i *v18; // rax
  __int64 v19; // rdx
  char *v20; // r8
  __int64 v21; // xmm0_8
  PVOID *v22; // rcx
  char *v23; // rdi
  struct _KERB_EXTRA_CRED *v24; // r9
  struct _KERB_EXTRA_CRED *v25; // rcx
  char *v26; // rcx
  int v27; // r14d
  unsigned int v28; // eax
  int v29; // eax
  __int16 v30; // ax
  struct _KERB_CONTEXT *v31; // rbx
  int v32; // eax
  unsigned int v33; // r13d
  int v34; // eax
  _DWORD *v35; // rax
  char v36; // di
  size_t v37; // rbx
  size_t v38; // rcx
  int v39; // eax
  __int64 v40; // rcx
  unsigned __int64 v41; // rcx
  void *v42; // rsp
  void *v43; // rsp
  _DWORD *v44; // rax
  struct _KERB_LOGON_SESSION *v45; // rcx
  _DWORD *v46; // rbx
  unsigned int v47; // r14d
  struct KERB_ENCRYPTED_DATA *v48; // rax
  struct KERB_TICKET *v49; // rcx
  int v50; // eax
  int v51; // eax
  int v52; // eax
  __int64 v53; // rbx
  int updated; // eax
  const void *v55; // rax
  __int64 v56; // r12
  struct KERB_ENCRYPTED_TICKET *v57; // rdx
  struct _UNICODE_STRING *v58; // rax
  __int16 *v59; // rsi
  unsigned __int64 v60; // rdi
  _BYTE *v61; // rbx
  struct KERB_ENCRYPTED_TICKET **v62; // rbx
  struct KERB_AUTHENTICATOR **v63; // rbx
  __int64 v65; // [rsp-20h] [rbp-B0h] BYREF
  struct KERB_ADJUSTED_TIME *v66; // [rsp+0h] [rbp-90h] BYREF
  __int64 v67; // [rsp+70h] [rbp-20h]
  _BYTE v68[24]; // [rsp+78h] [rbp-18h] BYREF
  int v69; // [rsp+90h] [rbp+0h] BYREF
  unsigned int v70; // [rsp+94h] [rbp+4h] BYREF
  struct _KERB_EXTRA_CRED *v71; // [rsp+98h] [rbp+8h] BYREF
  struct _KERB_TICKET_CACHE_ENTRY *TicketCacheEntryByRealm; // [rsp+A0h] [rbp+10h]
  struct KERB_AP_REQUEST *v73; // [rsp+A8h] [rbp+18h]
  struct KERB_TICKET *v74; // [rsp+B0h] [rbp+20h]
  struct _KERB_CREDENTIAL *v75; // [rsp+B8h] [rbp+28h]
  struct KERB_ENCRYPTED_TICKET **v76; // [rsp+C0h] [rbp+30h]
  char v77[8]; // [rsp+C8h] [rbp+38h]
  _QWORD v78[2]; // [rsp+D0h] [rbp+40h] BYREF
  struct KERB_AUTHENTICATOR **v79; // [rsp+E0h] [rbp+50h]
  struct _KERB_ENCRYPTION_KEY *v80; // [rsp+E8h] [rbp+58h]
  unsigned int *v81; // [rsp+F0h] [rbp+60h]
  struct _UNICODE_STRING v82; // [rsp+F8h] [rbp+68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+108h] [rbp+78h] BYREF
  struct _UNICODE_STRING v84; // [rsp+118h] [rbp+88h] BYREF
  __int16 v85; // [rsp+128h] [rbp+98h] BYREF
  _BYTE v86[30]; // [rsp+12Ah] [rbp+9Ah] BYREF
  __int64 v87; // [rsp+148h] [rbp+B8h] BYREF
  unsigned __int64 v88; // [rsp+150h] [rbp+C0h] BYREF
  struct _KERB_CONTEXT *v89; // [rsp+158h] [rbp+C8h]
  __int128 v90; // [rsp+160h] [rbp+D0h] BYREF
  __int128 v91; // [rsp+170h] [rbp+E0h]
  __int64 v92; // [rsp+180h] [rbp+F0h]
  __int128 v93; // [rsp+188h] [rbp+F8h] BYREF
  __int64 v94; // [rsp+198h] [rbp+108h]
  char v95[24]; // [rsp+1A0h] [rbp+110h] BYREF
  __m128i v96; // [rsp+1B8h] [rbp+128h] BYREF
  __int64 v97; // [rsp+1C8h] [rbp+138h]
  struct _UNICODE_STRING v98[3]; // [rsp+1D0h] [rbp+140h] BYREF

  v89 = a5;
  v76 = a7;
  v79 = a8;
  *(_QWORD *)&DestinationString.Length = a9;
  v75 = a1;
  v14 = 0;
  v15 = 0;
  v80 = a10;
  v16 = 0;
  v78[0] = a2;
  memset(v98, 0, sizeof(v98));
  TicketCacheEntryByRealm = 0;
  BYTE1(v69) = 0;
  *(_QWORD *)&v82.Length = a11;
  v73 = a4;
  v71 = a3;
  v81 = a6;
  v70 = 0;
  v17 = KerbConvertFlagsToUlong((struct KERB_AP_REQUEST *)((char *)a4 + 8));
  *a12 = 0;
  v92 = 0;
  v85 = 0;
  LOBYTE(v69) = 0;
  *(_OWORD *)v86 = 0;
  *v76 = 0;
  v90 = 0;
  v91 = 0;
  *(_OWORD *)&v86[14] = 0;
  v18 = (__m128i *)((__int64 (__fastcall *)(_QWORD, _QWORD))KERB_ADJUSTED_TIME::SkewSystemTime)(
                     v95,
                     (union _LARGE_INTEGER)KerbGlobalSkewTime.QuadPart);
  v96 = *v18;
  v21 = v18[1].m128i_i64[0];
  v88 = _mm_srli_si128(v96, 8).m128i_u64[0];
  v97 = v21;
  v87 = v96.m128i_i64[0];
  v22 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF__PDATE_TIME_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        WPP_6aa791a05c093f7e04cd3adcd492ce53_Traceguids,
        &v87);
      v22 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 4) != 0 )
      WPP_SF__PDATE_TIME_(v22[2], 40, WPP_6aa791a05c093f7e04cd3adcd492ce53_Traceguids, &v88);
  }
  v23 = (char *)*((_QWORD *)a1 + 9);
  v24 = 0;
  v25 = v71;
  if ( !v23 )
  {
    if ( v71 )
    {
      v23 = (char *)*((_QWORD *)v71 + 8);
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a2 + 856));
      v25 = v71;
      v24 = 0;
      LOBYTE(v69) = 1;
    }
    else
    {
      if ( (_BYTE)KerbGlobalRoles
        && (*(_DWORD *)(a2 + 64) == 999 || *(_DWORD *)(a2 + 64) == 996)
        && !*(_DWORD *)(a2 + 68)
        && ((*((_DWORD *)v73 + 15) - 1) & 0xFFFFFFFD) == 0 )
      {
        *a12 = 41;
        v27 = KerbMapKerbError(41);
        KerbTracerT::Log(1, "KerbDecryptServiceTicket", 8842, "reject DES service ticket: %#x, %#x\n", v27, 41);
        goto LABEL_110;
      }
      v23 = (char *)(a2 + 120);
    }
  }
  LODWORD(v74) = v17 & 0x40000000;
  if ( (v17 & 0x40000000) != 0 )
    goto LABEL_36;
  if ( !*((_QWORD *)v75 + 9) && !v25 )
  {
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a2 + 856));
    v20 = (char *)(a2 + 840);
    LOBYTE(v69) = 1;
    v26 = *(char **)(a2 + 840);
    v24 = 0;
    v14 = 0;
    while ( v26 != v20 )
    {
      v19 = *((_QWORD *)v26 + 8);
      if ( v19 )
      {
        v28 = v14 + 1;
        if ( !*(_QWORD *)(v19 + 144) )
          v28 = v14;
        v14 = v28;
        if ( *(_QWORD *)(v19 + 152) )
          v14 = v28 + 1;
      }
      v26 = *(char **)v26;
    }
    v70 = v14;
  }
  if ( *((_QWORD *)v23 + 18) )
  {
    v14 = (unsigned int)(v14 + 1);
    v70 = v14;
  }
  if ( *((_QWORD *)v23 + 19) )
  {
    v14 = (unsigned int)(v14 + 1);
    v70 = v14;
  }
  if ( (_DWORD)v14 )
  {
LABEL_36:
    *(_QWORD *)&v84.Length = v23 + 16;
    v29 = KerbBuildFullServiceName(v23 + 16, v23, v98);
    v24 = 0;
    if ( v29 )
    {
LABEL_37:
      v27 = -1073741670;
      goto LABEL_108;
    }
    v30 = *((_WORD *)v75 + 24);
    v98[1] = *(struct _UNICODE_STRING *)v23;
    if ( v30 )
      v98[2] = *((struct _UNICODE_STRING *)v75 + 3);
    *(_DWORD *)v77 = (v30 != 0) + 2;
    if ( (_DWORD)v74 )
    {
      v31 = v89;
      if ( !v89 )
      {
        KerbTracerT::Log(
          1,
          "KerbDecryptServiceTicket",
          8911,
          "KerbDecryptServiceTicket U2U requests require a context to store the TGT");
        v27 = -1073741811;
LABEL_43:
        v24 = 0;
        goto LABEL_108;
      }
      KerbTracerT::Log(
        25,
        "KerbDecryptServiceTicket",
        8916,
        "KerbDecryptServiceTicket verifying ticket with TGT session key\n");
      *v81 |= 0x10u;
      RtlAcquireResourceShared(&KerbContextResource, 1u);
      v16 = (struct _KERB_TICKET_CACHE_ENTRY *)*((_QWORD *)v31 + 34);
      TicketCacheEntryByRealm = v16;
      if ( v16 )
        _InterlockedIncrement((volatile signed __int32 *)v16 + 4);
      RtlReleaseResource(&KerbContextResource);
      if ( !v16 )
      {
        KerbTracerT::Log(
          2,
          "KerbDecryptServiceTicket",
          8944,
          "KerbDecryptServiceTicket tried to request TGT on credential without a TGT\n");
        TicketCacheEntryByRealm = KerbLocateTicketCacheEntryByRealm(
                                    (struct _KERB_TICKET_CACHE *)(v23 + 240),
                                    (struct _UNICODE_STRING *)v23 + 1,
                                    0);
        v16 = TicketCacheEntryByRealm;
        if ( !TicketCacheEntryByRealm )
        {
          KerbTracerT::Log(
            1,
            "KerbDecryptServiceTicket",
            8955,
            "KerbDecryptServiceTicket tried to request TGT on credential without a TGT\n");
          *a12 = 67;
          v27 = -2146893042;
          goto LABEL_43;
        }
      }
      RtlAcquireResourceExclusive(&KerbContextResource, 1u);
      if ( !*((_QWORD *)v31 + 34) )
      {
        _InterlockedIncrement((volatile signed __int32 *)v16 + 4);
        *((_QWORD *)v31 + 34) = v16;
      }
      RtlReleaseResource(&KerbContextResource);
      v32 = KerbDuplicateKey(&v90, (char *)v16 + 168);
      v24 = 0;
      if ( v32 )
        goto LABEL_37;
      v33 = 1;
      if ( (unsigned __int64)g_ulMaxStackAllocSize < 0x10
        || (unsigned __int64)(g_ulAdditionalProbeSize + 24) < 0x10
        || (v34 = VerifyStackAvailable(g_ulAdditionalProbeSize + 24, v19, v20, 0), v24 = 0, !v34)
        || &v65 == (__int64 *)-144LL
        || (LODWORD(v67) = 1801679955, (v15 = (struct _KERB_EXTRA_CRED **)v68) == 0) )
      {
        v35 = (_DWORD *)((__int64 (__fastcall *)(__int64, __int64, char *, _QWORD))g_pfnAllocate)(24, v19, v20, 0);
        v24 = 0;
        v15 = (struct _KERB_EXTRA_CRED **)v35;
        if ( v35 )
        {
          *v35 = 1885431112;
          v15 = (struct _KERB_EXTRA_CRED **)(v35 + 2);
        }
      }
      if ( !v15 )
        goto LABEL_60;
      v15[1] = (struct _KERB_EXTRA_CRED *)v23;
      *v15 = (struct _KERB_EXTRA_CRED *)&v90;
      v36 = 1;
    }
    else
    {
      v37 = 16 * v14;
      if ( !v37 )
        goto LABEL_138;
      if ( v37 > g_ulMaxStackAllocSize )
        goto LABEL_138;
      v38 = v37 + g_ulAdditionalProbeSize + 8;
      if ( v38 < v37 )
        goto LABEL_138;
      v39 = VerifyStackAvailable(v38, v19, v20, 0);
      v24 = 0;
      if ( !v39 )
        goto LABEL_138;
      v40 = v37 + 23;
      if ( v37 + 23 <= v37 + 8 )
        v40 = 0xFFFFFFFFFFFFFF0LL;
      v41 = v40 & 0xFFFFFFFFFFFFFFF0uLL;
      v42 = alloca(v41);
      v43 = alloca(v41);
      v15 = (struct _KERB_EXTRA_CRED **)&v69;
      if ( &v66 == (struct KERB_ADJUSTED_TIME **)-144LL || (v69 = 1801679955, (v15 = &v71) == 0) )
      {
LABEL_138:
        if ( v37 + 8 >= v37 )
        {
          v44 = (_DWORD *)((__int64 (__fastcall *)(size_t, __int64, char *, _QWORD))g_pfnAllocate)(v37 + 8, v19, v20, 0);
          v24 = 0;
          v15 = (struct _KERB_EXTRA_CRED **)v44;
          if ( v44 )
          {
            *v44 = 1885431112;
            v15 = (struct _KERB_EXTRA_CRED **)(v44 + 2);
          }
        }
      }
      if ( !v15 )
        goto LABEL_37;
      memset_0(v15, 0, v37);
      v45 = 0;
      if ( !*((_QWORD *)v75 + 9) && !v71 )
        v45 = (struct _KERB_LOGON_SESSION *)(a2 & -(__int64)(*(_DWORD *)(a2 + 896) != 0));
      v46 = (_DWORD *)((char *)v73 + 60);
      v27 = KerbBuildKeyArray(
              v45,
              (struct _KERB_PRIMARY_CREDENTIAL *)v23,
              *((_DWORD *)v73 + 15),
              (struct _KERB_KEY_AND_CRED *)v15,
              &v70);
      if ( v27 < 0 )
      {
        *a12 = 41;
        KerbTracerT::Log(
          1,
          "KerbDecryptServiceTicket",
          9041,
          "KerbDecryptServiceTicket couldn't find server key of type 0x%x",
          *v46);
        goto LABEL_43;
      }
      v33 = v70;
      v36 = 0;
    }
    *a12 = 0;
    v47 = 0;
    if ( v33 )
    {
      v48 = (struct KERB_AP_REQUEST *)((char *)v73 + 96);
      v49 = (struct KERB_AP_REQUEST *)((char *)v73 + 24);
      v74 = (struct KERB_AP_REQUEST *)((char *)v73 + 24);
      v71 = (struct KERB_AP_REQUEST *)((char *)v73 + 96);
      while ( 1 )
      {
        if ( !v36 )
        {
          KerbRevealKey(v15[2 * v47]);
          v48 = v71;
          v49 = v74;
        }
        v50 = KerbCheckTicket(
                v49,
                v48,
                v15[2 * v47],
                (struct CAuthenticatorList *)Authenticators,
                (struct KERB_ADJUSTED_TIME *)&v96,
                v77[0],
                v98,
                *(struct _UNICODE_STRING **)&v84.Length,
                0xEu,
                0xBu,
                (struct _KERB_REPLAY_AUDIT_INFO *)&v85,
                (union _LARGE_INTEGER)VerifyTicketUsingKerbCredIso,
                v76,
                v79,
                v80,
                *(struct _KERB_ENCRYPTION_KEY **)&DestinationString.Length,
                (unsigned __int8 *)&v69 + 1,
                0);
        *a12 = v50;
        if ( !v50 )
          break;
        if ( v50 != 41 )
        {
          if ( !v36 )
            KerbHideKey(v15[2 * v47]);
          v51 = KerbMapKerbError(*a12);
          goto LABEL_106;
        }
        if ( !v36 )
          KerbHideKey(v15[2 * v47]);
        v48 = v71;
        ++v47;
        v49 = v74;
        if ( v47 >= v33 )
          goto LABEL_98;
      }
      KerbTracerT::Log(
        3,
        "KerbDecryptServiceTicket",
        9079,
        "KerbDecryptServiceTicket ticket check succeeded using key %x\n",
        v47);
      v52 = KerbDuplicateKey(*(_QWORD *)&v82.Length, v15[2 * v47]);
      v24 = 0;
      if ( v52 )
      {
        if ( !v36 )
        {
          KerbHideKey(v15[2 * v47]);
          v24 = 0;
        }
LABEL_60:
        v27 = -1073741670;
        goto LABEL_107;
      }
      if ( !v36 )
        KerbHideKey(v15[2 * v47]);
    }
LABEL_98:
    if ( *a12 )
      goto LABEL_105;
    v53 = 2LL * v47;
    updated = KerbUpdateDecryptingCredential(v15[2 * v47 + 1], v73);
    v24 = 0;
    v27 = updated;
    if ( updated < 0 )
    {
      if ( v15[v53 + 1] )
        v55 = (const void *)WORD1(v15[v53 + 1]);
      else
        v55 = 0;
      KerbTracerT::Log(
        1,
        "KerbDecryptServiceTicket",
        9137,
        "KerbUpdateDecryptingCredential failed %#x, PrimaryCred = %p\n",
        v27,
        v55);
      v24 = 0;
      goto LABEL_107;
    }
    if ( *a12 )
    {
LABEL_105:
      KerbTracerT::Log(
        1,
        "KerbDecryptServiceTicket",
        9144,
        "KerbDecryptServiceTicket failed to decrypt service ticket\n");
      v51 = KerbMapKerbError(*a12);
      v24 = 0;
LABEL_106:
      v27 = v51;
    }
LABEL_107:
    v16 = TicketCacheEntryByRealm;
    goto LABEL_108;
  }
  v27 = -2146893042;
  *a12 = 69;
LABEL_108:
  if ( (_BYTE)v69 == (_BYTE)v24 )
    goto LABEL_111;
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v78[0] + 856LL));
LABEL_110:
  v24 = 0;
LABEL_111:
  if ( *a12 == 34 )
  {
    v78[0] = 0;
    v94 = 0;
    v78[1] = v24;
    DestinationString = 0;
    v56 = (__int64)v24;
    v71 = v24;
    v57 = *v76;
    v84 = 0;
    v82 = 0;
    v93 = 0;
    if ( v57 && (*(_BYTE *)v57 & 0x20) != 0 )
    {
      KerbGetClientNetbiosAddress(&v82, *((struct PKERB_HOST_ADDRESSES_s **)v57 + 19));
      v58 = &v82;
      if ( !v82.Length )
        v58 = (struct _UNICODE_STRING *)v56;
      v56 = (__int64)v58;
    }
    v59 = &v85;
    v60 = (unsigned __int64)&v93
        & -(__int64)(((unsigned __int8 (__fastcall *)(__int128 *))LsaFunctions->GetCallInfo)(&v93) != 0);
    if ( !v85 )
      v59 = (__int16 *)v78;
    v61 = &v86[14];
    if ( !*(_WORD *)&v86[14] )
      v61 = v78;
    v71 = *(struct _KERB_EXTRA_CRED **)((char *)v75 + 28);
    RtlInitUnicodeString(&DestinationString, L"KRB_AP_REQ");
    RtlInitUnicodeString(&v84, L"Kerberos");
    LsaIAuditReplay(v59, v61, &DestinationString, &v84, v56, &v71, v60, 0);
    KerbFreeString(v56);
  }
  if ( v15 && *((_DWORD *)v15 - 2) == 1885431112 )
    ((void (__fastcall *)(struct _KERB_EXTRA_CRED **, __int64, char *, struct _KERB_EXTRA_CRED *))g_pfnFree)(
      v15 - 1,
      v19,
      v20,
      v24);
  if ( v16 )
    KerbDereferenceTicketCacheEntry(v16);
  KerbFreeString((__int64)v98);
  if ( *((_QWORD *)&v91 + 1) )
    KerbFreeKey(&v90);
  if ( v27 < 0 )
  {
    v62 = v76;
    if ( *v76 )
    {
      KerbFreeData(51);
      *v62 = 0;
    }
    v63 = v79;
    if ( *v79 )
    {
      KerbFreeData(52);
      *v63 = 0;
    }
    KerbFreeKey(v80);
  }
  KerbFreeString((__int64)&v85);
  KerbFreeString((__int64)&v86[14]);
  return (unsigned int)v27;
}

```

## disassembly

```asm
0x1800872a0  push    rbp
0x1800872a2  push    rbx
0x1800872a3  push    rsi
0x1800872a4  push    rdi
0x1800872a5  push    r12
0x1800872a7  push    r13
0x1800872a9  push    r14
0x1800872ab  push    r15
0x1800872ad  sub     rsp, 218h
0x1800872b4  lea     rbp, [rsp+90h]
0x1800872bc  mov     rax, cs:__security_cookie
0x1800872c3  xor     rax, rbp
0x1800872c6  mov     [rbp+1C0h+var_50], rax
0x1800872cd  mov     rax, [rbp+1C0h+arg_20]
0x1800872d4  mov     rdi, rcx
0x1800872d7  mov     r12, [rbp+1C0h+arg_58]
0x1800872de  xorps   xmm0, xmm0
0x1800872e1  mov     [rbp+1C0h+var_F8], rax
0x1800872e8  mov     r14, rdx
0x1800872eb  mov     rax, [rbp+1C0h+arg_30]
0x1800872f2  mov     [rbp+1C0h+var_190], rax
0x1800872f6  mov     rax, [rbp+1C0h+arg_38]
0x1800872fd  mov     [rbp+1C0h+var_170], rax
0x180087301  mov     rax, [rbp+1C0h+arg_40]
0x180087308  mov     qword ptr [rbp+1C0h+DestinationString.Length], rax
0x18008730c  mov     rax, [rbp+1C0h+arg_48]
0x180087313  mov     [rbp+1C0h+var_198], rcx
0x180087317  xor     ecx, ecx
0x180087319  mov     ebx, ecx
0x18008731b  mov     r15d, ecx
0x18008731e  mov     [rbp+1C0h+var_168], rax
0x180087322  mov     r13d, ecx
0x180087325  mov     rax, [rbp+1C0h+arg_50]
0x18008732c  mov     [rbp+1C0h+var_180], rdx
0x180087330  mov     rdx, [rbp+1C0h+arg_28]
0x180087337  mov     [rbp+1C0h+var_80.Length], cx
0x18008733e  mov     [rbp+1C0h+var_1B0], rcx
0x180087342  mov     [rbp+1C0h+var_1BF], cl
0x180087345  lea     rcx, [r9+8]; struct tagASN1bitstring_t *
0x180087349  movups  [rbp+1C0h+var_6E], xmm0
0x180087350  mov     qword ptr [rbp+1C0h+var_158.Length], rax
0x180087354  mov     [rbp+1C0h+var_1A8], r9
0x180087358  mov     [rbp+1C0h+var_1B8], r8
0x18008735c  mov     [rbp+1C0h+var_160], rdx
0x180087360  mov     [rbp+1C0h+var_1BC], ebx
0x180087363  movups  xmmword ptr [rbp+1C0h+var_80.MaximumLength], xmm0
0x18008736a  movups  [rbp+1C0h+var_6E+0Eh], xmm0
0x180087371  call    ?KerbConvertFlagsToUlong@@YAKPEBUtagASN1bitstring_t@@@Z; KerbConvertFlagsToUlong(tagASN1bitstring_t const *)
0x180087376  xor     ecx, ecx
0x180087378  mov     esi, eax
0x18008737a  mov     [r12], ecx
0x18008737e  xor     eax, eax
0x180087380  mov     [rbp+1C0h+var_D0], rax
0x180087387  mov     rax, [rbp+1C0h+var_190]
0x18008738b  mov     [rbp+1C0h+var_128], cx
0x180087392  mov     [rbp+1C0h+var_1C0], cl
0x180087395  movups  xmmword ptr [rbp+1C0h+var_126], xmm0
0x18008739c  mov     [rax], rcx
0x18008739f  lea     rcx, [rbp+1C0h+var_B0]
0x1800873a6  mov     rdx, qword ptr cs:?KerbGlobalSkewTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER KerbGlobalSkewTime ...
0x1800873ad  movups  [rbp+1C0h+var_F0], xmm0
0x1800873b4  movups  [rbp+1C0h+var_E0], xmm0
0x1800873bb  movups  xmmword ptr [rbp+1C0h+var_126+0Eh], xmm0
0x1800873c2  call    ?SkewSystemTime@KERB_ADJUSTED_TIME@@SA?AU1@_K@Z; KERB_ADJUSTED_TIME::SkewSystemTime(unsigned __int64)
0x1800873c7  movups  xmm2, xmmword ptr [rax]
0x1800873ca  movdqa  xmm1, xmm2
0x1800873ce  movups  [rbp+1C0h+var_98], xmm2
0x1800873d5  movsd   xmm0, qword ptr [rax+10h]
0x1800873da  psrldq  xmm1, 8
0x1800873df  movq    [rbp+1C0h+var_100], xmm1
0x1800873e7  movsd   [rbp+1C0h+var_88], xmm0
0x1800873ef  movsd   [rbp+1C0h+var_108], xmm2
0x1800873f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800873fe  lea     rax, WPP_GLOBAL_Control
0x180087405  cmp     rcx, rax
0x180087408  jz      short loc_180087460
0x18008740a  test    byte ptr [rcx+1Ch], 4
0x18008740e  jz      short loc_180087439
0x180087410  mov     rcx, [rcx+10h]
0x180087414  lea     edx, [r13+27h]
0x180087418  lea     r9, [rbp+1C0h+var_108]
0x18008741f  lea     r8, WPP_6aa791a05c093f7e04cd3adcd492ce53_Traceguids
0x180087426  call    WPP_SF__PDATE_TIME_
0x18008742b  mov     rcx, cs:WPP_GLOBAL_Control
0x180087432  lea     rax, WPP_GLOBAL_Control
0x180087439  cmp     rcx, rax
0x18008743c  jz      short loc_180087460
0x18008743e  test    byte ptr [rcx+1Ch], 4
0x180087442  jz      short loc_180087460
0x180087444  mov     rcx, [rcx+10h]
0x180087448  lea     r9, [rbp+1C0h+var_100]
0x18008744f  mov     edx, 28h ; '('
0x180087454  lea     r8, WPP_6aa791a05c093f7e04cd3adcd492ce53_Traceguids
0x18008745b  call    WPP_SF__PDATE_TIME_
0x180087460  mov     rdi, [rdi+48h]
0x180087464  xor     r9d, r9d
0x180087467  mov     rcx, [rbp+1C0h+var_1B8]
0x18008746b  test    rdi, rdi
0x18008746e  jnz     short loc_1800874B0
0x180087470  test    rcx, rcx
0x180087473  jz      short loc_180087493
0x180087475  mov     rdi, [rcx+40h]
0x180087479  lea     rcx, [r14+358h]; CriticalSection
0x180087480  call    cs:__imp_RtlEnterCriticalSection
0x180087486  mov     rcx, [rbp+1C0h+var_1B8]
0x18008748a  xor     r9d, r9d
0x18008748d  mov     [rbp+1C0h+var_1C0], 1
0x180087491  jmp     short loc_1800874B0
0x180087493  cmp     byte ptr cs:?KerbGlobalRoles@@3U_KerberosSystemRole@@A, r9b; _KerberosSystemRole KerbGlobalRoles
0x18008749a  jz      short loc_1800874AC
0x18008749c  cmp     dword ptr [r14+40h], 3E7h
0x1800874a4  jnz     short loc_1800874FC
0x1800874a6  cmp     [r14+44h], r9d
0x1800874aa  jz      short loc_180087508
0x1800874ac  lea     rdi, [r14+78h]
0x1800874b0  and     esi, 40000000h
0x1800874b6  mov     dword ptr [rbp+1C0h+var_1A0], esi
0x1800874b9  mov     rsi, [rbp+1C0h+var_198]
0x1800874bd  jnz     loc_1800875BD
0x1800874c3  cmp     [rsi+48h], r9
0x1800874c7  jnz     loc_18008758A
0x1800874cd  test    rcx, rcx
0x1800874d0  jnz     loc_18008758A
0x1800874d6  lea     rcx, [r14+358h]; CriticalSection
0x1800874dd  call    cs:__imp_RtlEnterCriticalSection
0x1800874e3  lea     r8, [r14+348h]
0x1800874ea  mov     [rbp+1C0h+var_1C0], 1
0x1800874ee  mov     rcx, [r8]
0x1800874f1  xor     r9d, r9d
0x1800874f4  mov     ebx, r9d
0x1800874f7  jmp     loc_180087582
0x1800874fc  cmp     dword ptr [r14+40h], 3E4h
0x180087504  jnz     short loc_1800874AC
0x180087506  jmp     short loc_1800874A6
0x180087508  mov     rax, [rbp+1C0h+var_1A8]
0x18008750c  mov     eax, [rax+3Ch]
0x18008750f  dec     eax
0x180087511  test    eax, 0FFFFFFFDh
0x180087516  jnz     short loc_1800874AC
0x180087518  mov     ecx, 29h ; ')'; int
0x18008751d  mov     dword ptr [r12], 29h ; ')'
0x180087525  call    ?KerbMapKerbError@@YAJJ@Z; KerbMapKerbError(long)
0x18008752a  lea     rdx, aKerbdecryptser; "KerbDecryptServiceTicket"
0x180087531  mov     [rsp+250h+var_228], 29h ; ')'
0x180087539  mov     ecx, 1
0x18008753e  mov     dword ptr [rsp+250h+var_230], eax
0x180087542  lea     r9, aRejectDesServi; "reject DES service ticket: %#x, %#x\n"
0x180087549  mov     r8d, 228Ah
0x18008754f  mov     r14d, eax
0x180087552  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180087557  jmp     loc_180087B70
0x18008755c  mov     rdx, [rcx+40h]
0x180087560  test    rdx, rdx
0x180087563  jz      short loc_18008757F
0x180087565  cmp     [rdx+90h], r9
0x18008756c  lea     eax, [rbx+1]
0x18008756f  cmovz   eax, ebx
0x180087572  mov     ebx, eax
0x180087574  cmp     [rdx+98h], r9
0x18008757b  jz      short loc_18008757F
0x18008757d  inc     ebx
0x18008757f  mov     rcx, [rcx]
0x180087582  cmp     rcx, r8
0x180087585  jnz     short loc_18008755C
0x180087587  mov     [rbp+1C0h+var_1BC], ebx
0x18008758a  cmp     [rdi+90h], r9
0x180087591  jz      short loc_180087598
0x180087593  inc     ebx
0x180087595  mov     [rbp+1C0h+var_1BC], ebx
0x180087598  cmp     [rdi+98h], r9
0x18008759f  jz      short loc_1800875A6
0x1800875a1  inc     ebx
0x1800875a3  mov     [rbp+1C0h+var_1BC], ebx
0x1800875a6  test    ebx, ebx
0x1800875a8  jnz     short loc_1800875BD
0x1800875aa  mov     r14d, 8009030Eh
0x1800875b0  mov     dword ptr [r12], 45h ; 'E'
0x1800875b8  jmp     loc_180087B59
0x1800875bd  lea     rax, [rdi+10h]
0x1800875c1  mov     rdx, rdi
0x1800875c4  mov     rcx, rax
0x1800875c7  mov     qword ptr [rbp+1C0h+var_138.Length], rax
0x1800875ce  lea     r8, [rbp+1C0h+var_80]
0x1800875d5  call    KerbBuildFullServiceName
0x1800875da  xor     r9d, r9d
0x1800875dd  test    eax, eax
0x1800875df  jz      short loc_1800875EC
0x1800875e1  mov     r14d, 0C000009Ah
0x1800875e7  jmp     loc_180087B59
0x1800875ec  movups  xmm0, xmmword ptr [rdi]
0x1800875ef  movzx   eax, word ptr [rsi+30h]
0x1800875f3  movdqu  xmmword ptr [rbp+150h], xmm0
0x1800875fb  test    ax, ax
0x1800875fe  jz      short loc_18008760C
0x180087600  movups  xmm0, xmmword ptr [rsi+30h]
0x180087604  movdqu  [rbp+1C0h+var_6E+0Eh], xmm0
0x18008760c  neg     ax
0x18008760f  lea     rsi, aKerbdecryptser; "KerbDecryptServiceTicket"
0x180087616  sbb     eax, eax
0x180087618  neg     eax
0x18008761a  add     eax, 2
0x18008761d  mov     dword ptr [rbp+1C0h+var_188], eax
0x180087620  cmp     dword ptr [rbp+1C0h+var_1A0], r9d
0x180087624  jz      loc_180087800
0x18008762a  mov     rbx, [rbp+1C0h+var_F8]
0x180087631  mov     rdx, rsi
0x180087634  test    rbx, rbx
0x180087637  jnz     short loc_18008765C
0x180087639  lea     r9, aKerbdecryptser_5; "KerbDecryptServiceTicket U2U requests r"...
0x180087640  mov     r8d, 22CFh
0x180087646  lea     ecx, [rbx+1]
0x180087649  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18008764e  mov     r14d, 0C000000Dh
0x180087654  xor     r9d, r9d
0x180087657  jmp     loc_180087B59
0x18008765c  lea     r9, aKerbdecryptser_2; "KerbDecryptServiceTicket verifying tick"...
0x180087663  mov     r8d, 22D4h
0x180087669  mov     ecx, 19h
0x18008766e  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180087673  mov     rax, [rbp+1C0h+var_160]
0x180087677  lea     rcx, ?KerbContextResource@@3U_RTL_RESOURCE@@A; Resource
0x18008767e  mov     dl, 1; Wait
0x180087680  or      dword ptr [rax], 10h
0x180087683  call    cs:__imp_RtlAcquireResourceShared
0x180087689  mov     r13, [rbx+110h]
0x180087690  xor     r14d, r14d
0x180087693  mov     [rbp+1C0h+var_1B0], r13
0x180087697  test    r13, r13
0x18008769a  jz      short loc_1800876A1
0x18008769c  lock inc dword ptr [r13+10h]
0x1800876a1  lea     rcx, ?KerbContextResource@@3U_RTL_RESOURCE@@A; Resource
0x1800876a8  call    cs:__imp_RtlReleaseResource
0x1800876ae  test    r13, r13
0x1800876b1  jnz     short loc_180087716
0x1800876b3  lea     r9, aKerbdecryptser_6; "KerbDecryptServiceTicket tried to reque"...
0x1800876ba  mov     r8d, 22F0h
0x1800876c0  mov     rdx, rsi
0x1800876c3  lea     ecx, [r13+2]
0x1800876c7  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800876cc  lea     rcx, [rdi+0F0h]; struct _KERB_TICKET_CACHE *
0x1800876d3  xor     r8d, r8d; unsigned int
0x1800876d6  lea     rdx, [rdi+10h]; struct _UNICODE_STRING *
0x1800876da  call    ?KerbLocateTicketCacheEntryByRealm@@YAPEAU_KERB_TICKET_CACHE_ENTRY@@PEAU_KERB_TICKET_CACHE@@PEAU_UNICODE_STRING@@K@Z; KerbLocateTicketCacheEntryByRealm(_KERB_TICKET_CACHE *,_UNICODE_STRING *,ulong)
0x1800876df  mov     [rbp+1C0h+var_1B0], rax
0x1800876e3  mov     r13, rax
0x1800876e6  test    rax, rax
0x1800876e9  jnz     short loc_180087716
0x1800876eb  lea     r9, aKerbdecryptser_6; "KerbDecryptServiceTicket tried to reque"...
0x1800876f2  mov     r8d, 22FBh
0x1800876f8  mov     rdx, rsi
0x1800876fb  lea     ecx, [rax+1]
0x1800876fe  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180087703  mov     dword ptr [r12], 43h ; 'C'
0x18008770b  mov     r14d, 8009030Eh
0x180087711  jmp     loc_180087654
0x180087716  mov     dl, 1; Wait
0x180087718  lea     rcx, ?KerbContextResource@@3U_RTL_RESOURCE@@A; Resource
0x18008771f  call    cs:__imp_RtlAcquireResourceExclusive
0x180087725  cmp     [rbx+110h], r14
0x18008772c  jnz     short loc_18008773A
0x18008772e  lock inc dword ptr [r13+10h]
0x180087733  mov     [rbx+110h], r13
0x18008773a  lea     rcx, ?KerbContextResource@@3U_RTL_RESOURCE@@A; Resource
0x180087741  call    cs:__imp_RtlReleaseResource
0x180087747  lea     rdx, [r13+0A8h]
0x18008774e  lea     rcx, [rbp+1C0h+var_F0]
0x180087755  call    KerbDuplicateKey
0x18008775a  xor     r9d, r9d
0x18008775d  test    eax, eax
0x18008775f  jnz     loc_1800875E1
0x180087765  cmp     cs:g_ulMaxStackAllocSize, 10h
0x18008776d  lea     r13d, [r9+1]
0x180087771  jb      short loc_1800877B4
0x180087773  mov     rcx, cs:g_ulAdditionalProbeSize
0x18008777a  add     rcx, 18h
0x18008777e  cmp     rcx, 10h
0x180087782  jb      short loc_1800877B4
0x180087784  call    VerifyStackAvailable
0x180087789  xor     r9d, r9d
0x18008778c  test    eax, eax
0x18008778e  jz      short loc_1800877B4
0x180087790  mov     eax, dword ptr [rsp+250h+var_250]
0x180087793  sub     rsp, 20h
0x180087797  lea     r15, [rsp+270h+var_1E0]
0x18008779f  mov     eax, [r15]
0x1800877a2  test    r15, r15
0x1800877a5  jz      short loc_1800877B4
0x1800877a7  mov     dword ptr [r15], 6B637453h
0x1800877ae  add     r15, 8
0x1800877b2  jnz     short loc_1800877DA
0x1800877b4  mov     rax, cs:g_pfnAllocate
0x1800877bb  mov     ecx, 18h
0x1800877c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800877c5  xor     r9d, r9d
0x1800877c8  mov     r15, rax
0x1800877cb  test    rax, rax
0x1800877ce  jz      short loc_1800877DA
0x1800877d0  mov     dword ptr [rax], 70616548h
0x1800877d6  add     r15, 8
0x1800877da  test    r15, r15
  ... truncated ...
```
