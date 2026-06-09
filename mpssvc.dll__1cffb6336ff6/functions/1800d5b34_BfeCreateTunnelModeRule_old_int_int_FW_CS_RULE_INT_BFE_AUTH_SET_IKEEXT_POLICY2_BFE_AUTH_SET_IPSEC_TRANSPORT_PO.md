# BfeCreateTunnelModeRule_old(int,int,_FW_CS_RULE_INT_ *,_BFE_AUTH_SET_ *,IKEEXT_POLICY2_ *,_BFE_AUTH_SET_ *,IPSEC_TRANSPORT_POLICY2_ *,_GUID *,_GUID *)

- ea: `0x1800d5b34`
- end: `0x1800d6169`
- name: `?BfeCreateTunnelModeRule_old@@YAKHHPEAU_FW_CS_RULE_INT_@@PEAU_BFE_AUTH_SET_@@PEAUIKEEXT_POLICY2_@@1PEAUIPSEC_TRANSPORT_POLICY2_@@PEAU_GUID@@4@Z`
- size: `1589`
- prototype: `unsigned int __fastcall(int, __int64, struct _FW_CS_RULE_INT_ *, struct _BFE_AUTH_SET_ *, struct IKEEXT_POLICY2_ *, struct _BFE_AUTH_SET_ *, struct IPSEC_TRANSPORT_POLICY2_ *, struct _GUID *Uuid, struct _GUID *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d4e10`

## callees

- `0x1800093b0`
- `0x18004c284`
- `0x18006b2b8`
- `0x18006f520`
- `0x18006ffc8`
- `0x1800d3ba8`
- `0x1800d516c`
- `0x1800d5b34`
- `0x1800d6170`
- `0x1800d6188`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800d5c99`
- `RPCRT4!UuidCreate` at `0x1800d5c99`
- `fwbase!FwSizeTAdd` at `0x1800d5eff`
- `fwbase!FwSizeTAdd` at `0x1800d5eff`
- `fwbase!FwAllocArray` at `0x1800d5f27`
- `fwbase!FwAllocArray` at `0x1800d5f27`
- `fwbase!FwReportReturnError` at `0x1800d5f12`
- `fwbase!FwReportReturnError` at `0x1800d5f12`
- `fwbase!FwFree` at `0x1800d60e6`
- `fwbase!FwFree` at `0x1800d6109`
- `fwbase!FwFree` at `0x1800d6118`
- `fwbase!FwFree` at `0x1800d60e6`
- `fwbase!FwFree` at `0x1800d6109`
- `fwbase!FwFree` at `0x1800d6118`

## string_xrefs

- `0x1800d5c67`: `BfeCreateTunnelModeRule_old`
- `0x1800d5f0b`: `BfeCreateTunnelModeRule_old`
- `0x1800d60d1`: `BfeCreateTunnelModeRule_old`
- `0x1800d6129`: `BfeCreateTunnelModeRule_old`

## pseudocode

```c
unsigned int __fastcall BfeCreateTunnelModeRule_old(
        int a1,
        __int64 a2,
        struct _FW_CS_RULE_INT_ *a3,
        struct _BFE_AUTH_SET_ *a4,
        struct IKEEXT_POLICY2_ *a5,
        struct _BFE_AUTH_SET_ *a6,
        struct IPSEC_TRANSPORT_POLICY2_ *a7,
        struct _GUID *Uuid,
        struct _GUID *a9)
{
  int v12; // eax
  int v13; // edx
  unsigned int v14; // ebx
  int v15; // r14d
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  RPC_STATUS v18; // eax
  unsigned int v19; // edx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rax
  __int64 v25; // rcx
  const wchar_t *v26; // rdx
  __int64 v27; // xmm0_8
  const wchar_t *v28; // rax
  unsigned int v29; // eax
  unsigned int v30; // edx
  bool v31; // zf
  unsigned int v32; // esi
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  unsigned __int64 v36; // xmm6_8
  unsigned __int64 v37; // rax
  unsigned __int64 v38; // rax
  _DWORD *v39; // rax
  int v40; // eax
  __int64 v41; // r8
  unsigned int v42; // r8d
  unsigned int i; // r9d
  __int64 v44; // rdx
  __int64 v45; // r8
  unsigned int v46; // r10d
  __int64 v47; // rax
  __int64 v48; // rdx
  __int64 v49; // r8
  int v50; // ecx
  int v51; // eax
  struct FWP_CONDITION_VALUE0_ *v52; // r9
  struct FWP_CONDITION_VALUE0_ *v53; // r8
  int v55; // [rsp+48h] [rbp-C0h]
  struct FWP_CONDITION_VALUE0_ v56; // [rsp+58h] [rbp-B0h] BYREF
  struct FWP_CONDITION_VALUE0_ v57; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v58; // [rsp+78h] [rbp-90h] BYREF
  _DWORD v59[2]; // [rsp+88h] [rbp-80h] BYREF
  __int64 v60; // [rsp+90h] [rbp-78h]
  int v61; // [rsp+98h] [rbp-70h]
  int v62; // [rsp+9Ch] [rbp-6Ch]
  __int64 v63; // [rsp+A0h] [rbp-68h]
  int v64; // [rsp+A8h] [rbp-60h]
  int v65; // [rsp+ACh] [rbp-5Ch]
  __int64 v66; // [rsp+B0h] [rbp-58h]
  int v67; // [rsp+B8h] [rbp-50h]
  __int64 v68; // [rsp+C0h] [rbp-48h]
  __int64 v69; // [rsp+C8h] [rbp-40h]
  int v70; // [rsp+D0h] [rbp-38h]
  __int64 v71; // [rsp+D8h] [rbp-30h]
  __int64 v72; // [rsp+E0h] [rbp-28h]
  struct IKEEXT_AUTHENTICATION_METHOD2_ **v73; // [rsp+E8h] [rbp-20h]
  int v74; // [rsp+F0h] [rbp-18h]
  struct IKEEXT_AUTHENTICATION_METHOD2_ *v75[2]; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v76; // [rsp+108h] [rbp+0h]
  struct IKEEXT_AUTHENTICATION_METHOD2_ *v77[2]; // [rsp+110h] [rbp+8h] BYREF
  __int128 v78; // [rsp+120h] [rbp+18h]
  __int128 v79; // [rsp+130h] [rbp+28h]
  unsigned int Data1; // [rsp+148h] [rbp+40h] BYREF
  __int64 v81; // [rsp+14Ch] [rbp+44h] BYREF
  int v82; // [rsp+154h] [rbp+4Ch]
  const wchar_t *v83; // [rsp+158h] [rbp+50h]
  const wchar_t *v84; // [rsp+160h] [rbp+58h]
  int v85; // [rsp+188h] [rbp+80h]
  struct IKEEXT_AUTHENTICATION_METHOD2_ **v86; // [rsp+190h] [rbp+88h]
  UUID v87[4]; // [rsp+1A8h] [rbp+A0h] BYREF
  int v88; // [rsp+1E8h] [rbp+E0h]
  _DWORD *v89; // [rsp+1F0h] [rbp+E8h]

