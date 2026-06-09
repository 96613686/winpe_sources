# MkvMfSourceLib::MkvTimedText::CreateChapterTracks(void)

- ea: `0x18003d8bc`
- end: `0x18003dea0`
- name: `?CreateChapterTracks@MkvTimedText@MkvMfSourceLib@@AEAAJXZ`
- size: `1508`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvTimedText *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003ede0`

## callees

- `0x180001ff0`
- `0x180002400`
- `0x180005c68`
- `0x180008da0`
- `0x180009b04`
- `0x180009bec`
- `0x18000acc0`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x18003c15c`
- `0x18003ce90`
- `0x18003d8bc`
- `0x18003defc`
- `0x180047fec`
- `0x1800744d8`
- `0x18008867c`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d9fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003db8b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003dd3d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d9fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003db8b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003dd3d`

## string_xrefs

- `0x18003d8f7`: `MkvMfSourceLib::MkvTimedText::CreateChapterTracks`
- `0x18003da68`: `MkvMfSourceLib::MkvTimedText::CreateChapterTracks`
- `0x18003dbf6`: `MkvMfSourceLib::MkvTimedText::CreateChapterTracks`
- `0x18003dda8`: `MkvMfSourceLib::MkvTimedText::CreateChapterTracks`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall MkvMfSourceLib::MkvTimedText::CreateChapterTracks(struct IMFTimedTextTrack **this)
{
  const char *v2; // rdx
  __int64 v3; // rax
  __int64 v4; // r13
  unsigned int v5; // eax
  int v6; // r14d
  __int64 v7; // rsi
  unsigned int v8; // eax
  int i; // r12d
  LPCCH *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned int v17; // ebx
  struct IMFTimedTextTrack *v18; // rdi
  __int64 (__fastcall *v19)(struct IMFTimedTextTrack *, _QWORD, _QWORD *, _QWORD, int, _QWORD, int, GUID *, int, struct mkvparser::Chapters::Display **); // rbx
  _QWORD *v20; // r8
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  struct mkvparser::Chapters::Display *v27; // rbx
  const char *v28; // r9
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  _BYTE v36[4]; // [rsp+60h] [rbp-C8h] BYREF
  int v37; // [rsp+64h] [rbp-C4h] BYREF
  struct mkvparser::Chapters::Display *v38; // [rsp+68h] [rbp-C0h] BYREF
  void *Block; // [rsp+70h] [rbp-B8h] BYREF
  unsigned int v40; // [rsp+78h] [rbp-B0h]
  unsigned int v41; // [rsp+7Ch] [rbp-ACh]
  struct mkvparser::Chapters::Display *v42; // [rsp+80h] [rbp-A8h] BYREF
  struct mkvparser::Chapters::Atom *v43; // [rsp+88h] [rbp-A0h]
  int v44; // [rsp+90h] [rbp-98h] BYREF
  _QWORD v45[2]; // [rsp+98h] [rbp-90h] BYREF
  char v46; // [rsp+A8h] [rbp-80h]
  MkvMfSourceLib::MkvTimedText *v47; // [rsp+B0h] [rbp-78h]
  int *v48; // [rsp+B8h] [rbp-70h]
  char v49[16]; // [rsp+C0h] [rbp-68h] BYREF
  _QWORD v50[4]; // [rsp+D0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v37 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v36,
    "MkvMfSourceLib::MkvTimedText::CreateChapterTracks",
    606);
  v47 = (MkvMfSourceLib::MkvTimedText *)this;
  v48 = &v37;
  v3 = *(_QWORD *)(*((_QWORD *)this[24] + 52) + 144LL);
  if ( v3 && *(_DWORD *)(v3 + 52) )
  {
    v4 = *(_QWORD *)(v3 + 40);
    v5 = *(_DWORD *)(v4 + 12);
    v41 = v5;
    v6 = 0;
LABEL_4:
    if ( v6 >= v5 )
    {
      v17 = v37;
    }
    else
    {
      if ( v6 < 0 || (unsigned int)v6 >= *(_DWORD *)(v4 + 12) )
        v7 = 0;
      else
        v7 = *(_QWORD *)v4 + 48LL * v6;
      v8 = *(_DWORD *)(v7 + 44);
      v40 = v8;
      for ( i = 0; ; ++i )
      {
        if ( i >= v8 )
        {
          ++v6;
          v5 = v41;
          goto LABEL_4;
        }
        Block = 0;
        v45[1] = &Block;
        v46 = 1;
        if ( i < 0 || (unsigned int)i >= *(_DWORD *)(v7 + 44) )
          v10 = 0;
        else
          v10 = (LPCCH *)(*(_QWORD *)(v7 + 32) + 24LL * i);
        v43 = (struct mkvparser::Chapters::Atom *)v10;
        Block = mkvparser::ConvertFromUTF8(v10[1], v2);
        if ( !Block )
        {
          v37 = -2147024882;
          v14 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11, v12, v13);
            CallStackTracing::s_wpInstance = v15;
            if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
            {
              v14 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v14 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v14 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
            if ( v37 < 0 && *((_DWORD *)ThreadRelativeContext + 499) != v37 )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "MkvMfSourceLib::MkvTimedText::CreateChapterTracks",
                636,
                v37);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              95,
              &WPP_b10f0ccfbc7f3992efd0aeaf903260ed_Traceguids,
              this,
              v37);
          v17 = v37;
LABEL_44:
          operator delete(Block);
          goto LABEL_59;
        }
        std::wstring::wstring(v50, Block);
        MkvMfSourceLib::ConvertMKVLanguageStringToRFC1766(v50);
        v38 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        if ( (int)MkvMfSourceLib::MkvTimedText::FindChapterTrackForLanguage((__int64)this, v50, &v38) < 0 )
        {
          v18 = this[13];
          v19 = *(__int64 (__fastcall **)(struct IMFTimedTextTrack *, _QWORD, _QWORD *, _QWORD, int, _QWORD, int, GUID *, int, struct mkvparser::Chapters::Display **))(*(_QWORD *)v18 + 32LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
          v20 = v50;
          if ( v50[3] > 7u )
            v20 = (_QWORD *)v50[0];
          v37 = v19(
                  v18,
                  *((unsigned int *)this + 22),
                  v20,
                  0,
                  1,
                  0,
                  1,
                  &GUID_00000000_0000_0000_0000_000000000000,
                  2,
                  &v38);
          if ( v37 < 0 )
          {
            v24 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
              CallStackTracing::s_wpInstance = v25;
              if ( v25
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
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
              if ( v37 < 0 && *((_DWORD *)v26 + 499) != v37 )
                CallStackContext::TraceFailure(v26, "MkvMfSourceLib::MkvTimedText::CreateChapterTracks", 653, v37);
            }
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                96,
                &WPP_b10f0ccfbc7f3992efd0aeaf903260ed_Traceguids,
                this,
                v37);
            v17 = v37;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
            std::wstring::_Tidy_deallocate(v50);
            goto LABEL_44;
          }
          v27 = v38;
          v42 = v38;
          Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(&v42);
          try
          {
            v44 = (*(__int64 (__fastcall **)(struct mkvparser::Chapters::Display *))(*(_QWORD *)v38 + 24LL))(v38);
            v45[0] = v27;
            v42 = 0;
            std::_Tree<std::_Tmap_traits<unsigned long,MkvMfSourceLib::MkvTimedText::ChapterTrackData,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,MkvMfSourceLib::MkvTimedText::ChapterTrackData>>,0>>::_Emplace<std::pair<unsigned long,MkvMfSourceLib::MkvTimedText::ChapterTrackData>>(
              this + 22,
              v49,
              &v44);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v45);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
          }
          catch ( ... )
          {
            v40 = wil::details::in1diag3::Return_CaughtException(
                    retaddr,
                    (void *)0x294,
                    (unsigned int)"avcore\\mf\\core\\mediasource\\mkv\\lib\\mkvttcomponent.cpp",
                    v28);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
            std::wstring::_Tidy_deallocate(v50);
            operator delete(Block);
            v17 = v40;
            goto LABEL_59;
          }
        }
        v37 = MkvMfSourceLib::CreateAndAddChapterCue((MkvMfSourceLib *)v7, (LPCCH *)v43, v38, this[14]);
        if ( v37 < 0 )
          break;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        std::wstring::_Tidy_deallocate(v50);
        v46 = 0;
        operator delete(Block);
        v8 = v40;
      }
      v32 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30, v31);
        CallStackTracing::s_wpInstance = v33;
        if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
        {
          v32 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v32 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v32 + 8) )
      {
        v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
        if ( v37 < 0 && *((_DWORD *)v34 + 499) != v37 )
          CallStackContext::TraceFailure(v34, "MkvMfSourceLib::MkvTimedText::CreateChapterTracks", 664, v37);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_b10f0ccfbc7f3992efd0aeaf903260ed_Traceguids, this, v37);
      v17 = v37;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
      std::wstring::_Tidy_deallocate(v50);
      operator delete(Block);
    }
LABEL_59:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v36);
    return v17;
  }
  else
  {
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v36);
    return 0;
  }
}

```

