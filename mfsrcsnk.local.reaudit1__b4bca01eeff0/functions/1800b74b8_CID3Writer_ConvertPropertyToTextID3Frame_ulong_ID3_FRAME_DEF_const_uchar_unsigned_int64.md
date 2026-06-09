# CID3Writer::ConvertPropertyToTextID3Frame(ulong,ID3_FRAME_DEF const *,uchar * *,unsigned __int64 *)

- ea: `0x1800b74b8`
- end: `0x1800b79ef`
- name: `?ConvertPropertyToTextID3Frame@CID3Writer@@IEAAJKPEBUID3_FRAME_DEF@@PEAPEAEPEA_K@Z`
- size: `1335`
- prototype: `__int64 __usercall@<rax>(CID3Writer *__hidden this@<rcx>, unsigned int@<edx>, const struct ID3_FRAME_DEF *@<r8>, unsigned __int8 **@<r9>, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1801297b8`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180079680`
- `0x1800b74b8`
- `0x180110a88`
- `0x180110ad4`
- `0x180110ed0`
- `0x18012910c`
- `0x1801291f0`
- `0x180129b30`
- `0x18012a094`
- `0x18016b2b8`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b75d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b76a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b774e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b786d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b7940`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b75d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b76a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b774e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b786d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b7940`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b7562`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b7562`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800b77f4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800b77f4`

## string_xrefs

- `0x1800b74f4`: `CID3Writer::ConvertPropertyToTextID3Frame`
- `0x1800b7632`: `CID3Writer::ConvertPropertyToTextID3Frame`
- `0x1800b76fd`: `CID3Writer::ConvertPropertyToTextID3Frame`
- `0x1800b77ab`: `CID3Writer::ConvertPropertyToTextID3Frame`
- `0x1800b78ca`: `CID3Writer::ConvertPropertyToTextID3Frame`
- `0x1800b799d`: `CID3Writer::ConvertPropertyToTextID3Frame`

## pseudocode

