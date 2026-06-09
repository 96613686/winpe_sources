# CXMLReader::ResolveSymbol(CParseNode *)

- ea: `0x1800287cc`
- end: `0x180028a96`
- name: `?ResolveSymbol@CXMLReader@@AEAAJPEAVCParseNode@@@Z`
- size: `714`
- prototype: `__int64 __fastcall(CXMLReader *__hidden this, struct CParseNode *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180025e20`

## callees

- `0x180016584`
- `0x18001b008`
- `0x180024334`
- `0x180024434`
- `0x1800248d8`
- `0x180026d04`
- `0x1800286bc`
- `0x1800287cc`
- `0x180029dc0`
- `0x18002dca4`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x1800287fd`
- `OLEAUT32!__imp_SysStringLen` at `0x18002883f`
- `OLEAUT32!__imp_SysStringLen` at `0x18002896d`
- `OLEAUT32!__imp_SysStringLen` at `0x1800287fd`
- `OLEAUT32!__imp_SysStringLen` at `0x18002883f`
- `OLEAUT32!__imp_SysStringLen` at `0x18002896d`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CXMLReader::ResolveSymbol(CXMLReader *this, struct CParseNode *a2)
{
  unsigned int v4; // r15d
  BSTR *Value; // r14
  CCollectionList *v6; // rbx
  UINT v7; // eax
  struct CSymbol *v8; // rbx
  CScope *v9; // rbx
  UINT v10; // eax
  int v11; // ebx
  int v12; // r14d
  __int64 v13; // rax
  __int64 v14; // rax
  CCollectionList *v15; // rbx
  UINT v16; // eax
  __int64 v17; // rax
  int v18; // r14d
  __int64 v19; // rax
  struct CSymbol *v21; // [rsp+60h] [rbp+8h] BYREF

  v4 = 0;
  Value = (BSTR *)CParseNode::GetValue(a2);
  v6 = (CCollectionList *)*((_QWORD *)this + 17);
  v7 = SysStringLen(*Value);
  v21 = 0;
  CCollectionList::LookUpByKey(v6, *Value, v7, (unsigned __int64 *)&v21);
  v8 = v21;
  if ( (*((_BYTE *)a2 + 40) & 1) == 0 )
  {
    v9 = (CScope *)*((_QWORD *)this + 17);
    v10 = SysStringLen(*Value);
    v11 = CScope::AddSymbol(v9, *Value, v10, &v21);
    if ( v11 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_180049D10[0] )
          bidTraceW(off_180049208[0], 2240512, off_180049D10[0], (unsigned int)v11, 2188);
      }
      ThrowHR(v11);
    }
    v8 = v21;
    v12 = CXMLReader::BuildRowDefinition(this, a2, *((_DWORD *)a2 + 6), v21);
    if ( v12 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180049D08[0] )
        bidTraceW(off_180049208[0], 2241536, off_180049D08[0], (unsigned int)v12, 2189);
      ThrowHR(v12);
    }
LABEL_28:
    if ( v8 )
    {
      v19 = (unsigned int)(*((_DWORD *)a2 + 11) + 1);
      if ( (unsigned int)v19 < *((_DWORD *)this + 108) )
        CXMLReader::ReduceStack(this, *(struct CParseNode **)(*((_QWORD *)this + 53) + 8 * v19));
      *((_BYTE *)a2 + 40) = 8;
      *((_QWORD *)a2 + 2) = v8;
    }
    return v4;
  }
  if ( !*((_BYTE *)this + 472) || (v13 = *((_QWORD *)this + 17), !*(_DWORD *)(v13 + 16)) )
  {
    if ( !v21 )
      return v4;
LABEL_22:
    v18 = CXMLReader::BuildColumnDefinition(this, a2, v8, 0);
    if ( v18 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180049D00[0] )
        bidTraceW(off_180049208[0], 2276352, off_180049D00[0], (unsigned int)v18, 2223);
      ThrowHR(v18);
    }
    *((_QWORD *)this + 17) = *(_QWORD *)(*((_QWORD *)this + 17) + 48LL);
    goto LABEL_28;
  }
  if ( *(_DWORD *)(v13 + 16) != 1 )
  {
    v4 = Exit(-2147467259, 0x91u);
    if ( (v4 & 0x80000000) != 0 )
      return v4;
  }
  v14 = *((_QWORD *)this + 17);
  if ( *(_DWORD *)(v14 + 16) )
    v8 = **(struct CSymbol ***)(v14 + 8);
  v15 = *(CCollectionList **)(*((_QWORD *)v8 + 1) + 632LL);
  *((_QWORD *)this + 17) = v15;
  v16 = SysStringLen(*Value);
  v21 = 0;
  CCollectionList::LookUpByKey(v15, *Value, v16, (unsigned __int64 *)&v21);
  v8 = v21;
  if ( v21 )
    goto LABEL_22;
  *((_QWORD *)this + 17) = *(_QWORD *)(*((_QWORD *)this + 17) + 48LL);
  v17 = (unsigned int)(*((_DWORD *)a2 + 11) + 1);
  if ( (unsigned int)v17 < *((_DWORD *)this + 108) )
    CXMLReader::ReduceStack(this, *(struct CParseNode **)(*((_QWORD *)this + 53) + 8 * v17));
  return v4;
}

```

