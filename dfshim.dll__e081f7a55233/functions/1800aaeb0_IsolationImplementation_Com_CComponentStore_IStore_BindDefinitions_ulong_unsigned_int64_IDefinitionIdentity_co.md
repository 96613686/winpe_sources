# IsolationImplementation::Com::CComponentStore::IStore_BindDefinitions(ulong,unsigned __int64,IDefinitionIdentity * * const,ulong,IDefinitionIdentity * * const,_ISTORE_BINDING_RESULT * const)

- ea: `0x1800aaeb0`
- end: `0x1800ab55f`
- name: `?IStore_BindDefinitions@CComponentStore@Com@IsolationImplementation@@IEAAJK_KQEAPEAUIDefinitionIdentity@@K1QEAU_ISTORE_BINDING_RESULT@@@Z`
- size: `1711`
- prototype: `__int64 __fastcall(IsolationImplementation::Com::CComponentStore *__hidden this, unsigned int, unsigned __int64, struct IDefinitionIdentity **const, unsigned int, struct IDefinitionIdentity **const, struct _ISTORE_BINDING_RESULT *const)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1800a97f0`

## callees

- `0x180006991`
- `0x1800069b5`
- `0x1800069c1`
- `0x180012acc`
- `0x18001631c`
- `0x180017514`
- `0x180017530`
- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x180030674`
- `0x180039c1c`
- `0x1800a77cc`
- `0x1800a7a18`
- `0x1800aaeb0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800aafe0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ab24c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ab52a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800aafe0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ab24c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ab52a`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800aaf15`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ab065`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ab18f`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ab436`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800aaf15`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ab065`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ab18f`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ab436`

## string_xrefs

- `0x1800aaecd`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800ab198`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800ab1d5`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800ab34c`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800ab43f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CComponentStore::IStore_BindDefinitions(
        IsolationImplementation::Com::CComponentStore *this,
        int a2,
        unsigned __int64 a3,
        struct IDefinitionIdentity **const a4,
        unsigned int a5,
        struct IDefinitionIdentity **const a6,
        struct _ISTORE_BINDING_RESULT *const a7)
{
  __int64 v10; // r12
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // edx
  unsigned int v14; // edi
  unsigned __int64 i; // rcx
  __int64 v16; // rax
  HANDLE v17; // rbx
  char *v18; // rcx
  unsigned int v19; // ebx
  int v20; // edx
  void (__fastcall *v21)(LPVOID *); // rax
  HANDLE ProcessHeap_0; // rax
  LPVOID *v23; // rbx
  struct Windows::Isolation::Rtl::_DEFINITION_IDENTITY *v24; // rsi
  __int64 v25; // rbx
  __int64 v26; // r12
  struct Windows::Isolation::Rtl::_DEFINITION_IDENTITY *v27; // r8
  _QWORD *v28; // rdx
  char *v29; // rcx
  _QWORD *v30; // rax
  int v31; // eax
  int v32; // r9d
  struct Windows::Isolation::Rtl::_DEFINITION_IDENTITY *v33; // r8
  unsigned int v34; // ebx
  int v35; // edx
  void (__fastcall *v36)(LPVOID *); // rax
  HANDLE v37; // rax
  LPVOID *v38; // rbx
  HANDLE v39; // rbx
  void (__fastcall *v40)(LPVOID *); // rax
  HANDLE v41; // rax
  LPVOID *v42; // rbx
  unsigned __int64 v43; // r14
  unsigned __int64 v44; // rbx
  __int64 v45; // rdx
  unsigned __int64 v46; // rcx
  _QWORD *v47; // rax
  int v48; // eax
  int v49; // r9d
  __int64 v50; // r8
  __int64 v51; // rdx
  _QWORD *v52; // rax
  void (__fastcall *v53)(LPVOID *); // rax
  HANDLE v54; // rax
  LPVOID *v55; // rbx
  struct Windows::Isolation::Rtl::_DEFINITION_IDENTITY *v56; // r10
  __int64 v57; // rdx
  _QWORD *v58; // rax
  int v59; // eax
  unsigned int v60; // ebx
  int v61; // edx
  void (__fastcall *v62)(LPVOID *); // rax
  HANDLE v63; // rax
  LPVOID *v64; // rbx
  void (__fastcall *v65)(LPVOID *); // rax
  HANDLE v66; // rax
  LPVOID *v67; // rbx
  unsigned int v69; // [rsp+20h] [rbp-D1h]
  unsigned int v70; // [rsp+20h] [rbp-D1h]
  LPVOID lpMem[2]; // [rsp+40h] [rbp-B1h] BYREF
  Windows::ErrorHandling::COM *v72; // [rsp+50h] [rbp-A1h] BYREF
  __int128 v73; // [rsp+58h] [rbp-99h] BYREF
  struct Windows::Isolation::Rtl::_DEFINITION_IDENTITY *v74; // [rsp+68h] [rbp-89h]
  struct Windows::Isolation::Rtl::_DEFINITION_IDENTITY *v75; // [rsp+70h] [rbp-81h]
  HANDLE hMutex; // [rsp+80h] [rbp-71h] BYREF
  __int16 v77; // [rsp+88h] [rbp-69h]
  _BYTE v78[64]; // [rsp+90h] [rbp-61h] BYREF
  __int128 v79; // [rsp+D0h] [rbp-21h] BYREF
  unsigned __int64 v80; // [rsp+E0h] [rbp-11h]
  unsigned __int64 v81; // [rsp+E8h] [rbp-9h]

