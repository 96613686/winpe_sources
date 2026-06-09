# WSTComputeInitialHelloMessage(_SecBuffer *,_WST_CONTEXT *,ulong *)

- ea: `0x180008e60`
- end: `0x180009c92`
- name: `?WSTComputeInitialHelloMessage@@YAJPEAU_SecBuffer@@PEAU_WST_CONTEXT@@PEAK@Z`
- size: `3634`
- prototype: `__int64 __fastcall(struct _SecBuffer *, struct _WST_CONTEXT *, unsigned int *)`
- caller_count: `1`
- callee_count: `28`
- tags: `broker_com_uri`

## callers

- `0x18000a29c`

## callees

- `0x1800011b4`
- `0x180002694`
- `0x1800027e4`
- `0x1800028a0`
- `0x1800087d0`
- `0x180008ca0`
- `0x180008e60`
- `0x180009c98`
- `0x18000ba90`
- `0x18000bb08`
- `0x18000bd20`
- `0x18000be70`
- `0x18000c528`
- `0x18000ea54`
- `0x18000ebcc`
- `0x18000ec28`
- `0x180015824`
- `0x18001a390`
- `0x18001b9b0`
- `0x18001c154`
- `0x18001c378`
- `0x18001c8f8`
- `0x18001cac0`
- `0x18001ecd6`
- `0x18001ece2`
- `0x18001ed20`
- `0x18001edb0`
- `0x180020010`

## import_xrefs

- `CRYPTBASE!SystemFunction036` at `0x1800099fc`
- `CRYPTBASE!SystemFunction036` at `0x1800099fc`

## pseudocode