## disassembly

```asm
0x1800287cc  mov     [rsp+arg_8], rbx
0x1800287d1  mov     [rsp+arg_10], rsi
0x1800287d6  push    rdi
0x1800287d7  push    r14
0x1800287d9  push    r15
0x1800287db  sub     rsp, 40h
0x1800287df  mov     rsi, rdx
0x1800287e2  mov     rdi, rcx
0x1800287e5  xor     r15d, r15d
0x1800287e8  mov     rcx, rdx; this
0x1800287eb  call    ?GetValue@CParseNode@@QEAAAEAVCComBSTR@ATL@@XZ; CParseNode::GetValue(void)
0x1800287f0  mov     r14, rax
0x1800287f3  mov     rbx, [rdi+88h]
0x1800287fa  mov     rcx, [rax]; pbstr
0x1800287fd  call    cs:__imp_SysStringLen
0x180028804  nop     dword ptr [rax+rax+00h]
0x180028809  mov     [rsp+58h+arg_0], r15
0x18002880e  lea     r9, [rsp+58h+arg_0]; unsigned __int64 *
0x180028813  mov     r8d, eax; unsigned int
0x180028816  mov     rdx, [r14]; unsigned __int16 *
0x180028819  mov     rcx, rbx; this
0x18002881c  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x180028821  mov     rbx, [rsp+58h+arg_0]
0x180028826  mov     [rsp+58h+arg_0], rbx
0x18002882b  test    byte ptr [rsi+28h], 1
0x18002882f  jnz     loc_180028905
0x180028835  mov     rbx, [rdi+88h]
0x18002883c  mov     rcx, [r14]; pbstr
0x18002883f  call    cs:__imp_SysStringLen
0x180028846  nop     dword ptr [rax+rax+00h]
0x18002884b  lea     r9, [rsp+58h+arg_0]; struct CSymbol **
0x180028850  mov     r8d, eax; unsigned int
0x180028853  mov     rdx, [r14]; unsigned __int16 *
0x180028856  mov     rcx, rbx; this
0x180028859  call    ?AddSymbol@CScope@@QEAAJPEAGKPEAPEAVCSymbol@@@Z; CScope::AddSymbol(ushort *,ulong,CSymbol * *)
0x18002885e  mov     ebx, eax
0x180028860  test    eax, eax
0x180028862  jns     short loc_1800288A3
0x180028864  test    byte ptr cs:_bidGblFlags, 2
0x18002886b  jz      short loc_18002889C
0x18002886d  mov     rax, cs:off_180049D10; "<CXMLReader::ResolveSymbol|ADO|ERR>  HR"...
0x180028874  test    rax, rax
0x180028877  jz      short loc_18002889C
0x180028879  mov     [rsp+58h+var_38], 88Ch
0x180028881  mov     r9d, ebx
0x180028884  mov     r8, cs:off_180049D10; "<CXMLReader::ResolveSymbol|ADO|ERR>  HR"...
0x18002888b  mov     edx, 223000h
0x180028890  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180028897  call    _bidTraceW
0x18002889c  mov     ecx, ebx; int
0x18002889e  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800288a3  mov     rbx, [rsp+58h+arg_0]
0x1800288a8  mov     r9, rbx; struct CSymbol *
0x1800288ab  mov     r8d, [rsi+18h]; unsigned int
0x1800288af  mov     rdx, rsi; struct CParseNode *
0x1800288b2  mov     rcx, rdi; this
0x1800288b5  call    ?BuildRowDefinition@CXMLReader@@AEAAJPEAVCParseNode@@KPEAVCSymbol@@@Z; CXMLReader::BuildRowDefinition(CParseNode *,ulong,CSymbol *)
0x1800288ba  mov     r14d, eax
0x1800288bd  test    eax, eax
0x1800288bf  jns     loc_180028A4A
0x1800288c5  test    byte ptr cs:_bidGblFlags, 2
0x1800288cc  jz      short loc_1800288FD
0x1800288ce  mov     rax, cs:off_180049D08; "<CXMLReader::ResolveSymbol|ADO|ERR>  HR"...
0x1800288d5  test    rax, rax
0x1800288d8  jz      short loc_1800288FD
0x1800288da  mov     [rsp+58h+var_38], 88Dh
0x1800288e2  mov     r9d, r14d
0x1800288e5  mov     r8, cs:off_180049D08; "<CXMLReader::ResolveSymbol|ADO|ERR>  HR"...
0x1800288ec  mov     edx, 223400h
0x1800288f1  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800288f8  call    _bidTraceW
0x1800288fd  mov     ecx, r14d; int
0x180028900  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180028905  cmp     byte ptr [rdi+1D8h], 0
0x18002890c  jz      loc_1800289D7
0x180028912  mov     rax, [rdi+88h]
0x180028919  cmp     dword ptr [rax+10h], 0
0x18002891d  jz      loc_1800289D7
0x180028923  cmp     dword ptr [rax+10h], 1
0x180028927  jz      short loc_180028944
0x180028929  mov     edx, 91h; unsigned int
0x18002892e  mov     ecx, 80004005h; int
0x180028933  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180028938  mov     r15d, eax
0x18002893b  test    eax, eax
0x18002893d  jns     short loc_180028944
0x18002893f  jmp     loc_180028A7E
0x180028944  mov     rax, [rdi+88h]
0x18002894b  cmp     dword ptr [rax+10h], 0
0x18002894f  jbe     short loc_180028958
0x180028951  mov     rax, [rax+8]
0x180028955  mov     rbx, [rax]
0x180028958  mov     rax, [rbx+8]
0x18002895c  mov     rbx, [rax+278h]
0x180028963  mov     [rdi+88h], rbx
0x18002896a  mov     rcx, [r14]; pbstr
0x18002896d  call    cs:__imp_SysStringLen
0x180028974  nop     dword ptr [rax+rax+00h]
0x180028979  mov     [rsp+58h+arg_0], 0
0x180028982  lea     r9, [rsp+58h+arg_0]; unsigned __int64 *
0x180028987  mov     r8d, eax; unsigned int
0x18002898a  mov     rdx, [r14]; unsigned __int16 *
0x18002898d  mov     rcx, rbx; this
0x180028990  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x180028995  mov     rbx, [rsp+58h+arg_0]
0x18002899a  test    rbx, rbx
0x18002899d  jnz     short loc_1800289E0
0x18002899f  mov     rax, [rdi+88h]
0x1800289a6  mov     rcx, [rax+30h]
0x1800289aa  mov     [rdi+88h], rcx
0x1800289b1  mov     eax, [rsi+2Ch]
0x1800289b4  inc     eax
0x1800289b6  cmp     eax, [rdi+1B0h]
0x1800289bc  jnb     short loc_1800289D2
0x1800289be  mov     rdx, [rdi+1A8h]
0x1800289c5  mov     rdx, [rdx+rax*8]; struct CParseNode *
0x1800289c9  mov     rcx, rdi; this
0x1800289cc  call    ?ReduceStack@CXMLReader@@AEAAXPEAVCParseNode@@@Z; CXMLReader::ReduceStack(CParseNode *)
0x1800289d1  nop
0x1800289d2  jmp     loc_180028A7E
0x1800289d7  test    rbx, rbx
0x1800289da  jz      loc_180028A77
0x1800289e0  xor     r9d, r9d; struct XMLCHAPTER *
0x1800289e3  mov     r8, rbx; struct CSymbol *
0x1800289e6  mov     rdx, rsi; struct CParseNode *
0x1800289e9  mov     rcx, rdi; this
0x1800289ec  call    ?BuildColumnDefinition@CXMLReader@@AEAAJPEAVCParseNode@@PEAVCSymbol@@PEAVXMLCHAPTER@@@Z; CXMLReader::BuildColumnDefinition(CParseNode *,CSymbol *,XMLCHAPTER *)
0x1800289f1  mov     r14d, eax
0x1800289f4  test    eax, eax
0x1800289f6  jns     short loc_180028A38
0x1800289f8  test    byte ptr cs:_bidGblFlags, 2
0x1800289ff  jz      short loc_180028A30
0x180028a01  mov     rax, cs:off_180049D00; "<CXMLReader::ResolveSymbol|ADO|ERR>  HR"...
0x180028a08  test    rax, rax
0x180028a0b  jz      short loc_180028A30
0x180028a0d  mov     [rsp+58h+var_38], 8AFh
0x180028a15  mov     r9d, r14d
0x180028a18  mov     r8, cs:off_180049D00; "<CXMLReader::ResolveSymbol|ADO|ERR>  HR"...
0x180028a1f  mov     edx, 22BC00h
0x180028a24  mov     rcx, cs:off_180049208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180028a2b  call    _bidTraceW
0x180028a30  mov     ecx, r14d; int
0x180028a33  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180028a38  mov     rax, [rdi+88h]
0x180028a3f  mov     rcx, [rax+30h]
0x180028a43  mov     [rdi+88h], rcx
0x180028a4a  test    rbx, rbx
0x180028a4d  jz      short loc_180028A77
0x180028a4f  mov     eax, [rsi+2Ch]
0x180028a52  inc     eax
0x180028a54  cmp     eax, [rdi+1B0h]
0x180028a5a  jnb     short loc_180028A6F
0x180028a5c  mov     rdx, [rdi+1A8h]
0x180028a63  mov     rdx, [rdx+rax*8]; struct CParseNode *
0x180028a67  mov     rcx, rdi; this
0x180028a6a  call    ?ReduceStack@CXMLReader@@AEAAXPEAVCParseNode@@@Z; CXMLReader::ReduceStack(CParseNode *)
0x180028a6f  mov     byte ptr [rsi+28h], 8
0x180028a73  mov     [rsi+10h], rbx
0x180028a77  jmp     short loc_180028A7E
0x180028a79  mov     r15d, dword ptr [rsp+58h+arg_0]
0x180028a7e  mov     eax, r15d
0x180028a81  mov     rbx, [rsp+58h+arg_8]
0x180028a86  mov     rsi, [rsp+58h+arg_10]
0x180028a8b  add     rsp, 40h
0x180028a8f  pop     r15
0x180028a91  pop     r14
0x180028a93  pop     rdi
0x180028a94  retn
```
