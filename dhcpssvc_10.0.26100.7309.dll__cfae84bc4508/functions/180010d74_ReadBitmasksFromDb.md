# ReadBitmasksFromDb

- ea: `0x180010d74`
- end: `0x180011195`
- name: `ReadBitmasksFromDb`
- size: `1057`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x18001119c`

## callees

- `0x18000323c`
- `0x18000ce5c`
- `0x18000f144`
- `0x1800109ec`
- `0x180010d74`
- `0x180011618`
- `0x180094650`
- `0x1800cc9e0`

## import_xrefs

- `ESENT!JetOpenTable` at `0x180010e03`
- `ESENT!JetOpenTable` at `0x180010e03`
- `ESENT!JetGetColumnInfo` at `0x180010e5b`
- `ESENT!JetGetColumnInfo` at `0x180010e5b`
- `ESENT!JetRetrieveColumn` at `0x180010f3c`
- `ESENT!JetRetrieveColumn` at `0x180010f8c`
- `ESENT!JetRetrieveColumn` at `0x180010fdc`
- `ESENT!JetRetrieveColumn` at `0x180011030`
- `ESENT!JetRetrieveColumn` at `0x180010f3c`
- `ESENT!JetRetrieveColumn` at `0x180010f8c`
- `ESENT!JetRetrieveColumn` at `0x180010fdc`
- `ESENT!JetRetrieveColumn` at `0x180011030`
- `ESENT!JetMove` at `0x180010eed`
- `ESENT!JetMove` at `0x18001111e`
- `ESENT!JetMove` at `0x180010eed`
- `ESENT!JetMove` at `0x18001111e`

## string_xrefs

- `0x180010e11`: `BitmaskOpenTable`
- `0x180010ef9`: `Bitmask move first`
- `0x18001112a`: `Bitmask Move next `

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
  unsigned int v8; // eax
  const char *i; // rdx
  unsigned int v10; // eax
  int v11; // eax
  unsigned int Column; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  __int64 Range; // rsi
  unsigned int v16; // r9d
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
  if ( v4 )
    return v4;
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
  if ( v4 )
    return v4;
  cbData.m256i_i32[0] = 2049;
  v22 = &v25;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids);
  v8 = JetMove(v0, BitmaskTbl, 0x80000000, 0);
  for ( i = "Bitmask move first"; ; i = "Bitmask Move next " )
  {
    v11 = DhcpMapJetError(v8, i);
    if ( v11 )
      break;
    pcbActual[0] = 0;
    v10 = JetRetrieveColumn(v0, BitmaskTbl, columnid, &pvData, 4u, pcbActual, 1u, 0);
    v11 = DhcpMapJetError(v10, "Bitmask Range");
    if ( v11 )
      break;
    Column = JetRetrieveColumn(v0, BitmaskTbl, dword_1800F6078, (char *)&pvData + 4, 4u, pcbActual, 1u, 0);
    v11 = DhcpMapJetError(Column, "Bitmask Offset");
    if ( v11 )
      break;
    v13 = JetRetrieveColumn(v0, BitmaskTbl, dword_1800F6088, &v21, 4u, pcbActual, 1u, 0);
    v11 = DhcpMapJetError(v13, "Bitmask Numbits");
    if ( v11 )
      break;
    v14 = JetRetrieveColumn(v0, BitmaskTbl, dword_1800F6068, v22, cbData.m256i_u32[0], pcbActual, 1u, 0);
    if ( v14 == 1004 )
    {
      v11 = 20013;
      break;
    }
    v11 = DhcpMapJetError(v14, "Bitmask Bitmap");
    if ( v11 )
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
      v11 = 4312;
      break;
    }
    v16 = v21;
    for ( j = 0; j < v16; ++j )
    {
      if ( (*((_BYTE *)v22 + ((unsigned __int64)j >> 3)) & byte_1800DD068[4 * (j & 7)]) != 0 )
      {
        MemBitSetOrClear(*(_QWORD *)(Range + 48), j + HIDWORD(pvData), 1, pcbActual);
        v16 = v21;
      }
    }
    v8 = JetMove(v0, BitmaskTbl, 1, 0);
  }
  if ( v11 != 259 )
    v2 = v11;
  CloseBitmaskTable(v0);
  return v2;
}

```

## disassembly

