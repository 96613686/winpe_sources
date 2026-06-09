# WSTProcessContextLevelTokens(int,unsigned __int64,unsigned __int64,_UNICODE_STRING *,ulong,ulong,_SecBufferDesc *,unsigned __int64 *,_SecBufferDesc *,ulong *,_LARGE_INTEGER *,uchar *,_SecBuffer *)

- ea: `0x18000a29c`
- end: `0x18000b558`
- name: `?WSTProcessContextLevelTokens@@YAJH_K0PEAU_UNICODE_STRING@@KKPEAU_SecBufferDesc@@PEA_K2PEAKPEAT_LARGE_INTEGER@@PEAEPEAU_SecBuffer@@@Z`
- size: `4796`
- prototype: `__int64 __fastcall(int, unsigned __int64, struct _WST_CONTEXT *, struct _UNICODE_STRING *, unsigned int, unsigned int, struct _SecBufferDesc *, unsigned __int64 *, struct _SecBufferDesc *, unsigned int *, union _LARGE_INTEGER *, unsigned __int8 *, struct _SecBuffer *)`
- caller_count: `2`
- callee_count: `35`
- tags: `broker_com_uri`

## callers

- `0x18000a020`
- `0x18000a160`

## callees

- `0x180001414`
- `0x1800027e4`
- `0x180002970`
- `0x180003250`
- `0x180004230`
- `0x1800070d0`
- `0x180008e60`
- `0x180009db0`
- `0x18000a29c`
- `0x18000bc0c`
- `0x18000bde0`
- `0x18000c528`
- `0x18000ca08`
- `0x18000ebcc`
- `0x18000ec28`
- `0x18000ec70`
- `0x180015150`
- `0x180015608`
- `0x1800157d8`
- `0x180015824`
- `0x1800158ec`
- `0x1800159d8`
- `0x180015aa8`
- `0x180015bc0`
- `0x180015ce4`
- `0x180015e08`
- `0x180015e5c`
- `0x180015f80`
- `0x180016824`
- `0x18001a3b4`
- `0x18001bba4`
- `0x18001cff0`
- `0x18001d024`
- `0x18001ece2`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall WSTProcessContextLevelTokens(
        int a1,
        unsigned __int64 a2,
        struct _WST_CONTEXT *a3,
        struct _UNICODE_STRING *a4,
        unsigned int a5,
        unsigned int a6,
        struct _SecBufferDesc *a7,
        unsigned __int64 *a8,
        struct _SecBufferDesc *a9,
        unsigned int *a10,
        union _LARGE_INTEGER *a11,
        unsigned __int8 *a12,
        struct _SecBuffer *a13)
{
  int v13; // esi
  struct _SecBuffer *v14; // rbx
  void *v15; // r13
  char IsEnabled; // al
  struct _WST_CONTEXT *pBuffers; // r8
  unsigned int cBuffers; // edx
  struct _SecBuffer *v19; // r15
  struct _SecBuffer *v20; // rdi
  int v21; // eax
  int v22; // eax
  int v23; // ebx
  int v24; // eax
  struct _SecBuffer *v25; // r13
  basessp::BaseSSP *v26; // rcx
  unsigned int v27; // r15d
  __int64 v28; // rsi
  struct _SecBuffer *v29; // rdi
  int v30; // eax
  _QWORD *v31; // rcx
  __int64 v32; // rdx
  unsigned int v33; // ecx
  int v34; // eax
  int v35; // eax
  int v36; // eax
  PSecBuffer v37; // rdx
  unsigned __int64 v38; // rsi
  unsigned int v39; // edx
  struct _SecBuffer *v40; // rdi
  struct _WST_CONTEXT *v41; // rbx
  basessp::BaseSSP *v42; // rcx
  _QWORD *v43; // rcx
  __int64 v44; // rdx
  unsigned int *v45; // r15
  unsigned __int64 *v46; // rsi
  unsigned __int64 v47; // rax
  __int64 v48; // rcx
  int v49; // ecx
  __int64 v50; // rdx
  struct basessp::_WST_CREDENTIAL *v51; // r15
  struct _WST_CONTEXT *v52; // r9
  __int64 v53; // r8
  int v54; // r11d
  char v55; // r10
  struct _WST_CONTEXT *v56; // rax
  struct _WST_CONTEXT *v57; // rcx
  char *v58; // rax
  struct _WST_CONTEXT **v59; // rdx
  _QWORD *v60; // rcx
  __int64 v61; // rdx
  struct _UNICODE_STRING *v62; // rbx
  struct _WST_CONTEXT *v63; // rax
  struct _WST_CONTEXT *v64; // rax
  struct _WST_CONTEXT *v65; // rcx
  struct basessp::_WST_CREDENTIAL *v66; // rdx
  char *v67; // rax
  struct _WST_CONTEXT **v68; // rdx
  basessp::BaseSSP *v69; // rcx
  int v70; // eax
  __int64 v71; // r8
  struct _SecBuffer *v72; // rcx
  _QWORD *v73; // rcx
  struct _SecBuffer *v74; // rcx
  int v75; // ecx
  BOOL v76; // r15d
  struct _WST_CONTEXT **cbBuffer; // rdx
  _QWORD *v78; // rcx
  __int64 v79; // rdx
  int v80; // r8d
  int v81; // eax
  __int64 v82; // rdx
  unsigned int v83; // ebx
  struct _SecBuffer *v84; // rsi
  void *pvBuffer; // rcx
  struct _WST_ACTIVE_ENGINE_CONTEXT *v86; // rax
  struct _WST_CONTEXT *v87; // rax
  struct _WST_CONTEXT *v89; // [rsp+58h] [rbp-71h] BYREF
  void *v90; // [rsp+60h] [rbp-69h]
  struct basessp::_WST_CREDENTIAL *v91; // [rsp+68h] [rbp-61h]
  char v92[16]; // [rsp+70h] [rbp-59h] BYREF
  __int64 v93; // [rsp+80h] [rbp-49h]
  struct basessp::_WST_CREDENTIAL *v94; // [rsp+88h] [rbp-41h] BYREF
  struct _SecBuffer *v95; // [rsp+90h] [rbp-39h]
  void *Src; // [rsp+98h] [rbp-31h] BYREF
  size_t Size; // [rsp+A0h] [rbp-29h] BYREF
  struct _SecBuffer *v98; // [rsp+A8h] [rbp-21h]
  struct _SecBuffer *v99; // [rsp+B0h] [rbp-19h]
  struct _SecBuffer *v100; // [rsp+B8h] [rbp-11h]
  struct _SecBuffer *v101; // [rsp+C0h] [rbp-9h]
  unsigned int v106; // [rsp+140h] [rbp+77h]

