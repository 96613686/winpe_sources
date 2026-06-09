# MkvMfSourceLib::MkvMfSource::Start(IMFPresentationDescriptor *,_GUID const *,tagPROPVARIANT const *)

- ea: `0x18001d620`
- end: `0x18001df65`
- name: `?Start@MkvMfSource@MkvMfSourceLib@@UEAAJPEAUIMFPresentationDescriptor@@PEBU_GUID@@PEBUtagPROPVARIANT@@@Z`
- size: `2373`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource *__hidden this, struct IMFPresentationDescriptor *, const struct _GUID *, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18001df70`

## callees

- `0x1800023e0`
- `0x180005ab8`
- `0x1800097f0`
- `0x1800098b8`
- `0x18000cfb4`
- `0x18000d0f8`
- `0x18000d7cc`
- `0x18000d80c`
- `0x18001ac70`
- `0x18001c874`
- `0x18001d620`
- `0x180020c18`
- `0x180020c3c`
- `0x180020d84`
- `0x180071330`
- `0x18008bef4`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d968`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d968`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001da37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001db13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001de4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001de6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001da37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001db13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001de4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001de6b`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001de08`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001de08`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001d716`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001d807`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001d8d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001d990`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001da68`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001de92`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001d716`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001d807`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001d8d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001d990`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001da68`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001de92`

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
  struct IMFAsyncCallback *v29; // rdi
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 v34; // rdx
  __int64 v35; // rdx
  MkvMfSourceLib::MkvMfSource::Command *v36; // rdi
  const char *v37; // r9
  LARGE_INTEGER v38; // r15
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
        v11 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v11 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v11 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v26 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
    v29 = this + 83;
    if ( !this[84].lpVtbl )
    {
      v49 = -1072875845;
      v30 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24, v25);
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
        if ( v49 < 0 && *((_DWORD *)v32 + 499) != v49 )
          CallStackContext::TraceFailure(v32, "MkvMfSourceLib::MkvMfSource::Start", 700, v49);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v49);
      goto LABEL_74;
    }
    try
    {
      if ( *((_DWORD *)v29->lpVtbl->AddRef + 4) == 4 )
      {
        v34 = MkvMfSourceLib::MkvMfSource::Command::Command(v63, 0, this);
        std::list<MkvMfSourceLib::MkvMfSource::Command>::push_back(&this[83], v34);
      }
      else
      {
        if ( a4->vt == 20 )
          v35 = MkvMfSourceLib::MkvMfSource::Command::Command(v63, 1, this);
        else
          v35 = MkvMfSourceLib::MkvMfSource::Command::Command(v63, 2, this);
        std::list<MkvMfSourceLib::MkvMfSource::Command>::push_back(&this[83], v35);
      }
      MkvMfSourceLib::MkvMfSource::Command::~Command((MkvMfSourceLib::MkvMfSource::Command *)v63);
      v36 = (MkvMfSourceLib::MkvMfSource::Command *)((char *)v29->lpVtbl->AddRef + 16);
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
        v11 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x18001d620  push    rbx
0x18001d622  push    rsi
0x18001d623  push    rdi
0x18001d624  push    r12
0x18001d626  push    r13
0x18001d628  push    r14
0x18001d62a  push    r15
0x18001d62c  sub     rsp, 0F0h
0x18001d633  mov     rax, cs:__security_cookie
0x18001d63a  xor     rax, rsp
0x18001d63d  mov     [rsp+128h+var_48], rax
0x18001d645  mov     r12, r9
0x18001d648  mov     r14, r8
0x18001d64b  mov     r13, rdx
0x18001d64e  mov     rsi, rcx
0x18001d651  xor     r15d, r15d
0x18001d654  mov     [rsp+128h+var_F8], r15d
0x18001d659  mov     r8d, 298h; int
0x18001d65f  lea     rdi, aMkvmfsourcelib_128; "MkvMfSourceLib::MkvMfSource::Start"
0x18001d666  mov     rdx, rdi; char *
0x18001d669  lea     rcx, [rsp+128h+var_F4]; this
0x18001d66e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001d673  nop
0x18001d674  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001d67b  cmp     [rcx+8], r15b
0x18001d67f  jz      short loc_18001D6E7
0x18001d681  cmp     [rsi+2B0h], r15
0x18001d688  jz      short loc_18001D6E7
0x18001d68a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001d68f  mov     rdi, rax
0x18001d692  mov     rcx, [rsi+2B0h]
0x18001d699  mov     rdx, [rcx]
0x18001d69c  mov     rax, [rdx+128h]
0x18001d6a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6a8  mov     ebx, eax
0x18001d6aa  mov     rcx, [rsi+2B0h]
0x18001d6b1  mov     rdx, [rcx]
0x18001d6b4  mov     rax, [rdx+118h]
0x18001d6bb  lea     rdx, [rsp+128h+pvarDest]
0x18001d6c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6c8  movups  xmm0, xmmword ptr [rax]
0x18001d6cb  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18001d6d3  mov     [rdi+7E0h], ebx
0x18001d6d9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d6e0  lea     rdi, aMkvmfsourcelib_128; "MkvMfSourceLib::MkvMfSource::Start"
0x18001d6e7  mov     [rsp+128h+var_A8], rsi
0x18001d6ef  lea     rax, [rsp+128h+var_F8]
0x18001d6f4  mov     [rsp+128h+var_A0], rax
0x18001d6fc  cmp     [rsi+1C9h], r15b
0x18001d703  jnz     loc_18001D7BF
0x18001d709  mov     [rsp+128h+var_F8], 0C00D36B6h
0x18001d711  test    rcx, rcx
0x18001d714  jnz     short loc_18001D757
0x18001d716  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001d71c  mov     rcx, rax
0x18001d71f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d726  test    rax, rax
0x18001d729  jz      short loc_18001D749
0x18001d72b  mov     rax, [rax]
0x18001d72e  mov     edx, 7F0h
0x18001d733  mov     rax, [rax+8]
0x18001d737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d73c  test    eax, eax
0x18001d73e  jz      short loc_18001D749
0x18001d740  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d747  jmp     short loc_18001D757
0x18001d749  lea     rcx, qword_1800D6F70; this
0x18001d750  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d757  cmp     [rcx+8], r15b
0x18001d75b  jz      short loc_18001D786
0x18001d75d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001d762  mov     r9d, [rsp+128h+var_F8]; int
0x18001d767  test    r9d, r9d
0x18001d76a  jns     short loc_18001D786
0x18001d76c  cmp     [rax+7CCh], r9d
0x18001d773  jz      short loc_18001D786
0x18001d775  mov     r8d, 29Ch; int
0x18001d77b  mov     rdx, rdi; char *
0x18001d77e  mov     rcx, rax; this
0x18001d781  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001d786  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001d78d  jb      short loc_18001D7B6
0x18001d78f  mov     edx, 4Eh ; 'N'
0x18001d794  mov     eax, [rsp+128h+var_F8]
0x18001d798  mov     [rsp+128h+var_108], eax
0x18001d79c  mov     r9, rsi
0x18001d79f  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x18001d7a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d7ad  mov     rcx, [rcx+10h]
0x18001d7b1  call    WPP_SF_qD
0x18001d7b6  mov     edi, [rsp+128h+var_F8]
0x18001d7ba  jmp     loc_18001DA3E
0x18001d7bf  test    r13, r13
0x18001d7c2  jz      loc_18001DE85
0x18001d7c8  test    r12, r12
0x18001d7cb  jz      loc_18001DE85
0x18001d7d1  test    r14, r14
0x18001d7d4  jz      loc_18001D8B1
0x18001d7da  mov     rax, [r14]
0x18001d7dd  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18001d7e4  jnz     short loc_18001D7F1
0x18001d7e6  mov     rax, [r14+8]
0x18001d7ea  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x18001d7f1  test    rax, rax
0x18001d7f4  jz      loc_18001D8B1
0x18001d7fa  mov     [rsp+128h+var_F8], 0C00D36C5h
0x18001d802  test    rcx, rcx
0x18001d805  jnz     short loc_18001D848
0x18001d807  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001d80d  mov     rcx, rax
0x18001d810  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d817  test    rax, rax
0x18001d81a  jz      short loc_18001D83A
0x18001d81c  mov     rax, [rax]
0x18001d81f  mov     edx, 7F0h
0x18001d824  mov     rax, [rax+8]
0x18001d828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d82d  test    eax, eax
0x18001d82f  jz      short loc_18001D83A
0x18001d831  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d838  jmp     short loc_18001D848
0x18001d83a  lea     rcx, qword_1800D6F70; this
0x18001d841  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d848  cmp     [rcx+8], r15b
0x18001d84c  jz      short loc_18001D877
0x18001d84e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001d853  mov     r9d, [rsp+128h+var_F8]; int
0x18001d858  test    r9d, r9d
0x18001d85b  jns     short loc_18001D877
0x18001d85d  cmp     [rax+7CCh], r9d
0x18001d864  jz      short loc_18001D877
0x18001d866  mov     r8d, 2A6h; int
0x18001d86c  mov     rdx, rdi; char *
0x18001d86f  mov     rcx, rax; this
0x18001d872  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001d877  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001d87e  jb      short loc_18001D8A8
0x18001d880  mov     edx, 50h ; 'P'
0x18001d885  mov     eax, [rsp+128h+var_F8]
0x18001d889  mov     [rsp+128h+var_108], eax
0x18001d88d  mov     r9, rsi
0x18001d890  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x18001d897  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d89e  mov     rcx, [rcx+10h]
0x18001d8a2  call    WPP_SF_qD
0x18001d8a7  nop
0x18001d8a8  mov     edi, [rsp+128h+var_F8]
0x18001d8ac  jmp     loc_18001DB1A
0x18001d8b1  cmp     [r12], r15w
0x18001d8b6  jz      loc_18001D95C
0x18001d8bc  cmp     word ptr [r12], 14h
0x18001d8c2  jz      loc_18001D95C
0x18001d8c8  mov     [rsp+128h+var_F8], 0C00D36C5h
0x18001d8d0  test    rcx, rcx
0x18001d8d3  jnz     short loc_18001D916
0x18001d8d5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001d8db  mov     rcx, rax
0x18001d8de  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d8e5  test    rax, rax
0x18001d8e8  jz      short loc_18001D908
0x18001d8ea  mov     rax, [rax]
0x18001d8ed  mov     edx, 7F0h
0x18001d8f2  mov     rax, [rax+8]
0x18001d8f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8fb  test    eax, eax
0x18001d8fd  jz      short loc_18001D908
0x18001d8ff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d906  jmp     short loc_18001D916
0x18001d908  lea     rcx, qword_1800D6F70; this
0x18001d90f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d916  cmp     [rcx+8], r15b
0x18001d91a  jz      short loc_18001D945
0x18001d91c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001d921  mov     r9d, [rsp+128h+var_F8]; int
0x18001d926  test    r9d, r9d
0x18001d929  jns     short loc_18001D945
0x18001d92b  cmp     [rax+7CCh], r9d
0x18001d932  jz      short loc_18001D945
0x18001d934  mov     r8d, 2B0h; int
0x18001d93a  mov     rdx, rdi; char *
0x18001d93d  mov     rcx, rax; this
0x18001d940  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001d945  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001d94c  jb      loc_18001D8A8
0x18001d952  mov     edx, 51h ; 'Q'
0x18001d957  jmp     loc_18001D885
0x18001d95c  lea     rbx, [rsi+68h]
0x18001d960  mov     [rsp+128h+lpCriticalSection], rbx
0x18001d965  mov     rcx, rbx; lpCriticalSection
0x18001d968  call    cs:__imp_EnterCriticalSection
0x18001d96e  nop
0x18001d96f  cmp     [rsi+90h], r15
0x18001d976  jnz     loc_18001DA43
0x18001d97c  mov     [rsp+128h+var_F8], 0C00D3E85h
0x18001d984  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d98b  test    rcx, rcx
0x18001d98e  jnz     short loc_18001D9D1
0x18001d990  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001d996  mov     rcx, rax
0x18001d999  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d9a0  test    rax, rax
0x18001d9a3  jz      short loc_18001D9C3
0x18001d9a5  mov     rax, [rax]
0x18001d9a8  mov     edx, 7F0h
0x18001d9ad  mov     rax, [rax+8]
0x18001d9b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9b6  test    eax, eax
0x18001d9b8  jz      short loc_18001D9C3
0x18001d9ba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d9c1  jmp     short loc_18001D9D1
0x18001d9c3  lea     rcx, qword_1800D6F70; this
0x18001d9ca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d9d1  cmp     [rcx+8], r15b
0x18001d9d5  jz      short loc_18001DA00
0x18001d9d7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001d9dc  mov     r9d, [rsp+128h+var_F8]; int
0x18001d9e1  test    r9d, r9d
0x18001d9e4  jns     short loc_18001DA00
0x18001d9e6  cmp     [rax+7CCh], r9d
0x18001d9ed  jz      short loc_18001DA00
0x18001d9ef  mov     r8d, 2B7h; int
0x18001d9f5  mov     rdx, rdi; char *
0x18001d9f8  mov     rcx, rax; this
0x18001d9fb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001da00  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001da07  jb      short loc_18001DA30
0x18001da09  mov     edx, 52h ; 'R'
0x18001da0e  mov     eax, [rsp+128h+var_F8]
0x18001da12  mov     [rsp+128h+var_108], eax
0x18001da16  mov     r9, rsi
0x18001da19  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x18001da20  mov     rcx, cs:WPP_GLOBAL_Control
0x18001da27  mov     rcx, [rcx+10h]
0x18001da2b  call    WPP_SF_qD
0x18001da30  mov     edi, [rsp+128h+var_F8]
0x18001da34  mov     rcx, rbx; lpCriticalSection
0x18001da37  call    cs:__imp_LeaveCriticalSection
0x18001da3d  nop
0x18001da3e  jmp     loc_18001DB1A
0x18001da43  lea     rdi, [rsi+298h]
0x18001da4a  cmp     [rdi+8], r15
0x18001da4e  jnz     loc_18001DB2B
0x18001da54  mov     [rsp+128h+var_F8], 0C00D36BBh
0x18001da5c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001da63  test    rcx, rcx
0x18001da66  jnz     short loc_18001DAA9
0x18001da68  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001da6e  mov     rcx, rax
0x18001da71  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001da78  test    rax, rax
0x18001da7b  jz      short loc_18001DA9B
0x18001da7d  mov     rax, [rax]
0x18001da80  mov     edx, 7F0h
0x18001da85  mov     rax, [rax+8]
0x18001da89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da8e  test    eax, eax
0x18001da90  jz      short loc_18001DA9B
0x18001da92  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001da99  jmp     short loc_18001DAA9
0x18001da9b  lea     rcx, qword_1800D6F70; this
0x18001daa2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001daa9  cmp     [rcx+8], r15b
0x18001daad  jz      short loc_18001DADC
0x18001daaf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001dab4  mov     r9d, [rsp+128h+var_F8]; int
0x18001dab9  test    r9d, r9d
0x18001dabc  jns     short loc_18001DADC
0x18001dabe  cmp     [rax+7CCh], r9d
0x18001dac5  jz      short loc_18001DADC
0x18001dac7  mov     r8d, 2BCh; int
0x18001dacd  lea     rdx, aMkvmfsourcelib_128; "MkvMfSourceLib::MkvMfSource::Start"
0x18001dad4  mov     rcx, rax; this
0x18001dad7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001dadc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001dae3  jb      short loc_18001DB0C
0x18001dae5  mov     edx, 53h ; 'S'
0x18001daea  mov     eax, [rsp+128h+var_F8]
0x18001daee  mov     [rsp+128h+var_108], eax
0x18001daf2  mov     r9, rsi
0x18001daf5  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x18001dafc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db03  mov     rcx, [rcx+10h]
0x18001db07  call    WPP_SF_qD
0x18001db0c  mov     edi, [rsp+128h+var_F8]
0x18001db10  mov     rcx, rbx; lpCriticalSection
0x18001db13  call    cs:__imp_LeaveCriticalSection
0x18001db19  nop
0x18001db1a  lea     rcx, [rsp+128h+var_F4]; this
0x18001db1f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001db24  mov     eax, edi
0x18001db26  jmp     loc_18001DF42
0x18001db2b  mov     rax, [rdi]
0x18001db2e  mov     rcx, [rax+8]
0x18001db32  mov     r8, rsi
0x18001db35  cmp     dword ptr [rcx+10h], 4
0x18001db39  lea     rcx, [rsp+128h+var_98]
0x18001db41  jnz     short loc_18001DB59
0x18001db43  xor     edx, edx
0x18001db45  call    ??0Command@MkvMfSource@MkvMfSourceLib@@QEAA@W4Kind@012@PEAV12@@Z; MkvMfSourceLib::MkvMfSource::Command::Command(MkvMfSourceLib::MkvMfSource::Command::Kind,MkvMfSourceLib::MkvMfSource *)
0x18001db4a  nop
  ... truncated ...
```
