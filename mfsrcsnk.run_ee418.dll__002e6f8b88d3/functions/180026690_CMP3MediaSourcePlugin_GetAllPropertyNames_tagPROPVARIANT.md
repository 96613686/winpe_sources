# CMP3MediaSourcePlugin::GetAllPropertyNames(tagPROPVARIANT *)

- ea: `0x180026690`
- end: `0x180026f48`
- name: `?GetAllPropertyNames@CMP3MediaSourcePlugin@@UEAAJPEAUtagPROPVARIANT@@@Z`
- size: `2232`
- prototype: `__int64 __fastcall(CMP3MediaSourcePlugin *__hidden this, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, loader_planting`

## callees

- `0x18000d800`
- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x18001428c`
- `0x180025548`
- `0x180025e90`
- `0x180026690`
- `0x180028340`
- `0x18003bf60`
- `0x180071a44`
- `0x180073b14`
- `0x18010959c`
- `0x1801095e8`
- `0x1801099f0`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800269d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800269d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002673d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002673d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026918`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026a3a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026a76`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026aae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026ae6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026b23`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026b5b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026918`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026a3a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026a76`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026aae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026ae6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026b23`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026b5b`

## string_xrefs

- `0x1800266db`: `CMP3MediaSourcePlugin::GetAllPropertyNames`
- `0x180026b97`: `CMP3MediaSourcePlugin::GetAllPropertyNames`
- `0x180026bc8`: `CMP3MediaSourcePlugin::GetAllPropertyNames`
- `0x180026bf6`: `CMP3MediaSourcePlugin::GetAllPropertyNames`
- `0x180026c24`: `CMP3MediaSourcePlugin::GetAllPropertyNames`
- `0x180026c52`: `CMP3MediaSourcePlugin::GetAllPropertyNames`
- `0x180026c80`: `CMP3MediaSourcePlugin::GetAllPropertyNames`
- `0x180026cae`: `CMP3MediaSourcePlugin::GetAllPropertyNames`
- `0x180026cdc`: `CMP3MediaSourcePlugin::GetAllPropertyNames`
- `0x180026d0a`: `CMP3MediaSourcePlugin::GetAllPropertyNames`

## pseudocode

