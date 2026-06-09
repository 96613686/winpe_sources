# IsolationImplementation::Com::CComponentStore::IStore_BindReferenceToAssembly(ulong,IReferenceIdentity *,ulong,IDefinitionIdentity * * const,_GUID const &,IUnknown * *)

- ea: `0x1800ab568`
- end: `0x1800abbc4`
- name: `?IStore_BindReferenceToAssembly@CComponentStore@Com@IsolationImplementation@@IEAAJKPEAUIReferenceIdentity@@KQEAPEAUIDefinitionIdentity@@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `1628`
- prototype: `int(IsolationImplementation::Com::CComponentStore *__hidden this, unsigned int, struct IReferenceIdentity *, unsigned int, struct IDefinitionIdentity **const, const struct _GUID *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x1800a9800`

## callees

- `0x180006991`
- `0x1800069b5`
- `0x1800069c1`
- `0x180012acc`
- `0x180012b38`
- `0x1800161b4`
- `0x180017514`
- `0x180017530`
- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x1800199b4`
- `0x18002f364`
- `0x180030674`
- `0x18003094c`
- `0x180039c1c`
- `0x180044708`
- `0x1800a77cc`
- `0x1800a7a18`
- `0x1800ab568`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ab610`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ab671`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ab6bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800abb88`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ab610`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ab671`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ab6bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800abb88`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ab5d3`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ab7df`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ab9c3`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ab5d3`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ab7df`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ab9c3`

## string_xrefs

- `0x1800ab58c`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800ab73a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800ab7e8`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800ab8d7`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800ab9cc`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800aba81`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CComponentStore::IStore_BindReferenceToAssembly(
        IsolationImplementation::Com::CComponentStore *this,
        int a2,
        struct IReferenceIdentity *a3,
        unsigned int a4,
        struct IDefinitionIdentity **const a5,
        const struct _GUID *a6,
        struct IUnknown **a7)
{
  __int64 v7; // r15
  int v9; // r13d
  int v10; // eax
  struct Windows::Isolation::Rtl::_REFERENCE_IDENTITY *v11; // r8
  unsigned int v12; // ebx
  int v13; // edx
  unsigned int v14; // edi
  HANDLE v15; // rbx
  HANDLE v16; // rbx
  HANDLE v17; // rbx
  unsigned __int64 v18; // rbx
  unsigned __int64 v19; // rsi
  int v20; // eax
  int v21; // r9d
  void (__fastcall *v22)(LPVOID *); // rax
  HANDLE ProcessHeap_0; // rax
  LPVOID *v24; // rbx
  struct Windows::Isolation::Rtl::_DEFINITION_IDENTITY *v25; // r8
  unsigned int v26; // ebx
  int v27; // edx
  void (__fastcall *v28)(LPVOID *); // rax
  HANDLE v29; // rax
  LPVOID *v30; // rbx
  unsigned int v31; // r13d
  __int64 v32; // r14
  _QWORD *v33; // rdx
  unsigned __int64 v34; // rcx
  _QWORD *v35; // rax
  int v36; // eax
  int v37; // r9d
  void (__fastcall *v38)(LPVOID *); // rax
  HANDLE v39; // rax
  LPVOID *v40; // rbx
  int v41; // r13d
  _QWORD *v42; // rdx
  unsigned __int64 v43; // rcx
  _QWORD *v44; // rax
  __int64 v45; // rbx
  int v46; // eax
  unsigned int v47; // edi
  int v48; // edx
  void (__fastcall *v49)(LPVOID *); // rax
  HANDLE v50; // rax
  LPVOID *v51; // rbx
  int v52; // eax
  int v53; // r9d
  void (__fastcall *v54)(LPVOID *); // rax
  HANDLE v55; // rax
  LPVOID *v56; // rbx
  void (__fastcall *v57)(LPVOID *); // rax
  HANDLE v58; // rax
  LPVOID *v59; // rbx
  unsigned int v61; // [rsp+28h] [rbp-A1h]
  unsigned int v62; // [rsp+28h] [rbp-A1h]
  LPVOID lpMem[2]; // [rsp+38h] [rbp-91h] BYREF
  __int64 v64; // [rsp+48h] [rbp-81h] BYREF
  unsigned int v65[4]; // [rsp+50h] [rbp-79h] BYREF
  unsigned __int64 v66; // [rsp+60h] [rbp-69h]
  unsigned __int64 v67; // [rsp+68h] [rbp-61h]
  HANDLE hMutex; // [rsp+78h] [rbp-51h] BYREF
  __int16 v69; // [rsp+80h] [rbp-49h]
  _BYTE v70[64]; // [rsp+88h] [rbp-41h] BYREF
  __int64 v71; // [rsp+C8h] [rbp-1h] BYREF
  Windows::ErrorHandling::COM *v72; // [rsp+D0h] [rbp+7h] BYREF
  char v74; // [rsp+120h] [rbp+57h]

  v74 = a2;
  v7 = a4;
  *(_QWORD *)v65 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp";
  LODWORD(v66) = -2147023537;
  v9 = a2;
  BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v70);
  hMutex = 0;
  v69 = 0;
  v10 = StoreLock::Lock((StoreLock *)&hMutex);
  v12 = v10;
  if ( v10 < 0 )
  {
    if ( v10 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
      (const char *)0x1AA,
      v12,
      v61);
    v14 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v12, v13);
    goto LABEL_5;
  }
  if ( a7 )
    *a7 = 0;
  if ( (v9 & 0xFFFFFFFE) == 0 )
  {
    if ( !a3 )
    {
      v65[2] = 434;
LABEL_15:
      Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(v65);
      v16 = hMutex;
      if ( hMutex )
      {
        if ( (_BYTE)v69 )
        {
          ReleaseMutex(hMutex);
          LOBYTE(v69) = 0;
        }
        CloseHandle_0(v16);
        hMutex = 0;
      }
      BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v70);
      return (unsigned int)v66;
    }
    if ( (_DWORD)v7 && !a5 )
    {
      v65[2] = 435;
      goto LABEL_24;
    }
    if ( !a7 )
    {
      v65[2] = 436;
      goto LABEL_15;
    }
    v71 = 0;
    lpMem[1] = lpMem;
    v66 = 0;
    lpMem[0] = lpMem;
    v18 = 0;
    *(_OWORD *)v65 = 0;
    v19 = 0;
    v67 = 0;
    v20 = IsolationImplementation::Com::ConvertIn(a3, (struct IReferenceIdentity *)&v71, v11);
    v14 = v20;
    if ( v20 < 0 )
    {
      Windows::ErrorHandling::COM::ReportErrorPropagation(
        (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
        (const char *)0x1BF,
        v20,
        v21);
      BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(v65);
      if ( v71 )
        RtlCloseReferenceIdentityHandle(v71);
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
      goto LABEL_5;
    }
    if ( (_DWORD)v7 )
    {
      BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::EnlargeGeneric(
        v65,
        &v72,
        2,
        v7);
      v26 = (unsigned int)v72;
      if ( (int)v72 < 0 )
      {
        if ( (_DWORD)v72 == g_NTSTATUS_to_break_on_propagate )
          DebugBreak();
        Windows::ErrorHandling::COM::ReportError(
          (Windows::ErrorHandling::COM *)"Status propagated",
          "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
          (const char *)0x1C3,
          v26,
          v61);
        v14 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v26, v27);
        BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(v65);
        if ( v71 )
          RtlCloseReferenceIdentityHandle(v71);
        while ( 1 )
        {
          v30 = (LPVOID *)lpMem[0];
          lpMem[0] = *(LPVOID *)lpMem[0];
          *((_QWORD *)lpMem[0] + 1) = lpMem;
          if ( v30 == lpMem )
            break;
          v28 = (void (__fastcall *)(LPVOID *))v30[2];
          if ( v28 )
            v28(v30 + 3);
          v29 = GetProcessHeap_0();
          HeapFree_0(v29, 0, v30);
        }
LABEL_5:
        v15 = hMutex;
        if ( hMutex )
        {
          if ( (_BYTE)v69 )
          {
            ReleaseMutex(hMutex);
            LOBYTE(v69) = 0;
          }
LABEL_103:
          CloseHandle_0(v15);
          hMutex = 0;
          goto LABEL_104;
        }
        goto LABEL_104;
      }
      v19 = v66;
      v31 = 0;
      v32 = *(_QWORD *)&v65[2];
      v18 = v67;
      while ( 1 )
      {
        if ( v18 < v19 )
        {
          v33 = (_QWORD *)(v32 + 8 * v18);
          v34 = v19 - v18;
          if ( v19 != v18 )
          {
            do
            {
              v35 = v33++;
              *v35 = 0;
              --v34;
            }
            while ( v34 );
          }
          v18 = v19;
          v67 = v19;
        }
        v36 = IsolationImplementation::Com::ConvertIn(a5[v31], (struct IDefinitionIdentity *)(v32 + 8LL * v31), v25);
        v14 = v36;
        if ( v36 < 0 )
          break;
        if ( ++v31 >= (unsigned int)v7 )
        {
          LOBYTE(v9) = v74;
          goto LABEL_66;
        }
      }
      Windows::ErrorHandling::COM::ReportErrorPropagation(
        (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
        (const char *)0x1C6,
        v36,
        v37);
      BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(v65);
      if ( v71 )
        ((void (*)(void))RtlCloseReferenceIdentityHandle)();
      while ( 1 )
      {
        v40 = (LPVOID *)lpMem[0];
        lpMem[0] = *(LPVOID *)lpMem[0];
        *((_QWORD *)lpMem[0] + 1) = lpMem;
        if ( v40 == lpMem )
          break;
        v38 = (void (__fastcall *)(LPVOID *))v40[2];
        if ( v38 )
          v38(v40 + 3);
        v39 = GetProcessHeap_0();
        HeapFree_0(v39, 0, v40);
      }
    }
    else
    {
      v32 = *(_QWORD *)&v65[2];
LABEL_66:
      v41 = v9 & 1;
      v64 = 0;
      if ( v18 < v19 )
      {
        v42 = (_QWORD *)(v32 + 8 * v18);
        v43 = v19 - v18;
        if ( v19 != v18 )
        {
          do
          {
            v44 = v42++;
            *v44 = 0;
            --v43;
          }
          while ( v43 );
        }
        v67 = v19;
      }
      v45 = v71;
      v46 = RtlBindComponentStoreComponentReference(v41, *((_QWORD *)this + 2), v71, v7, v32, (__int64)&v64);
      v47 = v46;
      if ( v46 >= 0 )
      {
        v52 = IsolationImplementation::Com::CopyOut(v64, a6, a7);
        v14 = v52;
        if ( v52 >= 0 )
        {
          v14 = 0;
          if ( v64 )
          {
            CdfCloseHandle();
            v64 = 0;
          }
          BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(v65);
          if ( v45 )
            RtlCloseReferenceIdentityHandle(v45);
          while ( 1 )
          {
            v59 = (LPVOID *)lpMem[0];
            lpMem[0] = *(LPVOID *)lpMem[0];
            *((_QWORD *)lpMem[0] + 1) = lpMem;
            if ( v59 == lpMem )
              break;
            v57 = (void (__fastcall *)(LPVOID *))v59[2];
            if ( v57 )
              v57(v59 + 3);
            v58 = GetProcessHeap_0();
            HeapFree_0(v58, 0, v59);
          }
        }
        else
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
            (const char *)0x1D4,
            v52,
            v53);
          if ( v64 )
          {
            CdfCloseHandle();
            v64 = 0;
          }
          BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(v65);
          if ( v45 )
            RtlCloseReferenceIdentityHandle(v45);
          while ( 1 )
          {
            v56 = (LPVOID *)lpMem[0];
            lpMem[0] = *(LPVOID *)lpMem[0];
            *((_QWORD *)lpMem[0] + 1) = lpMem;
            if ( v56 == lpMem )
              break;
            v54 = (void (__fastcall *)(LPVOID *))v56[2];
            if ( v54 )
              v54(v56 + 3);
            v55 = GetProcessHeap_0();
            HeapFree_0(v55, 0, v56);
          }
        }
      }
      else
      {
        if ( v46 == g_NTSTATUS_to_break_on_propagate )
          DebugBreak();
        Windows::ErrorHandling::COM::ReportError(
          (Windows::ErrorHandling::COM *)"Status propagated",
          "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
          (const char *)0x1D2,
          v47,
          v62);
        v14 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v47, v48);
        if ( v64 )
        {
          CdfCloseHandle();
          v64 = 0;
        }
        BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(v65);
        if ( v45 )
          RtlCloseReferenceIdentityHandle(v45);
        while ( 1 )
        {
          v51 = (LPVOID *)lpMem[0];
          lpMem[0] = *(LPVOID *)lpMem[0];
          *((_QWORD *)lpMem[0] + 1) = lpMem;
          if ( v51 == lpMem )
            break;
          v49 = (void (__fastcall *)(LPVOID *))v51[2];
          if ( v49 )
            v49(v51 + 3);
          v50 = GetProcessHeap_0();
          HeapFree_0(v50, 0, v51);
        }
      }
    }
    v15 = hMutex;
    if ( hMutex )
    {
      if ( (_BYTE)v69 )
      {
        ReleaseMutex(hMutex);
        LOBYTE(v69) = 0;
      }
      goto LABEL_103;
    }
