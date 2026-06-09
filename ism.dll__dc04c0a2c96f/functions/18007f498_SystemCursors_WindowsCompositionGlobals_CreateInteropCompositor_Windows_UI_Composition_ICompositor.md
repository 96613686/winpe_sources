# SystemCursors::WindowsCompositionGlobals::CreateInteropCompositor(Windows::UI::Composition::ICompositor * *)

- ea: `0x18007f498`
- end: `0x18007f682`
- name: `?CreateInteropCompositor@WindowsCompositionGlobals@SystemCursors@@SAJPEAPEAUICompositor@Composition@UI@Windows@@@Z`
- size: `490`
- prototype: `__int64 __fastcall(struct Windows::UI::Composition::ICompositor **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800af800`

## callees

- `0x180069f90`
- `0x18007f498`
- `0x18008ead4`
- `0x1800f0990`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007f4f5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007f4f5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007f50b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007f50b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007f4df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007f4df`

## string_xrefs

- `0x18007f4d8`: `Windows.UI.Composition.Compositor`
- `0x18007f51e`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\cursor\systemcursorservice\lib\cursorwc.cpp`
- `0x18007f560`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\cursor\systemcursorservice\lib\cursorwc.cpp`
- `0x18007f5ce`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\cursor\systemcursorservice\lib\cursorwc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall SystemCursors::WindowsCompositionGlobals::CreateInteropCompositor(
        struct Windows::UI::Composition::ICompositor **a1)
{
  HRESULT v2; // eax
  int ActivationFactory; // eax
  unsigned int v4; // ebx
  int v5; // eax
  __int64 v7; // rax
  int v8; // eax
  struct Windows::UI::Composition::ICompositor *v9; // rax
  int v10; // [rsp+20h] [rbp-50h]
  int v11[2]; // [rsp+30h] [rbp-40h] BYREF
  __int64 *v12; // [rsp+38h] [rbp-38h] BYREF
  __int64 v13; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  HSTRING string; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  v13 = 0;
  string = 0;
  v2 = WindowsCreateStringReference(L"Windows.UI.Composition.Compositor", 0x21u, &hstringHeader, &string);
  if ( v2 < 0 )
  {
    RaiseException(v2, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_00000035_0000_0000_c000_000000000046, &v13);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8E,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\cursor\\systemcursorservice\\lib\\cursorwc.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v10);
LABEL_7:
    wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(&v13);
    return v4;
  }
  v12 = 0;
  v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 **))v13)(
         v13,
         &GUID_22118adf_23f1_4801_bcfa_66cbf48cc51b,
         &v12);
  v4 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x90,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\cursor\\systemcursorservice\\lib\\cursorwc.cpp",
      (const char *)(unsigned int)v5,
      v10);
    wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(&v12);
    goto LABEL_7;
  }
  *(_QWORD *)v11 = 0;
  v7 = *v12;
  *(_QWORD *)v11 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, GUID *))(v7 + 48))(
         v12,
         0,
         0,
         &GUID_b403ca50_7f8c_4e83_985f_cc45060036d8);
  v4 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x95,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\cursor\\systemcursorservice\\lib\\cursorwc.cpp",
      (const char *)(unsigned int)v8,
      (int)v11);
    if ( *(_QWORD *)v11 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v11 + 16LL))(*(_QWORD *)v11);
    if ( v12 )
      (*(void (__fastcall **)(__int64 *))(*v12 + 16))(v12);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    return v4;
  }
  v9 = *(struct Windows::UI::Composition::ICompositor **)v11;
  *(_QWORD *)v11 = 0;
  *a1 = v9;
  if ( v12 )
    (*(void (__fastcall **)(__int64 *))(*v12 + 16))(v12);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  return 0;
}

```

## disassembly

