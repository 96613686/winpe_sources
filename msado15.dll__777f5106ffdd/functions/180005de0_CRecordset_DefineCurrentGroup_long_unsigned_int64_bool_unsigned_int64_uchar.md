# CRecordset::DefineCurrentGroup(long,unsigned __int64,bool,unsigned __int64,uchar *)

- ea: `0x180005de0`
- end: `0x1800062fe`
- name: `?DefineCurrentGroup@CRecordset@@AEAAJJ_K_N0PEAE@Z`
- size: `1310`
- prototype: `int(CRecordset *__hidden this, int, unsigned __int64, bool, unsigned __int64, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005a70`

## callees

- `0x180001514`
- `0x180005de0`
- `0x180006310`
- `0x18006a22c`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapFree` at `0x180006080`
- `MSDART!MpHeapFree` at `0x180006080`
- `ole32!CoTaskMemFree` at `0x1800062ed`
- `ole32!CoTaskMemFree` at `0x1800062ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRecordset::DefineCurrentGroup(
        CRecordset *this,
        int a2,
        unsigned __int64 a3,
        bool a4,
        unsigned __int64 a5)
{
  int v8; // esi
  unsigned __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r15
  __int64 v12; // r13
  __int64 v13; // r12
  int v14; // eax
  _BYTE *v15; // rax
  BOOL v16; // r14d
  int v17; // eax
  void *v18; // rcx
  __int64 v19; // rdx
  _QWORD *v20; // rbx
  __int64 v22; // r8
  unsigned int BidObjectID; // eax
  unsigned int v24; // eax
  __int64 v25; // r9
  __int64 v26; // rdx
  unsigned int v27; // eax
  __int64 v28; // rax
  __int64 v29; // [rsp+20h] [rbp-68h]
  __int128 v30; // [rsp+30h] [rbp-58h] BYREF
  __int64 v31; // [rsp+40h] [rbp-48h]

  v8 = CRecordGroup::SetGroupProperties((CRecordset *)((char *)this + 736), a3, a4, 1u, 1u);
  if ( v8 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
      {
        bidTraceW(off_18012A208[0], 8743945, L"<CRecordset::DefineCurrentGroup|ADO|ERR>  line %d\n", 8539);
      }
      else
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        LODWORD(v29) = 8539;
        bidTraceW(
          off_18012A208[0],
          8743945,
          L"<CRecordset::DefineCurrentGroup|ADO|ERR> %u#, line %d\n",
          BidObjectID,
          v29);
      }
    }
  }
  else if ( a3 )
  {
    v9 = 0;
    a5 = 0;
    v10 = *((_QWORD *)this + 141);
    if ( !v10 )
      goto LABEL_30;
    v8 = 0;
    if ( (*((_BYTE *)this + 1136) & 1) != 0 )
    {
      a5 = 0;
      if ( (_DWORD)v10 )
      {
        v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, GUID *, unsigned __int64 *))(**((_QWORD **)g_pStaticGlobals + 10)
                                                                                    + 40LL))(
               *((_QWORD *)g_pStaticGlobals + 10),
               v10,
               &IID_IRowset,
               &a5);
        v9 = a5;
      }
    }
    else
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v10 + 8LL))(*((_QWORD *)this + 141));
      v9 = *((_QWORD *)this + 141);
      a5 = v9;
    }
    if ( v8 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
        {
          v25 = 8544;
          v26 = 8749065;
LABEL_52:
          bidTraceW(off_18012A208[0], v26, L"<CRecordset::DefineCurrentGroup|ADO|ERR>  line %d\n", v25);
        }
        else
        {
          v24 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          LODWORD(v29) = 8544;
          bidTraceW(off_18012A208[0], 8749065, L"<CRecordset::DefineCurrentGroup|ADO|ERR> %u#, line %d\n", v24, v29);
        }
      }
    }
    else
    {
LABEL_30:
      if ( a4 )
        v11 = 0;
      else
        v11 = *((_QWORD *)this + 93) - 1LL;
      *((_QWORD *)this + 91) = *((_QWORD *)this + 93) - a3;
      v30 = 0;
      v17 = 8;
      v31 = 8;
      while ( 1 )
      {
        v22 = *((_QWORD *)this + 150);
        if ( !v22 )
        {
          v30 = 0u;
          v8 = 0;
          goto LABEL_17;
        }
        v8 = (*(__int64 (__fastcall **)(unsigned __int64, _QWORD, __int64, __int128 *))(*(_QWORD *)v9 + 32LL))(
               v9,
               *(_QWORD *)(*((_QWORD *)this + 97) + 8 * v11),
               v22,
               &v30);
        v17 = v31;
        if ( v8 == -2147217887 && (_DWORD)v31 == 8 )
        {
          v30 = 0u;
          v8 = 0;
        }
        if ( v8 != -2147217885 )
          break;
        if ( a4 )
          ++v11;
        else
          --v11;
        if ( v11 < 0 || v11 >= (__int64)a3 )
          goto LABEL_57;
        v9 = a5;
      }
      if ( v8 >= 0 )
      {
        v9 = a5;
LABEL_17:
        if ( v17 )
        {
          v12 = byBmkLast;
          v13 = 1;
          v16 = 0;
        }
        else
        {
          v13 = *((_QWORD *)&v30 + 1);
          v12 = v30;
          v16 = *((_BYTE *)this + 1256) == 1;
        }
        if ( v9 )
          (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v9 + 16LL))(v9);
        v15 = (char *)this + 1504;
        goto LABEL_22;
      }
