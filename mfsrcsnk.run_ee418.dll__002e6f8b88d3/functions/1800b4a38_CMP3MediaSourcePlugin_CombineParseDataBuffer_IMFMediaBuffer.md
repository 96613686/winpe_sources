# CMP3MediaSourcePlugin::CombineParseDataBuffer(IMFMediaBuffer *)

- ea: `0x1800b4a38`
- end: `0x1800b4f0e`
- name: `?CombineParseDataBuffer@CMP3MediaSourcePlugin@@AEAAJPEAUIMFMediaBuffer@@@Z`
- size: `1238`
- prototype: `__int64 __fastcall(CMP3MediaSourcePlugin *__hidden this, struct IMFMediaBuffer *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800dd8e0`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x18004e074`
- `0x180055890`
- `0x180060768`
- `0x180073b14`
- `0x1800b4a38`
- `0x1801099f0`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b4ac6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b4b93`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b4c40`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b4d05`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b4dac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b4e53`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b4ac6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b4b93`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b4c40`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b4d05`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b4dac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b4e53`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800b4c24`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800b4c24`

## string_xrefs

- `0x1800b4a5c`: `CMP3MediaSourcePlugin::CombineParseDataBuffer`

## pseudocode

```c
__int64 __fastcall CMP3MediaSourcePlugin::CombineParseDataBuffer(
        CMP3MediaSourcePlugin *this,
        struct IMFMediaBuffer *a2)
{
  __int64 v4; // rcx
  HRESULT v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  wchar_t *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
  struct IMFMediaBufferVtbl *lpVtbl; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  wchar_t *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  _BYTE v46[8]; // [rsp+30h] [rbp-20h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+38h] [rbp-18h] BYREF
  int v48; // [rsp+40h] [rbp-10h] BYREF
  int v49; // [rsp+44h] [rbp-Ch] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v46,
    "CMP3MediaSourcePlugin::CombineParseDataBuffer",
    1659);
  v4 = *((_QWORD *)this + 165);
  if ( !v4 )
  {
    v5 = 0;
    ComSmartPtr<IMFMediaBuffer>::operator=((char *)this + 1320, a2);
    goto LABEL_73;
  }
  v48 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v4 + 40LL))(v4, &v48);
  if ( v5 < 0 )
  {
    v9 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v7, v8);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMP3MediaSourcePlugin::CombineParseDataBuffer", 1668, v5);
    }
    if ( g_wppLevels )
    {
      v12 = 189;
LABEL_14:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_d883d89413f235918ed5b1c680996b82_Traceguids, this, v5);
      goto LABEL_73;
    }
    goto LABEL_73;
  }
  lpVtbl = a2->lpVtbl;
  v49 = 0;
  v5 = ((__int64 (__fastcall *)(struct IMFMediaBuffer *, int *))lpVtbl->GetCurrentLength)(a2, &v49);
  if ( v5 >= 0 )
  {
    ppBuffer = 0;
    v5 = MFCreateMemoryBuffer(v49 + v48, &ppBuffer);
    if ( v5 >= 0 )
    {
      v5 = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->SetCurrentLength)(ppBuffer, 0);
      if ( v5 >= 0 )
      {
        v5 = CMP3MediaSourcePlugin::AppendToBuffer(this, *((struct IMFMediaBuffer **)this + 165), 0, ppBuffer);
        if ( v5 >= 0 )
        {
          v5 = CMP3MediaSourcePlugin::AppendToBuffer(this, a2, 0, ppBuffer);
          if ( v5 >= 0 )
          {
            ComSmartPtr<IMFMediaBuffer>::operator=((char *)this + 1320, &ppBuffer);
            goto LABEL_72;
          }
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
            if ( *((_DWORD *)v44 + 499) != v5 )
              CallStackContext::TraceFailure(v44, "CMP3MediaSourcePlugin::CombineParseDataBuffer", 1676, v5);
          }
          if ( !g_wppLevels )
            goto LABEL_72;
          v26 = 194;
        }
        else
        {
          v36 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34, v35);
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
          if ( *((_BYTE *)v36 + 8) )
          {
            v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
            if ( *((_DWORD *)v38 + 499) != v5 )
              CallStackContext::TraceFailure(v38, "CMP3MediaSourcePlugin::CombineParseDataBuffer", 1675, v5);
          }
          if ( !g_wppLevels )
            goto LABEL_72;
          v26 = 193;
        }
      }
      else
      {
        v30 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, v29);
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
          if ( *((_DWORD *)v32 + 499) != v5 )
            CallStackContext::TraceFailure(v32, "CMP3MediaSourcePlugin::CombineParseDataBuffer", 1674, v5);
        }
        if ( !g_wppLevels )
          goto LABEL_72;
        v26 = 192;
      }
    }
    else
    {
      v23 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v21, v22);
        CallStackTracing::s_wpInstance = v24;
        if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
        {
          v23 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v23 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v23 + 8) )
      {
        v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
        if ( *((_DWORD *)v25 + 499) != v5 )
          CallStackContext::TraceFailure(v25, "CMP3MediaSourcePlugin::CombineParseDataBuffer", 1673, v5);
      }
      if ( !g_wppLevels )
        goto LABEL_72;
      v26 = 191;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v26, &WPP_d883d89413f235918ed5b1c680996b82_Traceguids, this, v5);
