# CFLACMetadataWriter::SetProperty(ushort const *,tagPROPVARIANT const *)

- ea: `0x180032ab0`
- end: `0x1800332c4`
- name: `?SetProperty@CFLACMetadataWriter@@UEAAJPEBGPEBUtagPROPVARIANT@@@Z`
- size: `2068`
- prototype: `int(CFLACMetadataWriter *__hidden this, const unsigned __int16 *, const struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `20`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002a85c`
- `0x18002d69c`

## callees

- `0x1800018e4`
- `0x1800018f0`
- `0x180001e80`
- `0x18001b654`
- `0x18001ef50`
- `0x180020398`
- `0x180020484`
- `0x1800234fc`
- `0x18002fce8`
- `0x18002fff0`
- `0x180030064`
- `0x180031074`
- `0x180031bdc`
- `0x180032900`
- `0x180032ab0`
- `0x1800332cc`
- `0x180033414`
- `0x180034188`
- `0x180039e60`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180032b48`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180032fc6`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180032b48`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180032fc6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180032b3b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180032b3b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032b64`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032c36`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032cfa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032dc0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032e67`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032f19`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032fe2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033148`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800331eb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032b64`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032c36`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032cfa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032dc0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032e67`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032f19`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032fe2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033148`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800331eb`

## string_xrefs

- `0x180032ae8`: `CFLACMetadataWriter::SetProperty`
- `0x180032e1d`: `CFLACMetadataWriter::SetProperty`
- `0x180032ec4`: `CFLACMetadataWriter::SetProperty`
- `0x180032f76`: `CFLACMetadataWriter::SetProperty`
- `0x18003303f`: `CFLACMetadataWriter::SetProperty`
- `0x1800331a5`: `CFLACMetadataWriter::SetProperty`
- `0x180033248`: `CFLACMetadataWriter::SetProperty`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFLACMetadataWriter::SetProperty(
        CFLACMetadataWriter *this,
        const unsigned __int16 *a2,
        struct tagPROPVARIANT *a3)
{
  void *v6; // r12
  char *v7; // r14
  unsigned int PropertyIndex; // eax
  __int64 v9; // r15
  __int64 v10; // rdx
  HRESULT v11; // edi
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned __int64 v23; // r13
  unsigned __int64 v24; // rdi
  unsigned __int16 *v25; // rax
  __int64 v26; // rdx
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  __int64 v40; // rdi
  __int64 v41; // rdx
  __int64 *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  signed __int64 v45; // rdx
  int v46; // ecx
  int v47; // eax
  const wchar_t *bstrVal; // rax
  __int64 v49; // rdx
  __int64 *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  __int64 v53; // rdx
  __int64 *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  unsigned __int64 v58; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v59[8]; // [rsp+38h] [rbp-38h] BYREF
  unsigned __int16 *v60; // [rsp+40h] [rbp-30h] BYREF
  PROPVARIANT *pvarSrc; // [rsp+48h] [rbp-28h]
  PROPVARIANT pvarDest; // [rsp+50h] [rbp-20h] BYREF

