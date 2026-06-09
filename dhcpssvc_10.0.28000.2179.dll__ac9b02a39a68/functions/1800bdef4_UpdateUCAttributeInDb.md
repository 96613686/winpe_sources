# UpdateUCAttributeInDb

- ea: `0x1800bdef4`
- end: `0x1800be10c`
- name: `UpdateUCAttributeInDb`
- size: `536`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180089938`

## callees

- `0x1800bc990`
- `0x1800bdef4`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800bdf6b`
- `ESENT!JetSetCurrentIndexA` at `0x1800bdf6b`
- `ESENT!JetSetColumns` at `0x1800be06c`
- `ESENT!JetSetColumns` at `0x1800be06c`
- `ESENT!JetUpdate` at `0x1800be0a1`
- `ESENT!JetUpdate` at `0x1800be0a1`
- `ESENT!JetMakeKey` at `0x1800bdfaa`
- `ESENT!JetMakeKey` at `0x1800bdfaa`
- `ESENT!JetSeek` at `0x1800bdfdc`
- `ESENT!JetSeek` at `0x1800bdfdc`
- `ESENT!JetBeginTransaction` at `0x1800be003`
- `ESENT!JetBeginTransaction` at `0x1800be003`
- `ESENT!JetRollback` at `0x1800be0eb`
- `ESENT!JetRollback` at `0x1800be0eb`
- `ESENT!JetCommitTransaction` at `0x1800be0c6`
- `ESENT!JetCommitTransaction` at `0x1800be0c6`
- `ESENT!JetPrepareUpdate` at `0x1800be035`
- `ESENT!JetPrepareUpdate` at `0x1800be035`

## string_xrefs

- `0x1800bdfea`: `DhcpRemoveLegacyAttribute:JetSeek`
- `0x1800bdfb8`: `DhcpRemoveLegacyAttribute:JetMakeKey`
- `0x1800bdf79`: `DhcpRemoveLegacyAttribute:JetSetCurrentIndex`
- `0x1800be0af`: `DhcpRemoveLegacyAttribute:JetUPdate`
- `0x1800be07a`: `DhcpRemoveLegacyAttribute:JetSetColumns`
- `0x1800be043`: `DhcpRemoveLegacyAttribute:JetPrepareUpdate`
- `0x1800be011`: `DhcpRemoveLegacyAttribute:JetBeginTransaction`
- `0x1800be0d4`: `DhcpRemoveLegacyAttribute:JetCommitTransaction`

## pseudocode

