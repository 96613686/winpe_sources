# OpenBitmaskCleanFlagTable

- ea: `0x180010bd4`
- end: `0x180010d6e`
- name: `OpenBitmaskCleanFlagTable`
- size: `410`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180010a70`
- `0x18001119c`

## callees

- `0x18000f144`
- `0x180010bd4`
- `0x1800cc9e0`

## import_xrefs

- `ESENT!JetOpenTable` at `0x180010c31`
- `ESENT!JetOpenTable` at `0x180010c31`
- `ESENT!JetGetColumnInfo` at `0x180010d24`
- `ESENT!JetGetColumnInfo` at `0x180010d24`
- `ESENT!JetCreateTable` at `0x180010c78`
- `ESENT!JetCreateTable` at `0x180010c78`
- `ESENT!JetAddColumn` at `0x180010cea`
- `ESENT!JetAddColumn` at `0x180010cea`

## string_xrefs

- `0x180010c3f`: `Bitmask clean table open`
- `0x180010c86`: `Create bitmask clean table`

## pseudocode

```c
__int64 OpenBitmaskCleanFlagTable()
{
  unsigned int v0; // eax
  unsigned int Table; // eax
  __int64 result; // rax
  unsigned int v3; // eax
  unsigned int v4; // ecx
  unsigned int ColumnInfo; // eax
  __int128 v6; // [rsp+40h] [rbp-30h] BYREF
  __int64 v7; // [rsp+50h] [rbp-20h]
  int v8; // [rsp+58h] [rbp-18h]

  v7 = 0;
  v6 = 0;
  v8 = 0;
  v0 = JetOpenTable(
         DhcpGlobalJetServerSession,
         DhcpGlobalDatabaseHandle,
         "BitmaskCleanTable",
         0,
         0,
         0,
         &BitmaskCleanFlagTbl);
  if ( (unsigned int)DhcpMapJetError(v0, "Bitmask clean table open") )
  {
    Table = JetCreateTable(
              DhcpGlobalJetServerSession,
              DhcpGlobalDatabaseHandle,
              "BitmaskCleanTable",
              10,
              80,
              &BitmaskCleanFlagTbl);
    result = DhcpMapJetError(Table, "Create bitmask clean table");
    if ( (_DWORD)result )
      return result;
    *(_QWORD *)&v6 = 28;
    WORD6(v6) = 1033;
    LODWORD(v7) = 1252;
    v8 = 0;
    DWORD2(v6) = 2;
    v3 = JetAddColumn(
           DhcpGlobalJetServerSession,
           BitmaskCleanFlagTbl,
           "BitmaskClean",
           &v6,
           0,
           0,
           &BitmaskCleanFlagColId);
    return (unsigned int)DhcpMapJetError(v3, "Bitmask clean add column");
  }
  else
  {
    ColumnInfo = JetGetColumnInfo(
                   DhcpGlobalJetServerSession,
                   DhcpGlobalDatabaseHandle,
                   "BitmaskCleanTable",
                   "BitmaskClean",
                   &v6,
                   28,
                   0);
    result = DhcpMapJetError(ColumnInfo, "Get column info: bitmask clean flag");
    v4 = result;
    if ( (_DWORD)result )
      return result;
    BitmaskCleanFlagColId = DWORD1(v6);
  }
  return v4;
}

