# CMP3MediaSourcePlugin::GetAllPropertyNames(tagPROPVARIANT *)

- ea: `0x180012170`
- end: `0x180012a35`
- name: `?GetAllPropertyNames@CMP3MediaSourcePlugin@@UEAAJPEAUtagPROPVARIANT@@@Z`
- size: `2245`
- prototype: `__int64 __fastcall(CMP3MediaSourcePlugin *__hidden this, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, loader_planting`

## callees

- `0x180005cf4`
- `0x180010fc4`
- `0x180011940`
- `0x180012170`
- `0x180013f10`
- `0x180015f58`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x18003e890`
- `0x18004452c`
- `0x180077708`
- `0x180079680`
- `0x180110a88`
- `0x180110ad4`
- `0x180110ed0`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012482`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012482`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800121e4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800121e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800123ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800124f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012536`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012574`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800125b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800125f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012633`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800123ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800124f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012536`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012574`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800125b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800125f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012633`

## string_xrefs

- `0x1800121a8`: `CMP3MediaSourcePlugin::GetAllPropertyNames`
- `0x1800126cc`: `CMP3MediaSourcePlugin::GetAllPropertyNames`
- `0x1800126fa`: `CMP3MediaSourcePlugin::GetAllPropertyNames`
- `0x180012728`: `CMP3MediaSourcePlugin::GetAllPropertyNames`
- `0x180012756`: `CMP3MediaSourcePlugin::GetAllPropertyNames`
- `0x180012784`: `CMP3MediaSourcePlugin::GetAllPropertyNames`
- `0x1800127b2`: `CMP3MediaSourcePlugin::GetAllPropertyNames`
- `0x1800127e0`: `CMP3MediaSourcePlugin::GetAllPropertyNames`

## pseudocode

```c
__int64 __fastcall CMP3MediaSourcePlugin::GetAllPropertyNames(CMP3MediaSourcePlugin *this, struct tagPROPVARIANT *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  unsigned __int16 *v5; // r15
  int v6; // r9d
  char *v7; // r13
  __int64 v8; // rdx
  __int64 v9; // rcx
  int IndexedAttributeCount; // edi
  unsigned __int16 i; // r13
  unsigned __int16 *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rdx
  CallStackTracing *v17; // rcx
  __int64 v18; // rdx
  wchar_t *v19; // rcx
  CallStackTracing *v20; // rax
  CallStackTracing *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rdx
  struct tagPROPVARIANT *v24; // rax
  __int128 v25; // xmm0
  BYTE *pData; // xmm1_8
  wchar_t *v28; // rsi
  CallStackTracing *v29; // rax
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  wchar_t *v32; // rcx
  CallStackTracing *v33; // rax
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  wchar_t *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct CallStackContext *v41; // rax
  struct CallStackContext *v42; // rax
  struct CallStackContext *v43; // rax
  struct CallStackContext *v44; // rax
  struct CallStackContext *v45; // rax
  struct CallStackContext *v46; // rax
  struct CallStackContext *v47; // rax
  struct CallStackContext *v48; // rax
  char *v49; // r9
  __int64 v50; // rdx
  int v51; // [rsp+48h] [rbp-51h]
  const unsigned __int16 *v52; // [rsp+50h] [rbp-49h]
  unsigned __int16 v53[2]; // [rsp+60h] [rbp-39h] BYREF
  unsigned __int16 v54[2]; // [rsp+64h] [rbp-35h] BYREF
  unsigned __int16 v55; // [rsp+68h] [rbp-31h] BYREF
  CMP3MediaSourcePlugin *v56; // [rsp+70h] [rbp-29h]
  struct tagPROPVARIANT *v57; // [rsp+78h] [rbp-21h]
  PROPVARIANT pvar; // [rsp+80h] [rbp-19h] BYREF
  PROPVARIANT v59; // [rsp+98h] [rbp-1h] BYREF

  v57 = a2;
  v56 = this;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v53,
    "CMP3MediaSourcePlugin::GetAllPropertyNames",
    3222);
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  v55 = 0;
  v53[0] = 0;
  v54[0] = 0;
  v5 = 0;
  memset(&v59, 0, sizeof(v59));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v7 = (char *)this - 40;
  if ( !a2 )
  {
    v21 = CallStackTracing::s_wpInstance;
    IndexedAttributeCount = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v21 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v21 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v21);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMP3MediaSourcePlugin::GetAllPropertyNames",
          3239,
          -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_26;
    v22 = 311;
    goto LABEL_64;
  }
  *(_OWORD *)&a2->vt = 0;
  a2->bstrblobVal.pData = 0;
  IndexedAttributeCount = CWMHeaderInfoIndexBase::GetIndexedAttributeCountEx(
                            (CWMHeaderInfoIndexBase *)(*((_QWORD *)v7 + 51)
                                                     + 16LL
                                                     + *(int *)(*(_QWORD *)(*((_QWORD *)v7 + 51) + 16LL) + 8LL)),
                            0,
                            &v55,
                            v6);
  if ( IndexedAttributeCount < 0 )
  {
    v28 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v9, v8);
      CallStackTracing::s_wpInstance = v29;
      if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
      {
        v28 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v28 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v28 + 8) )
    {
      v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
      if ( *((_DWORD *)v41 + 499) != IndexedAttributeCount )
        CallStackContext::TraceFailure(v41, "CMP3MediaSourcePlugin::GetAllPropertyNames", 3251, IndexedAttributeCount);
    }
    if ( !g_wppLevels )
      goto LABEL_26;
    v22 = 312;
