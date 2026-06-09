# OpenBitmaskCleanFlagTable

- ea: `0x1800102d0`
- end: `0x18001046a`
- name: `OpenBitmaskCleanFlagTable`
- size: `410`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001016c`
- `0x18001089c`

## callees

- `0x18000e814`
- `0x1800102d0`
- `0x1800cdac0`

## import_xrefs

- `ESENT!JetOpenTable` at `0x18001032d`
- `ESENT!JetOpenTable` at `0x18001032d`
- `ESENT!JetGetColumnInfo` at `0x180010420`
- `ESENT!JetGetColumnInfo` at `0x180010420`
- `ESENT!JetCreateTable` at `0x180010374`
- `ESENT!JetCreateTable` at `0x180010374`
- `ESENT!JetAddColumn` at `0x1800103e6`
- `ESENT!JetAddColumn` at `0x1800103e6`

## string_xrefs

- `0x18001033b`: `Bitmask clean table open`
- `0x180010382`: `Create bitmask clean table`

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
0x1800102d0  mov     [rsp-8+arg_0], rbx
0x1800102d5  mov     [rsp-8+arg_8], rsi
0x1800102da  push    rbp
0x1800102db  mov     rbp, rsp
0x1800102de  sub     rsp, 70h
0x1800102e2  mov     rax, cs:__security_cookie
0x1800102e9  xor     rax, rsp
0x1800102ec  mov     [rbp+var_10], rax
0x1800102f0  mov     edx, cs:DhcpGlobalDatabaseHandle
0x1800102f6  lea     rsi, BitmaskCleanFlagTbl
0x1800102fd  mov     rcx, cs:DhcpGlobalJetServerSession
0x180010304  lea     r8, aBitmaskcleanta; "BitmaskCleanTable"
0x18001030b  xor     eax, eax
0x18001030d  mov     [rsp+70h+var_40], rsi
0x180010312  xor     ebx, ebx
0x180010314  mov     [rbp+var_20], rax
0x180010318  xorps   xmm0, xmm0
0x18001031b  mov     dword ptr [rsp+70h+var_48], ebx
0x18001031f  xor     r9d, r9d
0x180010322  mov     dword ptr [rsp+70h+var_50], ebx
0x180010326  movups  [rbp+var_30], xmm0
0x18001032a  mov     [rbp+var_18], eax
0x18001032d  call    cs:__imp_JetOpenTable
0x180010334  nop     dword ptr [rax+rax+00h]
0x180010339  mov     ecx, eax
0x18001033b  lea     rdx, aBitmaskCleanTa; "Bitmask clean table open"
0x180010342  call    DhcpMapJetError
0x180010347  mov     edx, cs:DhcpGlobalDatabaseHandle
0x18001034d  lea     r8, aBitmaskcleanta; "BitmaskCleanTable"
0x180010354  mov     rcx, cs:DhcpGlobalJetServerSession
0x18001035b  test    eax, eax
0x18001035d  jz      loc_180010404
0x180010363  mov     [rsp+70h+var_48], rsi
0x180010368  lea     r9d, [rbx+0Ah]
0x18001036c  mov     dword ptr [rsp+70h+var_50], 50h ; 'P'
0x180010374  call    cs:__imp_JetCreateTable
0x18001037b  nop     dword ptr [rax+rax+00h]
0x180010380  mov     ecx, eax
0x180010382  lea     rdx, aCreateBitmaskC; "Create bitmask clean table"
0x180010389  call    DhcpMapJetError
0x18001038e  test    eax, eax
0x180010390  jnz     loc_18001044B
0x180010396  mov     rdx, cs:BitmaskCleanFlagTbl
0x18001039d  lea     r9, [rbp+var_30]
0x1800103a1  mov     rcx, cs:DhcpGlobalJetServerSession
0x1800103a8  lea     r8, aBitmaskclean; "BitmaskClean"
0x1800103af  mov     eax, 409h
0x1800103b4  mov     qword ptr [rbp+var_30], 1Ch
0x1800103bc  mov     word ptr [rbp+var_30+0Ch], ax
0x1800103c0  lea     rax, BitmaskCleanFlagColId
0x1800103c7  mov     [rsp+70h+var_40], rax
0x1800103cc  mov     dword ptr [rsp+70h+var_48], ebx
0x1800103d0  mov     [rsp+70h+var_50], rbx
0x1800103d5  mov     dword ptr [rbp+var_20], 4E4h
0x1800103dc  mov     [rbp+var_18], ebx
0x1800103df  mov     dword ptr [rbp+var_30+8], 2
0x1800103e6  call    cs:__imp_JetAddColumn
0x1800103ed  nop     dword ptr [rax+rax+00h]
0x1800103f2  mov     ecx, eax
0x1800103f4  lea     rdx, aBitmaskCleanAd; "Bitmask clean add column"
0x1800103fb  call    DhcpMapJetError
0x180010400  mov     ecx, eax
0x180010402  jmp     short loc_180010449
0x180010404  mov     dword ptr [rsp+70h+var_40], ebx
0x180010408  lea     rax, [rbp+var_30]
0x18001040c  mov     dword ptr [rsp+70h+var_48], 1Ch
0x180010414  lea     r9, aBitmaskclean; "BitmaskClean"
0x18001041b  mov     [rsp+70h+var_50], rax
0x180010420  call    cs:__imp_JetGetColumnInfo
0x180010427  nop     dword ptr [rax+rax+00h]
0x18001042c  mov     ecx, eax
0x18001042e  lea     rdx, aGetColumnInfoB; "Get column info: bitmask clean flag"
0x180010435  call    DhcpMapJetError
0x18001043a  mov     ecx, eax
0x18001043c  test    eax, eax
0x18001043e  jnz     short loc_18001044B
0x180010440  mov     eax, dword ptr [rbp+var_30+4]
0x180010443  mov     cs:BitmaskCleanFlagColId, eax
0x180010449  mov     eax, ecx
0x18001044b  mov     rcx, [rbp+var_10]
0x18001044f  xor     rcx, rsp; StackCookie
0x180010452  call    __security_check_cookie
0x180010457  lea     r11, [rsp+70h+var_s0]
0x18001045c  mov     rbx, [r11+10h]
0x180010460  mov     rsi, [r11+18h]
0x180010464  mov     rsp, r11
0x180010467  pop     rbp
0x180010468  retn
```
