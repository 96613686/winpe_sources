# NativeImageDumper::DumpMethodDesc(__DPtr<MethodDesc>,__VPtr<Module>)

- ea: `0x1800599a4`
- end: `0x18005bb29`
- name: `?DumpMethodDesc@NativeImageDumper@@QEAAXV?$__DPtr@VMethodDesc@@@@V?$__VPtr@VModule@@@@@Z`
- size: `8581`
- prototype: `__int64 __fastcall(NativeImageDumper *this)`
- caller_count: `3`
- callee_count: `33`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180050b3c`
- `0x180050ca8`
- `0x18005bb2c`

## callees

- `0x18000b980`
- `0x18001df18`
- `0x18001e010`
- `0x1800210f0`
- `0x180022068`
- `0x18004240c`
- `0x180042724`
- `0x180054364`
- `0x180054434`
- `0x18005495c`
- `0x180054a1c`
- `0x180054c84`
- `0x180054e3c`
- `0x1800552bc`
- `0x18005541c`
- `0x1800592c8`
- `0x1800599a4`
- `0x1800628f8`
- `0x18006421c`
- `0x1800672f8`
- `0x180072664`
- `0x18007344c`
- `0x1800774f4`
- `0x18007838c`
- `0x180089fd4`
- `0x18008a3fc`
- `0x18008a4ec`
- `0x18008ab4c`
- `0x18008ad10`
- `0x18008ae70`
- `0x18009e948`
- `0x1800f0d20`
- `0x180106100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180059b2e`
- `KERNEL32!HeapFree` at `0x180059dab`
- `KERNEL32!HeapFree` at `0x180059f0f`
- `KERNEL32!HeapFree` at `0x18005a95e`
- `KERNEL32!HeapFree` at `0x180059b2e`
- `KERNEL32!HeapFree` at `0x180059dab`
- `KERNEL32!HeapFree` at `0x180059f0f`
- `KERNEL32!HeapFree` at `0x18005a95e`
- `KERNEL32!GetProcessHeap` at `0x180059b19`
- `KERNEL32!GetProcessHeap` at `0x180059d96`
- `KERNEL32!GetProcessHeap` at `0x180059efa`
- `KERNEL32!GetProcessHeap` at `0x18005a949`
- `KERNEL32!GetProcessHeap` at `0x180059b19`
- `KERNEL32!GetProcessHeap` at `0x180059d96`
- `KERNEL32!GetProcessHeap` at `0x180059efa`
- `KERNEL32!GetProcessHeap` at `0x18005a949`

## string_xrefs

- `0x18005af1d`: `m_pWriteableData`
- `0x18005b245`: `ComPlusCallMethodDesc`
- `0x180059b7c`: `m_wFlags3AndTokenRemainder`
- `0x18005b299`: `m_pComPlusCallInfo`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall NativeImageDumper::DumpMethodDesc(NativeImageDumper *this, unsigned __int64 *a2)
{
  unsigned __int64 *v2; // r12
  __int64 v4; // r15
  char *v5; // rbx
  MethodDesc *v6; // rax
  unsigned __int64 v7; // rdi
  int v8; // ecx
  unsigned __int64 v9; // rax
  void *v10; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v12; // rax
  unsigned __int8 *v13; // rbx
  __int64 v14; // rdx
  __int64 TargetAddrForHostAddr; // rax
  void *v16; // rax
  __int64 v17; // rdx
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rbx
  __int64 v20; // rdi
  unsigned __int64 v21; // rax
  unsigned __int8 *v22; // rax
  void *v23; // rbx
  HANDLE v24; // rax
  unsigned __int16 *v25; // rax
  LPVOID v26; // rbx
  unsigned __int16 *v27; // rax
  void *v28; // rbx
  HANDLE v29; // rax
  __int16 v30; // cx
  unsigned __int8 *v31; // rbx
  __int64 v32; // rdx
  __int64 v33; // rax
  void *v34; // rax
  __int64 v35; // rdx
  unsigned __int64 v36; // rax
  _QWORD *v37; // rbx
  __int64 v38; // rdx
  __int64 v39; // rdx
  MethodDesc *v40; // rax
  unsigned __int8 *v41; // rbx
  __int64 v42; // rdx
  __int64 v43; // rax
  _WORD *v44; // rax
  unsigned int v45; // ebx
  unsigned int v46; // eax
  struct _IMAGE_SECTION_HEADER *v47; // rax
  unsigned __int64 v48; // r14
  int v49; // r11d
  void (__fastcall **v50)(_QWORD, const char *, unsigned __int64, unsigned __int64); // rdi
  unsigned __int64 v51; // rbx
  unsigned __int64 v52; // rax
  MethodDesc *v53; // rax
  unsigned __int64 MethodEntryPoint; // rax
  int v55; // edx
  struct Precode *PrecodeFromEntryPoint; // rax
  __int64 v57; // rdx
  _WORD *v58; // rax
  __int64 v59; // rdx
  __int16 v60; // di
  const unsigned __int64 near *v61; // rbx
  unsigned int v62; // eax
  unsigned __int16 v63; // bx
  unsigned __int64 *MethodTable; // rax
  void *v65; // rax
  unsigned __int16 v66; // cx
  _WORD *v67; // rax
  const unsigned __int64 near *v68; // rbx
  __int64 v69; // rdx
  int v70; // eax
  MethodDesc *v71; // rax
  struct MethodImpl *MethodImpl; // rax
  __int64 v73; // rdx
  unsigned __int64 v74; // rdi
  unsigned __int64 v75; // rbx
  unsigned __int64 v76; // rcx
  unsigned int v77; // edx
  unsigned __int64 v78; // rcx
  __int64 v79; // r14
  unsigned __int64 v80; // rax
  __int64 v81; // r14
  unsigned __int64 v82; // rax
  unsigned __int64 v83; // rdx
  unsigned __int64 v84; // rcx
  _QWORD *v85; // rax
  __int64 v86; // rdi
  __int64 v87; // rbx
  unsigned __int64 v88; // rax
  _QWORD *v89; // rax
  __int64 v90; // rbx
  unsigned __int64 v91; // rax
  unsigned __int64 v92; // rbx
  unsigned __int64 v93; // rdx
  unsigned __int64 v94; // rcx
  bool v95; // cf
  char v96; // cl
  int v97; // eax
  unsigned int *v98; // rdi
  _QWORD *v99; // rax
  __int64 v100; // r14
  __int64 v101; // rdi
  unsigned __int64 v102; // rax
  _QWORD *v103; // rax
  __int64 v104; // rdi
  unsigned __int64 v105; // rax
  int v106; // eax
  _DWORD *v107; // rdi
  _QWORD *v108; // rax
  _DWORD *v109; // rax
  void *v110; // rbx
  HANDLE v111; // rax
  unsigned __int64 v112; // rdi
  int v113; // eax
  unsigned __int64 v114; // rbx
  unsigned __int64 v115; // rcx
  _QWORD *v116; // rax
  unsigned __int64 v117; // rbx
  _DWORD *v118; // rax
  unsigned __int64 v119; // rbx
  void *v120; // rax
  __int64 v121; // rdx
  unsigned __int64 v122; // rbx
  unsigned __int64 v123; // rax
  unsigned __int64 *v124; // rax
  __int64 v125; // rdi
  unsigned __int64 v126; // rax
  unsigned __int16 *v127; // rax
  LPVOID v128; // rdi
  unsigned __int16 *v129; // rax
  unsigned __int64 v130; // rdi
  unsigned __int64 v131; // rcx
  _BYTE *v132; // rax
  __int64 v133; // rdx
  unsigned __int64 v134; // rax
  _WORD *v135; // rax
  int v136; // ecx
  int v137; // eax
  unsigned __int64 v138; // rdi
  unsigned __int64 v139; // rcx
  unsigned __int64 v140; // rdi
  int v141; // eax
  unsigned __int64 v142; // rax
  unsigned __int64 *v143; // rax
  __int64 v144; // r14
  unsigned __int64 v145; // rax
  unsigned __int64 v146; // rdi
  int v147; // ecx
  int v148; // eax
  void *v149; // rdi
  _QWORD *v150; // rbx
  __int64 v151; // rdx
  unsigned __int64 v152; // rax
  int v153; // eax
  bool v154; // zf
  unsigned __int64 v155; // rbx
  __int64 v156; // rax
  int v157; // ecx
  void (*v158)(void); // rax
  unsigned __int64 v159; // rbx
  int v160; // esi
  unsigned __int64 v161; // rdi
  unsigned int v162; // r15d
  unsigned __int64 v163; // rdi
  unsigned __int64 v164; // rsi
  MethodDesc *v165; // rax
  unsigned __int16 *v166; // rax
  unsigned __int64 v167; // rdi
  MethodDesc *v168; // rax
  __int64 v169; // rcx
  MethodDesc *v170; // rax
  unsigned int NumGenericMethodArgs; // eax
  int v172; // eax
  int v173; // ecx
  unsigned int v174; // esi
  void *v175; // rax
  __int64 v176; // rdx
  __int64 v177; // rdx
  __int64 v178; // rsi
  unsigned __int64 v179; // rdx
  unsigned __int16 *v180; // rax
  __int64 v181; // rdx
  _WORD *v182; // rdi
  const unsigned __int64 near *v183; // rbx
  __int64 v184; // rax
  __int64 v185; // rax
  __int64 result; // rax
  __int64 v187; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v188[2]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 *v189; // [rsp+70h] [rbp-90h]
  unsigned int v190[2]; // [rsp+78h] [rbp-88h]
  _BYTE v191[16]; // [rsp+80h] [rbp-80h] BYREF
  int v192; // [rsp+90h] [rbp-70h] BYREF
  __int64 v193; // [rsp+94h] [rbp-6Ch]
  LPVOID lpMem; // [rsp+A0h] [rbp-60h]
  _WORD v195[68]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v196[4]; // [rsp+130h] [rbp+30h] BYREF
  unsigned int v197; // [rsp+134h] [rbp+34h]

  v2 = a2;
  v189 = a2;
  v4 = *((_WORD *)DacInstantiateTypeByAddressHelper(*a2, 8u, 1, 1) + 3) & 7;
  v187 = v4;
  v5 = off_18012EBE0[v4];
  v6 = (MethodDesc *)DacInstantiateTypeByAddressHelper(*v2, 8u, 1, 1);
  v7 = MethodDesc::SizeOf(v6);
  *(_QWORD *)v190 = v7;
  v8 = *((_DWORD *)this + 102);
  if ( (v8 & 0x80000) != 0 )
  {
    v9 = NativeImageDumper::DataPtrToDisplay(this, *v2);
    (*(void (__fastcall **)(_QWORD, char *, unsigned __int64, _QWORD))(**((_QWORD **)this + 17) + 392LL))(
      *((_QWORD *)this + 17),
      v5,
      v9,
      (unsigned int)v7);
    v8 = *((_DWORD *)this + 102);
  }
  if ( (v8 & 0x80000) != 0 )
  {
    v193 = 128;
    lpMem = v195;
    v192 = 2;
    v195[0] = 0;
    *(_QWORD *)v188 = *v2;
    NativeImageDumper::MethodDescToString(this);
    if ( (*((_DWORD *)this + 102) & 0x80000) != 0 )
    {
      SString::ConvertToUnicode((SString *)&v192);
      (*(void (__fastcall **)(_QWORD, const char *, LPVOID))(**((_QWORD **)this + 17) + 216LL))(
        *((_QWORD *)this + 17),
        "Name",
        lpMem);
    }
    if ( (v193 & 0x800000000LL) != 0 )
    {
      v10 = lpMem;
      if ( lpMem )
      {
        ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          ProcessHeap = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
        }
        HeapFree(ProcessHeap, 0, v10);
      }
    }
  }
  if ( (*((_DWORD *)this + 102) & 0x80000) != 0 )
  {
    v12 = (unsigned __int16 *)DacInstantiateTypeByAddressHelper(*v2, 8u, 1, 1);
    (*(void (__fastcall **)(_QWORD, const char *, _QWORD, __int64, _DWORD))(**((_QWORD **)this + 17) + 336LL))(
      *((_QWORD *)this + 17),
      "m_wFlags3AndTokenRemainder",
      0,
      2,
      *v12);
    if ( (*((_DWORD *)this + 102) & 0x80000) != 0 )
    {
      DacInstantiateTypeByAddressHelper(*v2, 8u, 1, 1);
      (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 336LL))(
        *((_QWORD *)this + 17),
        "m_chunkIndex",
        2);
    }
  }
  if ( (_DWORD)v4 == 5 && !*((_BYTE *)DacInstantiateTypeByAddressHelper(*v2, 8u, 1, 1) + 2) )
  {
    v13 = (unsigned __int8 *)DacInstantiateTypeByAddressHelper(*v2, 8u, 1, 1);
    LOBYTE(v14) = 1;
    TargetAddrForHostAddr = DacGetTargetAddrForHostAddr(v13, v14);
    v16 = DacInstantiateTypeByAddressHelper(TargetAddrForHostAddr - 8LL * v13[2] - 24, 0x18u, 1, 1);
    LOBYTE(v17) = 1;
    v18 = DacGetTargetAddrForHostAddr(v16, v17);
    v19 = v18;
    if ( (*((_DWORD *)this + 102) & 0x80000) == 0 )
      goto LABEL_24;
    v20 = 8LL * *((unsigned __int8 *)DacInstantiateTypeByAddressHelper(v18, 0x18u, 1, 1) + 16) + 32;
    v21 = NativeImageDumper::DataPtrToDisplay(this, v19);
    (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, __int64))(**((_QWORD **)this + 17) + 184LL))(
      *((_QWORD *)this + 17),
      "MethodDescChunk",
      v21,
      v20);
  }
  if ( (*((_DWORD *)this + 102) & 0x80000) != 0 )
  {
    v193 = 128;
    lpMem = v195;
    v192 = 2;
    v195[0] = 0;
    v22 = (unsigned __int8 *)DacInstantiateTypeByAddressHelper(*v2, 8u, 1, 1);
    EnumFlagsToString(
      v22[3],
      (const struct NativeImageDumper::EnumMnemonics *)&NativeImageDumper::s_MDFlag2,
      9,
      L", ",
      (struct SString *)&v192);
    SString::ConvertToUnicode((SString *)&v192);
    DacInstantiateTypeByAddressHelper(*v2, 8u, 1, 1);
    (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 352LL))(
      *((_QWORD *)this + 17),
      "m_bFlags2",
      3);
    if ( (v193 & 0x800000000LL) != 0 )
    {
      v23 = lpMem;
      if ( lpMem )
      {
        v24 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          v24 = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = v24;
        }
        HeapFree(v24, 0, v23);
      }
    }
  }
LABEL_24:
  if ( (*((_DWORD *)this + 102) & 0x80000) != 0 )
  {
    DacInstantiateTypeByAddressHelper(*v2, 8u, 1, 1);
    (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 336LL))(
      *((_QWORD *)this + 17),
      "m_wSlotNumber",
      4);
    if ( (*((_DWORD *)this + 102) & 0x80000) != 0 )
    {
      v193 = 128;
      lpMem = v195;
      v192 = 2;
      v195[0] = 0;
      v25 = (unsigned __int16 *)DacInstantiateTypeByAddressHelper(*v2, 8u, 1, 1);
      EnumFlagsToString(
        v25[3],
        (const struct NativeImageDumper::EnumMnemonics *)&NativeImageDumper::s_MDC,
        21,
        L", ",
        (struct SString *)&v192);
      SString::ConvertToUnicode((SString *)&v192);
      v26 = lpMem;
      v27 = (unsigned __int16 *)DacInstantiateTypeByAddressHelper(*v2, 8u, 1, 1);
      (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD, LPVOID))(**((_QWORD **)this + 17) + 352LL))(
        *((_QWORD *)this + 17),
        "m_wFlags",
        6,
        2,
        v27[3],
        v26);
      if ( (v193 & 0x800000000LL) != 0 )
      {
        v28 = lpMem;
        if ( lpMem )
        {
          v29 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
          if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
          {
            v29 = GetProcessHeap();
            `ClrFreeInProcessHeap'::`2'::ProcessHeap = v29;
          }
          HeapFree(v29, 0, v28);
        }
      }
    }
  }
  if ( *((char *)this + 408) < 0 )
  {
    v30 = *((_WORD *)DacInstantiateTypeByAddressHelper(*v2, 8u, 1, 1) + 3) & 7;
    if ( !v30 || v30 == 5 )
    {
      v31 = (unsigned __int8 *)DacInstantiateTypeByAddressHelper(*v2, 8u, 1, 1);
      LOBYTE(v32) = 1;
      v33 = DacGetTargetAddrForHostAddr(v31, v32);
      v34 = DacInstantiateTypeByAddressHelper(v33 - 8LL * v31[2] - 24, 0x18u, 1, 1);
      LOBYTE(v35) = 1;
      v36 = DacGetTargetAddrForHostAddr(v34, v35);
      v37 = DacInstantiateTypeByAddressHelper(v36, 0x18u, 1, 1);
      LOBYTE(v38) = 1;
      v39 = DacGetTargetAddrForHostAddr(v37, v38) + *v37;
      if ( (v39 & 1) == 0 || (*(_QWORD *)DacInstantiateTypeByAddressHelper(v39 - 1, 8u, 1, 1) & 1) == 0 )
      {
        v40 = (MethodDesc *)DacInstantiateTypeByAddressHelper(*v2, 8u, 1, 1);
        if ( (unsigned int)MethodDesc::IsTypicalMethodDefinition(v40) )
        {
          v188[0] = 0;
          v41 = (unsigned __int8 *)DacInstantiateTypeByAddressHelper(*v2, 8u, 1, 1);
          LOBYTE(v42) = 1;
          v43 = DacGetTargetAddrForHostAddr(v41, v42);
          v44 = DacInstantiateTypeByAddressHelper(v43 - 8LL * v41[2] - 24, 0x18u, 1, 1);
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int *, _QWORD))(**((_QWORD **)this + 29) + 240LL))(
            *((_QWORD *)this + 29),
            *(_WORD *)v41 & 0x3FFF | ((v44[9] & 0x3FF | 0x1800u) << 14),
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            v188,
            0);
          v45 = v188[0];
          if ( v188[0] )
          {
            if ( (*((_BYTE *)this + 76) & 1) != 0 )
            {
              v46 = v188[0];
            }
            else
            {
              v47 = PEDecoder::RvaToSection((NativeImageDumper *)((char *)this + 64), v188[0]);
              if ( v47 )
                v46 = v45 + v47->PointerToRawData - v47->VirtualAddress;
              else
                v46 = v45;
              v45 = v188[0];
            }
            v48 = *((_QWORD *)this + 8) + v46;
            COR_ILMETHOD_DECODER::COR_ILMETHOD_DECODER(
              (COR_ILMETHOD_DECODER *)v196,
              (const struct COR_ILMETHOD *)(v45 + *((_QWORD *)this + 67) - *((unsigned int *)this + 133)));
            v49 = *((_DWORD *)this + 102);
            if ( v49 )
            {
              v50 = (void (__fastcall **)(_QWORD, const char *, unsigned __int64, unsigned __int64))(**((_QWORD **)this + 17) + 392LL);
              v51 = PEDecoder::ComputeILMethodSize(v48);
              v52 = NativeImageDumper::DataPtrToDisplay(this, v48);
              (*v50)(*((_QWORD *)this + 17), "IL", v52, v51);
              v49 = *((_DWORD *)this + 102);
            }
            if ( v49 )
            {
              (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 224LL))(
                *((_QWORD *)this + 17),
                "CodeSize",
                v197);
              if ( *((_DWORD *)this + 102) )
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
            }
          }
        }
      }
    }
  }
  if ( (*((_BYTE *)DacInstantiateTypeByAddressHelper(*v2, 8u, 1, 1) + 3) & 2) != 0 )
  {
    v53 = (MethodDesc *)DacInstantiateTypeByAddressHelper(*v2, 8u, 1, 1);
    MethodEntryPoint = MethodDesc::GetMethodEntryPoint(v53);
    PrecodeFromEntryPoint = Precode::GetPrecodeFromEntryPoint(MethodEntryPoint, v55);
    LOBYTE(v57) = 1;
    *(_QWORD *)v188 = DacGetTargetAddrForHostAddr(PrecodeFromEntryPoint, v57);
    NativeImageDumper::DumpPrecode(this);
  }
  if ( (*((_BYTE *)DacInstantiateTypeByAddressHelper(*v2, 8u, 1, 1) + 6) & 8) != 0 && *((_DWORD *)this + 102) )
  {
    v58 = DacInstantiateTypeByAddressHelper(*v2, 8u, 1, 1);
    v60 = v58[3];
    if ( (v60 & 8) != 0 )
    {
      v61 = (&MethodDesc::s_ClassificationSizeTable)[v60 & 7];
      LOBYTE(v59) = 1;
      v62 = (_DWORD)v61 + DacGetTargetAddrForHostAddr(v58, v59);
    }
    else
    {
      v63 = v58[2];
      MethodTable = (unsigned __int64 *)MethodDesc::GetMethodTable(v58, v191);
      v65 = DacInstantiateTypeByAddressHelper(*MethodTable, 0x40u, 1, 1);
      v66 = v63 & 0x3FF;
      if ( v60 < 0 )
        v66 = v63;
      MethodTable::GetSlotPtrRaw(v65, v188, v66);
      v62 = v188[0];
    }
    (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 224LL))(
      *((_QWORD *)this + 17),
      "Slot",
      v62 - *(_DWORD *)v2);
  }
  if ( (*((_BYTE *)DacInstantiateTypeByAddressHelper(*v2, 8u, 1, 1) + 3) & 8) != 0 && *((_DWORD *)this + 102) )
  {
    v67 = DacInstantiateTypeByAddressHelper(*v2, 8u, 1, 1);
    v68 = (&MethodDesc::s_ClassificationSizeTable)[v67[3] & 0x1F];
    LOBYTE(v69) = 1;
    v70 = DacGetTargetAddrForHostAddr(v67, v69);
    (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 224LL))(
      *((_QWORD *)this + 17),
      "NativeCode",
      (unsigned int)(v70 + (_DWORD)v68 - *(_DWORD *)v2));
  }
  if ( (*((_BYTE *)DacInstantiateTypeByAddressHelper(*v2, 8u, 1, 1) + 6) & 0x10) != 0 )
  {
    if ( (*((_DWORD *)this + 102) & 0x80000) != 0 )
      (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 104LL))(
        *((_QWORD *)this + 17),
        "MethodImpl");
    v71 = (MethodDesc *)DacInstantiateTypeByAddressHelper(*v2, 8u, 1, 1);
    MethodImpl = MethodDesc::GetMethodImpl(v71);
    LOBYTE(v73) = 1;
    v74 = DacGetTargetAddrForHostAddr(MethodImpl, v73);
    v75 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v74, 0x10u, 1, 1);
    if ( !v75 )
      v75 = -4;
    v76 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v74, 0x10u, 1, 1);
    if ( v76 )
      v77 = *(_DWORD *)DacInstantiateTypeByAddressHelper(v76, 4u, 1, 1);
    else
      v77 = 0;
    v188[0] = v77;
    v78 = *((_QWORD *)this + 15);
    if ( v78 > v75 || v75 >= *((_QWORD *)this + 16) + v78 )
    {
      if ( (*((_DWORD *)this + 102) & 0x80000) != 0 )
      {
        v81 = **((_QWORD **)this + 17);
        v82 = NativeImageDumper::DataPtrToDisplay(this, v75);
        (*(void (__fastcall **)(_QWORD, const char *, _QWORD, __int64, unsigned __int64))(v81 + 320))(
          *((_QWORD *)this + 17),
          "pdwSlots",
          0,
          8,
          v82);
      }
    }
    else if ( (*((_DWORD *)this + 102) & 0x80000) != 0 )
    {
      v4 = **((_QWORD **)this + 17);
      v79 = 4LL * (v77 + 1);
      v80 = NativeImageDumper::DataPtrToDisplay(this, v75);
      (*(void (__fastcall **)(_QWORD, const char *, _QWORD, __int64, unsigned __int64, __int64))(v4 + 384))(
        *((_QWORD *)this + 17),
        "pdwSlots",
        0,
        8,
        v80,
        v79);
      LODWORD(v4) = v187;
    }
    if ( *((_QWORD *)DacInstantiateTypeByAddressHelper(v74, 0x10u, 1, 1) + 1)
      && (v83 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v74, 0x10u, 1, 1) + 1),
          v84 = *((_QWORD *)this + 15),
          v84 <= v83)
      && v83 < *((_QWORD *)this + 16) + v84 )
    {
      if ( (*((_DWORD *)this + 102) & 0x80000) != 0 )
      {
        v85 = DacInstantiateTypeByAddressHelper(v74, 0x10u, 1, 1);
        v86 = **((_QWORD **)this + 17);
        v87 = 8LL * v188[0];
        v88 = NativeImageDumper::DataPtrToDisplay(this, v85[1]);
        (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, __int64))(v86 + 384))(
          *((_QWORD *)this + 17),
          "pImplementedMD",
          8,
          8,
          v88,
          v87);
      }
    }
    else if ( (*((_DWORD *)this + 102) & 0x80000) != 0 )
    {
      v89 = DacInstantiateTypeByAddressHelper(v74, 0x10u, 1, 1);
      v90 = **((_QWORD **)this + 17);
      v91 = NativeImageDumper::DataPtrToDisplay(this, v89[1]);
      (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64))(v90 + 320))(
        *((_QWORD *)this + 17),
        "pImplementedMD",
        8,
        8,
        v91);
    }
    if ( (*((_DWORD *)this + 102) & 0x80000) != 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 120LL))(*((_QWORD *)this + 17));
  }
  if ( (((*((_WORD *)DacInstantiateTypeByAddressHelper(*v2, 8u, 1, 1) + 3) & 7) - 3) & 0xFFFA) == 0 )
  {
    if ( (*((_DWORD *)this + 102) & 0x80000) != 0 )
      (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 104LL))(
        *((_QWORD *)this + 17),
        "StoredSigMethodDesc");
    v92 = *v2;
    v93 = *((_QWORD *)DacInstantiateTypeByAddressHelper(*v2, 0x18u, 1, 1) + 1);
    v94 = *((_QWORD *)this + 15);
    if ( v94 > v93 || (v95 = v93 < *((_QWORD *)this + 16) + v94, v96 = 1, !v95) )
      v96 = 0;
    v97 = *((_DWORD *)this + 102) & 0x80000;
    if ( v96 )
    {
      if ( v97 )
      {
        v98 = (unsigned int *)DacInstantiateTypeByAddressHelper(v92, 0x18u, 1, 1);
        v99 = DacInstantiateTypeByAddressHelper(v92, 0x18u, 1, 1);
        v100 = **((_QWORD **)this + 17);
        v101 = v98[4];
        v102 = NativeImageDumper::DataPtrToDisplay(this, v99[1]);
        (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, __int64))(v100 + 384))(
          *((_QWORD *)this + 17),
          "m_pSig",
          8,
          8,
          v102,
          v101);
      }
    }
    else if ( v97 )
    {
      v103 = DacInstantiateTypeByAddressHelper(v92, 0x18u, 1, 1);
      v104 = **((_QWORD **)this + 17);
      v105 = NativeImageDumper::DataPtrToDisplay(this, v103[1]);
      (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64))(v104 + 320))(
        *((_QWORD *)this + 17),
        "m_pSig",
        8,
        8,
        v105);
    }
    v106 = *((_DWORD *)this + 102);
    if ( v106 < 0 )
    {
      v107 = DacInstantiateTypeByAddressHelper(v92, 0x18u, 1, 1);
      v108 = DacInstantiateTypeByAddressHelper(v92, 0x18u, 1, 1);
      DacInstantiateTypeByAddressHelper(v108[1], v107[4], 1, 1);
      v106 = *((_DWORD *)this + 102);
    }
    if ( (v106 & 0x80000) != 0 )
    {
      DacInstantiateTypeByAddressHelper(v92, 0x18u, 1, 1);
      (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 336LL))(
        *((_QWORD *)this + 17),
        "m_cSig",
        16);
      if ( (*((_DWORD *)this + 102) & 0x80000) != 0 )
      {
        v192 = 2;
        v193 = 128;
        lpMem = v195;
        v195[0] = 0;
        v109 = DacInstantiateTypeByAddressHelper(v92, 0x18u, 1, 1);
        EnumFlagsToString(
          v109[5],
          (const struct NativeImageDumper::EnumMnemonics *)&NativeImageDumper::s_SSMDExtendedFlags,
          23,
          L", ",
          (struct SString *)&v192);
        SString::ConvertToUnicode((SString *)&v192);
        DacInstantiateTypeByAddressHelper(v92, 0x18u, 1, 1);
        (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 352LL))(
          *((_QWORD *)this + 17),
          "m_dwExtendedFlags",
          20);
        if ( (v193 & 0x800000000LL) != 0 )
        {
          v110 = lpMem;
          if ( lpMem )
          {
            v111 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
            if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
            {
              v111 = GetProcessHeap();
              `ClrFreeInProcessHeap'::`2'::ProcessHeap = v111;
            }
            HeapFree(v111, 0, v110);
          }
        }
      }
    }
    if ( (*((_DWORD *)this + 102) & 0x80000) != 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 120LL))(*((_QWORD *)this + 17));
  }
  switch ( (_DWORD)v4 )
  {
    case 7:
      v112 = *v2;
      v113 = *((_DWORD *)this + 102);
      if ( (v113 & 0x80000) != 0 )
      {
        (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 104LL))(
          *((_QWORD *)this + 17),
          "DynamicMethodDesc");
        v113 = *((_DWORD *)this + 102);
      }
      if ( (v113 & 0x80000) != 0 )
      {
        v187 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v112, 0x28u, 1, 1) + 3);
        NativeImageDumper::DoWriteFieldStr(this);
        v113 = *((_DWORD *)this + 102);
      }
      if ( (v113 & 0x80000) == 0 )
      {
        v114 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v112, 0x28u, 1, 1) + 3);
        do
          v115 = v114++;
        while ( *(_BYTE *)DacInstantiateTypeByAddressHelper(v115, 1u, 1, 1) );
        v113 = *((_DWORD *)this + 102);
      }
      if ( (v113 & 0x80000) != 0 )
      {
        v116 = DacInstantiateTypeByAddressHelper(v112, 0x28u, 1, 1);
        NativeImageDumper::DataPtrToDisplay(this, v116[4]);
        (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 320LL))(
          *((_QWORD *)this + 17),
          "m_pResolver",
          32);
        v113 = *((_DWORD *)this + 102);
      }
      goto LABEL_173;
    case 1:
      v117 = *v2;
      if ( (*((_DWORD *)this + 102) & 0x80000) == 0 )
        goto LABEL_256;
      (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 104LL))(
        *((_QWORD *)this + 17),
        "FCallMethodDesc");
      if ( (*((_DWORD *)this + 102) & 0x80000) == 0 )
        goto LABEL_256;
      v118 = DacInstantiateTypeByAddressHelper(v117, 0x10u, 1, 1);
      (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(**((_QWORD **)this + 17) + 336LL))(
        *((_QWORD *)this + 17),
        "m_dwECallID",
        8,
        4,
        v118[2]);
      goto LABEL_172;
    case 2:
      v119 = *v2;
      if ( (*((_DWORD *)this + 102) & 0x80000) != 0 )
        (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 104LL))(
          *((_QWORD *)this + 17),
          "NDirectMethodDesc");
      v120 = DacInstantiateTypeByAddressHelper(v119, 0x40u, 1, 1);
      LOBYTE(v121) = 1;
      v122 = DacGetTargetAddrForHostAddr(v120, v121) + 8;
      if ( (*((_DWORD *)this + 102) & 0x80000) != 0 )
      {
        v123 = NativeImageDumper::DataPtrToDisplay(this, v122);
        (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, __int64))(**((_QWORD **)this + 17)
                                                                                                  + 408LL))(
          *((_QWORD *)this + 17),
          "ndirect",
          8,
          56,
          v123,
          56);
        if ( (*((_DWORD *)this + 102) & 0x80000) != 0 )
        {
          v124 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper(v122, 0x38u, 1, 1);
          v125 = **((_QWORD **)this + 17);
          v126 = NativeImageDumper::DataPtrToDisplay(this, *v124);
          (*(void (__fastcall **)(_QWORD, const char *, _QWORD, __int64, unsigned __int64))(v125 + 320))(
            *((_QWORD *)this + 17),
            "m_pNativeNDirectTarget",
            0,
            8,
            v126);
          if ( (*((_DWORD *)this + 102) & 0x80000) != 0 )
          {
            v192 = 2;
            v193 = 128;
            lpMem = v195;
            v195[0] = 0;
            v127 = (unsigned __int16 *)DacInstantiateTypeByAddressHelper(v122, 0x38u, 1, 1);
            EnumFlagsToString(
              v127[22],
              (const struct NativeImageDumper::EnumMnemonics *)&qword_180161B70,
              13,
              L", ",
              (struct SString *)&v192);
            SString::ConvertToUnicode((SString *)&v192);
            v128 = lpMem;
            v129 = (unsigned __int16 *)DacInstantiateTypeByAddressHelper(v122, 0x38u, 1, 1);
            (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD, LPVOID))(**((_QWORD **)this + 17)
                                                                                           + 352LL))(
              *((_QWORD *)this + 17),
              "m_wFlags",
              44,
              2,
              v129[22],
              v128);
            if ( (v193 & 0x800000000LL) != 0 )
              operator delete(lpMem);
          }
        }
      }
      if ( (*((_DWORD *)this + 102) & 0x80000) == 0
        || (v187 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v122, 0x38u, 1, 1) + 1),
            NativeImageDumper::DoWriteFieldStr(this),
            (*((_DWORD *)this + 102) & 0x80000) == 0) )
      {
        v130 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v122, 0x38u, 1, 1) + 1);
        do
          v131 = v130++;
        while ( *(_BYTE *)DacInstantiateTypeByAddressHelper(v131, 1u, 1, 1) );
      }
      v132 = DacInstantiateTypeByAddressHelper(*v2, 8u, 1, 1);
      if ( (v132[6] & 7) != 2
        || (LOBYTE(v133) = 1,
            v134 = DacGetTargetAddrForHostAddr(v132, v133),
            v135 = DacInstantiateTypeByAddressHelper(v134, 0x40u, 1, 1),
            v136 = 1,
            (v135[26] & 0x1000) == 0) )
      {
        v136 = 0;
      }
      v137 = *((_DWORD *)this + 102) & 0x80000;
      if ( v136 )
      {
        if ( v137 )
        {
          DacInstantiateTypeByAddressHelper(v122, 0x38u, 1, 1);
          (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 336LL))(
            *((_QWORD *)this + 17),
            "m_dwECallID",
            16);
        }
      }
      else if ( v137 )
      {
        v187 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v122, 0x38u, 1, 1) + 2);
        NativeImageDumper::DoWriteFieldStr(this);
      }
      if ( (*((_DWORD *)this + 102) & 0x80000) == 0 )
      {
        v138 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v122, 0x38u, 1, 1) + 2);
        do
          v139 = v138++;
        while ( *(_BYTE *)DacInstantiateTypeByAddressHelper(v139, 1u, 1, 1) );
      }
      v140 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v122, 0x38u, 1, 1) + 3);
      v141 = *((_DWORD *)this + 102);
      if ( (v141 & 0x80000) != 0 )
      {
        v142 = NativeImageDumper::DataPtrToDisplay(this, v140);
        (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, __int64))(**((_QWORD **)this + 17)
                                                                                                  + 408LL))(
          *((_QWORD *)this + 17),
          "m_pWriteableData",
          24,
          8,
          v142,
          8);
        v141 = *((_DWORD *)this + 102);
        if ( (v141 & 0x80000) != 0 )
        {
          v143 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper(v140, 8u, 1, 1);
          v144 = **((_QWORD **)this + 17);
          v145 = NativeImageDumper::DataPtrToDisplay(this, *v143);
          (*(void (__fastcall **)(_QWORD, const char *, _QWORD, __int64, unsigned __int64))(v144 + 320))(
            *((_QWORD *)this + 17),
            "m_pNDirectTarget",
            0,
            8,
            v145);
          v141 = *((_DWORD *)this + 102);
          if ( (v141 & 0x80000) != 0 )
            goto LABEL_152;
        }
      }
      if ( v141 < 0 )
      {
        DacInstantiateTypeByAddressHelper(v140, 8u, 1, 1);
        v141 = *((_DWORD *)this + 102);
      }
      if ( (v141 & 0x80000) != 0 )
