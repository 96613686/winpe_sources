# THashedPKIndexes::FillInTheHashTableForQueryMeta(void)

- ea: `0x1800218f4`
- end: `0x180021bad`
- name: `?FillInTheHashTableForQueryMeta@THashedPKIndexes@@AEAAXXZ`
- size: `697`
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
- `0x1800218f4`
- `0x1800224fc`
- `0x180022600`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180021b89`
- `ole32!CoTaskMemFree` at `0x180021b89`
- `ole32!CoTaskMemAlloc` at `0x1800219a9`
- `ole32!CoTaskMemAlloc` at `0x1800219a9`

## string_xrefs

- `0x180021994`: `inetsrv\iis\mb\config\src\core\schemagen\thashedpkindexes.cpp`
- `0x1800219e5`: `inetsrv\iis\mb\config\src\core\schemagen\thashedpkindexes.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall THashedPKIndexes::FillInTheHashTableForQueryMeta(THashedPKIndexes *this)
{
  unsigned int v2; // r14d
  const unsigned __int16 *Table; // r15
  unsigned int *v4; // rax
  unsigned int *v5; // rbx
  unsigned int v6; // eax
  __int64 v7; // rsi
  __int64 v8; // rsi
  const unsigned __int16 *v9; // rax
  unsigned int v10; // r12d
  __int64 v11; // r15
  __int64 (__fastcall *v12)(__int64, _QWORD); // r13
  __int64 v13; // rax
  const unsigned __int16 *v14; // rax
  unsigned int v15; // eax
  bool v16; // zf
  unsigned int v17; // eax
  unsigned int v18; // r15d
  unsigned int v19; // esi
  unsigned int v20; // eax
  TException *v21; // [rsp+40h] [rbp-68h] BYREF
  void **v22; // [rsp+48h] [rbp-60h] BYREF
  __int64 v23; // [rsp+50h] [rbp-58h]
  __int64 v24; // [rsp+58h] [rbp-50h]
  _OWORD v25[2]; // [rsp+60h] [rbp-48h] BYREF
  unsigned int v26; // [rsp+B0h] [rbp+8h] BYREF
  unsigned int *v27; // [rsp+B8h] [rbp+10h]

  v23 = *((_QWORD *)this + 4);
  v24 = 0;
  v22 = &TQueryMeta::`vftable';
  v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 296LL))(v23);
  v26 = 1;
  (***((void (__fastcall ****)(_QWORD, const wchar_t *))this + 5))(
    *((_QWORD *)this + 5),
    L"\nBuilding QueryMeta hash table");
  if ( v2 > 0x2000 )
  {
    (***((void (__fastcall ****)(_QWORD, const wchar_t *, _QWORD))this + 5))(
      *((_QWORD *)this + 5),
      L"Error! Too Many Rows - QueryMeta has %d rows, Hash table generation relies on fixed tables being less than %d rows\n",
      v2);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\thashedpkindexes.cpp",
      L"TOO MANY ROWS - HASH TABLE GENERATION ASSUMES FIXED TABLES ARE RELATIVELY SMALL",
      0x160u,
      0);
  }
  Table = 0;
  v4 = (unsigned int *)CoTaskMemAlloc(0x10000u);
  v5 = v4;
  v27 = v4;
  if ( !v4 )
  {
    (***((void (__fastcall ****)(_QWORD, const wchar_t *))this + 5))(
      *((_QWORD *)this + 5),
      L"Error! Out of memory in THashedPKIndexes::FillInTheHashTableForQueryMeta");
    ThrowException(L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\thashedpkindexes.cpp", L"OUT OF MEMORY", 0x167u, 0);
  }
  try
  {
    *v4 = -1;
    v7 = 0;
    while ( (unsigned int)v7 < v2 )
    {
      if ( TQueryMeta::Get_Table((TQueryMeta *)&v22) == Table )
      {
        v6 = -1;
      }
      else
      {
        Table = TQueryMeta::Get_Table((TQueryMeta *)&v22);
        v6 = Hash(Table, 0);
      }
      v5[v7] = v6;
      v7 = (unsigned int)(v7 + 1);
      TMetaTable<QueryMetaPublic>::Next(&v22);
    }
    LODWORD(v24) = HIDWORD(v24);
    v5[0x2000] = -1;
    v8 = 0;
    while ( (unsigned int)v8 < v2 )
    {
      v9 = TQueryMeta::Get_Table((TQueryMeta *)&v22);
      v10 = Hash(v9, 0);
      v11 = v23;
      v12 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v23 + 144LL);
      v13 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v23 + 208LL))(v23, (unsigned int)v24);
      v14 = (const unsigned __int16 *)v12(v11, *(unsigned int *)(v13 + 4));
      v5[v8 + 0x2000] = Hash(v14, v10);
      v8 = (unsigned int)(v8 + 1);
      TMetaTable<QueryMetaPublic>::Next(&v22);
    }
    v15 = v2
        | (v2 >> 1)
        | ((v2 | (v2 >> 1)) >> 2)
        | ((v2 | (v2 >> 1) | ((v2 | (v2 >> 1)) >> 2)) >> 4)
        | ((v2 | (v2 >> 1) | ((v2 | (v2 >> 1)) >> 2) | ((v2 | (v2 >> 1) | ((v2 | (v2 >> 1)) >> 2)) >> 4)) >> 8)
        | ((v2
          | (v2 >> 1)
          | ((v2 | (v2 >> 1)) >> 2)
          | ((v2 | (v2 >> 1) | ((v2 | (v2 >> 1)) >> 2)) >> 4)
          | ((v2 | (v2 >> 1) | ((v2 | (v2 >> 1)) >> 2) | ((v2 | (v2 >> 1) | ((v2 | (v2 >> 1)) >> 2)) >> 4)) >> 8)) >> 16);
    v16 = v15 == -1;
    v17 = v15 + 1;
    v18 = 0x80000000;
    if ( !v16 )
      v18 = v17;
    v19 = THashedPKIndexes::FillInTheHashTable(this, v2, 2u, (unsigned int (*const)[8192])v5, v18, &v26);
    v20 = (*(__int64 (__fastcall **)(_QWORD, const WCHAR *))(**((_QWORD **)this + 4) + 352LL))(
            *((_QWORD *)this + 4),
            L"QUERYMETA");
    *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 4) + 232LL))(
                  *((_QWORD *)this + 4),
                  v20)
              + 92) = v19;
    (***((void (__fastcall ****)(_QWORD, const wchar_t *, _QWORD))this + 5))(
      *((_QWORD *)this + 5),
      L"\nQueryMeta has %d rows, the hash table has %d elements, %d modulo, %d max chain and %d nonunique entries.\n",
      v2);
  }
  catch ( TException *v21 )
  {
    if ( v27 )
      CoTaskMemFree(v27);
    v25[0] = *(_OWORD *)v21;
    v25[1] = *((_OWORD *)v21 + 1);
    throw (TException *)v25;
  }
  CoTaskMemFree(v5);
}

```

## disassembly

```asm
0x1800218f4  mov     r11, rsp
0x1800218f7  mov     [r11+18h], rbx
0x1800218fb  mov     [r11+20h], rsi
0x1800218ff  push    rdi
0x180021900  push    r12
0x180021902  push    r13
0x180021904  push    r14
0x180021906  push    r15
0x180021908  sub     rsp, 80h
0x18002190f  mov     rdi, rcx
0x180021912  mov     rcx, [rcx+20h]
0x180021916  mov     [r11-58h], rcx
0x18002191a  mov     qword ptr [r11-50h], 0
0x180021922  lea     rax, ??_7TQueryMeta@@6B@; const TQueryMeta::`vftable'
0x180021929  mov     [r11-60h], rax
0x18002192d  mov     rax, [rcx]
0x180021930  mov     rax, [rax+128h]
0x180021937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002193c  mov     r14d, eax
0x18002193f  mov     [rsp+0A8h+arg_0], 1
0x18002194a  mov     rcx, [rdi+28h]
0x18002194e  mov     rdx, [rcx]
0x180021951  mov     rax, [rdx]
0x180021954  lea     rdx, aBuildingQuerym; "\nBuilding QueryMeta hash table"
0x18002195b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021960  mov     r9d, 2000h
0x180021966  cmp     r14d, r9d
0x180021969  jbe     short loc_1800219A1
0x18002196b  mov     rcx, [rdi+28h]
0x18002196f  mov     rax, [rcx]
0x180021972  mov     r8d, r14d
0x180021975  lea     rdx, aErrorTooManyRo_2; "Error! Too Many Rows - QueryMeta has %d"...
0x18002197c  mov     rax, [rax]
0x18002197f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021984  xor     r9d, r9d; unsigned int
0x180021987  mov     r8d, 160h; unsigned int
0x18002198d  lea     rdx, aTooManyRowsHas; "TOO MANY ROWS - HASH TABLE GENERATION A"...
0x180021994  lea     rcx, aInetsrvIisMbCo_14; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18002199b  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x1800219a1  xor     r15d, r15d
0x1800219a4  mov     ecx, 10000h; cb
0x1800219a9  call    cs:__imp_CoTaskMemAlloc
0x1800219af  mov     rbx, rax
0x1800219b2  mov     [rsp+0A8h+arg_8], rax
0x1800219ba  test    rax, rax
0x1800219bd  jnz     short loc_1800219F2
0x1800219bf  mov     rcx, [rdi+28h]
0x1800219c3  mov     rax, [rcx]
0x1800219c6  lea     rdx, aErrorOutOfMemo_1; "Error! Out of memory in THashedPKIndexe"...
0x1800219cd  mov     rax, [rax]
0x1800219d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219d5  xor     r9d, r9d; unsigned int
0x1800219d8  mov     r8d, 167h; unsigned int
0x1800219de  lea     rdx, aOutOfMemory; "OUT OF MEMORY"
0x1800219e5  lea     rcx, aInetsrvIisMbCo_14; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x1800219ec  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x1800219f2  or      r12d, 0FFFFFFFFh
0x1800219f6  mov     [rax], r12d
0x1800219f9  xor     esi, esi
0x1800219fb  cmp     esi, r14d
0x1800219fe  jnb     short loc_180021A3C
0x180021a00  lea     rcx, [rsp+0A8h+var_60]; this
0x180021a05  call    ?Get_Table@TQueryMeta@@QEBAPEBGXZ; TQueryMeta::Get_Table(void)
0x180021a0a  cmp     rax, r15
0x180021a0d  jnz     short loc_180021A14
0x180021a0f  mov     eax, r12d
0x180021a12  jmp     short loc_180021A2B
0x180021a14  lea     rcx, [rsp+0A8h+var_60]; this
0x180021a19  call    ?Get_Table@TQueryMeta@@QEBAPEBGXZ; TQueryMeta::Get_Table(void)
0x180021a1e  mov     r15, rax
0x180021a21  xor     edx, edx; unsigned int
0x180021a23  mov     rcx, rax; unsigned __int16 *
0x180021a26  call    ?Hash@@YAKPEBGK@Z; Hash(ushort const *,ulong)
0x180021a2b  mov     [rbx+rsi*4], eax
0x180021a2e  inc     esi
0x180021a30  lea     rcx, [rsp+0A8h+var_60]
0x180021a35  call    ?Next@?$TMetaTable@UQueryMetaPublic@@@@UEAA_NXZ; TMetaTable<QueryMetaPublic>::Next(void)
0x180021a3a  jmp     short loc_1800219FB
0x180021a3c  mov     eax, [rsp+0A8h+var_4C]
0x180021a40  mov     [rsp+0A8h+var_50], eax
0x180021a44  mov     [rbx+8000h], r12d
0x180021a4b  xor     esi, esi
0x180021a4d  cmp     esi, r14d
0x180021a50  jnb     short loc_180021AB9
0x180021a52  lea     rcx, [rsp+0A8h+var_60]; this
0x180021a57  call    ?Get_Table@TQueryMeta@@QEBAPEBGXZ; TQueryMeta::Get_Table(void)
0x180021a5c  xor     edx, edx; unsigned int
0x180021a5e  mov     rcx, rax; unsigned __int16 *
0x180021a61  call    ?Hash@@YAKPEBGK@Z; Hash(ushort const *,ulong)
0x180021a66  mov     r12d, eax
0x180021a69  mov     r15, [rsp+0A8h+var_58]
0x180021a6e  mov     rdx, [r15]
0x180021a71  mov     r13, [rdx+90h]
0x180021a78  mov     rax, [rdx+0D0h]
0x180021a7f  mov     edx, [rsp+0A8h+var_50]
0x180021a83  mov     rcx, r15
0x180021a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a8b  mov     edx, [rax+4]
0x180021a8e  mov     rcx, r15
0x180021a91  mov     rax, r13
0x180021a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a99  mov     edx, r12d; unsigned int
0x180021a9c  mov     rcx, rax; unsigned __int16 *
0x180021a9f  call    ?Hash@@YAKPEBGK@Z; Hash(ushort const *,ulong)
0x180021aa4  mov     [rbx+rsi*4+8000h], eax
0x180021aab  inc     esi
0x180021aad  lea     rcx, [rsp+0A8h+var_60]
0x180021ab2  call    ?Next@?$TMetaTable@UQueryMetaPublic@@@@UEAA_NXZ; TMetaTable<QueryMetaPublic>::Next(void)
0x180021ab7  jmp     short loc_180021A4D
0x180021ab9  mov     eax, r14d
0x180021abc  shr     eax, 1
0x180021abe  or      eax, r14d
0x180021ac1  mov     ecx, eax
0x180021ac3  shr     ecx, 2
0x180021ac6  or      ecx, eax
0x180021ac8  mov     eax, ecx
0x180021aca  shr     eax, 4
0x180021acd  or      eax, ecx
0x180021acf  mov     ecx, eax
0x180021ad1  shr     ecx, 8
0x180021ad4  or      ecx, eax
0x180021ad6  mov     eax, ecx
0x180021ad8  shr     eax, 10h
0x180021adb  or      eax, ecx
0x180021add  add     eax, 1
0x180021ae0  mov     r15d, 80000000h
0x180021ae6  cmovnz  r15d, eax
0x180021aea  lea     rax, [rsp+0A8h+arg_0]
0x180021af2  mov     [rsp+0A8h+var_80], rax; unsigned int *
0x180021af7  mov     [rsp+0A8h+var_88], r15d; unsigned int
0x180021afc  mov     r9, rbx; unsigned int (*)[8192]
0x180021aff  mov     r8d, 2; unsigned int
0x180021b05  mov     edx, r14d; unsigned int
0x180021b08  mov     rcx, rdi; this
0x180021b0b  call    ?FillInTheHashTable@THashedPKIndexes@@AEAAKKKQEAY0CAAA@KKPEAK@Z; THashedPKIndexes::FillInTheHashTable(ulong,ulong,ulong (* const)[8192],ulong,ulong *)
0x180021b10  mov     esi, eax
0x180021b12  mov     rcx, [rdi+20h]
0x180021b16  mov     rdx, [rcx]
0x180021b19  mov     rax, [rdx+160h]
0x180021b20  lea     rdx, aQuerymeta; "QUERYMETA"
0x180021b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b2c  mov     r8d, eax
0x180021b2f  mov     rcx, [rdi+20h]
0x180021b33  mov     rdx, [rcx]
0x180021b36  mov     rax, [rdx+0E8h]
0x180021b3d  mov     edx, r8d
0x180021b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b45  mov     [rax+5Ch], esi
0x180021b48  mov     r8, [rdi+10h]
0x180021b4c  mov     rcx, [rdi+28h]
0x180021b50  mov     r9d, [r8+rsi*8+4]
0x180021b55  mov     rax, [rcx]
0x180021b58  mov     edx, r9d
0x180021b5b  sub     edx, [r8+rsi*8]
0x180021b5f  mov     [rsp+0A8h+var_78], edx
0x180021b63  mov     edx, [rsp+0A8h+arg_0]
0x180021b6a  mov     dword ptr [rsp+0A8h+var_80], edx
0x180021b6e  mov     [rsp+0A8h+var_88], r15d
0x180021b73  mov     r8d, r14d
0x180021b76  lea     rdx, aQuerymetaHasDR; "\nQueryMeta has %d rows, the hash table"...
0x180021b7d  mov     rax, [rax]
0x180021b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b85  nop
0x180021b86  mov     rcx, rbx; pv
0x180021b89  call    cs:__imp_CoTaskMemFree
0x180021b8f  nop
0x180021b90  lea     r11, [rsp+0A8h+var_28]
0x180021b98  mov     rbx, [r11+40h]
0x180021b9c  mov     rsi, [r11+48h]
0x180021ba0  mov     rsp, r11
0x180021ba3  pop     r15
0x180021ba5  pop     r14
0x180021ba7  pop     r13
0x180021ba9  pop     r12
0x180021bab  pop     rdi
0x180021bac  retn
```
