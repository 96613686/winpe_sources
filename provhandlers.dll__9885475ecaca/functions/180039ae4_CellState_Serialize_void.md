# CellState::Serialize(void)

- ea: `0x180039ae4`
- end: `0x18003aab1`
- name: `?Serialize@CellState@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_MVCellularStateHdr@@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ`
- size: `4045`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180011890`

## callees

- `0x18000df98`
- `0x18000e308`
- `0x180012d80`
- `0x180012da0`
- `0x18001493c`
- `0x180024e34`
- `0x18003831c`
- `0x180038678`
- `0x1800388e4`
- `0x180039ae4`
- `0x18003b952`
- `0x18003b9a0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180039d4a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039eb4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a59a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039d4a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039eb4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a59a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18003a0bf`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18003a0bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180039ff6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180039ff6`

## string_xrefs

- `0x18003a937`: `onecoreuap\admin\prov\multivariant\common\inc\MvTypes.h`
- `0x18003a949`: `onecoreuap\admin\prov\multivariant\common\inc\MvTypes.h`
- `0x18003a95b`: `onecoreuap\admin\prov\multivariant\common\inc\MvTypes.h`
- `0x18003a823`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x18003a835`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x18003a847`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x18003a859`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x18003a86e`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x18003a880`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x18003a895`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x18003a8aa`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x18003a8bf`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x18003a8d4`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x18003a8e9`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x18003a8fb`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x18003a910`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x18003a925`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x18003a96d`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x18003a97f`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x18003a99d`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x18003a9b5`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x18003a9c7`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x18003a9dc`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x18003a9f4`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x18003aa06`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x18003aa1b`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x18003aa2d`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x18003aa3f`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x18003aa51`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x18003aa63`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x18003aa78`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x18003aa8a`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`
- `0x18003aa9f`: `onecoreuap\admin\prov\multivariant\handlers\common\cellstate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall CellState::Serialize(__int64 a1, _QWORD *a2)
{
  __int64 v2; // rax
  __int64 v3; // r9
  unsigned __int64 v4; // rax
  unsigned __int64 v5; // r13
  __int64 *v6; // r12
  __int64 *v7; // rbx
  unsigned __int64 v8; // rdi
  __int64 v9; // r15
  __int64 *v10; // rsi
  __int64 *v11; // r15
  unsigned __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // r9
  unsigned __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // r14
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rdi
  __int64 v22; // r14
  __int64 v23; // rax
  __int64 v24; // r9
  unsigned __int64 v25; // rdx
  unsigned __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rdx
  unsigned __int64 v29; // rdx
  _QWORD *v30; // rax
  _QWORD *v31; // rax
  unsigned __int64 v32; // rcx
  unsigned int v33; // eax
  unsigned __int8 v34; // cl
  __int64 v35; // r11
  unsigned __int8 v36; // cl
  char v37; // al
  _QWORD *v38; // rdx
  unsigned __int8 v39; // r9
  unsigned __int64 v40; // rcx
  unsigned __int64 v41; // rax
  unsigned int v42; // r8d
  unsigned __int64 v43; // rdx
  unsigned __int64 v44; // rcx
  __int64 v45; // rax
  __int64 *i; // rax
  __int64 *v47; // rcx
  SIZE_T v48; // rax
  __int64 v49; // r9
  _DWORD *v50; // rax
  _DWORD *v51; // r8
  const char *v52; // r9
  _DWORD *v53; // rdx
  unsigned __int64 v54; // rax
  int v55; // ecx
  char *v56; // r9
  __int64 v57; // r15
  __int64 *v58; // r13
  __int64 *v59; // rdi
  _DWORD *v60; // rbx
  const OLECHAR *v61; // rcx
  HRESULT v62; // eax
  _QWORD *v63; // rax
  __int64 v64; // rcx
  __int64 v65; // rdx
  __int16 v66; // r9
  _WORD *v67; // rcx
  unsigned __int64 v68; // rcx
  int v69; // eax
  int v70; // r11d
  __int64 v71; // r12
  _QWORD *v72; // r14
  _QWORD *v73; // r12
  __int64 v74; // rax
  const char *v75; // rcx
  char *j; // rax
  unsigned __int64 v77; // rax
  int v78; // ecx
  unsigned int v79; // esi
  _QWORD *v80; // rax
  __int64 v81; // rcx
  __int64 v82; // rdx
  _WORD *v83; // r9
  __int16 v84; // r10
  _WORD *v85; // rcx
  unsigned __int64 v86; // rcx
  __int64 v87; // rdx
  unsigned int v88; // r10d
  unsigned __int8 *v89; // rax
  unsigned __int8 *v90; // r11
  unsigned __int8 *v91; // rbx
  int v92; // edx
  unsigned __int8 *v93; // rcx
  int v94; // r9d
  unsigned __int8 *v95; // rcx
  unsigned int v96; // edx
  __int64 v97; // rcx
  unsigned __int64 v98; // rax
  int v99; // ecx
  _QWORD *v100; // rbx
  _QWORD *v101; // rsi
  __int64 v102; // r10
  _QWORD *v103; // rax
  __int64 v104; // rcx
  __int64 v105; // rdx
  _WORD *v106; // r9
  __int16 v107; // r10
  _WORD *v108; // rcx
  unsigned __int64 v109; // rax
  int v110; // ecx
  void **v111; // rax
  __int64 v112; // rcx
  __int64 v113; // rdx
  __int64 v114; // r11
  _WORD *v115; // r10
  __int16 v116; // r9
  _WORD *v117; // rcx
  char *v118; // r10
  unsigned __int64 v119; // rax
  unsigned int v120; // edx
  unsigned __int64 v121; // rax
  unsigned int v122; // edx
  unsigned int v123; // ecx
  int v124; // eax
  unsigned int v125; // edx
  unsigned int v126; // ecx
  int v127; // r10d
  int v128; // ecx
  __int64 *k; // rax
  __int64 *v130; // rcx
  _QWORD *v131; // rbx
  int v133; // [rsp+20h] [rbp-A9h]
  unsigned int v134; // [rsp+24h] [rbp-A5h]
  int v135; // [rsp+24h] [rbp-A5h]
  int v136; // [rsp+24h] [rbp-A5h]
  const char *v137; // [rsp+28h] [rbp-A1h]
  __int64 v138; // [rsp+28h] [rbp-A1h]
  unsigned __int64 v139; // [rsp+30h] [rbp-99h]
  _DWORD *v140; // [rsp+30h] [rbp-99h]
  _QWORD *v141; // [rsp+38h] [rbp-91h]
  __int64 v142; // [rsp+38h] [rbp-91h]
  _DWORD *v143; // [rsp+40h] [rbp-89h]
  __int64 v144; // [rsp+50h] [rbp-79h]
  unsigned int v146; // [rsp+58h] [rbp-71h]
  __int128 v147; // [rsp+60h] [rbp-69h] BYREF
  __int64 v148; // [rsp+70h] [rbp-59h]
  __int64 v149; // [rsp+78h] [rbp-51h]
  _DWORD *v150; // [rsp+80h] [rbp-49h]
  _QWORD *v151; // [rsp+88h] [rbp-41h]
  __int128 v152; // [rsp+90h] [rbp-39h] BYREF
  __int64 v153; // [rsp+A0h] [rbp-29h]
  void *v154; // [rsp+A8h] [rbp-21h] BYREF
  void *v155[3]; // [rsp+C0h] [rbp-9h] BYREF
  unsigned __int64 v156; // [rsp+D8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v151 = a2;
  v149 = 0;
  v134 = 0;
  v2 = 18 * ((__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 5);
  if ( is_mul_ok((__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 5, 0x12u) )
  {
    v3 = 0;
  }
  else
  {
    v2 = -1;
    v3 = 2147942934LL;
  }
  if ( (int)v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
      (const char *)v3,
      v133);
  v4 = v2 + 4;
  if ( v4 < 4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
      v4 < 4 ? (const char *)0x80070216LL : 0,
      v133);
  v5 = v4;
  v147 = 0;
  v148 = 0;
  v6 = *(__int64 **)(a1 + 24);
  v7 = (__int64 *)*v6;
  v144 = 0;
  while ( 1 )
  {
    v8 = v5;
    if ( v7 == v6 )
      break;
    v9 = v7[8];
    v10 = *(__int64 **)(v9 + 64);
    v11 = *(__int64 **)(v9 + 72);
    v12 = v11 - v10;
    v13 = 19 * v12;
    if ( is_mul_ok(v12, 0x13u) )
    {
      v14 = 0;
    }
    else
    {
      v13 = -1;
      v14 = 2147942934LL;
    }
    if ( (int)v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x46,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
        (const char *)v14,
        v133);
    v15 = v13 + v5;
    v16 = -1;
    if ( v15 >= v5 )
      v16 = v15;
    v5 = v16;
    if ( v15 < v8 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x47,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
        v15 < v8 ? (const char *)0x80070216LL : 0,
        v133);
    while ( v10 != v11 )
    {
      v17 = *v10;
      if ( *v10 )
      {
        v18 = v5;
        v19 = v5 + ((unsigned __int64)(((__int64)(*(_QWORD *)(v17 + 40) - *(_QWORD *)(v17 + 32)) >> 5) + 1) >> 1);
        v20 = -1;
        if ( v19 >= v5 )
          v20 = v5 + ((unsigned __int64)(((__int64)(*(_QWORD *)(v17 + 40) - *(_QWORD *)(v17 + 32)) >> 5) + 1) >> 1);
        v5 = v20;
        if ( v19 < v18 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x4C,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
            v19 < v18 ? (const char *)0x80070216LL : 0,
            v133);
        if ( *(_DWORD *)(v17 + 100) == 1 )
        {
          v21 = *(_QWORD *)(v17 + 56);
          v22 = *(_QWORD *)(v17 + 64);
          v23 = 8 * ((v22 - v21) >> 5);
          if ( is_mul_ok(0xAAAAAAAAAAAAAAABuLL * ((v22 - v21) >> 5), 0x18u) )
          {
            v24 = 0;
          }
          else
          {
            v23 = -1;
            v24 = 2147942934LL;
          }
          if ( (int)v24 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x4F,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
              (const char *)v24,
              v133);
          v25 = v5;
          v26 = v23 + v5;
          v27 = -1;
          if ( v26 >= v5 )
            v27 = v26;
          v5 = v27;
          if ( v26 < v25 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x50,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
              v26 < v25 ? (const char *)0x80070216LL : 0,
              v133);
          while ( v21 != v22 )
          {
            v28 = *(_QWORD *)(v21 + 80);
            if ( v28 )
            {
              v30 = CellState::BytesFromGid1(&v154, v28);
              std::vector<std::vector<unsigned char>>::emplace_back<std::vector<unsigned char>>(&v147, v30);
              if ( v154 )
                operator delete(v154);
              v144 = *((_QWORD *)&v147 + 1);
              v29 = *(_QWORD *)(*((_QWORD *)&v147 + 1) - 16LL) - *(_QWORD *)(*((_QWORD *)&v147 + 1) - 24LL);
            }
            else
            {
              v29 = 0;
            }
            v139 = v29;
            v31 = *(_QWORD **)(v21 + 72);
            v141 = v31;
            if ( v31 )
            {
              v32 = v31[2];
              if ( v32 > 0xFF )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x1CF,
                  (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
                  v32 > 0xFF ? (const char *)0x80070216LL : 0,
                  v133);
              v33 = 2 * (unsigned __int8)v32;
              v34 = 2 * v32;
              if ( v33 > 0xFF )
                v34 = -1;
              LOBYTE(v133) = v34;
              if ( v33 > 0xFF )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x1D0,
                  (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
                  v33 > 0xFF ? (const char *)0x80070216LL : 0,
                  v133);
              v152 = 0;
              v153 = 0;
              std::vector<unsigned char>::resize(&v152, v34 + 3LL);
              v135 = v134 | 2;
              v35 = v152;
              *(_BYTE *)v152 = 67;
              *(_BYTE *)(v35 + 2) = 16;
              v36 = v133 + 1;
              v37 = -1;
              if ( (unsigned __int8)(v133 + 1) >= (unsigned __int8)v133 )
                v37 = v133 + 1;
              *(_BYTE *)(v35 + 1) = v37;
              if ( v36 < (unsigned __int8)v133 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x1DA,
                  (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
                  v36 < (unsigned __int8)v133 ? (const char *)0x80070216LL : 0,
                  v133);
              v38 = v141;
              if ( v141[3] >= 8u )
                v38 = (_QWORD *)*v141;
              v39 = 0;
              if ( (unsigned __int8)v133 > 1u )
              {
                do
                {
                  *(_BYTE *)(v35 + v39 + 3) = *((_BYTE *)v38 + v39 + 1);
                  *(_BYTE *)(v35 + v39 + 4) = *((_BYTE *)v38 + v39);
                  v39 += 2;
                }
                while ( (unsigned int)v39 + 1 < (unsigned __int8)v133 );
              }
              std::vector<std::vector<unsigned char>>::emplace_back<std::vector<unsigned char>>(&v147, &v152);
              v134 = v135 & 0xFFFFFFFD;
              if ( (_QWORD)v152 )
                operator delete((void *)v152);
              v144 = *((_QWORD *)&v147 + 1);
              v40 = v139 + *(_QWORD *)(*((_QWORD *)&v147 + 1) - 16LL) - *(_QWORD *)(*((_QWORD *)&v147 + 1) - 24LL);
              if ( v40 < v139 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x5C,
                  (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
                  v40 < v139 ? (const char *)0x80070216LL : 0,
                  v133);
              v29 = v139 + *(_QWORD *)(*((_QWORD *)&v147 + 1) - 16LL) - *(_QWORD *)(*((_QWORD *)&v147 + 1) - 24LL);
            }
            v41 = (v29 + 3) >> 2;
            v42 = v41;
            if ( v41 > 0xFFFFFFFF )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x31,
                (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
                v41 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
                v133);
            v43 = v5;
            v44 = v5 + (unsigned int)v41;
            v45 = -1;
            if ( v44 >= v5 )
              v45 = v5 + v42;
            v5 = v45;
            if ( v44 < v43 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x5E,
                (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
                v44 < v43 ? (const char *)0x80070216LL : 0,
                v133);
            v21 += 96;
          }
        }
      }
      ++v10;
    }
    if ( !*((_BYTE *)v7 + 25) )
    {
      i = (__int64 *)v7[2];
      if ( *((_BYTE *)i + 25) )
      {
        for ( i = (__int64 *)v7[1]; !*((_BYTE *)i + 25) && v7 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v7 = i;
LABEL_67:
        v7 = i;
      }
      else
      {
        v47 = (__int64 *)*i;
        if ( *(_BYTE *)(*i + 25) )
          goto LABEL_67;
        do
        {
          v7 = v47;
          v47 = (__int64 *)*v47;
        }
        while ( !*((_BYTE *)v47 + 25) );
      }
    }
  }
  v48 = 4 * v5;
  if ( is_mul_ok(v5, 4u) )
  {
    v49 = 0;
  }
  else
  {
    v48 = -1;
    v49 = 2147942934LL;
  }
  if ( (int)v49 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\MvTypes.h",
      (const char *)v49,
      v133);
  v50 = CoTaskMemRealloc(0, v48);
  v53 = v50;
  v143 = v50;
  if ( v5 && !v50 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x3F,
      (int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\MvTypes.h",
      v52);
  if ( v5 > 0xFFFFFFFF )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\MvTypes.h",
      v5 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
      v133);
  *v50 = 2;
  v50[1] = 4;
  v50[2] = *(_DWORD *)(a1 + 40);
  v54 = (__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 5;
  v55 = v54;
  if ( v54 > 0xFFFFFFFF )
    v55 = -1;
  v56 = v54 > 0xFFFFFFFF ? (char *)0x80070216LL : 0LL;
  v53[3] = v55;
  if ( v54 > 0xFFFFFFFF )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6B,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
      v56,
      v133);
  v57 = v147;
  v58 = *(__int64 **)(a1 + 24);
  v59 = (__int64 *)*v58;
  while ( v59 != v58 )
  {
    v60 = &v53[v53[1]];
    v150 = v60;
    *v60 = 3;
    v60[1] = 18;
    v61 = (const OLECHAR *)v59[8];
    if ( *((_QWORD *)v61 + 3) >= 8u )
      v61 = *(const OLECHAR **)v61;
    v62 = CLSIDFromString(v61, (LPCLSID)(v60 + 2));
    if ( v62 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x75,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
        (const char *)(unsigned int)v62,
        v133);
    v63 = (_QWORD *)(v59[8] + 32);
    if ( *(_QWORD *)(v59[8] + 56) >= 8u )
      v63 = (_QWORD *)*v63;
    v64 = 2147483646;
    v65 = 18;
    v51 = v60 + 6;
    do
    {
      if ( !v64 )
        break;
      v66 = *(_WORD *)v63;
      if ( !*(_WORD *)v63 )
        break;
      v63 = (_QWORD *)((char *)v63 + 2);
      *(_WORD *)v51 = v66;
      v51 = (_DWORD *)((char *)v51 + 2);
      --v64;
      --v65;
    }
    while ( v65 );
    v67 = (_WORD *)v51 - 1;
    if ( v65 )
      v67 = v51;
    *v67 = 0;
    if ( !v65 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x76,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
        (const char *)0x8007007ALL,
        v133);
    v60[15] = *(_BYTE *)(v59[8] + 113) != 0;
    v68 = (__int64)(*(_QWORD *)(v59[8] + 72) - *(_QWORD *)(v59[8] + 64)) >> 3;
    v69 = v68;
    if ( v68 > 0xFFFFFFFF )
      v69 = -1;
    v56 = v68 > 0xFFFFFFFF ? (char *)0x80070216LL : 0LL;
    v60[17] = v69;
    if ( v68 > 0xFFFFFFFF )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x78,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
        v56,
        v133);
    v70 = 0;
    v136 = 0;
    v71 = v59[8];
    v72 = *(_QWORD **)(v71 + 64);
    v73 = *(_QWORD **)(v71 + 72);
    while ( v72 != v73 )
    {
      v51 = &v60[v60[1]];
      v140 = v51;
      *v51 = 2;
      v51[1] = 19;
      v74 = v59[8];
      v75 = *(const char **)(v74 + 96);
      v56 = *(char **)(v74 + 88);
      for ( j = v56; j != v75; j += 8 )
      {
        if ( *(_QWORD *)j == v70 )
          break;
      }
      if ( v75 != j )
      {
        v77 = (j - v56) >> 3;
        v78 = v77;
        if ( v77 > 0xFFFFFFFF )
          v78 = -1;
        v56 = v77 > 0xFFFFFFFF ? (char *)0x80070216LL : 0LL;
        v51[3] = v78;
        if ( v77 > 0xFFFFFFFF )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x85,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
            v56,
            v133);
      }
      v51[2] = v70;
      v79 = 0;
      v51[16] = 0;
      v80 = (_QWORD *)*v72;
      if ( *v72 )
      {
        if ( v80[3] >= 8u )
          v80 = (_QWORD *)*v80;
        v81 = 2147483646;
        v82 = 21;
        v83 = v51 + 5;
        do
        {
          if ( !v81 )
            break;
          v84 = *(_WORD *)v80;
          if ( !*(_WORD *)v80 )
            break;
          v80 = (_QWORD *)((char *)v80 + 2);
          *v83++ = v84;
          --v81;
          --v82;
        }
        while ( v82 );
        v85 = v83 - 1;
        if ( v82 )
          v85 = v83;
        *v85 = 0;
        if ( !v82 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x8C,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
            (const char *)0x8007007ALL,
            v133);
        v86 = (__int64)(*(_QWORD *)(*v72 + 40LL) - *(_QWORD *)(*v72 + 32LL)) >> 5;
        v87 = (unsigned int)v86;
        if ( v86 > 0xFFFFFFFF )
          v87 = 0xFFFFFFFFLL;
        v56 = v86 > 0xFFFFFFFF ? (char *)0x80070216LL : 0LL;
        v51[17] = v87;
        if ( v86 > 0xFFFFFFFF )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x8D,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
            v56,
            v133);
        if ( *(_BYTE *)(*v72 + 105LL) )
          v51[16] = 1;
        v88 = (unsigned int)(v87 + 1) >> 1;
        v137 = (const char *)&v51[v51[1]];
        v89 = *(unsigned __int8 **)(*v72 + 32LL);
        if ( v88 )
        {
          v56 = (char *)&v51[v51[1]];
          do
          {
            if ( *((_QWORD *)v89 + 2) <= 1u )
              std::wstring::_Xran(v86, v87, v51, v56);
            if ( *((_QWORD *)v89 + 3) < 8u )
            {
              v90 = v89;
              v91 = v89;
            }
            else
            {
              v90 = *(unsigned __int8 **)v89;
              v91 = *(unsigned __int8 **)v89;
            }
            v89 += 32;
            if ( *(unsigned __int8 **)(*v72 + 40LL) == v89 )
            {
              v92 = 0xFFFF;
            }
            else
            {
              if ( *((_QWORD *)v89 + 2) <= 1u )
                std::wstring::_Xran(*v72, v87, v51, v56);
              if ( *((_QWORD *)v89 + 3) < 8u )
                v93 = v89;
              else
                v93 = *(unsigned __int8 **)v89;
              v94 = v93[2];
              if ( *((_QWORD *)v89 + 3) < 8u )
                v95 = v89;
              else
                v95 = *(unsigned __int8 **)v89;
              v92 = v94 | (*v95 << 8);
              v56 = (char *)v137;
            }
            v87 = v91[2] | ((*v90 | (unsigned int)(v92 << 8)) << 8);
            v86 = v79;
            *(_DWORD *)&v56[4 * v79++] = v87;
          }
          while ( v79 < v88 );
          v70 = v136;
        }
        v51[1] += v88;
        v96 = v51[1];
        v97 = *v72;
        if ( *(_DWORD *)(*v72 + 100LL) == 1 )
        {
          v98 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)(v97 + 64) - *(_QWORD *)(v97 + 56)) >> 5);
          v99 = -1431655765 * ((__int64)(*(_QWORD *)(v97 + 64) - *(_QWORD *)(v97 + 56)) >> 5);
          if ( v98 > 0xFFFFFFFF )
            v99 = -1;
          v56 = v98 > 0xFFFFFFFF ? (char *)0x80070216LL : 0LL;
          v51[18] = v99;
          if ( v98 > 0xFFFFFFFF )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xAA,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
              v56,
              v133);
          v100 = *(_QWORD **)(*v72 + 56LL);
          v101 = *(_QWORD **)(*v72 + 64LL);
          while ( v100 != v101 )
          {
            v102 = v96;
            v138 = v96;
            v51[v96] = 1;
            v51[v96 + 1] = 24;
            v103 = v100 + 4;
            if ( v100[7] >= 8u )
              v103 = (_QWORD *)*v103;
            v104 = 2147483646;
            v105 = 16;
            v106 = &v51[v102 + 2];
            do
            {
              if ( !v104 )
                break;
              v107 = *(_WORD *)v103;
              if ( !*(_WORD *)v103 )
                break;
              v103 = (_QWORD *)((char *)v103 + 2);
              *v106++ = v107;
              --v104;
              --v105;
            }
            while ( v105 );
            v108 = v106 - 1;
            if ( v105 )
              v108 = v106;
            *v108 = 0;
            if ( !v105 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xB3,
                (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
                (const char *)0x8007007ALL,
                v133);
            v109 = v100[11];
            v110 = v109;
            if ( v109 > 0xFFFFFFFF )
              v110 = -1;
            v51[v138 + 10] = v110;
            if ( v109 > 0xFFFFFFFF )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xB4,
                (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
                v109 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
                v133);
            v156 = 7;
            v155[2] = 0;
            LOWORD(v155[0]) = 0;
            std::wstring::assign(v155, (char *)&Src, 0);
            v111 = v155;
            if ( v100[8] )
              v111 = (void **)v100[8];
            if ( (unsigned __int64)v111[3] >= 8 )
              v111 = (void **)*v111;
            v112 = 2147483646;
            v113 = 21;
            v51 = v140;
            v114 = v138;
            v115 = &v140[v138 + 11];
            do
            {
              if ( !v112 )
                break;
              v116 = *(_WORD *)v111;
              if ( *(_WORD *)v111 == (_WORD)v149 )
                break;
              v111 = (void **)((char *)v111 + 2);
              *v115++ = v116;
              --v112;
              --v113;
            }
            while ( v113 );
            v117 = v115 - 1;
            if ( v113 )
              v117 = v115;
            *v117 = 0;
            if ( !v113 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xB5,
                (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
                (const char *)0x8007007ALL,
                v133);
            if ( v156 >= 8 )
            {
              operator delete(v155[0]);
              v51 = v140;
              v114 = v138;
            }
            v118 = (char *)&v51[v114 + 24];
            if ( v100[10] )
            {
              if ( v57 == v144 )
                wil::details::in1diag3::_FailFast_Hr(
                  retaddr,
                  (void *)0xBB,
                  (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
                  (const char *)0x8000FFFFLL,
                  v133);
              v119 = *(_QWORD *)(v57 + 8) - *(_QWORD *)v57;
              v120 = *(_DWORD *)(v57 + 8) - *(_DWORD *)v57;
              if ( v119 > 0xFFFFFFFF )
                v120 = -1;
              v51[v114 + 22] = v120;
              if ( v119 > 0xFFFFFFFF )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xBC,
                  (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
                  v119 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
                  v133);
              memcpy_0(v118, *(const void **)v57, v120);
              v51 = v140;
              v114 = v138;
              v142 = (unsigned int)v140[v138 + 22];
              v118 = (char *)&v140[v138 + 24] + v142;
              v57 += 24;
            }
            else
            {
              LODWORD(v142) = 0;
              v51[v114 + 22] = 0;
            }
            if ( v100[9] )
            {
              if ( v57 == v144 )
                wil::details::in1diag3::_FailFast_Hr(
                  retaddr,
                  (void *)0xC9,
                  (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
                  (const char *)0x8000FFFFLL,
                  v133);
              v121 = *(_QWORD *)(v57 + 8) - *(_QWORD *)v57;
              v122 = *(_DWORD *)(v57 + 8) - *(_DWORD *)v57;
              if ( v121 > 0xFFFFFFFF )
                v122 = -1;
              v51[v114 + 23] = v122;
              if ( v121 > 0xFFFFFFFF )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xCA,
                  (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
                  v121 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
                  v133);
              v146 = v142;
              memcpy_0(v118, *(const void **)v57, v122);
              v51 = v140;
              v114 = v138;
              v123 = v142 + v140[v138 + 23];
              v124 = -1;
              if ( v123 >= (unsigned int)v142 )
                v124 = v142 + v140[v138 + 23];
              LODWORD(v142) = v124;
              if ( v123 < v146 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xCC,
                  (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
                  v123 < v146 ? (const char *)0x80070216LL : 0,
                  v133);
              v57 += 24;
            }
            else
            {
              v51[v114 + 23] = 0;
            }
            v125 = v51[v114 + 1];
            v126 = v125 + (((unsigned __int64)(unsigned int)v142 + 3) >> 2);
            v127 = -1;
            if ( v126 >= v125 )
              v127 = v125 + (((unsigned __int64)(unsigned int)v142 + 3) >> 2);
            v56 = v126 < v125 ? (char *)0x80070216LL : 0LL;
            v51[v114 + 1] = v127;
            if ( v126 < v125 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xD4,
                (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\cellstate.cpp",
                v56,
                v133);
            v51[1] += v127;
            v96 = v51[1];
            v100 += 12;
          }
          v70 = v136;
        }
        v128 = *(_DWORD *)(*v72 + 100LL);
        v60 = v150;
      }
      else
      {
        v51[18] = 0;
        v128 = 0;
      }
      v136 = ++v70;
      v51[4] = v128;
      v60[1] += v51[1];
      ++v72;
    }
    v53 = v143;
    v143[1] += v60[1];
    if ( !*((_BYTE *)v59 + 25) )
    {
      k = (__int64 *)v59[2];
      if ( *((_BYTE *)k + 25) )
      {
        for ( k = (__int64 *)v59[1]; !*((_BYTE *)k + 25) && v59 == (__int64 *)k[2]; k = (__int64 *)k[1] )
          v59 = k;
LABEL_202:
        v59 = k;
        continue;
      }
      v130 = (__int64 *)*k;
      if ( *(_BYTE *)(*k + 25) )
        goto LABEL_202;
      do
      {
        v59 = v130;
        v130 = (__int64 *)*v130;
      }
      while ( !*((_BYTE *)v130 + 25) );
    }
  }
  v131 = v151;
  *v151 = v53;
  std::vector<std::vector<unsigned char>>::~vector<std::vector<unsigned char>>(&v147, v53, v51, v56);
  return v131;
}

```

## disassembly

```asm
0x180039ae4  mov     [rsp-8+arg_10], rbx
0x180039ae9  mov     [rsp-8+arg_8], rdx
0x180039aee  push    rbp
0x180039aef  push    rsi
0x180039af0  push    rdi
0x180039af1  push    r12
0x180039af3  push    r13
0x180039af5  push    r14
0x180039af7  push    r15
0x180039af9  lea     rbp, [rsp-27h]
0x180039afe  sub     rsp, 0F0h
0x180039b05  mov     rax, cs:__security_cookie
0x180039b0c  xor     rax, rsp
0x180039b0f  mov     [rbp+57h+var_40], rax
0x180039b13  mov     [rbp+57h+var_98], rdx
0x180039b17  mov     rsi, rcx
0x180039b1a  mov     [rbp+57h+var_C8], rcx
0x180039b1e  mov     [rsp+120h+var_E0], rdx
0x180039b23  xor     r14d, r14d
0x180039b26  mov     [rbp+57h+var_A8], r14
0x180039b2a  mov     eax, r14d
0x180039b2d  mov     [rsp+120h+var_FC], eax
0x180039b31  mov     [rsp+120h+var_D8], eax
0x180039b35  mov     [rsp+120h+var_E0], r14
0x180039b3a  mov     rdx, [rcx+8]
0x180039b3e  sub     rdx, [rcx]
0x180039b41  sar     rdx, 5
0x180039b45  lea     eax, [r14+12h]
0x180039b49  mul     rdx
0x180039b4c  or      r10, 0FFFFFFFFFFFFFFFFh
0x180039b50  test    rdx, rdx
0x180039b53  jnz     short loc_180039B5A
0x180039b55  mov     r9d, r14d
0x180039b58  jmp     short loc_180039B63
0x180039b5a  mov     rax, r10
0x180039b5d  mov     r9d, 80070216h; char *
0x180039b63  mov     rcx, [rbp+5Fh]; this
0x180039b67  test    r9d, r9d
0x180039b6a  js      loc_18003A835
0x180039b70  add     rax, 4
0x180039b74  mov     r13, r10
0x180039b77  cmp     rax, 4
0x180039b7b  cmovnb  r13, rax
0x180039b7f  sbb     r9d, r9d
0x180039b82  and     r9d, 80070216h; char *
0x180039b89  mov     rcx, [rbp+5Fh]; this
0x180039b8d  cmp     rax, 4
0x180039b91  jb      loc_18003A847
0x180039b97  xorps   xmm0, xmm0
0x180039b9a  movdqu  [rbp+57h+var_C0], xmm0
0x180039b9f  mov     [rbp+57h+var_B0], r14
0x180039ba3  mov     r12, [rsi+18h]
0x180039ba7  mov     rbx, [r12]
0x180039bab  mov     r11d, 0FFh
0x180039bb1  mov     rax, qword ptr [rbp+57h+var_C0+8]
0x180039bb5  mov     [rbp+57h+var_D0], rax
0x180039bb9  mov     rdi, r13
0x180039bbc  mov     [rsp+120h+var_E0], r14
0x180039bc1  cmp     rbx, r12
0x180039bc4  jz      loc_180039FC9
0x180039bca  mov     r15, [rbx+40h]
0x180039bce  mov     rsi, [r15+40h]
0x180039bd2  mov     r15, [r15+48h]
0x180039bd6  mov     rcx, r15
0x180039bd9  sub     rcx, rsi
0x180039bdc  sar     rcx, 3
0x180039be0  mov     eax, 13h
0x180039be5  mul     rcx
0x180039be8  test    rdx, rdx
0x180039beb  jnz     short loc_180039BF2
0x180039bed  mov     r9d, r14d
0x180039bf0  jmp     short loc_180039BFB
0x180039bf2  mov     rax, r10
0x180039bf5  mov     r9d, 80070216h; char *
0x180039bfb  mov     rcx, [rbp+5Fh]; this
0x180039bff  test    r9d, r9d
0x180039c02  js      loc_18003A925
0x180039c08  lea     rcx, [rax+r13]
0x180039c0c  mov     rax, r10
0x180039c0f  cmp     rcx, r13
0x180039c12  cmovnb  rax, rcx
0x180039c16  mov     r13, rax
0x180039c19  cmp     rcx, rdi
0x180039c1c  sbb     r9d, r9d
0x180039c1f  and     r9d, 80070216h; char *
0x180039c26  mov     rax, [rbp+5Fh]
0x180039c2a  cmp     rcx, rdi
0x180039c2d  jb      loc_18003A910
0x180039c33  xor     r8d, r8d
0x180039c36  cmp     rsi, r15
0x180039c39  jz      loc_180039F74
0x180039c3f  mov     r14, [rsi]
0x180039c42  test    r14, r14
0x180039c45  jz      loc_180039F6B
0x180039c4b  mov     rdx, r13
0x180039c4e  mov     rcx, [r14+28h]
0x180039c52  sub     rcx, [r14+20h]
0x180039c56  sar     rcx, 5
0x180039c5a  inc     rcx
0x180039c5d  shr     rcx, 1
0x180039c60  add     rcx, r13
0x180039c63  mov     rax, r10
0x180039c66  cmp     rcx, r13
0x180039c69  cmovnb  rax, rcx
0x180039c6d  mov     r13, rax
0x180039c70  cmp     rcx, rdx
0x180039c73  sbb     r9d, r9d
0x180039c76  and     r9d, 80070216h; char *
0x180039c7d  mov     rax, [rbp+5Fh]
0x180039c81  cmp     rcx, rdx
0x180039c84  jb      loc_18003A8FB
0x180039c8a  cmp     dword ptr [r14+64h], 1
0x180039c8f  jnz     loc_180039F6B
0x180039c95  mov     rdi, [r14+38h]
0x180039c99  mov     r14, [r14+40h]
0x180039c9d  mov     [rsp+120h+var_E0], r8
0x180039ca2  mov     rcx, r14
0x180039ca5  sub     rcx, rdi
0x180039ca8  sar     rcx, 5
0x180039cac  mov     rax, 0AAAAAAAAAAAAAAABh
0x180039cb6  imul    rcx, rax
0x180039cba  mov     eax, 18h
0x180039cbf  mul     rcx
0x180039cc2  test    rdx, rdx
0x180039cc5  jnz     short loc_180039CCC
0x180039cc7  mov     r9d, r8d
0x180039cca  jmp     short loc_180039CD5
0x180039ccc  mov     rax, r10
0x180039ccf  mov     r9d, 80070216h; char *
0x180039cd5  mov     rcx, [rbp+5Fh]; this
0x180039cd9  test    r9d, r9d
0x180039cdc  js      loc_18003A8E9
0x180039ce2  mov     rdx, r13
0x180039ce5  lea     rcx, [rax+r13]
0x180039ce9  mov     rax, r10
0x180039cec  cmp     rcx, r13
0x180039cef  cmovnb  rax, rcx
0x180039cf3  mov     r13, rax
0x180039cf6  cmp     rcx, rdx
0x180039cf9  sbb     r9d, r9d
0x180039cfc  and     r9d, 80070216h; char *
0x180039d03  mov     rax, [rbp+5Fh]
0x180039d07  cmp     rcx, rdx
0x180039d0a  jb      loc_18003A8D4
0x180039d10  cmp     rdi, r14
0x180039d13  jz      loc_180039F6B
0x180039d19  mov     rdx, [rdi+50h]
0x180039d1d  test    rdx, rdx
0x180039d20  jnz     short loc_180039D27
0x180039d22  mov     rdx, r8
0x180039d25  jmp     short loc_180039D6D
0x180039d27  lea     rcx, [rbp+57h+var_78]
0x180039d2b  call    ?BytesFromGid1@CellState@@SA?AV?$vector@EV?$allocator@E@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; CellState::BytesFromGid1(std::wstring const &)
0x180039d30  nop
0x180039d31  mov     rdx, rax
0x180039d34  lea     rcx, [rbp+57h+var_C0]
0x180039d38  call    ??$emplace_back@V?$vector@EV?$allocator@E@std@@@std@@@?$vector@V?$vector@EV?$allocator@E@std@@@std@@V?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@QEAAX$$QEAV?$vector@EV?$allocator@E@std@@@1@@Z; std::vector<std::vector<uchar>>::emplace_back<std::vector<uchar>>(std::vector<uchar> &&)
0x180039d3d  nop
0x180039d3e  mov     rcx, [rbp+57h+var_78]
0x180039d42  xor     r8d, r8d
0x180039d45  test    rcx, rcx
0x180039d48  jz      short loc_180039D53
0x180039d4a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180039d50  xor     r8d, r8d
0x180039d53  mov     r10, qword ptr [rbp+57h+var_C0+8]
0x180039d57  mov     [rbp+57h+var_D0], r10
0x180039d5b  mov     rdx, [r10-10h]
0x180039d5f  sub     rdx, [r10-18h]
0x180039d63  or      r10, 0FFFFFFFFFFFFFFFFh
0x180039d67  mov     r11d, 0FFh
0x180039d6d  mov     [rsp+120h+var_F0], rdx
0x180039d72  mov     rax, [rdi+48h]
0x180039d76  mov     [rsp+120h+var_E8], rax
0x180039d7b  test    rax, rax
0x180039d7e  jnz     short loc_180039D8B
0x180039d80  mov     r11d, 80070216h
0x180039d86  jmp     loc_180039EFF
0x180039d8b  mov     rcx, [rax+10h]
0x180039d8f  cmp     rcx, r11
0x180039d92  mov     dl, cl
0x180039d94  jbe     short loc_180039D99
0x180039d96  mov     dl, r11b
0x180039d99  cmp     r11, rcx
0x180039d9c  sbb     r9d, r9d
0x180039d9f  mov     r10d, 80070216h
0x180039da5  and     r9d, r10d; char *
0x180039da8  mov     rax, [rbp+5Fh]
0x180039dac  cmp     rcx, r11
0x180039daf  ja      loc_18003A8BF
0x180039db5  movzx   eax, dl
0x180039db8  add     eax, eax
0x180039dba  cmp     eax, r11d
0x180039dbd  mov     cl, al
0x180039dbf  jbe     short loc_180039DC4
0x180039dc1  mov     cl, r11b
0x180039dc4  mov     byte ptr [rsp+120h+var_100], cl; int
0x180039dc8  cmp     r11d, eax
0x180039dcb  sbb     r9d, r9d
0x180039dce  and     r9d, r10d; char *
0x180039dd1  mov     r10, [rbp+5Fh]
0x180039dd5  cmp     eax, r11d
0x180039dd8  ja      loc_18003A8AA
0x180039dde  xorps   xmm0, xmm0
0x180039de1  movdqu  [rbp+57h+var_90], xmm0
0x180039de6  mov     [rbp+57h+var_80], r8
0x180039dea  movzx   edx, cl
0x180039ded  add     rdx, 3
0x180039df1  lea     rcx, [rbp+57h+var_90]
0x180039df5  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x180039dfa  mov     eax, [rsp+120h+var_FC]
0x180039dfe  or      eax, 2
0x180039e01  mov     [rsp+120h+var_FC], eax
0x180039e05  mov     [rsp+120h+var_D8], eax
0x180039e09  mov     r11, qword ptr [rbp+57h+var_90]
0x180039e0d  mov     byte ptr [r11], 43h ; 'C'
0x180039e11  mov     byte ptr [r11+2], 10h
0x180039e16  movzx   r8d, byte ptr [rsp+120h+var_100]
0x180039e1c  lea     eax, [r8+1]
0x180039e20  movzx   ecx, al
0x180039e23  mov     eax, 0FFh
0x180039e28  cmp     cl, r8b
0x180039e2b  cmovnb  eax, ecx
0x180039e2e  sbb     r9d, r9d
0x180039e31  and     r9d, 80070216h; char *
0x180039e38  mov     [r11+1], al
0x180039e3c  mov     rax, [rbp+5Fh]
0x180039e40  cmp     cl, r8b
0x180039e43  jb      loc_18003A895
0x180039e49  mov     rax, [rsp+120h+var_F0]
0x180039e4e  mov     [rsp+120h+var_F8], rax
0x180039e53  mov     rdx, [rsp+120h+var_E8]
0x180039e58  cmp     qword ptr [rdx+18h], 8
0x180039e5d  jb      short loc_180039E62
0x180039e5f  mov     rdx, [rdx]
0x180039e62  xor     r9b, r9b
0x180039e65  cmp     r8d, 1
0x180039e69  jbe     short loc_180039E8F
0x180039e6b  movzx   ecx, r9b
0x180039e6f  mov     al, [rcx+rdx+1]
0x180039e73  mov     [r11+rcx+3], al
0x180039e78  mov     al, [rcx+rdx]
0x180039e7b  mov     [r11+rcx+4], al
0x180039e80  add     r9b, 2
0x180039e84  movzx   eax, r9b
0x180039e88  inc     eax
0x180039e8a  cmp     eax, r8d
0x180039e8d  jb      short loc_180039E6B
0x180039e8f  lea     rdx, [rbp+57h+var_90]
0x180039e93  lea     rcx, [rbp+57h+var_C0]
0x180039e97  call    ??$emplace_back@V?$vector@EV?$allocator@E@std@@@std@@@?$vector@V?$vector@EV?$allocator@E@std@@@std@@V?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@QEAAX$$QEAV?$vector@EV?$allocator@E@std@@@1@@Z; std::vector<std::vector<uchar>>::emplace_back<std::vector<uchar>>(std::vector<uchar> &&)
0x180039e9c  mov     eax, [rsp+120h+var_FC]
0x180039ea0  and     eax, 0FFFFFFFDh
0x180039ea3  mov     [rsp+120h+var_FC], eax
0x180039ea7  mov     [rsp+120h+var_D8], eax
0x180039eab  mov     rcx, qword ptr [rbp+57h+var_90]
0x180039eaf  test    rcx, rcx
0x180039eb2  jz      short loc_180039EBA
0x180039eb4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180039eba  mov     r10, qword ptr [rbp+57h+var_C0+8]
0x180039ebe  mov     [rbp+57h+var_D0], r10
0x180039ec2  mov     rcx, [r10-10h]
0x180039ec6  sub     rcx, [r10-18h]
0x180039eca  add     rcx, [rsp+120h+var_F0]
0x180039ecf  or      r10, 0FFFFFFFFFFFFFFFFh
0x180039ed3  mov     rdx, r10
0x180039ed6  cmp     rcx, [rsp+120h+var_F0]
0x180039edb  cmovnb  rdx, rcx
0x180039edf  cmp     rcx, [rsp+120h+var_F8]
0x180039ee4  sbb     r9d, r9d
0x180039ee7  mov     r11d, 80070216h
0x180039eed  and     r9d, r11d; char *
0x180039ef0  mov     rax, [rbp+5Fh]
0x180039ef4  cmp     rcx, [rsp+120h+var_F8]
0x180039ef9  jb      loc_18003A880
0x180039eff  lea     rax, [rdx+3]
0x180039f03  shr     rax, 2
0x180039f07  mov     edx, 0FFFFFFFFh
0x180039f0c  cmp     rax, rdx
0x180039f0f  mov     r8d, eax
0x180039f12  jbe     short loc_180039F17
0x180039f14  mov     r8d, edx
0x180039f17  cmp     rdx, rax
0x180039f1a  sbb     r9d, r9d
0x180039f1d  and     r9d, r11d; char *
0x180039f20  mov     rcx, [rbp+5Fh]; this
0x180039f24  cmp     rax, rdx
0x180039f27  ja      loc_18003A86E
0x180039f2d  mov     rdx, r13
0x180039f30  mov     ecx, r8d
0x180039f33  add     rcx, r13
0x180039f36  mov     rax, r10
0x180039f39  cmp     rcx, r13
0x180039f3c  cmovnb  rax, rcx
0x180039f40  mov     r13, rax
0x180039f43  cmp     rcx, rdx
0x180039f46  sbb     r9d, r9d
0x180039f49  and     r9d, r11d; char *
0x180039f4c  mov     rax, [rbp+5Fh]
0x180039f50  cmp     rcx, rdx
0x180039f53  jb      loc_18003A859
  ... truncated ...
```
