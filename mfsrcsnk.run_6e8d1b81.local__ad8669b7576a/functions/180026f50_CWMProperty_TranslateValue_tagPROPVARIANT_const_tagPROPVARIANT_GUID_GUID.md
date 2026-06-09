# CWMProperty::TranslateValue(tagPROPVARIANT const &,tagPROPVARIANT *,_GUID,_GUID)

- ea: `0x180026f50`
- end: `0x1800275e7`
- name: `?TranslateValue@CWMProperty@@IEAAJAEBUtagPROPVARIANT@@PEAU2@U_GUID@@2@Z`
- size: `1687`
- prototype: `int(CWMProperty *__hidden this, const struct tagPROPVARIANT *, struct tagPROPVARIANT *, struct _GUID *__struct_ptr, struct _GUID *__struct_ptr)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180027ce0`
- `0x180053790`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180025548`
- `0x180026f50`
- `0x1800275f0`
- `0x18006036c`
- `0x180062b30`
- `0x180071a44`
- `0x180072190`
- `0x180073b14`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027102`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800271fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027238`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027297`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800272d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027102`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800271fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027238`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027297`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800272d3`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180027058`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180027534`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180027058`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180027534`
- `PROPSYS!PropVariantChangeType` at `0x1800270da`
- `PROPSYS!PropVariantChangeType` at `0x1800270da`

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
  int v6; // ebx
  __int64 v8; // rax
  unsigned int v10; // ebx
  int v12; // r12d
  int (__fastcall *v13)(CWMProperty *, struct _GUID *, unsigned int *); // rax
  unsigned int v14; // edi
  __int64 v15; // rax
  int v16; // r15d
  CallStackTracing *v17; // rcx
  struct CallStackContext *v18; // rax
  unsigned int v19; // ecx
  __int64 v20; // rdx
  __int64 v21; // rdx
  HRESULT Element; // ebx
  __int64 v24; // rdx
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rdx
  wchar_t *v29; // rcx
  CallStackTracing *v30; // rax
  wchar_t *v31; // rcx
  CallStackTracing *v32; // rax
  __int64 v33; // rdx
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct CallStackContext *v40; // rax
  struct CallStackContext *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // rdx
  _BYTE v44[4]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v45; // [rsp+34h] [rbp-44h] BYREF
  PROPVARIANT pvarDest; // [rsp+38h] [rbp-40h] BYREF
  unsigned int v47; // [rsp+50h] [rbp-28h]
  PROPVARIANT pvarSrc; // [rsp+58h] [rbp-20h] BYREF

  vt = a2->vt;
  v6 = a2->vt;
  v45 = 0;
  v8 = *(_QWORD *)this;
  v10 = v6 & 0xFFFFEFFF;
  v47 = v10;
  v12 = vt & 0x1000;
  v13 = *(int (__fastcall **)(CWMProperty *, struct _GUID *, unsigned int *))(v8 + 56);
  memset(&pvarSrc, 0, sizeof(pvarSrc));
  v14 = v10;
  if ( v13(this, a4, &v45) >= 0 )
    v14 = v45;
  v15 = *(_QWORD *)this;
  v45 = 0;
  v16 = v12;
  if ( (*(int (__fastcall **)(CWMProperty *, struct _GUID *, unsigned int *))(v15 + 56))(this, a5, &v45) >= 0 )
    v16 = v45;
  if ( !v12 || v16 )
  {
    CMFPropVariant::Copy(&pvarSrc, a2);
  }
  else
  {
    memset(&pvarDest, 0, sizeof(pvarDest));
    CMFPropVariant::Clear(&pvarDest);
    CMFPropVariant::Copy(&pvarDest, a2);
    if ( !pvarDest.vt || !pvarDest.lVal && (pvarDest.vt & 0x1000) != 0 )
    {
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v44, "CWMProperty::TranslateValue", 263);
      v29 = (wchar_t *)CallStackTracing::s_wpInstance;
      Element = -1072875854;
      if ( !CallStackTracing::s_wpInstance )
      {
        v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28);
        CallStackTracing::s_wpInstance = v30;
        if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
        {
          v29 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v29 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v29 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875854 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CWMProperty::TranslateValue", 263, -1072875854);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
          this,
          -1072875854);
LABEL_58:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v44);
      CMFPropVariant::Clear(&pvarDest);
      goto LABEL_17;
    }
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v44, "CWMProperty::TranslateValue", 254);
    Element = CMFPropVariant::GetElement((CMFPropVariant *)&pvarDest, 0, &pvarSrc);
    if ( Element < 0 )
    {
      v31 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
        CallStackTracing::s_wpInstance = v32;
        if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
        {
          v31 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v31 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v31 + 8) )
      {
        v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
        if ( *((_DWORD *)v38 + 499) != Element )
          CallStackContext::TraceFailure(v38, "CWMProperty::TranslateValue", 254, Element);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
          this,
          Element);
      goto LABEL_58;
    }
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v44);
    CMFPropVariant::Clear(&pvarDest);
    v10 = v47;
  }
  if ( a2->vt == 65 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v44, "CWMProperty::TranslateValue", 277);
    v34 = (wchar_t *)CallStackTracing::s_wpInstance;
    Element = -1072875854;
    if ( !CallStackTracing::s_wpInstance )
    {
      v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
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
      v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
      if ( *((_DWORD *)v40 + 499) != -1072875854 )
        CallStackContext::TraceFailure(v40, "CWMProperty::TranslateValue", 277, -1072875854);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
        this,
        -1072875854);
    goto LABEL_16;
  }
  if ( v10 == v14 )
  {
    v17 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v17 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v17 + 8) )
    {
      v18 = CallStackTracing::GetThreadRelativeContext(v17);
      v19 = *((_DWORD *)v18 + 497);
      if ( v19 < *((_DWORD *)v18 + 498) )
      {
        v20 = 2LL * v19;
        *((_QWORD *)v18 + v20) = "CWMProperty::TranslateValue";
        *((_DWORD *)v18 + 2 * v20 + 2) = 286;
      }
      ++*((_DWORD *)v18 + 497);
    }
    Element = PropVariantCopy(a3, &pvarSrc);
    if ( Element >= 0 )
      goto LABEL_16;
    v36 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
      CallStackTracing::s_wpInstance = v37;
      if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
      {
        v36 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v36 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v36 + 8) )
    {
      v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
      if ( *((_DWORD *)v41 + 499) != Element )
        CallStackContext::TraceFailure(v41, "CWMProperty::TranslateValue", 286, Element);
    }
    if ( !g_wppLevels )
      goto LABEL_16;
    v43 = 27;
    goto LABEL_87;
  }
  if ( v12 && v16 )
    LOWORD(v14) = v14 | 0x1000;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v44, "CWMProperty::TranslateValue", 297);
  Element = PropVariantChangeType(a3, &pvarSrc, 0, v14);
  if ( Element >= 0 )
    goto LABEL_85;
  CMFPropVariant::CMFPropVariant((CMFPropVariant *)&pvarDest, &pvarSrc);
  Element = CMFPropVariantConvert::Convert((struct CMFPropVariant *)&pvarDest, v14);
  if ( Element >= 0 )
    Element = PropVariantCopy(a3, &pvarDest);
  CMFPropVariant::Clear(&pvarDest);
  if ( Element >= 0 )
    goto LABEL_16;
  if ( pvarSrc.vt != 21 || (_WORD)v14 != 64 )
  {
LABEL_85:
    if ( Element >= 0 )
      goto LABEL_16;
    v25 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
      CallStackTracing::s_wpInstance = v26;
      if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
      {
        v25 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v25 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v25 + 8) )
    {
      v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
      if ( *((_DWORD *)v42 + 499) != Element )
        CallStackContext::TraceFailure(v42, "CWMProperty::TranslateValue", 297, Element);
    }
    if ( !g_wppLevels )
      goto LABEL_16;
    v43 = 28;
