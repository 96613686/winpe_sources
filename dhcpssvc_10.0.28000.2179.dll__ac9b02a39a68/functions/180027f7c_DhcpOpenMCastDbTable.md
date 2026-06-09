# DhcpOpenMCastDbTable

- ea: `0x180027f7c`
- end: `0x18002837f`
- name: `DhcpOpenMCastDbTable`
- size: `1027`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18000ca98`
- `0x18000d644`

## callees

- `0x18000282c`
- `0x180003228`
- `0x18000e814`
- `0x180010e3c`
- `0x180027f7c`
- `0x1800cdac0`

## import_xrefs

- `ESENT!JetGetTableColumnInfo` at `0x18002806d`
- `ESENT!JetGetTableColumnInfo` at `0x18002806d`
- `ESENT!JetOpenTable` at `0x180027ff2`
- `ESENT!JetOpenTable` at `0x180027ff2`
- `ESENT!JetCreateIndex` at `0x180028283`
- `ESENT!JetCreateIndex` at `0x1800282d3`
- `ESENT!JetCreateIndex` at `0x180028283`
- `ESENT!JetCreateIndex` at `0x1800282d3`
- `ESENT!JetCreateTable` at `0x180028127`
- `ESENT!JetCreateTable` at `0x180028127`
- `ESENT!JetAddColumn` at `0x1800281db`
- `ESENT!JetAddColumn` at `0x1800281db`

## string_xrefs

- `0x1800280fa`: `M:OpenTable`
- `0x180028161`: `M:CreateTAble`
- `0x180028291`: `M:CreateIndex`
- `0x1800282e1`: `M:CreateIndex`

## pseudocode

```c
__int64 __fastcall DhcpOpenMCastDbTable(__int64 a1)
{
  JET_DBID v1; // edi
  unsigned int v3; // ebx
  unsigned int v4; // esi
  __int64 v5; // rdi
  unsigned int TableColumnInfo; // eax
  unsigned int v7; // ebx
  __int64 v8; // r9
  _QWORD *v9; // rcx
  const char *v10; // rdx
  __int64 v11; // rcx
  unsigned int Table; // ebx
  unsigned int v13; // esi
  __int64 v14; // rdi
  unsigned int v15; // eax
  unsigned int Index; // eax
  __int128 v18; // [rsp+40h] [rbp-30h] BYREF
  __int64 v19; // [rsp+50h] [rbp-20h]
  int v20; // [rsp+58h] [rbp-18h]

  v1 = DhcpGlobalDatabaseHandle;
  v19 = 0;
  v20 = 0;
  MadcapGlobalClientTable = (__int64)&MCastClientTable;
  v18 = 0;
  v3 = JetOpenTable(a1, DhcpGlobalDatabaseHandle, "MCastClientTableVer3", 0, 0, 0, &MadcapGlobalClientTableHandle);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_98c938fc0f4f3ca9547042810852d8b7_Traceguids);
  if ( !v3 )
  {
    v4 = 0;
    v5 = 0;
    while ( 1 )
    {
      TableColumnInfo = JetGetTableColumnInfo(
                          a1,
                          MadcapGlobalClientTableHandle,
                          *(_QWORD *)(v5 + MadcapGlobalClientTable),
                          &v18,
                          28,
                          0);
      v7 = DhcpMapJetError(TableColumnInfo, "M:GetTableColumnInfo");
      if ( v7 )
        goto LABEL_31;
      v8 = MadcapGlobalClientTable;
      *(_DWORD *)(v5 + MadcapGlobalClientTable + 8) = DWORD1(v18);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v7 + 11,
          (unsigned int)&WPP_98c938fc0f4f3ca9547042810852d8b7_Traceguids,
          *(_QWORD *)(v5 + v8),
          SBYTE4(v18));
        v9 = WPP_GLOBAL_Control;
      }
      ++v4;
      v5 += 16;
      if ( v4 >= 0xA )
        goto LABEL_28;
    }
  }
  if ( v3 == -1305 )
  {
    Table = JetCreateTable(a1, v1, "MCastClientTableVer3", 10, 80, &MadcapGlobalClientTableHandle);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_98c938fc0f4f3ca9547042810852d8b7_Traceguids, Table);
    v7 = DhcpMapJetError(Table, "M:CreateTAble");
    if ( !v7 )
    {
      *(_QWORD *)&v18 = 28;
      HIDWORD(v18) = 67698689;
      v13 = 0;
      v19 = 1252;
      v14 = 0;
      v20 = 0;
      while ( 1 )
      {
        DWORD2(v18) = *(_DWORD *)(v14 + MadcapGlobalClientTable + 12);
        v15 = JetAddColumn(
                a1,
                MadcapGlobalClientTableHandle,
                *(_QWORD *)(v14 + MadcapGlobalClientTable),
                &v18,
                0,
                0,
                MadcapGlobalClientTable + 16LL * v13 + 8);
        v7 = DhcpMapJetError(v15, "M:AddColumn");
        if ( v7 )
          break;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            (unsigned int)&WPP_98c938fc0f4f3ca9547042810852d8b7_Traceguids,
            *(_QWORD *)(v14 + MadcapGlobalClientTable),
            *(_DWORD *)(v14 + MadcapGlobalClientTable + 8));
        }
        ++v13;
        v14 += 16;
        if ( v13 >= 0xA )
        {
          Index = JetCreateIndex(
                    a1,
                    MadcapGlobalClientTableHandle,
                    *(_QWORD *)MadcapGlobalClientTable,
                    2,
                    "+MCastIpAddr",
                    14,
                    50);
          v7 = DhcpMapJetError(Index, "M:CreateIndex");
          if ( v7 )
            goto LABEL_31;
          v11 = (unsigned int)JetCreateIndex(
                                a1,
                                MadcapGlobalClientTableHandle,
                                *(_QWORD *)(MadcapGlobalClientTable + 16),
                                1,
                                "+MCastClientID",
                                16,
                                50);
          v10 = "M:CreateIndex";
          goto LABEL_26;
        }
      }
    }
    goto LABEL_31;
  }
  v10 = "M:OpenTable";
  v11 = v3;
