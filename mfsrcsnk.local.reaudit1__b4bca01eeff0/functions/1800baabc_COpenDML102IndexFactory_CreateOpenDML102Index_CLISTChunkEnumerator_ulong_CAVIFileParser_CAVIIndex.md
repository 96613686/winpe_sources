# COpenDML102IndexFactory::CreateOpenDML102Index(CLISTChunkEnumerator *,ulong,CAVIFileParser *,CAVIIndex * *)

- ea: `0x1800baabc`
- end: `0x1800bb082`
- name: `?CreateOpenDML102Index@COpenDML102IndexFactory@@QEAAJPEAVCLISTChunkEnumerator@@KPEAVCAVIFileParser@@PEAPEAVCAVIIndex@@@Z`
- size: `1478`
- prototype: `int(COpenDML102IndexFactory *__hidden this, struct CLISTChunkEnumerator *, unsigned int, struct CAVIFileParser *, struct CAVIIndex **)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting`

## callers

- `0x18006d984`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180034ce8`
- `0x180079680`
- `0x1800a2320`
- `0x1800a9fc8`
- `0x1800baabc`
- `0x180110a7c`
- `0x180110a94`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bab1e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800babce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bac84`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bad3a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bae10`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800baef7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800baf9f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bab1e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800babce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bac84`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bad3a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bae10`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800baef7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800baf9f`

## string_xrefs

- `0x1800baad8`: `COpenDML102IndexFactory::CreateOpenDML102Index`
- `0x1800bab7b`: `COpenDML102IndexFactory::CreateOpenDML102Index`
- `0x1800bac2b`: `COpenDML102IndexFactory::CreateOpenDML102Index`
- `0x1800bace1`: `COpenDML102IndexFactory::CreateOpenDML102Index`
- `0x1800bad97`: `COpenDML102IndexFactory::CreateOpenDML102Index`
- `0x1800bae6d`: `COpenDML102IndexFactory::CreateOpenDML102Index`
- `0x1800baf58`: `COpenDML102IndexFactory::CreateOpenDML102Index`
- `0x1800baffc`: `COpenDML102IndexFactory::CreateOpenDML102Index`

## pseudocode