  v13 = 0;
  v14 = 0;
  v91 = 0;
  v94 = 0;
  v15 = 0;
  v89 = 0;
  *a12 = 0;
  LODWORD(Size) = 0;
  v90 = 0;
  Src = 0;
  v99 = 0;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NegoLateFallback>::GetImpl'::`2'::impl);
  cBuffers = a9->cBuffers;
  if ( IsEnabled )
  {
    pBuffers = 0;
    v98 = 0;
    v19 = 0;
    if ( cBuffers )
    {
      while ( 1 )
      {
        v20 = &a9->pBuffers[v13];
        v21 = v20->BufferType & 0xFFFFFFF;
        if ( v21 == 2 )
        {
          if ( v19 )
          {
            v23 = -1073741811;
            v31 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v32 = 10;
              goto LABEL_26;
            }
            goto LABEL_72;
          }
          v22 = ((__int64 (__fastcall *)(struct _SecBuffer *, struct _SecBuffer *, _QWORD))basessp::WSTGlobalLsaFunctions->MapBuffer)(
                  &a9->pBuffers[v13],
                  &a9->pBuffers[v13],
                  0);
          pBuffers = 0;
          v23 = v22;
          if ( v22 < 0 )
            goto LABEL_72;
          v14 = v99;
          v19 = v20;
          v98 = v20;
        }
        else if ( v21 == 12 )
        {
          if ( v14 )
          {
            v23 = -1073741811;
            v31 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v32 = 11;
              goto LABEL_26;
            }
            goto LABEL_72;
          }
          v24 = ((__int64 (__fastcall *)(struct _SecBuffer *, struct _SecBuffer *, _QWORD))basessp::WSTGlobalLsaFunctions->MapBuffer)(
                  &a9->pBuffers[v13],
                  &a9->pBuffers[v13],
                  0);
          pBuffers = 0;
          v23 = v24;
          if ( v24 < 0 )
            goto LABEL_72;
          v14 = v20;
          v99 = v20;
        }
        if ( ++v13 >= a9->cBuffers )
        {
          v13 = 0;
          goto LABEL_13;
        }
      }
    }
    goto LABEL_34;
  }
  if ( cBuffers )
  {
    pBuffers = (struct _WST_CONTEXT *)a9->pBuffers;
    v33 = 0;
    while ( 1 )
    {
      v19 = (struct _SecBuffer *)((char *)pBuffers + 16 * v33);
      v98 = v19;
      if ( (v19->BufferType & 0xFFFFFFF) == 2 )
        break;
      if ( ++v33 >= cBuffers )
        goto LABEL_34;
    }
    v23 = ((__int64 (__fastcall *)(char *, char *))basessp::WSTGlobalLsaFunctions->MapBuffer)(
            (char *)pBuffers + 16 * v33,
            (char *)pBuffers + 16 * v33);
    if ( v23 < 0 )
      goto LABEL_72;
LABEL_13:
    if ( v19 )
    {
      v95 = 0;
      v25 = 0;
      v101 = 0;
      v100 = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NegoLateFallback>::GetImpl'::`2'::impl) )
      {
        if ( a7 )
        {
          v27 = 0;
          if ( a7->cBuffers )
          {
            while ( 1 )
            {
              v28 = v27;
              v29 = &a7->pBuffers[v28];
              v30 = v29->BufferType & 0xFFFFFFF;
              if ( v30 == 14 )
                break;
              switch ( v30 )
              {
                case 2:
                  v34 = ((__int64 (__fastcall *)(struct _SecBuffer *, struct _SecBuffer *))basessp::WSTGlobalLsaFunctions->MapBuffer)(
                          &a7->pBuffers[v28],
                          &a7->pBuffers[v28]);
                  v13 = 0;
                  v23 = v34;
                  if ( v34 < 0 )
                    goto LABEL_71;
                  v25 = v29;
                  break;
                case 11:
                  v35 = ((__int64 (__fastcall *)(struct _SecBuffer *, struct _SecBuffer *))basessp::WSTGlobalLsaFunctions->MapBuffer)(
                          &a7->pBuffers[v28],
                          &a7->pBuffers[v28]);
                  v13 = 0;
                  v23 = v35;
                  if ( v35 < 0 )
                    goto LABEL_71;
                  v101 = v29;
                  break;
                case 12:
                  v36 = ((__int64 (__fastcall *)(struct _SecBuffer *, struct _SecBuffer *))basessp::WSTGlobalLsaFunctions->MapBuffer)(
                          &a7->pBuffers[v28],
                          &a7->pBuffers[v28]);
                  v13 = 0;
                  v23 = v36;
                  if ( v36 < 0 )
                    goto LABEL_71;
                  v100 = v29;
                  break;
                default:
                  goto LABEL_20;
              }
LABEL_21:
              if ( ++v27 >= a7->cBuffers )
                goto LABEL_64;
            }
            v23 = ((__int64 (__fastcall *)(struct _SecBuffer *, struct _SecBuffer *))basessp::WSTGlobalLsaFunctions->MapBuffer)(
                    &a7->pBuffers[v28],
                    &a7->pBuffers[v28]);
            if ( v23 < 0 )
              goto LABEL_71;
            v95 = &a7->pBuffers[v28];
LABEL_20:
            v13 = 0;
            goto LABEL_21;
          }
        }
      }
      else if ( a7 )
      {
        if ( a7->cBuffers )
        {
          v37 = a7->pBuffers;
          LODWORD(v26) = 0;
          while ( 1 )
          {
            v38 = (unsigned int)v26;
            pBuffers = (struct _WST_CONTEXT *)&v37[v38];
            if ( (v37[v38].BufferType & 0xFFFFFFF) == 0xE )
              break;
            v26 = (basessp::BaseSSP *)(unsigned int)((_DWORD)v26 + 1);
            if ( (unsigned int)v26 >= a7->cBuffers )
              goto LABEL_56;
          }
          v23 = ((__int64 (__fastcall *)(struct _WST_CONTEXT *, struct _SecBuffer *))basessp::WSTGlobalLsaFunctions->MapBuffer)(
                  pBuffers,
                  &v37[v38]);
          if ( v23 < 0 )
            goto LABEL_71;
          v95 = &a7->pBuffers[v38];
LABEL_56:
          v13 = 0;
        }
        v39 = a7->cBuffers;
        if ( v39 )
        {
          pBuffers = (struct _WST_CONTEXT *)a7->pBuffers;
          LODWORD(v26) = 0;
          while ( 1 )
          {
            v40 = (struct _SecBuffer *)((char *)pBuffers + 16 * (unsigned int)v26);
            if ( (v40->BufferType & 0xFFFFFFF) == 2 )
              break;
            v26 = (basessp::BaseSSP *)(unsigned int)((_DWORD)v26 + 1);
            if ( (unsigned int)v26 >= v39 )
              goto LABEL_64;
          }
          v23 = ((__int64 (__fastcall *)(char *, char *))basessp::WSTGlobalLsaFunctions->MapBuffer)(
                  (char *)pBuffers + 16 * (unsigned int)v26,
                  (char *)pBuffers + 16 * (unsigned int)v26);
          if ( v23 < 0 )
            goto LABEL_71;
          v25 = v40;
        }
      }
