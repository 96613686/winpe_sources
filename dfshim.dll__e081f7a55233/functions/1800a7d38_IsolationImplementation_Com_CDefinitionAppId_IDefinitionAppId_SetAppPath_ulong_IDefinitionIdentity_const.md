# IsolationImplementation::Com::CDefinitionAppId::IDefinitionAppId_SetAppPath(ulong,IDefinitionIdentity * * const)

- ea: `0x1800a7d38`
- end: `0x1800a8190`
- name: `?IDefinitionAppId_SetAppPath@CDefinitionAppId@Com@IsolationImplementation@@IEAAJKQEAPEAUIDefinitionIdentity@@@Z`
- size: `1112`
- prototype: `__int64 __fastcall(IsolationImplementation::Com::CDefinitionAppId *__hidden this, unsigned int, struct IDefinitionIdentity **const)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800a8820`

## callees

- `0x1800069b5`
- `0x1800069c1`
- `0x180012acc`
- `0x180012b38`
- `0x1800187f0`
- `0x180018940`
- `0x180030674`
- `0x18003ee70`
- `0x1800a77cc`
- `0x1800a7a18`
- `0x1800a7d38`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a7e3b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a8025`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a8067`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a7e3b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a8025`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a8067`

## string_xrefs

- `0x1800a7d74`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\definitionappid.cpp`
- `0x1800a802e`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\definitionappid.cpp`
- `0x1800a8070`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\definitionappid.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CDefinitionAppId::IDefinitionAppId_SetAppPath(
        IsolationImplementation::Com::CDefinitionAppId *this,
        unsigned int a2,
        struct IDefinitionIdentity **const a3)
{
  __int64 v3; // rdi
  IsolationImplementation::Com::CDefinitionAppId *v5; // r14
  void (__fastcall *v6)(LPVOID *); // rax
  HANDLE ProcessHeap_0; // rax
  LPVOID *v8; // rbx
  int v9; // ecx
  unsigned __int64 v10; // rcx
  struct Windows::Isolation::Rtl::_DEFINITION_IDENTITY *v11; // r8
  int v12; // r9d
  unsigned int v13; // ebx
  int v14; // edx
  unsigned int v15; // edi
  LPVOID *v16; // rbx
  void (__fastcall *v17)(LPVOID *); // rax
  HANDLE v18; // rax
  LPVOID *v19; // rbx
  void (__fastcall *v20)(LPVOID *); // rax
  HANDLE v21; // rax
  __int64 v22; // r13
  unsigned int v23; // r15d
  unsigned __int64 v24; // rsi
  unsigned __int64 v25; // rbx
  _QWORD *v26; // rdx
  unsigned __int64 v27; // rcx
  _QWORD *v28; // rax
  int v29; // r14d
  _QWORD *v30; // rdx
  _QWORD *v31; // rax
  __int64 v32; // rdx
  int v33; // eax
  unsigned int v34; // ebx
  int v35; // edx
  int v36; // edx
  void (__fastcall *v37)(LPVOID *); // rax
  HANDLE v38; // rax
  LPVOID *v39; // rbx
  void (__fastcall *v40)(LPVOID *); // rax
  HANDLE v41; // rax
  LPVOID *v42; // rbx
  void (__fastcall *v43)(LPVOID *); // rax
  HANDLE v44; // rax
  LPVOID *v45; // rbx
  unsigned int v47; // [rsp+20h] [rbp-89h]
  LPVOID lpMem[2]; // [rsp+30h] [rbp-79h] BYREF
  __int128 v49; // [rsp+40h] [rbp-69h] BYREF
  unsigned __int64 v50; // [rsp+50h] [rbp-59h]
  unsigned __int64 v51; // [rsp+58h] [rbp-51h]
  const char *v52; // [rsp+60h] [rbp-49h] BYREF
  int v53; // [rsp+68h] [rbp-41h]
  unsigned int v54; // [rsp+70h] [rbp-39h]
  _QWORD v55[7]; // [rsp+80h] [rbp-29h] BYREF
  __int128 v56; // [rsp+B8h] [rbp+Fh]
  __int64 v57; // [rsp+C8h] [rbp+1Fh]
  Windows::ErrorHandling::COM *v59; // [rsp+118h] [rbp+6Fh] BYREF

