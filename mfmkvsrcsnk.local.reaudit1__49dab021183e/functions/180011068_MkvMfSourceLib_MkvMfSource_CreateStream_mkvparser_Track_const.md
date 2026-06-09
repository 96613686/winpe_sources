# MkvMfSourceLib::MkvMfSource::CreateStream(mkvparser::Track const *)

- ea: `0x180011068`
- end: `0x1800113da`
- name: `?CreateStream@MkvMfSource@MkvMfSourceLib@@AEAAJPEBVTrack@mkvparser@@@Z`
- size: `882`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource *__hidden this, const struct mkvparser::Track *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180020110`

## callees

- `0x180002400`
- `0x180005c68`
- `0x180009b04`
- `0x180009bec`
- `0x18000d2c4`
- `0x18000d554`
- `0x18000ddc0`
- `0x180011068`
- `0x180021b9c`
- `0x18002d6c4`
- `0x180030e28`
- `0x180032dbc`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001115b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001121f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001115b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001121f`

## string_xrefs

- `0x18001109b`: `MkvMfSourceLib::MkvMfSource::CreateStream`
- `0x1800111c6`: `MkvMfSourceLib::MkvMfSource::CreateStream`
- `0x18001128a`: `MkvMfSourceLib::MkvMfSource::CreateStream`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall MkvMfSourceLib::MkvMfSource::CreateStream(
        MkvMfSourceLib::MkvMfSource *this,
        const struct mkvparser::Track *a2)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  unsigned int v19; // ebx
  int v20; // edi
  struct IMFMediaStream *v21; // rbx
  const char *v22; // r9
  _BYTE v24[4]; // [rsp+30h] [rbp-68h] BYREF
  int v25; // [rsp+34h] [rbp-64h] BYREF
  struct IMFMediaStream *v26; // [rsp+38h] [rbp-60h] BYREF
  struct IMFMediaStream *v27; // [rsp+40h] [rbp-58h] BYREF
  int v28; // [rsp+48h] [rbp-50h] BYREF
  struct IMFMediaStream *v29; // [rsp+50h] [rbp-48h]
  _BYTE v30[16]; // [rsp+58h] [rbp-40h] BYREF
  _QWORD v31[2]; // [rsp+68h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v25 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v24, "MkvMfSourceLib::MkvMfSource::CreateStream", 153);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 86) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 86) + 296LL))(*((_QWORD *)this + 86));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 86) + 280LL))(
                                                            *((_QWORD *)this + 86),
                                                            v31);
    *((_DWORD *)ThreadRelativeContext + 504) = v5;
  }
  v31[0] = this;
  v31[1] = &v25;
  v26 = 0;
  if ( *((_DWORD *)a2 + 8) == 1 )
  {
    v25 = MkvMfSourceLib::MkvMfStreamVideo::CreateStream(this, a2, &v26);
    if ( v25 < 0 )
    {
      v9 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v7, v8);
        CallStackTracing::s_wpInstance = v10;
        if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
        {
          v9 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v9 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v9 + 8) )
      {
        v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
        if ( v25 < 0 && *((_DWORD *)v11 + 499) != v25 )
          CallStackContext::TraceFailure(v11, "MkvMfSourceLib::MkvMfSource::CreateStream", 161, v25);
      }
      if ( !g_wppLevels )
        goto LABEL_31;
      v12 = 22;
