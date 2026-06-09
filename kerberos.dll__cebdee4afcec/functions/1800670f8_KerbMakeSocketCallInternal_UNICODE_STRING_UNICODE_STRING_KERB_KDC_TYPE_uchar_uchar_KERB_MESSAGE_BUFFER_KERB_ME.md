# KerbMakeSocketCallInternal(_UNICODE_STRING *,_UNICODE_STRING *,_KERB_KDC_TYPE,uchar,uchar,_KERB_MESSAGE_BUFFER *,_KERB_MESSAGE_BUFFER *,_KERB_BINDING_CACHE_ENTRY *,ulong,uchar,uchar *,_UNICODE_STRING *,ulong *)

- ea: `0x1800670f8`
- end: `0x180067ad1`
- name: `?KerbMakeSocketCallInternal@@YAJPEAU_UNICODE_STRING@@0W4_KERB_KDC_TYPE@@EEPEAU_KERB_MESSAGE_BUFFER@@2PEAU_KERB_BINDING_CACHE_ENTRY@@KEPEAE0PEAK@Z`
- size: `2521`
- prototype: `__int64 __fastcall(const UNICODE_STRING *, const UNICODE_STRING *, int, unsigned __int8, unsigned __int8, struct _KERB_MESSAGE_BUFFER *, struct _KERB_MESSAGE_BUFFER *, struct _KERB_TABLE_ENTRY *, unsigned int, char, bool *, struct _UNICODE_STRING *, unsigned int *)`
- caller_count: `4`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800363f4`
- `0x18008a050`
- `0x1800b1a0c`
- `0x1800b2c30`

## callees

- `0x1800068d0`
- `0x18000b300`
- `0x18000d9e4`
- `0x180012e30`
- `0x18002c31c`
- `0x180031c64`
- `0x180037e30`
- `0x180037ea8`
- `0x180050f70`
- `0x180065c48`
- `0x180066934`
- `0x1800670f8`
- `0x18006b590`
- `0x18006ba6c`
- `0x18007108c`
- `0x180077bb0`
- `0x18007b4e0`
- `0x18007b86c`
- `0x18008723c`
- `0x18008a114`
- `0x18008a1e4`
- `0x18008b2f4`
- `0x18008b70c`
- `0x18009378c`
- `0x1800b5a10`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180067633`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180067633`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180067482`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180067482`
- `ntdll!NtClose` at `0x180067640`
- `ntdll!NtClose` at `0x180067640`
- `ntdll!RtlReleaseResource` at `0x180067ab5`
- `ntdll!RtlReleaseResource` at `0x180067ab5`
- `ntdll!RtlAcquireResourceExclusive` at `0x180067aa0`
- `ntdll!RtlAcquireResourceExclusive` at `0x180067aa0`
- `ntdll!NtOpenThreadToken` at `0x180067476`
- `ntdll!NtOpenThreadToken` at `0x180067476`

## string_xrefs

- `0x180067982`: `Failed to open Token For Thread. Status:0x%x\n`
- `0x180067652`: `Failed to set thread token: %#x\n`

## pseudocode

