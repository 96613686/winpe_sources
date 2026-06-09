# RRasRoutingDomainConfig::UpdateConfigEx1Data(_MPRI_ROUTING_DOMAIN_CONFIG_EX1 *)

- ea: `0x180042398`
- end: `0x1800427c9`
- name: `?UpdateConfigEx1Data@RRasRoutingDomainConfig@@AEAAKPEAU_MPRI_ROUTING_DOMAIN_CONFIG_EX1@@@Z`
- size: `1073`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, struct _MPRI_ROUTING_DOMAIN_CONFIG_EX1 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update`

## callers

- `0x180041494`

## callees

- `0x180035118`
- `0x180037d0c`
- `0x180042090`
- `0x180042398`
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

## string_xrefs

- `0x180042441`: `RRasRoutingDomainConfig::UpdateConfigEx1Data`
- `0x180042526`: `RRasRoutingDomainConfig::UpdateConfigEx1Data`
- `0x18004265f`: `RRasRoutingDomainConfig::UpdateConfigEx1Data`
- `0x18004273a`: `RRasRoutingDomainConfig::UpdateConfigEx1Data`
- `0x180042666`: `%s: UpdateTransportInfo failed: %d.`
- `0x1800425a7`: `%s: UpdateDialInConfig failed: %d.`
- `0x180042506`: `%s: UpdateRouterType failed: %d.`
- `0x180042741`: `%s: SetConfig failed for cfg type (%d): %d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RRasRoutingDomainConfig::UpdateConfigEx1Data(
        RRasRoutingDomainConfig *this,
        struct _MPRI_ROUTING_DOMAIN_CONFIG_EX1 *a2)
{
  unsigned int v4; // ebx
  void (*v5)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  unsigned int i; // r15d
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  unsigned int v16; // eax
  const wchar_t *v17; // rdx
  GUID *v18; // r9
  unsigned int updated; // eax
  unsigned int j; // r14d
  unsigned int v21; // eax
  GUID *v22; // r9
  GUID *v23; // r9
  struct _GUID *v25; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v26; // [rsp+28h] [rbp-D8h]
  unsigned int v27; // [rsp+30h] [rbp-D0h]
  unsigned int v28; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v29; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v30; // [rsp+50h] [rbp-B0h]
  __int128 v31; // [rsp+60h] [rbp-A0h]
  __int64 v32; // [rsp+70h] [rbp-90h]
  int v33; // [rsp+78h] [rbp-88h]
  int v34; // [rsp+7Ch] [rbp-84h]
  GUID v35; // [rsp+80h] [rbp-80h] BYREF
  int v36; // [rsp+90h] [rbp-70h] BYREF
  __int128 v37; // [rsp+94h] [rbp-6Ch]
  __int128 v38; // [rsp+A4h] [rbp-5Ch]
  int v39; // [rsp+B4h] [rbp-4Ch]
  int v40; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v41[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v4 = 0;
  v28 = 0;
  v40 = 0;
  memset_0(v41, 0, sizeof(v41));
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v30 = 0;
  v29 = 0;
  v31 = 0;
  v32 = 0;
  v33 = -1;
  v34 = 0;
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v29,
      L"RRasRoutingDomainConfig::UpdateConfigEx1Data",
      &v28,
      v5,
      (struct _GUID *)((char *)this + 516),
      v26,
      v27);
    v4 = v28;
  }
  for ( i = 0; i < 0xC; ++i )
  {
    v7 = *((_DWORD *)qword_180066550 + i);
    if ( (v7 & *((_DWORD *)a2 + 161)) == 0 )
      continue;
    v8 = v7 - 1;
    if ( !v8 )
    {
      updated = RRasRoutingDomainConfig::UpdateIpv4AddrPool(
                  this,
                  (struct _MPRI_ROUTING_DOMAIN_CONFIG_EX1 *)((char *)a2 + 648));
      goto LABEL_41;
    }
    v9 = v8 - 1;
    if ( !v9 )
    {
      updated = RRasRoutingDomainConfig::UpdateIpv6AddrPool(
                  this,
                  (struct _MPRI_ROUTING_DOMAIN_CONFIG_EX1 *)((char *)a2 + 664));
      goto LABEL_41;
    }
    v10 = v9 - 2;
    if ( !v10 )
      goto LABEL_42;
    v11 = v10 - 4;
    if ( !v11 )
    {
      updated = RRasRoutingDomainConfig::UpdateIkev2Config(
                  this,
                  (struct _MPRI_ROUTING_DOMAIN_CONFIG_EX1 *)((char *)a2 + 688));
      goto LABEL_41;
    }
    v12 = v11 - 8;
    if ( v12 )
    {
      v13 = v12 - 2032;
      if ( !v13 )
      {
        updated = RRasRoutingDomainConfig::UpdateAccountingConfig(
                    this,
                    (struct _MPRI_ROUTING_DOMAIN_CONFIG_EX1 *)((char *)a2 + 792));
LABEL_41:
        v28 = updated;
        v4 = updated;
        goto LABEL_42;
      }
      v14 = v13 - 6144;
      if ( v14 )
      {
        v15 = v14 - 0x2000;
        if ( v15 )
        {
          if ( v15 != 0x4000 )
          {
            v4 = 50;
            v28 = 50;
LABEL_45:
            if ( (_QWORD)xmmword_1800710A0 )
            {
              LOWORD(v40) = 0;
              v35 = GUID_NULL;
              LOWORD(v36) = 0;
              LODWORD(v25) = v4;
              FormatRRASErrorString(
                &v40,
                L"%s: SetConfig failed for cfg type (%d): %d.",
                L"RRasRoutingDomainConfig::UpdateConfigEx1Data",
                *((unsigned int *)qword_180066550 + i),
                v25);
              v23 = &v35;
              if ( this != (RRasRoutingDomainConfig *)-516LL )
                v23 = (GUID *)((char *)this + 516);
              ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
                gCfgStoreEtwContext,
                xmmword_1800710A0,
                &v40,
                v23,
                0,
                &v36);
              v4 = v28;
            }
            break;
          }
          v16 = RRasRoutingDomainConfig::UpdateRouterType(this, *((_DWORD *)a2 + 133), 0);
          v4 = v16;
          v28 = v16;
          if ( !v16 || !(_QWORD)xmmword_1800710A0 )
            goto LABEL_42;
          v17 = L"%s: UpdateRouterType failed: %d.";
LABEL_18:
          LOWORD(v40) = 0;
          v35 = GUID_NULL;
          LOWORD(v36) = 0;
          FormatRRASErrorString(&v40, v17, L"RRasRoutingDomainConfig::UpdateConfigEx1Data", v16);
          v18 = &v35;
          if ( this != (RRasRoutingDomainConfig *)-516LL )
            v18 = (GUID *)((char *)this + 516);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
            gCfgStoreEtwContext,
            xmmword_1800710A0,
            &v40,
            v18,
            0,
            &v36);
LABEL_21:
          v4 = v28;
          goto LABEL_42;
        }
        v16 = RRasRoutingDomainConfig::UpdateDialInConfig(
                this,
                (struct _MPRI_ROUTING_DOMAIN_CONFIG_EX1 *)((char *)a2 + 536));
        v4 = v16;
        v28 = v16;
        if ( v16 && (_QWORD)xmmword_1800710A0 )
        {
          v17 = L"%s: UpdateDialInConfig failed: %d.";
          goto LABEL_18;
        }
      }
      else
      {
        v16 = ValidateQoSPolicies((char *)a2 + 832);
        v4 = v16;
        v28 = v16;
        if ( !v16 )
        {
          CopyValidQoSPoliciesFromUserBuffer((char *)this + 544, (char *)a2 + 832);
          goto LABEL_21;
        }
        if ( (_QWORD)xmmword_1800710A0 )
        {
          v17 = L"%s: ValidateQoSPolicies failed: %d.";
          goto LABEL_18;
        }
      }
    }
    else
    {
      for ( j = 0; j < *((_DWORD *)a2 + 200); ++j )
      {
        v21 = RRasRoutingDomainConfig::UpdateTransportInfo(
                this,
                (struct _MPRI_TRANSPORT_INFO_1 *)(*((_QWORD *)a2 + 101) + 16LL * j));
        v4 = v21;
        v28 = v21;
        if ( v21 && (_QWORD)xmmword_1800710A0 )
        {
          LOWORD(v40) = 0;
          v35 = GUID_NULL;
          LOWORD(v36) = 0;
          FormatRRASErrorString(
            &v40,
            L"%s: UpdateTransportInfo failed: %d.",
            L"RRasRoutingDomainConfig::UpdateConfigEx1Data",
            v21);
          v22 = &v35;
          if ( this != (RRasRoutingDomainConfig *)-516LL )
            v22 = (GUID *)((char *)this + 516);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
            gCfgStoreEtwContext,
            xmmword_1800710A0,
            &v40,
            v22,
            0,
            &v36);
          v4 = v28;
        }
      }
    }
