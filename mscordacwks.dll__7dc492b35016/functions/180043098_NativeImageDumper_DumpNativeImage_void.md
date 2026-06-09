# NativeImageDumper::DumpNativeImage(void)

- ea: `0x180043098`
- end: `0x180045463`
- name: `?DumpNativeImage@NativeImageDumper@@QEAAXXZ`
- size: `9163`
- prototype: `void __fastcall(NativeImageDumper *__hidden this)`
- caller_count: `1`
- callee_count: `50`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800427c0`

## callees

- `0x18000b448`
- `0x18000ba00`
- `0x18000bb04`
- `0x18000bb64`
- `0x18000c824`
- `0x18000c86c`
- `0x18001d674`
- `0x180020f50`
- `0x1800210f0`
- `0x18002127c`
- `0x180022068`
- `0x1800222a8`
- `0x180040f74`
- `0x18004240c`
- `0x180042724`
- `0x180042a8c`
- `0x180042e18`
- `0x180042f28`
- `0x180043098`
- `0x180045464`
- `0x180045664`
- `0x1800457b8`
- `0x180045d28`
- `0x180045fa8`
- `0x180048870`
- `0x180048fb0`
- `0x180049300`
- `0x18004c8e8`
- `0x180055e00`
- `0x18005ecd4`
- `0x180062b20`
- `0x180067790`
- `0x180072664`
- `0x18007344c`
- `0x180076604`
- `0x180076d20`
- `0x180076e04`
- `0x1800777d0`
- `0x18007785c`
- `0x180078074`
- `0x1800780c4`
- `0x180078128`
- `0x1800782ac`
- `0x1800785d4`
- `0x180078608`
- `0x180078678`
- `0x1800f0d20`
- `0x1800f0fc4`
- `0x1801043f0`
- `0x180106100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180043981`
- `KERNEL32!HeapFree` at `0x180043e98`
- `KERNEL32!HeapFree` at `0x180044343`
- `KERNEL32!HeapFree` at `0x180043981`
- `KERNEL32!HeapFree` at `0x180043e98`
- `KERNEL32!HeapFree` at `0x180044343`
- `KERNEL32!GetProcessHeap` at `0x18004396c`
- `KERNEL32!GetProcessHeap` at `0x180043e83`
- `KERNEL32!GetProcessHeap` at `0x18004432e`
- `KERNEL32!GetProcessHeap` at `0x18004396c`
- `KERNEL32!GetProcessHeap` at `0x180043e83`
- `KERNEL32!GetProcessHeap` at `0x18004432e`

## string_xrefs

- `0x180043940`: `access`
- `0x180043a7d`: `Directory`
- `0x180043edc`: `EntryPointToken`
- `0x18004439a`: `ReadyToRun image`
- `0x180044533`: `NativeManifestMetadata`
- `0x180044563`: `NativeManifestMetadata`
- `0x1800449e2`: `scopeName`
- `0x180044a9d`: `Token`
- `0x180044b0a`: `TokenName`
- `0x180044c0b`: `CORCOMPILE_VERSION_INFO`
- `0x180044d52`: `CORCOMPILE_DEPENDENCY`
- `0x180045380`: `Assembly %S is soft bound to mscorlib.  nidump cannot dump MethodTables completely.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
void __fastcall NativeImageDumper::DumpNativeImage(NativeImageDumper *this)
{
  int v2; // eax
  unsigned __int64 v3; // rax
  unsigned __int64 *v4; // r15
  unsigned int v5; // r12d
  __int64 *v6; // rcx
  __int64 v7; // rax
  const char *v8; // rdx
  int *v9; // rax
  _WORD *v10; // rax
  const char *v11; // r8
  int *v12; // rax
  unsigned int v13; // ebx
  struct CORCOMPILE_HEADER *NativeHeader; // rax
  int *v15; // rax
  unsigned int *v16; // rax
  int *v17; // rax
  _WORD *v18; // rax
  unsigned __int64 v19; // rcx
  int *v20; // rax
  void *v21; // rax
  __int64 v22; // rdx
  unsigned __int64 TargetAddrForHostAddr; // rax
  void *v24; // rax
  __int64 v25; // rdx
  unsigned __int64 v26; // rbx
  unsigned int *v27; // rdi
  unsigned int *v28; // rax
  __int64 v29; // rdi
  unsigned __int64 v30; // r8
  int *v31; // rax
  void *v32; // rax
  __int64 v33; // rdx
  unsigned __int64 v34; // rax
  void *v35; // rax
  __int64 v36; // rdx
  unsigned __int64 v37; // rbx
  unsigned int *v38; // rsi
  unsigned int *v39; // rdi
  _QWORD *v40; // rax
  __int64 v41; // rdi
  unsigned __int64 v42; // r8
  int *v43; // rax
  int *v44; // rax
  unsigned __int16 *v45; // rbx
  __int64 v46; // rdx
  __int64 v47; // rax
  void *v48; // rax
  __int64 v49; // rdx
  unsigned __int64 v50; // rbx
  unsigned int *v51; // rsi
  unsigned int *v52; // rdi
  void *v53; // rax
  int v54; // eax
  unsigned __int64 v55; // rax
  void *v56; // rax
  unsigned int *v57; // rdi
  unsigned int *v58; // rax
  unsigned __int64 RvaData; // rax
  unsigned __int64 v60; // rax
  unsigned int *v61; // rdi
  unsigned int *v62; // rax
  _DWORD *v63; // rax
  LPVOID v64; // rdi
  unsigned int *v65; // rax
  void *v66; // rbx
  HANDLE ProcessHeap; // rax
  int *v68; // rax
  unsigned int v69; // r12d
  unsigned int v70; // ebx
  char **v71; // rdi
  struct _IMAGE_DATA_DIRECTORY *DirectoryEntry; // rsi
  unsigned __int64 v73; // rax
  unsigned __int64 v74; // rax
  unsigned __int64 v75; // rax
  struct _IMAGE_DATA_DIRECTORY *v76; // rax
  unsigned __int64 v77; // rax
  void *v78; // rax
  __int64 v79; // rdx
  void *v80; // rax
  __int64 v81; // rdx
  unsigned __int64 v82; // rbx
  unsigned __int64 v83; // rax
  unsigned __int16 *v84; // rax
  unsigned __int16 *v85; // rax
  unsigned int *v86; // rax
  unsigned __int64 v87; // rax
  _DWORD *v88; // rax
  void *v89; // rdi
  HANDLE v90; // rax
  _DWORD *v91; // rax
  unsigned int *v92; // rax
  unsigned __int64 v93; // rax
  unsigned int *v94; // rax
  unsigned __int64 v95; // rax
  unsigned int *v96; // rax
  unsigned __int64 v97; // rax
  unsigned int *v98; // rax
  unsigned __int64 v99; // rax
  unsigned int *v100; // rax
  unsigned __int64 v101; // rax
  unsigned int *v102; // rax
  unsigned __int64 v103; // rax
  unsigned __int64 v104; // rax
  struct _IMAGE_DATA_DIRECTORY *v105; // rax
  unsigned __int64 v106; // rax
  void *v107; // rax
  __int64 v108; // rdx
  unsigned __int64 v109; // rax
  struct _IMAGE_DATA_DIRECTORY *v110; // rax
  unsigned __int64 v111; // rax
  void *v112; // rax
  __int64 v113; // rdx
  struct IMAGE_COR20_HEADER *CorHeader; // rax
  unsigned int Size; // ebx
  const unsigned __int8 *v116; // rdx
  void *v117; // rbx
  HANDLE v118; // rax
  const char *v119; // r8
  int HasNativeHeader; // eax
  int v121; // ecx
  unsigned __int64 v122; // rbx
  int v123; // eax
  unsigned __int64 v124; // r12
  int v125; // eax
  __int64 v126; // rsi
  __int64 v127; // rdi
  unsigned __int64 v128; // rax
  unsigned __int64 NativeDebugMap; // rax
  unsigned __int64 v130; // rsi
  int v131; // ecx
  __int64 v132; // rdi
  unsigned int v133; // ebx
  unsigned __int64 v134; // rax
  struct _IMAGE_SECTION_HEADER *Section; // rax
  struct _IMAGE_SECTION_HEADER *v136; // rax
  unsigned int v137; // ebx
  unsigned __int64 v138; // rax
  struct _IMAGE_SECTION_HEADER *v139; // rax
  unsigned int PhysicalAddress; // ebx
  unsigned __int64 v141; // rax
  struct IMAGE_COR20_HEADER *v142; // rax
  __int64 v143; // rbx
  unsigned __int64 v144; // rsi
  int v145; // edx
  __int64 v146; // rdi
  unsigned __int64 v147; // rax
  __int64 v148; // rcx
  int v149; // eax
  int v150; // eax
  unsigned __int64 v151; // rbx
  __int64 v152; // rdi
  unsigned __int64 v153; // rax
  __int64 v154; // rdi
  unsigned __int64 v155; // rax
  __int64 v156; // rax
  unsigned int EntryPointToken; // ebx
  struct IMAGE_COR20_HEADER *v158; // rax
  __int64 v159; // rax
  struct CORCOMPILE_VERSION_INFO *NativeVersionInfo; // rax
  __int64 v161; // rdx
  unsigned __int64 v162; // rbx
  unsigned __int64 v163; // rax
  unsigned __int64 v164; // rax
  char *v165; // rax
  struct CORCOMPILE_HEADER *v166; // rax
  unsigned int v167; // r13d
  unsigned __int64 v168; // rbx
  unsigned __int64 v169; // rsi
  unsigned __int64 v170; // rax
  unsigned __int64 v171; // rax
  struct IMetaDataImport2 *v172; // rdi
  unsigned int *v173; // rax
  __int64 v174; // rax
  __int64 v175; // rax
  __int64 v176; // rdi
  unsigned __int64 v177; // rax
  __int64 v178; // rax
  __int64 v179; // rax
  struct _GUID *v180; // rax
  unsigned int v181; // ebx
  unsigned __int64 *v182; // rdi
  unsigned __int16 *v183; // rax
  unsigned __int16 *v184; // rax
  struct NativeImageDumper::Dependency *v185; // rax
  int v186; // ebx
  __int64 v187; // rdi
  struct NativeImageDumper::Dependency *v188; // rax
  unsigned int v189; // edx
  unsigned int v190; // r8d
  struct NativeImageDumper::Dependency *Dependency; // rbx
  __int64 v192; // rax
  _OWORD *v193; // rbx
  __int64 v194; // rax
  _OWORD *v195; // rax
  __int64 v196; // rdx
  __int64 v197; // rax
  char *v198; // rax
  __int64 v199; // rbx
  __int64 v200; // rax
  _QWORD *v201; // rax
  __int64 v202; // rdx
  unsigned int v203[2]; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int64 v204; // [rsp+70h] [rbp-98h] BYREF
  __int64 v205; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int64 v206; // [rsp+80h] [rbp-88h] BYREF
  int v207; // [rsp+88h] [rbp-80h] BYREF
  unsigned int v208; // [rsp+8Ch] [rbp-7Ch] BYREF
  char v209[8]; // [rsp+90h] [rbp-78h] BYREF
  int v210; // [rsp+98h] [rbp-70h] BYREF
  __int64 v211; // [rsp+9Ch] [rbp-6Ch]
  LPVOID lpMem; // [rsp+A8h] [rbp-60h]
  _WORD v213[68]; // [rsp+B0h] [rbp-58h] BYREF
  struct _GUID v214; // [rsp+138h] [rbp+30h] BYREF
  int v215; // [rsp+148h] [rbp+40h] BYREF
  __int64 v216; // [rsp+14Ch] [rbp+44h]
  void *v217; // [rsp+158h] [rbp+50h]
  __int16 v218; // [rsp+160h] [rbp+58h] BYREF
  int v219; // [rsp+1E8h] [rbp+E0h] BYREF
  __int64 v220; // [rsp+1ECh] [rbp+E4h]
  void *v221; // [rsp+1F8h] [rbp+F0h]
  __int16 v222; // [rsp+200h] [rbp+F8h] BYREF

  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 56LL))(*((_QWORD *)this + 17));
  v2 = *((_DWORD *)this + 102);
  if ( (v2 & 1) != 0 )
  {
    (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 72LL))(*((_QWORD *)this + 17), "File");
    v2 = *((_DWORD *)this + 102);
    if ( (v2 & 1) != 0 )
    {
      (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 216LL))(
        *((_QWORD *)this + 17),
        "path",
        *((_QWORD *)this + 14));
      v2 = *((_DWORD *)this + 102);
      if ( (v2 & 1) != 0 )
      {
        (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 224LL))(
          *((_QWORD *)this + 17),
          "diskSize",
          *((unsigned int *)this + 18));
        v2 = *((_DWORD *)this + 102);
      }
    }
  }
  if ( (v2 & 1) != 0 )
  {
    v3 = NativeImageDumper::DataPtrToDisplay(this, *((_QWORD *)this + 15));
    (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, __int64))(**((_QWORD **)this + 17) + 184LL))(
      *((_QWORD *)this + 17),
      "IMAGE_DOS_HEADER",
      v3,
      64);
  }
  v4 = (unsigned __int64 *)((char *)this + 64);
  v5 = 0;
  if ( !(unsigned int)PEDecoder::HasNTHeaders((NativeImageDumper *)((char *)this + 64)) )
  {
    v6 = (__int64 *)*((_QWORD *)this + 17);
    v7 = *v6;
    if ( (*((_BYTE *)this + 408) & 1) != 0 )
    {
      (*(void (__fastcall **)(__int64 *, const char *, const char *))(v7 + 208))(v6, "isPEFile", "false");
      if ( (*((_BYTE *)this + 408) & 1) != 0 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 80LL))(*((_QWORD *)this + 17));
      goto LABEL_13;
    }
    v8 = "Non-PE file";
    goto LABEL_12;
  }
  if ( *(_QWORD *)PEDecoder::CheckNTHeaders((char *)this + 64, &v205) )
  {
    (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 24LL))(
      *((_QWORD *)this + 17),
      "*** NT headers are not valid ***");
    return;
  }
  if ( (*((_DWORD *)this + 102) & 1) != 0 )
  {
    v9 = (int *)DacInstantiateTypeByAddressHelper(*v4, 0x40u, 1, 1);
    v10 = DacInstantiateTypeByAddressHelper(*v4 + v9[15], 0x108u, 1, 1);
    v11 = "64 bit image";
    if ( v10[12] == 267 )
      v11 = "32 bit image";
    (*(void (__fastcall **)(_QWORD, const char *, const char *))(**((_QWORD **)this + 17) + 208LL))(
      *((_QWORD *)this + 17),
      "imageType",
      v11);
    if ( (*((_DWORD *)this + 102) & 1) != 0 )
    {
      v12 = (int *)DacInstantiateTypeByAddressHelper(*v4, 0x40u, 1, 1);
      v13 = *((_DWORD *)DacInstantiateTypeByAddressHelper(*v4 + v12[15], 0x108u, 1, 1) + 20);
      NativeHeader = PEDecoder::GetNativeHeader((NativeImageDumper *)((char *)this + 64));
      (*(void (__fastcall **)(_QWORD, const char *, _QWORD, _QWORD))(**((_QWORD **)this + 17) + 184LL))(
        *((_QWORD *)this + 17),
        "address",
        *((_QWORD *)NativeHeader + 13),
        v13);
      if ( (*((_DWORD *)this + 102) & 1) != 0 )
      {
        v15 = (int *)DacInstantiateTypeByAddressHelper(*v4, 0x40u, 1, 1);
        v16 = (unsigned int *)DacInstantiateTypeByAddressHelper(*v4 + v15[15], 0x108u, 1, 1);
        (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 224LL))(
          *((_QWORD *)this + 17),
          "TimeDateStamp",
          v16[2]);
      }
    }
  }
  v17 = (int *)DacInstantiateTypeByAddressHelper(*v4, 0x40u, 1, 1);
  v18 = DacInstantiateTypeByAddressHelper(*v4 + v17[15], 0x108u, 1, 1);
  v19 = *((_QWORD *)this + 8);
  if ( v18[12] == 267 )
  {
    v20 = (int *)DacInstantiateTypeByAddressHelper(v19, 0x40u, 1, 1);
    v21 = DacInstantiateTypeByAddressHelper(*((_QWORD *)this + 8) + v20[15], 0x108u, 1, 1);
    LOBYTE(v22) = 1;
    TargetAddrForHostAddr = DacGetTargetAddrForHostAddr(v21, v22);
    v24 = DacInstantiateTypeByAddressHelper(TargetAddrForHostAddr, 0xF8u, 1, 1);
    LOBYTE(v25) = 1;
    v26 = DacGetTargetAddrForHostAddr(v24, v25);
    *((_QWORD *)this + 16) = *((unsigned int *)DacInstantiateTypeByAddressHelper(v26, 0xF8u, 1, 1) + 20);
    v27 = (unsigned int *)DacInstantiateTypeByAddressHelper(v26, 0xF8u, 1, 1);
    v28 = (unsigned int *)DacInstantiateTypeByAddressHelper(v26, 0xF8u, 1, 1);
    (*(void (__fastcall **)(_QWORD, unsigned __int64, _QWORD, _QWORD))(**((_QWORD **)this + 17) + 32LL))(
      *((_QWORD *)this + 17),
      *v4,
      v28[20],
      v27[14]);
    *((_QWORD *)this + 69) = 4096;
    v29 = *((unsigned __int16 *)DacInstantiateTypeByAddressHelper(v26, 0xF8u, 1, 1) + 10);
    if ( (*((_BYTE *)this + 408) & 1) != 0 )
    {
      v30 = NativeImageDumper::DataPtrToDisplay(this, v26);
      (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, __int64))(**((_QWORD **)this + 17) + 184LL))(
        *((_QWORD *)this + 17),
        "IMAGE_NT_HEADERS32",
        v30,
        v29 + 24);
    }
  }
  else
  {
    v31 = (int *)DacInstantiateTypeByAddressHelper(v19, 0x40u, 1, 1);
    v32 = DacInstantiateTypeByAddressHelper(*((_QWORD *)this + 8) + v31[15], 0x108u, 1, 1);
    LOBYTE(v33) = 1;
    v34 = DacGetTargetAddrForHostAddr(v32, v33);
    v35 = DacInstantiateTypeByAddressHelper(v34, 0x108u, 1, 1);
    LOBYTE(v36) = 1;
    v37 = DacGetTargetAddrForHostAddr(v35, v36);
    *((_QWORD *)this + 16) = *((unsigned int *)DacInstantiateTypeByAddressHelper(v37, 0x108u, 1, 1) + 20);
    v38 = (unsigned int *)DacInstantiateTypeByAddressHelper(v37, 0x108u, 1, 1);
    v39 = (unsigned int *)DacInstantiateTypeByAddressHelper(v37, 0x108u, 1, 1);
    v40 = DacInstantiateTypeByAddressHelper(v37, 0x108u, 1, 1);
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 17) + 32LL))(
      *((_QWORD *)this + 17),
      v40[6],
      v39[20],
      v38[14]);
    *((_QWORD *)this + 69) = *((unsigned int *)DacInstantiateTypeByAddressHelper(v37, 0x108u, 1, 1) + 14);
    v41 = *((unsigned __int16 *)DacInstantiateTypeByAddressHelper(v37, 0x108u, 1, 1) + 10);
    if ( (*((_BYTE *)this + 408) & 1) != 0 )
    {
      v42 = NativeImageDumper::DataPtrToDisplay(this, v37);
      (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, __int64))(**((_QWORD **)this + 17) + 184LL))(
        *((_QWORD *)this + 17),
        "IMAGE_NT_HEADERS64",
        v42,
        v41 + 24);
    }
  }
  if ( (*((_DWORD *)this + 102) & 1) != 0 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 80LL))(*((_QWORD *)this + 17));
    if ( (*((_DWORD *)this + 102) & 1) != 0 )
      (*(void (**)(_QWORD, const char *, const wchar_t *, ...))(**((_QWORD **)this + 17) + 264LL))(
        *((_QWORD *)this + 17),
        "Sections",
        L"%-8s%s\t(disk %s)  %s");
  }
  v43 = (int *)DacInstantiateTypeByAddressHelper(*v4, 0x40u, 1, 1);
  if ( *((_WORD *)DacInstantiateTypeByAddressHelper(*v4 + v43[15], 0x108u, 1, 1) + 3) )
  {
    do
    {
      v44 = (int *)DacInstantiateTypeByAddressHelper(*v4, 0x40u, 1, 1);
      v45 = (unsigned __int16 *)DacInstantiateTypeByAddressHelper(*v4 + v44[15], 0x108u, 1, 1);
      LOBYTE(v46) = 1;
      v47 = DacGetTargetAddrForHostAddr(v45, v46);
      v48 = DacInstantiateTypeByAddressHelper(v47 + 24 + v45[10], 0x28u, 1, 1);
      LOBYTE(v49) = 1;
      v50 = DacGetTargetAddrForHostAddr(v48, v49) + 40LL * v5;
      v51 = (unsigned int *)DacInstantiateTypeByAddressHelper(v50, 0x28u, 1, 1);
      v52 = (unsigned int *)DacInstantiateTypeByAddressHelper(v50, 0x28u, 1, 1);
      v53 = DacInstantiateTypeByAddressHelper(v50, 0x28u, 1, 1);
      (*(void (__fastcall **)(_QWORD, void *, _QWORD, _QWORD))(**((_QWORD **)this + 17) + 40LL))(
        *((_QWORD *)this + 17),
        v53,
        v52[3],
        v51[4]);
      v54 = *((_DWORD *)this + 102);
      if ( (v54 & 1) != 0 )
      {
        v55 = NativeImageDumper::DataPtrToDisplay(this, v50);
        (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, __int64))(**((_QWORD **)this + 17) + 392LL))(
          *((_QWORD *)this + 17),
          "Section",
          v55,
          40);
        v54 = *((_DWORD *)this + 102);
      }
      if ( (v54 & 1) != 0 )
      {
        v56 = DacInstantiateTypeByAddressHelper(v50, 0x28u, 1, 1);
        (*(void (__fastcall **)(_QWORD, const char *, void *))(**((_QWORD **)this + 17) + 208LL))(
          *((_QWORD *)this + 17),
          "name",
          v56);
        if ( (*((_DWORD *)this + 102) & 1) != 0 )
        {
          v57 = (unsigned int *)DacInstantiateTypeByAddressHelper(v50, 0x28u, 1, 1);
          v58 = (unsigned int *)DacInstantiateTypeByAddressHelper(v50, 0x28u, 1, 1);
          RvaData = PEDecoder::GetRvaData((char *)this + 64, v58[3], 0);
          v60 = NativeImageDumper::DataPtrToDisplay(this, RvaData);
          (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, _QWORD))(**((_QWORD **)this + 17) + 184LL))(
            *((_QWORD *)this + 17),
            "address",
            v60,
            v57[2]);
          if ( (*((_DWORD *)this + 102) & 1) != 0 )
          {
            v61 = (unsigned int *)DacInstantiateTypeByAddressHelper(v50, 0x28u, 1, 1);
            v62 = (unsigned int *)DacInstantiateTypeByAddressHelper(v50, 0x28u, 1, 1);
            (*(void (__fastcall **)(_QWORD, const char *, _QWORD, _QWORD))(**((_QWORD **)this + 17) + 184LL))(
              *((_QWORD *)this + 17),
              "disk",
              v62[5],
              v61[4]);
            if ( (*((_DWORD *)this + 102) & 1) != 0 )
            {
              v211 = 128;
              lpMem = v213;
              v210 = 2;
              v213[0] = 0;
              v63 = DacInstantiateTypeByAddressHelper(v50, 0x28u, 1, 1);
              EnumFlagsToString(
                v63[9],
                (const struct NativeImageDumper::EnumMnemonics *)&qword_180160480,
                6,
                L", ",
                (struct SString *)&v210);
              SString::ConvertToUnicode((SString *)&v210);
              v64 = lpMem;
              v65 = (unsigned int *)DacInstantiateTypeByAddressHelper(v50, 0x28u, 1, 1);
              (*(void (__fastcall **)(_QWORD, const char *, _QWORD, LPVOID))(**((_QWORD **)this + 17) + 240LL))(
                *((_QWORD *)this + 17),
                "access",
                v65[9],
                v64);
              if ( (v211 & 0x800000000LL) != 0 )
              {
                v66 = lpMem;
                if ( lpMem )
                {
                  ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
                  if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
                  {
                    ProcessHeap = GetProcessHeap();
                    `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
                  }
                  HeapFree(ProcessHeap, 0, v66);
                }
              }
            }
          }
        }
      }
      if ( (*((_BYTE *)this + 408) & 1) != 0 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
      ++v5;
      v68 = (int *)DacInstantiateTypeByAddressHelper(*v4, 0x40u, 1, 1);
    }
    while ( v5 < *((unsigned __int16 *)DacInstantiateTypeByAddressHelper(*v4 + v68[15], 0x108u, 1, 1) + 3) );
  }
  if ( (*((_DWORD *)this + 102) & 1) != 0 )
  {
    (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 272LL))(
      *((_QWORD *)this + 17),
      "Total Sections");
    if ( (*((_DWORD *)this + 102) & 1) != 0 )
      (*(void (**)(_QWORD, const char *, const wchar_t *, ...))(**((_QWORD **)this + 17) + 264LL))(
        *((_QWORD *)this + 17),
        "Directories",
        L"%-40s%s");
  }
  v69 = 0;
  v70 = 0;
  v71 = off_180136790;
  do
  {
    DirectoryEntry = PEDecoder::GetDirectoryEntry((NativeImageDumper *)((char *)this + 64), v70);
    if ( DirectoryEntry->VirtualAddress )
    {
      if ( (*((_DWORD *)this + 102) & 1) != 0 )
      {
        (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 88LL))(
          *((_QWORD *)this + 17),
          "Directory");
        if ( (*((_DWORD *)this + 102) & 1) != 0 )
        {
          (*(void (__fastcall **)(_QWORD, const char *, char *))(**((_QWORD **)this + 17) + 208LL))(
            *((_QWORD *)this + 17),
            "name",
            *v71);
          if ( (*((_DWORD *)this + 102) & 1) != 0 )
          {
            v73 = PEDecoder::GetRvaData((char *)this + 64, DirectoryEntry->VirtualAddress, 0);
            v74 = NativeImageDumper::DataPtrToDisplay(this, v73);
            (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, _QWORD))(**((_QWORD **)this + 17) + 184LL))(
              *((_QWORD *)this + 17),
              "address",
              v74,
              DirectoryEntry->Size);
            if ( (*((_DWORD *)this + 102) & 1) != 0 )
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 96LL))(*((_QWORD *)this + 17));
          }
        }
      }
    }
    ++v70;
    ++v71;
  }
  while ( v70 < 0x10 );
  if ( (*((_BYTE *)this + 408) & 1) != 0 )
    (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 272LL))(
      *((_QWORD *)this + 17),
      "Total Directories");
  if ( !(unsigned int)PEDecoder::HasDirectoryEntry((NativeImageDumper *)((char *)this + 64), 14) )
  {
    v6 = (__int64 *)*((_QWORD *)this + 17);
    v7 = *v6;
    if ( (*((_BYTE *)this + 408) & 2) != 0 )
    {
      (*(void (__fastcall **)(__int64 *, const char *, const char *))(v7 + 208))(v6, "CLRInfo", "<none>");
      goto LABEL_13;
    }
    v8 = "Non-CLR image\n";
LABEL_12:
    (*(void (__fastcall **)(__int64 *, const char *))(v7 + 24))(v6, v8);
LABEL_13:
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 64LL))(*((_QWORD *)this + 17));
    return;
  }
  if ( *(_QWORD *)PEDecoder::CheckCorHeader((char *)this + 64, &v205) )
  {
    v6 = (__int64 *)*((_QWORD *)this + 17);
    v7 = *v6;
    v8 = "*** INVALID CLR Header ***";
    goto LABEL_12;
  }
  if ( (*((_BYTE *)this + 408) & 2) != 0 )
    (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 72LL))(*((_QWORD *)this + 17), "CLRInfo");
  v75 = *((_QWORD *)this + 11);
  if ( !v75 )
  {
    v76 = PEDecoder::GetDirectoryEntry((NativeImageDumper *)((char *)this + 64), 14);
    v77 = PEDecoder::GetRvaData((char *)this + 64, v76->VirtualAddress, 0);
    v78 = DacInstantiateTypeByAddressHelper(v77, 0x48u, 1, 1);
    LOBYTE(v79) = 1;
    v75 = DacGetTargetAddrForHostAddr(v78, v79);
    *((_QWORD *)this + 11) = v75;
  }
  v80 = DacInstantiateTypeByAddressHelper(v75, 0x48u, 1, 1);
  LOBYTE(v81) = 1;
  v82 = DacGetTargetAddrForHostAddr(v80, v81);
  v83 = NativeImageDumper::DataPtrToDisplay(this, v82);
  (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, __int64))(**((_QWORD **)this + 17) + 392LL))(
    *((_QWORD *)this + 17),
    "IMAGE_COR20_HEADER",
    v83,
    72);
  if ( (*((_DWORD *)this + 102) & 2) != 0 )
  {
    v84 = (unsigned __int16 *)DacInstantiateTypeByAddressHelper(v82, 0x48u, 1, 1);
    (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(**((_QWORD **)this + 17) + 344LL))(
      *((_QWORD *)this + 17),
      "MajorRuntimeVersion",
      4,
      2,
      v84[2]);
    if ( (*((_DWORD *)this + 102) & 2) != 0 )
    {
      v85 = (unsigned __int16 *)DacInstantiateTypeByAddressHelper(v82, 0x48u, 1, 1);
      (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(**((_QWORD **)this + 17) + 344LL))(
        *((_QWORD *)this + 17),
        "MinorRuntimeVersion",
        6,
        2,
        v85[3]);
    }
  }
  DacInstantiateTypeByAddressHelper(v82, 0x48u, 1, 1);
  v86 = (unsigned int *)DacInstantiateTypeByAddressHelper(v82, 0x48u, 1, 1);
  v87 = PEDecoder::GetRvaData((char *)this + 64, v86[2], 0);
  NativeImageDumper::DataPtrToDisplay(this, v87);
  (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 384LL))(
    *((_QWORD *)this + 17),
    "MetaData",
    8);
  if ( (*((_BYTE *)this + 408) & 2) != 0 )
  {
    v211 = 128;
    lpMem = v213;
    v210 = 2;
    v213[0] = 0;
    v88 = DacInstantiateTypeByAddressHelper(v82, 0x48u, 1, 1);
    EnumFlagsToString(
      v88[4],
      (const struct NativeImageDumper::EnumMnemonics *)&qword_180160540,
      7,
      L", ",
      (struct SString *)&v210);
    SString::ConvertToUnicode((SString *)&v210);
    DacInstantiateTypeByAddressHelper(v82, 0x48u, 1, 1);
    (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 352LL))(
      *((_QWORD *)this + 17),
      "Flags",
      16);
    if ( (v211 & 0x800000000LL) != 0 )
    {
      v89 = lpMem;
      if ( lpMem )
      {
        v90 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          v90 = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = v90;
        }
        HeapFree(v90, 0, v89);
      }
    }
    if ( (*((_BYTE *)this + 408) & 2) != 0 )
    {
      v91 = DacInstantiateTypeByAddressHelper(v82, 0x48u, 1, 1);
      (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, _DWORD))(**((_QWORD **)this + 17) + 344LL))(
        *((_QWORD *)this + 17),
        "EntryPointToken",
        20,
        4,
        v91[5]);
    }
  }
  DacInstantiateTypeByAddressHelper(v82, 0x48u, 1, 1);
  v92 = (unsigned int *)DacInstantiateTypeByAddressHelper(v82, 0x48u, 1, 1);
  v93 = PEDecoder::GetRvaData((char *)this + 64, v92[6], 0);
  NativeImageDumper::DataPtrToDisplay(this, v93);
  (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 384LL))(
    *((_QWORD *)this + 17),
    "Resources",
    24);
  DacInstantiateTypeByAddressHelper(v82, 0x48u, 1, 1);
  v94 = (unsigned int *)DacInstantiateTypeByAddressHelper(v82, 0x48u, 1, 1);
  v95 = PEDecoder::GetRvaData((char *)this + 64, v94[8], 0);
  NativeImageDumper::DataPtrToDisplay(this, v95);
  (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 384LL))(
    *((_QWORD *)this + 17),
    "StrongNameSignature",
    32);
  DacInstantiateTypeByAddressHelper(v82, 0x48u, 1, 1);
  v96 = (unsigned int *)DacInstantiateTypeByAddressHelper(v82, 0x48u, 1, 1);
  v97 = PEDecoder::GetRvaData((char *)this + 64, v96[10], 0);
  NativeImageDumper::DataPtrToDisplay(this, v97);
  (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 384LL))(
    *((_QWORD *)this + 17),
    "CodeManagerTable",
    40);
  DacInstantiateTypeByAddressHelper(v82, 0x48u, 1, 1);
  v98 = (unsigned int *)DacInstantiateTypeByAddressHelper(v82, 0x48u, 1, 1);
  v99 = PEDecoder::GetRvaData((char *)this + 64, v98[12], 0);
  NativeImageDumper::DataPtrToDisplay(this, v99);
  (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 384LL))(
    *((_QWORD *)this + 17),
    "VTableFixups",
    48);
  DacInstantiateTypeByAddressHelper(v82, 0x48u, 1, 1);
  v100 = (unsigned int *)DacInstantiateTypeByAddressHelper(v82, 0x48u, 1, 1);
  v101 = PEDecoder::GetRvaData((char *)this + 64, v100[14], 0);
  NativeImageDumper::DataPtrToDisplay(this, v101);
  (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 384LL))(
    *((_QWORD *)this + 17),
    "ExportAddressTableJumps",
    56);
  DacInstantiateTypeByAddressHelper(v82, 0x48u, 1, 1);
  v102 = (unsigned int *)DacInstantiateTypeByAddressHelper(v82, 0x48u, 1, 1);
  v103 = PEDecoder::GetRvaData((char *)this + 64, v102[16], 0);
  NativeImageDumper::DataPtrToDisplay(this, v103);
  (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 384LL))(
    *((_QWORD *)this + 17),
    "ManagedNativeHeader",
    64);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
  v104 = *((_QWORD *)this + 11);
  if ( !v104 )
  {
    v105 = PEDecoder::GetDirectoryEntry((NativeImageDumper *)((char *)this + 64), 14);
    v106 = PEDecoder::GetRvaData((char *)this + 64, v105->VirtualAddress, 0);
    v107 = DacInstantiateTypeByAddressHelper(v106, 0x48u, 1, 1);
    LOBYTE(v108) = 1;
    v104 = DacGetTargetAddrForHostAddr(v107, v108);
    *((_QWORD *)this + 11) = v104;
  }
  if ( *((_DWORD *)DacInstantiateTypeByAddressHelper(v104, 0x48u, 1, 1) + 8) )
  {
    v109 = *((_QWORD *)this + 11);
    if ( !v109 )
    {
      v110 = PEDecoder::GetDirectoryEntry((NativeImageDumper *)((char *)this + 64), 14);
      v111 = PEDecoder::GetRvaData((char *)this + 64, v110->VirtualAddress, 0);
      v112 = DacInstantiateTypeByAddressHelper(v111, 0x48u, 1, 1);
      LOBYTE(v113) = 1;
      v109 = DacGetTargetAddrForHostAddr(v112, v113);
      *((_QWORD *)this + 11) = v109;
    }
    if ( (*((_BYTE *)DacInstantiateTypeByAddressHelper(v109, 0x48u, 1, 1) + 16) & 8) != 0 )
    {
      CorHeader = PEDecoder::GetCorHeader((NativeImageDumper *)((char *)this + 64));
      Size = CorHeader->StrongNameSignature.Size;
      v203[0] = Size;
      v116 = (const unsigned __int8 *)PEDecoder::GetRvaData(
                                        (char *)this + 64,
                                        CorHeader->StrongNameSignature.VirtualAddress,
                                        0);
      if ( (*((_BYTE *)this + 408) & 2) != 0 )
      {
        v211 = 128;
        lpMem = v213;
        v210 = 2;
        v213[0] = 0;
        appendByteArray((struct SString *)&v210, v116, Size);
        if ( (*((_BYTE *)this + 408) & 2) != 0 )
        {
          SString::ConvertToUnicode((SString *)&v210);
          (*(void (__fastcall **)(_QWORD, const char *, LPVOID))(**((_QWORD **)this + 17) + 216LL))(
            *((_QWORD *)this + 17),
            "StrongName",
            lpMem);
        }
        if ( (v211 & 0x800000000LL) != 0 )
        {
          v117 = lpMem;
          if ( lpMem )
          {
            v118 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
            if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
            {
              v118 = GetProcessHeap();
              `ClrFreeInProcessHeap'::`2'::ProcessHeap = v118;
            }
            HeapFree(v118, 0, v117);
          }
        }
      }
    }
    else if ( (*((_BYTE *)this + 408) & 2) != 0 )
    {
      (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 160LL))(
        *((_QWORD *)this + 17),
        "DelaySigned");
    }
  }
  if ( (*((_DWORD *)this + 19) & 0x100) == 0
    && (*((_QWORD *)this + 13) || PEDecoder::FindReadyToRunHeader((NativeImageDumper *)((char *)this + 64))) )
  {
    if ( (*((_BYTE *)this + 408) & 2) == 0 )
      goto LABEL_109;
    v119 = "ReadyToRun image";
  }
  else if ( (unsigned int)PEDecoder::IsILOnly((NativeImageDumper *)((char *)this + 64)) )
  {
    if ( (*((_BYTE *)this + 408) & 2) == 0 )
      goto LABEL_109;
    v119 = "IL only image";
  }
  else
  {
    HasNativeHeader = PEDecoder::HasNativeHeader((NativeImageDumper *)((char *)this + 64));
    v121 = *((_DWORD *)this + 102) & 2;
    if ( HasNativeHeader )
    {
      if ( !v121 )
        goto LABEL_109;
      v119 = "Native image";
    }
    else
    {
      if ( !v121 )
        goto LABEL_109;
      v119 = "Mixed image";
    }
  }
  (*(void (__fastcall **)(_QWORD, const char *, const char *))(**((_QWORD **)this + 17) + 208LL))(
    *((_QWORD *)this + 17),
    "imageType",
    v119);
