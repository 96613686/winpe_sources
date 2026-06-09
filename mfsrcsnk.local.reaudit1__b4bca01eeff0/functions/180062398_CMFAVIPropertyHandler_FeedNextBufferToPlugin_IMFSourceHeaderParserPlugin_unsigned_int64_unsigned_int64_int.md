# CMFAVIPropertyHandler::FeedNextBufferToPlugin(IMFSourceHeaderParserPlugin *,unsigned __int64,unsigned __int64 *,int *)

- ea: `0x180062398`
- end: `0x1800628ed`
- name: `?FeedNextBufferToPlugin@CMFAVIPropertyHandler@@AEAAJPEAUIMFSourceHeaderParserPlugin@@_KPEA_KPEAH@Z`
- size: `1365`
- prototype: `__int64 __fastcall(CMFAVIPropertyHandler *__hidden this, struct IMFSourceHeaderParserPlugin *, unsigned __int64, unsigned __int64 *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800f2ccc`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180062398`
- `0x180077708`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062489`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062537`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800625bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006264b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800626f1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800627c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006284b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062489`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062537`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800625bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006264b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800626f1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800627c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006284b`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800623f9`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800623f9`

## string_xrefs

- `0x1800623b5`: `CMFAVIPropertyHandler::FeedNextBufferToPlugin`
- `0x180062447`: `CMFAVIPropertyHandler::FeedNextBufferToPlugin`

## pseudocode

