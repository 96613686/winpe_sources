# RRasRoutingDomainConfig::GetConfigParam(_RRAS_RD_CONFIG_TYPE,int,ulong *,void *)

- ea: `0x180047ff4`
- end: `0x18004894d`
- name: `?GetConfigParam@RRasRoutingDomainConfig@@QEAAKW4_RRAS_RD_CONFIG_TYPE@@HPEAKPEAX@Z`
- size: `2393`
- prototype: `__int64 __fastcall(__int64, int, int, unsigned int *, char *Destination)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x1800490a0`

## callees

- `0x180008860`
- `0x180030498`
- `0x180042bc4`
- `0x18004480c`
- `0x180044e6c`
- `0x1800454dc`
- `0x180045668`
- `0x1800458bc`
- `0x180045c14`
- `0x180047ff4`
- `0x18004b690`
- `0x18004bca0`
- `0x18004be7c`
- `0x18004bf80`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18004866f`
- `msvcrt!memcpy_s` at `0x18004866f`

## string_xrefs

- `0x18004807a`: `RRasRoutingDomainConfig::GetConfigParam`
- `0x180048148`: `RRasRoutingDomainConfig::GetConfigParam`
- `0x180048258`: `RRasRoutingDomainConfig::GetConfigParam`
- `0x1800482f4`: `RRasRoutingDomainConfig::GetConfigParam`
- `0x1800483a3`: `RRasRoutingDomainConfig::GetConfigParam`
- `0x18004840e`: `RRasRoutingDomainConfig::GetConfigParam`
- `0x1800484c5`: `RRasRoutingDomainConfig::GetConfigParam`
- `0x1800485d2`: `RRasRoutingDomainConfig::GetConfigParam`
- `0x1800486ef`: `RRasRoutingDomainConfig::GetConfigParam`
- `0x1800487d1`: `RRasRoutingDomainConfig::GetConfigParam`
- `0x180048158`: `%s: Insufficient buffer for config type %d`
- `0x180048267`: `%s: Insufficient buffer for config type %d`
- `0x18004830a`: `%s: Insufficient buffer for config type %d`
- `0x18004841d`: `%s: Insufficient buffer for config type %d`
- `0x1800486ff`: `%s: Insufficient buffer for config type %d`
- `0x1800487e1`: `%s: Insufficient buffer for config type %d`
- `0x18004878c`: `%s: ReadQoSPoliciesFromRegistry failed for QoS policies: %d`
- `0x180048863`: `%s: Refresh failed for Accounting config: %d`
- `0x1800488b6`: `GetConfigParam: Insufficient buffer for config type %d`
- `0x1800486b3`: `%s: Refresh failed for DialIn config: %d`
- `0x1800485e5`: `%s: set config not supported for cfg type: %d`

## pseudocode

```c
__int64 __fastcall RRasRoutingDomainConfig::GetConfigParam(
        __int64 a1,
        int a2,
        int a3,
        unsigned int *a4,
        char *Destination)
{
  __int64 v9; // r8
  unsigned int v10; // ebx
  __int64 v11; // r9
  unsigned int v12; // r13d
  const struct _GUID *v13; // r9
  int v14; // eax
  __int64 v15; // r9
  int v16; // r8d
  __int64 v18; // r9
  const struct _GUID *v19; // r9
  const struct _GUID *v20; // r9
  unsigned int v21; // eax
  const struct _GUID *v22; // r9
  unsigned int AccountingConfig; // eax
  const wchar_t *v24; // rdx
  const struct _GUID *v25; // r9
  __int64 v26; // r8
  __int64 v27; // r9
  const void *v28; // r8
  rsize_t v29; // r9
  const struct _GUID *v30; // r9
  const struct _GUID *v31; // r9
  __int64 v32; // rax
  unsigned int v33; // r15d
  const struct _GUID *v34; // r9
  GUID v36; // [rsp+40h] [rbp-C0h] BYREF
  int v37; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v38; // [rsp+54h] [rbp-ACh]
  __int128 v39; // [rsp+64h] [rbp-9Ch]
  int v40; // [rsp+74h] [rbp-8Ch]
  int v41; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v42[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v41 = 0;
  memset_0(v42, 0, sizeof(v42));
  v37 = 0;
  v40 = 0;
  v38 = 0;
  v39 = 0;
  if ( !Destination )
  {
    if ( (_QWORD)xmmword_180078C50 )
    {
      LOWORD(v41) = 0;
      FormatRRASErrorString(&v41, L"%hs(Line#%d): Invalid parameter.", "RRasRoutingDomainConfig::GetConfigParam", 2344);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180078C50,
        &v41);
    }
    return 87;
  }
  v11 = 512;
  v12 = a2 & 0x80000000;
  v10 = 0;
  if ( a2 <= 512 )
  {
    if ( a2 != 512 )
    {
      if ( a2 != 1 )
      {
        if ( a2 == 2 )
        {
          if ( *a4 < 0x14 )
          {
            if ( (_QWORD)xmmword_180078C60 )
            {
              LOWORD(v41) = 0;
              LOWORD(v37) = 0;
              v36 = GUID_NULL;
              FormatRRASErrorString(
                &v41,
                L"%s: Insufficient buffer for config type %d",
                L"RRasRoutingDomainConfig::GetConfigParam",
                2);
              v20 = &v36;
              if ( a1 != -516 )
                v20 = (const struct _GUID *)(a1 + 516);
              gCfgStoreParamTemplateFunc(
                gCfgStoreEtwContext,
                (const struct _EVENT_DESCRIPTOR *)xmmword_180078C60,
                (const unsigned __int16 *)&v41,
                v20,
                0,
                (const unsigned __int16 *)&v37);
            }
            *a4 = 20;
            return 122;
          }
          if ( a3 )
          {
            v21 = RRasRoutingDomainConfig::PopulateIpv6AddrPool((RRasRoutingDomainConfig *)a1);
            v10 = v21;
            if ( v21 )
            {
              if ( v21 != 1168 )
              {
                if ( !(_QWORD)xmmword_180078C60 )
                  return v10;
                LOWORD(v41) = 0;
                LOWORD(v37) = 0;
                v36 = GUID_NULL;
                FormatRRASErrorString(
                  &v41,
                  L"%s: Refresh failed for IPv6 address pool: %d",
                  L"RRasRoutingDomainConfig::GetConfigParam",
                  v21);
                goto LABEL_68;
              }
            }
          }
          return (unsigned int)RRasRoutingDomainConfig::CopyIpv6AddrPool(
                                 (RRasRoutingDomainConfig *)a1,
                                 (struct _MPRI_IPV6_CONFIG_1 *)Destination,
                                 v9,
                                 (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))v11);
        }
        if ( a2 == 4 )
          return v10;
        if ( a2 != 8 )
        {
          switch ( a2 )
          {
            case 32:
              if ( *a4 < 0x10 )
              {
                if ( (_QWORD)xmmword_180078C60 )
                {
                  v15 = 32;
                  goto LABEL_57;
                }
LABEL_60:
                *a4 = 16;
                return 122;
              }
              v16 = 1;
              break;
            case 128:
              if ( *a4 < 0x10 )
              {
                if ( (_QWORD)xmmword_180078C60 )
                {
                  v15 = 128;
LABEL_57:
                  LOWORD(v37) = 0;
                  LOWORD(v41) = 0;
                  v36 = GUID_NULL;
                  FormatRRASErrorString(
                    &v41,
                    L"%s: Insufficient buffer for config type %d",
                    L"RRasRoutingDomainConfig::GetConfigParam",
                    v15);
                  v22 = &v36;
                  if ( a1 != -516 )
                    v22 = (const struct _GUID *)(a1 + 516);
                  gCfgStoreParamTemplateFunc(
                    gCfgStoreEtwContext,
                    (const struct _EVENT_DESCRIPTOR *)xmmword_180078C60,
                    (const unsigned __int16 *)&v41,
                    v22,
                    0,
                    (const unsigned __int16 *)&v37);
                  goto LABEL_60;
                }
                goto LABEL_60;
              }
              v16 = 0;
              break;
            case 256:
              if ( *a4 < 4 )
              {
                if ( (_QWORD)xmmword_180078C60 )
                {
                  v11 = 256;
LABEL_17:
                  LOWORD(v41) = 0;
                  LOWORD(v37) = 0;
                  v36 = GUID_NULL;
                  FormatRRASErrorString(
                    &v41,
                    L"%s: Insufficient buffer for config type %d",
                    L"RRasRoutingDomainConfig::GetConfigParam",
                    v11);
                  v13 = &v36;
                  if ( a1 != -516 )
                    v13 = (const struct _GUID *)(a1 + 516);
                  gCfgStoreParamTemplateFunc(
                    gCfgStoreEtwContext,
                    (const struct _EVENT_DESCRIPTOR *)xmmword_180078C60,
                    (const unsigned __int16 *)&v41,
                    v13,
                    0,
                    (const unsigned __int16 *)&v37);
                }
LABEL_20:
                *a4 = 4;
                return 122;
              }
              if ( (*(_BYTE *)(a1 + 532) & 1) == 0 )
              {
                *(_DWORD *)Destination = 0;
                return 1168;
              }
              v14 = *(_DWORD *)(a1 + 540);
LABEL_24:
              *(_DWORD *)Destination = v14;
              return v10;
            default:
              goto LABEL_83;
          }
          return (unsigned int)RRasRoutingDomainConfig::CopyTransportInfo(
                                 (RRasRoutingDomainConfig *)a1,
                                 v12,
                                 v16,
                                 (struct _MPRI_TRANSPORT_INFO_1 *)Destination);
        }
        if ( *a4 >= 0x68 )
          return (unsigned int)RRasRoutingDomainConfig::CopyIkev2Config(
                                 (RRasRoutingDomainConfig *)a1,
                                 (struct _IKEV2_TUNNEL_CONFIG_PARAMS_4 *)Destination);
        if ( (_QWORD)xmmword_180078C60 )
        {
          v18 = 8;
LABEL_37:
          LOWORD(v37) = 0;
          LOWORD(v41) = 0;
          v36 = GUID_NULL;
          FormatRRASErrorString(
            &v41,
            L"%s: Insufficient buffer for config type %d",
            L"RRasRoutingDomainConfig::GetConfigParam",
            v18);
          v19 = &v36;
          if ( a1 != -516 )
            v19 = (const struct _GUID *)(a1 + 516);
          gCfgStoreParamTemplateFunc(
            gCfgStoreEtwContext,
            (const struct _EVENT_DESCRIPTOR *)xmmword_180078C60,
            (const unsigned __int16 *)&v41,
            v19,
            0,
            (const unsigned __int16 *)&v37);
        }
LABEL_40:
        *a4 = 104;
        return 122;
      }
      if ( *a4 < 0x10 )
      {
        if ( (_QWORD)xmmword_180078C60 )
        {
          v15 = 1;
          goto LABEL_57;
        }
        goto LABEL_60;
      }
      if ( !a3 )
        return (unsigned int)RRasRoutingDomainConfig::CopyIpv4AddrPool(
                               (RRasRoutingDomainConfig *)a1,
                               v12,
                               (struct _MPRI_IPV4_CONFIG_1 *)Destination);
      AccountingConfig = RRasRoutingDomainConfig::PopulateIpv4AddrPool((RRasRoutingDomainConfig *)a1);
      if ( (v10 = AccountingConfig) == 0 || AccountingConfig == 1168 )
        return (unsigned int)RRasRoutingDomainConfig::CopyIpv4AddrPool(
                               (RRasRoutingDomainConfig *)a1,
                               v12,
                               (struct _MPRI_IPV4_CONFIG_1 *)Destination);
      if ( !(_QWORD)xmmword_180078C60 )
        return v10;
      v24 = L"%s: Refresh failed for IPv4 address pool: %d";
      goto LABEL_67;
    }
    if ( *a4 >= 4 )
    {
      v14 = *(_DWORD *)(a1 + 532);
      goto LABEL_24;
    }
LABEL_74:
    if ( (_QWORD)xmmword_180078C60 )
      goto LABEL_17;
    goto LABEL_20;
  }
  v26 = 1024;
  if ( a2 == 1024 )
  {
    v32 = -1;
    do
      ++v32;
    while ( *(_WORD *)(a1 + 2 * v32) );
    v33 = 2 * v32 + 2;
    if ( *a4 >= v33 )
    {
      StringCbCopyW((STRSAFE_LPWSTR)Destination, v33, (STRSAFE_LPCWSTR)a1);
      return v10;
    }
    if ( (_QWORD)xmmword_180078C60 )
    {
      LOWORD(v41) = 0;
      LOWORD(v37) = 0;
      v36 = GUID_NULL;
      FormatRRASErrorString(&v41, L"GetConfigParam: Insufficient buffer for config type %d");
      v34 = &v36;
      if ( a1 != -516 )
        v34 = (const struct _GUID *)(a1 + 516);
      gCfgStoreParamTemplateFunc(
        gCfgStoreEtwContext,
        (const struct _EVENT_DESCRIPTOR *)xmmword_180078C60,
        (const unsigned __int16 *)&v41,
        v34,
        0,
        (const unsigned __int16 *)&v37);
    }
    *a4 = v33;
    return 122;
  }
  v27 = 2048;
  if ( a2 == 2048 )
  {
    if ( *a4 < 8 )
    {
      if ( (_QWORD)xmmword_180078C60 )
      {
        LOWORD(v41) = 0;
        LOWORD(v37) = 0;
        v36 = GUID_NULL;
        FormatRRASErrorString(
          &v41,
          L"%s: Insufficient buffer for config type %d",
          L"RRasRoutingDomainConfig::GetConfigParam");
        v31 = &v36;
        if ( a1 != -516 )
          v31 = (const struct _GUID *)(a1 + 516);
        gCfgStoreParamTemplateFunc(
          gCfgStoreEtwContext,
          (const struct _EVENT_DESCRIPTOR *)xmmword_180078C60,
          (const unsigned __int16 *)&v41,
          v31,
          0,
          (const unsigned __int16 *)&v37);
      }
      *a4 = 8;
      return 122;
    }
    if ( !a3 )
      return (unsigned int)RRasRoutingDomainConfig::CopyAccoountingConfig(
                             (RRasRoutingDomainConfig *)a1,
                             (struct _MPRI_ACCOUNTING_CONFIG_1 *)Destination,
                             v26,
                             (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))v27);
    AccountingConfig = RRasRoutingDomainConfig::ReadAccountingConfig((RRasRoutingDomainConfig *)a1);
    if ( (v10 = AccountingConfig) == 0 )
      return (unsigned int)RRasRoutingDomainConfig::CopyAccoountingConfig(
                             (RRasRoutingDomainConfig *)a1,
                             (struct _MPRI_ACCOUNTING_CONFIG_1 *)Destination,
                             v26,
                             (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))v27);
    if ( !(_QWORD)xmmword_180078C60 )
      return v10;
    v24 = L"%s: Refresh failed for Accounting config: %d";
    goto LABEL_67;
  }
  if ( a2 != 0x2000 )
  {
    v18 = 0x4000;
    if ( a2 == 0x4000 )
    {
      if ( *a4 < 0x68 )
      {
        if ( (_QWORD)xmmword_180078C60 )
          goto LABEL_37;
        goto LABEL_40;
      }
      if ( !a3 )
        return (unsigned int)RRasRoutingDomainConfig::CopyDialInConfig(
                               (RRasRoutingDomainConfig *)a1,
                               v12,
                               (struct _MPRI_DIAL_IN_CONFIG_1 *)Destination);
      AccountingConfig = RRasRoutingDomainConfig::ReadDialInConfig((RRasRoutingDomainConfig *)a1);
      if ( (v10 = AccountingConfig) == 0 )
        return (unsigned int)RRasRoutingDomainConfig::CopyDialInConfig(
                               (RRasRoutingDomainConfig *)a1,
                               v12,
                               (struct _MPRI_DIAL_IN_CONFIG_1 *)Destination);
      if ( !(_QWORD)xmmword_180078C60 )
        return v10;
      v24 = L"%s: Refresh failed for DialIn config: %d";
LABEL_67:
      LOWORD(v37) = 0;
      LOWORD(v41) = 0;
      v36 = GUID_NULL;
      FormatRRASErrorString(&v41, v24, L"RRasRoutingDomainConfig::GetConfigParam", AccountingConfig);
LABEL_68:
      v25 = &v36;
      if ( a1 != -516 )
        v25 = (const struct _GUID *)(a1 + 516);
      gCfgStoreParamTemplateFunc(
        gCfgStoreEtwContext,
        (const struct _EVENT_DESCRIPTOR *)xmmword_180078C60,
        (const unsigned __int16 *)&v41,
        v25,
        0,
        (const unsigned __int16 *)&v37);
      return v10;
    }
    v11 = 0x8000;
    if ( a2 == 0x8000 )
    {
      if ( *a4 < 4 )
        goto LABEL_74;
      if ( a3 )
        RegGetDword(*(_QWORD *)(a1 + 824), L"RouterType", 0, 0xFFFFFFFFLL, 0, a1 + 536);
      v28 = (const void *)(a1 + 536);
      v29 = 4;
    }
    else
    {
      v15 = 0x10000;
      if ( a2 != 0x10000 )
      {
LABEL_83:
        v10 = 50;
        if ( !(_QWORD)xmmword_180078C60 )
          return v10;
        LOWORD(v41) = 0;
        LOWORD(v37) = 0;
        v36 = GUID_NULL;
        FormatRRASErrorString(
          &v41,
          L"%s: set config not supported for cfg type: %d",
          L"RRasRoutingDomainConfig::GetConfigParam",
          (unsigned int)a2);
        goto LABEL_68;
      }
      if ( *a4 < 0x10 )
      {
        if ( (_QWORD)xmmword_180078C60 )
          goto LABEL_57;
        goto LABEL_60;
      }
      v28 = (const void *)(a1 + 840);
      v29 = 16;
    }
    return (unsigned int)memcpy_s(Destination, *a4, v28, v29);
  }
  if ( *a4 < 0x1C )
  {
    if ( (_QWORD)xmmword_180078C60 )
    {
      LOWORD(v41) = 0;
      LOWORD(v37) = 0;
      v36 = GUID_NULL;
      FormatRRASErrorString(
        &v41,
        L"%s: Insufficient buffer for config type %d",
        L"RRasRoutingDomainConfig::GetConfigParam");
      v30 = &v36;
      if ( a1 != -516 )
        v30 = (const struct _GUID *)(a1 + 516);
      gCfgStoreParamTemplateFunc(
        gCfgStoreEtwContext,
        (const struct _EVENT_DESCRIPTOR *)xmmword_180078C60,
        (const unsigned __int16 *)&v41,
        v30,
        0,
        (const unsigned __int16 *)&v37);
    }
    *a4 = 28;
    return 122;
  }
  if ( !a3 || (AccountingConfig = ReadQoSPoliciesFromRegistry(*(HKEY *)(a1 + 824)), (v10 = AccountingConfig) == 0) )
  {
    *(_OWORD *)Destination = *(_OWORD *)(a1 + 544);
    *(_OWORD *)(Destination + 12) = *(_OWORD *)(a1 + 556);
    return v10;
  }
  if ( (_QWORD)xmmword_180078C60 )
  {
    v24 = L"%s: ReadQoSPoliciesFromRegistry failed for QoS policies: %d";
    goto LABEL_67;
  }
  return v10;
}

