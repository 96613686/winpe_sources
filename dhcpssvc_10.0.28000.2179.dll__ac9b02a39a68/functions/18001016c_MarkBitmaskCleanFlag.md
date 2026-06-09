# MarkBitmaskCleanFlag

- ea: `0x18001016c`
- end: `0x1800102ca`
- name: `MarkBitmaskCleanFlag`
- size: `350`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18000fedc`
- `0x18001089c`

## callees

- `0x18000e814`
- `0x18001016c`
- `0x1800102d0`

## import_xrefs

- `ESENT!JetCloseTable` at `0x1800102ab`
- `ESENT!JetCloseTable` at `0x1800102ab`
- `ESENT!JetUpdate` at `0x18001025b`
- `ESENT!JetUpdate` at `0x18001025b`
- `ESENT!JetPrepareUpdate` at `0x1800101e7`
- `ESENT!JetPrepareUpdate` at `0x180010291`
- `ESENT!JetPrepareUpdate` at `0x1800101e7`
- `ESENT!JetPrepareUpdate` at `0x180010291`
- `ESENT!JetSetColumn` at `0x180010236`
- `ESENT!JetSetColumn` at `0x180010236`
- `ESENT!JetMove` at `0x1800101a2`
- `ESENT!JetMove` at `0x1800101a2`

## string_xrefs

- `0x1800101b0`: `Bitmask flag jetmove`
- `0x1800101f5`: `Bitmask clean prepare update`
- `0x180010269`: `Jet update`

## pseudocode

```c
__int64 __fastcall MarkBitmaskCleanFlag(char a1)
{
  __int64 result; // rax
  unsigned int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // edi
  unsigned int v5; // r8d
  unsigned int v6; // eax
  unsigned int v7; // ebx
  char pvData; // [rsp+50h] [rbp+8h] BYREF

  pvData = a1;
  result = OpenBitmaskCleanFlagTable();
  if ( !(_DWORD)result )
  {
    v2 = JetMove(DhcpGlobalJetServerSession, BitmaskCleanFlagTbl, 0, 0);
    v3 = DhcpMapJetError(v2, "Bitmask flag jetmove");
    v4 = v3;
    if ( v3 == 259 || !v3 )
    {
      v5 = 2;
      if ( v3 )
        v5 = 0;
      v6 = JetPrepareUpdate(DhcpGlobalJetServerSession, BitmaskCleanFlagTbl, v5);
      v4 = DhcpMapJetError(v6, "Bitmask clean prepare update");
      if ( !v4 )
      {
        JetSetColumn(DhcpGlobalJetServerSession, BitmaskCleanFlagTbl, BitmaskCleanFlagColId, &pvData, 1u, 0, 0);
        v7 = JetUpdate(DhcpGlobalJetServerSession, BitmaskCleanFlagTbl, 0, 0, 0);
        v4 = DhcpMapJetError(v7, "Jet update");
        if ( v7 )
          JetPrepareUpdate(DhcpGlobalJetServerSession, BitmaskCleanFlagTbl, 3u);
      }
    }
    JetCloseTable(DhcpGlobalJetServerSession, BitmaskCleanFlagTbl);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x18001016c  mov     [rsp+arg_8], rbx
0x180010171  mov     [rsp+arg_10], rsi
0x180010176  mov     [rsp+pvData], cl
0x18001017a  push    rdi
0x18001017b  sub     rsp, 40h
0x18001017f  call    OpenBitmaskCleanFlagTable
0x180010184  xor     esi, esi
0x180010186  test    eax, eax
0x180010188  jnz     loc_1800102B9
0x18001018e  mov     rdx, cs:BitmaskCleanFlagTbl; tableid
0x180010195  xor     r9d, r9d; grbit
0x180010198  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18001019f  xor     r8d, r8d; cRow
0x1800101a2  call    cs:__imp_JetMove
0x1800101a9  nop     dword ptr [rax+rax+00h]
0x1800101ae  mov     ecx, eax
0x1800101b0  lea     rdx, aBitmaskFlagJet; "Bitmask flag jetmove"
0x1800101b7  call    DhcpMapJetError
0x1800101bc  mov     edi, eax
0x1800101be  cmp     eax, 103h
0x1800101c3  jz      short loc_1800101CD
0x1800101c5  test    eax, eax
0x1800101c7  jnz     loc_18001029D
0x1800101cd  mov     rdx, cs:BitmaskCleanFlagTbl; tableid
0x1800101d4  test    eax, eax
0x1800101d6  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800101dd  mov     r8d, 2
0x1800101e3  cmovnz  r8d, esi; prep
0x1800101e7  call    cs:__imp_JetPrepareUpdate
0x1800101ee  nop     dword ptr [rax+rax+00h]
0x1800101f3  mov     ecx, eax
0x1800101f5  lea     rdx, aBitmaskCleanPr; "Bitmask clean prepare update"
0x1800101fc  call    DhcpMapJetError
0x180010201  mov     edi, eax
0x180010203  test    eax, eax
0x180010205  jnz     loc_18001029D
0x18001020b  mov     r8d, cs:BitmaskCleanFlagColId; columnid
0x180010212  lea     r9, [rsp+48h+pvData]; pvData
0x180010217  mov     rdx, cs:BitmaskCleanFlagTbl; tableid
0x18001021e  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180010225  mov     [rsp+48h+psetinfo], rsi; psetinfo
0x18001022a  mov     [rsp+48h+grbit], esi; grbit
0x18001022e  mov     [rsp+48h+cbData], 1; cbData
0x180010236  call    cs:__imp_JetSetColumn
0x18001023d  nop     dword ptr [rax+rax+00h]
0x180010242  mov     rdx, cs:BitmaskCleanFlagTbl; tableid
0x180010249  xor     r9d, r9d; cbBookmark
0x18001024c  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180010253  xor     r8d, r8d; pvBookmark
0x180010256  mov     qword ptr [rsp+48h+cbData], rsi; pcbActual
0x18001025b  call    cs:__imp_JetUpdate
0x180010262  nop     dword ptr [rax+rax+00h]
0x180010267  mov     ecx, eax
0x180010269  lea     rdx, aJetUpdate; "Jet update"
0x180010270  mov     ebx, eax
0x180010272  call    DhcpMapJetError
0x180010277  mov     edi, eax
0x180010279  test    ebx, ebx
0x18001027b  jz      short loc_18001029D
0x18001027d  mov     rdx, cs:BitmaskCleanFlagTbl; tableid
0x180010284  mov     r8d, 3; prep
0x18001028a  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180010291  call    cs:__imp_JetPrepareUpdate
0x180010298  nop     dword ptr [rax+rax+00h]
0x18001029d  mov     rdx, cs:BitmaskCleanFlagTbl; tableid
0x1800102a4  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800102ab  call    cs:__imp_JetCloseTable
0x1800102b2  nop     dword ptr [rax+rax+00h]
0x1800102b7  mov     eax, edi
0x1800102b9  mov     rbx, [rsp+48h+arg_8]
0x1800102be  mov     rsi, [rsp+48h+arg_10]
0x1800102c3  add     rsp, 40h
0x1800102c7  pop     rdi
0x1800102c8  retn
```
