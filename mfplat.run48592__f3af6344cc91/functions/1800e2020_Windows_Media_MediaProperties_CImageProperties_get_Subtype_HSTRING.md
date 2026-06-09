# Windows::Media::MediaProperties::CImageProperties::get_Subtype(HSTRING__ * *)

- ea: `0x1800e2020`
- end: `0x1800e23bc`
- name: `?get_Subtype@CImageProperties@MediaProperties@Media@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `924`
- prototype: `int(Windows::Media::MediaProperties::CImageProperties *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18002146c`
- `0x180024390`
- `0x180035e28`
- `0x18007b720`
- `0x18008a268`
- `0x1800e2020`
- `0x1801200d0`
- `0x180121575`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e2055`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e2055`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e238d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e238d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e2376`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e2376`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x1800e2166`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x1800e2166`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800e21fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800e22d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800e22ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800e21fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800e22d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800e22ee`

## pseudocode

```c
__int64 __fastcall Windows::Media::MediaProperties::CImageProperties::get_Subtype(
        Windows::Media::MediaProperties::CImageProperties *this,
        HSTRING *a2)
{
  Microsoft::WRL::Wrappers::SRWLock *p_Lock; // r15
  CallStackTracing *v5; // rcx
  HRESULT String; // edi
  struct CallStackContext *ThreadRelativeContext; // rax
  int v8; // r8d
  Windows::Media::MediaProperties::CMediaPropertySet *ptr; // rcx
  Windows::Media::MediaProperties::CMediaPropertySet_vtbl *v10; // rax
  int v11; // ebx
  CallStackTracing *v12; // rcx
  __int64 v13; // rdx
  CallStackTracing *v14; // rcx
  unsigned int i; // ebx
  CallStackTracing *v16; // rcx
  LPOLESTR lpsz; // [rsp+20h] [rbp-60h] BYREF
  __int64 v19; // [rsp+28h] [rbp-58h] BYREF
  int v20; // [rsp+30h] [rbp-50h]
  RoVariant *v21; // [rsp+38h] [rbp-48h]
  struct IInspectable *v22; // [rsp+40h] [rbp-40h] BYREF
  GUID v23; // [rsp+50h] [rbp-30h] BYREF
  IID rclsid; // [rsp+60h] [rbp-20h] BYREF

  p_Lock = &this->_Lock;
  AcquireSRWLockExclusive(&this->_Lock.SRWLock_);
  v19 = 0;
  v20 = 0;
  lpsz = 0;
  rclsid = 0;
  if ( !a2 )
  {
    v5 = CallStackTracing::s_wpInstance;
    String = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v5 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v5->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v5);
      if ( ThreadRelativeContext->m_result != -2147467261 )
      {
        v8 = 231;
LABEL_44:
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "Windows::Media::MediaProperties::CImageProperties::get_Subtype",
          v8,
          String);
        goto LABEL_45;
      }
    }
    goto LABEL_45;
  }
  *a2 = 0;
  ptr = this->_spProperties.ptr_;
  String = 0;
  v10 = ptr->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<_GUID,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<_GUID,IInspectable *> *>,Microsoft::WRL::CloakedIid<Windows::Media::MediaProperties::IMediaPropertySetInternal>,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<_GUID,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<_GUID,IInspectable *> *>,Microsoft::WRL::CloakedIid<Windows::Media::MediaProperties::IMediaPropertySetInternal>,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IMap<_GUID,IInspectable *>,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<_GUID,IInspectable *> *>,Microsoft::WRL::CloakedIid<Windows::Media::MediaProperties::IMediaPropertySetInternal>,Microsoft::WRL::FtmBase>::Windows::Foundation::Collections::IMap<_GUID,IInspectable *>::Windows::Foundation::Collections::IMap_impl<_GUID,IInspectable *>::IInspectable::IUnknown::__vftable;
  v21 = (RoVariant *)&v19;
  v22 = 0;
  v23 = MF_MT_SUBTYPE;
  v11 = ((__int64 (__fastcall *)(Windows::Media::MediaProperties::CMediaPropertySet *, GUID *, struct IInspectable **))v10->Lookup)(
          ptr,
          &v23,
          &v22);
  RoVariant::Attach(v21, v22);
  if ( v11 < 0 )
    goto LABEL_45;
  if ( !this->_fSubtypeIsGuid || GetGuid((const struct RoVariant *)&v19, &rclsid) < 0 )
  {
LABEL_30:
    if ( GetGuid((const struct RoVariant *)&v19, &rclsid) >= 0 )
    {
      for ( i = 0; i < 0xB; ++i )
      {
        if ( !memcmp_0(&details::s_arrImageSubtype + 6 * i, &rclsid, 0x10u) )
        {
          if ( WindowsCreateString(
                 *((PCNZWCH *)&details::s_arrImageSubtype + 6 * i + 2),
                 *((_DWORD *)&details::s_arrImageSubtype + 12 * i + 6),
                 a2) >= 0 )
            goto LABEL_45;
          break;
        }
      }
    }
    String = WindowsCreateString(L"Unknown", 7u, a2);
    if ( String < 0 )
    {
      v16 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v16 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v16 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v16->m_fEnabled )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v16);
        if ( ThreadRelativeContext->m_result != String )
        {
          v8 = 246;
          goto LABEL_44;
        }
      }
    }
    goto LABEL_45;
  }
  String = StringFromIID(&rclsid, &lpsz);
  if ( String >= 0 )
  {
    v13 = -1;
    do
      ++v13;
    while ( lpsz[v13] );
    String = WindowsCreateString(lpsz, v13, a2);
    if ( String < 0 )
    {
      v14 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v14 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v14 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v14->m_fEnabled )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v14);
        if ( ThreadRelativeContext->m_result != String )
        {
          v8 = 240;
          goto LABEL_44;
        }
      }
      goto LABEL_45;
    }
    goto LABEL_30;
  }
  v12 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
    {
      v12 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v12 = &stru_1801F8A30;
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
  }
  if ( v12->m_fEnabled )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v12);
    if ( ThreadRelativeContext->m_result != String )
    {
      v8 = 239;
      goto LABEL_44;
    }
  }
LABEL_45:
  CoTaskMemFree(lpsz);
  RoVariant::~RoVariant((RoVariant *)&v19);
  if ( p_Lock )
    ReleaseSRWLockExclusive(&p_Lock->SRWLock_);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x1800e2020  mov     [rsp-38h+arg_10], rbx
0x1800e2025  push    rbp
0x1800e2026  push    rsi
0x1800e2027  push    rdi
0x1800e2028  push    r12
0x1800e202a  push    r13
0x1800e202c  push    r14
0x1800e202e  push    r15
0x1800e2030  mov     rbp, rsp
0x1800e2033  sub     rsp, 80h
0x1800e203a  mov     rax, cs:__security_cookie
0x1800e2041  xor     rax, rsp
0x1800e2044  mov     [rbp+var_10], rax
0x1800e2048  lea     r15, [rcx+38h]
0x1800e204c  mov     r14, rcx
0x1800e204f  mov     rcx, r15; SRWLock
0x1800e2052  mov     rsi, rdx
0x1800e2055  call    cs:__imp_AcquireSRWLockExclusive
0x1800e205b  xor     r12d, r12d
0x1800e205e  xorps   xmm0, xmm0
0x1800e2061  mov     [rbp+var_58], r12
0x1800e2065  mov     [rbp+var_50], r12d
0x1800e2069  mov     [rbp+lpsz], r12
0x1800e206d  movups  xmmword ptr [rbp+rclsid.Data1], xmm0
0x1800e2071  test    rsi, rsi
0x1800e2074  jnz     short loc_1800E20EE
0x1800e2076  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e207d  mov     edi, 80004003h
0x1800e2082  test    rcx, rcx
0x1800e2085  jnz     short loc_1800E20C8
0x1800e2087  mov     rax, cs:stru_1801FC290.__vftable
0x1800e208e  lea     r8, stru_1801FC290
0x1800e2095  mov     edx, 7F0h
0x1800e209a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e20a1  mov     rcx, r8
0x1800e20a4  mov     rax, [rax+8]
0x1800e20a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e20ad  test    eax, eax
0x1800e20af  jnz     short loc_1800E20C1
0x1800e20b1  lea     rcx, stru_1801F8A30
0x1800e20b8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e20bf  jmp     short loc_1800E20C8
0x1800e20c1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800e20c8  cmp     [rcx+8], r12b
0x1800e20cc  jz      loc_1800E2372
0x1800e20d2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e20d7  cmp     [rax+7CCh], edi
0x1800e20dd  jz      loc_1800E2372
0x1800e20e3  mov     r8d, 0E7h
0x1800e20e9  jmp     loc_1800E2360
0x1800e20ee  mov     [rsi], r12
0x1800e20f1  lea     rdx, [rbp+var_58]
0x1800e20f5  mov     rcx, [r14+30h]
0x1800e20f9  lea     r8, [rbp+var_40]
0x1800e20fd  movups  xmm0, xmmword ptr cs:MF_MT_SUBTYPE.Data1
0x1800e2104  mov     edi, r12d
0x1800e2107  mov     rax, [rcx]
0x1800e210a  mov     [rbp+var_48], rdx
0x1800e210e  lea     rdx, [rbp+var_30]
0x1800e2112  mov     [rbp+var_40], r12
0x1800e2116  movdqu  [rbp+var_30], xmm0
0x1800e211b  mov     rax, [rax+30h]
0x1800e211f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2124  mov     rdx, [rbp+var_40]; struct IInspectable *
0x1800e2128  mov     ebx, eax
0x1800e212a  mov     rcx, [rbp+var_48]; this
0x1800e212e  call    ?Attach@RoVariant@@QEAAXPEAUIInspectable@@@Z; RoVariant::Attach(IInspectable *)
0x1800e2133  shr     ebx, 1Fh
0x1800e2136  xor     bl, 1
0x1800e2139  jz      loc_1800E2372
0x1800e213f  cmp     [r14+40h], r12b
0x1800e2143  jz      loc_1800E2279
0x1800e2149  lea     rdx, [rbp+rclsid]; struct _GUID *
0x1800e214d  lea     rcx, [rbp+var_58]; struct RoVariant *
0x1800e2151  call    ?GetGuid@@YAJAEBVRoVariant@@PEAU_GUID@@@Z; GetGuid(RoVariant const &,_GUID *)
0x1800e2156  test    eax, eax
0x1800e2158  js      loc_1800E2279
0x1800e215e  lea     rdx, [rbp+lpsz]; lplpsz
0x1800e2162  lea     rcx, [rbp+rclsid]; rclsid
0x1800e2166  call    cs:__imp_StringFromIID
0x1800e216c  mov     edi, eax
0x1800e216e  test    eax, eax
0x1800e2170  jns     short loc_1800E21E5
0x1800e2172  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2179  test    rcx, rcx
0x1800e217c  jnz     short loc_1800E21BF
0x1800e217e  mov     rcx, cs:stru_1801FC290.__vftable
0x1800e2185  lea     r8, stru_1801FC290
0x1800e218c  mov     edx, 7F0h
0x1800e2191  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2198  mov     rax, [rcx+8]
0x1800e219c  mov     rcx, r8
0x1800e219f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e21a4  test    eax, eax
0x1800e21a6  jnz     short loc_1800E21B8
0x1800e21a8  lea     rcx, stru_1801F8A30
0x1800e21af  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e21b6  jmp     short loc_1800E21BF
0x1800e21b8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800e21bf  cmp     [rcx+8], r12b
0x1800e21c3  jz      loc_1800E2372
0x1800e21c9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e21ce  cmp     [rax+7CCh], edi
0x1800e21d4  jz      loc_1800E2372
0x1800e21da  mov     r8d, 0EFh
0x1800e21e0  jmp     loc_1800E2360
0x1800e21e5  mov     rcx, [rbp+lpsz]; sourceString
0x1800e21e9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800e21ed  inc     rdx; length
0x1800e21f0  cmp     [rcx+rdx*2], r12w
0x1800e21f5  jnz     short loc_1800E21ED
0x1800e21f7  mov     r8, rsi; string
0x1800e21fa  call    cs:__imp_WindowsCreateString
0x1800e2200  mov     edi, eax
0x1800e2202  test    eax, eax
0x1800e2204  jns     short loc_1800E2279
0x1800e2206  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e220d  test    rcx, rcx
0x1800e2210  jnz     short loc_1800E2253
0x1800e2212  mov     rax, cs:stru_1801FC290.__vftable
0x1800e2219  lea     r8, stru_1801FC290
0x1800e2220  mov     edx, 7F0h
0x1800e2225  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e222c  mov     rcx, r8
0x1800e222f  mov     rax, [rax+8]
0x1800e2233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2238  test    eax, eax
0x1800e223a  jnz     short loc_1800E224C
0x1800e223c  lea     rcx, stru_1801F8A30
0x1800e2243  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e224a  jmp     short loc_1800E2253
0x1800e224c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800e2253  cmp     [rcx+8], r12b
0x1800e2257  jz      loc_1800E2372
0x1800e225d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e2262  cmp     [rax+7CCh], edi
0x1800e2268  jz      loc_1800E2372
0x1800e226e  mov     r8d, 0F0h
0x1800e2274  jmp     loc_1800E2360
0x1800e2279  lea     rdx, [rbp+rclsid]; struct _GUID *
0x1800e227d  lea     rcx, [rbp+var_58]; struct RoVariant *
0x1800e2281  call    ?GetGuid@@YAJAEBVRoVariant@@PEAU_GUID@@@Z; GetGuid(RoVariant const &,_GUID *)
0x1800e2286  test    eax, eax
0x1800e2288  js      short loc_1800E22DF
0x1800e228a  mov     ebx, r12d
0x1800e228d  lea     r13, ?s_arrImageSubtype@details@@3QBUGuidNameMappingEntryWithContentType@1@B; details::GuidNameMappingEntryWithContentType const near * const details::s_arrImageSubtype
0x1800e2294  cmp     ebx, 0Bh
0x1800e2297  jnb     short loc_1800E22DF
0x1800e2299  mov     eax, ebx
0x1800e229b  lea     rdx, [rbp+rclsid]; Buf2
0x1800e229f  mov     r8d, 10h; Size
0x1800e22a5  lea     r14, [rax+rax*2]
0x1800e22a9  add     r14, r14
0x1800e22ac  lea     rcx, ds:0[r14*8]
0x1800e22b4  add     rcx, r13; Buf1
0x1800e22b7  call    memcmp_0
0x1800e22bc  test    eax, eax
0x1800e22be  jz      short loc_1800E22C4
0x1800e22c0  inc     ebx
0x1800e22c2  jmp     short loc_1800E2294
0x1800e22c4  mov     edx, [r13+r14*8+18h]; length
0x1800e22c9  mov     r8, rsi; string
0x1800e22cc  mov     rcx, [r13+r14*8+10h]; sourceString
0x1800e22d1  call    cs:__imp_WindowsCreateString
0x1800e22d7  test    eax, eax
0x1800e22d9  jns     loc_1800E2372
0x1800e22df  mov     r8, rsi; string
0x1800e22e2  lea     rcx, ?Media_Unknown@@3QBGB; "Unknown"
0x1800e22e9  mov     edx, 7; length
0x1800e22ee  call    cs:__imp_WindowsCreateString
0x1800e22f4  mov     edi, eax
0x1800e22f6  test    eax, eax
0x1800e22f8  jns     short loc_1800E2372
0x1800e22fa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2301  test    rcx, rcx
0x1800e2304  jnz     short loc_1800E2347
0x1800e2306  mov     rax, cs:stru_1801FC290.__vftable
0x1800e230d  lea     r8, stru_1801FC290
0x1800e2314  mov     edx, 7F0h
0x1800e2319  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2320  mov     rcx, r8
0x1800e2323  mov     rax, [rax+8]
0x1800e2327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e232c  test    eax, eax
0x1800e232e  jnz     short loc_1800E2340
0x1800e2330  lea     rcx, stru_1801F8A30
0x1800e2337  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e233e  jmp     short loc_1800E2347
0x1800e2340  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800e2347  cmp     [rcx+8], r12b
0x1800e234b  jz      short loc_1800E2372
0x1800e234d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e2352  cmp     [rax+7CCh], edi
0x1800e2358  jz      short loc_1800E2372
0x1800e235a  mov     r8d, 0F6h; int
0x1800e2360  mov     r9d, edi; int
0x1800e2363  lea     rdx, aWindowsMediaMe_6; "Windows::Media::MediaProperties::CImage"...
0x1800e236a  mov     rcx, rax; this
0x1800e236d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e2372  mov     rcx, [rbp+lpsz]; pv
0x1800e2376  call    cs:__imp_CoTaskMemFree
0x1800e237c  lea     rcx, [rbp+var_58]; this
0x1800e2380  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x1800e2385  test    r15, r15
0x1800e2388  jz      short loc_1800E2393
0x1800e238a  mov     rcx, r15; SRWLock
0x1800e238d  call    cs:__imp_ReleaseSRWLockExclusive
0x1800e2393  mov     eax, edi
0x1800e2395  mov     rcx, [rbp+var_10]
0x1800e2399  xor     rcx, rsp; StackCookie
0x1800e239c  call    __security_check_cookie
0x1800e23a1  mov     rbx, [rsp+80h+arg_10]
0x1800e23a9  add     rsp, 80h
0x1800e23b0  pop     r15
0x1800e23b2  pop     r14
0x1800e23b4  pop     r13
0x1800e23b6  pop     r12
0x1800e23b8  pop     rdi
0x1800e23b9  pop     rsi
0x1800e23ba  pop     rbp
0x1800e23bb  retn
```
