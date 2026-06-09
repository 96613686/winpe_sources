# CMFStreamingPropHandler::InsertPropertiesFromPresentationDescriptor(IMFPresentationDescriptor *)

- ea: `0x180052a48`
- end: `0x180053283`
- name: `?InsertPropertiesFromPresentationDescriptor@CMFStreamingPropHandler@@QEAAJPEAUIMFPresentationDescriptor@@@Z`
- size: `2107`
- prototype: `__int64 __fastcall(CMFStreamingPropHandler *__hidden this, struct IMFPresentationDescriptor *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010540`

## callees

- `0x180002400`
- `0x1800036f9`
- `0x180009b04`
- `0x1800516a4`
- `0x1800526dc`
- `0x180052a48`
- `0x18005328c`
- `0x180053900`
- `0x1800744d8`
- `0x1800746f8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052ab2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052b6f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052cee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052d67`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052de0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052e56`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052f64`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053059`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005314e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800531de`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052ab2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052b6f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052cee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052d67`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052de0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052e56`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052f64`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053059`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005314e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800531de`

## string_xrefs

- `0x180052eb9`: `CMFStreamingPropHandler::InsertPropertiesFromPresentationDescriptor`
- `0x180053241`: `CMFStreamingPropHandler::InsertPropertiesFromPresentationDescriptor`

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
        v9 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v43 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v41 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v39 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v35 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                v63 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
              v58 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v53 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v48 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
      v16 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x180052a48  mov     [rsp-38h+arg_10], rbx
0x180052a4d  push    rbp
0x180052a4e  push    rsi
0x180052a4f  push    rdi
0x180052a50  push    r12
0x180052a52  push    r13
0x180052a54  push    r14
0x180052a56  push    r15
0x180052a58  mov     rbp, rsp
0x180052a5b  sub     rsp, 80h
0x180052a62  mov     rax, cs:__security_cookie
0x180052a69  xor     rax, rsp
0x180052a6c  mov     [rbp+var_10], rax
0x180052a70  xor     eax, eax
0x180052a72  mov     rsi, rdx
0x180052a75  mov     qword ptr [rbp+pvar+10h], rax
0x180052a79  mov     rdi, rcx
0x180052a7c  mov     rax, [rdx]
0x180052a7f  xorps   xmm0, xmm0
0x180052a82  xor     r13d, r13d
0x180052a85  lea     rdx, [rbp+var_28]
0x180052a89  mov     rcx, rsi
0x180052a8c  mov     [rbp+var_28], r13d
0x180052a90  movups  xmmword ptr [rbp+pvar], xmm0
0x180052a94  mov     rax, [rax+108h]
0x180052a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052aa0  mov     ebx, eax
0x180052aa2  test    eax, eax
0x180052aa4  jns     short loc_180052B1F
0x180052aa6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052aad  test    rcx, rcx
0x180052ab0  jnz     short loc_180052AF9
0x180052ab2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180052ab9  nop     dword ptr [rax+rax+00h]
0x180052abe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180052ac5  mov     rcx, rax
0x180052ac8  test    rax, rax
0x180052acb  jz      short loc_180052AEB
0x180052acd  mov     rax, [rax]
0x180052ad0  mov     edx, 7F0h
0x180052ad5  mov     rax, [rax+8]
0x180052ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052ade  test    eax, eax
0x180052ae0  jz      short loc_180052AEB
0x180052ae2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052ae9  jmp     short loc_180052AF9
0x180052aeb  lea     rcx, qword_1800DBF70; this
0x180052af2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180052af9  cmp     [rcx+8], r13b
0x180052afd  jz      loc_180053250
0x180052b03  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180052b08  cmp     [rax+7CCh], ebx
0x180052b0e  jz      loc_180053250
0x180052b14  mov     r8d, 61h ; 'a'
0x180052b1a  jmp     loc_18005323E
0x180052b1f  mov     rax, [rsi]
0x180052b22  lea     r8, [rbp+pvar+8]
0x180052b26  lea     rdx, MF_PD_DURATION
0x180052b2d  mov     rcx, rsi
0x180052b30  mov     rax, [rax+40h]
0x180052b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052b39  test    eax, eax
0x180052b3b  js      loc_180052BE5
0x180052b41  mov     eax, 15h
0x180052b46  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x180052b4a  lea     rdx, PKEY_Media_Duration; struct _tagpropertykey *
0x180052b51  mov     word ptr [rbp+pvar], ax
0x180052b55  mov     rcx, rdi; this
0x180052b58  call    ?InsertProperty@CMFStreamingPropHandler@@QEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@@Z; CMFStreamingPropHandler::InsertProperty(_tagpropertykey const &,tagPROPVARIANT const &)
0x180052b5d  mov     ebx, eax
0x180052b5f  test    eax, eax
0x180052b61  jns     short loc_180052BDC
0x180052b63  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052b6a  test    rcx, rcx
0x180052b6d  jnz     short loc_180052BB6
0x180052b6f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180052b76  nop     dword ptr [rax+rax+00h]
0x180052b7b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180052b82  mov     rcx, rax
0x180052b85  test    rax, rax
0x180052b88  jz      short loc_180052BA8
0x180052b8a  mov     rax, [rax]
0x180052b8d  mov     edx, 7F0h
0x180052b92  mov     rax, [rax+8]
0x180052b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052b9b  test    eax, eax
0x180052b9d  jz      short loc_180052BA8
0x180052b9f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052ba6  jmp     short loc_180052BB6
0x180052ba8  lea     rcx, qword_1800DBF70; this
0x180052baf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180052bb6  cmp     [rcx+8], r13b
0x180052bba  jz      loc_180053250
0x180052bc0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180052bc5  cmp     [rax+7CCh], ebx
0x180052bcb  jz      loc_180053250
0x180052bd1  mov     r8d, 6Ah ; 'j'
0x180052bd7  jmp     loc_18005323E
0x180052bdc  lea     rcx, [rbp+pvar]; pvar
0x180052be0  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180052be5  mov     r12b, r13b
0x180052be8  mov     r15b, r13b
0x180052beb  mov     r14d, r13d
0x180052bee  cmp     r14d, [rbp+var_28]
0x180052bf2  jnb     loc_180052EDF
0x180052bf8  mov     rax, [rsi]
0x180052bfb  lea     r9, [rbp+var_50]
0x180052bff  xorps   xmm0, xmm0
0x180052c02  mov     [rbp+var_50], r13
0x180052c06  lea     r8, [rbp+var_24]
0x180052c0a  mov     [rbp+var_30], r13
0x180052c0e  mov     edx, r14d
0x180052c11  mov     [rbp+var_24], r13d
0x180052c15  mov     rax, [rax+110h]
0x180052c1c  mov     rcx, rsi
0x180052c1f  movups  [rbp+Buf1], xmm0
0x180052c23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052c28  mov     ebx, eax
0x180052c2a  test    eax, eax
0x180052c2c  js      loc_180052E4A
0x180052c32  mov     rdx, [rbp+var_50]; struct IMFStreamDescriptor *
0x180052c36  mov     rcx, rdi; this
0x180052c39  call    ?InsertPropertiesFromStreamDescriptor@CMFStreamingPropHandler@@AEAAJPEAUIMFStreamDescriptor@@@Z; CMFStreamingPropHandler::InsertPropertiesFromStreamDescriptor(IMFStreamDescriptor *)
0x180052c3e  mov     ebx, eax
0x180052c40  test    eax, eax
0x180052c42  js      loc_180052DD4
0x180052c48  mov     rcx, [rbp+var_50]
0x180052c4c  lea     rdx, [rbp+var_30]
0x180052c50  mov     rax, [rcx]
0x180052c53  mov     rax, [rax+110h]
0x180052c5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052c5f  mov     ebx, eax
0x180052c61  test    eax, eax
0x180052c63  js      loc_180052D5B
0x180052c69  mov     rcx, [rbp+var_30]
0x180052c6d  lea     rdx, [rbp+Buf1]
0x180052c71  mov     rax, [rcx]
0x180052c74  mov     rax, [rax+40h]
0x180052c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052c7d  mov     ebx, eax
0x180052c7f  test    eax, eax
0x180052c81  js      short loc_180052CE2
0x180052c83  mov     r8d, 10h; Size
0x180052c89  lea     rdx, MFMediaType_Video; Buf2
0x180052c90  lea     rcx, [rbp+Buf1]; Buf1
0x180052c94  call    memcmp_0
0x180052c99  test    eax, eax
0x180052c9b  jnz     short loc_180052CA3
0x180052c9d  lea     r12d, [rax+1]
0x180052ca1  jmp     short loc_180052CC8
0x180052ca3  mov     r8d, 10h; Size
0x180052ca9  lea     rdx, MFMediaType_Audio; Buf2
0x180052cb0  lea     rcx, [rbp+Buf1]; Buf1
0x180052cb4  call    memcmp_0
0x180052cb9  test    eax, eax
0x180052cbb  movzx   r15d, r15b
0x180052cbf  mov     eax, 1
0x180052cc4  cmovz   r15d, eax
0x180052cc8  lea     rcx, [rbp+var_30]
0x180052ccc  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x180052cd1  lea     rcx, [rbp+var_50]
0x180052cd5  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x180052cda  inc     r14d
0x180052cdd  jmp     loc_180052BEE
0x180052ce2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052ce9  test    rcx, rcx
0x180052cec  jnz     short loc_180052D35
0x180052cee  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180052cf5  nop     dword ptr [rax+rax+00h]
0x180052cfa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180052d01  mov     rcx, rax
0x180052d04  test    rax, rax
0x180052d07  jz      short loc_180052D27
0x180052d09  mov     rax, [rax]
0x180052d0c  mov     edx, 7F0h
0x180052d11  mov     rax, [rax+8]
0x180052d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052d1a  test    eax, eax
0x180052d1c  jz      short loc_180052D27
0x180052d1e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052d25  jmp     short loc_180052D35
0x180052d27  lea     rcx, qword_1800DBF70; this
0x180052d2e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180052d35  cmp     [rcx+8], r13b
0x180052d39  jz      loc_180052EC8
0x180052d3f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180052d44  cmp     [rax+7CCh], ebx
0x180052d4a  jz      loc_180052EC8
0x180052d50  mov     r8d, 79h ; 'y'
0x180052d56  jmp     loc_180052EB6
0x180052d5b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052d62  test    rcx, rcx
0x180052d65  jnz     short loc_180052DAE
0x180052d67  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180052d6e  nop     dword ptr [rax+rax+00h]
0x180052d73  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180052d7a  mov     rcx, rax
0x180052d7d  test    rax, rax
0x180052d80  jz      short loc_180052DA0
0x180052d82  mov     rax, [rax]
0x180052d85  mov     edx, 7F0h
0x180052d8a  mov     rax, [rax+8]
0x180052d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052d93  test    eax, eax
0x180052d95  jz      short loc_180052DA0
0x180052d97  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052d9e  jmp     short loc_180052DAE
0x180052da0  lea     rcx, qword_1800DBF70; this
0x180052da7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180052dae  cmp     [rcx+8], r13b
0x180052db2  jz      loc_180052EC8
0x180052db8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180052dbd  cmp     [rax+7CCh], ebx
0x180052dc3  jz      loc_180052EC8
0x180052dc9  mov     r8d, 78h ; 'x'
0x180052dcf  jmp     loc_180052EB6
0x180052dd4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052ddb  test    rcx, rcx
0x180052dde  jnz     short loc_180052E27
0x180052de0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180052de7  nop     dword ptr [rax+rax+00h]
0x180052dec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180052df3  mov     rcx, rax
0x180052df6  test    rax, rax
0x180052df9  jz      short loc_180052E19
0x180052dfb  mov     rax, [rax]
0x180052dfe  mov     edx, 7F0h
0x180052e03  mov     rax, [rax+8]
0x180052e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e0c  test    eax, eax
0x180052e0e  jz      short loc_180052E19
0x180052e10  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052e17  jmp     short loc_180052E27
0x180052e19  lea     rcx, qword_1800DBF70; this
0x180052e20  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180052e27  cmp     [rcx+8], r13b
0x180052e2b  jz      loc_180052EC8
0x180052e31  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180052e36  cmp     [rax+7CCh], ebx
0x180052e3c  jz      loc_180052EC8
0x180052e42  mov     r8d, 77h ; 'w'
0x180052e48  jmp     short loc_180052EB6
0x180052e4a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052e51  test    rcx, rcx
0x180052e54  jnz     short loc_180052E9D
0x180052e56  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180052e5d  nop     dword ptr [rax+rax+00h]
0x180052e62  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180052e69  mov     rcx, rax
0x180052e6c  test    rax, rax
0x180052e6f  jz      short loc_180052E8F
0x180052e71  mov     rax, [rax]
0x180052e74  mov     edx, 7F0h
0x180052e79  mov     rax, [rax+8]
0x180052e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e82  test    eax, eax
0x180052e84  jz      short loc_180052E8F
0x180052e86  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052e8d  jmp     short loc_180052E9D
0x180052e8f  lea     rcx, qword_1800DBF70; this
0x180052e96  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180052e9d  cmp     [rcx+8], r13b
0x180052ea1  jz      short loc_180052EC8
0x180052ea3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180052ea8  cmp     [rax+7CCh], ebx
0x180052eae  jz      short loc_180052EC8
0x180052eb0  mov     r8d, 76h ; 'v'; int
0x180052eb6  mov     r9d, ebx; int
0x180052eb9  lea     rdx, aCmfstreamingpr_0; "CMFStreamingPropHandler::InsertProperti"...
0x180052ec0  mov     rcx, rax; this
0x180052ec3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180052ec8  lea     rcx, [rbp+var_30]
0x180052ecc  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x180052ed1  lea     rcx, [rbp+var_50]
0x180052ed5  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x180052eda  jmp     loc_180053250
0x180052edf  mov     r14d, 13h
0x180052ee5  test    r15b, r15b
0x180052ee8  jz      loc_180052FD1
0x180052eee  mov     rcx, [rdi+18h]
0x180052ef2  lea     r8, [rbp+pvar]
0x180052ef6  lea     rdx, PKEY_Audio_EncodingBitrate
0x180052efd  mov     rax, [rcx]
0x180052f00  mov     rax, [rax+28h]
0x180052f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f09  test    eax, eax
0x180052f0b  js      short loc_180052F18
0x180052f0d  cmp     word ptr [rbp+pvar], r13w
0x180052f12  jnz     loc_180052FD1
0x180052f18  mov     rax, [rsi]
0x180052f1b  lea     r8, [rbp+pvar+8]
0x180052f1f  lea     rdx, MF_PD_AUDIO_ENCODING_BITRATE
0x180052f26  mov     rcx, rsi
0x180052f29  mov     rax, [rax+38h]
0x180052f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f32  test    eax, eax
0x180052f34  js      loc_180052FD1
0x180052f3a  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x180052f3e  mov     word ptr [rbp+pvar], r14w
0x180052f43  lea     rdx, PKEY_Audio_EncodingBitrate; struct _tagpropertykey *
  ... truncated ...
```
