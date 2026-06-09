# CID3Writer::ConvertPropertyToGeneralTextID3Frame(ulong,ID3_FRAME_DEF const *,uchar * *,unsigned __int64 *)

- ea: `0x1800abbb8`
- end: `0x1800ac121`
- name: `?ConvertPropertyToGeneralTextID3Frame@CID3Writer@@IEAAJKPEBUID3_FRAME_DEF@@PEAPEAEPEA_K@Z`
- size: `1385`
- prototype: `__int64 __usercall@<rax>(CID3Writer *__hidden this@<rcx>, unsigned int@<edx>, const struct ID3_FRAME_DEF *@<r8>, unsigned __int8 **@<r9>, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x1801297b8`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180079680`
- `0x1800abbb8`
- `0x180110a88`
- `0x180110ad4`
- `0x180110ed0`
- `0x18012910c`
- `0x1801291f0`
- `0x180129b30`
- `0x18012a094`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abf2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abf2c`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x1800abf18`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x1800abf18`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800abc4f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800abcfc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800abdaa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800abe58`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800abf5b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ac031`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800abc4f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800abcfc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800abdaa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800abe58`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800abf5b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ac031`

## string_xrefs

- `0x1800abbf7`: `CID3Writer::ConvertPropertyToGeneralTextID3Frame`
- `0x1800abcac`: `CID3Writer::ConvertPropertyToGeneralTextID3Frame`
- `0x1800abd59`: `CID3Writer::ConvertPropertyToGeneralTextID3Frame`
- `0x1800abe07`: `CID3Writer::ConvertPropertyToGeneralTextID3Frame`
- `0x1800abeb5`: `CID3Writer::ConvertPropertyToGeneralTextID3Frame`
- `0x1800abfb8`: `CID3Writer::ConvertPropertyToGeneralTextID3Frame`
- `0x1800ac08e`: `CID3Writer::ConvertPropertyToGeneralTextID3Frame`

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
        v11 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v16 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v21 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v27 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v32 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
      v38 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x1800abbb8  mov     [rsp-38h+arg_8], rbx
