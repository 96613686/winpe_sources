# CWMThumbnailStreamProperty::SetNativeValue(tagPROPVARIANT const &)

- ea: `0x180052eb0`
- end: `0x180053500`
- name: `?SetNativeValue@CWMThumbnailStreamProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1616`
- prototype: `__int64 __fastcall(CWMThumbnailStreamProperty *__hidden this, PROPVARIANT *pvarSrc)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180016e48`
- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180034a04`
- `0x18003733c`
- `0x180039e60`
- `0x180051094`
- `0x180052eb0`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180053151`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180053151`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180052eee`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005308f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180052eee`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005308f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052f4e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005300c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800530ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005316d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005321d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800532ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005337c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005343f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052f4e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005300c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800530ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005316d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005321d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800532ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005337c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005343f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWMThumbnailStreamProperty::SetNativeValue(PROPVARIANT *this, PROPVARIANT *pvarSrc)
{
  void *v4; // rax
  BYTE *pData; // r15
  __int64 v6; // rdx
  HRESULT ImageDataPtrAndSize; // ebx
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  unsigned int v12; // r13d
  __int64 v13; // rdx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  LPSTREAM v37; // rax
  __int64 v38; // rdx
  __int64 *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned __int8 *v43; // [rsp+30h] [rbp-28h] BYREF
  PROPVARIANT pvarDest; // [rsp+38h] [rbp-20h] BYREF
  char v45; // [rsp+A0h] [rbp+48h] BYREF
  unsigned int v46; // [rsp+A8h] [rbp+50h] BYREF
  int v47; // [rsp+B0h] [rbp+58h] BYREF
  LPSTREAM ppstm; // [rsp+B8h] [rbp+60h] BYREF

  ppstm = 0;
  v47 = 0;
  v43 = 0;
  v46 = 0;
  memset(&pvarDest, 0, sizeof(pvarDest));
  PropVariantClear(this + 4);
  if ( (pvarSrc->vt & 0x41) == 0 )
  {
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v45,
      "CWMThumbnailStreamProperty::SetNativeValue",
      617);
    ImageDataPtrAndSize = -2147418113;
    v39 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38);
      CallStackTracing::s_wpInstance = v40;
      if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
      {
        v39 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v39 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v39 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CWMThumbnailStreamProperty::SetNativeValue",
          617,
          -2147418113);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v11 = 59;
      goto LABEL_93;
    }
    goto LABEL_94;
  }
  v4 = &pvarSrc->decVal.8;
  if ( (pvarSrc->vt & 0x1000) == 0 )
  {
    pData = pvarSrc->bstrblobVal.pData;
LABEL_16:
    v12 = *(_DWORD *)v4;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v45,
      "CWMThumbnailStreamProperty::SetNativeValue",
      584);
    ImageDataPtrAndSize = CMFPropVariant::Copy(&pvarDest, pvarSrc);
    if ( ImageDataPtrAndSize >= 0 )
    {
      ImageDataPtrAndSize = PropVariantClear(this + 5);
      if ( ImageDataPtrAndSize >= 0 )
      {
        this[5] = pvarDest;
        pvarDest.vt = 0;
        ImageDataPtrAndSize = CreateStreamOnHGlobal(0, 1, &ppstm);
        if ( ImageDataPtrAndSize >= 0 )
        {
          ImageDataPtrAndSize = CWMThumbnailStreamProperty::GetImageDataPtrAndSize(
                                  (CWMThumbnailStreamProperty *)this,
                                  pData,
                                  v12,
                                  &v43,
                                  &v46);
          if ( ImageDataPtrAndSize >= 0 )
          {
            ImageDataPtrAndSize = ((__int64 (__fastcall *)(LPSTREAM, unsigned __int8 *, _QWORD, int *))ppstm->lpVtbl->Write)(
                                    ppstm,
                                    v43,
                                    v46,
                                    &v47);
            if ( ImageDataPtrAndSize >= 0 )
            {
              ImageDataPtrAndSize = ((__int64 (__fastcall *)(LPSTREAM, _QWORD, _QWORD, _QWORD))ppstm->lpVtbl->Seek)(
                                      ppstm,
                                      0,
                                      0,
                                      0);
              if ( ImageDataPtrAndSize >= 0 )
              {
                this[4].vt = 66;
                v37 = ppstm;
                ppstm = 0;
                this[4].hVal.QuadPart = (LONGLONG)v37;
              }
              else
              {
                v34 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
                  CallStackTracing::s_wpInstance = v35;
                  if ( v35
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
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
                  v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
                  if ( *((_DWORD *)v36 + 499) != ImageDataPtrAndSize )
                    CallStackContext::TraceFailure(
                      v36,
                      "CWMThumbnailStreamProperty::SetNativeValue",
                      606,
                      ImageDataPtrAndSize);
                }
                if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                {
                  v11 = 58;
                  goto LABEL_93;
                }
              }
            }
            else
            {
              v30 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
                CallStackTracing::s_wpInstance = v31;
                if ( v31
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
                {
                  v30 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v30 = &qword_18006EB20;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                }
              }
              if ( *((_BYTE *)v30 + 8) )
              {
                v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
                if ( *((_DWORD *)v32 + 499) != ImageDataPtrAndSize )
                  CallStackContext::TraceFailure(
                    v32,
                    "CWMThumbnailStreamProperty::SetNativeValue",
                    604,
                    ImageDataPtrAndSize);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v11 = 57;
                goto LABEL_93;
              }
            }
          }
          else
          {
            v26 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
              CallStackTracing::s_wpInstance = v27;
              if ( v27
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
              {
                v26 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v26 = &qword_18006EB20;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
              }
            }
            if ( *((_BYTE *)v26 + 8) )
            {
              v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
              if ( *((_DWORD *)v28 + 499) != ImageDataPtrAndSize )
                CallStackContext::TraceFailure(
                  v28,
                  "CWMThumbnailStreamProperty::SetNativeValue",
                  602,
                  ImageDataPtrAndSize);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v11 = 56;
              goto LABEL_93;
            }
          }
        }
        else
        {
          v22 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
            CallStackTracing::s_wpInstance = v23;
            if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
            {
              v22 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v22 = &qword_18006EB20;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
            }
          }
          if ( *((_BYTE *)v22 + 8) )
          {
            v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
            if ( *((_DWORD *)v24 + 499) != ImageDataPtrAndSize )
              CallStackContext::TraceFailure(
                v24,
                "CWMThumbnailStreamProperty::SetNativeValue",
                600,
                ImageDataPtrAndSize);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v11 = 55;
            goto LABEL_93;
          }
        }
      }
      else
      {
        v18 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
          CallStackTracing::s_wpInstance = v19;
          if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
          {
            v18 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v18 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v18 + 8) )
        {
          v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
          if ( *((_DWORD *)v20 + 499) != ImageDataPtrAndSize )
            CallStackContext::TraceFailure(v20, "CWMThumbnailStreamProperty::SetNativeValue", 585, ImageDataPtrAndSize);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v11 = 54;
          goto LABEL_93;
        }
      }
    }
    else
    {
      v14 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
        CallStackTracing::s_wpInstance = v15;
        if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
        {
          v14 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v14 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v14 + 8) )
      {
        v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
        if ( *((_DWORD *)v16 + 499) != ImageDataPtrAndSize )
          CallStackContext::TraceFailure(v16, "CWMThumbnailStreamProperty::SetNativeValue", 584, ImageDataPtrAndSize);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v11 = 53;
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
    (CallStackScopeTrace *)&v45,
    "CWMThumbnailStreamProperty::SetNativeValue",
    570);
  ImageDataPtrAndSize = -2147024809;
  v8 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
    CallStackTracing::s_wpInstance = v9;
    if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
    {
      v8 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v8 = &qword_18006EB20;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
    }
  }
  if ( *((_BYTE *)v8 + 8) )
  {
    v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
    if ( *((_DWORD *)v10 + 499) != -2147024809 )
      CallStackContext::TraceFailure(v10, "CWMThumbnailStreamProperty::SetNativeValue", 570, -2147024809);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v11 = 52;
LABEL_93:
    WPP_SF_qd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
      this,
      ImageDataPtrAndSize);
  }
LABEL_94:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v45);
  CMFPropVariant::Clear(&pvarDest);
  ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(&ppstm);
  return (unsigned int)ImageDataPtrAndSize;
}

```

