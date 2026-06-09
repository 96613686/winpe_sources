# IsolationImplementation::Com::CReferenceIdentity::IReferenceIdentity_Clone(unsigned __int64,_IDENTITY_ATTRIBUTE const * const,IReferenceIdentity * *)

- ea: `0x1800a6ba0`
- end: `0x1800a6ef7`
- name: `?IReferenceIdentity_Clone@CReferenceIdentity@Com@IsolationImplementation@@IEAAJ_KQEBU_IDENTITY_ATTRIBUTE@@PEAPEAUIReferenceIdentity@@@Z`
- size: `855`
- prototype: `__int64 __fastcall(IsolationImplementation::Com::CReferenceIdentity *__hidden this, unsigned __int64, const struct _IDENTITY_ATTRIBUTE *const, struct IReferenceIdentity **)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800a69d0`

## callees

- `0x1800069b5`
- `0x1800069c1`
- `0x180012acc`
- `0x180012b38`
- `0x1800144d0`
- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x18001ae14`
- `0x180044708`
- `0x180044790`
- `0x1800a5980`
- `0x1800a5a80`
- `0x1800a6ba0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a6c54`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a6d26`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a6c54`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a6d26`

## string_xrefs

- `0x1800a6bc5`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\referenceidentity.cpp`
- `0x1800a6cdb`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\referenceidentity.cpp`
- `0x1800a6d64`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\referenceidentity.cpp`
- `0x1800a6e20`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\referenceidentity.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CReferenceIdentity::IReferenceIdentity_Clone(
        IsolationImplementation::Com::CReferenceIdentity *this,
        unsigned __int64 a2,
        const struct _IDENTITY_ATTRIBUTE *const a3,
        struct IReferenceIdentity **a4)
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
  int ReferenceIdentity; // eax
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
  v40[0] = (IsolationImplementation::Com *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\referenceidentity.cpp";
  if ( a4 )
    *a4 = 0;
  if ( a2 && !a3 )
  {
    LODWORD(v40[1]) = 162;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(v40);
    return (unsigned int)v41;
  }
  if ( !a4 )
  {
    LODWORD(v40[1]) = 163;
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
        (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\referenceidentity.cpp",
        (const char *)0xAC,
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
      ReferenceIdentity = RtlCreateReferenceIdentity(v8, v18, a2, v40[1], (__int64)&v44);
      v20 = ReferenceIdentity;
      if ( ReferenceIdentity >= 0 )
      {
        v28 = v44;
        v29 = IsolationImplementation::Com::CopyOut(v44, &GUID_6eaf5ace_7917_4f3c_b129_e046a9704766, a4);
        v7 = v29;
        if ( v29 >= 0 )
        {
          v7 = 0;
          if ( v28 )
            RtlCloseReferenceIdentityHandle(v28);
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
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\referenceidentity.cpp",
            (const char *)0xB2,
            v29,
            v14);
          if ( v28 )
            RtlCloseReferenceIdentityHandle(v28);
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
        if ( ReferenceIdentity == g_NTSTATUS_to_break_on_propagate )
          DebugBreak();
        Windows::ErrorHandling::COM::ReportError(
          (Windows::ErrorHandling::COM *)"Status propagated",
          "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\referenceidentity.cpp",
          (const char *)0xB0,
          v20,
          v38);
        v7 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v20, v21);
        if ( v44 )
          RtlCloseReferenceIdentityHandle(v44);
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
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\referenceidentity.cpp",
      (const char *)0xA7,
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
0x1800a6ba0  mov     [rsp-28h+arg_10], rbx
0x1800a6ba5  mov     [rsp-28h+arg_18], rsi
0x1800a6baa  mov     [rsp-28h+arg_0], rcx
0x1800a6baf  push    rbp
0x1800a6bb0  push    rdi
0x1800a6bb1  push    r13
0x1800a6bb3  push    r14
0x1800a6bb5  push    r15
0x1800a6bb7  mov     rbp, rsp
0x1800a6bba  sub     rsp, 60h
0x1800a6bbe  mov     dword ptr [rbp+var_10], 8007054Fh
0x1800a6bc5  lea     rdi, aOnecoreComNetf_120; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a6bcc  mov     [rbp+var_20], rdi
0x1800a6bd0  mov     r15, r9
0x1800a6bd3  mov     r13, r8
0x1800a6bd6  mov     rsi, rdx
0x1800a6bd9  test    r9, r9
0x1800a6bdc  jz      short loc_1800A6BE5
0x1800a6bde  mov     qword ptr [r9], 0
0x1800a6be5  test    rsi, rsi
0x1800a6be8  jz      short loc_1800A6C01
0x1800a6bea  test    r13, r13
0x1800a6bed  jnz     short loc_1800A6C01
0x1800a6bef  mov     dword ptr [rbp+var_20+8], 0A2h
0x1800a6bf6  lea     rcx, [rbp+var_20]
0x1800a6bfa  call    ?SetInvalidParameter@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(void)
0x1800a6bff  jmp     short loc_1800A6C16
0x1800a6c01  test    r15, r15
0x1800a6c04  jnz     short loc_1800A6C1E
0x1800a6c06  lea     rcx, [rbp+var_20]
0x1800a6c0a  mov     dword ptr [rbp+var_20+8], 0A3h
0x1800a6c11  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x1800a6c16  mov     edi, dword ptr [rbp+var_10]
0x1800a6c19  jmp     loc_1800A6EDC
0x1800a6c1e  xorps   xmm0, xmm0
0x1800a6c21  mov     [rbp+var_10], 0
0x1800a6c29  mov     r8, rsi
0x1800a6c2c  mov     [rbp+var_8], 0
0x1800a6c34  lea     rdx, [rbp+arg_8]
0x1800a6c38  lea     rcx, [rbp+var_20]
0x1800a6c3c  movdqu  xmmword ptr [rbp+var_20], xmm0
0x1800a6c41  call    ?EnlargeNoPreserve@?$CSmartArrayHolder@_KU_IDENTITY_ATTRIBUTE@Rtl@Isolation@Windows@@V?$CDefaultObjectTraits@U_IDENTITY_ATTRIBUTE@Rtl@Isolation@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@6@@Nt@BCL@@QEAA?AVCCallDisposition@23@_K@Z; BCL::Nt::CSmartArrayHolder<unsigned __int64,Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE,BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>>::EnlargeNoPreserve(unsigned __int64)
0x1800a6c46  mov     ebx, [rax]
0x1800a6c48  test    ebx, ebx
0x1800a6c4a  jns     short loc_1800A6C80
0x1800a6c4c  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x1800a6c52  jnz     short loc_1800A6C5A
0x1800a6c54  call    cs:__imp_DebugBreak
0x1800a6c5a  mov     r9d, ebx; int
0x1800a6c5d  lea     rcx, aStatusPropagat; "Status propagated"
0x1800a6c64  mov     r8d, 0A7h; char *
0x1800a6c6a  mov     rdx, rdi; char *
0x1800a6c6d  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800a6c72  mov     ecx, ebx; this
0x1800a6c74  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800a6c79  mov     edi, eax
0x1800a6c7b  jmp     loc_1800A6ED3
0x1800a6c80  mov     rbx, [rbp+var_8]
0x1800a6c84  lea     rax, [rbp+lpMem]
0x1800a6c88  mov     [rbp+var_28], rax
0x1800a6c8c  xor     r14d, r14d
0x1800a6c8f  lea     rax, [rbp+lpMem]
0x1800a6c93  mov     [rbp+lpMem], rax
0x1800a6c97  test    rsi, rsi
0x1800a6c9a  jz      short loc_1800A6CE2
0x1800a6c9c  mov     rcx, [rbp+var_20+8]; this
0x1800a6ca0  lea     rax, [r14+r14*8]
0x1800a6ca4  cmp     rbx, [rbp+var_10]
0x1800a6ca8  cmovb   rbx, [rbp+var_10]
0x1800a6cad  lea     r8, [rcx+rax*8]; struct _IDENTITY_ATTRIBUTE *
0x1800a6cb1  mov     [rbp+var_8], rbx
0x1800a6cb5  lea     rax, [r14+r14*2]
0x1800a6cb9  lea     rdx, ds:0[rax*8]
0x1800a6cc1  add     rdx, r13; struct _RTL_ALLOCATION_LIST *
0x1800a6cc4  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAU_RTL_ALLOCATION_LIST@@AEBU_IDENTITY_ATTRIBUTE@@AEAU4Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(_RTL_ALLOCATION_LIST *,_IDENTITY_ATTRIBUTE const &,Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE &)
0x1800a6cc9  mov     edi, eax
0x1800a6ccb  test    eax, eax
0x1800a6ccd  js      loc_1800A6D61
0x1800a6cd3  inc     r14
0x1800a6cd6  cmp     r14, rsi
0x1800a6cd9  jb      short loc_1800A6C9C
0x1800a6cdb  lea     rdi, aOnecoreComNetf_120; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a6ce2  mov     rdx, [rbp+arg_0]
0x1800a6ce6  lea     rax, [rbp+arg_8]
0x1800a6cea  cmp     rbx, [rbp+var_10]
0x1800a6cee  mov     r8, rsi
0x1800a6cf1  mov     r9, [rbp+var_20+8]
0x1800a6cf5  cmovb   rbx, [rbp+var_10]
0x1800a6cfa  mov     rdx, [rdx+10h]
0x1800a6cfe  mov     [rbp+arg_8], 0
0x1800a6d06  mov     [rbp+var_8], rbx
0x1800a6d0a  mov     qword ptr [rsp+60h+var_40], rax; unsigned int
0x1800a6d0f  call    RtlCreateReferenceIdentity
0x1800a6d14  mov     ebx, eax
0x1800a6d16  test    eax, eax
0x1800a6d18  jns     loc_1800A6E01
0x1800a6d1e  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800a6d24  jnz     short loc_1800A6D2C
0x1800a6d26  call    cs:__imp_DebugBreak
0x1800a6d2c  mov     r9d, ebx; int
0x1800a6d2f  lea     rcx, aStatusPropagat; "Status propagated"
0x1800a6d36  mov     r8d, 0B0h; char *
0x1800a6d3c  mov     rdx, rdi; char *
0x1800a6d3f  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800a6d44  mov     ecx, ebx; this
0x1800a6d46  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800a6d4b  mov     rcx, [rbp+arg_8]
0x1800a6d4f  mov     edi, eax
0x1800a6d51  test    rcx, rcx
0x1800a6d54  jz      loc_1800A6DE0
0x1800a6d5a  call    RtlCloseReferenceIdentityHandle
0x1800a6d5f  jmp     short loc_1800A6DE0
0x1800a6d61  mov     r8d, eax; int
0x1800a6d64  lea     rcx, aOnecoreComNetf_120; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a6d6b  mov     edx, 0ACh; char *
0x1800a6d70  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800a6d75  jmp     short loc_1800A6D9B
0x1800a6d77  mov     rax, [rbx+10h]
0x1800a6d7b  test    rax, rax
0x1800a6d7e  jz      short loc_1800A6D89
0x1800a6d80  lea     rcx, [rbx+18h]
0x1800a6d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6d89  call    GetProcessHeap_0
0x1800a6d8e  mov     r8, rbx; lpMem
0x1800a6d91  xor     edx, edx; dwFlags
0x1800a6d93  mov     rcx, rax; hHeap
0x1800a6d96  call    HeapFree_0
0x1800a6d9b  mov     rbx, [rbp+lpMem]
0x1800a6d9f  lea     rcx, [rbp+lpMem]
0x1800a6da3  mov     rax, [rbx]
0x1800a6da6  mov     [rbp+lpMem], rax
0x1800a6daa  mov     [rax+8], rcx
0x1800a6dae  lea     rax, [rbp+lpMem]
0x1800a6db2  cmp     rbx, rax
0x1800a6db5  jnz     short loc_1800A6D77
0x1800a6db7  jmp     loc_1800A6ED3
0x1800a6dbc  mov     rax, [rbx+10h]
0x1800a6dc0  test    rax, rax
0x1800a6dc3  jz      short loc_1800A6DCE
0x1800a6dc5  lea     rcx, [rbx+18h]
0x1800a6dc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6dce  call    GetProcessHeap_0
0x1800a6dd3  mov     r8, rbx; lpMem
0x1800a6dd6  xor     edx, edx; dwFlags
0x1800a6dd8  mov     rcx, rax; hHeap
0x1800a6ddb  call    HeapFree_0
0x1800a6de0  mov     rbx, [rbp+lpMem]
0x1800a6de4  lea     rcx, [rbp+lpMem]
0x1800a6de8  mov     rax, [rbx]
0x1800a6deb  mov     [rbp+lpMem], rax
0x1800a6def  mov     [rax+8], rcx
0x1800a6df3  lea     rax, [rbp+lpMem]
0x1800a6df7  cmp     rbx, rax
0x1800a6dfa  jnz     short loc_1800A6DBC
0x1800a6dfc  jmp     loc_1800A6ED3
0x1800a6e01  mov     rbx, [rbp+arg_8]
0x1800a6e05  lea     rdx, _GUID_6eaf5ace_7917_4f3c_b129_e046a9704766
0x1800a6e0c  mov     rcx, rbx
0x1800a6e0f  mov     r8, r15
0x1800a6e12  call    ?CopyOut@Com@IsolationImplementation@@YAJU_REFERENCE_IDENTITY@Rtl@Isolation@Windows@@AEBU_GUID@@PEAPEAUIUnknown@@@Z; IsolationImplementation::Com::CopyOut(Windows::Isolation::Rtl::_REFERENCE_IDENTITY,_GUID const &,IUnknown * *)
0x1800a6e17  mov     edi, eax
0x1800a6e19  test    eax, eax
0x1800a6e1b  jns     short loc_1800A6E82
0x1800a6e1d  mov     r8d, eax; int
0x1800a6e20  lea     rcx, aOnecoreComNetf_120; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a6e27  mov     edx, 0B2h; char *
0x1800a6e2c  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800a6e31  test    rbx, rbx
0x1800a6e34  jz      short loc_1800A6E64
0x1800a6e36  mov     rcx, rbx
0x1800a6e39  call    RtlCloseReferenceIdentityHandle
0x1800a6e3e  jmp     short loc_1800A6E64
0x1800a6e40  mov     rax, [rbx+10h]
0x1800a6e44  test    rax, rax
0x1800a6e47  jz      short loc_1800A6E52
0x1800a6e49  lea     rcx, [rbx+18h]
0x1800a6e4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6e52  call    GetProcessHeap_0
0x1800a6e57  mov     r8, rbx; lpMem
0x1800a6e5a  xor     edx, edx; dwFlags
0x1800a6e5c  mov     rcx, rax; hHeap
0x1800a6e5f  call    HeapFree_0
0x1800a6e64  mov     rbx, [rbp+lpMem]
0x1800a6e68  lea     rcx, [rbp+lpMem]
0x1800a6e6c  mov     rax, [rbx]
0x1800a6e6f  mov     [rbp+lpMem], rax
0x1800a6e73  mov     [rax+8], rcx
0x1800a6e77  lea     rax, [rbp+lpMem]
0x1800a6e7b  cmp     rbx, rax
0x1800a6e7e  jnz     short loc_1800A6E40
0x1800a6e80  jmp     short loc_1800A6ED3
0x1800a6e82  xor     edi, edi
0x1800a6e84  test    rbx, rbx
0x1800a6e87  jz      short loc_1800A6EB7
0x1800a6e89  mov     rcx, rbx
0x1800a6e8c  call    RtlCloseReferenceIdentityHandle
0x1800a6e91  jmp     short loc_1800A6EB7
0x1800a6e93  mov     rax, [rbx+10h]
0x1800a6e97  test    rax, rax
0x1800a6e9a  jz      short loc_1800A6EA5
0x1800a6e9c  lea     rcx, [rbx+18h]
0x1800a6ea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6ea5  call    GetProcessHeap_0
0x1800a6eaa  mov     r8, rbx; lpMem
0x1800a6ead  xor     edx, edx; dwFlags
0x1800a6eaf  mov     rcx, rax; hHeap
0x1800a6eb2  call    HeapFree_0
0x1800a6eb7  mov     rbx, [rbp+lpMem]
0x1800a6ebb  lea     rcx, [rbp+lpMem]
0x1800a6ebf  mov     rax, [rbx]
0x1800a6ec2  mov     [rbp+lpMem], rax
0x1800a6ec6  mov     [rax+8], rcx
0x1800a6eca  lea     rax, [rbp+lpMem]
0x1800a6ece  cmp     rbx, rax
0x1800a6ed1  jnz     short loc_1800A6E93
0x1800a6ed3  lea     rcx, [rbp+var_20]
0x1800a6ed7  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_IDENTITY_UTF8_ATTRIBUTE@Rtl@Isolation@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CSmartInlineArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_IDENTITY_UTF8_ATTRIBUTE,BCL::Nt::CCallDisposition>,BCL::Nt::CSmartInlineArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_IDENTITY_UTF8_ATTRIBUTE,BCL::Nt::CCallDisposition>,BCL::Nt::CSmartInlineArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(void)
0x1800a6edc  lea     r11, [rsp+60h+var_s0]
0x1800a6ee1  mov     eax, edi
0x1800a6ee3  mov     rbx, [r11+40h]
0x1800a6ee7  mov     rsi, [r11+48h]
0x1800a6eeb  mov     rsp, r11
0x1800a6eee  pop     r15
0x1800a6ef0  pop     r14
0x1800a6ef2  pop     r13
0x1800a6ef4  pop     rdi
0x1800a6ef5  pop     rbp
0x1800a6ef6  retn
```
