# NativeImageDumper::DumpEEClassForMethodTable(__DPtr<MethodTable>)

- ea: `0x18005bb2c`
- end: `0x18005dd86`
- name: `?DumpEEClassForMethodTable@NativeImageDumper@@QEAAXV?$__DPtr@VMethodTable@@@@@Z`
- size: `8794`
- prototype: `__int64 __fastcall(NativeImageDumper *this)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180053538`

## callees

- `0x180020e20`
- `0x1800210f0`
- `0x180022068`
- `0x18004240c`
- `0x180042724`
- `0x180042e18`
- `0x18005106c`
- `0x180053420`
- `0x180054090`
- `0x180054204`
- `0x1800547e4`
- `0x180054980`
- `0x180054a1c`
- `0x180054e3c`
- `0x1800552bc`
- `0x180055f3c`
- `0x18005609c`
- `0x1800599a4`
- `0x18005bb2c`
- `0x180064318`
- `0x1800675c4`
- `0x180072664`
- `0x18007344c`
- `0x18007d678`
- `0x180081de0`
- `0x180089fd4`
- `0x1800f0d20`
- `0x180106100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18005bda0`
- `KERNEL32!HeapFree` at `0x18005bf51`
- `KERNEL32!HeapFree` at `0x18005c332`
- `KERNEL32!HeapFree` at `0x18005bda0`
- `KERNEL32!HeapFree` at `0x18005bf51`
- `KERNEL32!HeapFree` at `0x18005c332`
- `KERNEL32!GetProcessHeap` at `0x18005bd8b`
- `KERNEL32!GetProcessHeap` at `0x18005bf3c`
- `KERNEL32!GetProcessHeap` at `0x18005c31d`
- `KERNEL32!GetProcessHeap` at `0x18005bd8b`
- `KERNEL32!GetProcessHeap` at `0x18005bf3c`
- `KERNEL32!GetProcessHeap` at `0x18005c31d`

## string_xrefs

