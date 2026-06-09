# TMetaInferrence::InferRelationMeta(void)

- ea: `0x18001f02c`
- end: `0x18001fa93`
- name: `?InferRelationMeta@TMetaInferrence@@AEAAXXZ`
- size: `2663`
- prototype: `void __fastcall(TMetaInferrence *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001e000`

## callees

- `0x180017ad8`
- `0x18001f02c`
- `0x180030010`

## string_xrefs

- `0x18001f4b1`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001f521`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001f595`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001f609`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001f67d`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001f6f1`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001f765`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001f7d9`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001f850`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001f89f`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001f8ee`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001f924`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001f99b`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001f9ed`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001fa3f`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001fa75`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`

## pseudocode

```c
void __fastcall TMetaInferrence::InferRelationMeta(TMetaInferrence *this)
{
  unsigned int i; // r15d
  unsigned int *v3; // r14
  __int64 v4; // rdx
  unsigned int v5; // eax
  __int64 *v6; // rsi
  unsigned int v7; // edi
  unsigned int v8; // r13d
  __int64 v9; // rbx
  __int64 v10; // rax
  unsigned int v11; // r12d
  __int64 *v12; // rsi
  __int64 v13; // rbx
  int v14; // edi
  _DWORD *v15; // rax
  __int64 *v16; // rcx
  __int64 v17; // r8
  __int64 v18; // rax
  bool v19; // zf
  unsigned int v20; // eax
  __int64 v21; // rdx
  unsigned int v22; // eax
  __int64 v23; // rcx
  unsigned int v24; // r15d
  __int64 *v25; // rdi
  __int64 v26; // rbx
  int v27; // eax
  __int64 *v28; // rsi
  unsigned int v29; // edi
  __int64 v30; // rbx
  __int64 v31; // rax
  int v32; // esi
  __int64 v33; // r12
  int v34; // edi
  int v35; // ebx
  _DWORD *v36; // r15
  _DWORD *v37; // rax
  _DWORD *v38; // r13
  __int64 v39; // rsi
  __int64 (__fastcall *v40)(__int64, _QWORD); // rdi
  __int64 v41; // rbx
  int v42; // eax
  __int64 v43; // rcx
  __int64 v44; // rsi
  __int64 (__fastcall *v45)(__int64, _QWORD); // rdi
  __int64 v46; // rax
  __int64 *v47; // rdi
  __int64 v48; // rbx
  int v49; // eax
  void (***v50)(_QWORD, const wchar_t *, ...); // rsi
  void (*v51)(_QWORD, const wchar_t *, ...); // rdi
  __int64 v52; // rbx
  __int64 v53; // rax
  void (***v54)(_QWORD, const wchar_t *, ...); // rsi
  void (*v55)(_QWORD, const wchar_t *, ...); // rdi
  __int64 v56; // rbx
  __int64 v57; // rax
  void (***v58)(_QWORD, const wchar_t *, ...); // rsi
  void (*v59)(_QWORD, const wchar_t *, ...); // rdi
  __int64 v60; // rbx
  __int64 v61; // rax
  void (***v62)(_QWORD, const wchar_t *, ...); // rsi
  void (*v63)(_QWORD, const wchar_t *, ...); // rdi
  __int64 v64; // rbx
  __int64 v65; // rax
  void (***v66)(_QWORD, const wchar_t *, ...); // rsi
  void (*v67)(_QWORD, const wchar_t *, ...); // rdi
  __int64 v68; // rbx
  __int64 v69; // rax
  void (***v70)(_QWORD, const wchar_t *, ...); // rsi
  void (*v71)(_QWORD, const wchar_t *, ...); // rdi
  __int64 v72; // rbx
  __int64 v73; // rax
  void (***v74)(_QWORD, const wchar_t *, ...); // rsi
  void (*v75)(_QWORD, const wchar_t *, ...); // rdi
  __int64 v76; // rbx
  __int64 v77; // rax
  void (***v78)(_QWORD, const wchar_t *, ...); // rsi
  void (*v79)(_QWORD, const wchar_t *, ...); // rdi
  __int64 v80; // rbx
  __int64 v81; // rax
  void (***v82)(_QWORD, const wchar_t *, ...); // rsi
  void (*v83)(_QWORD, const wchar_t *, ...); // rdi
  unsigned __int64 v84; // rbx
  __int64 v85; // rax
  void (***v86)(_QWORD, const wchar_t *, ...); // rdi
  void (*v87)(_QWORD, const wchar_t *, ...); // rbx
  __int64 v88; // rax
  void (***v89)(_QWORD, const wchar_t *, ...); // rdi
  void (*v90)(_QWORD, const wchar_t *, ...); // rbx
  __int64 v91; // rax
  void (***v92)(_QWORD, const wchar_t *, ...); // rsi
  void (*v93)(_QWORD, const wchar_t *, ...); // rdi
  unsigned __int64 v94; // rbx
  __int64 v95; // rax
  void (***v96)(_QWORD, const wchar_t *, ...); // rdi
  void (*v97)(_QWORD, const wchar_t *, ...); // rbx
  __int64 v98; // rax
  void (***v99)(_QWORD, const wchar_t *, ...); // rdi
  void (*v100)(_QWORD, const wchar_t *, ...); // rbx
  __int64 v101; // rax
  unsigned int v102; // [rsp+80h] [rbp+8h]
  unsigned int v103; // [rsp+88h] [rbp+10h]
  unsigned int v104; // [rsp+90h] [rbp+18h]
  int v105; // [rsp+90h] [rbp+18h]
  unsigned int v106; // [rsp+98h] [rbp+20h]

  for ( i = 0; ; i = v102 + 1 )
  {
    v102 = i;
    if ( i >= (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 304LL))(*((_QWORD *)this + 1)) )
      break;
    v3 = (unsigned int *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 216LL))(
                           *((_QWORD *)this + 1),
                           i);
    v4 = *v3;
    if ( !(_DWORD)v4 )
    {
      (***((void (****)(_QWORD, const wchar_t *, ...))this + 2))(
        *((_QWORD *)this + 2),
        L"Error in RelationMeta Row (%s) - PrimaryTable must exist.",
        i);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
        L"ERROR - VALIDATION ERROR",
        0x228u,
        0);
    }
    v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 1) + 360LL))(
           *((_QWORD *)this + 1),
           v4,
           0);
    v104 = v5;
    if ( v5 == -1 )
    {
      v99 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
      v100 = **v99;
      v101 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), *v3);
      v100(v99, L"Error in RelationMeta - PrimaryTable (%s) not found in TableMeta", v101);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
        L"ERROR - VALIDATION ERROR",
        0x22Eu,
        0);
    }
    if ( !v3[1] )
    {
      v96 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
      v97 = **v96;
      v98 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), *v3);
      v97(v96, L"Error in RelationMeta - PrimaryTable (%s) has no PrimaryColumns entry", v98);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
        L"ERROR - VALIDATION ERROR",
        0x237u,
        0);
    }
    v6 = (__int64 *)*((_QWORD *)this + 1);
    v7 = *((_DWORD *)this + 6);
    v8 = 0;
    v9 = *v6;
    v10 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v6 + 232))(v6, v5);
    v11 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD))(v9 + 368))(
            v6,
            *(unsigned int *)(v10 + 4),
            v7,
            0);
    v106 = v11;
    while ( 1 )
    {
      v12 = (__int64 *)*((_QWORD *)this + 1);
      v13 = *v12;
      v14 = *(_DWORD *)((*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v12 + 232))(v12, v104) + 4);
      v15 = (_DWORD *)(*(__int64 (__fastcall **)(__int64 *, _QWORD))(v13 + 176))(v12, v11);
      v16 = (__int64 *)*((_QWORD *)this + 1);
      v17 = *v16;
      if ( *v15 != v14 )
        break;
      v18 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(v17 + 176))(v16, v11++);
      v19 = ((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(
               *((_QWORD *)this + 1),
               *(unsigned int *)(v18 + 24))
           & 1) == 0;
      v20 = v8 + 1;
      if ( v19 )
        v20 = v8;
      v8 = v20;
    }
    v103 = v8;
    if ( v8 != (*(unsigned int (__fastcall **)(__int64 *, _QWORD))(v17 + 168))(v16, v3[1]) >> 2 )
    {
      v92 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
      v93 = **v92;
      v94 = (unsigned __int64)(*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 168LL))(
                                *((_QWORD *)this + 1),
                                v3[1]) >> 2;
      v95 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), *v3);
      v93(
        v92,
        L"Error in RelationMeta - PrimaryTable (%s) has (%d) PrimaryColumns but (%d) were supplied",
        v95,
        v8,
        v94);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
        L"ERROR - VALIDATION ERROR",
        0x245u,
        0);
    }
    v21 = v3[2];
    if ( !(_DWORD)v21 )
    {
      (***((void (****)(_QWORD, const wchar_t *, ...))this + 2))(
        *((_QWORD *)this + 2),
        L"Error in RelationMeta Row (%s) - ForeignTable must exist.",
        i);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
        L"ERROR - VALIDATION ERROR",
        0x24Eu,
        0);
    }
    v22 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 1) + 360LL))(
            *((_QWORD *)this + 1),
            v21,
            0);
    v23 = *((_QWORD *)this + 1);
    v24 = v22;
    if ( v22 == -1 )
    {
      v89 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
      v90 = **v89;
      v91 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v23 + 144LL))(v23, v3[2]);
      v90(v89, L"Error in RelationMeta - ForeignTable (%s) not found in TableMeta", v91);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
        L"ERROR - VALIDATION ERROR",
        0x254u,
        0);
    }
    if ( !v3[3] )
    {
      v86 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
      v87 = **v86;
      v88 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v23 + 144LL))(v23, v3[2]);
      v87(v86, L"Error in RelationMeta - ForeignTable (%s) has no ForeignColumns entry", v88);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
        L"ERROR - VALIDATION ERROR",
        0x25Cu,
        0);
    }
    if ( v8 != (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v23 + 168LL))(v23) >> 2 )
    {
      v82 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
      v83 = **v82;
      v84 = (unsigned __int64)(*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 168LL))(
                                *((_QWORD *)this + 1),
                                v3[3]) >> 2;
      v85 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), *v3);
      v83(
        v82,
        L"Error in RelationMeta - PrimaryTable (%s) has (%d) PrimaryColumns but (%d) ForeignColumns were supplied",
        v85,
        v8,
        v84);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
        L"ERROR - VALIDATION ERROR",
        0x261u,
        0);
    }
    if ( !v3[4] )
      v3[4] = *((_DWORD *)this + 6);
    if ( ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 152LL))(*((_QWORD *)this + 1)) & 0xC) == 8 )
    {
      v25 = (__int64 *)*((_QWORD *)this + 1);
      v26 = *v25;
      v27 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v25 + 152))(v25, v3[4]);
      v3[4] = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(v26 + 16))(v25, v27 | 4u);
    }
    v28 = (__int64 *)*((_QWORD *)this + 1);
    v29 = *((_DWORD *)this + 6);
    v30 = *v28;
    v31 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v28 + 232))(v28, v24);
    v32 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD))(v30 + 368))(
            v28,
            *(unsigned int *)(v31 + 4),
            v29,
            0);
    v105 = v32;
    v33 = 0;
    while ( (unsigned int)v33 < v8 )
    {
      v34 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 128LL))(
                          *((_QWORD *)this + 1),
                          v3[3])
                      + 4 * v33);
      v35 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 128LL))(
                          *((_QWORD *)this + 1),
                          v3[1])
                      + 4 * v33);
      v36 = (_DWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 176LL))(
                        *((_QWORD *)this + 1),
                        (unsigned int)(v34 + v32));
      v37 = (_DWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 176LL))(
                        *((_QWORD *)this + 1),
                        v35 + v106);
      v38 = v37;
      if ( v36[4] != v37[4] )
      {
        v78 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
        v79 = **v78;
        v80 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(
                *((_QWORD *)this + 1),
                v3[2]);
        v81 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), *v3);
        v79(
          v78,
          L"Error in RelationMeta - PrimaryTable (%s), ForeignTable (%s) - ColumnMeta.Type mismatch between ForeignColumn "
           "/ PrimaryColumn %dth PrimaryKey",
          v81,
          v80,
          v33);
        ThrowException(
          L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
          L"ERROR - VALIDATION ERROR",
          0x285u,
          0);
      }
      if ( v36[5] != v37[5] )
      {
        v74 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
        v75 = **v74;
        v76 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(
                *((_QWORD *)this + 1),
                v3[2]);
        v77 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), *v3);
        v75(
          v74,
          L"Error in RelationMeta - PrimaryTable (%s), ForeignTable (%s) - ColumnMeta.Size mismatch between ForeignColumn "
           "/ PrimaryColumn %dth PrimaryKey",
          v77,
          v76,
          v33);
        ThrowException(
          L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
          L"ERROR - VALIDATION ERROR",
          0x28Fu,
          0);
      }
      if ( v36[8] != v37[8] )
      {
        v70 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
        v71 = **v70;
        v72 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(
                *((_QWORD *)this + 1),
                v3[2]);
        v73 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), *v3);
        v71(
          v70,
          L"Error in RelationMeta - PrimaryTable (%s), ForeignTable (%s) - ColumnMeta.FlagMask mismatch between ForeignCol"
           "umn / PrimaryColumn %dth PrimaryKey",
          v73,
          v72,
          v33);
        ThrowException(
          L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
          L"ERROR - VALIDATION ERROR",
          0x299u,
          0);
      }
      if ( v36[9] != v37[9] )
      {
        v66 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
        v67 = **v66;
        v68 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(
                *((_QWORD *)this + 1),
                v3[2]);
        v69 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), *v3);
        v67(
          v66,
          L"Error in RelationMeta - PrimaryTable (%s), ForeignTable (%s) - ColumnMeta.StartingNumber mismatch between Fore"
           "ignColumn / PrimaryColumn %dth PrimaryKey",
          v69,
          v68,
          v33);
        ThrowException(
          L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
          L"ERROR - VALIDATION ERROR",
          0x2A3u,
          0);
      }
      if ( v36[10] != v37[10] )
      {
        v62 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
        v63 = **v62;
        v64 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(
                *((_QWORD *)this + 1),
                v3[2]);
        v65 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), *v3);
        v63(
          v62,
          L"Error in RelationMeta - PrimaryTable (%s), ForeignTable (%s) - ColumnMeta.EndingNumber mismatch between Foreig"
           "nColumn / PrimaryColumn %dth PrimaryKey",
          v65,
          v64,
          v33);
        ThrowException(
          L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
          L"ERROR - VALIDATION ERROR",
          0x2ADu,
          0);
      }
      if ( v36[11] != v37[11] )
      {
        v58 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
        v59 = **v58;
        v60 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(
                *((_QWORD *)this + 1),
                v3[2]);
        v61 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), *v3);
        v59(
          v58,
          L"Error in RelationMeta - PrimaryTable (%s), ForeignTable (%s) - ColumnMeta.CharacterSet mismatch between Foreig"
           "nColumn / PrimaryColumn %dth PrimaryKey",
          v61,
          v60,
          v33);
        ThrowException(
          L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
          L"ERROR - VALIDATION ERROR",
          0x2B7u,
          0);
      }
      v39 = *((_QWORD *)this + 1);
      v40 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v39 + 152LL);
      v41 = v40(v39, (unsigned int)v37[6]) & 0x1FF000E0;
      v42 = v40(v39, (unsigned int)v36[6]);
      v43 = *((_QWORD *)this + 1);
      if ( (v42 & 0x1FF000E0) != (_DWORD)v41 )
      {
        v54 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
        v55 = **v54;
        v56 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v43 + 144LL))(v43, v3[2]);
        v57 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), *v3);
        v55(
          v54,
          L"Error in RelationMeta - PrimaryTable (%s), ForeignTable (%s) - ColumnMeta.MetaFlags mismatch between ForeignCo"
           "lumn / PrimaryColumn %dth PrimaryKey",
          v57,
          v56,
          v33);
        ThrowException(
          L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
          L"ERROR - VALIDATION ERROR",
          0x2C3u,
          0);
      }
      if ( ((*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v43 + 152LL))(v43, v3[4]) & 4) != 0 )
      {
        v44 = *((_QWORD *)this + 1);
        v45 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v44 + 152LL);
        v46 = v45(v44, (unsigned int)v38[6]);
        if ( (v45(v44, (unsigned int)v36[6]) & 0x80000) != (v46 & 0x80000) )
        {
          v50 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
          v51 = **v50;
          v52 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(
                  *((_QWORD *)this + 1),
                  v3[2]);
          v53 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(
                  *((_QWORD *)this + 1),
                  *v3);
          v51(
            v50,
            L"Error in RelationMeta - PrimaryTable (%s), ForeignTable (%s) - ColumnMeta.MetaFlags mismatch between Foreign"
             "Column / PrimaryColumn %dth PrimaryKey",
            v53,
            v52,
            v33);
          ThrowException(
            L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
            L"ERROR - VALIDATION ERROR",
            0x2CFu,
            0);
        }
      }
      v47 = (__int64 *)*((_QWORD *)this + 1);
      v48 = *v47;
      v49 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v47 + 152))(v47, (unsigned int)v36[6]);
      v8 = v103;
      v33 = (unsigned int)(v33 + 1);
      v32 = v105;
      v36[6] = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(v48 + 16))(v47, v49 | 2u);
    }
  }
}

```

