# CLogonTaskFramework::s_ShouldLaunchTailoredScoobe(CLogonTaskFramework *,HSTRING__ * *)

- ea: `0x140006244`
- end: `0x1400064a9`
- name: `?s_ShouldLaunchTailoredScoobe@CLogonTaskFramework@@CA_NPEAV1@PEAPEAUHSTRING__@@@Z`
- size: `613`
- prototype: `bool __fastcall(struct CLogonTaskFramework *, HSTRING *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400a08d0`

## callees

- `0x140005aa8`
- `0x140005e14`
- `0x140006244`
- `0x140006edc`
- `0x1400ae8b0`
- `0x1400baca0`
- `0x14010e160`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000641e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000641e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400062a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400063b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400062a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400063b0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400062d0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400062d0`

## string_xrefs

- `0x140006300`: `shell\lib\logontasks\logontasks.cpp`
- `0x140006345`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400063ea`: `shell\lib\logontasks\logontasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
bool __fastcall CLogonTaskFramework::s_ShouldLaunchTailoredScoobe(struct CLogonTaskFramework *a1, HSTRING *a2)
{
  HRESULT v3; // eax
  int v4; // edx
  unsigned int v5; // r8d
  int ActivationFactory; // eax
  __int64 v8; // rax
  int v9; // eax
  __int64 *v10; // rbx
  __int64 v11; // r14
  HRESULT v12; // eax
  int v13; // edx
  unsigned int v14; // r8d
  int v15; // eax
  HSTRING v16; // rax
  int v17[2]; // [rsp+20h] [rbp-58h] BYREF
  __int64 *v18; // [rsp+28h] [rbp-50h] BYREF
  __int64 v19; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v20[2]; // [rsp+38h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-30h] BYREF
  HSTRING string; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v20[1] = a2;
  *a2 = 0;
  if ( (*((_DWORD *)a1 + 54) & 0x10330B) != 0 )
    return 0;
  v18 = 0;
  string = 0;
  v3 = WindowsCreateStringReference(
         L"Windows.Internal.System.UserProfile.ScoobeEligibility.ModalUserSetupEligibilityManager",
         0x56u,
         &hstringHeader,
         &string);
  if ( v3 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v3, v4, v5);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_84ae8f5d_1038_583c_b777_68136b1e903d, &v18);
  if ( ActivationFactory == -2147221164 )
  {
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v18);
    return 0;
  }
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14D9,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v17[0]);
  *(_QWORD *)v17 = 0;
  v8 = *v18;
  *(_QWORD *)v17 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, int *))(v8 + 48))(v18, v17);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14DB,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      (const char *)(unsigned int)v9,
      v17[0]);
  v10 = *(__int64 **)v17;
  if ( !*(_QWORD *)v17 )
  {
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(v17);
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v18);
    return 0;
  }
  v19 = 0;
  v11 = **(_QWORD **)v17;
  v19 = 0;
  string = 0;
  v12 = WindowsCreateStringReference(L"mz", 2u, &hstringHeader, &string);
  if ( v12 < 0 )
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v12, v13, v14);
  v15 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(v11 + 56))(v10, string, &v19);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14E4,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      (const char *)(unsigned int)v15,
      v17[0]);
  wil::wait_for_completion<HSTRING__ *,wil::details::MapToSmartType<HSTRING__ *,void>::HStringWithRelease>(v20, v19);
  v16 = (HSTRING)v20[0];
  v20[0] = 0;
  *a2 = v16;
  WindowsDeleteString(0);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( *(_QWORD *)v17 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v17 + 16LL))(*(_QWORD *)v17);
  if ( v18 )
    (*(void (__fastcall **)(__int64 *))(*v18 + 16))(v18);
  return *a2 && !IsOnUserDesktop();
}

```

## disassembly