```

## disassembly

```asm
0x180010bd4  mov     [rsp-8+arg_0], rbx
0x180010bd9  mov     [rsp-8+arg_8], rsi
0x180010bde  push    rbp
0x180010bdf  mov     rbp, rsp
0x180010be2  sub     rsp, 70h
0x180010be6  mov     rax, cs:__security_cookie
0x180010bed  xor     rax, rsp
0x180010bf0  mov     [rbp+var_10], rax
0x180010bf4  mov     edx, cs:DhcpGlobalDatabaseHandle
0x180010bfa  lea     rsi, BitmaskCleanFlagTbl
0x180010c01  mov     rcx, cs:DhcpGlobalJetServerSession
0x180010c08  lea     r8, aBitmaskcleanta; "BitmaskCleanTable"
0x180010c0f  xor     eax, eax
0x180010c11  mov     [rsp+70h+var_40], rsi
0x180010c16  xor     ebx, ebx
0x180010c18  mov     [rbp+var_20], rax
0x180010c1c  xorps   xmm0, xmm0
0x180010c1f  mov     dword ptr [rsp+70h+var_48], ebx
0x180010c23  xor     r9d, r9d
0x180010c26  mov     dword ptr [rsp+70h+var_50], ebx
0x180010c2a  movups  [rbp+var_30], xmm0
0x180010c2e  mov     [rbp+var_18], eax
0x180010c31  call    cs:__imp_JetOpenTable
0x180010c38  nop     dword ptr [rax+rax+00h]
0x180010c3d  mov     ecx, eax
0x180010c3f  lea     rdx, aBitmaskCleanTa; "Bitmask clean table open"
0x180010c46  call    DhcpMapJetError
0x180010c4b  mov     edx, cs:DhcpGlobalDatabaseHandle
0x180010c51  lea     r8, aBitmaskcleanta; "BitmaskCleanTable"
0x180010c58  mov     rcx, cs:DhcpGlobalJetServerSession
0x180010c5f  test    eax, eax
0x180010c61  jz      loc_180010D08
0x180010c67  mov     [rsp+70h+var_48], rsi
0x180010c6c  lea     r9d, [rbx+0Ah]
0x180010c70  mov     dword ptr [rsp+70h+var_50], 50h ; 'P'
0x180010c78  call    cs:__imp_JetCreateTable
0x180010c7f  nop     dword ptr [rax+rax+00h]
0x180010c84  mov     ecx, eax
0x180010c86  lea     rdx, aCreateBitmaskC; "Create bitmask clean table"
0x180010c8d  call    DhcpMapJetError
0x180010c92  test    eax, eax
0x180010c94  jnz     loc_180010D4F
0x180010c9a  mov     rdx, cs:BitmaskCleanFlagTbl
0x180010ca1  lea     r9, [rbp+var_30]
0x180010ca5  mov     rcx, cs:DhcpGlobalJetServerSession
0x180010cac  lea     r8, aBitmaskclean; "BitmaskClean"
0x180010cb3  mov     eax, 409h
0x180010cb8  mov     qword ptr [rbp+var_30], 1Ch
0x180010cc0  mov     word ptr [rbp+var_30+0Ch], ax
0x180010cc4  lea     rax, BitmaskCleanFlagColId
0x180010ccb  mov     [rsp+70h+var_40], rax
0x180010cd0  mov     dword ptr [rsp+70h+var_48], ebx
0x180010cd4  mov     [rsp+70h+var_50], rbx
0x180010cd9  mov     dword ptr [rbp+var_20], 4E4h
0x180010ce0  mov     [rbp+var_18], ebx
0x180010ce3  mov     dword ptr [rbp+var_30+8], 2
0x180010cea  call    cs:__imp_JetAddColumn
0x180010cf1  nop     dword ptr [rax+rax+00h]
0x180010cf6  mov     ecx, eax
0x180010cf8  lea     rdx, aBitmaskCleanAd; "Bitmask clean add column"
0x180010cff  call    DhcpMapJetError
0x180010d04  mov     ecx, eax
0x180010d06  jmp     short loc_180010D4D
0x180010d08  mov     dword ptr [rsp+70h+var_40], ebx
0x180010d0c  lea     rax, [rbp+var_30]
0x180010d10  mov     dword ptr [rsp+70h+var_48], 1Ch
0x180010d18  lea     r9, aBitmaskclean; "BitmaskClean"
0x180010d1f  mov     [rsp+70h+var_50], rax
0x180010d24  call    cs:__imp_JetGetColumnInfo
0x180010d2b  nop     dword ptr [rax+rax+00h]
0x180010d30  mov     ecx, eax
0x180010d32  lea     rdx, aGetColumnInfoB; "Get column info: bitmask clean flag"
0x180010d39  call    DhcpMapJetError
0x180010d3e  mov     ecx, eax
0x180010d40  test    eax, eax
0x180010d42  jnz     short loc_180010D4F
0x180010d44  mov     eax, dword ptr [rbp+var_30+4]
0x180010d47  mov     cs:BitmaskCleanFlagColId, eax
0x180010d4d  mov     eax, ecx
0x180010d4f  mov     rcx, [rbp+var_10]
0x180010d53  xor     rcx, rsp; StackCookie
0x180010d56  call    __security_check_cookie
0x180010d5b  lea     r11, [rsp+70h+var_s0]
0x180010d60  mov     rbx, [r11+10h]
0x180010d64  mov     rsi, [r11+18h]
0x180010d68  mov     rsp, r11
0x180010d6b  pop     rbp
0x180010d6c  retn
```
