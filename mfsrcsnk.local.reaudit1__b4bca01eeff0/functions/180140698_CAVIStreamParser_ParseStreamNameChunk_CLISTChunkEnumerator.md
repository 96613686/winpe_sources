# CAVIStreamParser::ParseStreamNameChunk(CLISTChunkEnumerator *)

- ea: `0x180140698`
- end: `0x180140a76`
- name: `?ParseStreamNameChunk@CAVIStreamParser@@AEAAJPEAVCLISTChunkEnumerator@@@Z`
- size: `990`
- prototype: `__int64 __fastcall(CAVIStreamParser *__hidden this, struct CLISTChunkEnumerator *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18006d984`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180034ce8`
- `0x180079680`
- `0x180140464`
- `0x180140698`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801406ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014079f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180140849`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801408ee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801409ad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801406ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014079f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180140849`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801408ee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801409ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180140776`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180140776`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180140a4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180140a4a`

## pseudocode

```c
__int64 __fastcall CAVIStreamParser::ParseStreamNameChunk(CAVIStreamParser *this, struct CLISTChunkEnumerator *a2)
{
  __int64 v4; // rdx
  unsigned int v5; // edi
  wchar_t *v6; // rcx
  unsigned __int8 *v7; // rsi
  int Data; // ebx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v11; // rdx
  unsigned __int8 *v12; // rax
  __int64 v13; // rdx
  wchar_t *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  wchar_t *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rax
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  wchar_t *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  char v31; // [rsp+58h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v31, "CAVIStreamParser::ParseStreamNameChunk", 843);
  v5 = *((_DWORD *)a2 + 14);
  if ( !v5 )
  {
    v6 = (wchar_t *)CallStackTracing::s_wpInstance;
    v7 = 0;
    Data = -1072875842;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
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
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875842 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CAVIStreamParser::ParseStreamNameChunk",
          852,
          -1072875842);
    }
    if ( g_wppLevels )
    {
      v11 = 91;
LABEL_12:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        &WPP_84f618ec34f9330309cc271626c14d28_Traceguids,
        this,
        -1072875842);
      goto LABEL_58;
    }
    goto LABEL_58;
  }
  v12 = (unsigned __int8 *)CoTaskMemAlloc(*((unsigned int *)a2 + 14));
  v7 = v12;
  if ( !v12 )
  {
    v14 = (wchar_t *)CallStackTracing::s_wpInstance;
    Data = -2147024882;
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
      v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
      if ( *((_DWORD *)v16 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v16, "CAVIStreamParser::ParseStreamNameChunk", 856, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_58;
    v17 = 92;
    goto LABEL_57;
  }
  Data = ReadData(*((struct CSourcePluginBufferReader **)a2 + 1), v12, v5);
  if ( Data < 0 )
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
        v19 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v19 + 8) )
    {
      v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
      if ( *((_DWORD *)v21 + 499) != Data )
        CallStackContext::TraceFailure(v21, "CAVIStreamParser::ParseStreamNameChunk", 858, Data);
    }
    if ( !g_wppLevels )
      goto LABEL_58;
    v17 = 93;
    goto LABEL_57;
  }
  v22 = v5 - 1;
  if ( !v7[v22] )
  {
    v7[v22] = 0;
    *(_QWORD *)((char *)this + 588) = 0;
    Data = CMFBaseStringT<unsigned short>::Append((char *)this + 584, 65001, v7, 0xFFFFFFFFLL);
    if ( Data >= 0 )
      goto LABEL_58;
    v27 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
      CallStackTracing::s_wpInstance = v28;
      if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
      {
        v27 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v27 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v27 + 8) )
    {
      v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
      if ( *((_DWORD *)v29 + 499) != Data )
        CallStackContext::TraceFailure(v29, "CAVIStreamParser::ParseStreamNameChunk", 873, Data);
    }
    if ( !g_wppLevels )
      goto LABEL_58;
    v17 = 95;
LABEL_57:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_84f618ec34f9330309cc271626c14d28_Traceguids, this, Data);
    goto LABEL_58;
  }
  v23 = (wchar_t *)CallStackTracing::s_wpInstance;
  Data = -1072875842;
  if ( !CallStackTracing::s_wpInstance )
  {
    v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
    CallStackTracing::s_wpInstance = v24;
    if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
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
    v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
    if ( *((_DWORD *)v25 + 499) != -1072875842 )
      CallStackContext::TraceFailure(v25, "CAVIStreamParser::ParseStreamNameChunk", 865, -1072875842);
  }
  if ( g_wppLevels )
  {
    v11 = 94;
    goto LABEL_12;
  }
LABEL_58:
  CoTaskMemFree(v7);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v31);
  return (unsigned int)Data;
}

```

## disassembly

