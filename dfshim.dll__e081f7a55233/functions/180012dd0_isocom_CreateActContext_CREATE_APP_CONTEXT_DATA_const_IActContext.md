# isocom_CreateActContext(_CREATE_APP_CONTEXT_DATA const *,IActContext * *)

- ea: `0x180012dd0`
- end: `0x180013197`
- name: `?isocom_CreateActContext@@YAJPEBU_CREATE_APP_CONTEXT_DATA@@PEAPEAUIActContext@@@Z`
- size: `967`
- prototype: `__int64 __fastcall(const struct _CREATE_APP_CONTEXT_DATA *, struct IActContext **)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x1800069b5`
- `0x1800069c1`
- `0x180012b1c`
- `0x180012b38`
- `0x180012dd0`
- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x1800197b4`
- `0x180030b70`
- `0x18003b558`
- `0x18003eb10`
- `0x18004f2dc`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180012ee0`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180012ee0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180012f60`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001305a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001311f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180012f60`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001305a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001311f`

## string_xrefs

- `0x180012dec`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\globalfunctions.cpp`
- `0x180012f1b`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x180013015`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800130da`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`

## pseudocode

```c
__int64 __fastcall isocom_CreateActContext(
        const struct _CREATE_APP_CONTEXT_DATA *a1,
        struct IActContext **a2,
        __int64 a3,
        struct Windows::Isolation::Rtl::_CREATE_APPLICATION_CONTEXT_DATA **a4)
{
  unsigned int v5; // edi
  int v6; // eax
  int v7; // r9d
  void (__fastcall *v8)(LPVOID *); // rax
  HANDLE v9; // rax
  LPVOID *v10; // rbx
  __int64 v11; // rsi
  int v12; // eax
  unsigned int v13; // edi
  int v14; // edx
  __int64 v15; // r10
  unsigned int *v16; // r11
  signed int v17; // ecx
  void (__fastcall *v18)(LPVOID *); // rax
  HANDLE v19; // rax
  LPVOID *v20; // rbx
  __int64 v21; // rdx
  int v22; // eax
  int v23; // r9d
  __int64 v24; // r10
  unsigned int *v25; // r11
  signed int v26; // ecx
  void (__fastcall *v27)(LPVOID *); // rax
  HANDLE v28; // rax
  LPVOID *v29; // rbx
  __int64 v30; // r10
  unsigned int *v31; // r11
  signed int v32; // ecx
  void (__fastcall *v33)(LPVOID *); // rax
  HANDLE ProcessHeap_0; // rax
  LPVOID *v35; // rbx
  LPVOID lpMem[2]; // [rsp+20h] [rbp-30h] BYREF
  const char *v38; // [rsp+30h] [rbp-20h] BYREF
  int v39; // [rsp+38h] [rbp-18h]
  unsigned int v40; // [rsp+40h] [rbp-10h]
  __int64 v41; // [rsp+70h] [rbp+20h] BYREF
  __int64 v42; // [rsp+78h] [rbp+28h] BYREF

