# SampDsQueryDisplayInformation

- ea: `0x180408d10`
- end: `0x180409663`
- name: `SampDsQueryDisplayInformation`
- size: `2387`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation`

## callees

- `0x18001e090`
- `0x18001ea60`
- `0x1803aff80`
- `0x1803b0070`
- `0x1803b0860`
- `0x1803b5f10`
- `0x1803de50c`
- `0x1803df7f4`
- `0x180407f0c`
- `0x1804081b4`
- `0x1804082a0`
- `0x1804082cc`
- `0x180408d10`
- `0x180412364`
- `0x18041d700`
- `0x18041dd10`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180408f4e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180409028`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180409077`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1804090d6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18040912c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180409194`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180408f4e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180409028`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180409077`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1804090d6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18040912c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180409194`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1804091cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18040925c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1804091cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18040925c`
- `SAMSRV!SampIncrementActiveThreads` at `0x18040932b`
- `SAMSRV!SampIncrementActiveThreads` at `0x18040932b`
- `SAMSRV!SampDecrementActiveThreads` at `0x180408f96`
- `SAMSRV!SampDecrementActiveThreads` at `0x180409583`
- `SAMSRV!SampDecrementActiveThreads` at `0x180408f96`
- `SAMSRV!SampDecrementActiveThreads` at `0x180409583`
- `SAMSRV!SampAcquireReadLock` at `0x180408fa1`
- `SAMSRV!SampAcquireReadLock` at `0x180409589`
- `SAMSRV!SampAcquireReadLock` at `0x180408fa1`
- `SAMSRV!SampAcquireReadLock` at `0x180409589`
- `SAMSRV!SampReleaseReadLock` at `0x180409320`
- `SAMSRV!SampReleaseReadLock` at `0x180409320`
- `SAMSRV!SamDsExtFree` at `0x180408faf`
- `SAMSRV!SamDsExtFree` at `0x18040923e`
- `SAMSRV!SamDsExtFree` at `0x180408faf`
- `SAMSRV!SamDsExtFree` at `0x18040923e`

## pseudocode