```c
__int64 __fastcall UpdateUCAttributeInDb(__int64 a1, int a2, __int64 a3)
{
  JET_SESID v3; // rbx
  _WORD *v4; // rcx
  __int64 v5; // rax
  unsigned int v6; // edx
  unsigned int v7; // eax
  unsigned int v8; // edi
  unsigned int Key; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  JET_SESID v12; // rcx
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  JET_SETCOLUMN psetcolumn; // [rsp+30h] [rbp-38h] BYREF
  int pvData; // [rsp+78h] [rbp+10h] BYREF

  pvData = a2;
  v3 = DhcpGlobalJetServerSession;
  if ( !a3 )
  {
    v4 = 0;
    goto LABEL_7;
  }
  v4 = *(_WORD **)(a3 + 16);
  if ( !v4 )
  {
LABEL_7:
    v6 = 0;
    goto LABEL_8;
  }
  v5 = -1;
  do
    ++v5;
  while ( v4[v5] );
  v6 = 2 * v5 + 2;
LABEL_8:
  psetcolumn.pvData = v4;
  psetcolumn.cbData = v6;
  psetcolumn.columnid = dword_1800F9818;
  *(_QWORD *)&psetcolumn.grbit = 0;
  *(_QWORD *)&psetcolumn.itagSequence = 1;
  v7 = JetSetCurrentIndexA(DhcpGlobalJetServerSession, PolicyTableId, "PolicyTable_Index1");
  v8 = PolicyMapJetError(v7, "DhcpRemoveLegacyAttribute:JetSetCurrentIndex");
  if ( !v8 )
  {
    Key = JetMakeKey(v3, PolicyTableId, &pvData, 4u, 1u);
    v8 = PolicyMapJetError(Key, "DhcpRemoveLegacyAttribute:JetMakeKey");
    if ( !v8 )
    {
      v10 = JetSeek(v3, PolicyTableId, 1u);
      v8 = PolicyMapJetError(v10, "DhcpRemoveLegacyAttribute:JetSeek");
      if ( !v8 )
      {
        v11 = JetBeginTransaction(v3);
        v8 = PolicyMapJetError(v11, "DhcpRemoveLegacyAttribute:JetBeginTransaction");
        v12 = v3;
        if ( v8 )
          goto LABEL_17;
        v13 = JetPrepareUpdate(v3, PolicyTableId, 2u);
        v8 = PolicyMapJetError(v13, "DhcpRemoveLegacyAttribute:JetPrepareUpdate");
        v12 = v3;
        if ( v8 )
          goto LABEL_17;
        v14 = JetSetColumns(v3, PolicyTableId, &psetcolumn, 1u);
        v8 = PolicyMapJetError(v14, "DhcpRemoveLegacyAttribute:JetSetColumns");
        v12 = v3;
        if ( v8 )
          goto LABEL_17;
        v15 = JetUpdate(v3, PolicyTableId, 0, 0, 0);
        v8 = PolicyMapJetError(v15, "DhcpRemoveLegacyAttribute:JetUPdate");
        v12 = v3;
        if ( v8 )
          goto LABEL_17;
        v16 = JetCommitTransaction(v3, 0);
        v8 = PolicyMapJetError(v16, "DhcpRemoveLegacyAttribute:JetCommitTransaction");
        if ( v8 )
        {
          v12 = v3;
LABEL_17:
          JetRollback(v12, 0);
        }
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1800bdef4  mov     [rsp+arg_0], rbx
0x1800bdef9  mov     [rsp+arg_10], rsi
0x1800bdefe  mov     [rsp+pvData], edx
0x1800bdf02  push    rdi
0x1800bdf03  sub     rsp, 60h
0x1800bdf07  mov     rbx, cs:DhcpGlobalJetServerSession
0x1800bdf0e  xor     esi, esi
0x1800bdf10  test    r8, r8
0x1800bdf13  jz      short loc_1800BDF34
0x1800bdf15  mov     rcx, [r8+10h]
0x1800bdf19  test    rcx, rcx
0x1800bdf1c  jz      short loc_1800BDF37
0x1800bdf1e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800bdf22  inc     rax
0x1800bdf25  cmp     [rcx+rax*2], si
0x1800bdf29  jnz     short loc_1800BDF22
0x1800bdf2b  lea     edx, ds:2[rax*2]
0x1800bdf32  jmp     short loc_1800BDF39
0x1800bdf34  mov     rcx, rsi
0x1800bdf37  mov     edx, esi
0x1800bdf39  mov     eax, cs:dword_1800F9818
0x1800bdf3f  lea     r8, aPolicytableInd_1; "PolicyTable_Index1"
0x1800bdf46  mov     [rsp+68h+psetcolumn.pvData], rcx
0x1800bdf4b  mov     rcx, rbx; sesid
0x1800bdf4e  mov     [rsp+68h+psetcolumn.cbData], edx
0x1800bdf52  mov     rdx, cs:PolicyTableId; tableid
0x1800bdf59  mov     [rsp+68h+psetcolumn.columnid], eax
0x1800bdf5d  mov     qword ptr [rsp+68h+psetcolumn.grbit], rsi
0x1800bdf62  mov     qword ptr [rsp+68h+psetcolumn.itagSequence], 1
0x1800bdf6b  call    cs:__imp_JetSetCurrentIndexA
0x1800bdf72  nop     dword ptr [rax+rax+00h]
0x1800bdf77  mov     ecx, eax
0x1800bdf79  lea     rdx, aDhcpremovelega_6; "DhcpRemoveLegacyAttribute:JetSetCurrent"...
0x1800bdf80  call    PolicyMapJetError
0x1800bdf85  mov     edi, eax
0x1800bdf87  test    eax, eax
0x1800bdf89  jnz     loc_1800BE0F7
0x1800bdf8f  mov     rdx, cs:PolicyTableId; tableid
0x1800bdf96  lea     r9d, [rax+4]; cbData
0x1800bdf9a  lea     r8, [rsp+68h+pvData]; pvData
0x1800bdf9f  mov     [rsp+68h+grbit], 1; grbit
0x1800bdfa7  mov     rcx, rbx; sesid
0x1800bdfaa  call    cs:__imp_JetMakeKey
0x1800bdfb1  nop     dword ptr [rax+rax+00h]
0x1800bdfb6  mov     ecx, eax
0x1800bdfb8  lea     rdx, aDhcpremovelega_0; "DhcpRemoveLegacyAttribute:JetMakeKey"
0x1800bdfbf  call    PolicyMapJetError
0x1800bdfc4  mov     edi, eax
0x1800bdfc6  test    eax, eax
0x1800bdfc8  jnz     loc_1800BE0F7
0x1800bdfce  mov     rdx, cs:PolicyTableId; tableid
0x1800bdfd5  lea     r8d, [rax+1]; grbit
0x1800bdfd9  mov     rcx, rbx; sesid
0x1800bdfdc  call    cs:__imp_JetSeek
0x1800bdfe3  nop     dword ptr [rax+rax+00h]
0x1800bdfe8  mov     ecx, eax
0x1800bdfea  lea     rdx, aDhcpremovelega_2; "DhcpRemoveLegacyAttribute:JetSeek"
0x1800bdff1  call    PolicyMapJetError
0x1800bdff6  mov     edi, eax
0x1800bdff8  test    eax, eax
0x1800bdffa  jnz     loc_1800BE0F7
0x1800be000  mov     rcx, rbx; sesid
0x1800be003  call    cs:__imp_JetBeginTransaction
0x1800be00a  nop     dword ptr [rax+rax+00h]
0x1800be00f  mov     ecx, eax
0x1800be011  lea     rdx, aDhcpremovelega_1; "DhcpRemoveLegacyAttribute:JetBeginTrans"...
0x1800be018  call    PolicyMapJetError
0x1800be01d  mov     edi, eax
0x1800be01f  mov     rcx, rbx; sesid
0x1800be022  test    eax, eax
0x1800be024  jnz     loc_1800BE0E9
0x1800be02a  mov     rdx, cs:PolicyTableId; tableid
0x1800be031  lea     r8d, [rax+2]; prep
0x1800be035  call    cs:__imp_JetPrepareUpdate
0x1800be03c  nop     dword ptr [rax+rax+00h]
0x1800be041  mov     ecx, eax
0x1800be043  lea     rdx, aDhcpremovelega_4; "DhcpRemoveLegacyAttribute:JetPrepareUpd"...
0x1800be04a  call    PolicyMapJetError
0x1800be04f  mov     edi, eax
0x1800be051  mov     rcx, rbx; sesid
0x1800be054  test    eax, eax
0x1800be056  jnz     loc_1800BE0E9
0x1800be05c  mov     rdx, cs:PolicyTableId; tableid
0x1800be063  lea     r9d, [rax+1]; csetcolumn
0x1800be067  lea     r8, [rsp+68h+psetcolumn]; psetcolumn
0x1800be06c  call    cs:__imp_JetSetColumns
0x1800be073  nop     dword ptr [rax+rax+00h]
0x1800be078  mov     ecx, eax
0x1800be07a  lea     rdx, aDhcpremovelega; "DhcpRemoveLegacyAttribute:JetSetColumns"
0x1800be081  call    PolicyMapJetError
0x1800be086  mov     edi, eax
0x1800be088  mov     rcx, rbx; sesid
0x1800be08b  test    eax, eax
0x1800be08d  jnz     short loc_1800BE0E9
0x1800be08f  mov     rdx, cs:PolicyTableId; tableid
0x1800be096  xor     r9d, r9d; cbBookmark
0x1800be099  xor     r8d, r8d; pvBookmark
0x1800be09c  mov     qword ptr [rsp+68h+grbit], rsi; pcbActual
0x1800be0a1  call    cs:__imp_JetUpdate
0x1800be0a8  nop     dword ptr [rax+rax+00h]
0x1800be0ad  mov     ecx, eax
0x1800be0af  lea     rdx, aDhcpremovelega_5; "DhcpRemoveLegacyAttribute:JetUPdate"
0x1800be0b6  call    PolicyMapJetError
0x1800be0bb  xor     edx, edx; grbit
0x1800be0bd  mov     edi, eax
0x1800be0bf  mov     rcx, rbx; sesid
0x1800be0c2  test    eax, eax
0x1800be0c4  jnz     short loc_1800BE0EB
0x1800be0c6  call    cs:__imp_JetCommitTransaction
0x1800be0cd  nop     dword ptr [rax+rax+00h]
0x1800be0d2  mov     ecx, eax
0x1800be0d4  lea     rdx, aDhcpremovelega_3; "DhcpRemoveLegacyAttribute:JetCommitTran"...
0x1800be0db  call    PolicyMapJetError
0x1800be0e0  mov     edi, eax
0x1800be0e2  test    eax, eax
0x1800be0e4  jz      short loc_1800BE0F7
0x1800be0e6  mov     rcx, rbx; sesid
0x1800be0e9  xor     edx, edx; grbit
0x1800be0eb  call    cs:__imp_JetRollback
0x1800be0f2  nop     dword ptr [rax+rax+00h]
0x1800be0f7  lea     r11, [rsp+68h+var_8]
0x1800be0fc  mov     eax, edi
0x1800be0fe  mov     rbx, [r11+10h]
0x1800be102  mov     rsi, [r11+20h]
0x1800be106  mov     rsp, r11
0x1800be109  pop     rdi
0x1800be10a  retn
```