LABEL_26:
  v7 = DhcpMapJetError(v11, v10);
  if ( v7 )
  {
LABEL_31:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_98c938fc0f4f3ca9547042810852d8b7_Traceguids, v7);
    return v7;
  }
  v9 = WPP_GLOBAL_Control;
LABEL_28:
  if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x800) != 0 )
    WPP_SF_(v9[2], 15, &WPP_98c938fc0f4f3ca9547042810852d8b7_Traceguids);
  return v7;
}

```

## disassembly

```asm
0x180027f7c  mov     r11, rsp
0x180027f7f  mov     [r11+10h], rbx
0x180027f83  mov     [r11+18h], rsi
0x180027f87  mov     [r11+20h], rdi
0x180027f8b  push    rbp
0x180027f8c  push    r12
0x180027f8e  push    r13
0x180027f90  push    r14
0x180027f92  push    r15
0x180027f94  mov     rbp, rsp
0x180027f97  sub     rsp, 70h
0x180027f9b  mov     rax, cs:__security_cookie
0x180027fa2  xor     rax, rsp
0x180027fa5  mov     [rbp+var_10], rax
0x180027fa9  mov     edi, cs:DhcpGlobalDatabaseHandle
0x180027faf  lea     r14, MadcapGlobalClientTableHandle
0x180027fb6  xor     eax, eax
0x180027fb8  mov     [r11-68h], r14
0x180027fbc  xor     r12d, r12d
0x180027fbf  mov     [rbp+var_20], rax
0x180027fc3  mov     [rbp+var_18], eax
0x180027fc6  lea     r8, aMcastclienttab; "MCastClientTableVer3"
0x180027fcd  lea     rax, MCastClientTable
0x180027fd4  mov     [r11-70h], r12d
0x180027fd8  xorps   xmm0, xmm0
0x180027fdb  mov     cs:MadcapGlobalClientTable, rax
0x180027fe2  xor     r9d, r9d
0x180027fe5  mov     [r11-78h], r12d
0x180027fe9  mov     edx, edi
0x180027feb  mov     r15, rcx
0x180027fee  movups  [rbp+var_30], xmm0
0x180027ff2  call    cs:__imp_JetOpenTable
0x180027ff9  nop     dword ptr [rax+rax+00h]
0x180027ffe  mov     ebx, eax
0x180028000  mov     rcx, cs:WPP_GLOBAL_Control
0x180028007  lea     rax, WPP_GLOBAL_Control
0x18002800e  lea     r13, WPP_98c938fc0f4f3ca9547042810852d8b7_Traceguids
0x180028015  mov     esi, 8000h
0x18002801a  cmp     rcx, rax
0x18002801d  jz      short loc_180028035
0x18002801f  test    [rcx+1Ch], esi
0x180028022  jz      short loc_180028035
0x180028024  mov     rcx, [rcx+10h]
0x180028028  lea     edx, [r12+0Ah]
0x18002802d  mov     r8, r13
0x180028030  call    WPP_SF_
0x180028035  test    ebx, ebx
0x180028037  jnz     loc_1800280F2
0x18002803d  mov     esi, r12d
0x180028040  lea     r14d, [rbx+1]
0x180028044  mov     rdi, r12
0x180028047  mov     r8, cs:MadcapGlobalClientTable
0x18002804e  lea     r9, [rbp+var_30]
0x180028052  mov     rdx, cs:MadcapGlobalClientTableHandle
0x180028059  mov     rcx, r15
0x18002805c  mov     dword ptr [rsp+70h+var_48], r12d
0x180028061  mov     dword ptr [rsp+70h+var_50], 1Ch
0x180028069  mov     r8, [rdi+r8]
0x18002806d  call    cs:__imp_JetGetTableColumnInfo
0x180028074  nop     dword ptr [rax+rax+00h]
0x180028079  mov     ecx, eax
0x18002807b  lea     rdx, aMGettablecolum; "M:GetTableColumnInfo"
0x180028082  call    DhcpMapJetError
0x180028087  mov     ebx, eax
0x180028089  test    eax, eax
0x18002808b  jnz     loc_180028322
0x180028091  mov     r9, cs:MadcapGlobalClientTable
0x180028098  mov     ecx, dword ptr [rbp+var_30+4]
0x18002809b  mov     [rdi+r9+8], ecx
0x1800280a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800280a7  lea     rax, WPP_GLOBAL_Control
0x1800280ae  cmp     rcx, rax
0x1800280b1  jz      short loc_1800280DD
0x1800280b3  test    dword ptr [rcx+1Ch], 8000h
0x1800280ba  jz      short loc_1800280DD
0x1800280bc  mov     eax, dword ptr [rbp+var_30+4]
0x1800280bf  lea     edx, [rbx+0Bh]
0x1800280c2  mov     r9, [rdi+r9]
0x1800280c6  mov     r8, r13
0x1800280c9  mov     rcx, [rcx+10h]
0x1800280cd  mov     dword ptr [rsp+70h+var_50], eax
0x1800280d1  call    WPP_SF_sd
0x1800280d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800280dd  add     esi, r14d
0x1800280e0  add     rdi, 10h
0x1800280e4  cmp     esi, 0Ah
0x1800280e7  jb      loc_180028047
0x1800280ed  jmp     loc_1800282FA
0x1800280f2  cmp     ebx, 0FFFFFAE7h
0x1800280f8  jz      short loc_180028108
0x1800280fa  lea     rdx, aMOpentable; "M:OpenTable"
0x180028101  mov     ecx, ebx
0x180028103  jmp     loc_1800282E8
0x180028108  mov     [rsp+70h+var_48], r14
0x18002810d  lea     r8, aMcastclienttab; "MCastClientTableVer3"
0x180028114  mov     r9d, 0Ah
0x18002811a  mov     dword ptr [rsp+70h+var_50], 50h ; 'P'
0x180028122  mov     edx, edi
0x180028124  mov     rcx, r15
0x180028127  call    cs:__imp_JetCreateTable
0x18002812e  nop     dword ptr [rax+rax+00h]
0x180028133  mov     ebx, eax
0x180028135  mov     rcx, cs:WPP_GLOBAL_Control
0x18002813c  lea     rax, WPP_GLOBAL_Control
0x180028143  cmp     rcx, rax
0x180028146  jz      short loc_180028161
0x180028148  test    [rcx+1Ch], esi
0x18002814b  jz      short loc_180028161
0x18002814d  mov     rcx, [rcx+10h]
0x180028151  mov     edx, 0Ch
0x180028156  mov     r9d, ebx
0x180028159  mov     r8, r13
0x18002815c  call    WPP_SF_D
0x180028161  lea     rdx, aMCreatetable; "M:CreateTAble"
0x180028168  mov     ecx, ebx
0x18002816a  call    DhcpMapJetError
0x18002816f  mov     ebx, eax
0x180028171  test    eax, eax
0x180028173  jnz     loc_180028322
0x180028179  mov     qword ptr [rbp+var_30], 1Ch
0x180028181  lea     r14d, [rax+1]
0x180028185  mov     dword ptr [rbp+var_30+0Ch], 4090001h
0x18002818c  mov     esi, r12d
0x18002818f  mov     [rbp+var_20], 4E4h
0x180028197  mov     rdi, r12
0x18002819a  mov     [rbp+var_18], r12d
0x18002819e  mov     r8, cs:MadcapGlobalClientTable
0x1800281a5  lea     r9, [rbp+var_30]
0x1800281a9  mov     rdx, cs:MadcapGlobalClientTableHandle
0x1800281b0  mov     rcx, r15
0x1800281b3  mov     eax, [rdi+r8+0Ch]
0x1800281b8  mov     dword ptr [rbp+var_30+8], eax
0x1800281bb  mov     eax, esi
0x1800281bd  shl     rax, 4
0x1800281c1  add     rax, 8
0x1800281c5  add     rax, r8
0x1800281c8  mov     r8, [rdi+r8]
0x1800281cc  mov     [rsp+70h+var_40], rax
0x1800281d1  mov     dword ptr [rsp+70h+var_48], r12d
0x1800281d6  mov     [rsp+70h+var_50], r12
0x1800281db  call    cs:__imp_JetAddColumn
0x1800281e2  nop     dword ptr [rax+rax+00h]
0x1800281e7  mov     ecx, eax
0x1800281e9  lea     rdx, aMAddcolumn; "M:AddColumn"
0x1800281f0  call    DhcpMapJetError
0x1800281f5  mov     ebx, eax
0x1800281f7  test    eax, eax
0x1800281f9  jnz     loc_180028322
0x1800281ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180028206  lea     rax, WPP_GLOBAL_Control
0x18002820d  cmp     rcx, rax
0x180028210  jz      short loc_18002823E
0x180028212  test    dword ptr [rcx+1Ch], 8000h
0x180028219  jz      short loc_18002823E
0x18002821b  mov     r9, cs:MadcapGlobalClientTable
0x180028222  lea     edx, [rbx+0Dh]
0x180028225  mov     rcx, [rcx+10h]
0x180028229  mov     r8, r13
0x18002822c  mov     eax, [rdi+r9+8]
0x180028231  mov     r9, [rdi+r9]
0x180028235  mov     dword ptr [rsp+70h+var_50], eax
0x180028239  call    WPP_SF_sd
0x18002823e  add     esi, r14d
0x180028241  add     rdi, 10h
0x180028245  cmp     esi, 0Ah
0x180028248  jb      loc_18002819E
0x18002824e  mov     r8, cs:MadcapGlobalClientTable
0x180028255  lea     rax, aMcastipaddr; "+MCastIpAddr"
0x18002825c  mov     rdx, cs:MadcapGlobalClientTableHandle
0x180028263  mov     edi, 32h ; '2'
0x180028268  mov     dword ptr [rsp+70h+var_40], edi
0x18002826c  mov     rcx, r15
0x18002826f  mov     dword ptr [rsp+70h+var_48], 0Eh
0x180028277  mov     r8, [r8]
0x18002827a  lea     r9d, [rdi-30h]
0x18002827e  mov     [rsp+70h+var_50], rax
0x180028283  call    cs:__imp_JetCreateIndex
0x18002828a  nop     dword ptr [rax+rax+00h]
0x18002828f  mov     ecx, eax
0x180028291  lea     rdx, aMCreateindex; "M:CreateIndex"
0x180028298  call    DhcpMapJetError
0x18002829d  mov     ebx, eax
0x18002829f  test    eax, eax
0x1800282a1  jnz     short loc_180028322
0x1800282a3  mov     r8, cs:MadcapGlobalClientTable
0x1800282aa  lea     rax, aMcastclientid_0; "+MCastClientID"
0x1800282b1  mov     rdx, cs:MadcapGlobalClientTableHandle
0x1800282b8  mov     r9d, r14d
0x1800282bb  mov     dword ptr [rsp+70h+var_40], edi
0x1800282bf  mov     rcx, r15
0x1800282c2  mov     dword ptr [rsp+70h+var_48], 10h
0x1800282ca  mov     r8, [r8+10h]
0x1800282ce  mov     [rsp+70h+var_50], rax
0x1800282d3  call    cs:__imp_JetCreateIndex
0x1800282da  nop     dword ptr [rax+rax+00h]
0x1800282df  mov     ecx, eax
0x1800282e1  lea     rdx, aMCreateindex; "M:CreateIndex"
0x1800282e8  call    DhcpMapJetError
0x1800282ed  mov     ebx, eax
0x1800282ef  test    eax, eax
0x1800282f1  jnz     short loc_180028322
0x1800282f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800282fa  lea     rax, WPP_GLOBAL_Control
0x180028301  cmp     rcx, rax
0x180028304  jz      short loc_180028352
0x180028306  test    dword ptr [rcx+1Ch], 800h
0x18002830d  jz      short loc_180028352
0x18002830f  mov     rcx, [rcx+10h]
0x180028313  mov     edx, 0Fh
0x180028318  mov     r8, r13
0x18002831b  call    WPP_SF_
0x180028320  jmp     short loc_180028352
0x180028322  mov     rcx, cs:WPP_GLOBAL_Control
0x180028329  lea     rax, WPP_GLOBAL_Control
0x180028330  cmp     rcx, rax
0x180028333  jz      short loc_180028352
0x180028335  test    dword ptr [rcx+1Ch], 800h
0x18002833c  jz      short loc_180028352
0x18002833e  mov     rcx, [rcx+10h]
0x180028342  mov     edx, 0Eh
0x180028347  mov     r9d, ebx
0x18002834a  mov     r8, r13
0x18002834d  call    WPP_SF_D
0x180028352  mov     eax, ebx
0x180028354  mov     rcx, [rbp+var_10]
0x180028358  xor     rcx, rsp; StackCookie
0x18002835b  call    __security_check_cookie
0x180028360  lea     r11, [rsp+70h+var_s0]
0x180028365  mov     rbx, [r11+38h]
0x180028369  mov     rsi, [r11+40h]
0x18002836d  mov     rdi, [r11+48h]
0x180028371  mov     rsp, r11
0x180028374  pop     r15
0x180028376  pop     r14
0x180028378  pop     r13
0x18002837a  pop     r12
0x18002837c  pop     rbp
0x18002837d  retn
```
