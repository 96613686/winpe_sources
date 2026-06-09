# CMFInprocDllManager::LoadDllInternal(ushort const *,IInspectable * *)

- ea: `0x18003e9d0`
- end: `0x18003eeec`
- name: `?LoadDllInternal@CMFInprocDllManager@@QEAAJPEBGPEAPEAUIInspectable@@@Z`
- size: `1308`
- prototype: `int(CMFInprocDllManager *__hidden this, const unsigned __int16 *, struct IInspectable **)`
- caller_count: `3`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003e538`
- `0x1800bbc00`
- `0x1801530ac`

## callees

- `0x180004870`
- `0x180019124`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18003e9d0`
- `0x18003eef4`
- `0x18003ef40`
- `0x1801200d0`
- `0x1801250c8`
- `0x18014aa80`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ea65`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ea65`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003ead2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003ead2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ea05`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ea05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ebf0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ebf0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003eaaf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003eaaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eae5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ec9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eae5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ec9b`
- `RTWorkQ!RtwqCancelWorkItem` at `0x18003eedd`
- `RTWorkQ!RtwqCancelWorkItem` at `0x18003eedd`

## string_xrefs

- `0x18003ea0e`: `CMFInprocDllManager::LoadDllInternal`
- `0x18003ec81`: `CMFInprocDllManager::LoadDllInternal`
- `0x18003ed4c`: `CMFInprocDllManager::LoadDllInternal`
- `0x18003ede1`: `CMFInprocDllManager::LoadDllInternal`
- `0x18003ee72`: `CMFInprocDllManager::LoadDllInternal`
- `0x18003ea5b`: `DllGetActivationFactory`

## pseudocode

