# CLogonTaskFramework::s_ShouldLaunchTailoredScoobe(CLogonTaskFramework *,HSTRING__ * *)

- ea: `0x14001a5dc`
- end: `0x14001a83f`
- name: `?s_ShouldLaunchTailoredScoobe@CLogonTaskFramework@@CA_NPEAV1@PEAPEAUHSTRING__@@@Z`
- size: `611`
- prototype: `bool __fastcall(struct CLogonTaskFramework *, HSTRING *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14009d5c0`

## callees

- `0x140019308`
- `0x14001a5dc`
- `0x14002f838`
- `0x140082398`
- `0x1400a88a4`
- `0x1401040e0`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14001a655`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14001a75d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14001a655`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14001a75d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001a7ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001a7ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001a63f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001a747`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001a63f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001a747`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14001a66d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14001a66d`

## string_xrefs

- `0x14001a697`: `shell\lib\logontasks\logontasks.cpp`
- `0x14001a6dc`: `shell\lib\logontasks\logontasks.cpp`
- `0x14001a786`: `shell\lib\logontasks\logontasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
bool __fastcall CLogonTaskFramework::s_ShouldLaunchTailoredScoobe(struct CLogonTaskFramework *a1, HSTRING *a2)
{
  HRESULT v3; // eax
  int ActivationFactory; // eax
  __int64 v6; // rax
  int v7; // eax
  __int64 *v8; // rbx
  __int64 v9; // r14
  HRESULT v10; // eax
  int v11; // eax
  HSTRING v12; // rax
  int v13[2]; // [rsp+20h] [rbp-58h] BYREF
  __int64 *v14; // [rsp+28h] [rbp-50h] BYREF
  __int64 v15; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v16[2]; // [rsp+38h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-30h] BYREF
  HSTRING string; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v16[1] = a2;
  *a2 = 0;
  if ( (*((_DWORD *)a1 + 54) & 0x10330B) != 0 )
    return 0;
  v14 = 0;
  string = 0;
  v3 = WindowsCreateStringReference(
         L"Windows.Internal.System.UserProfile.ScoobeEligibility.ModalUserSetupEligibilityManager",
         0x56u,
         &hstringHeader,
         &string);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_84ae8f5d_1038_583c_b777_68136b1e903d, &v14);
  if ( ActivationFactory == -2147221164 )
  {
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v14);
    return 0;
  }
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14E0,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v13[0]);
  *(_QWORD *)v13 = 0;
  v6 = *v14;
  *(_QWORD *)v13 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, int *))(v6 + 48))(v14, v13);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14E2,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      (const char *)(unsigned int)v7,
      v13[0]);
  v8 = *(__int64 **)v13;
  if ( !*(_QWORD *)v13 )
  {
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(v13);
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v14);
    return 0;
  }
  v15 = 0;
  v9 = **(_QWORD **)v13;
  v15 = 0;
  string = 0;
  v10 = WindowsCreateStringReference(L"mz", 2u, &hstringHeader, &string);
  if ( v10 < 0 )
    RaiseException(v10, 1u, 0, 0);
  v11 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(v9 + 56))(v8, string, &v15);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14EB,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      (const char *)(unsigned int)v11,
      v13[0]);
  wil::wait_for_completion<HSTRING__ *,wil::details::MapToSmartType<HSTRING__ *,void>::HStringWithRelease>(v16, v15);
  v12 = (HSTRING)v16[0];
  v16[0] = 0;
  *a2 = v12;
  WindowsDeleteString(0);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  if ( *(_QWORD *)v13 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v13 + 16LL))(*(_QWORD *)v13);
  if ( v14 )
    (*(void (__fastcall **)(__int64 *))(*v14 + 16))(v14);
  return *a2 && !IsOnUserDesktop();
}

