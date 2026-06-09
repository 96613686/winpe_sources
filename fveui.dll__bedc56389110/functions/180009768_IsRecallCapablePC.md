# IsRecallCapablePC

- ea: `0x180009768`
- end: `0x1800098bf`
- name: `IsRecallCapablePC`
- size: `343`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c924`

## callees

- `0x180001bb0`
- `0x1800037a0`
- `0x18000468c`
- `0x180009768`
- `0x18002d010`

## import_xrefs

- `KERNEL32!RaiseException` at `0x1800097ec`
- `KERNEL32!RaiseException` at `0x1800097ec`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180009896`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180009896`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180009802`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180009802`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180009791`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180009791`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800097d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800097d6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool IsRecallCapablePC()
{
  int v0; // ebx
  HRESULT v1; // eax
  unsigned int ActivationFactory; // eax
  int v3; // edi
  unsigned int v4; // eax
  bool v5; // di
  _BYTE v7[8]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v8; // [rsp+28h] [rbp-40h] BYREF
  int v9; // [rsp+30h] [rbp-38h]
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-30h] BYREF
  HSTRING string; // [rsp+50h] [rbp-18h] BYREF

  v7[0] = 0;
  v0 = RoInitialize(0);
  v9 = v0;
  v8 = 0;
  string = 0;
  v1 = WindowsCreateStringReference(L"WindowsUdk.System.Profile.HardwareRequirements", 0x2Eu, &hstringHeader, &string);
  if ( v1 < 0 )
  {
    RaiseException(v1, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_aa0872bc_bbf2_538f_9629_93a4ce6cae21, &v8);
  v3 = ActivationFactory;
  if ( !ActivationFactory )
    goto LABEL_8;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      &WPP_148a443baae43b032f4bebf0684096f9_Traceguids,
      ActivationFactory);
  if ( v3 >= 0 )
  {
LABEL_8:
    v4 = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *))(*(_QWORD *)v8 + 48LL))(v8, 1, v7);
    if ( v4 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids, v4);
  }
  v5 = v7[0] != 0;
  if ( v0 >= 0 )
    RoUninitialize();
  wil::com_ptr_t<WindowsUdk::System::Profile::IHardwareRequirementsStatics,wil::err_exception_policy>::~com_ptr_t<WindowsUdk::System::Profile::IHardwareRequirementsStatics,wil::err_exception_policy>(&v8);
  return v5;
}

```

## disassembly

```asm
0x180009768  push    rbp
0x18000976a  push    rbx
0x18000976b  push    rdi
0x18000976c  push    r14
0x18000976e  mov     rbp, rsp
0x180009771  sub     rsp, 68h
0x180009775  mov     rax, cs:__security_cookie
0x18000977c  xor     rax, rsp
0x18000977f  mov     [rbp+var_10], rax
0x180009783  mov     [rbp+var_40], 0
0x18000978b  mov     [rbp+var_48], 0
0x18000978f  xor     ecx, ecx
0x180009791  call    cs:__imp_RoInitialize
0x180009797  mov     ebx, eax
0x180009799  mov     [rbp+var_38], eax
0x18000979c  mov     rcx, [rbp+var_40]
0x1800097a0  mov     [rbp+var_40], 0
0x1800097a8  test    rcx, rcx
0x1800097ab  jz      short loc_1800097BA
0x1800097ad  mov     rax, [rcx]
0x1800097b0  mov     rax, [rax+10h]
0x1800097b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097b9  nop
0x1800097ba  mov     [rbp+string], 0
0x1800097c2  lea     r9, [rbp+string]; string
0x1800097c6  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800097ca  mov     edx, 2Eh ; '.'; length
0x1800097cf  lea     rcx, ?RuntimeClass_WindowsUdk_System_Profile_HardwareRequirements@@3QBGB; "WindowsUdk.System.Profile.HardwareRequi"...
0x1800097d6  call    cs:__imp_WindowsCreateStringReference
0x1800097dc  test    eax, eax
0x1800097de  jns     short loc_1800097F3
0x1800097e0  xor     r9d, r9d; lpArguments
0x1800097e3  xor     r8d, r8d; nNumberOfArguments
0x1800097e6  lea     edx, [r9+1]; dwExceptionFlags
0x1800097ea  mov     ecx, eax; dwExceptionCode
0x1800097ec  call    cs:__imp_RaiseException
0x1800097f2  int     3; Trap to Debugger
0x1800097f3  lea     r8, [rbp+var_40]
0x1800097f7  lea     rdx, _GUID_aa0872bc_bbf2_538f_9629_93a4ce6cae21
0x1800097fe  mov     rcx, [rbp+string]
0x180009802  call    cs:__imp_RoGetActivationFactory
0x180009808  mov     edi, eax
0x18000980a  lea     r14, WPP_GLOBAL_Control
0x180009811  test    eax, eax
0x180009813  jz      short loc_180009843
0x180009815  mov     rcx, cs:WPP_GLOBAL_Control
0x18000981c  cmp     rcx, r14
0x18000981f  jz      short loc_18000983F
0x180009821  test    byte ptr [rcx+1Ch], 40h
0x180009825  jz      short loc_18000983F
0x180009827  mov     edx, 0Ah
0x18000982c  mov     r9d, eax
0x18000982f  lea     r8, WPP_148a443baae43b032f4bebf0684096f9_Traceguids
0x180009836  mov     rcx, [rcx+10h]
0x18000983a  call    WPP_SF_d
0x18000983f  test    edi, edi
0x180009841  js      short loc_18000988A
0x180009843  mov     rcx, [rbp+var_40]
0x180009847  mov     rax, [rcx]
0x18000984a  lea     r8, [rbp+var_48]
0x18000984e  mov     edx, 1
0x180009853  mov     rax, [rax+30h]
0x180009857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000985c  test    eax, eax
0x18000985e  jz      short loc_18000988A
0x180009860  mov     rcx, cs:WPP_GLOBAL_Control
0x180009867  cmp     rcx, r14
0x18000986a  jz      short loc_18000988A
0x18000986c  test    byte ptr [rcx+1Ch], 40h
0x180009870  jz      short loc_18000988A
0x180009872  mov     edx, 0Bh
0x180009877  mov     r9d, eax
0x18000987a  lea     r8, WPP_148a443baae43b032f4bebf0684096f9_Traceguids
0x180009881  mov     rcx, [rcx+10h]
0x180009885  call    WPP_SF_d
0x18000988a  cmp     [rbp+var_48], 0
0x18000988e  setnz   dil
0x180009892  test    ebx, ebx
0x180009894  js      short loc_18000989D
0x180009896  call    cs:__imp_RoUninitialize
0x18000989c  nop
0x18000989d  lea     rcx, [rbp+var_40]
0x1800098a1  call    ??1?$com_ptr_t@UIHardwareRequirementsStatics@Profile@System@WindowsUdk@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<WindowsUdk::System::Profile::IHardwareRequirementsStatics,wil::err_exception_policy>::~com_ptr_t<WindowsUdk::System::Profile::IHardwareRequirementsStatics,wil::err_exception_policy>(void)
0x1800098a6  mov     al, dil
0x1800098a9  mov     rcx, [rbp+var_10]
0x1800098ad  xor     rcx, rsp; StackCookie
0x1800098b0  call    __security_check_cookie
0x1800098b5  add     rsp, 68h
0x1800098b9  pop     r14
0x1800098bb  pop     rdi
0x1800098bc  pop     rbx
0x1800098bd  pop     rbp
0x1800098be  retn
```
