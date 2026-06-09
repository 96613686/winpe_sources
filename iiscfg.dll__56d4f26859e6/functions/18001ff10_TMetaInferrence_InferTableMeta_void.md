# TMetaInferrence::InferTableMeta(void)

- ea: `0x18001ff10`
- end: `0x1800206cb`
- name: `?InferTableMeta@TMetaInferrence@@AEAAXXZ`
- size: `1979`
- prototype: `void __fastcall(TMetaInferrence *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001e000`

## callees

- `0x180017ad8`
- `0x18001ff10`
- `0x1800206d4`
- `0x180020c1c`
- `0x180030010`

## string_xrefs

- `0x1800201e4`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18002052a`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x180020599`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18002061e`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x180020670`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x1800206a6`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x180020577`: `Error - Table (%s) has a PRIMARYKEY column that is also marked as INSERTUNIQUE.  This requires the table to be marked as OVERWRITEALLROWS`

## pseudocode

```c
void __fastcall TMetaInferrence::InferTableMeta(TMetaInferrence *this)
{
  int v1; // r13d
  unsigned int v3; // r12d
  __int64 v4; // rbp
  const unsigned __int16 *v5; // rax
  const unsigned __int16 *v6; // rax
  unsigned int i; // ebx
  unsigned int v8; // ebx
  char v9; // r12
  unsigned int v10; // esi
  int v11; // r15d
  __int64 v12; // rbx
  int v13; // eax
  int v14; // edi
  void (***v15)(_QWORD, const wchar_t *, ...); // rdi
  void (*v16)(_QWORD, const wchar_t *, ...); // rbx
  __int64 v17; // rax
  unsigned int v18; // esi
  int v19; // eax
  __int64 v20; // rdx
  unsigned int v21; // edi
  unsigned int j; // ebx
  __int64 v23; // r15
  unsigned int k; // ebx
  int m; // edx
  unsigned int v26; // ebx
  unsigned int n; // ebx
  int ii; // edx
  unsigned int v29; // ebx
  unsigned int jj; // ebx
  unsigned int *v31; // r15
  bool v32; // zf
  unsigned int v33; // eax
  void (***v34)(_QWORD, const wchar_t *, ...); // rsi
  void (*v35)(_QWORD, const wchar_t *, ...); // rdi
  __int64 v36; // rbx
  __int64 v37; // rax
  void (***v38)(_QWORD, const wchar_t *, ...); // rdi
  void (*v39)(_QWORD, const wchar_t *, ...); // rbx
  __int64 v40; // rax
  void (***v41)(_QWORD, const wchar_t *, ...); // rsi
  void (*v42)(_QWORD, const wchar_t *, ...); // rdi
  __int64 v43; // rbx
  __int64 v44; // rax
  void (***v45)(_QWORD, const wchar_t *, ...); // rdi
  void (*v46)(_QWORD, const wchar_t *, ...); // rbx
  __int64 v47; // rax
  int v48; // [rsp+78h] [rbp+10h]
  int v49; // [rsp+80h] [rbp+18h]

  v1 = 0;
  v3 = 0;
  v48 = 0;
  while ( v3 < (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 320LL))(*((_QWORD *)this + 1)) )
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 232LL))(*((_QWORD *)this + 1), v3);
    if ( !*(_DWORD *)(v4 + 4) )
    {
      (***((void (****)(_QWORD, const wchar_t *, ...))this + 2))(
        *((_QWORD *)this + 2),
        L"Validation Error in TableMeta Row %d. TableMeta.InternalName is a primarykey, so it must not be NULL.",
        v3);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
        L"ERROR - VALIDATION ERROR",
        0x2EAu,
        0);
    }
    v5 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1));
    TMetaInferrence::ValidateStringAsLegalVariableName(this, v5, 0, 0);
    if ( *(_DWORD *)(v4 + 8) )
    {
      v6 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1));
      TMetaInferrence::ValidateStringAsLegalVariableName(this, v6, 0, 0);
    }
    else
    {
      *(_DWORD *)(v4 + 8) = *(_DWORD *)(v4 + 4);
    }
    if ( !*(_DWORD *)(v4 + 16) )
      *(_DWORD *)(v4 + 16) = *((_DWORD *)this + 6);
    if ( !*(_DWORD *)(v4 + 20) )
      *(_DWORD *)(v4 + 20) = *((_DWORD *)this + 6);
    *(_DWORD *)(v4 + 72) = 0;
    for ( i = 0;
          i < (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 264LL))(*((_QWORD *)this + 1))
       && *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 176LL))(
                       *((_QWORD *)this + 1),
                       i) != *(_DWORD *)(v4 + 4);
          i = *(_DWORD *)(v4 + 72) )
    {
      ++*(_DWORD *)(v4 + 72);
    }
    while ( 1 )
    {
      v8 = *(_DWORD *)(v4 + 72) + *(_DWORD *)(v4 + 32);
      if ( v8 >= (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 264LL))(*((_QWORD *)this + 1))
        || *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 176LL))(
                        *((_QWORD *)this + 1),
                        v8) != *(_DWORD *)(v4 + 4) )
      {
        break;
      }
      ++*(_DWORD *)(v4 + 32);
    }
    *(_DWORD *)(v4 + 32) = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 16LL))(
                             *((_QWORD *)this + 1),
                             *(unsigned int *)(v4 + 32));
    TMetaInferrence::InferTableMeta_NameColumn_NavColumn(this, (struct TableMeta *)v4);
    v9 = 0;
    v49 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(
            *((_QWORD *)this + 1),
            *(unsigned int *)(v4 + 36));
    v10 = 0;
    v11 = 0;
    while ( v10 < (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(
                    *((_QWORD *)this + 1),
                    *(unsigned int *)(v4 + 32)) )
    {
      v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 176LL))(
              *((_QWORD *)this + 1),
              v10 + *(_DWORD *)(v4 + 72));
      if ( ((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(
              *((_QWORD *)this + 1),
              *(unsigned int *)(v12 + 24))
          & 0x20001) == 0x20001 )
        v9 = 1;
      v11 |= (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(
               *((_QWORD *)this + 1),
               *(unsigned int *)(v12 + 24));
      v1 |= (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(
              *((_QWORD *)this + 1),
              *(unsigned int *)(v12 + 48));
      if ( (*(char (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(
             *((_QWORD *)this + 1),
             *(unsigned int *)(v12 + 48)) < 0 )
        *(_DWORD *)(v4 + 52) = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 16LL))(
                                 *((_QWORD *)this + 1),
                                 v10);
      ++v10;
    }
    v13 = *(_DWORD *)(v4 + 64);
    v14 = v49;
    if ( (v1 & 0x4000) != 0 )
    {
      v1 = 0;
      if ( !v13 )
      {
        v15 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
        v16 = **v15;
        v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(
                *((_QWORD *)this + 1),
                *(unsigned int *)(v4 + 4));
        v16(
          v15,
          L"Error - Table (%s) has at least one column marked as VALUEINCHILDELEMENT but no ChildElementName is set in the TableMeta",
          v17);
        ThrowException(
          L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
          L"ERROR - VALIDATION ERROR",
          0x353u,
          0);
      }
    }
    else
    {
      v1 = 0;
      if ( v13 )
      {
        v45 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
        v46 = **v45;
        v47 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(
                *((_QWORD *)this + 1),
                *(unsigned int *)(v4 + 4));
        v46(
          v45,
          L"Error - Table (%s) has no column marked as VALUEINCHILDELEMENT but a ChildElementName is set in the TableMeta",
          v47);
        ThrowException(
          L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
          L"ERROR - VALIDATION ERROR",
          0x35Du,
          0);
      }
    }
    if ( v9 && (v49 & 0x20000) == 0 )
    {
      v38 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
      v39 = **v38;
      v40 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(
              *((_QWORD *)this + 1),
              *(unsigned int *)(v4 + 4));
      v39(
        v38,
        L"Error - Table (%s) has a PRIMARYKEY column that is also marked as INSERTUNIQUE.  This requires the table to be m"
         "arked as OVERWRITEALLROWS",
        v40);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
        L"ERROR - VALIDATION ERROR",
        0x367u,
        0);
    }
    if ( (v11 & 0x8000000) != 0 )
      v14 = v49 | 0x10;
    v18 = v14 | 0x200;
    if ( (v11 & 0x10) == 0 )
      v18 = v14;
    v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1), v18);
    v20 = *(unsigned int *)(v4 + 40);
    *(_DWORD *)(v4 + 36) = v19;
    v21 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1) + 152LL))(*((_QWORD *)this + 1), v20);
    for ( j = 0; j < (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 304LL))(*((_QWORD *)this + 1)); ++j )
    {
      v23 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 216LL))(*((_QWORD *)this + 1), j);
      if ( ((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(
              *((_QWORD *)this + 1),
              *(unsigned int *)(v23 + 16))
          & 4) != 0
        && *(_DWORD *)(v23 + 8) == *(_DWORD *)(v4 + 4) )
      {
        v21 |= 4u;
        break;
      }
    }
    *(_DWORD *)(v4 + 40) = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 16LL))(
                             *((_QWORD *)this + 1),
                             v21);
    if ( !*(_DWORD *)(v4 + 52) )
      *(_DWORD *)(v4 + 52) = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1) + 16LL))(
                               *((_QWORD *)this + 1),
                               0xFFFFFFFFLL);
    *(_DWORD *)(v4 + 88) = 0;
    for ( k = 0;
          k < (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 288LL))(*((_QWORD *)this + 1))
       && *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 200LL))(
                       *((_QWORD *)this + 1),
                       k) != *(_DWORD *)(v4 + 4);
          *(_DWORD *)(v4 + 88) = k )
    {
      k = *(_DWORD *)(v4 + 88) + 1;
    }
    if ( *(_DWORD *)(v4 + 88) == (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 288LL))(*((_QWORD *)this + 1)) )
      *(_DWORD *)(v4 + 88) = -1;
    *(_DWORD *)(v4 + 84) = 0;
    for ( m = 0; ; *(_DWORD *)(v4 + 84) = m )
    {
      v26 = m + *(_DWORD *)(v4 + 88);
      if ( v26 >= (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 288LL))(*((_QWORD *)this + 1))
        || *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 200LL))(
                        *((_QWORD *)this + 1),
                        v26) != *(_DWORD *)(v4 + 4) )
      {
        break;
      }
      m = *(_DWORD *)(v4 + 84) + 1;
    }
    *(_DWORD *)(v4 + 100) = 0;
    for ( n = 0;
          n < (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 312LL))(*((_QWORD *)this + 1))
       && *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 224LL))(
                       *((_QWORD *)this + 1),
                       n) != *(_DWORD *)(v4 + 4);
          *(_DWORD *)(v4 + 100) = n )
    {
      n = *(_DWORD *)(v4 + 100) + 1;
    }
    *(_DWORD *)(v4 + 104) = 0;
    for ( ii = 0; ; *(_DWORD *)(v4 + 104) = ii )
    {
      v29 = ii + *(_DWORD *)(v4 + 100);
      if ( v29 >= (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 312LL))(*((_QWORD *)this + 1))
        || *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 224LL))(
                        *((_QWORD *)this + 1),
                        v29) != *(_DWORD *)(v4 + 4) )
      {
        break;
      }
      ii = *(_DWORD *)(v4 + 104) + 1;
    }
    if ( (v18 & 0x200) != 0 )
    {
      for ( jj = 0;
            jj < (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(
                   *((_QWORD *)this + 1),
                   *(unsigned int *)(v4 + 32));
            ++jj )
      {
        v31 = (unsigned int *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 176LL))(
                                *((_QWORD *)this + 1),
                                jj + *(_DWORD *)(v4 + 72));
        if ( ((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(
                *((_QWORD *)this + 1),
                v31[6])
            & 3) == 1 )
        {
          v32 = ((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(
                   *((_QWORD *)this + 1),
                   v31[6])
               & 0x10) == 0;
          v33 = v31[7];
          if ( v32 )
          {
            if ( !v33 )
            {
              v41 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
              v42 = **v41;
              v43 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(
                      *((_QWORD *)this + 1),
                      v31[2]);
              v44 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(
                      *((_QWORD *)this + 1),
                      *(unsigned int *)(v4 + 4));
              v42(
                v41,
                L"Directive Table (%s), has PrimaryKey Column (%s) but no DefaultValue was supplied\r\n",
                v44,
                v43);
              (***((void (__fastcall ****)(_QWORD, const wchar_t *))this + 2))(
                *((_QWORD *)this + 2),
                L"In a Directive Table, all PrimaryKeys that are not ForeignKeys must have a defaultvalue (with one except"
                 "ion - the Directive column itself must NOT have a Default Value)\r\n");
              ThrowException(
                L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
                L"ERROR IN DIRECTIVE COLUMN - NOT DEFAULT VALUE",
                0x3DAu,
                0);
            }
          }
          else if ( v33 )
          {
            v34 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
            v35 = **v34;
            v36 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(
                    *((_QWORD *)this + 1),
                    v31[2]);
            v37 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(
                    *((_QWORD *)this + 1),
                    *(unsigned int *)(v4 + 4));
            v35(v34, L"Directive Table (%s), has Directive Column (%s) with a DefaultValue.\r\n", v37, v36);
            (***((void (__fastcall ****)(_QWORD, const wchar_t *))this + 2))(
              *((_QWORD *)this + 2),
              L"In a Directive Table, all PrimaryKeys that are not ForeignKeys must have a defaultvalue (with one exceptio"
               "n - the Directive column itself must NOT have a Default Value)\r\n");
            ThrowException(
              L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
              L"ERROR IN DIRECTIVE COLUMN - DEFAULT VALUE SUPPLIED FOR DIRECTIVE COLUMN",
              0x3CEu,
              0);
          }
        }
      }
    }
    v3 = ++v48;
  }
}

```

