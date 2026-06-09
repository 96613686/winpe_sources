# CStoreByteStreamRegistrar::EnumerateStoreMediaSourceExtensions(void)

- ea: `0x18001d2bc`
- end: `0x18001d514`
- name: `?EnumerateStoreMediaSourceExtensions@CStoreByteStreamRegistrar@@AEAAJXZ`
- size: `600`
- prototype: `__int64 __fastcall(CStoreByteStreamRegistrar *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ce20`
- `0x180176adc`

## callees

- `0x180004870`
- `0x1800144ac`
- `0x18001d2bc`
- `0x18001d51c`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x1801200d0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001d50d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001d50d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001d327`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001d327`
- `CompPkgSup!GetMediaComponentPackageInfo` at `0x18001d33f`
- `CompPkgSup!GetMediaComponentPackageInfo` at `0x18001d33f`

## string_xrefs

- `0x18001d2f1`: `CStoreByteStreamRegistrar::EnumerateStoreMediaSourceExtensions`
- `0x18001d441`: `CStoreByteStreamRegistrar::EnumerateStoreMediaSourceExtensions`
- `0x18001d4f0`: `CStoreByteStreamRegistrar::EnumerateStoreMediaSourceExtensions`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CStoreByteStreamRegistrar::EnumerateStoreMediaSourceExtensions(CStoreByteStreamRegistrar *this)
{
  HRESULT v2; // eax
  int MediaComponentPackageInfo; // ebx
  __int64 *v4; // rcx
  CallStackTracing *v6; // rcx
  __int64 v7; // rdx
  struct CallStackContext *ThreadRelativeContext; // rax
  CallStackTracing *v9; // rcx
  struct CallStackContext *v10; // rax
  CallStackScopeTrace v11; // [rsp+30h] [rbp-40h] BYREF
  __int64 *v12; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-18h] BYREF

  *((_BYTE *)this + 64) = 1;
  v12 = 0;
  CallStackScopeTrace::CallStackScopeTrace(&v11, "CStoreByteStreamRegistrar::EnumerateStoreMediaSourceExtensions", 305);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v12);
  string = 0;
  v2 = WindowsCreateStringReference(L"windows.mediaSource", 0x13u, &hstringHeader, &string);
  if ( v2 < 0 )
  {
    RaiseException(v2, 1u, 0, 0);
    JUMPOUT(0x18001D513LL);
  }
  MediaComponentPackageInfo = GetMediaComponentPackageInfo(0, string, &v12);
  string = 0;
  if ( MediaComponentPackageInfo < 0 )
  {
    v6 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v6 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v6->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v6);
      if ( ThreadRelativeContext->m_result != MediaComponentPackageInfo )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CStoreByteStreamRegistrar::EnumerateStoreMediaSourceExtensions",
          305,
          MediaComponentPackageInfo);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v7 = 30;
LABEL_23:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        WPP_b75d7078c4363b03f2a23387d5361fbc_Traceguids,
        this,
        MediaComponentPackageInfo);
    }
  }
  else
  {
    Microsoft::WRL::ComPtr<CMFInprocLifetimeAssociation>::InternalRelease((char *)this + 72);
    MediaComponentPackageInfo = GetExtensionInfoArrayFromVector<CExtensionPackInfoArray<SourcePackInfo>>(
                                  v12,
                                  (_QWORD *)this + 9);
    if ( MediaComponentPackageInfo < 0 )
    {
      v9 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v9 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v9 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v9->m_fEnabled )
      {
        v10 = CallStackTracing::GetThreadRelativeContext(v9);
        if ( v10->m_result != MediaComponentPackageInfo )
          CallStackContext::TraceFailure(
            v10,
            "CStoreByteStreamRegistrar::EnumerateStoreMediaSourceExtensions",
            307,
            MediaComponentPackageInfo);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v7 = 31;
        goto LABEL_23;
      }
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace(&v11);
  v4 = v12;
  if ( v12 )
  {
    v12 = 0;
    (*(void (__fastcall **)(__int64 *))(*v4 + 16))(v4);
  }
  return (unsigned int)MediaComponentPackageInfo;
}