- `0x18005d3d8`: `m_pComPlusCallInfo`
- `0x18005c6e2`: `m_flagsAndTokenRange`
- `0x18005ca2b`: `ComInterfaceType`
- `0x18005cad0`: `m_pccwTemplate`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall NativeImageDumper::DumpEEClassForMethodTable(NativeImageDumper *this, unsigned __int64 *a2)
{
  unsigned __int64 *v2; // r12
  unsigned __int64 v4; // rdi
  unsigned __int64 v5; // rcx
  const char *v6; // r14
  _BYTE *v7; // rax
  __int64 v8; // rdx
  _BYTE *v9; // rsi
  __int64 TargetAddrForHostAddr; // rax
  void *v11; // r15
  unsigned int v12; // r10d
  int v13; // eax
  int v14; // r10d
  __int64 v15; // r11
  unsigned int v16; // eax
  unsigned int v17; // esi
  unsigned __int64 v18; // rax
  void *v19; // rsi
  HANDLE ProcessHeap; // rax
  unsigned __int64 v21; // rsi
  int v22; // eax
  unsigned __int64 v23; // rax
  struct _GUID *v24; // rax
  void *v25; // rsi
  HANDLE v26; // rax
  _QWORD *v27; // rsi
  __int64 v28; // rdx
  unsigned __int64 v29; // rsi
  unsigned int v30; // r14d
  int v31; // ecx
  unsigned __int64 v32; // r15
  unsigned __int64 v33; // r14
  unsigned __int64 v34; // rcx
  unsigned __int64 v35; // rcx
  unsigned __int64 v36; // rdx
  _DWORD *v37; // rax
  LPVOID v38; // rsi
  _DWORD *v39; // rax
  void *v40; // rsi
  HANDLE v41; // rax
  _DWORD *v42; // rax
  _QWORD *v43; // rsi
  __int64 v44; // rdx
  unsigned __int64 v45; // rsi
  unsigned __int64 *v46; // rdi
  __int64 v47; // r14
  unsigned __int64 v48; // rax
  _QWORD *v49; // r14
  __int64 v50; // rdx
  unsigned __int64 v51; // rdx
  unsigned __int64 v52; // rax
  _QWORD *v53; // r14
  __int64 v54; // rdx
  unsigned __int64 v55; // rdx
  int v56; // eax
  unsigned __int8 *v57; // rax
  void *v58; // rax
  __int64 v59; // rdx
  __int64 v60; // rax
  void *v61; // rax
  __int64 v62; // rdx
  unsigned __int64 v63; // r14
  void *v64; // rax
  void *v65; // r12
  MethodDesc *v66; // r15
  __int64 v67; // rdx
  __int64 v68; // r14
  void *v69; // r12
  __int64 v70; // r15
  __int64 v71; // rdx
  _QWORD *v72; // rsi
  __int64 v73; // rdx
  _BYTE *v74; // rax
  _QWORD *v75; // rax
  __int64 v76; // rsi
  _QWORD *v77; // rax
  int v78; // ecx
  unsigned __int64 v79; // rax
  void *v80; // rax
  __int64 v81; // rdx
  unsigned __int64 v82; // rsi
  int v83; // eax
  unsigned __int64 v84; // rax
  _DWORD *v85; // rax
  unsigned __int8 *v86; // rax
  unsigned __int8 *v87; // rax
  LPVOID v88; // r14
  unsigned __int8 *v89; // rax
  unsigned __int64 v90; // r14
  int v91; // eax
  int v92; // eax
  int v93; // r9d
  int v94; // r9d
  int v95; // r9d
  unsigned __int64 v96; // rdx
  int v97; // ecx
  unsigned __int64 v98; // rax
  _QWORD *v99; // rax
  __int64 v100; // rax
  int v101; // ecx
  _QWORD *v102; // rsi
  __int64 v103; // rdx
  unsigned __int64 v104; // r14
  unsigned __int64 v105; // rax
  unsigned __int64 v106; // rsi
  int v107; // eax
  unsigned __int64 v108; // rax
  unsigned __int16 i; // r12
  __int64 v110; // r15
  __int64 v111; // r15
  __int64 v112; // rax
  __int64 v113; // r15
  __int64 v114; // rax
  _QWORD *v115; // rax
  int v116; // ecx
  unsigned __int64 v117; // rsi
  int v118; // eax
  unsigned __int16 *v119; // rax
  unsigned __int64 v120; // rdx
  int v121; // eax
  _QWORD *v122; // rax
  __int64 v123; // rdx
  _QWORD *v124; // rsi
  __int64 v125; // rax
  _QWORD *v126; // rax
  __int64 v127; // rdx
  _QWORD *v128; // rsi
  __int64 v129; // rax
  unsigned int *v130; // rax
  _QWORD *v131; // rax
  unsigned __int64 *OptionalFields; // rax
  struct SString *v133; // [rsp+20h] [rbp-E0h]
  struct SString *v134; // [rsp+20h] [rbp-E0h]
  __int64 v135; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v136; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v137; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v138; // [rsp+58h] [rbp-A8h]
  int v139; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v140; // [rsp+64h] [rbp-9Ch]
  LPVOID lpMem; // [rsp+70h] [rbp-90h]
  _WORD v142[68]; // [rsp+78h] [rbp-88h] BYREF

  v2 = a2;
  v138 = (__int64 *)a2;
  v4 = *((_QWORD *)DacInstantiateTypeByAddressHelper(*a2, 0x40u, 1, 1) + 5);
  v137 = v4;
  if ( (v4 & 2) != 0 )
  {
    if ( (v4 & 1) != 0 )
      v5 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v4 - 3, 8u, 1, 1);
    else
      v5 = v4 - 2;
    v4 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v5, 0x40u, 1, 1) + 5);
    v137 = v4;
  }
  if ( (*((_BYTE *)DacInstantiateTypeByAddressHelper(v4, 0x48u, 1, 1) + 60) & 0x40) != 0 )
  {
    v6 = "LayoutEEClass";
  }
  else if ( (*(_DWORD *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1) & 0xC0000) == 0x80000 )
  {
    v6 = "ArrayClass";
  }
  else
  {
    v6 = "DelegateEEClass";
    if ( (*((_BYTE *)DacInstantiateTypeByAddressHelper(v4, 0x48u, 1, 1) + 60) & 2) == 0 )
      v6 = "EEClass";
  }
  if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
  {
    v7 = DacInstantiateTypeByAddressHelper(v4, 0x48u, 1, 1);
    v9 = v7;
    if ( v7[65] )
    {
      LOBYTE(v8) = 1;
      TargetAddrForHostAddr = DacGetTargetAddrForHostAddr(v7, v8);
      v11 = DacInstantiateTypeByAddressHelper(TargetAddrForHostAddr + (unsigned __int8)v9[66], 0x2Cu, 1, 1);
      v12 = 0;
      do
      {
        v13 = PackedDWORDFields<11>::BitVectorGet(v11, v12, 5);
        v12 = v13 + 6 + v14;
      }
      while ( v15 != 1 );
      v16 = 4 * ((v12 + 31) >> 5);
    }
    else
    {
      v16 = 44;
    }
    v17 = v16 + (unsigned __int8)v9[66];
    v18 = NativeImageDumper::DataPtrToDisplay(this, v4);
    (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, _QWORD))(**((_QWORD **)this + 17) + 392LL))(
      *((_QWORD *)this + 17),
      v6,
      v18,
      v17);
  }
  v140 = 128;
  lpMem = v142;
  v139 = 2;
  v142[0] = 0;
  v136 = *v2;
  NativeImageDumper::MethodTableToString(this);
  if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
  {
    SString::ConvertToUnicode((SString *)&v139);
    (*(void (__fastcall **)(_QWORD, const char *, LPVOID))(**((_QWORD **)this + 17) + 216LL))(
      *((_QWORD *)this + 17),
      "Name",
      lpMem);
  }
  if ( (v140 & 0x800000000LL) != 0 )
  {
    v19 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v19);
    }
  }
  v21 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v4, 0x48u, 1, 1);
  v22 = *((_DWORD *)this + 102) & 0x4000;
  if ( v21 )
  {
    if ( v22 )
    {
      v23 = NativeImageDumper::DataPtrToDisplay(this, v21);
      (*(void (__fastcall **)(_QWORD, const char *, _QWORD, __int64, unsigned __int64, __int64))(**((_QWORD **)this + 17)
                                                                                               + 408LL))(
        *((_QWORD *)this + 17),
        "m_pGuidInfo",
        0,
        8,
        v23,
        20);
    }
    v140 = 128;
    lpMem = v142;
    v139 = 2;
    v142[0] = 0;
    v24 = (struct _GUID *)DacInstantiateTypeByAddressHelper(v21, 0x14u, 1, 1);
    GuidToString(v24, (struct SString *)&v139);
    if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
    {
      SString::ConvertToUnicode((SString *)&v139);
      (*(void (__fastcall **)(_QWORD, const char *, _QWORD, __int64, LPVOID))(**((_QWORD **)this + 17) + 312LL))(
        *((_QWORD *)this + 17),
        "m_Guid",
        0,
        16,
        lpMem);
      if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
      {
        DacInstantiateTypeByAddressHelper(v21, 0x14u, 1, 1);
        (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 368LL))(
          *((_QWORD *)this + 17),
          "m_bGeneratedFromName",
          16);
        if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
      }
    }
    if ( (v140 & 0x800000000LL) != 0 )
    {
      v25 = lpMem;
      if ( lpMem )
      {
        v26 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          v26 = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = v26;
        }
        HeapFree(v26, 0, v25);
      }
    }
  }
  else if ( v22 )
  {
    (*(void (__fastcall **)(_QWORD, const char *, _QWORD, __int64, _QWORD))(**((_QWORD **)this + 17) + 320LL))(
      *((_QWORD *)this + 17),
      "m_pGuidInfo",
      0,
      8,
      0);
  }
  if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
  {
    v136 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v4, 0x48u, 1, 1) + 2);
    NativeImageDumper::DoWriteFieldMethodTable(this, (__int64)&v136);
    if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
    {
      DacInstantiateTypeByAddressHelper(v4, 0x48u, 1, 1);
      NativeImageDumper::DoWriteFieldCorElementType(this, "m_NormType", 64);
    }
  }
  v27 = DacInstantiateTypeByAddressHelper(v4, 0x48u, 1, 1);
  LOBYTE(v28) = 1;
  v29 = (v27[3] + DacGetTargetAddrForHostAddr(v27, v28) + 24) & -(__int64)(v27[3] != 0);
  v136 = *v2;
  v30 = NativeImageDumper::CountFields(this, &v136);
  v31 = *((_DWORD *)this + 102);
  v32 = v30;
  if ( (v31 & 0x4000) != 0 )
  {
    v133 = (struct SString *)NativeImageDumper::DataPtrToDisplay(this, v29);
    (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 408LL))(
      *((_QWORD *)this + 17),
      "m_pFieldDescList",
      24);
    v31 = *((_DWORD *)this + 102);
  }
  if ( v29 )
  {
    if ( (v31 & 0x40000) != 0 )
    {
      if ( (v31 & 0x4000) != 0 )
        (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 264LL))(
          *((_QWORD *)this + 17),
          "FieldDescs",
          0);
      v33 = 0;
      if ( v32 )
      {
        while ( 1 )
        {
          if ( v33 )
          {
            if ( 0xFFFFFFFFFFFFFFFFuLL / v33 < 0x10 )
              break;
            v34 = 16 * v33;
          }
          else
          {
            v34 = 0;
          }
          if ( ~v29 < v34 )
            break;
          if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
          {
            v136 = v34 + v29;
            NativeImageDumper::DumpFieldDesc(this);
          }
          if ( ++v33 >= v32 )
            goto LABEL_58;
        }
LABEL_239:
        DacError(-2146231242);
      }
LABEL_58:
      if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
        (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 272LL))(
          *((_QWORD *)this + 17),
          "Total FieldDescs");
    }
    else if ( v31 < 0 )
    {
      v35 = 0;
      if ( !v30 )
        goto LABEL_69;
      do
      {
        if ( v35 )
        {
          if ( 0xFFFFFFFFFFFFFFFFuLL / v35 < 0x10 )
            goto LABEL_239;
          v36 = 16 * v35;
        }
        else
        {
          v36 = 0;
        }
        if ( ~v29 < v36 )
          goto LABEL_239;
        ++v35;
      }
      while ( v35 < v30 );
      if ( *((int *)this + 102) < 0 )
LABEL_69:
        DacInstantiateTypeByAddressHelper(v29, 16 * v30, 1, 1);
    }
  }
  if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
    if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
    {
      v140 = 128;
      lpMem = v142;
      v139 = 2;
      v142[0] = 0;
      v37 = DacInstantiateTypeByAddressHelper(v4, 0x48u, 1, 1);
      EnumFlagsToString(
        v37[14],
        (const struct NativeImageDumper::EnumMnemonics *)&qword_1801611C0,
        24,
        L" ",
        (struct SString *)&v139);
      SString::ConvertToUnicode((SString *)&v139);
      v38 = lpMem;
      v39 = DacInstantiateTypeByAddressHelper(v4, 0x48u, 1, 1);
      (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD, LPVOID))(**((_QWORD **)this + 17) + 352LL))(
        *((_QWORD *)this + 17),
        "m_dwAttrClass",
        56,
        4,
        v39[14],
        v38);
      if ( (v140 & 0x800000000LL) != 0 )
      {
        v40 = lpMem;
        if ( lpMem )
        {
          v41 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
          if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
          {
            v41 = GetProcessHeap();
            `ClrFreeInProcessHeap'::`2'::ProcessHeap = v41;
          }
          HeapFree(v41, 0, v40);
        }
      }
    }
  }
  if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
  {
    v140 = 128;
    lpMem = v142;
    v139 = 2;
    v142[0] = 0;
    v42 = DacInstantiateTypeByAddressHelper(v4, 0x48u, 1, 1);
    EnumFlagsToString(
      v42[15],
      (const struct NativeImageDumper::EnumMnemonics *)&qword_180161340,
      39,
      L", ",
      (struct SString *)&v139);
    SString::ConvertToUnicode((SString *)&v139);
    DacInstantiateTypeByAddressHelper(v4, 0x48u, 1, 1);
    (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 352LL))(
      *((_QWORD *)this + 17),
      "m_VMFlags",
      60);
    if ( (v140 & 0x800000000LL) != 0 )
      operator delete(lpMem);
  }
  v43 = DacInstantiateTypeByAddressHelper(v4, 0x48u, 1, 1);
  LOBYTE(v44) = 1;
  v45 = (v43[4] + DacGetTargetAddrForHostAddr(v43, v44) + 32) & -(__int64)(v43[4] != 0);
  if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
  {
    HIDWORD(v133) = 0;
    (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 296LL))(
      *((_QWORD *)this + 17),
      "m_pChunks",
      32);
  }
  if ( v45 )
  {
    v46 = (unsigned __int64 *)v138;
    do
    {
      if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
      {
        v47 = 8LL * *((unsigned __int8 *)DacInstantiateTypeByAddressHelper(v45, 0x18u, 1, 1) + 16) + 32;
        v48 = NativeImageDumper::DataPtrToDisplay(this, v45);
        (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, __int64))(**((_QWORD **)this + 17) + 392LL))(
          *((_QWORD *)this + 17),
          "MethodDescChunk",
          v48,
          v47);
      }
      v49 = DacInstantiateTypeByAddressHelper(v45, 0x18u, 1, 1);
      LOBYTE(v50) = 1;
      v51 = DacGetTargetAddrForHostAddr(v49, v50) + *v49;
      if ( (v51 & 1) != 0 )
        v51 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v51 - 1, 8u, 1, 1);
      if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
      {
        v52 = NativeImageDumper::DataPtrToDisplay(this, v51);
        (*(void (__fastcall **)(_QWORD, const char *, _QWORD, __int64, unsigned __int64))(**((_QWORD **)this + 17)
                                                                                        + 320LL))(
          *((_QWORD *)this + 17),
          "m_methodTable",
          0,
          8,
          v52);
      }
      v53 = DacInstantiateTypeByAddressHelper(v45, 0x18u, 1, 1);
      LOBYTE(v54) = 1;
      v55 = (v53[1] + DacGetTargetAddrForHostAddr(v53, v54) + 8) & -(__int64)(v53[1] != 0);
      v56 = *((_DWORD *)this + 102);
      if ( (v56 & 0x4000) != 0 )
      {
        v133 = (struct SString *)NativeImageDumper::DataPtrToDisplay(this, v55);
        (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 320LL))(
          *((_QWORD *)this + 17),
          "m_next",
          8);
        v56 = *((_DWORD *)this + 102);
        if ( (v56 & 0x4000) != 0 )
        {
          LODWORD(v133) = *((unsigned __int8 *)DacInstantiateTypeByAddressHelper(v45, 0x18u, 1, 1) + 16);
          (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, struct SString *))(**((_QWORD **)this + 17)
                                                                                           + 336LL))(
            *((_QWORD *)this + 17),
            "m_size",
            16,
            1,
            v133);
          v56 = *((_DWORD *)this + 102);
          if ( (v56 & 0x4000) != 0 )
          {
            v57 = (unsigned __int8 *)DacInstantiateTypeByAddressHelper(v45, 0x18u, 1, 1);
            (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(**((_QWORD **)this + 17) + 336LL))(
              *((_QWORD *)this + 17),
              "m_count",
              17,
              1,
              v57[17]);
            v56 = *((_DWORD *)this + 102);
            if ( (v56 & 0x4000) != 0 )
            {
              DacInstantiateTypeByAddressHelper(v45, 0x18u, 1, 1);
              (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 336LL))(
                *((_QWORD *)this + 17),
                "m_flagsAndTokenRange",
                18);
              v56 = *((_DWORD *)this + 102);
            }
          }
        }
      }
      if ( (v56 & 0x80000) != 0 )
        (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 264LL))(
          *((_QWORD *)this + 17),
          "MethodDescs",
          0);
      v58 = DacInstantiateTypeByAddressHelper(v45, 0x18u, 1, 1);
      LOBYTE(v59) = 1;
      v60 = DacGetTargetAddrForHostAddr(v58, v59);
      v61 = DacInstantiateTypeByAddressHelper(v60 + 24, 8u, 1, 1);
      LOBYTE(v62) = 1;
      v63 = DacGetTargetAddrForHostAddr(v61, v62);
      if ( v63 )
      {
        do
        {
          if ( (*((_DWORD *)this + 102) & 0x80080000) != 0 )
          {
            v64 = DacInstantiateTypeByAddressHelper(*v46, 0x40u, 1, 1);
            MethodTable::GetModule(v64, &v136);
            v135 = v63;
            NativeImageDumper::DumpMethodDesc(this, (unsigned __int64 *)&v135);
          }
          v65 = DacInstantiateTypeByAddressHelper(v63, 8u, 1, 1);
          v66 = (MethodDesc *)DacInstantiateTypeByAddressHelper(v63, 8u, 1, 1);
          LOBYTE(v67) = 1;
          v68 = DacGetTargetAddrForHostAddr(v65, v67);
          v63 = MethodDesc::SizeOf(v66) + v68;
          v69 = DacInstantiateTypeByAddressHelper(v45, 0x18u, 1, 1);
          v70 = 8LL * *((unsigned __int8 *)DacInstantiateTypeByAddressHelper(v45, 0x18u, 1, 1) + 16) + 32;
          LOBYTE(v71) = 1;
        }
        while ( v63 < v70 + DacGetTargetAddrForHostAddr(v69, v71) && v63 );
      }
      if ( (*((_DWORD *)this + 102) & 0x80000) != 0 )
        (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 272LL))(
          *((_QWORD *)this + 17),
          "Total MethodDescs");
      v72 = DacInstantiateTypeByAddressHelper(v45, 0x18u, 1, 1);
      LOBYTE(v73) = 1;
      v45 = (v72[1] + DacGetTargetAddrForHostAddr(v72, v73) + 8) & -(__int64)(v72[1] != 0);
      if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
    }
    while ( v45 );
    v4 = v137;
    v2 = (unsigned __int64 *)v138;
  }
  if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
    (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 272LL))(
      *((_QWORD *)this + 17),
      "Total MethodDescChunks");
  v74 = DacInstantiateTypeByAddressHelper(v4, 0x48u, 1, 1);
  if ( (v74[60] & 0x40) != 0 && (v74[82] & 1) != 0
    || (*((_BYTE *)DacInstantiateTypeByAddressHelper(v4, 0x48u, 1, 1) + 60) & 0x40) != 0 )
  {
    if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
    {
      LODWORD(v133) = *((_DWORD *)DacInstantiateTypeByAddressHelper(v4, 0x48u, 1, 1) + 10);
      (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, struct SString *))(**((_QWORD **)this + 17) + 336LL))(
        *((_QWORD *)this + 17),
        "m_cbNativeSize",
        40,
        4,
        v133);
    }
  }
  else if ( (*((_BYTE *)DacInstantiateTypeByAddressHelper(v4, 0x48u, 1, 1) + 56) & 0x20) != 0 )
  {
    if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
    {
      v75 = DacInstantiateTypeByAddressHelper(v4, 0x48u, 1, 1);
      v76 = **((_QWORD **)this + 17);
      v134 = (struct SString *)NativeImageDumper::DataPtrToDisplay(this, v75[5]);
      (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, struct SString *))(v76 + 320))(
        *((_QWORD *)this + 17),
        "m_ohDelegate",
        40,
        8,
        v134);
    }
  }
  else
  {
    DacInstantiateTypeByAddressHelper(v4, 0x48u, 1, 1);
    DacInstantiateTypeByAddressHelper(v4, 0x48u, 1, 1);
    (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 352LL))(
      *((_QWORD *)this + 17),
      "ComInterfaceType",
      40);
  }
  v77 = DacInstantiateTypeByAddressHelper(v4, 0x48u, 1, 1);
  v78 = *((_DWORD *)this + 102) & 0x4000;
  if ( v77[6] )
  {
    if ( v78 )
      (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _QWORD))(**((_QWORD **)this + 17) + 320LL))(
        *((_QWORD *)this + 17),
        "m_pccwTemplate",
        48,
        8,
        0);
  }
  else if ( v78 )
  {
    v79 = NativeImageDumper::DataPtrToDisplay(this, 0);
    (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64))(**((_QWORD **)this + 17) + 320LL))(
      *((_QWORD *)this + 17),
      "m_pccwTemplate",
      48,
      8,
      v79);
  }
  if ( (*((_BYTE *)DacInstantiateTypeByAddressHelper(v4, 0x48u, 1, 1) + 60) & 0x40) != 0 )
  {
    if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
      (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 104LL))(
        *((_QWORD *)this + 17),
        "LayoutEEClass");
    v80 = DacInstantiateTypeByAddressHelper(v4, 0x60u, 1, 1);
    LOBYTE(v81) = 1;
    v82 = DacGetTargetAddrForHostAddr(v80, v81) + 72;
    v83 = *((_DWORD *)this + 102);
    if ( (v83 & 0x4000) != 0 )
    {
      v84 = NativeImageDumper::DataPtrToDisplay(this, v82);
      (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, __int64))(**((_QWORD **)this + 17)
                                                                                                + 408LL))(
        *((_QWORD *)this + 17),
        "m_LayoutInfo",
        72,
        24,
        v84,
        24);
      v83 = *((_DWORD *)this + 102);
    }
    if ( (v83 & 0x40000) != 0 )
    {
      LODWORD(v133) = *(_DWORD *)DacInstantiateTypeByAddressHelper(v82, 0x18u, 1, 1);
      (*(void (__fastcall **)(_QWORD, const char *, _QWORD, __int64, struct SString *))(**((_QWORD **)this + 17) + 336LL))(
        *((_QWORD *)this + 17),
        "m_cbNativeSize",
        0,
        4,
        v133);
      v83 = *((_DWORD *)this + 102);
      if ( (v83 & 0x40000) != 0 )
      {
        v85 = DacInstantiateTypeByAddressHelper(v82, 0x18u, 1, 1);
        (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(**((_QWORD **)this + 17) + 336LL))(
          *((_QWORD *)this + 17),
          "m_cbManagedSize",
          4,
          4,
          v85[1]);
        v83 = *((_DWORD *)this + 102);
        if ( (v83 & 0x40000) != 0 )
        {
          v86 = (unsigned __int8 *)DacInstantiateTypeByAddressHelper(v82, 0x18u, 1, 1);
          (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(**((_QWORD **)this + 17) + 336LL))(
            *((_QWORD *)this + 17),
            "m_LargestAlignmentRequirementOfAllMembers",
            8,
            1,
            v86[8]);
          v83 = *((_DWORD *)this + 102);
        }
      }
    }
    if ( (v83 & 0x40000) != 0 )
    {
      LODWORD(v133) = *((unsigned __int8 *)DacInstantiateTypeByAddressHelper(v82, 0x18u, 1, 1) + 9);
      (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, struct SString *))(**((_QWORD **)this + 17) + 336LL))(
        *((_QWORD *)this + 17),
        "m_ManagedLargestAlignmentRequirementOfAllMembers",
        9,
        1,
        v133);
      v83 = *((_DWORD *)this + 102);
    }
    if ( (v83 & 0x40000) != 0 )
    {
      v140 = 128;
      lpMem = v142;
      v139 = 2;
      v142[0] = 0;
      v87 = (unsigned __int8 *)DacInstantiateTypeByAddressHelper(v82, 0x18u, 1, 1);
      EnumFlagsToString(
        v87[10],
        (const struct NativeImageDumper::EnumMnemonics *)&NativeImageDumper::s_EECLIFlags,
        4,
        L", ",
        (struct SString *)&v139);
      SString::ConvertToUnicode((SString *)&v139);
      v88 = lpMem;
      v89 = (unsigned __int8 *)DacInstantiateTypeByAddressHelper(v82, 0x18u, 1, 1);
      (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD, LPVOID))(**((_QWORD **)this + 17) + 352LL))(
        *((_QWORD *)this + 17),
        "m_bFlags",
        10,
        1,
        v89[10],
        v88);
      if ( (v140 & 0x800000000LL) != 0 )
        operator delete(lpMem);
    }
    if ( (*((_DWORD *)this + 102) & 0x40000) != 0 )
    {
      DacInstantiateTypeByAddressHelper(v82, 0x18u, 1, 1);
      (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 336LL))(
        *((_QWORD *)this + 17),
        "m_numCTMFields",
        12);
    }
    v90 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v82, 0x18u, 1, 1) + 2);
    v91 = *((_DWORD *)this + 102);
    if ( (v91 & 0x40000) != 0 )
    {
      DacInstantiateTypeByAddressHelper(v82, 0x18u, 1, 1);
      HIDWORD(v133) = NativeImageDumper::DataPtrToDisplay(this, v90) >> 32;
      (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 384LL))(
        *((_QWORD *)this + 17),
        "m_pFieldMarshalers",
        16);
      v91 = *((_DWORD *)this + 102);
    }
    if ( (v91 & 0x4000) == 0 )
      goto LABEL_178;
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
    if ( (*((_DWORD *)this + 102) & 0x4000) == 0 )
      goto LABEL_178;
  }
  else
  {
    if ( (*(_DWORD *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1) & 0xC0000) == 0x80000 )
    {
      if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
      {
        (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 104LL))(
          *((_QWORD *)this + 17),
          "ArrayClass");
        if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
        {
          LODWORD(v133) = *((unsigned __int8 *)DacInstantiateTypeByAddressHelper(v4, 0x50u, 1, 1) + 72);
          (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, struct SString *))(**((_QWORD **)this + 17)
                                                                                           + 336LL))(
            *((_QWORD *)this + 17),
            "m_rank",
            72,
            1,
            v133);
        }
      }
      DacInstantiateTypeByAddressHelper(v4, 0x50u, 1, 1);
      NativeImageDumper::DoWriteFieldCorElementType(this, "m_ElementType", 76);
    }
    else
    {
      if ( (*((_BYTE *)DacInstantiateTypeByAddressHelper(v4, 0x48u, 1, 1) + 60) & 2) == 0 )
        goto LABEL_178;
      v92 = *((_DWORD *)this + 102);
      if ( (v92 & 0x4000) != 0 )
      {
        (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 104LL))(
          *((_QWORD *)this + 17),
          "DelegateEEClass");
        v92 = *((_DWORD *)this + 102);
      }
      if ( (v92 & 0x4000) != 0 )
      {
        v135 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v4, 0xA0u, 1, 1) + 9);
        NativeImageDumper::DoDumpFieldStub((_DWORD)this, (unsigned int)&v135, 72, v93, (__int64)"m_pStaticCallStub");
        if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
        {
          v135 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v4, 0xA0u, 1, 1) + 10);
          NativeImageDumper::DoDumpFieldStub(
            (_DWORD)this,
            (unsigned int)&v135,
            80,
            v94,
            (__int64)"m_pInstRetBuffCallStub");
          if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
          {
            v135 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v4, 0xA0u, 1, 1) + 11);
            NativeImageDumper::DoWriteFieldMethodDesc(this, (__int64)&v135);
            if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
            {
              v135 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v4, 0xA0u, 1, 1) + 12);
              NativeImageDumper::DoDumpFieldStub(
                (_DWORD)this,
                (unsigned int)&v135,
                96,
                v95,
                (__int64)"m_pMultiCastInvokeStub");
            }
          }
        }
      }
      v96 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v4, 0xA0u, 1, 1) + 13);
      v97 = *((_DWORD *)this + 102);
      if ( v96 )
      {
        if ( (v97 & 0x4000) != 0 )
        {
          v98 = NativeImageDumper::DataPtrToDisplay(this, v96);
          (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, __int64))(**((_QWORD **)this + 17) + 408LL))(
            *((_QWORD *)this + 17),
            "m_pUMThunkMarshInfo",
            104,
            8,
            v98,
            48);
          v97 = *((_DWORD *)this + 102);
        }
        if ( (v97 & 0x4000) != 0 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
      }
      else if ( (v97 & 0x4000) != 0 )
      {
        (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _QWORD))(**((_QWORD **)this + 17) + 320LL))(
          *((_QWORD *)this + 17),
          "m_pUMThunkMarshInfo",
          104,
          8,
          0);
      }
      if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
      {
        v135 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v4, 0xA0u, 1, 1) + 14);
        NativeImageDumper::DoWriteFieldMethodDesc(this, (__int64)&v135);
        if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
        {
          v135 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v4, 0xA0u, 1, 1) + 15);
          NativeImageDumper::DoWriteFieldMethodDesc(this, (__int64)&v135);
          if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
          {
            v99 = DacInstantiateTypeByAddressHelper(v4, 0xA0u, 1, 1);
            (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _QWORD))(**((_QWORD **)this + 17) + 320LL))(
              *((_QWORD *)this + 17),
              "m_pMarshalStub",
              128,
              8,
              v99[16]);
            if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
            {
              v135 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v4, 0xA0u, 1, 1) + 18);
              NativeImageDumper::DoWriteFieldMethodDesc(this, (__int64)&v135);
              if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
              {
                v135 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v4, 0xA0u, 1, 1) + 19);
                NativeImageDumper::DoWriteFieldMethodDesc(this, (__int64)&v135);
              }
            }
          }
        }
      }
      v100 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v4, 0xA0u, 1, 1) + 17);
      v101 = *((_DWORD *)this + 102) & 0x4000;
      if ( v100 )
      {
        if ( v101 )
        {
          v135 = v100;
          NativeImageDumper::DoDumpComPlusCallInfo(this);
        }
      }
      else if ( v101 )
      {
        (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _QWORD))(**((_QWORD **)this + 17) + 320LL))(
          *((_QWORD *)this + 17),
          "m_pComPlusCallInfo",
          136,
          8,
          0);
      }
    }
    if ( (*((_DWORD *)this + 102) & 0x4000) == 0 )
      goto LABEL_180;
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 120LL))(*((_QWORD *)this + 17));
LABEL_178:
  if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
