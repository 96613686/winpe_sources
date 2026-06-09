# SampDsEnumerateAccountNames

- ea: `0x1803fd680`
- end: `0x1803fde67`
- name: `SampDsEnumerateAccountNames`
- size: `2023`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x180010510`
- `0x18001e090`
- `0x18001ea60`
- `0x180030bd4`
- `0x1803aff80`
- `0x1803b0070`
- `0x1803b0860`
- `0x1803df7f4`
- `0x1803fcf18`
- `0x1803fd0e8`
- `0x1803fd194`
- `0x1803fd680`
- `0x1803fde70`
- `0x180412364`
- `0x18041dd10`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1803fda50`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1803fda5e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1803fda50`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1803fda5e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1803fd82b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1803fd82b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803fdb61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803fdb6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803fddee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803fde0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803fde26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803fde35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803fdb61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803fdb6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803fddee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803fde0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803fde26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803fde35`
- `ntdll!RtlValidSid` at `0x1803fd816`
- `ntdll!RtlValidSid` at `0x1803fd816`
- `ntdll!RtlLengthSid` at `0x1803fd963`
- `ntdll!RtlLengthSid` at `0x1803fd972`
- `ntdll!RtlLengthSid` at `0x1803fd963`
- `ntdll!RtlLengthSid` at `0x1803fd972`
- `SAMSRV!SampCreateFullSid` at `0x1803fd8f9`
- `SAMSRV!SampCreateFullSid` at `0x1803fd913`
- `SAMSRV!SampCreateFullSid` at `0x1803fd8f9`
- `SAMSRV!SampCreateFullSid` at `0x1803fd913`

## pseudocode