```asm
0x18007f498  mov     [rsp-8+arg_8], rbx
0x18007f49d  mov     [rsp-8+arg_10], rdi
0x18007f4a2  push    rbp
0x18007f4a3  mov     rbp, rsp
0x18007f4a6  sub     rsp, 70h
0x18007f4aa  mov     rax, cs:__security_cookie
0x18007f4b1  xor     rax, rsp
0x18007f4b4  mov     [rbp+var_8], rax
0x18007f4b8  mov     rdi, rcx
0x18007f4bb  mov     [rbp+var_30], 0
0x18007f4c3  mov     [rbp+string], 0
0x18007f4cb  lea     r9, [rbp+string]; string
0x18007f4cf  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18007f4d3  mov     edx, 21h ; '!'; length
0x18007f4d8  lea     rcx, ?RuntimeClass_Windows_UI_Composition_Compositor@@3QBGB; "Windows.UI.Composition.Compositor"
0x18007f4df  call    cs:__imp_WindowsCreateStringReference
0x18007f4e5  test    eax, eax
0x18007f4e7  jns     short loc_18007F4FC
0x18007f4e9  xor     r9d, r9d; lpArguments
0x18007f4ec  xor     r8d, r8d; nNumberOfArguments
0x18007f4ef  lea     edx, [r9+1]; dwExceptionFlags
0x18007f4f3  mov     ecx, eax; dwExceptionCode
0x18007f4f5  call    cs:__imp_RaiseException
0x18007f4fb  int     3; Trap to Debugger
0x18007f4fc  lea     r8, [rbp+var_30]
0x18007f500  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x18007f507  mov     rcx, [rbp+string]
0x18007f50b  call    cs:__imp_RoGetActivationFactory
0x18007f511  mov     ebx, eax
0x18007f513  test    eax, eax
0x18007f515  jns     short loc_18007F531
0x18007f517  mov     rcx, [rbp+8]; this
0x18007f51b  mov     r9d, eax; char *
0x18007f51e  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\moderncore\\inputv"...
0x18007f525  mov     edx, 8Eh; void *
0x18007f52a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007f52f  jmp     short loc_18007F57C
0x18007f531  mov     [rbp+var_38], 0
0x18007f539  mov     rcx, [rbp+var_30]
0x18007f53d  mov     rax, [rcx]
0x18007f540  lea     r8, [rbp+var_38]
0x18007f544  lea     rdx, _GUID_22118adf_23f1_4801_bcfa_66cbf48cc51b
0x18007f54b  mov     rax, [rax]
0x18007f54e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f553  mov     ebx, eax
0x18007f555  test    eax, eax
0x18007f557  jns     short loc_18007F58C
0x18007f559  mov     rcx, [rbp+8]; this
0x18007f55d  mov     r9d, eax; char *
0x18007f560  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\moderncore\\inputv"...
0x18007f567  mov     edx, 90h; void *
0x18007f56c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007f571  nop
0x18007f572  lea     rcx, [rbp+var_38]
0x18007f576  call    ??1?$com_ptr_t@UIMPCInputProviderBase@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(void)
0x18007f57b  nop
0x18007f57c  lea     rcx, [rbp+var_30]
0x18007f580  call    ??1?$com_ptr_t@UIMPCInputProviderBase@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(void)
0x18007f585  mov     eax, ebx
0x18007f587  jmp     loc_18007F664
0x18007f58c  mov     qword ptr [rbp+var_40], 0
0x18007f594  mov     rcx, [rbp+var_38]
0x18007f598  mov     rax, [rcx]
0x18007f59b  mov     qword ptr [rbp+var_40], 0
0x18007f5a3  lea     rdx, [rbp+var_40]
0x18007f5a7  mov     qword ptr [rsp+70h+var_50], rdx; int
0x18007f5ac  lea     r9, _GUID_b403ca50_7f8c_4e83_985f_cc45060036d8
0x18007f5b3  xor     r8d, r8d
0x18007f5b6  xor     edx, edx
0x18007f5b8  mov     rax, [rax+30h]
0x18007f5bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f5c1  mov     ebx, eax
0x18007f5c3  test    eax, eax
0x18007f5c5  jns     short loc_18007F627
0x18007f5c7  mov     rcx, [rbp+8]; this
0x18007f5cb  mov     r9d, eax; char *
0x18007f5ce  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\moderncore\\inputv"...
0x18007f5d5  mov     edx, 95h; void *
0x18007f5da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007f5df  nop
0x18007f5e0  mov     rcx, qword ptr [rbp+var_40]
0x18007f5e4  test    rcx, rcx
0x18007f5e7  jz      short loc_18007F5F6
0x18007f5e9  mov     rax, [rcx]
0x18007f5ec  mov     rax, [rax+10h]
0x18007f5f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f5f5  nop
0x18007f5f6  mov     rcx, [rbp+var_38]
0x18007f5fa  test    rcx, rcx
0x18007f5fd  jz      short loc_18007F60C
0x18007f5ff  mov     rax, [rcx]
0x18007f602  mov     rax, [rax+10h]
0x18007f606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f60b  nop
0x18007f60c  mov     rcx, [rbp+var_30]
0x18007f610  test    rcx, rcx
0x18007f613  jz      short loc_18007F622
0x18007f615  mov     rax, [rcx]
0x18007f618  mov     rax, [rax+10h]
0x18007f61c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f621  nop
0x18007f622  jmp     loc_18007F585
0x18007f627  mov     rax, qword ptr [rbp+var_40]
0x18007f62b  mov     qword ptr [rbp+var_40], 0
0x18007f633  mov     [rdi], rax
0x18007f636  mov     rcx, [rbp+var_38]
0x18007f63a  test    rcx, rcx
0x18007f63d  jz      short loc_18007F64C
0x18007f63f  mov     rax, [rcx]
0x18007f642  mov     rax, [rax+10h]
0x18007f646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f64b  nop
0x18007f64c  mov     rcx, [rbp+var_30]
0x18007f650  test    rcx, rcx
0x18007f653  jz      short loc_18007F662
0x18007f655  mov     rax, [rcx]
0x18007f658  mov     rax, [rax+10h]
0x18007f65c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f661  nop
0x18007f662  xor     eax, eax
0x18007f664  mov     rcx, [rbp+var_8]
0x18007f668  xor     rcx, rsp; StackCookie
0x18007f66b  call    __security_check_cookie
0x18007f670  lea     r11, [rsp+70h+var_s0]
0x18007f675  mov     rbx, [r11+18h]
0x18007f679  mov     rdi, [r11+20h]
0x18007f67d  mov     rsp, r11
0x18007f680  pop     rbp
0x18007f681  retn
```
