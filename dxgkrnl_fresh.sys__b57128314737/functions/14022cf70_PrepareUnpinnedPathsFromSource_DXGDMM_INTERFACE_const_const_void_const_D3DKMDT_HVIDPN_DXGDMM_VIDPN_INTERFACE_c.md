# PrepareUnpinnedPathsFromSource(_DXGDMM_INTERFACE const * const,void * const,D3DKMDT_HVIDPN__ *,_DXGDMM_VIDPN_INTERFACE const *,D3DKMDT_HVIDPNTOPOLOGY__ *,_DXGDMM_VIDPNTOPOLOGY_INTERFACE const * const,uint,uchar,uchar,uchar,unsigned __int64 * const,uint (*)[16],uchar *)

- ea: `0x14022cf70`
- end: `0x14022d90e`
- name: `?PrepareUnpinnedPathsFromSource@@YAJQEBU_DXGDMM_INTERFACE@@QEAXPEAUD3DKMDT_HVIDPN__@@PEBU_DXGDMM_VIDPN_INTERFACE@@PEAUD3DKMDT_HVIDPNTOPOLOGY__@@QEBU_DXGDMM_VIDPNTOPOLOGY_INTERFACE@@IEEEQEA_KPEAY0BA@IPEAE@Z`
- size: `2462`
- prototype: `int(const struct _DXGDMM_INTERFACE *const, void *const, struct D3DKMDT_HVIDPN__ *, const struct _DXGDMM_VIDPN_INTERFACE *, struct D3DKMDT_HVIDPNTOPOLOGY__ *, const struct _DXGDMM_VIDPNTOPOLOGY_INTERFACE *const, unsigned int, unsigned __int8, unsigned __int8, unsigned __int8, unsigned __int64 *const, unsigned int (*)[16], unsigned __int8 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path`

## callers

- `0x1401b7b98`
- `0x1401dd4a4`

## callees

- `0x14001b9c0`
- `0x1400a0cb0`
- `0x1400a0d00`
- `0x1401a83a8`
- `0x14022b678`
- `0x14022cf70`

## import_xrefs

- `watchdog!WdLogSingleEntry4` at `0x14022d7a7`
- `watchdog!WdLogSingleEntry4` at `0x14022d7a7`
- `watchdog!WdLogSingleEntry2` at `0x14022d30b`
- `watchdog!WdLogSingleEntry2` at `0x14022d495`
- `watchdog!WdLogSingleEntry2` at `0x14022d552`
- `watchdog!WdLogSingleEntry2` at `0x14022d5a0`
- `watchdog!WdLogSingleEntry2` at `0x14022d6a6`
- `watchdog!WdLogSingleEntry2` at `0x14022d6d6`
- `watchdog!WdLogSingleEntry2` at `0x14022d6fd`
- `watchdog!WdLogSingleEntry2` at `0x14022d30b`
- `watchdog!WdLogSingleEntry2` at `0x14022d495`
- `watchdog!WdLogSingleEntry2` at `0x14022d552`
- `watchdog!WdLogSingleEntry2` at `0x14022d5a0`
- `watchdog!WdLogSingleEntry2` at `0x14022d6a6`
- `watchdog!WdLogSingleEntry2` at `0x14022d6d6`
- `watchdog!WdLogSingleEntry2` at `0x14022d6fd`
- `watchdog!WdLogSingleEntry3` at `0x14022d33a`
- `watchdog!WdLogSingleEntry3` at `0x14022d46c`
- `watchdog!WdLogSingleEntry3` at `0x14022d4f0`
- `watchdog!WdLogSingleEntry3` at `0x14022d5ec`
- `watchdog!WdLogSingleEntry3` at `0x14022d33a`
- `watchdog!WdLogSingleEntry3` at `0x14022d46c`
- `watchdog!WdLogSingleEntry3` at `0x14022d4f0`
- `watchdog!WdLogSingleEntry3` at `0x14022d5ec`
- `watchdog!WdLogSingleEntry0` at `0x14022cfdb`
- `watchdog!WdLogSingleEntry0` at `0x14022d02a`
- `watchdog!WdLogSingleEntry0` at `0x14022d07a`
- `watchdog!WdLogSingleEntry0` at `0x14022d0d0`
- `watchdog!WdLogSingleEntry0` at `0x14022d11f`
- `watchdog!WdLogSingleEntry0` at `0x14022d16f`
- `watchdog!WdLogSingleEntry0` at `0x14022d1c5`
- `watchdog!WdLogSingleEntry0` at `0x14022d214`
- `watchdog!WdLogSingleEntry0` at `0x14022d2af`
- `watchdog!WdLogSingleEntry0` at `0x14022d3d6`
- `watchdog!WdLogSingleEntry0` at `0x14022d745`
- `watchdog!WdLogSingleEntry0` at `0x14022d7d9`
- `watchdog!WdLogSingleEntry0` at `0x14022cfdb`
- `watchdog!WdLogSingleEntry0` at `0x14022d02a`
- `watchdog!WdLogSingleEntry0` at `0x14022d07a`
- `watchdog!WdLogSingleEntry0` at `0x14022d0d0`
- `watchdog!WdLogSingleEntry0` at `0x14022d11f`
- `watchdog!WdLogSingleEntry0` at `0x14022d16f`
- `watchdog!WdLogSingleEntry0` at `0x14022d1c5`
- `watchdog!WdLogSingleEntry0` at `0x14022d214`
- `watchdog!WdLogSingleEntry0` at `0x14022d2af`
- `watchdog!WdLogSingleEntry0` at `0x14022d3d6`
- `watchdog!WdLogSingleEntry0` at `0x14022d745`
- `watchdog!WdLogSingleEntry0` at `0x14022d7d9`
- `watchdog!WdLogSingleEntry5` at `0x14022d878`
- `watchdog!WdLogSingleEntry5` at `0x14022d878`

