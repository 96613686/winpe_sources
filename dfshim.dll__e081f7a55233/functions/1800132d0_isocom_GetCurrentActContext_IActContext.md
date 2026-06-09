# isocom_GetCurrentActContext(IActContext * *)

- ea: `0x1800132d0`
- end: `0x180013484`
- name: `?isocom_GetCurrentActContext@@YAJPEAPEAUIActContext@@@Z`
- size: `436`
- prototype: `__int64 __fastcall(struct IActContext **)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180012b1c`
- `0x180012b38`
- `0x1800132d0`
- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x1800197b4`
- `0x18003f0b8`
- `0x18004f2dc`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180013324`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180013324`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800133a8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001345b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800133a8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001345b`

## string_xrefs

- `0x1800132e3`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\globalfunctions.cpp`
- `0x18001335f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x180013416`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`

## pseudocode

```c
__int64 __fastcall isocom_GetCurrentActContext(struct IActContext **a1)
{
  int CurrentApplicationContext; // eax
  __int64 v3; // rdx
  unsigned int v4; // edi
  int v5; // edx
  unsigned int v6; // ebx
  __int64 v7; // r10
  unsigned int *v8; // r11
  signed int v9; // ecx
  int v10; // eax
  int v11; // r9d
  __int64 v12; // r10
  unsigned int *v13; // r11
  signed int v14; // ecx
  const char *v16; // [rsp+20h] [rbp-38h] BYREF
  int v17; // [rsp+28h] [rbp-30h]
  unsigned int v18; // [rsp+30h] [rbp-28h]
  const char *v19; // [rsp+38h] [rbp-20h] BYREF
  int v20; // [rsp+40h] [rbp-18h]
  int v21; // [rsp+48h] [rbp-10h]
  __int64 v22; // [rsp+80h] [rbp+28h] BYREF

  v18 = -2147023537;
  v16 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\globalfunctions.cpp";
  v22 = 0;
  if ( a1 )
  {
    *a1 = 0;
    CurrentApplicationContext = RtlGetCurrentApplicationContext(a1, &v22);
    v4 = CurrentApplicationContext;
    if ( CurrentApplicationContext >= 0 )
    {
      v10 = IsolationImplementation::Com::CopyOut(v22, v3, a1);
      v6 = v10;
      if ( v10 >= 0 )
        v6 = 0;
      else
        Windows::ErrorHandling::COM::ReportErrorPropagation(
          (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\globalfunctions.cpp",
          (const char *)0x219,
          v10,
          v11);
    }
    else
    {
      if ( CurrentApplicationContext == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\globalfunctions.cpp",
        (const char *)0x218,
        v4,
        (unsigned int)v16);
      v6 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v4, v5);
    }
    if ( v22 )
    {
      v18 = -1073741595;
      v16 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_APPLICATION_CONTEXT,IsolationImplementation::Rtl::CApplicationContext,IsolationImplementation::Rtl::CApplicationContextCD,IsolationImplementation::Rtl::CApplicationContextImplTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v22) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v8 + 4))(*v8, v7);
        v9 = 0;
      }
      else
      {
        v17 = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v16);
        v9 = v18;
      }
      if ( v9 < 0 )
        RaiseException(v9, 1u, 0, 0);
    }
  }
  else
  {
    v17 = 534;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v16);
    if ( v22 )
    {
      v21 = -1073741595;
      v19 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_APPLICATION_CONTEXT,IsolationImplementation::Rtl::CApplicationContext,IsolationImplementation::Rtl::CApplicationContextCD,IsolationImplementation::Rtl::CApplicationContextImplTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v22) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v13 + 4))(*v13, v12);
        v14 = 0;
      }
      else
      {
        v20 = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v19);
        v14 = v21;
      }
      if ( v14 < 0 )
        RaiseException(v14, 1u, 0, 0);
    }
    return v18;
  }
  return v6;
}

```

## disassembly

