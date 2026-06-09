# CMFByteStreamSourceReader::EndReadData(IMFAsyncResult *,IMFMediaBuffer * *,ulong *)

- ea: `0x180037dec`
- end: `0x1800382ba`
- name: `?EndReadData@CMFByteStreamSourceReader@@QEAAJPEAUIMFAsyncResult@@PEAPEAUIMFMediaBuffer@@PEAK@Z`
- size: `1230`
- prototype: `int(CMFByteStreamSourceReader *__hidden this, struct IMFAsyncResult *, struct IMFMediaBuffer **, unsigned int *)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x180037280`
- `0x1800892a0`
- `0x1800db2f8`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180037dec`
- `0x180039ca8`
- `0x180077708`
- `0x180079680`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037ef5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037fa3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003805c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003812d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800381e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037ef5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037fa3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003805c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003812d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800381e1`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x1800381bf`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x1800381bf`

## string_xrefs

- `0x180037e03`: `CMFByteStreamSourceReader::EndReadData`
- `0x1800380b9`: `CMFByteStreamSourceReader::EndReadData`
- `0x18003818a`: `CMFByteStreamSourceReader::EndReadData`
- `0x18003823e`: `CMFByteStreamSourceReader::EndReadData`

## pseudocode

```c
__int64 __fastcall CMFByteStreamSourceReader::EndReadData(
        CMFByteStreamSourceReader *this,
        struct IMFAsyncResult *a2,
        struct IMFMediaBuffer **a3,
        unsigned int *a4)
{
  CByteStreamCacheReader2 *v8; // rcx
  HRESULT v9; // edi
  CallStackTracing *v10; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
  IMFMediaBuffer *v13; // rbx
  __int64 v14; // rdx
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  wchar_t *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // r15
  struct IMFMediaBuffer *v23; // r14
  __int64 v24; // rdx
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rdx
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  unsigned int v38; // [rsp+30h] [rbp-18h] BYREF
  __int64 v39; // [rsp+38h] [rbp-10h] BYREF
  IMFMediaBuffer *pBuffer; // [rsp+90h] [rbp+48h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&pBuffer,
    "CMFByteStreamSourceReader::EndReadData",
    456);
  v8 = (CByteStreamCacheReader2 *)*((_QWORD *)this + 2);
  v39 = 0;
  pBuffer = 0;
  v38 = 0;
  v9 = CByteStreamCacheReader2::EndCacheRead(v8, a2, &pBuffer, 0);
  if ( v9 < 0 )
  {
    v10 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v10 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v10);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFByteStreamSourceReader::EndReadData", 468, v9);
    }
    if ( !g_wppLevels )
      goto LABEL_10;
    v12 = 39;
LABEL_9:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_f019a0467ccf3e64ef7099288b24b930_Traceguids, this, v9);
LABEL_10:
    v13 = pBuffer;
    goto LABEL_70;
  }
  *((_DWORD *)this + 6) = 0;
  v9 = ((__int64 (__fastcall *)(struct IMFAsyncResult *))a2->lpVtbl->GetStatus)(a2);
  if ( v9 < 0 )
  {
    v15 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
      CallStackTracing::s_wpInstance = v16;
      if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
      {
        v15 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v15 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v15 + 8) )
    {
      v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
      if ( *((_DWORD *)v17 + 499) != v9 )
        CallStackContext::TraceFailure(v17, "CMFByteStreamSourceReader::EndReadData", 475, v9);
    }
    if ( !g_wppLevels )
      goto LABEL_10;
    v12 = 40;
    goto LABEL_9;
  }
  v9 = ((__int64 (__fastcall *)(struct IMFAsyncResult *, __int64 *))a2->lpVtbl->GetState)(a2, &v39);
  if ( v9 < 0 )
  {
    v19 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
      CallStackTracing::s_wpInstance = v20;
      if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
      {
        v19 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v19 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v19 + 8) )
    {
      v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
      if ( *((_DWORD *)v21 + 499) != v9 )
        CallStackContext::TraceFailure(v21, "CMFByteStreamSourceReader::EndReadData", 480, v9);
    }
    if ( !g_wppLevels )
      goto LABEL_10;
    v12 = 41;
    goto LABEL_9;
  }
  v13 = pBuffer;
  v22 = v39;
  v23 = pBuffer;
  v9 = ((__int64 (__fastcall *)(IMFMediaBuffer *, unsigned int *))pBuffer->lpVtbl->GetCurrentLength)(pBuffer, &v38);
  if ( v9 < 0 )
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
      if ( *((_DWORD *)v27 + 499) != v9 )
        CallStackContext::TraceFailure(v27, "CMFByteStreamSourceReader::EndReadData", 485, v9);
    }
    if ( g_wppLevels )
    {
      v28 = 42;
LABEL_44:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v28, &WPP_f019a0467ccf3e64ef7099288b24b930_Traceguids, this, v9);
      goto LABEL_70;
    }
    goto LABEL_70;
  }
  v29 = *(unsigned int *)(v22 + 16);
  if ( !(_DWORD)v29 )
  {
    v13 = 0;
    *a3 = v23;
    goto LABEL_69;
  }
  if ( (unsigned int)v29 < v38 )
  {
    v9 = MFCreateMediaBufferWrapper(v13, v29, v38 - v29, a3);
    if ( v9 < 0 )
    {
      v34 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
        CallStackTracing::s_wpInstance = v35;
        if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
        {
          v34 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v34 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v34 + 8) )
      {
        v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
        if ( *((_DWORD *)v36 + 499) != v9 )
          CallStackContext::TraceFailure(v36, "CMFByteStreamSourceReader::EndReadData", 504, v9);
      }
      if ( g_wppLevels )
      {
        v28 = 44;
        goto LABEL_44;
      }
      goto LABEL_70;
    }
LABEL_69:
    *a4 = *(_DWORD *)(v22 + 12);
    goto LABEL_70;
  }
  v30 = (wchar_t *)CallStackTracing::s_wpInstance;
  v9 = -2147418113;
  if ( !CallStackTracing::s_wpInstance )
  {
    v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
    CallStackTracing::s_wpInstance = v31;
    if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
    {
      v30 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v30 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
  }
  if ( *((_BYTE *)v30 + 8) )
  {
    v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
    if ( *((_DWORD *)v32 + 499) != -2147418113 )
      CallStackContext::TraceFailure(v32, "CMFByteStreamSourceReader::EndReadData", 498, -2147418113);
  }
  if ( g_wppLevels )
  {
    v28 = 43;
    goto LABEL_44;
  }
LABEL_70:
  if ( v13 )
    ((void (__fastcall *)(IMFMediaBuffer *))v13->lpVtbl->Release)(v13);
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&pBuffer);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180037dec  push    rbp
0x180037dee  push    rbx
0x180037def  push    rsi
0x180037df0  push    rdi
0x180037df1  push    r12
0x180037df3  push    r13
0x180037df5  push    r14
0x180037df7  push    r15
0x180037df9  mov     rbp, rsp
0x180037dfc  sub     rsp, 48h
0x180037e00  mov     r12, r8
0x180037e03  lea     r14, aCmfbytestreams_3; "CMFByteStreamSourceReader::EndReadData"
0x180037e0a  mov     rbx, rdx
0x180037e0d  mov     rsi, rcx
0x180037e10  mov     rdx, r14; char *
0x180037e13  lea     rcx, [rbp+pBuffer]; this
0x180037e17  mov     r8d, 1C8h; int
0x180037e1d  mov     r13, r9
0x180037e20  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180037e25  mov     rcx, [rsi+10h]; this
0x180037e29  lea     r8, [rbp+pBuffer]; struct IMFMediaBuffer **
0x180037e2d  xor     r9d, r9d; struct CByteStreamCacheItem **
0x180037e30  mov     [rbp+var_10], 0
0x180037e38  mov     rdx, rbx; struct IMFAsyncResult *
0x180037e3b  mov     [rbp+pBuffer], 0
0x180037e43  mov     [rbp+var_18], 0
0x180037e4a  call    ?EndCacheRead@CByteStreamCacheReader2@@QEAAJPEAUIMFAsyncResult@@PEAPEAUIMFMediaBuffer@@PEAPEAVCByteStreamCacheItem@@@Z; CByteStreamCacheReader2::EndCacheRead(IMFAsyncResult *,IMFMediaBuffer * *,CByteStreamCacheItem * *)
0x180037e4f  mov     edi, eax
0x180037e51  test    eax, eax
0x180037e53  jns     short loc_180037EC9
0x180037e55  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037e5c  test    rcx, rcx
0x180037e5f  jnz     short loc_180037E6D
0x180037e61  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180037e66  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180037e6d  cmp     byte ptr [rcx+8], 0
0x180037e71  jz      short loc_180037E94
0x180037e73  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180037e78  cmp     [rax+7CCh], edi
0x180037e7e  jz      short loc_180037E94
0x180037e80  mov     r9d, edi; int
0x180037e83  mov     r8d, 1D4h; int
0x180037e89  mov     rdx, r14; char *
0x180037e8c  mov     rcx, rax; this
0x180037e8f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180037e94  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180037e9b  jb      short loc_180037EC0
0x180037e9d  mov     edx, 27h ; '''
0x180037ea2  mov     rcx, cs:WPP_GLOBAL_Control
0x180037ea9  lea     r8, WPP_f019a0467ccf3e64ef7099288b24b930_Traceguids
0x180037eb0  mov     r9, rsi
0x180037eb3  mov     [rsp+48h+var_28], edi
0x180037eb7  mov     rcx, [rcx+10h]
0x180037ebb  call    WPP_SF_qD
0x180037ec0  mov     rbx, [rbp+pBuffer]
0x180037ec4  jmp     loc_180038274
0x180037ec9  mov     dword ptr [rsi+18h], 0
0x180037ed0  mov     rcx, rbx
0x180037ed3  mov     rax, [rbx]
0x180037ed6  mov     rax, [rax+20h]
0x180037eda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037edf  mov     edi, eax
0x180037ee1  test    eax, eax
0x180037ee3  jns     loc_180037F7A
0x180037ee9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037ef0  test    rcx, rcx
0x180037ef3  jnz     short loc_180037F3C
0x180037ef5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180037efc  nop     dword ptr [rax+rax+00h]
0x180037f01  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180037f08  mov     rcx, rax
0x180037f0b  test    rax, rax
0x180037f0e  jz      short loc_180037F2E
0x180037f10  mov     rax, [rax]
0x180037f13  mov     edx, 7F0h
0x180037f18  mov     rax, [rax+8]
0x180037f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f21  test    eax, eax
0x180037f23  jz      short loc_180037F2E
0x180037f25  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037f2c  jmp     short loc_180037F3C
0x180037f2e  lea     rcx, qword_1801B97E0; this
0x180037f35  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180037f3c  cmp     byte ptr [rcx+8], 0
0x180037f40  jz      short loc_180037F63
0x180037f42  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180037f47  cmp     [rax+7CCh], edi
0x180037f4d  jz      short loc_180037F63
0x180037f4f  mov     r9d, edi; int
0x180037f52  mov     r8d, 1DBh; int
0x180037f58  mov     rdx, r14; char *
0x180037f5b  mov     rcx, rax; this
0x180037f5e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180037f63  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180037f6a  jb      loc_180037EC0
0x180037f70  mov     edx, 28h ; '('
0x180037f75  jmp     loc_180037EA2
0x180037f7a  mov     rax, [rbx]
0x180037f7d  lea     rdx, [rbp+var_10]
0x180037f81  mov     rcx, rbx
0x180037f84  mov     rax, [rax+18h]
0x180037f88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f8d  mov     edi, eax
0x180037f8f  test    eax, eax
0x180037f91  jns     loc_180038028
0x180037f97  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037f9e  test    rcx, rcx
0x180037fa1  jnz     short loc_180037FEA
0x180037fa3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180037faa  nop     dword ptr [rax+rax+00h]
0x180037faf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180037fb6  mov     rcx, rax
0x180037fb9  test    rax, rax
0x180037fbc  jz      short loc_180037FDC
0x180037fbe  mov     rax, [rax]
0x180037fc1  mov     edx, 7F0h
0x180037fc6  mov     rax, [rax+8]
0x180037fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037fcf  test    eax, eax
0x180037fd1  jz      short loc_180037FDC
0x180037fd3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037fda  jmp     short loc_180037FEA
0x180037fdc  lea     rcx, qword_1801B97E0; this
0x180037fe3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180037fea  cmp     byte ptr [rcx+8], 0
0x180037fee  jz      short loc_180038011
0x180037ff0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180037ff5  cmp     [rax+7CCh], edi
0x180037ffb  jz      short loc_180038011
0x180037ffd  mov     r9d, edi; int
0x180038000  mov     r8d, 1E0h; int
0x180038006  mov     rdx, r14; char *
0x180038009  mov     rcx, rax; this
0x18003800c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180038011  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038018  jb      loc_180037EC0
0x18003801e  mov     edx, 29h ; ')'
0x180038023  jmp     loc_180037EA2
0x180038028  mov     rbx, [rbp+pBuffer]
0x18003802c  lea     rdx, [rbp+var_18]
0x180038030  mov     r15, [rbp+var_10]
0x180038034  mov     rcx, rbx
0x180038037  mov     r14, rbx
0x18003803a  mov     rax, [rbx]
0x18003803d  mov     rax, [rax+28h]
0x180038041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038046  mov     edi, eax
0x180038048  test    eax, eax
0x18003804a  jns     loc_180038103
0x180038050  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038057  test    rcx, rcx
0x18003805a  jnz     short loc_1800380A3
0x18003805c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180038063  nop     dword ptr [rax+rax+00h]
0x180038068  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003806f  mov     rcx, rax
0x180038072  test    rax, rax
0x180038075  jz      short loc_180038095
0x180038077  mov     rax, [rax]
0x18003807a  mov     edx, 7F0h
0x18003807f  mov     rax, [rax+8]
0x180038083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038088  test    eax, eax
0x18003808a  jz      short loc_180038095
0x18003808c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038093  jmp     short loc_1800380A3
0x180038095  lea     rcx, qword_1801B97E0; this
0x18003809c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800380a3  cmp     byte ptr [rcx+8], 0
0x1800380a7  jz      short loc_1800380CE
0x1800380a9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800380ae  cmp     [rax+7CCh], edi
0x1800380b4  jz      short loc_1800380CE
0x1800380b6  mov     r9d, edi; int
0x1800380b9  lea     rdx, aCmfbytestreams_3; "CMFByteStreamSourceReader::EndReadData"
0x1800380c0  mov     r8d, 1E5h; int
0x1800380c6  mov     rcx, rax; this
0x1800380c9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800380ce  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800380d5  jb      loc_180038274
0x1800380db  mov     edx, 2Ah ; '*'
0x1800380e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800380e7  lea     r8, WPP_f019a0467ccf3e64ef7099288b24b930_Traceguids
0x1800380ee  mov     r9, rsi
0x1800380f1  mov     [rsp+48h+var_28], edi
0x1800380f5  mov     rcx, [rcx+10h]
0x1800380f9  call    WPP_SF_qD
0x1800380fe  jmp     loc_180038274
0x180038103  mov     edx, [r15+10h]; cbOffset
0x180038107  test    edx, edx
0x180038109  jz      loc_180038266
0x18003810f  mov     r8d, [rbp+var_18]
0x180038113  cmp     edx, r8d
0x180038116  jb      loc_1800381B6
0x18003811c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038123  mov     edi, 8000FFFFh
0x180038128  test    rcx, rcx
0x18003812b  jnz     short loc_180038174
0x18003812d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180038134  nop     dword ptr [rax+rax+00h]
0x180038139  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180038140  mov     rcx, rax
0x180038143  test    rax, rax
0x180038146  jz      short loc_180038166
0x180038148  mov     rax, [rax]
0x18003814b  mov     edx, 7F0h
0x180038150  mov     rax, [rax+8]
0x180038154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038159  test    eax, eax
0x18003815b  jz      short loc_180038166
0x18003815d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038164  jmp     short loc_180038174
0x180038166  lea     rcx, qword_1801B97E0; this
0x18003816d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180038174  cmp     byte ptr [rcx+8], 0
0x180038178  jz      short loc_18003819F
0x18003817a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003817f  cmp     [rax+7CCh], edi
0x180038185  jz      short loc_18003819F
0x180038187  mov     r9d, edi; int
0x18003818a  lea     rdx, aCmfbytestreams_3; "CMFByteStreamSourceReader::EndReadData"
0x180038191  mov     r8d, 1F2h; int
0x180038197  mov     rcx, rax; this
0x18003819a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003819f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800381a6  jb      loc_180038274
0x1800381ac  mov     edx, 2Bh ; '+'
0x1800381b1  jmp     loc_1800380E0
0x1800381b6  sub     r8d, edx; dwLength
0x1800381b9  mov     r9, r12; ppBuffer
0x1800381bc  mov     rcx, rbx; pBuffer
0x1800381bf  call    cs:__imp_MFCreateMediaBufferWrapper
0x1800381c6  nop     dword ptr [rax+rax+00h]
0x1800381cb  mov     edi, eax
0x1800381cd  test    eax, eax
0x1800381cf  jns     loc_18003826C
0x1800381d5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800381dc  test    rcx, rcx
0x1800381df  jnz     short loc_180038228
0x1800381e1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800381e8  nop     dword ptr [rax+rax+00h]
0x1800381ed  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800381f4  mov     rcx, rax
0x1800381f7  test    rax, rax
0x1800381fa  jz      short loc_18003821A
0x1800381fc  mov     rax, [rax]
0x1800381ff  mov     edx, 7F0h
0x180038204  mov     rax, [rax+8]
0x180038208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003820d  test    eax, eax
0x18003820f  jz      short loc_18003821A
0x180038211  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038218  jmp     short loc_180038228
0x18003821a  lea     rcx, qword_1801B97E0; this
0x180038221  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180038228  cmp     byte ptr [rcx+8], 0
0x18003822c  jz      short loc_180038253
0x18003822e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180038233  cmp     [rax+7CCh], edi
0x180038239  jz      short loc_180038253
0x18003823b  mov     r9d, edi; int
0x18003823e  lea     rdx, aCmfbytestreams_3; "CMFByteStreamSourceReader::EndReadData"
0x180038245  mov     r8d, 1F8h; int
0x18003824b  mov     rcx, rax; this
0x18003824e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180038253  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003825a  jb      short loc_180038274
0x18003825c  mov     edx, 2Ch ; ','
0x180038261  jmp     loc_1800380E0
0x180038266  xor     ebx, ebx
0x180038268  mov     [r12], r14
0x18003826c  mov     eax, [r15+0Ch]
0x180038270  mov     [r13+0], eax
0x180038274  test    rbx, rbx
0x180038277  jz      short loc_180038288
0x180038279  mov     rax, [rbx]
0x18003827c  mov     rcx, rbx
0x18003827f  mov     rax, [rax+10h]
0x180038283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038288  mov     rcx, [rbp+var_10]
0x18003828c  test    rcx, rcx
0x18003828f  jz      short loc_18003829D
0x180038291  mov     rax, [rcx]
0x180038294  mov     rax, [rax+10h]
0x180038298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003829d  lea     rcx, [rbp+pBuffer]; this
0x1800382a1  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800382a6  mov     eax, edi
0x1800382a8  add     rsp, 48h
0x1800382ac  pop     r15
0x1800382ae  pop     r14
0x1800382b0  pop     r13
0x1800382b2  pop     r12
0x1800382b4  pop     rdi
0x1800382b5  pop     rsi
0x1800382b6  pop     rbx
0x1800382b7  pop     rbp
0x1800382b8  retn
```