LABEL_180:
  v102 = DacInstantiateTypeByAddressHelper(v4, 0x48u, 1, 1);
  LOBYTE(v103) = 1;
  v104 = (v102[1] + DacGetTargetAddrForHostAddr(v102, v103) + 8) & -(__int64)(v102[1] != 0);
  if ( DacInstantiateTypeByAddressHelper(v104, 0x38u, 1, 1) )
  {
    if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
    {
      v105 = NativeImageDumper::DataPtrToDisplay(this, v104);
      (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, __int64))(**((_QWORD **)this + 17) + 392LL))(
        *((_QWORD *)this + 17),
        "EEClassOptionalFields",
        v105,
        56);
    }
    v106 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v104, 0x38u, 1, 1) + 2);
    v107 = *((_DWORD *)this + 102) & 0x4000;
    if ( v106 )
    {
      if ( v107 )
      {
        v108 = NativeImageDumper::DataPtrToDisplay(this, v106);
        (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, __int64))(**((_QWORD **)this + 17) + 392LL))(
          *((_QWORD *)this + 17),
          "m_SparseVTableMap",
          v108,
          24);
      }
      v137 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v106, 0x18u, 1, 1);
      if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
        (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 264LL))(
          *((_QWORD *)this + 17),
          "m_MapList",
          0);
      for ( i = 0; i < *((_WORD *)DacInstantiateTypeByAddressHelper(v106, 0x18u, 1, 1) + 4); ++i )
      {
        if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
        {
          v110 = **((_QWORD **)this + 17);
          LODWORD(v133) = *(unsigned __int16 *)__DPtrBase<SparseVTableMap::Entry,__DPtr<SparseVTableMap::Entry>>::operator[]<unsigned short>(
                                                 &v137,
                                                 i);
          (*(void (__fastcall **)(_QWORD, const char *, _QWORD, __int64, struct SString *))(v110 + 336))(
            *((_QWORD *)this + 17),
            "m_Start",
            0,
            2,
            v133);
          if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
          {
            v111 = **((_QWORD **)this + 17);
            v112 = __DPtrBase<SparseVTableMap::Entry,__DPtr<SparseVTableMap::Entry>>::operator[]<unsigned short>(
                     &v137,
                     i);
            (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(v111 + 336))(
              *((_QWORD *)this + 17),
              "m_Span",
              2,
              2,
              *(unsigned __int16 *)(v112 + 2));
            if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
            {
              v113 = **((_QWORD **)this + 17);
              v114 = __DPtrBase<SparseVTableMap::Entry,__DPtr<SparseVTableMap::Entry>>::operator[]<unsigned short>(
                       &v137,
                       i);
              (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(v113 + 336))(
                *((_QWORD *)this + 17),
                "m_Span",
                2,
                2,
                *(unsigned __int16 *)(v114 + 4));
            }
          }
        }
      }
      if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
      {
        (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 272LL))(
          *((_QWORD *)this + 17),
          "Total Entries");
        if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
        {
          DacInstantiateTypeByAddressHelper(v106, 0x18u, 1, 1);
          (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 336LL))(
            *((_QWORD *)this + 17),
            "m_MapEntries",
            8);
          if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
          {
            DacInstantiateTypeByAddressHelper(v106, 0x18u, 1, 1);
            (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 336LL))(
              *((_QWORD *)this + 17),
              "m_Allocated",
              10);
            if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
            {
              DacInstantiateTypeByAddressHelper(v106, 0x18u, 1, 1);
              (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 336LL))(
                *((_QWORD *)this + 17),
                "m_LastUsed",
                12);
              if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
              {
                DacInstantiateTypeByAddressHelper(v106, 0x18u, 1, 1);
                (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 336LL))(
                  *((_QWORD *)this + 17),
                  "m_VTSlot",
                  14);
                if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
                {
                  DacInstantiateTypeByAddressHelper(v106, 0x18u, 1, 1);
                  (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 336LL))(
                    *((_QWORD *)this + 17),
                    "m_MTSlot",
                    16);
                  if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
                    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
                }
              }
            }
          }
        }
      }
    }
    else if ( v107 )
    {
      (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _QWORD))(**((_QWORD **)this + 17) + 320LL))(
        *((_QWORD *)this + 17),
        "m_pSparseVTableMap",
        16,
        8,
        0);
    }
    if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
    {
      DacInstantiateTypeByAddressHelper(v104, 0x38u, 1, 1);
      NativeImageDumper::DoWriteFieldTypeHandle(this, "m_pCoClassForIntf", 24);
    }
    v115 = DacInstantiateTypeByAddressHelper(v104, 0x38u, 1, 1);
    v116 = *((_DWORD *)this + 102) & 0x4000;
    if ( v115[4] )
    {
      if ( v116 )
        (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 320LL))(
          *((_QWORD *)this + 17),
          "m_pClassFactory",
          32);
    }
    else if ( v116 )
    {
      NativeImageDumper::DataPtrToDisplay(this, 0);
      (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 320LL))(
        *((_QWORD *)this + 17),
        "m_pClassFactory",
        32);
    }
    v117 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v104, 0x38u, 1, 1);
    v118 = *((_DWORD *)this + 102);
    if ( v117 )
    {
      if ( (v118 & 0x40000) != 0 )
      {
        v135 = *v138;
        v136 = v117;
        NativeImageDumper::GetDependencyFromMT(this);
        NativeImageDumper::WriteFieldDictionaryLayout(this, (__int64)&v136);
      }
      else
      {
        do
        {
          if ( *((int *)this + 102) < 0 )
          {
            v119 = (unsigned __int16 *)DacInstantiateTypeByAddressHelper(v117, 0x20u, 1, 1);
            DacInstantiateTypeByAddressHelper(v117, 16 * (v119[4] + 1), 1, 1);
          }
          v117 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v117, 0x20u, 1, 1);
        }
        while ( v117 );
      }
    }
    else if ( (v118 & 0x4000) != 0 )
    {
      (*(void (__fastcall **)(_QWORD, const char *, _QWORD, __int64, _QWORD))(**((_QWORD **)this + 17) + 320LL))(
        *((_QWORD *)this + 17),
        "m_pDictLayout",
        0,
        8,
        0);
    }
    v120 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v104, 0x38u, 1, 1) + 1);
    v121 = *((_DWORD *)this + 102) & 0x4000;
    if ( v120 )
    {
      if ( v121 )
      {
        NativeImageDumper::DataPtrToDisplay(this, v120);
        (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 320LL))(
          *((_QWORD *)this + 17),
          "m_pVarianceInfo",
          8);
      }
    }
    else if ( v121 )
    {
      (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 320LL))(
        *((_QWORD *)this + 17),
        "m_pVarianceInfo",
        8);
    }
    if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
    {
      DacInstantiateTypeByAddressHelper(v104, 0x38u, 1, 1);
      (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 336LL))(
        *((_QWORD *)this + 17),
        "m_cbModuleDynamicID",
        44);
      if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
      {
        v122 = DacInstantiateTypeByAddressHelper(v4, 0x48u, 1, 1);
        v124 = v122;
        if ( v122[1] )
        {
          LOBYTE(v123) = 1;
          v125 = DacGetTargetAddrForHostAddr(v122, v123);
          DacInstantiateTypeByAddressHelper((v124[1] + v125 + 8) & -(__int64)(v124[1] != 0), 0x38u, 1, 1);
        }
        (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 344LL))(
          *((_QWORD *)this + 17),
          "m_dwReliabilityContract",
          48);
        if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
        {
          v140 = 128;
          lpMem = v142;
          v139 = 2;
          v142[0] = 0;
          v126 = DacInstantiateTypeByAddressHelper(v4, 0x48u, 1, 1);
          v128 = v126;
          if ( v126[1] )
          {
            LOBYTE(v127) = 1;
            v129 = DacGetTargetAddrForHostAddr(v126, v127);
            v130 = (unsigned int *)((char *)DacInstantiateTypeByAddressHelper(
                                              (v128[1] + v129 + 8) & -(__int64)(v128[1] != 0),
                                              0x38u,
                                              1,
                                              1)
                                  + 52);
          }
          else
          {
            v130 = 0;
          }
          EnumFlagsToString(
            *v130,
            (const struct NativeImageDumper::EnumMnemonics *)&qword_1801615B0,
            13,
            L"|",
            (struct SString *)&v139);
          SString::ConvertToUnicode((SString *)&v139);
          v131 = DacInstantiateTypeByAddressHelper(v4, 0x48u, 1, 1);
          if ( v131[1] )
          {
            OptionalFields = (unsigned __int64 *)EEClass::GetOptionalFields(v131, &v135);
            DacInstantiateTypeByAddressHelper(*OptionalFields, 0x38u, 1, 1);
          }
          (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 352LL))(
            *((_QWORD *)this + 17),
            "m_SecProps",
            52);
          if ( (v140 & 0x800000000LL) != 0 )
            operator delete(lpMem);
        }
      }
    }
    if ( (*((_DWORD *)this + 102) & 0x4000) != 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
  }
}