LABEL_64:
      v41 = a3;
      v106 = 0;
      v89 = a3;
      if ( a3 )
      {
        WSTReferenceContext(a3);
        v42 = (basessp::BaseSSP *)(unsigned int)_InterlockedIncrement((volatile signed __int32 *)v89 + 2);
        if ( (int)v42 > 1 )
        {
          v43 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_70;
          v44 = 13;
LABEL_69:
          WPP_SF_qd(v43[2], v44);
LABEL_70:
          v23 = -2146893054;
LABEL_71:
          v15 = v90;
          goto LABEL_72;
        }
        if ( !a1 )
        {
LABEL_134:
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NegoLateFallback>::GetImpl'::`2'::impl)
            && (!v25 || !v25->cbBuffer)
            && (!v100 || !v100->cbBuffer)
            && !*((_DWORD *)v89 + 62) )
          {
            if ( v41 )
            {
              v23 = -1073741811;
              v60 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                goto LABEL_71;
              v61 = 22;
              goto LABEL_144;
            }
            v45 = a10;
            v72 = v95;
            *((_DWORD *)v89 + 34) = 1;
            v23 = WSTComputeInitialHelloMessage(v72, v89, a10);
            if ( v23 < 0 )
            {
              v93 = 0;
              *(_OWORD *)v92 = 0;
              ((void (__fastcall *)(char *))basessp::WSTGlobalLsaFunctions->GetCallInfo)(v92);
              v73 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                goto LABEL_71;
              goto LABEL_193;
            }
            goto LABEL_243;
          }
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NegoLateFallback>::GetImpl'::`2'::impl)
            && (!v25 || !v25->cbBuffer)
            && !*((_DWORD *)v89 + 62) )
          {
            if ( !v41 )
            {
              v45 = a10;
              v74 = v95;
              *((_DWORD *)v89 + 34) = 1;
              v23 = WSTComputeInitialHelloMessage(v74, v89, a10);
              if ( v23 < 0 )
              {
                v93 = 0;
                *(_OWORD *)v92 = 0;
                ((void (__fastcall *)(char *))basessp::WSTGlobalLsaFunctions->GetCallInfo)(v92);
                v73 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                  goto LABEL_71;
LABEL_193:
                WPP_SF_ZDd(v73[2], v23, v92[0]);
                goto LABEL_71;
              }
LABEL_243:
              v81 = WSTExtractMessagesToSend(v89, (unsigned __int8 **)&Src, (unsigned int *)&Size);
              v23 = v81;
              if ( v81 < 0 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    31,
                    &WPP_6fa7dbc14d303f0b349d28a6dba66ee3_Traceguids,
                    (unsigned int)v81);
LABEL_253:
                v15 = Src;
                goto LABEL_72;
              }
              v83 = Size;
              v84 = v98;
              if ( (a5 & 0x100) != 0 )
              {
                v98->pvBuffer = Src;
                *v45 |= 0x100u;
                v15 = 0;
                v90 = 0;
              }
              else
              {
                if ( v98->cbBuffer < (unsigned int)Size )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    WPP_SF_ddsd(*((_QWORD *)WPP_GLOBAL_Control + 2), v82, pBuffers, v98->cbBuffer, Size);
                  v84->cbBuffer = v83;
                  v23 = -1073741789;
                  goto LABEL_253;
                }
                v15 = Src;
                pvBuffer = v98->pvBuffer;
                v90 = Src;
                memcpy_0(pvBuffer, Src, (unsigned int)Size);
                *v45 &= ~0x100u;
              }
              v84->cbBuffer = v83;
              v86 = WSTGetActiveContextByAuthScheme(v89, (struct _GUID *)((char *)v89 + 228));
              if ( !v86 )
              {
                v23 = -2146893052;
                goto LABEL_72;
              }
              if ( *((_DWORD *)v86 + 21) && *((_DWORD *)v86 + 18) && *((_DWORD *)v86 + 19) )
              {
                v23 = NegoExtsMapLsaModeContext(
                        (struct _GUID *)((char *)v86 + 24),
                        (struct _SecBuffer *)((char *)v86 + 56),
                        a13);
                if ( v23 < 0 )
                  goto LABEL_71;
                v23 = 0;
                *a12 = 1;
                *((_DWORD *)v89 + 12) = 5;
                if ( *((_DWORD *)v89 + 39) && !*((_DWORD *)v89 + 66) && !*((_DWORD *)v89 + 67) )
                {
                  WSTContextByTargetTableInsertEx(NegoExtsGlobalWillNever, v89);
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                    WPP_SF_qDDZ(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      *(_DWORD *)(*((_QWORD *)v89 + 3) + 44LL),
                      *(_DWORD *)(*((_QWORD *)v89 + 3) + 40LL),
                      (__int64)v89 + 168);
                  *((_DWORD *)v89 + 66) = 1;
                }
              }
              else
              {
                a11->QuadPart = 0x7FFFFF36D5969FFFLL;
                if ( !v83 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_6fa7dbc14d303f0b349d28a6dba66ee3_Traceguids);
                  v23 = -1073741637;
                  goto LABEL_72;
                }
                v23 = 590610;
              }
              v87 = v89;
              if ( *((_DWORD *)v89 + 39) && (*((_DWORD *)v89 + 54) & 0x1000000) != 0 )
                *v45 |= 0x1000000u;
              if ( v106 && *((_DWORD *)v87 + 39) && *((_DWORD *)v89 + 34) )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2));
                *v45 |= 0x1000u;
              }
              v46 = a8;
              *a8 = (unsigned __int64)v89;
