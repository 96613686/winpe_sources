# RRasRoutingDomainConfig::GetConfigParam(_RRAS_RD_CONFIG_TYPE,int,ulong *,void *)

- ea: `0x18003c810`
- end: `0x18003d169`
- name: `?GetConfigParam@RRasRoutingDomainConfig@@QEAAKW4_RRAS_RD_CONFIG_TYPE@@HPEAKPEAX@Z`
- size: `2393`
- prototype: `__int64 __fastcall(__int64, int, int, unsigned int *, char *Destination)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x18003d6bc`

## callees

- `0x180010dc4`
- `0x180034094`
- `0x180037308`
- `0x180038f1c`
- `0x1800394dc`
- `0x180039b4c`
- `0x180039cd8`
- `0x180039f2c`
- `0x18003a284`
- `0x18003c810`
- `0x1800400c4`
- `0x1800406cc`
- `0x1800408a8`
- `0x1800409ac`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18003ce8b`
- `msvcrt!memcpy_s` at `0x18003ce8b`

## string_xrefs

- `0x18003c896`: `RRasRoutingDomainConfig::GetConfigParam`
- `0x18003c964`: `RRasRoutingDomainConfig::GetConfigParam`
- `0x18003ca74`: `RRasRoutingDomainConfig::GetConfigParam`
- `0x18003cb10`: `RRasRoutingDomainConfig::GetConfigParam`
- `0x18003cbbf`: `RRasRoutingDomainConfig::GetConfigParam`
- `0x18003cc2a`: `RRasRoutingDomainConfig::GetConfigParam`
- `0x18003cce1`: `RRasRoutingDomainConfig::GetConfigParam`
- `0x18003cdee`: `RRasRoutingDomainConfig::GetConfigParam`
- `0x18003cf0b`: `RRasRoutingDomainConfig::GetConfigParam`
- `0x18003cfed`: `RRasRoutingDomainConfig::GetConfigParam`
- `0x18003c974`: `%s: Insufficient buffer for config type %d`
- `0x18003ca83`: `%s: Insufficient buffer for config type %d`
- `0x18003cb26`: `%s: Insufficient buffer for config type %d`
- `0x18003cc39`: `%s: Insufficient buffer for config type %d`
- `0x18003cf1b`: `%s: Insufficient buffer for config type %d`
- `0x18003cffd`: `%s: Insufficient buffer for config type %d`
- `0x18003cfa8`: `%s: ReadQoSPoliciesFromRegistry failed for QoS policies: %d`
- `0x18003d07f`: `%s: Refresh failed for Accounting config: %d`
- `0x18003d0d2`: `GetConfigParam: Insufficient buffer for config type %d`
- `0x18003cecf`: `%s: Refresh failed for DialIn config: %d`
- `0x18003ce01`: `%s: set config not supported for cfg type: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
    if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v41) = 0;
      FormatRRASErrorString(&v41, L"%hs(Line#%d): Invalid parameter.", "RRasRoutingDomainConfig::GetConfigParam", 2344);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
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
            if ( (_QWORD)xmmword_1800710A0 )
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
                (const struct _EVENT_DESCRIPTOR *)xmmword_1800710A0,
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
                if ( !(_QWORD)xmmword_1800710A0 )
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
                if ( (_QWORD)xmmword_1800710A0 )
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
                if ( (_QWORD)xmmword_1800710A0 )
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
                    (const struct _EVENT_DESCRIPTOR *)xmmword_1800710A0,
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
                if ( (_QWORD)xmmword_1800710A0 )
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
                    (const struct _EVENT_DESCRIPTOR *)xmmword_1800710A0,
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
        if ( (_QWORD)xmmword_1800710A0 )
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
            (const struct _EVENT_DESCRIPTOR *)xmmword_1800710A0,
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
        if ( (_QWORD)xmmword_1800710A0 )
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
      if ( !(_QWORD)xmmword_1800710A0 )
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
    if ( (_QWORD)xmmword_1800710A0 )
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
    if ( (_QWORD)xmmword_1800710A0 )
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
        (const struct _EVENT_DESCRIPTOR *)xmmword_1800710A0,
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
      if ( (_QWORD)xmmword_1800710A0 )
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
          (const struct _EVENT_DESCRIPTOR *)xmmword_1800710A0,
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
    if ( !(_QWORD)xmmword_1800710A0 )
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
        if ( (_QWORD)xmmword_1800710A0 )
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
      if ( !(_QWORD)xmmword_1800710A0 )
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
        (const struct _EVENT_DESCRIPTOR *)xmmword_1800710A0,
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
        if ( !(_QWORD)xmmword_1800710A0 )
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
        if ( (_QWORD)xmmword_1800710A0 )
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
    if ( (_QWORD)xmmword_1800710A0 )
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
        (const struct _EVENT_DESCRIPTOR *)xmmword_1800710A0,
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
  if ( (_QWORD)xmmword_1800710A0 )
  {
    v24 = L"%s: ReadQoSPoliciesFromRegistry failed for QoS policies: %d";
    goto LABEL_67;
  }
  return v10;
}