```c
__int64 __fastcall KerbMakeSocketCallInternal(
        const UNICODE_STRING *a1,
        const UNICODE_STRING *a2,
        int a3,
        unsigned __int8 a4,
        unsigned __int8 a5,
        struct _KERB_MESSAGE_BUFFER *a6,
        struct _KERB_MESSAGE_BUFFER *a7,
        struct _KERB_TABLE_ENTRY *a8,
        unsigned int a9,
        char a10,
        bool *a11,
        struct _UNICODE_STRING *a12,
        unsigned int *a13)
{
  unsigned int v13; // r13d
  int v16; // r14d
  int v17; // edi
  struct _KERB_PIN_KDC_ENTRY *v18; // r15
  int v19; // ebx
  __int64 v20; // rdx
  unsigned int v21; // esi
  bool IsDmsaCapableDCRequired; // al
  unsigned int v23; // ecx
  Ntlmless::Kerberos *v24; // rcx
  struct _UNICODE_STRING *v25; // r9
  unsigned int v26; // r12d
  const UNICODE_STRING *v27; // rbx
  int PinKdcEntry; // eax
  unsigned int v29; // esi
  struct _KERB_TABLE_ENTRY *v30; // rcx
  int KdcBinding; // eax
  const struct _UNICODE_STRING *v32; // rdx
  int v33; // eax
  char v34; // dl
  NTSTATUS v35; // eax
  NTSTATUS v36; // ebx
  int v37; // esi
  int v38; // edx
  const void *v39; // rcx
  __int64 v40; // r8
  __int64 (__fastcall *v41)(_QWORD, _QWORD, _QWORD, struct _KERB_MESSAGE_BUFFER *, __int128 *, unsigned int *); // rax
  BOOL v42; // ebx
  __int64 *v43; // rax
  int v44; // edx
  int v45; // ecx
  unsigned int v46; // r8d
  int v47; // eax
  struct _KERB_TABLE_ENTRY *v48; // rdx
  unsigned int v49; // r8d
  __int64 *v50; // rax
  int v51; // edx
  int v52; // ecx
  struct _KERB_TABLE_ENTRY *v53; // rdx
  __int64 *CorrelationId; // rax
  int v55; // ecx
  char v57[8]; // [rsp+20h] [rbp-E0h]
  struct _KERB_BINDING_CACHE_ENTRY **v58; // [rsp+28h] [rbp-D8h]
  struct _KERB_BINDING_CACHE_ENTRY **v59; // [rsp+30h] [rbp-D0h]
  struct _KERB_MESSAGE_BUFFER *v60; // [rsp+38h] [rbp-C8h]
  __int64 v61; // [rsp+40h] [rbp-C0h]
  struct _KERB_TABLE_ENTRY *v62; // [rsp+50h] [rbp-B0h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v64; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v65[32]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v66; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v67[64]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v68; // [rsp+D8h] [rbp-28h]
  __int128 v69; // [rsp+E8h] [rbp-18h]
  int v70; // [rsp+F8h] [rbp-8h]
  unsigned int v73; // [rsp+180h] [rbp+80h]

  v13 = KerbGlobalKdcCallTimeout;
  v73 = 0;
  v16 = 0;
  v17 = 0;
  v62 = 0;
  v18 = 0;
  TokenHandle = 0;
  v66 = 0;
  v19 = 128;
  memset_0(v67, 0, 0x80u);
  if ( a5 && v13 < KerbGlobalKPassCallTimeout )
    v13 = KerbGlobalKPassCallTimeout;
  *a11 = 0;
  if ( a3 != 1 )
  {
    if ( a3 == 2 )
    {
      v19 = 790528;
    }
    else if ( a3 == 3 )
    {
      v19 = 0x80000;
    }
    else
    {
      v19 = 0;
    }
  }
  KerbTracerT::Log(3, "KerbMakeSocketCallInternal", 3216, "KerbMakeSocketCall uses KdcToCall option %d.\n", a3);
  v21 = a9;
  if ( (a9 & 1) != 0 )
  {
    v19 |= 1u;
    KerbTracerT::Log(3, "KerbMakeSocketCallInternal", 3224, "KerbMakeSocketCall() caller wants rediscovery!\n");
  }
  LOBYTE(v20) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstantHAADJ>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_InstantHAADJ>::GetImpl'::`2'::impl,
    v20);
  IsDmsaCapableDCRequired = KerbDmsaPolicy::IsDmsaCapableDCRequired(a1);
  v23 = v21 | 0x2000000;
  if ( !IsDmsaCapableDCRequired )
    v23 = v21;
  v26 = v19 & 0xF017FFEF | KerbConsolidateDsVersionAndKeyListFlags(v23);
  v27 = a1;
  if ( a8 != (struct _KERB_TABLE_ENTRY *)v25 || a10 != (_BYTE)v25 )
    goto LABEL_25;
  PinKdcEntry = KerbLocatePinKdcEntry(a1, v26, (struct _KERB_PIN_KDC_ENTRY **)&TokenHandle);
  v25 = 0;
  v17 = PinKdcEntry;
  if ( PinKdcEntry >= 0 )
  {
    v18 = (struct _KERB_PIN_KDC_ENTRY *)TokenHandle;
    if ( TokenHandle )
    {
      v70 = 0;
      v68 = *(_OWORD *)((char *)TokenHandle + 40);
      v69 = *(_OWORD *)((char *)TokenHandle + 56);
    }
LABEL_25:
    v29 = 0;
    while ( 1 )
    {
      if ( v29 )
      {
        if ( v18 )
        {
          v17 = -1073741715;
          goto LABEL_19;
        }
        v26 |= 1u;
        v13 += KerbGlobalKdcCallBackoff;
      }
      if ( a8 != (struct _KERB_TABLE_ENTRY *)v25 && !v29 )
        break;
      if ( v18 )
      {
        v30 = (struct _KERB_TABLE_ENTRY *)&v66;
        goto LABEL_34;
      }
      if ( Ntlmless::Kerberos::IsEnabled(v24) )
        KdcBinding = KerbGetKdcBindingEx(v27, a2, v26, a5, a4, *a13, &v62);
      else
        KdcBinding = KerbGetKdcBinding(v27, a2, v26, a5, a4, &v62);
      v25 = 0;
      v17 = KdcBinding;
      if ( KdcBinding < 0 )
      {
        LODWORD(v58) = KdcBinding;
        KerbTracerT::Log(2, "KerbMakeSocketCallInternal", 3348, "Failed to get KDC binding for %wZ: 0x%x\n", v27, v58);
        if ( (Microsoft_Windows_Security_KerberosEnableBits & 4) != 0 )
        {
          CorrelationId = (__int64 *)KerbTracerT::GetCorrelationId(v65);
          LOBYTE(v16) = v16 | 1;
          McTemplateU0zqz_EtwEventWriteTransfer(v55, (unsigned int)FailureLocatingDc, v27->Buffer, v17, *CorrelationId);
        }
        if ( (v16 & 1) != 0 )
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v65);
        goto LABEL_18;
      }
      v30 = v62;
LABEL_40:
      if ( a12 != v25 )
      {
        KerbFreeString(a12);
        if ( *((_WORD *)v62 + 60) )
          v32 = (const struct _UNICODE_STRING *)((char *)v62 + 120);
        else
          v32 = (const struct _UNICODE_STRING *)((char *)v62 + 88);
        v33 = KerbDuplicateStringEx(a12, v32);
        v25 = 0;
        v17 = v33;
        if ( v33 < 0 )
        {
          KerbTracerT::Log(2, "KerbMakeSocketCallInternal", 3373, "Failed to get KDC name\n");
          goto LABEL_18;
        }
        v30 = v62;
      }
      if ( (*((_DWORD *)v30 + 29) & 0x40000000) == 0 )
      {
        v34 = a4;
        if ( *(_DWORD *)a6 > (unsigned int)KerbGlobalMaxDatagramSize )
          v34 = 1;
        a4 = v34;
      }
      if ( *a11 == (_BYTE)v25 )
        *a11 = (*((_DWORD *)v30 + 27) & 0x80) != 0;
      if ( *((_DWORD *)v30 + 29) < (int)v25 )
      {
        TokenHandle = v25;
        v35 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
        v36 = v35;
        if ( v35 < 0 )
        {
          if ( v35 != -1073741700 )
          {
            KerbTracerT::Log(
              2,
              "KerbMakeSocketCallInternal",
              3429,
              "Failed to open Token For Thread. Status:0x%x\n",
              v35);
            v17 = v36;
            goto LABEL_18;
          }
        }
        else
        {
          RevertToSelf();
        }
        v64 = 0;
        if ( !a5 )
        {
          KerbTracerT::Log(3, "KerbMakeSocketCallInternal", 3438, "Calling kdc directly\n");
          KerbBeginKdcCall();
          if ( KerbGlobalKerbKdcCallInfo )
          {
            v37 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, struct _KERB_MESSAGE_BUFFER *, __int128 *, unsigned int *))KerbGlobalKerbKdcCallInfo
                   + 1))(
                    0,
                    0,
                    0,
                    a6,
                    &v64,
                    a13);
            if ( v37 != -2147483646 )
            {
              v38 = v64;
              if ( (_DWORD)v64 )
              {
                if ( *((_QWORD *)&v64 + 1) )
                  goto LABEL_61;
LABEL_64:
                v39 = 0;
              }
              else
              {
                if ( !*((_QWORD *)&v64 + 1) )
                  goto LABEL_64;
                v39 = (const void *)WORD5(v64);
              }
              v40 = 3467;
LABEL_72:
              KerbTracerT::Log(
                1,
                "KerbMakeSocketCallInternal",
                v40,
                "KerbMakeSocketCall direct kdc call returned %#x and received no error message KdcReplyMessage.BufferSize"
                " %#x KdcReplyMessage.Buffer %p\n",
                v37,
                v38,
                v39);
              v17 = -1073741670;
            }
