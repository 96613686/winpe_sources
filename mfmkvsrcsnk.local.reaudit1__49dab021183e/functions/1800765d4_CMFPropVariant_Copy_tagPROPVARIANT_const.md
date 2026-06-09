# CMFPropVariant::Copy(tagPROPVARIANT const *)

- ea: `0x1800765d4`
- end: `0x180076a8c`
- name: `?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z`
- size: `1208`
- prototype: `__int64 __fastcall(PROPVARIANT *pvarDest, PROPVARIANT *pvarSrc)`
- caller_count: `5`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18006f224`
- `0x180071c50`
- `0x180073704`
- `0x1800748fc`
- `0x180077298`

## callees

- `0x180003705`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x1800765d4`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800766ae`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800766ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007677e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007684d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007677e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007684d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007661c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800766e8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800767b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076897`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076936`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800769d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007661c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800766e8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800767b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076897`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076936`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800769d5`

## string_xrefs

- `0x1800765eb`: `CMFPropVariant::Copy`
- `0x18007667c`: `CMFPropVariant::Copy`
- `0x18007673c`: `CMFPropVariant::Copy`
- `0x180076805`: `CMFPropVariant::Copy`
- `0x1800768eb`: `CMFPropVariant::Copy`
- `0x18007698a`: `CMFPropVariant::Copy`
- `0x180076a29`: `CMFPropVariant::Copy`

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
        v8 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x1800765d4  mov     [rsp+arg_10], rbp