```c
__int64 __fastcall WSTComputeInitialHelloMessage(struct _SecBuffer *a1, struct _WST_CONTEXT *a2, unsigned int *a3)
{
  int active; // ebx
  unsigned __int64 v5; // rbx
  int *v6; // r15
  __int64 v7; // rcx
  unsigned __int64 v8; // rcx
  void *v9; // rsp
  void *v10; // rsp
  unsigned __int8 *v11; // rax
  unsigned __int8 *v12; // rbx
  unsigned int v13; // r12d
  _DWORD *v14; // r15
  struct _WST_SSP_PACKAGE **v15; // r13
  int v16; // r14d
  BOOL v17; // eax
  struct _WST_CONTEXT *v18; // rsi
  struct _WST_ACTIVE_ENGINE_CONTEXT *v19; // r14
  unsigned int v20; // esi
  __int64 v21; // r14
  char *v22; // rdx
  __int64 v23; // r9
  char *v24; // r8
  int v25; // eax
  struct _WST_SSP_PACKAGE *v26; // r8
  struct _WST_ACTIVE_ENGINE_CONTEXT **v27; // rcx
  unsigned int v28; // r14d
  unsigned int v29; // esi
  char *v30; // rax
  char *v31; // rbx
  _OWORD *v32; // rsi
  __int64 *i; // rcx
  unsigned __int8 *v34; // r8
  __int64 v35; // rax
  unsigned __int8 *v36; // rbx
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r8
  void *v40; // rcx
  unsigned int v41; // eax
  struct _WST_MESSAGE **v42; // rsi
  __int64 v43; // rcx
  struct _WST_MESSAGE *v44; // rax
  struct _WST_ACTIVE_ENGINE_CONTEXT *v45; // rax
  struct _WST_ACTIVE_ENGINE_CONTEXT *v46; // r14
  struct _WST_MESSAGE **v47; // rcx
  struct _WST_MESSAGE *v48; // rax
  _DWORD *v49; // rdi
  __int64 v50; // rax
  _BYTE *v51; // rcx
  char v53[8]; // [rsp+20h] [rbp-50h]
  int v54; // [rsp+70h] [rbp+0h] BYREF
  int v55; // [rsp+74h] [rbp+4h]
  char v56[8]; // [rsp+78h] [rbp+8h] BYREF
  void *Src; // [rsp+80h] [rbp+10h]
  unsigned int v58; // [rsp+88h] [rbp+18h]
  unsigned int v59; // [rsp+8Ch] [rbp+1Ch]
  unsigned int v60; // [rsp+90h] [rbp+20h] BYREF
  struct _WST_ACTIVE_ENGINE_CONTEXT *v61; // [rsp+98h] [rbp+28h] BYREF
  unsigned int v62; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v63; // [rsp+A8h] [rbp+38h] BYREF
  unsigned __int64 v64; // [rsp+B0h] [rbp+40h] BYREF
  struct _WST_MESSAGE *v65; // [rsp+B8h] [rbp+48h] BYREF
  struct _WST_SSP_PACKAGE **v66; // [rsp+C0h] [rbp+50h] BYREF
  unsigned __int8 *v67; // [rsp+C8h] [rbp+58h] BYREF
  int v68; // [rsp+D0h] [rbp+60h] BYREF
  unsigned int v69; // [rsp+D4h] [rbp+64h] BYREF
  unsigned int v70; // [rsp+D8h] [rbp+68h]
  unsigned __int8 *v71[3]; // [rsp+E0h] [rbp+70h] BYREF
  unsigned __int8 *v72[2]; // [rsp+F8h] [rbp+88h] BYREF
  struct _WST_SSP_PACKAGE **v73; // [rsp+108h] [rbp+98h]
  char *v74; // [rsp+110h] [rbp+A0h]
  __int64 v75[2]; // [rsp+120h] [rbp+B0h] BYREF
  __int64 v76; // [rsp+130h] [rbp+C0h]
  struct _WST_CONTEXT *v77; // [rsp+140h] [rbp+D0h]
  __int128 v78; // [rsp+148h] [rbp+D8h] BYREF
  __int128 v79; // [rsp+158h] [rbp+E8h] BYREF
  struct _WST_CONTEXT *v80; // [rsp+168h] [rbp+F8h]
  __int64 v81; // [rsp+170h] [rbp+100h] BYREF
  __int64 v82; // [rsp+178h] [rbp+108h] BYREF
  struct _WST_CONTEXT *v83; // [rsp+180h] [rbp+110h]
  _OWORD *v84; // [rsp+188h] [rbp+118h]

  v66 = 0;
  v62 = 0;
  v67 = 0;
  v79 = 0;
  v78 = 0;
  *(_OWORD *)v72 = 0;
  v65 = 0;
  v71[0] = 0;
  v69 = 0;
  v81 = 0;
  v63 = 0;
  v64 = 0;
  v60 = 0;
  active = WSTGetAllPackages(&v62, &v66);
  Src = 0;
  if ( active < 0 )
  {
    v70 = 0;
    goto LABEL_142;
  }
  ++*((_DWORD *)a2 + 35);
  v84 = (_OWORD *)((char *)a2 + 32);
  *((GUID *)a2 + 2) = WSTGlobalConversationId;
  *((_QWORD *)a2 + 4) += _InterlockedIncrement(&WSTGlobalCounter);
  v5 = *(unsigned int *)(*((_QWORD *)a2 + 3) + 28LL);
  v70 = v5;
  v6 = 0;
  if ( !(_DWORD)v5 || v5 > g_ulMaxStackAllocSize || v5 + g_ulAdditionalProbeSize + 8 < v5 )
  {
LABEL_11:
    if ( v6 )
      goto LABEL_15;
    goto LABEL_12;
  }
  if ( (unsigned int)VerifyStackAvailable() )
  {
    v7 = v5 + 23;
    if ( v5 + 23 <= v5 + 8 )
      v7 = 0xFFFFFFFFFFFFFF0LL;
    v8 = v7 & 0xFFFFFFFFFFFFFFF0uLL;
    v9 = alloca(v8);
    v10 = alloca(v8);
    v6 = &v54;
    Src = &v54;
  }
  if ( v6 )
  {
    *v6 = 1801679955;
    v6 += 2;
    Src = v6;
    goto LABEL_11;
  }
LABEL_12:
  if ( v5 + 8 >= v5 )
  {
    v11 = (unsigned __int8 *)((__int64 (*)(void))g_pfnAllocate)();
    v12 = v11;
    Src = v11;
    if ( v11 )
    {
      *(_DWORD *)v11 = 1885431112;
      v12 = v11 + 8;
      Src = v11 + 8;
    }
    goto LABEL_16;
  }
LABEL_15:
  v12 = (unsigned __int8 *)Src;
LABEL_16:
  v71[1] = v12;
  if ( !v12 )
  {
    active = -1073741801;
    goto LABEL_142;
  }
  v80 = a2;
  v74 = (char *)a2 + 24;
  v77 = a2;
  v83 = a2;
  v59 = 0;
  v55 = 0;
  memcpy_0(v12, (const void *)(*((_QWORD *)a2 + 3) + 16LL), *(unsigned int *)(*((_QWORD *)a2 + 3) + 28LL));
  v13 = 0;
  v58 = 0;
  v14 = (_DWORD *)((char *)a2 + 156);
  while ( v13 < v62 )
  {
    v15 = &v66[v13];
    v16 = *((_DWORD *)*v15 + 103);
    v68 = 0;
    active = (*(__int64 (__fastcall **)(int *))(*((_QWORD *)WSTGlobalBaseSSP + 30) + 432LL))(&v68);
    if ( active >= 0 )
      v17 = (v68 & 1) == 0 || (v16 & 0xC00000) != 0;
    else
      v17 = 0;
    if ( active < 0 )
      goto LABEL_142;
    if ( v17 )
    {
      v73 = v15;
      v18 = a2;
      v14 = (_DWORD *)((char *)a2 + 156);
      v71[2] = (unsigned __int8 *)a2 + 156;
      if ( !*((_DWORD *)a2 + 39) )
      {
        active = WSTIsPackageExcluded(
                   (struct _SECPKG_CREDENTIAL *)(*((_QWORD *)a2 + 3) + 16LL),
                   (struct _UNICODE_STRING *)((char *)*v15 + 376),
                   (int *)&v60);
        if ( active < 0 )
          goto LABEL_142;
        if ( v60 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2));
          goto LABEL_112;
        }
      }
      v63 = 0;
      v64 = 0;
      v19 = 0;
      v61 = 0;
      active = 0;
      v54 = 0;
      if ( !v55 )
      {
        active = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, _QWORD, _QWORD, __int64 *, __int64 *))v66[v13]
                  + 16))(
                   0,
                   *(unsigned int *)(*((_QWORD *)a2 + 3) + 68LL),
                   0,
                   *((_QWORD *)a2 + 3) + 16LL,
                   0,
                   0,
                   &v63,
                   &v81);
        v54 = active;
        v20 = *((_DWORD *)Src + 3);
        v21 = *((_QWORD *)a2 + 3);
        if ( memcmp_0(Src, (const void *)(v21 + 16), v20) )
          memcpy_0((void *)(v21 + 16), Src, v20);
        if ( active >= 0 )
        {
          v75[0] = (__int64)a2 + 156;
          if ( v71[0] )
          {
            WSTFree(v71[0]);
            v71[0] = 0;
          }
          v22 = (char *)v77 + 168;
          if ( !*v14 )
            v22 = 0;
          active = (*((__int64 (__fastcall **)(__int64, char *, _QWORD, unsigned int *, unsigned __int8 **, unsigned __int64 *))*v15
                    + 34))(
                     v63,
                     v22,
                     *((_DWORD *)a2 + 54) & (*v14 != 0 ? 0x107423F : 0),
                     &v69,
                     v71,
                     &v64);
          v54 = active;
          if ( active < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_DdDDdZ(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                *v14,
                *(_DWORD *)(*(_QWORD *)v74 + 44LL),
                *(_DWORD *)(*(_QWORD *)v74 + 40LL),
                *((_DWORD *)*v15 + 6),
                (__int64)*v15 + 376);
            goto LABEL_93;
          }
          if ( v69 )
          {
            active = WSTAddMetaDataMessage(a2, v71[0], v69, (struct _GUID *)((char *)*v15 + 392));
            v54 = active;
            if ( active < 0 )
            {
              v55 = 1;
              goto LABEL_93;
            }
          }
          active = WSTAllocateActiveEngineContext(*v15, v64, &v61);
          v54 = active;
          v19 = v61;
          if ( active >= 0 )
          {
            v64 = 0;
            *((_QWORD *)v61 + 6) = v63;
            v63 = 0;
            if ( *v14 && !v59 && (*((_BYTE *)*v15 + 408) & 1) != 0 )
            {
              LODWORD(v78) = 0;
              if ( a1 )
              {
                DWORD1(v78) = 1;
                *((_QWORD *)&v78 + 1) = a1;
              }
              else
              {
                DWORD1(v78) = 0;
              }
              v72[0] = (unsigned __int8 *)0x200000000LL;
              if ( v72[1] )
              {
                WSTFree(v72[1]);
                v72[1] = 0;
              }
              *(_QWORD *)&v79 = 0x100000000LL;
              *((_QWORD *)&v79 + 1) = v72;
              v56[0] = 0;
              v82 = 0;
              if ( (*(_BYTE *)(*(_QWORD *)v74 + 68LL) & 0x20) != 0 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_2c71e2299e853e517959ad87a3f04733_Traceguids);
                v55 = 1;
                active = -2146893042;
                v54 = -2146893042;
                v18 = a2;
              }
              else
              {
                v18 = a2;
                v23 = *((_DWORD *)a2 + 54) & (*v14 != 0 ? 0x107423F : 0);
                LODWORD(v23) = v23 | 0x100;
                v24 = (char *)v77 + 168;
                if ( !*v14 )
                  v24 = 0;
                *(_DWORD *)v53 = 0;
                active = (*((__int64 (__fastcall **)(_QWORD, _QWORD, char *, __int64, char *, __int128 *, __int64, __int128 *, unsigned int *, __int64 *, char *, __int64))*v15
                          + 22))(
                           *((_QWORD *)v19 + 6),
                           *((_QWORD *)v19 + 5),
                           v24,
                           v23,
                           *(char **)v53,
                           &v78,
                           (__int64)v19 + 40,
                           &v79,
                           a3,
                           &v82,
                           v56,
                           (__int64)v19 + 56);
                v54 = active;
                if ( active >= 0 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
                    WPP_SF_ddZdqZ(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      *((_DWORD *)*v15 + 6),
                      (__int64)*v15 + 376,
                      active,
                      (char)a2,
                      (__int64)a2 + 168);
                  if ( active == 590610 )
                  {
                    *((_DWORD *)v83 + 12) = 2;
                    *((_DWORD *)v19 + 21) = 0;
                  }
                  else
                  {
                    *((_DWORD *)v83 + 12) = 4;
                    *((_DWORD *)a2 + 13) = *a3;
                    *((_DWORD *)v19 + 21) = 1;
                  }
                  if ( (LODWORD(v72[0]) || active == 590610)
                    && (active = WSTAddTokenMessage(
                                   a2,
                                   v72[1],
                                   (unsigned int)v72[0],
                                   (struct _GUID *)((char *)*v15 + 392)),
                        v54 = active,
                        active < 0) )
                  {
                    v55 = 1;
                  }
                  else
                  {
                    active = WSTRetrieveSessionKeys(v19);
                    v54 = active;
                    if ( active >= 0 )
                    {
                      if ( *((_DWORD *)v19 + 24) )
                      {
                        v25 = 0x10000;
                        if ( !*v14 )
                          v25 = 0x20000;
                        *a3 |= v25;
                      }
                    }
                    else
                    {
                      v55 = 1;
                    }
                  }
                }
                else
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    WPP_SF_DdDDdZ(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      *v14,
                      *(_DWORD *)(*(_QWORD *)v74 + 44LL),
                      *(_DWORD *)(*(_QWORD *)v74 + 40LL),
                      *((_DWORD *)*v15 + 6),
                      (__int64)*v15 + 376);
                  v55 = 1;
                }
              }
              goto LABEL_95;
            }
          }
          else
          {
            v55 = 1;
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v18 = a2;
            WPP_SF_DdDDdZ(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              *v14,
              *(_DWORD *)(*((_QWORD *)a2 + 3) + 44LL),
              *(_DWORD *)(*((_QWORD *)a2 + 3) + 40LL),
              *((_DWORD *)*v15 + 6),
              (__int64)*v15 + 376);
            v19 = v61;
            goto LABEL_95;
          }
LABEL_93:
          v19 = v61;
        }
        v18 = a2;
      }
LABEL_95:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v26 = *v15;
        v75[1] = 16;
        v75[0] = (__int64)v26 + 392;
        WPP_SF_dqZDdZ_HEX_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (char)v18,
          (__int64)v18 + 168,
          active,
          *((_DWORD *)v26 + 6),
          (__int64)v26 + 376,
          (__int64)v75);
      }
      if ( v64 )
        (*((void (**)(void))*v15 + 24))();
      if ( v63 )
        (*((void (**)(void))*v15 + 18))();
      v64 = 0;
      if ( v55 )
      {
        if ( active >= 0 )
          active = -2146893042;
        goto LABEL_142;
      }
      if ( active < 0 )
      {
        if ( v19 )
          WSTFreeActiveEngineContext(v19);
LABEL_112:
        v58 = ++v13;
      }
      else
      {
        if ( !v19 )
        {
          active = -2146893042;
          goto LABEL_142;
        }
        v27 = (struct _WST_ACTIVE_ENGINE_CONTEXT **)*((_QWORD *)v18 + 8);
        if ( *v27 != (struct _WST_CONTEXT *)((char *)v18 + 56) )
          goto LABEL_140;
        *(_QWORD *)v19 = (char *)v18 + 56;
        *((_QWORD *)v19 + 1) = v27;
        *v27 = v19;
        *((_QWORD *)v18 + 8) = v19;
        ++v59;
        v58 = ++v13;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2));
      v14 = (_DWORD *)((char *)v80 + 156);
      v58 = ++v13;
    }
  }
  v28 = v59;
  if ( !v59 )
  {
    active = -2146893042;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        &WPP_2c71e2299e853e517959ad87a3f04733_Traceguids,
        *((unsigned int *)a2 + 39));
    goto LABEL_142;
  }
  v29 = 16 * (v59 + 6);
  v60 = v29;
  v30 = (char *)basessp::BaseSSP::WSTAllocate(WSTGlobalBaseSSP, v29);
  v31 = v30;
  v67 = (unsigned __int8 *)v30;
  if ( !v30 )
  {
    active = -1073741801;
    goto LABEL_142;
  }
  *((_DWORD *)v30 + 4) = 96;
  *((_DWORD *)v30 + 5) = v29;
  *(_QWORD *)v67 = 0x535458454F47454ELL;
  *((_DWORD *)v30 + 2) = *v14 == 0;
  *((_DWORD *)v30 + 3) = 0;
  *(_OWORD *)(v30 + 24) = *v84;
  if ( !SystemFunction036(v30 + 40, 0x20u) )
  {
    active = -1073741670;
    goto LABEL_142;
  }
  *((_DWORD *)v31 + 20) = 96;
  v32 = v31 + 96;
  for ( i = (__int64 *)*((_QWORD *)a2 + 7); i != (__int64 *)((char *)a2 + 56); i = (__int64 *)*i )
  {
    v34 = v67;
    v35 = *((unsigned __int16 *)v67 + 42);
    if ( (unsigned int)v35 < v28 )
    {
      v32[v35] = *(_OWORD *)(i + 3);
      ++*((_WORD *)v34 + 42);
    }
  }
  v36 = v67;
  v37 = *((unsigned __int16 *)v67 + 42);
  if ( !(_WORD)v37 )
  {
    *(_OWORD *)v75 = 0;
    v76 = 0;
    active = -2146893042;
    ((void (__fastcall *)(__int64 *))basessp::WSTGlobalLsaFunctions->GetCallInfo)(v75);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_Ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), v38, v39, 2148074254LL, v75[0], *v14);
    goto LABEL_142;
  }
  v40 = basessp::BaseSSP::WSTAllocate(WSTGlobalBaseSSP, 16 * v37);
  *((_QWORD *)a2 + 18) = v40;
  if ( !v40 )
  {
    active = -1073741801;
    goto LABEL_142;
  }
  v41 = *((unsigned __int16 *)v36 + 42);
  *((_WORD *)a2 + 76) = v41;
  memcpy_0(v40, v32, 16LL * v41);
  *(_OWORD *)((char *)a2 + 228) = *(_OWORD *)*((_QWORD *)a2 + 18);
  active = WSTAllocateWstMessage(&v67, &v60, &v65);
  if ( active >= 0 )
  {
    v42 = (struct _WST_MESSAGE **)((char *)a2 + 88);
    v43 = *((_QWORD *)a2 + 11);
    if ( *(struct _WST_CONTEXT **)(v43 + 8) != (struct _WST_CONTEXT *)((char *)a2 + 88) )
      goto LABEL_140;
    v44 = v65;
    *(_QWORD *)v65 = v43;
    *((_QWORD *)v44 + 1) = v42;
    *(_QWORD *)(v43 + 8) = v44;
    *v42 = v44;
    v65 = 0;
    if ( !*((_DWORD *)a2 + 12) )
      *((_DWORD *)a2 + 12) = 2;
    v45 = WSTGetActiveContextByAuthScheme(a2, (struct _GUID *)((char *)a2 + 228));
    v46 = v45;
    if ( v45 )
    {
      if ( *((_DWORD *)v45 + 24) )
      {
        active = WSTComputeVerifyMessage(a2, (struct _GUID *)((char *)a2 + 228), 0, &v65);
        if ( active >= 0 )
        {
          v47 = (struct _WST_MESSAGE **)*((_QWORD *)a2 + 12);
          if ( *v47 == (struct _WST_MESSAGE *)v42 )
          {
            v48 = v65;
            *(_QWORD *)v65 = v42;
            *((_QWORD *)v48 + 1) = v47;
            *v47 = v48;
            *((_QWORD *)a2 + 12) = v48;
            v65 = 0;
            *((_DWORD *)v46 + 18) = 1;
            goto LABEL_142;
          }
LABEL_140:
          __fastfail(3u);
        }
      }
    }
  }
LABEL_142:
  v49 = Src;
  if ( Src )
  {
    v50 = v70;
    v51 = Src;
    if ( v70 )
    {
      do
      {
        *v51++ = 0;
        --v50;
      }
      while ( v50 );
    }
    if ( *(v49 - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
  if ( v66 )
    WSTFreePackages(&v62, v66);
  if ( v72[1] )
    WSTFree(v72[1]);
  if ( v67 )
    WSTFree(v67);
  if ( v71[0] )
    WSTFree(v71[0]);
  return (unsigned int)active;
}

```

