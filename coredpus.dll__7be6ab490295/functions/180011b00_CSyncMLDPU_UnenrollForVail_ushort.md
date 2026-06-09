# CSyncMLDPU::UnenrollForVail(ushort *)

- ea: `0x180011b00`
- end: `0x180011d66`
- name: `?UnenrollForVail@CSyncMLDPU@@UEAAJPEAG@Z`
- size: `614`
- prototype: `__int64 __fastcall(CSyncMLDPU *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ccf0`

## callees

- `0x180011b00`
- `0x180011d6c`
- `0x180011d9c`
- `0x1800128e4`
- `0x180014330`
- `0x180016948`
- `0x1800174b8`
- `0x18001bc9c`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011b2e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011b2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011bbe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011d37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011bbe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011d37`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011b73`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011b73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180011b54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180011b54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011c7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011d0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011c7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011d0a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180011b83`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180011b83`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180011c05`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180011d23`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180011c05`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180011d23`

## pseudocode

```c
__int64 __fastcall CSyncMLDPU::UnenrollForVail(CSyncMLDPU *this, unsigned __int16 *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // r14
  HRESULT v4; // eax
  int v5; // ebx
  int v7; // eax
  unsigned __int64 v8; // rcx
  unsigned int v9; // r8d
  const unsigned __int16 *v10; // rdx
  __int64 v11; // rsi
  HSTRING v12; // rbx
  __int64 (__fastcall *v13)(__int64, HSTRING, __int64 *); // rdi
  __int64 v14; // rdx
  HSTRING v15; // [rsp+20h] [rbp-50h] BYREF
  __int64 v16; // [rsp+28h] [rbp-48h] BYREF
  __int64 v17; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v18; // [rsp+38h] [rbp-38h] BYREF
  HSTRING string; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 472);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 472));
  v16 = 0;
  if ( WindowsCreateStringReference(L"Windows.Internal.Management.Enrollment.Enroller", 0x2Fu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v4 = CoInitializeEx(0, 0);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A4,
      (unsigned int)"onecoreuap\\admin\\dm\\coredpus\\syncmldpu\\syncmldpu.cpp",
      (const char *)(unsigned int)v4,
      (int)v15);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
LABEL_5:
    if ( v2 )
      LeaveCriticalSection(v2);
    return (unsigned int)v5;
  }
  v7 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>(
         string,
         &v16);
  v5 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A5,
      (unsigned int)"onecoreuap\\admin\\dm\\coredpus\\syncmldpu\\syncmldpu.cpp",
      (const char *)(unsigned int)v7,
      (int)v15);
LABEL_10:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
    CoUninitialize();
    goto LABEL_5;
  }
  v15 = 0;
  if ( a2 )
  {
    v18 = 0;
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
    v5 = ULongLongToULong(v8, &v18);
    if ( v5 < 0 )
      goto LABEL_18;
    v9 = v18;
    v10 = a2;
  }
  else
  {
    v9 = 0;
    v10 = &word_180032B28;
  }
  v5 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&v15, v10, v9);
  if ( v5 < 0 )
  {
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A8,
      (unsigned int)"onecoreuap\\admin\\dm\\coredpus\\syncmldpu\\syncmldpu.cpp",
      (const char *)(unsigned int)v5,
      (int)v15);
LABEL_19:
    WindowsDeleteString(v15);
    v15 = 0;
    goto LABEL_10;
  }
  v11 = v16;
  v12 = v15;
  v17 = 0;
  v13 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v16 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  v5 = v13(v11, v12, &v17);
  if ( v5 < 0 )
  {
    v14 = 942;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\admin\\dm\\coredpus\\syncmldpu\\syncmldpu.cpp",
      (const char *)(unsigned int)v5,
      (int)v15);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
    goto LABEL_19;
  }
  v5 = WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(v17);
  if ( v5 < 0 )
  {
    v14 = 943;
    goto LABEL_22;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  WindowsDeleteString(v15);
  v15 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
  CoUninitialize();
  if ( v2 )
    LeaveCriticalSection(v2);
  return 0;
}

```

## disassembly