LABEL_72:
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppBuffer);
    goto LABEL_73;
  }
  v17 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v15, v16);
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
    v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
    if ( *((_DWORD *)v19 + 499) != v5 )
      CallStackContext::TraceFailure(v19, "CMP3MediaSourcePlugin::CombineParseDataBuffer", 1670, v5);
  }
  if ( g_wppLevels )
  {
    v12 = 190;
    goto LABEL_14;
  }
LABEL_73:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v46);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800b4a38  mov     [rsp-28h+arg_10], rbx
0x1800b4a3d  push    rbp
0x1800b4a3e  push    rsi
0x1800b4a3f  push    rdi
0x1800b4a40  push    r12
0x1800b4a42  push    r14
0x1800b4a44  mov     rbp, rsp
0x1800b4a47  sub     rsp, 50h
0x1800b4a4b  mov     rax, cs:__security_cookie
0x1800b4a52  xor     rax, rsp
0x1800b4a55  mov     [rbp+var_8], rax
0x1800b4a59  mov     rsi, rdx
0x1800b4a5c  lea     r12, aCmp3mediasourc_56; "CMP3MediaSourcePlugin::CombineParseData"...
0x1800b4a63  mov     r14, rcx
0x1800b4a66  mov     rdx, r12; char *
0x1800b4a69  mov     r8d, 67Bh; int
0x1800b4a6f  lea     rcx, [rbp+var_20]; this
0x1800b4a73  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b4a78  lea     rdi, [r14+528h]
0x1800b4a7f  mov     rcx, [rdi]
0x1800b4a82  test    rcx, rcx
0x1800b4a85  jnz     short loc_1800B4A99
0x1800b4a87  xor     ebx, ebx
0x1800b4a89  mov     rdx, rsi
0x1800b4a8c  mov     rcx, rdi
0x1800b4a8f  call    ??4?$ComSmartPtr@UIMFMediaBuffer@@@@QEAAPEAUIMFMediaBuffer@@PEAU1@@Z; ComSmartPtr<IMFMediaBuffer>::operator=(IMFMediaBuffer *)
0x1800b4a94  jmp     loc_1800B4EE3
0x1800b4a99  mov     [rbp+var_10], 0
0x1800b4aa0  lea     rdx, [rbp+var_10]
0x1800b4aa4  mov     rax, [rcx]
0x1800b4aa7  mov     rax, [rax+28h]
0x1800b4aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4ab0  mov     ebx, eax
0x1800b4ab2  test    eax, eax
0x1800b4ab4  jns     loc_1800B4B63
0x1800b4aba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4ac1  test    rcx, rcx
0x1800b4ac4  jnz     short loc_1800B4B07
0x1800b4ac6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b4acc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4ad3  mov     rcx, rax
0x1800b4ad6  test    rax, rax
0x1800b4ad9  jz      short loc_1800B4AF9
0x1800b4adb  mov     rax, [rax]
0x1800b4ade  mov     edx, 7F0h
0x1800b4ae3  mov     rax, [rax+8]
0x1800b4ae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4aec  test    eax, eax
0x1800b4aee  jz      short loc_1800B4AF9
0x1800b4af0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4af7  jmp     short loc_1800B4B07
0x1800b4af9  lea     rcx, qword_1801B07E0; this
0x1800b4b00  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4b07  cmp     byte ptr [rcx+8], 0
0x1800b4b0b  jz      short loc_1800B4B2E
0x1800b4b0d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b4b12  cmp     [rax+7CCh], ebx
0x1800b4b18  jz      short loc_1800B4B2E
0x1800b4b1a  mov     r9d, ebx; int
0x1800b4b1d  mov     r8d, 684h; int
0x1800b4b23  mov     rdx, r12; char *
0x1800b4b26  mov     rcx, rax; this
0x1800b4b29  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b4b2e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b4b35  jb      loc_1800B4EE3
0x1800b4b3b  mov     edx, 0BDh
0x1800b4b40  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4b47  lea     r8, WPP_d883d89413f235918ed5b1c680996b82_Traceguids
0x1800b4b4e  mov     r9, r14
0x1800b4b51  mov     [rsp+50h+var_30], ebx
0x1800b4b55  mov     rcx, [rcx+10h]
0x1800b4b59  call    WPP_SF_qD
0x1800b4b5e  jmp     loc_1800B4EE3
0x1800b4b63  mov     rax, [rsi]
0x1800b4b66  lea     rdx, [rbp+var_C]
0x1800b4b6a  mov     rcx, rsi
0x1800b4b6d  mov     [rbp+var_C], 0
0x1800b4b74  mov     rax, [rax+28h]
0x1800b4b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4b7d  mov     ebx, eax
0x1800b4b7f  test    eax, eax
0x1800b4b81  jns     loc_1800B4C12
0x1800b4b87  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4b8e  test    rcx, rcx
0x1800b4b91  jnz     short loc_1800B4BD4
0x1800b4b93  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b4b99  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4ba0  mov     rcx, rax
0x1800b4ba3  test    rax, rax
0x1800b4ba6  jz      short loc_1800B4BC6
0x1800b4ba8  mov     rax, [rax]
0x1800b4bab  mov     edx, 7F0h
0x1800b4bb0  mov     rax, [rax+8]
0x1800b4bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4bb9  test    eax, eax
0x1800b4bbb  jz      short loc_1800B4BC6
0x1800b4bbd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4bc4  jmp     short loc_1800B4BD4
0x1800b4bc6  lea     rcx, qword_1801B07E0; this
0x1800b4bcd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4bd4  cmp     byte ptr [rcx+8], 0
0x1800b4bd8  jz      short loc_1800B4BFB
0x1800b4bda  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b4bdf  cmp     [rax+7CCh], ebx
0x1800b4be5  jz      short loc_1800B4BFB
0x1800b4be7  mov     r9d, ebx; int
0x1800b4bea  mov     r8d, 686h; int
0x1800b4bf0  mov     rdx, r12; char *
0x1800b4bf3  mov     rcx, rax; this
0x1800b4bf6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b4bfb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b4c02  jb      loc_1800B4EE3
0x1800b4c08  mov     edx, 0BEh
0x1800b4c0d  jmp     loc_1800B4B40
0x1800b4c12  mov     ecx, [rbp+var_10]
0x1800b4c15  lea     rdx, [rbp+ppBuffer]; ppBuffer
0x1800b4c19  add     ecx, [rbp+var_C]; cbMaxLength
0x1800b4c1c  mov     [rbp+ppBuffer], 0
0x1800b4c24  call    cs:__imp_MFCreateMemoryBuffer
0x1800b4c2a  mov     ebx, eax
0x1800b4c2c  test    eax, eax
0x1800b4c2e  jns     loc_1800B4CDD
0x1800b4c34  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4c3b  test    rcx, rcx
0x1800b4c3e  jnz     short loc_1800B4C81
0x1800b4c40  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b4c46  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4c4d  mov     rcx, rax
0x1800b4c50  test    rax, rax
0x1800b4c53  jz      short loc_1800B4C73
0x1800b4c55  mov     rax, [rax]
0x1800b4c58  mov     edx, 7F0h
0x1800b4c5d  mov     rax, [rax+8]
0x1800b4c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4c66  test    eax, eax
0x1800b4c68  jz      short loc_1800B4C73
0x1800b4c6a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4c71  jmp     short loc_1800B4C81
0x1800b4c73  lea     rcx, qword_1801B07E0; this
0x1800b4c7a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4c81  cmp     byte ptr [rcx+8], 0
0x1800b4c85  jz      short loc_1800B4CA8
0x1800b4c87  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b4c8c  cmp     [rax+7CCh], ebx
0x1800b4c92  jz      short loc_1800B4CA8
0x1800b4c94  mov     r9d, ebx; int
0x1800b4c97  mov     r8d, 689h; int
0x1800b4c9d  mov     rdx, r12; char *
0x1800b4ca0  mov     rcx, rax; this
0x1800b4ca3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b4ca8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b4caf  jb      loc_1800B4EDA
0x1800b4cb5  mov     edx, 0BFh
0x1800b4cba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4cc1  lea     r8, WPP_d883d89413f235918ed5b1c680996b82_Traceguids
0x1800b4cc8  mov     r9, r14
0x1800b4ccb  mov     [rsp+50h+var_30], ebx
0x1800b4ccf  mov     rcx, [rcx+10h]
0x1800b4cd3  call    WPP_SF_qD
0x1800b4cd8  jmp     loc_1800B4EDA
0x1800b4cdd  mov     rcx, [rbp+ppBuffer]
0x1800b4ce1  xor     edx, edx
0x1800b4ce3  mov     rax, [rcx]
0x1800b4ce6  mov     rax, [rax+30h]
0x1800b4cea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4cef  mov     ebx, eax
0x1800b4cf1  test    eax, eax
0x1800b4cf3  jns     loc_1800B4D84
0x1800b4cf9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4d00  test    rcx, rcx
0x1800b4d03  jnz     short loc_1800B4D46
0x1800b4d05  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b4d0b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4d12  mov     rcx, rax
0x1800b4d15  test    rax, rax
0x1800b4d18  jz      short loc_1800B4D38
0x1800b4d1a  mov     rax, [rax]
0x1800b4d1d  mov     edx, 7F0h
0x1800b4d22  mov     rax, [rax+8]
0x1800b4d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4d2b  test    eax, eax
0x1800b4d2d  jz      short loc_1800B4D38
0x1800b4d2f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4d36  jmp     short loc_1800B4D46
0x1800b4d38  lea     rcx, qword_1801B07E0; this
0x1800b4d3f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4d46  cmp     byte ptr [rcx+8], 0
0x1800b4d4a  jz      short loc_1800B4D6D
0x1800b4d4c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b4d51  cmp     [rax+7CCh], ebx
0x1800b4d57  jz      short loc_1800B4D6D
0x1800b4d59  mov     r9d, ebx; int
0x1800b4d5c  mov     r8d, 68Ah; int
0x1800b4d62  mov     rdx, r12; char *
0x1800b4d65  mov     rcx, rax; this
0x1800b4d68  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b4d6d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b4d74  jb      loc_1800B4EDA
0x1800b4d7a  mov     edx, 0C0h
0x1800b4d7f  jmp     loc_1800B4CBA
0x1800b4d84  mov     r9, [rbp+ppBuffer]; struct IMFMediaBuffer *
0x1800b4d88  xor     r8d, r8d; unsigned int
0x1800b4d8b  mov     rdx, [rdi]; struct IMFMediaBuffer *
0x1800b4d8e  mov     rcx, r14; this
0x1800b4d91  call    ?AppendToBuffer@CMP3MediaSourcePlugin@@AEAAJPEAUIMFMediaBuffer@@K0@Z; CMP3MediaSourcePlugin::AppendToBuffer(IMFMediaBuffer *,ulong,IMFMediaBuffer *)
0x1800b4d96  mov     ebx, eax
0x1800b4d98  test    eax, eax
0x1800b4d9a  jns     loc_1800B4E2B
0x1800b4da0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4da7  test    rcx, rcx
0x1800b4daa  jnz     short loc_1800B4DED
0x1800b4dac  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b4db2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4db9  mov     rcx, rax
0x1800b4dbc  test    rax, rax
0x1800b4dbf  jz      short loc_1800B4DDF
0x1800b4dc1  mov     rax, [rax]
0x1800b4dc4  mov     edx, 7F0h
0x1800b4dc9  mov     rax, [rax+8]
0x1800b4dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4dd2  test    eax, eax
0x1800b4dd4  jz      short loc_1800B4DDF
0x1800b4dd6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4ddd  jmp     short loc_1800B4DED
0x1800b4ddf  lea     rcx, qword_1801B07E0; this
0x1800b4de6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4ded  cmp     byte ptr [rcx+8], 0
0x1800b4df1  jz      short loc_1800B4E14
0x1800b4df3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b4df8  cmp     [rax+7CCh], ebx
0x1800b4dfe  jz      short loc_1800B4E14
0x1800b4e00  mov     r9d, ebx; int
0x1800b4e03  mov     r8d, 68Bh; int
0x1800b4e09  mov     rdx, r12; char *
0x1800b4e0c  mov     rcx, rax; this
0x1800b4e0f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b4e14  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b4e1b  jb      loc_1800B4EDA
0x1800b4e21  mov     edx, 0C1h
0x1800b4e26  jmp     loc_1800B4CBA
0x1800b4e2b  mov     r9, [rbp+ppBuffer]; struct IMFMediaBuffer *
0x1800b4e2f  xor     r8d, r8d; unsigned int
0x1800b4e32  mov     rdx, rsi; struct IMFMediaBuffer *
0x1800b4e35  mov     rcx, r14; this
0x1800b4e38  call    ?AppendToBuffer@CMP3MediaSourcePlugin@@AEAAJPEAUIMFMediaBuffer@@K0@Z; CMP3MediaSourcePlugin::AppendToBuffer(IMFMediaBuffer *,ulong,IMFMediaBuffer *)
0x1800b4e3d  mov     ebx, eax
0x1800b4e3f  test    eax, eax
0x1800b4e41  jns     loc_1800B4ECE
0x1800b4e47  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4e4e  test    rcx, rcx
0x1800b4e51  jnz     short loc_1800B4E94
0x1800b4e53  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b4e59  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4e60  mov     rcx, rax
0x1800b4e63  test    rax, rax
0x1800b4e66  jz      short loc_1800B4E86
0x1800b4e68  mov     rax, [rax]
0x1800b4e6b  mov     edx, 7F0h
0x1800b4e70  mov     rax, [rax+8]
0x1800b4e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4e79  test    eax, eax
0x1800b4e7b  jz      short loc_1800B4E86
0x1800b4e7d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4e84  jmp     short loc_1800B4E94
0x1800b4e86  lea     rcx, qword_1801B07E0; this
0x1800b4e8d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4e94  cmp     byte ptr [rcx+8], 0
0x1800b4e98  jz      short loc_1800B4EBB
0x1800b4e9a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b4e9f  cmp     [rax+7CCh], ebx
0x1800b4ea5  jz      short loc_1800B4EBB
0x1800b4ea7  mov     r9d, ebx; int
0x1800b4eaa  mov     r8d, 68Ch; int
0x1800b4eb0  mov     rdx, r12; char *
0x1800b4eb3  mov     rcx, rax; this
0x1800b4eb6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b4ebb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b4ec2  jb      short loc_1800B4EDA
0x1800b4ec4  mov     edx, 0C2h
0x1800b4ec9  jmp     loc_1800B4CBA
0x1800b4ece  lea     rdx, [rbp+ppBuffer]
0x1800b4ed2  mov     rcx, rdi
0x1800b4ed5  call    ??4?$ComSmartPtr@UIMFMediaBuffer@@@@QEAAPEAUIMFMediaBuffer@@AEBV0@@Z; ComSmartPtr<IMFMediaBuffer>::operator=(ComSmartPtr<IMFMediaBuffer> const &)
0x1800b4eda  lea     rcx, [rbp+ppBuffer]; void *
0x1800b4ede  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800b4ee3  lea     rcx, [rbp+var_20]; this
0x1800b4ee7  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800b4eec  mov     eax, ebx
0x1800b4eee  mov     rcx, [rbp+var_8]
0x1800b4ef2  xor     rcx, rsp; StackCookie
0x1800b4ef5  call    __security_check_cookie
0x1800b4efa  mov     rbx, [rsp+50h+arg_10]
0x1800b4f02  add     rsp, 50h
0x1800b4f06  pop     r14
0x1800b4f08  pop     r12
0x1800b4f0a  pop     rdi
0x1800b4f0b  pop     rsi
0x1800b4f0c  pop     rbp
0x1800b4f0d  retn
```