```

## disassembly

```asm
0x180047ff4  mov     [rsp-8+arg_10], rbx
0x180047ff9  push    rbp
0x180047ffa  push    rsi
0x180047ffb  push    rdi
0x180047ffc  push    r12
0x180047ffe  push    r13
0x180048000  push    r14
0x180048002  push    r15
0x180048004  lea     rbp, [rsp-790h]
0x18004800c  sub     rsp, 890h
0x180048013  mov     rax, cs:__security_cookie
0x18004801a  xor     rax, rsp
0x18004801d  mov     [rbp+7C0h+var_40], rax
0x180048024  mov     r14, [rbp+7C0h+Destination]
0x18004802b  mov     r12d, r8d
0x18004802e  mov     r15d, edx
0x180048031  mov     rdi, rcx
0x180048034  xor     r13d, r13d
0x180048037  lea     rcx, [rbp+7C0h+var_83C]; void *
0x18004803b  xor     edx, edx; Val
0x18004803d  mov     [rbp+7C0h+var_840], r13d
0x180048041  mov     r8d, 7FCh; Size
0x180048047  mov     rsi, r9
0x18004804a  call    memset_0
0x18004804f  xor     edx, edx
0x180048051  xor     eax, eax
0x180048053  mov     [rsp+8C0h+var_870], edx
0x180048057  xorps   xmm0, xmm0
0x18004805a  mov     [rsp+8C0h+var_84C], eax
0x18004805e  movups  [rsp+8C0h+var_86C], xmm0
0x180048063  movups  [rsp+8C0h+var_85C], xmm0
0x180048068  test    r14, r14
0x18004806b  jnz     short loc_1800480BF
0x18004806d  cmp     qword ptr cs:xmmword_180078C50, rdx
0x180048074  jz      short loc_1800480B5
0x180048076  mov     word ptr [rbp+7C0h+var_840], dx
0x18004807a  lea     r8, aRrasroutingdom_14; "RRasRoutingDomainConfig::GetConfigParam"
0x180048081  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x180048088  mov     r9d, 928h
0x18004808e  lea     rcx, [rbp+7C0h+var_840]
0x180048092  call    FormatRRASErrorString
0x180048097  mov     rdx, qword ptr cs:xmmword_180078C50
0x18004809e  lea     r8, [rbp+7C0h+var_840]
0x1800480a2  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x1800480a9  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800480b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800480b5  mov     ebx, 57h ; 'W'
0x1800480ba  jmp     loc_180048921
0x1800480bf  mov     r13d, r15d
0x1800480c2  mov     r9d, 200h
0x1800480c8  and     r13d, 80000000h
0x1800480cf  mov     ebx, edx
0x1800480d1  cmp     r15d, r9d
0x1800480d4  jg      loc_180048563
0x1800480da  jz      loc_180048541
0x1800480e0  mov     ecx, r15d
0x1800480e3  sub     ecx, 1
0x1800480e6  jz      loc_1800483EA
0x1800480ec  sub     ecx, 1
0x1800480ef  jz      loc_1800482D7
0x1800480f5  sub     ecx, 2
0x1800480f8  jz      loc_180048921
0x1800480fe  sub     ecx, 4
0x180048101  jz      loc_180048234
0x180048107  sub     ecx, 18h
0x18004810a  jz      loc_1800481FE
0x180048110  sub     ecx, 60h ; '`'
0x180048113  jz      loc_1800481DC
0x180048119  cmp     ecx, 80h
0x18004811f  jnz     loc_1800485B5
0x180048125  cmp     dword ptr [rsi], 4
0x180048128  jnb     loc_1800481B8
0x18004812e  cmp     qword ptr cs:xmmword_180078C60, rdx
0x180048135  jz      short loc_1800481AD
0x180048137  mov     r9d, 100h
0x18004813d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180048144  mov     word ptr [rbp+7C0h+var_840], dx
0x180048148  lea     r8, aRrasroutingdom_33; "RRasRoutingDomainConfig::GetConfigParam"
0x18004814f  mov     word ptr [rsp+8C0h+var_870], dx
0x180048154  lea     rcx, [rbp+7C0h+var_840]
0x180048158  lea     rdx, aSInsufficientB; "%s: Insufficient buffer for config type"...
0x18004815f  movdqu  [rsp+8C0h+var_880], xmm0
0x180048165  call    FormatRRASErrorString
0x18004816a  mov     rdx, qword ptr cs:xmmword_180078C60
0x180048171  lea     rcx, [rdi+204h]
0x180048178  xor     r13d, r13d
0x18004817b  lea     rax, [rsp+8C0h+var_870]
0x180048180  test    rcx, rcx
0x180048183  mov     [rsp+8C0h+var_898], rax
0x180048188  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004818f  lea     r9, [rsp+8C0h+var_880]
0x180048194  cmovnz  r9, rcx
0x180048198  mov     [rsp+8C0h+var_8A0], r13
0x18004819d  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x1800481a4  lea     r8, [rbp+7C0h+var_840]
0x1800481a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800481ad  mov     dword ptr [rsi], 4
0x1800481b3  jmp     loc_180048478
0x1800481b8  test    byte ptr [rdi+214h], 1
0x1800481bf  jnz     short loc_1800481CE
0x1800481c1  mov     [r14], edx
0x1800481c4  mov     ebx, 490h
0x1800481c9  jmp     loc_180048921
0x1800481ce  mov     eax, [rdi+21Ch]
0x1800481d4  mov     [r14], eax
0x1800481d7  jmp     loc_180048921
0x1800481dc  cmp     dword ptr [rsi], 10h
0x1800481df  jnb     short loc_1800481F9
0x1800481e1  cmp     qword ptr cs:xmmword_180078C60, rdx
0x1800481e8  jz      loc_180048472
0x1800481ee  mov     r9d, 80h
0x1800481f4  jmp     loc_180048402
0x1800481f9  xor     r8d, r8d
0x1800481fc  jmp     short loc_180048221
0x1800481fe  cmp     dword ptr [rsi], 10h
0x180048201  jnb     short loc_18004821B
0x180048203  cmp     qword ptr cs:xmmword_180078C60, rdx
0x18004820a  jz      loc_180048472
0x180048210  mov     r9d, 20h ; ' '
0x180048216  jmp     loc_180048402
0x18004821b  mov     r8d, 1; int
0x180048221  mov     r9, r14; struct _MPRI_TRANSPORT_INFO_1 *
0x180048224  mov     edx, r13d; int
0x180048227  mov     rcx, rdi; this
0x18004822a  call    ?CopyTransportInfo@RRasRoutingDomainConfig@@AEAAKHHPEAU_MPRI_TRANSPORT_INFO_1@@@Z; RRasRoutingDomainConfig::CopyTransportInfo(int,int,_MPRI_TRANSPORT_INFO_1 *)
0x18004822f  jmp     loc_18004853A
0x180048234  cmp     dword ptr [rsi], 68h ; 'h'
0x180048237  jnb     loc_1800482C7
0x18004823d  cmp     qword ptr cs:xmmword_180078C60, rdx
0x180048244  jz      short loc_1800482BC
0x180048246  mov     r9d, 8
0x18004824c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180048253  mov     word ptr [rsp+8C0h+var_870], dx
0x180048258  lea     r8, aRrasroutingdom_33; "RRasRoutingDomainConfig::GetConfigParam"
0x18004825f  mov     word ptr [rbp+7C0h+var_840], dx
0x180048263  lea     rcx, [rbp+7C0h+var_840]
0x180048267  lea     rdx, aSInsufficientB; "%s: Insufficient buffer for config type"...
0x18004826e  movdqu  [rsp+8C0h+var_880], xmm0
0x180048274  call    FormatRRASErrorString
0x180048279  mov     rdx, qword ptr cs:xmmword_180078C60
0x180048280  lea     rcx, [rdi+204h]
0x180048287  xor     r13d, r13d
0x18004828a  lea     rax, [rsp+8C0h+var_870]
0x18004828f  test    rcx, rcx
0x180048292  mov     [rsp+8C0h+var_898], rax
0x180048297  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004829e  lea     r9, [rsp+8C0h+var_880]
0x1800482a3  cmovnz  r9, rcx
0x1800482a7  mov     [rsp+8C0h+var_8A0], r13
0x1800482ac  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x1800482b3  lea     r8, [rbp+7C0h+var_840]
0x1800482b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482bc  mov     dword ptr [rsi], 68h ; 'h'
0x1800482c2  jmp     loc_180048478
0x1800482c7  mov     rdx, r14; struct _IKEV2_TUNNEL_CONFIG_PARAMS_4 *
0x1800482ca  mov     rcx, rdi; this
0x1800482cd  call    ?CopyIkev2Config@RRasRoutingDomainConfig@@AEAAKPEAU_IKEV2_TUNNEL_CONFIG_PARAMS_4@@@Z; RRasRoutingDomainConfig::CopyIkev2Config(_IKEV2_TUNNEL_CONFIG_PARAMS_4 *)
0x1800482d2  jmp     loc_18004853A
0x1800482d7  cmp     dword ptr [rsi], 14h
0x1800482da  jnb     loc_18004836A
0x1800482e0  cmp     qword ptr cs:xmmword_180078C60, rdx
0x1800482e7  jz      short loc_18004835F
0x1800482e9  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800482f0  mov     word ptr [rbp+7C0h+var_840], dx
0x1800482f4  lea     r8, aRrasroutingdom_33; "RRasRoutingDomainConfig::GetConfigParam"
0x1800482fb  mov     word ptr [rsp+8C0h+var_870], dx
0x180048300  lea     rcx, [rbp+7C0h+var_840]
0x180048304  mov     r9d, 2
0x18004830a  lea     rdx, aSInsufficientB; "%s: Insufficient buffer for config type"...
0x180048311  movdqu  [rsp+8C0h+var_880], xmm0
0x180048317  call    FormatRRASErrorString
0x18004831c  mov     rdx, qword ptr cs:xmmword_180078C60
0x180048323  lea     rcx, [rdi+204h]
0x18004832a  xor     r13d, r13d
0x18004832d  lea     rax, [rsp+8C0h+var_870]
0x180048332  test    rcx, rcx
0x180048335  mov     [rsp+8C0h+var_898], rax
0x18004833a  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180048341  lea     r9, [rsp+8C0h+var_880]
0x180048346  cmovnz  r9, rcx
0x18004834a  mov     [rsp+8C0h+var_8A0], r13
0x18004834f  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180048356  lea     r8, [rbp+7C0h+var_840]
0x18004835a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004835f  mov     dword ptr [rsi], 14h
0x180048365  jmp     loc_180048478
0x18004836a  test    r12d, r12d
0x18004836d  jz      short loc_1800483DA
0x18004836f  mov     rcx, rdi; this
0x180048372  call    ?PopulateIpv6AddrPool@RRasRoutingDomainConfig@@AEAAKXZ; RRasRoutingDomainConfig::PopulateIpv6AddrPool(void)
0x180048377  xor     r13d, r13d
0x18004837a  mov     ebx, eax
0x18004837c  test    eax, eax
0x18004837e  jz      short loc_1800483DA
0x180048380  cmp     eax, 490h
0x180048385  jz      short loc_1800483DA
0x180048387  cmp     qword ptr cs:xmmword_180078C60, r13
0x18004838e  jz      loc_180048921
0x180048394  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004839b  mov     r9d, eax
0x18004839e  mov     word ptr [rbp+7C0h+var_840], r13w
0x1800483a3  lea     r8, aRrasroutingdom_33; "RRasRoutingDomainConfig::GetConfigParam"
0x1800483aa  mov     word ptr [rsp+8C0h+var_870], r13w
0x1800483b0  lea     rdx, aSRefreshFailed_0; "%s: Refresh failed for IPv6 address poo"...
0x1800483b7  lea     rcx, [rbp+7C0h+var_840]
0x1800483bb  movdqu  [rsp+8C0h+var_880], xmm0
0x1800483c1  call    FormatRRASErrorString
0x1800483c6  lea     rax, [rsp+8C0h+var_870]
0x1800483cb  mov     [rsp+8C0h+var_898], rax
0x1800483d0  mov     [rsp+8C0h+var_8A0], r13
0x1800483d5  jmp     loc_1800484F6
0x1800483da  mov     rdx, r14; struct _MPRI_IPV6_CONFIG_1 *
0x1800483dd  mov     rcx, rdi; this
0x1800483e0  call    ?CopyIpv6AddrPool@RRasRoutingDomainConfig@@AEAAKPEAU_MPRI_IPV6_CONFIG_1@@@Z; RRasRoutingDomainConfig::CopyIpv6AddrPool(_MPRI_IPV6_CONFIG_1 *)
0x1800483e5  jmp     loc_18004853A
0x1800483ea  cmp     dword ptr [rsi], 10h
0x1800483ed  jnb     loc_180048482
0x1800483f3  cmp     qword ptr cs:xmmword_180078C60, rdx
0x1800483fa  jz      short loc_180048472
0x1800483fc  mov     r9d, 1
0x180048402  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180048409  mov     word ptr [rsp+8C0h+var_870], dx
0x18004840e  lea     r8, aRrasroutingdom_33; "RRasRoutingDomainConfig::GetConfigParam"
0x180048415  mov     word ptr [rbp+7C0h+var_840], dx
0x180048419  lea     rcx, [rbp+7C0h+var_840]
0x18004841d  lea     rdx, aSInsufficientB; "%s: Insufficient buffer for config type"...
0x180048424  movdqu  [rsp+8C0h+var_880], xmm0
0x18004842a  call    FormatRRASErrorString
0x18004842f  mov     rdx, qword ptr cs:xmmword_180078C60
0x180048436  lea     rcx, [rdi+204h]
0x18004843d  xor     r13d, r13d
0x180048440  lea     rax, [rsp+8C0h+var_870]
0x180048445  test    rcx, rcx
0x180048448  mov     [rsp+8C0h+var_898], rax
0x18004844d  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180048454  lea     r9, [rsp+8C0h+var_880]
0x180048459  cmovnz  r9, rcx
0x18004845d  mov     [rsp+8C0h+var_8A0], r13
0x180048462  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180048469  lea     r8, [rbp+7C0h+var_840]
0x18004846d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048472  mov     dword ptr [rsi], 10h
0x180048478  mov     ebx, 7Ah ; 'z'
0x18004847d  jmp     loc_180048921
0x180048482  test    r12d, r12d
0x180048485  jz      loc_18004852C
0x18004848b  mov     rcx, rdi; this
0x18004848e  call    ?PopulateIpv4AddrPool@RRasRoutingDomainConfig@@AEAAKXZ; RRasRoutingDomainConfig::PopulateIpv4AddrPool(void)
0x180048493  xor     esi, esi
0x180048495  mov     ebx, eax
0x180048497  test    eax, eax
0x180048499  jz      loc_18004852C
0x18004849f  cmp     eax, 490h
0x1800484a4  jz      loc_18004852C
0x1800484aa  cmp     qword ptr cs:xmmword_180078C60, rsi
0x1800484b1  jz      loc_180048921
0x1800484b7  lea     rdx, aSRefreshFailed_2; "%s: Refresh failed for IPv4 address poo"...
0x1800484be  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800484c5  lea     r8, aRrasroutingdom_33; "RRasRoutingDomainConfig::GetConfigParam"
0x1800484cc  mov     word ptr [rsp+8C0h+var_870], si
0x1800484d1  mov     r9d, eax
0x1800484d4  mov     word ptr [rbp+7C0h+var_840], si
0x1800484d8  lea     rcx, [rbp+7C0h+var_840]
0x1800484dc  movdqu  [rsp+8C0h+var_880], xmm0
0x1800484e2  call    FormatRRASErrorString
0x1800484e7  lea     rax, [rsp+8C0h+var_870]
0x1800484ec  mov     [rsp+8C0h+var_898], rax
0x1800484f1  mov     [rsp+8C0h+var_8A0], rsi
0x1800484f6  mov     rdx, qword ptr cs:xmmword_180078C60
0x1800484fd  lea     rcx, [rdi+204h]
0x180048504  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004850b  lea     r9, [rsp+8C0h+var_880]
0x180048510  test    rcx, rcx
0x180048513  lea     r8, [rbp+7C0h+var_840]
0x180048517  cmovnz  r9, rcx
0x18004851b  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180048522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048527  jmp     loc_180048921
0x18004852c  mov     r8, r14; struct _MPRI_IPV4_CONFIG_1 *
0x18004852f  mov     edx, r13d; int
0x180048532  mov     rcx, rdi; this
0x180048535  call    ?CopyIpv4AddrPool@RRasRoutingDomainConfig@@AEAAKHPEAU_MPRI_IPV4_CONFIG_1@@@Z; RRasRoutingDomainConfig::CopyIpv4AddrPool(int,_MPRI_IPV4_CONFIG_1 *)
0x18004853a  mov     ebx, eax
0x18004853c  jmp     loc_180048921
0x180048541  cmp     dword ptr [rsi], 4
0x180048544  jnb     short loc_180048558
0x180048546  cmp     qword ptr cs:xmmword_180078C60, rdx
0x18004854d  jz      loc_1800481AD
0x180048553  jmp     loc_18004813D
0x180048558  mov     eax, [rdi+214h]
0x18004855e  jmp     loc_1800481D4
0x180048563  mov     r8d, 400h
0x180048569  cmp     r15d, r8d
0x18004856c  jz      loc_18004887F
0x180048572  mov     r9d, 800h
0x180048578  cmp     r15d, r9d
0x18004857b  jz      loc_1800487B4
0x180048581  mov     r9d, 2000h
0x180048587  cmp     r15d, r9d
0x18004858a  jz      loc_1800486D2
  ... truncated ...
```
