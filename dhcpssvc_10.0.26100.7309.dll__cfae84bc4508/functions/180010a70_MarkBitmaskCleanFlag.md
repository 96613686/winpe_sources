# MarkBitmaskCleanFlag

- ea: `0x180010a70`
- end: `0x180010bce`
- name: `MarkBitmaskCleanFlag`
- size: `350`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800107ec`
- `0x18001119c`

## callees

- `0x18000f144`
- `0x180010a70`
- `0x180010bd4`

## import_xrefs

- `ESENT!JetCloseTable` at `0x180010baf`
- `ESENT!JetCloseTable` at `0x180010baf`
- `ESENT!JetUpdate` at `0x180010b5f`
- `ESENT!JetUpdate` at `0x180010b5f`
- `ESENT!JetPrepareUpdate` at `0x180010aeb`
- `ESENT!JetPrepareUpdate` at `0x180010b95`
- `ESENT!JetPrepareUpdate` at `0x180010aeb`
- `ESENT!JetPrepareUpdate` at `0x180010b95`
- `ESENT!JetSetColumn` at `0x180010b3a`
- `ESENT!JetSetColumn` at `0x180010b3a`
- `ESENT!JetMove` at `0x180010aa6`
- `ESENT!JetMove` at `0x180010aa6`

## string_xrefs

- `0x180010ab4`: `Bitmask flag jetmove`
- `0x180010af9`: `Bitmask clean prepare update`
- `0x180010b6d`: `Jet update`

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
0x180010a70  mov     [rsp+arg_8], rbx
0x180010a75  mov     [rsp+arg_10], rsi
0x180010a7a  mov     [rsp+pvData], cl
0x180010a7e  push    rdi
0x180010a7f  sub     rsp, 40h
0x180010a83  call    OpenBitmaskCleanFlagTable
0x180010a88  xor     esi, esi
0x180010a8a  test    eax, eax
0x180010a8c  jnz     loc_180010BBD
0x180010a92  mov     rdx, cs:BitmaskCleanFlagTbl; tableid
0x180010a99  xor     r9d, r9d; grbit
0x180010a9c  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180010aa3  xor     r8d, r8d; cRow
0x180010aa6  call    cs:__imp_JetMove
0x180010aad  nop     dword ptr [rax+rax+00h]
0x180010ab2  mov     ecx, eax
0x180010ab4  lea     rdx, aBitmaskFlagJet; "Bitmask flag jetmove"
0x180010abb  call    DhcpMapJetError
0x180010ac0  mov     edi, eax
0x180010ac2  cmp     eax, 103h
0x180010ac7  jz      short loc_180010AD1
0x180010ac9  test    eax, eax
0x180010acb  jnz     loc_180010BA1
0x180010ad1  mov     rdx, cs:BitmaskCleanFlagTbl; tableid
0x180010ad8  test    eax, eax
0x180010ada  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180010ae1  mov     r8d, 2
0x180010ae7  cmovnz  r8d, esi; prep
0x180010aeb  call    cs:__imp_JetPrepareUpdate
0x180010af2  nop     dword ptr [rax+rax+00h]
0x180010af7  mov     ecx, eax
0x180010af9  lea     rdx, aBitmaskCleanPr; "Bitmask clean prepare update"
0x180010b00  call    DhcpMapJetError
0x180010b05  mov     edi, eax
0x180010b07  test    eax, eax
0x180010b09  jnz     loc_180010BA1
0x180010b0f  mov     r8d, cs:BitmaskCleanFlagColId; columnid
0x180010b16  lea     r9, [rsp+48h+pvData]; pvData
0x180010b1b  mov     rdx, cs:BitmaskCleanFlagTbl; tableid
0x180010b22  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180010b29  mov     [rsp+48h+psetinfo], rsi; psetinfo
0x180010b2e  mov     [rsp+48h+grbit], esi; grbit
0x180010b32  mov     [rsp+48h+cbData], 1; cbData
0x180010b3a  call    cs:__imp_JetSetColumn
0x180010b41  nop     dword ptr [rax+rax+00h]
0x180010b46  mov     rdx, cs:BitmaskCleanFlagTbl; tableid
0x180010b4d  xor     r9d, r9d; cbBookmark
0x180010b50  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180010b57  xor     r8d, r8d; pvBookmark
0x180010b5a  mov     qword ptr [rsp+48h+cbData], rsi; pcbActual
0x180010b5f  call    cs:__imp_JetUpdate
0x180010b66  nop     dword ptr [rax+rax+00h]
0x180010b6b  mov     ecx, eax
0x180010b6d  lea     rdx, aJetUpdate; "Jet update"
0x180010b74  mov     ebx, eax
0x180010b76  call    DhcpMapJetError
0x180010b7b  mov     edi, eax
0x180010b7d  test    ebx, ebx
0x180010b7f  jz      short loc_180010BA1
0x180010b81  mov     rdx, cs:BitmaskCleanFlagTbl; tableid
0x180010b88  mov     r8d, 3; prep
0x180010b8e  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180010b95  call    cs:__imp_JetPrepareUpdate
0x180010b9c  nop     dword ptr [rax+rax+00h]
0x180010ba1  mov     rdx, cs:BitmaskCleanFlagTbl; tableid
0x180010ba8  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180010baf  call    cs:__imp_JetCloseTable
0x180010bb6  nop     dword ptr [rax+rax+00h]
0x180010bbb  mov     eax, edi
0x180010bbd  mov     rbx, [rsp+48h+arg_8]
0x180010bc2  mov     rsi, [rsp+48h+arg_10]
0x180010bc7  add     rsp, 40h
0x180010bcb  pop     rdi
0x180010bcc  retn
```
