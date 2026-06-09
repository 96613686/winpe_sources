# CMFContentDecryptionModuleAccessStoreWrapper::CreateContentDecryptionModule(IPropertyStore *,IMFContentDecryptionModule * *)

- ea: `0x18010e580`
- end: `0x18010ed59`
- name: `?CreateContentDecryptionModule@CMFContentDecryptionModuleAccessStoreWrapper@@UEAAJPEAUIPropertyStore@@PEAPEAUIMFContentDecryptionModule@@@Z`
- size: `2009`
- prototype: `__int64 __fastcall(CMFContentDecryptionModuleAccessStoreWrapper *__hidden this, struct IPropertyStore *, struct IMFContentDecryptionModule **)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180004870`
- `0x180014488`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x1800e4cb0`
- `0x18010e580`
- `0x18011fff0`
- `0x1801200d0`
- `0x180138340`
- `0x180154028`
- `0x180154aa0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18010ecf9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18010ecf9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010e790`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010e790`

## string_xrefs

- `0x18010e5d2`: `CMFContentDecryptionModuleAccessStoreWrapper::CreateContentDecryptionModule`
- `0x18010e6b8`: `CMFContentDecryptionModuleAccessStoreWrapper::CreateContentDecryptionModule`
- `0x18010e755`: `CMFContentDecryptionModuleAccessStoreWrapper::CreateContentDecryptionModule`
- `0x18010e822`: `CMFContentDecryptionModuleAccessStoreWrapper::CreateContentDecryptionModule`
- `0x18010e8d5`: `CMFContentDecryptionModuleAccessStoreWrapper::CreateContentDecryptionModule`
- `0x18010e994`: `CMFContentDecryptionModuleAccessStoreWrapper::CreateContentDecryptionModule`
- `0x18010ea56`: `CMFContentDecryptionModuleAccessStoreWrapper::CreateContentDecryptionModule`
- `0x18010eb0d`: `CMFContentDecryptionModuleAccessStoreWrapper::CreateContentDecryptionModule`
- `0x18010ec05`: `CMFContentDecryptionModuleAccessStoreWrapper::CreateContentDecryptionModule`
- `0x18010ecb4`: `CMFContentDecryptionModuleAccessStoreWrapper::CreateContentDecryptionModule`

## pseudocode

