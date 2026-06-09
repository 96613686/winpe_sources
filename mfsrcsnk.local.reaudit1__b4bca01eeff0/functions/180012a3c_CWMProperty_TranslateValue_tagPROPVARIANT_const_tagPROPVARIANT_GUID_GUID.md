# CWMProperty::TranslateValue(tagPROPVARIANT const &,tagPROPVARIANT *,_GUID,_GUID)

- ea: `0x180012a3c`
- end: `0x180013108`
- name: `?TranslateValue@CWMProperty@@IEAAJAEBUtagPROPVARIANT@@PEAU2@U_GUID@@2@Z`
- size: `1740`
- prototype: `int(CWMProperty *__hidden this, const struct tagPROPVARIANT *, struct tagPROPVARIANT *, struct _GUID *__struct_ptr, struct _GUID *__struct_ptr)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013870`
- `0x1800229e0`

## callees

- `0x180005cf4`
- `0x180010fc4`
- `0x180012a3c`
- `0x180013110`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180060ea0`
- `0x1800638a0`
- `0x180077708`
- `0x180077d2c`
- `0x180079680`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012bfb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012cff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012d41`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012da6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012de8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012bfb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012cff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012d41`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012da6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012de8`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180012b44`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001304f`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180012b44`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001304f`
- `PROPSYS!PropVariantChangeType` at `0x180012bcd`
- `PROPSYS!PropVariantChangeType` at `0x180012bcd`

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
          v29 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v31 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v34 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v36 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
  Element = CMFPropVariantConvert::Convert(&pvarDest, v14);
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
        v25 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x180012a3c  push    rbp
