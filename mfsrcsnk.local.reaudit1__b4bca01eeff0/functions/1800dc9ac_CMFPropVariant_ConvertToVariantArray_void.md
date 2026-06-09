# CMFPropVariant::ConvertToVariantArray(void)

- ea: `0x1800dc9ac`
- end: `0x1800dd245`
- name: `?ConvertToVariantArray@CMFPropVariant@@QEAAJXZ`
- size: `2201`
- prototype: `__int64 __fastcall(CMFPropVariant *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180010140`
- `0x1800ad900`

## callees

- `0x180005cf4`
- `0x180010fc4`
- `0x180013110`
- `0x1800153e4`
- `0x180016f60`
- `0x180019264`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180079680`
- `0x1800b6db0`
- `0x1800c8690`
- `0x1800dc9ac`
- `0x180110ed0`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dca7c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dcb61`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dcc0b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dccc0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dcd95`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dce21`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dcebb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dcf5c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dd002`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dd0c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dd182`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dca7c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dcb61`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dcc0b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dccc0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dcd95`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dce21`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dcebb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dcf5c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dd002`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dd0c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dd182`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800dca4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800dd09b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800dca4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800dd09b`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::ConvertToVariantArray(CMFPropVariant *this)
{
  int UnSetArray; // edi
  __int16 v3; // cx
  _QWORD *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  wchar_t *v7; // rbx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rcx
  wchar_t *v13; // rbx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rcx
  wchar_t *v19; // rbx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  unsigned int ElementCount; // r14d
  unsigned __int16 v23; // dx
  __int64 v24; // rdx
  __int64 v25; // rcx
  wchar_t *v26; // rbx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  unsigned int i; // ebx
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // rcx
  CallStackTracing *v33; // rax
  CallStackTracing *v34; // rcx
  struct CallStackContext *v35; // rax
  __int64 v36; // rdx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  __int64 v41; // rdx
  __int64 v42; // rcx
  wchar_t *v43; // rbx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  __int64 v46; // rdx
  __int64 v47; // rcx
  wchar_t *v48; // rbx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  _QWORD *v51; // rax
  __int64 v52; // rdx
  __int64 v53; // rcx
  wchar_t *v54; // rbx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  __int64 v57; // rdx
  __int64 v58; // rcx
  wchar_t *v59; // rbx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  _BYTE v63[8]; // [rsp+30h] [rbp-40h] BYREF
  PROPVARIANT pvarDest; // [rsp+38h] [rbp-38h] BYREF
  PROPVARIANT pvarSrc; // [rsp+50h] [rbp-20h] BYREF

  UnSetArray = 0;
  memset(&pvarDest, 0, sizeof(pvarDest));
  memset(&pvarSrc, 0, sizeof(pvarSrc));
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v63, "CMFPropVariant::ConvertToVariantArray", 1589);
  v3 = *(_WORD *)this & 0x1000;
  if ( v3 && (*(_WORD *)this & 0xFFF) == 0xC )
    goto LABEL_132;
  if ( !*(_WORD *)this )
  {
    *(_WORD *)this = 4108;
    *((_DWORD *)this + 2) = 0;
    v4 = CoTaskMemAlloc(0x18u);
    *((_QWORD *)this + 2) = v4;
    if ( v4 )
    {
      *(_OWORD *)v4 = 0;
      v4[2] = 0;
    }
    else
    {
      v7 = (wchar_t *)CallStackTracing::s_wpInstance;
      UnSetArray = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v6, v5);
        CallStackTracing::s_wpInstance = v8;
        if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
        {
          v7 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v7 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v7 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CMFPropVariant::ConvertToVariantArray",
            1614,
            -2147024882);
      }
      if ( g_wppLevels )
      {
        v10 = 101;
LABEL_15:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v10,
          WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
          this,
          -2147024882);
        goto LABEL_132;
      }
    }
    goto LABEL_132;
  }
  if ( v3 )
  {
    UnSetArray = CMFPropVariant::Copy(&pvarDest, (PROPVARIANT *)this);
    if ( UnSetArray >= 0 )
    {
      UnSetArray = CMFPropVariant::Clear((PROPVARIANT *)this);
      if ( UnSetArray >= 0 )
      {
        ElementCount = CMFPropVariant::GetElementCount((CMFPropVariant *)&pvarDest);
        UnSetArray = CMFPropVariant::CreateUnSetArray(this, v23, ElementCount);
        if ( UnSetArray >= 0 )
        {
          for ( i = 0; ; ++i )
          {
            if ( ElementCount <= i )
            {
              CMFPropVariant::Clear(&pvarDest);
              goto LABEL_132;
            }
            UnSetArray = CMFPropVariant::GetElementDataAsVariant((CMFPropVariant *)&pvarDest, i, &pvarSrc);
            if ( UnSetArray < 0 )
              break;
            UnSetArray = CMFPropVariant::SetElement(this, i, &pvarSrc);
            if ( UnSetArray < 0 )
            {
              if ( !CallStackTracing::s_wpInstance )
              {
                v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v32, v30);
                CallStackTracing::s_wpInstance = v33;
                if ( !v33
                  || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
                {
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                }
              }
              v34 = CallStackTracing::s_wpInstance;
              if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
              {
                v35 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
                if ( *((_DWORD *)v35 + 499) != UnSetArray )
                  CallStackContext::TraceFailure(v35, "CMFPropVariant::ConvertToVariantArray", 1653, UnSetArray);
              }
              if ( g_wppLevels )
              {
                v36 = 106;
LABEL_76:
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v36,
                  WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
                  this,
                  UnSetArray);
                goto LABEL_77;
              }
              goto LABEL_77;
            }
          }
          if ( !CallStackTracing::s_wpInstance )
          {
            v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v31, v30);
            CallStackTracing::s_wpInstance = v37;
            if ( !v37
              || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
            {
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          v34 = CallStackTracing::s_wpInstance;
          if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
          {
            v38 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
            if ( *((_DWORD *)v38 + 499) != UnSetArray )
              CallStackContext::TraceFailure(v38, "CMFPropVariant::ConvertToVariantArray", 1646, UnSetArray);
          }
          if ( g_wppLevels )
          {
            v36 = 105;
            goto LABEL_76;
          }
LABEL_77:
          if ( !CallStackTracing::s_wpInstance )
          {
            v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v34, v30);
            CallStackTracing::s_wpInstance = v39;
            if ( !v39
              || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
            {
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
          {
            v40 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
            if ( *((_DWORD *)v40 + 499) != UnSetArray )
              CallStackContext::TraceFailure(v40, "CMFPropVariant::ConvertToVariantArray", 1655, UnSetArray);
          }
          if ( g_wppLevels )
          {
            v16 = 107;
            goto LABEL_30;
          }
          goto LABEL_132;
        }
        v26 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v25, v24);
          CallStackTracing::s_wpInstance = v27;
          if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
          {
            v26 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v26 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v26 + 8) )
        {
          v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
          if ( *((_DWORD *)v28 + 499) != UnSetArray )
            CallStackContext::TraceFailure(v28, "CMFPropVariant::ConvertToVariantArray", 1638, UnSetArray);
        }
        if ( !g_wppLevels )
          goto LABEL_132;
        v16 = 104;
      }
      else
      {
        v19 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v18, v17);
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
          v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
          if ( *((_DWORD *)v21 + 499) != UnSetArray )
            CallStackContext::TraceFailure(v21, "CMFPropVariant::ConvertToVariantArray", 1630, UnSetArray);
        }
        if ( !g_wppLevels )
          goto LABEL_132;
        v16 = 103;
      }
    }
    else
    {
      v13 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v12, v11);
        CallStackTracing::s_wpInstance = v14;
        if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
        {
          v13 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v13 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v13 + 8) )
      {
        v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
        if ( *((_DWORD *)v15 + 499) != UnSetArray )
          CallStackContext::TraceFailure(v15, "CMFPropVariant::ConvertToVariantArray", 1627, UnSetArray);
      }
      if ( !g_wppLevels )
        goto LABEL_132;
      v16 = 102;
    }