  pvarSrc = a3;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v59, "CFLACMetadataWriter::SetProperty", 233);
  v58 = 0;
  v6 = 0;
  memset(&pvarDest, 0, sizeof(pvarDest));
  v7 = (char *)this - 8;
  PropertyIndex = CFLACMetadataWriter::FindPropertyIndex((CFLACMetadataWriter *)((char *)this - 8), a2);
  v9 = PropertyIndex;
  if ( PropertyIndex == -1 )
  {
    v11 = StringCchLengthW(a2, 0x7FFFFFFFu, &v58);
    if ( v11 < 0 )
    {
      v20 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v11 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CFLACMetadataWriter::SetProperty", 254, v11);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_116;
      v15 = 23;
LABEL_13:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        &WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids,
        (char *)this - 8,
        v11);
      goto LABEL_116;
    }
    v23 = v58;
    v24 = v58 + 1;
    v25 = (unsigned __int16 *)operator new[](saturated_mul(v58 + 1, 2u));
    v58 = (unsigned __int64)v25;
    v60 = v25;
    if ( !v25 )
    {
      v11 = -2147024882;
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
        if ( *((_DWORD *)v29 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v29, "CFLACMetadataWriter::SetProperty", 256, -2147024882);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_115;
      v30 = 24;
      goto LABEL_114;
    }
    v11 = StringCchCopyW(v25, v24, a2);
    if ( v11 < 0 )
    {
      v32 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
        CallStackTracing::s_wpInstance = v33;
        if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
        {
          v32 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v32 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v32 + 8) )
      {
        v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
        if ( *((_DWORD *)v34 + 499) != v11 )
          CallStackContext::TraceFailure(v34, "CFLACMetadataWriter::SetProperty", 257, v11);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_115;
      v35 = 25;
      goto LABEL_59;
    }
    if ( (unsigned int)CTEntryArray<unsigned short const *>::Add((char *)this + 16, &v60) )
    {
      v40 = *((unsigned int *)this + 18);
      if ( (unsigned int)CTEntryArray<unsigned __int64>::SetSize((char *)this + 64, (unsigned int)(v40 + 1)) )
      {
        *(_QWORD *)(*((_QWORD *)this + 8) + 8 * v40) = v23;
        v11 = PropVariantCopy(&pvarDest, pvarSrc);
        if ( v11 < 0 )
        {
          v42 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41);
            CallStackTracing::s_wpInstance = v43;
            if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
            {
              v42 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v42 = &qword_18006EB20;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
            }
          }
          if ( *((_BYTE *)v42 + 8) )
          {
            v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
            if ( *((_DWORD *)v44 + 499) != v11 )
              CallStackContext::TraceFailure(v44, "CFLACMetadataWriter::SetProperty", 270, v11);
          }
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_115;
          v35 = 28;
LABEL_59:
          WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v35, &WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids, v7, v11);
          goto LABEL_115;
        }
        LODWORD(v60) = *((_DWORD *)this + 24);
        if ( (unsigned int)CTEntryArray<tagPROPVARIANT>::SetSize((char *)this + 88, (unsigned int)((_DWORD)v60 + 1)) )
        {
          *(PROPVARIANT *)(*((_QWORD *)this + 11) + 24LL * (unsigned int)v60) = pvarDest;
          v45 = (char *)L"WM/Picture" - (char *)a2;
          do
          {
            v46 = *(const unsigned __int16 *)((char *)a2 + v45);
            v47 = *a2 - v46;
            if ( v47 )
              break;
            ++a2;
          }
          while ( v46 );
          v6 = (void *)v58;
          if ( !v47 )
          {
            *((_BYTE *)this + 129) = 1;
            *((_DWORD *)this + 33) = *((_DWORD *)this + 24) - 1;
          }
          goto LABEL_89;
        }
        CTEntryArray<unsigned __int64>::RemoveAt((char *)this + 16, (unsigned int)(*((_DWORD *)this + 6) - 1));
        CTEntryArray<unsigned __int64>::RemoveAt((char *)this + 64, (unsigned int)(*((_DWORD *)this + 18) - 1));
        v11 = -2147024882;
        v50 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v49);
          CallStackTracing::s_wpInstance = v51;
          if ( v51 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
          {
            v50 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v50 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v50 + 8) )
        {
          v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
          if ( *((_DWORD *)v52 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v52, "CFLACMetadataWriter::SetProperty", 276, -2147024882);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
LABEL_115:
          v6 = (void *)v58;
LABEL_116:
          if ( v6 )
            operator delete(v6);
          goto LABEL_118;
        }
        v30 = 29;
      }
      else
      {
        CTEntryArray<unsigned __int64>::RemoveAt((char *)this + 16, (unsigned int)(*((_DWORD *)this + 6) - 1));
        v11 = -2147024882;
        v54 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v53);
          CallStackTracing::s_wpInstance = v55;
          if ( v55 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
          {
            v54 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v54 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v54 + 8) )
        {
          v56 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
          if ( *((_DWORD *)v56 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v56, "CFLACMetadataWriter::SetProperty", 267, -2147024882);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_115;
        v30 = 27;
      }
    }
    else
    {
      v11 = -2147024882;
      v37 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36);
        CallStackTracing::s_wpInstance = v38;
        if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
        {
          v37 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v37 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v37 + 8) )
      {
        v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
        if ( *((_DWORD *)v39 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v39, "CFLACMetadataWriter::SetProperty", 261, -2147024882);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_115;
      v30 = 26;
    }
LABEL_114:
    WPP_SF_qd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v30,
      &WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids,
      v7,
      -2147024882);
    goto LABEL_115;
  }
  PropVariantClear((PROPVARIANT *)(*((_QWORD *)this + 11) + 24LL * PropertyIndex));
  v11 = PropVariantCopy(&pvarDest, a3);
  if ( v11 < 0 )
  {
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)v14 + 499) != v11 )
        CallStackContext::TraceFailure(v14, "CFLACMetadataWriter::SetProperty", 246, v11);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_116;
    v15 = 21;
    goto LABEL_13;
  }
  if ( (unsigned int)v9 < *((_DWORD *)this + 24) )
  {
    *(PROPVARIANT *)(*((_QWORD *)this + 11) + 24 * v9) = pvarDest;
LABEL_89:
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 0x20u )
    {
      bstrVal = L"Non-string";
      if ( pvarDest.vt == 31 )
        bstrVal = pvarDest.bstrVal;
      WPP_SF_qSS(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)v6, (__int64)bstrVal);
    }
    goto LABEL_118;
  }
  v11 = -2147024882;
  v16 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
    CallStackTracing::s_wpInstance = v17;
    if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
    {
      v16 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v16 = &qword_18006EB20;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
    }
  }
  if ( *((_BYTE *)v16 + 8) )
  {
    v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
    if ( *((_DWORD *)v18 + 499) != -2147024882 )
      CallStackContext::TraceFailure(v18, "CFLACMetadataWriter::SetProperty", 249, -2147024882);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    WPP_SF_qd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      &WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids,
      v7,
      -2147024882);
