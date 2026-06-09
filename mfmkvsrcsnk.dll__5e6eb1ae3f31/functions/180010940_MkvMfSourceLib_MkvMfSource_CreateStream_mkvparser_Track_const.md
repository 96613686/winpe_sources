# MkvMfSourceLib::MkvMfSource::CreateStream(mkvparser::Track const *)

- ea: `0x180010940`
- end: `0x180010ca5`
- name: `?CreateStream@MkvMfSource@MkvMfSourceLib@@AEAAJPEBVTrack@mkvparser@@@Z`
- size: `869`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource *__hidden this, const struct mkvparser::Track *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18001f300`

## callees

- `0x1800023e0`
- `0x180005ab8`
- `0x1800097f0`
- `0x1800098b8`
- `0x18000cd2c`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180010940`
- `0x180020d84`
- `0x18002c340`
- `0x18002f8a8`
- `0x1800317ac`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010a33`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010af1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010a33`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010af1`

## string_xrefs

- `0x180010973`: `MkvMfSourceLib::MkvMfSource::CreateStream`
- `0x180010a98`: `MkvMfSourceLib::MkvMfSource::CreateStream`
- `0x180010b56`: `MkvMfSourceLib::MkvMfSource::CreateStream`

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
          v9 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v16 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x180010940  mov     [rsp+arg_10], rbx
0x180010945  push    rsi
0x180010946  push    rdi
0x180010947  push    r14
0x180010949  sub     rsp, 80h
0x180010950  mov     rax, cs:__security_cookie
0x180010957  xor     rax, rsp
0x18001095a  mov     [rsp+98h+var_20], rax
0x18001095f  mov     r14, rdx
0x180010962  mov     rsi, rcx
0x180010965  mov     [rsp+98h+var_64], 0
0x18001096d  mov     r8d, 99h; int
0x180010973  lea     rdx, aMkvmfsourcelib_137; "MkvMfSourceLib::MkvMfSource::CreateStre"...
0x18001097a  lea     rcx, [rsp+98h+var_68]; this
0x18001097f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180010984  nop
0x180010985  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001098c  cmp     byte ptr [rcx+8], 0
0x180010990  jz      short loc_1800109E8
0x180010992  cmp     qword ptr [rsi+2B0h], 0
0x18001099a  jz      short loc_1800109E8
0x18001099c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800109a1  mov     rdi, rax
0x1800109a4  mov     rcx, [rsi+2B0h]
0x1800109ab  mov     rdx, [rcx]
0x1800109ae  mov     rax, [rdx+128h]
0x1800109b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109ba  mov     ebx, eax
0x1800109bc  mov     rcx, [rsi+2B0h]
0x1800109c3  mov     rdx, [rcx]
0x1800109c6  mov     rax, [rdx+118h]
0x1800109cd  lea     rdx, [rsp+98h+var_30]
0x1800109d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109d7  movups  xmm0, xmmword ptr [rax]
0x1800109da  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800109e2  mov     [rdi+7E0h], ebx
0x1800109e8  mov     [rsp+98h+var_30], rsi
0x1800109ed  lea     rax, [rsp+98h+var_64]
0x1800109f2  mov     [rsp+98h+var_28], rax
0x1800109f7  mov     [rsp+98h+var_60], 0
0x180010a00  cmp     dword ptr [r14+20h], 1
0x180010a05  jnz     loc_180010ABE
0x180010a0b  lea     r8, [rsp+98h+var_60]; struct IMFMediaStream **
0x180010a10  mov     rdx, r14; struct mkvparser::Track *
0x180010a13  mov     rcx, rsi; struct MkvMfSourceLib::MkvMfSource *
0x180010a16  call    ?CreateStream@MkvMfStreamVideo@MkvMfSourceLib@@SAJPEAVMkvMfSource@2@PEBVTrack@mkvparser@@PEAPEAUIMFMediaStream@@@Z; MkvMfSourceLib::MkvMfStreamVideo::CreateStream(MkvMfSourceLib::MkvMfSource *,mkvparser::Track const *,IMFMediaStream * *)
0x180010a1b  mov     [rsp+98h+var_64], eax
0x180010a1f  test    eax, eax
0x180010a21  jns     loc_180010BE7
0x180010a27  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010a2e  test    rcx, rcx
0x180010a31  jnz     short loc_180010A74
0x180010a33  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180010a39  mov     rcx, rax
0x180010a3c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180010a43  test    rax, rax
0x180010a46  jz      short loc_180010A66
0x180010a48  mov     rax, [rax]
0x180010a4b  mov     edx, 7F0h
0x180010a50  mov     rax, [rax+8]
0x180010a54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a59  test    eax, eax
0x180010a5b  jz      short loc_180010A66
0x180010a5d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010a64  jmp     short loc_180010A74
0x180010a66  lea     rcx, qword_1800D6F70; this
0x180010a6d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180010a74  cmp     byte ptr [rcx+8], 0
0x180010a78  jz      short loc_180010AA7
0x180010a7a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180010a7f  mov     r9d, [rsp+98h+var_64]; int
0x180010a84  test    r9d, r9d
0x180010a87  jns     short loc_180010AA7
0x180010a89  cmp     [rax+7CCh], r9d
0x180010a90  jz      short loc_180010AA7
0x180010a92  mov     r8d, 0A1h; int
0x180010a98  lea     rdx, aMkvmfsourcelib_137; "MkvMfSourceLib::MkvMfSource::CreateStre"...
0x180010a9f  mov     rcx, rax; this
0x180010aa2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180010aa7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180010aae  jb      loc_180010B95
0x180010ab4  mov     edx, 16h
0x180010ab9  jmp     loc_180010B73
0x180010abe  cmp     dword ptr [r14+20h], 2
0x180010ac3  jnz     loc_180010BA9
0x180010ac9  lea     r8, [rsp+98h+var_60]; struct IMFMediaStream **
0x180010ace  mov     rdx, r14; struct mkvparser::Track *
0x180010ad1  mov     rcx, rsi; struct MkvMfSourceLib::MkvMfSource *
0x180010ad4  call    ?CreateStream@MkvMfStreamAudio@MkvMfSourceLib@@SAJPEAVMkvMfSource@2@PEBVTrack@mkvparser@@PEAPEAUIMFMediaStream@@@Z; MkvMfSourceLib::MkvMfStreamAudio::CreateStream(MkvMfSourceLib::MkvMfSource *,mkvparser::Track const *,IMFMediaStream * *)
0x180010ad9  mov     [rsp+98h+var_64], eax
0x180010add  test    eax, eax
0x180010adf  jns     loc_180010BE7
0x180010ae5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010aec  test    rcx, rcx
0x180010aef  jnz     short loc_180010B32
0x180010af1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180010af7  mov     rcx, rax
0x180010afa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180010b01  test    rax, rax
0x180010b04  jz      short loc_180010B24
0x180010b06  mov     rax, [rax]
0x180010b09  mov     edx, 7F0h
0x180010b0e  mov     rax, [rax+8]
0x180010b12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b17  test    eax, eax
0x180010b19  jz      short loc_180010B24
0x180010b1b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010b22  jmp     short loc_180010B32
0x180010b24  lea     rcx, qword_1800D6F70; this
0x180010b2b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180010b32  cmp     byte ptr [rcx+8], 0
0x180010b36  jz      short loc_180010B65
0x180010b38  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180010b3d  mov     r9d, [rsp+98h+var_64]; int
0x180010b42  test    r9d, r9d
0x180010b45  jns     short loc_180010B65
0x180010b47  cmp     [rax+7CCh], r9d
0x180010b4e  jz      short loc_180010B65
0x180010b50  mov     r8d, 0A6h; int
0x180010b56  lea     rdx, aMkvmfsourcelib_137; "MkvMfSourceLib::MkvMfSource::CreateStre"...
0x180010b5d  mov     rcx, rax; this
0x180010b60  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180010b65  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180010b6c  jb      short loc_180010B95
0x180010b6e  mov     edx, 17h
0x180010b73  mov     eax, [rsp+98h+var_64]
0x180010b77  mov     [rsp+98h+var_78], eax
0x180010b7b  mov     r9, rsi
0x180010b7e  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180010b85  mov     rcx, cs:WPP_GLOBAL_Control
0x180010b8c  mov     rcx, [rcx+10h]
0x180010b90  call    WPP_SF_qD
0x180010b95  mov     ebx, [rsp+98h+var_64]
0x180010b99  lea     rcx, [rsp+98h+var_60]
0x180010b9e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010ba3  nop
0x180010ba4  jmp     loc_180010C97
0x180010ba9  cmp     byte ptr [rsi+290h], 0
0x180010bb0  jnz     loc_180010C50
0x180010bb6  cmp     dword ptr [r14+20h], 11h
0x180010bbb  jnz     loc_180010C50
0x180010bc1  lea     r8, [rsp+98h+var_60]; struct IMFMediaStream **
0x180010bc6  mov     rdx, r14; struct mkvparser::Track *
0x180010bc9  mov     rcx, rsi; struct MkvMfSourceLib::MkvMfSource *
0x180010bcc  call    ?CreateStream@MkvMfStreamSubtitle@MkvMfSourceLib@@SAJPEAVMkvMfSource@2@PEBVTrack@mkvparser@@PEAPEAUIMFMediaStream@@@Z; MkvMfSourceLib::MkvMfStreamSubtitle::CreateStream(MkvMfSourceLib::MkvMfSource *,mkvparser::Track const *,IMFMediaStream * *)
0x180010bd1  test    eax, eax
0x180010bd3  jns     short loc_180010BE7
0x180010bd5  lea     rcx, [rsp+98h+var_60]
0x180010bda  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010bdf  nop
0x180010be0  xor     ebx, ebx
0x180010be2  jmp     loc_180010C97
0x180010be7  mov     edi, [r14+24h]
0x180010beb  mov     rbx, [rsp+98h+var_60]
0x180010bf0  mov     [rsp+98h+var_58], rbx
0x180010bf5  lea     rcx, [rsp+98h+var_58]
0x180010bfa  call    ?InternalAddRef@?$ComPtr@VMkvMfStreamSubtitle@MkvMfSourceLib@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(void)
0x180010bff  nop
0x180010c00  mov     [rsp+98h+var_50], edi
0x180010c04  mov     [rsp+98h+var_48], rbx
0x180010c09  mov     [rsp+98h+var_58], 0
0x180010c12  lea     rbx, [rsi+240h]
0x180010c19  lea     r8, [rsp+98h+var_50]
0x180010c1e  lea     rdx, [rsp+98h+var_40]
0x180010c23  mov     rcx, rbx
0x180010c26  call    ??$insert@U?$pair@KV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@$0A@@?$map@KV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@@5@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@KV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@1@@Z; std::map<ulong,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>::insert<std::pair<ulong,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>,0>(std::pair<ulong,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>> &&)
0x180010c2b  nop
0x180010c2c  mov     rcx, [rsp+98h+var_48]
0x180010c31  test    rcx, rcx
0x180010c34  jz      short loc_180010C43
0x180010c36  mov     rax, [rcx]
0x180010c39  mov     rax, [rax+10h]
0x180010c3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c42  nop
0x180010c43  mov     rax, [rbx]
0x180010c46  mov     rcx, [rax]
0x180010c49  mov     [rsi+1B0h], rcx
0x180010c50  lea     rcx, [rsp+98h+var_60]
0x180010c55  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010c5a  nop
0x180010c5b  lea     rcx, [rsp+98h+var_68]; this
0x180010c60  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180010c65  xor     eax, eax
0x180010c67  mov     rcx, [rsp+98h+var_20]
0x180010c6c  xor     rcx, rsp; StackCookie
0x180010c6f  call    __security_check_cookie
0x180010c74  mov     rbx, [rsp+98h+arg_10]
0x180010c7c  add     rsp, 80h
0x180010c83  pop     r14
0x180010c85  pop     rdi
0x180010c86  pop     rsi
0x180010c87  retn
0x180010c88  lea     rcx, [rsp+98h+var_60]
0x180010c8d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010c92  nop
0x180010c93  mov     ebx, dword ptr [rsp+98h+var_58]
0x180010c97  lea     rcx, [rsp+98h+var_68]; this
0x180010c9c  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180010ca1  mov     eax, ebx
0x180010ca3  jmp     short loc_180010C67
```