```c
__int64 __fastcall SampDsQueryDisplayInformation(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        _DWORD *a6,
        _DWORD *a7,
        int *a8)
{
  void *v11; // r12
  HLOCAL v13; // rax
  int active; // ebx
  char v15; // di
  HLOCAL v16; // rax
  HLOCAL v17; // rax
  HLOCAL v18; // rax
  _QWORD *v19; // rax
  HLOCAL v20; // rax
  HLOCAL v21; // rax
  unsigned int v22; // ebx
  void *v23; // rcx
  int v24; // r15d
  int v25; // eax
  int v26; // eax
  int v27; // eax
  __int64 v28; // r8
  char v29; // r14
  int QDIRestart; // eax
  _DWORD *v31; // rcx
  int v32; // eax
  int v33; // edx
  __int64 v34; // rcx
  _DWORD *v35; // rbx
  int v36; // eax
  unsigned int v37; // r14d
  __int64 v38; // rcx
  char v39; // r13
  __int64 v40; // r13
  unsigned int v41; // r9d
  unsigned int v42; // edx
  int v43; // r8d
  int v44; // [rsp+38h] [rbp-C8h]
  __int64 v45; // [rsp+40h] [rbp-C0h]
  int v46; // [rsp+40h] [rbp-C0h]
  int v47; // [rsp+48h] [rbp-B8h]
  char v48; // [rsp+50h] [rbp-B0h]
  char v49; // [rsp+51h] [rbp-AFh] BYREF
  char v50; // [rsp+52h] [rbp-AEh]
  char v51; // [rsp+53h] [rbp-ADh]
  char v52; // [rsp+54h] [rbp-ACh]
  int v53; // [rsp+58h] [rbp-A8h]
  int v54; // [rsp+5Ch] [rbp-A4h] BYREF
  int v55; // [rsp+60h] [rbp-A0h]
  int v56; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v57; // [rsp+68h] [rbp-98h]
  int v58; // [rsp+6Ch] [rbp-94h]
  unsigned int v59; // [rsp+70h] [rbp-90h]
  void *v60; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v61; // [rsp+80h] [rbp-80h]
  void *Src; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v63; // [rsp+90h] [rbp-70h]
  unsigned int v64; // [rsp+98h] [rbp-68h]
  _DWORD *v65; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v66[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v67; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v68[2]; // [rsp+C0h] [rbp-40h] BYREF
  _DWORD *v69; // [rsp+D0h] [rbp-30h]
  int v70; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v71; // [rsp+E0h] [rbp-20h]
  int v72; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v73; // [rsp+F0h] [rbp-10h]
  _DWORD v74[4]; // [rsp+F8h] [rbp-8h] BYREF
  int *v75; // [rsp+108h] [rbp+8h]
  int v76; // [rsp+110h] [rbp+10h]
  int v77; // [rsp+118h] [rbp+18h]
  int *v78; // [rsp+120h] [rbp+20h]
  _BYTE v79[128]; // [rsp+130h] [rbp+30h] BYREF
  int v80; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v81; // [rsp+1B8h] [rbp+B8h]
  int v82; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v83; // [rsp+1C8h] [rbp+C8h]
  int v84; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v85; // [rsp+1D8h] [rbp+D8h]
  int v86; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v87; // [rsp+1E8h] [rbp+E8h]
  int v88; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v89; // [rsp+1F8h] [rbp+F8h]
  _DWORD v90[4]; // [rsp+200h] [rbp+100h] BYREF
  int *v91; // [rsp+210h] [rbp+110h]
  int v92; // [rsp+218h] [rbp+118h]
  int v93; // [rsp+220h] [rbp+120h]
  int *v94; // [rsp+228h] [rbp+128h]
  int v95; // [rsp+230h] [rbp+130h]
  int v96; // [rsp+238h] [rbp+138h]
  int *v97; // [rsp+240h] [rbp+140h]
  int v98; // [rsp+248h] [rbp+148h]
  int v99; // [rsp+250h] [rbp+150h]
  int *v100; // [rsp+258h] [rbp+158h]
  int v101; // [rsp+260h] [rbp+160h]
  int v102; // [rsp+268h] [rbp+168h]
  int *v103; // [rsp+270h] [rbp+170h]

  v65 = a6;
  v57 = a3;
  v59 = a2;
  v69 = a7;
  v64 = 1;
  memset_0(v79, 0, 0x78u);
  v90[0] = 107;
  v50 = 0;
  v48 = 0;
  v91 = &v80;
  v11 = 0;
  v80 = 0;
  v94 = &v82;
  v97 = &v84;
  v100 = &v86;
  v103 = &v88;
  v66[1] = v90;
  v75 = &v70;
  v78 = &v72;
  v68[1] = v74;
  v81 = 0;
  v82 = 0;
  if ( a4 > a5 >> 5 )
    a4 = a5 >> 5;
  v83 = 0;
  v84 = 0;
  v85 = 0;
  v86 = 0;
  v87 = 0;
  v88 = 0;
  v89 = 0;
  v90[2] = 1;
  v92 = 126;
  v93 = 1;
  v95 = 1;
  v96 = 1;
  v98 = 3;
  v99 = 1;
  v55 = 2;
  v101 = 2;
  v102 = 1;
  v66[0] = 5;
  v70 = 0;
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v74[0] = 1;
  v74[2] = 1;
  v76 = 2;
  v77 = 1;
  v68[0] = 2;
  v60 = 0;
  v67 = 0;
  v49 = 1;
  if ( a4 <= 0x64 )
  {
    if ( !a4 )
      a4 = 1;
  }
  else
  {
    a4 = 100;
  }
  v61 = a4;
  switch ( a2 )
  {
    case 1u:
      v55 = 4;
      v54 = 805306368;
      v53 = 805306368;
      v63 = v66;
      if ( !*((_QWORD *)a8 + 1) )
      {
        v21 = LocalAlloc(0x40u, (unsigned __int64)a4 << 6);
        *((_QWORD *)a8 + 1) = v21;
        if ( !v21 )
          goto LABEL_16;
        memset_0(v21, 0, (unsigned __int64)a4 << 6);
        *a8 = 0;
      }
      goto LABEL_49;
    case 2u:
      v54 = 805306369;
      v53 = 805306369;
      if ( !*((_QWORD *)a8 + 1) )
      {
        v20 = LocalAlloc(0x40u, 48LL * a4);
        *((_QWORD *)a8 + 1) = v20;
        if ( !v20 )
          goto LABEL_16;
        memset_0(v20, 0, 48LL * a4);
        *a8 = 0;
      }
      goto LABEL_44;
    case 3u:
      v54 = 0x10000000;
      v53 = 0x10000000;
      if ( !*((_QWORD *)a8 + 1) )
      {
        v18 = LocalAlloc(0x40u, 48LL * a4);
        *((_QWORD *)a8 + 1) = v18;
        if ( !v18 )
          goto LABEL_16;
        *a8 = 0;
        memset_0(v18, 0, 48LL * a4);
      }
      v55 = 2;
LABEL_40:
      v19 = v68;
LABEL_45:
      v63 = v19;
      goto LABEL_49;
    case 4u:
      v54 = 805306368;
      v53 = 805306368;
      if ( !*((_QWORD *)a8 + 1) )
      {
        v17 = LocalAlloc(0x40u, 24LL * a4);
        *((_QWORD *)a8 + 1) = v17;
        if ( !v17 )
          goto LABEL_16;
        memset_0(v17, 0, 24LL * a4);
        *a8 = 0;
      }
      v55 = 4;
      v63 = v66;
LABEL_49:
      v22 = v57;
      v23 = *(void **)(a1 + 256);
      if ( !v57 )
      {
        if ( v23 )
          LocalFree(v23);
        *(_QWORD *)(a1 + 256) = 0;
        v24 = 0;
        *(_QWORD *)(a1 + 272) = 0;
        *(_DWORD *)(a1 + 264) = a2;
        v51 = 1;
LABEL_75:
        v31 = v65;
        *v65 = 0;
        v32 = *(_DWORD *)(a1 + 268);
        if ( v32 )
          *v31 = v32;
        if ( v61 > 0x64 )
          a4 = 100;
        SampReleaseReadLock();
        v50 = 1;
        active = SampIncrementActiveThreads();
        if ( active < 0 )
          goto LABEL_17;
        v35 = v65;
        v29 = 1;
        v58 = 0;
        v48 = 1;
        if ( !*v65 )
        {
          v56 = 0;
          LODWORD(Src) = 0;
          LODWORD(v65) = 0;
          LOBYTE(v33) = 1;
          *v35 = 0;
          if ( (int)SampDsRetrieveAccountCounts(a1, v33, (unsigned int)&v56, (unsigned int)&Src, (__int64)&v65) >= 0
            && v59 == 1 )
          {
            v36 = 32 * v56;
            *v35 = 32 * v56;
            *(_DWORD *)(a1 + 268) = v36;
          }
          SampMaybeEndDsTransaction(3);
        }
        LOBYTE(v34) = (*(_BYTE *)(a1 + 20) & 0x20) != 0;
        active = SampExtendedEnumerationAccessCheck(v34, &v49);
        if ( active < 0 )
          goto LABEL_17;
        while ( a4 && v29 )
        {
          v56 = 0;
          active = SampMaybeBeginDsTransaction(0);
          if ( active < 0 )
            goto LABEL_17;
          v37 = v59;
          active = SampDsBuildQDIFilter(v59, v79);
          if ( active < 0 )
            goto LABEL_17;
          v47 = 1;
          v45 = 0;
          v44 = 0;
          active = SampSetIndexRanges(v64, 4, &v54, 0, 0, 4);
          if ( active < 0 )
            goto LABEL_17;
          if ( (*(_BYTE *)(a1 + 20) & 0x20) == 0 )
            SampSetDsa(0);
          if ( v51 || (v52 = 0, v49) )
          {
            v46 = (*(_BYTE *)(a1 + 20) & 0x20) != 0 ? 0 : 0xEA60;
            active = SampDsDoSearch2(
                       v46,
                       (_DWORD)v11,
                       *(_QWORD *)(a1 + 176),
                       (unsigned int)v79,
                       v24,
                       v55,
                       (__int64)v63,
                       a4,
                       v46,
                       (__int64)&v67);
            v39 = 1;
          }
          else
          {
            v39 = v52;
          }
          LOBYTE(v38) = 1;
          SampSetDsa(v38);
          if ( active < 0 )
            goto LABEL_17;
          SampDsFreeQDIFilter((struct _FILTER_V1 *)v79);
          if ( !v39 )
            goto LABEL_105;
          v40 = v67;
          if ( !*(_DWORD *)(v67 + 16) )
            goto LABEL_105;
          active = SampDsPackQDI(v67, v37, *(unsigned int *)(a1 + 200), v58 + v57, a8, &v60, &v56, v44, v45, v47);
          if ( active < 0 )
            goto LABEL_110;
          v11 = v60;
          if ( *(_DWORD *)(v40 + 16) && v60 && v49 )
            v29 = 1;
          else
LABEL_105:
            v29 = 0;
          active = SampMaybeEndDsTransaction(3);
          if ( active < 0 )
            goto LABEL_17;
          a4 = v61 - (v56 + v58);
          v58 += v56;
          if ( a4 > 0x64 )
            a4 = 100;
        }
        SampDecrementActiveThreads();
        SampAcquireReadLock();
        v41 = v59;
        v42 = 0;
        switch ( v59 )
        {
          case 1u:
            v43 = *a8;
            if ( *a8 )
              v42 = *(_DWORD *)(((unsigned __int64)(unsigned int)(v43 - 1) << 6) + *((_QWORD *)a8 + 1));
            break;
          case 2u:
          case 3u:
            goto LABEL_120;
          case 4u:
          case 5u:
            v43 = *a8;
            if ( *a8 )
              v42 = *(_DWORD *)(*((_QWORD *)a8 + 1) + 24LL * (unsigned int)(v43 - 1));
            break;
          case 6u:
LABEL_120:
            v43 = *a8;
            if ( *a8 )
              v42 = *(_DWORD *)(*((_QWORD *)a8 + 1) + 48LL * (unsigned int)(v43 - 1));
            break;
          default:
            v43 = 0;
            break;
        }
        *(_DWORD *)(a1 + 272) += v43;
        *(_QWORD *)(a1 + 256) = v11;
        v11 = 0;
        *(_DWORD *)(a1 + 264) = v41;
        if ( !v43 )
          v42 = v57;
        v24 = v58;
        *(_DWORD *)(a1 + 276) = v42;
        goto LABEL_127;
      }
      v25 = *(_DWORD *)(a1 + 264);
      v24 = 0;
      v51 = 0;
      if ( v23 )
      {
        if ( a2 == v25 )
        {
          v26 = *(_DWORD *)(a1 + 276);
          if ( v57 == v26 || v57 == *(_DWORD *)(a1 + 272) )
            goto LABEL_60;
          v24 = v57 - v26;
          v27 = v26 - v57;
          if ( v27 < 0 )
            v27 = v24;
          if ( v27 < (int)v57 )
          {
LABEL_60:
            *(_QWORD *)(a1 + 256) = 0;
            v11 = v23;
          }
          else
          {
            ((void (*)(void))SamDsExtFree)();
            *(_QWORD *)(a1 + 256) = 0;
            v24 = v22;
          }
          v60 = v11;
          goto LABEL_75;
        }
        Src = 0;
        LocalFree(v23);
        v28 = v57;
        *(_QWORD *)(a1 + 256) = 0;
        *(_DWORD *)(a1 + 276) = v22;
        *(_DWORD *)(a1 + 272) = 0;
        *(_DWORD *)(a1 + 264) = a2;
      }
      else
      {
        if ( a2 == v25 )
        {
          v29 = 0;
          active = 0;
          goto LABEL_127;
        }
        Src = 0;
        active = SampMaybeBeginDsTransaction(0);
        if ( active < 0 )
          goto LABEL_17;
        v28 = v57;
      }
      QDIRestart = SampGetQDIRestart(*(_QWORD *)(a1 + 176), a2, v28, &Src);
      active = QDIRestart;
      if ( QDIRestart != -2147483622 )
      {
        if ( QDIRestart < 0 )
          goto LABEL_17;
        if ( Src )
        {
          active = SampCopyRestart(Src);
          if ( active < 0 )
          {
LABEL_110:
            v11 = v60;
            goto LABEL_17;
          }
          v11 = v60;
        }
        v24 = 0;
        goto LABEL_75;
      }
      v29 = 0;
      active = 0;
LABEL_127:
      SampMaybeEndDsTransaction(3);
      v15 = 0;
      v48 = 0;
      *v69 = 32 * v24;
      if ( v29 )
        active = 261;
      goto LABEL_20;
    case 5u:
      v54 = 0x10000000;
      v53 = 0x10000000;
      if ( !*((_QWORD *)a8 + 1) )
      {
        v16 = LocalAlloc(0x40u, 24LL * a4);
        *((_QWORD *)a8 + 1) = v16;
        if ( !v16 )
          goto LABEL_16;
        memset_0(v16, 0, 24LL * a4);
        *a8 = 0;
      }
      goto LABEL_40;
  }
  if ( a2 != 6 )
    return 3221225485LL;
  v54 = 516;
  v53 = 516;
  if ( *((_QWORD *)a8 + 1) )
    goto LABEL_28;
  v13 = LocalAlloc(0x40u, 48LL * a4);
  *((_QWORD *)a8 + 1) = v13;
  if ( v13 )
  {
    memset_0(v13, 0, 48LL * a4);
    *a8 = 0;
LABEL_28:
    v64 = 3;
LABEL_44:
    v55 = 4;
    v19 = v66;
    goto LABEL_45;
  }
LABEL_16:
  active = -1073741670;
LABEL_17:
  SampMaybeEndDsTransaction(3);
  if ( a8 )
    SampDsCleanQDIBuffer(v59, a8);
  v15 = v50;
LABEL_20:
  SampDsFreeQDIFilter((struct _FILTER_V1 *)v79);
  if ( v48 )
    SampDecrementActiveThreads();
  if ( v15 )
    SampAcquireReadLock();
  if ( v11 )
    SamDsExtFree(v11);
  return (unsigned int)active;
}

```