  v3 = a2;
  v54 = -2147023537;
  lpMem[1] = lpMem;
  lpMem[0] = lpMem;
  v52 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\definitionappid.cpp";
  v50 = 0;
  v51 = 0;
  v5 = this;
  v49 = 0;
  if ( a2 && !a3 )
  {
    v53 = 242;
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(&v49);
    while ( 1 )
    {
      v8 = (LPVOID *)lpMem[0];
      lpMem[0] = *(LPVOID *)lpMem[0];
      *((_QWORD *)lpMem[0] + 1) = lpMem;
      if ( v8 == lpMem )
        break;
      v6 = (void (__fastcall *)(LPVOID *))v8[2];
      if ( v6 )
        v6(v8 + 3);
      ProcessHeap_0 = GetProcessHeap_0();
      HeapFree_0(ProcessHeap_0, 0, v8);
    }
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(&v52);
    return v54;
  }
  v9 = 0;
  if ( a2 )
  {
    while ( a3[v9] )
    {
      if ( ++v9 == a2 )
        goto LABEL_12;
    }
    v53 = 245;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v52);
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(&v49);
    while ( 1 )
    {
      v19 = (LPVOID *)lpMem[0];
      lpMem[0] = *(LPVOID *)lpMem[0];
      *((_QWORD *)lpMem[0] + 1) = lpMem;
      if ( v19 == lpMem )
        break;
      v17 = (void (__fastcall *)(LPVOID *))v19[2];
      if ( v17 )
        v17(v19 + 3);
      v18 = GetProcessHeap_0();
      HeapFree_0(v18, 0, v19);
    }
    return v54;
  }
LABEL_12:
  BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::EnlargeGeneric(
    &v49,
    &v59,
    2,
    a2);
  v13 = (unsigned int)v59;
  if ( (int)v59 >= 0 )
  {
    v22 = *((_QWORD *)&v49 + 1);
    v23 = 0;
    v24 = v50;
    v25 = v51;
    if ( (_DWORD)v3 )
    {
      while ( 1 )
      {
        if ( v25 < v24 )
        {
          v26 = (_QWORD *)(v22 + 8 * v25);
          v27 = v24 - v25;
          if ( v24 != v25 )
          {
            do
            {
              v28 = v26++;
              *v28 = 0;
              --v27;
            }
            while ( v27 );
          }
          v25 = v24;
          v51 = v24;
        }
        v29 = IsolationImplementation::Com::ConvertIn(
                (__int64 (__fastcall ***)(IsolationImplementation::Com *, GUID *, __int64 *))a3[v23],
                (struct IDefinitionIdentity *)(v22 + 8LL * v23),
                v11);
        if ( v29 < 0 )
          break;
        if ( ++v23 == (_DWORD)v3 )
        {
          v5 = this;
          goto LABEL_35;
        }
      }
      if ( v29 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\definitionappid.cpp",
        (const char *)0x104,
        v29,
        v47);
      v15 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v29, v36);
      BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(&v49);
      while ( 1 )
      {
        v39 = (LPVOID *)lpMem[0];
        lpMem[0] = *(LPVOID *)lpMem[0];
        *((_QWORD *)lpMem[0] + 1) = lpMem;
        if ( v39 == lpMem )
          break;
        v37 = (void (__fastcall *)(LPVOID *))v39[2];
        if ( v37 )
          v37(v39 + 3);
        v38 = GetProcessHeap_0();
        HeapFree_0(v38, 0, v39);
      }
    }
    else
    {
LABEL_35:
      v55[0] = 80;
      memset(&v55[2], 0, 24);
      v55[1] = 2;
      v55[5] = v3;
      if ( v25 < v24 )
      {
        v30 = (_QWORD *)(v22 + 8 * v25);
        v10 = v24 - v25;
        if ( v24 != v25 )
        {
          do
          {
            v31 = v30++;
            *v31 = 0;
            --v10;
          }
          while ( v10 );
        }
        v51 = v24;
      }
      v32 = *((_QWORD *)v5 + 2);
      v57 = 0;
      v56 = 0;
      v55[6] = v22;
      v33 = RtlSetInformationDefinitionAppId(v10, v32, (unsigned int)v55, v12);
      v34 = v33;
      if ( v33 >= 0 )
      {
        v15 = 0;
        BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(&v49);
        while ( 1 )
        {
          v45 = (LPVOID *)lpMem[0];
          lpMem[0] = *(LPVOID *)lpMem[0];
          *((_QWORD *)lpMem[0] + 1) = lpMem;
          if ( v45 == lpMem )
            break;
          v43 = (void (__fastcall *)(LPVOID *))v45[2];
          if ( v43 )
            v43(v45 + 3);
          v44 = GetProcessHeap_0();
          HeapFree_0(v44, 0, v45);
        }
      }
      else
      {
        if ( v33 == g_NTSTATUS_to_break_on_propagate )
          DebugBreak();
        Windows::ErrorHandling::COM::ReportError(
          (Windows::ErrorHandling::COM *)"Status propagated",
          "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\definitionappid.cpp",
          (const char *)0x116,
          v34,
          v47);
        v15 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v34, v35);
        BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(&v49);
        while ( 1 )
        {
          v42 = (LPVOID *)lpMem[0];
          lpMem[0] = *(LPVOID *)lpMem[0];
          *((_QWORD *)lpMem[0] + 1) = lpMem;
          if ( v42 == lpMem )
            break;
          v40 = (void (__fastcall *)(LPVOID *))v42[2];
          if ( v40 )
            v40(v42 + 3);
          v41 = GetProcessHeap_0();
          HeapFree_0(v41, 0, v42);
        }
      }
    }
  }
  else
  {
    if ( (_DWORD)v59 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\definitionappid.cpp",
      (const char *)0xFA,
      v13,
      v47);
    v15 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v13, v14);
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(&v49);
    v16 = (LPVOID *)lpMem[0];
    lpMem[0] = *(LPVOID *)lpMem[0];
    *((_QWORD *)lpMem[0] + 1) = lpMem;
    while ( v16 != lpMem )
    {
      v20 = (void (__fastcall *)(LPVOID *))v16[2];
      if ( v20 )
        v20(v16 + 3);
      v21 = GetProcessHeap_0();
      HeapFree_0(v21, 0, v16);
      v16 = (LPVOID *)lpMem[0];
      lpMem[0] = *(LPVOID *)lpMem[0];
      *((_QWORD *)lpMem[0] + 1) = lpMem;
    }
  }
  return v15;
}

