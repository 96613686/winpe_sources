# CRecFields::CreateObject(void *,IUnknown *,CStdComObjectRoot * *)

- ea: `0x18009d340`
- end: `0x18009d5e3`
- name: `?CreateObject@CRecFields@@UEAAJPEAXPEAUIUnknown@@PEAPEAVCStdComObjectRoot@@@Z`
- size: `675`
- prototype: `__int64 __fastcall(CRecFields *__hidden this, void *, struct IUnknown *, struct CStdComObjectRoot **)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18006a22c`
- `0x18009c3c4`
- `0x18009d340`
- `0x18009e3c8`
- `0x18009f188`
- `0x1800c8f34`
- `0x1800cdac6`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x18009d404`
- `MSDART!MpHeapAlloc` at `0x18009d404`

## string_xrefs

- `0x18009d3b4`: `<CRecFields::CreateObject|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x18009d47a`: `<CRecFields::CreateObject|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x18009d3d5`: `<CRecFields::CreateObject|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x18009d49b`: `<CRecFields::CreateObject|ADO|ERR> 0x%08x{HRESULT} line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRecFields::CreateObject(
        CBidGenericBase **this,
        _QWORD *a2,
        struct IUnknown *a3,
        struct CStdComObjectRoot **a4)
{
  struct IRow *Row; // r15
  unsigned int v8; // ebp
  unsigned int v9; // eax
  __int64 v10; // rax
  __int64 v11; // rsi
  unsigned int BidObjectID; // eax
  int v13; // ebx
  unsigned int v14; // eax
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // r12

  Row = CRecFields::GetRow((CRecFields *)(this - 1));
  if ( Row )
  {
    v10 = MpHeapAlloc(g_hHeapHandle, 10485760, 456);
    if ( v10 )
      v11 = ATL::CComObject<CRecField>::CComObject<CRecField>(v10);
    else
      v11 = 0;
    if ( !v11 )
    {
      v8 = -2147024882;
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID(this[17]) == -1 )
        {
          bidTraceW(
            off_18012A200[0],
            2515977,
            L"<CRecFields::CreateObject|ADO|ERR> 0x%08x{HRESULT} line %d\n",
            2147942414LL,
            2457);
        }
        else
        {
          BidObjectID = CBidGenericBase::GetBidObjectID(this[17]);
          bidTraceW(
            off_18012A200[0],
            2515977,
            L"<CRecFields::CreateObject|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
            BidObjectID,
            -2147024882,
            2457);
        }
      }
      goto LABEL_29;
    }
    v8 = 0;
    if ( (bidGblFlags & 2) != 0 && off_18012A678[0] )
    {
      v13 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(v11 + 88));
      v14 = CBidGenericBase::GetBidObjectID(this[17]);
      bidTraceW(off_18012A200[0], 2520064, off_18012A678[0], v14, v13);
    }
    CRecFields::InitLockOfField((CRecFields *)(this - 1), (struct CRecField *)v11);
    v15 = 10LL * a2[1];
    v16 = a2[3];
    if ( (*(_DWORD *)(v16 + 80LL * a2[1] + 24) & 0x20000) != 0 )
    {
      this[14] = (CBidGenericBase *)v11;
    }
    else
    {
      if ( (*(_DWORD *)(v16 + 80LL * a2[1] + 24) & 0x10000) == 0 )
      {
        v17 = v16 + 80LL * a2[1];
        if ( !memcmp_0((const void *)(v17 + 48), &DBROWCOL_ISCOLLECTION, 0x20u) )
        {
          if ( *(_WORD *)(*(_QWORD *)(a2[4] + 8 * v15) + 8LL) == 0xFFFF )
            *((_DWORD *)this + 32) |= 1u;
        }
        else if ( !memcmp_0((const void *)(v17 + 48), &DBROWCOL_ISSTRUCTUREDDOCUMENT, 0x20u)
               && *(_WORD *)(*(_QWORD *)(a2[4] + 8 * v15) + 8LL) == 0xFFFF )
        {
          *((_DWORD *)this + 32) |= 2u;
        }
        goto LABEL_28;
      }
      this[15] = (CBidGenericBase *)v11;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v11 + 8) + 80LL))(v11 + 8);
LABEL_28:
    *a4 = (struct CStdComObjectRoot *)(v11 + 8);
