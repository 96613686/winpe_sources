# CID3Writer::FinalizeGaplessMetadata(IMFByteStream *,MFEncodedStreamInfo *)

- ea: `0x1800a54e0`
- end: `0x1800a5b90`
- name: `?FinalizeGaplessMetadata@CID3Writer@@QEAAXPEAUIMFByteStream@@PEAUMFEncodedStreamInfo@@@Z`
- size: `1712`
- prototype: `void __fastcall(CID3Writer *__hidden this, struct IMFByteStream *, struct MFEncodedStreamInfo *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800c6ad0`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180079680`
- `0x1800a54e0`
- `0x180110ed0`
- `0x180111960`
- `0x180128fa4`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a556c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a5624`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a56e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a57a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a5848`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a5918`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a59da`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a5a7b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a556c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a5624`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a56e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a57a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a5848`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a5918`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a59da`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a5a7b`

## string_xrefs

- `0x1800a5509`: `CID3Writer::FinalizeGaplessMetadata`
- `0x1800a58aa`: `CID3Writer::FinalizeGaplessMetadata`
- `0x1800a597a`: `CID3Writer::FinalizeGaplessMetadata`
- `0x1800a5a37`: `CID3Writer::FinalizeGaplessMetadata`
- `0x1800a5add`: `CID3Writer::FinalizeGaplessMetadata`

## pseudocode