```c
__int64 __fastcall SampDsEnumerateAccountNames(
        __int64 a1,
        unsigned int a2,
        char a3,
        _DWORD *a4,
        _DWORD *a5,
        HLOCAL *a6,
        unsigned int a7,
        unsigned int a8,
        _DWORD *a9,
        char a10)
{
  int v13; // r14d
  __int64 v14; // rdi
  HLOCAL v15; // rax
  __int64 v16; // rcx
  int LastEntryRidAndAccountControl; // ebx
  unsigned int v18; // r15d
  int v19; // eax
  _DWORD *v20; // r14
  unsigned int *v21; // rax
  __int64 v22; // rdi
  ULONG v23; // eax
  PSID v24; // rsi
  ULONG v25; // ebx
  ULONG v26; // eax
  unsigned __int64 v27; // rdx
  int v28; // ebx
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // r9
  char v41; // si
  LPWSTR v42; // rdi
  LPWSTR v43; // r15
  __int64 v44; // r8
  __int64 v45; // r9
  BOOL v46; // ebx
  int v47; // eax
  unsigned int *v48; // r13
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // r15
  char v52; // di
  __int64 v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // r8
  __int64 v56; // r9
  const wchar_t *v57; // rbx
  __int64 v58; // r8
  __int64 v59; // r9
  BOOL v60; // esi
  unsigned int v61; // esi
  __int64 v62; // r8
  bool v63; // zf
  HLOCAL *v64; // rsi
  HLOCAL *v65; // rsi
  char *v67; // [rsp+30h] [rbp-D0h]
  int v68; // [rsp+38h] [rbp-C8h]
  char v69; // [rsp+70h] [rbp-90h] BYREF
  char v70; // [rsp+71h] [rbp-8Fh]
  char v71[4]; // [rsp+74h] [rbp-8Ch] BYREF
  _DWORD *v72; // [rsp+78h] [rbp-88h]
  char v73[4]; // [rsp+80h] [rbp-80h] BYREF
  int v74; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v75; // [rsp+88h] [rbp-78h]
  PSID v76; // [rsp+90h] [rbp-70h] BYREF
  PSID Sid; // [rsp+98h] [rbp-68h] BYREF
  int v78; // [rsp+A0h] [rbp-60h]
  int v79; // [rsp+A4h] [rbp-5Ch]
  LPWSTR StringSid; // [rsp+A8h] [rbp-58h] BYREF
  LPWSTR v81; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD *v82; // [rsp+B8h] [rbp-48h]
  __int64 v83; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v84; // [rsp+C8h] [rbp-38h]
  __int64 v85; // [rsp+D0h] [rbp-30h] BYREF
  HLOCAL *v86; // [rsp+D8h] [rbp-28h]
  unsigned int *v87; // [rsp+E0h] [rbp-20h]
  __int64 v88; // [rsp+E8h] [rbp-18h]
  _QWORD v89[2]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v90[2]; // [rsp+100h] [rbp+0h] BYREF
  int v91; // [rsp+110h] [rbp+10h] BYREF
  __int64 v92; // [rsp+118h] [rbp+18h]
  int v93; // [rsp+120h] [rbp+20h] BYREF
  __int64 v94; // [rsp+128h] [rbp+28h]
  _DWORD v95[4]; // [rsp+130h] [rbp+30h] BYREF
  int *v96; // [rsp+140h] [rbp+40h]
  int v97; // [rsp+148h] [rbp+48h]
  int v98; // [rsp+150h] [rbp+50h]
  int *v99; // [rsp+158h] [rbp+58h]
  _BYTE v100[40]; // [rsp+160h] [rbp+60h] BYREF
  HLOCAL hMem; // [rsp+188h] [rbp+88h]
  int v102; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v103; // [rsp+1E8h] [rbp+E8h]
  int v104; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v105; // [rsp+1F8h] [rbp+F8h]
  int v106; // [rsp+200h] [rbp+100h] BYREF
  __int64 v107; // [rsp+208h] [rbp+108h]
  _DWORD v108[4]; // [rsp+210h] [rbp+110h] BYREF
  int *v109; // [rsp+220h] [rbp+120h]
  int v110; // [rsp+228h] [rbp+128h]
  int v111; // [rsp+230h] [rbp+130h]
  int *v112; // [rsp+238h] [rbp+138h]
  int v113; // [rsp+240h] [rbp+140h]
  int v114; // [rsp+248h] [rbp+148h]
  int *v115; // [rsp+250h] [rbp+150h]

  v82 = a5;
  v72 = a9;
  v13 = 1;
  v70 = a3;
  v96 = &v91;
  v75 = a2;
  v99 = &v93;
  v88 = a1;
  v89[1] = v95;
  v86 = a6;
  v109 = &v102;
  v14 = 0;
  v91 = 0;
  v112 = &v104;
  v115 = &v106;
  v90[1] = v108;
  v92 = 0;
  v93 = 0;
  v94 = 0;
  v95[0] = 101;
  v95[2] = 1;
  v97 = 102;
  v98 = 1;
  v89[0] = 2;
  v102 = 0;
  v103 = 0;
  v104 = 0;
  v105 = 0;
  v106 = 0;
  v107 = 0;
  v108[0] = 105;
  v108[2] = 1;
  v110 = 1;
  v111 = 1;
  v113 = 107;
  v114 = 1;
  v90[0] = 3;
  v85 = 0;
  v83 = 0;
  v69 = 1;
  memset_0(v100, 0, 0x78u);
  *a6 = 0;
  *(_DWORD *)v73 = 0;
  *(_DWORD *)v71 = 0;
  v76 = 0;
  Sid = 0;
  v74 = 0;
  if ( !*(_DWORD *)(a1 + 4) || (v84 = a1 + 24, !RtlValidSid((PSID)(a1 + 24))) )
  {
    LastEntryRidAndAccountControl = -1073741811;
    goto LABEL_88;
  }
  v15 = LocalAlloc(0x40u, 0x10u);
  *a6 = v15;
  if ( v15 )
  {
    v18 = a7;
    if ( !a10 && a7 > 0x8400 )
      v18 = 33792;
    LOBYTE(v16) = a10;
    if ( v70 )
      v18 = 33792;
    LastEntryRidAndAccountControl = SampExtendedEnumerationAccessCheck(v16, &v69);
    v19 = 0;
    if ( LastEntryRidAndAccountControl < 0 )
      goto LABEL_88;
    if ( v69 || !*a4 )
    {
      LOBYTE(v19) = a2 != 4;
      v79 = v19 + 4;
      v21 = (unsigned int *)v89;
      if ( a2 == 4 )
        v21 = (unsigned int *)v90;
      v87 = v21;
      LastEntryRidAndAccountControl = SampBuildDsEnumerationFilter(a2, a8, v100, v73, v71);
      if ( LastEntryRidAndAccountControl < 0 )
        goto LABEL_88;
      v22 = v84;
      LastEntryRidAndAccountControl = SampCreateFullSid(v84, (unsigned int)(*a4 + 1), &v76);
      if ( LastEntryRidAndAccountControl < 0 )
        goto LABEL_88;
      LastEntryRidAndAccountControl = SampCreateFullSid(v22, 0xFFFFFFFFLL, &Sid);
      if ( LastEntryRidAndAccountControl < 0 )
        goto LABEL_88;
      LastEntryRidAndAccountControl = SampMaybeBeginDsTransaction(0);
      if ( LastEntryRidAndAccountControl < 0 )
        goto LABEL_88;
      if ( *a4 && a2 == 4 )
        *(_DWORD *)v73 = *v82;
      if ( !a10 )
        SampSetDsa(0);
      if ( !v70 )
      {
        v23 = RtlLengthSid(Sid);
        v24 = v76;
        v25 = v23;
        v26 = RtlLengthSid(v76);
        v68 = v25;
        v67 = v71;
        LastEntryRidAndAccountControl = SampSetIndexRanges(2, 4, v73, v26, v24, 4);
        if ( LastEntryRidAndAccountControl < 0 )
          goto LABEL_88;
      }
      v27 = v18 / 0x42uLL;
      v28 = v27 + 1;
      v78 = v27 + 1;
      if ( (unsigned int)THStateCheckForTraceOverride(v18, v27)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v30, v29)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v32, v31, v33, v34)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
      {
        StringSid = 0;
        v81 = 0;
        ConvertSidToStringSidW(v76, &StringSid);
        ConvertSidToStringSidW(Sid, &v81);
        if ( (unsigned int)THStateCheckForTraceOverride(v36, v35)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v38, v37)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(v38, v37, v39, v40)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
        {
          v41 = v71[0];
          v42 = v81;
          v43 = StringSid;
          *(_DWORD *)v71 = *a4;
          v46 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v38, v37)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier(v38, v37, v44, v45)
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13));
          if ( (unsigned int)THStateCheckForTraceOverride(v38, v37)
            || (v47 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)) != 0 )
          {
            v47 = 1;
          }
          WPP_SF_DDSDS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v47,
            v46,
            (int)v67,
            v68,
            v71[0],
            v73[0],
            (__int64)v43,
            v41,
            (__int64)v42);
          v28 = v78;
        }
        LocalFree(StringSid);
        LocalFree(v81);
      }
      v48 = v87;
      LastEntryRidAndAccountControl = SampDsDoSearch2(
                                        (unsigned int)&v83,
                                        0,
                                        v88,
                                        (unsigned int)v100,
                                        0,
                                        v79,
                                        (__int64)v87,
                                        v28,
                                        a10 != 0 ? 0 : 0xDBBA0,
                                        (__int64)&v83);
      if ( LastEntryRidAndAccountControl < 0 )
        goto LABEL_88;
      v51 = v83;
      if ( (*(_BYTE *)(v83 + 120) & 1) != 0 && *(_QWORD *)(v83 + 112) && v69 )
      {
        v52 = 1;
      }
      else
      {
        v52 = 0;
        *a4 = 0;
      }
      if ( (unsigned int)THStateCheckForTraceOverride(v50, v49)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v54, v53)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v54, v53, v55, v56)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
      {
        v57 = L"TRUE";
        if ( !v52 )
          v57 = L"FALSE";
        v60 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v54, v53)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier(v54, v53, v58, v59)
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13));
        if ( !(unsigned int)THStateCheckForTraceOverride(v54, v53)
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13) )
        {
          v13 = 0;
        }
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          521142844,
          4,
          13,
          v13,
          v60,
          11,
          &WPP_a999499ef26f32b73436668eb28f53bb_Traceguids,
          (__int64)v57);
      }
      v61 = v75;
      if ( v52 )
      {
        v62 = *v48;
        *(_DWORD *)v71 = 0;
        LastEntryRidAndAccountControl = SampGetLastEntryRidAndAccountControl(v51, v75, v62, v71, &v74);
        if ( LastEntryRidAndAccountControl < 0 )
          goto LABEL_88;
        if ( !*(_DWORD *)v71 )
        {
          LastEntryRidAndAccountControl = -1073741790;
          goto LABEL_88;
        }
        *a4 = *(_DWORD *)v71;
        if ( v61 == 4 )
        {
          if ( (v74 & 0x40) != 0 )
            *v82 = 805306370;
          else
            *v82 = ((v74 & 0x1C0) != 0) + 805306368;
        }
      }
      else
      {
        *a4 = 0;
      }
      v20 = v72;
      LOBYTE(v53) = v70;
      LastEntryRidAndAccountControl = SampPackDsEnumerationResults(v84, v53, v51, v61, *v48, a8, v72, &v85);
      if ( LastEntryRidAndAccountControl < 0 )
        goto LABEL_89;
      v63 = v52 == 0;
      v14 = v85;
      if ( !v63 )
        LastEntryRidAndAccountControl = 261;
    }
    else
    {
      v20 = v72;
      LastEntryRidAndAccountControl = 0;
      *v72 = 0;
    }
    v64 = v86;
    *(_DWORD *)*v86 = *v20;
    *((_QWORD *)*v64 + 1) = v14;
    goto LABEL_91;
  }
  LastEntryRidAndAccountControl = -1073741801;
LABEL_88:
  v20 = v72;
LABEL_89:
  v65 = v86;
  *a4 = 0;
  *v20 = 0;
  if ( *v65 )
  {
    LocalFree(*v65);
    *v65 = 0;
  }
LABEL_91:
  SampMaybeEndDsTransaction(3);
  LocalFree(hMem);
  hMem = 0;
  if ( v76 )
    LocalFree(v76);
  if ( Sid )
    LocalFree(Sid);
  return (unsigned int)LastEntryRidAndAccountControl;
}

```