## disassembly

```asm
0x18001f02c  push    rbx
0x18001f02e  push    rbp
0x18001f02f  push    rsi
0x18001f030  push    rdi
0x18001f031  push    r12
0x18001f033  push    r13
0x18001f035  push    r14
0x18001f037  push    r15
0x18001f039  sub     rsp, 38h
0x18001f03d  mov     rbp, rcx
0x18001f040  xor     r15d, r15d
0x18001f043  mov     rcx, [rbp+8]
0x18001f047  mov     [rsp+78h+arg_0], r15d
0x18001f04f  mov     rax, [rcx]
0x18001f052  mov     rax, [rax+130h]
0x18001f059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f05e  cmp     r15d, eax
0x18001f061  jnb     loc_18001FA82
0x18001f067  mov     rcx, [rbp+8]
0x18001f06b  mov     edx, r15d
0x18001f06e  mov     rax, [rcx]
0x18001f071  mov     rax, [rax+0D8h]
0x18001f078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f07d  mov     r14, rax
0x18001f080  mov     edx, [rax]
0x18001f082  test    edx, edx
0x18001f084  jz      loc_18001FA4C
0x18001f08a  mov     rcx, [rbp+8]
0x18001f08e  xor     r8d, r8d
0x18001f091  mov     rax, [rcx]
0x18001f094  mov     rax, [rax+168h]
0x18001f09b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0a0  mov     [rsp+78h+arg_10], eax
0x18001f0a7  cmp     eax, 0FFFFFFFFh
0x18001f0aa  jz      loc_18001F9FA
0x18001f0b0  cmp     dword ptr [r14+4], 0
0x18001f0b5  jz      loc_18001F9A8
0x18001f0bb  mov     rsi, [rbp+8]
0x18001f0bf  mov     edx, eax
0x18001f0c1  mov     edi, [rbp+18h]
0x18001f0c4  mov     rcx, rsi
0x18001f0c7  xor     r13d, r13d
0x18001f0ca  mov     rbx, [rsi]
0x18001f0cd  mov     rax, [rbx+0E8h]
0x18001f0d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0d9  xor     r9d, r9d
0x18001f0dc  mov     r8d, edi
0x18001f0df  mov     rcx, rsi
0x18001f0e2  mov     edx, [rax+4]
0x18001f0e5  mov     rax, [rbx+170h]
0x18001f0ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0f1  mov     r15d, [rsp+78h+arg_10]
0x18001f0f9  mov     r12d, eax
0x18001f0fc  mov     [rsp+78h+arg_18], eax
0x18001f103  mov     rsi, [rbp+8]
0x18001f107  mov     edx, r15d
0x18001f10a  mov     rcx, rsi
0x18001f10d  mov     rbx, [rsi]
0x18001f110  mov     rax, [rbx+0E8h]
0x18001f117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f11c  mov     edx, r12d
0x18001f11f  mov     rcx, rsi
0x18001f122  mov     edi, [rax+4]
0x18001f125  mov     rax, [rbx+0B0h]
0x18001f12c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f131  mov     rcx, [rbp+8]
0x18001f135  mov     r8, [rcx]
0x18001f138  cmp     [rax], edi
0x18001f13a  jnz     short loc_18001F177
0x18001f13c  mov     rax, [r8+0B0h]
0x18001f143  mov     edx, r12d
0x18001f146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f14b  mov     rcx, [rbp+8]
0x18001f14f  mov     r8, rax
0x18001f152  inc     r12d
0x18001f155  mov     rdx, [rcx]
0x18001f158  mov     rax, [rdx+98h]
0x18001f15f  mov     edx, [r8+18h]
0x18001f163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f168  test    al, 1
0x18001f16a  lea     eax, [r13+1]
0x18001f16e  cmovz   eax, r13d
0x18001f172  mov     r13d, eax
0x18001f175  jmp     short loc_18001F103
0x18001f177  mov     edx, [r14+4]
0x18001f17b  mov     rax, [r8+0A8h]
0x18001f182  mov     [rsp+78h+arg_8], r13d
0x18001f18a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f18f  mov     r15d, [rsp+78h+arg_0]
0x18001f197  shr     eax, 2
0x18001f19a  cmp     r13d, eax
0x18001f19d  jnz     loc_18001F931
0x18001f1a3  mov     edx, [r14+8]
0x18001f1a7  test    edx, edx
0x18001f1a9  jz      loc_18001F8FB
0x18001f1af  mov     rcx, [rbp+8]
0x18001f1b3  xor     r8d, r8d
0x18001f1b6  mov     rax, [rcx]
0x18001f1b9  mov     rax, [rax+168h]
0x18001f1c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1c5  mov     rcx, [rbp+8]
0x18001f1c9  mov     r15d, eax
0x18001f1cc  cmp     eax, 0FFFFFFFFh
0x18001f1cf  jz      loc_18001F8AC
0x18001f1d5  mov     edx, [r14+0Ch]
0x18001f1d9  test    edx, edx
0x18001f1db  jz      loc_18001F85D
0x18001f1e1  mov     r8, [rcx]
0x18001f1e4  mov     rax, [r8+0A8h]
0x18001f1eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1f0  shr     eax, 2
0x18001f1f3  cmp     r13d, eax
0x18001f1f6  jnz     loc_18001F7E6
0x18001f1fc  mov     edx, [r14+10h]
0x18001f200  test    edx, edx
0x18001f202  jnz     short loc_18001F20B
0x18001f204  mov     edx, [rbp+18h]
0x18001f207  mov     [r14+10h], edx
0x18001f20b  mov     rcx, [rbp+8]
0x18001f20f  mov     rax, [rcx]
0x18001f212  mov     rax, [rax+98h]
0x18001f219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f21e  and     al, 0Ch
0x18001f220  cmp     al, 8
0x18001f222  jnz     short loc_18001F253
0x18001f224  mov     rdi, [rbp+8]
0x18001f228  mov     edx, [r14+10h]
0x18001f22c  mov     rcx, rdi
0x18001f22f  mov     rbx, [rdi]
0x18001f232  mov     rax, [rbx+98h]
0x18001f239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f23e  or      eax, 4
0x18001f241  mov     rcx, rdi
0x18001f244  mov     edx, eax
0x18001f246  mov     rax, [rbx+10h]
0x18001f24a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f24f  mov     [r14+10h], eax
0x18001f253  mov     rsi, [rbp+8]
0x18001f257  mov     edx, r15d
0x18001f25a  mov     edi, [rbp+18h]
0x18001f25d  mov     rcx, rsi
0x18001f260  mov     rbx, [rsi]
0x18001f263  mov     rax, [rbx+0E8h]
0x18001f26a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f26f  xor     r9d, r9d
0x18001f272  mov     r8d, edi
0x18001f275  mov     rcx, rsi
0x18001f278  mov     edx, [rax+4]
0x18001f27b  mov     rax, [rbx+170h]
0x18001f282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f287  mov     esi, eax
0x18001f289  mov     [rsp+78h+arg_10], eax
0x18001f290  xor     r12d, r12d
0x18001f293  cmp     r12d, r13d
0x18001f296  jnb     loc_18001F43A
0x18001f29c  mov     rcx, [rbp+8]
0x18001f2a0  mov     rdx, [rcx]
0x18001f2a3  mov     rax, [rdx+80h]
0x18001f2aa  mov     edx, [r14+0Ch]
0x18001f2ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2b3  mov     rcx, [rbp+8]
0x18001f2b7  mov     edx, [r14+4]
0x18001f2bb  mov     edi, [rax+r12*4]
0x18001f2bf  mov     rax, [rcx]
0x18001f2c2  mov     rax, [rax+80h]
0x18001f2c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2ce  mov     rcx, [rbp+8]
0x18001f2d2  lea     edx, [rdi+rsi]
0x18001f2d5  mov     ebx, [rax+r12*4]
0x18001f2d9  mov     rax, [rcx]
0x18001f2dc  mov     rax, [rax+0B0h]
0x18001f2e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2e8  mov     rcx, [rbp+8]
0x18001f2ec  mov     r15, rax
0x18001f2ef  mov     edx, [rsp+78h+arg_18]
0x18001f2f6  add     edx, ebx
0x18001f2f8  mov     r8, [rcx]
0x18001f2fb  mov     rax, [r8+0B0h]
0x18001f302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f307  mov     r13, rax
0x18001f30a  mov     ecx, [rax+10h]
0x18001f30d  cmp     [r15+10h], ecx
0x18001f311  jnz     loc_18001F772
0x18001f317  mov     ecx, [rax+14h]
0x18001f31a  cmp     [r15+14h], ecx
0x18001f31e  jnz     loc_18001F6FE
0x18001f324  mov     ecx, [rax+20h]
0x18001f327  cmp     [r15+20h], ecx
0x18001f32b  jnz     loc_18001F68A
0x18001f331  mov     eax, [rax+24h]
0x18001f334  cmp     [r15+24h], eax
0x18001f338  jnz     loc_18001F616
0x18001f33e  mov     eax, [r13+28h]
0x18001f342  cmp     [r15+28h], eax
0x18001f346  jnz     loc_18001F5A2
0x18001f34c  mov     eax, [r13+2Ch]
0x18001f350  cmp     [r15+2Ch], eax
0x18001f354  jnz     loc_18001F52E
0x18001f35a  mov     rsi, [rbp+8]
0x18001f35e  mov     edx, [r13+18h]
0x18001f362  mov     rcx, rsi
0x18001f365  mov     rax, [rsi]
0x18001f368  mov     rdi, [rax+98h]
0x18001f36f  mov     rax, rdi
0x18001f372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f377  mov     edx, [r15+18h]
0x18001f37b  mov     ebx, eax
0x18001f37d  mov     rax, rdi
0x18001f380  mov     rcx, rsi
0x18001f383  and     ebx, 1FF000E0h
0x18001f389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f38e  mov     rcx, [rbp+8]
0x18001f392  and     eax, 1FF000E0h
0x18001f397  cmp     eax, ebx
0x18001f399  jnz     loc_18001F4BE
0x18001f39f  mov     rax, [rcx]
0x18001f3a2  mov     edx, [r14+10h]
0x18001f3a6  mov     rax, [rax+98h]
0x18001f3ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3b2  test    al, 4
0x18001f3b4  jz      short loc_18001F3F4
0x18001f3b6  mov     rsi, [rbp+8]
0x18001f3ba  mov     edx, [r13+18h]
0x18001f3be  mov     rcx, rsi
0x18001f3c1  mov     rax, [rsi]
0x18001f3c4  mov     rdi, [rax+98h]
0x18001f3cb  mov     rax, rdi
0x18001f3ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3d3  mov     edx, [r15+18h]
0x18001f3d7  mov     ebx, eax
0x18001f3d9  mov     r13d, 80000h
0x18001f3df  mov     rax, rdi
0x18001f3e2  mov     rcx, rsi
0x18001f3e5  and     ebx, r13d
0x18001f3e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3ed  and     eax, r13d
0x18001f3f0  cmp     eax, ebx
0x18001f3f2  jnz     short loc_18001F44A
0x18001f3f4  mov     rdi, [rbp+8]
0x18001f3f8  mov     edx, [r15+18h]
0x18001f3fc  mov     rcx, rdi
0x18001f3ff  mov     rbx, [rdi]
0x18001f402  mov     rax, [rbx+98h]
0x18001f409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f40e  or      eax, 2
0x18001f411  mov     rcx, rdi
0x18001f414  mov     edx, eax
0x18001f416  mov     rax, [rbx+10h]
0x18001f41a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f41f  mov     r13d, [rsp+78h+arg_8]
0x18001f427  inc     r12d
0x18001f42a  mov     esi, [rsp+78h+arg_10]
0x18001f431  mov     [r15+18h], eax
0x18001f435  jmp     loc_18001F293
0x18001f43a  mov     r15d, [rsp+78h+arg_0]
0x18001f442  inc     r15d
0x18001f445  jmp     loc_18001F043
0x18001f44a  mov     rsi, [rbp+10h]
0x18001f44e  mov     rcx, [rbp+8]
0x18001f452  mov     edx, [r14+8]
0x18001f456  mov     rax, [rsi]
0x18001f459  mov     rdi, [rax]
0x18001f45c  mov     rax, [rcx]
0x18001f45f  mov     rax, [rax+90h]
0x18001f466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f46b  mov     rcx, [rbp+8]
0x18001f46f  mov     rbx, rax
0x18001f472  mov     edx, [r14]
0x18001f475  mov     r8, [rcx]
0x18001f478  mov     rax, [r8+90h]
0x18001f47f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f484  mov     r8, rax
0x18001f487  mov     dword ptr [rsp+78h+var_58], r12d
0x18001f48c  mov     rax, rdi
0x18001f48f  lea     rdx, aErrorInRelatio_3; "Error in RelationMeta - PrimaryTable (%"...
0x18001f496  mov     r9, rbx
0x18001f499  mov     rcx, rsi
0x18001f49c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4a1  xor     r9d, r9d; unsigned int
0x18001f4a4  lea     rdx, aErrorValidatio; "ERROR - VALIDATION ERROR"
0x18001f4ab  mov     r8d, 2CFh; unsigned int
0x18001f4b1  lea     rcx, aInetsrvIisMbCo_13; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001f4b8  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001f4be  mov     rsi, [rbp+10h]
0x18001f4c2  mov     edx, [r14+8]
0x18001f4c6  mov     rax, [rsi]
0x18001f4c9  mov     rdi, [rax]
0x18001f4cc  mov     rax, [rcx]
0x18001f4cf  mov     rax, [rax+90h]
0x18001f4d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4db  mov     rcx, [rbp+8]
0x18001f4df  mov     rbx, rax
0x18001f4e2  mov     rdx, [rcx]
0x18001f4e5  mov     rax, [rdx+90h]
0x18001f4ec  mov     edx, [r14]
0x18001f4ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4f4  mov     r8, rax
0x18001f4f7  mov     dword ptr [rsp+78h+var_58], r12d
0x18001f4fc  mov     rax, rdi
0x18001f4ff  lea     rdx, aErrorInRelatio_3; "Error in RelationMeta - PrimaryTable (%"...
  ... truncated ...
```