## disassembly

```asm
0x180008e60  mov     [rsp-8+arg_10], r8
0x180008e65  mov     [rsp-8+arg_8], rdx
0x180008e6a  mov     [rsp-8+arg_0], rcx
0x180008e6f  push    rbp
0x180008e70  push    rsi
0x180008e71  push    rdi
0x180008e72  push    r12
0x180008e74  push    r13
0x180008e76  push    r14
0x180008e78  push    r15
0x180008e7a  sub     rsp, 1A0h
0x180008e81  lea     rbp, [rsp+70h]
0x180008e86  mov     [rbp+160h+arg_18], rbx
0x180008e8d  mov     rax, cs:__security_cookie
0x180008e94  xor     rax, rbp
0x180008e97  mov     [rbp+160h+var_40], rax
0x180008e9e  mov     r13, rdx
0x180008ea1  xor     edi, edi
0x180008ea3  mov     [rbp+160h+var_110], rdi
0x180008ea7  mov     [rbp+160h+var_130], edi
0x180008eaa  mov     [rbp+160h+var_108], rdi
0x180008eae  xorps   xmm0, xmm0
0x180008eb1  movups  [rbp+160h+var_78], xmm0
0x180008eb8  xorps   xmm1, xmm1
0x180008ebb  movups  [rbp+160h+var_88], xmm1
0x180008ec2  movups  xmmword ptr [rbp+160h+var_D8], xmm0
0x180008ec9  mov     [rbp+160h+var_118], rdi
0x180008ecd  mov     [rbp+160h+var_F0], rdi
0x180008ed1  mov     [rbp+160h+var_FC], edi
0x180008ed4  mov     [rbp+160h+var_60], rdi
0x180008edb  mov     [rbp+160h+var_128], rdi
0x180008edf  mov     [rbp+160h+var_120], rdi
0x180008ee3  mov     [rbp+160h+var_140], edi
0x180008ee6  lea     rdx, [rbp+160h+var_110]; struct _WST_SSP_PACKAGE ***
0x180008eea  lea     rcx, [rbp+160h+var_130]; unsigned int *
0x180008eee  call    ?WSTGetAllPackages@@YAJPEAKPEAPEAPEAU_WST_SSP_PACKAGE@@@Z; WSTGetAllPackages(ulong *,_WST_SSP_PACKAGE * * *)
0x180008ef3  mov     ebx, eax
0x180008ef5  mov     [rbp+160h+Src], rdi
0x180008ef9  test    eax, eax
0x180008efb  js      loc_180009BEC
0x180008f01  inc     dword ptr [r13+8Ch]
0x180008f08  lea     rcx, [r13+20h]
0x180008f0c  mov     [rbp+160h+var_48], rcx
0x180008f13  movups  xmm0, xmmword ptr cs:?WSTGlobalConversationId@@3U_GUID@@A.Data1; _GUID WSTGlobalConversationId ...
0x180008f1a  movups  xmmword ptr [rcx], xmm0
0x180008f1d  mov     eax, 1
0x180008f22  lock xadd cs:?WSTGlobalCounter@@3JA, eax; long WSTGlobalCounter
0x180008f2a  inc     eax
0x180008f2c  cdqe
0x180008f2e  add     [rcx], rax
0x180008f31  lea     rsi, [r13+18h]
0x180008f35  mov     rax, [rsi]
0x180008f38  mov     ebx, [rax+1Ch]
0x180008f3b  mov     [rbp+160h+var_F8], ebx
0x180008f3e  mov     r15d, edi
0x180008f41  test    ebx, ebx
0x180008f43  jz      short loc_180008FAD
0x180008f45  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180008f4c  ja      short loc_180008FAD
0x180008f4e  mov     rcx, cs:g_ulAdditionalProbeSize
0x180008f55  add     rcx, 8
0x180008f59  add     rcx, rbx
0x180008f5c  cmp     rcx, rbx
0x180008f5f  jb      short loc_180008FAD
0x180008f61  call    VerifyStackAvailable
0x180008f66  test    eax, eax
0x180008f68  jz      short loc_180008F99
0x180008f6a  lea     rax, [rbx+8]
0x180008f6e  lea     rcx, [rax+0Fh]
0x180008f72  cmp     rcx, rax
0x180008f75  ja      short loc_180008F81
0x180008f77  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180008f81  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180008f85  mov     rax, rcx
0x180008f88  call    _alloca_probe
0x180008f8d  sub     rsp, rcx
0x180008f90  lea     r15, [rsp+1D0h+var_160]
0x180008f95  mov     [rbp+160h+Src], r15
0x180008f99  test    r15, r15
0x180008f9c  jz      short loc_180008FB2
0x180008f9e  mov     dword ptr [r15], 6B637453h
0x180008fa5  add     r15, 8
0x180008fa9  mov     [rbp+160h+Src], r15
0x180008fad  test    r15, r15
0x180008fb0  jnz     short loc_180008FE3
0x180008fb2  lea     rcx, [rbx+8]
0x180008fb6  cmp     rcx, rbx
0x180008fb9  jb      short loc_180008FE3
0x180008fbb  mov     rax, cs:g_pfnAllocate
0x180008fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fc7  mov     rbx, rax
0x180008fca  mov     [rbp+160h+Src], rax
0x180008fce  test    rax, rax
0x180008fd1  jz      short loc_180008FE7
0x180008fd3  mov     dword ptr [rax], 70616548h
0x180008fd9  add     rbx, 8
0x180008fdd  mov     [rbp+160h+Src], rbx
0x180008fe1  jmp     short loc_180008FE7
0x180008fe3  mov     rbx, [rbp+160h+Src]
0x180008fe7  mov     [rbp+160h+Buf1], rbx
0x180008feb  test    rbx, rbx
0x180008fee  jnz     short loc_180008FFA
0x180008ff0  mov     ebx, 0C0000017h
0x180008ff5  jmp     loc_180009BEF
0x180008ffa  mov     [rbp+160h+var_68], r13
0x180009001  mov     [rbp+160h+var_C0], rsi
0x180009008  mov     [rbp+160h+var_90], r13
0x18000900f  mov     [rbp+160h+var_50], r13
0x180009016  mov     [rbp+160h+var_144], edi
0x180009019  mov     [rbp+160h+var_15C], edi
0x18000901c  mov     rdx, [r13+18h]
0x180009020  add     rdx, 10h; Src
0x180009024  mov     r8d, [rdx+0Ch]; Size
0x180009028  mov     rcx, rbx; void *
0x18000902b  call    memcpy_0
0x180009030  mov     r12d, edi
0x180009033  mov     [rbp+160h+var_148], edi
0x180009036  lea     r15, [r13+9Ch]
0x18000903d  nop     dword ptr [rax]
0x180009040  cmp     r12d, [rbp+160h+var_130]
0x180009044  jnb     loc_180009934
0x18000904a  mov     eax, r12d
0x18000904d  lea     rsi, ds:0[rax*8]
0x180009055  mov     r13, [rbp+160h+var_110]
0x180009059  add     r13, rsi
0x18000905c  mov     rax, [r13+0]
0x180009060  mov     r14d, [rax+19Ch]
0x180009067  mov     [rbp+160h+var_100], edi
0x18000906a  mov     rax, cs:?WSTGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * WSTGlobalBaseSSP
0x180009071  mov     rcx, [rax+0F0h]
0x180009078  mov     rax, [rcx+1B0h]
0x18000907f  lea     rcx, [rbp+160h+var_100]
0x180009083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009088  mov     ebx, eax
0x18000908a  test    eax, eax
0x18000908c  jns     short loc_180009092
0x18000908e  mov     eax, edi
0x180009090  jmp     short loc_1800090AB
0x180009092  test    byte ptr [rbp+160h+var_100], 1
0x180009096  jz      short loc_1800090A6
0x180009098  test    r14d, 0C00000h
0x18000909f  mov     eax, edi
0x1800090a1  setnz   al
0x1800090a4  jmp     short loc_1800090AB
0x1800090a6  mov     eax, 1
0x1800090ab  test    ebx, ebx
0x1800090ad  js      loc_180009BEF
0x1800090b3  test    eax, eax
0x1800090b5  jnz     short loc_18000910E
0x1800090b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090be  lea     rax, WPP_GLOBAL_Control
0x1800090c5  cmp     rcx, rax
0x1800090c8  jz      short loc_1800090F4
0x1800090ca  test    byte ptr [rcx+1Ch], 2
0x1800090ce  jz      short loc_1800090F4
0x1800090d0  mov     rax, [rbp+160h+var_110]
0x1800090d4  mov     r9, [rsi+rax]
0x1800090d8  add     r9, 178h
0x1800090df  mov     edx, 12h
0x1800090e4  lea     r8, WPP_2c71e2299e853e517959ad87a3f04733_Traceguids
0x1800090eb  mov     rcx, [rcx+10h]; LoggerHandle
0x1800090ef  call    WPP_SF_Z
0x1800090f4  mov     r15, [rbp+160h+var_68]
0x1800090fb  add     r15, 9Ch
0x180009102  inc     r12d
0x180009105  mov     [rbp+160h+var_148], r12d
0x180009109  jmp     loc_180009040
0x18000910e  mov     [rbp+160h+var_C8], r13
0x180009115  mov     rsi, [rbp+160h+arg_8]
0x18000911c  lea     r15, [rsi+9Ch]
0x180009123  mov     [rbp+160h+var_E0], r15
0x18000912a  cmp     dword ptr [r15], 0
0x18000912e  jnz     short loc_1800091A9
0x180009130  mov     rdx, [r13+0]
0x180009134  add     rdx, 178h; struct _UNICODE_STRING *
0x18000913b  mov     rcx, [rsi+18h]
0x18000913f  add     rcx, 10h; struct _SECPKG_CREDENTIAL *
0x180009143  lea     r8, [rbp+160h+var_140]; int *
0x180009147  call    ?WSTIsPackageExcluded@@YAJPEAU_SECPKG_CREDENTIAL@@PEAU_UNICODE_STRING@@PEAH@Z; WSTIsPackageExcluded(_SECPKG_CREDENTIAL *,_UNICODE_STRING *,int *)
0x18000914c  mov     ebx, eax
0x18000914e  test    eax, eax
0x180009150  js      loc_180009BEF
0x180009156  cmp     [rbp+160h+var_140], 0
0x18000915a  jz      short loc_1800091A9
0x18000915c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009163  lea     rax, WPP_GLOBAL_Control
0x18000916a  cmp     rcx, rax
0x18000916d  jz      loc_180009928
0x180009173  test    byte ptr [rcx+1Ch], 2
0x180009177  jz      loc_180009928
0x18000917d  mov     edx, r12d
0x180009180  mov     rax, [rbp+160h+var_110]
0x180009184  mov     r9, [rax+rdx*8]
0x180009188  add     r9, 178h
0x18000918f  mov     edx, 13h
0x180009194  lea     r8, WPP_2c71e2299e853e517959ad87a3f04733_Traceguids
0x18000919b  mov     rcx, [rcx+10h]; LoggerHandle
0x18000919f  call    WPP_SF_Z
0x1800091a4  jmp     loc_180009928
0x1800091a9  mov     [rbp+160h+var_128], rdi
0x1800091ad  mov     [rbp+160h+var_120], rdi
0x1800091b1  mov     r14, rdi
0x1800091b4  mov     [rbp+160h+var_138], rdi
0x1800091b8  mov     ebx, edi
0x1800091ba  mov     [rbp+160h+var_160], ebx
0x1800091bd  cmp     [rbp+160h+var_15C], 0
0x1800091c1  jnz     loc_1800097D5
0x1800091c7  mov     rdx, [rsi+18h]
0x1800091cb  mov     ecx, r12d
0x1800091ce  mov     rax, [rbp+160h+var_110]
0x1800091d2  mov     r8, [rax+rcx*8]
0x1800091d6  lea     r9, [rdx+10h]
0x1800091da  mov     rax, [r8+80h]
0x1800091e1  lea     rcx, [rbp+160h+var_60]
0x1800091e8  mov     qword ptr [rsp+1D0h+var_198], rcx
0x1800091ed  lea     rcx, [rbp+160h+var_128]
0x1800091f1  mov     qword ptr [rsp+1D0h+var_1A0], rcx
0x1800091f6  mov     qword ptr [rsp+1D0h+var_1A8], rdi
0x1800091fb  mov     qword ptr [rsp+1D0h+var_1B0], rdi
0x180009200  xor     r8d, r8d
0x180009203  mov     edx, [rdx+44h]
0x180009206  xor     ecx, ecx
0x180009208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000920d  mov     ebx, eax
0x18000920f  mov     [rbp+160h+var_160], eax
0x180009212  mov     rcx, [rbp+160h+Src]
0x180009216  jmp     short loc_180009239
0x180009218  mov     ebx, eax
0x18000921a  mov     [rbp+160h+var_160], eax
0x18000921d  xor     edi, edi
0x18000921f  mov     rcx, [rbp+160h+Buf1]; Buf1
0x180009223  mov     [rbp+160h+Src], rcx
0x180009227  mov     r12d, [rbp+160h+var_148]
0x18000922b  mov     r13, [rbp+160h+var_C8]
0x180009232  mov     r15, [rbp+160h+var_E0]
0x180009239  mov     esi, [rcx+0Ch]
0x18000923c  mov     r9, [rbp+160h+arg_8]
0x180009243  mov     r14, [r9+18h]
0x180009247  mov     r8d, esi; Size
0x18000924a  lea     rdx, [r14+10h]; Buf2
0x18000924e  call    memcmp_0
0x180009253  test    eax, eax
0x180009255  jz      short loc_180009267
0x180009257  mov     r8d, esi; Size
0x18000925a  mov     rdx, [rbp+160h+Src]; Src
0x18000925e  lea     rcx, [r14+10h]; void *
0x180009262  call    memcpy_0
0x180009267  test    ebx, ebx
0x180009269  jns     short loc_1800092E0
0x18000926b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009272  lea     rax, WPP_GLOBAL_Control
0x180009279  cmp     rcx, rax
0x18000927c  jz      loc_1800097CA
0x180009282  test    byte ptr [rcx+1Ch], 2
0x180009286  jz      loc_1800097CA
0x18000928c  mov     rsi, [rbp+160h+arg_8]
0x180009293  mov     r9, [rsi+18h]
0x180009297  mov     r8, [r13+0]
0x18000929b  lea     rax, [r8+178h]
0x1800092a2  mov     edx, 14h
0x1800092a7  mov     [rsp+1D0h+var_190], rax; __int64
0x1800092ac  mov     eax, [r8+18h]
0x1800092b0  mov     dword ptr [rsp+1D0h+var_198], eax; char
0x1800092b4  mov     eax, [r9+28h]
0x1800092b8  mov     dword ptr [rsp+1D0h+var_1A0], eax; char
0x1800092bc  mov     eax, [r9+2Ch]
0x1800092c0  mov     dword ptr [rsp+1D0h+var_1A8], eax; char
0x1800092c4  mov     eax, [r15]
0x1800092c7  mov     dword ptr [rsp+1D0h+var_1B0], eax; char
0x1800092cb  mov     r9d, ebx
0x1800092ce  mov     rcx, [rcx+10h]; LoggerHandle
0x1800092d2  call    WPP_SF_DdDDdZ
0x1800092d7  mov     r14, [rbp+160h+var_138]
0x1800092db  jmp     loc_1800097D5
0x1800092e0  mov     rsi, r15
0x1800092e3  mov     [rbp+160h+var_B0], r15
0x1800092ea  mov     rcx, [rbp+160h+var_F0]; void *
0x1800092ee  test    rcx, rcx
0x1800092f1  jz      short loc_1800092FC
0x1800092f3  call    ?WSTFree@@YAXPEAX@Z; WSTFree(void *)
0x1800092f8  mov     [rbp+160h+var_F0], rdi
0x1800092fc  mov     ecx, [r15]
0x1800092ff  mov     r10, [r13+0]
0x180009303  mov     eax, ecx
0x180009305  neg     eax
0x180009307  sbb     r8d, r8d
0x18000930a  and     r8d, 107423Fh
0x180009311  mov     r14, [rbp+160h+arg_8]
0x180009318  and     r8d, [r14+0D8h]
0x18000931f  mov     rdx, [rbp+160h+var_90]
0x180009326  add     rdx, 0A8h
0x18000932d  test    ecx, ecx
0x18000932f  cmovz   rdx, rdi
0x180009333  lea     rax, [rbp+160h+var_120]
0x180009337  mov     qword ptr [rsp+1D0h+var_1A8], rax
0x18000933c  lea     rax, [rbp+160h+var_F0]
0x180009340  mov     qword ptr [rsp+1D0h+var_1B0], rax
0x180009345  lea     r9, [rbp+160h+var_FC]
0x180009349  mov     rcx, [rbp+160h+var_128]
0x18000934d  mov     rax, [r10+110h]
  ... truncated ...
```