```c
__int64 __fastcall CMFInprocDllManager::LoadDllInternal(
        CMFInprocDllManager *this,
        const unsigned __int16 *a2,
        struct IInspectable **a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // r12
  char v7; // al
  RTWQWORKITEM_KEY v8; // rcx
  HMODULE v9; // rcx
  FARPROC ProcAddress; // rdi
  unsigned __int64 v11; // rbx
  const WCHAR *v12; // rax
  HMODULE Library; // rax
  signed int v14; // eax
  signed int v15; // ebx
  CallStackTracing *v16; // rcx
  __int64 v17; // rdx
  unsigned int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, struct IInspectable **); // rbx
  struct IInspectable *v21; // rcx
  __int64 v22; // rcx
  struct IInspectable *v23; // rcx
  struct CallStackContext *v25; // rax
  signed int LastError; // eax
  CallStackTracing *v27; // rcx
  struct CallStackContext *v28; // rax
  CallStackTracing *v29; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  CallStackTracing *v31; // rcx
  struct CallStackContext *v32; // rax
  __int64 v33; // rax
  CallStackScopeTrace v34; // [rsp+30h] [rbp-40h] BYREF
  struct IInspectable *v35; // [rsp+38h] [rbp-38h] BYREF
  __int64 v36; // [rsp+40h] [rbp-30h] BYREF
  Microsoft::WRL::Wrappers::HStringReference v37; // [rsp+48h] [rbp-28h] BYREF

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *a3 = 0;
  v35 = 0;
  v36 = 0;
  CallStackScopeTrace::CallStackScopeTrace(&v34, "CMFInprocDllManager::LoadDllInternal", 255);
  v7 = byte_1801FD289;
  if ( (unsigned __int8)byte_1801FD289 >= 0x10u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 29, &WPP_c9af1473a3d13c7b102f7fb7cc990054_Traceguids, this);
    v7 = byte_1801FD289;
  }
  if ( *((_QWORD *)this + 11) )
    goto LABEL_4;
  if ( (unsigned __int8)v7 >= 0x10u )
  {
    v33 = CMFBaseStringT<unsigned short>::PContents((char *)this + 64);
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      30,
      (unsigned int)&WPP_c9af1473a3d13c7b102f7fb7cc990054_Traceguids,
      (_DWORD)this,
      v33);
  }
  v12 = (const WCHAR *)CMFBaseStringT<unsigned short>::PContents((char *)this + 64);
  Library = LoadLibraryExW(v12, 0, 0x1100u);
  *((_QWORD *)this + 11) = Library;
  if ( Library )
  {
LABEL_4:
    v8 = *((_QWORD *)this + 12);
    if ( v8 )
    {
      RtwqCancelWorkItem(v8);
      *((_QWORD *)this + 12) = 0;
    }
    v9 = (HMODULE)*((_QWORD *)this + 11);
    ++*((_DWORD *)this + 26);
    ProcAddress = GetProcAddress(v9, "DllGetActivationFactory");
    if ( ProcAddress )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
      v11 = -1;
      v37.hstr_ = 0;
      do
        ++v11;
      while ( a2[v11] );
      if ( v11 > 0xFFFFFFFF )
      {
        RaiseException(0x80070216, 1u, 0, 0);
        __debugbreak();
      }
      v18 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v11);
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v37, a2, v18, v11);
      v15 = ((__int64 (__fastcall *)(HSTRING__ *, __int64 *))ProcAddress)(v37.hstr_, &v36);
      if ( v15 < 0 )
      {
        v29 = CallStackTracing::s_wpInstance;
        v37.hstr_ = 0;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v29 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v29 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v29->m_fEnabled )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v29);
          if ( ThreadRelativeContext->m_result != v15 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "CMFInprocDllManager::LoadDllInternal", 278, v15);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v17 = 33;
          goto LABEL_46;
        }
      }
      else
      {
        v19 = v36;
        v20 = *(__int64 (__fastcall **)(__int64, struct IInspectable **))(*(_QWORD *)v36 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
        v15 = v20(v19, &v35);
        if ( v15 < 0 )
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
            if ( v32->m_result != v15 )
              CallStackContext::TraceFailure(v32, "CMFInprocDllManager::LoadDllInternal", 279, v15);
          }
          if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          {
            v17 = 34;
            goto LABEL_46;
          }
        }
        else
        {
          v21 = v35;
          if ( v35 )
          {
            v35->AddRef(v35);
            v21 = v35;
          }
          *a3 = v21;
          v15 = 0;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v15 = LastError;
      if ( LastError > 0 )
        v15 = (unsigned __int16)LastError | 0x80070000;
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
        if ( v15 < 0 && v28->m_result != v15 )
          CallStackContext::TraceFailure(v28, "CMFInprocDllManager::LoadDllInternal", 276, v15);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v17 = 32;
        goto LABEL_46;
      }
    }
  }
  else
  {
    v14 = GetLastError();
    v15 = v14;
    if ( v14 > 0 )
      v15 = (unsigned __int16)v14 | 0x80070000;
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
      v25 = CallStackTracing::GetThreadRelativeContext(v16);
      if ( v15 < 0 && v25->m_result != v15 )
        CallStackContext::TraceFailure(v25, "CMFInprocDllManager::LoadDllInternal", 261, v15);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v17 = 31;
LABEL_46:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_c9af1473a3d13c7b102f7fb7cc990054_Traceguids, this, v15);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace(&v34);
  v22 = v36;
  if ( v36 )
  {
    v36 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  v23 = v35;
  if ( v35 )
  {
    v35 = 0;
    v23->Release(v23);
  }
  if ( v3 )
    LeaveCriticalSection(v3);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18003e9d0  mov     [rsp-38h+arg_18], rbx
0x18003e9d5  push    rbp
0x18003e9d6  push    rsi
0x18003e9d7  push    rdi
0x18003e9d8  push    r12
0x18003e9da  push    r13
0x18003e9dc  push    r14
0x18003e9de  push    r15
0x18003e9e0  mov     rbp, rsp
0x18003e9e3  sub     rsp, 70h
0x18003e9e7  mov     rax, cs:__security_cookie
0x18003e9ee  xor     rax, rsp
0x18003e9f1  mov     [rbp+var_8], rax
0x18003e9f5  lea     r12, [rcx+10h]
0x18003e9f9  mov     rsi, rcx
0x18003e9fc  mov     rcx, r12; lpCriticalSection
0x18003e9ff  mov     r14, r8
0x18003ea02  mov     r15, rdx
0x18003ea05  call    cs:__imp_EnterCriticalSection
0x18003ea0b  xor     r13d, r13d
0x18003ea0e  lea     rdx, aCmfinprocdllma_2; "CMFInprocDllManager::LoadDllInternal"
0x18003ea15  mov     r8d, 0FFh; int
0x18003ea1b  mov     [r14], r13
0x18003ea1e  lea     rcx, [rbp+var_40]; this
0x18003ea22  mov     [rbp+var_38], r13
0x18003ea26  mov     [rbp+var_30], r13
0x18003ea2a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003ea2f  mov     al, cs:byte_1801FD289
0x18003ea35  lea     rdi, WPP_c9af1473a3d13c7b102f7fb7cc990054_Traceguids
0x18003ea3c  cmp     al, 10h
0x18003ea3e  jnb     loc_18003EE89
0x18003ea44  cmp     [rsi+58h], r13
0x18003ea48  jz      short loc_18003EAB6
0x18003ea4a  mov     rcx, [rsi+60h]; Key
0x18003ea4e  test    rcx, rcx
0x18003ea51  jnz     loc_18003EEDD
0x18003ea57  mov     rcx, [rsi+58h]; hModule
0x18003ea5b  lea     rdx, ProcName; "DllGetActivationFactory"
0x18003ea62  inc     dword ptr [rsi+68h]
0x18003ea65  call    cs:__imp_GetProcAddress
0x18003ea6b  mov     rdi, rax
0x18003ea6e  test    rax, rax
0x18003ea71  jz      loc_18003EC9B
0x18003ea77  lea     rcx, [rbp+var_30]
0x18003ea7b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003ea80  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003ea84  mov     [rbp+var_28.hstr_], r13
0x18003ea88  inc     rbx
0x18003ea8b  cmp     [r15+rbx*2], r13w
0x18003ea90  jnz     short loc_18003EA88
0x18003ea92  mov     eax, 0FFFFFFFFh
0x18003ea97  cmp     rbx, rax
0x18003ea9a  jbe     loc_18003EB2E
0x18003eaa0  xor     r9d, r9d; lpArguments
0x18003eaa3  xor     r8d, r8d; nNumberOfArguments
0x18003eaa6  mov     ecx, 80070216h; dwExceptionCode
0x18003eaab  lea     edx, [r9+1]; dwExceptionFlags
0x18003eaaf  call    cs:__imp_RaiseException
0x18003eab5  int     3; Trap to Debugger
0x18003eab6  cmp     al, 10h
0x18003eab8  jnb     loc_18003EEAF
0x18003eabe  lea     rcx, [rsi+40h]
0x18003eac2  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x18003eac7  mov     rcx, rax; lpLibFileName
0x18003eaca  xor     edx, edx; hFile
0x18003eacc  mov     r8d, 1100h; dwFlags
0x18003ead2  call    cs:__imp_LoadLibraryExW
0x18003ead8  mov     [rsi+58h], rax
0x18003eadc  test    rax, rax
0x18003eadf  jnz     loc_18003EA4A
0x18003eae5  call    cs:__imp_GetLastError
0x18003eaeb  mov     ebx, eax
0x18003eaed  test    eax, eax
0x18003eaef  jle     short loc_18003EAFA
0x18003eaf1  movzx   ebx, ax
0x18003eaf4  or      ebx, 80070000h
0x18003eafa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003eb01  test    rcx, rcx
0x18003eb04  jz      loc_18003EC1C
0x18003eb0a  cmp     [rcx+8], r13b
0x18003eb0e  jnz     loc_18003EC65
0x18003eb14  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003eb1b  jb      loc_18003EBAD
0x18003eb21  mov     edx, 1Fh
0x18003eb26  mov     r8, rdi
0x18003eb29  jmp     loc_18003ED13
0x18003eb2e  mov     ecx, ebx; unsigned int
0x18003eb30  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18003eb35  mov     r9d, ebx; unsigned int
0x18003eb38  lea     rcx, [rbp+var_28]; this
0x18003eb3c  mov     r8d, eax; unsigned int
0x18003eb3f  mov     rdx, r15; sourceString
0x18003eb42  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003eb47  mov     rcx, [rbp+var_28.hstr_]
0x18003eb4b  lea     rdx, [rbp+var_30]
0x18003eb4f  mov     rax, rdi
0x18003eb52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eb57  mov     ebx, eax
0x18003eb59  test    eax, eax
0x18003eb5b  js      loc_18003ED63
0x18003eb61  mov     rdi, [rbp+var_30]
0x18003eb65  lea     rcx, [rbp+var_38]
0x18003eb69  mov     rax, [rdi]
0x18003eb6c  mov     rbx, [rax+30h]
0x18003eb70  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003eb75  lea     rdx, [rbp+var_38]
0x18003eb79  mov     rcx, rdi
0x18003eb7c  mov     rax, rbx
0x18003eb7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eb84  mov     ebx, eax
0x18003eb86  test    eax, eax
0x18003eb88  js      loc_18003EDF8
0x18003eb8e  mov     rcx, [rbp+var_38]
0x18003eb92  test    rcx, rcx
0x18003eb95  jz      short loc_18003EBA7
0x18003eb97  mov     rax, [rcx]
0x18003eb9a  mov     rax, [rax+8]
0x18003eb9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eba3  mov     rcx, [rbp+var_38]
0x18003eba7  mov     [r14], rcx
0x18003ebaa  mov     ebx, r13d
0x18003ebad  lea     rcx, [rbp+var_40]; this
0x18003ebb1  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003ebb6  mov     rcx, [rbp+var_30]
0x18003ebba  test    rcx, rcx
0x18003ebbd  jz      short loc_18003EBCF
0x18003ebbf  mov     [rbp+var_30], r13
0x18003ebc3  mov     rax, [rcx]
0x18003ebc6  mov     rax, [rax+10h]
0x18003ebca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ebcf  mov     rcx, [rbp+var_38]
0x18003ebd3  test    rcx, rcx
0x18003ebd6  jz      short loc_18003EBE8
0x18003ebd8  mov     [rbp+var_38], r13
0x18003ebdc  mov     rax, [rcx]
0x18003ebdf  mov     rax, [rax+10h]
0x18003ebe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ebe8  test    r12, r12
0x18003ebeb  jz      short loc_18003EBF6
0x18003ebed  mov     rcx, r12; lpCriticalSection
0x18003ebf0  call    cs:__imp_LeaveCriticalSection
0x18003ebf6  mov     eax, ebx
0x18003ebf8  mov     rcx, [rbp+var_8]
0x18003ebfc  xor     rcx, rsp; StackCookie
0x18003ebff  call    __security_check_cookie
0x18003ec04  mov     rbx, [rsp+70h+arg_18]
0x18003ec0c  add     rsp, 70h
0x18003ec10  pop     r15
0x18003ec12  pop     r14
0x18003ec14  pop     r13
0x18003ec16  pop     r12
0x18003ec18  pop     rdi
0x18003ec19  pop     rsi
0x18003ec1a  pop     rbp
0x18003ec1b  retn
0x18003ec1c  mov     rax, cs:stru_1801FC290.__vftable
0x18003ec23  lea     r8, stru_1801FC290
0x18003ec2a  mov     edx, 7F0h
0x18003ec2f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ec36  mov     rcx, r8
0x18003ec39  mov     rax, [rax+8]
0x18003ec3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ec42  test    eax, eax
0x18003ec44  jnz     short loc_18003EC59
0x18003ec46  lea     rcx, stru_1801F8A30
0x18003ec4d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ec54  jmp     loc_18003EB0A
0x18003ec59  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ec60  jmp     loc_18003EB0A
0x18003ec65  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003ec6a  test    ebx, ebx
0x18003ec6c  jns     loc_18003EB14
0x18003ec72  cmp     [rax+7CCh], ebx
0x18003ec78  jz      loc_18003EB14
0x18003ec7e  mov     r9d, ebx; int
0x18003ec81  lea     rdx, aCmfinprocdllma_2; "CMFInprocDllManager::LoadDllInternal"
0x18003ec88  mov     r8d, 105h; int
0x18003ec8e  mov     rcx, rax; this
0x18003ec91  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003ec96  jmp     loc_18003EB14
0x18003ec9b  call    cs:__imp_GetLastError
0x18003eca1  mov     ebx, eax
0x18003eca3  test    eax, eax
0x18003eca5  jle     short loc_18003ECB0
0x18003eca7  movzx   ebx, ax
0x18003ecaa  or      ebx, 80070000h
0x18003ecb0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ecb7  test    rcx, rcx
0x18003ecba  jnz     short loc_18003ECF4
0x18003ecbc  mov     rax, cs:stru_1801FC290.__vftable
0x18003ecc3  lea     r8, stru_1801FC290
0x18003ecca  mov     edx, 7F0h
0x18003eccf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ecd6  mov     rcx, r8
0x18003ecd9  mov     rax, [rax+8]
0x18003ecdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ece2  test    eax, eax
0x18003ece4  jnz     short loc_18003ED2F
0x18003ece6  lea     rcx, stru_1801F8A30; this
0x18003eced  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ecf4  cmp     [rcx+8], r13b
0x18003ecf8  jnz     short loc_18003ED38
0x18003ecfa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ed01  jb      loc_18003EBAD
0x18003ed07  mov     edx, 20h ; ' '
0x18003ed0c  lea     r8, WPP_c9af1473a3d13c7b102f7fb7cc990054_Traceguids
0x18003ed13  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ed1a  mov     r9, rsi
0x18003ed1d  mov     dword ptr [rsp+70h+var_50], ebx
0x18003ed21  mov     rcx, [rcx+10h]
0x18003ed25  call    WPP_SF_qD
0x18003ed2a  jmp     loc_18003EBAD
0x18003ed2f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ed36  jmp     short loc_18003ECF4
0x18003ed38  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003ed3d  test    ebx, ebx
0x18003ed3f  jns     short loc_18003ECFA
0x18003ed41  cmp     [rax+7CCh], ebx
0x18003ed47  jz      short loc_18003ECFA
0x18003ed49  mov     r9d, ebx; int
0x18003ed4c  lea     rdx, aCmfinprocdllma_2; "CMFInprocDllManager::LoadDllInternal"
0x18003ed53  mov     r8d, 114h; int
0x18003ed59  mov     rcx, rax; this
0x18003ed5c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003ed61  jmp     short loc_18003ECFA
0x18003ed63  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ed6a  mov     [rbp+var_28.hstr_], r13
0x18003ed6e  test    rcx, rcx
0x18003ed71  jnz     short loc_18003EDAB
0x18003ed73  mov     rcx, cs:stru_1801FC290.__vftable
0x18003ed7a  lea     r8, stru_1801FC290
0x18003ed81  mov     edx, 7F0h
0x18003ed86  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ed8d  mov     rax, [rcx+8]
0x18003ed91  mov     rcx, r8
0x18003ed94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ed99  test    eax, eax
0x18003ed9b  jnz     short loc_18003EDC8
0x18003ed9d  lea     rcx, stru_1801F8A30; this
0x18003eda4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003edab  cmp     [rcx+8], r13b
0x18003edaf  jnz     short loc_18003EDD1
0x18003edb1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003edb8  jb      loc_18003EBAD
0x18003edbe  mov     edx, 21h ; '!'
0x18003edc3  jmp     loc_18003ED0C
0x18003edc8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003edcf  jmp     short loc_18003EDAB
0x18003edd1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003edd6  cmp     [rax+7CCh], ebx
0x18003eddc  jz      short loc_18003EDB1
0x18003edde  mov     r9d, ebx; int
0x18003ede1  lea     rdx, aCmfinprocdllma_2; "CMFInprocDllManager::LoadDllInternal"
0x18003ede8  mov     r8d, 116h; int
0x18003edee  mov     rcx, rax; this
0x18003edf1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003edf6  jmp     short loc_18003EDB1
0x18003edf8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003edff  test    rcx, rcx
0x18003ee02  jnz     short loc_18003EE3C
0x18003ee04  mov     rax, cs:stru_1801FC290.__vftable
0x18003ee0b  lea     r8, stru_1801FC290
0x18003ee12  mov     edx, 7F0h
0x18003ee17  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ee1e  mov     rcx, r8
0x18003ee21  mov     rax, [rax+8]
0x18003ee25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ee2a  test    eax, eax
0x18003ee2c  jnz     short loc_18003EE59
0x18003ee2e  lea     rcx, stru_1801F8A30; this
0x18003ee35  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ee3c  cmp     [rcx+8], r13b
0x18003ee40  jnz     short loc_18003EE62
0x18003ee42  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ee49  jb      loc_18003EBAD
0x18003ee4f  mov     edx, 22h ; '"'
0x18003ee54  jmp     loc_18003ED0C
0x18003ee59  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ee60  jmp     short loc_18003EE3C
0x18003ee62  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003ee67  cmp     [rax+7CCh], ebx
0x18003ee6d  jz      short loc_18003EE42
0x18003ee6f  mov     r9d, ebx; int
0x18003ee72  lea     rdx, aCmfinprocdllma_2; "CMFInprocDllManager::LoadDllInternal"
0x18003ee79  mov     r8d, 117h; int
0x18003ee7f  mov     rcx, rax; this
0x18003ee82  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003ee87  jmp     short loc_18003EE42
0x18003ee89  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ee90  mov     edx, 1Dh
0x18003ee95  mov     r9, rsi
0x18003ee98  mov     r8, rdi
0x18003ee9b  mov     rcx, [rcx+38h]
0x18003ee9f  call    WPP_SF_q
0x18003eea4  mov     al, cs:byte_1801FD289
0x18003eeaa  jmp     loc_18003EA44
0x18003eeaf  lea     rcx, [rsi+40h]
0x18003eeb3  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x18003eeb8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003eebf  mov     edx, 1Eh
  ... truncated ...
```