## disassembly

```asm
0x1803fd680  mov     [rsp-8+arg_8], rbx
0x1803fd685  push    rbp
0x1803fd686  push    rsi
0x1803fd687  push    rdi
0x1803fd688  push    r12
0x1803fd68a  push    r13
0x1803fd68c  push    r14
0x1803fd68e  push    r15
0x1803fd690  lea     rbp, [rsp-170h]
0x1803fd698  sub     rsp, 270h
0x1803fd69f  mov     rax, cs:__security_cookie
0x1803fd6a6  xor     rax, rsp
0x1803fd6a9  mov     [rbp+1A0h+var_40], rax
0x1803fd6b0  mov     rax, [rbp+1A0h+arg_20]
0x1803fd6b7  xor     r13d, r13d
0x1803fd6ba  mov     rbx, [rbp+1A0h+arg_28]
0x1803fd6c1  mov     esi, edx
0x1803fd6c3  mov     [rbp+1A0h+var_1E8], rax
0x1803fd6c7  mov     r15, rcx
0x1803fd6ca  mov     rax, [rbp+1A0h+arg_40]
0x1803fd6d1  mov     r12, r9
0x1803fd6d4  mov     [rsp+2A0h+var_228], rax
0x1803fd6d9  lea     r14d, [r13+1]
0x1803fd6dd  lea     rax, [rbp+1A0h+var_190]
0x1803fd6e1  mov     [rsp+2A0h+var_22F], r8b
0x1803fd6e6  mov     [rbp+1A0h+var_160], rax
0x1803fd6ea  lea     r8d, [r13+78h]; Size
0x1803fd6ee  lea     rax, [rbp+1A0h+var_180]
0x1803fd6f2  mov     [rbp+1A0h+var_218], edx
0x1803fd6f5  mov     [rbp+1A0h+var_148], rax
0x1803fd6f9  xor     edx, edx; Val
0x1803fd6fb  lea     rax, [rbp+1A0h+var_170]
0x1803fd6ff  mov     [rbp+1A0h+var_1B8], rcx
0x1803fd703  mov     [rbp+1A0h+var_1A8], rax
0x1803fd707  lea     rcx, [rbp+1A0h+var_140]; void *
0x1803fd70b  lea     rax, [rbp+1A0h+var_C0]
0x1803fd712  mov     [rbp+1A0h+var_1C8], rbx
0x1803fd716  mov     [rbp+1A0h+var_80], rax
0x1803fd71d  mov     edi, r13d
0x1803fd720  lea     rax, [rbp+1A0h+var_B0]
0x1803fd727  mov     [rbp+1A0h+var_190], r13d
0x1803fd72b  mov     [rbp+1A0h+var_68], rax
0x1803fd732  lea     rax, [rbp+1A0h+var_A0]
0x1803fd739  mov     [rbp+1A0h+var_50], rax
0x1803fd740  lea     rax, [rbp+1A0h+var_90]
0x1803fd747  mov     [rbp+1A0h+var_198], rax
0x1803fd74b  mov     [rbp+1A0h+var_188], r13
0x1803fd74f  mov     [rbp+1A0h+var_180], r13d
0x1803fd753  mov     [rbp+1A0h+var_178], r13
0x1803fd757  mov     [rbp+1A0h+var_170], 65h ; 'e'
0x1803fd75e  mov     [rbp+1A0h+var_168], r14d
0x1803fd762  mov     [rbp+1A0h+var_158], 66h ; 'f'
0x1803fd769  mov     [rbp+1A0h+var_150], r14d
0x1803fd76d  mov     [rbp+1A0h+var_1B0], 2
0x1803fd775  mov     [rbp+1A0h+var_C0], r13d
0x1803fd77c  mov     [rbp+1A0h+var_B8], r13
0x1803fd783  mov     [rbp+1A0h+var_B0], r13d
0x1803fd78a  mov     [rbp+1A0h+var_A8], r13
0x1803fd791  mov     [rbp+1A0h+var_A0], r13d
0x1803fd798  mov     [rbp+1A0h+var_98], r13
0x1803fd79f  mov     [rbp+1A0h+var_90], 69h ; 'i'
0x1803fd7a9  mov     [rbp+1A0h+var_88], r14d
0x1803fd7b0  mov     [rbp+1A0h+var_78], r14d
0x1803fd7b7  mov     [rbp+1A0h+var_70], r14d
0x1803fd7be  mov     [rbp+1A0h+var_60], 6Bh ; 'k'
0x1803fd7c8  mov     [rbp+1A0h+var_58], r14d
0x1803fd7cf  mov     [rbp+1A0h+var_1A0], 3
0x1803fd7d7  mov     [rbp+1A0h+var_1D0], r13
0x1803fd7db  mov     [rbp+1A0h+var_1E0], r13
0x1803fd7df  mov     [rsp+2A0h+var_230], r14b
0x1803fd7e4  call    memset_0
0x1803fd7e9  mov     [rbx], r13
0x1803fd7ec  mov     dword ptr [rbp+1A0h+var_220], r13d
0x1803fd7f0  mov     dword ptr [rsp+2A0h+var_22C], r13d
0x1803fd7f5  mov     [rbp+1A0h+var_210], r13
0x1803fd7f9  mov     [rbp+1A0h+Sid], r13
0x1803fd7fd  mov     [rbp+1A0h+var_21C], r13d
0x1803fd801  cmp     [r15+4], r13d
0x1803fd805  jbe     loc_1803FDDC9
0x1803fd80b  lea     rax, [r15+18h]
0x1803fd80f  mov     rcx, rax; Sid
0x1803fd812  mov     [rbp+1A0h+var_1D8], rax
0x1803fd816  call    cs:__imp_RtlValidSid
0x1803fd81c  test    al, al
0x1803fd81e  jz      loc_1803FDDC9
0x1803fd824  lea     edx, [r13+10h]; uBytes
0x1803fd828  lea     ecx, [rdx+30h]; uFlags
0x1803fd82b  call    cs:__imp_LocalAlloc
0x1803fd831  mov     [rbx], rax
0x1803fd834  test    rax, rax
0x1803fd837  jnz     short loc_1803FD843
0x1803fd839  mov     ebx, 0C0000017h
0x1803fd83e  jmp     loc_1803FDDCE
0x1803fd843  mov     r13b, [rbp+1A0h+arg_48]
0x1803fd84a  mov     eax, 8400h
0x1803fd84f  mov     r15d, [rbp+1A0h+arg_30]
0x1803fd856  test    r13b, r13b
0x1803fd859  jnz     short loc_1803FD862
0x1803fd85b  cmp     r15d, eax
0x1803fd85e  cmova   r15d, eax
0x1803fd862  cmp     [rsp+2A0h+var_22F], dil
0x1803fd867  lea     rdx, [rsp+2A0h+var_230]
0x1803fd86c  mov     cl, r13b
0x1803fd86f  cmovnz  r15d, eax
0x1803fd873  call    SampExtendedEnumerationAccessCheck
0x1803fd878  mov     ebx, eax
0x1803fd87a  xor     eax, eax
0x1803fd87c  test    ebx, ebx
0x1803fd87e  js      loc_1803FDDCE
0x1803fd884  cmp     [rsp+2A0h+var_230], al
0x1803fd888  jnz     short loc_1803FD89F
0x1803fd88a  cmp     [r12], eax
0x1803fd88e  jz      short loc_1803FD89F
0x1803fd890  mov     r14, [rsp+2A0h+var_228]
0x1803fd895  mov     ebx, eax
0x1803fd897  mov     [r14], eax
0x1803fd89a  jmp     loc_1803FDDB4
0x1803fd89f  mov     edx, [rbp+1A0h+arg_38]
0x1803fd8a5  lea     rcx, [rbp+1A0h+var_1A0]
0x1803fd8a9  cmp     esi, 4
0x1803fd8ac  lea     r9, [rbp+1A0h+var_220]
0x1803fd8b0  lea     r8, [rbp+1A0h+var_140]
0x1803fd8b4  setnz   al
0x1803fd8b7  add     eax, 4
0x1803fd8ba  mov     [rbp+1A0h+var_1FC], eax
0x1803fd8bd  cmp     esi, 4
0x1803fd8c0  lea     rax, [rbp+1A0h+var_1B0]
0x1803fd8c4  cmovz   rax, rcx
0x1803fd8c8  mov     ecx, esi
0x1803fd8ca  mov     [rbp+1A0h+var_1C0], rax
0x1803fd8ce  lea     rax, [rsp+2A0h+var_22C]
0x1803fd8d3  mov     qword ptr [rsp+2A0h+var_280], rax
0x1803fd8d8  call    ?SampBuildDsEnumerationFilter@@YAJW4_SAMP_OBJECT_TYPE@@KPEAU_FILTER_V1@@PEAK2@Z; SampBuildDsEnumerationFilter(_SAMP_OBJECT_TYPE,ulong,_FILTER_V1 *,ulong *,ulong *)
0x1803fd8dd  mov     ebx, eax
0x1803fd8df  test    eax, eax
0x1803fd8e1  js      loc_1803FDDCE
0x1803fd8e7  mov     edx, [r12]
0x1803fd8eb  lea     r8, [rbp+1A0h+var_210]
0x1803fd8ef  mov     rdi, [rbp+1A0h+var_1D8]
0x1803fd8f3  add     edx, r14d
0x1803fd8f6  mov     rcx, rdi
0x1803fd8f9  call    cs:__imp_SampCreateFullSid
0x1803fd8ff  mov     ebx, eax
0x1803fd901  test    eax, eax
0x1803fd903  js      loc_1803FDDCE
0x1803fd909  lea     r8, [rbp+1A0h+Sid]
0x1803fd90d  or      edx, 0FFFFFFFFh
0x1803fd910  mov     rcx, rdi
0x1803fd913  call    cs:__imp_SampCreateFullSid
0x1803fd919  mov     ebx, eax
0x1803fd91b  test    eax, eax
0x1803fd91d  js      loc_1803FDDCE
0x1803fd923  xor     ecx, ecx
0x1803fd925  call    SampMaybeBeginDsTransaction
0x1803fd92a  mov     ebx, eax
0x1803fd92c  test    eax, eax
0x1803fd92e  js      loc_1803FDDCE
0x1803fd934  cmp     dword ptr [r12], 0
0x1803fd939  jz      short loc_1803FD949
0x1803fd93b  cmp     esi, 4
0x1803fd93e  jnz     short loc_1803FD949
0x1803fd940  mov     rax, [rbp+1A0h+var_1E8]
0x1803fd944  mov     eax, [rax]
0x1803fd946  mov     dword ptr [rbp+1A0h+var_220], eax
0x1803fd949  test    r13b, r13b
0x1803fd94c  jnz     short loc_1803FD955
0x1803fd94e  xor     ecx, ecx
0x1803fd950  call    SampSetDsa
0x1803fd955  cmp     [rsp+2A0h+var_22F], 0
0x1803fd95a  jnz     short loc_1803FD9C2
0x1803fd95c  mov     rdi, [rbp+1A0h+Sid]
0x1803fd960  mov     rcx, rdi; Sid
0x1803fd963  call    cs:__imp_RtlLengthSid
0x1803fd969  mov     rsi, [rbp+1A0h+var_210]
0x1803fd96d  mov     ebx, eax
0x1803fd96f  mov     rcx, rsi; Sid
0x1803fd972  call    cs:__imp_RtlLengthSid
0x1803fd978  mov     dword ptr [rsp+2A0h+var_258], 0
0x1803fd980  lea     rdx, [rsp+2A0h+var_22C]
0x1803fd985  mov     qword ptr [rsp+2A0h+var_260], rdi
0x1803fd98a  lea     r8, [rbp+1A0h+var_220]
0x1803fd98e  mov     dword ptr [rsp+2A0h+var_268], ebx
0x1803fd992  mov     r9d, eax
0x1803fd995  mov     qword ptr [rsp+2A0h+var_270], rdx
0x1803fd99a  mov     [rsp+2A0h+var_278], 4
0x1803fd9a2  mov     qword ptr [rsp+2A0h+var_280], rsi
0x1803fd9a7  mov     esi, 4
0x1803fd9ac  mov     edx, esi
0x1803fd9ae  lea     ecx, [rsi-2]
0x1803fd9b1  call    SampSetIndexRanges
0x1803fd9b6  mov     ebx, eax
0x1803fd9b8  test    eax, eax
0x1803fd9ba  js      loc_1803FDDCE
0x1803fd9c0  jmp     short loc_1803FD9C7
0x1803fd9c2  mov     esi, 4
0x1803fd9c7  mov     ecx, r15d
0x1803fd9ca  mov     rax, 0F83E0F83E0F83E1h
0x1803fd9d4  mul     rcx
0x1803fd9d7  shr     rdx, 2
0x1803fd9db  lea     ebx, [rdx+1]
0x1803fd9de  mov     [rbp+1A0h+var_200], ebx
0x1803fd9e1  call    THStateCheckForTraceOverride
0x1803fd9e6  mov     edi, 0Dh
0x1803fd9eb  test    eax, eax
0x1803fd9ed  jnz     short loc_1803FDA38
0x1803fd9ef  mov     r8d, edi
0x1803fd9f2  mov     edx, esi
0x1803fd9f4  xor     ecx, ecx
0x1803fd9f6  call    CheckWPPLevelFlagsEnabledForProvider
0x1803fd9fb  test    eax, eax
0x1803fd9fd  jnz     short loc_1803FDA38
0x1803fd9ff  mov     eax, cs:gfTraceToSecondProvider
0x1803fda05  test    eax, eax
0x1803fda07  jz      loc_1803FDB71
0x1803fda0d  call    THStateCheckForTraceOverride
0x1803fda12  test    eax, eax
0x1803fda14  jnz     short loc_1803FDA38
0x1803fda16  call    ThStateCheckIfTraceToSecondProvier
0x1803fda1b  test    eax, eax
0x1803fda1d  jz      loc_1803FDB71
0x1803fda23  mov     r8d, edi
0x1803fda26  mov     edx, esi
0x1803fda28  mov     ecx, r14d
0x1803fda2b  call    CheckWPPLevelFlagsEnabledForProvider
0x1803fda30  test    eax, eax
0x1803fda32  jz      loc_1803FDB71
0x1803fda38  mov     rcx, [rbp+1A0h+var_210]; Sid
0x1803fda3c  lea     rdx, [rbp+1A0h+StringSid]; StringSid
0x1803fda40  mov     [rbp+1A0h+StringSid], 0
0x1803fda48  mov     [rbp+1A0h+var_1F0], 0
0x1803fda50  call    cs:__imp_ConvertSidToStringSidW
0x1803fda56  mov     rcx, [rbp+1A0h+Sid]; Sid
0x1803fda5a  lea     rdx, [rbp+1A0h+var_1F0]; StringSid
0x1803fda5e  call    cs:__imp_ConvertSidToStringSidW
0x1803fda64  call    THStateCheckForTraceOverride
0x1803fda69  test    eax, eax
0x1803fda6b  jnz     short loc_1803FDAB6
0x1803fda6d  mov     r8d, edi
0x1803fda70  mov     edx, esi
0x1803fda72  xor     ecx, ecx
0x1803fda74  call    CheckWPPLevelFlagsEnabledForProvider
0x1803fda79  test    eax, eax
0x1803fda7b  jnz     short loc_1803FDAB6
0x1803fda7d  mov     eax, cs:gfTraceToSecondProvider
0x1803fda83  test    eax, eax
0x1803fda85  jz      loc_1803FDB5D
0x1803fda8b  call    THStateCheckForTraceOverride
0x1803fda90  test    eax, eax
0x1803fda92  jnz     short loc_1803FDAB6
0x1803fda94  call    ThStateCheckIfTraceToSecondProvier
0x1803fda99  test    eax, eax
0x1803fda9b  jz      loc_1803FDB5D
0x1803fdaa1  mov     r8d, edi
0x1803fdaa4  mov     edx, esi
0x1803fdaa6  mov     ecx, r14d
0x1803fdaa9  call    CheckWPPLevelFlagsEnabledForProvider
0x1803fdaae  test    eax, eax
0x1803fdab0  jz      loc_1803FDB5D
0x1803fdab6  mov     eax, [r12]
0x1803fdaba  mov     esi, dword ptr [rsp+2A0h+var_22C]
0x1803fdabe  mov     rdi, [rbp+1A0h+var_1F0]
0x1803fdac2  mov     r15, [rbp+1A0h+StringSid]
0x1803fdac6  mov     dword ptr [rsp+2A0h+var_22C], eax
0x1803fdaca  mov     eax, cs:gfTraceToSecondProvider
0x1803fdad0  test    eax, eax
0x1803fdad2  jz      short loc_1803FDB00
0x1803fdad4  call    THStateCheckForTraceOverride
0x1803fdad9  test    eax, eax
0x1803fdadb  jnz     short loc_1803FDAFB
0x1803fdadd  call    ThStateCheckIfTraceToSecondProvier
0x1803fdae2  test    eax, eax
0x1803fdae4  jz      short loc_1803FDB00
0x1803fdae6  mov     edx, 4
0x1803fdaeb  mov     ecx, r14d
0x1803fdaee  lea     r8d, [rdx+9]
0x1803fdaf2  call    CheckWPPLevelFlagsEnabledForProvider
0x1803fdaf7  test    eax, eax
0x1803fdaf9  jz      short loc_1803FDB00
0x1803fdafb  mov     ebx, r14d
0x1803fdafe  jmp     short loc_1803FDB02
0x1803fdb00  xor     ebx, ebx
0x1803fdb02  call    THStateCheckForTraceOverride
0x1803fdb07  test    eax, eax
0x1803fdb09  jnz     short loc_1803FDB1D
0x1803fdb0b  lea     edx, [rax+4]
0x1803fdb0e  xor     ecx, ecx
0x1803fdb10  lea     r8d, [rax+0Dh]
0x1803fdb14  call    CheckWPPLevelFlagsEnabledForProvider
0x1803fdb19  test    eax, eax
0x1803fdb1b  jz      short loc_1803FDB20
0x1803fdb1d  mov     eax, r14d
0x1803fdb20  mov     ecx, dword ptr [rbp+1A0h+var_220]
0x1803fdb23  mov     [rsp+2A0h+var_240], rdi; __int64
0x1803fdb28  mov     dword ptr [rsp+2A0h+var_248], esi; char
0x1803fdb2c  mov     [rsp+2A0h+var_250], r15; __int64
0x1803fdb31  mov     dword ptr [rsp+2A0h+var_258], ecx; char
0x1803fdb35  mov     ecx, dword ptr [rsp+2A0h+var_22C]
0x1803fdb39  mov     dword ptr [rsp+2A0h+var_260], ecx; char
0x1803fdb3d  mov     rcx, cs:WPP_GLOBAL_Control
0x1803fdb44  mov     [rsp+2A0h+var_278], ebx; int
  ... truncated ...
```