LABEL_30:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v25);
LABEL_31:
      v19 = v25;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
      goto LABEL_41;
    }
  }
  else if ( *((_DWORD *)a2 + 8) == 2 )
  {
    v25 = MkvMfSourceLib::MkvMfStreamAudio::CreateStream(this, a2, &v26);
    if ( v25 < 0 )
    {
      v16 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14, v15);
        CallStackTracing::s_wpInstance = v17;
        if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
        {
          v16 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v16 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
        if ( v25 < 0 && *((_DWORD *)v18 + 499) != v25 )
          CallStackContext::TraceFailure(v18, "MkvMfSourceLib::MkvMfSource::CreateStream", 166, v25);
      }
      if ( !g_wppLevels )
        goto LABEL_31;
      v12 = 23;
      goto LABEL_30;
    }
  }
  else
  {
    if ( *((_BYTE *)this + 656) || *((_DWORD *)a2 + 8) != 17 )
      goto LABEL_40;
    if ( (int)MkvMfSourceLib::MkvMfStreamSubtitle::CreateStream(this, a2, &v26) < 0 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
      v19 = 0;
      goto LABEL_41;
    }
  }
  v20 = *((_DWORD *)a2 + 9);
  v21 = v26;
  v27 = v26;
  Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(&v27);
  try
  {
    v28 = v20;
    v29 = v21;
    v27 = 0;
    std::map<unsigned long,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>::insert<std::pair<unsigned long,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>,0>(
      (char *)this + 576,
      v30,
      &v28);
    if ( v29 )
      ((void (__fastcall *)(struct IMFMediaStream *))v29->lpVtbl->Release)(v29);
    *((_QWORD *)this + 54) = **((_QWORD **)this + 72);
  }
  catch ( ... )
  {
    LODWORD(v27) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0xC3,
                     (unsigned int)"avcore\\mf\\core\\mediasource\\mkv\\lib\\mkvmfsource.cpp",
                     v22);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
    v19 = (unsigned int)v27;
LABEL_41:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v24);
    return v19;
  }
LABEL_40:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v24);
  return 0;
}