LABEL_109:
  v122 = *(_QWORD *)PEDecoder::GetMetadata((char *)this + 64, &v205, v203);
  NativeImageDumper::OpenMetadata(this);
  if ( (*((_DWORD *)this + 102) & 0x100000) != 0 )
  {
    v203[1] = 0;
    v123 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, unsigned int *))(**((_QWORD **)this + 32) + 24LL))(
             *((_QWORD *)this + 32),
             536870913,
             0,
             0,
             0,
             0,
             0,
             0,
             0,
             &v203[1]);
    if ( v123 < 0 )
      ThrowHR(v123);
    if ( (v203[1] & 0x200) != 0 )
    {
      if ( (*((_BYTE *)this + 408) & 2) != 0 )
        (*(void (__fastcall **)(_QWORD, const char *, const char *))(**((_QWORD **)this + 17) + 208LL))(
          *((_QWORD *)this + 17),
          "Metadata",
          "Not supported by WinRT");
    }
    else
    {
      NativeImageDumper::WriteElementsMetadata(this, "Metadata", v122, v203[0]);
    }
  }
  if ( *((int *)this + 102) < 0 )
    DacInstantiateTypeByAddressHelper(v122, v203[0], 1, 1);
  if ( (unsigned int)PEDecoder::HasNativeHeader((NativeImageDumper *)((char *)this + 64)) )
  {
    v124 = *(_QWORD *)PEDecoder::GetNativeManifestMetadata((char *)this + 64, &v205, v203);
    v125 = *((_DWORD *)this + 102);
    v126 = v203[0];
    if ( (v125 & 0x100000) != 0 )
    {
      NativeImageDumper::WriteElementsMetadata(this, "NativeManifestMetadata", v124, v203[0]);
    }
    else if ( (v125 & 2) != 0 )
    {
      v127 = **((_QWORD **)this + 17);
      v128 = NativeImageDumper::DataPtrToDisplay(this, v124);
      (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, __int64))(v127 + 184))(
        *((_QWORD *)this + 17),
        "NativeManifestMetadata",
        v128,
        v126);
    }
    if ( *((int *)this + 102) < 0 )
      DacInstantiateTypeByAddressHelper(v124, v126, 1, 1);
    NativeDebugMap = PEDecoder::GetNativeDebugMap((NativeImageDumper *)((char *)this + 64), v203);
    v130 = NativeDebugMap;
    v131 = *((_DWORD *)this + 102);
    if ( (v131 & 2) != 0 )
    {
      v132 = **((_QWORD **)this + 17);
      v133 = v203[0];
      v134 = NativeImageDumper::DataPtrToDisplay(this, NativeDebugMap);
      (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, _QWORD))(v132 + 184))(
        *((_QWORD *)this + 17),
        "debugMap",
        v134,
        v133);
      v131 = *((_DWORD *)this + 102);
    }
    v69 = 0;
    if ( v131 < 0 )
      DacInstantiateTypeByAddressHelper(v130, v203[0], 1, 1);
    Section = NativeImageDumper::FindSection(this, ".dbgmap");
    if ( Section )
    {
      if ( *((int *)this + 102) >= 0 )
      {
LABEL_135:
        if ( (*((_DWORD *)this + 102) & 0x80000080) != 0 )
        {
          v139 = NativeImageDumper::FindSection(this, ".text");
          if ( v139 )
          {
            *((_DWORD *)this + 133) = v139->VirtualAddress;
            PhysicalAddress = v139->Misc.PhysicalAddress;
            v141 = PEDecoder::GetRvaData((char *)this + 64, v139->VirtualAddress, 0);
            *((_QWORD *)this + 67) = DacInstantiateTypeByAddressHelper(v141, PhysicalAddress, 1, 1);
          }
          else
          {
            *((_DWORD *)this + 133) = 0;
            *((_QWORD *)this + 67) = 0;
          }
        }
        goto LABEL_139;
      }
      DacInstantiateTypeByAddressHelper(
        *v4 + Section->VirtualAddress,
        (Section->Misc.PhysicalAddress + *((_QWORD *)this + 69) - 1) & ~(*((_QWORD *)this + 69) - 1),
        1,
        1);
    }
    if ( *((int *)this + 102) < 0 )
    {
      v136 = NativeImageDumper::FindSection(this, ".rsrc");
      if ( v136 )
      {
        if ( *((int *)this + 102) < 0 )
        {
          v137 = v136->Misc.PhysicalAddress;
          v138 = PEDecoder::GetRvaData((char *)this + 64, v136->VirtualAddress, 0);
          DacInstantiateTypeByAddressHelper(v138, v137, 1, 1);
        }
      }
    }
    goto LABEL_135;
  }