  v40 = -2147023537;
  v38 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\globalfunctions.cpp";
  if ( a2 )
    *a2 = 0;
  if ( !a1 )
  {
    v39 = 504;
LABEL_5:
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v38);
    return v40;
  }
  if ( !a2 )
  {
    v39 = 505;
    goto LABEL_5;
  }
  v42 = 0;
  lpMem[1] = lpMem;
  lpMem[0] = lpMem;
  v6 = IsolationImplementation::Com::ConvertIn(
         (IsolationImplementation::Com *)lpMem,
         a1,
         (const struct _CREATE_APP_CONTEXT_DATA *)&v42,
         a4);
  v5 = v6;
  if ( v6 >= 0 )
  {
    v11 = v42;
    v41 = 0;
    v12 = RtlCreateApplicationContext(v42, &v41);
    v13 = v12;
    if ( v12 >= 0 )
    {
      RtlCloseDefinitionAppIdHandle(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v11 + 40) + 16LL) + 16LL));
      v22 = IsolationImplementation::Com::CopyOut(v41, v21, a2);
      v5 = v22;
      if ( v22 >= 0 )
      {
        v5 = 0;
        if ( v41 )
        {
          v40 = -1073741595;
          v38 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
          if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_APPLICATION_CONTEXT,IsolationImplementation::Rtl::CApplicationContext,IsolationImplementation::Rtl::CApplicationContextCD,IsolationImplementation::Rtl::CApplicationContextImplTraits>::ms_ptti
            && (unsigned __int8)RtlIsTypeSafeHandleValid(v41) )
          {
            (*((void (__fastcall **)(_QWORD, __int64))v31 + 4))(*v31, v30);
            v32 = 0;
          }
          else
          {
            v39 = 292;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v38);
            v32 = v40;
          }
          if ( v32 < 0 )
            RaiseException(v32, 1u, 0, 0);
          v41 = 0;
        }
        while ( 1 )
        {
          v35 = (LPVOID *)lpMem[0];
          lpMem[0] = *(LPVOID *)lpMem[0];
          *((_QWORD *)lpMem[0] + 1) = lpMem;
          if ( v35 == lpMem )
            break;
          v33 = (void (__fastcall *)(LPVOID *))v35[2];
          if ( v33 )
            v33(v35 + 3);
          ProcessHeap_0 = GetProcessHeap_0();
          HeapFree_0(ProcessHeap_0, 0, v35);
        }
      }
      else
      {
        Windows::ErrorHandling::COM::ReportErrorPropagation(
          (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\globalfunctions.cpp",
          (const char *)0x206,
          v22,
          v23);
        if ( v41 )
        {
          v40 = -1073741595;
          v38 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
          if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_APPLICATION_CONTEXT,IsolationImplementation::Rtl::CApplicationContext,IsolationImplementation::Rtl::CApplicationContextCD,IsolationImplementation::Rtl::CApplicationContextImplTraits>::ms_ptti
            && (unsigned __int8)RtlIsTypeSafeHandleValid(v41) )
          {
            (*((void (__fastcall **)(_QWORD, __int64))v25 + 4))(*v25, v24);
            v26 = 0;
          }
          else
          {
            v39 = 292;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v38);
            v26 = v40;
          }
          if ( v26 < 0 )
            RaiseException(v26, 1u, 0, 0);
          v41 = 0;
        }
        while ( 1 )
        {
          v29 = (LPVOID *)lpMem[0];
          lpMem[0] = *(LPVOID *)lpMem[0];
          *((_QWORD *)lpMem[0] + 1) = lpMem;
          if ( v29 == lpMem )
            break;
          v27 = (void (__fastcall *)(LPVOID *))v29[2];
          if ( v27 )
            v27(v29 + 3);
          v28 = GetProcessHeap_0();
          HeapFree_0(v28, 0, v29);
        }
      }
    }
    else
    {
      if ( v12 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\globalfunctions.cpp",
        (const char *)0x202,
        v13,
        (unsigned int)lpMem[0]);
      v5 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v13, v14);
      if ( v41 )
      {
        v40 = -1073741595;
        v38 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
        if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_APPLICATION_CONTEXT,IsolationImplementation::Rtl::CApplicationContext,IsolationImplementation::Rtl::CApplicationContextCD,IsolationImplementation::Rtl::CApplicationContextImplTraits>::ms_ptti
          && (unsigned __int8)RtlIsTypeSafeHandleValid(v41) )
        {
          (*((void (__fastcall **)(_QWORD, __int64))v16 + 4))(*v16, v15);
          v17 = 0;
        }
        else
        {
          v39 = 292;
          Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v38);
          v17 = v40;
        }
        if ( v17 < 0 )
          RaiseException(v17, 1u, 0, 0);
        v41 = 0;
      }
      while ( 1 )
      {
        v20 = (LPVOID *)lpMem[0];
        lpMem[0] = *(LPVOID *)lpMem[0];
        *((_QWORD *)lpMem[0] + 1) = lpMem;
        if ( v20 == lpMem )
          break;
        v18 = (void (__fastcall *)(LPVOID *))v20[2];
        if ( v18 )
          v18(v20 + 3);
        v19 = GetProcessHeap_0();
        HeapFree_0(v19, 0, v20);
      }
    }
  }
  else
  {
    Windows::ErrorHandling::COM::ReportErrorPropagation(
      (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\globalfunctions.cpp",
      (const char *)0x1FE,
      v6,
      v7);
    while ( 1 )
    {
      v10 = (LPVOID *)lpMem[0];
      lpMem[0] = *(LPVOID *)lpMem[0];
      *((_QWORD *)lpMem[0] + 1) = lpMem;
      if ( v10 == lpMem )
        break;
      v8 = (void (__fastcall *)(LPVOID *))v10[2];
      if ( v8 )
        v8(v10 + 3);
      v9 = GetProcessHeap_0();
      HeapFree_0(v9, 0, v10);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180012dd0  mov     [rsp-18h+arg_10], rbx
0x180012dd5  mov     [rsp-18h+arg_18], rsi
0x180012dda  push    rbp
0x180012ddb  push    rdi
0x180012ddc  push    r15
0x180012dde  mov     rbp, rsp
0x180012de1  sub     rsp, 50h
0x180012de5  mov     [rbp+var_10], 8007054Fh
0x180012dec  lea     r15, aOnecoreComNetf_38; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180012df3  mov     [rbp+var_20], r15
0x180012df7  mov     rbx, rdx
0x180012dfa  test    rdx, rdx
0x180012dfd  jz      short loc_180012E06
0x180012dff  mov     qword ptr [rdx], 0
0x180012e06  test    rcx, rcx
0x180012e09  jnz     short loc_180012E23
0x180012e0b  mov     [rbp+var_18], 1F8h
0x180012e12  lea     rcx, [rbp+var_20]
0x180012e16  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x180012e1b  mov     edi, [rbp+var_10]
0x180012e1e  jmp     loc_180013180
0x180012e23  test    rbx, rbx
0x180012e26  jnz     short loc_180012E31
0x180012e28  mov     [rbp+var_18], 1F9h
0x180012e2f  jmp     short loc_180012E12
0x180012e31  lea     rax, [rbp+lpMem]
0x180012e35  mov     [rbp+arg_8], 0
0x180012e3d  mov     [rbp+var_28], rax
0x180012e41  lea     r8, [rbp+arg_8]; struct _CREATE_APP_CONTEXT_DATA *
0x180012e45  lea     rax, [rbp+lpMem]
0x180012e49  mov     rdx, rcx; struct _RTL_ALLOCATION_LIST *
0x180012e4c  lea     rcx, [rbp+lpMem]; this
0x180012e50  mov     [rbp+lpMem], rax
0x180012e54  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAU_RTL_ALLOCATION_LIST@@PEBU_CREATE_APP_CONTEXT_DATA@@AEAPEAU_CREATE_APPLICATION_CONTEXT_DATA@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(_RTL_ALLOCATION_LIST *,_CREATE_APP_CONTEXT_DATA const *,Windows::Isolation::Rtl::_CREATE_APPLICATION_CONTEXT_DATA * &)
0x180012e59  mov     edi, eax
0x180012e5b  test    eax, eax
0x180012e5d  jns     short loc_180012EB6
0x180012e5f  mov     r8d, eax; int
0x180012e62  mov     edx, 1FEh; char *
0x180012e67  mov     rcx, r15; this
0x180012e6a  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x180012e6f  jmp     short loc_180012E95
0x180012e71  mov     rax, [rbx+10h]
0x180012e75  test    rax, rax
0x180012e78  jz      short loc_180012E83
0x180012e7a  lea     rcx, [rbx+18h]
0x180012e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e83  call    GetProcessHeap_0
0x180012e88  mov     r8, rbx; lpMem
0x180012e8b  xor     edx, edx; dwFlags
0x180012e8d  mov     rcx, rax; hHeap
0x180012e90  call    HeapFree_0
0x180012e95  mov     rbx, [rbp+lpMem]
0x180012e99  lea     rcx, [rbp+lpMem]
0x180012e9d  mov     rax, [rbx]
0x180012ea0  mov     [rbp+lpMem], rax
0x180012ea4  mov     [rax+8], rcx
0x180012ea8  lea     rax, [rbp+lpMem]
0x180012eac  cmp     rbx, rax
0x180012eaf  jnz     short loc_180012E71
0x180012eb1  jmp     loc_180013180
0x180012eb6  mov     rsi, [rbp+arg_8]
0x180012eba  lea     rdx, [rbp+arg_0]
0x180012ebe  mov     rcx, rsi
0x180012ec1  mov     [rbp+arg_0], 0
0x180012ec9  call    RtlCreateApplicationContext
0x180012ece  mov     edi, eax
0x180012ed0  test    eax, eax
0x180012ed2  jns     loc_180012FCA
0x180012ed8  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180012ede  jnz     short loc_180012EE6
0x180012ee0  call    cs:__imp_DebugBreak
0x180012ee6  mov     r9d, edi; int
0x180012ee9  lea     rcx, aStatusPropagat; "Status propagated"
0x180012ef0  mov     r8d, 202h; char *
0x180012ef6  mov     rdx, r15; char *
0x180012ef9  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180012efe  mov     ecx, edi; this
0x180012f00  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180012f05  mov     r10, [rbp+arg_0]
0x180012f09  mov     edi, eax
0x180012f0b  test    r10, r10
0x180012f0e  jz      loc_180012FA9
0x180012f14  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_APPLICATION_CONTEXT@Rtl@Isolation@Windows@@VCApplicationContext@2IsolationImplementation@@VCApplicationContextCD@26@VCApplicationContextImplTraits@26@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_APPLICATION_CONTEXT,IsolationImplementation::Rtl::CApplicationContext,IsolationImplementation::Rtl::CApplicationContextCD,IsolationImplementation::Rtl::CApplicationContextImplTraits>::ms_ptti
0x180012f1b  lea     rcx, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180012f22  mov     [rbp+var_10], 0C00000E5h
0x180012f29  mov     [rbp+var_20], rcx
0x180012f2d  test    r11, r11
0x180012f30  jz      short loc_180012F70
0x180012f32  mov     rdx, r11
0x180012f35  mov     rcx, r10
0x180012f38  call    RtlIsTypeSafeHandleValid
0x180012f3d  test    al, al
0x180012f3f  jz      short loc_180012F70
0x180012f41  mov     ecx, [r11]
0x180012f44  mov     rdx, r10
0x180012f47  mov     rax, [r11+20h]
0x180012f4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f50  xor     ecx, ecx; dwExceptionCode
0x180012f52  test    ecx, ecx
0x180012f54  jns     short loc_180012F66
0x180012f56  xor     r9d, r9d; lpArguments
0x180012f59  xor     r8d, r8d; nNumberOfArguments
0x180012f5c  lea     edx, [r9+1]; dwExceptionFlags
0x180012f60  call    cs:__imp_RaiseException
0x180012f66  mov     [rbp+arg_0], 0
0x180012f6e  jmp     short loc_180012FA9
0x180012f70  mov     [rbp+var_18], 124h
0x180012f77  lea     rcx, [rbp+var_20]
0x180012f7b  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x180012f80  mov     ecx, [rbp+var_10]
0x180012f83  jmp     short loc_180012F52
0x180012f85  mov     rax, [rbx+10h]
0x180012f89  test    rax, rax
0x180012f8c  jz      short loc_180012F97
0x180012f8e  lea     rcx, [rbx+18h]
0x180012f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f97  call    GetProcessHeap_0
0x180012f9c  mov     r8, rbx; lpMem
0x180012f9f  xor     edx, edx; dwFlags
0x180012fa1  mov     rcx, rax; hHeap
0x180012fa4  call    HeapFree_0
0x180012fa9  mov     rbx, [rbp+lpMem]
0x180012fad  lea     rcx, [rbp+lpMem]
0x180012fb1  mov     rax, [rbx]
0x180012fb4  mov     [rbp+lpMem], rax
0x180012fb8  mov     [rax+8], rcx
0x180012fbc  lea     rax, [rbp+lpMem]
0x180012fc0  cmp     rbx, rax
0x180012fc3  jnz     short loc_180012F85
0x180012fc5  jmp     loc_180013180
0x180012fca  mov     rax, [rsi+28h]
0x180012fce  mov     rcx, [rax+10h]
0x180012fd2  mov     rcx, [rcx+10h]
0x180012fd6  call    RtlCloseDefinitionAppIdHandle
0x180012fdb  mov     rcx, [rbp+arg_0]
0x180012fdf  mov     r8, rbx
0x180012fe2  call    ?CopyOut@Com@IsolationImplementation@@YAJU_APPLICATION_CONTEXT@Rtl@Isolation@Windows@@AEBU_GUID@@PEAPEAUIUnknown@@@Z; IsolationImplementation::Com::CopyOut(Windows::Isolation::Rtl::_APPLICATION_CONTEXT,_GUID const &,IUnknown * *)
0x180012fe7  mov     edi, eax
0x180012fe9  test    eax, eax
0x180012feb  jns     loc_1800130C4
0x180012ff1  mov     r8d, eax; int
0x180012ff4  mov     edx, 206h; char *
0x180012ff9  mov     rcx, r15; this
0x180012ffc  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x180013001  mov     r10, [rbp+arg_0]
0x180013005  test    r10, r10
0x180013008  jz      loc_1800130A3
0x18001300e  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_APPLICATION_CONTEXT@Rtl@Isolation@Windows@@VCApplicationContext@2IsolationImplementation@@VCApplicationContextCD@26@VCApplicationContextImplTraits@26@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_APPLICATION_CONTEXT,IsolationImplementation::Rtl::CApplicationContext,IsolationImplementation::Rtl::CApplicationContextCD,IsolationImplementation::Rtl::CApplicationContextImplTraits>::ms_ptti
0x180013015  lea     rcx, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18001301c  mov     [rbp+var_10], 0C00000E5h
0x180013023  mov     [rbp+var_20], rcx
0x180013027  test    r11, r11
0x18001302a  jz      short loc_18001306A
0x18001302c  mov     rdx, r11
0x18001302f  mov     rcx, r10
0x180013032  call    RtlIsTypeSafeHandleValid
0x180013037  test    al, al
0x180013039  jz      short loc_18001306A
0x18001303b  mov     ecx, [r11]
0x18001303e  mov     rdx, r10
0x180013041  mov     rax, [r11+20h]
0x180013045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001304a  xor     ecx, ecx; dwExceptionCode
0x18001304c  test    ecx, ecx
0x18001304e  jns     short loc_180013060
0x180013050  xor     r9d, r9d; lpArguments
0x180013053  xor     r8d, r8d; nNumberOfArguments
0x180013056  lea     edx, [r9+1]; dwExceptionFlags
0x18001305a  call    cs:__imp_RaiseException
0x180013060  mov     [rbp+arg_0], 0
0x180013068  jmp     short loc_1800130A3
0x18001306a  mov     [rbp+var_18], 124h
0x180013071  lea     rcx, [rbp+var_20]
0x180013075  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x18001307a  mov     ecx, [rbp+var_10]
0x18001307d  jmp     short loc_18001304C
0x18001307f  mov     rax, [rbx+10h]
0x180013083  test    rax, rax
0x180013086  jz      short loc_180013091
0x180013088  lea     rcx, [rbx+18h]
0x18001308c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013091  call    GetProcessHeap_0
0x180013096  mov     r8, rbx; lpMem
0x180013099  xor     edx, edx; dwFlags
0x18001309b  mov     rcx, rax; hHeap
0x18001309e  call    HeapFree_0
0x1800130a3  mov     rbx, [rbp+lpMem]
0x1800130a7  lea     rcx, [rbp+lpMem]
0x1800130ab  mov     rax, [rbx]
0x1800130ae  mov     [rbp+lpMem], rax
0x1800130b2  mov     [rax+8], rcx
0x1800130b6  lea     rax, [rbp+lpMem]
0x1800130ba  cmp     rbx, rax
0x1800130bd  jnz     short loc_18001307F
0x1800130bf  jmp     loc_180013180
0x1800130c4  mov     r10, [rbp+arg_0]
0x1800130c8  xor     edi, edi
0x1800130ca  test    r10, r10
0x1800130cd  jz      loc_180013164
0x1800130d3  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_APPLICATION_CONTEXT@Rtl@Isolation@Windows@@VCApplicationContext@2IsolationImplementation@@VCApplicationContextCD@26@VCApplicationContextImplTraits@26@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_APPLICATION_CONTEXT,IsolationImplementation::Rtl::CApplicationContext,IsolationImplementation::Rtl::CApplicationContextCD,IsolationImplementation::Rtl::CApplicationContextImplTraits>::ms_ptti
0x1800130da  lea     rcx, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800130e1  mov     [rbp+var_10], 0C00000E5h
0x1800130e8  mov     [rbp+var_20], rcx
0x1800130ec  test    r11, r11
0x1800130ef  jz      short loc_18001312B
0x1800130f1  mov     rdx, r11
0x1800130f4  mov     rcx, r10
0x1800130f7  call    RtlIsTypeSafeHandleValid
0x1800130fc  test    al, al
0x1800130fe  jz      short loc_18001312B
0x180013100  mov     ecx, [r11]
0x180013103  mov     rdx, r10
0x180013106  mov     rax, [r11+20h]
0x18001310a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001310f  xor     ecx, ecx; dwExceptionCode
0x180013111  test    ecx, ecx
0x180013113  jns     short loc_180013125
0x180013115  xor     r9d, r9d; lpArguments
0x180013118  xor     r8d, r8d; nNumberOfArguments
0x18001311b  lea     edx, [r9+1]; dwExceptionFlags
0x18001311f  call    cs:__imp_RaiseException
0x180013125  mov     [rbp+arg_0], rdi
0x180013129  jmp     short loc_180013164
0x18001312b  mov     [rbp+var_18], 124h
0x180013132  lea     rcx, [rbp+var_20]
0x180013136  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x18001313b  mov     ecx, [rbp+var_10]
0x18001313e  jmp     short loc_180013111
0x180013140  mov     rax, [rbx+10h]
0x180013144  test    rax, rax
0x180013147  jz      short loc_180013152
0x180013149  lea     rcx, [rbx+18h]
0x18001314d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013152  call    GetProcessHeap_0
0x180013157  mov     r8, rbx; lpMem
0x18001315a  xor     edx, edx; dwFlags
0x18001315c  mov     rcx, rax; hHeap
0x18001315f  call    HeapFree_0
0x180013164  mov     rbx, [rbp+lpMem]
0x180013168  lea     rcx, [rbp+lpMem]
0x18001316c  mov     rax, [rbx]
0x18001316f  mov     [rbp+lpMem], rax
0x180013173  mov     [rax+8], rcx
0x180013177  lea     rax, [rbp+lpMem]
0x18001317b  cmp     rbx, rax
0x18001317e  jnz     short loc_180013140
0x180013180  lea     r11, [rsp+50h+var_s0]
0x180013185  mov     eax, edi
0x180013187  mov     rbx, [r11+30h]
0x18001318b  mov     rsi, [r11+38h]
0x18001318f  mov     rsp, r11
0x180013192  pop     r15
0x180013194  pop     rdi
0x180013195  pop     rbp
0x180013196  retn
```
