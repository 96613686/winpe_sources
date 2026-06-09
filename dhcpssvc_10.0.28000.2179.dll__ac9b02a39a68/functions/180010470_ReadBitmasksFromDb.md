# ReadBitmasksFromDb

- ea: `0x180010470`
- end: `0x180010895`
- name: `ReadBitmasksFromDb`
- size: `1061`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x18001089c`

## callees

- `0x180003228`
- `0x18000c504`
- `0x18000e814`
- `0x1800100dc`
- `0x180010470`
- `0x180010d2c`
- `0x1800948d0`
- `0x1800cdac0`

## import_xrefs

- `ESENT!JetOpenTable` at `0x1800104ff`
- `ESENT!JetOpenTable` at `0x1800104ff`
- `ESENT!JetGetColumnInfo` at `0x180010553`
- `ESENT!JetGetColumnInfo` at `0x180010553`
- `ESENT!JetRetrieveColumn` at `0x180010636`
- `ESENT!JetRetrieveColumn` at `0x18001068a`
- `ESENT!JetRetrieveColumn` at `0x1800106de`
- `ESENT!JetRetrieveColumn` at `0x180010732`
- `ESENT!JetRetrieveColumn` at `0x180010636`
- `ESENT!JetRetrieveColumn` at `0x18001068a`
- `ESENT!JetRetrieveColumn` at `0x1800106de`
- `ESENT!JetRetrieveColumn` at `0x180010732`
- `ESENT!JetMove` at `0x1800105e8`
- `ESENT!JetMove` at `0x180010822`
- `ESENT!JetMove` at `0x1800105e8`
- `ESENT!JetMove` at `0x180010822`

## string_xrefs

- `0x18001050d`: `BitmaskOpenTable`
- `0x1800105f4`: `Bitmask move first`
- `0x18001082e`: `Bitmask Move next `

## pseudocode

```c
__int64 ReadBitmasksFromDb()
{
  JET_SESID v0; // r14
  JET_DBID v1; // r15d
  unsigned int v2; // ebx
  unsigned int v3; // eax
  unsigned int v4; // ecx
  unsigned int v5; // esi
  JET_COLUMNID *v6; // rdi
  unsigned int ColumnInfo; // eax
  unsigned int v9; // eax
  const char *i; // rdx
  unsigned int v11; // eax
  int v12; // eax
  unsigned int Column; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  __int64 Range; // rsi
  unsigned int v17; // r9d
  unsigned int j; // edi
  unsigned int pcbActual[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 pvData; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v21; // [rsp+58h] [rbp-B0h] BYREF
  void *v22; // [rsp+60h] [rbp-A8h]
  __m256i cbData; // [rsp+68h] [rbp-A0h] BYREF
  int v24; // [rsp+88h] [rbp-80h]
  char v25; // [rsp+98h] [rbp-70h] BYREF

  v0 = DhcpGlobalJetServerSession;
  v1 = DhcpGlobalDatabaseHandle;
  v2 = 0;
  v24 = 0;
  pvData = 0;
  v21 = 0;
  memset((char *)cbData.m256i_i64 + 4, 0, 28);
  v3 = JetOpenTable(DhcpGlobalJetServerSession, DhcpGlobalDatabaseHandle, "BitmaskTable", 0, 0, 4, &BitmaskTbl);
  v4 = DhcpMapJetError(v3, "BitmaskOpenTable");
  if ( !v4 )
  {
    v5 = 0;
    v6 = &columnid;
    do
    {
      ColumnInfo = JetGetColumnInfo(v0, v1, "BitmaskTable", *((_QWORD *)v6 - 1), &cbData.m256i_u64[1], 28, 0);
      v4 = DhcpMapJetError(ColumnInfo, "Bitmask: GetColumnInfo");
      if ( v4 )
        break;
      ++v5;
      *v6 = cbData.m256i_u32[3];
      v6 += 4;
    }
    while ( v5 < 4 );
  }
  if ( v4 )
    return v4;
  cbData.m256i_i32[0] = 2049;
  v22 = &v25;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids);
  v9 = JetMove(v0, BitmaskTbl, 0x80000000, 0);
  for ( i = "Bitmask move first"; ; i = "Bitmask Move next " )
  {
    v12 = DhcpMapJetError(v9, i);
    if ( v12 )
      break;
    pcbActual[0] = 0;
    v11 = JetRetrieveColumn(v0, BitmaskTbl, columnid, &pvData, 4u, pcbActual, 1u, 0);
    v12 = DhcpMapJetError(v11, "Bitmask Range");
    if ( v12 )
      break;
    Column = JetRetrieveColumn(v0, BitmaskTbl, dword_1800F8078, (char *)&pvData + 4, 4u, pcbActual, 1u, 0);
    v12 = DhcpMapJetError(Column, "Bitmask Offset");
    if ( v12 )
      break;
    v14 = JetRetrieveColumn(v0, BitmaskTbl, dword_1800F8088, &v21, 4u, pcbActual, 1u, 0);
    v12 = DhcpMapJetError(v14, "Bitmask Numbits");
    if ( v12 )
      break;
    v15 = JetRetrieveColumn(v0, BitmaskTbl, dword_1800F8068, v22, cbData.m256i_u32[0], pcbActual, 1u, 0);
    if ( v15 == 1004 )
    {
      v12 = 20013;
      break;
    }
    v12 = DhcpMapJetError(v15, "Bitmask Bitmap");
    if ( v12 )
      break;
    HIDWORD(v21) = pcbActual[0];
    if ( pcbActual[0]
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    {
      WPP_SF_dddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        117,
        &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids,
        (unsigned int)pvData,
        HIDWORD(pvData),
        v21,
        pcbActual[0]);
    }
    Range = GetRange((unsigned int)pvData);
    if ( !Range )
    {
      v12 = 4312;
      break;
    }
    v17 = v21;
    for ( j = 0; j < v17; ++j )
    {
      if ( (*((_BYTE *)v22 + ((unsigned __int64)j >> 3)) & byte_1800DF008[4 * (j & 7)]) != 0 )
      {
        MemBitSetOrClear(*(_QWORD *)(Range + 48), j + HIDWORD(pvData), 1, pcbActual);
        v17 = v21;
      }
    }
    v9 = JetMove(v0, BitmaskTbl, 1, 0);
  }
  if ( v12 != 259 )
    v2 = v12;
  CloseBitmaskTable(v0);
  return v2;
}