  *(_OWORD *)v77 = 0;
  v78 = 0;
  v79 = 0;
  memset_0(v59, 0, 0x70u);
  Data1 = 0;
  memset_0(&v81, 0, 0x54u);
  v87[0].Data1 = 0;
  memset_0(&v87[0].Data2, 0, 0x54u);
  v58 = 0;
  v76 = 0;
  v55 = *((_DWORD *)a3 + 15);
  v12 = *((_DWORD *)a3 + 43);
  *(_OWORD *)v75 = 0;
  v56 = 0;
  v57 = 0;
  if ( *((_DWORD *)a3 + 38) == v12 )
  {
    v13 = v59[0];
    v14 = 0;
    v15 = 0;
    goto LABEL_33;
  }
  v16 = *((_OWORD *)a5 + 1);
  *(_OWORD *)v77 = *(_OWORD *)a5;
  v17 = *((_OWORD *)a5 + 2);
  v78 = v16;
  v79 = v17;
  v18 = BfeConvertAuthMethodsV0ToV2(a4, &v77[1]);
  v14 = v18;
  if ( v18 )
  {
    v19 = 1043;
LABEL_5:
    IpsTraceError("BfeCreateTunnelModeRule_old", v19, v18, 0);
    goto LABEL_85;
  }
  HIDWORD(v77[0]) = *((_DWORD *)a4 + 2);
  if ( a1 )
    LODWORD(v78) = *((_DWORD *)a4 + 3) != 0;
  v18 = UuidCreate(Uuid);
  v14 = v18;
  if ( v18 )
  {
    v19 = 1056;
    goto LABEL_5;
  }
  v85 = 6;
  v86 = v77;
  v15 = 1;
  if ( !a1 )
    v85 = 5;
  v24 = *(_QWORD *)&GUID_NULL.Data1 - *(_QWORD *)&Uuid->Data1;
  if ( *(_QWORD *)&GUID_NULL.Data1 == *(_QWORD *)&Uuid->Data1 )
    v24 = *(_QWORD *)GUID_NULL.Data4 - *(_QWORD *)Uuid->Data4;
  if ( !v24 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v21, v20, v22, v23);
  v25 = *(_QWORD *)a3;
  v26 = L" ";
  v27 = *(_QWORD *)&Uuid->Data2;
  Data1 = Uuid->Data1;
  v82 = *(_DWORD *)&Uuid->Data4[4];
  v28 = L" ";
  v81 = v27;
  if ( *(_QWORD *)(v25 + 24) )
    v28 = *(const wchar_t **)(v25 + 24);
  v83 = v28;
  if ( *(_QWORD *)(v25 + 32) )
    v26 = *(const wchar_t **)(v25 + 32);
  v59[1] = *(_DWORD *)a7;
  v60 = *((_QWORD *)a7 + 1);
  v72 = *((_QWORD *)a7 + 3);
  v84 = v26;
  v13 = v59[0];
  if ( (_DWORD)xmmword_18012C890 == 1 )
  {
    v13 = v59[0] | 0x10;
LABEL_24:
    v59[0] = v13;
    goto LABEL_25;
  }
  if ( (_DWORD)xmmword_18012C890 == 2 )
  {
    v13 = v59[0] | 0x20;
    goto LABEL_24;
  }
LABEL_25:
  if ( a1 )
  {
    if ( a6 )
    {
      v29 = BfeConvertAuthMethodsV0ToV2(a6, &v75[1]);
      v14 = v29;
      if ( v29 )
      {
        v30 = 1100;
LABEL_83:
        v42 = v29;
        goto LABEL_84;
      }
      v31 = *((_DWORD *)a6 + 3) == 0;
      v13 = v59[0];
      LODWORD(v75[0]) = *((_DWORD *)a6 + 2);
      LODWORD(v76) = !v31;
      v73 = v75;
    }
    v88 = 4;
  }
  else
  {
    v88 = 2;
  }
  v89 = v59;
LABEL_33:
  v32 = 0;
  if ( v55 == 1 )
  {
    if ( v15 == 1 )
    {
      v33 = *(_QWORD *)a3;
      v61 = 0;
      v62 = *(_DWORD *)(v33 + 212);
      v65 = *(_DWORD *)(v33 + 232);
      v68 = *((_QWORD *)a3 + 18);
    }
    v34 = *(_QWORD *)a3;
    if ( !*(_DWORD *)(*(_QWORD *)a3 + 212LL) && !*(_DWORD *)(v34 + 232) )
      v32 = 1;
  }
  else
  {
    if ( v15 == 1 )
    {
      v35 = *(_QWORD *)a3;
      v61 = 1;
      v62 = *(_DWORD *)(v35 + 216);
      v63 = *(_QWORD *)(v35 + 220);
      v64 = *(_DWORD *)(v35 + 228);
      v65 = *(_DWORD *)(v35 + 236);
      v66 = *(_QWORD *)(v35 + 240);
      v67 = *(_DWORD *)(v35 + 248);
      v68 = *((_QWORD *)a3 + 18);
    }
    v34 = *(_QWORD *)a3;
    v36 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    v37 = *(_QWORD *)(*(_QWORD *)a3 + 216LL);
    if ( !v37 )
      v37 = *(_QWORD *)(v34 + 224) - v36;
    if ( !v37 )
    {
      v38 = *(_QWORD *)(v34 + 236);
      if ( !v38 )
        v38 = *(_QWORD *)(v34 + 244) - v36;
      if ( !v38 )
        v32 = 1;
    }
  }
  v69 = *(_QWORD *)(v34 + 416);
  v39 = (_DWORD *)(v34 + 480);
  if ( *(_DWORD *)(v34 + 448) || *v39 )
  {
    v40 = FwSizeTAdd(*(unsigned int *)(v34 + 448), (unsigned int)*v39, &v58);
    if ( v40 < 0 )
    {
      FwReportReturnError("BfeCreateTunnelModeRule_old", (unsigned int)v40, v41);
      goto LABEL_85;
    }
    v71 = FwAllocArray(v58, 20);
    if ( !v71 )
    {
      v14 = 14;
      v30 = 1207;
      v42 = 14;
LABEL_84:
      IpsTraceError("BfeCreateTunnelModeRule_old", v30, v42, 0);
      goto LABEL_85;
    }
    v34 = *(_QWORD *)a3;
    for ( i = 0; i < *(_DWORD *)(*(_QWORD *)a3 + 448LL); v34 = *(_QWORD *)a3 )
    {
      v44 = i++;
      v45 = 5 * v44;
      *(_DWORD *)(v71 + 4 * v45) = 0;
      *(_DWORD *)(v71 + 4 * v45 + 4) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a3 + 456LL) + 8 * v44);
    }
    v46 = 0;
    if ( *(_DWORD *)(v34 + 480) )
    {
      do
      {
        v47 = i++;
        v48 = v46++;
        v49 = 5 * v47;
        *(_DWORD *)(v71 + 4 * v49) = 1;
        *(_OWORD *)(v71 + 4 * v49 + 4) = *(_OWORD *)(32 * v48 + *(_QWORD *)(*(_QWORD *)a3 + 488LL));
        v34 = *(_QWORD *)a3;
      }
      while ( v46 < *(_DWORD *)(*(_QWORD *)a3 + 480LL) );
    }
    v13 = v59[0];
    v70 = v58;
  }
  if ( (*(_BYTE *)(v34 + 340) & 0x10) != 0 )
  {
    v13 |= 0x400u;
    v59[0] = v13;
  }
  if ( (*(_BYTE *)(v34 + 340) & 8) != 0 )
  {
    v13 |= 0x800u;
    v59[0] = v13;
  }
  if ( (*(&gvIpsGlobalConfig + 12) & 2) != 0 )
  {
    v13 |= 0x1000u;
    v59[0] = v13;
  }
  if ( (*(_BYTE *)(v34 + 340) & 0x40) != 0 && a1 )
  {
    v13 |= 0x2000u;
    v59[0] = v13;
  }
  if ( *(char *)(v34 + 340) < 0 )
    v59[0] = v13 | 0x4000;
  v50 = *(_DWORD *)(v34 + 500);
  v51 = v74;
  if ( v50 )
    v51 = v50;
  v74 = v51;
  v29 = BfeIpAddressFill((struct _FW_CS_RULE_INT_ *)((char *)a3 + 56), &v56);
  v14 = v29;
  if ( v29 )
  {
    v30 = 1271;
    goto LABEL_83;
  }
  v29 = BfeIpAddressFill((struct _FW_CS_RULE_INT_ *)((char *)a3 + 96), &v57);
  v14 = v29;
  if ( v29 )
  {
    v30 = 1276;
    goto LABEL_83;
  }
  v52 = &v57;
  v53 = &v56;
  if ( *((_DWORD *)a3 + 24) == 1 )
    v52 = 0;
  if ( *((_DWORD *)a3 + 14) == 1 )
    v53 = 0;
  v29 = BfeCallTunnelFilterAdd_old(a3, v32, (struct FWPM_PROVIDER_CONTEXT2_ *)&Data1, v87, v53, v52, a9);
  v14 = v29;
  if ( v29 )
  {
    v30 = 1286;
    goto LABEL_83;
  }