LABEL_64:
    v49 = v7;
LABEL_65:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v22,
      &WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
      v49,
      IndexedAttributeCount);
    goto LABEL_26;
  }
  for ( i = 0; v55 > i; ++i )
  {
    memset(&pvar, 0, sizeof(pvar));
    operator delete(v5);
    v5 = 0;
    IndexedAttributeCount = CWMHeaderInfoIndexBase::GetIndexedAttributeByIndexEx(
                              (CWMHeaderInfoIndexBase *)(*((_QWORD *)v56 + 46)
                                                       + *(int *)(*(_QWORD *)(*((_QWORD *)v56 + 46) + 16LL) + 8LL)
                                                       + 16LL),
                              0,
                              i,
                              0,
                              v53,
                              0,
                              v54,
                              0,
                              0,
                              v51,
                              v52);
    if ( IndexedAttributeCount < 0 )
    {
      v17 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v17 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v17 + 8) )
      {
        v46 = CallStackTracing::GetThreadRelativeContext(v17);
        if ( *((_DWORD *)v46 + 499) != IndexedAttributeCount )
          CallStackContext::TraceFailure(v46, "CMP3MediaSourcePlugin::GetAllPropertyNames", 3269, IndexedAttributeCount);
      }
      if ( !g_wppLevels )
        goto LABEL_16;
      v50 = 313;
