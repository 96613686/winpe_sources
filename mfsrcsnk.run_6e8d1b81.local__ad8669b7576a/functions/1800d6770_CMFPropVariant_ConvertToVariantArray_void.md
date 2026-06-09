# CMFPropVariant::ConvertToVariantArray(void)

- ea: `0x1800d6770`
- end: `0x1800d6fb7`
- name: `?ConvertToVariantArray@CMFPropVariant@@QEAAJXZ`
- size: `2119`
- prototype: `__int64 __fastcall(CMFPropVariant *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180024720`
- `0x1800a8760`

## callees

- `0x18000be28`
- `0x18000e0c0`
- `0x180010190`
- `0x18001105c`
- `0x18001303c`
- `0x180018b90`
- `0x180025548`
- `0x1800275f0`
- `0x180029a00`
- `0x180073b14`
- `0x1800b17a8`
- `0x1800c27f8`
- `0x1800d6770`
- `0x1801099f0`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d683a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d6919`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d69bd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d6a6c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d6b3b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d6bbe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d6c52`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d6ced`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d6d8d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d6e48`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d6efb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d683a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d6919`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d69bd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d6a6c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d6b3b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d6bbe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d6c52`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d6ced`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d6d8d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d6e48`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d6efb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d6812`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d6e20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d6812`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d6e20`

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
          v7 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            v26 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            v19 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v13 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v43 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v48 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v59 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v54 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
0x1800d6770  mov     [rsp-28h+arg_8], rbx
0x1800d6775  mov     [rsp-28h+arg_10], rsi
0x1800d677a  push    rbp
0x1800d677b  push    rdi
0x1800d677c  push    r12
0x1800d677e  push    r14
0x1800d6780  push    r15
0x1800d6782  mov     rbp, rsp
0x1800d6785  sub     rsp, 70h
0x1800d6789  mov     rax, cs:__security_cookie
0x1800d6790  xor     rax, rsp
0x1800d6793  mov     [rbp+var_8], rax
0x1800d6797  xor     eax, eax
0x1800d6799  lea     r12, aCmfpropvariant_17; "CMFPropVariant::ConvertToVariantArray"
0x1800d67a0  mov     rsi, rcx
0x1800d67a3  mov     qword ptr [rbp+pvarDest+10h], rax
0x1800d67a7  xorps   xmm0, xmm0
0x1800d67aa  mov     qword ptr [rbp+pvarSrc+10h], rax
0x1800d67ae  xorps   xmm1, xmm1
0x1800d67b1  lea     rcx, [rbp+var_40]; this
0x1800d67b5  xor     r15d, r15d
0x1800d67b8  mov     rdx, r12; char *
0x1800d67bb  mov     r8d, 635h; int
0x1800d67c1  mov     edi, r15d
0x1800d67c4  movups  xmmword ptr [rbp+pvarDest], xmm0
0x1800d67c8  movups  xmmword ptr [rbp+pvarSrc], xmm1
0x1800d67cc  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800d67d1  movzx   ecx, word ptr [rsi]
0x1800d67d4  mov     eax, 1000h
0x1800d67d9  and     cx, ax
0x1800d67dc  cmp     r15w, cx
0x1800d67e0  jz      short loc_1800D67FA
0x1800d67e2  movzx   eax, word ptr [rsi]
0x1800d67e5  mov     edx, 0FFFh
0x1800d67ea  and     ax, dx
0x1800d67ed  lea     edx, [r15+0Ch]
0x1800d67f1  cmp     dx, ax
0x1800d67f4  jz      loc_1800D6F7E
0x1800d67fa  cmp     r15w, [rsi]
0x1800d67fe  jnz     loc_1800D68ED
0x1800d6804  mov     ecx, 18h; cb
0x1800d6809  mov     word ptr [rsi], 100Ch
0x1800d680e  mov     [rsi+8], r15d
0x1800d6812  call    cs:__imp_CoTaskMemAlloc
0x1800d6818  mov     [rsi+10h], rax
0x1800d681c  test    rax, rax
0x1800d681f  jnz     loc_1800D68DC
0x1800d6825  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d682c  mov     r14d, 8007000Eh
0x1800d6832  mov     edi, r14d
0x1800d6835  test    rbx, rbx
0x1800d6838  jnz     short loc_1800D687B
0x1800d683a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d6840  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d6847  mov     rcx, rax
0x1800d684a  test    rax, rax
0x1800d684d  jz      short loc_1800D686D
0x1800d684f  mov     rax, [rax]
0x1800d6852  mov     edx, 7F0h
0x1800d6857  mov     rax, [rax+8]
0x1800d685b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6860  test    eax, eax
0x1800d6862  jz      short loc_1800D686D
0x1800d6864  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d686b  jmp     short loc_1800D687B
0x1800d686d  lea     rbx, qword_1801B07E0
0x1800d6874  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d687b  cmp     [rbx+8], r15b
0x1800d687f  jz      short loc_1800D68A6
0x1800d6881  mov     rcx, rbx; this
0x1800d6884  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d6889  cmp     [rax+7CCh], r14d
0x1800d6890  jz      short loc_1800D68A6
0x1800d6892  mov     r9d, r14d; int
0x1800d6895  mov     r8d, 64Eh; int
0x1800d689b  mov     rdx, r12; char *
0x1800d689e  mov     rcx, rax; this
0x1800d68a1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d68a6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d68ad  jb      loc_1800D6F7E
0x1800d68b3  mov     edx, 65h ; 'e'
0x1800d68b8  mov     [rsp+70h+var_50], r14d
0x1800d68bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d68c4  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x1800d68cb  mov     r9, rsi
0x1800d68ce  mov     rcx, [rcx+10h]
0x1800d68d2  call    WPP_SF_qD
0x1800d68d7  jmp     loc_1800D6F7E
0x1800d68dc  xorps   xmm0, xmm0
0x1800d68df  xor     ecx, ecx
0x1800d68e1  movups  xmmword ptr [rax], xmm0
0x1800d68e4  mov     [rax+10h], rcx
0x1800d68e8  jmp     loc_1800D6F7E
0x1800d68ed  cmp     r15w, cx
0x1800d68f1  mov     rdx, rsi; pvarSrc
0x1800d68f4  lea     rcx, [rbp+pvarDest]; pvarDest
0x1800d68f8  jz      loc_1800D6CD2
0x1800d68fe  call    ?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::Copy(tagPROPVARIANT const *)
0x1800d6903  mov     edi, eax
0x1800d6905  test    eax, eax
0x1800d6907  jns     loc_1800D699F
0x1800d690d  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d6914  test    rbx, rbx
0x1800d6917  jnz     short loc_1800D695A
0x1800d6919  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d691f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d6926  mov     rcx, rax
0x1800d6929  test    rax, rax
0x1800d692c  jz      short loc_1800D694C
0x1800d692e  mov     rax, [rax]
0x1800d6931  mov     edx, 7F0h
0x1800d6936  mov     rax, [rax+8]
0x1800d693a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d693f  test    eax, eax
0x1800d6941  jz      short loc_1800D694C
0x1800d6943  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d694a  jmp     short loc_1800D695A
0x1800d694c  lea     rbx, qword_1801B07E0
0x1800d6953  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d695a  cmp     [rbx+8], r15b
0x1800d695e  jz      short loc_1800D6984
0x1800d6960  mov     rcx, rbx; this
0x1800d6963  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d6968  cmp     [rax+7CCh], edi
0x1800d696e  jz      short loc_1800D6984
0x1800d6970  mov     r9d, edi; int
0x1800d6973  mov     r8d, 65Bh; int
0x1800d6979  mov     rdx, r12; char *
0x1800d697c  mov     rcx, rax; this
0x1800d697f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d6984  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d698b  jb      loc_1800D6F7E
0x1800d6991  mov     edx, 66h ; 'f'
0x1800d6996  mov     [rsp+70h+var_50], edi
0x1800d699a  jmp     loc_1800D68BD
0x1800d699f  mov     rcx, rsi; this
0x1800d69a2  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x1800d69a7  mov     edi, eax
0x1800d69a9  test    eax, eax
0x1800d69ab  jns     loc_1800D6A3F
0x1800d69b1  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d69b8  test    rbx, rbx
0x1800d69bb  jnz     short loc_1800D69FE
0x1800d69bd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d69c3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d69ca  mov     rcx, rax
0x1800d69cd  test    rax, rax
0x1800d69d0  jz      short loc_1800D69F0
0x1800d69d2  mov     rax, [rax]
0x1800d69d5  mov     edx, 7F0h
0x1800d69da  mov     rax, [rax+8]
0x1800d69de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d69e3  test    eax, eax
0x1800d69e5  jz      short loc_1800D69F0
0x1800d69e7  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d69ee  jmp     short loc_1800D69FE
0x1800d69f0  lea     rbx, qword_1801B07E0
0x1800d69f7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d69fe  cmp     [rbx+8], r15b
0x1800d6a02  jz      short loc_1800D6A28
0x1800d6a04  mov     rcx, rbx; this
0x1800d6a07  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d6a0c  cmp     [rax+7CCh], edi
0x1800d6a12  jz      short loc_1800D6A28
0x1800d6a14  mov     r9d, edi; int
0x1800d6a17  mov     r8d, 65Eh; int
0x1800d6a1d  mov     rdx, r12; char *
0x1800d6a20  mov     rcx, rax; this
0x1800d6a23  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d6a28  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d6a2f  jb      loc_1800D6F7E
0x1800d6a35  mov     edx, 67h ; 'g'
0x1800d6a3a  jmp     loc_1800D6996
0x1800d6a3f  lea     rcx, [rbp+pvarDest]; this
0x1800d6a43  call    ?GetElementCount@CMFPropVariant@@QEBAKXZ; CMFPropVariant::GetElementCount(void)
0x1800d6a48  mov     r8d, eax; unsigned int
0x1800d6a4b  mov     rcx, rsi; this
0x1800d6a4e  mov     r14d, eax
0x1800d6a51  call    ?CreateUnSetArray@CMFPropVariant@@QEAAJGK@Z; CMFPropVariant::CreateUnSetArray(ushort,ulong)
0x1800d6a56  mov     edi, eax
0x1800d6a58  test    eax, eax
0x1800d6a5a  jns     loc_1800D6AEE
0x1800d6a60  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d6a67  test    rbx, rbx
0x1800d6a6a  jnz     short loc_1800D6AAD
0x1800d6a6c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d6a72  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d6a79  mov     rcx, rax
0x1800d6a7c  test    rax, rax
0x1800d6a7f  jz      short loc_1800D6A9F
0x1800d6a81  mov     rax, [rax]
0x1800d6a84  mov     edx, 7F0h
0x1800d6a89  mov     rax, [rax+8]
0x1800d6a8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6a92  test    eax, eax
0x1800d6a94  jz      short loc_1800D6A9F
0x1800d6a96  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d6a9d  jmp     short loc_1800D6AAD
0x1800d6a9f  lea     rbx, qword_1801B07E0
0x1800d6aa6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d6aad  cmp     [rbx+8], r15b
0x1800d6ab1  jz      short loc_1800D6AD7
0x1800d6ab3  mov     rcx, rbx; this
0x1800d6ab6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d6abb  cmp     [rax+7CCh], edi
0x1800d6ac1  jz      short loc_1800D6AD7
0x1800d6ac3  mov     r9d, edi; int
0x1800d6ac6  mov     r8d, 666h; int
0x1800d6acc  mov     rdx, r12; char *
0x1800d6acf  mov     rcx, rax; this
0x1800d6ad2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d6ad7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d6ade  jb      loc_1800D6F7E
0x1800d6ae4  mov     edx, 68h ; 'h'
0x1800d6ae9  jmp     loc_1800D6996
0x1800d6aee  mov     ebx, r15d
0x1800d6af1  lea     rcx, [rbp+pvarDest]; this
0x1800d6af5  cmp     r14d, ebx
0x1800d6af8  jbe     loc_1800D6CC8
0x1800d6afe  lea     r8, [rbp+pvarSrc]; struct tagPROPVARIANT *
0x1800d6b02  mov     edx, ebx; unsigned int
0x1800d6b04  call    ?GetElementDataAsVariant@CMFPropVariant@@IEBAJKPEAUtagPROPVARIANT@@@Z; CMFPropVariant::GetElementDataAsVariant(ulong,tagPROPVARIANT *)
0x1800d6b09  mov     edi, eax
0x1800d6b0b  test    eax, eax
0x1800d6b0d  js      loc_1800D6BAE
0x1800d6b13  lea     r8, [rbp+pvarSrc]; pvarSrc
0x1800d6b17  mov     edx, ebx; unsigned int
0x1800d6b19  mov     rcx, rsi; this
0x1800d6b1c  call    ?SetElement@CMFPropVariant@@QEAAJKPEBUtagPROPVARIANT@@@Z; CMFPropVariant::SetElement(ulong,tagPROPVARIANT const *)
0x1800d6b21  mov     edi, eax
0x1800d6b23  test    eax, eax
0x1800d6b25  js      short loc_1800D6B2B
0x1800d6b27  inc     ebx
0x1800d6b29  jmp     short loc_1800D6AF1
0x1800d6b2b  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r15; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d6b32  lea     rbx, qword_1801B07E0
0x1800d6b39  jnz     short loc_1800D6B6C
0x1800d6b3b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d6b41  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d6b48  mov     rcx, rax
0x1800d6b4b  test    rax, rax
0x1800d6b4e  jz      short loc_1800D6B65
0x1800d6b50  mov     rax, [rax]
0x1800d6b53  mov     edx, 7F0h
0x1800d6b58  mov     rax, [rax+8]
0x1800d6b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6b61  test    eax, eax
0x1800d6b63  jnz     short loc_1800D6B6C
0x1800d6b65  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d6b6c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800d6b73  cmp     [rcx+8], r15b
0x1800d6b77  jz      short loc_1800D6B9A
0x1800d6b79  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d6b7e  cmp     [rax+7CCh], edi
0x1800d6b84  jz      short loc_1800D6B9A
0x1800d6b86  mov     r9d, edi; int
0x1800d6b89  mov     r8d, 675h; int
0x1800d6b8f  mov     rdx, r12; char *
0x1800d6b92  mov     rcx, rax; this
0x1800d6b95  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d6b9a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d6ba1  jb      loc_1800D6C49
0x1800d6ba7  mov     edx, 6Ah ; 'j'
0x1800d6bac  jmp     short loc_1800D6C2B
0x1800d6bae  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r15; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d6bb5  lea     rbx, qword_1801B07E0
0x1800d6bbc  jnz     short loc_1800D6BEF
0x1800d6bbe  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d6bc4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d6bcb  mov     rcx, rax
0x1800d6bce  test    rax, rax
0x1800d6bd1  jz      short loc_1800D6BE8
0x1800d6bd3  mov     rax, [rax]
0x1800d6bd6  mov     edx, 7F0h
0x1800d6bdb  mov     rax, [rax+8]
0x1800d6bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6be4  test    eax, eax
0x1800d6be6  jnz     short loc_1800D6BEF
0x1800d6be8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d6bef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800d6bf6  cmp     [rcx+8], r15b
0x1800d6bfa  jz      short loc_1800D6C1D
0x1800d6bfc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d6c01  cmp     [rax+7CCh], edi
0x1800d6c07  jz      short loc_1800D6C1D
0x1800d6c09  mov     r9d, edi; int
0x1800d6c0c  mov     r8d, 66Eh; int
0x1800d6c12  mov     rdx, r12; char *
0x1800d6c15  mov     rcx, rax; this
0x1800d6c18  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d6c1d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d6c24  jb      short loc_1800D6C49
0x1800d6c26  mov     edx, 69h ; 'i'
0x1800d6c2b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d6c32  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x1800d6c39  mov     r9, rsi
0x1800d6c3c  mov     [rsp+70h+var_50], edi
0x1800d6c40  mov     rcx, [rcx+10h]
0x1800d6c44  call    WPP_SF_qD
0x1800d6c49  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r15; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
