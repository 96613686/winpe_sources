# CWMProperty::TranslateValue(tagPROPVARIANT const &,tagPROPVARIANT *,_GUID,_GUID)

- ea: `0x18007064c`
- end: `0x180070b12`
- name: `?TranslateValue@CWMProperty@@IEAAJAEBUtagPROPVARIANT@@PEAU2@U_GUID@@2@Z`
- size: `1222`
- prototype: `int(CWMProperty *__hidden this, const struct tagPROPVARIANT *, struct tagPROPVARIANT *, struct _GUID *__struct_ptr, struct _GUID *__struct_ptr)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18006e500`
- `0x18006fa60`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x18005d6f4`
- `0x18006c404`
- `0x18007064c`
- `0x180070b18`
- `0x180071330`
- `0x180071524`
- `0x180073310`
- `0x180073f40`
- `0x180074268`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180070973`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180070973`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007071a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070808`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800708cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007098f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070a58`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007071a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070808`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800708cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007098f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070a58`

## pseudocode

```c
__int64 __fastcall CWMProperty::TranslateValue(
        CWMProperty *this,
        struct tagPROPVARIANT *a2,
        struct tagPROPVARIANT *a3,
        struct _GUID *a4,
        struct _GUID *a5)
{
  VARTYPE vt; // r12
  unsigned int v9; // r12d
  int v10; // edi
  int v11; // eax
  int v12; // r15d
  unsigned int v13; // edx
  __int64 v14; // rdx
  HRESULT Element; // ebx
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
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 v39; // rdx
  CWMProperty *v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  _BYTE v48[4]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v49; // [rsp+34h] [rbp-44h]
  PROPVARIANT pvarSrc; // [rsp+38h] [rbp-40h] BYREF
  PROPVARIANT pvarDest; // [rsp+50h] [rbp-28h] BYREF

  vt = a2->vt;
  v49 = a2->vt & 0xEFFF;
  v9 = vt & 0x1000;
  memset(&pvarSrc, 0, sizeof(pvarSrc));
  v10 = MFGetAttributeUINT32(this, a4, v49);
  v11 = MFGetAttributeUINT32(this, a5, v9);
  v12 = v11;
  if ( !v9 || v11 )
  {
    CMFPropVariant::Copy(&pvarSrc, a2);
LABEL_28:
    if ( a2->vt == 65 )
    {
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v48, "CWMProperty::TranslateValue", 277);
      v30 = (__int64 *)CallStackTracing::s_wpInstance;
      Element = -1072875854;
      if ( !CallStackTracing::s_wpInstance )
      {
        v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, v29);
        CallStackTracing::s_wpInstance = v31;
        if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
        {
          v30 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v30 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v30 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875854 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CWMProperty::TranslateValue", 277, -1072875854);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
          this,
          -1072875854);
    }
    else
    {
      if ( v49 == v10 )
      {
        CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v48, "CWMProperty::TranslateValue", 286);
        Element = PropVariantCopy(a3, &pvarSrc);
        if ( Element >= 0 )
          goto LABEL_66;
        v36 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34, v35);
          CallStackTracing::s_wpInstance = v37;
          if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
          {
            v36 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v36 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v36 + 8) )
        {
          v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
          if ( *((_DWORD *)v38 + 499) != Element )
            CallStackContext::TraceFailure(v38, "CWMProperty::TranslateValue", 286, Element);
        }
        if ( !g_wppLevels )
          goto LABEL_66;
        v39 = 27;
      }
      else
      {
        if ( v9 && v12 )
          LOWORD(v10) = v10 | 0x1000;
        CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v48, "CWMProperty::TranslateValue", 297);
        Element = CWMProperty::WMPropVariantChangeType(v40, a3, &pvarSrc, v10);
        if ( Element >= 0 )
          goto LABEL_66;
        v44 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, v42, v43);
          CallStackTracing::s_wpInstance = v45;
          if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
          {
            v44 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v44 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v44 + 8) )
        {
          v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
          if ( *((_DWORD *)v46 + 499) != Element )
            CallStackContext::TraceFailure(v46, "CWMProperty::TranslateValue", 297, Element);
        }
        if ( !g_wppLevels )
          goto LABEL_66;
        v39 = 28;
      }
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v39,
        WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
        this,
        Element);
    }
