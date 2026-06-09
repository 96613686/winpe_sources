# THashedPKIndexes::FillInTheHashTableForColumnMeta(void)

- ea: `0x180021084`
- end: `0x18002135f`
- name: `?FillInTheHashTableForColumnMeta@THashedPKIndexes@@AEAAXXZ`
- size: `731`
- prototype: `void __fastcall(THashedPKIndexes *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180020e10`

## callees

- `0x180014168`
- `0x180017ad8`
- `0x180020e78`
- `0x180021084`
- `0x1800222e0`
- `0x18002247c`
- `0x180022600`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002133f`
- `ole32!CoTaskMemFree` at `0x18002133f`
- `ole32!CoTaskMemAlloc` at `0x180021138`
- `ole32!CoTaskMemAlloc` at `0x180021138`

## string_xrefs

- `0x180021123`: `inetsrv\iis\mb\config\src\core\schemagen\thashedpkindexes.cpp`
- `0x180021172`: `inetsrv\iis\mb\config\src\core\schemagen\thashedpkindexes.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall THashedPKIndexes::FillInTheHashTableForColumnMeta(THashedPKIndexes *this)
{
  unsigned int v2; // r15d
  const unsigned __int16 *Table; // r14
  unsigned int *v4; // rax
  unsigned int *v5; // rbx
  unsigned int v6; // eax
  __int64 v7; // rsi
  unsigned int i; // r14d
  int v9; // esi
  const unsigned __int16 *v10; // rax
  unsigned int v11; // esi
  const unsigned int *Index; // rax
  unsigned int v13; // eax
  bool v14; // zf
  unsigned int v15; // eax
  unsigned int v16; // esi
  unsigned int v17; // r14d
  unsigned int v18; // eax
  TException *v19; // [rsp+40h] [rbp-58h] BYREF
  void **v20; // [rsp+48h] [rbp-50h] BYREF
  __int64 v21; // [rsp+50h] [rbp-48h]
  __int64 v22; // [rsp+58h] [rbp-40h]
  _OWORD v23[2]; // [rsp+60h] [rbp-38h] BYREF
  unsigned int v24; // [rsp+A0h] [rbp+8h] BYREF
  unsigned int *v25; // [rsp+A8h] [rbp+10h]

  v21 = *((_QWORD *)this + 4);
  v22 = 0;
  v20 = &TColumnMeta::`vftable';
  v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 264LL))(v21);
  v24 = 0;
  (***((void (__fastcall ****)(_QWORD, const wchar_t *))this + 5))(
    *((_QWORD *)this + 5),
    L"\nBuilding ColumnMeta hash table");
  if ( v2 > 0x2000 )
  {
    (***((void (__fastcall ****)(_QWORD, const wchar_t *, _QWORD))this + 5))(
      *((_QWORD *)this + 5),
      L"Error! Too Many Rows - ColumnMeta has %d rows, Hash table generation relies on fixed tables being less than %d rows\n",
      v2);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\thashedpkindexes.cpp",
      L"TOO MANY ROWS - HASH TABLE GENERATION ASSUMES FIXED TABLES ARE RELATIVELY SMALL",
      0x75u,
      0xC00210F2);
  }
  Table = 0;
  v4 = (unsigned int *)CoTaskMemAlloc(0x10000u);
  v5 = v4;
  v25 = v4;
  if ( !v4 )
  {
    (***((void (__fastcall ****)(_QWORD, const wchar_t *))this + 5))(
      *((_QWORD *)this + 5),
      L"Error! Out of memory in THashedPKIndexes::FillInTheHashTableForColumnMeta");
    ThrowException(L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\thashedpkindexes.cpp", L"OUT OF MEMORY", 0x7Cu, 0);
  }
  try
  {
    *v4 = -1;
    v7 = 0;
    while ( (unsigned int)v7 < v2 )
    {
      if ( TColumnMeta::Get_Table((TColumnMeta *)&v20) == Table )
      {
        v6 = -1;
      }
      else
      {
        Table = TColumnMeta::Get_Table((TColumnMeta *)&v20);
        v6 = Hash(Table, 0);
      }
      v5[v7] = v6;
      v7 = (unsigned int)(v7 + 1);
      TMetaTable<QueryMetaPublic>::Next(&v20);
    }
    LODWORD(v22) = HIDWORD(v22);
    v5[0x2000] = -1;
    for ( i = 0; i < v2; ++i )
    {
      if ( TColumnMeta::Get_Index((TColumnMeta *)&v20) )
      {
        v10 = TColumnMeta::Get_Table((TColumnMeta *)&v20);
        v11 = Hash(v10, 0);
        Index = TColumnMeta::Get_Index((TColumnMeta *)&v20);
        v9 = *((_DWORD *)c_rgulHashTable + ((unsigned __int64)HIWORD(*Index) >> 8))
           ^ __ROL4__(
               *((_DWORD *)c_rgulHashTable + (unsigned __int8)BYTE2(*Index))
             ^ __ROL4__(
                 *((_DWORD *)c_rgulHashTable + ((unsigned __int64)*(unsigned __int16 *)Index >> 8))
               ^ __ROL4__(*((_DWORD *)c_rgulHashTable + *(unsigned __int8 *)Index) ^ __ROL4__(v11, 1), 1),
                 1),
               1);
      }
      else
      {
        v9 = -1;
      }
      v5[i + 0x2000] = v9;
      TMetaTable<QueryMetaPublic>::Next(&v20);
    }
    v13 = v2
        | (v2 >> 1)
        | ((v2 | (v2 >> 1)) >> 2)
        | ((v2 | (v2 >> 1) | ((v2 | (v2 >> 1)) >> 2)) >> 4)
        | ((v2 | (v2 >> 1) | ((v2 | (v2 >> 1)) >> 2) | ((v2 | (v2 >> 1) | ((v2 | (v2 >> 1)) >> 2)) >> 4)) >> 8)
        | ((v2
          | (v2 >> 1)
          | ((v2 | (v2 >> 1)) >> 2)
          | ((v2 | (v2 >> 1) | ((v2 | (v2 >> 1)) >> 2)) >> 4)
          | ((v2 | (v2 >> 1) | ((v2 | (v2 >> 1)) >> 2) | ((v2 | (v2 >> 1) | ((v2 | (v2 >> 1)) >> 2)) >> 4)) >> 8)) >> 16);
    v14 = v13 == -1;
    v15 = v13 + 1;
    v16 = 0x80000000;
    if ( !v14 )
      v16 = v15;
    v17 = THashedPKIndexes::FillInTheHashTable(this, v2, 2u, (unsigned int (*const)[8192])v5, v16, &v24);
    v18 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *))(**((_QWORD **)this + 4) + 352LL))(
            *((_QWORD *)this + 4),
            L"COLUMNMETA");
    *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 4) + 232LL))(
                  *((_QWORD *)this + 4),
                  v18)
              + 92) = v17;
    (***((void (__fastcall ****)(_QWORD, const wchar_t *, _QWORD))this + 5))(
      *((_QWORD *)this + 5),
      L"\nColumnMeta has %d rows, the hash table has %d elements, %d modulo, %d max chain and %d nonunique entries.\n",
      v2);
  }
  catch ( TException *v19 )
  {
    if ( v25 )
      CoTaskMemFree(v25);
    v23[0] = *(_OWORD *)v19;
    v23[1] = *((_OWORD *)v19 + 1);
    throw (TException *)v23;
  }
  CoTaskMemFree(v5);
}

```

## disassembly

```asm
0x180021084  mov     r11, rsp
0x180021087  mov     [r11+18h], rbx
0x18002108b  mov     [r11+20h], rsi
0x18002108f  push    rdi
0x180021090  push    r14
0x180021092  push    r15
0x180021094  sub     rsp, 80h
0x18002109b  mov     rdi, rcx
0x18002109e  mov     rcx, [rcx+20h]
0x1800210a2  mov     [r11-48h], rcx
0x1800210a6  mov     qword ptr [r11-40h], 0
0x1800210ae  lea     rax, ??_7TColumnMeta@@6B@; const TColumnMeta::`vftable'
0x1800210b5  mov     [r11-50h], rax
0x1800210b9  mov     rax, [rcx]
0x1800210bc  mov     rax, [rax+108h]
0x1800210c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210c8  mov     r15d, eax
0x1800210cb  mov     [rsp+98h+arg_0], 0
0x1800210d6  mov     rcx, [rdi+28h]
0x1800210da  mov     rdx, [rcx]
0x1800210dd  mov     rax, [rdx]
0x1800210e0  lea     rdx, aBuildingColumn; "\nBuilding ColumnMeta hash table"
0x1800210e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210ec  mov     r9d, 2000h
0x1800210f2  cmp     r15d, r9d
0x1800210f5  jbe     short loc_180021130
0x1800210f7  mov     rcx, [rdi+28h]
0x1800210fb  mov     rax, [rcx]
0x1800210fe  mov     r8d, r15d
0x180021101  lea     rdx, aErrorTooManyRo_4; "Error! Too Many Rows - ColumnMeta has %"...
0x180021108  mov     rax, [rax]
0x18002110b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021110  mov     r9d, 0C00210F2h; unsigned int
0x180021116  mov     r8d, 75h ; 'u'; unsigned int
0x18002111c  lea     rdx, aTooManyRowsHas; "TOO MANY ROWS - HASH TABLE GENERATION A"...
0x180021123  lea     rcx, aInetsrvIisMbCo_14; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18002112a  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x180021130  xor     r14d, r14d
0x180021133  mov     ecx, 10000h; cb
0x180021138  call    cs:__imp_CoTaskMemAlloc
0x18002113e  mov     rbx, rax
0x180021141  mov     [rsp+98h+arg_8], rax
0x180021149  test    rax, rax
0x18002114c  jnz     short loc_18002117F
0x18002114e  mov     rcx, [rdi+28h]
0x180021152  mov     rax, [rcx]
0x180021155  lea     rdx, aErrorOutOfMemo_0; "Error! Out of memory in THashedPKIndexe"...
0x18002115c  mov     rax, [rax]
0x18002115f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021164  xor     r9d, r9d; unsigned int
0x180021167  lea     r8d, [r14+7Ch]; unsigned int
0x18002116b  lea     rdx, aOutOfMemory; "OUT OF MEMORY"
0x180021172  lea     rcx, aInetsrvIisMbCo_14; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180021179  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18002117f  mov     dword ptr [rax], 0FFFFFFFFh
0x180021185  xor     esi, esi
0x180021187  cmp     esi, r15d
0x18002118a  jnb     short loc_1800211C8
0x18002118c  lea     rcx, [rsp+98h+var_50]; this
0x180021191  call    ?Get_Table@TColumnMeta@@QEBAPEBGXZ; TColumnMeta::Get_Table(void)
0x180021196  cmp     rax, r14
0x180021199  jnz     short loc_1800211A0
0x18002119b  or      eax, 0FFFFFFFFh
0x18002119e  jmp     short loc_1800211B7
0x1800211a0  lea     rcx, [rsp+98h+var_50]; this
0x1800211a5  call    ?Get_Table@TColumnMeta@@QEBAPEBGXZ; TColumnMeta::Get_Table(void)
0x1800211aa  mov     r14, rax
0x1800211ad  xor     edx, edx; unsigned int
0x1800211af  mov     rcx, rax; unsigned __int16 *
0x1800211b2  call    ?Hash@@YAKPEBGK@Z; Hash(ushort const *,ulong)
0x1800211b7  mov     [rbx+rsi*4], eax
0x1800211ba  inc     esi
0x1800211bc  lea     rcx, [rsp+98h+var_50]
0x1800211c1  call    ?Next@?$TMetaTable@UQueryMetaPublic@@@@UEAA_NXZ; TMetaTable<QueryMetaPublic>::Next(void)
0x1800211c6  jmp     short loc_180021187
0x1800211c8  mov     eax, [rsp+98h+var_3C]
0x1800211cc  mov     [rsp+98h+var_40], eax
0x1800211d0  mov     dword ptr [rbx+8000h], 0FFFFFFFFh
0x1800211da  xor     r14d, r14d
0x1800211dd  cmp     r14d, r15d
0x1800211e0  jnb     loc_180021271
0x1800211e6  lea     rcx, [rsp+98h+var_50]; this
0x1800211eb  call    ?Get_Index@TColumnMeta@@QEBAPEBKXZ; TColumnMeta::Get_Index(void)
0x1800211f0  test    rax, rax
0x1800211f3  jnz     short loc_1800211FA
0x1800211f5  or      esi, 0FFFFFFFFh
0x1800211f8  jmp     short loc_180021252
0x1800211fa  lea     rcx, [rsp+98h+var_50]; this
0x1800211ff  call    ?Get_Table@TColumnMeta@@QEBAPEBGXZ; TColumnMeta::Get_Table(void)
0x180021204  xor     edx, edx; unsigned int
0x180021206  mov     rcx, rax; unsigned __int16 *
0x180021209  call    ?Hash@@YAKPEBGK@Z; Hash(ushort const *,ulong)
0x18002120e  mov     esi, eax
0x180021210  lea     rcx, [rsp+98h+var_50]; this
0x180021215  call    ?Get_Index@TColumnMeta@@QEBAPEBKXZ; TColumnMeta::Get_Index(void)
0x18002121a  mov     edx, [rax]
0x18002121c  shr     edx, 10h
0x18002121f  rol     esi, 1
0x180021221  movzx   ecx, byte ptr [rax]
0x180021224  lea     r8, c_rgulHashTable
0x18002122b  xor     esi, [r8+rcx*4]
0x18002122f  rol     esi, 1
0x180021231  movzx   eax, word ptr [rax]
0x180021234  shr     rax, 8
0x180021238  xor     esi, [r8+rax*4]
0x18002123c  rol     esi, 1
0x18002123e  movzx   eax, dl
0x180021241  xor     esi, [r8+rax*4]
0x180021245  rol     esi, 1
0x180021247  movzx   eax, dx
0x18002124a  shr     rax, 8
0x18002124e  xor     esi, [r8+rax*4]
0x180021252  mov     eax, r14d
0x180021255  mov     rcx, rbx
0x180021258  mov     [rbx+rax*4+8000h], esi
0x18002125f  inc     r14d
0x180021262  lea     rcx, [rsp+98h+var_50]
0x180021267  call    ?Next@?$TMetaTable@UQueryMetaPublic@@@@UEAA_NXZ; TMetaTable<QueryMetaPublic>::Next(void)
0x18002126c  jmp     loc_1800211DD
0x180021271  mov     eax, r15d
0x180021274  shr     eax, 1
0x180021276  or      eax, r15d
0x180021279  mov     ecx, eax
0x18002127b  shr     ecx, 2
0x18002127e  or      ecx, eax
0x180021280  mov     eax, ecx
0x180021282  shr     eax, 4
0x180021285  or      eax, ecx
0x180021287  mov     ecx, eax
0x180021289  shr     ecx, 8
0x18002128c  or      ecx, eax
0x18002128e  mov     eax, ecx
0x180021290  shr     eax, 10h
0x180021293  or      eax, ecx
0x180021295  add     eax, 1
0x180021298  mov     esi, 80000000h
0x18002129d  cmovnz  esi, eax
0x1800212a0  lea     rax, [rsp+98h+arg_0]
0x1800212a8  mov     [rsp+98h+var_70], rax; unsigned int *
0x1800212ad  mov     [rsp+98h+var_78], esi; unsigned int
0x1800212b1  mov     r9, rbx; unsigned int (*)[8192]
0x1800212b4  mov     r8d, 2; unsigned int
0x1800212ba  mov     edx, r15d; unsigned int
0x1800212bd  mov     rcx, rdi; this
0x1800212c0  call    ?FillInTheHashTable@THashedPKIndexes@@AEAAKKKQEAY0CAAA@KKPEAK@Z; THashedPKIndexes::FillInTheHashTable(ulong,ulong,ulong (* const)[8192],ulong,ulong *)
0x1800212c5  mov     r14d, eax
0x1800212c8  mov     rcx, [rdi+20h]
0x1800212cc  mov     rdx, [rcx]
0x1800212cf  mov     rax, [rdx+160h]
0x1800212d6  lea     rdx, aColumnmeta; "COLUMNMETA"
0x1800212dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212e2  mov     r8d, eax
0x1800212e5  mov     rcx, [rdi+20h]
0x1800212e9  mov     rdx, [rcx]
0x1800212ec  mov     rax, [rdx+0E8h]
0x1800212f3  mov     edx, r8d
0x1800212f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212fb  mov     [rax+5Ch], r14d
0x1800212ff  mov     r8, [rdi+10h]
0x180021303  mov     rcx, [rdi+28h]
0x180021307  mov     r9d, [r8+r14*8+4]
0x18002130c  mov     rax, [rcx]
0x18002130f  mov     edx, r9d
0x180021312  sub     edx, [r8+r14*8]
0x180021316  mov     [rsp+98h+var_68], edx
0x18002131a  mov     edx, [rsp+98h+arg_0]
0x180021321  mov     dword ptr [rsp+98h+var_70], edx
0x180021325  mov     [rsp+98h+var_78], esi
0x180021329  mov     r8d, r15d
0x18002132c  lea     rdx, aColumnmetaHasD; "\nColumnMeta has %d rows, the hash tabl"...
0x180021333  mov     rax, [rax]
0x180021336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002133b  nop
0x18002133c  mov     rcx, rbx; pv
0x18002133f  call    cs:__imp_CoTaskMemFree
0x180021345  nop
0x180021346  lea     r11, [rsp+98h+var_18]
0x18002134e  mov     rbx, [r11+30h]
0x180021352  mov     rsi, [r11+38h]
0x180021356  mov     rsp, r11
0x180021359  pop     r15
0x18002135b  pop     r14
0x18002135d  pop     rdi
0x18002135e  retn
```
