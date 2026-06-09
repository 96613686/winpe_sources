# RRasRoutingDomainConfig::SetConfigParam(_RRAS_RD_CONFIG_TYPE,int,ulong,void *)

- ea: `0x1800416fc`
- end: `0x180041c9c`
- name: `?SetConfigParam@RRasRoutingDomainConfig@@QEAAKW4_RRAS_RD_CONFIG_TYPE@@HKPEAX@Z`
- size: `1440`
- prototype: `__int64 __fastcall(__int64, int, int, __int64, struct _MPRI_IPV4_CONFIG_1 *Source)`
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, installer_update`

## callers

- `0x18003bd5c`
- `0x180041edc`

## callees

- `0x180035118`
- `0x180037d0c`
- `0x1800383ac`
- `0x18003eefc`
- `0x18003f420`
- `0x18003f824`
- `0x18003fc38`
- `0x1800416fc`
- `0x180042090`
- `0x1800427d0`
- `0x180042b00`
- `0x180042d5c`
- `0x18004306c`
- `0x1800431d8`
- `0x180043460`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180041a1e`
- `msvcrt!memcpy_s` at `0x180041a1e`
- `ADVAPI32!RegSetValueExW` at `0x180041a95`
- `ADVAPI32!RegSetValueExW` at `0x180041a95`

## string_xrefs

- `0x180041a00`: `%s: set config not supported for cfg type: %d`
- `0x180041794`: `RRasRoutingDomainConfig::SetConfigParam`
- `0x1800417e7`: `RRasRoutingDomainConfig::SetConfigParam`
- `0x18004196f`: `%s: UpdateIpv4AddrPool failed: %d`
- `0x180041907`: `%s: UpdateIpv6AddrPool failed: %d`
- `0x1800418d8`: `%s: UpdatePreSharedKey failed: %d`
- `0x1800418b1`: `%s: UpdateIkev2Config failed: %d`
- `0x18004187e`: `%s: UpdateTransportInfo: UpdateIkev2Config failed: %d`
- `0x180041bcc`: `%s: UpdateAccoountingConfig failed: %d`
- `0x180041bfa`: `%s: PersistAccountingConfig failed: %d`
- `0x180041b1d`: `%s: UpdateDialInConfig failed: %d`
- `0x180041aee`: `%s: PersistDialInConfig failed: %d`
- `0x180041a55`: `%s: UpdateRouterType failed: %d`
- `0x180041ab3`: `%s: RegSetValueEx(RouterType) failed: %d`

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
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  GUID *v26; // r9
  unsigned int v27; // ebx
  unsigned __int16 *cbData; // [rsp+28h] [rbp-D8h]
  unsigned int v30; // [rsp+30h] [rbp-D0h]
  unsigned int v31; // [rsp+40h] [rbp-C0h] BYREF
  bool v32; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v33; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v34; // [rsp+50h] [rbp-B0h]
  __int128 v35; // [rsp+60h] [rbp-A0h]
  __int64 v36; // [rsp+70h] [rbp-90h]
  int v37; // [rsp+78h] [rbp-88h]
  int v38; // [rsp+7Ch] [rbp-84h]
  GUID v39; // [rsp+80h] [rbp-80h] BYREF
  int v40; // [rsp+90h] [rbp-70h] BYREF
  __int128 v41; // [rsp+94h] [rbp-6Ch]
  __int128 v42; // [rsp+A4h] [rbp-5Ch]
  int v43; // [rsp+B4h] [rbp-4Ch]
  int v44; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v45[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v31 = 0;
  v44 = 0;
  memset_0(v45, 0, sizeof(v45));
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v34 = 0;
  v33 = 0;
  v35 = 0;
  v36 = 0;
  v37 = -1;
  v38 = 0;
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v33,
      L"RRasRoutingDomainConfig::SetConfigParam",
      &v31,
      v8,
      (struct _GUID *)(a1 + 516),
      cbData,
      v30);
  if ( !Source )
  {
    v31 = 87;
    if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v44) = 0;
      FormatRRASErrorString(&v44, L"%hs(Line#%d): Invalid parameter.", "RRasRoutingDomainConfig::SetConfigParam", 2607);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
        &v44);
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
        v31 = updated;
        if ( updated )
        {
          if ( !(_QWORD)xmmword_1800710A0 )
            goto LABEL_77;
          v11 = L"%s: UpdateIpv4AddrPool failed: %d";
        }
        else
        {
          if ( !a3 )
            goto LABEL_77;
          v16 = RRasRoutingDomainConfig::PersistIpv4AddrPool((RRasRoutingDomainConfig *)a1);
          v10 = v16;
          v31 = v16;
          if ( !v16 || !(_QWORD)xmmword_1800710A0 )
            goto LABEL_77;
          v11 = L"%s: Persist failed for IPv4 address pool: %d";
        }
        goto LABEL_74;
      case 2:
        v13 = RRasRoutingDomainConfig::UpdateIpv6AddrPool((RRasRoutingDomainConfig *)a1, Source);
        v10 = v13;
        v31 = v13;
        if ( v13 )
        {
          if ( !(_QWORD)xmmword_1800710A0 )
            goto LABEL_77;
          v11 = L"%s: UpdateIpv6AddrPool failed: %d";
        }
        else
        {
          if ( !a3 )
            goto LABEL_77;
          v14 = RRasRoutingDomainConfig::PersistIpv6AddrPool((RRasRoutingDomainConfig *)a1);
          v10 = v14;
          v31 = v14;
          if ( !v14 || !(_QWORD)xmmword_1800710A0 )
            goto LABEL_77;
          v11 = L"%s: Refresh failed for IPv6 address pool: %d";
        }
        goto LABEL_74;
      case 4:
        v10 = v31;
        if ( !v31 || !(_QWORD)xmmword_1800710A0 )
          goto LABEL_77;
        v11 = L"%s: UpdatePreSharedKey failed: %d";
        goto LABEL_74;
      case 8:
        v12 = RRasRoutingDomainConfig::UpdateIkev2Config((RRasRoutingDomainConfig *)a1, Source);
        v10 = v12;
        v31 = v12;
        if ( !v12 || !(_QWORD)xmmword_1800710A0 )
          goto LABEL_77;
        v11 = L"%s: UpdateIkev2Config failed: %d";
        goto LABEL_74;
      case 32:
LABEL_13:
        v9 = RRasRoutingDomainConfig::UpdateTransportInfo((RRasRoutingDomainConfig *)a1, Source);
        v10 = v9;
        v31 = v9;
        if ( !v9 || !(_QWORD)xmmword_1800710A0 )
          goto LABEL_77;
        v11 = L"%s: UpdateTransportInfo: UpdateIkev2Config failed: %d";
        goto LABEL_74;
    }
    goto LABEL_41;
  }
  if ( a2 == 2048 )
  {
    v24 = RRasRoutingDomainConfig::UpdateAccountingConfig((RRasRoutingDomainConfig *)a1, Source);
    v10 = v24;
    v31 = v24;
    if ( v24 )
    {
      if ( !(_QWORD)xmmword_1800710A0 )
        goto LABEL_77;
      v11 = L"%s: UpdateAccoountingConfig failed: %d";
    }
    else
    {
      if ( !a3 )
        goto LABEL_77;
      v25 = RRasRoutingDomainConfig::PersistAccountingConfig((RRasRoutingDomainConfig *)a1);
      v10 = v25;
      v31 = v25;
      if ( !v25 || !(_QWORD)xmmword_1800710A0 )
        goto LABEL_77;
      v11 = L"%s: PersistAccountingConfig failed: %d";
    }
    goto LABEL_74;
  }
  if ( a2 == 0x2000 )
  {
    v22 = ValidateQoSPolicies(Source);
    v10 = v22;
    v31 = v22;
    if ( v22 )
    {
      if ( !(_QWORD)xmmword_1800710A0 )
        goto LABEL_77;
      v11 = L"%s: ValidateQoSPolicies failed: %d";
    }
    else
    {
      CopyValidQoSPoliciesFromUserBuffer(a1 + 544, Source);
      if ( !a3 )
        goto LABEL_77;
      v23 = WriteQoSPoliciesToRegsitry(*(HKEY *)(a1 + 824));
      v10 = v23;
      v31 = v23;
      if ( !v23 || !(_QWORD)xmmword_1800710A0 )
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
      v31 = 50;
      if ( !(_QWORD)xmmword_1800710A0 )
        goto LABEL_77;
      v10 = (unsigned int)a2;
      v11 = L"%s: set config not supported for cfg type: %d";
      goto LABEL_74;
    }
    v32 = 0;
    v17 = RRasRoutingDomainConfig::UpdateRouterType((RRasRoutingDomainConfig *)a1, *(_DWORD *)Source, &v32);
    v10 = v17;
    v31 = v17;
    if ( v17 )
    {
      if ( !(_QWORD)xmmword_1800710A0 )
        goto LABEL_77;
      v11 = L"%s: UpdateRouterType failed: %d";
      goto LABEL_74;
    }
    if ( !a3 )
      goto LABEL_77;
    v18 = RegSetValueExW(*(HKEY *)(a1 + 824), L"RouterType", 0, 4u, (const BYTE *)(a1 + 536), 4u);
    v10 = v18;
    v31 = v18;
    if ( v18 )
    {
      if ( !(_QWORD)xmmword_1800710A0 )
        goto LABEL_77;
      v11 = L"%s: RegSetValueEx(RouterType) failed: %d";
      goto LABEL_74;
    }
    v19 = !v32;
LABEL_52:
    if ( v19 )
      goto LABEL_77;
    v20 = RRasRoutingDomainConfig::PersistDialInConfig((RRasRoutingDomainConfig *)a1);
    v10 = v20;
    v31 = v20;
    if ( !v20 || !(_QWORD)xmmword_1800710A0 )
      goto LABEL_77;
    v11 = L"%s: PersistDialInConfig failed: %d";
    goto LABEL_74;
  }
  v21 = RRasRoutingDomainConfig::UpdateDialInConfig((RRasRoutingDomainConfig *)a1, Source);
  v10 = v21;
  v31 = v21;
  if ( !v21 )
  {
    v19 = a3 == 0;
    goto LABEL_52;
  }
  if ( !(_QWORD)xmmword_1800710A0 )
    goto LABEL_77;
  v11 = L"%s: UpdateDialInConfig failed: %d";