LABEL_76:
            KerbEndKdcCall();
            if ( TokenHandle )
            {
              v42 = SetThreadToken(0, TokenHandle);
              NtClose(TokenHandle);
              LOBYTE(v25) = 0;
              if ( !v42 )
              {
                v17 = -1073741555;
                KerbTracerT::Log(
                  1,
                  "KerbMakeSocketCallInternal",
                  3533,
                  "Failed to set thread token: %#x\n",
                  -1073741555);
                v29 = v73;
                goto LABEL_18;
              }
            }
            else
            {
              LOBYTE(v25) = 0;
            }
            if ( v37 != -2147483646 )
            {
              v29 = v73;
              goto LABEL_19;
            }
            v17 = -1073741422;
            if ( (Microsoft_Windows_Security_KerberosEnableBits & 8) != 0 )
            {
              v43 = (__int64 *)KerbTracerT::GetCorrelationId(v65);
              v16 |= 2u;
              McTemplateU0zzqqqz_EtwEventWriteTransfer(
                v45,
                v44,
                *((_QWORD *)v62 + 16),
                *((_QWORD *)v62 + 10),
                v26,
                *((_DWORD *)v62 + 29),
                146,
                *v43);
            }
            if ( (v16 & 2) != 0 )
            {
              v16 &= ~2u;
LABEL_102:
              utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v65);
              goto LABEL_103;
            }
            goto LABEL_103;
          }