## string_xrefs

- `0x14022d505`: `Failed to enumerate target of %I64d'th path originating from source 0x%I64x (status = 0x%I64x)`
- `0x14022d34b`: `Failed to determine number of paths originating from source 0x%I64x in topology 0x%I64x (status = 0x%I64x)`
- `0x14022d2c0`: `sztNumPathsFromSource == 0`
- `0x14022d225`: `o_pNumVidPnPresentPathsFromSource != NULL`
- `0x14022d601`: `Failed to remove all paths from source 0x%I64x in topology 0x%I64x (status = 0x%I64x)`
- `0x14022d756`: `sztNumAugmentedPathsFromSource > 0`
- `0x14022d889`: `Failed to unpin modality of %I64d present path(s) originating from source 0x%I64x in VidPN 0x%I64x of adapter 0x%I64x (status = 0x%I64x)`
- `0x14022d7ea`: `sztNumPathsFromSource > 0`

## pseudocode

```c
__int64 __fastcall PrepareUnpinnedPathsFromSource(
        struct _DXGDMM_INTERFACE *a1,
        void *const a2,
        struct D3DKMDT_HVIDPN__ *a3,
        const struct _DXGDMM_VIDPN_INTERFACE *a4,
        struct D3DKMDT_HVIDPNTOPOLOGY__ *a5,
        struct _DXGDMM_VIDPNTOPOLOGY_INTERFACE *a6,
        unsigned int a7,
        unsigned __int8 a8,
        unsigned __int8 a9,
        unsigned __int8 a10,
        unsigned __int64 *const a11,
        __m128i *a12,
        unsigned __int8 *a13)
{
  struct _DXGDMM_VIDPNTOPOLOGY_INTERFACE *v14; // r15
  __m128i si128; // xmm0
  __int64 (__fastcall *v18)(struct D3DKMDT_HVIDPNTOPOLOGY__ *, _QWORD, unsigned __int64 *); // rax
  int v19; // eax
  __int64 v20; // r14
  char v21; // r13
  __int64 v22; // rdi
  __int64 result; // rax
  unsigned __int64 i; // r15
  int v25; // eax
  __int64 v26; // r13
  __int64 v27; // rdx
  int v28; // eax
  __int64 v29; // rdi
  int v30; // eax
  __int64 v31; // r15
  int v32; // eax
  unsigned int v33; // ebx
  unsigned __int64 v34; // rbx
  __int64 v35; // r15
  struct D3DKMDT_HVIDPN__ *v36; // r14
  int v37; // eax
  __int64 v38; // rsi
  void *v39; // rcx
  _BYTE v40[8]; // [rsp+50h] [rbp-A1h] BYREF
  unsigned __int64 v41; // [rsp+58h] [rbp-99h] BYREF
  unsigned __int64 v42; // [rsp+60h] [rbp-91h] BYREF
  struct _DXGDMM_VIDPNTOPOLOGY_INTERFACE *v43; // [rsp+68h] [rbp-89h]
  __int64 v44; // [rsp+70h] [rbp-81h]
  struct _DXGDMM_INTERFACE *v45; // [rsp+78h] [rbp-79h]
  struct _DXGDMM_VIDPN_INTERFACE *v46; // [rsp+80h] [rbp-71h]
  struct D3DKMDT_HVIDPN__ *v47; // [rsp+88h] [rbp-69h]
  unsigned __int64 *v48; // [rsp+90h] [rbp-61h]
  void *v49; // [rsp+98h] [rbp-59h]
  unsigned __int8 *v50; // [rsp+A0h] [rbp-51h]
  _OWORD Src[8]; // [rsp+B0h] [rbp-41h] BYREF

  v14 = a6;
  v49 = a12;
  v43 = a6;
  v48 = a11;
  v50 = a13;
  v46 = a4;
  v47 = a3;
  v44 = (__int64)a2;
  v45 = a1;
  if ( !a1 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4461;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"i_pDxgDmmInterface != NULL", 4461, 0, 0, 0, 0);
  }
  if ( !a2 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4462;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"i_hDxgAdapter != NULL", 4462, 0, 0, 0, 0);
  }
  if ( !a3 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4463;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"i_hVidPn != NULL", 4463, 0, 0, 0, 0);
  }
  if ( !a4 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4464;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"i_pDmmVidPnInterface != NULL", 4464, 0, 0, 0, 0);
  }
  if ( !a5 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4465;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"i_hVidPnTopology != NULL", 4465, 0, 0, 0, 0);
  }
  if ( !a6 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4466;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"i_pDmmVidPnTopologyInterface != NULL", 4466, 0, 0, 0, 0);
  }
  if ( a7 == -1 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4467;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"i_VidPnSourceId != D3DDDI_ID_UNINITIALIZED",
      4467,
      0,
      0,
      0,
      0);
  }
  if ( !a11 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4468;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"o_pNumVidPnPresentPathsFromSource != NULL",
      4468,
      0,
      0,
      0,
      0);
  }
  *a11 = 0;
  if ( a12 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    *a12 = si128;
    a12[1] = si128;
    a12[2] = si128;
    a12[3] = si128;
  }
  v18 = *(__int64 (__fastcall **)(struct D3DKMDT_HVIDPNTOPOLOGY__ *, _QWORD, unsigned __int64 *))a6;
  v41 = 0;
  v19 = v18(a5, a7, &v41);
  v20 = v19;
  if ( v19 == -1071774919 )
  {
    if ( v41 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 4499;
      DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"sztNumPathsFromSource == 0", 4499, 0, 0, 0, 0);
    }
    v21 = 1;
    v22 = a7;
    WdLogSingleEntry2(7, a5, a7);
    WdLogGlobalForLineNumber = 4505;
  }
  else
  {
    v21 = 0;
    if ( v19 < 0 )
    {
      WdLogSingleEntry3(2, a7, a5, v19);
      WdLogGlobalForLineNumber = 4513;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Failed to determine number of paths originating from source 0x%I64x in topology 0x%I64x (status = 0x%I64x)",
        a7,
        (__int64)a5,
        v20,
        0,
        0);
      return (unsigned int)v20;
    }
    for ( i = 0; i < v41; ++i )
    {
      LODWORD(v42) = -1;
      v25 = (*((__int64 (__fastcall **)(struct D3DKMDT_HVIDPNTOPOLOGY__ *, _QWORD, unsigned __int64, unsigned __int64 *))v43
             + 1))(
              a5,
              a7,
              i,
              &v42);
      v26 = v25;
      if ( v25 < 0 )
      {
        WdLogSingleEntry3(2, i, a7, v25);
        WdLogGlobalForLineNumber = 4536;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Failed to enumerate target of %I64d'th path originating from source 0x%I64x (status = 0x%I64x)",
          i,
          a7,
          v26,
          0,
          0);
        return (unsigned int)v26;
      }
      v27 = (unsigned int)v42;
      if ( (_DWORD)v42 == -1 )
      {
        WdLogSingleEntry0(1);
        v21 = 0;
        WdLogGlobalForLineNumber = 4542;
        DxgkLogInternalTriageEvent(
          0,
          262146,
          -1,
          (unsigned int)L"ConnectedVidPnTargetId != D3DDDI_ID_UNINITIALIZED",
          4542,
          0,
          0,
          0,
          0);
        v27 = (unsigned int)v42;
      }
      else
      {
        v21 = 0;
      }
      v40[0] = 0;
      v28 = (*((__int64 (__fastcall **)(void *const, __int64, _BYTE *))v45 + 9))(a2, v27, v40);
      v29 = v28;
      if ( v28 < 0 )
      {
        WdLogSingleEntry2(2, a2, v28);
        WdLogGlobalForLineNumber = 4555;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Failed to acquire target set of adapter 0x%I64x (status = 0x%I64x)",
          (__int64)a2,
          v29,
          0,
          0,
          0);
        return (unsigned int)v29;
      }
      if ( !v40[0] )
      {
        v21 = 1;
        v22 = a7;
        WdLogSingleEntry3(7, a5, a7, (unsigned int)v42);
        WdLogGlobalForLineNumber = 4568;
        goto LABEL_38;
      }
    }
    v22 = a7;
LABEL_38:
    WdLogSingleEntry2(7, v22, a5);
    v14 = v43;
    WdLogGlobalForLineNumber = 4576;
  }
  Src[0] = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  Src[1] = Src[0];
  Src[2] = Src[0];
  Src[3] = Src[0];
  if ( v21 )
  {
    if ( !a8 )
    {
      WdLogSingleEntry2(7, v22, a2);
      result = 3223192403LL;
      WdLogGlobalForLineNumber = 4597;
      return result;
    }
    if ( v41 )
    {
      v30 = (*((__int64 (__fastcall **)(struct D3DKMDT_HVIDPNTOPOLOGY__ *, _QWORD))v14 + 7))(a5, a7);
      v31 = v30;
      if ( v30 < 0 )
      {
        WdLogSingleEntry3(2, v22, a5, v30);
        WdLogGlobalForLineNumber = 4611;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Failed to remove all paths from source 0x%I64x in topology 0x%I64x (status = 0x%I64x)",
          v22,
          (__int64)a5,
          v31,
          0,
          0);
        return (unsigned int)v31;
      }
    }
    v42 = 0;
    v32 = AugmentVidPnTopology(v47, v46, a5, v43, a2, v45, a7, a10, &v42, (unsigned int (*)[16])Src);
    v31 = v32;
    v33 = -1071774925;
    if ( v32 == -1071774925 )
    {
      WdLogSingleEntry2(7, a5, v22);
      WdLogGlobalForLineNumber = 4634;
      return v33;
    }
    v33 = -1071774886;
    if ( v32 == -1071774886 )
    {
      WdLogSingleEntry2(7, a5, v22);
      WdLogGlobalForLineNumber = 4641;
      return v33;
    }
    if ( v32 < 0 )
    {
      WdLogSingleEntry2(2, v22, v32);
      WdLogGlobalForLineNumber = 4648;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Failed to augment VidPN topology  on source 0x%I64x (status = 0x%I64x).",
        v22,
        v31,
        0,
        0,
        0);
      return (unsigned int)v31;
    }
    v34 = v42;
    if ( !v42 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 4655;
      DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"sztNumAugmentedPathsFromSource > 0", 4655, 0, 0, 0, 0);
    }
    v35 = v44;
    WdLogSingleEntry4(7, v44, v34);
    WdLogGlobalForLineNumber = 4658;
    v41 = v34;
  }
  else
  {
    v34 = v41;
    v35 = v44;
  }
  if ( !v34 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4665;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"sztNumPathsFromSource > 0", 4665, 0, 0, 0, 0);
    v34 = v41;
  }
  if ( a9 )
  {
    v36 = v47;
    v37 = UnpinCofuncModalityOnPathsFromSource(v47, v46, a5, v43, a7, v34);
    v38 = v37;
    if ( v37 < 0 )
    {
      WdLogSingleEntry5(2, v41, v22, v36, v35, v37);
      WdLogGlobalForLineNumber = 4681;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Failed to unpin modality of %I64d present path(s) originating from source 0x%I64x in VidPN 0x%I64x"
                       " of adapter 0x%I64x (status = 0x%I64x)",
        v41,
        v22,
        (__int64)v36,
        v35,
        v38);
      return (unsigned int)v38;
    }
    v34 = v41;
  }
  v39 = v49;
  *v48 = v34;
  if ( v39 )
    memmove(v39, Src, 0x40u);
  if ( v50 )
    *v50 = v21;
  return 0;
}

```

