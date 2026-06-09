# CMFVideoThumbnail::Generate(IStream *,tagPROPVARIANT *)

- ea: `0x1801637dc`
- end: `0x180163db3`
- name: `?Generate@CMFVideoThumbnail@@QEAAJPEAUIStream@@PEAUtagPROPVARIANT@@@Z`
- size: `1495`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, IStream *pStream, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004f1a0`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x18006fb00`
- `0x18007904c`
- `0x1800790a8`
- `0x180079680`
- `0x1800c5298`
- `0x1800e2cb8`
- `0x1800f4ef0`
- `0x180110ed0`
- `0x1801637dc`
- `0x1801645d0`
- `0x180164624`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801638d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180163990`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180163a7f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180163b33`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180163bf4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180163ca2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801638d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180163990`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180163a7f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180163b33`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180163bf4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180163ca2`
- `MFPlat!MFCreateMFByteStreamOnStream` at `0x18016396e`
- `MFPlat!MFCreateMFByteStreamOnStream` at `0x18016396e`

## pseudocode

```c
__int64 __fastcall CMFVideoThumbnail::Generate(CMFVideoThumbnail *this, IStream *pStream, struct tagPROPVARIANT *a3)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v7; // ebx
  __int128 v8; // xmm0
  __int64 v9; // rdx
  HRESULT started; // ebx
  wchar_t *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  wchar_t *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  wchar_t *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  wchar_t *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  wchar_t *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  struct IUnknown **v35; // rcx
  _BYTE v37[8]; // [rsp+30h] [rbp-40h] BYREF
  struct IMFSourceReader *v38; // [rsp+38h] [rbp-38h] BYREF
  struct IMFMediaType *v39; // [rsp+40h] [rbp-30h] BYREF
  struct IMFSample *v40; // [rsp+48h] [rbp-28h] BYREF
  IMFByteStream *ppByteStream; // [rsp+50h] [rbp-20h] BYREF
  _BYTE v42[16]; // [rsp+58h] [rbp-18h] BYREF

  if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
    McTemplateU0pq_EventWriteTransfer(
      this,
      Property_Handler_ThumbnailGeneration_Start,
      this,
      *((unsigned int *)this + 7));
  ppByteStream = 0;
  v38 = 0;
  v40 = 0;
  v39 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v37, "CMFVideoThumbnail::Generate", 317);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 50) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 296LL))(*((_QWORD *)this + 50));
    v8 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 50) + 280LL))(
                      *((_QWORD *)this + 50),
                      v42);
    *((_DWORD *)ThreadRelativeContext + 504) = v7;
    *((_OWORD *)ThreadRelativeContext + 125) = v8;
  }
  started = CMFVideoThumbnail::StartTiming(this);
  if ( started >= 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppByteStream);
    started = MFCreateMFByteStreamOnStream(pStream, &ppByteStream);
    if ( started >= 0 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
      started = CMFVideoThumbnail::CreateSourceReaderFromMFSource(this, ppByteStream, &v38);
      if ( !started )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
        started = CMFVideoThumbnail::GetRepresentativeFrame(this, v38, &v40, &v39);
      }
      if ( started < 0 )
      {
        if ( (unsigned int)(*((_DWORD *)this + 7) - 4) > 1 )
        {
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
            if ( *((_DWORD *)v22 + 499) != started )
              CallStackContext::TraceFailure(v22, "CMFVideoThumbnail::Generate", 353, started);
          }
          if ( g_wppLevels )
          {
            v14 = 18;
            goto LABEL_75;
          }
          goto LABEL_76;
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        started = CMFVideoThumbnail::CreateSourceReaderFromDShowSource(this, ppByteStream, &v38);
        if ( started < 0 )
        {
          v24 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
            CallStackTracing::s_wpInstance = v25;
            if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
            {
              v24 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v24 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v24 + 8) )
          {
            v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
            if ( *((_DWORD *)v26 + 499) != started )
              CallStackContext::TraceFailure(v26, "CMFVideoThumbnail::Generate", 360, started);
          }
          if ( g_wppLevels )
          {
            v14 = 19;
            goto LABEL_75;
          }
          goto LABEL_76;
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
        started = CMFVideoThumbnail::GetRepresentativeFrame(this, v38, &v40, &v39);
        if ( started < 0 )
        {
          v28 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
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
          if ( *((_BYTE *)v28 + 8) )
          {
            v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
            if ( *((_DWORD *)v30 + 499) != started )
              CallStackContext::TraceFailure(v30, "CMFVideoThumbnail::Generate", 362, started);
          }
          if ( g_wppLevels )
          {
            v14 = 20;
            goto LABEL_75;
          }
          goto LABEL_76;
        }
      }
      started = CMFVideoThumbnail::MFSampleToThumbnailStream(this, v39, v40, a3);
      if ( started < 0 )
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
          if ( *((_DWORD *)v34 + 499) != started )
            CallStackContext::TraceFailure(v34, "CMFVideoThumbnail::Generate", 365, started);
        }
        if ( g_wppLevels )
        {
          v14 = 21;
          goto LABEL_75;
        }
      }
      goto LABEL_76;
    }
    v16 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
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
      if ( *((_DWORD *)v18 + 499) != started )
        CallStackContext::TraceFailure(v18, "CMFVideoThumbnail::Generate", 332, started);
    }
    if ( g_wppLevels )
    {
      v14 = 17;
      goto LABEL_75;
    }
  }
  else
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
      v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)v13 + 499) != started )
        CallStackContext::TraceFailure(v13, "CMFVideoThumbnail::Generate", 319, started);
    }
    if ( g_wppLevels )
    {
      v14 = 16;
LABEL_75:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids,
        this,
        started);
    }
  }
