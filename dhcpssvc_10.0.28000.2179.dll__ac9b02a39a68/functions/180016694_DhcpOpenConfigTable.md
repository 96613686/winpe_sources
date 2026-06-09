# DhcpOpenConfigTable

- ea: `0x180016694`
- end: `0x180016a6e`
- name: `DhcpOpenConfigTable`
- size: `986`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000d644`
- `0x18000eaa0`
- `0x180016a74`

## callees

- `0x18000282c`
- `0x180003228`
- `0x18000e814`
- `0x180010e3c`
- `0x180016694`
- `0x1800cdac0`

## import_xrefs

- `ESENT!JetGetTableColumnInfo` at `0x180016760`
- `ESENT!JetGetTableColumnInfo` at `0x180016760`
- `ESENT!JetOpenTable` at `0x180016723`
- `ESENT!JetOpenTable` at `0x180016723`
- `ESENT!JetCreateIndex` at `0x1800169a4`
- `ESENT!JetCreateIndex` at `0x1800169a4`
- `ESENT!JetCreateTable` at `0x18001688b`
- `ESENT!JetCreateTable` at `0x18001688b`
- `ESENT!JetAddColumn` at `0x1800167c4`
- `ESENT!JetAddColumn` at `0x180016904`
- `ESENT!JetAddColumn` at `0x1800167c4`
- `ESENT!JetAddColumn` at `0x180016904`

## string_xrefs

- `0x18001684f`: `C:OpenTable`
- `0x180016899`: `C:CreateTAble`
- `0x1800169b2`: `C:CreateIndex`

## pseudocode

```c
__int64 __fastcall DhcpOpenConfigTable(__int64 a1, __int64 a2)
{
  int *v2; // rsi
  __int64 v3; // r15
  unsigned int v5; // ebx
  int *v6; // rax
  __int64 v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // r14d
  char **v10; // rbx
  unsigned int TableColumnInfo; // eax
  unsigned int v12; // edi
  char *v13; // r8
  unsigned int v14; // edi
  unsigned int Table; // eax
  char **v16; // rbx
  unsigned int v17; // r14d
  char *v18; // r8
  unsigned int v19; // eax
  unsigned int Index; // eax
  __int128 v22; // [rsp+40h] [rbp-29h] BYREF
  __int64 v23; // [rsp+50h] [rbp-19h]
  int v24; // [rsp+58h] [rbp-11h]
  __int64 v25; // [rsp+60h] [rbp-9h] BYREF
  int v26; // [rsp+68h] [rbp-1h]
  int v27; // [rsp+6Ch] [rbp+3h]
  __int64 v28; // [rsp+70h] [rbp+7h]
  int v29; // [rsp+78h] [rbp+Fh]

  v2 = dword_1800F9038;
  v3 = 25;
  v23 = 0;
  v24 = 0;
  v5 = a2;
  v22 = 0;
  v6 = dword_1800F9038;
  v7 = 25;
  do
  {
    *v6 = 0;
    v6 += 4;
    --v7;
  }
  while ( v7 );
  DbcfgTbl = 0;
  v8 = JetOpenTable(a1, a2, "DbcfgTable", 0, 0, 0, &DbcfgTbl);
  if ( v8 )
  {
    if ( v8 == -1305 )
    {
      Table = JetCreateTable(a1, v5, "DbcfgTable", 10, 80, &DbcfgTbl);
      v14 = DhcpMapJetError(Table, "C:CreateTAble");
      if ( !v14 )
      {
        *(_QWORD *)&v22 = 28;
        v16 = &DbcfgTable;
        HIDWORD(v22) = 67698689;
        v17 = 0;
        v23 = 1252;
        v24 = 0;
        while ( 1 )
        {
          v18 = *v16;
          DWORD2(v22) = *((_DWORD *)v16 + 3);
          v19 = JetAddColumn(a1, DbcfgTbl, v18, &v22, 0, 0, &dword_1800F9038[4 * v17]);
          v14 = DhcpMapJetError(v19, "C:AddColumn");
          if ( v14 )
            break;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
          {
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              18,
              (unsigned int)&WPP_4c45059f8aca3467116f61052473c3dc_Traceguids,
              (unsigned int)*v16,
              *((_DWORD *)v16 + 2));
          }
          ++v17;
          v16 += 2;
          if ( v17 >= 0x19 )
          {
            Index = JetCreateIndex(a1, DbcfgTbl, "DbcfgIndex", 3, "+DbcfgIndex", 13, 50);
            v14 = DhcpMapJetError(Index, "C:CreateIndex");
            if ( v14 )
              break;
            goto LABEL_25;
          }
        }
      }
    }
    else
    {
      v14 = DhcpMapJetError(v8, "C:OpenTable");
      if ( !v14 )
      {
LABEL_25:
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_4c45059f8aca3467116f61052473c3dc_Traceguids);
        return v14;
      }
    }
  }
  else
  {
    v9 = 0;
    v10 = &DbcfgTable;
    while ( 1 )
    {
      TableColumnInfo = JetGetTableColumnInfo(a1, DbcfgTbl, *v10, &v22, 28, 0);
      v12 = TableColumnInfo;
      if ( TableColumnInfo == -1507 )
      {
        v13 = *v10;
        v26 = *((_DWORD *)v10 + 3);
        v29 = 0;
        v25 = 28;
        v27 = 67698689;
        v28 = 1252;
        v12 = JetAddColumn(a1, DbcfgTbl, v13, &v25, 0, 0, &dword_1800F9038[4 * v9]);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            (unsigned int)&WPP_4c45059f8aca3467116f61052473c3dc_Traceguids,
            (unsigned int)*v10,
            *((_DWORD *)v10 + 2));
        }
      }
      else if ( !TableColumnInfo )
      {
        *((_DWORD *)v10 + 2) = DWORD1(v22);
      }
      v14 = DhcpMapJetError(v12, "C:GetTableColumnInfo");
      if ( v14 )
        break;
      ++v9;
      v10 += 2;
      if ( v9 >= 0x19 )
        goto LABEL_25;
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_4c45059f8aca3467116f61052473c3dc_Traceguids, v14);
  do
  {
    *v2 = 0;
    v2 += 4;
    --v3;
  }
  while ( v3 );
  DbcfgTbl = 0;
  return v14;
}

