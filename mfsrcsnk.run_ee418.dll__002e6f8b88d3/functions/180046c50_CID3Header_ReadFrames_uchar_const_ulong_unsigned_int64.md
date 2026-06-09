# CID3Header::ReadFrames(uchar const *,ulong,unsigned __int64 *)

- ea: `0x180046c50`
- end: `0x18004712f`
- name: `?ReadFrames@CID3Header@@AEAAJPEBEKPEA_K@Z`
- size: `1247`
- prototype: `__int64 __fastcall(CID3Header *__hidden this, const unsigned __int8 *, unsigned int, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180064ea0`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180046c50`
- `0x180047138`
- `0x180073b14`
- `0x1801095a8`
- `0x1801099f0`
- `0x18011e37c`
- `0x18016b488`
- `0x18016c554`
- `0x18016c584`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180046e0f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180046e0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046e01`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046e01`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046cc7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046f04`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046f93`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047032`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046cc7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046f04`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046f93`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047032`

## string_xrefs

- `0x180046c7c`: `CID3Header::ReadFrames`
- `0x180046d1e`: `CID3Header::ReadFrames`
- `0x180046f5b`: `CID3Header::ReadFrames`
- `0x180046fea`: `CID3Header::ReadFrames`
- `0x180047089`: `CID3Header::ReadFrames`

## pseudocode

```c
__int64 __fastcall CID3Header::ReadFrames(
        CID3Header *this,
        const unsigned __int8 *a2,
        unsigned int a3,
        unsigned __int64 *a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned int v11; // ebp
  wchar_t *v12; // rcx
  int v13; // esi
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  unsigned int *v16; // rbx
  CID3Frame *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  CID3Frame *v21; // rax
  CID3Frame *v22; // r14
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // r15
  SIZE_T v27; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v29; // rdx
  __int64 v30; // r8
  _QWORD *v31; // r9
  __int64 i; // r8
  __int64 v33; // rdx
  _QWORD *v34; // rdx
  CID3Frame **v35; // rcx
  __int64 v36; // rax
  CID3Frame *v37; // rcx
  char FileSpace; // al
  char v39; // r8
  wchar_t *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // rdx
  wchar_t *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  wchar_t *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v51[8]; // [rsp+40h] [rbp-58h] BYREF
  CID3Frame *v52; // [rsp+48h] [rbp-50h] BYREF
  unsigned int v53; // [rsp+50h] [rbp-48h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v51, "CID3Header::ReadFrames", 1018);
  *a4 = 0;
  v11 = *((_DWORD *)this + 133) - *((_DWORD *)this + 136);
  v53 = 0;
  if ( a3 >= v11 )
  {
    v13 = 0;
    v16 = (unsigned int *)((char *)this + 496);
    while ( v11 )
    {
      v17 = (CID3Frame *)operator new(0x90u);
      if ( !v17 )
      {
        v52 = 0;
LABEL_49:
        v47 = (wchar_t *)CallStackTracing::s_wpInstance;
        v13 = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19, v20);
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
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v47);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "CID3Header::ReadFrames", 1035, -2147024882);
        }
        if ( g_wppLevels )
        {
          v43 = 91;
LABEL_59:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v43,
            &WPP_37a327c391a7379b3721a372142db134_Traceguids,
            this,
            -2147024882);
        }
