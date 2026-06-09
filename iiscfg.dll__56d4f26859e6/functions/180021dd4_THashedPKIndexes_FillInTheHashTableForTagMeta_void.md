# THashedPKIndexes::FillInTheHashTableForTagMeta(void)

- ea: `0x180021dd4`
- end: `0x18002217c`
- name: `?FillInTheHashTableForTagMeta@THashedPKIndexes@@AEAAXXZ`
- size: `936`
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
- `0x180021dd4`
- `0x1800222a4`
- `0x1800223e4`
- `0x180022540`
- `0x180022600`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180022158`
- `ole32!CoTaskMemFree` at `0x180022158`
- `ole32!CoTaskMemAlloc` at `0x180021e90`
- `ole32!CoTaskMemAlloc` at `0x180021e90`

## string_xrefs

- `0x180021e74`: `inetsrv\iis\mb\config\src\core\schemagen\thashedpkindexes.cpp`
- `0x180021ecc`: `inetsrv\iis\mb\config\src\core\schemagen\thashedpkindexes.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall THashedPKIndexes::FillInTheHashTableForTagMeta(THashedPKIndexes *this)
{
  unsigned int v2; // r14d
  const unsigned __int16 *Table; // r15
  int v4; // r13d
  unsigned int *v5; // rax
  unsigned int *v6; // rbx
  unsigned int v7; // eax
  __int64 v8; // rdi
  const unsigned __int16 *v9; // r12
  unsigned int i; // r15d
  int v11; // edi
  unsigned int v12; // edi
  const unsigned int *ColumnIndex; // rax
  __int64 v14; // r15
  const unsigned __int16 *v15; // rax
  unsigned int v16; // edi
  const unsigned int *v17; // rax
  unsigned int v18; // edi
  const unsigned __int16 *InternalName; // rax
  unsigned int v20; // eax
  bool v21; // zf
  unsigned int v22; // eax
  unsigned int v23; // edi
  unsigned int v24; // r15d
  unsigned int v25; // eax
  TException *v26; // [rsp+40h] [rbp-68h] BYREF
  void **v27; // [rsp+48h] [rbp-60h] BYREF
  __int64 v28; // [rsp+50h] [rbp-58h]
  __int64 v29; // [rsp+58h] [rbp-50h]
  _OWORD v30[2]; // [rsp+60h] [rbp-48h] BYREF
  unsigned int v31; // [rsp+B0h] [rbp+8h] BYREF
  unsigned int *v32; // [rsp+B8h] [rbp+10h]

  v28 = *((_QWORD *)this + 4);
  v29 = 0;
  v27 = &TTagMeta::`vftable';
  v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 328LL))(v28);
  v31 = 1;
  (***((void (__fastcall ****)(_QWORD, const wchar_t *))this + 5))(
    *((_QWORD *)this + 5),
    L"\nBuilding TagMeta hash table");
  if ( v2 > 0x2000 )
  {
    (***((void (__fastcall ****)(_QWORD, const wchar_t *, _QWORD))this + 5))(
      *((_QWORD *)this + 5),
      L"Error! Too Many Rows - TagMeta has %d rows, Hash table generation relies on fixed tables being less than %d rows\n",
      v2);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\thashedpkindexes.cpp",
      L"TOO MANY ROWS - HASH TABLE GENERATION ASSUMES FIXED TABLES ARE RELATIVELY SMALL",
      0x1F6u,
      0);
  }
  Table = 0;
  v4 = -1;
  v5 = (unsigned int *)CoTaskMemAlloc(0x18000u);
  v6 = v5;
  v32 = v5;
  if ( !v5 )
  {
    (***((void (__fastcall ****)(_QWORD, const wchar_t *))this + 5))(
      *((_QWORD *)this + 5),
      L"Error! Out of memory in THashedPKIndexes::FillInTheHashTableForTableMeta");
    ThrowException(L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\thashedpkindexes.cpp", L"OUT OF MEMORY", 0x1FDu, 0);
  }
  try
  {
    *v5 = -1;
    v8 = 0;
    while ( (unsigned int)v8 < v2 )
    {
      if ( TTagMeta::Get_Table((TTagMeta *)&v27) == Table )
      {
        v7 = -1;
      }
      else
      {
        Table = TTagMeta::Get_Table((TTagMeta *)&v27);
        v7 = Hash(Table, 0);
      }
      v6[v8] = v7;
      v8 = (unsigned int)(v8 + 1);
      TMetaTable<QueryMetaPublic>::Next(&v27);
    }
    LODWORD(v29) = HIDWORD(v29);
    v9 = 0;
    v6[0x2000] = -1;
    for ( i = 0; i < v2; ++i )
    {
      if ( TTagMeta::Get_Table((TTagMeta *)&v27) == v9 && *TTagMeta::Get_ColumnIndex((TTagMeta *)&v27) == v4 )
      {
        v11 = -1;
      }
      else
      {
        v9 = TTagMeta::Get_Table((TTagMeta *)&v27);
        v12 = Hash(v9, 0);
        ColumnIndex = TTagMeta::Get_ColumnIndex((TTagMeta *)&v27);
        v4 = *ColumnIndex;
        v11 = *((_DWORD *)c_rgulHashTable + ((unsigned __int64)HIWORD(*ColumnIndex) >> 8))
            ^ __ROL4__(
                *((_DWORD *)c_rgulHashTable + (unsigned __int8)BYTE2(*ColumnIndex))
              ^ __ROL4__(
                  *((_DWORD *)c_rgulHashTable + ((unsigned __int64)(unsigned __int16)v4 >> 8))
                ^ __ROL4__(*((_DWORD *)c_rgulHashTable + (unsigned __int8)v4) ^ __ROL4__(v12, 1), 1),
                  1),
                1);
      }
      v6[i + 0x2000] = v11;
      TMetaTable<QueryMetaPublic>::Next(&v27);
    }
    LODWORD(v29) = HIDWORD(v29);
    v6[0x4000] = -1;
    v14 = 0;
    while ( (unsigned int)v14 < v2 )
    {
      v15 = TTagMeta::Get_Table((TTagMeta *)&v27);
      v16 = Hash(v15, 0);
      v17 = TTagMeta::Get_ColumnIndex((TTagMeta *)&v27);
      v18 = *((_DWORD *)c_rgulHashTable + ((unsigned __int64)HIWORD(*v17) >> 8))
          ^ __ROL4__(
              *((_DWORD *)c_rgulHashTable + (unsigned __int8)BYTE2(*v17))
            ^ __ROL4__(
                *((_DWORD *)c_rgulHashTable + ((unsigned __int64)*(unsigned __int16 *)v17 >> 8))
              ^ __ROL4__(*((_DWORD *)c_rgulHashTable + *(unsigned __int8 *)v17) ^ __ROL4__(v16, 1), 1),
                1),
              1);
      InternalName = TTagMeta::Get_InternalName((TTagMeta *)&v27);
      v6[v14 + 0x4000] = Hash(InternalName, v18);
      v14 = (unsigned int)(v14 + 1);
      TMetaTable<QueryMetaPublic>::Next(&v27);
    }
    v20 = v2
        | (v2 >> 1)
        | ((v2 | (v2 >> 1)) >> 2)
        | ((v2 | (v2 >> 1) | ((v2 | (v2 >> 1)) >> 2)) >> 4)
        | ((v2 | (v2 >> 1) | ((v2 | (v2 >> 1)) >> 2) | ((v2 | (v2 >> 1) | ((v2 | (v2 >> 1)) >> 2)) >> 4)) >> 8)
        | ((v2
          | (v2 >> 1)
          | ((v2 | (v2 >> 1)) >> 2)
          | ((v2 | (v2 >> 1) | ((v2 | (v2 >> 1)) >> 2)) >> 4)
          | ((v2 | (v2 >> 1) | ((v2 | (v2 >> 1)) >> 2) | ((v2 | (v2 >> 1) | ((v2 | (v2 >> 1)) >> 2)) >> 4)) >> 8)) >> 16);
    v21 = v20 == -1;
    v22 = v20 + 1;
    v23 = 0x80000000;
    if ( !v21 )
      v23 = v22;
    v24 = THashedPKIndexes::FillInTheHashTable(this, v2, 3u, (unsigned int (*const)[8192])v6, v23, &v31);
    v25 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *))(**((_QWORD **)this + 4) + 352LL))(
            *((_QWORD *)this + 4),
            L"TAGMETA");
    *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 4) + 232LL))(
                  *((_QWORD *)this + 4),
                  v25)
              + 92) = v24;
    (***((void (__fastcall ****)(_QWORD, const wchar_t *, _QWORD))this + 5))(
      *((_QWORD *)this + 5),
      L"\nTagMeta has %d rows, the hash table has %d elements, %d modulo, %d max chain and %d nonunique entries.\n",
      v2);
  }
  catch ( TException *v26 )
  {
    if ( v32 )
      CoTaskMemFree(v32);
    v30[0] = *(_OWORD *)v26;
    v30[1] = *((_OWORD *)v26 + 1);
    throw (TException *)v30;
  }
  CoTaskMemFree(v6);
}

```

## disassembly

```asm
0x180021dd4  mov     r11, rsp
0x180021dd7  mov     [r11+18h], rbx
0x180021ddb  mov     [r11+20h], rsi
0x180021ddf  push    rdi
0x180021de0  push    r12
0x180021de2  push    r13
0x180021de4  push    r14
0x180021de6  push    r15
0x180021de8  sub     rsp, 80h
0x180021def  mov     rsi, rcx
0x180021df2  mov     rcx, [rcx+20h]
0x180021df6  mov     [r11-58h], rcx
0x180021dfa  mov     qword ptr [r11-50h], 0
0x180021e02  lea     rax, ??_7TTagMeta@@6B@; const TTagMeta::`vftable'
0x180021e09  mov     [r11-60h], rax
0x180021e0d  mov     rax, [rcx]
0x180021e10  mov     rax, [rax+148h]
0x180021e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e1c  mov     r14d, eax
0x180021e1f  mov     [rsp+0A8h+arg_0], 1
0x180021e2a  mov     rcx, [rsi+28h]
0x180021e2e  mov     rdx, [rcx]
0x180021e31  mov     rax, [rdx]
0x180021e34  lea     rdx, aBuildingTagmet; "\nBuilding TagMeta hash table"
0x180021e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e40  mov     r9d, 2000h
0x180021e46  cmp     r14d, r9d
0x180021e49  jbe     short loc_180021E81
0x180021e4b  mov     rcx, [rsi+28h]
0x180021e4f  mov     rax, [rcx]
0x180021e52  mov     r8d, r14d
0x180021e55  lea     rdx, aErrorTooManyRo; "Error! Too Many Rows - TagMeta has %d r"...
0x180021e5c  mov     rax, [rax]
0x180021e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e64  xor     r9d, r9d; unsigned int
0x180021e67  mov     r8d, 1F6h; unsigned int
0x180021e6d  lea     rdx, aTooManyRowsHas; "TOO MANY ROWS - HASH TABLE GENERATION A"...
0x180021e74  lea     rcx, aInetsrvIisMbCo_14; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180021e7b  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x180021e81  xor     r15d, r15d
0x180021e84  or      r12d, 0FFFFFFFFh
0x180021e88  mov     r13d, r12d
0x180021e8b  mov     ecx, 18000h; cb
0x180021e90  call    cs:__imp_CoTaskMemAlloc
0x180021e96  mov     rbx, rax
0x180021e99  mov     [rsp+0A8h+arg_8], rax
0x180021ea1  test    rax, rax
0x180021ea4  jnz     short loc_180021ED9
0x180021ea6  mov     rcx, [rsi+28h]
0x180021eaa  mov     rax, [rcx]
0x180021ead  lea     rdx, aErrorOutOfMemo_3; "Error! Out of memory in THashedPKIndexe"...
0x180021eb4  mov     rax, [rax]
0x180021eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ebc  xor     r9d, r9d; unsigned int
0x180021ebf  mov     r8d, 1FDh; unsigned int
0x180021ec5  lea     rdx, aOutOfMemory; "OUT OF MEMORY"
0x180021ecc  lea     rcx, aInetsrvIisMbCo_14; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180021ed3  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x180021ed9  mov     [rax], r12d
0x180021edc  xor     edi, edi
0x180021ede  cmp     edi, r14d
0x180021ee1  jnb     short loc_180021F1F
0x180021ee3  lea     rcx, [rsp+0A8h+var_60]; this
0x180021ee8  call    ?Get_Table@TTagMeta@@QEBAPEBGXZ; TTagMeta::Get_Table(void)
0x180021eed  cmp     rax, r15
0x180021ef0  jnz     short loc_180021EF7
0x180021ef2  mov     eax, r12d
0x180021ef5  jmp     short loc_180021F0E
0x180021ef7  lea     rcx, [rsp+0A8h+var_60]; this
0x180021efc  call    ?Get_Table@TTagMeta@@QEBAPEBGXZ; TTagMeta::Get_Table(void)
0x180021f01  mov     r15, rax
0x180021f04  xor     edx, edx; unsigned int
0x180021f06  mov     rcx, rax; unsigned __int16 *
0x180021f09  call    ?Hash@@YAKPEBGK@Z; Hash(ushort const *,ulong)
0x180021f0e  mov     [rbx+rdi*4], eax
0x180021f11  inc     edi
0x180021f13  lea     rcx, [rsp+0A8h+var_60]
0x180021f18  call    ?Next@?$TMetaTable@UQueryMetaPublic@@@@UEAA_NXZ; TMetaTable<QueryMetaPublic>::Next(void)
0x180021f1d  jmp     short loc_180021EDE
0x180021f1f  mov     eax, [rsp+0A8h+var_4C]
0x180021f23  mov     [rsp+0A8h+var_50], eax
0x180021f27  xor     r12d, r12d
0x180021f2a  mov     dword ptr [rbx+8000h], 0FFFFFFFFh
0x180021f34  xor     r15d, r15d
0x180021f37  cmp     r15d, r14d
0x180021f3a  jnb     loc_180021FE3
0x180021f40  lea     rcx, [rsp+0A8h+var_60]; this
0x180021f45  call    ?Get_Table@TTagMeta@@QEBAPEBGXZ; TTagMeta::Get_Table(void)
0x180021f4a  cmp     rax, r12
0x180021f4d  jnz     short loc_180021F63
0x180021f4f  lea     rcx, [rsp+0A8h+var_60]; this
0x180021f54  call    ?Get_ColumnIndex@TTagMeta@@QEBAPEBKXZ; TTagMeta::Get_ColumnIndex(void)
0x180021f59  cmp     [rax], r13d
0x180021f5c  jnz     short loc_180021F63
0x180021f5e  or      edi, 0FFFFFFFFh
0x180021f61  jmp     short loc_180021FC4
0x180021f63  lea     rcx, [rsp+0A8h+var_60]; this
0x180021f68  call    ?Get_Table@TTagMeta@@QEBAPEBGXZ; TTagMeta::Get_Table(void)
0x180021f6d  mov     r12, rax
0x180021f70  xor     edx, edx; unsigned int
0x180021f72  mov     rcx, rax; unsigned __int16 *
0x180021f75  call    ?Hash@@YAKPEBGK@Z; Hash(ushort const *,ulong)
0x180021f7a  mov     edi, eax
0x180021f7c  lea     rcx, [rsp+0A8h+var_60]; this
0x180021f81  call    ?Get_ColumnIndex@TTagMeta@@QEBAPEBKXZ; TTagMeta::Get_ColumnIndex(void)
0x180021f86  mov     r13d, [rax]
0x180021f89  mov     edx, r13d
0x180021f8c  shr     edx, 10h
0x180021f8f  rol     edi, 1
0x180021f91  movzx   ecx, r13b
0x180021f95  lea     r8, c_rgulHashTable
0x180021f9c  xor     edi, [r8+rcx*4]
0x180021fa0  rol     edi, 1
0x180021fa2  movzx   eax, r13w
0x180021fa6  shr     rax, 8
0x180021faa  xor     edi, [r8+rax*4]
0x180021fae  rol     edi, 1
0x180021fb0  movzx   eax, dl
0x180021fb3  xor     edi, [r8+rax*4]
0x180021fb7  rol     edi, 1
0x180021fb9  movzx   eax, dx
0x180021fbc  shr     rax, 8
0x180021fc0  xor     edi, [r8+rax*4]
0x180021fc4  mov     eax, r15d
0x180021fc7  mov     rcx, rbx
0x180021fca  mov     [rbx+rax*4+8000h], edi
0x180021fd1  inc     r15d
0x180021fd4  lea     rcx, [rsp+0A8h+var_60]
0x180021fd9  call    ?Next@?$TMetaTable@UQueryMetaPublic@@@@UEAA_NXZ; TMetaTable<QueryMetaPublic>::Next(void)
0x180021fde  jmp     loc_180021F37
0x180021fe3  mov     eax, [rsp+0A8h+var_4C]
0x180021fe7  mov     [rsp+0A8h+var_50], eax
0x180021feb  mov     dword ptr [rbx+10000h], 0FFFFFFFFh
0x180021ff5  xor     r15d, r15d
0x180021ff8  cmp     r15d, r14d
0x180021ffb  jnb     loc_18002208A
0x180022001  lea     rcx, [rsp+0A8h+var_60]; this
0x180022006  call    ?Get_Table@TTagMeta@@QEBAPEBGXZ; TTagMeta::Get_Table(void)
0x18002200b  xor     edx, edx; unsigned int
0x18002200d  mov     rcx, rax; unsigned __int16 *
0x180022010  call    ?Hash@@YAKPEBGK@Z; Hash(ushort const *,ulong)
0x180022015  mov     edi, eax
0x180022017  lea     rcx, [rsp+0A8h+var_60]; this
0x18002201c  call    ?Get_ColumnIndex@TTagMeta@@QEBAPEBKXZ; TTagMeta::Get_ColumnIndex(void)
0x180022021  mov     rdx, rax
0x180022024  mov     ecx, [rax]
0x180022026  shr     ecx, 10h
0x180022029  rol     edi, 1
0x18002202b  movzx   eax, byte ptr [rax]
0x18002202e  lea     r8, c_rgulHashTable
0x180022035  xor     edi, [r8+rax*4]
0x180022039  rol     edi, 1
0x18002203b  movzx   eax, word ptr [rdx]
0x18002203e  shr     rax, 8
0x180022042  xor     edi, [r8+rax*4]
0x180022046  rol     edi, 1
0x180022048  movzx   eax, cl
0x18002204b  xor     edi, [r8+rax*4]
0x18002204f  rol     edi, 1
0x180022051  movzx   eax, cx
0x180022054  shr     rax, 8
0x180022058  xor     edi, [r8+rax*4]
0x18002205c  lea     rcx, [rsp+0A8h+var_60]; this
0x180022061  call    ?Get_InternalName@TTagMeta@@QEBAPEBGXZ; TTagMeta::Get_InternalName(void)
0x180022066  mov     edx, edi; unsigned int
0x180022068  mov     rcx, rax; unsigned __int16 *
0x18002206b  call    ?Hash@@YAKPEBGK@Z; Hash(ushort const *,ulong)
0x180022070  mov     [rbx+r15*4+10000h], eax
0x180022078  inc     r15d
0x18002207b  lea     rcx, [rsp+0A8h+var_60]
0x180022080  call    ?Next@?$TMetaTable@UQueryMetaPublic@@@@UEAA_NXZ; TMetaTable<QueryMetaPublic>::Next(void)
0x180022085  jmp     loc_180021FF8
0x18002208a  mov     eax, r14d
0x18002208d  shr     eax, 1
0x18002208f  or      eax, r14d
0x180022092  mov     ecx, eax
0x180022094  shr     ecx, 2
0x180022097  or      ecx, eax
0x180022099  mov     eax, ecx
0x18002209b  shr     eax, 4
0x18002209e  or      eax, ecx
0x1800220a0  mov     ecx, eax
0x1800220a2  shr     ecx, 8
0x1800220a5  or      ecx, eax
0x1800220a7  mov     eax, ecx
0x1800220a9  shr     eax, 10h
0x1800220ac  or      eax, ecx
0x1800220ae  add     eax, 1
0x1800220b1  mov     edi, 80000000h
0x1800220b6  cmovnz  edi, eax
0x1800220b9  lea     rax, [rsp+0A8h+arg_0]
0x1800220c1  mov     [rsp+0A8h+var_80], rax; unsigned int *
0x1800220c6  mov     [rsp+0A8h+var_88], edi; unsigned int
0x1800220ca  mov     r9, rbx; unsigned int (*)[8192]
0x1800220cd  mov     r8d, 3; unsigned int
0x1800220d3  mov     edx, r14d; unsigned int
0x1800220d6  mov     rcx, rsi; this
0x1800220d9  call    ?FillInTheHashTable@THashedPKIndexes@@AEAAKKKQEAY0CAAA@KKPEAK@Z; THashedPKIndexes::FillInTheHashTable(ulong,ulong,ulong (* const)[8192],ulong,ulong *)
0x1800220de  mov     r15d, eax
0x1800220e1  mov     rcx, [rsi+20h]
0x1800220e5  mov     rdx, [rcx]
0x1800220e8  mov     rax, [rdx+160h]
0x1800220ef  lea     rdx, aTagmeta; "TAGMETA"
0x1800220f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220fb  mov     r8d, eax
0x1800220fe  mov     rcx, [rsi+20h]
0x180022102  mov     rdx, [rcx]
0x180022105  mov     rax, [rdx+0E8h]
0x18002210c  mov     edx, r8d
0x18002210f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022114  mov     [rax+5Ch], r15d
0x180022118  mov     r8, [rsi+10h]
0x18002211c  mov     rcx, [rsi+28h]
0x180022120  mov     r9d, [r8+r15*8+4]
0x180022125  mov     rax, [rcx]
0x180022128  mov     edx, r9d
0x18002212b  sub     edx, [r8+r15*8]
0x18002212f  mov     [rsp+0A8h+var_78], edx
0x180022133  mov     edx, [rsp+0A8h+arg_0]
0x18002213a  mov     dword ptr [rsp+0A8h+var_80], edx
0x18002213e  mov     [rsp+0A8h+var_88], edi
0x180022142  mov     r8d, r14d
0x180022145  lea     rdx, aTagmetaHasDRow; "\nTagMeta has %d rows, the hash table h"...
0x18002214c  mov     rax, [rax]
0x18002214f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022154  nop
0x180022155  mov     rcx, rbx; pv
0x180022158  call    cs:__imp_CoTaskMemFree
0x18002215e  nop
0x18002215f  lea     r11, [rsp+0A8h+var_28]
0x180022167  mov     rbx, [r11+40h]
0x18002216b  mov     rsi, [r11+48h]
0x18002216f  mov     rsp, r11
0x180022172  pop     r15
0x180022174  pop     r14
0x180022176  pop     r13
0x180022178  pop     r12
0x18002217a  pop     rdi
0x18002217b  retn
```
