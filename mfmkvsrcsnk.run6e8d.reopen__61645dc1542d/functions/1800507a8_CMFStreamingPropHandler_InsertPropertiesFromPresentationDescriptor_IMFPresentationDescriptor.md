# CMFStreamingPropHandler::InsertPropertiesFromPresentationDescriptor(IMFPresentationDescriptor *)

- ea: `0x1800507a8`
- end: `0x180050fa3`
- name: `?InsertPropertiesFromPresentationDescriptor@CMFStreamingPropHandler@@QEAAJPEAUIMFPresentationDescriptor@@@Z`
- size: `2043`
- prototype: `__int64 __fastcall(CMFStreamingPropHandler *__hidden this, struct IMFPresentationDescriptor *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000fe50`

## callees

- `0x1800023e0`
- `0x1800036b9`
- `0x1800097f0`
- `0x18004f47c`
- `0x180050454`
- `0x1800507a8`
- `0x180050fac`
- `0x1800515ec`
- `0x180071330`
- `0x180071524`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050812`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800508c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050a42`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050ab5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050b28`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050b98`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050ca0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050d8f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050e7e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050f05`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050812`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800508c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050a42`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050ab5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050b28`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050b98`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050ca0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050d8f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050e7e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050f05`

## string_xrefs

- `0x180050bf5`: `CMFStreamingPropHandler::InsertPropertiesFromPresentationDescriptor`
- `0x180050f62`: `CMFStreamingPropHandler::InsertPropertiesFromPresentationDescriptor`

## pseudocode

