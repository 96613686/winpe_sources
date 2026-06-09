# CMFStreamingPropHandler::InsertPropertiesFromPresentationDescriptor(IMFPresentationDescriptor *)

- ea: `0x1800475c8`
- end: `0x180047dc3`
- name: `?InsertPropertiesFromPresentationDescriptor@CMFStreamingPropHandler@@QEAAJPEAUIMFPresentationDescriptor@@@Z`
- size: `2043`
- prototype: `__int64 __fastcall(CMFStreamingPropHandler *__hidden this, struct IMFPresentationDescriptor *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800223b8`

## callees

- `0x180001e80`
- `0x180016b18`
- `0x18002a100`
- `0x180031bdc`
- `0x180034a04`
- `0x180039e60`
- `0x180047278`
- `0x1800475c8`
- `0x180047dcc`
- `0x18004840c`
- `0x180056010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047632`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800476e9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047862`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800478d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047948`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800479b8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047ac0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047baf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047c9e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047d25`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047632`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800476e9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047862`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800478d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047948`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800479b8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047ac0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047baf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047c9e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047d25`

## string_xrefs

- `0x180047a15`: `CMFStreamingPropHandler::InsertPropertiesFromPresentationDescriptor`
- `0x180047d82`: `CMFStreamingPropHandler::InsertPropertiesFromPresentationDescriptor`

## pseudocode

```c
__int64 __fastcall CMFStreamingPropHandler::InsertPropertiesFromPresentationDescriptor(
        CMFStreamingPropHandler *this,
        struct IMFPresentationDescriptor *a2)
{
  struct IMFPresentationDescriptorVtbl *lpVtbl; // rax
  __int64 v5; // rdx
  int inserted; // ebx
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v10; // r8d
  __int64 v11; // rdx
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  char v14; // r12
  char v15; // r15
  unsigned int i; // r14d
  struct IMFPresentationDescriptorVtbl *v17; // rax
  HRESULT (__stdcall *GetStreamDescriptorByIndex)(IMFPresentationDescriptor *, DWORD, BOOL *, IMFStreamDescriptor **); // rax
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  int v26; // r8d
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  __int64 v33; // rdx
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  __int64 v36; // rdx
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  __int64 v39; // rdx
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  __int64 v42; // rdx
  __int64 *v43; // rcx
  CallStackTracing *v44; // rax
  struct IMFStreamDescriptor *v46; // [rsp+30h] [rbp-50h] BYREF
  PROPVARIANT pvar; // [rsp+38h] [rbp-48h] BYREF
  __int64 v48; // [rsp+50h] [rbp-30h] BYREF
  unsigned int v49; // [rsp+58h] [rbp-28h] BYREF
  int v50; // [rsp+5Ch] [rbp-24h] BYREF
  __int128 Buf1; // [rsp+60h] [rbp-20h] BYREF