## disassembly

```asm
0x18003d8bc  mov     [rsp+arg_8], rbx
0x18003d8c1  mov     [rsp+arg_10], rsi
0x18003d8c6  push    rdi
0x18003d8c7  push    r12
0x18003d8c9  push    r13
0x18003d8cb  push    r14
0x18003d8cd  push    r15
0x18003d8cf  sub     rsp, 100h
0x18003d8d6  mov     rax, cs:__security_cookie
0x18003d8dd  xor     rax, rsp
0x18003d8e0  mov     [rsp+128h+var_38], rax
0x18003d8e8  mov     r15, rcx
0x18003d8eb  xor     edi, edi
0x18003d8ed  mov     [rsp+128h+var_C4], edi
0x18003d8f1  mov     r8d, 25Eh; int
0x18003d8f7  lea     rdx, aMkvmfsourcelib_134; "MkvMfSourceLib::MkvTimedText::CreateCha"...
0x18003d8fe  lea     rcx, [rsp+128h+var_C8]; this
0x18003d903  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003d908  nop
0x18003d909  mov     [rsp+128h+var_78], r15
0x18003d911  lea     rax, [rsp+128h+var_C4]
0x18003d916  mov     [rsp+128h+var_70], rax
0x18003d91e  mov     rax, [r15+0C0h]
0x18003d925  mov     rcx, [rax+1A0h]
0x18003d92c  mov     rax, [rcx+90h]
0x18003d933  test    rax, rax
0x18003d936  jz      loc_18003DE66
0x18003d93c  mov     ecx, [rax+34h]
0x18003d93f  test    ecx, ecx
0x18003d941  jz      loc_18003DE66
0x18003d947  mov     r13, [rax+28h]
0x18003d94b  mov     eax, [r13+0Ch]
0x18003d94f  mov     [rsp+128h+var_AC], eax
0x18003d953  mov     r14d, edi
0x18003d956  cmp     r14d, eax
0x18003d959  jnb     loc_18003DE60
0x18003d95f  test    r14d, r14d
0x18003d962  jns     short loc_18003D969
0x18003d964  mov     rsi, rdi
0x18003d967  jmp     short loc_18003D97E
0x18003d969  cmp     r14d, [r13+0Ch]
0x18003d96d  jnb     short loc_18003D964
0x18003d96f  movsxd  rax, r14d
0x18003d972  lea     rsi, [rax+rax*2]
0x18003d976  shl     rsi, 4
0x18003d97a  add     rsi, [r13+0]
0x18003d97e  mov     eax, [rsi+2Ch]
0x18003d981  mov     [rsp+128h+var_B0], eax
0x18003d985  mov     r12d, edi
0x18003d988  cmp     r12d, eax
0x18003d98b  jnb     loc_18003DE54
0x18003d991  mov     [rsp+128h+Block], rdi
0x18003d996  lea     rax, [rsp+128h+Block]
0x18003d99b  mov     [rsp+128h+var_88], rax
0x18003d9a3  mov     [rsp+128h+var_80], 1
0x18003d9ab  test    r12d, r12d
0x18003d9ae  jns     short loc_18003D9B5
0x18003d9b0  mov     rax, rdi
0x18003d9b3  jmp     short loc_18003D9CA
0x18003d9b5  cmp     r12d, [rsi+2Ch]
0x18003d9b9  jnb     short loc_18003D9B0
0x18003d9bb  movsxd  rax, r12d
0x18003d9be  lea     rcx, [rax+rax*2]
0x18003d9c2  mov     rax, [rsi+20h]
0x18003d9c6  lea     rax, [rax+rcx*8]
0x18003d9ca  mov     [rsp+128h+var_A0], rax
0x18003d9d2  mov     rcx, [rax+8]; lpMultiByteStr
0x18003d9d6  call    ?ConvertFromUTF8@mkvparser@@YAPEAGPEBD@Z; mkvparser::ConvertFromUTF8(char const *)
0x18003d9db  mov     [rsp+128h+Block], rax
0x18003d9e0  test    rax, rax
0x18003d9e3  jnz     loc_18003DAB0
0x18003d9e9  mov     [rsp+128h+var_C4], 8007000Eh
0x18003d9f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d9f8  test    rcx, rcx
0x18003d9fb  jnz     short loc_18003DA44
0x18003d9fd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003da04  nop     dword ptr [rax+rax+00h]
0x18003da09  mov     rcx, rax
0x18003da0c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003da13  test    rax, rax
0x18003da16  jz      short loc_18003DA36
0x18003da18  mov     rax, [rax]
0x18003da1b  mov     edx, 7F0h
0x18003da20  mov     rax, [rax+8]
0x18003da24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da29  test    eax, eax
0x18003da2b  jz      short loc_18003DA36
0x18003da2d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003da34  jmp     short loc_18003DA44
0x18003da36  lea     rcx, qword_1800DBF70; this
0x18003da3d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003da44  cmp     [rcx+8], dil
0x18003da48  jz      short loc_18003DA77
0x18003da4a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003da4f  mov     r9d, [rsp+128h+var_C4]; int
0x18003da54  test    r9d, r9d
0x18003da57  jns     short loc_18003DA77
0x18003da59  cmp     [rax+7CCh], r9d
0x18003da60  jz      short loc_18003DA77
0x18003da62  mov     r8d, 27Ch; int
0x18003da68  lea     rdx, aMkvmfsourcelib_134; "MkvMfSourceLib::MkvTimedText::CreateCha"...
0x18003da6f  mov     rcx, rax; this
0x18003da72  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003da77  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003da7e  jb      short loc_18003DAA7
0x18003da80  mov     edx, 5Fh ; '_'
0x18003da85  mov     eax, [rsp+128h+var_C4]
0x18003da89  mov     [rsp+128h+var_108], eax
0x18003da8d  mov     r9, r15
0x18003da90  lea     r8, WPP_b10f0ccfbc7f3992efd0aeaf903260ed_Traceguids
0x18003da97  mov     rcx, cs:WPP_GLOBAL_Control
0x18003da9e  mov     rcx, [rcx+10h]
0x18003daa2  call    WPP_SF_qD
0x18003daa7  mov     ebx, [rsp+128h+var_C4]
0x18003daab  jmp     loc_18003DC52
0x18003dab0  mov     rdx, [rsp+128h+Block]
0x18003dab5  lea     rcx, [rsp+128h+var_58]
0x18003dabd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003dac2  nop
0x18003dac3  lea     rcx, [rsp+128h+var_58]
0x18003dacb  call    ?ConvertMKVLanguageStringToRFC1766@MkvMfSourceLib@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MkvMfSourceLib::ConvertMKVLanguageStringToRFC1766(std::wstring &)
0x18003dad0  mov     [rsp+128h+var_C0], rdi
0x18003dad5  lea     rcx, [rsp+128h+var_C0]
0x18003dada  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003dadf  lea     r8, [rsp+128h+var_C0]
0x18003dae4  lea     rdx, [rsp+128h+var_58]
0x18003daec  mov     rcx, r15
0x18003daef  call    ?FindChapterTrackForLanguage@MkvTimedText@MkvMfSourceLib@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAUIMFTimedTextTrack@@@Z; MkvMfSourceLib::MkvTimedText::FindChapterTrackForLanguage(std::wstring &,IMFTimedTextTrack * *)
0x18003daf4  test    eax, eax
0x18003daf6  jns     loc_18003DD0C
0x18003dafc  mov     rdi, [r15+68h]
0x18003db00  mov     rax, [rdi]
0x18003db03  mov     rbx, [rax+20h]
0x18003db07  lea     rcx, [rsp+128h+var_C0]
0x18003db0c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003db11  lea     r8, [rsp+128h+var_58]
0x18003db19  cmp     [rsp+128h+var_40], 7
0x18003db22  cmova   r8, [rsp+128h+var_58]
0x18003db2b  lea     rax, [rsp+128h+var_C0]
0x18003db30  mov     [rsp+128h+var_E0], rax
0x18003db35  mov     [rsp+128h+var_E8], 2
0x18003db3d  lea     rax, _GUID_00000000_0000_0000_0000_000000000000
0x18003db44  mov     [rsp+128h+var_F0], rax
0x18003db49  mov     eax, 1
0x18003db4e  mov     [rsp+128h+var_F8], eax
0x18003db52  mov     [rsp+128h+var_100], 0
0x18003db5b  mov     [rsp+128h+var_108], eax
0x18003db5f  xor     r9d, r9d
0x18003db62  mov     edx, [r15+58h]
0x18003db66  mov     rcx, rdi
0x18003db69  mov     rax, rbx
0x18003db6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db71  mov     [rsp+128h+var_C4], eax
0x18003db75  xor     edi, edi
0x18003db77  test    eax, eax
0x18003db79  jns     loc_18003DC62
0x18003db7f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003db86  test    rcx, rcx
0x18003db89  jnz     short loc_18003DBD2
0x18003db8b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003db92  nop     dword ptr [rax+rax+00h]
0x18003db97  mov     rcx, rax
0x18003db9a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003dba1  test    rax, rax
0x18003dba4  jz      short loc_18003DBC4
0x18003dba6  mov     rax, [rax]
0x18003dba9  mov     edx, 7F0h
0x18003dbae  mov     rax, [rax+8]
0x18003dbb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dbb7  test    eax, eax
0x18003dbb9  jz      short loc_18003DBC4
0x18003dbbb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003dbc2  jmp     short loc_18003DBD2
0x18003dbc4  lea     rcx, qword_1800DBF70; this
0x18003dbcb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003dbd2  cmp     [rcx+8], dil
0x18003dbd6  jz      short loc_18003DC05
0x18003dbd8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003dbdd  mov     r9d, [rsp+128h+var_C4]; int
0x18003dbe2  test    r9d, r9d
0x18003dbe5  jns     short loc_18003DC05
0x18003dbe7  cmp     [rax+7CCh], r9d
0x18003dbee  jz      short loc_18003DC05
0x18003dbf0  mov     r8d, 28Dh; int
0x18003dbf6  lea     rdx, aMkvmfsourcelib_134; "MkvMfSourceLib::MkvTimedText::CreateCha"...
0x18003dbfd  mov     rcx, rax; this
0x18003dc00  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003dc05  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003dc0c  jb      short loc_18003DC35
0x18003dc0e  mov     edx, 60h ; '`'
0x18003dc13  mov     eax, [rsp+128h+var_C4]
0x18003dc17  mov     [rsp+128h+var_108], eax
0x18003dc1b  mov     r9, r15
0x18003dc1e  lea     r8, WPP_b10f0ccfbc7f3992efd0aeaf903260ed_Traceguids
0x18003dc25  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dc2c  mov     rcx, [rcx+10h]
0x18003dc30  call    WPP_SF_qD
0x18003dc35  mov     ebx, [rsp+128h+var_C4]
0x18003dc39  lea     rcx, [rsp+128h+var_C0]
0x18003dc3e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003dc43  nop
0x18003dc44  lea     rcx, [rsp+128h+var_58]
0x18003dc4c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003dc51  nop
0x18003dc52  mov     rcx, [rsp+128h+Block]; Block
0x18003dc57  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003dc5c  nop
0x18003dc5d  jmp     loc_18003DE0F
0x18003dc62  mov     rbx, [rsp+128h+var_C0]
0x18003dc67  mov     [rsp+128h+var_A8], rbx
0x18003dc6f  lea     rcx, [rsp+128h+var_A8]
0x18003dc77  call    ?InternalAddRef@?$ComPtr@VMkvMfStreamSubtitle@MkvMfSourceLib@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(void)
0x18003dc7c  nop
0x18003dc7d  mov     rcx, [rsp+128h+var_C0]
0x18003dc82  mov     rax, [rcx]
0x18003dc85  mov     rax, [rax+18h]
0x18003dc89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc8e  mov     [rsp+128h+var_98], eax
0x18003dc95  mov     [rsp+128h+var_90], rbx
0x18003dc9d  mov     [rsp+128h+var_A8], rdi
0x18003dca5  lea     rcx, [r15+0B0h]
0x18003dcac  lea     r8, [rsp+128h+var_98]
0x18003dcb4  lea     rdx, [rsp+128h+var_68]
0x18003dcbc  call    ??$_Emplace@U?$pair@KVChapterTrackData@MkvTimedText@MkvMfSourceLib@@@std@@@?$_Tree@V?$_Tmap_traits@KVChapterTrackData@MkvTimedText@MkvMfSourceLib@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKVChapterTrackData@MkvTimedText@MkvMfSourceLib@@@std@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKVChapterTrackData@MkvTimedText@MkvMfSourceLib@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@KVChapterTrackData@MkvTimedText@MkvMfSourceLib@@@1@@Z; std::_Tree<std::_Tmap_traits<ulong,MkvMfSourceLib::MkvTimedText::ChapterTrackData,std::less<ulong>,std::allocator<std::pair<ulong const,MkvMfSourceLib::MkvTimedText::ChapterTrackData>>,0>>::_Emplace<std::pair<ulong,MkvMfSourceLib::MkvTimedText::ChapterTrackData>>(std::pair<ulong,MkvMfSourceLib::MkvTimedText::ChapterTrackData> &&)
0x18003dcc1  nop
0x18003dcc2  lea     rcx, [rsp+128h+var_90]
0x18003dcca  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003dccf  nop
0x18003dcd0  lea     rcx, [rsp+128h+var_A8]
0x18003dcd8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003dcdd  jmp     short loc_18003DD0C
0x18003dcdf  lea     rcx, [rsp+128h+var_C0]
0x18003dce4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003dce9  nop
0x18003dcea  lea     rcx, [rsp+128h+var_58]
0x18003dcf2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003dcf7  nop
0x18003dcf8  mov     rcx, [rsp+128h+Block]; Block
0x18003dcfd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003dd02  nop
0x18003dd03  mov     ebx, [rsp+128h+var_B0]
0x18003dd07  jmp     loc_18003DE0F
0x18003dd0c  mov     r9, [r15+70h]; struct IMFTimedTextTrack *
0x18003dd10  mov     r8, [rsp+128h+var_C0]; struct mkvparser::Chapters::Display *
0x18003dd15  mov     rdx, [rsp+128h+var_A0]; struct mkvparser::Chapters::Atom *
0x18003dd1d  mov     rcx, rsi; this
0x18003dd20  call    ?CreateAndAddChapterCue@MkvMfSourceLib@@YAJPEBVAtom@Chapters@mkvparser@@PEBVDisplay@34@PEAUIMFTimedTextTrack@@PEAUIMFTimedTextCueBuilder@@@Z; MkvMfSourceLib::CreateAndAddChapterCue(mkvparser::Chapters::Atom const *,mkvparser::Chapters::Display const *,IMFTimedTextTrack *,IMFTimedTextCueBuilder *)
0x18003dd25  mov     [rsp+128h+var_C4], eax
0x18003dd29  test    eax, eax
0x18003dd2b  jns     loc_18003DE1D
0x18003dd31  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003dd38  test    rcx, rcx
0x18003dd3b  jnz     short loc_18003DD84
0x18003dd3d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003dd44  nop     dword ptr [rax+rax+00h]
0x18003dd49  mov     rcx, rax
0x18003dd4c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003dd53  test    rax, rax
0x18003dd56  jz      short loc_18003DD76
0x18003dd58  mov     rax, [rax]
0x18003dd5b  mov     edx, 7F0h
0x18003dd60  mov     rax, [rax+8]
0x18003dd64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd69  test    eax, eax
0x18003dd6b  jz      short loc_18003DD76
0x18003dd6d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003dd74  jmp     short loc_18003DD84
0x18003dd76  lea     rcx, qword_1800DBF70; this
0x18003dd7d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003dd84  cmp     [rcx+8], dil
0x18003dd88  jz      short loc_18003DDB7
0x18003dd8a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003dd8f  mov     r9d, [rsp+128h+var_C4]; int
0x18003dd94  test    r9d, r9d
0x18003dd97  jns     short loc_18003DDB7
0x18003dd99  cmp     [rax+7CCh], r9d
0x18003dda0  jz      short loc_18003DDB7
0x18003dda2  mov     r8d, 298h; int
0x18003dda8  lea     rdx, aMkvmfsourcelib_134; "MkvMfSourceLib::MkvTimedText::CreateCha"...
0x18003ddaf  mov     rcx, rax; this
0x18003ddb2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003ddb7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ddbe  jb      short loc_18003DDE7
0x18003ddc0  mov     edx, 61h ; 'a'
0x18003ddc5  mov     eax, [rsp+128h+var_C4]
0x18003ddc9  mov     [rsp+128h+var_108], eax
0x18003ddcd  mov     r9, r15
0x18003ddd0  lea     r8, WPP_b10f0ccfbc7f3992efd0aeaf903260ed_Traceguids
0x18003ddd7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ddde  mov     rcx, [rcx+10h]
0x18003dde2  call    WPP_SF_qD
0x18003dde7  mov     ebx, [rsp+128h+var_C4]
0x18003ddeb  lea     rcx, [rsp+128h+var_C0]
0x18003ddf0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ddf5  nop
0x18003ddf6  lea     rcx, [rsp+128h+var_58]
0x18003ddfe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003de03  nop
0x18003de04  mov     rcx, [rsp+128h+Block]; Block
0x18003de09  call    ??3@YAXPEAX@Z; operator delete(void *)
  ... truncated ...
```
