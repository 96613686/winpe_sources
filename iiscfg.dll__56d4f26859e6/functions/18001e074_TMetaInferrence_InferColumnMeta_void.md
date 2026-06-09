# TMetaInferrence::InferColumnMeta(void)

- ea: `0x18001e074`
- end: `0x18001e9cd`
- name: `?InferColumnMeta@TMetaInferrence@@AEAAXXZ`
- size: `2393`
- prototype: `void __fastcall(TMetaInferrence *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001e000`

## callees

- `0x180017ad8`
- `0x18001e074`
- `0x180020c1c`
- `0x180030010`

## string_xrefs

- `0x18001e5d4`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001e641`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001e6b4`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001e723`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001e792`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001e801`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001e853`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001e89f`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001e8ef`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001e938`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001e9a8`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001e7dc`: `Error - Table (%s) has XMLBLOB column (%s) marked as the PrimaryKey`

## pseudocode

```c
void __fastcall TMetaInferrence::InferColumnMeta(TMetaInferrence *this)
{
  char v1; // si
  unsigned int v2; // r15d
  unsigned int v4; // r12d
  int v5; // r13d
  unsigned int *v6; // rax
  __int64 *v7; // rcx
  unsigned int *v8; // r14
  __int64 v9; // rdx
  const unsigned __int16 *v10; // rax
  const unsigned __int16 *v11; // rax
  int v12; // edi
  int v13; // ebx
  unsigned int v14; // r15d
  int v15; // eax
  int v16; // edi
  unsigned int i; // ebx
  unsigned int v18; // r12d
  unsigned int v19; // r13d
  __int64 *v20; // rdi
  __int64 v21; // rbx
  __int64 v22; // rax
  const unsigned __int16 *v23; // rax
  void (***v24)(_QWORD, const wchar_t *, ...); // rdi
  void (*v25)(_QWORD, const wchar_t *, ...); // rbx
  __int64 v26; // rax
  void (***v27)(_QWORD, const wchar_t *, ...); // rsi
  void (*v28)(_QWORD, const wchar_t *, ...); // rdi
  __int64 v29; // rbx
  __int64 v30; // rax
  void (***v31)(_QWORD, const wchar_t *, ...); // rsi
  void (*v32)(_QWORD, const wchar_t *, ...); // rdi
  __int64 v33; // rbx
  __int64 v34; // rax
  void (***v35)(_QWORD, const wchar_t *, ...); // rsi
  void (*v36)(_QWORD, const wchar_t *, ...); // rdi
  __int64 v37; // rbx
  __int64 v38; // rax
  void (***v39)(_QWORD, const wchar_t *, ...); // rsi
  void (*v40)(_QWORD, const wchar_t *, ...); // rdi
  __int64 v41; // rbx
  __int64 v42; // rax
  void (***v43)(_QWORD, const wchar_t *, ...); // rsi
  void (*v44)(_QWORD, const wchar_t *, ...); // rdi
  __int64 v45; // rbx
  __int64 v46; // rax
  void (***v47)(_QWORD, const wchar_t *, ...); // rdi
  void (*v48)(_QWORD, const wchar_t *, ...); // rbx
  __int64 v49; // rax
  void (***v50)(_QWORD, const wchar_t *, ...); // rdi
  void (*v51)(_QWORD, const wchar_t *, ...); // rbx
  __int64 v52; // rax
  void (***v53)(_QWORD, const wchar_t *, ...); // rdi
  void (*v54)(_QWORD, const wchar_t *, ...); // rbx
  __int64 v55; // rax
  void (***v56)(_QWORD, const wchar_t *, ...); // rdi
  void (*v57)(_QWORD, const wchar_t *, ...); // rbx
  __int64 v58; // rax
  __int64 *v59; // rdi
  void (***v60)(_QWORD, const wchar_t *, ...); // r14
  __int64 v61; // rbx
  void (*v62)(_QWORD, const wchar_t *, ...); // rsi
  unsigned int *v63; // rax
  __int64 v64; // rax
  int v65; // [rsp+70h] [rbp+8h]
  unsigned int v66; // [rsp+78h] [rbp+10h]
  int v67; // [rsp+80h] [rbp+18h]

  v1 = 13;
  v2 = 0;
  v4 = 0;
  v5 = 128;
  v65 = 128;
  while ( 1 )
  {
    v66 = v4;
    if ( v4 >= (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 264LL))(*((_QWORD *)this + 1)) )
      break;
    v6 = (unsigned int *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 176LL))(
                           *((_QWORD *)this + 1),
                           v4);
    v7 = (__int64 *)*((_QWORD *)this + 1);
    v8 = v6;
    v9 = *v7;
    if ( !v6[2] )
    {
      v56 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
      v57 = **v56;
      v58 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(v9 + 144))(v7, *v6);
      v57(
        v56,
        L"Validation Error in ColumnMeta for Table (%s). ColumnMeta.InternalName is a primarykey, so it must not be NULL.",
        v58);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
        L"ERROR - VALIDATION ERROR",
        0x37u,
        0);
    }
    v10 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64 *, _QWORD))(v9 + 144))(v7, v6[2]);
    TMetaInferrence::ValidateStringAsLegalVariableName(this, v10, 0, 0);
    if ( v8[3] )
    {
      v11 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1));
      TMetaInferrence::ValidateStringAsLegalVariableName(this, v11, 0, 0);
    }
    else
    {
      v8[3] = v8[2];
    }
    if ( v2 != *v8 )
    {
      if ( (v1 & 1) == 0 )
      {
        v24 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
        v25 = **v24;
        v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), v2);
        v25(
          v24,
          L"Error - Table (%s) has no primarykey.  fCOLUMNMETA_PRIMARYKEY must be set on at least one column per table",
          v26);
        ThrowException(
          L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
          L"ERROR - VALIDATION ERROR",
          0x5Fu,
          0);
      }
      v1 = 0;
      v5 = 0;
      v65 = 0;
    }
    v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(*((_QWORD *)this + 1), v8[6]);
    if ( ((unsigned __int8)v1 & (unsigned __int8)v12 & 4) != 0 )
    {
      v53 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
      v54 = **v53;
      v55 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), *v8);
      v54(v53, L"Error - Table (%s) has more than one NameColumn", v55);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
        L"ERROR - VALIDATION ERROR",
        0x6Fu,
        0);
    }
    if ( ((unsigned __int8)v1 & (unsigned __int8)v12 & 8) != 0 )
    {
      v50 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
      v51 = **v50;
      v52 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), *v8);
      v51(v50, L"Error - Table (%s) has more than one NavColumn", v52);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
        L"ERROR - VALIDATION ERROR",
        0x77u,
        0);
    }
    if ( (v12 & 0x40) != 0
      && (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(
           *((_QWORD *)this + 1),
           v8[4]) != 19
      && (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(
           *((_QWORD *)this + 1),
           v8[4]) != 1 )
    {
      v27 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
      v28 = **v27;
      v29 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), v8[2]);
      v30 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), *v8);
      v28(v27, L"Error - Table (%s) Column (%s) - fCOLUMNMETA_FLAG must only be set on UI4 columns", v30, v29);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
        L"ERROR - VALIDATION ERROR",
        0x7Fu,
        0);
    }
    if ( (v12 & 0x80u) != 0
      && (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(
           *((_QWORD *)this + 1),
           v8[4]) != 19
      && (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(
           *((_QWORD *)this + 1),
           v8[4]) != 1 )
    {
      v31 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
      v32 = **v31;
      v33 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), v8[2]);
      v34 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), *v8);
      v32(v31, L"Error - Table (%s) Column (%s) - fCOLUMNMETA_ENUM must only be set on UI4 columns", v34, v33);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
        L"ERROR - VALIDATION ERROR",
        0x87u,
        0);
    }
    if ( (v12 & 1) != 0 )
      v12 |= 0x80000u;
    if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(
           *((_QWORD *)this + 1),
           v8[5]) == -1
      && ((*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(
            *((_QWORD *)this + 1),
            v8[4]) == 128
       || (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(
            *((_QWORD *)this + 1),
            v8[4]) == 3) )
    {
      v12 |= 0x8000000u;
    }
    v13 = v12 | 0x100000;
    if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(
           *((_QWORD *)this + 1),
           v8[5]) == -1 )
      v13 = v12;
    if ( !v8[9] )
      v8[9] = *((_DWORD *)this + 6);
    if ( !v8[10] )
      v8[10] = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1) + 16LL))(
                 *((_QWORD *)this + 1),
                 0xFFFFFFFFLL);
    if ( ((*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(
            *((_QWORD *)this + 1),
            v8[4]) == 19
       || (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(
            *((_QWORD *)this + 1),
            v8[4]) == 1)
      && ((*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(
            *((_QWORD *)this + 1),
            v8[9])
       || (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(
            *((_QWORD *)this + 1),
            v8[10]) != -1) )
    {
      v13 |= 0x200000u;
    }
    v14 = v13 | 0x10000000;
    if ( (v13 & 0x100000) != 0 )
      v14 = v13;
    if ( (*(char (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(*((_QWORD *)this + 1), v8[12]) < 0
      && (*(char (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(*((_QWORD *)this + 1), v8[6]) >= 0 )
    {
      v35 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
      v36 = **v35;
      v37 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), v8[2]);
      v38 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), *v8);
      v36(v35, L"Error - Table (%s) - USEASPUBLICROWNAME was set on a non ENUM Column (%s)", v38, v37);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
        L"ERROR - VALIDATION ERROR",
        0xC5u,
        0);
    }
    v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(*((_QWORD *)this + 1), v8[12]);
    v67 = v15;
    v16 = v15;
    if ( (v5 & v15 & 0x80u) != 0 )
    {
      v47 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
      v48 = **v47;
      v49 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), *v8);
      v48(v47, L"Error - Table (%s) has more than one PublicRowNameColumn", v49);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
        L"ERROR - VALIDATION ERROR",
        0xCEu,
        0);
    }
    if ( (v14 & 1) != 0 && (v15 & 0x1000) != 0 )
    {
      v43 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
      v44 = **v43;
      v45 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), v8[2]);
      v46 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), *v8);
      v44(v43, L"Error - Table (%s) has XMLBLOB column (%s) marked as the PrimaryKey", v46, v45);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
        L"ERROR - VALIDATION ERROR",
        0xD6u,
        0);
    }
    *((_QWORD *)v8 + 9) = 0;
    v8[8] = *((_DWORD *)this + 6);
    if ( (v14 & 0xC0) != 0 )
    {
      for ( i = 0;
            i < (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 328LL))(*((_QWORD *)this + 1))
         && (*(_DWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 240LL))(
                          *((_QWORD *)this + 1),
                          i) != *v8
          || *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 240LL))(
                           *((_QWORD *)this + 1),
                           v8[19])
                       + 4) != v8[1]);
            i = v8[19] )
      {
        ++v8[19];
      }
      v18 = v8[19];
      if ( v18 == (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 328LL))(*((_QWORD *)this + 1)) )
      {
        v39 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
        v40 = **v39;
        v41 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(
                *((_QWORD *)this + 1),
                v8[2]);
        v42 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), *v8);
        v40(v39, L"Error - Table (%s) - No TagMeta found for Column (%s)", v42, v41);
        ThrowException(
          L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
          L"ERROR - VALIDATION ERROR",
          0xEFu,
          0);
      }
      v19 = 0;
      while ( v18 < (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 328LL))(*((_QWORD *)this + 1))
           && *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 240LL))(
                           *((_QWORD *)this + 1),
                           v18) == *v8
           && *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 240LL))(
                            *((_QWORD *)this + 1),
                            v18)
                        + 4) == v8[1] )
      {
        v20 = (__int64 *)*((_QWORD *)this + 1);
        v21 = *v20;
        v22 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v20 + 240))(v20, v18);
        v19 |= (*(__int64 (__fastcall **)(__int64 *, _QWORD))(v21 + 152))(v20, *(unsigned int *)(v22 + 16));
        ++v18;
        ++v8[18];
      }
      if ( (v14 & 0x40) != 0 )
        v8[8] = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1), v19);
      v5 = v65;
      v4 = v66;
      v16 = v67;
    }
    v1 |= v14;
    v8[6] = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1), v14);
    v2 = *v8;
    v5 |= v16;
    v65 = v5;
    if ( !v8[13] )
      v8[13] = *((_DWORD *)this + 6);
    if ( !v8[14] )
      v8[14] = *((_DWORD *)this + 6);
    if ( v8[17] )
    {
      v23 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1));
      TMetaInferrence::ValidateStringAsLegalVariableName(this, v23, 0, 0);
    }
    else
    {
      v8[17] = v8[3];
    }
    ++v4;
  }
  if ( (v1 & 1) == 0 )
  {
    v59 = (__int64 *)*((_QWORD *)this + 1);
    v60 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
    v61 = *v59;
    v62 = **v60;
    v63 = (unsigned int *)(*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v59 + 176))(v59, v2);
    v64 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(v61 + 144))(v59, *v63);
    v62(
      v60,
      L"Error - Table (%s) has no primarykey.  fCOLUMNMETA_PRIMARYKEY must be set on at least one column per table",
      v64);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
      L"ERROR - VALIDATION ERROR",
      0x125u,
      0);
  }
}

