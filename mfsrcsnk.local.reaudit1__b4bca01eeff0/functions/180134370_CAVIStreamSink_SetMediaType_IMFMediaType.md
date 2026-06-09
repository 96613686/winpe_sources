# CAVIStreamSink::SetMediaType(IMFMediaType *)

- ea: `0x180134370`
- end: `0x180134749`
- name: `?SetMediaType@CAVIStreamSink@@UEAAJPEAUIMFMediaType@@@Z`
- size: `985`
- prototype: `int(CAVIStreamSink *__hidden this, struct IMFMediaType *)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x1800790a8`
- `0x180079680`
- `0x1801310a0`
- `0x180134370`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801343cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180134478`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180134531`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801345e5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013468f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801343cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180134478`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180134531`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801345e5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013468f`
- `MFPlat!MFCreateMediaType` at `0x18013450f`
- `MFPlat!MFCreateMediaType` at `0x18013450f`

## string_xrefs

- `0x180134385`: `CAVIStreamSink::SetMediaType`

## pseudocode

```c
__int64 __fastcall CAVIStreamSink::SetMediaType(CAVIStreamSink *this, struct IMFMediaType *a2)
{
  HRESULT MinSampleSizeForMediaType; // ebx
  __int64 v5; // rdx
  _QWORD *v6; // rsi
  wchar_t *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  wchar_t *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
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
  struct CallStackContext *ThreadRelativeContext; // rax
  char v28; // [rsp+58h] [rbp+10h] BYREF

  MinSampleSizeForMediaType = a2 == 0 ? 0x80004003 : 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v28, "CAVIStreamSink::SetMediaType", 576);
  v6 = (_QWORD *)((char *)this - 32);
  if ( a2 )
  {
    MinSampleSizeForMediaType = (*(__int64 (__fastcall **)(char *, struct IMFMediaType *))(*v6 + 32LL))(
                                  (char *)this - 32,
                                  a2);
    if ( MinSampleSizeForMediaType >= 0 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 336);
      MinSampleSizeForMediaType = MFCreateMediaType((IMFMediaType **)this + 42);
      if ( MinSampleSizeForMediaType >= 0 )
      {
        MinSampleSizeForMediaType = ((__int64 (__fastcall *)(struct IMFMediaType *, _QWORD))a2->lpVtbl->CopyAllItems)(
                                      a2,
                                      v6[46]);
        if ( MinSampleSizeForMediaType >= 0 )
        {
          MinSampleSizeForMediaType = CAVIStreamSink::GetMinSampleSizeForMediaType(a2, (unsigned int *)this + 117);
          if ( MinSampleSizeForMediaType < 0 )
          {
            v24 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
              CallStackTracing::s_wpInstance = v25;
              if ( v25
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
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
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != MinSampleSizeForMediaType )
                CallStackContext::TraceFailure(
                  ThreadRelativeContext,
                  "CAVIStreamSink::SetMediaType",
                  581,
                  MinSampleSizeForMediaType);
            }
            if ( g_wppLevels )
            {
              v10 = 117;
              goto LABEL_56;
            }
          }
        }
        else
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
            if ( *((_DWORD *)v22 + 499) != MinSampleSizeForMediaType )
              CallStackContext::TraceFailure(v22, "CAVIStreamSink::SetMediaType", 580, MinSampleSizeForMediaType);
          }
          if ( g_wppLevels )
          {
            v10 = 116;
            goto LABEL_56;
          }
        }
      }
      else
      {
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
          if ( *((_DWORD *)v18 + 499) != MinSampleSizeForMediaType )
            CallStackContext::TraceFailure(v18, "CAVIStreamSink::SetMediaType", 579, MinSampleSizeForMediaType);
        }
        if ( g_wppLevels )
        {
          v10 = 115;
          goto LABEL_56;
        }
      }
    }
    else
    {
      v12 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
        CallStackTracing::s_wpInstance = v13;
        if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
        {
          v12 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
        if ( *((_DWORD *)v14 + 499) != MinSampleSizeForMediaType )
          CallStackContext::TraceFailure(v14, "CAVIStreamSink::SetMediaType", 578, MinSampleSizeForMediaType);
      }
      if ( g_wppLevels )
      {
        v10 = 114;
        goto LABEL_56;
      }
    }
  }
  else
  {
    v7 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v9 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)v9 + 499) != MinSampleSizeForMediaType )
        CallStackContext::TraceFailure(v9, "CAVIStreamSink::SetMediaType", 577, MinSampleSizeForMediaType);
    }
    if ( g_wppLevels )
    {
      v10 = 113;
LABEL_56:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids,
        (char *)this - 32,
        MinSampleSizeForMediaType);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v28);
  return (unsigned int)MinSampleSizeForMediaType;
}

