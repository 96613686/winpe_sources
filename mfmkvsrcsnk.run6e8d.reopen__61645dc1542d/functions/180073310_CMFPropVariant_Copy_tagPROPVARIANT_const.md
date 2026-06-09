# CMFPropVariant::Copy(tagPROPVARIANT const *)

- ea: `0x180073310`
- end: `0x180073791`
- name: `?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z`
- size: `1153`
- prototype: `__int64 __fastcall(PROPVARIANT *pvarDest, PROPVARIANT *pvarSrc)`
- caller_count: `5`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18006c404`
- `0x18006ecc0`
- `0x18007064c`
- `0x180071710`
- `0x180073f40`

## callees

- `0x1800036c5`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x180073310`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800733e4`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800733e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800734a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007356b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800734a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007356b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073358`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073418`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800734d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800735af`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073648`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800736e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073358`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073418`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800734d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800735af`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073648`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800736e1`

## string_xrefs

- `0x180073327`: `CMFPropVariant::Copy`
- `0x1800733b2`: `CMFPropVariant::Copy`
- `0x180073466`: `CMFPropVariant::Copy`
- `0x180073523`: `CMFPropVariant::Copy`
- `0x1800735fd`: `CMFPropVariant::Copy`
- `0x180073696`: `CMFPropVariant::Copy`
- `0x18007372f`: `CMFPropVariant::Copy`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::Copy(PROPVARIANT *pvarDest, PROPVARIANT *pvarSrc)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *v8; // rdi
  HRESULT v9; // esi
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  CallStackTracing *v17; // rax
  CallStackTracing *v18; // rcx
  struct CallStackContext *v19; // rax
  BYTE *v20; // rax
  __int64 v21; // rcx
  BYTE *v22; // r14
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  BYTE *pData; // rbp
  unsigned int i; // r12d
  void *v28; // rax
  __int64 v29; // rcx
  CallStackTracing *v30; // rax
  CallStackTracing *v31; // rcx
  struct CallStackContext *v32; // rax
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  _BYTE v38[56]; // [rsp+30h] [rbp-38h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v38, "CMFPropVariant::Copy", 181);
  if ( pvarDest == pvarSrc )
  {
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    v9 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v5, v4, v6, v7);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v8 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropVariant::Copy", 190, -2147467261);
    }
    if ( g_wppLevels )
    {
      v12 = 15;
LABEL_65:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, pvarDest, v9);
    }
  }
  else
  {
    v9 = PropVariantCopy(pvarDest, pvarSrc);
    if ( v9 >= 0 )
      goto LABEL_66;
    if ( pvarSrc->vt == 4161 )
    {
      pvarDest->vt = 4161;
      pvarDest->lVal = pvarSrc->lVal;
      v20 = (BYTE *)CoTaskMemAlloc(16LL * pvarSrc->ulVal);
      pvarDest->bstrblobVal.pData = v20;
      v22 = v20;
      if ( v20 )
      {
        pData = pvarSrc->bstrblobVal.pData;
        v9 = 0;
        for ( i = 0; pvarSrc->lVal > i; ++i )
        {
          *(_DWORD *)v22 = *(_DWORD *)pData;
          v28 = CoTaskMemAlloc(*(unsigned int *)pData);
          *((_QWORD *)v22 + 1) = v28;
          if ( !v28 )
          {
            v9 = -2147024882;
            if ( !CallStackTracing::s_wpInstance )
            {
              v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v29, v13, v15, v16);
              CallStackTracing::s_wpInstance = v30;
              if ( !v30
                || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
              {
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
              }
            }
            v31 = CallStackTracing::s_wpInstance;
            if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
            {
              v32 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
              if ( *((_DWORD *)v32 + 499) != -2147024882 )
                CallStackContext::TraceFailure(v32, "CMFPropVariant::Copy", 231, -2147024882);
            }
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                17,
                WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
                pvarDest,
                -2147024882);
            if ( !CallStackTracing::s_wpInstance )
            {
              v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v31, v13, v15, v16);
              CallStackTracing::s_wpInstance = v33;
              if ( !v33
                || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
              {
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
              }
            }
            v18 = CallStackTracing::s_wpInstance;
            if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
            {
              v34 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
              if ( *((_DWORD *)v34 + 499) != -2147024882 )
                CallStackContext::TraceFailure(v34, "CMFPropVariant::Copy", 236, -2147024882);
            }
            if ( g_wppLevels )
            {
              v25 = 18;
              goto LABEL_55;
            }
            goto LABEL_56;
          }
          memcpy_0(v28, *((const void **)pData + 1), *(unsigned int *)pData);
          v22 += 16;
          pData += 16;
        }
        goto LABEL_66;
      }
      v9 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v21, v13, v15, v16);
        CallStackTracing::s_wpInstance = v23;
        if ( !v23 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
      v18 = CallStackTracing::s_wpInstance;
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v24 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v24 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v24, "CMFPropVariant::Copy", 224, -2147024882);
      }
      if ( g_wppLevels )
      {
        v25 = 16;
LABEL_55:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v25,
          WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
          pvarDest,
          -2147024882);
      }
    }
    else
    {
      v9 = -1072875800;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v14, v13, v15, v16);
        CallStackTracing::s_wpInstance = v17;
        if ( !v17 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
      v18 = CallStackTracing::s_wpInstance;
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v19 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v19 + 499) != -1072875800 )
          CallStackContext::TraceFailure(v19, "CMFPropVariant::Copy", 241, -1072875800);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
          pvarDest,
          -1072875800);
    }
