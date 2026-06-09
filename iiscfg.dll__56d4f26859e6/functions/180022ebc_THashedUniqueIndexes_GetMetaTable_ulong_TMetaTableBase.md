# THashedUniqueIndexes::GetMetaTable(ulong,TMetaTableBase * *)

- ea: `0x180022ebc`
- end: `0x180023185`
- name: `?GetMetaTable@THashedUniqueIndexes@@AEBAXKPEAPEAVTMetaTableBase@@@Z`
- size: `713`
- prototype: `void __fastcall(THashedUniqueIndexes *__hidden this, unsigned int, struct TMetaTableBase **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180022a20`

## callees

- `0x180017ad8`
- `0x180022ebc`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180022f00`
- `ole32!CoTaskMemAlloc` at `0x180022f52`
- `ole32!CoTaskMemAlloc` at `0x180022fa0`
- `ole32!CoTaskMemAlloc` at `0x180022fee`
- `ole32!CoTaskMemAlloc` at `0x18002303c`
- `ole32!CoTaskMemAlloc` at `0x18002308a`
- `ole32!CoTaskMemAlloc` at `0x1800230d8`
- `ole32!CoTaskMemAlloc` at `0x18002311f`
- `ole32!CoTaskMemAlloc` at `0x180022f00`
- `ole32!CoTaskMemAlloc` at `0x180022f52`
- `ole32!CoTaskMemAlloc` at `0x180022fa0`
- `ole32!CoTaskMemAlloc` at `0x180022fee`
- `ole32!CoTaskMemAlloc` at `0x18002303c`
- `ole32!CoTaskMemAlloc` at `0x18002308a`
- `ole32!CoTaskMemAlloc` at `0x1800230d8`
- `ole32!CoTaskMemAlloc` at `0x18002311f`

## string_xrefs

- `0x180023165`: `inetsrv\iis\mb\config\src\core\schemagen\thasheduniqueindexes.cpp`

## pseudocode

```c
void __fastcall THashedUniqueIndexes::GetMetaTable(THashedUniqueIndexes *this, int a2, void ****a3)
{
  void ***v6; // rax
  void ***v7; // rdx
  void **v8; // rax
  void ***v9; // rax
  void ***v10; // rax
  void ***v11; // rax
  void ***v12; // rax
  void ***v13; // rax
  void ***v14; // rax
  void ***v15; // rax

  *a3 = 0;
  if ( a2 != (*(unsigned int (__fastcall **)(_QWORD, const wchar_t *, __int64))(**((_QWORD **)this + 1) + 48LL))(
               *((_QWORD *)this + 1),
               L"COLUMNMETA",
               0xFFFFFFFFLL) )
  {
    if ( a2 == (*(unsigned int (__fastcall **)(_QWORD, const WCHAR *, __int64))(**((_QWORD **)this + 1) + 48LL))(
                 *((_QWORD *)this + 1),
                 L"DATABASEMETA",
                 0xFFFFFFFFLL) )
    {
      v9 = (void ***)CoTaskMemAlloc(0x18u);
      v7 = v9;
      if ( !v9 )
        goto LABEL_27;
      v9[1] = (void **)*((_QWORD *)this + 1);
      v8 = &TDatabaseMeta::`vftable';
    }
    else if ( a2 == (*(unsigned int (__fastcall **)(_QWORD, const WCHAR *, __int64))(**((_QWORD **)this + 1) + 48LL))(
                      *((_QWORD *)this + 1),
                      L"INDEXMETA",
                      0xFFFFFFFFLL) )
    {
      v10 = (void ***)CoTaskMemAlloc(0x18u);
      v7 = v10;
      if ( !v10 )
        goto LABEL_27;
      v10[1] = (void **)*((_QWORD *)this + 1);
      v8 = &TIndexMeta::`vftable';
    }
    else if ( a2 == (*(unsigned int (__fastcall **)(_QWORD, const WCHAR *, __int64))(**((_QWORD **)this + 1) + 48LL))(
                      *((_QWORD *)this + 1),
                      L"QUERYMETA",
                      0xFFFFFFFFLL) )
    {
      v11 = (void ***)CoTaskMemAlloc(0x18u);
      v7 = v11;
      if ( !v11 )
        goto LABEL_27;
      v11[1] = (void **)*((_QWORD *)this + 1);
      v8 = &TQueryMeta::`vftable';
    }
    else if ( a2 == (*(unsigned int (__fastcall **)(_QWORD, const WCHAR *, __int64))(**((_QWORD **)this + 1) + 48LL))(
                      *((_QWORD *)this + 1),
                      L"RELATIONMETA",
                      0xFFFFFFFFLL) )
    {
      v12 = (void ***)CoTaskMemAlloc(0x18u);
      v7 = v12;
      if ( !v12 )
        goto LABEL_27;
      v12[1] = (void **)*((_QWORD *)this + 1);
      v8 = &TRelationMeta::`vftable';
    }
    else if ( a2 == (*(unsigned int (__fastcall **)(_QWORD, const wchar_t *, __int64))(**((_QWORD **)this + 1) + 48LL))(
                      *((_QWORD *)this + 1),
                      L"SERVERWIRINGMETA",
                      0xFFFFFFFFLL) )
    {
      v13 = (void ***)CoTaskMemAlloc(0x18u);
      v7 = v13;
      if ( !v13 )
        goto LABEL_27;
      v13[1] = (void **)*((_QWORD *)this + 1);
      v8 = &TServerWiringMeta::`vftable';
    }
    else if ( a2 == (*(unsigned int (__fastcall **)(_QWORD, const wchar_t *, __int64))(**((_QWORD **)this + 1) + 48LL))(
                      *((_QWORD *)this + 1),
                      L"TABLEMETA",
                      0xFFFFFFFFLL) )
    {
      v14 = (void ***)CoTaskMemAlloc(0x18u);
      v7 = v14;
      if ( !v14 )
        goto LABEL_27;
      v14[1] = (void **)*((_QWORD *)this + 1);
      v8 = &TTableMeta::`vftable';
    }
    else
    {
      if ( a2 != (*(unsigned int (__fastcall **)(_QWORD, const wchar_t *, __int64))(**((_QWORD **)this + 1) + 48LL))(
                   *((_QWORD *)this + 1),
                   L"TAGMETA",
                   0xFFFFFFFFLL) )
        return;
      v15 = (void ***)CoTaskMemAlloc(0x18u);
      v7 = v15;
      if ( !v15 )
        goto LABEL_27;
      v15[1] = (void **)*((_QWORD *)this + 1);
      v8 = &TTagMeta::`vftable';
    }
    v7[2] = 0;
    goto LABEL_26;
  }
  v6 = (void ***)CoTaskMemAlloc(0x18u);
  v7 = v6;
  if ( v6 )
  {
    v6[1] = (void **)*((_QWORD *)this + 1);
    v6[2] = 0;
    v8 = &TColumnMeta::`vftable';
LABEL_26:
    *v7 = v8;
    goto LABEL_28;
  }
LABEL_27:
  v7 = 0;
LABEL_28:
  *a3 = v7;
  if ( !v7 )
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\thasheduniqueindexes.cpp",
      L"OUT OF MEMORY",
      0x10Du,
      0);
}

