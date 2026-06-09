# MkvMfSourceLib::MkvMfSource::Command::OnStartComplete(bool)

- ea: `0x180018260`
- end: `0x180018955`
- name: `?OnStartComplete@Command@MkvMfSource@MkvMfSourceLib@@AEBAJ_N@Z`
- size: `1781`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource::Command *__hidden this, bool)`
- caller_count: `2`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180017658`
- `0x180017f48`

## callees

- `0x180002400`
- `0x180009b04`
- `0x180009bec`
- `0x18000d554`
- `0x18000ddc0`
- `0x18000e148`
- `0x180012310`
- `0x180018260`
- `0x18001cb78`
- `0x18001dc28`
- `0x180021b9c`
- `0x180021c78`
- `0x1800262a8`
- `0x1800276f4`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018331`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001846d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001858f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800186fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018821`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018331`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001846d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001858f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800186fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018821`
- `MFPlat!MFCreateMediaEvent` at `0x18001844a`
- `MFPlat!MFCreateMediaEvent` at `0x18001844a`

## string_xrefs

- `0x180018298`: `MkvMfSourceLib::MkvMfSource::Command::OnStartComplete`
- `0x18001839b`: `MkvMfSourceLib::MkvMfSource::Command::OnStartComplete`
- `0x1800184d7`: `MkvMfSourceLib::MkvMfSource::Command::OnStartComplete`
- `0x1800185f9`: `MkvMfSourceLib::MkvMfSource::Command::OnStartComplete`
- `0x18001879a`: `MkvMfSourceLib::MkvMfSource::Command::OnStartComplete`
- `0x18001888b`: `MkvMfSourceLib::MkvMfSource::Command::OnStartComplete`

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
    if ( (unsigned __int8)byte_1800DC8D3 >= 4u )
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
                    v35 = &qword_1800DBF70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                    v43 = &qword_1800DBF70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v25 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v18 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v9 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x180018260  mov     [rsp-28h+arg_8], rbx
