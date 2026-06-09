# CQuery::SetCommandText(long,unsigned __int64,uchar,uchar)

- ea: `0x180016730`
- end: `0x180016b80`
- name: `?SetCommandText@CQuery@@QEAAJJ_KEE@Z`
- size: `1104`
- prototype: `__int64 __usercall@<rax>(CQuery *__hidden this@<rcx>, int@<edx>, unsigned __int64@<r8>, unsigned __int8@<r9b>, unsigned __int8)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800337d0`
- `0x1800799d0`
- `0x180088670`

## callees

- `0x180016730`
- `0x180016b90`
- `0x1800265d0`
- `0x180045580`
- `0x18004f140`
- `0x180059d44`
- `0x18006a22c`
- `0x180084608`
- `0x1800c8f34`
- `0x1800cdad2`
- `0x1800d0010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001678a`
- `OLEAUT32!__imp_SysAllocString` at `0x18001678a`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001686d`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180016ac0`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001686d`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180016ac0`
- `OLEAUT32!__imp_SysFreeString` at `0x180016777`
- `OLEAUT32!__imp_SysFreeString` at `0x1800167e9`
- `OLEAUT32!__imp_SysFreeString` at `0x18001683c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800168e5`
- `OLEAUT32!__imp_SysFreeString` at `0x180016777`
- `OLEAUT32!__imp_SysFreeString` at `0x1800167e9`
- `OLEAUT32!__imp_SysFreeString` at `0x18001683c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800168e5`
- `OLEAUT32!__imp_SysStringLen` at `0x180016856`
- `OLEAUT32!__imp_SysStringLen` at `0x180016a8d`
- `OLEAUT32!__imp_SysStringLen` at `0x180016aa6`
- `OLEAUT32!__imp_SysStringLen` at `0x180016856`
- `OLEAUT32!__imp_SysStringLen` at `0x180016a8d`
- `OLEAUT32!__imp_SysStringLen` at `0x180016aa6`

## string_xrefs

