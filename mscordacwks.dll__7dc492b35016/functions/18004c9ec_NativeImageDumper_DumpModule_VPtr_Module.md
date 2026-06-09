# NativeImageDumper::DumpModule(__VPtr<Module>)

- ea: `0x18004c9ec`
- end: `0x18004e361`
- name: `?DumpModule@NativeImageDumper@@QEAAXV?$__VPtr@VModule@@@@@Z`
- size: `6517`
- prototype: `__int64 __fastcall(NativeImageDumper *this, unsigned __int64)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180045464`

## callees

- `0x1800210f0`
- `0x18002127c`
- `0x180022068`
- `0x18004240c`
- `0x180042724`
- `0x18004c9ec`
- `0x18004e3b8`
- `0x18004fdd4`
- `0x1800552bc`
- `0x180062cb8`
- `0x180063044`
- `0x1800633cc`
- `0x180063754`
- `0x180063adc`
- `0x180063e7c`
- `0x18007344c`
- `0x1800f0d20`
- `0x180106100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18004cc34`
- `KERNEL32!HeapFree` at `0x18004e293`
- `KERNEL32!HeapFree` at `0x18004cc34`
- `KERNEL32!HeapFree` at `0x18004e293`
- `KERNEL32!GetProcessHeap` at `0x18004cc1f`
- `KERNEL32!GetProcessHeap` at `0x18004e27e`
- `KERNEL32!GetProcessHeap` at `0x18004cc1f`
- `KERNEL32!GetProcessHeap` at `0x18004e27e`

## string_xrefs

