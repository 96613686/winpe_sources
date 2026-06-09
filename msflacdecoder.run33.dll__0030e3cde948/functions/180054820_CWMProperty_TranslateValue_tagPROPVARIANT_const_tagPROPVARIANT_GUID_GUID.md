# CWMProperty::TranslateValue(tagPROPVARIANT const &,tagPROPVARIANT *,_GUID,_GUID)

- ea: `0x180054820`
- end: `0x180054ce8`
- name: `?TranslateValue@CWMProperty@@IEAAJAEBUtagPROPVARIANT@@PEAU2@U_GUID@@2@Z`
- size: `1224`
- prototype: `int(CWMProperty *__hidden this, const struct tagPROPVARIANT *, struct tagPROPVARIANT *, struct _GUID *__struct_ptr, struct _GUID *__struct_ptr)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800526f0`
- `0x180053c30`

## callees

- `0x180020398`
- `0x180020484`
- `0x18002fa8c`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180034a04`
- `0x18003733c`
- `0x180037f6c`
- `0x180038298`
- `0x180039e60`
- `0x180050a48`
- `0x180054820`
- `0x180054cf0`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180054b49`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180054b49`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800548f0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800549de`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054aa1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054b65`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054c2e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800548f0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800549de`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054aa1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054b65`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054c2e`

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
  __int64 v13; // rdx
  HRESULT Element; // ebx
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v26; // rdx
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  CWMProperty *v31; // rcx
  __int64 v32; // rdx
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  _BYTE v37[4]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v38; // [rsp+34h] [rbp-44h]
  PROPVARIANT pvarSrc; // [rsp+38h] [rbp-40h] BYREF
  PROPVARIANT pvar; // [rsp+50h] [rbp-28h] BYREF

  vt = a2->vt;
  v38 = a2->vt & 0xEFFF;
  v9 = vt & 0x1000;
  memset(&pvarSrc, 0, sizeof(pvarSrc));
  v10 = MFGetAttributeUINT32(this, a4, v38);
  v11 = MFGetAttributeUINT32(this, a5, v9);
  v12 = v11;
  if ( !v9 || v11 )
  {
    CMFPropVariant::Copy(&pvarSrc, a2);
LABEL_28:
    if ( a2->vt == 65 )
    {
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v37, "CWMProperty::TranslateValue", 277);
      v23 = (__int64 *)CallStackTracing::s_wpInstance;
      Element = -1072875854;
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
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875854 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CWMProperty::TranslateValue", 277, -1072875854);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        WPP_SF_qd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
          this,
          -1072875854);
    }
    else
    {
      if ( v38 == v10 )
      {
        CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v37, "CWMProperty::TranslateValue", 286);
        Element = PropVariantCopy(a3, &pvarSrc);
        if ( Element >= 0 )
          goto LABEL_66;
        v27 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
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
        if ( *((_BYTE *)v27 + 8) )
        {
          v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
          if ( *((_DWORD *)v29 + 499) != Element )
            CallStackContext::TraceFailure(v29, "CWMProperty::TranslateValue", 286, Element);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_66;
        v30 = 27;
      }
      else
      {
        if ( v9 && v12 )
          LOWORD(v10) = v10 | 0x1000;
        CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v37, "CWMProperty::TranslateValue", 297);
        Element = CWMProperty::WMPropVariantChangeType(v31, a3, &pvarSrc, v10);
        if ( Element >= 0 )
          goto LABEL_66;
        v33 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32);
          CallStackTracing::s_wpInstance = v34;
          if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
          {
            v33 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v33 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v33 + 8) )
        {
          v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
          if ( *((_DWORD *)v35 + 499) != Element )
            CallStackContext::TraceFailure(v35, "CWMProperty::TranslateValue", 297, Element);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_66;
        v30 = 28;
      }
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v30,
        &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
        this,
        Element);
    }