- `0x1800169af`: `<CCommand::GetCommandText|ADO|ERR> %u#, line %d\n`
- `0x1800169cb`: `<CCommand::GetCommandText|ADO|ERR>  line %d\n`
- `0x180016a4b`: `<CCommand::GetCommandText|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x180016b41`: `<CQuery::SetCommandText|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x180016b62`: `<CQuery::SetCommandText|ADO|ERR> 0x%08x{HRESULT} line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CQuery::SetCommandText(CQuery *this, int a2, unsigned __int64 a3, unsigned __int8 a4, signed int a5)
{
  int v5; // r12d
  OLECHAR *v8; // rdi
  char v9; // bl
  __int64 v10; // r15
  OLECHAR *v11; // rcx
  unsigned __int16 *v12; // rdx
  int StoredProc; // esi
  int v15; // edx
  int v16; // edx
  int v17; // edx
  BSTR *v18; // rsi
  UINT v19; // eax
  const OLECHAR *v20; // rcx
  const void *v21; // rdx
  struct _ADOConnection *Connection; // rax
  int v23; // eax
  unsigned int BidObjectID; // eax
  UINT v25; // esi
  signed int v26; // r12d
  BSTR v27; // rsi
  unsigned int v28; // eax
  __int64 v29; // [rsp+20h] [rbp-28h]
  OLECHAR *v30; // [rsp+30h] [rbp-18h] BYREF
  char v31; // [rsp+38h] [rbp-10h]
  int v32; // [rsp+98h] [rbp+50h] BYREF

  v5 = a4;
  v8 = 0;
  v30 = 0;
  v9 = 7;
  v31 = 7;
  v10 = *((_QWORD *)this + 17);
  if ( (_BYTE)a5 )
    *((_BYTE *)this + 172) = a5;
  if ( a2 != 2 )
  {
    v15 = a2 - 1;
    if ( !v15 )
    {
LABEL_19:
      v18 = (BSTR *)(v10 + 176);
      if ( (OLECHAR **)(v10 + 176) != &v30 && *v18 )
      {
        SysFreeString(0);
        if ( (*(_BYTE *)(v10 + 184) & 4) != 0 && *v18 )
        {
          v19 = SysStringLen(*v18);
          if ( (*(_BYTE *)(v10 + 184) & 4) != 0 )
            v20 = *v18;
          else
            v20 = 0;
          v8 = SysAllocStringLen(v20, v19);
          v30 = v8;
          if ( v8 )
          {
            v9 = 7;
            v31 = 7;
          }
          else
          {
            v9 = 3;
            v31 = 3;
          }
        }
        else
        {
          v8 = 0;
          v30 = 0;
        }
      }
      StoredProc = -2147024882;
      if ( (v9 & 4) != 0 )
        StoredProc = 0;
LABEL_29:
      if ( StoredProc < 0 )
        goto LABEL_66;
LABEL_9:
      v12 = 0;
      if ( (v9 & 4) != 0 )
        v12 = v8;
      StoredProc = CQuery::SetSQL(this, v12);
      goto LABEL_12;
    }
    v16 = v15 - 3;
    if ( v16 )
    {
      v17 = v16 - 4;
      if ( v17 && v17 != 504 )
        goto LABEL_9;
      goto LABEL_19;
    }
    StoredProc = 0;
    v32 = 256;
    a5 = 0;
    Connection = CCommand::GetConnection((CCommand *)v10);
    if ( Connection
      && (v23 = (*(__int64 (__fastcall **)(struct _ADOConnection *, const GUID *, __int64, signed int *, int *))(*(_QWORD *)Connection + 384LL))(
                  Connection,
                  &DBPROPSET_DATASOURCEINFO,
                  109,
                  &a5,
                  &v32),
          StoredProc = v23,
          v23 < 0) )
    {
      if ( v23 != -2147217887 || a5 != 1 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_12;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(v10 + 144)) == -1 )
        {
          bidTraceW(off_18012A1E0[0], 1249289, L"<CCommand::GetCommandText|ADO|ERR>  line %d\n", 1220);
        }
        else
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(v10 + 144));
          LODWORD(v29) = 1220;
          bidTraceW(off_18012A1E0[0], 1249289, L"<CCommand::GetCommandText|ADO|ERR> %u#, line %d\n", BidObjectID, v29);
        }
        goto LABEL_66;
      }
    }
    else if ( a5 != 1 && (v32 & 0x100) == 0 )
    {
      if ( v32 )
      {
        CSysString::operator=(&v30, L"exec ");
        CSysString::operator+=(&v30, v10 + 176);
      }
      else
      {
        CSysString::operator=(&v30, v10 + 176);
      }
      v9 = v31;
      if ( (v31 & 4) == 0 )
      {
        StoredProc = -2147024882;
        if ( (bidGblFlags & 2) != 0 )
        {
          LODWORD(v29) = 1238;
          bidTraceW(
            off_18012A1E0[0],
            1267721,
            L"<CCommand::GetCommandText|ADO|ERR> 0x%08x{HRESULT} line %d\n",
            2147942414LL,
            v29);
        }
        v8 = v30;
        goto LABEL_66;
      }
      goto LABEL_57;
    }
    StoredProc = CCommand::GetStoredProc((CCommand *)v10, a3, v5, (struct CSysString *)&v30);
    v9 = v31;
LABEL_57:
    v8 = v30;
    goto LABEL_29;
  }
  SysFreeString(0);
  v8 = SysAllocString(L"select * from ");
  v30 = v8;
  if ( v8 )
    v9 = 7;
  else
    v9 = 3;
  v31 = v9;
  if ( (*(_BYTE *)(v10 + 184) & 4) != 0 )
  {
    v11 = *(OLECHAR **)(v10 + 176);
    if ( v11 )
    {
      v25 = SysStringLen(v11);
      a5 = v25;
      if ( v8 )
        v26 = SysStringLen(v8);
      else
        v26 = 0;
      v27 = SysAllocStringLen(0, v25 + v26);
      if ( v27 )
      {
        if ( v26 > 0 )
          memcpy_0(v27, v8, 2LL * v26);
        if ( (*(_BYTE *)(v10 + 184) & 4) != 0 )
          v21 = *(const void **)(v10 + 176);
        else
          v21 = 0;
        memcpy_0(&v27[v26], v21, 2LL * a5);
        SysFreeString(v8);
        v8 = v27;
        v30 = v27;
      }
      else
      {
        v9 &= ~4u;
        v31 = v9;
      }
    }
  }
  if ( (v9 & 4) != 0 )
    goto LABEL_9;
  StoredProc = -2147024882;
LABEL_66:
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CQuery *)((char *)this + 64)) == -1 )
    {
      LODWORD(v29) = 4298;
      bidTraceW(
        off_18012A1E0[0],
        4401161,
        L"<CQuery::SetCommandText|ADO|ERR> 0x%08x{HRESULT} line %d\n",
        (unsigned int)StoredProc,
        v29);
    }
    else
    {
      v28 = CBidGenericBase::GetBidObjectID((CQuery *)((char *)this + 64));
      LODWORD(v29) = StoredProc;
      bidTraceW(
        off_18012A1E0[0],
        4401161,
        L"<CQuery::SetCommandText|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
        v28,
        v29,
        4298);
    }
  }
LABEL_12:
  if ( (v9 & 2) != 0 )
    SysFreeString(v8);
  return (unsigned int)StoredProc;
}

```

