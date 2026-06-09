# PrepareUnpinnedPathsFromSource(_DXGDMM_INTERFACE const * const,void * const,D3DKMDT_HVIDPN__ *,_DXGDMM_VIDPN_INTERFACE const *,D3DKMDT_HVIDPNTOPOLOGY__ *,_DXGDMM_VIDPNTOPOLOGY_INTERFACE const * const,uint,uchar,uchar,uchar,unsigned __int64 * const,uint (*)[16],uchar *)

- ea: `0x14022a910`
- end: `0x14022b2ae`
- name: `?PrepareUnpinnedPathsFromSource@@YAJQEBU_DXGDMM_INTERFACE@@QEAXPEAUD3DKMDT_HVIDPN__@@PEBU_DXGDMM_VIDPN_INTERFACE@@PEAUD3DKMDT_HVIDPNTOPOLOGY__@@QEBU_DXGDMM_VIDPNTOPOLOGY_INTERFACE@@IEEEQEA_KPEAY0BA@IPEAE@Z`
- size: `2462`
- prototype: `int(const struct _DXGDMM_INTERFACE *const, void *const, struct D3DKMDT_HVIDPN__ *, const struct _DXGDMM_VIDPN_INTERFACE *, struct D3DKMDT_HVIDPNTOPOLOGY__ *, const struct _DXGDMM_VIDPNTOPOLOGY_INTERFACE *const, unsigned int, unsigned __int8, unsigned __int8, unsigned __int8, unsigned __int64 *const, unsigned int (*)[16], unsigned __int8 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path`

## callers

- `0x1401b4f98`
- `0x1401db134`

## callees

- `0x14001b890`
- `0x1400a01e0`
- `0x1400a0240`
- `0x1401a40e8`
- `0x140229018`
- `0x14022a910`

## import_xrefs

- `watchdog!WdLogSingleEntry4` at `0x14022b147`
- `watchdog!WdLogSingleEntry4` at `0x14022b147`
- `watchdog!WdLogSingleEntry2` at `0x14022acab`
- `watchdog!WdLogSingleEntry2` at `0x14022ae35`
- `watchdog!WdLogSingleEntry2` at `0x14022aef2`
- `watchdog!WdLogSingleEntry2` at `0x14022af40`
- `watchdog!WdLogSingleEntry2` at `0x14022b046`
- `watchdog!WdLogSingleEntry2` at `0x14022b076`
- `watchdog!WdLogSingleEntry2` at `0x14022b09d`
- `watchdog!WdLogSingleEntry2` at `0x14022acab`
- `watchdog!WdLogSingleEntry2` at `0x14022ae35`
- `watchdog!WdLogSingleEntry2` at `0x14022aef2`
- `watchdog!WdLogSingleEntry2` at `0x14022af40`
- `watchdog!WdLogSingleEntry2` at `0x14022b046`
- `watchdog!WdLogSingleEntry2` at `0x14022b076`
- `watchdog!WdLogSingleEntry2` at `0x14022b09d`
- `watchdog!WdLogSingleEntry3` at `0x14022acda`
- `watchdog!WdLogSingleEntry3` at `0x14022ae0c`
- `watchdog!WdLogSingleEntry3` at `0x14022ae90`
- `watchdog!WdLogSingleEntry3` at `0x14022af8c`
- `watchdog!WdLogSingleEntry3` at `0x14022acda`
- `watchdog!WdLogSingleEntry3` at `0x14022ae0c`
- `watchdog!WdLogSingleEntry3` at `0x14022ae90`
- `watchdog!WdLogSingleEntry3` at `0x14022af8c`
- `watchdog!WdLogSingleEntry0` at `0x14022a97b`
- `watchdog!WdLogSingleEntry0` at `0x14022a9ca`
- `watchdog!WdLogSingleEntry0` at `0x14022aa1a`
- `watchdog!WdLogSingleEntry0` at `0x14022aa70`
- `watchdog!WdLogSingleEntry0` at `0x14022aabf`
- `watchdog!WdLogSingleEntry0` at `0x14022ab0f`
- `watchdog!WdLogSingleEntry0` at `0x14022ab65`
- `watchdog!WdLogSingleEntry0` at `0x14022abb4`
- `watchdog!WdLogSingleEntry0` at `0x14022ac4f`
- `watchdog!WdLogSingleEntry0` at `0x14022ad76`
- `watchdog!WdLogSingleEntry0` at `0x14022b0e5`
- `watchdog!WdLogSingleEntry0` at `0x14022b179`
- `watchdog!WdLogSingleEntry0` at `0x14022a97b`
- `watchdog!WdLogSingleEntry0` at `0x14022a9ca`
- `watchdog!WdLogSingleEntry0` at `0x14022aa1a`
- `watchdog!WdLogSingleEntry0` at `0x14022aa70`
- `watchdog!WdLogSingleEntry0` at `0x14022aabf`
- `watchdog!WdLogSingleEntry0` at `0x14022ab0f`
- `watchdog!WdLogSingleEntry0` at `0x14022ab65`
- `watchdog!WdLogSingleEntry0` at `0x14022abb4`
- `watchdog!WdLogSingleEntry0` at `0x14022ac4f`
- `watchdog!WdLogSingleEntry0` at `0x14022ad76`
- `watchdog!WdLogSingleEntry0` at `0x14022b0e5`
- `watchdog!WdLogSingleEntry0` at `0x14022b179`
- `watchdog!WdLogSingleEntry5` at `0x14022b218`
- `watchdog!WdLogSingleEntry5` at `0x14022b218`