```c
__int64 __fastcall CMFAVIPropertyHandler::FeedNextBufferToPlugin(
        CMFAVIPropertyHandler *this,
        struct IMFSourceHeaderParserPlugin *a2,
        __int64 a3,
        unsigned __int64 *a4,
        int *a5)
{
  unsigned __int64 v9; // rsi
  HRESULT v10; // ebx
  CallStackTracing *v11; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  int v13; // r8d
  __int64 v14; // rdx
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  __int64 v17; // rdx
  wchar_t *v18; // rcx
  CallStackTracing *v19; // rax
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  __int64 v22; // rdx
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  __int64 v25; // rdx
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  int v28; // ecx
  unsigned __int64 v29; // rdx
  __int64 v30; // rdx
  wchar_t *v31; // rcx
  CallStackTracing *v32; // rax
  int v33; // ecx
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  unsigned int v37; // [rsp+40h] [rbp-38h] BYREF
  int v38; // [rsp+44h] [rbp-34h] BYREF
  unsigned int v39; // [rsp+48h] [rbp-30h] BYREF
  int v40; // [rsp+4Ch] [rbp-2Ch] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+50h] [rbp-28h] BYREF
  __int64 v42; // [rsp+58h] [rbp-20h] BYREF
  _QWORD v43[3]; // [rsp+60h] [rbp-18h] BYREF
  char v44; // [rsp+D8h] [rbp+60h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v44,
    "CMFAVIPropertyHandler::FeedNextBufferToPlugin",
    248);
  v9 = *a4;
  ppBuffer = 0;
  v38 = 0;
  v42 = 0;
  v40 = 0;
  v39 = 0;
  v37 = 0;
  v43[0] = 0;
  v10 = MFCreateMemoryBuffer(0x4000u, &ppBuffer);
  if ( v10 >= 0 )
  {
    v10 = ((__int64 (__fastcall *)(IMFMediaBuffer *, __int64 *, unsigned int *, int *))ppBuffer->lpVtbl->Lock)(
            ppBuffer,
            &v42,
            &v39,
            &v40);
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, unsigned int *))(**((_QWORD **)this + 111) + 24LL))(
              *((_QWORD *)this + 111),
              v42,
              v39,
              &v37);
      ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
      if ( v10 >= 0 )
      {
        if ( v37 )
        {
          v10 = ((__int64 (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->SetCurrentLength)(ppBuffer);
          if ( v10 >= 0 )
          {
            v10 = (*(__int64 (__fastcall **)(struct IMFSourceHeaderParserPlugin *, __int64, IMFMediaBuffer *, unsigned __int64, unsigned __int64 *, int *))(*(_QWORD *)a2 + 24LL))(
                    a2,
                    a3,
                    ppBuffer,
                    v9,
                    a4,
                    &v38);
            if ( v10 >= 0 )
            {
              v28 = v38;
              if ( !v38 )
                goto LABEL_78;
              v29 = v9 + v37;
              if ( v29 < v9 )
              {
                v34 = (wchar_t *)CallStackTracing::s_wpInstance;
                v10 = -2147024362;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
                  CallStackTracing::s_wpInstance = v35;
                  if ( v35
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
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
                  ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
                  if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024362 )
                  {
                    v13 = 287;
                    goto LABEL_7;
                  }
                }
                goto LABEL_80;
              }
              v10 = 0;
              if ( *a4 == -1 )
              {
                *a4 = v29;
              }
              else if ( *a4 != v29 )
              {
                v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD *))(**((_QWORD **)this + 111) + 40LL))(
                        *((_QWORD *)this + 111),
                        *a4,
                        0,
                        v43);
                if ( v10 < 0 )
                {
                  v31 = (wchar_t *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30);
                    CallStackTracing::s_wpInstance = v32;
                    if ( v32
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
                    {
                      v31 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v31 = &qword_1801B97E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                    }
                  }
                  if ( *((_BYTE *)v31 + 8) )
                  {
                    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
                    if ( *((_DWORD *)ThreadRelativeContext + 499) != v10 )
                    {
                      v13 = 300;
                      goto LABEL_7;
                    }
                  }
                  goto LABEL_80;
                }
                v28 = v38;
              }
              if ( v28 )
                v33 = 0;
              else
LABEL_78:
                v33 = 1;
              *a5 = v33;
              goto LABEL_80;
            }
            v26 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
              CallStackTracing::s_wpInstance = v27;
              if ( v27
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
              {
                v26 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v26 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)v26 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v10 )
              {
                v13 = 283;
                goto LABEL_7;
              }
            }
          }
          else
          {
            v23 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
              CallStackTracing::s_wpInstance = v24;
              if ( v24
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
              {
                v23 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v23 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)v23 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v10 )
              {
                v13 = 281;
                goto LABEL_7;
              }
            }
          }
        }
        else
        {
          v20 = (wchar_t *)CallStackTracing::s_wpInstance;
          v10 = -2147418113;
          if ( !CallStackTracing::s_wpInstance )
          {
            v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37);
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
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
            {
              v13 = 278;
              goto LABEL_7;
            }
          }
        }
      }
      else
      {
        v18 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
          CallStackTracing::s_wpInstance = v19;
          if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
          {
            v18 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v18 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v18 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v10 )
          {
            v13 = 270;
            goto LABEL_7;
          }
        }
      }
    }
    else
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
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v10 )
        {
          v13 = 264;
          goto LABEL_7;
        }
      }
    }
  }
  else
  {
    v11 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v11 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v11);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v10 )
      {
        v13 = 262;
LABEL_7:
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFAVIPropertyHandler::FeedNextBufferToPlugin", v13, v10);
      }
    }
  }
LABEL_80:
  if ( ppBuffer )
    ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Release)(ppBuffer);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v44);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180062398  push    rbp
0x18006239a  push    rbx
0x18006239b  push    rsi
0x18006239c  push    rdi
0x18006239d  push    r12
0x18006239f  push    r13
0x1800623a1  push    r14
0x1800623a3  push    r15
0x1800623a5  mov     rbp, rsp
0x1800623a8  sub     rsp, 78h
0x1800623ac  mov     r12, r8
0x1800623af  mov     r14, rdx
0x1800623b2  mov     r15, rcx
0x1800623b5  lea     rdx, aCmfaviproperty_1; "CMFAVIPropertyHandler::FeedNextBufferTo"...
0x1800623bc  mov     r8d, 0F8h; int
0x1800623c2  lea     rcx, [rbp+arg_18]; this
0x1800623c6  mov     rdi, r9
0x1800623c9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800623ce  mov     rsi, [rdi]
0x1800623d1  lea     rdx, [rbp+ppBuffer]; ppBuffer
0x1800623d5  xor     r13d, r13d
0x1800623d8  mov     ecx, 4000h; cbMaxLength
0x1800623dd  mov     [rbp+ppBuffer], r13
0x1800623e1  mov     [rbp+var_34], r13d
0x1800623e5  mov     [rbp+var_20], r13
0x1800623e9  mov     [rbp+var_2C], r13d
0x1800623ed  mov     [rbp+var_30], r13d
0x1800623f1  mov     [rbp+var_38], r13d
0x1800623f5  mov     [rbp+var_18], r13
0x1800623f9  call    cs:__imp_MFCreateMemoryBuffer
0x180062400  nop     dword ptr [rax+rax+00h]
0x180062405  mov     ebx, eax
0x180062407  test    eax, eax
0x180062409  jns     short loc_18006245B
0x18006240b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062412  test    rcx, rcx
0x180062415  jnz     short loc_180062423
0x180062417  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18006241c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180062423  cmp     [rcx+8], r13b
0x180062427  jz      loc_1800628BB
0x18006242d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180062432  cmp     [rax+7CCh], ebx
0x180062438  jz      loc_1800628BB
0x18006243e  mov     r8d, 106h; int
0x180062444  mov     r9d, ebx; int
0x180062447  lea     rdx, aCmfaviproperty_1; "CMFAVIPropertyHandler::FeedNextBufferTo"...
0x18006244e  mov     rcx, rax; this
0x180062451  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180062456  jmp     loc_1800628BB
0x18006245b  mov     rcx, [rbp+ppBuffer]
0x18006245f  lea     r9, [rbp+var_2C]
0x180062463  lea     r8, [rbp+var_30]
0x180062467  lea     rdx, [rbp+var_20]
0x18006246b  mov     rax, [rcx]
0x18006246e  mov     rax, [rax+18h]
0x180062472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062477  mov     ebx, eax
0x180062479  test    eax, eax
0x18006247b  jns     short loc_1800624F6
0x18006247d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062484  test    rcx, rcx
0x180062487  jnz     short loc_1800624D0
0x180062489  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180062490  nop     dword ptr [rax+rax+00h]
0x180062495  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006249c  mov     rcx, rax
0x18006249f  test    rax, rax
0x1800624a2  jz      short loc_1800624C2
0x1800624a4  mov     rax, [rax]
0x1800624a7  mov     edx, 7F0h
0x1800624ac  mov     rax, [rax+8]
0x1800624b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800624b5  test    eax, eax
0x1800624b7  jz      short loc_1800624C2
0x1800624b9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800624c0  jmp     short loc_1800624D0
0x1800624c2  lea     rcx, qword_1801B97E0; this
0x1800624c9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800624d0  cmp     [rcx+8], r13b
0x1800624d4  jz      loc_1800628BB
0x1800624da  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800624df  cmp     [rax+7CCh], ebx
0x1800624e5  jz      loc_1800628BB
0x1800624eb  mov     r8d, 108h
0x1800624f1  jmp     loc_180062444
0x1800624f6  mov     rcx, [r15+378h]
0x1800624fd  lea     r9, [rbp+var_38]
0x180062501  mov     r8d, [rbp+var_30]
0x180062505  mov     rdx, [rbp+var_20]
0x180062509  mov     rax, [rcx]
0x18006250c  mov     rax, [rax+18h]
0x180062510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062515  mov     rcx, [rbp+ppBuffer]
0x180062519  mov     ebx, eax
0x18006251b  mov     rax, [rcx]
0x18006251e  mov     rax, [rax+20h]
0x180062522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062527  test    ebx, ebx
0x180062529  jns     short loc_1800625A4
0x18006252b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062532  test    rcx, rcx
0x180062535  jnz     short loc_18006257E
0x180062537  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006253e  nop     dword ptr [rax+rax+00h]
0x180062543  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006254a  mov     rcx, rax
0x18006254d  test    rax, rax
0x180062550  jz      short loc_180062570
0x180062552  mov     rax, [rax]
0x180062555  mov     edx, 7F0h
0x18006255a  mov     rax, [rax+8]
0x18006255e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062563  test    eax, eax
0x180062565  jz      short loc_180062570
0x180062567  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006256e  jmp     short loc_18006257E
0x180062570  lea     rcx, qword_1801B97E0; this
0x180062577  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006257e  cmp     [rcx+8], r13b
0x180062582  jz      loc_1800628BB
0x180062588  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006258d  cmp     [rax+7CCh], ebx
0x180062593  jz      loc_1800628BB
0x180062599  mov     r8d, 10Eh
0x18006259f  jmp     loc_180062444
0x1800625a4  mov     edx, [rbp+var_38]
0x1800625a7  test    edx, edx
0x1800625a9  jnz     short loc_180062629
0x1800625ab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800625b2  mov     ebx, 8000FFFFh
0x1800625b7  test    rcx, rcx
0x1800625ba  jnz     short loc_180062603
0x1800625bc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800625c3  nop     dword ptr [rax+rax+00h]
0x1800625c8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800625cf  mov     rcx, rax
0x1800625d2  test    rax, rax
0x1800625d5  jz      short loc_1800625F5
0x1800625d7  mov     rax, [rax]
0x1800625da  mov     edx, 7F0h
0x1800625df  mov     rax, [rax+8]
0x1800625e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800625e8  test    eax, eax
0x1800625ea  jz      short loc_1800625F5
0x1800625ec  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800625f3  jmp     short loc_180062603
0x1800625f5  lea     rcx, qword_1801B97E0; this
0x1800625fc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180062603  cmp     [rcx+8], r13b
0x180062607  jz      loc_1800628BB
0x18006260d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180062612  cmp     [rax+7CCh], ebx
0x180062618  jz      loc_1800628BB
0x18006261e  mov     r8d, 116h
0x180062624  jmp     loc_180062444
0x180062629  mov     rcx, [rbp+ppBuffer]
0x18006262d  mov     rax, [rcx]
0x180062630  mov     rax, [rax+30h]
0x180062634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062639  mov     ebx, eax
0x18006263b  test    eax, eax
0x18006263d  jns     short loc_1800626B8
0x18006263f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062646  test    rcx, rcx
0x180062649  jnz     short loc_180062692
0x18006264b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180062652  nop     dword ptr [rax+rax+00h]
0x180062657  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006265e  mov     rcx, rax
0x180062661  test    rax, rax
0x180062664  jz      short loc_180062684
0x180062666  mov     rax, [rax]
0x180062669  mov     edx, 7F0h
0x18006266e  mov     rax, [rax+8]
0x180062672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062677  test    eax, eax
0x180062679  jz      short loc_180062684
0x18006267b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062682  jmp     short loc_180062692
0x180062684  lea     rcx, qword_1801B97E0; this
0x18006268b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180062692  cmp     [rcx+8], r13b
0x180062696  jz      loc_1800628BB
0x18006269c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800626a1  cmp     [rax+7CCh], ebx
0x1800626a7  jz      loc_1800628BB
0x1800626ad  mov     r8d, 119h
0x1800626b3  jmp     loc_180062444
0x1800626b8  mov     rax, [r14]
0x1800626bb  lea     rcx, [rbp+var_34]
0x1800626bf  mov     r8, [rbp+ppBuffer]
0x1800626c3  mov     r9, rsi
0x1800626c6  mov     [rsp+78h+var_50], rcx
0x1800626cb  mov     rdx, r12
0x1800626ce  mov     rcx, r14
0x1800626d1  mov     [rsp+78h+var_58], rdi
0x1800626d6  mov     rax, [rax+18h]
0x1800626da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800626df  mov     ebx, eax
0x1800626e1  test    eax, eax
0x1800626e3  jns     short loc_18006275E
0x1800626e5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800626ec  test    rcx, rcx
0x1800626ef  jnz     short loc_180062738
0x1800626f1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800626f8  nop     dword ptr [rax+rax+00h]
0x1800626fd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180062704  mov     rcx, rax
0x180062707  test    rax, rax
0x18006270a  jz      short loc_18006272A
0x18006270c  mov     rax, [rax]
0x18006270f  mov     edx, 7F0h
0x180062714  mov     rax, [rax+8]
0x180062718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006271d  test    eax, eax
0x18006271f  jz      short loc_18006272A
0x180062721  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062728  jmp     short loc_180062738
0x18006272a  lea     rcx, qword_1801B97E0; this
0x180062731  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180062738  cmp     [rcx+8], r13b
0x18006273c  jz      loc_1800628BB
0x180062742  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180062747  cmp     [rax+7CCh], ebx
0x18006274d  jz      loc_1800628BB
0x180062753  mov     r8d, 11Bh
0x180062759  jmp     loc_180062444
0x18006275e  mov     ecx, [rbp+var_34]
0x180062761  test    ecx, ecx
0x180062763  jz      loc_1800628B0
0x180062769  mov     edx, [rbp+var_38]
0x18006276c  add     rdx, rsi
0x18006276f  cmp     rdx, rsi
0x180062772  jb      loc_18006283A
0x180062778  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18006277c  mov     ebx, r13d
0x18006277f  jnz     short loc_180062789
0x180062781  mov     [rdi], rdx
0x180062784  jmp     loc_180062831
0x180062789  cmp     [rdi], rdx
0x18006278c  jz      loc_180062831
0x180062792  mov     rcx, [r15+378h]
0x180062799  lea     r9, [rbp+var_18]
0x18006279d  mov     rdx, [rdi]
0x1800627a0  xor     r8d, r8d
0x1800627a3  mov     rax, [rcx]
0x1800627a6  mov     rax, [rax+28h]
0x1800627aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800627af  mov     ebx, eax
0x1800627b1  test    eax, eax
0x1800627b3  jns     short loc_18006282E
0x1800627b5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800627bc  test    rcx, rcx
0x1800627bf  jnz     short loc_180062808
0x1800627c1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800627c8  nop     dword ptr [rax+rax+00h]
0x1800627cd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800627d4  mov     rcx, rax
0x1800627d7  test    rax, rax
0x1800627da  jz      short loc_1800627FA
0x1800627dc  mov     rax, [rax]
0x1800627df  mov     edx, 7F0h
0x1800627e4  mov     rax, [rax+8]
0x1800627e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800627ed  test    eax, eax
0x1800627ef  jz      short loc_1800627FA
0x1800627f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800627f8  jmp     short loc_180062808
0x1800627fa  lea     rcx, qword_1801B97E0; this
0x180062801  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180062808  cmp     [rcx+8], r13b
0x18006280c  jz      loc_1800628BB
0x180062812  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180062817  cmp     [rax+7CCh], ebx
0x18006281d  jz      loc_1800628BB
0x180062823  mov     r8d, 12Ch
0x180062829  jmp     loc_180062444
0x18006282e  mov     ecx, [rbp+var_34]
0x180062831  test    ecx, ecx
0x180062833  jz      short loc_1800628B0
0x180062835  mov     ecx, r13d
0x180062838  jmp     short loc_1800628B5
0x18006283a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180062841  mov     ebx, 80070216h
0x180062846  test    rcx, rcx
0x180062849  jnz     short loc_180062892
0x18006284b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180062852  nop     dword ptr [rax+rax+00h]
0x180062857  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006285e  mov     rcx, rax
0x180062861  test    rax, rax
0x180062864  jz      short loc_180062884
0x180062866  mov     rax, [rax]
0x180062869  mov     edx, 7F0h
0x18006286e  mov     rax, [rax+8]
0x180062872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062877  test    eax, eax
0x180062879  jz      short loc_180062884
0x18006287b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