LABEL_139:
  v142 = PEDecoder::GetCorHeader((NativeImageDumper *)((char *)this + 64));
  v143 = v142->Resources.Size;
  v144 = PEDecoder::GetRvaData((char *)this + 64, v142->Resources.VirtualAddress, 0);
  v145 = *((_DWORD *)this + 102);
  if ( (v145 & 0x1000000) != 0 )
  {
    if ( (v145 & 2) != 0 )
    {
      v146 = **((_QWORD **)this + 17);
      v147 = NativeImageDumper::DataPtrToDisplay(this, v144);
      (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, _QWORD))(v146 + 392))(
        *((_QWORD *)this + 17),
        "resource",
        v147,
        (unsigned int)v143);
      v145 = *((_DWORD *)this + 102);
    }
    if ( (v145 & 2) != 0 )
      (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 264LL))(
        *((_QWORD *)this + 17),
        "Resources",
        0);
    v205 = 0;
    while ( 1 )
    {
      v148 = *((_QWORD *)this + 30);
      v203[0] = 0;
      v149 = (*(__int64 (__fastcall **)(__int64, __int64 *, unsigned int *, __int64, unsigned int *))(*(_QWORD *)v148 + 88LL))(
               v148,
               &v205,
               &v203[1],
               1,
               v203);
      if ( v149 < 0 )
        ThrowHR(v149);
      if ( !v203[0] )
        break;
      v150 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *, __int64, unsigned int *, int *, unsigned __int64 *, unsigned __int64 *))(**((_QWORD **)this + 30) + 56LL))(
               *((_QWORD *)this + 30),
               v203[1],
               &v219,
               256,
               &v208,
               &v207,
               &v206,
               &v204);
      if ( v150 < 0 )
        ThrowHR(v150);
      if ( (v207 & 0xFFFFFF) == 0 )
      {
        if ( 2 * (unsigned __int64)v208 >= 0x200 )
          _report_rangecheckfailure();
        *((_WORD *)&v219 + v208) = 0;
        v151 = v144 + (unsigned int)v206;
        v152 = *(unsigned int *)DacInstantiateTypeByAddressHelper(v151, 4u, 1, 1);
        if ( (*((_DWORD *)this + 102) & 0x1000000) != 0 )
        {
          v153 = NativeImageDumper::DataPtrToDisplay(this, v151);
          (*(void (__fastcall **)(_QWORD, const char *, int *, unsigned __int64, __int64))(**((_QWORD **)this + 17)
                                                                                         + 200LL))(
            *((_QWORD *)this + 17),
            "Resource",
            &v219,
            v153,
            v152 + 4);
        }
      }
    }
    if ( (*((_DWORD *)this + 102) & 2) != 0 )
    {
      (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 272LL))(
        *((_QWORD *)this + 17),
        "Total Resources");
      if ( (*((_DWORD *)this + 102) & 2) != 0 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
    }
  }
  else if ( (v145 & 2) != 0 )
  {
    v154 = **((_QWORD **)this + 17);
    v155 = NativeImageDumper::DataPtrToDisplay(this, v144);
    (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, __int64))(v154 + 184))(
      *((_QWORD *)this + 17),
      "resource",
      v155,
      v143);
  }
  (*(void (__fastcall **)(_QWORD, unsigned __int16 *, __int64, char *, struct _GUID *))(**((_QWORD **)this + 31) + 80LL))(
    *((_QWORD *)this + 31),
    &qword_180164020,
    0x2000,
    v209,
    &v214);
  v215 = 2;
  v216 = 128;
  v217 = &v218;
  v218 = 0;
  GuidToString(&v214, (struct SString *)&v215);
  v156 = -1;
  do
    ++v156;
  while ( *(&qword_180164020 + v156) );
  if ( v156 )
  {
    if ( (*((_BYTE *)this + 408) & 2) == 0 )
      goto LABEL_164;
    (*(void (__fastcall **)(_QWORD, const char *, unsigned __int16 *))(**((_QWORD **)this + 17) + 216LL))(
      *((_QWORD *)this + 17),
      "scopeName",
      &qword_180164020);
  }
  if ( (*((_BYTE *)this + 408) & 2) != 0 )
  {
    SString::ConvertToUnicode((SString *)&v215);
    (*(void (__fastcall **)(_QWORD, const char *, void *))(**((_QWORD **)this + 17) + 216LL))(
      *((_QWORD *)this + 17),
      "mvid",
      v217);
  }
