# TMetaInferrence::InferTableMeta_NameColumn_NavColumn(TableMeta *)

- ea: `0x1800206d4`
- end: `0x180020a60`
- name: `?InferTableMeta_NameColumn_NavColumn@TMetaInferrence@@AEAAXPEAUTableMeta@@@Z`
- size: `908`
- prototype: `void __fastcall(TMetaInferrence *__hidden this, struct TableMeta *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001ff10`

## callees

- `0x180017ad8`
- `0x1800206d4`
- `0x180030010`

## string_xrefs

- `0x18002092f`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18002099e`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`

## pseudocode

```c
void __fastcall TMetaInferrence::InferTableMeta_NameColumn_NavColumn(TMetaInferrence *this, struct TableMeta *a2)
{
  unsigned int v3; // ebx
  int v4; // r14d
  int v5; // r15d
  int v6; // r12d
  int v7; // r13d
  unsigned int v8; // esi
  unsigned int i; // edi
  unsigned int *v10; // r14
  int v11; // eax
  void (***v12)(_QWORD, const wchar_t *, ...); // rsi
  void (*v13)(_QWORD, const wchar_t *, ...); // rdi
  __int64 v14; // rbx
  __int64 v15; // rax
  void (***v16)(_QWORD, const wchar_t *, ...); // rsi
  void (*v17)(_QWORD, const wchar_t *, ...); // rdi
  __int64 v18; // rbx
  __int64 v19; // rax
  void (***v20)(_QWORD, const wchar_t *, ...); // rdi
  void (*v21)(_QWORD, const wchar_t *, ...); // rbx
  __int64 v22; // rax
  int v23; // [rsp+70h] [rbp+8h]
  struct TableMeta *v24; // [rsp+78h] [rbp+10h]

  v24 = a2;
  v3 = -1;
  v23 = -1;
  v4 = -1;
  v5 = -1;
  v6 = -1;
  v7 = -1;
  v8 = -1;
  for ( i = 0;
        i < (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(
              *((_QWORD *)this + 1),
              *((unsigned int *)a2 + 8));
        ++i )
  {
    v10 = (unsigned int *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 176LL))(
                            *((_QWORD *)this + 1),
                            i + *((_DWORD *)v24 + 18));
    if ( ((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(*((_QWORD *)this + 1), v10[6])
        & 4) != 0 )
    {
      if ( v8 != -1 )
      {
        v12 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
        v13 = **v12;
        v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(
                *((_QWORD *)this + 1),
                v10[2]);
        v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), *v10);
        v13(
          v12,
          L"Error - Multiple NameColumns specified (Table %s, Column %s).\n"
           "\tOnly one Column should have the fCOLUMNMETA_NAMECOLUMN set.\n",
          v15,
          v14);
        ThrowException(
          L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
          L"ERROR - MULTIPLE NAME COLUMNS SPECIFIED",
          0x43Du,
          0);
      }
      v8 = i;
    }
    if ( ((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(*((_QWORD *)this + 1), v10[6])
        & 8) != 0 )
    {
      if ( v7 != -1 )
      {
        v16 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
        v17 = **v16;
        v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(
                *((_QWORD *)this + 1),
                v10[2]);
        v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), *v10);
        v17(
          v16,
          L"Error - Multiple NavColumns specified (Table %s, Column %s).\n"
           "\tOnly one Column should have the fCOLUMNMETA_NAVCOLUMN set.\n",
          v19,
          v18);
        ThrowException(
          L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
          L"ERROR - MULTIPLE NAV COLUMNS SPECIFIED",
          0x448u,
          0);
      }
      v7 = i;
    }
    if ( v3 == -1
      && ((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(*((_QWORD *)this + 1), v10[6])
        & 1) != 0
      && ((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(*((_QWORD *)this + 1), v10[6])
        & 2) == 0 )
    {
      v3 = i;
    }
    if ( v6 == -1
      && (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(
           *((_QWORD *)this + 1),
           v10[4]) == 130 )
    {
      v6 = i;
    }
    if ( v5 == -1
      && ((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(*((_QWORD *)this + 1), v10[6])
        & 1) != 0
      && ((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(*((_QWORD *)this + 1), v10[6])
        & 2) == 0
      && (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(
           *((_QWORD *)this + 1),
           v10[4]) == 130 )
    {
      v5 = i;
    }
    if ( v23 == -1
      && ((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(*((_QWORD *)this + 1), v10[6])
        & 1) != 0
      && ((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(*((_QWORD *)this + 1), v10[6])
        & 2) != 0 )
    {
      v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(*((_QWORD *)this + 1), v10[4]);
      v4 = -1;
      if ( v11 == 130 )
        v4 = i;
      v23 = v4;
    }
    else
    {
      v4 = v23;
    }
    a2 = v24;
  }
  if ( v3 == -1 )
  {
    v20 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
    v21 = **v20;
    v22 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(
            *((_QWORD *)this + 1),
            *((unsigned int *)v24 + 1));
    v21(v20, L"Warning - Table (%s) contains no PRIMARYKEY that is not also a FOREIGNKEY.\n", v22);
    v3 = v4;
    if ( v4 == -1 )
      v3 = 0;
  }
  if ( v7 != -1 )
    v3 = v7;
  if ( v8 == -1 )
  {
    if ( v5 == -1 )
    {
      v8 = v3;
      if ( v6 != -1 )
        v8 = v6;
    }
    else
    {
      v8 = v5;
    }
  }
  *((_DWORD *)v24 + 6) = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 16LL))(
                           *((_QWORD *)this + 1),
                           v8);
  *((_DWORD *)v24 + 7) = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 16LL))(
                           *((_QWORD *)this + 1),
                           v3);
}

```

