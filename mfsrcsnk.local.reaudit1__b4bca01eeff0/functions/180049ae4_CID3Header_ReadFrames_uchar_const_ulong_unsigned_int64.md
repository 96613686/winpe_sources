# CID3Header::ReadFrames(uchar const *,ulong,unsigned __int64 *)

- ea: `0x180049ae4`
- end: `0x180049fe8`
- name: `?ReadFrames@CID3Header@@AEAAJPEBEKPEA_K@Z`
- size: `1284`
- prototype: `__int64 __fastcall(CID3Header *__hidden this, const unsigned __int8 *, unsigned int, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180065850`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x180049ae4`
- `0x180049ff0`
- `0x180079680`
- `0x180110a94`
- `0x180110ed0`
- `0x180124a8c`
- `0x180174544`
- `0x180175650`
- `0x180175680`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049caf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049caf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049c9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049c9b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049b5b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049daa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049e3f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049ee4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049b5b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049daa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049e3f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049ee4`

## string_xrefs

- `0x180049b10`: `CID3Header::ReadFrames`
- `0x180049bb8`: `CID3Header::ReadFrames`
- `0x180049e07`: `CID3Header::ReadFrames`
- `0x180049e9c`: `CID3Header::ReadFrames`
- `0x180049f41`: `CID3Header::ReadFrames`

## pseudocode