LABEL_75:
              if ( !v89 )
                goto LABEL_289;
              *((_DWORD *)v89 + 55) = v23;
              _InterlockedDecrement((volatile signed __int32 *)v89 + 2);
              if ( !a3 && v23 >= 0 )
                goto LABEL_289;
              if ( v23 < 0 )
              {
                pBuffers = v89;
                if ( !*((_DWORD *)v89 + 39)
                  || !*((_DWORD *)v89 + 65) && !*((_WORD *)v89 + 76)
                  || (unsigned int)(v23 + 1067646974) > 2
                  && v23 != -799211518
                  && ((v47 = (unsigned int)(v23 + 2147023631), (unsigned int)v47 > 0x3D)
                   || (v48 = 0x2010800000000081LL, !_bittest64(&v48, v47)))
                  && v23 != -1067646970
                  && v23 != -799211514
                  && v23 != -2147022959
                  && ((v49 = 280609, (unsigned int)(v23 + 1073741729) > 0x12) || !_bittest(&v49, v23 + 1073741729))
                  && ((unsigned int)(v23 + 805306273) > 0x12 || !_bittest(&v49, v23 + 805306273))
                  && v23 != -2147024891
                  && v23 != -1073741790
                  && v23 != -805306334
                  && v23 != -2147024810
                  && v23 != -2146893042
                  && v23 != -2146893044
                  && v23 != -2146892959
                  && v23 != -1073740755
                  && v23 != -1073740920
                  && v23 != -805305464
                  && v23 != -2146892976
                  && v23 != -2147023566
                  && v23 != -2147022989
                  && v23 != -1073741276
                  && v23 != -805305820
                  && v23 != -2147022654
                  && (*((_DWORD *)v89 + 12) == 7
                   || !*((_DWORD *)v89 + 12)
                   || !*((_DWORD *)v89 + 62)
                   || (unsigned int)WSTIsExplicitCredentials((struct _SECPKG_CREDENTIAL *)(*((_QWORD *)v89 + 3) + 16LL))) )
                {
LABEL_287:
                  if ( pBuffers )
                    WSTDereferenceContext(pBuffers);
                  goto LABEL_289;
                }
                WSTContextByTargetTableInsert(pBuffers);
                if ( !a3 )
                {
                  v23 = 590610;
                  *v46 = (unsigned __int64)v89;
                  pBuffers = 0;
                  *v45 |= 0x8000000u;
                  v89 = 0;
                  goto LABEL_287;
                }
              }
              pBuffers = v89;
              goto LABEL_287;
            }
            v23 = -1073741811;
            v60 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_71;
            v61 = 24;
