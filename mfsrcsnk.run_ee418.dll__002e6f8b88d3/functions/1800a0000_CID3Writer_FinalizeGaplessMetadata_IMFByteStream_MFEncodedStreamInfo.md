# CID3Writer::FinalizeGaplessMetadata(IMFByteStream *,MFEncodedStreamInfo *)

- ea: `0x1800a0000`
- end: `0x1800a067f`
- name: `?FinalizeGaplessMetadata@CID3Writer@@QEAAXPEAUIMFByteStream@@PEAUMFEncodedStreamInfo@@@Z`
- size: `1663`
- prototype: `void __fastcall(CID3Writer *__hidden this, struct IMFByteStream *, struct MFEncodedStreamInfo *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800c0d10`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180073b14`
- `0x1800a0000`
- `0x1801099f0`
- `0x18010a450`
- `0x180122228`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a008c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a013e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a01f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a02ae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a0350`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a041a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a04d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a0571`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a008c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a013e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a01f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a02ae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a0350`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a041a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a04d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a0571`

## string_xrefs

- `0x1800a0029`: `CID3Writer::FinalizeGaplessMetadata`
- `0x1800a03ac`: `CID3Writer::FinalizeGaplessMetadata`
- `0x1800a0476`: `CID3Writer::FinalizeGaplessMetadata`
- `0x1800a052d`: `CID3Writer::FinalizeGaplessMetadata`
- `0x1800a05cd`: `CID3Writer::FinalizeGaplessMetadata`

## pseudocode

```c
void __fastcall CID3Writer::FinalizeGaplessMetadata(
        CID3Writer *this,
        struct IMFByteStream *a2,
        struct MFEncodedStreamInfo *a3)
{
  char v6; // r13
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  wchar_t *v10; // rcx
  CallStackTracing *v11; // rax
  int v12; // ebx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  wchar_t *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  struct IMFByteStreamVtbl *lpVtbl; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  struct IMFByteStreamVtbl *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  wchar_t *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  wchar_t *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  __int64 v45; // rdx
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // r9
  wchar_t *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  wchar_t *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  _BYTE v55[8]; // [rsp+30h] [rbp-89h] BYREF
  __int64 v56; // [rsp+38h] [rbp-81h]
  unsigned int v57; // [rsp+40h] [rbp-79h] BYREF
  __int64 v58; // [rsp+48h] [rbp-71h] BYREF
  _BYTE v59[128]; // [rsp+50h] [rbp-69h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v55, "CID3Writer::FinalizeGaplessMetadata", 948);
  v58 = 0;
  v56 = 0;
  v57 = 0;
  v6 = 0;
  memset_0(v59, 0, 0x75u);
  if ( !*((_BYTE *)this + 288) )
  {
    v10 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7, v8, v9);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    v12 = -1072875854;
    if ( *((_BYTE *)v10 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875854 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CID3Writer::FinalizeGaplessMetadata", 967, -1072875854);
    }
    if ( !g_wppLevels )
      goto LABEL_95;
    v14 = 74;
    goto LABEL_12;
  }
  v12 = ((__int64 (__fastcall *)(struct IMFByteStream *, __int64 *))a2->lpVtbl->GetCurrentPosition)(a2, &v58);
  if ( v12 >= 0 )
  {
    v21 = *((_QWORD *)this + 34);
    v56 = v58;
    lpVtbl = a2->lpVtbl;
    v58 = v21;
    v12 = ((__int64 (__fastcall *)(struct IMFByteStream *))lpVtbl->SetCurrentPosition)(a2);
    if ( v12 >= 0 )
    {
      v29 = a2->lpVtbl;
      v6 = 1;
      v57 = 23;
      v12 = ((__int64 (__fastcall *)(struct IMFByteStream *, __int64))v29->SetCurrentPosition)(a2, v58 + 23);
      if ( v12 < 0 )
      {
        v33 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30, v31, v32);
          CallStackTracing::s_wpInstance = v34;
          if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
          {
            v33 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v33 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v33 + 8) )
        {
          v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
          if ( *((_DWORD *)v35 + 499) != v12 )
            CallStackContext::TraceFailure(v35, "CID3Writer::FinalizeGaplessMetadata", 989, v12);
        }
        if ( !g_wppLevels )
          goto LABEL_91;
        v14 = 77;
        goto LABEL_12;
      }
      if ( *((_QWORD *)this + 35) - v57 == 117 )
      {
        if ( (unsigned int)sprintf_s<117>(
                             v59,
                             " 00000000 %08x %08x %016I64x 00000000 %08I64x 00000000 00000000 00000000 00000000 00000000 00000000",
                             *((_DWORD *)a3 + 9),
                             *((_DWORD *)a3 + 9) + *((_DWORD *)a3 + 8),
                             *((_QWORD *)a3 + 1),
                             *((_QWORD *)a3 + 2)) == 116 )
        {
          v12 = ((__int64 (__fastcall *)(struct IMFByteStream *, _BYTE *, __int64, unsigned int *))a2->lpVtbl->Write)(
                  a2,
                  v59,
                  117,
                  &v57);
          if ( v12 < 0 )
          {
            v49 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46, v47, v48);
              CallStackTracing::s_wpInstance = v50;
              if ( v50
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
              {
                v49 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v49 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v49 + 8) )
            {
              v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
              if ( *((_DWORD *)v51 + 499) != v12 )
                CallStackContext::TraceFailure(v51, "CID3Writer::FinalizeGaplessMetadata", 1011, v12);
            }
            if ( !g_wppLevels )
              goto LABEL_91;
            v14 = 80;
            goto LABEL_12;
          }
          if ( v57 == 117 )
            goto LABEL_94;
          v52 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46, v47, v48);
            CallStackTracing::s_wpInstance = v53;
            if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
            {
              v52 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v52 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v52 + 8) )
          {
            v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
            if ( *((_DWORD *)v54 + 499) != -2147467259 )
              CallStackContext::TraceFailure(v54, "CID3Writer::FinalizeGaplessMetadata", 1014, -2147467259);
          }
          if ( !g_wppLevels )
            goto LABEL_94;
          v45 = 81;
        }
        else
        {
          v42 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39, v40, v41);
            CallStackTracing::s_wpInstance = v43;
            if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
            {
              v42 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v42 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v42 + 8) )
          {
            v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
            if ( *((_DWORD *)v44 + 499) != -2147467259 )
              CallStackContext::TraceFailure(v44, "CID3Writer::FinalizeGaplessMetadata", 1008, -2147467259);
          }
          if ( !g_wppLevels )
            goto LABEL_94;
          v45 = 79;
        }
        v12 = -2147467259;
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v45,
          &WPP_02bf30fd61593fcad53f801c1bfe75a2_Traceguids,
          this,
          -2147467259);
