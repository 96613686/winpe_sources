# BfeCreateTunnelModeRule_old(int,int,_FW_CS_RULE_INT_ *,_BFE_AUTH_SET_ *,IKEEXT_POLICY2_ *,_BFE_AUTH_SET_ *,IPSEC_TRANSPORT_POLICY2_ *,_GUID *,_GUID *)

- ea: `0x1800dc30c`
- end: `0x1800dc96c`
- name: `?BfeCreateTunnelModeRule_old@@YAKHHPEAU_FW_CS_RULE_INT_@@PEAU_BFE_AUTH_SET_@@PEAUIKEEXT_POLICY2_@@1PEAUIPSEC_TRANSPORT_POLICY2_@@PEAU_GUID@@4@Z`
- size: `1632`
- prototype: `unsigned int(int, int, struct _FW_CS_RULE_INT_ *, struct _BFE_AUTH_SET_ *, struct IKEEXT_POLICY2_ *, struct _BFE_AUTH_SET_ *, struct IPSEC_TRANSPORT_POLICY2_ *, struct _GUID *, struct _GUID *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800db5c8`

## callees

- `0x1800089bc`
- `0x18004f4ac`
- `0x18006e384`
- `0x1800729c0`
- `0x180073488`
- `0x1800da2e0`
- `0x1800db924`
- `0x1800dc30c`
- `0x1800dc974`
- `0x1800dc98c`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800dc471`
- `RPCRT4!UuidCreate` at `0x1800dc471`
- `fwbase!FwSizeTAdd` at `0x1800dc6dd`
- `fwbase!FwSizeTAdd` at `0x1800dc6dd`
- `fwbase!FwAllocArray` at `0x1800dc711`
- `fwbase!FwAllocArray` at `0x1800dc711`
- `fwbase!FwReportReturnError` at `0x1800dc6f6`
- `fwbase!FwReportReturnError` at `0x1800dc6f6`
- `fwbase!FwFree` at `0x1800dc8d6`
- `fwbase!FwFree` at `0x1800dc8ff`
- `fwbase!FwFree` at `0x1800dc914`
- `fwbase!FwFree` at `0x1800dc8d6`
- `fwbase!FwFree` at `0x1800dc8ff`
- `fwbase!FwFree` at `0x1800dc914`

## string_xrefs

- `0x1800dc43f`: `BfeCreateTunnelModeRule_old`
- `0x1800dc6ef`: `BfeCreateTunnelModeRule_old`
- `0x1800dc8c1`: `BfeCreateTunnelModeRule_old`
- `0x1800dc92b`: `BfeCreateTunnelModeRule_old`

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
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rcx
  const wchar_t *v23; // rdx
  __int64 v24; // xmm0_8
  const wchar_t *v25; // rax
  unsigned int v26; // eax
  unsigned int v27; // edx
  bool v28; // zf
  unsigned int v29; // esi
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  unsigned __int64 v33; // xmm6_8
  unsigned __int64 v34; // rax
  unsigned __int64 v35; // rax
  _DWORD *v36; // rax
  int v37; // eax
  unsigned int v38; // r8d
  unsigned int i; // r9d
  __int64 v40; // rdx
  __int64 v41; // r8
  unsigned int v42; // r10d
  __int64 v43; // rax
  __int64 v44; // rdx
  __int64 v45; // r8
  int v46; // ecx
  int v47; // eax
  struct FWP_CONDITION_VALUE0_ *v48; // r9
  struct FWP_CONDITION_VALUE0_ *v49; // r8
  int v51; // [rsp+48h] [rbp-C0h]
  struct FWP_CONDITION_VALUE0_ v52; // [rsp+58h] [rbp-B0h] BYREF
  struct FWP_CONDITION_VALUE0_ v53; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v54; // [rsp+78h] [rbp-90h] BYREF
  _DWORD v55[2]; // [rsp+88h] [rbp-80h] BYREF
  __int64 v56; // [rsp+90h] [rbp-78h]
  int v57; // [rsp+98h] [rbp-70h]
  int v58; // [rsp+9Ch] [rbp-6Ch]
  __int64 v59; // [rsp+A0h] [rbp-68h]
  int v60; // [rsp+A8h] [rbp-60h]
  int v61; // [rsp+ACh] [rbp-5Ch]
  __int64 v62; // [rsp+B0h] [rbp-58h]
  int v63; // [rsp+B8h] [rbp-50h]
  __int64 v64; // [rsp+C0h] [rbp-48h]
  __int64 v65; // [rsp+C8h] [rbp-40h]
  int v66; // [rsp+D0h] [rbp-38h]
  __int64 v67; // [rsp+D8h] [rbp-30h]
  __int64 v68; // [rsp+E0h] [rbp-28h]
  struct IKEEXT_AUTHENTICATION_METHOD2_ **v69; // [rsp+E8h] [rbp-20h]
  int v70; // [rsp+F0h] [rbp-18h]
  struct IKEEXT_AUTHENTICATION_METHOD2_ *v71[2]; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v72; // [rsp+108h] [rbp+0h]
  struct IKEEXT_AUTHENTICATION_METHOD2_ *v73[2]; // [rsp+110h] [rbp+8h] BYREF
  __int128 v74; // [rsp+120h] [rbp+18h]
  __int128 v75; // [rsp+130h] [rbp+28h]
  unsigned int Data1; // [rsp+148h] [rbp+40h] BYREF
  __int64 v77; // [rsp+14Ch] [rbp+44h] BYREF
  int v78; // [rsp+154h] [rbp+4Ch]
  const wchar_t *v79; // [rsp+158h] [rbp+50h]
  const wchar_t *v80; // [rsp+160h] [rbp+58h]
  int v81; // [rsp+188h] [rbp+80h]
  struct IKEEXT_AUTHENTICATION_METHOD2_ **v82; // [rsp+190h] [rbp+88h]
  int v83; // [rsp+1A8h] [rbp+A0h] BYREF
  _BYTE v84[60]; // [rsp+1ACh] [rbp+A4h] BYREF
  int v85; // [rsp+1E8h] [rbp+E0h]
  _DWORD *v86; // [rsp+1F0h] [rbp+E8h]

  *(_OWORD *)v73 = 0;
  v74 = 0;
  v75 = 0;
  memset_0(v55, 0, 0x70u);
  Data1 = 0;
  memset_0(&v77, 0, 0x54u);
  v83 = 0;
  memset_0(v84, 0, 0x54u);
  v54 = 0;
  v72 = 0;
  v51 = *((_DWORD *)a3 + 15);
  v12 = *((_DWORD *)a3 + 43);
  *(_OWORD *)v71 = 0;
  v52 = 0;
  v53 = 0;
  if ( *((_DWORD *)a3 + 38) == v12 )
  {
    v13 = v55[0];
    v14 = 0;
    v15 = 0;
    goto LABEL_33;
  }
  v16 = *((_OWORD *)a5 + 1);
  *(_OWORD *)v73 = *(_OWORD *)a5;
  v17 = *((_OWORD *)a5 + 2);
  v74 = v16;
  v75 = v17;
  v18 = BfeConvertAuthMethodsV0ToV2(a4, &v73[1]);
  v14 = v18;
  if ( v18 )
  {
    v19 = 1017;
LABEL_5:
    IpsTraceError("BfeCreateTunnelModeRule_old", v19, v18, 0);
    goto LABEL_85;
  }
  HIDWORD(v73[0]) = *((_DWORD *)a4 + 2);
  if ( a1 )
    LODWORD(v74) = *((_DWORD *)a4 + 3) != 0;
  v18 = UuidCreate(Uuid);
  v14 = v18;
  if ( v18 )
  {
    v19 = 1030;
    goto LABEL_5;
  }
  v81 = 6;
  v82 = v73;
  v15 = 1;
  if ( !a1 )
    v81 = 5;
  v21 = *(_QWORD *)&GUID_NULL.Data1 - *(_QWORD *)&Uuid->Data1;
  if ( *(_QWORD *)&GUID_NULL.Data1 == *(_QWORD *)&Uuid->Data1 )
    v21 = *(_QWORD *)GUID_NULL.Data4 - *(_QWORD *)Uuid->Data4;
  if ( !v21 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v20);
  v22 = *(_QWORD *)a3;
  v23 = L" ";
  v24 = *(_QWORD *)&Uuid->Data2;
  Data1 = Uuid->Data1;
  v78 = *(_DWORD *)&Uuid->Data4[4];
  v25 = L" ";
  v77 = v24;
  if ( *(_QWORD *)(v22 + 24) )
    v25 = *(const wchar_t **)(v22 + 24);
  v79 = v25;
  if ( *(_QWORD *)(v22 + 32) )
    v23 = *(const wchar_t **)(v22 + 32);
  v55[1] = *(_DWORD *)a7;
  v56 = *((_QWORD *)a7 + 1);
  v68 = *((_QWORD *)a7 + 3);
  v80 = v23;
  v13 = v55[0];
  if ( (_DWORD)xmmword_180132A70 == 1 )
  {
    v13 = v55[0] | 0x10;
LABEL_24:
    v55[0] = v13;
    goto LABEL_25;
  }
  if ( (_DWORD)xmmword_180132A70 == 2 )
  {
    v13 = v55[0] | 0x20;
    goto LABEL_24;
  }
LABEL_25:
  if ( a1 )
  {
    if ( a6 )
    {
      v26 = BfeConvertAuthMethodsV0ToV2(a6, &v71[1]);
      v14 = v26;
      if ( v26 )
      {
        v27 = 1074;
LABEL_83:
        v38 = v26;
        goto LABEL_84;
      }
      v28 = *((_DWORD *)a6 + 3) == 0;
      v13 = v55[0];
      LODWORD(v71[0]) = *((_DWORD *)a6 + 2);
      LODWORD(v72) = !v28;
      v69 = v71;
    }
    v85 = 4;
  }
  else
  {
    v85 = 2;
  }
  v86 = v55;
LABEL_33:
  v29 = 0;
  if ( v51 == 1 )
  {
    if ( v15 == 1 )
    {
      v30 = *(_QWORD *)a3;
      v57 = 0;
      v58 = *(_DWORD *)(v30 + 212);
      v61 = *(_DWORD *)(v30 + 232);
      v64 = *((_QWORD *)a3 + 18);
    }
    v31 = *(_QWORD *)a3;
    if ( !*(_DWORD *)(*(_QWORD *)a3 + 212LL) && !*(_DWORD *)(v31 + 232) )
      v29 = 1;
  }
  else
  {
    if ( v15 == 1 )
    {
      v32 = *(_QWORD *)a3;
      v57 = 1;
      v58 = *(_DWORD *)(v32 + 216);
      v59 = *(_QWORD *)(v32 + 220);
      v60 = *(_DWORD *)(v32 + 228);
      v61 = *(_DWORD *)(v32 + 236);
      v62 = *(_QWORD *)(v32 + 240);
      v63 = *(_DWORD *)(v32 + 248);
      v64 = *((_QWORD *)a3 + 18);
    }
    v31 = *(_QWORD *)a3;
    v33 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    v34 = *(_QWORD *)(*(_QWORD *)a3 + 216LL);
    if ( !v34 )
      v34 = *(_QWORD *)(v31 + 224) - v33;
    if ( !v34 )
    {
      v35 = *(_QWORD *)(v31 + 236);
      if ( !v35 )
        v35 = *(_QWORD *)(v31 + 244) - v33;
      if ( !v35 )
        v29 = 1;
    }
  }
  v65 = *(_QWORD *)(v31 + 416);
  v36 = (_DWORD *)(v31 + 480);
  if ( *(_DWORD *)(v31 + 448) || *v36 )
  {
    v37 = FwSizeTAdd(*(unsigned int *)(v31 + 448), (unsigned int)*v36, &v54);
    if ( v37 < 0 )
    {
      FwReportReturnError("BfeCreateTunnelModeRule_old", (unsigned int)v37);
      goto LABEL_85;
    }
    v67 = FwAllocArray(v54, 20);
    if ( !v67 )
    {
      v14 = 14;
      v27 = 1181;
      v38 = 14;
LABEL_84:
      IpsTraceError("BfeCreateTunnelModeRule_old", v27, v38, 0);
      goto LABEL_85;
    }
    v31 = *(_QWORD *)a3;
    for ( i = 0; i < *(_DWORD *)(*(_QWORD *)a3 + 448LL); v31 = *(_QWORD *)a3 )
    {
      v40 = i++;
      v41 = 5 * v40;
      *(_DWORD *)(v67 + 4 * v41) = 0;
      *(_DWORD *)(v67 + 4 * v41 + 4) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a3 + 456LL) + 8 * v40);
    }
    v42 = 0;
    if ( *(_DWORD *)(v31 + 480) )
    {
      do
      {
        v43 = i++;
        v44 = v42++;
        v45 = 5 * v43;
        *(_DWORD *)(v67 + 4 * v45) = 1;
        *(_OWORD *)(v67 + 4 * v45 + 4) = *(_OWORD *)(32 * v44 + *(_QWORD *)(*(_QWORD *)a3 + 488LL));
        v31 = *(_QWORD *)a3;
      }
      while ( v42 < *(_DWORD *)(*(_QWORD *)a3 + 480LL) );
    }
    v13 = v55[0];
    v66 = v54;
  }
  if ( (*(_BYTE *)(v31 + 340) & 0x10) != 0 )
  {
    v13 |= 0x400u;
    v55[0] = v13;
  }
  if ( (*(_BYTE *)(v31 + 340) & 8) != 0 )
  {
    v13 |= 0x800u;
    v55[0] = v13;
  }
  if ( (*(&gvIpsGlobalConfig + 12) & 2) != 0 )
  {
    v13 |= 0x1000u;
    v55[0] = v13;
  }
  if ( (*(_BYTE *)(v31 + 340) & 0x40) != 0 && a1 )
  {
    v13 |= 0x2000u;
    v55[0] = v13;
  }
  if ( *(char *)(v31 + 340) < 0 )
    v55[0] = v13 | 0x4000;
  v46 = *(_DWORD *)(v31 + 500);
  v47 = v70;
  if ( v46 )
    v47 = v46;
  v70 = v47;
  v26 = BfeIpAddressFill((struct _FW_CS_RULE_INT_ *)((char *)a3 + 56), &v52);
  v14 = v26;
  if ( v26 )
  {
    v27 = 1245;
    goto LABEL_83;
  }
  v26 = BfeIpAddressFill((struct _FW_CS_RULE_INT_ *)((char *)a3 + 96), &v53);
  v14 = v26;
  if ( v26 )
  {
    v27 = 1250;
    goto LABEL_83;
  }
  v48 = &v53;
  v49 = &v52;
  if ( *((_DWORD *)a3 + 24) == 1 )
    v48 = 0;
  if ( *((_DWORD *)a3 + 14) == 1 )
    v49 = 0;
  v26 = BfeCallTunnelFilterAdd_old(
          a3,
          v29,
          (struct FWPM_PROVIDER_CONTEXT2_ *)&Data1,
          (struct FWPM_PROVIDER_CONTEXT2_ *)&v83,
          v49,
          v48,
          a9);
  v14 = v26;
  if ( v26 )
  {
    v27 = 1260;
    goto LABEL_83;
  }
LABEL_85:
  if ( v67 )
    FwFree(v67);
  BfeIpAddressFree(&v52);
  BfeIpAddressFree(&v53);
  if ( v73[1] )
    FwFree(v73[1]);
  if ( v71[1] )
    FwFree(v71[1]);
  return IpsReturnError("BfeCreateTunnelModeRule_old", 0x4FBu, v14, 0, 0);
}

```