  LODWORD(v74) = -2147023537;
  *(_QWORD *)&v73 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp";
  BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v78);
  v10 = 0;
  hMutex = 0;
  v77 = 0;
  v11 = StoreLock::Lock((StoreLock *)&hMutex);
  v12 = v11;
  if ( v11 < 0 )
  {
    if ( v11 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
      (const char *)0x226,
      v12,
      v69);
    v14 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v12, v13);
    goto LABEL_98;
  }
  if ( a7 )
  {
    for ( i = 0; i < a3; *(GUID *)((char *)a7 + 8 * v16 + 16) = GUID_NULL )
    {
      v16 = 5 * i++;
      *((_DWORD *)a7 + 2 * v16) = 0;
      *((_DWORD *)a7 + 2 * v16 + 1) = 1;
      *((_QWORD *)a7 + v16 + 1) = 0;
      *((_QWORD *)a7 + v16 + 4) = 0;
    }
  }
  if ( !a2 )
  {
    if ( a3 && !a4 )
    {
      DWORD2(v73) = 576;
      goto LABEL_19;
    }
    if ( a5 && !a6 )
    {
      DWORD2(v73) = 577;
      goto LABEL_19;
    }
    if ( a3 && !a7 )
    {
      DWORD2(v73) = 578;
      goto LABEL_19;
    }
    v74 = 0;
    lpMem[1] = lpMem;
    v75 = 0;
    lpMem[0] = lpMem;
    v73 = 0;
    BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::EnlargeGeneric(
      &v73,
      &v72,
      2,
      a3);
    v19 = (unsigned int)v72;
    if ( (int)v72 < 0 )
    {
      if ( (_DWORD)v72 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
        (const char *)0x248,
        v19,
        v69);
      v14 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v19, v20);
      BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(&v73);
      while ( 1 )
      {
        v23 = (LPVOID *)lpMem[0];
        lpMem[0] = *(LPVOID *)lpMem[0];
        *((_QWORD *)lpMem[0] + 1) = lpMem;
        if ( v23 == lpMem )
          break;
        v21 = (void (__fastcall *)(LPVOID *))v23[2];
        if ( v21 )
          v21(v23 + 3);
        ProcessHeap_0 = GetProcessHeap_0();
        HeapFree_0(ProcessHeap_0, 0, v23);
      }
      goto LABEL_98;
    }
    v24 = v75;
    v25 = 0;
    if ( a3 )
    {
      v26 = *((_QWORD *)&v73 + 1);
      while ( 1 )
      {
        v27 = v74;
        if ( v24 < v74 )
        {
          v28 = (_QWORD *)(v26 + 8LL * (_QWORD)v24);
          v29 = (char *)(v74 - v24);
          if ( v74 != v24 )
          {
            do
            {
              v30 = v28++;
              *v30 = 0;
              --v29;
            }
            while ( v29 );
          }
          v24 = v27;
          v75 = v27;
        }
        v31 = IsolationImplementation::Com::ConvertIn(a4[v25], (struct IDefinitionIdentity *)(v26 + 8 * v25), v27);
        v14 = v31;
        if ( v31 < 0 )
          break;
        if ( ++v25 >= a3 )
        {
          v10 = 0;
          goto LABEL_42;
        }
      }
      Windows::ErrorHandling::COM::ReportErrorPropagation(
        (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
        (const char *)0x24A,
        v31,
        v32);
      BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(&v73);
      while ( 1 )
      {
        v38 = (LPVOID *)lpMem[0];
        lpMem[0] = *(LPVOID *)lpMem[0];
        *((_QWORD *)lpMem[0] + 1) = lpMem;
        if ( v38 == lpMem )
          break;
        v36 = (void (__fastcall *)(LPVOID *))v38[2];
        if ( v36 )
          v36(v38 + 3);
        v37 = GetProcessHeap_0();
        HeapFree_0(v37, 0, v38);
      }
LABEL_52:
      v39 = hMutex;
      if ( hMutex )
      {
        if ( (_BYTE)v77 )
        {
          ReleaseMutex(hMutex);
          LOBYTE(v77) = 0;
        }
        goto LABEL_101;
      }
LABEL_102:
      BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v78);
      return v14;
    }