```c
__int64 __fastcall CMP3MediaSourcePlugin::GetAllPropertyNames(CMP3MediaSourcePlugin *this, struct tagPROPVARIANT *a2)
{
  CallStackTracing *v3; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v6; // rcx
  __int64 v7; // rcx
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  unsigned __int16 *v9; // r14
  int v10; // r9d
  char *v11; // r13
  __int64 v12; // rdx
  __int64 v13; // rcx
  int IndexedAttributeCount; // edi
  __int64 v15; // r8
  __int64 v16; // r9
  unsigned __int16 i; // r12
  unsigned __int16 *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  CallStackTracing *v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  wchar_t *v35; // rcx
  CallStackTracing *v36; // rax
  CallStackTracing *v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  struct tagPROPVARIANT *v42; // rax
  __int128 v43; // xmm0
  BYTE *v44; // xmm1_8
  wchar_t *v46; // rsi
  CallStackTracing *v47; // rax
  wchar_t *v48; // rcx
  CallStackTracing *v49; // rax
  wchar_t *v50; // rcx
  CallStackTracing *v51; // rax
  wchar_t *v52; // rcx
  CallStackTracing *v53; // rax
  wchar_t *v54; // rcx
  CallStackTracing *v55; // rax
  wchar_t *v56; // rcx
  CallStackTracing *v57; // rax
  struct CallStackContext *v58; // rax
  struct CallStackContext *v59; // rax
  struct CallStackContext *v60; // rax
  struct CallStackContext *v61; // rax
  struct CallStackContext *v62; // rax
  struct CallStackContext *v63; // rax
  struct CallStackContext *v64; // rax
  struct CallStackContext *v65; // rax
  struct CallStackContext *v66; // rax
  __int64 v67; // rdx
  int v68; // [rsp+48h] [rbp-51h]
  const unsigned __int16 *v69; // [rsp+50h] [rbp-49h]
  unsigned __int16 v70[2]; // [rsp+60h] [rbp-39h] BYREF
  unsigned __int16 v71[2]; // [rsp+64h] [rbp-35h] BYREF
  unsigned __int16 v72; // [rsp+68h] [rbp-31h] BYREF
  CMP3MediaSourcePlugin *v73; // [rsp+70h] [rbp-29h]
  struct tagPROPVARIANT *v74; // [rsp+78h] [rbp-21h]
  struct tagPROPVARIANT v75; // [rsp+80h] [rbp-19h] BYREF
  __int128 v76; // [rsp+98h] [rbp-1h] BYREF
  BYTE *v77; // [rsp+A8h] [rbp+Fh]

  v73 = this;
  v3 = CallStackTracing::s_wpInstance;
  v74 = a2;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v3 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v3 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v3);
    v6 = *((unsigned int *)ThreadRelativeContext + 497);
    if ( (unsigned int)v6 < *((_DWORD *)ThreadRelativeContext + 498) )
    {
      v7 = 2 * v6;
      *((_QWORD *)ThreadRelativeContext + v7) = "CMP3MediaSourcePlugin::GetAllPropertyNames";
      *((_DWORD *)ThreadRelativeContext + 2 * v7 + 2) = 3222;
    }
    ++*((_DWORD *)ThreadRelativeContext + 497);
  }
  v72 = 0;
  v70[0] = 0;
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  v71[0] = 0;
  v77 = 0;
  v9 = 0;
  v76 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v11 = (char *)this - 40;
  if ( !a2 )
  {
    v37 = CallStackTracing::s_wpInstance;
    IndexedAttributeCount = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v37 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v37 + 8) )
    {
      v58 = CallStackTracing::GetThreadRelativeContext(v37);
      if ( *((_DWORD *)v58 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v58, "CMP3MediaSourcePlugin::GetAllPropertyNames", 3239, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_32;
    v38 = 311;
LABEL_70:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v38,
      &WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
      v11,
      IndexedAttributeCount);
    goto LABEL_32;
  }
  *(_OWORD *)&a2->vt = 0;
  a2->bstrblobVal.pData = 0;
  IndexedAttributeCount = CWMHeaderInfoIndexBase::GetIndexedAttributeCountEx(
                            (CWMHeaderInfoIndexBase *)(*((_QWORD *)v11 + 51)
                                                     + 16LL
                                                     + *(int *)(*(_QWORD *)(*((_QWORD *)v11 + 51) + 16LL) + 8LL)),
                            0,
                            &v72,
                            v10);
  if ( IndexedAttributeCount < 0 )
  {
    v46 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v13, v12, v15, v16);
      CallStackTracing::s_wpInstance = v47;
      if ( v47 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
      {
        v46 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v46 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v46 + 8) )
    {
      v59 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
      if ( *((_DWORD *)v59 + 499) != IndexedAttributeCount )
        CallStackContext::TraceFailure(v59, "CMP3MediaSourcePlugin::GetAllPropertyNames", 3251, IndexedAttributeCount);
    }
    if ( !g_wppLevels )
      goto LABEL_32;
    v38 = 312;
    goto LABEL_70;
  }
  for ( i = 0; v72 > i; ++i )
  {
    memset(&v75, 0, sizeof(v75));
    operator delete(v9);
    v9 = 0;
    IndexedAttributeCount = CWMHeaderInfoIndexBase::GetIndexedAttributeByIndexEx(
                              (CWMHeaderInfoIndexBase *)(*((_QWORD *)v73 + 46)
                                                       + *(int *)(*(_QWORD *)(*((_QWORD *)v73 + 46) + 16LL) + 8LL)
                                                       + 16LL),
                              0,
                              i,
                              0,
                              v70,
                              0,
                              v71,
                              0,
                              0,
                              v68,
                              v69);
    if ( IndexedAttributeCount < 0 )
    {
      v31 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v31 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v31 + 8) )
      {
        v64 = CallStackTracing::GetThreadRelativeContext(v31);
        if ( *((_DWORD *)v64 + 499) != IndexedAttributeCount )
          CallStackContext::TraceFailure(v64, "CMP3MediaSourcePlugin::GetAllPropertyNames", 3269, IndexedAttributeCount);
      }
      if ( !g_wppLevels )
        goto LABEL_22;
      v67 = 313;
LABEL_97:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v67,
        &WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
        v11,
        IndexedAttributeCount);
      goto LABEL_22;
    }
    if ( !v71[0] )
    {
      v18 = (unsigned __int16 *)operator new[](saturated_mul(v70[0], 2u));
      v9 = v18;
      if ( !v18 )
      {
        v54 = (wchar_t *)CallStackTracing::s_wpInstance;
        IndexedAttributeCount = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20, v21);
          CallStackTracing::s_wpInstance = v55;
          if ( v55 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
          {
            v54 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v54 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v54 + 8) )
        {
          v63 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
          if ( *((_DWORD *)v63 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v63, "CMP3MediaSourcePlugin::GetAllPropertyNames", 3283, -2147024882);
        }
        if ( !g_wppLevels )
          goto LABEL_22;
        v67 = 314;
        goto LABEL_97;
      }
      IndexedAttributeCount = CWMHeaderInfoIndexBase::GetIndexedAttributeByIndexEx(
                                (CWMHeaderInfoIndexBase *)(*((_QWORD *)v11 + 51)
                                                         + *(int *)(*(_QWORD *)(*((_QWORD *)v11 + 51) + 16LL) + 8LL)
                                                         + 16LL),
                                0,
                                i,
                                v18,
                                v70,
                                0,
                                v71,
                                0,
                                0,
                                v68,
                                v69);
      if ( IndexedAttributeCount < 0 )
      {
        v52 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23, v24);
          CallStackTracing::s_wpInstance = v53;
          if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
          {
            v52 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v52 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v52 + 8) )
        {
          v62 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
          if ( *((_DWORD *)v62 + 499) != IndexedAttributeCount )
            CallStackContext::TraceFailure(
              v62,
              "CMP3MediaSourcePlugin::GetAllPropertyNames",
              3296,
              IndexedAttributeCount);
        }
        if ( !g_wppLevels )
          goto LABEL_22;
        v67 = 315;
        goto LABEL_97;
      }
      IndexedAttributeCount = CMFPropVariantConvert::CreateFromData(
                                (struct CMFPropVariant *)&v75,
                                31,
                                v9,
                                2 * (unsigned int)v70[0]);
      if ( IndexedAttributeCount < 0 )
      {
        v50 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v26, v27);
          CallStackTracing::s_wpInstance = v51;
          if ( v51 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
          {
            v50 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v50 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v50 + 8) )
        {
          v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
          if ( *((_DWORD *)v61 + 499) != IndexedAttributeCount )
            CallStackContext::TraceFailure(
              v61,
              "CMP3MediaSourcePlugin::GetAllPropertyNames",
              3302,
              IndexedAttributeCount);
        }
        if ( !g_wppLevels )
          goto LABEL_22;
        v67 = 316;
        goto LABEL_97;
      }
      IndexedAttributeCount = CMFPropVariant::AppendUniqueElement((CMFPropVariant *)&v76, &v75);
      if ( IndexedAttributeCount < 0 )
      {
        v48 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v29, v30);
          CallStackTracing::s_wpInstance = v49;
          if ( v49 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
          {
            v48 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v48 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v48 + 8) )
        {
          v60 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v48);
          if ( *((_DWORD *)v60 + 499) != IndexedAttributeCount )
            CallStackContext::TraceFailure(
              v60,
              "CMP3MediaSourcePlugin::GetAllPropertyNames",
              3308,
              IndexedAttributeCount);
        }
        if ( g_wppLevels )
        {
          v67 = 317;
          goto LABEL_97;
        }
LABEL_22:
        CMFPropVariant::Clear((CMFPropVariant *)&v75);
        v35 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v33, v34);
          CallStackTracing::s_wpInstance = v36;
          if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
          {
            v35 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v35 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v35 + 8) )
        {
          v65 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
          if ( *((_DWORD *)v65 + 499) != IndexedAttributeCount )
            CallStackContext::TraceFailure(
              v65,
              "CMP3MediaSourcePlugin::GetAllPropertyNames",
              3310,
              IndexedAttributeCount);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            318,
            &WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
            v11,
            IndexedAttributeCount);
        goto LABEL_32;
      }
    }
    CMFPropVariant::Clear((CMFPropVariant *)&v75);
  }
  IndexedAttributeCount = CMFPropVariant::SortElements((CMFPropVariant *)&v76);
  if ( IndexedAttributeCount >= 0 )
  {
    v42 = v74;
    v43 = v76;
    LOWORD(v76) = 0;
    v44 = v77;
    *(_OWORD *)&v74->vt = v43;
    v42->bstrblobVal.pData = v44;
    goto LABEL_32;
  }
  v56 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39, v40, v41);
    CallStackTracing::s_wpInstance = v57;
    if ( v57 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v57 + 8LL))(v57, 2032) )
    {
      v56 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v56 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v56 + 8) )
  {
    v66 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v56);
    if ( *((_DWORD *)v66 + 499) != IndexedAttributeCount )
      CallStackContext::TraceFailure(v66, "CMP3MediaSourcePlugin::GetAllPropertyNames", 3324, IndexedAttributeCount);
  }
  if ( g_wppLevels )
  {
    v38 = 319;
    goto LABEL_70;
  }
LABEL_32:
  operator delete(v9);
  LeaveCriticalSection(v8);
  CMFPropVariant::Clear((CMFPropVariant *)&v76);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v70);
  return (unsigned int)IndexedAttributeCount;
}

```

