# CAVIFileParser::ReadAVISampleChunk(unsigned __int64,ulong,ulong,ulong,uchar * *,ulong *)

- ea: `0x180097e1c`
- end: `0x1800982d9`
- name: `?ReadAVISampleChunk@CAVIFileParser@@QEAAJ_KKKKPEAPEAEPEAK@Z`
- size: `1213`
- prototype: `__int64 __fastcall(CAVIFileParser *this, __int64, unsigned int, unsigned int, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, loader_planting`

## callers

- `0x180075654`
- `0x1801394b4`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x1800370c4`
- `0x180073b14`
- `0x180097e1c`
- `0x1800a8528`
- `0x180109590`
- `0x1801095a8`
- `0x180137d44`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180097e79`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180097f20`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180097fcb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800980bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009816a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098211`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180097e79`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180097f20`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180097fcb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800980bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009816a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098211`

## string_xrefs

- `0x180097e38`: `CAVIFileParser::ReadAVISampleChunk`
- `0x180097ed0`: `CAVIFileParser::ReadAVISampleChunk`
- `0x180097f77`: `CAVIFileParser::ReadAVISampleChunk`
- `0x180098022`: `CAVIFileParser::ReadAVISampleChunk`
- `0x180098113`: `CAVIFileParser::ReadAVISampleChunk`
- `0x1800981c1`: `CAVIFileParser::ReadAVISampleChunk`
- `0x180098268`: `CAVIFileParser::ReadAVISampleChunk`

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
  __int64 v13; // r9
  unsigned __int8 *v14; // r13
  wchar_t *v15; // rcx
  int RIFFChunkHeader; // ebx
  CallStackTracing *v17; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v19; // rdx
  unsigned __int8 **v20; // r14
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  unsigned int *v25; // r15
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  unsigned int v29; // ebx
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  wchar_t *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  unsigned int v36; // edi
  unsigned __int8 *v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // r9
  wchar_t *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // r9
  wchar_t *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  size_t Size; // [rsp+90h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&Size, "CAVIFileParser::ReadAVISampleChunk", 80);
  v14 = 0;
  Size = 0;
  if ( !*(_QWORD *)this )
  {
    v15 = (wchar_t *)CallStackTracing::s_wpInstance;
    RIFFChunkHeader = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11, v12, v13);
      CallStackTracing::s_wpInstance = v17;
      if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
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
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CAVIFileParser::ReadAVISampleChunk", 86, -2147418113);
    }
    if ( !g_wppLevels )
      goto LABEL_71;
    v19 = 11;
    goto LABEL_70;
  }
  v20 = a6;
  if ( !a6 )
  {
    v21 = (wchar_t *)CallStackTracing::s_wpInstance;
    RIFFChunkHeader = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11, v12, v13);
      CallStackTracing::s_wpInstance = v22;
      if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
      {
        v21 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v21 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v21 + 8) )
    {
      v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
      if ( *((_DWORD *)v23 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v23, "CAVIFileParser::ReadAVISampleChunk", 87, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_71;
    v24 = 12;
    goto LABEL_23;
  }
  v25 = a7;
  if ( !a7 )
  {
    v26 = (wchar_t *)CallStackTracing::s_wpInstance;
    RIFFChunkHeader = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11, v12, v13);
      CallStackTracing::s_wpInstance = v27;
      if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
      {
        v26 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v26 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v26 + 8) )
    {
      v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
      if ( *((_DWORD *)v28 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v28, "CAVIFileParser::ReadAVISampleChunk", 88, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_71;
    v24 = 13;
LABEL_23:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v24,
      &WPP_b5fedc4f08bc3a8ba0f41d2b4d5376ee_Traceguids,
      this,
      -2147467261);
    goto LABEL_71;
  }
  v29 = a5;
  if ( (unsigned __int8)byte_1801B1109 >= 0x20u )
    WPP_SF_iddd(*((_QWORD *)WPP_GLOBAL_Control + 7), v11, v12, a2, a3, a4, a5);
  *(_QWORD *)(*(_QWORD *)this + 472LL) = a2;
  RIFFChunkHeader = CAVIFileParser::ReadRIFFChunkHeader(this, a3, a4, v29, (struct RIFF_CHUNK_HEADER *)&Size);
  if ( RIFFChunkHeader < 0 )
  {
    v33 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30, v31, v32);
      CallStackTracing::s_wpInstance = v34;
      if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
      {
        v33 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v33 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v33 + 8) )
    {
      v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
      if ( *((_DWORD *)v35 + 499) != RIFFChunkHeader )
        CallStackContext::TraceFailure(v35, "CAVIFileParser::ReadAVISampleChunk", 99, RIFFChunkHeader);
    }
    if ( !g_wppLevels )
      goto LABEL_71;
    v19 = 16;
    goto LABEL_70;
  }
  v36 = HIDWORD(Size);
  v37 = (unsigned __int8 *)operator new(HIDWORD(Size));
  v14 = v37;
  if ( !v37 )
  {
    v41 = (wchar_t *)CallStackTracing::s_wpInstance;
    RIFFChunkHeader = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38, v39, v40);
      CallStackTracing::s_wpInstance = v42;
      if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
      {
        v41 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v41 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v41 + 8) )
    {
      v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
      if ( *((_DWORD *)v43 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v43, "CAVIFileParser::ReadAVISampleChunk", 102, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_71;
    v19 = 17;
    goto LABEL_70;
  }
  RIFFChunkHeader = ReadData(*(struct CSourcePluginBufferReader **)this, v37, v36);
  if ( RIFFChunkHeader >= 0 )
  {
    *v20 = v14;
    *v25 = v36;
    goto LABEL_73;
  }
  v47 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44, v45, v46);
    CallStackTracing::s_wpInstance = v48;
    if ( v48 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
    {
      v47 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v47 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v47 + 8) )
  {
    v49 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v47);
    if ( *((_DWORD *)v49 + 499) != RIFFChunkHeader )
      CallStackContext::TraceFailure(v49, "CAVIFileParser::ReadAVISampleChunk", 104, RIFFChunkHeader);
  }
  if ( g_wppLevels )
  {
    v19 = 18;
LABEL_70:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v19,
      &WPP_b5fedc4f08bc3a8ba0f41d2b4d5376ee_Traceguids,
      this,
      RIFFChunkHeader);
  }
LABEL_71:
  operator delete(v14);
LABEL_73:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&Size);
  return (unsigned int)RIFFChunkHeader;
}

```