LABEL_57:
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
        {
          v25 = 8572;
          v26 = 8777737;
          goto LABEL_52;
        }
        v27 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        LODWORD(v29) = 8572;
        bidTraceW(off_18012A208[0], 8777737, L"<CRecordset::DefineCurrentGroup|ADO|ERR> %u#, line %d\n", v27, v29);
      }
    }
    ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&a5);
  }
  else
  {
    v11 = -1;
    v12 = byBmkFirst;
    if ( !a4 )
      v12 = byBmkLast;
    v13 = 1;
    v14 = *((_DWORD *)this + 174);
    if ( (v14 & 0x100) == 0 || (v14 & 0x200) != 0 )
    {
      *((_QWORD *)this + 91) = 0;
    }
    else
    {
      v28 = *((_QWORD *)this + 91);
      if ( a4 )
      {
        if ( v28 > 0 )
          *((_QWORD *)this + 91) = v28 - 1;
      }
      else if ( (unsigned __int64)v28 < *((_QWORD *)this + 93) )
      {
        *((_QWORD *)this + 91) = v28 + 1;
      }
    }
    v15 = (char *)this + 1504;
    v16 = 0;
    if ( *((_BYTE *)this + 1504) )
      *((_QWORD *)this + 96) = 0;
LABEL_22:
    if ( !*v15 || a3 && (a2 != 265926 || a3 > 1) )
    {
      v18 = (void *)*((_QWORD *)this + 101);
      if ( v18 && *((_DWORD *)this + 199) )
        CoTaskMemFree(v18);
      *((_BYTE *)this + 833) = 0;
      *((_QWORD *)this + 100) = v13;
      *((_QWORD *)this + 101) = v12;
      *((_DWORD *)this + 199) = v16;
      *((_QWORD *)this + 96) = v11;
      v19 = *((_QWORD *)this + 102);
      if ( v19 )
      {
        MpHeapFree(g_hHeapHandle, v19);
        *((_QWORD *)this + 102) = 0;
        v20 = (_QWORD *)((char *)this + 824);
        *v20 = 0;
      }
      else
      {
        v20 = (_QWORD *)((char *)this + 824);
      }
      *v20 = 0;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180005de0  mov     [rsp+arg_10], rbx
0x180005de5  mov     [rsp+arg_8], edx
0x180005de9  push    rbp
0x180005dea  push    rsi
0x180005deb  push    rdi
0x180005dec  push    r12
0x180005dee  push    r13
0x180005df0  push    r14
0x180005df2  push    r15
0x180005df4  sub     rsp, 50h
0x180005df8  movzx   r14d, r9b
0x180005dfc  mov     rbp, r8
0x180005dff  mov     rbx, rcx
0x180005e02  add     rcx, 2E0h; this
0x180005e09  mov     [rsp+88h+var_68], 1; unsigned __int8
0x180005e0e  mov     r9b, 1; unsigned __int8
0x180005e11  movzx   r8d, r14b; bool
0x180005e15  mov     rdx, rbp; unsigned __int64
0x180005e18  call    ?SetGroupProperties@CRecordGroup@@QEAAJ_K_NEE@Z; CRecordGroup::SetGroupProperties(unsigned __int64,bool,uchar,uchar)
0x180005e1d  mov     esi, eax
0x180005e1f  test    eax, eax
0x180005e21  js      loc_1800060D8
0x180005e27  test    rbp, rbp
0x180005e2a  jz      short loc_180005E9C
0x180005e2c  xor     edi, edi
0x180005e2e  mov     ecx, edi
0x180005e30  mov     [rsp+88h+arg_20], rcx
0x180005e38  mov     rdx, [rbx+468h]
0x180005e3f  test    rdx, rdx
0x180005e42  jz      loc_18000601C
0x180005e48  mov     esi, edi
0x180005e4a  test    byte ptr [rbx+470h], 1
0x180005e51  jz      loc_180005FF6
0x180005e57  test    edx, edx
0x180005e59  jz      loc_1800060C6
0x180005e5f  mov     [rsp+88h+arg_20], rdi
0x180005e67  mov     rax, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180005e6e  mov     rcx, [rax+50h]
0x180005e72  mov     rax, [rcx]
0x180005e75  lea     r9, [rsp+88h+arg_20]
0x180005e7d  lea     r8, IID_IRowset
0x180005e84  mov     rax, [rax+28h]
0x180005e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e8d  mov     esi, eax
0x180005e8f  mov     rcx, [rsp+88h+arg_20]
0x180005e97  jmp     loc_180006014
0x180005e9c  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180005ea3  test    r14b, r14b
0x180005ea6  movzx   r13d, cs:?byBmkFirst@@3EA; uchar byBmkFirst
0x180005eae  jnz     short loc_180005EB8
0x180005eb0  movzx   r13d, cs:?byBmkLast@@3EA; uchar byBmkLast
0x180005eb8  xor     edi, edi
0x180005eba  mov     r12d, 1
0x180005ec0  mov     [rsp+88h+arg_0], edi
0x180005ec7  mov     eax, [rbx+2B8h]
0x180005ecd  bt      eax, 8
0x180005ed1  jb      loc_18000626D
0x180005ed7  mov     [rbx+2D8h], rdi
0x180005ede  lea     rax, [rbx+5E0h]
0x180005ee5  mov     r14d, [rsp+88h+arg_0]
0x180005eed  cmp     [rax], dil
0x180005ef0  jz      loc_180005F85
0x180005ef6  mov     [rbx+300h], rdi
0x180005efd  jmp     loc_180005F85
0x180005f02  mov     rax, [rcx]
0x180005f05  mov     rdx, [rbx+308h]
0x180005f0c  lea     r9, [rsp+88h+var_58]
0x180005f11  mov     rdx, [rdx+r15*8]
0x180005f15  mov     rax, [rax+20h]
0x180005f19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f1e  mov     esi, eax
0x180005f20  mov     eax, dword ptr [rsp+88h+var_48]
0x180005f24  cmp     esi, 80040E21h
0x180005f2a  jz      loc_180006213
0x180005f30  cmp     esi, 80040E23h
0x180005f36  jz      loc_1800060A2
0x180005f3c  test    esi, esi
0x180005f3e  js      loc_18000622D
0x180005f44  mov     rcx, [rsp+88h+arg_20]
0x180005f4c  test    eax, eax
0x180005f4e  jz      loc_180006250
0x180005f54  movzx   r13d, cs:?byBmkLast@@3EA; uchar byBmkLast
0x180005f5c  mov     r12d, 1
0x180005f62  mov     [rsp+88h+arg_0], edi
0x180005f69  mov     r14d, edi
0x180005f6c  test    rcx, rcx
0x180005f6f  jz      short loc_180005F7E
0x180005f71  mov     rax, [rcx]
0x180005f74  mov     rax, [rax+10h]
0x180005f78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f7d  nop
0x180005f7e  lea     rax, [rbx+5E0h]
0x180005f85  cmp     byte ptr [rax], 0
0x180005f88  jnz     loc_1800062B7
0x180005f8e  mov     rcx, [rbx+328h]; pv
0x180005f95  test    rcx, rcx
0x180005f98  jnz     loc_1800062E0
0x180005f9e  mov     byte ptr [rbx+341h], 0
0x180005fa5  mov     [rbx+320h], r12
0x180005fac  mov     [rbx+328h], r13
0x180005fb3  mov     [rbx+31Ch], r14d
0x180005fba  mov     [rbx+300h], r15
0x180005fc1  mov     rdx, [rbx+330h]
0x180005fc8  test    rdx, rdx
0x180005fcb  jnz     loc_180006079
0x180005fd1  add     rbx, 338h
0x180005fd8  mov     [rbx], rdi
0x180005fdb  mov     eax, esi
0x180005fdd  mov     rbx, [rsp+88h+arg_10]
0x180005fe5  add     rsp, 50h
0x180005fe9  pop     r15
0x180005feb  pop     r14
0x180005fed  pop     r13
0x180005fef  pop     r12
0x180005ff1  pop     rdi
0x180005ff2  pop     rsi
0x180005ff3  pop     rbp
0x180005ff4  retn
0x180005ff6  mov     rax, [rdx]
0x180005ff9  mov     rcx, rdx
0x180005ffc  mov     rax, [rax+8]
0x180006000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006005  mov     rcx, [rbx+468h]
0x18000600c  mov     [rsp+88h+arg_20], rcx
0x180006014  test    esi, esi
0x180006016  js      loc_18000614D
0x18000601c  test    r14b, r14b
0x18000601f  jnz     loc_18000620B
0x180006025  mov     r15, [rbx+2E8h]
0x18000602c  dec     r15
0x18000602f  mov     rax, [rbx+2E8h]
0x180006036  sub     rax, rbp
0x180006039  mov     [rbx+2D8h], rax
0x180006040  xorps   xmm0, xmm0
0x180006043  xor     eax, eax
0x180006045  movups  [rsp+88h+var_58], xmm0
0x18000604a  mov     [rsp+88h+var_48], rax
0x18000604f  mov     eax, 8
0x180006054  mov     dword ptr [rsp+88h+var_48], eax
0x180006058  mov     r8, [rbx+4B0h]
0x18000605f  test    r8, r8
0x180006062  jnz     loc_180005F02
0x180006068  mov     qword ptr [rsp+88h+var_58], rdi
0x18000606d  mov     qword ptr [rsp+88h+var_58+8], rdi
0x180006072  mov     esi, edi
0x180006074  jmp     loc_180005F4C
0x180006079  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180006080  call    cs:__imp_MpHeapFree
0x180006087  nop     dword ptr [rax+rax+00h]
0x18000608c  mov     [rbx+330h], rdi
0x180006093  add     rbx, 338h
0x18000609a  mov     [rbx], rdi
0x18000609d  jmp     loc_180005FD8
0x1800060a2  test    r14b, r14b
0x1800060a5  jnz     short loc_1800060D3
0x1800060a7  dec     r15
0x1800060aa  test    r15, r15
0x1800060ad  js      loc_18000622D
0x1800060b3  cmp     r15, rbp
0x1800060b6  jge     loc_18000622D
0x1800060bc  mov     rcx, [rsp+88h+arg_20]
0x1800060c4  jmp     short loc_180006058
0x1800060c6  mov     [rsp+88h+arg_20], rcx
0x1800060ce  jmp     loc_180006014
0x1800060d3  inc     r15
0x1800060d6  jmp     short loc_1800060AA
0x1800060d8  test    byte ptr cs:_bidGblFlags, 2
0x1800060df  jz      loc_180005FDB
0x1800060e5  lea     rcx, [rbx+618h]; this
0x1800060ec  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800060f1  cmp     eax, 0FFFFFFFFh
0x1800060f4  jz      short loc_18000612A
0x1800060f6  lea     rcx, [rbx+618h]; this
0x1800060fd  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180006102  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180006109  mov     dword ptr [rsp+88h+var_68], 215Bh
0x180006111  mov     r9d, eax
0x180006114  lea     r8, aCrecordsetDefi_2; "<CRecordset::DefineCurrentGroup|ADO|ERR"...
0x18000611b  mov     edx, 856C09h
0x180006120  call    _bidTraceW
0x180006125  jmp     loc_180005FDB
0x18000612a  mov     r9d, 215Bh
0x180006130  lea     r8, aCrecordsetDefi; "<CRecordset::DefineCurrentGroup|ADO|ERR"...
0x180006137  mov     edx, 856C09h
0x18000613c  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180006143  call    _bidTraceW
0x180006148  jmp     loc_180005FDB
0x18000614d  test    byte ptr cs:_bidGblFlags, 2
0x180006154  jz      loc_1800061F9
0x18000615a  lea     rcx, [rbx+618h]; this
0x180006161  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180006166  cmp     eax, 0FFFFFFFFh
0x180006169  jz      short loc_18000619C
0x18000616b  lea     rcx, [rbx+618h]; this
0x180006172  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180006177  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18000617e  mov     dword ptr [rsp+88h+var_68], 2160h
0x180006186  mov     r9d, eax
0x180006189  lea     r8, aCrecordsetDefi_2; "<CRecordset::DefineCurrentGroup|ADO|ERR"...
0x180006190  mov     edx, 858009h
0x180006195  call    _bidTraceW
0x18000619a  jmp     short loc_1800061F9
0x18000619c  mov     r9d, 2160h
0x1800061a2  mov     edx, 858009h
0x1800061a7  jmp     short loc_1800061B4
0x1800061a9  mov     r9d, 217Ch
0x1800061af  mov     edx, 85F009h
0x1800061b4  lea     r8, aCrecordsetDefi; "<CRecordset::DefineCurrentGroup|ADO|ERR"...
0x1800061bb  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800061c2  call    _bidTraceW
0x1800061c7  jmp     short loc_1800061F9
0x1800061c9  lea     rcx, [rbx+618h]; this
0x1800061d0  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800061d5  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800061dc  mov     dword ptr [rsp+88h+var_68], 217Ch
0x1800061e4  mov     r9d, eax
0x1800061e7  lea     r8, aCrecordsetDefi_2; "<CRecordset::DefineCurrentGroup|ADO|ERR"...
0x1800061ee  mov     edx, 85F009h
0x1800061f3  call    _bidTraceW
0x1800061f8  nop
0x1800061f9  lea     rcx, [rsp+88h+arg_20]
0x180006201  call    ??1?$CComPtr@UIDBCreateSession@@@ATL@@QEAA@XZ; ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(void)
0x180006206  jmp     loc_180005FDB
0x18000620b  mov     r15, rdi
0x18000620e  jmp     loc_18000602F
0x180006213  cmp     eax, 8
0x180006216  jnz     loc_180005F30
0x18000621c  mov     qword ptr [rsp+88h+var_58], rdi
0x180006221  mov     qword ptr [rsp+88h+var_58+8], rdi
0x180006226  mov     esi, edi
0x180006228  jmp     loc_180005F30
0x18000622d  test    byte ptr cs:_bidGblFlags, 2
0x180006234  jz      short loc_1800061F9
0x180006236  lea     rcx, [rbx+618h]; this
0x18000623d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180006242  cmp     eax, 0FFFFFFFFh
0x180006245  jz      loc_1800061A9
0x18000624b  jmp     loc_1800061C9
0x180006250  mov     r13, qword ptr [rsp+88h+var_58]
0x180006255  mov     r12, qword ptr [rsp+88h+var_58+8]
0x18000625a  mov     r14d, edi
0x18000625d  cmp     byte ptr [rbx+4E8h], 1
0x180006264  setz    r14b
0x180006268  jmp     loc_180005F6C
0x18000626d  bt      eax, 9
0x180006271  jb      loc_180005ED7
0x180006277  mov     rax, [rbx+2D8h]
0x18000627e  test    r14b, r14b
0x180006281  jz      short loc_18000629B
0x180006283  test    rax, rax
0x180006286  jle     loc_180005EDE
0x18000628c  dec     rax
0x18000628f  mov     [rbx+2D8h], rax
0x180006296  jmp     loc_180005EDE
0x18000629b  cmp     rax, [rbx+2E8h]
0x1800062a2  jnb     loc_180005EDE
0x1800062a8  inc     rax
0x1800062ab  mov     [rbx+2D8h], rax
0x1800062b2  jmp     loc_180005EDE
0x1800062b7  test    rbp, rbp
0x1800062ba  jz      loc_180005FDB
0x1800062c0  cmp     [rsp+88h+arg_8], 40EC6h
0x1800062cb  jnz     loc_180005F8E
0x1800062d1  cmp     rbp, 1
0x1800062d5  jbe     loc_180005FDB
0x1800062db  jmp     loc_180005F8E
0x1800062e0  cmp     dword ptr [rbx+31Ch], 0
0x1800062e7  jz      loc_180005F9E
0x1800062ed  call    cs:__imp_CoTaskMemFree
0x1800062f4  nop     dword ptr [rax+rax+00h]
0x1800062f9  jmp     loc_180005F9E
```