  lpVtbl = a2->lpVtbl;
  v49 = 0;
  memset(&pvar, 0, sizeof(pvar));
  inserted = ((__int64 (__fastcall *)(struct IMFPresentationDescriptor *, unsigned int *))lpVtbl->GetStreamDescriptorCount)(
               a2,
               &v49);
  if ( inserted < 0 )
  {
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != inserted )
      {
        v10 = 97;
LABEL_114:
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFStreamingPropHandler::InsertPropertiesFromPresentationDescriptor",
          v10,
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
    v14 = 0;
    v15 = 0;
    for ( i = 0; i < v49; ++i )
    {
      v17 = a2->lpVtbl;
      v46 = 0;
      v48 = 0;
      v50 = 0;
      GetStreamDescriptorByIndex = v17->GetStreamDescriptorByIndex;
      Buf1 = 0;
      inserted = ((__int64 (__fastcall *)(struct IMFPresentationDescriptor *, _QWORD, int *, struct IMFStreamDescriptor **))GetStreamDescriptorByIndex)(
                   a2,
                   i,
                   &v50,
                   &v46);
      if ( inserted < 0 )
      {
        v31 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
          CallStackTracing::s_wpInstance = v32;
          if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
          {
            v31 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v31 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( !*((_BYTE *)v31 + 8) )
          goto LABEL_65;
        v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
        if ( *((_DWORD *)v25 + 499) == inserted )
          goto LABEL_65;
        v26 = 118;
LABEL_64:
        CallStackContext::TraceFailure(
          v25,
          "CMFStreamingPropHandler::InsertPropertiesFromPresentationDescriptor",
          v26,
          inserted);
        goto LABEL_65;
      }
      inserted = CMFStreamingPropHandler::InsertPropertiesFromStreamDescriptor(this, v46);
      if ( inserted < 0 )
      {
        v29 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
          CallStackTracing::s_wpInstance = v30;
          if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
          {
            v29 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v29 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( !*((_BYTE *)v29 + 8) )
          goto LABEL_65;
        v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
        if ( *((_DWORD *)v25 + 499) == inserted )
          goto LABEL_65;
        v26 = 119;
        goto LABEL_64;
      }
      inserted = ((__int64 (__fastcall *)(struct IMFStreamDescriptor *, __int64 *))v46->lpVtbl->GetMediaTypeHandler)(
                   v46,
                   &v48);
      if ( inserted < 0 )
      {
        v27 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
          CallStackTracing::s_wpInstance = v28;
          if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
          {
            v27 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v27 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( !*((_BYTE *)v27 + 8) )
          goto LABEL_65;
        v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
        if ( *((_DWORD *)v25 + 499) == inserted )
          goto LABEL_65;
        v26 = 120;
        goto LABEL_64;
      }
      inserted = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v48 + 64LL))(v48, &Buf1);
      if ( inserted < 0 )
      {
        v23 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
          CallStackTracing::s_wpInstance = v24;
          if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
          {
            v23 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v23 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v23 + 8) )
        {
          v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
          if ( *((_DWORD *)v25 + 499) != inserted )
          {
            v26 = 121;
            goto LABEL_64;
          }
        }
LABEL_65:
        ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v48);
        ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v46);
        goto LABEL_115;
      }
      if ( !memcmp_0(&Buf1, &MFMediaType_Video, 0x10u) )
      {
        v14 = 1;
      }
      else if ( !memcmp_0(&Buf1, &MFMediaType_Audio, 0x10u) )
      {
        v15 = 1;
      }
      ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v48);
      ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v46);
    }
    if ( !v15
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
      if ( !v14
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
        if ( !v15
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
            v43 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v42);
              CallStackTracing::s_wpInstance = v44;
              if ( v44
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
              {
                v43 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v43 = &qword_18006EB20;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
              }
            }
            if ( *((_BYTE *)v43 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != inserted )
              {
                v10 = 178;
                goto LABEL_114;
              }
            }
          }
        }
        else
        {
          v40 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39);
            CallStackTracing::s_wpInstance = v41;
            if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
            {
              v40 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v40 = &qword_18006EB20;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
            }
          }
          if ( *((_BYTE *)v40 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != inserted )
            {
              v10 = 168;
              goto LABEL_114;
            }
          }
        }
      }
      else
      {
        v37 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36);
          CallStackTracing::s_wpInstance = v38;
          if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
          {
            v37 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v37 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v37 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != inserted )
          {
            v10 = 155;
            goto LABEL_114;
          }
        }
      }
    }
    else
    {
      v34 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
        CallStackTracing::s_wpInstance = v35;
        if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
        {
          v34 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v34 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v34 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != inserted )
        {
          v10 = 142;
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
  v12 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
    CallStackTracing::s_wpInstance = v13;
    if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
    {
      v12 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v12 = &qword_18006EB20;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
    }
  }
  if ( *((_BYTE *)v12 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
    if ( *((_DWORD *)ThreadRelativeContext + 499) != inserted )
    {
      v10 = 106;
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
0x1800475c8  mov     [rsp-38h+arg_10], rbx
0x1800475cd  push    rbp
0x1800475ce  push    rsi
0x1800475cf  push    rdi
0x1800475d0  push    r12
0x1800475d2  push    r13
0x1800475d4  push    r14
0x1800475d6  push    r15
0x1800475d8  mov     rbp, rsp
0x1800475db  sub     rsp, 80h
0x1800475e2  mov     rax, cs:__security_cookie
0x1800475e9  xor     rax, rsp
0x1800475ec  mov     [rbp+var_10], rax
0x1800475f0  xor     eax, eax
0x1800475f2  mov     rsi, rdx
0x1800475f5  mov     qword ptr [rbp+pvar+10h], rax
0x1800475f9  mov     rdi, rcx
0x1800475fc  mov     rax, [rdx]
0x1800475ff  xorps   xmm0, xmm0
0x180047602  xor     r13d, r13d
0x180047605  lea     rdx, [rbp+var_28]
0x180047609  mov     rcx, rsi
0x18004760c  mov     [rbp+var_28], r13d
0x180047610  movups  xmmword ptr [rbp+pvar], xmm0
0x180047614  mov     rax, [rax+108h]
0x18004761b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047620  mov     ebx, eax
0x180047622  test    eax, eax
0x180047624  jns     short loc_180047699
0x180047626  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004762d  test    rcx, rcx
0x180047630  jnz     short loc_180047673
0x180047632  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180047638  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004763f  mov     rcx, rax
0x180047642  test    rax, rax
0x180047645  jz      short loc_180047665
0x180047647  mov     rax, [rax]
0x18004764a  mov     edx, 7F0h
0x18004764f  mov     rax, [rax+8]
0x180047653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047658  test    eax, eax
0x18004765a  jz      short loc_180047665
0x18004765c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180047663  jmp     short loc_180047673
0x180047665  lea     rcx, qword_18006EB20; this
0x18004766c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180047673  cmp     [rcx+8], r13b
0x180047677  jz      loc_180047D91
0x18004767d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180047682  cmp     [rax+7CCh], ebx
0x180047688  jz      loc_180047D91
0x18004768e  mov     r8d, 61h ; 'a'
0x180047694  jmp     loc_180047D7F
0x180047699  mov     rax, [rsi]
0x18004769c  lea     r8, [rbp+pvar+8]
0x1800476a0  lea     rdx, MF_PD_DURATION
0x1800476a7  mov     rcx, rsi
0x1800476aa  mov     rax, [rax+40h]
0x1800476ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800476b3  test    eax, eax
0x1800476b5  js      loc_180047759
0x1800476bb  mov     eax, 15h
0x1800476c0  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x1800476c4  lea     rdx, PKEY_Media_Duration; struct _tagpropertykey *
0x1800476cb  mov     word ptr [rbp+pvar], ax
0x1800476cf  mov     rcx, rdi; this
0x1800476d2  call    ?InsertProperty@CMFStreamingPropHandler@@QEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@@Z; CMFStreamingPropHandler::InsertProperty(_tagpropertykey const &,tagPROPVARIANT const &)
0x1800476d7  mov     ebx, eax
0x1800476d9  test    eax, eax
0x1800476db  jns     short loc_180047750
0x1800476dd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800476e4  test    rcx, rcx
0x1800476e7  jnz     short loc_18004772A
0x1800476e9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800476ef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800476f6  mov     rcx, rax
0x1800476f9  test    rax, rax
0x1800476fc  jz      short loc_18004771C
0x1800476fe  mov     rax, [rax]
0x180047701  mov     edx, 7F0h
0x180047706  mov     rax, [rax+8]
0x18004770a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004770f  test    eax, eax
0x180047711  jz      short loc_18004771C
0x180047713  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004771a  jmp     short loc_18004772A
0x18004771c  lea     rcx, qword_18006EB20; this
0x180047723  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004772a  cmp     [rcx+8], r13b
0x18004772e  jz      loc_180047D91
0x180047734  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180047739  cmp     [rax+7CCh], ebx
0x18004773f  jz      loc_180047D91
0x180047745  mov     r8d, 6Ah ; 'j'
0x18004774b  jmp     loc_180047D7F
0x180047750  lea     rcx, [rbp+pvar]; pvar
0x180047754  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180047759  mov     r12b, r13b
0x18004775c  mov     r15b, r13b
0x18004775f  mov     r14d, r13d
0x180047762  cmp     r14d, [rbp+var_28]
0x180047766  jnb     loc_180047A3B
0x18004776c  mov     rax, [rsi]
0x18004776f  lea     r9, [rbp+var_50]
0x180047773  xorps   xmm0, xmm0
0x180047776  mov     [rbp+var_50], r13
0x18004777a  lea     r8, [rbp+var_24]
0x18004777e  mov     [rbp+var_30], r13
0x180047782  mov     edx, r14d
0x180047785  mov     [rbp+var_24], r13d
0x180047789  mov     rax, [rax+110h]
0x180047790  mov     rcx, rsi
0x180047793  movups  [rbp+Buf1], xmm0
0x180047797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004779c  mov     ebx, eax
0x18004779e  test    eax, eax
0x1800477a0  js      loc_1800479AC
0x1800477a6  mov     rdx, [rbp+var_50]; struct IMFStreamDescriptor *
0x1800477aa  mov     rcx, rdi; this
0x1800477ad  call    ?InsertPropertiesFromStreamDescriptor@CMFStreamingPropHandler@@AEAAJPEAUIMFStreamDescriptor@@@Z; CMFStreamingPropHandler::InsertPropertiesFromStreamDescriptor(IMFStreamDescriptor *)
0x1800477b2  mov     ebx, eax
0x1800477b4  test    eax, eax
0x1800477b6  js      loc_18004793C
0x1800477bc  mov     rcx, [rbp+var_50]
0x1800477c0  lea     rdx, [rbp+var_30]
0x1800477c4  mov     rax, [rcx]
0x1800477c7  mov     rax, [rax+110h]
0x1800477ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800477d3  mov     ebx, eax
0x1800477d5  test    eax, eax
0x1800477d7  js      loc_1800478C9
0x1800477dd  mov     rcx, [rbp+var_30]
0x1800477e1  lea     rdx, [rbp+Buf1]
0x1800477e5  mov     rax, [rcx]
0x1800477e8  mov     rax, [rax+40h]
0x1800477ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800477f1  mov     ebx, eax
0x1800477f3  test    eax, eax
0x1800477f5  js      short loc_180047856
0x1800477f7  mov     r8d, 10h; Size
0x1800477fd  lea     rdx, MFMediaType_Video; Buf2
0x180047804  lea     rcx, [rbp+Buf1]; Buf1
0x180047808  call    memcmp_0
0x18004780d  test    eax, eax
0x18004780f  jnz     short loc_180047817
0x180047811  lea     r12d, [rax+1]
0x180047815  jmp     short loc_18004783C
0x180047817  mov     r8d, 10h; Size
0x18004781d  lea     rdx, MFMediaType_Audio; Buf2
0x180047824  lea     rcx, [rbp+Buf1]; Buf1
0x180047828  call    memcmp_0
0x18004782d  test    eax, eax
0x18004782f  movzx   r15d, r15b
0x180047833  mov     eax, 1
0x180047838  cmovz   r15d, eax
0x18004783c  lea     rcx, [rbp+var_30]
0x180047840  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x180047845  lea     rcx, [rbp+var_50]
0x180047849  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x18004784e  inc     r14d
0x180047851  jmp     loc_180047762
0x180047856  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004785d  test    rcx, rcx
0x180047860  jnz     short loc_1800478A3
0x180047862  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180047868  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004786f  mov     rcx, rax
0x180047872  test    rax, rax
0x180047875  jz      short loc_180047895
0x180047877  mov     rax, [rax]
0x18004787a  mov     edx, 7F0h
0x18004787f  mov     rax, [rax+8]
0x180047883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047888  test    eax, eax
0x18004788a  jz      short loc_180047895
0x18004788c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180047893  jmp     short loc_1800478A3
0x180047895  lea     rcx, qword_18006EB20; this
0x18004789c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800478a3  cmp     [rcx+8], r13b
0x1800478a7  jz      loc_180047A24
0x1800478ad  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800478b2  cmp     [rax+7CCh], ebx
0x1800478b8  jz      loc_180047A24
0x1800478be  mov     r8d, 79h ; 'y'
0x1800478c4  jmp     loc_180047A12
0x1800478c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800478d0  test    rcx, rcx
0x1800478d3  jnz     short loc_180047916
0x1800478d5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800478db  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800478e2  mov     rcx, rax
0x1800478e5  test    rax, rax
0x1800478e8  jz      short loc_180047908
0x1800478ea  mov     rax, [rax]
0x1800478ed  mov     edx, 7F0h
0x1800478f2  mov     rax, [rax+8]
0x1800478f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800478fb  test    eax, eax
0x1800478fd  jz      short loc_180047908
0x1800478ff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180047906  jmp     short loc_180047916
0x180047908  lea     rcx, qword_18006EB20; this
0x18004790f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180047916  cmp     [rcx+8], r13b
0x18004791a  jz      loc_180047A24
0x180047920  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180047925  cmp     [rax+7CCh], ebx
0x18004792b  jz      loc_180047A24
0x180047931  mov     r8d, 78h ; 'x'
0x180047937  jmp     loc_180047A12
0x18004793c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180047943  test    rcx, rcx
0x180047946  jnz     short loc_180047989
0x180047948  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004794e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180047955  mov     rcx, rax
0x180047958  test    rax, rax
0x18004795b  jz      short loc_18004797B
0x18004795d  mov     rax, [rax]
0x180047960  mov     edx, 7F0h
0x180047965  mov     rax, [rax+8]
0x180047969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004796e  test    eax, eax
0x180047970  jz      short loc_18004797B
0x180047972  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180047979  jmp     short loc_180047989
0x18004797b  lea     rcx, qword_18006EB20; this
0x180047982  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180047989  cmp     [rcx+8], r13b
0x18004798d  jz      loc_180047A24
0x180047993  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180047998  cmp     [rax+7CCh], ebx
0x18004799e  jz      loc_180047A24
0x1800479a4  mov     r8d, 77h ; 'w'
0x1800479aa  jmp     short loc_180047A12
0x1800479ac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800479b3  test    rcx, rcx
0x1800479b6  jnz     short loc_1800479F9
0x1800479b8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800479be  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800479c5  mov     rcx, rax
0x1800479c8  test    rax, rax
0x1800479cb  jz      short loc_1800479EB
0x1800479cd  mov     rax, [rax]
0x1800479d0  mov     edx, 7F0h
0x1800479d5  mov     rax, [rax+8]
0x1800479d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800479de  test    eax, eax
0x1800479e0  jz      short loc_1800479EB
0x1800479e2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800479e9  jmp     short loc_1800479F9
0x1800479eb  lea     rcx, qword_18006EB20; this
0x1800479f2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800479f9  cmp     [rcx+8], r13b
0x1800479fd  jz      short loc_180047A24
0x1800479ff  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180047a04  cmp     [rax+7CCh], ebx
0x180047a0a  jz      short loc_180047A24
0x180047a0c  mov     r8d, 76h ; 'v'; int
0x180047a12  mov     r9d, ebx; int
0x180047a15  lea     rdx, aCmfstreamingpr_0; "CMFStreamingPropHandler::InsertProperti"...
0x180047a1c  mov     rcx, rax; this
0x180047a1f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180047a24  lea     rcx, [rbp+var_30]
0x180047a28  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x180047a2d  lea     rcx, [rbp+var_50]
0x180047a31  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x180047a36  jmp     loc_180047D91
0x180047a3b  mov     r14d, 13h
0x180047a41  test    r15b, r15b
0x180047a44  jz      loc_180047B27
0x180047a4a  mov     rcx, [rdi+18h]
0x180047a4e  lea     r8, [rbp+pvar]
0x180047a52  lea     rdx, PKEY_Audio_EncodingBitrate
0x180047a59  mov     rax, [rcx]
0x180047a5c  mov     rax, [rax+28h]
0x180047a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047a65  test    eax, eax
0x180047a67  js      short loc_180047A74
0x180047a69  cmp     word ptr [rbp+pvar], r13w
0x180047a6e  jnz     loc_180047B27
0x180047a74  mov     rax, [rsi]
0x180047a77  lea     r8, [rbp+pvar+8]
0x180047a7b  lea     rdx, MF_PD_AUDIO_ENCODING_BITRATE
0x180047a82  mov     rcx, rsi
0x180047a85  mov     rax, [rax+38h]
0x180047a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047a8e  test    eax, eax
0x180047a90  js      loc_180047B27
0x180047a96  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x180047a9a  mov     word ptr [rbp+pvar], r14w
0x180047a9f  lea     rdx, PKEY_Audio_EncodingBitrate; struct _tagpropertykey *
0x180047aa6  mov     rcx, rdi; this
0x180047aa9  call    ?InsertProperty@CMFStreamingPropHandler@@QEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@@Z; CMFStreamingPropHandler::InsertProperty(_tagpropertykey const &,tagPROPVARIANT const &)
0x180047aae  mov     ebx, eax
0x180047ab0  test    eax, eax
0x180047ab2  jns     short loc_180047B27
0x180047ab4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
