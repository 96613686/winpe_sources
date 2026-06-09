# MkvMfSourceLib::MkvTimedText::CreateChapterTracks(void)

- ea: `0x18003bea0`
- end: `0x18003c471`
- name: `?CreateChapterTracks@MkvTimedText@MkvMfSourceLib@@AEAAJXZ`
- size: `1489`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvTimedText *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003d330`

## callees

- `0x180001fd0`
- `0x1800023e0`
- `0x180005ab8`
- `0x180008a74`
- `0x1800097f0`
- `0x1800098b8`
- `0x18000a968`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x18003a724`
- `0x18003b4b8`
- `0x18003bea0`
- `0x18003c4c0`
- `0x18004613c`
- `0x180071330`
- `0x180084b34`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003bfe1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c169`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c315`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003bfe1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c169`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c315`

## string_xrefs

- `0x18003bedb`: `MkvMfSourceLib::MkvTimedText::CreateChapterTracks`
- `0x18003c046`: `MkvMfSourceLib::MkvTimedText::CreateChapterTracks`
- `0x18003c1ce`: `MkvMfSourceLib::MkvTimedText::CreateChapterTracks`
- `0x18003c37a`: `MkvMfSourceLib::MkvTimedText::CreateChapterTracks`

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
              v14 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                v24 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v32 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x18003bea0  mov     [rsp+arg_8], rbx