```asm
0x1800132d0  push    rbp
0x1800132d2  push    rbx
0x1800132d3  push    rsi
0x1800132d4  push    rdi
0x1800132d5  mov     rbp, rsp
0x1800132d8  sub     rsp, 58h
0x1800132dc  mov     [rbp+var_28], 8007054Fh
0x1800132e3  lea     rsi, aOnecoreComNetf_38; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800132ea  mov     [rbp+var_38], rsi
0x1800132ee  mov     rbx, rcx
0x1800132f1  mov     [rbp+arg_0], 0
0x1800132f9  test    rcx, rcx
0x1800132fc  jz      loc_1800133F6
0x180013302  lea     rdx, [rbp+arg_0]
0x180013306  mov     qword ptr [rcx], 0
0x18001330d  call    RtlGetCurrentApplicationContext
0x180013312  mov     edi, eax
0x180013314  test    eax, eax
0x180013316  jns     loc_1800133C8
0x18001331c  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180013322  jnz     short loc_18001332A
0x180013324  call    cs:__imp_DebugBreak
0x18001332a  mov     r9d, edi; int
0x18001332d  lea     rcx, aStatusPropagat; "Status propagated"
0x180013334  mov     r8d, 218h; char *
0x18001333a  mov     rdx, rsi; char *
0x18001333d  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180013342  mov     ecx, edi; this
0x180013344  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180013349  mov     ebx, eax
0x18001334b  mov     r10, [rbp+arg_0]
0x18001334f  test    r10, r10
0x180013352  jz      loc_180013464
0x180013358  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_APPLICATION_CONTEXT@Rtl@Isolation@Windows@@VCApplicationContext@2IsolationImplementation@@VCApplicationContextCD@26@VCApplicationContextImplTraits@26@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_APPLICATION_CONTEXT,IsolationImplementation::Rtl::CApplicationContext,IsolationImplementation::Rtl::CApplicationContextCD,IsolationImplementation::Rtl::CApplicationContextImplTraits>::ms_ptti
0x18001335f  lea     rcx, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180013366  mov     [rbp+var_28], 0C00000E5h
0x18001336d  mov     [rbp+var_38], rcx
0x180013371  test    r11, r11
0x180013374  jz      short loc_1800133B3
0x180013376  mov     rdx, r11
0x180013379  mov     rcx, r10
0x18001337c  call    RtlIsTypeSafeHandleValid
0x180013381  test    al, al
0x180013383  jz      short loc_1800133B3
0x180013385  mov     ecx, [r11]
0x180013388  mov     rdx, r10
0x18001338b  mov     rax, [r11+20h]
0x18001338f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013394  xor     ecx, ecx; dwExceptionCode
0x180013396  test    ecx, ecx
0x180013398  jns     loc_180013464
0x18001339e  xor     r9d, r9d; lpArguments
0x1800133a1  xor     r8d, r8d; nNumberOfArguments
0x1800133a4  lea     edx, [r9+1]; dwExceptionFlags
0x1800133a8  call    cs:__imp_RaiseException
0x1800133ae  jmp     loc_180013464
0x1800133b3  mov     [rbp+var_30], 124h
0x1800133ba  lea     rcx, [rbp+var_38]
0x1800133be  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800133c3  mov     ecx, [rbp+var_28]
0x1800133c6  jmp     short loc_180013396
0x1800133c8  mov     rcx, [rbp+arg_0]
0x1800133cc  mov     r8, rbx
0x1800133cf  call    ?CopyOut@Com@IsolationImplementation@@YAJU_APPLICATION_CONTEXT@Rtl@Isolation@Windows@@AEBU_GUID@@PEAPEAUIUnknown@@@Z; IsolationImplementation::Com::CopyOut(Windows::Isolation::Rtl::_APPLICATION_CONTEXT,_GUID const &,IUnknown * *)
0x1800133d4  mov     ebx, eax
0x1800133d6  test    eax, eax
0x1800133d8  jns     short loc_1800133EF
0x1800133da  mov     r8d, eax; int
0x1800133dd  mov     edx, 219h; char *
0x1800133e2  mov     rcx, rsi; this
0x1800133e5  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800133ea  jmp     loc_18001334B
0x1800133ef  xor     ebx, ebx
0x1800133f1  jmp     loc_18001334B
0x1800133f6  lea     rcx, [rbp+var_38]
0x1800133fa  mov     [rbp+var_30], 216h
0x180013401  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x180013406  mov     r10, [rbp+arg_0]
0x18001340a  test    r10, r10
0x18001340d  jz      short loc_180013461
0x18001340f  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_APPLICATION_CONTEXT@Rtl@Isolation@Windows@@VCApplicationContext@2IsolationImplementation@@VCApplicationContextCD@26@VCApplicationContextImplTraits@26@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_APPLICATION_CONTEXT,IsolationImplementation::Rtl::CApplicationContext,IsolationImplementation::Rtl::CApplicationContextCD,IsolationImplementation::Rtl::CApplicationContextImplTraits>::ms_ptti
0x180013416  lea     rcx, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18001341d  mov     [rbp+var_10], 0C00000E5h
0x180013424  mov     [rbp+var_20], rcx
0x180013428  test    r11, r11
0x18001342b  jz      short loc_18001346F
0x18001342d  mov     rdx, r11
0x180013430  mov     rcx, r10
0x180013433  call    RtlIsTypeSafeHandleValid
0x180013438  test    al, al
0x18001343a  jz      short loc_18001346F
0x18001343c  mov     ecx, [r11]
0x18001343f  mov     rdx, r10
0x180013442  mov     rax, [r11+20h]
0x180013446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001344b  xor     ecx, ecx; dwExceptionCode
0x18001344d  test    ecx, ecx
0x18001344f  jns     short loc_180013461
0x180013451  xor     r9d, r9d; lpArguments
0x180013454  xor     r8d, r8d; nNumberOfArguments
0x180013457  lea     edx, [r9+1]; dwExceptionFlags
0x18001345b  call    cs:__imp_RaiseException
0x180013461  mov     ebx, [rbp+var_28]
0x180013464  mov     eax, ebx
0x180013466  add     rsp, 58h
0x18001346a  pop     rdi
0x18001346b  pop     rsi
0x18001346c  pop     rbx
0x18001346d  pop     rbp
0x18001346e  retn
0x18001346f  mov     [rbp+var_18], 124h
0x180013476  lea     rcx, [rbp+var_20]
0x18001347a  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x18001347f  mov     ecx, [rbp+var_10]
0x180013482  jmp     short loc_18001344D
```