0x180012a3e  push    rbx
0x180012a3f  push    rsi
0x180012a40  push    rdi
0x180012a41  push    r12
0x180012a43  push    r13
0x180012a45  push    r14
0x180012a47  push    r15
0x180012a49  mov     rbp, rsp
0x180012a4c  sub     rsp, 78h
0x180012a50  movzx   r12d, word ptr [rdx]
0x180012a54  xor     eax, eax
0x180012a56  mov     r15, [rbp+arg_20]
0x180012a5a  mov     ebx, r12d
0x180012a5d  mov     qword ptr [rbp+pvarSrc+10h], rax
0x180012a61  mov     rsi, r8
0x180012a64  mov     [rbp+var_44], eax
0x180012a67  lea     r8, [rbp+var_44]
0x180012a6b  mov     rax, [rcx]
0x180012a6e  mov     r13, rdx
0x180012a71  xorps   xmm0, xmm0
0x180012a74  btr     ebx, 0Ch
0x180012a78  mov     rdx, r9
0x180012a7b  mov     [rbp+var_28], ebx
0x180012a7e  mov     r14, rcx
0x180012a81  and     r12d, 1000h
0x180012a88  mov     rax, [rax+38h]
0x180012a8c  movups  xmmword ptr [rbp+pvarSrc], xmm0
0x180012a90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a95  mov     edi, ebx
0x180012a97  test    eax, eax
0x180012a99  js      short loc_180012A9E
0x180012a9b  mov     edi, [rbp+var_44]
0x180012a9e  mov     rax, [r14]
0x180012aa1  lea     r8, [rbp+var_44]
0x180012aa5  mov     rdx, r15
0x180012aa8  mov     [rbp+var_44], 0
0x180012aaf  mov     rcx, r14
0x180012ab2  mov     rax, [rax+38h]
0x180012ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012abb  mov     r15d, r12d
0x180012abe  test    eax, eax
0x180012ac0  jns     loc_180012B80
0x180012ac6  test    r12d, r12d
0x180012ac9  jnz     loc_180012C39
0x180012acf  mov     rdx, r13; pvarSrc
0x180012ad2  lea     rcx, [rbp+pvarSrc]; pvarDest
0x180012ad6  call    ?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::Copy(tagPROPVARIANT const *)
0x180012adb  cmp     word ptr [r13+0], 41h ; 'A'
0x180012ae1  jz      loc_180012D73
0x180012ae7  cmp     ebx, edi
0x180012ae9  jnz     loc_180012B9A
0x180012aef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180012af6  test    rcx, rcx
0x180012af9  jz      loc_180012B89
0x180012aff  cmp     byte ptr [rcx+8], 0
0x180012b03  mov     r15d, 11Eh
0x180012b09  jz      loc_180012C2D
0x180012b0f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180012b14  lea     rdi, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x180012b1b  mov     ecx, [rax+7C4h]
0x180012b21  cmp     ecx, [rax+7C8h]
0x180012b27  jnb     short loc_180012B37
0x180012b29  mov     edx, ecx
0x180012b2b  add     rdx, rdx
0x180012b2e  mov     [rax+rdx*8], rdi
0x180012b32  mov     [rax+rdx*8+8], r15d
0x180012b37  inc     dword ptr [rax+7C4h]
0x180012b3d  lea     rdx, [rbp+pvarSrc]; pvarSrc
0x180012b41  mov     rcx, rsi; pvarDest
0x180012b44  call    cs:__imp_PropVariantCopy
0x180012b4b  nop     dword ptr [rax+rax+00h]
0x180012b50  mov     ebx, eax
0x180012b52  test    eax, eax
0x180012b54  js      loc_180012DD8
0x180012b5a  lea     rcx, [rbp+var_48]; this
0x180012b5e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180012b63  lea     rcx, [rbp+pvarSrc]; pvar
0x180012b67  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180012b6c  mov     eax, ebx
0x180012b6e  add     rsp, 78h
0x180012b72  pop     r15
0x180012b74  pop     r14
0x180012b76  pop     r13
0x180012b78  pop     r12
0x180012b7a  pop     rdi
0x180012b7b  pop     rsi
0x180012b7c  pop     rbx
0x180012b7d  pop     rbp
0x180012b7e  retn
0x180012b80  mov     r15d, [rbp+var_44]
0x180012b84  jmp     loc_180012AC6
0x180012b89  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180012b8e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012b95  jmp     loc_180012AFF
0x180012b9a  test    r12d, r12d
0x180012b9d  jnz     loc_180013017
0x180012ba3  mov     r12d, 129h
0x180012ba9  lea     r15, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x180012bb0  mov     r8d, r12d; int
0x180012bb3  lea     rcx, [rbp+var_48]; this
0x180012bb7  mov     rdx, r15; char *
0x180012bba  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180012bbf  movzx   r9d, di; vt
0x180012bc3  lea     rdx, [rbp+pvarSrc]; propvarSrc
0x180012bc7  xor     r8d, r8d; flags
0x180012bca  mov     rcx, rsi; ppropvarDest
0x180012bcd  call    cs:__imp_PropVariantChangeType
0x180012bd4  nop     dword ptr [rax+rax+00h]
0x180012bd9  mov     ebx, eax
0x180012bdb  test    eax, eax
0x180012bdd  js      loc_180013029
0x180012be3  test    ebx, ebx
0x180012be5  jns     loc_180012B5A
0x180012beb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012bf2  test    rcx, rcx
0x180012bf5  jnz     loc_1800130C9
0x180012bfb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180012c02  nop     dword ptr [rax+rax+00h]
0x180012c07  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180012c0e  mov     rcx, rax
0x180012c11  test    rax, rax
0x180012c14  jnz     loc_1800130A9
0x180012c1a  lea     rcx, qword_1801B97E0
0x180012c21  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180012c28  jmp     loc_1800130C9
0x180012c2d  lea     rdi, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x180012c34  jmp     loc_180012B3D
0x180012c39  test    r15d, r15d
0x180012c3c  jnz     loc_180012ACF
0x180012c42  xorps   xmm0, xmm0
0x180012c45  lea     rcx, [rbp+pvarDest]; pvar
0x180012c49  xor     eax, eax
0x180012c4b  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180012c4f  mov     qword ptr [rbp+pvarDest+10h], rax
0x180012c53  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180012c58  mov     rdx, r13; pvarSrc
0x180012c5b  lea     rcx, [rbp+pvarDest]; pvarDest
0x180012c5f  call    ?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::Copy(tagPROPVARIANT const *)
0x180012c64  movzx   ecx, word ptr [rbp+pvarDest]
0x180012c68  xor     eax, eax
0x180012c6a  cmp     ax, cx
0x180012c6d  jz      short loc_180012CCC
0x180012c6f  mov     eax, 1000h
0x180012c74  and     cx, ax
0x180012c77  xor     eax, eax
0x180012c79  cmp     dword ptr [rbp+pvarDest+8], eax
0x180012c7c  jbe     short loc_180012CC7
0x180012c7e  mov     r8d, 0FEh; int
0x180012c84  lea     rdx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x180012c8b  lea     rcx, [rbp+var_48]; this
0x180012c8f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180012c94  lea     r8, [rbp+pvarSrc]; pvarDest
0x180012c98  xor     edx, edx; unsigned int
0x180012c9a  lea     rcx, [rbp+pvarDest]; this
0x180012c9e  call    ?GetElement@CMFPropVariant@@QEBAJKPEAUtagPROPVARIANT@@@Z; CMFPropVariant::GetElement(ulong,tagPROPVARIANT *)
0x180012ca3  mov     ebx, eax
0x180012ca5  test    eax, eax
0x180012ca7  js      loc_180012D31
0x180012cad  lea     rcx, [rbp+var_48]; this
0x180012cb1  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180012cb6  lea     rcx, [rbp+pvarDest]; pvar
0x180012cba  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180012cbf  mov     ebx, [rbp+var_28]
0x180012cc2  jmp     loc_180012ADB
0x180012cc7  cmp     ax, cx
0x180012cca  jz      short loc_180012C7E
0x180012ccc  mov     r15d, 107h
0x180012cd2  lea     rsi, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x180012cd9  mov     r8d, r15d; int
0x180012cdc  lea     rcx, [rbp+var_48]; this
0x180012ce0  mov     rdx, rsi; char *
0x180012ce3  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180012ce8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012cef  mov     edi, 0C00D36B2h
0x180012cf4  mov     ebx, edi
0x180012cf6  test    rcx, rcx
0x180012cf9  jnz     loc_180012F7C
0x180012cff  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180012d06  nop     dword ptr [rax+rax+00h]
0x180012d0b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180012d12  mov     rcx, rax
0x180012d15  test    rax, rax
0x180012d18  jnz     loc_180012F5C
0x180012d1e  lea     rcx, qword_1801B97E0
0x180012d25  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180012d2c  jmp     loc_180012F7C
0x180012d31  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012d38  test    rcx, rcx
0x180012d3b  jnz     loc_180012F04
0x180012d41  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180012d48  nop     dword ptr [rax+rax+00h]
0x180012d4d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180012d54  mov     rcx, rax
0x180012d57  test    rax, rax
0x180012d5a  jnz     loc_180012EE4
0x180012d60  lea     rcx, qword_1801B97E0
0x180012d67  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180012d6e  jmp     loc_180012F04
0x180012d73  mov     r15d, 115h
0x180012d79  lea     rsi, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x180012d80  mov     r8d, r15d; int
0x180012d83  lea     rcx, [rbp+var_48]; this
0x180012d87  mov     rdx, rsi; char *
0x180012d8a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180012d8f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012d96  mov     edi, 0C00D36B2h
0x180012d9b  mov     ebx, edi
0x180012d9d  test    rcx, rcx
0x180012da0  jnz     loc_180012FB1
0x180012da6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180012dad  nop     dword ptr [rax+rax+00h]
0x180012db2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180012db9  mov     rcx, rax
0x180012dbc  test    rax, rax
0x180012dbf  jnz     loc_180012F91
0x180012dc5  lea     rcx, qword_1801B97E0
0x180012dcc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180012dd3  jmp     loc_180012FB1
0x180012dd8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012ddf  test    rcx, rcx
0x180012de2  jnz     loc_180012FF6
0x180012de8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180012def  nop     dword ptr [rax+rax+00h]
0x180012df4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180012dfb  mov     rcx, rax
0x180012dfe  test    rax, rax
0x180012e01  jnz     loc_180012FD6
0x180012e07  lea     rcx, qword_1801B97E0
0x180012e0e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180012e15  jmp     loc_180012FF6
0x180012e1a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180012e1f  cmp     [rax+7CCh], ebx
0x180012e25  jz      loc_180012F0E
0x180012e2b  mov     r9d, ebx; int
0x180012e2e  lea     rdx, aCwmpropertyTra; "CWMProperty::TranslateValue"
0x180012e35  mov     r8d, 0FEh; int
0x180012e3b  mov     rcx, rax; this
0x180012e3e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180012e43  jmp     loc_180012F0E
0x180012e48  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180012e4d  cmp     [rax+7CCh], edi
0x180012e53  jz      loc_180012F86
0x180012e59  mov     r9d, edi; int
0x180012e5c  mov     r8d, r15d; int
0x180012e5f  mov     rdx, rsi; char *
0x180012e62  mov     rcx, rax; this
0x180012e65  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180012e6a  jmp     loc_180012F86
0x180012e6f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180012e74  cmp     [rax+7CCh], edi
0x180012e7a  jz      loc_180012FBB
0x180012e80  mov     r9d, edi; int
0x180012e83  mov     r8d, r15d; int
0x180012e86  mov     rdx, rsi; char *
0x180012e89  mov     rcx, rax; this
0x180012e8c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180012e91  jmp     loc_180012FBB
0x180012e96  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180012e9b  cmp     [rax+7CCh], ebx
0x180012ea1  jz      loc_180013000
0x180012ea7  mov     r9d, ebx; int
0x180012eaa  mov     r8d, r15d; int
0x180012ead  mov     rdx, rdi; char *
0x180012eb0  mov     rcx, rax; this
0x180012eb3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180012eb8  jmp     loc_180013000
0x180012ebd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180012ec2  cmp     [rax+7CCh], ebx
0x180012ec8  jz      loc_1800130D3
0x180012ece  mov     r9d, ebx; int
0x180012ed1  mov     r8d, r12d; int
0x180012ed4  mov     rdx, r15; char *
0x180012ed7  mov     rcx, rax; this
0x180012eda  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180012edf  jmp     loc_1800130D3
0x180012ee4  mov     rax, [rax]
0x180012ee7  mov     edx, 7F0h
0x180012eec  mov     rax, [rax+8]
0x180012ef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ef5  test    eax, eax
0x180012ef7  jz      loc_180012D60
0x180012efd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180012f04  cmp     byte ptr [rcx+8], 0
0x180012f08  jnz     loc_180012E1A
0x180012f0e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180012f15  jb      short loc_180012F45
0x180012f17  mov     edx, 18h
0x180012f1c  mov     [rsp+78h+var_58], ebx
0x180012f20  jmp     short loc_180012F2B
0x180012f22  mov     edx, 19h
0x180012f27  mov     [rsp+78h+var_58], edi
0x180012f2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012f32  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x180012f39  mov     r9, r14
0x180012f3c  mov     rcx, [rcx+10h]
0x180012f40  call    WPP_SF_qD
0x180012f45  lea     rcx, [rbp+var_48]; this
0x180012f49  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180012f4e  lea     rcx, [rbp+pvarDest]; pvar
  ... truncated ...
```
