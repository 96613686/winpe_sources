# DhcpOpenMCastDbTable

- ea: `0x1800289e8`
- end: `0x180028deb`
- name: `DhcpOpenMCastDbTable`
- size: `1027`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18000d3ec`
- `0x18000df98`

## callees

- `0x180002854`
- `0x18000323c`
- `0x18000f144`
- `0x180011724`
- `0x1800289e8`
- `0x1800cc9e0`

## import_xrefs

- `ESENT!JetOpenTable` at `0x180028a5e`
- `ESENT!JetOpenTable` at `0x180028a5e`
- `ESENT!JetGetTableColumnInfo` at `0x180028ad9`
- `ESENT!JetGetTableColumnInfo` at `0x180028ad9`
- `ESENT!JetCreateIndex` at `0x180028cef`
- `ESENT!JetCreateIndex` at `0x180028d3f`
- `ESENT!JetCreateIndex` at `0x180028cef`
- `ESENT!JetCreateIndex` at `0x180028d3f`
- `ESENT!JetCreateTable` at `0x180028b93`
- `ESENT!JetCreateTable` at `0x180028b93`
- `ESENT!JetAddColumn` at `0x180028c47`
- `ESENT!JetAddColumn` at `0x180028c47`

## string_xrefs

- `0x180028b66`: `M:OpenTable`
- `0x180028bcd`: `M:CreateTAble`
- `0x180028cfd`: `M:CreateIndex`
- `0x180028d4d`: `M:CreateIndex`

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
0x1800289e8  mov     r11, rsp
0x1800289eb  mov     [r11+10h], rbx
0x1800289ef  mov     [r11+18h], rsi
0x1800289f3  mov     [r11+20h], rdi
0x1800289f7  push    rbp
0x1800289f8  push    r12
0x1800289fa  push    r13
0x1800289fc  push    r14
0x1800289fe  push    r15
0x180028a00  mov     rbp, rsp
0x180028a03  sub     rsp, 70h
0x180028a07  mov     rax, cs:__security_cookie
0x180028a0e  xor     rax, rsp
0x180028a11  mov     [rbp+var_10], rax
0x180028a15  mov     edi, cs:DhcpGlobalDatabaseHandle
0x180028a1b  lea     r14, MadcapGlobalClientTableHandle
0x180028a22  xor     eax, eax
0x180028a24  mov     [r11-68h], r14
0x180028a28  xor     r12d, r12d
0x180028a2b  mov     [rbp+var_20], rax
0x180028a2f  mov     [rbp+var_18], eax
0x180028a32  lea     r8, aMcastclienttab; "MCastClientTableVer3"
0x180028a39  lea     rax, MCastClientTable
0x180028a40  mov     [r11-70h], r12d
0x180028a44  xorps   xmm0, xmm0
0x180028a47  mov     cs:MadcapGlobalClientTable, rax
0x180028a4e  xor     r9d, r9d
0x180028a51  mov     [r11-78h], r12d
0x180028a55  mov     edx, edi
0x180028a57  mov     r15, rcx
0x180028a5a  movups  [rbp+var_30], xmm0
0x180028a5e  call    cs:__imp_JetOpenTable
0x180028a65  nop     dword ptr [rax+rax+00h]
0x180028a6a  mov     ebx, eax
0x180028a6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180028a73  lea     rax, WPP_GLOBAL_Control
0x180028a7a  lea     r13, WPP_98c938fc0f4f3ca9547042810852d8b7_Traceguids
0x180028a81  mov     esi, 8000h
0x180028a86  cmp     rcx, rax
0x180028a89  jz      short loc_180028AA1
0x180028a8b  test    [rcx+1Ch], esi
0x180028a8e  jz      short loc_180028AA1
0x180028a90  mov     rcx, [rcx+10h]
0x180028a94  lea     edx, [r12+0Ah]
0x180028a99  mov     r8, r13
0x180028a9c  call    WPP_SF_
0x180028aa1  test    ebx, ebx
0x180028aa3  jnz     loc_180028B5E
0x180028aa9  mov     esi, r12d
0x180028aac  lea     r14d, [rbx+1]
0x180028ab0  mov     rdi, r12
0x180028ab3  mov     r8, cs:MadcapGlobalClientTable
0x180028aba  lea     r9, [rbp+var_30]
0x180028abe  mov     rdx, cs:MadcapGlobalClientTableHandle
0x180028ac5  mov     rcx, r15
0x180028ac8  mov     dword ptr [rsp+70h+var_48], r12d
0x180028acd  mov     dword ptr [rsp+70h+var_50], 1Ch
0x180028ad5  mov     r8, [rdi+r8]
0x180028ad9  call    cs:__imp_JetGetTableColumnInfo
0x180028ae0  nop     dword ptr [rax+rax+00h]
0x180028ae5  mov     ecx, eax
0x180028ae7  lea     rdx, aMGettablecolum; "M:GetTableColumnInfo"
0x180028aee  call    DhcpMapJetError
0x180028af3  mov     ebx, eax
0x180028af5  test    eax, eax
0x180028af7  jnz     loc_180028D8E
0x180028afd  mov     r9, cs:MadcapGlobalClientTable
0x180028b04  mov     ecx, dword ptr [rbp+var_30+4]
0x180028b07  mov     [rdi+r9+8], ecx
0x180028b0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180028b13  lea     rax, WPP_GLOBAL_Control
0x180028b1a  cmp     rcx, rax
0x180028b1d  jz      short loc_180028B49
0x180028b1f  test    dword ptr [rcx+1Ch], 8000h
0x180028b26  jz      short loc_180028B49
0x180028b28  mov     eax, dword ptr [rbp+var_30+4]
0x180028b2b  lea     edx, [rbx+0Bh]
0x180028b2e  mov     r9, [rdi+r9]
0x180028b32  mov     r8, r13
0x180028b35  mov     rcx, [rcx+10h]
0x180028b39  mov     dword ptr [rsp+70h+var_50], eax
0x180028b3d  call    WPP_SF_sd
0x180028b42  mov     rcx, cs:WPP_GLOBAL_Control
0x180028b49  add     esi, r14d
0x180028b4c  add     rdi, 10h
0x180028b50  cmp     esi, 0Ah
0x180028b53  jb      loc_180028AB3
0x180028b59  jmp     loc_180028D66
0x180028b5e  cmp     ebx, 0FFFFFAE7h
0x180028b64  jz      short loc_180028B74
0x180028b66  lea     rdx, aMOpentable; "M:OpenTable"
0x180028b6d  mov     ecx, ebx
0x180028b6f  jmp     loc_180028D54
0x180028b74  mov     [rsp+70h+var_48], r14
0x180028b79  lea     r8, aMcastclienttab; "MCastClientTableVer3"
0x180028b80  mov     r9d, 0Ah
0x180028b86  mov     dword ptr [rsp+70h+var_50], 50h ; 'P'
0x180028b8e  mov     edx, edi
0x180028b90  mov     rcx, r15
0x180028b93  call    cs:__imp_JetCreateTable
0x180028b9a  nop     dword ptr [rax+rax+00h]
0x180028b9f  mov     ebx, eax
0x180028ba1  mov     rcx, cs:WPP_GLOBAL_Control
0x180028ba8  lea     rax, WPP_GLOBAL_Control
0x180028baf  cmp     rcx, rax
0x180028bb2  jz      short loc_180028BCD
0x180028bb4  test    [rcx+1Ch], esi
0x180028bb7  jz      short loc_180028BCD
0x180028bb9  mov     rcx, [rcx+10h]
0x180028bbd  mov     edx, 0Ch
0x180028bc2  mov     r9d, ebx
0x180028bc5  mov     r8, r13
0x180028bc8  call    WPP_SF_D
0x180028bcd  lea     rdx, aMCreatetable; "M:CreateTAble"
0x180028bd4  mov     ecx, ebx
0x180028bd6  call    DhcpMapJetError
0x180028bdb  mov     ebx, eax
0x180028bdd  test    eax, eax
0x180028bdf  jnz     loc_180028D8E
0x180028be5  mov     qword ptr [rbp+var_30], 1Ch
0x180028bed  lea     r14d, [rax+1]
0x180028bf1  mov     dword ptr [rbp+var_30+0Ch], 4090001h
0x180028bf8  mov     esi, r12d
0x180028bfb  mov     [rbp+var_20], 4E4h
0x180028c03  mov     rdi, r12
0x180028c06  mov     [rbp+var_18], r12d
0x180028c0a  mov     r8, cs:MadcapGlobalClientTable
0x180028c11  lea     r9, [rbp+var_30]
0x180028c15  mov     rdx, cs:MadcapGlobalClientTableHandle
0x180028c1c  mov     rcx, r15
0x180028c1f  mov     eax, [rdi+r8+0Ch]
0x180028c24  mov     dword ptr [rbp+var_30+8], eax
0x180028c27  mov     eax, esi
0x180028c29  shl     rax, 4
0x180028c2d  add     rax, 8
0x180028c31  add     rax, r8
0x180028c34  mov     r8, [rdi+r8]
0x180028c38  mov     [rsp+70h+var_40], rax
0x180028c3d  mov     dword ptr [rsp+70h+var_48], r12d
0x180028c42  mov     [rsp+70h+var_50], r12
0x180028c47  call    cs:__imp_JetAddColumn
0x180028c4e  nop     dword ptr [rax+rax+00h]
0x180028c53  mov     ecx, eax
0x180028c55  lea     rdx, aMAddcolumn; "M:AddColumn"
0x180028c5c  call    DhcpMapJetError
0x180028c61  mov     ebx, eax
0x180028c63  test    eax, eax
0x180028c65  jnz     loc_180028D8E
0x180028c6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180028c72  lea     rax, WPP_GLOBAL_Control
0x180028c79  cmp     rcx, rax
0x180028c7c  jz      short loc_180028CAA
0x180028c7e  test    dword ptr [rcx+1Ch], 8000h
0x180028c85  jz      short loc_180028CAA
0x180028c87  mov     r9, cs:MadcapGlobalClientTable
0x180028c8e  lea     edx, [rbx+0Dh]
0x180028c91  mov     rcx, [rcx+10h]
0x180028c95  mov     r8, r13
0x180028c98  mov     eax, [rdi+r9+8]
0x180028c9d  mov     r9, [rdi+r9]
0x180028ca1  mov     dword ptr [rsp+70h+var_50], eax
0x180028ca5  call    WPP_SF_sd
0x180028caa  add     esi, r14d
0x180028cad  add     rdi, 10h
0x180028cb1  cmp     esi, 0Ah
0x180028cb4  jb      loc_180028C0A
0x180028cba  mov     r8, cs:MadcapGlobalClientTable
0x180028cc1  lea     rax, aMcastipaddr; "+MCastIpAddr"
0x180028cc8  mov     rdx, cs:MadcapGlobalClientTableHandle
0x180028ccf  mov     edi, 32h ; '2'
0x180028cd4  mov     dword ptr [rsp+70h+var_40], edi
0x180028cd8  mov     rcx, r15
0x180028cdb  mov     dword ptr [rsp+70h+var_48], 0Eh
0x180028ce3  mov     r8, [r8]
0x180028ce6  lea     r9d, [rdi-30h]
0x180028cea  mov     [rsp+70h+var_50], rax
0x180028cef  call    cs:__imp_JetCreateIndex
0x180028cf6  nop     dword ptr [rax+rax+00h]
0x180028cfb  mov     ecx, eax
0x180028cfd  lea     rdx, aMCreateindex; "M:CreateIndex"
0x180028d04  call    DhcpMapJetError
0x180028d09  mov     ebx, eax
0x180028d0b  test    eax, eax
0x180028d0d  jnz     short loc_180028D8E
0x180028d0f  mov     r8, cs:MadcapGlobalClientTable
0x180028d16  lea     rax, aMcastclientid_0; "+MCastClientID"
0x180028d1d  mov     rdx, cs:MadcapGlobalClientTableHandle
0x180028d24  mov     r9d, r14d
0x180028d27  mov     dword ptr [rsp+70h+var_40], edi
0x180028d2b  mov     rcx, r15
0x180028d2e  mov     dword ptr [rsp+70h+var_48], 10h
0x180028d36  mov     r8, [r8+10h]
0x180028d3a  mov     [rsp+70h+var_50], rax
0x180028d3f  call    cs:__imp_JetCreateIndex
0x180028d46  nop     dword ptr [rax+rax+00h]
0x180028d4b  mov     ecx, eax
0x180028d4d  lea     rdx, aMCreateindex; "M:CreateIndex"
0x180028d54  call    DhcpMapJetError
0x180028d59  mov     ebx, eax
0x180028d5b  test    eax, eax
0x180028d5d  jnz     short loc_180028D8E
0x180028d5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180028d66  lea     rax, WPP_GLOBAL_Control
0x180028d6d  cmp     rcx, rax
0x180028d70  jz      short loc_180028DBE
0x180028d72  test    dword ptr [rcx+1Ch], 800h
0x180028d79  jz      short loc_180028DBE
0x180028d7b  mov     rcx, [rcx+10h]
0x180028d7f  mov     edx, 0Fh
0x180028d84  mov     r8, r13
0x180028d87  call    WPP_SF_
0x180028d8c  jmp     short loc_180028DBE
0x180028d8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180028d95  lea     rax, WPP_GLOBAL_Control
0x180028d9c  cmp     rcx, rax
0x180028d9f  jz      short loc_180028DBE
0x180028da1  test    dword ptr [rcx+1Ch], 800h
0x180028da8  jz      short loc_180028DBE
0x180028daa  mov     rcx, [rcx+10h]
0x180028dae  mov     edx, 0Eh
0x180028db3  mov     r9d, ebx
0x180028db6  mov     r8, r13
0x180028db9  call    WPP_SF_D
0x180028dbe  mov     eax, ebx
0x180028dc0  mov     rcx, [rbp+var_10]
0x180028dc4  xor     rcx, rsp; StackCookie
0x180028dc7  call    __security_check_cookie
0x180028dcc  lea     r11, [rsp+70h+var_s0]
0x180028dd1  mov     rbx, [r11+38h]
0x180028dd5  mov     rsi, [r11+40h]
0x180028dd9  mov     rdi, [r11+48h]
0x180028ddd  mov     rsp, r11
0x180028de0  pop     r15
0x180028de2  pop     r14
0x180028de4  pop     r13
0x180028de6  pop     r12
0x180028de8  pop     rbp
0x180028de9  retn
```