## disassembly

```asm
0x180408d10  mov     [rsp-8+arg_8], rbx
0x180408d15  push    rbp
0x180408d16  push    rsi
0x180408d17  push    rdi
0x180408d18  push    r12
0x180408d1a  push    r13
0x180408d1c  push    r14
0x180408d1e  push    r15
0x180408d20  lea     rbp, [rsp-190h]
0x180408d28  sub     rsp, 290h
0x180408d2f  mov     rax, cs:__security_cookie
0x180408d36  xor     rax, rsp
0x180408d39  mov     [rbp+1C0h+var_40], rax
0x180408d40  mov     rax, [rbp+1C0h+arg_28]
0x180408d47  mov     ebx, 1
0x180408d4c  mov     rdi, [rbp+1C0h+arg_38]
0x180408d53  mov     r14d, edx
0x180408d56  mov     [rbp+1C0h+var_220], rax
0x180408d5a  mov     rsi, rcx
0x180408d5d  mov     rax, [rbp+1C0h+arg_30]
0x180408d64  lea     rcx, [rbp+1C0h+var_190]; void *
0x180408d68  mov     [rsp+2C0h+var_258], r8d
0x180408d6d  mov     r13d, r9d
0x180408d70  mov     [rsp+2C0h+var_250], edx
0x180408d74  lea     r8d, [rbx+77h]; Size
0x180408d78  xor     edx, edx; Val
0x180408d7a  mov     [rbp+1C0h+var_1F0], rax
0x180408d7e  mov     [rbp+1C0h+var_228], ebx
0x180408d81  call    memset_0
0x180408d86  xor     edx, edx
0x180408d88  mov     [rbp+1C0h+var_C0], 6Bh ; 'k'
0x180408d92  lea     r15d, [rbx+1]
0x180408d96  mov     [rsp+2C0h+var_26E], dl
0x180408d9a  lea     rax, [rbp+1C0h+var_110]
0x180408da1  mov     [rsp+2C0h+var_270], dl
0x180408da5  mov     [rbp+1C0h+var_B0], rax
0x180408dac  mov     r12d, edx
0x180408daf  lea     rax, [rbp+1C0h+var_100]
0x180408db6  mov     [rbp+1C0h+var_110], edx
0x180408dbc  mov     [rbp+1C0h+var_98], rax
0x180408dc3  lea     rax, [rbp+1C0h+var_F0]
0x180408dca  mov     [rbp+1C0h+var_80], rax
0x180408dd1  lea     rax, [rbp+1C0h+var_E0]
0x180408dd8  mov     [rbp+1C0h+var_68], rax
0x180408ddf  lea     rax, [rbp+1C0h+var_D0]
0x180408de6  mov     [rbp+1C0h+var_50], rax
0x180408ded  lea     rax, [rbp+1C0h+var_C0]
0x180408df4  mov     [rbp+1C0h+var_210], rax
0x180408df8  lea     rax, [rbp+1C0h+var_1E8]
0x180408dfc  mov     [rbp+1C0h+var_1B8], rax
0x180408e00  lea     rax, [rbp+1C0h+var_1D8]
0x180408e04  mov     [rbp+1C0h+var_1A0], rax
0x180408e08  lea     rax, [rbp+1C0h+var_1C8]
0x180408e0c  mov     [rbp+1C0h+var_1F8], rax
0x180408e10  mov     eax, [rbp+1C0h+arg_20]
0x180408e16  shr     eax, 5
0x180408e19  cmp     r13d, eax
0x180408e1c  mov     [rbp+1C0h+var_108], rdx
0x180408e23  mov     [rbp+1C0h+var_100], edx
0x180408e29  cmova   r13d, eax
0x180408e2d  mov     [rbp+1C0h+var_F8], rdx
0x180408e34  lea     eax, [rbx+63h]
0x180408e37  mov     [rbp+1C0h+var_F0], edx
0x180408e3d  mov     [rbp+1C0h+var_E8], rdx
0x180408e44  mov     [rbp+1C0h+var_E0], edx
0x180408e4a  mov     [rbp+1C0h+var_D8], rdx
0x180408e51  mov     [rbp+1C0h+var_D0], edx
0x180408e57  mov     [rbp+1C0h+var_C8], rdx
0x180408e5e  mov     [rbp+1C0h+var_B8], ebx
0x180408e64  mov     [rbp+1C0h+var_A8], 7Eh ; '~'
0x180408e6e  mov     [rbp+1C0h+var_A0], ebx
0x180408e74  mov     [rbp+1C0h+var_90], ebx
0x180408e7a  mov     [rbp+1C0h+var_88], ebx
0x180408e80  mov     [rbp+1C0h+var_78], 3
0x180408e8a  mov     [rbp+1C0h+var_70], ebx
0x180408e90  mov     [rsp+2C0h+var_260], r15d
0x180408e95  mov     [rbp+1C0h+var_60], r15d
0x180408e9c  mov     [rbp+1C0h+var_58], ebx
0x180408ea2  mov     [rbp+1C0h+var_218], 5
0x180408eaa  mov     [rbp+1C0h+var_1E8], edx
0x180408ead  mov     [rbp+1C0h+var_1E0], rdx
0x180408eb1  mov     [rbp+1C0h+var_1D8], edx
0x180408eb4  mov     [rbp+1C0h+var_1D0], rdx
0x180408eb8  mov     [rbp+1C0h+var_1C8], ebx
0x180408ebb  mov     [rbp+1C0h+var_1C0], ebx
0x180408ebe  mov     [rbp+1C0h+var_1B0], r15d
0x180408ec2  mov     [rbp+1C0h+var_1A8], ebx
0x180408ec5  mov     [rbp+1C0h+var_200], r15
0x180408ec9  mov     [rsp+2C0h+var_248], rdx
0x180408ece  mov     [rbp+1C0h+var_208], rdx
0x180408ed2  mov     [rsp+2C0h+var_26F], bl
0x180408ed6  cmp     r13d, eax
0x180408ed9  jbe     short loc_180408EE0
0x180408edb  mov     r13d, eax
0x180408ede  jmp     short loc_180408EE7
0x180408ee0  cmp     r13d, ebx
0x180408ee3  cmovb   r13d, ebx
0x180408ee7  mov     ecx, r14d
0x180408eea  mov     [rbp+1C0h+var_240], r13d
0x180408eee  sub     ecx, ebx
0x180408ef0  jz      loc_180409162
0x180408ef6  sub     ecx, ebx
0x180408ef8  jz      loc_180409106
0x180408efe  sub     ecx, ebx
0x180408f00  jz      loc_1804090B0
0x180408f06  sub     ecx, ebx
0x180408f08  jz      loc_180409051
0x180408f0e  sub     ecx, ebx
0x180408f10  jz      loc_180408FFE
0x180408f16  cmp     ecx, ebx
0x180408f18  jz      short loc_180408F24
0x180408f1a  mov     eax, 0C000000Dh
0x180408f1f  jmp     loc_180408FB7
0x180408f24  mov     eax, 204h
0x180408f29  mov     [rsp+2C0h+var_264], eax
0x180408f2d  mov     [rsp+2C0h+var_268], eax
0x180408f31  cmp     [rdi+8], rdx
0x180408f35  jnz     loc_180408FF2
0x180408f3b  mov     eax, r13d
0x180408f3e  mov     ecx, 40h ; '@'; uFlags
0x180408f43  lea     rbx, [rax+rax*2]
0x180408f47  shl     rbx, 4
0x180408f4b  mov     rdx, rbx; uBytes
0x180408f4e  call    cs:__imp_LocalAlloc
0x180408f54  mov     [rdi+8], rax
0x180408f58  test    rax, rax
0x180408f5b  jnz     loc_180408FE1
0x180408f61  mov     ebx, 0C000009Ah
0x180408f66  mov     ecx, 3
0x180408f6b  call    SampMaybeEndDsTransaction
0x180408f70  test    rdi, rdi
0x180408f73  jz      short loc_180408F81
0x180408f75  mov     ecx, [rsp+2C0h+var_250]
0x180408f79  mov     rdx, rdi
0x180408f7c  call    ?SampDsCleanQDIBuffer@@YAJW4_DOMAIN_DISPLAY_INFORMATION@@PEAT_SAMPR_DISPLAY_INFO_BUFFER@@@Z; SampDsCleanQDIBuffer(_DOMAIN_DISPLAY_INFORMATION,_SAMPR_DISPLAY_INFO_BUFFER *)
0x180408f81  mov     dil, [rsp+2C0h+var_26E]
0x180408f86  lea     rcx, [rbp+1C0h+var_190]; struct _FILTER_V1 *
0x180408f8a  call    ?SampDsFreeQDIFilter@@YAXPEAU_FILTER_V1@@@Z; SampDsFreeQDIFilter(_FILTER_V1 *)
0x180408f8f  cmp     [rsp+2C0h+var_270], 0
0x180408f94  jz      short loc_180408F9C
0x180408f96  call    cs:__imp_SampDecrementActiveThreads
0x180408f9c  test    dil, dil
0x180408f9f  jz      short loc_180408FA7
0x180408fa1  call    cs:__imp_SampAcquireReadLock
0x180408fa7  test    r12, r12
0x180408faa  jz      short loc_180408FB5
0x180408fac  mov     rcx, r12
0x180408faf  call    cs:__imp_SamDsExtFree
0x180408fb5  mov     eax, ebx
0x180408fb7  mov     rcx, [rbp+1C0h+var_40]
0x180408fbe  xor     rcx, rsp; StackCookie
0x180408fc1  call    __security_check_cookie
0x180408fc6  mov     rbx, [rsp+2C0h+arg_8]
0x180408fce  add     rsp, 290h
0x180408fd5  pop     r15
0x180408fd7  pop     r14
0x180408fd9  pop     r13
0x180408fdb  pop     r12
0x180408fdd  pop     rdi
0x180408fde  pop     rsi
0x180408fdf  pop     rbp
0x180408fe0  retn
0x180408fe1  mov     r8, rbx; Size
0x180408fe4  xor     edx, edx; Val
0x180408fe6  mov     rcx, rax; void *
0x180408fe9  call    memset_0
0x180408fee  xor     edx, edx
0x180408ff0  mov     [rdi], edx
0x180408ff2  mov     [rbp+1C0h+var_228], 3
0x180408ff9  jmp     loc_180409150
0x180408ffe  mov     eax, 10000000h
0x180409003  mov     [rsp+2C0h+var_264], eax
0x180409007  mov     [rsp+2C0h+var_268], eax
0x18040900b  cmp     [rdi+8], rdx
0x18040900f  jnz     loc_180409100
0x180409015  mov     eax, r13d
0x180409018  mov     ecx, 40h ; '@'; uFlags
0x18040901d  lea     rbx, [rax+rax*2]
0x180409021  shl     rbx, 3
0x180409025  mov     rdx, rbx; uBytes
0x180409028  call    cs:__imp_LocalAlloc
0x18040902e  mov     [rdi+8], rax
0x180409032  test    rax, rax
0x180409035  jz      loc_180408F61
0x18040903b  mov     r8, rbx; Size
0x18040903e  xor     edx, edx; Val
0x180409040  mov     rcx, rax; void *
0x180409043  call    memset_0
0x180409048  xor     edx, edx
0x18040904a  mov     [rdi], edx
0x18040904c  jmp     loc_180409100
0x180409051  mov     eax, 30000000h
0x180409056  mov     [rsp+2C0h+var_264], eax
0x18040905a  mov     [rsp+2C0h+var_268], eax
0x18040905e  cmp     [rdi+8], rdx
0x180409062  jnz     short loc_18040909B
0x180409064  mov     eax, r13d
0x180409067  mov     ecx, 40h ; '@'; uFlags
0x18040906c  lea     rbx, [rax+rax*2]
0x180409070  shl     rbx, 3
0x180409074  mov     rdx, rbx; uBytes
0x180409077  call    cs:__imp_LocalAlloc
0x18040907d  mov     [rdi+8], rax
0x180409081  test    rax, rax
0x180409084  jz      loc_180408F61
0x18040908a  mov     r8, rbx; Size
0x18040908d  xor     edx, edx; Val
0x18040908f  mov     rcx, rax; void *
0x180409092  call    memset_0
0x180409097  xor     edx, edx
0x180409099  mov     [rdi], edx
0x18040909b  lea     rax, [rbp+1C0h+var_218]
0x18040909f  mov     [rsp+2C0h+var_260], 4
0x1804090a7  mov     [rbp+1C0h+var_230], rax
0x1804090ab  jmp     loc_1804091B8
0x1804090b0  mov     eax, 10000000h
0x1804090b5  mov     [rsp+2C0h+var_264], eax
0x1804090b9  mov     [rsp+2C0h+var_268], eax
0x1804090bd  cmp     [rdi+8], rdx
0x1804090c1  jnz     short loc_1804090FB
0x1804090c3  mov     eax, r13d
0x1804090c6  mov     ecx, 40h ; '@'; uFlags
0x1804090cb  lea     rbx, [rax+rax*2]
0x1804090cf  shl     rbx, 4
0x1804090d3  mov     rdx, rbx; uBytes
0x1804090d6  call    cs:__imp_LocalAlloc
0x1804090dc  mov     [rdi+8], rax
0x1804090e0  test    rax, rax
0x1804090e3  jz      loc_180408F61
0x1804090e9  mov     r8, rbx; Size
0x1804090ec  mov     [rdi], r12d
0x1804090ef  xor     edx, edx; Val
0x1804090f1  mov     rcx, rax; void *
0x1804090f4  call    memset_0
0x1804090f9  xor     edx, edx
0x1804090fb  mov     [rsp+2C0h+var_260], r15d
0x180409100  lea     rax, [rbp+1C0h+var_200]
0x180409104  jmp     short loc_18040915C
0x180409106  mov     eax, 30000001h
0x18040910b  mov     [rsp+2C0h+var_264], eax
0x18040910f  mov     [rsp+2C0h+var_268], eax
0x180409113  cmp     [rdi+8], rdx
0x180409117  jnz     short loc_180409150
0x180409119  mov     eax, r13d
0x18040911c  mov     ecx, 40h ; '@'; uFlags
0x180409121  lea     rbx, [rax+rax*2]
0x180409125  shl     rbx, 4
0x180409129  mov     rdx, rbx; uBytes
0x18040912c  call    cs:__imp_LocalAlloc
0x180409132  mov     [rdi+8], rax
0x180409136  test    rax, rax
0x180409139  jz      loc_180408F61
0x18040913f  mov     r8, rbx; Size
0x180409142  xor     edx, edx; Val
0x180409144  mov     rcx, rax; void *
0x180409147  call    memset_0
0x18040914c  xor     edx, edx
0x18040914e  mov     [rdi], edx
0x180409150  mov     [rsp+2C0h+var_260], 4
0x180409158  lea     rax, [rbp+1C0h+var_218]
0x18040915c  mov     [rbp+1C0h+var_230], rax
0x180409160  jmp     short loc_1804091B8
0x180409162  mov     eax, 30000000h
0x180409167  mov     [rsp+2C0h+var_260], 4
0x18040916f  mov     [rsp+2C0h+var_264], eax
0x180409173  mov     [rsp+2C0h+var_268], eax
0x180409177  lea     rax, [rbp+1C0h+var_218]
0x18040917b  mov     [rbp+1C0h+var_230], rax
0x18040917f  cmp     [rdi+8], rdx
0x180409183  jnz     short loc_1804091B8
0x180409185  mov     ebx, r13d
0x180409188  mov     ecx, 40h ; '@'; uFlags
0x18040918d  shl     rbx, 6
0x180409191  mov     rdx, rbx; uBytes
0x180409194  call    cs:__imp_LocalAlloc
0x18040919a  mov     [rdi+8], rax
0x18040919e  test    rax, rax
0x1804091a1  jz      loc_180408F61
0x1804091a7  mov     r8, rbx; Size
0x1804091aa  xor     edx, edx; Val
0x1804091ac  mov     rcx, rax; void *
0x1804091af  call    memset_0
0x1804091b4  xor     edx, edx
0x1804091b6  mov     [rdi], edx
0x1804091b8  mov     ebx, [rsp+2C0h+var_258]
0x1804091bc  mov     rcx, [rsi+100h]; hMem
0x1804091c3  test    ebx, ebx
0x1804091c5  jnz     short loc_1804091F6
0x1804091c7  test    rcx, rcx
0x1804091ca  jz      short loc_1804091D4
0x1804091cc  call    cs:__imp_LocalFree
0x1804091d2  xor     edx, edx
0x1804091d4  mov     [rsi+100h], rdx
0x1804091db  mov     r15d, edx
0x1804091de  mov     [rsi+110h], r12
0x1804091e5  mov     [rsi+108h], r14d
0x1804091ec  mov     [rsp+2C0h+var_26D], 1
0x1804091f1  jmp     loc_1804092FE
0x1804091f6  mov     eax, [rsi+108h]
0x1804091fc  mov     r15d, edx
  ... truncated ...
```