LABEL_152:
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
      v146 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v122, 0x38u, 1, 1) + 4);
      v147 = *((_DWORD *)this + 102);
      v148 = v147 & 0x80000;
      if ( v146 )
      {
        if ( v148 )
        {
          v152 = NativeImageDumper::DataPtrToDisplay(this, v146);
          (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, __int64))(**((_QWORD **)this + 17) + 408LL))(
            *((_QWORD *)this + 17),
            "m_pImportThunkGlue",
            32,
            8,
            v152,
            16);
          v147 = *((_DWORD *)this + 102);
        }
        if ( (v147 & 0x80000) != 0 )
        {
          v187 = *(_QWORD *)((char *)DacInstantiateTypeByAddressHelper(v146, 0x10u, 1, 1) + 2);
          NativeImageDumper::DoWriteFieldMethodDesc(this, (__int64)&v187);
        }
        v187 = v146;
        NativeImageDumper::DumpPrecode(this);
        v153 = *((_DWORD *)this + 102);
        if ( (v153 & 0x80000) == 0 && v153 < 0 )
        {
          DacInstantiateTypeByAddressHelper(v146, 0x10u, 1, 1);
          v153 = *((_DWORD *)this + 102);
        }
        if ( (v153 & 0x80000) != 0 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
      }
      else if ( v148 )
      {
        (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _QWORD))(**((_QWORD **)this + 17) + 320LL))(
          *((_QWORD *)this + 17),
          "m_pImportThunkGlue",
          32,
          8,
          0);
      }
      if ( (*((_DWORD *)this + 102) & 0x80000) == 0 )
        goto LABEL_256;
      v149 = DacInstantiateTypeByAddressHelper(v122, 0x38u, 1, 1);
      v150 = DacInstantiateTypeByAddressHelper(v122, 0x38u, 1, 1);
      LOBYTE(v151) = 1;
      v187 = (v150[6] + DacGetTargetAddrForHostAddr(v149, v151) + 48) & -(__int64)(v150[6] != 0);
      NativeImageDumper::DoWriteFieldMethodDesc(this, (__int64)&v187);
      if ( (*((_DWORD *)this + 102) & 0x80000) == 0 )
        goto LABEL_256;
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
      goto LABEL_172;
    case 3:
      if ( (*((_DWORD *)this + 102) & 0x80000) == 0 )
        goto LABEL_256;
      (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 104LL))(
        *((_QWORD *)this + 17),
        "EEImplMethodDesc");