LABEL_56:
    if ( !CallStackTracing::s_wpInstance )
    {
      v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v18, v13, v15, v16);
      CallStackTracing::s_wpInstance = v35;
      if ( !v35 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v36 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v36 + 499) != v9 )
        CallStackContext::TraceFailure(v36, "CMFPropVariant::Copy", 247, v9);
    }
    if ( g_wppLevels )
    {
      v12 = 20;
      goto LABEL_65;
    }
  }
LABEL_66:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v38);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180073310  mov     [rsp+arg_10], rbp
0x180073315  push    rsi
0x180073316  push    rdi
0x180073317  push    r12
0x180073319  push    r14
0x18007331b  push    r15
0x18007331d  sub     rsp, 40h
0x180073321  mov     rdi, rdx
0x180073324  mov     r15, rcx
0x180073327  lea     rdx, aCmfpropvariant_8; "CMFPropVariant::Copy"
0x18007332e  mov     r8d, 0B5h; int
0x180073334  lea     rcx, [rsp+68h+var_38]; this
0x180073339  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18007333e  cmp     r15, rdi
0x180073341  jnz     loc_1800733DE
0x180073347  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007334e  mov     esi, 80004003h
0x180073353  test    rdi, rdi
0x180073356  jnz     short loc_180073399
0x180073358  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007335e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180073365  mov     rcx, rax
0x180073368  test    rax, rax
0x18007336b  jz      short loc_18007338B
0x18007336d  mov     rax, [rax]
0x180073370  mov     edx, 7F0h
0x180073375  mov     rax, [rax+8]
0x180073379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007337e  test    eax, eax
0x180073380  jz      short loc_18007338B
0x180073382  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073389  jmp     short loc_180073399
0x18007338b  lea     rdi, qword_1800D6F70
0x180073392  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180073399  cmp     byte ptr [rdi+8], 0
0x18007339d  jz      short loc_1800733C7
0x18007339f  mov     rcx, rdi; this
0x1800733a2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800733a7  cmp     [rax+7CCh], esi
0x1800733ad  jz      short loc_1800733C7
0x1800733af  mov     r9d, esi; int
0x1800733b2  lea     rdx, aCmfpropvariant_8; "CMFPropVariant::Copy"
0x1800733b9  mov     r8d, 0BEh; int
0x1800733bf  mov     rcx, rax; this
0x1800733c2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800733c7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800733ce  jb      loc_180073770
0x1800733d4  mov     edx, 0Fh
0x1800733d9  jmp     loc_180073752
0x1800733de  mov     rdx, rdi; pvarSrc
0x1800733e1  mov     rcx, r15; pvarDest
0x1800733e4  call    cs:__imp_PropVariantCopy
0x1800733ea  mov     esi, eax
0x1800733ec  test    eax, eax
0x1800733ee  jns     loc_180073770
0x1800733f4  mov     eax, 1041h
0x1800733f9  cmp     [rdi], ax
0x1800733fc  jz      loc_180073496
0x180073402  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18007340a  lea     rdi, qword_1800D6F70
0x180073411  mov     esi, 0C00D36E8h
0x180073416  jnz     short loc_180073449
0x180073418  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007341e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180073425  mov     rcx, rax
0x180073428  test    rax, rax
0x18007342b  jz      short loc_180073442
0x18007342d  mov     rax, [rax]
0x180073430  mov     edx, 7F0h
0x180073435  mov     rax, [rax+8]
0x180073439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007343e  test    eax, eax
0x180073440  jnz     short loc_180073449
0x180073442  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180073449  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180073450  cmp     byte ptr [rcx+8], 0
0x180073454  jz      short loc_18007347B
0x180073456  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007345b  cmp     [rax+7CCh], esi
0x180073461  jz      short loc_18007347B
0x180073463  mov     r9d, esi; int
0x180073466  lea     rdx, aCmfpropvariant_8; "CMFPropVariant::Copy"
0x18007346d  mov     r8d, 0F1h; int
0x180073473  mov     rcx, rax; this
0x180073476  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007347b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180073482  jb      loc_1800736D7
0x180073488  mov     edx, 13h
0x18007348d  mov     [rsp+68h+var_48], esi
0x180073491  jmp     loc_1800736BD
0x180073496  mov     [r15], ax
0x18007349a  mov     eax, [rdi+8]
0x18007349d  mov     [r15+8], eax
0x1800734a1  mov     ecx, [rdi+8]
0x1800734a4  shl     rcx, 4; cb
0x1800734a8  call    cs:__imp_CoTaskMemAlloc
0x1800734ae  mov     [r15+10h], rax
0x1800734b2  mov     r14, rax
0x1800734b5  test    rax, rax
0x1800734b8  jnz     loc_18007354F
0x1800734be  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800734c5  lea     rdi, qword_1800D6F70
0x1800734cc  mov     ebp, 8007000Eh
0x1800734d1  mov     esi, ebp
0x1800734d3  jnz     short loc_180073506
0x1800734d5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800734db  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800734e2  mov     rcx, rax
0x1800734e5  test    rax, rax
0x1800734e8  jz      short loc_1800734FF
0x1800734ea  mov     rax, [rax]
0x1800734ed  mov     edx, 7F0h
0x1800734f2  mov     rax, [rax+8]
0x1800734f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800734fb  test    eax, eax
0x1800734fd  jnz     short loc_180073506
0x1800734ff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180073506  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18007350d  cmp     byte ptr [rcx+8], 0
0x180073511  jz      short loc_180073538
0x180073513  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180073518  cmp     [rax+7CCh], ebp
0x18007351e  jz      short loc_180073538
0x180073520  mov     r9d, ebp; int
0x180073523  lea     rdx, aCmfpropvariant_8; "CMFPropVariant::Copy"
0x18007352a  mov     r8d, 0E0h; int
0x180073530  mov     rcx, rax; this
0x180073533  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180073538  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007353f  jb      loc_1800736D7
0x180073545  mov     edx, 10h
0x18007354a  jmp     loc_1800736B9
0x18007354f  mov     rbp, [rdi+10h]
0x180073553  xor     esi, esi
0x180073555  xor     r12d, r12d
0x180073558  cmp     [rdi+8], r12d
0x18007355c  jbe     loc_180073770
0x180073562  mov     eax, [rbp+0]
0x180073565  mov     [r14], eax
0x180073568  mov     ecx, [rbp+0]; cb
0x18007356b  call    cs:__imp_CoTaskMemAlloc
0x180073571  mov     [r14+8], rax
0x180073575  test    rax, rax
0x180073578  jz      short loc_180073597
0x18007357a  mov     r8d, [rbp+0]; Size
0x18007357e  mov     rcx, rax; void *
0x180073581  mov     rdx, [rbp+8]; Src
0x180073585  call    memcpy_0
0x18007358a  add     r14, 10h
0x18007358e  add     rbp, 10h
0x180073592  inc     r12d
0x180073595  jmp     short loc_180073558
0x180073597  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18007359f  lea     rdi, qword_1800D6F70
0x1800735a6  mov     ebp, 8007000Eh
0x1800735ab  mov     esi, ebp
0x1800735ad  jnz     short loc_1800735E0
0x1800735af  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800735b5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800735bc  mov     rcx, rax
0x1800735bf  test    rax, rax
0x1800735c2  jz      short loc_1800735D9
0x1800735c4  mov     rax, [rax]
0x1800735c7  mov     edx, 7F0h
0x1800735cc  mov     rax, [rax+8]
0x1800735d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800735d5  test    eax, eax
0x1800735d7  jnz     short loc_1800735E0
0x1800735d9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800735e0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800735e7  cmp     byte ptr [rcx+8], 0
0x1800735eb  jz      short loc_180073612
0x1800735ed  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800735f2  cmp     [rax+7CCh], ebp
0x1800735f8  jz      short loc_180073612
0x1800735fa  mov     r9d, ebp; int
0x1800735fd  lea     rdx, aCmfpropvariant_8; "CMFPropVariant::Copy"
0x180073604  mov     r8d, 0E7h; int
0x18007360a  mov     rcx, rax; this
0x18007360d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180073612  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180073619  jb      short loc_18007363E
0x18007361b  mov     rcx, cs:WPP_GLOBAL_Control
0x180073622  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x180073629  mov     edx, 11h
0x18007362e  mov     [rsp+68h+var_48], ebp
0x180073632  mov     r9, r15
0x180073635  mov     rcx, [rcx+10h]
0x180073639  call    WPP_SF_qD
0x18007363e  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x180073646  jnz     short loc_180073679
0x180073648  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007364e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180073655  mov     rcx, rax
0x180073658  test    rax, rax
0x18007365b  jz      short loc_180073672
0x18007365d  mov     rax, [rax]
0x180073660  mov     edx, 7F0h
0x180073665  mov     rax, [rax+8]
0x180073669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007366e  test    eax, eax
0x180073670  jnz     short loc_180073679
0x180073672  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180073679  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180073680  cmp     byte ptr [rcx+8], 0
0x180073684  jz      short loc_1800736AB
0x180073686  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007368b  cmp     [rax+7CCh], ebp
0x180073691  jz      short loc_1800736AB
0x180073693  mov     r9d, ebp; int
0x180073696  lea     rdx, aCmfpropvariant_8; "CMFPropVariant::Copy"
0x18007369d  mov     r8d, 0ECh; int
0x1800736a3  mov     rcx, rax; this
0x1800736a6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800736ab  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800736b2  jb      short loc_1800736D7
0x1800736b4  mov     edx, 12h
0x1800736b9  mov     [rsp+68h+var_48], ebp
0x1800736bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800736c4  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x1800736cb  mov     r9, r15
0x1800736ce  mov     rcx, [rcx+10h]
0x1800736d2  call    WPP_SF_qD
0x1800736d7  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x1800736df  jnz     short loc_180073712
0x1800736e1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800736e7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800736ee  mov     rcx, rax
0x1800736f1  test    rax, rax
0x1800736f4  jz      short loc_18007370B
0x1800736f6  mov     rax, [rax]
0x1800736f9  mov     edx, 7F0h
0x1800736fe  mov     rax, [rax+8]
0x180073702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073707  test    eax, eax
0x180073709  jnz     short loc_180073712
0x18007370b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180073712  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180073719  cmp     byte ptr [rcx+8], 0
0x18007371d  jz      short loc_180073744
0x18007371f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180073724  cmp     [rax+7CCh], esi
0x18007372a  jz      short loc_180073744
0x18007372c  mov     r9d, esi; int
0x18007372f  lea     rdx, aCmfpropvariant_8; "CMFPropVariant::Copy"
0x180073736  mov     r8d, 0F7h; int
0x18007373c  mov     rcx, rax; this
0x18007373f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180073744  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007374b  jb      short loc_180073770
0x18007374d  mov     edx, 14h
0x180073752  mov     rcx, cs:WPP_GLOBAL_Control
0x180073759  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x180073760  mov     r9, r15
0x180073763  mov     [rsp+68h+var_48], esi
0x180073767  mov     rcx, [rcx+10h]
0x18007376b  call    WPP_SF_qD
0x180073770  lea     rcx, [rsp+68h+var_38]; this
0x180073775  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18007377a  mov     rbp, [rsp+68h+arg_10]
0x180073782  mov     eax, esi
0x180073784  add     rsp, 40h
0x180073788  pop     r15
0x18007378a  pop     r14
0x18007378c  pop     r12
0x18007378e  pop     rdi
0x18007378f  pop     rsi
0x180073790  retn
```
