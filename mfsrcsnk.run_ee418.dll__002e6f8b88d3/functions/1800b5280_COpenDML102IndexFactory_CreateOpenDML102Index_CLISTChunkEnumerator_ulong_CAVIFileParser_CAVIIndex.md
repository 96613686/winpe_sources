# COpenDML102IndexFactory::CreateOpenDML102Index(CLISTChunkEnumerator *,ulong,CAVIFileParser *,CAVIIndex * *)

- ea: `0x1800b5280`
- end: `0x1800b581b`
- name: `?CreateOpenDML102Index@COpenDML102IndexFactory@@QEAAJPEAVCLISTChunkEnumerator@@KPEAVCAVIFileParser@@PEAPEAVCAVIIndex@@@Z`
- size: `1435`
- prototype: `__int64 __fastcall(COpenDML102IndexFactory *this, struct CLISTChunkEnumerator *, unsigned int, struct CAVIFileParser *, struct CAVIIndex **)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting`

## callers

- `0x180034fc4`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x1800370c4`
- `0x180073b14`
- `0x18009cfd4`
- `0x1800a4fb8`
- `0x1800b5280`
- `0x180109590`
- `0x1801095a8`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b52e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b538c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b543c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b54ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b55bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b569d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b573f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b52e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b538c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b543c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b54ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b55bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b569d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b573f`

## string_xrefs

- `0x1800b529c`: `COpenDML102IndexFactory::CreateOpenDML102Index`
- `0x1800b5339`: `COpenDML102IndexFactory::CreateOpenDML102Index`
- `0x1800b53e3`: `COpenDML102IndexFactory::CreateOpenDML102Index`
- `0x1800b5493`: `COpenDML102IndexFactory::CreateOpenDML102Index`
- `0x1800b5543`: `COpenDML102IndexFactory::CreateOpenDML102Index`
- `0x1800b5613`: `COpenDML102IndexFactory::CreateOpenDML102Index`
- `0x1800b56f8`: `COpenDML102IndexFactory::CreateOpenDML102Index`
- `0x1800b5796`: `COpenDML102IndexFactory::CreateOpenDML102Index`

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
  __int64 v10; // r8
  __int64 v11; // r9
  struct CAVIIndex **v12; // r14
  CODMLSuperIndex *v13; // rsi
  wchar_t *v14; // rcx
  unsigned __int8 *v15; // r13
  int v16; // ebx
  int v17; // edi
  CallStackTracing *v18; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v20; // rdx
  unsigned __int8 *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  wchar_t *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  wchar_t *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  CODMLStandardIndex *v38; // rax
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  wchar_t *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  CODMLSuperIndex *v45; // rax
  wchar_t *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  wchar_t *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  char v53; // [rsp+80h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v53,
    "COpenDML102IndexFactory::CreateOpenDML102Index",
    40);
  v12 = a5;
  v13 = 0;
  *a5 = 0;
  if ( *((_DWORD *)a2 + 14) < 0x18u )
  {
    v14 = (wchar_t *)CallStackTracing::s_wpInstance;
    v15 = 0;
    v16 = -1072875842;
    v17 = -1072875842;
    if ( !CallStackTracing::s_wpInstance )
    {
      v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v10, v11);
      CallStackTracing::s_wpInstance = v18;
      if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
      {
        v14 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v14 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v14 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875842 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "COpenDML102IndexFactory::CreateOpenDML102Index",
          55,
          -1072875842);
    }
    if ( g_wppLevels )
    {
      v20 = 11;
LABEL_84:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, &WPP_8c8e1fda19d530912db1a52be9331974_Traceguids, this, v16);
      goto LABEL_85;
    }
    goto LABEL_85;
  }
  v21 = (unsigned __int8 *)operator new(*((unsigned int *)a2 + 14));
  v15 = v21;
  if ( !v21 )
  {
    v25 = (wchar_t *)CallStackTracing::s_wpInstance;
    v16 = -2147024882;
    v17 = -2147024882;
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
      v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
      if ( *((_DWORD *)v27 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v27, "COpenDML102IndexFactory::CreateOpenDML102Index", 59, -2147024882);
    }
    if ( g_wppLevels )
    {
      v20 = 12;
      goto LABEL_84;
    }
    goto LABEL_85;
  }
  LODWORD(a5) = ReadData(*((struct CSourcePluginBufferReader **)a2 + 1), v21, *((_DWORD *)a2 + 14));
  v17 = (int)a5;
  if ( (int)a5 < 0 )
  {
    v31 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v29, v30);
      CallStackTracing::s_wpInstance = v32;
      if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
      {
        v31 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v31 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v31 + 8) )
    {
      v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
      if ( *((_DWORD *)v33 + 499) != v17 )
        CallStackContext::TraceFailure(v33, "COpenDML102IndexFactory::CreateOpenDML102Index", 60, v17);
    }
    if ( !g_wppLevels )
      goto LABEL_85;
    v34 = 13;
