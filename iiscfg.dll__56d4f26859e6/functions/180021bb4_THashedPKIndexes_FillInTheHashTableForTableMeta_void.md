# THashedPKIndexes::FillInTheHashTableForTableMeta(void)

- ea: `0x180021bb4`
- end: `0x180021dcd`
- name: `?FillInTheHashTableForTableMeta@THashedPKIndexes@@AEAAXXZ`
- size: `537`
- prototype: `void __fastcall(THashedPKIndexes *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180020e10`

## callees

- `0x180014168`
- `0x180017ad8`
- `0x180020e78`
- `0x180021bb4`
- `0x1800223a8`
- `0x180022600`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180021dad`
- `ole32!CoTaskMemFree` at `0x180021dad`
- `ole32!CoTaskMemAlloc` at `0x180021c62`
- `ole32!CoTaskMemAlloc` at `0x180021c62`

## string_xrefs

- `0x180021c50`: `inetsrv\iis\mb\config\src\core\schemagen\thashedpkindexes.cpp`
- `0x180021c9e`: `inetsrv\iis\mb\config\src\core\schemagen\thashedpkindexes.cpp`

## pseudocode

```c
void __fastcall THashedPKIndexes::FillInTheHashTableForTableMeta(THashedPKIndexes *this)
{
  unsigned int v2; // r14d
  unsigned int *v3; // rax
  unsigned int *v4; // rdi
  __int64 v5; // rsi
  const unsigned __int16 *InternalName; // rax
  unsigned int v7; // eax
  bool v8; // zf
  unsigned int v9; // eax
  unsigned int v10; // r15d
  unsigned int v11; // esi
  unsigned int v12; // eax
  void **v13; // [rsp+48h] [rbp-50h] BYREF
  __int64 v14; // [rsp+50h] [rbp-48h]
  __int64 v15; // [rsp+58h] [rbp-40h]
  unsigned int v16; // [rsp+A0h] [rbp+8h] BYREF
  unsigned int *v17; // [rsp+A8h] [rbp+10h]

  v14 = *((_QWORD *)this + 4);
  v15 = 0;
  v13 = &TTableMeta::`vftable';
  v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 320LL))(v14);
  v16 = 1;
  (***((void (__fastcall ****)(_QWORD, const wchar_t *))this + 5))(
    *((_QWORD *)this + 5),
    L"\nBuilding TableMeta hash table");
  if ( v2 > 0x2000 )
  {
    (***((void (__fastcall ****)(_QWORD, const wchar_t *, _QWORD))this + 5))(
      *((_QWORD *)this + 5),
      L"Error! Too Many Rows - TableMeta has %d rows, Hash table generation relies on fixed tables being less than %d rows\n",
      v2);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\thashedpkindexes.cpp",
      L"TOO MANY ROWS - HASH TABLE GENERATION ASSUMES FIXED TABLES ARE RELATIVELY SMALL",
      0x1B2u,
      0);
  }
  v3 = (unsigned int *)CoTaskMemAlloc(0x8000u);
  v4 = v3;
  v17 = v3;
  if ( !v3 )
  {
    (***((void (__fastcall ****)(_QWORD, const wchar_t *))this + 5))(
      *((_QWORD *)this + 5),
      L"Error! Out of memory in THashedPKIndexes::FillInTheHashTableForTableMeta");
    ThrowException(L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\thashedpkindexes.cpp", L"OUT OF MEMORY", 0x1B9u, 0);
  }
  *v3 = -1;
  v5 = 0;
  while ( (unsigned int)v5 < v2 )
  {
    InternalName = TTableMeta::Get_InternalName((TTableMeta *)&v13);
    v4[v5] = Hash(InternalName, 0);
    v5 = (unsigned int)(v5 + 1);
    TMetaTable<QueryMetaPublic>::Next(&v13);
  }
  v7 = v2
     | (v2 >> 1)
     | ((v2 | (v2 >> 1)) >> 2)
     | ((v2 | (v2 >> 1) | ((v2 | (v2 >> 1)) >> 2)) >> 4)
     | ((v2 | (v2 >> 1) | ((v2 | (v2 >> 1)) >> 2) | ((v2 | (v2 >> 1) | ((v2 | (v2 >> 1)) >> 2)) >> 4)) >> 8)
     | ((v2
       | (v2 >> 1)
       | ((v2 | (v2 >> 1)) >> 2)
       | ((v2 | (v2 >> 1) | ((v2 | (v2 >> 1)) >> 2)) >> 4)
       | ((v2 | (v2 >> 1) | ((v2 | (v2 >> 1)) >> 2) | ((v2 | (v2 >> 1) | ((v2 | (v2 >> 1)) >> 2)) >> 4)) >> 8)) >> 16);
  v8 = v7 == -1;
  v9 = v7 + 1;
  v10 = 0x80000000;
  if ( !v8 )
    v10 = v9;
  v11 = THashedPKIndexes::FillInTheHashTable(this, v2, 1u, (unsigned int (*const)[8192])v4, v10, &v16);
  v12 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *))(**((_QWORD **)this + 4) + 352LL))(
          *((_QWORD *)this + 4),
          L"TABLEMETA");
  *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 4) + 232LL))(*((_QWORD *)this + 4), v12)
            + 92) = v11;
  (***((void (__fastcall ****)(_QWORD, const wchar_t *, _QWORD))this + 5))(
    *((_QWORD *)this + 5),
    L"\nTableMeta has %d rows, the hash table has %d elements, %d modulo, %d max chain and %d nonunique entries.\n",
    v2);
  CoTaskMemFree(v4);
}

```

## disassembly

```asm
0x180021bb4  mov     r11, rsp
0x180021bb7  mov     [r11+18h], rbx
0x180021bbb  mov     [r11+20h], rsi
0x180021bbf  push    rdi
0x180021bc0  push    r14
0x180021bc2  push    r15
0x180021bc4  sub     rsp, 80h
0x180021bcb  mov     rbx, rcx
0x180021bce  mov     rcx, [rcx+20h]
0x180021bd2  mov     [r11-48h], rcx
0x180021bd6  mov     qword ptr [r11-40h], 0
0x180021bde  lea     rax, ??_7TTableMeta@@6B@; const TTableMeta::`vftable'
0x180021be5  mov     [r11-50h], rax
0x180021be9  mov     rax, [rcx]
0x180021bec  mov     rax, [rax+140h]
0x180021bf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021bf8  mov     r14d, eax
0x180021bfb  mov     [rsp+98h+arg_0], 1
0x180021c06  mov     rcx, [rbx+28h]
0x180021c0a  mov     rdx, [rcx]
0x180021c0d  mov     rax, [rdx]
0x180021c10  lea     rdx, aBuildingTablem; "\nBuilding TableMeta hash table"
0x180021c17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c1c  mov     r9d, 2000h
0x180021c22  cmp     r14d, r9d
0x180021c25  jbe     short loc_180021C5D
0x180021c27  mov     rcx, [rbx+28h]
0x180021c2b  mov     rax, [rcx]
0x180021c2e  mov     r8d, r14d
0x180021c31  lea     rdx, aErrorTooManyRo_3; "Error! Too Many Rows - TableMeta has %d"...
0x180021c38  mov     rax, [rax]
0x180021c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c40  xor     r9d, r9d; unsigned int
0x180021c43  mov     r8d, 1B2h; unsigned int
0x180021c49  lea     rdx, aTooManyRowsHas; "TOO MANY ROWS - HASH TABLE GENERATION A"...
0x180021c50  lea     rcx, aInetsrvIisMbCo_14; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180021c57  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x180021c5d  mov     ecx, 8000h; cb
0x180021c62  call    cs:__imp_CoTaskMemAlloc
0x180021c68  mov     rdi, rax
0x180021c6b  mov     [rsp+98h+arg_8], rax
0x180021c73  test    rax, rax
0x180021c76  jnz     short loc_180021CAB
0x180021c78  mov     rcx, [rbx+28h]
0x180021c7c  mov     rax, [rcx]
0x180021c7f  lea     rdx, aErrorOutOfMemo_3; "Error! Out of memory in THashedPKIndexe"...
0x180021c86  mov     rax, [rax]
0x180021c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c8e  xor     r9d, r9d; unsigned int
0x180021c91  mov     r8d, 1B9h; unsigned int
0x180021c97  lea     rdx, aOutOfMemory; "OUT OF MEMORY"
0x180021c9e  lea     rcx, aInetsrvIisMbCo_14; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180021ca5  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x180021cab  mov     dword ptr [rax], 0FFFFFFFFh
0x180021cb1  xor     esi, esi
0x180021cb3  cmp     esi, r14d
0x180021cb6  jnb     short loc_180021CDD
0x180021cb8  lea     rcx, [rsp+98h+var_50]; this
0x180021cbd  call    ?Get_InternalName@TTableMeta@@QEBAPEBGXZ; TTableMeta::Get_InternalName(void)
0x180021cc2  xor     edx, edx; unsigned int
0x180021cc4  mov     rcx, rax; unsigned __int16 *
0x180021cc7  call    ?Hash@@YAKPEBGK@Z; Hash(ushort const *,ulong)
0x180021ccc  mov     [rdi+rsi*4], eax
0x180021ccf  inc     esi
0x180021cd1  lea     rcx, [rsp+98h+var_50]
0x180021cd6  call    ?Next@?$TMetaTable@UQueryMetaPublic@@@@UEAA_NXZ; TMetaTable<QueryMetaPublic>::Next(void)
0x180021cdb  jmp     short loc_180021CB3
0x180021cdd  mov     eax, r14d
0x180021ce0  shr     eax, 1
0x180021ce2  or      eax, r14d
0x180021ce5  mov     ecx, eax
0x180021ce7  shr     ecx, 2
0x180021cea  or      ecx, eax
0x180021cec  mov     eax, ecx
0x180021cee  shr     eax, 4
0x180021cf1  or      eax, ecx
0x180021cf3  mov     ecx, eax
0x180021cf5  shr     ecx, 8
0x180021cf8  or      ecx, eax
0x180021cfa  mov     eax, ecx
0x180021cfc  shr     eax, 10h
0x180021cff  or      eax, ecx
0x180021d01  add     eax, 1
0x180021d04  mov     r15d, 80000000h
0x180021d0a  cmovnz  r15d, eax
0x180021d0e  lea     rax, [rsp+98h+arg_0]
0x180021d16  mov     [rsp+98h+var_70], rax; unsigned int *
0x180021d1b  mov     [rsp+98h+var_78], r15d; unsigned int
0x180021d20  mov     r9, rdi; unsigned int (*)[8192]
0x180021d23  mov     r8d, 1; unsigned int
0x180021d29  mov     edx, r14d; unsigned int
0x180021d2c  mov     rcx, rbx; this
0x180021d2f  call    ?FillInTheHashTable@THashedPKIndexes@@AEAAKKKQEAY0CAAA@KKPEAK@Z; THashedPKIndexes::FillInTheHashTable(ulong,ulong,ulong (* const)[8192],ulong,ulong *)
0x180021d34  mov     esi, eax
0x180021d36  mov     rcx, [rbx+20h]
0x180021d3a  mov     rdx, [rcx]
0x180021d3d  mov     rax, [rdx+160h]
0x180021d44  lea     rdx, aTablemeta; "TABLEMETA"
0x180021d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d50  mov     r8d, eax
0x180021d53  mov     rcx, [rbx+20h]
0x180021d57  mov     rdx, [rcx]
0x180021d5a  mov     rax, [rdx+0E8h]
0x180021d61  mov     edx, r8d
0x180021d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d69  mov     [rax+5Ch], esi
0x180021d6c  mov     r8, [rbx+10h]
0x180021d70  mov     rcx, [rbx+28h]
0x180021d74  mov     r9d, [r8+rsi*8+4]
0x180021d79  mov     rax, [rcx]
0x180021d7c  mov     edx, r9d
0x180021d7f  sub     edx, [r8+rsi*8]
0x180021d83  mov     [rsp+98h+var_68], edx
0x180021d87  mov     edx, [rsp+98h+arg_0]
0x180021d8e  mov     dword ptr [rsp+98h+var_70], edx
0x180021d92  mov     [rsp+98h+var_78], r15d
0x180021d97  mov     r8d, r14d
0x180021d9a  lea     rdx, aTablemetaHasDR; "\nTableMeta has %d rows, the hash table"...
0x180021da1  mov     rax, [rax]
0x180021da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021da9  nop
0x180021daa  mov     rcx, rdi; pv
0x180021dad  call    cs:__imp_CoTaskMemFree
0x180021db3  nop
0x180021db4  lea     r11, [rsp+98h+var_18]
0x180021dbc  mov     rbx, [r11+30h]
0x180021dc0  mov     rsi, [r11+38h]
0x180021dc4  mov     rsp, r11
0x180021dc7  pop     r15
0x180021dc9  pop     r14
0x180021dcb  pop     rdi
0x180021dcc  retn
```
