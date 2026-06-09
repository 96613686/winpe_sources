# CDimFullRouterInterface::PlumbIkev2PskPolicy(bool)

- ea: `0x180002ddc`
- end: `0x180003224`
- name: `?PlumbIkev2PskPolicy@CDimFullRouterInterface@@QEAAK_N@Z`
- size: `1096`
- prototype: `unsigned int __fastcall(CDimFullRouterInterface *__hidden this, bool)`
- caller_count: `7`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002598`
- `0x1800033c8`
- `0x180003800`
- `0x1800042a8`
- `0x18001baa0`
- `0x180027f74`
- `0x180028cb4`

## callees

- `0x180002ddc`
- `0x18000df70`
- `0x18001c28c`
- `0x180035d10`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `MPRDDM!DdmDeleteIkev2PskPolicy` at `0x1800030a1`
- `MPRDDM!DdmDeleteIkev2PskPolicy` at `0x1800030a1`
- `MPRDDM!DdmPlumbIkev2PskPolicy` at `0x180003169`
- `MPRDDM!DdmPlumbIkev2PskPolicy` at `0x180003169`

## string_xrefs

- `0x180002f37`: `PlumbIkev2PskPolicy: GetRoutingDomainConfiguration failed: %d`
- `0x1800030c7`: `PlumbIkev2PskPolicy: DdmDeleteIkev2PskPolicy failed Error: %d`

## pseudocode

```c
__int64 __fastcall CDimFullRouterInterface::PlumbIkev2PskPolicy(struct _GUID *this, char a2)
{
  void (__fastcall **v4)(struct _GUID *); // rax
  unsigned int v5; // ebx
  __int64 *v6; // r14
  __int64 v7; // rax
  unsigned int RoutingDomainConfiguration; // eax
  __int64 v9; // rax
  __int128 *v10; // r9
  __int64 v11; // rax
  __int128 *v12; // r9
  const wchar_t *v13; // r8
  __int64 v14; // rax
  __int128 *v15; // r9
  __int64 v16; // rax
  __int64 v17; // rdi
  unsigned int v18; // ebx
  __int64 v19; // rax
  int v21; // [rsp+30h] [rbp-D0h]
  _BYTE v22[56]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+78h] [rbp-88h]
  __int64 v24[14]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v25; // [rsp+120h] [rbp+20h] BYREF
  int v26; // [rsp+130h] [rbp+30h] BYREF
  __int128 v27; // [rsp+134h] [rbp+34h]
  __int128 v28; // [rsp+144h] [rbp+44h]
  int v29; // [rsp+154h] [rbp+54h]
  int v30; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v31[2044]; // [rsp+164h] [rbp+64h] BYREF

  v21 = 0;
  memset_0(v22, 0, 0x68u);
  memset_0(v24, 0, 0x68u);
  v30 = 0;
  v25 = 0;
  memset_0(v31, 0, sizeof(v31));
  v26 = 0;
  v29 = 0;
  v4 = *(void (__fastcall ***)(struct _GUID *))&this->Data1;
  v27 = 0;
  v28 = 0;
  (*v4)(this);
  if ( !a2 )
  {
    v5 = 0;
    if ( ((*(__int64 (__fastcall **)(struct _GUID *))(*(_QWORD *)&this->Data1 + 120LL))(this) & 0x10000000) == 0
      || ((*(__int64 (__fastcall **)(struct _GUID *))(*(_QWORD *)&this->Data1 + 104LL))(this) & 4) == 0 )
    {
      goto LABEL_48;
    }
  }
  v6 = 0;
  if ( a2 )
    goto LABEL_22;
  CDimFullRouterInterface::GetIKEV2TunnelConfigParams(
    (CDimFullRouterInterface *)this,
    (struct _IKEV2_TUNNEL_CONFIG_PARAMS_4 *)v22);
  if ( !v23 )
  {
    v7 = *(_QWORD *)&this[194].Data1 - *(_QWORD *)&GUID_NULL.Data1;
    if ( !v7 )
      v7 = *(_QWORD *)this[194].Data4 - *(_QWORD *)GUID_NULL.Data4;
    if ( v7 )
    {
      v21 = 104;
      RoutingDomainConfiguration = GetRoutingDomainConfiguration(this + 194, (__int64)v24);
      v5 = RoutingDomainConfiguration;
      if ( RoutingDomainConfiguration )
      {
        if ( RoutingDomainConfiguration != 1168 )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
          {
            LOWORD(v30) = 0;
            LOWORD(v26) = 0;
            FormatRRASErrorString(
              &v30,
              L"PlumbIkev2PskPolicy: GetRoutingDomainConfiguration failed: %d",
              RoutingDomainConfiguration);
            if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
            {
              v9 = (*(__int64 (__fastcall **)(struct _GUID *))(*(_QWORD *)&this->Data1 + 280LL))(this);
              v10 = &v25;
              if ( this != (struct _GUID *)-3104LL )
                LODWORD(v10) = (_DWORD)this + 3104;
LABEL_47:
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasDimParamTraceError,
                (unsigned int)&v30,
                (_DWORD)v10,
                v9,
                (__int64)&v26);
              goto LABEL_48;
            }
          }
          goto LABEL_48;
        }
        if ( (Microsoft_Windows_RRASEnableBits & 2) != 0 )
        {
          LOWORD(v26) = 0;
          v11 = (*(__int64 (__fastcall **)(struct _GUID *))(*(_QWORD *)&this->Data1 + 280LL))(this);
          v12 = &v25;
          if ( this != (struct _GUID *)-3104LL )
            LODWORD(v12) = (_DWORD)this + 3104;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceAdminInfo,
            (unsigned int)L"PlumbIkev2PskPolicy: Custom IKEv2 policy is not available. Default policy would be used.",
            (_DWORD)v12,
            v11,
            (__int64)&v26);
        }
      }
      else
      {
        v6 = v24;
        if ( v24[7] )
          goto LABEL_22;
      }
    }
  }
  v6 = (__int64 *)v22;