LABEL_34:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v34, &WPP_8c8e1fda19d530912db1a52be9331974_Traceguids, this, v17);
    goto LABEL_85;
  }
  if ( v15[3] )
  {
    if ( v15[3] != 1 )
    {
      v35 = (wchar_t *)CallStackTracing::s_wpInstance;
      v16 = -1072875842;
      v17 = -1072875842;
      if ( !CallStackTracing::s_wpInstance )
      {
        v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v29, v30);
        CallStackTracing::s_wpInstance = v36;
        if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
        {
          v35 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v35 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v35 + 8) )
      {
        v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
        if ( *((_DWORD *)v37 + 499) != -1072875842 )
          CallStackContext::TraceFailure(v37, "COpenDML102IndexFactory::CreateOpenDML102Index", 84, -1072875842);
      }
      if ( g_wppLevels )
      {
        v20 = 16;
        goto LABEL_84;
      }
      goto LABEL_85;
    }
    v38 = (CODMLStandardIndex *)operator new(0x30u);
    if ( !v38 || (v13 = CODMLStandardIndex::CODMLStandardIndex(v38, v15, *((_DWORD *)a2 + 14), a3, (int *)&a5)) == 0 )
    {
      v42 = (wchar_t *)CallStackTracing::s_wpInstance;
      v16 = -2147024882;
      v17 = -2147024882;
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
        if ( *((_DWORD *)v44 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v44, "COpenDML102IndexFactory::CreateOpenDML102Index", 80, -2147024882);
      }
      if ( g_wppLevels )
      {
        v20 = 15;
        goto LABEL_84;
      }
      goto LABEL_85;
    }
  }
  else
  {
    v45 = (CODMLSuperIndex *)operator new(0x40u);
    if ( !v45 || (v13 = CODMLSuperIndex::CODMLSuperIndex(v45, v15, *((_DWORD *)a2 + 14), a3, a4, (int *)&a5)) == 0 )
    {
      v49 = (wchar_t *)CallStackTracing::s_wpInstance;
      v16 = -2147024882;
      v17 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39, v40, v41);
        CallStackTracing::s_wpInstance = v50;
        if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
        {
          v49 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v49 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v49 + 8) )
      {
        v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
        if ( *((_DWORD *)v51 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v51, "COpenDML102IndexFactory::CreateOpenDML102Index", 72, -2147024882);
      }
      if ( g_wppLevels )
      {
        v20 = 14;
        goto LABEL_84;
      }
      goto LABEL_85;
    }
  }
  v17 = (int)a5;
  if ( (int)a5 >= 0 )
  {
    *v12 = v13;
    goto LABEL_85;
  }
  v46 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39, v40, v41);
    CallStackTracing::s_wpInstance = v47;
    if ( v47 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
    {
      v46 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v46 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v46 + 8) )
  {
    v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
    if ( v17 < 0 && *((_DWORD *)v48 + 499) != v17 )
      CallStackContext::TraceFailure(v48, "COpenDML102IndexFactory::CreateOpenDML102Index", 86, v17);
  }
  if ( g_wppLevels )
  {
    v34 = 17;
    goto LABEL_34;
  }
LABEL_85:
  operator delete(v15);
  if ( v17 < 0 && v13 )
    (**(void (__fastcall ***)(CODMLSuperIndex *, __int64))v13)(v13, 1);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v53);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800b5280  mov     rax, rsp
