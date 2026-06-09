# MkvMfSourceLib::MkvMfSource::Command::OnStartComplete(bool)

- ea: `0x180017764`
- end: `0x180017e34`
- name: `?OnStartComplete@Command@MkvMfSource@MkvMfSourceLib@@AEBAJ_N@Z`
- size: `1744`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource::Command *__hidden this, bool)`
- caller_count: `2`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180016ba0`
- `0x180017460`

## callees

- `0x1800023e0`
- `0x1800097f0`
- `0x1800098b8`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x18000db40`
- `0x180011b30`
- `0x180017764`
- `0x18001be98`
- `0x18001ce90`
- `0x180020d84`
- `0x180020e54`
- `0x1800252e8`
- `0x1800266d4`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017835`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017965`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017a81`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017be7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017d07`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017835`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017965`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017a81`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017be7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017d07`
- `MFPlat!MFCreateMediaEvent` at `0x180017948`
- `MFPlat!MFCreateMediaEvent` at `0x180017948`

## string_xrefs

- `0x18001779c`: `MkvMfSourceLib::MkvMfSource::Command::OnStartComplete`
- `0x180017899`: `MkvMfSourceLib::MkvMfSource::Command::OnStartComplete`
- `0x1800179c9`: `MkvMfSourceLib::MkvMfSource::Command::OnStartComplete`
- `0x180017ae5`: `MkvMfSourceLib::MkvMfSource::Command::OnStartComplete`
- `0x180017c80`: `MkvMfSourceLib::MkvMfSource::Command::OnStartComplete`
- `0x180017d6b`: `MkvMfSourceLib::MkvMfSource::Command::OnStartComplete`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall MkvMfSourceLib::MkvMfSource::Command::OnStartComplete(
        MkvMfSourceLib::MkvMfSource::Command *this,
        char a2)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  unsigned int v12; // ebx
  __int64 CurrTime; // rax
  __int64 v14; // r15
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  IMFMediaEvent *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  IMFMediaEvent *v28; // rcx
  _QWORD *v29; // rdi
  _QWORD *v30; // rbx
  MkvMfSourceLib::MkvMfStream *v31; // rbx
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // r9
  struct CallStackContext *v40; // rax
  int v41; // edi
  IMFMediaEvent *v42; // rcx
  __int64 *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  IMFMediaEvent *v46; // rcx
  IMFMediaEvent *v47; // rcx
  int v49; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v50[4]; // [rsp+34h] [rbp-3Ch] BYREF
  IMFMediaEvent *ppEvent; // [rsp+38h] [rbp-38h] BYREF
  _QWORD *v52; // [rsp+40h] [rbp-30h] BYREF
  MkvMfSourceLib::MkvMfStream *v53; // [rsp+48h] [rbp-28h] BYREF
  _QWORD v54[2]; // [rsp+50h] [rbp-20h] BYREF

  v49 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v50,
    "MkvMfSourceLib::MkvMfSource::Command::OnStartComplete",
    3896);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 2) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 296LL))(*((_QWORD *)this + 2));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 2) + 280LL))(
                                                            *((_QWORD *)this + 2),
                                                            v54);
    *((_DWORD *)ThreadRelativeContext + 504) = v5;
  }
  v54[0] = this;
  v54[1] = &v49;
  v49 = MkvMfSourceLib::MkvMfSource::SetEOP(*((MkvMfSourceLib::MkvMfSource **)this + 1), 0);
  if ( v49 >= 0 )
  {
    MkvMfSourceLib::MkvMfSource::SetupBuffering(*((MkvMfSourceLib::MkvMfSource **)this + 1));
    CurrTime = MkvMfSourceLib::MkvMfSource::GetCurrTime(
                 *((MkvMfSourceLib::MkvMfSource **)this + 1),
                 *((struct IMFPresentationDescriptor **)this + 3));
    v14 = CurrTime;
    if ( (unsigned __int8)byte_1800D78D3 >= 4u )
      WPP_SF_qi(
        *((_QWORD *)WPP_GLOBAL_Control + 17),
        253,
        &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
        this,
        CurrTime);
    ppEvent = 0;
    v49 = MFCreateMediaEvent(
            0xC9u,
            &GUID_00000000_0000_0000_0000_000000000000,
            0,
            (const PROPVARIANT *)((char *)this + 32),
            &ppEvent);
    if ( v49 >= 0 )
    {
      if ( v14 < 0
        || (v49 = ((__int64 (__fastcall *)(IMFMediaEvent *, const GUID *, __int64))ppEvent->lpVtbl->SetUINT64)(
                    ppEvent,
                    &MF_EVENT_SOURCE_ACTUAL_START,
                    v14 / 100),
            v49 >= 0) )
      {
        v49 = (*(__int64 (__fastcall **)(_QWORD, IMFMediaEvent *))(**(_QWORD **)(*((_QWORD *)this + 1) + 144LL) + 48LL))(
                *(_QWORD *)(*((_QWORD *)this + 1) + 144LL),
                ppEvent);
        v29 = *(_QWORD **)(*((_QWORD *)this + 1) + 576LL);
        v30 = (_QWORD *)*v29;
        v52 = (_QWORD *)*v29;
        while ( v30 != v29 )
        {
          std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>>,std::_Iterator_base0>::operator++(&v52);
          v31 = (MkvMfSourceLib::MkvMfStream *)v30[5];
          v53 = v31;
          Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(&v53);
          if ( (*(unsigned __int8 (__fastcall **)(MkvMfSourceLib::MkvMfStream *))(*(_QWORD *)v31 + 120LL))(v31) )
          {
            if ( v31 )
              (*(void (__fastcall **)(MkvMfSourceLib::MkvMfStream *))(*(_QWORD *)v31 + 16LL))(v31);
          }
          else
          {
            if ( a2 )
            {
              v49 = MkvMfSourceLib::MkvMfStream::Restart(v31);
              if ( v49 < 0 )
              {
                v35 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v33, v34);
                  CallStackTracing::s_wpInstance = v36;
                  if ( v36
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
                  {
                    v35 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v35 = &qword_1800D6F70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                  }
                }
                if ( *((_BYTE *)v35 + 8) )
                {
                  v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
                  if ( v49 < 0 && *((_DWORD *)v40 + 499) != v49 )
                    CallStackContext::TraceFailure(
                      v40,
                      "MkvMfSourceLib::MkvMfSource::Command::OnStartComplete",
                      3935,
                      v49);
                }
                if ( g_wppLevels )
                  WPP_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    256,
                    &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
                    this,
                    v49);
                v41 = v49;
                if ( v31 )
                  (*(void (__fastcall **)(MkvMfSourceLib::MkvMfStream *))(*(_QWORD *)v31 + 16LL))(v31);
                v42 = ppEvent;
                if ( ppEvent )
                {
                  ppEvent = 0;
                  ((void (__fastcall *)(IMFMediaEvent *))v42->lpVtbl->Release)(v42);
                }
LABEL_77:
                v12 = v41;
                goto LABEL_97;
              }
            }
            else
            {
              v49 = MkvMfSourceLib::MkvMfStream::Start(v31, (const struct tagPROPVARIANT *)((char *)this + 32));
              if ( v49 < 0 )
              {
                v43 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37, v38, v39);
                  CallStackTracing::s_wpInstance = v44;
                  if ( v44
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
                  {
                    v43 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v43 = &qword_1800D6F70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                  }
                }
                if ( *((_BYTE *)v43 + 8) )
                {
                  v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
                  if ( v49 < 0 && *((_DWORD *)v45 + 499) != v49 )
                    CallStackContext::TraceFailure(
                      v45,
                      "MkvMfSourceLib::MkvMfSource::Command::OnStartComplete",
                      3939,
                      v49);
                }
                if ( g_wppLevels )
                  WPP_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    257,
                    &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
                    this,
                    v49);
                v41 = v49;
                if ( v31 )
                  (*(void (__fastcall **)(MkvMfSourceLib::MkvMfStream *))(*(_QWORD *)v31 + 16LL))(v31);
                v46 = ppEvent;
                if ( ppEvent )
                {
                  ppEvent = 0;
                  ((void (__fastcall *)(IMFMediaEvent *))v46->lpVtbl->Release)(v46);
                }
                goto LABEL_77;
              }
            }
            *((_QWORD *)v31 + 33) = v14;
            if ( v31 )
              (*(void (__fastcall **)(MkvMfSourceLib::MkvMfStream *))(*(_QWORD *)v31 + 16LL))(v31);
          }
          v30 = v52;
        }
        v47 = ppEvent;
        if ( ppEvent )
        {
          ppEvent = 0;
          ((void (__fastcall *)(IMFMediaEvent *))v47->lpVtbl->Release)(v47);
        }
        v12 = 0;
      }
      else
      {
        v25 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23, v24);
          CallStackTracing::s_wpInstance = v26;
          if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
          {
            v25 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v25 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v25 + 8) )
        {
          v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
          if ( v49 < 0 && *((_DWORD *)v27 + 499) != v49 )
            CallStackContext::TraceFailure(v27, "MkvMfSourceLib::MkvMfSource::Command::OnStartComplete", 3911, v49);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            255,
            &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
            this,
            v49);
        v12 = v49;
        v28 = ppEvent;
        if ( ppEvent )
        {
          ppEvent = 0;
          ((void (__fastcall *)(IMFMediaEvent *))v28->lpVtbl->Release)(v28);
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
        if ( v49 < 0 && *((_DWORD *)v20 + 499) != v49 )
          CallStackContext::TraceFailure(v20, "MkvMfSourceLib::MkvMfSource::Command::OnStartComplete", 3905, v49);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 254, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v49);
      v12 = v49;
      v21 = ppEvent;
      if ( ppEvent )
      {
        ppEvent = 0;
        ((void (__fastcall *)(IMFMediaEvent *))v21->lpVtbl->Release)(v21);
      }
    }
  }
  else
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
      if ( v49 < 0 && *((_DWORD *)v11 + 499) != v49 )
        CallStackContext::TraceFailure(v11, "MkvMfSourceLib::MkvMfSource::Command::OnStartComplete", 3898, v49);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 252, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v49);
    v12 = v49;
  }
LABEL_97:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v50);
  return v12;
}

```