0x1800765d9  push    rsi
0x1800765da  push    rdi
0x1800765db  push    r12
0x1800765dd  push    r14
0x1800765df  push    r15
0x1800765e1  sub     rsp, 40h
0x1800765e5  mov     rdi, rdx
0x1800765e8  mov     r15, rcx
0x1800765eb  lea     rdx, aCmfpropvariant_8; "CMFPropVariant::Copy"
0x1800765f2  mov     r8d, 0B5h; int
0x1800765f8  lea     rcx, [rsp+68h+var_38]; this
0x1800765fd  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180076602  cmp     r15, rdi
0x180076605  jnz     loc_1800766A8
0x18007660b  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076612  mov     esi, 80004003h
0x180076617  test    rdi, rdi
0x18007661a  jnz     short loc_180076663
0x18007661c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180076623  nop     dword ptr [rax+rax+00h]
0x180076628  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007662f  mov     rcx, rax
0x180076632  test    rax, rax
0x180076635  jz      short loc_180076655
0x180076637  mov     rax, [rax]
0x18007663a  mov     edx, 7F0h
0x18007663f  mov     rax, [rax+8]
0x180076643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076648  test    eax, eax
0x18007664a  jz      short loc_180076655
0x18007664c  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076653  jmp     short loc_180076663
0x180076655  lea     rdi, qword_1800DBF70
0x18007665c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180076663  cmp     byte ptr [rdi+8], 0
0x180076667  jz      short loc_180076691
0x180076669  mov     rcx, rdi; this
0x18007666c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180076671  cmp     [rax+7CCh], esi
0x180076677  jz      short loc_180076691
0x180076679  mov     r9d, esi; int
0x18007667c  lea     rdx, aCmfpropvariant_8; "CMFPropVariant::Copy"
0x180076683  mov     r8d, 0BEh; int
0x180076689  mov     rcx, rax; this
0x18007668c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180076691  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180076698  jb      loc_180076A6A
0x18007669e  mov     edx, 0Fh
0x1800766a3  jmp     loc_180076A4C
0x1800766a8  mov     rdx, rdi; pvarSrc
0x1800766ab  mov     rcx, r15; pvarDest
0x1800766ae  call    cs:__imp_PropVariantCopy
0x1800766b5  nop     dword ptr [rax+rax+00h]
0x1800766ba  mov     esi, eax
0x1800766bc  test    eax, eax
0x1800766be  jns     loc_180076A6A
0x1800766c4  mov     eax, 1041h
0x1800766c9  cmp     [rdi], ax
0x1800766cc  jz      loc_18007676C
0x1800766d2  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x1800766da  lea     rdi, qword_1800DBF70
0x1800766e1  mov     esi, 0C00D36E8h
0x1800766e6  jnz     short loc_18007671F
0x1800766e8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800766ef  nop     dword ptr [rax+rax+00h]
0x1800766f4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800766fb  mov     rcx, rax
0x1800766fe  test    rax, rax
0x180076701  jz      short loc_180076718
0x180076703  mov     rax, [rax]
0x180076706  mov     edx, 7F0h
0x18007670b  mov     rax, [rax+8]
0x18007670f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076714  test    eax, eax
0x180076716  jnz     short loc_18007671F
0x180076718  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18007671f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180076726  cmp     byte ptr [rcx+8], 0
0x18007672a  jz      short loc_180076751
0x18007672c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180076731  cmp     [rax+7CCh], esi
0x180076737  jz      short loc_180076751
0x180076739  mov     r9d, esi; int
0x18007673c  lea     rdx, aCmfpropvariant_8; "CMFPropVariant::Copy"
0x180076743  mov     r8d, 0F1h; int
0x180076749  mov     rcx, rax; this
0x18007674c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180076751  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180076758  jb      loc_1800769CB
0x18007675e  mov     edx, 13h
0x180076763  mov     [rsp+68h+var_48], esi
0x180076767  jmp     loc_1800769B1
0x18007676c  mov     [r15], ax
0x180076770  mov     eax, [rdi+8]
0x180076773  mov     [r15+8], eax
0x180076777  mov     ecx, [rdi+8]
0x18007677a  shl     rcx, 4; cb
0x18007677e  call    cs:__imp_CoTaskMemAlloc
0x180076785  nop     dword ptr [rax+rax+00h]
0x18007678a  mov     [r15+10h], rax
0x18007678e  mov     r14, rax
0x180076791  test    rax, rax
0x180076794  jnz     loc_180076831
0x18007679a  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800767a1  lea     rdi, qword_1800DBF70
0x1800767a8  mov     ebp, 8007000Eh
0x1800767ad  mov     esi, ebp
0x1800767af  jnz     short loc_1800767E8
0x1800767b1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800767b8  nop     dword ptr [rax+rax+00h]
0x1800767bd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800767c4  mov     rcx, rax
0x1800767c7  test    rax, rax
0x1800767ca  jz      short loc_1800767E1
0x1800767cc  mov     rax, [rax]
0x1800767cf  mov     edx, 7F0h
0x1800767d4  mov     rax, [rax+8]
0x1800767d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800767dd  test    eax, eax
0x1800767df  jnz     short loc_1800767E8
0x1800767e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800767e8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800767ef  cmp     byte ptr [rcx+8], 0
0x1800767f3  jz      short loc_18007681A
0x1800767f5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800767fa  cmp     [rax+7CCh], ebp
0x180076800  jz      short loc_18007681A
0x180076802  mov     r9d, ebp; int
0x180076805  lea     rdx, aCmfpropvariant_8; "CMFPropVariant::Copy"
0x18007680c  mov     r8d, 0E0h; int
0x180076812  mov     rcx, rax; this
0x180076815  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007681a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180076821  jb      loc_1800769CB
0x180076827  mov     edx, 10h
0x18007682c  jmp     loc_1800769AD
0x180076831  mov     rbp, [rdi+10h]
0x180076835  xor     esi, esi
0x180076837  xor     r12d, r12d
0x18007683a  cmp     [rdi+8], r12d
0x18007683e  jbe     loc_180076A6A
0x180076844  mov     eax, [rbp+0]
0x180076847  mov     [r14], eax
0x18007684a  mov     ecx, [rbp+0]; cb
0x18007684d  call    cs:__imp_CoTaskMemAlloc
0x180076854  nop     dword ptr [rax+rax+00h]
0x180076859  mov     [r14+8], rax
0x18007685d  test    rax, rax
0x180076860  jz      short loc_18007687F
0x180076862  mov     r8d, [rbp+0]; Size
0x180076866  mov     rcx, rax; void *
0x180076869  mov     rdx, [rbp+8]; Src
0x18007686d  call    memcpy_0
0x180076872  add     r14, 10h
0x180076876  add     rbp, 10h
0x18007687a  inc     r12d
0x18007687d  jmp     short loc_18007683A
0x18007687f  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x180076887  lea     rdi, qword_1800DBF70
0x18007688e  mov     ebp, 8007000Eh
0x180076893  mov     esi, ebp
0x180076895  jnz     short loc_1800768CE
0x180076897  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007689e  nop     dword ptr [rax+rax+00h]
0x1800768a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800768aa  mov     rcx, rax
0x1800768ad  test    rax, rax
0x1800768b0  jz      short loc_1800768C7
0x1800768b2  mov     rax, [rax]
0x1800768b5  mov     edx, 7F0h
0x1800768ba  mov     rax, [rax+8]
0x1800768be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800768c3  test    eax, eax
0x1800768c5  jnz     short loc_1800768CE
0x1800768c7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800768ce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800768d5  cmp     byte ptr [rcx+8], 0
0x1800768d9  jz      short loc_180076900
0x1800768db  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800768e0  cmp     [rax+7CCh], ebp
0x1800768e6  jz      short loc_180076900
0x1800768e8  mov     r9d, ebp; int
0x1800768eb  lea     rdx, aCmfpropvariant_8; "CMFPropVariant::Copy"
0x1800768f2  mov     r8d, 0E7h; int
0x1800768f8  mov     rcx, rax; this
0x1800768fb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180076900  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180076907  jb      short loc_18007692C
0x180076909  mov     rcx, cs:WPP_GLOBAL_Control
0x180076910  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x180076917  mov     edx, 11h
0x18007691c  mov     [rsp+68h+var_48], ebp
0x180076920  mov     r9, r15
0x180076923  mov     rcx, [rcx+10h]
0x180076927  call    WPP_SF_qD
0x18007692c  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x180076934  jnz     short loc_18007696D
0x180076936  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007693d  nop     dword ptr [rax+rax+00h]
0x180076942  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180076949  mov     rcx, rax
0x18007694c  test    rax, rax
0x18007694f  jz      short loc_180076966
0x180076951  mov     rax, [rax]
0x180076954  mov     edx, 7F0h
0x180076959  mov     rax, [rax+8]
0x18007695d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076962  test    eax, eax
0x180076964  jnz     short loc_18007696D
0x180076966  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18007696d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180076974  cmp     byte ptr [rcx+8], 0
0x180076978  jz      short loc_18007699F
0x18007697a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007697f  cmp     [rax+7CCh], ebp
0x180076985  jz      short loc_18007699F
0x180076987  mov     r9d, ebp; int
0x18007698a  lea     rdx, aCmfpropvariant_8; "CMFPropVariant::Copy"
0x180076991  mov     r8d, 0ECh; int
0x180076997  mov     rcx, rax; this
0x18007699a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007699f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800769a6  jb      short loc_1800769CB
0x1800769a8  mov     edx, 12h
0x1800769ad  mov     [rsp+68h+var_48], ebp
0x1800769b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800769b8  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x1800769bf  mov     r9, r15
0x1800769c2  mov     rcx, [rcx+10h]
0x1800769c6  call    WPP_SF_qD
0x1800769cb  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x1800769d3  jnz     short loc_180076A0C
0x1800769d5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800769dc  nop     dword ptr [rax+rax+00h]
0x1800769e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800769e8  mov     rcx, rax
0x1800769eb  test    rax, rax
0x1800769ee  jz      short loc_180076A05
0x1800769f0  mov     rax, [rax]
0x1800769f3  mov     edx, 7F0h
0x1800769f8  mov     rax, [rax+8]
0x1800769fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076a01  test    eax, eax
0x180076a03  jnz     short loc_180076A0C
0x180076a05  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180076a0c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180076a13  cmp     byte ptr [rcx+8], 0
0x180076a17  jz      short loc_180076A3E
0x180076a19  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180076a1e  cmp     [rax+7CCh], esi
0x180076a24  jz      short loc_180076A3E
0x180076a26  mov     r9d, esi; int
0x180076a29  lea     rdx, aCmfpropvariant_8; "CMFPropVariant::Copy"
0x180076a30  mov     r8d, 0F7h; int
0x180076a36  mov     rcx, rax; this
0x180076a39  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180076a3e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180076a45  jb      short loc_180076A6A
0x180076a47  mov     edx, 14h
0x180076a4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180076a53  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x180076a5a  mov     r9, r15
0x180076a5d  mov     [rsp+68h+var_48], esi
0x180076a61  mov     rcx, [rcx+10h]
0x180076a65  call    WPP_SF_qD
0x180076a6a  lea     rcx, [rsp+68h+var_38]; this
0x180076a6f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180076a74  mov     rbp, [rsp+68h+arg_10]
0x180076a7c  mov     eax, esi
0x180076a7e  add     rsp, 40h
0x180076a82  pop     r15
0x180076a84  pop     r14
0x180076a86  pop     r12
0x180076a88  pop     rdi
0x180076a89  pop     rsi
0x180076a8a  retn
```