## disassembly

```asm
0x18001ff10  mov     [rsp+arg_18], rbx
0x18001ff15  push    rbp
0x18001ff16  push    rsi
0x18001ff17  push    rdi
0x18001ff18  push    r12
0x18001ff1a  push    r13
0x18001ff1c  push    r14
0x18001ff1e  push    r15
0x18001ff20  sub     rsp, 30h
0x18001ff24  xor     r13d, r13d
0x18001ff27  mov     r14, rcx
0x18001ff2a  mov     r12d, r13d
0x18001ff2d  mov     [rsp+68h+arg_8], r13d
0x18001ff32  lea     edi, [r13+1]
0x18001ff36  mov     rcx, [r14+8]
0x18001ff3a  mov     rax, [rcx]
0x18001ff3d  mov     rax, [rax+140h]
0x18001ff44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff49  cmp     r12d, eax
0x18001ff4c  jnb     loc_1800206B3
0x18001ff52  mov     rcx, [r14+8]
0x18001ff56  mov     edx, r12d
0x18001ff59  mov     rax, [rcx]
0x18001ff5c  mov     rax, [rax+0E8h]
0x18001ff63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff68  mov     rbp, rax
0x18001ff6b  mov     edx, [rax+4]
0x18001ff6e  test    edx, edx
0x18001ff70  jz      loc_18002067D
0x18001ff76  mov     rcx, [r14+8]
0x18001ff7a  mov     r8, [rcx]
0x18001ff7d  mov     rax, [r8+90h]
0x18001ff84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff89  mov     rdx, rax; unsigned __int16 *
0x18001ff8c  xor     r9d, r9d; bool
0x18001ff8f  xor     r8d, r8d; unsigned __int16 *
0x18001ff92  mov     rcx, r14; this
0x18001ff95  call    ?ValidateStringAsLegalVariableName@TMetaInferrence@@AEAAXPEBG0_N@Z; TMetaInferrence::ValidateStringAsLegalVariableName(ushort const *,ushort const *,bool)
0x18001ff9a  mov     edx, [rbp+8]
0x18001ff9d  test    edx, edx
0x18001ff9f  jnz     short loc_18001FFA9
0x18001ffa1  mov     eax, [rbp+4]
0x18001ffa4  mov     [rbp+8], eax
0x18001ffa7  jmp     short loc_18001FFCD
0x18001ffa9  mov     rcx, [r14+8]
0x18001ffad  mov     rax, [rcx]
0x18001ffb0  mov     rax, [rax+90h]
0x18001ffb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffbc  mov     rdx, rax; unsigned __int16 *
0x18001ffbf  xor     r9d, r9d; bool
0x18001ffc2  xor     r8d, r8d; unsigned __int16 *
0x18001ffc5  mov     rcx, r14; this
0x18001ffc8  call    ?ValidateStringAsLegalVariableName@TMetaInferrence@@AEAAXPEBG0_N@Z; TMetaInferrence::ValidateStringAsLegalVariableName(ushort const *,ushort const *,bool)
0x18001ffcd  cmp     [rbp+10h], r13d
0x18001ffd1  jnz     short loc_18001FFDA
0x18001ffd3  mov     eax, [r14+18h]
0x18001ffd7  mov     [rbp+10h], eax
0x18001ffda  cmp     [rbp+14h], r13d
0x18001ffde  jnz     short loc_18001FFE7
0x18001ffe0  mov     eax, [r14+18h]
0x18001ffe4  mov     [rbp+14h], eax
0x18001ffe7  mov     [rbp+48h], r13d
0x18001ffeb  mov     ebx, r13d
0x18001ffee  mov     rcx, [r14+8]
0x18001fff2  mov     rax, [rcx]
0x18001fff5  mov     rax, [rax+108h]
0x18001fffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020001  cmp     ebx, eax
0x180020003  jnb     short loc_180020029
0x180020005  mov     rcx, [r14+8]
0x180020009  mov     edx, ebx
0x18002000b  mov     rax, [rcx]
0x18002000e  mov     rax, [rax+0B0h]
0x180020015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002001a  mov     ecx, [rbp+4]
0x18002001d  cmp     [rax], ecx
0x18002001f  jz      short loc_180020029
0x180020021  add     [rbp+48h], edi
0x180020024  mov     ebx, [rbp+48h]
0x180020027  jmp     short loc_18001FFEE
0x180020029  mov     rcx, [r14+8]
0x18002002d  mov     ebx, [rbp+20h]
0x180020030  add     ebx, [rbp+48h]
0x180020033  mov     rax, [rcx]
0x180020036  mov     rax, [rax+108h]
0x18002003d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020042  cmp     ebx, eax
0x180020044  jnb     short loc_180020067
0x180020046  mov     rcx, [r14+8]
0x18002004a  mov     edx, ebx
0x18002004c  mov     rax, [rcx]
0x18002004f  mov     rax, [rax+0B0h]
0x180020056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002005b  mov     ecx, [rbp+4]
0x18002005e  cmp     [rax], ecx
0x180020060  jnz     short loc_180020067
0x180020062  add     [rbp+20h], edi
0x180020065  jmp     short loc_180020029
0x180020067  mov     rcx, [r14+8]
0x18002006b  mov     edx, [rbp+20h]
0x18002006e  mov     rax, [rcx]
0x180020071  mov     rax, [rax+10h]
0x180020075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002007a  mov     rdx, rbp; struct TableMeta *
0x18002007d  mov     [rbp+20h], eax
0x180020080  mov     rcx, r14; this
0x180020083  call    ?InferTableMeta_NameColumn_NavColumn@TMetaInferrence@@AEAAXPEAUTableMeta@@@Z; TMetaInferrence::InferTableMeta_NameColumn_NavColumn(TableMeta *)
0x180020088  mov     rcx, [r14+8]
0x18002008c  mov     edx, [rbp+24h]
0x18002008f  mov     rax, [rcx]
0x180020092  mov     rax, [rax+98h]
0x180020099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002009e  xor     r12b, r12b
0x1800200a1  mov     [rsp+68h+arg_10], eax
0x1800200a8  xor     esi, esi
0x1800200aa  mov     [rsp+68h+arg_0], r12d
0x1800200af  mov     r15d, r13d
0x1800200b2  lea     edi, [rsi+1]
0x1800200b5  mov     rcx, [r14+8]
0x1800200b9  mov     rdx, [rcx]
0x1800200bc  mov     rax, [rdx+98h]
0x1800200c3  mov     edx, [rbp+20h]
0x1800200c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200cb  cmp     esi, eax
0x1800200cd  jnb     loc_18002017D
0x1800200d3  mov     rcx, [r14+8]
0x1800200d7  mov     edx, [rbp+48h]
0x1800200da  add     edx, esi
0x1800200dc  mov     r8, [rcx]
0x1800200df  mov     rax, [r8+0B0h]
0x1800200e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200eb  mov     rcx, [r14+8]
0x1800200ef  mov     rbx, rax
0x1800200f2  mov     rdx, [rcx]
0x1800200f5  mov     rax, [rdx+98h]
0x1800200fc  mov     edx, [rbx+18h]
0x1800200ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020104  mov     edx, [rbx+18h]
0x180020107  mov     ecx, 20001h
0x18002010c  and     eax, ecx
0x18002010e  movzx   r12d, r12b
0x180020112  cmp     eax, ecx
0x180020114  mov     rcx, [r14+8]
0x180020118  cmovz   r12d, edi
0x18002011c  mov     rax, [rcx]
0x18002011f  mov     rax, [rax+98h]
0x180020126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002012b  mov     rcx, [r14+8]
0x18002012f  or      r15d, eax
0x180020132  mov     edx, [rbx+30h]
0x180020135  mov     rax, [rcx]
0x180020138  mov     rax, [rax+98h]
0x18002013f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020144  mov     rcx, [r14+8]
0x180020148  or      r13d, eax
0x18002014b  mov     edx, [rbx+30h]
0x18002014e  mov     rax, [rcx]
0x180020151  mov     rax, [rax+98h]
0x180020158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002015d  test    al, al
0x18002015f  jns     short loc_180020176
0x180020161  mov     rcx, [r14+8]
0x180020165  mov     edx, esi
0x180020167  mov     rax, [rcx]
0x18002016a  mov     rax, [rax+10h]
0x18002016e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020173  mov     [rbp+34h], eax
0x180020176  add     esi, edi
0x180020178  jmp     loc_1800200B5
0x18002017d  mov     eax, [rbp+40h]
0x180020180  mov     edi, [rsp+68h+arg_10]
0x180020187  mov     [rsp+68h+arg_0], r12d
0x18002018c  mov     r12d, [rsp+68h+arg_8]
0x180020191  bt      r13d, 0Eh
0x180020196  jnb     short loc_1800201F1
0x180020198  xor     r13d, r13d
0x18002019b  test    eax, eax
0x18002019d  jnz     short loc_1800201FC
0x18002019f  mov     rdi, [r14+10h]
0x1800201a3  mov     rcx, [r14+8]
0x1800201a7  mov     rax, [rdi]
0x1800201aa  mov     rdx, [rcx]
0x1800201ad  mov     rbx, [rax]
0x1800201b0  mov     rax, [rdx+90h]
0x1800201b7  mov     edx, [rbp+4]
0x1800201ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201bf  mov     r8, rax
0x1800201c2  lea     rdx, aErrorTableSHas_2; "Error - Table (%s) has at least one col"...
0x1800201c9  mov     rax, rbx
0x1800201cc  mov     rcx, rdi
0x1800201cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201d4  xor     r9d, r9d; unsigned int
0x1800201d7  lea     rdx, aErrorValidatio; "ERROR - VALIDATION ERROR"
0x1800201de  mov     r8d, 353h; unsigned int
0x1800201e4  lea     rcx, aInetsrvIisMbCo_13; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x1800201eb  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x1800201f1  xor     r13d, r13d
0x1800201f4  test    eax, eax
0x1800201f6  jnz     loc_18002062B
0x1800201fc  cmp     byte ptr [rsp+68h+arg_0], r13b
0x180020201  jz      short loc_18002020D
0x180020203  bt      edi, 11h
0x180020207  jnb     loc_180020554
0x18002020d  bt      r15d, 1Bh
0x180020212  jnb     short loc_180020217
0x180020214  or      edi, 10h
0x180020217  mov     rcx, [r14+8]
0x18002021b  mov     esi, edi
0x18002021d  bts     esi, 9
0x180020221  test    r15b, 10h
0x180020225  mov     rax, [rcx]
0x180020228  cmovz   esi, edi
0x18002022b  mov     edx, esi
0x18002022d  mov     rax, [rax+10h]
0x180020231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020236  mov     edx, [rbp+28h]
0x180020239  mov     [rbp+24h], eax
0x18002023c  mov     rcx, [r14+8]
0x180020240  mov     rax, [rcx]
0x180020243  mov     rax, [rax+98h]
0x18002024a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002024f  mov     edi, eax
0x180020251  mov     ebx, r13d
0x180020254  mov     rcx, [r14+8]
0x180020258  mov     rdx, [rcx]
0x18002025b  mov     rax, [rdx+130h]
0x180020262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020267  cmp     ebx, eax
0x180020269  jnb     short loc_1800202AE
0x18002026b  mov     rcx, [r14+8]
0x18002026f  mov     edx, ebx
0x180020271  mov     rax, [rcx]
0x180020274  mov     rax, [rax+0D8h]
0x18002027b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020280  mov     rcx, [r14+8]
0x180020284  mov     r15, rax
0x180020287  mov     rdx, [rcx]
0x18002028a  mov     rax, [rdx+98h]
0x180020291  mov     edx, [r15+10h]
0x180020295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002029a  test    al, 4
0x18002029c  jz      short loc_1800202A7
0x18002029e  mov     ecx, [rbp+4]
0x1800202a1  cmp     [r15+8], ecx
0x1800202a5  jz      short loc_1800202AB
0x1800202a7  inc     ebx
0x1800202a9  jmp     short loc_180020254
0x1800202ab  or      edi, 4
0x1800202ae  mov     rcx, [r14+8]
0x1800202b2  mov     edx, edi
0x1800202b4  mov     rax, [rcx]
0x1800202b7  mov     rax, [rax+10h]
0x1800202bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202c0  mov     [rbp+28h], eax
0x1800202c3  cmp     [rbp+34h], r13d
0x1800202c7  jnz     short loc_1800202DF
0x1800202c9  mov     rcx, [r14+8]
0x1800202cd  or      edx, 0FFFFFFFFh
0x1800202d0  mov     rax, [rcx]
0x1800202d3  mov     rax, [rax+10h]
0x1800202d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202dc  mov     [rbp+34h], eax
0x1800202df  mov     [rbp+58h], r13d
0x1800202e3  mov     ebx, r13d
0x1800202e6  mov     rcx, [r14+8]
0x1800202ea  mov     rax, [rcx]
0x1800202ed  mov     rax, [rax+120h]
0x1800202f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202f9  cmp     ebx, eax
0x1800202fb  jnb     short loc_180020323
0x1800202fd  mov     rcx, [r14+8]
0x180020301  mov     edx, ebx
0x180020303  mov     rax, [rcx]
0x180020306  mov     rax, [rax+0C8h]
0x18002030d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020312  mov     ecx, [rbp+4]
0x180020315  cmp     [rax], ecx
0x180020317  jz      short loc_180020323
0x180020319  mov     ebx, [rbp+58h]
0x18002031c  inc     ebx
0x18002031e  mov     [rbp+58h], ebx
0x180020321  jmp     short loc_1800202E6
0x180020323  mov     rcx, [r14+8]
0x180020327  mov     rax, [rcx]
0x18002032a  mov     rax, [rax+120h]
0x180020331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020336  cmp     [rbp+58h], eax
0x180020339  jnz     short loc_180020342
0x18002033b  mov     dword ptr [rbp+58h], 0FFFFFFFFh
0x180020342  mov     [rbp+54h], r13d
0x180020346  mov     edx, r13d
0x180020349  mov     rcx, [r14+8]
0x18002034d  mov     ebx, [rbp+58h]
0x180020350  add     ebx, edx
0x180020352  mov     rax, [rcx]
0x180020355  mov     rax, [rax+120h]
0x18002035c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020361  cmp     ebx, eax
0x180020363  jnb     short loc_18002038B
0x180020365  mov     rcx, [r14+8]
  ... truncated ...
```