```

## disassembly

```asm
0x18001e074  mov     [rsp+arg_18], rbx
0x18001e079  push    rbp
0x18001e07a  push    rsi
0x18001e07b  push    rdi
0x18001e07c  push    r12
0x18001e07e  push    r13
0x18001e080  push    r14
0x18001e082  push    r15
0x18001e084  sub     rsp, 30h
0x18001e088  mov     esi, 0Dh
0x18001e08d  xor     r15d, r15d
0x18001e090  mov     rbp, rcx
0x18001e093  xor     r12d, r12d
0x18001e096  lea     r13d, [rsi+73h]
0x18001e09a  mov     [rsp+68h+arg_0], r13d
0x18001e09f  mov     rcx, [rbp+8]
0x18001e0a3  mov     [rsp+68h+arg_8], r12d
0x18001e0a8  mov     rax, [rcx]
0x18001e0ab  mov     rax, [rax+108h]
0x18001e0b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0b7  cmp     r12d, eax
0x18001e0ba  jnb     loc_18001E949
0x18001e0c0  mov     rcx, [rbp+8]
0x18001e0c4  mov     edx, r12d
0x18001e0c7  mov     rax, [rcx]
0x18001e0ca  mov     rax, [rax+0B0h]
0x18001e0d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0d6  mov     rcx, [rbp+8]
0x18001e0da  mov     r14, rax
0x18001e0dd  cmp     dword ptr [rax+8], 0
0x18001e0e1  mov     rdx, [rcx]
0x18001e0e4  jz      loc_18001E900
0x18001e0ea  mov     rax, [rdx+90h]
0x18001e0f1  mov     edx, [r14+8]
0x18001e0f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0fa  mov     rdx, rax; unsigned __int16 *
0x18001e0fd  xor     r9d, r9d; bool
0x18001e100  xor     r8d, r8d; unsigned __int16 *
0x18001e103  mov     rcx, rbp; this
0x18001e106  call    ?ValidateStringAsLegalVariableName@TMetaInferrence@@AEAAXPEBG0_N@Z; TMetaInferrence::ValidateStringAsLegalVariableName(ushort const *,ushort const *,bool)
0x18001e10b  mov     edx, [r14+0Ch]
0x18001e10f  test    edx, edx
0x18001e111  jnz     short loc_18001E11D
0x18001e113  mov     eax, [r14+8]
0x18001e117  mov     [r14+0Ch], eax
0x18001e11b  jmp     short loc_18001E141
0x18001e11d  mov     rcx, [rbp+8]
0x18001e121  mov     rax, [rcx]
0x18001e124  mov     rax, [rax+90h]
0x18001e12b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e130  mov     rdx, rax; unsigned __int16 *
0x18001e133  xor     r9d, r9d; bool
0x18001e136  xor     r8d, r8d; unsigned __int16 *
0x18001e139  mov     rcx, rbp; this
0x18001e13c  call    ?ValidateStringAsLegalVariableName@TMetaInferrence@@AEAAXPEBG0_N@Z; TMetaInferrence::ValidateStringAsLegalVariableName(ushort const *,ushort const *,bool)
0x18001e141  cmp     r15d, [r14]
0x18001e144  jz      short loc_18001E15A
0x18001e146  test    sil, 1
0x18001e14a  jz      loc_18001E595
0x18001e150  xor     esi, esi
0x18001e152  xor     r13d, r13d
0x18001e155  mov     [rsp+68h+arg_0], r13d
0x18001e15a  mov     rcx, [rbp+8]
0x18001e15e  mov     edx, [r14+18h]
0x18001e162  mov     rax, [rcx]
0x18001e165  mov     rax, [rax+98h]
0x18001e16c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e171  mov     edi, eax
0x18001e173  and     eax, esi
0x18001e175  test    al, 4
0x18001e177  jnz     loc_18001E8B0
0x18001e17d  test    al, 8
0x18001e17f  jnz     loc_18001E860
0x18001e185  test    dil, 40h
0x18001e189  jz      short loc_18001E1C7
0x18001e18b  mov     rcx, [rbp+8]
0x18001e18f  mov     edx, [r14+10h]
0x18001e193  mov     rax, [rcx]
0x18001e196  mov     rax, [rax+98h]
0x18001e19d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1a2  cmp     eax, 13h
0x18001e1a5  jz      short loc_18001E1C7
0x18001e1a7  mov     rcx, [rbp+8]
0x18001e1ab  mov     edx, [r14+10h]
0x18001e1af  mov     rax, [rcx]
0x18001e1b2  mov     rax, [rax+98h]
0x18001e1b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1be  cmp     eax, 1
0x18001e1c1  jnz     loc_18001E5E5
0x18001e1c7  test    dil, dil
0x18001e1ca  jns     short loc_18001E208
0x18001e1cc  mov     rcx, [rbp+8]
0x18001e1d0  mov     edx, [r14+10h]
0x18001e1d4  mov     rax, [rcx]
0x18001e1d7  mov     rax, [rax+98h]
0x18001e1de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1e3  cmp     eax, 13h
0x18001e1e6  jz      short loc_18001E208
0x18001e1e8  mov     rcx, [rbp+8]
0x18001e1ec  mov     edx, [r14+10h]
0x18001e1f0  mov     rax, [rcx]
0x18001e1f3  mov     rax, [rax+98h]
0x18001e1fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1ff  cmp     eax, 1
0x18001e202  jnz     loc_18001E652
0x18001e208  test    dil, 1
0x18001e20c  jz      short loc_18001E212
0x18001e20e  bts     edi, 13h
0x18001e212  mov     rcx, [rbp+8]
0x18001e216  mov     edx, [r14+14h]
0x18001e21a  mov     rax, [rcx]
0x18001e21d  mov     rax, [rax+98h]
0x18001e224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e229  or      r15d, 0FFFFFFFFh
0x18001e22d  cmp     eax, r15d
0x18001e230  jnz     short loc_18001E270
0x18001e232  mov     rcx, [rbp+8]
0x18001e236  mov     edx, [r14+10h]
0x18001e23a  mov     rax, [rcx]
0x18001e23d  mov     rax, [rax+98h]
0x18001e244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e249  cmp     eax, 80h
0x18001e24e  jz      short loc_18001E26C
0x18001e250  mov     rcx, [rbp+8]
0x18001e254  mov     edx, [r14+10h]
0x18001e258  mov     rax, [rcx]
0x18001e25b  mov     rax, [rax+98h]
0x18001e262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e267  cmp     eax, 3
0x18001e26a  jnz     short loc_18001E270
0x18001e26c  bts     edi, 1Bh
0x18001e270  mov     rcx, [rbp+8]
0x18001e274  mov     edx, [r14+14h]
0x18001e278  mov     rax, [rcx]
0x18001e27b  mov     rax, [rax+98h]
0x18001e282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e287  mov     ebx, edi
0x18001e289  bts     ebx, 14h
0x18001e28d  cmp     eax, r15d
0x18001e290  cmovz   ebx, edi
0x18001e293  cmp     dword ptr [r14+24h], 0
0x18001e298  jnz     short loc_18001E2A1
0x18001e29a  mov     eax, [rbp+18h]
0x18001e29d  mov     [r14+24h], eax
0x18001e2a1  cmp     dword ptr [r14+28h], 0
0x18001e2a6  jnz     short loc_18001E2BF
0x18001e2a8  mov     rcx, [rbp+8]
0x18001e2ac  mov     edx, r15d
0x18001e2af  mov     rax, [rcx]
0x18001e2b2  mov     rax, [rax+10h]
0x18001e2b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2bb  mov     [r14+28h], eax
0x18001e2bf  mov     rcx, [rbp+8]
0x18001e2c3  mov     edx, [r14+10h]
0x18001e2c7  mov     rax, [rcx]
0x18001e2ca  mov     rax, [rax+98h]
0x18001e2d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2d6  cmp     eax, 13h
0x18001e2d9  jz      short loc_18001E2F7
0x18001e2db  mov     rcx, [rbp+8]
0x18001e2df  mov     edx, [r14+10h]
0x18001e2e3  mov     rax, [rcx]
0x18001e2e6  mov     rax, [rax+98h]
0x18001e2ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2f2  cmp     eax, 1
0x18001e2f5  jnz     short loc_18001E332
0x18001e2f7  mov     rcx, [rbp+8]
0x18001e2fb  mov     edx, [r14+24h]
0x18001e2ff  mov     rax, [rcx]
0x18001e302  mov     rax, [rax+98h]
0x18001e309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e30e  test    eax, eax
0x18001e310  jnz     short loc_18001E32E
0x18001e312  mov     rcx, [rbp+8]
0x18001e316  mov     edx, [r14+28h]
0x18001e31a  mov     rax, [rcx]
0x18001e31d  mov     rax, [rax+98h]
0x18001e324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e329  cmp     eax, r15d
0x18001e32c  jz      short loc_18001E332
0x18001e32e  bts     ebx, 15h
0x18001e332  mov     rcx, [rbp+8]
0x18001e336  mov     r15d, ebx
0x18001e339  mov     edx, [r14+30h]
0x18001e33d  bts     r15d, 1Ch
0x18001e342  bt      ebx, 14h
0x18001e346  mov     rax, [rcx]
0x18001e349  cmovb   r15d, ebx
0x18001e34d  mov     rax, [rax+98h]
0x18001e354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e359  test    al, al
0x18001e35b  jns     short loc_18001E37C
0x18001e35d  mov     rcx, [rbp+8]
0x18001e361  mov     edx, [r14+18h]
0x18001e365  mov     rax, [rcx]
0x18001e368  mov     rax, [rax+98h]
0x18001e36f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e374  test    al, 80h
0x18001e376  jz      loc_18001E6C1
0x18001e37c  mov     rcx, [rbp+8]
0x18001e380  mov     edx, [r14+30h]
0x18001e384  mov     rax, [rcx]
0x18001e387  mov     rax, [rax+98h]
0x18001e38e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e393  mov     ecx, eax
0x18001e395  mov     [rsp+68h+arg_10], eax
0x18001e39c  and     ecx, r13d
0x18001e39f  mov     edi, eax
0x18001e3a1  test    cl, cl
0x18001e3a3  js      loc_18001E80E
0x18001e3a9  test    r15b, 1
0x18001e3ad  setnz   dl
0x18001e3b0  bt      eax, 0Ch
0x18001e3b4  setb    cl
0x18001e3b7  test    cl, dl
0x18001e3b9  jnz     loc_18001E79F
0x18001e3bf  mov     qword ptr [r14+48h], 0
0x18001e3c7  mov     eax, [rbp+18h]
0x18001e3ca  mov     [r14+20h], eax
0x18001e3ce  test    r15b, 0C0h
0x18001e3d2  jz      loc_18001E516
0x18001e3d8  xor     ebx, ebx
0x18001e3da  mov     rcx, [rbp+8]
0x18001e3de  mov     rax, [rcx]
0x18001e3e1  mov     rax, [rax+148h]
0x18001e3e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3ed  cmp     ebx, eax
0x18001e3ef  jnb     short loc_18001E437
0x18001e3f1  mov     rcx, [rbp+8]
0x18001e3f5  mov     edx, ebx
0x18001e3f7  mov     rax, [rcx]
0x18001e3fa  mov     rax, [rax+0F0h]
0x18001e401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e406  mov     ecx, [rax]
0x18001e408  cmp     ecx, [r14]
0x18001e40b  jnz     short loc_18001E42D
0x18001e40d  mov     rcx, [rbp+8]
0x18001e411  mov     edx, [r14+4Ch]
0x18001e415  mov     rax, [rcx]
0x18001e418  mov     rax, [rax+0F0h]
0x18001e41f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e424  mov     ecx, [rax+4]
0x18001e427  cmp     ecx, [r14+4]
0x18001e42b  jz      short loc_18001E437
0x18001e42d  inc     dword ptr [r14+4Ch]
0x18001e431  mov     ebx, [r14+4Ch]
0x18001e435  jmp     short loc_18001E3DA
0x18001e437  mov     rcx, [rbp+8]
0x18001e43b  mov     r12d, [r14+4Ch]
0x18001e43f  mov     rax, [rcx]
0x18001e442  mov     rax, [rax+148h]
0x18001e449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e44e  cmp     r12d, eax
0x18001e451  jz      loc_18001E730
0x18001e457  xor     r13d, r13d
0x18001e45a  mov     rcx, [rbp+8]
0x18001e45e  mov     rax, [rcx]
0x18001e461  mov     rax, [rax+148h]
0x18001e468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e46d  cmp     r12d, eax
0x18001e470  jnb     short loc_18001E4E8
0x18001e472  mov     rcx, [rbp+8]
0x18001e476  mov     edx, r12d
0x18001e479  mov     rax, [rcx]
0x18001e47c  mov     rax, [rax+0F0h]
0x18001e483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e488  mov     ecx, [rax]
0x18001e48a  cmp     ecx, [r14]
0x18001e48d  jnz     short loc_18001E4E8
0x18001e48f  mov     rcx, [rbp+8]
0x18001e493  mov     edx, r12d
0x18001e496  mov     rax, [rcx]
0x18001e499  mov     rax, [rax+0F0h]
0x18001e4a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4a5  mov     ecx, [rax+4]
0x18001e4a8  cmp     ecx, [r14+4]
0x18001e4ac  jnz     short loc_18001E4E8
0x18001e4ae  mov     rdi, [rbp+8]
0x18001e4b2  mov     edx, r12d
0x18001e4b5  mov     rcx, rdi
0x18001e4b8  mov     rbx, [rdi]
0x18001e4bb  mov     rax, [rbx+0F0h]
0x18001e4c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4c7  mov     rcx, rdi
0x18001e4ca  mov     edx, [rax+10h]
0x18001e4cd  mov     rax, [rbx+98h]
0x18001e4d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4d9  or      r13d, eax
0x18001e4dc  inc     r12d
0x18001e4df  inc     dword ptr [r14+48h]
0x18001e4e3  jmp     loc_18001E45A
0x18001e4e8  test    r15b, 40h
0x18001e4ec  jz      short loc_18001E505
0x18001e4ee  mov     rcx, [rbp+8]
0x18001e4f2  mov     edx, r13d
0x18001e4f5  mov     rax, [rcx]
0x18001e4f8  mov     rax, [rax+10h]
0x18001e4fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e501  mov     [r14+20h], eax
0x18001e505  mov     r13d, [rsp+68h+arg_0]
  ... truncated ...
```
