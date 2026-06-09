# THashedPKIndexes::FillInTheHashTableForIndexMeta(void)

- ea: `0x180021588`
- end: `0x1800218ed`
- name: `?FillInTheHashTableForIndexMeta@THashedPKIndexes@@AEAAXXZ`
- size: `869`
- prototype: `void __fastcall(THashedPKIndexes *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x180020e10`

## callees

- `0x180014168`
- `0x180017ad8`
- `0x180020e78`
- `0x180021588`
- `0x18002225c`
- `0x180022360`
- `0x1800224b8`
- `0x180022600`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800218c9`
- `ole32!CoTaskMemFree` at `0x1800218c9`
- `ole32!CoTaskMemAlloc` at `0x180021640`
- `ole32!CoTaskMemAlloc` at `0x180021640`

## string_xrefs

- `0x180021628`: `inetsrv\iis\mb\config\src\core\schemagen\thashedpkindexes.cpp`
- `0x18002167c`: `inetsrv\iis\mb\config\src\core\schemagen\thashedpkindexes.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall THashedPKIndexes::FillInTheHashTableForIndexMeta(THashedPKIndexes *this)
{
  unsigned int v2; // r14d
  const unsigned __int16 *Table; // r15
  const unsigned __int16 *InternalName; // r12
  unsigned int *v5; // rax
  unsigned int *v6; // rbx
  unsigned int v7; // eax
  __int64 v8; // rdi
  const unsigned __int16 *v9; // r15
  unsigned int i; // edi
  unsigned int v11; // eax
  unsigned int v12; // r13d
  __int64 v13; // r15
  const unsigned __int16 *v14; // rax
  unsigned int v15; // edi
  const unsigned __int16 *v16; // rax
  unsigned int v17; // edi
  const unsigned int *ColumnIndex; // rax
  unsigned int v19; // eax
  bool v20; // zf
  unsigned int v21; // eax
  unsigned int v22; // edi
  unsigned int v23; // r15d
  unsigned int v24; // eax
  TException *v25; // [rsp+40h] [rbp-68h] BYREF
  void **v26; // [rsp+48h] [rbp-60h] BYREF
  __int64 v27; // [rsp+50h] [rbp-58h]
  __int64 v28; // [rsp+58h] [rbp-50h]
  _OWORD v29[2]; // [rsp+60h] [rbp-48h] BYREF
  unsigned int v30; // [rsp+B0h] [rbp+8h] BYREF
  unsigned int *v31; // [rsp+B8h] [rbp+10h]

  v27 = *((_QWORD *)this + 4);
  v28 = 0;
  v26 = &TIndexMeta::`vftable';
  v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 288LL))(v27);
  v30 = 1;
  (***((void (__fastcall ****)(_QWORD, const wchar_t *))this + 5))(
    *((_QWORD *)this + 5),
    L"\nBuilding IndexMeta hash table");
  if ( v2 > 0x2000 )
  {
    (***((void (__fastcall ****)(_QWORD, const wchar_t *, _QWORD))this + 5))(
      *((_QWORD *)this + 5),
      L"Error! Too Many Rows - IndexMeta has %d rows, Hash table generation relies on fixed tables being less than %d rows\n",
      v2);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\thashedpkindexes.cpp",
      L"TOO MANY ROWS - HASH TABLE GENERATION ASSUMES FIXED TABLES ARE RELATIVELY SMALL",
      0x109u,
      0);
  }
  Table = 0;
  InternalName = 0;
  v5 = (unsigned int *)CoTaskMemAlloc(0x18000u);
  v6 = v5;
  v31 = v5;
  if ( !v5 )
  {
    (***((void (__fastcall ****)(_QWORD, const wchar_t *))this + 5))(
      *((_QWORD *)this + 5),
      L"Error! Out of memory in THashedPKIndexes::FillInTheHashTableForIndexMeta");
    ThrowException(L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\thashedpkindexes.cpp", L"OUT OF MEMORY", 0x110u, 0);
  }
  try
  {
    *v5 = -1;
    v8 = 0;
    while ( (unsigned int)v8 < v2 )
    {
      if ( TIndexMeta::Get_Table((TIndexMeta *)&v26) == Table )
      {
        v7 = -1;
      }
      else
      {
        Table = TIndexMeta::Get_Table((TIndexMeta *)&v26);
        v7 = Hash(Table, 0);
      }
      v6[v8] = v7;
      v8 = (unsigned int)(v8 + 1);
      TMetaTable<QueryMetaPublic>::Next(&v26);
    }
    LODWORD(v28) = HIDWORD(v28);
    v9 = 0;
    v6[0x2000] = -1;
    for ( i = 0; i < v2; ++i )
    {
      if ( TIndexMeta::Get_Table((TIndexMeta *)&v26) == v9
        && TIndexMeta::Get_InternalName((TIndexMeta *)&v26) == InternalName )
      {
        v11 = -1;
      }
      else
      {
        v9 = TIndexMeta::Get_Table((TIndexMeta *)&v26);
        v12 = Hash(v9, 0);
        InternalName = TIndexMeta::Get_InternalName((TIndexMeta *)&v26);
        v11 = Hash(InternalName, v12);
      }
      v6[i + 0x2000] = v11;
      TMetaTable<QueryMetaPublic>::Next(&v26);
    }
    LODWORD(v28) = HIDWORD(v28);
    v13 = 0;
    while ( (unsigned int)v13 < v2 )
    {
      v14 = TIndexMeta::Get_Table((TIndexMeta *)&v26);
      v15 = Hash(v14, 0);
      v16 = TIndexMeta::Get_InternalName((TIndexMeta *)&v26);
      v17 = Hash(v16, v15);
      ColumnIndex = TIndexMeta::Get_ColumnIndex((TIndexMeta *)&v26);
      v6[v13 + 0x4000] = *((_DWORD *)c_rgulHashTable + ((unsigned __int64)HIWORD(*ColumnIndex) >> 8))
                       ^ __ROL4__(
                           *((_DWORD *)c_rgulHashTable + (unsigned __int8)BYTE2(*ColumnIndex))
                         ^ __ROL4__(
                             *((_DWORD *)c_rgulHashTable + ((unsigned __int64)*(unsigned __int16 *)ColumnIndex >> 8))
                           ^ __ROL4__(
                               *((_DWORD *)c_rgulHashTable + *(unsigned __int8 *)ColumnIndex) ^ __ROL4__(v17, 1),
                               1),
                             1),
                           1);
      v13 = (unsigned int)(v13 + 1);
      TMetaTable<QueryMetaPublic>::Next(&v26);
    }
    v19 = v2
        | (v2 >> 1)
        | ((v2 | (v2 >> 1)) >> 2)
        | ((v2 | (v2 >> 1) | ((v2 | (v2 >> 1)) >> 2)) >> 4)
        | ((v2 | (v2 >> 1) | ((v2 | (v2 >> 1)) >> 2) | ((v2 | (v2 >> 1) | ((v2 | (v2 >> 1)) >> 2)) >> 4)) >> 8)
        | ((v2
          | (v2 >> 1)
          | ((v2 | (v2 >> 1)) >> 2)
          | ((v2 | (v2 >> 1) | ((v2 | (v2 >> 1)) >> 2)) >> 4)
          | ((v2 | (v2 >> 1) | ((v2 | (v2 >> 1)) >> 2) | ((v2 | (v2 >> 1) | ((v2 | (v2 >> 1)) >> 2)) >> 4)) >> 8)) >> 16);
    v20 = v19 == -1;
    v21 = v19 + 1;
    v22 = 0x80000000;
    if ( !v20 )
      v22 = v21;
    v23 = THashedPKIndexes::FillInTheHashTable(this, v2, 3u, (unsigned int (*const)[8192])v6, v22, &v30);
    v24 = (*(__int64 (__fastcall **)(_QWORD, const WCHAR *))(**((_QWORD **)this + 4) + 352LL))(
            *((_QWORD *)this + 4),
            L"INDEXMETA");
    *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 4) + 232LL))(
                  *((_QWORD *)this + 4),
                  v24)
              + 92) = v23;
    (***((void (__fastcall ****)(_QWORD, const wchar_t *, _QWORD))this + 5))(
      *((_QWORD *)this + 5),
      L"\nIndexMeta has %d rows, the hash table has %d elements, %d modulo, %d max chain and %d nonunique entries.\n",
      v2);
  }
  catch ( TException *v25 )
  {
    if ( v31 )
      CoTaskMemFree(v31);
    v29[0] = *(_OWORD *)v25;
    v29[1] = *((_OWORD *)v25 + 1);
    throw (TException *)v29;
  }
  CoTaskMemFree(v6);
}

```

## disassembly

```asm
0x180021588  mov     r11, rsp
0x18002158b  mov     [r11+18h], rbx
0x18002158f  mov     [r11+20h], rsi
0x180021593  push    rdi
0x180021594  push    r12
0x180021596  push    r13
0x180021598  push    r14
0x18002159a  push    r15
0x18002159c  sub     rsp, 80h
0x1800215a3  mov     rsi, rcx
0x1800215a6  mov     rcx, [rcx+20h]
0x1800215aa  mov     [r11-58h], rcx
0x1800215ae  mov     qword ptr [r11-50h], 0
0x1800215b6  lea     rax, ??_7TIndexMeta@@6B@; const TIndexMeta::`vftable'
0x1800215bd  mov     [r11-60h], rax
0x1800215c1  mov     rax, [rcx]
0x1800215c4  mov     rax, [rax+120h]
0x1800215cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800215d0  mov     r14d, eax
0x1800215d3  mov     [rsp+0A8h+arg_0], 1
0x1800215de  mov     rcx, [rsi+28h]
0x1800215e2  mov     rdx, [rcx]
0x1800215e5  mov     rax, [rdx]
0x1800215e8  lea     rdx, aBuildingIndexm; "\nBuilding IndexMeta hash table"
0x1800215ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800215f4  mov     r9d, 2000h
0x1800215fa  cmp     r14d, r9d
0x1800215fd  jbe     short loc_180021635
0x1800215ff  mov     rcx, [rsi+28h]
0x180021603  mov     rax, [rcx]
0x180021606  mov     r8d, r14d
0x180021609  lea     rdx, aErrorTooManyRo_0; "Error! Too Many Rows - IndexMeta has %d"...
0x180021610  mov     rax, [rax]
0x180021613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021618  xor     r9d, r9d; unsigned int
0x18002161b  mov     r8d, 109h; unsigned int
0x180021621  lea     rdx, aTooManyRowsHas; "TOO MANY ROWS - HASH TABLE GENERATION A"...
0x180021628  lea     rcx, aInetsrvIisMbCo_14; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18002162f  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x180021635  xor     r15d, r15d
0x180021638  xor     r12d, r12d
0x18002163b  mov     ecx, 18000h; cb
0x180021640  call    cs:__imp_CoTaskMemAlloc
0x180021646  mov     rbx, rax
0x180021649  mov     [rsp+0A8h+arg_8], rax
0x180021651  test    rax, rax
0x180021654  jnz     short loc_180021689
0x180021656  mov     rcx, [rsi+28h]
0x18002165a  mov     rax, [rcx]
0x18002165d  lea     rdx, aErrorOutOfMemo; "Error! Out of memory in THashedPKIndexe"...
0x180021664  mov     rax, [rax]
0x180021667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002166c  xor     r9d, r9d; unsigned int
0x18002166f  mov     r8d, 110h; unsigned int
0x180021675  lea     rdx, aOutOfMemory; "OUT OF MEMORY"
0x18002167c  lea     rcx, aInetsrvIisMbCo_14; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180021683  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x180021689  or      r13d, 0FFFFFFFFh
0x18002168d  mov     [rax], r13d
0x180021690  xor     edi, edi
0x180021692  cmp     edi, r14d
0x180021695  jnb     short loc_1800216D3
0x180021697  lea     rcx, [rsp+0A8h+var_60]; this
0x18002169c  call    ?Get_Table@TIndexMeta@@QEBAPEBGXZ; TIndexMeta::Get_Table(void)
0x1800216a1  cmp     rax, r15
0x1800216a4  jnz     short loc_1800216AB
0x1800216a6  mov     eax, r13d
0x1800216a9  jmp     short loc_1800216C2
0x1800216ab  lea     rcx, [rsp+0A8h+var_60]; this
0x1800216b0  call    ?Get_Table@TIndexMeta@@QEBAPEBGXZ; TIndexMeta::Get_Table(void)
0x1800216b5  mov     r15, rax
0x1800216b8  xor     edx, edx; unsigned int
0x1800216ba  mov     rcx, rax; unsigned __int16 *
0x1800216bd  call    ?Hash@@YAKPEBGK@Z; Hash(ushort const *,ulong)
0x1800216c2  mov     [rbx+rdi*4], eax
0x1800216c5  inc     edi
0x1800216c7  lea     rcx, [rsp+0A8h+var_60]
0x1800216cc  call    ?Next@?$TMetaTable@UQueryMetaPublic@@@@UEAA_NXZ; TMetaTable<QueryMetaPublic>::Next(void)
0x1800216d1  jmp     short loc_180021692
0x1800216d3  mov     eax, [rsp+0A8h+var_4C]
0x1800216d7  mov     [rsp+0A8h+var_50], eax
0x1800216db  xor     r15d, r15d
0x1800216de  mov     [rbx+8000h], r13d
0x1800216e5  xor     edi, edi
0x1800216e7  cmp     edi, r14d
0x1800216ea  jnb     short loc_18002175F
0x1800216ec  lea     rcx, [rsp+0A8h+var_60]; this
0x1800216f1  call    ?Get_Table@TIndexMeta@@QEBAPEBGXZ; TIndexMeta::Get_Table(void)
0x1800216f6  cmp     rax, r15
0x1800216f9  jnz     short loc_18002170F
0x1800216fb  lea     rcx, [rsp+0A8h+var_60]; this
0x180021700  call    ?Get_InternalName@TIndexMeta@@QEBAPEBGXZ; TIndexMeta::Get_InternalName(void)
0x180021705  cmp     rax, r12
0x180021708  jnz     short loc_18002170F
0x18002170a  mov     eax, r13d
0x18002170d  jmp     short loc_180021745
0x18002170f  lea     rcx, [rsp+0A8h+var_60]; this
0x180021714  call    ?Get_Table@TIndexMeta@@QEBAPEBGXZ; TIndexMeta::Get_Table(void)
0x180021719  mov     r15, rax
0x18002171c  xor     edx, edx; unsigned int
0x18002171e  mov     rcx, rax; unsigned __int16 *
0x180021721  call    ?Hash@@YAKPEBGK@Z; Hash(ushort const *,ulong)
0x180021726  mov     r13d, eax
0x180021729  lea     rcx, [rsp+0A8h+var_60]; this
0x18002172e  call    ?Get_InternalName@TIndexMeta@@QEBAPEBGXZ; TIndexMeta::Get_InternalName(void)
0x180021733  mov     r12, rax
0x180021736  mov     edx, r13d; unsigned int
0x180021739  mov     rcx, rax; unsigned __int16 *
0x18002173c  call    ?Hash@@YAKPEBGK@Z; Hash(ushort const *,ulong)
0x180021741  or      r13d, 0FFFFFFFFh
0x180021745  mov     ecx, edi
0x180021747  mov     rdx, rbx
0x18002174a  mov     [rbx+rcx*4+8000h], eax
0x180021751  inc     edi
0x180021753  lea     rcx, [rsp+0A8h+var_60]
0x180021758  call    ?Next@?$TMetaTable@UQueryMetaPublic@@@@UEAA_NXZ; TMetaTable<QueryMetaPublic>::Next(void)
0x18002175d  jmp     short loc_1800216E7
0x18002175f  mov     eax, [rsp+0A8h+var_4C]
0x180021763  mov     [rsp+0A8h+var_50], eax
0x180021767  xor     r15d, r15d
0x18002176a  lea     r12, c_rgulHashTable
0x180021771  cmp     r15d, r14d
0x180021774  jnb     loc_1800217FB
0x18002177a  lea     rcx, [rsp+0A8h+var_60]; this
0x18002177f  call    ?Get_Table@TIndexMeta@@QEBAPEBGXZ; TIndexMeta::Get_Table(void)
0x180021784  xor     edx, edx; unsigned int
0x180021786  mov     rcx, rax; unsigned __int16 *
0x180021789  call    ?Hash@@YAKPEBGK@Z; Hash(ushort const *,ulong)
0x18002178e  mov     edi, eax
0x180021790  lea     rcx, [rsp+0A8h+var_60]; this
0x180021795  call    ?Get_InternalName@TIndexMeta@@QEBAPEBGXZ; TIndexMeta::Get_InternalName(void)
0x18002179a  mov     edx, edi; unsigned int
0x18002179c  mov     rcx, rax; unsigned __int16 *
0x18002179f  call    ?Hash@@YAKPEBGK@Z; Hash(ushort const *,ulong)
0x1800217a4  mov     edi, eax
0x1800217a6  lea     rcx, [rsp+0A8h+var_60]; this
0x1800217ab  call    ?Get_ColumnIndex@TIndexMeta@@QEBAPEBKXZ; TIndexMeta::Get_ColumnIndex(void)
0x1800217b0  mov     edx, [rax]
0x1800217b2  shr     edx, 10h
0x1800217b5  rol     edi, 1
0x1800217b7  movzx   ecx, byte ptr [rax]
0x1800217ba  xor     edi, [r12+rcx*4]
0x1800217be  rol     edi, 1
0x1800217c0  movzx   eax, word ptr [rax]
0x1800217c3  shr     rax, 8
0x1800217c7  xor     edi, [r12+rax*4]
0x1800217cb  rol     edi, 1
0x1800217cd  movzx   eax, dl
0x1800217d0  xor     edi, [r12+rax*4]
0x1800217d4  rol     edi, 1
0x1800217d6  movzx   eax, dx
0x1800217d9  shr     rax, 8
0x1800217dd  xor     edi, [r12+rax*4]
0x1800217e1  mov     [rbx+r15*4+10000h], edi
0x1800217e9  inc     r15d
0x1800217ec  lea     rcx, [rsp+0A8h+var_60]
0x1800217f1  call    ?Next@?$TMetaTable@UQueryMetaPublic@@@@UEAA_NXZ; TMetaTable<QueryMetaPublic>::Next(void)
0x1800217f6  jmp     loc_180021771
0x1800217fb  mov     eax, r14d
0x1800217fe  shr     eax, 1
0x180021800  or      eax, r14d
0x180021803  mov     ecx, eax
0x180021805  shr     ecx, 2
0x180021808  or      ecx, eax
0x18002180a  mov     eax, ecx
0x18002180c  shr     eax, 4
0x18002180f  or      eax, ecx
0x180021811  mov     ecx, eax
0x180021813  shr     ecx, 8
0x180021816  or      ecx, eax
0x180021818  mov     eax, ecx
0x18002181a  shr     eax, 10h
0x18002181d  or      eax, ecx
0x18002181f  add     eax, 1
0x180021822  mov     edi, 80000000h
0x180021827  cmovnz  edi, eax
0x18002182a  lea     rax, [rsp+0A8h+arg_0]
0x180021832  mov     [rsp+0A8h+var_80], rax; unsigned int *
0x180021837  mov     [rsp+0A8h+var_88], edi; unsigned int
0x18002183b  mov     r9, rbx; unsigned int (*)[8192]
0x18002183e  mov     r8d, 3; unsigned int
0x180021844  mov     edx, r14d; unsigned int
0x180021847  mov     rcx, rsi; this
0x18002184a  call    ?FillInTheHashTable@THashedPKIndexes@@AEAAKKKQEAY0CAAA@KKPEAK@Z; THashedPKIndexes::FillInTheHashTable(ulong,ulong,ulong (* const)[8192],ulong,ulong *)
0x18002184f  mov     r15d, eax
0x180021852  mov     rcx, [rsi+20h]
0x180021856  mov     rdx, [rcx]
0x180021859  mov     rax, [rdx+160h]
0x180021860  lea     rdx, aIndexmeta; "INDEXMETA"
0x180021867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002186c  mov     r8d, eax
0x18002186f  mov     rcx, [rsi+20h]
0x180021873  mov     rdx, [rcx]
0x180021876  mov     rax, [rdx+0E8h]
0x18002187d  mov     edx, r8d
0x180021880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021885  mov     [rax+5Ch], r15d
0x180021889  mov     r8, [rsi+10h]
0x18002188d  mov     rcx, [rsi+28h]
0x180021891  mov     r9d, [r8+r15*8+4]
0x180021896  mov     rax, [rcx]
0x180021899  mov     edx, r9d
0x18002189c  sub     edx, [r8+r15*8]
0x1800218a0  mov     [rsp+0A8h+var_78], edx
0x1800218a4  mov     edx, [rsp+0A8h+arg_0]
0x1800218ab  mov     dword ptr [rsp+0A8h+var_80], edx
0x1800218af  mov     [rsp+0A8h+var_88], edi
0x1800218b3  mov     r8d, r14d
0x1800218b6  lea     rdx, aIndexmetaHasDR; "\nIndexMeta has %d rows, the hash table"...
0x1800218bd  mov     rax, [rax]
0x1800218c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218c5  nop
0x1800218c6  mov     rcx, rbx; pv
0x1800218c9  call    cs:__imp_CoTaskMemFree
0x1800218cf  nop
0x1800218d0  lea     r11, [rsp+0A8h+var_28]
0x1800218d8  mov     rbx, [r11+40h]
0x1800218dc  mov     rsi, [r11+48h]
0x1800218e0  mov     rsp, r11
0x1800218e3  pop     r15
0x1800218e5  pop     r14
0x1800218e7  pop     r13
0x1800218e9  pop     r12
0x1800218eb  pop     rdi
0x1800218ec  retn
```