```

## disassembly

```asm
0x180134370  mov     [rsp+arg_0], rbx
0x180134375  mov     [rsp+arg_10], rbp
0x18013437a  push    rsi
0x18013437b  push    rdi
0x18013437c  push    r15
0x18013437e  sub     rsp, 30h
0x180134382  mov     rax, rdx
0x180134385  lea     r15, aCavistreamsink_15; "CAVIStreamSink::SetMediaType"
0x18013438c  neg     rax
0x18013438f  mov     rdi, rdx
0x180134392  mov     rbp, rcx
0x180134395  mov     r8d, 240h; int
0x18013439b  sbb     ebx, ebx
0x18013439d  lea     rcx, [rsp+48h+arg_8]; this
0x1801343a2  not     ebx
0x1801343a4  mov     rdx, r15; char *
0x1801343a7  and     ebx, 80004003h
0x1801343ad  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801343b2  lea     rsi, [rbp-20h]
0x1801343b6  test    rdi, rdi
0x1801343b9  jnz     loc_180134450
0x1801343bf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801343c6  test    rcx, rcx
0x1801343c9  jnz     short loc_180134412
0x1801343cb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801343d2  nop     dword ptr [rax+rax+00h]
0x1801343d7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801343de  mov     rcx, rax
0x1801343e1  test    rax, rax
0x1801343e4  jz      short loc_180134404
0x1801343e6  mov     rax, [rax]
0x1801343e9  mov     edx, 7F0h
0x1801343ee  mov     rax, [rax+8]
0x1801343f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801343f7  test    eax, eax
0x1801343f9  jz      short loc_180134404
0x1801343fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180134402  jmp     short loc_180134412
0x180134404  lea     rcx, qword_1801B97E0; this
0x18013440b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180134412  cmp     byte ptr [rcx+8], 0
0x180134416  jz      short loc_180134439
0x180134418  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013441d  cmp     [rax+7CCh], ebx
0x180134423  jz      short loc_180134439
0x180134425  mov     r9d, ebx; int
0x180134428  mov     r8d, 241h; int
0x18013442e  mov     rdx, r15; char *
0x180134431  mov     rcx, rax; this
0x180134434  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180134439  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180134440  jb      loc_180134729
0x180134446  mov     edx, 71h ; 'q'
0x18013444b  jmp     loc_18013470B
0x180134450  mov     rax, [rsi]
0x180134453  mov     rdx, rdi
0x180134456  mov     rcx, rsi
0x180134459  mov     rax, [rax+20h]
0x18013445d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134462  mov     ebx, eax
0x180134464  test    eax, eax
0x180134466  jns     loc_1801344FD
0x18013446c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180134473  test    rcx, rcx
0x180134476  jnz     short loc_1801344BF
0x180134478  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013447f  nop     dword ptr [rax+rax+00h]
0x180134484  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013448b  mov     rcx, rax
0x18013448e  test    rax, rax
0x180134491  jz      short loc_1801344B1
0x180134493  mov     rax, [rax]
0x180134496  mov     edx, 7F0h
0x18013449b  mov     rax, [rax+8]
0x18013449f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801344a4  test    eax, eax
0x1801344a6  jz      short loc_1801344B1
0x1801344a8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801344af  jmp     short loc_1801344BF
0x1801344b1  lea     rcx, qword_1801B97E0; this
0x1801344b8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801344bf  cmp     byte ptr [rcx+8], 0
0x1801344c3  jz      short loc_1801344E6
0x1801344c5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801344ca  cmp     [rax+7CCh], ebx
0x1801344d0  jz      short loc_1801344E6
0x1801344d2  mov     r9d, ebx; int
0x1801344d5  mov     r8d, 242h; int
0x1801344db  mov     rdx, r15; char *
0x1801344de  mov     rcx, rax; this
0x1801344e1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801344e6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801344ed  jb      loc_180134729
0x1801344f3  mov     edx, 72h ; 'r'
0x1801344f8  jmp     loc_18013470B
0x1801344fd  lea     rbx, [rbp+150h]
0x180134504  mov     rcx, rbx
0x180134507  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18013450c  mov     rcx, rbx; ppMFType
0x18013450f  call    cs:__imp_MFCreateMediaType
0x180134516  nop     dword ptr [rax+rax+00h]
0x18013451b  mov     ebx, eax
0x18013451d  test    eax, eax
0x18013451f  jns     loc_1801345B6
0x180134525  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013452c  test    rcx, rcx
0x18013452f  jnz     short loc_180134578
0x180134531  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180134538  nop     dword ptr [rax+rax+00h]
0x18013453d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180134544  mov     rcx, rax
0x180134547  test    rax, rax
0x18013454a  jz      short loc_18013456A
0x18013454c  mov     rax, [rax]
0x18013454f  mov     edx, 7F0h
0x180134554  mov     rax, [rax+8]
0x180134558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013455d  test    eax, eax
0x18013455f  jz      short loc_18013456A
0x180134561  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180134568  jmp     short loc_180134578
0x18013456a  lea     rcx, qword_1801B97E0; this
0x180134571  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180134578  cmp     byte ptr [rcx+8], 0
0x18013457c  jz      short loc_18013459F
0x18013457e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180134583  cmp     [rax+7CCh], ebx
0x180134589  jz      short loc_18013459F
0x18013458b  mov     r9d, ebx; int
0x18013458e  mov     r8d, 243h; int
0x180134594  mov     rdx, r15; char *
0x180134597  mov     rcx, rax; this
0x18013459a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013459f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801345a6  jb      loc_180134729
0x1801345ac  mov     edx, 73h ; 's'
0x1801345b1  jmp     loc_18013470B
0x1801345b6  mov     rax, [rdi]
0x1801345b9  mov     rcx, rdi
0x1801345bc  mov     rdx, [rsi+170h]
0x1801345c3  mov     rax, [rax+100h]
0x1801345ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801345cf  mov     ebx, eax
0x1801345d1  test    eax, eax
0x1801345d3  jns     loc_18013466A
0x1801345d9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801345e0  test    rcx, rcx
0x1801345e3  jnz     short loc_18013462C
0x1801345e5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801345ec  nop     dword ptr [rax+rax+00h]
0x1801345f1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801345f8  mov     rcx, rax
0x1801345fb  test    rax, rax
0x1801345fe  jz      short loc_18013461E
0x180134600  mov     rax, [rax]
0x180134603  mov     edx, 7F0h
0x180134608  mov     rax, [rax+8]
0x18013460c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134611  test    eax, eax
0x180134613  jz      short loc_18013461E
0x180134615  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013461c  jmp     short loc_18013462C
0x18013461e  lea     rcx, qword_1801B97E0; this
0x180134625  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013462c  cmp     byte ptr [rcx+8], 0
0x180134630  jz      short loc_180134653
0x180134632  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180134637  cmp     [rax+7CCh], ebx
0x18013463d  jz      short loc_180134653
0x18013463f  mov     r9d, ebx; int
0x180134642  mov     r8d, 244h; int
0x180134648  mov     rdx, r15; char *
0x18013464b  mov     rcx, rax; this
0x18013464e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180134653  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18013465a  jb      loc_180134729
0x180134660  mov     edx, 74h ; 't'
0x180134665  jmp     loc_18013470B
0x18013466a  lea     rdx, [rbp+1D4h]; unsigned int *
0x180134671  mov     rcx, rdi; struct IMFMediaType *
0x180134674  call    ?GetMinSampleSizeForMediaType@CAVIStreamSink@@CAJPEAUIMFMediaType@@PEAK@Z; CAVIStreamSink::GetMinSampleSizeForMediaType(IMFMediaType *,ulong *)
0x180134679  mov     ebx, eax
0x18013467b  test    eax, eax
0x18013467d  jns     loc_180134729
0x180134683  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013468a  test    rcx, rcx
0x18013468d  jnz     short loc_1801346D6
0x18013468f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180134696  nop     dword ptr [rax+rax+00h]
0x18013469b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801346a2  mov     rcx, rax
0x1801346a5  test    rax, rax
0x1801346a8  jz      short loc_1801346C8
0x1801346aa  mov     rax, [rax]
0x1801346ad  mov     edx, 7F0h
0x1801346b2  mov     rax, [rax+8]
0x1801346b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801346bb  test    eax, eax
0x1801346bd  jz      short loc_1801346C8
0x1801346bf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801346c6  jmp     short loc_1801346D6
0x1801346c8  lea     rcx, qword_1801B97E0; this
0x1801346cf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801346d6  cmp     byte ptr [rcx+8], 0
0x1801346da  jz      short loc_1801346FD
0x1801346dc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801346e1  cmp     [rax+7CCh], ebx
0x1801346e7  jz      short loc_1801346FD
0x1801346e9  mov     r9d, ebx; int
0x1801346ec  mov     r8d, 245h; int
0x1801346f2  mov     rdx, r15; char *
0x1801346f5  mov     rcx, rax; this
0x1801346f8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801346fd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180134704  jb      short loc_180134729
0x180134706  mov     edx, 75h ; 'u'
0x18013470b  mov     rcx, cs:WPP_GLOBAL_Control
0x180134712  lea     r8, WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids
0x180134719  mov     r9, rsi
0x18013471c  mov     [rsp+48h+var_28], ebx
0x180134720  mov     rcx, [rcx+10h]
0x180134724  call    WPP_SF_qD
0x180134729  lea     rcx, [rsp+48h+arg_8]; this
0x18013472e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180134733  mov     rbp, [rsp+48h+arg_10]
0x180134738  mov     eax, ebx
0x18013473a  mov     rbx, [rsp+48h+arg_0]
0x18013473f  add     rsp, 30h
0x180134743  pop     r15
0x180134745  pop     rdi
0x180134746  pop     rsi
0x180134747  retn
```