LABEL_104:
    BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v70);
    return v14;
  }
  v65[2] = 433;
LABEL_24:
  v17 = hMutex;
  if ( hMutex )
  {
    if ( (_BYTE)v69 )
    {
      ReleaseMutex(hMutex);
      LOBYTE(v69) = 0;
    }
    CloseHandle_0(v17);
    hMutex = 0;
  }
  BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v70);
  Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(v65);
  return (unsigned int)v66;
}

```

## disassembly

```asm
0x1800ab568  mov     rax, rsp
0x1800ab56b  mov     [rax+18h], rbx
0x1800ab56f  mov     [rax+10h], edx
0x1800ab572  mov     [rax+8], rcx
0x1800ab576  push    rbp
0x1800ab577  push    rsi
0x1800ab578  push    rdi
0x1800ab579  push    r12
0x1800ab57b  push    r13
0x1800ab57d  push    r14
0x1800ab57f  push    r15
0x1800ab581  lea     rbp, [rax-47h]
0x1800ab585  sub     rsp, 0D0h
0x1800ab58c  lea     rsi, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ab593  mov     r15d, r9d
0x1800ab596  lea     rcx, [rbp+3Fh+var_80]; this
0x1800ab59a  mov     qword ptr [rbp+3Fh+var_B8], rsi
0x1800ab59e  mov     rdi, r8
0x1800ab5a1  mov     dword ptr [rbp+3Fh+var_A8], 8007054Fh
0x1800ab5a8  mov     r13d, edx
0x1800ab5ab  call    ??0CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer(void)
0x1800ab5b0  xor     r14d, r14d
0x1800ab5b3  lea     rcx, [rbp+3Fh+hMutex]; this
0x1800ab5b7  mov     [rbp+3Fh+hMutex], r14
0x1800ab5bb  mov     [rbp+3Fh+var_88], r14w
0x1800ab5c0  call    ?Lock@StoreLock@@QEAAJXZ; StoreLock::Lock(void)
0x1800ab5c5  mov     ebx, eax
0x1800ab5c7  test    eax, eax
0x1800ab5c9  jns     short loc_1800AB62B
0x1800ab5cb  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800ab5d1  jnz     short loc_1800AB5D9
0x1800ab5d3  call    cs:__imp_DebugBreak
0x1800ab5d9  mov     r9d, ebx; int
0x1800ab5dc  lea     rcx, aStatusPropagat; "Status propagated"
0x1800ab5e3  mov     r8d, 1AAh; char *
0x1800ab5e9  mov     rdx, rsi; char *
0x1800ab5ec  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800ab5f1  mov     ecx, ebx; this
0x1800ab5f3  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800ab5f8  mov     edi, eax
0x1800ab5fa  mov     rbx, [rbp+3Fh+hMutex]
0x1800ab5fe  test    rbx, rbx
0x1800ab601  jz      loc_1800ABB9E
0x1800ab607  cmp     byte ptr [rbp+3Fh+var_88], r14b
0x1800ab60b  jz      short loc_1800AB61A
0x1800ab60d  mov     rcx, rbx; hMutex
0x1800ab610  call    cs:__imp_ReleaseMutex
0x1800ab616  mov     byte ptr [rbp+3Fh+var_88], r14b
0x1800ab61a  mov     rcx, rbx; hObject
0x1800ab61d  call    CloseHandle_0
0x1800ab622  mov     [rbp+3Fh+hMutex], r14
0x1800ab626  jmp     loc_1800ABB9E
0x1800ab62b  mov     r12, [rbp+3Fh+arg_30]
0x1800ab62f  test    r12, r12
0x1800ab632  jz      short loc_1800AB638
0x1800ab634  mov     [r12], r14
0x1800ab638  test    r13d, 0FFFFFFFEh
0x1800ab63f  jz      short loc_1800AB64A
0x1800ab641  mov     [rbp+3Fh+var_B8+8], 1B1h
0x1800ab648  jmp     short loc_1800AB6AA
0x1800ab64a  test    rdi, rdi
0x1800ab64d  jnz     short loc_1800AB698
0x1800ab64f  mov     [rbp+3Fh+var_B8+8], 1B2h
0x1800ab656  lea     rcx, [rbp+3Fh+var_B8]
0x1800ab65a  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x1800ab65f  mov     rbx, [rbp+3Fh+hMutex]
0x1800ab663  test    rbx, rbx
0x1800ab666  jz      short loc_1800AB687
0x1800ab668  cmp     byte ptr [rbp+3Fh+var_88], r14b
0x1800ab66c  jz      short loc_1800AB67B
0x1800ab66e  mov     rcx, rbx; hMutex
0x1800ab671  call    cs:__imp_ReleaseMutex
0x1800ab677  mov     byte ptr [rbp+3Fh+var_88], r14b
0x1800ab67b  mov     rcx, rbx; hObject
0x1800ab67e  call    CloseHandle_0
0x1800ab683  mov     [rbp+3Fh+hMutex], r14
0x1800ab687  lea     rcx, [rbp+3Fh+var_80]; this
0x1800ab68b  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800ab690  mov     edi, dword ptr [rbp+3Fh+var_A8]
0x1800ab693  jmp     loc_1800ABBA7
0x1800ab698  test    r15d, r15d
0x1800ab69b  jz      short loc_1800AB6E6
0x1800ab69d  cmp     [rbp+3Fh+arg_20], r14
0x1800ab6a1  jnz     short loc_1800AB6E6
0x1800ab6a3  mov     [rbp+3Fh+var_B8+8], 1B3h
0x1800ab6aa  mov     rbx, [rbp+3Fh+hMutex]
0x1800ab6ae  test    rbx, rbx
0x1800ab6b1  jz      short loc_1800AB6D2
0x1800ab6b3  cmp     byte ptr [rbp+3Fh+var_88], r14b
0x1800ab6b7  jz      short loc_1800AB6C6
0x1800ab6b9  mov     rcx, rbx; hMutex
0x1800ab6bc  call    cs:__imp_ReleaseMutex
0x1800ab6c2  mov     byte ptr [rbp+3Fh+var_88], r14b
0x1800ab6c6  mov     rcx, rbx; hObject
0x1800ab6c9  call    CloseHandle_0
0x1800ab6ce  mov     [rbp+3Fh+hMutex], r14
0x1800ab6d2  lea     rcx, [rbp+3Fh+var_80]; this
0x1800ab6d6  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800ab6db  lea     rcx, [rbp+3Fh+var_B8]
0x1800ab6df  call    ?SetInvalidParameter@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(void)
0x1800ab6e4  jmp     short loc_1800AB690
0x1800ab6e6  test    r12, r12
0x1800ab6e9  jnz     short loc_1800AB6F7
0x1800ab6eb  mov     [rbp+3Fh+var_B8+8], 1B4h
0x1800ab6f2  jmp     loc_1800AB656
0x1800ab6f7  lea     rax, [rsp+100h+lpMem]
0x1800ab6fc  mov     [rbp+3Fh+var_40], r14
0x1800ab700  mov     [rsp+100h+var_C8], rax
0x1800ab705  lea     rdx, [rbp+3Fh+var_40]; struct IReferenceIdentity *
0x1800ab709  lea     rax, [rsp+100h+lpMem]
0x1800ab70e  mov     [rbp+3Fh+var_A8], r14
0x1800ab712  xorps   xmm0, xmm0
0x1800ab715  mov     [rsp+100h+lpMem], rax
0x1800ab71a  mov     rbx, r14
0x1800ab71d  mov     rcx, rdi; this
0x1800ab720  movdqu  xmmword ptr [rbp+3Fh+var_B8], xmm0
0x1800ab725  mov     rsi, r14
0x1800ab728  mov     [rbp+3Fh+var_A0], rbx
0x1800ab72c  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAUIReferenceIdentity@@PEAU_REFERENCE_IDENTITY@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(IReferenceIdentity *,Windows::Isolation::Rtl::_REFERENCE_IDENTITY *)
0x1800ab731  mov     edi, eax
0x1800ab733  test    eax, eax
0x1800ab735  jns     short loc_1800AB7AD
0x1800ab737  mov     r8d, eax; int
0x1800ab73a  lea     rcx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ab741  mov     edx, 1BFh; char *
0x1800ab746  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800ab74b  lea     rcx, [rbp+3Fh+var_B8]
0x1800ab74f  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@V?$CBaseIdentity@VCDefinitionIdentityHandleTraits@Rtl@Isolation@Windows@@@Rtl@Isolation@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(void)
0x1800ab754  mov     rcx, [rbp+3Fh+var_40]
0x1800ab758  test    rcx, rcx
0x1800ab75b  jz      short loc_1800AB788
0x1800ab75d  call    RtlCloseReferenceIdentityHandle
0x1800ab762  jmp     short loc_1800AB788
0x1800ab764  mov     rax, [rbx+10h]
0x1800ab768  test    rax, rax
0x1800ab76b  jz      short loc_1800AB776
0x1800ab76d  lea     rcx, [rbx+18h]
0x1800ab771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab776  call    GetProcessHeap_0
0x1800ab77b  mov     r8, rbx; lpMem
0x1800ab77e  xor     edx, edx; dwFlags
0x1800ab780  mov     rcx, rax; hHeap
0x1800ab783  call    HeapFree_0
0x1800ab788  mov     rbx, [rsp+100h+lpMem]
0x1800ab78d  lea     rcx, [rsp+100h+lpMem]
0x1800ab792  mov     rax, [rbx]
0x1800ab795  mov     [rsp+100h+lpMem], rax
0x1800ab79a  mov     [rax+8], rcx
0x1800ab79e  lea     rax, [rsp+100h+lpMem]
0x1800ab7a3  cmp     rbx, rax
0x1800ab7a6  jnz     short loc_1800AB764
0x1800ab7a8  jmp     loc_1800AB5FA
0x1800ab7ad  test    r15d, r15d
0x1800ab7b0  jz      loc_1800AB94C
0x1800ab7b6  mov     r9, r15
0x1800ab7b9  lea     rdx, [rbp+3Fh+var_38]
0x1800ab7bd  mov     r8d, 2
0x1800ab7c3  lea     rcx, [rbp+3Fh+var_B8]
0x1800ab7c7  call    ?EnlargeGeneric@?$CSmartArrayHolder@V?$CDefaultObjectTraits@V?$CBaseIdentity@VCDefinitionIdentityHandleTraits@Rtl@Isolation@Windows@@@Rtl@Isolation@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@IEAA?AVCCallDisposition@Nt@2@K_K@Z; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::EnlargeGeneric(ulong,unsigned __int64)
0x1800ab7cc  mov     ebx, dword ptr [rbp+3Fh+var_38]
0x1800ab7cf  test    ebx, ebx
0x1800ab7d1  jns     loc_1800AB86C
0x1800ab7d7  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x1800ab7dd  jnz     short loc_1800AB7E5
0x1800ab7df  call    cs:__imp_DebugBreak
0x1800ab7e5  mov     r9d, ebx; int
0x1800ab7e8  lea     rdx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ab7ef  mov     r8d, 1C3h; char *
0x1800ab7f5  lea     rcx, aStatusPropagat; "Status propagated"
0x1800ab7fc  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800ab801  mov     ecx, ebx; this
0x1800ab803  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800ab808  lea     rcx, [rbp+3Fh+var_B8]
0x1800ab80c  mov     edi, eax
0x1800ab80e  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@V?$CBaseIdentity@VCDefinitionIdentityHandleTraits@Rtl@Isolation@Windows@@@Rtl@Isolation@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(void)
0x1800ab813  mov     rcx, [rbp+3Fh+var_40]
0x1800ab817  test    rcx, rcx
0x1800ab81a  jz      short loc_1800AB847
0x1800ab81c  call    RtlCloseReferenceIdentityHandle
0x1800ab821  jmp     short loc_1800AB847
0x1800ab823  mov     rax, [rbx+10h]
0x1800ab827  test    rax, rax
0x1800ab82a  jz      short loc_1800AB835
0x1800ab82c  lea     rcx, [rbx+18h]
0x1800ab830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab835  call    GetProcessHeap_0
0x1800ab83a  mov     r8, rbx; lpMem
0x1800ab83d  xor     edx, edx; dwFlags
0x1800ab83f  mov     rcx, rax; hHeap
0x1800ab842  call    HeapFree_0
0x1800ab847  mov     rbx, [rsp+100h+lpMem]
0x1800ab84c  lea     rcx, [rsp+100h+lpMem]
0x1800ab851  mov     rax, [rbx]
0x1800ab854  mov     [rsp+100h+lpMem], rax
0x1800ab859  mov     [rax+8], rcx
0x1800ab85d  lea     rax, [rsp+100h+lpMem]
0x1800ab862  cmp     rbx, rax
0x1800ab865  jnz     short loc_1800AB823
0x1800ab867  jmp     loc_1800AB5FA
0x1800ab86c  mov     rsi, [rbp+3Fh+var_A8]
0x1800ab870  mov     r13d, r14d
0x1800ab873  mov     r14, qword ptr [rbp+3Fh+var_B8+8]
0x1800ab877  mov     rbx, [rbp+3Fh+var_A0]
0x1800ab87b  test    r15d, r15d
0x1800ab87e  jz      short loc_1800AB8CE
0x1800ab880  cmp     rbx, rsi
0x1800ab883  jnb     short loc_1800AB8AC
0x1800ab885  mov     rcx, rsi
0x1800ab888  lea     rdx, [r14+rbx*8]
0x1800ab88c  sub     rcx, rbx
0x1800ab88f  jz      short loc_1800AB8A5
0x1800ab891  mov     rax, rdx
0x1800ab894  add     rdx, 8
0x1800ab898  mov     qword ptr [rax], 0
0x1800ab89f  sub     rcx, 1
0x1800ab8a3  jnz     short loc_1800AB891
0x1800ab8a5  mov     rbx, rsi
0x1800ab8a8  mov     [rbp+3Fh+var_A0], rbx
0x1800ab8ac  mov     rax, [rbp+3Fh+arg_20]
0x1800ab8b0  mov     ecx, r13d
0x1800ab8b3  lea     rdx, [r14+rcx*8]; struct IDefinitionIdentity *
0x1800ab8b7  mov     rcx, [rax+rcx*8]; this
0x1800ab8bb  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAUIDefinitionIdentity@@PEAU_DEFINITION_IDENTITY@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(IDefinitionIdentity *,Windows::Isolation::Rtl::_DEFINITION_IDENTITY *)
0x1800ab8c0  mov     edi, eax
0x1800ab8c2  test    eax, eax
0x1800ab8c4  js      short loc_1800AB8D4
0x1800ab8c6  inc     r13d
0x1800ab8c9  cmp     r13d, r15d
0x1800ab8cc  jb      short loc_1800AB880
0x1800ab8ce  mov     r13d, [rbp+3Fh+arg_8]
0x1800ab8d2  jmp     short loc_1800AB950
0x1800ab8d4  mov     r8d, eax; int
0x1800ab8d7  lea     rcx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ab8de  mov     edx, 1C6h; char *
0x1800ab8e3  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800ab8e8  lea     rcx, [rbp+3Fh+var_B8]
0x1800ab8ec  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@V?$CBaseIdentity@VCDefinitionIdentityHandleTraits@Rtl@Isolation@Windows@@@Rtl@Isolation@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(void)
0x1800ab8f1  mov     rcx, [rbp+3Fh+var_40]
0x1800ab8f5  xor     esi, esi
0x1800ab8f7  test    rcx, rcx
0x1800ab8fa  jz      short loc_1800AB927
0x1800ab8fc  call    RtlCloseReferenceIdentityHandle
0x1800ab901  jmp     short loc_1800AB927
0x1800ab903  mov     rax, [rbx+10h]
0x1800ab907  test    rax, rax
0x1800ab90a  jz      short loc_1800AB915
0x1800ab90c  lea     rcx, [rbx+18h]
0x1800ab910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab915  call    GetProcessHeap_0
0x1800ab91a  mov     r8, rbx; lpMem
0x1800ab91d  xor     edx, edx; dwFlags
0x1800ab91f  mov     rcx, rax; hHeap
0x1800ab922  call    HeapFree_0
0x1800ab927  mov     rbx, [rsp+100h+lpMem]
0x1800ab92c  lea     rcx, [rsp+100h+lpMem]
0x1800ab931  mov     rax, [rbx]
0x1800ab934  mov     [rsp+100h+lpMem], rax
0x1800ab939  mov     [rax+8], rcx
0x1800ab93d  lea     rax, [rsp+100h+lpMem]
0x1800ab942  cmp     rbx, rax
0x1800ab945  jnz     short loc_1800AB903
0x1800ab947  jmp     loc_1800ABB76
0x1800ab94c  mov     r14, qword ptr [rbp+3Fh+var_B8+8]
0x1800ab950  and     r13d, 1
0x1800ab954  mov     [rsp+100h+var_C0], 0
0x1800ab95d  cmp     rbx, rsi
0x1800ab960  jnb     short loc_1800AB986
0x1800ab962  mov     rcx, rsi
0x1800ab965  lea     rdx, [r14+rbx*8]
0x1800ab969  sub     rcx, rbx
0x1800ab96c  jz      short loc_1800AB982
0x1800ab96e  mov     rax, rdx
0x1800ab971  add     rdx, 8
0x1800ab975  mov     qword ptr [rax], 0
0x1800ab97c  sub     rcx, 1
0x1800ab980  jnz     short loc_1800AB96E
0x1800ab982  mov     [rbp+3Fh+var_A0], rsi
0x1800ab986  mov     rdx, [rbp+3Fh+arg_0]
0x1800ab98a  lea     rax, [rsp+100h+var_C0]
0x1800ab98f  mov     rbx, [rbp+3Fh+var_40]
0x1800ab993  mov     r9, r15
0x1800ab996  mov     [rsp+100h+var_D8], rax
0x1800ab99b  mov     r8, rbx
0x1800ab99e  mov     ecx, r13d
0x1800ab9a1  mov     qword ptr [rsp+100h+var_E0], r14; unsigned int
0x1800ab9a6  mov     rdx, [rdx+10h]
0x1800ab9aa  call    RtlBindComponentStoreComponentReference
0x1800ab9af  xor     esi, esi
0x1800ab9b1  mov     edi, eax
0x1800ab9b3  test    eax, eax
0x1800ab9b5  jns     loc_1800ABA63
0x1800ab9bb  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800ab9c1  jnz     short loc_1800AB9C9
0x1800ab9c3  call    cs:__imp_DebugBreak
0x1800ab9c9  mov     r9d, edi; int
0x1800ab9cc  lea     rdx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ab9d3  mov     r8d, 1D2h; char *
0x1800ab9d9  lea     rcx, aStatusPropagat; "Status propagated"
0x1800ab9e0  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800ab9e5  mov     ecx, edi; this
  ... truncated ...
```
