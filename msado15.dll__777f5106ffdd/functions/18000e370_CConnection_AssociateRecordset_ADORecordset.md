# CConnection::AssociateRecordset(_ADORecordset *)

- ea: `0x18000e370`
- end: `0x18000e6cc`
- name: `?AssociateRecordset@CConnection@@UEAAJPEAU_ADORecordset@@@Z`
- size: `860`
- prototype: `__int64 __fastcall(CConnection *__hidden this, struct _ADORecordset *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x18000c700`
- `0x18000cd80`
- `0x18000e370`
- `0x180020fc0`
- `0x180053130`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000e417`
- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000e417`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000e623`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000e623`
- `KERNEL32!TlsSetValue` at `0x18000e3f4`
- `KERNEL32!TlsSetValue` at `0x18000e697`
- `KERNEL32!TlsSetValue` at `0x18000e3f4`
- `KERNEL32!TlsSetValue` at `0x18000e697`
- `KERNEL32!TlsGetValue` at `0x18000e3b0`
- `KERNEL32!TlsGetValue` at `0x18000e3b0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e4de`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e63b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e4de`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e63b`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000e661`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000e661`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CConnection::AssociateRecordset(CConnection *this, struct _ADORecordset *a2)
{
  char *v2; // rdi
  unsigned __int64 v3; // rbx
  _DWORD *Value; // rax
  OLECHAR *v5; // r14
  __int64 v6; // r9
  __int64 v7; // rdx
  char *v8; // rdx
  __int64 v9; // rsi
  unsigned int v10; // edx
  unsigned int v11; // r12d
  int v12; // eax
  int v13; // r15d
  int v14; // r14d
  unsigned int v15; // ebx
  _DWORD *v17; // rax
  IErrorInfo *v18; // rdx
  OLECHAR *v20; // [rsp+30h] [rbp-40h] BYREF
  char v21; // [rsp+38h] [rbp-38h]
  _DWORD *TlsValue; // [rsp+40h] [rbp-30h] BYREF
  int v23; // [rsp+48h] [rbp-28h]
  __int64 v24; // [rsp+50h] [rbp-20h]
  int v25; // [rsp+58h] [rbp-18h]
  __int16 v26; // [rsp+5Ch] [rbp-14h]
  char v27; // [rsp+5Eh] [rbp-12h]
  char *v28; // [rsp+60h] [rbp-10h]
  int v29; // [rsp+68h] [rbp-8h]
  int v30; // [rsp+6Ch] [rbp-4h]
  OLECHAR *v31; // [rsp+B8h] [rbp+48h] BYREF

  v2 = (char *)this + 680;
  v3 = ((unsigned __int64)a2 + 32) & -(__int64)(a2 != 0);
  v28 = (char *)this + 680;
  v30 = 0;
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = Value;
  v29 = 0;
  if ( Value )
  {
    ++Value[2];
  }
  else
  {
    v23 = 1;
    v24 = 0;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  v31 = 0;
  v5 = 0;
  v21 = 6;
  CReaderWriterLock3AR::WriteLock((CReaderWriterLock3AR *)(v2 + 72));
  v29 = (*(__int64 (__fastcall **)(char *, _QWORD, __int64))(*(_QWORD *)v2 + 128LL))(v2, 0, 1);
  if ( v29 < 0 )
  {
    CContext::PushError((CContext *)&TlsValue);
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_30;
    v6 = 321;
    v7 = 328713;
    goto LABEL_7;
  }
  v8 = (char *)*((_QWORD *)v2 + 4);
  if ( v2 == v8 )
    v8 = 0;
  (*(void (__fastcall **)(unsigned __int64, char *))(*(_QWORD *)v3 + 152LL))(v3, v8);
  v29 = (*(__int64 (__fastcall **)(unsigned __int64, OLECHAR **))(*(_QWORD *)v3 + 176LL))(v3, &v31);
  if ( v29 >= 0 )
  {
    v5 = v31;
    SysFreeString(0);
    v20 = v5;
    (*(void (__fastcall **)(char *, unsigned __int64))(*(_QWORD *)v2 + 344LL))(v2, v3);
    v9 = *((_QWORD *)v2 + 8);
    v10 = 0;
    v11 = *(_DWORD *)(v9 + 16);
    while ( v10 < v11 )
    {
      if ( *(_QWORD *)(*(_QWORD *)(v9 + 8) + 8LL * v10) == v3 )
      {
        if ( (bidGblFlags & 2) != 0 )
          bidTraceW(
            off_18012A218[0],
            1358857,
            L"<CCollectionList::Append|ADO|ERR> 0x%08x{HRESULT} line %d\n",
            2148142375LL,
            1327);
        v29 = -2146824921;
        goto LABEL_26;
      }
      ++v10;
    }
    v12 = CCollectionArray::Insert(*((CCollectionArray **)v2 + 8), v11, v3);
    v13 = v12;
    if ( v12 >= 0 )
    {
      v14 = CCollectionMap::Insert((CCollectionMap *)(v9 + 24), (const struct CSysString *)&v20, v3);
      if ( v14 >= 0 )
      {
        v29 = v14;
        v5 = v20;
        goto LABEL_30;
      }
      CCollectionArray::Delete((CCollectionArray *)v9, v11);
      v29 = v14;
      v5 = v20;
    }
    else
    {
      if ( (bidGblFlags & 2) != 0 )
        bidTraceW(
          off_18012A218[0],
          1380361,
          L"<CCollectionList::Insert|ADO|ERR> 0x%08x{HRESULT} line %d\n",
          (unsigned int)v12,
          1348);
      v29 = v13;
    }
LABEL_26:
    CContext::PushError((CContext *)&TlsValue);
    if ( (bidGblFlags & 2) != 0 )
      bidTraceW(off_18012A1B8[0], 350217, L"<CStdCollection::Append|ADO|ERR>  line %d\n", 342);
    (*(void (__fastcall **)(char *, unsigned __int64))(*(_QWORD *)v2 + 352LL))(v2, v3);
  }
  else
  {
    CContext::PushError((CContext *)&TlsValue);
    if ( (bidGblFlags & 2) != 0 )
    {
      v6 = 332;
      v7 = 339977;
LABEL_7:
      bidTraceW(off_18012A1B8[0], v7, L"<CStdCollection::Append|ADO|ERR>  line %d\n", v6);
    }
  }
LABEL_30:
  CReaderWriterLock3AR::WriteUnlock((CReaderWriterLock3AR *)(v2 + 72));
  v15 = v29;
  if ( (v21 & 2) != 0 )
    SysFreeString(v5);
  if ( TlsValue[2]-- == 1 )
  {
    v17 = TlsValue;
    v18 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
    if ( v18 )
    {
      SetErrorInfo(0, v18);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
      v17 = TlsValue;
    }
    if ( *((_BYTE *)v17 + 30) )
    {
      *((_QWORD *)v17 + 2) = 0;
      TlsValue[6] = 0;
    }
    else
    {
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
    }
  }
  return v15;
}

```

## disassembly

```asm
0x18000e370  mov     [rsp-38h+arg_10], rbx
0x18000e375  push    rbp
0x18000e376  push    rsi
0x18000e377  push    rdi
0x18000e378  push    r12
0x18000e37a  push    r13
0x18000e37c  push    r14
0x18000e37e  push    r15
0x18000e380  mov     rbp, rsp
0x18000e383  sub     rsp, 70h
0x18000e387  lea     rdi, [rcx+2A8h]
0x18000e38e  lea     rax, [rdx+20h]
0x18000e392  neg     rdx
0x18000e395  sbb     rbx, rbx
0x18000e398  and     rbx, rax
0x18000e39b  mov     [rbp+var_10], rdi
0x18000e39f  xor     r15d, r15d
0x18000e3a2  mov     [rbp+var_4], r15d
0x18000e3a6  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18000e3ad  mov     ecx, [rcx+14h]; dwTlsIndex
0x18000e3b0  call    cs:__imp_TlsGetValue
0x18000e3b7  nop     dword ptr [rax+rax+00h]
0x18000e3bc  mov     [rbp+TlsValue], rax
0x18000e3c0  mov     [rbp+var_8], r15d
0x18000e3c4  test    rax, rax
0x18000e3c7  jz      short loc_18000E3CE
0x18000e3c9  inc     dword ptr [rax+8]
0x18000e3cc  jmp     short loc_18000E408
0x18000e3ce  mov     [rbp+var_28], 1
0x18000e3d5  mov     [rbp+var_20], r15
0x18000e3d9  mov     [rbp+var_18], r15d
0x18000e3dd  mov     [rbp+var_14], r15w
0x18000e3e2  mov     [rbp+var_12], r15b
0x18000e3e6  lea     rdx, [rbp+TlsValue]; lpTlsValue
0x18000e3ea  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18000e3f1  mov     ecx, [rcx+14h]; dwTlsIndex
0x18000e3f4  call    cs:__imp_TlsSetValue
0x18000e3fb  nop     dword ptr [rax+rax+00h]
0x18000e400  lea     rax, [rbp+TlsValue]
0x18000e404  mov     [rbp+TlsValue], rax
0x18000e408  mov     [rbp+arg_8], r15
0x18000e40c  mov     r14, r15
0x18000e40f  mov     [rbp+var_38], 6
0x18000e413  lea     rcx, [rdi+48h]
0x18000e417  call    cs:__imp_?WriteLock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteLock(void)
0x18000e41e  nop     dword ptr [rax+rax+00h]
0x18000e423  mov     rax, [rdi]
0x18000e426  xor     edx, edx
0x18000e428  lea     r8d, [rdx+1]
0x18000e42c  mov     rcx, rdi
0x18000e42f  mov     rax, [rax+80h]
0x18000e436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e43b  mov     [rbp+var_8], eax
0x18000e43e  test    eax, eax
0x18000e440  jns     short loc_18000E47B
0x18000e442  lea     rcx, [rbp+TlsValue]; this
0x18000e446  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18000e44b  test    byte ptr cs:_bidGblFlags, 2
0x18000e452  jz      loc_18000E61F
0x18000e458  mov     r9d, 141h
0x18000e45e  mov     edx, 50409h
0x18000e463  lea     r8, aCstdcollection; "<CStdCollection::Append|ADO|ERR>  line "...
0x18000e46a  mov     rcx, cs:off_18012A1B8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18000e471  call    _bidTraceW
0x18000e476  jmp     loc_18000E61F
0x18000e47b  mov     rax, [rbx]
0x18000e47e  mov     rdx, [rdi+20h]
0x18000e482  cmp     rdi, rdx
0x18000e485  cmovz   rdx, r15
0x18000e489  mov     rcx, rbx
0x18000e48c  mov     rax, [rax+98h]
0x18000e493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e498  mov     rax, [rbx]
0x18000e49b  lea     rdx, [rbp+arg_8]
0x18000e49f  mov     rcx, rbx
0x18000e4a2  mov     rax, [rax+0B0h]
0x18000e4a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4ae  mov     [rbp+var_8], eax
0x18000e4b1  test    eax, eax
0x18000e4b3  jns     short loc_18000E4D8
0x18000e4b5  lea     rcx, [rbp+TlsValue]; this
0x18000e4b9  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18000e4be  test    byte ptr cs:_bidGblFlags, 2
0x18000e4c5  jz      loc_18000E61F
0x18000e4cb  mov     r9d, 14Ch
0x18000e4d1  mov     edx, 53009h
0x18000e4d6  jmp     short loc_18000E463
0x18000e4d8  mov     r14, [rbp+arg_8]
0x18000e4dc  xor     ecx, ecx; bstrString
0x18000e4de  call    cs:__imp_SysFreeString
0x18000e4e5  nop     dword ptr [rax+rax+00h]
0x18000e4ea  mov     [rbp+var_40], r14
0x18000e4ee  mov     rax, [rdi]
0x18000e4f1  mov     rdx, rbx
0x18000e4f4  mov     rcx, rdi
0x18000e4f7  mov     rax, [rax+158h]
0x18000e4fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e503  mov     rsi, [rdi+40h]
0x18000e507  mov     edx, r15d
0x18000e50a  mov     r12d, [rsi+10h]
0x18000e50e  cmp     edx, r12d
0x18000e511  jnb     short loc_18000E559
0x18000e513  mov     ecx, edx
0x18000e515  mov     rax, [rsi+8]
0x18000e519  cmp     [rax+rcx*8], rbx
0x18000e51d  jz      short loc_18000E523
0x18000e51f  inc     edx
0x18000e521  jmp     short loc_18000E50E
0x18000e523  mov     esi, 800A0D27h
0x18000e528  test    byte ptr cs:_bidGblFlags, 2
0x18000e52f  jz      short loc_18000E554
0x18000e531  mov     [rsp+70h+var_50], 52Fh
0x18000e539  mov     r9d, esi
0x18000e53c  lea     r8, aCcollectionlis_0; "<CCollectionList::Append|ADO|ERR> 0x%08"...
0x18000e543  mov     edx, 14BC09h
0x18000e548  mov     rcx, cs:off_18012A218; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18000e54f  call    _bidTraceW
0x18000e554  mov     [rbp+var_8], esi
0x18000e557  jmp     short loc_18000E5D0
0x18000e559  mov     r8, rbx; unsigned __int64
0x18000e55c  mov     edx, r12d; unsigned int
0x18000e55f  mov     rcx, rsi; this
0x18000e562  call    ?Insert@CCollectionArray@@QEAAJK_K@Z; CCollectionArray::Insert(ulong,unsigned __int64)
0x18000e567  mov     r15d, eax
0x18000e56a  test    eax, eax
0x18000e56c  jns     short loc_18000E5A3
0x18000e56e  test    byte ptr cs:_bidGblFlags, 2
0x18000e575  jz      short loc_18000E59A
0x18000e577  mov     [rsp+70h+var_50], 544h
0x18000e57f  mov     r9d, eax
0x18000e582  lea     r8, aCcollectionlis_3; "<CCollectionList::Insert|ADO|ERR> 0x%08"...
0x18000e589  mov     edx, 151009h
0x18000e58e  mov     rcx, cs:off_18012A218; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18000e595  call    _bidTraceW
0x18000e59a  mov     [rbp+var_8], r15d
0x18000e59e  xor     r15d, r15d
0x18000e5a1  jmp     short loc_18000E5D0
0x18000e5a3  lea     rcx, [rsi+18h]; this
0x18000e5a7  mov     r8, rbx; unsigned __int64
0x18000e5aa  lea     rdx, [rbp+var_40]; struct CSysString *
0x18000e5ae  call    ?Insert@CCollectionMap@@QEAAJAEBVCSysString@@_K@Z; CCollectionMap::Insert(CSysString const &,unsigned __int64)
0x18000e5b3  mov     r14d, eax
0x18000e5b6  xor     r15d, r15d
0x18000e5b9  test    eax, eax
0x18000e5bb  jns     short loc_18000E617
0x18000e5bd  mov     edx, r12d; unsigned int
0x18000e5c0  mov     rcx, rsi; this
0x18000e5c3  call    ?Delete@CCollectionArray@@QEAAJK@Z; CCollectionArray::Delete(ulong)
0x18000e5c8  mov     [rbp+var_8], r14d
0x18000e5cc  mov     r14, [rbp+var_40]
0x18000e5d0  lea     rcx, [rbp+TlsValue]; this
0x18000e5d4  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18000e5d9  test    byte ptr cs:_bidGblFlags, 2
0x18000e5e0  jz      short loc_18000E600
0x18000e5e2  mov     r9d, 156h
0x18000e5e8  lea     r8, aCstdcollection; "<CStdCollection::Append|ADO|ERR>  line "...
0x18000e5ef  mov     edx, 55809h
0x18000e5f4  mov     rcx, cs:off_18012A1B8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18000e5fb  call    _bidTraceW
0x18000e600  mov     rax, [rdi]
0x18000e603  mov     rdx, rbx
0x18000e606  mov     rcx, rdi
0x18000e609  mov     rax, [rax+160h]
0x18000e610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e615  jmp     short loc_18000E61F
0x18000e617  mov     [rbp+var_8], r14d
0x18000e61b  mov     r14, [rbp+var_40]
0x18000e61f  lea     rcx, [rdi+48h]
0x18000e623  call    cs:__imp_?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteUnlock(void)
0x18000e62a  nop     dword ptr [rax+rax+00h]
0x18000e62f  mov     ebx, [rbp+var_8]
0x18000e632  test    [rbp+var_38], 2
0x18000e636  jz      short loc_18000E648
0x18000e638  mov     rcx, r14; bstrString
0x18000e63b  call    cs:__imp_SysFreeString
0x18000e642  nop     dword ptr [rax+rax+00h]
0x18000e647  nop
0x18000e648  mov     rax, [rbp+TlsValue]
0x18000e64c  add     dword ptr [rax+8], 0FFFFFFFFh
0x18000e650  jnz     short loc_18000E6B1
0x18000e652  mov     rax, [rbp+TlsValue]
0x18000e656  mov     rdx, [rax+10h]; perrinfo
0x18000e65a  test    rdx, rdx
0x18000e65d  jz      short loc_18000E685
0x18000e65f  xor     ecx, ecx; dwReserved
0x18000e661  call    cs:__imp_SetErrorInfo
0x18000e668  nop     dword ptr [rax+rax+00h]
0x18000e66d  mov     rax, [rbp+TlsValue]
0x18000e671  mov     rcx, [rax+10h]
0x18000e675  mov     rax, [rcx]
0x18000e678  mov     rax, [rax+10h]
0x18000e67c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e681  mov     rax, [rbp+TlsValue]
0x18000e685  cmp     [rax+1Eh], r15b
0x18000e689  jnz     short loc_18000E6A5
0x18000e68b  xor     edx, edx; lpTlsValue
0x18000e68d  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18000e694  mov     ecx, [rcx+14h]; dwTlsIndex
0x18000e697  call    cs:__imp_TlsSetValue
0x18000e69e  nop     dword ptr [rax+rax+00h]
0x18000e6a3  jmp     short loc_18000E6B1
0x18000e6a5  mov     [rax+10h], r15
0x18000e6a9  mov     rcx, [rbp+TlsValue]
0x18000e6ad  mov     [rcx+18h], r15d
0x18000e6b1  mov     eax, ebx
0x18000e6b3  mov     rbx, [rsp+70h+arg_10]
0x18000e6bb  add     rsp, 70h
0x18000e6bf  pop     r15
0x18000e6c1  pop     r14
0x18000e6c3  pop     r13
0x18000e6c5  pop     r12
0x18000e6c7  pop     rdi
0x18000e6c8  pop     rsi
0x18000e6c9  pop     rbp
0x18000e6ca  retn
```