LABEL_66:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v37);
    goto LABEL_67;
  }
  CMFPropVariant::CMFPropVariant((CMFPropVariant *)&pvar, a2);
  if ( !CMFPropVariant::GetElementCount((CMFPropVariant *)&pvar) )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v37, "CWMProperty::TranslateValue", 263);
    v19 = (__int64 *)CallStackTracing::s_wpInstance;
    Element = -1072875854;
    if ( !CallStackTracing::s_wpInstance )
    {
      v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
      CallStackTracing::s_wpInstance = v20;
      if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
      {
        v19 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v19 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v19 + 8) )
    {
      v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
      if ( *((_DWORD *)v21 + 499) != -1072875854 )
        CallStackContext::TraceFailure(v21, "CWMProperty::TranslateValue", 263, -1072875854);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
        this,
        -1072875854);
    goto LABEL_15;
  }
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v37, "CWMProperty::TranslateValue", 254);
  Element = CMFPropVariant::GetElement((CMFPropVariant *)&pvar, 0, &pvarSrc);
  if ( Element >= 0 )
  {
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v37);
    CMFPropVariant::Clear(&pvar);
    goto LABEL_28;
  }
  v15 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
    CallStackTracing::s_wpInstance = v16;
    if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
    {
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v15 = &qword_18006EB20;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
    }
  }
  if ( *((_BYTE *)v15 + 8) )
  {
    v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
    if ( *((_DWORD *)v17 + 499) != Element )
      CallStackContext::TraceFailure(v17, "CWMProperty::TranslateValue", 254, Element);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, Element);
LABEL_15:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v37);
  CMFPropVariant::Clear(&pvar);
LABEL_67:
  CMFPropVariant::Clear(&pvarSrc);
  return (unsigned int)Element;
}

