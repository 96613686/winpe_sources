# mkvparser::ParseElementHeader(mkvparser::IMkvReader *,__int64 &,__int64,__int64 &,__int64 &)

- ea: `0x1800a1710`
- end: `0x1800a1b92`
- name: `?ParseElementHeader@mkvparser@@YAJPEAUIMkvReader@1@AEA_J_J11@Z`
- size: `1154`
- prototype: `__int64 __usercall@<rax>(mkvparser *__hidden this@<rcx>, struct mkvparser::IMkvReader *@<rdx>, __int64 *@<r8>, __int64@<r9>, __int64 *, __int64 *)`
- caller_count: `20`
- callee_count: `9`
- tags: ``

## callers

- `0x180091db0`
- `0x1800923e0`
- `0x1800950fc`
- `0x1800964a0`
- `0x180097480`
- `0x180097920`
- `0x180098c60`
- `0x180098f7c`
- `0x180099bb0`
- `0x18009a3e0`
- `0x18009abd8`
- `0x18009c14c`
- `0x18009c6dc`
- `0x18009ecd4`
- `0x18009f1d8`
- `0x18009f58c`
- `0x1800a0298`
- `0x1800a1b98`
- `0x1800a27b8`
- `0x1800a67dc`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x1800a1710`
- `0x1800a9220`
- `0x1800a96cc`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1768`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1834`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a18d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a198b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1a31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1ad6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1768`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1834`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a18d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a198b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1a31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1ad6`

## pseudocode

```c
__int64 __fastcall mkvparser::ParseElementHeader(
        __int64 (__fastcall ***this)(mkvparser *, struct mkvparser::IMkvReader *, __int64, unsigned __int8 *),
        struct mkvparser::IMkvReader **a2,
        struct mkvparser::IMkvReader *a3,
        __int64 *a4,
        __int64 *a5)
{
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  int ID; // ebx
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 v32; // rdx
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v40[5]; // [rsp+30h] [rbp-28h] BYREF
  char v41; // [rsp+70h] [rbp+18h] BYREF

  if ( (__int64)a3 < 0 || (__int64)*a2 < (__int64)a3 )
  {
    LODWORD(v40[0]) = 0;
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v41, "mkvparser::ParseElementHeader", 586);
    ID = mkvparser::ReadID(this, *a2, a4, v40);
    if ( ID >= 0 )
    {
      *a2 = (struct mkvparser::IMkvReader *)((char *)*a2 + SLODWORD(v40[0]));
      if ( (__int64)a3 < 0 || (__int64)*a2 < (__int64)a3 )
      {
        ID = mkvparser::ReadUInt(this, *a2, a5, v40);
        if ( ID >= 0 )
        {
          v32 = (__int64)*a2 + SLODWORD(v40[0]);
          if ( (unsigned __int64)v32 <= 0x7FFFFFFFFFFFFFFFLL )
          {
            *a2 = (struct mkvparser::IMkvReader *)v32;
            if ( (__int64)a3 < 0 || v32 <= (__int64)a3 )
            {
              ID = 0;
              goto LABEL_72;
            }
            v36 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v27, v28);
              CallStackTracing::s_wpInstance = v37;
              if ( v37
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
              {
                v36 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v36 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
              }
            }
            ID = -1072875842;
            if ( *((_BYTE *)v36 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875842 )
                CallStackContext::TraceFailure(ThreadRelativeContext, "mkvparser::ParseElementHeader", 611, -1072875842);
            }
            if ( g_wppLevels )
            {
              v16 = 52;
              goto LABEL_70;
            }
          }
          else
          {
            v33 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v27, v28);
              CallStackTracing::s_wpInstance = v34;
              if ( v34
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
              {
                v33 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v33 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
              }
            }
            ID = -1072875842;
            if ( *((_BYTE *)v33 + 8) )
            {
              v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
              if ( *((_DWORD *)v35 + 499) != -1072875842 )
                CallStackContext::TraceFailure(v35, "mkvparser::ParseElementHeader", 602, -1072875842);
            }
            if ( g_wppLevels )
            {
              v16 = 51;
              goto LABEL_70;
            }
          }
        }
        else
        {
          v29 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26, v27, v28);
            CallStackTracing::s_wpInstance = v30;
            if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
            {
              v29 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v29 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v29 + 8) )
          {
            v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
            if ( *((_DWORD *)v31 + 499) != ID )
              CallStackContext::TraceFailure(v31, "mkvparser::ParseElementHeader", 595, ID);
          }
          if ( g_wppLevels )
          {
            v16 = 50;
            goto LABEL_70;
          }
        }
      }
      else
      {
        v23 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17, v18, v19);
          CallStackTracing::s_wpInstance = v24;
          if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
          {
            v23 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v23 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        ID = -1072875842;
        if ( *((_BYTE *)v23 + 8) )
        {
          v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
          if ( *((_DWORD *)v25 + 499) != -1072875842 )
            CallStackContext::TraceFailure(v25, "mkvparser::ParseElementHeader", 592, -1072875842);
        }
        if ( g_wppLevels )
        {
          v16 = 49;
          goto LABEL_70;
        }
      }
    }
    else
    {
      v20 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17, v18, v19);
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
        if ( *((_DWORD *)v22 + 499) != ID )
          CallStackContext::TraceFailure(v22, "mkvparser::ParseElementHeader", 586, ID);
      }
      if ( g_wppLevels )
      {
        v16 = 48;
        goto LABEL_70;
      }
    }
  }
  else
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v41, "mkvparser::ParseElementHeader", 581);
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v10, v11);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    ID = -1072875842;
    if ( *((_BYTE *)v12 + 8) )
    {
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)v15 + 499) != -1072875842 )
        CallStackContext::TraceFailure(v15, "mkvparser::ParseElementHeader", 581, -1072875842);
    }
    if ( g_wppLevels )
    {
      v16 = 47;
LABEL_70:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids, 0, ID);
    }
  }
LABEL_72:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v41);
  return (unsigned int)ID;
}

```