LABEL_22:
  if ( (Microsoft_Windows_RRASEnableBits & 2) != 0 )
  {
    v13 = L"Removing";
    LOWORD(v30) = 0;
    LOWORD(v26) = 0;
    if ( !a2 )
      v13 = L"Plumbing";
    FormatRRASErrorString(&v30, L"%s IKEv2 PSK policies", v13);
    if ( (Microsoft_Windows_RRASEnableBits & 2) != 0 )
    {
      v14 = (*(__int64 (__fastcall **)(struct _GUID *))(*(_QWORD *)&this->Data1 + 280LL))(this);
      v15 = &v25;
      if ( this != (struct _GUID *)-3104LL )
        LODWORD(v15) = (_DWORD)this + 3104;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDimParamTraceAdminInfo,
        (unsigned int)&v30,
        (_DWORD)v15,
        v14,
        (__int64)&v26);
    }
  }
  if ( a2 )
  {
    if ( (gbldwDIMComponentsLoaded & 4) != 0 )
    {
      v16 = (*(__int64 (__fastcall **)(struct _GUID *))(*(_QWORD *)&this->Data1 + 16LL))(this);
      v5 = DdmDeleteIkev2PskPolicy(v16);
      if ( !v5 )
        goto LABEL_48;
    }
    else
    {
      v5 = 903;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
    {
      LOWORD(v30) = 0;
      LOWORD(v26) = 0;
      FormatRRASErrorString(&v30, L"PlumbIkev2PskPolicy: DdmDeleteIkev2PskPolicy failed Error: %d", v5);
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        v9 = (*(__int64 (__fastcall **)(struct _GUID *))(*(_QWORD *)&this->Data1 + 280LL))(this);
        v10 = &v25;
        if ( this != (struct _GUID *)-3104LL )
          LODWORD(v10) = (_DWORD)this + 3104;
        goto LABEL_47;
      }
    }
  }
  else
  {
    if ( (gbldwDIMComponentsLoaded & 4) != 0 )
    {
      v17 = *(_QWORD *)&this[199].Data1;
      v18 = (*(__int64 (__fastcall **)(struct _GUID *))(*(_QWORD *)&this->Data1 + 344LL))(this);
      v19 = (*(__int64 (__fastcall **)(struct _GUID *))(*(_QWORD *)&this->Data1 + 16LL))(this);
      v5 = DdmPlumbIkev2PskPolicy(v19, &this[52], &this[126].Data4[4], v18, v17, v6, v21);
      if ( !v5 )
        goto LABEL_48;
    }
    else
    {
      v5 = 903;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
    {
      LOWORD(v30) = 0;
      LOWORD(v26) = 0;
      FormatRRASErrorString(&v30, L"PlumbIkev2PskPolicy: DdmPlumbIkev2PskPolicy failed Error: %d", v5);
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        v9 = (*(__int64 (__fastcall **)(struct _GUID *))(*(_QWORD *)&this->Data1 + 280LL))(this);
        v10 = &v25;
        if ( this != (struct _GUID *)-3104LL )
          LODWORD(v10) = (_DWORD)this + 3104;
        goto LABEL_47;
      }
    }
  }
