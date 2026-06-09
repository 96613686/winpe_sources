# CRecordset::MoveRelative(__int64)

- ea: `0x180003fa0`
- end: `0x18000440f`
- name: `?MoveRelative@CRecordset@@AEAAJ_J@Z`
- size: `1135`
- prototype: `__int64 __fastcall(CRecordset *__hidden this, __int64)`
- caller_count: `7`
- callee_count: `10`
- tags: ``

## callers

- `0x180002990`
- `0x180003b00`
- `0x18000a320`
- `0x1800604c4`
- `0x1800ae220`
- `0x1800b5d64`
- `0x1800b5efc`

## callees

- `0x180003fa0`
- `0x180004418`
- `0x1800046d0`
- `0x180004de0`
- `0x180006610`
- `0x18000a320`
- `0x18006a22c`
- `0x1800c8f34`
- `0x1800cdad2`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x1800042b4`
- `MSDART!MpHeapAlloc` at `0x1800042b4`
- `MSDART!MpHeapFree` at `0x1800043b8`
- `MSDART!MpHeapFree` at `0x1800043b8`

## string_xrefs

- `0x18000411e`: `<CRecordset::MoveRelative|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x1800041af`: `<CRecordset::MoveRelative|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x180004222`: `<CRecordset::MoveRelative|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x1800043fb`: `<CRecordset::MoveRelative|ADO|ERR> 0x%08x{HRESULT} line %d\n`

## pseudocode

```c
__int64 __fastcall CRecordset::MoveRelative(CRecordset *this, unsigned __int64 a2)
{
  int v2; // r13d
  __int64 v3; // r14
  __int64 v6; // rcx
  _BOOL8 v7; // rbp
  __int64 v8; // rax
  __int64 v9; // rdi
  __int64 v10; // rsi
  unsigned int NextRecords; // ebp
  unsigned __int8 *v13; // r12
  size_t v14; // rsi
  char v15; // al
  int v16; // ecx
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int BidObjectID; // eax
  size_t v20; // r9
  void *v21; // rax
  __int64 v22; // r14
  unsigned __int8 *v23; // rax
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // [rsp+20h] [rbp-48h]
  size_t Size; // [rsp+70h] [rbp+8h] BYREF
  void *v28; // [rsp+78h] [rbp+10h] BYREF
  void *Src; // [rsp+80h] [rbp+18h]

  v2 = 0;
  v3 = 1;
  v28 = 0;
  if ( *((_BYTE *)this + 1506) == 1 )
    CRecordset::_MoveFirst(this, 0, 1);
  v6 = *((_QWORD *)this + 91);
  v7 = a2 >> 63;
  v8 = -(__int64)a2;
  if ( !*((_BYTE *)this + 752) )
    v8 = a2;
  v9 = v8 + v6;
  if ( **((_DWORD **)this + 186) == 1 )
  {
    NextRecords = CRecordset::PositionInGroupFilter(this, v9, v7);
    if ( (NextRecords & 0x80000000) == 0 || (bidGblFlags & 2) == 0 )
      return NextRecords;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      bidTraceW(
        off_18012A208[0],
        10163209,
        L"<CRecordset::MoveRelative|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
        BidObjectID,
        NextRecords,
        9925);
      return NextRecords;
    }
    LODWORD(v26) = 9925;
    v25 = 10163209;
LABEL_69:
    bidTraceW(off_18012A208[0], v25, L"<CRecordset::MoveRelative|ADO|ERR> 0x%08x{HRESULT} line %d\n", NextRecords, v26);
    return NextRecords;
  }
  v10 = *((_QWORD *)this + 93);
  if ( v9 < v10 && v9 >= 0 )
  {
    NextRecords = 0;
    if ( v6 >= v10 || v6 < 0 )
      *((_DWORD *)this + 274) = 0;
    *((_QWORD *)this + 91) = v9;
    return NextRecords;
  }
  if ( (*((_BYTE *)this + 328) & 4) != 0 )
  {
    if ( !*((_QWORD *)this + 40) )
    {
LABEL_14:
      v9 -= v10;
      v13 = 0;
      v14 = 0;
      goto LABEL_15;
    }
  }
  else
  {
    Size = 0;
    if ( (int)CRsetOptionalInterface<IRowsetLocate,&_GUID const IID_IRowsetLocate>::GetInterface(
                (char *)this + 312,
                &Size) < 0 )
      goto LABEL_14;
    if ( Size )
      (*(void (__fastcall **)(size_t))(*(_QWORD *)Size + 16LL))(Size);
  }
  v20 = *((_QWORD *)this + 100);
  v21 = (void *)*((_QWORD *)this + 101);
  v2 = *((_DWORD *)this + 199);
  v22 = *((_QWORD *)this + 96);
  Size = v20;
  Src = v21;
  if ( v2 )
  {
    v23 = (unsigned __int8 *)MpHeapAlloc(g_hHeapHandle, 10485760, v20);
    v14 = Size;
    v13 = v23;
    memcpy_0(v23, Src, Size);
  }
  else
  {
    v28 = v21;
    v13 = (unsigned __int8 *)&v28;
    v14 = v20;
  }
  if ( v22 && (*((_DWORD *)this + 174) & 0x2000000) != 0 && *((_BYTE *)this + 833) && v7 )
  {
    if ( v22 <= 0 )
    {
      if ( *((_BYTE *)this + 752) )
        goto LABEL_42;
    }
    else if ( !*((_BYTE *)this + 752) )
    {
      goto LABEL_42;
    }
  }
  v9 -= v22;
