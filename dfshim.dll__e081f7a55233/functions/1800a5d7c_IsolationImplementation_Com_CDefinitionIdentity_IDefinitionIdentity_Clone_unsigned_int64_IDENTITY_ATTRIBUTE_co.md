# IsolationImplementation::Com::CDefinitionIdentity::IDefinitionIdentity_Clone(unsigned __int64,_IDENTITY_ATTRIBUTE const * const,IDefinitionIdentity * *)

- ea: `0x1800a5d7c`
- end: `0x1800a60d3`
- name: `?IDefinitionIdentity_Clone@CDefinitionIdentity@Com@IsolationImplementation@@IEAAJ_KQEBU_IDENTITY_ATTRIBUTE@@PEAPEAUIDefinitionIdentity@@@Z`
- size: `855`
- prototype: `__int64 __fastcall(IsolationImplementation::Com::CDefinitionIdentity *__hidden this, unsigned __int64, const struct _IDENTITY_ATTRIBUTE *const, struct IDefinitionIdentity **)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800a5a70`

## callees

- `0x1800069b5`
- `0x1800069c1`
- `0x180012acc`
- `0x180012b38`
- `0x1800144d0`
- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x18001aa4c`
- `0x180043644`
- `0x1800436cc`
- `0x1800a5980`
- `0x1800a5a80`
- `0x1800a5d7c`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a5e30`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a5f02`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a5e30`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a5f02`

## string_xrefs

- `0x1800a5da1`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\definitionidentity.cpp`
- `0x1800a5eb7`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\definitionidentity.cpp`
- `0x1800a5f40`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\definitionidentity.cpp`
- `0x1800a5ffc`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\definitionidentity.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CDefinitionIdentity::IDefinitionIdentity_Clone(
        IsolationImplementation::Com::CDefinitionIdentity *this,
        unsigned __int64 a2,
        const struct _IDENTITY_ATTRIBUTE *const a3,
        struct IDefinitionIdentity **a4)
{
  unsigned int v7; // edi
  int v8; // ecx
  int v9; // ebx
  struct Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE *v10; // r9
  int v11; // edx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  unsigned __int64 v15; // rbx
  __int64 v16; // r14
  int v17; // eax
  __int64 v18; // rdx
  int DefinitionIdentity; // eax
  unsigned int v20; // ebx
  int v21; // edx
  void (__fastcall *v22)(LPVOID *); // rax
  HANDLE ProcessHeap_0; // rax
  LPVOID *v24; // rbx
  void (__fastcall *v25)(LPVOID *); // rax
  HANDLE v26; // rax
  LPVOID *v27; // rbx
  __int64 v28; // rbx
  int v29; // eax
  void (__fastcall *v30)(LPVOID *); // rax
  HANDLE v31; // rax
  LPVOID *v32; // rbx
  void (__fastcall *v33)(LPVOID *); // rax
  HANDLE v34; // rax
  LPVOID *v35; // rbx
  unsigned int v37; // [rsp+20h] [rbp-40h]
  unsigned int v38; // [rsp+20h] [rbp-40h]
  LPVOID lpMem[2]; // [rsp+30h] [rbp-30h] BYREF
  IsolationImplementation::Com *v40[2]; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int64 v41; // [rsp+50h] [rbp-10h]
  unsigned __int64 v42; // [rsp+58h] [rbp-8h]
  __int64 v44; // [rsp+98h] [rbp+38h] BYREF

