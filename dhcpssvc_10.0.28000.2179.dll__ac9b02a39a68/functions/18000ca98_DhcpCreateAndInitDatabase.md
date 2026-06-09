# DhcpCreateAndInitDatabase

- ea: `0x18000ca98`
- end: `0x18000cfb9`
- name: `DhcpCreateAndInitDatabase`
- size: `1313`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18000d644`

## callees

- `0x18000282c`
- `0x180003228`
- `0x18000c714`
- `0x18000ca98`
- `0x18000e814`
- `0x180010a14`
- `0x180027f7c`
- `0x18009e464`
- `0x18009e90c`
- `0x18009ea58`
- `0x1800b546c`
- `0x1800cdac0`

## import_xrefs

- `ESENT!JetCreateIndex` at `0x18000cdec`
- `ESENT!JetCreateIndex` at `0x18000ce47`
- `ESENT!JetCreateIndex` at `0x18000ce9c`
- `ESENT!JetCreateIndex` at `0x18000cdec`
- `ESENT!JetCreateIndex` at `0x18000ce47`
- `ESENT!JetCreateIndex` at `0x18000ce9c`
- `ESENT!JetCreateDatabase` at `0x18000cb8f`
- `ESENT!JetCreateDatabase` at `0x18000cb8f`
- `ESENT!JetCreateTable` at `0x18000cbdf`
- `ESENT!JetCreateTable` at `0x18000cbdf`
- `ESENT!JetAddColumn` at `0x18000cc6f`
- `ESENT!JetAddColumn` at `0x18000cc6f`
- `ESENT!JetSetColumnDefaultValue` at `0x18000ccd5`
- `ESENT!JetSetColumnDefaultValue` at `0x18000cd32`
- `ESENT!JetSetColumnDefaultValue` at `0x18000cd91`
- `ESENT!JetSetColumnDefaultValue` at `0x18000ccd5`
- `ESENT!JetSetColumnDefaultValue` at `0x18000cd32`
- `ESENT!JetSetColumnDefaultValue` at `0x18000cd91`
- `USER32!OemToCharBuffA` at `0x18000cb68`
- `USER32!OemToCharBuffA` at `0x18000cb68`

## string_xrefs

- `0x18000cb9d`: `CreateDatabase`
- `0x18000cbed`: `CreateTable`
- `0x18000cdf8`: `CreateIndex`
- `0x18000ce1a`: `+HardwareAddress`

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
  while ( DhcpGlobalOemDatabasePath[v1] );
  v2 = -1;
  do
    ++v2;
  while ( DhcpGlobalOemDatabaseName[v2] );
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
0x18000ca98  mov     rax, rsp
0x18000ca9b  mov     [rax+8], rbx
0x18000ca9f  mov     [rax+10h], rsi
0x18000caa3  mov     [rax+18h], rdi
0x18000caa7  push    rbp
0x18000caa8  push    r14
0x18000caaa  push    r15
0x18000caac  lea     rbp, [rax-0A8h]
0x18000cab3  sub     rsp, 190h
0x18000caba  mov     rax, cs:__security_cookie
0x18000cac1  xor     rax, rsp
0x18000cac4  mov     [rbp+0A0h+var_20], rax
0x18000cacb  mov     r9, cs:DhcpGlobalOemDatabasePath
0x18000cad2  xor     eax, eax
0x18000cad4  xor     r14d, r14d
0x18000cad7  mov     [rsp+1A0h+var_140], rax
0x18000cadc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000cae0  mov     [rsp+1A0h+var_138], eax
0x18000cae4  xorps   xmm0, xmm0
0x18000cae7  mov     byte ptr [rsp+1A0h+var_160], r14b
0x18000caec  mov     rax, rbx
0x18000caef  mov     qword ptr [rsp+1A0h+var_158], r14
0x18000caf4  movups  [rsp+1A0h+var_158+8], xmm0
0x18000caf9  mov     [rsp+1A0h+pszDest], r14b
0x18000cafe  inc     rax
0x18000cb01  cmp     [r9+rax], r14b
0x18000cb05  jnz     short loc_18000CAFE
0x18000cb07  mov     r8, cs:DhcpGlobalOemDatabaseName
0x18000cb0e  mov     rcx, rbx
0x18000cb11  inc     rcx
0x18000cb14  cmp     [r8+rcx], r14b
0x18000cb18  jnz     short loc_18000CB11
0x18000cb1a  add     rax, 2
0x18000cb1e  mov     edx, 104h; cbDest
0x18000cb23  add     rax, rcx
0x18000cb26  cmp     rax, rdx
0x18000cb29  jnb     short loc_18000CB4D
0x18000cb2b  mov     [rsp+1A0h+var_178], r8
0x18000cb30  lea     rax, asc_1800DEB20; "\\"
0x18000cb37  lea     r8, aSSS_0; "%s%s%s"
0x18000cb3e  mov     [rsp+1A0h+var_180], rax
0x18000cb43  lea     rcx, [rsp+1A0h+pszDest]; pszDest
0x18000cb48  call    StringCbPrintfA
0x18000cb4d  lea     rax, [rsp+1A0h+pszDest]
0x18000cb52  inc     rbx
0x18000cb55  cmp     [rax+rbx], r14b
0x18000cb59  jnz     short loc_18000CB52
0x18000cb5b  mov     r8d, ebx; cchDstLength
0x18000cb5e  lea     rdx, [rsp+1A0h+pszDest]; lpszDst
0x18000cb63  lea     rcx, [rsp+1A0h+pszDest]; lpszSrc
0x18000cb68  call    cs:__imp_OemToCharBuffA
0x18000cb6f  nop     dword ptr [rax+rax+00h]
0x18000cb74  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000cb7b  lea     r9, DhcpGlobalDatabaseHandle
0x18000cb82  xor     r8d, r8d
0x18000cb85  mov     dword ptr [rsp+1A0h+var_180], r14d
0x18000cb8a  lea     rdx, [rsp+1A0h+pszDest]
0x18000cb8f  call    cs:__imp_JetCreateDatabase
0x18000cb96  nop     dword ptr [rax+rax+00h]
0x18000cb9b  mov     ecx, eax
0x18000cb9d  lea     rdx, aCreatedatabase; "CreateDatabase"
0x18000cba4  call    DhcpMapJetError
0x18000cba9  mov     ebx, eax
0x18000cbab  test    eax, eax
0x18000cbad  jnz     loc_18000CF56
0x18000cbb3  mov     edx, cs:DhcpGlobalDatabaseHandle
0x18000cbb9  lea     rax, DhcpGlobalClientTableHandle
0x18000cbc0  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000cbc7  lea     r9d, [rbx+0Ah]
0x18000cbcb  mov     [rsp+1A0h+var_178], rax
0x18000cbd0  lea     r8, aClienttable; "ClientTable"
0x18000cbd7  mov     dword ptr [rsp+1A0h+var_180], 50h ; 'P'
0x18000cbdf  call    cs:__imp_JetCreateTable
0x18000cbe6  nop     dword ptr [rax+rax+00h]
0x18000cbeb  mov     ecx, eax
0x18000cbed  lea     rdx, aCreatetable_0; "CreateTable"
0x18000cbf4  call    DhcpMapJetError
0x18000cbf9  mov     ebx, eax
0x18000cbfb  test    eax, eax
0x18000cbfd  jnz     loc_18000CF56
0x18000cc03  mov     qword ptr [rsp+1A0h+var_158+8], 1Ch
0x18000cc0c  lea     r15d, [rax+1]
0x18000cc10  mov     dword ptr [rsp+1A0h+var_148+4], 4090001h
0x18000cc18  mov     edi, r14d
0x18000cc1b  mov     [rsp+1A0h+var_140], 4E4h
0x18000cc24  mov     rsi, r14
0x18000cc27  mov     [rsp+1A0h+var_138], r14d
0x18000cc2c  mov     r8, cs:DhcpGlobalClientTable
0x18000cc33  lea     r9, [rsp+1A0h+var_158+8]
0x18000cc38  mov     rdx, cs:DhcpGlobalClientTableHandle
0x18000cc3f  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000cc46  mov     eax, [rsi+r8+0Ch]
0x18000cc4b  mov     dword ptr [rsp+1A0h+var_148], eax
0x18000cc4f  mov     eax, edi
0x18000cc51  shl     rax, 4
0x18000cc55  add     rax, 8
0x18000cc59  add     rax, r8
0x18000cc5c  mov     r8, [rsi+r8]
0x18000cc60  mov     [rsp+1A0h+var_170], rax
0x18000cc65  mov     dword ptr [rsp+1A0h+var_178], r14d
0x18000cc6a  mov     [rsp+1A0h+var_180], r14
0x18000cc6f  call    cs:__imp_JetAddColumn
0x18000cc76  nop     dword ptr [rax+rax+00h]
0x18000cc7b  mov     ecx, eax
0x18000cc7d  lea     rdx, aAddcolumn; "AddColumn"
0x18000cc84  call    DhcpMapJetError
0x18000cc89  mov     ebx, eax
0x18000cc8b  test    eax, eax
0x18000cc8d  jnz     loc_18000CF56
0x18000cc93  add     edi, r15d
0x18000cc96  add     rsi, 10h
0x18000cc9a  cmp     edi, 17h
0x18000cc9d  jb      short loc_18000CC2C
0x18000cc9f  mov     r9, cs:DhcpGlobalClientTable
0x18000cca6  lea     rax, [rsp+1A0h+var_160]
0x18000ccab  mov     edx, cs:DhcpGlobalDatabaseHandle
0x18000ccb1  lea     r8, aClienttable; "ClientTable"
0x18000ccb8  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000ccbf  mov     dword ptr [rsp+1A0h+var_170], r14d
0x18000ccc4  mov     r9, [r9+0A0h]
0x18000cccb  mov     dword ptr [rsp+1A0h+var_178], r15d
0x18000ccd0  mov     [rsp+1A0h+var_180], rax
0x18000ccd5  call    cs:__imp_JetSetColumnDefaultValue
0x18000ccdc  nop     dword ptr [rax+rax+00h]
0x18000cce1  mov     ecx, eax
0x18000cce3  lea     rdx, aAddcolumndefau_1; "AddColumnDefaultValue-qstatus"
0x18000ccea  call    DhcpMapJetError
0x18000ccef  mov     ebx, eax
0x18000ccf1  test    eax, eax
0x18000ccf3  jnz     loc_18000CF56
0x18000ccf9  mov     r9, cs:DhcpGlobalClientTable
0x18000cd00  lea     rax, [rsp+1A0h+var_158]
0x18000cd05  mov     edx, cs:DhcpGlobalDatabaseHandle
0x18000cd0b  lea     r8, aClienttable; "ClientTable"
0x18000cd12  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000cd19  mov     dword ptr [rsp+1A0h+var_170], r14d
0x18000cd1e  mov     r9, [r9+0B0h]
0x18000cd25  mov     dword ptr [rsp+1A0h+var_178], 8
0x18000cd2d  mov     [rsp+1A0h+var_180], rax
0x18000cd32  call    cs:__imp_JetSetColumnDefaultValue
0x18000cd39  nop     dword ptr [rax+rax+00h]
0x18000cd3e  mov     ecx, eax
0x18000cd40  lea     rdx, aAddcolumndefau; "AddColumnDefaultValue-qprob"
0x18000cd47  call    DhcpMapJetError
0x18000cd4c  mov     ebx, eax
0x18000cd4e  test    eax, eax
0x18000cd50  jnz     loc_18000CF56
0x18000cd56  mov     r9, cs:DhcpGlobalClientTable
0x18000cd5d  lea     rax, [rsp+1A0h+var_160]
0x18000cd62  mov     edx, cs:DhcpGlobalDatabaseHandle
0x18000cd68  lea     r8, aClienttable; "ClientTable"
0x18000cd6f  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000cd76  mov     byte ptr [rsp+1A0h+var_160], r15b
0x18000cd7b  mov     r9, [r9+0C0h]
0x18000cd82  mov     dword ptr [rsp+1A0h+var_170], r14d
0x18000cd87  mov     dword ptr [rsp+1A0h+var_178], r15d
0x18000cd8c  mov     [rsp+1A0h+var_180], rax
0x18000cd91  call    cs:__imp_JetSetColumnDefaultValue
0x18000cd98  nop     dword ptr [rax+rax+00h]
0x18000cd9d  mov     ecx, eax
0x18000cd9f  lea     rdx, aAddcolumndefau_0; "AddColumnDefaultValue-qcapable"
0x18000cda6  call    DhcpMapJetError
0x18000cdab  mov     ebx, eax
0x18000cdad  test    eax, eax
0x18000cdaf  jnz     loc_18000CF56
0x18000cdb5  mov     r8, cs:DhcpGlobalClientTable
0x18000cdbc  lea     edi, [rax+32h]
0x18000cdbf  mov     rdx, cs:DhcpGlobalClientTableHandle
0x18000cdc6  lea     rax, aIpaddress_1; "+IpAddress"
0x18000cdcd  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000cdd4  lea     r9d, [rbx+2]
0x18000cdd8  mov     dword ptr [rsp+1A0h+var_170], edi
0x18000cddc  mov     r8, [r8]
0x18000cddf  mov     dword ptr [rsp+1A0h+var_178], 0Ch
0x18000cde7  mov     [rsp+1A0h+var_180], rax
0x18000cdec  call    cs:__imp_JetCreateIndex
0x18000cdf3  nop     dword ptr [rax+rax+00h]
0x18000cdf8  lea     rsi, aCreateindex; "CreateIndex"
0x18000cdff  mov     ecx, eax
0x18000ce01  mov     rdx, rsi
0x18000ce04  call    DhcpMapJetError
0x18000ce09  mov     ebx, eax
0x18000ce0b  test    eax, eax
0x18000ce0d  jnz     loc_18000CF56
0x18000ce13  mov     r8, cs:DhcpGlobalClientTable
0x18000ce1a  lea     rax, aHardwareaddres_0; "+HardwareAddress"
0x18000ce21  mov     rdx, cs:DhcpGlobalClientTableHandle
0x18000ce28  mov     r9d, r15d
0x18000ce2b  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000ce32  mov     dword ptr [rsp+1A0h+var_170], edi
0x18000ce36  mov     r8, [r8+10h]
0x18000ce3a  mov     dword ptr [rsp+1A0h+var_178], 12h
0x18000ce42  mov     [rsp+1A0h+var_180], rax
0x18000ce47  call    cs:__imp_JetCreateIndex
0x18000ce4e  nop     dword ptr [rax+rax+00h]
0x18000ce53  mov     ecx, eax
0x18000ce55  mov     rdx, rsi
0x18000ce58  call    DhcpMapJetError
0x18000ce5d  mov     ebx, eax
0x18000ce5f  test    eax, eax
0x18000ce61  jnz     loc_18000CF56
0x18000ce67  mov     r8, cs:DhcpGlobalClientTable
0x18000ce6e  lea     rax, aMachinename; "+MachineName"
0x18000ce75  mov     rdx, cs:DhcpGlobalClientTableHandle
0x18000ce7c  lea     r9d, [rdi-2Ah]
0x18000ce80  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000ce87  mov     dword ptr [rsp+1A0h+var_170], edi
0x18000ce8b  mov     r8, [r8+40h]
0x18000ce8f  mov     dword ptr [rsp+1A0h+var_178], 0Eh
0x18000ce97  mov     [rsp+1A0h+var_180], rax
0x18000ce9c  call    cs:__imp_JetCreateIndex
0x18000cea3  nop     dword ptr [rax+rax+00h]
0x18000cea8  mov     ecx, eax
0x18000ceaa  mov     rdx, rsi
0x18000cead  call    DhcpMapJetError
0x18000ceb2  mov     ebx, eax
0x18000ceb4  test    eax, eax
0x18000ceb6  jnz     loc_18000CF56
0x18000cebc  call    CreateClientTableWin8Indices
0x18000cec1  mov     ebx, eax
0x18000cec3  test    eax, eax
0x18000cec5  jnz     loc_18000CF56
0x18000cecb  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18000ced2  call    DhcpOpenFilterDbTable
0x18000ced7  mov     ebx, eax
0x18000ced9  test    eax, eax
0x18000cedb  jnz     short loc_18000CF56
0x18000cedd  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000cee4  call    DhcpOpenFailoverDbTable
0x18000cee9  mov     ebx, eax
0x18000ceeb  test    eax, eax
0x18000ceed  jnz     short loc_18000CF56
0x18000ceef  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000cef6  call    DhcpFOOpenDeletedAddressTable
0x18000cefb  mov     ebx, eax
0x18000cefd  test    eax, eax
0x18000ceff  jnz     short loc_18000CF56
0x18000cf01  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000cf08  call    DhcpOpenFailoverBitmaskTable
0x18000cf0d  mov     ebx, eax
0x18000cf0f  test    eax, eax
0x18000cf11  jnz     short loc_18000CF56
0x18000cf13  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000cf1a  call    DhcpOpenMCastDbTable
0x18000cf1f  mov     ebx, eax
0x18000cf21  test    eax, eax
0x18000cf23  jnz     short loc_18000CF56
0x18000cf25  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf2c  lea     rax, WPP_GLOBAL_Control
0x18000cf33  cmp     rcx, rax
0x18000cf36  jz      short loc_18000CF8A
0x18000cf38  test    dword ptr [rcx+1Ch], 800h
0x18000cf3f  jz      short loc_18000CF8A
0x18000cf41  mov     rcx, [rcx+10h]
0x18000cf45  lea     edx, [rdi-22h]
0x18000cf48  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000cf4f  call    WPP_SF_
0x18000cf54  jmp     short loc_18000CF8A
0x18000cf56  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf5d  lea     rax, WPP_GLOBAL_Control
0x18000cf64  cmp     rcx, rax
0x18000cf67  jz      short loc_18000CF8A
0x18000cf69  test    dword ptr [rcx+1Ch], 800h
0x18000cf70  jz      short loc_18000CF8A
0x18000cf72  mov     rcx, [rcx+10h]
0x18000cf76  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000cf7d  mov     edx, 0Fh
0x18000cf82  mov     r9d, ebx
0x18000cf85  call    WPP_SF_D
0x18000cf8a  mov     eax, ebx
0x18000cf8c  mov     rcx, [rbp+0A0h+var_20]
0x18000cf93  xor     rcx, rsp; StackCookie
0x18000cf96  call    __security_check_cookie
0x18000cf9b  lea     r11, [rsp+1A0h+var_10]
0x18000cfa3  mov     rbx, [r11+20h]
0x18000cfa7  mov     rsi, [r11+28h]
0x18000cfab  mov     rdi, [r11+30h]
0x18000cfaf  mov     rsp, r11
0x18000cfb2  pop     r15
0x18000cfb4  pop     r14
0x18000cfb6  pop     rbp
0x18000cfb7  retn
```