LABEL_66:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v48);
    goto LABEL_67;
  }
  CMFPropVariant::CMFPropVariant(&pvarDest, a2);
  if ( !CMFPropVariant::GetElementCount((CMFPropVariant *)&pvarDest) )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v48, "CWMProperty::TranslateValue", 263);
    v24 = (__int64 *)CallStackTracing::s_wpInstance;
    Element = -1072875854;
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
      if ( *((_DWORD *)v26 + 499) != -1072875854 )
        CallStackContext::TraceFailure(v26, "CWMProperty::TranslateValue", 263, -1072875854);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
        this,
        -1072875854);
    goto LABEL_15;
  }
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v48, "CWMProperty::TranslateValue", 254);
  Element = CMFPropVariant::GetElement((CMFPropVariant *)&pvarDest, v13, &pvarSrc);
  if ( Element >= 0 )
  {
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v48);
    CMFPropVariant::Clear(&pvarDest);
    goto LABEL_28;
  }
  v18 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v16, v17);
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
    if ( *((_DWORD *)v20 + 499) != Element )
      CallStackContext::TraceFailure(v20, "CWMProperty::TranslateValue", 254, Element);
  }
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, Element);
LABEL_15:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v48);
  CMFPropVariant::Clear(&pvarDest);
LABEL_67:
  CMFPropVariant::Clear(&pvarSrc);
  return (unsigned int)Element;
}