LABEL_42:
    v80 = 0;
    v79 = 0;
    v81 = 0;
    if ( a5 )
    {
      BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::EnlargeGeneric(
        &v79,
        &v72,
        2,
        a5);
      v34 = (unsigned int)v72;
      if ( (int)v72 >= 0 )
      {
        v43 = v80;
        v44 = v81;
        while ( 1 )
        {
          if ( v44 < v43 )
          {
            v45 = *((_QWORD *)&v79 + 1) + 8 * v44;
            v46 = v43 - v44;
            if ( v43 != v44 )
            {
              do
              {
                v47 = (_QWORD *)v45;
                v45 += 8;
                *v47 = 0;
                --v46;
              }
              while ( v46 );
            }
            v44 = v43;
            v81 = v43;
          }
          v48 = IsolationImplementation::Com::ConvertIn(
                  a6[v10],
                  (struct IDefinitionIdentity *)(*((_QWORD *)&v79 + 1) + 8 * v10),
                  v33);
          v14 = v48;
          if ( v48 < 0 )
            break;
          if ( ++v10 >= (unsigned __int64)a5 )
          {
            v50 = *((_QWORD *)&v79 + 1);
            if ( v44 < v43 )
            {
              v51 = *((_QWORD *)&v79 + 1) + 8 * v44;
              v18 = (char *)(v43 - v44);
              if ( v43 != v44 )
              {
                do
                {
                  v52 = (_QWORD *)v51;
                  v51 += 8;
                  *v52 = 0;
                  --v18;
                }
                while ( v18 );
              }
              v81 = v43;
            }
            goto LABEL_80;
          }
        }
        Windows::ErrorHandling::COM::ReportErrorPropagation(
          (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
          (const char *)0x252,
          v48,
          v49);
        BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(&v79);
        BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(&v73);
        while ( 1 )
        {
          v55 = (LPVOID *)lpMem[0];
          lpMem[0] = *(LPVOID *)lpMem[0];
          *((_QWORD *)lpMem[0] + 1) = lpMem;
          if ( v55 == lpMem )
            break;
          v53 = (void (__fastcall *)(LPVOID *))v55[2];
          if ( v53 )
            v53(v55 + 3);
          v54 = GetProcessHeap_0();
          HeapFree_0(v54, 0, v55);
        }
        goto LABEL_52;
      }
      if ( (_DWORD)v72 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
        (const char *)0x250,
        v34,
        v69);
      v14 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v34, v35);
      BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(&v79);
      BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(&v73);
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
    else
    {
      v50 = *((_QWORD *)&v79 + 1);
LABEL_80:
      v56 = v74;
      if ( v24 < v74 )
      {
        v57 = *((_QWORD *)&v73 + 1) + 8LL * (_QWORD)v24;
        v18 = (char *)(v74 - v24);
        if ( v74 != v24 )
        {
          do
          {
            v58 = (_QWORD *)v57;
            v57 += 8;
            *v58 = 0;
            --v18;
          }
          while ( v18 );
        }
        v75 = v56;
      }
      v59 = RtlBindComponentStoreComponents((_DWORD)v18, *((_QWORD *)this + 2), a3, DWORD2(v73), a5, v50, (__int64)a7);
      v60 = v59;
      if ( v59 >= 0 )
      {
        v14 = 0;
        BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(&v79);
        BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(&v73);
        while ( 1 )
        {
          v67 = (LPVOID *)lpMem[0];
          lpMem[0] = *(LPVOID *)lpMem[0];
          *((_QWORD *)lpMem[0] + 1) = lpMem;
          if ( v67 == lpMem )
            break;
          v65 = (void (__fastcall *)(LPVOID *))v67[2];
          if ( v65 )
            v65(v67 + 3);
          v66 = GetProcessHeap_0();
          HeapFree_0(v66, 0, v67);
        }
      }
      else
      {
        if ( v59 == g_NTSTATUS_to_break_on_propagate )
          DebugBreak();
        Windows::ErrorHandling::COM::ReportError(
          (Windows::ErrorHandling::COM *)"Status propagated",
          "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
          (const char *)0x266,
          v60,
          v70);
        v14 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v60, v61);
        BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(&v79);
        BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(&v73);
        while ( 1 )
        {
          v64 = (LPVOID *)lpMem[0];
          lpMem[0] = *(LPVOID *)lpMem[0];
          *((_QWORD *)lpMem[0] + 1) = lpMem;
          if ( v64 == lpMem )
            break;
          v62 = (void (__fastcall *)(LPVOID *))v64[2];
          if ( v62 )
            v62(v64 + 3);
          v63 = GetProcessHeap_0();
          HeapFree_0(v63, 0, v64);
        }
      }
    }
