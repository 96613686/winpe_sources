# CAVIFileParser::ReadAVISampleChunk(unsigned __int64,ulong,ulong,ulong,uchar * *,ulong *)

- ea: `0x18009d35c`
- end: `0x18009d83e`
- name: `?ReadAVISampleChunk@CAVIFileParser@@QEAAJ_KKKKPEAPEAEPEAK@Z`
- size: `1250`
- prototype: `__int64 __fastcall(CAVIFileParser *this, __int64, unsigned int, unsigned int, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, loader_planting`

## callers

- `0x18007b128`
- `0x180140e04`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180034ce8`
- `0x180079680`
- `0x18009d35c`
- `0x1800ad6b8`
- `0x180110a7c`
- `0x180110a94`
- `0x18013f5f0`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009d3b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009d466`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009d517`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009d60e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009d6c2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009d76f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009d3b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009d466`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009d517`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009d60e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009d6c2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009d76f`

## string_xrefs

- `0x18009d378`: `CAVIFileParser::ReadAVISampleChunk`
- `0x18009d416`: `CAVIFileParser::ReadAVISampleChunk`
- `0x18009d4c3`: `CAVIFileParser::ReadAVISampleChunk`
- `0x18009d574`: `CAVIFileParser::ReadAVISampleChunk`
- `0x18009d66b`: `CAVIFileParser::ReadAVISampleChunk`
- `0x18009d71f`: `CAVIFileParser::ReadAVISampleChunk`
- `0x18009d7cc`: `CAVIFileParser::ReadAVISampleChunk`

## pseudocode

```c
__int64 __fastcall CAVIFileParser::ReadAVISampleChunk(
        CAVIFileParser *this,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned __int8 **a6,
        unsigned int *a7)
{
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned __int8 *v13; // r13
  wchar_t *v14; // rcx
  int RIFFChunkHeader; // ebx
  CallStackTracing *v16; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v18; // rdx
  unsigned __int8 **v19; // r14
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  unsigned int *v24; // r15
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  unsigned int v28; // ebx
  __int64 v29; // rdx
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  unsigned int v33; // edi
  unsigned __int8 *v34; // rax
  __int64 v35; // rdx
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 v39; // rdx
  wchar_t *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  size_t Size; // [rsp+90h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&Size, "CAVIFileParser::ReadAVISampleChunk", 80);
  v13 = 0;
  Size = 0;
  if ( !*(_QWORD *)this )
  {
    v14 = (wchar_t *)CallStackTracing::s_wpInstance;
    RIFFChunkHeader = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
      CallStackTracing::s_wpInstance = v16;
      if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
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
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CAVIFileParser::ReadAVISampleChunk", 86, -2147418113);
    }
    if ( !g_wppLevels )
      goto LABEL_71;
    v18 = 11;
    goto LABEL_70;
  }
  v19 = a6;
  if ( !a6 )
  {
    v20 = (wchar_t *)CallStackTracing::s_wpInstance;
    RIFFChunkHeader = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
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
      if ( *((_DWORD *)v22 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v22, "CAVIFileParser::ReadAVISampleChunk", 87, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_71;
    v23 = 12;
    goto LABEL_23;
  }
  v24 = a7;
  if ( !a7 )
  {
    v25 = (wchar_t *)CallStackTracing::s_wpInstance;
    RIFFChunkHeader = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
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
      if ( *((_DWORD *)v27 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v27, "CAVIFileParser::ReadAVISampleChunk", 88, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_71;
    v23 = 13;
LABEL_23:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v23,
      &WPP_b5fedc4f08bc3a8ba0f41d2b4d5376ee_Traceguids,
      this,
      -2147467261);
    goto LABEL_71;
  }
  v28 = a5;
  if ( (unsigned __int8)byte_1801BA109 >= 0x20u )
    WPP_SF_iddd(*((_QWORD *)WPP_GLOBAL_Control + 7), v11, v12, a2, a3, a4, a5);
  *(_QWORD *)(*(_QWORD *)this + 472LL) = a2;
  RIFFChunkHeader = CAVIFileParser::ReadRIFFChunkHeader(this, a3, a4, v28, (struct RIFF_CHUNK_HEADER *)&Size);
  if ( RIFFChunkHeader < 0 )
  {
    v30 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
      CallStackTracing::s_wpInstance = v31;
      if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
      {
        v30 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v30 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v30 + 8) )
    {
      v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
      if ( *((_DWORD *)v32 + 499) != RIFFChunkHeader )
        CallStackContext::TraceFailure(v32, "CAVIFileParser::ReadAVISampleChunk", 99, RIFFChunkHeader);
    }
    if ( !g_wppLevels )
      goto LABEL_71;
    v18 = 16;
    goto LABEL_70;
  }
  v33 = HIDWORD(Size);
  v34 = (unsigned __int8 *)operator new(HIDWORD(Size));
  v13 = v34;
  if ( !v34 )
  {
    v36 = (wchar_t *)CallStackTracing::s_wpInstance;
    RIFFChunkHeader = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35);
      CallStackTracing::s_wpInstance = v37;
      if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
      {
        v36 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v36 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v36 + 8) )
    {
      v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
      if ( *((_DWORD *)v38 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v38, "CAVIFileParser::ReadAVISampleChunk", 102, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_71;
    v18 = 17;
    goto LABEL_70;
  }
  RIFFChunkHeader = ReadData(*(struct CSourcePluginBufferReader **)this, v34, v33);
  if ( RIFFChunkHeader >= 0 )
  {
    *v19 = v13;
    *v24 = v33;
    goto LABEL_73;
  }
  v40 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39);
    CallStackTracing::s_wpInstance = v41;
    if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
    {
      v40 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v40 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
  }
  if ( *((_BYTE *)v40 + 8) )
  {
    v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
    if ( *((_DWORD *)v42 + 499) != RIFFChunkHeader )
      CallStackContext::TraceFailure(v42, "CAVIFileParser::ReadAVISampleChunk", 104, RIFFChunkHeader);
  }
  if ( g_wppLevels )
  {
    v18 = 18;
LABEL_70:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v18,
      &WPP_b5fedc4f08bc3a8ba0f41d2b4d5376ee_Traceguids,
      this,
      RIFFChunkHeader);
  }
LABEL_71:
  operator delete(v13);
LABEL_73:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&Size);
  return (unsigned int)RIFFChunkHeader;
}

```

