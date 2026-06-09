# DhcpOpenConfigTable

- ea: `0x1800170e4`
- end: `0x1800174b9`
- name: `DhcpOpenConfigTable`
- size: `981`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000df98`
- `0x18000f3d0`
- `0x1800174c0`

## callees

- `0x180002854`
- `0x18000323c`
- `0x18000f144`
- `0x180011724`
- `0x1800170e4`
- `0x1800cc9e0`

## import_xrefs

- `ESENT!JetOpenTable` at `0x180017173`
- `ESENT!JetOpenTable` at `0x180017173`
- `ESENT!JetGetTableColumnInfo` at `0x1800171b0`
- `ESENT!JetGetTableColumnInfo` at `0x1800171b0`
- `ESENT!JetCreateIndex` at `0x1800173f0`
- `ESENT!JetCreateIndex` at `0x1800173f0`
- `ESENT!JetCreateTable` at `0x1800172d9`
- `ESENT!JetCreateTable` at `0x1800172d9`
- `ESENT!JetAddColumn` at `0x180017213`
- `ESENT!JetAddColumn` at `0x180017351`
- `ESENT!JetAddColumn` at `0x180017213`
- `ESENT!JetAddColumn` at `0x180017351`

## string_xrefs

- `0x18001729d`: `C:OpenTable`
- `0x1800172e7`: `C:CreateTAble`
- `0x1800173fe`: `C:CreateIndex`

## pseudocode

```c
__int64 __fastcall DhcpOpenConfigTable(__int64 a1, __int64 a2)
{
  _DWORD *v2; // r14
  __int64 v3; // r15
  unsigned int v5; // ebx
  _DWORD *v6; // rax
  __int64 v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // esi
  char **v10; // rbx
  unsigned int TableColumnInfo; // eax
  unsigned int v12; // edi
  char *v13; // r8
  unsigned int v14; // edi
  unsigned int Table; // eax
  char **v16; // rbx
  unsigned int v17; // esi
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

  v2 = &unk_1800F7038;
  v3 = 25;
  v23 = 0;
  v24 = 0;
  v5 = a2;
  v22 = 0;
  v6 = &unk_1800F7038;
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
          v19 = JetAddColumn(a1, DbcfgTbl, v18, &v22, 0, 0, (char *)&unk_1800F7038 + 16 * v17);
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
        v12 = JetAddColumn(a1, DbcfgTbl, v13, &v25, 0, 0, (char *)&unk_1800F7038 + 16 * v9);
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
0x1800170e4  mov     [rsp-8+arg_10], rbx
0x1800170e9  push    rbp
0x1800170ea  push    rsi
0x1800170eb  push    rdi
0x1800170ec  push    r12
0x1800170ee  push    r13
0x1800170f0  push    r14
0x1800170f2  push    r15
0x1800170f4  lea     rbp, [rsp-27h]
0x1800170f9  sub     rsp, 90h
0x180017100  mov     rax, cs:__security_cookie
0x180017107  xor     rax, rsp
0x18001710a  mov     [rbp+57h+var_40], rax
0x18001710e  xor     eax, eax
0x180017110  lea     r14, unk_1800F7038
0x180017117  mov     r15d, 19h
0x18001711d  mov     [rbp+57h+var_70], rax
0x180017121  xorps   xmm0, xmm0
0x180017124  mov     [rbp+57h+var_68], eax
0x180017127  mov     r12, rcx
0x18001712a  mov     ebx, edx
0x18001712c  movups  [rbp+57h+var_80], xmm0
0x180017130  lea     esi, [r15-18h]
0x180017134  mov     rax, r14
0x180017137  mov     ecx, r15d
0x18001713a  xor     r13d, r13d
0x18001713d  mov     [rax], r13d
0x180017140  lea     rax, [rax+10h]
0x180017144  sub     rcx, rsi
0x180017147  jnz     short loc_18001713D
0x180017149  lea     rdi, DbcfgTbl
0x180017150  mov     cs:DbcfgTbl, r13
0x180017157  mov     [rsp+0C0h+var_90], rdi
0x18001715c  lea     r8, aDbcfgtable; "DbcfgTable"
0x180017163  mov     dword ptr [rsp+0C0h+var_98], r13d
0x180017168  xor     r9d, r9d
0x18001716b  mov     rcx, r12
0x18001716e  mov     dword ptr [rsp+0C0h+var_A0], r13d
0x180017173  call    cs:__imp_JetOpenTable
0x18001717a  nop     dword ptr [rax+rax+00h]
0x18001717f  test    eax, eax
0x180017181  jnz     loc_180017296
0x180017187  mov     esi, r13d
0x18001718a  lea     rbx, DbcfgTable
0x180017191  xor     eax, eax
0x180017193  mov     r8, [rbx]
0x180017196  lea     r9, [rbp+57h+var_80]
0x18001719a  mov     rdx, cs:DbcfgTbl
0x1800171a1  mov     rcx, r12
0x1800171a4  mov     dword ptr [rsp+0C0h+var_98], eax
0x1800171a8  mov     dword ptr [rsp+0C0h+var_A0], 1Ch
0x1800171b0  call    cs:__imp_JetGetTableColumnInfo
0x1800171b7  nop     dword ptr [rax+rax+00h]
0x1800171bc  mov     edi, eax
0x1800171be  cmp     eax, 0FFFFFA1Dh
0x1800171c3  jnz     loc_18001725E
0x1800171c9  mov     eax, [rbx+0Ch]
0x1800171cc  lea     r9, [rbp+57h+var_60]
0x1800171d0  mov     r8, [rbx]
0x1800171d3  xor     ecx, ecx
0x1800171d5  mov     rdx, cs:DbcfgTbl
0x1800171dc  mov     [rbp+57h+var_58], eax
0x1800171df  mov     [rbp+57h+var_48], ecx
0x1800171e2  mov     eax, esi
0x1800171e4  shl     rax, 4
0x1800171e8  add     rax, r14
0x1800171eb  mov     [rbp+57h+var_60], 1Ch
0x1800171f3  mov     [rsp+0C0h+var_90], rax
0x1800171f8  mov     dword ptr [rsp+0C0h+var_98], ecx
0x1800171fc  mov     [rsp+0C0h+var_A0], rcx
0x180017201  mov     rcx, r12
0x180017204  mov     [rbp+57h+var_54], 4090001h
0x18001720b  mov     [rbp+57h+var_50], 4E4h
0x180017213  call    cs:__imp_JetAddColumn
0x18001721a  nop     dword ptr [rax+rax+00h]
0x18001721f  mov     edi, eax
0x180017221  mov     rcx, cs:WPP_GLOBAL_Control
0x180017228  lea     rax, WPP_GLOBAL_Control
0x18001722f  cmp     rcx, rax
0x180017232  jz      short loc_180017268
0x180017234  test    dword ptr [rcx+1Ch], 8000h
0x18001723b  jz      short loc_180017268
0x18001723d  mov     eax, [rbx+8]
0x180017240  lea     r8, WPP_4c45059f8aca3467116f61052473c3dc_Traceguids
0x180017247  mov     r9, [rbx]
0x18001724a  mov     edx, 11h
0x18001724f  mov     rcx, [rcx+10h]
0x180017253  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180017257  call    WPP_SF_sd
0x18001725c  jmp     short loc_180017268
0x18001725e  test    eax, eax
0x180017260  jnz     short loc_180017268
0x180017262  mov     eax, dword ptr [rbp+57h+var_80+4]
0x180017265  mov     [rbx+8], eax
0x180017268  lea     rdx, aCGettablecolum; "C:GetTableColumnInfo"
0x18001726f  mov     ecx, edi
0x180017271  call    DhcpMapJetError
0x180017276  mov     edi, eax
0x180017278  xor     eax, eax
0x18001727a  test    edi, edi
0x18001727c  jnz     loc_180017443
0x180017282  inc     esi
0x180017284  add     rbx, 10h
0x180017288  cmp     esi, r15d
0x18001728b  jb      loc_180017193
0x180017291  jmp     loc_180017410
0x180017296  cmp     eax, 0FFFFFAE7h
0x18001729b  jz      short loc_1800172BA
0x18001729d  lea     rdx, aCOpentable; "C:OpenTable"
0x1800172a4  mov     ecx, eax
0x1800172a6  call    DhcpMapJetError
0x1800172ab  mov     edi, eax
0x1800172ad  test    eax, eax
0x1800172af  jnz     loc_180017448
0x1800172b5  jmp     loc_180017410
0x1800172ba  mov     [rsp+0C0h+var_98], rdi
0x1800172bf  lea     r8, aDbcfgtable; "DbcfgTable"
0x1800172c6  mov     r9d, 0Ah
0x1800172cc  mov     dword ptr [rsp+0C0h+var_A0], 50h ; 'P'
0x1800172d4  mov     edx, ebx
0x1800172d6  mov     rcx, r12
0x1800172d9  call    cs:__imp_JetCreateTable
0x1800172e0  nop     dword ptr [rax+rax+00h]
0x1800172e5  mov     ecx, eax
0x1800172e7  lea     rdx, aCCreatetable; "C:CreateTAble"
0x1800172ee  call    DhcpMapJetError
0x1800172f3  mov     edi, eax
0x1800172f5  test    eax, eax
0x1800172f7  jnz     loc_180017448
0x1800172fd  mov     qword ptr [rbp+57h+var_80], 1Ch
0x180017305  lea     rbx, DbcfgTable
0x18001730c  mov     dword ptr [rbp+57h+var_80+0Ch], 4090001h
0x180017313  mov     esi, r13d
0x180017316  mov     [rbp+57h+var_70], 4E4h
0x18001731e  mov     [rbp+57h+var_68], r13d
0x180017322  mov     eax, [rbx+0Ch]
0x180017325  lea     r9, [rbp+57h+var_80]
0x180017329  mov     r8, [rbx]
0x18001732c  mov     rcx, r12
0x18001732f  mov     rdx, cs:DbcfgTbl
0x180017336  mov     dword ptr [rbp+57h+var_80+8], eax
0x180017339  mov     eax, esi
0x18001733b  shl     rax, 4
0x18001733f  add     rax, r14
0x180017342  mov     [rsp+0C0h+var_90], rax
0x180017347  mov     dword ptr [rsp+0C0h+var_98], r13d
0x18001734c  mov     [rsp+0C0h+var_A0], r13
0x180017351  call    cs:__imp_JetAddColumn
0x180017358  nop     dword ptr [rax+rax+00h]
0x18001735d  mov     ecx, eax
0x18001735f  lea     rdx, aCAddcolumn; "C:AddColumn"
0x180017366  call    DhcpMapJetError
0x18001736b  mov     edi, eax
0x18001736d  test    eax, eax
0x18001736f  jnz     loc_180017443
0x180017375  mov     rcx, cs:WPP_GLOBAL_Control
0x18001737c  lea     rax, WPP_GLOBAL_Control
0x180017383  cmp     rcx, rax
0x180017386  jz      short loc_1800173AE
0x180017388  test    dword ptr [rcx+1Ch], 8000h
0x18001738f  jz      short loc_1800173AE
0x180017391  mov     eax, [rbx+8]
0x180017394  lea     edx, [rdi+12h]
0x180017397  mov     r9, [rbx]
0x18001739a  lea     r8, WPP_4c45059f8aca3467116f61052473c3dc_Traceguids
0x1800173a1  mov     rcx, [rcx+10h]
0x1800173a5  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1800173a9  call    WPP_SF_sd
0x1800173ae  inc     esi
0x1800173b0  add     rbx, 10h
0x1800173b4  cmp     esi, r15d
0x1800173b7  jb      loc_180017322
0x1800173bd  mov     rdx, cs:DbcfgTbl
0x1800173c4  lea     rax, aDbcfgindex_0; "+DbcfgIndex"
0x1800173cb  mov     dword ptr [rsp+0C0h+var_90], 32h ; '2'
0x1800173d3  lea     r8, aDbcfgindex; "DbcfgIndex"
0x1800173da  mov     dword ptr [rsp+0C0h+var_98], 0Dh
0x1800173e2  mov     r9d, 3
0x1800173e8  mov     rcx, r12
0x1800173eb  mov     [rsp+0C0h+var_A0], rax
0x1800173f0  call    cs:__imp_JetCreateIndex
0x1800173f7  nop     dword ptr [rax+rax+00h]
0x1800173fc  mov     ecx, eax
0x1800173fe  lea     rdx, aCCreateindex; "C:CreateIndex"
0x180017405  call    DhcpMapJetError
0x18001740a  mov     edi, eax
0x18001740c  test    eax, eax
0x18001740e  jnz     short loc_180017443
0x180017410  mov     rcx, cs:WPP_GLOBAL_Control
0x180017417  lea     rax, WPP_GLOBAL_Control
0x18001741e  cmp     rcx, rax
0x180017421  jz      short loc_18001748F
0x180017423  test    dword ptr [rcx+1Ch], 800h
0x18001742a  jz      short loc_18001748F
0x18001742c  mov     rcx, [rcx+10h]
0x180017430  lea     r8, WPP_4c45059f8aca3467116f61052473c3dc_Traceguids
0x180017437  mov     edx, 14h
0x18001743c  call    WPP_SF_
0x180017441  jmp     short loc_18001748F
0x180017443  mov     esi, 1
0x180017448  mov     rcx, cs:WPP_GLOBAL_Control
0x18001744f  lea     rax, WPP_GLOBAL_Control
0x180017456  cmp     rcx, rax
0x180017459  jz      short loc_18001747C
0x18001745b  test    dword ptr [rcx+1Ch], 800h
0x180017462  jz      short loc_18001747C
0x180017464  mov     rcx, [rcx+10h]
0x180017468  lea     r8, WPP_4c45059f8aca3467116f61052473c3dc_Traceguids
0x18001746f  mov     edx, 13h
0x180017474  mov     r9d, edi
0x180017477  call    WPP_SF_D
0x18001747c  mov     [r14], r13d
0x18001747f  lea     r14, [r14+10h]
0x180017483  sub     r15, rsi
0x180017486  jnz     short loc_18001747C
0x180017488  mov     cs:DbcfgTbl, r13
0x18001748f  mov     eax, edi
0x180017491  mov     rcx, [rbp+57h+var_40]
0x180017495  xor     rcx, rsp; StackCookie
0x180017498  call    __security_check_cookie
0x18001749d  mov     rbx, [rsp+0C0h+arg_10]
0x1800174a5  add     rsp, 90h
0x1800174ac  pop     r15
0x1800174ae  pop     r14
0x1800174b0  pop     r13
0x1800174b2  pop     r12
0x1800174b4  pop     rdi
0x1800174b5  pop     rsi
0x1800174b6  pop     rbp
0x1800174b7  retn
```
