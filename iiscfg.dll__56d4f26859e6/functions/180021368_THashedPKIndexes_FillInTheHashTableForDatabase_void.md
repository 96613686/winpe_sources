# THashedPKIndexes::FillInTheHashTableForDatabase(void)

- ea: `0x180021368`
- end: `0x180021581`
- name: `?FillInTheHashTableForDatabase@THashedPKIndexes@@AEAAXXZ`
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
- `0x180021368`
- `0x18002231c`
- `0x180022600`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180021561`
- `ole32!CoTaskMemFree` at `0x180021561`
- `ole32!CoTaskMemAlloc` at `0x180021416`
- `ole32!CoTaskMemAlloc` at `0x180021416`

## string_xrefs

- `0x180021404`: `inetsrv\iis\mb\config\src\core\schemagen\thashedpkindexes.cpp`
- `0x180021452`: `inetsrv\iis\mb\config\src\core\schemagen\thashedpkindexes.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall THashedPKIndexes::FillInTheHashTableForDatabase(THashedPKIndexes *this)
{
  unsigned int v2; // r14d
  unsigned int *v3; // rax
  unsigned int *v4; // rdi
  const unsigned __int16 *InternalName; // rax
  __int64 v6; // rsi
  unsigned int v7; // eax
  bool v8; // zf
  unsigned int v9; // eax
  unsigned int v10; // r15d
  unsigned int v11; // esi
  unsigned int v12; // eax
  TException *v13; // [rsp+40h] [rbp-58h] BYREF
  void **v14; // [rsp+48h] [rbp-50h] BYREF
  __int64 v15; // [rsp+50h] [rbp-48h]
  __int64 v16; // [rsp+58h] [rbp-40h]
  _OWORD v17[2]; // [rsp+60h] [rbp-38h] BYREF
  unsigned int v18; // [rsp+A0h] [rbp+8h] BYREF
  unsigned int *v19; // [rsp+A8h] [rbp+10h]

  v15 = *((_QWORD *)this + 4);
  v16 = 0;
  v14 = &TDatabaseMeta::`vftable';
  v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 272LL))(v15);
  v18 = 1;
  (***((void (__fastcall ****)(_QWORD, const wchar_t *))this + 5))(
    *((_QWORD *)this + 5),
    L"\nBuilding DatabaseMeta hash table");
  if ( v2 > 0x2000 )
  {
    (***((void (__fastcall ****)(_QWORD, const wchar_t *, _QWORD))this + 5))(
      *((_QWORD *)this + 5),
      L"Error! Too Many Rows - DatabaseMeta has %d rows, Hash table generation relies on fixed tables being less than %d rows\n",
      v2);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\thashedpkindexes.cpp",
      L"TOO MANY ROWS - HASH TABLE GENERATION ASSUMES FIXED TABLES ARE RELATIVELY SMALL",
      0xC5u,
      0);
  }
  v3 = (unsigned int *)CoTaskMemAlloc(0x8000u);
  v4 = v3;
  v19 = v3;
  if ( !v3 )
  {
    (***((void (__fastcall ****)(_QWORD, const wchar_t *))this + 5))(
      *((_QWORD *)this + 5),
      L"Error! Out of memory in THashedPKIndexes::FillInTheHashTableForDatabase");
    ThrowException(L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\thashedpkindexes.cpp", L"OUT OF MEMORY", 0xCCu, 0);
  }
  try
  {
    *v3 = -1;
    v6 = 0;
    while ( (unsigned int)v6 < v2 )
    {
      InternalName = TDatabaseMeta::Get_InternalName((TDatabaseMeta *)&v14);
      v4[v6] = Hash(InternalName, 0);
      v6 = (unsigned int)(v6 + 1);
      TMetaTable<QueryMetaPublic>::Next(&v14);
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
    v11 = THashedPKIndexes::FillInTheHashTable(this, v2, 1u, (unsigned int (*const)[8192])v4, v10, &v18);
    v12 = (*(__int64 (__fastcall **)(_QWORD, const WCHAR *))(**((_QWORD **)this + 4) + 352LL))(
            *((_QWORD *)this + 4),
            L"DATABASEMETA");
    *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 4) + 232LL))(
                  *((_QWORD *)this + 4),
                  v12)
              + 92) = v11;
    (***((void (__fastcall ****)(_QWORD, const wchar_t *, _QWORD))this + 5))(
      *((_QWORD *)this + 5),
      L"\nDatabaseMeta has %d rows, the hash table has %d elements, %d modulo, %d max chain and %d nonunique entries.\n",
      v2);
  }
  catch ( TException *v13 )
  {
    if ( v19 )
      CoTaskMemFree(v19);
    v17[0] = *(_OWORD *)v13;
    v17[1] = *((_OWORD *)v13 + 1);
    throw (TException *)v17;
  }
  CoTaskMemFree(v4);
}

```

## disassembly

```asm
0x180021368  mov     r11, rsp
0x18002136b  mov     [r11+18h], rbx
0x18002136f  mov     [r11+20h], rsi
0x180021373  push    rdi
0x180021374  push    r14
0x180021376  push    r15
0x180021378  sub     rsp, 80h
0x18002137f  mov     rbx, rcx
0x180021382  mov     rcx, [rcx+20h]
0x180021386  mov     [r11-48h], rcx
0x18002138a  mov     qword ptr [r11-40h], 0
0x180021392  lea     rax, ??_7TDatabaseMeta@@6B@; const TDatabaseMeta::`vftable'
0x180021399  mov     [r11-50h], rax
0x18002139d  mov     rax, [rcx]
0x1800213a0  mov     rax, [rax+110h]
0x1800213a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213ac  mov     r14d, eax
0x1800213af  mov     [rsp+98h+arg_0], 1
0x1800213ba  mov     rcx, [rbx+28h]
0x1800213be  mov     rdx, [rcx]
0x1800213c1  mov     rax, [rdx]
0x1800213c4  lea     rdx, aBuildingDataba; "\nBuilding DatabaseMeta hash table"
0x1800213cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213d0  mov     r9d, 2000h
0x1800213d6  cmp     r14d, r9d
0x1800213d9  jbe     short loc_180021411
0x1800213db  mov     rcx, [rbx+28h]
0x1800213df  mov     rax, [rcx]
0x1800213e2  mov     r8d, r14d
0x1800213e5  lea     rdx, aErrorTooManyRo_1; "Error! Too Many Rows - DatabaseMeta has"...
0x1800213ec  mov     rax, [rax]
0x1800213ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213f4  xor     r9d, r9d; unsigned int
0x1800213f7  mov     r8d, 0C5h; unsigned int
0x1800213fd  lea     rdx, aTooManyRowsHas; "TOO MANY ROWS - HASH TABLE GENERATION A"...
0x180021404  lea     rcx, aInetsrvIisMbCo_14; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18002140b  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x180021411  mov     ecx, 8000h; cb
0x180021416  call    cs:__imp_CoTaskMemAlloc
0x18002141c  mov     rdi, rax
0x18002141f  mov     [rsp+98h+arg_8], rax
0x180021427  test    rax, rax
0x18002142a  jnz     short loc_18002145F
0x18002142c  mov     rcx, [rbx+28h]
0x180021430  mov     rax, [rcx]
0x180021433  lea     rdx, aErrorOutOfMemo_2; "Error! Out of memory in THashedPKIndexe"...
0x18002143a  mov     rax, [rax]
0x18002143d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021442  xor     r9d, r9d; unsigned int
0x180021445  mov     r8d, 0CCh; unsigned int
0x18002144b  lea     rdx, aOutOfMemory; "OUT OF MEMORY"
0x180021452  lea     rcx, aInetsrvIisMbCo_14; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180021459  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18002145f  mov     dword ptr [rax], 0FFFFFFFFh
0x180021465  xor     esi, esi
0x180021467  cmp     esi, r14d
0x18002146a  jnb     short loc_180021491
0x18002146c  lea     rcx, [rsp+98h+var_50]; this
0x180021471  call    ?Get_InternalName@TDatabaseMeta@@QEBAPEBGXZ; TDatabaseMeta::Get_InternalName(void)
0x180021476  xor     edx, edx; unsigned int
0x180021478  mov     rcx, rax; unsigned __int16 *
0x18002147b  call    ?Hash@@YAKPEBGK@Z; Hash(ushort const *,ulong)
0x180021480  mov     [rdi+rsi*4], eax
0x180021483  inc     esi
0x180021485  lea     rcx, [rsp+98h+var_50]
0x18002148a  call    ?Next@?$TMetaTable@UQueryMetaPublic@@@@UEAA_NXZ; TMetaTable<QueryMetaPublic>::Next(void)
0x18002148f  jmp     short loc_180021467
0x180021491  mov     eax, r14d
0x180021494  shr     eax, 1
0x180021496  or      eax, r14d
0x180021499  mov     ecx, eax
0x18002149b  shr     ecx, 2
0x18002149e  or      ecx, eax
0x1800214a0  mov     eax, ecx
0x1800214a2  shr     eax, 4
0x1800214a5  or      eax, ecx
0x1800214a7  mov     ecx, eax
0x1800214a9  shr     ecx, 8
0x1800214ac  or      ecx, eax
0x1800214ae  mov     eax, ecx
0x1800214b0  shr     eax, 10h
0x1800214b3  or      eax, ecx
0x1800214b5  add     eax, 1
0x1800214b8  mov     r15d, 80000000h
0x1800214be  cmovnz  r15d, eax
0x1800214c2  lea     rax, [rsp+98h+arg_0]
0x1800214ca  mov     [rsp+98h+var_70], rax; unsigned int *
0x1800214cf  mov     [rsp+98h+var_78], r15d; unsigned int
0x1800214d4  mov     r9, rdi; unsigned int (*)[8192]
0x1800214d7  mov     r8d, 1; unsigned int
0x1800214dd  mov     edx, r14d; unsigned int
0x1800214e0  mov     rcx, rbx; this
0x1800214e3  call    ?FillInTheHashTable@THashedPKIndexes@@AEAAKKKQEAY0CAAA@KKPEAK@Z; THashedPKIndexes::FillInTheHashTable(ulong,ulong,ulong (* const)[8192],ulong,ulong *)
0x1800214e8  mov     esi, eax
0x1800214ea  mov     rcx, [rbx+20h]
0x1800214ee  mov     rdx, [rcx]
0x1800214f1  mov     rax, [rdx+160h]
0x1800214f8  lea     rdx, aDatabasemeta_0; "DATABASEMETA"
0x1800214ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021504  mov     r8d, eax
0x180021507  mov     rcx, [rbx+20h]
0x18002150b  mov     rdx, [rcx]
0x18002150e  mov     rax, [rdx+0E8h]
0x180021515  mov     edx, r8d
0x180021518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002151d  mov     [rax+5Ch], esi
0x180021520  mov     r8, [rbx+10h]
0x180021524  mov     rcx, [rbx+28h]
0x180021528  mov     r9d, [r8+rsi*8+4]
0x18002152d  mov     rax, [rcx]
0x180021530  mov     edx, r9d
0x180021533  sub     edx, [r8+rsi*8]
0x180021537  mov     [rsp+98h+var_68], edx
0x18002153b  mov     edx, [rsp+98h+arg_0]
0x180021542  mov     dword ptr [rsp+98h+var_70], edx
0x180021546  mov     [rsp+98h+var_78], r15d
0x18002154b  mov     r8d, r14d
0x18002154e  lea     rdx, aDatabasemetaHa; "\nDatabaseMeta has %d rows, the hash ta"...
0x180021555  mov     rax, [rax]
0x180021558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002155d  nop
0x18002155e  mov     rcx, rdi; pv
0x180021561  call    cs:__imp_CoTaskMemFree
0x180021567  nop
0x180021568  lea     r11, [rsp+98h+var_18]
0x180021570  mov     rbx, [r11+30h]
0x180021574  mov     rsi, [r11+38h]
0x180021578  mov     rsp, r11
0x18002157b  pop     r15
0x18002157d  pop     r14
0x18002157f  pop     rdi
0x180021580  retn
```