LABEL_92:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v50,
        &WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
        (char *)v56 - 40,
        IndexedAttributeCount);
      goto LABEL_16;
    }
    if ( !v54[0] )
    {
      v12 = (unsigned __int16 *)operator new[](saturated_mul(v53[0], 2u));
      v5 = v12;
      if ( !v12 )
      {
        v36 = (wchar_t *)CallStackTracing::s_wpInstance;
        IndexedAttributeCount = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
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
          v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
          if ( *((_DWORD *)v45 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v45, "CMP3MediaSourcePlugin::GetAllPropertyNames", 3283, -2147024882);
        }
        if ( !g_wppLevels )
          goto LABEL_16;
        v50 = 314;
        goto LABEL_92;
      }
      IndexedAttributeCount = CWMHeaderInfoIndexBase::GetIndexedAttributeByIndexEx(
                                (CWMHeaderInfoIndexBase *)(*((_QWORD *)v56 + 46)
                                                         + *(int *)(*(_QWORD *)(*((_QWORD *)v56 + 46) + 16LL) + 8LL)
                                                         + 16LL),
                                0,
                                i,
                                v12,
                                v53,
                                0,
                                v54,
                                0,
                                0,
                                v51,
                                v52);
      if ( IndexedAttributeCount < 0 )
      {
        v34 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
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
          v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
          if ( *((_DWORD *)v44 + 499) != IndexedAttributeCount )
            CallStackContext::TraceFailure(
              v44,
              "CMP3MediaSourcePlugin::GetAllPropertyNames",
              3296,
              IndexedAttributeCount);
        }
        if ( !g_wppLevels )
          goto LABEL_16;
        v50 = 315;
        goto LABEL_92;
      }
      IndexedAttributeCount = CMFPropVariantConvert::CreateFromData(
                                (__int64)&pvar,
                                0x1Fu,
                                (char *)v5,
                                2 * (unsigned int)v53[0]);
      if ( IndexedAttributeCount < 0 )
      {
        v32 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
          CallStackTracing::s_wpInstance = v33;
          if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
          {
            v32 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v32 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v32 + 8) )
        {
          v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
          if ( *((_DWORD *)v43 + 499) != IndexedAttributeCount )
            CallStackContext::TraceFailure(
              v43,
              "CMP3MediaSourcePlugin::GetAllPropertyNames",
              3302,
              IndexedAttributeCount);
        }
        if ( !g_wppLevels )
          goto LABEL_16;
        v50 = 316;
        goto LABEL_92;
      }
      IndexedAttributeCount = CMFPropVariant::AppendUniqueElement((CMFPropVariant *)&v59, &pvar);
      if ( IndexedAttributeCount < 0 )
      {
        v30 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
          CallStackTracing::s_wpInstance = v31;
          if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
          {
            v30 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v30 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v30 + 8) )
        {
          v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
          if ( *((_DWORD *)v42 + 499) != IndexedAttributeCount )
            CallStackContext::TraceFailure(
              v42,
              "CMP3MediaSourcePlugin::GetAllPropertyNames",
              3308,
              IndexedAttributeCount);
        }
        if ( g_wppLevels )
        {
          v50 = 317;
          goto LABEL_92;
        }
LABEL_16:
        CMFPropVariant::Clear(&pvar);
        v19 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
          CallStackTracing::s_wpInstance = v20;
          if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
          {
            v19 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v19 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v19 + 8) )
        {
          v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
          if ( *((_DWORD *)v47 + 499) != IndexedAttributeCount )
            CallStackContext::TraceFailure(
              v47,
              "CMP3MediaSourcePlugin::GetAllPropertyNames",
              3310,
              IndexedAttributeCount);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            318,
            &WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
            (char *)v56 - 40,
            IndexedAttributeCount);
        goto LABEL_26;
      }
    }
    CMFPropVariant::Clear(&pvar);
  }
  IndexedAttributeCount = CMFPropVariant::SortElements((CMFPropVariant *)&v59);
  if ( IndexedAttributeCount >= 0 )
  {
    v24 = v57;
    v25 = *(_OWORD *)&v59.vt;
    v59.vt = 0;
    pData = v59.bstrblobVal.pData;
    *(_OWORD *)&v57->vt = v25;
    v24->bstrblobVal.pData = pData;
    goto LABEL_26;
  }
  v38 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
    CallStackTracing::s_wpInstance = v39;
    if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
    {
      v38 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v38 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
  }
  if ( *((_BYTE *)v38 + 8) )
  {
    v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
    if ( *((_DWORD *)v48 + 499) != IndexedAttributeCount )
      CallStackContext::TraceFailure(v48, "CMP3MediaSourcePlugin::GetAllPropertyNames", 3324, IndexedAttributeCount);
  }
  if ( g_wppLevels )
  {
    v22 = 319;
    v49 = (char *)v56 - 40;
    goto LABEL_65;
  }
