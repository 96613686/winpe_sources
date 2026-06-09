# CMFPropVariant::Copy(tagPROPVARIANT const *)

- ea: `0x18003733c`
- end: `0x1800377bc`
- name: `?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z`
- size: `1152`
- prototype: `__int64 __fastcall(PROPVARIANT *pvarDest, PROPVARIANT *pvarSrc)`
- caller_count: `8`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18002d69c`
- `0x180030030`
- `0x180035148`
- `0x180036d48`
- `0x180037f6c`
- `0x180038b38`
- `0x180052eb0`
- `0x180054820`

## callees

- `0x180016b0c`
- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x18003733c`
- `0x180039e60`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180037410`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180037410`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800374d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037598`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800374d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037598`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037384`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037444`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037504`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800375da`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037673`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003770c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037384`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037444`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037504`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800375da`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037673`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003770c`

## string_xrefs

- `0x180037353`: `CMFPropVariant::Copy`
- `0x1800373de`: `CMFPropVariant::Copy`
- `0x180037492`: `CMFPropVariant::Copy`
- `0x180037552`: `CMFPropVariant::Copy`
- `0x180037628`: `CMFPropVariant::Copy`
- `0x1800376c1`: `CMFPropVariant::Copy`
- `0x18003775a`: `CMFPropVariant::Copy`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::Copy(PROPVARIANT *pvarDest, PROPVARIANT *pvarSrc)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 *v6; // rdi
  HRESULT v7; // esi
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  BYTE *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  BYTE *v20; // r14
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  BYTE *pData; // r15
  unsigned int i; // ebp
  void *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  _BYTE v38[56]; // [rsp+30h] [rbp-38h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v38, "CMFPropVariant::Copy", 181);
  if ( pvarDest == pvarSrc )
  {
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    v7 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v5, v4);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v6 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropVariant::Copy", 190, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v10 = 15;
LABEL_65:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, pvarDest, v7);
    }
  }
  else
  {
    v7 = PropVariantCopy(pvarDest, pvarSrc);
    if ( v7 >= 0 )
      goto LABEL_66;
    if ( pvarSrc->vt == 4161 )
    {
      pvarDest->vt = 4161;
      pvarDest->lVal = pvarSrc->lVal;
      v17 = (BYTE *)CoTaskMemAlloc(16LL * pvarSrc->ulVal);
      pvarDest->bstrblobVal.pData = v17;
      v20 = v17;
      if ( v17 )
      {
        pData = pvarSrc->bstrblobVal.pData;
        v7 = 0;
        for ( i = 0; pvarSrc->lVal > i; ++i )
        {
          *(_DWORD *)v20 = *(_DWORD *)pData;
          v26 = CoTaskMemAlloc(*(unsigned int *)pData);
          *((_QWORD *)v20 + 1) = v26;
          if ( !v26 )
          {
            v7 = -2147024882;
            if ( !CallStackTracing::s_wpInstance )
            {
              v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v28, v27);
              CallStackTracing::s_wpInstance = v29;
              if ( !v29
                || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
              {
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
              }
            }
            if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
            {
              v30 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
              if ( *((_DWORD *)v30 + 499) != -2147024882 )
                CallStackContext::TraceFailure(v30, "CMFPropVariant::Copy", 231, -2147024882);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              WPP_SF_qd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                17,
                WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
                pvarDest,
                -2147024882);
            if ( !CallStackTracing::s_wpInstance )
            {
              v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v32, v31);
              CallStackTracing::s_wpInstance = v33;
              if ( !v33
                || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
              {
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
              }
            }
            if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
            {
              v34 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
              if ( *((_DWORD *)v34 + 499) != -2147024882 )
                CallStackContext::TraceFailure(v34, "CMFPropVariant::Copy", 236, -2147024882);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v23 = 18;
              goto LABEL_55;
            }
            goto LABEL_56;
          }
          memcpy_0(v26, *((const void **)pData + 1), *(unsigned int *)pData);
          v20 += 16;
          pData += 16;
        }
        goto LABEL_66;
      }
      v7 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v19, v18);
        CallStackTracing::s_wpInstance = v21;
        if ( !v21 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v22 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v22 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v22, "CMFPropVariant::Copy", 224, -2147024882);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v23 = 16;
LABEL_55:
        WPP_SF_qd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v23,
          WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
          pvarDest,
          -2147024882);
      }
    }
    else
    {
      v7 = -1072875800;
      if ( !CallStackTracing::s_wpInstance )
      {
        v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v12, v11);
        CallStackTracing::s_wpInstance = v13;
        if ( !v13 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v14 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v14 + 499) != -1072875800 )
          CallStackContext::TraceFailure(v14, "CMFPropVariant::Copy", 241, -1072875800);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        WPP_SF_qd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
          pvarDest,
          -1072875800);
    }
LABEL_56:
    if ( !CallStackTracing::s_wpInstance )
    {
      v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v16, v15);
      CallStackTracing::s_wpInstance = v35;
      if ( !v35 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v36 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v36 + 499) != v7 )
        CallStackContext::TraceFailure(v36, "CMFPropVariant::Copy", 247, v7);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v10 = 20;
      goto LABEL_65;
    }
  }
LABEL_66:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v38);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003733c  mov     [rsp+arg_10], rbp
0x180037341  push    rsi
0x180037342  push    rdi
0x180037343  push    r12
0x180037345  push    r14
0x180037347  push    r15
0x180037349  sub     rsp, 40h
0x18003734d  mov     rdi, rdx
0x180037350  mov     r12, rcx
0x180037353  lea     rdx, aCmfpropvariant_13; "CMFPropVariant::Copy"
0x18003735a  mov     r8d, 0B5h; int
0x180037360  lea     rcx, [rsp+68h+var_38]; this
0x180037365  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003736a  cmp     r12, rdi
0x18003736d  jnz     loc_18003740A
0x180037373  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003737a  mov     esi, 80004003h
0x18003737f  test    rdi, rdi
0x180037382  jnz     short loc_1800373C5
0x180037384  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003738a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180037391  mov     rcx, rax
0x180037394  test    rax, rax
0x180037397  jz      short loc_1800373B7
0x180037399  mov     rax, [rax]
0x18003739c  mov     edx, 7F0h
0x1800373a1  mov     rax, [rax+8]
0x1800373a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800373aa  test    eax, eax
0x1800373ac  jz      short loc_1800373B7
0x1800373ae  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800373b5  jmp     short loc_1800373C5
0x1800373b7  lea     rdi, qword_18006EB20
0x1800373be  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800373c5  cmp     byte ptr [rdi+8], 0
0x1800373c9  jz      short loc_1800373F3
0x1800373cb  mov     rcx, rdi; this
0x1800373ce  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800373d3  cmp     [rax+7CCh], esi
0x1800373d9  jz      short loc_1800373F3
0x1800373db  mov     r9d, esi; int
0x1800373de  lea     rdx, aCmfpropvariant_13; "CMFPropVariant::Copy"
0x1800373e5  mov     r8d, 0BEh; int
0x1800373eb  mov     rcx, rax; this
0x1800373ee  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800373f3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800373f8  cmp     al, 1
0x1800373fa  jb      loc_18003779B
0x180037400  mov     edx, 0Fh
0x180037405  jmp     loc_18003777D
0x18003740a  mov     rdx, rdi; pvarSrc
0x18003740d  mov     rcx, r12; pvarDest
0x180037410  call    cs:__imp_PropVariantCopy
0x180037416  mov     esi, eax
0x180037418  test    eax, eax
0x18003741a  jns     loc_18003779B
0x180037420  mov     eax, 1041h
0x180037425  cmp     [rdi], ax
0x180037428  jz      loc_1800374C2
0x18003742e  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x180037436  lea     rdi, qword_18006EB20
0x18003743d  mov     esi, 0C00D36E8h
0x180037442  jnz     short loc_180037475
0x180037444  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003744a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180037451  mov     rcx, rax
0x180037454  test    rax, rax
0x180037457  jz      short loc_18003746E
0x180037459  mov     rax, [rax]
0x18003745c  mov     edx, 7F0h
0x180037461  mov     rax, [rax+8]
0x180037465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003746a  test    eax, eax
0x18003746c  jnz     short loc_180037475
0x18003746e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180037475  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003747c  cmp     byte ptr [rcx+8], 0
0x180037480  jz      short loc_1800374A7
0x180037482  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180037487  cmp     [rax+7CCh], esi
0x18003748d  jz      short loc_1800374A7
0x18003748f  mov     r9d, esi; int
0x180037492  lea     rdx, aCmfpropvariant_13; "CMFPropVariant::Copy"
0x180037499  mov     r8d, 0F1h; int
0x18003749f  mov     rcx, rax; this
0x1800374a2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800374a7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800374ac  cmp     al, 1
0x1800374ae  jb      loc_180037702
0x1800374b4  mov     edx, 13h
0x1800374b9  mov     [rsp+68h+var_48], esi
0x1800374bd  jmp     loc_1800376E8
0x1800374c2  mov     [r12], ax
0x1800374c7  mov     eax, [rdi+8]
0x1800374ca  mov     [r12+8], eax
0x1800374cf  mov     ecx, [rdi+8]
0x1800374d2  shl     rcx, 4; cb
0x1800374d6  call    cs:__imp_CoTaskMemAlloc
0x1800374dc  mov     [r12+10h], rax
0x1800374e1  mov     r14, rax
0x1800374e4  test    rax, rax
0x1800374e7  jnz     loc_18003757E
0x1800374ed  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800374f4  lea     rdi, qword_18006EB20
0x1800374fb  mov     ebp, 8007000Eh
0x180037500  mov     esi, ebp
0x180037502  jnz     short loc_180037535
0x180037504  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003750a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180037511  mov     rcx, rax
0x180037514  test    rax, rax
0x180037517  jz      short loc_18003752E
0x180037519  mov     rax, [rax]
0x18003751c  mov     edx, 7F0h
0x180037521  mov     rax, [rax+8]
0x180037525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003752a  test    eax, eax
0x18003752c  jnz     short loc_180037535
0x18003752e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180037535  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003753c  cmp     byte ptr [rcx+8], 0
0x180037540  jz      short loc_180037567
0x180037542  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180037547  cmp     [rax+7CCh], ebp
0x18003754d  jz      short loc_180037567
0x18003754f  mov     r9d, ebp; int
0x180037552  lea     rdx, aCmfpropvariant_13; "CMFPropVariant::Copy"
0x180037559  mov     r8d, 0E0h; int
0x18003755f  mov     rcx, rax; this
0x180037562  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180037567  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003756c  cmp     al, 1
0x18003756e  jb      loc_180037702
0x180037574  mov     edx, 10h
0x180037579  jmp     loc_1800376E4
0x18003757e  mov     r15, [rdi+10h]
0x180037582  xor     esi, esi
0x180037584  xor     ebp, ebp
0x180037586  cmp     [rdi+8], ebp
0x180037589  jbe     loc_18003779B
0x18003758f  mov     eax, [r15]
0x180037592  mov     [r14], eax
0x180037595  mov     ecx, [r15]; cb
0x180037598  call    cs:__imp_CoTaskMemAlloc
0x18003759e  mov     [r14+8], rax
0x1800375a2  test    rax, rax
0x1800375a5  jz      short loc_1800375C2
0x1800375a7  mov     r8d, [r15]; Size
0x1800375aa  mov     rcx, rax; void *
0x1800375ad  mov     rdx, [r15+8]; Src
0x1800375b1  call    memcpy_0
0x1800375b6  add     r14, 10h
0x1800375ba  add     r15, 10h
0x1800375be  inc     ebp
0x1800375c0  jmp     short loc_180037586
0x1800375c2  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x1800375ca  lea     rdi, qword_18006EB20
0x1800375d1  mov     ebp, 8007000Eh
0x1800375d6  mov     esi, ebp
0x1800375d8  jnz     short loc_18003760B
0x1800375da  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800375e0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800375e7  mov     rcx, rax
0x1800375ea  test    rax, rax
0x1800375ed  jz      short loc_180037604
0x1800375ef  mov     rax, [rax]
0x1800375f2  mov     edx, 7F0h
0x1800375f7  mov     rax, [rax+8]
0x1800375fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037600  test    eax, eax
0x180037602  jnz     short loc_18003760B
0x180037604  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18003760b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180037612  cmp     byte ptr [rcx+8], 0
0x180037616  jz      short loc_18003763D
0x180037618  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003761d  cmp     [rax+7CCh], ebp
0x180037623  jz      short loc_18003763D
0x180037625  mov     r9d, ebp; int
0x180037628  lea     rdx, aCmfpropvariant_13; "CMFPropVariant::Copy"
0x18003762f  mov     r8d, 0E7h; int
0x180037635  mov     rcx, rax; this
0x180037638  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003763d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180037642  cmp     al, 1
0x180037644  jb      short loc_180037669
0x180037646  mov     rcx, cs:WPP_GLOBAL_Control
0x18003764d  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x180037654  mov     edx, 11h
0x180037659  mov     [rsp+68h+var_48], ebp
0x18003765d  mov     r9, r12
0x180037660  mov     rcx, [rcx+10h]
0x180037664  call    WPP_SF_qd
0x180037669  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x180037671  jnz     short loc_1800376A4
0x180037673  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180037679  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180037680  mov     rcx, rax
0x180037683  test    rax, rax
0x180037686  jz      short loc_18003769D
0x180037688  mov     rax, [rax]
0x18003768b  mov     edx, 7F0h
0x180037690  mov     rax, [rax+8]
0x180037694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037699  test    eax, eax
0x18003769b  jnz     short loc_1800376A4
0x18003769d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800376a4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800376ab  cmp     byte ptr [rcx+8], 0
0x1800376af  jz      short loc_1800376D6
0x1800376b1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800376b6  cmp     [rax+7CCh], ebp
0x1800376bc  jz      short loc_1800376D6
0x1800376be  mov     r9d, ebp; int
0x1800376c1  lea     rdx, aCmfpropvariant_13; "CMFPropVariant::Copy"
0x1800376c8  mov     r8d, 0ECh; int
0x1800376ce  mov     rcx, rax; this
0x1800376d1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800376d6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800376db  cmp     al, 1
0x1800376dd  jb      short loc_180037702
0x1800376df  mov     edx, 12h
0x1800376e4  mov     [rsp+68h+var_48], ebp
0x1800376e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800376ef  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x1800376f6  mov     r9, r12
0x1800376f9  mov     rcx, [rcx+10h]
0x1800376fd  call    WPP_SF_qd
0x180037702  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18003770a  jnz     short loc_18003773D
0x18003770c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180037712  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180037719  mov     rcx, rax
0x18003771c  test    rax, rax
0x18003771f  jz      short loc_180037736
0x180037721  mov     rax, [rax]
0x180037724  mov     edx, 7F0h
0x180037729  mov     rax, [rax+8]
0x18003772d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037732  test    eax, eax
0x180037734  jnz     short loc_18003773D
0x180037736  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18003773d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180037744  cmp     byte ptr [rcx+8], 0
0x180037748  jz      short loc_18003776F
0x18003774a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003774f  cmp     [rax+7CCh], esi
0x180037755  jz      short loc_18003776F
0x180037757  mov     r9d, esi; int
0x18003775a  lea     rdx, aCmfpropvariant_13; "CMFPropVariant::Copy"
0x180037761  mov     r8d, 0F7h; int
0x180037767  mov     rcx, rax; this
0x18003776a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003776f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180037774  cmp     al, 1
0x180037776  jb      short loc_18003779B
0x180037778  mov     edx, 14h
0x18003777d  mov     rcx, cs:WPP_GLOBAL_Control
0x180037784  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x18003778b  mov     r9, r12
0x18003778e  mov     [rsp+68h+var_48], esi
0x180037792  mov     rcx, [rcx+10h]
0x180037796  call    WPP_SF_qd
0x18003779b  lea     rcx, [rsp+68h+var_38]; this
0x1800377a0  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800377a5  mov     rbp, [rsp+68h+arg_10]
0x1800377ad  mov     eax, esi
0x1800377af  add     rsp, 40h
0x1800377b3  pop     r15
0x1800377b5  pop     r14
0x1800377b7  pop     r12
0x1800377b9  pop     rdi
0x1800377ba  pop     rsi
0x1800377bb  retn
```