LABEL_144:
            WPP_SF_(v60[2], v61, &WPP_6fa7dbc14d303f0b349d28a6dba66ee3_Traceguids);
            goto LABEL_71;
          }
          v75 = *((_DWORD *)v89 + 62);
          if ( v75 && v25 && v25->cbBuffer )
          {
            v23 = -1073741811;
            v60 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_71;
            v61 = 26;
            goto LABEL_144;
          }
          if ( v41 )
          {
            LODWORD(v41) = 0;
            v76 = *((_DWORD *)v89 + 40) == 0;
          }
          else
          {
            v13 = 1;
            v76 = 1;
          }
          if ( v75 )
            goto LABEL_231;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NegoLateFallback>::GetImpl'::`2'::impl) )
          {
            if ( !v25 || (cbBuffer = (struct _WST_CONTEXT **)v25->cbBuffer, !(_DWORD)cbBuffer) )
            {
LABEL_229:
              if ( *((_DWORD *)v89 + 12) != (_DWORD)v41 )
              {
                v106 = v13;
                v13 = (int)v41;
              }
LABEL_231:
              v80 = *((_DWORD *)v89 + 62);
              if ( v80 == 1 || !v80 && v13 )
              {
                v45 = a10;
                v23 = WSTProcessInitialHelloMessage(v95, v89, a10);
                if ( v23 >= 0 )
                  goto LABEL_243;
                v93 = 0;
                *(_OWORD *)v92 = 0;
                ((void (__fastcall *)(char *))basessp::WSTGlobalLsaFunctions->GetCallInfo)(v92);
                v78 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                  goto LABEL_71;
                v79 = 29;
              }
              else
              {
                v23 = WSTProcessResponse(v101, v100, v95, v76, v89, a10, v99);
                if ( v23 >= 0 )
                {
                  v45 = a10;
                  goto LABEL_243;
                }
                v93 = 0;
                *(_OWORD *)v92 = 0;
                ((void (__fastcall *)(char *))basessp::WSTGlobalLsaFunctions->GetCallInfo)(v92);
                v78 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                  goto LABEL_71;
                v79 = 30;
              }
LABEL_223:
              WPP_SF_Dd(
                v78[2],
                v79,
                &WPP_6fa7dbc14d303f0b349d28a6dba66ee3_Traceguids,
                (unsigned int)v23,
                *(_DWORD *)v92);
              goto LABEL_71;
            }
            v23 = WSTParseMessages((unsigned __int8 *)v25->pvBuffer, cbBuffer, v76, v13, &v89);
            if ( v23 < 0 )
            {
              v93 = 0;
              *(_OWORD *)v92 = 0;
              ((void (__fastcall *)(char *))basessp::WSTGlobalLsaFunctions->GetCallInfo)(v92);
              v78 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                goto LABEL_71;
              v79 = 27;
              goto LABEL_223;
            }
          }
          else
          {
            v23 = WSTParseMessages(
                    (unsigned __int8 *)v25->pvBuffer,
                    (struct _WST_CONTEXT **)v25->cbBuffer,
                    v76,
                    v13,
                    &v89);
            if ( v23 < 0 )
            {
              v93 = 0;
              *(_OWORD *)v92 = 0;
              ((void (__fastcall *)(char *))basessp::WSTGlobalLsaFunctions->GetCallInfo)(v92);
              v78 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                goto LABEL_71;
              v79 = 28;
              goto LABEL_223;
            }
          }
          LODWORD(v41) = 0;
          goto LABEL_229;
        }
        v50 = *((_QWORD *)v89 + 3);
        if ( v50 != a2 )
        {
          if ( *((_DWORD *)v89 + 62) )
          {
            v23 = basessp::BaseSSP::WSTValidateAndReferenceCredential(v42, a2, &v94);
            if ( v23 >= 0 )
            {
              v51 = v94;
              v52 = v89;
              v91 = v94;
              v53 = *((_QWORD *)v89 + 3);
              v54 = *(_DWORD *)(v53 + 40);
              if ( *((_QWORD *)v94 + 5) == *(_QWORD *)(v53 + 40)
                && (unsigned int)WSTIsExplicitCredentials((struct _SECPKG_CREDENTIAL *)((char *)v94 + 16)) )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  WPP_SF_qDDZ(*((_QWORD *)WPP_GLOBAL_Control + 2), v55, v54, (__int64)v52 + 168);
                v56 = (struct _WST_CONTEXT *)basessp::BaseSSP::WSTAllocate(WSTGlobalBaseSSP, 0x18u);
                v13 = 0;
                v57 = v56;
                if ( !v56 )
                  goto LABEL_125;
                *((_QWORD *)v56 + 1) = v56;
                *(_QWORD *)v56 = v56;
                *((_QWORD *)v56 + 2) = _InterlockedExchange64((volatile __int64 *)v89 + 3, (__int64)v51);
                v58 = (char *)v89 + 120;
                v59 = (struct _WST_CONTEXT **)*((_QWORD *)v89 + 16);
                if ( *v59 == (struct _WST_CONTEXT *)((char *)v89 + 120) )
                {
                  *(_QWORD *)v57 = v58;
                  *((_QWORD *)v57 + 1) = v59;
                  *v59 = v57;
                  *((_QWORD *)v58 + 1) = v57;
                  v91 = 0;
                  v23 = WSTSelectAuthScheme(v89);
                  if ( v23 < 0 )
                    goto LABEL_71;
LABEL_189:
                  v41 = a3;
                  goto LABEL_134;
                }
LABEL_171:
                __fastfail(3u);
              }
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                WPP_SF_qDDZq(*((_QWORD *)WPP_GLOBAL_Control + 2), *(_DWORD *)(v53 + 44), v54, (__int64)v52 + 168, a2);
              goto LABEL_132;
            }
LABEL_145:
            v91 = v94;
            goto LABEL_71;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v13 = 0;
            WPP_SF_qdDDZq(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              0,
              *(_DWORD *)(v50 + 44),
              *(_DWORD *)(v50 + 40),
              (__int64)v89 + 168,
              a2);
            goto LABEL_134;
          }
        }
LABEL_133:
        v13 = 0;
        goto LABEL_134;
      }
      if ( !a2 )
      {
        v23 = -1073741816;
        goto LABEL_71;
      }
      if ( a1 && (!v25 || !v25->cbBuffer) )
      {
        if ( !a4 || !a4->Length )
        {
          v23 = -2146893053;
          goto LABEL_71;
        }
        v23 = basessp::BaseSSP::WSTValidateAndReferenceCredential(v26, a2, &v94);
        if ( v23 < 0 )
          goto LABEL_145;
        v62 = a4;
        v91 = v94;
        v63 = WSTLocateContextByTargetName(a4, (struct _LUID *)v94 + 5);
        v89 = v63;
        pBuffers = v63;
        if ( !v63 )
          goto LABEL_174;
        if ( *((_DWORD *)v63 + 12) == 5
          || !*((_DWORD *)v63 + 62)
          || a5 != *((_DWORD *)v63 + 54)
          || !(unsigned int)WSTIsExplicitCredentials((struct _SECPKG_CREDENTIAL *)((char *)v91 + 16)) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_qdDDZ(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              *((_DWORD *)pBuffers + 62),
              *(_DWORD *)(*((_QWORD *)pBuffers + 3) + 44LL),
              *(_DWORD *)(*((_QWORD *)pBuffers + 3) + 40LL),
              (__int64)pBuffers + 168);
          WSTDereferenceContext(v89);
          v89 = 0;
          goto LABEL_175;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_DDZ(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            *(_DWORD *)(*((_QWORD *)pBuffers + 3) + 40LL),
            (__int64)pBuffers + 168);
        if ( _InterlockedIncrement((volatile signed __int32 *)v89 + 2) > 1 )
        {
          v43 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_70;
          v44 = 19;
          goto LABEL_69;
        }
        v64 = (struct _WST_CONTEXT *)basessp::BaseSSP::WSTAllocate(WSTGlobalBaseSSP, 0x18u);
        pBuffers = 0;
        v65 = v64;
        if ( !v64 )
        {
LABEL_125:
          v23 = -1073741801;
          goto LABEL_71;
        }
        v66 = v91;
        *((_QWORD *)v64 + 1) = v64;
        *(_QWORD *)v64 = v64;
        *((_QWORD *)v64 + 2) = _InterlockedExchange64((volatile __int64 *)v89 + 3, (__int64)v66);
        v67 = (char *)v89 + 120;
        v68 = (struct _WST_CONTEXT **)*((_QWORD *)v89 + 16);
        if ( *v68 != (struct _WST_CONTEXT *)((char *)v89 + 120) )
          goto LABEL_171;
        *(_QWORD *)v65 = v67;
        *((_QWORD *)v65 + 1) = v68;
        *v68 = v65;
        *((_QWORD *)v67 + 1) = v65;
        v106 = 1;
        v91 = 0;
        v23 = WSTSelectAuthScheme(v89);
        if ( v23 < 0 )
          goto LABEL_71;
      }
      v62 = a4;
LABEL_174:
      if ( v89 )
      {
LABEL_132:
        v41 = a3;
        goto LABEL_133;
      }
LABEL_175:
      v23 = WSTAllocateContext(a1, v62, a5, &v89);
      if ( v23 < 0 )
        goto LABEL_71;
      v69 = (basessp::BaseSSP *)(unsigned int)_InterlockedIncrement((volatile signed __int32 *)v89 + 2);
      if ( (int)v69 > 1 )
      {
        v43 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_70;
        v44 = 20;
        goto LABEL_69;
      }
      v13 = 0;
      v23 = basessp::BaseSSP::WSTValidateAndReferenceCredential(v69, a2, (struct basessp::_WST_CREDENTIAL **)v89 + 3);
      if ( v23 < 0 )
        goto LABEL_71;
      v70 = WSTIsExplicitCredentials((struct _SECPKG_CREDENTIAL *)(*((_QWORD *)v89 + 3) + 16LL));
      *(_DWORD *)(v71 + 268) = v70;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_qDDZd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *(_DWORD *)(*((_QWORD *)v89 + 3) + 44LL),
          *(_DWORD *)(*((_QWORD *)v89 + 3) + 40LL),
          (__int64)v89 + 168,
          v70);
      goto LABEL_189;
    }
  }
