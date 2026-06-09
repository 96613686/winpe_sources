# CAVIStreamParser::ParseStreamNameChunk(CLISTChunkEnumerator *)

- ea: `0x180138d88`
- end: `0x18013913b`
- name: `?ParseStreamNameChunk@CAVIStreamParser@@AEAAJPEAVCLISTChunkEnumerator@@@Z`
- size: `947`
- prototype: `__int64 __fastcall(CAVIStreamParser *__hidden this, struct CLISTChunkEnumerator *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180034fc4`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x1800370c4`
- `0x180073b14`
- `0x180138b60`
- `0x180138d88`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180138dda`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180138e83`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180138f27`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180138fc6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013907f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180138dda`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180138e83`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180138f27`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180138fc6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013907f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180138e60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180138e60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180139116`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180139116`

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
        v6 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v14 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v19 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v27 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
      v23 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
0x180138d88  mov     [rsp+arg_0], rbx
0x180138d8d  mov     [rsp+arg_10], rbp
0x180138d92  push    rsi
0x180138d93  push    rdi
0x180138d94  push    r15
0x180138d96  sub     rsp, 30h
0x180138d9a  mov     rbx, rdx
0x180138d9d  lea     r15, aCavistreampars_3; "CAVIStreamParser::ParseStreamNameChunk"
0x180138da4  mov     rbp, rcx
0x180138da7  mov     rdx, r15; char *
0x180138daa  mov     r8d, 34Bh; int
0x180138db0  lea     rcx, [rsp+48h+arg_8]; this
0x180138db5  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180138dba  mov     edi, [rbx+38h]
0x180138dbd  test    edi, edi
0x180138dbf  jnz     loc_180138E5D
0x180138dc5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180138dcc  xor     esi, esi
0x180138dce  mov     edi, 0C00D36BEh
0x180138dd3  mov     ebx, edi
0x180138dd5  test    rcx, rcx
0x180138dd8  jnz     short loc_180138E1B
0x180138dda  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180138de0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180138de7  mov     rcx, rax
0x180138dea  test    rax, rax
0x180138ded  jz      short loc_180138E0D
0x180138def  mov     rax, [rax]
0x180138df2  mov     edx, 7F0h
0x180138df7  mov     rax, [rax+8]
0x180138dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180138e00  test    eax, eax
0x180138e02  jz      short loc_180138E0D
0x180138e04  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180138e0b  jmp     short loc_180138E1B
0x180138e0d  lea     rcx, qword_1801B07E0; this
0x180138e14  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180138e1b  cmp     [rcx+8], sil
0x180138e1f  jz      short loc_180138E42
0x180138e21  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180138e26  cmp     [rax+7CCh], edi
0x180138e2c  jz      short loc_180138E42
0x180138e2e  mov     r9d, edi; int
0x180138e31  mov     r8d, 354h; int
0x180138e37  mov     rdx, r15; char *
0x180138e3a  mov     rcx, rax; this
0x180138e3d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180138e42  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180138e49  jb      loc_180139113
0x180138e4f  mov     edx, 5Bh ; '['
0x180138e54  mov     [rsp+48h+var_28], edi
0x180138e58  jmp     loc_1801390F9
0x180138e5d  mov     rcx, rdi; cb
0x180138e60  call    cs:__imp_CoTaskMemAlloc
0x180138e66  mov     rsi, rax
0x180138e69  test    rax, rax
0x180138e6c  jnz     loc_180138F02
0x180138e72  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180138e79  mov     ebx, 8007000Eh
0x180138e7e  test    rcx, rcx
0x180138e81  jnz     short loc_180138EC4
0x180138e83  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180138e89  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180138e90  mov     rcx, rax
0x180138e93  test    rax, rax
0x180138e96  jz      short loc_180138EB6
0x180138e98  mov     rax, [rax]
0x180138e9b  mov     edx, 7F0h
0x180138ea0  mov     rax, [rax+8]
0x180138ea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180138ea9  test    eax, eax
0x180138eab  jz      short loc_180138EB6
0x180138ead  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180138eb4  jmp     short loc_180138EC4
0x180138eb6  lea     rcx, qword_1801B07E0; this
0x180138ebd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180138ec4  cmp     byte ptr [rcx+8], 0
0x180138ec8  jz      short loc_180138EEB
0x180138eca  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180138ecf  cmp     [rax+7CCh], ebx
0x180138ed5  jz      short loc_180138EEB
0x180138ed7  mov     r9d, ebx; int
0x180138eda  mov     r8d, 358h; int
0x180138ee0  mov     rdx, r15; char *
0x180138ee3  mov     rcx, rax; this
0x180138ee6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180138eeb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180138ef2  jb      loc_180139113
0x180138ef8  mov     edx, 5Ch ; '\'
0x180138efd  jmp     loc_1801390F5
0x180138f02  mov     rcx, [rbx+8]; struct CSourcePluginBufferReader *
0x180138f06  mov     r8d, edi; unsigned int
0x180138f09  mov     rdx, rsi; unsigned __int8 *
0x180138f0c  call    ?ReadData@@YAJPEAVCSourcePluginBufferReader@@PEAEK@Z; ReadData(CSourcePluginBufferReader *,uchar *,ulong)
0x180138f11  mov     ebx, eax
0x180138f13  test    eax, eax
0x180138f15  jns     loc_180138FA6
0x180138f1b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180138f22  test    rcx, rcx
0x180138f25  jnz     short loc_180138F68
0x180138f27  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180138f2d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180138f34  mov     rcx, rax
0x180138f37  test    rax, rax
0x180138f3a  jz      short loc_180138F5A
0x180138f3c  mov     rax, [rax]
0x180138f3f  mov     edx, 7F0h
0x180138f44  mov     rax, [rax+8]
0x180138f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180138f4d  test    eax, eax
0x180138f4f  jz      short loc_180138F5A
0x180138f51  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180138f58  jmp     short loc_180138F68
0x180138f5a  lea     rcx, qword_1801B07E0; this
0x180138f61  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180138f68  cmp     byte ptr [rcx+8], 0
0x180138f6c  jz      short loc_180138F8F
0x180138f6e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180138f73  cmp     [rax+7CCh], ebx
0x180138f79  jz      short loc_180138F8F
0x180138f7b  mov     r9d, ebx; int
0x180138f7e  mov     r8d, 35Ah; int
0x180138f84  mov     rdx, r15; char *
0x180138f87  mov     rcx, rax; this
0x180138f8a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180138f8f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180138f96  jb      loc_180139113
0x180138f9c  mov     edx, 5Dh ; ']'
0x180138fa1  jmp     loc_1801390F5
0x180138fa6  lea     eax, [rdi-1]
0x180138fa9  cmp     byte ptr [rax+rsi], 0
0x180138fad  jz      loc_180139045
0x180138fb3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180138fba  mov     edi, 0C00D36BEh
0x180138fbf  mov     ebx, edi
0x180138fc1  test    rcx, rcx
0x180138fc4  jnz     short loc_180139007
0x180138fc6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180138fcc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180138fd3  mov     rcx, rax
0x180138fd6  test    rax, rax
0x180138fd9  jz      short loc_180138FF9
0x180138fdb  mov     rax, [rax]
0x180138fde  mov     edx, 7F0h
0x180138fe3  mov     rax, [rax+8]
0x180138fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180138fec  test    eax, eax
0x180138fee  jz      short loc_180138FF9
0x180138ff0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180138ff7  jmp     short loc_180139007
0x180138ff9  lea     rcx, qword_1801B07E0; this
0x180139000  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180139007  cmp     byte ptr [rcx+8], 0
0x18013900b  jz      short loc_18013902E
0x18013900d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180139012  cmp     [rax+7CCh], edi
0x180139018  jz      short loc_18013902E
0x18013901a  mov     r9d, edi; int
0x18013901d  mov     r8d, 361h; int
0x180139023  mov     rdx, r15; char *
0x180139026  mov     rcx, rax; this
0x180139029  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013902e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180139035  jb      loc_180139113
0x18013903b  mov     edx, 5Eh ; '^'
0x180139040  jmp     loc_180138E54
0x180139045  lea     rcx, [rbp+248h]
0x18013904c  mov     byte ptr [rax+rsi], 0
0x180139050  or      r9d, 0FFFFFFFFh
0x180139054  mov     qword ptr [rcx+4], 0
0x18013905c  mov     r8, rsi
0x18013905f  mov     edx, 0FDE9h
0x180139064  call    ?Append@?$CMFBaseStringT@G@@QEAAJIPEBDJ@Z; CMFBaseStringT<ushort>::Append(uint,char const *,long)
0x180139069  mov     ebx, eax
0x18013906b  test    eax, eax
0x18013906d  jns     loc_180139113
0x180139073  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013907a  test    rcx, rcx
0x18013907d  jnz     short loc_1801390C0
0x18013907f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180139085  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013908c  mov     rcx, rax
0x18013908f  test    rax, rax
0x180139092  jz      short loc_1801390B2
0x180139094  mov     rax, [rax]
0x180139097  mov     edx, 7F0h
0x18013909c  mov     rax, [rax+8]
0x1801390a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801390a5  test    eax, eax
0x1801390a7  jz      short loc_1801390B2
0x1801390a9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801390b0  jmp     short loc_1801390C0
0x1801390b2  lea     rcx, qword_1801B07E0; this
0x1801390b9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801390c0  cmp     byte ptr [rcx+8], 0
0x1801390c4  jz      short loc_1801390E7
0x1801390c6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801390cb  cmp     [rax+7CCh], ebx
0x1801390d1  jz      short loc_1801390E7
0x1801390d3  mov     r9d, ebx; int
0x1801390d6  mov     r8d, 369h; int
0x1801390dc  mov     rdx, r15; char *
0x1801390df  mov     rcx, rax; this
0x1801390e2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801390e7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801390ee  jb      short loc_180139113
0x1801390f0  mov     edx, 5Fh ; '_'
0x1801390f5  mov     [rsp+48h+var_28], ebx
0x1801390f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180139100  lea     r8, WPP_84f618ec34f9330309cc271626c14d28_Traceguids
0x180139107  mov     r9, rbp
0x18013910a  mov     rcx, [rcx+10h]
0x18013910e  call    WPP_SF_qD
0x180139113  mov     rcx, rsi; pv
0x180139116  call    cs:__imp_CoTaskMemFree
0x18013911c  lea     rcx, [rsp+48h+arg_8]; this
0x180139121  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180139126  mov     rbp, [rsp+48h+arg_10]
0x18013912b  mov     eax, ebx
0x18013912d  mov     rbx, [rsp+48h+arg_0]
0x180139132  add     rsp, 30h
0x180139136  pop     r15
0x180139138  pop     rdi
0x180139139  pop     rsi
0x18013913a  retn
```