```c
__int64 __fastcall CID3Writer::ConvertPropertyToTextID3Frame(
        CID3Writer *this,
        unsigned int a2,
        const struct ID3_FRAME_DEF *a3,
        unsigned __int8 **a4,
        unsigned __int64 *a5)
{
  __int64 v6; // rdi
  void *v9; // r14
  bool v10; // zf
  __int64 v11; // rcx
  const unsigned __int16 *v12; // rcx
  unsigned __int16 *v13; // rax
  PROPVARIANT *p_pvar; // rax
  __int64 v15; // rdx
  int StringSize; // ebx
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned __int64 v20; // rbx
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  unsigned __int64 v24; // r14
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v29; // rdx
  void *v30; // rdi
  wchar_t *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  wchar_t *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  unsigned __int16 v38; // [rsp+30h] [rbp-41h] BYREF
  void *v39; // [rsp+38h] [rbp-39h]
  unsigned __int64 v40; // [rsp+40h] [rbp-31h] BYREF
  PROPVARIANT pvar; // [rsp+48h] [rbp-29h] BYREF
  _QWORD v42[4]; // [rsp+60h] [rbp-11h] BYREF

  v6 = a2;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v38,
    "CID3Writer::ConvertPropertyToTextID3Frame",
    478);
  v9 = 0;
  v10 = *(_DWORD *)a3 == 36;
  v39 = 0;
  v40 = 0;
  memset(&pvar, 0, sizeof(pvar));
  if ( v10
    && (v11 = *((_QWORD *)this + 9), *(_WORD *)(v11 + 24 * v6) == 31)
    && (v12 = *(const unsigned __int16 **)(v11 + 24 * v6 + 8), v38 = 0, (int)MapGenreStringToGenreID(v12, &v38, 0) >= 0)
    && (pvar.vt = 31, v13 = (unsigned __int16 *)CoTaskMemAlloc(2LL * v38), (pvar.hVal.QuadPart = (LONGLONG)v13) != 0)
    && (int)MapGenreStringToGenreID(*(const unsigned __int16 **)(*((_QWORD *)this + 9) + 24 * v6 + 8), &v38, v13) >= 0 )
  {
    p_pvar = &pvar;
  }
  else
  {
    p_pvar = (PROPVARIANT *)(*((_QWORD *)this + 9) + 24 * v6);
  }
  v42[0] = p_pvar;
  memset(&v42[1], 0, 24);
  StringSize = CPropVariantID3ConversionHelper::GetStringSize((CPropVariantID3ConversionHelper *)v42, &v40);
  if ( StringSize < 0 )
  {
    v17 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
      CallStackTracing::s_wpInstance = v18;
      if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
      {
        v17 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v17 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v17 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != StringSize )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CID3Writer::ConvertPropertyToTextID3Frame",
          518,
          StringSize);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        &WPP_02bf30fd61593fcad53f801c1bfe75a2_Traceguids,
        this,
        StringSize);
    goto LABEL_43;
  }
  v20 = v40 + 1;
  if ( v40 + 1 < v40 )
  {
    v21 = (wchar_t *)CallStackTracing::s_wpInstance;
    StringSize = -2147024362;
    if ( !CallStackTracing::s_wpInstance )
    {
      v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
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
      if ( *((_DWORD *)v23 + 499) != -2147024362 )
        CallStackContext::TraceFailure(v23, "CID3Writer::ConvertPropertyToTextID3Frame", 519, -2147024362);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        &WPP_02bf30fd61593fcad53f801c1bfe75a2_Traceguids,
        this,
        -2147024362);
    goto LABEL_43;
  }
  v24 = v40 + 11;
  if ( v20 >= 0xFFFFFFFFFFFFFFF6uLL )
  {
    v25 = (wchar_t *)CallStackTracing::s_wpInstance;
    StringSize = -2147024362;
    if ( !CallStackTracing::s_wpInstance )
    {
      v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
      CallStackTracing::s_wpInstance = v26;
      if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
      {
        v25 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v25 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v25 + 8) )
    {
      v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
      if ( *((_DWORD *)v27 + 499) != -2147024362 )
        CallStackContext::TraceFailure(v27, "CID3Writer::ConvertPropertyToTextID3Frame", 520, -2147024362);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        &WPP_02bf30fd61593fcad53f801c1bfe75a2_Traceguids,
        this,
        -2147024362);
LABEL_42:
    v9 = v39;
    goto LABEL_43;
  }
  v30 = operator new[](v40 + 11);
  if ( !v30 )
  {
    v31 = (wchar_t *)CallStackTracing::s_wpInstance;
    StringSize = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
      CallStackTracing::s_wpInstance = v32;
      if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
      {
        v31 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v31 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v31 + 8) )
    {
      v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
      if ( *((_DWORD *)v33 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v33, "CID3Writer::ConvertPropertyToTextID3Frame", 522, -2147024882);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        &WPP_02bf30fd61593fcad53f801c1bfe75a2_Traceguids,
        this,
        -2147024882);
    goto LABEL_42;
  }
  *(_DWORD *)v30 = **((_DWORD **)a3 + 2);
  *((_DWORD *)v30 + 1) = CID3Writer::AdjustSize(this, v20);
  *((_WORD *)v30 + 4) = 0;
  *((_BYTE *)v30 + 10) = 1;
  StringSize = CPropVariantID3ConversionHelper::CopyStringToBuffer(
                 (CPropVariantID3ConversionHelper *)v42,
                 (unsigned __int8 *)v30 + 11,
                 v20 - 1);
  if ( StringSize >= 0 )
  {
    *a4 = (unsigned __int8 *)v30;
    *a5 = v24;
  }
  else
  {
    v35 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34);
      CallStackTracing::s_wpInstance = v36;
      if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
      {
        v35 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v35 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v35 + 8) )
    {
      v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
      if ( *((_DWORD *)v37 + 499) != StringSize )
        CallStackContext::TraceFailure(v37, "CID3Writer::ConvertPropertyToTextID3Frame", 536, StringSize);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        44,
        &WPP_02bf30fd61593fcad53f801c1bfe75a2_Traceguids,
        this,
        StringSize);
  }
  v9 = v30;
LABEL_43:
  PropVariantClear(&pvar);
  if ( StringSize < 0 )
    operator delete(v9);
  CPropVariantID3ConversionHelper::~CPropVariantID3ConversionHelper((CPropVariantID3ConversionHelper *)v42);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v38);
  return (unsigned int)StringSize;
}

```