LABEL_29:
    ((void (__fastcall *)(struct IRow *))Row->lpVtbl->Release)(Row);
    return v8;
  }
  v8 = -2146824584;
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID(this[17]) == -1 )
    {
      bidTraceW(
        off_18012A200[0],
        2508809,
        L"<CRecFields::CreateObject|ADO|ERR> 0x%08x{HRESULT} line %d\n",
        2148142712LL,
        2450);
    }
    else
    {
      v9 = CBidGenericBase::GetBidObjectID(this[17]);
      bidTraceW(
        off_18012A200[0],
        2508809,
        L"<CRecFields::CreateObject|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
        v9,
        -2146824584,
        2450);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18009d340  push    rbx
0x18009d342  push    rbp
0x18009d343  push    rsi
0x18009d344  push    rdi
0x18009d345  push    r12
0x18009d347  push    r13
0x18009d349  push    r14
0x18009d34b  push    r15
0x18009d34d  sub     rsp, 38h
0x18009d351  mov     r13, r9
0x18009d354  mov     r14, rdx
0x18009d357  mov     rdi, rcx
0x18009d35a  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x18009d35e  call    ?GetRow@CRecFields@@AEAAPEAUIRow@@XZ; CRecFields::GetRow(void)
0x18009d363  mov     r15, rax
0x18009d366  test    rax, rax
0x18009d369  jnz     loc_18009D3F2
0x18009d36f  mov     ebp, 800A0E78h
0x18009d374  test    byte ptr cs:_bidGblFlags, 2
0x18009d37b  jz      loc_18009D5CF
0x18009d381  mov     rcx, [rdi+88h]; this
0x18009d388  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009d38d  cmp     eax, 0FFFFFFFFh
0x18009d390  jz      short loc_18009D3CA
0x18009d392  mov     rcx, [rdi+88h]; this
0x18009d399  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009d39e  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18009d3a5  mov     [rsp+78h+var_50], 992h
0x18009d3ad  mov     [rsp+78h+var_58], ebp
0x18009d3b1  mov     r9d, eax
0x18009d3b4  lea     r8, aCrecfieldsCrea_1; "<CRecFields::CreateObject|ADO|ERR> %u#,"...
0x18009d3bb  mov     edx, 264809h
0x18009d3c0  call    _bidTraceW
0x18009d3c5  jmp     loc_18009D5CF
0x18009d3ca  mov     [rsp+78h+var_58], 992h
0x18009d3d2  mov     r9d, ebp
0x18009d3d5  lea     r8, aCrecfieldsCrea_0; "<CRecFields::CreateObject|ADO|ERR> 0x%0"...
0x18009d3dc  mov     edx, 264809h
0x18009d3e1  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18009d3e8  call    _bidTraceW
0x18009d3ed  jmp     loc_18009D5CF
0x18009d3f2  mov     edx, 0A00000h
0x18009d3f7  mov     r8d, 1C8h
0x18009d3fd  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18009d404  call    cs:__imp_MpHeapAlloc
0x18009d40b  nop     dword ptr [rax+rax+00h]
0x18009d410  mov     [rsp+78h+arg_0], rax
0x18009d418  test    rax, rax
0x18009d41b  jz      short loc_18009D42A
0x18009d41d  mov     rcx, rax
0x18009d420  call    ??0?$CComObject@VCRecField@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CRecField>::CComObject<CRecField>(void *)
0x18009d425  mov     rsi, rax
0x18009d428  jmp     short loc_18009D42C
0x18009d42a  xor     esi, esi
0x18009d42c  test    rsi, rsi
0x18009d42f  jnz     loc_18009D4B8
0x18009d435  mov     ebp, 8007000Eh
0x18009d43a  test    byte ptr cs:_bidGblFlags, 2
0x18009d441  jz      loc_18009D5C0
0x18009d447  mov     rcx, [rdi+88h]; this
0x18009d44e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009d453  cmp     eax, 0FFFFFFFFh
0x18009d456  jz      short loc_18009D490
0x18009d458  mov     rcx, [rdi+88h]; this
0x18009d45f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009d464  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18009d46b  mov     [rsp+78h+var_50], 999h
0x18009d473  mov     [rsp+78h+var_58], ebp
0x18009d477  mov     r9d, eax
0x18009d47a  lea     r8, aCrecfieldsCrea_1; "<CRecFields::CreateObject|ADO|ERR> %u#,"...
0x18009d481  mov     edx, 266409h
0x18009d486  call    _bidTraceW
0x18009d48b  jmp     loc_18009D5C0
0x18009d490  mov     [rsp+78h+var_58], 999h
0x18009d498  mov     r9d, ebp
0x18009d49b  lea     r8, aCrecfieldsCrea_0; "<CRecFields::CreateObject|ADO|ERR> 0x%0"...
0x18009d4a2  mov     edx, 266409h
0x18009d4a7  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18009d4ae  call    _bidTraceW
0x18009d4b3  jmp     loc_18009D5C0
0x18009d4b8  xor     ebp, ebp
0x18009d4ba  test    byte ptr cs:_bidGblFlags, 2
0x18009d4c1  jz      short loc_18009D505
0x18009d4c3  mov     rax, cs:off_18012A678; "<CRecFields::CreateObject|INFO|ADO> %u#"...
0x18009d4ca  test    rax, rax
0x18009d4cd  jz      short loc_18009D505
0x18009d4cf  lea     rcx, [rsi+58h]; this
0x18009d4d3  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009d4d8  mov     ebx, eax
0x18009d4da  mov     rcx, [rdi+88h]; this
0x18009d4e1  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009d4e6  mov     r8, cs:off_18012A678; "<CRecFields::CreateObject|INFO|ADO> %u#"...
0x18009d4ed  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18009d4f4  mov     [rsp+78h+var_58], ebx
0x18009d4f8  mov     r9d, eax
0x18009d4fb  mov     edx, 267400h
0x18009d500  call    _bidTraceW
0x18009d505  mov     rdx, rsi; struct CRecField *
0x18009d508  lea     rcx, [rdi-8]; this
0x18009d50c  call    ?InitLockOfField@CRecFields@@AEAAJPEAVCRecField@@@Z; CRecFields::InitLockOfField(CRecField *)
0x18009d511  mov     rax, [r14+8]
0x18009d515  lea     rbx, [rax+rax*4]
0x18009d519  add     rbx, rbx
0x18009d51c  mov     rax, [r14+18h]
0x18009d520  test    dword ptr [rax+rbx*8+18h], 20000h
0x18009d528  jz      short loc_18009D530
0x18009d52a  mov     [rdi+70h], rsi
0x18009d52e  jmp     short loc_18009D53E
0x18009d530  test    dword ptr [rax+rbx*8+18h], 10000h
0x18009d538  jz      short loc_18009D550
0x18009d53a  mov     [rdi+78h], rsi
0x18009d53e  lea     rcx, [rsi+8]
0x18009d542  mov     rax, [rcx]
0x18009d545  mov     rax, [rax+50h]
0x18009d549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d54e  jmp     short loc_18009D5B8
0x18009d550  lea     r12, [rax+rbx*8]
0x18009d554  mov     r8d, 20h ; ' '; Size
0x18009d55a  lea     rdx, DBROWCOL_ISCOLLECTION; Buf2
0x18009d561  lea     rcx, [r12+30h]; Buf1
0x18009d566  call    memcmp_0
0x18009d56b  test    eax, eax
0x18009d56d  jnz     short loc_18009D587
0x18009d56f  mov     rax, [r14+20h]
0x18009d573  mov     rcx, [rax+rbx*8]
0x18009d577  cmp     word ptr [rcx+8], 0FFFFh
0x18009d57c  jnz     short loc_18009D5B8
0x18009d57e  or      dword ptr [rdi+80h], 1
0x18009d585  jmp     short loc_18009D5B8
0x18009d587  mov     r8d, 20h ; ' '; Size
0x18009d58d  lea     rdx, DBROWCOL_ISSTRUCTUREDDOCUMENT; Buf2
0x18009d594  lea     rcx, [r12+30h]; Buf1
0x18009d599  call    memcmp_0
0x18009d59e  test    eax, eax
0x18009d5a0  jnz     short loc_18009D5B8
0x18009d5a2  mov     rax, [r14+20h]
0x18009d5a6  mov     rcx, [rax+rbx*8]
0x18009d5aa  cmp     word ptr [rcx+8], 0FFFFh
0x18009d5af  jnz     short loc_18009D5B8
0x18009d5b1  or      dword ptr [rdi+80h], 2
0x18009d5b8  lea     rcx, [rsi+8]
0x18009d5bc  mov     [r13+0], rcx
0x18009d5c0  mov     rcx, [r15]
0x18009d5c3  mov     rax, [rcx+10h]
0x18009d5c7  mov     rcx, r15
0x18009d5ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d5cf  mov     eax, ebp
0x18009d5d1  add     rsp, 38h
0x18009d5d5  pop     r15
0x18009d5d7  pop     r14
0x18009d5d9  pop     r13
0x18009d5db  pop     r12
0x18009d5dd  pop     rdi
0x18009d5de  pop     rsi
0x18009d5df  pop     rbp
0x18009d5e0  pop     rbx
0x18009d5e1  retn
```
