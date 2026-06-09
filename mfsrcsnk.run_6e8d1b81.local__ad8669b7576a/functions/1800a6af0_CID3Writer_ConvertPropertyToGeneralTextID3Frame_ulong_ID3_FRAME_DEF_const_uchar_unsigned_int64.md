# CID3Writer::ConvertPropertyToGeneralTextID3Frame(ulong,ID3_FRAME_DEF const *,uchar * *,unsigned __int64 *)

- ea: `0x1800a6af0`
- end: `0x1800a7028`
- name: `?ConvertPropertyToGeneralTextID3Frame@CID3Writer@@IEAAJKPEBUID3_FRAME_DEF@@PEAPEAEPEA_K@Z`
- size: `1336`
- prototype: `__int64 __usercall@<rax>(CID3Writer *__hidden this@<rcx>, unsigned int@<edx>, const struct ID3_FRAME_DEF *@<r8>, unsigned __int8 **@<r9>, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x18012296c`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180073b14`
- `0x1800a6af0`
- `0x18010959c`
- `0x1801095e8`
- `0x1801099f0`
- `0x180122308`
- `0x1801223e0`
- `0x180122cc8`
- `0x180123210`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6e46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6e46`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x1800a6e38`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x1800a6e38`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6b87`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6c2e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6cd6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6d7e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6e6f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6f3f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6b87`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6c2e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6cd6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6d7e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6e6f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a6f3f`

## string_xrefs

- `0x1800a6b2f`: `CID3Writer::ConvertPropertyToGeneralTextID3Frame`
- `0x1800a6bde`: `CID3Writer::ConvertPropertyToGeneralTextID3Frame`
- `0x1800a6c85`: `CID3Writer::ConvertPropertyToGeneralTextID3Frame`
- `0x1800a6d2d`: `CID3Writer::ConvertPropertyToGeneralTextID3Frame`
- `0x1800a6dd5`: `CID3Writer::ConvertPropertyToGeneralTextID3Frame`
- `0x1800a6ec6`: `CID3Writer::ConvertPropertyToGeneralTextID3Frame`
- `0x1800a6f96`: `CID3Writer::ConvertPropertyToGeneralTextID3Frame`

## pseudocode

```c
__int64 __fastcall CID3Writer::ConvertPropertyToGeneralTextID3Frame(
        CID3Writer *this,
        unsigned int a2,
        const struct ID3_FRAME_DEF *a3,
        unsigned __int8 **a4,
        unsigned __int64 *a5)
{
  __int64 v6; // rbx
  __int64 v8; // rax
  __int64 v9; // rdx
  signed int StringSize; // ebx
  wchar_t *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v14; // rdx
  unsigned __int64 v15; // r14
  wchar_t *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  unsigned __int64 v20; // rsi
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  _DWORD *v24; // rax
  __int64 v25; // rdx
  _DWORD *v26; // rdi
  wchar_t *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  signed int LastError; // eax
  __int64 v31; // rdx
  wchar_t *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  unsigned int i; // edx
  __int64 v36; // rcx
  __int64 v37; // rdx
  wchar_t *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  _BYTE v42[8]; // [rsp+30h] [rbp-50h] BYREF
  void *Block; // [rsp+38h] [rbp-48h]
  const struct ID3_FRAME_DEF *v44; // [rsp+40h] [rbp-40h]
  unsigned __int64 v45; // [rsp+48h] [rbp-38h] BYREF
  _QWORD v46[4]; // [rsp+50h] [rbp-30h] BYREF
  WCHAR LCData[4]; // [rsp+70h] [rbp-10h] BYREF

  v44 = a3;
  v6 = a2;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v42,
    "CID3Writer::ConvertPropertyToGeneralTextID3Frame",
    554);
  v8 = *((_QWORD *)this + 9);
  Block = 0;
  v45 = 0;
  memset(&v46[1], 0, 24);
  v46[0] = v8 + 24 * v6;
  StringSize = CPropVariantID3ConversionHelper::GetStringSize((CPropVariantID3ConversionHelper *)v46, &v45);
  if ( StringSize < 0 )
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
        v11 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != StringSize )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CID3Writer::ConvertPropertyToGeneralTextID3Frame",
          569,
          StringSize);
    }
    if ( !g_wppLevels )
      goto LABEL_74;
    v14 = 45;
    goto LABEL_73;
  }
  v15 = v45 + 6;
  if ( v45 + 6 < v45 )
  {
    v16 = (wchar_t *)CallStackTracing::s_wpInstance;
    StringSize = -2147024362;
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
        v16 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v16 + 8) )
    {
      v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
      if ( *((_DWORD *)v18 + 499) != -2147024362 )
        CallStackContext::TraceFailure(v18, "CID3Writer::ConvertPropertyToGeneralTextID3Frame", 570, -2147024362);
    }
    if ( !g_wppLevels )
      goto LABEL_74;
    v19 = 46;
    goto LABEL_23;
  }
  v20 = v45 + 16;
  if ( v15 >= 0xFFFFFFFFFFFFFFF6uLL )
  {
    v21 = (wchar_t *)CallStackTracing::s_wpInstance;
    StringSize = -2147024362;
    if ( !CallStackTracing::s_wpInstance )
    {
      v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
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
        CallStackContext::TraceFailure(v23, "CID3Writer::ConvertPropertyToGeneralTextID3Frame", 571, -2147024362);
    }
    if ( !g_wppLevels )
      goto LABEL_74;
    v19 = 47;
LABEL_23:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v19,
      &WPP_02bf30fd61593fcad53f801c1bfe75a2_Traceguids,
      this,
      -2147024362);
    goto LABEL_74;
  }
  v24 = operator new[](v45 + 16);
  v26 = v24;
  if ( !v24 )
  {
    v27 = (wchar_t *)CallStackTracing::s_wpInstance;
    StringSize = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
      CallStackTracing::s_wpInstance = v28;
      if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
      {
        v27 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v27 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v27 + 8) )
    {
      v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
      if ( *((_DWORD *)v29 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v29, "CID3Writer::ConvertPropertyToGeneralTextID3Frame", 573, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_74;
    v14 = 48;
    goto LABEL_73;
  }
  Block = v24;
  *v24 = **((_DWORD **)v44 + 2);
  v24[1] = CID3Writer::AdjustSize(this, v15);
  *((_WORD *)v26 + 4) = 0;
  *((_BYTE *)v26 + 10) = 1;
  if ( !GetLocaleInfoEx((LPCWSTR)this + 48, 0x67u, LCData, 4) )
  {
    LastError = GetLastError();
    StringSize = LastError;
    if ( LastError > 0 )
      StringSize = (unsigned __int16)LastError | 0x80070000;
    if ( StringSize < 0 )
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
          v32 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v32 + 8) )
      {
        v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
        if ( *((_DWORD *)v34 + 499) != StringSize )
          CallStackContext::TraceFailure(v34, "CID3Writer::ConvertPropertyToGeneralTextID3Frame", 589, StringSize);
      }
      if ( !g_wppLevels )
        goto LABEL_74;
      v14 = 49;
      goto LABEL_73;
    }
  }
  for ( i = 0; i < 4; ++i )
  {
    v36 = (int)i;
    *((_BYTE *)&v46[-1] + v36) = LCData[v36];
  }
  *(_WORD *)((char *)v26 + 11) = v45;
  *((_BYTE *)v26 + 13) = BYTE2(v45);
  *((_BYTE *)v26 + 11) = 0;
  StringSize = CPropVariantID3ConversionHelper::CopyStringToBuffer(
                 (CPropVariantID3ConversionHelper *)v46,
                 (unsigned __int8 *)v26 + 12,
                 v15 - 5);
  if ( StringSize >= 0 )
  {
    *a4 = (unsigned __int8 *)v26;
    *a5 = v20;
    goto LABEL_76;
  }
  v38 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37);
    CallStackTracing::s_wpInstance = v39;
    if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
    {
      v38 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v38 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v38 + 8) )
  {
    v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
    if ( *((_DWORD *)v40 + 499) != StringSize )
      CallStackContext::TraceFailure(v40, "CID3Writer::ConvertPropertyToGeneralTextID3Frame", 606, StringSize);
  }
  if ( g_wppLevels )
  {
    v14 = 50;
LABEL_73:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v14,
      &WPP_02bf30fd61593fcad53f801c1bfe75a2_Traceguids,
      this,
      StringSize);
  }