LABEL_91:
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            82,
            &WPP_02bf30fd61593fcad53f801c1bfe75a2_Traceguids,
            this,
            v12);
        goto LABEL_93;
      }
      v36 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30, v31, v32);
        CallStackTracing::s_wpInstance = v37;
        if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
        {
          v36 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v36 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      v12 = -1072875841;
      if ( *((_BYTE *)v36 + 8) )
      {
        v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
        if ( *((_DWORD *)v38 + 499) != -1072875841 )
          CallStackContext::TraceFailure(v38, "CID3Writer::FinalizeGaplessMetadata", 996, -1072875841);
      }
      if ( !g_wppLevels )
        goto LABEL_94;
      v14 = 78;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_02bf30fd61593fcad53f801c1bfe75a2_Traceguids, this, v12);
      goto LABEL_91;
    }
    v26 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24, v25);
      CallStackTracing::s_wpInstance = v27;
      if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
      {
        v26 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v26 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v26 + 8) )
    {
      v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
      if ( *((_DWORD *)v28 + 499) != v12 )
        CallStackContext::TraceFailure(v28, "CID3Writer::FinalizeGaplessMetadata", 976, v12);
    }
    if ( g_wppLevels )
    {
      v14 = 76;
      goto LABEL_12;
    }
  }
  else
  {
    v18 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15, v16, v17);
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
      if ( *((_DWORD *)v20 + 499) != v12 )
        CallStackContext::TraceFailure(v20, "CID3Writer::FinalizeGaplessMetadata", 971, v12);
    }
    if ( g_wppLevels )
    {
      v14 = 75;
      goto LABEL_12;
    }
  }
LABEL_93:
  if ( v6 )
LABEL_94:
    ((void (__fastcall *)(struct IMFByteStream *, __int64))a2->lpVtbl->SetCurrentPosition)(a2, v56);
LABEL_95:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v55);
}