LABEL_75:
          v37 = -2147483646;
          goto LABEL_76;
        }
        KerbBeginKdcCall();
        if ( !KerbGlobalKerbKdcCallInfo )
          goto LABEL_75;
        v41 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, struct _KERB_MESSAGE_BUFFER *, __int128 *, unsigned int *))*((_QWORD *)KerbGlobalKerbKdcCallInfo + 2);
        a9 = 0;
        v37 = v41(0, 0, 0, a6, &v64, &a9);
        if ( v37 == -2147483646 )
          goto LABEL_76;
        v38 = v64;
        if ( (_DWORD)v64 )
        {
          if ( *((_QWORD *)&v64 + 1) )
          {
LABEL_61:
            v17 = KerbCopyKerbMessageBuffer(a7, (struct _KERB_MESSAGE_BUFFER *)&v64);
            (*((void (__fastcall **)(_QWORD))KerbGlobalKerbKdcCallInfo + 3))(*((_QWORD *)&v64 + 1));
            goto LABEL_76;
          }
LABEL_70:
          v39 = 0;
        }
        else
        {
          if ( !*((_QWORD *)&v64 + 1) )
            goto LABEL_70;
          v39 = (const void *)WORD5(v64);
        }
        v40 = 3509;
        goto LABEL_72;
      }
      if ( KerbGlobalNoTcpUdp != (_BYTE)v25 )
      {
        KerbTracerT::Log(1, "KerbMakeSocketCallInternal", 3565, "KerbMakeSocketCall no IP\n");
        v17 = -1073741252;
        goto LABEL_18;
      }
      if ( v30 == (struct _KERB_TABLE_ENTRY *)&v66 )
      {
        KerbTracerT::Log(22, "KerbMakeSocketCallInternal", 3573, "use pin kdc entry for domain %wZ\n", v27);
        v30 = v62;
      }
      LODWORD(v61) = KerbGlobalCachedKdcConnectTimeout;
      LODWORD(v60) = v26;
      *(_DWORD *)v57 = v29;
      KerbTracerT::Log(
        22,
        "KerbMakeSocketCallInternal",
        3577,
        "Retry #%d Calling kdc %wZ for realm %wZ, DesiredFlags %#x, connection timeout: %d secs\n",
        *(_QWORD *)v57,
        (char *)v30 + 88,
        v27,
        v60,
        v61);
      v46 = KerbGlobalCachedKdcConnectTimeout;
      if ( (v26 & 1) != 0 )
        v46 = 0;
      v47 = KerbCallKdcEx(
              (struct _UNICODE_STRING *)((char *)v62 + 88),
              *((_DWORD *)v62 + 26),
              v46,
              v13,
              a4 == 0,
              a5 != 0 ? 464 : 88,
              a6,
              a7);
      v17 = v47;
      if ( v47 >= 0 )
        goto LABEL_106;
      if ( v47 == -1073741306 && !a4 )
      {
        v48 = v62;
        if ( (*((_DWORD *)v62 + 29) & 0x40000000) != 0 )
          goto LABEL_98;
        v49 = KerbGlobalCachedKdcConnectTimeout;
        if ( (v26 & 1) != 0 )
          v49 = 0;
        a4 = 1;
        v17 = KerbCallKdcEx(
                (struct _UNICODE_STRING *)((char *)v62 + 88),
                *((_DWORD *)v62 + 26),
                v49,
                v13,
                0,
                a5 != 0 ? 464 : 88,
                a6,
                a7);
        if ( v17 >= 0 )
          goto LABEL_106;
      }
      v48 = v62;
LABEL_98:
      LODWORD(v59) = v17;
      *(_DWORD *)v57 = v73;
      KerbTracerT::Log(
        1,
        "KerbMakeSocketCallInternal",
        3627,
        "Failed retries %d to get make call to KDC %wZ: 0x%x",
        *(_QWORD *)v57,
        (char *)v48 + 88,
        v59);
      if ( (Microsoft_Windows_Security_KerberosEnableBits & 8) != 0 )
      {
        v50 = (__int64 *)KerbTracerT::GetCorrelationId(v65);
        v16 |= 4u;
        McTemplateU0zzqqqz_EtwEventWriteTransfer(
          v52,
          v51,
          *((_QWORD *)v62 + 16),
          *((_QWORD *)v62 + 10),
          v26,
          *((_DWORD *)v62 + 29),
          v17,
          *v50);
      }
      if ( (v16 & 4) != 0 )
      {
        v16 &= ~4u;
        goto LABEL_102;
      }
LABEL_103:
      v53 = v62;
      if ( v62 == a8 )
        goto LABEL_110;
      if ( v62 != (struct _KERB_TABLE_ENTRY *)&v66 )
      {
        KerbRemoveBindingCacheEntry(v62);
LABEL_106:
        v53 = v62;
      }
      if ( v53 != a8 && v53 != (struct _KERB_TABLE_ENTRY *)&v66 )
        _KERB_TABLE::Dereference((_KERB_TABLE *)&KerbBindingCache, v53);
LABEL_110:
      v25 = 0;
      v29 = v73 + 1;
      v62 = 0;
      ++v73;
      if ( v17 >= 0 || v29 >= KerbGlobalKdcSendRetries )
        goto LABEL_19;
      v27 = a1;
    }
    v30 = a8;
LABEL_34:
    v62 = v30;
    goto LABEL_40;
  }
  KerbTracerT::Log(
    1,
    "KerbMakeSocketCallInternal",
    3281,
    "Failed to locate a pin kdc entry for domain %wZ: %#x, DesiredFlags %#x\n",
    a1,
    PinKdcEntry,
    v26);
  v18 = (struct _KERB_PIN_KDC_ENTRY *)TokenHandle;
  v29 = 0;
LABEL_18:
  LOBYTE(v25) = 0;