LABEL_172:
      v113 = *((_DWORD *)this + 102);
LABEL_173:
      v154 = (v113 & 0x80000) == 0;
      goto LABEL_183;
    case 6:
      v155 = *v2;
      if ( (*((_DWORD *)this + 102) & 0x80000) != 0 )
        (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 104LL))(
          *((_QWORD *)this + 17),
          "ComPlusCallMethodDesc");
      v156 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v155, 0x10u, 1, 1) + 1);
      v157 = *((_DWORD *)this + 102) & 0x80000;
      if ( v156 )
      {
        if ( v157 )
        {
          v187 = v156;
          NativeImageDumper::DoDumpComPlusCallInfo(this);
        }
      }
      else if ( v157 )
      {
        (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _QWORD))(**((_QWORD **)this + 17) + 320LL))(
          *((_QWORD *)this + 17),
          "m_pComPlusCallInfo",
          8,
          8,
          0);
      }
      v154 = (*((_DWORD *)this + 102) & 0x80000) == 0;
LABEL_183:
      if ( !v154 )
      {
        v158 = *(void (**)(void))(**((_QWORD **)this + 17) + 120LL);
LABEL_255:
        v158();
        goto LABEL_256;
      }
      goto LABEL_256;
  }
  if ( (_DWORD)v4 != 5 )
    goto LABEL_256;
  v159 = *v2;
  if ( (*((_DWORD *)this + 102) & 0x80000) != 0 )
    (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 104LL))(
      *((_QWORD *)this + 17),
      "InstantiatedMethodDesc");
  v160 = *((_WORD *)DacInstantiateTypeByAddressHelper(v159, 0x20u, 1, 1) + 12) & 7;
  if ( v160 == 2 )
  {
    v161 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v159, 0x20u, 1, 1) + 1);
    if ( (*((_DWORD *)this + 102) & 0x80000) == 0 )
    {
      v162 = 0;
      while ( v161 )
      {
        if ( *((int *)this + 102) < 0 )
        {
          v166 = (unsigned __int16 *)DacInstantiateTypeByAddressHelper(v161, 0x20u, 1, 1);
          DacInstantiateTypeByAddressHelper(v161, 16 * (v166[4] + 1), 1, 1);
        }
        v161 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v161, 0x20u, 1, 1);
      }
      goto LABEL_192;
    }
    v187 = *v2;
    *(_QWORD *)v188 = v161;
    NativeImageDumper::GetDependencyFromMD(this);
    NativeImageDumper::WriteFieldDictionaryLayout(this, (__int64)v188);
  }
  else
  {
    if ( v160 == 3 )
    {
      v167 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v159, 0x20u, 1, 1) + 1);
      if ( (v167 & 1) != 0 )
        v167 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v167 - 1, 8u, 1, 1);
      v162 = 0;
      if ( (!v167 || !(unsigned int)NativeImageDumper::DoWriteFieldAsFixup(this, "m_pWrappedMethodDesc", 8u, 8u, v167))
        && (*((_DWORD *)this + 102) & 0x80000) != 0 )
      {
        v187 = v167;
        NativeImageDumper::DoWriteFieldMethodDesc(this, (__int64)&v187);
      }
      goto LABEL_192;
    }
    if ( (*((_DWORD *)this + 102) & 0x80000) != 0 )
    {
      v162 = 0;
      (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _QWORD))(**((_QWORD **)this + 17) + 320LL))(
        *((_QWORD *)this + 17),
        "m_pDictLayout",
        8,
        8,
        0);
      goto LABEL_192;
    }
  }
  v162 = 0;
