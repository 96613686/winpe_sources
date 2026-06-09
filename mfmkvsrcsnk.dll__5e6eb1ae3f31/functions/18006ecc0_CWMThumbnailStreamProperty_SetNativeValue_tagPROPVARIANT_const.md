# CWMThumbnailStreamProperty::SetNativeValue(tagPROPVARIANT const &)

- ea: `0x18006ecc0`
- end: `0x18006f30c`
- name: `?SetNativeValue@CWMThumbnailStreamProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1612`
- prototype: `__int64 __fastcall(CWMThumbnailStreamProperty *__hidden this, PROPVARIANT *pvarSrc)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x18004f47c`
- `0x18006ca64`
- `0x18006ecc0`
- `0x180071330`
- `0x180071524`
- `0x180073310`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18006ef5f`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18006ef5f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006ecfe`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006ee9f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006ecfe`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006ee9f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ed5e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ee1c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006eebb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ef7b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f02b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f0dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f18a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f24d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ed5e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ee1c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006eebb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ef7b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f02b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f0dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f18a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006f24d`

## pseudocode

```c
__int64 __fastcall CWMThumbnailStreamProperty::SetNativeValue(PROPVARIANT *this, PROPVARIANT *pvarSrc)
{
  void *v4; // rax
  BYTE *pData; // r15
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rcx
  HRESULT ImageDataPtrAndSize; // ebx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  unsigned int v14; // r13d
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  BYTE *v27; // xmm1_8
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // r9
  __int64 *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // r9
  __int64 *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // r9
  __int64 *v55; // rcx
  CallStackTracing *v56; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned __int8 *v59; // [rsp+30h] [rbp-28h] BYREF
  PROPVARIANT pvarDest; // [rsp+38h] [rbp-20h] BYREF
  char v61; // [rsp+A0h] [rbp+48h] BYREF
  unsigned int v62; // [rsp+A8h] [rbp+50h] BYREF
  int v63; // [rsp+B0h] [rbp+58h] BYREF
  LPSTREAM ppstm; // [rsp+B8h] [rbp+60h] BYREF

  ppstm = 0;
  v63 = 0;
  v59 = 0;
  v62 = 0;
  memset(&pvarDest, 0, sizeof(pvarDest));
  PropVariantClear(this + 4);
  if ( (pvarSrc->vt & 0x41) == 0 )
  {
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v61,
      "CWMThumbnailStreamProperty::SetNativeValue",
      617);
    v55 = (__int64 *)CallStackTracing::s_wpInstance;
    ImageDataPtrAndSize = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v52, v53, v54);
      CallStackTracing::s_wpInstance = v56;
      if ( v56 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
      {
        v55 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v55 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v55 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CWMThumbnailStreamProperty::SetNativeValue",
          617,
          -2147418113);
    }
    if ( g_wppLevels )
    {
      v13 = 59;
      goto LABEL_93;
    }
    goto LABEL_94;
  }
  v4 = &pvarSrc->decVal.8;
  if ( (pvarSrc->vt & 0x1000) == 0 )
  {
    pData = pvarSrc->bstrblobVal.pData;
LABEL_16:
    v14 = *(_DWORD *)v4;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v61,
      "CWMThumbnailStreamProperty::SetNativeValue",
      584);
    ImageDataPtrAndSize = CMFPropVariant::Copy(&pvarDest, pvarSrc);
    if ( ImageDataPtrAndSize >= 0 )
    {
      ImageDataPtrAndSize = PropVariantClear(this + 5);
      if ( ImageDataPtrAndSize >= 0 )
      {
        v27 = pvarDest.bstrblobVal.pData;
        *(_OWORD *)&this[5].vt = *(_OWORD *)&pvarDest.vt;
        pvarDest.vt = 0;
        this[5].bstrblobVal.pData = v27;
        ImageDataPtrAndSize = CreateStreamOnHGlobal(0, 1, &ppstm);
        if ( ImageDataPtrAndSize >= 0 )
        {
          ImageDataPtrAndSize = CWMThumbnailStreamProperty::GetImageDataPtrAndSize(
                                  (CWMThumbnailStreamProperty *)this,
                                  pData,
                                  v14,
                                  &v59,
                                  &v62);
          if ( ImageDataPtrAndSize >= 0 )
          {
            ImageDataPtrAndSize = ((__int64 (__fastcall *)(LPSTREAM, unsigned __int8 *, _QWORD, int *))ppstm->lpVtbl->Write)(
                                    ppstm,
                                    v59,
                                    v62,
                                    &v63);
            if ( ImageDataPtrAndSize >= 0 )
            {
              ImageDataPtrAndSize = ((__int64 (__fastcall *)(LPSTREAM, _QWORD, _QWORD, _QWORD))ppstm->lpVtbl->Seek)(
                                      ppstm,
                                      0,
                                      0,
                                      0);
              if ( ImageDataPtrAndSize >= 0 )
              {
                this[4].hVal.QuadPart = (LONGLONG)ppstm;
                this[4].vt = 66;
                ppstm = 0;
              }
              else
              {
                v49 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46, v47, v48);
                  CallStackTracing::s_wpInstance = v50;
                  if ( v50
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
                  {
                    v49 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v49 = &qword_1800D6F70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                  }
                }
                if ( *((_BYTE *)v49 + 8) )
                {
                  v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
                  if ( *((_DWORD *)v51 + 499) != ImageDataPtrAndSize )
                    CallStackContext::TraceFailure(
                      v51,
                      "CWMThumbnailStreamProperty::SetNativeValue",
                      606,
                      ImageDataPtrAndSize);
                }
                if ( g_wppLevels )
                {
                  v13 = 58;
                  goto LABEL_93;
                }
              }
            }
            else
            {
              v43 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40, v41, v42);
                CallStackTracing::s_wpInstance = v44;
                if ( v44
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
                {
                  v43 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v43 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                }
              }
              if ( *((_BYTE *)v43 + 8) )
              {
                v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
                if ( *((_DWORD *)v45 + 499) != ImageDataPtrAndSize )
                  CallStackContext::TraceFailure(
                    v45,
                    "CWMThumbnailStreamProperty::SetNativeValue",
                    604,
                    ImageDataPtrAndSize);
              }
              if ( g_wppLevels )
              {
                v13 = 57;
                goto LABEL_93;
              }
            }
          }
          else
          {
            v37 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34, v35, v36);
              CallStackTracing::s_wpInstance = v38;
              if ( v38
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
              {
                v37 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v37 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
              }
            }
            if ( *((_BYTE *)v37 + 8) )
            {
              v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
              if ( *((_DWORD *)v39 + 499) != ImageDataPtrAndSize )
                CallStackContext::TraceFailure(
                  v39,
                  "CWMThumbnailStreamProperty::SetNativeValue",
                  602,
                  ImageDataPtrAndSize);
            }
            if ( g_wppLevels )
            {
              v13 = 56;
              goto LABEL_93;
            }
          }
        }
        else
        {
          v31 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v29, v30);
            CallStackTracing::s_wpInstance = v32;
            if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
            {
              v31 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v31 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v31 + 8) )
          {
            v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
            if ( *((_DWORD *)v33 + 499) != ImageDataPtrAndSize )
              CallStackContext::TraceFailure(
                v33,
                "CWMThumbnailStreamProperty::SetNativeValue",
                600,
                ImageDataPtrAndSize);
          }
          if ( g_wppLevels )
          {
            v13 = 55;
            goto LABEL_93;
          }
        }
      }
      else
      {
        v24 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
          CallStackTracing::s_wpInstance = v25;
          if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
          {
            v24 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v24 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v24 + 8) )
        {
          v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
          if ( *((_DWORD *)v26 + 499) != ImageDataPtrAndSize )
            CallStackContext::TraceFailure(v26, "CWMThumbnailStreamProperty::SetNativeValue", 585, ImageDataPtrAndSize);
        }
        if ( g_wppLevels )
        {
          v13 = 54;
          goto LABEL_93;
        }
      }
    }
    else
    {
      v18 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15, v16, v17);
        CallStackTracing::s_wpInstance = v19;
        if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
        {
          v18 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v18 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v18 + 8) )
      {
        v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
        if ( *((_DWORD *)v20 + 499) != ImageDataPtrAndSize )
          CallStackContext::TraceFailure(v20, "CWMThumbnailStreamProperty::SetNativeValue", 584, ImageDataPtrAndSize);
      }
      if ( g_wppLevels )
      {
        v13 = 53;
        goto LABEL_93;
      }
    }
    goto LABEL_94;
  }
  if ( *(_DWORD *)v4 )
  {
    v4 = pvarSrc->bstrblobVal.pData;
    pData = (BYTE *)*((_QWORD *)v4 + 1);
    goto LABEL_16;
  }
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v61,
    "CWMThumbnailStreamProperty::SetNativeValue",
    570);
  v9 = (__int64 *)CallStackTracing::s_wpInstance;
  ImageDataPtrAndSize = -2147024809;
  if ( !CallStackTracing::s_wpInstance )
  {
    v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v7, v8);
    CallStackTracing::s_wpInstance = v11;
    if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
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
    v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
    if ( *((_DWORD *)v12 + 499) != -2147024809 )
      CallStackContext::TraceFailure(v12, "CWMThumbnailStreamProperty::SetNativeValue", 570, -2147024809);
  }
  if ( g_wppLevels )
  {
    v13 = 52;
LABEL_93:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
      this,
      ImageDataPtrAndSize);
  }
LABEL_94:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v61);
  CMFPropVariant::Clear(&pvarDest);
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&ppstm);
  return (unsigned int)ImageDataPtrAndSize;
}

```