```

## disassembly

```asm
0x1800a0000  push    rbp
0x1800a0002  push    rbx
0x1800a0003  push    rsi
0x1800a0004  push    r12
0x1800a0006  push    r13
0x1800a0008  push    r14
0x1800a000a  push    r15
0x1800a000c  lea     rbp, [rsp-27h]
0x1800a0011  sub     rsp, 0E0h
0x1800a0018  mov     rax, cs:__security_cookie
0x1800a001f  xor     rax, rsp
0x1800a0022  mov     [rbp+57h+var_40], rax
0x1800a0026  mov     r15, r8
0x1800a0029  lea     rsi, aCid3writerFina; "CID3Writer::FinalizeGaplessMetadata"
0x1800a0030  mov     r12, rdx
0x1800a0033  mov     r14, rcx
0x1800a0036  mov     rdx, rsi; char *
0x1800a0039  lea     rcx, [rsp+110h+var_E0]; this
0x1800a003e  mov     r8d, 3B4h; int
0x1800a0044  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a0049  xor     edx, edx; Val
0x1800a004b  mov     [rbp+57h+var_C8], 0
0x1800a0053  lea     rcx, [rbp+57h+var_C0]; void *
0x1800a0057  mov     [rsp+110h+var_D8], 0
0x1800a0060  mov     [rbp+57h+var_D0], 0
0x1800a0067  xor     r13b, r13b
0x1800a006a  lea     r8d, [rdx+75h]; Size
0x1800a006e  call    memset_0
0x1800a0073  cmp     [r14+120h], r13b
0x1800a007a  jnz     loc_1800A0114
0x1800a0080  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a0087  test    rcx, rcx
0x1800a008a  jnz     short loc_1800A00CD
0x1800a008c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a0092  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a0099  mov     rcx, rax
0x1800a009c  test    rax, rax
0x1800a009f  jz      short loc_1800A00BF
0x1800a00a1  mov     rax, [rax]
0x1800a00a4  mov     edx, 7F0h
0x1800a00a9  mov     rax, [rax+8]
0x1800a00ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a00b2  test    eax, eax
0x1800a00b4  jz      short loc_1800A00BF
0x1800a00b6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a00bd  jmp     short loc_1800A00CD
0x1800a00bf  lea     rcx, qword_1801B07E0; this
0x1800a00c6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a00cd  mov     ebx, 0C00D36B2h
0x1800a00d2  cmp     [rcx+8], r13b
0x1800a00d6  jz      short loc_1800A00F9
0x1800a00d8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a00dd  cmp     [rax+7CCh], ebx
0x1800a00e3  jz      short loc_1800A00F9
0x1800a00e5  mov     r9d, ebx; int
0x1800a00e8  mov     r8d, 3C7h; int
0x1800a00ee  mov     rdx, rsi; char *
0x1800a00f1  mov     rcx, rax; this
0x1800a00f4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a00f9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a0100  jb      loc_1800A0656
0x1800a0106  mov     edx, 4Ah ; 'J'
0x1800a010b  mov     dword ptr [rsp+110h+var_F0], ebx
0x1800a010f  jmp     loc_1800A05F6
0x1800a0114  mov     rax, [r12]
0x1800a0118  lea     rdx, [rbp+57h+var_C8]
0x1800a011c  mov     rcx, r12
0x1800a011f  mov     rax, [rax+30h]
0x1800a0123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0128  mov     ebx, eax
0x1800a012a  test    eax, eax
0x1800a012c  jns     loc_1800A01BD
0x1800a0132  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a0139  test    rcx, rcx
0x1800a013c  jnz     short loc_1800A017F
0x1800a013e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a0144  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a014b  mov     rcx, rax
0x1800a014e  test    rax, rax
0x1800a0151  jz      short loc_1800A0171
0x1800a0153  mov     rax, [rax]
0x1800a0156  mov     edx, 7F0h
0x1800a015b  mov     rax, [rax+8]
0x1800a015f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0164  test    eax, eax
0x1800a0166  jz      short loc_1800A0171
0x1800a0168  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a016f  jmp     short loc_1800A017F
0x1800a0171  lea     rcx, qword_1801B07E0; this
0x1800a0178  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a017f  cmp     [rcx+8], r13b
0x1800a0183  jz      short loc_1800A01A6
0x1800a0185  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a018a  cmp     [rax+7CCh], ebx
0x1800a0190  jz      short loc_1800A01A6
0x1800a0192  mov     r9d, ebx; int
0x1800a0195  mov     r8d, 3CBh; int
0x1800a019b  mov     rdx, rsi; char *
0x1800a019e  mov     rcx, rax; this
0x1800a01a1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a01a6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a01ad  jb      loc_1800A063C
0x1800a01b3  mov     edx, 4Bh ; 'K'
0x1800a01b8  jmp     loc_1800A010B
0x1800a01bd  mov     rax, [rbp+57h+var_C8]
0x1800a01c1  mov     rcx, r12
0x1800a01c4  mov     rdx, [r14+110h]
0x1800a01cb  mov     [rsp+110h+var_D8], rax
0x1800a01d0  mov     rax, [r12]
0x1800a01d4  mov     [rbp+57h+var_C8], rdx
0x1800a01d8  mov     rax, [rax+38h]
0x1800a01dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a01e1  mov     ebx, eax
0x1800a01e3  test    eax, eax
0x1800a01e5  jns     loc_1800A0276
0x1800a01eb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a01f2  test    rcx, rcx
0x1800a01f5  jnz     short loc_1800A0238
0x1800a01f7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a01fd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a0204  mov     rcx, rax
0x1800a0207  test    rax, rax
0x1800a020a  jz      short loc_1800A022A
0x1800a020c  mov     rax, [rax]
0x1800a020f  mov     edx, 7F0h
0x1800a0214  mov     rax, [rax+8]
0x1800a0218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a021d  test    eax, eax
0x1800a021f  jz      short loc_1800A022A
0x1800a0221  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a0228  jmp     short loc_1800A0238
0x1800a022a  lea     rcx, qword_1801B07E0; this
0x1800a0231  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a0238  cmp     [rcx+8], r13b
0x1800a023c  jz      short loc_1800A025F
0x1800a023e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a0243  cmp     [rax+7CCh], ebx
0x1800a0249  jz      short loc_1800A025F
0x1800a024b  mov     r9d, ebx; int
0x1800a024e  mov     r8d, 3D0h; int
0x1800a0254  mov     rdx, rsi; char *
0x1800a0257  mov     rcx, rax; this
0x1800a025a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a025f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a0266  jb      loc_1800A063C
0x1800a026c  mov     edx, 4Ch ; 'L'
0x1800a0271  jmp     loc_1800A010B
0x1800a0276  mov     rax, [r12]
0x1800a027a  mov     rcx, r12
0x1800a027d  mov     rdx, [rbp+57h+var_C8]
0x1800a0281  mov     r13b, 1
0x1800a0284  add     rdx, 17h
0x1800a0288  mov     [rbp+57h+var_D0], 17h
0x1800a028f  mov     rax, [rax+38h]
0x1800a0293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0298  mov     ebx, eax
0x1800a029a  test    eax, eax
0x1800a029c  jns     loc_1800A032D
0x1800a02a2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a02a9  test    rcx, rcx
0x1800a02ac  jnz     short loc_1800A02EF
0x1800a02ae  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a02b4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a02bb  mov     rcx, rax
0x1800a02be  test    rax, rax
0x1800a02c1  jz      short loc_1800A02E1
0x1800a02c3  mov     rax, [rax]
0x1800a02c6  mov     edx, 7F0h
0x1800a02cb  mov     rax, [rax+8]
0x1800a02cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a02d4  test    eax, eax
0x1800a02d6  jz      short loc_1800A02E1
0x1800a02d8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a02df  jmp     short loc_1800A02EF
0x1800a02e1  lea     rcx, qword_1801B07E0; this
0x1800a02e8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a02ef  cmp     byte ptr [rcx+8], 0
0x1800a02f3  jz      short loc_1800A0316
0x1800a02f5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a02fa  cmp     [rax+7CCh], ebx
0x1800a0300  jz      short loc_1800A0316
0x1800a0302  mov     r9d, ebx; int
0x1800a0305  mov     r8d, 3DDh; int
0x1800a030b  mov     rdx, rsi; char *
0x1800a030e  mov     rcx, rax; this
0x1800a0311  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a0316  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800a031d  jb      loc_1800A0610
0x1800a0323  mov     edx, 4Dh ; 'M'
0x1800a0328  jmp     loc_1800A010B
0x1800a032d  mov     eax, [rbp+57h+var_D0]
0x1800a0330  mov     rsi, [r14+118h]
0x1800a0337  sub     rsi, rax
0x1800a033a  cmp     rsi, 75h ; 'u'
0x1800a033e  jz      loc_1800A03D8
0x1800a0344  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a034b  test    rcx, rcx
0x1800a034e  jnz     short loc_1800A0391
0x1800a0350  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a0356  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a035d  mov     rcx, rax
0x1800a0360  test    rax, rax
0x1800a0363  jz      short loc_1800A0383
0x1800a0365  mov     rax, [rax]
0x1800a0368  mov     edx, 7F0h
0x1800a036d  mov     rax, [rax+8]
0x1800a0371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0376  test    eax, eax
0x1800a0378  jz      short loc_1800A0383
0x1800a037a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a0381  jmp     short loc_1800A0391
0x1800a0383  lea     rcx, qword_1801B07E0; this
0x1800a038a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a0391  cmp     byte ptr [rcx+8], 0
0x1800a0395  mov     ebx, 0C00D36BFh
0x1800a039a  jz      short loc_1800A03C1
0x1800a039c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a03a1  cmp     [rax+7CCh], ebx
0x1800a03a7  jz      short loc_1800A03C1
0x1800a03a9  mov     r9d, ebx; int
0x1800a03ac  lea     rdx, aCid3writerFina; "CID3Writer::FinalizeGaplessMetadata"
0x1800a03b3  mov     r8d, 3E4h; int
0x1800a03b9  mov     rcx, rax; this
0x1800a03bc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a03c1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800a03c8  jb      loc_1800A0641
0x1800a03ce  mov     edx, 4Eh ; 'N'
0x1800a03d3  jmp     loc_1800A010B
0x1800a03d8  mov     rax, [r15+10h]
0x1800a03dc  lea     rdx, a0000000008x08x; " 00000000 %08x %08x %016I64x 00000000 %"...
0x1800a03e3  mov     r9d, [r15+20h]
0x1800a03e7  lea     rcx, [rbp+57h+var_C0]
0x1800a03eb  mov     r8d, [r15+24h]
0x1800a03ef  add     r9d, r8d
0x1800a03f2  mov     [rsp+110h+var_E8], rax
0x1800a03f7  mov     rax, [r15+8]
0x1800a03fb  mov     [rsp+110h+var_F0], rax
0x1800a0400  call    ??$sprintf_s@$0HF@@@YAHAEAY0HF@DPEBDZZ; sprintf_s<117>(char (&)[117],char const *,...)
0x1800a0405  cmp     eax, 74h ; 't'
0x1800a0408  jz      loc_1800A04A2
0x1800a040e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a0415  test    rcx, rcx
0x1800a0418  jnz     short loc_1800A045B
0x1800a041a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a0420  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a0427  mov     rcx, rax
0x1800a042a  test    rax, rax
0x1800a042d  jz      short loc_1800A044D
0x1800a042f  mov     rax, [rax]
0x1800a0432  mov     edx, 7F0h
0x1800a0437  mov     rax, [rax+8]
0x1800a043b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0440  test    eax, eax
0x1800a0442  jz      short loc_1800A044D
0x1800a0444  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a044b  jmp     short loc_1800A045B
0x1800a044d  lea     rcx, qword_1801B07E0; this
0x1800a0454  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a045b  cmp     byte ptr [rcx+8], 0
0x1800a045f  mov     esi, 80004005h
0x1800a0464  jz      short loc_1800A048B
0x1800a0466  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a046b  cmp     [rax+7CCh], esi
0x1800a0471  jz      short loc_1800A048B
0x1800a0473  mov     r9d, esi; int
0x1800a0476  lea     rdx, aCid3writerFina; "CID3Writer::FinalizeGaplessMetadata"
0x1800a047d  mov     r8d, 3F0h; int
0x1800a0483  mov     rcx, rax; this
0x1800a0486  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a048b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800a0492  jb      loc_1800A0641
0x1800a0498  mov     edx, 4Fh ; 'O'
0x1800a049d  jmp     loc_1800A05F0
0x1800a04a2  mov     rax, [r12]
0x1800a04a6  lea     r9, [rbp+57h+var_D0]
0x1800a04aa  mov     r8d, 75h ; 'u'
0x1800a04b0  lea     rdx, [rbp+57h+var_C0]
0x1800a04b4  mov     rcx, r12
0x1800a04b7  mov     rax, [rax+60h]
0x1800a04bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a04c0  mov     ebx, eax
0x1800a04c2  test    eax, eax
0x1800a04c4  jns     loc_1800A0559
0x1800a04ca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a04d1  test    rcx, rcx
0x1800a04d4  jnz     short loc_1800A0517
0x1800a04d6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a04dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a04e3  mov     rcx, rax
0x1800a04e6  test    rax, rax
0x1800a04e9  jz      short loc_1800A0509
0x1800a04eb  mov     rax, [rax]
0x1800a04ee  mov     edx, 7F0h
0x1800a04f3  mov     rax, [rax+8]
0x1800a04f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a04fc  test    eax, eax
0x1800a04fe  jz      short loc_1800A0509
0x1800a0500  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a0507  jmp     short loc_1800A0517
0x1800a0509  lea     rcx, qword_1801B07E0; this
  ... truncated ...
```