```c
void __fastcall CID3Writer::FinalizeGaplessMetadata(
        CID3Writer *this,
        struct IMFByteStream *a2,
        struct MFEncodedStreamInfo *a3)
{
  char v6; // r13
  __int64 v7; // rdx
  wchar_t *v8; // rcx
  CallStackTracing *v9; // rax
  int v10; // ebx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  wchar_t *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  struct IMFByteStreamVtbl *lpVtbl; // rax
  __int64 v19; // rdx
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  struct IMFByteStreamVtbl *v23; // rax
  __int64 v24; // rdx
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  wchar_t *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  wchar_t *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rdx
  wchar_t *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  wchar_t *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  _BYTE v43[8]; // [rsp+30h] [rbp-89h] BYREF
  __int64 v44; // [rsp+38h] [rbp-81h]
  unsigned int v45; // [rsp+40h] [rbp-79h] BYREF
  __int64 v46; // [rsp+48h] [rbp-71h] BYREF
  _BYTE v47[128]; // [rsp+50h] [rbp-69h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v43, "CID3Writer::FinalizeGaplessMetadata", 948);
  v46 = 0;
  v44 = 0;
  v45 = 0;
  v6 = 0;
  memset_0(v47, 0, 0x75u);
  if ( !*((_BYTE *)this + 288) )
  {
    v8 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v8 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    v10 = -1072875854;
    if ( *((_BYTE *)v8 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875854 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CID3Writer::FinalizeGaplessMetadata", 967, -1072875854);
    }
    if ( !g_wppLevels )
      goto LABEL_95;
    v12 = 74;
    goto LABEL_12;
  }
  v10 = ((__int64 (__fastcall *)(struct IMFByteStream *, __int64 *))a2->lpVtbl->GetCurrentPosition)(a2, &v46);
  if ( v10 >= 0 )
  {
    v17 = *((_QWORD *)this + 34);
    v44 = v46;
    lpVtbl = a2->lpVtbl;
    v46 = v17;
    v10 = ((__int64 (__fastcall *)(struct IMFByteStream *))lpVtbl->SetCurrentPosition)(a2);
    if ( v10 >= 0 )
    {
      v23 = a2->lpVtbl;
      v6 = 1;
      v45 = 23;
      v10 = ((__int64 (__fastcall *)(struct IMFByteStream *, __int64))v23->SetCurrentPosition)(a2, v46 + 23);
      if ( v10 < 0 )
      {
        v25 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
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
          if ( *((_DWORD *)v27 + 499) != v10 )
            CallStackContext::TraceFailure(v27, "CID3Writer::FinalizeGaplessMetadata", 989, v10);
        }
        if ( !g_wppLevels )
          goto LABEL_91;
        v12 = 77;
        goto LABEL_12;
      }
      if ( *((_QWORD *)this + 35) - v45 == 117 )
      {
        if ( (unsigned int)sprintf_s<117>(
                             v47,
                             " 00000000 %08x %08x %016I64x 00000000 %08I64x 00000000 00000000 00000000 00000000 00000000 00000000",
                             *((_DWORD *)a3 + 9),
                             *((_DWORD *)a3 + 9) + *((_DWORD *)a3 + 8),
                             *((_QWORD *)a3 + 1),
                             *((_QWORD *)a3 + 2)) == 116 )
        {
          v10 = ((__int64 (__fastcall *)(struct IMFByteStream *, _BYTE *, __int64, unsigned int *))a2->lpVtbl->Write)(
                  a2,
                  v47,
                  117,
                  &v45);
          if ( v10 < 0 )
          {
            v37 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36);
              CallStackTracing::s_wpInstance = v38;
              if ( v38
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
              {
                v37 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v37 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)v37 + 8) )
            {
              v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
              if ( *((_DWORD *)v39 + 499) != v10 )
                CallStackContext::TraceFailure(v39, "CID3Writer::FinalizeGaplessMetadata", 1011, v10);
            }
            if ( !g_wppLevels )
              goto LABEL_91;
            v12 = 80;
            goto LABEL_12;
          }
          if ( v45 == 117 )
            goto LABEL_94;
          v40 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36);
            CallStackTracing::s_wpInstance = v41;
            if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
            {
              v40 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v40 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v40 + 8) )
          {
            v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
            if ( *((_DWORD *)v42 + 499) != -2147467259 )
              CallStackContext::TraceFailure(v42, "CID3Writer::FinalizeGaplessMetadata", 1014, -2147467259);
          }
          if ( !g_wppLevels )
            goto LABEL_94;
          v35 = 81;
        }
        else
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
            if ( *((_DWORD *)v34 + 499) != -2147467259 )
              CallStackContext::TraceFailure(v34, "CID3Writer::FinalizeGaplessMetadata", 1008, -2147467259);
          }
          if ( !g_wppLevels )
            goto LABEL_94;
          v35 = 79;
        }
        v10 = -2147467259;
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v35,
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
            v10);
        goto LABEL_93;
      }
      v28 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
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
      v10 = -1072875841;
      if ( *((_BYTE *)v28 + 8) )
      {
        v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
        if ( *((_DWORD *)v30 + 499) != -1072875841 )
          CallStackContext::TraceFailure(v30, "CID3Writer::FinalizeGaplessMetadata", 996, -1072875841);
      }
      if ( !g_wppLevels )
        goto LABEL_94;
      v12 = 78;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_02bf30fd61593fcad53f801c1bfe75a2_Traceguids, this, v10);
      goto LABEL_91;
    }
    v20 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
      CallStackTracing::s_wpInstance = v21;
      if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
      {
        v20 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v20 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v20 + 8) )
    {
      v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
      if ( *((_DWORD *)v22 + 499) != v10 )
        CallStackContext::TraceFailure(v22, "CID3Writer::FinalizeGaplessMetadata", 976, v10);
    }
    if ( g_wppLevels )
    {
      v12 = 76;
      goto LABEL_12;
    }
  }
  else
  {
    v14 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
      CallStackTracing::s_wpInstance = v15;
      if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
      {
        v14 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v14 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v14 + 8) )
    {
      v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
      if ( *((_DWORD *)v16 + 499) != v10 )
        CallStackContext::TraceFailure(v16, "CID3Writer::FinalizeGaplessMetadata", 971, v10);
    }
    if ( g_wppLevels )
    {
      v12 = 75;
      goto LABEL_12;
    }
  }
LABEL_93:
  if ( v6 )
LABEL_94:
    ((void (__fastcall *)(struct IMFByteStream *, __int64))a2->lpVtbl->SetCurrentPosition)(a2, v44);
LABEL_95:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v43);
}

```

## disassembly

