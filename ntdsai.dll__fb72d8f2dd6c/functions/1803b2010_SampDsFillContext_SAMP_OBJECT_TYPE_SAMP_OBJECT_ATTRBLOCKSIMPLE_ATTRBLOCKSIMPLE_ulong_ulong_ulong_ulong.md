# SampDsFillContext(_SAMP_OBJECT_TYPE,_SAMP_OBJECT *,_ATTRBLOCKSIMPLE,_ATTRBLOCKSIMPLE,ulong,ulong,ulong,ulong)

- ea: `0x1803b2010`
- end: `0x1803b28b5`
- name: `?SampDsFillContext@@YAJW4_SAMP_OBJECT_TYPE@@PEAU_SAMP_OBJECT@@U_ATTRBLOCKSIMPLE@@2KKKK@Z`
- size: `2213`
- prototype: `int __high(enum _SAMP_OBJECT_TYPE, struct _SAMP_OBJECT *, struct _ATTRBLOCKSIMPLE, struct _ATTRBLOCKSIMPLE, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update`

## callers

- `0x1803b1a18`

## callees

- `0x18001e090`
- `0x180021aa3`
- `0x18016ab64`
- `0x1803b2010`
- `0x1803b2aac`
- `0x1803cf8e4`
- `0x1803e01b0`
- `0x1803e2dfc`
- `0x18041cbf8`
- `0x18042addc`
- `0x180453340`
- `0x18047b010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1803b23d6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1803b2490`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1803b26d1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1803b23d6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1803b2490`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1803b26d1`
- `ntdll!RtlFreeHeap` at `0x1803b282c`
- `ntdll!RtlFreeHeap` at `0x1803b284b`
- `ntdll!RtlFreeHeap` at `0x1803b282c`
- `ntdll!RtlFreeHeap` at `0x1803b284b`
- `SAMSRV!SampDsConvertReadAttrBlock` at `0x1803b21be`
- `SAMSRV!SampDsConvertReadAttrBlock` at `0x1803b2352`
- `SAMSRV!SampDsConvertReadAttrBlock` at `0x1803b21be`
- `SAMSRV!SampDsConvertReadAttrBlock` at `0x1803b2352`
- `SAMSRV!SampDsUpdateContextAttributes` at `0x1803b21ee`
- `SAMSRV!SampDsUpdateContextAttributes` at `0x1803b2380`
- `SAMSRV!SampDsUpdateContextAttributes` at `0x1803b21ee`
- `SAMSRV!SampDsUpdateContextAttributes` at `0x1803b2380`
- `SAMSRV!SampCreateDefaultUPN` at `0x1803b252a`
- `SAMSRV!SampCreateDefaultUPN` at `0x1803b252a`

## pseudocode