## disassembly

```asm
0x1800b74b8  mov     [rsp-8+arg_10], rbx
0x1800b74bd  push    rbp
0x1800b74be  push    rsi
0x1800b74bf  push    rdi
0x1800b74c0  push    r12
0x1800b74c2  push    r13
0x1800b74c4  push    r14
0x1800b74c6  push    r15
0x1800b74c8  lea     rbp, [rsp-1Fh]
0x1800b74cd  sub     rsp, 90h
0x1800b74d4  mov     rax, cs:__security_cookie
0x1800b74db  xor     rax, rsp
0x1800b74de  mov     [rbp+4Fh+var_40], rax
0x1800b74e2  mov     r12, [rbp+4Fh+arg_20]
0x1800b74e6  mov     r13, r8
0x1800b74e9  mov     edi, edx
0x1800b74eb  mov     rsi, rcx
0x1800b74ee  mov     r8d, 1DEh; int
0x1800b74f4  lea     rdx, aCid3writerConv; "CID3Writer::ConvertPropertyToTextID3Fra"...
0x1800b74fb  lea     rcx, [rbp+4Fh+var_90]; this
0x1800b74ff  mov     r15, r9
0x1800b7502  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b7507  xor     r14d, r14d
0x1800b750a  xor     eax, eax
0x1800b750c  cmp     dword ptr [r13+0], 24h ; '$'
0x1800b7511  xorps   xmm0, xmm0
0x1800b7514  mov     [rbp+4Fh+var_88], r14
0x1800b7518  mov     [rbp+4Fh+var_80], r14
0x1800b751c  movups  xmmword ptr [rbp+4Fh+pvar], xmm0
0x1800b7520  mov     qword ptr [rbp+4Fh+pvar+10h], rax
0x1800b7524  jnz     short loc_1800B7596
0x1800b7526  mov     rcx, [rsi+48h]
0x1800b752a  lea     rbx, [rdi+rdi*2]
0x1800b752e  lea     eax, [r14+1Fh]
0x1800b7532  cmp     [rcx+rbx*8], ax
0x1800b7536  jnz     short loc_1800B7596
0x1800b7538  mov     rcx, [rcx+rbx*8+8]; unsigned __int16 *
0x1800b753d  lea     rdx, [rbp+4Fh+var_90]; unsigned __int16 *
0x1800b7541  xor     eax, eax
0x1800b7543  xor     r8d, r8d; unsigned __int16 *
0x1800b7546  mov     [rbp+4Fh+var_90], ax
0x1800b754a  call    ?MapGenreStringToGenreID@@YAJPEBGPEAG1@Z; MapGenreStringToGenreID(ushort const *,ushort *,ushort *)
0x1800b754f  test    eax, eax
0x1800b7551  js      short loc_1800B7596
0x1800b7553  movzx   ecx, [rbp+4Fh+var_90]
0x1800b7557  lea     eax, [r14+1Fh]
0x1800b755b  add     rcx, rcx; cb
0x1800b755e  mov     word ptr [rbp+4Fh+pvar], ax
0x1800b7562  call    cs:__imp_CoTaskMemAlloc
0x1800b7569  nop     dword ptr [rax+rax+00h]
0x1800b756e  mov     qword ptr [rbp+4Fh+pvar+8], rax
0x1800b7572  test    rax, rax
0x1800b7575  jz      short loc_1800B7596
0x1800b7577  mov     rcx, [rsi+48h]
0x1800b757b  lea     rdx, [rbp+4Fh+var_90]; unsigned __int16 *
0x1800b757f  mov     r8, rax; unsigned __int16 *
0x1800b7582  mov     rcx, [rcx+rbx*8+8]; unsigned __int16 *
0x1800b7587  call    ?MapGenreStringToGenreID@@YAJPEBGPEAG1@Z; MapGenreStringToGenreID(ushort const *,ushort *,ushort *)
0x1800b758c  test    eax, eax
0x1800b758e  js      short loc_1800B7596
0x1800b7590  lea     rax, [rbp+4Fh+pvar]
0x1800b7594  jmp     short loc_1800B75A2
0x1800b7596  mov     rax, [rsi+48h]
0x1800b759a  lea     rcx, [rdi+rdi*2]
0x1800b759e  lea     rax, [rax+rcx*8]
0x1800b75a2  lea     rdx, [rbp+4Fh+var_80]; unsigned __int64 *
0x1800b75a6  mov     [rbp+4Fh+var_60], rax
0x1800b75aa  lea     rcx, [rbp+4Fh+var_60]; this
0x1800b75ae  mov     [rbp+4Fh+var_58], r14
0x1800b75b2  mov     [rbp+4Fh+var_50], r14
0x1800b75b6  mov     [rbp+4Fh+var_48], r14
0x1800b75ba  call    ?GetStringSize@CPropVariantID3ConversionHelper@@QEAAJPEA_K@Z; CPropVariantID3ConversionHelper::GetStringSize(unsigned __int64 *)
0x1800b75bf  mov     ebx, eax
0x1800b75c1  test    eax, eax
0x1800b75c3  jns     loc_1800B767C
0x1800b75c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b75d0  test    rcx, rcx
0x1800b75d3  jnz     short loc_1800B761C
0x1800b75d5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b75dc  nop     dword ptr [rax+rax+00h]
0x1800b75e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b75e8  mov     rcx, rax
0x1800b75eb  test    rax, rax
0x1800b75ee  jz      short loc_1800B760E
0x1800b75f0  mov     rax, [rax]
0x1800b75f3  mov     edx, 7F0h
0x1800b75f8  mov     rax, [rax+8]
0x1800b75fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7601  test    eax, eax
0x1800b7603  jz      short loc_1800B760E
0x1800b7605  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b760c  jmp     short loc_1800B761C
0x1800b760e  lea     rcx, qword_1801B97E0; this
0x1800b7615  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b761c  cmp     [rcx+8], r14b
0x1800b7620  jz      short loc_1800B7647
0x1800b7622  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b7627  cmp     [rax+7CCh], ebx
0x1800b762d  jz      short loc_1800B7647
0x1800b762f  mov     r9d, ebx; int
0x1800b7632  lea     rdx, aCid3writerConv; "CID3Writer::ConvertPropertyToTextID3Fra"...
0x1800b7639  mov     r8d, 206h; int
0x1800b763f  mov     rcx, rax; this
0x1800b7642  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b7647  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b764e  jb      loc_1800B77F0
0x1800b7654  mov     edx, 28h ; '('
0x1800b7659  mov     [rsp+0C0h+var_A0], ebx
0x1800b765d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b7664  lea     r8, WPP_02bf30fd61593fcad53f801c1bfe75a2_Traceguids
0x1800b766b  mov     r9, rsi
0x1800b766e  mov     rcx, [rcx+10h]
0x1800b7672  call    WPP_SF_qD
0x1800b7677  jmp     loc_1800B77F0
0x1800b767c  mov     rax, [rbp+4Fh+var_80]
0x1800b7680  lea     rbx, [rax+1]
0x1800b7684  cmp     rbx, rax
0x1800b7687  jnb     loc_1800B772D
0x1800b768d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7694  mov     edi, 80070216h
0x1800b7699  mov     ebx, edi
0x1800b769b  test    rcx, rcx
0x1800b769e  jnz     short loc_1800B76E7
0x1800b76a0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b76a7  nop     dword ptr [rax+rax+00h]
0x1800b76ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b76b3  mov     rcx, rax
0x1800b76b6  test    rax, rax
0x1800b76b9  jz      short loc_1800B76D9
0x1800b76bb  mov     rax, [rax]
0x1800b76be  mov     edx, 7F0h
0x1800b76c3  mov     rax, [rax+8]
0x1800b76c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b76cc  test    eax, eax
0x1800b76ce  jz      short loc_1800B76D9
0x1800b76d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b76d7  jmp     short loc_1800B76E7
0x1800b76d9  lea     rcx, qword_1801B97E0; this
0x1800b76e0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b76e7  cmp     [rcx+8], r14b
0x1800b76eb  jz      short loc_1800B7712
0x1800b76ed  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b76f2  cmp     [rax+7CCh], edi
0x1800b76f8  jz      short loc_1800B7712
0x1800b76fa  mov     r9d, edi; int
0x1800b76fd  lea     rdx, aCid3writerConv; "CID3Writer::ConvertPropertyToTextID3Fra"...
0x1800b7704  mov     r8d, 207h; int
0x1800b770a  mov     rcx, rax; this
0x1800b770d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b7712  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b7719  jb      loc_1800B77F0
0x1800b771f  mov     edx, 29h ; ')'
0x1800b7724  mov     [rsp+0C0h+var_A0], edi
0x1800b7728  jmp     loc_1800B765D
0x1800b772d  lea     r14, [rbx+0Ah]
0x1800b7731  cmp     r14, 0Ah
0x1800b7735  jnb     loc_1800B7848
0x1800b773b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7742  mov     edi, 80070216h
0x1800b7747  mov     ebx, edi
0x1800b7749  test    rcx, rcx
0x1800b774c  jnz     short loc_1800B7795
0x1800b774e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b7755  nop     dword ptr [rax+rax+00h]
0x1800b775a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7761  mov     rcx, rax
0x1800b7764  test    rax, rax
0x1800b7767  jz      short loc_1800B7787
0x1800b7769  mov     rax, [rax]
0x1800b776c  mov     edx, 7F0h
0x1800b7771  mov     rax, [rax+8]
0x1800b7775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b777a  test    eax, eax
0x1800b777c  jz      short loc_1800B7787
0x1800b777e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7785  jmp     short loc_1800B7795
0x1800b7787  lea     rcx, qword_1801B97E0; this
0x1800b778e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7795  cmp     byte ptr [rcx+8], 0
0x1800b7799  jz      short loc_1800B77C0
0x1800b779b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b77a0  cmp     [rax+7CCh], edi
0x1800b77a6  jz      short loc_1800B77C0
0x1800b77a8  mov     r9d, edi; int
0x1800b77ab  lea     rdx, aCid3writerConv; "CID3Writer::ConvertPropertyToTextID3Fra"...
0x1800b77b2  mov     r8d, 208h; int
0x1800b77b8  mov     rcx, rax; this
0x1800b77bb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b77c0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b77c7  jb      short loc_1800B77EC
0x1800b77c9  mov     edx, 2Ah ; '*'
0x1800b77ce  mov     [rsp+0C0h+var_A0], edi
0x1800b77d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b77d9  lea     r8, WPP_02bf30fd61593fcad53f801c1bfe75a2_Traceguids
0x1800b77e0  mov     r9, rsi
0x1800b77e3  mov     rcx, [rcx+10h]
0x1800b77e7  call    WPP_SF_qD
0x1800b77ec  mov     r14, [rbp+4Fh+var_88]
0x1800b77f0  lea     rcx, [rbp+4Fh+pvar]; pvar
0x1800b77f4  call    cs:__imp_PropVariantClear
0x1800b77fb  nop     dword ptr [rax+rax+00h]
0x1800b7800  test    ebx, ebx
0x1800b7802  jns     short loc_1800B780C
0x1800b7804  mov     rcx, r14; Block
0x1800b7807  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800b780c  lea     rcx, [rbp+4Fh+var_60]; this
0x1800b7810  call    ??1CPropVariantID3ConversionHelper@@QEAA@XZ; CPropVariantID3ConversionHelper::~CPropVariantID3ConversionHelper(void)
0x1800b7815  lea     rcx, [rbp+4Fh+var_90]; this
0x1800b7819  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800b781e  mov     eax, ebx
0x1800b7820  mov     rcx, [rbp+4Fh+var_40]
0x1800b7824  xor     rcx, rsp; StackCookie
0x1800b7827  call    __security_check_cookie
0x1800b782c  mov     rbx, [rsp+0C0h+arg_10]
0x1800b7834  add     rsp, 90h
0x1800b783b  pop     r15
0x1800b783d  pop     r14
0x1800b783f  pop     r13
0x1800b7841  pop     r12
0x1800b7843  pop     rdi
0x1800b7844  pop     rsi
0x1800b7845  pop     rbp
0x1800b7846  retn
0x1800b7848  mov     rcx, r14; unsigned __int64
0x1800b784b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800b7850  mov     rdi, rax
0x1800b7853  test    rax, rax
0x1800b7856  jnz     loc_1800B78FA
0x1800b785c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7863  mov     ebx, 8007000Eh
0x1800b7868  test    rcx, rcx
0x1800b786b  jnz     short loc_1800B78B4
0x1800b786d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b7874  nop     dword ptr [rax+rax+00h]
0x1800b7879  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7880  mov     rcx, rax
0x1800b7883  test    rax, rax
0x1800b7886  jz      short loc_1800B78A6
0x1800b7888  mov     rax, [rax]
0x1800b788b  mov     edx, 7F0h
0x1800b7890  mov     rax, [rax+8]
0x1800b7894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7899  test    eax, eax
0x1800b789b  jz      short loc_1800B78A6
0x1800b789d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b78a4  jmp     short loc_1800B78B4
0x1800b78a6  lea     rcx, qword_1801B97E0; this
0x1800b78ad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b78b4  cmp     byte ptr [rcx+8], 0
0x1800b78b8  jz      short loc_1800B78DF
0x1800b78ba  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b78bf  cmp     [rax+7CCh], ebx
0x1800b78c5  jz      short loc_1800B78DF
0x1800b78c7  mov     r9d, ebx; int
0x1800b78ca  lea     rdx, aCid3writerConv; "CID3Writer::ConvertPropertyToTextID3Fra"...
0x1800b78d1  mov     r8d, 20Ah; int
0x1800b78d7  mov     rcx, rax; this
0x1800b78da  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b78df  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b78e6  jb      loc_1800B77EC
0x1800b78ec  mov     edx, 2Bh ; '+'
0x1800b78f1  mov     [rsp+0C0h+var_A0], ebx
0x1800b78f5  jmp     loc_1800B77D2
0x1800b78fa  mov     rax, [r13+10h]
0x1800b78fe  mov     edx, ebx; unsigned int
0x1800b7900  mov     ecx, [rax]
0x1800b7902  mov     [rdi], ecx
0x1800b7904  mov     rcx, rsi; this
0x1800b7907  call    ?AdjustSize@CID3Writer@@IEAAII@Z; CID3Writer::AdjustSize(uint)
0x1800b790c  mov     [rdi+4], eax
0x1800b790f  lea     r8, [rbx-1]; unsigned __int64
0x1800b7913  xor     eax, eax
0x1800b7915  lea     rdx, [rdi+0Bh]; unsigned __int8 *
0x1800b7919  mov     [rdi+8], ax
0x1800b791d  lea     rcx, [rbp+4Fh+var_60]; this
0x1800b7921  mov     byte ptr [rdi+0Ah], 1
0x1800b7925  call    ?CopyStringToBuffer@CPropVariantID3ConversionHelper@@QEAAJPEAE_K@Z; CPropVariantID3ConversionHelper::CopyStringToBuffer(uchar *,unsigned __int64)
0x1800b792a  mov     ebx, eax
0x1800b792c  test    eax, eax
0x1800b792e  jns     loc_1800B79E6
0x1800b7934  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b793b  test    rcx, rcx
0x1800b793e  jnz     short loc_1800B7987
0x1800b7940  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b7947  nop     dword ptr [rax+rax+00h]
0x1800b794c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7953  mov     rcx, rax
0x1800b7956  test    rax, rax
0x1800b7959  jz      short loc_1800B7979
0x1800b795b  mov     rax, [rax]
0x1800b795e  mov     edx, 7F0h
0x1800b7963  mov     rax, [rax+8]
0x1800b7967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b796c  test    eax, eax
0x1800b796e  jz      short loc_1800B7979
0x1800b7970  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7977  jmp     short loc_1800B7987
0x1800b7979  lea     rcx, qword_1801B97E0; this
0x1800b7980  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b7987  cmp     byte ptr [rcx+8], 0
  ... truncated ...
```