LABEL_60:
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v52);
        goto LABEL_63;
      }
      v21 = CID3Frame::CID3Frame(v17, this);
      v52 = v21;
      v22 = v21;
      if ( !v21 )
        goto LABEL_49;
      (*(void (__fastcall **)(CID3Frame *))(*(_QWORD *)v21 + 8LL))(v21);
      v13 = (*(__int64 (__fastcall **)(CID3Frame *, const unsigned __int8 *, _QWORD, unsigned int *))(*(_QWORD *)v22 + 40LL))(
              v22,
              a2,
              v11,
              &v53);
      if ( v13 < 0 )
      {
        v44 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24, v25);
          CallStackTracing::s_wpInstance = v45;
          if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
          {
            v44 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v44 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v44 + 8) )
        {
          v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
          if ( *((_DWORD *)v46 + 499) != v13 )
            CallStackContext::TraceFailure(v46, "CID3Header::ReadFrames", 1037, v13);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            92,
            &WPP_37a327c391a7379b3721a372142db134_Traceguids,
            this,
            v13);
        goto LABEL_60;
      }
      v26 = v53;
      *a4 += v53;
      v11 -= v53;
      if ( !*((_QWORD *)this + 7) )
      {
        v27 = 24LL * (unsigned int)(*((_DWORD *)this + 18) - 1) + 32;
        ProcessHeap = GetProcessHeap();
        v31 = HeapAlloc(ProcessHeap, 0, v27);
        if ( !v31 )
        {
          v40 = (wchar_t *)CallStackTracing::s_wpInstance;
          v13 = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30, 0);
            CallStackTracing::s_wpInstance = v41;
            if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
            {
              v40 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v40 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v40 + 8) )
          {
            v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
            if ( *((_DWORD *)v42 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v42, "CID3Header::ReadFrames", 1045, -2147024882);
          }
          if ( g_wppLevels )
          {
            v43 = 93;
            goto LABEL_59;
          }
          goto LABEL_60;
        }
        for ( i = 0; (unsigned int)i < *((_DWORD *)this + 18); *((_QWORD *)this + 7) = v34 )
        {
          v33 = (unsigned int)i + 1LL + 2 * i;
          i = (unsigned int)(i + 1);
          v34 = &v31[v33];
          v34[1] = *((_QWORD *)this + 7);
        }
        *v31 = *((_QWORD *)this + 8);
        *((_QWORD *)this + 8) = v31;
      }
      v35 = (CID3Frame **)*((_QWORD *)this + 7);
      *((_QWORD *)this + 7) = v35[1];
      *v35 = v22;
      v35[1] = 0;
      v35[2] = (CID3Frame *)*((_QWORD *)this + 61);
      v36 = *((_QWORD *)this + 61);
      if ( v36 )
        *(_QWORD *)(v36 + 8) = v35;
      else
        *((_QWORD *)this + 60) = v35;
      v16 = (unsigned int *)((char *)this + 496);
      *((_QWORD *)this + 61) = v35;
      ++*((_DWORD *)this + 124);
      a2 += v26;
      if ( g_wppLevels >= 0x20u )
      {
        CID3Frame::GetStorageSpace(v22);
        FileSpace = CID3Frame::GetFileSpace(v37);
        WPP_SF_qsdd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v22 + 56, FileSpace, v39);
      }
    }
    if ( g_wppLevels >= 8u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, &WPP_37a327c391a7379b3721a372142db134_Traceguids, *v16);
  }
  else
  {
    v12 = (wchar_t *)CallStackTracing::s_wpInstance;
    v13 = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9, v10);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v12 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)v15 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v15, "CID3Header::ReadFrames", 1029, -2147024809);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        90,
        &WPP_37a327c391a7379b3721a372142db134_Traceguids,
        this,
        -2147024809);
  }
