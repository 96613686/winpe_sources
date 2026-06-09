# RRasRoutingDomainConfig::SetConfigParam(_RRAS_RD_CONFIG_TYPE,int,ulong,void *)

- ea: `0x18004c944`
- end: `0x18004cee4`
- name: `?SetConfigParam@RRasRoutingDomainConfig@@QEAAKW4_RRAS_RD_CONFIG_TYPE@@HKPEAX@Z`
- size: `1440`
- prototype: `__int64 __fastcall(__int64, int, int, __int64, struct _MPRI_IPV4_CONFIG_1 *Source)`
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, installer_update`

## callers

- `0x180047508`
- `0x18004d150`

## callees

- `0x180040d48`
- `0x180043390`
- `0x180043aa0`
- `0x18004a4b8`
- `0x18004a9dc`
- `0x18004ade0`
- `0x18004b204`
- `0x18004c944`
- `0x18004d304`
- `0x18004da50`
- `0x18004dd80`
- `0x18004dfe0`
- `0x18004e2fc`
- `0x18004e468`
- `0x18004e6f0`
- `0x180050b2c`
- `0x180050be8`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18004cc66`
- `msvcrt!memcpy_s` at `0x18004cc66`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004ccdd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004ccdd`

## string_xrefs

- `0x18004cc48`: `%s: set config not supported for cfg type: %d`
- `0x18004c9dc`: `RRasRoutingDomainConfig::SetConfigParam`
- `0x18004ca2f`: `RRasRoutingDomainConfig::SetConfigParam`
- `0x18004cbb7`: `%s: UpdateIpv4AddrPool failed: %d`
- `0x18004cb4f`: `%s: UpdateIpv6AddrPool failed: %d`
- `0x18004cb20`: `%s: UpdatePreSharedKey failed: %d`
- `0x18004caf9`: `%s: UpdateIkev2Config failed: %d`
- `0x18004cac6`: `%s: UpdateTransportInfo: UpdateIkev2Config failed: %d`
- `0x18004ce14`: `%s: UpdateAccoountingConfig failed: %d`
- `0x18004ce42`: `%s: PersistAccountingConfig failed: %d`
- `0x18004cd65`: `%s: UpdateDialInConfig failed: %d`
- `0x18004cd36`: `%s: PersistDialInConfig failed: %d`
- `0x18004cc9d`: `%s: UpdateRouterType failed: %d`
- `0x18004ccfb`: `%s: RegSetValueEx(RouterType) failed: %d`

## pseudocode

```c
__int64 __fastcall RRasRoutingDomainConfig::SetConfigParam(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        struct _MPRI_IPV4_CONFIG_1 *Source)
{
  void (*v8)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  unsigned int v9; // eax
  __int64 v10; // r9
  const wchar_t *v11; // rdx
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int updated; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  bool v19; // zf
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  __int64 v23; // r8
  unsigned int v24; // eax
  unsigned int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // r8
  unsigned int v28; // eax
  GUID *v29; // r9
  unsigned int v30; // ebx
  unsigned int v32; // [rsp+40h] [rbp-C0h] BYREF
  bool v33; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v34; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v35; // [rsp+50h] [rbp-B0h]
  __int128 v36; // [rsp+60h] [rbp-A0h]
  __int64 v37; // [rsp+70h] [rbp-90h]
  int v38; // [rsp+78h] [rbp-88h]
  int v39; // [rsp+7Ch] [rbp-84h]
  GUID v40; // [rsp+80h] [rbp-80h] BYREF
  int v41; // [rsp+90h] [rbp-70h] BYREF
  __int128 v42; // [rsp+94h] [rbp-6Ch]
  __int128 v43; // [rsp+A4h] [rbp-5Ch]
  int v44; // [rsp+B4h] [rbp-4Ch]
  int v45; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v46[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v32 = 0;
  v45 = 0;
  memset_0(v46, 0, sizeof(v46));
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v35 = 0;
  v34 = 0;
  v36 = 0;
  v37 = 0;
  v38 = -1;
  v39 = 0;
  if ( *((_QWORD *)&xmmword_180078C60 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v34,
      L"RRasRoutingDomainConfig::SetConfigParam",
      &v32,
      v8,
      (struct _GUID *)(a1 + 516));
  if ( !Source )
  {
    v32 = 87;
    if ( (_QWORD)xmmword_180078C50 )
    {
      LOWORD(v45) = 0;
      FormatRRASErrorString(&v45, L"%hs(Line#%d): Invalid parameter.", "RRasRoutingDomainConfig::SetConfigParam", 2607);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180078C50,
        &v45);
    }
    goto LABEL_77;
  }
  if ( a2 <= 128 )
  {
    switch ( a2 )
    {
      case 128:
        goto LABEL_13;
      case 1:
        updated = RRasRoutingDomainConfig::UpdateIpv4AddrPool((RRasRoutingDomainConfig *)a1, Source);
        v10 = updated;
        v32 = updated;
        if ( updated )
        {
          if ( !(_QWORD)xmmword_180078C60 )
            goto LABEL_77;
          v11 = L"%s: UpdateIpv4AddrPool failed: %d";
        }
        else
        {
          if ( !a3 )
            goto LABEL_77;
          v16 = RRasRoutingDomainConfig::PersistIpv4AddrPool((RRasRoutingDomainConfig *)a1);
          v10 = v16;
          v32 = v16;
          if ( !v16 || !(_QWORD)xmmword_180078C60 )
            goto LABEL_77;
          v11 = L"%s: Persist failed for IPv4 address pool: %d";
        }
        goto LABEL_74;
      case 2:
        v13 = RRasRoutingDomainConfig::UpdateIpv6AddrPool((RRasRoutingDomainConfig *)a1, Source);
        v10 = v13;
        v32 = v13;
        if ( v13 )
        {
          if ( !(_QWORD)xmmword_180078C60 )
            goto LABEL_77;
          v11 = L"%s: UpdateIpv6AddrPool failed: %d";
        }
        else
        {
          if ( !a3 )
            goto LABEL_77;
          v14 = RRasRoutingDomainConfig::PersistIpv6AddrPool((RRasRoutingDomainConfig *)a1);
          v10 = v14;
          v32 = v14;
          if ( !v14 || !(_QWORD)xmmword_180078C60 )
            goto LABEL_77;
          v11 = L"%s: Refresh failed for IPv6 address pool: %d";
        }
        goto LABEL_74;
      case 4:
        v10 = v32;
        if ( !v32 || !(_QWORD)xmmword_180078C60 )
          goto LABEL_77;
        v11 = L"%s: UpdatePreSharedKey failed: %d";
        goto LABEL_74;
      case 8:
        v12 = RRasRoutingDomainConfig::UpdateIkev2Config((RRasRoutingDomainConfig *)a1, Source);
        v10 = v12;
        v32 = v12;
        if ( !v12 || !(_QWORD)xmmword_180078C60 )
          goto LABEL_77;
        v11 = L"%s: UpdateIkev2Config failed: %d";
        goto LABEL_74;
      case 32:
LABEL_13:
        v9 = RRasRoutingDomainConfig::UpdateTransportInfo((RRasRoutingDomainConfig *)a1, Source);
        v10 = v9;
        v32 = v9;
        if ( !v9 || !(_QWORD)xmmword_180078C60 )
          goto LABEL_77;
        v11 = L"%s: UpdateTransportInfo: UpdateIkev2Config failed: %d";
        goto LABEL_74;
    }
    goto LABEL_41;
  }
  if ( a2 == 2048 )
  {
    v25 = RRasRoutingDomainConfig::UpdateAccountingConfig((RRasRoutingDomainConfig *)a1, Source);
    v10 = v25;
    v32 = v25;
    if ( v25 )
    {
      if ( !(_QWORD)xmmword_180078C60 )
        goto LABEL_77;
      v11 = L"%s: UpdateAccoountingConfig failed: %d";
    }
    else
    {
      if ( !a3 )
        goto LABEL_77;
      v28 = RRasRoutingDomainConfig::PersistAccountingConfig(
              (RRasRoutingDomainConfig *)a1,
              v26,
              v27,
              (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))v25);
      v10 = v28;
      v32 = v28;
      if ( !v28 || !(_QWORD)xmmword_180078C60 )
        goto LABEL_77;
      v11 = L"%s: PersistAccountingConfig failed: %d";
    }
    goto LABEL_74;
  }
  if ( a2 == 0x2000 )
  {
    v22 = ValidateQoSPolicies(Source);
    v10 = v22;
    v32 = v22;
    if ( v22 )
    {
      if ( !(_QWORD)xmmword_180078C60 )
        goto LABEL_77;
      v11 = L"%s: ValidateQoSPolicies failed: %d";
    }
    else
    {
      CopyValidQoSPoliciesFromUserBuffer(a1 + 544, Source, v23, 0);
      if ( !a3 )
        goto LABEL_77;
      v24 = WriteQoSPoliciesToRegsitry(*(HKEY *)(a1 + 824));
      v10 = v24;
      v32 = v24;
      if ( !v24 || !(_QWORD)xmmword_180078C60 )
        goto LABEL_77;
      v11 = L"%s: Persist failed for QoS policies: %d";
    }
    goto LABEL_74;
  }
  if ( a2 != 0x4000 )
  {
    if ( a2 != 0x8000 )
    {
      if ( a2 == 0x10000 )
      {
        memcpy_s((void *const)(a1 + 840), 0x10u, Source, 0x10u);
        goto LABEL_77;
      }
LABEL_41:
      v32 = 50;
      if ( !(_QWORD)xmmword_180078C60 )
        goto LABEL_77;
      v10 = (unsigned int)a2;
      v11 = L"%s: set config not supported for cfg type: %d";
      goto LABEL_74;
    }
    v33 = 0;
    v17 = RRasRoutingDomainConfig::UpdateRouterType((RRasRoutingDomainConfig *)a1, *(_DWORD *)Source, &v33);
    v10 = v17;
    v32 = v17;
    if ( v17 )
    {
      if ( !(_QWORD)xmmword_180078C60 )
        goto LABEL_77;
      v11 = L"%s: UpdateRouterType failed: %d";
      goto LABEL_74;
    }
    if ( !a3 )
      goto LABEL_77;
    v18 = RegSetValueExW(*(HKEY *)(a1 + 824), L"RouterType", 0, 4u, (const BYTE *)(a1 + 536), 4u);
    v10 = v18;
    v32 = v18;
    if ( v18 )
    {
      if ( !(_QWORD)xmmword_180078C60 )
        goto LABEL_77;
      v11 = L"%s: RegSetValueEx(RouterType) failed: %d";
      goto LABEL_74;
    }
    v19 = !v33;
LABEL_52:
    if ( v19 )
      goto LABEL_77;
    v20 = RRasRoutingDomainConfig::PersistDialInConfig((RRasRoutingDomainConfig *)a1);
    v10 = v20;
    v32 = v20;
    if ( !v20 || !(_QWORD)xmmword_180078C60 )
      goto LABEL_77;
    v11 = L"%s: PersistDialInConfig failed: %d";
    goto LABEL_74;
  }
  v21 = RRasRoutingDomainConfig::UpdateDialInConfig((RRasRoutingDomainConfig *)a1, Source);
  v10 = v21;
  v32 = v21;
  if ( !v21 )
  {
    v19 = a3 == 0;
    goto LABEL_52;
  }
  if ( !(_QWORD)xmmword_180078C60 )
    goto LABEL_77;
  v11 = L"%s: UpdateDialInConfig failed: %d";
LABEL_74:
  LOWORD(v45) = 0;
  v40 = GUID_NULL;
  LOWORD(v41) = 0;
  FormatRRASErrorString(&v45, v11, L"RRasRoutingDomainConfig::SetConfigParam", v10);
  v29 = &v40;
  if ( a1 != -516 )
    v29 = (GUID *)(a1 + 516);
  ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
    gCfgStoreEtwContext,
    xmmword_180078C60,
    &v45,
    v29,
    0,
    &v41);