## disassembly

```asm
0x14022cf70  push    rbp
0x14022cf72  push    rbx
0x14022cf73  push    rsi
0x14022cf74  push    rdi
0x14022cf75  push    r12
0x14022cf77  push    r13
0x14022cf79  push    r14
0x14022cf7b  push    r15
0x14022cf7d  lea     rbp, [rsp-7]
0x14022cf82  sub     rsp, 0F8h
0x14022cf89  mov     rdi, [rbp+3Fh+arg_58]
0x14022cf90  mov     r12, r9
0x14022cf93  mov     r15, [rbp+3Fh+arg_28]
0x14022cf97  mov     r14, r8
0x14022cf9a  mov     r13, [rbp+3Fh+arg_50]
0x14022cfa1  mov     rbx, rdx
0x14022cfa4  mov     rax, [rbp+3Fh+arg_60]
0x14022cfab  mov     rsi, [rbp+3Fh+arg_20]
0x14022cfaf  mov     [rbp+3Fh+var_98], rdi
0x14022cfb3  mov     [rsp+130h+var_C8], r15
0x14022cfb8  mov     [rbp+3Fh+var_A0], r13
0x14022cfbc  mov     [rbp+3Fh+var_90], rax
0x14022cfc0  mov     [rbp+3Fh+var_B0], r9
0x14022cfc4  mov     [rbp+3Fh+var_A8], r8
0x14022cfc8  mov     [rsp+130h+var_C0], rdx
0x14022cfcd  mov     [rbp+3Fh+var_B8], rcx
0x14022cfd1  test    rcx, rcx
0x14022cfd4  jnz     short loc_14022D022
0x14022cfd6  mov     ecx, 1
0x14022cfdb  call    cs:__imp_WdLogSingleEntry0
0x14022cfe2  nop     dword ptr [rax+rax+00h]
0x14022cfe7  xor     ecx, ecx
0x14022cfe9  lea     r9, aIPdxgdmminterf; "i_pDxgDmmInterface != NULL"
0x14022cff0  mov     [rsp+130h+var_F0], rcx
0x14022cff5  mov     eax, 116Dh
0x14022cffa  mov     qword ptr [rsp+130h+var_F8], rcx
0x14022cfff  or      r8d, 0FFFFFFFFh
0x14022d003  mov     qword ptr [rsp+130h+var_100], rcx
0x14022d008  mov     edx, 40002h
0x14022d00d  mov     [rsp+130h+var_108], rcx
0x14022d012  mov     [rsp+130h+var_110], rax
0x14022d017  mov     cs:WdLogGlobalForLineNumber, eax
0x14022d01d  call    DxgkLogInternalTriageEvent
0x14022d022  test    rbx, rbx
0x14022d025  jnz     short loc_14022D071
0x14022d027  lea     ecx, [rbx+1]
0x14022d02a  call    cs:__imp_WdLogSingleEntry0
0x14022d031  nop     dword ptr [rax+rax+00h]
0x14022d036  xor     ecx, ecx
0x14022d038  lea     r9, aIHdxgadapterNu; "i_hDxgAdapter != NULL"
0x14022d03f  mov     [rsp+130h+var_F0], rcx
0x14022d044  mov     eax, 116Eh
0x14022d049  mov     qword ptr [rsp+130h+var_F8], rcx
0x14022d04e  or      r8d, 0FFFFFFFFh
0x14022d052  mov     qword ptr [rsp+130h+var_100], rcx
0x14022d057  mov     edx, 40002h
0x14022d05c  mov     [rsp+130h+var_108], rcx
0x14022d061  mov     [rsp+130h+var_110], rax
0x14022d066  mov     cs:WdLogGlobalForLineNumber, eax
0x14022d06c  call    DxgkLogInternalTriageEvent
0x14022d071  test    r14, r14
0x14022d074  jnz     short loc_14022D0C3
0x14022d076  lea     ecx, [r14+1]
0x14022d07a  call    cs:__imp_WdLogSingleEntry0
0x14022d081  nop     dword ptr [rax+rax+00h]
0x14022d086  mov     [rsp+130h+var_F0], r14
0x14022d08b  lea     r9, aIHvidpnNull; "i_hVidPn != NULL"
0x14022d092  mov     qword ptr [rsp+130h+var_F8], r14
0x14022d097  mov     eax, 116Fh
0x14022d09c  mov     qword ptr [rsp+130h+var_100], r14
0x14022d0a1  or      r8d, 0FFFFFFFFh
0x14022d0a5  mov     [rsp+130h+var_108], r14
0x14022d0aa  mov     edx, 40002h
0x14022d0af  xor     ecx, ecx
0x14022d0b1  mov     [rsp+130h+var_110], rax
0x14022d0b6  mov     cs:WdLogGlobalForLineNumber, eax
0x14022d0bc  call    DxgkLogInternalTriageEvent
0x14022d0c1  jmp     short loc_14022D0C6
0x14022d0c3  xor     r14d, r14d
0x14022d0c6  test    r12, r12
0x14022d0c9  jnz     short loc_14022D117
0x14022d0cb  lea     ecx, [r12+1]
0x14022d0d0  call    cs:__imp_WdLogSingleEntry0
0x14022d0d7  nop     dword ptr [rax+rax+00h]
0x14022d0dc  mov     [rsp+130h+var_F0], r14
0x14022d0e1  lea     r9, aIPdmmvidpninte; "i_pDmmVidPnInterface != NULL"
0x14022d0e8  mov     qword ptr [rsp+130h+var_F8], r14
0x14022d0ed  mov     eax, 1170h
0x14022d0f2  mov     qword ptr [rsp+130h+var_100], r14
0x14022d0f7  or      r8d, 0FFFFFFFFh
0x14022d0fb  mov     [rsp+130h+var_108], r14
0x14022d100  mov     edx, 40002h
0x14022d105  xor     ecx, ecx
0x14022d107  mov     [rsp+130h+var_110], rax
0x14022d10c  mov     cs:WdLogGlobalForLineNumber, eax
0x14022d112  call    DxgkLogInternalTriageEvent
0x14022d117  test    rsi, rsi
0x14022d11a  jnz     short loc_14022D166
0x14022d11c  lea     ecx, [rsi+1]
0x14022d11f  call    cs:__imp_WdLogSingleEntry0
0x14022d126  nop     dword ptr [rax+rax+00h]
0x14022d12b  mov     [rsp+130h+var_F0], r14
0x14022d130  lea     r9, aIHvidpntopolog; "i_hVidPnTopology != NULL"
0x14022d137  mov     qword ptr [rsp+130h+var_F8], r14
0x14022d13c  mov     eax, 1171h
0x14022d141  mov     qword ptr [rsp+130h+var_100], r14
0x14022d146  or      r8d, 0FFFFFFFFh
0x14022d14a  mov     [rsp+130h+var_108], r14
0x14022d14f  mov     edx, 40002h
0x14022d154  xor     ecx, ecx
0x14022d156  mov     [rsp+130h+var_110], rax
0x14022d15b  mov     cs:WdLogGlobalForLineNumber, eax
0x14022d161  call    DxgkLogInternalTriageEvent
0x14022d166  test    r15, r15
0x14022d169  jnz     short loc_14022D1B6
0x14022d16b  lea     ecx, [r15+1]
0x14022d16f  call    cs:__imp_WdLogSingleEntry0
0x14022d176  nop     dword ptr [rax+rax+00h]
0x14022d17b  mov     [rsp+130h+var_F0], r14
0x14022d180  lea     r9, aIPdmmvidpntopo; "i_pDmmVidPnTopologyInterface != NULL"
0x14022d187  mov     qword ptr [rsp+130h+var_F8], r14
0x14022d18c  mov     eax, 1172h
0x14022d191  mov     qword ptr [rsp+130h+var_100], r14
0x14022d196  or      r8d, 0FFFFFFFFh
0x14022d19a  mov     [rsp+130h+var_108], r14
0x14022d19f  mov     edx, 40002h
0x14022d1a4  xor     ecx, ecx
0x14022d1a6  mov     [rsp+130h+var_110], rax
0x14022d1ab  mov     cs:WdLogGlobalForLineNumber, eax
0x14022d1b1  call    DxgkLogInternalTriageEvent
0x14022d1b6  mov     r12d, [rbp+3Fh+arg_30]
0x14022d1ba  cmp     r12d, 0FFFFFFFFh
0x14022d1be  jnz     short loc_14022D20B
0x14022d1c0  mov     ecx, 1
0x14022d1c5  call    cs:__imp_WdLogSingleEntry0
0x14022d1cc  nop     dword ptr [rax+rax+00h]
0x14022d1d1  mov     [rsp+130h+var_F0], r14
0x14022d1d6  lea     r9, aIVidpnsourceid; "i_VidPnSourceId != D3DDDI_ID_UNINITIALI"...
0x14022d1dd  mov     qword ptr [rsp+130h+var_F8], r14
0x14022d1e2  mov     eax, 1173h
0x14022d1e7  mov     qword ptr [rsp+130h+var_100], r14
0x14022d1ec  or      r8d, r12d
0x14022d1ef  mov     [rsp+130h+var_108], r14
0x14022d1f4  mov     edx, 40002h
0x14022d1f9  xor     ecx, ecx
0x14022d1fb  mov     [rsp+130h+var_110], rax
0x14022d200  mov     cs:WdLogGlobalForLineNumber, eax
0x14022d206  call    DxgkLogInternalTriageEvent
0x14022d20b  test    r13, r13
0x14022d20e  jnz     short loc_14022D25B
0x14022d210  lea     ecx, [r13+1]
0x14022d214  call    cs:__imp_WdLogSingleEntry0
0x14022d21b  nop     dword ptr [rax+rax+00h]
0x14022d220  mov     [rsp+130h+var_F0], r14
0x14022d225  lea     r9, aOPnumvidpnpres; "o_pNumVidPnPresentPathsFromSource != NU"...
0x14022d22c  mov     qword ptr [rsp+130h+var_F8], r14
0x14022d231  mov     eax, 1174h
0x14022d236  mov     qword ptr [rsp+130h+var_100], r14
0x14022d23b  or      r8d, 0FFFFFFFFh
0x14022d23f  mov     [rsp+130h+var_108], r14
0x14022d244  mov     edx, 40002h
0x14022d249  xor     ecx, ecx
0x14022d24b  mov     [rsp+130h+var_110], rax
0x14022d250  mov     cs:WdLogGlobalForLineNumber, eax
0x14022d256  call    DxgkLogInternalTriageEvent
0x14022d25b  mov     [r13+0], r14
0x14022d25f  test    rdi, rdi
0x14022d262  jz      short loc_14022D27B
0x14022d264  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14022d26c  movups  xmmword ptr [rdi], xmm0
0x14022d26f  movups  xmmword ptr [rdi+10h], xmm0
0x14022d273  movups  xmmword ptr [rdi+20h], xmm0
0x14022d277  movups  xmmword ptr [rdi+30h], xmm0
0x14022d27b  mov     rax, [r15]
0x14022d27e  lea     r8, [rsp+130h+var_D8]
0x14022d283  mov     edx, r12d
0x14022d286  mov     [rsp+130h+var_D8], r14
0x14022d28b  mov     rcx, rsi
0x14022d28e  call    _guard_dispatch_icall
0x14022d293  movsxd  r14, eax
0x14022d296  cmp     r14d, 0C01E0339h
0x14022d29d  jnz     loc_14022D326
0x14022d2a3  xor     edi, edi
0x14022d2a5  cmp     [rsp+130h+var_D8], rdi
0x14022d2aa  jz      short loc_14022D2F6
0x14022d2ac  lea     ecx, [rdi+1]
0x14022d2af  call    cs:__imp_WdLogSingleEntry0
0x14022d2b6  nop     dword ptr [rax+rax+00h]
0x14022d2bb  mov     [rsp+130h+var_F0], rdi
0x14022d2c0  lea     r9, aSztnumpathsfro; "sztNumPathsFromSource == 0"
0x14022d2c7  mov     qword ptr [rsp+130h+var_F8], rdi
0x14022d2cc  mov     eax, 1193h
0x14022d2d1  mov     qword ptr [rsp+130h+var_100], rdi
0x14022d2d6  or      r8d, 0FFFFFFFFh
0x14022d2da  mov     [rsp+130h+var_108], rdi
0x14022d2df  mov     edx, 40002h
0x14022d2e4  xor     ecx, ecx
0x14022d2e6  mov     [rsp+130h+var_110], rax
0x14022d2eb  mov     cs:WdLogGlobalForLineNumber, eax
0x14022d2f1  call    DxgkLogInternalTriageEvent
0x14022d2f6  mov     r13b, 1
0x14022d2f9  mov     r14d, 7
0x14022d2ff  mov     r8, r12
0x14022d302  mov     ecx, r14d
0x14022d305  mov     rdx, rsi
0x14022d308  mov     rdi, r12
0x14022d30b  call    cs:__imp_WdLogSingleEntry2
0x14022d312  nop     dword ptr [rax+rax+00h]
0x14022d317  mov     cs:WdLogGlobalForLineNumber, 1199h
0x14022d321  jmp     loc_14022D56D
0x14022d326  xor     r13d, r13d
0x14022d329  test    eax, eax
0x14022d32b  jns     short loc_14022D388
0x14022d32d  mov     r9, r14
0x14022d330  lea     ecx, [r13+2]
0x14022d334  mov     r8, rsi
0x14022d337  mov     rdx, r12
0x14022d33a  call    cs:__imp_WdLogSingleEntry3
0x14022d341  nop     dword ptr [rax+rax+00h]
0x14022d346  mov     [rsp+130h+var_F0], r13
0x14022d34b  lea     r9, aFailedToDeterm_0; "Failed to determine number of paths ori"...
0x14022d352  mov     qword ptr [rsp+130h+var_F8], r13
0x14022d357  or      r8d, 0FFFFFFFFh
0x14022d35b  mov     qword ptr [rsp+130h+var_100], r14
0x14022d360  mov     edx, 40000h
0x14022d365  mov     [rsp+130h+var_108], rsi
0x14022d36a  xor     ecx, ecx
0x14022d36c  mov     [rsp+130h+var_110], r12
0x14022d371  mov     cs:WdLogGlobalForLineNumber, 11A1h
0x14022d37b  call    DxgkLogInternalTriageEvent
0x14022d380  mov     eax, r14d
0x14022d383  jmp     loc_14022D8F9
0x14022d388  mov     r15, r13
0x14022d38b  mov     r14d, 7
0x14022d391  cmp     r15, [rsp+130h+var_D8]
0x14022d396  jnb     loc_14022D546
0x14022d39c  mov     rax, [rsp+130h+var_C8]
0x14022d3a1  lea     r9, [rsp+130h+var_D0]
0x14022d3a6  or      edi, 0FFFFFFFFh
0x14022d3a9  mov     r8, r15
0x14022d3ac  mov     edx, r12d
0x14022d3af  mov     dword ptr [rsp+130h+var_D0], edi
0x14022d3b3  mov     rcx, rsi
0x14022d3b6  mov     rax, [rax+8]
0x14022d3ba  call    _guard_dispatch_icall
0x14022d3bf  movsxd  r13, eax
0x14022d3c2  test    eax, eax
0x14022d3c4  js      loc_14022D4E2
0x14022d3ca  mov     edx, dword ptr [rsp+130h+var_D0]
0x14022d3ce  cmp     edx, edi
0x14022d3d0  jnz     short loc_14022D425
0x14022d3d2  lea     ecx, [r14-6]
0x14022d3d6  call    cs:__imp_WdLogSingleEntry0
0x14022d3dd  nop     dword ptr [rax+rax+00h]
0x14022d3e2  xor     r13d, r13d
0x14022d3e5  lea     r9, aConnectedvidpn; "ConnectedVidPnTargetId != D3DDDI_ID_UNI"...
0x14022d3ec  mov     [rsp+130h+var_F0], r13
0x14022d3f1  mov     eax, 11BEh
0x14022d3f6  mov     qword ptr [rsp+130h+var_F8], r13
0x14022d3fb  mov     r8d, edi
0x14022d3fe  mov     qword ptr [rsp+130h+var_100], r13
0x14022d403  mov     edx, 40002h
0x14022d408  mov     [rsp+130h+var_108], r13
0x14022d40d  xor     ecx, ecx
0x14022d40f  mov     [rsp+130h+var_110], rax
0x14022d414  mov     cs:WdLogGlobalForLineNumber, eax
0x14022d41a  call    DxgkLogInternalTriageEvent
0x14022d41f  mov     edx, dword ptr [rsp+130h+var_D0]
0x14022d423  jmp     short loc_14022D428
0x14022d425  xor     r13d, r13d
0x14022d428  mov     rax, [rbp+3Fh+var_B8]
0x14022d42c  lea     r8, [rsp+130h+var_E0]
0x14022d431  mov     rcx, rbx
0x14022d434  mov     [rsp+130h+var_E0], r13b
0x14022d439  mov     rax, [rax+48h]
0x14022d43d  call    _guard_dispatch_icall
0x14022d442  movsxd  rdi, eax
0x14022d445  test    eax, eax
0x14022d447  js      short loc_14022D487
0x14022d449  cmp     [rsp+130h+var_E0], r13b
0x14022d44e  jz      short loc_14022D458
0x14022d450  inc     r15
0x14022d453  jmp     loc_14022D38B
0x14022d458  mov     r13b, 1
0x14022d45b  mov     r9d, dword ptr [rsp+130h+var_D0]
0x14022d460  mov     r8, r12
0x14022d463  mov     rdx, rsi
0x14022d466  mov     ecx, r14d
0x14022d469  mov     rdi, r12
0x14022d46c  call    cs:__imp_WdLogSingleEntry3
0x14022d473  nop     dword ptr [rax+rax+00h]
0x14022d478  mov     cs:WdLogGlobalForLineNumber, 11D8h
0x14022d482  jmp     loc_14022D549
0x14022d487  mov     r8, rdi
0x14022d48a  mov     rdx, rbx
0x14022d48d  mov     ecx, 2
0x14022d492  mov     r15, rbx
0x14022d495  call    cs:__imp_WdLogSingleEntry2
0x14022d49c  nop     dword ptr [rax+rax+00h]
0x14022d4a1  mov     [rsp+130h+var_F0], r13
  ... truncated ...
```