```asm
0x140006244  mov     r11, rsp
0x140006247  mov     [r11+8], rbx
0x14000624b  mov     [r11+18h], rsi
0x14000624f  push    r14
0x140006251  sub     rsp, 70h
0x140006255  mov     rax, cs:__security_cookie
0x14000625c  xor     rax, rsp
0x14000625f  mov     [rsp+78h+var_10], rax
0x140006264  mov     rsi, rdx
0x140006267  mov     [rsp+78h+var_38], rdx
0x14000626c  mov     qword ptr [rdx], 0
0x140006273  test    dword ptr [rcx+0D8h], 10330Bh
0x14000627d  jnz     loc_140006486
0x140006283  mov     qword ptr [r11-50h], 0
0x14000628b  mov     qword ptr [r11-18h], 0
0x140006293  lea     r9, [r11-18h]; string
0x140006297  lea     r8, [r11-30h]; hstringHeader
0x14000629b  mov     edx, 56h ; 'V'; length
0x1400062a0  lea     rcx, ?RuntimeClass_Windows_Internal_System_UserProfile_ScoobeEligibility_ModalUserSetupEligibilityManager@@3QBGB; "Windows.Internal.System.UserProfile.Sco"...
0x1400062a7  call    cs:__imp_WindowsCreateStringReference
0x1400062ae  nop     dword ptr [rax+rax+00h]
0x1400062b3  test    eax, eax
0x1400062b5  jns     short loc_1400062BF
0x1400062b7  mov     ecx, eax; this
0x1400062b9  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1400062be  int     3; Trap to Debugger
0x1400062bf  lea     r8, [rsp+78h+var_50]
0x1400062c4  lea     rdx, _GUID_84ae8f5d_1038_583c_b777_68136b1e903d
0x1400062cb  mov     rcx, [rsp+78h+string]
0x1400062d0  call    cs:__imp_RoGetActivationFactory
0x1400062d7  nop     dword ptr [rax+rax+00h]
0x1400062dc  cmp     eax, 80040154h
0x1400062e1  jnz     short loc_1400062F4
0x1400062e3  lea     rcx, [rsp+78h+var_50]
0x1400062e8  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1400062ed  xor     al, al
0x1400062ef  jmp     loc_140006488
0x1400062f4  mov     rcx, [rsp+78h]; this
0x1400062f9  test    eax, eax
0x1400062fb  jns     short loc_140006311
0x1400062fd  mov     r9d, eax; char *
0x140006300  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x140006307  mov     edx, 14D9h; void *
0x14000630c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140006311  mov     qword ptr [rsp+78h+var_58], 0
0x14000631a  mov     rcx, [rsp+78h+var_50]
0x14000631f  mov     rax, [rcx]
0x140006322  mov     qword ptr [rsp+78h+var_58], 0; int
0x14000632b  lea     rdx, [rsp+78h+var_58]
0x140006330  mov     rax, [rax+30h]
0x140006334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006339  mov     rcx, [rsp+78h]; this
0x14000633e  test    eax, eax
0x140006340  jns     short loc_140006356
0x140006342  mov     r9d, eax; char *
0x140006345  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14000634c  mov     edx, 14DBh; void *
0x140006351  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140006356  mov     rbx, qword ptr [rsp+78h+var_58]
0x14000635b  test    rbx, rbx
0x14000635e  jnz     short loc_14000637C
0x140006360  lea     rcx, [rsp+78h+var_58]
0x140006365  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x14000636a  nop
0x14000636b  lea     rcx, [rsp+78h+var_50]
0x140006370  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x140006375  xor     al, al
0x140006377  jmp     loc_140006488
0x14000637c  mov     [rsp+78h+var_48], 0
0x140006385  mov     r14, [rbx]
0x140006388  mov     [rsp+78h+var_48], 0
0x140006391  mov     [rsp+78h+string], 0
0x14000639a  lea     r9, [rsp+78h+string]; string
0x14000639f  lea     r8, [rsp+78h+hstringHeader]; hstringHeader
0x1400063a4  mov     edx, 2; length
0x1400063a9  lea     rcx, sourceString; "mz"
0x1400063b0  call    cs:__imp_WindowsCreateStringReference
0x1400063b7  nop     dword ptr [rax+rax+00h]
0x1400063bc  test    eax, eax
0x1400063be  jns     short loc_1400063C8
0x1400063c0  mov     ecx, eax; this
0x1400063c2  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1400063c7  nop
0x1400063c8  lea     r8, [rsp+78h+var_48]
0x1400063cd  mov     rdx, [rsp+78h+string]
0x1400063d2  mov     rcx, rbx
0x1400063d5  mov     rax, [r14+38h]
0x1400063d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400063de  mov     rcx, [rsp+78h]; this
0x1400063e3  test    eax, eax
0x1400063e5  jns     short loc_1400063FC
0x1400063e7  mov     r9d, eax; char *
0x1400063ea  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400063f1  mov     edx, 14E4h; void *
0x1400063f6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400063fc  mov     rdx, [rsp+78h+var_48]
0x140006401  lea     rcx, [rsp+78h+var_40]
0x140006406  call    ??$wait_for_completion@PEAUHSTRING__@@VHStringWithRelease@?$MapToSmartType@PEAUHSTRING__@@X@details@wil@@@wil@@YA?AVHStringWithRelease@?$MapToSmartType@PEAUHSTRING__@@X@details@0@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@@Z; wil::wait_for_completion<HSTRING__ *,wil::details::MapToSmartType<HSTRING__ *,void>::HStringWithRelease>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS)
0x14000640b  mov     rax, [rsp+78h+var_40]
0x140006410  mov     [rsp+78h+var_40], 0
0x140006419  mov     [rsi], rax
0x14000641c  xor     ecx, ecx; string
0x14000641e  call    cs:__imp_WindowsDeleteString
0x140006425  nop     dword ptr [rax+rax+00h]
0x14000642a  nop
0x14000642b  mov     rcx, [rsp+78h+var_48]
0x140006430  test    rcx, rcx
0x140006433  jz      short loc_140006442
0x140006435  mov     rax, [rcx]
0x140006438  mov     rax, [rax+10h]
0x14000643c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006441  nop
0x140006442  mov     rcx, qword ptr [rsp+78h+var_58]
0x140006447  test    rcx, rcx
0x14000644a  jz      short loc_140006459
0x14000644c  mov     rax, [rcx]
0x14000644f  mov     rax, [rax+10h]
0x140006453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006458  nop
0x140006459  mov     rcx, [rsp+78h+var_50]
0x14000645e  test    rcx, rcx
0x140006461  jz      short loc_140006470
0x140006463  mov     rax, [rcx]
0x140006466  mov     rax, [rax+10h]
0x14000646a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000646f  nop
0x140006470  jmp     short loc_140006477
0x140006472  mov     rsi, [rsp+78h+var_38]
0x140006477  cmp     qword ptr [rsi], 0
0x14000647b  jz      short loc_140006486
0x14000647d  call    ?IsOnUserDesktop@@YA_NXZ; IsOnUserDesktop(void)
0x140006482  xor     al, 1
0x140006484  jmp     short loc_140006488
0x140006486  xor     al, al
0x140006488  mov     rcx, [rsp+78h+var_10]
0x14000648d  xor     rcx, rsp; StackCookie
0x140006490  call    __security_check_cookie
0x140006495  lea     r11, [rsp+78h+var_8]
0x14000649a  mov     rbx, [r11+10h]
0x14000649e  mov     rsi, [r11+20h]
0x1400064a2  mov     rsp, r11
0x1400064a5  pop     r14
0x1400064a7  retn
```