## disassembly

```asm
0x180026690  mov     [rsp-8+arg_10], rbx
0x180026695  push    rbp
0x180026696  push    rsi
0x180026697  push    rdi
0x180026698  push    r12
0x18002669a  push    r13
0x18002669c  push    r14
0x18002669e  push    r15
0x1800266a0  lea     rbp, [rsp-27h]
0x1800266a5  sub     rsp, 0C0h
0x1800266ac  mov     rax, cs:__security_cookie
0x1800266b3  xor     rax, rsp
0x1800266b6  mov     [rbp+57h+var_40], rax
0x1800266ba  mov     rdi, rcx
0x1800266bd  mov     [rbp+57h+var_80], rcx
0x1800266c1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800266c8  xor     r15d, r15d
0x1800266cb  mov     [rbp+57h+var_78], rdx
0x1800266cf  mov     rsi, rdx
0x1800266d2  test    rcx, rcx
0x1800266d5  jz      loc_180026940
0x1800266db  lea     rbx, aCmp3mediasourc_32; "CMP3MediaSourcePlugin::GetAllPropertyNa"...
0x1800266e2  mov     r12d, 1
0x1800266e8  cmp     [rcx+8], r15b
0x1800266ec  jz      short loc_180026717
0x1800266ee  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800266f3  mov     ecx, [rax+7C4h]
0x1800266f9  cmp     ecx, [rax+7C8h]
0x1800266ff  jnb     short loc_180026710
0x180026701  add     rcx, rcx
0x180026704  mov     [rax+rcx*8], rbx
0x180026708  mov     dword ptr [rax+rcx*8+8], 0C96h
0x180026710  add     [rax+7C4h], r12d
0x180026717  xorps   xmm0, xmm0
0x18002671a  mov     [rbp+57h+var_88], r15w
0x18002671f  xor     eax, eax
0x180026721  mov     [rbp+57h+var_90], r15w
0x180026726  lea     rbx, [rdi+10h]
0x18002672a  mov     [rbp+57h+var_8C], r15w
0x18002672f  mov     rcx, rbx; lpCriticalSection
0x180026732  mov     [rbp+57h+var_48], rax
0x180026736  mov     r14, r15
0x180026739  movups  [rbp+57h+var_58], xmm0
0x18002673d  call    cs:__imp_EnterCriticalSection
0x180026743  lea     r13, [rdi-28h]
0x180026747  test    rsi, rsi
0x18002674a  jz      loc_18002695F
0x180026750  xor     eax, eax
0x180026752  xorps   xmm0, xmm0
0x180026755  movups  xmmword ptr [rsi], xmm0
0x180026758  mov     [rsi+10h], rax
0x18002675c  xor     edx, edx; unsigned __int16
0x18002675e  mov     r8, [r13+198h]
0x180026765  mov     rax, [r8+10h]
0x180026769  add     r8, 10h
0x18002676d  movsxd  rcx, dword ptr [rax+8]
0x180026771  add     rcx, r8; this
0x180026774  lea     r8, [rbp+57h+var_88]; unsigned __int16 *
0x180026778  call    ?GetIndexedAttributeCountEx@CWMHeaderInfoIndexBase@@QEAAJGPEAGH@Z; CWMHeaderInfoIndexBase::GetIndexedAttributeCountEx(ushort,ushort *,int)
0x18002677d  mov     edi, eax
0x18002677f  test    eax, eax
0x180026781  js      loc_180026A2A
0x180026787  mov     r12d, r15d
0x18002678a  lea     rsi, qword_1801B07E0
0x180026791  lea     r15, WPP_d883d89413f235918ed5b1c680996b82_Traceguids
0x180026798  cmp     [rbp+57h+var_88], r12w
0x18002679d  jbe     loc_180026991
0x1800267a3  xorps   xmm0, xmm0
0x1800267a6  xor     eax, eax
0x1800267a8  mov     rcx, r14; Block
0x1800267ab  mov     qword ptr [rbp+57h+var_70+10h], rax
0x1800267af  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x1800267b3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800267b8  mov     rax, [rbp+57h+var_80]
0x1800267bc  xor     r9d, r9d; unsigned __int16 *
0x1800267bf  mov     [rsp+0F0h+var_B0], r9; unsigned int *
0x1800267c4  xor     edx, edx; unsigned __int16
0x1800267c6  mov     [rsp+0F0h+var_B8], r9; unsigned __int8 *
0x1800267cb  mov     r14d, r9d
0x1800267ce  mov     r8, [rax+170h]
0x1800267d5  mov     rax, [r8+10h]
0x1800267d9  movsxd  rcx, dword ptr [rax+8]
0x1800267dd  lea     rax, [rbp+57h+var_8C]
0x1800267e1  mov     [rsp+0F0h+var_C0], rax; unsigned __int16 *
0x1800267e6  add     rcx, 10h
0x1800267ea  add     rcx, r8; this
0x1800267ed  mov     [rsp+0F0h+var_C8], r9; enum WMT_ATTR_DATATYPE *
0x1800267f2  lea     rax, [rbp+57h+var_90]
0x1800267f6  movzx   r8d, r12w; unsigned __int16
0x1800267fa  mov     [rsp+0F0h+var_D0], rax; unsigned __int16 *
0x1800267ff  call    ?GetIndexedAttributeByIndexEx@CWMHeaderInfoIndexBase@@QEAAJGGPEAG0PEAW4WMT_ATTR_DATATYPE@@0PEAEPEAKHPEBG@Z; CWMHeaderInfoIndexBase::GetIndexedAttributeByIndexEx(ushort,ushort,ushort *,ushort *,WMT_ATTR_DATATYPE *,ushort *,uchar *,ulong *,int,ushort const *)
0x180026804  mov     edi, eax
0x180026806  test    eax, eax
0x180026808  js      loc_1800268DC
0x18002680e  xor     eax, eax
0x180026810  cmp     ax, [rbp+57h+var_8C]
0x180026814  jnz     loc_1800268CA
0x18002681a  movzx   ecx, [rbp+57h+var_90]
0x18002681e  lea     eax, [r14+2]
0x180026822  mul     rcx
0x180026825  lea     rcx, [r14-1]
0x180026829  cmovb   rax, rcx
0x18002682d  mov     rcx, rax; unsigned __int64
0x180026830  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180026835  mov     r14, rax
0x180026838  test    rax, rax
0x18002683b  jz      loc_180026B0E
0x180026841  mov     r8, [r13+198h]
0x180026848  xor     edx, edx; unsigned __int16
0x18002684a  mov     [rsp+0F0h+var_B0], rdx; unsigned int *
0x18002684f  mov     r9, r14; unsigned __int16 *
0x180026852  mov     [rsp+0F0h+var_B8], rdx; unsigned __int8 *
0x180026857  mov     rax, [r8+10h]
0x18002685b  movsxd  rcx, dword ptr [rax+8]
0x18002685f  lea     rax, [rbp+57h+var_8C]
0x180026863  mov     [rsp+0F0h+var_C0], rax; unsigned __int16 *
0x180026868  add     rcx, 10h
0x18002686c  add     rcx, r8; this
0x18002686f  mov     [rsp+0F0h+var_C8], rdx; enum WMT_ATTR_DATATYPE *
0x180026874  lea     rax, [rbp+57h+var_90]
0x180026878  movzx   r8d, r12w; unsigned __int16
0x18002687c  mov     [rsp+0F0h+var_D0], rax; unsigned __int16 *
0x180026881  call    ?GetIndexedAttributeByIndexEx@CWMHeaderInfoIndexBase@@QEAAJGGPEAG0PEAW4WMT_ATTR_DATATYPE@@0PEAEPEAKHPEBG@Z; CWMHeaderInfoIndexBase::GetIndexedAttributeByIndexEx(ushort,ushort,ushort *,ushort *,WMT_ATTR_DATATYPE *,ushort *,uchar *,ulong *,int,ushort const *)
0x180026886  mov     edi, eax
0x180026888  test    eax, eax
0x18002688a  js      loc_180026AD6
0x180026890  movzx   r9d, [rbp+57h+var_90]
0x180026895  lea     rcx, [rbp+57h+var_70]; this
0x180026899  add     r9d, r9d; unsigned int
0x18002689c  mov     edx, 1Fh; unsigned __int16
0x1800268a1  mov     r8, r14; void *
0x1800268a4  call    ?CreateFromData@CMFPropVariantConvert@@SAJPEAVCMFPropVariant@@GPEBXK@Z; CMFPropVariantConvert::CreateFromData(CMFPropVariant *,ushort,void const *,ulong)
0x1800268a9  mov     edi, eax
0x1800268ab  test    eax, eax
0x1800268ad  js      loc_180026A9E
0x1800268b3  lea     rdx, [rbp+57h+var_70]; struct tagPROPVARIANT *
0x1800268b7  lea     rcx, [rbp+57h+var_58]; this
0x1800268bb  call    ?AppendUniqueElement@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::AppendUniqueElement(tagPROPVARIANT const *)
0x1800268c0  mov     edi, eax
0x1800268c2  test    eax, eax
0x1800268c4  js      loc_180026A66
0x1800268ca  lea     rcx, [rbp+57h+var_70]; this
0x1800268ce  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x1800268d3  inc     r12w
0x1800268d7  jmp     loc_18002678A
0x1800268dc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800268e3  test    rcx, rcx
0x1800268e6  jz      short loc_180026951
0x1800268e8  cmp     [rcx+8], r14b
0x1800268ec  jnz     loc_180026C9A
0x1800268f2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800268f9  jnb     loc_180026E8D
0x1800268ff  lea     rcx, [rbp+57h+var_70]; this
0x180026903  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180026908  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002690f  test    rcx, rcx
0x180026912  jnz     loc_180026ED1
0x180026918  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002691e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180026925  mov     rcx, rax
0x180026928  test    rax, rax
0x18002692b  jnz     loc_180026EB1
0x180026931  mov     rcx, rsi
0x180026934  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002693b  jmp     loc_180026ED1
0x180026940  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180026945  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002694c  jmp     loc_1800266DB
0x180026951  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180026956  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002695d  jmp     short loc_1800268E8
0x18002695f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180026966  mov     edi, 80004003h
0x18002696b  test    rcx, rcx
0x18002696e  jz      loc_180026A13
0x180026974  cmp     [rcx+8], r15b
0x180026978  jnz     loc_180026B83
0x18002697e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180026985  jb      short loc_1800269C7
0x180026987  mov     edx, 137h
0x18002698c  jmp     loc_180026D29
0x180026991  test    edi, edi
0x180026993  js      loc_180026908
0x180026999  lea     rcx, [rbp+57h+var_58]; this
0x18002699d  call    ?SortElements@CMFPropVariant@@QEAAJXZ; CMFPropVariant::SortElements(void)
0x1800269a2  mov     edi, eax
0x1800269a4  test    eax, eax
0x1800269a6  js      loc_180026B4B
0x1800269ac  mov     rax, [rbp+57h+var_78]
0x1800269b0  xor     ecx, ecx
0x1800269b2  movups  xmm0, [rbp+57h+var_58]
0x1800269b6  mov     word ptr [rbp+57h+var_58], cx
0x1800269ba  movsd   xmm1, [rbp+57h+var_48]
0x1800269bf  movups  xmmword ptr [rax], xmm0
0x1800269c2  movsd   qword ptr [rax+10h], xmm1
0x1800269c7  mov     rcx, r14; Block
0x1800269ca  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800269cf  mov     rcx, rbx; lpCriticalSection
0x1800269d2  call    cs:__imp_LeaveCriticalSection
0x1800269d8  lea     rcx, [rbp+57h+var_58]; this
0x1800269dc  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x1800269e1  lea     rcx, [rbp+57h+var_90]; this
0x1800269e5  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800269ea  mov     eax, edi
0x1800269ec  mov     rcx, [rbp+57h+var_40]
0x1800269f0  xor     rcx, rsp; StackCookie
0x1800269f3  call    __security_check_cookie
0x1800269f8  mov     rbx, [rsp+0F0h+arg_10]
0x180026a00  add     rsp, 0C0h
0x180026a07  pop     r15
0x180026a09  pop     r14
0x180026a0b  pop     r13
0x180026a0d  pop     r12
0x180026a0f  pop     rdi
0x180026a10  pop     rsi
0x180026a11  pop     rbp
0x180026a12  retn
0x180026a13  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180026a18  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026a1f  jmp     loc_180026974
0x180026a24  test    edi, edi
0x180026a26  js      short loc_1800269C7
0x180026a28  jmp     short loc_1800269AC
0x180026a2a  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026a31  test    rsi, rsi
0x180026a34  jnz     loc_180026D76
0x180026a3a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180026a40  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180026a47  mov     rcx, rax
0x180026a4a  test    rax, rax
0x180026a4d  jnz     loc_180026D56
0x180026a53  lea     rsi, qword_1801B07E0
0x180026a5a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x180026a61  jmp     loc_180026D76
0x180026a66  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026a6d  test    rcx, rcx
0x180026a70  jnz     loc_180026DAF
0x180026a76  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180026a7c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180026a83  mov     rcx, rax
0x180026a86  test    rax, rax
0x180026a89  jnz     loc_180026D8F
0x180026a8f  mov     rcx, rsi
0x180026a92  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180026a99  jmp     loc_180026DAF
0x180026a9e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026aa5  test    rcx, rcx
0x180026aa8  jnz     loc_180026DF0
0x180026aae  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180026ab4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180026abb  mov     rcx, rax
0x180026abe  test    rax, rax
0x180026ac1  jnz     loc_180026DD0
0x180026ac7  mov     rcx, rsi
0x180026aca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180026ad1  jmp     loc_180026DF0
0x180026ad6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026add  test    rcx, rcx
0x180026ae0  jnz     loc_180026E31
0x180026ae6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180026aec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180026af3  mov     rcx, rax
0x180026af6  test    rax, rax
0x180026af9  jnz     loc_180026E11
0x180026aff  mov     rcx, rsi
0x180026b02  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180026b09  jmp     loc_180026E31
0x180026b0e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026b15  mov     edi, 8007000Eh
0x180026b1a  test    rcx, rcx
0x180026b1d  jnz     loc_180026E6F
0x180026b23  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180026b29  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180026b30  mov     rcx, rax
0x180026b33  test    rax, rax
0x180026b36  jnz     loc_180026E4F
0x180026b3c  mov     rcx, rsi
0x180026b3f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180026b46  jmp     loc_180026E6F
0x180026b4b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026b52  test    rcx, rcx
0x180026b55  jnz     loc_180026F2C
0x180026b5b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180026b61  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180026b68  mov     rcx, rax
0x180026b6b  test    rax, rax
0x180026b6e  jnz     loc_180026F0C
0x180026b74  mov     rcx, rsi
0x180026b77  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180026b7e  jmp     loc_180026F2C
0x180026b83  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180026b88  cmp     [rax+7CCh], edi
0x180026b8e  jz      loc_18002697E
0x180026b94  mov     r9d, edi; int
0x180026b97  lea     rdx, aCmp3mediasourc_32; "CMP3MediaSourcePlugin::GetAllPropertyNa"...
0x180026b9e  mov     r8d, 0CA7h; int
0x180026ba4  mov     rcx, rax; this
0x180026ba7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180026bac  jmp     loc_18002697E
0x180026bb1  mov     rcx, rsi; this
  ... truncated ...
```