  LODWORD(v41) = -2147023537;
  v40[0] = (IsolationImplementation::Com *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\definitionidentity.cpp";
  if ( a4 )
    *a4 = 0;
  if ( a2 && !a3 )
  {
    LODWORD(v40[1]) = 164;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(v40);
    return (unsigned int)v41;
  }
  if ( !a4 )
  {
    LODWORD(v40[1]) = 165;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(v40);
    return (unsigned int)v41;
  }
  v41 = 0;
  v42 = 0;
  *(_OWORD *)v40 = 0;
  v9 = *(_DWORD *)BCL::Nt::CSmartArrayHolder<unsigned __int64,Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE,BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>>::EnlargeNoPreserve(
                    v40,
                    &v44,
                    a2);
  if ( v9 >= 0 )
  {
    v15 = v42;
    lpMem[1] = lpMem;
    v16 = 0;
    lpMem[0] = lpMem;
    if ( a2 )
    {
      while ( 1 )
      {
        if ( v15 < v41 )
          v15 = v41;
        v42 = v15;
        v17 = IsolationImplementation::Com::ConvertIn(
                v40[1],
                (const struct _IDENTITY_ATTRIBUTE *const)((char *)a3 + 24 * v16),
                (IsolationImplementation::Com *)((char *)v40[1] + 72 * v16),
                v10);
        v7 = v17;
        if ( v17 < 0 )
          break;
        if ( ++v16 >= a2 )
          goto LABEL_18;
      }
      Windows::ErrorHandling::COM::ReportErrorPropagation(
        (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\definitionidentity.cpp",
        (const char *)0xAE,
        v17,
        (int)v10);
      while ( 1 )
      {
        v24 = (LPVOID *)lpMem[0];
        lpMem[0] = *(LPVOID *)lpMem[0];
        *((_QWORD *)lpMem[0] + 1) = lpMem;
        if ( v24 == lpMem )
          break;
        v22 = (void (__fastcall *)(LPVOID *))v24[2];
        if ( v22 )
          v22(v24 + 3);
        ProcessHeap_0 = GetProcessHeap_0();
        HeapFree_0(ProcessHeap_0, 0, v24);
      }
    }
    else
    {
LABEL_18:
      if ( v15 < v41 )
        v15 = v41;
      v18 = *((_QWORD *)this + 2);
      v44 = 0;
      v42 = v15;
      DefinitionIdentity = RtlCreateDefinitionIdentity(v8, v18, a2, v40[1], (__int64)&v44);
      v20 = DefinitionIdentity;
      if ( DefinitionIdentity >= 0 )
      {
        v28 = v44;
        v29 = IsolationImplementation::Com::CopyOut(v44, &GUID_587bf538_4d90_4a3c_9ef1_58a200a8a9e7, a4);
        v7 = v29;
        if ( v29 >= 0 )
        {
          v7 = 0;
          if ( v28 )
            RtlCloseDefinitionIdentityHandle(v28);
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
            v34 = GetProcessHeap_0();
            HeapFree_0(v34, 0, v35);
          }
        }
        else
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\definitionidentity.cpp",
            (const char *)0xB4,
            v29,
            v14);
          if ( v28 )
            RtlCloseDefinitionIdentityHandle(v28);
          while ( 1 )
          {
            v32 = (LPVOID *)lpMem[0];
            lpMem[0] = *(LPVOID *)lpMem[0];
            *((_QWORD *)lpMem[0] + 1) = lpMem;
            if ( v32 == lpMem )
              break;
            v30 = (void (__fastcall *)(LPVOID *))v32[2];
            if ( v30 )
              v30(v32 + 3);
            v31 = GetProcessHeap_0();
            HeapFree_0(v31, 0, v32);
          }
        }
      }
      else
      {
        if ( DefinitionIdentity == g_NTSTATUS_to_break_on_propagate )
          DebugBreak();
        Windows::ErrorHandling::COM::ReportError(
          (Windows::ErrorHandling::COM *)"Status propagated",
          "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\definitionidentity.cpp",
          (const char *)0xB2,
          v20,
          v38);
        v7 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v20, v21);
        if ( v44 )
          RtlCloseDefinitionIdentityHandle(v44);
        while ( 1 )
        {
          v27 = (LPVOID *)lpMem[0];
          lpMem[0] = *(LPVOID *)lpMem[0];
          *((_QWORD *)lpMem[0] + 1) = lpMem;
          if ( v27 == lpMem )
            break;
          v25 = (void (__fastcall *)(LPVOID *))v27[2];
          if ( v25 )
            v25(v27 + 3);
          v26 = GetProcessHeap_0();
          HeapFree_0(v26, 0, v27);
        }
      }
    }
  }
  else
  {
    if ( v9 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\definitionidentity.cpp",
      (const char *)0xA9,
      v9,
      v37);
    v7 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v9, v11);
  }
  BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_IDENTITY_UTF8_ATTRIBUTE,BCL::Nt::CCallDisposition>,BCL::Nt::CSmartInlineArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_IDENTITY_UTF8_ATTRIBUTE,BCL::Nt::CCallDisposition>,BCL::Nt::CSmartInlineArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(
    v40,
    v12,
    v13,
    v14);
  return v7;
}