```

## disassembly

```asm
0x18001d2bc  mov     [rsp-8+arg_8], rbx
0x18001d2c1  mov     [rsp-8+arg_10], rdi
0x18001d2c6  push    rbp
0x18001d2c7  mov     rbp, rsp
0x18001d2ca  sub     rsp, 70h
0x18001d2ce  mov     rax, cs:__security_cookie
0x18001d2d5  xor     rax, rsp
0x18001d2d8  mov     [rbp+var_10], rax
0x18001d2dc  mov     rdi, rcx
0x18001d2df  mov     byte ptr [rcx+40h], 1
0x18001d2e3  mov     [rbp+var_38], 0
0x18001d2eb  mov     r8d, 131h; int
0x18001d2f1  lea     rdx, aCstorebytestre_3; "CStoreByteStreamRegistrar::EnumerateSto"...
0x18001d2f8  lea     rcx, [rbp+var_40]; this
0x18001d2fc  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001d301  nop
0x18001d302  lea     rcx, [rbp+var_38]
0x18001d306  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001d30b  mov     [rbp+string], 0
0x18001d313  lea     r9, [rbp+string]; string
0x18001d317  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001d31b  mov     edx, 13h; length
0x18001d320  lea     rcx, sourceString; "windows.mediaSource"
0x18001d327  call    cs:__imp_WindowsCreateStringReference
0x18001d32d  test    eax, eax
0x18001d32f  js      loc_18001D501
0x18001d335  lea     r8, [rbp+var_38]
0x18001d339  mov     rdx, [rbp+string]
0x18001d33d  xor     ecx, ecx
0x18001d33f  call    cs:__imp_GetMediaComponentPackageInfo
0x18001d345  mov     ebx, eax
0x18001d347  mov     [rbp+string], 0
0x18001d34f  shr     eax, 1Fh
0x18001d352  test    al, al
0x18001d354  jnz     short loc_18001D3BD
0x18001d356  lea     rcx, [rdi+48h]
0x18001d35a  call    ?InternalRelease@?$ComPtr@VCMFInprocLifetimeAssociation@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CMFInprocLifetimeAssociation>::InternalRelease(void)
0x18001d35f  lea     rdx, [rdi+48h]
0x18001d363  mov     rcx, [rbp+var_38]
0x18001d367  call    ??$GetExtensionInfoArrayFromVector@V?$CExtensionPackInfoArray@USourcePackInfo@@@@@@YAJPEAU?$IVector@PEAUIPropertySet@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@PEAPEAV?$CExtensionPackInfoArray@USourcePackInfo@@@@@Z; GetExtensionInfoArrayFromVector<CExtensionPackInfoArray<SourcePackInfo>>(Windows::Foundation::Collections::IVector<Windows::Foundation::Collections::IPropertySet *> *,CExtensionPackInfoArray<SourcePackInfo> * *)
0x18001d36c  mov     ebx, eax
0x18001d36e  test    eax, eax
0x18001d370  js      loc_18001D452
0x18001d376  lea     rcx, [rbp+var_40]; this
0x18001d37a  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001d37f  nop
0x18001d380  mov     rcx, [rbp+var_38]
0x18001d384  test    rcx, rcx
0x18001d387  jz      short loc_18001D39D
0x18001d389  mov     [rbp+var_38], 0
0x18001d391  mov     rax, [rcx]
0x18001d394  mov     rax, [rax+10h]
0x18001d398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d39d  mov     eax, ebx
0x18001d39f  mov     rcx, [rbp+var_10]
0x18001d3a3  xor     rcx, rsp; StackCookie
0x18001d3a6  call    __security_check_cookie
0x18001d3ab  lea     r11, [rsp+70h+var_s0]
0x18001d3b0  mov     rbx, [r11+18h]
0x18001d3b4  mov     rdi, [r11+20h]
0x18001d3b8  mov     rsp, r11
0x18001d3bb  pop     rbp
0x18001d3bc  retn
0x18001d3bd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d3c4  test    rcx, rcx
0x18001d3c7  jnz     short loc_18001D401
0x18001d3c9  lea     r8, stru_1801FC290
0x18001d3d0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d3d7  mov     rax, cs:stru_1801FC290.__vftable
0x18001d3de  mov     edx, 7F0h
0x18001d3e3  mov     rcx, r8
0x18001d3e6  mov     rax, [rax+8]
0x18001d3ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3ef  test    eax, eax
0x18001d3f1  jnz     short loc_18001D41E
0x18001d3f3  lea     rcx, stru_1801F8A30; this
0x18001d3fa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d401  cmp     byte ptr [rcx+8], 0
0x18001d405  jnz     short loc_18001D427
0x18001d407  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001d40e  jb      loc_18001D376
0x18001d414  mov     edx, 1Eh
0x18001d419  jmp     loc_18001D4AE
0x18001d41e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d425  jmp     short loc_18001D401
0x18001d427  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001d42c  test    ebx, ebx
0x18001d42e  jns     short loc_18001D407
0x18001d430  cmp     [rax+7CCh], ebx
0x18001d436  jz      short loc_18001D407
0x18001d438  mov     r9d, ebx; int
0x18001d43b  mov     r8d, 131h; int
0x18001d441  lea     rdx, aCstorebytestre_3; "CStoreByteStreamRegistrar::EnumerateSto"...
0x18001d448  mov     rcx, rax; this
0x18001d44b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001d450  jmp     short loc_18001D407
0x18001d452  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d459  test    rcx, rcx
0x18001d45c  jnz     short loc_18001D496
0x18001d45e  lea     r8, stru_1801FC290
0x18001d465  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d46c  mov     rcx, cs:stru_1801FC290.__vftable
0x18001d473  mov     rax, [rcx+8]
0x18001d477  mov     edx, 7F0h
0x18001d47c  mov     rcx, r8
0x18001d47f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d484  test    eax, eax
0x18001d486  jnz     short loc_18001D4D1
0x18001d488  lea     rcx, stru_1801F8A30; this
0x18001d48f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d496  cmp     byte ptr [rcx+8], 0
0x18001d49a  jnz     short loc_18001D4DA
0x18001d49c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001d4a3  jb      loc_18001D376
0x18001d4a9  mov     edx, 1Fh
0x18001d4ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d4b5  mov     [rsp+70h+var_50], ebx
0x18001d4b9  mov     r9, rdi
0x18001d4bc  lea     r8, WPP_b75d7078c4363b03f2a23387d5361fbc_Traceguids
0x18001d4c3  mov     rcx, [rcx+10h]
0x18001d4c7  call    WPP_SF_qD
0x18001d4cc  jmp     loc_18001D376
0x18001d4d1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d4d8  jmp     short loc_18001D496
0x18001d4da  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001d4df  cmp     [rax+7CCh], ebx
0x18001d4e5  jz      short loc_18001D49C
0x18001d4e7  mov     r9d, ebx; int
0x18001d4ea  mov     r8d, 133h; int
0x18001d4f0  lea     rdx, aCstorebytestre_3; "CStoreByteStreamRegistrar::EnumerateSto"...
0x18001d4f7  mov     rcx, rax; this
0x18001d4fa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001d4ff  jmp     short loc_18001D49C
0x18001d501  xor     r9d, r9d; lpArguments
0x18001d504  xor     r8d, r8d; nNumberOfArguments
0x18001d507  lea     edx, [r9+1]; dwExceptionFlags
0x18001d50b  mov     ecx, eax; dwExceptionCode
0x18001d50d  call    cs:__imp_RaiseException
```
