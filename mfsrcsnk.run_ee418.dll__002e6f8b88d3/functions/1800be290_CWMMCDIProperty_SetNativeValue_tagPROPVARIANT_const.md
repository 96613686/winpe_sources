# CWMMCDIProperty::SetNativeValue(tagPROPVARIANT const &)

- ea: `0x1800be290`
- end: `0x1800be62f`
- name: `?SetNativeValue@CWMMCDIProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `927`
- prototype: `int(CWMMCDIProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x180012a20`
- `0x18001303c`
- `0x180018b90`
- `0x180073b14`
- `0x1800be290`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800be2f2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800be394`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800be440`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800be4e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800be584`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800be2f2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800be394`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800be440`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800be4e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800be584`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800be41c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800be41c`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800be378`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800be378`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800be2a8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800be2d6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800be2a8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800be2d6`

## pseudocode

```c
__int64 __fastcall CWMMCDIProperty::SetNativeValue(PROPVARIANT *this, const struct tagPROPVARIANT *a2)
{
  __int64 v4; // rdx
  HRESULT v5; // edi
  __int64 v6; // r8
  __int64 v7; // r9
  wchar_t *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  unsigned __int16 *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  wchar_t *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  wchar_t *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  char v38; // [rsp+70h] [rbp+8h] BYREF

  PropVariantClear(this + 4);
  if ( a2->vt == 65 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CWMMCDIProperty::SetNativeValue", 423);
    v5 = PropVariantClear(this + 5);
    if ( v5 >= 0 )
    {
      v5 = PropVariantCopy(this + 5, a2);
      if ( v5 >= 0 )
      {
        this[4].vt = 31;
        v18 = (unsigned __int16 *)CoTaskMemAlloc(a2->ulVal);
        this[4].hVal.QuadPart = (LONGLONG)v18;
        if ( v18 )
        {
          v5 = StringCchCopyW(v18, (unsigned __int64)a2->ulVal >> 1, a2->caui.pElems);
          if ( v5 < 0 )
          {
            v28 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v26, v27);
              CallStackTracing::s_wpInstance = v29;
              if ( v29
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
              {
                v28 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v28 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v28 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
                CallStackContext::TraceFailure(ThreadRelativeContext, "CWMMCDIProperty::SetNativeValue", 446, v5);
            }
            if ( g_wppLevels )
            {
              v11 = 38;
              goto LABEL_56;
            }
          }
        }
        else
        {
          v22 = (wchar_t *)CallStackTracing::s_wpInstance;
          v5 = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20, v21);
            CallStackTracing::s_wpInstance = v23;
            if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
            {
              v22 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v22 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v22 + 8) )
          {
            v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
            if ( *((_DWORD *)v24 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v24, "CWMMCDIProperty::SetNativeValue", 438, -2147024882);
          }
          if ( g_wppLevels )
          {
            v11 = 37;
            goto LABEL_56;
          }
        }
      }
      else
      {
        v15 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
          CallStackTracing::s_wpInstance = v16;
          if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
          {
            v15 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v15 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v15 + 8) )
        {
          v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
          if ( *((_DWORD *)v17 + 499) != v5 )
            CallStackContext::TraceFailure(v17, "CWMMCDIProperty::SetNativeValue", 425, v5);
        }
        if ( g_wppLevels )
        {
          v11 = 36;
          goto LABEL_56;
        }
      }
    }
    else
    {
      v8 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v6, v7);
        CallStackTracing::s_wpInstance = v9;
        if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
        {
          v8 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v8 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v8 + 8) )
      {
        v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
        if ( *((_DWORD *)v10 + 499) != v5 )
          CallStackContext::TraceFailure(v10, "CWMMCDIProperty::SetNativeValue", 423, v5);
      }
      if ( g_wppLevels )
      {
        v11 = 35;
LABEL_56:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v5);
      }
    }
  }
  else
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CWMMCDIProperty::SetNativeValue", 451);
    v34 = (wchar_t *)CallStackTracing::s_wpInstance;
    v5 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32, v33);
      CallStackTracing::s_wpInstance = v35;
      if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
      {
        v34 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v34 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v34 + 8) )
    {
      v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
      if ( *((_DWORD *)v36 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v36, "CWMMCDIProperty::SetNativeValue", 451, -2147418113);
    }
    if ( g_wppLevels )
    {
      v11 = 39;
      goto LABEL_56;
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v38);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800be290  push    rbp
0x1800be292  push    rsi
0x1800be293  push    rdi
0x1800be294  push    r12
0x1800be296  push    r14
0x1800be298  push    r15
0x1800be29a  sub     rsp, 38h
0x1800be29e  mov     rbp, rcx
0x1800be2a1  mov     rsi, rdx
0x1800be2a4  add     rcx, 60h ; '`'; pvar
0x1800be2a8  call    cs:__imp_PropVariantClear
0x1800be2ae  cmp     word ptr [rsi], 41h ; 'A'
0x1800be2b2  lea     r14, aCwmmcdipropert_0; "CWMMCDIProperty::SetNativeValue"
0x1800be2b9  mov     rdx, r14; char *
0x1800be2bc  lea     rcx, [rsp+68h+arg_0]; this
0x1800be2c1  jnz     loc_1800BE566
0x1800be2c7  mov     r8d, 1A7h; int
0x1800be2cd  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800be2d2  lea     rcx, [rbp+78h]; pvar
0x1800be2d6  call    cs:__imp_PropVariantClear
0x1800be2dc  mov     edi, eax
0x1800be2de  test    eax, eax
0x1800be2e0  jns     loc_1800BE371
0x1800be2e6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800be2ed  test    rcx, rcx
0x1800be2f0  jnz     short loc_1800BE333
0x1800be2f2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800be2f8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800be2ff  mov     rcx, rax
0x1800be302  test    rax, rax
0x1800be305  jz      short loc_1800BE325
0x1800be307  mov     rax, [rax]
0x1800be30a  mov     edx, 7F0h
0x1800be30f  mov     rax, [rax+8]
0x1800be313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be318  test    eax, eax
0x1800be31a  jz      short loc_1800BE325
0x1800be31c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800be323  jmp     short loc_1800BE333
0x1800be325  lea     rcx, qword_1801B07E0; this
0x1800be32c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800be333  cmp     byte ptr [rcx+8], 0
0x1800be337  jz      short loc_1800BE35A
0x1800be339  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800be33e  cmp     [rax+7CCh], edi
0x1800be344  jz      short loc_1800BE35A
0x1800be346  mov     r9d, edi; int
0x1800be349  mov     r8d, 1A7h; int
0x1800be34f  mov     rdx, r14; char *
0x1800be352  mov     rcx, rax; this
0x1800be355  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800be35a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800be361  jb      loc_1800BE615
0x1800be367  mov     edx, 23h ; '#'
0x1800be36c  jmp     loc_1800BE5F7
0x1800be371  mov     rdx, rsi; pvarSrc
0x1800be374  lea     rcx, [rbp+78h]; pvarDest
0x1800be378  call    cs:__imp_PropVariantCopy
0x1800be37e  mov     edi, eax
0x1800be380  test    eax, eax
0x1800be382  jns     loc_1800BE413
0x1800be388  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800be38f  test    rcx, rcx
0x1800be392  jnz     short loc_1800BE3D5
0x1800be394  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800be39a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800be3a1  mov     rcx, rax
0x1800be3a4  test    rax, rax
0x1800be3a7  jz      short loc_1800BE3C7
0x1800be3a9  mov     rax, [rax]
0x1800be3ac  mov     edx, 7F0h
0x1800be3b1  mov     rax, [rax+8]
0x1800be3b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be3ba  test    eax, eax
0x1800be3bc  jz      short loc_1800BE3C7
0x1800be3be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800be3c5  jmp     short loc_1800BE3D5
0x1800be3c7  lea     rcx, qword_1801B07E0; this
0x1800be3ce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800be3d5  cmp     byte ptr [rcx+8], 0
0x1800be3d9  jz      short loc_1800BE3FC
0x1800be3db  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800be3e0  cmp     [rax+7CCh], edi
0x1800be3e6  jz      short loc_1800BE3FC
0x1800be3e8  mov     r9d, edi; int
0x1800be3eb  mov     r8d, 1A9h; int
0x1800be3f1  mov     rdx, r14; char *
0x1800be3f4  mov     rcx, rax; this
0x1800be3f7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800be3fc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800be403  jb      loc_1800BE615
0x1800be409  mov     edx, 24h ; '$'
0x1800be40e  jmp     loc_1800BE5F7
0x1800be413  mov     word ptr [rbp+60h], 1Fh
0x1800be419  mov     ecx, [rsi+8]; cb
0x1800be41c  call    cs:__imp_CoTaskMemAlloc
0x1800be422  mov     [rbp+68h], rax
0x1800be426  test    rax, rax
0x1800be429  jnz     loc_1800BE4BF
0x1800be42f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800be436  mov     edi, 8007000Eh
0x1800be43b  test    rcx, rcx
0x1800be43e  jnz     short loc_1800BE481
0x1800be440  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800be446  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800be44d  mov     rcx, rax
0x1800be450  test    rax, rax
0x1800be453  jz      short loc_1800BE473
0x1800be455  mov     rax, [rax]
0x1800be458  mov     edx, 7F0h
0x1800be45d  mov     rax, [rax+8]
0x1800be461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be466  test    eax, eax
0x1800be468  jz      short loc_1800BE473
0x1800be46a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800be471  jmp     short loc_1800BE481
0x1800be473  lea     rcx, qword_1801B07E0; this
0x1800be47a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800be481  cmp     byte ptr [rcx+8], 0
0x1800be485  jz      short loc_1800BE4A8
0x1800be487  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800be48c  cmp     [rax+7CCh], edi
0x1800be492  jz      short loc_1800BE4A8
0x1800be494  mov     r9d, edi; int
0x1800be497  mov     r8d, 1B6h; int
0x1800be49d  mov     rdx, r14; char *
0x1800be4a0  mov     rcx, rax; this
0x1800be4a3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800be4a8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800be4af  jb      loc_1800BE615
0x1800be4b5  mov     edx, 25h ; '%'
0x1800be4ba  jmp     loc_1800BE5F7
0x1800be4bf  mov     edx, [rsi+8]
0x1800be4c2  mov     rcx, rax; unsigned __int16 *
0x1800be4c5  mov     r8, [rsi+10h]; unsigned __int16 *
0x1800be4c9  shr     rdx, 1; unsigned __int64
0x1800be4cc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800be4d1  mov     edi, eax
0x1800be4d3  test    eax, eax
0x1800be4d5  jns     loc_1800BE615
0x1800be4db  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800be4e2  test    rcx, rcx
0x1800be4e5  jnz     short loc_1800BE528
0x1800be4e7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800be4ed  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800be4f4  mov     rcx, rax
0x1800be4f7  test    rax, rax
0x1800be4fa  jz      short loc_1800BE51A
0x1800be4fc  mov     rax, [rax]
0x1800be4ff  mov     edx, 7F0h
0x1800be504  mov     rax, [rax+8]
0x1800be508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be50d  test    eax, eax
0x1800be50f  jz      short loc_1800BE51A
0x1800be511  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800be518  jmp     short loc_1800BE528
0x1800be51a  lea     rcx, qword_1801B07E0; this
0x1800be521  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800be528  cmp     byte ptr [rcx+8], 0
0x1800be52c  jz      short loc_1800BE54F
0x1800be52e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800be533  cmp     [rax+7CCh], edi
0x1800be539  jz      short loc_1800BE54F
0x1800be53b  mov     r9d, edi; int
0x1800be53e  mov     r8d, 1BEh; int
0x1800be544  mov     rdx, r14; char *
0x1800be547  mov     rcx, rax; this
0x1800be54a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800be54f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800be556  jb      loc_1800BE615
0x1800be55c  mov     edx, 26h ; '&'
0x1800be561  jmp     loc_1800BE5F7
0x1800be566  mov     esi, 1C3h
0x1800be56b  mov     r8d, esi; int
0x1800be56e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800be573  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800be57a  mov     edi, 8000FFFFh
0x1800be57f  test    rcx, rcx
0x1800be582  jnz     short loc_1800BE5C5
0x1800be584  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800be58a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800be591  mov     rcx, rax
0x1800be594  test    rax, rax
0x1800be597  jz      short loc_1800BE5B7
0x1800be599  mov     rax, [rax]
0x1800be59c  mov     edx, 7F0h
0x1800be5a1  mov     rax, [rax+8]
0x1800be5a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be5aa  test    eax, eax
0x1800be5ac  jz      short loc_1800BE5B7
0x1800be5ae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800be5b5  jmp     short loc_1800BE5C5
0x1800be5b7  lea     rcx, qword_1801B07E0; this
0x1800be5be  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800be5c5  cmp     byte ptr [rcx+8], 0
0x1800be5c9  jz      short loc_1800BE5E9
0x1800be5cb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800be5d0  cmp     [rax+7CCh], edi
0x1800be5d6  jz      short loc_1800BE5E9
0x1800be5d8  mov     r9d, edi; int
0x1800be5db  mov     r8d, esi; int
0x1800be5de  mov     rdx, r14; char *
0x1800be5e1  mov     rcx, rax; this
0x1800be5e4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800be5e9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800be5f0  jb      short loc_1800BE615
0x1800be5f2  mov     edx, 27h ; '''
0x1800be5f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be5fe  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x1800be605  mov     r9, rbp
0x1800be608  mov     [rsp+68h+var_48], edi
0x1800be60c  mov     rcx, [rcx+10h]
0x1800be610  call    WPP_SF_qD
0x1800be615  lea     rcx, [rsp+68h+arg_0]; this
0x1800be61a  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800be61f  mov     eax, edi
0x1800be621  add     rsp, 38h
0x1800be625  pop     r15
0x1800be627  pop     r14
0x1800be629  pop     r12
0x1800be62b  pop     rdi
0x1800be62c  pop     rsi
0x1800be62d  pop     rbp
0x1800be62e  retn
```