LABEL_48:
  (*(void (__fastcall **)(struct _GUID *))(*(_QWORD *)&this->Data1 + 8LL))(this);
  return v5;
}

```

## disassembly

```asm
0x180002ddc  push    rbp
0x180002dde  push    rbx
0x180002ddf  push    rsi
0x180002de0  push    rdi
0x180002de1  push    r14
0x180002de3  push    r15
0x180002de5  lea     rbp, [rsp-878h]
0x180002ded  sub     rsp, 978h
0x180002df4  mov     rax, cs:__security_cookie
0x180002dfb  xor     rax, rsp
0x180002dfe  mov     [rbp+8A0h+var_40], rax
0x180002e05  mov     r15b, dl
0x180002e08  mov     [rsp+9A0h+var_970], 0
0x180002e10  xor     edx, edx; Val
0x180002e12  mov     rsi, rcx
0x180002e15  lea     rcx, [rsp+9A0h+var_960]; void *
0x180002e1a  lea     r8d, [rdx+68h]; Size
0x180002e1e  call    memset_0
0x180002e23  xor     edx, edx; Val
0x180002e25  lea     rcx, [rbp+8A0h+var_8F0]; void *
0x180002e29  lea     r8d, [rdx+68h]; Size
0x180002e2d  call    memset_0
0x180002e32  xorps   xmm0, xmm0
0x180002e35  lea     rcx, [rbp+8A0h+var_83C]; void *
0x180002e39  xor     eax, eax
0x180002e3b  xor     edx, edx; Val
0x180002e3d  mov     r8d, 7FCh; Size
0x180002e43  mov     [rbp+8A0h+var_840], eax
0x180002e46  movups  [rbp+8A0h+var_880], xmm0
0x180002e4a  call    memset_0
0x180002e4f  xor     eax, eax
0x180002e51  xorps   xmm0, xmm0
0x180002e54  mov     [rbp+8A0h+var_870], eax
0x180002e57  mov     rcx, rsi
0x180002e5a  mov     [rbp+8A0h+var_84C], eax
0x180002e5d  mov     rax, [rsi]
0x180002e60  movups  [rbp+8A0h+var_86C], xmm0
0x180002e64  movups  [rbp+8A0h+var_85C], xmm0
0x180002e68  mov     rax, [rax]
0x180002e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e70  test    r15b, r15b
0x180002e73  jnz     short loc_180002EA7
0x180002e75  mov     rax, [rsi]
0x180002e78  mov     rcx, rsi
0x180002e7b  xor     ebx, ebx
0x180002e7d  mov     rax, [rax+78h]
0x180002e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e86  bt      eax, 1Ch
0x180002e8a  jnb     loc_1800031F4
0x180002e90  mov     rax, [rsi]
0x180002e93  mov     rcx, rsi
0x180002e96  mov     rax, [rax+68h]
0x180002e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e9f  test    al, 4
0x180002ea1  jz      loc_1800031F4
0x180002ea7  xor     r14d, r14d
0x180002eaa  test    r15b, r15b
0x180002ead  jnz     loc_180002FEF
0x180002eb3  lea     rdx, [rsp+9A0h+var_960]; struct _IKEV2_TUNNEL_CONFIG_PARAMS_4 *
0x180002eb8  mov     rcx, rsi; this
0x180002ebb  call    ?GetIKEV2TunnelConfigParams@CDimFullRouterInterface@@QEAAXPEAU_IKEV2_TUNNEL_CONFIG_PARAMS_4@@@Z; CDimFullRouterInterface::GetIKEV2TunnelConfigParams(_IKEV2_TUNNEL_CONFIG_PARAMS_4 *)
0x180002ec0  cmp     [rsp+9A0h+var_928], r14
0x180002ec5  jnz     loc_180002FEA
0x180002ecb  lea     rdi, [rsi+0C20h]
0x180002ed2  mov     rax, [rdi]
0x180002ed5  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180002edc  jnz     short loc_180002EE9
0x180002ede  mov     rax, [rdi+8]
0x180002ee2  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180002ee9  test    rax, rax
0x180002eec  jz      loc_180002FEA
0x180002ef2  xor     r8d, r8d
0x180002ef5  mov     [rsp+9A0h+var_970], 68h ; 'h'
0x180002efd  lea     rax, [rbp+8A0h+var_8F0]
0x180002f01  mov     rcx, rdi; struct _GUID *
0x180002f04  lea     r9, [rsp+9A0h+var_970]
0x180002f09  mov     [rsp+9A0h+var_980], rax; __int64
0x180002f0e  lea     edx, [r8+8]
0x180002f12  call    GetRoutingDomainConfiguration
0x180002f17  mov     ebx, eax
0x180002f19  test    eax, eax
0x180002f1b  jz      loc_180002FE0
0x180002f21  cmp     eax, 490h
0x180002f26  jz      short loc_180002F8A
0x180002f28  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180002f2f  jz      loc_1800031F4
0x180002f35  xor     ecx, ecx
0x180002f37  lea     rdx, aPlumbikev2pskp; "PlumbIkev2PskPolicy: GetRoutingDomainCo"...
0x180002f3e  mov     word ptr [rbp+8A0h+var_840], cx
0x180002f42  mov     r8d, eax
0x180002f45  mov     word ptr [rbp+8A0h+var_870], cx
0x180002f49  lea     rcx, [rbp+8A0h+var_840]
0x180002f4d  call    FormatRRASErrorString
0x180002f52  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180002f59  jz      loc_1800031F4
0x180002f5f  mov     rax, [rsi]
0x180002f62  mov     rcx, rsi
0x180002f65  mov     rax, [rax+118h]
0x180002f6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f71  test    rdi, rdi
0x180002f74  lea     r9, [rbp+8A0h+var_880]
0x180002f78  cmovnz  r9, rdi
0x180002f7c  lea     rcx, [rbp+8A0h+var_870]
0x180002f80  mov     [rsp+9A0h+var_978], rcx
0x180002f85  jmp     loc_1800031D8
0x180002f8a  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 2
0x180002f91  jz      short loc_180002FEA
0x180002f93  xor     eax, eax
0x180002f95  mov     rcx, rsi
0x180002f98  mov     word ptr [rbp+8A0h+var_870], ax
0x180002f9c  mov     rax, [rsi]
0x180002f9f  mov     rax, [rax+118h]
0x180002fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fab  test    rdi, rdi
0x180002fae  lea     rcx, [rbp+8A0h+var_870]
0x180002fb2  mov     [rsp+9A0h+var_978], rcx
0x180002fb7  lea     r9, [rbp+8A0h+var_880]
0x180002fbb  cmovnz  r9, rdi
0x180002fbf  mov     [rsp+9A0h+var_980], rax
0x180002fc4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180002fcb  lea     r8, aPlumbikev2pskp_2; "PlumbIkev2PskPolicy: Custom IKEv2 polic"...
0x180002fd2  lea     rdx, RasDimParamTraceAdminInfo
0x180002fd9  call    McTemplateU0zjzz_EventWriteTransfer
0x180002fde  jmp     short loc_180002FEA
0x180002fe0  cmp     [rbp+8A0h+var_8B8], r14
0x180002fe4  lea     r14, [rbp+8A0h+var_8F0]
0x180002fe8  jnz     short loc_180002FEF
0x180002fea  lea     r14, [rsp+9A0h+var_960]
0x180002fef  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 2
0x180002ff6  jz      loc_18000307D
0x180002ffc  xor     eax, eax
0x180002ffe  lea     r8, aRemoving; "Removing"
0x180003005  mov     word ptr [rbp+8A0h+var_840], ax
0x180003009  lea     rdx, aSIkev2PskPolic; "%s IKEv2 PSK policies"
0x180003010  mov     word ptr [rbp+8A0h+var_870], ax
0x180003014  lea     rcx, [rbp+8A0h+var_840]
0x180003018  lea     rax, aPlumbing; "Plumbing"
0x18000301f  test    r15b, r15b
0x180003022  cmovz   r8, rax
0x180003026  call    FormatRRASErrorString
0x18000302b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 2
0x180003032  jz      short loc_18000307D
0x180003034  mov     rax, [rsi]
0x180003037  mov     rcx, rsi
0x18000303a  mov     rax, [rax+118h]
0x180003041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003046  lea     rcx, [rsi+0C20h]
0x18000304d  test    rcx, rcx
0x180003050  lea     r9, [rbp+8A0h+var_880]
0x180003054  lea     r8, [rbp+8A0h+var_840]
0x180003058  cmovnz  r9, rcx
0x18000305c  lea     rdx, RasDimParamTraceAdminInfo
0x180003063  lea     rcx, [rbp+8A0h+var_870]
0x180003067  mov     [rsp+9A0h+var_978], rcx
0x18000306c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003073  mov     [rsp+9A0h+var_980], rax
0x180003078  call    McTemplateU0zjzz_EventWriteTransfer
0x18000307d  test    r15b, r15b
0x180003080  jz      loc_180003118
0x180003086  test    byte ptr cs:?gbldwDIMComponentsLoaded@@3KA, 4; ulong gbldwDIMComponentsLoaded
0x18000308d  jz      short loc_1800030B3
0x18000308f  mov     rax, [rsi]
0x180003092  mov     rcx, rsi
0x180003095  mov     rax, [rax+10h]
0x180003099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000309e  mov     rcx, rax
0x1800030a1  call    cs:__imp_DdmDeleteIkev2PskPolicy
0x1800030a7  mov     ebx, eax
0x1800030a9  test    eax, eax
0x1800030ab  jz      loc_1800031F4
0x1800030b1  jmp     short loc_1800030B8
0x1800030b3  mov     ebx, 387h
0x1800030b8  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x1800030bf  jz      loc_1800031F4
0x1800030c5  xor     eax, eax
0x1800030c7  lea     rdx, aPlumbikev2pskp_3; "PlumbIkev2PskPolicy: DdmDeleteIkev2PskP"...
0x1800030ce  mov     r8d, ebx
0x1800030d1  mov     word ptr [rbp+8A0h+var_840], ax
0x1800030d5  lea     rcx, [rbp+8A0h+var_840]
0x1800030d9  mov     word ptr [rbp+8A0h+var_870], ax
0x1800030dd  call    FormatRRASErrorString
0x1800030e2  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x1800030e9  jz      loc_1800031F4
0x1800030ef  mov     rax, [rsi]
0x1800030f2  mov     rcx, rsi
0x1800030f5  mov     rax, [rax+118h]
0x1800030fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003101  lea     rcx, [rsi+0C20h]
0x180003108  test    rcx, rcx
0x18000310b  lea     r9, [rbp+8A0h+var_880]
0x18000310f  cmovnz  r9, rcx
0x180003113  jmp     loc_180002F7C
0x180003118  test    byte ptr cs:?gbldwDIMComponentsLoaded@@3KA, 4; ulong gbldwDIMComponentsLoaded
0x18000311f  jz      short loc_180003177
0x180003121  mov     rax, [rsi]
0x180003124  mov     rcx, rsi
0x180003127  mov     rdi, [rsi+0C70h]
0x18000312e  mov     rax, [rax+158h]
0x180003135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000313a  mov     rcx, [rsi]
0x18000313d  mov     ebx, eax
0x18000313f  mov     rax, [rcx+10h]
0x180003143  mov     rcx, rsi
0x180003146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000314b  lea     r8, [rsi+7ECh]
0x180003152  mov     [rsp+9A0h+var_978], r14
0x180003157  lea     rdx, [rsi+340h]
0x18000315e  mov     [rsp+9A0h+var_980], rdi
0x180003163  mov     r9d, ebx
0x180003166  mov     rcx, rax
0x180003169  call    cs:__imp_DdmPlumbIkev2PskPolicy
0x18000316f  mov     ebx, eax
0x180003171  test    eax, eax
0x180003173  jz      short loc_1800031F4
0x180003175  jmp     short loc_18000317C
0x180003177  mov     ebx, 387h
0x18000317c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180003183  jz      short loc_1800031F4
0x180003185  xor     eax, eax
0x180003187  lea     rdx, aPlumbikev2pskp_1; "PlumbIkev2PskPolicy: DdmPlumbIkev2PskPo"...
0x18000318e  mov     r8d, ebx
0x180003191  mov     word ptr [rbp+8A0h+var_840], ax
0x180003195  lea     rcx, [rbp+8A0h+var_840]
0x180003199  mov     word ptr [rbp+8A0h+var_870], ax
0x18000319d  call    FormatRRASErrorString
0x1800031a2  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x1800031a9  jz      short loc_1800031F4
0x1800031ab  mov     rax, [rsi]
0x1800031ae  mov     rcx, rsi
0x1800031b1  mov     rax, [rax+118h]
0x1800031b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031bd  lea     rcx, [rsi+0C20h]
0x1800031c4  test    rcx, rcx
0x1800031c7  lea     r9, [rbp+8A0h+var_880]
0x1800031cb  lea     rdx, [rbp+8A0h+var_870]
0x1800031cf  cmovnz  r9, rcx
0x1800031d3  mov     [rsp+9A0h+var_978], rdx
0x1800031d8  lea     r8, [rbp+8A0h+var_840]
0x1800031dc  mov     [rsp+9A0h+var_980], rax
0x1800031e1  lea     rdx, RasDimParamTraceError
0x1800031e8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800031ef  call    McTemplateU0zjzz_EventWriteTransfer
0x1800031f4  mov     rax, [rsi]
0x1800031f7  mov     rcx, rsi
0x1800031fa  mov     rax, [rax+8]
0x1800031fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003203  mov     eax, ebx
0x180003205  mov     rcx, [rbp+8A0h+var_40]
0x18000320c  xor     rcx, rsp; StackCookie
0x18000320f  call    __security_check_cookie
0x180003214  add     rsp, 978h
0x18000321b  pop     r15
0x18000321d  pop     r14
0x18000321f  pop     rdi
0x180003220  pop     rsi
0x180003221  pop     rbx
0x180003222  pop     rbp
0x180003223  retn
```