## disassembly

```asm
0x18006ecc0  push    rbp
0x18006ecc2  push    rbx
0x18006ecc3  push    rsi
0x18006ecc4  push    rdi
0x18006ecc5  push    r12
0x18006ecc7  push    r13
0x18006ecc9  push    r14
0x18006eccb  push    r15
0x18006eccd  mov     rbp, rsp
0x18006ecd0  sub     rsp, 58h
0x18006ecd4  xor     r14d, r14d
0x18006ecd7  mov     rsi, rcx
0x18006ecda  xorps   xmm0, xmm0
0x18006ecdd  mov     [rbp+ppstm], r14
0x18006ece1  xor     eax, eax
0x18006ece3  mov     [rbp+arg_10], r14d
0x18006ece7  add     rcx, 60h ; '`'; pvar
0x18006eceb  mov     [rbp+var_28], r14
0x18006ecef  mov     [rbp+arg_8], r14d
0x18006ecf3  mov     rbx, rdx
0x18006ecf6  movups  xmmword ptr [rbp+pvarDest], xmm0
0x18006ecfa  mov     qword ptr [rbp+pvarDest+10h], rax
0x18006ecfe  call    cs:__imp_PropVariantClear
0x18006ed04  test    byte ptr [rbx], 41h
0x18006ed07  jz      loc_18006F220
0x18006ed0d  mov     ecx, 1000h
0x18006ed12  lea     rax, [rbx+8]
0x18006ed16  test    [rbx], cx
0x18006ed19  jz      loc_18006EDDA
0x18006ed1f  cmp     [rax], r14d
0x18006ed22  jbe     short loc_18006ED31
0x18006ed24  mov     rax, [rbx+10h]
0x18006ed28  mov     r15, [rax+8]
0x18006ed2c  jmp     loc_18006EDDE
0x18006ed31  mov     r15d, 23Ah
0x18006ed37  lea     rdi, aCwmthumbnailst_2; "CWMThumbnailStreamProperty::SetNativeVa"...
0x18006ed3e  mov     r8d, r15d; int
0x18006ed41  lea     rcx, [rbp+arg_0]; this
0x18006ed45  mov     rdx, rdi; char *
0x18006ed48  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006ed4d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ed54  mov     ebx, 80070057h
0x18006ed59  test    rcx, rcx
0x18006ed5c  jnz     short loc_18006ED9F
0x18006ed5e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006ed64  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ed6b  mov     rcx, rax
0x18006ed6e  test    rax, rax
0x18006ed71  jz      short loc_18006ED91
0x18006ed73  mov     rax, [rax]
0x18006ed76  mov     edx, 7F0h
0x18006ed7b  mov     rax, [rax+8]
0x18006ed7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ed84  test    eax, eax
0x18006ed86  jz      short loc_18006ED91
0x18006ed88  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ed8f  jmp     short loc_18006ED9F
0x18006ed91  lea     rcx, qword_1800D6F70; this
0x18006ed98  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ed9f  cmp     [rcx+8], r14b
0x18006eda3  jz      short loc_18006EDC3
0x18006eda5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006edaa  cmp     [rax+7CCh], ebx
0x18006edb0  jz      short loc_18006EDC3
0x18006edb2  mov     r9d, ebx; int
0x18006edb5  mov     r8d, r15d; int
0x18006edb8  mov     rdx, rdi; char *
0x18006edbb  mov     rcx, rax; this
0x18006edbe  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006edc3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006edca  jb      loc_18006F2DE
0x18006edd0  mov     edx, 34h ; '4'
0x18006edd5  jmp     loc_18006F2C0
0x18006edda  mov     r15, [rbx+10h]
0x18006edde  mov     r13d, [rax]
0x18006ede1  lea     rdi, aCwmthumbnailst_2; "CWMThumbnailStreamProperty::SetNativeVa"...
0x18006ede8  mov     rdx, rdi; char *
0x18006edeb  lea     rcx, [rbp+arg_0]; this
0x18006edef  mov     r8d, 248h; int
0x18006edf5  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006edfa  mov     rdx, rbx; pvarSrc
0x18006edfd  lea     rcx, [rbp+pvarDest]; pvarDest
0x18006ee01  call    ?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::Copy(tagPROPVARIANT const *)
0x18006ee06  mov     ebx, eax
0x18006ee08  test    eax, eax
0x18006ee0a  jns     loc_18006EE9B
0x18006ee10  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ee17  test    rcx, rcx
0x18006ee1a  jnz     short loc_18006EE5D
0x18006ee1c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006ee22  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ee29  mov     rcx, rax
0x18006ee2c  test    rax, rax
0x18006ee2f  jz      short loc_18006EE4F
0x18006ee31  mov     rax, [rax]
0x18006ee34  mov     edx, 7F0h
0x18006ee39  mov     rax, [rax+8]
0x18006ee3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ee42  test    eax, eax
0x18006ee44  jz      short loc_18006EE4F
0x18006ee46  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ee4d  jmp     short loc_18006EE5D
0x18006ee4f  lea     rcx, qword_1800D6F70; this
0x18006ee56  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ee5d  cmp     [rcx+8], r14b
0x18006ee61  jz      short loc_18006EE84
0x18006ee63  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006ee68  cmp     [rax+7CCh], ebx
0x18006ee6e  jz      short loc_18006EE84
0x18006ee70  mov     r9d, ebx; int
0x18006ee73  mov     r8d, 248h; int
0x18006ee79  mov     rdx, rdi; char *
0x18006ee7c  mov     rcx, rax; this
0x18006ee7f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006ee84  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006ee8b  jb      loc_18006F2DE
0x18006ee91  mov     edx, 35h ; '5'
0x18006ee96  jmp     loc_18006F2C0
0x18006ee9b  lea     rcx, [rsi+78h]; pvar
0x18006ee9f  call    cs:__imp_PropVariantClear
0x18006eea5  mov     ebx, eax
0x18006eea7  test    eax, eax
0x18006eea9  jns     loc_18006EF3A
0x18006eeaf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006eeb6  test    rcx, rcx
0x18006eeb9  jnz     short loc_18006EEFC
0x18006eebb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006eec1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006eec8  mov     rcx, rax
0x18006eecb  test    rax, rax
0x18006eece  jz      short loc_18006EEEE
0x18006eed0  mov     rax, [rax]
0x18006eed3  mov     edx, 7F0h
0x18006eed8  mov     rax, [rax+8]
0x18006eedc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006eee1  test    eax, eax
0x18006eee3  jz      short loc_18006EEEE
0x18006eee5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006eeec  jmp     short loc_18006EEFC
0x18006eeee  lea     rcx, qword_1800D6F70; this
0x18006eef5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006eefc  cmp     [rcx+8], r14b
0x18006ef00  jz      short loc_18006EF23
0x18006ef02  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006ef07  cmp     [rax+7CCh], ebx
0x18006ef0d  jz      short loc_18006EF23
0x18006ef0f  mov     r9d, ebx; int
0x18006ef12  mov     r8d, 249h; int
0x18006ef18  mov     rdx, rdi; char *
0x18006ef1b  mov     rcx, rax; this
0x18006ef1e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006ef23  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006ef2a  jb      loc_18006F2DE
0x18006ef30  mov     edx, 36h ; '6'
0x18006ef35  jmp     loc_18006F2C0
0x18006ef3a  movups  xmm0, xmmword ptr [rbp+pvarDest]
0x18006ef3e  lea     r8, [rbp+ppstm]; ppstm
0x18006ef42  mov     edx, 1; fDeleteOnRelease
0x18006ef47  movsd   xmm1, qword ptr [rbp+pvarDest+10h]
0x18006ef4c  xor     ecx, ecx; hGlobal
0x18006ef4e  movups  xmmword ptr [rsi+78h], xmm0
0x18006ef52  mov     word ptr [rbp+pvarDest], r14w
0x18006ef57  movsd   qword ptr [rsi+88h], xmm1
0x18006ef5f  call    cs:__imp_CreateStreamOnHGlobal
0x18006ef65  mov     ebx, eax
0x18006ef67  test    eax, eax
0x18006ef69  jns     loc_18006EFFA
0x18006ef6f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ef76  test    rcx, rcx
0x18006ef79  jnz     short loc_18006EFBC
0x18006ef7b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006ef81  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ef88  mov     rcx, rax
0x18006ef8b  test    rax, rax
0x18006ef8e  jz      short loc_18006EFAE
0x18006ef90  mov     rax, [rax]
0x18006ef93  mov     edx, 7F0h
0x18006ef98  mov     rax, [rax+8]
0x18006ef9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006efa1  test    eax, eax
0x18006efa3  jz      short loc_18006EFAE
0x18006efa5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006efac  jmp     short loc_18006EFBC
0x18006efae  lea     rcx, qword_1800D6F70; this
0x18006efb5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006efbc  cmp     [rcx+8], r14b
0x18006efc0  jz      short loc_18006EFE3
0x18006efc2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006efc7  cmp     [rax+7CCh], ebx
0x18006efcd  jz      short loc_18006EFE3
0x18006efcf  mov     r9d, ebx; int
0x18006efd2  mov     r8d, 258h; int
0x18006efd8  mov     rdx, rdi; char *
0x18006efdb  mov     rcx, rax; this
0x18006efde  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006efe3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006efea  jb      loc_18006F2DE
0x18006eff0  mov     edx, 37h ; '7'
0x18006eff5  jmp     loc_18006F2C0
0x18006effa  lea     rax, [rbp+arg_8]
0x18006effe  mov     r8d, r13d; unsigned int
0x18006f001  lea     r9, [rbp+var_28]; unsigned __int8 **
0x18006f005  mov     [rsp+58h+var_38], rax; unsigned int *
0x18006f00a  mov     rdx, r15; unsigned __int8 *
0x18006f00d  mov     rcx, rsi; this
0x18006f010  call    ?GetImageDataPtrAndSize@CWMThumbnailStreamProperty@@AEAAJPEBEKPEAPEAEPEAK@Z; CWMThumbnailStreamProperty::GetImageDataPtrAndSize(uchar const *,ulong,uchar * *,ulong *)
0x18006f015  mov     ebx, eax
0x18006f017  test    eax, eax
0x18006f019  jns     loc_18006F0AA
0x18006f01f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f026  test    rcx, rcx
0x18006f029  jnz     short loc_18006F06C
0x18006f02b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006f031  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f038  mov     rcx, rax
0x18006f03b  test    rax, rax
0x18006f03e  jz      short loc_18006F05E
0x18006f040  mov     rax, [rax]
0x18006f043  mov     edx, 7F0h
0x18006f048  mov     rax, [rax+8]
0x18006f04c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f051  test    eax, eax
0x18006f053  jz      short loc_18006F05E
0x18006f055  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f05c  jmp     short loc_18006F06C
0x18006f05e  lea     rcx, qword_1800D6F70; this
0x18006f065  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f06c  cmp     [rcx+8], r14b
0x18006f070  jz      short loc_18006F093
0x18006f072  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006f077  cmp     [rax+7CCh], ebx
0x18006f07d  jz      short loc_18006F093
0x18006f07f  mov     r9d, ebx; int
0x18006f082  mov     r8d, 25Ah; int
0x18006f088  mov     rdx, rdi; char *
0x18006f08b  mov     rcx, rax; this
0x18006f08e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006f093  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006f09a  jb      loc_18006F2DE
0x18006f0a0  mov     edx, 38h ; '8'
0x18006f0a5  jmp     loc_18006F2C0
0x18006f0aa  mov     rcx, [rbp+ppstm]
0x18006f0ae  lea     r9, [rbp+arg_10]
0x18006f0b2  mov     r8d, [rbp+arg_8]
0x18006f0b6  mov     rdx, [rbp+var_28]
0x18006f0ba  mov     rax, [rcx]
0x18006f0bd  mov     rax, [rax+20h]
0x18006f0c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f0c6  mov     ebx, eax
0x18006f0c8  test    eax, eax
0x18006f0ca  jns     loc_18006F15B
0x18006f0d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f0d7  test    rcx, rcx
0x18006f0da  jnz     short loc_18006F11D
0x18006f0dc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006f0e2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f0e9  mov     rcx, rax
0x18006f0ec  test    rax, rax
0x18006f0ef  jz      short loc_18006F10F
0x18006f0f1  mov     rax, [rax]
0x18006f0f4  mov     edx, 7F0h
0x18006f0f9  mov     rax, [rax+8]
0x18006f0fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f102  test    eax, eax
0x18006f104  jz      short loc_18006F10F
0x18006f106  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f10d  jmp     short loc_18006F11D
0x18006f10f  lea     rcx, qword_1800D6F70; this
0x18006f116  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f11d  cmp     [rcx+8], r14b
0x18006f121  jz      short loc_18006F144
0x18006f123  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006f128  cmp     [rax+7CCh], ebx
0x18006f12e  jz      short loc_18006F144
0x18006f130  mov     r9d, ebx; int
0x18006f133  mov     r8d, 25Ch; int
0x18006f139  mov     rdx, rdi; char *
0x18006f13c  mov     rcx, rax; this
0x18006f13f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006f144  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006f14b  jb      loc_18006F2DE
0x18006f151  mov     edx, 39h ; '9'
0x18006f156  jmp     loc_18006F2C0
0x18006f15b  mov     rcx, [rbp+ppstm]
0x18006f15f  mov     rdx, r14
0x18006f162  xor     r9d, r9d
0x18006f165  xor     r8d, r8d
0x18006f168  mov     rax, [rcx]
0x18006f16b  mov     rax, [rax+28h]
0x18006f16f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f174  mov     ebx, eax
0x18006f176  test    eax, eax
0x18006f178  jns     loc_18006F209
0x18006f17e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f185  test    rcx, rcx
0x18006f188  jnz     short loc_18006F1CB
0x18006f18a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006f190  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006f197  mov     rcx, rax
0x18006f19a  test    rax, rax
  ... truncated ...
```
