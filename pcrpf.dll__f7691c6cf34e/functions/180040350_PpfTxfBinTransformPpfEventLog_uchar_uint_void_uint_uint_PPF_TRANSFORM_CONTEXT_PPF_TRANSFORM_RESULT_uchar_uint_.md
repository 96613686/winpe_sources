# PpfTxfBinTransformPpfEventLog(uchar *,uint,void *,uint,uint,PPF_TRANSFORM_CONTEXT *,PPF_TRANSFORM_RESULT *,uchar * *,uint *,uchar * *,uint *,uint *)

- ea: `0x180040350`
- end: `0x180041705`
- name: `?PpfTxfBinTransformPpfEventLog@@YAJPEAEIPEAXIIPEAUPPF_TRANSFORM_CONTEXT@@PEAW4PPF_TRANSFORM_RESULT@@PEAPEAEPEAI455@Z`
- size: `5045`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, const GUID *, unsigned int, char, struct PPF_TRANSFORM_CONTEXT *, enum PPF_TRANSFORM_RESULT *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, registry_config`

## callers

- `0x18001be88`

## callees

- `0x180003270`
- `0x180003640`
- `0x18000367c`
- `0x180009c64`
- `0x18000dfa0`
- `0x18000dfe0`
- `0x18000f4fc`
- `0x1800181fc`
- `0x18001af7c`
- `0x180028c28`
- `0x180028d5c`
- `0x180028f7c`
- `0x18002904c`
- `0x18002d5ec`
- `0x18002d85c`
- `0x1800327e8`
- `0x18003375c`
- `0x180040008`
- `0x180040060`
- `0x1800400f0`
- `0x180040350`
- `0x18004170c`
- `0x1800570a4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004141d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041502`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004152f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800415ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041617`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004141d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041502`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004152f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800415ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041617`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041431`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041516`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041543`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800415fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004162b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041431`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041516`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041543`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800415fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004162b`

## string_xrefs

- `0x1800407d8`: `Transform PPF event log configured to use DigestAlgID = 0x%x, DigestSize = 0x%x`
- `0x18004092e`: `Replacement event has the same digest`
- `0x180041316`: `txNrEvents = %u, replacedEvents = %u, sameDigestEvents = %u`
- `0x180041687`: `Transform is not applicable. txNrEvents = %u, replacedEvents = %u, sameDigestEvents = %u`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PpfTxfBinTransformPpfEventLog(
        unsigned __int8 *a1,
        unsigned int a2,
        const GUID *a3,
        unsigned int a4,
        char a5,
        struct PPF_TRANSFORM_CONTEXT *a6,
        enum PPF_TRANSFORM_RESULT *a7,
        unsigned __int8 **a8,
        unsigned int *a9,
        unsigned __int8 **a10,
        unsigned int *a11,
        unsigned int *a12)
{
  int v16; // eax
  unsigned int v17; // ebx
  _QWORD *v19; // rax
  _QWORD *v20; // rax
  int v21; // eax
  unsigned int v22; // edi
  _QWORD **v23; // rdx
  _QWORD *v24; // rcx
  _QWORD *v25; // rbx
  _QWORD **v26; // rcx
  _QWORD *v27; // rcx
  _QWORD *v28; // rbx
  int v29; // r15d
  bool v30; // bl
  unsigned __int16 v31; // r13
  unsigned __int16 v32; // r14
  int Current; // eax
  int v34; // eax
  bool v35; // al
  int IsSBVarSupported; // eax
  unsigned int v37; // esi
  int v38; // eax
  int v39; // eax
  char v40; // bl
  int v41; // eax
  int v42; // eax
  int v43; // eax
  unsigned __int16 v44; // dx
  int DigestAsString; // eax
  int v46; // eax
  int Next; // eax
  int v48; // eax
  int v49; // eax
  int v50; // eax
  _QWORD **v51; // rcx
  _QWORD *v52; // rcx
  _QWORD *v53; // rbx
  _QWORD **v54; // rcx
  _QWORD *v55; // rcx
  _QWORD *v56; // rbx
  _QWORD **v57; // rdx
  _QWORD *v58; // rcx
  _QWORD *v59; // rbx
  _QWORD **v60; // rcx
  _QWORD *v61; // rcx
  _QWORD *v62; // rbx
  unsigned int v63; // r15d
  _QWORD **v64; // rcx
  _QWORD *v65; // rcx
  _QWORD *v66; // rbx
  _QWORD **v67; // rcx
  _QWORD *v68; // rcx
  _QWORD *v69; // rbx
  _QWORD **v70; // rcx
  _QWORD *v71; // rcx
  _QWORD *v72; // rbx
  _QWORD **v73; // rcx
  _QWORD *v74; // rcx
  _QWORD *v75; // rbx
  _QWORD **v76; // rcx
  _QWORD *v77; // rcx
  _QWORD *v78; // rbx
  _QWORD **v79; // rcx
  _QWORD *v80; // rcx
  _QWORD *v81; // rbx
  _QWORD **v82; // rcx
  _QWORD *v83; // rcx
  _QWORD *v84; // rbx
  _QWORD **v85; // rcx
  _QWORD *v86; // rcx
  _QWORD *v87; // rbx
  _QWORD **v88; // rcx
  _QWORD *v89; // rcx
  _QWORD *v90; // rbx
  _QWORD **v91; // rdx
  _QWORD *v92; // rcx
  _QWORD *v93; // rbx
  _QWORD **v94; // rcx
  _QWORD *v95; // rcx
  _QWORD *v96; // rbx
  _QWORD **v97; // rdx
  _QWORD *v98; // rcx
  _QWORD *v99; // rbx
  _QWORD **v100; // rcx
  _QWORD *v101; // rcx
  _QWORD *v102; // rbx
  _QWORD **v103; // rdx
  _QWORD *v104; // rcx
  _QWORD *v105; // rbx
  _QWORD **v106; // rcx
  _QWORD *v107; // rcx
  _QWORD *v108; // rbx
  int v109; // ebx
  int v110; // esi
  int v111; // r14d
  int v112; // ebx
  void *v113; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int8 *v115; // rbx
  unsigned int v116; // ecx
  void *v117; // rbx
  HANDLE v118; // rax
  void *v119; // rbx
  HANDLE v120; // rax
  unsigned __int8 *v121; // rax
  void *v122; // rdi
  unsigned __int8 *v123; // rax
  HANDLE v124; // rax
  HANDLE v125; // rax
  unsigned int v126; // [rsp+20h] [rbp-E0h]
  int v127; // [rsp+20h] [rbp-E0h]
  int v128; // [rsp+20h] [rbp-E0h]
  int v129; // [rsp+20h] [rbp-E0h]
  int v130; // [rsp+20h] [rbp-E0h]
  struct TREE_VARIABLE_DATA **v131; // [rsp+28h] [rbp-D8h]
  struct TREE_VARIABLE_DATA **v132; // [rsp+28h] [rbp-D8h]
  unsigned __int8 **v133; // [rsp+30h] [rbp-D0h]
  unsigned __int8 **v134; // [rsp+30h] [rbp-D0h]
  unsigned int *v135; // [rsp+38h] [rbp-C8h]
  unsigned int *v136; // [rsp+38h] [rbp-C8h]
  unsigned __int8 **v137; // [rsp+40h] [rbp-C0h]
  unsigned __int8 **v138; // [rsp+40h] [rbp-C0h]
  bool v139[8]; // [rsp+50h] [rbp-B0h] BYREF
  void *v140[2]; // [rsp+58h] [rbp-A8h] BYREF
  void *v141[2]; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v142; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v143; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v144; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v145; // [rsp+84h] [rbp-7Ch] BYREF
  LPVOID lpMem; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int8 *v147; // [rsp+90h] [rbp-70h] BYREF
  unsigned int Size; // [rsp+98h] [rbp-68h] BYREF
  int Size_4; // [rsp+9Ch] [rbp-64h]
  int v150; // [rsp+A0h] [rbp-60h]
  unsigned int v151; // [rsp+A4h] [rbp-5Ch]
  unsigned int v152; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID v153; // [rsp+B0h] [rbp-50h] BYREF
  void *Buf1; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int8 *v155; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v156; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v157; // [rsp+D8h] [rbp-28h]
  __int64 v158; // [rsp+E8h] [rbp-18h]
  __int128 v159; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v160; // [rsp+100h] [rbp+0h]
  __int64 v161; // [rsp+110h] [rbp+10h]
  struct TREE_VARIABLE_DATA *v162; // [rsp+118h] [rbp+18h] BYREF
  struct TREE_VARIABLE_DATA *v163; // [rsp+120h] [rbp+20h] BYREF
  void *Buf2; // [rsp+128h] [rbp+28h] BYREF
  void *v165; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int8 **v166; // [rsp+138h] [rbp+38h]
  unsigned int *v167; // [rsp+140h] [rbp+40h]
  unsigned int *v168; // [rsp+148h] [rbp+48h]
  enum PPF_TRANSFORM_RESULT *v169; // [rsp+150h] [rbp+50h]
  unsigned __int8 *v170; // [rsp+158h] [rbp+58h] BYREF
  unsigned __int8 *v171; // [rsp+160h] [rbp+60h] BYREF
  unsigned int *v172; // [rsp+168h] [rbp+68h]
  char v173[16]; // [rsp+170h] [rbp+70h] BYREF
  char v174; // [rsp+180h] [rbp+80h]
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  v169 = a7;
  v166 = a8;
  v167 = a9;
  v168 = a11;
  v172 = a12;
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x84u,
    "PpfTraceFunctionEntryExit::PpfTraceFunctionEntryExit",
    "Entering %hs",
    "PpfTxfBinTransformPpfEventLog");
  *a8 = 0;
  *v167 = 0;
  if ( a10 )
  {
    *a10 = 0;
    *v168 = 0;
  }
  if ( a12 )
    *a12 = 0;
  *(_DWORD *)a7 = 0;
  v170 = 0;
  v152 = 0;
  v16 = PpfTxfBinValidateTransform(a3, a4, &v170, &v152);
  v17 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCB,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\txfbin\\ppftxfbin.cpp",
      (const char *)(unsigned int)v16,
      v126);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfTxfBinTransformPpfEventLog");
    return v17;
  }
  if ( *(_DWORD *)&a3[1].Data2 != 1 )
  {
    v17 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xD1,
            (unsigned int)"onecore\\base\\ngscb\\pcrpf\\txfbin\\ppftxfbin.cpp",
            (const char *)0x32,
            v126);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfTxfBinTransformPpfEventLog");
    return v17;
  }
  v141[1] = 0;
  v19 = operator new(0x20u);
  *v19 = v19;
  v19[1] = v19;
  v141[0] = v19;
  v140[1] = 0;
  v20 = operator new(0x20u);
  *v20 = v20;
  v20[1] = v20;
  v140[0] = v20;
  v156 = 0;
  v157 = 0;
  v158 = 0;
  v139[1] = 0;
  v21 = PpfEvtLogIteratorInitialize(a1, a2, &v156, &v139[1]);
  if ( v21 < 0 )
  {
    v22 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0xE7,
            (unsigned int)"onecore\\base\\ngscb\\pcrpf\\txfbin\\ppftxfbin.cpp",
            (const char *)(unsigned int)v21,
            v126);
    v23 = (_QWORD **)v140[0];
    **((_QWORD **)v140[0] + 1) = 0;
    v24 = *v23;
    if ( *v23 )
    {
      do
      {
        v25 = (_QWORD *)*v24;
        operator delete(v24, 0x20u);
        v24 = v25;
      }
      while ( v25 );
    }
    operator delete(v140[0], 0x20u);
    v26 = (_QWORD **)v141[0];
    **((_QWORD **)v141[0] + 1) = 0;
    v27 = *v26;
    if ( v27 )
    {
      do
      {
        v28 = (_QWORD *)*v27;
        operator delete(v27, 0x20u);
        v27 = v28;
      }
      while ( v28 );
    }
    operator delete(v141[0], 0x20u);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfTxfBinTransformPpfEventLog");
    return v22;
  }
  v29 = 0;
  Size_4 = 0;
  v150 = 0;
  v139[3] = 0;
  v151 = 0;
  v145 = 0;
  v30 = v139[1];
  v31 = WORD1(v158);
  v32 = v158;
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\txfbin\\ppftxfbin.cpp",
    0xE9u,
    "PpfTxfBinTransformPpfEventLog",
    "Transforming PPF event log of size 0x%x B, DigestAlgID = 0x%x, DigestSize = 0x%x, has events: %u",
    a2,
    (unsigned __int16)v158,
    WORD1(v158),
    v139[1]);
  if ( v30 )
  {
    while ( 1 )
    {
      v144 = 0;
      v143 = 0;
      v155 = 0;
      v142 = 0;
      v147 = 0;
      Current = PpfEvtLogIteratorGetCurrent(
                  (unsigned int)&v156,
                  (unsigned int)&v144,
                  (unsigned int)&v143,
                  (unsigned int)&v155,
                  (__int64)&v142,
                  (__int64)&v147);
      if ( Current < 0 )
      {
        v22 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0xF2,
                (unsigned int)"onecore\\base\\ngscb\\pcrpf\\txfbin\\ppftxfbin.cpp",
                (const char *)(unsigned int)Current,
                v127);
        v103 = (_QWORD **)v140[0];
        **((_QWORD **)v140[0] + 1) = 0;
        v104 = *v103;
        if ( *v103 )
        {
          do
          {
            v105 = (_QWORD *)*v104;
            operator delete(v104, 0x20u);
            v104 = v105;
          }
          while ( v105 );
        }
        operator delete(v140[0], 0x20u);
        v106 = (_QWORD **)v141[0];
        **((_QWORD **)v141[0] + 1) = 0;
        v107 = *v106;
        if ( v107 )
        {
          do
          {
            v108 = (_QWORD *)*v107;
            operator delete(v107, 0x20u);
            v107 = v108;
          }
          while ( v108 );
        }
        goto LABEL_108;
      }
      v139[0] = 0;
      v163 = 0;
      Buf1 = 0;
      Size = 0;
      v34 = PpfhCheckForAndValidateSBVarEvent(
              v144,
              v143,
              v147,
              v142,
              v139,
              &v163,
              (unsigned __int8 **)&Buf1,
              &Size,
              0,
              0);
      if ( v34 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xFE,
          (unsigned int)"onecore\\base\\ngscb\\pcrpf\\txfbin\\ppftxfbin.cpp",
          (const char *)(unsigned int)v34,
          v128);
      v35 = v139[0];
      if ( !v139[0] )
        goto LABEL_54;
      if ( (a5 & 1) == 0 )
      {
        v139[0] = 0;
        IsSBVarSupported = PpfhIsSBVarSupported((unsigned __int8 *)Buf1, Size, v139);
        v37 = IsSBVarSupported;
        if ( IsSBVarSupported < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x104,
            (unsigned int)"onecore\\base\\ngscb\\pcrpf\\txfbin\\ppftxfbin.cpp",
            (const char *)(unsigned int)IsSBVarSupported,
            v128);
          v51 = (_QWORD **)v140[0];
          **((_QWORD **)v140[0] + 1) = 0;
          v52 = *v51;
          if ( v52 )
          {
            do
            {
              v53 = (_QWORD *)*v52;
              operator delete(v52, 0x20u);
              v52 = v53;
            }
            while ( v53 );
          }
          operator delete(v140[0], 0x20u);
          v54 = (_QWORD **)v141[0];
          **((_QWORD **)v141[0] + 1) = 0;
          v55 = *v54;
          if ( v55 )
          {
            do
            {
              v56 = (_QWORD *)*v55;
              operator delete(v55, 0x20u);
              v55 = v56;
            }
            while ( v56 );
          }
LABEL_62:
          operator delete(v141[0], 0x20u);
          PpfTraceLogFormat(
            "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
            0x89u,
            "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
            "Leaving %hs",
            "PpfTxfBinTransformPpfEventLog");
          return v37;
        }
        v35 = v139[0];
      }
      if ( v35 )
      {
        v159 = 0;
        v160 = 0;
        v161 = 0;
        v139[0] = 0;
        v38 = PpfEvtLogIteratorInitialize(v170, v152, &v159, v139);
        if ( v38 < 0 )
        {
          v22 = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x10E,
                  (unsigned int)"onecore\\base\\ngscb\\pcrpf\\txfbin\\ppftxfbin.cpp",
                  (const char *)(unsigned int)v38,
                  v128);
          v97 = (_QWORD **)v140[0];
          **((_QWORD **)v140[0] + 1) = 0;
          v98 = *v97;
          if ( *v97 )
          {
            do
            {
              v99 = (_QWORD *)*v98;
              operator delete(v98, 0x20u);
              v98 = v99;
            }
            while ( v99 );
          }
          operator delete(v140[0], 0x20u);
          v100 = (_QWORD **)v141[0];
          **((_QWORD **)v141[0] + 1) = 0;
          v101 = *v100;
          if ( v101 )
          {
            do
            {
              v102 = (_QWORD *)*v101;
              operator delete(v101, 0x20u);
              v101 = v102;
            }
            while ( v102 );
          }
          goto LABEL_108;
        }
        v145 = HIDWORD(v161);
        if ( (_WORD)v161 != v32 )
        {
          v39 = PpfEvtLogIteratorSetPreferredHashAlgID(&v159, v32);
          if ( v39 == -1073741637 )
          {
            LODWORD(v137) = v31;
            LODWORD(v135) = v32;
            LODWORD(v133) = WORD1(v161);
            LODWORD(v131) = (unsigned __int16)v161;
            v63 = -920125440;
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0x119,
              (unsigned int)"onecore\\base\\ngscb\\pcrpf\\txfbin\\ppftxfbin.cpp",
              (const char *)0xC9280000LL,
              (int)"Transform PPF event log does not support system selected algorithm. transformDigestAlgID = 0x%x, tran"
                   "sformDigestSize = 0x%x, logDigestAlgID = 0x%x, logDigestSize = 0x%x",
              (const char *)v131,
              v133,
              v135,
              v137);
            v64 = (_QWORD **)v140[0];
            **((_QWORD **)v140[0] + 1) = 0;
            v65 = *v64;
            if ( v65 )
            {
              do
              {
                v66 = (_QWORD *)*v65;
                operator delete(v65, 0x20u);
                v65 = v66;
              }
              while ( v66 );
            }
            operator delete(v140[0], 0x20u);
            v67 = (_QWORD **)v141[0];
            **((_QWORD **)v141[0] + 1) = 0;
            v68 = *v67;
            if ( v68 )
            {
              do
              {
                v69 = (_QWORD *)*v68;
                operator delete(v68, 0x20u);
                v68 = v69;
              }
              while ( v69 );
            }
LABEL_73:
            operator delete(v141[0], 0x20u);
            PpfTraceLogFormat(
              "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
              0x89u,
              "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
              "Leaving %hs",
              "PpfTxfBinTransformPpfEventLog");
            return v63;
          }
          if ( v39 < 0 )
          {
            v22 = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x11B,
                    (unsigned int)"onecore\\base\\ngscb\\pcrpf\\txfbin\\ppftxfbin.cpp",
                    (const char *)(unsigned int)v39,
                    v128);
            v57 = (_QWORD **)v140[0];
            **((_QWORD **)v140[0] + 1) = 0;
            v58 = *v57;
            if ( *v57 )
            {
              do
              {
                v59 = (_QWORD *)*v58;
                operator delete(v58, 0x20u);
                v58 = v59;
              }
              while ( v59 );
            }
            operator delete(v140[0], 0x20u);
            v60 = (_QWORD **)v141[0];
            **((_QWORD **)v141[0] + 1) = 0;
            v61 = *v60;
            if ( v61 )
            {
              do
              {
                v62 = (_QWORD *)*v61;
                operator delete(v61, 0x20u);
                v61 = v62;
              }
              while ( v62 );
            }
LABEL_108:
            operator delete(v141[0], 0x20u);
            PpfTraceLogFormat(
              "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
              0x89u,
              "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
              "Leaving %hs",
              "PpfTxfBinTransformPpfEventLog");
            return v22;
          }
          PpfTraceLogFormat(
            "onecore\\base\\ngscb\\pcrpf\\txfbin\\ppftxfbin.cpp",
            0x11Cu,
            "PpfTxfBinTransformPpfEventLog",
            "Transform PPF event log configured to use DigestAlgID = 0x%x, DigestSize = 0x%x",
            (unsigned __int16)v161,
            WORD1(v161));
        }
        v40 = 0;
        while ( v139[0] )
        {
          v142 = 0;
          v143 = 0;
          v165 = 0;
          v144 = 0;
          v171 = 0;
          v41 = PpfEvtLogIteratorGetCurrent(
                  (unsigned int)&v159,
                  (unsigned int)&v142,
                  (unsigned int)&v143,
                  (unsigned int)&v165,
                  (__int64)&v144,
                  (__int64)&v171);
          if ( v41 < 0 )
          {
            v22 = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x126,
                    (unsigned int)"onecore\\base\\ngscb\\pcrpf\\txfbin\\ppftxfbin.cpp",
                    (const char *)(unsigned int)v41,
                    v129);
            v91 = (_QWORD **)v140[0];
            **((_QWORD **)v140[0] + 1) = 0;
            v92 = *v91;
            if ( *v91 )
            {
              do
              {
                v93 = (_QWORD *)*v92;
                operator delete(v92, 0x20u);
                v92 = v93;
              }
              while ( v93 );
            }
            operator delete(v140[0], 0x20u);
            v94 = (_QWORD **)v141[0];
            **((_QWORD **)v141[0] + 1) = 0;
            v95 = *v94;
            if ( v95 )
            {
              do
              {
                v96 = (_QWORD *)*v95;
                operator delete(v95, 0x20u);
                v95 = v96;
              }
              while ( v96 );
            }
            goto LABEL_108;
          }
          v42 = v150 + 1;
          if ( v139[3] )
            v42 = v150;
          v150 = v42;
          v139[2] = 0;
          v162 = 0;
          Buf2 = 0;
          LODWORD(v147) = 0;
          v43 = PpfhCheckForAndValidateSBVarEvent(
                  v142,
                  v143,
                  v171,
                  v144,
                  &v139[2],
                  &v162,
                  (unsigned __int8 **)&Buf2,
                  (unsigned int *)&v147,
                  0,
                  0);
          if ( v43 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x131,
              (unsigned int)"onecore\\base\\ngscb\\pcrpf\\txfbin\\ppftxfbin.cpp",
              (const char *)(unsigned int)v43,
              v128);
          if ( v139[2]
            && *(_QWORD *)v163 == *(_QWORD *)v162
            && *((_QWORD *)v163 + 1) == *((_QWORD *)v162 + 1)
            && Size == (_DWORD)v147
            && !memcmp_0(Buf1, Buf2, Size) )
          {
            if ( !v165 )
            {
              LODWORD(v138) = v31;
              LODWORD(v136) = v32;
              LODWORD(v134) = WORD1(v161);
              LODWORD(v132) = (unsigned __int16)v161;
              v63 = -920125436;
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x13F,
                (unsigned int)"onecore\\base\\ngscb\\pcrpf\\txfbin\\ppftxfbin.cpp",
                (const char *)0xC9280004LL,
                (int)"Transform PPF event log event does not have a digest for system selected algorithm. transformDigest"
                     "AlgID = 0x%x, transformDigestSize = 0x%x, logDigestAlgID = 0x%x, logDigestSize = 0x%x",
                (const char *)v132,
                v134,
                v136,
                v138);
              v82 = (_QWORD **)v140[0];
              **((_QWORD **)v140[0] + 1) = 0;
              v83 = *v82;
              if ( v83 )
              {
                do
                {
                  v84 = (_QWORD *)*v83;
                  operator delete(v83, 0x20u);
                  v83 = v84;
                }
                while ( v84 );
              }
              operator delete(v140[0], 0x20u);
              v85 = (_QWORD **)v141[0];
              **((_QWORD **)v141[0] + 1) = 0;
              v86 = *v85;
              if ( v86 )
              {
                do
                {
                  v87 = (_QWORD *)*v86;
                  operator delete(v86, 0x20u);
                  v86 = v87;
                }
                while ( v87 );
              }
              goto LABEL_73;
            }
            if ( !memcmp_0(v155, v165, v31) )
            {
              PpfTraceLogFormat(
                "onecore\\base\\ngscb\\pcrpf\\txfbin\\ppftxfbin.cpp",
                0x143u,
                "PpfTxfBinTransformPpfEventLog",
                "Replacement event has the same digest");
              ++Size_4;
            }
            else
            {
              *(_OWORD *)v173 = 0;
              v174 = 0;
              DigestAsString = PpfhGetDigestAsString(v155, v44, v173);
              v37 = DigestAsString;
              if ( DigestAsString < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x14B,
                  (unsigned int)"onecore\\base\\ngscb\\pcrpf\\txfbin\\ppftxfbin.cpp",
                  (const char *)(unsigned int)DigestAsString,
                  v128);
                v76 = (_QWORD **)v140[0];
                **((_QWORD **)v140[0] + 1) = 0;
                v77 = *v76;
                if ( v77 )
                {
                  do
                  {
                    v78 = (_QWORD *)*v77;
                    operator delete(v77, 0x20u);
                    v77 = v78;
                  }
                  while ( v78 );
                }
                operator delete(v140[0], 0x20u);
                v79 = (_QWORD **)v141[0];
                **((_QWORD **)v141[0] + 1) = 0;
                v80 = *v79;
                if ( v80 )
                {
                  do
                  {
                    v81 = (_QWORD *)*v80;
                    operator delete(v80, 0x20u);
                    v80 = v81;
                  }
                  while ( v81 );
                }
                goto LABEL_62;
              }
              PpfTraceLogFormat(
                "onecore\\base\\ngscb\\pcrpf\\txfbin\\ppftxfbin.cpp",
                0x14Cu,
                "PpfTxfBinTransformPpfEventLog",
                "Replacing event with digest %hs",
                v173);
              v46 = AddToPpfEventLogList(v141, v160, DWORD2(v160));
              v37 = v46;
              if ( v46 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x14F,
                  (unsigned int)"onecore\\base\\ngscb\\pcrpf\\txfbin\\ppftxfbin.cpp",
                  (const char *)(unsigned int)v46,
                  v128);
                v70 = (_QWORD **)v140[0];
                **((_QWORD **)v140[0] + 1) = 0;
                v71 = *v70;
                if ( v71 )
                {
                  do
                  {
                    v72 = (_QWORD *)*v71;
                    operator delete(v71, 0x20u);
                    v71 = v72;
                  }
                  while ( v72 );
                }
                operator delete(v140[0], 0x20u);
                v73 = (_QWORD **)v141[0];
                **((_QWORD **)v141[0] + 1) = 0;
                v74 = *v73;
                if ( v74 )
                {
                  do
                  {
                    v75 = (_QWORD *)*v74;
                    operator delete(v74, 0x20u);
                    v74 = v75;
                  }
                  while ( v75 );
                }
                goto LABEL_62;
              }
              v40 = 1;
              ++v29;
              v151 |= 0x80u;
            }
          }
          Next = PpfEvtLogIteratorTryGetNext(&v159, v139);
          v37 = Next;
          if ( Next < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x157,
              (unsigned int)"onecore\\base\\ngscb\\pcrpf\\txfbin\\ppftxfbin.cpp",
              (const char *)(unsigned int)Next,
              v128);
            v88 = (_QWORD **)v140[0];
            **((_QWORD **)v140[0] + 1) = 0;
            v89 = *v88;
            if ( v89 )
            {
              do
              {
                v90 = (_QWORD *)*v89;
                operator delete(v89, 0x20u);
                v89 = v90;
              }
              while ( v90 );
            }
            operator delete(v140[0], 0x20u);
            std::list<std::pair<unsigned char *,unsigned int>>::~list<std::pair<unsigned char *,unsigned int>>(v141);
            PpfTraceLogFormat(
              "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
              0x89u,
              "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
              "Leaving %hs",
              "PpfTxfBinTransformPpfEventLog");
            return v37;
          }
        }
        v139[3] = 1;
        if ( !v40 )
          goto LABEL_54;
        if ( a10 )
        {
          v48 = AddToPpfEventLogList(v140, v157, DWORD2(v157));
          v17 = v48;
          if ( v48 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x161,
              (unsigned int)"onecore\\base\\ngscb\\pcrpf\\txfbin\\ppftxfbin.cpp",
              (const char *)(unsigned int)v48,
              v128);
            std::list<std::pair<unsigned char *,unsigned int>>::~list<std::pair<unsigned char *,unsigned int>>(v140);
            std::list<std::pair<unsigned char *,unsigned int>>::~list<std::pair<unsigned char *,unsigned int>>(v141);
            PpfTraceLogFormat(
              "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
              0x89u,
              "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
              "Leaving %hs",
              "PpfTxfBinTransformPpfEventLog");
            return v17;
          }
        }
      }
      else
      {
LABEL_54:
        v49 = AddToPpfEventLogList(v141, v157, DWORD2(v157));
        v17 = v49;
        if ( v49 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x167,
            (unsigned int)"onecore\\base\\ngscb\\pcrpf\\txfbin\\ppftxfbin.cpp",
            (const char *)(unsigned int)v49,
            v128);
          std::list<std::pair<unsigned char *,unsigned int>>::~list<std::pair<unsigned char *,unsigned int>>(v140);
          std::list<std::pair<unsigned char *,unsigned int>>::~list<std::pair<unsigned char *,unsigned int>>(v141);
          PpfTraceLogFormat(
            "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
            0x89u,
            "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
            "Leaving %hs",
            "PpfTxfBinTransformPpfEventLog");
          return v17;
        }
      }
      v50 = PpfEvtLogIteratorTryGetNext(&v156, &v139[1]);
      v17 = v50;
      if ( v50 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x16A,
          (unsigned int)"onecore\\base\\ngscb\\pcrpf\\txfbin\\ppftxfbin.cpp",
          (const char *)(unsigned int)v50,
          v128);
        std::list<std::pair<unsigned char *,unsigned int>>::~list<std::pair<unsigned char *,unsigned int>>(v140);
        std::list<std::pair<unsigned char *,unsigned int>>::~list<std::pair<unsigned char *,unsigned int>>(v141);
        PpfTraceLogFormat(
          "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
          0x89u,
          "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
          "Leaving %hs",
          "PpfTxfBinTransformPpfEventLog");
        return v17;
      }
      if ( !v139[1] )
        break;
      v31 = WORD1(v158);
      v32 = v158;
    }
  }
  v109 = Size_4;
  v110 = v150;
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\txfbin\\ppftxfbin.cpp",
    0x17Au,
    "PpfTxfBinTransformPpfEventLog",
    "txNrEvents = %u, replacedEvents = %u, sameDigestEvents = %u",
    v150,
    v29,
    Size_4);
  if ( v110 != v109 + v29 )
  {
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\txfbin\\ppftxfbin.cpp",
      0x18Bu,
      "PpfTxfBinTransformPpfEventLog",
      "Transform is not applicable. txNrEvents = %u, replacedEvents = %u, sameDigestEvents = %u",
      v110,
      v29,
      v109);
    *(_DWORD *)v169 = 2;
    std::list<std::pair<unsigned char *,unsigned int>>::~list<std::pair<unsigned char *,unsigned int>>(v140);
    std::list<std::pair<unsigned char *,unsigned int>>::~list<std::pair<unsigned char *,unsigned int>>(v141);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfTxfBinTransformPpfEventLog");
    return 0;
  }
  v111 = 1;
  if ( !v29 )
    v111 = 3;
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\txfbin\\ppftxfbin.cpp",
    0x184u,
    "PpfTxfBinTransformPpfEventLog",
    "TransformResult = %u",
    v111);
  v112 = HIDWORD(v158);
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\txfbin\\ppftxfbin.cpp",
    0x197u,
    "PpfTxfBinTransformPpfEventLog",
    "Current SupportedDigestAlgIDBitmap: %u",
    HIDWORD(v158));
  HIDWORD(v158) = v145 | v112;
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\txfbin\\ppftxfbin.cpp",
    0x199u,
    "PpfTxfBinTransformPpfEventLog",
    "Adjusted SupportedDigestAlgIDBitmap: %u",
    v145 | v112);
  lpMem = 0;
  LODWORD(v147) = 0;
  *(_QWORD *)v173 = &lpMem;
  *(_QWORD *)&v173[8] = 0;
  v174 = 1;
  v37 = CreatePpfEventLogFromList(&v156, v141, &v173[8], &v147);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::process_heap_deleter>>(v173);
  if ( (v37 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19F,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\txfbin\\ppftxfbin.cpp",
      (const char *)v37,
      v130);
    v113 = lpMem;
    lpMem = 0;
    if ( v113 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v113);
    }
    goto LABEL_115;
  }
  v115 = 0;
  v153 = 0;
  v116 = 0;
  v145 = 0;
  if ( !v29 || !a10 )
  {
LABEL_125:
    *(_DWORD *)v169 = v111;
    v121 = (unsigned __int8 *)lpMem;
    v122 = 0;
    lpMem = 0;
    *v166 = v121;
    *v167 = (unsigned int)v147;
    if ( a10 )
    {
      v123 = v115;
      v115 = 0;
      *a10 = v123;
      *v168 = v116;
    }
    if ( v172 )
      *v172 = v151;
    v153 = 0;
    if ( v115 )
    {
      v124 = GetProcessHeap();
      HeapFree(v124, 0, v115);
      v122 = lpMem;
    }
    lpMem = 0;
    if ( v122 )
    {
      v125 = GetProcessHeap();
      HeapFree(v125, 0, v122);
    }
    std::list<std::pair<unsigned char *,unsigned int>>::~list<std::pair<unsigned char *,unsigned int>>(v140);
    std::list<std::pair<unsigned char *,unsigned int>>::~list<std::pair<unsigned char *,unsigned int>>(v141);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfTxfBinTransformPpfEventLog");
    return 0;
  }
  *(_QWORD *)v173 = &v153;
  *(_QWORD *)&v173[8] = 0;
  v174 = 1;
  v37 = CreatePpfEventLogFromList(&v156, v140, &v173[8], &v145);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::process_heap_deleter>>(v173);
  if ( (v37 & 0x80000000) == 0 )
  {
    v115 = (unsigned __int8 *)v153;
    v116 = v145;
    goto LABEL_125;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1A8,
    (unsigned int)"onecore\\base\\ngscb\\pcrpf\\txfbin\\ppftxfbin.cpp",
    (const char *)v37,
    v130);
  v117 = v153;
  v153 = 0;
  if ( v117 )
  {
    v118 = GetProcessHeap();
    HeapFree(v118, 0, v117);
  }
  v119 = lpMem;
  lpMem = 0;
  if ( v119 )
  {
    v120 = GetProcessHeap();
    HeapFree(v120, 0, v119);
  }
LABEL_115:
  std::list<std::pair<unsigned char *,unsigned int>>::~list<std::pair<unsigned char *,unsigned int>>(v140);
  std::list<std::pair<unsigned char *,unsigned int>>::~list<std::pair<unsigned char *,unsigned int>>(v141);
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x89u,
    "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
    "Leaving %hs",
    "PpfTxfBinTransformPpfEventLog");
  return v37;
}

```