```

## disassembly

```asm
0x18007064c  push    rbp
0x18007064e  push    rbx
0x18007064f  push    rsi
0x180070650  push    rdi
0x180070651  push    r12
0x180070653  push    r13
0x180070655  push    r14
0x180070657  push    r15
0x180070659  mov     rbp, rsp
0x18007065c  sub     rsp, 78h
0x180070660  movzx   r12d, word ptr [rdx]
0x180070664  mov     rsi, rcx
0x180070667  mov     rbx, [rbp+arg_20]
0x18007066b  mov     eax, r12d
0x18007066e  xor     ecx, ecx
0x180070670  btr     eax, 0Ch
0x180070674  mov     r13, r8
0x180070677  mov     qword ptr [rbp+pvarSrc+10h], rcx
0x18007067b  mov     r14, rdx
0x18007067e  mov     [rbp+var_44], eax
0x180070681  xorps   xmm0, xmm0
0x180070684  mov     r8d, eax
0x180070687  mov     rdx, r9
0x18007068a  mov     rcx, rsi
0x18007068d  and     r12d, 1000h
0x180070694  movups  xmmword ptr [rbp+pvarSrc], xmm0
0x180070698  call    MFGetAttributeUINT32
0x18007069d  mov     r8d, r12d
0x1800706a0  mov     rdx, rbx
0x1800706a3  mov     rcx, rsi
0x1800706a6  mov     edi, eax
0x1800706a8  call    MFGetAttributeUINT32
0x1800706ad  lea     rbx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x1800706b4  mov     r15d, eax
0x1800706b7  test    r12d, r12d
0x1800706ba  jz      loc_18007088C
0x1800706c0  test    eax, eax
0x1800706c2  jnz     loc_18007088C
0x1800706c8  mov     rdx, r14; pvarSrc
0x1800706cb  lea     rcx, [rbp+pvarDest]; pvarDest
0x1800706cf  call    ??0CMFPropVariant@@QEAA@AEBUtagPROPVARIANT@@@Z; CMFPropVariant::CMFPropVariant(tagPROPVARIANT const &)
0x1800706d4  lea     rcx, [rbp+pvarDest]; this
0x1800706d8  call    ?GetElementCount@CMFPropVariant@@QEBAKXZ; CMFPropVariant::GetElementCount(void)
0x1800706dd  lea     rcx, [rbp+var_48]; this
0x1800706e1  mov     rdx, rbx; char *
0x1800706e4  test    eax, eax
0x1800706e6  jz      loc_1800707E7
0x1800706ec  mov     r8d, 0FEh; int
0x1800706f2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800706f7  lea     r8, [rbp+pvarSrc]; struct tagPROPVARIANT *
0x1800706fb  lea     rcx, [rbp+pvarDest]; this
0x1800706ff  call    ?GetElement@CMFPropVariant@@QEBAJKPEAUtagPROPVARIANT@@@Z; CMFPropVariant::GetElement(ulong,tagPROPVARIANT *)
0x180070704  mov     ebx, eax
0x180070706  test    eax, eax
0x180070708  jns     loc_1800707C9
0x18007070e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180070715  test    rcx, rcx
0x180070718  jnz     short loc_18007075B
0x18007071a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180070720  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180070727  mov     rcx, rax
0x18007072a  test    rax, rax
0x18007072d  jz      short loc_18007074D
0x18007072f  mov     rax, [rax]
0x180070732  mov     edx, 7F0h
0x180070737  mov     rax, [rax+8]
0x18007073b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070740  test    eax, eax
0x180070742  jz      short loc_18007074D
0x180070744  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007074b  jmp     short loc_18007075B
0x18007074d  lea     rcx, qword_1800D6F70; this
0x180070754  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007075b  cmp     byte ptr [rcx+8], 0
0x18007075f  jz      short loc_180070786
0x180070761  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180070766  cmp     [rax+7CCh], ebx
0x18007076c  jz      short loc_180070786
0x18007076e  mov     r9d, ebx; int
0x180070771  lea     rdx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x180070778  mov     r8d, 0FEh; int
0x18007077e  mov     rcx, rax; this
0x180070781  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180070786  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007078d  jb      short loc_1800707B2
0x18007078f  mov     edx, 18h
0x180070794  mov     [rsp+78h+var_58], ebx
0x180070798  mov     rcx, cs:WPP_GLOBAL_Control
0x18007079f  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x1800707a6  mov     r9, rsi
0x1800707a9  mov     rcx, [rcx+10h]
0x1800707ad  call    WPP_SF_qD
0x1800707b2  lea     rcx, [rbp+var_48]; this
0x1800707b6  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800707bb  lea     rcx, [rbp+pvarDest]; pvar
0x1800707bf  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x1800707c4  jmp     loc_180070AF6
0x1800707c9  lea     rcx, [rbp+var_48]; this
0x1800707cd  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800707d2  lea     rcx, [rbp+pvarDest]; pvar
0x1800707d6  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x1800707db  lea     rbx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x1800707e2  jmp     loc_180070898
0x1800707e7  mov     r14d, 107h
0x1800707ed  mov     r8d, r14d; int
0x1800707f0  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800707f5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800707fc  mov     edi, 0C00D36B2h
0x180070801  mov     ebx, edi
0x180070803  test    rcx, rcx
0x180070806  jnz     short loc_180070849
0x180070808  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007080e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180070815  mov     rcx, rax
0x180070818  test    rax, rax
0x18007081b  jz      short loc_18007083B
0x18007081d  mov     rax, [rax]
0x180070820  mov     edx, 7F0h
0x180070825  mov     rax, [rax+8]
0x180070829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007082e  test    eax, eax
0x180070830  jz      short loc_18007083B
0x180070832  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180070839  jmp     short loc_180070849
0x18007083b  lea     rcx, qword_1800D6F70; this
0x180070842  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180070849  cmp     byte ptr [rcx+8], 0
0x18007084d  jz      short loc_180070871
0x18007084f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180070854  cmp     [rax+7CCh], edi
0x18007085a  jz      short loc_180070871
0x18007085c  mov     r9d, edi; int
0x18007085f  lea     rdx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x180070866  mov     r8d, r14d; int
0x180070869  mov     rcx, rax; this
0x18007086c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180070871  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180070878  jb      loc_1800707B2
0x18007087e  mov     edx, 19h
0x180070883  mov     [rsp+78h+var_58], edi
0x180070887  jmp     loc_180070798
0x18007088c  mov     rdx, r14; pvarSrc
0x18007088f  lea     rcx, [rbp+pvarSrc]; pvarDest
0x180070893  call    ?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::Copy(tagPROPVARIANT const *)
0x180070898  cmp     word ptr [r14], 41h ; 'A'
0x18007089d  jnz     loc_18007094F
0x1800708a3  mov     r14d, 115h
0x1800708a9  lea     rcx, [rbp+var_48]; this
0x1800708ad  mov     r8d, r14d; int
0x1800708b0  mov     rdx, rbx; char *
0x1800708b3  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800708b8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800708bf  mov     edi, 0C00D36B2h
0x1800708c4  mov     ebx, edi
0x1800708c6  test    rcx, rcx
0x1800708c9  jnz     short loc_18007090C
0x1800708cb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800708d1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800708d8  mov     rcx, rax
0x1800708db  test    rax, rax
0x1800708de  jz      short loc_1800708FE
0x1800708e0  mov     rax, [rax]
0x1800708e3  mov     edx, 7F0h
0x1800708e8  mov     rax, [rax+8]
0x1800708ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800708f1  test    eax, eax
0x1800708f3  jz      short loc_1800708FE
0x1800708f5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800708fc  jmp     short loc_18007090C
0x1800708fe  lea     rcx, qword_1800D6F70; this
0x180070905  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007090c  cmp     byte ptr [rcx+8], 0
0x180070910  jz      short loc_180070934
0x180070912  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180070917  cmp     [rax+7CCh], edi
0x18007091d  jz      short loc_180070934
0x18007091f  mov     r9d, edi; int
0x180070922  lea     rdx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x180070929  mov     r8d, r14d; int
0x18007092c  mov     rcx, rax; this
0x18007092f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180070934  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007093b  jb      loc_180070AED
0x180070941  mov     edx, 1Ah
0x180070946  mov     [rsp+78h+var_58], edi
0x18007094a  jmp     loc_180070AD3
0x18007094f  cmp     [rbp+var_44], edi
0x180070952  jnz     loc_180070A0F
0x180070958  mov     edi, 11Eh
0x18007095d  lea     rcx, [rbp+var_48]; this
0x180070961  mov     r8d, edi; int
0x180070964  mov     rdx, rbx; char *
0x180070967  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18007096c  lea     rdx, [rbp+pvarSrc]; pvarSrc
0x180070970  mov     rcx, r13; pvarDest
0x180070973  call    cs:__imp_PropVariantCopy
0x180070979  mov     ebx, eax
0x18007097b  test    eax, eax
0x18007097d  jns     loc_180070AED
0x180070983  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007098a  test    rcx, rcx
0x18007098d  jnz     short loc_1800709D0
0x18007098f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180070995  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007099c  mov     rcx, rax
0x18007099f  test    rax, rax
0x1800709a2  jz      short loc_1800709C2
0x1800709a4  mov     rax, [rax]
0x1800709a7  mov     edx, 7F0h
0x1800709ac  mov     rax, [rax+8]
0x1800709b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800709b5  test    eax, eax
0x1800709b7  jz      short loc_1800709C2
0x1800709b9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800709c0  jmp     short loc_1800709D0
0x1800709c2  lea     rcx, qword_1800D6F70; this
0x1800709c9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800709d0  cmp     byte ptr [rcx+8], 0
0x1800709d4  jz      short loc_1800709F8
0x1800709d6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800709db  cmp     [rax+7CCh], ebx
0x1800709e1  jz      short loc_1800709F8
0x1800709e3  mov     r9d, ebx; int
0x1800709e6  lea     rdx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x1800709ed  mov     r8d, edi; int
0x1800709f0  mov     rcx, rax; this
0x1800709f3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800709f8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800709ff  jb      loc_180070AED
0x180070a05  mov     edx, 1Bh
0x180070a0a  jmp     loc_180070ACF
0x180070a0f  test    r12d, r12d
0x180070a12  jz      short loc_180070A1D
0x180070a14  test    r15d, r15d
0x180070a17  jz      short loc_180070A1D
0x180070a19  bts     edi, 0Ch
0x180070a1d  mov     r14d, 129h
0x180070a23  lea     rcx, [rbp+var_48]; this
0x180070a27  mov     r8d, r14d; int
0x180070a2a  mov     rdx, rbx; char *
0x180070a2d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180070a32  movzx   r9d, di; unsigned __int16
0x180070a36  lea     r8, [rbp+pvarSrc]; struct tagPROPVARIANT *
0x180070a3a  mov     rdx, r13; struct tagPROPVARIANT *
0x180070a3d  call    ?WMPropVariantChangeType@CWMProperty@@IEAAJPEAUtagPROPVARIANT@@AEBU2@G@Z; CWMProperty::WMPropVariantChangeType(tagPROPVARIANT *,tagPROPVARIANT const &,ushort)
0x180070a42  mov     ebx, eax
0x180070a44  test    eax, eax
0x180070a46  jns     loc_180070AED
0x180070a4c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180070a53  test    rcx, rcx
0x180070a56  jnz     short loc_180070A99
0x180070a58  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180070a5e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180070a65  mov     rcx, rax
0x180070a68  test    rax, rax
0x180070a6b  jz      short loc_180070A8B
0x180070a6d  mov     rax, [rax]
0x180070a70  mov     edx, 7F0h
0x180070a75  mov     rax, [rax+8]
0x180070a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070a7e  test    eax, eax
0x180070a80  jz      short loc_180070A8B
0x180070a82  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180070a89  jmp     short loc_180070A99
0x180070a8b  lea     rcx, qword_1800D6F70; this
0x180070a92  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180070a99  cmp     byte ptr [rcx+8], 0
0x180070a9d  jz      short loc_180070AC1
0x180070a9f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180070aa4  cmp     [rax+7CCh], ebx
0x180070aaa  jz      short loc_180070AC1
0x180070aac  mov     r9d, ebx; int
0x180070aaf  lea     rdx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x180070ab6  mov     r8d, r14d; int
0x180070ab9  mov     rcx, rax; this
0x180070abc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180070ac1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180070ac8  jb      short loc_180070AED
0x180070aca  mov     edx, 1Ch
0x180070acf  mov     [rsp+78h+var_58], ebx
0x180070ad3  mov     rcx, cs:WPP_GLOBAL_Control
0x180070ada  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x180070ae1  mov     r9, rsi
0x180070ae4  mov     rcx, [rcx+10h]
0x180070ae8  call    WPP_SF_qD
0x180070aed  lea     rcx, [rbp+var_48]; this
0x180070af1  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180070af6  lea     rcx, [rbp+pvarSrc]; pvar
0x180070afa  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180070aff  mov     eax, ebx
0x180070b01  add     rsp, 78h
0x180070b05  pop     r15
0x180070b07  pop     r14
0x180070b09  pop     r13
0x180070b0b  pop     r12
0x180070b0d  pop     rdi
0x180070b0e  pop     rsi
0x180070b0f  pop     rbx
0x180070b10  pop     rbp
0x180070b11  retn
  ... truncated ...
```
