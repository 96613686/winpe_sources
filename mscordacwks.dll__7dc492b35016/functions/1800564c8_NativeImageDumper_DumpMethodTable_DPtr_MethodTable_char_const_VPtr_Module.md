# NativeImageDumper::DumpMethodTable(__DPtr<MethodTable>,char const *,__VPtr<Module>)

- ea: `0x1800564c8`
- end: `0x180059116`
- name: `?DumpMethodTable@NativeImageDumper@@QEAAXV?$__DPtr@VMethodTable@@@@PEBDV?$__VPtr@VModule@@@@@Z`
- size: `11342`
- prototype: `__int64 __fastcall(NativeImageDumper *this)`
- caller_count: `1`
- callee_count: `45`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180053538`

## callees

- `0x18000c824`
- `0x18001dd50`
- `0x1800210f0`
- `0x180022068`
- `0x180040b04`
- `0x180040ba0`
- `0x180040c60`
- `0x180041044`
- `0x18004240c`
- `0x180042724`
- `0x180042e18`
- `0x18005106c`
- `0x180054090`
- `0x1800547e4`
- `0x1800552bc`
- `0x180055b7c`
- `0x180055f3c`
- `0x18005609c`
- `0x1800564c8`
- `0x180059118`
- `0x18005e9d0`
- `0x1800629c8`
- `0x1800671c4`
- `0x180067230`
- `0x180067284`
- `0x1800672f8`
- `0x180067498`
- `0x180067508`
- `0x180067574`
- `0x180067600`
- `0x180067658`
- `0x180072664`
- `0x18007344c`
- `0x18007d5c8`
- `0x180081f00`
- `0x180082694`
- `0x18008276c`
- `0x18009e948`
- `0x18009e97c`
- `0x18009e9f4`
- `0x18009eab0`
- `0x18009ec58`
- `0x18009ece4`
- `0x1800f0d20`
- `0x180106100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180056610`
- `KERNEL32!HeapFree` at `0x1800567da`
- `KERNEL32!HeapFree` at `0x1800569e1`
- `KERNEL32!HeapFree` at `0x180056ae4`
- `KERNEL32!HeapFree` at `0x180056610`
- `KERNEL32!HeapFree` at `0x1800567da`
- `KERNEL32!HeapFree` at `0x1800569e1`
- `KERNEL32!HeapFree` at `0x180056ae4`
- `KERNEL32!GetProcessHeap` at `0x1800565fb`
- `KERNEL32!GetProcessHeap` at `0x1800567c5`
- `KERNEL32!GetProcessHeap` at `0x1800569cc`
- `KERNEL32!GetProcessHeap` at `0x180056acf`
- `KERNEL32!GetProcessHeap` at `0x1800565fb`
- `KERNEL32!GetProcessHeap` at `0x1800567c5`
- `KERNEL32!GetProcessHeap` at `0x1800569cc`
- `KERNEL32!GetProcessHeap` at `0x180056acf`

## string_xrefs

- `0x1800565ce`: `WARNING! MethodTable %S is generic but is not hard bound to its EEClass.  Cannot compute generic dictionary sizes.\n`
- `0x1800568e3`: `ComponentSize`
- `0x180056c5a`: `m_wToken`
- `0x180056e5f`: `m_pWriteableData`
- `0x1800586b3`: `OptionalMember_CCWTemplate`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall NativeImageDumper::DumpMethodTable(NativeImageDumper *this, unsigned __int64 *a2)
{
  unsigned __int64 *v2; // r15
  unsigned __int64 v4; // r14
  _QWORD *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rax
  void *v9; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int64 v11; // rsi
  __int64 v12; // r12
  unsigned __int64 v13; // rdx
  MethodTable *v14; // rax
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rdi
  __int64 v17; // rbx
  unsigned __int64 v18; // rax
  unsigned int v19; // r12d
  void *v20; // rbx
  HANDLE v21; // rax
  void *v22; // rax
  __int64 v23; // rdx
  unsigned __int64 TargetAddrForHostAddr; // rax
  void *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rax
  __int64 *v28; // rax
  unsigned int v29; // edx
  int *v30; // rax
  int v31; // ecx
  unsigned __int16 *v32; // rax
  unsigned __int16 *v33; // rax
  LPVOID v34; // rbx
  unsigned __int16 *v35; // rax
  void *v36; // rbx
  HANDLE v37; // rax
  _DWORD *v38; // rax
  LPVOID v39; // rbx
  _DWORD *v40; // rax
  void *v41; // rbx
  HANDLE v42; // rax
  unsigned __int16 *v43; // rax
  LPVOID v44; // rbx
  unsigned __int16 *v45; // rax
  _QWORD *v46; // rax
  _QWORD *v47; // rax
  unsigned __int64 v48; // rcx
  _QWORD *v49; // rax
  unsigned __int64 v50; // rax
  unsigned __int64 v51; // rbx
  unsigned int *v52; // rax
  LPVOID v53; // rdi
  _DWORD *v54; // rax
  _QWORD *v55; // rax
  __int64 v56; // rbx
  unsigned __int64 v57; // rax
  _BYTE *v58; // rax
  int v59; // ecx
  void *v60; // rax
  __int64 CanonicalMethodTable; // rax
  void *v62; // rax
  unsigned __int64 *Class; // rax
  unsigned __int64 v64; // rax
  _BYTE *v65; // rax
  unsigned __int64 v66; // rbx
  unsigned __int64 v67; // rax
  unsigned __int64 v68; // rbx
  _QWORD *v69; // rax
  __int64 v70; // rdi
  unsigned __int64 v71; // rax
  MethodTable *v72; // rax
  struct Dictionary *Dictionary; // rax
  __int64 v74; // rdx
  unsigned __int64 v75; // rax
  unsigned __int64 v76; // rdi
  void *v77; // rax
  __int64 v78; // rdx
  unsigned __int64 v79; // rsi
  void *v80; // rax
  int *v81; // rax
  unsigned __int64 v82; // r12
  __int64 v83; // r15
  unsigned int FirstDictionaryBucketSize; // eax
  int *v85; // rax
  unsigned int v86; // ecx
  unsigned __int64 v87; // rbx
  unsigned int v88; // r12d
  DictionaryLayout *v89; // rax
  DictionaryLayout *v90; // rax
  __int64 v91; // r14
  void *v92; // rax
  __int64 v93; // rdx
  __int64 v94; // rsi
  int *v95; // rax
  void *v96; // rax
  __int64 v97; // rdx
  __int64 v98; // rax
  void *v99; // rax
  void *v100; // rax
  int v101; // eax
  unsigned __int64 v102; // rbx
  DispatchMap *v103; // rax
  unsigned int MapSize; // edi
  unsigned __int64 v105; // rax
  struct MethodTable *v106; // rax
  int v107; // edi
  int v108; // esi
  int v109; // eax
  int v110; // ebx
  unsigned int v111; // ebx
  __int64 v112; // rbx
  int v113; // esi
  __int64 v114; // rdi
  unsigned __int64 v115; // rax
  void *v116; // rax
  unsigned int v117; // edi
  unsigned __int64 v118; // rsi
  unsigned __int64 v119; // rbx
  __int16 NumSlots; // ax
  DispatchMap *v121; // rax
  unsigned int v122; // eax
  int v123; // eax
  unsigned int v124; // edi
  void *v125; // rax
  __int64 v126; // rdx
  __int64 v127; // rax
  unsigned __int64 v128; // rax
  unsigned __int64 v129; // rdx
  __int64 v130; // rbx
  unsigned __int64 v131; // rax
  void *v132; // rax
  unsigned __int64 v133; // rbx
  __int64 v134; // rdi
  unsigned __int64 v135; // rax
  MethodTable *v136; // rsi
  _WORD *v137; // rdi
  unsigned __int16 *v138; // rbx
  void *v139; // rax
  unsigned __int64 *v140; // rax
  bool v141; // zf
  unsigned __int16 *v142; // rax
  MethodTable *v143; // rdi
  void *v144; // rbx
  unsigned __int64 *NonVirtualSlotsArray; // rax
  __int64 result; // rax
  unsigned __int64 v147; // rdi
  unsigned int v148; // esi
  unsigned __int64 v149; // rbx
  unsigned __int64 v150; // rax
  unsigned __int64 v151; // rcx
  int v152; // ecx
  int v153; // edx
  void *v154; // rax
  unsigned __int64 v155; // rdi
  unsigned __int64 v156; // rbx
  _WORD *v157; // rax
  __int64 v158; // rbx
  int v159; // eax
  int v160; // esi
  void *v161; // rax
  void *v162; // rax
  int v163; // eax
  _DWORD *v164; // rax
  MethodTable *v165; // rax
  void *v166; // rax
  unsigned __int64 *GuidInfoPtr; // rax
  unsigned __int64 *v168; // rax
  unsigned __int64 v169; // rbx
  unsigned __int64 v170; // rdi
  _WORD *v171; // r8
  unsigned int v172; // r9d
  int v173; // edx
  __int64 v174; // r8
  struct _GUID *v175; // rax
  _DWORD *v176; // rax
  MethodTable *v177; // rdi
  __int64 v178; // rdx
  __int64 v179; // rsi
  int v180; // eax
  unsigned int v181; // ebx
  __int64 v182; // rcx
  unsigned __int64 *v183; // rax
  unsigned __int64 v184; // rsi
  MethodTable *v185; // rdi
  int v186; // eax
  unsigned int v187; // ebx
  __int64 v188; // r8
  void *v189; // rax
  unsigned __int16 PackableField; // bx
  int v191; // esi
  MethodTable *v192; // rdi
  __int64 v193; // rdx
  __int64 v194; // r14
  int v195; // ecx
  unsigned int v196; // ebx
  unsigned int v197; // ecx
  unsigned int v198; // eax
  unsigned __int64 v199; // rbx
  unsigned int v200; // r12d
  unsigned __int64 v201; // r14
  MethodTable *v202; // rsi
  int v203; // ecx
  unsigned int v204; // edi
  unsigned int v205; // r9d
  __int64 v206; // rcx
  unsigned int v207; // r12d
  __int64 v208; // r8
  unsigned int v209; // r14d
  __int64 v210; // rsi
  unsigned __int64 v211; // rdi
  int v212; // eax
  unsigned int v213; // r12d
  MethodTable *v214; // rax
  MethodTable *v215; // rdi
  __int64 v216; // rdx
  __int64 v217; // rsi
  int v218; // ecx
  unsigned int v219; // ebx
  unsigned int v220; // eax
  unsigned int v221; // ecx
  unsigned int v222; // eax
  unsigned __int64 v223; // rbx
  MethodTable *v224; // rax
  unsigned int v225; // r14d
  unsigned __int64 v226; // r12
  MethodTable *v227; // rsi
  int v228; // ecx
  unsigned int v229; // edi
  unsigned int v230; // eax
  unsigned int v231; // r9d
  __int64 v232; // r8
  MethodTable *v233; // rax
  __int64 v234; // rdi
  unsigned __int16 NumVtableSlots; // ax
  void *v236; // rax
  __int64 v237; // rdx
  unsigned __int64 v238; // rdi
  unsigned int v239; // r14d
  MethodTable *v240; // rax
  unsigned __int64 v241; // rbx
  unsigned __int64 v242; // rax
  unsigned int *v243; // rax
  LPVOID v244; // rsi
  _DWORD *v245; // rax
  MethodTable *v246; // rax
  int v247; // edx
  MethodTable *v248; // rax
  unsigned __int64 *ContextStaticsBucketPtr; // rax
  unsigned __int64 v250; // rbx
  unsigned __int64 v251; // r14
  MethodTable *v252; // rsi
  int v253; // ecx
  unsigned int v254; // edi
  unsigned int v255; // ecx
  unsigned int v256; // eax
  unsigned int v257; // edi
  _DWORD *v258; // rax
  unsigned __int16 *v259; // rax
  char v260; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v261; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v262; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v263[2]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v264; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v265; // [rsp+70h] [rbp-90h]
  unsigned __int64 *v266; // [rsp+78h] [rbp-88h]
  unsigned __int64 v267; // [rsp+80h] [rbp-80h] BYREF
  int v268; // [rsp+88h] [rbp-78h]
  unsigned int v269; // [rsp+8Ch] [rbp-74h]
  int v270; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v271; // [rsp+A4h] [rbp-5Ch]
  LPVOID lpMem; // [rsp+B0h] [rbp-50h]
  _WORD v273[12]; // [rsp+B8h] [rbp-48h] BYREF
  int v274; // [rsp+D0h] [rbp-30h]
  int v275; // [rsp+D4h] [rbp-2Ch]

  v2 = a2;
  v266 = a2;
  v4 = 0;
  v265 = 0;
  if ( (*((_BYTE *)DacInstantiateTypeByAddressHelper(*a2, 0x40u, 1, 1) + 40) & 3) != 0 )
  {
    v5 = DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
    v7 = v5[5];
    if ( (v7 & 2) != 0 )
    {
      if ( (v7 & 1) != 0 )
        v8 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v7 - 3, 8u, 1, 1);
      else
        LOBYTE(v8) = v7 - 2;
    }
    else
    {
      LOBYTE(v6) = 1;
      LOBYTE(v8) = DacGetTargetAddrForHostAddr(v5, v6);
    }
    if ( (v8 & 1) != 0 )
    {
      v260 = 0;
      v271 = 128;
      lpMem = v273;
      v270 = 2;
      v273[0] = 0;
      v263[0] = *v2;
      NativeImageDumper::MethodTableToString(this);
      SString::ConvertToUnicode((SString *)&v270);
      (*(void (**)(_QWORD, const char *, ...))(**((_QWORD **)this + 17) + 24LL))(
        *((_QWORD *)this + 17),
        "WARNING! MethodTable %S is generic but is not hard bound to its EEClass.  Cannot compute generic dictionary sizes.\n",
        lpMem);
      if ( (v271 & 0x800000000LL) != 0 )
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
      goto LABEL_15;
    }
  }
  if ( !*((_BYTE *)this + 544) )
  {
    v260 = 0;
LABEL_15:
    v11 = *v2;
    v12 = *v2 + 64;
    v13 = *v2;
    goto LABEL_22;
  }
  v14 = (MethodTable *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
  MethodTable::GetSavedExtent(v14, &v264, v263);
  v4 = *((_QWORD *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1) + 5);
  v265 = v4;
  if ( (v4 & 2) != 0 )
  {
    if ( (v4 & 1) != 0 )
      v15 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v4 - 3, 8u, 1, 1);
    else
      v15 = v4 - 2;
    v4 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v15, 0x40u, 1, 1) + 5);
    v265 = v4;
  }
  v13 = *v2;
  v260 = 1;
  v12 = v263[0];
  v11 = v264;
LABEL_22:
  if ( (*((_DWORD *)this + 102) & 0x100) != 0
    && (v16 = NativeImageDumper::DataPtrToDisplay(this, v13),
        v17 = **((_QWORD **)this + 17),
        v18 = NativeImageDumper::DataPtrToDisplay(this, v11),
        (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, unsigned __int64, unsigned __int64))(v17 + 400))(
          *((_QWORD *)this + 17),
          "MethodTable",
          v16,
          v18,
          v12 - v11),
        (*((_DWORD *)this + 102) & 0x100) != 0) )
  {
    v19 = 0;
    v271 = 128;
    lpMem = v273;
    v270 = 2;
    v273[0] = 0;
    v263[0] = *v2;
    NativeImageDumper::MethodTableToString(this);
    if ( *((_DWORD *)this + 102) )
    {
      SString::ConvertToUnicode((SString *)&v270);
      (*(void (__fastcall **)(_QWORD, const char *, LPVOID))(**((_QWORD **)this + 17) + 216LL))(
        *((_QWORD *)this + 17),
        "Name",
        lpMem);
    }
    if ( (v271 & 0x800000000LL) != 0 )
    {
      v20 = lpMem;
      if ( lpMem )
      {
        v21 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          v21 = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = v21;
        }
        HeapFree(v21, 0, v20);
      }
    }
    if ( (*(_DWORD *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1) & 0x1000000) != 0 )
    {
      v22 = DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
      LOBYTE(v23) = 1;
      TargetAddrForHostAddr = DacGetTargetAddrForHostAddr(v22, v23);
      v25 = DacInstantiateTypeByAddressHelper(TargetAddrForHostAddr, 1u, 1, 1);
      LOBYTE(v26) = 1;
      v27 = DacGetTargetAddrForHostAddr(v25, v26);
      v28 = (__int64 *)DacInstantiateTypeByAddressHelper(v27 - 8, 8u, 1, 1);
      if ( *v28 >= 0 )
        v29 = 16 * *(_DWORD *)v28 + 8;
      else
        v29 = 8 * (2 - *(_DWORD *)v28);
      (*(void (__fastcall **)(_QWORD, const char *, _QWORD, _QWORD))(**((_QWORD **)this + 17) + 360LL))(
        *((_QWORD *)this + 17),
        "CGCDesc",
        -v29,
        v29);
    }
  }
  else
  {
    v19 = 0;
  }
  v30 = (int *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
  v31 = *((_DWORD *)this + 102) & 0x100;
  if ( *v30 >= 0 )
  {
    if ( v31 )
    {
      v270 = 2;
      v271 = 128;
      lpMem = v273;
      v273[0] = 0;
      v33 = (unsigned __int16 *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
      EnumFlagsToString(
        *v33,
        (const struct NativeImageDumper::EnumMnemonics *)&s_MTFlagsLow,
        21,
        L", ",
        (struct SString *)&v270);
      SString::ConvertToUnicode((SString *)&v270);
      v34 = lpMem;
      v35 = (unsigned __int16 *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
      (*(void (__fastcall **)(_QWORD, const char *, _QWORD, __int64, _DWORD, LPVOID))(**((_QWORD **)this + 17) + 352LL))(
        *((_QWORD *)this + 17),
        "m_dwFlags",
        0,
        4,
        *v35,
        v34);
      if ( (v271 & 0x800000000LL) != 0 )
      {
        v36 = lpMem;
        if ( lpMem )
        {
          v37 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
          if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
          {
            v37 = GetProcessHeap();
            `ClrFreeInProcessHeap'::`2'::ProcessHeap = v37;
          }
          HeapFree(v37, 0, v36);
        }
      }
    }
  }
  else if ( v31 )
  {
    v32 = (unsigned __int16 *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
    (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 224LL))(
      *((_QWORD *)this + 17),
      "ComponentSize",
      *v32);
  }
  if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
  {
    v270 = 2;
    v271 = 128;
    lpMem = v273;
    v273[0] = 0;
    v38 = DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
    EnumFlagsToString(
      *v38 & 0xFFFF0000,
      (const struct NativeImageDumper::EnumMnemonics *)&s_MTFlagsHigh,
      27,
      L", ",
      (struct SString *)&v270);
    SString::ConvertToUnicode((SString *)&v270);
    v39 = lpMem;
    v40 = DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
    (*(void (__fastcall **)(_QWORD, const char *, _QWORD, __int64, unsigned int, LPVOID))(**((_QWORD **)this + 17)
                                                                                        + 352LL))(
      *((_QWORD *)this + 17),
      "m_dwFlags",
      0,
      4,
      *v40 & 0xFFFF0000,
      v39);
    if ( (v271 & 0x800000000LL) != 0 )
    {
      v41 = lpMem;
      if ( lpMem )
      {
        v42 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          v42 = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = v42;
        }
        HeapFree(v42, 0, v41);
      }
    }
  }
  if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
  {
    DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
    (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 336LL))(
      *((_QWORD *)this + 17),
      "m_BaseSize",
      4);
    if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
    {
      v270 = 2;
      v271 = 128;
      lpMem = v273;
      v273[0] = 0;
      v43 = (unsigned __int16 *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
      EnumFlagsToString(
        v43[4],
        (const struct NativeImageDumper::EnumMnemonics *)&s_MTFlags2,
        15,
        L", ",
        (struct SString *)&v270);
      SString::ConvertToUnicode((SString *)&v270);
      v44 = lpMem;
      v45 = (unsigned __int16 *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
      (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD, LPVOID))(**((_QWORD **)this + 17) + 352LL))(
        *((_QWORD *)this + 17),
        "m_wFlags2",
        8,
        2,
        v45[4],
        v44);
      if ( (v271 & 0x800000000LL) != 0 )
        operator delete(lpMem);
    }
  }
  if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
  {
    DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
    (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 336LL))(
      *((_QWORD *)this + 17),
      "m_wToken",
      10);
    if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
    {
      DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
      (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 336LL))(
        *((_QWORD *)this + 17),
        "m_wNumVirtuals",
        12);
      if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
      {
        DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
        (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 336LL))(
          *((_QWORD *)this + 17),
          "m_wNumInterfaces",
          14);
      }
    }
  }
  v46 = DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
  if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
  {
    if ( v46[2] )
    {
      v47 = DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
      v48 = v47[2];
      if ( (*(_DWORD *)v47 & 0x800000) != 0 )
        v48 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v48 + 16, 8u, 1, 1);
      v263[0] = v48;
      NativeImageDumper::DoWriteFieldMethodTable(this, (__int64)v263);
    }
    else
    {
      (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _QWORD))(**((_QWORD **)this + 17) + 320LL))(
        *((_QWORD *)this + 17),
        "m_pParentMethodTable",
        16,
        8,
        0);
    }
    if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
    {
      v49 = DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
      v50 = NativeImageDumper::DataPtrToDisplay(this, v49[3]);
      (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64))(**((_QWORD **)this + 17) + 320LL))(
        *((_QWORD *)this + 17),
        "m_pLoaderModule",
        24,
        8,
        v50);
    }
  }
  v51 = *((_QWORD *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1) + 4);
  if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
  {
    NativeImageDumper::DataPtrToDisplay(this, v51);
    (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 408LL))(
      *((_QWORD *)this + 17),
      "m_pWriteableData",
      32);
    if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
    {
      v270 = 2;
      v271 = 128;
      lpMem = v273;
      v273[0] = 0;
      v52 = (unsigned int *)DacInstantiateTypeByAddressHelper(v51, 0x10u, 1, 1);
      EnumFlagsToString(
        *v52,
        (const struct NativeImageDumper::EnumMnemonics *)&s_WriteableMTFlags,
        11,
        L", ",
        (struct SString *)&v270);
      SString::ConvertToUnicode((SString *)&v270);
      v53 = lpMem;
      v54 = DacInstantiateTypeByAddressHelper(v51, 0x10u, 1, 1);
      (*(void (__fastcall **)(_QWORD, const char *, _QWORD, __int64, _DWORD, LPVOID))(**((_QWORD **)this + 17) + 352LL))(
        *((_QWORD *)this + 17),
        "m_dwFlags",
        0,
        4,
        *v54,
        v53);
      if ( (v271 & 0x800000000LL) != 0 )
        operator delete(lpMem);
    }
  }
  if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
  {
    v55 = DacInstantiateTypeByAddressHelper(v51, 0x10u, 1, 1);
    v56 = **((_QWORD **)this + 17);
    v57 = NativeImageDumper::DataPtrToDisplay(this, v55[1]);
    (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64))(v56 + 320))(
      *((_QWORD *)this + 17),
      "m_hExposedClassObject",
      8,
      8,
      v57);
    if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
  }
  v58 = DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
  v59 = *((_DWORD *)this + 102) & 0x100;
  if ( (v58[40] & 3) != 0 )
  {
    if ( v59 )
    {
      v60 = DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
      CanonicalMethodTable = MethodTable::GetCanonicalMethodTable(v60, &v261);
      NativeImageDumper::DoWriteFieldMethodTable(this, CanonicalMethodTable);
    }
  }
  else if ( v59 )
  {
    v62 = DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
    Class = (unsigned __int64 *)MethodTable::GetClass(v62, &v261);
    v64 = NativeImageDumper::DataPtrToDisplay(this, *Class);
    (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64))(**((_QWORD **)this + 17) + 320LL))(
      *((_QWORD *)this + 17),
      "m_pEEClass",
      40,
      8,
      v64);
  }
  if ( (*(_DWORD *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1) & 0xC0000) == 0x80000
    && (*((_DWORD *)this + 102) & 0x100) != 0 )
  {
    DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
    NativeImageDumper::DoWriteFieldTypeHandle(this, "m_ElementTypeHnd", 48);
  }
  v65 = DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
  if ( (v65[8] & 1) != 0 && (*(_DWORD *)v65 & 0xC0000) != 0x80000 && v260 )
  {
    v66 = *((_QWORD *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1) + 6) - 8LL;
    if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
    {
      v67 = NativeImageDumper::DataPtrToDisplay(this, v66);
      (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, __int64))(**((_QWORD **)this + 17) + 392LL))(
        *((_QWORD *)this + 17),
        "GenericsDictInfo",
        v67,
        8);
      if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
      {
        DacInstantiateTypeByAddressHelper(v66, 8u, 1, 1);
        (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 336LL))(
          *((_QWORD *)this + 17),
          "m_wNumDicts",
          4);
        if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
        {
          DacInstantiateTypeByAddressHelper(v66, 8u, 1, 1);
          (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 336LL))(
            *((_QWORD *)this + 17),
            "m_wNumTyPars",
            6);
          if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
        }
      }
    }
    v68 = *((_QWORD *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1) + 6);
    if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
    {
      v69 = DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
      if ( (v69[1] & 1) == 0 || (*(_DWORD *)v69 & 0xC0000) == 0x80000 )
        v70 = 0;
      else
        v70 = *((unsigned __int16 *)DacInstantiateTypeByAddressHelper(v69[6] - 8LL, 8u, 1, 1) + 2);
      v71 = NativeImageDumper::DataPtrToDisplay(this, v68);
      (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, __int64))(**((_QWORD **)this + 17) + 392LL))(
        *((_QWORD *)this + 17),
        "PerInstInfo",
        v71,
        8 * v70);
    }
    v72 = (MethodTable *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
    Dictionary = MethodTable::GetDictionary(v72);
    LOBYTE(v74) = 1;
    v75 = DacGetTargetAddrForHostAddr(Dictionary, v74);
    v76 = v75;
    if ( v75 )
    {
      v77 = DacInstantiateTypeByAddressHelper(v75, 8u, 1, 1);
      LOBYTE(v78) = 1;
      v79 = DacGetTargetAddrForHostAddr(v77, v78);
      v80 = DacInstantiateTypeByAddressHelper(v4, 0x48u, 1, 1);
      EEClass::GetDictionaryLayout(v80, v263);
      if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
      {
        v261 = v263[0];
        v81 = (int *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
        if ( *v81 >= 0 && (*(_BYTE *)v81 & 0x30) != 0 )
          LODWORD(v264) = *((unsigned __int16 *)DacInstantiateTypeByAddressHelper(*((_QWORD *)v81 + 6) - 8LL, 8u, 1, 1)
                          + 3);
        else
          LODWORD(v264) = 0;
        v82 = NativeImageDumper::DataPtrToDisplay(this, v76);
        v83 = **((_QWORD **)this + 17);
        FirstDictionaryBucketSize = DictionaryLayout::GetFirstDictionaryBucketSize((unsigned int)v264, &v261);
        (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, _QWORD))(v83 + 392))(
          *((_QWORD *)this + 17),
          "Dictionary",
          v82,
          FirstDictionaryBucketSize);
        v2 = v266;
        v19 = 0;
        if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
          (*(void (__fastcall **)(_QWORD, const char *, _QWORD, __int64, _QWORD))(**((_QWORD **)this + 17) + 296LL))(
            *((_QWORD *)this + 17),
            "m_pEntries",
            0,
            8,
            0);
      }
      while ( 1 )
      {
        v85 = (int *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
        if ( *v85 >= 0 && (*(_BYTE *)v85 & 0x30) != 0 )
          v86 = *((unsigned __int16 *)DacInstantiateTypeByAddressHelper(*((_QWORD *)v85 + 6) - 8LL, 8u, 1, 1) + 3);
        else
          v86 = 0;
        if ( v19 >= v86 )
          break;
        v261 = DacTAddrOffset(v79, v19, 8u);
        NativeImageDumper::DumpDictionaryEntry(this);
        ++v19;
      }
      v87 = v263[0];
      v88 = 0;
      v4 = v265;
      if ( v263[0] )
      {
        v89 = (DictionaryLayout *)DacInstantiateTypeByAddressHelper(v263[0], 0x20u, 1, 1);
        if ( DictionaryLayout::GetNumUsedSlots(v89) )
        {
          v90 = (DictionaryLayout *)DacInstantiateTypeByAddressHelper(v87, 0x20u, 1, 1);
          LODWORD(v263[0]) = DictionaryLayout::GetNumUsedSlots(v90);
          if ( LODWORD(v263[0]) )
          {
            v91 = 0;
            do
            {
              v92 = DacInstantiateTypeByAddressHelper(v87, 0x20u, 1, 1);
              LOBYTE(v93) = 1;
              v94 = DacGetTargetAddrForHostAddr(v92, v93) + 16;
              v95 = (int *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
              if ( *v95 >= 0 && (*(_BYTE *)v95 & 0x30) != 0 )
                LODWORD(v264) = *((unsigned __int16 *)DacInstantiateTypeByAddressHelper(
                                                        *((_QWORD *)v95 + 6) - 8LL,
                                                        8u,
                                                        1,
                                                        1)
                                + 3);
              else
                LODWORD(v264) = 0;
              v96 = DacInstantiateTypeByAddressHelper(v76, 8u, 1, 1);
              LOBYTE(v97) = 1;
              v98 = DacGetTargetAddrForHostAddr(v96, v97);
              v261 = v98 + 8LL * (v88 + (unsigned int)v264);
              v99 = DacInstantiateTypeByAddressHelper(v94 + v91, 0x10u, 1, 1);
              DictionaryEntryLayout::GetKind(v99);
              NativeImageDumper::DumpDictionaryEntry(this);
              ++v88;
              v91 += 16;
            }
            while ( v88 < LODWORD(v263[0]) );
            v4 = v265;
          }
        }
      }
      if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
      {
        (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 272LL))(
          *((_QWORD *)this + 17),
          "Total Per instance Info");
        if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
      }
    }
    if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
  }
  if ( (*((_BYTE *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1) + 8) & 4) == 0 )
  {
LABEL_154:
    if ( (*((_DWORD *)this + 102) & 0x100) == 0 )
      goto LABEL_195;
    DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
    DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
    v112 = (unsigned int)*((unsigned __int16 *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1) + 6) + 7;
    v113 = *((unsigned __int16 *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1) + 6) + 7;
    v114 = **((_QWORD **)this + 17);
    v115 = NativeImageDumper::DataPtrToDisplay(this, *v2 + 64);
    (*(void (__fastcall **)(_QWORD, const char *, __int64, _QWORD, unsigned __int64, unsigned __int64))(v114 + 408))(
      *((_QWORD *)this + 17),
      "Vtable",
      64,
      v113 & 0xFFFFFFF8,
      v115,
      v112 & 0xFFFFFFFFFFFFFFF8uLL);
    v116 = DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
    MethodTable::IterateVtableIndirectionSlots(v116, &v267);
    v117 = v268;
    v118 = v267;
    while ( 1 )
    {
      if ( v117 != -1 )
      {
        v118 += 8LL;
        v267 = v118;
      }
      v268 = ++v117;
      if ( v117 >= v269 )
        break;
      v119 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v118, 8u, 1, 1);
      NumSlots = MethodTable::VtableIndirectionSlotIterator::GetNumSlots((MethodTable::VtableIndirectionSlotIterator *)&v267);
      v261 = v119;
      v262 = NumSlots;
      SArray<NativeImageDumper::SlotChunk,1>::AppendEx((NativeImageDumper *)((char *)this + 440));
    }
    v123 = *((_DWORD *)this + 102);
    if ( (v123 & 0x40000) != 0 )
    {
      if ( v123 )
        (*(void (**)(_QWORD, const wchar_t *, ...))(**((_QWORD **)this + 17) + 280LL))(
          *((_QWORD *)this + 17),
          L"[%-4s]: %s (%s)");
      v124 = 0;
      if ( ((*((unsigned __int16 *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1) + 6) + 7) & 0xFFFFFFF8) != 0 )
      {
        do
        {
          if ( *((_DWORD *)this + 102) )
          {
            (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 88LL))(
              *((_QWORD *)this + 17),
              "Slot");
            if ( *((_DWORD *)this + 102) )
              (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 224LL))(
                *((_QWORD *)this + 17),
                "Index",
                v124);
          }
          v125 = DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
          LOBYTE(v126) = 1;
          v127 = DacGetTargetAddrForHostAddr(v125, v126);
          v128 = DacTAddrOffset(v127 + 64, v124, 8u);
          v129 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v128, 8u, 1, 1);
          if ( *((_DWORD *)this + 102) )
          {
            v130 = **((_QWORD **)this + 17);
            v131 = NativeImageDumper::DataPtrToDisplay(this, v129);
            (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64))(v130 + 168))(
              *((_QWORD *)this + 17),
              "Pointer",
              v131);
            if ( *((_DWORD *)this + 102) )
            {
              (*(void (__fastcall **)(_QWORD, const char *, const char *))(**((_QWORD **)this + 17) + 208LL))(
                *((_QWORD *)this + 17),
                "Type",
                "chunk indirection");
              if ( *((_DWORD *)this + 102) )
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 96LL))(*((_QWORD *)this + 17));
            }
          }
          ++v124;
        }
        while ( v124 < ((unsigned int)*((unsigned __int16 *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1) + 6) + 7) >> 3 );
      }
      if ( (*((_WORD *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1) + 4) & 0x4008) == 8 )
      {
        if ( *((_DWORD *)this + 102) )
        {
          (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 88LL))(
            *((_QWORD *)this + 17),
            "Slot");
          if ( *((_DWORD *)this + 102) )
            (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 224LL))(
              *((_QWORD *)this + 17),
              "Index",
              0xFFFFFFFFLL);
        }
        v132 = DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
        MethodTable::GetNonVirtualSlotsArray(v132, &v261);
        v133 = v261;
        if ( *((_DWORD *)this + 102) )
        {
          v134 = **((_QWORD **)this + 17);
          v135 = NativeImageDumper::DataPtrToDisplay(this, v261);
          (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64))(v134 + 168))(
            *((_QWORD *)this + 17),
            "Pointer",
            v135);
          if ( *((_DWORD *)this + 102) )
          {
            (*(void (__fastcall **)(_QWORD, const char *, const char *))(**((_QWORD **)this + 17) + 208LL))(
              *((_QWORD *)this + 17),
              "Type",
              "non-virtual chunk indirection");
            if ( *((_DWORD *)this + 102) )
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 96LL))(*((_QWORD *)this + 17));
          }
        }
        v136 = (MethodTable *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
        v137 = DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
        v261 = v133;
        v262 = MethodTable::GetNumVtableSlots(v136) - v137[6];
        SArray<NativeImageDumper::SlotChunk,1>::AppendEx((NativeImageDumper *)((char *)this + 440));
      }
      else if ( (*((_WORD *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1) + 4) & 0x4000) != 0 )
      {
        v138 = (unsigned __int16 *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
        v139 = DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
        MethodTable::GetSlotPtrRaw(v139, &v261, v138[6]);
        v140 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper(v261, 8u, 1, 1);
        NativeImageDumper::DumpSlot(this, 0xFFFFFFFF, *v140);
      }
      v141 = *((_DWORD *)this + 102) == 0;
      if ( !*((_DWORD *)this + 102) )
        goto LABEL_193;
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 288LL))(*((_QWORD *)this + 17));
    }
    else
    {
      if ( v123 < 0 )
      {
        DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
        v142 = (unsigned __int16 *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
        DacInstantiateTypeByAddressHelper(*v2 + 64, (v142[6] + 7) & 0xFFFFFFF8, 1, 1);
      }
      if ( (*((_WORD *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1) + 4) & 0x4008) == 8 )
      {
        v141 = *((_DWORD *)this + 102) == 0;
        if ( *((int *)this + 102) >= 0 )
          goto LABEL_193;
        v143 = (MethodTable *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
        v144 = DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
        LODWORD(v143) = MethodTable::GetNonVirtualSlotsArraySize(v143);
        NonVirtualSlotsArray = (unsigned __int64 *)MethodTable::GetNonVirtualSlotsArray(v144, &v261);
        DacInstantiateTypeByAddressHelper(*NonVirtualSlotsArray, (unsigned int)v143, 1, 1);
      }
    }
    v141 = *((_DWORD *)this + 102) == 0;
LABEL_193:
    v4 = v265;
    if ( !v141 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
    goto LABEL_195;
  }
  v100 = DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
  MethodTable::GetDispatchMap(v100, &v261);
  v101 = *((_DWORD *)this + 102);
  v102 = v261;
  if ( (v101 & 0x100) != 0 )
  {
    v103 = (DispatchMap *)DacInstantiateTypeByAddressHelper(v261, 1u, 1, 1);
    MapSize = DispatchMap::GetMapSize(v103);
    v105 = NativeImageDumper::DataPtrToDisplay(this, v102);
    (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, _QWORD))(**((_QWORD **)this + 17) + 392LL))(
      *((_QWORD *)this + 17),
      "DispatchMap",
      v105,
      MapSize + 1);
    v101 = *((_DWORD *)this + 102);
  }
  if ( (v101 & 0x40000) != 0 )
  {
    v106 = (struct MethodTable *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
    DispatchMap::EncodedMapIterator::EncodedMapIterator((DispatchMap::EncodedMapIterator *)&v270, v106);
    if ( (*((_DWORD *)this + 102) & 0x40000) != 0 )
      (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 264LL))(
        *((_QWORD *)this + 17),
        "DispatchMap",
        0);
    v107 = v275;
    v108 = v274;
    while ( v107 < v108 )
    {
      DispatchMap::EncodedMapIterator::Next((DispatchMap::EncodedMapIterator *)&v270);
      v107 = v275;
      v108 = v274;
      if ( v275 >= v274 )
        break;
      v109 = *((_DWORD *)this + 102);
      if ( (v109 & 0x100) != 0 )
      {
        (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 88LL))(
          *((_QWORD *)this + 17),
          "Entry");
        v109 = *((_DWORD *)this + 102);
        if ( (v109 & 0x100) != 0 )
        {
          (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 104LL))(
            *((_QWORD *)this + 17),
            "TypeID");
          v109 = *((_DWORD *)this + 102);
        }
      }
      v110 = v270;
      if ( v270 )
      {
        if ( (v109 & 0x100) != 0 )
        {
          (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 256LL))(
            *((_QWORD *)this + 17),
            "IsImplementedInterface",
            1);
          if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
            (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 224LL))(
              *((_QWORD *)this + 17),
              "GetInterfaceNum",
              (unsigned int)(v110 - 1));
        }
      }
      else if ( (v109 & 0x100) != 0 )
      {
        (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 256LL))(
          *((_QWORD *)this + 17),
          "IsThisClass",
          (unsigned int)(v270 + 1));
      }
      if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
      v111 = (unsigned __int16)v271;
      (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 224LL))(
        *((_QWORD *)this + 17),
        "SlotNumber",
        (unsigned __int16)v271);
      if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
        (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 224LL))(
          *((_QWORD *)this + 17),
          "TargetSlotNumber",
          v111);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 96LL))(*((_QWORD *)this + 17));
    }
    if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
      (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 272LL))(
        *((_QWORD *)this + 17),
        "Total Dispatch Map Entries");
  }
  else if ( v101 < 0 )
  {
    v121 = (DispatchMap *)DacInstantiateTypeByAddressHelper(v102, 1u, 1, 1);
    v122 = DispatchMap::GetMapSize(v121);
    DacInstantiateTypeByAddressHelper(v102, v122 + 1, 1, 1);
  }
  if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
    goto LABEL_154;
  }
