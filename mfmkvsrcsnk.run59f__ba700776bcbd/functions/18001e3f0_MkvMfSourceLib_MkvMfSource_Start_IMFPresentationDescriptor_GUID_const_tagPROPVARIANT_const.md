# MkvMfSourceLib::MkvMfSource::Start(IMFPresentationDescriptor *,_GUID const *,tagPROPVARIANT const *)

- ea: `0x18001e3f0`
- end: `0x18001ed77`
- name: `?Start@MkvMfSource@MkvMfSourceLib@@UEAAJPEAUIMFPresentationDescriptor@@PEBU_GUID@@PEBUtagPROPVARIANT@@@Z`
- size: `2439`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource *__hidden this, struct IMFPresentationDescriptor *, const struct _GUID *, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18001ed80`

## callees

- `0x180002400`
- `0x180005c68`
- `0x180009b04`
- `0x180009bec`
- `0x18000c9a0`
- `0x18000d554`
- `0x18000d6a4`
- `0x18000ddc0`
- `0x18000de00`
- `0x18001b8b0`
- `0x18001d5b8`
- `0x18001e3f0`
- `0x180021abc`
- `0x180021b9c`
- `0x1800744d8`
- `0x18008fd7c`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e741`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e741`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e81c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e8fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ec4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ec70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e81c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e8fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ec4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ec70`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001ec04`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001ec04`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001e4df`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001e5d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001e6a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001e76f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001e84f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001ec9d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001e4df`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001e5d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001e6a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001e76f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001e84f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001ec9d`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall MkvMfSourceLib::MkvMfSource::Start(
        struct IMFAsyncCallback *this,
        struct IMFPresentationDescriptor *a2,
        const struct _GUID *a3,
        const struct tagPROPVARIANT *a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 *v11; // rcx
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v13; // ebx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  unsigned int v16; // edi
  __int64 v17; // rax
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  struct IMFAsyncCallback *v33; // rdi
  __int64 v34; // r8
  __int64 v35; // r8
  MkvMfSourceLib::MkvMfSource::Command *v36; // rdi
  const char *v37; // r9
  LARGE_INTEGER v38; // r12
  unsigned int v39; // r14d
  HRESULT (__stdcall *GetStreamDescriptorByIndex)(IMFPresentationDescriptor *, DWORD, BOOL *, IMFStreamDescriptor **); // rdi
  BSTR *pbstrVal; // rdi
  __int64 QuadPart; // r14
  struct Cluster **v43; // rcx
  mkvparser::Block *v44; // rax
  struct Cluster *v45; // rdx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  unsigned int v48; // ebx
  int v49; // [rsp+30h] [rbp-F8h] BYREF
  _BYTE v50[4]; // [rsp+34h] [rbp-F4h] BYREF
  unsigned int v51; // [rsp+38h] [rbp-F0h]
  struct IMFPresentationDescriptor *v52; // [rsp+40h] [rbp-E8h] BYREF
  unsigned int v53; // [rsp+48h] [rbp-E0h] BYREF
  int v54; // [rsp+4Ch] [rbp-DCh] BYREF
  int v55; // [rsp+50h] [rbp-D8h] BYREF
  struct Cluster *v56; // [rsp+58h] [rbp-D0h] BYREF
  LARGE_INTEGER *v57; // [rsp+60h] [rbp-C8h] BYREF
  BSTR *v58; // [rsp+68h] [rbp-C0h] BYREF
  MkvMfSourceLib::MkvMfSource::Command *v59; // [rsp+70h] [rbp-B8h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+78h] [rbp-B0h]
  struct IMFAsyncCallback *v61; // [rsp+80h] [rbp-A8h]
  int *v62; // [rsp+88h] [rbp-A0h]
  _BYTE v63[56]; // [rsp+90h] [rbp-98h] BYREF
  PROPVARIANT pvarDest; // [rsp+C8h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v49 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v50, "MkvMfSourceLib::MkvMfSource::Start", 664);
  v11 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && this[86].lpVtbl )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v13 = (*((__int64 (__fastcall **)(struct IMFAsyncCallbackVtbl *))this[86].lpVtbl->QueryInterface + 37))(this[86].lpVtbl);
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*((__int64 (__fastcall **)(struct IMFAsyncCallbackVtbl *, PROPVARIANT *))this[86].lpVtbl->QueryInterface
                                                           + 35))(
                                                            this[86].lpVtbl,
                                                            &pvarDest);
    *((_DWORD *)ThreadRelativeContext + 504) = v13;
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
  }
  v61 = this;
  v62 = &v49;
  if ( !BYTE1(this[57].lpVtbl) )
  {
    v49 = -1072875850;
    if ( !v11 )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9, v10);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( v49 < 0 && *((_DWORD *)v15 + 499) != v49 )
        CallStackContext::TraceFailure(v15, "MkvMfSourceLib::MkvMfSource::Start", 668, v49);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v49);
    v16 = v49;
    goto LABEL_75;
  }
  if ( a2 && a4 )
  {
    if ( a3 )
    {
      v17 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1 )
        v17 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
      if ( v17 )
      {
        v49 = -1072875835;
        if ( !v11 )
        {
          v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9, v10);
          CallStackTracing::s_wpInstance = v18;
          if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
          {
            v11 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v11 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v11 + 8) )
        {
          v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
          if ( v49 < 0 && *((_DWORD *)v19 + 499) != v49 )
            CallStackContext::TraceFailure(v19, "MkvMfSourceLib::MkvMfSource::Start", 678, v49);
        }
        if ( !g_wppLevels )
          goto LABEL_35;
        v20 = 80;
LABEL_34:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v49);
LABEL_35:
        v16 = v49;
LABEL_75:
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v50);
        return v16;
      }
    }
    if ( a4->vt && a4->vt != 20 )
    {
      v49 = -1072875835;
      if ( !v11 )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9, v10);
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v11 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( v49 < 0 && *((_DWORD *)v22 + 499) != v49 )
          CallStackContext::TraceFailure(v22, "MkvMfSourceLib::MkvMfSource::Start", 688, v49);
      }
      if ( !g_wppLevels )
        goto LABEL_35;
      v20 = 81;
      goto LABEL_34;
    }
    lpCriticalSection = (LPCRITICAL_SECTION)&this[13];
    EnterCriticalSection((LPCRITICAL_SECTION)&this[13]);
    if ( !this[18].lpVtbl )
    {
      v49 = -1072873851;
      v26 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24, v25);
        CallStackTracing::s_wpInstance = v27;
        if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
        {
          v26 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v26 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v26 + 8) )
      {
        v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
        if ( v49 < 0 && *((_DWORD *)v28 + 499) != v49 )
          CallStackContext::TraceFailure(v28, "MkvMfSourceLib::MkvMfSource::Start", 695, v49);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v49);
LABEL_74:
      v16 = v49;
      LeaveCriticalSection((LPCRITICAL_SECTION)&this[13]);
      goto LABEL_75;
    }
    if ( !this[84].lpVtbl )
    {
      v49 = -1072875845;
      v29 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24, v25);
        CallStackTracing::s_wpInstance = v30;
        if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
        {
          v29 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v29 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v29 + 8) )
      {
        v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
        if ( v49 < 0 && *((_DWORD *)v31 + 499) != v49 )
          CallStackContext::TraceFailure(v31, "MkvMfSourceLib::MkvMfSource::Start", 700, v49);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v49);
      goto LABEL_74;
    }
    try
    {
      v33 = this + 83;
      if ( *((_DWORD *)this[83].lpVtbl->AddRef + 4) == 4 )
      {
        v34 = MkvMfSourceLib::MkvMfSource::Command::Command(v63, 0, this);
        std::list<MkvMfSourceLib::MkvMfSource::Command>::_Emplace<MkvMfSourceLib::MkvMfSource::Command>(
          &this[83],
          v33->lpVtbl,
          v34);
      }
      else
      {
        if ( a4->vt == 20 )
          v35 = MkvMfSourceLib::MkvMfSource::Command::Command(v63, 1, this);
        else
          v35 = MkvMfSourceLib::MkvMfSource::Command::Command(v63, 2, this);
        std::list<MkvMfSourceLib::MkvMfSource::Command>::_Emplace<MkvMfSourceLib::MkvMfSource::Command>(
          &this[83],
          v33->lpVtbl,
          v35);
      }
      MkvMfSourceLib::MkvMfSource::Command::~Command((MkvMfSourceLib::MkvMfSource::Command *)v63);
      v36 = (MkvMfSourceLib::MkvMfSource::Command *)((char *)v33->lpVtbl->AddRef + 16);
      v59 = v36;
      if ( a2 != *((struct IMFPresentationDescriptor **)v36 + 3) )
      {
        v52 = a2;
        Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(&v52);
        v52 = (struct IMFPresentationDescriptor *)*((_QWORD *)v36 + 3);
        *((_QWORD *)v36 + 3) = a2;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
      }
      MkvMfSourceLib::MkvMfSource::Command::SetTime(v36, a4);
    }
    catch ( ... )
    {
      v51 = wil::details::in1diag3::Return_CaughtException(
              retaddr,
              (void *)0x2CE,
              (unsigned int)"avcore\\mf\\core\\mediasource\\mkv\\lib\\mkvmfsource.cpp",
              v37);
      LeaveCriticalSection(lpCriticalSection);
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v50);
      return v51;
    }
    if ( a4->vt == 20 )
    {
      v38.QuadPart = 0x7FFFFFFFFFFFFFFFLL;
      v53 = 0;
      ((void (__fastcall *)(struct IMFPresentationDescriptor *, unsigned int *))a2->lpVtbl->GetStreamDescriptorCount)(
        a2,
        &v53);
      v39 = 0;
      v51 = 0;
      if ( v53 )
      {
        do
        {
          v54 = 0;
          v52 = 0;
          GetStreamDescriptorByIndex = a2->lpVtbl->GetStreamDescriptorByIndex;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
          if ( ((int (__fastcall *)(struct IMFPresentationDescriptor *, _QWORD, int *, struct IMFPresentationDescriptor **))GetStreamDescriptorByIndex)(
                 a2,
                 v39,
                 &v54,
                 &v52) >= 0 )
          {
            if ( v54 )
            {
              v55 = 0;
              if ( ((int (__fastcall *)(struct IMFPresentationDescriptor *, int *))v52->lpVtbl->GetStreamDescriptorCount)(
                     v52,
                     &v55) >= 0 )
              {
                std::_Tree<std::_Tmap_traits<unsigned long,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>,0>>::find(
                  &this[72],
                  &v57,
                  &v55);
                if ( v57 != (LARGE_INTEGER *)this[72].lpVtbl )
                {
                  *(_DWORD *)&pvarDest.vt = v57[4].LowPart;
                  pvarDest.hVal = v57[5];
                  pbstrVal = pvarDest.pbstrVal;
                  Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(&pvarDest.decVal.Lo32);
                  v58 = pbstrVal;
                  Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(&v58);
                  QuadPart = 0;
                  v43 = (struct Cluster **)pbstrVal[29];
                  if ( v43 )
                  {
                    v56 = v43[1];
                    v44 = (mkvparser::Block *)(*((__int64 (__fastcall **)(struct Cluster **))*v43 + 1))(v43);
                    v45 = v56;
                    if ( v56 )
                    {
                      if ( v44 )
                      {
                        v56 = 0;
                        mkvparser::Block::GetTime(v44, v45, (__int64 *)&v56);
                        QuadPart = (__int64)v56 / 100;
                      }
                    }
                  }
                  if ( QuadPart >= v38.QuadPart )
                    QuadPart = v38.QuadPart;
                  v38.QuadPart = QuadPart;
                  if ( pbstrVal )
                  {
                    (*((void (__fastcall **)(BSTR *))*pbstrVal + 2))(pbstrVal);
                    pvarDest.hVal.QuadPart = 0;
                    (*((void (__fastcall **)(BSTR *))*pbstrVal + 2))(pbstrVal);
                  }
                  v39 = v51;
                }
              }
            }
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
          v51 = ++v39;
        }
        while ( v39 < v53 );
        if ( v38.QuadPart != 0x7FFFFFFFFFFFFFFFLL && a4->hVal.QuadPart < v38.QuadPart )
        {
          memset(&pvarDest, 0, sizeof(pvarDest));
          PropVariantCopy(&pvarDest, a4);
          pvarDest.hVal = v38;
          MkvMfSourceLib::MkvMfSource::Command::SetTime(v59, &pvarDest);
        }
      }
    }
    if ( !BYTE5(this[60].lpVtbl) )
    {
      BYTE5(this[60].lpVtbl) = 1;
      MkvMfSourceLib::MkvMfSource::QueueOperation((MkvMfSourceLib::MkvMfSource *)this, this + 63);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)&this[13]);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v50);
    return 0;
  }
  else
  {
    v49 = -2147467261;
    if ( !v11 )
    {
      v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9, v10);
      CallStackTracing::s_wpInstance = v46;
      if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( v49 < 0 && *((_DWORD *)v47 + 499) != v49 )
        CallStackContext::TraceFailure(v47, "MkvMfSourceLib::MkvMfSource::Start", 673, v49);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v49);
    v48 = v49;
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v50);
    return v48;
  }
}

```