LABEL_30:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v16,
      WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
      this,
      UnSetArray);
    goto LABEL_132;
  }
  UnSetArray = CMFPropVariant::Copy(&pvarDest, (PROPVARIANT *)this);
  if ( UnSetArray < 0 )
  {
    v43 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v42, v41);
      CallStackTracing::s_wpInstance = v44;
      if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
      {
        v43 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v43 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v43 + 8) )
    {
      v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
      if ( *((_DWORD *)v45 + 499) != UnSetArray )
        CallStackContext::TraceFailure(v45, "CMFPropVariant::ConvertToVariantArray", 1668, UnSetArray);
    }
    if ( !g_wppLevels )
      goto LABEL_132;
    v16 = 108;
    goto LABEL_30;
  }
  UnSetArray = CMFPropVariant::Clear((PROPVARIANT *)this);
  if ( UnSetArray < 0 )
  {
    v48 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v47, v46);
      CallStackTracing::s_wpInstance = v49;
      if ( v49 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
      {
        v48 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v48 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v48 + 8) )
    {
      v50 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v48);
      if ( *((_DWORD *)v50 + 499) != UnSetArray )
        CallStackContext::TraceFailure(v50, "CMFPropVariant::ConvertToVariantArray", 1674, UnSetArray);
    }
    if ( !g_wppLevels )
      goto LABEL_132;
    v16 = 109;
    goto LABEL_30;
  }
  *(_WORD *)this = 4108;
  *((_DWORD *)this + 2) = 1;
  v51 = CoTaskMemAlloc(0x18u);
  *((_QWORD *)this + 2) = v51;
  if ( v51 )
  {
    *(_OWORD *)v51 = 0;
    v51[2] = 0;
    UnSetArray = CMFPropVariant::SetElementData(this, 0, &pvarDest);
    if ( UnSetArray >= 0 )
    {
      pvarDest.vt = 0;
      goto LABEL_132;
    }
    v59 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v58, v57);
      CallStackTracing::s_wpInstance = v60;
      if ( v60 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
      {
        v59 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v59 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v59 + 8) )
    {
      v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
      if ( *((_DWORD *)v61 + 499) != UnSetArray )
        CallStackContext::TraceFailure(v61, "CMFPropVariant::ConvertToVariantArray", 1693, UnSetArray);
    }
    if ( g_wppLevels )
    {
      v16 = 111;
      goto LABEL_30;
    }
  }
  else
  {
    v54 = (wchar_t *)CallStackTracing::s_wpInstance;
    UnSetArray = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v53, v52);
      CallStackTracing::s_wpInstance = v55;
      if ( v55 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
      {
        v54 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v54 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v54 + 8) )
    {
      v56 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
      if ( *((_DWORD *)v56 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v56, "CMFPropVariant::ConvertToVariantArray", 1686, -2147024882);
    }
    if ( g_wppLevels )
    {
      v10 = 110;
      goto LABEL_15;
    }
  }