LABEL_42:
  v3 = 0;
LABEL_15:
  v15 = *((_BYTE *)this + 752);
  v16 = *((_DWORD *)this + 180);
  if ( v7 )
  {
    if ( v15 )
    {
      if ( v16 > 0 )
LABEL_18:
        v9 = -v9;
    }
    else
    {
      v9 += v3;
      if ( v16 <= 0 )
        v9 = -v9;
    }
  }
  else
  {
    if ( !v15 )
    {
      if ( v16 > 0 )
        goto LABEL_19;
      goto LABEL_18;
    }
    v24 = v3 + v9;
    v9 = -(v3 + v9);
    if ( v16 <= 0 )
      v9 = v24;
  }
LABEL_19:
  if ( (*((_BYTE *)this + 328) & 4) != 0 )
  {
    if ( *((_QWORD *)this + 40) )
      goto LABEL_21;
    goto LABEL_27;
  }
  Size = 0;
  if ( (int)CRsetOptionalInterface<IRowsetLocate,&_GUID const IID_IRowsetLocate>::GetInterface(
              (char *)this + 312,
              &Size) < 0 )
  {
LABEL_27:
    NextRecords = CRecordset::GetNextRecords(this, v9, v7);
    if ( (NextRecords & 0x80000000) == 0 || (bidGblFlags & 2) == 0 )
      return NextRecords;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      v18 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      bidTraceW(
        off_18012A208[0],
        10157065,
        L"<CRecordset::MoveRelative|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
        v18,
        NextRecords,
        9919);
      return NextRecords;
    }
    LODWORD(v26) = 9919;
    v25 = 10157065;
    goto LABEL_69;
  }
  if ( Size )
    (*(void (__fastcall **)(size_t))(*(_QWORD *)Size + 16LL))(Size);
LABEL_21:
  NextRecords = CRecordset::MoveAbsolute(this, v9, v14, v13, v7);
  if ( v2 && v13 )
    MpHeapFree(g_hHeapHandle, v13);
  if ( NextRecords && (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      v17 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v26) = NextRecords;
      bidTraceW(
        off_18012A208[0],
        10150921,
        L"<CRecordset::MoveRelative|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
        v17,
        v26,
        9913);
      return NextRecords;
    }
    LODWORD(v26) = 9913;
    v25 = 10150921;
    goto LABEL_69;
  }
  return NextRecords;
}