## disassembly

```asm
0x180016730  push    rbp
0x180016732  push    rbx
0x180016733  push    rsi
0x180016734  push    rdi
0x180016735  push    r12
0x180016737  push    r13
0x180016739  push    r14
0x18001673b  push    r15
0x18001673d  mov     rbp, rsp
0x180016740  sub     rsp, 48h
0x180016744  movzx   r12d, r9b
0x180016748  mov     r13, r8
0x18001674b  mov     r14, rcx
0x18001674e  xor     edi, edi
0x180016750  mov     [rbp+var_18], rdi
0x180016754  mov     bl, 7
0x180016756  mov     [rbp+var_10], bl
0x180016759  mov     r15, [rcx+88h]
0x180016760  movzx   eax, byte ptr [rbp+arg_20]
0x180016764  test    al, al
0x180016766  jnz     loc_180016901
0x18001676c  cmp     edx, 2
0x18001676f  jnz     loc_180016809
0x180016775  xor     ecx, ecx; bstrString
0x180016777  call    cs:__imp_SysFreeString
0x18001677e  nop     dword ptr [rax+rax+00h]
0x180016783  lea     rcx, ?szSelectPrefix@@3QBGB; "select * from "
0x18001678a  call    cs:__imp_SysAllocString
0x180016791  nop     dword ptr [rax+rax+00h]
0x180016796  mov     rdi, rax
0x180016799  mov     [rbp+var_18], rax
0x18001679d  test    rax, rax
0x1800167a0  jz      loc_1800168B6
0x1800167a6  mov     bl, 7
0x1800167a8  mov     [rbp+var_10], bl
0x1800167ab  test    byte ptr [r15+0B8h], 4
0x1800167b3  jz      short loc_1800167C5
0x1800167b5  mov     rcx, [r15+0B0h]; pbstr
0x1800167bc  test    rcx, rcx
0x1800167bf  jnz     loc_180016A8D
0x1800167c5  test    bl, 4
0x1800167c8  jz      loc_180016B02
0x1800167ce  xor     edx, edx
0x1800167d0  test    bl, 4
0x1800167d3  cmovnz  rdx, rdi; unsigned __int16 *
0x1800167d7  mov     rcx, r14; this
0x1800167da  call    ?SetSQL@CQuery@@QEAAJPEAG@Z; CQuery::SetSQL(ushort *)
0x1800167df  mov     esi, eax
0x1800167e1  test    bl, 2
0x1800167e4  jz      short loc_1800167F5
0x1800167e6  mov     rcx, rdi; bstrString
0x1800167e9  call    cs:__imp_SysFreeString
0x1800167f0  nop     dword ptr [rax+rax+00h]
0x1800167f5  mov     eax, esi
0x1800167f7  add     rsp, 48h
0x1800167fb  pop     r15
0x1800167fd  pop     r14
0x1800167ff  pop     r13
0x180016801  pop     r12
0x180016803  pop     rdi
0x180016804  pop     rsi
0x180016805  pop     rbx
0x180016806  pop     rbp
0x180016807  retn
0x180016809  sub     edx, 1
0x18001680c  jz      short loc_180016824
0x18001680e  sub     edx, 3
0x180016811  jz      loc_18001690C
0x180016817  sub     edx, 4
0x18001681a  jz      short loc_180016824
0x18001681c  cmp     edx, 1F8h
0x180016822  jnz     short loc_1800167CE
0x180016824  lea     rsi, [r15+0B0h]
0x18001682b  lea     rax, [rbp+var_18]
0x18001682f  cmp     rsi, rax
0x180016832  jz      short loc_18001688A
0x180016834  cmp     qword ptr [rsi], 0
0x180016838  jz      short loc_18001688A
0x18001683a  xor     ecx, ecx; bstrString
0x18001683c  call    cs:__imp_SysFreeString
0x180016843  nop     dword ptr [rax+rax+00h]
0x180016848  test    byte ptr [rsi+8], 4
0x18001684c  jz      short loc_1800168A7
0x18001684e  mov     rcx, [rsi]; pbstr
0x180016851  test    rcx, rcx
0x180016854  jz      short loc_1800168A7
0x180016856  call    cs:__imp_SysStringLen
0x18001685d  nop     dword ptr [rax+rax+00h]
0x180016862  test    byte ptr [rsi+8], 4
0x180016866  jz      short loc_1800168BD
0x180016868  mov     rcx, [rsi]; strIn
0x18001686b  mov     edx, eax; ui
0x18001686d  call    cs:__imp_SysAllocStringLen
0x180016874  nop     dword ptr [rax+rax+00h]
0x180016879  mov     rdi, rax
0x18001687c  mov     [rbp+var_18], rax
0x180016880  test    rax, rax
0x180016883  jz      short loc_1800168AF
0x180016885  mov     bl, 7
0x180016887  mov     [rbp+var_10], bl
0x18001688a  test    bl, 4
0x18001688d  mov     esi, 8007000Eh
0x180016892  mov     eax, 0
0x180016897  cmovnz  esi, eax
0x18001689a  test    esi, esi
0x18001689c  jns     loc_1800167CE
0x1800168a2  jmp     loc_180016B07
0x1800168a7  xor     edi, edi
0x1800168a9  mov     [rbp+var_18], rdi
0x1800168ad  jmp     short loc_18001688A
0x1800168af  mov     bl, 3
0x1800168b1  mov     [rbp+var_10], bl
0x1800168b4  jmp     short loc_18001688A
0x1800168b6  mov     bl, 3
0x1800168b8  jmp     loc_1800167A8
0x1800168bd  xor     ecx, ecx
0x1800168bf  jmp     short loc_18001686B
0x1800168c1  test    byte ptr [r15+0B8h], 4
0x1800168c9  jz      short loc_1800168FD
0x1800168cb  mov     rdx, [r15+0B0h]; Src
0x1800168d2  movsxd  r8, [rbp+arg_20]
0x1800168d6  add     r8, r8; Size
0x1800168d9  lea     rcx, [rsi+r13]; void *
0x1800168dd  call    memcpy_0
0x1800168e2  mov     rcx, rdi; bstrString
0x1800168e5  call    cs:__imp_SysFreeString
0x1800168ec  nop     dword ptr [rax+rax+00h]
0x1800168f1  mov     rdi, rsi
0x1800168f4  mov     [rbp+var_18], rsi
0x1800168f8  jmp     loc_1800167C5
0x1800168fd  xor     edx, edx
0x1800168ff  jmp     short loc_1800168D2
0x180016901  mov     [rcx+0ACh], al
0x180016907  jmp     loc_18001676C
0x18001690c  xor     esi, esi
0x18001690e  mov     [rbp+arg_8], 100h
0x180016915  mov     [rbp+arg_20], esi
0x180016918  mov     rcx, r15; this
0x18001691b  call    ?GetConnection@CCommand@@QEAAPEAU_ADOConnection@@XZ; CCommand::GetConnection(void)
0x180016920  mov     r10, rax
0x180016923  test    rax, rax
0x180016926  jz      loc_1800169E8
0x18001692c  mov     rcx, [rax]
0x18001692f  mov     rax, [rcx+180h]
0x180016936  lea     rcx, [rbp+arg_8]
0x18001693a  mov     [rsp+48h+var_28], rcx
0x18001693f  lea     r9, [rbp+arg_20]
0x180016943  mov     r8d, 6Dh ; 'm'
0x180016949  lea     rdx, DBPROPSET_DATASOURCEINFO
0x180016950  mov     rcx, r10
0x180016953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016958  mov     esi, eax
0x18001695a  test    eax, eax
0x18001695c  jns     loc_1800169E8
0x180016962  cmp     eax, 80040E21h
0x180016967  jnz     short loc_180016973
0x180016969  cmp     [rbp+arg_20], 1
0x18001696d  jz      loc_180016A6C
0x180016973  test    byte ptr cs:_bidGblFlags, 2
0x18001697a  jz      loc_1800167E1
0x180016980  lea     rcx, [r15+90h]; this
0x180016987  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001698c  cmp     eax, 0FFFFFFFFh
0x18001698f  jz      short loc_1800169C5
0x180016991  lea     rcx, [r15+90h]; this
0x180016998  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001699d  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800169a4  mov     dword ptr [rsp+48h+var_28], 4C4h
0x1800169ac  mov     r9d, eax
0x1800169af  lea     r8, aCcommandGetcom_1; "<CCommand::GetCommandText|ADO|ERR> %u#,"...
0x1800169b6  mov     edx, 131009h
0x1800169bb  call    _bidTraceW
0x1800169c0  jmp     loc_180016B07
0x1800169c5  mov     r9d, 4C4h
0x1800169cb  lea     r8, aCcommandGetcom_0; "<CCommand::GetCommandText|ADO|ERR>  lin"...
0x1800169d2  mov     edx, 131009h
0x1800169d7  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800169de  call    _bidTraceW
0x1800169e3  jmp     loc_180016B07
0x1800169e8  cmp     [rbp+arg_20], 1
0x1800169ec  jz      short loc_180016A6C
0x1800169ee  mov     eax, [rbp+arg_8]
0x1800169f1  bt      eax, 8
0x1800169f5  jb      short loc_180016A6C
0x1800169f7  lea     rcx, [rbp+var_18]
0x1800169fb  test    eax, eax
0x1800169fd  jnz     short loc_180016A0D
0x1800169ff  lea     rdx, [r15+0B0h]
0x180016a06  call    ??4CSysString@@QEAAAEBV0@AEBV0@@Z; CSysString::operator=(CSysString const &)
0x180016a0b  jmp     short loc_180016A29
0x180016a0d  lea     rdx, aExec; "exec "
0x180016a14  call    ??4CSysString@@QEAAAEBV0@PEBG@Z; CSysString::operator=(ushort const *)
0x180016a19  lea     rdx, [r15+0B0h]
0x180016a20  lea     rcx, [rbp+var_18]
0x180016a24  call    ??YCSysString@@QEAAAEBV0@AEBV0@@Z; CSysString::operator+=(CSysString const &)
0x180016a29  movzx   ebx, [rbp+var_10]
0x180016a2d  test    bl, 4
0x180016a30  jnz     short loc_180016A84
0x180016a32  mov     esi, 8007000Eh
0x180016a37  test    byte ptr cs:_bidGblFlags, 2
0x180016a3e  jz      short loc_180016A63
0x180016a40  mov     dword ptr [rsp+48h+var_28], 4D6h
0x180016a48  mov     r9d, esi
0x180016a4b  lea     r8, aCcommandGetcom; "<CCommand::GetCommandText|ADO|ERR> 0x%0"...
0x180016a52  mov     edx, 135809h
0x180016a57  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180016a5e  call    _bidTraceW
0x180016a63  mov     rdi, [rbp+var_18]
0x180016a67  jmp     loc_180016B07
0x180016a6c  mov     r8d, r12d; int
0x180016a6f  lea     r9, [rbp+var_18]; struct CSysString *
0x180016a73  mov     rdx, r13; unsigned __int64
0x180016a76  mov     rcx, r15; this
0x180016a79  call    ?GetStoredProc@CCommand@@QEAAJ_KHAEAVCSysString@@@Z; CCommand::GetStoredProc(unsigned __int64,int,CSysString &)
0x180016a7e  mov     esi, eax
0x180016a80  movzx   ebx, [rbp+var_10]
0x180016a84  mov     rdi, [rbp+var_18]
0x180016a88  jmp     loc_18001689A
0x180016a8d  call    cs:__imp_SysStringLen
0x180016a94  nop     dword ptr [rax+rax+00h]
0x180016a99  mov     esi, eax
0x180016a9b  mov     [rbp+arg_20], eax
0x180016a9e  test    rdi, rdi
0x180016aa1  jz      short loc_180016AB7
0x180016aa3  mov     rcx, rdi; pbstr
0x180016aa6  call    cs:__imp_SysStringLen
0x180016aad  nop     dword ptr [rax+rax+00h]
0x180016ab2  mov     r12d, eax
0x180016ab5  jmp     short loc_180016ABA
0x180016ab7  xor     r12d, r12d
0x180016aba  lea     edx, [rsi+r12]; ui
0x180016abe  xor     ecx, ecx; strIn
0x180016ac0  call    cs:__imp_SysAllocStringLen
0x180016ac7  nop     dword ptr [rax+rax+00h]
0x180016acc  mov     rsi, rax
0x180016acf  test    rax, rax
0x180016ad2  jnz     short loc_180016ADF
0x180016ad4  and     bl, 0FBh
0x180016ad7  mov     [rbp+var_10], bl
0x180016ada  jmp     loc_1800167C5
0x180016adf  movsxd  rax, r12d
0x180016ae2  lea     r13, [rax+rax]
0x180016ae6  test    r12d, r12d
0x180016ae9  jle     loc_1800168C1
0x180016aef  mov     r8, r13; Size
0x180016af2  mov     rdx, rdi; Src
0x180016af5  mov     rcx, rsi; void *
0x180016af8  call    memcpy_0
0x180016afd  jmp     loc_1800168C1
0x180016b02  mov     esi, 8007000Eh
0x180016b07  test    byte ptr cs:_bidGblFlags, 2
0x180016b0e  jz      loc_1800167E1
0x180016b14  lea     rcx, [r14+40h]; this
0x180016b18  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180016b1d  cmp     eax, 0FFFFFFFFh
0x180016b20  jz      short loc_180016B57
0x180016b22  lea     rcx, [r14+40h]; this
0x180016b26  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180016b2b  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180016b32  mov     [rsp+48h+var_20], 10CAh
0x180016b3a  mov     dword ptr [rsp+48h+var_28], esi
0x180016b3e  mov     r9d, eax
0x180016b41  lea     r8, aCquerySetcomma_2; "<CQuery::SetCommandText|ADO|ERR> %u#,0x"...
0x180016b48  mov     edx, 432809h
0x180016b4d  call    _bidTraceW
0x180016b52  jmp     loc_1800167E1
0x180016b57  mov     dword ptr [rsp+48h+var_28], 10CAh
0x180016b5f  mov     r9d, esi
0x180016b62  lea     r8, aCquerySetcomma_1; "<CQuery::SetCommandText|ADO|ERR> 0x%08x"...
0x180016b69  mov     edx, 432809h
0x180016b6e  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180016b75  call    _bidTraceW
0x180016b7a  jmp     loc_1800167E1
```