```c
__int64 __fastcall CID3Header::ReadFrames(
        CID3Header *this,
        const unsigned __int8 *a2,
        unsigned int a3,
        unsigned __int64 *a4)
{
  __int64 v8; // rdx
  unsigned int v9; // ebp
  wchar_t *v10; // rcx
  int v11; // esi
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  unsigned int *v14; // rbx
  CID3Frame *v15; // rax
  __int64 v16; // rdx
  CID3Frame *v17; // rax
  CID3Frame *v18; // r14
  __int64 v19; // rdx
  __int64 v20; // r15
  SIZE_T v21; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v23; // rdx
  _QWORD *v24; // r9
  __int64 i; // r8
  __int64 v26; // rdx
  _QWORD *v27; // rdx
  CID3Frame **v28; // rcx
  __int64 v29; // rax
  CID3Frame *v30; // rcx
  char FileSpace; // al
  char v32; // r8
  wchar_t *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 v36; // rdx
  wchar_t *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  wchar_t *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v44[8]; // [rsp+40h] [rbp-58h] BYREF
  CID3Frame *v45; // [rsp+48h] [rbp-50h] BYREF
  unsigned int v46; // [rsp+50h] [rbp-48h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v44, "CID3Header::ReadFrames", 1018);
  *a4 = 0;
  v9 = *((_DWORD *)this + 133) - *((_DWORD *)this + 136);
  v46 = 0;
  if ( a3 >= v9 )
  {
    v11 = 0;
    v14 = (unsigned int *)((char *)this + 496);
    while ( v9 )
    {
      v15 = (CID3Frame *)operator new(0x90u);
      if ( !v15 )
      {
        v45 = 0;
LABEL_49:
        v40 = (wchar_t *)CallStackTracing::s_wpInstance;
        v11 = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
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
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "CID3Header::ReadFrames", 1035, -2147024882);
        }
        if ( g_wppLevels )
        {
          v36 = 91;
LABEL_59:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v36,
            &WPP_37a327c391a7379b3721a372142db134_Traceguids,
            this,
            -2147024882);
        }
LABEL_60:
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v45);
        goto LABEL_63;
      }
      v17 = CID3Frame::CID3Frame(v15, this);
      v45 = v17;
      v18 = v17;
      if ( !v17 )
        goto LABEL_49;
      (*(void (__fastcall **)(CID3Frame *))(*(_QWORD *)v17 + 8LL))(v17);
      v11 = (*(__int64 (__fastcall **)(CID3Frame *, const unsigned __int8 *, _QWORD, unsigned int *))(*(_QWORD *)v18 + 40LL))(
              v18,
              a2,
              v9,
              &v46);
      if ( v11 < 0 )
      {
        v37 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
          CallStackTracing::s_wpInstance = v38;
          if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
          {
            v37 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v37 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v37 + 8) )
        {
          v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
          if ( *((_DWORD *)v39 + 499) != v11 )
            CallStackContext::TraceFailure(v39, "CID3Header::ReadFrames", 1037, v11);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            92,
            &WPP_37a327c391a7379b3721a372142db134_Traceguids,
            this,
            v11);
        goto LABEL_60;
      }
      v20 = v46;
      *a4 += v46;
      v9 -= v46;
      if ( !*((_QWORD *)this + 7) )
      {
        v21 = 24LL * (unsigned int)(*((_DWORD *)this + 18) - 1) + 32;
        ProcessHeap = GetProcessHeap();
        v24 = HeapAlloc(ProcessHeap, 0, v21);
        if ( !v24 )
        {
          v33 = (wchar_t *)CallStackTracing::s_wpInstance;
          v11 = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
            CallStackTracing::s_wpInstance = v34;
            if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
            {
              v33 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v33 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v33 + 8) )
          {
            v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
            if ( *((_DWORD *)v35 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v35, "CID3Header::ReadFrames", 1045, -2147024882);
          }
          if ( g_wppLevels )
          {
            v36 = 93;
            goto LABEL_59;
          }
          goto LABEL_60;
        }
        for ( i = 0; (unsigned int)i < *((_DWORD *)this + 18); *((_QWORD *)this + 7) = v27 )
        {
          v26 = (unsigned int)i + 1LL + 2 * i;
          i = (unsigned int)(i + 1);
          v27 = &v24[v26];
          v27[1] = *((_QWORD *)this + 7);
        }
        *v24 = *((_QWORD *)this + 8);
        *((_QWORD *)this + 8) = v24;
      }
      v28 = (CID3Frame **)*((_QWORD *)this + 7);
      *((_QWORD *)this + 7) = v28[1];
      *v28 = v18;
      v28[1] = 0;
      v28[2] = (CID3Frame *)*((_QWORD *)this + 61);
      v29 = *((_QWORD *)this + 61);
      if ( v29 )
        *(_QWORD *)(v29 + 8) = v28;
      else
        *((_QWORD *)this + 60) = v28;
      v14 = (unsigned int *)((char *)this + 496);
      *((_QWORD *)this + 61) = v28;
      ++*((_DWORD *)this + 124);
      a2 += v20;
      if ( g_wppLevels >= 0x20u )
      {
        CID3Frame::GetStorageSpace(v18);
        FileSpace = CID3Frame::GetFileSpace(v30);
        WPP_SF_qsdd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v18 + 56, FileSpace, v32);
      }
    }
    if ( g_wppLevels >= 8u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, &WPP_37a327c391a7379b3721a372142db134_Traceguids, *v14);
  }
  else
  {
    v10 = (wchar_t *)CallStackTracing::s_wpInstance;
    v11 = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v10 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)v13 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v13, "CID3Header::ReadFrames", 1029, -2147024809);
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
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v44);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180049ae4  mov     [rsp+arg_10], rbx
0x180049ae9  push    rbp
0x180049aea  push    rsi
0x180049aeb  push    rdi
0x180049aec  push    r12
0x180049aee  push    r13
0x180049af0  push    r14
0x180049af2  push    r15
0x180049af4  sub     rsp, 60h
0x180049af8  mov     rax, cs:__security_cookie
0x180049aff  xor     rax, rsp
0x180049b02  mov     [rsp+98h+var_40], rax
0x180049b07  mov     ebx, r8d
0x180049b0a  mov     r12, rdx
0x180049b0d  mov     rdi, rcx
0x180049b10  lea     rdx, aCid3headerRead; "CID3Header::ReadFrames"
0x180049b17  mov     r8d, 3FAh; int
0x180049b1d  lea     rcx, [rsp+98h+var_58]; this
0x180049b22  mov     r13, r9
0x180049b25  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180049b2a  xor     r15d, r15d
0x180049b2d  mov     [r13+0], r15
0x180049b31  mov     ebp, [rdi+214h]
0x180049b37  sub     ebp, [rdi+220h]
0x180049b3d  mov     [rsp+98h+var_48], r15d
0x180049b42  cmp     ebx, ebp
0x180049b44  jnb     loc_180049C02
0x180049b4a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180049b51  mov     esi, 80070057h
0x180049b56  test    rcx, rcx
0x180049b59  jnz     short loc_180049BA2
0x180049b5b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180049b62  nop     dword ptr [rax+rax+00h]
0x180049b67  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180049b6e  mov     rcx, rax
0x180049b71  test    rax, rax
0x180049b74  jz      short loc_180049B94
0x180049b76  mov     rax, [rax]
0x180049b79  mov     edx, 7F0h
0x180049b7e  mov     rax, [rax+8]
0x180049b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b87  test    eax, eax
0x180049b89  jz      short loc_180049B94
0x180049b8b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180049b92  jmp     short loc_180049BA2
0x180049b94  lea     rcx, qword_1801B97E0; this
0x180049b9b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180049ba2  cmp     [rcx+8], r15b
0x180049ba6  jz      short loc_180049BCD
0x180049ba8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180049bad  cmp     [rax+7CCh], esi
0x180049bb3  jz      short loc_180049BCD
0x180049bb5  mov     r9d, esi; int
0x180049bb8  lea     rdx, aCid3headerRead; "CID3Header::ReadFrames"
0x180049bbf  mov     r8d, 405h; int
0x180049bc5  mov     rcx, rax; this
0x180049bc8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180049bcd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180049bd4  jb      loc_180049FB6
0x180049bda  mov     rcx, cs:WPP_GLOBAL_Control
0x180049be1  lea     r8, WPP_37a327c391a7379b3721a372142db134_Traceguids
0x180049be8  mov     edx, 5Ah ; 'Z'
0x180049bed  mov     dword ptr [rsp+98h+var_78], esi
0x180049bf1  mov     r9, rdi
0x180049bf4  mov     rcx, [rcx+10h]
0x180049bf8  call    WPP_SF_qD
0x180049bfd  jmp     loc_180049FB6
0x180049c02  mov     esi, r15d
0x180049c05  lea     rbx, [rdi+1F0h]
0x180049c0c  test    ebp, ebp
0x180049c0e  jz      loc_180049F8E
0x180049c14  mov     ecx, 90h; Size
0x180049c19  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180049c1e  test    rax, rax
0x180049c21  jz      loc_180049ECC
0x180049c27  mov     rdx, rdi; struct CID3Header *
0x180049c2a  mov     rcx, rax; this
0x180049c2d  call    ??0CID3Frame@@QEAA@PEAVCID3Header@@@Z; CID3Frame::CID3Frame(CID3Header *)
0x180049c32  mov     [rsp+98h+var_50], rax
0x180049c37  mov     r14, rax
0x180049c3a  test    rax, rax
0x180049c3d  jz      loc_180049ED1
0x180049c43  mov     rax, [rax]
0x180049c46  mov     rcx, r14
0x180049c49  mov     rax, [rax+8]
0x180049c4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c52  mov     rax, [r14]
0x180049c55  lea     r9, [rsp+98h+var_48]
0x180049c5a  mov     r8d, ebp
0x180049c5d  mov     rdx, r12
0x180049c60  mov     rcx, r14
0x180049c63  mov     rax, [rax+28h]
0x180049c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c6c  mov     esi, eax
0x180049c6e  test    eax, eax
0x180049c70  js      loc_180049E33
0x180049c76  mov     r15d, [rsp+98h+var_48]
0x180049c7b  add     [r13+0], r15
0x180049c7f  sub     ebp, [rsp+98h+var_48]
0x180049c83  cmp     qword ptr [rdi+38h], 0
0x180049c88  jnz     short loc_180049CFE
0x180049c8a  mov     eax, [rdi+48h]
0x180049c8d  dec     eax
0x180049c8f  lea     rcx, [rax+rax*2]
0x180049c93  lea     rbx, ds:20h[rcx*8]
0x180049c9b  call    cs:__imp_GetProcessHeap
0x180049ca2  nop     dword ptr [rax+rax+00h]
0x180049ca7  mov     r8, rbx; dwBytes
0x180049caa  xor     edx, edx; dwFlags
0x180049cac  mov     rcx, rax; hHeap
0x180049caf  call    cs:__imp_HeapAlloc
0x180049cb6  nop     dword ptr [rax+rax+00h]
0x180049cbb  mov     r9, rax
0x180049cbe  test    rax, rax
0x180049cc1  jz      loc_180049D97
0x180049cc7  xor     r8d, r8d
0x180049cca  cmp     [rdi+48h], r8d
0x180049cce  jbe     short loc_180049CF3
0x180049cd0  mov     rax, [rdi+38h]
0x180049cd4  mov     edx, r8d
0x180049cd7  inc     rdx
0x180049cda  lea     rdx, [rdx+r8*2]
0x180049cde  inc     r8d
0x180049ce1  lea     rdx, [r9+rdx*8]
0x180049ce5  mov     [rdx+8], rax
0x180049ce9  mov     [rdi+38h], rdx
0x180049ced  cmp     r8d, [rdi+48h]
0x180049cf1  jb      short loc_180049CD0
0x180049cf3  mov     rax, [rdi+40h]
0x180049cf7  mov     [r9], rax
0x180049cfa  mov     [rdi+40h], r9
0x180049cfe  mov     rcx, [rdi+38h]
0x180049d02  mov     rax, [rcx+8]
0x180049d06  mov     [rdi+38h], rax
0x180049d0a  mov     [rcx], r14
0x180049d0d  mov     qword ptr [rcx+8], 0
0x180049d15  mov     rax, [rdi+1E8h]
0x180049d1c  mov     [rcx+10h], rax
0x180049d20  mov     rax, [rdi+1E8h]
0x180049d27  test    rax, rax
0x180049d2a  jz      short loc_180049D32
0x180049d2c  mov     [rax+8], rcx
0x180049d30  jmp     short loc_180049D39
0x180049d32  mov     [rdi+1E0h], rcx
0x180049d39  lea     rbx, [rdi+1F0h]
0x180049d40  mov     [rdi+1E8h], rcx
0x180049d47  inc     dword ptr [rbx]
0x180049d49  add     r12, r15
0x180049d4c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x180049d53  jb      short loc_180049D8F
0x180049d55  mov     rcx, r14; this
0x180049d58  call    ?GetStorageSpace@CID3Frame@@QEAAKXZ; CID3Frame::GetStorageSpace(void)
0x180049d5d  mov     r8d, eax
0x180049d60  call    ?GetFileSpace@CID3Frame@@QEAAKXZ; CID3Frame::GetFileSpace(void)
0x180049d65  mov     dword ptr [rsp+98h+var_68], r8d; char
0x180049d6a  lea     rcx, [r14+38h]
0x180049d6e  mov     dword ptr [rsp+98h+var_70], eax; char
0x180049d72  mov     edx, 5Eh ; '^'
0x180049d77  mov     [rsp+98h+var_78], rcx; __int64
0x180049d7c  mov     r9, rdi
0x180049d7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180049d86  mov     rcx, [rcx+10h]; LoggerHandle
0x180049d8a  call    WPP_SF_qsdd
0x180049d8f  xor     r15d, r15d
0x180049d92  jmp     loc_180049C0C
0x180049d97  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180049d9e  mov     ebx, 8007000Eh
0x180049da3  mov     esi, ebx
0x180049da5  test    rcx, rcx
0x180049da8  jnz     short loc_180049DF1
0x180049daa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180049db1  nop     dword ptr [rax+rax+00h]
0x180049db6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180049dbd  mov     rcx, rax
0x180049dc0  test    rax, rax
0x180049dc3  jz      short loc_180049DE3
0x180049dc5  mov     rax, [rax]
0x180049dc8  mov     edx, 7F0h
0x180049dcd  mov     rax, [rax+8]
0x180049dd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049dd6  test    eax, eax
0x180049dd8  jz      short loc_180049DE3
0x180049dda  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180049de1  jmp     short loc_180049DF1
0x180049de3  lea     rcx, qword_1801B97E0; this
0x180049dea  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180049df1  cmp     byte ptr [rcx+8], 0
0x180049df5  jz      short loc_180049E1C
0x180049df7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180049dfc  cmp     [rax+7CCh], ebx
0x180049e02  jz      short loc_180049E1C
0x180049e04  mov     r9d, ebx; int
0x180049e07  lea     rdx, aCid3headerRead; "CID3Header::ReadFrames"
0x180049e0e  mov     r8d, 415h; int
0x180049e14  mov     rcx, rax; this
0x180049e17  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180049e1c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180049e23  jb      loc_180049F82
0x180049e29  mov     edx, 5Dh ; ']'
0x180049e2e  jmp     loc_180049F64
0x180049e33  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180049e3a  test    rcx, rcx
0x180049e3d  jnz     short loc_180049E86
0x180049e3f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180049e46  nop     dword ptr [rax+rax+00h]
0x180049e4b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180049e52  mov     rcx, rax
0x180049e55  test    rax, rax
0x180049e58  jz      short loc_180049E78
0x180049e5a  mov     rax, [rax]
0x180049e5d  mov     edx, 7F0h
0x180049e62  mov     rax, [rax+8]
0x180049e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049e6b  test    eax, eax
0x180049e6d  jz      short loc_180049E78
0x180049e6f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180049e76  jmp     short loc_180049E86
0x180049e78  lea     rcx, qword_1801B97E0; this
0x180049e7f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180049e86  cmp     [rcx+8], r15b
0x180049e8a  jz      short loc_180049EB1
0x180049e8c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180049e91  cmp     [rax+7CCh], esi
0x180049e97  jz      short loc_180049EB1
0x180049e99  mov     r9d, esi; int
0x180049e9c  lea     rdx, aCid3headerRead; "CID3Header::ReadFrames"
0x180049ea3  mov     r8d, 40Dh; int
0x180049ea9  mov     rcx, rax; this
0x180049eac  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180049eb1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180049eb8  jb      loc_180049F82
0x180049ebe  mov     edx, 5Ch ; '\'
0x180049ec3  mov     dword ptr [rsp+98h+var_78], esi
0x180049ec7  jmp     loc_180049F68
0x180049ecc  mov     [rsp+98h+var_50], r15
0x180049ed1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180049ed8  mov     ebx, 8007000Eh
0x180049edd  mov     esi, ebx
0x180049edf  test    rcx, rcx
0x180049ee2  jnz     short loc_180049F2B
0x180049ee4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180049eeb  nop     dword ptr [rax+rax+00h]
0x180049ef0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180049ef7  mov     rcx, rax
0x180049efa  test    rax, rax
0x180049efd  jz      short loc_180049F1D
0x180049eff  mov     rax, [rax]
0x180049f02  mov     edx, 7F0h
0x180049f07  mov     rax, [rax+8]
0x180049f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049f10  test    eax, eax
0x180049f12  jz      short loc_180049F1D
0x180049f14  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180049f1b  jmp     short loc_180049F2B
0x180049f1d  lea     rcx, qword_1801B97E0; this
0x180049f24  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180049f2b  cmp     [rcx+8], r15b
0x180049f2f  jz      short loc_180049F56
0x180049f31  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180049f36  cmp     [rax+7CCh], ebx
0x180049f3c  jz      short loc_180049F56
0x180049f3e  mov     r9d, ebx; int
0x180049f41  lea     rdx, aCid3headerRead; "CID3Header::ReadFrames"
0x180049f48  mov     r8d, 40Bh; int
0x180049f4e  mov     rcx, rax; this
0x180049f51  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180049f56  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180049f5d  jb      short loc_180049F82
0x180049f5f  mov     edx, 5Bh ; '['
0x180049f64  mov     dword ptr [rsp+98h+var_78], ebx
0x180049f68  mov     rcx, cs:WPP_GLOBAL_Control
0x180049f6f  lea     r8, WPP_37a327c391a7379b3721a372142db134_Traceguids
0x180049f76  mov     r9, rdi
0x180049f79  mov     rcx, [rcx+10h]
0x180049f7d  call    WPP_SF_qD
0x180049f82  lea     rcx, [rsp+98h+var_50]; void *
0x180049f87  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x180049f8c  jmp     short loc_180049FB6
0x180049f8e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x180049f95  jb      short loc_180049FB6
0x180049f97  mov     rcx, cs:WPP_GLOBAL_Control
0x180049f9e  lea     r8, WPP_37a327c391a7379b3721a372142db134_Traceguids
0x180049fa5  mov     r9d, [rbx]
0x180049fa8  mov     edx, 5Fh ; '_'
0x180049fad  mov     rcx, [rcx+10h]
0x180049fb1  call    WPP_SF_d
0x180049fb6  lea     rcx, [rsp+98h+var_58]; this
0x180049fbb  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180049fc0  mov     eax, esi
0x180049fc2  mov     rcx, [rsp+98h+var_40]
0x180049fc7  xor     rcx, rsp; StackCookie
0x180049fca  call    __security_check_cookie
0x180049fcf  mov     rbx, [rsp+98h+arg_10]
0x180049fd7  add     rsp, 60h
0x180049fdb  pop     r15
0x180049fdd  pop     r14
0x180049fdf  pop     r13
0x180049fe1  pop     r12
0x180049fe3  pop     rdi
0x180049fe4  pop     rsi
  ... truncated ...
```
