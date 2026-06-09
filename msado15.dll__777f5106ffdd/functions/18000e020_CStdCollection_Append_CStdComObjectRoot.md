# CStdCollection::Append(CStdComObjectRoot *)

- ea: `0x18000e020`
- end: `0x18000e362`
- name: `?Append@CStdCollection@@UEAAJPEAVCStdComObjectRoot@@@Z`
- size: `834`
- prototype: `int(CStdCollection *__hidden this, struct CStdComObjectRoot *)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003fbd0`
- `0x180066650`
- `0x18009a100`
- `0x18009cd6c`
- `0x18009f2d0`

## callees

- `0x18000c700`
- `0x18000cd80`
- `0x18000e020`
- `0x180020fc0`
- `0x180053130`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000e0ba`
- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000e0ba`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000e2b8`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000e2b8`
- `KERNEL32!TlsSetValue` at `0x18000e096`
- `KERNEL32!TlsSetValue` at `0x18000e32d`
- `KERNEL32!TlsSetValue` at `0x18000e096`
- `KERNEL32!TlsSetValue` at `0x18000e32d`
- `KERNEL32!TlsGetValue` at `0x18000e052`
- `KERNEL32!TlsGetValue` at `0x18000e052`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e185`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e2d1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e185`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e2d1`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000e2f7`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000e2f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CStdCollection::Append(CStdCollection *this, struct CStdComObjectRoot *a2)
{
  _DWORD *Value; // rax
  __int64 v5; // r9
  __int64 v6; // rdx
  CStdCollection *v7; // rdx
  OLECHAR *v8; // rbx
  __int64 v9; // rbx
  unsigned int v10; // edx
  unsigned int v11; // r15d
  int v12; // eax
  int v13; // r14d
  unsigned int v14; // ebx
  _DWORD *v16; // rax
  IErrorInfo *v17; // rdx
  BSTR bstrString; // [rsp+30h] [rbp-40h] BYREF
  char v20; // [rsp+38h] [rbp-38h]
  _DWORD *TlsValue; // [rsp+40h] [rbp-30h] BYREF
  int v22; // [rsp+48h] [rbp-28h]
  __int64 v23; // [rsp+50h] [rbp-20h]
  int v24; // [rsp+58h] [rbp-18h]
  __int16 v25; // [rsp+5Ch] [rbp-14h]
  char v26; // [rsp+5Eh] [rbp-12h]
  CStdCollection *v27; // [rsp+60h] [rbp-10h]
  int v28; // [rsp+68h] [rbp-8h]
  int v29; // [rsp+6Ch] [rbp-4h]
  OLECHAR *v30; // [rsp+C0h] [rbp+50h] BYREF

  v27 = this;
  v29 = 0;
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = Value;
  v28 = 0;
  if ( Value )
  {
    ++Value[2];
  }
  else
  {
    v22 = 1;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v26 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  v30 = 0;
  bstrString = 0;
  v20 = 6;
  CReaderWriterLock3AR::WriteLock((CStdCollection *)((char *)this + 72));
  v28 = (*(__int64 (__fastcall **)(CStdCollection *, _QWORD, __int64))(*(_QWORD *)this + 128LL))(this, 0, 1);
  if ( v28 < 0 )
  {
    CContext::PushError((CContext *)&TlsValue);
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_30;
    v5 = 321;
    v6 = 328713;
    goto LABEL_7;
  }
  v7 = (CStdCollection *)*((_QWORD *)this + 4);
  if ( this == v7 )
    v7 = 0;
  (*(void (__fastcall **)(struct CStdComObjectRoot *, CStdCollection *))(*(_QWORD *)a2 + 152LL))(a2, v7);
  v28 = (*(__int64 (__fastcall **)(struct CStdComObjectRoot *, OLECHAR **))(*(_QWORD *)a2 + 176LL))(a2, &v30);
  if ( v28 >= 0 )
  {
    v8 = v30;
    v20 = 6;
    SysFreeString(0);
    bstrString = v8;
    (*(void (__fastcall **)(CStdCollection *, struct CStdComObjectRoot *))(*(_QWORD *)this + 344LL))(this, a2);
    v9 = *((_QWORD *)this + 8);
    v10 = 0;
    v11 = *(_DWORD *)(v9 + 16);
    while ( v10 < v11 )
    {
      if ( *(struct CStdComObjectRoot **)(*(_QWORD *)(v9 + 8) + 8LL * v10) == a2 )
      {
        if ( (bidGblFlags & 2) != 0 )
          bidTraceW(
            off_18012A218[0],
            1358857,
            L"<CCollectionList::Append|ADO|ERR> 0x%08x{HRESULT} line %d\n",
            2148142375LL,
            1327);
        v28 = -2146824921;
        goto LABEL_26;
      }
      ++v10;
    }
    v12 = CCollectionArray::Insert(*((CCollectionArray **)this + 8), v11, (unsigned __int64)a2);
    v13 = v12;
    if ( v12 >= 0 )
    {
      v13 = CCollectionMap::Insert(
              (CCollectionMap *)(v9 + 24),
              (const struct CSysString *)&bstrString,
              (unsigned __int64)a2);
      if ( v13 >= 0 )
      {
        v28 = v13;
        goto LABEL_30;
      }
      CCollectionArray::Delete((CCollectionArray *)v9, v11);
    }
    else if ( (bidGblFlags & 2) != 0 )
    {
      bidTraceW(
        off_18012A218[0],
        1380361,
        L"<CCollectionList::Insert|ADO|ERR> 0x%08x{HRESULT} line %d\n",
        (unsigned int)v12,
        1348);
    }
    v28 = v13;
LABEL_26:
    CContext::PushError((CContext *)&TlsValue);
    if ( (bidGblFlags & 2) != 0 )
      bidTraceW(off_18012A1B8[0], 350217, L"<CStdCollection::Append|ADO|ERR>  line %d\n", 342);
    (*(void (__fastcall **)(CStdCollection *, struct CStdComObjectRoot *))(*(_QWORD *)this + 352LL))(this, a2);
  }
  else
  {
    CContext::PushError((CContext *)&TlsValue);
    if ( (bidGblFlags & 2) != 0 )
    {
      v5 = 332;
      v6 = 339977;
LABEL_7:
      bidTraceW(off_18012A1B8[0], v6, L"<CStdCollection::Append|ADO|ERR>  line %d\n", v5);
    }
  }
LABEL_30:
  CReaderWriterLock3AR::WriteUnlock((CStdCollection *)((char *)this + 72));
  v14 = v28;
  if ( (v20 & 2) != 0 )
    SysFreeString(bstrString);
  if ( TlsValue[2]-- == 1 )
  {
    v16 = TlsValue;
    v17 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
    if ( v17 )
    {
      SetErrorInfo(0, v17);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
      v16 = TlsValue;
    }
    if ( *((_BYTE *)v16 + 30) )
    {
      *((_QWORD *)v16 + 2) = 0;
      TlsValue[6] = 0;
    }
    else
    {
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
    }
  }
  return v14;
}

```

## disassembly

```asm
0x18000e020  mov     [rsp-38h+arg_8], rbx
0x18000e025  push    rbp
0x18000e026  push    rsi
0x18000e027  push    rdi
0x18000e028  push    r12
0x18000e02a  push    r13
0x18000e02c  push    r14
0x18000e02e  push    r15
0x18000e030  mov     rbp, rsp
0x18000e033  sub     rsp, 70h
0x18000e037  mov     rsi, rdx
0x18000e03a  mov     rdi, rcx
0x18000e03d  mov     [rbp+var_10], rcx
0x18000e041  xor     r13d, r13d
0x18000e044  mov     [rbp+var_4], r13d
0x18000e048  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18000e04f  mov     ecx, [rcx+14h]; dwTlsIndex
0x18000e052  call    cs:__imp_TlsGetValue
0x18000e059  nop     dword ptr [rax+rax+00h]
0x18000e05e  mov     [rbp+TlsValue], rax
0x18000e062  mov     [rbp+var_8], r13d
0x18000e066  test    rax, rax
0x18000e069  jz      short loc_18000E070
0x18000e06b  inc     dword ptr [rax+8]
0x18000e06e  jmp     short loc_18000E0AA
0x18000e070  mov     [rbp+var_28], 1
0x18000e077  mov     [rbp+var_20], r13
0x18000e07b  mov     [rbp+var_18], r13d
0x18000e07f  mov     [rbp+var_14], r13w
0x18000e084  mov     [rbp+var_12], r13b
0x18000e088  lea     rdx, [rbp+TlsValue]; lpTlsValue
0x18000e08c  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18000e093  mov     ecx, [rcx+14h]; dwTlsIndex
0x18000e096  call    cs:__imp_TlsSetValue
0x18000e09d  nop     dword ptr [rax+rax+00h]
0x18000e0a2  lea     rax, [rbp+TlsValue]
0x18000e0a6  mov     [rbp+TlsValue], rax
0x18000e0aa  mov     [rbp+arg_10], r13
0x18000e0ae  mov     [rbp+bstrString], r13
0x18000e0b2  mov     [rbp+var_38], 6
0x18000e0b6  lea     rcx, [rdi+48h]
0x18000e0ba  call    cs:__imp_?WriteLock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteLock(void)
0x18000e0c1  nop     dword ptr [rax+rax+00h]
0x18000e0c6  mov     rax, [rdi]
0x18000e0c9  xor     edx, edx
0x18000e0cb  lea     r8d, [rdx+1]
0x18000e0cf  mov     rcx, rdi
0x18000e0d2  mov     rax, [rax+80h]
0x18000e0d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0de  mov     [rbp+var_8], eax
0x18000e0e1  test    eax, eax
0x18000e0e3  jns     short loc_18000E11E
0x18000e0e5  lea     rcx, [rbp+TlsValue]; this
0x18000e0e9  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18000e0ee  test    byte ptr cs:_bidGblFlags, 2
0x18000e0f5  jz      loc_18000E2B4
0x18000e0fb  mov     r9d, 141h
0x18000e101  mov     edx, 50409h
0x18000e106  lea     r8, aCstdcollection; "<CStdCollection::Append|ADO|ERR>  line "...
0x18000e10d  mov     rcx, cs:off_18012A1B8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18000e114  call    _bidTraceW
0x18000e119  jmp     loc_18000E2B4
0x18000e11e  mov     rax, [rsi]
0x18000e121  mov     rdx, [rdi+20h]
0x18000e125  cmp     rdi, rdx
0x18000e128  cmovz   rdx, r13
0x18000e12c  mov     rcx, rsi
0x18000e12f  mov     rax, [rax+98h]
0x18000e136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e13b  mov     rax, [rsi]
0x18000e13e  lea     rdx, [rbp+arg_10]
0x18000e142  mov     rcx, rsi
0x18000e145  mov     rax, [rax+0B0h]
0x18000e14c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e151  mov     [rbp+var_8], eax
0x18000e154  test    eax, eax
0x18000e156  jns     short loc_18000E17B
0x18000e158  lea     rcx, [rbp+TlsValue]; this
0x18000e15c  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18000e161  test    byte ptr cs:_bidGblFlags, 2
0x18000e168  jz      loc_18000E2B4
0x18000e16e  mov     r9d, 14Ch
0x18000e174  mov     edx, 53009h
0x18000e179  jmp     short loc_18000E106
0x18000e17b  mov     rbx, [rbp+arg_10]
0x18000e17f  mov     [rbp+var_38], 6
0x18000e183  xor     ecx, ecx; bstrString
0x18000e185  call    cs:__imp_SysFreeString
0x18000e18c  nop     dword ptr [rax+rax+00h]
0x18000e191  mov     [rbp+bstrString], rbx
0x18000e195  mov     rax, [rdi]
0x18000e198  mov     rdx, rsi
0x18000e19b  mov     rcx, rdi
0x18000e19e  mov     rax, [rax+158h]
0x18000e1a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1aa  mov     rbx, [rdi+40h]
0x18000e1ae  mov     edx, r13d
0x18000e1b1  mov     r15d, [rbx+10h]
0x18000e1b5  cmp     edx, r15d
0x18000e1b8  jnb     short loc_18000E200
0x18000e1ba  mov     ecx, edx
0x18000e1bc  mov     rax, [rbx+8]
0x18000e1c0  cmp     [rax+rcx*8], rsi
0x18000e1c4  jz      short loc_18000E1CA
0x18000e1c6  inc     edx
0x18000e1c8  jmp     short loc_18000E1B5
0x18000e1ca  mov     ebx, 800A0D27h
0x18000e1cf  test    byte ptr cs:_bidGblFlags, 2
0x18000e1d6  jz      short loc_18000E1FB
0x18000e1d8  mov     [rsp+70h+var_50], 52Fh
0x18000e1e0  mov     r9d, ebx
0x18000e1e3  lea     r8, aCcollectionlis_0; "<CCollectionList::Append|ADO|ERR> 0x%08"...
0x18000e1ea  mov     edx, 14BC09h
0x18000e1ef  mov     rcx, cs:off_18012A218; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18000e1f6  call    _bidTraceW
0x18000e1fb  mov     [rbp+var_8], ebx
0x18000e1fe  jmp     short loc_18000E269
0x18000e200  mov     r8, rsi; unsigned __int64
0x18000e203  mov     edx, r15d; unsigned int
0x18000e206  mov     rcx, rbx; this
0x18000e209  call    ?Insert@CCollectionArray@@QEAAJK_K@Z; CCollectionArray::Insert(ulong,unsigned __int64)
0x18000e20e  mov     r14d, eax
0x18000e211  test    eax, eax
0x18000e213  jns     short loc_18000E243
0x18000e215  test    byte ptr cs:_bidGblFlags, 2
0x18000e21c  jz      short loc_18000E265
0x18000e21e  mov     [rsp+70h+var_50], 544h
0x18000e226  mov     r9d, eax
0x18000e229  lea     r8, aCcollectionlis_3; "<CCollectionList::Insert|ADO|ERR> 0x%08"...
0x18000e230  mov     edx, 151009h
0x18000e235  mov     rcx, cs:off_18012A218; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18000e23c  call    _bidTraceW
0x18000e241  jmp     short loc_18000E265
0x18000e243  lea     rcx, [rbx+18h]; this
0x18000e247  mov     r8, rsi; unsigned __int64
0x18000e24a  lea     rdx, [rbp+bstrString]; struct CSysString *
0x18000e24e  call    ?Insert@CCollectionMap@@QEAAJAEBVCSysString@@_K@Z; CCollectionMap::Insert(CSysString const &,unsigned __int64)
0x18000e253  mov     r14d, eax
0x18000e256  test    eax, eax
0x18000e258  jns     short loc_18000E2B0
0x18000e25a  mov     edx, r15d; unsigned int
0x18000e25d  mov     rcx, rbx; this
0x18000e260  call    ?Delete@CCollectionArray@@QEAAJK@Z; CCollectionArray::Delete(ulong)
0x18000e265  mov     [rbp+var_8], r14d
0x18000e269  lea     rcx, [rbp+TlsValue]; this
0x18000e26d  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18000e272  test    byte ptr cs:_bidGblFlags, 2
0x18000e279  jz      short loc_18000E299
0x18000e27b  mov     r9d, 156h
0x18000e281  lea     r8, aCstdcollection; "<CStdCollection::Append|ADO|ERR>  line "...
0x18000e288  mov     edx, 55809h
0x18000e28d  mov     rcx, cs:off_18012A1B8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18000e294  call    _bidTraceW
0x18000e299  mov     rax, [rdi]
0x18000e29c  mov     rdx, rsi
0x18000e29f  mov     rcx, rdi
0x18000e2a2  mov     rax, [rax+160h]
0x18000e2a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2ae  jmp     short loc_18000E2B4
0x18000e2b0  mov     [rbp+var_8], r14d
0x18000e2b4  lea     rcx, [rdi+48h]
0x18000e2b8  call    cs:__imp_?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteUnlock(void)
0x18000e2bf  nop     dword ptr [rax+rax+00h]
0x18000e2c4  mov     ebx, [rbp+var_8]
0x18000e2c7  test    [rbp+var_38], 2
0x18000e2cb  jz      short loc_18000E2DE
0x18000e2cd  mov     rcx, [rbp+bstrString]; bstrString
0x18000e2d1  call    cs:__imp_SysFreeString
0x18000e2d8  nop     dword ptr [rax+rax+00h]
0x18000e2dd  nop
0x18000e2de  mov     rax, [rbp+TlsValue]
0x18000e2e2  add     dword ptr [rax+8], 0FFFFFFFFh
0x18000e2e6  jnz     short loc_18000E347
0x18000e2e8  mov     rax, [rbp+TlsValue]
0x18000e2ec  mov     rdx, [rax+10h]; perrinfo
0x18000e2f0  test    rdx, rdx
0x18000e2f3  jz      short loc_18000E31B
0x18000e2f5  xor     ecx, ecx; dwReserved
0x18000e2f7  call    cs:__imp_SetErrorInfo
0x18000e2fe  nop     dword ptr [rax+rax+00h]
0x18000e303  mov     rax, [rbp+TlsValue]
0x18000e307  mov     rcx, [rax+10h]
0x18000e30b  mov     rax, [rcx]
0x18000e30e  mov     rax, [rax+10h]
0x18000e312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e317  mov     rax, [rbp+TlsValue]
0x18000e31b  cmp     [rax+1Eh], r13b
0x18000e31f  jnz     short loc_18000E33B
0x18000e321  xor     edx, edx; lpTlsValue
0x18000e323  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18000e32a  mov     ecx, [rcx+14h]; dwTlsIndex
0x18000e32d  call    cs:__imp_TlsSetValue
0x18000e334  nop     dword ptr [rax+rax+00h]
0x18000e339  jmp     short loc_18000E347
0x18000e33b  mov     [rax+10h], r13
0x18000e33f  mov     rcx, [rbp+TlsValue]
0x18000e343  mov     [rcx+18h], r13d
0x18000e347  mov     eax, ebx
0x18000e349  mov     rbx, [rsp+70h+arg_8]
0x18000e351  add     rsp, 70h
0x18000e355  pop     r15
0x18000e357  pop     r14
0x18000e359  pop     r13
0x18000e35b  pop     r12
0x18000e35d  pop     rdi
0x18000e35e  pop     rsi
0x18000e35f  pop     rbp
0x18000e360  retn
```
