# CMFMP3PropertyHandler::UpdateFooter(IStream *)

- ea: `0x180168ea8`
- end: `0x1801692c3`
- name: `?UpdateFooter@CMFMP3PropertyHandler@@IEAAJPEAUIStream@@@Z`
- size: `1051`
- prototype: `__int64 __fastcall(CMFMP3PropertyHandler *__hidden this, struct IStream *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180167b70`
- `0x1801688b8`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x180168ea8`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180168f20`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180168fc4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180169063`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801690fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180169198`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016921c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180168f20`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180168fc4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180169063`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801690fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180169198`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016921c`
- `MFPlat!MFCreateMemoryBuffer` at `0x180168efe`
- `MFPlat!MFCreateMemoryBuffer` at `0x180168efe`

## string_xrefs

- `0x180168ebe`: `CMFMP3PropertyHandler::UpdateFooter`

## pseudocode

```c
__int64 __fastcall CMFMP3PropertyHandler::UpdateFooter(CMFMP3PropertyHandler *this, struct IStream *a2)
{
  __int64 v4; // rdx
  HRESULT v5; // ebx
  wchar_t *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v9; // r8d
  __int64 v10; // rdx
  wchar_t *v11; // rcx
  CallStackTracing *v12; // rax
  __int64 v13; // rdx
  wchar_t *v14; // rcx
  CallStackTracing *v15; // rax
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  __int64 v19; // rdx
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  int v23; // r8d
  wchar_t *v24; // rcx
  CallStackTracing *v25; // rax
  int v27; // [rsp+30h] [rbp-20h] BYREF
  int v28; // [rsp+34h] [rbp-1Ch] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+38h] [rbp-18h] BYREF
  __int64 v30; // [rsp+40h] [rbp-10h] BYREF
  __int64 v31; // [rsp+48h] [rbp-8h] BYREF
  char v32; // [rsp+90h] [rbp+40h] BYREF
  unsigned int v33; // [rsp+98h] [rbp+48h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v32, "CMFMP3PropertyHandler::UpdateFooter", 396);
  ppBuffer = 0;
  v31 = 0;
  v30 = 0;
  v33 = 0;
  v28 = 0;
  v27 = 0;
  v5 = MFCreateMemoryBuffer(0x80u, &ppBuffer);
  if ( v5 < 0 )
  {
    v6 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
      {
        v9 = 411;
LABEL_10:
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFMP3PropertyHandler::UpdateFooter", v9, v5);
        goto LABEL_58;
      }
    }
    goto LABEL_58;
  }
  v5 = (*(__int64 (__fastcall **)(_QWORD, IMFMediaBuffer *))(**((_QWORD **)this + 238) + 48LL))(
         *((_QWORD *)this + 238),
         ppBuffer);
  if ( v5 >= 0 )
  {
    v5 = ((__int64 (__fastcall *)(struct IStream *, __int64, __int64, __int64 *))a2->lpVtbl->Seek)(a2, -128, 2, &v31);
    if ( v5 < 0 )
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
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
        {
          v9 = 415;
          goto LABEL_10;
        }
      }
      goto LABEL_58;
    }
    v5 = ((__int64 (__fastcall *)(IMFMediaBuffer *, __int64 *, unsigned int *, int *))ppBuffer->lpVtbl->Lock)(
           ppBuffer,
           &v30,
           &v33,
           &v28);
    if ( v5 < 0 )
    {
      v17 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
        CallStackTracing::s_wpInstance = v18;
        if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        {
          v17 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v17 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
        {
          v9 = 417;
          goto LABEL_10;
        }
      }
      goto LABEL_58;
    }
    v5 = ((__int64 (__fastcall *)(struct IStream *, __int64, _QWORD, int *))a2->lpVtbl->Write)(a2, v30, v33, &v27);
    if ( v5 >= 0 )
    {
      if ( v27 == 128 )
        goto LABEL_57;
      v24 = (wchar_t *)CallStackTracing::s_wpInstance;
      v5 = -2147418113;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
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
      if ( !*((_BYTE *)v24 + 8) )
        goto LABEL_57;
      v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
      if ( *((_DWORD *)v22 + 499) == -2147418113 )
        goto LABEL_57;
      v23 = 423;
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
      if ( !*((_BYTE *)v20 + 8) )
        goto LABEL_57;
      v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
      if ( *((_DWORD *)v22 + 499) == v5 )
        goto LABEL_57;
      v23 = 420;
    }
    CallStackContext::TraceFailure(v22, "CMFMP3PropertyHandler::UpdateFooter", v23, v5);
LABEL_57:
    ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
    goto LABEL_58;
  }
  v11 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
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
    if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
    {
      v9 = 413;
      goto LABEL_10;
    }
  }
LABEL_58:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppBuffer);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v32);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180168ea8  mov     [rsp-28h+arg_0], rbx
0x180168ead  push    rbp
0x180168eae  push    rsi
0x180168eaf  push    rdi
0x180168eb0  push    r14
0x180168eb2  push    r15
0x180168eb4  mov     rbp, rsp
0x180168eb7  sub     rsp, 50h
0x180168ebb  mov     rdi, rdx
0x180168ebe  lea     r15, aCmfmp3property_6; "CMFMP3PropertyHandler::UpdateFooter"
0x180168ec5  mov     rsi, rcx
0x180168ec8  mov     rdx, r15; char *
0x180168ecb  mov     r8d, 18Ch; int
0x180168ed1  lea     rcx, [rbp+arg_10]; this
0x180168ed5  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180168eda  xor     r14d, r14d
0x180168edd  lea     rdx, [rbp+ppBuffer]; ppBuffer
0x180168ee1  mov     ecx, 80h; cbMaxLength
0x180168ee6  mov     [rbp+ppBuffer], r14
0x180168eea  mov     [rbp+var_8], r14
0x180168eee  mov     [rbp+var_10], r14
0x180168ef2  mov     [rbp+arg_18], r14d
0x180168ef6  mov     [rbp+var_1C], r14d
0x180168efa  mov     [rbp+var_20], r14d
0x180168efe  call    cs:__imp_MFCreateMemoryBuffer
0x180168f05  nop     dword ptr [rax+rax+00h]
0x180168f0a  mov     ebx, eax
0x180168f0c  test    eax, eax
0x180168f0e  jns     loc_180168F9B
0x180168f14  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180168f1b  test    rcx, rcx
0x180168f1e  jnz     short loc_180168F67
0x180168f20  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180168f27  nop     dword ptr [rax+rax+00h]
0x180168f2c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180168f33  mov     rcx, rax
0x180168f36  test    rax, rax
0x180168f39  jz      short loc_180168F59
0x180168f3b  mov     rax, [rax]
0x180168f3e  mov     edx, 7F0h
0x180168f43  mov     rax, [rax+8]
0x180168f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180168f4c  test    eax, eax
0x180168f4e  jz      short loc_180168F59
0x180168f50  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180168f57  jmp     short loc_180168F67
0x180168f59  lea     rcx, qword_1801B97E0; this
0x180168f60  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180168f67  cmp     [rcx+8], r14b
0x180168f6b  jz      loc_18016929A
0x180168f71  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180168f76  cmp     [rax+7CCh], ebx
0x180168f7c  jz      loc_18016929A
0x180168f82  mov     r8d, 19Bh; int
0x180168f88  mov     r9d, ebx; int
0x180168f8b  mov     rdx, r15; char *
0x180168f8e  mov     rcx, rax; this
0x180168f91  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180168f96  jmp     loc_18016929A
0x180168f9b  mov     rcx, [rsi+770h]
0x180168fa2  mov     rdx, [rbp+ppBuffer]
0x180168fa6  mov     rax, [rcx]
0x180168fa9  mov     rax, [rax+30h]
0x180168fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180168fb2  mov     ebx, eax
0x180168fb4  test    eax, eax
0x180168fb6  jns     short loc_180169031
0x180168fb8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180168fbf  test    rcx, rcx
0x180168fc2  jnz     short loc_18016900B
0x180168fc4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180168fcb  nop     dword ptr [rax+rax+00h]
0x180168fd0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180168fd7  mov     rcx, rax
0x180168fda  test    rax, rax
0x180168fdd  jz      short loc_180168FFD
0x180168fdf  mov     rax, [rax]
0x180168fe2  mov     edx, 7F0h
0x180168fe7  mov     rax, [rax+8]
0x180168feb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180168ff0  test    eax, eax
0x180168ff2  jz      short loc_180168FFD
0x180168ff4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180168ffb  jmp     short loc_18016900B
0x180168ffd  lea     rcx, qword_1801B97E0; this
0x180169004  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18016900b  cmp     [rcx+8], r14b
0x18016900f  jz      loc_18016929A
0x180169015  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18016901a  cmp     [rax+7CCh], ebx
0x180169020  jz      loc_18016929A
0x180169026  mov     r8d, 19Dh
0x18016902c  jmp     loc_180168F88
0x180169031  mov     rax, [rdi]
0x180169034  lea     r9, [rbp+var_8]
0x180169038  mov     rdx, 0FFFFFFFFFFFFFF80h
0x18016903f  mov     r8d, 2
0x180169045  mov     rcx, rdi
0x180169048  mov     rax, [rax+28h]
0x18016904c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180169051  mov     ebx, eax
0x180169053  test    eax, eax
0x180169055  jns     short loc_1801690D0
0x180169057  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016905e  test    rcx, rcx
0x180169061  jnz     short loc_1801690AA
0x180169063  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18016906a  nop     dword ptr [rax+rax+00h]
0x18016906f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180169076  mov     rcx, rax
0x180169079  test    rax, rax
0x18016907c  jz      short loc_18016909C
0x18016907e  mov     rax, [rax]
0x180169081  mov     edx, 7F0h
0x180169086  mov     rax, [rax+8]
0x18016908a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016908f  test    eax, eax
0x180169091  jz      short loc_18016909C
0x180169093  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016909a  jmp     short loc_1801690AA
0x18016909c  lea     rcx, qword_1801B97E0; this
0x1801690a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801690aa  cmp     [rcx+8], r14b
0x1801690ae  jz      loc_18016929A
0x1801690b4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801690b9  cmp     [rax+7CCh], ebx
0x1801690bf  jz      loc_18016929A
0x1801690c5  mov     r8d, 19Fh
0x1801690cb  jmp     loc_180168F88
0x1801690d0  mov     rcx, [rbp+ppBuffer]
0x1801690d4  lea     r9, [rbp+var_1C]
0x1801690d8  lea     r8, [rbp+arg_18]
0x1801690dc  lea     rdx, [rbp+var_10]
0x1801690e0  mov     rax, [rcx]
0x1801690e3  mov     rax, [rax+18h]
0x1801690e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801690ec  mov     ebx, eax
0x1801690ee  test    eax, eax
0x1801690f0  jns     short loc_18016916B
0x1801690f2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801690f9  test    rcx, rcx
0x1801690fc  jnz     short loc_180169145
0x1801690fe  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180169105  nop     dword ptr [rax+rax+00h]
0x18016910a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180169111  mov     rcx, rax
0x180169114  test    rax, rax
0x180169117  jz      short loc_180169137
0x180169119  mov     rax, [rax]
0x18016911c  mov     edx, 7F0h
0x180169121  mov     rax, [rax+8]
0x180169125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016912a  test    eax, eax
0x18016912c  jz      short loc_180169137
0x18016912e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180169135  jmp     short loc_180169145
0x180169137  lea     rcx, qword_1801B97E0; this
0x18016913e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180169145  cmp     [rcx+8], r14b
0x180169149  jz      loc_18016929A
0x18016914f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180169154  cmp     [rax+7CCh], ebx
0x18016915a  jz      loc_18016929A
0x180169160  mov     r8d, 1A1h
0x180169166  jmp     loc_180168F88
0x18016916b  mov     rax, [rdi]
0x18016916e  lea     r9, [rbp+var_20]
0x180169172  mov     r8d, [rbp+arg_18]
0x180169176  mov     rcx, rdi
0x180169179  mov     rdx, [rbp+var_10]
0x18016917d  mov     rax, [rax+20h]
0x180169181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180169186  mov     ebx, eax
0x180169188  test    eax, eax
0x18016918a  jns     short loc_180169202
0x18016918c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180169193  test    rcx, rcx
0x180169196  jnz     short loc_1801691DF
0x180169198  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18016919f  nop     dword ptr [rax+rax+00h]
0x1801691a4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801691ab  mov     rcx, rax
0x1801691ae  test    rax, rax
0x1801691b1  jz      short loc_1801691D1
0x1801691b3  mov     rax, [rax]
0x1801691b6  mov     edx, 7F0h
0x1801691bb  mov     rax, [rax+8]
0x1801691bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801691c4  test    eax, eax
0x1801691c6  jz      short loc_1801691D1
0x1801691c8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801691cf  jmp     short loc_1801691DF
0x1801691d1  lea     rcx, qword_1801B97E0; this
0x1801691d8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801691df  cmp     [rcx+8], r14b
0x1801691e3  jz      loc_18016928A
0x1801691e9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801691ee  cmp     [rax+7CCh], ebx
0x1801691f4  jz      loc_18016928A
0x1801691fa  mov     r8d, 1A4h
0x180169200  jmp     short loc_18016927C
0x180169202  cmp     [rbp+var_20], 80h
0x180169209  jz      short loc_18016928A
0x18016920b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180169212  mov     ebx, 8000FFFFh
0x180169217  test    rcx, rcx
0x18016921a  jnz     short loc_180169263
0x18016921c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180169223  nop     dword ptr [rax+rax+00h]
0x180169228  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18016922f  mov     rcx, rax
0x180169232  test    rax, rax
0x180169235  jz      short loc_180169255
0x180169237  mov     rax, [rax]
0x18016923a  mov     edx, 7F0h
0x18016923f  mov     rax, [rax+8]
0x180169243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180169248  test    eax, eax
0x18016924a  jz      short loc_180169255
0x18016924c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180169253  jmp     short loc_180169263
0x180169255  lea     rcx, qword_1801B97E0; this
0x18016925c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180169263  cmp     [rcx+8], r14b
0x180169267  jz      short loc_18016928A
0x180169269  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18016926e  cmp     [rax+7CCh], ebx
0x180169274  jz      short loc_18016928A
0x180169276  mov     r8d, 1A7h; int
0x18016927c  mov     r9d, ebx; int
0x18016927f  mov     rdx, r15; char *
0x180169282  mov     rcx, rax; this
0x180169285  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18016928a  mov     rcx, [rbp+ppBuffer]
0x18016928e  mov     rax, [rcx]
0x180169291  mov     rax, [rax+20h]
0x180169295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016929a  lea     rcx, [rbp+ppBuffer]; void *
0x18016929e  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1801692a3  lea     rcx, [rbp+arg_10]; this
0x1801692a7  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1801692ac  mov     eax, ebx
0x1801692ae  mov     rbx, [rsp+50h+arg_0]
0x1801692b6  add     rsp, 50h
0x1801692ba  pop     r15
0x1801692bc  pop     r14
0x1801692be  pop     rdi
0x1801692bf  pop     rsi
0x1801692c0  pop     rbp
0x1801692c1  retn
```