## disassembly

```asm
0x1800a1710  mov     [rsp+arg_0], rbx
0x1800a1715  mov     [rsp+arg_8], rbp
0x1800a171a  push    rsi
0x1800a171b  push    rdi
0x1800a171c  push    r14
0x1800a171e  sub     rsp, 40h
0x1800a1722  mov     rbx, r9
0x1800a1725  mov     rsi, r8
0x1800a1728  mov     rdi, rdx
0x1800a172b  mov     r14, rcx
0x1800a172e  test    r8, r8
0x1800a1731  js      loc_1800A17E9
0x1800a1737  cmp     [rdx], r8
0x1800a173a  jl      loc_1800A17E9
0x1800a1740  mov     edi, 245h
0x1800a1745  lea     rbp, aMkvparserParse; "mkvparser::ParseElementHeader"
0x1800a174c  mov     r8d, edi; int
0x1800a174f  lea     rcx, [rsp+58h+arg_10]; this
0x1800a1754  mov     rdx, rbp; char *
0x1800a1757  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a175c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1763  test    rcx, rcx
0x1800a1766  jnz     short loc_1800A17A9
0x1800a1768  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a176e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1775  mov     rcx, rax
0x1800a1778  test    rax, rax
0x1800a177b  jz      short loc_1800A179B
0x1800a177d  mov     rax, [rax]
0x1800a1780  mov     edx, 7F0h
0x1800a1785  mov     rax, [rax+8]
0x1800a1789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a178e  test    eax, eax
0x1800a1790  jz      short loc_1800A179B
0x1800a1792  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1799  jmp     short loc_1800A17A9
0x1800a179b  lea     rcx, qword_1800D6F70; this
0x1800a17a2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a17a9  cmp     byte ptr [rcx+8], 0
0x1800a17ad  mov     ebx, 0C00D36BEh
0x1800a17b2  jz      short loc_1800A17D2
0x1800a17b4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a17b9  cmp     [rax+7CCh], ebx
0x1800a17bf  jz      short loc_1800A17D2
0x1800a17c1  mov     r9d, ebx; int
0x1800a17c4  mov     r8d, edi; int
0x1800a17c7  mov     rdx, rbp; char *
0x1800a17ca  mov     rcx, rax; this
0x1800a17cd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a17d2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a17d9  jb      loc_1800A1B73
0x1800a17df  mov     edx, 2Fh ; '/'
0x1800a17e4  jmp     loc_1800A1B51
0x1800a17e9  lea     rbp, aMkvparserParse; "mkvparser::ParseElementHeader"
0x1800a17f0  mov     dword ptr [rsp+58h+var_28], 0
0x1800a17f8  mov     rdx, rbp; char *
0x1800a17fb  lea     rcx, [rsp+58h+arg_10]; this
0x1800a1800  mov     r8d, 24Ah; int
0x1800a1806  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a180b  mov     rdx, [rdi]; struct mkvparser::IMkvReader *
0x1800a180e  lea     r9, [rsp+58h+var_28]; __int64 *
0x1800a1813  mov     r8, rbx; __int64
0x1800a1816  mov     rcx, r14; this
0x1800a1819  call    ?ReadID@mkvparser@@YAJPEAUIMkvReader@1@_JAEA_JAEAJ@Z; mkvparser::ReadID(mkvparser::IMkvReader *,__int64,__int64 &,long &)
0x1800a181e  mov     ebx, eax
0x1800a1820  test    eax, eax
0x1800a1822  jns     loc_1800A18B3
0x1800a1828  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a182f  test    rcx, rcx
0x1800a1832  jnz     short loc_1800A1875
0x1800a1834  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a183a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1841  mov     rcx, rax
0x1800a1844  test    rax, rax
0x1800a1847  jz      short loc_1800A1867
0x1800a1849  mov     rax, [rax]
0x1800a184c  mov     edx, 7F0h
0x1800a1851  mov     rax, [rax+8]
0x1800a1855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a185a  test    eax, eax
0x1800a185c  jz      short loc_1800A1867
0x1800a185e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1865  jmp     short loc_1800A1875
0x1800a1867  lea     rcx, qword_1800D6F70; this
0x1800a186e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1875  cmp     byte ptr [rcx+8], 0
0x1800a1879  jz      short loc_1800A189C
0x1800a187b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a1880  cmp     [rax+7CCh], ebx
0x1800a1886  jz      short loc_1800A189C
0x1800a1888  mov     r9d, ebx; int
0x1800a188b  mov     r8d, 24Ah; int
0x1800a1891  mov     rdx, rbp; char *
0x1800a1894  mov     rcx, rax; this
0x1800a1897  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a189c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a18a3  jb      loc_1800A1B73
0x1800a18a9  mov     edx, 30h ; '0'
0x1800a18ae  jmp     loc_1800A1B51
0x1800a18b3  movsxd  rax, dword ptr [rsp+58h+var_28]
0x1800a18b8  add     [rdi], rax
0x1800a18bb  test    rsi, rsi
0x1800a18be  js      loc_1800A195D
0x1800a18c4  cmp     [rdi], rsi
0x1800a18c7  jl      loc_1800A195D
0x1800a18cd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a18d4  test    rcx, rcx
0x1800a18d7  jnz     short loc_1800A191A
0x1800a18d9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a18df  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a18e6  mov     rcx, rax
0x1800a18e9  test    rax, rax
0x1800a18ec  jz      short loc_1800A190C
0x1800a18ee  mov     rax, [rax]
0x1800a18f1  mov     edx, 7F0h
0x1800a18f6  mov     rax, [rax+8]
0x1800a18fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a18ff  test    eax, eax
0x1800a1901  jz      short loc_1800A190C
0x1800a1903  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a190a  jmp     short loc_1800A191A
0x1800a190c  lea     rcx, qword_1800D6F70; this
0x1800a1913  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a191a  cmp     byte ptr [rcx+8], 0
0x1800a191e  mov     ebx, 0C00D36BEh
0x1800a1923  jz      short loc_1800A1946
0x1800a1925  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a192a  cmp     [rax+7CCh], ebx
0x1800a1930  jz      short loc_1800A1946
0x1800a1932  mov     r9d, ebx; int
0x1800a1935  mov     r8d, 250h; int
0x1800a193b  mov     rdx, rbp; char *
0x1800a193e  mov     rcx, rax; this
0x1800a1941  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a1946  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a194d  jb      loc_1800A1B73
0x1800a1953  mov     edx, 31h ; '1'
0x1800a1958  jmp     loc_1800A1B51
0x1800a195d  mov     r8, [rsp+58h+arg_20]; __int64
0x1800a1965  lea     r9, [rsp+58h+var_28]; __int64 *
0x1800a196a  mov     rdx, [rdi]; struct mkvparser::IMkvReader *
0x1800a196d  mov     rcx, r14; this
0x1800a1970  call    ?ReadUInt@mkvparser@@YAJPEAUIMkvReader@1@_JAEA_JAEAJ@Z; mkvparser::ReadUInt(mkvparser::IMkvReader *,__int64,__int64 &,long &)
0x1800a1975  mov     ebx, eax
0x1800a1977  test    eax, eax
0x1800a1979  jns     loc_1800A1A0A
0x1800a197f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1986  test    rcx, rcx
0x1800a1989  jnz     short loc_1800A19CC
0x1800a198b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a1991  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1998  mov     rcx, rax
0x1800a199b  test    rax, rax
0x1800a199e  jz      short loc_1800A19BE
0x1800a19a0  mov     rax, [rax]
0x1800a19a3  mov     edx, 7F0h
0x1800a19a8  mov     rax, [rax+8]
0x1800a19ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a19b1  test    eax, eax
0x1800a19b3  jz      short loc_1800A19BE
0x1800a19b5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a19bc  jmp     short loc_1800A19CC
0x1800a19be  lea     rcx, qword_1800D6F70; this
0x1800a19c5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a19cc  cmp     byte ptr [rcx+8], 0
0x1800a19d0  jz      short loc_1800A19F3
0x1800a19d2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a19d7  cmp     [rax+7CCh], ebx
0x1800a19dd  jz      short loc_1800A19F3
0x1800a19df  mov     r9d, ebx; int
0x1800a19e2  mov     r8d, 253h; int
0x1800a19e8  mov     rdx, rbp; char *
0x1800a19eb  mov     rcx, rax; this
0x1800a19ee  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a19f3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a19fa  jb      loc_1800A1B73
0x1800a1a00  mov     edx, 32h ; '2'
0x1800a1a05  jmp     loc_1800A1B51
0x1800a1a0a  movsxd  rdx, dword ptr [rsp+58h+var_28]
0x1800a1a0f  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800a1a19  add     rdx, [rdi]
0x1800a1a1c  cmp     rdx, rax
0x1800a1a1f  jbe     loc_1800A1AB5
0x1800a1a25  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1a2c  test    rcx, rcx
0x1800a1a2f  jnz     short loc_1800A1A72
0x1800a1a31  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a1a37  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1a3e  mov     rcx, rax
0x1800a1a41  test    rax, rax
0x1800a1a44  jz      short loc_1800A1A64
0x1800a1a46  mov     rax, [rax]
0x1800a1a49  mov     edx, 7F0h
0x1800a1a4e  mov     rax, [rax+8]
0x1800a1a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1a57  test    eax, eax
0x1800a1a59  jz      short loc_1800A1A64
0x1800a1a5b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1a62  jmp     short loc_1800A1A72
0x1800a1a64  lea     rcx, qword_1800D6F70; this
0x1800a1a6b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1a72  cmp     byte ptr [rcx+8], 0
0x1800a1a76  mov     ebx, 0C00D36BEh
0x1800a1a7b  jz      short loc_1800A1A9E
0x1800a1a7d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a1a82  cmp     [rax+7CCh], ebx
0x1800a1a88  jz      short loc_1800A1A9E
0x1800a1a8a  mov     r9d, ebx; int
0x1800a1a8d  mov     r8d, 25Ah; int
0x1800a1a93  mov     rdx, rbp; char *
0x1800a1a96  mov     rcx, rax; this
0x1800a1a99  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a1a9e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a1aa5  jb      loc_1800A1B73
0x1800a1aab  mov     edx, 33h ; '3'
0x1800a1ab0  jmp     loc_1800A1B51
0x1800a1ab5  mov     [rdi], rdx
0x1800a1ab8  test    rsi, rsi
0x1800a1abb  js      loc_1800A1B71
0x1800a1ac1  cmp     rdx, rsi
0x1800a1ac4  jle     loc_1800A1B71
0x1800a1aca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1ad1  test    rcx, rcx
0x1800a1ad4  jnz     short loc_1800A1B17
0x1800a1ad6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a1adc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1ae3  mov     rcx, rax
0x1800a1ae6  test    rax, rax
0x1800a1ae9  jz      short loc_1800A1B09
0x1800a1aeb  mov     rax, [rax]
0x1800a1aee  mov     edx, 7F0h
0x1800a1af3  mov     rax, [rax+8]
0x1800a1af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1afc  test    eax, eax
0x1800a1afe  jz      short loc_1800A1B09
0x1800a1b00  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1b07  jmp     short loc_1800A1B17
0x1800a1b09  lea     rcx, qword_1800D6F70; this
0x1800a1b10  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1b17  cmp     byte ptr [rcx+8], 0
0x1800a1b1b  mov     ebx, 0C00D36BEh
0x1800a1b20  jz      short loc_1800A1B43
0x1800a1b22  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a1b27  cmp     [rax+7CCh], ebx
0x1800a1b2d  jz      short loc_1800A1B43
0x1800a1b2f  mov     r9d, ebx; int
0x1800a1b32  mov     r8d, 263h; int
0x1800a1b38  mov     rdx, rbp; char *
0x1800a1b3b  mov     rcx, rax; this
0x1800a1b3e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a1b43  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a1b4a  jb      short loc_1800A1B73
0x1800a1b4c  mov     edx, 34h ; '4'
0x1800a1b51  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a1b58  lea     r8, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids
0x1800a1b5f  xor     r9d, r9d
0x1800a1b62  mov     [rsp+58h+var_38], ebx
0x1800a1b66  mov     rcx, [rcx+10h]
0x1800a1b6a  call    WPP_SF_qD
0x1800a1b6f  jmp     short loc_1800A1B73
0x1800a1b71  xor     ebx, ebx
0x1800a1b73  lea     rcx, [rsp+58h+arg_10]; this
0x1800a1b78  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a1b7d  mov     rbp, [rsp+58h+arg_8]
0x1800a1b82  mov     eax, ebx
0x1800a1b84  mov     rbx, [rsp+58h+arg_0]
0x1800a1b89  add     rsp, 40h
0x1800a1b8d  pop     r14
0x1800a1b8f  pop     rdi
0x1800a1b90  pop     rsi
0x1800a1b91  retn
```