```asm
0x180010d74  mov     rax, rsp
0x180010d77  mov     [rax+8], rbx
0x180010d7b  mov     [rax+10h], rsi
0x180010d7f  mov     [rax+18h], rdi
0x180010d83  push    rbp
0x180010d84  push    r12
0x180010d86  push    r13
0x180010d88  push    r14
0x180010d8a  push    r15
0x180010d8c  lea     rbp, [rax-7D8h]
0x180010d93  sub     rsp, 8B0h
0x180010d9a  mov     rax, cs:__security_cookie
0x180010da1  xor     rax, rsp
0x180010da4  mov     [rbp+7D0h+var_30], rax
0x180010dab  mov     r14, cs:DhcpGlobalJetServerSession
0x180010db2  lea     r8, aBitmasktable; "BitmaskTable"
0x180010db9  mov     r15d, cs:DhcpGlobalDatabaseHandle
0x180010dc0  xor     eax, eax
0x180010dc2  xor     ebx, ebx
0x180010dc4  mov     [rsp+8D0h+var_858], rax
0x180010dc9  mov     [rbp+7D0h+var_850], eax
0x180010dcc  xorps   xmm0, xmm0
0x180010dcf  lea     rax, BitmaskTbl
0x180010dd6  mov     [rsp+8D0h+pvData], rbx
0x180010ddb  mov     qword ptr [rsp+8D0h+grbit], rax
0x180010de0  xor     r9d, r9d
0x180010de3  mov     dword ptr [rsp+8D0h+pcbActual], 4
0x180010deb  mov     edx, r15d
0x180010dee  mov     rcx, r14
0x180010df1  mov     [rsp+8D0h+cbData], ebx
0x180010df5  mov     [rsp+8D0h+var_880], rbx
0x180010dfa  mov     dword ptr [rsp+8D0h+var_870+4], ebx
0x180010dfe  movups  xmmword ptr [rsp+8D0h+var_870+8], xmm0
0x180010e03  call    cs:__imp_JetOpenTable
0x180010e0a  nop     dword ptr [rax+rax+00h]
0x180010e0f  mov     ecx, eax
0x180010e11  lea     rdx, aBitmaskopentab; "BitmaskOpenTable"
0x180010e18  call    DhcpMapJetError
0x180010e1d  mov     ecx, eax
0x180010e1f  test    eax, eax
0x180010e21  jnz     loc_180011162
0x180010e27  mov     esi, ebx
0x180010e29  lea     rdi, columnid
0x180010e30  lea     r12d, [rbx+1]
0x180010e34  mov     r9, [rdi-8]
0x180010e38  lea     rax, [rsp+8D0h+var_870+8]
0x180010e3d  mov     [rsp+8D0h+grbit], ebx
0x180010e41  lea     r8, aBitmasktable; "BitmaskTable"
0x180010e48  mov     dword ptr [rsp+8D0h+pcbActual], 1Ch
0x180010e50  mov     edx, r15d
0x180010e53  mov     rcx, r14
0x180010e56  mov     qword ptr [rsp+8D0h+cbData], rax
0x180010e5b  call    cs:__imp_JetGetColumnInfo
0x180010e62  nop     dword ptr [rax+rax+00h]
0x180010e67  mov     ecx, eax
0x180010e69  lea     rdx, aBitmaskGetcolu; "Bitmask: GetColumnInfo"
0x180010e70  call    DhcpMapJetError
0x180010e75  mov     ecx, eax
0x180010e77  test    eax, eax
0x180010e79  jnz     short loc_180010E8D
0x180010e7b  mov     eax, dword ptr [rsp+8D0h+var_870+0Ch]
0x180010e7f  add     esi, r12d
0x180010e82  mov     [rdi], eax
0x180010e84  add     rdi, 10h
0x180010e88  cmp     esi, 4
0x180010e8b  jb      short loc_180010E34
0x180010e8d  test    ecx, ecx
0x180010e8f  jnz     loc_180011162
0x180010e95  lea     rax, [rbp+7D0h+var_840]
0x180010e99  mov     dword ptr [rsp+8D0h+var_870], 801h
0x180010ea1  mov     [rsp+8D0h+var_878], rax
0x180010ea6  mov     rcx, cs:WPP_GLOBAL_Control
0x180010ead  lea     r13, WPP_GLOBAL_Control
0x180010eb4  mov     r15d, 10000000h
0x180010eba  cmp     rcx, r13
0x180010ebd  jz      short loc_180010EDA
0x180010ebf  test    [rcx+1Ch], r15d
0x180010ec3  jz      short loc_180010EDA
0x180010ec5  mov     rcx, [rcx+10h]
0x180010ec9  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x180010ed0  mov     edx, 74h ; 't'
0x180010ed5  call    WPP_SF_
0x180010eda  mov     rdx, cs:BitmaskTbl; tableid
0x180010ee1  xor     r9d, r9d; grbit
0x180010ee4  mov     r8d, 80000000h; cRow
0x180010eea  mov     rcx, r14; sesid
0x180010eed  call    cs:__imp_JetMove
0x180010ef4  nop     dword ptr [rax+rax+00h]
0x180010ef9  lea     rdx, aBitmaskMoveFir; "Bitmask move first"
0x180010f00  jmp     loc_180011131
0x180010f05  mov     r8d, cs:columnid; columnid
0x180010f0c  lea     rax, [rsp+8D0h+var_890]
0x180010f11  mov     rdx, cs:BitmaskTbl; tableid
0x180010f18  lea     r9, [rsp+8D0h+pvData]; pvData
0x180010f1d  mov     [rsp+8D0h+pretinfo], rbx; pretinfo
0x180010f22  mov     edi, 4
0x180010f27  mov     [rsp+8D0h+grbit], r12d; grbit
0x180010f2c  mov     rcx, r14; sesid
0x180010f2f  mov     [rsp+8D0h+pcbActual], rax; pcbActual
0x180010f34  mov     [rsp+8D0h+cbData], edi; cbData
0x180010f38  mov     [rsp+8D0h+var_890], ebx
0x180010f3c  call    cs:__imp_JetRetrieveColumn
0x180010f43  nop     dword ptr [rax+rax+00h]
0x180010f48  mov     ecx, eax
0x180010f4a  lea     rdx, aBitmaskRange; "Bitmask Range"
0x180010f51  call    DhcpMapJetError
0x180010f56  test    eax, eax
0x180010f58  jnz     loc_18001114E
0x180010f5e  mov     r8d, cs:dword_1800F6078; columnid
0x180010f65  lea     rax, [rsp+8D0h+var_890]
0x180010f6a  mov     rdx, cs:BitmaskTbl; tableid
0x180010f71  lea     r9, [rsp+8D0h+pvData+4]; pvData
0x180010f76  mov     [rsp+8D0h+pretinfo], rbx; pretinfo
0x180010f7b  mov     rcx, r14; sesid
0x180010f7e  mov     [rsp+8D0h+grbit], r12d; grbit
0x180010f83  mov     [rsp+8D0h+pcbActual], rax; pcbActual
0x180010f88  mov     [rsp+8D0h+cbData], edi; cbData
0x180010f8c  call    cs:__imp_JetRetrieveColumn
0x180010f93  nop     dword ptr [rax+rax+00h]
0x180010f98  mov     ecx, eax
0x180010f9a  lea     rdx, aBitmaskOffset; "Bitmask Offset"
0x180010fa1  call    DhcpMapJetError
0x180010fa6  test    eax, eax
0x180010fa8  jnz     loc_18001114E
0x180010fae  mov     r8d, cs:dword_1800F6088; columnid
0x180010fb5  lea     rax, [rsp+8D0h+var_890]
0x180010fba  mov     rdx, cs:BitmaskTbl; tableid
0x180010fc1  lea     r9, [rsp+8D0h+var_880]; pvData
0x180010fc6  mov     [rsp+8D0h+pretinfo], rbx; pretinfo
0x180010fcb  mov     rcx, r14; sesid
0x180010fce  mov     [rsp+8D0h+grbit], r12d; grbit
0x180010fd3  mov     [rsp+8D0h+pcbActual], rax; pcbActual
0x180010fd8  mov     [rsp+8D0h+cbData], edi; cbData
0x180010fdc  call    cs:__imp_JetRetrieveColumn
0x180010fe3  nop     dword ptr [rax+rax+00h]
0x180010fe8  mov     ecx, eax
0x180010fea  lea     rdx, aBitmaskNumbits; "Bitmask Numbits"
0x180010ff1  call    DhcpMapJetError
0x180010ff6  test    eax, eax
0x180010ff8  jnz     loc_18001114E
0x180010ffe  mov     r9, [rsp+8D0h+var_878]; pvData
0x180011003  lea     rax, [rsp+8D0h+var_890]
0x180011008  mov     r8d, cs:dword_1800F6068; columnid
0x18001100f  mov     rcx, r14; sesid
0x180011012  mov     rdx, cs:BitmaskTbl; tableid
0x180011019  mov     [rsp+8D0h+pretinfo], rbx; pretinfo
0x18001101e  mov     [rsp+8D0h+grbit], r12d; grbit
0x180011023  mov     [rsp+8D0h+pcbActual], rax; pcbActual
0x180011028  mov     eax, dword ptr [rsp+8D0h+var_870]
0x18001102c  mov     [rsp+8D0h+cbData], eax; cbData
0x180011030  call    cs:__imp_JetRetrieveColumn
0x180011037  nop     dword ptr [rax+rax+00h]
0x18001103c  cmp     eax, 3ECh
0x180011041  jz      loc_180011142
0x180011047  lea     rdx, aBitmaskBitmap; "Bitmask Bitmap"
0x18001104e  mov     ecx, eax
0x180011050  call    DhcpMapJetError
0x180011055  test    eax, eax
0x180011057  jnz     loc_18001114E
0x18001105d  mov     eax, [rsp+8D0h+var_890]
0x180011061  mov     dword ptr [rsp+8D0h+var_880+4], eax
0x180011065  test    eax, eax
0x180011067  jz      short loc_1800110A7
0x180011069  mov     rcx, cs:WPP_GLOBAL_Control
0x180011070  cmp     rcx, r13
0x180011073  jz      short loc_1800110A7
0x180011075  test    [rcx+1Ch], r15d
0x180011079  jz      short loc_1800110A7
0x18001107b  mov     r9d, dword ptr [rsp+8D0h+pvData]
0x180011080  lea     edx, [rdi+71h]
0x180011083  mov     rcx, [rcx+10h]
0x180011087  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18001108e  mov     [rsp+8D0h+grbit], eax
0x180011092  mov     eax, dword ptr [rsp+8D0h+var_880]
0x180011096  mov     dword ptr [rsp+8D0h+pcbActual], eax
0x18001109a  mov     eax, dword ptr [rsp+8D0h+pvData+4]
0x18001109e  mov     [rsp+8D0h+cbData], eax
0x1800110a2  call    WPP_SF_dddd
0x1800110a7  mov     ecx, dword ptr [rsp+8D0h+pvData]
0x1800110ab  call    GetRange
0x1800110b0  mov     rsi, rax
0x1800110b3  test    rax, rax
0x1800110b6  jz      loc_180011149
0x1800110bc  mov     r9d, dword ptr [rsp+8D0h+var_880]
0x1800110c1  mov     edi, ebx
0x1800110c3  test    r9d, r9d
0x1800110c6  jz      short loc_18001110E
0x1800110c8  mov     rax, [rsp+8D0h+var_878]
0x1800110cd  mov     r8d, edi
0x1800110d0  mov     ecx, edi
0x1800110d2  and     r8d, 7
0x1800110d6  shr     rcx, 3
0x1800110da  mov     dl, [rcx+rax]
0x1800110dd  lea     rax, byte_1800DD068
0x1800110e4  test    [rax+r8*4], dl
0x1800110e8  jz      short loc_180011106
0x1800110ea  mov     edx, dword ptr [rsp+8D0h+pvData+4]
0x1800110ee  lea     r9, [rsp+8D0h+var_890]
0x1800110f3  mov     rcx, [rsi+30h]
0x1800110f7  add     edx, edi
0x1800110f9  mov     r8d, r12d
0x1800110fc  call    MemBitSetOrClear
0x180011101  mov     r9d, dword ptr [rsp+8D0h+var_880]
0x180011106  add     edi, r12d
0x180011109  cmp     edi, r9d
0x18001110c  jb      short loc_1800110C8
0x18001110e  mov     rdx, cs:BitmaskTbl; tableid
0x180011115  xor     r9d, r9d; grbit
0x180011118  mov     r8d, r12d; cRow
0x18001111b  mov     rcx, r14; sesid
0x18001111e  call    cs:__imp_JetMove
0x180011125  nop     dword ptr [rax+rax+00h]
0x18001112a  lea     rdx, aBitmaskMoveNex; "Bitmask Move next "
0x180011131  mov     ecx, eax
0x180011133  call    DhcpMapJetError
0x180011138  test    eax, eax
0x18001113a  jz      loc_180010F05
0x180011140  jmp     short loc_18001114E
0x180011142  mov     eax, 4E2Dh
0x180011147  jmp     short loc_18001114E
0x180011149  mov     eax, 10D8h
0x18001114e  cmp     eax, 103h
0x180011153  mov     rcx, r14
0x180011156  cmovnz  ebx, eax
0x180011159  call    CloseBitmaskTable
0x18001115e  mov     eax, ebx
0x180011160  jmp     short loc_180011164
0x180011162  mov     eax, ecx
0x180011164  mov     rcx, [rbp+7D0h+var_30]
0x18001116b  xor     rcx, rsp; StackCookie
0x18001116e  call    __security_check_cookie
0x180011173  lea     r11, [rsp+8D0h+var_20]
0x18001117b  mov     rbx, [r11+30h]
0x18001117f  mov     rsi, [r11+38h]
0x180011183  mov     rdi, [r11+40h]
0x180011187  mov     rsp, r11
0x18001118a  pop     r15
0x18001118c  pop     r14
0x18001118e  pop     r13
0x180011190  pop     r12
0x180011192  pop     rbp
0x180011193  retn
```