```

## disassembly

```asm
0x180054820  push    rbp
0x180054822  push    rbx
0x180054823  push    rsi
0x180054824  push    rdi
0x180054825  push    r12
0x180054827  push    r13
0x180054829  push    r14
0x18005482b  push    r15
0x18005482d  mov     rbp, rsp
0x180054830  sub     rsp, 78h
0x180054834  movzx   r12d, word ptr [rdx]
0x180054838  mov     rsi, rcx
0x18005483b  mov     rbx, [rbp+arg_20]
0x18005483f  mov     eax, r12d
0x180054842  xor     ecx, ecx
0x180054844  btr     eax, 0Ch
0x180054848  mov     r13, r8
0x18005484b  mov     qword ptr [rbp+pvarSrc+10h], rcx
0x18005484f  mov     r14, rdx
0x180054852  mov     [rbp+var_44], eax
0x180054855  xorps   xmm0, xmm0
0x180054858  mov     r8d, eax
0x18005485b  mov     rdx, r9
0x18005485e  mov     rcx, rsi
0x180054861  and     r12d, 1000h
0x180054868  movups  xmmword ptr [rbp+pvarSrc], xmm0
0x18005486c  call    MFGetAttributeUINT32
0x180054871  mov     r8d, r12d
0x180054874  mov     rdx, rbx
0x180054877  mov     rcx, rsi
0x18005487a  mov     edi, eax
0x18005487c  call    MFGetAttributeUINT32
0x180054881  lea     rbx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x180054888  mov     r15d, eax
0x18005488b  test    r12d, r12d
0x18005488e  jz      loc_180054A62
0x180054894  test    eax, eax
0x180054896  jnz     loc_180054A62
0x18005489c  mov     rdx, r14; struct tagPROPVARIANT *
0x18005489f  lea     rcx, [rbp+pvar]; this
0x1800548a3  call    ??0CMFPropVariant@@QEAA@AEBUtagPROPVARIANT@@@Z; CMFPropVariant::CMFPropVariant(tagPROPVARIANT const &)
0x1800548a8  lea     rcx, [rbp+pvar]; this
0x1800548ac  call    ?GetElementCount@CMFPropVariant@@QEBAKXZ; CMFPropVariant::GetElementCount(void)
0x1800548b1  lea     rcx, [rbp+var_48]; this
0x1800548b5  mov     rdx, rbx; char *
0x1800548b8  test    eax, eax
0x1800548ba  jz      loc_1800549BD
0x1800548c0  mov     r8d, 0FEh; int
0x1800548c6  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800548cb  lea     r8, [rbp+pvarSrc]; struct tagPROPVARIANT *
0x1800548cf  xor     edx, edx; unsigned int
0x1800548d1  lea     rcx, [rbp+pvar]; this
0x1800548d5  call    ?GetElement@CMFPropVariant@@QEBAJKPEAUtagPROPVARIANT@@@Z; CMFPropVariant::GetElement(ulong,tagPROPVARIANT *)
0x1800548da  mov     ebx, eax
0x1800548dc  test    eax, eax
0x1800548de  jns     loc_18005499F
0x1800548e4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800548eb  test    rcx, rcx
0x1800548ee  jnz     short loc_180054931
0x1800548f0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800548f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800548fd  mov     rcx, rax
0x180054900  test    rax, rax
0x180054903  jz      short loc_180054923
0x180054905  mov     rax, [rax]
0x180054908  mov     edx, 7F0h
0x18005490d  mov     rax, [rax+8]
0x180054911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054916  test    eax, eax
0x180054918  jz      short loc_180054923
0x18005491a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054921  jmp     short loc_180054931
0x180054923  lea     rcx, qword_18006EB20; this
0x18005492a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180054931  cmp     byte ptr [rcx+8], 0
0x180054935  jz      short loc_18005495C
0x180054937  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005493c  cmp     [rax+7CCh], ebx
0x180054942  jz      short loc_18005495C
0x180054944  mov     r9d, ebx; int
0x180054947  lea     rdx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x18005494e  mov     r8d, 0FEh; int
0x180054954  mov     rcx, rax; this
0x180054957  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005495c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180054961  cmp     al, 1
0x180054963  jb      short loc_180054988
0x180054965  mov     edx, 18h
0x18005496a  mov     [rsp+78h+var_58], ebx
0x18005496e  mov     rcx, cs:WPP_GLOBAL_Control
0x180054975  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x18005497c  mov     r9, rsi
0x18005497f  mov     rcx, [rcx+10h]
0x180054983  call    WPP_SF_qd
0x180054988  lea     rcx, [rbp+var_48]; this
0x18005498c  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180054991  lea     rcx, [rbp+pvar]; pvar
0x180054995  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x18005499a  jmp     loc_180054CCC
0x18005499f  lea     rcx, [rbp+var_48]; this
0x1800549a3  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800549a8  lea     rcx, [rbp+pvar]; pvar
0x1800549ac  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x1800549b1  lea     rbx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x1800549b8  jmp     loc_180054A6E
0x1800549bd  mov     r14d, 107h
0x1800549c3  mov     r8d, r14d; int
0x1800549c6  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800549cb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800549d2  mov     edi, 0C00D36B2h
0x1800549d7  mov     ebx, edi
0x1800549d9  test    rcx, rcx
0x1800549dc  jnz     short loc_180054A1F
0x1800549de  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800549e4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800549eb  mov     rcx, rax
0x1800549ee  test    rax, rax
0x1800549f1  jz      short loc_180054A11
0x1800549f3  mov     rax, [rax]
0x1800549f6  mov     edx, 7F0h
0x1800549fb  mov     rax, [rax+8]
0x1800549ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054a04  test    eax, eax
0x180054a06  jz      short loc_180054A11
0x180054a08  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054a0f  jmp     short loc_180054A1F
0x180054a11  lea     rcx, qword_18006EB20; this
0x180054a18  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180054a1f  cmp     byte ptr [rcx+8], 0
0x180054a23  jz      short loc_180054A47
0x180054a25  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180054a2a  cmp     [rax+7CCh], edi
0x180054a30  jz      short loc_180054A47
0x180054a32  mov     r9d, edi; int
0x180054a35  lea     rdx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x180054a3c  mov     r8d, r14d; int
0x180054a3f  mov     rcx, rax; this
0x180054a42  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180054a47  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180054a4c  cmp     al, 1
0x180054a4e  jb      loc_180054988
0x180054a54  mov     edx, 19h
0x180054a59  mov     [rsp+78h+var_58], edi
0x180054a5d  jmp     loc_18005496E
0x180054a62  mov     rdx, r14; pvarSrc
0x180054a65  lea     rcx, [rbp+pvarSrc]; pvarDest
0x180054a69  call    ?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::Copy(tagPROPVARIANT const *)
0x180054a6e  cmp     word ptr [r14], 41h ; 'A'
0x180054a73  jnz     loc_180054B25
0x180054a79  mov     r14d, 115h
0x180054a7f  lea     rcx, [rbp+var_48]; this
0x180054a83  mov     r8d, r14d; int
0x180054a86  mov     rdx, rbx; char *
0x180054a89  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180054a8e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054a95  mov     edi, 0C00D36B2h
0x180054a9a  mov     ebx, edi
0x180054a9c  test    rcx, rcx
0x180054a9f  jnz     short loc_180054AE2
0x180054aa1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180054aa7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180054aae  mov     rcx, rax
0x180054ab1  test    rax, rax
0x180054ab4  jz      short loc_180054AD4
0x180054ab6  mov     rax, [rax]
0x180054ab9  mov     edx, 7F0h
0x180054abe  mov     rax, [rax+8]
0x180054ac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054ac7  test    eax, eax
0x180054ac9  jz      short loc_180054AD4
0x180054acb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054ad2  jmp     short loc_180054AE2
0x180054ad4  lea     rcx, qword_18006EB20; this
0x180054adb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180054ae2  cmp     byte ptr [rcx+8], 0
0x180054ae6  jz      short loc_180054B0A
0x180054ae8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180054aed  cmp     [rax+7CCh], edi
0x180054af3  jz      short loc_180054B0A
0x180054af5  mov     r9d, edi; int
0x180054af8  lea     rdx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x180054aff  mov     r8d, r14d; int
0x180054b02  mov     rcx, rax; this
0x180054b05  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180054b0a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180054b0f  cmp     al, 1
0x180054b11  jb      loc_180054CC3
0x180054b17  mov     edx, 1Ah
0x180054b1c  mov     [rsp+78h+var_58], edi
0x180054b20  jmp     loc_180054CA9
0x180054b25  cmp     [rbp+var_44], edi
0x180054b28  jnz     loc_180054BE5
0x180054b2e  mov     edi, 11Eh
0x180054b33  lea     rcx, [rbp+var_48]; this
0x180054b37  mov     r8d, edi; int
0x180054b3a  mov     rdx, rbx; char *
0x180054b3d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180054b42  lea     rdx, [rbp+pvarSrc]; pvarSrc
0x180054b46  mov     rcx, r13; pvarDest
0x180054b49  call    cs:__imp_PropVariantCopy
0x180054b4f  mov     ebx, eax
0x180054b51  test    eax, eax
0x180054b53  jns     loc_180054CC3
0x180054b59  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054b60  test    rcx, rcx
0x180054b63  jnz     short loc_180054BA6
0x180054b65  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180054b6b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180054b72  mov     rcx, rax
0x180054b75  test    rax, rax
0x180054b78  jz      short loc_180054B98
0x180054b7a  mov     rax, [rax]
0x180054b7d  mov     edx, 7F0h
0x180054b82  mov     rax, [rax+8]
0x180054b86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054b8b  test    eax, eax
0x180054b8d  jz      short loc_180054B98
0x180054b8f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054b96  jmp     short loc_180054BA6
0x180054b98  lea     rcx, qword_18006EB20; this
0x180054b9f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180054ba6  cmp     byte ptr [rcx+8], 0
0x180054baa  jz      short loc_180054BCE
0x180054bac  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180054bb1  cmp     [rax+7CCh], ebx
0x180054bb7  jz      short loc_180054BCE
0x180054bb9  mov     r9d, ebx; int
0x180054bbc  lea     rdx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x180054bc3  mov     r8d, edi; int
0x180054bc6  mov     rcx, rax; this
0x180054bc9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180054bce  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180054bd3  cmp     al, 1
0x180054bd5  jb      loc_180054CC3
0x180054bdb  mov     edx, 1Bh
0x180054be0  jmp     loc_180054CA5
0x180054be5  test    r12d, r12d
0x180054be8  jz      short loc_180054BF3
0x180054bea  test    r15d, r15d
0x180054bed  jz      short loc_180054BF3
0x180054bef  bts     edi, 0Ch
0x180054bf3  mov     r14d, 129h
0x180054bf9  lea     rcx, [rbp+var_48]; this
0x180054bfd  mov     r8d, r14d; int
0x180054c00  mov     rdx, rbx; char *
0x180054c03  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180054c08  movzx   r9d, di; unsigned __int16
0x180054c0c  lea     r8, [rbp+pvarSrc]; struct tagPROPVARIANT *
0x180054c10  mov     rdx, r13; struct tagPROPVARIANT *
0x180054c13  call    ?WMPropVariantChangeType@CWMProperty@@IEAAJPEAUtagPROPVARIANT@@AEBU2@G@Z; CWMProperty::WMPropVariantChangeType(tagPROPVARIANT *,tagPROPVARIANT const &,ushort)
0x180054c18  mov     ebx, eax
0x180054c1a  test    eax, eax
0x180054c1c  jns     loc_180054CC3
0x180054c22  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054c29  test    rcx, rcx
0x180054c2c  jnz     short loc_180054C6F
0x180054c2e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180054c34  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180054c3b  mov     rcx, rax
0x180054c3e  test    rax, rax
0x180054c41  jz      short loc_180054C61
0x180054c43  mov     rax, [rax]
0x180054c46  mov     edx, 7F0h
0x180054c4b  mov     rax, [rax+8]
0x180054c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054c54  test    eax, eax
0x180054c56  jz      short loc_180054C61
0x180054c58  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054c5f  jmp     short loc_180054C6F
0x180054c61  lea     rcx, qword_18006EB20; this
0x180054c68  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180054c6f  cmp     byte ptr [rcx+8], 0
0x180054c73  jz      short loc_180054C97
0x180054c75  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180054c7a  cmp     [rax+7CCh], ebx
0x180054c80  jz      short loc_180054C97
0x180054c82  mov     r9d, ebx; int
0x180054c85  lea     rdx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x180054c8c  mov     r8d, r14d; int
0x180054c8f  mov     rcx, rax; this
0x180054c92  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180054c97  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180054c9c  cmp     al, 1
0x180054c9e  jb      short loc_180054CC3
0x180054ca0  mov     edx, 1Ch
0x180054ca5  mov     [rsp+78h+var_58], ebx
0x180054ca9  mov     rcx, cs:WPP_GLOBAL_Control
0x180054cb0  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x180054cb7  mov     r9, rsi
0x180054cba  mov     rcx, [rcx+10h]
0x180054cbe  call    WPP_SF_qd
0x180054cc3  lea     rcx, [rbp+var_48]; this
0x180054cc7  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180054ccc  lea     rcx, [rbp+pvarSrc]; pvar
0x180054cd0  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180054cd5  mov     eax, ebx
0x180054cd7  add     rsp, 78h
0x180054cdb  pop     r15
0x180054cdd  pop     r14
0x180054cdf  pop     r13
  ... truncated ...
```