LABEL_19:
  if ( a4 == (_BYTE)v25 )
  {
    if ( v17 >= 0 )
    {
      if ( v29 < KerbGlobalKdcSendRetries )
      {
        KerbResetTransportCounter();
        goto LABEL_124;
      }
    }
    else if ( v29 == KerbGlobalKdcSendRetries )
    {
      KerbTracerT::Log(1, "KerbMakeSocketCallInternal", 3666, "We look to be timing out on UDP \n");
      KerbReportTransportError(v17);
LABEL_124:
      LOBYTE(v25) = 0;
    }
  }
  if ( v62 && v62 != a8 && v62 != (struct _KERB_TABLE_ENTRY *)&v66 )
  {
    _KERB_TABLE::Dereference((_KERB_TABLE *)&KerbBindingCache, v62);
    LOBYTE(v25) = 0;
  }
  if ( v18 && KerbGlobalProcessTableInitialized != (_BYTE)v25 )
  {
    RtlAcquireResourceExclusive(&KerbGlobalProcessTableLock, 1u);
    KerbDereferencePinKdcEntry(v18);
    RtlReleaseResource(&KerbGlobalProcessTableLock);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800670f8  mov     [rsp-8+String2], rdx
0x1800670fd  mov     [rsp-8+String1], rcx
0x180067102  push    rbp
0x180067103  push    rbx
0x180067104  push    rsi
0x180067105  push    rdi
0x180067106  push    r12
0x180067108  push    r13
0x18006710a  push    r14
0x18006710c  push    r15
0x18006710e  lea     rbp, [rsp-28h]
0x180067113  sub     rsp, 128h
0x18006711a  mov     r13d, cs:?KerbGlobalKdcCallTimeout@@3KA; ulong KerbGlobalKdcCallTimeout
0x180067121  mov     r12, rcx
0x180067124  xor     ecx, ecx
0x180067126  mov     byte ptr [rbp+60h+arg_18], r9b
0x18006712d  mov     [rbp+60h+arg_10], ecx
0x180067133  mov     esi, r8d
0x180067136  mov     [rbp+60h+arg_10], ecx
0x18006713c  mov     r14d, ecx
0x18006713f  mov     edi, ecx
0x180067141  mov     [rsp+160h+var_110], rcx
0x180067146  mov     r15d, ecx
0x180067149  mov     [rsp+160h+TokenHandle], rcx
0x18006714e  mov     [rbp+60h+var_D0], rcx
0x180067152  mov     ebx, 80h
0x180067157  lea     rcx, [rbp+60h+var_C8]; void *
0x18006715b  mov     r8d, ebx; Size
0x18006715e  xor     edx, edx; Val
0x180067160  call    memset_0
0x180067165  xor     r10d, r10d
0x180067168  cmp     [rbp+60h+arg_20], r10b
0x18006716f  jz      short loc_180067180
0x180067171  cmp     r13d, cs:?KerbGlobalKPassCallTimeout@@3KA; ulong KerbGlobalKPassCallTimeout
0x180067178  cmovb   r13d, cs:?KerbGlobalKPassCallTimeout@@3KA; ulong KerbGlobalKPassCallTimeout
0x180067180  mov     rax, [rbp+60h+arg_50]
0x180067187  mov     ecx, esi
0x180067189  mov     [rax], r10b
0x18006718c  sub     ecx, 1
0x18006718f  jz      short loc_1800671AC
0x180067191  sub     ecx, 1
0x180067194  jz      short loc_1800671A7
0x180067196  cmp     ecx, 1
0x180067199  jz      short loc_1800671A0
0x18006719b  mov     ebx, r10d
0x18006719e  jmp     short loc_1800671AC
0x1800671a0  mov     ebx, 80000h
0x1800671a5  jmp     short loc_1800671AC
0x1800671a7  mov     ebx, 0C1000h
0x1800671ac  lea     r9, aKerbmakesocket_1; "KerbMakeSocketCall uses KdcToCall optio"...
0x1800671b3  mov     dword ptr [rsp+160h+var_140], esi
0x1800671b7  mov     r8d, 0C90h
0x1800671bd  lea     rdx, aKerbmakesocket_3; "KerbMakeSocketCallInternal"
0x1800671c4  mov     ecx, 3
0x1800671c9  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800671ce  mov     esi, [rbp+60h+arg_40]
0x1800671d4  mov     eax, 1
0x1800671d9  test    al, sil
0x1800671dc  jz      short loc_180067201
0x1800671de  or      ebx, eax
0x1800671e0  lea     r9, aKerbmakesocket_0; "KerbMakeSocketCall() caller wants redis"...
0x1800671e7  mov     r8d, 0C98h
0x1800671ed  lea     rdx, aKerbmakesocket_3; "KerbMakeSocketCallInternal"
0x1800671f4  lea     ecx, [rax+2]
0x1800671f7  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800671fc  mov     eax, 1
0x180067201  mov     dl, al
0x180067203  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InstantHAADJ@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InstantHAADJ@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstantHAADJ> `wil::Feature<__WilFeatureTraits_Feature_InstantHAADJ>::GetImpl(void)'::`2'::impl
0x18006720a  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_InstantHAADJ@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstantHAADJ>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18006720f  mov     rcx, r12; String1
0x180067212  call    ?IsDmsaCapableDCRequired@KerbDmsaPolicy@@SA_NPEAU_UNICODE_STRING@@@Z; KerbDmsaPolicy::IsDmsaCapableDCRequired(_UNICODE_STRING *)
0x180067217  mov     ecx, esi
0x180067219  xor     r9d, r9d
0x18006721c  bts     ecx, 19h
0x180067220  test    al, al
0x180067222  cmovz   ecx, esi; unsigned int
0x180067225  call    ?KerbConsolidateDsVersionAndKeyListFlags@@YAKK@Z; KerbConsolidateDsVersionAndKeyListFlags(ulong)
0x18006722a  and     ebx, 0F017FFEFh
0x180067230  mov     r12d, eax
0x180067233  or      r12d, ebx
0x180067236  mov     rbx, [rbp+60h+String1]
0x18006723a  cmp     [rbp+60h+arg_38], r9
0x180067241  jnz     loc_180067315
0x180067247  cmp     [rbp+60h+arg_48], r9b
0x18006724e  jnz     loc_180067315
0x180067254  lea     r8, [rsp+160h+TokenHandle]; struct _KERB_PIN_KDC_ENTRY **
0x180067259  mov     edx, r12d; unsigned int
0x18006725c  mov     rcx, rbx; String1
0x18006725f  call    ?KerbLocatePinKdcEntry@@YAJPEAU_UNICODE_STRING@@KPEAPEAU_KERB_PIN_KDC_ENTRY@@@Z; KerbLocatePinKdcEntry(_UNICODE_STRING *,ulong,_KERB_PIN_KDC_ENTRY * *)
0x180067264  xor     r9d, r9d
0x180067267  mov     edi, eax
0x180067269  test    eax, eax
0x18006726b  jns     loc_1800672F3
0x180067271  mov     dword ptr [rsp+160h+var_130], r12d
0x180067276  lea     r9, aFailedToLocate; "Failed to locate a pin kdc entry for do"...
0x18006727d  mov     dword ptr [rsp+160h+var_138], eax
0x180067281  lea     rdx, aKerbmakesocket_3; "KerbMakeSocketCallInternal"
0x180067288  mov     r8d, 0CD1h
0x18006728e  mov     qword ptr [rsp+160h+var_140], rbx
0x180067293  mov     ecx, 1
0x180067298  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18006729d  mov     r15, [rsp+160h+TokenHandle]
0x1800672a2  mov     esi, r14d
0x1800672a5  xor     r9d, r9d
0x1800672a8  cmp     byte ptr [rbp+60h+arg_18], r9b
0x1800672af  jnz     loc_180067A5E
0x1800672b5  test    edi, edi
0x1800672b7  jns     loc_180067A4E
0x1800672bd  cmp     esi, cs:?KerbGlobalKdcSendRetries@@3KA; ulong KerbGlobalKdcSendRetries
0x1800672c3  jnz     loc_180067A5E
0x1800672c9  lea     r9, aWeLookToBeTimi; "We look to be timing out on UDP \n"
0x1800672d0  mov     r8d, 0E52h
0x1800672d6  lea     rdx, aKerbmakesocket_3; "KerbMakeSocketCallInternal"
0x1800672dd  mov     ecx, 1
0x1800672e2  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800672e7  mov     ecx, edi; int
0x1800672e9  call    ?KerbReportTransportError@@YAXJ@Z; KerbReportTransportError(long)
0x1800672ee  jmp     loc_180067A5B
0x1800672f3  mov     r15, [rsp+160h+TokenHandle]
0x1800672f8  test    r15, r15
0x1800672fb  jz      short loc_180067315
0x1800672fd  mov     [rbp+60h+var_68], r9d
0x180067301  movups  xmm0, xmmword ptr [r15+28h]
0x180067306  movdqu  [rbp+60h+var_88], xmm0
0x18006730b  movups  xmm1, xmmword ptr [r15+38h]
0x180067310  movdqu  [rbp+60h+var_78], xmm1
0x180067315  mov     esi, r14d
0x180067318  test    esi, esi
0x18006731a  jz      short loc_180067330
0x18006731c  test    r15, r15
0x18006731f  jnz     loc_180067955
0x180067325  or      r12d, 1
0x180067329  add     r13d, cs:?KerbGlobalKdcCallBackoff@@3KA; ulong KerbGlobalKdcCallBackoff
0x180067330  cmp     [rbp+60h+arg_38], r9
0x180067337  jz      short loc_180067346
0x180067339  test    esi, esi
0x18006733b  jnz     short loc_180067346
0x18006733d  mov     rcx, [rbp+60h+arg_38]
0x180067344  jmp     short loc_18006734F
0x180067346  test    r15, r15
0x180067349  jz      short loc_180067356
0x18006734b  lea     rcx, [rbp+60h+var_D0]
0x18006734f  mov     [rsp+160h+var_110], rcx
0x180067354  jmp     short loc_1800673BE
0x180067356  call    ?IsEnabled@Kerberos@Ntlmless@@YA_NXZ; Ntlmless::Kerberos::IsEnabled(void)
0x18006735b  mov     r9b, [rbp+60h+arg_20]; unsigned __int8
0x180067362  test    al, al
0x180067364  mov     rdx, [rbp+60h+String2]; String2
0x180067368  lea     rax, [rsp+160h+var_110]
0x18006736d  mov     r8d, r12d; unsigned int
0x180067370  mov     rcx, rbx; String1
0x180067373  jz      short loc_180067398
0x180067375  mov     [rsp+160h+var_130], rax; struct _KERB_BINDING_CACHE_ENTRY **
0x18006737a  mov     rax, [rbp+60h+arg_60]
0x180067381  mov     eax, [rax]
0x180067383  mov     dword ptr [rsp+160h+var_138], eax; unsigned int
0x180067387  mov     eax, [rbp+60h+arg_18]
0x18006738d  mov     [rsp+160h+var_140], al; unsigned __int8
0x180067391  call    ?KerbGetKdcBindingEx@@YAJPEAU_UNICODE_STRING@@0KEEKPEAPEAU_KERB_BINDING_CACHE_ENTRY@@@Z; KerbGetKdcBindingEx(_UNICODE_STRING *,_UNICODE_STRING *,ulong,uchar,uchar,ulong,_KERB_BINDING_CACHE_ENTRY * *)
0x180067396  jmp     short loc_1800673AC
0x180067398  mov     [rsp+160h+var_138], rax; struct _KERB_BINDING_CACHE_ENTRY **
0x18006739d  mov     eax, [rbp+60h+arg_18]
0x1800673a3  mov     [rsp+160h+var_140], al; unsigned __int8
0x1800673a7  call    ?KerbGetKdcBinding@@YAJPEAU_UNICODE_STRING@@0KEEPEAPEAU_KERB_BINDING_CACHE_ENTRY@@@Z; KerbGetKdcBinding(_UNICODE_STRING *,_UNICODE_STRING *,ulong,uchar,uchar,_KERB_BINDING_CACHE_ENTRY * *)
0x1800673ac  xor     r9d, r9d
0x1800673af  mov     edi, eax
0x1800673b1  test    eax, eax
0x1800673b3  js      loc_1800679D1
0x1800673b9  mov     rcx, [rsp+160h+var_110]
0x1800673be  cmp     [rbp+60h+arg_58], r9
0x1800673c5  jz      short loc_18006740A
0x1800673c7  mov     rcx, [rbp+60h+arg_58]
0x1800673ce  call    KerbFreeString
0x1800673d3  mov     rdx, [rsp+160h+var_110]
0x1800673d8  xor     r10d, r10d
0x1800673db  mov     rcx, [rbp+60h+arg_58]; struct _UNICODE_STRING *
0x1800673e2  cmp     [rdx+78h], r10w
0x1800673e7  jz      short loc_1800673EF
0x1800673e9  add     rdx, 78h ; 'x'
0x1800673ed  jmp     short loc_1800673F3
0x1800673ef  add     rdx, 58h ; 'X'; struct _UNICODE_STRING *
0x1800673f3  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x1800673f8  xor     r9d, r9d
0x1800673fb  mov     edi, eax
0x1800673fd  test    eax, eax
0x1800673ff  js      loc_18006795F
0x180067405  mov     rcx, [rsp+160h+var_110]
0x18006740a  test    dword ptr [rcx+74h], 40000000h
0x180067411  mov     r10d, 1
0x180067417  jnz     short loc_18006743C
0x180067419  mov     edx, [rbp+60h+arg_18]
0x18006741f  mov     r8, [rbp+60h+arg_28]
0x180067426  mov     eax, cs:?KerbGlobalMaxDatagramSize@@3KA; ulong KerbGlobalMaxDatagramSize
0x18006742c  movzx   edx, dl
0x18006742f  cmp     [r8], eax
0x180067432  cmova   edx, r10d
0x180067436  mov     [rbp+60h+arg_18], edx
0x18006743c  mov     rdx, [rbp+60h+arg_50]
0x180067443  cmp     [rdx], r9b
0x180067446  jnz     short loc_180067453
0x180067448  mov     eax, [rcx+6Ch]
0x18006744b  shr     eax, 7
0x18006744e  and     al, r10b
0x180067451  mov     [rdx], al
0x180067453  cmp     [rcx+74h], r9d
0x180067457  jge     loc_1800676ED
0x18006745d  mov     [rsp+160h+TokenHandle], r9
0x180067462  mov     r8b, r10b; OpenAsSelf
0x180067465  lea     r9, [rsp+160h+TokenHandle]; TokenHandle
0x18006746a  mov     edx, 0Ch; DesiredAccess
0x18006746f  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180067476  call    cs:__imp_NtOpenThreadToken
0x18006747c  mov     ebx, eax
0x18006747e  test    eax, eax
0x180067480  js      short loc_18006748A
0x180067482  call    cs:__imp_RevertToSelf
0x180067488  jmp     short loc_180067496
0x18006748a  cmp     ebx, 0C000007Ch
0x180067490  jnz     loc_180067982
0x180067496  xor     ebx, ebx
0x180067498  xorps   xmm0, xmm0
0x18006749b  movups  [rsp+160h+var_100], xmm0
0x1800674a0  cmp     [rbp+60h+arg_20], bl
0x1800674a6  jnz     loc_180067571
0x1800674ac  lea     r9, aCallingKdcDire; "Calling kdc directly\n"
0x1800674b3  mov     r8d, 0D6Eh
0x1800674b9  lea     rdx, aKerbmakesocket_3; "KerbMakeSocketCallInternal"
0x1800674c0  lea     ecx, [rbx+3]
0x1800674c3  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800674c8  call    ?KerbBeginKdcCall@@YAXXZ; KerbBeginKdcCall(void)
0x1800674cd  mov     rax, cs:?KerbGlobalKerbKdcCallInfo@@3PEAU_KERB_KDC_CALL_INFO@@EA; _KERB_KDC_CALL_INFO * KerbGlobalKerbKdcCallInfo
0x1800674d4  test    rax, rax
0x1800674d7  jz      loc_18006761D
0x1800674dd  mov     rcx, [rbp+60h+arg_60]
0x1800674e4  xor     r8d, r8d
0x1800674e7  mov     r9, [rbp+60h+arg_28]
0x1800674ee  xor     edx, edx
0x1800674f0  mov     rax, [rax+8]
0x1800674f4  mov     [rsp+160h+var_138], rcx
0x1800674f9  lea     rcx, [rsp+160h+var_100]
0x1800674fe  mov     qword ptr [rsp+160h+var_140], rcx
0x180067503  xor     ecx, ecx
0x180067505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006750a  mov     esi, eax
0x18006750c  cmp     eax, 80000002h
0x180067511  jz      loc_180067622
0x180067517  mov     edx, dword ptr [rsp+160h+var_100]
0x18006751b  test    edx, edx
0x18006751d  jz      short loc_180067553
0x18006751f  cmp     qword ptr [rsp+160h+var_100+8], rbx
0x180067524  jz      short loc_180067566
0x180067526  mov     rcx, [rbp+60h+arg_30]; struct _KERB_MESSAGE_BUFFER *
0x18006752d  lea     rdx, [rsp+160h+var_100]; struct _KERB_MESSAGE_BUFFER *
0x180067532  call    ?KerbCopyKerbMessageBuffer@@YAJPEAU_KERB_MESSAGE_BUFFER@@0@Z; KerbCopyKerbMessageBuffer(_KERB_MESSAGE_BUFFER *,_KERB_MESSAGE_BUFFER *)
0x180067537  mov     rcx, qword ptr [rsp+160h+var_100+8]
0x18006753c  mov     edi, eax
0x18006753e  mov     rax, cs:?KerbGlobalKerbKdcCallInfo@@3PEAU_KERB_KDC_CALL_INFO@@EA; _KERB_KDC_CALL_INFO * KerbGlobalKerbKdcCallInfo
0x180067545  mov     rax, [rax+18h]
0x180067549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006754e  jmp     loc_180067622
0x180067553  mov     rax, qword ptr [rsp+160h+var_100+8]
0x180067558  test    rax, rax
0x18006755b  jz      short loc_180067566
0x18006755d  shr     rax, 10h
0x180067561  movzx   ecx, ax
0x180067564  jmp     short loc_180067569
0x180067566  mov     rcx, rbx
0x180067569  mov     r8d, 0D8Bh
0x18006756f  jmp     short loc_1800675DE
0x180067571  call    ?KerbBeginKdcCall@@YAXXZ; KerbBeginKdcCall(void)
0x180067576  mov     rax, cs:?KerbGlobalKerbKdcCallInfo@@3PEAU_KERB_KDC_CALL_INFO@@EA; _KERB_KDC_CALL_INFO * KerbGlobalKerbKdcCallInfo
0x18006757d  test    rax, rax
0x180067580  jz      loc_18006761D
0x180067586  mov     r9, [rbp+60h+arg_28]
0x18006758d  lea     rcx, [rbp+60h+arg_40]
0x180067594  mov     rax, [rax+10h]
0x180067598  xor     r8d, r8d
0x18006759b  mov     [rsp+160h+var_138], rcx
0x1800675a0  xor     edx, edx
0x1800675a2  lea     rcx, [rsp+160h+var_100]
0x1800675a7  mov     [rbp+60h+arg_40], ebx
0x1800675ad  mov     qword ptr [rsp+160h+var_140], rcx
0x1800675b2  xor     ecx, ecx
0x1800675b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800675b9  mov     esi, eax
0x1800675bb  cmp     eax, 80000002h
0x1800675c0  jz      short loc_180067622
0x1800675c2  mov     edx, dword ptr [rsp+160h+var_100]
0x1800675c6  test    edx, edx
0x1800675c8  jz      short loc_18006760A
0x1800675ca  cmp     qword ptr [rsp+160h+var_100+8], rbx
0x1800675cf  jnz     loc_180067526
0x1800675d5  mov     rcx, rbx
0x1800675d8  mov     r8d, 0DB5h
0x1800675de  mov     [rsp+160h+var_130], rcx
0x1800675e3  lea     r9, aKerbmakesocket_2; "KerbMakeSocketCall direct kdc call retu"...
0x1800675ea  mov     dword ptr [rsp+160h+var_138], edx
0x1800675ee  mov     ecx, 1
0x1800675f3  lea     rdx, aKerbmakesocket_3; "KerbMakeSocketCallInternal"
0x1800675fa  mov     dword ptr [rsp+160h+var_140], esi
  ... truncated ...
```