```

## disassembly

```asm
0x180022ebc  mov     [rsp+arg_8], rbx
0x180022ec1  mov     [rsp+arg_10], rbp
0x180022ec6  push    rsi
0x180022ec7  push    rdi
0x180022ec8  push    r14
0x180022eca  sub     rsp, 20h
0x180022ece  mov     rbx, rcx
0x180022ed1  mov     rsi, r8
0x180022ed4  mov     edi, edx
0x180022ed6  xor     ebp, ebp
0x180022ed8  mov     [r8], rbp
0x180022edb  lea     rdx, aColumnmeta; "COLUMNMETA"
0x180022ee2  mov     rcx, [rcx+8]
0x180022ee6  or      r14d, 0FFFFFFFFh
0x180022eea  mov     r8d, r14d
0x180022eed  mov     rax, [rcx]
0x180022ef0  mov     rax, [rax+30h]
0x180022ef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ef9  cmp     edi, eax
0x180022efb  jnz     short loc_180022F2F
0x180022efd  lea     ecx, [rbp+18h]; cb
0x180022f00  call    cs:__imp_CoTaskMemAlloc
0x180022f06  mov     [rsp+38h+arg_0], rax
0x180022f0b  mov     rdx, rax
0x180022f0e  test    rax, rax
0x180022f11  jz      loc_18002314A
0x180022f17  mov     rcx, [rbx+8]
0x180022f1b  mov     [rax+8], rcx
0x180022f1f  mov     [rax+10h], rbp
0x180022f23  lea     rax, ??_7TColumnMeta@@6B@; const TColumnMeta::`vftable'
0x180022f2a  jmp     loc_180023145
0x180022f2f  mov     rcx, [rbx+8]
0x180022f33  lea     rdx, aDatabasemeta_0; "DATABASEMETA"
0x180022f3a  mov     r8d, r14d
0x180022f3d  mov     rax, [rcx]
0x180022f40  mov     rax, [rax+30h]
0x180022f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f49  cmp     edi, eax
0x180022f4b  jnz     short loc_180022F7D
0x180022f4d  mov     ecx, 18h; cb
0x180022f52  call    cs:__imp_CoTaskMemAlloc
0x180022f58  mov     [rsp+38h+arg_0], rax
0x180022f5d  mov     rdx, rax
0x180022f60  test    rax, rax
0x180022f63  jz      loc_18002314A
0x180022f69  mov     rax, [rbx+8]
0x180022f6d  mov     [rdx+8], rax
0x180022f71  lea     rax, ??_7TDatabaseMeta@@6B@; const TDatabaseMeta::`vftable'
0x180022f78  jmp     loc_180023141
0x180022f7d  mov     rcx, [rbx+8]
0x180022f81  lea     rdx, aIndexmeta; "INDEXMETA"
0x180022f88  mov     r8d, r14d
0x180022f8b  mov     rax, [rcx]
0x180022f8e  mov     rax, [rax+30h]
0x180022f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f97  cmp     edi, eax
0x180022f99  jnz     short loc_180022FCB
0x180022f9b  mov     ecx, 18h; cb
0x180022fa0  call    cs:__imp_CoTaskMemAlloc
0x180022fa6  mov     [rsp+38h+arg_0], rax
0x180022fab  mov     rdx, rax
0x180022fae  test    rax, rax
0x180022fb1  jz      loc_18002314A
0x180022fb7  mov     rax, [rbx+8]
0x180022fbb  mov     [rdx+8], rax
0x180022fbf  lea     rax, ??_7TIndexMeta@@6B@; const TIndexMeta::`vftable'
0x180022fc6  jmp     loc_180023141
0x180022fcb  mov     rcx, [rbx+8]
0x180022fcf  lea     rdx, aQuerymeta; "QUERYMETA"
0x180022fd6  mov     r8d, r14d
0x180022fd9  mov     rax, [rcx]
0x180022fdc  mov     rax, [rax+30h]
0x180022fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022fe5  cmp     edi, eax
0x180022fe7  jnz     short loc_180023019
0x180022fe9  mov     ecx, 18h; cb
0x180022fee  call    cs:__imp_CoTaskMemAlloc
0x180022ff4  mov     [rsp+38h+arg_0], rax
0x180022ff9  mov     rdx, rax
0x180022ffc  test    rax, rax
0x180022fff  jz      loc_18002314A
0x180023005  mov     rax, [rbx+8]
0x180023009  mov     [rdx+8], rax
0x18002300d  lea     rax, ??_7TQueryMeta@@6B@; const TQueryMeta::`vftable'
0x180023014  jmp     loc_180023141
0x180023019  mov     rcx, [rbx+8]
0x18002301d  lea     rdx, aRelationmeta; "RELATIONMETA"
0x180023024  mov     r8d, r14d
0x180023027  mov     rax, [rcx]
0x18002302a  mov     rax, [rax+30h]
0x18002302e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023033  cmp     edi, eax
0x180023035  jnz     short loc_180023067
0x180023037  mov     ecx, 18h; cb
0x18002303c  call    cs:__imp_CoTaskMemAlloc
0x180023042  mov     [rsp+38h+arg_0], rax
0x180023047  mov     rdx, rax
0x18002304a  test    rax, rax
0x18002304d  jz      loc_18002314A
0x180023053  mov     rax, [rbx+8]
0x180023057  mov     [rdx+8], rax
0x18002305b  lea     rax, ??_7TRelationMeta@@6B@; const TRelationMeta::`vftable'
0x180023062  jmp     loc_180023141
0x180023067  mov     rcx, [rbx+8]
0x18002306b  lea     rdx, aServerwiringme; "SERVERWIRINGMETA"
0x180023072  mov     r8d, r14d
0x180023075  mov     rax, [rcx]
0x180023078  mov     rax, [rax+30h]
0x18002307c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023081  cmp     edi, eax
0x180023083  jnz     short loc_1800230B5
0x180023085  mov     ecx, 18h; cb
0x18002308a  call    cs:__imp_CoTaskMemAlloc
0x180023090  mov     [rsp+38h+arg_0], rax
0x180023095  mov     rdx, rax
0x180023098  test    rax, rax
0x18002309b  jz      loc_18002314A
0x1800230a1  mov     rax, [rbx+8]
0x1800230a5  mov     [rdx+8], rax
0x1800230a9  lea     rax, ??_7TServerWiringMeta@@6B@; const TServerWiringMeta::`vftable'
0x1800230b0  jmp     loc_180023141
0x1800230b5  mov     rcx, [rbx+8]
0x1800230b9  lea     rdx, aTablemeta; "TABLEMETA"
0x1800230c0  mov     r8d, r14d
0x1800230c3  mov     rax, [rcx]
0x1800230c6  mov     rax, [rax+30h]
0x1800230ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230cf  cmp     edi, eax
0x1800230d1  jnz     short loc_1800230FC
0x1800230d3  mov     ecx, 18h; cb
0x1800230d8  call    cs:__imp_CoTaskMemAlloc
0x1800230de  mov     [rsp+38h+arg_0], rax
0x1800230e3  mov     rdx, rax
0x1800230e6  test    rax, rax
0x1800230e9  jz      short loc_18002314A
0x1800230eb  mov     rax, [rbx+8]
0x1800230ef  mov     [rdx+8], rax
0x1800230f3  lea     rax, ??_7TTableMeta@@6B@; const TTableMeta::`vftable'
0x1800230fa  jmp     short loc_180023141
0x1800230fc  mov     rcx, [rbx+8]
0x180023100  lea     rdx, aTagmeta; "TAGMETA"
0x180023107  mov     r8d, r14d
0x18002310a  mov     rax, [rcx]
0x18002310d  mov     rax, [rax+30h]
0x180023111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023116  cmp     edi, eax
0x180023118  jnz     short loc_180023172
0x18002311a  mov     ecx, 18h; cb
0x18002311f  call    cs:__imp_CoTaskMemAlloc
0x180023125  mov     [rsp+38h+arg_0], rax
0x18002312a  mov     rdx, rax
0x18002312d  test    rax, rax
0x180023130  jz      short loc_18002314A
0x180023132  mov     rax, [rbx+8]
0x180023136  mov     [rdx+8], rax
0x18002313a  lea     rax, ??_7TTagMeta@@6B@; const TTagMeta::`vftable'
0x180023141  mov     [rdx+10h], rbp
0x180023145  mov     [rdx], rax
0x180023148  jmp     short loc_18002314D
0x18002314a  mov     rdx, rbp
0x18002314d  mov     [rsi], rdx
0x180023150  test    rdx, rdx
0x180023153  jnz     short loc_180023172
0x180023155  xor     r9d, r9d; unsigned int
0x180023158  lea     rdx, aOutOfMemory; "OUT OF MEMORY"
0x18002315f  mov     r8d, 10Dh; unsigned int
0x180023165  lea     rcx, aInetsrvIisMbCo_11; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18002316c  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x180023172  mov     rbx, [rsp+38h+arg_8]
0x180023177  mov     rbp, [rsp+38h+arg_10]
0x18002317c  add     rsp, 20h
0x180023180  pop     r14
0x180023182  pop     rdi
0x180023183  pop     rsi
0x180023184  retn
```