## disassembly

```asm
0x1800206d4  mov     [rsp+arg_10], rbx
0x1800206d9  mov     [rsp+arg_8], rdx
0x1800206de  push    rbp
0x1800206df  push    rsi
0x1800206e0  push    rdi
0x1800206e1  push    r12
0x1800206e3  push    r13
0x1800206e5  push    r14
0x1800206e7  push    r15
0x1800206e9  sub     rsp, 30h
0x1800206ed  or      eax, 0FFFFFFFFh
0x1800206f0  mov     rbp, rcx
0x1800206f3  mov     ebx, eax
0x1800206f5  mov     [rsp+68h+arg_0], eax
0x1800206f9  mov     r14d, eax
0x1800206fc  mov     r15d, eax
0x1800206ff  mov     r12d, eax
0x180020702  mov     r13d, eax
0x180020705  mov     esi, eax
0x180020707  xor     edi, edi
0x180020709  mov     rcx, [rbp+8]
0x18002070d  mov     edx, [rdx+20h]
0x180020710  mov     rax, [rcx]
0x180020713  mov     rax, [rax+98h]
0x18002071a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002071f  cmp     edi, eax
0x180020721  jnb     loc_1800209AB
0x180020727  mov     rcx, [rbp+8]
0x18002072b  mov     rdx, [rsp+68h+arg_8]
0x180020730  mov     r8, [rcx]
0x180020733  mov     edx, [rdx+48h]
0x180020736  add     edx, edi
0x180020738  mov     rax, [r8+0B0h]
0x18002073f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020744  mov     rcx, [rbp+8]
0x180020748  mov     r14, rax
0x18002074b  mov     rdx, [rcx]
0x18002074e  mov     rax, [rdx+98h]
0x180020755  mov     edx, [r14+18h]
0x180020759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002075e  test    al, 4
0x180020760  jz      short loc_18002076D
0x180020762  cmp     esi, 0FFFFFFFFh
0x180020765  jnz     loc_1800208CD
0x18002076b  mov     esi, edi
0x18002076d  mov     rcx, [rbp+8]
0x180020771  mov     edx, [r14+18h]
0x180020775  mov     rax, [rcx]
0x180020778  mov     rax, [rax+98h]
0x18002077f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020784  test    al, 8
0x180020786  jz      short loc_180020795
0x180020788  cmp     r13d, 0FFFFFFFFh
0x18002078c  jnz     loc_18002093C
0x180020792  mov     r13d, edi
0x180020795  cmp     ebx, 0FFFFFFFFh
0x180020798  jnz     short loc_1800207D1
0x18002079a  mov     rcx, [rbp+8]
0x18002079e  mov     edx, [r14+18h]
0x1800207a2  mov     rax, [rcx]
0x1800207a5  mov     rax, [rax+98h]
0x1800207ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207b1  test    al, 1
0x1800207b3  jz      short loc_1800207D1
0x1800207b5  mov     rcx, [rbp+8]
0x1800207b9  mov     edx, [r14+18h]
0x1800207bd  mov     rax, [rcx]
0x1800207c0  mov     rax, [rax+98h]
0x1800207c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207cc  test    al, 2
0x1800207ce  cmovz   ebx, edi
0x1800207d1  cmp     r12d, 0FFFFFFFFh
0x1800207d5  jnz     short loc_1800207F7
0x1800207d7  mov     rcx, [rbp+8]
0x1800207db  mov     edx, [r14+10h]
0x1800207df  mov     rax, [rcx]
0x1800207e2  mov     rax, [rax+98h]
0x1800207e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207ee  cmp     eax, 82h
0x1800207f3  cmovz   r12d, edi
0x1800207f7  cmp     r15d, 0FFFFFFFFh
0x1800207fb  jnz     short loc_180020853
0x1800207fd  mov     rcx, [rbp+8]
0x180020801  mov     edx, [r14+18h]
0x180020805  mov     rax, [rcx]
0x180020808  mov     rax, [rax+98h]
0x18002080f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020814  test    al, 1
0x180020816  jz      short loc_180020853
0x180020818  mov     rcx, [rbp+8]
0x18002081c  mov     edx, [r14+18h]
0x180020820  mov     rax, [rcx]
0x180020823  mov     rax, [rax+98h]
0x18002082a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002082f  test    al, 2
0x180020831  jnz     short loc_180020853
0x180020833  mov     rcx, [rbp+8]
0x180020837  mov     edx, [r14+10h]
0x18002083b  mov     rax, [rcx]
0x18002083e  mov     rax, [rax+98h]
0x180020845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002084a  cmp     eax, 82h
0x18002084f  cmovz   r15d, edi
0x180020853  cmp     [rsp+68h+arg_0], 0FFFFFFFFh
0x180020858  jnz     short loc_1800208BC
0x18002085a  mov     rcx, [rbp+8]
0x18002085e  mov     edx, [r14+18h]
0x180020862  mov     rax, [rcx]
0x180020865  mov     rax, [rax+98h]
0x18002086c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020871  test    al, 1
0x180020873  jz      short loc_1800208BC
0x180020875  mov     rcx, [rbp+8]
0x180020879  mov     edx, [r14+18h]
0x18002087d  mov     rax, [rcx]
0x180020880  mov     rax, [rax+98h]
0x180020887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002088c  test    al, 2
0x18002088e  jz      short loc_1800208BC
0x180020890  mov     rcx, [rbp+8]
0x180020894  mov     edx, [r14+10h]
0x180020898  mov     rax, [rcx]
0x18002089b  mov     rax, [rax+98h]
0x1800208a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208a7  mov     r14d, [rsp+68h+arg_0]
0x1800208ac  cmp     eax, 82h
0x1800208b1  cmovz   r14d, edi
0x1800208b5  mov     [rsp+68h+arg_0], r14d
0x1800208ba  jmp     short loc_1800208C1
0x1800208bc  mov     r14d, [rsp+68h+arg_0]
0x1800208c1  mov     rdx, [rsp+68h+arg_8]
0x1800208c6  inc     edi
0x1800208c8  jmp     loc_180020709
0x1800208cd  mov     rsi, [rbp+10h]
0x1800208d1  mov     rcx, [rbp+8]
0x1800208d5  mov     edx, [r14+8]
0x1800208d9  mov     rax, [rsi]
0x1800208dc  mov     rdi, [rax]
0x1800208df  mov     rax, [rcx]
0x1800208e2  mov     rax, [rax+90h]
0x1800208e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208ee  mov     rcx, [rbp+8]
0x1800208f2  mov     rbx, rax
0x1800208f5  mov     rdx, [rcx]
0x1800208f8  mov     rax, [rdx+90h]
0x1800208ff  mov     edx, [r14]
0x180020902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020907  mov     r8, rax
0x18002090a  lea     rdx, aErrorMultipleN_2; "Error - Multiple NameColumns specified "...
0x180020911  mov     rax, rdi
0x180020914  mov     r9, rbx
0x180020917  mov     rcx, rsi
0x18002091a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002091f  xor     r9d, r9d; unsigned int
0x180020922  lea     rdx, aErrorMultipleN; "ERROR - MULTIPLE NAME COLUMNS SPECIFIED"
0x180020929  mov     r8d, 43Dh; unsigned int
0x18002092f  lea     rcx, aInetsrvIisMbCo_13; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180020936  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18002093c  mov     rsi, [rbp+10h]
0x180020940  mov     rcx, [rbp+8]
0x180020944  mov     edx, [r14+8]
0x180020948  mov     rax, [rsi]
0x18002094b  mov     rdi, [rax]
0x18002094e  mov     rax, [rcx]
0x180020951  mov     rax, [rax+90h]
0x180020958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002095d  mov     rcx, [rbp+8]
0x180020961  mov     rbx, rax
0x180020964  mov     rdx, [rcx]
0x180020967  mov     rax, [rdx+90h]
0x18002096e  mov     edx, [r14]
0x180020971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020976  mov     r8, rax
0x180020979  lea     rdx, aErrorMultipleN_1; "Error - Multiple NavColumns specified ("...
0x180020980  mov     rax, rdi
0x180020983  mov     r9, rbx
0x180020986  mov     rcx, rsi
0x180020989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002098e  xor     r9d, r9d; unsigned int
0x180020991  lea     rdx, aErrorMultipleN_0; "ERROR - MULTIPLE NAV COLUMNS SPECIFIED"
0x180020998  mov     r8d, 448h; unsigned int
0x18002099e  lea     rcx, aInetsrvIisMbCo_13; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x1800209a5  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x1800209ab  or      eax, 0FFFFFFFFh
0x1800209ae  cmp     ebx, eax
0x1800209b0  jnz     short loc_1800209FB
0x1800209b2  mov     rdi, [rbp+10h]
0x1800209b6  mov     rcx, [rbp+8]
0x1800209ba  mov     rax, [rdi]
0x1800209bd  mov     rdx, [rcx]
0x1800209c0  mov     rbx, [rax]
0x1800209c3  mov     rax, [rdx+90h]
0x1800209ca  mov     rdx, [rsp+68h+arg_8]
0x1800209cf  mov     edx, [rdx+4]
0x1800209d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209d7  mov     r8, rax
0x1800209da  lea     rdx, aWarningTableSC; "Warning - Table (%s) contains no PRIMAR"...
0x1800209e1  mov     rax, rbx
0x1800209e4  mov     rcx, rdi
0x1800209e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209ec  xor     eax, eax
0x1800209ee  mov     ebx, r14d
0x1800209f1  cmp     r14d, 0FFFFFFFFh
0x1800209f5  cmovz   ebx, eax
0x1800209f8  or      eax, 0FFFFFFFFh
0x1800209fb  cmp     r13d, eax
0x1800209fe  cmovnz  ebx, r13d
0x180020a02  cmp     esi, eax
0x180020a04  jnz     short loc_180020A19
0x180020a06  cmp     r15d, eax
0x180020a09  jz      short loc_180020A10
0x180020a0b  mov     esi, r15d
0x180020a0e  jmp     short loc_180020A19
0x180020a10  cmp     r12d, eax
0x180020a13  mov     esi, ebx
0x180020a15  cmovnz  esi, r12d
0x180020a19  mov     rcx, [rbp+8]
0x180020a1d  mov     edx, esi
0x180020a1f  mov     rax, [rcx]
0x180020a22  mov     rax, [rax+10h]
0x180020a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a2b  mov     rdi, [rsp+68h+arg_8]
0x180020a30  mov     edx, ebx
0x180020a32  mov     [rdi+18h], eax
0x180020a35  mov     rcx, [rbp+8]
0x180020a39  mov     rax, [rcx]
0x180020a3c  mov     rax, [rax+10h]
0x180020a40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a45  mov     rbx, [rsp+68h+arg_10]
0x180020a4d  mov     [rdi+1Ch], eax
0x180020a50  add     rsp, 30h
0x180020a54  pop     r15
0x180020a56  pop     r14
0x180020a58  pop     r13
0x180020a5a  pop     r12
0x180020a5c  pop     rdi
0x180020a5d  pop     rsi
0x180020a5e  pop     rbp
0x180020a5f  retn
```
