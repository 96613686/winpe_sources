# THashedUniqueIndexes::FillInTheHashTableViaIndexMeta(TTableMeta &,TIndexMeta &,ulong)

- ea: `0x180022a20`
- end: `0x180022e6e`
- name: `?FillInTheHashTableViaIndexMeta@THashedUniqueIndexes@@AEAAXAEAVTTableMeta@@AEAVTIndexMeta@@K@Z`
- size: `1102`
- prototype: `void __fastcall(THashedUniqueIndexes *__hidden this, struct TTableMeta *, struct TIndexMeta *, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task`

## callers

- `0x1800228d0`

## callees

- `0x180002b90`
- `0x180014088`
- `0x180014140`
- `0x180014168`
- `0x180017ad8`
- `0x18002225c`
- `0x180022360`
- `0x1800223a8`
- `0x180022440`
- `0x180022714`
- `0x180022a20`
- `0x180022ebc`
- `0x18002318c`
- `0x1800231c8`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180022af4`
- `ole32!CoTaskMemAlloc` at `0x180022af4`

## string_xrefs

- `0x180022b16`: `inetsrv\iis\mb\config\src\core\schemagen\thasheduniqueindexes.cpp`
- `0x180022d0b`: `inetsrv\iis\mb\config\src\core\schemagen\thasheduniqueindexes.cpp`
- `0x180022d61`: `inetsrv\iis\mb\config\src\core\schemagen\thasheduniqueindexes.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall THashedUniqueIndexes::FillInTheHashTableViaIndexMeta(
        THashedUniqueIndexes *this,
        struct TTableMeta *a2,
        struct TIndexMeta *a3,
        unsigned int a4)
{
  void (***v6)(_QWORD, const wchar_t *, ...); // rsi
  void (*v7)(_QWORD, const wchar_t *, ...); // rdi
  const unsigned __int16 *InternalName; // rbx
  const unsigned __int16 *v9; // rax
  int *v10; // rax
  struct TMetaTableBase *v11; // rbx
  unsigned int v12; // esi
  void *v13; // rdi
  unsigned int v14; // r12d
  __int64 v15; // rsi
  unsigned int v16; // r14d
  unsigned int i; // eax
  unsigned int v18; // edx
  const unsigned int *Type; // rax
  const unsigned __int16 *v20; // rax
  unsigned int v21; // eax
  unsigned int v22; // esi
  const unsigned __int8 *v23; // rax
  const struct _GUID *v24; // rax
  int v25; // eax
  void (***v26)(_QWORD, const wchar_t *, ...); // rsi
  void (*v27)(_QWORD, const wchar_t *, ...); // rdi
  const unsigned __int16 *v28; // rbx
  const unsigned __int16 *v29; // rax
  unsigned int v30; // eax
  bool v31; // zf
  unsigned int v32; // eax
  unsigned int v33; // r12d
  unsigned int v34; // edi
  _DWORD *v35; // rax
  void (***v36)(_QWORD, const wchar_t *, ...); // r15
  void (*v37)(_QWORD, const wchar_t *, ...); // r14
  int v38; // esi
  int v39; // edi
  const unsigned __int16 *v40; // rax
  unsigned int *v41; // [rsp+20h] [rbp-59h]
  unsigned int v42; // [rsp+50h] [rbp-29h] BYREF
  unsigned int v43; // [rsp+54h] [rbp-25h]
  unsigned int v44; // [rsp+58h] [rbp-21h]
  LPVOID v45; // [rsp+60h] [rbp-19h] BYREF
  struct TMetaTableBase *v46; // [rsp+68h] [rbp-11h] BYREF
  __int64 v47; // [rsp+70h] [rbp-9h]
  _QWORD v48[2]; // [rsp+78h] [rbp-1h] BYREF
  unsigned int v49; // [rsp+88h] [rbp+Fh]
  unsigned int v50; // [rsp+8Ch] [rbp+13h]
  unsigned int v51; // [rsp+E0h] [rbp+67h]
  unsigned int v53; // [rsp+F0h] [rbp+77h]

  v42 = 0;
  v46 = 0;
  v45 = 0;
  v6 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
  v7 = **v6;
  InternalName = TTableMeta::Get_InternalName(a2);
  v9 = TIndexMeta::Get_InternalName(a3);
  v7(v6, L"\nBuilding indexed (%s) hash table for table: %s", v9, InternalName);
  v10 = (int *)(*(__int64 (__fastcall **)(struct TIndexMeta *))(*(_QWORD *)a3 + 56LL))(a3);
  THashedUniqueIndexes::GetMetaTable(this, *v10, (void ****)&v46);
  v11 = v46;
  if ( !v46 )
  {
    TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(&v45);
    return;
  }
  v12 = (*(__int64 (__fastcall **)(struct TMetaTableBase *))(*(_QWORD *)v46 + 48LL))(v46);
  v43 = v12;
  v13 = CoTaskMemAlloc(saturated_mul(v12, 4u));
  v45 = v13;
  if ( !v13 )
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\thasheduniqueindexes.cpp",
      L"OUT OF MEMORY",
      0xA8u,
      0);
  v14 = 0;
  v53 = 0;
