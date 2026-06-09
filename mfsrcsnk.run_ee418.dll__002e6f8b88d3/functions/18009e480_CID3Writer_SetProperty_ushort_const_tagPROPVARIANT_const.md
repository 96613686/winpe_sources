# CID3Writer::SetProperty(ushort const *,tagPROPVARIANT const *)

- ea: `0x18009e480`
- end: `0x18009ec6f`
- name: `?SetProperty@CID3Writer@@UEAAJPEBGPEBUtagPROPVARIANT@@@Z`
- size: `2031`
- prototype: `int(CID3Writer *__hidden this, const unsigned __int16 *, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18011f140`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x180012a20`
- `0x18001303c`
- `0x180018b90`
- `0x180042450`
- `0x180073b14`
- `0x180074054`
- `0x18009e480`
- `0x18009ec78`
- `0x18010959c`
- `0x1801095e8`
- `0x1801099f0`
- `0x180123158`
- `0x180123b88`
- `0x180123cd0`
- `0x1801240a8`
- `0x1801723ec`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e528`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e5e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e6ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e775`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e81c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e90d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009ea66`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009eb09`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009eb9f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e528`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e5e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e6ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e775`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e81c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e90d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009ea66`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009eb09`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009eb9f`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18009e50c`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18009e8f1`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18009e50c`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18009e8f1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18009e4ff`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18009e4ff`

## string_xrefs

- `0x18009e4ae`: `CID3Writer::SetProperty`
- `0x18009e57f`: `CID3Writer::SetProperty`
- `0x18009e63a`: `CID3Writer::SetProperty`
- `0x18009e702`: `CID3Writer::SetProperty`
- `0x18009e7cc`: `CID3Writer::SetProperty`
- `0x18009e873`: `CID3Writer::SetProperty`
- `0x18009e964`: `CID3Writer::SetProperty`
- `0x18009eabd`: `CID3Writer::SetProperty`
- `0x18009eb60`: `CID3Writer::SetProperty`
- `0x18009ebf6`: `CID3Writer::SetProperty`

## pseudocode

```c
__int64 __fastcall CID3Writer::SetProperty(
        CID3Writer *this,
        const unsigned __int16 *a2,
        const struct tagPROPVARIANT *a3)
{
  char *v6; // r14
  unsigned int PropertyIndex; // eax
  __int64 v8; // r15
  __int64 v9; // rdx
  HRESULT v10; // edi
  __int64 v11; // r8
  __int64 v12; // r9
  wchar_t *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v16; // rdx
  void *v17; // rcx
  wchar_t *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  int v28; // r13d
  char *v29; // rdi
  void *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // r9
  wchar_t *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rdi
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // r9
  _QWORD *v48; // rsi
  __int64 v49; // rdi
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // r9
  wchar_t *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  __int64 v56; // r13
  const wchar_t *bstrVal; // rax
  __int64 v58; // rdx
  __int64 v59; // r8
  __int64 v60; // r9
  int v61; // ecx
  int v62; // ecx
  wchar_t *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  __int64 v66; // rdx
  __int64 v67; // rdx
  __int64 v68; // r8
  __int64 v69; // r9
  wchar_t *v70; // rcx
  CallStackTracing *v71; // rax
  struct CallStackContext *v72; // rax
  wchar_t *v73; // rcx
  CallStackTracing *v74; // rax
  struct CallStackContext *v75; // rax
  _BYTE v77[8]; // [rsp+30h] [rbp-30h] BYREF
  void *Block; // [rsp+38h] [rbp-28h] BYREF
  PROPVARIANT pvarDest; // [rsp+40h] [rbp-20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v77, "CID3Writer::SetProperty", 224);
  v6 = (char *)this - 8;
  Block = 0;
  memset(&pvarDest, 0, sizeof(pvarDest));
  PropertyIndex = CID3Writer::FindPropertyIndex((CID3Writer *)((char *)this - 8), a2);
  v8 = PropertyIndex;
  if ( PropertyIndex != -1 )
  {
    PropVariantClear((PROPVARIANT *)(*((_QWORD *)this + 8) + 24LL * PropertyIndex));
    v10 = PropVariantCopy(&pvarDest, a3);
    if ( v10 < 0 )
    {
      v13 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v11, v12);
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
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v10 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CID3Writer::SetProperty", 235, v10);
      }
      if ( g_wppLevels )
      {
        v16 = 17;
LABEL_37:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_02bf30fd61593fcad53f801c1bfe75a2_Traceguids, v6, v10);
        goto LABEL_117;
      }
      goto LABEL_117;
    }
    if ( (unsigned int)v8 < *((_DWORD *)this + 18) )
    {
      v17 = 0;
      *(PROPVARIANT *)(*((_QWORD *)this + 8) + 24 * v8) = pvarDest;
      goto LABEL_76;
    }
    v18 = (wchar_t *)CallStackTracing::s_wpInstance;
    v10 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v11, v12);
      CallStackTracing::s_wpInstance = v19;
      if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
      {
        v18 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v18 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v18 + 8) )
    {
      v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
      if ( *((_DWORD *)v20 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v20, "CID3Writer::SetProperty", 238, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_117;
    v21 = 18;
LABEL_25:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v21,
      &WPP_02bf30fd61593fcad53f801c1bfe75a2_Traceguids,
      v6,
      -2147024882);
    goto LABEL_117;
  }
  v10 = StringCchLengthW(a2, 0x7FFFFFFFu, (unsigned __int64 *)&Block);
  if ( v10 >= 0 )
  {
    v28 = (int)Block;
    v29 = (char *)Block + 1;
    v30 = operator new[](saturated_mul((unsigned __int64)Block + 1, 2u));
    Block = v30;
    if ( !v30 )
    {
      v34 = (wchar_t *)CallStackTracing::s_wpInstance;
      v10 = -2147024882;
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
        if ( *((_DWORD *)v36 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v36, "CID3Writer::SetProperty", 245, -2147024882);
      }
      if ( !g_wppLevels )
        goto LABEL_117;
      v21 = 20;
      goto LABEL_25;
    }
    v10 = StringCchCopyW((unsigned __int16 *)v30, (unsigned __int64)v29, a2);
    if ( v10 < 0 )
    {
      v40 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37, v38, v39);
        CallStackTracing::s_wpInstance = v41;
        if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
        {
          v40 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v40 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v40 + 8) )
      {
        v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
        if ( *((_DWORD *)v42 + 499) != v10 )
          CallStackContext::TraceFailure(v42, "CID3Writer::SetProperty", 246, v10);
      }
      if ( !g_wppLevels )
        goto LABEL_116;
      v43 = 21;
      goto LABEL_60;
    }
    v44 = *((unsigned int *)this + 6);
    if ( (unsigned int)CTEntryArray<unsigned short const *>::SetSize((char *)this + 16, (unsigned int)(v44 + 1)) )
    {
      v48 = (_QWORD *)((char *)this + 40);
      *(_QWORD *)(*((_QWORD *)this + 2) + 8 * v44) = Block;
      v49 = *((unsigned int *)this + 12);
      if ( (unsigned int)CTEntryArray<unsigned long>::SetSize((char *)this + 40, (unsigned int)(v49 + 1)) )
      {
        *(_DWORD *)(*v48 + 4 * v49) = v28;
        v10 = PropVariantCopy(&pvarDest, a3);
        if ( v10 < 0 )
        {
          v53 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v50, v51, v52);
            CallStackTracing::s_wpInstance = v54;
            if ( v54 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
            {
              v53 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v53 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v53 + 8) )
          {
            v55 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v53);
            if ( *((_DWORD *)v55 + 499) != v10 )
              CallStackContext::TraceFailure(v55, "CID3Writer::SetProperty", 259, v10);
          }
          if ( !g_wppLevels )
            goto LABEL_116;
          v43 = 24;
LABEL_60:
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v43, &WPP_02bf30fd61593fcad53f801c1bfe75a2_Traceguids, v6, v10);
          goto LABEL_116;
        }
        v56 = *((unsigned int *)this + 18);
        if ( (unsigned int)CTEntryArray<tagPROPVARIANT>::SetSize((char *)this + 64, (unsigned int)(v56 + 1)) )
        {
          *(PROPVARIANT *)(*((_QWORD *)this + 8) + 24 * v56) = pvarDest;
          v17 = Block;
LABEL_76:
          if ( (unsigned __int8)byte_1801B110A >= 0x20u )
          {
            bstrVal = L"Non-string";
            if ( pvarDest.vt == 31 )
              bstrVal = pvarDest.bstrVal;
            WPP_SF_qSS(*((_QWORD *)WPP_GLOBAL_Control + 12), (__int64)v17, (__int64)bstrVal);
          }
          goto LABEL_117;
        }
        CTEntryArray<unsigned short const *>::RemoveAt((char *)this + 16, (unsigned int)(*((_DWORD *)this + 6) - 1));
        v61 = *((_DWORD *)this + 12);
        if ( v61 )
        {
          v58 = *((unsigned int *)this + 12);
          v60 = (unsigned int)(v58 - 1);
          if ( (unsigned int)v60 <= v61 - 1 )
          {
            v62 = v61 - v60;
            if ( v62 != 1 )
              memmove_0((void *)(*v48 + 4 * v60), (const void *)(*v48 + 4 * v58), 4LL * (unsigned int)(v62 - 1));
            --*((_DWORD *)this + 12);
          }
        }
        v63 = (wchar_t *)CallStackTracing::s_wpInstance;
        v10 = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v58, v59, v60);
          CallStackTracing::s_wpInstance = v64;
          if ( v64 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
          {
            v63 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v63 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v63 + 8) )
        {
          v65 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v63);
          if ( *((_DWORD *)v65 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v65, "CID3Writer::SetProperty", 265, -2147024882);
        }
        if ( !g_wppLevels )
        {
LABEL_116:
          operator delete(Block);
          goto LABEL_117;
        }
        v66 = 25;
      }
      else
      {
        CTEntryArray<unsigned short const *>::RemoveAt((char *)this + 16, (unsigned int)(*((_DWORD *)this + 6) - 1));
        v70 = (wchar_t *)CallStackTracing::s_wpInstance;
        v10 = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v71 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v67, v68, v69);
          CallStackTracing::s_wpInstance = v71;
          if ( v71 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v71 + 8LL))(v71, 2032) )
          {
            v70 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v70 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v70 + 8) )
        {
          v72 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v70);
          if ( *((_DWORD *)v72 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v72, "CID3Writer::SetProperty", 256, -2147024882);
        }
        if ( !g_wppLevels )
          goto LABEL_116;
        v66 = 23;
      }
    }
    else
    {
      v73 = (wchar_t *)CallStackTracing::s_wpInstance;
      v10 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v74 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45, v46, v47);
        CallStackTracing::s_wpInstance = v74;
        if ( v74 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v74 + 8LL))(v74, 2032) )
        {
          v73 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v73 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v73 + 8) )
      {
        v75 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v73);
        if ( *((_DWORD *)v75 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v75, "CID3Writer::SetProperty", 250, -2147024882);
      }
      if ( !g_wppLevels )
        goto LABEL_116;
      v66 = 22;
    }
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v66,
      &WPP_02bf30fd61593fcad53f801c1bfe75a2_Traceguids,
      v6,
      -2147024882);
    goto LABEL_116;
  }
  v25 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23, v24);
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
    v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
    if ( *((_DWORD *)v27 + 499) != v10 )
      CallStackContext::TraceFailure(v27, "CID3Writer::SetProperty", 243, v10);
  }
  if ( g_wppLevels )
  {
    v16 = 19;
    goto LABEL_37;
  }