LABEL_132:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v63);
  CMFPropVariant::Clear(&pvarDest);
  return (unsigned int)UnSetArray;
}

```

## disassembly

```asm
0x1800dc9ac  mov     [rsp-28h+arg_8], rbx
0x1800dc9b1  mov     [rsp-28h+arg_10], rsi
0x1800dc9b6  push    rbp
0x1800dc9b7  push    rdi
0x1800dc9b8  push    r12
0x1800dc9ba  push    r14
0x1800dc9bc  push    r15
0x1800dc9be  mov     rbp, rsp
0x1800dc9c1  sub     rsp, 70h
0x1800dc9c5  mov     rax, cs:__security_cookie
0x1800dc9cc  xor     rax, rsp
0x1800dc9cf  mov     [rbp+var_8], rax
0x1800dc9d3  xor     eax, eax
0x1800dc9d5  lea     r12, aCmfpropvariant_17; "CMFPropVariant::ConvertToVariantArray"
0x1800dc9dc  mov     rsi, rcx
0x1800dc9df  mov     qword ptr [rbp+pvarDest+10h], rax
0x1800dc9e3  xorps   xmm0, xmm0
0x1800dc9e6  mov     qword ptr [rbp+pvarSrc+10h], rax
0x1800dc9ea  xorps   xmm1, xmm1
0x1800dc9ed  lea     rcx, [rbp+var_40]; this
0x1800dc9f1  xor     r15d, r15d
0x1800dc9f4  mov     rdx, r12; char *
0x1800dc9f7  mov     r8d, 635h; int
0x1800dc9fd  mov     edi, r15d
0x1800dca00  movups  xmmword ptr [rbp+pvarDest], xmm0
0x1800dca04  movups  xmmword ptr [rbp+pvarSrc], xmm1
0x1800dca08  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800dca0d  movzx   ecx, word ptr [rsi]
0x1800dca10  mov     eax, 1000h
0x1800dca15  and     cx, ax
0x1800dca18  cmp     r15w, cx
0x1800dca1c  jz      short loc_1800DCA36
0x1800dca1e  movzx   eax, word ptr [rsi]
0x1800dca21  mov     edx, 0FFFh
0x1800dca26  and     ax, dx
0x1800dca29  lea     edx, [r15+0Ch]
0x1800dca2d  cmp     dx, ax
0x1800dca30  jz      loc_1800DD20B
0x1800dca36  cmp     r15w, [rsi]
0x1800dca3a  jnz     loc_1800DCB35
0x1800dca40  mov     ecx, 18h; cb
0x1800dca45  mov     word ptr [rsi], 100Ch
0x1800dca4a  mov     [rsi+8], r15d
0x1800dca4e  call    cs:__imp_CoTaskMemAlloc
0x1800dca55  nop     dword ptr [rax+rax+00h]
0x1800dca5a  mov     [rsi+10h], rax
0x1800dca5e  test    rax, rax
0x1800dca61  jnz     loc_1800DCB24
0x1800dca67  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dca6e  mov     r14d, 8007000Eh
0x1800dca74  mov     edi, r14d
0x1800dca77  test    rbx, rbx
0x1800dca7a  jnz     short loc_1800DCAC3
0x1800dca7c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800dca83  nop     dword ptr [rax+rax+00h]
0x1800dca88  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dca8f  mov     rcx, rax
0x1800dca92  test    rax, rax
0x1800dca95  jz      short loc_1800DCAB5
0x1800dca97  mov     rax, [rax]
0x1800dca9a  mov     edx, 7F0h
0x1800dca9f  mov     rax, [rax+8]
0x1800dcaa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dcaa8  test    eax, eax
0x1800dcaaa  jz      short loc_1800DCAB5
0x1800dcaac  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dcab3  jmp     short loc_1800DCAC3
0x1800dcab5  lea     rbx, qword_1801B97E0
0x1800dcabc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dcac3  cmp     [rbx+8], r15b
0x1800dcac7  jz      short loc_1800DCAEE
0x1800dcac9  mov     rcx, rbx; this
0x1800dcacc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800dcad1  cmp     [rax+7CCh], r14d
0x1800dcad8  jz      short loc_1800DCAEE
0x1800dcada  mov     r9d, r14d; int
0x1800dcadd  mov     r8d, 64Eh; int
0x1800dcae3  mov     rdx, r12; char *
0x1800dcae6  mov     rcx, rax; this
0x1800dcae9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800dcaee  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800dcaf5  jb      loc_1800DD20B
0x1800dcafb  mov     edx, 65h ; 'e'
0x1800dcb00  mov     [rsp+70h+var_50], r14d
0x1800dcb05  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dcb0c  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x1800dcb13  mov     r9, rsi
0x1800dcb16  mov     rcx, [rcx+10h]
0x1800dcb1a  call    WPP_SF_qD
0x1800dcb1f  jmp     loc_1800DD20B
0x1800dcb24  xorps   xmm0, xmm0
0x1800dcb27  xor     ecx, ecx
0x1800dcb29  movups  xmmword ptr [rax], xmm0
0x1800dcb2c  mov     [rax+10h], rcx
0x1800dcb30  jmp     loc_1800DD20B
0x1800dcb35  cmp     r15w, cx
0x1800dcb39  mov     rdx, rsi; pvarSrc
0x1800dcb3c  lea     rcx, [rbp+pvarDest]; pvarDest
0x1800dcb40  jz      loc_1800DCF41
0x1800dcb46  call    ?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::Copy(tagPROPVARIANT const *)
0x1800dcb4b  mov     edi, eax
0x1800dcb4d  test    eax, eax
0x1800dcb4f  jns     loc_1800DCBED
0x1800dcb55  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dcb5c  test    rbx, rbx
0x1800dcb5f  jnz     short loc_1800DCBA8
0x1800dcb61  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800dcb68  nop     dword ptr [rax+rax+00h]
0x1800dcb6d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dcb74  mov     rcx, rax
0x1800dcb77  test    rax, rax
0x1800dcb7a  jz      short loc_1800DCB9A
0x1800dcb7c  mov     rax, [rax]
0x1800dcb7f  mov     edx, 7F0h
0x1800dcb84  mov     rax, [rax+8]
0x1800dcb88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dcb8d  test    eax, eax
0x1800dcb8f  jz      short loc_1800DCB9A
0x1800dcb91  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dcb98  jmp     short loc_1800DCBA8
0x1800dcb9a  lea     rbx, qword_1801B97E0
0x1800dcba1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dcba8  cmp     [rbx+8], r15b
0x1800dcbac  jz      short loc_1800DCBD2
0x1800dcbae  mov     rcx, rbx; this
0x1800dcbb1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800dcbb6  cmp     [rax+7CCh], edi
0x1800dcbbc  jz      short loc_1800DCBD2
0x1800dcbbe  mov     r9d, edi; int
0x1800dcbc1  mov     r8d, 65Bh; int
0x1800dcbc7  mov     rdx, r12; char *
0x1800dcbca  mov     rcx, rax; this
0x1800dcbcd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800dcbd2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800dcbd9  jb      loc_1800DD20B
0x1800dcbdf  mov     edx, 66h ; 'f'
0x1800dcbe4  mov     [rsp+70h+var_50], edi
0x1800dcbe8  jmp     loc_1800DCB05
0x1800dcbed  mov     rcx, rsi; pvar
0x1800dcbf0  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x1800dcbf5  mov     edi, eax
0x1800dcbf7  test    eax, eax
0x1800dcbf9  jns     loc_1800DCC93
0x1800dcbff  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dcc06  test    rbx, rbx
0x1800dcc09  jnz     short loc_1800DCC52
0x1800dcc0b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800dcc12  nop     dword ptr [rax+rax+00h]
0x1800dcc17  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dcc1e  mov     rcx, rax
0x1800dcc21  test    rax, rax
0x1800dcc24  jz      short loc_1800DCC44
0x1800dcc26  mov     rax, [rax]
0x1800dcc29  mov     edx, 7F0h
0x1800dcc2e  mov     rax, [rax+8]
0x1800dcc32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dcc37  test    eax, eax
0x1800dcc39  jz      short loc_1800DCC44
0x1800dcc3b  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dcc42  jmp     short loc_1800DCC52
0x1800dcc44  lea     rbx, qword_1801B97E0
0x1800dcc4b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dcc52  cmp     [rbx+8], r15b
0x1800dcc56  jz      short loc_1800DCC7C
0x1800dcc58  mov     rcx, rbx; this
0x1800dcc5b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800dcc60  cmp     [rax+7CCh], edi
0x1800dcc66  jz      short loc_1800DCC7C
0x1800dcc68  mov     r9d, edi; int
0x1800dcc6b  mov     r8d, 65Eh; int
0x1800dcc71  mov     rdx, r12; char *
0x1800dcc74  mov     rcx, rax; this
0x1800dcc77  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800dcc7c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800dcc83  jb      loc_1800DD20B
0x1800dcc89  mov     edx, 67h ; 'g'
0x1800dcc8e  jmp     loc_1800DCBE4
0x1800dcc93  lea     rcx, [rbp+pvarDest]; this
0x1800dcc97  call    ?GetElementCount@CMFPropVariant@@QEBAKXZ; CMFPropVariant::GetElementCount(void)
0x1800dcc9c  mov     r8d, eax; unsigned int
0x1800dcc9f  mov     rcx, rsi; this
0x1800dcca2  mov     r14d, eax
0x1800dcca5  call    ?CreateUnSetArray@CMFPropVariant@@QEAAJGK@Z; CMFPropVariant::CreateUnSetArray(ushort,ulong)
0x1800dccaa  mov     edi, eax
0x1800dccac  test    eax, eax
0x1800dccae  jns     loc_1800DCD48
0x1800dccb4  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dccbb  test    rbx, rbx
0x1800dccbe  jnz     short loc_1800DCD07
0x1800dccc0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800dccc7  nop     dword ptr [rax+rax+00h]
0x1800dcccc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dccd3  mov     rcx, rax
0x1800dccd6  test    rax, rax
0x1800dccd9  jz      short loc_1800DCCF9
0x1800dccdb  mov     rax, [rax]
0x1800dccde  mov     edx, 7F0h
0x1800dcce3  mov     rax, [rax+8]
0x1800dcce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dccec  test    eax, eax
0x1800dccee  jz      short loc_1800DCCF9
0x1800dccf0  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dccf7  jmp     short loc_1800DCD07
0x1800dccf9  lea     rbx, qword_1801B97E0
0x1800dcd00  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dcd07  cmp     [rbx+8], r15b
0x1800dcd0b  jz      short loc_1800DCD31
0x1800dcd0d  mov     rcx, rbx; this
0x1800dcd10  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800dcd15  cmp     [rax+7CCh], edi
0x1800dcd1b  jz      short loc_1800DCD31
0x1800dcd1d  mov     r9d, edi; int
0x1800dcd20  mov     r8d, 666h; int
0x1800dcd26  mov     rdx, r12; char *
0x1800dcd29  mov     rcx, rax; this
0x1800dcd2c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800dcd31  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800dcd38  jb      loc_1800DD20B
0x1800dcd3e  mov     edx, 68h ; 'h'
0x1800dcd43  jmp     loc_1800DCBE4
0x1800dcd48  mov     ebx, r15d
0x1800dcd4b  lea     rcx, [rbp+pvarDest]; pvar
0x1800dcd4f  cmp     r14d, ebx
0x1800dcd52  jbe     loc_1800DCF37
0x1800dcd58  lea     r8, [rbp+pvarSrc]; struct tagPROPVARIANT *
0x1800dcd5c  mov     edx, ebx; unsigned int
0x1800dcd5e  call    ?GetElementDataAsVariant@CMFPropVariant@@IEBAJKPEAUtagPROPVARIANT@@@Z; CMFPropVariant::GetElementDataAsVariant(ulong,tagPROPVARIANT *)
0x1800dcd63  mov     edi, eax
0x1800dcd65  test    eax, eax
0x1800dcd67  js      loc_1800DCE11
0x1800dcd6d  lea     r8, [rbp+pvarSrc]; pvarSrc
0x1800dcd71  mov     edx, ebx; unsigned int
0x1800dcd73  mov     rcx, rsi; this
0x1800dcd76  call    ?SetElement@CMFPropVariant@@QEAAJKPEBUtagPROPVARIANT@@@Z; CMFPropVariant::SetElement(ulong,tagPROPVARIANT const *)
0x1800dcd7b  mov     edi, eax
0x1800dcd7d  test    eax, eax
0x1800dcd7f  js      short loc_1800DCD85
0x1800dcd81  inc     ebx
0x1800dcd83  jmp     short loc_1800DCD4B
0x1800dcd85  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r15; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dcd8c  lea     rbx, qword_1801B97E0
0x1800dcd93  jnz     short loc_1800DCDCC
0x1800dcd95  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800dcd9c  nop     dword ptr [rax+rax+00h]
0x1800dcda1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dcda8  mov     rcx, rax
0x1800dcdab  test    rax, rax
0x1800dcdae  jz      short loc_1800DCDC5
0x1800dcdb0  mov     rax, [rax]
0x1800dcdb3  mov     edx, 7F0h
0x1800dcdb8  mov     rax, [rax+8]
0x1800dcdbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dcdc1  test    eax, eax
0x1800dcdc3  jnz     short loc_1800DCDCC
0x1800dcdc5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dcdcc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800dcdd3  cmp     [rcx+8], r15b
0x1800dcdd7  jz      short loc_1800DCDFA
0x1800dcdd9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800dcdde  cmp     [rax+7CCh], edi
0x1800dcde4  jz      short loc_1800DCDFA
0x1800dcde6  mov     r9d, edi; int
0x1800dcde9  mov     r8d, 675h; int
0x1800dcdef  mov     rdx, r12; char *
0x1800dcdf2  mov     rcx, rax; this
0x1800dcdf5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800dcdfa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800dce01  jb      loc_1800DCEB2
0x1800dce07  mov     edx, 6Ah ; 'j'
0x1800dce0c  jmp     loc_1800DCE94
0x1800dce11  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r15; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dce18  lea     rbx, qword_1801B97E0
0x1800dce1f  jnz     short loc_1800DCE58
0x1800dce21  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800dce28  nop     dword ptr [rax+rax+00h]
0x1800dce2d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dce34  mov     rcx, rax
0x1800dce37  test    rax, rax
0x1800dce3a  jz      short loc_1800DCE51
0x1800dce3c  mov     rax, [rax]
0x1800dce3f  mov     edx, 7F0h
0x1800dce44  mov     rax, [rax+8]
0x1800dce48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dce4d  test    eax, eax
0x1800dce4f  jnz     short loc_1800DCE58
0x1800dce51  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800dce58  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800dce5f  cmp     [rcx+8], r15b
0x1800dce63  jz      short loc_1800DCE86
0x1800dce65  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800dce6a  cmp     [rax+7CCh], edi
0x1800dce70  jz      short loc_1800DCE86
0x1800dce72  mov     r9d, edi; int
0x1800dce75  mov     r8d, 66Eh; int
0x1800dce7b  mov     rdx, r12; char *
0x1800dce7e  mov     rcx, rax; this
0x1800dce81  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800dce86  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800dce8d  jb      short loc_1800DCEB2
0x1800dce8f  mov     edx, 69h ; 'i'
  ... truncated ...
```