```c
__int64 __fastcall CMFStreamingPropHandler::InsertPropertiesFromPresentationDescriptor(
        CMFStreamingPropHandler *this,
        struct IMFPresentationDescriptor *a2)
{
  struct IMFPresentationDescriptorVtbl *lpVtbl; // rax
  __int64 v5; // rdx
  int inserted; // ebx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v12; // r8d
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  char v18; // r12
  char v19; // r15
  unsigned int i; // r14d
  struct IMFPresentationDescriptorVtbl *v21; // rax
  HRESULT (__stdcall *GetStreamDescriptorByIndex)(IMFPresentationDescriptor *, DWORD, BOOL *, IMFStreamDescriptor **); // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  int v38; // r8d
  __int64 *v39; // rcx
  CallStackTracing *v40; // rax
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  __int64 *v43; // rcx
  CallStackTracing *v44; // rax
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // r9
  __int64 *v48; // rcx
  CallStackTracing *v49; // rax
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // r9
  __int64 *v53; // rcx
  CallStackTracing *v54; // rax
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 v57; // r9
  __int64 *v58; // rcx
  CallStackTracing *v59; // rax
  __int64 v60; // rdx
  __int64 v61; // r8
  __int64 v62; // r9
  __int64 *v63; // rcx
  CallStackTracing *v64; // rax
  struct IMFStreamDescriptor *v66; // [rsp+30h] [rbp-50h] BYREF
  PROPVARIANT pvar; // [rsp+38h] [rbp-48h] BYREF
  __int64 v68; // [rsp+50h] [rbp-30h] BYREF
  unsigned int v69; // [rsp+58h] [rbp-28h] BYREF
  int v70; // [rsp+5Ch] [rbp-24h] BYREF
  __int128 Buf1; // [rsp+60h] [rbp-20h] BYREF

  lpVtbl = a2->lpVtbl;
  v69 = 0;
  memset(&pvar, 0, sizeof(pvar));
  inserted = ((__int64 (__fastcall *)(struct IMFPresentationDescriptor *, unsigned int *))lpVtbl->GetStreamDescriptorCount)(
               a2,
               &v69);
  if ( inserted < 0 )
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5, v7, v8);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != inserted )
      {
        v12 = 97;
LABEL_114:
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFStreamingPropHandler::InsertPropertiesFromPresentationDescriptor",
          v12,
          inserted);
        goto LABEL_115;
      }
    }
    goto LABEL_115;
  }
  if ( ((int (__fastcall *)(struct IMFPresentationDescriptor *, const IID *, ULONG *))a2->lpVtbl->GetUINT64)(
         a2,
         &MF_PD_DURATION,
         &pvar.decVal.Lo32) < 0 )
  {
LABEL_21:
    v18 = 0;
    v19 = 0;
    for ( i = 0; i < v69; ++i )
    {
      v21 = a2->lpVtbl;
      v66 = 0;
      v68 = 0;
      v70 = 0;
      GetStreamDescriptorByIndex = v21->GetStreamDescriptorByIndex;
      Buf1 = 0;
      inserted = ((__int64 (__fastcall *)(struct IMFPresentationDescriptor *, _QWORD, int *, struct IMFStreamDescriptor **))GetStreamDescriptorByIndex)(
                   a2,
                   i,
                   &v70,
                   &v66);
      if ( inserted < 0 )
      {
        v43 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24, v25);
          CallStackTracing::s_wpInstance = v44;
          if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
          {
            v43 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v43 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( !*((_BYTE *)v43 + 8) )
          goto LABEL_65;
        v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
        if ( *((_DWORD *)v37 + 499) == inserted )
          goto LABEL_65;
        v38 = 118;
LABEL_64:
        CallStackContext::TraceFailure(
          v37,
          "CMFStreamingPropHandler::InsertPropertiesFromPresentationDescriptor",
          v38,
          inserted);
        goto LABEL_65;
      }
      inserted = CMFStreamingPropHandler::InsertPropertiesFromStreamDescriptor(this, v66);
      if ( inserted < 0 )
      {
        v41 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26, v27, v28);
          CallStackTracing::s_wpInstance = v42;
          if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
          {
            v41 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v41 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( !*((_BYTE *)v41 + 8) )
          goto LABEL_65;
        v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
        if ( *((_DWORD *)v37 + 499) == inserted )
          goto LABEL_65;
        v38 = 119;
        goto LABEL_64;
      }
      inserted = ((__int64 (__fastcall *)(struct IMFStreamDescriptor *, __int64 *))v66->lpVtbl->GetMediaTypeHandler)(
                   v66,
                   &v68);
      if ( inserted < 0 )
      {
        v39 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30, v31);
          CallStackTracing::s_wpInstance = v40;
          if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
          {
            v39 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v39 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( !*((_BYTE *)v39 + 8) )
          goto LABEL_65;
        v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
        if ( *((_DWORD *)v37 + 499) == inserted )
          goto LABEL_65;
        v38 = 120;
        goto LABEL_64;
      }
      inserted = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v68 + 64LL))(v68, &Buf1);
      if ( inserted < 0 )
      {
        v35 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v33, v34);
          CallStackTracing::s_wpInstance = v36;
          if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
          {
            v35 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v35 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v35 + 8) )
        {
          v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
          if ( *((_DWORD *)v37 + 499) != inserted )
          {
            v38 = 121;
            goto LABEL_64;
          }
        }
LABEL_65:
        ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v68);
        ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v66);
        goto LABEL_115;
      }
      if ( !memcmp_0(&Buf1, &MFMediaType_Video, 0x10u) )
      {
        v18 = 1;
      }
      else if ( !memcmp_0(&Buf1, &MFMediaType_Audio, 0x10u) )
      {
        v19 = 1;
      }
      ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v68);
      ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v66);
    }
    if ( !v19
      || (*(int (__fastcall **)(_QWORD, const PROPERTYKEY *, PROPVARIANT *))(**((_QWORD **)this + 3) + 40LL))(
           *((_QWORD *)this + 3),
           &PKEY_Audio_EncodingBitrate,
           &pvar) >= 0
      && pvar.vt
      || ((int (__fastcall *)(struct IMFPresentationDescriptor *, const IID *, ULONG *))a2->lpVtbl->GetUINT32)(
           a2,
           &MF_PD_AUDIO_ENCODING_BITRATE,
           &pvar.decVal.Lo32) < 0
      || (pvar.vt = 19,
          inserted = CMFStreamingPropHandler::InsertProperty(this, &PKEY_Audio_EncodingBitrate, &pvar),
          inserted >= 0) )
    {
      CMFPropVariant::Clear(&pvar);
      if ( !v18
        || (*(int (__fastcall **)(_QWORD, const PROPERTYKEY *, PROPVARIANT *))(**((_QWORD **)this + 3) + 40LL))(
             *((_QWORD *)this + 3),
             &PKEY_Video_EncodingBitrate,
             &pvar) >= 0
        && pvar.vt
        || ((int (__fastcall *)(struct IMFPresentationDescriptor *, const IID *, ULONG *))a2->lpVtbl->GetUINT32)(
             a2,
             &MF_PD_VIDEO_ENCODING_BITRATE,
             &pvar.decVal.Lo32) < 0
        || (pvar.vt = 19,
            inserted = CMFStreamingPropHandler::InsertProperty(this, &PKEY_Video_EncodingBitrate, &pvar),
            inserted >= 0) )
      {
        CMFPropVariant::Clear(&pvar);
        if ( !v19
          || (*(int (__fastcall **)(_QWORD, const PROPERTYKEY *, PROPVARIANT *))(**((_QWORD **)this + 3) + 40LL))(
               *((_QWORD *)this + 3),
               &PKEY_Audio_IsVariableBitRate,
               &pvar) >= 0
          && pvar.vt
          || ((int (__fastcall *)(struct IMFPresentationDescriptor *, const IID *, ULONG *))a2->lpVtbl->GetUINT32)(
               a2,
               &MF_PD_AUDIO_ISVARIABLEBITRATE,
               &pvar.decVal.Lo32) < 0
          || (pvar.vt = 19,
              inserted = CMFStreamingPropHandler::InsertProperty(this, &PKEY_Audio_IsVariableBitRate, &pvar),
              inserted >= 0) )
        {
          CMFPropVariant::Clear(&pvar);
          inserted = CMFStreamingPropHandler::CheckForTotalBitrateProperty(this);
          if ( inserted < 0 )
          {
            v63 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v60, v61, v62);
              CallStackTracing::s_wpInstance = v64;
              if ( v64
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
              {
                v63 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v63 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
              }
            }
            if ( *((_BYTE *)v63 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v63);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != inserted )
              {
                v12 = 178;
                goto LABEL_114;
              }
            }
          }
        }
        else
        {
          v58 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v55, v56, v57);
            CallStackTracing::s_wpInstance = v59;
            if ( v59 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v59 + 8LL))(v59, 2032) )
            {
              v58 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v58 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v58 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v58);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != inserted )
            {
              v12 = 168;
              goto LABEL_114;
            }
          }
        }
      }
      else
      {
        v53 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v50, v51, v52);
          CallStackTracing::s_wpInstance = v54;
          if ( v54 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
          {
            v53 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v53 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v53 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v53);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != inserted )
          {
            v12 = 155;
            goto LABEL_114;
          }
        }
      }
    }
    else
    {
      v48 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45, v46, v47);
        CallStackTracing::s_wpInstance = v49;
        if ( v49 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
        {
          v48 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v48 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v48 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v48);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != inserted )
        {
          v12 = 142;
          goto LABEL_114;
        }
      }
    }
    goto LABEL_115;
  }
  pvar.vt = 21;
  inserted = CMFStreamingPropHandler::InsertProperty(this, &PKEY_Media_Duration, &pvar);
  if ( inserted >= 0 )
  {
    CMFPropVariant::Clear(&pvar);
    goto LABEL_21;
  }
  v16 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14, v15);
    CallStackTracing::s_wpInstance = v17;
    if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
    {
      v16 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v16 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
    }
  }
  if ( *((_BYTE *)v16 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
    if ( *((_DWORD *)ThreadRelativeContext + 499) != inserted )
    {
      v12 = 106;
      goto LABEL_114;
    }
  }
LABEL_115:
  CMFPropVariant::Clear(&pvar);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1800507a8  mov     [rsp-38h+arg_10], rbx
0x1800507ad  push    rbp
0x1800507ae  push    rsi
0x1800507af  push    rdi
0x1800507b0  push    r12
0x1800507b2  push    r13
0x1800507b4  push    r14
0x1800507b6  push    r15
0x1800507b8  mov     rbp, rsp
0x1800507bb  sub     rsp, 80h
0x1800507c2  mov     rax, cs:__security_cookie
0x1800507c9  xor     rax, rsp
0x1800507cc  mov     [rbp+var_10], rax
0x1800507d0  xor     eax, eax
0x1800507d2  mov     rsi, rdx
0x1800507d5  mov     qword ptr [rbp+pvar+10h], rax
0x1800507d9  mov     rdi, rcx
0x1800507dc  mov     rax, [rdx]
0x1800507df  xorps   xmm0, xmm0
0x1800507e2  xor     r13d, r13d
0x1800507e5  lea     rdx, [rbp+var_28]
0x1800507e9  mov     rcx, rsi
0x1800507ec  mov     [rbp+var_28], r13d
0x1800507f0  movups  xmmword ptr [rbp+pvar], xmm0
0x1800507f4  mov     rax, [rax+108h]
0x1800507fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050800  mov     ebx, eax
0x180050802  test    eax, eax
0x180050804  jns     short loc_180050879
0x180050806  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005080d  test    rcx, rcx
0x180050810  jnz     short loc_180050853
0x180050812  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180050818  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005081f  mov     rcx, rax
0x180050822  test    rax, rax
0x180050825  jz      short loc_180050845
0x180050827  mov     rax, [rax]
0x18005082a  mov     edx, 7F0h
0x18005082f  mov     rax, [rax+8]
0x180050833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050838  test    eax, eax
0x18005083a  jz      short loc_180050845
0x18005083c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050843  jmp     short loc_180050853
0x180050845  lea     rcx, qword_1800D6F70; this
0x18005084c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180050853  cmp     [rcx+8], r13b
0x180050857  jz      loc_180050F71
0x18005085d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180050862  cmp     [rax+7CCh], ebx
0x180050868  jz      loc_180050F71
0x18005086e  mov     r8d, 61h ; 'a'
0x180050874  jmp     loc_180050F5F
0x180050879  mov     rax, [rsi]
0x18005087c  lea     r8, [rbp+pvar+8]
0x180050880  lea     rdx, MF_PD_DURATION
0x180050887  mov     rcx, rsi
0x18005088a  mov     rax, [rax+40h]
0x18005088e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050893  test    eax, eax
0x180050895  js      loc_180050939
0x18005089b  mov     eax, 15h
0x1800508a0  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x1800508a4  lea     rdx, PKEY_Media_Duration; struct _tagpropertykey *
0x1800508ab  mov     word ptr [rbp+pvar], ax
0x1800508af  mov     rcx, rdi; this
0x1800508b2  call    ?InsertProperty@CMFStreamingPropHandler@@QEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@@Z; CMFStreamingPropHandler::InsertProperty(_tagpropertykey const &,tagPROPVARIANT const &)
0x1800508b7  mov     ebx, eax
0x1800508b9  test    eax, eax
0x1800508bb  jns     short loc_180050930
0x1800508bd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800508c4  test    rcx, rcx
0x1800508c7  jnz     short loc_18005090A
0x1800508c9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800508cf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800508d6  mov     rcx, rax
0x1800508d9  test    rax, rax
0x1800508dc  jz      short loc_1800508FC
0x1800508de  mov     rax, [rax]
0x1800508e1  mov     edx, 7F0h
0x1800508e6  mov     rax, [rax+8]
0x1800508ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800508ef  test    eax, eax
0x1800508f1  jz      short loc_1800508FC
0x1800508f3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800508fa  jmp     short loc_18005090A
0x1800508fc  lea     rcx, qword_1800D6F70; this
0x180050903  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005090a  cmp     [rcx+8], r13b
0x18005090e  jz      loc_180050F71
0x180050914  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180050919  cmp     [rax+7CCh], ebx
0x18005091f  jz      loc_180050F71
0x180050925  mov     r8d, 6Ah ; 'j'
0x18005092b  jmp     loc_180050F5F
0x180050930  lea     rcx, [rbp+pvar]; pvar
0x180050934  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180050939  mov     r12b, r13b
0x18005093c  mov     r15b, r13b
0x18005093f  mov     r14d, r13d
0x180050942  cmp     r14d, [rbp+var_28]
0x180050946  jnb     loc_180050C1B
0x18005094c  mov     rax, [rsi]
0x18005094f  lea     r9, [rbp+var_50]
0x180050953  xorps   xmm0, xmm0
0x180050956  mov     [rbp+var_50], r13
0x18005095a  lea     r8, [rbp+var_24]
0x18005095e  mov     [rbp+var_30], r13
0x180050962  mov     edx, r14d
0x180050965  mov     [rbp+var_24], r13d
0x180050969  mov     rax, [rax+110h]
0x180050970  mov     rcx, rsi
0x180050973  movups  [rbp+Buf1], xmm0
0x180050977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005097c  mov     ebx, eax
0x18005097e  test    eax, eax
0x180050980  js      loc_180050B8C
0x180050986  mov     rdx, [rbp+var_50]; struct IMFStreamDescriptor *
0x18005098a  mov     rcx, rdi; this
0x18005098d  call    ?InsertPropertiesFromStreamDescriptor@CMFStreamingPropHandler@@AEAAJPEAUIMFStreamDescriptor@@@Z; CMFStreamingPropHandler::InsertPropertiesFromStreamDescriptor(IMFStreamDescriptor *)
0x180050992  mov     ebx, eax
0x180050994  test    eax, eax
0x180050996  js      loc_180050B1C
0x18005099c  mov     rcx, [rbp+var_50]
0x1800509a0  lea     rdx, [rbp+var_30]
0x1800509a4  mov     rax, [rcx]
0x1800509a7  mov     rax, [rax+110h]
0x1800509ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800509b3  mov     ebx, eax
0x1800509b5  test    eax, eax
0x1800509b7  js      loc_180050AA9
0x1800509bd  mov     rcx, [rbp+var_30]
0x1800509c1  lea     rdx, [rbp+Buf1]
0x1800509c5  mov     rax, [rcx]
0x1800509c8  mov     rax, [rax+40h]
0x1800509cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800509d1  mov     ebx, eax
0x1800509d3  test    eax, eax
0x1800509d5  js      short loc_180050A36
0x1800509d7  mov     r8d, 10h; Size
0x1800509dd  lea     rdx, MFMediaType_Video; Buf2
0x1800509e4  lea     rcx, [rbp+Buf1]; Buf1
0x1800509e8  call    memcmp_0
0x1800509ed  test    eax, eax
0x1800509ef  jnz     short loc_1800509F7
0x1800509f1  lea     r12d, [rax+1]
0x1800509f5  jmp     short loc_180050A1C
0x1800509f7  mov     r8d, 10h; Size
0x1800509fd  lea     rdx, MFMediaType_Audio; Buf2
0x180050a04  lea     rcx, [rbp+Buf1]; Buf1
0x180050a08  call    memcmp_0
0x180050a0d  test    eax, eax
0x180050a0f  movzx   r15d, r15b
0x180050a13  mov     eax, 1
0x180050a18  cmovz   r15d, eax
0x180050a1c  lea     rcx, [rbp+var_30]
0x180050a20  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x180050a25  lea     rcx, [rbp+var_50]
0x180050a29  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x180050a2e  inc     r14d
0x180050a31  jmp     loc_180050942
0x180050a36  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050a3d  test    rcx, rcx
0x180050a40  jnz     short loc_180050A83
0x180050a42  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180050a48  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180050a4f  mov     rcx, rax
0x180050a52  test    rax, rax
0x180050a55  jz      short loc_180050A75
0x180050a57  mov     rax, [rax]
0x180050a5a  mov     edx, 7F0h
0x180050a5f  mov     rax, [rax+8]
0x180050a63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a68  test    eax, eax
0x180050a6a  jz      short loc_180050A75
0x180050a6c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050a73  jmp     short loc_180050A83
0x180050a75  lea     rcx, qword_1800D6F70; this
0x180050a7c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180050a83  cmp     [rcx+8], r13b
0x180050a87  jz      loc_180050C04
0x180050a8d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180050a92  cmp     [rax+7CCh], ebx
0x180050a98  jz      loc_180050C04
0x180050a9e  mov     r8d, 79h ; 'y'
0x180050aa4  jmp     loc_180050BF2
0x180050aa9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050ab0  test    rcx, rcx
0x180050ab3  jnz     short loc_180050AF6
0x180050ab5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180050abb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180050ac2  mov     rcx, rax
0x180050ac5  test    rax, rax
0x180050ac8  jz      short loc_180050AE8
0x180050aca  mov     rax, [rax]
0x180050acd  mov     edx, 7F0h
0x180050ad2  mov     rax, [rax+8]
0x180050ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050adb  test    eax, eax
0x180050add  jz      short loc_180050AE8
0x180050adf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050ae6  jmp     short loc_180050AF6
0x180050ae8  lea     rcx, qword_1800D6F70; this
0x180050aef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180050af6  cmp     [rcx+8], r13b
0x180050afa  jz      loc_180050C04
0x180050b00  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180050b05  cmp     [rax+7CCh], ebx
0x180050b0b  jz      loc_180050C04
0x180050b11  mov     r8d, 78h ; 'x'
0x180050b17  jmp     loc_180050BF2
0x180050b1c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050b23  test    rcx, rcx
0x180050b26  jnz     short loc_180050B69
0x180050b28  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180050b2e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180050b35  mov     rcx, rax
0x180050b38  test    rax, rax
0x180050b3b  jz      short loc_180050B5B
0x180050b3d  mov     rax, [rax]
0x180050b40  mov     edx, 7F0h
0x180050b45  mov     rax, [rax+8]
0x180050b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b4e  test    eax, eax
0x180050b50  jz      short loc_180050B5B
0x180050b52  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050b59  jmp     short loc_180050B69
0x180050b5b  lea     rcx, qword_1800D6F70; this
0x180050b62  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180050b69  cmp     [rcx+8], r13b
0x180050b6d  jz      loc_180050C04
0x180050b73  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180050b78  cmp     [rax+7CCh], ebx
0x180050b7e  jz      loc_180050C04
0x180050b84  mov     r8d, 77h ; 'w'
0x180050b8a  jmp     short loc_180050BF2
0x180050b8c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050b93  test    rcx, rcx
0x180050b96  jnz     short loc_180050BD9
0x180050b98  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180050b9e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180050ba5  mov     rcx, rax
0x180050ba8  test    rax, rax
0x180050bab  jz      short loc_180050BCB
0x180050bad  mov     rax, [rax]
0x180050bb0  mov     edx, 7F0h
0x180050bb5  mov     rax, [rax+8]
0x180050bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050bbe  test    eax, eax
0x180050bc0  jz      short loc_180050BCB
0x180050bc2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050bc9  jmp     short loc_180050BD9
0x180050bcb  lea     rcx, qword_1800D6F70; this
0x180050bd2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180050bd9  cmp     [rcx+8], r13b
0x180050bdd  jz      short loc_180050C04
0x180050bdf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180050be4  cmp     [rax+7CCh], ebx
0x180050bea  jz      short loc_180050C04
0x180050bec  mov     r8d, 76h ; 'v'; int
0x180050bf2  mov     r9d, ebx; int
0x180050bf5  lea     rdx, aCmfstreamingpr_0; "CMFStreamingPropHandler::InsertProperti"...
0x180050bfc  mov     rcx, rax; this
0x180050bff  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180050c04  lea     rcx, [rbp+var_30]
0x180050c08  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x180050c0d  lea     rcx, [rbp+var_50]
0x180050c11  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x180050c16  jmp     loc_180050F71
0x180050c1b  mov     r14d, 13h
0x180050c21  test    r15b, r15b
0x180050c24  jz      loc_180050D07
0x180050c2a  mov     rcx, [rdi+18h]
0x180050c2e  lea     r8, [rbp+pvar]
0x180050c32  lea     rdx, PKEY_Audio_EncodingBitrate
0x180050c39  mov     rax, [rcx]
0x180050c3c  mov     rax, [rax+28h]
0x180050c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c45  test    eax, eax
0x180050c47  js      short loc_180050C54
0x180050c49  cmp     word ptr [rbp+pvar], r13w
0x180050c4e  jnz     loc_180050D07
0x180050c54  mov     rax, [rsi]
0x180050c57  lea     r8, [rbp+pvar+8]
0x180050c5b  lea     rdx, MF_PD_AUDIO_ENCODING_BITRATE
0x180050c62  mov     rcx, rsi
0x180050c65  mov     rax, [rax+38h]
0x180050c69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c6e  test    eax, eax
0x180050c70  js      loc_180050D07
0x180050c76  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x180050c7a  mov     word ptr [rbp+pvar], r14w
0x180050c7f  lea     rdx, PKEY_Audio_EncodingBitrate; struct _tagpropertykey *
0x180050c86  mov     rcx, rdi; this
0x180050c89  call    ?InsertProperty@CMFStreamingPropHandler@@QEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@@Z; CMFStreamingPropHandler::InsertProperty(_tagpropertykey const &,tagPROPVARIANT const &)
0x180050c8e  mov     ebx, eax
0x180050c90  test    eax, eax
0x180050c92  jns     short loc_180050D07
0x180050c94  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