```

## disassembly

```asm
0x180010470  mov     rax, rsp
0x180010473  mov     [rax+8], rbx
0x180010477  mov     [rax+10h], rsi
0x18001047b  mov     [rax+18h], rdi
0x18001047f  push    rbp
0x180010480  push    r12
0x180010482  push    r13
0x180010484  push    r14
0x180010486  push    r15
0x180010488  lea     rbp, [rax-7D8h]
0x18001048f  sub     rsp, 8B0h
0x180010496  mov     rax, cs:__security_cookie
0x18001049d  xor     rax, rsp
0x1800104a0  mov     [rbp+7D0h+var_30], rax
0x1800104a7  mov     r14, cs:DhcpGlobalJetServerSession
0x1800104ae  lea     r8, aBitmasktable; "BitmaskTable"
0x1800104b5  mov     r15d, cs:DhcpGlobalDatabaseHandle
0x1800104bc  xor     eax, eax
0x1800104be  xor     ebx, ebx
0x1800104c0  mov     [rsp+8D0h+var_858], rax
0x1800104c5  mov     [rbp+7D0h+var_850], eax
0x1800104c8  xorps   xmm0, xmm0
0x1800104cb  lea     rax, BitmaskTbl
0x1800104d2  mov     [rsp+8D0h+pvData], rbx
0x1800104d7  mov     qword ptr [rsp+8D0h+grbit], rax
0x1800104dc  xor     r9d, r9d
0x1800104df  mov     dword ptr [rsp+8D0h+pcbActual], 4
0x1800104e7  mov     edx, r15d
0x1800104ea  mov     rcx, r14
0x1800104ed  mov     [rsp+8D0h+cbData], ebx
0x1800104f1  mov     [rsp+8D0h+var_880], rbx
0x1800104f6  mov     dword ptr [rsp+8D0h+var_870+4], ebx
0x1800104fa  movups  xmmword ptr [rsp+8D0h+var_870+8], xmm0
0x1800104ff  call    cs:__imp_JetOpenTable
0x180010506  nop     dword ptr [rax+rax+00h]
0x18001050b  mov     ecx, eax
0x18001050d  lea     rdx, aBitmaskopentab; "BitmaskOpenTable"
0x180010514  call    DhcpMapJetError
0x180010519  lea     r12d, [rbx+1]
0x18001051d  mov     ecx, eax
0x18001051f  test    eax, eax
0x180010521  jnz     short loc_180010585
0x180010523  mov     esi, ebx
0x180010525  lea     rdi, columnid
0x18001052c  mov     r9, [rdi-8]
0x180010530  lea     rax, [rsp+8D0h+var_870+8]
0x180010535  mov     [rsp+8D0h+grbit], ebx
0x180010539  lea     r8, aBitmasktable; "BitmaskTable"
0x180010540  mov     dword ptr [rsp+8D0h+pcbActual], 1Ch
0x180010548  mov     edx, r15d
0x18001054b  mov     rcx, r14
0x18001054e  mov     qword ptr [rsp+8D0h+cbData], rax
0x180010553  call    cs:__imp_JetGetColumnInfo
0x18001055a  nop     dword ptr [rax+rax+00h]
0x18001055f  mov     ecx, eax
0x180010561  lea     rdx, aBitmaskGetcolu; "Bitmask: GetColumnInfo"
0x180010568  call    DhcpMapJetError
0x18001056d  mov     ecx, eax
0x18001056f  test    eax, eax
0x180010571  jnz     short loc_180010585
0x180010573  mov     eax, dword ptr [rsp+8D0h+var_870+0Ch]
0x180010577  add     esi, r12d
0x18001057a  mov     [rdi], eax
0x18001057c  add     rdi, 10h
0x180010580  cmp     esi, 4
0x180010583  jb      short loc_18001052C
0x180010585  test    ecx, ecx
0x180010587  jz      short loc_180010590
0x180010589  mov     eax, ecx
0x18001058b  jmp     loc_180010864
0x180010590  lea     rax, [rbp+7D0h+var_840]
0x180010594  mov     dword ptr [rsp+8D0h+var_870], 801h
0x18001059c  mov     [rsp+8D0h+var_878], rax
0x1800105a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800105a8  lea     r13, WPP_GLOBAL_Control
0x1800105af  mov     r15d, 10000000h
0x1800105b5  cmp     rcx, r13
0x1800105b8  jz      short loc_1800105D5
0x1800105ba  test    [rcx+1Ch], r15d
0x1800105be  jz      short loc_1800105D5
0x1800105c0  mov     rcx, [rcx+10h]
0x1800105c4  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x1800105cb  mov     edx, 74h ; 't'
0x1800105d0  call    WPP_SF_
0x1800105d5  mov     rdx, cs:BitmaskTbl; tableid
0x1800105dc  xor     r9d, r9d; grbit
0x1800105df  mov     r8d, 80000000h; cRow
0x1800105e5  mov     rcx, r14; sesid
0x1800105e8  call    cs:__imp_JetMove
0x1800105ef  nop     dword ptr [rax+rax+00h]
0x1800105f4  lea     rdx, aBitmaskMoveFir; "Bitmask move first"
0x1800105fb  jmp     loc_180010835
0x180010600  mov     r8d, cs:columnid; columnid
0x180010607  lea     rax, [rsp+8D0h+var_890]
0x18001060c  mov     rdx, cs:BitmaskTbl; tableid
0x180010613  lea     r9, [rsp+8D0h+pvData]; pvData
0x180010618  mov     [rsp+8D0h+pretinfo], rbx; pretinfo
0x18001061d  mov     rcx, r14; sesid
0x180010620  mov     [rsp+8D0h+grbit], r12d; grbit
0x180010625  mov     [rsp+8D0h+pcbActual], rax; pcbActual
0x18001062a  mov     [rsp+8D0h+cbData], 4; cbData
0x180010632  mov     [rsp+8D0h+var_890], ebx
0x180010636  call    cs:__imp_JetRetrieveColumn
0x18001063d  nop     dword ptr [rax+rax+00h]
0x180010642  mov     ecx, eax
0x180010644  lea     rdx, aBitmaskRange; "Bitmask Range"
0x18001064b  call    DhcpMapJetError
0x180010650  test    eax, eax
0x180010652  jnz     loc_180010852
0x180010658  mov     r8d, cs:dword_1800F8078; columnid
0x18001065f  lea     rax, [rsp+8D0h+var_890]
0x180010664  mov     rdx, cs:BitmaskTbl; tableid
0x18001066b  lea     r9, [rsp+8D0h+pvData+4]; pvData
0x180010670  mov     [rsp+8D0h+pretinfo], rbx; pretinfo
0x180010675  mov     rcx, r14; sesid
0x180010678  mov     [rsp+8D0h+grbit], r12d; grbit
0x18001067d  mov     [rsp+8D0h+pcbActual], rax; pcbActual
0x180010682  mov     [rsp+8D0h+cbData], 4; cbData
0x18001068a  call    cs:__imp_JetRetrieveColumn
0x180010691  nop     dword ptr [rax+rax+00h]
0x180010696  mov     ecx, eax
0x180010698  lea     rdx, aBitmaskOffset; "Bitmask Offset"
0x18001069f  call    DhcpMapJetError
0x1800106a4  test    eax, eax
0x1800106a6  jnz     loc_180010852
0x1800106ac  mov     r8d, cs:dword_1800F8088; columnid
0x1800106b3  lea     rax, [rsp+8D0h+var_890]
0x1800106b8  mov     rdx, cs:BitmaskTbl; tableid
0x1800106bf  lea     r9, [rsp+8D0h+var_880]; pvData
0x1800106c4  mov     [rsp+8D0h+pretinfo], rbx; pretinfo
0x1800106c9  mov     rcx, r14; sesid
0x1800106cc  mov     [rsp+8D0h+grbit], r12d; grbit
0x1800106d1  mov     [rsp+8D0h+pcbActual], rax; pcbActual
0x1800106d6  mov     [rsp+8D0h+cbData], 4; cbData
0x1800106de  call    cs:__imp_JetRetrieveColumn
0x1800106e5  nop     dword ptr [rax+rax+00h]
0x1800106ea  mov     ecx, eax
0x1800106ec  lea     rdx, aBitmaskNumbits; "Bitmask Numbits"
0x1800106f3  call    DhcpMapJetError
0x1800106f8  test    eax, eax
0x1800106fa  jnz     loc_180010852
0x180010700  mov     r9, [rsp+8D0h+var_878]; pvData
0x180010705  lea     rax, [rsp+8D0h+var_890]
0x18001070a  mov     r8d, cs:dword_1800F8068; columnid
0x180010711  mov     rcx, r14; sesid
0x180010714  mov     rdx, cs:BitmaskTbl; tableid
0x18001071b  mov     [rsp+8D0h+pretinfo], rbx; pretinfo
0x180010720  mov     [rsp+8D0h+grbit], r12d; grbit
0x180010725  mov     [rsp+8D0h+pcbActual], rax; pcbActual
0x18001072a  mov     eax, dword ptr [rsp+8D0h+var_870]
0x18001072e  mov     [rsp+8D0h+cbData], eax; cbData
0x180010732  call    cs:__imp_JetRetrieveColumn
0x180010739  nop     dword ptr [rax+rax+00h]
0x18001073e  cmp     eax, 3ECh
0x180010743  jz      loc_180010846
0x180010749  lea     rdx, aBitmaskBitmap; "Bitmask Bitmap"
0x180010750  mov     ecx, eax
0x180010752  call    DhcpMapJetError
0x180010757  test    eax, eax
0x180010759  jnz     loc_180010852
0x18001075f  mov     eax, [rsp+8D0h+var_890]
0x180010763  mov     dword ptr [rsp+8D0h+var_880+4], eax
0x180010767  test    eax, eax
0x180010769  jz      short loc_1800107AB
0x18001076b  mov     rcx, cs:WPP_GLOBAL_Control
0x180010772  cmp     rcx, r13
0x180010775  jz      short loc_1800107AB
0x180010777  test    [rcx+1Ch], r15d
0x18001077b  jz      short loc_1800107AB
0x18001077d  mov     r9d, dword ptr [rsp+8D0h+pvData]
0x180010782  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x180010789  mov     rcx, [rcx+10h]
0x18001078d  mov     edx, 75h ; 'u'
0x180010792  mov     [rsp+8D0h+grbit], eax
0x180010796  mov     eax, dword ptr [rsp+8D0h+var_880]
0x18001079a  mov     dword ptr [rsp+8D0h+pcbActual], eax
0x18001079e  mov     eax, dword ptr [rsp+8D0h+pvData+4]
0x1800107a2  mov     [rsp+8D0h+cbData], eax
0x1800107a6  call    WPP_SF_dddd
0x1800107ab  mov     ecx, dword ptr [rsp+8D0h+pvData]
0x1800107af  call    GetRange
0x1800107b4  mov     rsi, rax
0x1800107b7  test    rax, rax
0x1800107ba  jz      loc_18001084D
0x1800107c0  mov     r9d, dword ptr [rsp+8D0h+var_880]
0x1800107c5  mov     edi, ebx
0x1800107c7  test    r9d, r9d
0x1800107ca  jz      short loc_180010812
0x1800107cc  mov     rax, [rsp+8D0h+var_878]
0x1800107d1  mov     r8d, edi
0x1800107d4  mov     ecx, edi
0x1800107d6  and     r8d, 7
0x1800107da  shr     rcx, 3
0x1800107de  mov     dl, [rcx+rax]
0x1800107e1  lea     rax, byte_1800DF008
0x1800107e8  test    [rax+r8*4], dl
0x1800107ec  jz      short loc_18001080A
0x1800107ee  mov     edx, dword ptr [rsp+8D0h+pvData+4]
0x1800107f2  lea     r9, [rsp+8D0h+var_890]
0x1800107f7  mov     rcx, [rsi+30h]
0x1800107fb  add     edx, edi
0x1800107fd  mov     r8d, r12d
0x180010800  call    MemBitSetOrClear
0x180010805  mov     r9d, dword ptr [rsp+8D0h+var_880]
0x18001080a  add     edi, r12d
0x18001080d  cmp     edi, r9d
0x180010810  jb      short loc_1800107CC
0x180010812  mov     rdx, cs:BitmaskTbl; tableid
0x180010819  xor     r9d, r9d; grbit
0x18001081c  mov     r8d, r12d; cRow
0x18001081f  mov     rcx, r14; sesid
0x180010822  call    cs:__imp_JetMove
0x180010829  nop     dword ptr [rax+rax+00h]
0x18001082e  lea     rdx, aBitmaskMoveNex; "Bitmask Move next "
0x180010835  mov     ecx, eax
0x180010837  call    DhcpMapJetError
0x18001083c  test    eax, eax
0x18001083e  jz      loc_180010600
0x180010844  jmp     short loc_180010852
0x180010846  mov     eax, 4E2Dh
0x18001084b  jmp     short loc_180010852
0x18001084d  mov     eax, 10D8h
0x180010852  cmp     eax, 103h
0x180010857  mov     rcx, r14
0x18001085a  cmovnz  ebx, eax
0x18001085d  call    CloseBitmaskTable
0x180010862  mov     eax, ebx
0x180010864  mov     rcx, [rbp+7D0h+var_30]
0x18001086b  xor     rcx, rsp; StackCookie
0x18001086e  call    __security_check_cookie
0x180010873  lea     r11, [rsp+8D0h+var_20]
0x18001087b  mov     rbx, [r11+30h]
0x18001087f  mov     rsi, [r11+38h]
0x180010883  mov     rdi, [r11+40h]
0x180010887  mov     rsp, r11
0x18001088a  pop     r15
0x18001088c  pop     r14
0x18001088e  pop     r13
0x180010890  pop     r12
0x180010892  pop     rbp
0x180010893  retn
```