## disassembly

```asm
0x180052eb0  push    rbp
0x180052eb2  push    rbx
0x180052eb3  push    rsi
0x180052eb4  push    rdi
0x180052eb5  push    r12
0x180052eb7  push    r13
0x180052eb9  push    r14
0x180052ebb  push    r15
0x180052ebd  mov     rbp, rsp
0x180052ec0  sub     rsp, 58h
0x180052ec4  mov     rbx, rdx
0x180052ec7  mov     rsi, rcx
0x180052eca  xor     r14d, r14d
0x180052ecd  mov     [rbp+ppstm], r14
0x180052ed1  mov     [rbp+arg_10], r14d
0x180052ed5  mov     [rbp+var_28], r14
0x180052ed9  mov     [rbp+arg_8], r14d
0x180052edd  xorps   xmm0, xmm0
0x180052ee0  xor     eax, eax
0x180052ee2  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180052ee6  mov     qword ptr [rbp+pvarDest+10h], rax
0x180052eea  add     rcx, 60h ; '`'; pvar
0x180052eee  call    cs:__imp_PropVariantClear
0x180052ef4  test    byte ptr [rbx], 41h
0x180052ef7  jz      loc_180053412
0x180052efd  lea     rax, [rbx+8]
0x180052f01  mov     ecx, 1000h
0x180052f06  test    [rbx], cx
0x180052f09  jz      loc_180052FCA
0x180052f0f  cmp     [rax], r14d
0x180052f12  jbe     short loc_180052F21
0x180052f14  mov     rax, [rbx+10h]
0x180052f18  mov     r15, [rax+8]
0x180052f1c  jmp     loc_180052FCE
0x180052f21  mov     r15d, 23Ah
0x180052f27  mov     r8d, r15d; int
0x180052f2a  lea     rdi, aCwmthumbnailst_2; "CWMThumbnailStreamProperty::SetNativeVa"...
0x180052f31  mov     rdx, rdi; char *
0x180052f34  lea     rcx, [rbp+arg_0]; this
0x180052f38  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180052f3d  mov     ebx, 80070057h
0x180052f42  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052f49  test    rcx, rcx
0x180052f4c  jnz     short loc_180052F8F
0x180052f4e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180052f54  mov     rcx, rax
0x180052f57  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180052f5e  test    rax, rax
0x180052f61  jz      short loc_180052F81
0x180052f63  mov     rax, [rax]
0x180052f66  mov     edx, 7F0h
0x180052f6b  mov     rax, [rax+8]
0x180052f6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f74  test    eax, eax
0x180052f76  jz      short loc_180052F81
0x180052f78  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052f7f  jmp     short loc_180052F8F
0x180052f81  lea     rcx, qword_18006EB20; this
0x180052f88  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180052f8f  cmp     [rcx+8], r14b
0x180052f93  jz      short loc_180052FB3
0x180052f95  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180052f9a  cmp     [rax+7CCh], ebx
0x180052fa0  jz      short loc_180052FB3
0x180052fa2  mov     r9d, ebx; int
0x180052fa5  mov     r8d, r15d; int
0x180052fa8  mov     rdx, rdi; char *
0x180052fab  mov     rcx, rax; this
0x180052fae  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180052fb3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180052fb8  cmp     al, 1
0x180052fba  jb      loc_1800534D0
0x180052fc0  mov     edx, 34h ; '4'
0x180052fc5  jmp     loc_1800534B2
0x180052fca  mov     r15, [rbx+10h]
0x180052fce  mov     r13d, [rax]
0x180052fd1  mov     r8d, 248h; int
0x180052fd7  lea     rdi, aCwmthumbnailst_2; "CWMThumbnailStreamProperty::SetNativeVa"...
0x180052fde  mov     rdx, rdi; char *
0x180052fe1  lea     rcx, [rbp+arg_0]; this
0x180052fe5  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180052fea  mov     rdx, rbx; pvarSrc
0x180052fed  lea     rcx, [rbp+pvarDest]; pvarDest
0x180052ff1  call    ?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::Copy(tagPROPVARIANT const *)
0x180052ff6  mov     ebx, eax
0x180052ff8  test    eax, eax
0x180052ffa  jns     loc_18005308B
0x180053000  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053007  test    rcx, rcx
0x18005300a  jnz     short loc_18005304D
0x18005300c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053012  mov     rcx, rax
0x180053015  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005301c  test    rax, rax
0x18005301f  jz      short loc_18005303F
0x180053021  mov     rax, [rax]
0x180053024  mov     edx, 7F0h
0x180053029  mov     rax, [rax+8]
0x18005302d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053032  test    eax, eax
0x180053034  jz      short loc_18005303F
0x180053036  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005303d  jmp     short loc_18005304D
0x18005303f  lea     rcx, qword_18006EB20; this
0x180053046  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005304d  cmp     [rcx+8], r14b
0x180053051  jz      short loc_180053074
0x180053053  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053058  cmp     [rax+7CCh], ebx
0x18005305e  jz      short loc_180053074
0x180053060  mov     r9d, ebx; int
0x180053063  mov     r8d, 248h; int
0x180053069  mov     rdx, rdi; char *
0x18005306c  mov     rcx, rax; this
0x18005306f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180053074  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180053079  cmp     al, 1
0x18005307b  jb      loc_1800534D0
0x180053081  mov     edx, 35h ; '5'
0x180053086  jmp     loc_1800534B2
0x18005308b  lea     rcx, [rsi+78h]; pvar
0x18005308f  call    cs:__imp_PropVariantClear
0x180053095  mov     ebx, eax
0x180053097  test    eax, eax
0x180053099  jns     loc_18005312A
0x18005309f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800530a6  test    rcx, rcx
0x1800530a9  jnz     short loc_1800530EC
0x1800530ab  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800530b1  mov     rcx, rax
0x1800530b4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800530bb  test    rax, rax
0x1800530be  jz      short loc_1800530DE
0x1800530c0  mov     rax, [rax]
0x1800530c3  mov     edx, 7F0h
0x1800530c8  mov     rax, [rax+8]
0x1800530cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800530d1  test    eax, eax
0x1800530d3  jz      short loc_1800530DE
0x1800530d5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800530dc  jmp     short loc_1800530EC
0x1800530de  lea     rcx, qword_18006EB20; this
0x1800530e5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800530ec  cmp     byte ptr [rcx+8], 0
0x1800530f0  jz      short loc_180053113
0x1800530f2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800530f7  cmp     [rax+7CCh], ebx
0x1800530fd  jz      short loc_180053113
0x1800530ff  mov     r9d, ebx; int
0x180053102  mov     r8d, 249h; int
0x180053108  mov     rdx, rdi; char *
0x18005310b  mov     rcx, rax; this
0x18005310e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180053113  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180053118  cmp     al, 1
0x18005311a  jb      loc_1800534D0
0x180053120  mov     edx, 36h ; '6'
0x180053125  jmp     loc_1800534B2
0x18005312a  movups  xmm0, xmmword ptr [rbp+pvarDest]
0x18005312e  movups  xmmword ptr [rsi+78h], xmm0
0x180053132  movsd   xmm1, qword ptr [rbp+pvarDest+10h]
0x180053137  movsd   qword ptr [rsi+88h], xmm1
0x18005313f  xor     r14d, r14d
0x180053142  mov     word ptr [rbp+pvarDest], r14w
0x180053147  lea     r8, [rbp+ppstm]; ppstm
0x18005314b  lea     edx, [r14+1]; fDeleteOnRelease
0x18005314f  xor     ecx, ecx; hGlobal
0x180053151  call    cs:__imp_CreateStreamOnHGlobal
0x180053157  mov     ebx, eax
0x180053159  test    eax, eax
0x18005315b  jns     loc_1800531EC
0x180053161  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053168  test    rcx, rcx
0x18005316b  jnz     short loc_1800531AE
0x18005316d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053173  mov     rcx, rax
0x180053176  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005317d  test    rax, rax
0x180053180  jz      short loc_1800531A0
0x180053182  mov     rax, [rax]
0x180053185  mov     edx, 7F0h
0x18005318a  mov     rax, [rax+8]
0x18005318e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053193  test    eax, eax
0x180053195  jz      short loc_1800531A0
0x180053197  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005319e  jmp     short loc_1800531AE
0x1800531a0  lea     rcx, qword_18006EB20; this
0x1800531a7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800531ae  cmp     [rcx+8], r14b
0x1800531b2  jz      short loc_1800531D5
0x1800531b4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800531b9  cmp     [rax+7CCh], ebx
0x1800531bf  jz      short loc_1800531D5
0x1800531c1  mov     r9d, ebx; int
0x1800531c4  mov     r8d, 258h; int
0x1800531ca  mov     rdx, rdi; char *
0x1800531cd  mov     rcx, rax; this
0x1800531d0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800531d5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800531da  cmp     al, 1
0x1800531dc  jb      loc_1800534D0
0x1800531e2  mov     edx, 37h ; '7'
0x1800531e7  jmp     loc_1800534B2
0x1800531ec  lea     rax, [rbp+arg_8]
0x1800531f0  mov     [rsp+58h+var_38], rax; unsigned int *
0x1800531f5  lea     r9, [rbp+var_28]; unsigned __int8 **
0x1800531f9  mov     r8d, r13d; unsigned int
0x1800531fc  mov     rdx, r15; unsigned __int8 *
0x1800531ff  mov     rcx, rsi; this
0x180053202  call    ?GetImageDataPtrAndSize@CWMThumbnailStreamProperty@@AEAAJPEBEKPEAPEAEPEAK@Z; CWMThumbnailStreamProperty::GetImageDataPtrAndSize(uchar const *,ulong,uchar * *,ulong *)
0x180053207  mov     ebx, eax
0x180053209  test    eax, eax
0x18005320b  jns     loc_18005329C
0x180053211  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053218  test    rcx, rcx
0x18005321b  jnz     short loc_18005325E
0x18005321d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053223  mov     rcx, rax
0x180053226  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005322d  test    rax, rax
0x180053230  jz      short loc_180053250
0x180053232  mov     rax, [rax]
0x180053235  mov     edx, 7F0h
0x18005323a  mov     rax, [rax+8]
0x18005323e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053243  test    eax, eax
0x180053245  jz      short loc_180053250
0x180053247  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005324e  jmp     short loc_18005325E
0x180053250  lea     rcx, qword_18006EB20; this
0x180053257  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005325e  cmp     [rcx+8], r14b
0x180053262  jz      short loc_180053285
0x180053264  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053269  cmp     [rax+7CCh], ebx
0x18005326f  jz      short loc_180053285
0x180053271  mov     r9d, ebx; int
0x180053274  mov     r8d, 25Ah; int
0x18005327a  mov     rdx, rdi; char *
0x18005327d  mov     rcx, rax; this
0x180053280  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180053285  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18005328a  cmp     al, 1
0x18005328c  jb      loc_1800534D0
0x180053292  mov     edx, 38h ; '8'
0x180053297  jmp     loc_1800534B2
0x18005329c  mov     rcx, [rbp+ppstm]
0x1800532a0  mov     rax, [rcx]
0x1800532a3  lea     r9, [rbp+arg_10]
0x1800532a7  mov     r8d, [rbp+arg_8]
0x1800532ab  mov     rdx, [rbp+var_28]
0x1800532af  mov     rax, [rax+20h]
0x1800532b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800532b8  mov     ebx, eax
0x1800532ba  test    eax, eax
0x1800532bc  jns     loc_18005334D
0x1800532c2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800532c9  test    rcx, rcx
0x1800532cc  jnz     short loc_18005330F
0x1800532ce  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800532d4  mov     rcx, rax
0x1800532d7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800532de  test    rax, rax
0x1800532e1  jz      short loc_180053301
0x1800532e3  mov     rax, [rax]
0x1800532e6  mov     edx, 7F0h
0x1800532eb  mov     rax, [rax+8]
0x1800532ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800532f4  test    eax, eax
0x1800532f6  jz      short loc_180053301
0x1800532f8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800532ff  jmp     short loc_18005330F
0x180053301  lea     rcx, qword_18006EB20; this
0x180053308  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005330f  cmp     [rcx+8], r14b
0x180053313  jz      short loc_180053336
0x180053315  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005331a  cmp     [rax+7CCh], ebx
0x180053320  jz      short loc_180053336
0x180053322  mov     r9d, ebx; int
0x180053325  mov     r8d, 25Ch; int
0x18005332b  mov     rdx, rdi; char *
0x18005332e  mov     rcx, rax; this
0x180053331  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180053336  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18005333b  cmp     al, 1
0x18005333d  jb      loc_1800534D0
0x180053343  mov     edx, 39h ; '9'
0x180053348  jmp     loc_1800534B2
0x18005334d  mov     rcx, [rbp+ppstm]
0x180053351  mov     rdx, r14
0x180053354  mov     rax, [rcx]
0x180053357  xor     r9d, r9d
0x18005335a  xor     r8d, r8d
0x18005335d  mov     rax, [rax+28h]
0x180053361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053366  mov     ebx, eax
0x180053368  test    eax, eax
0x18005336a  jns     loc_1800533FB
  ... truncated ...
```
