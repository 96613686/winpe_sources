# CRdlsSqlTableKeyPackDesc::PrepareUpdateQueryStatement(IOdbcExecutionContext *,void *,ulong)

- ea: `0x1800923b0`
- end: `0x1800927e7`
- name: `?PrepareUpdateQueryStatement@CRdlsSqlTableKeyPackDesc@@UEAAPEAGPEAVIOdbcExecutionContext@@PEAXK@Z`
- size: `1079`
- prototype: `unsigned __int16 *(CRdlsSqlTableKeyPackDesc *__hidden this, struct IOdbcExecutionContext *, void *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180078be4`
- `0x180086778`
- `0x180091ce0`
- `0x1800923b0`
- `0x1800a5010`

## import_xrefs

- `msvcrt!wprintf_s` at `0x18009278a`
- `msvcrt!wprintf_s` at `0x18009279f`
- `msvcrt!wprintf_s` at `0x18009278a`
- `msvcrt!wprintf_s` at `0x18009279f`

## string_xrefs

- `0x180092783`: `"pOdbcExecContext->BindParameter, PrepareUpdateQueryStatement"`
- `0x1800925f6`: `, [CompanyName] = ? `
- `0x180092609`: `[CompanyName] = ? `
- `0x1800923f4`: `UPDATE [Rdls].[LICPACKDESCRECORD] SET `

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int16 *__fastcall CRdlsSqlTableKeyPackDesc::PrepareUpdateQueryStatement(
        CRdlsSqlTableKeyPackDesc *this,
        struct IOdbcExecutionContext *a2,
        char *a3,
        int a4)
{
  __int64 v8; // rbx
  int v9; // edi
  __int64 v10; // rsi
  __int64 v11; // r8
  __int64 v12; // r8
  int v13; // ebx
  __int64 v14; // r8
  const unsigned __int16 *v15; // rdx
  __int64 v16; // r8
  const unsigned __int16 *v17; // rdx
  __int64 v18; // r8
  const unsigned __int16 *v19; // rdx
  __int64 v20; // r8
  const unsigned __int16 *v21; // rdx
  __int64 v22; // r8
  const unsigned __int16 *v23; // rdx
  __int64 v24; // r8
  const unsigned __int16 *v25; // rdx
  __int64 v27; // [rsp+80h] [rbp+40h] BYREF

  v8 = 0;
  v9 = 0;
  v27 = 0;
  if ( a4 )
  {
    CRdlsSqlTableKeyPackDesc::InitDataSizes(this, a3);
    v10 = -1;
    v11 = -1;
    do
      ++v11;
    while ( aUpdateRdlsLicp[v11] );
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v27, L"UPDATE [Rdls].[LICPACKDESCRECORD] SET ", v11);
    if ( (a4 & 1) != 0 )
    {
      v12 = -1;
      do
        ++v12;
      while ( aInternalkeypac_3[v12] );
      ATL::CComBSTR::Append((ATL::CComBSTR *)&v27, L" [InternalKeyPackId] = ? ", v12);
      v13 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
              a2,
              0,
              2,
              2,
              0,
              a3 + 4,
              (char *)this + 16);
      if ( v13 )
        goto LABEL_64;
      v9 = 1;
    }
    if ( (a4 & 0x80u) != 0 )
    {
      v14 = -1;
      if ( v9 )
      {
        v15 = L", [LangId] = ? ";
        do
          ++v14;
        while ( aLangid_0[v14] );
      }
      else
      {
        v15 = L"[LangId] = ? ";
        do
          ++v14;
        while ( aLangid_1[v14] );
      }
      ATL::CComBSTR::Append((ATL::CComBSTR *)&v27, v15, v14);
      v13 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
              a2,
              0,
              2,
              2,
              0,
              a3 + 8,
              (char *)this + 24);
      if ( v13 )
        goto LABEL_64;
      ++v9;
    }
    if ( a4 < 0 )
    {
      v16 = -1;
      if ( v9 )
      {
        v17 = L", [LastModifyTime] = ? ";
        do
          ++v16;
        while ( aLastmodifytime_2[v16] );
      }
      else
      {
        v17 = L"[LastModifyTime] = ? ";
        do
          ++v16;
        while ( aLastmodifytime_1[v16] );
      }
      ATL::CComBSTR::Append((ATL::CComBSTR *)&v27, v17, v16);
      v13 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
              a2,
              0,
              12,
              5,
              0,
              a3 + 12,
              (char *)this + 32);
      if ( v13 )
        goto LABEL_64;
      ++v9;
    }
    if ( (a4 & 0x40000000) != 0 )
    {
      v18 = -1;
      if ( v9 )
      {
        v19 = L", [EntryStatus] = ? ";
        do
          ++v18;
        while ( aEntrystatus_0[v18] );
      }
      else
      {
        v19 = L"[EntryStatus] = ? ";
        do
          ++v18;
        while ( aEntrystatus[v18] );
      }
      ATL::CComBSTR::Append((ATL::CComBSTR *)&v27, v19, v18);
      v13 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
              a2,
              0,
              11,
              4,
              0,
              a3,
              (char *)this + 8);
      if ( v13 )
        goto LABEL_64;
      ++v9;
    }
    if ( (a4 & 0x1000) != 0 )
    {
      v20 = -1;
      if ( v9 )
      {
        v21 = L", [CompanyName] = ? ";
        do
          ++v20;
        while ( aCompanyname_1[v20] );
      }
      else
      {
        v21 = L"[CompanyName] = ? ";
        do
          ++v20;
        while ( aCompanyname_0[v20] );
      }
      ATL::CComBSTR::Append((ATL::CComBSTR *)&v27, v21, v20);
      v13 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, _QWORD, __int64, char *))(*(_QWORD *)a2 + 32LL))(
              a2,
              0,
              0,
              256,
              a3 + 20);
      if ( v13 )
        goto LABEL_64;
      ++v9;
    }
    if ( (a4 & 0x4000) == 0 )
      goto LABEL_54;
    v22 = -1;
    if ( v9 )
    {
      v23 = L", [ProductDesc] = ? ";
      do
        ++v22;
      while ( aProductdesc_1[v22] );
    }
    else
    {
      v23 = L"[ProductDesc] = ? ";
      do
        ++v22;
      while ( aProductdesc[v22] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v27, v23, v22);
    v13 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, _QWORD, __int64, char *))(*(_QWORD *)a2 + 32LL))(
            a2,
            0,
            0,
            256,
            a3 + 1044);
    if ( !v13 )
    {
      ++v9;
LABEL_54:
      if ( (a4 & 0x2000) == 0 )
        goto LABEL_71;
      v24 = -1;
      if ( v9 )
      {
        v25 = L", [ProductName] = ? ";
        do
          ++v24;
        while ( aProductname_1[v24] );
      }
      else
      {
        v25 = L"[ProductName] = ? ";
        do
          ++v24;
        while ( aProductname[v24] );
      }
      ATL::CComBSTR::Append((ATL::CComBSTR *)&v27, v25, v24);
      v13 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, _QWORD, __int64, char *))(*(_QWORD *)a2 + 32LL))(
              a2,
              0,
              0,
              256,
              a3 + 532);
      if ( !v13 )
      {
LABEL_71:
        do
          ++v10;
        while ( aWhereInternalk[v10] );
        ATL::CComBSTR::Append((ATL::CComBSTR *)&v27, L" WHERE [InternalKeyPackId] = ? ", v10);
        v13 = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
                a2,
                0,
                2,
                2,
                0,
                a3 + 4,
                (char *)this + 16);
        if ( !v13 )
          goto LABEL_65;
      }
    }