0x1800b5283  push    rbx
0x1800b5284  push    rbp
0x1800b5285  push    rsi
0x1800b5286  push    rdi
0x1800b5287  push    r12
0x1800b5289  push    r13
0x1800b528b  push    r14
0x1800b528d  push    r15
0x1800b528f  sub     rsp, 38h
0x1800b5293  mov     ebp, r8d
0x1800b5296  mov     rbx, rdx
0x1800b5299  mov     r12, rcx
0x1800b529c  lea     rdx, aCopendml102ind; "COpenDML102IndexFactory::CreateOpenDML1"...
0x1800b52a3  mov     r8d, 28h ; '('; int
0x1800b52a9  lea     rcx, [rax+8]; this
0x1800b52ad  mov     r15, r9
0x1800b52b0  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b52b5  mov     r14, [rsp+78h+arg_20]
0x1800b52bd  xor     esi, esi
0x1800b52bf  mov     [r14], rsi
0x1800b52c2  cmp     dword ptr [rbx+38h], 18h
0x1800b52c6  jnb     loc_1800B5365
0x1800b52cc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b52d3  xor     r13d, r13d
0x1800b52d6  mov     ebx, 0C00D36BEh
0x1800b52db  mov     edi, ebx
0x1800b52dd  test    rcx, rcx
0x1800b52e0  jnz     short loc_1800B5323
0x1800b52e2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b52e8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b52ef  mov     rcx, rax
0x1800b52f2  test    rax, rax
0x1800b52f5  jz      short loc_1800B5315
0x1800b52f7  mov     rax, [rax]
0x1800b52fa  mov     edx, 7F0h
0x1800b52ff  mov     rax, [rax+8]
0x1800b5303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5308  test    eax, eax
0x1800b530a  jz      short loc_1800B5315
0x1800b530c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5313  jmp     short loc_1800B5323
0x1800b5315  lea     rcx, qword_1801B07E0; this
0x1800b531c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5323  cmp     [rcx+8], sil
0x1800b5327  jz      short loc_1800B534E
0x1800b5329  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b532e  cmp     [rax+7CCh], ebx
0x1800b5334  jz      short loc_1800B534E
0x1800b5336  mov     r9d, ebx; int
0x1800b5339  lea     rdx, aCopendml102ind; "COpenDML102IndexFactory::CreateOpenDML1"...
0x1800b5340  mov     r8d, 37h ; '7'; int
0x1800b5346  mov     rcx, rax; this
0x1800b5349  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b534e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b5355  jb      loc_1800B57D7
0x1800b535b  mov     edx, 0Bh
0x1800b5360  jmp     loc_1800B57B9
0x1800b5365  mov     ecx, [rbx+38h]; Size
0x1800b5368  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b536d  mov     r13, rax
0x1800b5370  test    rax, rax
0x1800b5373  jnz     loc_1800B540F
0x1800b5379  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5380  mov     ebx, 8007000Eh
0x1800b5385  mov     edi, ebx
0x1800b5387  test    rcx, rcx
0x1800b538a  jnz     short loc_1800B53CD
0x1800b538c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b5392  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5399  mov     rcx, rax
0x1800b539c  test    rax, rax
0x1800b539f  jz      short loc_1800B53BF
0x1800b53a1  mov     rax, [rax]
0x1800b53a4  mov     edx, 7F0h
0x1800b53a9  mov     rax, [rax+8]
0x1800b53ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b53b2  test    eax, eax
0x1800b53b4  jz      short loc_1800B53BF
0x1800b53b6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b53bd  jmp     short loc_1800B53CD
0x1800b53bf  lea     rcx, qword_1801B07E0; this
0x1800b53c6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b53cd  cmp     [rcx+8], sil
0x1800b53d1  jz      short loc_1800B53F8
0x1800b53d3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b53d8  cmp     [rax+7CCh], ebx
0x1800b53de  jz      short loc_1800B53F8
0x1800b53e0  mov     r9d, ebx; int
0x1800b53e3  lea     rdx, aCopendml102ind; "COpenDML102IndexFactory::CreateOpenDML1"...
0x1800b53ea  mov     r8d, 3Bh ; ';'; int
0x1800b53f0  mov     rcx, rax; this
0x1800b53f3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b53f8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b53ff  jb      loc_1800B57D7
0x1800b5405  mov     edx, 0Ch
0x1800b540a  jmp     loc_1800B57B9
0x1800b540f  mov     r8d, [rbx+38h]; unsigned int
0x1800b5413  mov     rdx, r13; unsigned __int8 *
0x1800b5416  mov     rcx, [rbx+8]; struct CSourcePluginBufferReader *
0x1800b541a  call    ?ReadData@@YAJPEAVCSourcePluginBufferReader@@PEAEK@Z; ReadData(CSourcePluginBufferReader *,uchar *,ulong)
0x1800b541f  mov     dword ptr [rsp+78h+arg_20], eax
0x1800b5426  mov     edi, eax
0x1800b5428  test    eax, eax
0x1800b542a  jns     loc_1800B54C3
0x1800b5430  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5437  test    rcx, rcx
0x1800b543a  jnz     short loc_1800B547D
0x1800b543c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b5442  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5449  mov     rcx, rax
0x1800b544c  test    rax, rax
0x1800b544f  jz      short loc_1800B546F
0x1800b5451  mov     rax, [rax]
0x1800b5454  mov     edx, 7F0h
0x1800b5459  mov     rax, [rax+8]
0x1800b545d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5462  test    eax, eax
0x1800b5464  jz      short loc_1800B546F
0x1800b5466  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b546d  jmp     short loc_1800B547D
0x1800b546f  lea     rcx, qword_1801B07E0; this
0x1800b5476  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b547d  cmp     [rcx+8], sil
0x1800b5481  jz      short loc_1800B54A8
0x1800b5483  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b5488  cmp     [rax+7CCh], edi
0x1800b548e  jz      short loc_1800B54A8
0x1800b5490  mov     r9d, edi; int
0x1800b5493  lea     rdx, aCopendml102ind; "COpenDML102IndexFactory::CreateOpenDML1"...
0x1800b549a  mov     r8d, 3Ch ; '<'; int
0x1800b54a0  mov     rcx, rax; this
0x1800b54a3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b54a8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b54af  jb      loc_1800B57D7
0x1800b54b5  mov     edx, 0Dh
0x1800b54ba  mov     dword ptr [rsp+78h+var_58], edi
0x1800b54be  jmp     loc_1800B57BD
0x1800b54c3  movzx   ecx, byte ptr [r13+3]
0x1800b54c8  test    ecx, ecx
0x1800b54ca  jz      loc_1800B563F
0x1800b54d0  cmp     ecx, 1
0x1800b54d3  jz      loc_1800B556F
0x1800b54d9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b54e0  mov     ebx, 0C00D36BEh
0x1800b54e5  mov     edi, ebx
0x1800b54e7  test    rcx, rcx
0x1800b54ea  jnz     short loc_1800B552D
0x1800b54ec  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b54f2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b54f9  mov     rcx, rax
0x1800b54fc  test    rax, rax
0x1800b54ff  jz      short loc_1800B551F
0x1800b5501  mov     rax, [rax]
0x1800b5504  mov     edx, 7F0h
0x1800b5509  mov     rax, [rax+8]
0x1800b550d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5512  test    eax, eax
0x1800b5514  jz      short loc_1800B551F
0x1800b5516  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b551d  jmp     short loc_1800B552D
0x1800b551f  lea     rcx, qword_1801B07E0; this
0x1800b5526  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b552d  cmp     [rcx+8], sil
0x1800b5531  jz      short loc_1800B5558
0x1800b5533  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b5538  cmp     [rax+7CCh], ebx
0x1800b553e  jz      short loc_1800B5558
0x1800b5540  mov     r9d, ebx; int
0x1800b5543  lea     rdx, aCopendml102ind; "COpenDML102IndexFactory::CreateOpenDML1"...
0x1800b554a  mov     r8d, 54h ; 'T'; int
0x1800b5550  mov     rcx, rax; this
0x1800b5553  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b5558  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b555f  jb      loc_1800B57D7
0x1800b5565  mov     edx, 10h
0x1800b556a  jmp     loc_1800B57B9
0x1800b556f  mov     ecx, 30h ; '0'; Size
0x1800b5574  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b5579  test    rax, rax
0x1800b557c  jz      short loc_1800B55A9
0x1800b557e  mov     r8d, [rbx+38h]; unsigned int
0x1800b5582  lea     rcx, [rsp+78h+arg_20]
0x1800b558a  mov     [rsp+78h+var_58], rcx; int *
0x1800b558f  mov     r9d, ebp; unsigned int
0x1800b5592  mov     rcx, rax; this
0x1800b5595  mov     rdx, r13; unsigned __int8 *
0x1800b5598  call    ??0CODMLStandardIndex@@QEAA@PEBEKKPEAJ@Z; CODMLStandardIndex::CODMLStandardIndex(uchar const *,ulong,ulong,long *)
0x1800b559d  mov     rsi, rax
0x1800b55a0  test    rax, rax
0x1800b55a3  jnz     loc_1800B5682
0x1800b55a9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b55b0  mov     ebx, 8007000Eh
0x1800b55b5  mov     edi, ebx
0x1800b55b7  test    rcx, rcx
0x1800b55ba  jnz     short loc_1800B55FD
0x1800b55bc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b55c2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b55c9  mov     rcx, rax
0x1800b55cc  test    rax, rax
0x1800b55cf  jz      short loc_1800B55EF
0x1800b55d1  mov     rax, [rax]
0x1800b55d4  mov     edx, 7F0h
0x1800b55d9  mov     rax, [rax+8]
0x1800b55dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b55e2  test    eax, eax
0x1800b55e4  jz      short loc_1800B55EF
0x1800b55e6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b55ed  jmp     short loc_1800B55FD
0x1800b55ef  lea     rcx, qword_1801B07E0; this
0x1800b55f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b55fd  cmp     byte ptr [rcx+8], 0
0x1800b5601  jz      short loc_1800B5628
0x1800b5603  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b5608  cmp     [rax+7CCh], ebx
0x1800b560e  jz      short loc_1800B5628
0x1800b5610  mov     r9d, ebx; int
0x1800b5613  lea     rdx, aCopendml102ind; "COpenDML102IndexFactory::CreateOpenDML1"...
0x1800b561a  mov     r8d, 50h ; 'P'; int
0x1800b5620  mov     rcx, rax; this
0x1800b5623  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b5628  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b562f  jb      loc_1800B57D7
0x1800b5635  mov     edx, 0Fh
0x1800b563a  jmp     loc_1800B57B9
0x1800b563f  mov     ecx, 40h ; '@'; Size
0x1800b5644  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b5649  test    rax, rax
0x1800b564c  jz      loc_1800B572C
0x1800b5652  mov     r8d, [rbx+38h]; unsigned int
0x1800b5656  lea     rcx, [rsp+78h+arg_20]
0x1800b565e  mov     [rsp+78h+var_50], rcx; int *
0x1800b5663  mov     r9d, ebp; unsigned int
0x1800b5666  mov     rcx, rax; this
0x1800b5669  mov     [rsp+78h+var_58], r15; struct CAVIFileParser *
0x1800b566e  mov     rdx, r13; unsigned __int8 *
0x1800b5671  call    ??0CODMLSuperIndex@@QEAA@PEBEKKPEAVCAVIFileParser@@PEAJ@Z; CODMLSuperIndex::CODMLSuperIndex(uchar const *,ulong,ulong,CAVIFileParser *,long *)
0x1800b5676  mov     rsi, rax
0x1800b5679  test    rax, rax
0x1800b567c  jz      loc_1800B572C
0x1800b5682  mov     edi, dword ptr [rsp+78h+arg_20]
0x1800b5689  test    edi, edi
0x1800b568b  jns     loc_1800B5724
0x1800b5691  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5698  test    rcx, rcx
0x1800b569b  jnz     short loc_1800B56DE
0x1800b569d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b56a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b56aa  mov     rcx, rax
0x1800b56ad  test    rax, rax
0x1800b56b0  jz      short loc_1800B56D0
0x1800b56b2  mov     rax, [rax]
0x1800b56b5  mov     edx, 7F0h
0x1800b56ba  mov     rax, [rax+8]
0x1800b56be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b56c3  test    eax, eax
0x1800b56c5  jz      short loc_1800B56D0
0x1800b56c7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b56ce  jmp     short loc_1800B56DE
0x1800b56d0  lea     rcx, qword_1801B07E0; this
0x1800b56d7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b56de  cmp     byte ptr [rcx+8], 0
0x1800b56e2  jz      short loc_1800B570D
0x1800b56e4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b56e9  test    edi, edi
0x1800b56eb  jns     short loc_1800B570D
0x1800b56ed  cmp     [rax+7CCh], edi
0x1800b56f3  jz      short loc_1800B570D
0x1800b56f5  mov     r9d, edi; int
0x1800b56f8  lea     rdx, aCopendml102ind; "COpenDML102IndexFactory::CreateOpenDML1"...
0x1800b56ff  mov     r8d, 56h ; 'V'; int
0x1800b5705  mov     rcx, rax; this
0x1800b5708  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b570d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b5714  jb      loc_1800B57D7
0x1800b571a  mov     edx, 11h
0x1800b571f  jmp     loc_1800B54BA
0x1800b5724  mov     [r14], rsi
0x1800b5727  jmp     loc_1800B57D7
0x1800b572c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5733  mov     ebx, 8007000Eh
0x1800b5738  mov     edi, ebx
0x1800b573a  test    rcx, rcx
0x1800b573d  jnz     short loc_1800B5780
0x1800b573f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b5745  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b574c  mov     rcx, rax
0x1800b574f  test    rax, rax
0x1800b5752  jz      short loc_1800B5772
0x1800b5754  mov     rax, [rax]
0x1800b5757  mov     edx, 7F0h
0x1800b575c  mov     rax, [rax+8]
0x1800b5760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5765  test    eax, eax
0x1800b5767  jz      short loc_1800B5772
0x1800b5769  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5770  jmp     short loc_1800B5780
0x1800b5772  lea     rcx, qword_1801B07E0; this
0x1800b5779  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b5780  cmp     byte ptr [rcx+8], 0
  ... truncated ...
```