```c
__int64 __fastcall SampDsFillContext(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        unsigned int a7,
        int a8)
{
  int *v11; // rbx
  unsigned __int64 v12; // r14
  __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  void *v15; // rsp
  void *v16; // rsp
  int *v17; // rax
  unsigned int v18; // r9d
  __int64 v19; // r15
  unsigned int v20; // edx
  __int64 i; // r8
  __int64 v22; // r11
  __int64 v23; // rcx
  __int64 v24; // rax
  int updated; // ebx
  int *v26; // rbx
  unsigned __int64 v27; // r14
  __int64 v28; // rcx
  unsigned __int64 v29; // rcx
  void *v30; // rsp
  void *v31; // rsp
  int *v32; // rax
  __int64 v33; // r8
  unsigned int v34; // r11d
  __int64 v35; // r14
  __int64 j; // rdx
  __int64 v37; // r10
  __int64 v38; // rax
  __int64 v39; // rcx
  unsigned int v40; // r14d
  __int64 SingleValuedAttrFromAttrBlock; // rax
  __int64 v42; // r15
  HLOCAL v43; // rax
  __int64 v44; // rax
  void *v45; // r11
  __int64 v46; // rax
  void *v47; // r11
  __int64 v48; // rax
  __int64 v49; // r15
  HLOCAL v50; // rax
  __int16 v51; // cx
  char v52; // al
  __int64 v53; // rax
  __int64 v54; // rdx
  __int64 v55; // xmm1_8
  __int64 v56; // rax
  __int64 v57; // rax
  int v58; // eax
  __int64 v59; // rax
  __int64 v60; // rax
  __int64 v61; // rbx
  unsigned int *v62; // rax
  HLOCAL v63; // rax
  __int64 v64; // rax
  int IsEqualGUID; // eax
  __int64 v66; // r8
  __int64 v67; // rcx
  __int64 v68; // rax
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rax
  _BYTE v73[32]; // [rsp+0h] [rbp-30h] BYREF
  int v74; // [rsp+30h] [rbp+0h] BYREF
  unsigned int v75; // [rsp+34h] [rbp+4h] BYREF
  unsigned int v76; // [rsp+38h] [rbp+8h] BYREF
  PVOID P; // [rsp+40h] [rbp+10h] BYREF
  PVOID v78; // [rsp+48h] [rbp+18h] BYREF
  __int128 v79; // [rsp+50h] [rbp+20h] BYREF
  __int128 v80; // [rsp+60h] [rbp+30h] BYREF
  __int128 v81; // [rsp+70h] [rbp+40h] BYREF
  __int64 v82; // [rsp+80h] [rbp+50h]
  _BYTE v83[24]; // [rsp+88h] [rbp+58h] BYREF

  v82 = a4;
  v76 = a1;
  P = 0;
  v78 = 0;
  v75 = 0;
  v74 = 0;
  v11 = 0;
  v79 = 0;
  v12 = 24LL * a6;
  v80 = 0;
  if ( !v12
    || v12 > g_ulMaxStackAllocSize
    || v12 + g_ulAdditionalProbeSize + 8 < v12
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_125;
  }
  v13 = v12 + 23;
  if ( v12 + 23 <= v12 + 8 )
    v13 = 0xFFFFFFFFFFFFFF0LL;
  v14 = v13 & 0xFFFFFFFFFFFFFFF0uLL;
  v15 = alloca(v14);
  v16 = alloca(v14);
  v11 = &v74;
  if ( v73 == (_BYTE *)-48LL || (v74 = 1801679955, (v11 = (int *)&v76) == 0) )
  {
LABEL_125:
    if ( v12 + 8 >= v12 )
    {
      v17 = (int *)((__int64 (*)(void))g_pfnAllocate)();
      v11 = v17;
      if ( v17 )
      {
        *v17 = 1885431112;
        v11 = v17 + 2;
      }
    }
  }
  *((_QWORD *)&v79 + 1) = v11;
  if ( !v11 )
    goto LABEL_111;
  v18 = 0;
  LODWORD(v79) = 0;
  v19 = a6 + 1;
  if ( (unsigned int)v19 > 1 )
  {
    v20 = 1;
    do
    {
      if ( v20 >= *(_DWORD *)a4 )
        break;
      for ( i = 0; (unsigned int)i < *(_DWORD *)a3; i = (unsigned int)(i + 1) )
      {
        v22 = *(_QWORD *)(a3 + 8);
        if ( *(_DWORD *)(*(_QWORD *)(a4 + 8) + 24LL * v20) == *(_DWORD *)(v22 + 24 * i) )
        {
          v23 = 3LL * v18;
          v24 = *((_QWORD *)&v79 + 1);
          *(_OWORD *)(*((_QWORD *)&v79 + 1) + 8 * v23) = *(_OWORD *)(v22 + 24 * i);
          *(_QWORD *)(v24 + 8 * v23 + 16) = *(_QWORD *)(v22 + 24 * i + 16);
          v18 = v79 + 1;
          LODWORD(v79) = v79 + 1;
          break;
        }
      }
      ++v20;
    }
    while ( v20 < (unsigned int)v19 );
  }
  updated = SampDsConvertReadAttrBlock(v76, 0, &v79, &P, &v75, &v74);
  if ( updated >= 0 )
  {
    if ( P )
    {
      updated = SampDsUpdateContextAttributes(a2, 0, P, v75, v74);
      if ( updated < 0 )
        goto LABEL_112;
      v26 = 0;
      v27 = 24LL * a7;
      if ( !v27
        || v27 > g_ulMaxStackAllocSize
        || v27 + g_ulAdditionalProbeSize + 8 < v27
        || !(unsigned int)VerifyStackAvailable() )
      {
        goto LABEL_126;
      }
      v28 = v27 + 23;
      if ( v27 + 23 <= v27 + 8 )
        v28 = 0xFFFFFFFFFFFFFF0LL;
      v29 = v28 & 0xFFFFFFFFFFFFFFF0uLL;
      v30 = alloca(v29);
      v31 = alloca(v29);
      v26 = &v74;
      if ( v73 == (_BYTE *)-48LL || (v74 = 1801679955, (v26 = (int *)&v76) == 0) )
      {
LABEL_126:
        if ( v27 + 8 >= v27 )
        {
          v32 = (int *)((__int64 (*)(void))g_pfnAllocate)();
          v26 = v32;
          if ( v32 )
          {
            *v32 = 1885431112;
            v26 = v32 + 2;
          }
        }
      }
      *((_QWORD *)&v80 + 1) = v26;
      if ( v26 )
      {
        v33 = 0;
        v34 = a6 + a7 + 1;
        LODWORD(v80) = 0;
        if ( (unsigned int)v19 < v34 )
        {
          v35 = v82;
          do
          {
            if ( (unsigned int)v19 >= *(_DWORD *)v35 )
              break;
            for ( j = 0; (unsigned int)j < *(_DWORD *)a3; j = (unsigned int)(j + 1) )
            {
              v37 = *(_QWORD *)(a3 + 8);
              if ( *(_DWORD *)(*(_QWORD *)(v35 + 8) + 24 * v19) == *(_DWORD *)(v37 + 24 * j) )
              {
                v38 = *((_QWORD *)&v80 + 1);
                v39 = 3 * v33;
                *(_OWORD *)(*((_QWORD *)&v80 + 1) + 8 * v39) = *(_OWORD *)(v37 + 24 * j);
                *(_QWORD *)(v38 + 8 * v39 + 16) = *(_QWORD *)(v37 + 24 * j + 16);
                v33 = (unsigned int)(v80 + 1);
                LODWORD(v80) = v80 + 1;
                break;
              }
            }
            v19 = (unsigned int)(v19 + 1);
          }
          while ( (unsigned int)v19 < v34 );
        }
        v40 = v76;
        v75 = 0;
        v74 = 0;
        updated = SampDsConvertReadAttrBlock(v76, 1, &v80, &v78, &v75, &v74);
        if ( updated < 0 )
        {
          if ( v78 )
            goto LABEL_112;
          goto LABEL_111;
        }
        if ( v78 )
        {
          updated = SampDsUpdateContextAttributes(a2, 1, v78, v75, v74);
          if ( updated < 0 || v40 != 4 )
            goto LABEL_112;
          *(_DWORD *)(a2 + 296) = 0;
          *(_QWORD *)(a2 + 288) = 0;
          if ( (a8 & 0x100) != 0 )
          {
            SingleValuedAttrFromAttrBlock = SampDsGetSingleValuedAttrFromAttrBlock(115, a3);
            v42 = SingleValuedAttrFromAttrBlock;
            if ( SingleValuedAttrFromAttrBlock )
            {
              v43 = LocalAlloc(0x40u, **(unsigned int **)(SingleValuedAttrFromAttrBlock + 16));
              *(_QWORD *)(a2 + 288) = v43;
              if ( !v43 )
                goto LABEL_111;
              memcpy_0(v43, *(const void **)(*(_QWORD *)(v42 + 16) + 8LL), **(unsigned int **)(v42 + 16));
              *(_DWORD *)(a2 + 296) = **(_DWORD **)(v42 + 16);
            }
            *(_BYTE *)(a2 + 300) = 1;
          }
          *(_QWORD *)(a2 + 272) = 0;
          v44 = SampDsGetSingleValuedAttrFromAttrBlock(117, a3);
          if ( v44 )
            memcpy_0(v45, *(const void **)(*(_QWORD *)(v44 + 16) + 8LL), **(unsigned int **)(v44 + 16));
          *(_QWORD *)(a2 + 280) = 0;
          v46 = SampDsGetSingleValuedAttrFromAttrBlock(123, a3);
          if ( v46 )
            memcpy_0(v47, *(const void **)(*(_QWORD *)(v46 + 16) + 8LL), **(unsigned int **)(v46 + 16));
          v48 = SampDsGetSingleValuedAttrFromAttrBlock(119, a3);
          v49 = v48;
          if ( v48 )
          {
            v50 = LocalAlloc(0x40u, **(unsigned int **)(v48 + 16));
            *(_QWORD *)(a2 + 344) = v50;
            if ( !v50 )
              goto LABEL_111;
            memcpy_0(v50, *(const void **)(*(_QWORD *)(v49 + 16) + 8LL), **(unsigned int **)(v49 + 16));
            v51 = **(_WORD **)(v49 + 16);
            v52 = 0;
            *(_WORD *)(a2 + 338) = v51;
            *(_WORD *)(a2 + 336) = v51;
          }
          else
          {
            v81 = 0;
            v53 = SampDsGetSingleValuedAttrFromAttrBlock(1, a3);
            if ( !v53 )
              goto LABEL_64;
            v54 = *(unsigned int *)(a2 + 200);
            LOWORD(v81) = **(_WORD **)(v53 + 16);
            WORD1(v81) = **(_WORD **)(v53 + 16);
            *((_QWORD *)&v81 + 1) = *(_QWORD *)(*(_QWORD *)(v53 + 16) + 8LL);
            updated = SampCreateDefaultUPN(&v81, v54, a2 + 336);
            if ( updated < 0 )
              goto LABEL_112;
            v52 = 1;
          }
          *(_BYTE *)(a2 + 352) = v52;
          if ( (a8 & 0x1000000) != 0 )
          {
            memset(v83, 0, sizeof(v83));
            if ( (int)SampFindUserSiteAffinity(a2, a3, v83) >= 0 )
            {
              v55 = *(_QWORD *)&v83[16];
              *(_OWORD *)(a2 + 360) = *(_OWORD *)v83;
              *(_QWORD *)(a2 + 376) = v55;
            }
          }
          if ( (a8 & 2) != 0 )
          {
            *(_BYTE *)(a2 + 536) = 1;
            updated = SampFindUserStringListAttribute(
                        (struct _ATTRBLOCKSIMPLE *)a3,
                        0x80u,
                        (struct _USER_STRING_LIST **)(a2 + 528));
            if ( updated < 0 )
              goto LABEL_112;
          }
          if ( (a8 & 4) != 0 )
          {
            *(_BYTE *)(a2 + 552) = 1;
            updated = SampFindUserStringListAttribute(
                        (struct _ATTRBLOCKSIMPLE *)a3,
                        0x81u,
                        (struct _USER_STRING_LIST **)(a2 + 544));
            if ( updated < 0 )
              goto LABEL_112;
          }
          if ( (a8 & 8) != 0 )
          {
            *(_BYTE *)(a2 + 560) = 1;
            v56 = SampDsGetSingleValuedAttrFromAttrBlock(130, a3);
            if ( v56 )
              *(_DWORD *)(a2 + 556) = **(_DWORD **)(*(_QWORD *)(v56 + 16) + 8LL);
          }
          v57 = SampDsGetSingleValuedAttrFromAttrBlock(132, a3);
          if ( v57 )
          {
            v58 = **(_DWORD **)(*(_QWORD *)(v57 + 16) + 8LL);
            if ( v58 )
            {
              *(_DWORD *)(a2 + 564) = v58;
              *(_BYTE *)(a2 + 568) = 1;
            }
          }
          if ( (a8 & 0x40) != 0 )
          {
            *(_BYTE *)(a2 + 576) = 1;
            v59 = SampDsGetSingleValuedAttrFromAttrBlock(133, a3);
            if ( v59 )
              *(_DWORD *)(a2 + 572) = **(_DWORD **)(*(_QWORD *)(v59 + 16) + 8LL);
          }
          if ( (a8 & 0x80u) != 0 )
          {
            *(_BYTE *)(a2 + 592) = 1;
            updated = SampFindUserStringListAttribute(
                        (struct _ATTRBLOCKSIMPLE *)a3,
                        0x86u,
                        (struct _USER_STRING_LIST **)(a2 + 584));
            if ( updated < 0 )
              goto LABEL_112;
          }
          if ( (a8 & 0x800) == 0 )
          {
LABEL_92:
            if ( (a8 & 0x2000000) == 0
              || (updated = SampAddAPSInfoToContext((struct _ATTRBLOCKSIMPLE *)a3, (struct _SAMP_OBJECT *)a2),
                  updated >= 0) )
            {
              if ( (a8 & 0x8000000) != 0 )
              {
                v64 = SampDsGetSingleValuedAttrFromAttrBlock(139, a3);
                if ( v64 )
                {
                  IsEqualGUID = DsIsEqualGUID(
                                  *(_QWORD *)(*(_QWORD *)(v64 + 16) + 8LL) + 8LL,
                                  "/xb7/xef/x42/xae/x55/xe1/x7a/x4b/x98/x4f/x75/x75/x81/xf5/x84/x94");
                  v67 = v66 + 72;
                  if ( !IsEqualGUID )
                    v67 = v66;
                  *(_OWORD *)(a2 + 688) = *(_OWORD *)(v67 + 8);
                }
              }
              if ( (a8 & 0x10000000) != 0 )
              {
                v68 = SampDsGetSingleValuedAttrFromAttrBlock(140, a3);
                if ( !v68 )
                  goto LABEL_64;
                v69 = *(_QWORD *)(v68 + 16);
                if ( *(_DWORD *)v69 != 8 )
                  goto LABEL_64;
                *(_QWORD *)(a2 + 744) = 10000000LL * **(_QWORD **)(v69 + 8);
              }
              if ( (a8 & 0x20000000) == 0
                || (updated = SampAddDMSAInfoToContext((struct _ATTRBLOCKSIMPLE *)a3, (struct _SAMP_OBJECT *)a2),
                    updated >= 0) )
              {
                v70 = SampDsGetSingleValuedAttrFromAttrBlock(148, a3);
                if ( v70 )
                {
                  v71 = *(_QWORD *)(v70 + 16);
                  if ( *(_DWORD *)v71 == 16 )
                  {
                    *(_OWORD *)(a2 + 252) = *(_OWORD *)*(_QWORD *)(v71 + 8);
                    goto LABEL_112;
                  }
                }
LABEL_64:
                updated = -1073741595;
              }
            }
LABEL_112:
            if ( !P )
              goto LABEL_114;
            goto LABEL_113;
          }
          *(_QWORD *)(a2 + 600) = 0;
          *(_DWORD *)(a2 + 596) = 0;
          v60 = SampDsGetSingleValuedAttrFromAttrBlock(136, a3);
          v61 = v60;
          if ( !v60 || *(_DWORD *)(v60 + 8) != 1 || (v62 = *(unsigned int **)(v60 + 16), !*((_QWORD *)v62 + 1)) )
          {
LABEL_91:
            updated = 0;
            goto LABEL_92;
          }
          v63 = LocalAlloc(0x40u, *v62);
          *(_QWORD *)(a2 + 600) = v63;
          if ( v63 )
          {
            memcpy_0(v63, *(const void **)(*(_QWORD *)(v61 + 16) + 8LL), **(unsigned int **)(v61 + 16));
            *(_DWORD *)(a2 + 596) = **(_DWORD **)(v61 + 16);
            goto LABEL_91;
          }
        }
      }
    }
LABEL_111:
    updated = -1073741670;
    goto LABEL_112;
  }
  if ( !P )
    goto LABEL_111;
LABEL_113:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
LABEL_114:
  if ( v78 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v78);
  if ( *((_QWORD *)&v79 + 1) && *(_DWORD *)(*((_QWORD *)&v79 + 1) - 8LL) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( *((_QWORD *)&v80 + 1) && *(_DWORD *)(*((_QWORD *)&v80 + 1) - 8LL) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1803b2010  push    rbp
0x1803b2012  push    rbx
0x1803b2013  push    rsi
0x1803b2014  push    rdi
0x1803b2015  push    r12
0x1803b2017  push    r13
0x1803b2019  push    r14
0x1803b201b  push    r15
0x1803b201d  sub     rsp, 0B8h
0x1803b2024  lea     rbp, [rsp+30h]
0x1803b2029  mov     rax, cs:__security_cookie
0x1803b2030  xor     rax, rbp
0x1803b2033  mov     [rbp+0C0h+var_50], rax
0x1803b2037  mov     r13d, [rbp+0C0h+arg_28]
0x1803b203e  xor     r15d, r15d
0x1803b2041  mov     rsi, r8
0x1803b2044  mov     [rbp+0C0h+var_70], r9
0x1803b2048  xorps   xmm0, xmm0
0x1803b204b  mov     [rbp+0C0h+var_B8], ecx
0x1803b204e  xorps   xmm1, xmm1
0x1803b2051  mov     [rbp+0C0h+P], r15
0x1803b2055  lea     r8, ds:0[r13*2]
0x1803b205d  mov     [rbp+0C0h+var_A8], r15
0x1803b2061  add     r8, r13
0x1803b2064  mov     [rbp+0C0h+var_BC], r15d
0x1803b2068  mov     r12, r9
0x1803b206b  mov     [rbp+0C0h+var_C0], r15d
0x1803b206f  mov     rdi, rdx
0x1803b2072  mov     ebx, r15d
0x1803b2075  movups  [rbp+0C0h+var_A0], xmm0
0x1803b2079  lea     r14, ds:0[r8*8]
0x1803b2081  movups  [rbp+0C0h+var_90], xmm1
0x1803b2085  test    r14, r14
0x1803b2088  jz      short loc_1803B20EB
0x1803b208a  cmp     r14, cs:g_ulMaxStackAllocSize
0x1803b2091  ja      short loc_1803B20EB
0x1803b2093  mov     rcx, cs:g_ulAdditionalProbeSize
0x1803b209a  add     rcx, 8
0x1803b209e  add     rcx, r14
0x1803b20a1  cmp     rcx, r14
0x1803b20a4  jb      short loc_1803B20EB
0x1803b20a6  call    VerifyStackAvailable
0x1803b20ab  test    eax, eax
0x1803b20ad  jz      short loc_1803B20EB
0x1803b20af  lea     rax, [r14+8]
0x1803b20b3  lea     rcx, [rax+0Fh]
0x1803b20b7  cmp     rcx, rax
0x1803b20ba  ja      short loc_1803B20C6
0x1803b20bc  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1803b20c6  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1803b20ca  mov     rax, rcx
0x1803b20cd  call    _alloca_probe
0x1803b20d2  sub     rsp, rcx
0x1803b20d5  lea     rbx, [rsp+0F0h+var_C0]
0x1803b20da  test    rbx, rbx
0x1803b20dd  jz      short loc_1803B20EB
0x1803b20df  mov     dword ptr [rbx], 6B637453h
0x1803b20e5  add     rbx, 8
0x1803b20e9  jnz     short loc_1803B2112
0x1803b20eb  lea     rcx, [r14+8]
0x1803b20ef  cmp     rcx, r14
0x1803b20f2  jb      short loc_1803B2112
0x1803b20f4  mov     rax, cs:g_pfnAllocate
0x1803b20fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803b2100  mov     rbx, rax
0x1803b2103  test    rax, rax
0x1803b2106  jz      short loc_1803B2112
0x1803b2108  mov     dword ptr [rax], 70616548h
0x1803b210e  add     rbx, 8
0x1803b2112  mov     qword ptr [rbp+0C0h+var_A0+8], rbx
0x1803b2116  test    rbx, rbx
0x1803b2119  jnz     short loc_1803B2123
0x1803b211b  xor     r12d, r12d
0x1803b211e  jmp     loc_1803B280E
0x1803b2123  mov     r9d, r15d
0x1803b2126  mov     dword ptr [rbp+0C0h+var_A0], r15d
0x1803b212a  lea     r15d, [r13+1]
0x1803b212e  mov     r14d, 1
0x1803b2134  cmp     r15d, r14d
0x1803b2137  jbe     short loc_1803B219F
0x1803b2139  mov     edx, r14d
0x1803b213c  cmp     edx, [r12]
0x1803b2140  jnb     short loc_1803B219F
0x1803b2142  mov     eax, edx
0x1803b2144  xor     r8d, r8d
0x1803b2147  lea     rbx, [rax+rax*2]
0x1803b214b  cmp     r8d, [rsi]
0x1803b214e  jnb     short loc_1803B2197
0x1803b2150  mov     r11, [rsi+8]
0x1803b2154  lea     r10, [r8+r8*2]
0x1803b2158  mov     rcx, [r12+8]
0x1803b215d  mov     eax, [r11+r10*8]
0x1803b2161  cmp     [rcx+rbx*8], eax
0x1803b2164  jz      short loc_1803B216B
0x1803b2166  add     r8d, r14d
0x1803b2169  jmp     short loc_1803B214B
0x1803b216b  movups  xmm0, xmmword ptr [r11+r10*8]
0x1803b2170  mov     eax, r9d
0x1803b2173  lea     rcx, [rax+rax*2]
0x1803b2177  mov     rax, qword ptr [rbp+0C0h+var_A0+8]
0x1803b217b  movups  xmmword ptr [rax+rcx*8], xmm0
0x1803b217f  movsd   xmm1, qword ptr [r11+r10*8+10h]
0x1803b2186  movsd   qword ptr [rax+rcx*8+10h], xmm1
0x1803b218c  mov     r9d, dword ptr [rbp+0C0h+var_A0]
0x1803b2190  add     r9d, r14d
0x1803b2193  mov     dword ptr [rbp+0C0h+var_A0], r9d
0x1803b2197  add     edx, r14d
0x1803b219a  cmp     edx, r15d
0x1803b219d  jb      short loc_1803B213C
0x1803b219f  mov     ecx, [rbp+0C0h+var_B8]
0x1803b21a2  lea     rax, [rbp+0C0h+var_C0]
0x1803b21a6  mov     [rsp+0F0h+var_C8], rax
0x1803b21ab  lea     r9, [rbp+0C0h+P]
0x1803b21af  lea     rax, [rbp+0C0h+var_BC]
0x1803b21b3  xor     edx, edx
0x1803b21b5  lea     r8, [rbp+0C0h+var_A0]
0x1803b21b9  mov     [rsp+0F0h+var_D0], rax
0x1803b21be  call    cs:__imp_SampDsConvertReadAttrBlock
0x1803b21c4  xor     r12d, r12d
0x1803b21c7  mov     ebx, eax
0x1803b21c9  test    eax, eax
0x1803b21cb  js      loc_1803B2808
0x1803b21d1  mov     r8, [rbp+0C0h+P]
0x1803b21d5  test    r8, r8
0x1803b21d8  jz      loc_1803B280E
0x1803b21de  mov     eax, [rbp+0C0h+var_C0]
0x1803b21e1  xor     edx, edx
0x1803b21e3  mov     r9d, [rbp+0C0h+var_BC]
0x1803b21e7  mov     rcx, rdi
0x1803b21ea  mov     dword ptr [rsp+0F0h+var_D0], eax
0x1803b21ee  call    cs:__imp_SampDsUpdateContextAttributes
0x1803b21f4  mov     ebx, eax
0x1803b21f6  test    eax, eax
0x1803b21f8  js      loc_1803B2813
0x1803b21fe  mov     r12d, [rbp+0C0h+arg_30]
0x1803b2205  xor     ebx, ebx
0x1803b2207  lea     rcx, [r12+r12*2]
0x1803b220b  lea     r14, ds:0[rcx*8]
0x1803b2213  test    r14, r14
0x1803b2216  jz      short loc_1803B2279
0x1803b2218  cmp     r14, cs:g_ulMaxStackAllocSize
0x1803b221f  ja      short loc_1803B2279
0x1803b2221  mov     rcx, cs:g_ulAdditionalProbeSize
0x1803b2228  add     rcx, 8
0x1803b222c  add     rcx, r14
0x1803b222f  cmp     rcx, r14
0x1803b2232  jb      short loc_1803B2279
0x1803b2234  call    VerifyStackAvailable
0x1803b2239  test    eax, eax
0x1803b223b  jz      short loc_1803B2279
0x1803b223d  lea     rax, [r14+8]
0x1803b2241  lea     rcx, [rax+0Fh]
0x1803b2245  cmp     rcx, rax
0x1803b2248  ja      short loc_1803B2254
0x1803b224a  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1803b2254  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1803b2258  mov     rax, rcx
0x1803b225b  call    _alloca_probe
0x1803b2260  sub     rsp, rcx
0x1803b2263  lea     rbx, [rsp+0F0h+var_C0]
0x1803b2268  test    rbx, rbx
0x1803b226b  jz      short loc_1803B2279
0x1803b226d  mov     dword ptr [rbx], 6B637453h
0x1803b2273  add     rbx, 8
0x1803b2277  jnz     short loc_1803B22A0
0x1803b2279  lea     rcx, [r14+8]
0x1803b227d  cmp     rcx, r14
0x1803b2280  jb      short loc_1803B22A0
0x1803b2282  mov     rax, cs:g_pfnAllocate
0x1803b2289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803b228e  mov     rbx, rax
0x1803b2291  test    rax, rax
0x1803b2294  jz      short loc_1803B22A0
0x1803b2296  mov     dword ptr [rax], 70616548h
0x1803b229c  add     rbx, 8
0x1803b22a0  mov     qword ptr [rbp+0C0h+var_90+8], rbx
0x1803b22a4  test    rbx, rbx
0x1803b22a7  jz      loc_1803B211B
0x1803b22ad  xor     r8d, r8d
0x1803b22b0  lea     r11d, [r12+1]
0x1803b22b5  add     r11d, r13d
0x1803b22b8  mov     dword ptr [rbp+0C0h+var_90], r8d
0x1803b22bc  cmp     r15d, r11d
0x1803b22bf  jnb     short loc_1803B231E
0x1803b22c1  mov     r14, [rbp+0C0h+var_70]
0x1803b22c5  cmp     r15d, [r14]
0x1803b22c8  jnb     short loc_1803B231E
0x1803b22ca  xor     edx, edx
0x1803b22cc  lea     rbx, [r15+r15*2]
0x1803b22d0  cmp     edx, [rsi]
0x1803b22d2  jnb     short loc_1803B2316
0x1803b22d4  mov     r10, [rsi+8]
0x1803b22d8  lea     r9, [rdx+rdx*2]
0x1803b22dc  mov     rcx, [r14+8]
0x1803b22e0  mov     eax, [r10+r9*8]
0x1803b22e4  cmp     [rcx+rbx*8], eax
0x1803b22e7  jz      short loc_1803B22ED
0x1803b22e9  inc     edx
0x1803b22eb  jmp     short loc_1803B22D0
0x1803b22ed  movups  xmm0, xmmword ptr [r10+r9*8]
0x1803b22f2  mov     rax, qword ptr [rbp+0C0h+var_90+8]
0x1803b22f6  lea     rcx, [r8+r8*2]
0x1803b22fa  movups  xmmword ptr [rax+rcx*8], xmm0
0x1803b22fe  movsd   xmm1, qword ptr [r10+r9*8+10h]
0x1803b2305  movsd   qword ptr [rax+rcx*8+10h], xmm1
0x1803b230b  mov     r8d, dword ptr [rbp+0C0h+var_90]
0x1803b230f  inc     r8d
0x1803b2312  mov     dword ptr [rbp+0C0h+var_90], r8d
0x1803b2316  inc     r15d
0x1803b2319  cmp     r15d, r11d
0x1803b231c  jb      short loc_1803B22C5
0x1803b231e  mov     r14d, [rbp+0C0h+var_B8]
0x1803b2322  lea     rax, [rbp+0C0h+var_C0]
0x1803b2326  xor     r12d, r12d
0x1803b2329  mov     [rsp+0F0h+var_C8], rax
0x1803b232e  lea     rax, [rbp+0C0h+var_BC]
0x1803b2332  mov     [rbp+0C0h+var_BC], r12d
0x1803b2336  lea     r9, [rbp+0C0h+var_A8]
0x1803b233a  mov     [rbp+0C0h+var_C0], r12d
0x1803b233e  lea     r8, [rbp+0C0h+var_90]
0x1803b2342  mov     [rsp+0F0h+var_D0], rax
0x1803b2347  lea     r13d, [r12+1]
0x1803b234c  mov     ecx, r14d
0x1803b234f  mov     edx, r13d
0x1803b2352  call    cs:__imp_SampDsConvertReadAttrBlock
0x1803b2358  mov     ebx, eax
0x1803b235a  test    eax, eax
0x1803b235c  js      loc_1803B2800
0x1803b2362  mov     r8, [rbp+0C0h+var_A8]
0x1803b2366  test    r8, r8
0x1803b2369  jz      loc_1803B280E
0x1803b236f  mov     eax, [rbp+0C0h+var_C0]
0x1803b2372  mov     edx, r13d
0x1803b2375  mov     r9d, [rbp+0C0h+var_BC]
0x1803b2379  mov     rcx, rdi
0x1803b237c  mov     dword ptr [rsp+0F0h+var_D0], eax
0x1803b2380  call    cs:__imp_SampDsUpdateContextAttributes
0x1803b2386  mov     ebx, eax
0x1803b2388  test    eax, eax
0x1803b238a  js      loc_1803B2813
0x1803b2390  cmp     r14d, 4
0x1803b2394  jnz     loc_1803B2813
0x1803b239a  mov     r14d, [rbp+0C0h+arg_38]
0x1803b23a1  mov     [rdi+128h], r12d
0x1803b23a8  mov     [rdi+120h], r12
0x1803b23af  bt      r14d, 8
0x1803b23b4  jnb     short loc_1803B2412
0x1803b23b6  mov     rdx, rsi
0x1803b23b9  lea     ecx, [r12+73h]
0x1803b23be  call    SampDsGetSingleValuedAttrFromAttrBlock
0x1803b23c3  mov     r15, rax
0x1803b23c6  test    rax, rax
0x1803b23c9  jz      short loc_1803B240B
0x1803b23cb  mov     rcx, [rax+10h]
0x1803b23cf  mov     edx, [rcx]; uBytes
0x1803b23d1  lea     ecx, [r12+40h]; uFlags
0x1803b23d6  call    cs:__imp_LocalAlloc
0x1803b23dc  mov     [rdi+120h], rax
0x1803b23e3  test    rax, rax
0x1803b23e6  jz      loc_1803B280E
0x1803b23ec  mov     rdx, [r15+10h]
0x1803b23f0  mov     rcx, rax; void *
0x1803b23f3  mov     r8d, [rdx]; Size
0x1803b23f6  mov     rdx, [rdx+8]; Src
0x1803b23fa  call    memcpy_0
0x1803b23ff  mov     rax, [r15+10h]
0x1803b2403  mov     ecx, [rax]
0x1803b2405  mov     [rdi+128h], ecx
0x1803b240b  mov     [rdi+12Ch], r13b
0x1803b2412  xor     eax, eax
0x1803b2414  lea     r11, [rdi+110h]
0x1803b241b  mov     rdx, rsi
0x1803b241e  mov     [r11], rax
0x1803b2421  lea     ecx, [rax+75h]
0x1803b2424  call    SampDsGetSingleValuedAttrFromAttrBlock
0x1803b2429  test    rax, rax
0x1803b242c  jz      short loc_1803B2441
0x1803b242e  mov     rdx, [rax+10h]
0x1803b2432  mov     rcx, r11; void *
0x1803b2435  mov     r8d, [rdx]; Size
0x1803b2438  mov     rdx, [rdx+8]; Src
0x1803b243c  call    memcpy_0
0x1803b2441  xor     eax, eax
0x1803b2443  lea     r11, [rdi+118h]
0x1803b244a  mov     rdx, rsi
0x1803b244d  mov     [r11], rax
0x1803b2450  lea     ecx, [rax+7Bh]
0x1803b2453  call    SampDsGetSingleValuedAttrFromAttrBlock
0x1803b2458  test    rax, rax
0x1803b245b  jz      short loc_1803B2470
0x1803b245d  mov     rdx, [rax+10h]
0x1803b2461  mov     rcx, r11; void *
0x1803b2464  mov     r8d, [rdx]; Size
0x1803b2467  mov     rdx, [rdx+8]; Src
0x1803b246b  call    memcpy_0
0x1803b2470  mov     rdx, rsi
0x1803b2473  mov     ecx, 77h ; 'w'
0x1803b2478  call    SampDsGetSingleValuedAttrFromAttrBlock
0x1803b247d  mov     r15, rax
0x1803b2480  test    rax, rax
  ... truncated ...
```