LABEL_26:
  operator delete(v5);
  LeaveCriticalSection(v4);
  CMFPropVariant::Clear(&v59);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v53);
  return (unsigned int)IndexedAttributeCount;
}

```

## disassembly

```asm
0x180012170  mov     [rsp-8+arg_10], rbx
0x180012175  push    rbp
0x180012176  push    rsi
0x180012177  push    rdi
0x180012178  push    r12
0x18001217a  push    r13
0x18001217c  push    r14
0x18001217e  push    r15
0x180012180  lea     rbp, [rsp-27h]
0x180012185  sub     rsp, 0C0h
0x18001218c  mov     rax, cs:__security_cookie
0x180012193  xor     rax, rsp
0x180012196  mov     [rbp+57h+var_40], rax
0x18001219a  mov     rsi, rdx
0x18001219d  mov     [rbp+57h+var_78], rdx
0x1800121a1  mov     rdi, rcx
0x1800121a4  mov     [rbp+57h+var_80], rcx
0x1800121a8  lea     r14, aCmp3mediasourc_32; "CMP3MediaSourcePlugin::GetAllPropertyNa"...
0x1800121af  mov     r8d, 0C96h; int
0x1800121b5  mov     rdx, r14; char *
0x1800121b8  lea     rcx, [rbp+57h+var_90]; this
0x1800121bc  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800121c1  xor     eax, eax
0x1800121c3  lea     rbx, [rdi+10h]
0x1800121c7  xorps   xmm0, xmm0
0x1800121ca  mov     [rbp+57h+var_88], ax
0x1800121ce  mov     rcx, rbx; lpCriticalSection
0x1800121d1  mov     [rbp+57h+var_90], ax
0x1800121d5  mov     [rbp+57h+var_8C], ax
0x1800121d9  xor     r15d, r15d
0x1800121dc  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x1800121e0  mov     qword ptr [rbp+57h+var_58+10h], rax
0x1800121e4  call    cs:__imp_EnterCriticalSection
0x1800121eb  nop     dword ptr [rax+rax+00h]
0x1800121f0  lea     r13, [rdi-28h]
0x1800121f4  test    rsi, rsi
0x1800121f7  jz      loc_18001240A
0x1800121fd  xor     eax, eax
0x1800121ff  xorps   xmm0, xmm0
0x180012202  movups  xmmword ptr [rsi], xmm0
0x180012205  mov     [rsi+10h], rax
0x180012209  xor     edx, edx; unsigned __int16
0x18001220b  mov     r8, [r13+198h]
0x180012212  mov     rax, [r8+10h]
0x180012216  add     r8, 10h
0x18001221a  movsxd  rcx, dword ptr [rax+8]
0x18001221e  add     rcx, r8; this
0x180012221  lea     r8, [rbp+57h+var_88]; unsigned __int16 *
0x180012225  call    ?GetIndexedAttributeCountEx@CWMHeaderInfoIndexBase@@QEAAJGPEAGH@Z; CWMHeaderInfoIndexBase::GetIndexedAttributeCountEx(ushort,ushort *,int)
0x18001222a  mov     edi, eax
0x18001222c  test    eax, eax
0x18001222e  js      loc_1800124E4
0x180012234  xor     r13d, r13d
0x180012237  mov     r14w, 1
0x18001223c  lea     rsi, qword_1801B97E0
0x180012243  lea     r12, WPP_d883d89413f235918ed5b1c680996b82_Traceguids
0x18001224a  cmp     [rbp+57h+var_88], r13w
0x18001224f  jbe     loc_180012441
0x180012255  xorps   xmm0, xmm0
0x180012258  xor     eax, eax
0x18001225a  mov     rcx, r15; Block
0x18001225d  mov     qword ptr [rbp+57h+pvar+10h], rax
0x180012261  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180012265  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001226a  mov     rax, [rbp+57h+var_80]
0x18001226e  xor     r9d, r9d; unsigned __int16 *
0x180012271  mov     [rsp+0F0h+var_B0], r9; unsigned int *
0x180012276  xor     edx, edx; unsigned __int16
0x180012278  mov     [rsp+0F0h+var_B8], r9; unsigned __int8 *
0x18001227d  mov     r15d, r9d
0x180012280  mov     r8, [rax+170h]
0x180012287  mov     rax, [r8+10h]
0x18001228b  movsxd  rcx, dword ptr [rax+8]
0x18001228f  lea     rax, [rbp+57h+var_8C]
0x180012293  mov     [rsp+0F0h+var_C0], rax; unsigned __int16 *
0x180012298  add     rcx, 10h
0x18001229c  add     rcx, r8; this
0x18001229f  mov     [rsp+0F0h+var_C8], r9; enum WMT_ATTR_DATATYPE *
0x1800122a4  lea     rax, [rbp+57h+var_90]
0x1800122a8  movzx   r8d, r13w; unsigned __int16
0x1800122ac  mov     [rsp+0F0h+var_D0], rax; unsigned __int16 *
0x1800122b1  call    ?GetIndexedAttributeByIndexEx@CWMHeaderInfoIndexBase@@QEAAJGGPEAG0PEAW4WMT_ATTR_DATATYPE@@0PEAEPEAKHPEBG@Z; CWMHeaderInfoIndexBase::GetIndexedAttributeByIndexEx(ushort,ushort,ushort *,ushort *,WMT_ATTR_DATATYPE *,ushort *,uchar *,ulong *,int,ushort const *)
0x1800122b6  mov     edi, eax
0x1800122b8  test    eax, eax
0x1800122ba  js      loc_180012392
0x1800122c0  xor     eax, eax
0x1800122c2  cmp     ax, [rbp+57h+var_8C]
0x1800122c6  jnz     loc_180012380
0x1800122cc  movzx   ecx, [rbp+57h+var_90]
0x1800122d0  lea     eax, [r15+2]
0x1800122d4  mul     rcx
0x1800122d7  lea     rcx, [r15-1]
0x1800122db  cmovb   rax, rcx
0x1800122df  mov     rcx, rax; unsigned __int64
0x1800122e2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800122e7  mov     r15, rax
0x1800122ea  test    rax, rax
0x1800122ed  jz      loc_1800125E0
0x1800122f3  mov     rax, [rbp+57h+var_80]
0x1800122f7  xor     edx, edx; unsigned __int16
0x1800122f9  mov     [rsp+0F0h+var_B0], rdx; unsigned int *
0x1800122fe  mov     r9, r15; unsigned __int16 *
0x180012301  mov     [rsp+0F0h+var_B8], rdx; unsigned __int8 *
0x180012306  mov     r8, [rax+170h]
0x18001230d  mov     rax, [r8+10h]
0x180012311  movsxd  rcx, dword ptr [rax+8]
0x180012315  lea     rax, [rbp+57h+var_8C]
0x180012319  mov     [rsp+0F0h+var_C0], rax; unsigned __int16 *
0x18001231e  add     rcx, 10h
0x180012322  add     rcx, r8; this
0x180012325  mov     [rsp+0F0h+var_C8], rdx; enum WMT_ATTR_DATATYPE *
0x18001232a  lea     rax, [rbp+57h+var_90]
0x18001232e  movzx   r8d, r13w; unsigned __int16
0x180012332  mov     [rsp+0F0h+var_D0], rax; unsigned __int16 *
0x180012337  call    ?GetIndexedAttributeByIndexEx@CWMHeaderInfoIndexBase@@QEAAJGGPEAG0PEAW4WMT_ATTR_DATATYPE@@0PEAEPEAKHPEBG@Z; CWMHeaderInfoIndexBase::GetIndexedAttributeByIndexEx(ushort,ushort,ushort *,ushort *,WMT_ATTR_DATATYPE *,ushort *,uchar *,ulong *,int,ushort const *)
0x18001233c  mov     edi, eax
0x18001233e  test    eax, eax
0x180012340  js      loc_1800125A2
0x180012346  movzx   r9d, [rbp+57h+var_90]
0x18001234b  lea     rcx, [rbp+57h+pvar]; pvar
0x18001234f  add     r9d, r9d; unsigned int
0x180012352  mov     edx, 1Fh; unsigned __int16
0x180012357  mov     r8, r15; void *
0x18001235a  call    ?CreateFromData@CMFPropVariantConvert@@SAJPEAVCMFPropVariant@@GPEBXK@Z; CMFPropVariantConvert::CreateFromData(CMFPropVariant *,ushort,void const *,ulong)
0x18001235f  mov     edi, eax
0x180012361  test    eax, eax
0x180012363  js      loc_180012564
0x180012369  lea     rdx, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x18001236d  lea     rcx, [rbp+57h+var_58]; this
0x180012371  call    ?AppendUniqueElement@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::AppendUniqueElement(tagPROPVARIANT const *)
0x180012376  mov     edi, eax
0x180012378  test    eax, eax
0x18001237a  js      loc_180012526
0x180012380  lea     rcx, [rbp+57h+pvar]; pvar
0x180012384  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180012389  add     r13w, r14w
0x18001238d  jmp     loc_18001223C
0x180012392  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180012399  test    rcx, rcx
0x18001239c  jz      short loc_1800123FC
0x18001239e  cmp     [rcx+8], r15b
0x1800123a2  jnz     loc_180012770
0x1800123a8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1800123af  jnb     loc_180012970
0x1800123b5  lea     rcx, [rbp+57h+pvar]; pvar
0x1800123b9  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x1800123be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800123c5  test    rcx, rcx
0x1800123c8  jnz     loc_1800129B9
0x1800123ce  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800123d5  nop     dword ptr [rax+rax+00h]
0x1800123da  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800123e1  mov     rcx, rax
0x1800123e4  test    rax, rax
0x1800123e7  jnz     loc_180012999
0x1800123ed  mov     rcx, rsi
0x1800123f0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800123f7  jmp     loc_1800129B9
0x1800123fc  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180012401  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012408  jmp     short loc_18001239E
0x18001240a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180012411  mov     edi, 80004003h
0x180012416  test    rcx, rcx
0x180012419  jz      loc_1800124CA
0x18001241f  cmp     [rcx+8], r15b
0x180012423  jnz     loc_180012661
0x180012429  mov     r14w, 1
0x18001242e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x180012435  jb      short loc_180012477
0x180012437  mov     edx, 137h
0x18001243c  jmp     loc_1800127FF
0x180012441  test    edi, edi
0x180012443  js      loc_1800123BE
0x180012449  lea     rcx, [rbp+57h+var_58]; this
0x18001244d  call    ?SortElements@CMFPropVariant@@QEAAJXZ; CMFPropVariant::SortElements(void)
0x180012452  mov     edi, eax
0x180012454  test    eax, eax
0x180012456  js      loc_180012623
0x18001245c  mov     rax, [rbp+57h+var_78]
0x180012460  xor     ecx, ecx
0x180012462  movups  xmm0, xmmword ptr [rbp+57h+var_58]
0x180012466  mov     word ptr [rbp+57h+var_58], cx
0x18001246a  movsd   xmm1, qword ptr [rbp+57h+var_58+10h]
0x18001246f  movups  xmmword ptr [rax], xmm0
0x180012472  movsd   qword ptr [rax+10h], xmm1
0x180012477  mov     rcx, r15; Block
0x18001247a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001247f  mov     rcx, rbx; lpCriticalSection
0x180012482  call    cs:__imp_LeaveCriticalSection
0x180012489  nop     dword ptr [rax+rax+00h]
0x18001248e  lea     rcx, [rbp+57h+var_58]; pvar
0x180012492  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180012497  lea     rcx, [rbp+57h+var_90]; this
0x18001249b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800124a0  mov     eax, edi
0x1800124a2  mov     rcx, [rbp+57h+var_40]
0x1800124a6  xor     rcx, rsp; StackCookie
0x1800124a9  call    __security_check_cookie
0x1800124ae  mov     rbx, [rsp+0F0h+arg_10]
0x1800124b6  add     rsp, 0C0h
0x1800124bd  pop     r15
0x1800124bf  pop     r14
0x1800124c1  pop     r13
0x1800124c3  pop     r12
0x1800124c5  pop     rdi
0x1800124c6  pop     rsi
0x1800124c7  pop     rbp
0x1800124c8  retn
0x1800124ca  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800124cf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800124d6  jmp     loc_18001241F
0x1800124db  test    edi, edi
0x1800124dd  js      short loc_180012477
0x1800124df  jmp     loc_18001245C
0x1800124e4  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800124eb  test    rsi, rsi
0x1800124ee  jnz     loc_180012854
0x1800124f4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800124fb  nop     dword ptr [rax+rax+00h]
0x180012500  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180012507  mov     rcx, rax
0x18001250a  test    rax, rax
0x18001250d  jnz     loc_180012834
0x180012513  lea     rsi, qword_1801B97E0
0x18001251a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x180012521  jmp     loc_180012854
0x180012526  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001252d  test    rcx, rcx
0x180012530  jnz     loc_180012892
0x180012536  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001253d  nop     dword ptr [rax+rax+00h]
0x180012542  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180012549  mov     rcx, rax
0x18001254c  test    rax, rax
0x18001254f  jnz     loc_180012872
0x180012555  mov     rcx, rsi
0x180012558  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001255f  jmp     loc_180012892
0x180012564  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001256b  test    rcx, rcx
0x18001256e  jnz     loc_1800128D3
0x180012574  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001257b  nop     dword ptr [rax+rax+00h]
0x180012580  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180012587  mov     rcx, rax
0x18001258a  test    rax, rax
0x18001258d  jnz     loc_1800128B3
0x180012593  mov     rcx, rsi
0x180012596  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001259d  jmp     loc_1800128D3
0x1800125a2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800125a9  test    rcx, rcx
0x1800125ac  jnz     loc_180012914
0x1800125b2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800125b9  nop     dword ptr [rax+rax+00h]
0x1800125be  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800125c5  mov     rcx, rax
0x1800125c8  test    rax, rax
0x1800125cb  jnz     loc_1800128F4
0x1800125d1  mov     rcx, rsi
0x1800125d4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800125db  jmp     loc_180012914
0x1800125e0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800125e7  mov     edi, 8007000Eh
0x1800125ec  test    rcx, rcx
0x1800125ef  jnz     loc_180012952
0x1800125f5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800125fc  nop     dword ptr [rax+rax+00h]
0x180012601  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180012608  mov     rcx, rax
0x18001260b  test    rax, rax
0x18001260e  jnz     loc_180012932
0x180012614  mov     rcx, rsi
0x180012617  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001261e  jmp     loc_180012952
0x180012623  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001262a  test    rcx, rcx
0x18001262d  jnz     loc_180012A19
0x180012633  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001263a  nop     dword ptr [rax+rax+00h]
0x18001263f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180012646  mov     rcx, rax
0x180012649  test    rax, rax
0x18001264c  jnz     loc_1800129F9
0x180012652  mov     rcx, rsi
0x180012655  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001265c  jmp     loc_180012A19
0x180012661  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180012666  cmp     [rax+7CCh], edi
0x18001266c  jz      loc_180012429
0x180012672  mov     r9d, edi; int
0x180012675  mov     r8d, 0CA7h; int
0x18001267b  mov     rdx, r14; char *
0x18001267e  mov     rcx, rax; this
0x180012681  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180012686  jmp     loc_180012429
0x18001268b  mov     rcx, rsi; this
0x18001268e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180012693  cmp     [rax+7CCh], edi
  ... truncated ...
```