```

## disassembly

```asm
0x180016694  mov     [rsp-8+arg_10], rbx
0x180016699  push    rbp
0x18001669a  push    rsi
0x18001669b  push    rdi
0x18001669c  push    r12
0x18001669e  push    r13
0x1800166a0  push    r14
0x1800166a2  push    r15
0x1800166a4  lea     rbp, [rsp-27h]
0x1800166a9  sub     rsp, 90h
0x1800166b0  mov     rax, cs:__security_cookie
0x1800166b7  xor     rax, rsp
0x1800166ba  mov     [rbp+57h+var_40], rax
0x1800166be  xor     eax, eax
0x1800166c0  lea     rsi, dword_1800F9038
0x1800166c7  mov     r15d, 19h
0x1800166cd  mov     [rbp+57h+var_70], rax
0x1800166d1  xorps   xmm0, xmm0
0x1800166d4  mov     [rbp+57h+var_68], eax
0x1800166d7  mov     r12, rcx
0x1800166da  mov     ebx, edx
0x1800166dc  movups  [rbp+57h+var_80], xmm0
0x1800166e0  lea     r14d, [r15-18h]
0x1800166e4  mov     rax, rsi
0x1800166e7  mov     ecx, r15d
0x1800166ea  xor     r13d, r13d
0x1800166ed  mov     [rax], r13d
0x1800166f0  lea     rax, [rax+10h]
0x1800166f4  sub     rcx, r14
0x1800166f7  jnz     short loc_1800166ED
0x1800166f9  lea     rdi, DbcfgTbl
0x180016700  mov     cs:DbcfgTbl, r13
0x180016707  mov     [rsp+0C0h+var_90], rdi
0x18001670c  lea     r8, aDbcfgtable; "DbcfgTable"
0x180016713  mov     dword ptr [rsp+0C0h+var_98], r13d
0x180016718  xor     r9d, r9d
0x18001671b  mov     rcx, r12
0x18001671e  mov     dword ptr [rsp+0C0h+var_A0], r13d
0x180016723  call    cs:__imp_JetOpenTable
0x18001672a  nop     dword ptr [rax+rax+00h]
0x18001672f  test    eax, eax
0x180016731  jnz     loc_180016848
0x180016737  mov     r14d, r13d
0x18001673a  lea     rbx, DbcfgTable
0x180016741  xor     eax, eax
0x180016743  mov     r8, [rbx]
0x180016746  lea     r9, [rbp+57h+var_80]
0x18001674a  mov     rdx, cs:DbcfgTbl
0x180016751  mov     rcx, r12
0x180016754  mov     dword ptr [rsp+0C0h+var_98], eax
0x180016758  mov     dword ptr [rsp+0C0h+var_A0], 1Ch
0x180016760  call    cs:__imp_JetGetTableColumnInfo
0x180016767  nop     dword ptr [rax+rax+00h]
0x18001676c  mov     edi, eax
0x18001676e  cmp     eax, 0FFFFFA1Dh
0x180016773  jnz     loc_18001680F
0x180016779  mov     eax, [rbx+0Ch]
0x18001677c  lea     r9, [rbp+57h+var_60]
0x180016780  mov     r8, [rbx]
0x180016783  xor     ecx, ecx
0x180016785  mov     rdx, cs:DbcfgTbl
0x18001678c  mov     [rbp+57h+var_58], eax
0x18001678f  mov     [rbp+57h+var_48], ecx
0x180016792  mov     eax, r14d
0x180016795  shl     rax, 4
0x180016799  add     rax, rsi
0x18001679c  mov     [rbp+57h+var_60], 1Ch
0x1800167a4  mov     [rsp+0C0h+var_90], rax
0x1800167a9  mov     dword ptr [rsp+0C0h+var_98], ecx
0x1800167ad  mov     [rsp+0C0h+var_A0], rcx
0x1800167b2  mov     rcx, r12
0x1800167b5  mov     [rbp+57h+var_54], 4090001h
0x1800167bc  mov     [rbp+57h+var_50], 4E4h
0x1800167c4  call    cs:__imp_JetAddColumn
0x1800167cb  nop     dword ptr [rax+rax+00h]
0x1800167d0  mov     edi, eax
0x1800167d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800167d9  lea     rax, WPP_GLOBAL_Control
0x1800167e0  cmp     rcx, rax
0x1800167e3  jz      short loc_180016819
0x1800167e5  test    dword ptr [rcx+1Ch], 8000h
0x1800167ec  jz      short loc_180016819
0x1800167ee  mov     eax, [rbx+8]
0x1800167f1  lea     r8, WPP_4c45059f8aca3467116f61052473c3dc_Traceguids
0x1800167f8  mov     r9, [rbx]
0x1800167fb  mov     edx, 11h
0x180016800  mov     rcx, [rcx+10h]
0x180016804  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180016808  call    WPP_SF_sd
0x18001680d  jmp     short loc_180016819
0x18001680f  test    eax, eax
0x180016811  jnz     short loc_180016819
0x180016813  mov     eax, dword ptr [rbp+57h+var_80+4]
0x180016816  mov     [rbx+8], eax
0x180016819  lea     rdx, aCGettablecolum; "C:GetTableColumnInfo"
0x180016820  mov     ecx, edi
0x180016822  call    DhcpMapJetError
0x180016827  mov     edi, eax
0x180016829  xor     eax, eax
0x18001682b  test    edi, edi
0x18001682d  jnz     loc_1800169F7
0x180016833  inc     r14d
0x180016836  add     rbx, 10h
0x18001683a  cmp     r14d, r15d
0x18001683d  jb      loc_180016743
0x180016843  jmp     loc_1800169C4
0x180016848  cmp     eax, 0FFFFFAE7h
0x18001684d  jz      short loc_18001686C
0x18001684f  lea     rdx, aCOpentable; "C:OpenTable"
0x180016856  mov     ecx, eax
0x180016858  call    DhcpMapJetError
0x18001685d  mov     edi, eax
0x18001685f  test    eax, eax
0x180016861  jnz     loc_1800169FD
0x180016867  jmp     loc_1800169C4
0x18001686c  mov     [rsp+0C0h+var_98], rdi
0x180016871  lea     r8, aDbcfgtable; "DbcfgTable"
0x180016878  mov     r9d, 0Ah
0x18001687e  mov     dword ptr [rsp+0C0h+var_A0], 50h ; 'P'
0x180016886  mov     edx, ebx
0x180016888  mov     rcx, r12
0x18001688b  call    cs:__imp_JetCreateTable
0x180016892  nop     dword ptr [rax+rax+00h]
0x180016897  mov     ecx, eax
0x180016899  lea     rdx, aCCreatetable; "C:CreateTAble"
0x1800168a0  call    DhcpMapJetError
0x1800168a5  mov     edi, eax
0x1800168a7  test    eax, eax
0x1800168a9  jnz     loc_1800169FD
0x1800168af  mov     qword ptr [rbp+57h+var_80], 1Ch
0x1800168b7  lea     rbx, DbcfgTable
0x1800168be  mov     dword ptr [rbp+57h+var_80+0Ch], 4090001h
0x1800168c5  mov     r14d, r13d
0x1800168c8  mov     [rbp+57h+var_70], 4E4h
0x1800168d0  mov     [rbp+57h+var_68], r13d
0x1800168d4  mov     eax, [rbx+0Ch]
0x1800168d7  lea     r9, [rbp+57h+var_80]
0x1800168db  mov     r8, [rbx]
0x1800168de  mov     rcx, r12
0x1800168e1  mov     rdx, cs:DbcfgTbl
0x1800168e8  mov     dword ptr [rbp+57h+var_80+8], eax
0x1800168eb  mov     eax, r14d
0x1800168ee  shl     rax, 4
0x1800168f2  add     rax, rsi
0x1800168f5  mov     [rsp+0C0h+var_90], rax
0x1800168fa  mov     dword ptr [rsp+0C0h+var_98], r13d
0x1800168ff  mov     [rsp+0C0h+var_A0], r13
0x180016904  call    cs:__imp_JetAddColumn
0x18001690b  nop     dword ptr [rax+rax+00h]
0x180016910  mov     ecx, eax
0x180016912  lea     rdx, aCAddcolumn; "C:AddColumn"
0x180016919  call    DhcpMapJetError
0x18001691e  mov     edi, eax
0x180016920  test    eax, eax
0x180016922  jnz     loc_1800169F7
0x180016928  mov     rcx, cs:WPP_GLOBAL_Control
0x18001692f  lea     rax, WPP_GLOBAL_Control
0x180016936  cmp     rcx, rax
0x180016939  jz      short loc_180016961
0x18001693b  test    dword ptr [rcx+1Ch], 8000h
0x180016942  jz      short loc_180016961
0x180016944  mov     eax, [rbx+8]
0x180016947  lea     edx, [rdi+12h]
0x18001694a  mov     r9, [rbx]
0x18001694d  lea     r8, WPP_4c45059f8aca3467116f61052473c3dc_Traceguids
0x180016954  mov     rcx, [rcx+10h]
0x180016958  mov     dword ptr [rsp+0C0h+var_A0], eax
0x18001695c  call    WPP_SF_sd
0x180016961  inc     r14d
0x180016964  add     rbx, 10h
0x180016968  cmp     r14d, r15d
0x18001696b  jb      loc_1800168D4
0x180016971  mov     rdx, cs:DbcfgTbl
0x180016978  lea     rax, aDbcfgindex_0; "+DbcfgIndex"
0x18001697f  mov     dword ptr [rsp+0C0h+var_90], 32h ; '2'
0x180016987  lea     r8, aDbcfgindex; "DbcfgIndex"
0x18001698e  mov     dword ptr [rsp+0C0h+var_98], 0Dh
0x180016996  mov     r9d, 3
0x18001699c  mov     rcx, r12
0x18001699f  mov     [rsp+0C0h+var_A0], rax
0x1800169a4  call    cs:__imp_JetCreateIndex
0x1800169ab  nop     dword ptr [rax+rax+00h]
0x1800169b0  mov     ecx, eax
0x1800169b2  lea     rdx, aCCreateindex; "C:CreateIndex"
0x1800169b9  call    DhcpMapJetError
0x1800169be  mov     edi, eax
0x1800169c0  test    eax, eax
0x1800169c2  jnz     short loc_1800169F7
0x1800169c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800169cb  lea     rax, WPP_GLOBAL_Control
0x1800169d2  cmp     rcx, rax
0x1800169d5  jz      short loc_180016A44
0x1800169d7  test    dword ptr [rcx+1Ch], 800h
0x1800169de  jz      short loc_180016A44
0x1800169e0  mov     rcx, [rcx+10h]
0x1800169e4  lea     r8, WPP_4c45059f8aca3467116f61052473c3dc_Traceguids
0x1800169eb  mov     edx, 14h
0x1800169f0  call    WPP_SF_
0x1800169f5  jmp     short loc_180016A44
0x1800169f7  mov     r14d, 1
0x1800169fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a04  lea     rax, WPP_GLOBAL_Control
0x180016a0b  cmp     rcx, rax
0x180016a0e  jz      short loc_180016A31
0x180016a10  test    dword ptr [rcx+1Ch], 800h
0x180016a17  jz      short loc_180016A31
0x180016a19  mov     rcx, [rcx+10h]
0x180016a1d  lea     r8, WPP_4c45059f8aca3467116f61052473c3dc_Traceguids
0x180016a24  mov     edx, 13h
0x180016a29  mov     r9d, edi
0x180016a2c  call    WPP_SF_D
0x180016a31  mov     [rsi], r13d
0x180016a34  lea     rsi, [rsi+10h]
0x180016a38  sub     r15, r14
0x180016a3b  jnz     short loc_180016A31
0x180016a3d  mov     cs:DbcfgTbl, r13
0x180016a44  mov     eax, edi
0x180016a46  mov     rcx, [rbp+57h+var_40]
0x180016a4a  xor     rcx, rsp; StackCookie
0x180016a4d  call    __security_check_cookie
0x180016a52  mov     rbx, [rsp+0C0h+arg_10]
0x180016a5a  add     rsp, 90h
0x180016a61  pop     r15
0x180016a63  pop     r14
0x180016a65  pop     r13
0x180016a67  pop     r12
0x180016a69  pop     rdi
0x180016a6a  pop     rsi
0x180016a6b  pop     rbp
0x180016a6c  retn
```