```

## disassembly

```asm
0x180003fa0  push    rbx
0x180003fa2  push    rbp
0x180003fa3  push    rdi
0x180003fa4  push    r13
0x180003fa6  push    r14
0x180003fa8  sub     rsp, 40h
0x180003fac  xor     r13d, r13d
0x180003faf  mov     r14d, 1
0x180003fb5  mov     rdi, rdx
0x180003fb8  mov     rbx, rcx
0x180003fbb  mov     [rsp+68h+arg_8], r13
0x180003fc0  cmp     [rcx+5E2h], r14b
0x180003fc7  jz      loc_1800042FA
0x180003fcd  mov     rcx, [rbx+2D8h]
0x180003fd4  mov     rbp, rdi
0x180003fd7  mov     rax, rdi
0x180003fda  shr     rbp, 3Fh
0x180003fde  neg     rax
0x180003fe1  mov     [rsp+68h+arg_18], rsi
0x180003fe9  cmp     [rbx+2F0h], r13b
0x180003ff0  mov     [rsp+68h+var_30], r12
0x180003ff5  cmovz   rax, rdi
0x180003ff9  mov     [rsp+68h+var_38], r15
0x180003ffe  lea     rdi, [rax+rcx]
0x180004002  mov     rax, [rbx+5D0h]
0x180004009  cmp     [rax], r14d
0x18000400c  jz      loc_1800041D4
0x180004012  mov     rsi, [rbx+2E8h]
0x180004019  cmp     rdi, rsi
0x18000401c  jge     short loc_180004060
0x18000401e  test    rdi, rdi
0x180004021  js      short loc_180004060
0x180004023  mov     ebp, r13d
0x180004026  cmp     rcx, rsi
0x180004029  jge     loc_180004309
0x18000402f  test    rcx, rcx
0x180004032  js      loc_180004309
0x180004038  mov     [rbx+2D8h], rdi
0x18000403f  mov     r15, [rsp+68h+var_38]
0x180004044  mov     eax, ebp
0x180004046  mov     r12, [rsp+68h+var_30]
0x18000404b  mov     rsi, [rsp+68h+arg_18]
0x180004053  add     rsp, 40h
0x180004057  pop     r14
0x180004059  pop     r13
0x18000405b  pop     rdi
0x18000405c  pop     rbp
0x18000405d  pop     rbx
0x18000405e  retn
0x180004060  lea     r15, [rbx+138h]
0x180004067  test    byte ptr [r15+10h], 4
0x18000406c  jz      loc_180004247
0x180004072  cmp     [r15+8], r13
0x180004076  jnz     loc_180004277
0x18000407c  sub     rdi, rsi
0x18000407f  mov     r12, r13
0x180004082  mov     rsi, r13
0x180004085  movzx   eax, byte ptr [rbx+2F0h]
0x18000408c  mov     ecx, [rbx+2D0h]
0x180004092  test    bpl, bpl
0x180004095  jnz     loc_18000434C
0x18000409b  test    al, al
0x18000409d  jnz     loc_180004371
0x1800040a3  test    ecx, ecx
0x1800040a5  jg      short loc_1800040AA
0x1800040a7  neg     rdi
0x1800040aa  test    byte ptr [r15+10h], 4
0x1800040af  jz      loc_180004143
0x1800040b5  cmp     qword ptr [r15+8], 0
0x1800040ba  jz      loc_180004161
0x1800040c0  mov     r9, r12; unsigned __int8 *
0x1800040c3  mov     [rsp+68h+var_48], bpl; bool
0x1800040c8  mov     r8, rsi; unsigned __int64
0x1800040cb  mov     rdx, rdi; __int64
0x1800040ce  mov     rcx, rbx; this
0x1800040d1  call    ?MoveAbsolute@CRecordset@@AEAAJ_J_KPEAE_N@Z; CRecordset::MoveAbsolute(__int64,unsigned __int64,uchar *,bool)
0x1800040d6  mov     ebp, eax
0x1800040d8  test    r13d, r13d
0x1800040db  jnz     loc_1800043A5
0x1800040e1  test    ebp, ebp
0x1800040e3  jz      loc_18000403F
0x1800040e9  test    byte ptr cs:_bidGblFlags, 2
0x1800040f0  jz      loc_18000403F
0x1800040f6  lea     rcx, [rbx+618h]; this
0x1800040fd  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180004102  cmp     eax, 0FFFFFFFFh
0x180004105  jz      loc_1800043C9
0x18000410b  lea     rcx, [rbx+618h]; this
0x180004112  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180004117  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18000411e  lea     r8, aCrecordsetMove_30; "<CRecordset::MoveRelative|ADO|ERR> %u#,"...
0x180004125  mov     r9d, eax
0x180004128  mov     [rsp+68h+var_40], 26B9h
0x180004130  mov     edx, 9AE409h
0x180004135  mov     dword ptr [rsp+68h+var_48], ebp
0x180004139  call    _bidTraceW
0x18000413e  jmp     loc_18000403F
0x180004143  lea     rdx, [rsp+68h+Size]
0x180004148  mov     [rsp+68h+Size], 0
0x180004151  mov     rcx, r15
0x180004154  call    ?GetInterface@?$CRsetOptionalInterface@UIRowsetLocate@@$1?IID_IRowsetLocate@@3U_GUID@@B@@QEAAJPEAPEAUIRowsetLocate@@@Z; CRsetOptionalInterface<IRowsetLocate,&_GUID const IID_IRowsetLocate>::GetInterface(IRowsetLocate * *)
0x180004159  test    eax, eax
0x18000415b  jns     loc_180004386
0x180004161  movzx   r8d, bpl; bool
0x180004165  mov     rdx, rdi; __int64
0x180004168  mov     rcx, rbx; this
0x18000416b  call    ?GetNextRecords@CRecordset@@AEAAJ_J_N@Z; CRecordset::GetNextRecords(__int64,bool)
0x180004170  mov     ebp, eax
0x180004172  test    eax, eax
0x180004174  jns     loc_18000403F
0x18000417a  test    byte ptr cs:_bidGblFlags, 2
0x180004181  jz      loc_18000403F
0x180004187  lea     rcx, [rbx+618h]; this
0x18000418e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180004193  cmp     eax, 0FFFFFFFFh
0x180004196  jz      loc_1800043D8
0x18000419c  lea     rcx, [rbx+618h]; this
0x1800041a3  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800041a8  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800041af  lea     r8, aCrecordsetMove_30; "<CRecordset::MoveRelative|ADO|ERR> %u#,"...
0x1800041b6  mov     r9d, eax
0x1800041b9  mov     [rsp+68h+var_40], 26BFh
0x1800041c1  mov     edx, 9AFC09h
0x1800041c6  mov     dword ptr [rsp+68h+var_48], ebp
0x1800041ca  call    _bidTraceW
0x1800041cf  jmp     loc_18000403F
0x1800041d4  movzx   r8d, bpl; bool
0x1800041d8  mov     rdx, rdi; __int64
0x1800041db  mov     rcx, rbx; this
0x1800041de  call    ?PositionInGroupFilter@CRecordset@@AEAAJ_J_N@Z; CRecordset::PositionInGroupFilter(__int64,bool)
0x1800041e3  mov     ebp, eax
0x1800041e5  test    eax, eax
0x1800041e7  jns     loc_18000403F
0x1800041ed  test    byte ptr cs:_bidGblFlags, 2
0x1800041f4  jz      loc_18000403F
0x1800041fa  lea     rcx, [rbx+618h]; this
0x180004201  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180004206  cmp     eax, 0FFFFFFFFh
0x180004209  jz      loc_1800043E7
0x18000420f  lea     rcx, [rbx+618h]; this
0x180004216  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18000421b  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180004222  lea     r8, aCrecordsetMove_30; "<CRecordset::MoveRelative|ADO|ERR> %u#,"...
0x180004229  mov     r9d, eax
0x18000422c  mov     [rsp+68h+var_40], 26C5h
0x180004234  mov     edx, 9B1409h
0x180004239  mov     dword ptr [rsp+68h+var_48], ebp
0x18000423d  call    _bidTraceW
0x180004242  jmp     loc_18000403F
0x180004247  lea     rdx, [rsp+68h+Size]
0x18000424c  mov     [rsp+68h+Size], r13
0x180004251  mov     rcx, r15
0x180004254  call    ?GetInterface@?$CRsetOptionalInterface@UIRowsetLocate@@$1?IID_IRowsetLocate@@3U_GUID@@B@@QEAAJPEAPEAUIRowsetLocate@@@Z; CRsetOptionalInterface<IRowsetLocate,&_GUID const IID_IRowsetLocate>::GetInterface(IRowsetLocate * *)
0x180004259  test    eax, eax
0x18000425b  js      loc_18000407C
0x180004261  mov     rcx, [rsp+68h+Size]
0x180004266  test    rcx, rcx
0x180004269  jz      short loc_180004277
0x18000426b  mov     rax, [rcx]
0x18000426e  mov     rax, [rax+10h]
0x180004272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004277  mov     r9, [rbx+320h]
0x18000427e  mov     rax, [rbx+328h]
0x180004285  mov     r13d, [rbx+31Ch]
0x18000428c  mov     r14, [rbx+300h]
0x180004293  mov     [rsp+68h+Size], r9
0x180004298  mov     [rsp+68h+Src], rax
0x1800042a0  test    r13d, r13d
0x1800042a3  jz      short loc_1800042EB
0x1800042a5  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800042ac  mov     r8, r9
0x1800042af  mov     edx, 0A00000h
0x1800042b4  call    cs:__imp_MpHeapAlloc
0x1800042bb  nop     dword ptr [rax+rax+00h]
0x1800042c0  mov     rsi, [rsp+68h+Size]
0x1800042c5  mov     rcx, rax; void *
0x1800042c8  mov     rdx, [rsp+68h+Src]; Src
0x1800042d0  mov     r8, rsi; Size
0x1800042d3  mov     r12, rax
0x1800042d6  call    memcpy_0
0x1800042db  test    r14, r14
0x1800042de  jnz     short loc_180004315
0x1800042e0  sub     rdi, r14
0x1800042e3  xor     r14d, r14d
0x1800042e6  jmp     loc_180004085
0x1800042eb  mov     [rsp+68h+arg_8], rax
0x1800042f0  lea     r12, [rsp+68h+arg_8]
0x1800042f5  mov     rsi, r9
0x1800042f8  jmp     short loc_1800042DB
0x1800042fa  mov     r8d, r14d; int
0x1800042fd  xor     edx, edx; int
0x1800042ff  call    ?_MoveFirst@CRecordset@@QEAAJHH@Z; CRecordset::_MoveFirst(int,int)
0x180004304  jmp     loc_180003FCD
0x180004309  mov     [rbx+448h], r13d
0x180004310  jmp     loc_180004038
0x180004315  test    dword ptr [rbx+2B8h], 2000000h
0x18000431f  jz      short loc_1800042E0
0x180004321  cmp     byte ptr [rbx+341h], 0
0x180004328  jz      short loc_1800042E0
0x18000432a  test    bpl, bpl
0x18000432d  jz      short loc_1800042E0
0x18000432f  test    r14, r14
0x180004332  jle     short loc_18000433F
0x180004334  cmp     byte ptr [rbx+2F0h], 0
0x18000433b  jz      short loc_1800042E3
0x18000433d  jmp     short loc_1800042E0
0x18000433f  jns     short loc_1800042E0
0x180004341  cmp     byte ptr [rbx+2F0h], 0
0x180004348  jnz     short loc_1800042E3
0x18000434a  jmp     short loc_1800042E0
0x18000434c  test    al, al
0x18000434e  jnz     short loc_180004364
0x180004350  add     rdi, r14
0x180004353  mov     rax, rdi
0x180004356  neg     rax
0x180004359  test    ecx, ecx
0x18000435b  cmovle  rdi, rax
0x18000435f  jmp     loc_1800040AA
0x180004364  test    ecx, ecx
0x180004366  jle     loc_1800040AA
0x18000436c  jmp     loc_1800040A7
0x180004371  lea     rax, [r14+rdi]
0x180004375  mov     rdi, rax
0x180004378  neg     rdi
0x18000437b  test    ecx, ecx
0x18000437d  cmovle  rdi, rax
0x180004381  jmp     loc_1800040AA
0x180004386  mov     rcx, [rsp+68h+Size]
0x18000438b  test    rcx, rcx
0x18000438e  jz      loc_1800040C0
0x180004394  mov     rax, [rcx]
0x180004397  mov     rax, [rax+10h]
0x18000439b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043a0  jmp     loc_1800040C0
0x1800043a5  test    r12, r12
0x1800043a8  jz      loc_1800040E1
0x1800043ae  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800043b5  mov     rdx, r12
0x1800043b8  call    cs:__imp_MpHeapFree
0x1800043bf  nop     dword ptr [rax+rax+00h]
0x1800043c4  jmp     loc_1800040E1
0x1800043c9  mov     dword ptr [rsp+68h+var_48], 26B9h
0x1800043d1  mov     edx, 9AE409h
0x1800043d6  jmp     short loc_1800043F4
0x1800043d8  mov     dword ptr [rsp+68h+var_48], 26BFh
0x1800043e0  mov     edx, 9AFC09h
0x1800043e5  jmp     short loc_1800043F4
0x1800043e7  mov     dword ptr [rsp+68h+var_48], 26C5h
0x1800043ef  mov     edx, 9B1409h
0x1800043f4  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800043fb  lea     r8, aCrecordsetMove_2; "<CRecordset::MoveRelative|ADO|ERR> 0x%0"...
0x180004402  mov     r9d, ebp
0x180004405  call    _bidTraceW
0x18000440a  jmp     loc_18000403F
```