LABEL_6:
  if ( v14 < v12 )
  {
    v15 = (*(__int64 (__fastcall **)(struct TMetaTableBase *))(*(_QWORD *)v11 + 40LL))(v11);
    v47 = v15;
    v16 = 0;
    (*(void (__fastcall **)(struct TIndexMeta *))(*(_QWORD *)a3 + 32LL))(a3);
    for ( i = 0; ; i = v51 + 1 )
    {
      v51 = i;
      if ( i >= a4 )
      {
        *((_DWORD *)v13 + v53) = v16;
        v14 = ++v53;
        (*(void (__fastcall **)(struct TMetaTableBase *))(*(_QWORD *)v11 + 8LL))(v11);
        v12 = v43;
        goto LABEL_6;
      }
      v44 = *TIndexMeta::Get_ColumnIndex(a3);
      v18 = v44 + *((_DWORD *)TTableMeta::Get_pMetaTable(a2) + 18);
      v48[1] = *((_QWORD *)this + 1);
      v49 = v18;
      v50 = v18;
      v48[0] = &TColumnMeta::`vftable';
      if ( !*(_DWORD *)(v15 + 4LL * v44) )
      {
        v26 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
        v27 = **v26;
        v28 = TColumnMeta::Get_InternalName((TColumnMeta *)v48);
        v29 = TTableMeta::Get_InternalName(a2);
        v27(v26, L"\nError - Table (%s), Column number %d (%s) is an Index but is set to NULL.\n", v29, v44, v28);
        ThrowException(
          L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\thasheduniqueindexes.cpp",
          L"Fixed table contains NULL value in Unique Index",
          0xBAu,
          0);
      }
      Type = TColumnMeta::Get_Type((TColumnMeta *)v48);
      if ( *Type == 19 )
      {
        v25 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 152LL))(
                *((_QWORD *)this + 1),
                *(unsigned int *)(v15 + 4LL * v44));
        v16 = *((_DWORD *)c_rgulHashTable + ((unsigned __int64)HIWORD(v25) >> 8))
            ^ __ROL4__(
                *((_DWORD *)c_rgulHashTable + BYTE2(v25))
              ^ __ROL4__(
                  *((_DWORD *)c_rgulHashTable + ((unsigned __int64)(unsigned __int16)v25 >> 8))
                ^ __ROL4__(*((_DWORD *)c_rgulHashTable + (unsigned __int8)v25) ^ __ROL4__(v16, 1), 1),
                  1),
                1);
      }
      else
      {
        switch ( *Type )
        {
          case 0x48u:
            v24 = (const struct _GUID *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 136LL))(
                                          *((_QWORD *)this + 1),
                                          *(unsigned int *)(v15 + 4LL * v44));
            v21 = Hash(v24, v16);
            break;
          case 0x80u:
            v22 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 168LL))(
                    *((_QWORD *)this + 1),
                    *(unsigned int *)(v15 + 4LL * v44));
            v23 = (const unsigned __int8 *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 128LL))(
                                             *((_QWORD *)this + 1),
                                             *(unsigned int *)(v47 + 4LL * v44));
            v16 = Hash(v23, v22, v16);
            v15 = v47;
            goto LABEL_19;
          case 0x82u:
            v20 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(
                                              *((_QWORD *)this + 1),
                                              *(unsigned int *)(v15 + 4LL * v44));
            v21 = Hash(v20, v16);
            break;
          default:
            ThrowException(
              L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\thasheduniqueindexes.cpp",
              L"unsupported type",
              0xD0u,
              0);
        }
        v16 = v21;
      }
LABEL_19:
      (*(void (__fastcall **)(struct TIndexMeta *))(*(_QWORD *)a3 + 8LL))(a3);
    }
  }
  (*(void (__fastcall **)(struct TIndexMeta *))(*(_QWORD *)a3 + 32LL))(a3);
  v30 = v12
      | (v12 >> 1)
      | ((v12 | (v12 >> 1)) >> 2)
      | ((v12 | (v12 >> 1) | ((v12 | (v12 >> 1)) >> 2)) >> 4)
      | ((v12 | (v12 >> 1) | ((v12 | (v12 >> 1)) >> 2) | ((v12 | (v12 >> 1) | ((v12 | (v12 >> 1)) >> 2)) >> 4)) >> 8)
      | ((v12
        | (v12 >> 1)
        | ((v12 | (v12 >> 1)) >> 2)
        | ((v12 | (v12 >> 1) | ((v12 | (v12 >> 1)) >> 2)) >> 4)
        | ((v12 | (v12 >> 1) | ((v12 | (v12 >> 1)) >> 2) | ((v12 | (v12 >> 1) | ((v12 | (v12 >> 1)) >> 2)) >> 4)) >> 8)) >> 16);
  v31 = v30 == -1;
  v32 = v30 + 1;
  v33 = 0x80000000;
  if ( !v31 )
    v33 = v32;
  v34 = THashedUniqueIndexes::FillInTheHashTable(this, v12, (unsigned int *const)v13, v33, &v42);
  *(_DWORD *)((*(__int64 (__fastcall **)(struct TIndexMeta *))(*(_QWORD *)a3 + 56LL))(a3) + 24) = v34;
  v35 = (_DWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 192LL))(
                    *((_QWORD *)this + 1),
                    v34);
  v36 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
  v37 = **v36;
  v38 = v35[1];
  v39 = v38 - *v35;
  v40 = TTableMeta::Get_InternalName(a2);
  LODWORD(v41) = v38;
  v37(
    v36,
    L"\n%s has %d rows, the hash table has %d elements, %d modulo, %d max chain and %d nonunique entries.\n",
    v40,
    v43,
    v41,
    v33,
    v42,
    v39);
  TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(&v45);
  if ( v11 )
    (**(void (__fastcall ***)(struct TMetaTableBase *, __int64))v11)(v11, 1);
}

```

## disassembly

```asm
0x180022a20  mov     [rsp-8+arg_18], r9d
0x180022a25  mov     [rsp-8+arg_8], rdx
0x180022a2a  push    rbp
0x180022a2b  push    rbx
0x180022a2c  push    rsi
0x180022a2d  push    rdi
0x180022a2e  push    r12
0x180022a30  push    r13
0x180022a32  push    r14
0x180022a34  push    r15
0x180022a36  lea     rbp, [rsp-1Fh]
0x180022a3b  sub     rsp, 98h
0x180022a42  mov     r13, r8
0x180022a45  mov     r15, rcx
0x180022a48  mov     [rbp+57h+var_80], 0
0x180022a4f  mov     [rbp+57h+var_68], 0
0x180022a57  mov     [rbp+57h+var_70], 0
0x180022a5f  mov     rsi, [rcx+10h]
0x180022a63  mov     rax, [rsi]
0x180022a66  mov     rdi, [rax]
0x180022a69  mov     rcx, rdx; this
0x180022a6c  call    ?Get_InternalName@TTableMeta@@QEBAPEBGXZ; TTableMeta::Get_InternalName(void)
0x180022a71  mov     rbx, rax
0x180022a74  mov     rcx, r13; this
0x180022a77  call    ?Get_InternalName@TIndexMeta@@QEBAPEBGXZ; TIndexMeta::Get_InternalName(void)
0x180022a7c  mov     r9, rbx
0x180022a7f  mov     r8, rax
0x180022a82  lea     rdx, aBuildingIndexe_0; "\nBuilding indexed (%s) hash table for "...
0x180022a89  mov     rcx, rsi
0x180022a8c  mov     rax, rdi
0x180022a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a94  mov     rax, [r13+0]
0x180022a98  mov     rcx, r13
0x180022a9b  mov     rax, [rax+38h]
0x180022a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022aa4  lea     r8, [rbp+57h+var_68]; struct TMetaTableBase **
0x180022aa8  mov     edx, [rax]; unsigned int
0x180022aaa  mov     rcx, r15; this
0x180022aad  call    ?GetMetaTable@THashedUniqueIndexes@@AEBAXKPEAPEAVTMetaTableBase@@@Z; THashedUniqueIndexes::GetMetaTable(ulong,TMetaTableBase * *)
0x180022ab2  mov     rbx, [rbp+57h+var_68]
0x180022ab6  test    rbx, rbx
0x180022ab9  jnz     short loc_180022ACA
0x180022abb  lea     rcx, [rbp+57h+var_70]
0x180022abf  call    ??1?$TSmartPointerArray@U__MIDL___MIDL_itf_catalog_0000_0000_0004@@@@QEAA@XZ; TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(void)
0x180022ac4  nop
0x180022ac5  jmp     loc_180022E5A
0x180022aca  mov     rax, [rbx]
0x180022acd  mov     rcx, rbx
0x180022ad0  mov     rax, [rax+30h]
0x180022ad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ad9  mov     esi, eax
0x180022adb  mov     [rbp+57h+var_7C], esi
0x180022ade  mov     eax, 4
0x180022ae3  mul     rsi
0x180022ae6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180022aed  cmovb   rax, rcx
0x180022af1  mov     rcx, rax; cb
0x180022af4  call    cs:__imp_CoTaskMemAlloc
0x180022afa  mov     rdi, rax
0x180022afd  mov     [rbp+57h+var_70], rax
0x180022b01  test    rax, rax
0x180022b04  jnz     short loc_180022B23
0x180022b06  xor     r9d, r9d; unsigned int
0x180022b09  mov     r8d, 0A8h; unsigned int
0x180022b0f  lea     rdx, aOutOfMemory; "OUT OF MEMORY"
0x180022b16  lea     rcx, aInetsrvIisMbCo_11; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180022b1d  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x180022b23  xor     r12d, r12d
0x180022b26  mov     [rbp+57h+arg_10], r12d
0x180022b2a  cmp     r12d, esi
0x180022b2d  jnb     loc_180022D6E
0x180022b33  mov     rax, [rbx]
0x180022b36  mov     rcx, rbx
0x180022b39  mov     rax, [rax+28h]
0x180022b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b42  mov     rsi, rax
0x180022b45  mov     [rbp+57h+var_60], rax
0x180022b49  xor     r14d, r14d
0x180022b4c  mov     rcx, [r13+0]
0x180022b50  mov     rax, [rcx+20h]
0x180022b54  mov     rcx, r13
0x180022b57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b5c  xor     eax, eax
0x180022b5e  mov     [rbp+57h+arg_0], eax
0x180022b61  cmp     eax, [rbp+57h+arg_18]
0x180022b64  jnb     loc_180022CD5
0x180022b6a  mov     rcx, r13; this
0x180022b6d  call    ?Get_ColumnIndex@TIndexMeta@@QEBAPEBKXZ; TIndexMeta::Get_ColumnIndex(void)
0x180022b72  mov     r12d, [rax]
0x180022b75  mov     [rbp+57h+var_78], r12d
0x180022b79  mov     rcx, [rbp+57h+arg_8]; this
0x180022b7d  call    ?Get_pMetaTable@TTableMeta@@UEAAPEAUTableMeta@@XZ; TTableMeta::Get_pMetaTable(void)
0x180022b82  mov     edx, [rax+48h]
0x180022b85  add     edx, r12d
0x180022b88  mov     rax, [r15+8]
0x180022b8c  mov     [rbp+57h+var_50], rax
0x180022b90  mov     [rbp+57h+var_48], edx
0x180022b93  mov     [rbp+57h+var_44], edx
0x180022b96  lea     rax, ??_7TColumnMeta@@6B@; const TColumnMeta::`vftable'
0x180022b9d  mov     [rbp+57h+var_58], rax
0x180022ba1  lea     rcx, [rbp+57h+var_58]; this
0x180022ba5  cmp     dword ptr [rsi+r12*4], 0
0x180022baa  jz      loc_180022D18
0x180022bb0  call    ?Get_Type@TColumnMeta@@QEBAPEBKXZ; TColumnMeta::Get_Type(void)
0x180022bb5  mov     edx, [rax]
0x180022bb7  sub     edx, 13h
0x180022bba  jz      loc_180022C68
0x180022bc0  sub     edx, 35h ; '5'
0x180022bc3  jz      short loc_180022C41
0x180022bc5  sub     edx, 38h ; '8'
0x180022bc8  jz      short loc_180022BF7
0x180022bca  cmp     edx, 2
0x180022bcd  jnz     loc_180022CFB
0x180022bd3  mov     rcx, [r15+8]
0x180022bd7  mov     rax, [rcx]
0x180022bda  mov     edx, [rsi+r12*4]
0x180022bde  mov     rax, [rax+90h]
0x180022be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022bea  mov     rcx, rax; unsigned __int16 *
0x180022bed  mov     edx, r14d; unsigned int
0x180022bf0  call    ?Hash@@YAKPEBGK@Z; Hash(ushort const *,ulong)
0x180022bf5  jmp     short loc_180022C63
0x180022bf7  mov     rcx, [r15+8]
0x180022bfb  mov     rax, [rcx]
0x180022bfe  mov     edx, [rsi+r12*4]
0x180022c02  mov     rax, [rax+0A8h]
0x180022c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c0e  mov     esi, eax
0x180022c10  mov     rcx, [r15+8]
0x180022c14  mov     rdx, [rcx]
0x180022c17  mov     rax, [rdx+80h]
0x180022c1e  mov     rdx, [rbp+57h+var_60]
0x180022c22  mov     edx, [rdx+r12*4]
0x180022c26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c2b  mov     r8d, r14d; unsigned int
0x180022c2e  mov     edx, esi; unsigned int
0x180022c30  mov     rcx, rax; unsigned __int8 *
0x180022c33  call    ?Hash@@YAKPEBEKK@Z; Hash(uchar const *,ulong,ulong)
0x180022c38  mov     r14d, eax
0x180022c3b  mov     rsi, [rbp+57h+var_60]
0x180022c3f  jmp     short loc_180022CBB
0x180022c41  mov     rcx, [r15+8]
0x180022c45  mov     rax, [rcx]
0x180022c48  mov     edx, [rsi+r12*4]
0x180022c4c  mov     rax, [rax+88h]
0x180022c53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c58  mov     rcx, rax; struct _GUID *
0x180022c5b  mov     edx, r14d; unsigned int
0x180022c5e  call    ?Hash@@YAKAEBU_GUID@@K@Z; Hash(_GUID const &,ulong)
0x180022c63  mov     r14d, eax
0x180022c66  jmp     short loc_180022CBB
0x180022c68  mov     rcx, [r15+8]
0x180022c6c  mov     rax, [rcx]
0x180022c6f  mov     edx, [rsi+r12*4]
0x180022c73  mov     rax, [rax+98h]
0x180022c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c7f  mov     edx, eax
0x180022c81  shr     edx, 10h
0x180022c84  rol     r14d, 1
0x180022c87  movzx   ecx, al
0x180022c8a  lea     r8, c_rgulHashTable
0x180022c91  xor     r14d, [r8+rcx*4]
0x180022c95  rol     r14d, 1
0x180022c98  movzx   eax, ax
0x180022c9b  shr     rax, 8
0x180022c9f  xor     r14d, [r8+rax*4]
0x180022ca3  rol     r14d, 1
0x180022ca6  movzx   eax, dl
0x180022ca9  xor     r14d, [r8+rax*4]
0x180022cad  rol     r14d, 1
0x180022cb0  movzx   eax, dx
0x180022cb3  shr     rax, 8
0x180022cb7  xor     r14d, [r8+rax*4]
0x180022cbb  mov     rax, [r13+0]
0x180022cbf  mov     rcx, r13
0x180022cc2  mov     rax, [rax+8]
0x180022cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ccb  mov     eax, [rbp+57h+arg_0]
0x180022cce  inc     eax
0x180022cd0  jmp     loc_180022B5E
0x180022cd5  mov     r12d, [rbp+57h+arg_10]
0x180022cd9  mov     [rdi+r12*4], r14d
0x180022cdd  inc     r12d
0x180022ce0  mov     [rbp+57h+arg_10], r12d
0x180022ce4  mov     rax, [rbx]
0x180022ce7  mov     rcx, rbx
0x180022cea  mov     rax, [rax+8]
0x180022cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022cf3  mov     esi, [rbp+57h+var_7C]
0x180022cf6  jmp     loc_180022B2A
0x180022cfb  xor     r9d, r9d; unsigned int
0x180022cfe  mov     r8d, 0D0h; unsigned int
0x180022d04  lea     rdx, aUnsupportedTyp; "unsupported type"
0x180022d0b  lea     rcx, aInetsrvIisMbCo_11; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180022d12  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x180022d18  mov     rsi, [r15+10h]
0x180022d1c  mov     rax, [rsi]
0x180022d1f  mov     rdi, [rax]
0x180022d22  call    ?Get_InternalName@TColumnMeta@@QEBAPEBGXZ; TColumnMeta::Get_InternalName(void)
0x180022d27  mov     rbx, rax
0x180022d2a  mov     rcx, [rbp+57h+arg_8]; this
0x180022d2e  call    ?Get_InternalName@TTableMeta@@QEBAPEBGXZ; TTableMeta::Get_InternalName(void)
0x180022d33  mov     [rsp+0D0h+var_B0], rbx
0x180022d38  mov     r9d, [rbp+57h+var_78]
0x180022d3c  mov     r8, rax
0x180022d3f  lea     rdx, aErrorTableSCol_0; "\nError - Table (%s), Column number %d "...
0x180022d46  mov     rcx, rsi
0x180022d49  mov     rax, rdi
0x180022d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d51  xor     r9d, r9d; unsigned int
0x180022d54  mov     r8d, 0BAh; unsigned int
0x180022d5a  lea     rdx, aFixedTableCont; "Fixed table contains NULL value in Uniq"...
0x180022d61  lea     rcx, aInetsrvIisMbCo_11; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180022d68  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x180022d6e  mov     rax, [r13+0]
0x180022d72  mov     rcx, r13
0x180022d75  mov     rax, [rax+20h]
0x180022d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d7e  mov     eax, esi
0x180022d80  shr     eax, 1
0x180022d82  or      eax, esi
0x180022d84  mov     ecx, eax
0x180022d86  shr     ecx, 2
0x180022d89  or      ecx, eax
0x180022d8b  mov     eax, ecx
0x180022d8d  shr     eax, 4
0x180022d90  or      eax, ecx
0x180022d92  mov     ecx, eax
0x180022d94  shr     ecx, 8
0x180022d97  or      ecx, eax
0x180022d99  mov     eax, ecx
0x180022d9b  shr     eax, 10h
0x180022d9e  or      eax, ecx
0x180022da0  add     eax, 1
0x180022da3  mov     r12d, 80000000h
0x180022da9  cmovnz  r12d, eax
0x180022dad  lea     rax, [rbp+57h+var_80]
0x180022db1  mov     [rsp+0D0h+var_B0], rax; unsigned int *
0x180022db6  mov     r9d, r12d; unsigned int
0x180022db9  mov     r8, rdi; unsigned int *
0x180022dbc  mov     edx, esi; unsigned int
0x180022dbe  mov     rcx, r15; this
0x180022dc1  call    ?FillInTheHashTable@THashedUniqueIndexes@@AEAAKKQEAKKPEAK@Z; THashedUniqueIndexes::FillInTheHashTable(ulong,ulong * const,ulong,ulong *)
0x180022dc6  mov     edi, eax
0x180022dc8  mov     rcx, [r13+0]
0x180022dcc  mov     rax, [rcx+38h]
0x180022dd0  mov     rcx, r13
0x180022dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022dd8  mov     [rax+18h], edi
0x180022ddb  mov     rcx, [r15+8]
0x180022ddf  mov     rdx, [rcx]
0x180022de2  mov     rax, [rdx+0C0h]
0x180022de9  mov     edx, edi
0x180022deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022df0  mov     r15, [r15+10h]
0x180022df4  mov     rcx, [r15]
0x180022df7  mov     r14, [rcx]
0x180022dfa  mov     esi, [rax+4]
0x180022dfd  mov     edi, esi
0x180022dff  sub     edi, [rax]
0x180022e01  mov     rcx, [rbp+57h+arg_8]; this
0x180022e05  call    ?Get_InternalName@TTableMeta@@QEBAPEBGXZ; TTableMeta::Get_InternalName(void)
0x180022e0a  mov     [rsp+0D0h+var_98], edi
0x180022e0e  mov     edx, [rbp+57h+var_80]
0x180022e11  mov     [rsp+0D0h+var_A0], edx
0x180022e15  mov     [rsp+0D0h+var_A8], r12d
0x180022e1a  mov     dword ptr [rsp+0D0h+var_B0], esi
0x180022e1e  mov     r9d, [rbp+57h+var_7C]
0x180022e22  mov     r8, rax
0x180022e25  lea     rdx, aSHasDRowsTheHa; "\n%s has %d rows, the hash table has %d"...
0x180022e2c  mov     rcx, r15
0x180022e2f  mov     rax, r14
0x180022e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e37  nop
0x180022e38  lea     rcx, [rbp+57h+var_70]
0x180022e3c  call    ??1?$TSmartPointerArray@U__MIDL___MIDL_itf_catalog_0000_0000_0004@@@@QEAA@XZ; TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(void)
0x180022e41  nop
0x180022e42  test    rbx, rbx
0x180022e45  jz      short loc_180022E5A
0x180022e47  mov     rax, [rbx]
0x180022e4a  mov     edx, 1
0x180022e4f  mov     rcx, rbx
0x180022e52  mov     rax, [rax]
0x180022e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e5a  add     rsp, 98h
0x180022e61  pop     r15
0x180022e63  pop     r14
0x180022e65  pop     r13
0x180022e67  pop     r12
0x180022e69  pop     rdi
0x180022e6a  pop     rsi
0x180022e6b  pop     rbx
0x180022e6c  pop     rbp
0x180022e6d  retn
```
