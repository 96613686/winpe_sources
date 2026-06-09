# CMFMP3PropertyHandler::UpdateFooter(IStream *)

- ea: `0x1801600f0`
- end: `0x1801604e0`
- name: `?UpdateFooter@CMFMP3PropertyHandler@@IEAAJPEAUIStream@@@Z`
- size: `1008`
- prototype: `__int64 __fastcall(CMFMP3PropertyHandler *__hidden this, struct IStream *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18015ee70`
- `0x18015fb34`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x1801600f0`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180160162`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180160200`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180160299`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016032e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801603c2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180160440`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180160162`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180160200`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180160299`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016032e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801603c2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180160440`
- `MFPlat!MFCreateMemoryBuffer` at `0x180160146`
- `MFPlat!MFCreateMemoryBuffer` at `0x180160146`

## string_xrefs

- `0x180160106`: `CMFMP3PropertyHandler::UpdateFooter`

## pseudocode

```c
__int64 __fastcall CMFMP3PropertyHandler::UpdateFooter(CMFMP3PropertyHandler *this, struct IStream *a2)
{
  __int64 v4; // rdx
  HRESULT v5; // ebx
  __int64 v6; // r8
  __int64 v7; // r9
  wchar_t *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v11; // r8d
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  int v33; // r8d
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  int v37; // [rsp+30h] [rbp-20h] BYREF
  int v38; // [rsp+34h] [rbp-1Ch] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+38h] [rbp-18h] BYREF
  __int64 v40; // [rsp+40h] [rbp-10h] BYREF
  __int64 v41; // [rsp+48h] [rbp-8h] BYREF
  char v42; // [rsp+90h] [rbp+40h] BYREF
  unsigned int v43; // [rsp+98h] [rbp+48h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v42, "CMFMP3PropertyHandler::UpdateFooter", 396);
  ppBuffer = 0;
  v41 = 0;
  v40 = 0;
  v43 = 0;
  v38 = 0;
  v37 = 0;
  v5 = MFCreateMemoryBuffer(0x80u, &ppBuffer);
  if ( v5 < 0 )
  {
    v8 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v6, v7);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v8 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
      {
        v11 = 411;
LABEL_10:
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFMP3PropertyHandler::UpdateFooter", v11, v5);
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
    v5 = ((__int64 (__fastcall *)(struct IStream *, __int64, __int64, __int64 *))a2->lpVtbl->Seek)(a2, -128, 2, &v41);
    if ( v5 < 0 )
    {
      v20 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17, v18, v19);
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
        {
          v11 = 415;
          goto LABEL_10;
        }
      }
      goto LABEL_58;
    }
    v5 = ((__int64 (__fastcall *)(IMFMediaBuffer *, __int64 *, unsigned int *, int *))ppBuffer->lpVtbl->Lock)(
           ppBuffer,
           &v40,
           &v43,
           &v38);
    if ( v5 < 0 )
    {
      v25 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23, v24);
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
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
        {
          v11 = 417;
          goto LABEL_10;
        }
      }
      goto LABEL_58;
    }
    v5 = ((__int64 (__fastcall *)(struct IStream *, __int64, _QWORD, int *))a2->lpVtbl->Write)(a2, v40, v43, &v37);
    if ( v5 >= 0 )
    {
      if ( v37 == 128 )
        goto LABEL_57;
      v34 = (wchar_t *)CallStackTracing::s_wpInstance;
      v5 = -2147418113;
      if ( !CallStackTracing::s_wpInstance )
      {
        v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, v29);
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
      if ( !*((_BYTE *)v34 + 8) )
        goto LABEL_57;
      v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
      if ( *((_DWORD *)v32 + 499) == -2147418113 )
        goto LABEL_57;
      v33 = 423;
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
      if ( !*((_BYTE *)v30 + 8) )
        goto LABEL_57;
      v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
      if ( *((_DWORD *)v32 + 499) == v5 )
        goto LABEL_57;
      v33 = 420;
    }
    CallStackContext::TraceFailure(v32, "CMFMP3PropertyHandler::UpdateFooter", v33, v5);
LABEL_57:
    ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
    goto LABEL_58;
  }
  v15 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
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
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
    if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
    {
      v11 = 413;
      goto LABEL_10;
    }
  }