```

## disassembly

```asm
0x14001a5dc  mov     r11, rsp
0x14001a5df  mov     [r11+8], rbx
0x14001a5e3  mov     [r11+18h], rsi
0x14001a5e7  push    r14
0x14001a5e9  sub     rsp, 70h
0x14001a5ed  mov     rax, cs:__security_cookie
0x14001a5f4  xor     rax, rsp
0x14001a5f7  mov     [rsp+78h+var_10], rax
0x14001a5fc  mov     rsi, rdx
0x14001a5ff  mov     [rsp+78h+var_38], rdx
0x14001a604  mov     qword ptr [rdx], 0
0x14001a60b  test    dword ptr [rcx+0D8h], 10330Bh
0x14001a615  jnz     loc_14001A81C
0x14001a61b  mov     qword ptr [r11-50h], 0
0x14001a623  mov     qword ptr [r11-18h], 0
0x14001a62b  lea     r9, [r11-18h]; string
0x14001a62f  lea     r8, [r11-30h]; hstringHeader
0x14001a633  mov     edx, 56h ; 'V'; length
0x14001a638  lea     rcx, ?RuntimeClass_Windows_Internal_System_UserProfile_ScoobeEligibility_ModalUserSetupEligibilityManager@@3QBGB; "Windows.Internal.System.UserProfile.Sco"...
0x14001a63f  call    cs:__imp_WindowsCreateStringReference
0x14001a645  test    eax, eax
0x14001a647  jns     short loc_14001A65C
0x14001a649  xor     r9d, r9d; lpArguments
0x14001a64c  xor     r8d, r8d; nNumberOfArguments
0x14001a64f  lea     edx, [r9+1]; dwExceptionFlags
0x14001a653  mov     ecx, eax; dwExceptionCode
0x14001a655  call    cs:__imp_RaiseException
0x14001a65b  int     3; Trap to Debugger
0x14001a65c  lea     r8, [rsp+78h+var_50]
0x14001a661  lea     rdx, _GUID_84ae8f5d_1038_583c_b777_68136b1e903d
0x14001a668  mov     rcx, [rsp+78h+string]
0x14001a66d  call    cs:__imp_RoGetActivationFactory
0x14001a673  cmp     eax, 80040154h
0x14001a678  jnz     short loc_14001A68B
0x14001a67a  lea     rcx, [rsp+78h+var_50]
0x14001a67f  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x14001a684  xor     al, al
0x14001a686  jmp     loc_14001A81E
0x14001a68b  mov     rcx, [rsp+78h]; this
0x14001a690  test    eax, eax
0x14001a692  jns     short loc_14001A6A8
0x14001a694  mov     r9d, eax; char *
0x14001a697  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14001a69e  mov     edx, 14E0h; void *
0x14001a6a3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14001a6a8  mov     qword ptr [rsp+78h+var_58], 0
0x14001a6b1  mov     rcx, [rsp+78h+var_50]
0x14001a6b6  mov     rax, [rcx]
0x14001a6b9  mov     qword ptr [rsp+78h+var_58], 0; int
0x14001a6c2  lea     rdx, [rsp+78h+var_58]
0x14001a6c7  mov     rax, [rax+30h]
0x14001a6cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a6d0  mov     rcx, [rsp+78h]; this
0x14001a6d5  test    eax, eax
0x14001a6d7  jns     short loc_14001A6ED
0x14001a6d9  mov     r9d, eax; char *
0x14001a6dc  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14001a6e3  mov     edx, 14E2h; void *
0x14001a6e8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14001a6ed  mov     rbx, qword ptr [rsp+78h+var_58]
0x14001a6f2  test    rbx, rbx
0x14001a6f5  jnz     short loc_14001A713
0x14001a6f7  lea     rcx, [rsp+78h+var_58]
0x14001a6fc  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x14001a701  nop
0x14001a702  lea     rcx, [rsp+78h+var_50]
0x14001a707  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x14001a70c  xor     al, al
0x14001a70e  jmp     loc_14001A81E
0x14001a713  mov     [rsp+78h+var_48], 0
0x14001a71c  mov     r14, [rbx]
0x14001a71f  mov     [rsp+78h+var_48], 0
0x14001a728  mov     [rsp+78h+string], 0
0x14001a731  lea     r9, [rsp+78h+string]; string
0x14001a736  lea     r8, [rsp+78h+hstringHeader]; hstringHeader
0x14001a73b  mov     edx, 2; length
0x14001a740  lea     rcx, aMz; "mz"
0x14001a747  call    cs:__imp_WindowsCreateStringReference
0x14001a74d  test    eax, eax
0x14001a74f  jns     short loc_14001A764
0x14001a751  xor     r9d, r9d; lpArguments
0x14001a754  xor     r8d, r8d; nNumberOfArguments
0x14001a757  lea     edx, [r9+1]; dwExceptionFlags
0x14001a75b  mov     ecx, eax; dwExceptionCode
0x14001a75d  call    cs:__imp_RaiseException
0x14001a763  nop
0x14001a764  lea     r8, [rsp+78h+var_48]
0x14001a769  mov     rdx, [rsp+78h+string]
0x14001a76e  mov     rcx, rbx
0x14001a771  mov     rax, [r14+38h]
0x14001a775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a77a  mov     rcx, [rsp+78h]; this
0x14001a77f  test    eax, eax
0x14001a781  jns     short loc_14001A798
0x14001a783  mov     r9d, eax; char *
0x14001a786  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14001a78d  mov     edx, 14EBh; void *
0x14001a792  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14001a798  mov     rdx, [rsp+78h+var_48]
0x14001a79d  lea     rcx, [rsp+78h+var_40]
0x14001a7a2  call    ??$wait_for_completion@PEAUHSTRING__@@VHStringWithRelease@?$MapToSmartType@PEAUHSTRING__@@X@details@wil@@@wil@@YA?AVHStringWithRelease@?$MapToSmartType@PEAUHSTRING__@@X@details@0@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@@Z; wil::wait_for_completion<HSTRING__ *,wil::details::MapToSmartType<HSTRING__ *,void>::HStringWithRelease>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS)
0x14001a7a7  mov     rax, [rsp+78h+var_40]
0x14001a7ac  mov     [rsp+78h+var_40], 0
0x14001a7b5  mov     [rsi], rax
0x14001a7b8  xor     ecx, ecx; string
0x14001a7ba  call    cs:__imp_WindowsDeleteString
0x14001a7c0  nop
0x14001a7c1  mov     rcx, [rsp+78h+var_48]
0x14001a7c6  test    rcx, rcx
0x14001a7c9  jz      short loc_14001A7D8
0x14001a7cb  mov     rax, [rcx]
0x14001a7ce  mov     rax, [rax+10h]
0x14001a7d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a7d7  nop
0x14001a7d8  mov     rcx, qword ptr [rsp+78h+var_58]
0x14001a7dd  test    rcx, rcx
0x14001a7e0  jz      short loc_14001A7EF
0x14001a7e2  mov     rax, [rcx]
0x14001a7e5  mov     rax, [rax+10h]
0x14001a7e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a7ee  nop
0x14001a7ef  mov     rcx, [rsp+78h+var_50]
0x14001a7f4  test    rcx, rcx
0x14001a7f7  jz      short loc_14001A806
0x14001a7f9  mov     rax, [rcx]
0x14001a7fc  mov     rax, [rax+10h]
0x14001a800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a805  nop
0x14001a806  jmp     short loc_14001A80D
0x14001a808  mov     rsi, [rsp+78h+var_38]
0x14001a80d  cmp     qword ptr [rsi], 0
0x14001a811  jz      short loc_14001A81C
0x14001a813  call    ?IsOnUserDesktop@@YA_NXZ; IsOnUserDesktop(void)
0x14001a818  xor     al, 1
0x14001a81a  jmp     short loc_14001A81E
0x14001a81c  xor     al, al
0x14001a81e  mov     rcx, [rsp+78h+var_10]
0x14001a823  xor     rcx, rsp; StackCookie
0x14001a826  call    __security_check_cookie
0x14001a82b  lea     r11, [rsp+78h+var_8]
0x14001a830  mov     rbx, [r11+10h]
0x14001a834  mov     rsi, [r11+20h]
0x14001a838  mov     rsp, r11
0x14001a83b  pop     r14
0x14001a83d  retn
```