```c
__int64 __fastcall COpenDML102IndexFactory::CreateOpenDML102Index(
        COpenDML102IndexFactory *this,
        struct CLISTChunkEnumerator *a2,
        unsigned int a3,
        struct CAVIFileParser *a4,
        struct CAVIIndex **a5)
{
  __int64 v9; // rdx
  struct CAVIIndex **v10; // r14
  CODMLSuperIndex *v11; // rsi
  wchar_t *v12; // rcx
  unsigned __int8 *v13; // r13
  int v14; // ebx
  int v15; // edi
  CallStackTracing *v16; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v18; // rdx
  unsigned __int8 *v19; // rax
  __int64 v20; // rdx
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  wchar_t *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  CODMLStandardIndex *v32; // rax
  __int64 v33; // rdx
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  CODMLSuperIndex *v37; // rax
  wchar_t *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  wchar_t *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  char v45; // [rsp+80h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v45,
    "COpenDML102IndexFactory::CreateOpenDML102Index",
    40);
  v10 = a5;
  v11 = 0;
  *a5 = 0;
  if ( *((_DWORD *)a2 + 14) < 0x18u )
  {
    v12 = (wchar_t *)CallStackTracing::s_wpInstance;
    v13 = 0;
    v14 = -1072875842;
    v15 = -1072875842;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
      CallStackTracing::s_wpInstance = v16;
      if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875842 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "COpenDML102IndexFactory::CreateOpenDML102Index",
          55,
          -1072875842);
    }
    if ( g_wppLevels )
    {
      v18 = 11;
LABEL_84:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_8c8e1fda19d530912db1a52be9331974_Traceguids, this, v14);
      goto LABEL_85;
    }
    goto LABEL_85;
  }
  v19 = (unsigned __int8 *)operator new(*((unsigned int *)a2 + 14));
  v13 = v19;
  if ( !v19 )
  {
    v21 = (wchar_t *)CallStackTracing::s_wpInstance;
    v14 = -2147024882;
    v15 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
      CallStackTracing::s_wpInstance = v22;
      if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
      {
        v21 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v21 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v21 + 8) )
    {
      v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
      if ( *((_DWORD *)v23 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v23, "COpenDML102IndexFactory::CreateOpenDML102Index", 59, -2147024882);
    }
    if ( g_wppLevels )
    {
      v18 = 12;
      goto LABEL_84;
    }
    goto LABEL_85;
  }
  LODWORD(a5) = ReadData(*((struct CSourcePluginBufferReader **)a2 + 1), v19, *((_DWORD *)a2 + 14));
  v15 = (int)a5;
  if ( (int)a5 < 0 )
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
      if ( *((_DWORD *)v27 + 499) != v15 )
        CallStackContext::TraceFailure(v27, "COpenDML102IndexFactory::CreateOpenDML102Index", 60, v15);
    }
    if ( !g_wppLevels )
      goto LABEL_85;
    v28 = 13;
LABEL_34:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v28, &WPP_8c8e1fda19d530912db1a52be9331974_Traceguids, this, v15);
    goto LABEL_85;
  }
  if ( v13[3] )
  {
    if ( v13[3] != 1 )
    {
      v29 = (wchar_t *)CallStackTracing::s_wpInstance;
      v14 = -1072875842;
      v15 = -1072875842;
      if ( !CallStackTracing::s_wpInstance )
      {
        v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
        CallStackTracing::s_wpInstance = v30;
        if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
        {
          v29 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v29 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v29 + 8) )
      {
        v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
        if ( *((_DWORD *)v31 + 499) != -1072875842 )
          CallStackContext::TraceFailure(v31, "COpenDML102IndexFactory::CreateOpenDML102Index", 84, -1072875842);
      }
      if ( g_wppLevels )
      {
        v18 = 16;
        goto LABEL_84;
      }
      goto LABEL_85;
    }
    v32 = (CODMLStandardIndex *)operator new(0x30u);
    if ( !v32 || (v11 = CODMLStandardIndex::CODMLStandardIndex(v32, v13, *((_DWORD *)a2 + 14), a3, (int *)&a5)) == 0 )
    {
      v34 = (wchar_t *)CallStackTracing::s_wpInstance;
      v14 = -2147024882;
      v15 = -2147024882;
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
        if ( *((_DWORD *)v36 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v36, "COpenDML102IndexFactory::CreateOpenDML102Index", 80, -2147024882);
      }
      if ( g_wppLevels )
      {
        v18 = 15;
        goto LABEL_84;
      }
      goto LABEL_85;
    }
  }
  else
  {
    v37 = (CODMLSuperIndex *)operator new(0x40u);
    if ( !v37 || (v11 = CODMLSuperIndex::CODMLSuperIndex(v37, v13, *((_DWORD *)a2 + 14), a3, a4, (int *)&a5)) == 0 )
    {
      v41 = (wchar_t *)CallStackTracing::s_wpInstance;
      v14 = -2147024882;
      v15 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
        CallStackTracing::s_wpInstance = v42;
        if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
        {
          v41 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v41 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v41 + 8) )
      {
        v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
        if ( *((_DWORD *)v43 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v43, "COpenDML102IndexFactory::CreateOpenDML102Index", 72, -2147024882);
      }
      if ( g_wppLevels )
      {
        v18 = 14;
        goto LABEL_84;
      }
      goto LABEL_85;
    }
  }
  v15 = (int)a5;
  if ( (int)a5 >= 0 )
  {
    *v10 = v11;
    goto LABEL_85;
  }
  v38 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
    CallStackTracing::s_wpInstance = v39;
    if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
    {
      v38 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v38 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
  }
  if ( *((_BYTE *)v38 + 8) )
  {
    v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
    if ( v15 < 0 && *((_DWORD *)v40 + 499) != v15 )
      CallStackContext::TraceFailure(v40, "COpenDML102IndexFactory::CreateOpenDML102Index", 86, v15);
  }
  if ( g_wppLevels )
  {
    v28 = 17;
    goto LABEL_34;
  }
LABEL_85:
  operator delete(v13);
  if ( v15 < 0 && v11 )
    (**(void (__fastcall ***)(CODMLSuperIndex *, __int64))v11)(v11, 1);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v45);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800baabc  mov     rax, rsp
0x1800baabf  push    rbx
0x1800baac0  push    rbp
0x1800baac1  push    rsi
0x1800baac2  push    rdi
0x1800baac3  push    r12
0x1800baac5  push    r13
0x1800baac7  push    r14
0x1800baac9  push    r15
0x1800baacb  sub     rsp, 38h
0x1800baacf  mov     ebp, r8d
0x1800baad2  mov     rbx, rdx
0x1800baad5  mov     r12, rcx
0x1800baad8  lea     rdx, aCopendml102ind; "COpenDML102IndexFactory::CreateOpenDML1"...
0x1800baadf  mov     r8d, 28h ; '('; int
0x1800baae5  lea     rcx, [rax+8]; this
0x1800baae9  mov     r15, r9
0x1800baaec  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800baaf1  mov     r14, [rsp+78h+arg_20]
0x1800baaf9  xor     esi, esi
0x1800baafb  mov     [r14], rsi
0x1800baafe  cmp     dword ptr [rbx+38h], 18h
0x1800bab02  jnb     loc_1800BABA7
0x1800bab08  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bab0f  xor     r13d, r13d
0x1800bab12  mov     ebx, 0C00D36BEh
0x1800bab17  mov     edi, ebx
0x1800bab19  test    rcx, rcx
0x1800bab1c  jnz     short loc_1800BAB65
0x1800bab1e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bab25  nop     dword ptr [rax+rax+00h]
0x1800bab2a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bab31  mov     rcx, rax
0x1800bab34  test    rax, rax
0x1800bab37  jz      short loc_1800BAB57
0x1800bab39  mov     rax, [rax]
0x1800bab3c  mov     edx, 7F0h
0x1800bab41  mov     rax, [rax+8]
0x1800bab45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bab4a  test    eax, eax
0x1800bab4c  jz      short loc_1800BAB57
0x1800bab4e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bab55  jmp     short loc_1800BAB65
0x1800bab57  lea     rcx, qword_1801B97E0; this
0x1800bab5e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bab65  cmp     [rcx+8], sil
0x1800bab69  jz      short loc_1800BAB90
0x1800bab6b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bab70  cmp     [rax+7CCh], ebx
0x1800bab76  jz      short loc_1800BAB90
0x1800bab78  mov     r9d, ebx; int
0x1800bab7b  lea     rdx, aCopendml102ind; "COpenDML102IndexFactory::CreateOpenDML1"...
0x1800bab82  mov     r8d, 37h ; '7'; int
0x1800bab88  mov     rcx, rax; this
0x1800bab8b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bab90  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bab97  jb      loc_1800BB03D
0x1800bab9d  mov     edx, 0Bh
0x1800baba2  jmp     loc_1800BB01F
0x1800baba7  mov     ecx, [rbx+38h]; Size
0x1800babaa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800babaf  mov     r13, rax
0x1800babb2  test    rax, rax
0x1800babb5  jnz     loc_1800BAC57
0x1800babbb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800babc2  mov     ebx, 8007000Eh
0x1800babc7  mov     edi, ebx
0x1800babc9  test    rcx, rcx
0x1800babcc  jnz     short loc_1800BAC15
0x1800babce  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800babd5  nop     dword ptr [rax+rax+00h]
0x1800babda  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800babe1  mov     rcx, rax
0x1800babe4  test    rax, rax
0x1800babe7  jz      short loc_1800BAC07
0x1800babe9  mov     rax, [rax]
0x1800babec  mov     edx, 7F0h
0x1800babf1  mov     rax, [rax+8]
0x1800babf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800babfa  test    eax, eax
0x1800babfc  jz      short loc_1800BAC07
0x1800babfe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bac05  jmp     short loc_1800BAC15
0x1800bac07  lea     rcx, qword_1801B97E0; this
0x1800bac0e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bac15  cmp     [rcx+8], sil
0x1800bac19  jz      short loc_1800BAC40
0x1800bac1b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bac20  cmp     [rax+7CCh], ebx
0x1800bac26  jz      short loc_1800BAC40
0x1800bac28  mov     r9d, ebx; int
0x1800bac2b  lea     rdx, aCopendml102ind; "COpenDML102IndexFactory::CreateOpenDML1"...
0x1800bac32  mov     r8d, 3Bh ; ';'; int
0x1800bac38  mov     rcx, rax; this
0x1800bac3b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bac40  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bac47  jb      loc_1800BB03D
0x1800bac4d  mov     edx, 0Ch
0x1800bac52  jmp     loc_1800BB01F
0x1800bac57  mov     r8d, [rbx+38h]; unsigned int
0x1800bac5b  mov     rdx, r13; unsigned __int8 *
0x1800bac5e  mov     rcx, [rbx+8]; struct CSourcePluginBufferReader *
0x1800bac62  call    ?ReadData@@YAJPEAVCSourcePluginBufferReader@@PEAEK@Z; ReadData(CSourcePluginBufferReader *,uchar *,ulong)
0x1800bac67  mov     dword ptr [rsp+78h+arg_20], eax
0x1800bac6e  mov     edi, eax
0x1800bac70  test    eax, eax
0x1800bac72  jns     loc_1800BAD11
0x1800bac78  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bac7f  test    rcx, rcx
0x1800bac82  jnz     short loc_1800BACCB
0x1800bac84  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bac8b  nop     dword ptr [rax+rax+00h]
0x1800bac90  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bac97  mov     rcx, rax
0x1800bac9a  test    rax, rax
0x1800bac9d  jz      short loc_1800BACBD
0x1800bac9f  mov     rax, [rax]
0x1800baca2  mov     edx, 7F0h
0x1800baca7  mov     rax, [rax+8]
0x1800bacab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bacb0  test    eax, eax
0x1800bacb2  jz      short loc_1800BACBD
0x1800bacb4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bacbb  jmp     short loc_1800BACCB
0x1800bacbd  lea     rcx, qword_1801B97E0; this
0x1800bacc4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800baccb  cmp     [rcx+8], sil
0x1800baccf  jz      short loc_1800BACF6
0x1800bacd1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bacd6  cmp     [rax+7CCh], edi
0x1800bacdc  jz      short loc_1800BACF6
0x1800bacde  mov     r9d, edi; int
0x1800bace1  lea     rdx, aCopendml102ind; "COpenDML102IndexFactory::CreateOpenDML1"...
0x1800bace8  mov     r8d, 3Ch ; '<'; int
0x1800bacee  mov     rcx, rax; this
0x1800bacf1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bacf6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bacfd  jb      loc_1800BB03D
0x1800bad03  mov     edx, 0Dh
0x1800bad08  mov     dword ptr [rsp+78h+var_58], edi
0x1800bad0c  jmp     loc_1800BB023
0x1800bad11  movzx   ecx, byte ptr [r13+3]
0x1800bad16  test    ecx, ecx
0x1800bad18  jz      loc_1800BAE99
0x1800bad1e  cmp     ecx, 1
0x1800bad21  jz      loc_1800BADC3
0x1800bad27  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bad2e  mov     ebx, 0C00D36BEh
0x1800bad33  mov     edi, ebx
0x1800bad35  test    rcx, rcx
0x1800bad38  jnz     short loc_1800BAD81
0x1800bad3a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bad41  nop     dword ptr [rax+rax+00h]
0x1800bad46  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bad4d  mov     rcx, rax
0x1800bad50  test    rax, rax
0x1800bad53  jz      short loc_1800BAD73
0x1800bad55  mov     rax, [rax]
0x1800bad58  mov     edx, 7F0h
0x1800bad5d  mov     rax, [rax+8]
0x1800bad61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bad66  test    eax, eax
0x1800bad68  jz      short loc_1800BAD73
0x1800bad6a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bad71  jmp     short loc_1800BAD81
0x1800bad73  lea     rcx, qword_1801B97E0; this
0x1800bad7a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bad81  cmp     [rcx+8], sil
0x1800bad85  jz      short loc_1800BADAC
0x1800bad87  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bad8c  cmp     [rax+7CCh], ebx
0x1800bad92  jz      short loc_1800BADAC
0x1800bad94  mov     r9d, ebx; int
0x1800bad97  lea     rdx, aCopendml102ind; "COpenDML102IndexFactory::CreateOpenDML1"...
0x1800bad9e  mov     r8d, 54h ; 'T'; int
0x1800bada4  mov     rcx, rax; this
0x1800bada7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800badac  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800badb3  jb      loc_1800BB03D
0x1800badb9  mov     edx, 10h
0x1800badbe  jmp     loc_1800BB01F
0x1800badc3  mov     ecx, 30h ; '0'; Size
0x1800badc8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800badcd  test    rax, rax
0x1800badd0  jz      short loc_1800BADFD
0x1800badd2  mov     r8d, [rbx+38h]; unsigned int
0x1800badd6  lea     rcx, [rsp+78h+arg_20]
0x1800badde  mov     [rsp+78h+var_58], rcx; int *
0x1800bade3  mov     r9d, ebp; unsigned int
0x1800bade6  mov     rcx, rax; this
0x1800bade9  mov     rdx, r13; unsigned __int8 *
0x1800badec  call    ??0CODMLStandardIndex@@QEAA@PEBEKKPEAJ@Z; CODMLStandardIndex::CODMLStandardIndex(uchar const *,ulong,ulong,long *)
0x1800badf1  mov     rsi, rax
0x1800badf4  test    rax, rax
0x1800badf7  jnz     loc_1800BAEDC
0x1800badfd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bae04  mov     ebx, 8007000Eh
0x1800bae09  mov     edi, ebx
0x1800bae0b  test    rcx, rcx
0x1800bae0e  jnz     short loc_1800BAE57
0x1800bae10  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bae17  nop     dword ptr [rax+rax+00h]
0x1800bae1c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bae23  mov     rcx, rax
0x1800bae26  test    rax, rax
0x1800bae29  jz      short loc_1800BAE49
0x1800bae2b  mov     rax, [rax]
0x1800bae2e  mov     edx, 7F0h
0x1800bae33  mov     rax, [rax+8]
0x1800bae37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bae3c  test    eax, eax
0x1800bae3e  jz      short loc_1800BAE49
0x1800bae40  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bae47  jmp     short loc_1800BAE57
0x1800bae49  lea     rcx, qword_1801B97E0; this
0x1800bae50  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bae57  cmp     byte ptr [rcx+8], 0
0x1800bae5b  jz      short loc_1800BAE82
0x1800bae5d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bae62  cmp     [rax+7CCh], ebx
0x1800bae68  jz      short loc_1800BAE82
0x1800bae6a  mov     r9d, ebx; int
0x1800bae6d  lea     rdx, aCopendml102ind; "COpenDML102IndexFactory::CreateOpenDML1"...
0x1800bae74  mov     r8d, 50h ; 'P'; int
0x1800bae7a  mov     rcx, rax; this
0x1800bae7d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bae82  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bae89  jb      loc_1800BB03D
0x1800bae8f  mov     edx, 0Fh
0x1800bae94  jmp     loc_1800BB01F
0x1800bae99  mov     ecx, 40h ; '@'; Size
0x1800bae9e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800baea3  test    rax, rax
0x1800baea6  jz      loc_1800BAF8C
0x1800baeac  mov     r8d, [rbx+38h]; unsigned int
0x1800baeb0  lea     rcx, [rsp+78h+arg_20]
0x1800baeb8  mov     [rsp+78h+var_50], rcx; int *
0x1800baebd  mov     r9d, ebp; unsigned int
0x1800baec0  mov     rcx, rax; this
0x1800baec3  mov     [rsp+78h+var_58], r15; struct CAVIFileParser *
0x1800baec8  mov     rdx, r13; unsigned __int8 *
0x1800baecb  call    ??0CODMLSuperIndex@@QEAA@PEBEKKPEAVCAVIFileParser@@PEAJ@Z; CODMLSuperIndex::CODMLSuperIndex(uchar const *,ulong,ulong,CAVIFileParser *,long *)
0x1800baed0  mov     rsi, rax
0x1800baed3  test    rax, rax
0x1800baed6  jz      loc_1800BAF8C
0x1800baedc  mov     edi, dword ptr [rsp+78h+arg_20]
0x1800baee3  test    edi, edi
0x1800baee5  jns     loc_1800BAF84
0x1800baeeb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800baef2  test    rcx, rcx
0x1800baef5  jnz     short loc_1800BAF3E
0x1800baef7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800baefe  nop     dword ptr [rax+rax+00h]
0x1800baf03  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800baf0a  mov     rcx, rax
0x1800baf0d  test    rax, rax
0x1800baf10  jz      short loc_1800BAF30
0x1800baf12  mov     rax, [rax]
0x1800baf15  mov     edx, 7F0h
0x1800baf1a  mov     rax, [rax+8]
0x1800baf1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800baf23  test    eax, eax
0x1800baf25  jz      short loc_1800BAF30
0x1800baf27  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800baf2e  jmp     short loc_1800BAF3E
0x1800baf30  lea     rcx, qword_1801B97E0; this
0x1800baf37  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800baf3e  cmp     byte ptr [rcx+8], 0
0x1800baf42  jz      short loc_1800BAF6D
0x1800baf44  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800baf49  test    edi, edi
0x1800baf4b  jns     short loc_1800BAF6D
0x1800baf4d  cmp     [rax+7CCh], edi
0x1800baf53  jz      short loc_1800BAF6D
0x1800baf55  mov     r9d, edi; int
0x1800baf58  lea     rdx, aCopendml102ind; "COpenDML102IndexFactory::CreateOpenDML1"...
0x1800baf5f  mov     r8d, 56h ; 'V'; int
0x1800baf65  mov     rcx, rax; this
0x1800baf68  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800baf6d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800baf74  jb      loc_1800BB03D
0x1800baf7a  mov     edx, 11h
0x1800baf7f  jmp     loc_1800BAD08
0x1800baf84  mov     [r14], rsi
0x1800baf87  jmp     loc_1800BB03D
0x1800baf8c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800baf93  mov     ebx, 8007000Eh
0x1800baf98  mov     edi, ebx
0x1800baf9a  test    rcx, rcx
0x1800baf9d  jnz     short loc_1800BAFE6
0x1800baf9f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bafa6  nop     dword ptr [rax+rax+00h]
0x1800bafab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bafb2  mov     rcx, rax
0x1800bafb5  test    rax, rax
0x1800bafb8  jz      short loc_1800BAFD8
0x1800bafba  mov     rax, [rax]
0x1800bafbd  mov     edx, 7F0h
0x1800bafc2  mov     rax, [rax+8]
0x1800bafc6  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