```

## disassembly

```asm
0x1800a7d38  mov     [rsp-8+arg_10], rbx
0x1800a7d3d  mov     [rsp-8+arg_0], rcx
0x1800a7d42  push    rbp
0x1800a7d43  push    rsi
0x1800a7d44  push    rdi
0x1800a7d45  push    r12
0x1800a7d47  push    r13
0x1800a7d49  push    r14
0x1800a7d4b  push    r15
0x1800a7d4d  lea     rbp, [rsp-27h]
0x1800a7d52  sub     rsp, 0D0h
0x1800a7d59  xor     esi, esi
0x1800a7d5b  mov     edi, edx
0x1800a7d5d  mov     [rbp+57h+var_90], 8007054Fh
0x1800a7d64  lea     rax, [rbp+57h+lpMem]
0x1800a7d68  mov     [rbp+57h+var_C8], rax
0x1800a7d6c  lea     rax, [rbp+57h+lpMem]
0x1800a7d70  mov     [rbp+57h+lpMem], rax
0x1800a7d74  lea     r15, aOnecoreComNetf_94; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a7d7b  mov     [rbp+57h+var_A0], r15
0x1800a7d7f  xorps   xmm0, xmm0
0x1800a7d82  mov     [rbp+57h+var_B0], rsi
0x1800a7d86  mov     r12, r8
0x1800a7d89  mov     [rbp+57h+var_A8], rsi
0x1800a7d8d  mov     r14, rcx
0x1800a7d90  movdqu  [rbp+57h+var_C0], xmm0
0x1800a7d95  test    edx, edx
0x1800a7d97  jz      short loc_1800A7DFE
0x1800a7d99  test    r8, r8
0x1800a7d9c  jnz     short loc_1800A7DFE
0x1800a7d9e  lea     rcx, [rbp+57h+var_C0]
0x1800a7da2  mov     [rbp+57h+var_98], 0F2h
0x1800a7da9  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@V?$CBaseIdentity@VCDefinitionIdentityHandleTraits@Rtl@Isolation@Windows@@@Rtl@Isolation@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(void)
0x1800a7dae  jmp     short loc_1800A7DD4
0x1800a7db0  mov     rax, [rbx+10h]
0x1800a7db4  test    rax, rax
0x1800a7db7  jz      short loc_1800A7DC2
0x1800a7db9  lea     rcx, [rbx+18h]
0x1800a7dbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7dc2  call    GetProcessHeap_0
0x1800a7dc7  mov     r8, rbx; lpMem
0x1800a7dca  xor     edx, edx; dwFlags
0x1800a7dcc  mov     rcx, rax; hHeap
0x1800a7dcf  call    HeapFree_0
0x1800a7dd4  mov     rbx, [rbp+57h+lpMem]
0x1800a7dd8  lea     rcx, [rbp+57h+lpMem]
0x1800a7ddc  mov     rax, [rbx]
0x1800a7ddf  mov     [rbp+57h+lpMem], rax
0x1800a7de3  mov     [rax+8], rcx
0x1800a7de7  lea     rax, [rbp+57h+lpMem]
0x1800a7deb  cmp     rbx, rax
0x1800a7dee  jnz     short loc_1800A7DB0
0x1800a7df0  lea     rcx, [rbp+57h+var_A0]
0x1800a7df4  call    ?SetInvalidParameter@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(void)
0x1800a7df9  jmp     loc_1800A7EDE
0x1800a7dfe  mov     ecx, esi
0x1800a7e00  test    edx, edx
0x1800a7e02  jz      short loc_1800A7E12
0x1800a7e04  mov     eax, ecx
0x1800a7e06  cmp     [r8+rax*8], rsi
0x1800a7e0a  jz      short loc_1800A7E83
0x1800a7e0c  inc     ecx
0x1800a7e0e  cmp     ecx, edi
0x1800a7e10  jnz     short loc_1800A7E04
0x1800a7e12  mov     r9, rdi
0x1800a7e15  lea     rdx, [rbp+57h+arg_8]
0x1800a7e19  mov     r8d, 2
0x1800a7e1f  lea     rcx, [rbp+57h+var_C0]
0x1800a7e23  call    ?EnlargeGeneric@?$CSmartArrayHolder@V?$CDefaultObjectTraits@V?$CBaseIdentity@VCDefinitionIdentityHandleTraits@Rtl@Isolation@Windows@@@Rtl@Isolation@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@IEAA?AVCCallDisposition@Nt@2@K_K@Z; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::EnlargeGeneric(ulong,unsigned __int64)
0x1800a7e28  mov     ebx, dword ptr [rbp+57h+arg_8]
0x1800a7e2b  test    ebx, ebx
0x1800a7e2d  jns     loc_1800A7F2B
0x1800a7e33  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x1800a7e39  jnz     short loc_1800A7E41
0x1800a7e3b  call    cs:__imp_DebugBreak
0x1800a7e41  mov     r9d, ebx; int
0x1800a7e44  lea     rcx, aStatusPropagat; "Status propagated"
0x1800a7e4b  mov     r8d, 0FAh; char *
0x1800a7e51  mov     rdx, r15; char *
0x1800a7e54  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800a7e59  mov     ecx, ebx; this
0x1800a7e5b  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800a7e60  lea     rcx, [rbp+57h+var_C0]
0x1800a7e64  mov     edi, eax
0x1800a7e66  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@V?$CBaseIdentity@VCDefinitionIdentityHandleTraits@Rtl@Isolation@Windows@@@Rtl@Isolation@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(void)
0x1800a7e6b  mov     rbx, [rbp+57h+lpMem]
0x1800a7e6f  lea     rax, [rbp+57h+lpMem]
0x1800a7e73  mov     rcx, [rbx]
0x1800a7e76  mov     [rbp+57h+lpMem], rcx
0x1800a7e7a  mov     [rcx+8], rax
0x1800a7e7e  jmp     loc_1800A7F1D
0x1800a7e83  lea     rcx, [rbp+57h+var_A0]
0x1800a7e87  mov     [rbp+57h+var_98], 0F5h
0x1800a7e8e  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x1800a7e93  lea     rcx, [rbp+57h+var_C0]
0x1800a7e97  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@V?$CBaseIdentity@VCDefinitionIdentityHandleTraits@Rtl@Isolation@Windows@@@Rtl@Isolation@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(void)
0x1800a7e9c  jmp     short loc_1800A7EC2
0x1800a7e9e  mov     rax, [rbx+10h]
0x1800a7ea2  test    rax, rax
0x1800a7ea5  jz      short loc_1800A7EB0
0x1800a7ea7  lea     rcx, [rbx+18h]
0x1800a7eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7eb0  call    GetProcessHeap_0
0x1800a7eb5  mov     r8, rbx; lpMem
0x1800a7eb8  xor     edx, edx; dwFlags
0x1800a7eba  mov     rcx, rax; hHeap
0x1800a7ebd  call    HeapFree_0
0x1800a7ec2  mov     rbx, [rbp+57h+lpMem]
0x1800a7ec6  lea     rcx, [rbp+57h+lpMem]
0x1800a7eca  mov     rax, [rbx]
0x1800a7ecd  mov     [rbp+57h+lpMem], rax
0x1800a7ed1  mov     [rax+8], rcx
0x1800a7ed5  lea     rax, [rbp+57h+lpMem]
0x1800a7ed9  cmp     rbx, rax
0x1800a7edc  jnz     short loc_1800A7E9E
0x1800a7ede  mov     edi, [rbp+57h+var_90]
0x1800a7ee1  jmp     loc_1800A8173
0x1800a7ee6  mov     rax, [rbx+10h]
0x1800a7eea  test    rax, rax
0x1800a7eed  jz      short loc_1800A7EF8
0x1800a7eef  lea     rcx, [rbx+18h]
0x1800a7ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7ef8  call    GetProcessHeap_0
0x1800a7efd  mov     r8, rbx; lpMem
0x1800a7f00  xor     edx, edx; dwFlags
0x1800a7f02  mov     rcx, rax; hHeap
0x1800a7f05  call    HeapFree_0
0x1800a7f0a  mov     rbx, [rbp+57h+lpMem]
0x1800a7f0e  lea     rcx, [rbp+57h+lpMem]
0x1800a7f12  mov     rax, [rbx]
0x1800a7f15  mov     [rbp+57h+lpMem], rax
0x1800a7f19  mov     [rax+8], rcx
0x1800a7f1d  lea     rax, [rbp+57h+lpMem]
0x1800a7f21  cmp     rbx, rax
0x1800a7f24  jnz     short loc_1800A7EE6
0x1800a7f26  jmp     loc_1800A8173
0x1800a7f2b  mov     r13, qword ptr [rbp+57h+var_C0+8]
0x1800a7f2f  mov     r15d, esi
0x1800a7f32  mov     rsi, [rbp+57h+var_B0]
0x1800a7f36  mov     rbx, [rbp+57h+var_A8]
0x1800a7f3a  test    edi, edi
0x1800a7f3c  jz      short loc_1800A7F9F
0x1800a7f3e  cmp     rbx, rsi
0x1800a7f41  jnb     short loc_1800A7F71
0x1800a7f43  lea     rdx, ds:0[rbx*8]
0x1800a7f4b  mov     rcx, rsi
0x1800a7f4e  add     rdx, r13
0x1800a7f51  sub     rcx, rbx
0x1800a7f54  jz      short loc_1800A7F6A
0x1800a7f56  mov     rax, rdx
0x1800a7f59  add     rdx, 8
0x1800a7f5d  mov     qword ptr [rax], 0
0x1800a7f64  sub     rcx, 1
0x1800a7f68  jnz     short loc_1800A7F56
0x1800a7f6a  mov     rbx, rsi
0x1800a7f6d  mov     [rbp+57h+var_A8], rbx
0x1800a7f71  mov     ecx, r15d
0x1800a7f74  lea     rdx, ds:0[rcx*8]
0x1800a7f7c  mov     rcx, [r12+rcx*8]; this
0x1800a7f80  add     rdx, r13; struct IDefinitionIdentity *
0x1800a7f83  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAUIDefinitionIdentity@@PEAU_DEFINITION_IDENTITY@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(IDefinitionIdentity *,Windows::Isolation::Rtl::_DEFINITION_IDENTITY *)
0x1800a7f88  mov     r14d, eax
0x1800a7f8b  test    eax, eax
0x1800a7f8d  js      loc_1800A805E
0x1800a7f93  inc     r15d
0x1800a7f96  cmp     r15d, edi
0x1800a7f99  jnz     short loc_1800A7F3E
0x1800a7f9b  mov     r14, [rbp+57h+arg_0]
0x1800a7f9f  xor     r15d, r15d
0x1800a7fa2  mov     [rbp+57h+var_80], 50h ; 'P'
0x1800a7faa  mov     [rbp+57h+var_70], r15
0x1800a7fae  mov     r8d, 2
0x1800a7fb4  mov     [rbp+57h+var_78], r8
0x1800a7fb8  mov     [rbp+57h+var_68], r15
0x1800a7fbc  mov     [rbp+57h+var_60], r15
0x1800a7fc0  mov     [rbp+57h+var_58], rdi
0x1800a7fc4  cmp     rbx, rsi
0x1800a7fc7  jnb     short loc_1800A7FF0
0x1800a7fc9  lea     rdx, ds:0[rbx*8]
0x1800a7fd1  mov     rcx, rsi
0x1800a7fd4  add     rdx, r13
0x1800a7fd7  sub     rcx, rbx
0x1800a7fda  jz      short loc_1800A7FEC
0x1800a7fdc  mov     rax, rdx
0x1800a7fdf  add     rdx, 8
0x1800a7fe3  mov     [rax], r15
0x1800a7fe6  sub     rcx, 1
0x1800a7fea  jnz     short loc_1800A7FDC
0x1800a7fec  mov     [rbp+57h+var_A8], rsi
0x1800a7ff0  mov     rdx, [r14+10h]
0x1800a7ff4  xorps   xmm0, xmm0
0x1800a7ff7  xor     eax, eax
0x1800a7ff9  mov     [rsp+100h+var_D8], r8d
0x1800a7ffe  lea     r8, [rbp+57h+var_80]
0x1800a8002  mov     [rbp+57h+var_38], rax
0x1800a8006  movups  [rbp+57h+var_48], xmm0
0x1800a800a  mov     [rbp+57h+var_50], r13
0x1800a800e  call    RtlSetInformationDefinitionAppId
0x1800a8013  mov     ebx, eax
0x1800a8015  test    eax, eax
0x1800a8017  jns     loc_1800A8125
0x1800a801d  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800a8023  jnz     short loc_1800A802B
0x1800a8025  call    cs:__imp_DebugBreak
0x1800a802b  mov     r9d, ebx; int
0x1800a802e  lea     rdx, aOnecoreComNetf_94; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a8035  mov     r8d, 116h; char *
0x1800a803b  lea     rcx, aStatusPropagat; "Status propagated"
0x1800a8042  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800a8047  mov     ecx, ebx; this
0x1800a8049  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800a804e  lea     rcx, [rbp+57h+var_C0]
0x1800a8052  mov     edi, eax
0x1800a8054  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@V?$CBaseIdentity@VCDefinitionIdentityHandleTraits@Rtl@Isolation@Windows@@@Rtl@Isolation@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(void)
0x1800a8059  jmp     loc_1800A8107
0x1800a805e  cmp     r14d, cs:g_NTSTATUS_to_break_on_propagate
0x1800a8065  jnz     short loc_1800A806D
0x1800a8067  call    cs:__imp_DebugBreak
0x1800a806d  mov     r9d, r14d; int
0x1800a8070  lea     rdx, aOnecoreComNetf_94; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a8077  mov     r8d, 104h; char *
0x1800a807d  lea     rcx, aStatusPropagat; "Status propagated"
0x1800a8084  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800a8089  mov     ecx, r14d; this
0x1800a808c  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800a8091  lea     rcx, [rbp+57h+var_C0]
0x1800a8095  mov     edi, eax
0x1800a8097  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@V?$CBaseIdentity@VCDefinitionIdentityHandleTraits@Rtl@Isolation@Windows@@@Rtl@Isolation@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(void)
0x1800a809c  jmp     short loc_1800A80C2
0x1800a809e  mov     rax, [rbx+10h]
0x1800a80a2  test    rax, rax
0x1800a80a5  jz      short loc_1800A80B0
0x1800a80a7  lea     rcx, [rbx+18h]
0x1800a80ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a80b0  call    GetProcessHeap_0
0x1800a80b5  mov     r8, rbx; lpMem
0x1800a80b8  xor     edx, edx; dwFlags
0x1800a80ba  mov     rcx, rax; hHeap
0x1800a80bd  call    HeapFree_0
0x1800a80c2  mov     rbx, [rbp+57h+lpMem]
0x1800a80c6  lea     rcx, [rbp+57h+lpMem]
0x1800a80ca  mov     rax, [rbx]
0x1800a80cd  mov     [rbp+57h+lpMem], rax
0x1800a80d1  mov     [rax+8], rcx
0x1800a80d5  lea     rax, [rbp+57h+lpMem]
0x1800a80d9  cmp     rbx, rax
0x1800a80dc  jnz     short loc_1800A809E
0x1800a80de  jmp     loc_1800A8173
0x1800a80e3  mov     rax, [rbx+10h]
0x1800a80e7  test    rax, rax
0x1800a80ea  jz      short loc_1800A80F5
0x1800a80ec  lea     rcx, [rbx+18h]
0x1800a80f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a80f5  call    GetProcessHeap_0
0x1800a80fa  mov     r8, rbx; lpMem
0x1800a80fd  xor     edx, edx; dwFlags
0x1800a80ff  mov     rcx, rax; hHeap
0x1800a8102  call    HeapFree_0
0x1800a8107  mov     rbx, [rbp+57h+lpMem]
0x1800a810b  lea     rcx, [rbp+57h+lpMem]
0x1800a810f  mov     rax, [rbx]
0x1800a8112  mov     [rbp+57h+lpMem], rax
0x1800a8116  mov     [rax+8], rcx
0x1800a811a  lea     rax, [rbp+57h+lpMem]
0x1800a811e  cmp     rbx, rax
0x1800a8121  jnz     short loc_1800A80E3
0x1800a8123  jmp     short loc_1800A8173
0x1800a8125  lea     rcx, [rbp+57h+var_C0]
0x1800a8129  mov     edi, r15d
0x1800a812c  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@V?$CBaseIdentity@VCDefinitionIdentityHandleTraits@Rtl@Isolation@Windows@@@Rtl@Isolation@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(void)
0x1800a8131  jmp     short loc_1800A8157
0x1800a8133  mov     rax, [rbx+10h]
0x1800a8137  test    rax, rax
0x1800a813a  jz      short loc_1800A8145
0x1800a813c  lea     rcx, [rbx+18h]
0x1800a8140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8145  call    GetProcessHeap_0
0x1800a814a  mov     r8, rbx; lpMem
0x1800a814d  xor     edx, edx; dwFlags
0x1800a814f  mov     rcx, rax; hHeap
0x1800a8152  call    HeapFree_0
0x1800a8157  mov     rbx, [rbp+57h+lpMem]
0x1800a815b  lea     rcx, [rbp+57h+lpMem]
0x1800a815f  mov     rax, [rbx]
0x1800a8162  mov     [rbp+57h+lpMem], rax
0x1800a8166  mov     [rax+8], rcx
0x1800a816a  lea     rax, [rbp+57h+lpMem]
0x1800a816e  cmp     rbx, rax
0x1800a8171  jnz     short loc_1800A8133
0x1800a8173  mov     rbx, [rsp+100h+arg_10]
0x1800a817b  mov     eax, edi
0x1800a817d  add     rsp, 0D0h
0x1800a8184  pop     r15
0x1800a8186  pop     r14
0x1800a8188  pop     r13
0x1800a818a  pop     r12
0x1800a818c  pop     rdi
0x1800a818d  pop     rsi
0x1800a818e  pop     rbp
0x1800a818f  retn
  ... truncated ...
```