LABEL_74:
  LOWORD(v44) = 0;
  v39 = GUID_NULL;
  LOWORD(v40) = 0;
  FormatRRASErrorString(&v44, v11, L"RRasRoutingDomainConfig::SetConfigParam", v10);
  v26 = &v39;
  if ( a1 != -516 )
    v26 = (GUID *)(a1 + 516);
  ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
    gCfgStoreEtwContext,
    xmmword_1800710A0,
    &v44,
    v26,
    0,
    &v40);
LABEL_77:
  v27 = v31;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v33);
  return v27;
}

```

## disassembly

```asm
0x1800416fc  mov     [rsp-8+arg_10], rbx
0x180041701  mov     [rsp-8+arg_18], rsi
0x180041706  push    rbp
0x180041707  push    rdi
0x180041708  push    r12
0x18004170a  push    r14
0x18004170c  push    r15
0x18004170e  lea     rbp, [rsp-7D0h]
0x180041716  sub     rsp, 8D0h
0x18004171d  mov     rax, cs:__security_cookie
0x180041724  xor     rax, rsp
0x180041727  mov     [rbp+7F0h+var_30], rax
0x18004172e  mov     r14d, r8d
0x180041731  mov     esi, edx
0x180041733  mov     rbx, rcx
0x180041736  mov     rdi, [rbp+7F0h+Source]
0x18004173d  xor     r15d, r15d
0x180041740  mov     [rsp+8F0h+var_8B0], r15d
0x180041745  mov     [rbp+7F0h+var_830], r15d
0x180041749  xor     edx, edx; Val
0x18004174b  mov     r8d, 7FCh; Size
0x180041751  lea     rcx, [rbp+7F0h+var_82C]; void *
0x180041755  call    memset_0
0x18004175a  mov     [rbp+7F0h+var_860], r15d
0x18004175e  xorps   xmm0, xmm0
0x180041761  xor     eax, eax
0x180041763  movups  [rbp+7F0h+var_85C], xmm0
0x180041767  movups  [rbp+7F0h+var_84C], xmm0
0x18004176b  mov     [rbp+7F0h+var_83C], eax
0x18004176e  movdqu  [rsp+8F0h+var_8A0], xmm0
0x180041774  mov     [rsp+8F0h+var_8A8], r15
0x180041779  xorps   xmm1, xmm1
0x18004177c  movdqu  [rsp+8F0h+var_890], xmm1
0x180041782  mov     [rsp+8F0h+var_880], r15
0x180041787  mov     [rsp+8F0h+var_878], 0FFFFFFFFh
0x18004178f  mov     [rsp+8F0h+var_874], r15d
0x180041794  lea     r12, aRrasroutingdom_37; "RRasRoutingDomainConfig::SetConfigParam"
0x18004179b  cmp     qword ptr cs:xmmword_1800710A0+8, r15
0x1800417a2  jz      short loc_1800417C2
0x1800417a4  lea     rax, [rbx+204h]
0x1800417ab  mov     [rsp+8F0h+lpData], rax; struct _GUID *
0x1800417b0  lea     r8, [rsp+8F0h+var_8B0]; unsigned int *
0x1800417b5  mov     rdx, r12; unsigned __int16 *
0x1800417b8  lea     rcx, [rsp+8F0h+var_8A8]; this
0x1800417bd  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x1800417c2  test    rdi, rdi
0x1800417c5  jnz     short loc_180041821
0x1800417c7  mov     [rsp+8F0h+var_8B0], 57h ; 'W'
0x1800417cf  cmp     qword ptr cs:xmmword_180071090, r15
0x1800417d6  jz      loc_180041C61
0x1800417dc  mov     word ptr [rbp+7F0h+var_830], r15w
0x1800417e1  mov     r9d, 0A2Fh
0x1800417e7  lea     r8, aRrasroutingdom_26; "RRasRoutingDomainConfig::SetConfigParam"
0x1800417ee  lea     rdx, aHsLineDInvalid; "%hs(Line#%d): Invalid parameter."
0x1800417f5  lea     rcx, [rbp+7F0h+var_830]
0x1800417f9  call    FormatRRASErrorString
0x1800417fe  lea     r8, [rbp+7F0h+var_830]
0x180041802  mov     rdx, qword ptr cs:xmmword_180071090
0x180041809  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180041810  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180041817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004181c  jmp     loc_180041C61
0x180041821  mov     eax, 80h
0x180041826  cmp     esi, eax
0x180041828  jg      loc_1800419B4
0x18004182e  jz      short loc_180041857
0x180041830  mov     ecx, esi
0x180041832  sub     ecx, 1
0x180041835  jz      loc_18004194C
0x18004183b  sub     ecx, 1
0x18004183e  jz      loc_1800418E4
0x180041844  sub     ecx, 2
0x180041847  jz      short loc_1800418BD
0x180041849  sub     ecx, 4
0x18004184c  jz      short loc_18004188A
0x18004184e  cmp     ecx, 18h
0x180041851  jnz     loc_1800419E8
0x180041857  mov     rdx, rdi; struct _MPRI_TRANSPORT_INFO_1 *
0x18004185a  mov     rcx, rbx; this
0x18004185d  call    ?UpdateTransportInfo@RRasRoutingDomainConfig@@AEAAKPEAU_MPRI_TRANSPORT_INFO_1@@@Z; RRasRoutingDomainConfig::UpdateTransportInfo(_MPRI_TRANSPORT_INFO_1 *)
0x180041862  mov     r9d, eax
0x180041865  mov     [rsp+8F0h+var_8B0], eax
0x180041869  test    eax, eax
0x18004186b  jz      loc_180041C61
0x180041871  cmp     qword ptr cs:xmmword_1800710A0, r15
0x180041878  jz      loc_180041C61
0x18004187e  lea     rdx, aSUpdatetranspo; "%s: UpdateTransportInfo: UpdateIkev2Con"...
0x180041885  jmp     loc_180041C01
0x18004188a  mov     rdx, rdi; struct _IKEV2_TUNNEL_CONFIG_PARAMS_4 *
0x18004188d  mov     rcx, rbx; this
0x180041890  call    ?UpdateIkev2Config@RRasRoutingDomainConfig@@AEAAKPEAU_IKEV2_TUNNEL_CONFIG_PARAMS_4@@@Z; RRasRoutingDomainConfig::UpdateIkev2Config(_IKEV2_TUNNEL_CONFIG_PARAMS_4 *)
0x180041895  mov     r9d, eax
0x180041898  mov     [rsp+8F0h+var_8B0], eax
0x18004189c  test    eax, eax
0x18004189e  jz      loc_180041C61
0x1800418a4  cmp     qword ptr cs:xmmword_1800710A0, r15
0x1800418ab  jz      loc_180041C61
0x1800418b1  lea     rdx, aSUpdateikev2co; "%s: UpdateIkev2Config failed: %d"
0x1800418b8  jmp     loc_180041C01
0x1800418bd  mov     r9d, [rsp+8F0h+var_8B0]
0x1800418c2  test    r9d, r9d
0x1800418c5  jz      loc_180041C61
0x1800418cb  cmp     qword ptr cs:xmmword_1800710A0, r15
0x1800418d2  jz      loc_180041C61
0x1800418d8  lea     rdx, aSUpdatepreshar; "%s: UpdatePreSharedKey failed: %d"
0x1800418df  jmp     loc_180041C01
0x1800418e4  mov     rdx, rdi; struct _MPRI_IPV6_CONFIG_1 *
0x1800418e7  mov     rcx, rbx; this
0x1800418ea  call    ?UpdateIpv6AddrPool@RRasRoutingDomainConfig@@AEAAKPEAU_MPRI_IPV6_CONFIG_1@@@Z; RRasRoutingDomainConfig::UpdateIpv6AddrPool(_MPRI_IPV6_CONFIG_1 *)
0x1800418ef  mov     r9d, eax
0x1800418f2  mov     [rsp+8F0h+var_8B0], eax
0x1800418f6  test    eax, eax
0x1800418f8  jz      short loc_180041913
0x1800418fa  cmp     qword ptr cs:xmmword_1800710A0, r15
0x180041901  jz      loc_180041C61
0x180041907  lea     rdx, aSUpdateipv6add; "%s: UpdateIpv6AddrPool failed: %d"
0x18004190e  jmp     loc_180041C01
0x180041913  test    r14d, r14d
0x180041916  jz      loc_180041C61
0x18004191c  mov     rcx, rbx; this
0x18004191f  call    ?PersistIpv6AddrPool@RRasRoutingDomainConfig@@AEAAKXZ; RRasRoutingDomainConfig::PersistIpv6AddrPool(void)
0x180041924  mov     r9d, eax
0x180041927  mov     [rsp+8F0h+var_8B0], eax
0x18004192b  test    eax, eax
0x18004192d  jz      loc_180041C61
0x180041933  cmp     qword ptr cs:xmmword_1800710A0, r15
0x18004193a  jz      loc_180041C61
0x180041940  lea     rdx, aSRefreshFailed_0; "%s: Refresh failed for IPv6 address poo"...
0x180041947  jmp     loc_180041C01
0x18004194c  mov     rdx, rdi; struct _MPRI_IPV4_CONFIG_1 *
0x18004194f  mov     rcx, rbx; this
0x180041952  call    ?UpdateIpv4AddrPool@RRasRoutingDomainConfig@@AEAAKPEAU_MPRI_IPV4_CONFIG_1@@@Z; RRasRoutingDomainConfig::UpdateIpv4AddrPool(_MPRI_IPV4_CONFIG_1 *)
0x180041957  mov     r9d, eax
0x18004195a  mov     [rsp+8F0h+var_8B0], eax
0x18004195e  test    eax, eax
0x180041960  jz      short loc_18004197B
0x180041962  cmp     qword ptr cs:xmmword_1800710A0, r15
0x180041969  jz      loc_180041C61
0x18004196f  lea     rdx, aSUpdateipv4add; "%s: UpdateIpv4AddrPool failed: %d"
0x180041976  jmp     loc_180041C01
0x18004197b  test    r14d, r14d
0x18004197e  jz      loc_180041C61
0x180041984  mov     rcx, rbx; this
0x180041987  call    ?PersistIpv4AddrPool@RRasRoutingDomainConfig@@AEAAKXZ; RRasRoutingDomainConfig::PersistIpv4AddrPool(void)
0x18004198c  mov     r9d, eax
0x18004198f  mov     [rsp+8F0h+var_8B0], eax
0x180041993  test    eax, eax
0x180041995  jz      loc_180041C61
0x18004199b  cmp     qword ptr cs:xmmword_1800710A0, r15
0x1800419a2  jz      loc_180041C61
0x1800419a8  lea     rdx, aSPersistFailed; "%s: Persist failed for IPv4 address poo"...
0x1800419af  jmp     loc_180041C01
0x1800419b4  cmp     esi, 800h
0x1800419ba  jz      loc_180041BA9
0x1800419c0  cmp     esi, 2000h
0x1800419c6  jz      loc_180041B2E
0x1800419cc  cmp     esi, 4000h
0x1800419d2  jz      loc_180041AFA
0x1800419d8  cmp     esi, 8000h
0x1800419de  jz      short loc_180041A29
0x1800419e0  cmp     esi, 10000h
0x1800419e6  jz      short loc_180041A0C
0x1800419e8  mov     [rsp+8F0h+var_8B0], 32h ; '2'
0x1800419f0  cmp     qword ptr cs:xmmword_1800710A0, r15
0x1800419f7  jz      loc_180041C61
0x1800419fd  mov     r9d, esi
0x180041a00  lea     rdx, aSSetConfigNotS; "%s: set config not supported for cfg ty"...
0x180041a07  jmp     loc_180041C01
0x180041a0c  lea     rcx, [rbx+348h]; Destination
0x180041a13  mov     edx, 10h; DestinationSize
0x180041a18  mov     r9d, edx; SourceSize
0x180041a1b  mov     r8, rdi; Source
0x180041a1e  call    cs:__imp_memcpy_s
0x180041a24  jmp     loc_180041C61
0x180041a29  mov     [rsp+8F0h+var_8AC], r15b
0x180041a2e  lea     r8, [rsp+8F0h+var_8AC]; bool *
0x180041a33  mov     edx, [rdi]; unsigned int
0x180041a35  mov     rcx, rbx; this
0x180041a38  call    ?UpdateRouterType@RRasRoutingDomainConfig@@AEAAKKPEA_N@Z; RRasRoutingDomainConfig::UpdateRouterType(ulong,bool *)
0x180041a3d  mov     r9d, eax
0x180041a40  mov     [rsp+8F0h+var_8B0], eax
0x180041a44  test    eax, eax
0x180041a46  jz      short loc_180041A61
0x180041a48  cmp     qword ptr cs:xmmword_1800710A0, r15
0x180041a4f  jz      loc_180041C61
0x180041a55  lea     rdx, aSUpdateroutert; "%s: UpdateRouterType failed: %d"
0x180041a5c  jmp     loc_180041C01
0x180041a61  test    r14d, r14d
0x180041a64  jz      loc_180041C61
0x180041a6a  lea     rax, [rbx+218h]
0x180041a71  mov     [rsp+8F0h+cbData], 4; cbData
0x180041a79  mov     [rsp+8F0h+lpData], rax; lpData
0x180041a7e  mov     r9d, 4; dwType
0x180041a84  xor     r8d, r8d; Reserved
0x180041a87  lea     rdx, aRoutertype; "RouterType"
0x180041a8e  mov     rcx, [rbx+338h]; hKey
0x180041a95  call    cs:__imp_RegSetValueExW
0x180041a9b  mov     r9d, eax
0x180041a9e  mov     [rsp+8F0h+var_8B0], eax
0x180041aa2  test    eax, eax
0x180041aa4  jz      short loc_180041ABF
0x180041aa6  cmp     qword ptr cs:xmmword_1800710A0, r15
0x180041aad  jz      loc_180041C61
0x180041ab3  lea     rdx, aSRegsetvalueex_0; "%s: RegSetValueEx(RouterType) failed: %"...
0x180041aba  jmp     loc_180041C01
0x180041abf  cmp     [rsp+8F0h+var_8AC], r15b
0x180041ac4  jz      loc_180041C61
0x180041aca  mov     rcx, rbx; this
0x180041acd  call    ?PersistDialInConfig@RRasRoutingDomainConfig@@AEAAKXZ; RRasRoutingDomainConfig::PersistDialInConfig(void)
0x180041ad2  mov     r9d, eax
0x180041ad5  mov     [rsp+8F0h+var_8B0], eax
0x180041ad9  test    eax, eax
0x180041adb  jz      loc_180041C61
0x180041ae1  cmp     qword ptr cs:xmmword_1800710A0, r15
0x180041ae8  jz      loc_180041C61
0x180041aee  lea     rdx, aSPersistdialin; "%s: PersistDialInConfig failed: %d"
0x180041af5  jmp     loc_180041C01
0x180041afa  mov     rdx, rdi; struct _MPRI_DIAL_IN_CONFIG_1 *
0x180041afd  mov     rcx, rbx; this
0x180041b00  call    ?UpdateDialInConfig@RRasRoutingDomainConfig@@AEAAKPEAU_MPRI_DIAL_IN_CONFIG_1@@@Z; RRasRoutingDomainConfig::UpdateDialInConfig(_MPRI_DIAL_IN_CONFIG_1 *)
0x180041b05  mov     r9d, eax
0x180041b08  mov     [rsp+8F0h+var_8B0], eax
0x180041b0c  test    eax, eax
0x180041b0e  jz      short loc_180041B29
0x180041b10  cmp     qword ptr cs:xmmword_1800710A0, r15
0x180041b17  jz      loc_180041C61
0x180041b1d  lea     rdx, aSUpdatedialinc_0; "%s: UpdateDialInConfig failed: %d"
0x180041b24  jmp     loc_180041C01
0x180041b29  test    r14d, r14d
0x180041b2c  jmp     short loc_180041AC4
0x180041b2e  mov     rcx, rdi
0x180041b31  call    ValidateQoSPolicies
0x180041b36  mov     r9d, eax
0x180041b39  mov     [rsp+8F0h+var_8B0], eax
0x180041b3d  test    eax, eax
0x180041b3f  jz      short loc_180041B5A
0x180041b41  cmp     qword ptr cs:xmmword_1800710A0, r15
0x180041b48  jz      loc_180041C61
0x180041b4e  lea     rdx, aSValidateqospo; "%s: ValidateQoSPolicies failed: %d"
0x180041b55  jmp     loc_180041C01
0x180041b5a  lea     rsi, [rbx+220h]
0x180041b61  mov     rdx, rdi
0x180041b64  mov     rcx, rsi
0x180041b67  call    CopyValidQoSPoliciesFromUserBuffer
0x180041b6c  test    r14d, r14d
0x180041b6f  jz      loc_180041C61
0x180041b75  mov     rdx, rsi
0x180041b78  mov     rcx, [rbx+338h]; hKey
0x180041b7f  call    WriteQoSPoliciesToRegsitry
0x180041b84  mov     r9d, eax
0x180041b87  mov     [rsp+8F0h+var_8B0], eax
0x180041b8b  test    eax, eax
0x180041b8d  jz      loc_180041C61
0x180041b93  cmp     qword ptr cs:xmmword_1800710A0, r15
0x180041b9a  jz      loc_180041C61
0x180041ba0  lea     rdx, aSPersistFailed_0; "%s: Persist failed for QoS policies: %d"
0x180041ba7  jmp     short loc_180041C01
0x180041ba9  mov     rdx, rdi; struct _MPRI_ACCOUNTING_CONFIG_1 *
0x180041bac  mov     rcx, rbx; this
0x180041baf  call    ?UpdateAccountingConfig@RRasRoutingDomainConfig@@AEAAKPEAU_MPRI_ACCOUNTING_CONFIG_1@@@Z; RRasRoutingDomainConfig::UpdateAccountingConfig(_MPRI_ACCOUNTING_CONFIG_1 *)
0x180041bb4  mov     r9d, eax
0x180041bb7  mov     [rsp+8F0h+var_8B0], eax
0x180041bbb  test    eax, eax
0x180041bbd  jz      short loc_180041BD5
0x180041bbf  cmp     qword ptr cs:xmmword_1800710A0, r15
0x180041bc6  jz      loc_180041C61
0x180041bcc  lea     rdx, aSUpdateaccooun; "%s: UpdateAccoountingConfig failed: %d"
0x180041bd3  jmp     short loc_180041C01
0x180041bd5  test    r14d, r14d
0x180041bd8  jz      loc_180041C61
0x180041bde  mov     rcx, rbx; this
0x180041be1  call    ?PersistAccountingConfig@RRasRoutingDomainConfig@@AEAAKXZ; RRasRoutingDomainConfig::PersistAccountingConfig(void)
0x180041be6  mov     r9d, eax
0x180041be9  mov     [rsp+8F0h+var_8B0], eax
0x180041bed  test    eax, eax
0x180041bef  jz      short loc_180041C61
0x180041bf1  cmp     qword ptr cs:xmmword_1800710A0, r15
0x180041bf8  jz      short loc_180041C61
0x180041bfa  lea     rdx, aSPersistaccoun; "%s: PersistAccountingConfig failed: %d"
0x180041c01  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180041c08  mov     word ptr [rbp+7F0h+var_830], r15w
0x180041c0d  movdqu  [rbp+7F0h+var_870], xmm0
0x180041c12  mov     word ptr [rbp+7F0h+var_860], r15w
0x180041c17  mov     r8, r12
0x180041c1a  lea     rcx, [rbp+7F0h+var_830]
0x180041c1e  call    FormatRRASErrorString
0x180041c23  lea     rcx, [rbx+204h]
0x180041c2a  lea     rax, [rbp+7F0h+var_860]
0x180041c2e  lea     r9, [rbp+7F0h+var_870]
0x180041c32  test    rcx, rcx
0x180041c35  mov     qword ptr [rsp+8F0h+cbData], rax
0x180041c3a  cmovnz  r9, rcx
0x180041c3e  mov     [rsp+8F0h+lpData], r15
0x180041c43  lea     r8, [rbp+7F0h+var_830]
0x180041c47  mov     rdx, qword ptr cs:xmmword_1800710A0
0x180041c4e  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180041c55  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180041c5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c61  mov     ebx, [rsp+8F0h+var_8B0]
0x180041c65  lea     rcx, [rsp+8F0h+var_8A8]; this
  ... truncated ...
```
