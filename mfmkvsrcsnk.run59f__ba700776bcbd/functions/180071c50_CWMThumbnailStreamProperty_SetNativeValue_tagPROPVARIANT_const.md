# CWMThumbnailStreamProperty::SetNativeValue(tagPROPVARIANT const &)

- ea: `0x180071c50`
- end: `0x1800722df`
- name: `?SetNativeValue@CWMThumbnailStreamProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1679`
- prototype: `__int64 __fastcall(CWMThumbnailStreamProperty *__hidden this, PROPVARIANT *pvarSrc)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800516a4`
- `0x18006f8b4`
- `0x180071c50`
- `0x1800744d8`
- `0x1800746f8`
- `0x1800765d4`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180071f0d`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180071f0d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180071c8e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180071e41`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180071c8e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180071e41`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071cf4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071db8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071e63`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071f2f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071fe5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007209c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072150`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072219`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071cf4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071db8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071e63`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071f2f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071fe5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007209c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072150`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072219`

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
        v55 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                    v49 = &qword_1800DBF70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                  v43 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                v37 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
              v31 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v24 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v18 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
      v9 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
      &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
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
0x180071c50  push    rbp
0x180071c52  push    rbx
0x180071c53  push    rsi
0x180071c54  push    rdi
0x180071c55  push    r12
0x180071c57  push    r13
0x180071c59  push    r14
0x180071c5b  push    r15
0x180071c5d  mov     rbp, rsp
0x180071c60  sub     rsp, 58h
0x180071c64  xor     r14d, r14d
0x180071c67  mov     rsi, rcx
0x180071c6a  xorps   xmm0, xmm0
0x180071c6d  mov     [rbp+ppstm], r14
0x180071c71  xor     eax, eax
0x180071c73  mov     [rbp+arg_10], r14d
0x180071c77  add     rcx, 60h ; '`'; pvar
0x180071c7b  mov     [rbp+var_28], r14
0x180071c7f  mov     [rbp+arg_8], r14d
0x180071c83  mov     rbx, rdx
0x180071c86  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180071c8a  mov     qword ptr [rbp+pvarDest+10h], rax
0x180071c8e  call    cs:__imp_PropVariantClear
0x180071c95  nop     dword ptr [rax+rax+00h]
0x180071c9a  test    byte ptr [rbx], 41h
0x180071c9d  jz      loc_1800721EC
0x180071ca3  mov     ecx, 1000h
0x180071ca8  lea     rax, [rbx+8]
0x180071cac  test    [rbx], cx
0x180071caf  jz      loc_180071D76
0x180071cb5  cmp     [rax], r14d
0x180071cb8  jbe     short loc_180071CC7
0x180071cba  mov     rax, [rbx+10h]
0x180071cbe  mov     r15, [rax+8]
0x180071cc2  jmp     loc_180071D7A
0x180071cc7  mov     r15d, 23Ah
0x180071ccd  lea     rdi, aCwmthumbnailst_2; "CWMThumbnailStreamProperty::SetNativeVa"...
0x180071cd4  mov     r8d, r15d; int
0x180071cd7  lea     rcx, [rbp+arg_0]; this
0x180071cdb  mov     rdx, rdi; char *
0x180071cde  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180071ce3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071cea  mov     ebx, 80070057h
0x180071cef  test    rcx, rcx
0x180071cf2  jnz     short loc_180071D3B
0x180071cf4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180071cfb  nop     dword ptr [rax+rax+00h]
0x180071d00  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180071d07  mov     rcx, rax
0x180071d0a  test    rax, rax
0x180071d0d  jz      short loc_180071D2D
0x180071d0f  mov     rax, [rax]
0x180071d12  mov     edx, 7F0h
0x180071d17  mov     rax, [rax+8]
0x180071d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071d20  test    eax, eax
0x180071d22  jz      short loc_180071D2D
0x180071d24  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071d2b  jmp     short loc_180071D3B
0x180071d2d  lea     rcx, qword_1800DBF70; this
0x180071d34  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180071d3b  cmp     [rcx+8], r14b
0x180071d3f  jz      short loc_180071D5F
0x180071d41  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180071d46  cmp     [rax+7CCh], ebx
0x180071d4c  jz      short loc_180071D5F
0x180071d4e  mov     r9d, ebx; int
0x180071d51  mov     r8d, r15d; int
0x180071d54  mov     rdx, rdi; char *
0x180071d57  mov     rcx, rax; this
0x180071d5a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180071d5f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071d66  jb      loc_1800722B0
0x180071d6c  mov     edx, 34h ; '4'
0x180071d71  jmp     loc_180072292
0x180071d76  mov     r15, [rbx+10h]
0x180071d7a  mov     r13d, [rax]
0x180071d7d  lea     rdi, aCwmthumbnailst_2; "CWMThumbnailStreamProperty::SetNativeVa"...
0x180071d84  mov     rdx, rdi; char *
0x180071d87  lea     rcx, [rbp+arg_0]; this
0x180071d8b  mov     r8d, 248h; int
0x180071d91  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180071d96  mov     rdx, rbx; pvarSrc
0x180071d99  lea     rcx, [rbp+pvarDest]; pvarDest
0x180071d9d  call    ?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::Copy(tagPROPVARIANT const *)
0x180071da2  mov     ebx, eax
0x180071da4  test    eax, eax
0x180071da6  jns     loc_180071E3D
0x180071dac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071db3  test    rcx, rcx
0x180071db6  jnz     short loc_180071DFF
0x180071db8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180071dbf  nop     dword ptr [rax+rax+00h]
0x180071dc4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180071dcb  mov     rcx, rax
0x180071dce  test    rax, rax
0x180071dd1  jz      short loc_180071DF1
0x180071dd3  mov     rax, [rax]
0x180071dd6  mov     edx, 7F0h
0x180071ddb  mov     rax, [rax+8]
0x180071ddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071de4  test    eax, eax
0x180071de6  jz      short loc_180071DF1
0x180071de8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071def  jmp     short loc_180071DFF
0x180071df1  lea     rcx, qword_1800DBF70; this
0x180071df8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180071dff  cmp     [rcx+8], r14b
0x180071e03  jz      short loc_180071E26
0x180071e05  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180071e0a  cmp     [rax+7CCh], ebx
0x180071e10  jz      short loc_180071E26
0x180071e12  mov     r9d, ebx; int
0x180071e15  mov     r8d, 248h; int
0x180071e1b  mov     rdx, rdi; char *
0x180071e1e  mov     rcx, rax; this
0x180071e21  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180071e26  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071e2d  jb      loc_1800722B0
0x180071e33  mov     edx, 35h ; '5'
0x180071e38  jmp     loc_180072292
0x180071e3d  lea     rcx, [rsi+78h]; pvar
0x180071e41  call    cs:__imp_PropVariantClear
0x180071e48  nop     dword ptr [rax+rax+00h]
0x180071e4d  mov     ebx, eax
0x180071e4f  test    eax, eax
0x180071e51  jns     loc_180071EE8
0x180071e57  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071e5e  test    rcx, rcx
0x180071e61  jnz     short loc_180071EAA
0x180071e63  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180071e6a  nop     dword ptr [rax+rax+00h]
0x180071e6f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180071e76  mov     rcx, rax
0x180071e79  test    rax, rax
0x180071e7c  jz      short loc_180071E9C
0x180071e7e  mov     rax, [rax]
0x180071e81  mov     edx, 7F0h
0x180071e86  mov     rax, [rax+8]
0x180071e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071e8f  test    eax, eax
0x180071e91  jz      short loc_180071E9C
0x180071e93  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071e9a  jmp     short loc_180071EAA
0x180071e9c  lea     rcx, qword_1800DBF70; this
0x180071ea3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180071eaa  cmp     [rcx+8], r14b
0x180071eae  jz      short loc_180071ED1
0x180071eb0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180071eb5  cmp     [rax+7CCh], ebx
0x180071ebb  jz      short loc_180071ED1
0x180071ebd  mov     r9d, ebx; int
0x180071ec0  mov     r8d, 249h; int
0x180071ec6  mov     rdx, rdi; char *
0x180071ec9  mov     rcx, rax; this
0x180071ecc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180071ed1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071ed8  jb      loc_1800722B0
0x180071ede  mov     edx, 36h ; '6'
0x180071ee3  jmp     loc_180072292
0x180071ee8  movups  xmm0, xmmword ptr [rbp+pvarDest]
0x180071eec  lea     r8, [rbp+ppstm]; ppstm
0x180071ef0  mov     edx, 1; fDeleteOnRelease
0x180071ef5  movsd   xmm1, qword ptr [rbp+pvarDest+10h]
0x180071efa  xor     ecx, ecx; hGlobal
0x180071efc  movups  xmmword ptr [rsi+78h], xmm0
0x180071f00  mov     word ptr [rbp+pvarDest], r14w
0x180071f05  movsd   qword ptr [rsi+88h], xmm1
0x180071f0d  call    cs:__imp_CreateStreamOnHGlobal
0x180071f14  nop     dword ptr [rax+rax+00h]
0x180071f19  mov     ebx, eax
0x180071f1b  test    eax, eax
0x180071f1d  jns     loc_180071FB4
0x180071f23  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071f2a  test    rcx, rcx
0x180071f2d  jnz     short loc_180071F76
0x180071f2f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180071f36  nop     dword ptr [rax+rax+00h]
0x180071f3b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180071f42  mov     rcx, rax
0x180071f45  test    rax, rax
0x180071f48  jz      short loc_180071F68
0x180071f4a  mov     rax, [rax]
0x180071f4d  mov     edx, 7F0h
0x180071f52  mov     rax, [rax+8]
0x180071f56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071f5b  test    eax, eax
0x180071f5d  jz      short loc_180071F68
0x180071f5f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071f66  jmp     short loc_180071F76
0x180071f68  lea     rcx, qword_1800DBF70; this
0x180071f6f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180071f76  cmp     [rcx+8], r14b
0x180071f7a  jz      short loc_180071F9D
0x180071f7c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180071f81  cmp     [rax+7CCh], ebx
0x180071f87  jz      short loc_180071F9D
0x180071f89  mov     r9d, ebx; int
0x180071f8c  mov     r8d, 258h; int
0x180071f92  mov     rdx, rdi; char *
0x180071f95  mov     rcx, rax; this
0x180071f98  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180071f9d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071fa4  jb      loc_1800722B0
0x180071faa  mov     edx, 37h ; '7'
0x180071faf  jmp     loc_180072292
0x180071fb4  lea     rax, [rbp+arg_8]
0x180071fb8  mov     r8d, r13d; unsigned int
0x180071fbb  lea     r9, [rbp+var_28]; unsigned __int8 **
0x180071fbf  mov     [rsp+58h+var_38], rax; unsigned int *
0x180071fc4  mov     rdx, r15; unsigned __int8 *
0x180071fc7  mov     rcx, rsi; this
0x180071fca  call    ?GetImageDataPtrAndSize@CWMThumbnailStreamProperty@@AEAAJPEBEKPEAPEAEPEAK@Z; CWMThumbnailStreamProperty::GetImageDataPtrAndSize(uchar const *,ulong,uchar * *,ulong *)
0x180071fcf  mov     ebx, eax
0x180071fd1  test    eax, eax
0x180071fd3  jns     loc_18007206A
0x180071fd9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071fe0  test    rcx, rcx
0x180071fe3  jnz     short loc_18007202C
0x180071fe5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180071fec  nop     dword ptr [rax+rax+00h]
0x180071ff1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180071ff8  mov     rcx, rax
0x180071ffb  test    rax, rax
0x180071ffe  jz      short loc_18007201E
0x180072000  mov     rax, [rax]
0x180072003  mov     edx, 7F0h
0x180072008  mov     rax, [rax+8]
0x18007200c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072011  test    eax, eax
0x180072013  jz      short loc_18007201E
0x180072015  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007201c  jmp     short loc_18007202C
0x18007201e  lea     rcx, qword_1800DBF70; this
0x180072025  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007202c  cmp     [rcx+8], r14b
0x180072030  jz      short loc_180072053
0x180072032  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180072037  cmp     [rax+7CCh], ebx
0x18007203d  jz      short loc_180072053
0x18007203f  mov     r9d, ebx; int
0x180072042  mov     r8d, 25Ah; int
0x180072048  mov     rdx, rdi; char *
0x18007204b  mov     rcx, rax; this
0x18007204e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180072053  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007205a  jb      loc_1800722B0
0x180072060  mov     edx, 38h ; '8'
0x180072065  jmp     loc_180072292
0x18007206a  mov     rcx, [rbp+ppstm]
0x18007206e  lea     r9, [rbp+arg_10]
0x180072072  mov     r8d, [rbp+arg_8]
0x180072076  mov     rdx, [rbp+var_28]
0x18007207a  mov     rax, [rcx]
0x18007207d  mov     rax, [rax+20h]
0x180072081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072086  mov     ebx, eax
0x180072088  test    eax, eax
0x18007208a  jns     loc_180072121
0x180072090  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072097  test    rcx, rcx
0x18007209a  jnz     short loc_1800720E3
0x18007209c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800720a3  nop     dword ptr [rax+rax+00h]
0x1800720a8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800720af  mov     rcx, rax
0x1800720b2  test    rax, rax
0x1800720b5  jz      short loc_1800720D5
0x1800720b7  mov     rax, [rax]
0x1800720ba  mov     edx, 7F0h
0x1800720bf  mov     rax, [rax+8]
0x1800720c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800720c8  test    eax, eax
0x1800720ca  jz      short loc_1800720D5
0x1800720cc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800720d3  jmp     short loc_1800720E3
0x1800720d5  lea     rcx, qword_1800DBF70; this
0x1800720dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800720e3  cmp     [rcx+8], r14b
0x1800720e7  jz      short loc_18007210A
0x1800720e9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800720ee  cmp     [rax+7CCh], ebx
0x1800720f4  jz      short loc_18007210A
0x1800720f6  mov     r9d, ebx; int
0x1800720f9  mov     r8d, 25Ch; int
0x1800720ff  mov     rdx, rdi; char *
0x180072102  mov     rcx, rax; this
0x180072105  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007210a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180072111  jb      loc_1800722B0
0x180072117  mov     edx, 39h ; '9'
0x18007211c  jmp     loc_180072292
0x180072121  mov     rcx, [rbp+ppstm]
0x180072125  mov     rdx, r14
0x180072128  xor     r9d, r9d
0x18007212b  xor     r8d, r8d
0x18007212e  mov     rax, [rcx]
0x180072131  mov     rax, [rax+28h]
0x180072135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007213a  mov     ebx, eax
  ... truncated ...
```