- `0x18004caef`: `m_pDllMain`
- `0x18004d362`: `m_ManifestModuleReferencesMap`
- `0x18004e1a0`: `m_pModuleSecurityDescriptor`
- `0x18004e301`: `m_DefaultDllImportSearchPathsAttributeValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall NativeImageDumper::DumpModule(NativeImageDumper *this, unsigned __int64 a2)
{
  unsigned __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  int v7; // ecx
  __int64 v8; // rax
  void *v9; // rdi
  HANDLE ProcessHeap; // rax
  __int64 v11; // rax
  unsigned __int64 v12; // rdi
  void *v13; // rax
  int v14; // ecx
  _QWORD *v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // rax
  unsigned __int64 *v18; // rax
  _QWORD *v19; // rax
  _QWORD *v20; // rax
  _QWORD *v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rdi
  unsigned __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rdx
  unsigned __int64 v28; // rdi
  int v29; // eax
  unsigned __int64 v30; // rax
  _DWORD *v31; // rax
  _DWORD *v32; // rax
  _DWORD *v33; // rax
  unsigned int *v34; // rsi
  _QWORD *v35; // rax
  unsigned __int64 v36; // rax
  unsigned int *v37; // rsi
  _QWORD *v38; // rax
  unsigned __int64 v39; // rax
  _DWORD *v40; // r14
  _DWORD *v41; // rsi
  _QWORD *v42; // rax
  unsigned __int64 v43; // rax
  _DWORD *v44; // rsi
  _QWORD *v45; // rax
  unsigned __int64 v46; // rax
  _DWORD *v47; // rsi
  _QWORD *v48; // rax
  unsigned __int64 v49; // rax
  _DWORD *v50; // rax
  _DWORD *v51; // rax
  unsigned int *v52; // rsi
  _QWORD *v53; // rax
  unsigned __int64 v54; // rax
  unsigned int *v55; // rsi
  _QWORD *v56; // rax
  unsigned __int64 v57; // rax
  _DWORD *v58; // rax
  _DWORD *v59; // rax
  __int64 v60; // rax
  __int64 v61; // rdi
  unsigned __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // rdi
  unsigned __int64 v65; // rax
  __int64 v66; // rdi
  __int64 v67; // rax
  unsigned __int64 v68; // rax
  __int64 v69; // rax
  __int64 v70; // rdi
  unsigned __int64 v71; // rax
  __int64 v72; // rax
  __int64 v73; // rax
  __int64 v74; // rax
  __int64 v75; // rdi
  __int64 v76; // rax
  __int64 v77; // rsi
  __int64 v78; // rdi
  unsigned __int64 v79; // rax
  __int64 v80; // rax
  __int64 v81; // rdi
  __int64 v82; // rax
  __int64 v83; // rax
  __int64 v84; // rax
  __int64 v85; // rdi
  unsigned __int64 v86; // rax
  __int64 v87; // rax
  __int64 v88; // rdi
  unsigned __int64 v89; // rax
  __int64 v90; // rax
  __int64 v91; // rdi
  unsigned __int64 v92; // rax
  unsigned __int64 v93; // rdi
  unsigned __int64 v94; // rax
  _DWORD *v95; // rax
  LPVOID v96; // rsi
  unsigned int *v97; // rax
  void *v98; // rdi
  HANDLE v99; // rax
  __int64 result; // rax
  __int64 v101; // rax
  int v102; // [rsp+28h] [rbp-A9h]
  int v103; // [rsp+28h] [rbp-A9h]
  int v104; // [rsp+28h] [rbp-A9h]
  int v105; // [rsp+28h] [rbp-A9h]
  int v106; // [rsp+28h] [rbp-A9h]
  int v107; // [rsp+28h] [rbp-A9h]
  int v108; // [rsp+28h] [rbp-A9h]
  int v109; // [rsp+28h] [rbp-A9h]
  int v110; // [rsp+28h] [rbp-A9h]
  int v111; // [rsp+28h] [rbp-A9h]
  int v112; // [rsp+28h] [rbp-A9h]
  int v113; // [rsp+28h] [rbp-A9h]
  int v114; // [rsp+30h] [rbp-A1h]
  int v115; // [rsp+30h] [rbp-A1h]
  int v116; // [rsp+38h] [rbp-99h]
  int v117; // [rsp+38h] [rbp-99h]
  __int64 v118; // [rsp+48h] [rbp-89h] BYREF
  int v119; // [rsp+58h] [rbp-79h] BYREF
  __int64 v120; // [rsp+5Ch] [rbp-75h]
  LPVOID lpMem; // [rsp+68h] [rbp-69h]
  _WORD v122[68]; // [rsp+70h] [rbp-61h] BYREF

  if ( (*((_BYTE *)this + 408) & 0x10) != 0 )
  {
    v4 = NativeImageDumper::DataPtrToDisplay(this, a2);
    (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, __int64))(**((_QWORD **)this + 17) + 392LL))(
      *((_QWORD *)this + 17),
      "module",
      v4,
      1576);
  }
  v5 = DacInstantiateClassByVTable(a2);
  if ( (*((_BYTE *)this + 408) & 0x10) != 0 )
  {
    v102 = NativeImageDumper::DataPtrToDisplay(this, *(_QWORD *)(v5 + 16));
    (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64))(**((_QWORD **)this + 17) + 320LL))(
      *((_QWORD *)this + 17),
      "m_file",
      16,
      8);
  }
  v6 = *(_QWORD *)(DacInstantiateClassByVTable(a2) + 24);
  v7 = *((_DWORD *)this + 102);
  if ( (v7 & 0x10) != 0 )
  {
    v118 = v6;
    NativeImageDumper::DoWriteFieldMethodDesc(this, (__int64)&v118);
    v7 = *((_DWORD *)this + 102);
    if ( (v7 & 0x10) != 0 )
    {
      v102 = *(_DWORD *)(DacInstantiateClassByVTable(a2) + 32);
      (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 344LL))(
        *((_QWORD *)this + 17),
        "m_dwTransientFlags",
        32);
      v7 = *((_DWORD *)this + 102);
    }
  }
  if ( (v7 & 0x10) != 0 )
  {
    v120 = 128;
    lpMem = v122;
    v119 = 2;
    v122[0] = 0;
    v8 = DacInstantiateClassByVTable(a2);
    EnumFlagsToString(
      *(_DWORD *)(v8 + 36),
      (const struct NativeImageDumper::EnumMnemonics *)&NativeImageDumper::s_ModulePersistedFlags,
      14,
      L"|",
      (struct SString *)&v119);
    SString::ConvertToUnicode((SString *)&v119);
    v102 = *(_DWORD *)(DacInstantiateClassByVTable(a2) + 36);
    (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64))(**((_QWORD **)this + 17) + 352LL))(
      *((_QWORD *)this + 17),
      "m_dwPersistedFlags",
      36,
      4);
    if ( (v120 & 0x800000000LL) != 0 )
    {
      v9 = lpMem;
      if ( lpMem )
      {
        ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          ProcessHeap = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
        }
        HeapFree(ProcessHeap, 0, v9);
      }
    }
  }
  if ( (*((_DWORD *)this + 102) & 0x10) != 0 )
  {
    v11 = DacInstantiateClassByVTable(a2);
    v102 = NativeImageDumper::DataPtrToDisplay(this, *(_QWORD *)(v11 + 48));
    (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64))(**((_QWORD **)this + 17) + 320LL))(
      *((_QWORD *)this + 17),
      "m_pAssembly",
      48,
      8);
    if ( (*((_DWORD *)this + 102) & 0x10) != 0 )
    {
      v102 = *(_DWORD *)(DacInstantiateClassByVTable(a2) + 56);
      (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 344LL))(
        *((_QWORD *)this + 17),
        "m_moduleRef",
        56);
      if ( (*((_DWORD *)this + 102) & 0x10) != 0 )
      {
        v102 = *(_DWORD *)(DacInstantiateClassByVTable(a2) + 1152);
        (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64))(**((_QWORD **)this + 17) + 336LL))(
          *((_QWORD *)this + 17),
          "m_dwDebuggerJMCProbeCount",
          1152,
          4);
      }
    }
  }
  v12 = *(_QWORD *)(DacInstantiateClassByVTable(a2) + 1168);
  v13 = DacInstantiateTypeByAddressHelper(v12, 0x40u, 1, 1);
  v14 = *((_DWORD *)this + 102);
  if ( v13 )
  {
    if ( (v14 & 0x10) != 0 )
    {
      v102 = NativeImageDumper::DataPtrToDisplay(this, v12);
      (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64))(**((_QWORD **)this + 17) + 408LL))(
        *((_QWORD *)this + 17),
        "m_pBinder",
        1168,
        8);
      v14 = *((_DWORD *)this + 102);
    }
    if ( (v14 & 0x10) != 0 )
    {
      v15 = DacInstantiateTypeByAddressHelper(v12, 0x40u, 1, 1);
      v102 = NativeImageDumper::DataPtrToDisplay(this, v15[4]);
      (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64))(**((_QWORD **)this + 17) + 320LL))(
        *((_QWORD *)this + 17),
        "m_classDescriptions",
        32,
        8);
      if ( (*((_DWORD *)this + 102) & 0x10) != 0 )
      {
        v16 = DacInstantiateTypeByAddressHelper(v12, 0x40u, 1, 1);
        v102 = NativeImageDumper::DataPtrToDisplay(this, v16[5]);
        (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64))(**((_QWORD **)this + 17) + 320LL))(
          *((_QWORD *)this + 17),
          "m_methodDescriptions",
          40,
          8);
        if ( (*((_DWORD *)this + 102) & 0x10) != 0 )
        {
          v17 = DacInstantiateTypeByAddressHelper(v12, 0x40u, 1, 1);
          v102 = NativeImageDumper::DataPtrToDisplay(this, v17[6]);
          (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64))(**((_QWORD **)this + 17) + 320LL))(
            *((_QWORD *)this + 17),
            "m_fieldDescriptions",
            48,
            8);
          if ( (*((_DWORD *)this + 102) & 0x10) != 0 )
          {
            v18 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper(v12, 0x40u, 1, 1);
            v102 = NativeImageDumper::DataPtrToDisplay(this, *v18);
            (*(void (__fastcall **)(_QWORD, const char *, _QWORD, __int64))(**((_QWORD **)this + 17) + 320LL))(
              *((_QWORD *)this + 17),
              "m_pModule",
              0,
              8);
            if ( (*((_DWORD *)this + 102) & 0x10) != 0 )
            {
              v102 = *((unsigned __int16 *)DacInstantiateTypeByAddressHelper(v12, 0x40u, 1, 1) + 28);
              (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 336LL))(
                *((_QWORD *)this + 17),
                "m_cClasses",
                56);
              if ( (*((_DWORD *)this + 102) & 0x10) != 0 )
              {
                DacInstantiateTypeByAddressHelper(v12, 0x40u, 1, 1);
                v19 = DacInstantiateTypeByAddressHelper(v12, 0x40u, 1, 1);
                v102 = NativeImageDumper::DataPtrToDisplay(this, v19[1]);
                (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64))(**((_QWORD **)this + 17) + 384LL))(
                  *((_QWORD *)this + 17),
                  "m_pClasses",
                  8,
                  8);
                if ( (*((_DWORD *)this + 102) & 0x10) != 0 )
                {
                  v102 = *((unsigned __int16 *)DacInstantiateTypeByAddressHelper(v12, 0x40u, 1, 1) + 30);
                  (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 336LL))(
                    *((_QWORD *)this + 17),
                    "m_cFields",
                    60);
                  if ( (*((_DWORD *)this + 102) & 0x10) != 0 )
                  {
                    DacInstantiateTypeByAddressHelper(v12, 0x40u, 1, 1);
                    v20 = DacInstantiateTypeByAddressHelper(v12, 0x40u, 1, 1);
                    v102 = NativeImageDumper::DataPtrToDisplay(this, v20[3]);
                    (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64))(**((_QWORD **)this + 17) + 384LL))(
                      *((_QWORD *)this + 17),
                      "m_pFields",
                      24,
                      8);
                    if ( (*((_DWORD *)this + 102) & 0x10) != 0 )
                    {
                      v102 = *((unsigned __int16 *)DacInstantiateTypeByAddressHelper(v12, 0x40u, 1, 1) + 29);
                      (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 336LL))(
                        *((_QWORD *)this + 17),
                        "m_cMethods",
                        58);
                      if ( (*((_DWORD *)this + 102) & 0x10) != 0 )
                      {
                        DacInstantiateTypeByAddressHelper(v12, 0x40u, 1, 1);
                        v21 = DacInstantiateTypeByAddressHelper(v12, 0x40u, 1, 1);
                        v102 = NativeImageDumper::DataPtrToDisplay(this, v21[2]);
                        (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64))(**((_QWORD **)this + 17) + 384LL))(
                          *((_QWORD *)this + 17),
                          "m_pMethods",
                          16,
                          8);
                        if ( (*((_DWORD *)this + 102) & 0x10) != 0 )
                          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else if ( (v14 & 0x10) != 0 )
  {
    v102 = 0;
    (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64))(**((_QWORD **)this + 17) + 320LL))(
      *((_QWORD *)this + 17),
      "m_pBinder",
      1168,
      8);
  }
  v118 = a2 + 376;
  NativeImageDumper::TraverseMap(this, v102, (__int64)NativeImageDumper::IterateTypeDefToMTCallback);
  v118 = a2 + 448;
  NativeImageDumper::TraverseMap(this, v103, (__int64)NativeImageDumper::IterateTypeRefToMTCallback);
  v118 = a2 + 520;
  NativeImageDumper::TraverseMap(this, v104, (__int64)NativeImageDumper::IterateMethodDefToMDCallback);
  v118 = a2 + 592;
  NativeImageDumper::TraverseMap(this, v105, (__int64)NativeImageDumper::IterateFieldDefToFDCallback);
  v118 = *(_QWORD *)(DacInstantiateClassByVTable(a2) + 664);
  NativeImageDumper::TraverseNgenHash<MemberRefToDescHashTable,MemberRefToDescHashEntry>(this);
  v118 = a2 + 672;
  NativeImageDumper::TraverseMap(this, v106, (__int64)NativeImageDumper::IterateGenericParamToDescCallback);
  v118 = a2 + 744;
  NativeImageDumper::TraverseMap(this, v107, (__int64)NativeImageDumper::IterateTypeDefToMTCallback);
  v118 = a2 + 816;
  NativeImageDumper::TraverseMap(this, v108, (__int64)NativeImageDumper::IterateMemberRefToDescCallback);
  v118 = a2 + 888;
  NativeImageDumper::TraverseMap(this, v109, (__int64)NativeImageDumper::IterateManifestModules);
  v118 = *(_QWORD *)(DacInstantiateClassByVTable(a2) + 1072);
  NativeImageDumper::TraverseNgenHash<EEClassHashTable,EEClassHashEntry>(this, v110, 1);
  v118 = *(_QWORD *)(DacInstantiateClassByVTable(a2) + 1080);
  NativeImageDumper::TraverseNgenHash<EETypeHashTable,EETypeHashEntry>(this);
  v118 = *(_QWORD *)(DacInstantiateClassByVTable(a2) + 1136);
  NativeImageDumper::TraverseNgenHash<InstMethodHashTable,InstMethodHashEntry>(this, v111, v114, v116, a2);
  v118 = *(_QWORD *)(DacInstantiateClassByVTable(a2) + 1144);
  NativeImageDumper::TraverseNgenHash<StubMethodHashTable,StubMethodHashEntry>(this, v112, v115, v117, a2);
  if ( (*((_BYTE *)this + 408) & 0x10) != 0 )
  {
    v118 = *(_QWORD *)(DacInstantiateClassByVTable(a2) + 1160);
    NativeImageDumper::TraverseNgenHash<EEClassHashTable,EEClassHashEntry>(this, v113, 0);
  }
  v118 = *(_QWORD *)(DacInstantiateClassByVTable(a2) + 1232);
  NativeImageDumper::TraverseNgenHash<GuidToMethodTableHashTable,GuidToMethodTableEntry>(this);
  if ( (*((_DWORD *)this + 102) & 0x10) != 0 )
  {
    v22 = DacInstantiateClassByVTable(a2);
    (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(**((_QWORD **)this + 17) + 368LL))(
      *((_QWORD *)this + 17),
      "m_nativeImageProfiling",
      1216,
      4,
      *(_DWORD *)(v22 + 1216));
    if ( (*((_DWORD *)this + 102) & 0x10) != 0 )
    {
      v23 = DacInstantiateClassByVTable(a2);
      v24 = **((_QWORD **)this + 17);
      v25 = NativeImageDumper::DataPtrToDisplay(this, *(_QWORD *)(v23 + 1224));
      (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64))(v24 + 320))(
        *((_QWORD *)this + 17),
        "m_methodProfileList",
        1224,
        8,
        v25);
    }
  }
  v26 = DacInstantiateClassByVTable(a2);
  LOBYTE(v27) = 1;
  v28 = DacGetTargetAddrForHostAddr(v26, v27) + 1240;
  v29 = *((_DWORD *)this + 102);
  if ( (v29 & 0x800000) != 0 )
  {
    v30 = NativeImageDumper::DataPtrToDisplay(this, v28);
    (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, __int64))(**((_QWORD **)this + 17)
                                                                                              + 408LL))(
      *((_QWORD *)this + 17),
      "m_ModuleCtorInfo",
      1240,
      88,
      v30,
      88);
    v29 = *((_DWORD *)this + 102);
    if ( (v29 & 0x800000) != 0 )
    {
      v31 = DacInstantiateTypeByAddressHelper(v28, 0x58u, 1, 1);
      (*(void (__fastcall **)(_QWORD, const char *, _QWORD, __int64, _DWORD))(**((_QWORD **)this + 17) + 336LL))(
        *((_QWORD *)this + 17),
        "numElements",
        0,
        4,
        *v31);
      v29 = *((_DWORD *)this + 102);
      if ( (v29 & 0x800000) != 0 )
      {
        v32 = DacInstantiateTypeByAddressHelper(v28, 0x58u, 1, 1);
        (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(**((_QWORD **)this + 17) + 336LL))(
          *((_QWORD *)this + 17),
          "numLastAllocated",
          4,
          4,
          v32[1]);
        v29 = *((_DWORD *)this + 102);
        if ( (v29 & 0x800000) != 0 )
        {
          v33 = DacInstantiateTypeByAddressHelper(v28, 0x58u, 1, 1);
          (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(**((_QWORD **)this + 17) + 336LL))(
            *((_QWORD *)this + 17),
            "numElementsHot",
            8,
            4,
            v33[2]);
          v29 = *((_DWORD *)this + 102);
          if ( (v29 & 0x800000) != 0 )
          {
            v34 = (unsigned int *)DacInstantiateTypeByAddressHelper(v28, 0x58u, 1, 1);
            v35 = DacInstantiateTypeByAddressHelper(v28, 0x58u, 1, 1);
            v36 = NativeImageDumper::DataPtrToDisplay(this, v35[2]);
            (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, __int64))(**((_QWORD **)this + 17) + 384LL))(
              *((_QWORD *)this + 17),
              "ppMT",
              16,
              8,
              v36,
              8LL * *v34);
            v29 = *((_DWORD *)this + 102);
            if ( (v29 & 0x800000) != 0 )
            {
              v37 = (unsigned int *)DacInstantiateTypeByAddressHelper(v28, 0x58u, 1, 1);
              v38 = DacInstantiateTypeByAddressHelper(v28, 0x58u, 1, 1);
              v39 = NativeImageDumper::DataPtrToDisplay(this, v38[3]);
              (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, __int64))(**((_QWORD **)this + 17) + 384LL))(
                *((_QWORD *)this + 17),
                "cctorInfoHot",
                24,
                8,
                v39,
                12LL * v37[2]);
              v29 = *((_DWORD *)this + 102);
            }
          }
        }
      }
    }
  }
  if ( (v29 & 0x800000) != 0 )
  {
    v40 = DacInstantiateTypeByAddressHelper(v28, 0x58u, 1, 1);
    v41 = DacInstantiateTypeByAddressHelper(v28, 0x58u, 1, 1);
    v42 = DacInstantiateTypeByAddressHelper(v28, 0x58u, 1, 1);
    v43 = NativeImageDumper::DataPtrToDisplay(this, v42[4]);
    (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, __int64))(**((_QWORD **)this + 17)
                                                                                              + 384LL))(
      *((_QWORD *)this + 17),
      "cctorInfoCold",
      32,
      8,
      v43,
      12LL * (unsigned int)(*v40 - v41[2]));
    v29 = *((_DWORD *)this + 102);
    if ( (v29 & 0x800000) != 0 )
    {
      v44 = DacInstantiateTypeByAddressHelper(v28, 0x58u, 1, 1);
      v45 = DacInstantiateTypeByAddressHelper(v28, 0x58u, 1, 1);
      v46 = NativeImageDumper::DataPtrToDisplay(this, v45[5]);
      (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, __int64))(**((_QWORD **)this + 17)
                                                                                                + 384LL))(
        *((_QWORD *)this + 17),
        "hotHashOffsets",
        40,
        8,
        v46,
        4LL * (unsigned int)(v44[14] + 1));
      v29 = *((_DWORD *)this + 102);
      if ( (v29 & 0x800000) != 0 )
      {
        v47 = DacInstantiateTypeByAddressHelper(v28, 0x58u, 1, 1);
        v48 = DacInstantiateTypeByAddressHelper(v28, 0x58u, 1, 1);
        v49 = NativeImageDumper::DataPtrToDisplay(this, v48[6]);
        (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, __int64))(**((_QWORD **)this + 17)
                                                                                                  + 384LL))(
          *((_QWORD *)this + 17),
          "coldHashOffsets",
          48,
          8,
          v49,
          4LL * (unsigned int)(v47[15] + 1));
        v29 = *((_DWORD *)this + 102);
        if ( (v29 & 0x800000) != 0 )
        {
          v50 = DacInstantiateTypeByAddressHelper(v28, 0x58u, 1, 1);
          (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(**((_QWORD **)this + 17) + 336LL))(
            *((_QWORD *)this + 17),
            "numHotHashes",
            56,
            4,
            v50[14]);
          v29 = *((_DWORD *)this + 102);
          if ( (v29 & 0x800000) != 0 )
          {
            v51 = DacInstantiateTypeByAddressHelper(v28, 0x58u, 1, 1);
            (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(**((_QWORD **)this + 17) + 336LL))(
              *((_QWORD *)this + 17),
              "numColdHashes",
              60,
              4,
              v51[15]);
            v29 = *((_DWORD *)this + 102);
            if ( (v29 & 0x800000) != 0 )
            {
              v52 = (unsigned int *)DacInstantiateTypeByAddressHelper(v28, 0x58u, 1, 1);
              v53 = DacInstantiateTypeByAddressHelper(v28, 0x58u, 1, 1);
              v54 = NativeImageDumper::DataPtrToDisplay(this, v53[8]);
              (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, __int64))(**((_QWORD **)this + 17) + 384LL))(
                *((_QWORD *)this + 17),
                "ppHotGCStaticsMTs",
                64,
                8,
                v54,
                8LL * v52[20]);
              v29 = *((_DWORD *)this + 102);
              if ( (v29 & 0x800000) != 0 )
              {
                v55 = (unsigned int *)DacInstantiateTypeByAddressHelper(v28, 0x58u, 1, 1);
                v56 = DacInstantiateTypeByAddressHelper(v28, 0x58u, 1, 1);
                v57 = NativeImageDumper::DataPtrToDisplay(this, v56[9]);
                (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, __int64))(**((_QWORD **)this + 17) + 384LL))(
                  *((_QWORD *)this + 17),
                  "ppColdGCStaticsMTs",
                  72,
                  8,
                  v57,
                  8LL * v55[21]);
                v29 = *((_DWORD *)this + 102);
                if ( (v29 & 0x800000) != 0 )
                {
                  v58 = DacInstantiateTypeByAddressHelper(v28, 0x58u, 1, 1);
                  (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(**((_QWORD **)this + 17)
                                                                                         + 336LL))(
                    *((_QWORD *)this + 17),
                    "numHotGCStaticsMTs",
                    80,
                    4,
                    v58[20]);
                  v29 = *((_DWORD *)this + 102);
                  if ( (v29 & 0x800000) != 0 )
                  {
                    v59 = DacInstantiateTypeByAddressHelper(v28, 0x58u, 1, 1);
                    (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(**((_QWORD **)this + 17)
                                                                                           + 336LL))(
                      *((_QWORD *)this + 17),
                      "numColdGCStaticsMTs",
                      84,
                      4,
                      v59[21]);
                    v29 = *((_DWORD *)this + 102);
                    if ( (v29 & 0x800000) != 0 )
                    {
                      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
                      v29 = *((_DWORD *)this + 102);
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( (v29 & 0x10) != 0 )
  {
    v60 = DacInstantiateClassByVTable(a2);
    v61 = **((_QWORD **)this + 17);
    v62 = NativeImageDumper::DataPtrToDisplay(this, *(_QWORD *)(v60 + 1336));
    (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64))(v61 + 320))(
      *((_QWORD *)this + 17),
      "m_pNgenStats",
      1336,
      8,
      v62);
    v29 = *((_DWORD *)this + 102);
  }
  if ( (v29 & 0x10) != 0 )
  {
    v63 = DacInstantiateClassByVTable(a2);
    v64 = **((_QWORD **)this + 17);
    v65 = NativeImageDumper::DataPtrToDisplay(this, *(_QWORD *)(v63 + 1344));
    (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64))(v64 + 320))(
      *((_QWORD *)this + 17),
      "m_pThunkHeap",
      1344,
      8,
      v65);
    v29 = *((_DWORD *)this + 102);
    if ( (v29 & 0x10) != 0 )
    {
      v66 = DacInstantiateClassByVTable(a2);
      v67 = DacInstantiateClassByVTable(a2);
      v68 = NativeImageDumper::DataPtrToDisplay(this, *(_QWORD *)(v67 + 1360));
      (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, _QWORD))(**((_QWORD **)this + 17)
                                                                                               + 384LL))(
        *((_QWORD *)this + 17),
        "m_propertyNameSet",
        1360,
        8,
        v68,
        *(unsigned int *)(v66 + 1368));
      v29 = *((_DWORD *)this + 102);
      if ( (v29 & 0x10) != 0 )
      {
        v69 = DacInstantiateClassByVTable(a2);
        v70 = **((_QWORD **)this + 17);
        v71 = NativeImageDumper::DataPtrToDisplay(this, *(_QWORD *)(v69 + 1384));
        (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64))(v70 + 320))(
          *((_QWORD *)this + 17),
          "m_ModuleID",
          1384,
          8,
          v71);
        v29 = *((_DWORD *)this + 102);
        if ( (v29 & 0x10) != 0 )
        {
          v72 = DacInstantiateClassByVTable(a2);
          (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _QWORD))(**((_QWORD **)this + 17) + 320LL))(
            *((_QWORD *)this + 17),
            "m_pRegularStaticOffsets",
            1400,
            8,
            *(_QWORD *)(v72 + 1400));
          v29 = *((_DWORD *)this + 102);
          if ( (v29 & 0x10) != 0 )
          {
            v73 = DacInstantiateClassByVTable(a2);
            (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(**((_QWORD **)this + 17) + 336LL))(
              *((_QWORD *)this + 17),
              "m_dwMaxGCRegularStaticHandles",
              1420,
              4,
              *(_DWORD *)(v73 + 1420));
            v29 = *((_DWORD *)this + 102);
            if ( (v29 & 0x10) != 0 )
            {
              v74 = DacInstantiateClassByVTable(a2);
              (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(**((_QWORD **)this + 17) + 336LL))(
                *((_QWORD *)this + 17),
                "m_dwRegularStaticsBlockSize",
                1428,
                4,
                *(_DWORD *)(v74 + 1428));
              v29 = *((_DWORD *)this + 102);
              if ( (v29 & 0x10) != 0 )
              {
                v75 = DacInstantiateClassByVTable(a2);
                v76 = DacInstantiateClassByVTable(a2);
                v77 = **((_QWORD **)this + 17);
                v78 = 8LL * *(_QWORD *)(v75 + 1448);
                v79 = NativeImageDumper::DataPtrToDisplay(this, *(_QWORD *)(v76 + 1456));
                (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, __int64))(v77 + 384))(
                  *((_QWORD *)this + 17),
                  "m_pDynamicStaticsInfo",
                  1456,
                  8,
                  v79,
                  v78);
                v29 = *((_DWORD *)this + 102);
                if ( (v29 & 0x10) != 0 )
                {
                  v80 = DacInstantiateClassByVTable(a2);
                  (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(**((_QWORD **)this + 17)
                                                                                         + 336LL))(
                    *((_QWORD *)this + 17),
                    "m_cDynamicEntries",
                    1440,
                    8,
                    *(_DWORD *)(v80 + 1440));
                  v29 = *((_DWORD *)this + 102);
                }
              }
            }
          }
        }
      }
    }
  }
  if ( v29 < 0 )
  {
    v81 = DacInstantiateClassByVTable(a2);
    v82 = DacInstantiateClassByVTable(a2);
    DacInstantiateTypeByAddressHelper(*(_QWORD *)(v82 + 1456), 8 * *(_DWORD *)(v81 + 1448), 1, 1);
    v29 = *((_DWORD *)this + 102);
  }
  if ( (v29 & 0x10) != 0 )
  {
    v83 = DacInstantiateClassByVTable(a2);
    (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(**((_QWORD **)this + 17) + 336LL))(
      *((_QWORD *)this + 17),
      "m_dwReliabilityContract",
      1464,
      4,
      *(_DWORD *)(v83 + 1464));
    v29 = *((_DWORD *)this + 102);
    if ( (v29 & 0x10) != 0 )
    {
      v84 = DacInstantiateClassByVTable(a2);
      v85 = **((_QWORD **)this + 17);
      v86 = NativeImageDumper::DataPtrToDisplay(this, *(_QWORD *)(v84 + 1472));
      (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64))(v85 + 320))(
        *((_QWORD *)this + 17),
        "m_pCerPrepInfo",
        1472,
        8,
        v86);
      v29 = *((_DWORD *)this + 102);
      if ( (v29 & 0x10) != 0 )
      {
        v87 = DacInstantiateClassByVTable(a2);
        v88 = **((_QWORD **)this + 17);
        v89 = NativeImageDumper::DataPtrToDisplay(this, *(_QWORD *)(v87 + 1480));
        (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64))(v88 + 320))(
          *((_QWORD *)this + 17),
          "m_pCerCrst",
          1480,
          8,
          v89);
        v29 = *((_DWORD *)this + 102);
      }
    }
  }
  if ( (v29 & 0x800010) != 0 )
  {
    v118 = *(_QWORD *)(DacInstantiateClassByVTable(a2) + 1488);
    NativeImageDumper::DumpNgenRootTable(this);
    v29 = *((_DWORD *)this + 102);
  }
  if ( (v29 & 0x10) != 0 )
  {
    v90 = DacInstantiateClassByVTable(a2);
    v91 = **((_QWORD **)this + 17);
    v92 = NativeImageDumper::DataPtrToDisplay(this, *(_QWORD *)(v90 + 1496));
    (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64))(v91 + 320))(
      *((_QWORD *)this + 17),
      "m_debuggerSpecificData.m_pDynamicILCrst",
      1496,
      8,
      v92);
  }
  v93 = *(_QWORD *)(DacInstantiateClassByVTable(a2) + 1568);
  if ( (*((_DWORD *)this + 102) & 0x10) != 0 )
  {
    v94 = NativeImageDumper::DataPtrToDisplay(this, v93);
    (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, __int64))(**((_QWORD **)this + 17)
                                                                                              + 408LL))(
      *((_QWORD *)this + 17),
      "m_pModuleSecurityDescriptor",
      1568,
      8,
      v94,
      16);
    if ( (*((_DWORD *)this + 102) & 0x10) != 0 )
    {
      v120 = 128;
      lpMem = v122;
      v119 = 2;
      v122[0] = 0;
      v95 = DacInstantiateTypeByAddressHelper(v93, 0x10u, 1, 1);
      EnumFlagsToString(
        v95[2],
        (const struct NativeImageDumper::EnumMnemonics *)&qword_1801607D0,
        7,
        L", ",
        (struct SString *)&v119);
      SString::ConvertToUnicode((SString *)&v119);
      v96 = lpMem;
      v97 = (unsigned int *)DacInstantiateTypeByAddressHelper(v93, 0x10u, 1, 1);
      (*(void (__fastcall **)(_QWORD, const char *, _QWORD, LPVOID))(**((_QWORD **)this + 17) + 240LL))(
        *((_QWORD *)this + 17),
        "Flags",
        v97[2],
        v96);
      if ( (v120 & 0x800000000LL) != 0 )
      {
        v98 = lpMem;
        if ( lpMem )
        {
          v99 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
          if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
          {
            v99 = GetProcessHeap();
            `ClrFreeInProcessHeap'::`2'::ProcessHeap = v99;
          }
          HeapFree(v99, 0, v98);
        }
      }
    }
  }
  result = *((unsigned int *)this + 102);
  if ( (result & 0x10) != 0 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
    result = *((unsigned int *)this + 102);
    if ( (result & 0x10) != 0 )
    {
      v101 = DacInstantiateClassByVTable(a2);
      (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(**((_QWORD **)this + 17) + 336LL))(
        *((_QWORD *)this + 17),
        "m_DefaultDllImportSearchPathsAttributeValue",
        1040,
        4,
        *(_DWORD *)(v101 + 1040));
      result = *((unsigned int *)this + 102);
      if ( (result & 0x10) != 0 )
        return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004c9ec  mov     rax, rsp
0x18004c9ef  mov     [rax+10h], rbx
0x18004c9f3  mov     [rax+18h], rsi
0x18004c9f7  mov     [rax+20h], rdi
0x18004c9fb  push    rbp
0x18004c9fc  push    r12
0x18004c9fe  push    r13
0x18004ca00  push    r14
0x18004ca02  push    r15
0x18004ca04  lea     rbp, [rax-5Fh]
0x18004ca08  sub     rsp, 100h
0x18004ca0f  mov     rax, cs:__security_cookie
0x18004ca16  xor     rax, rsp
0x18004ca19  mov     [rbp+57h+var_30], rax
0x18004ca1d  mov     rbx, rdx
0x18004ca20  mov     r15, rcx
0x18004ca23  mov     r13d, 628h
0x18004ca29  mov     r12d, 10h
0x18004ca2f  test    [rcx+198h], r12b
0x18004ca36  jz      short loc_18004CA64
0x18004ca38  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z; NativeImageDumper::DataPtrToDisplay(unsigned __int64)
0x18004ca3d  mov     rcx, [r15+88h]
0x18004ca44  mov     rdx, [rcx]
0x18004ca47  mov     r10, [rdx+188h]
0x18004ca4e  mov     r9d, r13d
0x18004ca51  mov     r8, rax
0x18004ca54  lea     rdx, aModule; "module"
0x18004ca5b  mov     rax, r10
0x18004ca5e  call    cs:__guard_dispatch_icall_fptr
0x18004ca64  mov     r8b, 1
0x18004ca67  mov     edx, r13d
0x18004ca6a  mov     rcx, rbx; unsigned __int64
0x18004ca6d  call    DacInstantiateClassByVTable
0x18004ca72  mov     r14d, 8
0x18004ca78  test    [r15+198h], r12b
0x18004ca7f  jz      short loc_18004CAB9
0x18004ca81  mov     rdx, [rax+10h]; unsigned __int64
0x18004ca85  mov     rcx, r15; this
0x18004ca88  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z; NativeImageDumper::DataPtrToDisplay(unsigned __int64)
0x18004ca8d  mov     rcx, [r15+88h]
0x18004ca94  mov     rdx, [rcx]
0x18004ca97  mov     r10, [rdx+140h]
0x18004ca9e  mov     [rsp+120h+var_100], rax
0x18004caa3  mov     r9d, r14d
0x18004caa6  mov     r8d, r12d
0x18004caa9  lea     rdx, aMFile; "m_file"
0x18004cab0  mov     rax, r10
0x18004cab3  call    cs:__guard_dispatch_icall_fptr
0x18004cab9  mov     r8b, 1
0x18004cabc  mov     edx, r13d
0x18004cabf  mov     rcx, rbx; unsigned __int64
0x18004cac2  call    DacInstantiateClassByVTable
0x18004cac7  mov     rax, [rax+18h]
0x18004cacb  mov     ecx, [r15+198h]
0x18004cad2  test    r12b, cl
0x18004cad5  jz      short loc_18004CB51
0x18004cad7  mov     [rsp+120h+var_E0], rax
0x18004cadc  lea     rax, [rsp+120h+var_E0]
0x18004cae1  mov     [rsp+120h+var_100], rax; __int64
0x18004cae6  mov     r9d, r14d
0x18004cae9  mov     r8d, 18h
0x18004caef  lea     rdx, aMPdllmain; "m_pDllMain"
0x18004caf6  mov     rcx, r15; this
0x18004caf9  call    ?DoWriteFieldMethodDesc@NativeImageDumper@@QEAAXPEBDIIV?$__DPtr@VMethodDesc@@@@@Z; NativeImageDumper::DoWriteFieldMethodDesc(char const *,uint,uint,__DPtr<MethodDesc>)
0x18004cafe  mov     ecx, [r15+198h]
0x18004cb05  test    r12b, cl
0x18004cb08  jz      short loc_18004CB51
0x18004cb0a  mov     r8b, 1
0x18004cb0d  mov     edx, r13d
0x18004cb10  mov     rcx, rbx; unsigned __int64
0x18004cb13  call    DacInstantiateClassByVTable
0x18004cb18  mov     rcx, [r15+88h]
0x18004cb1f  mov     rdx, [rcx]
0x18004cb22  mov     r10, [rdx+158h]
0x18004cb29  mov     edx, [rax+20h]
0x18004cb2c  mov     dword ptr [rsp+120h+var_100], edx
0x18004cb30  mov     r9d, 4
0x18004cb36  lea     r8d, [r9+1Ch]
0x18004cb3a  lea     rdx, aMDwtransientfl; "m_dwTransientFlags"
0x18004cb41  mov     rax, r10
0x18004cb44  call    cs:__guard_dispatch_icall_fptr
0x18004cb4a  mov     ecx, [r15+198h]
0x18004cb51  xor     esi, esi
0x18004cb53  test    r12b, cl
0x18004cb56  jz      loc_18004CC3A
0x18004cb5c  mov     [rbp+57h+var_D0], rsi
0x18004cb60  mov     [rbp+57h+var_D0+4], 80h
0x18004cb68  mov     [rbp+57h+lpMem], rsi
0x18004cb6c  lea     rax, [rbp+57h+var_B8]
0x18004cb70  mov     [rbp+57h+lpMem], rax
0x18004cb74  mov     dword ptr [rbp+57h+var_D0], 2
0x18004cb7b  mov     rax, [rbp+57h+lpMem]
0x18004cb7f  mov     [rax], si
0x18004cb82  mov     r8b, 1
0x18004cb85  mov     edx, r13d
0x18004cb88  mov     rcx, rbx; unsigned __int64
0x18004cb8b  call    DacInstantiateClassByVTable
0x18004cb90  lea     rcx, [rbp+57h+var_D0]
0x18004cb94  mov     [rsp+120h+var_100], rcx; struct SString *
0x18004cb99  lea     r9, asc_18013911C; "|"
0x18004cba0  lea     r8d, [rsi+0Eh]; int
0x18004cba4  lea     rdx, ?s_ModulePersistedFlags@NativeImageDumper@@2PAUEnumMnemonics@1@A; struct NativeImageDumper::EnumMnemonics *
0x18004cbab  mov     ecx, [rax+24h]; unsigned int
0x18004cbae  call    ?EnumFlagsToString@@YAXKPEBUEnumMnemonics@NativeImageDumper@@HPEBGAEAVSString@@@Z; EnumFlagsToString(ulong,NativeImageDumper::EnumMnemonics const *,int,ushort const *,SString &)
0x18004cbb3  lea     rcx, [rbp+57h+var_D0]; this
0x18004cbb7  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18004cbbc  mov     rdi, [rbp+57h+lpMem]
0x18004cbc0  mov     r8b, 1
0x18004cbc3  mov     edx, r13d
0x18004cbc6  mov     rcx, rbx; unsigned __int64
0x18004cbc9  call    DacInstantiateClassByVTable
0x18004cbce  mov     rcx, [r15+88h]
0x18004cbd5  mov     rdx, [rcx]
0x18004cbd8  mov     r10, [rdx+160h]
0x18004cbdf  mov     qword ptr [rsp+120h+var_F8], rdi
0x18004cbe4  mov     edx, [rax+24h]
0x18004cbe7  mov     dword ptr [rsp+120h+var_100], edx
0x18004cbeb  lea     r9d, [rsi+4]
0x18004cbef  lea     r8d, [rsi+24h]
0x18004cbf3  lea     rdx, aMDwpersistedfl; "m_dwPersistedFlags"
0x18004cbfa  mov     rax, r10
0x18004cbfd  call    cs:__guard_dispatch_icall_fptr
0x18004cc03  nop
0x18004cc04  test    [rbp+57h+var_C8], r14b
0x18004cc08  jz      short loc_18004CC3A
0x18004cc0a  mov     rdi, [rbp+57h+lpMem]
0x18004cc0e  test    rdi, rdi
0x18004cc11  jz      short loc_18004CC3A
0x18004cc13  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18004cc1a  test    rax, rax
0x18004cc1d  jnz     short loc_18004CC2C
0x18004cc1f  call    cs:__imp_GetProcessHeap
0x18004cc25  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18004cc2c  mov     r8, rdi; lpMem
0x18004cc2f  xor     edx, edx; dwFlags
0x18004cc31  mov     rcx, rax; hHeap
0x18004cc34  call    cs:__imp_HeapFree
0x18004cc3a  mov     eax, [r15+198h]
0x18004cc41  test    r12b, al
0x18004cc44  jz      loc_18004CD34
0x18004cc4a  mov     r8b, 1
0x18004cc4d  mov     edx, r13d
0x18004cc50  mov     rcx, rbx; unsigned __int64
0x18004cc53  call    DacInstantiateClassByVTable
0x18004cc58  mov     rdx, [rax+30h]; unsigned __int64
0x18004cc5c  mov     rcx, r15; this
0x18004cc5f  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z; NativeImageDumper::DataPtrToDisplay(unsigned __int64)
0x18004cc64  mov     rcx, [r15+88h]
0x18004cc6b  mov     rdx, [rcx]
0x18004cc6e  mov     r10, [rdx+140h]
0x18004cc75  mov     [rsp+120h+var_100], rax
0x18004cc7a  mov     r9d, r14d
0x18004cc7d  mov     r8d, 30h ; '0'
0x18004cc83  lea     rdx, aMPassembly; "m_pAssembly"
0x18004cc8a  mov     rax, r10
0x18004cc8d  call    cs:__guard_dispatch_icall_fptr
0x18004cc93  mov     eax, [r15+198h]
0x18004cc9a  test    r12b, al
0x18004cc9d  jz      loc_18004CD34
0x18004cca3  mov     r8b, 1
0x18004cca6  mov     edx, r13d
0x18004cca9  mov     rcx, rbx; unsigned __int64
0x18004ccac  call    DacInstantiateClassByVTable
0x18004ccb1  mov     rcx, [r15+88h]
0x18004ccb8  mov     rdx, [rcx]
0x18004ccbb  mov     r10, [rdx+158h]
0x18004ccc2  mov     edx, [rax+38h]
0x18004ccc5  mov     dword ptr [rsp+120h+var_100], edx
0x18004ccc9  mov     r9d, 4
0x18004cccf  lea     r8d, [r9+34h]
0x18004ccd3  lea     rdx, aMModuleref; "m_moduleRef"
0x18004ccda  mov     rax, r10
0x18004ccdd  call    cs:__guard_dispatch_icall_fptr
0x18004cce3  mov     eax, [r15+198h]
0x18004ccea  test    r12b, al
0x18004cced  jz      short loc_18004CD34
0x18004ccef  mov     r8b, 1
0x18004ccf2  mov     edx, r13d
0x18004ccf5  mov     rcx, rbx; unsigned __int64
0x18004ccf8  call    DacInstantiateClassByVTable
0x18004ccfd  mov     rcx, [r15+88h]
0x18004cd04  mov     rdx, [rcx]
0x18004cd07  mov     r10, [rdx+150h]
0x18004cd0e  mov     edx, [rax+480h]
0x18004cd14  mov     dword ptr [rsp+120h+var_100], edx
0x18004cd18  mov     r9d, 4
0x18004cd1e  mov     r8d, 480h
0x18004cd24  lea     rdx, aMDwdebuggerjmc; "m_dwDebuggerJMCProbeCount"
0x18004cd2b  mov     rax, r10
0x18004cd2e  call    cs:__guard_dispatch_icall_fptr
0x18004cd34  mov     r8b, 1
0x18004cd37  mov     edx, r13d
0x18004cd3a  mov     rcx, rbx; unsigned __int64
0x18004cd3d  call    DacInstantiateClassByVTable
0x18004cd42  mov     rdi, [rax+490h]
0x18004cd49  mov     r9b, 1; bool
0x18004cd4c  mov     r8b, r9b; bool
0x18004cd4f  mov     edx, 40h ; '@'; unsigned int
0x18004cd54  mov     rcx, rdi; unsigned __int64
0x18004cd57  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18004cd5c  mov     ecx, [r15+198h]
0x18004cd63  mov     edx, ecx
0x18004cd65  and     edx, r12d
0x18004cd68  test    rax, rax
0x18004cd6b  jz      loc_18004DC2C
0x18004cd71  test    edx, edx
0x18004cd73  jz      short loc_18004CDC2
0x18004cd75  mov     rdx, rdi; unsigned __int64
0x18004cd78  mov     rcx, r15; this
0x18004cd7b  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z; NativeImageDumper::DataPtrToDisplay(unsigned __int64)
0x18004cd80  mov     rcx, [r15+88h]
0x18004cd87  mov     rdx, [rcx]
0x18004cd8a  mov     r10, [rdx+198h]
0x18004cd91  mov     esi, 40h ; '@'
0x18004cd96  mov     qword ptr [rsp+120h+var_F8], rsi
0x18004cd9b  mov     [rsp+120h+var_100], rax
0x18004cda0  mov     r9d, r14d
0x18004cda3  mov     r8d, 490h
0x18004cda9  lea     rdx, aMPbinder; "m_pBinder"
0x18004cdb0  mov     rax, r10
0x18004cdb3  call    cs:__guard_dispatch_icall_fptr
0x18004cdb9  mov     ecx, [r15+198h]
0x18004cdc0  jmp     short loc_18004CDC7
0x18004cdc2  mov     esi, 40h ; '@'
0x18004cdc7  test    r12b, cl
0x18004cdca  jz      loc_18004D1C4
0x18004cdd0  mov     r9b, 1; bool
0x18004cdd3  mov     r8b, r9b; bool
0x18004cdd6  mov     edx, esi; unsigned int
0x18004cdd8  mov     rcx, rdi; unsigned __int64
0x18004cddb  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18004cde0  mov     rdx, [rax+20h]; unsigned __int64
0x18004cde4  mov     rcx, r15; this
0x18004cde7  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z; NativeImageDumper::DataPtrToDisplay(unsigned __int64)
0x18004cdec  mov     rcx, [r15+88h]
0x18004cdf3  mov     rdx, [rcx]
0x18004cdf6  mov     r10, [rdx+140h]
0x18004cdfd  mov     [rsp+120h+var_100], rax
0x18004ce02  mov     r9d, r14d
0x18004ce05  mov     r8d, 20h ; ' '
0x18004ce0b  lea     rdx, aMClassdescript; "m_classDescriptions"
0x18004ce12  mov     rax, r10
0x18004ce15  call    cs:__guard_dispatch_icall_fptr
0x18004ce1b  mov     ecx, [r15+198h]
0x18004ce22  test    r12b, cl
0x18004ce25  jz      loc_18004D1C4
0x18004ce2b  mov     r9b, 1; bool
0x18004ce2e  mov     r8b, r9b; bool
0x18004ce31  mov     edx, esi; unsigned int
0x18004ce33  mov     rcx, rdi; unsigned __int64
0x18004ce36  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18004ce3b  mov     rdx, [rax+28h]; unsigned __int64
0x18004ce3f  mov     rcx, r15; this
0x18004ce42  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z; NativeImageDumper::DataPtrToDisplay(unsigned __int64)
0x18004ce47  mov     rcx, [r15+88h]
0x18004ce4e  mov     rdx, [rcx]
0x18004ce51  mov     r10, [rdx+140h]
0x18004ce58  mov     [rsp+120h+var_100], rax
0x18004ce5d  mov     r9d, r14d
0x18004ce60  mov     r8d, 28h ; '('
0x18004ce66  lea     rdx, aMMethoddescrip; "m_methodDescriptions"
0x18004ce6d  mov     rax, r10
0x18004ce70  call    cs:__guard_dispatch_icall_fptr
0x18004ce76  mov     ecx, [r15+198h]
0x18004ce7d  test    r12b, cl
0x18004ce80  jz      loc_18004D1C4
0x18004ce86  mov     r9b, 1; bool
0x18004ce89  mov     r8b, r9b; bool
0x18004ce8c  mov     edx, esi; unsigned int
0x18004ce8e  mov     rcx, rdi; unsigned __int64
0x18004ce91  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18004ce96  mov     rdx, [rax+30h]; unsigned __int64
0x18004ce9a  mov     rcx, r15; this
0x18004ce9d  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z; NativeImageDumper::DataPtrToDisplay(unsigned __int64)
0x18004cea2  mov     rcx, [r15+88h]
0x18004cea9  mov     rdx, [rcx]
0x18004ceac  mov     r10, [rdx+140h]
0x18004ceb3  mov     [rsp+120h+var_100], rax
0x18004ceb8  mov     r9d, r14d
0x18004cebb  mov     r8d, 30h ; '0'
0x18004cec1  lea     rdx, aMFielddescript; "m_fieldDescriptions"
0x18004cec8  mov     rax, r10
0x18004cecb  call    cs:__guard_dispatch_icall_fptr
0x18004ced1  mov     ecx, [r15+198h]
0x18004ced8  test    r12b, cl
0x18004cedb  jz      loc_18004D1C4
0x18004cee1  mov     r9b, 1; bool
0x18004cee4  mov     r8b, r9b; bool
0x18004cee7  mov     edx, esi; unsigned int
0x18004cee9  mov     rcx, rdi; unsigned __int64
0x18004ceec  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18004cef1  mov     rdx, [rax]; unsigned __int64
0x18004cef4  mov     rcx, r15; this
0x18004cef7  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z; NativeImageDumper::DataPtrToDisplay(unsigned __int64)
0x18004cefc  mov     rcx, [r15+88h]
0x18004cf03  mov     rdx, [rcx]
0x18004cf06  mov     r10, [rdx+140h]
0x18004cf0d  mov     [rsp+120h+var_100], rax
0x18004cf12  mov     r9d, r14d
0x18004cf15  xor     r8d, r8d
  ... truncated ...
```