## disassembly

```asm
0x1800dc30c  mov     rax, rsp
0x1800dc30f  mov     [rax+8], rbx
0x1800dc313  push    rbp
0x1800dc314  push    rsi
0x1800dc315  push    rdi
0x1800dc316  push    r12
0x1800dc318  push    r13
0x1800dc31a  push    r14
0x1800dc31c  push    r15
0x1800dc31e  lea     rbp, [rax-158h]
0x1800dc325  sub     rsp, 220h
0x1800dc32c  movaps  xmmword ptr [rax-48h], xmm6
0x1800dc330  mov     rax, cs:__security_cookie
0x1800dc337  xor     rax, rsp
0x1800dc33a  mov     [rbp+150h+var_50], rax
0x1800dc341  mov     rax, [rbp+150h+arg_40]
0x1800dc348  xorps   xmm0, xmm0
0x1800dc34b  mov     r12, [rbp+150h+arg_30]
0x1800dc352  xor     edx, edx; Val
0x1800dc354  mov     rbx, [rbp+150h+arg_20]
0x1800dc35b  mov     rdi, r8
0x1800dc35e  mov     r15, [rbp+150h+arg_28]
0x1800dc365  mov     r13d, ecx
0x1800dc368  mov     rsi, [rbp+150h+Uuid]
0x1800dc36f  lea     rcx, [rbp+150h+var_1D0]; void *
0x1800dc373  lea     r8d, [rdx+70h]; Size
0x1800dc377  mov     qword ptr [rsp+250h+var_208.type], rax
0x1800dc37c  mov     r14, r9
0x1800dc37f  movups  xmmword ptr [rbp+150h+var_148], xmm0
0x1800dc383  movups  [rbp+150h+var_138], xmm0
0x1800dc387  movups  [rbp+150h+var_128], xmm0
0x1800dc38b  call    memset_0
0x1800dc390  xor     edx, edx; Val
0x1800dc392  mov     [rbp+150h+var_110], 0
0x1800dc399  lea     rcx, [rbp+150h+var_10C]; void *
0x1800dc39d  lea     r8d, [rdx+54h]; Size
0x1800dc3a1  call    memset_0
0x1800dc3a6  xor     edx, edx; Val
0x1800dc3a8  mov     [rbp+150h+var_B0], 0
0x1800dc3b2  lea     rcx, [rbp+150h+var_AC]; void *
0x1800dc3b9  lea     r8d, [rdx+54h]; Size
0x1800dc3bd  call    memset_0
0x1800dc3c2  xor     eax, eax
0x1800dc3c4  mov     [rsp+250h+var_1E0], 0
0x1800dc3cd  mov     [rbp+150h+var_150], rax
0x1800dc3d1  xorps   xmm0, xmm0
0x1800dc3d4  mov     eax, [rdi+3Ch]
0x1800dc3d7  xorps   xmm1, xmm1
0x1800dc3da  mov     dword ptr [rsp+250h+var_210], eax
0x1800dc3de  xorps   xmm6, xmm6
0x1800dc3e1  mov     eax, [rdi+0ACh]
0x1800dc3e7  movups  xmmword ptr [rbp+150h+var_160], xmm0
0x1800dc3eb  movups  xmmword ptr [rsp+250h+var_208.8], xmm0
0x1800dc3f0  movups  xmmword ptr [rsp+250h+var_1F8+8], xmm1
0x1800dc3f5  cmp     [rdi+98h], eax
0x1800dc3fb  jnz     short loc_1800DC40E
0x1800dc3fd  mov     edx, [rbp+150h+var_1D0]
0x1800dc400  xor     r12d, r12d
0x1800dc403  mov     ebx, r12d
0x1800dc406  mov     r14d, r12d
0x1800dc409  jmp     loc_1800DC5B3
0x1800dc40e  movups  xmm0, xmmword ptr [rbx]
0x1800dc411  lea     rdx, [rbp+150h+var_148+8]; struct IKEEXT_AUTHENTICATION_METHOD2_ **
0x1800dc415  mov     rcx, r14; struct _BFE_AUTH_SET_ *
0x1800dc418  movups  xmm1, xmmword ptr [rbx+10h]
0x1800dc41c  movups  xmmword ptr [rbp+150h+var_148], xmm0
0x1800dc420  movups  xmm0, xmmword ptr [rbx+20h]
0x1800dc424  movups  [rbp+150h+var_138], xmm1
0x1800dc428  movups  [rbp+150h+var_128], xmm0
0x1800dc42c  call    ?BfeConvertAuthMethodsV0ToV2@@YAKPEAU_BFE_AUTH_SET_@@PEAPEAUIKEEXT_AUTHENTICATION_METHOD2_@@@Z; BfeConvertAuthMethodsV0ToV2(_BFE_AUTH_SET_ *,IKEEXT_AUTHENTICATION_METHOD2_ * *)
0x1800dc431  mov     ebx, eax
0x1800dc433  test    eax, eax
0x1800dc435  jz      short loc_1800DC456
0x1800dc437  mov     edx, 3F9h; unsigned int
0x1800dc43c  mov     r8d, eax; unsigned int
0x1800dc43f  lea     rcx, aBfecreatetunne_0; "BfeCreateTunnelModeRule_old"
0x1800dc446  xor     r9d, r9d; int
0x1800dc449  call    ?IpsTraceError@@YAXPEBDKKH@Z; IpsTraceError(char const *,ulong,ulong,int)
0x1800dc44e  xor     r12d, r12d
0x1800dc451  jmp     loc_1800DC8CD
0x1800dc456  mov     eax, [r14+8]
0x1800dc45a  mov     dword ptr [rbp+150h+var_148+4], eax
0x1800dc45d  test    r13d, r13d
0x1800dc460  jz      short loc_1800DC46E
0x1800dc462  xor     eax, eax
0x1800dc464  cmp     [r14+0Ch], eax
0x1800dc468  setnz   al
0x1800dc46b  mov     dword ptr [rbp+150h+var_138], eax
0x1800dc46e  mov     rcx, rsi; Uuid
0x1800dc471  call    cs:__imp_UuidCreate
0x1800dc478  nop     dword ptr [rax+rax+00h]
0x1800dc47d  mov     ebx, eax
0x1800dc47f  test    eax, eax
0x1800dc481  jz      short loc_1800DC48A
0x1800dc483  mov     edx, 406h
0x1800dc488  jmp     short loc_1800DC43C
0x1800dc48a  mov     [rbp+150h+var_D0], 6
0x1800dc494  lea     rax, [rbp+150h+var_148]
0x1800dc498  mov     [rbp+150h+var_C8], rax
0x1800dc49f  mov     r14d, 1
0x1800dc4a5  test    r13d, r13d
0x1800dc4a8  jnz     short loc_1800DC4B4
0x1800dc4aa  mov     [rbp+150h+var_D0], 5
0x1800dc4b4  mov     rax, qword ptr cs:GUID_NULL.Data1
0x1800dc4bb  sub     rax, [rsi]
0x1800dc4be  jnz     short loc_1800DC4CB
0x1800dc4c0  mov     rax, qword ptr cs:GUID_NULL.Data4
0x1800dc4c7  sub     rax, [rsi+8]
0x1800dc4cb  test    rax, rax
0x1800dc4ce  jnz     short loc_1800DC4D5
0x1800dc4d0  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "!IsEqualGUID(GUID_NULL, *pMainModeContext)")
0x1800dc4d5  mov     rcx, [rdi]
0x1800dc4d8  lea     rdx, asc_1801110D8; " "
0x1800dc4df  mov     eax, [rsi]
0x1800dc4e1  movsd   xmm0, qword ptr [rsi+4]
0x1800dc4e6  mov     [rbp+150h+var_110], eax
0x1800dc4e9  mov     eax, [rsi+0Ch]
0x1800dc4ec  mov     [rbp+150h+var_104], eax
0x1800dc4ef  mov     rax, rdx
0x1800dc4f2  movsd   [rbp+150h+var_10C], xmm0
0x1800dc4f7  cmp     qword ptr [rcx+18h], 0
0x1800dc4fc  cmovnz  rax, [rcx+18h]
0x1800dc501  mov     [rbp+150h+var_100], rax
0x1800dc505  cmp     qword ptr [rcx+20h], 0
0x1800dc50a  mov     eax, [r12]
0x1800dc50e  cmovnz  rdx, [rcx+20h]
0x1800dc513  mov     [rbp+150h+var_1CC], eax
0x1800dc516  mov     rax, [r12+8]
0x1800dc51b  mov     [rbp+150h+var_1C8], rax
0x1800dc51f  mov     rax, [r12+18h]
0x1800dc524  mov     [rbp+150h+var_178], rax
0x1800dc528  mov     eax, dword ptr cs:xmmword_180132A70
0x1800dc52e  mov     [rbp+150h+var_F8], rdx
0x1800dc532  mov     edx, [rbp+150h+var_1D0]
0x1800dc535  cmp     eax, r14d
0x1800dc538  jnz     short loc_1800DC53F
0x1800dc53a  or      edx, 10h
0x1800dc53d  jmp     short loc_1800DC547
0x1800dc53f  cmp     eax, 2
0x1800dc542  jnz     short loc_1800DC54A
0x1800dc544  or      edx, 20h
0x1800dc547  mov     [rbp+150h+var_1D0], edx
0x1800dc54a  xor     r12d, r12d
0x1800dc54d  test    r13d, r13d
0x1800dc550  jz      short loc_1800DC59E
0x1800dc552  test    r15, r15
0x1800dc555  jz      short loc_1800DC592
0x1800dc557  lea     rdx, [rbp+150h+var_160+8]; struct IKEEXT_AUTHENTICATION_METHOD2_ **
0x1800dc55b  mov     rcx, r15; struct _BFE_AUTH_SET_ *
0x1800dc55e  call    ?BfeConvertAuthMethodsV0ToV2@@YAKPEAU_BFE_AUTH_SET_@@PEAPEAUIKEEXT_AUTHENTICATION_METHOD2_@@@Z; BfeConvertAuthMethodsV0ToV2(_BFE_AUTH_SET_ *,IKEEXT_AUTHENTICATION_METHOD2_ * *)
0x1800dc563  mov     ebx, eax
0x1800dc565  test    eax, eax
0x1800dc567  jz      short loc_1800DC573
0x1800dc569  mov     edx, 432h
0x1800dc56e  jmp     loc_1800DC8BB
0x1800dc573  mov     eax, [r15+8]
0x1800dc577  cmp     [r15+0Ch], r12d
0x1800dc57b  mov     edx, [rbp+150h+var_1D0]
0x1800dc57e  mov     dword ptr [rbp+150h+var_160], eax
0x1800dc581  mov     eax, r12d
0x1800dc584  setnz   al
0x1800dc587  mov     dword ptr [rbp+150h+var_150], eax
0x1800dc58a  lea     rax, [rbp+150h+var_160]
0x1800dc58e  mov     [rbp+150h+var_170], rax
0x1800dc592  mov     [rbp+150h+var_70], 4
0x1800dc59c  jmp     short loc_1800DC5A8
0x1800dc59e  mov     [rbp+150h+var_70], 2
0x1800dc5a8  lea     rax, [rbp+150h+var_1D0]
0x1800dc5ac  mov     [rbp+150h+var_68], rax
0x1800dc5b3  mov     r15d, 1
0x1800dc5b9  mov     esi, r12d
0x1800dc5bc  cmp     dword ptr [rsp+250h+var_210], r15d
0x1800dc5c1  jnz     short loc_1800DC60C
0x1800dc5c3  cmp     r14d, r15d
0x1800dc5c6  jnz     short loc_1800DC5EC
0x1800dc5c8  mov     rcx, [rdi]
0x1800dc5cb  mov     [rbp+150h+var_1C0], r12d
0x1800dc5cf  mov     eax, [rcx+0D4h]
0x1800dc5d5  mov     [rbp+150h+var_1BC], eax
0x1800dc5d8  mov     eax, [rcx+0E8h]
0x1800dc5de  mov     [rbp+150h+var_1AC], eax
0x1800dc5e1  mov     rax, [rdi+90h]
0x1800dc5e8  mov     [rbp+150h+var_198], rax
0x1800dc5ec  mov     rcx, [rdi]
0x1800dc5ef  cmp     [rcx+0D4h], r12d
0x1800dc5f6  jnz     loc_1800DC6AC
0x1800dc5fc  cmp     [rcx+0E8h], r12d
0x1800dc603  cmovz   esi, r15d
0x1800dc607  jmp     loc_1800DC6AC
0x1800dc60c  cmp     r14d, r15d
0x1800dc60f  jnz     short loc_1800DC661
0x1800dc611  mov     rcx, [rdi]
0x1800dc614  mov     [rbp+150h+var_1C0], r15d
0x1800dc618  mov     eax, [rcx+0D8h]
0x1800dc61e  mov     [rbp+150h+var_1BC], eax
0x1800dc621  movsd   xmm0, qword ptr [rcx+0DCh]
0x1800dc629  movsd   [rbp+150h+var_1B8], xmm0
0x1800dc62e  mov     eax, [rcx+0E4h]
0x1800dc634  mov     [rbp+150h+var_1B0], eax
0x1800dc637  mov     eax, [rcx+0ECh]
0x1800dc63d  mov     [rbp+150h+var_1AC], eax
0x1800dc640  movsd   xmm0, qword ptr [rcx+0F0h]
0x1800dc648  movsd   [rbp+150h+var_1A8], xmm0
0x1800dc64d  mov     eax, [rcx+0F8h]
0x1800dc653  mov     [rbp+150h+var_1A0], eax
0x1800dc656  mov     rax, [rdi+90h]
0x1800dc65d  mov     [rbp+150h+var_198], rax
0x1800dc661  mov     rcx, [rdi]
0x1800dc664  movq    r9, xmm6
0x1800dc669  psrldq  xmm6, 8
0x1800dc66e  movq    r8, xmm6
0x1800dc673  mov     rax, [rcx+0D8h]
0x1800dc67a  sub     rax, r9
0x1800dc67d  jnz     short loc_1800DC689
0x1800dc67f  mov     rax, [rcx+0E0h]
0x1800dc686  sub     rax, r8
0x1800dc689  test    rax, rax
0x1800dc68c  jnz     short loc_1800DC6AC
0x1800dc68e  mov     rax, [rcx+0ECh]
0x1800dc695  sub     rax, r9
0x1800dc698  jnz     short loc_1800DC6A4
0x1800dc69a  mov     rax, [rcx+0F4h]
0x1800dc6a1  sub     rax, r8
0x1800dc6a4  test    rax, rax
0x1800dc6a7  jnz     short loc_1800DC6AC
0x1800dc6a9  mov     esi, r15d
0x1800dc6ac  mov     rax, [rcx+1A0h]
0x1800dc6b3  mov     [rbp+150h+var_190], rax
0x1800dc6b7  lea     rax, [rcx+1E0h]
0x1800dc6be  mov     r8d, [rcx+1C0h]
0x1800dc6c5  test    r8d, r8d
0x1800dc6c8  jnz     short loc_1800DC6D3
0x1800dc6ca  cmp     [rax], r12d
0x1800dc6cd  jz      loc_1800DC7D0
0x1800dc6d3  mov     edx, [rax]
0x1800dc6d5  mov     rcx, r8
0x1800dc6d8  lea     r8, [rsp+250h+var_1E0]
0x1800dc6dd  call    cs:__imp_FwSizeTAdd
0x1800dc6e4  nop     dword ptr [rax+rax+00h]
0x1800dc6e9  test    eax, eax
0x1800dc6eb  jns     short loc_1800DC707
0x1800dc6ed  mov     edx, eax
0x1800dc6ef  lea     rcx, aBfecreatetunne_0; "BfeCreateTunnelModeRule_old"
0x1800dc6f6  call    cs:__imp_FwReportReturnError
0x1800dc6fd  nop     dword ptr [rax+rax+00h]
0x1800dc702  jmp     loc_1800DC8CD
0x1800dc707  mov     rcx, [rsp+250h+var_1E0]
0x1800dc70c  mov     edx, 14h
0x1800dc711  call    cs:__imp_FwAllocArray
0x1800dc718  nop     dword ptr [rax+rax+00h]
0x1800dc71d  mov     [rbp+150h+var_180], rax
0x1800dc721  test    rax, rax
0x1800dc724  jnz     short loc_1800DC736
0x1800dc726  lea     ebx, [rax+0Eh]
0x1800dc729  mov     edx, 49Dh
0x1800dc72e  mov     r8d, ebx
0x1800dc731  jmp     loc_1800DC8BE
0x1800dc736  mov     rcx, [rdi]
0x1800dc739  mov     r9d, r12d
0x1800dc73c  cmp     [rcx+1C0h], r12d
0x1800dc743  jbe     short loc_1800DC779
0x1800dc745  mov     rax, [rbp+150h+var_180]
0x1800dc749  mov     edx, r9d
0x1800dc74c  add     r9d, r15d
0x1800dc74f  lea     r8, [rdx+rdx*4]
0x1800dc753  mov     [rax+r8*4], r12d
0x1800dc757  mov     rax, [rdi]
0x1800dc75a  mov     rcx, [rax+1C8h]
0x1800dc761  mov     rax, [rbp+150h+var_180]
0x1800dc765  mov     edx, [rcx+rdx*8]
0x1800dc768  mov     [rax+r8*4+4], edx
0x1800dc76d  mov     rcx, [rdi]
0x1800dc770  cmp     r9d, [rcx+1C0h]
0x1800dc777  jb      short loc_1800DC745
0x1800dc779  mov     r10d, r12d
0x1800dc77c  cmp     [rcx+1E0h], r12d
0x1800dc783  jbe     short loc_1800DC7C6
0x1800dc785  mov     eax, r9d
0x1800dc788  add     r9d, r15d
0x1800dc78b  mov     edx, r10d
0x1800dc78e  add     r10d, r15d
0x1800dc791  shl     rdx, 5
0x1800dc795  lea     r8, [rax+rax*4]
0x1800dc799  mov     rax, [rbp+150h+var_180]
0x1800dc79d  mov     [rax+r8*4], r15d
0x1800dc7a1  mov     rax, [rdi]
0x1800dc7a4  mov     rcx, [rax+1E8h]
0x1800dc7ab  mov     rax, [rbp+150h+var_180]
0x1800dc7af  movups  xmm0, xmmword ptr [rdx+rcx]
0x1800dc7b3  movdqu  xmmword ptr [rax+r8*4+4], xmm0
0x1800dc7ba  mov     rcx, [rdi]
0x1800dc7bd  cmp     r10d, [rcx+1E0h]
0x1800dc7c4  jb      short loc_1800DC785
0x1800dc7c6  mov     eax, dword ptr [rsp+250h+var_1E0]
0x1800dc7ca  mov     edx, [rbp+150h+var_1D0]
0x1800dc7cd  mov     [rbp+150h+var_188], eax
0x1800dc7d0  test    byte ptr [rcx+154h], 10h
0x1800dc7d7  jz      short loc_1800DC7E0
0x1800dc7d9  bts     edx, 0Ah
0x1800dc7dd  mov     [rbp+150h+var_1D0], edx
  ... truncated ...
```