0x180018265  mov     [rsp-28h+arg_10], rsi
0x18001826a  push    rbp
0x18001826b  push    rdi
0x18001826c  push    r12
0x18001826e  push    r13
0x180018270  push    r15
0x180018272  mov     rbp, rsp
0x180018275  sub     rsp, 70h
0x180018279  mov     rax, cs:__security_cookie
0x180018280  xor     rax, rsp
0x180018283  mov     [rbp+var_10], rax
0x180018287  mov     r13b, dl
0x18001828a  mov     rsi, rcx
0x18001828d  xor     edi, edi
0x18001828f  mov     [rbp+var_40], edi
0x180018292  mov     r8d, 0F38h; int
0x180018298  lea     rdx, aMkvmfsourcelib_18; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x18001829f  lea     rcx, [rbp+var_3C]; this
0x1800182a3  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800182a8  nop
0x1800182a9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800182b0  cmp     [rcx+8], dil
0x1800182b4  jz      short loc_180018303
0x1800182b6  cmp     [rsi+10h], rdi
0x1800182ba  jz      short loc_180018303
0x1800182bc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800182c1  mov     rdi, rax
0x1800182c4  mov     rcx, [rsi+10h]
0x1800182c8  mov     rdx, [rcx]
0x1800182cb  mov     rax, [rdx+128h]
0x1800182d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182d7  mov     ebx, eax
0x1800182d9  mov     rcx, [rsi+10h]
0x1800182dd  mov     rdx, [rcx]
0x1800182e0  mov     rax, [rdx+118h]
0x1800182e7  lea     rdx, [rbp+var_20]
0x1800182eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182f0  movups  xmm0, xmmword ptr [rax]
0x1800182f3  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800182fb  mov     [rdi+7E0h], ebx
0x180018301  xor     edi, edi
0x180018303  mov     [rbp+var_20], rsi
0x180018307  lea     rax, [rbp+var_40]
0x18001830b  mov     [rbp+var_18], rax
0x18001830f  xor     edx, edx; bool
0x180018311  mov     rcx, [rsi+8]; this
0x180018315  call    ?SetEOP@MkvMfSource@MkvMfSourceLib@@AEAAJ_N@Z; MkvMfSourceLib::MkvMfSource::SetEOP(bool)
0x18001831a  mov     [rbp+var_40], eax
0x18001831d  test    eax, eax
0x18001831f  jns     loc_1800183E1
0x180018325  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001832c  test    rcx, rcx
0x18001832f  jnz     short loc_180018378
0x180018331  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180018338  nop     dword ptr [rax+rax+00h]
0x18001833d  mov     rcx, rax
0x180018340  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180018347  test    rax, rax
0x18001834a  jz      short loc_18001836A
0x18001834c  mov     rax, [rax]
0x18001834f  mov     edx, 7F0h
0x180018354  mov     rax, [rax+8]
0x180018358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001835d  test    eax, eax
0x18001835f  jz      short loc_18001836A
0x180018361  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018368  jmp     short loc_180018378
0x18001836a  lea     rcx, qword_1800DBF70; this
0x180018371  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180018378  cmp     [rcx+8], dil
0x18001837c  jz      short loc_1800183AA
0x18001837e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180018383  mov     r9d, [rbp+var_40]; int
0x180018387  test    r9d, r9d
0x18001838a  jns     short loc_1800183AA
0x18001838c  cmp     [rax+7CCh], r9d
0x180018393  jz      short loc_1800183AA
0x180018395  mov     r8d, 0F3Ah; int
0x18001839b  lea     rdx, aMkvmfsourcelib_18; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x1800183a2  mov     rcx, rax; this
0x1800183a5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800183aa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800183b1  jb      short loc_1800183D9
0x1800183b3  mov     edx, 0FCh
0x1800183b8  mov     eax, [rbp+var_40]
0x1800183bb  mov     dword ptr [rsp+70h+ppEvent], eax
0x1800183bf  mov     r9, rsi
0x1800183c2  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x1800183c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800183d0  mov     rcx, [rcx+10h]
0x1800183d4  call    WPP_SF_qD
0x1800183d9  mov     ebx, [rbp+var_40]
0x1800183dc  jmp     loc_180018532
0x1800183e1  mov     rcx, [rsi+8]; this
0x1800183e5  call    ?SetupBuffering@MkvMfSource@MkvMfSourceLib@@AEAAJXZ; MkvMfSourceLib::MkvMfSource::SetupBuffering(void)
0x1800183ea  mov     rdx, [rsi+18h]; struct IMFPresentationDescriptor *
0x1800183ee  mov     rcx, [rsi+8]; this
0x1800183f2  call    ?GetCurrTime@MkvMfSource@MkvMfSourceLib@@AEBA_JPEAUIMFPresentationDescriptor@@@Z; MkvMfSourceLib::MkvMfSource::GetCurrTime(IMFPresentationDescriptor *)
0x1800183f7  mov     r15, rax
0x1800183fa  cmp     cs:byte_1800DC8D3, 4
0x180018401  jb      short loc_18001842A
0x180018403  mov     edx, 0FDh
0x180018408  mov     [rsp+70h+ppEvent], rax
0x18001840d  mov     r9, rsi
0x180018410  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180018417  mov     rcx, cs:WPP_GLOBAL_Control
0x18001841e  mov     rcx, [rcx+88h]
0x180018425  call    WPP_SF_qi
0x18001842a  mov     [rbp+var_38], rdi
0x18001842e  lea     rax, [rbp+var_38]
0x180018432  mov     [rsp+70h+ppEvent], rax; ppEvent
0x180018437  lea     r9, [rsi+20h]; pvValue
0x18001843b  xor     r8d, r8d; hrStatus
0x18001843e  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; guidExtendedType
0x180018445  mov     ecx, 0C9h; met
0x18001844a  call    cs:__imp_MFCreateMediaEvent
0x180018451  nop     dword ptr [rax+rax+00h]
0x180018456  mov     [rbp+var_40], eax
0x180018459  test    eax, eax
0x18001845b  jns     loc_180018537
0x180018461  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018468  test    rcx, rcx
0x18001846b  jnz     short loc_1800184B4
0x18001846d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180018474  nop     dword ptr [rax+rax+00h]
0x180018479  mov     rcx, rax
0x18001847c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180018483  test    rax, rax
0x180018486  jz      short loc_1800184A6
0x180018488  mov     rax, [rax]
0x18001848b  mov     edx, 7F0h
0x180018490  mov     rax, [rax+8]
0x180018494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018499  test    eax, eax
0x18001849b  jz      short loc_1800184A6
0x18001849d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800184a4  jmp     short loc_1800184B4
0x1800184a6  lea     rcx, qword_1800DBF70; this
0x1800184ad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800184b4  cmp     [rcx+8], dil
0x1800184b8  jz      short loc_1800184E6
0x1800184ba  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800184bf  mov     r9d, [rbp+var_40]; int
0x1800184c3  test    r9d, r9d
0x1800184c6  jns     short loc_1800184E6
0x1800184c8  cmp     [rax+7CCh], r9d
0x1800184cf  jz      short loc_1800184E6
0x1800184d1  mov     r8d, 0F41h; int
0x1800184d7  lea     rdx, aMkvmfsourcelib_18; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x1800184de  mov     rcx, rax; this
0x1800184e1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800184e6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800184ed  jb      short loc_180018515
0x1800184ef  mov     edx, 0FEh
0x1800184f4  mov     eax, [rbp+var_40]
0x1800184f7  mov     dword ptr [rsp+70h+ppEvent], eax
0x1800184fb  mov     r9, rsi
0x1800184fe  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180018505  mov     rcx, cs:WPP_GLOBAL_Control
0x18001850c  mov     rcx, [rcx+10h]
0x180018510  call    WPP_SF_qD
0x180018515  mov     ebx, [rbp+var_40]
0x180018518  mov     rcx, [rbp+var_38]
0x18001851c  test    rcx, rcx
0x18001851f  jz      short loc_180018532
0x180018521  mov     [rbp+var_38], rdi
0x180018525  mov     rax, [rcx]
0x180018528  mov     rax, [rax+10h]
0x18001852c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018531  nop
0x180018532  jmp     loc_180018924
0x180018537  test    r15, r15
0x18001853a  js      loc_180018659
0x180018540  mov     rcx, [rbp+var_38]
0x180018544  mov     r9, [rcx]
0x180018547  mov     rax, 0A3D70A3D70A3D70Bh
0x180018551  imul    r15
0x180018554  add     rdx, r15
0x180018557  sar     rdx, 6
0x18001855b  mov     r8, rdx
0x18001855e  shr     r8, 3Fh
0x180018562  add     r8, rdx
0x180018565  lea     rdx, MF_EVENT_SOURCE_ACTUAL_START
0x18001856c  mov     rax, [r9+0B0h]
0x180018573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018578  mov     [rbp+var_40], eax
0x18001857b  test    eax, eax
0x18001857d  jns     loc_180018659
0x180018583  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001858a  test    rcx, rcx
0x18001858d  jnz     short loc_1800185D6
0x18001858f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180018596  nop     dword ptr [rax+rax+00h]
0x18001859b  mov     rcx, rax
0x18001859e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800185a5  test    rax, rax
0x1800185a8  jz      short loc_1800185C8
0x1800185aa  mov     rax, [rax]
0x1800185ad  mov     edx, 7F0h
0x1800185b2  mov     rax, [rax+8]
0x1800185b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185bb  test    eax, eax
0x1800185bd  jz      short loc_1800185C8
0x1800185bf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800185c6  jmp     short loc_1800185D6
0x1800185c8  lea     rcx, qword_1800DBF70; this
0x1800185cf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800185d6  cmp     [rcx+8], dil
0x1800185da  jz      short loc_180018608
0x1800185dc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800185e1  mov     r9d, [rbp+var_40]; int
0x1800185e5  test    r9d, r9d
0x1800185e8  jns     short loc_180018608
0x1800185ea  cmp     [rax+7CCh], r9d
0x1800185f1  jz      short loc_180018608
0x1800185f3  mov     r8d, 0F47h; int
0x1800185f9  lea     rdx, aMkvmfsourcelib_18; "MkvMfSourceLib::MkvMfSource::Command::O"...
0x180018600  mov     rcx, rax; this
0x180018603  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180018608  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001860f  jb      short loc_180018637
0x180018611  mov     edx, 0FFh
0x180018616  mov     eax, [rbp+var_40]
0x180018619  mov     dword ptr [rsp+70h+ppEvent], eax
0x18001861d  mov     r9, rsi
0x180018620  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180018627  mov     rcx, cs:WPP_GLOBAL_Control
0x18001862e  mov     rcx, [rcx+10h]
0x180018632  call    WPP_SF_qD
0x180018637  mov     ebx, [rbp+var_40]
0x18001863a  mov     rcx, [rbp+var_38]
0x18001863e  test    rcx, rcx
0x180018641  jz      short loc_180018654
0x180018643  mov     [rbp+var_38], rdi
0x180018647  mov     rax, [rcx]
0x18001864a  mov     rax, [rax+10h]
0x18001864e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018653  nop
0x180018654  jmp     loc_180018532
0x180018659  mov     rax, [rsi+8]
0x18001865d  mov     rcx, [rax+90h]
0x180018664  mov     rax, [rcx]
0x180018667  mov     rdx, [rbp+var_38]
0x18001866b  mov     rax, [rax+30h]
0x18001866f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018674  mov     [rbp+var_40], eax
0x180018677  mov     rdi, [rsi+8]
0x18001867b  mov     rdi, [rdi+240h]
0x180018682  mov     rbx, [rdi]
0x180018685  mov     [rbp+var_30], rbx
0x180018689  cmp     rbx, rdi
0x18001868c  jz      loc_180018904
0x180018692  lea     rcx, [rbp+var_30]
0x180018696  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>>,std::_Iterator_base0>::operator++(void)
0x18001869b  mov     rbx, [rbx+28h]
0x18001869f  mov     [rbp+var_28], rbx
0x1800186a3  lea     rcx, [rbp+var_28]
0x1800186a7  call    ?InternalAddRef@?$ComPtr@VMkvMfStreamSubtitle@MkvMfSourceLib@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(void)
0x1800186ac  nop
0x1800186ad  mov     rax, [rbx]
0x1800186b0  mov     rcx, rbx
0x1800186b3  mov     rax, [rax+78h]
0x1800186b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186bc  test    al, al
0x1800186be  jz      short loc_1800186DB
0x1800186c0  test    rbx, rbx
0x1800186c3  jz      short loc_1800186D5
0x1800186c5  mov     rax, [rbx]
0x1800186c8  mov     rcx, rbx
0x1800186cb  mov     rax, [rax+10h]
0x1800186cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186d4  nop
0x1800186d5  mov     rbx, [rbp+var_30]
0x1800186d9  jmp     short loc_180018689
0x1800186db  mov     rcx, rbx; this
0x1800186de  test    r13b, r13b
0x1800186e1  jz      short loc_180018734
0x1800186e3  call    ?Restart@MkvMfStream@MkvMfSourceLib@@QEAAJXZ; MkvMfSourceLib::MkvMfStream::Restart(void)
0x1800186e8  mov     [rbp+var_40], eax
0x1800186eb  test    eax, eax
0x1800186ed  jns     short loc_180018748
0x1800186ef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800186f6  test    rcx, rcx
0x1800186f9  jnz     short loc_180018777
0x1800186fb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180018702  nop     dword ptr [rax+rax+00h]
0x180018707  mov     rcx, rax
0x18001870a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180018711  test    rax, rax
0x180018714  jz      short loc_180018769
0x180018716  mov     rax, [rax]
0x180018719  mov     edx, 7F0h
0x18001871e  mov     rax, [rax+8]
0x180018722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018727  test    eax, eax
0x180018729  jz      short loc_180018769
0x18001872b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018732  jmp     short loc_180018777
0x180018734  lea     rdx, [rsi+20h]; struct tagPROPVARIANT *
  ... truncated ...
```