```

## disassembly

```asm
0x180011068  mov     [rsp+arg_10], rbx
0x18001106d  push    rsi
0x18001106e  push    rdi
0x18001106f  push    r14
0x180011071  sub     rsp, 80h
0x180011078  mov     rax, cs:__security_cookie
0x18001107f  xor     rax, rsp
0x180011082  mov     [rsp+98h+var_20], rax
0x180011087  mov     r14, rdx
0x18001108a  mov     rsi, rcx
0x18001108d  mov     [rsp+98h+var_64], 0
0x180011095  mov     r8d, 99h; int
0x18001109b  lea     rdx, aMkvmfsourcelib_137; "MkvMfSourceLib::MkvMfSource::CreateStre"...
0x1800110a2  lea     rcx, [rsp+98h+var_68]; this
0x1800110a7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800110ac  nop
0x1800110ad  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800110b4  cmp     byte ptr [rcx+8], 0
0x1800110b8  jz      short loc_180011110
0x1800110ba  cmp     qword ptr [rsi+2B0h], 0
0x1800110c2  jz      short loc_180011110
0x1800110c4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800110c9  mov     rdi, rax
0x1800110cc  mov     rcx, [rsi+2B0h]
0x1800110d3  mov     rdx, [rcx]
0x1800110d6  mov     rax, [rdx+128h]
0x1800110dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110e2  mov     ebx, eax
0x1800110e4  mov     rcx, [rsi+2B0h]
0x1800110eb  mov     rdx, [rcx]
0x1800110ee  mov     rax, [rdx+118h]
0x1800110f5  lea     rdx, [rsp+98h+var_30]
0x1800110fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110ff  movups  xmm0, xmmword ptr [rax]
0x180011102  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18001110a  mov     [rdi+7E0h], ebx
0x180011110  mov     [rsp+98h+var_30], rsi
0x180011115  lea     rax, [rsp+98h+var_64]
0x18001111a  mov     [rsp+98h+var_28], rax
0x18001111f  mov     [rsp+98h+var_60], 0
0x180011128  cmp     dword ptr [r14+20h], 1
0x18001112d  jnz     loc_1800111EC
0x180011133  lea     r8, [rsp+98h+var_60]; struct IMFMediaStream **
0x180011138  mov     rdx, r14; struct mkvparser::Track *
0x18001113b  mov     rcx, rsi; struct MkvMfSourceLib::MkvMfSource *
0x18001113e  call    ?CreateStream@MkvMfStreamVideo@MkvMfSourceLib@@SAJPEAVMkvMfSource@2@PEBVTrack@mkvparser@@PEAPEAUIMFMediaStream@@@Z; MkvMfSourceLib::MkvMfStreamVideo::CreateStream(MkvMfSourceLib::MkvMfSource *,mkvparser::Track const *,IMFMediaStream * *)
0x180011143  mov     [rsp+98h+var_64], eax
0x180011147  test    eax, eax
0x180011149  jns     loc_18001131B
0x18001114f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180011156  test    rcx, rcx
0x180011159  jnz     short loc_1800111A2
0x18001115b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180011162  nop     dword ptr [rax+rax+00h]
0x180011167  mov     rcx, rax
0x18001116a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180011171  test    rax, rax
0x180011174  jz      short loc_180011194
0x180011176  mov     rax, [rax]
0x180011179  mov     edx, 7F0h
0x18001117e  mov     rax, [rax+8]
0x180011182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011187  test    eax, eax
0x180011189  jz      short loc_180011194
0x18001118b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180011192  jmp     short loc_1800111A2
0x180011194  lea     rcx, qword_1800DBF70; this
0x18001119b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800111a2  cmp     byte ptr [rcx+8], 0
0x1800111a6  jz      short loc_1800111D5
0x1800111a8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800111ad  mov     r9d, [rsp+98h+var_64]; int
0x1800111b2  test    r9d, r9d
0x1800111b5  jns     short loc_1800111D5
0x1800111b7  cmp     [rax+7CCh], r9d
0x1800111be  jz      short loc_1800111D5
0x1800111c0  mov     r8d, 0A1h; int
0x1800111c6  lea     rdx, aMkvmfsourcelib_137; "MkvMfSourceLib::MkvMfSource::CreateStre"...
0x1800111cd  mov     rcx, rax; this
0x1800111d0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800111d5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800111dc  jb      loc_1800112C9
0x1800111e2  mov     edx, 16h
0x1800111e7  jmp     loc_1800112A7
0x1800111ec  cmp     dword ptr [r14+20h], 2
0x1800111f1  jnz     loc_1800112DD
0x1800111f7  lea     r8, [rsp+98h+var_60]; struct IMFMediaStream **
0x1800111fc  mov     rdx, r14; struct mkvparser::Track *
0x1800111ff  mov     rcx, rsi; struct MkvMfSourceLib::MkvMfSource *
0x180011202  call    ?CreateStream@MkvMfStreamAudio@MkvMfSourceLib@@SAJPEAVMkvMfSource@2@PEBVTrack@mkvparser@@PEAPEAUIMFMediaStream@@@Z; MkvMfSourceLib::MkvMfStreamAudio::CreateStream(MkvMfSourceLib::MkvMfSource *,mkvparser::Track const *,IMFMediaStream * *)
0x180011207  mov     [rsp+98h+var_64], eax
0x18001120b  test    eax, eax
0x18001120d  jns     loc_18001131B
0x180011213  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001121a  test    rcx, rcx
0x18001121d  jnz     short loc_180011266
0x18001121f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180011226  nop     dword ptr [rax+rax+00h]
0x18001122b  mov     rcx, rax
0x18001122e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180011235  test    rax, rax
0x180011238  jz      short loc_180011258
0x18001123a  mov     rax, [rax]
0x18001123d  mov     edx, 7F0h
0x180011242  mov     rax, [rax+8]
0x180011246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001124b  test    eax, eax
0x18001124d  jz      short loc_180011258
0x18001124f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180011256  jmp     short loc_180011266
0x180011258  lea     rcx, qword_1800DBF70; this
0x18001125f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180011266  cmp     byte ptr [rcx+8], 0
0x18001126a  jz      short loc_180011299
0x18001126c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180011271  mov     r9d, [rsp+98h+var_64]; int
0x180011276  test    r9d, r9d
0x180011279  jns     short loc_180011299
0x18001127b  cmp     [rax+7CCh], r9d
0x180011282  jz      short loc_180011299
0x180011284  mov     r8d, 0A6h; int
0x18001128a  lea     rdx, aMkvmfsourcelib_137; "MkvMfSourceLib::MkvMfSource::CreateStre"...
0x180011291  mov     rcx, rax; this
0x180011294  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180011299  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800112a0  jb      short loc_1800112C9
0x1800112a2  mov     edx, 17h
0x1800112a7  mov     eax, [rsp+98h+var_64]
0x1800112ab  mov     [rsp+98h+var_78], eax
0x1800112af  mov     r9, rsi
0x1800112b2  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x1800112b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800112c0  mov     rcx, [rcx+10h]
0x1800112c4  call    WPP_SF_qD
0x1800112c9  mov     ebx, [rsp+98h+var_64]
0x1800112cd  lea     rcx, [rsp+98h+var_60]
0x1800112d2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800112d7  nop
0x1800112d8  jmp     loc_1800113CC
0x1800112dd  cmp     byte ptr [rsi+290h], 0
0x1800112e4  jnz     loc_180011384
0x1800112ea  cmp     dword ptr [r14+20h], 11h
0x1800112ef  jnz     loc_180011384
0x1800112f5  lea     r8, [rsp+98h+var_60]; struct IMFMediaStream **
0x1800112fa  mov     rdx, r14; struct mkvparser::Track *
0x1800112fd  mov     rcx, rsi; struct MkvMfSourceLib::MkvMfSource *
0x180011300  call    ?CreateStream@MkvMfStreamSubtitle@MkvMfSourceLib@@SAJPEAVMkvMfSource@2@PEBVTrack@mkvparser@@PEAPEAUIMFMediaStream@@@Z; MkvMfSourceLib::MkvMfStreamSubtitle::CreateStream(MkvMfSourceLib::MkvMfSource *,mkvparser::Track const *,IMFMediaStream * *)
0x180011305  test    eax, eax
0x180011307  jns     short loc_18001131B
0x180011309  lea     rcx, [rsp+98h+var_60]
0x18001130e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011313  nop
0x180011314  xor     ebx, ebx
0x180011316  jmp     loc_1800113CC
0x18001131b  mov     edi, [r14+24h]
0x18001131f  mov     rbx, [rsp+98h+var_60]
0x180011324  mov     [rsp+98h+var_58], rbx
0x180011329  lea     rcx, [rsp+98h+var_58]
0x18001132e  call    ?InternalAddRef@?$ComPtr@VMkvMfStreamSubtitle@MkvMfSourceLib@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(void)
0x180011333  nop
0x180011334  mov     [rsp+98h+var_50], edi
0x180011338  mov     [rsp+98h+var_48], rbx
0x18001133d  mov     [rsp+98h+var_58], 0
0x180011346  lea     rbx, [rsi+240h]
0x18001134d  lea     r8, [rsp+98h+var_50]
0x180011352  lea     rdx, [rsp+98h+var_40]
0x180011357  mov     rcx, rbx
0x18001135a  call    ??$insert@U?$pair@KV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@$0A@@?$map@KV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@@5@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@KV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@1@@Z; std::map<ulong,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>::insert<std::pair<ulong,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>,0>(std::pair<ulong,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>> &&)
0x18001135f  nop
0x180011360  mov     rcx, [rsp+98h+var_48]
0x180011365  test    rcx, rcx
0x180011368  jz      short loc_180011377
0x18001136a  mov     rax, [rcx]
0x18001136d  mov     rax, [rax+10h]
0x180011371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011376  nop
0x180011377  mov     rax, [rbx]
0x18001137a  mov     rcx, [rax]
0x18001137d  mov     [rsi+1B0h], rcx
0x180011384  lea     rcx, [rsp+98h+var_60]
0x180011389  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001138e  nop
0x18001138f  lea     rcx, [rsp+98h+var_68]; this
0x180011394  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180011399  xor     eax, eax
0x18001139b  mov     rcx, [rsp+98h+var_20]
0x1800113a0  xor     rcx, rsp; StackCookie
0x1800113a3  call    __security_check_cookie
0x1800113a8  mov     rbx, [rsp+98h+arg_10]
0x1800113b0  add     rsp, 80h
0x1800113b7  pop     r14
0x1800113b9  pop     rdi
0x1800113ba  pop     rsi
0x1800113bb  retn
0x1800113bd  lea     rcx, [rsp+98h+var_60]
0x1800113c2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800113c7  nop
0x1800113c8  mov     ebx, dword ptr [rsp+98h+var_58]
0x1800113cc  lea     rcx, [rsp+98h+var_68]; this
0x1800113d1  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800113d6  mov     eax, ebx
0x1800113d8  jmp     short loc_18001139B
```
