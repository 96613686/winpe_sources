# DhcpCreateAndInitDatabase

- ea: `0x18000d3ec`
- end: `0x18000d90d`
- name: `DhcpCreateAndInitDatabase`
- size: `1313`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18000df98`

## callees

- `0x180002854`
- `0x18000323c`
- `0x18000d06c`
- `0x18000d3ec`
- `0x18000f144`
- `0x18001130c`
- `0x1800289e8`
- `0x18009d7ac`
- `0x18009dc58`
- `0x18009dda0`
- `0x1800b45f0`
- `0x1800cc9e0`

## import_xrefs

- `ESENT!JetCreateIndex` at `0x18000d740`
- `ESENT!JetCreateIndex` at `0x18000d79b`
- `ESENT!JetCreateIndex` at `0x18000d7f0`
- `ESENT!JetCreateIndex` at `0x18000d740`
- `ESENT!JetCreateIndex` at `0x18000d79b`
- `ESENT!JetCreateIndex` at `0x18000d7f0`
- `ESENT!JetCreateDatabase` at `0x18000d4e3`
- `ESENT!JetCreateDatabase` at `0x18000d4e3`
- `ESENT!JetCreateTable` at `0x18000d533`
- `ESENT!JetCreateTable` at `0x18000d533`
- `ESENT!JetAddColumn` at `0x18000d5c3`
- `ESENT!JetAddColumn` at `0x18000d5c3`
- `ESENT!JetSetColumnDefaultValue` at `0x18000d629`
- `ESENT!JetSetColumnDefaultValue` at `0x18000d686`
- `ESENT!JetSetColumnDefaultValue` at `0x18000d6e5`
- `ESENT!JetSetColumnDefaultValue` at `0x18000d629`
- `ESENT!JetSetColumnDefaultValue` at `0x18000d686`
- `ESENT!JetSetColumnDefaultValue` at `0x18000d6e5`
- `USER32!OemToCharBuffA` at `0x18000d4bc`
- `USER32!OemToCharBuffA` at `0x18000d4bc`

## string_xrefs

- `0x18000d4f1`: `CreateDatabase`
- `0x18000d541`: `CreateTable`
- `0x18000d74c`: `CreateIndex`
- `0x18000d76e`: `+HardwareAddress`

## pseudocode

```c
__int64 DhcpCreateAndInitDatabase()
{
  __int64 v0; // rbx
  __int64 v1; // rax
  __int64 v2; // rcx
  unsigned int Database; // eax
  unsigned int ClientTableWin8Indices; // ebx
  unsigned int Table; // eax
  unsigned int v6; // edi
  __int64 v7; // rsi
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int Index; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  __int64 v16; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v18; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v19; // [rsp+68h] [rbp-A0h]
  int v20; // [rsp+70h] [rbp-98h]
  CHAR pszDest[272]; // [rsp+78h] [rbp-90h] BYREF

  v19 = 0;
  v0 = -1;
  v20 = 0;
  LOBYTE(v16) = 0;
  v1 = -1;
  v17 = 0;
  v18 = 0;
  pszDest[0] = 0;
  do
    ++v1;
  while ( DhcpGlobalOemDatabaseName[v1] );
  v2 = -1;
  do
    ++v2;
  while ( DhcpGlobalOemDatabasePath[v2] );
  if ( (unsigned __int64)(v2 + v1 + 2) < 0x104 )
    StringCbPrintfA(pszDest, 0x104u, "%s%s%s", DhcpGlobalOemDatabasePath, "\\", DhcpGlobalOemDatabaseName);
  do
    ++v0;
  while ( pszDest[v0] );
  OemToCharBuffA(pszDest, pszDest, v0);
  Database = JetCreateDatabase(DhcpGlobalJetServerSession, pszDest, 0, &DhcpGlobalDatabaseHandle, 0);
  ClientTableWin8Indices = DhcpMapJetError(Database, "CreateDatabase");
  if ( !ClientTableWin8Indices )
  {
    Table = JetCreateTable(
              DhcpGlobalJetServerSession,
              DhcpGlobalDatabaseHandle,
              "ClientTable",
              10,
              80,
              &DhcpGlobalClientTableHandle);
    ClientTableWin8Indices = DhcpMapJetError(Table, "CreateTable");
    if ( !ClientTableWin8Indices )
    {
      *(_QWORD *)&v18 = 28;
      HIDWORD(v18) = 67698689;
      v6 = 0;
      v19 = 1252;
      v7 = 0;
      v20 = 0;
      while ( 1 )
      {
        DWORD2(v18) = *(_DWORD *)(v7 + DhcpGlobalClientTable + 12);
        v8 = JetAddColumn(
               DhcpGlobalJetServerSession,
               DhcpGlobalClientTableHandle,
               *(_QWORD *)(v7 + DhcpGlobalClientTable),
               &v18,
               0,
               0,
               DhcpGlobalClientTable + 16LL * v6 + 8);
        ClientTableWin8Indices = DhcpMapJetError(v8, "AddColumn");
        if ( ClientTableWin8Indices )
          break;
        ++v6;
        v7 += 16;
        if ( v6 >= 0x17 )
        {
          v9 = JetSetColumnDefaultValue(
                 DhcpGlobalJetServerSession,
                 DhcpGlobalDatabaseHandle,
                 "ClientTable",
                 *(_QWORD *)(DhcpGlobalClientTable + 160),
                 &v16,
                 1,
                 0);
          ClientTableWin8Indices = DhcpMapJetError(v9, "AddColumnDefaultValue-qstatus");
          if ( ClientTableWin8Indices )
            break;
          v10 = JetSetColumnDefaultValue(
                  DhcpGlobalJetServerSession,
                  DhcpGlobalDatabaseHandle,
                  "ClientTable",
                  *(_QWORD *)(DhcpGlobalClientTable + 176),
                  &v17,
                  8,
                  0);
          ClientTableWin8Indices = DhcpMapJetError(v10, "AddColumnDefaultValue-qprob");
          if ( ClientTableWin8Indices )
            break;
          LOBYTE(v16) = 1;
          v11 = JetSetColumnDefaultValue(
                  DhcpGlobalJetServerSession,
                  DhcpGlobalDatabaseHandle,
                  "ClientTable",
                  *(_QWORD *)(DhcpGlobalClientTable + 192),
                  &v16,
                  1,
                  0);
          ClientTableWin8Indices = DhcpMapJetError(v11, "AddColumnDefaultValue-qcapable");
          if ( ClientTableWin8Indices )
            break;
          Index = JetCreateIndex(
                    DhcpGlobalJetServerSession,
                    DhcpGlobalClientTableHandle,
                    *(_QWORD *)DhcpGlobalClientTable,
                    2,
                    "+IpAddress",
                    12,
                    50);
          ClientTableWin8Indices = DhcpMapJetError(Index, "CreateIndex");
          if ( ClientTableWin8Indices )
            break;
          v13 = JetCreateIndex(
                  DhcpGlobalJetServerSession,
                  DhcpGlobalClientTableHandle,
                  *(_QWORD *)(DhcpGlobalClientTable + 16),
                  1,
                  "+HardwareAddress",
                  18,
                  50);
          ClientTableWin8Indices = DhcpMapJetError(v13, "CreateIndex");
          if ( ClientTableWin8Indices )
            break;
          v14 = JetCreateIndex(
                  DhcpGlobalJetServerSession,
                  DhcpGlobalClientTableHandle,
                  *(_QWORD *)(DhcpGlobalClientTable + 64),
                  8,
                  "+MachineName",
                  14,
                  50);
          ClientTableWin8Indices = DhcpMapJetError(v14, "CreateIndex");
          if ( ClientTableWin8Indices )
            break;
          ClientTableWin8Indices = CreateClientTableWin8Indices();
          if ( ClientTableWin8Indices )
            break;
          ClientTableWin8Indices = DhcpOpenFilterDbTable(DhcpGlobalJetServerSession);
          if ( ClientTableWin8Indices )
            break;
          ClientTableWin8Indices = DhcpOpenFailoverDbTable(DhcpGlobalJetServerSession);
          if ( ClientTableWin8Indices )
            break;
          ClientTableWin8Indices = DhcpFOOpenDeletedAddressTable(DhcpGlobalJetServerSession);
          if ( ClientTableWin8Indices )
            break;
          ClientTableWin8Indices = DhcpOpenFailoverBitmaskTable(DhcpGlobalJetServerSession);
          if ( ClientTableWin8Indices )
            break;
          ClientTableWin8Indices = DhcpOpenMCastDbTable(DhcpGlobalJetServerSession);
          if ( ClientTableWin8Indices )
            break;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids);
          }
          return ClientTableWin8Indices;
        }
      }
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids,
      ClientTableWin8Indices);
  return ClientTableWin8Indices;
}