LABEL_195:
  result = (__int64)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
  if ( *(_WORD *)(result + 14) && (*((_DWORD *)this + 102) & 0x100) != 0 )
  {
    v147 = *((_QWORD *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1) + 7);
    (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 296LL))(
      *((_QWORD *)this + 17),
      "InterfaceMap",
      56);
    v148 = 0;
    result = (__int64)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
    if ( *(_WORD *)(result + 14) )
    {
      do
      {
        v149 = DacTAddrOffset(v147, v148, 8u);
        if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
        {
          v150 = NativeImageDumper::DataPtrToDisplay(this, v149);
          (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, __int64))(**((_QWORD **)this + 17) + 392LL))(
            *((_QWORD *)this + 17),
            "InterfaceInfo_t",
            v150,
            8);
          if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
          {
            v151 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v149, 8u, 1, 1);
            if ( (v151 & 1) != 0 )
              v151 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v151 - 1, 8u, 1, 1);
            v261 = v151;
            NativeImageDumper::DoWriteFieldMethodTable(this, (__int64)&v261);
            if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
          }
        }
        ++v148;
        result = (__int64)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
      }
      while ( v148 < *(unsigned __int16 *)(result + 14) );
      v4 = v265;
    }
    if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
      result = (*(__int64 (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 272LL))(
                 *((_QWORD *)this + 17),
                 "Total InterfaceInfos");
  }
  if ( v260 )
  {
    v152 = *(_DWORD *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
    v153 = 0;
    if ( v152 >= 0 )
      v153 = v152 & 4;
    if ( v153 && (*((_DWORD *)this + 102) & 0x100) != 0 )
    {
      v154 = DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
      MethodTable::GetGenericsStaticsInfo(v154, &v261);
      v155 = v261;
      v156 = NativeImageDumper::DataPtrToDisplay(this, v261);
      v157 = DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
      (*(void (__fastcall **)(_QWORD, const char *, _QWORD, __int64, unsigned __int64, __int64))(**((_QWORD **)this + 17)
                                                                                               + 408LL))(
        *((_QWORD *)this + 17),
        "OptionalMember_GenericsStaticsInfo",
        *((unsigned __int8 *)&MethodTable::c_OptionalMembersStartOffsets + (v157[4] & 0x1F))
      + (((unsigned __int16)v157[6] + 7) & 0xFFFFFFF8),
        16,
        v156,
        16);
      v158 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v155, 0x10u, 1, 1);
      v159 = *((_DWORD *)this + 102);
      if ( v158 )
      {
        if ( v159 )
          (*(void (__fastcall **)(_QWORD, const char *, _QWORD, __int64, _QWORD))(**((_QWORD **)this + 17) + 296LL))(
            *((_QWORD *)this + 17),
            "m_pFieldDescs",
            0,
            8,
            0);
        v160 = 0;
        v161 = DacInstantiateTypeByAddressHelper(v4, 0x48u, 1, 1);
        if ( (unsigned __int16)EEClass::GetPackableField(v161, 2) )
        {
          do
          {
            v261 = v158 + 16LL * v160;
            NativeImageDumper::DumpFieldDesc(this);
            ++v160;
            v162 = DacInstantiateTypeByAddressHelper(v4, 0x48u, 1, 1);
          }
          while ( v160 < (unsigned __int16)EEClass::GetPackableField(v162, 2) );
        }
        if ( *((_DWORD *)this + 102) )
          (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 272LL))(
            *((_QWORD *)this + 17),
            "Total Static Fields");
      }
      else if ( v159 )
      {
        (*(void (__fastcall **)(_QWORD, const char *, _QWORD, __int64, _QWORD))(**((_QWORD **)this + 17) + 320LL))(
          *((_QWORD *)this + 17),
          "m_pFieldDescs",
          0,
          8,
          0);
      }
      v163 = *((_DWORD *)this + 102);
      if ( (v163 & 0x100) != 0 )
      {
        v164 = DacInstantiateTypeByAddressHelper(v155, 0x10u, 1, 1);
        (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(**((_QWORD **)this + 17) + 344LL))(
          *((_QWORD *)this + 17),
          "m_DynamicTypeID",
          8,
          8,
          v164[2]);
        v163 = *((_DWORD *)this + 102);
      }
      if ( (v163 & 0x100) != 0 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
    }
    v165 = (MethodTable *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
    if ( (unsigned int)MethodTable::HasGuidInfo(v165) )
    {
      if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
      {
        v166 = DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
        GuidInfoPtr = (unsigned __int64 *)MethodTable::GetGuidInfoPtr(v166, &v261);
        v168 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper(*GuidInfoPtr, 8u, 1, 1);
        v169 = *v168;
        if ( *v168 )
        {
          v170 = NativeImageDumper::DataPtrToDisplay(this, *v168);
          v171 = DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
          v172 = (((unsigned __int16)v171[6] + 7) & 0xFFFFFFF8)
               + *((unsigned __int8 *)&MethodTable::c_OptionalMembersStartOffsets + (v171[4] & 0x1F));
          v173 = 0;
          if ( *(int *)v171 >= 0 )
            v173 = *(_DWORD *)v171 & 4;
          v174 = v172 + 16;
          if ( !v173 )
            v174 = v172;
          (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, __int64))(**((_QWORD **)this + 17) + 408LL))(
            *((_QWORD *)this + 17),
            "OptionalMember_GuidInfo",
            v174,
            8,
            v170,
            20);
          v270 = 2;
          v271 = 128;
          lpMem = v273;
          v273[0] = 0;
          v175 = (struct _GUID *)DacInstantiateTypeByAddressHelper(v169, 0x14u, 1, 1);
          GuidToString(v175, (struct SString *)&v270);
          if ( *((_DWORD *)this + 102) )
          {
            SString::ConvertToUnicode((SString *)&v270);
            (*(void (__fastcall **)(_QWORD, const char *, _QWORD, __int64, LPVOID))(**((_QWORD **)this + 17) + 312LL))(
              *((_QWORD *)this + 17),
              "m_Guid",
              0,
              16,
              lpMem);
            if ( *((_DWORD *)this + 102) )
            {
              v176 = DacInstantiateTypeByAddressHelper(v169, 0x14u, 1, 1);
              (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(**((_QWORD **)this + 17) + 368LL))(
                *((_QWORD *)this + 17),
                "m_bGeneratedFromName",
                16,
                4,
                v176[4]);
              if ( *((_DWORD *)this + 102) )
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
            }
          }
          if ( (v271 & 0x800000000LL) != 0 )
            operator delete(lpMem);
        }
      }
    }
    if ( (*((_WORD *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1) + 4) & 0x800) != 0
      && (*((_DWORD *)this + 102) & 0x100) != 0 )
    {
      v177 = (MethodTable *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
      LOBYTE(v178) = 1;
      v179 = DacGetTargetAddrForHostAddr(v177, v178);
      v180 = 0;
      if ( *(int *)v177 >= 0 )
        v180 = *(_DWORD *)v177 & 4;
      v181 = ((*((unsigned __int16 *)v177 + 6) + 7) & 0xFFFFFFF8)
           + *((unsigned __int8 *)&MethodTable::c_OptionalMembersStartOffsets + (*((_WORD *)v177 + 4) & 0x1F))
           + 16;
      if ( !v180 )
        v181 = ((*((unsigned __int16 *)v177 + 6) + 7) & 0xFFFFFFF8)
             + *((unsigned __int8 *)&MethodTable::c_OptionalMembersStartOffsets + (*((_WORD *)v177 + 4) & 0x1F));
      if ( (unsigned int)MethodTable::HasGuidInfo(v177) )
        v181 += 8;
      v182 = v181 + 8;
      if ( (*(_DWORD *)v177 & 0x4000000) == 0 )
        v182 = v181;
      v183 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper(v179 + v182, 8u, 1, 1);
      v184 = NativeImageDumper::DataPtrToDisplay(this, *v183);
      v185 = (MethodTable *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
      v186 = 0;
      if ( *(int *)v185 >= 0 )
        v186 = *(_DWORD *)v185 & 4;
      v187 = ((*((unsigned __int16 *)v185 + 6) + 7) & 0xFFFFFFF8)
           + *((unsigned __int8 *)&MethodTable::c_OptionalMembersStartOffsets + (*((_WORD *)v185 + 4) & 0x1F))
           + 16;
      if ( !v186 )
        v187 = ((*((unsigned __int16 *)v185 + 6) + 7) & 0xFFFFFFF8)
             + *((unsigned __int8 *)&MethodTable::c_OptionalMembersStartOffsets + (*((_WORD *)v185 + 4) & 0x1F));
      if ( (unsigned int)MethodTable::HasGuidInfo(v185) )
        v187 += 8;
      v188 = v187 + 8;
      if ( (*(_DWORD *)v185 & 0x4000000) == 0 )
        v188 = v187;
      (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64))(**((_QWORD **)this + 17) + 320LL))(
        *((_QWORD *)this + 17),
        "OptionalMember_CCWTemplate",
        v188,
        8,
        v184);
    }
    if ( (*(_DWORD *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1) & 0x400000) != 0
      && (*((_DWORD *)this + 102) & 0x100) != 0 )
    {
      v261 = *v2;
      v189 = DacInstantiateTypeByAddressHelper(v4, 0x48u, 1, 1);
      PackableField = EEClass::GetPackableField(v189, 2);
      v191 = NativeImageDumper::CountFields(this, &v261) - PackableField;
      v192 = (MethodTable *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
      LOBYTE(v193) = 1;
      v194 = DacGetTargetAddrForHostAddr(v192, v193);
      v195 = 0;
      if ( *(int *)v192 >= 0 )
        v195 = *(_DWORD *)v192 & 4;
      v196 = ((*((unsigned __int16 *)v192 + 6) + 7) & 0xFFFFFFF8)
           + *((unsigned __int8 *)&MethodTable::c_OptionalMembersStartOffsets + (*((_WORD *)v192 + 4) & 0x1F))
           + 16;
      if ( !v195 )
        v196 = ((*((unsigned __int16 *)v192 + 6) + 7) & 0xFFFFFFF8)
             + *((unsigned __int8 *)&MethodTable::c_OptionalMembersStartOffsets + (*((_WORD *)v192 + 4) & 0x1F));
      if ( (unsigned int)MethodTable::HasGuidInfo(v192) )
        v196 += 8;
      v197 = v196 + 8;
      if ( (*(_DWORD *)v192 & 0x4000000) == 0 )
        v197 = v196;
      v198 = v197 + 8;
      if ( (*((_WORD *)v192 + 4) & 0x800) == 0 )
        v198 = v197;
      v199 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v194 + v198, 8u, 1, 1);
      v200 = (unsigned int)(2 * v191 + 7) >> 3;
      v201 = NativeImageDumper::DataPtrToDisplay(this, v199);
      v202 = (MethodTable *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
      v203 = 0;
      if ( *(int *)v202 >= 0 )
        v203 = *(_DWORD *)v202 & 4;
      v204 = ((*((unsigned __int16 *)v202 + 6) + 7) & 0xFFFFFFF8)
           + *((unsigned __int8 *)&MethodTable::c_OptionalMembersStartOffsets + (*((_WORD *)v202 + 4) & 0x1F))
           + 16;
      if ( !v203 )
        v204 = ((*((unsigned __int16 *)v202 + 6) + 7) & 0xFFFFFFF8)
             + *((unsigned __int8 *)&MethodTable::c_OptionalMembersStartOffsets + (*((_WORD *)v202 + 4) & 0x1F));
      if ( (unsigned int)MethodTable::HasGuidInfo(v202) )
        v204 += 8;
      v205 = v204 + 8;
      if ( (*(_DWORD *)v202 & 0x4000000) == 0 )
        v205 = v204;
      v206 = *((_QWORD *)this + 17);
      v207 = (v200 + 3) & 0xFFFFFFFC;
      LODWORD(v263[0]) = v207;
      v208 = v205 + 8;
      if ( (*((_WORD *)v202 + 4) & 0x800) == 0 )
        v208 = v205;
      (*(void (__fastcall **)(__int64, const char *, __int64, __int64, unsigned __int64, _QWORD))(*(_QWORD *)v206 + 408LL))(
        v206,
        "OptionalMember_RemotingVtsInfo",
        v208,
        8,
        v201,
        v207 + 32);
      if ( *((_DWORD *)this + 102) )
        (*(void (**)(_QWORD, const char *, _QWORD, __int64, const wchar_t *, ...))(**((_QWORD **)this + 17) + 296LL))(
          *((_QWORD *)this + 17),
          "m_pCallbacks",
          0,
          32,
          L"%-30s: %s");
      v209 = 0;
      v210 = 0;
      do
      {
        v211 = *(_QWORD *)((char *)DacInstantiateTypeByAddressHelper(v199, 0x28u, 1, 1) + v210 * 8);
        if ( (v211 & 1) != 0 )
          v211 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v211 - 1, 8u, 1, 1);
        if ( *((_DWORD *)this + 102) )
        {
          (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 88LL))(
            *((_QWORD *)this + 17),
            "Callback");
          if ( *((_DWORD *)this + 102) )
            (*(void (__fastcall **)(_QWORD, const char *, const char * near *))(**((_QWORD **)this + 17) + 208LL))(
              *((_QWORD *)this + 17),
              "CallbackType",
              (&s_VTSCallbackNames)[v210]);
        }
        v261 = v211;
        if ( (v211 & 1) != 0 )
          NativeImageDumper::DoWriteFieldMethodDesc(this, (__int64)&v261);
        else
          NativeImageDumper::WriteElementMethodDesc(this);
        v212 = *((_DWORD *)this + 102);
        if ( v212 )
        {
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 96LL))(*((_QWORD *)this + 17));
          v212 = *((_DWORD *)this + 102);
        }
        ++v209;
        ++v210;
      }
      while ( v209 < 4 );
      v2 = v266;
      v213 = v263[0];
      if ( v212 )
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 17) + 272LL))(*((_QWORD *)this + 17), 0);
      (*(void (__fastcall **)(_QWORD, const char *, __int64, _QWORD))(**((_QWORD **)this + 17) + 360LL))(
        *((_QWORD *)this + 17),
        "m_rFieldTypes",
        32,
        v213);
      if ( *((_DWORD *)this + 102) )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
    }
    v214 = (MethodTable *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
    if ( (unsigned int)MethodTable::HasRemotableMethodInfo(v214) && (*((_DWORD *)this + 102) & 0x100) != 0 )
    {
      v215 = (MethodTable *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
      LOBYTE(v216) = 1;
      v217 = DacGetTargetAddrForHostAddr(v215, v216);
      v218 = 0;
      if ( *(int *)v215 >= 0 )
        v218 = *(_DWORD *)v215 & 4;
      v219 = ((*((unsigned __int16 *)v215 + 6) + 7) & 0xFFFFFFF8)
           + *((unsigned __int8 *)&MethodTable::c_OptionalMembersStartOffsets + (*((_WORD *)v215 + 4) & 0x1F))
           + 16;
      if ( !v218 )
        v219 = ((*((unsigned __int16 *)v215 + 6) + 7) & 0xFFFFFFF8)
             + *((unsigned __int8 *)&MethodTable::c_OptionalMembersStartOffsets + (*((_WORD *)v215 + 4) & 0x1F));
      if ( (unsigned int)MethodTable::HasGuidInfo(v215) )
        v219 += 8;
      v220 = v219 + 8;
      if ( (*(_DWORD *)v215 & 0x4000000) == 0 )
        v220 = v219;
      v221 = v220 + 8;
      if ( (*((_WORD *)v215 + 4) & 0x800) == 0 )
        v221 = v220;
      v222 = v221 + 8;
      if ( (*(_DWORD *)v215 & 0x400000) == 0 )
        v222 = v221;
      v223 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v217 + v222, 8u, 1, 1);
      if ( v223 )
      {
        v224 = (MethodTable *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
        v225 = 4 * MethodTable::GetNumVtableSlots(v224);
        v226 = NativeImageDumper::DataPtrToDisplay(this, v223);
        v227 = (MethodTable *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
        v228 = 0;
        if ( *(int *)v227 >= 0 )
          v228 = *(_DWORD *)v227 & 4;
        v229 = ((*((unsigned __int16 *)v227 + 6) + 7) & 0xFFFFFFF8)
             + *((unsigned __int8 *)&MethodTable::c_OptionalMembersStartOffsets + (*((_WORD *)v227 + 4) & 0x1F))
             + 16;
        if ( !v228 )
          v229 = ((*((unsigned __int16 *)v227 + 6) + 7) & 0xFFFFFFF8)
               + *((unsigned __int8 *)&MethodTable::c_OptionalMembersStartOffsets + (*((_WORD *)v227 + 4) & 0x1F));
        if ( (unsigned int)MethodTable::HasGuidInfo(v227) )
          v229 += 8;
        v230 = v229 + 8;
        if ( (*(_DWORD *)v227 & 0x4000000) == 0 )
          v230 = v229;
        v231 = v230 + 8;
        if ( (*((_WORD *)v227 + 4) & 0x800) == 0 )
          v231 = v230;
        v232 = v231 + 8;
        if ( (*(_DWORD *)v227 & 0x400000) == 0 )
          v232 = v231;
        (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, _QWORD))(**((_QWORD **)this + 17)
                                                                                                 + 408LL))(
          *((_QWORD *)this + 17),
          "OptionalMember_RemotableMethodInfo",
          v232,
          8,
          v226,
          v225);
        v233 = (MethodTable *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
        v234 = **((_QWORD **)this + 17);
        NumVtableSlots = MethodTable::GetNumVtableSlots(v233);
        (*(void (__fastcall **)(_QWORD, const char *, _QWORD, _QWORD, _QWORD))(v234 + 296))(
          *((_QWORD *)this + 17),
          "m_rmi",
          0,
          4 * (unsigned int)NumVtableSlots,
          0);
        v236 = DacInstantiateTypeByAddressHelper(v223, 4u, 1, 1);
        LOBYTE(v237) = 1;
        v238 = DacGetTargetAddrForHostAddr(v236, v237);
        v239 = 0;
        v240 = (MethodTable *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
        if ( MethodTable::GetNumVtableSlots(v240) )
        {
          do
          {
            v241 = DacTAddrOffset(v238, v239, 4u);
            if ( *((_DWORD *)this + 102) )
            {
              v242 = NativeImageDumper::DataPtrToDisplay(this, v241);
              (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, __int64))(**((_QWORD **)this + 17) + 392LL))(
                *((_QWORD *)this + 17),
                "RemotableMethodInfo",
                v242,
                4);
              if ( *((_DWORD *)this + 102) )
              {
                v271 = 128;
                lpMem = v273;
                v270 = 2;
                v273[0] = 0;
                v243 = (unsigned int *)DacInstantiateTypeByAddressHelper(v241, 4u, 1, 1);
                EnumFlagsToString(
                  *v243,
                  (const struct NativeImageDumper::EnumMnemonics *)&s_XADOptFlags,
                  9,
                  L", ",
                  (struct SString *)&v270);
                SString::ConvertToUnicode((SString *)&v270);
                v244 = lpMem;
                v245 = DacInstantiateTypeByAddressHelper(v241, 4u, 1, 1);
                (*(void (__fastcall **)(_QWORD, const char *, _QWORD, __int64, _DWORD, LPVOID))(**((_QWORD **)this + 17)
                                                                                              + 352LL))(
                  *((_QWORD *)this + 17),
                  "m_OptFlags",
                  0,
                  4,
                  *v245,
                  v244);
                if ( (v271 & 0x800000000LL) != 0 )
                  operator delete(lpMem);
              }
            }
            if ( *((_DWORD *)this + 102) )
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
            ++v239;
            v246 = (MethodTable *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
          }
          while ( v239 < MethodTable::GetNumVtableSlots(v246) );
        }
        if ( *((_DWORD *)this + 102) )
        {
          (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 272LL))(
            *((_QWORD *)this + 17),
            "Total RemotableMethodInfos");
          if ( *((_DWORD *)this + 102) )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
        }
      }
      else
      {
        (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 168LL))(
          *((_QWORD *)this + 17),
          "OptionalMember_RemotableMethodInfo",
          0);
      }
    }
    v247 = *(_DWORD *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
    result = 0;
    if ( v247 >= 0 )
      result = v247 & 0x40;
    if ( (_DWORD)result )
    {
      if ( (*((_DWORD *)this + 102) & 0x100) == 0 )
        return result;
      v248 = (MethodTable *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
      ContextStaticsBucketPtr = (unsigned __int64 *)MethodTable::GetContextStaticsBucketPtr(v248);
      v250 = *(_QWORD *)DacInstantiateTypeByAddressHelper(*ContextStaticsBucketPtr, 8u, 1, 1);
      v251 = NativeImageDumper::DataPtrToDisplay(this, v250);
      v252 = (MethodTable *)DacInstantiateTypeByAddressHelper(*v2, 0x40u, 1, 1);
      v253 = 0;
      if ( *(int *)v252 >= 0 )
        v253 = *(_DWORD *)v252 & 4;
      v254 = ((*((unsigned __int16 *)v252 + 6) + 7) & 0xFFFFFFF8)
           + *((unsigned __int8 *)&MethodTable::c_OptionalMembersStartOffsets + (*((_WORD *)v252 + 4) & 0x1F))
           + 16;
      if ( !v253 )
        v254 = ((*((unsigned __int16 *)v252 + 6) + 7) & 0xFFFFFFF8)
             + *((unsigned __int8 *)&MethodTable::c_OptionalMembersStartOffsets + (*((_WORD *)v252 + 4) & 0x1F));
      if ( (unsigned int)MethodTable::HasGuidInfo(v252) )
        v254 += 8;
      v255 = v254 + 8;
      if ( (*(_DWORD *)v252 & 0x4000000) == 0 )
        v255 = v254;
      v256 = v255 + 8;
      if ( (*((_WORD *)v252 + 4) & 0x800) == 0 )
        v256 = v255;
      v257 = v256 + 8;
      if ( (*(_DWORD *)v252 & 0x400000) == 0 )
        v257 = v256;
      if ( (unsigned int)MethodTable::HasRemotableMethodInfo(v252) )
        v257 += 8;
      (*(void (__fastcall **)(_QWORD, const char *, _QWORD, __int64, unsigned __int64, __int64))(**((_QWORD **)this + 17)
                                                                                               + 408LL))(
        *((_QWORD *)this + 17),
        "OptionalMember_ContextStatics",
        v257,
        8,
        v251,
        8);
      result = *((unsigned int *)this + 102);
      if ( (_DWORD)result )
      {
        v258 = DacInstantiateTypeByAddressHelper(v250, 8u, 1, 1);
        (*(void (__fastcall **)(_QWORD, const char *, _QWORD, __int64, _DWORD))(**((_QWORD **)this + 17) + 336LL))(
          *((_QWORD *)this + 17),
          "m_dwContextStaticsOffset",
          0,
          4,
          *v258);
        result = *((unsigned int *)this + 102);
        if ( (_DWORD)result )
        {
          v259 = (unsigned __int16 *)DacInstantiateTypeByAddressHelper(v250, 8u, 1, 1);
          result = (*(__int64 (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(**((_QWORD **)this + 17)
                                                                                             + 336LL))(
                     *((_QWORD *)this + 17),
                     "m_wContextStaticsSize",
                     4,
                     2,
                     v259[2]);
          if ( *((_DWORD *)this + 102) )
            result = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
        }
      }
    }
  }
  if ( (*((_DWORD *)this + 102) & 0x100) != 0 )
    return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
  return result;
}

```

## disassembly

```asm
0x1800564c8  mov     [rsp-8+arg_10], rbx
0x1800564cd  push    rbp
0x1800564ce  push    rsi
0x1800564cf  push    rdi
0x1800564d0  push    r12
0x1800564d2  push    r13
0x1800564d4  push    r14
0x1800564d6  push    r15
0x1800564d8  lea     rbp, [rsp-50h]
0x1800564dd  sub     rsp, 150h
0x1800564e4  mov     rax, cs:__security_cookie
0x1800564eb  xor     rax, rsp
0x1800564ee  mov     [rbp+80h+var_40], rax
0x1800564f2  mov     r15, rdx
0x1800564f5  mov     [rsp+180h+var_108], rdx
0x1800564fa  mov     r13, rcx
0x1800564fd  xor     edi, edi
0x1800564ff  mov     r14d, edi
0x180056502  mov     [rsp+180h+var_110], rdi
0x180056507  mov     r9b, 1; bool
0x18005650a  mov     r8b, r9b; bool
0x18005650d  lea     ebx, [rdi+40h]
0x180056510  mov     edx, ebx; unsigned int
0x180056512  mov     rcx, [r15]; unsigned __int64
0x180056515  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005651a  lea     esi, [rdi+8]
0x18005651d  test    byte ptr [rax+28h], 3
0x180056521  jz      loc_180056618
0x180056527  mov     r9b, 1; bool
0x18005652a  mov     r8b, r9b; bool
0x18005652d  mov     edx, ebx; unsigned int
0x18005652f  mov     rcx, [r15]; unsigned __int64
0x180056532  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180056537  mov     rcx, [rax+28h]
0x18005653b  test    cl, 2
0x18005653e  jnz     short loc_18005654C
0x180056540  mov     dl, 1
0x180056542  mov     rcx, rax
0x180056545  call    DacGetTargetAddrForHostAddr
0x18005654a  jmp     short loc_18005656B
0x18005654c  test    cl, 1
0x18005654f  jz      short loc_180056567
0x180056551  add     rcx, 0FFFFFFFFFFFFFFFDh; unsigned __int64
0x180056555  mov     r9b, 1; bool
0x180056558  mov     r8b, r9b; bool
0x18005655b  mov     edx, esi; unsigned int
0x18005655d  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180056562  mov     rax, [rax]
0x180056565  jmp     short loc_18005656B
0x180056567  lea     rax, [rcx-2]
0x18005656b  test    al, 1
0x18005656d  jz      loc_180056618
0x180056573  mov     [rsp+180h+var_140], dil
0x180056578  mov     [rbp+80h+var_E0], rdi
0x18005657c  mov     [rbp+80h+var_E0+4], 80h
0x180056584  mov     [rbp+80h+lpMem], rdi
0x180056588  lea     rax, [rbp+80h+var_C8]
0x18005658c  mov     [rbp+80h+lpMem], rax
0x180056590  mov     dword ptr [rbp+80h+var_E0], 2
0x180056597  mov     rax, [rbp+80h+lpMem]
0x18005659b  mov     [rax], di
0x18005659e  mov     rax, [r15]
0x1800565a1  mov     [rsp+180h+var_128], rax
0x1800565a6  lea     r8, [rbp+80h+var_E0]
0x1800565aa  lea     rdx, [rsp+180h+var_128]
0x1800565af  mov     rcx, r13; this
0x1800565b2  call    ?MethodTableToString@NativeImageDumper@@QEAAXV?$__DPtr@VMethodTable@@@@AEAVSString@@@Z; NativeImageDumper::MethodTableToString(__DPtr<MethodTable>,SString &)
0x1800565b7  lea     rcx, [rbp+80h+var_E0]; this
0x1800565bb  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1800565c0  mov     rcx, [r13+88h]
0x1800565c7  mov     rax, [rcx]
0x1800565ca  mov     r8, [rbp+80h+lpMem]
0x1800565ce  lea     rdx, aWarningMethodt; "WARNING! MethodTable %S is generic but "...
0x1800565d5  mov     rax, [rax+18h]
0x1800565d9  call    cs:__guard_dispatch_icall_fptr
0x1800565df  nop
0x1800565e0  test    [rbp+80h+var_D8], sil
0x1800565e4  jz      short loc_180056626
0x1800565e6  mov     rbx, [rbp+80h+lpMem]
0x1800565ea  test    rbx, rbx
0x1800565ed  jz      short loc_180056626
0x1800565ef  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800565f6  test    rax, rax
0x1800565f9  jnz     short loc_180056608
0x1800565fb  call    cs:__imp_GetProcessHeap
0x180056601  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180056608  mov     r8, rbx; lpMem
0x18005660b  xor     edx, edx; dwFlags
0x18005660d  mov     rcx, rax; hHeap
0x180056610  call    cs:__imp_HeapFree
0x180056616  jmp     short loc_180056626
0x180056618  cmp     [r13+220h], dil
0x18005661f  jnz     short loc_180056635
0x180056621  mov     [rsp+180h+var_140], dil
0x180056626  mov     rsi, [r15]
0x180056629  lea     r12, [rsi+40h]
0x18005662d  mov     rdx, rsi
0x180056630  jmp     loc_1800566BD
0x180056635  mov     r9b, 1; bool
0x180056638  mov     r8b, r9b; bool
0x18005663b  mov     edx, ebx; unsigned int
0x18005663d  mov     rcx, [r15]; unsigned __int64
0x180056640  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180056645  mov     rcx, rax; this
0x180056648  lea     r8, [rsp+180h+var_128]; unsigned __int64 *
0x18005664d  lea     rdx, [rsp+180h+var_118]; unsigned __int64 *
0x180056652  call    ?GetSavedExtent@MethodTable@@QEAAXPEA_K0@Z; MethodTable::GetSavedExtent(unsigned __int64 *,unsigned __int64 *)
0x180056657  mov     r9b, 1; bool
0x18005665a  mov     r8b, r9b; bool
0x18005665d  mov     edx, ebx; unsigned int
0x18005665f  mov     rcx, [r15]; unsigned __int64
0x180056662  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180056667  mov     r14, [rax+28h]
0x18005666b  mov     [rsp+180h+var_110], r14
0x180056670  test    r14b, 2
0x180056674  jz      short loc_1800566AB
0x180056676  mov     r9b, 1; bool
0x180056679  mov     r8b, r9b; bool
0x18005667c  test    r9b, r14b
0x18005667f  jz      short loc_180056697
0x180056681  lea     rcx, [r14-3]; unsigned __int64
0x180056685  mov     edx, esi; unsigned int
0x180056687  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005668c  mov     r9b, 1
0x18005668f  mov     r8b, r9b
0x180056692  mov     rcx, [rax]
0x180056695  jmp     short loc_18005669B
0x180056697  lea     rcx, [r14-2]; unsigned __int64
0x18005669b  mov     edx, ebx; unsigned int
0x18005669d  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800566a2  mov     r14, [rax+28h]
0x1800566a6  mov     [rsp+180h+var_110], r14
0x1800566ab  mov     rdx, [r15]; unsigned __int64
0x1800566ae  mov     [rsp+180h+var_140], 1
0x1800566b3  mov     r12, [rsp+180h+var_128]
0x1800566b8  mov     rsi, [rsp+180h+var_118]
0x1800566bd  mov     eax, [r13+198h]
0x1800566c4  mov     edi, 100h
0x1800566c9  test    edi, eax
0x1800566cb  jz      loc_180056890
0x1800566d1  mov     rcx, r13; this
0x1800566d4  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z; NativeImageDumper::DataPtrToDisplay(unsigned __int64)
0x1800566d9  mov     rdi, rax
0x1800566dc  mov     rcx, [r13+88h]
0x1800566e3  mov     rbx, [rcx]
0x1800566e6  sub     r12, rsi
0x1800566e9  mov     rdx, rsi; unsigned __int64
0x1800566ec  mov     rcx, r13; this
0x1800566ef  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z; NativeImageDumper::DataPtrToDisplay(unsigned __int64)
0x1800566f4  mov     r9, rax
0x1800566f7  mov     [rsp+180h+var_160], r12
0x1800566fc  mov     r8, rdi
0x1800566ff  lea     rdx, aMethodtable; "MethodTable"
0x180056706  mov     rcx, [r13+88h]
0x18005670d  mov     rax, [rbx+190h]
0x180056714  call    cs:__guard_dispatch_icall_fptr
0x18005671a  mov     eax, [r13+198h]
0x180056721  mov     edi, 100h
0x180056726  test    edi, eax
0x180056728  jz      loc_180056890
0x18005672e  xor     r12d, r12d
0x180056731  mov     [rbp+80h+var_E0], r12
0x180056735  mov     [rbp+80h+var_E0+4], 80h
0x18005673d  mov     [rbp+80h+lpMem], r12
0x180056741  lea     rax, [rbp+80h+var_C8]
0x180056745  mov     [rbp+80h+lpMem], rax
0x180056749  mov     dword ptr [rbp+80h+var_E0], 2
0x180056750  mov     rax, [rbp+80h+lpMem]
0x180056754  mov     [rax], r12w
0x180056758  mov     rax, [r15]
0x18005675b  mov     [rsp+180h+var_128], rax
0x180056760  lea     r8, [rbp+80h+var_E0]
0x180056764  lea     rdx, [rsp+180h+var_128]
0x180056769  mov     rcx, r13; this
0x18005676c  call    ?MethodTableToString@NativeImageDumper@@QEAAXV?$__DPtr@VMethodTable@@@@AEAVSString@@@Z; NativeImageDumper::MethodTableToString(__DPtr<MethodTable>,SString &)
0x180056771  cmp     [r13+198h], r12d
0x180056778  jz      short loc_1800567A6
0x18005677a  lea     rcx, [rbp+80h+var_E0]; this
0x18005677e  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180056783  mov     rcx, [r13+88h]
0x18005678a  mov     rax, [rcx]
0x18005678d  mov     r8, [rbp+80h+lpMem]
0x180056791  lea     rdx, aName_0; "Name"
0x180056798  mov     rax, [rax+0D8h]
0x18005679f  call    cs:__guard_dispatch_icall_fptr
0x1800567a5  nop
0x1800567a6  mov     ebx, 8
0x1800567ab  test    [rbp+80h+var_D8], bl
0x1800567ae  jz      short loc_1800567E5
0x1800567b0  mov     rbx, [rbp+80h+lpMem]
0x1800567b4  test    rbx, rbx
0x1800567b7  jz      short loc_1800567E0
0x1800567b9  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800567c0  test    rax, rax
0x1800567c3  jnz     short loc_1800567D2
0x1800567c5  call    cs:__imp_GetProcessHeap
0x1800567cb  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800567d2  mov     r8, rbx; lpMem
0x1800567d5  xor     edx, edx; dwFlags
0x1800567d7  mov     rcx, rax; hHeap
0x1800567da  call    cs:__imp_HeapFree
0x1800567e0  mov     ebx, 8
0x1800567e5  mov     r9b, 1; bool
0x1800567e8  mov     r8b, r9b; bool
0x1800567eb  mov     esi, 40h ; '@'
0x1800567f0  mov     edx, esi; unsigned int
0x1800567f2  mov     rcx, [r15]; unsigned __int64
0x1800567f5  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800567fa  test    dword ptr [rax], 1000000h
0x180056800  jz      loc_180056898
0x180056806  mov     r9b, 1; bool
0x180056809  mov     r8b, r9b; bool
0x18005680c  mov     edx, esi; unsigned int
0x18005680e  mov     rcx, [r15]; unsigned __int64
0x180056811  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180056816  mov     dl, 1
0x180056818  mov     rcx, rax
0x18005681b  call    DacGetTargetAddrForHostAddr
0x180056820  mov     r9b, 1; bool
0x180056823  mov     r8b, r9b; bool
0x180056826  lea     edx, [rsi-3Fh]; unsigned int
0x180056829  mov     rcx, rax; unsigned __int64
0x18005682c  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180056831  mov     dl, 1
0x180056833  mov     rcx, rax
0x180056836  call    DacGetTargetAddrForHostAddr
0x18005683b  lea     rcx, [rax-8]; unsigned __int64
0x18005683f  mov     r9b, 1; bool
0x180056842  mov     r8b, r9b; bool
0x180056845  mov     edx, ebx; unsigned int
0x180056847  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18005684c  cmp     [rax], r12
0x18005684f  jge     short loc_18005685D
0x180056851  lea     edx, [rsi-3Eh]
0x180056854  sub     rdx, [rax]
0x180056857  shl     rdx, 3
0x18005685b  jmp     short loc_180056867
0x18005685d  mov     rdx, [rax]
0x180056860  shl     rdx, 4
0x180056864  add     rdx, rbx
0x180056867  mov     rcx, [r13+88h]
0x18005686e  mov     rax, [rcx]
0x180056871  mov     r8d, edx
0x180056874  neg     r8d
0x180056877  mov     r9d, edx
0x18005687a  lea     rdx, aCgcdesc; "CGCDesc"
0x180056881  mov     rax, [rax+168h]
0x180056888  call    cs:__guard_dispatch_icall_fptr
0x18005688e  jmp     short loc_180056898
0x180056890  xor     r12d, r12d
0x180056893  lea     esi, [r12+40h]
0x180056898  mov     r9b, 1; bool
0x18005689b  mov     r8b, r9b; bool
0x18005689e  mov     edx, esi; unsigned int
0x1800568a0  mov     rcx, [r15]; unsigned __int64
0x1800568a3  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800568a8  mov     ecx, [r13+198h]
0x1800568af  and     ecx, edi
0x1800568b1  cmp     [rax], r12d
0x1800568b4  jge     short loc_1800568F5
0x1800568b6  test    ecx, ecx
0x1800568b8  jz      loc_1800569E7
0x1800568be  mov     r9b, 1; bool
0x1800568c1  mov     r8b, r9b; bool
0x1800568c4  mov     edx, esi; unsigned int
0x1800568c6  mov     rcx, [r15]; unsigned __int64
0x1800568c9  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x1800568ce  mov     rcx, [r13+88h]
0x1800568d5  mov     rdx, [rcx]
0x1800568d8  movzx   r8d, word ptr [rax]
0x1800568dc  mov     rax, [rdx+0E0h]
0x1800568e3  lea     rdx, aComponentsize; "ComponentSize"
0x1800568ea  call    cs:__guard_dispatch_icall_fptr
0x1800568f0  jmp     loc_1800569E7
0x1800568f5  test    ecx, ecx
0x1800568f7  jz      loc_1800569E7
0x1800568fd  and     [rbp+80h+var_E0], 0
0x180056902  mov     [rbp+80h+var_E0+4], 80h
0x18005690a  mov     [rbp+80h+lpMem], r12
0x18005690e  lea     rax, [rbp+80h+var_C8]
0x180056912  mov     [rbp+80h+lpMem], rax
0x180056916  mov     dword ptr [rbp+80h+var_E0], 2
0x18005691d  mov     rax, [rbp+80h+lpMem]
0x180056921  mov     [rax], r12w
0x180056925  mov     r9b, 1; bool
0x180056928  mov     r8b, r9b; bool
0x18005692b  mov     edx, esi; unsigned int
0x18005692d  mov     rcx, [r15]; unsigned __int64
0x180056930  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180056935  movzx   ecx, word ptr [rax]; unsigned int
0x180056938  lea     rax, [rbp+80h+var_E0]
0x18005693c  mov     [rsp+180h+var_160], rax; struct SString *
0x180056941  lea     r9, asc_180137070; ", "
0x180056948  mov     r8d, 15h; int
0x18005694e  lea     rdx, ?s_MTFlagsLow@@3PAUEnumMnemonics@NativeImageDumper@@A; struct NativeImageDumper::EnumMnemonics *
0x180056955  call    ?EnumFlagsToString@@YAXKPEBUEnumMnemonics@NativeImageDumper@@HPEBGAEAVSString@@@Z; EnumFlagsToString(ulong,NativeImageDumper::EnumMnemonics const *,int,ushort const *,SString &)
0x18005695a  lea     rcx, [rbp+80h+var_E0]; this
0x18005695e  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180056963  mov     rbx, [rbp+80h+lpMem]
0x180056967  mov     r9b, 1; bool
  ... truncated ...
```