LABEL_192:
  v188[0] = *((unsigned __int16 *)DacInstantiateTypeByAddressHelper(v159, 0x20u, 1, 1) + 13);
  v163 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v159, 0x20u, 1, 1) + 2);
  if ( v160 == 3 )
  {
    v164 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v159, 0x20u, 1, 1) + 1);
    if ( (v164 & 1) != 0 && (v164 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v164 - 1, 8u, 1, 1), (v164 & 1) != 0) )
    {
      v192 = 2;
      v193 = 128;
      lpMem = v195;
      v195[0] = 0;
      v187 = *v2;
      NativeImageDumper::MethodDescToString(this);
      v165 = (MethodDesc *)DacInstantiateTypeByAddressHelper(v159, 0x20u, 1, 1);
      MethodDesc::GetNumGenericMethodArgs(v165);
      if ( (v193 & 0x800000000LL) != 0 )
        operator delete(lpMem);
    }
    else
    {
      v168 = (MethodDesc *)DacInstantiateTypeByAddressHelper(v164, 0x20u, 1, 1);
      if ( (unsigned int)MethodDesc::IsSharedByGenericMethodInstantiations(v168) )
        v169 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v164, 0x20u, 1, 1) + 1);
      else
        v169 = 0;
      v187 = v169;
      v170 = (MethodDesc *)DacInstantiateTypeByAddressHelper(v159, 0x20u, 1, 1);
      NumGenericMethodArgs = MethodDesc::GetNumGenericMethodArgs(v170);
      DictionaryLayout::GetFirstDictionaryBucketSize(NumGenericMethodArgs, &v187);
    }
  }
  if ( v163 )
  {
    v172 = *((_DWORD *)this + 102);
    v173 = v172;
    if ( (v172 & 0x80000) != 0 )
    {
      NativeImageDumper::DataPtrToDisplay(this, v163);
      (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 408LL))(
        *((_QWORD *)this + 17),
        "m_pPerInstInfo",
        16);
      v172 = *((_DWORD *)this + 102);
      v173 = v172;
      if ( (v172 & 0x80000) != 0 )
      {
        (*(void (**)(_QWORD, const char *, const wchar_t *, ...))(**((_QWORD **)this + 17) + 264LL))(
          *((_QWORD *)this + 17),
          "InstantiationInfo",
          L"[%-2s]: %s");
        v172 = *((_DWORD *)this + 102);
        v173 = v172;
      }
    }
    v174 = v188[0];
    if ( v188[0] )
    {
      do
      {
        v172 = v173;
        if ( (v173 & 0x80000) == 0 )
          break;
        (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 88LL))(
          *((_QWORD *)this + 17),
          "Handle");
        if ( (*((_DWORD *)this + 102) & 0x80000) != 0 )
          (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 224LL))(
            *((_QWORD *)this + 17),
            "Index",
            v162);
        v175 = DacInstantiateTypeByAddressHelper(v163, 8u, 1, 1);
        LOBYTE(v176) = 1;
        v187 = DacGetTargetAddrForHostAddr(v175, v176);
        v178 = *(_QWORD *)__DPtrBase<FixupPointer<TypeHandle>,__DPtr<FixupPointer<TypeHandle>>>::operator[]<unsigned int>(
                            &v187,
                            v162);
        if ( (v178 & 1) != 0 )
          v178 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v178 - 1, 8u, 1, 1);
        if ( (*((_DWORD *)this + 102) & 0x80000) != 0 )
          NativeImageDumper::WriteElementTypeHandle(this, v177, v178);
        if ( (v178 & 1) == 0 && (v178 & 2) != 0 )
        {
          v179 = *((_QWORD *)this + 15);
          if ( v179 <= v178 - 2 && v178 - 2 < *((_QWORD *)this + 16) + v179 )
          {
            v187 = v178 - 2;
            SArray<__DPtr<TypeDesc>,1>::AppendEx((NativeImageDumper *)((char *)this + 488));
          }
        }
        v172 = *((_DWORD *)this + 102);
        v173 = v172;
        if ( (v172 & 0x80000) != 0 )
        {
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 96LL))(*((_QWORD *)this + 17));
          v172 = *((_DWORD *)this + 102);
          v173 = v172;
        }
        ++v162;
        v174 = v188[0];
      }
      while ( v162 < v188[0] );
      v2 = v189;
    }
    if ( (v172 & 0x80000) == 0
      || ((*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 272LL))(
            *((_QWORD *)this + 17),
            "Total TypeHandles"),
          v172 = *((_DWORD *)this + 102),
          (v172 & 0x80000) == 0)
      || ((*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 120LL))(*((_QWORD *)this + 17)),
          v172 = *((_DWORD *)this + 102),
          (v172 & 0x80000) == 0) )
    {
      if ( v172 < 0 )
        DacInstantiateTypeByAddressHelper(v163, 8 * v174, 1, 1);
    }
  }
  else
  {
    (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _QWORD))(**((_QWORD **)this + 17) + 320LL))(
      *((_QWORD *)this + 17),
      "m_pPerInstInfo",
      16,
      8,
      0);
  }
  if ( (*((_DWORD *)this + 102) & 0x80000) != 0 )
  {
    v192 = 2;
    v193 = 128;
    lpMem = v195;
    v195[0] = 0;
    v180 = (unsigned __int16 *)DacInstantiateTypeByAddressHelper(v159, 0x20u, 1, 1);
    EnumFlagsToString(
      v180[12],
      (const struct NativeImageDumper::EnumMnemonics *)&NativeImageDumper::s_IMDFlags,
      7,
      L", ",
      (struct SString *)&v192);
    SString::ConvertToUnicode((SString *)&v192);
    DacInstantiateTypeByAddressHelper(v159, 0x20u, 1, 1);
    (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 352LL))(
      *((_QWORD *)this + 17),
      "m_wFlags2",
      24);
    if ( (v193 & 0x800000000LL) != 0 )
      operator delete(lpMem);
    if ( (*((_DWORD *)this + 102) & 0x80000) != 0 )
    {
      DacInstantiateTypeByAddressHelper(v159, 0x20u, 1, 1);
      (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 336LL))(
        *((_QWORD *)this + 17),
        "m_wNumGenericArgs",
        26);
    }
  }
  if ( (*((_BYTE *)DacInstantiateTypeByAddressHelper(v159, 0x20u, 1, 1) + 24) & 0x10) != 0 )
  {
    v182 = DacInstantiateTypeByAddressHelper(v159, 0x20u, 1, 1);
    v183 = (&MethodDesc::s_ClassificationSizeTable)[v182[3] & 0x1F];
    if ( (*((_BYTE *)v182 + 3) & 8) != 0 )
    {
      LOBYTE(v181) = 1;
      v184 = DacGetTargetAddrForHostAddr(v182, v181);
      v183 += (*(_DWORD *)DacInstantiateTypeByAddressHelper((unsigned __int64)v183 + v184, 8u, 1, 1) & 1) + 1;
    }
    LOBYTE(v181) = 1;
    v185 = DacGetTargetAddrForHostAddr(v182, v181);
    if ( (*((_DWORD *)this + 102) & 0x80000) == 0 )
      goto LABEL_256;
    v189 = (unsigned __int64 *)((char *)v183 + v185);
    NativeImageDumper::DoDumpComPlusCallInfo(this);
  }
  if ( (*((_DWORD *)this + 102) & 0x80000) != 0 )
  {
    v158 = *(void (**)(void))(**((_QWORD **)this + 17) + 416LL);
    goto LABEL_255;
  }
