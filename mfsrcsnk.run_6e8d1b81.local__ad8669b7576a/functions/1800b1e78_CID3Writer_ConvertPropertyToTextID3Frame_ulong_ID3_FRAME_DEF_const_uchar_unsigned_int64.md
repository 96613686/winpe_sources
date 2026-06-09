# CID3Writer::ConvertPropertyToTextID3Frame(ulong,ID3_FRAME_DEF const *,uchar * *,unsigned __int64 *)

- ea: `0x1800b1e78`
- end: `0x1800b2384`
- name: `?ConvertPropertyToTextID3Frame@CID3Writer@@IEAAJKPEBUID3_FRAME_DEF@@PEAPEAEPEA_K@Z`
- size: `1292`
- prototype: `__int64 __usercall@<rax>(CID3Writer *__hidden this@<rcx>, unsigned int@<edx>, const struct ID3_FRAME_DEF *@<r8>, unsigned __int8 **@<r9>, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18012296c`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180073b14`
- `0x1800b1e78`
- `0x18010959c`
- `0x1801095e8`
- `0x1801099f0`
- `0x180122308`
- `0x1801223e0`
- `0x180122cc8`
- `0x180123210`
- `0x1801624a0`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1f8f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b2054`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b20fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b220e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b22db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1f8f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b2054`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b20fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b220e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b22db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b1f22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b1f22`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800b219c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800b219c`

## string_xrefs

- `0x1800b1eb4`: `CID3Writer::ConvertPropertyToTextID3Frame`
- `0x1800b1fe6`: `CID3Writer::ConvertPropertyToTextID3Frame`
- `0x1800b20ab`: `CID3Writer::ConvertPropertyToTextID3Frame`
- `0x1800b2153`: `CID3Writer::ConvertPropertyToTextID3Frame`
- `0x1800b2265`: `CID3Writer::ConvertPropertyToTextID3Frame`
- `0x1800b2332`: `CID3Writer::ConvertPropertyToTextID3Frame`

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
        v17 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v21 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v25 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v31 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v35 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
0x1800b1e78  mov     [rsp-8+arg_10], rbx
0x1800b1e7d  push    rbp
0x1800b1e7e  push    rsi
0x1800b1e7f  push    rdi
0x1800b1e80  push    r12
0x1800b1e82  push    r13
0x1800b1e84  push    r14
0x1800b1e86  push    r15
0x1800b1e88  lea     rbp, [rsp-1Fh]
0x1800b1e8d  sub     rsp, 90h
0x1800b1e94  mov     rax, cs:__security_cookie
0x1800b1e9b  xor     rax, rsp
0x1800b1e9e  mov     [rbp+4Fh+var_40], rax
0x1800b1ea2  mov     r12, [rbp+4Fh+arg_20]
0x1800b1ea6  mov     r13, r8
0x1800b1ea9  mov     edi, edx
0x1800b1eab  mov     rsi, rcx
0x1800b1eae  mov     r8d, 1DEh; int
0x1800b1eb4  lea     rdx, aCid3writerConv; "CID3Writer::ConvertPropertyToTextID3Fra"...
0x1800b1ebb  lea     rcx, [rbp+4Fh+var_90]; this
0x1800b1ebf  mov     r15, r9
0x1800b1ec2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b1ec7  xor     r14d, r14d
0x1800b1eca  xor     eax, eax
0x1800b1ecc  cmp     dword ptr [r13+0], 24h ; '$'
0x1800b1ed1  xorps   xmm0, xmm0
0x1800b1ed4  mov     [rbp+4Fh+var_88], r14
0x1800b1ed8  mov     [rbp+4Fh+var_80], r14
0x1800b1edc  movups  xmmword ptr [rbp+4Fh+pvar], xmm0
0x1800b1ee0  mov     qword ptr [rbp+4Fh+pvar+10h], rax
0x1800b1ee4  jnz     short loc_1800B1F50
0x1800b1ee6  mov     rcx, [rsi+48h]
0x1800b1eea  lea     rbx, [rdi+rdi*2]
0x1800b1eee  lea     eax, [r14+1Fh]
0x1800b1ef2  cmp     [rcx+rbx*8], ax
0x1800b1ef6  jnz     short loc_1800B1F50
0x1800b1ef8  mov     rcx, [rcx+rbx*8+8]; unsigned __int16 *
0x1800b1efd  lea     rdx, [rbp+4Fh+var_90]; unsigned __int16 *
0x1800b1f01  xor     eax, eax
0x1800b1f03  xor     r8d, r8d; unsigned __int16 *
0x1800b1f06  mov     [rbp+4Fh+var_90], ax
0x1800b1f0a  call    ?MapGenreStringToGenreID@@YAJPEBGPEAG1@Z; MapGenreStringToGenreID(ushort const *,ushort *,ushort *)
0x1800b1f0f  test    eax, eax
0x1800b1f11  js      short loc_1800B1F50
0x1800b1f13  movzx   ecx, [rbp+4Fh+var_90]
0x1800b1f17  lea     eax, [r14+1Fh]
0x1800b1f1b  add     rcx, rcx; cb
0x1800b1f1e  mov     word ptr [rbp+4Fh+pvar], ax
0x1800b1f22  call    cs:__imp_CoTaskMemAlloc
0x1800b1f28  mov     qword ptr [rbp+4Fh+pvar+8], rax
0x1800b1f2c  test    rax, rax
0x1800b1f2f  jz      short loc_1800B1F50
0x1800b1f31  mov     rcx, [rsi+48h]
0x1800b1f35  lea     rdx, [rbp+4Fh+var_90]; unsigned __int16 *
0x1800b1f39  mov     r8, rax; unsigned __int16 *
0x1800b1f3c  mov     rcx, [rcx+rbx*8+8]; unsigned __int16 *
0x1800b1f41  call    ?MapGenreStringToGenreID@@YAJPEBGPEAG1@Z; MapGenreStringToGenreID(ushort const *,ushort *,ushort *)
0x1800b1f46  test    eax, eax
0x1800b1f48  js      short loc_1800B1F50
0x1800b1f4a  lea     rax, [rbp+4Fh+pvar]
0x1800b1f4e  jmp     short loc_1800B1F5C
0x1800b1f50  mov     rax, [rsi+48h]
0x1800b1f54  lea     rcx, [rdi+rdi*2]
0x1800b1f58  lea     rax, [rax+rcx*8]
0x1800b1f5c  lea     rdx, [rbp+4Fh+var_80]; unsigned __int64 *
0x1800b1f60  mov     [rbp+4Fh+var_60], rax
0x1800b1f64  lea     rcx, [rbp+4Fh+var_60]; this
0x1800b1f68  mov     [rbp+4Fh+var_58], r14
0x1800b1f6c  mov     [rbp+4Fh+var_50], r14
0x1800b1f70  mov     [rbp+4Fh+var_48], r14
0x1800b1f74  call    ?GetStringSize@CPropVariantID3ConversionHelper@@QEAAJPEA_K@Z; CPropVariantID3ConversionHelper::GetStringSize(unsigned __int64 *)
0x1800b1f79  mov     ebx, eax
0x1800b1f7b  test    eax, eax
0x1800b1f7d  jns     loc_1800B2030
0x1800b1f83  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1f8a  test    rcx, rcx
0x1800b1f8d  jnz     short loc_1800B1FD0
0x1800b1f8f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b1f95  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1f9c  mov     rcx, rax
0x1800b1f9f  test    rax, rax
0x1800b1fa2  jz      short loc_1800B1FC2
0x1800b1fa4  mov     rax, [rax]
0x1800b1fa7  mov     edx, 7F0h
0x1800b1fac  mov     rax, [rax+8]
0x1800b1fb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1fb5  test    eax, eax
0x1800b1fb7  jz      short loc_1800B1FC2
0x1800b1fb9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1fc0  jmp     short loc_1800B1FD0
0x1800b1fc2  lea     rcx, qword_1801B07E0; this
0x1800b1fc9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1fd0  cmp     [rcx+8], r14b
0x1800b1fd4  jz      short loc_1800B1FFB
0x1800b1fd6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b1fdb  cmp     [rax+7CCh], ebx
0x1800b1fe1  jz      short loc_1800B1FFB
0x1800b1fe3  mov     r9d, ebx; int
0x1800b1fe6  lea     rdx, aCid3writerConv; "CID3Writer::ConvertPropertyToTextID3Fra"...
0x1800b1fed  mov     r8d, 206h; int
0x1800b1ff3  mov     rcx, rax; this
0x1800b1ff6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b1ffb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b2002  jb      loc_1800B2198
0x1800b2008  mov     edx, 28h ; '('
0x1800b200d  mov     [rsp+0C0h+var_A0], ebx
0x1800b2011  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2018  lea     r8, WPP_02bf30fd61593fcad53f801c1bfe75a2_Traceguids
0x1800b201f  mov     r9, rsi
0x1800b2022  mov     rcx, [rcx+10h]
0x1800b2026  call    WPP_SF_qD
0x1800b202b  jmp     loc_1800B2198
0x1800b2030  mov     rax, [rbp+4Fh+var_80]
0x1800b2034  lea     rbx, [rax+1]
0x1800b2038  cmp     rbx, rax
0x1800b203b  jnb     loc_1800B20DB
0x1800b2041  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b2048  mov     edi, 80070216h
0x1800b204d  mov     ebx, edi
0x1800b204f  test    rcx, rcx
0x1800b2052  jnz     short loc_1800B2095
0x1800b2054  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b205a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b2061  mov     rcx, rax
0x1800b2064  test    rax, rax
0x1800b2067  jz      short loc_1800B2087
0x1800b2069  mov     rax, [rax]
0x1800b206c  mov     edx, 7F0h
0x1800b2071  mov     rax, [rax+8]
0x1800b2075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b207a  test    eax, eax
0x1800b207c  jz      short loc_1800B2087
0x1800b207e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b2085  jmp     short loc_1800B2095
0x1800b2087  lea     rcx, qword_1801B07E0; this
0x1800b208e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b2095  cmp     [rcx+8], r14b
0x1800b2099  jz      short loc_1800B20C0
0x1800b209b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b20a0  cmp     [rax+7CCh], edi
0x1800b20a6  jz      short loc_1800B20C0
0x1800b20a8  mov     r9d, edi; int
0x1800b20ab  lea     rdx, aCid3writerConv; "CID3Writer::ConvertPropertyToTextID3Fra"...
0x1800b20b2  mov     r8d, 207h; int
0x1800b20b8  mov     rcx, rax; this
0x1800b20bb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b20c0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b20c7  jb      loc_1800B2198
0x1800b20cd  mov     edx, 29h ; ')'
0x1800b20d2  mov     [rsp+0C0h+var_A0], edi
0x1800b20d6  jmp     loc_1800B2011
0x1800b20db  lea     r14, [rbx+0Ah]
0x1800b20df  cmp     r14, 0Ah
0x1800b20e3  jnb     loc_1800B21E9
0x1800b20e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b20f0  mov     edi, 80070216h
0x1800b20f5  mov     ebx, edi
0x1800b20f7  test    rcx, rcx
0x1800b20fa  jnz     short loc_1800B213D
0x1800b20fc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b2102  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b2109  mov     rcx, rax
0x1800b210c  test    rax, rax
0x1800b210f  jz      short loc_1800B212F
0x1800b2111  mov     rax, [rax]
0x1800b2114  mov     edx, 7F0h
0x1800b2119  mov     rax, [rax+8]
0x1800b211d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2122  test    eax, eax
0x1800b2124  jz      short loc_1800B212F
0x1800b2126  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b212d  jmp     short loc_1800B213D
0x1800b212f  lea     rcx, qword_1801B07E0; this
0x1800b2136  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b213d  cmp     byte ptr [rcx+8], 0
0x1800b2141  jz      short loc_1800B2168
0x1800b2143  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b2148  cmp     [rax+7CCh], edi
0x1800b214e  jz      short loc_1800B2168
0x1800b2150  mov     r9d, edi; int
0x1800b2153  lea     rdx, aCid3writerConv; "CID3Writer::ConvertPropertyToTextID3Fra"...
0x1800b215a  mov     r8d, 208h; int
0x1800b2160  mov     rcx, rax; this
0x1800b2163  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b2168  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b216f  jb      short loc_1800B2194
0x1800b2171  mov     edx, 2Ah ; '*'
0x1800b2176  mov     [rsp+0C0h+var_A0], edi
0x1800b217a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2181  lea     r8, WPP_02bf30fd61593fcad53f801c1bfe75a2_Traceguids
0x1800b2188  mov     r9, rsi
0x1800b218b  mov     rcx, [rcx+10h]
0x1800b218f  call    WPP_SF_qD
0x1800b2194  mov     r14, [rbp+4Fh+var_88]
0x1800b2198  lea     rcx, [rbp+4Fh+pvar]; pvar
0x1800b219c  call    cs:__imp_PropVariantClear
0x1800b21a2  test    ebx, ebx
0x1800b21a4  jns     short loc_1800B21AE
0x1800b21a6  mov     rcx, r14; Block
0x1800b21a9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800b21ae  lea     rcx, [rbp+4Fh+var_60]; this
0x1800b21b2  call    ??1CPropVariantID3ConversionHelper@@QEAA@XZ; CPropVariantID3ConversionHelper::~CPropVariantID3ConversionHelper(void)
0x1800b21b7  lea     rcx, [rbp+4Fh+var_90]; this
0x1800b21bb  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800b21c0  mov     eax, ebx
0x1800b21c2  mov     rcx, [rbp+4Fh+var_40]
0x1800b21c6  xor     rcx, rsp; StackCookie
0x1800b21c9  call    __security_check_cookie
0x1800b21ce  mov     rbx, [rsp+0C0h+arg_10]
0x1800b21d6  add     rsp, 90h
0x1800b21dd  pop     r15
0x1800b21df  pop     r14
0x1800b21e1  pop     r13
0x1800b21e3  pop     r12
0x1800b21e5  pop     rdi
0x1800b21e6  pop     rsi
0x1800b21e7  pop     rbp
0x1800b21e8  retn
0x1800b21e9  mov     rcx, r14; unsigned __int64
0x1800b21ec  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800b21f1  mov     rdi, rax
0x1800b21f4  test    rax, rax
0x1800b21f7  jnz     loc_1800B2295
0x1800b21fd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b2204  mov     ebx, 8007000Eh
0x1800b2209  test    rcx, rcx
0x1800b220c  jnz     short loc_1800B224F
0x1800b220e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b2214  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b221b  mov     rcx, rax
0x1800b221e  test    rax, rax
0x1800b2221  jz      short loc_1800B2241
0x1800b2223  mov     rax, [rax]
0x1800b2226  mov     edx, 7F0h
0x1800b222b  mov     rax, [rax+8]
0x1800b222f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2234  test    eax, eax
0x1800b2236  jz      short loc_1800B2241
0x1800b2238  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b223f  jmp     short loc_1800B224F
0x1800b2241  lea     rcx, qword_1801B07E0; this
0x1800b2248  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b224f  cmp     byte ptr [rcx+8], 0
0x1800b2253  jz      short loc_1800B227A
0x1800b2255  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b225a  cmp     [rax+7CCh], ebx
0x1800b2260  jz      short loc_1800B227A
0x1800b2262  mov     r9d, ebx; int
0x1800b2265  lea     rdx, aCid3writerConv; "CID3Writer::ConvertPropertyToTextID3Fra"...
0x1800b226c  mov     r8d, 20Ah; int
0x1800b2272  mov     rcx, rax; this
0x1800b2275  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b227a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b2281  jb      loc_1800B2194
0x1800b2287  mov     edx, 2Bh ; '+'
0x1800b228c  mov     [rsp+0C0h+var_A0], ebx
0x1800b2290  jmp     loc_1800B217A
0x1800b2295  mov     rax, [r13+10h]
0x1800b2299  mov     edx, ebx; unsigned int
0x1800b229b  mov     ecx, [rax]
0x1800b229d  mov     [rdi], ecx
0x1800b229f  mov     rcx, rsi; this
0x1800b22a2  call    ?AdjustSize@CID3Writer@@IEAAII@Z; CID3Writer::AdjustSize(uint)
0x1800b22a7  mov     [rdi+4], eax
0x1800b22aa  lea     r8, [rbx-1]; unsigned __int64
0x1800b22ae  xor     eax, eax
0x1800b22b0  lea     rdx, [rdi+0Bh]; unsigned __int8 *
0x1800b22b4  mov     [rdi+8], ax
0x1800b22b8  lea     rcx, [rbp+4Fh+var_60]; this
0x1800b22bc  mov     byte ptr [rdi+0Ah], 1
0x1800b22c0  call    ?CopyStringToBuffer@CPropVariantID3ConversionHelper@@QEAAJPEAE_K@Z; CPropVariantID3ConversionHelper::CopyStringToBuffer(uchar *,unsigned __int64)
0x1800b22c5  mov     ebx, eax
0x1800b22c7  test    eax, eax
0x1800b22c9  jns     loc_1800B237B
0x1800b22cf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b22d6  test    rcx, rcx
0x1800b22d9  jnz     short loc_1800B231C
0x1800b22db  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b22e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b22e8  mov     rcx, rax
0x1800b22eb  test    rax, rax
0x1800b22ee  jz      short loc_1800B230E
0x1800b22f0  mov     rax, [rax]
0x1800b22f3  mov     edx, 7F0h
0x1800b22f8  mov     rax, [rax+8]
0x1800b22fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2301  test    eax, eax
0x1800b2303  jz      short loc_1800B230E
0x1800b2305  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b230c  jmp     short loc_1800B231C
0x1800b230e  lea     rcx, qword_1801B07E0; this
0x1800b2315  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b231c  cmp     byte ptr [rcx+8], 0
0x1800b2320  jz      short loc_1800B2347
0x1800b2322  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b2327  cmp     [rax+7CCh], ebx
0x1800b232d  jz      short loc_1800B2347
0x1800b232f  mov     r9d, ebx; int
0x1800b2332  lea     rdx, aCid3writerConv; "CID3Writer::ConvertPropertyToTextID3Fra"...
0x1800b2339  mov     r8d, 218h; int
  ... truncated ...
```