LABEL_164:
  if ( (PEDecoder::GetCorHeader((NativeImageDumper *)((char *)this + 64))->Flags & 0x10) != 0
    || (PEDecoder::GetEntryPointToken((NativeImageDumper *)((char *)this + 64)) & 0xFFFFFF) == 0 )
  {
    if ( (PEDecoder::GetCorHeader((NativeImageDumper *)((char *)this + 64))->Flags & 0x10) != 0
      && PEDecoder::GetCorHeader((NativeImageDumper *)((char *)this + 64))->EntryPointToken
      && (*((_BYTE *)this + 408) & 2) != 0 )
    {
      v158 = PEDecoder::GetCorHeader((NativeImageDumper *)((char *)this + 64));
      v159 = PEDecoder::GetRvaData((char *)this + 64, v158->EntryPointToken, 0);
      (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 168LL))(
        *((_QWORD *)this + 17),
        "NativeEntryPoint",
        v159);
    }
  }
  else
  {
    if ( (*((_BYTE *)this + 408) & 2) != 0 )
      (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 104LL))(
        *((_QWORD *)this + 17),
        "ManagedEntryPoint");
    EntryPointToken = PEDecoder::GetEntryPointToken((NativeImageDumper *)((char *)this + 64));
    if ( (*((_BYTE *)this + 408) & 2) != 0 )
      (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 232LL))(
        *((_QWORD *)this + 17),
        "Token",
        EntryPointToken);
    v210 = 2;
    v211 = 128;
    lpMem = v213;
    v213[0] = 0;
    NativeImageDumper::AppendTokenName(this, EntryPointToken, (struct SString *)&v210, 0, 0);
    if ( (*((_DWORD *)this + 102) & 2) != 0 )
    {
      SString::ConvertToUnicode((SString *)&v210);
      (*(void (__fastcall **)(_QWORD, const char *, LPVOID))(**((_QWORD **)this + 17) + 216LL))(
        *((_QWORD *)this + 17),
        "TokenName",
        lpMem);
      if ( (*((_DWORD *)this + 102) & 2) != 0 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 120LL))(*((_QWORD *)this + 17));
    }
    if ( (v211 & 0x800000000LL) != 0 )
      operator delete(lpMem);
  }
  if ( !(unsigned int)PEDecoder::HasNativeHeader((NativeImageDumper *)((char *)this + 64)) )
    goto LABEL_235;
  NativeVersionInfo = PEDecoder::GetNativeVersionInfo((NativeImageDumper *)((char *)this + 64));
  LOBYTE(v161) = 1;
  v162 = DacGetTargetAddrForHostAddr(NativeVersionInfo, v161);
  if ( (*((_DWORD *)this + 102) & 2) != 0 )
  {
    v163 = NativeImageDumper::DataPtrToDisplay(this, v162);
    (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, __int64))(**((_QWORD **)this + 17) + 392LL))(
      *((_QWORD *)this + 17),
      "CORCOMPILE_VERSION_INFO",
      v163,
      88);
    if ( (*((_DWORD *)this + 102) & 2) != 0 )
    {
      v164 = NativeImageDumper::DataPtrToDisplay(this, v162);
      (*(void (__fastcall **)(_QWORD, const char *, __int64, __int64, unsigned __int64, __int64))(**((_QWORD **)this + 17)
                                                                                                + 408LL))(
        *((_QWORD *)this + 17),
        "sourceAssembly",
        32,
        24,
        v164 + 32,
        24);
    }
  }
  v165 = (char *)DacInstantiateTypeByAddressHelper(v162, 0x58u, 1, 1);
  NativeImageDumper::DumpAssemblySignature(this, (struct CORCOMPILE_ASSEMBLY_SIGNATURE *)(v165 + 32));
  if ( (*((_BYTE *)this + 408) & 2) != 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
  v166 = PEDecoder::GetNativeHeader((NativeImageDumper *)((char *)this + 64));
  v167 = *((_DWORD *)v166 + 13) >> 6;
  v168 = PEDecoder::GetRvaData((char *)this + 64, *((unsigned int *)v166 + 12), 0);
  v204 = v168;
  if ( (*((_BYTE *)this + 408) & 2) != 0 )
    (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 17) + 264LL))(
      *((_QWORD *)this + 17),
      "Dependencies",
      0);
  if ( v167 )
  {
    v169 = 0;
    v206 = 0;
    do
    {
      if ( (*((_DWORD *)this + 102) & 2) != 0 )
      {
        v170 = DacTAddrOffset(v168, v169, 0x40u);
        v171 = NativeImageDumper::DataPtrToDisplay(this, v170);
        (*(void (__fastcall **)(_QWORD, const char *, unsigned __int64, __int64))(**((_QWORD **)this + 17) + 392LL))(
          *((_QWORD *)this + 17),
          "CORCOMPILE_DEPENDENCY",
          v171,
          64);
        if ( (*((_DWORD *)this + 102) & 2) != 0 )
        {
          v172 = (struct IMetaDataImport2 *)*((_QWORD *)this + 31);
          v173 = (unsigned int *)__DPtrBase<CORCOMPILE_DEPENDENCY,__DPtr<CORCOMPILE_DEPENDENCY>>::operator[]<unsigned int>(
                                   &v204,
                                   v69);
          NativeImageDumper::DoWriteFieldMDToken(this, "dwAssemblyRef", 0, 4u, *v173, v172);
          if ( (*((_DWORD *)this + 102) & 2) != 0 )
          {
            v174 = __DPtrBase<CORCOMPILE_DEPENDENCY,__DPtr<CORCOMPILE_DEPENDENCY>>::operator[]<unsigned int>(&v204, v69);
            NativeImageDumper::DoWriteFieldMDToken(
              this,
              "dwAssemblyDef",
              4u,
              4u,
              *(_DWORD *)(v174 + 4),
              *((struct IMetaDataImport2 **)this + 31));
            if ( (*((_DWORD *)this + 102) & 2) != 0 )
            {
              v220 = 128;
              v221 = &v222;
              v219 = 2;
              v222 = 0;
              v175 = __DPtrBase<CORCOMPILE_DEPENDENCY,__DPtr<CORCOMPILE_DEPENDENCY>>::operator[]<unsigned int>(
                       &v204,
                       v69);
              EnumFlagsToString(
                *(_DWORD *)(v175 + 56),
                (const struct NativeImageDumper::EnumMnemonics *)&qword_1801605B0,
                2,
                L", ",
                (struct SString *)&v219);
              SString::ConvertToUnicode((SString *)&v219);
              v176 = **((_QWORD **)this + 17);
              __DPtrBase<CORCOMPILE_DEPENDENCY,__DPtr<CORCOMPILE_DEPENDENCY>>::operator[]<unsigned int>(&v204, v69);
              (*(void (__fastcall **)(_QWORD, const char *, __int64))(v176 + 352))(
                *((_QWORD *)this + 17),
                "dependencyInfo",
                56);
              if ( (v220 & 0x800000000LL) != 0 )
                operator delete(v221);
              v169 = v206;
            }
          }
        }
      }
      if ( (*((_BYTE *)this + 408) & 2) != 0 )
      {
        v177 = DacTAddrOffset(v168, v169, 0x40u);
        NativeImageDumper::DataPtrToDisplay(this, v177);
        (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 408LL))(
          *((_QWORD *)this + 17),
          "signAssemblyDef",
          8);
      }
      v178 = __DPtrBase<CORCOMPILE_DEPENDENCY,__DPtr<CORCOMPILE_DEPENDENCY>>::operator[]<unsigned int>(&v204, v69);
      NativeImageDumper::DumpAssemblySignature(this, (struct CORCOMPILE_ASSEMBLY_SIGNATURE *)(v178 + 8));
      if ( (*((_BYTE *)this + 408) & 2) != 0 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
      v211 = 128;
      lpMem = v213;
      v210 = 2;
      v213[0] = 0;
      v179 = __DPtrBase<CORCOMPILE_DEPENDENCY,__DPtr<CORCOMPILE_DEPENDENCY>>::operator[]<unsigned int>(&v204, v69);
      if ( *(_QWORD *)(v179 + 32) == INVALID_NGEN_SIGNATURE && *(_QWORD *)(v179 + 40) == 0xA1D1957ED914F39DuLL )
      {
        SString::Append((SString *)&v210, L"INVALID_NGEN_SIGNATURE");
      }
      else
      {
        v180 = (struct _GUID *)__DPtrBase<CORCOMPILE_DEPENDENCY,__DPtr<CORCOMPILE_DEPENDENCY>>::operator[]<unsigned int>(
                                 &v204,
                                 v69);
        GuidToString(v180 + 2, (struct SString *)&v210);
      }
      if ( (*((_BYTE *)this + 408) & 2) != 0 )
      {
        SString::ConvertToUnicode((SString *)&v210);
        (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 17) + 312LL))(
          *((_QWORD *)this + 17),
          "signNativeImage",
          32);
      }
      if ( (v211 & 0x800000000LL) != 0 )
        operator delete(lpMem);
      if ( (*((_BYTE *)this + 408) & 2) != 0 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
      ++v69;
      v206 = ++v169;
    }
    while ( v69 < v167 );
    v4 = (unsigned __int64 *)((char *)this + 64);
  }
  if ( (*((_DWORD *)this + 102) & 2) != 0 )
  {
    (*(void (__fastcall **)(_QWORD, const char *))(**((_QWORD **)this + 17) + 272LL))(
      *((_QWORD *)this + 17),
      "Total Dependencies");
    if ( (*((_DWORD *)this + 102) & 2) != 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 416LL))(*((_QWORD *)this + 17));
  }
  v181 = 0;
  if ( (*((_DWORD *)PEDecoder::GetNativeHeader((PEDecoder *)v4) + 7) & 0xFFFFFFFC) != 0 )
  {
    do
    {
      v182 = (unsigned __int64 *)NativeImageDumper::OpenImport(this, v181);
      if ( (*((_DWORD *)this + 102) & 0x4000000) != 0 )
      {
        (*(void (**)(_QWORD, const char *, ...))(**((_QWORD **)this + 17) + 24LL))(
          *((_QWORD *)this + 17),
          "Import: %d\n",
          v181);
        (*(void (**)(_QWORD, const char *, ...))(**((_QWORD **)this + 17) + 24LL))(
          *((_QWORD *)this + 17),
          "\tDependency: %p\n",
          v182[1]);
        v183 = (unsigned __int16 *)DacInstantiateTypeByAddressHelper(*v182, 4u, 1, 1);
        (*(void (**)(_QWORD, const char *, ...))(**((_QWORD **)this + 17) + 24LL))(
          *((_QWORD *)this + 17),
          "\twAssemblyRid: %d\n",
          *v183);
        v184 = (unsigned __int16 *)DacInstantiateTypeByAddressHelper(*v182, 4u, 1, 1);
        (*(void (**)(_QWORD, const char *, ...))(**((_QWORD **)this + 17) + 24LL))(
          *((_QWORD *)this + 17),
          "\twModuleRid %d\n",
          v184[1]);
      }
      ++v181;
    }
    while ( v181 < *((_DWORD *)PEDecoder::GetNativeHeader((PEDecoder *)v4) + 7) >> 2 );
  }
  v185 = NativeImageDumper::OpenDependency(this, 0);
  NativeImageDumper::TraceDumpDependency(this, 0, v185);
  if ( v167 )
  {
    v186 = 1;
    v187 = v167;
    do
    {
      v188 = NativeImageDumper::OpenDependency(this, v186);
      NativeImageDumper::TraceDumpDependency(this, v186++, v188);
      --v187;
    }
    while ( v187 );
  }
  v189 = 0;
  v190 = *((_DWORD *)this + 68);
  if ( !v190 )
    goto LABEL_228;
  while ( 1 )
  {
    Dependency = (struct NativeImageDumper::Dependency *)(*((_QWORD *)this + 33) + 336LL * v189);
    if ( *((_BYTE *)Dependency + 72) )
      break;
    if ( ++v189 >= v190 )
      goto LABEL_228;
  }
  if ( !Dependency || !wcscmp(*((const wchar_t **)this + 14), L"mscorlib") )
  {
LABEL_228:
    Dependency = NativeImageDumper::GetDependency(this, 0, 0);
    *((_BYTE *)Dependency + 72) = 1;
  }
  if ( *((_BYTE *)Dependency + 73) )
  {
    *((_BYTE *)this + 544) = 1;
  }
  else if ( !*((_BYTE *)this + 544) )
  {
    goto LABEL_233;
  }
  v192 = DacInstantiateClassByVTable(*((_QWORD *)Dependency + 4));
  v193 = DacInstantiateTypeByAddressHelper(*(_QWORD *)(v192 + 1168), 0x40u, 1, 1);
  v194 = DacGlobalBase();
  v195 = DacInstantiateTypeByAddressHelper(v194 + (unsigned int)*g_Mscorlib[0], 0x40u, 1, 1);
  *v195 = *v193;
  v195[1] = v193[1];
  v195[2] = v193[2];
  v195[3] = v193[3];
  LOBYTE(v196) = 1;
  DacWriteHostInstance(v195, v196);
  v197 = DacGlobalBase();
  v198 = (char *)DacInstantiateTypeByAddressHelper((unsigned int)*g_Mscorlib[0] + v197, 0x40u, 1, 1);
  v199 = *(_QWORD *)__DPtrBase<__DPtr<MethodTable>,__DPtr<__DPtr<MethodTable>>>::operator[]<enum BinderClassID>(
                      v198 + 8,
                      28);
  v200 = DacGlobalBase();
  v201 = DacInstantiateTypeByAddressHelper((unsigned int)*g_pObjectClass[0] + v200, 8u, 1, 1);
  *v201 = v199;
  LOBYTE(v202) = 1;
  DacWriteHostInstance(v201, v202);