0x1800abbbd  push    rbp
0x1800abbbe  push    rsi
0x1800abbbf  push    rdi
0x1800abbc0  push    r12
0x1800abbc2  push    r13
0x1800abbc4  push    r14
0x1800abbc6  push    r15
0x1800abbc8  mov     rbp, rsp
0x1800abbcb  sub     rsp, 80h
0x1800abbd2  mov     rax, cs:__security_cookie
0x1800abbd9  xor     rax, rsp
0x1800abbdc  mov     [rbp+var_8], rax
0x1800abbe0  mov     r13, [rbp+arg_20]
0x1800abbe4  mov     r15, rcx
0x1800abbe7  mov     [rbp+var_40], r8
0x1800abbeb  lea     rcx, [rbp+var_50]; this
0x1800abbef  mov     ebx, edx
0x1800abbf1  mov     r8d, 22Ah; int
0x1800abbf7  lea     rdx, aCid3writerConv_1; "CID3Writer::ConvertPropertyToGeneralTex"...
0x1800abbfe  mov     r12, r9
0x1800abc01  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800abc06  mov     rax, [r15+48h]
0x1800abc0a  lea     rcx, [rbx+rbx*2]
0x1800abc0e  xor     esi, esi
0x1800abc10  lea     rdx, [rbp+var_38]; unsigned __int64 *
0x1800abc14  mov     [rbp+Block], rsi
0x1800abc18  mov     [rbp+var_38], rsi
0x1800abc1c  lea     rcx, [rax+rcx*8]
0x1800abc20  mov     [rbp+var_28], rsi
0x1800abc24  mov     [rbp+var_30], rcx
0x1800abc28  lea     rcx, [rbp+var_30]; this
0x1800abc2c  mov     [rbp+var_20], rsi
0x1800abc30  mov     [rbp+var_18], rsi
0x1800abc34  call    ?GetStringSize@CPropVariantID3ConversionHelper@@QEAAJPEA_K@Z; CPropVariantID3ConversionHelper::GetStringSize(unsigned __int64 *)
0x1800abc39  mov     ebx, eax
0x1800abc3b  test    eax, eax
0x1800abc3d  jns     loc_1800ABCD8
0x1800abc43  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800abc4a  test    rcx, rcx
0x1800abc4d  jnz     short loc_1800ABC96
0x1800abc4f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800abc56  nop     dword ptr [rax+rax+00h]
0x1800abc5b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800abc62  mov     rcx, rax
0x1800abc65  test    rax, rax
0x1800abc68  jz      short loc_1800ABC88
0x1800abc6a  mov     rax, [rax]
0x1800abc6d  mov     edx, 7F0h
0x1800abc72  mov     rax, [rax+8]
0x1800abc76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abc7b  test    eax, eax
0x1800abc7d  jz      short loc_1800ABC88
0x1800abc7f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800abc86  jmp     short loc_1800ABC96
0x1800abc88  lea     rcx, qword_1801B97E0; this
0x1800abc8f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800abc96  cmp     [rcx+8], sil
0x1800abc9a  jz      short loc_1800ABCC1
0x1800abc9c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800abca1  cmp     [rax+7CCh], ebx
0x1800abca7  jz      short loc_1800ABCC1
0x1800abca9  mov     r9d, ebx; int
0x1800abcac  lea     rdx, aCid3writerConv_1; "CID3Writer::ConvertPropertyToGeneralTex"...
0x1800abcb3  mov     r8d, 239h; int
0x1800abcb9  mov     rcx, rax; this
0x1800abcbc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800abcc1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800abcc8  jb      loc_1800AC0CF
0x1800abcce  mov     edx, 2Dh ; '-'
0x1800abcd3  jmp     loc_1800AC0B1
0x1800abcd8  mov     rax, [rbp+var_38]
0x1800abcdc  lea     r14, [rax+6]
0x1800abce0  cmp     r14, rax
0x1800abce3  jnb     loc_1800ABD89
0x1800abce9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800abcf0  mov     edi, 80070216h
0x1800abcf5  mov     ebx, edi
0x1800abcf7  test    rcx, rcx
0x1800abcfa  jnz     short loc_1800ABD43
0x1800abcfc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800abd03  nop     dword ptr [rax+rax+00h]
0x1800abd08  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800abd0f  mov     rcx, rax
0x1800abd12  test    rax, rax
0x1800abd15  jz      short loc_1800ABD35
0x1800abd17  mov     rax, [rax]
0x1800abd1a  mov     edx, 7F0h
0x1800abd1f  mov     rax, [rax+8]
0x1800abd23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abd28  test    eax, eax
0x1800abd2a  jz      short loc_1800ABD35
0x1800abd2c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800abd33  jmp     short loc_1800ABD43
0x1800abd35  lea     rcx, qword_1801B97E0; this
0x1800abd3c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800abd43  cmp     [rcx+8], sil
0x1800abd47  jz      short loc_1800ABD6E
0x1800abd49  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800abd4e  cmp     [rax+7CCh], edi
0x1800abd54  jz      short loc_1800ABD6E
0x1800abd56  mov     r9d, edi; int
0x1800abd59  lea     rdx, aCid3writerConv_1; "CID3Writer::ConvertPropertyToGeneralTex"...
0x1800abd60  mov     r8d, 23Ah; int
0x1800abd66  mov     rcx, rax; this
0x1800abd69  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800abd6e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800abd75  jb      loc_1800AC0CF
0x1800abd7b  mov     edx, 2Eh ; '.'
0x1800abd80  mov     [rsp+80h+var_60], edi
0x1800abd84  jmp     loc_1800AC0B5
0x1800abd89  lea     rsi, [r14+0Ah]
0x1800abd8d  cmp     rsi, 0Ah
0x1800abd91  jnb     loc_1800ABE33
0x1800abd97  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800abd9e  mov     edi, 80070216h
0x1800abda3  mov     ebx, edi
0x1800abda5  test    rcx, rcx
0x1800abda8  jnz     short loc_1800ABDF1
0x1800abdaa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800abdb1  nop     dword ptr [rax+rax+00h]
0x1800abdb6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800abdbd  mov     rcx, rax
0x1800abdc0  test    rax, rax
0x1800abdc3  jz      short loc_1800ABDE3
0x1800abdc5  mov     rax, [rax]
0x1800abdc8  mov     edx, 7F0h
0x1800abdcd  mov     rax, [rax+8]
0x1800abdd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abdd6  test    eax, eax
0x1800abdd8  jz      short loc_1800ABDE3
0x1800abdda  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800abde1  jmp     short loc_1800ABDF1
0x1800abde3  lea     rcx, qword_1801B97E0; this
0x1800abdea  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800abdf1  cmp     byte ptr [rcx+8], 0
0x1800abdf5  jz      short loc_1800ABE1C
0x1800abdf7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800abdfc  cmp     [rax+7CCh], edi
0x1800abe02  jz      short loc_1800ABE1C
0x1800abe04  mov     r9d, edi; int
0x1800abe07  lea     rdx, aCid3writerConv_1; "CID3Writer::ConvertPropertyToGeneralTex"...
0x1800abe0e  mov     r8d, 23Bh; int
0x1800abe14  mov     rcx, rax; this
0x1800abe17  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800abe1c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800abe23  jb      loc_1800AC0CF
0x1800abe29  mov     edx, 2Fh ; '/'
0x1800abe2e  jmp     loc_1800ABD80
0x1800abe33  mov     rcx, rsi; unsigned __int64
0x1800abe36  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800abe3b  mov     rdi, rax
0x1800abe3e  test    rax, rax
0x1800abe41  jnz     loc_1800ABEE1
0x1800abe47  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800abe4e  mov     ebx, 8007000Eh
0x1800abe53  test    rcx, rcx
0x1800abe56  jnz     short loc_1800ABE9F
0x1800abe58  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800abe5f  nop     dword ptr [rax+rax+00h]
0x1800abe64  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800abe6b  mov     rcx, rax
0x1800abe6e  test    rax, rax
0x1800abe71  jz      short loc_1800ABE91
0x1800abe73  mov     rax, [rax]
0x1800abe76  mov     edx, 7F0h
0x1800abe7b  mov     rax, [rax+8]
0x1800abe7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abe84  test    eax, eax
0x1800abe86  jz      short loc_1800ABE91
0x1800abe88  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800abe8f  jmp     short loc_1800ABE9F
0x1800abe91  lea     rcx, qword_1801B97E0; this
0x1800abe98  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800abe9f  cmp     byte ptr [rcx+8], 0
0x1800abea3  jz      short loc_1800ABECA
0x1800abea5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800abeaa  cmp     [rax+7CCh], ebx
0x1800abeb0  jz      short loc_1800ABECA
0x1800abeb2  mov     r9d, ebx; int
0x1800abeb5  lea     rdx, aCid3writerConv_1; "CID3Writer::ConvertPropertyToGeneralTex"...
0x1800abebc  mov     r8d, 23Dh; int
0x1800abec2  mov     rcx, rax; this
0x1800abec5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800abeca  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800abed1  jb      loc_1800AC0CF
0x1800abed7  mov     edx, 30h ; '0'
0x1800abedc  jmp     loc_1800AC0B1
0x1800abee1  mov     rax, [rbp+var_40]
0x1800abee5  mov     edx, r14d; unsigned int
0x1800abee8  mov     [rbp+Block], rdi
0x1800abeec  mov     rax, [rax+10h]
0x1800abef0  mov     ecx, [rax]
0x1800abef2  mov     [rdi], ecx
0x1800abef4  mov     rcx, r15; this
0x1800abef7  call    ?AdjustSize@CID3Writer@@IEAAII@Z; CID3Writer::AdjustSize(uint)
0x1800abefc  mov     [rdi+4], eax
0x1800abeff  lea     rcx, [r15+60h]; lpLocaleName
0x1800abf03  xor     eax, eax
0x1800abf05  lea     r8, [rbp+LCData]; lpLCData
0x1800abf09  mov     [rdi+8], ax
0x1800abf0d  mov     byte ptr [rdi+0Ah], 1
0x1800abf11  lea     r9d, [rax+4]; cchData
0x1800abf15  lea     edx, [rax+67h]; LCType
0x1800abf18  call    cs:__imp_GetLocaleInfoEx
0x1800abf1f  nop     dword ptr [rax+rax+00h]
0x1800abf24  test    eax, eax
0x1800abf26  jnz     loc_1800ABFE4
0x1800abf2c  call    cs:__imp_GetLastError
0x1800abf33  nop     dword ptr [rax+rax+00h]
0x1800abf38  mov     ebx, eax
0x1800abf3a  test    eax, eax
0x1800abf3c  jle     short loc_1800ABF47
0x1800abf3e  movzx   ebx, ax
0x1800abf41  or      ebx, 80070000h
0x1800abf47  test    ebx, ebx
0x1800abf49  jns     loc_1800ABFE4
0x1800abf4f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800abf56  test    rcx, rcx
0x1800abf59  jnz     short loc_1800ABFA2
0x1800abf5b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800abf62  nop     dword ptr [rax+rax+00h]
0x1800abf67  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800abf6e  mov     rcx, rax
0x1800abf71  test    rax, rax
0x1800abf74  jz      short loc_1800ABF94
0x1800abf76  mov     rax, [rax]
0x1800abf79  mov     edx, 7F0h
0x1800abf7e  mov     rax, [rax+8]
0x1800abf82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abf87  test    eax, eax
0x1800abf89  jz      short loc_1800ABF94
0x1800abf8b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800abf92  jmp     short loc_1800ABFA2
0x1800abf94  lea     rcx, qword_1801B97E0; this
0x1800abf9b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800abfa2  cmp     byte ptr [rcx+8], 0
0x1800abfa6  jz      short loc_1800ABFCD
0x1800abfa8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800abfad  cmp     [rax+7CCh], ebx
0x1800abfb3  jz      short loc_1800ABFCD
0x1800abfb5  mov     r9d, ebx; int
0x1800abfb8  lea     rdx, aCid3writerConv_1; "CID3Writer::ConvertPropertyToGeneralTex"...
0x1800abfbf  mov     r8d, 24Dh; int
0x1800abfc5  mov     rcx, rax; this
0x1800abfc8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800abfcd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800abfd4  jb      loc_1800AC0CF
0x1800abfda  mov     edx, 31h ; '1'
0x1800abfdf  jmp     loc_1800AC0B1
0x1800abfe4  xor     edx, edx
0x1800abfe6  movsxd  rcx, edx
0x1800abfe9  inc     edx
0x1800abfeb  mov     al, byte ptr [rbp+rcx*2+LCData]
0x1800abfef  mov     byte ptr [rbp+rcx+var_38], al
0x1800abff3  cmp     edx, 4
0x1800abff6  jb      short loc_1800ABFE6
0x1800abff8  movzx   eax, word ptr [rbp+var_38]
0x1800abffc  lea     r8, [r14-5]; unsigned __int64
0x1800ac000  mov     [rdi+0Bh], ax
0x1800ac004  lea     rdx, [rdi+0Ch]; unsigned __int8 *
0x1800ac008  mov     al, byte ptr [rbp+var_38+2]
0x1800ac00b  lea     rcx, [rbp+var_30]; this
0x1800ac00f  mov     [rdi+0Dh], al
0x1800ac012  mov     byte ptr [rdi+0Bh], 0
0x1800ac016  call    ?CopyStringToBuffer@CPropVariantID3ConversionHelper@@QEAAJPEAE_K@Z; CPropVariantID3ConversionHelper::CopyStringToBuffer(uchar *,unsigned __int64)
0x1800ac01b  mov     ebx, eax
0x1800ac01d  test    eax, eax
0x1800ac01f  jns     loc_1800AC0DA
0x1800ac025  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ac02c  test    rcx, rcx
0x1800ac02f  jnz     short loc_1800AC078
0x1800ac031  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ac038  nop     dword ptr [rax+rax+00h]
0x1800ac03d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ac044  mov     rcx, rax
0x1800ac047  test    rax, rax
0x1800ac04a  jz      short loc_1800AC06A
0x1800ac04c  mov     rax, [rax]
0x1800ac04f  mov     edx, 7F0h
0x1800ac054  mov     rax, [rax+8]
0x1800ac058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac05d  test    eax, eax
0x1800ac05f  jz      short loc_1800AC06A
0x1800ac061  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ac068  jmp     short loc_1800AC078
0x1800ac06a  lea     rcx, qword_1801B97E0; this
0x1800ac071  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ac078  cmp     byte ptr [rcx+8], 0
0x1800ac07c  jz      short loc_1800AC0A3
0x1800ac07e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ac083  cmp     [rax+7CCh], ebx
0x1800ac089  jz      short loc_1800AC0A3
0x1800ac08b  mov     r9d, ebx; int
0x1800ac08e  lea     rdx, aCid3writerConv_1; "CID3Writer::ConvertPropertyToGeneralTex"...
0x1800ac095  mov     r8d, 25Eh; int
0x1800ac09b  mov     rcx, rax; this
0x1800ac09e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ac0a3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ac0aa  jb      short loc_1800AC0CF
  ... truncated ...
```