LABEL_42:
    if ( v4 )
      goto LABEL_45;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v29);
  return v4;
}

```

## disassembly

```asm
0x180042398  mov     [rsp-8+arg_10], rbx
0x18004239d  push    rbp
0x18004239e  push    rsi
0x18004239f  push    rdi
0x1800423a0  push    r12
0x1800423a2  push    r13
0x1800423a4  push    r14
0x1800423a6  push    r15
0x1800423a8  lea     rbp, [rsp-7D0h]
0x1800423b0  sub     rsp, 8D0h
0x1800423b7  mov     rax, cs:__security_cookie
0x1800423be  xor     rax, rsp
0x1800423c1  mov     [rbp+800h+var_40], rax
0x1800423c8  mov     rsi, rdx
0x1800423cb  mov     rdi, rcx
0x1800423ce  xor     r13d, r13d
0x1800423d1  mov     ebx, r13d
0x1800423d4  mov     [rsp+900h+var_8C0], ebx
0x1800423d8  mov     [rbp+800h+var_840], r13d
0x1800423dc  xor     edx, edx; Val
0x1800423de  mov     r8d, 7FCh; Size
0x1800423e4  lea     rcx, [rbp+800h+var_83C]; void *
0x1800423e8  call    memset_0
0x1800423ed  mov     [rbp+800h+var_870], r13d
0x1800423f1  xorps   xmm0, xmm0
0x1800423f4  xor     eax, eax
0x1800423f6  movups  [rbp+800h+var_86C], xmm0
0x1800423fa  movups  [rbp+800h+var_85C], xmm0
0x1800423fe  mov     [rbp+800h+var_84C], eax
0x180042401  movdqu  [rsp+900h+var_8B0], xmm0
0x180042407  mov     [rsp+900h+var_8B8], r13
0x18004240c  xorps   xmm1, xmm1
0x18004240f  movdqu  [rsp+900h+var_8A0], xmm1
0x180042415  mov     [rsp+900h+var_890], r13
0x18004241a  mov     [rsp+900h+var_888], 0FFFFFFFFh
0x180042422  mov     [rsp+900h+var_884], r13d
0x180042427  cmp     qword ptr cs:xmmword_1800710A0+8, r13
0x18004242e  jz      short loc_180042456
0x180042430  lea     rax, [rdi+204h]
0x180042437  mov     [rsp+900h+var_8E0], rax; struct _GUID *
0x18004243c  lea     r8, [rsp+900h+var_8C0]; unsigned int *
0x180042441  lea     rdx, aRrasroutingdom_45; "RRasRoutingDomainConfig::UpdateConfigEx"...
0x180042448  lea     rcx, [rsp+900h+var_8B8]; this
0x18004244d  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x180042452  mov     ebx, [rsp+900h+var_8C0]
0x180042456  mov     r15d, r13d
0x180042459  cmp     r15d, 0Ch
0x18004245d  jnb     loc_180042793
0x180042463  mov     r12d, r15d
0x180042466  lea     rdx, qword_180066550
0x18004246d  mov     ecx, [rdx+r12*4]
0x180042471  test    [rsi+284h], ecx
0x180042477  jz      loc_180042702
0x18004247d  sub     ecx, 1
0x180042480  jz      loc_1800426E2
0x180042486  sub     ecx, 1
0x180042489  jz      loc_1800426D1
0x18004248f  sub     ecx, 2
0x180042492  jz      loc_1800426FE
0x180042498  sub     ecx, 4
0x18004249b  jz      loc_1800426C0
0x1800424a1  sub     ecx, 8
0x1800424a4  jz      loc_18004260D
0x1800424aa  sub     ecx, 7F0h
0x1800424b0  jz      loc_1800425F9
0x1800424b6  sub     ecx, 1800h
0x1800424bc  jz      loc_1800425B3
0x1800424c2  sub     ecx, 2000h
0x1800424c8  jz      loc_18004257D
0x1800424ce  cmp     ecx, 4000h
0x1800424d4  jnz     loc_18004270A
0x1800424da  xor     r8d, r8d; bool *
0x1800424dd  mov     edx, [rsi+214h]; unsigned int
0x1800424e3  mov     rcx, rdi; this
0x1800424e6  call    ?UpdateRouterType@RRasRoutingDomainConfig@@AEAAKKPEA_N@Z; RRasRoutingDomainConfig::UpdateRouterType(ulong,bool *)
0x1800424eb  mov     ebx, eax
0x1800424ed  mov     [rsp+900h+var_8C0], eax
0x1800424f1  test    eax, eax
0x1800424f3  jz      loc_1800426F7
0x1800424f9  cmp     qword ptr cs:xmmword_1800710A0, r13
0x180042500  jz      loc_1800426F7
0x180042506  lea     rdx, aSUpdateroutert_0; "%s: UpdateRouterType failed: %d."
0x18004250d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180042514  mov     word ptr [rbp+800h+var_840], r13w
0x180042519  movdqu  [rbp+800h+var_880], xmm0
0x18004251e  mov     word ptr [rbp+800h+var_870], r13w
0x180042523  mov     r9d, eax
0x180042526  lea     r8, aRrasroutingdom_45; "RRasRoutingDomainConfig::UpdateConfigEx"...
0x18004252d  lea     rcx, [rbp+800h+var_840]
0x180042531  call    FormatRRASErrorString
0x180042536  lea     rcx, [rdi+204h]
0x18004253d  lea     r9, [rbp+800h+var_880]
0x180042541  test    rcx, rcx
0x180042544  cmovnz  r9, rcx
0x180042548  lea     rax, [rbp+800h+var_870]
0x18004254c  mov     [rsp+900h+var_8D8], rax
0x180042551  mov     [rsp+900h+var_8E0], r13
0x180042556  lea     r8, [rbp+800h+var_840]
0x18004255a  mov     rdx, qword ptr cs:xmmword_1800710A0
0x180042561  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180042568  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004256f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042574  mov     ebx, [rsp+900h+var_8C0]
0x180042578  jmp     loc_1800426F7
0x18004257d  lea     rdx, [rsi+218h]; struct _MPRI_DIAL_IN_CONFIG_1 *
0x180042584  mov     rcx, rdi; this
0x180042587  call    ?UpdateDialInConfig@RRasRoutingDomainConfig@@AEAAKPEAU_MPRI_DIAL_IN_CONFIG_1@@@Z; RRasRoutingDomainConfig::UpdateDialInConfig(_MPRI_DIAL_IN_CONFIG_1 *)
0x18004258c  mov     ebx, eax
0x18004258e  mov     [rsp+900h+var_8C0], eax
0x180042592  test    eax, eax
0x180042594  jz      loc_1800426F7
0x18004259a  cmp     qword ptr cs:xmmword_1800710A0, r13
0x1800425a1  jz      loc_1800426F7
0x1800425a7  lea     rdx, aSUpdatedialinc; "%s: UpdateDialInConfig failed: %d."
0x1800425ae  jmp     loc_18004250D
0x1800425b3  lea     r14, [rsi+340h]
0x1800425ba  mov     rcx, r14
0x1800425bd  call    ValidateQoSPolicies
0x1800425c2  mov     ebx, eax
0x1800425c4  mov     [rsp+900h+var_8C0], eax
0x1800425c8  test    eax, eax
0x1800425ca  jz      short loc_1800425E5
0x1800425cc  cmp     qword ptr cs:xmmword_1800710A0, r13
0x1800425d3  jz      loc_1800426F7
0x1800425d9  lea     rdx, aSValidateqospo_0; "%s: ValidateQoSPolicies failed: %d."
0x1800425e0  jmp     loc_18004250D
0x1800425e5  lea     rcx, [rdi+220h]
0x1800425ec  mov     rdx, r14
0x1800425ef  call    CopyValidQoSPoliciesFromUserBuffer
0x1800425f4  jmp     loc_180042574
0x1800425f9  lea     rdx, [rsi+318h]; struct _MPRI_ACCOUNTING_CONFIG_1 *
0x180042600  mov     rcx, rdi; this
0x180042603  call    ?UpdateAccountingConfig@RRasRoutingDomainConfig@@AEAAKPEAU_MPRI_ACCOUNTING_CONFIG_1@@@Z; RRasRoutingDomainConfig::UpdateAccountingConfig(_MPRI_ACCOUNTING_CONFIG_1 *)
0x180042608  jmp     loc_1800426F1
0x18004260d  mov     r14d, r13d
0x180042610  cmp     r14d, [rsi+320h]
0x180042617  jnb     loc_1800426F7
0x18004261d  mov     edx, r14d
0x180042620  shl     rdx, 4
0x180042624  add     rdx, [rsi+328h]; struct _MPRI_TRANSPORT_INFO_1 *
0x18004262b  mov     rcx, rdi; this
0x18004262e  call    ?UpdateTransportInfo@RRasRoutingDomainConfig@@AEAAKPEAU_MPRI_TRANSPORT_INFO_1@@@Z; RRasRoutingDomainConfig::UpdateTransportInfo(_MPRI_TRANSPORT_INFO_1 *)
0x180042633  mov     ebx, eax
0x180042635  mov     [rsp+900h+var_8C0], eax
0x180042639  test    eax, eax
0x18004263b  jz      short loc_1800426B8
0x18004263d  cmp     qword ptr cs:xmmword_1800710A0, r13
0x180042644  jz      short loc_1800426B8
0x180042646  mov     word ptr [rbp+800h+var_840], r13w
0x18004264b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180042652  movdqu  [rbp+800h+var_880], xmm0
0x180042657  mov     word ptr [rbp+800h+var_870], r13w
0x18004265c  mov     r9d, eax
0x18004265f  lea     r8, aRrasroutingdom_45; "RRasRoutingDomainConfig::UpdateConfigEx"...
0x180042666  lea     rdx, aSUpdatetranspo_0; "%s: UpdateTransportInfo failed: %d."
0x18004266d  lea     rcx, [rbp+800h+var_840]
0x180042671  call    FormatRRASErrorString
0x180042676  lea     rcx, [rdi+204h]
0x18004267d  lea     r9, [rbp+800h+var_880]
0x180042681  test    rcx, rcx
0x180042684  cmovnz  r9, rcx
0x180042688  lea     rax, [rbp+800h+var_870]
0x18004268c  mov     [rsp+900h+var_8D8], rax
0x180042691  mov     [rsp+900h+var_8E0], r13
0x180042696  lea     r8, [rbp+800h+var_840]
0x18004269a  mov     rdx, qword ptr cs:xmmword_1800710A0
0x1800426a1  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x1800426a8  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x1800426af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800426b4  mov     ebx, [rsp+900h+var_8C0]
0x1800426b8  inc     r14d
0x1800426bb  jmp     loc_180042610
0x1800426c0  lea     rdx, [rsi+2B0h]; struct _IKEV2_TUNNEL_CONFIG_PARAMS_4 *
0x1800426c7  mov     rcx, rdi; this
0x1800426ca  call    ?UpdateIkev2Config@RRasRoutingDomainConfig@@AEAAKPEAU_IKEV2_TUNNEL_CONFIG_PARAMS_4@@@Z; RRasRoutingDomainConfig::UpdateIkev2Config(_IKEV2_TUNNEL_CONFIG_PARAMS_4 *)
0x1800426cf  jmp     short loc_1800426F1
0x1800426d1  lea     rdx, [rsi+298h]; struct _MPRI_IPV6_CONFIG_1 *
0x1800426d8  mov     rcx, rdi; this
0x1800426db  call    ?UpdateIpv6AddrPool@RRasRoutingDomainConfig@@AEAAKPEAU_MPRI_IPV6_CONFIG_1@@@Z; RRasRoutingDomainConfig::UpdateIpv6AddrPool(_MPRI_IPV6_CONFIG_1 *)
0x1800426e0  jmp     short loc_1800426F1
0x1800426e2  lea     rdx, [rsi+288h]; struct _MPRI_IPV4_CONFIG_1 *
0x1800426e9  mov     rcx, rdi; this
0x1800426ec  call    ?UpdateIpv4AddrPool@RRasRoutingDomainConfig@@AEAAKPEAU_MPRI_IPV4_CONFIG_1@@@Z; RRasRoutingDomainConfig::UpdateIpv4AddrPool(_MPRI_IPV4_CONFIG_1 *)
0x1800426f1  mov     [rsp+900h+var_8C0], eax
0x1800426f5  mov     ebx, eax
0x1800426f7  lea     rdx, qword_180066550
0x1800426fe  test    ebx, ebx
0x180042700  jnz     short loc_180042713
0x180042702  inc     r15d
0x180042705  jmp     loc_180042459
0x18004270a  mov     ebx, 32h ; '2'
0x18004270f  mov     [rsp+900h+var_8C0], ebx
0x180042713  cmp     qword ptr cs:xmmword_1800710A0, r13
0x18004271a  jz      short loc_180042793
0x18004271c  mov     word ptr [rbp+800h+var_840], r13w
0x180042721  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180042728  movdqu  [rbp+800h+var_880], xmm0
0x18004272d  mov     word ptr [rbp+800h+var_870], r13w
0x180042732  mov     dword ptr [rsp+900h+var_8E0], ebx
0x180042736  mov     r9d, [rdx+r12*4]
0x18004273a  lea     r8, aRrasroutingdom_45; "RRasRoutingDomainConfig::UpdateConfigEx"...
0x180042741  lea     rdx, aSSetconfigFail; "%s: SetConfig failed for cfg type (%d):"...
0x180042748  lea     rcx, [rbp+800h+var_840]
0x18004274c  call    FormatRRASErrorString
0x180042751  lea     rcx, [rdi+204h]
0x180042758  lea     r9, [rbp+800h+var_880]
0x18004275c  test    rcx, rcx
0x18004275f  cmovnz  r9, rcx
0x180042763  lea     rax, [rbp+800h+var_870]
0x180042767  mov     [rsp+900h+var_8D8], rax
0x18004276c  mov     [rsp+900h+var_8E0], r13
0x180042771  lea     r8, [rbp+800h+var_840]
0x180042775  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18004277c  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180042783  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004278a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004278f  mov     ebx, [rsp+900h+var_8C0]
0x180042793  lea     rcx, [rsp+900h+var_8B8]; this
0x180042798  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18004279d  mov     eax, ebx
0x18004279f  mov     rcx, [rbp+800h+var_40]
0x1800427a6  xor     rcx, rsp; StackCookie
0x1800427a9  call    __security_check_cookie
0x1800427ae  mov     rbx, [rsp+900h+arg_10]
0x1800427b6  add     rsp, 8D0h
0x1800427bd  pop     r15
0x1800427bf  pop     r14
0x1800427c1  pop     r13
0x1800427c3  pop     r12
0x1800427c5  pop     rdi
0x1800427c6  pop     rsi
0x1800427c7  pop     rbp
0x1800427c8  retn
```
