# CWMProperty::TranslateValue(tagPROPVARIANT const &,tagPROPVARIANT *,_GUID,_GUID)

- ea: `0x180073704`
- end: `0x180073bef`
- name: `?TranslateValue@CWMProperty@@IEAAJAEBUtagPROPVARIANT@@PEAU2@U_GUID@@2@Z`
- size: `1259`
- prototype: `int(CWMProperty *__hidden this, const struct tagPROPVARIANT *, struct tagPROPVARIANT *, struct _GUID *__struct_ptr, struct _GUID *__struct_ptr)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180071430`
- `0x180072a80`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x18005fed8`
- `0x18006f224`
- `0x180073704`
- `0x180073bf8`
- `0x1800744d8`
- `0x1800746f8`
- `0x1800765d4`
- `0x180077298`
- `0x1800775dc`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180073a3d`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180073a3d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800737d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800738c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007398f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073a5f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073b2e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800737d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800738c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007398f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073a5f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073b2e`

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
          v30 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
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
            v36 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v44 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
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
        v24 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
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
      v18 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
    }
  }
  if ( *((_BYTE *)v18 + 8) )
  {
    v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
    if ( *((_DWORD *)v20 + 499) != Element )
      CallStackContext::TraceFailure(v20, "CWMProperty::TranslateValue", 254, Element);
  }
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, Element);
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
0x180073704  push    rbp
0x180073706  push    rbx
0x180073707  push    rsi
0x180073708  push    rdi
0x180073709  push    r12
0x18007370b  push    r13
0x18007370d  push    r14
0x18007370f  push    r15
0x180073711  mov     rbp, rsp
0x180073714  sub     rsp, 78h
0x180073718  movzx   r12d, word ptr [rdx]
0x18007371c  mov     rsi, rcx
0x18007371f  mov     rbx, [rbp+arg_20]
0x180073723  mov     eax, r12d
0x180073726  xor     ecx, ecx
0x180073728  btr     eax, 0Ch
0x18007372c  mov     r13, r8
0x18007372f  mov     qword ptr [rbp+pvarSrc+10h], rcx
0x180073733  mov     r14, rdx
0x180073736  mov     [rbp+var_44], eax
0x180073739  xorps   xmm0, xmm0
0x18007373c  mov     r8d, eax
0x18007373f  mov     rdx, r9
0x180073742  mov     rcx, rsi
0x180073745  and     r12d, 1000h
0x18007374c  movups  xmmword ptr [rbp+pvarSrc], xmm0
0x180073750  call    MFGetAttributeUINT32
0x180073755  mov     r8d, r12d
0x180073758  mov     rdx, rbx
0x18007375b  mov     rcx, rsi
0x18007375e  mov     edi, eax
0x180073760  call    MFGetAttributeUINT32
0x180073765  lea     rbx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x18007376c  mov     r15d, eax
0x18007376f  test    r12d, r12d
0x180073772  jz      loc_180073950
0x180073778  test    eax, eax
0x18007377a  jnz     loc_180073950
0x180073780  mov     rdx, r14; pvarSrc
0x180073783  lea     rcx, [rbp+pvarDest]; pvarDest
0x180073787  call    ??0CMFPropVariant@@QEAA@AEBUtagPROPVARIANT@@@Z; CMFPropVariant::CMFPropVariant(tagPROPVARIANT const &)
0x18007378c  lea     rcx, [rbp+pvarDest]; this
0x180073790  call    ?GetElementCount@CMFPropVariant@@QEBAKXZ; CMFPropVariant::GetElementCount(void)
0x180073795  lea     rcx, [rbp+var_48]; this
0x180073799  mov     rdx, rbx; char *
0x18007379c  test    eax, eax
0x18007379e  jz      loc_1800738A5
0x1800737a4  mov     r8d, 0FEh; int
0x1800737aa  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800737af  lea     r8, [rbp+pvarSrc]; struct tagPROPVARIANT *
0x1800737b3  lea     rcx, [rbp+pvarDest]; this
0x1800737b7  call    ?GetElement@CMFPropVariant@@QEBAJKPEAUtagPROPVARIANT@@@Z; CMFPropVariant::GetElement(ulong,tagPROPVARIANT *)
0x1800737bc  mov     ebx, eax
0x1800737be  test    eax, eax
0x1800737c0  jns     loc_180073887
0x1800737c6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800737cd  test    rcx, rcx
0x1800737d0  jnz     short loc_180073819
0x1800737d2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800737d9  nop     dword ptr [rax+rax+00h]
0x1800737de  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800737e5  mov     rcx, rax
0x1800737e8  test    rax, rax
0x1800737eb  jz      short loc_18007380B
0x1800737ed  mov     rax, [rax]
0x1800737f0  mov     edx, 7F0h
0x1800737f5  mov     rax, [rax+8]
0x1800737f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800737fe  test    eax, eax
0x180073800  jz      short loc_18007380B
0x180073802  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073809  jmp     short loc_180073819
0x18007380b  lea     rcx, qword_1800DBF70; this
0x180073812  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180073819  cmp     byte ptr [rcx+8], 0
0x18007381d  jz      short loc_180073844
0x18007381f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180073824  cmp     [rax+7CCh], ebx
0x18007382a  jz      short loc_180073844
0x18007382c  mov     r9d, ebx; int
0x18007382f  lea     rdx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x180073836  mov     r8d, 0FEh; int
0x18007383c  mov     rcx, rax; this
0x18007383f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180073844  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007384b  jb      short loc_180073870
0x18007384d  mov     edx, 18h
0x180073852  mov     [rsp+78h+var_58], ebx
0x180073856  mov     rcx, cs:WPP_GLOBAL_Control
0x18007385d  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x180073864  mov     r9, rsi
0x180073867  mov     rcx, [rcx+10h]
0x18007386b  call    WPP_SF_qD
0x180073870  lea     rcx, [rbp+var_48]; this
0x180073874  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180073879  lea     rcx, [rbp+pvarDest]; pvar
0x18007387d  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180073882  jmp     loc_180073BD2
0x180073887  lea     rcx, [rbp+var_48]; this
0x18007388b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180073890  lea     rcx, [rbp+pvarDest]; pvar
0x180073894  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180073899  lea     rbx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x1800738a0  jmp     loc_18007395C
0x1800738a5  mov     r14d, 107h
0x1800738ab  mov     r8d, r14d; int
0x1800738ae  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800738b3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800738ba  mov     edi, 0C00D36B2h
0x1800738bf  mov     ebx, edi
0x1800738c1  test    rcx, rcx
0x1800738c4  jnz     short loc_18007390D
0x1800738c6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800738cd  nop     dword ptr [rax+rax+00h]
0x1800738d2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800738d9  mov     rcx, rax
0x1800738dc  test    rax, rax
0x1800738df  jz      short loc_1800738FF
0x1800738e1  mov     rax, [rax]
0x1800738e4  mov     edx, 7F0h
0x1800738e9  mov     rax, [rax+8]
0x1800738ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800738f2  test    eax, eax
0x1800738f4  jz      short loc_1800738FF
0x1800738f6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800738fd  jmp     short loc_18007390D
0x1800738ff  lea     rcx, qword_1800DBF70; this
0x180073906  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007390d  cmp     byte ptr [rcx+8], 0
0x180073911  jz      short loc_180073935
0x180073913  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180073918  cmp     [rax+7CCh], edi
0x18007391e  jz      short loc_180073935
0x180073920  mov     r9d, edi; int
0x180073923  lea     rdx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x18007392a  mov     r8d, r14d; int
0x18007392d  mov     rcx, rax; this
0x180073930  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180073935  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007393c  jb      loc_180073870
0x180073942  mov     edx, 19h
0x180073947  mov     [rsp+78h+var_58], edi
0x18007394b  jmp     loc_180073856
0x180073950  mov     rdx, r14; pvarSrc
0x180073953  lea     rcx, [rbp+pvarSrc]; pvarDest
0x180073957  call    ?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::Copy(tagPROPVARIANT const *)
0x18007395c  cmp     word ptr [r14], 41h ; 'A'
0x180073961  jnz     loc_180073A19
0x180073967  mov     r14d, 115h
0x18007396d  lea     rcx, [rbp+var_48]; this
0x180073971  mov     r8d, r14d; int
0x180073974  mov     rdx, rbx; char *
0x180073977  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18007397c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073983  mov     edi, 0C00D36B2h
0x180073988  mov     ebx, edi
0x18007398a  test    rcx, rcx
0x18007398d  jnz     short loc_1800739D6
0x18007398f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180073996  nop     dword ptr [rax+rax+00h]
0x18007399b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800739a2  mov     rcx, rax
0x1800739a5  test    rax, rax
0x1800739a8  jz      short loc_1800739C8
0x1800739aa  mov     rax, [rax]
0x1800739ad  mov     edx, 7F0h
0x1800739b2  mov     rax, [rax+8]
0x1800739b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800739bb  test    eax, eax
0x1800739bd  jz      short loc_1800739C8
0x1800739bf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800739c6  jmp     short loc_1800739D6
0x1800739c8  lea     rcx, qword_1800DBF70; this
0x1800739cf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800739d6  cmp     byte ptr [rcx+8], 0
0x1800739da  jz      short loc_1800739FE
0x1800739dc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800739e1  cmp     [rax+7CCh], edi
0x1800739e7  jz      short loc_1800739FE
0x1800739e9  mov     r9d, edi; int
0x1800739ec  lea     rdx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x1800739f3  mov     r8d, r14d; int
0x1800739f6  mov     rcx, rax; this
0x1800739f9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800739fe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180073a05  jb      loc_180073BC9
0x180073a0b  mov     edx, 1Ah
0x180073a10  mov     [rsp+78h+var_58], edi
0x180073a14  jmp     loc_180073BAF
0x180073a19  cmp     [rbp+var_44], edi
0x180073a1c  jnz     loc_180073AE5
0x180073a22  mov     edi, 11Eh
0x180073a27  lea     rcx, [rbp+var_48]; this
0x180073a2b  mov     r8d, edi; int
0x180073a2e  mov     rdx, rbx; char *
0x180073a31  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180073a36  lea     rdx, [rbp+pvarSrc]; pvarSrc
0x180073a3a  mov     rcx, r13; pvarDest
0x180073a3d  call    cs:__imp_PropVariantCopy
0x180073a44  nop     dword ptr [rax+rax+00h]
0x180073a49  mov     ebx, eax
0x180073a4b  test    eax, eax
0x180073a4d  jns     loc_180073BC9
0x180073a53  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073a5a  test    rcx, rcx
0x180073a5d  jnz     short loc_180073AA6
0x180073a5f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180073a66  nop     dword ptr [rax+rax+00h]
0x180073a6b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180073a72  mov     rcx, rax
0x180073a75  test    rax, rax
0x180073a78  jz      short loc_180073A98
0x180073a7a  mov     rax, [rax]
0x180073a7d  mov     edx, 7F0h
0x180073a82  mov     rax, [rax+8]
0x180073a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073a8b  test    eax, eax
0x180073a8d  jz      short loc_180073A98
0x180073a8f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073a96  jmp     short loc_180073AA6
0x180073a98  lea     rcx, qword_1800DBF70; this
0x180073a9f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180073aa6  cmp     byte ptr [rcx+8], 0
0x180073aaa  jz      short loc_180073ACE
0x180073aac  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180073ab1  cmp     [rax+7CCh], ebx
0x180073ab7  jz      short loc_180073ACE
0x180073ab9  mov     r9d, ebx; int
0x180073abc  lea     rdx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x180073ac3  mov     r8d, edi; int
0x180073ac6  mov     rcx, rax; this
0x180073ac9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180073ace  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180073ad5  jb      loc_180073BC9
0x180073adb  mov     edx, 1Bh
0x180073ae0  jmp     loc_180073BAB
0x180073ae5  test    r12d, r12d
0x180073ae8  jz      short loc_180073AF3
0x180073aea  test    r15d, r15d
0x180073aed  jz      short loc_180073AF3
0x180073aef  bts     edi, 0Ch
0x180073af3  mov     r14d, 129h
0x180073af9  lea     rcx, [rbp+var_48]; this
0x180073afd  mov     r8d, r14d; int
0x180073b00  mov     rdx, rbx; char *
0x180073b03  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180073b08  movzx   r9d, di; unsigned __int16
0x180073b0c  lea     r8, [rbp+pvarSrc]; struct tagPROPVARIANT *
0x180073b10  mov     rdx, r13; struct tagPROPVARIANT *
0x180073b13  call    ?WMPropVariantChangeType@CWMProperty@@IEAAJPEAUtagPROPVARIANT@@AEBU2@G@Z; CWMProperty::WMPropVariantChangeType(tagPROPVARIANT *,tagPROPVARIANT const &,ushort)
0x180073b18  mov     ebx, eax
0x180073b1a  test    eax, eax
0x180073b1c  jns     loc_180073BC9
0x180073b22  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073b29  test    rcx, rcx
0x180073b2c  jnz     short loc_180073B75
0x180073b2e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180073b35  nop     dword ptr [rax+rax+00h]
0x180073b3a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180073b41  mov     rcx, rax
0x180073b44  test    rax, rax
0x180073b47  jz      short loc_180073B67
0x180073b49  mov     rax, [rax]
0x180073b4c  mov     edx, 7F0h
0x180073b51  mov     rax, [rax+8]
0x180073b55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073b5a  test    eax, eax
0x180073b5c  jz      short loc_180073B67
0x180073b5e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073b65  jmp     short loc_180073B75
0x180073b67  lea     rcx, qword_1800DBF70; this
0x180073b6e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180073b75  cmp     byte ptr [rcx+8], 0
0x180073b79  jz      short loc_180073B9D
0x180073b7b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180073b80  cmp     [rax+7CCh], ebx
0x180073b86  jz      short loc_180073B9D
0x180073b88  mov     r9d, ebx; int
0x180073b8b  lea     rdx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x180073b92  mov     r8d, r14d; int
0x180073b95  mov     rcx, rax; this
0x180073b98  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180073b9d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180073ba4  jb      short loc_180073BC9
0x180073ba6  mov     edx, 1Ch
0x180073bab  mov     [rsp+78h+var_58], ebx
0x180073baf  mov     rcx, cs:WPP_GLOBAL_Control
0x180073bb6  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x180073bbd  mov     r9, rsi
0x180073bc0  mov     rcx, [rcx+10h]
0x180073bc4  call    WPP_SF_qD
0x180073bc9  lea     rcx, [rbp+var_48]; this
0x180073bcd  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180073bd2  lea     rcx, [rbp+pvarSrc]; pvar
0x180073bd6  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180073bdb  mov     eax, ebx
0x180073bdd  add     rsp, 78h
0x180073be1  pop     r15
0x180073be3  pop     r14
0x180073be5  pop     r13
  ... truncated ...
```
