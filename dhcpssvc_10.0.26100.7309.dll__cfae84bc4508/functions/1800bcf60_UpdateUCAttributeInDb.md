# UpdateUCAttributeInDb

- ea: `0x1800bcf60`
- end: `0x1800bd178`
- name: `UpdateUCAttributeInDb`
- size: `536`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18008995c`

## callees

- `0x1800bba04`
- `0x1800bcf60`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800bcfd7`
- `ESENT!JetSetCurrentIndexA` at `0x1800bcfd7`
- `ESENT!JetSetColumns` at `0x1800bd0d8`
- `ESENT!JetSetColumns` at `0x1800bd0d8`
- `ESENT!JetUpdate` at `0x1800bd10d`
- `ESENT!JetUpdate` at `0x1800bd10d`
- `ESENT!JetMakeKey` at `0x1800bd016`
- `ESENT!JetMakeKey` at `0x1800bd016`
- `ESENT!JetSeek` at `0x1800bd048`
- `ESENT!JetSeek` at `0x1800bd048`
- `ESENT!JetBeginTransaction` at `0x1800bd06f`
- `ESENT!JetBeginTransaction` at `0x1800bd06f`
- `ESENT!JetRollback` at `0x1800bd157`
- `ESENT!JetRollback` at `0x1800bd157`
- `ESENT!JetCommitTransaction` at `0x1800bd132`
- `ESENT!JetCommitTransaction` at `0x1800bd132`
- `ESENT!JetPrepareUpdate` at `0x1800bd0a1`
- `ESENT!JetPrepareUpdate` at `0x1800bd0a1`

## string_xrefs