```

## disassembly

```asm
0x18003c810  mov     [rsp-8+arg_10], rbx
0x18003c815  push    rbp
0x18003c816  push    rsi
0x18003c817  push    rdi
0x18003c818  push    r12
0x18003c81a  push    r13
0x18003c81c  push    r14
0x18003c81e  push    r15
0x18003c820  lea     rbp, [rsp-790h]
0x18003c828  sub     rsp, 890h
0x18003c82f  mov     rax, cs:__security_cookie
0x18003c836  xor     rax, rsp
0x18003c839  mov     [rbp+7C0h+var_40], rax
0x18003c840  mov     r14, [rbp+7C0h+Destination]
0x18003c847  mov     r12d, r8d
0x18003c84a  mov     r15d, edx
0x18003c84d  mov     rdi, rcx
0x18003c850  xor     r13d, r13d
0x18003c853  lea     rcx, [rbp+7C0h+var_83C]; void *
0x18003c857  xor     edx, edx; Val
0x18003c859  mov     [rbp+7C0h+var_840], r13d
0x18003c85d  mov     r8d, 7FCh; Size
0x18003c863  mov     rsi, r9
0x18003c866  call    memset_0
0x18003c86b  xor     edx, edx
0x18003c86d  xor     eax, eax
0x18003c86f  mov     [rsp+8C0h+var_870], edx
0x18003c873  xorps   xmm0, xmm0
0x18003c876  mov     [rsp+8C0h+var_84C], eax
0x18003c87a  movups  [rsp+8C0h+var_86C], xmm0
0x18003c87f  movups  [rsp+8C0h+var_85C], xmm0
0x18003c884  test    r14, r14
0x18003c887  jnz     short loc_18003C8DB
0x18003c889  cmp     qword ptr cs:xmmword_180071090, rdx
0x18003c890  jz      short loc_18003C8D1
0x18003c892  mov     word ptr [rbp+7C0h+var_840], dx
0x18003c896  lea     r8, aRrasroutingdom_14; "RRasRoutingDomainConfig::GetConfigParam"
0x18003c89d  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x18003c8a4  mov     r9d, 928h
0x18003c8aa  lea     rcx, [rbp+7C0h+var_840]
0x18003c8ae  call    FormatRRASErrorString
0x18003c8b3  mov     rdx, qword ptr cs:xmmword_180071090
0x18003c8ba  lea     r8, [rbp+7C0h+var_840]
0x18003c8be  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003c8c5  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003c8cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c8d1  mov     ebx, 57h ; 'W'
0x18003c8d6  jmp     loc_18003D13D
0x18003c8db  mov     r13d, r15d
0x18003c8de  mov     r9d, 200h
0x18003c8e4  and     r13d, 80000000h
0x18003c8eb  mov     ebx, edx
0x18003c8ed  cmp     r15d, r9d
0x18003c8f0  jg      loc_18003CD7F
0x18003c8f6  jz      loc_18003CD5D
0x18003c8fc  mov     ecx, r15d
0x18003c8ff  sub     ecx, 1
0x18003c902  jz      loc_18003CC06
0x18003c908  sub     ecx, 1
0x18003c90b  jz      loc_18003CAF3
0x18003c911  sub     ecx, 2
0x18003c914  jz      loc_18003D13D
0x18003c91a  sub     ecx, 4
0x18003c91d  jz      loc_18003CA50
0x18003c923  sub     ecx, 18h
0x18003c926  jz      loc_18003CA1A
0x18003c92c  sub     ecx, 60h ; '`'
0x18003c92f  jz      loc_18003C9F8
0x18003c935  cmp     ecx, 80h
0x18003c93b  jnz     loc_18003CDD1
0x18003c941  cmp     dword ptr [rsi], 4
0x18003c944  jnb     loc_18003C9D4
0x18003c94a  cmp     qword ptr cs:xmmword_1800710A0, rdx
0x18003c951  jz      short loc_18003C9C9
0x18003c953  mov     r9d, 100h
0x18003c959  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003c960  mov     word ptr [rbp+7C0h+var_840], dx
0x18003c964  lea     r8, aRrasroutingdom_34; "RRasRoutingDomainConfig::GetConfigParam"
0x18003c96b  mov     word ptr [rsp+8C0h+var_870], dx
0x18003c970  lea     rcx, [rbp+7C0h+var_840]
0x18003c974  lea     rdx, aSInsufficientB; "%s: Insufficient buffer for config type"...
0x18003c97b  movdqu  [rsp+8C0h+var_880], xmm0
0x18003c981  call    FormatRRASErrorString
0x18003c986  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18003c98d  lea     rcx, [rdi+204h]
0x18003c994  xor     r13d, r13d
0x18003c997  lea     rax, [rsp+8C0h+var_870]
0x18003c99c  test    rcx, rcx
0x18003c99f  mov     [rsp+8C0h+var_898], rax
0x18003c9a4  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003c9ab  lea     r9, [rsp+8C0h+var_880]
0x18003c9b0  cmovnz  r9, rcx
0x18003c9b4  mov     [rsp+8C0h+var_8A0], r13
0x18003c9b9  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003c9c0  lea     r8, [rbp+7C0h+var_840]
0x18003c9c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c9c9  mov     dword ptr [rsi], 4
0x18003c9cf  jmp     loc_18003CC94
0x18003c9d4  test    byte ptr [rdi+214h], 1
0x18003c9db  jnz     short loc_18003C9EA
0x18003c9dd  mov     [r14], edx
0x18003c9e0  mov     ebx, 490h
0x18003c9e5  jmp     loc_18003D13D
0x18003c9ea  mov     eax, [rdi+21Ch]
0x18003c9f0  mov     [r14], eax
0x18003c9f3  jmp     loc_18003D13D
0x18003c9f8  cmp     dword ptr [rsi], 10h
0x18003c9fb  jnb     short loc_18003CA15
0x18003c9fd  cmp     qword ptr cs:xmmword_1800710A0, rdx
0x18003ca04  jz      loc_18003CC8E
0x18003ca0a  mov     r9d, 80h
0x18003ca10  jmp     loc_18003CC1E
0x18003ca15  xor     r8d, r8d
0x18003ca18  jmp     short loc_18003CA3D
0x18003ca1a  cmp     dword ptr [rsi], 10h
0x18003ca1d  jnb     short loc_18003CA37
0x18003ca1f  cmp     qword ptr cs:xmmword_1800710A0, rdx
0x18003ca26  jz      loc_18003CC8E
0x18003ca2c  mov     r9d, 20h ; ' '
0x18003ca32  jmp     loc_18003CC1E
0x18003ca37  mov     r8d, 1; int
0x18003ca3d  mov     r9, r14; struct _MPRI_TRANSPORT_INFO_1 *
0x18003ca40  mov     edx, r13d; int
0x18003ca43  mov     rcx, rdi; this
0x18003ca46  call    ?CopyTransportInfo@RRasRoutingDomainConfig@@AEAAKHHPEAU_MPRI_TRANSPORT_INFO_1@@@Z; RRasRoutingDomainConfig::CopyTransportInfo(int,int,_MPRI_TRANSPORT_INFO_1 *)
0x18003ca4b  jmp     loc_18003CD56
0x18003ca50  cmp     dword ptr [rsi], 68h ; 'h'
0x18003ca53  jnb     loc_18003CAE3
0x18003ca59  cmp     qword ptr cs:xmmword_1800710A0, rdx
0x18003ca60  jz      short loc_18003CAD8
0x18003ca62  mov     r9d, 8
0x18003ca68  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003ca6f  mov     word ptr [rsp+8C0h+var_870], dx
0x18003ca74  lea     r8, aRrasroutingdom_34; "RRasRoutingDomainConfig::GetConfigParam"
0x18003ca7b  mov     word ptr [rbp+7C0h+var_840], dx
0x18003ca7f  lea     rcx, [rbp+7C0h+var_840]
0x18003ca83  lea     rdx, aSInsufficientB; "%s: Insufficient buffer for config type"...
0x18003ca8a  movdqu  [rsp+8C0h+var_880], xmm0
0x18003ca90  call    FormatRRASErrorString
0x18003ca95  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18003ca9c  lea     rcx, [rdi+204h]
0x18003caa3  xor     r13d, r13d
0x18003caa6  lea     rax, [rsp+8C0h+var_870]
0x18003caab  test    rcx, rcx
0x18003caae  mov     [rsp+8C0h+var_898], rax
0x18003cab3  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003caba  lea     r9, [rsp+8C0h+var_880]
0x18003cabf  cmovnz  r9, rcx
0x18003cac3  mov     [rsp+8C0h+var_8A0], r13
0x18003cac8  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003cacf  lea     r8, [rbp+7C0h+var_840]
0x18003cad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cad8  mov     dword ptr [rsi], 68h ; 'h'
0x18003cade  jmp     loc_18003CC94
0x18003cae3  mov     rdx, r14; struct _IKEV2_TUNNEL_CONFIG_PARAMS_4 *
0x18003cae6  mov     rcx, rdi; this
0x18003cae9  call    ?CopyIkev2Config@RRasRoutingDomainConfig@@AEAAKPEAU_IKEV2_TUNNEL_CONFIG_PARAMS_4@@@Z; RRasRoutingDomainConfig::CopyIkev2Config(_IKEV2_TUNNEL_CONFIG_PARAMS_4 *)
0x18003caee  jmp     loc_18003CD56
0x18003caf3  cmp     dword ptr [rsi], 14h
0x18003caf6  jnb     loc_18003CB86
0x18003cafc  cmp     qword ptr cs:xmmword_1800710A0, rdx
0x18003cb03  jz      short loc_18003CB7B
0x18003cb05  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003cb0c  mov     word ptr [rbp+7C0h+var_840], dx
0x18003cb10  lea     r8, aRrasroutingdom_34; "RRasRoutingDomainConfig::GetConfigParam"
0x18003cb17  mov     word ptr [rsp+8C0h+var_870], dx
0x18003cb1c  lea     rcx, [rbp+7C0h+var_840]
0x18003cb20  mov     r9d, 2
0x18003cb26  lea     rdx, aSInsufficientB; "%s: Insufficient buffer for config type"...
0x18003cb2d  movdqu  [rsp+8C0h+var_880], xmm0
0x18003cb33  call    FormatRRASErrorString
0x18003cb38  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18003cb3f  lea     rcx, [rdi+204h]
0x18003cb46  xor     r13d, r13d
0x18003cb49  lea     rax, [rsp+8C0h+var_870]
0x18003cb4e  test    rcx, rcx
0x18003cb51  mov     [rsp+8C0h+var_898], rax
0x18003cb56  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003cb5d  lea     r9, [rsp+8C0h+var_880]
0x18003cb62  cmovnz  r9, rcx
0x18003cb66  mov     [rsp+8C0h+var_8A0], r13
0x18003cb6b  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003cb72  lea     r8, [rbp+7C0h+var_840]
0x18003cb76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb7b  mov     dword ptr [rsi], 14h
0x18003cb81  jmp     loc_18003CC94
0x18003cb86  test    r12d, r12d
0x18003cb89  jz      short loc_18003CBF6
0x18003cb8b  mov     rcx, rdi; this
0x18003cb8e  call    ?PopulateIpv6AddrPool@RRasRoutingDomainConfig@@AEAAKXZ; RRasRoutingDomainConfig::PopulateIpv6AddrPool(void)
0x18003cb93  xor     r13d, r13d
0x18003cb96  mov     ebx, eax
0x18003cb98  test    eax, eax
0x18003cb9a  jz      short loc_18003CBF6
0x18003cb9c  cmp     eax, 490h
0x18003cba1  jz      short loc_18003CBF6
0x18003cba3  cmp     qword ptr cs:xmmword_1800710A0, r13
0x18003cbaa  jz      loc_18003D13D
0x18003cbb0  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003cbb7  mov     r9d, eax
0x18003cbba  mov     word ptr [rbp+7C0h+var_840], r13w
0x18003cbbf  lea     r8, aRrasroutingdom_34; "RRasRoutingDomainConfig::GetConfigParam"
0x18003cbc6  mov     word ptr [rsp+8C0h+var_870], r13w
0x18003cbcc  lea     rdx, aSRefreshFailed_0; "%s: Refresh failed for IPv6 address poo"...
0x18003cbd3  lea     rcx, [rbp+7C0h+var_840]
0x18003cbd7  movdqu  [rsp+8C0h+var_880], xmm0
0x18003cbdd  call    FormatRRASErrorString
0x18003cbe2  lea     rax, [rsp+8C0h+var_870]
0x18003cbe7  mov     [rsp+8C0h+var_898], rax
0x18003cbec  mov     [rsp+8C0h+var_8A0], r13
0x18003cbf1  jmp     loc_18003CD12
0x18003cbf6  mov     rdx, r14; struct _MPRI_IPV6_CONFIG_1 *
0x18003cbf9  mov     rcx, rdi; this
0x18003cbfc  call    ?CopyIpv6AddrPool@RRasRoutingDomainConfig@@AEAAKPEAU_MPRI_IPV6_CONFIG_1@@@Z; RRasRoutingDomainConfig::CopyIpv6AddrPool(_MPRI_IPV6_CONFIG_1 *)
0x18003cc01  jmp     loc_18003CD56
0x18003cc06  cmp     dword ptr [rsi], 10h
0x18003cc09  jnb     loc_18003CC9E
0x18003cc0f  cmp     qword ptr cs:xmmword_1800710A0, rdx
0x18003cc16  jz      short loc_18003CC8E
0x18003cc18  mov     r9d, 1
0x18003cc1e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003cc25  mov     word ptr [rsp+8C0h+var_870], dx
0x18003cc2a  lea     r8, aRrasroutingdom_34; "RRasRoutingDomainConfig::GetConfigParam"
0x18003cc31  mov     word ptr [rbp+7C0h+var_840], dx
0x18003cc35  lea     rcx, [rbp+7C0h+var_840]
0x18003cc39  lea     rdx, aSInsufficientB; "%s: Insufficient buffer for config type"...
0x18003cc40  movdqu  [rsp+8C0h+var_880], xmm0
0x18003cc46  call    FormatRRASErrorString
0x18003cc4b  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18003cc52  lea     rcx, [rdi+204h]
0x18003cc59  xor     r13d, r13d
0x18003cc5c  lea     rax, [rsp+8C0h+var_870]
0x18003cc61  test    rcx, rcx
0x18003cc64  mov     [rsp+8C0h+var_898], rax
0x18003cc69  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003cc70  lea     r9, [rsp+8C0h+var_880]
0x18003cc75  cmovnz  r9, rcx
0x18003cc79  mov     [rsp+8C0h+var_8A0], r13
0x18003cc7e  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003cc85  lea     r8, [rbp+7C0h+var_840]
0x18003cc89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc8e  mov     dword ptr [rsi], 10h
0x18003cc94  mov     ebx, 7Ah ; 'z'
0x18003cc99  jmp     loc_18003D13D
0x18003cc9e  test    r12d, r12d
0x18003cca1  jz      loc_18003CD48
0x18003cca7  mov     rcx, rdi; this
0x18003ccaa  call    ?PopulateIpv4AddrPool@RRasRoutingDomainConfig@@AEAAKXZ; RRasRoutingDomainConfig::PopulateIpv4AddrPool(void)
0x18003ccaf  xor     esi, esi
0x18003ccb1  mov     ebx, eax
0x18003ccb3  test    eax, eax
0x18003ccb5  jz      loc_18003CD48
0x18003ccbb  cmp     eax, 490h
0x18003ccc0  jz      loc_18003CD48
0x18003ccc6  cmp     qword ptr cs:xmmword_1800710A0, rsi
0x18003cccd  jz      loc_18003D13D
0x18003ccd3  lea     rdx, aSRefreshFailed_2; "%s: Refresh failed for IPv4 address poo"...
0x18003ccda  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003cce1  lea     r8, aRrasroutingdom_34; "RRasRoutingDomainConfig::GetConfigParam"
0x18003cce8  mov     word ptr [rsp+8C0h+var_870], si
0x18003cced  mov     r9d, eax
0x18003ccf0  mov     word ptr [rbp+7C0h+var_840], si
0x18003ccf4  lea     rcx, [rbp+7C0h+var_840]
0x18003ccf8  movdqu  [rsp+8C0h+var_880], xmm0
0x18003ccfe  call    FormatRRASErrorString
0x18003cd03  lea     rax, [rsp+8C0h+var_870]
0x18003cd08  mov     [rsp+8C0h+var_898], rax
0x18003cd0d  mov     [rsp+8C0h+var_8A0], rsi
0x18003cd12  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18003cd19  lea     rcx, [rdi+204h]
0x18003cd20  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003cd27  lea     r9, [rsp+8C0h+var_880]
0x18003cd2c  test    rcx, rcx
0x18003cd2f  lea     r8, [rbp+7C0h+var_840]
0x18003cd33  cmovnz  r9, rcx
0x18003cd37  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003cd3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd43  jmp     loc_18003D13D
0x18003cd48  mov     r8, r14; struct _MPRI_IPV4_CONFIG_1 *
0x18003cd4b  mov     edx, r13d; int
0x18003cd4e  mov     rcx, rdi; this
0x18003cd51  call    ?CopyIpv4AddrPool@RRasRoutingDomainConfig@@AEAAKHPEAU_MPRI_IPV4_CONFIG_1@@@Z; RRasRoutingDomainConfig::CopyIpv4AddrPool(int,_MPRI_IPV4_CONFIG_1 *)
0x18003cd56  mov     ebx, eax
0x18003cd58  jmp     loc_18003D13D
0x18003cd5d  cmp     dword ptr [rsi], 4
0x18003cd60  jnb     short loc_18003CD74
0x18003cd62  cmp     qword ptr cs:xmmword_1800710A0, rdx
0x18003cd69  jz      loc_18003C9C9
0x18003cd6f  jmp     loc_18003C959
0x18003cd74  mov     eax, [rdi+214h]
0x18003cd7a  jmp     loc_18003C9F0
0x18003cd7f  mov     r8d, 400h
0x18003cd85  cmp     r15d, r8d
0x18003cd88  jz      loc_18003D09B
0x18003cd8e  mov     r9d, 800h
0x18003cd94  cmp     r15d, r9d
0x18003cd97  jz      loc_18003CFD0
0x18003cd9d  mov     r9d, 2000h
0x18003cda3  cmp     r15d, r9d
0x18003cda6  jz      loc_18003CEEE
  ... truncated ...
```