0x18003bea5  mov     [rsp+arg_10], rsi
0x18003beaa  push    rdi
0x18003beab  push    r12
0x18003bead  push    r13
0x18003beaf  push    r14
0x18003beb1  push    r15
0x18003beb3  sub     rsp, 100h
0x18003beba  mov     rax, cs:__security_cookie
0x18003bec1  xor     rax, rsp
0x18003bec4  mov     [rsp+128h+var_38], rax
0x18003becc  mov     r15, rcx
0x18003becf  xor     edi, edi
0x18003bed1  mov     [rsp+128h+var_C4], edi
0x18003bed5  mov     r8d, 25Eh; int
0x18003bedb  lea     rdx, aMkvmfsourcelib_134; "MkvMfSourceLib::MkvTimedText::CreateCha"...
0x18003bee2  lea     rcx, [rsp+128h+var_C8]; this
0x18003bee7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003beec  nop
0x18003beed  mov     [rsp+128h+var_78], r15
0x18003bef5  lea     rax, [rsp+128h+var_C4]
0x18003befa  mov     [rsp+128h+var_70], rax
0x18003bf02  mov     rax, [r15+0C0h]
0x18003bf09  mov     rcx, [rax+1A0h]
0x18003bf10  mov     rax, [rcx+90h]
0x18003bf17  test    rax, rax
0x18003bf1a  jz      loc_18003C438
0x18003bf20  mov     ecx, [rax+34h]
0x18003bf23  test    ecx, ecx
0x18003bf25  jz      loc_18003C438
0x18003bf2b  mov     r13, [rax+28h]
0x18003bf2f  mov     eax, [r13+0Ch]
0x18003bf33  mov     [rsp+128h+var_AC], eax
0x18003bf37  mov     r14d, edi
0x18003bf3a  cmp     r14d, eax
0x18003bf3d  jnb     loc_18003C432
0x18003bf43  test    r14d, r14d
0x18003bf46  jns     short loc_18003BF4D
0x18003bf48  mov     rsi, rdi
0x18003bf4b  jmp     short loc_18003BF62
0x18003bf4d  cmp     r14d, [r13+0Ch]
0x18003bf51  jnb     short loc_18003BF48
0x18003bf53  movsxd  rax, r14d
0x18003bf56  lea     rsi, [rax+rax*2]
0x18003bf5a  shl     rsi, 4
0x18003bf5e  add     rsi, [r13+0]
0x18003bf62  mov     eax, [rsi+2Ch]
0x18003bf65  mov     [rsp+128h+var_B0], eax
0x18003bf69  mov     r12d, edi
0x18003bf6c  cmp     r12d, eax
0x18003bf6f  jnb     loc_18003C426
0x18003bf75  mov     [rsp+128h+Block], rdi
0x18003bf7a  lea     rax, [rsp+128h+Block]
0x18003bf7f  mov     [rsp+128h+var_88], rax
0x18003bf87  mov     [rsp+128h+var_80], 1
0x18003bf8f  test    r12d, r12d
0x18003bf92  jns     short loc_18003BF99
0x18003bf94  mov     rax, rdi
0x18003bf97  jmp     short loc_18003BFAE
0x18003bf99  cmp     r12d, [rsi+2Ch]
0x18003bf9d  jnb     short loc_18003BF94
0x18003bf9f  movsxd  rax, r12d
0x18003bfa2  lea     rcx, [rax+rax*2]
0x18003bfa6  mov     rax, [rsi+20h]
0x18003bfaa  lea     rax, [rax+rcx*8]
0x18003bfae  mov     [rsp+128h+var_A0], rax
0x18003bfb6  mov     rcx, [rax+8]; lpMultiByteStr
0x18003bfba  call    ?ConvertFromUTF8@mkvparser@@YAPEAGPEBD@Z; mkvparser::ConvertFromUTF8(char const *)
0x18003bfbf  mov     [rsp+128h+Block], rax
0x18003bfc4  test    rax, rax
0x18003bfc7  jnz     loc_18003C08E
0x18003bfcd  mov     [rsp+128h+var_C4], 8007000Eh
0x18003bfd5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bfdc  test    rcx, rcx
0x18003bfdf  jnz     short loc_18003C022
0x18003bfe1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003bfe7  mov     rcx, rax
0x18003bfea  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bff1  test    rax, rax
0x18003bff4  jz      short loc_18003C014
0x18003bff6  mov     rax, [rax]
0x18003bff9  mov     edx, 7F0h
0x18003bffe  mov     rax, [rax+8]
0x18003c002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c007  test    eax, eax
0x18003c009  jz      short loc_18003C014
0x18003c00b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c012  jmp     short loc_18003C022
0x18003c014  lea     rcx, qword_1800D6F70; this
0x18003c01b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c022  cmp     [rcx+8], dil
0x18003c026  jz      short loc_18003C055
0x18003c028  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003c02d  mov     r9d, [rsp+128h+var_C4]; int
0x18003c032  test    r9d, r9d
0x18003c035  jns     short loc_18003C055
0x18003c037  cmp     [rax+7CCh], r9d
0x18003c03e  jz      short loc_18003C055
0x18003c040  mov     r8d, 27Ch; int
0x18003c046  lea     rdx, aMkvmfsourcelib_134; "MkvMfSourceLib::MkvTimedText::CreateCha"...
0x18003c04d  mov     rcx, rax; this
0x18003c050  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003c055  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003c05c  jb      short loc_18003C085
0x18003c05e  mov     edx, 5Fh ; '_'
0x18003c063  mov     eax, [rsp+128h+var_C4]
0x18003c067  mov     [rsp+128h+var_108], eax
0x18003c06b  mov     r9, r15
0x18003c06e  lea     r8, WPP_b10f0ccfbc7f3992efd0aeaf903260ed_Traceguids
0x18003c075  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c07c  mov     rcx, [rcx+10h]
0x18003c080  call    WPP_SF_qD
0x18003c085  mov     ebx, [rsp+128h+var_C4]
0x18003c089  jmp     loc_18003C22A
0x18003c08e  mov     rdx, [rsp+128h+Block]
0x18003c093  lea     rcx, [rsp+128h+var_58]
0x18003c09b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003c0a0  nop
0x18003c0a1  lea     rcx, [rsp+128h+var_58]
0x18003c0a9  call    ?ConvertMKVLanguageStringToRFC1766@MkvMfSourceLib@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MkvMfSourceLib::ConvertMKVLanguageStringToRFC1766(std::wstring &)
0x18003c0ae  mov     [rsp+128h+var_C0], rdi
0x18003c0b3  lea     rcx, [rsp+128h+var_C0]
0x18003c0b8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003c0bd  lea     r8, [rsp+128h+var_C0]
0x18003c0c2  lea     rdx, [rsp+128h+var_58]
0x18003c0ca  mov     rcx, r15
0x18003c0cd  call    ?FindChapterTrackForLanguage@MkvTimedText@MkvMfSourceLib@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAUIMFTimedTextTrack@@@Z; MkvMfSourceLib::MkvTimedText::FindChapterTrackForLanguage(std::wstring &,IMFTimedTextTrack * *)
0x18003c0d2  test    eax, eax
0x18003c0d4  jns     loc_18003C2E4
0x18003c0da  mov     rdi, [r15+68h]
0x18003c0de  mov     rax, [rdi]
0x18003c0e1  mov     rbx, [rax+20h]
0x18003c0e5  lea     rcx, [rsp+128h+var_C0]
0x18003c0ea  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003c0ef  lea     r8, [rsp+128h+var_58]
0x18003c0f7  cmp     [rsp+128h+var_40], 7
0x18003c100  cmova   r8, [rsp+128h+var_58]
0x18003c109  lea     rax, [rsp+128h+var_C0]
0x18003c10e  mov     [rsp+128h+var_E0], rax
0x18003c113  mov     [rsp+128h+var_E8], 2
0x18003c11b  lea     rax, _GUID_00000000_0000_0000_0000_000000000000
0x18003c122  mov     [rsp+128h+var_F0], rax
0x18003c127  mov     eax, 1
0x18003c12c  mov     [rsp+128h+var_F8], eax
0x18003c130  mov     [rsp+128h+var_100], 0
0x18003c139  mov     [rsp+128h+var_108], eax
0x18003c13d  xor     r9d, r9d
0x18003c140  mov     edx, [r15+58h]
0x18003c144  mov     rcx, rdi
0x18003c147  mov     rax, rbx
0x18003c14a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c14f  mov     [rsp+128h+var_C4], eax
0x18003c153  xor     edi, edi
0x18003c155  test    eax, eax
0x18003c157  jns     loc_18003C23A
0x18003c15d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c164  test    rcx, rcx
0x18003c167  jnz     short loc_18003C1AA
0x18003c169  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003c16f  mov     rcx, rax
0x18003c172  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c179  test    rax, rax
0x18003c17c  jz      short loc_18003C19C
0x18003c17e  mov     rax, [rax]
0x18003c181  mov     edx, 7F0h
0x18003c186  mov     rax, [rax+8]
0x18003c18a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c18f  test    eax, eax
0x18003c191  jz      short loc_18003C19C
0x18003c193  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c19a  jmp     short loc_18003C1AA
0x18003c19c  lea     rcx, qword_1800D6F70; this
0x18003c1a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c1aa  cmp     [rcx+8], dil
0x18003c1ae  jz      short loc_18003C1DD
0x18003c1b0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003c1b5  mov     r9d, [rsp+128h+var_C4]; int
0x18003c1ba  test    r9d, r9d
0x18003c1bd  jns     short loc_18003C1DD
0x18003c1bf  cmp     [rax+7CCh], r9d
0x18003c1c6  jz      short loc_18003C1DD
0x18003c1c8  mov     r8d, 28Dh; int
0x18003c1ce  lea     rdx, aMkvmfsourcelib_134; "MkvMfSourceLib::MkvTimedText::CreateCha"...
0x18003c1d5  mov     rcx, rax; this
0x18003c1d8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003c1dd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003c1e4  jb      short loc_18003C20D
0x18003c1e6  mov     edx, 60h ; '`'
0x18003c1eb  mov     eax, [rsp+128h+var_C4]
0x18003c1ef  mov     [rsp+128h+var_108], eax
0x18003c1f3  mov     r9, r15
0x18003c1f6  lea     r8, WPP_b10f0ccfbc7f3992efd0aeaf903260ed_Traceguids
0x18003c1fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c204  mov     rcx, [rcx+10h]
0x18003c208  call    WPP_SF_qD
0x18003c20d  mov     ebx, [rsp+128h+var_C4]
0x18003c211  lea     rcx, [rsp+128h+var_C0]
0x18003c216  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003c21b  nop
0x18003c21c  lea     rcx, [rsp+128h+var_58]
0x18003c224  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c229  nop
0x18003c22a  mov     rcx, [rsp+128h+Block]; Block
0x18003c22f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003c234  nop
0x18003c235  jmp     loc_18003C3E1
0x18003c23a  mov     rbx, [rsp+128h+var_C0]
0x18003c23f  mov     [rsp+128h+var_A8], rbx
0x18003c247  lea     rcx, [rsp+128h+var_A8]
0x18003c24f  call    ?InternalAddRef@?$ComPtr@VMkvMfStreamSubtitle@MkvMfSourceLib@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(void)
0x18003c254  nop
0x18003c255  mov     rcx, [rsp+128h+var_C0]
0x18003c25a  mov     rax, [rcx]
0x18003c25d  mov     rax, [rax+18h]
0x18003c261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c266  mov     [rsp+128h+var_98], eax
0x18003c26d  mov     [rsp+128h+var_90], rbx
0x18003c275  mov     [rsp+128h+var_A8], rdi
0x18003c27d  lea     rcx, [r15+0B0h]
0x18003c284  lea     r8, [rsp+128h+var_98]
0x18003c28c  lea     rdx, [rsp+128h+var_68]
0x18003c294  call    ??$_Emplace@U?$pair@KVChapterTrackData@MkvTimedText@MkvMfSourceLib@@@std@@@?$_Tree@V?$_Tmap_traits@KVChapterTrackData@MkvTimedText@MkvMfSourceLib@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKVChapterTrackData@MkvTimedText@MkvMfSourceLib@@@std@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKVChapterTrackData@MkvTimedText@MkvMfSourceLib@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@KVChapterTrackData@MkvTimedText@MkvMfSourceLib@@@1@@Z; std::_Tree<std::_Tmap_traits<ulong,MkvMfSourceLib::MkvTimedText::ChapterTrackData,std::less<ulong>,std::allocator<std::pair<ulong const,MkvMfSourceLib::MkvTimedText::ChapterTrackData>>,0>>::_Emplace<std::pair<ulong,MkvMfSourceLib::MkvTimedText::ChapterTrackData>>(std::pair<ulong,MkvMfSourceLib::MkvTimedText::ChapterTrackData> &&)
0x18003c299  nop
0x18003c29a  lea     rcx, [rsp+128h+var_90]
0x18003c2a2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003c2a7  nop
0x18003c2a8  lea     rcx, [rsp+128h+var_A8]
0x18003c2b0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003c2b5  jmp     short loc_18003C2E4
0x18003c2b7  lea     rcx, [rsp+128h+var_C0]
0x18003c2bc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003c2c1  nop
0x18003c2c2  lea     rcx, [rsp+128h+var_58]
0x18003c2ca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c2cf  nop
0x18003c2d0  mov     rcx, [rsp+128h+Block]; Block
0x18003c2d5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003c2da  nop
0x18003c2db  mov     ebx, [rsp+128h+var_B0]
0x18003c2df  jmp     loc_18003C3E1
0x18003c2e4  mov     r9, [r15+70h]; struct IMFTimedTextTrack *
0x18003c2e8  mov     r8, [rsp+128h+var_C0]; struct mkvparser::Chapters::Display *
0x18003c2ed  mov     rdx, [rsp+128h+var_A0]; struct mkvparser::Chapters::Atom *
0x18003c2f5  mov     rcx, rsi; this
0x18003c2f8  call    ?CreateAndAddChapterCue@MkvMfSourceLib@@YAJPEBVAtom@Chapters@mkvparser@@PEBVDisplay@34@PEAUIMFTimedTextTrack@@PEAUIMFTimedTextCueBuilder@@@Z; MkvMfSourceLib::CreateAndAddChapterCue(mkvparser::Chapters::Atom const *,mkvparser::Chapters::Display const *,IMFTimedTextTrack *,IMFTimedTextCueBuilder *)
0x18003c2fd  mov     [rsp+128h+var_C4], eax
0x18003c301  test    eax, eax
0x18003c303  jns     loc_18003C3EF
0x18003c309  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c310  test    rcx, rcx
0x18003c313  jnz     short loc_18003C356
0x18003c315  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003c31b  mov     rcx, rax
0x18003c31e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c325  test    rax, rax
0x18003c328  jz      short loc_18003C348
0x18003c32a  mov     rax, [rax]
0x18003c32d  mov     edx, 7F0h
0x18003c332  mov     rax, [rax+8]
0x18003c336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c33b  test    eax, eax
0x18003c33d  jz      short loc_18003C348
0x18003c33f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c346  jmp     short loc_18003C356
0x18003c348  lea     rcx, qword_1800D6F70; this
0x18003c34f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c356  cmp     [rcx+8], dil
0x18003c35a  jz      short loc_18003C389
0x18003c35c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003c361  mov     r9d, [rsp+128h+var_C4]; int
0x18003c366  test    r9d, r9d
0x18003c369  jns     short loc_18003C389
0x18003c36b  cmp     [rax+7CCh], r9d
0x18003c372  jz      short loc_18003C389
0x18003c374  mov     r8d, 298h; int
0x18003c37a  lea     rdx, aMkvmfsourcelib_134; "MkvMfSourceLib::MkvTimedText::CreateCha"...
0x18003c381  mov     rcx, rax; this
0x18003c384  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003c389  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003c390  jb      short loc_18003C3B9
0x18003c392  mov     edx, 61h ; 'a'
0x18003c397  mov     eax, [rsp+128h+var_C4]
0x18003c39b  mov     [rsp+128h+var_108], eax
0x18003c39f  mov     r9, r15
0x18003c3a2  lea     r8, WPP_b10f0ccfbc7f3992efd0aeaf903260ed_Traceguids
0x18003c3a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c3b0  mov     rcx, [rcx+10h]
0x18003c3b4  call    WPP_SF_qD
0x18003c3b9  mov     ebx, [rsp+128h+var_C4]
0x18003c3bd  lea     rcx, [rsp+128h+var_C0]
0x18003c3c2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003c3c7  nop
0x18003c3c8  lea     rcx, [rsp+128h+var_58]
0x18003c3d0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c3d5  nop
0x18003c3d6  mov     rcx, [rsp+128h+Block]; Block
0x18003c3db  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003c3e0  nop
0x18003c3e1  lea     rcx, [rsp+128h+var_C8]; this
0x18003c3e6  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
  ... truncated ...
```