```asm
0x180140698  mov     [rsp+arg_0], rbx
0x18014069d  mov     [rsp+arg_10], rbp
0x1801406a2  push    rsi
0x1801406a3  push    rdi
0x1801406a4  push    r15
0x1801406a6  sub     rsp, 30h
0x1801406aa  mov     rbx, rdx
0x1801406ad  lea     r15, aCavistreampars_3; "CAVIStreamParser::ParseStreamNameChunk"
0x1801406b4  mov     rbp, rcx
0x1801406b7  mov     rdx, r15; char *
0x1801406ba  mov     r8d, 34Bh; int
0x1801406c0  lea     rcx, [rsp+48h+arg_8]; this
0x1801406c5  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801406ca  mov     edi, [rbx+38h]
0x1801406cd  test    edi, edi
0x1801406cf  jnz     loc_180140773
0x1801406d5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801406dc  xor     esi, esi
0x1801406de  mov     edi, 0C00D36BEh
0x1801406e3  mov     ebx, edi
0x1801406e5  test    rcx, rcx
0x1801406e8  jnz     short loc_180140731
0x1801406ea  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801406f1  nop     dword ptr [rax+rax+00h]
0x1801406f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801406fd  mov     rcx, rax
0x180140700  test    rax, rax
0x180140703  jz      short loc_180140723
0x180140705  mov     rax, [rax]
0x180140708  mov     edx, 7F0h
0x18014070d  mov     rax, [rax+8]
0x180140711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180140716  test    eax, eax
0x180140718  jz      short loc_180140723
0x18014071a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180140721  jmp     short loc_180140731
0x180140723  lea     rcx, qword_1801B97E0; this
0x18014072a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180140731  cmp     [rcx+8], sil
0x180140735  jz      short loc_180140758
0x180140737  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014073c  cmp     [rax+7CCh], edi
0x180140742  jz      short loc_180140758
0x180140744  mov     r9d, edi; int
0x180140747  mov     r8d, 354h; int
0x18014074d  mov     rdx, r15; char *
0x180140750  mov     rcx, rax; this
0x180140753  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180140758  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18014075f  jb      loc_180140A47
0x180140765  mov     edx, 5Bh ; '['
0x18014076a  mov     [rsp+48h+var_28], edi
0x18014076e  jmp     loc_180140A2D
0x180140773  mov     rcx, rdi; cb
0x180140776  call    cs:__imp_CoTaskMemAlloc
0x18014077d  nop     dword ptr [rax+rax+00h]
0x180140782  mov     rsi, rax
0x180140785  test    rax, rax
0x180140788  jnz     loc_180140824
0x18014078e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180140795  mov     ebx, 8007000Eh
0x18014079a  test    rcx, rcx
0x18014079d  jnz     short loc_1801407E6
0x18014079f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801407a6  nop     dword ptr [rax+rax+00h]
0x1801407ab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801407b2  mov     rcx, rax
0x1801407b5  test    rax, rax
0x1801407b8  jz      short loc_1801407D8
0x1801407ba  mov     rax, [rax]
0x1801407bd  mov     edx, 7F0h
0x1801407c2  mov     rax, [rax+8]
0x1801407c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801407cb  test    eax, eax
0x1801407cd  jz      short loc_1801407D8
0x1801407cf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801407d6  jmp     short loc_1801407E6
0x1801407d8  lea     rcx, qword_1801B97E0; this
0x1801407df  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801407e6  cmp     byte ptr [rcx+8], 0
0x1801407ea  jz      short loc_18014080D
0x1801407ec  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801407f1  cmp     [rax+7CCh], ebx
0x1801407f7  jz      short loc_18014080D
0x1801407f9  mov     r9d, ebx; int
0x1801407fc  mov     r8d, 358h; int
0x180140802  mov     rdx, r15; char *
0x180140805  mov     rcx, rax; this
0x180140808  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18014080d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180140814  jb      loc_180140A47
0x18014081a  mov     edx, 5Ch ; '\'
0x18014081f  jmp     loc_180140A29
0x180140824  mov     rcx, [rbx+8]; struct CSourcePluginBufferReader *
0x180140828  mov     r8d, edi; unsigned int
0x18014082b  mov     rdx, rsi; unsigned __int8 *
0x18014082e  call    ?ReadData@@YAJPEAVCSourcePluginBufferReader@@PEAEK@Z; ReadData(CSourcePluginBufferReader *,uchar *,ulong)
0x180140833  mov     ebx, eax
0x180140835  test    eax, eax
0x180140837  jns     loc_1801408CE
0x18014083d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180140844  test    rcx, rcx
0x180140847  jnz     short loc_180140890
0x180140849  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180140850  nop     dword ptr [rax+rax+00h]
0x180140855  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18014085c  mov     rcx, rax
0x18014085f  test    rax, rax
0x180140862  jz      short loc_180140882
0x180140864  mov     rax, [rax]
0x180140867  mov     edx, 7F0h
0x18014086c  mov     rax, [rax+8]
0x180140870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180140875  test    eax, eax
0x180140877  jz      short loc_180140882
0x180140879  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180140880  jmp     short loc_180140890
0x180140882  lea     rcx, qword_1801B97E0; this
0x180140889  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180140890  cmp     byte ptr [rcx+8], 0
0x180140894  jz      short loc_1801408B7
0x180140896  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014089b  cmp     [rax+7CCh], ebx
0x1801408a1  jz      short loc_1801408B7
0x1801408a3  mov     r9d, ebx; int
0x1801408a6  mov     r8d, 35Ah; int
0x1801408ac  mov     rdx, r15; char *
0x1801408af  mov     rcx, rax; this
0x1801408b2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801408b7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801408be  jb      loc_180140A47
0x1801408c4  mov     edx, 5Dh ; ']'
0x1801408c9  jmp     loc_180140A29
0x1801408ce  lea     eax, [rdi-1]
0x1801408d1  cmp     byte ptr [rax+rsi], 0
0x1801408d5  jz      loc_180140973
0x1801408db  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801408e2  mov     edi, 0C00D36BEh
0x1801408e7  mov     ebx, edi
0x1801408e9  test    rcx, rcx
0x1801408ec  jnz     short loc_180140935
0x1801408ee  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801408f5  nop     dword ptr [rax+rax+00h]
0x1801408fa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180140901  mov     rcx, rax
0x180140904  test    rax, rax
0x180140907  jz      short loc_180140927
0x180140909  mov     rax, [rax]
0x18014090c  mov     edx, 7F0h
0x180140911  mov     rax, [rax+8]
0x180140915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014091a  test    eax, eax
0x18014091c  jz      short loc_180140927
0x18014091e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180140925  jmp     short loc_180140935
0x180140927  lea     rcx, qword_1801B97E0; this
0x18014092e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180140935  cmp     byte ptr [rcx+8], 0
0x180140939  jz      short loc_18014095C
0x18014093b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180140940  cmp     [rax+7CCh], edi
0x180140946  jz      short loc_18014095C
0x180140948  mov     r9d, edi; int
0x18014094b  mov     r8d, 361h; int
0x180140951  mov     rdx, r15; char *
0x180140954  mov     rcx, rax; this
0x180140957  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18014095c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180140963  jb      loc_180140A47
0x180140969  mov     edx, 5Eh ; '^'
0x18014096e  jmp     loc_18014076A
0x180140973  lea     rcx, [rbp+248h]
0x18014097a  mov     byte ptr [rax+rsi], 0
0x18014097e  or      r9d, 0FFFFFFFFh
0x180140982  mov     qword ptr [rcx+4], 0
0x18014098a  mov     r8, rsi
0x18014098d  mov     edx, 0FDE9h
0x180140992  call    ?Append@?$CMFBaseStringT@G@@QEAAJIPEBDJ@Z; CMFBaseStringT<ushort>::Append(uint,char const *,long)
0x180140997  mov     ebx, eax
0x180140999  test    eax, eax
0x18014099b  jns     loc_180140A47
0x1801409a1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801409a8  test    rcx, rcx
0x1801409ab  jnz     short loc_1801409F4
0x1801409ad  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801409b4  nop     dword ptr [rax+rax+00h]
0x1801409b9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801409c0  mov     rcx, rax
0x1801409c3  test    rax, rax
0x1801409c6  jz      short loc_1801409E6
0x1801409c8  mov     rax, [rax]
0x1801409cb  mov     edx, 7F0h
0x1801409d0  mov     rax, [rax+8]
0x1801409d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801409d9  test    eax, eax
0x1801409db  jz      short loc_1801409E6
0x1801409dd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801409e4  jmp     short loc_1801409F4
0x1801409e6  lea     rcx, qword_1801B97E0; this
0x1801409ed  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801409f4  cmp     byte ptr [rcx+8], 0
0x1801409f8  jz      short loc_180140A1B
0x1801409fa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801409ff  cmp     [rax+7CCh], ebx
0x180140a05  jz      short loc_180140A1B
0x180140a07  mov     r9d, ebx; int
0x180140a0a  mov     r8d, 369h; int
0x180140a10  mov     rdx, r15; char *
0x180140a13  mov     rcx, rax; this
0x180140a16  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180140a1b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180140a22  jb      short loc_180140A47
0x180140a24  mov     edx, 5Fh ; '_'
0x180140a29  mov     [rsp+48h+var_28], ebx
0x180140a2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180140a34  lea     r8, WPP_84f618ec34f9330309cc271626c14d28_Traceguids
0x180140a3b  mov     r9, rbp
0x180140a3e  mov     rcx, [rcx+10h]
0x180140a42  call    WPP_SF_qD
0x180140a47  mov     rcx, rsi; pv
0x180140a4a  call    cs:__imp_CoTaskMemFree
0x180140a51  nop     dword ptr [rax+rax+00h]
0x180140a56  lea     rcx, [rsp+48h+arg_8]; this
0x180140a5b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180140a60  mov     rbp, [rsp+48h+arg_10]
0x180140a65  mov     eax, ebx
0x180140a67  mov     rbx, [rsp+48h+arg_0]
0x180140a6c  add     rsp, 30h
0x180140a70  pop     r15
0x180140a72  pop     rdi
0x180140a73  pop     rsi
0x180140a74  retn
```
