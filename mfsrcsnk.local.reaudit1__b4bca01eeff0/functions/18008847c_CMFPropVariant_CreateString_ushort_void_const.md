# CMFPropVariant::CreateString(ushort,void const *)

- ea: `0x18008847c`
- end: `0x180088a09`
- name: `?CreateString@CMFPropVariant@@QEAAJGPEBX@Z`
- size: `1421`
- prototype: `int(CMFPropVariant *__hidden this, unsigned __int16, const void *)`
- caller_count: `12`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800638a0`
- `0x180076a70`
- `0x1800a0db0`
- `0x1800ab028`
- `0x1800c2278`
- `0x1800c5500`
- `0x1800c77e0`
- `0x1800e57f0`
- `0x1800fab34`
- `0x180155670`
- `0x1801592d0`
- `0x18015b190`

## callees

- `0x180005670`
- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180079680`
- `0x18008847c`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800886e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088920`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800886e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088920`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800886b7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800886b7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800884ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800885f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008870f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008879b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008886b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008894f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800884ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800885f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008870f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008879b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008886b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008894f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800888f2`
- `OLEAUT32!__imp_SysAllocString` at `0x1800888f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800885b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800885b7`

## string_xrefs

- `0x1800884d3`: `CMFPropVariant::CreateString`
- `0x180088597`: `CMFPropVariant::CreateString`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::CreateString(CMFPropVariant *this, __int16 a2, const CHAR *a3)
{
  __int64 v6; // rdx
  __int64 v7; // rdx
  wchar_t *v8; // rcx
  signed int v9; // ebx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  _WORD *v14; // rax
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  signed int LastError; // eax
  __int64 v19; // rdx
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  BSTR v29; // rax
  signed int v30; // eax
  __int64 v31; // rdx
  wchar_t *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  WCHAR *lpWideCharStr; // [rsp+20h] [rbp-10h]
  unsigned int v37; // [rsp+60h] [rbp+30h]
  char v38; // [rsp+68h] [rbp+38h] BYREF

  *(_WORD *)this = a2;
  if ( a2 == 30 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
  }
  else
  {
    if ( a2 != 31 && a2 != 8 )
    {
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CMFPropVariant::CreateString", 1854);
      v8 = (wchar_t *)CallStackTracing::s_wpInstance;
      v9 = -2147024809;
      if ( !CallStackTracing::s_wpInstance )
      {
        v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7);
        CallStackTracing::s_wpInstance = v10;
        if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
        {
          v8 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v8 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v8 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropVariant::CreateString", 1854, -2147024809);
      }
      if ( !g_wppLevels )
        goto LABEL_83;
      v12 = 123;
      goto LABEL_82;
    }
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)&a3[2 * v6] );
  }
  if ( (unsigned __int16)(a2 - 30) <= 1u )
  {
    v37 = 2 * v6 + 2;
    *((_QWORD *)this + 1) = CoTaskMemAlloc(v37);
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CMFPropVariant::CreateString", 1861);
    v14 = (_WORD *)*((_QWORD *)this + 1);
    if ( !v14 )
    {
      v15 = (wchar_t *)CallStackTracing::s_wpInstance;
      v9 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
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
        if ( *((_DWORD *)v17 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v17, "CMFPropVariant::CreateString", 1861, -2147024882);
      }
      if ( !g_wppLevels )
        goto LABEL_83;
      v12 = 124;
LABEL_82:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, this, v9);
LABEL_83:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v38);
      return (unsigned int)v9;
    }
    *v14 = 0;
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v38);
    if ( a2 == 30 )
    {
      lpWideCharStr = (WCHAR *)*((_QWORD *)this + 1);
      v9 = 0;
      *(_WORD *)this = 31;
      if ( !MultiByteToWideChar(0, 0, a3, -1, lpWideCharStr, v37 >> 1) )
      {
        CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CMFPropVariant::CreateString", 1881);
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        v20 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( v9 >= 0 )
        {
          v9 = -2147418113;
          if ( !CallStackTracing::s_wpInstance )
          {
            v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
            CallStackTracing::s_wpInstance = v23;
            if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
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
            v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
            if ( *((_DWORD *)v24 + 499) != -2147418113 )
              CallStackContext::TraceFailure(v24, "CMFPropVariant::CreateString", 1882, -2147418113);
          }
          if ( !g_wppLevels )
            goto LABEL_83;
          v12 = 126;
        }
        else
        {
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
            if ( *((_DWORD *)v22 + 499) != v9 )
              CallStackContext::TraceFailure(v22, "CMFPropVariant::CreateString", 1881, v9);
          }
          if ( !g_wppLevels )
            goto LABEL_83;
          v12 = 125;
        }
        goto LABEL_82;
      }
      return (unsigned int)v9;
    }
    if ( a2 == 31 )
    {
      v9 = StringCchCopyW(*((unsigned __int16 **)this + 1), (unsigned __int64)v37 >> 1, (const unsigned __int16 *)a3);
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CMFPropVariant::CreateString", 1888);
      if ( v9 >= 0 )
        goto LABEL_83;
      v26 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
        CallStackTracing::s_wpInstance = v27;
        if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
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
        v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
        if ( *((_DWORD *)v28 + 499) != v9 )
          CallStackContext::TraceFailure(v28, "CMFPropVariant::CreateString", 1888, v9);
      }
      if ( !g_wppLevels )
        goto LABEL_83;
      v12 = 127;
      goto LABEL_82;
    }
  }
  v9 = 0;
  v29 = SysAllocString((const OLECHAR *)a3);
  *((_QWORD *)this + 1) = v29;
  if ( !v29 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CMFPropVariant::CreateString", 1895);
    v30 = GetLastError();
    v9 = v30;
    if ( v30 > 0 )
      v9 = (unsigned __int16)v30 | 0x80070000;
    if ( v9 >= 0 )
      goto LABEL_83;
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
      if ( *((_DWORD *)v34 + 499) != v9 )
        CallStackContext::TraceFailure(v34, "CMFPropVariant::CreateString", 1895, v9);
    }
    if ( !g_wppLevels )
      goto LABEL_83;
    v12 = 128;
    goto LABEL_82;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18008847c  mov     [rsp-28h+arg_10], rbx
0x180088481  mov     [rsp-28h+arg_18], rsi
0x180088486  push    rbp
0x180088487  push    rdi
0x180088488  push    r12
0x18008848a  push    r13
0x18008848c  push    r15
0x18008848e  mov     rbp, rsp
0x180088491  sub     rsp, 30h
0x180088495  mov     [rcx], dx
0x180088498  mov     r12, r8
0x18008849b  movzx   ebx, dx
0x18008849e  mov     r15, rcx
0x1800884a1  mov     eax, 1Fh
0x1800884a6  cmp     dx, 1Eh
0x1800884aa  jnz     short loc_1800884C0
0x1800884ac  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800884b0  xor     edi, edi
0x1800884b2  inc     rdx
0x1800884b5  cmp     [r8+rdx], dil
0x1800884b9  jnz     short loc_1800884B2
0x1800884bb  jmp     loc_180088594
0x1800884c0  cmp     bx, ax
0x1800884c3  jz      loc_180088584
0x1800884c9  cmp     bx, 8
0x1800884cd  jz      loc_180088584
0x1800884d3  lea     rsi, aCmfpropvariant_15; "CMFPropVariant::CreateString"
0x1800884da  mov     r8d, 73Eh; int
0x1800884e0  mov     rdx, rsi; char *
0x1800884e3  lea     rcx, [rbp+arg_8]; this
0x1800884e7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800884ec  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800884f3  xor     edi, edi
0x1800884f5  mov     ebx, 80070057h
0x1800884fa  test    rcx, rcx
0x1800884fd  jnz     short loc_180088546
0x1800884ff  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180088506  nop     dword ptr [rax+rax+00h]
0x18008850b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180088512  mov     rcx, rax
0x180088515  test    rax, rax
0x180088518  jz      short loc_180088538
0x18008851a  mov     rax, [rax]
0x18008851d  mov     edx, 7F0h
0x180088522  mov     rax, [rax+8]
0x180088526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008852b  test    eax, eax
0x18008852d  jz      short loc_180088538
0x18008852f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088536  jmp     short loc_180088546
0x180088538  lea     rcx, qword_1801B97E0; this
0x18008853f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180088546  cmp     [rcx+8], dil
0x18008854a  jz      short loc_18008856D
0x18008854c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180088551  cmp     [rax+7CCh], ebx
0x180088557  jz      short loc_18008856D
0x180088559  mov     r9d, ebx; int
0x18008855c  mov     r8d, 73Eh; int
0x180088562  mov     rdx, rsi; char *
0x180088565  mov     rcx, rax; this
0x180088568  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008856d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180088574  jb      loc_1800889E6
0x18008857a  mov     edx, 7Bh ; '{'
0x18008857f  jmp     loc_1800889C8
0x180088584  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180088588  xor     edi, edi
0x18008858a  inc     rdx
0x18008858d  cmp     [r8+rdx*2], di
0x180088592  jnz     short loc_18008858A
0x180088594  lea     eax, [rbx-1Eh]
0x180088597  lea     rsi, aCmfpropvariant_15; "CMFPropVariant::CreateString"
0x18008859e  cmp     ax, 1
0x1800885a2  ja      loc_1800888ED
0x1800885a8  lea     edx, ds:2[rdx*2]
0x1800885af  mov     ecx, edx; cb
0x1800885b1  mov     [rbp+arg_0], edx
0x1800885b4  mov     r13d, edx
0x1800885b7  call    cs:__imp_CoTaskMemAlloc
0x1800885be  nop     dword ptr [rax+rax+00h]
0x1800885c3  mov     r8d, 745h; int
0x1800885c9  lea     rcx, [rbp+arg_8]; this
0x1800885cd  mov     rdx, rsi; char *
0x1800885d0  mov     [r15+8], rax
0x1800885d4  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800885d9  mov     rax, [r15+8]
0x1800885dd  test    rax, rax
0x1800885e0  jnz     loc_18008867C
0x1800885e6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800885ed  mov     ebx, 8007000Eh
0x1800885f2  test    rcx, rcx
0x1800885f5  jnz     short loc_18008863E
0x1800885f7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800885fe  nop     dword ptr [rax+rax+00h]
0x180088603  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008860a  mov     rcx, rax
0x18008860d  test    rax, rax
0x180088610  jz      short loc_180088630
0x180088612  mov     rax, [rax]
0x180088615  mov     edx, 7F0h
0x18008861a  mov     rax, [rax+8]
0x18008861e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088623  test    eax, eax
0x180088625  jz      short loc_180088630
0x180088627  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008862e  jmp     short loc_18008863E
0x180088630  lea     rcx, qword_1801B97E0; this
0x180088637  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008863e  cmp     [rcx+8], dil
0x180088642  jz      short loc_180088665
0x180088644  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180088649  cmp     [rax+7CCh], ebx
0x18008864f  jz      short loc_180088665
0x180088651  mov     r9d, ebx; int
0x180088654  mov     r8d, 745h; int
0x18008865a  mov     rdx, rsi; char *
0x18008865d  mov     rcx, rax; this
0x180088660  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180088665  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008866c  jb      loc_1800889E6
0x180088672  mov     edx, 7Ch ; '|'
0x180088677  jmp     loc_1800889C8
0x18008867c  lea     rcx, [rbp+arg_8]; this
0x180088680  mov     [rax], di
0x180088683  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180088688  cmp     bx, 1Eh
0x18008868c  jnz     loc_180088820
0x180088692  mov     eax, [rbp+arg_0]
0x180088695  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180088699  shr     eax, 1
0x18008869b  mov     r8, r12; lpMultiByteStr
0x18008869e  mov     [rsp+30h+cchWideChar], eax; cchWideChar
0x1800886a2  xor     edx, edx; dwFlags
0x1800886a4  mov     rax, [r15+8]
0x1800886a8  xor     ecx, ecx; CodePage
0x1800886aa  mov     [rsp+30h+lpWideCharStr], rax; lpWideCharStr
0x1800886af  mov     ebx, edi
0x1800886b1  mov     word ptr [r15], 1Fh
0x1800886b7  call    cs:__imp_MultiByteToWideChar
0x1800886be  nop     dword ptr [rax+rax+00h]
0x1800886c3  test    eax, eax
0x1800886c5  jnz     loc_1800889EF
0x1800886cb  mov     r12d, 759h
0x1800886d1  lea     rcx, [rbp+arg_8]; this
0x1800886d5  mov     r8d, r12d; int
0x1800886d8  mov     rdx, rsi; char *
0x1800886db  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800886e0  call    cs:__imp_GetLastError
0x1800886e7  nop     dword ptr [rax+rax+00h]
0x1800886ec  mov     ebx, eax
0x1800886ee  test    eax, eax
0x1800886f0  jle     short loc_1800886FB
0x1800886f2  movzx   ebx, ax
0x1800886f5  or      ebx, 80070000h
0x1800886fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088702  test    ebx, ebx
0x180088704  jns     loc_180088791
0x18008870a  test    rcx, rcx
0x18008870d  jnz     short loc_180088756
0x18008870f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180088716  nop     dword ptr [rax+rax+00h]
0x18008871b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180088722  mov     rcx, rax
0x180088725  test    rax, rax
0x180088728  jz      short loc_180088748
0x18008872a  mov     rax, [rax]
0x18008872d  mov     edx, 7F0h
0x180088732  mov     rax, [rax+8]
0x180088736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008873b  test    eax, eax
0x18008873d  jz      short loc_180088748
0x18008873f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088746  jmp     short loc_180088756
0x180088748  lea     rcx, qword_1801B97E0; this
0x18008874f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180088756  cmp     [rcx+8], dil
0x18008875a  jz      short loc_18008877A
0x18008875c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180088761  cmp     [rax+7CCh], ebx
0x180088767  jz      short loc_18008877A
0x180088769  mov     r9d, ebx; int
0x18008876c  mov     r8d, r12d; int
0x18008876f  mov     rdx, rsi; char *
0x180088772  mov     rcx, rax; this
0x180088775  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008877a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180088781  jb      loc_1800889E6
0x180088787  mov     edx, 7Dh ; '}'
0x18008878c  jmp     loc_1800889C8
0x180088791  mov     ebx, 8000FFFFh
0x180088796  test    rcx, rcx
0x180088799  jnz     short loc_1800887E2
0x18008879b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800887a2  nop     dword ptr [rax+rax+00h]
0x1800887a7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800887ae  mov     rcx, rax
0x1800887b1  test    rax, rax
0x1800887b4  jz      short loc_1800887D4
0x1800887b6  mov     rax, [rax]
0x1800887b9  mov     edx, 7F0h
0x1800887be  mov     rax, [rax+8]
0x1800887c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800887c7  test    eax, eax
0x1800887c9  jz      short loc_1800887D4
0x1800887cb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800887d2  jmp     short loc_1800887E2
0x1800887d4  lea     rcx, qword_1801B97E0; this
0x1800887db  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800887e2  cmp     [rcx+8], dil
0x1800887e6  jz      short loc_180088809
0x1800887e8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800887ed  cmp     [rax+7CCh], ebx
0x1800887f3  jz      short loc_180088809
0x1800887f5  mov     r9d, ebx; int
0x1800887f8  mov     r8d, 75Ah; int
0x1800887fe  mov     rdx, rsi; char *
0x180088801  mov     rcx, rax; this
0x180088804  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180088809  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180088810  jb      loc_1800889E6
0x180088816  mov     edx, 7Eh ; '~'
0x18008881b  jmp     loc_1800889C8
0x180088820  mov     eax, 1Fh
0x180088825  cmp     bx, ax
0x180088828  jnz     loc_1800888ED
0x18008882e  mov     rcx, [r15+8]; unsigned __int16 *
0x180088832  mov     r8, r12; unsigned __int16 *
0x180088835  shr     r13, 1
0x180088838  mov     rdx, r13; unsigned __int64
0x18008883b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180088840  mov     r12d, 760h
0x180088846  lea     rcx, [rbp+arg_8]; this
0x18008884a  mov     r8d, r12d; int
0x18008884d  mov     rdx, rsi; char *
0x180088850  mov     ebx, eax
0x180088852  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180088857  test    ebx, ebx
0x180088859  jns     loc_1800889E6
0x18008885f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088866  test    rcx, rcx
0x180088869  jnz     short loc_1800888B2
0x18008886b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180088872  nop     dword ptr [rax+rax+00h]
0x180088877  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008887e  mov     rcx, rax
0x180088881  test    rax, rax
0x180088884  jz      short loc_1800888A4
0x180088886  mov     rax, [rax]
0x180088889  mov     edx, 7F0h
0x18008888e  mov     rax, [rax+8]
0x180088892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088897  test    eax, eax
0x180088899  jz      short loc_1800888A4
0x18008889b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800888a2  jmp     short loc_1800888B2
0x1800888a4  lea     rcx, qword_1801B97E0; this
0x1800888ab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800888b2  cmp     [rcx+8], dil
0x1800888b6  jz      short loc_1800888D6
0x1800888b8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800888bd  cmp     [rax+7CCh], ebx
0x1800888c3  jz      short loc_1800888D6
0x1800888c5  mov     r9d, ebx; int
0x1800888c8  mov     r8d, r12d; int
0x1800888cb  mov     rdx, rsi; char *
0x1800888ce  mov     rcx, rax; this
0x1800888d1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800888d6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800888dd  jb      loc_1800889E6
0x1800888e3  mov     edx, 7Fh
0x1800888e8  jmp     loc_1800889C8
0x1800888ed  mov     rcx, r12; psz
0x1800888f0  mov     ebx, edi
0x1800888f2  call    cs:__imp_SysAllocString
0x1800888f9  nop     dword ptr [rax+rax+00h]
0x1800888fe  mov     [r15+8], rax
0x180088902  test    rax, rax
0x180088905  jnz     loc_1800889EF
0x18008890b  mov     r12d, 767h
0x180088911  lea     rcx, [rbp+arg_8]; this
0x180088915  mov     r8d, r12d; int
0x180088918  mov     rdx, rsi; char *
0x18008891b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180088920  call    cs:__imp_GetLastError
0x180088927  nop     dword ptr [rax+rax+00h]
0x18008892c  mov     ebx, eax
0x18008892e  test    eax, eax
0x180088930  jle     short loc_18008893B
0x180088932  movzx   ebx, ax
0x180088935  or      ebx, 80070000h
0x18008893b  test    ebx, ebx
0x18008893d  jns     loc_1800889E6
0x180088943  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008894a  test    rcx, rcx
0x18008894d  jnz     short loc_180088996
0x18008894f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180088956  nop     dword ptr [rax+rax+00h]
0x18008895b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180088962  mov     rcx, rax
  ... truncated ...
```