```

## disassembly

```asm
0x18005bb2c  mov     [rsp-8+arg_10], rbx
0x18005bb31  push    rbp
0x18005bb32  push    rsi
0x18005bb33  push    rdi
0x18005bb34  push    r12
0x18005bb36  push    r13
0x18005bb38  push    r14
0x18005bb3a  push    r15
0x18005bb3c  lea     rbp, [rsp-10h]
0x18005bb41  sub     rsp, 110h
0x18005bb48  mov     rax, cs:__security_cookie
0x18005bb4f  xor     rax, rsp
0x18005bb52  mov     [rbp+40h+var_40], rax
0x18005bb56  mov     r12, rdx
0x18005bb59  mov     [rsp+140h+var_E8], rdx
0x18005bb5e  mov     r13, rcx
0x18005bb61  mov     r9b, 1; bool
0x18005bb64  mov     r8b, r9b; bool
0x18005bb67  mov     ebx, 40h ; '@'
0x18005bb6c  mov     edx, ebx; unsigned int
0x18005bb6e  mov     rcx, [r12]; unsigned __int64
0x18005bb72  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005bb77  mov     rdi, [rax+28h]
0x18005bb7b  mov     [rsp+140h+var_F0], rdi
0x18005bb80  test    dil, 2
0x18005bb84  jz      short loc_18005BBBC
0x18005bb86  mov     r9b, 1; bool
0x18005bb89  mov     r8b, r9b; bool
0x18005bb8c  test    r9b, dil
0x18005bb8f  jz      short loc_18005BBA8
0x18005bb91  lea     rcx, [rdi-3]; unsigned __int64
0x18005bb95  lea     edx, [rbx-38h]; unsigned int
0x18005bb98  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005bb9d  mov     r9b, 1
0x18005bba0  mov     r8b, r9b
0x18005bba3  mov     rcx, [rax]
0x18005bba6  jmp     short loc_18005BBAC
0x18005bba8  lea     rcx, [rdi-2]; unsigned __int64
0x18005bbac  mov     edx, ebx; unsigned int
0x18005bbae  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005bbb3  mov     rdi, [rax+28h]
0x18005bbb7  mov     [rsp+140h+var_F0], rdi
0x18005bbbc  mov     r9b, 1; bool
0x18005bbbf  mov     r8b, r9b; bool
0x18005bbc2  mov     edx, 48h ; 'H'; unsigned int
0x18005bbc7  mov     rcx, rdi; unsigned __int64
0x18005bbca  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005bbcf  test    [rax+3Ch], bl
0x18005bbd2  jz      short loc_18005BBDD
0x18005bbd4  lea     r14, aLayouteeclass; "LayoutEEClass"
0x18005bbdb  jmp     short loc_18005BC30
0x18005bbdd  mov     r9b, 1; bool
0x18005bbe0  mov     r8b, r9b; bool
0x18005bbe3  mov     edx, ebx; unsigned int
0x18005bbe5  mov     rcx, [r12]; unsigned __int64
0x18005bbe9  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005bbee  mov     ecx, [rax]
0x18005bbf0  and     ecx, 0C0000h
0x18005bbf6  cmp     ecx, 80000h
0x18005bbfc  jnz     short loc_18005BC07
0x18005bbfe  lea     r14, aArrayclass; "ArrayClass"
0x18005bc05  jmp     short loc_18005BC30
0x18005bc07  mov     r9b, 1; bool
0x18005bc0a  mov     r8b, r9b; bool
0x18005bc0d  mov     edx, 48h ; 'H'; unsigned int
0x18005bc12  mov     rcx, rdi; unsigned __int64
0x18005bc15  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005bc1a  test    byte ptr [rax+3Ch], 2
0x18005bc1e  lea     r14, aDelegateeeclas; "DelegateEEClass"
0x18005bc25  lea     rax, aEeclass; "EEClass"
0x18005bc2c  cmovz   r14, rax
0x18005bc30  xor     ebx, ebx
0x18005bc32  mov     r15d, 4000h
0x18005bc38  test    [r13+198h], r15d
0x18005bc3f  jz      loc_18005BCEF
0x18005bc45  mov     r9b, 1; bool
0x18005bc48  mov     r8b, r9b; bool
0x18005bc4b  lea     edx, [rbx+48h]; unsigned int
0x18005bc4e  mov     rcx, rdi; unsigned __int64
0x18005bc51  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005bc56  mov     rsi, rax
0x18005bc59  cmp     [rax+41h], bl
0x18005bc5c  jz      short loc_18005BCB6
0x18005bc5e  mov     dl, 1
0x18005bc60  mov     rcx, rax
0x18005bc63  call    DacGetTargetAddrForHostAddr
0x18005bc68  movzx   ecx, byte ptr [rsi+42h]
0x18005bc6c  add     rcx, rax; unsigned __int64
0x18005bc6f  mov     r9b, 1; bool
0x18005bc72  mov     r8b, r9b; bool
0x18005bc75  lea     edx, [rbx+2Ch]; unsigned int
0x18005bc78  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005bc7d  mov     r15, rax
0x18005bc80  mov     r10d, ebx
0x18005bc83  lea     r11d, [rbx+0Bh]
0x18005bc87  mov     r8d, 5
0x18005bc8d  mov     edx, r10d
0x18005bc90  mov     rcx, r15
0x18005bc93  call    ?BitVectorGet@?$PackedDWORDFields@$0L@@@AEAAKKK@Z; PackedDWORDFields<11>::BitVectorGet(ulong,ulong)
0x18005bc98  add     eax, 6
0x18005bc9b  add     r10d, eax
0x18005bc9e  sub     r11, 1
0x18005bca2  jnz     short loc_18005BC87
0x18005bca4  lea     eax, [r10+1Fh]
0x18005bca8  shr     eax, 5
0x18005bcab  shl     eax, 2
0x18005bcae  mov     r15d, 4000h
0x18005bcb4  jmp     short loc_18005BCBB
0x18005bcb6  mov     eax, 2Ch ; ','
0x18005bcbb  movzx   esi, byte ptr [rsi+42h]
0x18005bcbf  add     esi, eax
0x18005bcc1  mov     rdx, rdi; unsigned __int64
0x18005bcc4  mov     rcx, r13; this
0x18005bcc7  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z; NativeImageDumper::DataPtrToDisplay(unsigned __int64)
0x18005bccc  mov     r10, rax
0x18005bccf  mov     rcx, [r13+88h]
0x18005bcd6  mov     r8, [rcx]
0x18005bcd9  mov     r9d, esi
0x18005bcdc  mov     rax, [r8+188h]
0x18005bce3  mov     r8, r10
0x18005bce6  mov     rdx, r14
0x18005bce9  call    cs:__guard_dispatch_icall_fptr
0x18005bcef  mov     [rsp+140h+var_E0], rbx
0x18005bcf4  mov     [rsp+140h+var_E0+4], 80h
0x18005bcfd  mov     [rsp+140h+lpMem], rbx
0x18005bd02  lea     rax, [rsp+140h+var_C8]
0x18005bd07  mov     [rsp+140h+lpMem], rax
0x18005bd0c  mov     dword ptr [rsp+140h+var_E0], 2
0x18005bd14  mov     rax, [rsp+140h+lpMem]
0x18005bd19  mov     [rax], bx
0x18005bd1c  mov     rax, [r12]
0x18005bd20  mov     [rsp+140h+var_F8], rax
0x18005bd25  lea     r8, [rsp+140h+var_E0]
0x18005bd2a  lea     rdx, [rsp+140h+var_F8]
0x18005bd2f  mov     rcx, r13; this
0x18005bd32  call    ?MethodTableToString@NativeImageDumper@@QEAAXV?$__DPtr@VMethodTable@@@@AEAVSString@@@Z; NativeImageDumper::MethodTableToString(__DPtr<MethodTable>,SString &)
0x18005bd37  test    [r13+198h], r15d
0x18005bd3e  jz      short loc_18005BD6E
0x18005bd40  lea     rcx, [rsp+140h+var_E0]; this
0x18005bd45  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18005bd4a  mov     rcx, [r13+88h]
0x18005bd51  mov     rax, [rcx]
0x18005bd54  mov     r8, [rsp+140h+lpMem]
0x18005bd59  lea     rdx, aName_0; "Name"
0x18005bd60  mov     rax, [rax+0D8h]
0x18005bd67  call    cs:__guard_dispatch_icall_fptr
0x18005bd6d  nop
0x18005bd6e  test    [rsp+140h+var_D8], 8
0x18005bd73  jz      short loc_18005BDA6
0x18005bd75  mov     rsi, [rsp+140h+lpMem]
0x18005bd7a  test    rsi, rsi
0x18005bd7d  jz      short loc_18005BDA6
0x18005bd7f  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18005bd86  test    rax, rax
0x18005bd89  jnz     short loc_18005BD98
0x18005bd8b  call    cs:__imp_GetProcessHeap
0x18005bd91  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18005bd98  mov     r8, rsi; lpMem
0x18005bd9b  xor     edx, edx; dwFlags
0x18005bd9d  mov     rcx, rax; hHeap
0x18005bda0  call    cs:__imp_HeapFree
0x18005bda6  mov     r9b, 1; bool
0x18005bda9  mov     r8b, r9b; bool
0x18005bdac  mov     edx, 48h ; 'H'; unsigned int
0x18005bdb1  mov     rcx, rdi; unsigned __int64
0x18005bdb4  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005bdb9  mov     rsi, [rax]
0x18005bdbc  mov     eax, [r13+198h]
0x18005bdc3  and     eax, r15d
0x18005bdc6  test    rsi, rsi
0x18005bdc9  jz      loc_18005BF59
0x18005bdcf  mov     r14d, 14h
0x18005bdd5  test    eax, eax
0x18005bdd7  jz      short loc_18005BE16
0x18005bdd9  mov     rdx, rsi; unsigned __int64
0x18005bddc  mov     rcx, r13; this
0x18005bddf  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z; NativeImageDumper::DataPtrToDisplay(unsigned __int64)
0x18005bde4  mov     rcx, [r13+88h]
0x18005bdeb  mov     rdx, [rcx]
0x18005bdee  mov     r10, [rdx+198h]
0x18005bdf5  mov     [rsp+140h+var_118], r14
0x18005bdfa  mov     [rsp+140h+var_120], rax
0x18005bdff  lea     r9d, [r14-0Ch]
0x18005be03  xor     r8d, r8d
0x18005be06  lea     rdx, aMPguidinfo; "m_pGuidInfo"
0x18005be0d  mov     rax, r10
0x18005be10  call    cs:__guard_dispatch_icall_fptr
0x18005be16  mov     [rsp+140h+var_E0], rbx
0x18005be1b  mov     [rsp+140h+var_E0+4], 80h
0x18005be24  mov     [rsp+140h+lpMem], rbx
0x18005be29  lea     rax, [rsp+140h+var_C8]
0x18005be2e  mov     [rsp+140h+lpMem], rax
0x18005be33  mov     dword ptr [rsp+140h+var_E0], 2
0x18005be3b  mov     rax, [rsp+140h+lpMem]
0x18005be40  mov     [rax], bx
0x18005be43  mov     r9b, 1; bool
0x18005be46  mov     r8b, r9b; bool
0x18005be49  mov     edx, r14d; unsigned int
0x18005be4c  mov     rcx, rsi; unsigned __int64
0x18005be4f  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005be54  mov     rcx, rax; struct _GUID *
0x18005be57  lea     rdx, [rsp+140h+var_E0]; struct SString *
0x18005be5c  call    ?GuidToString@@YAXAEAU_GUID@@AEAVSString@@@Z; GuidToString(_GUID &,SString &)
0x18005be61  mov     eax, [r13+198h]
0x18005be68  test    r15d, eax
0x18005be6b  jz      loc_18005BF1F
0x18005be71  lea     rcx, [rsp+140h+var_E0]; this
0x18005be76  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18005be7b  mov     rcx, [r13+88h]
0x18005be82  mov     rax, [rcx]
0x18005be85  mov     rdx, [rsp+140h+lpMem]
0x18005be8a  mov     [rsp+140h+var_120], rdx
0x18005be8f  mov     r9d, 10h
0x18005be95  xor     r8d, r8d
0x18005be98  lea     rdx, aMGuid; "m_Guid"
0x18005be9f  mov     rax, [rax+138h]
0x18005bea6  call    cs:__guard_dispatch_icall_fptr
0x18005beac  mov     eax, [r13+198h]
0x18005beb3  test    r15d, eax
0x18005beb6  jz      short loc_18005BF1F
0x18005beb8  mov     r9b, 1; bool
0x18005bebb  mov     r8b, r9b; bool
0x18005bebe  mov     edx, r14d; unsigned int
0x18005bec1  mov     rcx, rsi; unsigned __int64
0x18005bec4  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005bec9  mov     rcx, [r13+88h]
0x18005bed0  mov     rdx, [rcx]
0x18005bed3  mov     r10, [rdx+170h]
0x18005beda  mov     edx, [rax+10h]
0x18005bedd  mov     dword ptr [rsp+140h+var_120], edx
0x18005bee1  mov     r9d, 4
0x18005bee7  lea     r8d, [r9+0Ch]
0x18005beeb  lea     rdx, aMBgeneratedfro; "m_bGeneratedFromName"
0x18005bef2  mov     rax, r10
0x18005bef5  call    cs:__guard_dispatch_icall_fptr
0x18005befb  mov     eax, [r13+198h]
0x18005bf02  test    r15d, eax
0x18005bf05  jz      short loc_18005BF1F
0x18005bf07  mov     rcx, [r13+88h]
0x18005bf0e  mov     rax, [rcx]
0x18005bf11  mov     rax, [rax+1A0h]
0x18005bf18  call    cs:__guard_dispatch_icall_fptr
0x18005bf1e  nop
0x18005bf1f  test    [rsp+140h+var_D8], 8
0x18005bf24  jz      short loc_18005BF89
0x18005bf26  mov     rsi, [rsp+140h+lpMem]
0x18005bf2b  test    rsi, rsi
0x18005bf2e  jz      short loc_18005BF89
0x18005bf30  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18005bf37  test    rax, rax
0x18005bf3a  jnz     short loc_18005BF49
0x18005bf3c  call    cs:__imp_GetProcessHeap
0x18005bf42  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18005bf49  mov     r8, rsi; lpMem
0x18005bf4c  xor     edx, edx; dwFlags
0x18005bf4e  mov     rcx, rax; hHeap
0x18005bf51  call    cs:__imp_HeapFree
0x18005bf57  jmp     short loc_18005BF89
0x18005bf59  test    eax, eax
0x18005bf5b  jz      short loc_18005BF89
0x18005bf5d  mov     rcx, [r13+88h]
0x18005bf64  mov     rax, [rcx]
0x18005bf67  mov     [rsp+140h+var_120], rbx
0x18005bf6c  mov     r9d, 8
0x18005bf72  xor     r8d, r8d
0x18005bf75  lea     rdx, aMPguidinfo; "m_pGuidInfo"
0x18005bf7c  mov     rax, [rax+140h]
0x18005bf83  call    cs:__guard_dispatch_icall_fptr
0x18005bf89  mov     eax, [r13+198h]
0x18005bf90  test    r15d, eax
0x18005bf93  jz      short loc_18005C010
0x18005bf95  mov     r9b, 1; bool
0x18005bf98  mov     r8b, r9b; bool
0x18005bf9b  mov     edx, 48h ; 'H'; unsigned int
0x18005bfa0  mov     rcx, rdi; unsigned __int64
0x18005bfa3  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005bfa8  mov     rcx, [rax+10h]
0x18005bfac  mov     [rsp+140h+var_F8], rcx
0x18005bfb1  lea     rax, [rsp+140h+var_F8]
0x18005bfb6  mov     [rsp+140h+var_120], rax; __int64
0x18005bfbb  mov     r8d, 10h
0x18005bfc1  lea     rdx, aMPmethodtable; "m_pMethodTable"
0x18005bfc8  mov     rcx, r13; this
0x18005bfcb  call    ?DoWriteFieldMethodTable@NativeImageDumper@@QEAAXPEBDIIV?$__DPtr@VMethodTable@@@@@Z; NativeImageDumper::DoWriteFieldMethodTable(char const *,uint,uint,__DPtr<MethodTable>)
0x18005bfd0  mov     eax, [r13+198h]
0x18005bfd7  test    r15d, eax
0x18005bfda  jz      short loc_18005C010
0x18005bfdc  mov     r9b, 1; bool
0x18005bfdf  mov     r8b, r9b; bool
0x18005bfe2  mov     edx, 48h ; 'H'; unsigned int
0x18005bfe7  mov     rcx, rdi; unsigned __int64
0x18005bfea  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005bfef  movzx   ecx, byte ptr [rax+40h]
0x18005bff3  mov     dword ptr [rsp+140h+var_120], ecx
0x18005bff7  mov     r9d, 1
0x18005bffd  lea     r8d, [r9+3Fh]
0x18005c001  lea     rdx, aMNormtype; "m_NormType"
0x18005c008  mov     rcx, r13
0x18005c00b  call    ?DoWriteFieldCorElementType@NativeImageDumper@@QEAAXPEBDIIW4CorElementType@@@Z; NativeImageDumper::DoWriteFieldCorElementType(char const *,uint,uint,CorElementType)
0x18005c010  mov     r9b, 1; bool
  ... truncated ...
```
