# CID3Writer::SetProperty(ushort const *,tagPROPVARIANT const *)

- ea: `0x1800a3880`
- end: `0x1800a40b8`
- name: `?SetProperty@CID3Writer@@UEAAJPEBGPEBUtagPROPVARIANT@@@Z`
- size: `2104`
- prototype: `int(CID3Writer *__hidden this, const unsigned __int16 *, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1801258b0`

## callees

- `0x180005670`
- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180045400`
- `0x180079680`
- `0x180079d08`
- `0x1800a3880`
- `0x1800a40c0`
- `0x180110a88`
- `0x180110ad4`
- `0x180110ed0`
- `0x180129fd8`
- `0x18012aa50`
- `0x18012ab9c`
- `0x18012af80`
- `0x18017b74c`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3934`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a39f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3ac3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3b93`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3c40`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3d3d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3e9c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3f45`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3fe1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3934`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a39f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3ac3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3b93`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3c40`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3d3d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3e9c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3f45`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3fe1`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800a3912`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800a3d1b`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800a3912`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800a3d1b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a38ff`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a38ff`

## string_xrefs

- `0x1800a38ae`: `CID3Writer::SetProperty`
- `0x1800a3991`: `CID3Writer::SetProperty`
- `0x1800a3a52`: `CID3Writer::SetProperty`
- `0x1800a3b20`: `CID3Writer::SetProperty`
- `0x1800a3bf0`: `CID3Writer::SetProperty`
- `0x1800a3c9d`: `CID3Writer::SetProperty`
- `0x1800a3d9a`: `CID3Writer::SetProperty`
- `0x1800a3ef9`: `CID3Writer::SetProperty`
- `0x1800a3fa2`: `CID3Writer::SetProperty`
- `0x1800a403e`: `CID3Writer::SetProperty`

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
  wchar_t *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v14; // rdx
  void *v15; // rcx
  wchar_t *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rdx
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  int v24; // r13d
  char *v25; // rdi
  void *v26; // rax
  __int64 v27; // rdx
  wchar_t *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  wchar_t *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rdi
  __int64 v37; // rdx
  _QWORD *v38; // rsi
  __int64 v39; // rdi
  __int64 v40; // rdx
  wchar_t *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 v44; // r13
  const wchar_t *bstrVal; // rax
  __int64 v46; // rdx
  int v47; // ecx
  __int64 v48; // r9
  int v49; // ecx
  wchar_t *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  __int64 v53; // rdx
  __int64 v54; // rdx
  wchar_t *v55; // rcx
  CallStackTracing *v56; // rax
  struct CallStackContext *v57; // rax
  wchar_t *v58; // rcx
  CallStackTracing *v59; // rax
  struct CallStackContext *v60; // rax
  _BYTE v62[8]; // [rsp+30h] [rbp-30h] BYREF
  void *Block; // [rsp+38h] [rbp-28h] BYREF
  PROPVARIANT pvarDest; // [rsp+40h] [rbp-20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v62, "CID3Writer::SetProperty", 224);
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
      v11 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
        CallStackTracing::s_wpInstance = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v11 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v10 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CID3Writer::SetProperty", 235, v10);
      }
      if ( g_wppLevels )
      {
        v14 = 17;
LABEL_37:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_02bf30fd61593fcad53f801c1bfe75a2_Traceguids, v6, v10);
        goto LABEL_117;
      }
      goto LABEL_117;
    }
    if ( (unsigned int)v8 < *((_DWORD *)this + 18) )
    {
      v15 = 0;
      *(PROPVARIANT *)(*((_QWORD *)this + 8) + 24 * v8) = pvarDest;
      goto LABEL_76;
    }
    v16 = (wchar_t *)CallStackTracing::s_wpInstance;
    v10 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
      CallStackTracing::s_wpInstance = v17;
      if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
      {
        v16 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v16 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v16 + 8) )
    {
      v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
      if ( *((_DWORD *)v18 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v18, "CID3Writer::SetProperty", 238, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_117;
    v19 = 18;
LABEL_25:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v19,
      &WPP_02bf30fd61593fcad53f801c1bfe75a2_Traceguids,
      v6,
      -2147024882);
    goto LABEL_117;
  }
  v10 = StringCchLengthW(a2, 0x7FFFFFFFu, (unsigned __int64 *)&Block);
  if ( v10 >= 0 )
  {
    v24 = (int)Block;
    v25 = (char *)Block + 1;
    v26 = operator new[](saturated_mul((unsigned __int64)Block + 1, 2u));
    Block = v26;
    if ( !v26 )
    {
      v28 = (wchar_t *)CallStackTracing::s_wpInstance;
      v10 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
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
        v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
        if ( *((_DWORD *)v30 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v30, "CID3Writer::SetProperty", 245, -2147024882);
      }
      if ( !g_wppLevels )
        goto LABEL_117;
      v19 = 20;
      goto LABEL_25;
    }
    v10 = StringCchCopyW((unsigned __int16 *)v26, (unsigned __int64)v25, a2);
    if ( v10 < 0 )
    {
      v32 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
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
        v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
        if ( *((_DWORD *)v34 + 499) != v10 )
          CallStackContext::TraceFailure(v34, "CID3Writer::SetProperty", 246, v10);
      }
      if ( !g_wppLevels )
        goto LABEL_116;
      v35 = 21;
      goto LABEL_60;
    }
    v36 = *((unsigned int *)this + 6);
    if ( (unsigned int)CTEntryArray<unsigned short const *>::SetSize((char *)this + 16, (unsigned int)(v36 + 1)) )
    {
      v38 = (_QWORD *)((char *)this + 40);
      *(_QWORD *)(*((_QWORD *)this + 2) + 8 * v36) = Block;
      v39 = *((unsigned int *)this + 12);
      if ( (unsigned int)CTEntryArray<unsigned long>::SetSize((char *)this + 40, (unsigned int)(v39 + 1)) )
      {
        *(_DWORD *)(*v38 + 4 * v39) = v24;
        v10 = PropVariantCopy(&pvarDest, a3);
        if ( v10 < 0 )
        {
          v41 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40);
            CallStackTracing::s_wpInstance = v42;
            if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
            {
              v41 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v41 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v41 + 8) )
          {
            v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
            if ( *((_DWORD *)v43 + 499) != v10 )
              CallStackContext::TraceFailure(v43, "CID3Writer::SetProperty", 259, v10);
          }
          if ( !g_wppLevels )
            goto LABEL_116;
          v35 = 24;
LABEL_60:
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v35, &WPP_02bf30fd61593fcad53f801c1bfe75a2_Traceguids, v6, v10);
          goto LABEL_116;
        }
        v44 = *((unsigned int *)this + 18);
        if ( (unsigned int)CTEntryArray<tagPROPVARIANT>::SetSize((char *)this + 64, (unsigned int)(v44 + 1)) )
        {
          *(PROPVARIANT *)(*((_QWORD *)this + 8) + 24 * v44) = pvarDest;
          v15 = Block;
LABEL_76:
          if ( (unsigned __int8)byte_1801BA10A >= 0x20u )
          {
            bstrVal = L"Non-string";
            if ( pvarDest.vt == 31 )
              bstrVal = pvarDest.bstrVal;
            WPP_SF_qSS(*((_QWORD *)WPP_GLOBAL_Control + 12), (__int64)v15, (__int64)bstrVal);
          }
          goto LABEL_117;
        }
        CTEntryArray<unsigned short const *>::RemoveAt((char *)this + 16, (unsigned int)(*((_DWORD *)this + 6) - 1));
        v47 = *((_DWORD *)this + 12);
        if ( v47 )
        {
          v46 = *((unsigned int *)this + 12);
          v48 = (unsigned int)(v46 - 1);
          if ( (unsigned int)v48 <= v47 - 1 )
          {
            v49 = v47 - v48;
            if ( v49 != 1 )
              memmove_0((void *)(*v38 + 4 * v48), (const void *)(*v38 + 4 * v46), 4LL * (unsigned int)(v49 - 1));
            --*((_DWORD *)this + 12);
          }
        }
        v50 = (wchar_t *)CallStackTracing::s_wpInstance;
        v10 = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46);
          CallStackTracing::s_wpInstance = v51;
          if ( v51 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
          {
            v50 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v50 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v50 + 8) )
        {
          v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
          if ( *((_DWORD *)v52 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v52, "CID3Writer::SetProperty", 265, -2147024882);
        }
        if ( !g_wppLevels )
        {
LABEL_116:
          operator delete(Block);
          goto LABEL_117;
        }
        v53 = 25;
      }
      else
      {
        CTEntryArray<unsigned short const *>::RemoveAt((char *)this + 16, (unsigned int)(*((_DWORD *)this + 6) - 1));
        v55 = (wchar_t *)CallStackTracing::s_wpInstance;
        v10 = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v54);
          CallStackTracing::s_wpInstance = v56;
          if ( v56 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
          {
            v55 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v55 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v55 + 8) )
        {
          v57 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
          if ( *((_DWORD *)v57 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v57, "CID3Writer::SetProperty", 256, -2147024882);
        }
        if ( !g_wppLevels )
          goto LABEL_116;
        v53 = 23;
      }
    }
    else
    {
      v58 = (wchar_t *)CallStackTracing::s_wpInstance;
      v10 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37);
        CallStackTracing::s_wpInstance = v59;
        if ( v59 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v59 + 8LL))(v59, 2032) )
        {
          v58 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v58 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v58 + 8) )
      {
        v60 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v58);
        if ( *((_DWORD *)v60 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v60, "CID3Writer::SetProperty", 250, -2147024882);
      }
      if ( !g_wppLevels )
        goto LABEL_116;
      v53 = 22;
    }
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v53,
      &WPP_02bf30fd61593fcad53f801c1bfe75a2_Traceguids,
      v6,
      -2147024882);
    goto LABEL_116;
  }
  v21 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
    CallStackTracing::s_wpInstance = v22;
    if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
    {
      v21 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v21 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
  }
  if ( *((_BYTE *)v21 + 8) )
  {
    v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
    if ( *((_DWORD *)v23 + 499) != v10 )
      CallStackContext::TraceFailure(v23, "CID3Writer::SetProperty", 243, v10);
  }
  if ( g_wppLevels )
  {
    v14 = 19;
    goto LABEL_37;
  }
LABEL_117:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v62);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800a3880  mov     [rsp-38h+arg_18], rbx
0x1800a3885  push    rbp
0x1800a3886  push    rsi
0x1800a3887  push    rdi
0x1800a3888  push    r12
0x1800a388a  push    r13
0x1800a388c  push    r14
0x1800a388e  push    r15
0x1800a3890  mov     rbp, rsp
0x1800a3893  sub     rsp, 60h
0x1800a3897  mov     rax, cs:__security_cookie
0x1800a389e  xor     rax, rsp
0x1800a38a1  mov     [rbp+var_8], rax
0x1800a38a5  mov     r12, r8
0x1800a38a8  mov     rsi, rdx
0x1800a38ab  mov     rbx, rcx
0x1800a38ae  lea     rdx, aCid3writerSetp; "CID3Writer::SetProperty"
0x1800a38b5  mov     r8d, 0E0h; int
0x1800a38bb  lea     rcx, [rbp+var_30]; this
0x1800a38bf  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a38c4  xor     eax, eax
0x1800a38c6  lea     r14, [rbx-8]
0x1800a38ca  xorps   xmm0, xmm0
0x1800a38cd  mov     qword ptr [rbp+pvarDest+10h], rax
0x1800a38d1  xor     r13d, r13d
0x1800a38d4  mov     rcx, r14; this
0x1800a38d7  mov     rdx, rsi; unsigned __int16 *
0x1800a38da  mov     [rbp+Block], r13
0x1800a38de  movups  xmmword ptr [rbp+pvarDest], xmm0
0x1800a38e2  call    ?FindPropertyIndex@CID3Writer@@IEAAKPEBG@Z; CID3Writer::FindPropertyIndex(ushort const *)
0x1800a38e7  mov     r15d, eax
0x1800a38ea  cmp     eax, 0FFFFFFFFh
0x1800a38ed  jz      loc_1800A3A9C
0x1800a38f3  mov     rcx, [rbx+40h]
0x1800a38f7  lea     rsi, [r15+r15*2]
0x1800a38fb  lea     rcx, [rcx+rsi*8]; pvar
0x1800a38ff  call    cs:__imp_PropVariantClear
0x1800a3906  nop     dword ptr [rax+rax+00h]
0x1800a390b  mov     rdx, r12; pvarSrc
0x1800a390e  lea     rcx, [rbp+pvarDest]; pvarDest
0x1800a3912  call    cs:__imp_PropVariantCopy
0x1800a3919  nop     dword ptr [rax+rax+00h]
0x1800a391e  mov     edi, eax
0x1800a3920  test    eax, eax
0x1800a3922  jns     loc_1800A39BD
0x1800a3928  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a392f  test    rcx, rcx
0x1800a3932  jnz     short loc_1800A397B
0x1800a3934  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a393b  nop     dword ptr [rax+rax+00h]
0x1800a3940  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3947  mov     rcx, rax
0x1800a394a  test    rax, rax
0x1800a394d  jz      short loc_1800A396D
0x1800a394f  mov     rax, [rax]
0x1800a3952  mov     edx, 7F0h
0x1800a3957  mov     rax, [rax+8]
0x1800a395b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3960  test    eax, eax
0x1800a3962  jz      short loc_1800A396D
0x1800a3964  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a396b  jmp     short loc_1800A397B
0x1800a396d  lea     rcx, qword_1801B97E0; this
0x1800a3974  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a397b  cmp     [rcx+8], r13b
0x1800a397f  jz      short loc_1800A39A6
0x1800a3981  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a3986  cmp     [rax+7CCh], edi
0x1800a398c  jz      short loc_1800A39A6
0x1800a398e  mov     r9d, edi; int
0x1800a3991  lea     rdx, aCid3writerSetp; "CID3Writer::SetProperty"
0x1800a3998  mov     r8d, 0EBh; int
0x1800a399e  mov     rcx, rax; this
0x1800a39a1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a39a6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a39ad  jb      loc_1800A4088
0x1800a39b3  mov     edx, 11h
0x1800a39b8  jmp     loc_1800A3B47
0x1800a39bd  cmp     r15d, [rbx+48h]
0x1800a39c1  jnb     short loc_1800A39E2
0x1800a39c3  mov     rax, [rbx+40h]
0x1800a39c7  mov     rcx, r13
0x1800a39ca  movups  xmm0, xmmword ptr [rbp+pvarDest]
0x1800a39ce  movups  xmmword ptr [rax+rsi*8], xmm0
0x1800a39d2  movsd   xmm1, qword ptr [rbp+pvarDest+10h]
0x1800a39d7  movsd   qword ptr [rax+rsi*8+10h], xmm1
0x1800a39dd  jmp     loc_1800A3E01
0x1800a39e2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a39e9  mov     ebx, 8007000Eh
0x1800a39ee  mov     edi, ebx
0x1800a39f0  test    rcx, rcx
0x1800a39f3  jnz     short loc_1800A3A3C
0x1800a39f5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a39fc  nop     dword ptr [rax+rax+00h]
0x1800a3a01  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3a08  mov     rcx, rax
0x1800a3a0b  test    rax, rax
0x1800a3a0e  jz      short loc_1800A3A2E
0x1800a3a10  mov     rax, [rax]
0x1800a3a13  mov     edx, 7F0h
0x1800a3a18  mov     rax, [rax+8]
0x1800a3a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3a21  test    eax, eax
0x1800a3a23  jz      short loc_1800A3A2E
0x1800a3a25  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3a2c  jmp     short loc_1800A3A3C
0x1800a3a2e  lea     rcx, qword_1801B97E0; this
0x1800a3a35  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3a3c  cmp     [rcx+8], r13b
0x1800a3a40  jz      short loc_1800A3A67
0x1800a3a42  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a3a47  cmp     [rax+7CCh], ebx
0x1800a3a4d  jz      short loc_1800A3A67
0x1800a3a4f  mov     r9d, ebx; int
0x1800a3a52  lea     rdx, aCid3writerSetp; "CID3Writer::SetProperty"
0x1800a3a59  mov     r8d, 0EEh; int
0x1800a3a5f  mov     rcx, rax; this
0x1800a3a62  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a3a67  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a3a6e  jb      loc_1800A4088
0x1800a3a74  mov     edx, 12h
0x1800a3a79  mov     dword ptr [rsp+60h+var_40], ebx
0x1800a3a7d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a3a84  lea     r8, WPP_02bf30fd61593fcad53f801c1bfe75a2_Traceguids
0x1800a3a8b  mov     r9, r14
0x1800a3a8e  mov     rcx, [rcx+10h]
0x1800a3a92  call    WPP_SF_qD
0x1800a3a97  jmp     loc_1800A4088
0x1800a3a9c  lea     r8, [rbp+Block]; unsigned __int64 *
0x1800a3aa0  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800a3aa5  mov     rcx, rsi; unsigned __int16 *
0x1800a3aa8  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800a3aad  mov     edi, eax
0x1800a3aaf  test    eax, eax
0x1800a3ab1  jns     loc_1800A3B50
0x1800a3ab7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3abe  test    rcx, rcx
0x1800a3ac1  jnz     short loc_1800A3B0A
0x1800a3ac3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a3aca  nop     dword ptr [rax+rax+00h]
0x1800a3acf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3ad6  mov     rcx, rax
0x1800a3ad9  test    rax, rax
0x1800a3adc  jz      short loc_1800A3AFC
0x1800a3ade  mov     rax, [rax]
0x1800a3ae1  mov     edx, 7F0h
0x1800a3ae6  mov     rax, [rax+8]
0x1800a3aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3aef  test    eax, eax
0x1800a3af1  jz      short loc_1800A3AFC
0x1800a3af3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3afa  jmp     short loc_1800A3B0A
0x1800a3afc  lea     rcx, qword_1801B97E0; this
0x1800a3b03  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3b0a  cmp     [rcx+8], r13b
0x1800a3b0e  jz      short loc_1800A3B35
0x1800a3b10  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a3b15  cmp     [rax+7CCh], edi
0x1800a3b1b  jz      short loc_1800A3B35
0x1800a3b1d  mov     r9d, edi; int
0x1800a3b20  lea     rdx, aCid3writerSetp; "CID3Writer::SetProperty"
0x1800a3b27  mov     r8d, 0F3h; int
0x1800a3b2d  mov     rcx, rax; this
0x1800a3b30  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a3b35  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a3b3c  jb      loc_1800A4088
0x1800a3b42  mov     edx, 13h
0x1800a3b47  mov     dword ptr [rsp+60h+var_40], edi
0x1800a3b4b  jmp     loc_1800A3A7D
0x1800a3b50  mov     r13, [rbp+Block]
0x1800a3b54  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800a3b5b  mov     eax, 2
0x1800a3b60  lea     rdi, [r13+1]
0x1800a3b64  mul     rdi
0x1800a3b67  cmovb   rax, rcx
0x1800a3b6b  mov     rcx, rax; unsigned __int64
0x1800a3b6e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800a3b73  mov     [rbp+Block], rax
0x1800a3b77  test    rax, rax
0x1800a3b7a  jnz     loc_1800A3C1C
0x1800a3b80  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3b87  mov     ebx, 8007000Eh
0x1800a3b8c  mov     edi, ebx
0x1800a3b8e  test    rcx, rcx
0x1800a3b91  jnz     short loc_1800A3BDA
0x1800a3b93  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a3b9a  nop     dword ptr [rax+rax+00h]
0x1800a3b9f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3ba6  mov     rcx, rax
0x1800a3ba9  test    rax, rax
0x1800a3bac  jz      short loc_1800A3BCC
0x1800a3bae  mov     rax, [rax]
0x1800a3bb1  mov     edx, 7F0h
0x1800a3bb6  mov     rax, [rax+8]
0x1800a3bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3bbf  test    eax, eax
0x1800a3bc1  jz      short loc_1800A3BCC
0x1800a3bc3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3bca  jmp     short loc_1800A3BDA
0x1800a3bcc  lea     rcx, qword_1801B97E0; this
0x1800a3bd3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3bda  cmp     byte ptr [rcx+8], 0
0x1800a3bde  jz      short loc_1800A3C05
0x1800a3be0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a3be5  cmp     [rax+7CCh], ebx
0x1800a3beb  jz      short loc_1800A3C05
0x1800a3bed  mov     r9d, ebx; int
0x1800a3bf0  lea     rdx, aCid3writerSetp; "CID3Writer::SetProperty"
0x1800a3bf7  mov     r8d, 0F5h; int
0x1800a3bfd  mov     rcx, rax; this
0x1800a3c00  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a3c05  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a3c0c  jb      loc_1800A4088
0x1800a3c12  mov     edx, 14h
0x1800a3c17  jmp     loc_1800A3A79
0x1800a3c1c  mov     r8, rsi; unsigned __int16 *
0x1800a3c1f  mov     rdx, rdi; unsigned __int64
0x1800a3c22  mov     rcx, rax; unsigned __int16 *
0x1800a3c25  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a3c2a  mov     edi, eax
0x1800a3c2c  test    eax, eax
0x1800a3c2e  jns     loc_1800A3CCD
0x1800a3c34  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3c3b  test    rcx, rcx
0x1800a3c3e  jnz     short loc_1800A3C87
0x1800a3c40  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a3c47  nop     dword ptr [rax+rax+00h]
0x1800a3c4c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3c53  mov     rcx, rax
0x1800a3c56  test    rax, rax
0x1800a3c59  jz      short loc_1800A3C79
0x1800a3c5b  mov     rax, [rax]
0x1800a3c5e  mov     edx, 7F0h
0x1800a3c63  mov     rax, [rax+8]
0x1800a3c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3c6c  test    eax, eax
0x1800a3c6e  jz      short loc_1800A3C79
0x1800a3c70  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3c77  jmp     short loc_1800A3C87
0x1800a3c79  lea     rcx, qword_1801B97E0; this
0x1800a3c80  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3c87  cmp     byte ptr [rcx+8], 0
0x1800a3c8b  jz      short loc_1800A3CB2
0x1800a3c8d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a3c92  cmp     [rax+7CCh], edi
0x1800a3c98  jz      short loc_1800A3CB2
0x1800a3c9a  mov     r9d, edi; int
0x1800a3c9d  lea     rdx, aCid3writerSetp; "CID3Writer::SetProperty"
0x1800a3ca4  mov     r8d, 0F6h; int
0x1800a3caa  mov     rcx, rax; this
0x1800a3cad  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a3cb2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a3cb9  jb      loc_1800A407F
0x1800a3cbf  mov     edx, 15h
0x1800a3cc4  mov     dword ptr [rsp+60h+var_40], edi
0x1800a3cc8  jmp     loc_1800A4065
0x1800a3ccd  lea     r15, [rbx+10h]
0x1800a3cd1  mov     edi, [r15+8]
0x1800a3cd5  mov     rcx, r15
0x1800a3cd8  lea     edx, [rdi+1]
0x1800a3cdb  call    ?SetSize@?$CTEntryArray@PEBG@@QEAAHKK@Z; CTEntryArray<ushort const *>::SetSize(ulong,ulong)
0x1800a3ce0  test    eax, eax
0x1800a3ce2  jz      loc_1800A3FCE
0x1800a3ce8  mov     rdx, [rbp+Block]
0x1800a3cec  lea     rsi, [rbx+28h]
0x1800a3cf0  mov     rax, [r15]
0x1800a3cf3  mov     rcx, rsi
0x1800a3cf6  mov     [rax+rdi*8], rdx
0x1800a3cfa  mov     edi, [rsi+8]
0x1800a3cfd  lea     edx, [rdi+1]
0x1800a3d00  call    ?SetSize@?$CTEntryArray@K@@QEAAHKK@Z; CTEntryArray<ulong>::SetSize(ulong,ulong)
0x1800a3d05  test    eax, eax
0x1800a3d07  jz      loc_1800A3F25
0x1800a3d0d  mov     rax, [rsi]
0x1800a3d10  lea     rcx, [rbp+pvarDest]; pvarDest
0x1800a3d14  mov     rdx, r12; pvarSrc
0x1800a3d17  mov     [rax+rdi*4], r13d
0x1800a3d1b  call    cs:__imp_PropVariantCopy
0x1800a3d22  nop     dword ptr [rax+rax+00h]
0x1800a3d27  mov     edi, eax
0x1800a3d29  test    eax, eax
0x1800a3d2b  jns     loc_1800A3DC6
0x1800a3d31  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3d38  test    rcx, rcx
0x1800a3d3b  jnz     short loc_1800A3D84
0x1800a3d3d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a3d44  nop     dword ptr [rax+rax+00h]
0x1800a3d49  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3d50  mov     rcx, rax
0x1800a3d53  test    rax, rax
0x1800a3d56  jz      short loc_1800A3D76
0x1800a3d58  mov     rax, [rax]
0x1800a3d5b  mov     edx, 7F0h
0x1800a3d60  mov     rax, [rax+8]
0x1800a3d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3d69  test    eax, eax
0x1800a3d6b  jz      short loc_1800A3D76
0x1800a3d6d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3d74  jmp     short loc_1800A3D84
0x1800a3d76  lea     rcx, qword_1801B97E0; this
  ... truncated ...
```