```c
__int64 __fastcall CMFContentDecryptionModuleAccessStoreWrapper::CreateContentDecryptionModule(
        CMFContentDecryptionModuleAccessStoreWrapper *this,
        struct IPropertyStore *a2,
        struct IMFContentDecryptionModule **a3)
{
  CMFContentDecryptionModuleSessionStoreWrapper *v6; // rdi
  CallStackTracing *v7; // rcx
  struct CallStackContext *ThreadRelativeContext; // rsi
  unsigned int v9; // ebx
  _GUID *v10; // rax
  _GUID v11; // xmm0
  int v12; // ebx
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  HSTRING v17; // rcx
  PCWSTR StringRawBuffer; // rax
  __int64 v19; // rdx
  __int64 v20; // r9
  CallStackTracing *v21; // rcx
  struct CallStackContext *v22; // rax
  CallStackTracing *v23; // rcx
  struct CallStackContext *v24; // rax
  __int64 v25; // rsi
  __int64 (__fastcall *v26)(__int64, struct IPropertyStore *, struct IUnknown **); // rbx
  CallStackTracing *v27; // rcx
  struct CallStackContext *v28; // rax
  struct IUnknown *v29; // rbx
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rsi
  CallStackTracing *v31; // rcx
  struct CallStackContext *v32; // rax
  CallStackTracing *v33; // rcx
  struct CallStackContext *v34; // rax
  CMFContentDecryptionModuleStoreWrapper *v35; // rax
  CMFContentDecryptionModuleStoreWrapper *v36; // rax
  CMFContentDecryptionModuleStoreWrapper *v37; // rbx
  CallStackTracing *v38; // rcx
  struct CallStackContext *v39; // rax
  CallStackTracing *v40; // rcx
  struct CallStackContext *v41; // rax
  CallStackScopeTrace v43; // [rsp+30h] [rbp-50h] BYREF
  void *v44; // [rsp+38h] [rbp-48h] BYREF
  struct IUnknown *v45; // [rsp+40h] [rbp-40h] BYREF
  __int64 v46; // [rsp+48h] [rbp-38h] BYREF
  PROPVARIANT pvar[2]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v48; // [rsp+60h] [rbp-20h]
  _BYTE v49[16]; // [rsp+68h] [rbp-18h] BYREF

  *a3 = 0;
  v45 = 0;
  v44 = 0;
  v46 = 0;
  v48 = 0;
  v6 = 0;
  *(_OWORD *)pvar = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    &v43,
    "CMFContentDecryptionModuleAccessStoreWrapper::CreateContentDecryptionModule",
    417);
  v7 = CallStackTracing::s_wpInstance;
  if ( CallStackTracing::s_wpInstance->m_fEnabled && *((_QWORD *)this + 4) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 296LL))(*((_QWORD *)this + 4));
    v10 = (_GUID *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 4) + 280LL))(
                     *((_QWORD *)this + 4),
                     v49);
    v7 = CallStackTracing::s_wpInstance;
    v11 = *v10;
    ThreadRelativeContext->m_instanceId = v9;
    ThreadRelativeContext->m_sessionId = v11;
  }
  if ( !a2 )
  {
    v12 = -1072875845;
    if ( !v7 )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v7 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v7->m_fEnabled )
    {
      v13 = CallStackTracing::GetThreadRelativeContext(v7);
      if ( v13->m_result != -1072875845 )
        CallStackContext::TraceFailure(
          v13,
          "CMFContentDecryptionModuleAccessStoreWrapper::CreateContentDecryptionModule",
          417,
          -1072875845);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v14 = 45;
LABEL_14:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, WPP_95e19eb2fcbc35395588268428fbcc11_Traceguids, this, v12);
      goto LABEL_100;
    }
    goto LABEL_100;
  }
  if ( !*((_QWORD *)this + 5) )
  {
    v12 = -2147024882;
    if ( !v7 )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v7 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v7->m_fEnabled )
    {
      v15 = CallStackTracing::GetThreadRelativeContext(v7);
      if ( v15->m_result != -2147024882 )
        CallStackContext::TraceFailure(
          v15,
          "CMFContentDecryptionModuleAccessStoreWrapper::CreateContentDecryptionModule",
          420,
          -2147024882);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_100;
    v16 = 46;
    goto LABEL_99;
  }
  v17 = (HSTRING)*((_QWORD *)this + 5);
  LOWORD(pvar[0]) = 31;
  StringRawBuffer = WindowsGetStringRawBuffer(v17, 0);
  v20 = -1;
  do
    ++v20;
  while ( StringRawBuffer[v20] );
  v12 = _AllocStringWorker<CTCoAllocPolicy>(&pvar[1], v19, StringRawBuffer);
  if ( v12 >= 0 )
  {
    v12 = a2->SetValue(
            a2,
            (const _tagpropertykey *)MF_CONTENTDECRYPTIONMODULE_PMPSTORECONTEXT,
            (const tagPROPVARIANT *)pvar);
    if ( v12 < 0 )
    {
      v23 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v23 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v23 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v23->m_fEnabled )
      {
        v24 = CallStackTracing::GetThreadRelativeContext(v23);
        if ( v24->m_result != v12 )
          CallStackContext::TraceFailure(
            v24,
            "CMFContentDecryptionModuleAccessStoreWrapper::CreateContentDecryptionModule",
            426,
            v12);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v14 = 48;
        goto LABEL_14;
      }
      goto LABEL_100;
    }
    v25 = *((_QWORD *)this + 2);
    v26 = *(__int64 (__fastcall **)(__int64, struct IPropertyStore *, struct IUnknown **))(*(_QWORD *)v25 + 24LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v45);
    v12 = v26(v25, a2, &v45);
    if ( v12 < 0 )
    {
      v27 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v27 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v27 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v27->m_fEnabled )
      {
        v28 = CallStackTracing::GetThreadRelativeContext(v27);
        if ( v28->m_result != v12 )
          CallStackContext::TraceFailure(
            v28,
            "CMFContentDecryptionModuleAccessStoreWrapper::CreateContentDecryptionModule",
            429,
            v12);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v14 = 49;
        goto LABEL_14;
      }
      goto LABEL_100;
    }
    v29 = v45;
    QueryInterface = v45->QueryInterface;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    v12 = QueryInterface(v29, &GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3, (void **)&v46);
    if ( v12 < 0 )
    {
      v31 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v31 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v31 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v31->m_fEnabled )
      {
        v32 = CallStackTracing::GetThreadRelativeContext(v31);
        if ( v32->m_result != v12 )
          CallStackContext::TraceFailure(
            v32,
            "CMFContentDecryptionModuleAccessStoreWrapper::CreateContentDecryptionModule",
            432,
            v12);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v14 = 50;
        goto LABEL_14;
      }
      goto LABEL_100;
    }
    v12 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v46 + 216LL))(
            v46,
            MF_INPROCDLL_LIFETIME_MANAGER,
            *((_QWORD *)this + 3));
    if ( v12 < 0 )
    {
      v33 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v33 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v33 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v33->m_fEnabled )
      {
        v34 = CallStackTracing::GetThreadRelativeContext(v33);
        if ( v34->m_result != v12 )
          CallStackContext::TraceFailure(
            v34,
            "CMFContentDecryptionModuleAccessStoreWrapper::CreateContentDecryptionModule",
            433,
            v12);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v14 = 51;
        goto LABEL_14;
      }
      goto LABEL_100;
    }
    v35 = (CMFContentDecryptionModuleStoreWrapper *)operator new(0x38u);
    if ( v35 )
    {
      v36 = CMFContentDecryptionModuleStoreWrapper::CMFContentDecryptionModuleStoreWrapper(
              v35,
              v45,
              *((struct CMFInprocLifetimeAssociation **)this + 3),
              *((struct IMFTelemetrySession **)this + 4),
              *((HSTRING *)this + 5));
      v37 = v36;
      if ( v36 )
      {
        _InterlockedIncrement((volatile signed __int32 *)v36 + 12);
        v6 = v36;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v44);
        v12 = CMFContentDecryptionModuleStoreWrapper::QueryInterface(
                v37,
                &GUID_87be986c_10be_4943_bf48_4b54ce1983a2,
                &v44);
        if ( v12 >= 0 )
        {
          Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v44);
          v12 = 0;
          *a3 = (struct IMFContentDecryptionModule *)v44;
        }
        else
        {
          v38 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v38 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v38 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v38->m_fEnabled )
          {
            v39 = CallStackTracing::GetThreadRelativeContext(v38);
            if ( v39->m_result != v12 )
              CallStackContext::TraceFailure(
                v39,
                "CMFContentDecryptionModuleAccessStoreWrapper::CreateContentDecryptionModule",
                442,
                v12);
          }
          if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          {
            v14 = 53;
            goto LABEL_14;
          }
        }
        goto LABEL_100;
      }
    }
    v40 = CallStackTracing::s_wpInstance;
    v12 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v40 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v40 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v40->m_fEnabled )
    {
      v41 = CallStackTracing::GetThreadRelativeContext(v40);
      if ( v41->m_result != -2147024882 )
        CallStackContext::TraceFailure(
          v41,
          "CMFContentDecryptionModuleAccessStoreWrapper::CreateContentDecryptionModule",
          440,
          -2147024882);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_100;
    v16 = 52;
LABEL_99:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v16,
      WPP_95e19eb2fcbc35395588268428fbcc11_Traceguids,
      this,
      -2147024882);
    goto LABEL_100;
  }
  v21 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
    {
      v21 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v21 = &stru_1801F8A30;
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
  }
  if ( v21->m_fEnabled )
  {
    v22 = CallStackTracing::GetThreadRelativeContext(v21);
    if ( v22->m_result != v12 )
      CallStackContext::TraceFailure(
        v22,
        "CMFContentDecryptionModuleAccessStoreWrapper::CreateContentDecryptionModule",
        425,
        v12);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
  {
    v14 = 47;
    goto LABEL_14;
  }
LABEL_100:
  PropVariantClear(pvar);
  CallStackScopeTrace::~CallStackScopeTrace(&v43);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v44);
  if ( v6 )
    CMFContentDecryptionModuleSessionStoreWrapper::Release(v6);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v45);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18010e580  mov     [rsp-38h+arg_18], rbx
0x18010e585  push    rbp
0x18010e586  push    rsi
0x18010e587  push    rdi
0x18010e588  push    r12
0x18010e58a  push    r13
0x18010e58c  push    r14
0x18010e58e  push    r15
0x18010e590  mov     rbp, rsp
0x18010e593  sub     rsp, 80h
0x18010e59a  mov     rax, cs:__security_cookie
0x18010e5a1  xor     rax, rsp
0x18010e5a4  mov     [rbp+var_8], rax
0x18010e5a8  xor     r13d, r13d
0x18010e5ab  mov     r12, r8
0x18010e5ae  mov     [r8], r13
0x18010e5b1  mov     r15, rdx
0x18010e5b4  mov     r14, rcx
0x18010e5b7  mov     [rbp+var_40], r13
0x18010e5bb  xorps   xmm0, xmm0
0x18010e5be  mov     [rbp+var_48], r13
0x18010e5c2  xor     eax, eax
0x18010e5c4  mov     [rbp+var_38], r13
0x18010e5c8  mov     r8d, 1A1h; int
0x18010e5ce  mov     [rbp+var_20], rax
0x18010e5d2  lea     rdx, aCmfcontentdecr; "CMFContentDecryptionModuleAccessStoreWr"...
0x18010e5d9  mov     edi, r13d
0x18010e5dc  lea     rcx, [rbp+var_50]; this
0x18010e5e0  movups  xmmword ptr [rbp+pvar], xmm0
0x18010e5e4  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18010e5e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18010e5f0  cmp     [rcx+8], r13b
0x18010e5f4  jz      short loc_18010E64E
0x18010e5f6  cmp     [r14+20h], r13
0x18010e5fa  jz      short loc_18010E64E
0x18010e5fc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18010e601  mov     rdx, [r14+20h]
0x18010e605  mov     rsi, rax
0x18010e608  mov     rcx, [rdx]
0x18010e60b  mov     rax, [rcx+128h]
0x18010e612  mov     rcx, rdx
0x18010e615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e61a  mov     r8, [r14+20h]
0x18010e61e  lea     rdx, [rbp+var_18]
0x18010e622  mov     ebx, eax
0x18010e624  mov     rcx, [r8]
0x18010e627  mov     rax, [rcx+118h]
0x18010e62e  mov     rcx, r8
0x18010e631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e636  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18010e63d  movups  xmm0, xmmword ptr [rax]
0x18010e640  mov     [rsi+7E0h], ebx
0x18010e646  movdqu  xmmword ptr [rsi+7D0h], xmm0
0x18010e64e  test    r15, r15
0x18010e651  jnz     loc_18010E6E8
0x18010e657  mov     ebx, 0C00D36BBh
0x18010e65c  test    rcx, rcx
0x18010e65f  jnz     short loc_18010E6A2
0x18010e661  mov     rax, cs:stru_1801FC290.__vftable
0x18010e668  lea     r8, stru_1801FC290
0x18010e66f  mov     edx, 7F0h
0x18010e674  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18010e67b  mov     rcx, r8
0x18010e67e  mov     rax, [rax+8]
0x18010e682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e687  test    eax, eax
0x18010e689  jnz     short loc_18010E69B
0x18010e68b  lea     rcx, stru_1801F8A30
0x18010e692  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18010e699  jmp     short loc_18010E6A2
0x18010e69b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18010e6a2  cmp     [rcx+8], r13b
0x18010e6a6  jz      short loc_18010E6CD
0x18010e6a8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18010e6ad  cmp     [rax+7CCh], ebx
0x18010e6b3  jz      short loc_18010E6CD
0x18010e6b5  mov     r9d, ebx; int
0x18010e6b8  lea     rdx, aCmfcontentdecr; "CMFContentDecryptionModuleAccessStoreWr"...
0x18010e6bf  mov     r8d, 1A1h; int
0x18010e6c5  mov     rcx, rax; this
0x18010e6c8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18010e6cd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18010e6d4  jb      loc_18010ECF5
0x18010e6da  mov     edx, 2Dh ; '-'
0x18010e6df  mov     dword ptr [rsp+80h+var_60], ebx
0x18010e6e3  jmp     loc_18010ECDB
0x18010e6e8  cmp     [r14+28h], r13
0x18010e6ec  jnz     loc_18010E781
0x18010e6f2  mov     esi, 8007000Eh
0x18010e6f7  mov     ebx, esi
0x18010e6f9  test    rcx, rcx
0x18010e6fc  jnz     short loc_18010E73F
0x18010e6fe  mov     rax, cs:stru_1801FC290.__vftable
0x18010e705  lea     r8, stru_1801FC290
0x18010e70c  mov     edx, 7F0h
0x18010e711  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18010e718  mov     rcx, r8
0x18010e71b  mov     rax, [rax+8]
0x18010e71f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e724  test    eax, eax
0x18010e726  jnz     short loc_18010E738
0x18010e728  lea     rcx, stru_1801F8A30
0x18010e72f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18010e736  jmp     short loc_18010E73F
0x18010e738  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18010e73f  cmp     [rcx+8], r13b
0x18010e743  jz      short loc_18010E76A
0x18010e745  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18010e74a  cmp     [rax+7CCh], esi
0x18010e750  jz      short loc_18010E76A
0x18010e752  mov     r9d, esi; int
0x18010e755  lea     rdx, aCmfcontentdecr; "CMFContentDecryptionModuleAccessStoreWr"...
0x18010e75c  mov     r8d, 1A4h; int
0x18010e762  mov     rcx, rax; this
0x18010e765  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18010e76a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18010e771  jb      loc_18010ECF5
0x18010e777  mov     edx, 2Eh ; '.'
0x18010e77c  jmp     loc_18010ECD7
0x18010e781  mov     rcx, [r14+28h]; string
0x18010e785  mov     eax, 1Fh
0x18010e78a  xor     edx, edx; length
0x18010e78c  mov     word ptr [rbp+pvar], ax
0x18010e790  call    cs:__imp_WindowsGetStringRawBuffer
0x18010e796  or      r9, 0FFFFFFFFFFFFFFFFh
0x18010e79a  inc     r9
0x18010e79d  cmp     [rax+r9*2], r13w
0x18010e7a2  jnz     short loc_18010E79A
0x18010e7a4  lea     rcx, [rbp+pvar+8]
0x18010e7a8  mov     r8, rax
0x18010e7ab  mov     [rsp+80h+var_58], rcx
0x18010e7b0  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18010e7b5  mov     ebx, eax
0x18010e7b7  test    eax, eax
0x18010e7b9  jns     loc_18010E84E
0x18010e7bf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18010e7c6  test    rcx, rcx
0x18010e7c9  jnz     short loc_18010E80C
0x18010e7cb  mov     rcx, cs:stru_1801FC290.__vftable
0x18010e7d2  lea     r8, stru_1801FC290
0x18010e7d9  mov     edx, 7F0h
0x18010e7de  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18010e7e5  mov     rax, [rcx+8]
0x18010e7e9  mov     rcx, r8
0x18010e7ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e7f1  test    eax, eax
0x18010e7f3  jnz     short loc_18010E805
0x18010e7f5  lea     rcx, stru_1801F8A30
0x18010e7fc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18010e803  jmp     short loc_18010E80C
0x18010e805  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18010e80c  cmp     [rcx+8], r13b
0x18010e810  jz      short loc_18010E837
0x18010e812  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18010e817  cmp     [rax+7CCh], ebx
0x18010e81d  jz      short loc_18010E837
0x18010e81f  mov     r9d, ebx; int
0x18010e822  lea     rdx, aCmfcontentdecr; "CMFContentDecryptionModuleAccessStoreWr"...
0x18010e829  mov     r8d, 1A9h; int
0x18010e82f  mov     rcx, rax; this
0x18010e832  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18010e837  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18010e83e  jb      loc_18010ECF5
0x18010e844  mov     edx, 2Fh ; '/'
0x18010e849  jmp     loc_18010E6DF
0x18010e84e  mov     rax, [r15]
0x18010e851  lea     r8, [rbp+pvar]
0x18010e855  lea     rdx, MF_CONTENTDECRYPTIONMODULE_PMPSTORECONTEXT
0x18010e85c  mov     rcx, r15
0x18010e85f  mov     rax, [rax+30h]
0x18010e863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e868  mov     ebx, eax
0x18010e86a  test    eax, eax
0x18010e86c  jns     loc_18010E901
0x18010e872  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18010e879  test    rcx, rcx
0x18010e87c  jnz     short loc_18010E8BF
0x18010e87e  mov     rax, cs:stru_1801FC290.__vftable
0x18010e885  lea     r8, stru_1801FC290
0x18010e88c  mov     edx, 7F0h
0x18010e891  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18010e898  mov     rcx, r8
0x18010e89b  mov     rax, [rax+8]
0x18010e89f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e8a4  test    eax, eax
0x18010e8a6  jnz     short loc_18010E8B8
0x18010e8a8  lea     rcx, stru_1801F8A30
0x18010e8af  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18010e8b6  jmp     short loc_18010E8BF
0x18010e8b8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18010e8bf  cmp     [rcx+8], r13b
0x18010e8c3  jz      short loc_18010E8EA
0x18010e8c5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18010e8ca  cmp     [rax+7CCh], ebx
0x18010e8d0  jz      short loc_18010E8EA
0x18010e8d2  mov     r9d, ebx; int
0x18010e8d5  lea     rdx, aCmfcontentdecr; "CMFContentDecryptionModuleAccessStoreWr"...
0x18010e8dc  mov     r8d, 1AAh; int
0x18010e8e2  mov     rcx, rax; this
0x18010e8e5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18010e8ea  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18010e8f1  jb      loc_18010ECF5
0x18010e8f7  mov     edx, 30h ; '0'
0x18010e8fc  jmp     loc_18010E6DF
0x18010e901  mov     rsi, [r14+10h]
0x18010e905  lea     rcx, [rbp+var_40]
0x18010e909  mov     rax, [rsi]
0x18010e90c  mov     rbx, [rax+18h]
0x18010e910  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010e915  lea     r8, [rbp+var_40]
0x18010e919  mov     rdx, r15
0x18010e91c  mov     rcx, rsi
0x18010e91f  mov     rax, rbx
0x18010e922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e927  mov     ebx, eax
0x18010e929  test    eax, eax
0x18010e92b  jns     loc_18010E9C0
0x18010e931  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18010e938  test    rcx, rcx
0x18010e93b  jnz     short loc_18010E97E
0x18010e93d  mov     rax, cs:stru_1801FC290.__vftable
0x18010e944  lea     r8, stru_1801FC290
0x18010e94b  mov     edx, 7F0h
0x18010e950  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18010e957  mov     rcx, r8
0x18010e95a  mov     rax, [rax+8]
0x18010e95e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e963  test    eax, eax
0x18010e965  jnz     short loc_18010E977
0x18010e967  lea     rcx, stru_1801F8A30
0x18010e96e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18010e975  jmp     short loc_18010E97E
0x18010e977  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18010e97e  cmp     [rcx+8], r13b
0x18010e982  jz      short loc_18010E9A9
0x18010e984  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18010e989  cmp     [rax+7CCh], ebx
0x18010e98f  jz      short loc_18010E9A9
0x18010e991  mov     r9d, ebx; int
0x18010e994  lea     rdx, aCmfcontentdecr; "CMFContentDecryptionModuleAccessStoreWr"...
0x18010e99b  mov     r8d, 1ADh; int
0x18010e9a1  mov     rcx, rax; this
0x18010e9a4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18010e9a9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18010e9b0  jb      loc_18010ECF5
0x18010e9b6  mov     edx, 31h ; '1'
0x18010e9bb  jmp     loc_18010E6DF
0x18010e9c0  mov     rbx, [rbp+var_40]
0x18010e9c4  lea     rcx, [rbp+var_38]
0x18010e9c8  mov     rax, [rbx]
0x18010e9cb  mov     rsi, [rax]
0x18010e9ce  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010e9d3  lea     r8, [rbp+var_38]
0x18010e9d7  mov     rcx, rbx
0x18010e9da  lea     rdx, _GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3
0x18010e9e1  mov     rax, rsi
0x18010e9e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e9e9  mov     ebx, eax
0x18010e9eb  test    eax, eax
0x18010e9ed  jns     loc_18010EA82
0x18010e9f3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18010e9fa  test    rcx, rcx
0x18010e9fd  jnz     short loc_18010EA40
0x18010e9ff  mov     rax, cs:stru_1801FC290.__vftable
0x18010ea06  lea     r8, stru_1801FC290
0x18010ea0d  mov     edx, 7F0h
0x18010ea12  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18010ea19  mov     rcx, r8
0x18010ea1c  mov     rax, [rax+8]
0x18010ea20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ea25  test    eax, eax
0x18010ea27  jnz     short loc_18010EA39
0x18010ea29  lea     rcx, stru_1801F8A30
0x18010ea30  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18010ea37  jmp     short loc_18010EA40
0x18010ea39  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18010ea40  cmp     [rcx+8], r13b
0x18010ea44  jz      short loc_18010EA6B
0x18010ea46  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18010ea4b  cmp     [rax+7CCh], ebx
0x18010ea51  jz      short loc_18010EA6B
0x18010ea53  mov     r9d, ebx; int
0x18010ea56  lea     rdx, aCmfcontentdecr; "CMFContentDecryptionModuleAccessStoreWr"...
0x18010ea5d  mov     r8d, 1B0h; int
0x18010ea63  mov     rcx, rax; this
0x18010ea66  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18010ea6b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18010ea72  jb      loc_18010ECF5
0x18010ea78  mov     edx, 32h ; '2'
0x18010ea7d  jmp     loc_18010E6DF
0x18010ea82  mov     rcx, [rbp+var_38]
0x18010ea86  lea     rdx, MF_INPROCDLL_LIFETIME_MANAGER
0x18010ea8d  mov     r8, [r14+18h]
0x18010ea91  mov     rax, [rcx]
0x18010ea94  mov     rax, [rax+0D8h]
0x18010ea9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010eaa0  mov     ebx, eax
0x18010eaa2  test    eax, eax
0x18010eaa4  jns     loc_18010EB39
0x18010eaaa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