LABEL_233:
  if ( !__GlobalPtr<MethodTable *,__DPtr<MethodTable>>::operator MethodTable *(g_pObjectClass) )
  {
    (*(void (**)(_QWORD, const char *, ...))(**((_QWORD **)this + 17) + 24LL))(
      *((_QWORD *)this + 17),
      "Assembly %S is soft bound to mscorlib.  nidump cannot dump MethodTables completely.\n",
      *((_QWORD *)this + 14));
    *((_BYTE *)this + 544) = 0;
  }
LABEL_235:
  if ( (*((_BYTE *)this + 408) & 2) != 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 80LL))(*((_QWORD *)this + 17));
  if ( (*((_DWORD *)v4 + 3) & 0x100) == 0 && (v4[5] || PEDecoder::FindReadyToRunHeader((PEDecoder *)v4)) )
  {
    NativeImageDumper::DumpReadyToRun(this);
  }
  else if ( (unsigned int)PEDecoder::HasNativeHeader((PEDecoder *)v4) )
  {
    NativeImageDumper::DumpNative(this);
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 64LL))(*((_QWORD *)this + 17));
  if ( (v216 & 0x800000000LL) != 0 )
    operator delete(v217);
}

```

## disassembly

```asm
0x180043098  mov     rax, rsp
0x18004309b  mov     [rax+10h], rbx
0x18004309f  mov     [rax+18h], rsi
0x1800430a3  mov     [rax+20h], rdi
0x1800430a7  push    rbp
0x1800430a8  push    r12
0x1800430aa  push    r13
0x1800430ac  push    r14
0x1800430ae  push    r15
0x1800430b0  lea     rbp, [rax-318h]
0x1800430b7  sub     rsp, 3F0h
0x1800430be  mov     rax, cs:__security_cookie
0x1800430c5  xor     rax, rsp
0x1800430c8  mov     [rbp+310h+var_30], rax
0x1800430cf  mov     r14, rcx
0x1800430d2  mov     rcx, [rcx+88h]
0x1800430d9  mov     rax, [rcx]
0x1800430dc  mov     rax, [rax+38h]
0x1800430e0  call    cs:__guard_dispatch_icall_fptr
0x1800430e6  mov     eax, [r14+198h]
0x1800430ed  mov     r13d, 1
0x1800430f3  test    r13b, al
0x1800430f6  jz      short loc_180043176
0x1800430f8  mov     rcx, [r14+88h]
0x1800430ff  mov     rax, [rcx]
0x180043102  lea     rdx, aFile
0x180043109  mov     rax, [rax+48h]
0x18004310d  call    cs:__guard_dispatch_icall_fptr
0x180043113  mov     eax, [r14+198h]
0x18004311a  test    r13b, al
0x18004311d  jz      short loc_180043176
0x18004311f  mov     rcx, [r14+88h]
0x180043126  mov     rax, [rcx]
0x180043129  mov     r8, [r14+70h]
0x18004312d  lea     rdx, aPath
0x180043134  mov     rax, [rax+0D8h]
0x18004313b  call    cs:__guard_dispatch_icall_fptr
0x180043141  mov     eax, [r14+198h]
0x180043148  test    r13b, al
0x18004314b  jz      short loc_180043176
0x18004314d  mov     rcx, [r14+88h]
0x180043154  mov     rax, [rcx]
0x180043157  mov     r8d, [r14+48h]
0x18004315b  lea     rdx, aDisksize
0x180043162  mov     rax, [rax+0E0h]
0x180043169  call    cs:__guard_dispatch_icall_fptr
0x18004316f  mov     eax, [r14+198h]
0x180043176  mov     ebx, 40h ; '@'
0x18004317b  test    r13b, al
0x18004317e  jz      short loc_1800431B3
0x180043180  mov     rdx, [r14+78h]; unsigned __int64
0x180043184  mov     rcx, r14; this
0x180043187  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z
0x18004318c  mov     rcx, [r14+88h]
0x180043193  mov     rdx, [rcx]
0x180043196  mov     r10, [rdx+0B8h]
0x18004319d  mov     r9d, ebx
0x1800431a0  mov     r8, rax
0x1800431a3  lea     rdx, aImageDosHeader
0x1800431aa  mov     rax, r10
0x1800431ad  call    cs:__guard_dispatch_icall_fptr
0x1800431b3  lea     r15, [r14+40h]
0x1800431b7  mov     rcx, r15; this
0x1800431ba  call    ?HasNTHeaders@PEDecoder@@QEBAHXZ
0x1800431bf  xor     r12d, r12d
0x1800431c2  test    eax, eax
0x1800431c4  jnz     short loc_18004323D
0x1800431c6  mov     rcx, [r14+88h]
0x1800431cd  mov     rax, [rcx]
0x1800431d0  test    [r14+198h], r13b
0x1800431d7  jz      short loc_180043213
0x1800431d9  lea     r8, aFalse
0x1800431e0  lea     rdx, aIspefile
0x1800431e7  mov     rax, [rax+0D0h]
0x1800431ee  call    cs:__guard_dispatch_icall_fptr
0x1800431f4  test    [r14+198h], r13b
0x1800431fb  jz      short loc_180043224
0x1800431fd  mov     rcx, [r14+88h]
0x180043204  mov     rax, [rcx]
0x180043207  mov     rax, [rax+50h]
0x18004320b  call    cs:__guard_dispatch_icall_fptr
0x180043211  jmp     short loc_180043224
0x180043213  lea     rdx, aNonPeFile
0x18004321a  mov     rax, [rax+18h]
0x18004321e  call    cs:__guard_dispatch_icall_fptr
0x180043224  mov     rcx, [r14+88h]
0x18004322b  mov     rax, [rcx]
0x18004322e  mov     rax, [rax+40h]
0x180043232  call    cs:__guard_dispatch_icall_fptr
0x180043238  jmp     loc_180045415
0x18004323d  lea     rdx, [rsp+410h+var_3A0]
0x180043242  mov     rcx, r15
0x180043245  call    ?CheckNTHeaders@PEDecoder@@QEBA?AVCHECK@@XZ
0x18004324a  cmp     [rax], r12
0x18004324d  jz      short loc_18004326F
0x18004324f  mov     rcx, [r14+88h]
0x180043256  mov     rax, [rcx]
0x180043259  lea     rdx, aNtHeadersAreNo
0x180043260  mov     rax, [rax+18h]
0x180043264  call    cs:__guard_dispatch_icall_fptr
0x18004326a  jmp     loc_180045415
0x18004326f  mov     eax, [r14+198h]
0x180043276  mov     edi, 108h
0x18004327b  lea     esi, [rdi+3]
0x18004327e  test    r13b, al
0x180043281  jz      loc_18004339A
0x180043287  mov     r9b, r13b; bool
0x18004328a  mov     r8b, r13b; bool
0x18004328d  mov     edx, ebx; unsigned int
0x18004328f  mov     rcx, [r15]; unsigned __int64
0x180043292  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x180043297  movsxd  rcx, dword ptr [rax+3Ch]
0x18004329b  add     rcx, [r15]; unsigned __int64
0x18004329e  mov     r9b, r13b; bool
0x1800432a1  mov     r8b, r13b; bool
0x1800432a4  mov     edx, edi; unsigned int
0x1800432a6  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x1800432ab  mov     rcx, [r14+88h]
0x1800432b2  mov     r9, [rcx]
0x1800432b5  lea     rdx, a32BitImage
0x1800432bc  lea     r8, a64BitImage
0x1800432c3  cmp     [rax+18h], si
0x1800432c7  cmovz   r8, rdx
0x1800432cb  lea     rdx, aImagetype
0x1800432d2  mov     rax, [r9+0D0h]
0x1800432d9  call    cs:__guard_dispatch_icall_fptr
0x1800432df  mov     eax, [r14+198h]
0x1800432e6  test    r13b, al
0x1800432e9  jz      loc_18004339A
0x1800432ef  mov     r9b, r13b; bool
0x1800432f2  mov     r8b, r13b; bool
0x1800432f5  mov     edx, ebx; unsigned int
0x1800432f7  mov     rcx, [r15]; unsigned __int64
0x1800432fa  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x1800432ff  movsxd  rcx, dword ptr [rax+3Ch]
0x180043303  add     rcx, [r15]; unsigned __int64
0x180043306  mov     r9b, r13b; bool
0x180043309  mov     r8b, r13b; bool
0x18004330c  mov     edx, edi; unsigned int
0x18004330e  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x180043313  mov     ebx, [rax+50h]
0x180043316  mov     rcx, r15; this
0x180043319  call    ?GetNativeHeader@PEDecoder@@QEBAPEAUCORCOMPILE_HEADER@@XZ
0x18004331e  mov     r8, [rax+68h]
0x180043322  mov     rcx, [r14+88h]
0x180043329  mov     rax, [rcx]
0x18004332c  mov     r9d, ebx
0x18004332f  lea     rdx, aAddress_0
0x180043336  mov     rax, [rax+0B8h]
0x18004333d  call    cs:__guard_dispatch_icall_fptr
0x180043343  mov     eax, [r14+198h]
0x18004334a  mov     ebx, 40h ; '@'
0x18004334f  test    r13b, al
0x180043352  jz      short loc_18004339A
0x180043354  mov     r9b, r13b; bool
0x180043357  mov     r8b, r13b; bool
0x18004335a  mov     edx, ebx; unsigned int
0x18004335c  mov     rcx, [r15]; unsigned __int64
0x18004335f  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x180043364  movsxd  rcx, dword ptr [rax+3Ch]
0x180043368  add     rcx, [r15]; unsigned __int64
0x18004336b  mov     r9b, r13b; bool
0x18004336e  mov     r8b, r13b; bool
0x180043371  mov     edx, edi; unsigned int
0x180043373  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x180043378  mov     r8d, [rax+8]
0x18004337c  mov     rcx, [r14+88h]
0x180043383  mov     rax, [rcx]
0x180043386  lea     rdx, aTimedatestamp
0x18004338d  mov     rax, [rax+0E0h]
0x180043394  call    cs:__guard_dispatch_icall_fptr
0x18004339a  mov     r9b, r13b; bool
0x18004339d  mov     r8b, r13b; bool
0x1800433a0  mov     edx, ebx; unsigned int
0x1800433a2  mov     rcx, [r15]; unsigned __int64
0x1800433a5  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x1800433aa  movsxd  rcx, dword ptr [rax+3Ch]
0x1800433ae  add     rcx, [r15]; unsigned __int64
0x1800433b1  mov     r9b, r13b; bool
0x1800433b4  mov     r8b, r13b; bool
0x1800433b7  mov     edx, edi; unsigned int
0x1800433b9  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x1800433be  mov     r9b, r13b; bool
0x1800433c1  mov     r8b, r13b; bool
0x1800433c4  mov     edx, ebx; unsigned int
0x1800433c6  mov     rcx, [r14+40h]; unsigned __int64
0x1800433ca  cmp     [rax+18h], si
0x1800433ce  jnz     loc_1800434CF
0x1800433d4  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x1800433d9  movsxd  rcx, dword ptr [rax+3Ch]
0x1800433dd  add     rcx, [r14+40h]; unsigned __int64
0x1800433e1  mov     r9b, r13b; bool
0x1800433e4  mov     r8b, r13b; bool
0x1800433e7  mov     edx, edi; unsigned int
0x1800433e9  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x1800433ee  mov     dl, r13b
0x1800433f1  mov     rcx, rax
0x1800433f4  call    DacGetTargetAddrForHostAddr
0x1800433f9  mov     r9b, r13b; bool
0x1800433fc  mov     r8b, r13b; bool
0x1800433ff  mov     esi, 0F8h
0x180043404  mov     edx, esi; unsigned int
0x180043406  mov     rcx, rax; unsigned __int64
0x180043409  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x18004340e  mov     dl, r13b
0x180043411  mov     rcx, rax
0x180043414  call    DacGetTargetAddrForHostAddr
0x180043419  mov     rbx, rax
0x18004341c  mov     r9b, r13b; bool
0x18004341f  mov     r8b, r13b; bool
0x180043422  mov     edx, esi; unsigned int
0x180043424  mov     rcx, rax; unsigned __int64
0x180043427  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x18004342c  mov     ecx, [rax+50h]
0x18004342f  mov     [r14+80h], rcx
0x180043436  mov     r9b, r13b; bool
0x180043439  mov     r8b, r13b; bool
0x18004343c  mov     edx, esi; unsigned int
0x18004343e  mov     rcx, rbx; unsigned __int64
0x180043441  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x180043446  mov     rdi, rax
0x180043449  mov     r9b, r13b; bool
0x18004344c  mov     r8b, r13b; bool
0x18004344f  mov     edx, esi; unsigned int
0x180043451  mov     rcx, rbx; unsigned __int64
0x180043454  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x180043459  mov     rcx, [r14+88h]
0x180043460  mov     rdx, [rcx]
0x180043463  mov     r8d, [rax+50h]
0x180043467  mov     rax, [rdx+20h]
0x18004346b  mov     r9d, [rdi+38h]
0x18004346f  mov     rdx, [r15]
0x180043472  call    cs:__guard_dispatch_icall_fptr
0x180043478  mov     qword ptr [r14+228h], 1000h
0x180043483  mov     r9b, r13b; bool
0x180043486  mov     r8b, r13b; bool
0x180043489  mov     edx, esi; unsigned int
0x18004348b  mov     rcx, rbx; unsigned __int64
0x18004348e  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x180043493  movzx   edi, word ptr [rax+14h]
0x180043497  test    [r14+198h], r13b
0x18004349e  jz      loc_1800435F5
0x1800434a4  mov     rdx, rbx; unsigned __int64
0x1800434a7  mov     rcx, r14; this
0x1800434aa  call    ?DataPtrToDisplay@NativeImageDumper@@AEAA_K_K@Z
0x1800434af  mov     r8, rax
0x1800434b2  mov     rcx, [r14+88h]
0x1800434b9  mov     rdx, [rcx]
0x1800434bc  mov     rax, [rdx+0B8h]
0x1800434c3  lea     rdx, aImageNtHeaders
0x1800434ca  jmp     loc_1800435EB
0x1800434cf  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x1800434d4  movsxd  rcx, dword ptr [rax+3Ch]
0x1800434d8  add     rcx, [r14+40h]; unsigned __int64
0x1800434dc  mov     r9b, r13b; bool
0x1800434df  mov     r8b, r13b; bool
0x1800434e2  mov     edx, edi; unsigned int
0x1800434e4  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x1800434e9  mov     dl, r13b
0x1800434ec  mov     rcx, rax
0x1800434ef  call    DacGetTargetAddrForHostAddr
0x1800434f4  mov     r9b, r13b; bool
0x1800434f7  mov     r8b, r13b; bool
0x1800434fa  mov     edx, edi; unsigned int
0x1800434fc  mov     rcx, rax; unsigned __int64
0x1800434ff  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x180043504  mov     dl, r13b
0x180043507  mov     rcx, rax
0x18004350a  call    DacGetTargetAddrForHostAddr
0x18004350f  mov     rbx, rax
0x180043512  mov     r9b, r13b; bool
0x180043515  mov     r8b, r13b; bool
0x180043518  mov     edx, edi; unsigned int
0x18004351a  mov     rcx, rax; unsigned __int64
0x18004351d  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x180043522  mov     ecx, [rax+50h]
0x180043525  mov     [r14+80h], rcx
0x18004352c  mov     r9b, r13b; bool
0x18004352f  mov     r8b, r13b; bool
0x180043532  mov     edx, edi; unsigned int
0x180043534  mov     rcx, rbx; unsigned __int64
0x180043537  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x18004353c  mov     rsi, rax
0x18004353f  mov     r9b, r13b; bool
0x180043542  mov     r8b, r13b; bool
0x180043545  mov     edx, edi; unsigned int
0x180043547  mov     rcx, rbx; unsigned __int64
0x18004354a  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x18004354f  mov     rdi, rax
0x180043552  mov     r9b, r13b; bool
0x180043555  mov     r8b, r13b; bool
0x180043558  mov     edx, 108h; unsigned int
0x18004355d  mov     rcx, rbx; unsigned __int64
0x180043560  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z
0x180043565  mov     r10, rax
0x180043568  mov     rcx, [r14+88h]
0x18004356f  mov     rdx, [rcx]
0x180043572  mov     r8d, [rdi+50h]
0x180043576  mov     rax, [rdx+20h]
0x18004357a  mov     r9d, [rsi+38h]
  ... truncated ...
```