LABEL_85:
  if ( v71 )
    FwFree(v71);
  BfeIpAddressFree(&v56);
  BfeIpAddressFree(&v57);
  if ( v77[1] )
    FwFree(v77[1]);
  if ( v75[1] )
    FwFree(v75[1]);
  return IpsReturnError("BfeCreateTunnelModeRule_old", 0x515u, v14, 0, 0);
}

```

## disassembly

```asm
0x1800d5b34  mov     rax, rsp
0x1800d5b37  mov     [rax+8], rbx
0x1800d5b3b  push    rbp
0x1800d5b3c  push    rsi
0x1800d5b3d  push    rdi
0x1800d5b3e  push    r12
0x1800d5b40  push    r13
0x1800d5b42  push    r14
0x1800d5b44  push    r15
0x1800d5b46  lea     rbp, [rax-158h]
0x1800d5b4d  sub     rsp, 220h
0x1800d5b54  movaps  xmmword ptr [rax-48h], xmm6
0x1800d5b58  mov     rax, cs:__security_cookie
0x1800d5b5f  xor     rax, rsp
0x1800d5b62  mov     [rbp+150h+var_50], rax
0x1800d5b69  mov     rax, [rbp+150h+arg_40]
0x1800d5b70  xorps   xmm0, xmm0
0x1800d5b73  mov     r12, [rbp+150h+arg_30]
0x1800d5b7a  xor     edx, edx; Val
0x1800d5b7c  mov     rbx, [rbp+150h+arg_20]
0x1800d5b83  mov     rdi, r8
0x1800d5b86  mov     r15, [rbp+150h+arg_28]
0x1800d5b8d  mov     r13d, ecx
0x1800d5b90  mov     rsi, [rbp+150h+Uuid]
0x1800d5b97  lea     rcx, [rbp+150h+var_1D0]; void *
0x1800d5b9b  lea     r8d, [rdx+70h]; Size
0x1800d5b9f  mov     qword ptr [rsp+250h+var_208.type], rax
0x1800d5ba4  mov     r14, r9
0x1800d5ba7  movups  xmmword ptr [rbp+150h+var_148], xmm0
0x1800d5bab  movups  [rbp+150h+var_138], xmm0
0x1800d5baf  movups  [rbp+150h+var_128], xmm0
0x1800d5bb3  call    memset_0
0x1800d5bb8  xor     edx, edx; Val
0x1800d5bba  mov     [rbp+150h+var_110], 0
0x1800d5bc1  lea     rcx, [rbp+150h+var_10C]; void *
0x1800d5bc5  lea     r8d, [rdx+54h]; Size
0x1800d5bc9  call    memset_0
0x1800d5bce  xor     edx, edx; Val
0x1800d5bd0  mov     [rbp+150h+var_B0], 0
0x1800d5bda  lea     rcx, [rbp+150h+var_AC]; void *
0x1800d5be1  lea     r8d, [rdx+54h]; Size
0x1800d5be5  call    memset_0
0x1800d5bea  xor     eax, eax
0x1800d5bec  mov     [rsp+250h+var_1E0], 0
0x1800d5bf5  mov     [rbp+150h+var_150], rax
0x1800d5bf9  xorps   xmm0, xmm0
0x1800d5bfc  mov     eax, [rdi+3Ch]
0x1800d5bff  xorps   xmm1, xmm1
0x1800d5c02  mov     dword ptr [rsp+250h+var_210], eax
0x1800d5c06  xorps   xmm6, xmm6
0x1800d5c09  mov     eax, [rdi+0ACh]
0x1800d5c0f  movups  xmmword ptr [rbp+150h+var_160], xmm0
0x1800d5c13  movups  xmmword ptr [rsp+250h+var_208.8], xmm0
0x1800d5c18  movups  xmmword ptr [rsp+250h+var_1F8+8], xmm1
0x1800d5c1d  cmp     [rdi+98h], eax
0x1800d5c23  jnz     short loc_1800D5C36
0x1800d5c25  mov     edx, [rbp+150h+var_1D0]
0x1800d5c28  xor     r12d, r12d
0x1800d5c2b  mov     ebx, r12d
0x1800d5c2e  mov     r14d, r12d
0x1800d5c31  jmp     loc_1800D5DD5
0x1800d5c36  movups  xmm0, xmmword ptr [rbx]
0x1800d5c39  lea     rdx, [rbp+150h+var_148+8]; struct IKEEXT_AUTHENTICATION_METHOD2_ **
0x1800d5c3d  mov     rcx, r14; struct _BFE_AUTH_SET_ *
0x1800d5c40  movups  xmm1, xmmword ptr [rbx+10h]
0x1800d5c44  movups  xmmword ptr [rbp+150h+var_148], xmm0
0x1800d5c48  movups  xmm0, xmmword ptr [rbx+20h]
0x1800d5c4c  movups  [rbp+150h+var_138], xmm1
0x1800d5c50  movups  [rbp+150h+var_128], xmm0
0x1800d5c54  call    ?BfeConvertAuthMethodsV0ToV2@@YAKPEAU_BFE_AUTH_SET_@@PEAPEAUIKEEXT_AUTHENTICATION_METHOD2_@@@Z; BfeConvertAuthMethodsV0ToV2(_BFE_AUTH_SET_ *,IKEEXT_AUTHENTICATION_METHOD2_ * *)
0x1800d5c59  mov     ebx, eax
0x1800d5c5b  test    eax, eax
0x1800d5c5d  jz      short loc_1800D5C7E
0x1800d5c5f  mov     edx, 413h; unsigned int
0x1800d5c64  mov     r8d, eax; unsigned int
0x1800d5c67  lea     rcx, aBfecreatetunne_0; "BfeCreateTunnelModeRule_old"
0x1800d5c6e  xor     r9d, r9d; int
0x1800d5c71  call    ?IpsTraceError@@YAXPEBDKKH@Z; IpsTraceError(char const *,ulong,ulong,int)
0x1800d5c76  xor     r12d, r12d
0x1800d5c79  jmp     loc_1800D60DD
0x1800d5c7e  mov     eax, [r14+8]
0x1800d5c82  mov     dword ptr [rbp+150h+var_148+4], eax
0x1800d5c85  test    r13d, r13d
0x1800d5c88  jz      short loc_1800D5C96
0x1800d5c8a  xor     eax, eax
0x1800d5c8c  cmp     [r14+0Ch], eax
0x1800d5c90  setnz   al
0x1800d5c93  mov     dword ptr [rbp+150h+var_138], eax
0x1800d5c96  mov     rcx, rsi; Uuid
0x1800d5c99  call    cs:__imp_UuidCreate
0x1800d5c9f  mov     ebx, eax
0x1800d5ca1  test    eax, eax
0x1800d5ca3  jz      short loc_1800D5CAC
0x1800d5ca5  mov     edx, 420h
0x1800d5caa  jmp     short loc_1800D5C64
0x1800d5cac  mov     [rbp+150h+var_D0], 6
0x1800d5cb6  lea     rax, [rbp+150h+var_148]
0x1800d5cba  mov     [rbp+150h+var_C8], rax
0x1800d5cc1  mov     r14d, 1
0x1800d5cc7  test    r13d, r13d
0x1800d5cca  jnz     short loc_1800D5CD6
0x1800d5ccc  mov     [rbp+150h+var_D0], 5
0x1800d5cd6  mov     rax, qword ptr cs:GUID_NULL.Data1
0x1800d5cdd  sub     rax, [rsi]
0x1800d5ce0  jnz     short loc_1800D5CED
0x1800d5ce2  mov     rax, qword ptr cs:GUID_NULL.Data4
0x1800d5ce9  sub     rax, [rsi+8]
0x1800d5ced  test    rax, rax
0x1800d5cf0  jnz     short loc_1800D5CF7
0x1800d5cf2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800d5cf7  mov     rcx, [rdi]
0x1800d5cfa  lea     rdx, asc_18010B39C; " "
0x1800d5d01  mov     eax, [rsi]
0x1800d5d03  movsd   xmm0, qword ptr [rsi+4]
0x1800d5d08  mov     [rbp+150h+var_110], eax
0x1800d5d0b  mov     eax, [rsi+0Ch]
0x1800d5d0e  mov     [rbp+150h+var_104], eax
0x1800d5d11  mov     rax, rdx
0x1800d5d14  movsd   [rbp+150h+var_10C], xmm0
0x1800d5d19  cmp     qword ptr [rcx+18h], 0
0x1800d5d1e  cmovnz  rax, [rcx+18h]
0x1800d5d23  mov     [rbp+150h+var_100], rax
0x1800d5d27  cmp     qword ptr [rcx+20h], 0
0x1800d5d2c  mov     eax, [r12]
0x1800d5d30  cmovnz  rdx, [rcx+20h]
0x1800d5d35  mov     [rbp+150h+var_1CC], eax
0x1800d5d38  mov     rax, [r12+8]
0x1800d5d3d  mov     [rbp+150h+var_1C8], rax
0x1800d5d41  mov     rax, [r12+18h]
0x1800d5d46  mov     [rbp+150h+var_178], rax
0x1800d5d4a  mov     eax, dword ptr cs:xmmword_18012C890
0x1800d5d50  mov     [rbp+150h+var_F8], rdx
0x1800d5d54  mov     edx, [rbp+150h+var_1D0]
0x1800d5d57  cmp     eax, r14d
0x1800d5d5a  jnz     short loc_1800D5D61
0x1800d5d5c  or      edx, 10h
0x1800d5d5f  jmp     short loc_1800D5D69
0x1800d5d61  cmp     eax, 2
0x1800d5d64  jnz     short loc_1800D5D6C
0x1800d5d66  or      edx, 20h
0x1800d5d69  mov     [rbp+150h+var_1D0], edx
0x1800d5d6c  xor     r12d, r12d
0x1800d5d6f  test    r13d, r13d
0x1800d5d72  jz      short loc_1800D5DC0
0x1800d5d74  test    r15, r15
0x1800d5d77  jz      short loc_1800D5DB4
0x1800d5d79  lea     rdx, [rbp+150h+var_160+8]; struct IKEEXT_AUTHENTICATION_METHOD2_ **
0x1800d5d7d  mov     rcx, r15; struct _BFE_AUTH_SET_ *
0x1800d5d80  call    ?BfeConvertAuthMethodsV0ToV2@@YAKPEAU_BFE_AUTH_SET_@@PEAPEAUIKEEXT_AUTHENTICATION_METHOD2_@@@Z; BfeConvertAuthMethodsV0ToV2(_BFE_AUTH_SET_ *,IKEEXT_AUTHENTICATION_METHOD2_ * *)
0x1800d5d85  mov     ebx, eax
0x1800d5d87  test    eax, eax
0x1800d5d89  jz      short loc_1800D5D95
0x1800d5d8b  mov     edx, 44Ch
0x1800d5d90  jmp     loc_1800D60CB
0x1800d5d95  mov     eax, [r15+8]
0x1800d5d99  cmp     [r15+0Ch], r12d
0x1800d5d9d  mov     edx, [rbp+150h+var_1D0]
0x1800d5da0  mov     dword ptr [rbp+150h+var_160], eax
0x1800d5da3  mov     eax, r12d
0x1800d5da6  setnz   al
0x1800d5da9  mov     dword ptr [rbp+150h+var_150], eax
0x1800d5dac  lea     rax, [rbp+150h+var_160]
0x1800d5db0  mov     [rbp+150h+var_170], rax
0x1800d5db4  mov     [rbp+150h+var_70], 4
0x1800d5dbe  jmp     short loc_1800D5DCA
0x1800d5dc0  mov     [rbp+150h+var_70], 2
0x1800d5dca  lea     rax, [rbp+150h+var_1D0]
0x1800d5dce  mov     [rbp+150h+var_68], rax
0x1800d5dd5  mov     r15d, 1
0x1800d5ddb  mov     esi, r12d
0x1800d5dde  cmp     dword ptr [rsp+250h+var_210], r15d
0x1800d5de3  jnz     short loc_1800D5E2E
0x1800d5de5  cmp     r14d, r15d
0x1800d5de8  jnz     short loc_1800D5E0E
0x1800d5dea  mov     rcx, [rdi]
0x1800d5ded  mov     [rbp+150h+var_1C0], r12d
0x1800d5df1  mov     eax, [rcx+0D4h]
0x1800d5df7  mov     [rbp+150h+var_1BC], eax
0x1800d5dfa  mov     eax, [rcx+0E8h]
0x1800d5e00  mov     [rbp+150h+var_1AC], eax
0x1800d5e03  mov     rax, [rdi+90h]
0x1800d5e0a  mov     [rbp+150h+var_198], rax
0x1800d5e0e  mov     rcx, [rdi]
0x1800d5e11  cmp     [rcx+0D4h], r12d
0x1800d5e18  jnz     loc_1800D5ECE
0x1800d5e1e  cmp     [rcx+0E8h], r12d
0x1800d5e25  cmovz   esi, r15d
0x1800d5e29  jmp     loc_1800D5ECE
0x1800d5e2e  cmp     r14d, r15d
0x1800d5e31  jnz     short loc_1800D5E83
0x1800d5e33  mov     rcx, [rdi]
0x1800d5e36  mov     [rbp+150h+var_1C0], r15d
0x1800d5e3a  mov     eax, [rcx+0D8h]
0x1800d5e40  mov     [rbp+150h+var_1BC], eax
0x1800d5e43  movsd   xmm0, qword ptr [rcx+0DCh]
0x1800d5e4b  movsd   [rbp+150h+var_1B8], xmm0
0x1800d5e50  mov     eax, [rcx+0E4h]
0x1800d5e56  mov     [rbp+150h+var_1B0], eax
0x1800d5e59  mov     eax, [rcx+0ECh]
0x1800d5e5f  mov     [rbp+150h+var_1AC], eax
0x1800d5e62  movsd   xmm0, qword ptr [rcx+0F0h]
0x1800d5e6a  movsd   [rbp+150h+var_1A8], xmm0
0x1800d5e6f  mov     eax, [rcx+0F8h]
0x1800d5e75  mov     [rbp+150h+var_1A0], eax
0x1800d5e78  mov     rax, [rdi+90h]
0x1800d5e7f  mov     [rbp+150h+var_198], rax
0x1800d5e83  mov     rcx, [rdi]
0x1800d5e86  movq    r9, xmm6
0x1800d5e8b  psrldq  xmm6, 8
0x1800d5e90  movq    r8, xmm6
0x1800d5e95  mov     rax, [rcx+0D8h]
0x1800d5e9c  sub     rax, r9
0x1800d5e9f  jnz     short loc_1800D5EAB
0x1800d5ea1  mov     rax, [rcx+0E0h]
0x1800d5ea8  sub     rax, r8
0x1800d5eab  test    rax, rax
0x1800d5eae  jnz     short loc_1800D5ECE
0x1800d5eb0  mov     rax, [rcx+0ECh]
0x1800d5eb7  sub     rax, r9
0x1800d5eba  jnz     short loc_1800D5EC6
0x1800d5ebc  mov     rax, [rcx+0F4h]
0x1800d5ec3  sub     rax, r8
0x1800d5ec6  test    rax, rax
0x1800d5ec9  jnz     short loc_1800D5ECE
0x1800d5ecb  mov     esi, r15d
0x1800d5ece  mov     rax, [rcx+1A0h]
0x1800d5ed5  mov     [rbp+150h+var_190], rax
0x1800d5ed9  lea     rax, [rcx+1E0h]
0x1800d5ee0  mov     r8d, [rcx+1C0h]
0x1800d5ee7  test    r8d, r8d
0x1800d5eea  jnz     short loc_1800D5EF5
0x1800d5eec  cmp     [rax], r12d
0x1800d5eef  jz      loc_1800D5FE0
0x1800d5ef5  mov     edx, [rax]
0x1800d5ef7  mov     rcx, r8
0x1800d5efa  lea     r8, [rsp+250h+var_1E0]
0x1800d5eff  call    cs:__imp_FwSizeTAdd
0x1800d5f05  test    eax, eax
0x1800d5f07  jns     short loc_1800D5F1D
0x1800d5f09  mov     edx, eax
0x1800d5f0b  lea     rcx, aBfecreatetunne_0; "BfeCreateTunnelModeRule_old"
0x1800d5f12  call    cs:__imp_FwReportReturnError
0x1800d5f18  jmp     loc_1800D60DD
0x1800d5f1d  mov     rcx, [rsp+250h+var_1E0]
0x1800d5f22  mov     edx, 14h
0x1800d5f27  call    cs:__imp_FwAllocArray
0x1800d5f2d  mov     [rbp+150h+var_180], rax
0x1800d5f31  test    rax, rax
0x1800d5f34  jnz     short loc_1800D5F46
0x1800d5f36  lea     ebx, [rax+0Eh]
0x1800d5f39  mov     edx, 4B7h
0x1800d5f3e  mov     r8d, ebx
0x1800d5f41  jmp     loc_1800D60CE
0x1800d5f46  mov     rcx, [rdi]
0x1800d5f49  mov     r9d, r12d
0x1800d5f4c  cmp     [rcx+1C0h], r12d
0x1800d5f53  jbe     short loc_1800D5F89
0x1800d5f55  mov     rax, [rbp+150h+var_180]
0x1800d5f59  mov     edx, r9d
0x1800d5f5c  add     r9d, r15d
0x1800d5f5f  lea     r8, [rdx+rdx*4]
0x1800d5f63  mov     [rax+r8*4], r12d
0x1800d5f67  mov     rax, [rdi]
0x1800d5f6a  mov     rcx, [rax+1C8h]
0x1800d5f71  mov     rax, [rbp+150h+var_180]
0x1800d5f75  mov     edx, [rcx+rdx*8]
0x1800d5f78  mov     [rax+r8*4+4], edx
0x1800d5f7d  mov     rcx, [rdi]
0x1800d5f80  cmp     r9d, [rcx+1C0h]
0x1800d5f87  jb      short loc_1800D5F55
0x1800d5f89  mov     r10d, r12d
0x1800d5f8c  cmp     [rcx+1E0h], r12d
0x1800d5f93  jbe     short loc_1800D5FD6
0x1800d5f95  mov     eax, r9d
0x1800d5f98  add     r9d, r15d
0x1800d5f9b  mov     edx, r10d
0x1800d5f9e  add     r10d, r15d
0x1800d5fa1  shl     rdx, 5
0x1800d5fa5  lea     r8, [rax+rax*4]
0x1800d5fa9  mov     rax, [rbp+150h+var_180]
0x1800d5fad  mov     [rax+r8*4], r15d
0x1800d5fb1  mov     rax, [rdi]
0x1800d5fb4  mov     rcx, [rax+1E8h]
0x1800d5fbb  mov     rax, [rbp+150h+var_180]
0x1800d5fbf  movups  xmm0, xmmword ptr [rdx+rcx]
0x1800d5fc3  movdqu  xmmword ptr [rax+r8*4+4], xmm0
0x1800d5fca  mov     rcx, [rdi]
0x1800d5fcd  cmp     r10d, [rcx+1E0h]
0x1800d5fd4  jb      short loc_1800D5F95
0x1800d5fd6  mov     eax, dword ptr [rsp+250h+var_1E0]
0x1800d5fda  mov     edx, [rbp+150h+var_1D0]
0x1800d5fdd  mov     [rbp+150h+var_188], eax
0x1800d5fe0  test    byte ptr [rcx+154h], 10h
0x1800d5fe7  jz      short loc_1800D5FF0
0x1800d5fe9  bts     edx, 0Ah
0x1800d5fed  mov     [rbp+150h+var_1D0], edx
0x1800d5ff0  test    byte ptr [rcx+154h], 8
0x1800d5ff7  jz      short loc_1800D6000
0x1800d5ff9  bts     edx, 0Bh
0x1800d5ffd  mov     [rbp+150h+var_1D0], edx
  ... truncated ...
```