## disassembly

```asm
0x180097e1c  mov     rax, rsp
0x180097e1f  push    rbx
0x180097e20  push    rbp
0x180097e21  push    rsi
0x180097e22  push    rdi
0x180097e23  push    r12
0x180097e25  push    r13
0x180097e27  push    r14
0x180097e29  push    r15
0x180097e2b  sub     rsp, 48h
0x180097e2f  mov     ebp, r8d
0x180097e32  mov     r12, rdx
0x180097e35  mov     rsi, rcx
0x180097e38  lea     rdx, aCavifileparser_1; "CAVIFileParser::ReadAVISampleChunk"
0x180097e3f  mov     r8d, 50h ; 'P'; int
0x180097e45  lea     rcx, [rax+8]; this
0x180097e49  mov     edi, r9d
0x180097e4c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180097e51  xor     r15d, r15d
0x180097e54  mov     r13d, r15d
0x180097e57  mov     [rsp+88h+Size], r15
0x180097e5f  cmp     [rsi], r15
0x180097e62  jnz     loc_180097EFC
0x180097e68  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180097e6f  mov     ebx, 8000FFFFh
0x180097e74  test    rcx, rcx
0x180097e77  jnz     short loc_180097EBA
0x180097e79  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180097e7f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180097e86  mov     rcx, rax
0x180097e89  test    rax, rax
0x180097e8c  jz      short loc_180097EAC
0x180097e8e  mov     rax, [rax]
0x180097e91  mov     edx, 7F0h
0x180097e96  mov     rax, [rax+8]
0x180097e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097e9f  test    eax, eax
0x180097ea1  jz      short loc_180097EAC
0x180097ea3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180097eaa  jmp     short loc_180097EBA
0x180097eac  lea     rcx, qword_1801B07E0; this
0x180097eb3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180097eba  cmp     [rcx+8], r15b
0x180097ebe  jz      short loc_180097EE5
0x180097ec0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180097ec5  cmp     [rax+7CCh], ebx
0x180097ecb  jz      short loc_180097EE5
0x180097ecd  mov     r9d, ebx; int
0x180097ed0  lea     rdx, aCavifileparser_1; "CAVIFileParser::ReadAVISampleChunk"
0x180097ed7  mov     r8d, 56h ; 'V'; int
0x180097edd  mov     rcx, rax; this
0x180097ee0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180097ee5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180097eec  jb      loc_1800982A9
0x180097ef2  mov     edx, 0Bh
0x180097ef7  jmp     loc_18009828B
0x180097efc  mov     r14, [rsp+88h+arg_28]
0x180097f04  test    r14, r14
0x180097f07  jnz     loc_180097FA7
0x180097f0d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180097f14  mov     edi, 80004003h
0x180097f19  mov     ebx, edi
0x180097f1b  test    rcx, rcx
0x180097f1e  jnz     short loc_180097F61
0x180097f20  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180097f26  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180097f2d  mov     rcx, rax
0x180097f30  test    rax, rax
0x180097f33  jz      short loc_180097F53
0x180097f35  mov     rax, [rax]
0x180097f38  mov     edx, 7F0h
0x180097f3d  mov     rax, [rax+8]
0x180097f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097f46  test    eax, eax
0x180097f48  jz      short loc_180097F53
0x180097f4a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180097f51  jmp     short loc_180097F61
0x180097f53  lea     rcx, qword_1801B07E0; this
0x180097f5a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180097f61  cmp     [rcx+8], r15b
0x180097f65  jz      short loc_180097F8C
0x180097f67  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180097f6c  cmp     [rax+7CCh], edi
0x180097f72  jz      short loc_180097F8C
0x180097f74  mov     r9d, edi; int
0x180097f77  lea     rdx, aCavifileparser_1; "CAVIFileParser::ReadAVISampleChunk"
0x180097f7e  mov     r8d, 57h ; 'W'; int
0x180097f84  mov     rcx, rax; this
0x180097f87  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180097f8c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180097f93  jb      loc_1800982A9
0x180097f99  mov     edx, 0Ch
0x180097f9e  mov     dword ptr [rsp+88h+var_68], edi
0x180097fa2  jmp     loc_18009828F
0x180097fa7  mov     r15, [rsp+88h+arg_30]
0x180097faf  test    r15, r15
0x180097fb2  jnz     loc_18009804E
0x180097fb8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180097fbf  mov     edi, 80004003h
0x180097fc4  mov     ebx, edi
0x180097fc6  test    rcx, rcx
0x180097fc9  jnz     short loc_18009800C
0x180097fcb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180097fd1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180097fd8  mov     rcx, rax
0x180097fdb  test    rax, rax
0x180097fde  jz      short loc_180097FFE
0x180097fe0  mov     rax, [rax]
0x180097fe3  mov     edx, 7F0h
0x180097fe8  mov     rax, [rax+8]
0x180097fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097ff1  test    eax, eax
0x180097ff3  jz      short loc_180097FFE
0x180097ff5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180097ffc  jmp     short loc_18009800C
0x180097ffe  lea     rcx, qword_1801B07E0; this
0x180098005  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009800c  cmp     [rcx+8], r13b
0x180098010  jz      short loc_180098037
0x180098012  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180098017  cmp     [rax+7CCh], edi
0x18009801d  jz      short loc_180098037
0x18009801f  mov     r9d, edi; int
0x180098022  lea     rdx, aCavifileparser_1; "CAVIFileParser::ReadAVISampleChunk"
0x180098029  mov     r8d, 58h ; 'X'; int
0x18009802f  mov     rcx, rax; this
0x180098032  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180098037  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009803e  jb      loc_1800982A9
0x180098044  mov     edx, 0Dh
0x180098049  jmp     loc_180097F9E
0x18009804e  cmp     cs:byte_1801B1109, 20h ; ' '
0x180098055  mov     ebx, [rsp+88h+arg_20]
0x18009805c  jb      short loc_18009807D
0x18009805e  mov     rcx, cs:WPP_GLOBAL_Control
0x180098065  mov     r9, r12
0x180098068  mov     [rsp+88h+var_58], ebx
0x18009806c  mov     [rsp+88h+var_60], edi
0x180098070  mov     dword ptr [rsp+88h+var_68], ebp
0x180098074  mov     rcx, [rcx+38h]
0x180098078  call    WPP_SF_iddd
0x18009807d  mov     rax, [rsi]
0x180098080  mov     r9d, ebx; unsigned int
0x180098083  mov     r8d, edi; unsigned int
0x180098086  mov     edx, ebp; unsigned int
0x180098088  mov     rcx, rsi; this
0x18009808b  mov     [rax+1D8h], r12
0x180098092  lea     rax, [rsp+88h+Size]
0x18009809a  mov     [rsp+88h+var_68], rax; struct RIFF_CHUNK_HEADER *
0x18009809f  call    ?ReadRIFFChunkHeader@CAVIFileParser@@AEAAJKKKPEAURIFF_CHUNK_HEADER@@@Z; CAVIFileParser::ReadRIFFChunkHeader(ulong,ulong,ulong,RIFF_CHUNK_HEADER *)
0x1800980a4  xor     ebp, ebp
0x1800980a6  mov     ebx, eax
0x1800980a8  test    eax, eax
0x1800980aa  jns     loc_18009813F
0x1800980b0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800980b7  test    rcx, rcx
0x1800980ba  jnz     short loc_1800980FD
0x1800980bc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800980c2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800980c9  mov     rcx, rax
0x1800980cc  test    rax, rax
0x1800980cf  jz      short loc_1800980EF
0x1800980d1  mov     rax, [rax]
0x1800980d4  mov     edx, 7F0h
0x1800980d9  mov     rax, [rax+8]
0x1800980dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800980e2  test    eax, eax
0x1800980e4  jz      short loc_1800980EF
0x1800980e6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800980ed  jmp     short loc_1800980FD
0x1800980ef  lea     rcx, qword_1801B07E0; this
0x1800980f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800980fd  cmp     [rcx+8], bpl
0x180098101  jz      short loc_180098128
0x180098103  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180098108  cmp     [rax+7CCh], ebx
0x18009810e  jz      short loc_180098128
0x180098110  mov     r9d, ebx; int
0x180098113  lea     rdx, aCavifileparser_1; "CAVIFileParser::ReadAVISampleChunk"
0x18009811a  mov     r8d, 63h ; 'c'; int
0x180098120  mov     rcx, rax; this
0x180098123  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180098128  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009812f  jb      loc_1800982A9
0x180098135  mov     edx, 10h
0x18009813a  jmp     loc_18009828B
0x18009813f  mov     edi, dword ptr [rsp+88h+Size+4]
0x180098146  mov     ecx, edi; Size
0x180098148  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009814d  mov     r13, rax
0x180098150  test    rax, rax
0x180098153  jnz     loc_1800981ED
0x180098159  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180098160  mov     ebx, 8007000Eh
0x180098165  test    rcx, rcx
0x180098168  jnz     short loc_1800981AB
0x18009816a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180098170  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180098177  mov     rcx, rax
0x18009817a  test    rax, rax
0x18009817d  jz      short loc_18009819D
0x18009817f  mov     rax, [rax]
0x180098182  mov     edx, 7F0h
0x180098187  mov     rax, [rax+8]
0x18009818b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098190  test    eax, eax
0x180098192  jz      short loc_18009819D
0x180098194  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009819b  jmp     short loc_1800981AB
0x18009819d  lea     rcx, qword_1801B07E0; this
0x1800981a4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800981ab  cmp     [rcx+8], bpl
0x1800981af  jz      short loc_1800981D6
0x1800981b1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800981b6  cmp     [rax+7CCh], ebx
0x1800981bc  jz      short loc_1800981D6
0x1800981be  mov     r9d, ebx; int
0x1800981c1  lea     rdx, aCavifileparser_1; "CAVIFileParser::ReadAVISampleChunk"
0x1800981c8  mov     r8d, 66h ; 'f'; int
0x1800981ce  mov     rcx, rax; this
0x1800981d1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800981d6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800981dd  jb      loc_1800982A9
0x1800981e3  mov     edx, 11h
0x1800981e8  jmp     loc_18009828B
0x1800981ed  mov     rcx, [rsi]; struct CSourcePluginBufferReader *
0x1800981f0  mov     r8d, edi; unsigned int
0x1800981f3  mov     rdx, r13; unsigned __int8 *
0x1800981f6  call    ?ReadData@@YAJPEAVCSourcePluginBufferReader@@PEAEK@Z; ReadData(CSourcePluginBufferReader *,uchar *,ulong)
0x1800981fb  mov     ebx, eax
0x1800981fd  test    eax, eax
0x1800981ff  jns     loc_1800982B3
0x180098205  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009820c  test    rcx, rcx
0x18009820f  jnz     short loc_180098252
0x180098211  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180098217  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009821e  mov     rcx, rax
0x180098221  test    rax, rax
0x180098224  jz      short loc_180098244
0x180098226  mov     rax, [rax]
0x180098229  mov     edx, 7F0h
0x18009822e  mov     rax, [rax+8]
0x180098232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098237  test    eax, eax
0x180098239  jz      short loc_180098244
0x18009823b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180098242  jmp     short loc_180098252
0x180098244  lea     rcx, qword_1801B07E0; this
0x18009824b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180098252  cmp     [rcx+8], bpl
0x180098256  jz      short loc_18009827D
0x180098258  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009825d  cmp     [rax+7CCh], ebx
0x180098263  jz      short loc_18009827D
0x180098265  mov     r9d, ebx; int
0x180098268  lea     rdx, aCavifileparser_1; "CAVIFileParser::ReadAVISampleChunk"
0x18009826f  mov     r8d, 68h ; 'h'; int
0x180098275  mov     rcx, rax; this
0x180098278  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009827d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180098284  jb      short loc_1800982A9
0x180098286  mov     edx, 12h
0x18009828b  mov     dword ptr [rsp+88h+var_68], ebx
0x18009828f  mov     rcx, cs:WPP_GLOBAL_Control
0x180098296  lea     r8, WPP_b5fedc4f08bc3a8ba0f41d2b4d5376ee_Traceguids
0x18009829d  mov     r9, rsi
0x1800982a0  mov     rcx, [rcx+10h]
0x1800982a4  call    WPP_SF_qD
0x1800982a9  mov     rcx, r13; Block
0x1800982ac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800982b1  jmp     short loc_1800982B9
0x1800982b3  mov     [r14], r13
0x1800982b6  mov     [r15], edi
0x1800982b9  lea     rcx, [rsp+88h+Size]; this
0x1800982c1  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800982c6  mov     eax, ebx
0x1800982c8  add     rsp, 48h
0x1800982cc  pop     r15
0x1800982ce  pop     r14
0x1800982d0  pop     r13
0x1800982d2  pop     r12
0x1800982d4  pop     rdi
0x1800982d5  pop     rsi
0x1800982d6  pop     rbp
0x1800982d7  pop     rbx
0x1800982d8  retn
```