LABEL_77:
  v30 = v32;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v34);
  return v30;
}

```

## disassembly

```asm
0x18004c944  mov     [rsp-8+arg_10], rbx
0x18004c949  mov     [rsp-8+arg_18], rsi
0x18004c94e  push    rbp
0x18004c94f  push    rdi
0x18004c950  push    r12
0x18004c952  push    r14
0x18004c954  push    r15
0x18004c956  lea     rbp, [rsp-7D0h]
0x18004c95e  sub     rsp, 8D0h
0x18004c965  mov     rax, cs:__security_cookie
0x18004c96c  xor     rax, rsp
0x18004c96f  mov     [rbp+7F0h+var_30], rax
0x18004c976  mov     r14d, r8d
0x18004c979  mov     esi, edx
0x18004c97b  mov     rbx, rcx
0x18004c97e  mov     rdi, [rbp+7F0h+Source]
0x18004c985  xor     r15d, r15d
0x18004c988  mov     [rsp+8F0h+var_8B0], r15d
0x18004c98d  mov     [rbp+7F0h+var_830], r15d
0x18004c991  xor     edx, edx; Val
0x18004c993  mov     r8d, 7FCh; Size
0x18004c999  lea     rcx, [rbp+7F0h+var_82C]; void *
0x18004c99d  call    memset_0
0x18004c9a2  mov     [rbp+7F0h+var_860], r15d
0x18004c9a6  xorps   xmm0, xmm0
0x18004c9a9  xor     eax, eax
0x18004c9ab  movups  [rbp+7F0h+var_85C], xmm0
0x18004c9af  movups  [rbp+7F0h+var_84C], xmm0
0x18004c9b3  mov     [rbp+7F0h+var_83C], eax
0x18004c9b6  movdqu  [rsp+8F0h+var_8A0], xmm0
0x18004c9bc  mov     [rsp+8F0h+var_8A8], r15
0x18004c9c1  xorps   xmm1, xmm1
0x18004c9c4  movdqu  [rsp+8F0h+var_890], xmm1
0x18004c9ca  mov     [rsp+8F0h+var_880], r15
0x18004c9cf  mov     [rsp+8F0h+var_878], 0FFFFFFFFh
0x18004c9d7  mov     [rsp+8F0h+var_874], r15d
0x18004c9dc  lea     r12, aRrasroutingdom_36; "RRasRoutingDomainConfig::SetConfigParam"
0x18004c9e3  cmp     qword ptr cs:xmmword_180078C60+8, r15
0x18004c9ea  jz      short loc_18004CA0A
0x18004c9ec  lea     rax, [rbx+204h]
0x18004c9f3  mov     [rsp+8F0h+lpData], rax; struct _GUID *
0x18004c9f8  lea     r8, [rsp+8F0h+var_8B0]; unsigned int *
0x18004c9fd  mov     rdx, r12; unsigned __int16 *
0x18004ca00  lea     rcx, [rsp+8F0h+var_8A8]; this
0x18004ca05  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18004ca0a  test    rdi, rdi
0x18004ca0d  jnz     short loc_18004CA69
0x18004ca0f  mov     [rsp+8F0h+var_8B0], 57h ; 'W'
0x18004ca17  cmp     qword ptr cs:xmmword_180078C50, r15
0x18004ca1e  jz      loc_18004CEA9
0x18004ca24  mov     word ptr [rbp+7F0h+var_830], r15w
0x18004ca29  mov     r9d, 0A2Fh
0x18004ca2f  lea     r8, aRrasroutingdom_26; "RRasRoutingDomainConfig::SetConfigParam"
0x18004ca36  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x18004ca3d  lea     rcx, [rbp+7F0h+var_830]
0x18004ca41  call    FormatRRASErrorString
0x18004ca46  lea     r8, [rbp+7F0h+var_830]
0x18004ca4a  mov     rdx, qword ptr cs:xmmword_180078C50
0x18004ca51  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004ca58  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004ca5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca64  jmp     loc_18004CEA9
0x18004ca69  mov     eax, 80h
0x18004ca6e  cmp     esi, eax
0x18004ca70  jg      loc_18004CBFC
0x18004ca76  jz      short loc_18004CA9F
0x18004ca78  mov     ecx, esi
0x18004ca7a  sub     ecx, 1
0x18004ca7d  jz      loc_18004CB94
0x18004ca83  sub     ecx, 1
0x18004ca86  jz      loc_18004CB2C
0x18004ca8c  sub     ecx, 2
0x18004ca8f  jz      short loc_18004CB05
0x18004ca91  sub     ecx, 4
0x18004ca94  jz      short loc_18004CAD2
0x18004ca96  cmp     ecx, 18h
0x18004ca99  jnz     loc_18004CC30
0x18004ca9f  mov     rdx, rdi; struct _MPRI_TRANSPORT_INFO_1 *
0x18004caa2  mov     rcx, rbx; this
0x18004caa5  call    ?UpdateTransportInfo@RRasRoutingDomainConfig@@AEAAKPEAU_MPRI_TRANSPORT_INFO_1@@@Z; RRasRoutingDomainConfig::UpdateTransportInfo(_MPRI_TRANSPORT_INFO_1 *)
0x18004caaa  mov     r9d, eax
0x18004caad  mov     [rsp+8F0h+var_8B0], eax
0x18004cab1  test    eax, eax
0x18004cab3  jz      loc_18004CEA9
0x18004cab9  cmp     qword ptr cs:xmmword_180078C60, r15
0x18004cac0  jz      loc_18004CEA9
0x18004cac6  lea     rdx, aSUpdatetranspo; "%s: UpdateTransportInfo: UpdateIkev2Con"...
0x18004cacd  jmp     loc_18004CE49
0x18004cad2  mov     rdx, rdi; struct _IKEV2_TUNNEL_CONFIG_PARAMS_4 *
0x18004cad5  mov     rcx, rbx; this
0x18004cad8  call    ?UpdateIkev2Config@RRasRoutingDomainConfig@@AEAAKPEAU_IKEV2_TUNNEL_CONFIG_PARAMS_4@@@Z; RRasRoutingDomainConfig::UpdateIkev2Config(_IKEV2_TUNNEL_CONFIG_PARAMS_4 *)
0x18004cadd  mov     r9d, eax
0x18004cae0  mov     [rsp+8F0h+var_8B0], eax
0x18004cae4  test    eax, eax
0x18004cae6  jz      loc_18004CEA9
0x18004caec  cmp     qword ptr cs:xmmword_180078C60, r15
0x18004caf3  jz      loc_18004CEA9
0x18004caf9  lea     rdx, aSUpdateikev2co; "%s: UpdateIkev2Config failed: %d"
0x18004cb00  jmp     loc_18004CE49
0x18004cb05  mov     r9d, [rsp+8F0h+var_8B0]
0x18004cb0a  test    r9d, r9d
0x18004cb0d  jz      loc_18004CEA9
0x18004cb13  cmp     qword ptr cs:xmmword_180078C60, r15
0x18004cb1a  jz      loc_18004CEA9
0x18004cb20  lea     rdx, aSUpdatepreshar; "%s: UpdatePreSharedKey failed: %d"
0x18004cb27  jmp     loc_18004CE49
0x18004cb2c  mov     rdx, rdi; struct _MPRI_IPV6_CONFIG_1 *
0x18004cb2f  mov     rcx, rbx; this
0x18004cb32  call    ?UpdateIpv6AddrPool@RRasRoutingDomainConfig@@AEAAKPEAU_MPRI_IPV6_CONFIG_1@@@Z; RRasRoutingDomainConfig::UpdateIpv6AddrPool(_MPRI_IPV6_CONFIG_1 *)
0x18004cb37  mov     r9d, eax
0x18004cb3a  mov     [rsp+8F0h+var_8B0], eax
0x18004cb3e  test    eax, eax
0x18004cb40  jz      short loc_18004CB5B
0x18004cb42  cmp     qword ptr cs:xmmword_180078C60, r15
0x18004cb49  jz      loc_18004CEA9
0x18004cb4f  lea     rdx, aSUpdateipv6add; "%s: UpdateIpv6AddrPool failed: %d"
0x18004cb56  jmp     loc_18004CE49
0x18004cb5b  test    r14d, r14d
0x18004cb5e  jz      loc_18004CEA9
0x18004cb64  mov     rcx, rbx; this
0x18004cb67  call    ?PersistIpv6AddrPool@RRasRoutingDomainConfig@@AEAAKXZ; RRasRoutingDomainConfig::PersistIpv6AddrPool(void)
0x18004cb6c  mov     r9d, eax
0x18004cb6f  mov     [rsp+8F0h+var_8B0], eax
0x18004cb73  test    eax, eax
0x18004cb75  jz      loc_18004CEA9
0x18004cb7b  cmp     qword ptr cs:xmmword_180078C60, r15
0x18004cb82  jz      loc_18004CEA9
0x18004cb88  lea     rdx, aSRefreshFailed_0; "%s: Refresh failed for IPv6 address poo"...
0x18004cb8f  jmp     loc_18004CE49
0x18004cb94  mov     rdx, rdi; struct _MPRI_IPV4_CONFIG_1 *
0x18004cb97  mov     rcx, rbx; this
0x18004cb9a  call    ?UpdateIpv4AddrPool@RRasRoutingDomainConfig@@AEAAKPEAU_MPRI_IPV4_CONFIG_1@@@Z; RRasRoutingDomainConfig::UpdateIpv4AddrPool(_MPRI_IPV4_CONFIG_1 *)
0x18004cb9f  mov     r9d, eax
0x18004cba2  mov     [rsp+8F0h+var_8B0], eax
0x18004cba6  test    eax, eax
0x18004cba8  jz      short loc_18004CBC3
0x18004cbaa  cmp     qword ptr cs:xmmword_180078C60, r15
0x18004cbb1  jz      loc_18004CEA9
0x18004cbb7  lea     rdx, aSUpdateipv4add; "%s: UpdateIpv4AddrPool failed: %d"
0x18004cbbe  jmp     loc_18004CE49
0x18004cbc3  test    r14d, r14d
0x18004cbc6  jz      loc_18004CEA9
0x18004cbcc  mov     rcx, rbx; this
0x18004cbcf  call    ?PersistIpv4AddrPool@RRasRoutingDomainConfig@@AEAAKXZ; RRasRoutingDomainConfig::PersistIpv4AddrPool(void)
0x18004cbd4  mov     r9d, eax
0x18004cbd7  mov     [rsp+8F0h+var_8B0], eax
0x18004cbdb  test    eax, eax
0x18004cbdd  jz      loc_18004CEA9
0x18004cbe3  cmp     qword ptr cs:xmmword_180078C60, r15
0x18004cbea  jz      loc_18004CEA9
0x18004cbf0  lea     rdx, aSPersistFailed; "%s: Persist failed for IPv4 address poo"...
0x18004cbf7  jmp     loc_18004CE49
0x18004cbfc  cmp     esi, 800h
0x18004cc02  jz      loc_18004CDF1
0x18004cc08  cmp     esi, 2000h
0x18004cc0e  jz      loc_18004CD76
0x18004cc14  cmp     esi, 4000h
0x18004cc1a  jz      loc_18004CD42
0x18004cc20  cmp     esi, 8000h
0x18004cc26  jz      short loc_18004CC71
0x18004cc28  cmp     esi, 10000h
0x18004cc2e  jz      short loc_18004CC54
0x18004cc30  mov     [rsp+8F0h+var_8B0], 32h ; '2'
0x18004cc38  cmp     qword ptr cs:xmmword_180078C60, r15
0x18004cc3f  jz      loc_18004CEA9
0x18004cc45  mov     r9d, esi
0x18004cc48  lea     rdx, aSSetConfigNotS; "%s: set config not supported for cfg ty"...
0x18004cc4f  jmp     loc_18004CE49
0x18004cc54  lea     rcx, [rbx+348h]; Destination
0x18004cc5b  mov     edx, 10h; DestinationSize
0x18004cc60  mov     r9d, edx; SourceSize
0x18004cc63  mov     r8, rdi; Source
0x18004cc66  call    cs:__imp_memcpy_s
0x18004cc6c  jmp     loc_18004CEA9
0x18004cc71  mov     [rsp+8F0h+var_8AC], r15b
0x18004cc76  lea     r8, [rsp+8F0h+var_8AC]; bool *
0x18004cc7b  mov     edx, [rdi]; unsigned int
0x18004cc7d  mov     rcx, rbx; this
0x18004cc80  call    ?UpdateRouterType@RRasRoutingDomainConfig@@AEAAKKPEA_N@Z; RRasRoutingDomainConfig::UpdateRouterType(ulong,bool *)
0x18004cc85  mov     r9d, eax
0x18004cc88  mov     [rsp+8F0h+var_8B0], eax
0x18004cc8c  test    eax, eax
0x18004cc8e  jz      short loc_18004CCA9
0x18004cc90  cmp     qword ptr cs:xmmword_180078C60, r15
0x18004cc97  jz      loc_18004CEA9
0x18004cc9d  lea     rdx, aSUpdateroutert; "%s: UpdateRouterType failed: %d"
0x18004cca4  jmp     loc_18004CE49
0x18004cca9  test    r14d, r14d
0x18004ccac  jz      loc_18004CEA9
0x18004ccb2  lea     rax, [rbx+218h]
0x18004ccb9  mov     [rsp+8F0h+cbData], 4; cbData
0x18004ccc1  mov     [rsp+8F0h+lpData], rax; lpData
0x18004ccc6  mov     r9d, 4; dwType
0x18004cccc  xor     r8d, r8d; Reserved
0x18004cccf  lea     rdx, aRoutertype; "RouterType"
0x18004ccd6  mov     rcx, [rbx+338h]; hKey
0x18004ccdd  call    cs:__imp_RegSetValueExW
0x18004cce3  mov     r9d, eax
0x18004cce6  mov     [rsp+8F0h+var_8B0], eax
0x18004ccea  test    eax, eax
0x18004ccec  jz      short loc_18004CD07
0x18004ccee  cmp     qword ptr cs:xmmword_180078C60, r15
0x18004ccf5  jz      loc_18004CEA9
0x18004ccfb  lea     rdx, aSRegsetvalueex_0; "%s: RegSetValueEx(RouterType) failed: %"...
0x18004cd02  jmp     loc_18004CE49
0x18004cd07  cmp     [rsp+8F0h+var_8AC], r15b
0x18004cd0c  jz      loc_18004CEA9
0x18004cd12  mov     rcx, rbx; this
0x18004cd15  call    ?PersistDialInConfig@RRasRoutingDomainConfig@@AEAAKXZ; RRasRoutingDomainConfig::PersistDialInConfig(void)
0x18004cd1a  mov     r9d, eax
0x18004cd1d  mov     [rsp+8F0h+var_8B0], eax
0x18004cd21  test    eax, eax
0x18004cd23  jz      loc_18004CEA9
0x18004cd29  cmp     qword ptr cs:xmmword_180078C60, r15
0x18004cd30  jz      loc_18004CEA9
0x18004cd36  lea     rdx, aSPersistdialin; "%s: PersistDialInConfig failed: %d"
0x18004cd3d  jmp     loc_18004CE49
0x18004cd42  mov     rdx, rdi; struct _MPRI_DIAL_IN_CONFIG_1 *
0x18004cd45  mov     rcx, rbx; this
0x18004cd48  call    ?UpdateDialInConfig@RRasRoutingDomainConfig@@AEAAKPEAU_MPRI_DIAL_IN_CONFIG_1@@@Z; RRasRoutingDomainConfig::UpdateDialInConfig(_MPRI_DIAL_IN_CONFIG_1 *)
0x18004cd4d  mov     r9d, eax
0x18004cd50  mov     [rsp+8F0h+var_8B0], eax
0x18004cd54  test    eax, eax
0x18004cd56  jz      short loc_18004CD71
0x18004cd58  cmp     qword ptr cs:xmmword_180078C60, r15
0x18004cd5f  jz      loc_18004CEA9
0x18004cd65  lea     rdx, aSUpdatedialinc_0; "%s: UpdateDialInConfig failed: %d"
0x18004cd6c  jmp     loc_18004CE49
0x18004cd71  test    r14d, r14d
0x18004cd74  jmp     short loc_18004CD0C
0x18004cd76  mov     rcx, rdi
0x18004cd79  call    ValidateQoSPolicies
0x18004cd7e  mov     r9d, eax
0x18004cd81  mov     [rsp+8F0h+var_8B0], eax
0x18004cd85  test    eax, eax
0x18004cd87  jz      short loc_18004CDA2
0x18004cd89  cmp     qword ptr cs:xmmword_180078C60, r15
0x18004cd90  jz      loc_18004CEA9
0x18004cd96  lea     rdx, aSValidateqospo; "%s: ValidateQoSPolicies failed: %d"
0x18004cd9d  jmp     loc_18004CE49
0x18004cda2  lea     rsi, [rbx+220h]
0x18004cda9  mov     rdx, rdi
0x18004cdac  mov     rcx, rsi
0x18004cdaf  call    CopyValidQoSPoliciesFromUserBuffer
0x18004cdb4  test    r14d, r14d
0x18004cdb7  jz      loc_18004CEA9
0x18004cdbd  mov     rdx, rsi
0x18004cdc0  mov     rcx, [rbx+338h]; hKey
0x18004cdc7  call    WriteQoSPoliciesToRegsitry
0x18004cdcc  mov     r9d, eax
0x18004cdcf  mov     [rsp+8F0h+var_8B0], eax
0x18004cdd3  test    eax, eax
0x18004cdd5  jz      loc_18004CEA9
0x18004cddb  cmp     qword ptr cs:xmmword_180078C60, r15
0x18004cde2  jz      loc_18004CEA9
0x18004cde8  lea     rdx, aSPersistFailed_0; "%s: Persist failed for QoS policies: %d"
0x18004cdef  jmp     short loc_18004CE49
0x18004cdf1  mov     rdx, rdi; struct _MPRI_ACCOUNTING_CONFIG_1 *
0x18004cdf4  mov     rcx, rbx; this
0x18004cdf7  call    ?UpdateAccountingConfig@RRasRoutingDomainConfig@@AEAAKPEAU_MPRI_ACCOUNTING_CONFIG_1@@@Z; RRasRoutingDomainConfig::UpdateAccountingConfig(_MPRI_ACCOUNTING_CONFIG_1 *)
0x18004cdfc  mov     r9d, eax
0x18004cdff  mov     [rsp+8F0h+var_8B0], eax
0x18004ce03  test    eax, eax
0x18004ce05  jz      short loc_18004CE1D
0x18004ce07  cmp     qword ptr cs:xmmword_180078C60, r15
0x18004ce0e  jz      loc_18004CEA9
0x18004ce14  lea     rdx, aSUpdateaccooun; "%s: UpdateAccoountingConfig failed: %d"
0x18004ce1b  jmp     short loc_18004CE49
0x18004ce1d  test    r14d, r14d
0x18004ce20  jz      loc_18004CEA9
0x18004ce26  mov     rcx, rbx; this
0x18004ce29  call    ?PersistAccountingConfig@RRasRoutingDomainConfig@@AEAAKXZ; RRasRoutingDomainConfig::PersistAccountingConfig(void)
0x18004ce2e  mov     r9d, eax
0x18004ce31  mov     [rsp+8F0h+var_8B0], eax
0x18004ce35  test    eax, eax
0x18004ce37  jz      short loc_18004CEA9
0x18004ce39  cmp     qword ptr cs:xmmword_180078C60, r15
0x18004ce40  jz      short loc_18004CEA9
0x18004ce42  lea     rdx, aSPersistaccoun; "%s: PersistAccountingConfig failed: %d"
0x18004ce49  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004ce50  mov     word ptr [rbp+7F0h+var_830], r15w
0x18004ce55  movdqu  [rbp+7F0h+var_870], xmm0
0x18004ce5a  mov     word ptr [rbp+7F0h+var_860], r15w
0x18004ce5f  mov     r8, r12
0x18004ce62  lea     rcx, [rbp+7F0h+var_830]
0x18004ce66  call    FormatRRASErrorString
0x18004ce6b  lea     rcx, [rbx+204h]
0x18004ce72  lea     rax, [rbp+7F0h+var_860]
0x18004ce76  lea     r9, [rbp+7F0h+var_870]
0x18004ce7a  test    rcx, rcx
0x18004ce7d  mov     qword ptr [rsp+8F0h+cbData], rax
0x18004ce82  cmovnz  r9, rcx
0x18004ce86  mov     [rsp+8F0h+lpData], r15
0x18004ce8b  lea     r8, [rbp+7F0h+var_830]
0x18004ce8f  mov     rdx, qword ptr cs:xmmword_180078C60
0x18004ce96  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004ce9d  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004cea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cea9  mov     ebx, [rsp+8F0h+var_8B0]
0x18004cead  lea     rcx, [rsp+8F0h+var_8A8]; this
  ... truncated ...
```