LABEL_87:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v43, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, Element);
    goto LABEL_16;
  }
  *(_OWORD *)&a3->vt = 0;
  a3->bstrblobVal.pData = 0;
  Element = 0;
  a3->hVal.QuadPart = pvarSrc.hVal.QuadPart;
  a3->vt = 64;
LABEL_16:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v44);
LABEL_17:
  CMFPropVariant::Clear(&pvarSrc);
  return (unsigned int)Element;
}

```

## disassembly

```asm
0x180026f50  push    rbp
0x180026f52  push    rbx
0x180026f53  push    rsi
0x180026f54  push    rdi
0x180026f55  push    r12
0x180026f57  push    r13
0x180026f59  push    r14
0x180026f5b  push    r15
0x180026f5d  mov     rbp, rsp
0x180026f60  sub     rsp, 78h
0x180026f64  movzx   r12d, word ptr [rdx]
0x180026f68  xor     eax, eax
0x180026f6a  mov     r15, [rbp+arg_20]
0x180026f6e  mov     ebx, r12d
0x180026f71  mov     qword ptr [rbp+pvarSrc+10h], rax
0x180026f75  mov     rsi, r8
0x180026f78  mov     [rbp+var_44], eax
0x180026f7b  lea     r8, [rbp+var_44]
0x180026f7f  mov     rax, [rcx]
0x180026f82  mov     r13, rdx
0x180026f85  xorps   xmm0, xmm0
0x180026f88  btr     ebx, 0Ch
0x180026f8c  mov     rdx, r9
0x180026f8f  mov     [rbp+var_28], ebx
0x180026f92  mov     r14, rcx
0x180026f95  and     r12d, 1000h
0x180026f9c  mov     rax, [rax+38h]
0x180026fa0  movups  xmmword ptr [rbp+pvarSrc], xmm0
0x180026fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fa9  mov     edi, ebx
0x180026fab  test    eax, eax
0x180026fad  js      short loc_180026FB2
0x180026faf  mov     edi, [rbp+var_44]
0x180026fb2  mov     rax, [r14]
0x180026fb5  lea     r8, [rbp+var_44]
0x180026fb9  mov     rdx, r15
0x180026fbc  mov     [rbp+var_44], 0
0x180026fc3  mov     rcx, r14
0x180026fc6  mov     rax, [rax+38h]
0x180026fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fcf  mov     r15d, r12d
0x180026fd2  test    eax, eax
0x180026fd4  jns     loc_18002708D
0x180026fda  test    r12d, r12d
0x180026fdd  jnz     loc_18002713A
0x180026fe3  mov     rdx, r13; pvarSrc
0x180026fe6  lea     rcx, [rbp+pvarSrc]; pvarDest
0x180026fea  call    ?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::Copy(tagPROPVARIANT const *)
0x180026fef  cmp     word ptr [r13+0], 41h ; 'A'
0x180026ff5  jz      loc_180027264
0x180026ffb  cmp     ebx, edi
0x180026ffd  jnz     loc_1800270A7
0x180027003  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002700a  test    rcx, rcx
0x18002700d  jz      loc_180027096
0x180027013  cmp     byte ptr [rcx+8], 0
0x180027017  mov     r15d, 11Eh
0x18002701d  jz      loc_18002712E
0x180027023  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180027028  lea     rdi, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x18002702f  mov     ecx, [rax+7C4h]
0x180027035  cmp     ecx, [rax+7C8h]
0x18002703b  jnb     short loc_18002704B
0x18002703d  mov     edx, ecx
0x18002703f  add     rdx, rdx
0x180027042  mov     [rax+rdx*8], rdi
0x180027046  mov     [rax+rdx*8+8], r15d
0x18002704b  inc     dword ptr [rax+7C4h]
0x180027051  lea     rdx, [rbp+pvarSrc]; pvarSrc
0x180027055  mov     rcx, rsi; pvarDest
0x180027058  call    cs:__imp_PropVariantCopy
0x18002705e  mov     ebx, eax
0x180027060  test    eax, eax
0x180027062  js      loc_1800272C3
0x180027068  lea     rcx, [rbp+var_48]; this
0x18002706c  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180027071  lea     rcx, [rbp+pvarSrc]; this
0x180027075  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x18002707a  mov     eax, ebx
0x18002707c  add     rsp, 78h
0x180027080  pop     r15
0x180027082  pop     r14
0x180027084  pop     r13
0x180027086  pop     r12
0x180027088  pop     rdi
0x180027089  pop     rsi
0x18002708a  pop     rbx
0x18002708b  pop     rbp
0x18002708c  retn
0x18002708d  mov     r15d, [rbp+var_44]
0x180027091  jmp     loc_180026FDA
0x180027096  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002709b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800270a2  jmp     loc_180027013
0x1800270a7  test    r12d, r12d
0x1800270aa  jnz     loc_1800274FC
0x1800270b0  mov     r12d, 129h
0x1800270b6  lea     r15, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x1800270bd  mov     r8d, r12d; int
0x1800270c0  lea     rcx, [rbp+var_48]; this
0x1800270c4  mov     rdx, r15; char *
0x1800270c7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800270cc  movzx   r9d, di; vt
0x1800270d0  lea     rdx, [rbp+pvarSrc]; propvarSrc
0x1800270d4  xor     r8d, r8d; flags
0x1800270d7  mov     rcx, rsi; ppropvarDest
0x1800270da  call    cs:__imp_PropVariantChangeType
0x1800270e0  mov     ebx, eax
0x1800270e2  test    eax, eax
0x1800270e4  js      loc_18002750E
0x1800270ea  test    ebx, ebx
0x1800270ec  jns     loc_180027068
0x1800270f2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800270f9  test    rcx, rcx
0x1800270fc  jnz     loc_1800275A8
0x180027102  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180027108  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002710f  mov     rcx, rax
0x180027112  test    rax, rax
0x180027115  jnz     loc_180027588
0x18002711b  lea     rcx, qword_1801B07E0
0x180027122  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180027129  jmp     loc_1800275A8
0x18002712e  lea     rdi, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x180027135  jmp     loc_180027051
0x18002713a  test    r15d, r15d
0x18002713d  jnz     loc_180026FE3
0x180027143  xorps   xmm0, xmm0
0x180027146  lea     rcx, [rbp+pvarDest]; this
0x18002714a  xor     eax, eax
0x18002714c  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180027150  mov     qword ptr [rbp+pvarDest+10h], rax
0x180027154  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180027159  mov     rdx, r13; pvarSrc
0x18002715c  lea     rcx, [rbp+pvarDest]; pvarDest
0x180027160  call    ?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::Copy(tagPROPVARIANT const *)
0x180027165  movzx   ecx, word ptr [rbp+pvarDest]
0x180027169  xor     eax, eax
0x18002716b  cmp     ax, cx
0x18002716e  jz      short loc_1800271C9
0x180027170  mov     eax, 1000h
0x180027175  and     cx, ax
0x180027178  xor     eax, eax
0x18002717a  cmp     dword ptr [rbp+pvarDest+8], eax
0x18002717d  jbe     short loc_1800271C4
0x18002717f  mov     r8d, 0FEh; int
0x180027185  lea     rdx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x18002718c  lea     rcx, [rbp+var_48]; this
0x180027190  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180027195  lea     r8, [rbp+pvarSrc]; pvarDest
0x180027199  xor     edx, edx; unsigned int
0x18002719b  lea     rcx, [rbp+pvarDest]; this
0x18002719f  call    ?GetElement@CMFPropVariant@@QEBAJKPEAUtagPROPVARIANT@@@Z; CMFPropVariant::GetElement(ulong,tagPROPVARIANT *)
0x1800271a4  mov     ebx, eax
0x1800271a6  test    eax, eax
0x1800271a8  js      short loc_180027228
0x1800271aa  lea     rcx, [rbp+var_48]; this
0x1800271ae  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800271b3  lea     rcx, [rbp+pvarDest]; this
0x1800271b7  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x1800271bc  mov     ebx, [rbp+var_28]
0x1800271bf  jmp     loc_180026FEF
0x1800271c4  cmp     ax, cx
0x1800271c7  jz      short loc_18002717F
0x1800271c9  mov     r15d, 107h
0x1800271cf  lea     rsi, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x1800271d6  mov     r8d, r15d; int
0x1800271d9  lea     rcx, [rbp+var_48]; this
0x1800271dd  mov     rdx, rsi; char *
0x1800271e0  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800271e5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800271ec  mov     edi, 0C00D36B2h
0x1800271f1  mov     ebx, edi
0x1800271f3  test    rcx, rcx
0x1800271f6  jnz     loc_180027461
0x1800271fc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180027202  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180027209  mov     rcx, rax
0x18002720c  test    rax, rax
0x18002720f  jnz     loc_180027441
0x180027215  lea     rcx, qword_1801B07E0
0x18002721c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180027223  jmp     loc_180027461
0x180027228  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002722f  test    rcx, rcx
0x180027232  jnz     loc_1800273E9
0x180027238  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002723e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180027245  mov     rcx, rax
0x180027248  test    rax, rax
0x18002724b  jnz     loc_1800273C9
0x180027251  lea     rcx, qword_1801B07E0
0x180027258  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002725f  jmp     loc_1800273E9
0x180027264  mov     r15d, 115h
0x18002726a  lea     rsi, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x180027271  mov     r8d, r15d; int
0x180027274  lea     rcx, [rbp+var_48]; this
0x180027278  mov     rdx, rsi; char *
0x18002727b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180027280  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027287  mov     edi, 0C00D36B2h
0x18002728c  mov     ebx, edi
0x18002728e  test    rcx, rcx
0x180027291  jnz     loc_180027496
0x180027297  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002729d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800272a4  mov     rcx, rax
0x1800272a7  test    rax, rax
0x1800272aa  jnz     loc_180027476
0x1800272b0  lea     rcx, qword_1801B07E0
0x1800272b7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800272be  jmp     loc_180027496
0x1800272c3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800272ca  test    rcx, rcx
0x1800272cd  jnz     loc_1800274DB
0x1800272d3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800272d9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800272e0  mov     rcx, rax
0x1800272e3  test    rax, rax
0x1800272e6  jnz     loc_1800274BB
0x1800272ec  lea     rcx, qword_1801B07E0
0x1800272f3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800272fa  jmp     loc_1800274DB
0x1800272ff  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180027304  cmp     [rax+7CCh], ebx
0x18002730a  jz      loc_1800273F3
0x180027310  mov     r9d, ebx; int
0x180027313  lea     rdx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x18002731a  mov     r8d, 0FEh; int
0x180027320  mov     rcx, rax; this
0x180027323  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180027328  jmp     loc_1800273F3
0x18002732d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180027332  cmp     [rax+7CCh], edi
0x180027338  jz      loc_18002746B
0x18002733e  mov     r9d, edi; int
0x180027341  mov     r8d, r15d; int
0x180027344  mov     rdx, rsi; char *
0x180027347  mov     rcx, rax; this
0x18002734a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002734f  jmp     loc_18002746B
0x180027354  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180027359  cmp     [rax+7CCh], edi
0x18002735f  jz      loc_1800274A0
0x180027365  mov     r9d, edi; int
0x180027368  mov     r8d, r15d; int
0x18002736b  mov     rdx, rsi; char *
0x18002736e  mov     rcx, rax; this
0x180027371  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180027376  jmp     loc_1800274A0
0x18002737b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180027380  cmp     [rax+7CCh], ebx
0x180027386  jz      loc_1800274E5
0x18002738c  mov     r9d, ebx; int
0x18002738f  mov     r8d, r15d; int
0x180027392  mov     rdx, rdi; char *
0x180027395  mov     rcx, rax; this
0x180027398  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002739d  jmp     loc_1800274E5
0x1800273a2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800273a7  cmp     [rax+7CCh], ebx
0x1800273ad  jz      loc_1800275B2
0x1800273b3  mov     r9d, ebx; int
0x1800273b6  mov     r8d, r12d; int
0x1800273b9  mov     rdx, r15; char *
0x1800273bc  mov     rcx, rax; this
0x1800273bf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800273c4  jmp     loc_1800275B2
0x1800273c9  mov     rax, [rax]
0x1800273cc  mov     edx, 7F0h
0x1800273d1  mov     rax, [rax+8]
0x1800273d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800273da  test    eax, eax
0x1800273dc  jz      loc_180027251
0x1800273e2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800273e9  cmp     byte ptr [rcx+8], 0
0x1800273ed  jnz     loc_1800272FF
0x1800273f3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800273fa  jb      short loc_18002742A
0x1800273fc  mov     edx, 18h
0x180027401  mov     [rsp+78h+var_58], ebx
0x180027405  jmp     short loc_180027410
0x180027407  mov     edx, 19h
0x18002740c  mov     [rsp+78h+var_58], edi
0x180027410  mov     rcx, cs:WPP_GLOBAL_Control
0x180027417  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x18002741e  mov     r9, r14
0x180027421  mov     rcx, [rcx+10h]
0x180027425  call    WPP_SF_qD
0x18002742a  lea     rcx, [rbp+var_48]; this
0x18002742e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180027433  lea     rcx, [rbp+pvarDest]; this
0x180027437  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x18002743c  jmp     loc_180027071
0x180027441  mov     rax, [rax]
0x180027444  mov     edx, 7F0h
0x180027449  mov     rax, [rax+8]
0x18002744d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027452  test    eax, eax
  ... truncated ...
```