LABEL_118:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v59);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180032ab0  mov     [rsp-38h+arg_18], rbx
0x180032ab5  push    rbp
0x180032ab6  push    rsi
0x180032ab7  push    rdi
0x180032ab8  push    r12
0x180032aba  push    r13
0x180032abc  push    r14
0x180032abe  push    r15
0x180032ac0  mov     rbp, rsp
0x180032ac3  sub     rsp, 70h
0x180032ac7  mov     rax, cs:__security_cookie
0x180032ace  xor     rax, rsp
0x180032ad1  mov     [rbp+var_8], rax
0x180032ad5  mov     rdi, r8
0x180032ad8  mov     [rbp+pvarSrc], r8
0x180032adc  mov     rsi, rdx
0x180032adf  mov     rbx, rcx
0x180032ae2  mov     r8d, 0E9h; int
0x180032ae8  lea     r13, aCflacmetadataw_1; "CFLACMetadataWriter::SetProperty"
0x180032aef  mov     rdx, r13; char *
0x180032af2  lea     rcx, [rbp+var_38]; this
0x180032af6  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180032afb  nop
0x180032afc  mov     [rbp+var_40], 0
0x180032b04  xor     r12d, r12d
0x180032b07  xorps   xmm0, xmm0
0x180032b0a  xor     eax, eax
0x180032b0c  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180032b10  mov     qword ptr [rbp+pvarDest+10h], rax
0x180032b14  lea     r14, [rbx-8]
0x180032b18  mov     rdx, rsi; unsigned __int16 *
0x180032b1b  mov     rcx, r14; this
0x180032b1e  call    ?FindPropertyIndex@CFLACMetadataWriter@@IEAAKPEBG@Z; CFLACMetadataWriter::FindPropertyIndex(ushort const *)
0x180032b23  mov     r15d, eax
0x180032b26  cmp     eax, 0FFFFFFFFh
0x180032b29  jz      loc_180032CD3
0x180032b2f  lea     rsi, [r15+r15*2]
0x180032b33  mov     rcx, [rbx+58h]
0x180032b37  lea     rcx, [rcx+rsi*8]; pvar
0x180032b3b  call    cs:__imp_PropVariantClear
0x180032b41  mov     rdx, rdi; pvarSrc
0x180032b44  lea     rcx, [rbp+pvarDest]; pvarDest
0x180032b48  call    cs:__imp_PropVariantCopy
0x180032b4e  mov     edi, eax
0x180032b50  test    eax, eax
0x180032b52  jns     loc_180032C01
0x180032b58  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032b5f  test    rcx, rcx
0x180032b62  jnz     short loc_180032BA5
0x180032b64  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180032b6a  mov     rcx, rax
0x180032b6d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180032b74  test    rax, rax
0x180032b77  jz      short loc_180032B97
0x180032b79  mov     rax, [rax]
0x180032b7c  mov     edx, 7F0h
0x180032b81  mov     rax, [rax+8]
0x180032b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b8a  test    eax, eax
0x180032b8c  jz      short loc_180032B97
0x180032b8e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032b95  jmp     short loc_180032BA5
0x180032b97  lea     rcx, qword_18006EB20; this
0x180032b9e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180032ba5  cmp     [rcx+8], r12b
0x180032ba9  jz      short loc_180032BCC
0x180032bab  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180032bb0  cmp     [rax+7CCh], edi
0x180032bb6  jz      short loc_180032BCC
0x180032bb8  mov     r9d, edi; int
0x180032bbb  mov     r8d, 0F6h; int
0x180032bc1  mov     rdx, r13; char *
0x180032bc4  mov     rcx, rax; this
0x180032bc7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180032bcc  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180032bd1  cmp     al, 1
0x180032bd3  jb      loc_180033287
0x180032bd9  mov     edx, 15h
0x180032bde  mov     dword ptr [rsp+70h+var_50], edi
0x180032be2  mov     r9, r14
0x180032be5  lea     r8, WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids
0x180032bec  mov     rcx, cs:WPP_GLOBAL_Control
0x180032bf3  mov     rcx, [rcx+10h]
0x180032bf7  call    WPP_SF_qd
0x180032bfc  jmp     loc_180033287
0x180032c01  cmp     r15d, [rbx+60h]
0x180032c05  jnb     short loc_180032C23
0x180032c07  mov     rax, [rbx+58h]
0x180032c0b  movups  xmm0, xmmword ptr [rbp+pvarDest]
0x180032c0f  movups  xmmword ptr [rax+rsi*8], xmm0
0x180032c13  movsd   xmm1, qword ptr [rbp+pvarDest+10h]
0x180032c18  movsd   qword ptr [rax+rsi*8+10h], xmm1
0x180032c1e  jmp     loc_1800330D4
0x180032c23  mov     ebx, 8007000Eh
0x180032c28  mov     edi, ebx
0x180032c2a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032c31  test    rcx, rcx
0x180032c34  jnz     short loc_180032C77
0x180032c36  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180032c3c  mov     rcx, rax
0x180032c3f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180032c46  test    rax, rax
0x180032c49  jz      short loc_180032C69
0x180032c4b  mov     rax, [rax]
0x180032c4e  mov     edx, 7F0h
0x180032c53  mov     rax, [rax+8]
0x180032c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032c5c  test    eax, eax
0x180032c5e  jz      short loc_180032C69
0x180032c60  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032c67  jmp     short loc_180032C77
0x180032c69  lea     rcx, qword_18006EB20; this
0x180032c70  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180032c77  cmp     [rcx+8], r12b
0x180032c7b  jz      short loc_180032C9E
0x180032c7d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180032c82  cmp     [rax+7CCh], ebx
0x180032c88  jz      short loc_180032C9E
0x180032c8a  mov     r9d, ebx; int
0x180032c8d  mov     r8d, 0F9h; int
0x180032c93  mov     rdx, r13; char *
0x180032c96  mov     rcx, rax; this
0x180032c99  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180032c9e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180032ca3  cmp     al, 1
0x180032ca5  jb      loc_180033295
0x180032cab  mov     edx, 16h
0x180032cb0  mov     dword ptr [rsp+70h+var_50], ebx
0x180032cb4  mov     r9, r14
0x180032cb7  lea     r8, WPP_d608dde02ec63f35621638fdaae2eed9_Traceguids
0x180032cbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180032cc5  mov     rcx, [rcx+10h]
0x180032cc9  call    WPP_SF_qd
0x180032cce  jmp     loc_180033295
0x180032cd3  lea     r8, [rbp+var_40]; unsigned __int64 *
0x180032cd7  mov     edx, 7FFFFFFFh; unsigned __int64
0x180032cdc  mov     rcx, rsi; unsigned __int16 *
0x180032cdf  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180032ce4  mov     edi, eax
0x180032ce6  test    eax, eax
0x180032ce8  jns     loc_180032D79
0x180032cee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032cf5  test    rcx, rcx
0x180032cf8  jnz     short loc_180032D3B
0x180032cfa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180032d00  mov     rcx, rax
0x180032d03  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180032d0a  test    rax, rax
0x180032d0d  jz      short loc_180032D2D
0x180032d0f  mov     rax, [rax]
0x180032d12  mov     edx, 7F0h
0x180032d17  mov     rax, [rax+8]
0x180032d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032d20  test    eax, eax
0x180032d22  jz      short loc_180032D2D
0x180032d24  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032d2b  jmp     short loc_180032D3B
0x180032d2d  lea     rcx, qword_18006EB20; this
0x180032d34  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180032d3b  cmp     [rcx+8], r12b
0x180032d3f  jz      short loc_180032D62
0x180032d41  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180032d46  cmp     [rax+7CCh], edi
0x180032d4c  jz      short loc_180032D62
0x180032d4e  mov     r9d, edi; int
0x180032d51  mov     r8d, 0FEh; int
0x180032d57  mov     rdx, r13; char *
0x180032d5a  mov     rcx, rax; this
0x180032d5d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180032d62  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180032d67  cmp     al, 1
0x180032d69  jb      loc_180033287
0x180032d6f  mov     edx, 17h
0x180032d74  jmp     loc_180032BDE
0x180032d79  mov     r13, [rbp+var_40]
0x180032d7d  lea     rdi, [r13+1]
0x180032d81  mov     eax, 2
0x180032d86  mul     rdi
0x180032d89  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180032d90  cmovb   rax, rcx
0x180032d94  mov     rcx, rax; unsigned __int64
0x180032d97  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180032d9c  mov     [rbp+var_40], rax
0x180032da0  mov     [rbp+var_30], rax
0x180032da4  test    rax, rax
0x180032da7  jnz     loc_180032E43
0x180032dad  mov     ebx, 8007000Eh
0x180032db2  mov     edi, ebx
0x180032db4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032dbb  test    rcx, rcx
0x180032dbe  jnz     short loc_180032E01
0x180032dc0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180032dc6  mov     rcx, rax
0x180032dc9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180032dd0  test    rax, rax
0x180032dd3  jz      short loc_180032DF3
0x180032dd5  mov     rax, [rax]
0x180032dd8  mov     edx, 7F0h
0x180032ddd  mov     rax, [rax+8]
0x180032de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032de6  test    eax, eax
0x180032de8  jz      short loc_180032DF3
0x180032dea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032df1  jmp     short loc_180032E01
0x180032df3  lea     rcx, qword_18006EB20; this
0x180032dfa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180032e01  cmp     [rcx+8], r12b
0x180032e05  jz      short loc_180032E2C
0x180032e07  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180032e0c  cmp     [rax+7CCh], ebx
0x180032e12  jz      short loc_180032E2C
0x180032e14  mov     r9d, ebx; int
0x180032e17  mov     r8d, 100h; int
0x180032e1d  lea     rdx, aCflacmetadataw_1; "CFLACMetadataWriter::SetProperty"
0x180032e24  mov     rcx, rax; this
0x180032e27  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180032e2c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180032e31  cmp     al, 1
0x180032e33  jb      loc_180033283
0x180032e39  mov     edx, 18h
0x180032e3e  jmp     loc_180033265
0x180032e43  mov     r8, rsi; unsigned __int16 *
0x180032e46  mov     rdx, rdi; unsigned __int64
0x180032e49  mov     rcx, rax; unsigned __int16 *
0x180032e4c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180032e51  mov     edi, eax
0x180032e53  test    eax, eax
0x180032e55  jns     loc_180032EEE
0x180032e5b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032e62  test    rcx, rcx
0x180032e65  jnz     short loc_180032EA8
0x180032e67  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180032e6d  mov     rcx, rax
0x180032e70  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180032e77  test    rax, rax
0x180032e7a  jz      short loc_180032E9A
0x180032e7c  mov     rax, [rax]
0x180032e7f  mov     edx, 7F0h
0x180032e84  mov     rax, [rax+8]
0x180032e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e8d  test    eax, eax
0x180032e8f  jz      short loc_180032E9A
0x180032e91  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032e98  jmp     short loc_180032EA8
0x180032e9a  lea     rcx, qword_18006EB20; this
0x180032ea1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180032ea8  cmp     [rcx+8], r12b
0x180032eac  jz      short loc_180032ED3
0x180032eae  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180032eb3  cmp     [rax+7CCh], edi
0x180032eb9  jz      short loc_180032ED3
0x180032ebb  mov     r9d, edi; int
0x180032ebe  mov     r8d, 101h; int
0x180032ec4  lea     rdx, aCflacmetadataw_1; "CFLACMetadataWriter::SetProperty"
0x180032ecb  mov     rcx, rax; this
0x180032ece  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180032ed3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180032ed8  cmp     al, 1
0x180032eda  jb      loc_180033283
0x180032ee0  mov     edx, 19h
0x180032ee5  mov     dword ptr [rsp+70h+var_50], edi
0x180032ee9  jmp     loc_180033269
0x180032eee  lea     r12, [rbx+10h]
0x180032ef2  lea     rdx, [rbp+var_30]
0x180032ef6  mov     rcx, r12
0x180032ef9  call    ?Add@?$CTEntryArray@PEBG@@QEAAHAEBQEBGPEAK@Z; CTEntryArray<ushort const *>::Add(ushort const * const &,ulong *)
0x180032efe  test    eax, eax
0x180032f00  jnz     loc_180032F9C
0x180032f06  mov     ebx, 8007000Eh
0x180032f0b  mov     edi, ebx
0x180032f0d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032f14  test    rcx, rcx
0x180032f17  jnz     short loc_180032F5A
0x180032f19  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180032f1f  mov     rcx, rax
0x180032f22  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180032f29  test    rax, rax
0x180032f2c  jz      short loc_180032F4C
0x180032f2e  mov     rax, [rax]
0x180032f31  mov     edx, 7F0h
0x180032f36  mov     rax, [rax+8]
0x180032f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f3f  test    eax, eax
0x180032f41  jz      short loc_180032F4C
0x180032f43  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032f4a  jmp     short loc_180032F5A
0x180032f4c  lea     rcx, qword_18006EB20; this
0x180032f53  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180032f5a  cmp     byte ptr [rcx+8], 0
0x180032f5e  jz      short loc_180032F85
0x180032f60  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180032f65  cmp     [rax+7CCh], ebx
0x180032f6b  jz      short loc_180032F85
0x180032f6d  mov     r9d, ebx; int
0x180032f70  mov     r8d, 105h; int
0x180032f76  lea     rdx, aCflacmetadataw_1; "CFLACMetadataWriter::SetProperty"
0x180032f7d  mov     rcx, rax; this
0x180032f80  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180032f85  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180032f8a  cmp     al, 1
  ... truncated ...
```