LABEL_117:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v77);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18009e480  mov     [rsp-38h+arg_18], rbx
0x18009e485  push    rbp
0x18009e486  push    rsi
0x18009e487  push    rdi
0x18009e488  push    r12
0x18009e48a  push    r13
0x18009e48c  push    r14
0x18009e48e  push    r15
0x18009e490  mov     rbp, rsp
0x18009e493  sub     rsp, 60h
0x18009e497  mov     rax, cs:__security_cookie
0x18009e49e  xor     rax, rsp
0x18009e4a1  mov     [rbp+var_8], rax
0x18009e4a5  mov     r12, r8
0x18009e4a8  mov     rsi, rdx
0x18009e4ab  mov     rbx, rcx
0x18009e4ae  lea     rdx, aCid3writerSetp; "CID3Writer::SetProperty"
0x18009e4b5  mov     r8d, 0E0h; int
0x18009e4bb  lea     rcx, [rbp+var_30]; this
0x18009e4bf  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009e4c4  xor     eax, eax
0x18009e4c6  lea     r14, [rbx-8]
0x18009e4ca  xorps   xmm0, xmm0
0x18009e4cd  mov     qword ptr [rbp+pvarDest+10h], rax
0x18009e4d1  xor     r13d, r13d
0x18009e4d4  mov     rcx, r14; this
0x18009e4d7  mov     rdx, rsi; unsigned __int16 *
0x18009e4da  mov     [rbp+Block], r13
0x18009e4de  movups  xmmword ptr [rbp+pvarDest], xmm0
0x18009e4e2  call    ?FindPropertyIndex@CID3Writer@@IEAAKPEBG@Z; CID3Writer::FindPropertyIndex(ushort const *)
0x18009e4e7  mov     r15d, eax
0x18009e4ea  cmp     eax, 0FFFFFFFFh
0x18009e4ed  jz      loc_18009E684
0x18009e4f3  mov     rcx, [rbx+40h]
0x18009e4f7  lea     rsi, [r15+r15*2]
0x18009e4fb  lea     rcx, [rcx+rsi*8]; pvar
0x18009e4ff  call    cs:__imp_PropVariantClear
0x18009e505  mov     rdx, r12; pvarSrc
0x18009e508  lea     rcx, [rbp+pvarDest]; pvarDest
0x18009e50c  call    cs:__imp_PropVariantCopy
0x18009e512  mov     edi, eax
0x18009e514  test    eax, eax
0x18009e516  jns     loc_18009E5AB
0x18009e51c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e523  test    rcx, rcx
0x18009e526  jnz     short loc_18009E569
0x18009e528  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009e52e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e535  mov     rcx, rax
0x18009e538  test    rax, rax
0x18009e53b  jz      short loc_18009E55B
0x18009e53d  mov     rax, [rax]
0x18009e540  mov     edx, 7F0h
0x18009e545  mov     rax, [rax+8]
0x18009e549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e54e  test    eax, eax
0x18009e550  jz      short loc_18009E55B
0x18009e552  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e559  jmp     short loc_18009E569
0x18009e55b  lea     rcx, qword_1801B07E0; this
0x18009e562  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e569  cmp     [rcx+8], r13b
0x18009e56d  jz      short loc_18009E594
0x18009e56f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009e574  cmp     [rax+7CCh], edi
0x18009e57a  jz      short loc_18009E594
0x18009e57c  mov     r9d, edi; int
0x18009e57f  lea     rdx, aCid3writerSetp; "CID3Writer::SetProperty"
0x18009e586  mov     r8d, 0EBh; int
0x18009e58c  mov     rcx, rax; this
0x18009e58f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009e594  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009e59b  jb      loc_18009EC40
0x18009e5a1  mov     edx, 11h
0x18009e5a6  jmp     loc_18009E729
0x18009e5ab  cmp     r15d, [rbx+48h]
0x18009e5af  jnb     short loc_18009E5D0
0x18009e5b1  mov     rax, [rbx+40h]
0x18009e5b5  mov     rcx, r13
0x18009e5b8  movups  xmm0, xmmword ptr [rbp+pvarDest]
0x18009e5bc  movups  xmmword ptr [rax+rsi*8], xmm0
0x18009e5c0  movsd   xmm1, qword ptr [rbp+pvarDest+10h]
0x18009e5c5  movsd   qword ptr [rax+rsi*8+10h], xmm1
0x18009e5cb  jmp     loc_18009E9CB
0x18009e5d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e5d7  mov     ebx, 8007000Eh
0x18009e5dc  mov     edi, ebx
0x18009e5de  test    rcx, rcx
0x18009e5e1  jnz     short loc_18009E624
0x18009e5e3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009e5e9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e5f0  mov     rcx, rax
0x18009e5f3  test    rax, rax
0x18009e5f6  jz      short loc_18009E616
0x18009e5f8  mov     rax, [rax]
0x18009e5fb  mov     edx, 7F0h
0x18009e600  mov     rax, [rax+8]
0x18009e604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e609  test    eax, eax
0x18009e60b  jz      short loc_18009E616
0x18009e60d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e614  jmp     short loc_18009E624
0x18009e616  lea     rcx, qword_1801B07E0; this
0x18009e61d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e624  cmp     [rcx+8], r13b
0x18009e628  jz      short loc_18009E64F
0x18009e62a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009e62f  cmp     [rax+7CCh], ebx
0x18009e635  jz      short loc_18009E64F
0x18009e637  mov     r9d, ebx; int
0x18009e63a  lea     rdx, aCid3writerSetp; "CID3Writer::SetProperty"
0x18009e641  mov     r8d, 0EEh; int
0x18009e647  mov     rcx, rax; this
0x18009e64a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009e64f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009e656  jb      loc_18009EC40
0x18009e65c  mov     edx, 12h
0x18009e661  mov     dword ptr [rsp+60h+var_40], ebx
0x18009e665  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e66c  lea     r8, WPP_02bf30fd61593fcad53f801c1bfe75a2_Traceguids
0x18009e673  mov     r9, r14
0x18009e676  mov     rcx, [rcx+10h]
0x18009e67a  call    WPP_SF_qD
0x18009e67f  jmp     loc_18009EC40
0x18009e684  lea     r8, [rbp+Block]; unsigned __int64 *
0x18009e688  mov     edx, 7FFFFFFFh; unsigned __int64
0x18009e68d  mov     rcx, rsi; unsigned __int16 *
0x18009e690  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18009e695  mov     edi, eax
0x18009e697  test    eax, eax
0x18009e699  jns     loc_18009E732
0x18009e69f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e6a6  test    rcx, rcx
0x18009e6a9  jnz     short loc_18009E6EC
0x18009e6ab  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009e6b1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e6b8  mov     rcx, rax
0x18009e6bb  test    rax, rax
0x18009e6be  jz      short loc_18009E6DE
0x18009e6c0  mov     rax, [rax]
0x18009e6c3  mov     edx, 7F0h
0x18009e6c8  mov     rax, [rax+8]
0x18009e6cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e6d1  test    eax, eax
0x18009e6d3  jz      short loc_18009E6DE
0x18009e6d5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e6dc  jmp     short loc_18009E6EC
0x18009e6de  lea     rcx, qword_1801B07E0; this
0x18009e6e5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e6ec  cmp     [rcx+8], r13b
0x18009e6f0  jz      short loc_18009E717
0x18009e6f2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009e6f7  cmp     [rax+7CCh], edi
0x18009e6fd  jz      short loc_18009E717
0x18009e6ff  mov     r9d, edi; int
0x18009e702  lea     rdx, aCid3writerSetp; "CID3Writer::SetProperty"
0x18009e709  mov     r8d, 0F3h; int
0x18009e70f  mov     rcx, rax; this
0x18009e712  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009e717  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009e71e  jb      loc_18009EC40
0x18009e724  mov     edx, 13h
0x18009e729  mov     dword ptr [rsp+60h+var_40], edi
0x18009e72d  jmp     loc_18009E665
0x18009e732  mov     r13, [rbp+Block]
0x18009e736  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18009e73d  mov     eax, 2
0x18009e742  lea     rdi, [r13+1]
0x18009e746  mul     rdi
0x18009e749  cmovb   rax, rcx
0x18009e74d  mov     rcx, rax; unsigned __int64
0x18009e750  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18009e755  mov     [rbp+Block], rax
0x18009e759  test    rax, rax
0x18009e75c  jnz     loc_18009E7F8
0x18009e762  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e769  mov     ebx, 8007000Eh
0x18009e76e  mov     edi, ebx
0x18009e770  test    rcx, rcx
0x18009e773  jnz     short loc_18009E7B6
0x18009e775  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009e77b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e782  mov     rcx, rax
0x18009e785  test    rax, rax
0x18009e788  jz      short loc_18009E7A8
0x18009e78a  mov     rax, [rax]
0x18009e78d  mov     edx, 7F0h
0x18009e792  mov     rax, [rax+8]
0x18009e796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e79b  test    eax, eax
0x18009e79d  jz      short loc_18009E7A8
0x18009e79f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e7a6  jmp     short loc_18009E7B6
0x18009e7a8  lea     rcx, qword_1801B07E0; this
0x18009e7af  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e7b6  cmp     byte ptr [rcx+8], 0
0x18009e7ba  jz      short loc_18009E7E1
0x18009e7bc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009e7c1  cmp     [rax+7CCh], ebx
0x18009e7c7  jz      short loc_18009E7E1
0x18009e7c9  mov     r9d, ebx; int
0x18009e7cc  lea     rdx, aCid3writerSetp; "CID3Writer::SetProperty"
0x18009e7d3  mov     r8d, 0F5h; int
0x18009e7d9  mov     rcx, rax; this
0x18009e7dc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009e7e1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009e7e8  jb      loc_18009EC40
0x18009e7ee  mov     edx, 14h
0x18009e7f3  jmp     loc_18009E661
0x18009e7f8  mov     r8, rsi; unsigned __int16 *
0x18009e7fb  mov     rdx, rdi; unsigned __int64
0x18009e7fe  mov     rcx, rax; unsigned __int16 *
0x18009e801  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009e806  mov     edi, eax
0x18009e808  test    eax, eax
0x18009e80a  jns     loc_18009E8A3
0x18009e810  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e817  test    rcx, rcx
0x18009e81a  jnz     short loc_18009E85D
0x18009e81c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009e822  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e829  mov     rcx, rax
0x18009e82c  test    rax, rax
0x18009e82f  jz      short loc_18009E84F
0x18009e831  mov     rax, [rax]
0x18009e834  mov     edx, 7F0h
0x18009e839  mov     rax, [rax+8]
0x18009e83d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e842  test    eax, eax
0x18009e844  jz      short loc_18009E84F
0x18009e846  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e84d  jmp     short loc_18009E85D
0x18009e84f  lea     rcx, qword_1801B07E0; this
0x18009e856  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e85d  cmp     byte ptr [rcx+8], 0
0x18009e861  jz      short loc_18009E888
0x18009e863  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009e868  cmp     [rax+7CCh], edi
0x18009e86e  jz      short loc_18009E888
0x18009e870  mov     r9d, edi; int
0x18009e873  lea     rdx, aCid3writerSetp; "CID3Writer::SetProperty"
0x18009e87a  mov     r8d, 0F6h; int
0x18009e880  mov     rcx, rax; this
0x18009e883  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009e888  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009e88f  jb      loc_18009EC37
0x18009e895  mov     edx, 15h
0x18009e89a  mov     dword ptr [rsp+60h+var_40], edi
0x18009e89e  jmp     loc_18009EC1D
0x18009e8a3  lea     r15, [rbx+10h]
0x18009e8a7  mov     edi, [r15+8]
0x18009e8ab  mov     rcx, r15
0x18009e8ae  lea     edx, [rdi+1]
0x18009e8b1  call    ?SetSize@?$CTEntryArray@PEBG@@QEAAHKK@Z; CTEntryArray<ushort const *>::SetSize(ulong,ulong)
0x18009e8b6  test    eax, eax
0x18009e8b8  jz      loc_18009EB8C
0x18009e8be  mov     rdx, [rbp+Block]
0x18009e8c2  lea     rsi, [rbx+28h]
0x18009e8c6  mov     rax, [r15]
0x18009e8c9  mov     rcx, rsi
0x18009e8cc  mov     [rax+rdi*8], rdx
0x18009e8d0  mov     edi, [rsi+8]
0x18009e8d3  lea     edx, [rdi+1]
0x18009e8d6  call    ?SetSize@?$CTEntryArray@K@@QEAAHKK@Z; CTEntryArray<ulong>::SetSize(ulong,ulong)
0x18009e8db  test    eax, eax
0x18009e8dd  jz      loc_18009EAE9
0x18009e8e3  mov     rax, [rsi]
0x18009e8e6  lea     rcx, [rbp+pvarDest]; pvarDest
0x18009e8ea  mov     rdx, r12; pvarSrc
0x18009e8ed  mov     [rax+rdi*4], r13d
0x18009e8f1  call    cs:__imp_PropVariantCopy
0x18009e8f7  mov     edi, eax
0x18009e8f9  test    eax, eax
0x18009e8fb  jns     loc_18009E990
0x18009e901  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e908  test    rcx, rcx
0x18009e90b  jnz     short loc_18009E94E
0x18009e90d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009e913  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e91a  mov     rcx, rax
0x18009e91d  test    rax, rax
0x18009e920  jz      short loc_18009E940
0x18009e922  mov     rax, [rax]
0x18009e925  mov     edx, 7F0h
0x18009e92a  mov     rax, [rax+8]
0x18009e92e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e933  test    eax, eax
0x18009e935  jz      short loc_18009E940
0x18009e937  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e93e  jmp     short loc_18009E94E
0x18009e940  lea     rcx, qword_1801B07E0; this
0x18009e947  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e94e  cmp     byte ptr [rcx+8], 0
0x18009e952  jz      short loc_18009E979
0x18009e954  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009e959  cmp     [rax+7CCh], edi
0x18009e95f  jz      short loc_18009E979
0x18009e961  mov     r9d, edi; int
0x18009e964  lea     rdx, aCid3writerSetp; "CID3Writer::SetProperty"
0x18009e96b  mov     r8d, 103h; int
  ... truncated ...
```