```

## disassembly

```asm
0x1800a5d7c  mov     [rsp-28h+arg_10], rbx
0x1800a5d81  mov     [rsp-28h+arg_18], rsi
0x1800a5d86  mov     [rsp-28h+arg_0], rcx
0x1800a5d8b  push    rbp
0x1800a5d8c  push    rdi
0x1800a5d8d  push    r13
0x1800a5d8f  push    r14
0x1800a5d91  push    r15
0x1800a5d93  mov     rbp, rsp
0x1800a5d96  sub     rsp, 60h
0x1800a5d9a  mov     dword ptr [rbp+var_10], 8007054Fh
0x1800a5da1  lea     rdi, aOnecoreComNetf_7; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a5da8  mov     [rbp+var_20], rdi
0x1800a5dac  mov     r15, r9
0x1800a5daf  mov     r13, r8
0x1800a5db2  mov     rsi, rdx
0x1800a5db5  test    r9, r9
0x1800a5db8  jz      short loc_1800A5DC1
0x1800a5dba  mov     qword ptr [r9], 0
0x1800a5dc1  test    rsi, rsi
0x1800a5dc4  jz      short loc_1800A5DDD
0x1800a5dc6  test    r13, r13
0x1800a5dc9  jnz     short loc_1800A5DDD
0x1800a5dcb  mov     dword ptr [rbp+var_20+8], 0A4h
0x1800a5dd2  lea     rcx, [rbp+var_20]
0x1800a5dd6  call    ?SetInvalidParameter@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(void)
0x1800a5ddb  jmp     short loc_1800A5DF2
0x1800a5ddd  test    r15, r15
0x1800a5de0  jnz     short loc_1800A5DFA
0x1800a5de2  lea     rcx, [rbp+var_20]
0x1800a5de6  mov     dword ptr [rbp+var_20+8], 0A5h
0x1800a5ded  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x1800a5df2  mov     edi, dword ptr [rbp+var_10]
0x1800a5df5  jmp     loc_1800A60B8
0x1800a5dfa  xorps   xmm0, xmm0
0x1800a5dfd  mov     [rbp+var_10], 0
0x1800a5e05  mov     r8, rsi
0x1800a5e08  mov     [rbp+var_8], 0
0x1800a5e10  lea     rdx, [rbp+arg_8]
0x1800a5e14  lea     rcx, [rbp+var_20]
0x1800a5e18  movdqu  xmmword ptr [rbp+var_20], xmm0
0x1800a5e1d  call    ?EnlargeNoPreserve@?$CSmartArrayHolder@_KU_IDENTITY_ATTRIBUTE@Rtl@Isolation@Windows@@V?$CDefaultObjectTraits@U_IDENTITY_ATTRIBUTE@Rtl@Isolation@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@6@@Nt@BCL@@QEAA?AVCCallDisposition@23@_K@Z; BCL::Nt::CSmartArrayHolder<unsigned __int64,Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE,BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>>::EnlargeNoPreserve(unsigned __int64)
0x1800a5e22  mov     ebx, [rax]
0x1800a5e24  test    ebx, ebx
0x1800a5e26  jns     short loc_1800A5E5C
0x1800a5e28  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x1800a5e2e  jnz     short loc_1800A5E36
0x1800a5e30  call    cs:__imp_DebugBreak
0x1800a5e36  mov     r9d, ebx; int
0x1800a5e39  lea     rcx, aStatusPropagat; "Status propagated"
0x1800a5e40  mov     r8d, 0A9h; char *
0x1800a5e46  mov     rdx, rdi; char *
0x1800a5e49  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800a5e4e  mov     ecx, ebx; this
0x1800a5e50  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800a5e55  mov     edi, eax
0x1800a5e57  jmp     loc_1800A60AF
0x1800a5e5c  mov     rbx, [rbp+var_8]
0x1800a5e60  lea     rax, [rbp+lpMem]
0x1800a5e64  mov     [rbp+var_28], rax
0x1800a5e68  xor     r14d, r14d
0x1800a5e6b  lea     rax, [rbp+lpMem]
0x1800a5e6f  mov     [rbp+lpMem], rax
0x1800a5e73  test    rsi, rsi
0x1800a5e76  jz      short loc_1800A5EBE
0x1800a5e78  mov     rcx, [rbp+var_20+8]; this
0x1800a5e7c  lea     rax, [r14+r14*8]
0x1800a5e80  cmp     rbx, [rbp+var_10]
0x1800a5e84  cmovb   rbx, [rbp+var_10]
0x1800a5e89  lea     r8, [rcx+rax*8]; struct _IDENTITY_ATTRIBUTE *
0x1800a5e8d  mov     [rbp+var_8], rbx
0x1800a5e91  lea     rax, [r14+r14*2]
0x1800a5e95  lea     rdx, ds:0[rax*8]
0x1800a5e9d  add     rdx, r13; struct _RTL_ALLOCATION_LIST *
0x1800a5ea0  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAU_RTL_ALLOCATION_LIST@@AEBU_IDENTITY_ATTRIBUTE@@AEAU4Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(_RTL_ALLOCATION_LIST *,_IDENTITY_ATTRIBUTE const &,Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE &)
0x1800a5ea5  mov     edi, eax
0x1800a5ea7  test    eax, eax
0x1800a5ea9  js      loc_1800A5F3D
0x1800a5eaf  inc     r14
0x1800a5eb2  cmp     r14, rsi
0x1800a5eb5  jb      short loc_1800A5E78
0x1800a5eb7  lea     rdi, aOnecoreComNetf_7; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a5ebe  mov     rdx, [rbp+arg_0]
0x1800a5ec2  lea     rax, [rbp+arg_8]
0x1800a5ec6  cmp     rbx, [rbp+var_10]
0x1800a5eca  mov     r8, rsi
0x1800a5ecd  mov     r9, [rbp+var_20+8]
0x1800a5ed1  cmovb   rbx, [rbp+var_10]
0x1800a5ed6  mov     rdx, [rdx+10h]
0x1800a5eda  mov     [rbp+arg_8], 0
0x1800a5ee2  mov     [rbp+var_8], rbx
0x1800a5ee6  mov     qword ptr [rsp+60h+var_40], rax; unsigned int
0x1800a5eeb  call    RtlCreateDefinitionIdentity
0x1800a5ef0  mov     ebx, eax
0x1800a5ef2  test    eax, eax
0x1800a5ef4  jns     loc_1800A5FDD
0x1800a5efa  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800a5f00  jnz     short loc_1800A5F08
0x1800a5f02  call    cs:__imp_DebugBreak
0x1800a5f08  mov     r9d, ebx; int
0x1800a5f0b  lea     rcx, aStatusPropagat; "Status propagated"
0x1800a5f12  mov     r8d, 0B2h; char *
0x1800a5f18  mov     rdx, rdi; char *
0x1800a5f1b  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800a5f20  mov     ecx, ebx; this
0x1800a5f22  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800a5f27  mov     rcx, [rbp+arg_8]
0x1800a5f2b  mov     edi, eax
0x1800a5f2d  test    rcx, rcx
0x1800a5f30  jz      loc_1800A5FBC
0x1800a5f36  call    RtlCloseDefinitionIdentityHandle
0x1800a5f3b  jmp     short loc_1800A5FBC
0x1800a5f3d  mov     r8d, eax; int
0x1800a5f40  lea     rcx, aOnecoreComNetf_7; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a5f47  mov     edx, 0AEh; char *
0x1800a5f4c  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800a5f51  jmp     short loc_1800A5F77
0x1800a5f53  mov     rax, [rbx+10h]
0x1800a5f57  test    rax, rax
0x1800a5f5a  jz      short loc_1800A5F65
0x1800a5f5c  lea     rcx, [rbx+18h]
0x1800a5f60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5f65  call    GetProcessHeap_0
0x1800a5f6a  mov     r8, rbx; lpMem
0x1800a5f6d  xor     edx, edx; dwFlags
0x1800a5f6f  mov     rcx, rax; hHeap
0x1800a5f72  call    HeapFree_0
0x1800a5f77  mov     rbx, [rbp+lpMem]
0x1800a5f7b  lea     rcx, [rbp+lpMem]
0x1800a5f7f  mov     rax, [rbx]
0x1800a5f82  mov     [rbp+lpMem], rax
0x1800a5f86  mov     [rax+8], rcx
0x1800a5f8a  lea     rax, [rbp+lpMem]
0x1800a5f8e  cmp     rbx, rax
0x1800a5f91  jnz     short loc_1800A5F53
0x1800a5f93  jmp     loc_1800A60AF
0x1800a5f98  mov     rax, [rbx+10h]
0x1800a5f9c  test    rax, rax
0x1800a5f9f  jz      short loc_1800A5FAA
0x1800a5fa1  lea     rcx, [rbx+18h]
0x1800a5fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5faa  call    GetProcessHeap_0
0x1800a5faf  mov     r8, rbx; lpMem
0x1800a5fb2  xor     edx, edx; dwFlags
0x1800a5fb4  mov     rcx, rax; hHeap
0x1800a5fb7  call    HeapFree_0
0x1800a5fbc  mov     rbx, [rbp+lpMem]
0x1800a5fc0  lea     rcx, [rbp+lpMem]
0x1800a5fc4  mov     rax, [rbx]
0x1800a5fc7  mov     [rbp+lpMem], rax
0x1800a5fcb  mov     [rax+8], rcx
0x1800a5fcf  lea     rax, [rbp+lpMem]
0x1800a5fd3  cmp     rbx, rax
0x1800a5fd6  jnz     short loc_1800A5F98
0x1800a5fd8  jmp     loc_1800A60AF
0x1800a5fdd  mov     rbx, [rbp+arg_8]
0x1800a5fe1  lea     rdx, _GUID_587bf538_4d90_4a3c_9ef1_58a200a8a9e7
0x1800a5fe8  mov     rcx, rbx
0x1800a5feb  mov     r8, r15
0x1800a5fee  call    ?CopyOut@Com@IsolationImplementation@@YAJU_DEFINITION_IDENTITY@Rtl@Isolation@Windows@@AEBU_GUID@@PEAPEAUIUnknown@@@Z; IsolationImplementation::Com::CopyOut(Windows::Isolation::Rtl::_DEFINITION_IDENTITY,_GUID const &,IUnknown * *)
0x1800a5ff3  mov     edi, eax
0x1800a5ff5  test    eax, eax
0x1800a5ff7  jns     short loc_1800A605E
0x1800a5ff9  mov     r8d, eax; int
0x1800a5ffc  lea     rcx, aOnecoreComNetf_7; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a6003  mov     edx, 0B4h; char *
0x1800a6008  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800a600d  test    rbx, rbx
0x1800a6010  jz      short loc_1800A6040
0x1800a6012  mov     rcx, rbx
0x1800a6015  call    RtlCloseDefinitionIdentityHandle
0x1800a601a  jmp     short loc_1800A6040
0x1800a601c  mov     rax, [rbx+10h]
0x1800a6020  test    rax, rax
0x1800a6023  jz      short loc_1800A602E
0x1800a6025  lea     rcx, [rbx+18h]
0x1800a6029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a602e  call    GetProcessHeap_0
0x1800a6033  mov     r8, rbx; lpMem
0x1800a6036  xor     edx, edx; dwFlags
0x1800a6038  mov     rcx, rax; hHeap
0x1800a603b  call    HeapFree_0
0x1800a6040  mov     rbx, [rbp+lpMem]
0x1800a6044  lea     rcx, [rbp+lpMem]
0x1800a6048  mov     rax, [rbx]
0x1800a604b  mov     [rbp+lpMem], rax
0x1800a604f  mov     [rax+8], rcx
0x1800a6053  lea     rax, [rbp+lpMem]
0x1800a6057  cmp     rbx, rax
0x1800a605a  jnz     short loc_1800A601C
0x1800a605c  jmp     short loc_1800A60AF
0x1800a605e  xor     edi, edi
0x1800a6060  test    rbx, rbx
0x1800a6063  jz      short loc_1800A6093
0x1800a6065  mov     rcx, rbx
0x1800a6068  call    RtlCloseDefinitionIdentityHandle
0x1800a606d  jmp     short loc_1800A6093
0x1800a606f  mov     rax, [rbx+10h]
0x1800a6073  test    rax, rax
0x1800a6076  jz      short loc_1800A6081
0x1800a6078  lea     rcx, [rbx+18h]
0x1800a607c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6081  call    GetProcessHeap_0
0x1800a6086  mov     r8, rbx; lpMem
0x1800a6089  xor     edx, edx; dwFlags
0x1800a608b  mov     rcx, rax; hHeap
0x1800a608e  call    HeapFree_0
0x1800a6093  mov     rbx, [rbp+lpMem]
0x1800a6097  lea     rcx, [rbp+lpMem]
0x1800a609b  mov     rax, [rbx]
0x1800a609e  mov     [rbp+lpMem], rax
0x1800a60a2  mov     [rax+8], rcx
0x1800a60a6  lea     rax, [rbp+lpMem]
0x1800a60aa  cmp     rbx, rax
0x1800a60ad  jnz     short loc_1800A606F
0x1800a60af  lea     rcx, [rbp+var_20]
0x1800a60b3  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_IDENTITY_UTF8_ATTRIBUTE@Rtl@Isolation@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CSmartInlineArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_IDENTITY_UTF8_ATTRIBUTE,BCL::Nt::CCallDisposition>,BCL::Nt::CSmartInlineArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_IDENTITY_UTF8_ATTRIBUTE,BCL::Nt::CCallDisposition>,BCL::Nt::CSmartInlineArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(void)
0x1800a60b8  lea     r11, [rsp+60h+var_s0]
0x1800a60bd  mov     eax, edi
0x1800a60bf  mov     rbx, [r11+40h]
0x1800a60c3  mov     rsi, [r11+48h]
0x1800a60c7  mov     rsp, r11
0x1800a60ca  pop     r15
0x1800a60cc  pop     r14
0x1800a60ce  pop     r13
0x1800a60d0  pop     rdi
0x1800a60d1  pop     rbp
0x1800a60d2  retn
```