LABEL_74:
  operator delete(Block);
LABEL_76:
  CPropVariantID3ConversionHelper::~CPropVariantID3ConversionHelper((CPropVariantID3ConversionHelper *)v46);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v42);
  return (unsigned int)StringSize;
}

```

## disassembly

```asm
0x1800a6af0  mov     [rsp-38h+arg_8], rbx
0x1800a6af5  push    rbp
0x1800a6af6  push    rsi
0x1800a6af7  push    rdi
0x1800a6af8  push    r12
0x1800a6afa  push    r13
0x1800a6afc  push    r14
0x1800a6afe  push    r15
0x1800a6b00  mov     rbp, rsp
0x1800a6b03  sub     rsp, 80h
0x1800a6b0a  mov     rax, cs:__security_cookie
0x1800a6b11  xor     rax, rsp
0x1800a6b14  mov     [rbp+var_8], rax
0x1800a6b18  mov     r13, [rbp+arg_20]
0x1800a6b1c  mov     r15, rcx
0x1800a6b1f  mov     [rbp+var_40], r8
0x1800a6b23  lea     rcx, [rbp+var_50]; this
0x1800a6b27  mov     ebx, edx
0x1800a6b29  mov     r8d, 22Ah; int
0x1800a6b2f  lea     rdx, aCid3writerConv_1; "CID3Writer::ConvertPropertyToGeneralTex"...
0x1800a6b36  mov     r12, r9
0x1800a6b39  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a6b3e  mov     rax, [r15+48h]
0x1800a6b42  lea     rcx, [rbx+rbx*2]
0x1800a6b46  xor     esi, esi
0x1800a6b48  lea     rdx, [rbp+var_38]; unsigned __int64 *
0x1800a6b4c  mov     [rbp+Block], rsi
0x1800a6b50  mov     [rbp+var_38], rsi
0x1800a6b54  lea     rcx, [rax+rcx*8]
0x1800a6b58  mov     [rbp+var_28], rsi
0x1800a6b5c  mov     [rbp+var_30], rcx
0x1800a6b60  lea     rcx, [rbp+var_30]; this
0x1800a6b64  mov     [rbp+var_20], rsi
0x1800a6b68  mov     [rbp+var_18], rsi
0x1800a6b6c  call    ?GetStringSize@CPropVariantID3ConversionHelper@@QEAAJPEA_K@Z; CPropVariantID3ConversionHelper::GetStringSize(unsigned __int64 *)
0x1800a6b71  mov     ebx, eax
0x1800a6b73  test    eax, eax
0x1800a6b75  jns     loc_1800A6C0A
0x1800a6b7b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6b82  test    rcx, rcx
0x1800a6b85  jnz     short loc_1800A6BC8
0x1800a6b87  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a6b8d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6b94  mov     rcx, rax
0x1800a6b97  test    rax, rax
0x1800a6b9a  jz      short loc_1800A6BBA
0x1800a6b9c  mov     rax, [rax]
0x1800a6b9f  mov     edx, 7F0h
0x1800a6ba4  mov     rax, [rax+8]
0x1800a6ba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6bad  test    eax, eax
0x1800a6baf  jz      short loc_1800A6BBA
0x1800a6bb1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6bb8  jmp     short loc_1800A6BC8
0x1800a6bba  lea     rcx, qword_1801B07E0; this
0x1800a6bc1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6bc8  cmp     [rcx+8], sil
0x1800a6bcc  jz      short loc_1800A6BF3
0x1800a6bce  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a6bd3  cmp     [rax+7CCh], ebx
0x1800a6bd9  jz      short loc_1800A6BF3
0x1800a6bdb  mov     r9d, ebx; int
0x1800a6bde  lea     rdx, aCid3writerConv_1; "CID3Writer::ConvertPropertyToGeneralTex"...
0x1800a6be5  mov     r8d, 239h; int
0x1800a6beb  mov     rcx, rax; this
0x1800a6bee  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a6bf3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a6bfa  jb      loc_1800A6FD7
0x1800a6c00  mov     edx, 2Dh ; '-'
0x1800a6c05  jmp     loc_1800A6FB9
0x1800a6c0a  mov     rax, [rbp+var_38]
0x1800a6c0e  lea     r14, [rax+6]
0x1800a6c12  cmp     r14, rax
0x1800a6c15  jnb     loc_1800A6CB5
0x1800a6c1b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6c22  mov     edi, 80070216h
0x1800a6c27  mov     ebx, edi
0x1800a6c29  test    rcx, rcx
0x1800a6c2c  jnz     short loc_1800A6C6F
0x1800a6c2e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a6c34  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6c3b  mov     rcx, rax
0x1800a6c3e  test    rax, rax
0x1800a6c41  jz      short loc_1800A6C61
0x1800a6c43  mov     rax, [rax]
0x1800a6c46  mov     edx, 7F0h
0x1800a6c4b  mov     rax, [rax+8]
0x1800a6c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6c54  test    eax, eax
0x1800a6c56  jz      short loc_1800A6C61
0x1800a6c58  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6c5f  jmp     short loc_1800A6C6F
0x1800a6c61  lea     rcx, qword_1801B07E0; this
0x1800a6c68  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6c6f  cmp     [rcx+8], sil
0x1800a6c73  jz      short loc_1800A6C9A
0x1800a6c75  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a6c7a  cmp     [rax+7CCh], edi
0x1800a6c80  jz      short loc_1800A6C9A
0x1800a6c82  mov     r9d, edi; int
0x1800a6c85  lea     rdx, aCid3writerConv_1; "CID3Writer::ConvertPropertyToGeneralTex"...
0x1800a6c8c  mov     r8d, 23Ah; int
0x1800a6c92  mov     rcx, rax; this
0x1800a6c95  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a6c9a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a6ca1  jb      loc_1800A6FD7
0x1800a6ca7  mov     edx, 2Eh ; '.'
0x1800a6cac  mov     [rsp+80h+var_60], edi
0x1800a6cb0  jmp     loc_1800A6FBD
0x1800a6cb5  lea     rsi, [r14+0Ah]
0x1800a6cb9  cmp     rsi, 0Ah
0x1800a6cbd  jnb     loc_1800A6D59
0x1800a6cc3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6cca  mov     edi, 80070216h
0x1800a6ccf  mov     ebx, edi
0x1800a6cd1  test    rcx, rcx
0x1800a6cd4  jnz     short loc_1800A6D17
0x1800a6cd6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a6cdc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6ce3  mov     rcx, rax
0x1800a6ce6  test    rax, rax
0x1800a6ce9  jz      short loc_1800A6D09
0x1800a6ceb  mov     rax, [rax]
0x1800a6cee  mov     edx, 7F0h
0x1800a6cf3  mov     rax, [rax+8]
0x1800a6cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6cfc  test    eax, eax
0x1800a6cfe  jz      short loc_1800A6D09
0x1800a6d00  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6d07  jmp     short loc_1800A6D17
0x1800a6d09  lea     rcx, qword_1801B07E0; this
0x1800a6d10  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6d17  cmp     byte ptr [rcx+8], 0
0x1800a6d1b  jz      short loc_1800A6D42
0x1800a6d1d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a6d22  cmp     [rax+7CCh], edi
0x1800a6d28  jz      short loc_1800A6D42
0x1800a6d2a  mov     r9d, edi; int
0x1800a6d2d  lea     rdx, aCid3writerConv_1; "CID3Writer::ConvertPropertyToGeneralTex"...
0x1800a6d34  mov     r8d, 23Bh; int
0x1800a6d3a  mov     rcx, rax; this
0x1800a6d3d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a6d42  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a6d49  jb      loc_1800A6FD7
0x1800a6d4f  mov     edx, 2Fh ; '/'
0x1800a6d54  jmp     loc_1800A6CAC
0x1800a6d59  mov     rcx, rsi; unsigned __int64
0x1800a6d5c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800a6d61  mov     rdi, rax
0x1800a6d64  test    rax, rax
0x1800a6d67  jnz     loc_1800A6E01
0x1800a6d6d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6d74  mov     ebx, 8007000Eh
0x1800a6d79  test    rcx, rcx
0x1800a6d7c  jnz     short loc_1800A6DBF
0x1800a6d7e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a6d84  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6d8b  mov     rcx, rax
0x1800a6d8e  test    rax, rax
0x1800a6d91  jz      short loc_1800A6DB1
0x1800a6d93  mov     rax, [rax]
0x1800a6d96  mov     edx, 7F0h
0x1800a6d9b  mov     rax, [rax+8]
0x1800a6d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6da4  test    eax, eax
0x1800a6da6  jz      short loc_1800A6DB1
0x1800a6da8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6daf  jmp     short loc_1800A6DBF
0x1800a6db1  lea     rcx, qword_1801B07E0; this
0x1800a6db8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6dbf  cmp     byte ptr [rcx+8], 0
0x1800a6dc3  jz      short loc_1800A6DEA
0x1800a6dc5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a6dca  cmp     [rax+7CCh], ebx
0x1800a6dd0  jz      short loc_1800A6DEA
0x1800a6dd2  mov     r9d, ebx; int
0x1800a6dd5  lea     rdx, aCid3writerConv_1; "CID3Writer::ConvertPropertyToGeneralTex"...
0x1800a6ddc  mov     r8d, 23Dh; int
0x1800a6de2  mov     rcx, rax; this
0x1800a6de5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a6dea  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a6df1  jb      loc_1800A6FD7
0x1800a6df7  mov     edx, 30h ; '0'
0x1800a6dfc  jmp     loc_1800A6FB9
0x1800a6e01  mov     rax, [rbp+var_40]
0x1800a6e05  mov     edx, r14d; unsigned int
0x1800a6e08  mov     [rbp+Block], rdi
0x1800a6e0c  mov     rax, [rax+10h]
0x1800a6e10  mov     ecx, [rax]
0x1800a6e12  mov     [rdi], ecx
0x1800a6e14  mov     rcx, r15; this
0x1800a6e17  call    ?AdjustSize@CID3Writer@@IEAAII@Z; CID3Writer::AdjustSize(uint)
0x1800a6e1c  mov     [rdi+4], eax
0x1800a6e1f  lea     rcx, [r15+60h]; lpLocaleName
0x1800a6e23  xor     eax, eax
0x1800a6e25  lea     r8, [rbp+LCData]; lpLCData
0x1800a6e29  mov     [rdi+8], ax
0x1800a6e2d  mov     byte ptr [rdi+0Ah], 1
0x1800a6e31  lea     r9d, [rax+4]; cchData
0x1800a6e35  lea     edx, [rax+67h]; LCType
0x1800a6e38  call    cs:__imp_GetLocaleInfoEx
0x1800a6e3e  test    eax, eax
0x1800a6e40  jnz     loc_1800A6EF2
0x1800a6e46  call    cs:__imp_GetLastError
0x1800a6e4c  mov     ebx, eax
0x1800a6e4e  test    eax, eax
0x1800a6e50  jle     short loc_1800A6E5B
0x1800a6e52  movzx   ebx, ax
0x1800a6e55  or      ebx, 80070000h
0x1800a6e5b  test    ebx, ebx
0x1800a6e5d  jns     loc_1800A6EF2
0x1800a6e63  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6e6a  test    rcx, rcx
0x1800a6e6d  jnz     short loc_1800A6EB0
0x1800a6e6f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a6e75  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6e7c  mov     rcx, rax
0x1800a6e7f  test    rax, rax
0x1800a6e82  jz      short loc_1800A6EA2
0x1800a6e84  mov     rax, [rax]
0x1800a6e87  mov     edx, 7F0h
0x1800a6e8c  mov     rax, [rax+8]
0x1800a6e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6e95  test    eax, eax
0x1800a6e97  jz      short loc_1800A6EA2
0x1800a6e99  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6ea0  jmp     short loc_1800A6EB0
0x1800a6ea2  lea     rcx, qword_1801B07E0; this
0x1800a6ea9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6eb0  cmp     byte ptr [rcx+8], 0
0x1800a6eb4  jz      short loc_1800A6EDB
0x1800a6eb6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a6ebb  cmp     [rax+7CCh], ebx
0x1800a6ec1  jz      short loc_1800A6EDB
0x1800a6ec3  mov     r9d, ebx; int
0x1800a6ec6  lea     rdx, aCid3writerConv_1; "CID3Writer::ConvertPropertyToGeneralTex"...
0x1800a6ecd  mov     r8d, 24Dh; int
0x1800a6ed3  mov     rcx, rax; this
0x1800a6ed6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a6edb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a6ee2  jb      loc_1800A6FD7
0x1800a6ee8  mov     edx, 31h ; '1'
0x1800a6eed  jmp     loc_1800A6FB9
0x1800a6ef2  xor     edx, edx
0x1800a6ef4  movsxd  rcx, edx
0x1800a6ef7  inc     edx
0x1800a6ef9  mov     al, byte ptr [rbp+rcx*2+LCData]
0x1800a6efd  mov     byte ptr [rbp+rcx+var_38], al
0x1800a6f01  cmp     edx, 4
0x1800a6f04  jb      short loc_1800A6EF4
0x1800a6f06  movzx   eax, word ptr [rbp+var_38]
0x1800a6f0a  lea     r8, [r14-5]; unsigned __int64
0x1800a6f0e  mov     [rdi+0Bh], ax
0x1800a6f12  lea     rdx, [rdi+0Ch]; unsigned __int8 *
0x1800a6f16  mov     al, byte ptr [rbp+var_38+2]
0x1800a6f19  lea     rcx, [rbp+var_30]; this
0x1800a6f1d  mov     [rdi+0Dh], al
0x1800a6f20  mov     byte ptr [rdi+0Bh], 0
0x1800a6f24  call    ?CopyStringToBuffer@CPropVariantID3ConversionHelper@@QEAAJPEAE_K@Z; CPropVariantID3ConversionHelper::CopyStringToBuffer(uchar *,unsigned __int64)
0x1800a6f29  mov     ebx, eax
0x1800a6f2b  test    eax, eax
0x1800a6f2d  jns     loc_1800A6FE2
0x1800a6f33  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6f3a  test    rcx, rcx
0x1800a6f3d  jnz     short loc_1800A6F80
0x1800a6f3f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a6f45  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6f4c  mov     rcx, rax
0x1800a6f4f  test    rax, rax
0x1800a6f52  jz      short loc_1800A6F72
0x1800a6f54  mov     rax, [rax]
0x1800a6f57  mov     edx, 7F0h
0x1800a6f5c  mov     rax, [rax+8]
0x1800a6f60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6f65  test    eax, eax
0x1800a6f67  jz      short loc_1800A6F72
0x1800a6f69  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6f70  jmp     short loc_1800A6F80
0x1800a6f72  lea     rcx, qword_1801B07E0; this
0x1800a6f79  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a6f80  cmp     byte ptr [rcx+8], 0
0x1800a6f84  jz      short loc_1800A6FAB
0x1800a6f86  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a6f8b  cmp     [rax+7CCh], ebx
0x1800a6f91  jz      short loc_1800A6FAB
0x1800a6f93  mov     r9d, ebx; int
0x1800a6f96  lea     rdx, aCid3writerConv_1; "CID3Writer::ConvertPropertyToGeneralTex"...
0x1800a6f9d  mov     r8d, 25Eh; int
0x1800a6fa3  mov     rcx, rax; this
0x1800a6fa6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a6fab  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a6fb2  jb      short loc_1800A6FD7
0x1800a6fb4  mov     edx, 32h ; '2'
0x1800a6fb9  mov     [rsp+80h+var_60], ebx
0x1800a6fbd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a6fc4  lea     r8, WPP_02bf30fd61593fcad53f801c1bfe75a2_Traceguids
0x1800a6fcb  mov     r9, r15
0x1800a6fce  mov     rcx, [rcx+10h]
0x1800a6fd2  call    WPP_SF_qD
0x1800a6fd7  mov     rcx, [rbp+Block]; Block
  ... truncated ...
```