```

## disassembly

```asm
0x18000d3ec  mov     rax, rsp
0x18000d3ef  mov     [rax+8], rbx
0x18000d3f3  mov     [rax+10h], rsi
0x18000d3f7  mov     [rax+18h], rdi
0x18000d3fb  push    rbp
0x18000d3fc  push    r14
0x18000d3fe  push    r15
0x18000d400  lea     rbp, [rax-0A8h]
0x18000d407  sub     rsp, 190h
0x18000d40e  mov     rax, cs:__security_cookie
0x18000d415  xor     rax, rsp
0x18000d418  mov     [rbp+0A0h+var_20], rax
0x18000d41f  mov     r8, cs:DhcpGlobalOemDatabaseName
0x18000d426  xor     eax, eax
0x18000d428  xor     r14d, r14d
0x18000d42b  mov     [rsp+1A0h+var_140], rax
0x18000d430  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000d434  mov     [rsp+1A0h+var_138], eax
0x18000d438  xorps   xmm0, xmm0
0x18000d43b  mov     byte ptr [rsp+1A0h+var_160], r14b
0x18000d440  mov     rax, rbx
0x18000d443  mov     qword ptr [rsp+1A0h+var_158], r14
0x18000d448  movups  [rsp+1A0h+var_158+8], xmm0
0x18000d44d  mov     [rsp+1A0h+pszDest], r14b
0x18000d452  inc     rax
0x18000d455  cmp     [r8+rax], r14b
0x18000d459  jnz     short loc_18000D452
0x18000d45b  mov     r9, cs:DhcpGlobalOemDatabasePath
0x18000d462  mov     rcx, rbx
0x18000d465  inc     rcx
0x18000d468  cmp     [r9+rcx], r14b
0x18000d46c  jnz     short loc_18000D465
0x18000d46e  add     rax, 2
0x18000d472  mov     edx, 104h; cbDest
0x18000d477  add     rax, rcx
0x18000d47a  cmp     rax, rdx
0x18000d47d  jnb     short loc_18000D4A1
0x18000d47f  mov     [rsp+1A0h+var_178], r8
0x18000d484  lea     rax, asc_1800DCB80; "\\"
0x18000d48b  lea     r8, aSSS_0; "%s%s%s"
0x18000d492  mov     [rsp+1A0h+var_180], rax
0x18000d497  lea     rcx, [rsp+1A0h+pszDest]; pszDest
0x18000d49c  call    StringCbPrintfA
0x18000d4a1  lea     rax, [rsp+1A0h+pszDest]
0x18000d4a6  inc     rbx
0x18000d4a9  cmp     [rax+rbx], r14b
0x18000d4ad  jnz     short loc_18000D4A6
0x18000d4af  mov     r8, rbx; cchDstLength
0x18000d4b2  lea     rdx, [rsp+1A0h+pszDest]; lpszDst
0x18000d4b7  lea     rcx, [rsp+1A0h+pszDest]; lpszSrc
0x18000d4bc  call    cs:__imp_OemToCharBuffA
0x18000d4c3  nop     dword ptr [rax+rax+00h]
0x18000d4c8  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000d4cf  lea     r9, DhcpGlobalDatabaseHandle
0x18000d4d6  xor     r8d, r8d
0x18000d4d9  mov     dword ptr [rsp+1A0h+var_180], r14d
0x18000d4de  lea     rdx, [rsp+1A0h+pszDest]
0x18000d4e3  call    cs:__imp_JetCreateDatabase
0x18000d4ea  nop     dword ptr [rax+rax+00h]
0x18000d4ef  mov     ecx, eax
0x18000d4f1  lea     rdx, aCreatedatabase; "CreateDatabase"
0x18000d4f8  call    DhcpMapJetError
0x18000d4fd  mov     ebx, eax
0x18000d4ff  test    eax, eax
0x18000d501  jnz     loc_18000D8AA
0x18000d507  mov     edx, cs:DhcpGlobalDatabaseHandle
0x18000d50d  lea     rax, DhcpGlobalClientTableHandle
0x18000d514  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000d51b  lea     r9d, [rbx+0Ah]
0x18000d51f  mov     [rsp+1A0h+var_178], rax
0x18000d524  lea     r8, aClienttable; "ClientTable"
0x18000d52b  mov     dword ptr [rsp+1A0h+var_180], 50h ; 'P'
0x18000d533  call    cs:__imp_JetCreateTable
0x18000d53a  nop     dword ptr [rax+rax+00h]
0x18000d53f  mov     ecx, eax
0x18000d541  lea     rdx, aCreatetable_0; "CreateTable"
0x18000d548  call    DhcpMapJetError
0x18000d54d  mov     ebx, eax
0x18000d54f  test    eax, eax
0x18000d551  jnz     loc_18000D8AA
0x18000d557  mov     qword ptr [rsp+1A0h+var_158+8], 1Ch
0x18000d560  lea     r15d, [rax+1]
0x18000d564  mov     dword ptr [rsp+1A0h+var_148+4], 4090001h
0x18000d56c  mov     edi, r14d
0x18000d56f  mov     [rsp+1A0h+var_140], 4E4h
0x18000d578  mov     rsi, r14
0x18000d57b  mov     [rsp+1A0h+var_138], r14d
0x18000d580  mov     r8, cs:DhcpGlobalClientTable
0x18000d587  lea     r9, [rsp+1A0h+var_158+8]
0x18000d58c  mov     rdx, cs:DhcpGlobalClientTableHandle
0x18000d593  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000d59a  mov     eax, [rsi+r8+0Ch]
0x18000d59f  mov     dword ptr [rsp+1A0h+var_148], eax
0x18000d5a3  mov     eax, edi
0x18000d5a5  shl     rax, 4
0x18000d5a9  add     rax, 8
0x18000d5ad  add     rax, r8
0x18000d5b0  mov     r8, [rsi+r8]
0x18000d5b4  mov     [rsp+1A0h+var_170], rax
0x18000d5b9  mov     dword ptr [rsp+1A0h+var_178], r14d
0x18000d5be  mov     [rsp+1A0h+var_180], r14
0x18000d5c3  call    cs:__imp_JetAddColumn
0x18000d5ca  nop     dword ptr [rax+rax+00h]
0x18000d5cf  mov     ecx, eax
0x18000d5d1  lea     rdx, aAddcolumn; "AddColumn"
0x18000d5d8  call    DhcpMapJetError
0x18000d5dd  mov     ebx, eax
0x18000d5df  test    eax, eax
0x18000d5e1  jnz     loc_18000D8AA
0x18000d5e7  add     edi, r15d
0x18000d5ea  add     rsi, 10h
0x18000d5ee  cmp     edi, 17h
0x18000d5f1  jb      short loc_18000D580
0x18000d5f3  mov     r9, cs:DhcpGlobalClientTable
0x18000d5fa  lea     rax, [rsp+1A0h+var_160]
0x18000d5ff  mov     edx, cs:DhcpGlobalDatabaseHandle
0x18000d605  lea     r8, aClienttable; "ClientTable"
0x18000d60c  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000d613  mov     dword ptr [rsp+1A0h+var_170], r14d
0x18000d618  mov     r9, [r9+0A0h]
0x18000d61f  mov     dword ptr [rsp+1A0h+var_178], r15d
0x18000d624  mov     [rsp+1A0h+var_180], rax
0x18000d629  call    cs:__imp_JetSetColumnDefaultValue
0x18000d630  nop     dword ptr [rax+rax+00h]
0x18000d635  mov     ecx, eax
0x18000d637  lea     rdx, aAddcolumndefau_1; "AddColumnDefaultValue-qstatus"
0x18000d63e  call    DhcpMapJetError
0x18000d643  mov     ebx, eax
0x18000d645  test    eax, eax
0x18000d647  jnz     loc_18000D8AA
0x18000d64d  mov     r9, cs:DhcpGlobalClientTable
0x18000d654  lea     rax, [rsp+1A0h+var_158]
0x18000d659  mov     edx, cs:DhcpGlobalDatabaseHandle
0x18000d65f  lea     r8, aClienttable; "ClientTable"
0x18000d666  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000d66d  mov     dword ptr [rsp+1A0h+var_170], r14d
0x18000d672  mov     r9, [r9+0B0h]
0x18000d679  mov     dword ptr [rsp+1A0h+var_178], 8
0x18000d681  mov     [rsp+1A0h+var_180], rax
0x18000d686  call    cs:__imp_JetSetColumnDefaultValue
0x18000d68d  nop     dword ptr [rax+rax+00h]
0x18000d692  mov     ecx, eax
0x18000d694  lea     rdx, aAddcolumndefau; "AddColumnDefaultValue-qprob"
0x18000d69b  call    DhcpMapJetError
0x18000d6a0  mov     ebx, eax
0x18000d6a2  test    eax, eax
0x18000d6a4  jnz     loc_18000D8AA
0x18000d6aa  mov     r9, cs:DhcpGlobalClientTable
0x18000d6b1  lea     rax, [rsp+1A0h+var_160]
0x18000d6b6  mov     edx, cs:DhcpGlobalDatabaseHandle
0x18000d6bc  lea     r8, aClienttable; "ClientTable"
0x18000d6c3  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000d6ca  mov     byte ptr [rsp+1A0h+var_160], r15b
0x18000d6cf  mov     r9, [r9+0C0h]
0x18000d6d6  mov     dword ptr [rsp+1A0h+var_170], r14d
0x18000d6db  mov     dword ptr [rsp+1A0h+var_178], r15d
0x18000d6e0  mov     [rsp+1A0h+var_180], rax
0x18000d6e5  call    cs:__imp_JetSetColumnDefaultValue
0x18000d6ec  nop     dword ptr [rax+rax+00h]
0x18000d6f1  mov     ecx, eax
0x18000d6f3  lea     rdx, aAddcolumndefau_0; "AddColumnDefaultValue-qcapable"
0x18000d6fa  call    DhcpMapJetError
0x18000d6ff  mov     ebx, eax
0x18000d701  test    eax, eax
0x18000d703  jnz     loc_18000D8AA
0x18000d709  mov     r8, cs:DhcpGlobalClientTable
0x18000d710  lea     edi, [rax+32h]
0x18000d713  mov     rdx, cs:DhcpGlobalClientTableHandle
0x18000d71a  lea     rax, aIpaddress_1; "+IpAddress"
0x18000d721  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000d728  lea     r9d, [rbx+2]
0x18000d72c  mov     dword ptr [rsp+1A0h+var_170], edi
0x18000d730  mov     r8, [r8]
0x18000d733  mov     dword ptr [rsp+1A0h+var_178], 0Ch
0x18000d73b  mov     [rsp+1A0h+var_180], rax
0x18000d740  call    cs:__imp_JetCreateIndex
0x18000d747  nop     dword ptr [rax+rax+00h]
0x18000d74c  lea     rsi, aCreateindex; "CreateIndex"
0x18000d753  mov     ecx, eax
0x18000d755  mov     rdx, rsi
0x18000d758  call    DhcpMapJetError
0x18000d75d  mov     ebx, eax
0x18000d75f  test    eax, eax
0x18000d761  jnz     loc_18000D8AA
0x18000d767  mov     r8, cs:DhcpGlobalClientTable
0x18000d76e  lea     rax, aHardwareaddres_0; "+HardwareAddress"
0x18000d775  mov     rdx, cs:DhcpGlobalClientTableHandle
0x18000d77c  mov     r9d, r15d
0x18000d77f  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000d786  mov     dword ptr [rsp+1A0h+var_170], edi
0x18000d78a  mov     r8, [r8+10h]
0x18000d78e  mov     dword ptr [rsp+1A0h+var_178], 12h
0x18000d796  mov     [rsp+1A0h+var_180], rax
0x18000d79b  call    cs:__imp_JetCreateIndex
0x18000d7a2  nop     dword ptr [rax+rax+00h]
0x18000d7a7  mov     ecx, eax
0x18000d7a9  mov     rdx, rsi
0x18000d7ac  call    DhcpMapJetError
0x18000d7b1  mov     ebx, eax
0x18000d7b3  test    eax, eax
0x18000d7b5  jnz     loc_18000D8AA
0x18000d7bb  mov     r8, cs:DhcpGlobalClientTable
0x18000d7c2  lea     rax, aMachinename; "+MachineName"
0x18000d7c9  mov     rdx, cs:DhcpGlobalClientTableHandle
0x18000d7d0  lea     r9d, [rdi-2Ah]
0x18000d7d4  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000d7db  mov     dword ptr [rsp+1A0h+var_170], edi
0x18000d7df  mov     r8, [r8+40h]
0x18000d7e3  mov     dword ptr [rsp+1A0h+var_178], 0Eh
0x18000d7eb  mov     [rsp+1A0h+var_180], rax
0x18000d7f0  call    cs:__imp_JetCreateIndex
0x18000d7f7  nop     dword ptr [rax+rax+00h]
0x18000d7fc  mov     ecx, eax
0x18000d7fe  mov     rdx, rsi
0x18000d801  call    DhcpMapJetError
0x18000d806  mov     ebx, eax
0x18000d808  test    eax, eax
0x18000d80a  jnz     loc_18000D8AA
0x18000d810  call    CreateClientTableWin8Indices
0x18000d815  mov     ebx, eax
0x18000d817  test    eax, eax
0x18000d819  jnz     loc_18000D8AA
0x18000d81f  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18000d826  call    DhcpOpenFilterDbTable
0x18000d82b  mov     ebx, eax
0x18000d82d  test    eax, eax
0x18000d82f  jnz     short loc_18000D8AA
0x18000d831  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000d838  call    DhcpOpenFailoverDbTable
0x18000d83d  mov     ebx, eax
0x18000d83f  test    eax, eax
0x18000d841  jnz     short loc_18000D8AA
0x18000d843  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000d84a  call    DhcpFOOpenDeletedAddressTable
0x18000d84f  mov     ebx, eax
0x18000d851  test    eax, eax
0x18000d853  jnz     short loc_18000D8AA
0x18000d855  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000d85c  call    DhcpOpenFailoverBitmaskTable
0x18000d861  mov     ebx, eax
0x18000d863  test    eax, eax
0x18000d865  jnz     short loc_18000D8AA
0x18000d867  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000d86e  call    DhcpOpenMCastDbTable
0x18000d873  mov     ebx, eax
0x18000d875  test    eax, eax
0x18000d877  jnz     short loc_18000D8AA
0x18000d879  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d880  lea     rax, WPP_GLOBAL_Control
0x18000d887  cmp     rcx, rax
0x18000d88a  jz      short loc_18000D8DE
0x18000d88c  test    dword ptr [rcx+1Ch], 800h
0x18000d893  jz      short loc_18000D8DE
0x18000d895  mov     rcx, [rcx+10h]
0x18000d899  lea     edx, [rdi-22h]
0x18000d89c  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000d8a3  call    WPP_SF_
0x18000d8a8  jmp     short loc_18000D8DE
0x18000d8aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8b1  lea     rax, WPP_GLOBAL_Control
0x18000d8b8  cmp     rcx, rax
0x18000d8bb  jz      short loc_18000D8DE
0x18000d8bd  test    dword ptr [rcx+1Ch], 800h
0x18000d8c4  jz      short loc_18000D8DE
0x18000d8c6  mov     rcx, [rcx+10h]
0x18000d8ca  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000d8d1  mov     edx, 0Fh
0x18000d8d6  mov     r9d, ebx
0x18000d8d9  call    WPP_SF_D
0x18000d8de  mov     eax, ebx
0x18000d8e0  mov     rcx, [rbp+0A0h+var_20]
0x18000d8e7  xor     rcx, rsp; StackCookie
0x18000d8ea  call    __security_check_cookie
0x18000d8ef  lea     r11, [rsp+1A0h+var_10]
0x18000d8f7  mov     rbx, [r11+20h]
0x18000d8fb  mov     rsi, [r11+28h]
0x18000d8ff  mov     rdi, [r11+30h]
0x18000d903  mov     rsp, r11
0x18000d906  pop     r15
0x18000d908  pop     r14
0x18000d90a  pop     rbp
0x18000d90b  retn
```