```asm
0x180011b00  mov     [rsp-28h+arg_10], rbx
0x180011b05  push    rbp
0x180011b06  push    rsi
0x180011b07  push    rdi
0x180011b08  push    r14
0x180011b0a  push    r15
0x180011b0c  mov     rbp, rsp
0x180011b0f  sub     rsp, 70h
0x180011b13  mov     rax, cs:__security_cookie
0x180011b1a  xor     rax, rsp
0x180011b1d  mov     [rbp+var_10], rax
0x180011b21  lea     r14, [rcx+1D8h]
0x180011b28  mov     rdi, rdx
0x180011b2b  mov     rcx, r14; lpCriticalSection
0x180011b2e  call    cs:__imp_EnterCriticalSection
0x180011b35  nop     dword ptr [rax+rax+00h]
0x180011b3a  xor     r15d, r15d
0x180011b3d  lea     r9, [rbp+string]; string
0x180011b41  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180011b45  mov     [rbp+var_48], r15
0x180011b49  lea     rcx, ?RuntimeClass_Windows_Internal_Management_Enrollment_Enroller@@3QBGB; "Windows.Internal.Management.Enrollment."...
0x180011b50  lea     edx, [r15+2Fh]; length
0x180011b54  call    cs:__imp_WindowsCreateStringReference
0x180011b5b  nop     dword ptr [rax+rax+00h]
0x180011b60  test    eax, eax
0x180011b62  jns     short loc_180011B7F
0x180011b64  xor     r9d, r9d; lpArguments
0x180011b67  lea     edx, [r15+1]; dwExceptionFlags
0x180011b6b  xor     r8d, r8d; nNumberOfArguments
0x180011b6e  mov     ecx, 0C000000Dh; dwExceptionCode
0x180011b73  call    cs:__imp_RaiseException
0x180011b7a  nop     dword ptr [rax+rax+00h]
0x180011b7f  xor     edx, edx; dwCoInit
0x180011b81  xor     ecx, ecx; pvReserved
0x180011b83  call    cs:__imp_CoInitializeEx
0x180011b8a  nop     dword ptr [rax+rax+00h]
0x180011b8f  mov     ebx, eax
0x180011b91  test    eax, eax
0x180011b93  jns     short loc_180011BD1
0x180011b95  mov     rcx, [rbp+28h]; this
0x180011b99  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\coredpus\\syncml"...
0x180011ba0  mov     r9d, eax; char *
0x180011ba3  mov     edx, 3A4h; void *
0x180011ba8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011bad  lea     rcx, [rbp+var_48]
0x180011bb1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011bb6  test    r14, r14
0x180011bb9  jz      short loc_180011BCA
0x180011bbb  mov     rcx, r14; lpCriticalSection
0x180011bbe  call    cs:__imp_LeaveCriticalSection
0x180011bc5  nop     dword ptr [rax+rax+00h]
0x180011bca  mov     eax, ebx
0x180011bcc  jmp     loc_180011D45
0x180011bd1  mov     rcx, [rbp+string]
0x180011bd5  lea     rdx, [rbp+var_48]
0x180011bd9  call    ??$ActivateInstance@V?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>)
0x180011bde  mov     ebx, eax
0x180011be0  test    eax, eax
0x180011be2  jns     short loc_180011C13
0x180011be4  mov     rcx, [rbp+28h]; this
0x180011be8  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\coredpus\\syncml"...
0x180011bef  mov     r9d, eax; char *
0x180011bf2  mov     edx, 3A5h; void *
0x180011bf7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011bfc  lea     rcx, [rbp+var_48]
0x180011c00  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011c05  call    cs:__imp_CoUninitialize
0x180011c0c  nop     dword ptr [rax+rax+00h]
0x180011c11  jmp     short loc_180011BB6
0x180011c13  mov     [rbp+var_50], r15
0x180011c17  test    rdi, rdi
0x180011c1a  jz      short loc_180011C46
0x180011c1c  mov     [rbp+var_38], r15d
0x180011c20  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180011c24  inc     rcx; unsigned __int64
0x180011c27  cmp     [rdi+rcx*2], r15w
0x180011c2c  jnz     short loc_180011C24
0x180011c2e  lea     rdx, [rbp+var_38]; unsigned int *
0x180011c32  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180011c37  mov     ebx, eax
0x180011c39  test    eax, eax
0x180011c3b  js      short loc_180011C5F
0x180011c3d  mov     r8d, [rbp+var_38]
0x180011c41  mov     rdx, rdi
0x180011c44  jmp     short loc_180011C50
0x180011c46  xor     r8d, r8d; unsigned int
0x180011c49  lea     rdx, word_180032B28; unsigned __int16 *
0x180011c50  lea     rcx, [rbp+var_50]; this
0x180011c54  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180011c59  mov     ebx, eax
0x180011c5b  test    eax, eax
0x180011c5d  jns     short loc_180011C90
0x180011c5f  mov     rcx, [rbp+28h]; this
0x180011c63  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\coredpus\\syncml"...
0x180011c6a  mov     r9d, ebx; char *
0x180011c6d  mov     edx, 3A8h; void *
0x180011c72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011c77  mov     rcx, [rbp+var_50]; string
0x180011c7b  call    cs:__imp_WindowsDeleteString
0x180011c82  nop     dword ptr [rax+rax+00h]
0x180011c87  mov     [rbp+var_50], r15
0x180011c8b  jmp     loc_180011BFC
0x180011c90  mov     rsi, [rbp+var_48]
0x180011c94  lea     rcx, [rbp+var_40]
0x180011c98  mov     rbx, [rbp+var_50]
0x180011c9c  mov     [rbp+var_40], r15
0x180011ca0  mov     rax, [rsi]
0x180011ca3  mov     rdi, [rax+30h]
0x180011ca7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011cac  lea     r8, [rbp+var_40]
0x180011cb0  mov     rdx, rbx
0x180011cb3  mov     rcx, rsi
0x180011cb6  mov     rax, rdi
0x180011cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cbe  mov     ebx, eax
0x180011cc0  test    eax, eax
0x180011cc2  jns     short loc_180011CE7
0x180011cc4  mov     edx, 3AEh; void *
0x180011cc9  mov     rcx, [rbp+28h]; this
0x180011ccd  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\coredpus\\syncml"...
0x180011cd4  mov     r9d, ebx; char *
0x180011cd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011cdc  lea     rcx, [rbp+var_40]
0x180011ce0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011ce5  jmp     short loc_180011C77
0x180011ce7  mov     rcx, [rbp+var_40]
0x180011ceb  call    ??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)
0x180011cf0  mov     ebx, eax
0x180011cf2  test    eax, eax
0x180011cf4  jns     short loc_180011CFD
0x180011cf6  mov     edx, 3AFh
0x180011cfb  jmp     short loc_180011CC9
0x180011cfd  lea     rcx, [rbp+var_40]
0x180011d01  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011d06  mov     rcx, [rbp+var_50]; string
0x180011d0a  call    cs:__imp_WindowsDeleteString
0x180011d11  nop     dword ptr [rax+rax+00h]
0x180011d16  lea     rcx, [rbp+var_48]
0x180011d1a  mov     [rbp+var_50], r15
0x180011d1e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011d23  call    cs:__imp_CoUninitialize
0x180011d2a  nop     dword ptr [rax+rax+00h]
0x180011d2f  test    r14, r14
0x180011d32  jz      short loc_180011D43
0x180011d34  mov     rcx, r14; lpCriticalSection
0x180011d37  call    cs:__imp_LeaveCriticalSection
0x180011d3e  nop     dword ptr [rax+rax+00h]
0x180011d43  xor     eax, eax
0x180011d45  mov     rcx, [rbp+var_10]
0x180011d49  xor     rcx, rsp; StackCookie
0x180011d4c  call    __security_check_cookie
0x180011d51  mov     rbx, [rsp+70h+arg_10]
0x180011d59  add     rsp, 70h
0x180011d5d  pop     r15
0x180011d5f  pop     r14
0x180011d61  pop     rdi
0x180011d62  pop     rsi
0x180011d63  pop     rbp
0x180011d64  retn
```