- `0x1800bcfe5`: `DhcpRemoveLegacyAttribute:JetSetCurrentIndex`
- `0x1800bd07d`: `DhcpRemoveLegacyAttribute:JetBeginTransaction`
- `0x1800bd0af`: `DhcpRemoveLegacyAttribute:JetPrepareUpdate`
- `0x1800bd024`: `DhcpRemoveLegacyAttribute:JetMakeKey`
- `0x1800bd056`: `DhcpRemoveLegacyAttribute:JetSeek`
- `0x1800bd140`: `DhcpRemoveLegacyAttribute:JetCommitTransaction`
- `0x1800bd0e6`: `DhcpRemoveLegacyAttribute:JetSetColumns`
- `0x1800bd11b`: `DhcpRemoveLegacyAttribute:JetUPdate`

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
  psetcolumn.columnid = dword_1800F7648;
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
0x1800bcf60  mov     [rsp+arg_0], rbx
0x1800bcf65  mov     [rsp+arg_10], rsi
0x1800bcf6a  mov     [rsp+pvData], edx
0x1800bcf6e  push    rdi
0x1800bcf6f  sub     rsp, 60h
0x1800bcf73  mov     rbx, cs:DhcpGlobalJetServerSession
0x1800bcf7a  xor     esi, esi
0x1800bcf7c  test    r8, r8
0x1800bcf7f  jz      short loc_1800BCFA0
0x1800bcf81  mov     rcx, [r8+10h]
0x1800bcf85  test    rcx, rcx
0x1800bcf88  jz      short loc_1800BCFA3
0x1800bcf8a  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800bcf8e  inc     rax
0x1800bcf91  cmp     [rcx+rax*2], si
0x1800bcf95  jnz     short loc_1800BCF8E
0x1800bcf97  lea     edx, ds:2[rax*2]
0x1800bcf9e  jmp     short loc_1800BCFA5
0x1800bcfa0  mov     rcx, rsi
0x1800bcfa3  mov     edx, esi
0x1800bcfa5  mov     eax, cs:dword_1800F7648
0x1800bcfab  lea     r8, aPolicytableInd_1; "PolicyTable_Index1"
0x1800bcfb2  mov     [rsp+68h+psetcolumn.pvData], rcx
0x1800bcfb7  mov     rcx, rbx; sesid
0x1800bcfba  mov     [rsp+68h+psetcolumn.cbData], edx
0x1800bcfbe  mov     rdx, cs:PolicyTableId; tableid
0x1800bcfc5  mov     [rsp+68h+psetcolumn.columnid], eax
0x1800bcfc9  mov     qword ptr [rsp+68h+psetcolumn.grbit], rsi
0x1800bcfce  mov     qword ptr [rsp+68h+psetcolumn.itagSequence], 1
0x1800bcfd7  call    cs:__imp_JetSetCurrentIndexA
0x1800bcfde  nop     dword ptr [rax+rax+00h]
0x1800bcfe3  mov     ecx, eax
0x1800bcfe5  lea     rdx, aDhcpremovelega_6; "DhcpRemoveLegacyAttribute:JetSetCurrent"...
0x1800bcfec  call    PolicyMapJetError
0x1800bcff1  mov     edi, eax
0x1800bcff3  test    eax, eax
0x1800bcff5  jnz     loc_1800BD163
0x1800bcffb  mov     rdx, cs:PolicyTableId; tableid
0x1800bd002  lea     r9d, [rax+4]; cbData
0x1800bd006  lea     r8, [rsp+68h+pvData]; pvData
0x1800bd00b  mov     [rsp+68h+grbit], 1; grbit
0x1800bd013  mov     rcx, rbx; sesid
0x1800bd016  call    cs:__imp_JetMakeKey
0x1800bd01d  nop     dword ptr [rax+rax+00h]
0x1800bd022  mov     ecx, eax
0x1800bd024  lea     rdx, aDhcpremovelega_0; "DhcpRemoveLegacyAttribute:JetMakeKey"
0x1800bd02b  call    PolicyMapJetError
0x1800bd030  mov     edi, eax
0x1800bd032  test    eax, eax
0x1800bd034  jnz     loc_1800BD163
0x1800bd03a  mov     rdx, cs:PolicyTableId; tableid
0x1800bd041  lea     r8d, [rax+1]; grbit
0x1800bd045  mov     rcx, rbx; sesid
0x1800bd048  call    cs:__imp_JetSeek
0x1800bd04f  nop     dword ptr [rax+rax+00h]
0x1800bd054  mov     ecx, eax
0x1800bd056  lea     rdx, aDhcpremovelega_2; "DhcpRemoveLegacyAttribute:JetSeek"
0x1800bd05d  call    PolicyMapJetError
0x1800bd062  mov     edi, eax
0x1800bd064  test    eax, eax
0x1800bd066  jnz     loc_1800BD163
0x1800bd06c  mov     rcx, rbx; sesid
0x1800bd06f  call    cs:__imp_JetBeginTransaction
0x1800bd076  nop     dword ptr [rax+rax+00h]
0x1800bd07b  mov     ecx, eax
0x1800bd07d  lea     rdx, aDhcpremovelega_1; "DhcpRemoveLegacyAttribute:JetBeginTrans"...
0x1800bd084  call    PolicyMapJetError
0x1800bd089  mov     edi, eax
0x1800bd08b  mov     rcx, rbx; sesid
0x1800bd08e  test    eax, eax
0x1800bd090  jnz     loc_1800BD155
0x1800bd096  mov     rdx, cs:PolicyTableId; tableid
0x1800bd09d  lea     r8d, [rax+2]; prep
0x1800bd0a1  call    cs:__imp_JetPrepareUpdate
0x1800bd0a8  nop     dword ptr [rax+rax+00h]
0x1800bd0ad  mov     ecx, eax
0x1800bd0af  lea     rdx, aDhcpremovelega_4; "DhcpRemoveLegacyAttribute:JetPrepareUpd"...
0x1800bd0b6  call    PolicyMapJetError
0x1800bd0bb  mov     edi, eax
0x1800bd0bd  mov     rcx, rbx; sesid
0x1800bd0c0  test    eax, eax
0x1800bd0c2  jnz     loc_1800BD155
0x1800bd0c8  mov     rdx, cs:PolicyTableId; tableid
0x1800bd0cf  lea     r9d, [rax+1]; csetcolumn
0x1800bd0d3  lea     r8, [rsp+68h+psetcolumn]; psetcolumn
0x1800bd0d8  call    cs:__imp_JetSetColumns
0x1800bd0df  nop     dword ptr [rax+rax+00h]
0x1800bd0e4  mov     ecx, eax
0x1800bd0e6  lea     rdx, aDhcpremovelega; "DhcpRemoveLegacyAttribute:JetSetColumns"
0x1800bd0ed  call    PolicyMapJetError
0x1800bd0f2  mov     edi, eax
0x1800bd0f4  mov     rcx, rbx; sesid
0x1800bd0f7  test    eax, eax
0x1800bd0f9  jnz     short loc_1800BD155
0x1800bd0fb  mov     rdx, cs:PolicyTableId; tableid
0x1800bd102  xor     r9d, r9d; cbBookmark
0x1800bd105  xor     r8d, r8d; pvBookmark
0x1800bd108  mov     qword ptr [rsp+68h+grbit], rsi; pcbActual
0x1800bd10d  call    cs:__imp_JetUpdate
0x1800bd114  nop     dword ptr [rax+rax+00h]
0x1800bd119  mov     ecx, eax
0x1800bd11b  lea     rdx, aDhcpremovelega_5; "DhcpRemoveLegacyAttribute:JetUPdate"
0x1800bd122  call    PolicyMapJetError
0x1800bd127  xor     edx, edx; grbit
0x1800bd129  mov     edi, eax
0x1800bd12b  mov     rcx, rbx; sesid
0x1800bd12e  test    eax, eax
0x1800bd130  jnz     short loc_1800BD157
0x1800bd132  call    cs:__imp_JetCommitTransaction
0x1800bd139  nop     dword ptr [rax+rax+00h]
0x1800bd13e  mov     ecx, eax
0x1800bd140  lea     rdx, aDhcpremovelega_3; "DhcpRemoveLegacyAttribute:JetCommitTran"...
0x1800bd147  call    PolicyMapJetError
0x1800bd14c  mov     edi, eax
0x1800bd14e  test    eax, eax
0x1800bd150  jz      short loc_1800BD163
0x1800bd152  mov     rcx, rbx; sesid
0x1800bd155  xor     edx, edx; grbit
0x1800bd157  call    cs:__imp_JetRollback
0x1800bd15e  nop     dword ptr [rax+rax+00h]
0x1800bd163  lea     r11, [rsp+68h+var_8]
0x1800bd168  mov     eax, edi
0x1800bd16a  mov     rbx, [r11+10h]
0x1800bd16e  mov     rsi, [r11+20h]
0x1800bd172  mov     rsp, r11
0x1800bd175  pop     rdi
0x1800bd176  retn
```