LABEL_256:
  result = *((unsigned int *)this + 102);
  if ( (result & 0x80000) == 0
    || ((*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17)),
        result = *((unsigned int *)this + 102),
        (result & 0x80000) == 0) )
  {
    if ( (int)result < 0 )
      return (__int64)DacInstantiateTypeByAddressHelper(*v2, v190[0], 1, 1);
  }
  return result;
}

```

## disassembly

```asm
0x1800599a4  mov     [rsp-8+arg_10], rbx
0x1800599a9  push    rbp
0x1800599aa  push    rsi
0x1800599ab  push    rdi
0x1800599ac  push    r12
0x1800599ae  push    r13
0x1800599b0  push    r14
0x1800599b2  push    r15
0x1800599b4  lea     rbp, [rsp-70h]
0x1800599b9  sub     rsp, 170h
0x1800599c0  mov     rax, cs:__security_cookie
0x1800599c7  xor     rax, rsp
0x1800599ca  mov     [rbp+0A0h+var_38], rax
0x1800599ce  mov     rsi, r8
0x1800599d1  mov     r12, rdx
0x1800599d4  mov     [rsp+1A0h+var_130], rdx
0x1800599d9  mov     r13, rcx
0x1800599dc  mov     r9b, 1; bool
0x1800599df  mov     r8b, r9b; bool
0x1800599e2  mov     edi, 8
0x1800599e7  mov     edx, edi; unsigned int
0x1800599e9  mov     rcx, [r12]; unsigned __int64
0x1800599ed  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800599f2  movzx   ecx, word ptr [rax+6]
0x1800599f6  and     ecx, 7
0x1800599f9  mov     r15d, ecx
0x1800599fc  mov     [rsp+1A0h+var_140], r15
0x180059a01  lea     rax, __ImageBase
0x180059a08  mov     rbx, ds:rva off_18012EBE0[rax+rcx*8]; "MethodDesc" ...
0x180059a10  mov     r9b, 1; bool
0x180059a13  mov     r8b, r9b; bool
0x180059a16  mov     edx, edi; unsigned int
0x180059a18  mov     rcx, [r12]; unsigned __int64
0x180059a1c  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180059a21  mov     rcx, rax; this
0x180059a24  call    ?SizeOf@MethodDesc@@QEAA_KXZ; MethodDesc::SizeOf(void)
0x180059a29  mov     rdi, rax
0x180059a2c  mov     qword ptr [rsp+1A0h+var_128], rax
0x180059a31  mov     ecx, [r13+198h]
0x180059a38  bt      ecx, 13h
0x180059a3c  jnb     short loc_180059A74
0x180059a3e  mov     rdx, [r12]; unsigned __int64
0x180059a42  mov     rcx, r13; this
0x180059a45  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z; NativeImageDumper::DataPtrToDisplay(unsigned __int64)
0x180059a4a  mov     r10, rax
0x180059a4d  mov     rcx, [r13+88h]
0x180059a54  mov     r8, [rcx]
0x180059a57  mov     r9d, edi
0x180059a5a  mov     rax, [r8+188h]
0x180059a61  mov     r8, r10
0x180059a64  mov     rdx, rbx
0x180059a67  call    cs:__guard_dispatch_icall_fptr
0x180059a6d  mov     ecx, [r13+198h]
0x180059a74  xor     r14d, r14d
0x180059a77  mov     edi, 80000h
0x180059a7c  test    edi, ecx
0x180059a7e  jz      loc_180059B34
0x180059a84  mov     [rbp+0A0h+var_110], r14
0x180059a88  mov     [rbp+0A0h+var_110+4], 80h
0x180059a90  mov     [rbp+0A0h+lpMem], r14
0x180059a94  lea     rax, [rbp+0A0h+var_F8]
0x180059a98  mov     [rbp+0A0h+lpMem], rax
0x180059a9c  mov     dword ptr [rbp+0A0h+var_110], 2
0x180059aa3  mov     rax, [rbp+0A0h+lpMem]
0x180059aa7  mov     [rax], r14w
0x180059aab  mov     rax, [r12]
0x180059aaf  mov     qword ptr [rsp+1A0h+var_138], rax
0x180059ab4  lea     r8, [rbp+0A0h+var_110]
0x180059ab8  lea     rdx, [rsp+1A0h+var_138]
0x180059abd  mov     rcx, r13; this
0x180059ac0  call    ?MethodDescToString@NativeImageDumper@@QEAAXV?$__DPtr@VMethodDesc@@@@AEAVSString@@@Z; NativeImageDumper::MethodDescToString(__DPtr<MethodDesc>,SString &)
0x180059ac5  test    [r13+198h], edi
0x180059acc  jz      short loc_180059AFA
0x180059ace  lea     rcx, [rbp+0A0h+var_110]; this
0x180059ad2  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180059ad7  mov     rcx, [r13+88h]
0x180059ade  mov     rax, [rcx]
0x180059ae1  mov     r8, [rbp+0A0h+lpMem]
0x180059ae5  lea     rdx, aName_0; "Name"
0x180059aec  mov     rax, [rax+0D8h]
0x180059af3  call    cs:__guard_dispatch_icall_fptr
0x180059af9  nop
0x180059afa  mov     ebx, 8
0x180059aff  test    [rbp+0A0h+var_108], bl
0x180059b02  jz      short loc_180059B39
0x180059b04  mov     rbx, [rbp+0A0h+lpMem]
0x180059b08  test    rbx, rbx
0x180059b0b  jz      short loc_180059B34
0x180059b0d  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180059b14  test    rax, rax
0x180059b17  jnz     short loc_180059B26
0x180059b19  call    cs:__imp_GetProcessHeap
0x180059b1f  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180059b26  mov     r8, rbx; lpMem
0x180059b29  xor     edx, edx; dwFlags
0x180059b2b  mov     rcx, rax; hHeap
0x180059b2e  call    cs:__imp_HeapFree
0x180059b34  mov     ebx, 8
0x180059b39  mov     eax, [r13+198h]
0x180059b40  test    edi, eax
0x180059b42  jz      loc_180059BD7
0x180059b48  mov     r9b, 1; bool
0x180059b4b  mov     r8b, r9b; bool
0x180059b4e  mov     edx, ebx; unsigned int
0x180059b50  mov     rcx, [r12]; unsigned __int64
0x180059b54  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180059b59  mov     rcx, [r13+88h]
0x180059b60  mov     rdx, [rcx]
0x180059b63  movzx   r8d, word ptr [rax]
0x180059b67  mov     rax, [rdx+150h]
0x180059b6e  mov     dword ptr [rsp+1A0h+var_180], r8d
0x180059b73  mov     r9d, 2
0x180059b79  xor     r8d, r8d
0x180059b7c  lea     rdx, aMWflags3andtok; "m_wFlags3AndTokenRemainder"
0x180059b83  call    cs:__guard_dispatch_icall_fptr
0x180059b89  mov     eax, [r13+198h]
0x180059b90  test    edi, eax
0x180059b92  jz      short loc_180059BD7
0x180059b94  mov     r9b, 1; bool
0x180059b97  mov     r8b, r9b; bool
0x180059b9a  mov     edx, ebx; unsigned int
0x180059b9c  mov     rcx, [r12]; unsigned __int64
0x180059ba0  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180059ba5  mov     rcx, [r13+88h]
0x180059bac  mov     rdx, [rcx]
0x180059baf  movzx   r8d, byte ptr [rax+2]
0x180059bb4  mov     rax, [rdx+150h]
0x180059bbb  mov     dword ptr [rsp+1A0h+var_180], r8d
0x180059bc0  mov     r9d, 1
0x180059bc6  lea     r8d, [r9+1]
0x180059bca  lea     rdx, aMChunkindex; "m_chunkIndex"
0x180059bd1  call    cs:__guard_dispatch_icall_fptr
0x180059bd7  mov     eax, 5
0x180059bdc  cmp     r15d, eax
0x180059bdf  jnz     loc_180059CB0
0x180059be5  mov     r9b, 1; bool
0x180059be8  mov     r8b, r9b; bool
0x180059beb  mov     edx, ebx; unsigned int
0x180059bed  mov     rcx, [r12]; unsigned __int64
0x180059bf1  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180059bf6  cmp     [rax+2], r14b
0x180059bfa  jnz     loc_180059CB0
0x180059c00  mov     r9b, 1; bool
0x180059c03  mov     r8b, r9b; bool
0x180059c06  mov     edx, ebx; unsigned int
0x180059c08  mov     rcx, [r12]; unsigned __int64
0x180059c0c  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180059c11  mov     rbx, rax
0x180059c14  mov     dl, 1
0x180059c16  mov     rcx, rax
0x180059c19  call    DacGetTargetAddrForHostAddr
0x180059c1e  mov     rcx, rax
0x180059c21  movzx   eax, byte ptr [rbx+2]
0x180059c25  shl     rax, 3
0x180059c29  sub     rcx, rax
0x180059c2c  sub     rcx, 18h; unsigned __int64
0x180059c30  mov     r9b, 1; bool
0x180059c33  mov     r8b, r9b; bool
0x180059c36  mov     edx, 18h; unsigned int
0x180059c3b  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180059c40  mov     dl, 1
0x180059c42  mov     rcx, rax
0x180059c45  call    DacGetTargetAddrForHostAddr
0x180059c4a  mov     rbx, rax
0x180059c4d  test    [r13+198h], edi
0x180059c54  jz      loc_180059DB1
0x180059c5a  mov     r9b, 1; bool
0x180059c5d  mov     r8b, r9b; bool
0x180059c60  mov     edx, 18h; unsigned int
0x180059c65  mov     rcx, rax; unsigned __int64
0x180059c68  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180059c6d  movzx   ecx, byte ptr [rax+10h]
0x180059c71  lea     rdi, ds:20h[rcx*8]
0x180059c79  mov     rdx, rbx; unsigned __int64
0x180059c7c  mov     rcx, r13; this
0x180059c7f  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z; NativeImageDumper::DataPtrToDisplay(unsigned __int64)
0x180059c84  mov     rcx, [r13+88h]
0x180059c8b  mov     rdx, [rcx]
0x180059c8e  mov     r10, [rdx+0B8h]
0x180059c95  mov     r9, rdi
0x180059c98  mov     r8, rax
0x180059c9b  lea     rdx, aMethoddescchun; "MethodDescChunk"
0x180059ca2  mov     rax, r10
0x180059ca5  call    cs:__guard_dispatch_icall_fptr
0x180059cab  mov     edi, 80000h
0x180059cb0  test    [r13+198h], edi
0x180059cb7  jz      loc_180059DB1
0x180059cbd  mov     [rbp+0A0h+var_110], r14
0x180059cc1  mov     [rbp+0A0h+var_110+4], 80h
0x180059cc9  mov     [rbp+0A0h+lpMem], r14
0x180059ccd  lea     rax, [rbp+0A0h+var_F8]
0x180059cd1  mov     [rbp+0A0h+lpMem], rax
0x180059cd5  mov     dword ptr [rbp+0A0h+var_110], 2
0x180059cdc  mov     rax, [rbp+0A0h+lpMem]
0x180059ce0  mov     [rax], r14w
0x180059ce4  mov     r9b, 1; bool
0x180059ce7  mov     r8b, r9b; bool
0x180059cea  mov     edx, 8; unsigned int
0x180059cef  mov     rcx, [r12]; unsigned __int64
0x180059cf3  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180059cf8  movzx   ecx, byte ptr [rax+3]; unsigned int
0x180059cfc  lea     rax, [rbp+0A0h+var_110]
0x180059d00  mov     [rsp+1A0h+var_180], rax; struct SString *
0x180059d05  lea     r9, asc_180137070; ", "
0x180059d0c  mov     r8d, 9; int
0x180059d12  lea     rdx, ?s_MDFlag2@NativeImageDumper@@2PAUEnumMnemonics@1@A; struct NativeImageDumper::EnumMnemonics *
0x180059d19  call    ?EnumFlagsToString@@YAXKPEBUEnumMnemonics@NativeImageDumper@@HPEBGAEAVSString@@@Z; EnumFlagsToString(ulong,NativeImageDumper::EnumMnemonics const *,int,ushort const *,SString &)
0x180059d1e  lea     rcx, [rbp+0A0h+var_110]; this
0x180059d22  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180059d27  mov     rbx, [rbp+0A0h+lpMem]
0x180059d2b  mov     r9b, 1; bool
0x180059d2e  mov     r8b, r9b; bool
0x180059d31  mov     edx, 8; unsigned int
0x180059d36  mov     rcx, [r12]; unsigned __int64
0x180059d3a  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180059d3f  mov     rcx, [r13+88h]
0x180059d46  mov     rdx, [rcx]
0x180059d49  movzx   r8d, byte ptr [rax+3]
0x180059d4e  mov     rax, [rdx+160h]
0x180059d55  mov     [rsp+1A0h+var_178], rbx
0x180059d5a  mov     dword ptr [rsp+1A0h+var_180], r8d
0x180059d5f  mov     r9d, 1
0x180059d65  lea     r8d, [r9+2]
0x180059d69  lea     rdx, aMBflags2; "m_bFlags2"
0x180059d70  call    cs:__guard_dispatch_icall_fptr
0x180059d76  nop
0x180059d77  mov     ecx, 8
0x180059d7c  test    [rbp+0A0h+var_108], cl
0x180059d7f  jz      short loc_180059DB6
0x180059d81  mov     rbx, [rbp+0A0h+lpMem]
0x180059d85  test    rbx, rbx
0x180059d88  jz      short loc_180059DB6
0x180059d8a  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180059d91  test    rax, rax
0x180059d94  jnz     short loc_180059DA3
0x180059d96  call    cs:__imp_GetProcessHeap
0x180059d9c  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180059da3  mov     r8, rbx; lpMem
0x180059da6  xor     edx, edx; dwFlags
0x180059da8  mov     rcx, rax; hHeap
0x180059dab  call    cs:__imp_HeapFree
0x180059db1  mov     ecx, 8
0x180059db6  mov     eax, [r13+198h]
0x180059dbd  mov     ebx, 3FFh
0x180059dc2  test    edi, eax
0x180059dc4  jz      loc_180059F17
0x180059dca  mov     r9b, 1; bool
0x180059dcd  mov     r8b, r9b; bool
0x180059dd0  mov     edx, ecx; unsigned int
0x180059dd2  mov     rcx, [r12]; unsigned __int64
0x180059dd6  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180059ddb  mov     rcx, [r13+88h]
0x180059de2  mov     r10, [rcx]
0x180059de5  movzx   edx, word ptr [rax+4]
0x180059de9  and     dx, bx
0x180059dec  cmp     [rax+6], r14w
0x180059df1  cmovl   dx, [rax+4]
0x180059df6  movzx   edx, dx
0x180059df9  mov     dword ptr [rsp+1A0h+var_180], edx
0x180059dfd  mov     r9d, 2
0x180059e03  lea     r8d, [r9+2]
0x180059e07  lea     rdx, aMWslotnumber; "m_wSlotNumber"
0x180059e0e  mov     rax, [r10+150h]
0x180059e15  call    cs:__guard_dispatch_icall_fptr
0x180059e1b  mov     eax, [r13+198h]
0x180059e22  test    edi, eax
0x180059e24  jz      loc_180059F17
0x180059e2a  mov     [rbp+0A0h+var_110], r14
0x180059e2e  mov     [rbp+0A0h+var_110+4], 80h
0x180059e36  mov     [rbp+0A0h+lpMem], r14
0x180059e3a  lea     rax, [rbp+0A0h+var_F8]
0x180059e3e  mov     [rbp+0A0h+lpMem], rax
0x180059e42  mov     dword ptr [rbp+0A0h+var_110], 2
0x180059e49  mov     rax, [rbp+0A0h+lpMem]
0x180059e4d  mov     [rax], r14w
0x180059e51  mov     r9b, 1; bool
0x180059e54  mov     r8b, r9b; bool
0x180059e57  mov     edi, 8
0x180059e5c  mov     edx, edi; unsigned int
0x180059e5e  mov     rcx, [r12]; unsigned __int64
0x180059e62  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180059e67  movzx   ecx, word ptr [rax+6]; unsigned int
0x180059e6b  lea     rax, [rbp+0A0h+var_110]
0x180059e6f  mov     [rsp+1A0h+var_180], rax; struct SString *
0x180059e74  lea     r9, asc_180137070; ", "
0x180059e7b  lea     r8d, [rdi+0Dh]; int
0x180059e7f  lea     rdx, ?s_MDC@NativeImageDumper@@2PAUEnumMnemonics@1@A; struct NativeImageDumper::EnumMnemonics *
0x180059e86  call    ?EnumFlagsToString@@YAXKPEBUEnumMnemonics@NativeImageDumper@@HPEBGAEAVSString@@@Z; EnumFlagsToString(ulong,NativeImageDumper::EnumMnemonics const *,int,ushort const *,SString &)
0x180059e8b  lea     rcx, [rbp+0A0h+var_110]; this
0x180059e8f  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180059e94  mov     rbx, [rbp+0A0h+lpMem]
0x180059e98  mov     r9b, 1; bool
0x180059e9b  mov     r8b, r9b; bool
0x180059e9e  mov     edx, edi; unsigned int
0x180059ea0  mov     rcx, [r12]; unsigned __int64
0x180059ea4  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180059ea9  mov     rcx, [r13+88h]
0x180059eb0  mov     rdx, [rcx]
0x180059eb3  movzx   r8d, word ptr [rax+6]
0x180059eb8  mov     rax, [rdx+160h]
  ... truncated ...
```
