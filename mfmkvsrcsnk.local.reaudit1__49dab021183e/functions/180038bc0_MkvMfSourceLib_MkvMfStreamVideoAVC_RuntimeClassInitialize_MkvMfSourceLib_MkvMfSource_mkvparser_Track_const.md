# MkvMfSourceLib::MkvMfStreamVideoAVC::RuntimeClassInitialize(MkvMfSourceLib::MkvMfSource *,mkvparser::Track const *)

- ea: `0x180038bc0`
- end: `0x180038fa5`
- name: `?RuntimeClassInitialize@MkvMfStreamVideoAVC@MkvMfSourceLib@@UEAAJPEAVMkvMfSource@2@PEBVTrack@mkvparser@@@Z`
- size: `997`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfStreamVideoAVC *__hidden this, struct MkvMfSourceLib::MkvMfSource *, const struct mkvparser::Track *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180026430`
- `0x180038bc0`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038c13`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038cd2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038d87`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038e43`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038eed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038c13`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038cd2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038d87`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038e43`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038eed`
- `MFPlat!MFCreateAlignedMemoryBuffer` at `0x180038cb0`
- `MFPlat!MFCreateAlignedMemoryBuffer` at `0x180038cb0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MkvMfSourceLib::MkvMfStreamVideoAVC::RuntimeClassInitialize(
        IMFMediaBuffer **this,
        struct MkvMfSourceLib::MkvMfSource *a2,
        const struct mkvparser::Track *a3)
{
  __int64 v6; // rdx
  HRESULT v7; // ebx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  _QWORD *v14; // rdi
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _DWORD *v40; // [rsp+30h] [rbp-38h] BYREF
  char v41; // [rsp+88h] [rbp+20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v41,
    "MkvMfSourceLib::MkvMfStreamVideoAVC::RuntimeClassInitialize",
    366);
  v7 = MkvMfSourceLib::MkvMfStream::RuntimeClassInitialize((MkvMfSourceLib::MkvMfStream *)this, a2, a3);
  if ( v7 >= 0 )
  {
    v40 = 0;
    v14 = this + 63;
    v7 = MFCreateAlignedMemoryBuffer(4u, 0, this + 63);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD, _DWORD **, _QWORD, _QWORD))(*(_QWORD *)*v14 + 24LL))(*v14, &v40, 0, 0);
      if ( v7 >= 0 )
      {
        *v40 = (_DWORD)MkvMfSourceLib::MkvMfStreamVideoAVC::kNaluStartCode;
        v7 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v14 + 48LL))(*v14, 4);
        if ( v7 >= 0 )
        {
          v7 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 32LL))(*v14);
          if ( v7 >= 0 )
          {
            v7 = 0;
            goto LABEL_58;
          }
          v36 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34, v35);
            CallStackTracing::s_wpInstance = v37;
            if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
            {
              v36 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v36 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v36 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != v7 )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "MkvMfSourceLib::MkvMfStreamVideoAVC::RuntimeClassInitialize",
                375,
                v7);
          }
          if ( g_wppLevels )
          {
            v13 = 50;
            goto LABEL_56;
          }
        }
        else
        {
          v30 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, v29);
            CallStackTracing::s_wpInstance = v31;
            if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
            {
              v30 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v30 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v30 + 8) )
          {
            v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
            if ( *((_DWORD *)v32 + 499) != v7 )
              CallStackContext::TraceFailure(
                v32,
                "MkvMfSourceLib::MkvMfStreamVideoAVC::RuntimeClassInitialize",
                374,
                v7);
          }
          if ( g_wppLevels )
          {
            v13 = 49;
            goto LABEL_56;
          }
        }
      }
      else
      {
        v24 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
          CallStackTracing::s_wpInstance = v25;
          if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
          {
            v24 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v24 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v24 + 8) )
        {
          v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
          if ( *((_DWORD *)v26 + 499) != v7 )
            CallStackContext::TraceFailure(v26, "MkvMfSourceLib::MkvMfStreamVideoAVC::RuntimeClassInitialize", 371, v7);
        }
        if ( g_wppLevels )
        {
          v13 = 48;
          goto LABEL_56;
        }
      }
    }
    else
    {
      v18 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15, v16, v17);
        CallStackTracing::s_wpInstance = v19;
        if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
        {
          v18 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v18 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v18 + 8) )
      {
        v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
        if ( *((_DWORD *)v20 + 499) != v7 )
          CallStackContext::TraceFailure(v20, "MkvMfSourceLib::MkvMfStreamVideoAVC::RuntimeClassInitialize", 369, v7);
      }
      if ( g_wppLevels )
      {
        v13 = 47;
        goto LABEL_56;
      }
    }
  }
  else
  {
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v8, v9);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)v12 + 499) != v7 )
        CallStackContext::TraceFailure(v12, "MkvMfSourceLib::MkvMfStreamVideoAVC::RuntimeClassInitialize", 366, v7);
    }
    if ( g_wppLevels )
    {
      v13 = 46;
LABEL_56:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids, this, v7);
    }
  }
LABEL_58:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v41);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180038bc0  mov     rax, rsp
0x180038bc3  push    rbx
0x180038bc4  push    rsi
0x180038bc5  push    rdi
0x180038bc6  push    r14
0x180038bc8  sub     rsp, 48h
0x180038bcc  mov     rbx, r8
0x180038bcf  mov     rdi, rdx
0x180038bd2  mov     rsi, rcx
0x180038bd5  mov     r8d, 16Eh; int
0x180038bdb  lea     r14, aMkvmfsourcelib_73; "MkvMfSourceLib::MkvMfStreamVideoAVC::Ru"...
0x180038be2  mov     rdx, r14; char *
0x180038be5  lea     rcx, [rax+20h]; this
0x180038be9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180038bee  nop
0x180038bef  mov     r8, rbx; struct mkvparser::Track *
0x180038bf2  mov     rdx, rdi; struct MkvMfSourceLib::MkvMfSource *
0x180038bf5  mov     rcx, rsi; this
0x180038bf8  call    ?RuntimeClassInitialize@MkvMfStream@MkvMfSourceLib@@UEAAJPEAVMkvMfSource@2@PEBVTrack@mkvparser@@@Z; MkvMfSourceLib::MkvMfStream::RuntimeClassInitialize(MkvMfSourceLib::MkvMfSource *,mkvparser::Track const *)
0x180038bfd  mov     ebx, eax
0x180038bff  test    eax, eax
0x180038c01  jns     loc_180038C98
0x180038c07  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038c0e  test    rcx, rcx
0x180038c11  jnz     short loc_180038C5A
0x180038c13  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180038c1a  nop     dword ptr [rax+rax+00h]
0x180038c1f  mov     rcx, rax
0x180038c22  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180038c29  test    rax, rax
0x180038c2c  jz      short loc_180038C4C
0x180038c2e  mov     rax, [rax]
0x180038c31  mov     edx, 7F0h
0x180038c36  mov     rax, [rax+8]
0x180038c3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c3f  test    eax, eax
0x180038c41  jz      short loc_180038C4C
0x180038c43  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038c4a  jmp     short loc_180038C5A
0x180038c4c  lea     rcx, qword_1800DBF70; this
0x180038c53  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180038c5a  cmp     byte ptr [rcx+8], 0
0x180038c5e  jz      short loc_180038C81
0x180038c60  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180038c65  cmp     [rax+7CCh], ebx
0x180038c6b  jz      short loc_180038C81
0x180038c6d  mov     r9d, ebx; int
0x180038c70  mov     r8d, 16Eh; int
0x180038c76  mov     rdx, r14; char *
0x180038c79  mov     rcx, rax; this
0x180038c7c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180038c81  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038c88  jb      loc_180038F8B
0x180038c8e  mov     edx, 2Eh ; '.'
0x180038c93  jmp     loc_180038F69
0x180038c98  mov     [rsp+68h+var_38], 0
0x180038ca1  lea     rdi, [rsi+1F8h]
0x180038ca8  mov     r8, rdi; ppBuffer
0x180038cab  xor     edx, edx; cbAligment
0x180038cad  lea     ecx, [rdx+4]; cbMaxLength
0x180038cb0  call    cs:__imp_MFCreateAlignedMemoryBuffer
0x180038cb7  nop     dword ptr [rax+rax+00h]
0x180038cbc  mov     ebx, eax
0x180038cbe  test    eax, eax
0x180038cc0  jns     loc_180038D57
0x180038cc6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038ccd  test    rcx, rcx
0x180038cd0  jnz     short loc_180038D19
0x180038cd2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180038cd9  nop     dword ptr [rax+rax+00h]
0x180038cde  mov     rcx, rax
0x180038ce1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180038ce8  test    rax, rax
0x180038ceb  jz      short loc_180038D0B
0x180038ced  mov     rax, [rax]
0x180038cf0  mov     edx, 7F0h
0x180038cf5  mov     rax, [rax+8]
0x180038cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038cfe  test    eax, eax
0x180038d00  jz      short loc_180038D0B
0x180038d02  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038d09  jmp     short loc_180038D19
0x180038d0b  lea     rcx, qword_1800DBF70; this
0x180038d12  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180038d19  cmp     byte ptr [rcx+8], 0
0x180038d1d  jz      short loc_180038D40
0x180038d1f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180038d24  cmp     [rax+7CCh], ebx
0x180038d2a  jz      short loc_180038D40
0x180038d2c  mov     r9d, ebx; int
0x180038d2f  mov     r8d, 171h; int
0x180038d35  mov     rdx, r14; char *
0x180038d38  mov     rcx, rax; this
0x180038d3b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180038d40  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038d47  jb      loc_180038F8B
0x180038d4d  mov     edx, 2Fh ; '/'
0x180038d52  jmp     loc_180038F69
0x180038d57  mov     rcx, [rdi]
0x180038d5a  mov     rax, [rcx]
0x180038d5d  xor     r9d, r9d
0x180038d60  xor     r8d, r8d
0x180038d63  lea     rdx, [rsp+68h+var_38]
0x180038d68  mov     rax, [rax+18h]
0x180038d6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d71  mov     ebx, eax
0x180038d73  test    eax, eax
0x180038d75  jns     loc_180038E0C
0x180038d7b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038d82  test    rcx, rcx
0x180038d85  jnz     short loc_180038DCE
0x180038d87  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180038d8e  nop     dword ptr [rax+rax+00h]
0x180038d93  mov     rcx, rax
0x180038d96  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180038d9d  test    rax, rax
0x180038da0  jz      short loc_180038DC0
0x180038da2  mov     rax, [rax]
0x180038da5  mov     edx, 7F0h
0x180038daa  mov     rax, [rax+8]
0x180038dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038db3  test    eax, eax
0x180038db5  jz      short loc_180038DC0
0x180038db7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038dbe  jmp     short loc_180038DCE
0x180038dc0  lea     rcx, qword_1800DBF70; this
0x180038dc7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180038dce  cmp     byte ptr [rcx+8], 0
0x180038dd2  jz      short loc_180038DF5
0x180038dd4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180038dd9  cmp     [rax+7CCh], ebx
0x180038ddf  jz      short loc_180038DF5
0x180038de1  mov     r9d, ebx; int
0x180038de4  mov     r8d, 173h; int
0x180038dea  mov     rdx, r14; char *
0x180038ded  mov     rcx, rax; this
0x180038df0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180038df5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038dfc  jb      loc_180038F8B
0x180038e02  mov     edx, 30h ; '0'
0x180038e07  jmp     loc_180038F69
0x180038e0c  mov     eax, cs:?kNaluStartCode@MkvMfStreamVideoAVC@MkvMfSourceLib@@2QBEB; uchar const near * const MkvMfSourceLib::MkvMfStreamVideoAVC::kNaluStartCode
0x180038e12  mov     rcx, [rsp+68h+var_38]
0x180038e17  mov     [rcx], eax
0x180038e19  mov     rcx, [rdi]
0x180038e1c  mov     rax, [rcx]
0x180038e1f  mov     edx, 4
0x180038e24  mov     rax, [rax+30h]
0x180038e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e2d  mov     ebx, eax
0x180038e2f  test    eax, eax
0x180038e31  jns     loc_180038EC8
0x180038e37  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038e3e  test    rcx, rcx
0x180038e41  jnz     short loc_180038E8A
0x180038e43  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180038e4a  nop     dword ptr [rax+rax+00h]
0x180038e4f  mov     rcx, rax
0x180038e52  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180038e59  test    rax, rax
0x180038e5c  jz      short loc_180038E7C
0x180038e5e  mov     rax, [rax]
0x180038e61  mov     edx, 7F0h
0x180038e66  mov     rax, [rax+8]
0x180038e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e6f  test    eax, eax
0x180038e71  jz      short loc_180038E7C
0x180038e73  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038e7a  jmp     short loc_180038E8A
0x180038e7c  lea     rcx, qword_1800DBF70; this
0x180038e83  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180038e8a  cmp     byte ptr [rcx+8], 0
0x180038e8e  jz      short loc_180038EB1
0x180038e90  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180038e95  cmp     [rax+7CCh], ebx
0x180038e9b  jz      short loc_180038EB1
0x180038e9d  mov     r9d, ebx; int
0x180038ea0  mov     r8d, 176h; int
0x180038ea6  mov     rdx, r14; char *
0x180038ea9  mov     rcx, rax; this
0x180038eac  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180038eb1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038eb8  jb      loc_180038F8B
0x180038ebe  mov     edx, 31h ; '1'
0x180038ec3  jmp     loc_180038F69
0x180038ec8  mov     rcx, [rdi]
0x180038ecb  mov     rax, [rcx]
0x180038ece  mov     rax, [rax+20h]
0x180038ed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038ed7  mov     ebx, eax
0x180038ed9  test    eax, eax
0x180038edb  jns     loc_180038F89
0x180038ee1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038ee8  test    rcx, rcx
0x180038eeb  jnz     short loc_180038F34
0x180038eed  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180038ef4  nop     dword ptr [rax+rax+00h]
0x180038ef9  mov     rcx, rax
0x180038efc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180038f03  test    rax, rax
0x180038f06  jz      short loc_180038F26
0x180038f08  mov     rax, [rax]
0x180038f0b  mov     edx, 7F0h
0x180038f10  mov     rax, [rax+8]
0x180038f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f19  test    eax, eax
0x180038f1b  jz      short loc_180038F26
0x180038f1d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038f24  jmp     short loc_180038F34
0x180038f26  lea     rcx, qword_1800DBF70; this
0x180038f2d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180038f34  cmp     byte ptr [rcx+8], 0
0x180038f38  jz      short loc_180038F5B
0x180038f3a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180038f3f  cmp     [rax+7CCh], ebx
0x180038f45  jz      short loc_180038F5B
0x180038f47  mov     r9d, ebx; int
0x180038f4a  mov     r8d, 177h; int
0x180038f50  mov     rdx, r14; char *
0x180038f53  mov     rcx, rax; this
0x180038f56  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180038f5b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038f62  jb      short loc_180038F8B
0x180038f64  mov     edx, 32h ; '2'
0x180038f69  mov     [rsp+68h+var_48], ebx
0x180038f6d  mov     r9, rsi
0x180038f70  lea     r8, WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids
0x180038f77  mov     rcx, cs:WPP_GLOBAL_Control
0x180038f7e  mov     rcx, [rcx+10h]
0x180038f82  call    WPP_SF_qD
0x180038f87  jmp     short loc_180038F8B
0x180038f89  xor     ebx, ebx
0x180038f8b  lea     rcx, [rsp+68h+arg_18]; this
0x180038f93  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180038f98  mov     eax, ebx
0x180038f9a  add     rsp, 48h
0x180038f9e  pop     r14
0x180038fa0  pop     rdi
0x180038fa1  pop     rsi
0x180038fa2  pop     rbx
0x180038fa3  retn
```
