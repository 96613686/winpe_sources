# CMFByteStreamSourceReader::EndReadData(IMFAsyncResult *,IMFMediaBuffer * *,ulong *)

- ea: `0x18005de70`
- end: `0x18005e319`
- name: `?EndReadData@CMFByteStreamSourceReader@@QEAAJPEAUIMFAsyncResult@@PEAPEAUIMFMediaBuffer@@PEAK@Z`
- size: `1193`
- prototype: `__int64 __fastcall(CMFByteStreamSourceReader *this, struct IMFAsyncResult *, struct IMFMediaBuffer **, unsigned int *)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x18005d368`
- `0x1800846ec`
- `0x1800d5160`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x18005de70`
- `0x18005feac`
- `0x180071a44`
- `0x180073b14`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005df79`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e021`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e0d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e19f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e247`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005df79`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e021`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e0d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e19f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e247`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x18005e22b`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x18005e22b`

## string_xrefs

- `0x18005de87`: `CMFByteStreamSourceReader::EndReadData`
- `0x18005e12b`: `CMFByteStreamSourceReader::EndReadData`
- `0x18005e1f6`: `CMFByteStreamSourceReader::EndReadData`
- `0x18005e29e`: `CMFByteStreamSourceReader::EndReadData`

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
        v15 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v19 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v25 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v34 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
      v30 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
0x18005de70  push    rbp
0x18005de72  push    rbx
0x18005de73  push    rsi
0x18005de74  push    rdi
0x18005de75  push    r12
0x18005de77  push    r13
0x18005de79  push    r14
0x18005de7b  push    r15
0x18005de7d  mov     rbp, rsp
0x18005de80  sub     rsp, 48h
0x18005de84  mov     r12, r8
0x18005de87  lea     r14, aCmfbytestreams_3; "CMFByteStreamSourceReader::EndReadData"
0x18005de8e  mov     rbx, rdx
0x18005de91  mov     rsi, rcx
0x18005de94  mov     rdx, r14; char *
0x18005de97  lea     rcx, [rbp+pBuffer]; this
0x18005de9b  mov     r8d, 1C8h; int
0x18005dea1  mov     r13, r9
0x18005dea4  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18005dea9  mov     rcx, [rsi+10h]; this
0x18005dead  lea     r8, [rbp+pBuffer]; struct IMFMediaBuffer **
0x18005deb1  xor     r9d, r9d; struct CByteStreamCacheItem **
0x18005deb4  mov     [rbp+var_10], 0
0x18005debc  mov     rdx, rbx; struct IMFAsyncResult *
0x18005debf  mov     [rbp+pBuffer], 0
0x18005dec7  mov     [rbp+var_18], 0
0x18005dece  call    ?EndCacheRead@CByteStreamCacheReader2@@QEAAJPEAUIMFAsyncResult@@PEAPEAUIMFMediaBuffer@@PEAPEAVCByteStreamCacheItem@@@Z; CByteStreamCacheReader2::EndCacheRead(IMFAsyncResult *,IMFMediaBuffer * *,CByteStreamCacheItem * *)
0x18005ded3  mov     edi, eax
0x18005ded5  test    eax, eax
0x18005ded7  jns     short loc_18005DF4D
0x18005ded9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005dee0  test    rcx, rcx
0x18005dee3  jnz     short loc_18005DEF1
0x18005dee5  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18005deea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18005def1  cmp     byte ptr [rcx+8], 0
0x18005def5  jz      short loc_18005DF18
0x18005def7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005defc  cmp     [rax+7CCh], edi
0x18005df02  jz      short loc_18005DF18
0x18005df04  mov     r9d, edi; int
0x18005df07  mov     r8d, 1D4h; int
0x18005df0d  mov     rdx, r14; char *
0x18005df10  mov     rcx, rax; this
0x18005df13  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005df18  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005df1f  jb      short loc_18005DF44
0x18005df21  mov     edx, 27h ; '''
0x18005df26  mov     rcx, cs:WPP_GLOBAL_Control
0x18005df2d  lea     r8, WPP_f019a0467ccf3e64ef7099288b24b930_Traceguids
0x18005df34  mov     r9, rsi
0x18005df37  mov     [rsp+48h+var_28], edi
0x18005df3b  mov     rcx, [rcx+10h]
0x18005df3f  call    WPP_SF_qD
0x18005df44  mov     rbx, [rbp+pBuffer]
0x18005df48  jmp     loc_18005E2D4
0x18005df4d  mov     dword ptr [rsi+18h], 0
0x18005df54  mov     rcx, rbx
0x18005df57  mov     rax, [rbx]
0x18005df5a  mov     rax, [rax+20h]
0x18005df5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005df63  mov     edi, eax
0x18005df65  test    eax, eax
0x18005df67  jns     loc_18005DFF8
0x18005df6d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005df74  test    rcx, rcx
0x18005df77  jnz     short loc_18005DFBA
0x18005df79  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005df7f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005df86  mov     rcx, rax
0x18005df89  test    rax, rax
0x18005df8c  jz      short loc_18005DFAC
0x18005df8e  mov     rax, [rax]
0x18005df91  mov     edx, 7F0h
0x18005df96  mov     rax, [rax+8]
0x18005df9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005df9f  test    eax, eax
0x18005dfa1  jz      short loc_18005DFAC
0x18005dfa3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005dfaa  jmp     short loc_18005DFBA
0x18005dfac  lea     rcx, qword_1801B07E0; this
0x18005dfb3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005dfba  cmp     byte ptr [rcx+8], 0
0x18005dfbe  jz      short loc_18005DFE1
0x18005dfc0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005dfc5  cmp     [rax+7CCh], edi
0x18005dfcb  jz      short loc_18005DFE1
0x18005dfcd  mov     r9d, edi; int
0x18005dfd0  mov     r8d, 1DBh; int
0x18005dfd6  mov     rdx, r14; char *
0x18005dfd9  mov     rcx, rax; this
0x18005dfdc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005dfe1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005dfe8  jb      loc_18005DF44
0x18005dfee  mov     edx, 28h ; '('
0x18005dff3  jmp     loc_18005DF26
0x18005dff8  mov     rax, [rbx]
0x18005dffb  lea     rdx, [rbp+var_10]
0x18005dfff  mov     rcx, rbx
0x18005e002  mov     rax, [rax+18h]
0x18005e006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e00b  mov     edi, eax
0x18005e00d  test    eax, eax
0x18005e00f  jns     loc_18005E0A0
0x18005e015  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e01c  test    rcx, rcx
0x18005e01f  jnz     short loc_18005E062
0x18005e021  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005e027  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e02e  mov     rcx, rax
0x18005e031  test    rax, rax
0x18005e034  jz      short loc_18005E054
0x18005e036  mov     rax, [rax]
0x18005e039  mov     edx, 7F0h
0x18005e03e  mov     rax, [rax+8]
0x18005e042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e047  test    eax, eax
0x18005e049  jz      short loc_18005E054
0x18005e04b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e052  jmp     short loc_18005E062
0x18005e054  lea     rcx, qword_1801B07E0; this
0x18005e05b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e062  cmp     byte ptr [rcx+8], 0
0x18005e066  jz      short loc_18005E089
0x18005e068  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005e06d  cmp     [rax+7CCh], edi
0x18005e073  jz      short loc_18005E089
0x18005e075  mov     r9d, edi; int
0x18005e078  mov     r8d, 1E0h; int
0x18005e07e  mov     rdx, r14; char *
0x18005e081  mov     rcx, rax; this
0x18005e084  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005e089  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005e090  jb      loc_18005DF44
0x18005e096  mov     edx, 29h ; ')'
0x18005e09b  jmp     loc_18005DF26
0x18005e0a0  mov     rbx, [rbp+pBuffer]
0x18005e0a4  lea     rdx, [rbp+var_18]
0x18005e0a8  mov     r15, [rbp+var_10]
0x18005e0ac  mov     rcx, rbx
0x18005e0af  mov     r14, rbx
0x18005e0b2  mov     rax, [rbx]
0x18005e0b5  mov     rax, [rax+28h]
0x18005e0b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e0be  mov     edi, eax
0x18005e0c0  test    eax, eax
0x18005e0c2  jns     loc_18005E175
0x18005e0c8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e0cf  test    rcx, rcx
0x18005e0d2  jnz     short loc_18005E115
0x18005e0d4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005e0da  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e0e1  mov     rcx, rax
0x18005e0e4  test    rax, rax
0x18005e0e7  jz      short loc_18005E107
0x18005e0e9  mov     rax, [rax]
0x18005e0ec  mov     edx, 7F0h
0x18005e0f1  mov     rax, [rax+8]
0x18005e0f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e0fa  test    eax, eax
0x18005e0fc  jz      short loc_18005E107
0x18005e0fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e105  jmp     short loc_18005E115
0x18005e107  lea     rcx, qword_1801B07E0; this
0x18005e10e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e115  cmp     byte ptr [rcx+8], 0
0x18005e119  jz      short loc_18005E140
0x18005e11b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005e120  cmp     [rax+7CCh], edi
0x18005e126  jz      short loc_18005E140
0x18005e128  mov     r9d, edi; int
0x18005e12b  lea     rdx, aCmfbytestreams_3; "CMFByteStreamSourceReader::EndReadData"
0x18005e132  mov     r8d, 1E5h; int
0x18005e138  mov     rcx, rax; this
0x18005e13b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005e140  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005e147  jb      loc_18005E2D4
0x18005e14d  mov     edx, 2Ah ; '*'
0x18005e152  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e159  lea     r8, WPP_f019a0467ccf3e64ef7099288b24b930_Traceguids
0x18005e160  mov     r9, rsi
0x18005e163  mov     [rsp+48h+var_28], edi
0x18005e167  mov     rcx, [rcx+10h]
0x18005e16b  call    WPP_SF_qD
0x18005e170  jmp     loc_18005E2D4
0x18005e175  mov     edx, [r15+10h]; cbOffset
0x18005e179  test    edx, edx
0x18005e17b  jz      loc_18005E2C6
0x18005e181  mov     r8d, [rbp+var_18]
0x18005e185  cmp     edx, r8d
0x18005e188  jb      loc_18005E222
0x18005e18e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e195  mov     edi, 8000FFFFh
0x18005e19a  test    rcx, rcx
0x18005e19d  jnz     short loc_18005E1E0
0x18005e19f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005e1a5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e1ac  mov     rcx, rax
0x18005e1af  test    rax, rax
0x18005e1b2  jz      short loc_18005E1D2
0x18005e1b4  mov     rax, [rax]
0x18005e1b7  mov     edx, 7F0h
0x18005e1bc  mov     rax, [rax+8]
0x18005e1c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e1c5  test    eax, eax
0x18005e1c7  jz      short loc_18005E1D2
0x18005e1c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e1d0  jmp     short loc_18005E1E0
0x18005e1d2  lea     rcx, qword_1801B07E0; this
0x18005e1d9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e1e0  cmp     byte ptr [rcx+8], 0
0x18005e1e4  jz      short loc_18005E20B
0x18005e1e6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005e1eb  cmp     [rax+7CCh], edi
0x18005e1f1  jz      short loc_18005E20B
0x18005e1f3  mov     r9d, edi; int
0x18005e1f6  lea     rdx, aCmfbytestreams_3; "CMFByteStreamSourceReader::EndReadData"
0x18005e1fd  mov     r8d, 1F2h; int
0x18005e203  mov     rcx, rax; this
0x18005e206  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005e20b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005e212  jb      loc_18005E2D4
0x18005e218  mov     edx, 2Bh ; '+'
0x18005e21d  jmp     loc_18005E152
0x18005e222  sub     r8d, edx; dwLength
0x18005e225  mov     r9, r12; ppBuffer
0x18005e228  mov     rcx, rbx; pBuffer
0x18005e22b  call    cs:__imp_MFCreateMediaBufferWrapper
0x18005e231  mov     edi, eax
0x18005e233  test    eax, eax
0x18005e235  jns     loc_18005E2CC
0x18005e23b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e242  test    rcx, rcx
0x18005e245  jnz     short loc_18005E288
0x18005e247  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005e24d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e254  mov     rcx, rax
0x18005e257  test    rax, rax
0x18005e25a  jz      short loc_18005E27A
0x18005e25c  mov     rax, [rax]
0x18005e25f  mov     edx, 7F0h
0x18005e264  mov     rax, [rax+8]
0x18005e268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e26d  test    eax, eax
0x18005e26f  jz      short loc_18005E27A
0x18005e271  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e278  jmp     short loc_18005E288
0x18005e27a  lea     rcx, qword_1801B07E0; this
0x18005e281  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e288  cmp     byte ptr [rcx+8], 0
0x18005e28c  jz      short loc_18005E2B3
0x18005e28e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005e293  cmp     [rax+7CCh], edi
0x18005e299  jz      short loc_18005E2B3
0x18005e29b  mov     r9d, edi; int
0x18005e29e  lea     rdx, aCmfbytestreams_3; "CMFByteStreamSourceReader::EndReadData"
0x18005e2a5  mov     r8d, 1F8h; int
0x18005e2ab  mov     rcx, rax; this
0x18005e2ae  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005e2b3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005e2ba  jb      short loc_18005E2D4
0x18005e2bc  mov     edx, 2Ch ; ','
0x18005e2c1  jmp     loc_18005E152
0x18005e2c6  xor     ebx, ebx
0x18005e2c8  mov     [r12], r14
0x18005e2cc  mov     eax, [r15+0Ch]
0x18005e2d0  mov     [r13+0], eax
0x18005e2d4  test    rbx, rbx
0x18005e2d7  jz      short loc_18005E2E8
0x18005e2d9  mov     rax, [rbx]
0x18005e2dc  mov     rcx, rbx
0x18005e2df  mov     rax, [rax+10h]
0x18005e2e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e2e8  mov     rcx, [rbp+var_10]
0x18005e2ec  test    rcx, rcx
0x18005e2ef  jz      short loc_18005E2FD
0x18005e2f1  mov     rax, [rcx]
0x18005e2f4  mov     rax, [rax+10h]
0x18005e2f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e2fd  lea     rcx, [rbp+pBuffer]; this
0x18005e301  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18005e306  mov     eax, edi
0x18005e308  add     rsp, 48h
0x18005e30c  pop     r15
0x18005e30e  pop     r14
0x18005e310  pop     r13
0x18005e312  pop     r12
0x18005e314  pop     rdi
0x18005e315  pop     rsi
0x18005e316  pop     rbx
0x18005e317  pop     rbp
0x18005e318  retn
```