LABEL_63:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v51);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180046c50  mov     [rsp+arg_10], rbx
0x180046c55  push    rbp
0x180046c56  push    rsi
0x180046c57  push    rdi
0x180046c58  push    r12
0x180046c5a  push    r13
0x180046c5c  push    r14
0x180046c5e  push    r15
0x180046c60  sub     rsp, 60h
0x180046c64  mov     rax, cs:__security_cookie
0x180046c6b  xor     rax, rsp
0x180046c6e  mov     [rsp+98h+var_40], rax
0x180046c73  mov     ebx, r8d
0x180046c76  mov     r12, rdx
0x180046c79  mov     rdi, rcx
0x180046c7c  lea     rdx, aCid3headerRead; "CID3Header::ReadFrames"
0x180046c83  mov     r8d, 3FAh; int
0x180046c89  lea     rcx, [rsp+98h+var_58]; this
0x180046c8e  mov     r13, r9
0x180046c91  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180046c96  xor     r15d, r15d
0x180046c99  mov     [r13+0], r15
0x180046c9d  mov     ebp, [rdi+214h]
0x180046ca3  sub     ebp, [rdi+220h]
0x180046ca9  mov     [rsp+98h+var_48], r15d
0x180046cae  cmp     ebx, ebp
0x180046cb0  jnb     loc_180046D68
0x180046cb6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046cbd  mov     esi, 80070057h
0x180046cc2  test    rcx, rcx
0x180046cc5  jnz     short loc_180046D08
0x180046cc7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180046ccd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180046cd4  mov     rcx, rax
0x180046cd7  test    rax, rax
0x180046cda  jz      short loc_180046CFA
0x180046cdc  mov     rax, [rax]
0x180046cdf  mov     edx, 7F0h
0x180046ce4  mov     rax, [rax+8]
0x180046ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046ced  test    eax, eax
0x180046cef  jz      short loc_180046CFA
0x180046cf1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046cf8  jmp     short loc_180046D08
0x180046cfa  lea     rcx, qword_1801B07E0; this
0x180046d01  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180046d08  cmp     [rcx+8], r15b
0x180046d0c  jz      short loc_180046D33
0x180046d0e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180046d13  cmp     [rax+7CCh], esi
0x180046d19  jz      short loc_180046D33
0x180046d1b  mov     r9d, esi; int
0x180046d1e  lea     rdx, aCid3headerRead; "CID3Header::ReadFrames"
0x180046d25  mov     r8d, 405h; int
0x180046d2b  mov     rcx, rax; this
0x180046d2e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180046d33  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180046d3a  jb      loc_1800470FE
0x180046d40  mov     rcx, cs:WPP_GLOBAL_Control
0x180046d47  lea     r8, WPP_37a327c391a7379b3721a372142db134_Traceguids
0x180046d4e  mov     edx, 5Ah ; 'Z'
0x180046d53  mov     dword ptr [rsp+98h+var_78], esi
0x180046d57  mov     r9, rdi
0x180046d5a  mov     rcx, [rcx+10h]
0x180046d5e  call    WPP_SF_qD
0x180046d63  jmp     loc_1800470FE
0x180046d68  mov     esi, r15d
0x180046d6b  lea     rbx, [rdi+1F0h]
0x180046d72  test    ebp, ebp
0x180046d74  jz      loc_1800470D6
0x180046d7a  mov     ecx, 90h; Size
0x180046d7f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180046d84  test    rax, rax
0x180046d87  jz      loc_18004701A
0x180046d8d  mov     rdx, rdi; struct CID3Header *
0x180046d90  mov     rcx, rax; this
0x180046d93  call    ??0CID3Frame@@QEAA@PEAVCID3Header@@@Z; CID3Frame::CID3Frame(CID3Header *)
0x180046d98  mov     [rsp+98h+var_50], rax
0x180046d9d  mov     r14, rax
0x180046da0  test    rax, rax
0x180046da3  jz      loc_18004701F
0x180046da9  mov     rax, [rax]
0x180046dac  mov     rcx, r14
0x180046daf  mov     rax, [rax+8]
0x180046db3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046db8  mov     rax, [r14]
0x180046dbb  lea     r9, [rsp+98h+var_48]
0x180046dc0  mov     r8d, ebp
0x180046dc3  mov     rdx, r12
0x180046dc6  mov     rcx, r14
0x180046dc9  mov     rax, [rax+28h]
0x180046dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046dd2  mov     esi, eax
0x180046dd4  test    eax, eax
0x180046dd6  js      loc_180046F87
0x180046ddc  mov     r15d, [rsp+98h+var_48]
0x180046de1  add     [r13+0], r15
0x180046de5  sub     ebp, [rsp+98h+var_48]
0x180046de9  cmp     qword ptr [rdi+38h], 0
0x180046dee  jnz     short loc_180046E58
0x180046df0  mov     eax, [rdi+48h]
0x180046df3  dec     eax
0x180046df5  lea     rcx, [rax+rax*2]
0x180046df9  lea     rbx, ds:20h[rcx*8]
0x180046e01  call    cs:__imp_GetProcessHeap
0x180046e07  mov     r8, rbx; dwBytes
0x180046e0a  xor     edx, edx; dwFlags
0x180046e0c  mov     rcx, rax; hHeap
0x180046e0f  call    cs:__imp_HeapAlloc
0x180046e15  mov     r9, rax
0x180046e18  test    rax, rax
0x180046e1b  jz      loc_180046EF1
0x180046e21  xor     r8d, r8d
0x180046e24  cmp     [rdi+48h], r8d
0x180046e28  jbe     short loc_180046E4D
0x180046e2a  mov     rax, [rdi+38h]
0x180046e2e  mov     edx, r8d
0x180046e31  inc     rdx
0x180046e34  lea     rdx, [rdx+r8*2]
0x180046e38  inc     r8d
0x180046e3b  lea     rdx, [r9+rdx*8]
0x180046e3f  mov     [rdx+8], rax
0x180046e43  mov     [rdi+38h], rdx
0x180046e47  cmp     r8d, [rdi+48h]
0x180046e4b  jb      short loc_180046E2A
0x180046e4d  mov     rax, [rdi+40h]
0x180046e51  mov     [r9], rax
0x180046e54  mov     [rdi+40h], r9
0x180046e58  mov     rcx, [rdi+38h]
0x180046e5c  mov     rax, [rcx+8]
0x180046e60  mov     [rdi+38h], rax
0x180046e64  mov     [rcx], r14
0x180046e67  mov     qword ptr [rcx+8], 0
0x180046e6f  mov     rax, [rdi+1E8h]
0x180046e76  mov     [rcx+10h], rax
0x180046e7a  mov     rax, [rdi+1E8h]
0x180046e81  test    rax, rax
0x180046e84  jz      short loc_180046E8C
0x180046e86  mov     [rax+8], rcx
0x180046e8a  jmp     short loc_180046E93
0x180046e8c  mov     [rdi+1E0h], rcx
0x180046e93  lea     rbx, [rdi+1F0h]
0x180046e9a  mov     [rdi+1E8h], rcx
0x180046ea1  inc     dword ptr [rbx]
0x180046ea3  add     r12, r15
0x180046ea6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x180046ead  jb      short loc_180046EE9
0x180046eaf  mov     rcx, r14; this
0x180046eb2  call    ?GetStorageSpace@CID3Frame@@QEAAKXZ; CID3Frame::GetStorageSpace(void)
0x180046eb7  mov     r8d, eax
0x180046eba  call    ?GetFileSpace@CID3Frame@@QEAAKXZ; CID3Frame::GetFileSpace(void)
0x180046ebf  mov     dword ptr [rsp+98h+var_68], r8d; char
0x180046ec4  lea     rcx, [r14+38h]
0x180046ec8  mov     dword ptr [rsp+98h+var_70], eax; char
0x180046ecc  mov     edx, 5Eh ; '^'
0x180046ed1  mov     [rsp+98h+var_78], rcx; __int64
0x180046ed6  mov     r9, rdi
0x180046ed9  mov     rcx, cs:WPP_GLOBAL_Control
0x180046ee0  mov     rcx, [rcx+10h]; LoggerHandle
0x180046ee4  call    WPP_SF_qsdd
0x180046ee9  xor     r15d, r15d
0x180046eec  jmp     loc_180046D72
0x180046ef1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046ef8  mov     ebx, 8007000Eh
0x180046efd  mov     esi, ebx
0x180046eff  test    rcx, rcx
0x180046f02  jnz     short loc_180046F45
0x180046f04  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180046f0a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180046f11  mov     rcx, rax
0x180046f14  test    rax, rax
0x180046f17  jz      short loc_180046F37
0x180046f19  mov     rax, [rax]
0x180046f1c  mov     edx, 7F0h
0x180046f21  mov     rax, [rax+8]
0x180046f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f2a  test    eax, eax
0x180046f2c  jz      short loc_180046F37
0x180046f2e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046f35  jmp     short loc_180046F45
0x180046f37  lea     rcx, qword_1801B07E0; this
0x180046f3e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180046f45  cmp     byte ptr [rcx+8], 0
0x180046f49  jz      short loc_180046F70
0x180046f4b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180046f50  cmp     [rax+7CCh], ebx
0x180046f56  jz      short loc_180046F70
0x180046f58  mov     r9d, ebx; int
0x180046f5b  lea     rdx, aCid3headerRead; "CID3Header::ReadFrames"
0x180046f62  mov     r8d, 415h; int
0x180046f68  mov     rcx, rax; this
0x180046f6b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180046f70  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180046f77  jb      loc_1800470CA
0x180046f7d  mov     edx, 5Dh ; ']'
0x180046f82  jmp     loc_1800470AC
0x180046f87  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046f8e  test    rcx, rcx
0x180046f91  jnz     short loc_180046FD4
0x180046f93  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180046f99  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180046fa0  mov     rcx, rax
0x180046fa3  test    rax, rax
0x180046fa6  jz      short loc_180046FC6
0x180046fa8  mov     rax, [rax]
0x180046fab  mov     edx, 7F0h
0x180046fb0  mov     rax, [rax+8]
0x180046fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046fb9  test    eax, eax
0x180046fbb  jz      short loc_180046FC6
0x180046fbd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046fc4  jmp     short loc_180046FD4
0x180046fc6  lea     rcx, qword_1801B07E0; this
0x180046fcd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180046fd4  cmp     [rcx+8], r15b
0x180046fd8  jz      short loc_180046FFF
0x180046fda  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180046fdf  cmp     [rax+7CCh], esi
0x180046fe5  jz      short loc_180046FFF
0x180046fe7  mov     r9d, esi; int
0x180046fea  lea     rdx, aCid3headerRead; "CID3Header::ReadFrames"
0x180046ff1  mov     r8d, 40Dh; int
0x180046ff7  mov     rcx, rax; this
0x180046ffa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180046fff  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180047006  jb      loc_1800470CA
0x18004700c  mov     edx, 5Ch ; '\'
0x180047011  mov     dword ptr [rsp+98h+var_78], esi
0x180047015  jmp     loc_1800470B0
0x18004701a  mov     [rsp+98h+var_50], r15
0x18004701f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180047026  mov     ebx, 8007000Eh
0x18004702b  mov     esi, ebx
0x18004702d  test    rcx, rcx
0x180047030  jnz     short loc_180047073
0x180047032  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180047038  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004703f  mov     rcx, rax
0x180047042  test    rax, rax
0x180047045  jz      short loc_180047065
0x180047047  mov     rax, [rax]
0x18004704a  mov     edx, 7F0h
0x18004704f  mov     rax, [rax+8]
0x180047053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047058  test    eax, eax
0x18004705a  jz      short loc_180047065
0x18004705c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180047063  jmp     short loc_180047073
0x180047065  lea     rcx, qword_1801B07E0; this
0x18004706c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180047073  cmp     [rcx+8], r15b
0x180047077  jz      short loc_18004709E
0x180047079  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004707e  cmp     [rax+7CCh], ebx
0x180047084  jz      short loc_18004709E
0x180047086  mov     r9d, ebx; int
0x180047089  lea     rdx, aCid3headerRead; "CID3Header::ReadFrames"
0x180047090  mov     r8d, 40Bh; int
0x180047096  mov     rcx, rax; this
0x180047099  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004709e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800470a5  jb      short loc_1800470CA
0x1800470a7  mov     edx, 5Bh ; '['
0x1800470ac  mov     dword ptr [rsp+98h+var_78], ebx
0x1800470b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800470b7  lea     r8, WPP_37a327c391a7379b3721a372142db134_Traceguids
0x1800470be  mov     r9, rdi
0x1800470c1  mov     rcx, [rcx+10h]
0x1800470c5  call    WPP_SF_qD
0x1800470ca  lea     rcx, [rsp+98h+var_50]; void *
0x1800470cf  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800470d4  jmp     short loc_1800470FE
0x1800470d6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x1800470dd  jb      short loc_1800470FE
0x1800470df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800470e6  lea     r8, WPP_37a327c391a7379b3721a372142db134_Traceguids
0x1800470ed  mov     r9d, [rbx]
0x1800470f0  mov     edx, 5Fh ; '_'
0x1800470f5  mov     rcx, [rcx+10h]
0x1800470f9  call    WPP_SF_d
0x1800470fe  lea     rcx, [rsp+98h+var_58]; this
0x180047103  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180047108  mov     eax, esi
0x18004710a  mov     rcx, [rsp+98h+var_40]
0x18004710f  xor     rcx, rsp; StackCookie
0x180047112  call    __security_check_cookie
0x180047117  mov     rbx, [rsp+98h+arg_10]
0x18004711f  add     rsp, 60h
0x180047123  pop     r15
0x180047125  pop     r14
0x180047127  pop     r13
0x180047129  pop     r12
0x18004712b  pop     rdi
0x18004712c  pop     rsi
0x18004712d  pop     rbp
0x18004712e  retn
```