LABEL_64:
    wprintf_s(L"\"pOdbcExecContext->BindParameter, PrepareUpdateQueryStatement\"");
    wprintf_s(L" 0x%x \n", (unsigned int)v13);
LABEL_65:
    if ( v13 < 0 )
    {
      v8 = 0;
    }
    else
    {
      v8 = v27;
      v27 = 0;
    }
  }
  ATL::CComBSTR::~CComBSTR((ATL::CComBSTR *)&v27);
  return (unsigned __int16 *)v8;
}

```

## disassembly

```asm
0x1800923b0  mov     [rsp-28h+arg_0], rbx
0x1800923b5  mov     [rsp-28h+arg_8], rsi
0x1800923ba  mov     [rsp-28h+arg_18], rdi
0x1800923bf  push    rbp
0x1800923c0  push    r12
0x1800923c2  push    r13
0x1800923c4  push    r14
0x1800923c6  push    r15
0x1800923c8  mov     rbp, rsp
0x1800923cb  sub     rsp, 40h
0x1800923cf  mov     r14d, r9d
0x1800923d2  mov     r13, r8
0x1800923d5  mov     r15, rdx
0x1800923d8  mov     r12, rcx
0x1800923db  xor     ebx, ebx
0x1800923dd  mov     edi, ebx
0x1800923df  mov     [rbp+arg_10], rbx
0x1800923e3  test    r9d, r9d
0x1800923e6  jz      loc_1800927BC
0x1800923ec  mov     rdx, r8; void *
0x1800923ef  call    ?InitDataSizes@CRdlsSqlTableKeyPackDesc@@AEAAXPEAX@Z; CRdlsSqlTableKeyPackDesc::InitDataSizes(void *)
0x1800923f4  lea     rdx, aUpdateRdlsLicp; "UPDATE [Rdls].[LICPACKDESCRECORD] SET "
0x1800923fb  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800923ff  mov     r8, rsi
0x180092402  inc     r8; int
0x180092405  cmp     [rdx+r8*2], bx
0x18009240a  jnz     short loc_180092402
0x18009240c  lea     rcx, [rbp+arg_10]; this
0x180092410  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180092415  test    r14b, 1
0x180092419  jz      short loc_18009247A
0x18009241b  lea     rdx, aInternalkeypac_3; " [InternalKeyPackId] = ? "
0x180092422  mov     r8, rsi
0x180092425  inc     r8; int
0x180092428  cmp     [rdx+r8*2], bx
0x18009242d  jnz     short loc_180092425
0x18009242f  lea     rcx, [rbp+arg_10]; this
0x180092433  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180092438  mov     rax, [r15]
0x18009243b  lea     rcx, [r12+10h]
0x180092440  lea     rdx, [r13+4]
0x180092444  mov     [rsp+40h+var_10], rcx
0x180092449  mov     [rsp+40h+var_18], rdx
0x18009244e  mov     dword ptr [rsp+40h+var_20], ebx
0x180092452  mov     r8d, 2
0x180092458  mov     r9d, r8d
0x18009245b  xor     edx, edx
0x18009245d  mov     rcx, r15
0x180092460  mov     rax, [rax+28h]
0x180092464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092469  mov     ebx, eax
0x18009246b  xor     eax, eax
0x18009246d  test    ebx, ebx
0x18009246f  jnz     loc_180092783
0x180092475  lea     edi, [rax+1]
0x180092478  jmp     short loc_18009247C
0x18009247a  xor     eax, eax
0x18009247c  test    r14b, r14b
0x18009247f  jns     short loc_1800924F8
0x180092481  mov     r8, rsi
0x180092484  test    edi, edi
0x180092486  jz      short loc_18009249B
0x180092488  lea     rdx, aLangid_0; ", [LangId] = ? "
0x18009248f  inc     r8
0x180092492  cmp     [rdx+r8*2], ax
0x180092497  jnz     short loc_18009248F
0x180092499  jmp     short loc_1800924AC
0x18009249b  lea     rdx, aLangid_1; "[LangId] = ? "
0x1800924a2  inc     r8; int
0x1800924a5  cmp     [rdx+r8*2], ax
0x1800924aa  jnz     short loc_1800924A2
0x1800924ac  lea     rcx, [rbp+arg_10]; this
0x1800924b0  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800924b5  mov     rax, [r15]
0x1800924b8  lea     rcx, [r12+18h]
0x1800924bd  lea     rdx, [r13+8]
0x1800924c1  mov     [rsp+40h+var_10], rcx
0x1800924c6  mov     [rsp+40h+var_18], rdx
0x1800924cb  xor     ecx, ecx
0x1800924cd  mov     dword ptr [rsp+40h+var_20], ecx
0x1800924d1  mov     ecx, 2
0x1800924d6  mov     r9d, ecx
0x1800924d9  mov     r8d, ecx
0x1800924dc  xor     edx, edx
0x1800924de  mov     rcx, r15
0x1800924e1  mov     rax, [rax+28h]
0x1800924e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800924ea  mov     ebx, eax
0x1800924ec  xor     eax, eax
0x1800924ee  test    ebx, ebx
0x1800924f0  jnz     loc_180092783
0x1800924f6  inc     edi
0x1800924f8  test    r14d, r14d
0x1800924fb  jns     short loc_180092571
0x1800924fd  mov     r8, rsi
0x180092500  test    edi, edi
0x180092502  jz      short loc_180092517
0x180092504  lea     rdx, aLastmodifytime_2; ", [LastModifyTime] = ? "
0x18009250b  inc     r8
0x18009250e  cmp     [rdx+r8*2], ax
0x180092513  jnz     short loc_18009250B
0x180092515  jmp     short loc_180092528
0x180092517  lea     rdx, aLastmodifytime_1; "[LastModifyTime] = ? "
0x18009251e  inc     r8; int
0x180092521  cmp     [rdx+r8*2], ax
0x180092526  jnz     short loc_18009251E
0x180092528  lea     rcx, [rbp+arg_10]; this
0x18009252c  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180092531  mov     rax, [r15]
0x180092534  lea     rcx, [r12+20h]
0x180092539  lea     rdx, [r13+0Ch]
0x18009253d  mov     [rsp+40h+var_10], rcx
0x180092542  mov     [rsp+40h+var_18], rdx
0x180092547  xor     ecx, ecx
0x180092549  mov     dword ptr [rsp+40h+var_20], ecx
0x18009254d  xor     edx, edx
0x18009254f  lea     r9d, [rcx+5]
0x180092553  lea     r8d, [rcx+0Ch]
0x180092557  mov     rcx, r15
0x18009255a  mov     rax, [rax+28h]
0x18009255e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092563  mov     ebx, eax
0x180092565  xor     eax, eax
0x180092567  test    ebx, ebx
0x180092569  jnz     loc_180092783
0x18009256f  inc     edi
0x180092571  bt      r14d, 1Eh
0x180092576  jnb     short loc_1800925E8
0x180092578  mov     r8, rsi
0x18009257b  test    edi, edi
0x18009257d  jz      short loc_180092592
0x18009257f  lea     rdx, aEntrystatus_0; ", [EntryStatus] = ? "
0x180092586  inc     r8
0x180092589  cmp     [rdx+r8*2], ax
0x18009258e  jnz     short loc_180092586
0x180092590  jmp     short loc_1800925A3
0x180092592  lea     rdx, aEntrystatus; "[EntryStatus] = ? "
0x180092599  inc     r8; int
0x18009259c  cmp     [rdx+r8*2], ax
0x1800925a1  jnz     short loc_180092599
0x1800925a3  lea     rcx, [rbp+arg_10]; this
0x1800925a7  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800925ac  mov     rax, [r15]
0x1800925af  lea     rcx, [r12+8]
0x1800925b4  mov     [rsp+40h+var_10], rcx
0x1800925b9  mov     [rsp+40h+var_18], r13
0x1800925be  xor     ecx, ecx
0x1800925c0  mov     dword ptr [rsp+40h+var_20], ecx
0x1800925c4  xor     edx, edx
0x1800925c6  lea     r9d, [rcx+4]
0x1800925ca  lea     r8d, [rcx+0Bh]
0x1800925ce  mov     rcx, r15
0x1800925d1  mov     rax, [rax+28h]
0x1800925d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800925da  mov     ebx, eax
0x1800925dc  xor     eax, eax
0x1800925de  test    ebx, ebx
0x1800925e0  jnz     loc_180092783
0x1800925e6  inc     edi
0x1800925e8  bt      r14d, 0Ch
0x1800925ed  jnb     short loc_180092654
0x1800925ef  mov     r8, rsi
0x1800925f2  test    edi, edi
0x1800925f4  jz      short loc_180092609
0x1800925f6  lea     rdx, aCompanyname_1; ", [CompanyName] = ? "
0x1800925fd  inc     r8
0x180092600  cmp     [rdx+r8*2], ax
0x180092605  jnz     short loc_1800925FD
0x180092607  jmp     short loc_18009261A
0x180092609  lea     rdx, aCompanyname_0; "[CompanyName] = ? "
0x180092610  inc     r8; int
0x180092613  cmp     [rdx+r8*2], ax
0x180092618  jnz     short loc_180092610
0x18009261a  lea     rcx, [rbp+arg_10]; this
0x18009261e  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180092623  mov     rax, [r15]
0x180092626  lea     rcx, [r13+14h]
0x18009262a  mov     [rsp+40h+var_20], rcx
0x18009262f  mov     r9d, 100h
0x180092635  xor     r8d, r8d
0x180092638  xor     edx, edx
0x18009263a  mov     rcx, r15
0x18009263d  mov     rax, [rax+20h]
0x180092641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092646  mov     ebx, eax
0x180092648  xor     eax, eax
0x18009264a  test    ebx, ebx
0x18009264c  jnz     loc_180092783
0x180092652  inc     edi
0x180092654  bt      r14d, 0Eh
0x180092659  jnb     short loc_1800926C3
0x18009265b  mov     r8, rsi
0x18009265e  test    edi, edi
0x180092660  jz      short loc_180092675
0x180092662  lea     rdx, aProductdesc_1; ", [ProductDesc] = ? "
0x180092669  inc     r8
0x18009266c  cmp     [rdx+r8*2], ax
0x180092671  jnz     short loc_180092669
0x180092673  jmp     short loc_180092686
0x180092675  lea     rdx, aProductdesc; "[ProductDesc] = ? "
0x18009267c  inc     r8; int
0x18009267f  cmp     [rdx+r8*2], ax
0x180092684  jnz     short loc_18009267C
0x180092686  lea     rcx, [rbp+arg_10]; this
0x18009268a  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18009268f  mov     rax, [r15]
0x180092692  lea     rcx, [r13+414h]
0x180092699  mov     [rsp+40h+var_20], rcx
0x18009269e  mov     r9d, 100h
0x1800926a4  xor     r8d, r8d
0x1800926a7  xor     edx, edx
0x1800926a9  mov     rcx, r15
0x1800926ac  mov     rax, [rax+20h]
0x1800926b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800926b5  mov     ebx, eax
0x1800926b7  xor     eax, eax
0x1800926b9  test    ebx, ebx
0x1800926bb  jnz     loc_180092783
0x1800926c1  inc     edi
0x1800926c3  bt      r14d, 0Dh
0x1800926c8  jnb     short loc_18009272C
0x1800926ca  mov     r8, rsi
0x1800926cd  test    edi, edi
0x1800926cf  jz      short loc_1800926E4
0x1800926d1  lea     rdx, aProductname_1; ", [ProductName] = ? "
0x1800926d8  inc     r8
0x1800926db  cmp     [rdx+r8*2], ax
0x1800926e0  jnz     short loc_1800926D8
0x1800926e2  jmp     short loc_1800926F5
0x1800926e4  lea     rdx, aProductname; "[ProductName] = ? "
0x1800926eb  inc     r8; int
0x1800926ee  cmp     [rdx+r8*2], ax
0x1800926f3  jnz     short loc_1800926EB
0x1800926f5  lea     rcx, [rbp+arg_10]; this
0x1800926f9  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800926fe  mov     rax, [r15]
0x180092701  lea     rcx, [r13+214h]
0x180092708  mov     [rsp+40h+var_20], rcx
0x18009270d  mov     r9d, 100h
0x180092713  xor     r8d, r8d
0x180092716  xor     edx, edx
0x180092718  mov     rcx, r15
0x18009271b  mov     rax, [rax+20h]
0x18009271f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092724  mov     ebx, eax
0x180092726  xor     eax, eax
0x180092728  test    ebx, ebx
0x18009272a  jnz     short loc_180092783
0x18009272c  lea     rdx, aWhereInternalk; " WHERE [InternalKeyPackId] = ? "
0x180092733  inc     rsi
0x180092736  cmp     [rdx+rsi*2], ax
0x18009273a  jnz     short loc_180092733
0x18009273c  mov     r8d, esi; int
0x18009273f  lea     rcx, [rbp+arg_10]; this
0x180092743  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180092748  mov     rax, [r15]
0x18009274b  lea     rcx, [r12+10h]
0x180092750  lea     rdx, [r13+4]
0x180092754  mov     [rsp+40h+var_10], rcx
0x180092759  mov     [rsp+40h+var_18], rdx
0x18009275e  xor     ecx, ecx
0x180092760  mov     dword ptr [rsp+40h+var_20], ecx
0x180092764  mov     ecx, 2
0x180092769  mov     r9d, ecx
0x18009276c  mov     r8d, ecx
0x18009276f  xor     edx, edx
0x180092771  mov     rcx, r15
0x180092774  mov     rax, [rax+28h]
0x180092778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009277d  mov     ebx, eax
0x18009277f  test    eax, eax
0x180092781  jz      short loc_1800927AB
0x180092783  lea     rcx, aPodbcexecconte_2; "\"pOdbcExecContext->BindParameter, Prep"...
0x18009278a  call    cs:__imp_wprintf_s
0x180092791  nop     dword ptr [rax+rax+00h]
0x180092796  mov     edx, ebx
0x180092798  lea     rcx, a0xX; " 0x%x \n"
0x18009279f  call    cs:__imp_wprintf_s
0x1800927a6  nop     dword ptr [rax+rax+00h]
0x1800927ab  test    ebx, ebx
0x1800927ad  js      short loc_1800927BA
0x1800927af  mov     rbx, [rbp+arg_10]
0x1800927b3  and     [rbp+arg_10], 0
0x1800927b8  jmp     short loc_1800927BC
0x1800927ba  xor     ebx, ebx
0x1800927bc  lea     rcx, [rbp+arg_10]; this
0x1800927c0  call    ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x1800927c5  mov     rax, rbx
0x1800927c8  lea     r11, [rsp+40h+var_s0]
0x1800927cd  mov     rbx, [r11+30h]
0x1800927d1  mov     rsi, [r11+38h]
0x1800927d5  mov     rdi, [r11+48h]
0x1800927d9  mov     rsp, r11
0x1800927dc  pop     r15
0x1800927de  pop     r14
0x1800927e0  pop     r13
0x1800927e2  pop     r12
0x1800927e4  pop     rbp
0x1800927e5  retn
```