```asm
0x1800a54e0  push    rbp
0x1800a54e2  push    rbx
0x1800a54e3  push    rsi
0x1800a54e4  push    r12
0x1800a54e6  push    r13
0x1800a54e8  push    r14
0x1800a54ea  push    r15
0x1800a54ec  lea     rbp, [rsp-27h]
0x1800a54f1  sub     rsp, 0E0h
0x1800a54f8  mov     rax, cs:__security_cookie
0x1800a54ff  xor     rax, rsp
0x1800a5502  mov     [rbp+57h+var_40], rax
0x1800a5506  mov     r15, r8
0x1800a5509  lea     rsi, aCid3writerFina; "CID3Writer::FinalizeGaplessMetadata"
0x1800a5510  mov     r12, rdx
0x1800a5513  mov     r14, rcx
0x1800a5516  mov     rdx, rsi; char *
0x1800a5519  lea     rcx, [rsp+110h+var_E0]; this
0x1800a551e  mov     r8d, 3B4h; int
0x1800a5524  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a5529  xor     edx, edx; Val
0x1800a552b  mov     [rbp+57h+var_C8], 0
0x1800a5533  lea     rcx, [rbp+57h+var_C0]; void *
0x1800a5537  mov     [rsp+110h+var_D8], 0
0x1800a5540  mov     [rbp+57h+var_D0], 0
0x1800a5547  xor     r13b, r13b
0x1800a554a  lea     r8d, [rdx+75h]; Size
0x1800a554e  call    memset_0
0x1800a5553  cmp     [r14+120h], r13b
0x1800a555a  jnz     loc_1800A55FA
0x1800a5560  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5567  test    rcx, rcx
0x1800a556a  jnz     short loc_1800A55B3
0x1800a556c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a5573  nop     dword ptr [rax+rax+00h]
0x1800a5578  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a557f  mov     rcx, rax
0x1800a5582  test    rax, rax
0x1800a5585  jz      short loc_1800A55A5
0x1800a5587  mov     rax, [rax]
0x1800a558a  mov     edx, 7F0h
0x1800a558f  mov     rax, [rax+8]
0x1800a5593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5598  test    eax, eax
0x1800a559a  jz      short loc_1800A55A5
0x1800a559c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a55a3  jmp     short loc_1800A55B3
0x1800a55a5  lea     rcx, qword_1801B97E0; this
0x1800a55ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a55b3  mov     ebx, 0C00D36B2h
0x1800a55b8  cmp     [rcx+8], r13b
0x1800a55bc  jz      short loc_1800A55DF
0x1800a55be  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a55c3  cmp     [rax+7CCh], ebx
0x1800a55c9  jz      short loc_1800A55DF
0x1800a55cb  mov     r9d, ebx; int
0x1800a55ce  mov     r8d, 3C7h; int
0x1800a55d4  mov     rdx, rsi; char *
0x1800a55d7  mov     rcx, rax; this
0x1800a55da  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a55df  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a55e6  jb      loc_1800A5B66
0x1800a55ec  mov     edx, 4Ah ; 'J'
0x1800a55f1  mov     dword ptr [rsp+110h+var_F0], ebx
0x1800a55f5  jmp     loc_1800A5B06
0x1800a55fa  mov     rax, [r12]
0x1800a55fe  lea     rdx, [rbp+57h+var_C8]
0x1800a5602  mov     rcx, r12
0x1800a5605  mov     rax, [rax+30h]
0x1800a5609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a560e  mov     ebx, eax
0x1800a5610  test    eax, eax
0x1800a5612  jns     loc_1800A56A9
0x1800a5618  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a561f  test    rcx, rcx
0x1800a5622  jnz     short loc_1800A566B
0x1800a5624  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a562b  nop     dword ptr [rax+rax+00h]
0x1800a5630  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5637  mov     rcx, rax
0x1800a563a  test    rax, rax
0x1800a563d  jz      short loc_1800A565D
0x1800a563f  mov     rax, [rax]
0x1800a5642  mov     edx, 7F0h
0x1800a5647  mov     rax, [rax+8]
0x1800a564b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5650  test    eax, eax
0x1800a5652  jz      short loc_1800A565D
0x1800a5654  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a565b  jmp     short loc_1800A566B
0x1800a565d  lea     rcx, qword_1801B97E0; this
0x1800a5664  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a566b  cmp     [rcx+8], r13b
0x1800a566f  jz      short loc_1800A5692
0x1800a5671  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a5676  cmp     [rax+7CCh], ebx
0x1800a567c  jz      short loc_1800A5692
0x1800a567e  mov     r9d, ebx; int
0x1800a5681  mov     r8d, 3CBh; int
0x1800a5687  mov     rdx, rsi; char *
0x1800a568a  mov     rcx, rax; this
0x1800a568d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a5692  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a5699  jb      loc_1800A5B4C
0x1800a569f  mov     edx, 4Bh ; 'K'
0x1800a56a4  jmp     loc_1800A55F1
0x1800a56a9  mov     rax, [rbp+57h+var_C8]
0x1800a56ad  mov     rcx, r12
0x1800a56b0  mov     rdx, [r14+110h]
0x1800a56b7  mov     [rsp+110h+var_D8], rax
0x1800a56bc  mov     rax, [r12]
0x1800a56c0  mov     [rbp+57h+var_C8], rdx
0x1800a56c4  mov     rax, [rax+38h]
0x1800a56c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a56cd  mov     ebx, eax
0x1800a56cf  test    eax, eax
0x1800a56d1  jns     loc_1800A5768
0x1800a56d7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a56de  test    rcx, rcx
0x1800a56e1  jnz     short loc_1800A572A
0x1800a56e3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a56ea  nop     dword ptr [rax+rax+00h]
0x1800a56ef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a56f6  mov     rcx, rax
0x1800a56f9  test    rax, rax
0x1800a56fc  jz      short loc_1800A571C
0x1800a56fe  mov     rax, [rax]
0x1800a5701  mov     edx, 7F0h
0x1800a5706  mov     rax, [rax+8]
0x1800a570a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a570f  test    eax, eax
0x1800a5711  jz      short loc_1800A571C
0x1800a5713  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a571a  jmp     short loc_1800A572A
0x1800a571c  lea     rcx, qword_1801B97E0; this
0x1800a5723  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a572a  cmp     [rcx+8], r13b
0x1800a572e  jz      short loc_1800A5751
0x1800a5730  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a5735  cmp     [rax+7CCh], ebx
0x1800a573b  jz      short loc_1800A5751
0x1800a573d  mov     r9d, ebx; int
0x1800a5740  mov     r8d, 3D0h; int
0x1800a5746  mov     rdx, rsi; char *
0x1800a5749  mov     rcx, rax; this
0x1800a574c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a5751  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a5758  jb      loc_1800A5B4C
0x1800a575e  mov     edx, 4Ch ; 'L'
0x1800a5763  jmp     loc_1800A55F1
0x1800a5768  mov     rax, [r12]
0x1800a576c  mov     rcx, r12
0x1800a576f  mov     rdx, [rbp+57h+var_C8]
0x1800a5773  mov     r13b, 1
0x1800a5776  add     rdx, 17h
0x1800a577a  mov     [rbp+57h+var_D0], 17h
0x1800a5781  mov     rax, [rax+38h]
0x1800a5785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a578a  mov     ebx, eax
0x1800a578c  test    eax, eax
0x1800a578e  jns     loc_1800A5825
0x1800a5794  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a579b  test    rcx, rcx
0x1800a579e  jnz     short loc_1800A57E7
0x1800a57a0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a57a7  nop     dword ptr [rax+rax+00h]
0x1800a57ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a57b3  mov     rcx, rax
0x1800a57b6  test    rax, rax
0x1800a57b9  jz      short loc_1800A57D9
0x1800a57bb  mov     rax, [rax]
0x1800a57be  mov     edx, 7F0h
0x1800a57c3  mov     rax, [rax+8]
0x1800a57c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a57cc  test    eax, eax
0x1800a57ce  jz      short loc_1800A57D9
0x1800a57d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a57d7  jmp     short loc_1800A57E7
0x1800a57d9  lea     rcx, qword_1801B97E0; this
0x1800a57e0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a57e7  cmp     byte ptr [rcx+8], 0
0x1800a57eb  jz      short loc_1800A580E
0x1800a57ed  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a57f2  cmp     [rax+7CCh], ebx
0x1800a57f8  jz      short loc_1800A580E
0x1800a57fa  mov     r9d, ebx; int
0x1800a57fd  mov     r8d, 3DDh; int
0x1800a5803  mov     rdx, rsi; char *
0x1800a5806  mov     rcx, rax; this
0x1800a5809  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a580e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800a5815  jb      loc_1800A5B20
0x1800a581b  mov     edx, 4Dh ; 'M'
0x1800a5820  jmp     loc_1800A55F1
0x1800a5825  mov     eax, [rbp+57h+var_D0]
0x1800a5828  mov     rsi, [r14+118h]
0x1800a582f  sub     rsi, rax
0x1800a5832  cmp     rsi, 75h ; 'u'
0x1800a5836  jz      loc_1800A58D6
0x1800a583c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5843  test    rcx, rcx
0x1800a5846  jnz     short loc_1800A588F
0x1800a5848  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a584f  nop     dword ptr [rax+rax+00h]
0x1800a5854  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a585b  mov     rcx, rax
0x1800a585e  test    rax, rax
0x1800a5861  jz      short loc_1800A5881
0x1800a5863  mov     rax, [rax]
0x1800a5866  mov     edx, 7F0h
0x1800a586b  mov     rax, [rax+8]
0x1800a586f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5874  test    eax, eax
0x1800a5876  jz      short loc_1800A5881
0x1800a5878  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a587f  jmp     short loc_1800A588F
0x1800a5881  lea     rcx, qword_1801B97E0; this
0x1800a5888  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a588f  cmp     byte ptr [rcx+8], 0
0x1800a5893  mov     ebx, 0C00D36BFh
0x1800a5898  jz      short loc_1800A58BF
0x1800a589a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a589f  cmp     [rax+7CCh], ebx
0x1800a58a5  jz      short loc_1800A58BF
0x1800a58a7  mov     r9d, ebx; int
0x1800a58aa  lea     rdx, aCid3writerFina; "CID3Writer::FinalizeGaplessMetadata"
0x1800a58b1  mov     r8d, 3E4h; int
0x1800a58b7  mov     rcx, rax; this
0x1800a58ba  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a58bf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800a58c6  jb      loc_1800A5B51
0x1800a58cc  mov     edx, 4Eh ; 'N'
0x1800a58d1  jmp     loc_1800A55F1
0x1800a58d6  mov     rax, [r15+10h]
0x1800a58da  lea     rdx, a0000000008x08x; " 00000000 %08x %08x %016I64x 00000000 %"...
0x1800a58e1  mov     r9d, [r15+20h]
0x1800a58e5  lea     rcx, [rbp+57h+var_C0]
0x1800a58e9  mov     r8d, [r15+24h]
0x1800a58ed  add     r9d, r8d
0x1800a58f0  mov     [rsp+110h+var_E8], rax
0x1800a58f5  mov     rax, [r15+8]
0x1800a58f9  mov     [rsp+110h+var_F0], rax
0x1800a58fe  call    ??$sprintf_s@$0HF@@@YAHAEAY0HF@DPEBDZZ; sprintf_s<117>(char (&)[117],char const *,...)
0x1800a5903  cmp     eax, 74h ; 't'
0x1800a5906  jz      loc_1800A59A6
0x1800a590c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5913  test    rcx, rcx
0x1800a5916  jnz     short loc_1800A595F
0x1800a5918  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a591f  nop     dword ptr [rax+rax+00h]
0x1800a5924  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a592b  mov     rcx, rax
0x1800a592e  test    rax, rax
0x1800a5931  jz      short loc_1800A5951
0x1800a5933  mov     rax, [rax]
0x1800a5936  mov     edx, 7F0h
0x1800a593b  mov     rax, [rax+8]
0x1800a593f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5944  test    eax, eax
0x1800a5946  jz      short loc_1800A5951
0x1800a5948  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a594f  jmp     short loc_1800A595F
0x1800a5951  lea     rcx, qword_1801B97E0; this
0x1800a5958  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a595f  cmp     byte ptr [rcx+8], 0
0x1800a5963  mov     esi, 80004005h
0x1800a5968  jz      short loc_1800A598F
0x1800a596a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a596f  cmp     [rax+7CCh], esi
0x1800a5975  jz      short loc_1800A598F
0x1800a5977  mov     r9d, esi; int
0x1800a597a  lea     rdx, aCid3writerFina; "CID3Writer::FinalizeGaplessMetadata"
0x1800a5981  mov     r8d, 3F0h; int
0x1800a5987  mov     rcx, rax; this
0x1800a598a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a598f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800a5996  jb      loc_1800A5B51
0x1800a599c  mov     edx, 4Fh ; 'O'
0x1800a59a1  jmp     loc_1800A5B00
0x1800a59a6  mov     rax, [r12]
0x1800a59aa  lea     r9, [rbp+57h+var_D0]
0x1800a59ae  mov     r8d, 75h ; 'u'
0x1800a59b4  lea     rdx, [rbp+57h+var_C0]
0x1800a59b8  mov     rcx, r12
0x1800a59bb  mov     rax, [rax+60h]
0x1800a59bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a59c4  mov     ebx, eax
0x1800a59c6  test    eax, eax
0x1800a59c8  jns     loc_1800A5A63
0x1800a59ce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a59d5  test    rcx, rcx
0x1800a59d8  jnz     short loc_1800A5A21
0x1800a59da  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a59e1  nop     dword ptr [rax+rax+00h]
0x1800a59e6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a59ed  mov     rcx, rax
0x1800a59f0  test    rax, rax
0x1800a59f3  jz      short loc_1800A5A13
0x1800a59f5  mov     rax, [rax]
0x1800a59f8  mov     edx, 7F0h
  ... truncated ...
```