LABEL_76:
  v35 = (struct IUnknown **)((char *)this + 32);
  if ( *((_QWORD *)this + 4) )
    ATL::AtlComPtrAssign(v35, 0);
  if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
    McTemplateU0pq_EventWriteTransfer(v35, Property_Handler_ThumbnailGeneration_End, this, *((unsigned int *)this + 7));
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v37);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppByteStream);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1801637dc  push    rbp
0x1801637de  push    rbx
0x1801637df  push    rsi
0x1801637e0  push    rdi
0x1801637e1  push    r12
0x1801637e3  push    r14
0x1801637e5  push    r15
0x1801637e7  mov     rbp, rsp
0x1801637ea  sub     rsp, 70h
0x1801637ee  mov     rax, cs:__security_cookie
0x1801637f5  xor     rax, rsp
0x1801637f8  mov     [rbp+var_8], rax
0x1801637fc  test    cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 1
0x180163803  mov     r15, r8
0x180163806  mov     r14, rdx
0x180163809  mov     rsi, rcx
0x18016380c  jz      short loc_180163821
0x18016380e  mov     r9d, [rcx+1Ch]
0x180163812  lea     rdx, Property_Handler_ThumbnailGeneration_Start
0x180163819  mov     r8, rcx
0x18016381c  call    McTemplateU0pq_EventWriteTransfer
0x180163821  xor     r12d, r12d
0x180163824  lea     rdi, aCmfvideothumbn_6; "CMFVideoThumbnail::Generate"
0x18016382b  mov     rdx, rdi; char *
0x18016382e  mov     [rbp+ppByteStream], r12
0x180163832  mov     r8d, 13Dh; int
0x180163838  mov     [rbp+var_38], r12
0x18016383c  lea     rcx, [rbp+var_40]; this
0x180163840  mov     [rbp+var_28], r12
0x180163844  mov     [rbp+var_30], r12
0x180163848  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18016384d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180163854  cmp     [rcx+8], r12b
0x180163858  jz      short loc_1801638BB
0x18016385a  cmp     [rsi+190h], r12
0x180163861  jz      short loc_1801638BB
0x180163863  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180163868  mov     rdx, [rsi+190h]
0x18016386f  mov     rdi, rax
0x180163872  mov     rcx, [rdx]
0x180163875  mov     rax, [rcx+128h]
0x18016387c  mov     rcx, rdx
0x18016387f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180163884  mov     r8, [rsi+190h]
0x18016388b  lea     rdx, [rbp+var_18]
0x18016388f  mov     ebx, eax
0x180163891  mov     rcx, [r8]
0x180163894  mov     rax, [rcx+118h]
0x18016389b  mov     rcx, r8
0x18016389e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801638a3  movups  xmm0, xmmword ptr [rax]
0x1801638a6  mov     [rdi+7E0h], ebx
0x1801638ac  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1801638b4  lea     rdi, aCmfvideothumbn_6; "CMFVideoThumbnail::Generate"
0x1801638bb  mov     rcx, rsi; this
0x1801638be  call    ?StartTiming@CMFVideoThumbnail@@AEAAJXZ; CMFVideoThumbnail::StartTiming(void)
0x1801638c3  mov     ebx, eax
0x1801638c5  test    eax, eax
0x1801638c7  jns     loc_18016395E
0x1801638cd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801638d4  test    rcx, rcx
0x1801638d7  jnz     short loc_180163920
0x1801638d9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801638e0  nop     dword ptr [rax+rax+00h]
0x1801638e5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801638ec  mov     rcx, rax
0x1801638ef  test    rax, rax
0x1801638f2  jz      short loc_180163912
0x1801638f4  mov     rax, [rax]
0x1801638f7  mov     edx, 7F0h
0x1801638fc  mov     rax, [rax+8]
0x180163900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180163905  test    eax, eax
0x180163907  jz      short loc_180163912
0x180163909  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180163910  jmp     short loc_180163920
0x180163912  lea     rcx, qword_1801B97E0; this
0x180163919  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180163920  cmp     [rcx+8], r12b
0x180163924  jz      short loc_180163947
0x180163926  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18016392b  cmp     [rax+7CCh], ebx
0x180163931  jz      short loc_180163947
0x180163933  mov     r9d, ebx; int
0x180163936  mov     r8d, 13Fh; int
0x18016393c  mov     rdx, rdi; char *
0x18016393f  mov     rcx, rax; this
0x180163942  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180163947  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18016394e  jb      loc_180163D3C
0x180163954  mov     edx, 10h
0x180163959  jmp     loc_180163D1E
0x18016395e  lea     rcx, [rbp+ppByteStream]
0x180163962  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180163967  lea     rdx, [rbp+ppByteStream]; ppByteStream
0x18016396b  mov     rcx, r14; pStream
0x18016396e  call    cs:__imp_MFCreateMFByteStreamOnStream
0x180163975  nop     dword ptr [rax+rax+00h]
0x18016397a  mov     ebx, eax
0x18016397c  test    eax, eax
0x18016397e  jns     loc_180163A15
0x180163984  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016398b  test    rcx, rcx
0x18016398e  jnz     short loc_1801639D7
0x180163990  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180163997  nop     dword ptr [rax+rax+00h]
0x18016399c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801639a3  mov     rcx, rax
0x1801639a6  test    rax, rax
0x1801639a9  jz      short loc_1801639C9
0x1801639ab  mov     rax, [rax]
0x1801639ae  mov     edx, 7F0h
0x1801639b3  mov     rax, [rax+8]
0x1801639b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801639bc  test    eax, eax
0x1801639be  jz      short loc_1801639C9
0x1801639c0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801639c7  jmp     short loc_1801639D7
0x1801639c9  lea     rcx, qword_1801B97E0; this
0x1801639d0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801639d7  cmp     [rcx+8], r12b
0x1801639db  jz      short loc_1801639FE
0x1801639dd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801639e2  cmp     [rax+7CCh], ebx
0x1801639e8  jz      short loc_1801639FE
0x1801639ea  mov     r9d, ebx; int
0x1801639ed  mov     r8d, 14Ch; int
0x1801639f3  mov     rdx, rdi; char *
0x1801639f6  mov     rcx, rax; this
0x1801639f9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801639fe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180163a05  jb      loc_180163D3C
0x180163a0b  mov     edx, 11h
0x180163a10  jmp     loc_180163D1E
0x180163a15  lea     rcx, [rbp+var_38]
0x180163a19  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180163a1e  mov     rdx, [rbp+ppByteStream]; struct IMFByteStream *
0x180163a22  lea     r8, [rbp+var_38]; struct IMFSourceReader **
0x180163a26  mov     rcx, rsi; this
0x180163a29  call    ?CreateSourceReaderFromMFSource@CMFVideoThumbnail@@AEAAJPEAUIMFByteStream@@PEAPEAUIMFSourceReader@@@Z; CMFVideoThumbnail::CreateSourceReaderFromMFSource(IMFByteStream *,IMFSourceReader * *)
0x180163a2e  mov     ebx, eax
0x180163a30  test    eax, eax
0x180163a32  jnz     short loc_180163A5C
0x180163a34  lea     rcx, [rbp+var_30]
0x180163a38  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180163a3d  lea     rcx, [rbp+var_28]
0x180163a41  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180163a46  mov     rdx, [rbp+var_38]; struct IMFSourceReader *
0x180163a4a  lea     r9, [rbp+var_30]; struct IMFMediaType **
0x180163a4e  lea     r8, [rbp+var_28]; struct IMFSample **
0x180163a52  mov     rcx, rsi; this
0x180163a55  call    ?GetRepresentativeFrame@CMFVideoThumbnail@@AEAAJPEAUIMFSourceReader@@PEAPEAUIMFSample@@PEAPEAUIMFMediaType@@@Z; CMFVideoThumbnail::GetRepresentativeFrame(IMFSourceReader *,IMFSample * *,IMFMediaType * *)
0x180163a5a  mov     ebx, eax
0x180163a5c  test    ebx, ebx
0x180163a5e  jns     loc_180163C79
0x180163a64  mov     eax, [rsi+1Ch]
0x180163a67  sub     eax, 4
0x180163a6a  cmp     eax, 1
0x180163a6d  jbe     loc_180163B04
0x180163a73  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180163a7a  test    rcx, rcx
0x180163a7d  jnz     short loc_180163AC6
0x180163a7f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180163a86  nop     dword ptr [rax+rax+00h]
0x180163a8b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180163a92  mov     rcx, rax
0x180163a95  test    rax, rax
0x180163a98  jz      short loc_180163AB8
0x180163a9a  mov     rax, [rax]
0x180163a9d  mov     edx, 7F0h
0x180163aa2  mov     rax, [rax+8]
0x180163aa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180163aab  test    eax, eax
0x180163aad  jz      short loc_180163AB8
0x180163aaf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180163ab6  jmp     short loc_180163AC6
0x180163ab8  lea     rcx, qword_1801B97E0; this
0x180163abf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180163ac6  cmp     [rcx+8], r12b
0x180163aca  jz      short loc_180163AED
0x180163acc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180163ad1  cmp     [rax+7CCh], ebx
0x180163ad7  jz      short loc_180163AED
0x180163ad9  mov     r9d, ebx; int
0x180163adc  mov     r8d, 161h; int
0x180163ae2  mov     rdx, rdi; char *
0x180163ae5  mov     rcx, rax; this
0x180163ae8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180163aed  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180163af4  jb      loc_180163D3C
0x180163afa  mov     edx, 12h
0x180163aff  jmp     loc_180163D1E
0x180163b04  lea     rcx, [rbp+var_38]
0x180163b08  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180163b0d  mov     rdx, [rbp+ppByteStream]; struct IMFByteStream *
0x180163b11  lea     r8, [rbp+var_38]; struct IMFSourceReader **
0x180163b15  mov     rcx, rsi; this
0x180163b18  call    ?CreateSourceReaderFromDShowSource@CMFVideoThumbnail@@AEAAJPEAUIMFByteStream@@PEAPEAUIMFSourceReader@@@Z; CMFVideoThumbnail::CreateSourceReaderFromDShowSource(IMFByteStream *,IMFSourceReader * *)
0x180163b1d  mov     ebx, eax
0x180163b1f  test    eax, eax
0x180163b21  jns     loc_180163BB8
0x180163b27  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180163b2e  test    rcx, rcx
0x180163b31  jnz     short loc_180163B7A
0x180163b33  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180163b3a  nop     dword ptr [rax+rax+00h]
0x180163b3f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180163b46  mov     rcx, rax
0x180163b49  test    rax, rax
0x180163b4c  jz      short loc_180163B6C
0x180163b4e  mov     rax, [rax]
0x180163b51  mov     edx, 7F0h
0x180163b56  mov     rax, [rax+8]
0x180163b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180163b5f  test    eax, eax
0x180163b61  jz      short loc_180163B6C
0x180163b63  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180163b6a  jmp     short loc_180163B7A
0x180163b6c  lea     rcx, qword_1801B97E0; this
0x180163b73  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180163b7a  cmp     [rcx+8], r12b
0x180163b7e  jz      short loc_180163BA1
0x180163b80  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180163b85  cmp     [rax+7CCh], ebx
0x180163b8b  jz      short loc_180163BA1
0x180163b8d  mov     r9d, ebx; int
0x180163b90  mov     r8d, 168h; int
0x180163b96  mov     rdx, rdi; char *
0x180163b99  mov     rcx, rax; this
0x180163b9c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180163ba1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180163ba8  jb      loc_180163D3C
0x180163bae  mov     edx, 13h
0x180163bb3  jmp     loc_180163D1E
0x180163bb8  lea     rcx, [rbp+var_30]
0x180163bbc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180163bc1  lea     rcx, [rbp+var_28]
0x180163bc5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180163bca  mov     rdx, [rbp+var_38]; struct IMFSourceReader *
0x180163bce  lea     r9, [rbp+var_30]; struct IMFMediaType **
0x180163bd2  lea     r8, [rbp+var_28]; struct IMFSample **
0x180163bd6  mov     rcx, rsi; this
0x180163bd9  call    ?GetRepresentativeFrame@CMFVideoThumbnail@@AEAAJPEAUIMFSourceReader@@PEAPEAUIMFSample@@PEAPEAUIMFMediaType@@@Z; CMFVideoThumbnail::GetRepresentativeFrame(IMFSourceReader *,IMFSample * *,IMFMediaType * *)
0x180163bde  mov     ebx, eax
0x180163be0  test    eax, eax
0x180163be2  jns     loc_180163C79
0x180163be8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180163bef  test    rcx, rcx
0x180163bf2  jnz     short loc_180163C3B
0x180163bf4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180163bfb  nop     dword ptr [rax+rax+00h]
0x180163c00  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180163c07  mov     rcx, rax
0x180163c0a  test    rax, rax
0x180163c0d  jz      short loc_180163C2D
0x180163c0f  mov     rax, [rax]
0x180163c12  mov     edx, 7F0h
0x180163c17  mov     rax, [rax+8]
0x180163c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180163c20  test    eax, eax
0x180163c22  jz      short loc_180163C2D
0x180163c24  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180163c2b  jmp     short loc_180163C3B
0x180163c2d  lea     rcx, qword_1801B97E0; this
0x180163c34  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180163c3b  cmp     [rcx+8], r12b
0x180163c3f  jz      short loc_180163C62
0x180163c41  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180163c46  cmp     [rax+7CCh], ebx
0x180163c4c  jz      short loc_180163C62
0x180163c4e  mov     r9d, ebx; int
0x180163c51  mov     r8d, 16Ah; int
0x180163c57  mov     rdx, rdi; char *
0x180163c5a  mov     rcx, rax; this
0x180163c5d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180163c62  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180163c69  jb      loc_180163D3C
0x180163c6f  mov     edx, 14h
0x180163c74  jmp     loc_180163D1E
0x180163c79  mov     r8, [rbp+var_28]; struct IMFSample *
0x180163c7d  mov     r9, r15; struct tagPROPVARIANT *
0x180163c80  mov     rdx, [rbp+var_30]; struct IMFMediaType *
0x180163c84  mov     rcx, rsi; this
0x180163c87  call    ?MFSampleToThumbnailStream@CMFVideoThumbnail@@AEAAJPEAUIMFMediaType@@PEAUIMFSample@@PEAUtagPROPVARIANT@@@Z; CMFVideoThumbnail::MFSampleToThumbnailStream(IMFMediaType *,IMFSample *,tagPROPVARIANT *)
0x180163c8c  mov     ebx, eax
0x180163c8e  test    eax, eax
0x180163c90  jns     loc_180163D3C
0x180163c96  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180163c9d  test    rcx, rcx
0x180163ca0  jnz     short loc_180163CE9
0x180163ca2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180163ca9  nop     dword ptr [rax+rax+00h]
0x180163cae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180163cb5  mov     rcx, rax
0x180163cb8  test    rax, rax
0x180163cbb  jz      short loc_180163CDB
0x180163cbd  mov     rax, [rax]
0x180163cc0  mov     edx, 7F0h
0x180163cc5  mov     rax, [rax+8]
0x180163cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