## disassembly

```asm
0x180017764  mov     [rsp-28h+arg_8], rbx
0x180017769  mov     [rsp-28h+arg_10], rsi
0x18001776e  push    rbp
0x18001776f  push    rdi
0x180017770  push    r12
0x180017772  push    r13
0x180017774  push    r15
0x180017776  mov     rbp, rsp
0x180017779  sub     rsp, 70h
0x18001777d  mov     rax, cs:__security_cookie
0x180017784  xor     rax, rsp
0x180017787  mov     [rbp+var_10], rax
0x18001778b  mov     r13b, dl
0x18001778e  mov     rsi, rcx
0x180017791  xor     edi, edi
0x180017793  mov     [rbp+var_40], edi
0x180017796  mov     r8d, 0F38h; int
0x18001779c  lea     rdx, aMkvmfsourcelib_18; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x1800177a3  lea     rcx, [rbp+var_3C]; this
0x1800177a7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800177ac  nop
0x1800177ad  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800177b4  cmp     [rcx+8], dil
0x1800177b8  jz      short loc_180017807
0x1800177ba  cmp     [rsi+10h], rdi
0x1800177be  jz      short loc_180017807
0x1800177c0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800177c5  mov     rdi, rax
0x1800177c8  mov     rcx, [rsi+10h]
0x1800177cc  mov     rdx, [rcx]
0x1800177cf  mov     rax, [rdx+128h]
0x1800177d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800177db  mov     ebx, eax
0x1800177dd  mov     rcx, [rsi+10h]
0x1800177e1  mov     rdx, [rcx]
0x1800177e4  mov     rax, [rdx+118h]
0x1800177eb  lea     rdx, [rbp+var_20]
0x1800177ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800177f4  movups  xmm0, xmmword ptr [rax]
0x1800177f7  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800177ff  mov     [rdi+7E0h], ebx
0x180017805  xor     edi, edi
0x180017807  mov     [rbp+var_20], rsi
0x18001780b  lea     rax, [rbp+var_40]
0x18001780f  mov     [rbp+var_18], rax
0x180017813  xor     edx, edx; bool
0x180017815  mov     rcx, [rsi+8]; this
0x180017819  call    ?SetEOP@MkvMfSource@MkvMfSourceLib@@AEAAJ_N@Z; MkvMfSourceLib::MkvMfSource::SetEOP(bool)
0x18001781e  mov     [rbp+var_40], eax
0x180017821  test    eax, eax
0x180017823  jns     loc_1800178DF
0x180017829  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017830  test    rcx, rcx
0x180017833  jnz     short loc_180017876
0x180017835  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001783b  mov     rcx, rax
0x18001783e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180017845  test    rax, rax
0x180017848  jz      short loc_180017868
0x18001784a  mov     rax, [rax]
0x18001784d  mov     edx, 7F0h
0x180017852  mov     rax, [rax+8]
0x180017856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001785b  test    eax, eax
0x18001785d  jz      short loc_180017868
0x18001785f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017866  jmp     short loc_180017876
0x180017868  lea     rcx, qword_1800D6F70; this
0x18001786f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180017876  cmp     [rcx+8], dil
0x18001787a  jz      short loc_1800178A8
0x18001787c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180017881  mov     r9d, [rbp+var_40]; int
0x180017885  test    r9d, r9d
0x180017888  jns     short loc_1800178A8
0x18001788a  cmp     [rax+7CCh], r9d
0x180017891  jz      short loc_1800178A8
0x180017893  mov     r8d, 0F3Ah; int
0x180017899  lea     rdx, aMkvmfsourcelib_18; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x1800178a0  mov     rcx, rax; this
0x1800178a3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800178a8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800178af  jb      short loc_1800178D7
0x1800178b1  mov     edx, 0FCh
0x1800178b6  mov     eax, [rbp+var_40]
0x1800178b9  mov     dword ptr [rsp+70h+ppEvent], eax
0x1800178bd  mov     r9, rsi
0x1800178c0  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x1800178c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800178ce  mov     rcx, [rcx+10h]
0x1800178d2  call    WPP_SF_qD
0x1800178d7  mov     ebx, [rbp+var_40]
0x1800178da  jmp     loc_180017A24
0x1800178df  mov     rcx, [rsi+8]; this
0x1800178e3  call    ?SetupBuffering@MkvMfSource@MkvMfSourceLib@@AEAAJXZ; MkvMfSourceLib::MkvMfSource::SetupBuffering(void)
0x1800178e8  mov     rdx, [rsi+18h]; struct IMFPresentationDescriptor *
0x1800178ec  mov     rcx, [rsi+8]; this
0x1800178f0  call    ?GetCurrTime@MkvMfSource@MkvMfSourceLib@@AEBA_JPEAUIMFPresentationDescriptor@@@Z; MkvMfSourceLib::MkvMfSource::GetCurrTime(IMFPresentationDescriptor *)
0x1800178f5  mov     r15, rax
0x1800178f8  cmp     cs:byte_1800D78D3, 4
0x1800178ff  jb      short loc_180017928
0x180017901  mov     edx, 0FDh
0x180017906  mov     [rsp+70h+ppEvent], rax
0x18001790b  mov     r9, rsi
0x18001790e  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180017915  mov     rcx, cs:WPP_GLOBAL_Control
0x18001791c  mov     rcx, [rcx+88h]
0x180017923  call    WPP_SF_qi
0x180017928  mov     [rbp+var_38], rdi
0x18001792c  lea     rax, [rbp+var_38]
0x180017930  mov     [rsp+70h+ppEvent], rax; ppEvent
0x180017935  lea     r9, [rsi+20h]; pvValue
0x180017939  xor     r8d, r8d; hrStatus
0x18001793c  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; guidExtendedType
0x180017943  mov     ecx, 0C9h; met
0x180017948  call    cs:__imp_MFCreateMediaEvent
0x18001794e  mov     [rbp+var_40], eax
0x180017951  test    eax, eax
0x180017953  jns     loc_180017A29
0x180017959  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017960  test    rcx, rcx
0x180017963  jnz     short loc_1800179A6
0x180017965  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001796b  mov     rcx, rax
0x18001796e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180017975  test    rax, rax
0x180017978  jz      short loc_180017998
0x18001797a  mov     rax, [rax]
0x18001797d  mov     edx, 7F0h
0x180017982  mov     rax, [rax+8]
0x180017986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001798b  test    eax, eax
0x18001798d  jz      short loc_180017998
0x18001798f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017996  jmp     short loc_1800179A6
0x180017998  lea     rcx, qword_1800D6F70; this
0x18001799f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800179a6  cmp     [rcx+8], dil
0x1800179aa  jz      short loc_1800179D8
0x1800179ac  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800179b1  mov     r9d, [rbp+var_40]; int
0x1800179b5  test    r9d, r9d
0x1800179b8  jns     short loc_1800179D8
0x1800179ba  cmp     [rax+7CCh], r9d
0x1800179c1  jz      short loc_1800179D8
0x1800179c3  mov     r8d, 0F41h; int
0x1800179c9  lea     rdx, aMkvmfsourcelib_18; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x1800179d0  mov     rcx, rax; this
0x1800179d3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800179d8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800179df  jb      short loc_180017A07
0x1800179e1  mov     edx, 0FEh
0x1800179e6  mov     eax, [rbp+var_40]
0x1800179e9  mov     dword ptr [rsp+70h+ppEvent], eax
0x1800179ed  mov     r9, rsi
0x1800179f0  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x1800179f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800179fe  mov     rcx, [rcx+10h]
0x180017a02  call    WPP_SF_qD
0x180017a07  mov     ebx, [rbp+var_40]
0x180017a0a  mov     rcx, [rbp+var_38]
0x180017a0e  test    rcx, rcx
0x180017a11  jz      short loc_180017A24
0x180017a13  mov     [rbp+var_38], rdi
0x180017a17  mov     rax, [rcx]
0x180017a1a  mov     rax, [rax+10h]
0x180017a1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a23  nop
0x180017a24  jmp     loc_180017E04
0x180017a29  test    r15, r15
0x180017a2c  js      loc_180017B45
0x180017a32  mov     rcx, [rbp+var_38]
0x180017a36  mov     r9, [rcx]
0x180017a39  mov     rax, 0A3D70A3D70A3D70Bh
0x180017a43  imul    r15
0x180017a46  add     rdx, r15
0x180017a49  sar     rdx, 6
0x180017a4d  mov     r8, rdx
0x180017a50  shr     r8, 3Fh
0x180017a54  add     r8, rdx
0x180017a57  lea     rdx, MF_EVENT_SOURCE_ACTUAL_START
0x180017a5e  mov     rax, [r9+0B0h]
0x180017a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a6a  mov     [rbp+var_40], eax
0x180017a6d  test    eax, eax
0x180017a6f  jns     loc_180017B45
0x180017a75  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017a7c  test    rcx, rcx
0x180017a7f  jnz     short loc_180017AC2
0x180017a81  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180017a87  mov     rcx, rax
0x180017a8a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180017a91  test    rax, rax
0x180017a94  jz      short loc_180017AB4
0x180017a96  mov     rax, [rax]
0x180017a99  mov     edx, 7F0h
0x180017a9e  mov     rax, [rax+8]
0x180017aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017aa7  test    eax, eax
0x180017aa9  jz      short loc_180017AB4
0x180017aab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017ab2  jmp     short loc_180017AC2
0x180017ab4  lea     rcx, qword_1800D6F70; this
0x180017abb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180017ac2  cmp     [rcx+8], dil
0x180017ac6  jz      short loc_180017AF4
0x180017ac8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180017acd  mov     r9d, [rbp+var_40]; int
0x180017ad1  test    r9d, r9d
0x180017ad4  jns     short loc_180017AF4
0x180017ad6  cmp     [rax+7CCh], r9d
0x180017add  jz      short loc_180017AF4
0x180017adf  mov     r8d, 0F47h; int
0x180017ae5  lea     rdx, aMkvmfsourcelib_18; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180017aec  mov     rcx, rax; this
0x180017aef  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180017af4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180017afb  jb      short loc_180017B23
0x180017afd  mov     edx, 0FFh
0x180017b02  mov     eax, [rbp+var_40]
0x180017b05  mov     dword ptr [rsp+70h+ppEvent], eax
0x180017b09  mov     r9, rsi
0x180017b0c  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180017b13  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b1a  mov     rcx, [rcx+10h]
0x180017b1e  call    WPP_SF_qD
0x180017b23  mov     ebx, [rbp+var_40]
0x180017b26  mov     rcx, [rbp+var_38]
0x180017b2a  test    rcx, rcx
0x180017b2d  jz      short loc_180017B40
0x180017b2f  mov     [rbp+var_38], rdi
0x180017b33  mov     rax, [rcx]
0x180017b36  mov     rax, [rax+10h]
0x180017b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b3f  nop
0x180017b40  jmp     loc_180017A24
0x180017b45  mov     rax, [rsi+8]
0x180017b49  mov     rcx, [rax+90h]
0x180017b50  mov     rax, [rcx]
0x180017b53  mov     rdx, [rbp+var_38]
0x180017b57  mov     rax, [rax+30h]
0x180017b5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b60  mov     [rbp+var_40], eax
0x180017b63  mov     rdi, [rsi+8]
0x180017b67  mov     rdi, [rdi+240h]
0x180017b6e  mov     rbx, [rdi]
0x180017b71  mov     [rbp+var_30], rbx
0x180017b75  cmp     rbx, rdi
0x180017b78  jz      loc_180017DE4
0x180017b7e  lea     rcx, [rbp+var_30]
0x180017b82  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>>,std::_Iterator_base0>::operator++(void)
0x180017b87  mov     rbx, [rbx+28h]
0x180017b8b  mov     [rbp+var_28], rbx
0x180017b8f  lea     rcx, [rbp+var_28]
0x180017b93  call    ?InternalAddRef@?$ComPtr@VMkvMfStreamSubtitle@MkvMfSourceLib@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(void)
0x180017b98  nop
0x180017b99  mov     rax, [rbx]
0x180017b9c  mov     rcx, rbx
0x180017b9f  mov     rax, [rax+78h]
0x180017ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ba8  test    al, al
0x180017baa  jz      short loc_180017BC7
0x180017bac  test    rbx, rbx
0x180017baf  jz      short loc_180017BC1
0x180017bb1  mov     rax, [rbx]
0x180017bb4  mov     rcx, rbx
0x180017bb7  mov     rax, [rax+10h]
0x180017bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bc0  nop
0x180017bc1  mov     rbx, [rbp+var_30]
0x180017bc5  jmp     short loc_180017B75
0x180017bc7  mov     rcx, rbx; this
0x180017bca  test    r13b, r13b
0x180017bcd  jz      short loc_180017C1A
0x180017bcf  call    ?Restart@MkvMfStream@MkvMfSourceLib@@QEAAJXZ; MkvMfSourceLib::MkvMfStream::Restart(void)
0x180017bd4  mov     [rbp+var_40], eax
0x180017bd7  test    eax, eax
0x180017bd9  jns     short loc_180017C2E
0x180017bdb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017be2  test    rcx, rcx
0x180017be5  jnz     short loc_180017C5D
0x180017be7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180017bed  mov     rcx, rax
0x180017bf0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180017bf7  test    rax, rax
0x180017bfa  jz      short loc_180017C4F
0x180017bfc  mov     rax, [rax]
0x180017bff  mov     edx, 7F0h
0x180017c04  mov     rax, [rax+8]
0x180017c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c0d  test    eax, eax
0x180017c0f  jz      short loc_180017C4F
0x180017c11  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017c18  jmp     short loc_180017C5D
0x180017c1a  lea     rdx, [rsi+20h]; struct tagPROPVARIANT *
0x180017c1e  call    ?Start@MkvMfStream@MkvMfSourceLib@@QEAAJAEBUtagPROPVARIANT@@@Z; MkvMfSourceLib::MkvMfStream::Start(tagPROPVARIANT const &)
0x180017c23  mov     [rbp+var_40], eax
0x180017c26  test    eax, eax
0x180017c28  js      loc_180017CFB
0x180017c2e  mov     [rbx+108h], r15
  ... truncated ...
```