## disassembly

```asm
0x18009d35c  mov     rax, rsp
0x18009d35f  push    rbx
0x18009d360  push    rbp
0x18009d361  push    rsi
0x18009d362  push    rdi
0x18009d363  push    r12
0x18009d365  push    r13
0x18009d367  push    r14
0x18009d369  push    r15
0x18009d36b  sub     rsp, 48h
0x18009d36f  mov     ebp, r8d
0x18009d372  mov     r12, rdx
0x18009d375  mov     rsi, rcx
0x18009d378  lea     rdx, aCavifileparser_1; "CAVIFileParser::ReadAVISampleChunk"
0x18009d37f  mov     r8d, 50h ; 'P'; int
0x18009d385  lea     rcx, [rax+8]; this
0x18009d389  mov     edi, r9d
0x18009d38c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009d391  xor     r15d, r15d
0x18009d394  mov     r13d, r15d
0x18009d397  mov     [rsp+88h+Size], r15
0x18009d39f  cmp     [rsi], r15
0x18009d3a2  jnz     loc_18009D442
0x18009d3a8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009d3af  mov     ebx, 8000FFFFh
0x18009d3b4  test    rcx, rcx
0x18009d3b7  jnz     short loc_18009D400
0x18009d3b9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009d3c0  nop     dword ptr [rax+rax+00h]
0x18009d3c5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009d3cc  mov     rcx, rax
0x18009d3cf  test    rax, rax
0x18009d3d2  jz      short loc_18009D3F2
0x18009d3d4  mov     rax, [rax]
0x18009d3d7  mov     edx, 7F0h
0x18009d3dc  mov     rax, [rax+8]
0x18009d3e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d3e5  test    eax, eax
0x18009d3e7  jz      short loc_18009D3F2
0x18009d3e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009d3f0  jmp     short loc_18009D400
0x18009d3f2  lea     rcx, qword_1801B97E0; this
0x18009d3f9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009d400  cmp     [rcx+8], r15b
0x18009d404  jz      short loc_18009D42B
0x18009d406  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009d40b  cmp     [rax+7CCh], ebx
0x18009d411  jz      short loc_18009D42B
0x18009d413  mov     r9d, ebx; int
0x18009d416  lea     rdx, aCavifileparser_1; "CAVIFileParser::ReadAVISampleChunk"
0x18009d41d  mov     r8d, 56h ; 'V'; int
0x18009d423  mov     rcx, rax; this
0x18009d426  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009d42b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009d432  jb      loc_18009D80D
0x18009d438  mov     edx, 0Bh
0x18009d43d  jmp     loc_18009D7EF
0x18009d442  mov     r14, [rsp+88h+arg_28]
0x18009d44a  test    r14, r14
0x18009d44d  jnz     loc_18009D4F3
0x18009d453  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009d45a  mov     edi, 80004003h
0x18009d45f  mov     ebx, edi
0x18009d461  test    rcx, rcx
0x18009d464  jnz     short loc_18009D4AD
0x18009d466  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009d46d  nop     dword ptr [rax+rax+00h]
0x18009d472  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009d479  mov     rcx, rax
0x18009d47c  test    rax, rax
0x18009d47f  jz      short loc_18009D49F
0x18009d481  mov     rax, [rax]
0x18009d484  mov     edx, 7F0h
0x18009d489  mov     rax, [rax+8]
0x18009d48d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d492  test    eax, eax
0x18009d494  jz      short loc_18009D49F
0x18009d496  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009d49d  jmp     short loc_18009D4AD
0x18009d49f  lea     rcx, qword_1801B97E0; this
0x18009d4a6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009d4ad  cmp     [rcx+8], r15b
0x18009d4b1  jz      short loc_18009D4D8
0x18009d4b3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009d4b8  cmp     [rax+7CCh], edi
0x18009d4be  jz      short loc_18009D4D8
0x18009d4c0  mov     r9d, edi; int
0x18009d4c3  lea     rdx, aCavifileparser_1; "CAVIFileParser::ReadAVISampleChunk"
0x18009d4ca  mov     r8d, 57h ; 'W'; int
0x18009d4d0  mov     rcx, rax; this
0x18009d4d3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009d4d8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009d4df  jb      loc_18009D80D
0x18009d4e5  mov     edx, 0Ch
0x18009d4ea  mov     dword ptr [rsp+88h+var_68], edi
0x18009d4ee  jmp     loc_18009D7F3
0x18009d4f3  mov     r15, [rsp+88h+arg_30]
0x18009d4fb  test    r15, r15
0x18009d4fe  jnz     loc_18009D5A0
0x18009d504  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009d50b  mov     edi, 80004003h
0x18009d510  mov     ebx, edi
0x18009d512  test    rcx, rcx
0x18009d515  jnz     short loc_18009D55E
0x18009d517  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009d51e  nop     dword ptr [rax+rax+00h]
0x18009d523  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009d52a  mov     rcx, rax
0x18009d52d  test    rax, rax
0x18009d530  jz      short loc_18009D550
0x18009d532  mov     rax, [rax]
0x18009d535  mov     edx, 7F0h
0x18009d53a  mov     rax, [rax+8]
0x18009d53e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d543  test    eax, eax
0x18009d545  jz      short loc_18009D550
0x18009d547  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009d54e  jmp     short loc_18009D55E
0x18009d550  lea     rcx, qword_1801B97E0; this
0x18009d557  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009d55e  cmp     [rcx+8], r13b
0x18009d562  jz      short loc_18009D589
0x18009d564  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009d569  cmp     [rax+7CCh], edi
0x18009d56f  jz      short loc_18009D589
0x18009d571  mov     r9d, edi; int
0x18009d574  lea     rdx, aCavifileparser_1; "CAVIFileParser::ReadAVISampleChunk"
0x18009d57b  mov     r8d, 58h ; 'X'; int
0x18009d581  mov     rcx, rax; this
0x18009d584  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009d589  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009d590  jb      loc_18009D80D
0x18009d596  mov     edx, 0Dh
0x18009d59b  jmp     loc_18009D4EA
0x18009d5a0  cmp     cs:byte_1801BA109, 20h ; ' '
0x18009d5a7  mov     ebx, [rsp+88h+arg_20]
0x18009d5ae  jb      short loc_18009D5CF
0x18009d5b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d5b7  mov     r9, r12
0x18009d5ba  mov     [rsp+88h+var_58], ebx
0x18009d5be  mov     [rsp+88h+var_60], edi
0x18009d5c2  mov     dword ptr [rsp+88h+var_68], ebp
0x18009d5c6  mov     rcx, [rcx+38h]
0x18009d5ca  call    WPP_SF_iddd
0x18009d5cf  mov     rax, [rsi]
0x18009d5d2  mov     r9d, ebx; unsigned int
0x18009d5d5  mov     r8d, edi; unsigned int
0x18009d5d8  mov     edx, ebp; unsigned int
0x18009d5da  mov     rcx, rsi; this
0x18009d5dd  mov     [rax+1D8h], r12
0x18009d5e4  lea     rax, [rsp+88h+Size]
0x18009d5ec  mov     [rsp+88h+var_68], rax; struct RIFF_CHUNK_HEADER *
0x18009d5f1  call    ?ReadRIFFChunkHeader@CAVIFileParser@@AEAAJKKKPEAURIFF_CHUNK_HEADER@@@Z; CAVIFileParser::ReadRIFFChunkHeader(ulong,ulong,ulong,RIFF_CHUNK_HEADER *)
0x18009d5f6  xor     ebp, ebp
0x18009d5f8  mov     ebx, eax
0x18009d5fa  test    eax, eax
0x18009d5fc  jns     loc_18009D697
0x18009d602  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009d609  test    rcx, rcx
0x18009d60c  jnz     short loc_18009D655
0x18009d60e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009d615  nop     dword ptr [rax+rax+00h]
0x18009d61a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009d621  mov     rcx, rax
0x18009d624  test    rax, rax
0x18009d627  jz      short loc_18009D647
0x18009d629  mov     rax, [rax]
0x18009d62c  mov     edx, 7F0h
0x18009d631  mov     rax, [rax+8]
0x18009d635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d63a  test    eax, eax
0x18009d63c  jz      short loc_18009D647
0x18009d63e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009d645  jmp     short loc_18009D655
0x18009d647  lea     rcx, qword_1801B97E0; this
0x18009d64e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009d655  cmp     [rcx+8], bpl
0x18009d659  jz      short loc_18009D680
0x18009d65b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009d660  cmp     [rax+7CCh], ebx
0x18009d666  jz      short loc_18009D680
0x18009d668  mov     r9d, ebx; int
0x18009d66b  lea     rdx, aCavifileparser_1; "CAVIFileParser::ReadAVISampleChunk"
0x18009d672  mov     r8d, 63h ; 'c'; int
0x18009d678  mov     rcx, rax; this
0x18009d67b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009d680  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009d687  jb      loc_18009D80D
0x18009d68d  mov     edx, 10h
0x18009d692  jmp     loc_18009D7EF
0x18009d697  mov     edi, dword ptr [rsp+88h+Size+4]
0x18009d69e  mov     ecx, edi; Size
0x18009d6a0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009d6a5  mov     r13, rax
0x18009d6a8  test    rax, rax
0x18009d6ab  jnz     loc_18009D74B
0x18009d6b1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009d6b8  mov     ebx, 8007000Eh
0x18009d6bd  test    rcx, rcx
0x18009d6c0  jnz     short loc_18009D709
0x18009d6c2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009d6c9  nop     dword ptr [rax+rax+00h]
0x18009d6ce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009d6d5  mov     rcx, rax
0x18009d6d8  test    rax, rax
0x18009d6db  jz      short loc_18009D6FB
0x18009d6dd  mov     rax, [rax]
0x18009d6e0  mov     edx, 7F0h
0x18009d6e5  mov     rax, [rax+8]
0x18009d6e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d6ee  test    eax, eax
0x18009d6f0  jz      short loc_18009D6FB
0x18009d6f2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009d6f9  jmp     short loc_18009D709
0x18009d6fb  lea     rcx, qword_1801B97E0; this
0x18009d702  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009d709  cmp     [rcx+8], bpl
0x18009d70d  jz      short loc_18009D734
0x18009d70f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009d714  cmp     [rax+7CCh], ebx
0x18009d71a  jz      short loc_18009D734
0x18009d71c  mov     r9d, ebx; int
0x18009d71f  lea     rdx, aCavifileparser_1; "CAVIFileParser::ReadAVISampleChunk"
0x18009d726  mov     r8d, 66h ; 'f'; int
0x18009d72c  mov     rcx, rax; this
0x18009d72f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009d734  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009d73b  jb      loc_18009D80D
0x18009d741  mov     edx, 11h
0x18009d746  jmp     loc_18009D7EF
0x18009d74b  mov     rcx, [rsi]; struct CSourcePluginBufferReader *
0x18009d74e  mov     r8d, edi; unsigned int
0x18009d751  mov     rdx, r13; unsigned __int8 *
0x18009d754  call    ?ReadData@@YAJPEAVCSourcePluginBufferReader@@PEAEK@Z; ReadData(CSourcePluginBufferReader *,uchar *,ulong)
0x18009d759  mov     ebx, eax
0x18009d75b  test    eax, eax
0x18009d75d  jns     loc_18009D817
0x18009d763  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009d76a  test    rcx, rcx
0x18009d76d  jnz     short loc_18009D7B6
0x18009d76f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009d776  nop     dword ptr [rax+rax+00h]
0x18009d77b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009d782  mov     rcx, rax
0x18009d785  test    rax, rax
0x18009d788  jz      short loc_18009D7A8
0x18009d78a  mov     rax, [rax]
0x18009d78d  mov     edx, 7F0h
0x18009d792  mov     rax, [rax+8]
0x18009d796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d79b  test    eax, eax
0x18009d79d  jz      short loc_18009D7A8
0x18009d79f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009d7a6  jmp     short loc_18009D7B6
0x18009d7a8  lea     rcx, qword_1801B97E0; this
0x18009d7af  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009d7b6  cmp     [rcx+8], bpl
0x18009d7ba  jz      short loc_18009D7E1
0x18009d7bc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009d7c1  cmp     [rax+7CCh], ebx
0x18009d7c7  jz      short loc_18009D7E1
0x18009d7c9  mov     r9d, ebx; int
0x18009d7cc  lea     rdx, aCavifileparser_1; "CAVIFileParser::ReadAVISampleChunk"
0x18009d7d3  mov     r8d, 68h ; 'h'; int
0x18009d7d9  mov     rcx, rax; this
0x18009d7dc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009d7e1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009d7e8  jb      short loc_18009D80D
0x18009d7ea  mov     edx, 12h
0x18009d7ef  mov     dword ptr [rsp+88h+var_68], ebx
0x18009d7f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d7fa  lea     r8, WPP_b5fedc4f08bc3a8ba0f41d2b4d5376ee_Traceguids
0x18009d801  mov     r9, rsi
0x18009d804  mov     rcx, [rcx+10h]
0x18009d808  call    WPP_SF_qD
0x18009d80d  mov     rcx, r13; Block
0x18009d810  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009d815  jmp     short loc_18009D81D
0x18009d817  mov     [r14], r13
0x18009d81a  mov     [r15], edi
0x18009d81d  lea     rcx, [rsp+88h+Size]; this
0x18009d825  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18009d82a  mov     eax, ebx
0x18009d82c  add     rsp, 48h
0x18009d830  pop     r15
0x18009d832  pop     r14
0x18009d834  pop     r13
0x18009d836  pop     r12
0x18009d838  pop     rdi
0x18009d839  pop     rsi
0x18009d83a  pop     rbp
0x18009d83b  pop     rbx
0x18009d83c  retn
```