## string_xrefs

- `0x14022aea5`: `Failed to enumerate target of %I64d'th path originating from source 0x%I64x (status = 0x%I64x)`
- `0x14022aceb`: `Failed to determine number of paths originating from source 0x%I64x in topology 0x%I64x (status = 0x%I64x)`
- `0x14022ac60`: `sztNumPathsFromSource == 0`
- `0x14022abc5`: `o_pNumVidPnPresentPathsFromSource != NULL`
- `0x14022afa1`: `Failed to remove all paths from source 0x%I64x in topology 0x%I64x (status = 0x%I64x)`
- `0x14022b0f6`: `sztNumAugmentedPathsFromSource > 0`
- `0x14022b229`: `Failed to unpin modality of %I64d present path(s) originating from source 0x%I64x in VidPN 0x%I64x of adapter 0x%I64x (status = 0x%I64x)`
- `0x14022b18a`: `sztNumPathsFromSource > 0`

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
    WdLogSingleEntry2(7, a5);
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
        WdLogSingleEntry2(2, a2);
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
    WdLogSingleEntry2(7, v22);
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
      WdLogSingleEntry2(7, v22);
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
      WdLogSingleEntry2(7, a5);
      WdLogGlobalForLineNumber = 4634;
      return v33;
    }
    v33 = -1071774886;
    if ( v32 == -1071774886 )
    {
      WdLogSingleEntry2(7, a5);
      WdLogGlobalForLineNumber = 4641;
      return v33;
    }
    if ( v32 < 0 )
    {
      WdLogSingleEntry2(2, v22);
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
    WdLogSingleEntry4(7, v44, v34, v22, v41);
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
0x14022a910  push    rbp
0x14022a912  push    rbx
0x14022a913  push    rsi
0x14022a914  push    rdi
0x14022a915  push    r12
0x14022a917  push    r13
0x14022a919  push    r14
0x14022a91b  push    r15
0x14022a91d  lea     rbp, [rsp-7]
0x14022a922  sub     rsp, 0F8h
0x14022a929  mov     rdi, [rbp+3Fh+arg_58]
0x14022a930  mov     r12, r9
0x14022a933  mov     r15, [rbp+3Fh+arg_28]
0x14022a937  mov     r14, r8
0x14022a93a  mov     r13, [rbp+3Fh+arg_50]
0x14022a941  mov     rbx, rdx
0x14022a944  mov     rax, [rbp+3Fh+arg_60]
0x14022a94b  mov     rsi, [rbp+3Fh+arg_20]
0x14022a94f  mov     [rbp+3Fh+var_98], rdi
0x14022a953  mov     [rsp+130h+var_C8], r15
0x14022a958  mov     [rbp+3Fh+var_A0], r13
0x14022a95c  mov     [rbp+3Fh+var_90], rax
0x14022a960  mov     [rbp+3Fh+var_B0], r9
0x14022a964  mov     [rbp+3Fh+var_A8], r8
0x14022a968  mov     [rsp+130h+var_C0], rdx
0x14022a96d  mov     [rbp+3Fh+var_B8], rcx
0x14022a971  test    rcx, rcx
0x14022a974  jnz     short loc_14022A9C2
0x14022a976  mov     ecx, 1
0x14022a97b  call    cs:__imp_WdLogSingleEntry0
0x14022a982  nop     dword ptr [rax+rax+00h]
0x14022a987  xor     ecx, ecx
0x14022a989  lea     r9, aIPdxgdmminterf; "i_pDxgDmmInterface != NULL"
0x14022a990  mov     [rsp+130h+var_F0], rcx
0x14022a995  mov     eax, 116Dh
0x14022a99a  mov     qword ptr [rsp+130h+var_F8], rcx
0x14022a99f  or      r8d, 0FFFFFFFFh
0x14022a9a3  mov     qword ptr [rsp+130h+var_100], rcx
0x14022a9a8  mov     edx, 40002h
0x14022a9ad  mov     [rsp+130h+var_108], rcx
0x14022a9b2  mov     [rsp+130h+var_110], rax
0x14022a9b7  mov     cs:WdLogGlobalForLineNumber, eax
0x14022a9bd  call    DxgkLogInternalTriageEvent
0x14022a9c2  test    rbx, rbx
0x14022a9c5  jnz     short loc_14022AA11
0x14022a9c7  lea     ecx, [rbx+1]
0x14022a9ca  call    cs:__imp_WdLogSingleEntry0
0x14022a9d1  nop     dword ptr [rax+rax+00h]
0x14022a9d6  xor     ecx, ecx
0x14022a9d8  lea     r9, aIHdxgadapterNu; "i_hDxgAdapter != NULL"
0x14022a9df  mov     [rsp+130h+var_F0], rcx
0x14022a9e4  mov     eax, 116Eh
0x14022a9e9  mov     qword ptr [rsp+130h+var_F8], rcx
0x14022a9ee  or      r8d, 0FFFFFFFFh
0x14022a9f2  mov     qword ptr [rsp+130h+var_100], rcx
0x14022a9f7  mov     edx, 40002h
0x14022a9fc  mov     [rsp+130h+var_108], rcx
0x14022aa01  mov     [rsp+130h+var_110], rax
0x14022aa06  mov     cs:WdLogGlobalForLineNumber, eax
0x14022aa0c  call    DxgkLogInternalTriageEvent
0x14022aa11  test    r14, r14
0x14022aa14  jnz     short loc_14022AA63
0x14022aa16  lea     ecx, [r14+1]
0x14022aa1a  call    cs:__imp_WdLogSingleEntry0
0x14022aa21  nop     dword ptr [rax+rax+00h]
0x14022aa26  mov     [rsp+130h+var_F0], r14
0x14022aa2b  lea     r9, aIHvidpnNull; "i_hVidPn != NULL"
0x14022aa32  mov     qword ptr [rsp+130h+var_F8], r14
0x14022aa37  mov     eax, 116Fh
0x14022aa3c  mov     qword ptr [rsp+130h+var_100], r14
0x14022aa41  or      r8d, 0FFFFFFFFh
0x14022aa45  mov     [rsp+130h+var_108], r14
0x14022aa4a  mov     edx, 40002h
0x14022aa4f  xor     ecx, ecx
0x14022aa51  mov     [rsp+130h+var_110], rax
0x14022aa56  mov     cs:WdLogGlobalForLineNumber, eax
0x14022aa5c  call    DxgkLogInternalTriageEvent
0x14022aa61  jmp     short loc_14022AA66
0x14022aa63  xor     r14d, r14d
0x14022aa66  test    r12, r12
0x14022aa69  jnz     short loc_14022AAB7
0x14022aa6b  lea     ecx, [r12+1]
0x14022aa70  call    cs:__imp_WdLogSingleEntry0
0x14022aa77  nop     dword ptr [rax+rax+00h]
0x14022aa7c  mov     [rsp+130h+var_F0], r14
0x14022aa81  lea     r9, aIPdmmvidpninte; "i_pDmmVidPnInterface != NULL"
0x14022aa88  mov     qword ptr [rsp+130h+var_F8], r14
0x14022aa8d  mov     eax, 1170h
0x14022aa92  mov     qword ptr [rsp+130h+var_100], r14
0x14022aa97  or      r8d, 0FFFFFFFFh
0x14022aa9b  mov     [rsp+130h+var_108], r14
0x14022aaa0  mov     edx, 40002h
0x14022aaa5  xor     ecx, ecx
0x14022aaa7  mov     [rsp+130h+var_110], rax
0x14022aaac  mov     cs:WdLogGlobalForLineNumber, eax
0x14022aab2  call    DxgkLogInternalTriageEvent
0x14022aab7  test    rsi, rsi
0x14022aaba  jnz     short loc_14022AB06
0x14022aabc  lea     ecx, [rsi+1]
0x14022aabf  call    cs:__imp_WdLogSingleEntry0
0x14022aac6  nop     dword ptr [rax+rax+00h]
0x14022aacb  mov     [rsp+130h+var_F0], r14
0x14022aad0  lea     r9, aIHvidpntopolog; "i_hVidPnTopology != NULL"
0x14022aad7  mov     qword ptr [rsp+130h+var_F8], r14
0x14022aadc  mov     eax, 1171h
0x14022aae1  mov     qword ptr [rsp+130h+var_100], r14
0x14022aae6  or      r8d, 0FFFFFFFFh
0x14022aaea  mov     [rsp+130h+var_108], r14
0x14022aaef  mov     edx, 40002h
0x14022aaf4  xor     ecx, ecx
0x14022aaf6  mov     [rsp+130h+var_110], rax
0x14022aafb  mov     cs:WdLogGlobalForLineNumber, eax
0x14022ab01  call    DxgkLogInternalTriageEvent
0x14022ab06  test    r15, r15
0x14022ab09  jnz     short loc_14022AB56
0x14022ab0b  lea     ecx, [r15+1]
0x14022ab0f  call    cs:__imp_WdLogSingleEntry0
0x14022ab16  nop     dword ptr [rax+rax+00h]
0x14022ab1b  mov     [rsp+130h+var_F0], r14
0x14022ab20  lea     r9, aIPdmmvidpntopo; "i_pDmmVidPnTopologyInterface != NULL"
0x14022ab27  mov     qword ptr [rsp+130h+var_F8], r14
0x14022ab2c  mov     eax, 1172h
0x14022ab31  mov     qword ptr [rsp+130h+var_100], r14
0x14022ab36  or      r8d, 0FFFFFFFFh
0x14022ab3a  mov     [rsp+130h+var_108], r14
0x14022ab3f  mov     edx, 40002h
0x14022ab44  xor     ecx, ecx
0x14022ab46  mov     [rsp+130h+var_110], rax
0x14022ab4b  mov     cs:WdLogGlobalForLineNumber, eax
0x14022ab51  call    DxgkLogInternalTriageEvent
0x14022ab56  mov     r12d, [rbp+3Fh+arg_30]
0x14022ab5a  cmp     r12d, 0FFFFFFFFh
0x14022ab5e  jnz     short loc_14022ABAB
0x14022ab60  mov     ecx, 1
0x14022ab65  call    cs:__imp_WdLogSingleEntry0
0x14022ab6c  nop     dword ptr [rax+rax+00h]
0x14022ab71  mov     [rsp+130h+var_F0], r14
0x14022ab76  lea     r9, aIVidpnsourceid; "i_VidPnSourceId != D3DDDI_ID_UNINITIALI"...
0x14022ab7d  mov     qword ptr [rsp+130h+var_F8], r14
0x14022ab82  mov     eax, 1173h
0x14022ab87  mov     qword ptr [rsp+130h+var_100], r14
0x14022ab8c  or      r8d, r12d
0x14022ab8f  mov     [rsp+130h+var_108], r14
0x14022ab94  mov     edx, 40002h
0x14022ab99  xor     ecx, ecx
0x14022ab9b  mov     [rsp+130h+var_110], rax
0x14022aba0  mov     cs:WdLogGlobalForLineNumber, eax
0x14022aba6  call    DxgkLogInternalTriageEvent
0x14022abab  test    r13, r13
0x14022abae  jnz     short loc_14022ABFB
0x14022abb0  lea     ecx, [r13+1]
0x14022abb4  call    cs:__imp_WdLogSingleEntry0
0x14022abbb  nop     dword ptr [rax+rax+00h]
0x14022abc0  mov     [rsp+130h+var_F0], r14
0x14022abc5  lea     r9, aOPnumvidpnpres; "o_pNumVidPnPresentPathsFromSource != NU"...
0x14022abcc  mov     qword ptr [rsp+130h+var_F8], r14
0x14022abd1  mov     eax, 1174h
0x14022abd6  mov     qword ptr [rsp+130h+var_100], r14
0x14022abdb  or      r8d, 0FFFFFFFFh
0x14022abdf  mov     [rsp+130h+var_108], r14
0x14022abe4  mov     edx, 40002h
0x14022abe9  xor     ecx, ecx
0x14022abeb  mov     [rsp+130h+var_110], rax
0x14022abf0  mov     cs:WdLogGlobalForLineNumber, eax
0x14022abf6  call    DxgkLogInternalTriageEvent
0x14022abfb  mov     [r13+0], r14
0x14022abff  test    rdi, rdi
0x14022ac02  jz      short loc_14022AC1B
0x14022ac04  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14022ac0c  movups  xmmword ptr [rdi], xmm0
0x14022ac0f  movups  xmmword ptr [rdi+10h], xmm0
0x14022ac13  movups  xmmword ptr [rdi+20h], xmm0
0x14022ac17  movups  xmmword ptr [rdi+30h], xmm0
0x14022ac1b  mov     rax, [r15]
0x14022ac1e  lea     r8, [rsp+130h+var_D8]
0x14022ac23  mov     edx, r12d
0x14022ac26  mov     [rsp+130h+var_D8], r14
0x14022ac2b  mov     rcx, rsi
0x14022ac2e  call    _guard_dispatch_icall
0x14022ac33  movsxd  r14, eax
0x14022ac36  cmp     r14d, 0C01E0339h
0x14022ac3d  jnz     loc_14022ACC6
0x14022ac43  xor     edi, edi
0x14022ac45  cmp     [rsp+130h+var_D8], rdi
0x14022ac4a  jz      short loc_14022AC96
0x14022ac4c  lea     ecx, [rdi+1]
0x14022ac4f  call    cs:__imp_WdLogSingleEntry0
0x14022ac56  nop     dword ptr [rax+rax+00h]
0x14022ac5b  mov     [rsp+130h+var_F0], rdi
0x14022ac60  lea     r9, aSztnumpathsfro; "sztNumPathsFromSource == 0"
0x14022ac67  mov     qword ptr [rsp+130h+var_F8], rdi
0x14022ac6c  mov     eax, 1193h
0x14022ac71  mov     qword ptr [rsp+130h+var_100], rdi
0x14022ac76  or      r8d, 0FFFFFFFFh
0x14022ac7a  mov     [rsp+130h+var_108], rdi
0x14022ac7f  mov     edx, 40002h
0x14022ac84  xor     ecx, ecx
0x14022ac86  mov     [rsp+130h+var_110], rax
0x14022ac8b  mov     cs:WdLogGlobalForLineNumber, eax
0x14022ac91  call    DxgkLogInternalTriageEvent
0x14022ac96  mov     r13b, 1
0x14022ac99  mov     r14d, 7
0x14022ac9f  mov     r8, r12
0x14022aca2  mov     ecx, r14d
0x14022aca5  mov     rdx, rsi
0x14022aca8  mov     rdi, r12
0x14022acab  call    cs:__imp_WdLogSingleEntry2
0x14022acb2  nop     dword ptr [rax+rax+00h]
0x14022acb7  mov     cs:WdLogGlobalForLineNumber, 1199h
0x14022acc1  jmp     loc_14022AF0D
0x14022acc6  xor     r13d, r13d
0x14022acc9  test    eax, eax
0x14022accb  jns     short loc_14022AD28
0x14022accd  mov     r9, r14
0x14022acd0  lea     ecx, [r13+2]
0x14022acd4  mov     r8, rsi
0x14022acd7  mov     rdx, r12
0x14022acda  call    cs:__imp_WdLogSingleEntry3
0x14022ace1  nop     dword ptr [rax+rax+00h]
0x14022ace6  mov     [rsp+130h+var_F0], r13
0x14022aceb  lea     r9, aFailedToDeterm_0; "Failed to determine number of paths ori"...
0x14022acf2  mov     qword ptr [rsp+130h+var_F8], r13
0x14022acf7  or      r8d, 0FFFFFFFFh
0x14022acfb  mov     qword ptr [rsp+130h+var_100], r14
0x14022ad00  mov     edx, 40000h
0x14022ad05  mov     [rsp+130h+var_108], rsi
0x14022ad0a  xor     ecx, ecx
0x14022ad0c  mov     [rsp+130h+var_110], r12
0x14022ad11  mov     cs:WdLogGlobalForLineNumber, 11A1h
0x14022ad1b  call    DxgkLogInternalTriageEvent
0x14022ad20  mov     eax, r14d
0x14022ad23  jmp     loc_14022B299
0x14022ad28  mov     r15, r13
0x14022ad2b  mov     r14d, 7
0x14022ad31  cmp     r15, [rsp+130h+var_D8]
0x14022ad36  jnb     loc_14022AEE6
0x14022ad3c  mov     rax, [rsp+130h+var_C8]
0x14022ad41  lea     r9, [rsp+130h+var_D0]
0x14022ad46  or      edi, 0FFFFFFFFh
0x14022ad49  mov     r8, r15
0x14022ad4c  mov     edx, r12d
0x14022ad4f  mov     dword ptr [rsp+130h+var_D0], edi
0x14022ad53  mov     rcx, rsi
0x14022ad56  mov     rax, [rax+8]
0x14022ad5a  call    _guard_dispatch_icall
0x14022ad5f  movsxd  r13, eax
0x14022ad62  test    eax, eax
0x14022ad64  js      loc_14022AE82
0x14022ad6a  mov     edx, dword ptr [rsp+130h+var_D0]
0x14022ad6e  cmp     edx, edi
0x14022ad70  jnz     short loc_14022ADC5
0x14022ad72  lea     ecx, [r14-6]
0x14022ad76  call    cs:__imp_WdLogSingleEntry0
0x14022ad7d  nop     dword ptr [rax+rax+00h]
0x14022ad82  xor     r13d, r13d
0x14022ad85  lea     r9, aConnectedvidpn; "ConnectedVidPnTargetId != D3DDDI_ID_UNI"...
0x14022ad8c  mov     [rsp+130h+var_F0], r13
0x14022ad91  mov     eax, 11BEh
0x14022ad96  mov     qword ptr [rsp+130h+var_F8], r13
0x14022ad9b  mov     r8d, edi
0x14022ad9e  mov     qword ptr [rsp+130h+var_100], r13
0x14022ada3  mov     edx, 40002h
0x14022ada8  mov     [rsp+130h+var_108], r13
0x14022adad  xor     ecx, ecx
0x14022adaf  mov     [rsp+130h+var_110], rax
0x14022adb4  mov     cs:WdLogGlobalForLineNumber, eax
0x14022adba  call    DxgkLogInternalTriageEvent
0x14022adbf  mov     edx, dword ptr [rsp+130h+var_D0]
0x14022adc3  jmp     short loc_14022ADC8
0x14022adc5  xor     r13d, r13d
0x14022adc8  mov     rax, [rbp+3Fh+var_B8]
0x14022adcc  lea     r8, [rsp+130h+var_E0]
0x14022add1  mov     rcx, rbx
0x14022add4  mov     [rsp+130h+var_E0], r13b
0x14022add9  mov     rax, [rax+48h]
0x14022addd  call    _guard_dispatch_icall
0x14022ade2  movsxd  rdi, eax
0x14022ade5  test    eax, eax
0x14022ade7  js      short loc_14022AE27
0x14022ade9  cmp     [rsp+130h+var_E0], r13b
0x14022adee  jz      short loc_14022ADF8
0x14022adf0  inc     r15
0x14022adf3  jmp     loc_14022AD2B
0x14022adf8  mov     r13b, 1
0x14022adfb  mov     r9d, dword ptr [rsp+130h+var_D0]
0x14022ae00  mov     r8, r12
0x14022ae03  mov     rdx, rsi
0x14022ae06  mov     ecx, r14d
0x14022ae09  mov     rdi, r12
0x14022ae0c  call    cs:__imp_WdLogSingleEntry3
0x14022ae13  nop     dword ptr [rax+rax+00h]
0x14022ae18  mov     cs:WdLogGlobalForLineNumber, 11D8h
0x14022ae22  jmp     loc_14022AEE9
0x14022ae27  mov     r8, rdi
0x14022ae2a  mov     rdx, rbx
0x14022ae2d  mov     ecx, 2
0x14022ae32  mov     r15, rbx
0x14022ae35  call    cs:__imp_WdLogSingleEntry2
0x14022ae3c  nop     dword ptr [rax+rax+00h]
0x14022ae41  mov     [rsp+130h+var_F0], r13
  ... truncated ...
```