LABEL_34:
  v23 = -1073741811;
  v31 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v32 = 12;
LABEL_26:
    WPP_SF_(v31[2], v32, &WPP_6fa7dbc14d303f0b349d28a6dba66ee3_Traceguids);
  }
LABEL_72:
  if ( v89 )
  {
    v45 = a10;
    v46 = a8;
    if ( !*((_DWORD *)v89 + 62) )
      *((_DWORD *)v89 + 12) = 7;
    goto LABEL_75;
  }
LABEL_289:
  if ( v91 )
    basessp::BaseSSP::WSTDereferenceCredential(WSTGlobalBaseSSP, v91);
  if ( v15 )
    (*(void (__fastcall **)(void *, _QWORD, struct _WST_CONTEXT *))(*((_QWORD *)WSTGlobalBaseSSP + 30) + 48LL))(
      v15,
      *((_QWORD *)WSTGlobalBaseSSP + 30),
      pBuffers);
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x18000a29c  mov     rax, rsp
0x18000a29f  mov     [rax+20h], r9
0x18000a2a3  mov     [rax+18h], r8
0x18000a2a7  mov     [rax+10h], rdx
0x18000a2ab  mov     [rax+8], ecx
0x18000a2ae  push    rbp
0x18000a2af  push    rbx
0x18000a2b0  push    rsi
0x18000a2b1  push    rdi
0x18000a2b2  push    r12
0x18000a2b4  push    r13
0x18000a2b6  push    r14
0x18000a2b8  push    r15
0x18000a2ba  lea     rbp, [rax-47h]
0x18000a2be  sub     rsp, 0C8h
0x18000a2c5  mov     rax, [rbp+3Fh+arg_58]
0x18000a2cc  xor     esi, esi
0x18000a2ce  mov     ebx, esi
0x18000a2d0  mov     [rbp+3Fh+var_A0], rsi
0x18000a2d4  mov     [rbp+3Fh+var_80], rsi
0x18000a2d8  mov     r13d, esi
0x18000a2db  mov     [rbp+3Fh+var_B0], rsi
0x18000a2df  mov     [rax], sil
0x18000a2e2  mov     dword ptr [rbp+3Fh+Size], esi
0x18000a2e5  mov     [rbp+3Fh+var_A8], rsi
0x18000a2e9  mov     [rbp+3Fh+Src], rsi
0x18000a2ed  mov     [rbp+3Fh+var_58], rbx
0x18000a2f1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NegoLateFallback@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NegoLateFallback@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback> `wil::Feature<__WilFeatureTraits_Feature_NegoLateFallback>::GetImpl(void)'::`2'::impl
0x18000a2f8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NegoLateFallback@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback>::__private_IsEnabled(void)
0x18000a2fd  mov     r14, [rbp+3Fh+arg_40]
0x18000a304  mov     edx, [r14+4]
0x18000a308  test    al, al
0x18000a30a  jz      loc_18000A4D0
0x18000a310  xor     r8d, r8d
0x18000a313  mov     [rbp+3Fh+var_60], rsi
0x18000a317  mov     r15d, esi
0x18000a31a  test    edx, edx
0x18000a31c  jz      loc_18000A500
0x18000a322  mov     r12d, 0FFFFFFFh
0x18000a328  mov     edi, esi
0x18000a32a  shl     rdi, 4
0x18000a32e  add     rdi, [r14+8]
0x18000a332  mov     eax, [rdi+4]
0x18000a335  and     eax, r12d
0x18000a338  cmp     eax, 2
0x18000a33b  jnz     short loc_18000A379
0x18000a33d  test    r15, r15
0x18000a340  jnz     loc_18000A463
0x18000a346  mov     rax, cs:?WSTGlobalLsaFunctions@basessp@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * basessp::WSTGlobalLsaFunctions
0x18000a34d  mov     rdx, rdi
0x18000a350  mov     rcx, rdi
0x18000a353  mov     rax, [rax+98h]
0x18000a35a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a35f  xor     r8d, r8d
0x18000a362  mov     ebx, eax
0x18000a364  test    eax, eax
0x18000a366  js      loc_18000A722
0x18000a36c  mov     rbx, [rbp+3Fh+var_58]
0x18000a370  mov     r15, rdi
0x18000a373  mov     [rbp+3Fh+var_60], rdi
0x18000a377  jmp     short loc_18000A3B4
0x18000a379  cmp     eax, 0Ch
0x18000a37c  jnz     short loc_18000A3B4
0x18000a37e  test    rbx, rbx
0x18000a381  jnz     loc_18000A4A3
0x18000a387  mov     rax, cs:?WSTGlobalLsaFunctions@basessp@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * basessp::WSTGlobalLsaFunctions
0x18000a38e  mov     rdx, rdi
0x18000a391  mov     rcx, rdi
0x18000a394  mov     rax, [rax+98h]
0x18000a39b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3a0  xor     r8d, r8d
0x18000a3a3  mov     ebx, eax
0x18000a3a5  test    eax, eax
0x18000a3a7  js      loc_18000A722
0x18000a3ad  mov     rbx, rdi
0x18000a3b0  mov     [rbp+3Fh+var_58], rbx
0x18000a3b4  inc     esi
0x18000a3b6  cmp     esi, [r14+4]
0x18000a3ba  jb      loc_18000A328
0x18000a3c0  xor     esi, esi
0x18000a3c2  test    r15, r15
0x18000a3c5  jz      loc_18000A500
0x18000a3cb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NegoLateFallback@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NegoLateFallback@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback> `wil::Feature<__WilFeatureTraits_Feature_NegoLateFallback>::GetImpl(void)'::`2'::impl
0x18000a3d2  mov     [rbp+3Fh+var_78], rsi
0x18000a3d6  mov     r13, rsi
0x18000a3d9  mov     [rbp+3Fh+var_48], rsi
0x18000a3dd  mov     [rbp+3Fh+var_50], rsi
0x18000a3e1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NegoLateFallback@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback>::__private_IsEnabled(void)
0x18000a3e6  test    al, al
0x18000a3e8  jz      loc_18000A5F4
0x18000a3ee  mov     r14, [rbp+3Fh+arg_30]
0x18000a3f2  test    r14, r14
0x18000a3f5  jz      loc_18000A6A6
0x18000a3fb  mov     r15d, esi
0x18000a3fe  cmp     [r14+4], esi
0x18000a402  jbe     loc_18000A6A6
0x18000a408  mov     rdi, [r14+8]
0x18000a40c  mov     esi, r15d
0x18000a40f  shl     rsi, 4
0x18000a413  add     rdi, rsi
0x18000a416  mov     eax, [rdi+4]
0x18000a419  and     eax, r12d
0x18000a41c  cmp     eax, 0Eh
0x18000a41f  jnz     loc_18000A558
0x18000a425  mov     rax, cs:?WSTGlobalLsaFunctions@basessp@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * basessp::WSTGlobalLsaFunctions
0x18000a42c  mov     rdx, rdi
0x18000a42f  mov     rcx, rdi
0x18000a432  mov     rax, [rax+98h]
0x18000a439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a43e  mov     ebx, eax
0x18000a440  test    eax, eax
0x18000a442  js      loc_18000A71E
0x18000a448  mov     rax, [r14+8]
0x18000a44c  add     rax, rsi
0x18000a44f  mov     [rbp+3Fh+var_78], rax
0x18000a453  xor     esi, esi
0x18000a455  inc     r15d
0x18000a458  cmp     r15d, [r14+4]
0x18000a45c  jb      short loc_18000A408
0x18000a45e  jmp     loc_18000A6A6
0x18000a463  mov     ebx, 0C000000Dh
0x18000a468  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a46f  lea     rdi, WPP_GLOBAL_Control
0x18000a476  cmp     rcx, rdi
0x18000a479  jz      loc_18000A722
0x18000a47f  test    byte ptr [rcx+1Ch], 1
0x18000a483  jz      loc_18000A722
0x18000a489  mov     edx, 0Ah
0x18000a48e  mov     rcx, [rcx+10h]
0x18000a492  lea     r8, WPP_6fa7dbc14d303f0b349d28a6dba66ee3_Traceguids
0x18000a499  call    WPP_SF_
0x18000a49e  jmp     loc_18000A722
0x18000a4a3  mov     ebx, 0C000000Dh
0x18000a4a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a4af  lea     rdi, WPP_GLOBAL_Control
0x18000a4b6  cmp     rcx, rdi
0x18000a4b9  jz      loc_18000A722
0x18000a4bf  test    byte ptr [rcx+1Ch], 1
0x18000a4c3  jz      loc_18000A722
0x18000a4c9  mov     edx, 0Bh
0x18000a4ce  jmp     short loc_18000A48E
0x18000a4d0  test    edx, edx
0x18000a4d2  jz      short loc_18000A500
0x18000a4d4  mov     r8, [r14+8]
0x18000a4d8  mov     ecx, esi
0x18000a4da  mov     r12d, 0FFFFFFFh
0x18000a4e0  mov     r15d, ecx
0x18000a4e3  shl     r15, 4
0x18000a4e7  add     r15, r8
0x18000a4ea  mov     [rbp+3Fh+var_60], r15
0x18000a4ee  mov     eax, [r15+4]
0x18000a4f2  and     eax, r12d
0x18000a4f5  cmp     eax, 2
0x18000a4f8  jz      short loc_18000A530
0x18000a4fa  inc     ecx
0x18000a4fc  cmp     ecx, edx
0x18000a4fe  jb      short loc_18000A4E0
0x18000a500  mov     ebx, 0C000000Dh
0x18000a505  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a50c  lea     rdi, WPP_GLOBAL_Control
0x18000a513  cmp     rcx, rdi
0x18000a516  jz      loc_18000A722
0x18000a51c  test    byte ptr [rcx+1Ch], 1
0x18000a520  jz      loc_18000A722
0x18000a526  mov     edx, 0Ch
0x18000a52b  jmp     loc_18000A48E
0x18000a530  mov     rax, cs:?WSTGlobalLsaFunctions@basessp@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * basessp::WSTGlobalLsaFunctions
0x18000a537  mov     rdx, r15
0x18000a53a  mov     rcx, r15
0x18000a53d  mov     rax, [rax+98h]
0x18000a544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a549  mov     ebx, eax
0x18000a54b  test    eax, eax
0x18000a54d  js      loc_18000A722
0x18000a553  jmp     loc_18000A3C2
0x18000a558  cmp     eax, 2
0x18000a55b  jnz     short loc_18000A58A
0x18000a55d  mov     rax, cs:?WSTGlobalLsaFunctions@basessp@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * basessp::WSTGlobalLsaFunctions
0x18000a564  mov     rdx, rdi
0x18000a567  mov     rcx, rdi
0x18000a56a  mov     rax, [rax+98h]
0x18000a571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a576  xor     esi, esi
0x18000a578  mov     ebx, eax
0x18000a57a  test    eax, eax
0x18000a57c  js      loc_18000A71E
0x18000a582  mov     r13, rdi
0x18000a585  jmp     loc_18000A455
0x18000a58a  cmp     eax, 0Bh
0x18000a58d  jnz     short loc_18000A5BD
0x18000a58f  mov     rax, cs:?WSTGlobalLsaFunctions@basessp@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * basessp::WSTGlobalLsaFunctions
0x18000a596  mov     rdx, rdi
0x18000a599  mov     rcx, rdi
0x18000a59c  mov     rax, [rax+98h]
0x18000a5a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5a8  xor     esi, esi
0x18000a5aa  mov     ebx, eax
0x18000a5ac  test    eax, eax
0x18000a5ae  js      loc_18000A71E
0x18000a5b4  mov     [rbp+3Fh+var_48], rdi
0x18000a5b8  jmp     loc_18000A455
0x18000a5bd  cmp     eax, 0Ch
0x18000a5c0  jnz     loc_18000A453
0x18000a5c6  mov     rax, cs:?WSTGlobalLsaFunctions@basessp@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * basessp::WSTGlobalLsaFunctions
0x18000a5cd  mov     rdx, rdi
0x18000a5d0  mov     rcx, rdi
0x18000a5d3  mov     rax, [rax+98h]
0x18000a5da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5df  xor     esi, esi
0x18000a5e1  mov     ebx, eax
0x18000a5e3  test    eax, eax
0x18000a5e5  js      loc_18000A71E
0x18000a5eb  mov     [rbp+3Fh+var_50], rdi
0x18000a5ef  jmp     loc_18000A455
0x18000a5f4  mov     rdi, [rbp+3Fh+arg_30]
0x18000a5f8  test    rdi, rdi
0x18000a5fb  jz      loc_18000A6A6
0x18000a601  cmp     [rdi+4], esi
0x18000a604  jbe     short loc_18000A65B
0x18000a606  mov     rdx, [rdi+8]
0x18000a60a  mov     ecx, esi
0x18000a60c  mov     esi, ecx
0x18000a60e  shl     rsi, 4
0x18000a612  lea     r8, [rsi+rdx]
0x18000a616  mov     eax, [r8+4]
0x18000a61a  and     eax, r12d
0x18000a61d  cmp     eax, 0Eh
0x18000a620  jz      short loc_18000A62B
0x18000a622  inc     ecx
0x18000a624  cmp     ecx, [rdi+4]
0x18000a627  jb      short loc_18000A60C
0x18000a629  jmp     short loc_18000A659
0x18000a62b  mov     rax, cs:?WSTGlobalLsaFunctions@basessp@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * basessp::WSTGlobalLsaFunctions
0x18000a632  mov     rdx, r8
0x18000a635  mov     rcx, r8
0x18000a638  mov     rax, [rax+98h]
0x18000a63f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a644  mov     ebx, eax
0x18000a646  test    eax, eax
0x18000a648  js      loc_18000A71E
0x18000a64e  mov     rax, [rdi+8]
0x18000a652  add     rax, rsi
0x18000a655  mov     [rbp+3Fh+var_78], rax
0x18000a659  xor     esi, esi
0x18000a65b  mov     edx, [rdi+4]
0x18000a65e  test    edx, edx
0x18000a660  jz      short loc_18000A6A6
0x18000a662  mov     r8, [rdi+8]
0x18000a666  mov     ecx, esi
0x18000a668  mov     edi, ecx
0x18000a66a  shl     rdi, 4
0x18000a66e  add     rdi, r8
0x18000a671  mov     eax, [rdi+4]
0x18000a674  and     eax, r12d
0x18000a677  cmp     eax, 2
0x18000a67a  jz      short loc_18000A684
0x18000a67c  inc     ecx
0x18000a67e  cmp     ecx, edx
0x18000a680  jb      short loc_18000A668
0x18000a682  jmp     short loc_18000A6A6
0x18000a684  mov     rax, cs:?WSTGlobalLsaFunctions@basessp@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * basessp::WSTGlobalLsaFunctions
0x18000a68b  mov     rdx, rdi
0x18000a68e  mov     rcx, rdi
0x18000a691  mov     rax, [rax+98h]
0x18000a698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a69d  mov     ebx, eax
0x18000a69f  test    eax, eax
0x18000a6a1  js      short loc_18000A71E
0x18000a6a3  mov     r13, rdi
0x18000a6a6  mov     rbx, [rbp+3Fh+arg_10]
0x18000a6aa  lea     r14, WPP_6fa7dbc14d303f0b349d28a6dba66ee3_Traceguids
0x18000a6b1  mov     r12d, [rbp+3Fh+arg_20]
0x18000a6b5  lea     rdi, WPP_GLOBAL_Control
0x18000a6bc  mov     [rbp+3Fh+arg_28], esi
0x18000a6bf  mov     [rbp+3Fh+var_B0], rbx
0x18000a6c3  test    rbx, rbx
0x18000a6c6  jz      loc_18000AB81
0x18000a6cc  mov     rcx, rbx; struct _WST_CONTEXT *
0x18000a6cf  call    ?WSTReferenceContext@@YAXPEAU_WST_CONTEXT@@@Z; WSTReferenceContext(_WST_CONTEXT *)
0x18000a6d4  mov     rax, [rbp+3Fh+var_B0]
0x18000a6d8  mov     edx, 1
0x18000a6dd  mov     ecx, edx
0x18000a6df  lock xadd [rax+8], ecx
0x18000a6e4  add     ecx, edx; this
0x18000a6e6  cmp     ecx, edx
0x18000a6e8  jle     loc_18000A934
0x18000a6ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a6f5  cmp     rcx, rdi
0x18000a6f8  jz      short loc_18000A719
0x18000a6fa  test    [rcx+1Ch], dl
0x18000a6fd  jz      short loc_18000A719
0x18000a6ff  mov     edx, 0Dh
0x18000a704  mov     r9, [rbp+3Fh+var_B0]
0x18000a708  mov     rcx, [rcx+10h]
0x18000a70c  mov     eax, [r9+8]
0x18000a710  mov     dword ptr [rsp+100h+var_E0], eax
0x18000a714  call    WPP_SF_qd
0x18000a719  mov     ebx, 80090302h
0x18000a71e  mov     r13, [rbp+3Fh+var_A8]
0x18000a722  mov     rax, [rbp+3Fh+var_B0]
  ... truncated ...
```
