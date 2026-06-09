# MkvMfSourceLib::MkvMfStreamVideoAVC::RuntimeClassInitialize(MkvMfSourceLib::MkvMfSource *,mkvparser::Track const *)

- ea: `0x180037310`
- end: `0x1800376d0`
- name: `?RuntimeClassInitialize@MkvMfStreamVideoAVC@MkvMfSourceLib@@UEAAJPEAVMkvMfSource@2@PEBVTrack@mkvparser@@@Z`
- size: `960`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfStreamVideoAVC *__hidden this, struct MkvMfSourceLib::MkvMfSource *, const struct mkvparser::Track *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180025470`
- `0x180037310`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037363`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037416`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800374c5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003757b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003761f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037363`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037416`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800374c5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003757b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003761f`
- `MFPlat!MFCreateAlignedMemoryBuffer` at `0x1800373fa`
- `MFPlat!MFCreateAlignedMemoryBuffer` at `0x1800373fa`

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
              v36 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v30 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v24 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v18 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v10 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x180037310  mov     rax, rsp
0x180037313  push    rbx
0x180037314  push    rsi
0x180037315  push    rdi
0x180037316  push    r14
0x180037318  sub     rsp, 48h
0x18003731c  mov     rbx, r8
0x18003731f  mov     rdi, rdx
0x180037322  mov     rsi, rcx
0x180037325  mov     r8d, 16Eh; int
0x18003732b  lea     r14, aMkvmfsourcelib_73; "MkvMfSourceLib::MkvMfStreamVideoAVC::Ru"...
0x180037332  mov     rdx, r14; char *
0x180037335  lea     rcx, [rax+20h]; this
0x180037339  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003733e  nop
0x18003733f  mov     r8, rbx; struct mkvparser::Track *
0x180037342  mov     rdx, rdi; struct MkvMfSourceLib::MkvMfSource *
0x180037345  mov     rcx, rsi; this
0x180037348  call    ?RuntimeClassInitialize@MkvMfStream@MkvMfSourceLib@@UEAAJPEAVMkvMfSource@2@PEBVTrack@mkvparser@@@Z; MkvMfSourceLib::MkvMfStream::RuntimeClassInitialize(MkvMfSourceLib::MkvMfSource *,mkvparser::Track const *)
0x18003734d  mov     ebx, eax
0x18003734f  test    eax, eax
0x180037351  jns     loc_1800373E2
0x180037357  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003735e  test    rcx, rcx
0x180037361  jnz     short loc_1800373A4
0x180037363  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180037369  mov     rcx, rax
0x18003736c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180037373  test    rax, rax
0x180037376  jz      short loc_180037396
0x180037378  mov     rax, [rax]
0x18003737b  mov     edx, 7F0h
0x180037380  mov     rax, [rax+8]
0x180037384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037389  test    eax, eax
0x18003738b  jz      short loc_180037396
0x18003738d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037394  jmp     short loc_1800373A4
0x180037396  lea     rcx, qword_1800D6F70; this
0x18003739d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800373a4  cmp     byte ptr [rcx+8], 0
0x1800373a8  jz      short loc_1800373CB
0x1800373aa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800373af  cmp     [rax+7CCh], ebx
0x1800373b5  jz      short loc_1800373CB
0x1800373b7  mov     r9d, ebx; int
0x1800373ba  mov     r8d, 16Eh; int
0x1800373c0  mov     rdx, r14; char *
0x1800373c3  mov     rcx, rax; this
0x1800373c6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800373cb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800373d2  jb      loc_1800376B7
0x1800373d8  mov     edx, 2Eh ; '.'
0x1800373dd  jmp     loc_180037695
0x1800373e2  mov     [rsp+68h+var_38], 0
0x1800373eb  lea     rdi, [rsi+1F8h]
0x1800373f2  mov     r8, rdi; ppBuffer
0x1800373f5  xor     edx, edx; cbAligment
0x1800373f7  lea     ecx, [rdx+4]; cbMaxLength
0x1800373fa  call    cs:__imp_MFCreateAlignedMemoryBuffer
0x180037400  mov     ebx, eax
0x180037402  test    eax, eax
0x180037404  jns     loc_180037495
0x18003740a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037411  test    rcx, rcx
0x180037414  jnz     short loc_180037457
0x180037416  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003741c  mov     rcx, rax
0x18003741f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180037426  test    rax, rax
0x180037429  jz      short loc_180037449
0x18003742b  mov     rax, [rax]
0x18003742e  mov     edx, 7F0h
0x180037433  mov     rax, [rax+8]
0x180037437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003743c  test    eax, eax
0x18003743e  jz      short loc_180037449
0x180037440  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037447  jmp     short loc_180037457
0x180037449  lea     rcx, qword_1800D6F70; this
0x180037450  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180037457  cmp     byte ptr [rcx+8], 0
0x18003745b  jz      short loc_18003747E
0x18003745d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180037462  cmp     [rax+7CCh], ebx
0x180037468  jz      short loc_18003747E
0x18003746a  mov     r9d, ebx; int
0x18003746d  mov     r8d, 171h; int
0x180037473  mov     rdx, r14; char *
0x180037476  mov     rcx, rax; this
0x180037479  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003747e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180037485  jb      loc_1800376B7
0x18003748b  mov     edx, 2Fh ; '/'
0x180037490  jmp     loc_180037695
0x180037495  mov     rcx, [rdi]
0x180037498  mov     rax, [rcx]
0x18003749b  xor     r9d, r9d
0x18003749e  xor     r8d, r8d
0x1800374a1  lea     rdx, [rsp+68h+var_38]
0x1800374a6  mov     rax, [rax+18h]
0x1800374aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800374af  mov     ebx, eax
0x1800374b1  test    eax, eax
0x1800374b3  jns     loc_180037544
0x1800374b9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800374c0  test    rcx, rcx
0x1800374c3  jnz     short loc_180037506
0x1800374c5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800374cb  mov     rcx, rax
0x1800374ce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800374d5  test    rax, rax
0x1800374d8  jz      short loc_1800374F8
0x1800374da  mov     rax, [rax]
0x1800374dd  mov     edx, 7F0h
0x1800374e2  mov     rax, [rax+8]
0x1800374e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800374eb  test    eax, eax
0x1800374ed  jz      short loc_1800374F8
0x1800374ef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800374f6  jmp     short loc_180037506
0x1800374f8  lea     rcx, qword_1800D6F70; this
0x1800374ff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180037506  cmp     byte ptr [rcx+8], 0
0x18003750a  jz      short loc_18003752D
0x18003750c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180037511  cmp     [rax+7CCh], ebx
0x180037517  jz      short loc_18003752D
0x180037519  mov     r9d, ebx; int
0x18003751c  mov     r8d, 173h; int
0x180037522  mov     rdx, r14; char *
0x180037525  mov     rcx, rax; this
0x180037528  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003752d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180037534  jb      loc_1800376B7
0x18003753a  mov     edx, 30h ; '0'
0x18003753f  jmp     loc_180037695
0x180037544  mov     eax, cs:?kNaluStartCode@MkvMfStreamVideoAVC@MkvMfSourceLib@@2QBEB; uchar const near * const MkvMfSourceLib::MkvMfStreamVideoAVC::kNaluStartCode
0x18003754a  mov     rcx, [rsp+68h+var_38]
0x18003754f  mov     [rcx], eax
0x180037551  mov     rcx, [rdi]
0x180037554  mov     rax, [rcx]
0x180037557  mov     edx, 4
0x18003755c  mov     rax, [rax+30h]
0x180037560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037565  mov     ebx, eax
0x180037567  test    eax, eax
0x180037569  jns     loc_1800375FA
0x18003756f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037576  test    rcx, rcx
0x180037579  jnz     short loc_1800375BC
0x18003757b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180037581  mov     rcx, rax
0x180037584  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003758b  test    rax, rax
0x18003758e  jz      short loc_1800375AE
0x180037590  mov     rax, [rax]
0x180037593  mov     edx, 7F0h
0x180037598  mov     rax, [rax+8]
0x18003759c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800375a1  test    eax, eax
0x1800375a3  jz      short loc_1800375AE
0x1800375a5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800375ac  jmp     short loc_1800375BC
0x1800375ae  lea     rcx, qword_1800D6F70; this
0x1800375b5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800375bc  cmp     byte ptr [rcx+8], 0
0x1800375c0  jz      short loc_1800375E3
0x1800375c2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800375c7  cmp     [rax+7CCh], ebx
0x1800375cd  jz      short loc_1800375E3
0x1800375cf  mov     r9d, ebx; int
0x1800375d2  mov     r8d, 176h; int
0x1800375d8  mov     rdx, r14; char *
0x1800375db  mov     rcx, rax; this
0x1800375de  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800375e3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800375ea  jb      loc_1800376B7
0x1800375f0  mov     edx, 31h ; '1'
0x1800375f5  jmp     loc_180037695
0x1800375fa  mov     rcx, [rdi]
0x1800375fd  mov     rax, [rcx]
0x180037600  mov     rax, [rax+20h]
0x180037604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037609  mov     ebx, eax
0x18003760b  test    eax, eax
0x18003760d  jns     loc_1800376B5
0x180037613  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003761a  test    rcx, rcx
0x18003761d  jnz     short loc_180037660
0x18003761f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180037625  mov     rcx, rax
0x180037628  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003762f  test    rax, rax
0x180037632  jz      short loc_180037652
0x180037634  mov     rax, [rax]
0x180037637  mov     edx, 7F0h
0x18003763c  mov     rax, [rax+8]
0x180037640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037645  test    eax, eax
0x180037647  jz      short loc_180037652
0x180037649  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037650  jmp     short loc_180037660
0x180037652  lea     rcx, qword_1800D6F70; this
0x180037659  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180037660  cmp     byte ptr [rcx+8], 0
0x180037664  jz      short loc_180037687
0x180037666  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003766b  cmp     [rax+7CCh], ebx
0x180037671  jz      short loc_180037687
0x180037673  mov     r9d, ebx; int
0x180037676  mov     r8d, 177h; int
0x18003767c  mov     rdx, r14; char *
0x18003767f  mov     rcx, rax; this
0x180037682  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180037687  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003768e  jb      short loc_1800376B7
0x180037690  mov     edx, 32h ; '2'
0x180037695  mov     [rsp+68h+var_48], ebx
0x180037699  mov     r9, rsi
0x18003769c  lea     r8, WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids
0x1800376a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800376aa  mov     rcx, [rcx+10h]
0x1800376ae  call    WPP_SF_qD
0x1800376b3  jmp     short loc_1800376B7
0x1800376b5  xor     ebx, ebx
0x1800376b7  lea     rcx, [rsp+68h+arg_18]; this
0x1800376bf  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800376c4  mov     eax, ebx
0x1800376c6  add     rsp, 48h
0x1800376ca  pop     r14
0x1800376cc  pop     rdi
0x1800376cd  pop     rsi
0x1800376ce  pop     rbx
0x1800376cf  retn
```
