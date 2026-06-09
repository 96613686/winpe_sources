# DhcpPolicyWildCardLenListInit

- ea: `0x1800b9f4c`
- end: `0x1800ba182`
- name: `DhcpPolicyWildCardLenListInit`
- size: `566`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180025bf4`

## callees

- `0x1800b7cbc`
- `0x1800b9f4c`
- `0x1800bba04`
- `0x1800cc9e0`

## import_xrefs

- `ESENT!JetRetrieveColumns` at `0x1800ba0d3`
- `ESENT!JetRetrieveColumns` at `0x1800ba0d3`
- `ESENT!JetSetCurrentIndex2A` at `0x1800ba01a`
- `ESENT!JetSetCurrentIndex2A` at `0x1800ba01a`
- `ESENT!JetMakeKey` at `0x1800ba052`
- `ESENT!JetMakeKey` at `0x1800ba052`
- `ESENT!JetSeek` at `0x1800ba082`
- `ESENT!JetSeek` at `0x1800ba082`
- `ESENT!JetMove` at `0x1800ba129`
- `ESENT!JetMove` at `0x1800ba129`

## string_xrefs

- `0x1800ba137`: `DhcpPolicyWildCardLenListInit:JetMove`

## pseudocode

```c
__int64 DhcpPolicyWildCardLenListInit()
{
  JET_SESID v0; // rsi
  unsigned int v1; // ebx
  LPVOID v2; // r14
  unsigned int v3; // eax
  __int64 result; // rax
  unsigned int Key; // eax
  unsigned int v6; // edi
  unsigned int v7; // edi
  unsigned int v8; // eax
  __int64 v9; // r9
  char pvData[4]; // [rsp+38h] [rbp-69h] BYREF
  int v11; // [rsp+3Ch] [rbp-65h] BYREF
  unsigned int v12; // [rsp+40h] [rbp-61h] BYREF
  unsigned int v13; // [rsp+44h] [rbp-5Dh] BYREF
  JET_RETRIEVECOLUMN pretrievecolumn; // [rsp+48h] [rbp-59h] BYREF
  int v15; // [rsp+78h] [rbp-29h]
  unsigned int *v16; // [rsp+80h] [rbp-21h]
  __int64 v17; // [rsp+88h] [rbp-19h]
  __int64 v18; // [rsp+90h] [rbp-11h]
  __int64 v19; // [rsp+98h] [rbp-9h]
  int v20; // [rsp+A0h] [rbp-1h]
  JET_COLUMNID v21; // [rsp+A8h] [rbp+7h]
  int *v22; // [rsp+B0h] [rbp+Fh]
  __int64 v23; // [rsp+B8h] [rbp+17h]
  __int64 v24; // [rsp+C0h] [rbp+1Fh]
  __int64 v25; // [rsp+C8h] [rbp+27h]
  int v26; // [rsp+D0h] [rbp+2Fh]

  v0 = DhcpGlobalJetServerSession;
  v1 = 0;
  v2 = DhcpGlobalThisServer;
  pretrievecolumn.columnid = dword_1800F7770;
  pretrievecolumn.pvData = &v13;
  v15 = dword_1800F7830;
  v16 = &v12;
  v21 = dword_1800F77E8;
  v22 = &v11;
  v12 = 0;
  v11 = 0;
  v13 = 0;
  pvData[0] = 1;
  *(_QWORD *)&pretrievecolumn.cbData = 4;
  *(_QWORD *)&pretrievecolumn.grbit = 1;
  *(_QWORD *)&pretrievecolumn.itagSequence = 1;
  pretrievecolumn.err = 0;
  v17 = 4;
  v18 = 1;
  v19 = 1;
  v20 = 0;
  v23 = 4;
  v24 = 1;
  v25 = 1;
  v26 = 0;
  v3 = JetSetCurrentIndex2A(DhcpGlobalJetServerSession, PolicyConditionTableId, "PolicyConditionTable_Index3", 0);
  result = PolicyMapJetError(v3, "DhcpPolicyWildCardLenListInit:JetSetCurrentIndex2");
  if ( !(_DWORD)result )
  {
    Key = JetMakeKey(v0, PolicyConditionTableId, pvData, 1u, 1u);
    result = PolicyMapJetError(Key, "DhcpPolicyWildCardLenListInit:5");
    if ( !(_DWORD)result )
    {
      v6 = JetSeek(v0, PolicyConditionTableId, 0x21u);
      result = PolicyMapJetError(v6, "DhcpPolicyWildCardLenListInit:7");
      if ( !(_DWORD)result )
      {
        do
        {
          v7 = JetRetrieveColumns(v0, PolicyConditionTableId, &pretrievecolumn, 3u);
          v8 = PolicyMapJetError(v7, "DhcpPolicyWildCardLenListInit:1");
          if ( v8 )
            break;
          if ( v11 == 4 || (v9 = 1, v11 == 5) )
            v9 = 0;
          result = AddWildCardLengthToSubnet(v2, v13, v12, v9);
          if ( (_DWORD)result )
            return result;
          v7 = JetMove(v0, PolicyConditionTableId, 1, 0);
          v8 = PolicyMapJetError(v7, "DhcpPolicyWildCardLenListInit:JetMove");
        }
        while ( !v8 );
        if ( v7 != -1603 )
          return v8;
        return v1;
      }
      if ( v6 == -1601 || v6 == 1039 )
        return v1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800b9f4c  mov     rax, rsp
0x1800b9f4f  mov     [rax+8], rbx
0x1800b9f53  mov     [rax+10h], rsi
0x1800b9f57  mov     [rax+18h], rdi
0x1800b9f5b  push    rbp
0x1800b9f5c  push    r14
0x1800b9f5e  push    r15
0x1800b9f60  lea     rbp, [rax-5Fh]
0x1800b9f64  sub     rsp, 0E0h
0x1800b9f6b  mov     rax, cs:__security_cookie
0x1800b9f72  xor     rax, rsp
0x1800b9f75  mov     [rbp+57h+var_20], rax
0x1800b9f79  mov     eax, cs:dword_1800F7770
0x1800b9f7f  lea     r8, aPolicyconditio_4; "PolicyConditionTable_Index3"
0x1800b9f86  mov     rsi, cs:DhcpGlobalJetServerSession
0x1800b9f8d  xor     ebx, ebx
0x1800b9f8f  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800b9f96  xor     r9d, r9d; grbit
0x1800b9f99  mov     r14, cs:DhcpGlobalThisServer
0x1800b9fa0  mov     rcx, rsi; sesid
0x1800b9fa3  mov     [rbp+57h+pretrievecolumn.columnid], eax
0x1800b9fa6  lea     rax, [rbp+57h+var_B4]
0x1800b9faa  lea     r15d, [rbx+1]
0x1800b9fae  mov     [rbp+57h+pretrievecolumn.pvData], rax
0x1800b9fb2  mov     eax, cs:dword_1800F7830
0x1800b9fb8  mov     [rbp+57h+var_80], eax
0x1800b9fbb  lea     rax, [rbp+57h+var_B8]
0x1800b9fbf  mov     [rbp+57h+var_78], rax
0x1800b9fc3  mov     eax, cs:dword_1800F77E8
0x1800b9fc9  mov     [rbp+57h+var_50], eax
0x1800b9fcc  lea     rax, [rbp+57h+var_BC]
0x1800b9fd0  mov     [rbp+57h+var_48], rax
0x1800b9fd4  mov     [rbp+57h+var_B8], ebx
0x1800b9fd7  mov     [rbp+57h+var_BC], ebx
0x1800b9fda  mov     [rbp+57h+var_B4], ebx
0x1800b9fdd  mov     [rbp+57h+pvData], r15b
0x1800b9fe1  mov     qword ptr [rbp+57h+pretrievecolumn.cbData], 4
0x1800b9fe9  mov     qword ptr [rbp+57h+pretrievecolumn.grbit], r15
0x1800b9fed  mov     qword ptr [rbp+57h+pretrievecolumn.itagSequence], r15
0x1800b9ff1  mov     [rbp+57h+pretrievecolumn.err], ebx
0x1800b9ff4  mov     [rbp+57h+var_70], 4
0x1800b9ffc  mov     [rbp+57h+var_68], r15
0x1800ba000  mov     [rbp+57h+var_60], r15
0x1800ba004  mov     [rbp+57h+var_58], ebx
0x1800ba007  mov     [rbp+57h+var_40], 4
0x1800ba00f  mov     [rbp+57h+var_38], r15
0x1800ba013  mov     [rbp+57h+var_30], r15
0x1800ba017  mov     [rbp+57h+var_28], ebx
0x1800ba01a  call    cs:__imp_JetSetCurrentIndex2A
0x1800ba021  nop     dword ptr [rax+rax+00h]
0x1800ba026  mov     ecx, eax
0x1800ba028  lea     rdx, aDhcppolicywild; "DhcpPolicyWildCardLenListInit:JetSetCur"...
0x1800ba02f  call    PolicyMapJetError
0x1800ba034  test    eax, eax
0x1800ba036  jnz     loc_1800BA158
0x1800ba03c  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800ba043  lea     r8, [rbp+57h+pvData]; pvData
0x1800ba047  mov     r9d, r15d; cbData
0x1800ba04a  mov     [rsp+0F0h+grbit], r15d; grbit
0x1800ba04f  mov     rcx, rsi; sesid
0x1800ba052  call    cs:__imp_JetMakeKey
0x1800ba059  nop     dword ptr [rax+rax+00h]
0x1800ba05e  mov     ecx, eax
0x1800ba060  lea     rdx, aDhcppolicywild_0; "DhcpPolicyWildCardLenListInit:5"
0x1800ba067  call    PolicyMapJetError
0x1800ba06c  test    eax, eax
0x1800ba06e  jnz     loc_1800BA158
0x1800ba074  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800ba07b  lea     r8d, [rbx+21h]; grbit
0x1800ba07f  mov     rcx, rsi; sesid
0x1800ba082  call    cs:__imp_JetSeek
0x1800ba089  nop     dword ptr [rax+rax+00h]
0x1800ba08e  mov     ecx, eax
0x1800ba090  lea     rdx, aDhcppolicywild_3; "DhcpPolicyWildCardLenListInit:7"
0x1800ba097  mov     edi, eax
0x1800ba099  call    PolicyMapJetError
0x1800ba09e  test    eax, eax
0x1800ba0a0  jz      short loc_1800BA0BF
0x1800ba0a2  cmp     edi, 0FFFFF9BFh
0x1800ba0a8  jz      loc_1800BA156
0x1800ba0ae  cmp     edi, 40Fh
0x1800ba0b4  jnz     loc_1800BA158
0x1800ba0ba  jmp     loc_1800BA156
0x1800ba0bf  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800ba0c6  lea     r8, [rbp+57h+pretrievecolumn]; pretrievecolumn
0x1800ba0ca  mov     r9d, 3; cretrievecolumn
0x1800ba0d0  mov     rcx, rsi; sesid
0x1800ba0d3  call    cs:__imp_JetRetrieveColumns
0x1800ba0da  nop     dword ptr [rax+rax+00h]
0x1800ba0df  mov     ecx, eax
0x1800ba0e1  lea     rdx, aDhcppolicywild_1; "DhcpPolicyWildCardLenListInit:1"
0x1800ba0e8  mov     edi, eax
0x1800ba0ea  call    PolicyMapJetError
0x1800ba0ef  test    eax, eax
0x1800ba0f1  jnz     short loc_1800BA14D
0x1800ba0f3  mov     eax, [rbp+57h+var_BC]
0x1800ba0f6  sub     eax, 4
0x1800ba0f9  jz      short loc_1800BA103
0x1800ba0fb  mov     r9d, r15d
0x1800ba0fe  cmp     eax, r15d
0x1800ba101  jnz     short loc_1800BA106
0x1800ba103  mov     r9d, ebx
0x1800ba106  mov     r8d, [rbp+57h+var_B8]
0x1800ba10a  mov     rcx, r14
0x1800ba10d  mov     edx, [rbp+57h+var_B4]
0x1800ba110  call    AddWildCardLengthToSubnet
0x1800ba115  test    eax, eax
0x1800ba117  jnz     short loc_1800BA158
0x1800ba119  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800ba120  xor     r9d, r9d; grbit
0x1800ba123  mov     r8d, r15d; cRow
0x1800ba126  mov     rcx, rsi; sesid
0x1800ba129  call    cs:__imp_JetMove
0x1800ba130  nop     dword ptr [rax+rax+00h]
0x1800ba135  mov     ecx, eax
0x1800ba137  lea     rdx, aDhcppolicywild_2; "DhcpPolicyWildCardLenListInit:JetMove"
0x1800ba13e  mov     edi, eax
0x1800ba140  call    PolicyMapJetError
0x1800ba145  test    eax, eax
0x1800ba147  jz      loc_1800BA0BF
0x1800ba14d  cmp     edi, 0FFFFF9BDh
0x1800ba153  cmovnz  ebx, eax
0x1800ba156  mov     eax, ebx
0x1800ba158  mov     rcx, [rbp+57h+var_20]
0x1800ba15c  xor     rcx, rsp; StackCookie
0x1800ba15f  call    __security_check_cookie
0x1800ba164  lea     r11, [rsp+0F0h+var_10]
0x1800ba16c  mov     rbx, [r11+20h]
0x1800ba170  mov     rsi, [r11+28h]
0x1800ba174  mov     rdi, [r11+30h]
0x1800ba178  mov     rsp, r11
0x1800ba17b  pop     r15
0x1800ba17d  pop     r14
0x1800ba17f  pop     rbp
0x1800ba180  retn
```