## disassembly

```asm
0x18001e3f0  push    rbx
0x18001e3f2  push    rsi
0x18001e3f3  push    rdi
0x18001e3f4  push    r12
0x18001e3f6  push    r13
0x18001e3f8  push    r14
0x18001e3fa  push    r15
0x18001e3fc  sub     rsp, 0F0h
0x18001e403  mov     rax, cs:__security_cookie
0x18001e40a  xor     rax, rsp
0x18001e40d  mov     [rsp+128h+var_48], rax
0x18001e415  mov     r15, r9
0x18001e418  mov     r14, r8
0x18001e41b  mov     r13, rdx
0x18001e41e  mov     rsi, rcx
0x18001e421  xor     edi, edi
0x18001e423  mov     [rsp+128h+var_F8], edi
0x18001e427  mov     r8d, 298h; int
0x18001e42d  lea     r12, aMkvmfsourcelib_128; "MkvMfSourceLib::MkvMfSource::Start"
0x18001e434  mov     rdx, r12; char *
0x18001e437  lea     rcx, [rsp+128h+var_F4]; this
0x18001e43c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001e441  nop
0x18001e442  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001e449  cmp     [rcx+8], dil
0x18001e44d  jz      short loc_18001E4B0
0x18001e44f  cmp     [rsi+2B0h], rdi
0x18001e456  jz      short loc_18001E4B0
0x18001e458  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001e45d  mov     rdi, rax
0x18001e460  mov     rcx, [rsi+2B0h]
0x18001e467  mov     rdx, [rcx]
0x18001e46a  mov     rax, [rdx+128h]
0x18001e471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e476  mov     ebx, eax
0x18001e478  mov     rcx, [rsi+2B0h]
0x18001e47f  mov     rdx, [rcx]
0x18001e482  mov     rax, [rdx+118h]
0x18001e489  lea     rdx, [rsp+128h+pvarDest]
0x18001e491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e496  movups  xmm0, xmmword ptr [rax]
0x18001e499  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18001e4a1  mov     [rdi+7E0h], ebx
0x18001e4a7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e4ae  xor     edi, edi
0x18001e4b0  mov     [rsp+128h+var_A8], rsi
0x18001e4b8  lea     rax, [rsp+128h+var_F8]
0x18001e4bd  mov     [rsp+128h+var_A0], rax
0x18001e4c5  cmp     [rsi+1C9h], dil
0x18001e4cc  jnz     loc_18001E58E
0x18001e4d2  mov     [rsp+128h+var_F8], 0C00D36B6h
0x18001e4da  test    rcx, rcx
0x18001e4dd  jnz     short loc_18001E526
0x18001e4df  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001e4e6  nop     dword ptr [rax+rax+00h]
0x18001e4eb  mov     rcx, rax
0x18001e4ee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e4f5  test    rax, rax
0x18001e4f8  jz      short loc_18001E518
0x18001e4fa  mov     rax, [rax]
0x18001e4fd  mov     edx, 7F0h
0x18001e502  mov     rax, [rax+8]
0x18001e506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e50b  test    eax, eax
0x18001e50d  jz      short loc_18001E518
0x18001e50f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e516  jmp     short loc_18001E526
0x18001e518  lea     rcx, qword_1800DBF70; this
0x18001e51f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e526  cmp     [rcx+8], dil
0x18001e52a  jz      short loc_18001E555
0x18001e52c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001e531  mov     r9d, [rsp+128h+var_F8]; int
0x18001e536  test    r9d, r9d
0x18001e539  jns     short loc_18001E555
0x18001e53b  cmp     [rax+7CCh], r9d
0x18001e542  jz      short loc_18001E555
0x18001e544  mov     r8d, 29Ch; int
0x18001e54a  mov     rdx, r12; char *
0x18001e54d  mov     rcx, rax; this
0x18001e550  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001e555  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001e55c  jb      short loc_18001E585
0x18001e55e  mov     edx, 4Eh ; 'N'
0x18001e563  mov     eax, [rsp+128h+var_F8]
0x18001e567  mov     [rsp+128h+var_108], eax
0x18001e56b  mov     r9, rsi
0x18001e56e  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x18001e575  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e57c  mov     rcx, [rcx+10h]
0x18001e580  call    WPP_SF_qD
0x18001e585  mov     edi, [rsp+128h+var_F8]
0x18001e589  jmp     loc_18001E829
0x18001e58e  test    r13, r13
0x18001e591  jz      loc_18001EC90
0x18001e597  test    r15, r15
0x18001e59a  jz      loc_18001EC90
0x18001e5a0  test    r14, r14
0x18001e5a3  jz      loc_18001E686
0x18001e5a9  mov     rax, [r14]
0x18001e5ac  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18001e5b3  jnz     short loc_18001E5C0
0x18001e5b5  mov     rax, [r14+8]
0x18001e5b9  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x18001e5c0  test    rax, rax
0x18001e5c3  jz      loc_18001E686
0x18001e5c9  mov     [rsp+128h+var_F8], 0C00D36C5h
0x18001e5d1  test    rcx, rcx
0x18001e5d4  jnz     short loc_18001E61D
0x18001e5d6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001e5dd  nop     dword ptr [rax+rax+00h]
0x18001e5e2  mov     rcx, rax
0x18001e5e5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e5ec  test    rax, rax
0x18001e5ef  jz      short loc_18001E60F
0x18001e5f1  mov     rax, [rax]
0x18001e5f4  mov     edx, 7F0h
0x18001e5f9  mov     rax, [rax+8]
0x18001e5fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e602  test    eax, eax
0x18001e604  jz      short loc_18001E60F
0x18001e606  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e60d  jmp     short loc_18001E61D
0x18001e60f  lea     rcx, qword_1800DBF70; this
0x18001e616  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e61d  cmp     [rcx+8], dil
0x18001e621  jz      short loc_18001E64C
0x18001e623  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001e628  mov     r9d, [rsp+128h+var_F8]; int
0x18001e62d  test    r9d, r9d
0x18001e630  jns     short loc_18001E64C
0x18001e632  cmp     [rax+7CCh], r9d
0x18001e639  jz      short loc_18001E64C
0x18001e63b  mov     r8d, 2A6h; int
0x18001e641  mov     rdx, r12; char *
0x18001e644  mov     rcx, rax; this
0x18001e647  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001e64c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001e653  jb      short loc_18001E67D
0x18001e655  mov     edx, 50h ; 'P'
0x18001e65a  mov     eax, [rsp+128h+var_F8]
0x18001e65e  mov     [rsp+128h+var_108], eax
0x18001e662  mov     r9, rsi
0x18001e665  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x18001e66c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e673  mov     rcx, [rcx+10h]
0x18001e677  call    WPP_SF_qD
0x18001e67c  nop
0x18001e67d  mov     edi, [rsp+128h+var_F8]
0x18001e681  jmp     loc_18001E909
0x18001e686  cmp     [r15], di
0x18001e68a  jz      loc_18001E735
0x18001e690  cmp     word ptr [r15], 14h
0x18001e695  jz      loc_18001E735
0x18001e69b  mov     [rsp+128h+var_F8], 0C00D36C5h
0x18001e6a3  test    rcx, rcx
0x18001e6a6  jnz     short loc_18001E6EF
0x18001e6a8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001e6af  nop     dword ptr [rax+rax+00h]
0x18001e6b4  mov     rcx, rax
0x18001e6b7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e6be  test    rax, rax
0x18001e6c1  jz      short loc_18001E6E1
0x18001e6c3  mov     rax, [rax]
0x18001e6c6  mov     edx, 7F0h
0x18001e6cb  mov     rax, [rax+8]
0x18001e6cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6d4  test    eax, eax
0x18001e6d6  jz      short loc_18001E6E1
0x18001e6d8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e6df  jmp     short loc_18001E6EF
0x18001e6e1  lea     rcx, qword_1800DBF70; this
0x18001e6e8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e6ef  cmp     [rcx+8], dil
0x18001e6f3  jz      short loc_18001E71E
0x18001e6f5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001e6fa  mov     r9d, [rsp+128h+var_F8]; int
0x18001e6ff  test    r9d, r9d
0x18001e702  jns     short loc_18001E71E
0x18001e704  cmp     [rax+7CCh], r9d
0x18001e70b  jz      short loc_18001E71E
0x18001e70d  mov     r8d, 2B0h; int
0x18001e713  mov     rdx, r12; char *
0x18001e716  mov     rcx, rax; this
0x18001e719  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001e71e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001e725  jb      loc_18001E67D
0x18001e72b  mov     edx, 51h ; 'Q'
0x18001e730  jmp     loc_18001E65A
0x18001e735  lea     rbx, [rsi+68h]
0x18001e739  mov     [rsp+128h+lpCriticalSection], rbx
0x18001e73e  mov     rcx, rbx; lpCriticalSection
0x18001e741  call    cs:__imp_EnterCriticalSection
0x18001e748  nop     dword ptr [rax+rax+00h]
0x18001e74d  nop
0x18001e74e  cmp     [rsi+90h], rdi
0x18001e755  jnz     loc_18001E82E
0x18001e75b  mov     [rsp+128h+var_F8], 0C00D3E85h
0x18001e763  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e76a  test    rcx, rcx
0x18001e76d  jnz     short loc_18001E7B6
0x18001e76f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001e776  nop     dword ptr [rax+rax+00h]
0x18001e77b  mov     rcx, rax
0x18001e77e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e785  test    rax, rax
0x18001e788  jz      short loc_18001E7A8
0x18001e78a  mov     rax, [rax]
0x18001e78d  mov     edx, 7F0h
0x18001e792  mov     rax, [rax+8]
0x18001e796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e79b  test    eax, eax
0x18001e79d  jz      short loc_18001E7A8
0x18001e79f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e7a6  jmp     short loc_18001E7B6
0x18001e7a8  lea     rcx, qword_1800DBF70; this
0x18001e7af  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e7b6  cmp     [rcx+8], dil
0x18001e7ba  jz      short loc_18001E7E5
0x18001e7bc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001e7c1  mov     r9d, [rsp+128h+var_F8]; int
0x18001e7c6  test    r9d, r9d
0x18001e7c9  jns     short loc_18001E7E5
0x18001e7cb  cmp     [rax+7CCh], r9d
0x18001e7d2  jz      short loc_18001E7E5
0x18001e7d4  mov     r8d, 2B7h; int
0x18001e7da  mov     rdx, r12; char *
0x18001e7dd  mov     rcx, rax; this
0x18001e7e0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001e7e5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001e7ec  jb      short loc_18001E815
0x18001e7ee  mov     edx, 52h ; 'R'
0x18001e7f3  mov     eax, [rsp+128h+var_F8]
0x18001e7f7  mov     [rsp+128h+var_108], eax
0x18001e7fb  mov     r9, rsi
0x18001e7fe  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x18001e805  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e80c  mov     rcx, [rcx+10h]
0x18001e810  call    WPP_SF_qD
0x18001e815  mov     edi, [rsp+128h+var_F8]
0x18001e819  mov     rcx, rbx; lpCriticalSection
0x18001e81c  call    cs:__imp_LeaveCriticalSection
0x18001e823  nop     dword ptr [rax+rax+00h]
0x18001e828  nop
0x18001e829  jmp     loc_18001E909
0x18001e82e  cmp     [rsi+2A0h], rdi
0x18001e835  jnz     loc_18001E91A
0x18001e83b  mov     [rsp+128h+var_F8], 0C00D36BBh
0x18001e843  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e84a  test    rcx, rcx
0x18001e84d  jnz     short loc_18001E896
0x18001e84f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001e856  nop     dword ptr [rax+rax+00h]
0x18001e85b  mov     rcx, rax
0x18001e85e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e865  test    rax, rax
0x18001e868  jz      short loc_18001E888
0x18001e86a  mov     rax, [rax]
0x18001e86d  mov     edx, 7F0h
0x18001e872  mov     rax, [rax+8]
0x18001e876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e87b  test    eax, eax
0x18001e87d  jz      short loc_18001E888
0x18001e87f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e886  jmp     short loc_18001E896
0x18001e888  lea     rcx, qword_1800DBF70; this
0x18001e88f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e896  cmp     [rcx+8], dil
0x18001e89a  jz      short loc_18001E8C5
0x18001e89c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001e8a1  mov     r9d, [rsp+128h+var_F8]; int
0x18001e8a6  test    r9d, r9d
0x18001e8a9  jns     short loc_18001E8C5
0x18001e8ab  cmp     [rax+7CCh], r9d
0x18001e8b2  jz      short loc_18001E8C5
0x18001e8b4  mov     r8d, 2BCh; int
0x18001e8ba  mov     rdx, r12; char *
0x18001e8bd  mov     rcx, rax; this
0x18001e8c0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001e8c5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001e8cc  jb      short loc_18001E8F5
0x18001e8ce  mov     edx, 53h ; 'S'
0x18001e8d3  mov     eax, [rsp+128h+var_F8]
0x18001e8d7  mov     [rsp+128h+var_108], eax
0x18001e8db  mov     r9, rsi
0x18001e8de  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x18001e8e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e8ec  mov     rcx, [rcx+10h]
0x18001e8f0  call    WPP_SF_qD
0x18001e8f5  mov     edi, [rsp+128h+var_F8]
0x18001e8f9  mov     rcx, rbx; lpCriticalSection
0x18001e8fc  call    cs:__imp_LeaveCriticalSection
0x18001e903  nop     dword ptr [rax+rax+00h]
0x18001e908  nop
0x18001e909  lea     rcx, [rsp+128h+var_F4]; this
0x18001e90e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001e913  mov     eax, edi
0x18001e915  jmp     loc_18001ED53
0x18001e91a  lea     rdi, [rsi+298h]
0x18001e921  mov     rax, [rdi]
  ... truncated ...
```