## disassembly

```asm
0x180040350  push    rbp
0x180040352  push    rbx
0x180040353  push    rsi
0x180040354  push    rdi
0x180040355  push    r12
0x180040357  push    r13
0x180040359  push    r14
0x18004035b  push    r15
0x18004035d  lea     rbp, [rsp-98h]
0x180040365  sub     rsp, 198h
0x18004036c  mov     rax, cs:__security_cookie
0x180040373  xor     rax, rsp
0x180040376  mov     [rbp+0D0h+var_48], rax
0x18004037d  mov     ebx, r9d
0x180040380  mov     rdi, r8
0x180040383  mov     esi, edx
0x180040385  mov     r14, rcx
0x180040388  mov     r13, [rbp+0D0h+arg_30]
0x18004038f  mov     [rbp+0D0h+var_80], r13
0x180040393  mov     rax, [rbp+0D0h+arg_38]
0x18004039a  mov     [rbp+0D0h+var_98], rax
0x18004039e  mov     rax, [rbp+0D0h+arg_40]
0x1800403a5  mov     [rbp+0D0h+var_90], rax
0x1800403a9  mov     r12, [rbp+0D0h+arg_48]
0x1800403b0  mov     rax, [rbp+0D0h+arg_50]
0x1800403b7  mov     [rbp+0D0h+var_88], rax
0x1800403bb  mov     r15, [rbp+0D0h+arg_58]
0x1800403c2  mov     [rbp+0D0h+var_68], r15
0x1800403c6  lea     rax, aPpftxfbintrans; "PpfTxfBinTransformPpfEventLog"
0x1800403cd  mov     [rsp+1D0h+var_1B0], rax; int
0x1800403d2  lea     r9, aEnteringHs; "Entering %hs"
0x1800403d9  lea     r8, aPpftracefuncti; "PpfTraceFunctionEntryExit::PpfTraceFunc"...
0x1800403e0  mov     edx, 84h; unsigned int
0x1800403e5  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800403ec  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x1800403f1  xor     ecx, ecx
0x1800403f3  mov     rax, [rbp+0D0h+var_98]
0x1800403f7  mov     [rax], rcx
0x1800403fa  mov     rax, [rbp+0D0h+var_90]
0x1800403fe  mov     [rax], ecx
0x180040400  test    r12, r12
0x180040403  jz      short loc_18004040F
0x180040405  mov     [r12], rcx
0x180040409  mov     rax, [rbp+0D0h+var_88]
0x18004040d  mov     [rax], ecx
0x18004040f  test    r15, r15
0x180040412  jz      short loc_180040417
0x180040414  mov     [r15], ecx
0x180040417  mov     [r13+0], ecx
0x18004041b  xor     r13d, r13d
0x18004041e  mov     [rbp+0D0h+var_78], r13
0x180040422  mov     [rbp+0D0h+var_128], r13d
0x180040426  lea     r9, [rbp+0D0h+var_128]; unsigned int *
0x18004042a  lea     r8, [rbp+0D0h+var_78]; unsigned __int8 **
0x18004042e  mov     edx, ebx; unsigned int
0x180040430  mov     rcx, rdi; void *
0x180040433  call    ?PpfTxfBinValidateTransform@@YAJPEAXIPEAPEAEPEAI@Z; PpfTxfBinValidateTransform(void *,uint,uchar * *,uint *)
0x180040438  mov     ebx, eax
0x18004043a  test    eax, eax
0x18004043c  jns     short loc_18004048D
0x18004043e  mov     rcx, [rbp+0D8h]; this
0x180040445  mov     r9d, eax; char *
0x180040448  lea     r8, aOnecoreBaseNgs; "onecore\\base\\ngscb\\pcrpf\\txfbin\\pp"...
0x18004044f  mov     edx, 0CBh; void *
0x180040454  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040459  nop
0x18004045a  lea     r8, aPpftxfbintrans; "PpfTxfBinTransformPpfEventLog"
0x180040461  mov     [rsp+1D0h+var_1B0], r8
0x180040466  lea     r9, aLeavingHs; "Leaving %hs"
0x18004046d  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x180040474  mov     edx, 89h; unsigned int
0x180040479  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180040480  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180040485  nop
0x180040486  mov     eax, ebx
0x180040488  jmp     loc_1800416E1
0x18004048d  cmp     dword ptr [rdi+14h], 1
0x180040491  jz      short loc_1800404E1
0x180040493  mov     rcx, [rbp+0D8h]; this
0x18004049a  mov     r9d, 32h ; '2'; char *
0x1800404a0  lea     r8, aOnecoreBaseNgs; "onecore\\base\\ngscb\\pcrpf\\txfbin\\pp"...
0x1800404a7  mov     edx, 0D1h; void *
0x1800404ac  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800404b1  mov     ebx, eax
0x1800404b3  lea     r8, aPpftxfbintrans; "PpfTxfBinTransformPpfEventLog"
0x1800404ba  mov     [rsp+1D0h+var_1B0], r8
0x1800404bf  lea     r9, aLeavingHs; "Leaving %hs"
0x1800404c6  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x1800404cd  mov     edx, 89h; unsigned int
0x1800404d2  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800404d9  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x1800404de  nop
0x1800404df  jmp     short loc_180040486
0x1800404e1  mov     [rsp+1D0h+var_168], r13
0x1800404e6  mov     [rsp+1D0h+var_160], r13
0x1800404eb  mov     r15d, 20h ; ' '
0x1800404f1  mov     ecx, r15d; Size
0x1800404f4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800404f9  mov     [rax], rax
0x1800404fc  mov     [rax+8], rax
0x180040500  mov     [rsp+1D0h+var_168], rax
0x180040505  mov     [rsp+1D0h+var_178], r13
0x18004050a  mov     [rsp+1D0h+var_170], r13
0x18004050f  mov     ecx, r15d; Size
0x180040512  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180040517  mov     [rax], rax
0x18004051a  mov     [rax+8], rax
0x18004051e  mov     [rsp+1D0h+var_178], rax
0x180040523  xorps   xmm0, xmm0
0x180040526  xor     eax, eax
0x180040528  movups  [rbp+0D0h+var_108], xmm0
0x18004052c  movups  [rbp+0D0h+var_F8], xmm0
0x180040530  mov     [rbp+0D0h+var_E8], rax
0x180040534  mov     [rsp+1D0h+var_180+1], r13b
0x180040539  lea     r9, [rsp+1D0h+var_180+1]
0x18004053e  lea     r8, [rbp+0D0h+var_108]
0x180040542  mov     edx, esi
0x180040544  mov     rcx, r14
0x180040547  call    PpfEvtLogIteratorInitialize
0x18004054c  test    eax, eax
0x18004054e  jns     loc_18004060D
0x180040554  mov     rcx, [rbp+0D8h]; this
0x18004055b  mov     r9d, eax; char *
0x18004055e  lea     r8, aOnecoreBaseNgs; "onecore\\base\\ngscb\\pcrpf\\txfbin\\pp"...
0x180040565  mov     edx, 0E7h; void *
0x18004056a  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18004056f  mov     edi, eax
0x180040571  mov     rdx, [rsp+1D0h+var_178]
0x180040576  mov     rcx, [rdx+8]
0x18004057a  mov     [rcx], r13
0x18004057d  mov     rcx, [rdx]; void *
0x180040580  test    rcx, rcx
0x180040583  jz      short loc_180040598
0x180040585  mov     rbx, [rcx]
0x180040588  mov     rdx, r15; unsigned __int64
0x18004058b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180040590  mov     rcx, rbx
0x180040593  test    rbx, rbx
0x180040596  jnz     short loc_180040585
0x180040598  mov     rdx, r15; unsigned __int64
0x18004059b  mov     rcx, [rsp+1D0h+var_178]; void *
0x1800405a0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800405a5  mov     rcx, [rsp+1D0h+var_168]
0x1800405aa  mov     rax, [rcx+8]
0x1800405ae  mov     [rax], r13
0x1800405b1  mov     rcx, [rcx]; void *
0x1800405b4  test    rcx, rcx
0x1800405b7  jz      short loc_1800405CC
0x1800405b9  mov     rbx, [rcx]
0x1800405bc  mov     rdx, r15; unsigned __int64
0x1800405bf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800405c4  mov     rcx, rbx
0x1800405c7  test    rbx, rbx
0x1800405ca  jnz     short loc_1800405B9
0x1800405cc  mov     rdx, r15; unsigned __int64
0x1800405cf  mov     rcx, [rsp+1D0h+var_168]; void *
0x1800405d4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800405d9  nop
0x1800405da  lea     r8, aPpftxfbintrans; "PpfTxfBinTransformPpfEventLog"
0x1800405e1  mov     [rsp+1D0h+var_1B0], r8
0x1800405e6  lea     r9, aLeavingHs; "Leaving %hs"
0x1800405ed  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x1800405f4  mov     edx, 89h; unsigned int
0x1800405f9  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180040600  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180040605  nop
0x180040606  mov     eax, edi
0x180040608  jmp     loc_1800416E1
0x18004060d  mov     r15d, r13d
0x180040610  mov     dword ptr [rbp+0D0h+Size+4], r13d
0x180040614  mov     [rbp+0D0h+var_130], r13d
0x180040618  mov     [rsp+1D0h+var_180+3], r13b
0x18004061d  mov     [rbp+0D0h+var_12C], r13d
0x180040621  mov     [rbp+0D0h+var_14C], r13d
0x180040625  movzx   ebx, [rsp+1D0h+var_180+1]
0x18004062a  movzx   r13d, word ptr [rbp+0D0h+var_E8+2]
0x18004062f  movzx   r14d, word ptr [rbp+0D0h+var_E8]
0x180040634  mov     dword ptr [rsp+1D0h+var_198], ebx
0x180040638  mov     dword ptr [rsp+1D0h+var_1A0], r13d
0x18004063d  mov     dword ptr [rsp+1D0h+var_1A8], r14d
0x180040642  mov     dword ptr [rsp+1D0h+var_1B0], esi
0x180040646  lea     r9, aTransformingPp; "Transforming PPF event log of size 0x%x"...
0x18004064d  lea     r8, aPpftxfbintrans; "PpfTxfBinTransformPpfEventLog"
0x180040654  mov     edx, 0E9h; unsigned int
0x180040659  lea     rdi, aOnecoreBaseNgs; "onecore\\base\\ngscb\\pcrpf\\txfbin\\pp"...
0x180040660  mov     rcx, rdi; char *
0x180040663  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180040668  xor     esi, esi
0x18004066a  test    bl, bl
0x18004066c  jz      loc_180041303
0x180040672  mov     [rbp+0D0h+var_150], esi
0x180040675  mov     [rsp+1D0h+var_154], esi
0x180040679  mov     [rbp+0D0h+var_110], rsi
0x18004067d  mov     [rsp+1D0h+var_158], esi
0x180040681  mov     [rbp+0D0h+var_140], rsi
0x180040685  lea     rax, [rbp+0D0h+var_140]
0x180040689  mov     [rsp+1D0h+var_1A8], rax
0x18004068e  lea     rax, [rsp+1D0h+var_158]
0x180040693  mov     [rsp+1D0h+var_1B0], rax; int
0x180040698  lea     r9, [rbp+0D0h+var_110]
0x18004069c  lea     r8, [rsp+1D0h+var_154]
0x1800406a1  lea     rdx, [rbp+0D0h+var_150]
0x1800406a5  lea     rcx, [rbp+0D0h+var_108]
0x1800406a9  call    PpfEvtLogIteratorGetCurrent
0x1800406ae  test    eax, eax
0x1800406b0  js      loc_18004124A
0x1800406b6  mov     [rsp+1D0h+var_180], sil
0x1800406bb  mov     [rbp+0D0h+var_B0], rsi
0x1800406bf  mov     [rbp+0D0h+Buf1], rsi
0x1800406c3  mov     dword ptr [rbp+0D0h+Size], esi
0x1800406c6  mov     [rsp+1D0h+var_188], rsi; unsigned int *
0x1800406cb  mov     [rsp+1D0h+var_190], rsi; unsigned __int8 **
0x1800406d0  lea     rax, [rbp+0D0h+Size]
0x1800406d4  mov     [rsp+1D0h+var_198], rax; unsigned int *
0x1800406d9  lea     rax, [rbp+0D0h+Buf1]
0x1800406dd  mov     [rsp+1D0h+var_1A0], rax; unsigned __int8 **
0x1800406e2  lea     rax, [rbp+0D0h+var_B0]
0x1800406e6  mov     [rsp+1D0h+var_1A8], rax; struct TREE_VARIABLE_DATA **
0x1800406eb  lea     rax, [rsp+1D0h+var_180]
0x1800406f0  mov     [rsp+1D0h+var_1B0], rax; int
0x1800406f5  mov     r9d, [rsp+1D0h+var_158]; unsigned int
0x1800406fa  mov     r8, [rbp+0D0h+var_140]; unsigned __int8 *
0x1800406fe  mov     edx, [rsp+1D0h+var_154]; unsigned int
0x180040702  mov     ecx, [rbp+0D0h+var_150]; unsigned int
0x180040705  call    ?PpfhCheckForAndValidateSBVarEvent@@YAJIIPEAEIPEA_NPEAPEAUTREE_VARIABLE_DATA@@PEAPEAEPEAI34@Z; PpfhCheckForAndValidateSBVarEvent(uint,uint,uchar *,uint,bool *,TREE_VARIABLE_DATA * *,uchar * *,uint *,uchar * *,uint *)
0x18004070a  mov     rcx, [rbp+0D8h]; this
0x180040711  test    eax, eax
0x180040713  jns     short loc_180040725
0x180040715  mov     r9d, eax; char *
0x180040718  mov     r8, rdi; unsigned int
0x18004071b  mov     edx, 0FEh; void *
0x180040720  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180040725  mov     al, [rsp+1D0h+var_180]
0x180040729  test    al, al
0x18004072b  jz      loc_180040A6A
0x180040731  test    [rbp+0D0h+arg_20], 1
0x180040738  jnz     short loc_180040760
0x18004073a  mov     [rsp+1D0h+var_180], sil
0x18004073f  lea     r8, [rsp+1D0h+var_180]; bool *
0x180040744  mov     edx, dword ptr [rbp+0D0h+Size]; unsigned int
0x180040747  mov     rcx, [rbp+0D0h+Buf1]; unsigned __int8 *
0x18004074b  call    ?PpfhIsSBVarSupported@@YAJPEAEIPEA_N@Z; PpfhIsSBVarSupported(uchar *,uint,bool *)
0x180040750  mov     esi, eax
0x180040752  test    eax, eax
0x180040754  js      loc_180040AB8
0x18004075a  mov     al, [rsp+1D0h+var_180]
0x18004075e  xor     esi, esi
0x180040760  test    al, al
0x180040762  jz      loc_180040A6A
0x180040768  xorps   xmm0, xmm0
0x18004076b  xor     eax, eax
0x18004076d  movups  [rbp+0D0h+var_E0], xmm0
0x180040771  movups  [rbp+0D0h+var_D0], xmm0
0x180040775  mov     [rbp+0D0h+var_C0], rax
0x180040779  mov     [rsp+1D0h+var_180], sil
0x18004077e  lea     r9, [rsp+1D0h+var_180]
0x180040783  lea     r8, [rbp+0D0h+var_E0]
0x180040787  mov     edx, [rbp+0D0h+var_128]
0x18004078a  mov     rcx, [rbp+0D0h+var_78]
0x18004078e  call    PpfEvtLogIteratorInitialize
0x180040793  test    eax, eax
0x180040795  js      loc_1800410D7
0x18004079b  mov     eax, dword ptr [rbp+0D0h+var_C0+4]
0x18004079e  mov     [rbp+0D0h+var_14C], eax
0x1800407a1  cmp     word ptr [rbp+0D0h+var_C0], r14w
0x1800407a6  jz      short loc_1800407F3
0x1800407a8  movzx   edx, r14w
0x1800407ac  lea     rcx, [rbp+0D0h+var_E0]
0x1800407b0  call    PpfEvtLogIteratorSetPreferredHashAlgID
0x1800407b5  cmp     eax, 0C00000BBh
0x1800407ba  jz      loc_180040C32
0x1800407c0  test    eax, eax
0x1800407c2  js      loc_180040B79
0x1800407c8  movzx   eax, word ptr [rbp+0D0h+var_C0+2]
0x1800407cc  movzx   ecx, word ptr [rbp+0D0h+var_C0]
0x1800407d0  mov     dword ptr [rsp+1D0h+var_1A8], eax
0x1800407d4  mov     dword ptr [rsp+1D0h+var_1B0], ecx
0x1800407d8  lea     r9, aTransformPpfEv; "Transform PPF event log configured to u"...
0x1800407df  lea     r8, aPpftxfbintrans; "PpfTxfBinTransformPpfEventLog"
0x1800407e6  mov     edx, 11Ch; unsigned int
0x1800407eb  mov     rcx, rdi; char *
0x1800407ee  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x1800407f3  mov     bl, sil
0x1800407f6  jmp     loc_1800409D8
0x1800407fb  mov     [rsp+1D0h+var_158], esi
0x1800407ff  mov     [rsp+1D0h+var_154], esi
0x180040803  mov     [rbp+0D0h+var_A0], rsi
0x180040807  mov     [rbp+0D0h+var_150], esi
0x18004080a  mov     [rbp+0D0h+var_70], rsi
0x18004080e  lea     rax, [rbp+0D0h+var_70]
0x180040812  mov     [rsp+1D0h+var_1A8], rax
0x180040817  lea     rax, [rbp+0D0h+var_150]
0x18004081b  mov     [rsp+1D0h+var_1B0], rax; int
0x180040820  lea     r9, [rbp+0D0h+var_A0]
0x180040824  lea     r8, [rsp+1D0h+var_154]
0x180040829  lea     rdx, [rsp+1D0h+var_158]
0x18004082e  lea     rcx, [rbp+0D0h+var_E0]
0x180040832  call    PpfEvtLogIteratorGetCurrent
0x180040837  test    eax, eax
0x180040839  js      loc_18004101E
  ... truncated ...
```