LABEL_98:
    v39 = hMutex;
    if ( hMutex )
    {
      if ( (_BYTE)v77 )
      {
        ReleaseMutex(hMutex);
        LOBYTE(v77) = 0;
      }
LABEL_101:
      CloseHandle_0(v39);
      hMutex = 0;
      goto LABEL_102;
    }
    goto LABEL_102;
  }
  DWORD2(v73) = 575;
LABEL_19:
  v17 = hMutex;
  if ( hMutex )
  {
    if ( (_BYTE)v77 )
    {
      ReleaseMutex(hMutex);
      LOBYTE(v77) = 0;
    }
    CloseHandle_0(v17);
    hMutex = 0;
  }
  BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v78);
  Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(&v73);
  return (unsigned int)v74;
}

```

## disassembly

```asm
0x1800aaeb0  mov     [rsp-8+arg_0], rcx
0x1800aaeb5  push    rbp
0x1800aaeb6  push    rbx
0x1800aaeb7  push    rsi
0x1800aaeb8  push    rdi
0x1800aaeb9  push    r12
0x1800aaebb  push    r13
0x1800aaebd  push    r14
0x1800aaebf  push    r15
0x1800aaec1  lea     rbp, [rsp-7]
0x1800aaec6  sub     rsp, 0F8h
0x1800aaecd  lea     rsi, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800aaed4  mov     dword ptr [rsp+130h+var_C8], 8007054Fh
0x1800aaedc  lea     rcx, [rbp+3Fh+var_A0]; this
0x1800aaee0  mov     qword ptr [rsp+130h+var_D8], rsi
0x1800aaee5  mov     r14, r9
0x1800aaee8  mov     r15, r8
0x1800aaeeb  mov     edi, edx
0x1800aaeed  call    ??0CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer(void)
0x1800aaef2  xor     r12d, r12d
0x1800aaef5  lea     rcx, [rbp+3Fh+hMutex]; this
0x1800aaef9  mov     [rbp+3Fh+hMutex], r12
0x1800aaefd  mov     [rbp+3Fh+var_A8], r12w
0x1800aaf02  call    ?Lock@StoreLock@@QEAAJXZ; StoreLock::Lock(void)
0x1800aaf07  mov     ebx, eax
0x1800aaf09  test    eax, eax
0x1800aaf0b  jns     short loc_1800AAF41
0x1800aaf0d  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800aaf13  jnz     short loc_1800AAF1B
0x1800aaf15  call    cs:__imp_DebugBreak
0x1800aaf1b  mov     r9d, ebx; int
0x1800aaf1e  lea     rcx, aStatusPropagat; "Status propagated"
0x1800aaf25  mov     r8d, 226h; char *
0x1800aaf2b  mov     rdx, rsi; char *
0x1800aaf2e  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800aaf33  mov     ecx, ebx; this
0x1800aaf35  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800aaf3a  mov     edi, eax
0x1800aaf3c  jmp     loc_1800AB518
0x1800aaf41  mov     r13, [rbp+3Fh+arg_30]
0x1800aaf45  test    r13, r13
0x1800aaf48  jz      short loc_1800AAF84
0x1800aaf4a  mov     rcx, r12
0x1800aaf4d  test    r15, r15
0x1800aaf50  jz      short loc_1800AAF84
0x1800aaf52  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800aaf59  lea     rax, [rcx+rcx*4]
0x1800aaf5d  inc     rcx
0x1800aaf60  mov     [r13+rax*8+0], r12d
0x1800aaf65  mov     dword ptr [r13+rax*8+4], 1
0x1800aaf6e  mov     [r13+rax*8+8], r12
0x1800aaf73  mov     [r13+rax*8+20h], r12
0x1800aaf78  movdqu  xmmword ptr [r13+rax*8+10h], xmm0
0x1800aaf7f  cmp     rcx, r15
0x1800aaf82  jb      short loc_1800AAF59
0x1800aaf84  test    edi, edi
0x1800aaf86  jz      short loc_1800AAF92
0x1800aaf88  mov     dword ptr [rsp+130h+var_D8+8], 23Fh
0x1800aaf90  jmp     short loc_1800AAFCE
0x1800aaf92  test    r15, r15
0x1800aaf95  jz      short loc_1800AAFA6
0x1800aaf97  test    r14, r14
0x1800aaf9a  jnz     short loc_1800AAFA6
0x1800aaf9c  mov     dword ptr [rsp+130h+var_D8+8], 240h
0x1800aafa4  jmp     short loc_1800AAFCE
0x1800aafa6  cmp     [rbp+3Fh+arg_20], r12d
0x1800aafaa  jz      short loc_1800AAFBC
0x1800aafac  cmp     [rbp+3Fh+arg_28], r12
0x1800aafb0  jnz     short loc_1800AAFBC
0x1800aafb2  mov     dword ptr [rsp+130h+var_D8+8], 241h
0x1800aafba  jmp     short loc_1800AAFCE
0x1800aafbc  test    r15, r15
0x1800aafbf  jz      short loc_1800AB012
0x1800aafc1  test    r13, r13
0x1800aafc4  jnz     short loc_1800AB012
0x1800aafc6  mov     dword ptr [rsp+130h+var_D8+8], 242h
0x1800aafce  mov     rbx, [rbp+3Fh+hMutex]
0x1800aafd2  test    rbx, rbx
0x1800aafd5  jz      short loc_1800AAFF6
0x1800aafd7  cmp     byte ptr [rbp+3Fh+var_A8], r12b
0x1800aafdb  jz      short loc_1800AAFEA
0x1800aafdd  mov     rcx, rbx; hMutex
0x1800aafe0  call    cs:__imp_ReleaseMutex
0x1800aafe6  mov     byte ptr [rbp+3Fh+var_A8], r12b
0x1800aafea  mov     rcx, rbx; hObject
0x1800aafed  call    CloseHandle_0
0x1800aaff2  mov     [rbp+3Fh+hMutex], r12
0x1800aaff6  lea     rcx, [rbp+3Fh+var_A0]; this
0x1800aaffa  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800aafff  lea     rcx, [rsp+130h+var_D8]
0x1800ab004  call    ?SetInvalidParameter@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(void)
0x1800ab009  mov     edi, dword ptr [rsp+130h+var_C8]
0x1800ab00d  jmp     loc_1800AB549
0x1800ab012  lea     rax, [rsp+130h+lpMem]
0x1800ab017  mov     [rsp+130h+var_C8], r12
0x1800ab01c  mov     [rsp+130h+var_E8], rax
0x1800ab021  lea     rdx, [rsp+130h+var_E0]
0x1800ab026  lea     rax, [rsp+130h+lpMem]
0x1800ab02b  mov     [rsp+130h+var_C0], r12
0x1800ab030  xorps   xmm0, xmm0
0x1800ab033  mov     [rsp+130h+lpMem], rax
0x1800ab038  mov     r9, r15
0x1800ab03b  lea     rcx, [rsp+130h+var_D8]
0x1800ab040  mov     r8d, 2
0x1800ab046  movdqu  [rsp+130h+var_D8], xmm0
0x1800ab04c  call    ?EnlargeGeneric@?$CSmartArrayHolder@V?$CDefaultObjectTraits@V?$CBaseIdentity@VCDefinitionIdentityHandleTraits@Rtl@Isolation@Windows@@@Rtl@Isolation@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@IEAA?AVCCallDisposition@Nt@2@K_K@Z; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::EnlargeGeneric(ulong,unsigned __int64)
0x1800ab051  mov     ebx, dword ptr [rsp+130h+var_E0]
0x1800ab055  test    ebx, ebx
0x1800ab057  jns     loc_1800AB0E1
0x1800ab05d  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x1800ab063  jnz     short loc_1800AB06B
0x1800ab065  call    cs:__imp_DebugBreak
0x1800ab06b  mov     r9d, ebx; int
0x1800ab06e  lea     rcx, aStatusPropagat; "Status propagated"
0x1800ab075  mov     r8d, 248h; char *
0x1800ab07b  mov     rdx, rsi; char *
0x1800ab07e  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800ab083  mov     ecx, ebx; this
0x1800ab085  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800ab08a  lea     rcx, [rsp+130h+var_D8]
0x1800ab08f  mov     edi, eax
0x1800ab091  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@V?$CBaseIdentity@VCDefinitionIdentityHandleTraits@Rtl@Isolation@Windows@@@Rtl@Isolation@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(void)
0x1800ab096  jmp     short loc_1800AB0BC
0x1800ab098  mov     rax, [rbx+10h]
0x1800ab09c  test    rax, rax
0x1800ab09f  jz      short loc_1800AB0AA
0x1800ab0a1  lea     rcx, [rbx+18h]
0x1800ab0a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab0aa  call    GetProcessHeap_0
0x1800ab0af  mov     r8, rbx; lpMem
0x1800ab0b2  xor     edx, edx; dwFlags
0x1800ab0b4  mov     rcx, rax; hHeap
0x1800ab0b7  call    HeapFree_0
0x1800ab0bc  mov     rbx, [rsp+130h+lpMem]
0x1800ab0c1  lea     rcx, [rsp+130h+lpMem]
0x1800ab0c6  mov     rax, [rbx]
0x1800ab0c9  mov     [rsp+130h+lpMem], rax
0x1800ab0ce  mov     [rax+8], rcx
0x1800ab0d2  lea     rax, [rsp+130h+lpMem]
0x1800ab0d7  cmp     rbx, rax
0x1800ab0da  jnz     short loc_1800AB098
0x1800ab0dc  jmp     loc_1800AB518
0x1800ab0e1  mov     rsi, [rsp+130h+var_C0]
0x1800ab0e6  mov     rbx, r12
0x1800ab0e9  test    r15, r15
0x1800ab0ec  jz      short loc_1800AB147
0x1800ab0ee  mov     r12, qword ptr [rsp+130h+var_D8+8]
0x1800ab0f3  mov     r8, [rsp+130h+var_C8]; struct Windows::Isolation::Rtl::_DEFINITION_IDENTITY *
0x1800ab0f8  cmp     rsi, r8
0x1800ab0fb  jnb     short loc_1800AB125
0x1800ab0fd  mov     rcx, r8
0x1800ab100  lea     rdx, [r12+rsi*8]
0x1800ab104  sub     rcx, rsi
0x1800ab107  jz      short loc_1800AB11D
0x1800ab109  mov     rax, rdx
0x1800ab10c  add     rdx, 8
0x1800ab110  mov     qword ptr [rax], 0
0x1800ab117  sub     rcx, 1
0x1800ab11b  jnz     short loc_1800AB109
0x1800ab11d  mov     rsi, r8
0x1800ab120  mov     [rsp+130h+var_C0], r8
0x1800ab125  mov     rcx, [r14+rbx*8]; this
0x1800ab129  lea     rdx, [r12+rbx*8]; struct IDefinitionIdentity *
0x1800ab12d  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAUIDefinitionIdentity@@PEAU_DEFINITION_IDENTITY@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(IDefinitionIdentity *,Windows::Isolation::Rtl::_DEFINITION_IDENTITY *)
0x1800ab132  mov     edi, eax
0x1800ab134  test    eax, eax
0x1800ab136  js      loc_1800AB1D2
0x1800ab13c  inc     rbx
0x1800ab13f  cmp     rbx, r15
0x1800ab142  jb      short loc_1800AB0F3
0x1800ab144  xor     r12d, r12d
0x1800ab147  xorps   xmm0, xmm0
0x1800ab14a  mov     [rbp+3Fh+var_50], r12
0x1800ab14e  movdqu  [rbp+3Fh+var_60], xmm0
0x1800ab153  mov     [rbp+3Fh+var_48], r12
0x1800ab157  cmp     [rbp+3Fh+arg_20], r12d
0x1800ab15b  jz      loc_1800AB3C4
0x1800ab161  mov     edi, [rbp+3Fh+arg_20]
0x1800ab164  lea     rdx, [rsp+130h+var_E0]
0x1800ab169  mov     r9d, edi
0x1800ab16c  lea     rcx, [rbp+3Fh+var_60]
0x1800ab170  mov     r8d, 2
0x1800ab176  call    ?EnlargeGeneric@?$CSmartArrayHolder@V?$CDefaultObjectTraits@V?$CBaseIdentity@VCDefinitionIdentityHandleTraits@Rtl@Isolation@Windows@@@Rtl@Isolation@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@IEAA?AVCCallDisposition@Nt@2@K_K@Z; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::EnlargeGeneric(ulong,unsigned __int64)
0x1800ab17b  mov     ebx, dword ptr [rsp+130h+var_E0]
0x1800ab17f  test    ebx, ebx
0x1800ab181  jns     loc_1800AB2B4
0x1800ab187  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x1800ab18d  jnz     short loc_1800AB195
0x1800ab18f  call    cs:__imp_DebugBreak
0x1800ab195  mov     r9d, ebx; int
0x1800ab198  lea     rdx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ab19f  mov     r8d, 250h; char *
0x1800ab1a5  lea     rcx, aStatusPropagat; "Status propagated"
0x1800ab1ac  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800ab1b1  mov     ecx, ebx; this
0x1800ab1b3  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800ab1b8  lea     rcx, [rbp+3Fh+var_60]
0x1800ab1bc  mov     edi, eax
0x1800ab1be  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@V?$CBaseIdentity@VCDefinitionIdentityHandleTraits@Rtl@Isolation@Windows@@@Rtl@Isolation@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(void)
0x1800ab1c3  lea     rcx, [rsp+130h+var_D8]
0x1800ab1c8  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@V?$CBaseIdentity@VCDefinitionIdentityHandleTraits@Rtl@Isolation@Windows@@@Rtl@Isolation@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(void)
0x1800ab1cd  jmp     loc_1800AB28F
0x1800ab1d2  mov     r8d, eax; int
0x1800ab1d5  lea     rcx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ab1dc  mov     edx, 24Ah; char *
0x1800ab1e1  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800ab1e6  lea     rcx, [rsp+130h+var_D8]
0x1800ab1eb  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@V?$CBaseIdentity@VCDefinitionIdentityHandleTraits@Rtl@Isolation@Windows@@@Rtl@Isolation@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::CBaseIdentity<Windows::Isolation::Rtl::CDefinitionIdentityHandleTraits>,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(void)
0x1800ab1f0  jmp     short loc_1800AB216
0x1800ab1f2  mov     rax, [rbx+10h]
0x1800ab1f6  test    rax, rax
0x1800ab1f9  jz      short loc_1800AB204
0x1800ab1fb  lea     rcx, [rbx+18h]
0x1800ab1ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab204  call    GetProcessHeap_0
0x1800ab209  mov     r8, rbx; lpMem
0x1800ab20c  xor     edx, edx; dwFlags
0x1800ab20e  mov     rcx, rax; hHeap
0x1800ab211  call    HeapFree_0
0x1800ab216  mov     rbx, [rsp+130h+lpMem]
0x1800ab21b  lea     rcx, [rsp+130h+lpMem]
0x1800ab220  mov     rax, [rbx]
0x1800ab223  mov     [rsp+130h+lpMem], rax
0x1800ab228  mov     [rax+8], rcx
0x1800ab22c  lea     rax, [rsp+130h+lpMem]
0x1800ab231  cmp     rbx, rax
0x1800ab234  jnz     short loc_1800AB1F2
0x1800ab236  mov     rbx, [rbp+3Fh+hMutex]
0x1800ab23a  test    rbx, rbx
0x1800ab23d  jz      loc_1800AB540
0x1800ab243  cmp     byte ptr [rbp+3Fh+var_A8], 0
0x1800ab247  jz      short loc_1800AB256
0x1800ab249  mov     rcx, rbx; hMutex
0x1800ab24c  call    cs:__imp_ReleaseMutex
0x1800ab252  mov     byte ptr [rbp+3Fh+var_A8], 0
0x1800ab256  mov     rcx, rbx; hObject
0x1800ab259  call    CloseHandle_0
0x1800ab25e  mov     [rbp+3Fh+hMutex], 0
0x1800ab266  jmp     loc_1800AB540
0x1800ab26b  mov     rax, [rbx+10h]
0x1800ab26f  test    rax, rax
0x1800ab272  jz      short loc_1800AB27D
0x1800ab274  lea     rcx, [rbx+18h]
0x1800ab278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab27d  call    GetProcessHeap_0
0x1800ab282  mov     r8, rbx; lpMem
0x1800ab285  xor     edx, edx; dwFlags
0x1800ab287  mov     rcx, rax; hHeap
0x1800ab28a  call    HeapFree_0
0x1800ab28f  mov     rbx, [rsp+130h+lpMem]
0x1800ab294  lea     rcx, [rsp+130h+lpMem]
0x1800ab299  mov     rax, [rbx]
0x1800ab29c  mov     [rsp+130h+lpMem], rax
0x1800ab2a1  mov     [rax+8], rcx
0x1800ab2a5  lea     rax, [rsp+130h+lpMem]
0x1800ab2aa  cmp     rbx, rax
0x1800ab2ad  jnz     short loc_1800AB26B
0x1800ab2af  jmp     loc_1800AB518
0x1800ab2b4  mov     r14, [rbp+3Fh+var_50]
0x1800ab2b8  mov     rbx, [rbp+3Fh+var_48]
0x1800ab2bc  test    rdi, rdi
0x1800ab2bf  jz      short loc_1800AB317
0x1800ab2c1  cmp     rbx, r14
0x1800ab2c4  jnb     short loc_1800AB2F1
0x1800ab2c6  mov     rax, qword ptr [rbp+3Fh+var_60+8]
0x1800ab2ca  mov     rcx, r14
0x1800ab2cd  lea     rdx, [rax+rbx*8]
0x1800ab2d1  sub     rcx, rbx
0x1800ab2d4  jz      short loc_1800AB2EA
0x1800ab2d6  mov     rax, rdx
0x1800ab2d9  add     rdx, 8
0x1800ab2dd  mov     qword ptr [rax], 0
0x1800ab2e4  sub     rcx, 1
0x1800ab2e8  jnz     short loc_1800AB2D6
0x1800ab2ea  mov     rbx, r14
0x1800ab2ed  mov     [rbp+3Fh+var_48], rbx
0x1800ab2f1  mov     rax, qword ptr [rbp+3Fh+var_60+8]
0x1800ab2f5  lea     rdx, [rax+r12*8]; struct IDefinitionIdentity *
0x1800ab2f9  mov     rax, [rbp+3Fh+arg_28]
0x1800ab2fd  mov     rcx, [rax+r12*8]; this
0x1800ab301  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAUIDefinitionIdentity@@PEAU_DEFINITION_IDENTITY@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(IDefinitionIdentity *,Windows::Isolation::Rtl::_DEFINITION_IDENTITY *)
0x1800ab306  mov     edi, eax
0x1800ab308  test    eax, eax
0x1800ab30a  js      short loc_1800AB349
0x1800ab30c  mov     eax, [rbp+3Fh+arg_20]
0x1800ab30f  inc     r12
0x1800ab312  cmp     r12, rax
0x1800ab315  jb      short loc_1800AB2C1
0x1800ab317  mov     r8, qword ptr [rbp+3Fh+var_60+8]
0x1800ab31b  cmp     rbx, r14
0x1800ab31e  jnb     loc_1800AB3CA
0x1800ab324  mov     rcx, r14
0x1800ab327  lea     rdx, [r8+rbx*8]
0x1800ab32b  sub     rcx, rbx
0x1800ab32e  jz      loc_1800AB3BB
0x1800ab334  xor     r12d, r12d
0x1800ab337  mov     rax, rdx
0x1800ab33a  add     rdx, 8
0x1800ab33e  mov     [rax], r12
0x1800ab341  sub     rcx, 1
  ... truncated ...
```