LABEL_58:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppBuffer);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v42);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1801600f0  mov     [rsp-28h+arg_0], rbx
0x1801600f5  push    rbp
0x1801600f6  push    rsi
0x1801600f7  push    rdi
0x1801600f8  push    r14
0x1801600fa  push    r15
0x1801600fc  mov     rbp, rsp
0x1801600ff  sub     rsp, 50h
0x180160103  mov     rdi, rdx
0x180160106  lea     r15, aCmfmp3property_6; "CMFMP3PropertyHandler::UpdateFooter"
0x18016010d  mov     rsi, rcx
0x180160110  mov     rdx, r15; char *
0x180160113  mov     r8d, 18Ch; int
0x180160119  lea     rcx, [rbp+arg_10]; this
0x18016011d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180160122  xor     r14d, r14d
0x180160125  lea     rdx, [rbp+ppBuffer]; ppBuffer
0x180160129  mov     ecx, 80h; cbMaxLength
0x18016012e  mov     [rbp+ppBuffer], r14
0x180160132  mov     [rbp+var_8], r14
0x180160136  mov     [rbp+var_10], r14
0x18016013a  mov     [rbp+arg_18], r14d
0x18016013e  mov     [rbp+var_1C], r14d
0x180160142  mov     [rbp+var_20], r14d
0x180160146  call    cs:__imp_MFCreateMemoryBuffer
0x18016014c  mov     ebx, eax
0x18016014e  test    eax, eax
0x180160150  jns     loc_1801601D7
0x180160156  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016015d  test    rcx, rcx
0x180160160  jnz     short loc_1801601A3
0x180160162  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180160168  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18016016f  mov     rcx, rax
0x180160172  test    rax, rax
0x180160175  jz      short loc_180160195
0x180160177  mov     rax, [rax]
0x18016017a  mov     edx, 7F0h
0x18016017f  mov     rax, [rax+8]
0x180160183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180160188  test    eax, eax
0x18016018a  jz      short loc_180160195
0x18016018c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180160193  jmp     short loc_1801601A3
0x180160195  lea     rcx, qword_1801B07E0; this
0x18016019c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801601a3  cmp     [rcx+8], r14b
0x1801601a7  jz      loc_1801604B8
0x1801601ad  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801601b2  cmp     [rax+7CCh], ebx
0x1801601b8  jz      loc_1801604B8
0x1801601be  mov     r8d, 19Bh; int
0x1801601c4  mov     r9d, ebx; int
0x1801601c7  mov     rdx, r15; char *
0x1801601ca  mov     rcx, rax; this
0x1801601cd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801601d2  jmp     loc_1801604B8
0x1801601d7  mov     rcx, [rsi+770h]
0x1801601de  mov     rdx, [rbp+ppBuffer]
0x1801601e2  mov     rax, [rcx]
0x1801601e5  mov     rax, [rax+30h]
0x1801601e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801601ee  mov     ebx, eax
0x1801601f0  test    eax, eax
0x1801601f2  jns     short loc_180160267
0x1801601f4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801601fb  test    rcx, rcx
0x1801601fe  jnz     short loc_180160241
0x180160200  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180160206  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18016020d  mov     rcx, rax
0x180160210  test    rax, rax
0x180160213  jz      short loc_180160233
0x180160215  mov     rax, [rax]
0x180160218  mov     edx, 7F0h
0x18016021d  mov     rax, [rax+8]
0x180160221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180160226  test    eax, eax
0x180160228  jz      short loc_180160233
0x18016022a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180160231  jmp     short loc_180160241
0x180160233  lea     rcx, qword_1801B07E0; this
0x18016023a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180160241  cmp     [rcx+8], r14b
0x180160245  jz      loc_1801604B8
0x18016024b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180160250  cmp     [rax+7CCh], ebx
0x180160256  jz      loc_1801604B8
0x18016025c  mov     r8d, 19Dh
0x180160262  jmp     loc_1801601C4
0x180160267  mov     rax, [rdi]
0x18016026a  lea     r9, [rbp+var_8]
0x18016026e  mov     rdx, 0FFFFFFFFFFFFFF80h
0x180160275  mov     r8d, 2
0x18016027b  mov     rcx, rdi
0x18016027e  mov     rax, [rax+28h]
0x180160282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180160287  mov     ebx, eax
0x180160289  test    eax, eax
0x18016028b  jns     short loc_180160300
0x18016028d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180160294  test    rcx, rcx
0x180160297  jnz     short loc_1801602DA
0x180160299  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18016029f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801602a6  mov     rcx, rax
0x1801602a9  test    rax, rax
0x1801602ac  jz      short loc_1801602CC
0x1801602ae  mov     rax, [rax]
0x1801602b1  mov     edx, 7F0h
0x1801602b6  mov     rax, [rax+8]
0x1801602ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801602bf  test    eax, eax
0x1801602c1  jz      short loc_1801602CC
0x1801602c3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801602ca  jmp     short loc_1801602DA
0x1801602cc  lea     rcx, qword_1801B07E0; this
0x1801602d3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801602da  cmp     [rcx+8], r14b
0x1801602de  jz      loc_1801604B8
0x1801602e4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801602e9  cmp     [rax+7CCh], ebx
0x1801602ef  jz      loc_1801604B8
0x1801602f5  mov     r8d, 19Fh
0x1801602fb  jmp     loc_1801601C4
0x180160300  mov     rcx, [rbp+ppBuffer]
0x180160304  lea     r9, [rbp+var_1C]
0x180160308  lea     r8, [rbp+arg_18]
0x18016030c  lea     rdx, [rbp+var_10]
0x180160310  mov     rax, [rcx]
0x180160313  mov     rax, [rax+18h]
0x180160317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016031c  mov     ebx, eax
0x18016031e  test    eax, eax
0x180160320  jns     short loc_180160395
0x180160322  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180160329  test    rcx, rcx
0x18016032c  jnz     short loc_18016036F
0x18016032e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180160334  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18016033b  mov     rcx, rax
0x18016033e  test    rax, rax
0x180160341  jz      short loc_180160361
0x180160343  mov     rax, [rax]
0x180160346  mov     edx, 7F0h
0x18016034b  mov     rax, [rax+8]
0x18016034f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180160354  test    eax, eax
0x180160356  jz      short loc_180160361
0x180160358  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016035f  jmp     short loc_18016036F
0x180160361  lea     rcx, qword_1801B07E0; this
0x180160368  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18016036f  cmp     [rcx+8], r14b
0x180160373  jz      loc_1801604B8
0x180160379  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18016037e  cmp     [rax+7CCh], ebx
0x180160384  jz      loc_1801604B8
0x18016038a  mov     r8d, 1A1h
0x180160390  jmp     loc_1801601C4
0x180160395  mov     rax, [rdi]
0x180160398  lea     r9, [rbp+var_20]
0x18016039c  mov     r8d, [rbp+arg_18]
0x1801603a0  mov     rcx, rdi
0x1801603a3  mov     rdx, [rbp+var_10]
0x1801603a7  mov     rax, [rax+20h]
0x1801603ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801603b0  mov     ebx, eax
0x1801603b2  test    eax, eax
0x1801603b4  jns     short loc_180160426
0x1801603b6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801603bd  test    rcx, rcx
0x1801603c0  jnz     short loc_180160403
0x1801603c2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801603c8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801603cf  mov     rcx, rax
0x1801603d2  test    rax, rax
0x1801603d5  jz      short loc_1801603F5
0x1801603d7  mov     rax, [rax]
0x1801603da  mov     edx, 7F0h
0x1801603df  mov     rax, [rax+8]
0x1801603e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801603e8  test    eax, eax
0x1801603ea  jz      short loc_1801603F5
0x1801603ec  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801603f3  jmp     short loc_180160403
0x1801603f5  lea     rcx, qword_1801B07E0; this
0x1801603fc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180160403  cmp     [rcx+8], r14b
0x180160407  jz      loc_1801604A8
0x18016040d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180160412  cmp     [rax+7CCh], ebx
0x180160418  jz      loc_1801604A8
0x18016041e  mov     r8d, 1A4h
0x180160424  jmp     short loc_18016049A
0x180160426  cmp     [rbp+var_20], 80h
0x18016042d  jz      short loc_1801604A8
0x18016042f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180160436  mov     ebx, 8000FFFFh
0x18016043b  test    rcx, rcx
0x18016043e  jnz     short loc_180160481
0x180160440  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180160446  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18016044d  mov     rcx, rax
0x180160450  test    rax, rax
0x180160453  jz      short loc_180160473
0x180160455  mov     rax, [rax]
0x180160458  mov     edx, 7F0h
0x18016045d  mov     rax, [rax+8]
0x180160461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180160466  test    eax, eax
0x180160468  jz      short loc_180160473
0x18016046a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180160471  jmp     short loc_180160481
0x180160473  lea     rcx, qword_1801B07E0; this
0x18016047a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180160481  cmp     [rcx+8], r14b
0x180160485  jz      short loc_1801604A8
0x180160487  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18016048c  cmp     [rax+7CCh], ebx
0x180160492  jz      short loc_1801604A8
0x180160494  mov     r8d, 1A7h; int
0x18016049a  mov     r9d, ebx; int
0x18016049d  mov     rdx, r15; char *
0x1801604a0  mov     rcx, rax; this
0x1801604a3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801604a8  mov     rcx, [rbp+ppBuffer]
0x1801604ac  mov     rax, [rcx]
0x1801604af  mov     rax, [rax+20h]
0x1801604b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801604b8  lea     rcx, [rbp+ppBuffer]; void *
0x1801604bc  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1801604c1  lea     rcx, [rbp+arg_10]; this
0x1801604c5  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1801604ca  mov     eax, ebx
0x1801604cc  mov     rbx, [rsp+50h+arg_0]
0x1801604d4  add     rsp, 50h
0x1801604d8  pop     r15
0x1801604da  pop     r14
0x1801604dc  pop     rdi
0x1801604dd  pop     rsi
0x1801604de  pop     rbp
0x1801604df  retn
```
