# AddConditionEntries

- ea: `0x1800b6fc8`
- end: `0x1800b76e6`
- name: `AddConditionEntries`
- size: `1822`
- prototype: `__int64 __usercall@<rax>(JET_SESID sesid@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800b8118`
- `0x1800bd190`

## callees

- `0x1800b6fc8`
- `0x1800b8ba0`
- `0x1800bb09c`
- `0x1800bb66c`
- `0x1800bc990`
- `0x1800cdac0`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800b705f`
- `ESENT!JetSetCurrentIndexA` at `0x1800b705f`
- `ESENT!JetSetColumns` at `0x1800b748f`
- `ESENT!JetSetColumns` at `0x1800b7618`
- `ESENT!JetSetColumns` at `0x1800b748f`
- `ESENT!JetSetColumns` at `0x1800b7618`
- `ESENT!JetUpdate` at `0x1800b74c0`
- `ESENT!JetUpdate` at `0x1800b7650`
- `ESENT!JetUpdate` at `0x1800b74c0`
- `ESENT!JetUpdate` at `0x1800b7650`
- `ESENT!JetMakeKey` at `0x1800b70c3`
- `ESENT!JetMakeKey` at `0x1800b7113`
- `ESENT!JetMakeKey` at `0x1800b7156`
- `ESENT!JetMakeKey` at `0x1800b7199`
- `ESENT!JetMakeKey` at `0x1800b71f5`
- `ESENT!JetMakeKey` at `0x1800b7237`
- `ESENT!JetMakeKey` at `0x1800b7278`
- `ESENT!JetMakeKey` at `0x1800b72f7`
- `ESENT!JetMakeKey` at `0x1800b732f`
- `ESENT!JetMakeKey` at `0x1800b70c3`
- `ESENT!JetMakeKey` at `0x1800b7113`
- `ESENT!JetMakeKey` at `0x1800b7156`
- `ESENT!JetMakeKey` at `0x1800b7199`
- `ESENT!JetMakeKey` at `0x1800b71f5`
- `ESENT!JetMakeKey` at `0x1800b7237`
- `ESENT!JetMakeKey` at `0x1800b7278`
- `ESENT!JetMakeKey` at `0x1800b72f7`
- `ESENT!JetMakeKey` at `0x1800b732f`
- `ESENT!JetSeek` at `0x1800b735d`
- `ESENT!JetSeek` at `0x1800b735d`
- `ESENT!JetBeginTransaction` at `0x1800b73dc`
- `ESENT!JetBeginTransaction` at `0x1800b7566`
- `ESENT!JetBeginTransaction` at `0x1800b73dc`
- `ESENT!JetBeginTransaction` at `0x1800b7566`
- `ESENT!JetRollback` at `0x1800b750e`
- `ESENT!JetRollback` at `0x1800b750e`
- `ESENT!JetCommitTransaction` at `0x1800b74e5`
- `ESENT!JetCommitTransaction` at `0x1800b7679`
- `ESENT!JetCommitTransaction` at `0x1800b74e5`
- `ESENT!JetCommitTransaction` at `0x1800b7679`
- `ESENT!JetPrepareUpdate` at `0x1800b740a`
- `ESENT!JetPrepareUpdate` at `0x1800b758f`
- `ESENT!JetPrepareUpdate` at `0x1800b740a`
- `ESENT!JetPrepareUpdate` at `0x1800b758f`
- `ESENT!JetRetrieveColumn` at `0x1800b73b5`
- `ESENT!JetRetrieveColumn` at `0x1800b73b5`
- `USER32!CharLowerBuffW` at `0x1800b709f`
- `USER32!CharLowerBuffW` at `0x1800b709f`

## string_xrefs

- `0x1800b74f3`: `AddConditionEntries:JetCommitTransaction1`
- `0x1800b74ce`: `AddConditionEntries:JetUpdate`
- `0x1800b7418`: `AddConditionEntries:JetPrepareUpdate`
- `0x1800b765e`: `AddConditionEntries:JetUPdate2`
- `0x1800b759d`: `AddConditionEntries:JetPrepareUpdate2`
- `0x1800b7687`: `AddConditionEntries:JetCommitTransaction2`

## pseudocode

```c
__int64 __fastcall AddConditionEntries(JET_SESID sesid, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  JET_TABLEID v5; // rsi
  unsigned int *v8; // rax
  unsigned int AvailablePolicyCondnId; // ebx
  unsigned int v10; // r12d
  __int64 v11; // r14
  unsigned int v12; // eax
  __int64 v13; // rcx
  unsigned int Key; // eax
  __int64 v15; // r13
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  _WORD *v19; // r8
  __int64 v20; // rax
  unsigned int v21; // r9d
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  __int64 v25; // rdx
  int v26; // ecx
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  __int64 v30; // r12
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  __int64 v34; // rax
  __int64 v35; // rax
  unsigned int v36; // eax
  unsigned int v37; // eax
  unsigned int v38; // eax
  unsigned int v40; // eax
  unsigned int v41; // eax
  __int64 v42; // rax
  unsigned int v43; // eax
  unsigned int v44; // eax
  unsigned int v45; // eax
  char pvData; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 v47; // [rsp+41h] [rbp-BFh]
  int v48; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v49; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v50; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v51; // [rsp+54h] [rbp-ACh]
  __int64 v52; // [rsp+58h] [rbp-A8h]
  __int64 v53; // [rsp+60h] [rbp-A0h]
  JET_SETCOLUMN psetcolumn; // [rsp+70h] [rbp-90h] BYREF
  JET_COLUMNID v55; // [rsp+98h] [rbp-68h]
  int *v56; // [rsp+A0h] [rbp-60h]
  int v57; // [rsp+A8h] [rbp-58h]
  __int64 v58; // [rsp+ACh] [rbp-54h]
  __int64 v59; // [rsp+B4h] [rbp-4Ch]

  v5 = PolicyConditionTableId;
  v53 = a5;
  v8 = *(unsigned int **)(a3 + 24);
  AvailablePolicyCondnId = 0;
  v52 = a4;
  v10 = 0;
  v47 = 1;
  v51 = *v8;
  v49 = 0;
  v48 = 0;
  v50 = 0;
  pvData = 0;
  if ( v51 )
  {
    v11 = 0;
    while ( 1 )
    {
      v12 = JetSetCurrentIndexA(sesid, v5, "PolicyConditionTable_Index4");
      AvailablePolicyCondnId = PolicyMapJetError(v12, "AddConditionEntries:JetSetCurrentIndex");
      if ( AvailablePolicyCondnId )
        return AvailablePolicyCondnId;
      v13 = *(_QWORD *)(*(_QWORD *)(a3 + 24) + 8LL);
      if ( *(_DWORD *)(v13 + v11 + 4) == 3 )
        CharLowerBuffW(*(LPWSTR *)(v13 + v11 + 32), *(_DWORD *)(v13 + v11 + 40) >> 1);
      Key = JetMakeKey(sesid, v5, (const void *)(a3 + 12), 4u, 1u);
      AvailablePolicyCondnId = PolicyMapJetError(Key, "AddConditionEntries:JetMakeKey1");
      if ( AvailablePolicyCondnId )
        return AvailablePolicyCondnId;
      v15 = 48LL * v10;
      v16 = JetMakeKey(sesid, v5, (const void *)(v15 + *(_QWORD *)(*(_QWORD *)(a3 + 24) + 8LL) + 4LL), 4u, 0);
      AvailablePolicyCondnId = PolicyMapJetError(v16, "AddConditionEntries:JetMakeKey2");
      if ( AvailablePolicyCondnId )
        return AvailablePolicyCondnId;
      v17 = JetMakeKey(sesid, v5, (const void *)(v15 + *(_QWORD *)(*(_QWORD *)(a3 + 24) + 8LL) + 8LL), 4u, 0);
      AvailablePolicyCondnId = PolicyMapJetError(v17, "AddConditionEntries:JetMakeKey3");
      if ( AvailablePolicyCondnId )
        return AvailablePolicyCondnId;
      v18 = JetMakeKey(sesid, v5, (const void *)(v15 + *(_QWORD *)(*(_QWORD *)(a3 + 24) + 8LL) + 12LL), 4u, 0);
      AvailablePolicyCondnId = PolicyMapJetError(v18, "AddConditionEntries:JetMakeKey4");
      if ( AvailablePolicyCondnId )
        return AvailablePolicyCondnId;
      v19 = *(_WORD **)(*(_QWORD *)(*(_QWORD *)(a3 + 24) + 8LL) + v11 + 16);
      if ( v19 )
      {
        v20 = -1;
        do
          ++v20;
        while ( v19[v20] );
        v21 = 2 * v20 + 2;
      }
      else
      {
        v21 = 0;
      }
      v22 = JetMakeKey(sesid, v5, v19, v21, 0);
      AvailablePolicyCondnId = PolicyMapJetError(v22, "AddConditionEntries:JetMakeKey5");
      if ( AvailablePolicyCondnId )
        return AvailablePolicyCondnId;
      v23 = JetMakeKey(sesid, v5, (const void *)(v15 + *(_QWORD *)(*(_QWORD *)(a3 + 24) + 8LL) + 24LL), 4u, 0);
      AvailablePolicyCondnId = PolicyMapJetError(v23, "AddConditionEntries:JetMakeKey6");
      if ( AvailablePolicyCondnId )
        return AvailablePolicyCondnId;
      v24 = JetMakeKey(
              sesid,
              v5,
              *(const void **)(*(_QWORD *)(*(_QWORD *)(a3 + 24) + 8LL) + v11 + 32),
              *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 24) + 8LL) + v11 + 40),
              0);
      AvailablePolicyCondnId = PolicyMapJetError(v24, "AddConditionEntries:JetMakeKey7");
      if ( AvailablePolicyCondnId )
        return AvailablePolicyCondnId;
      v25 = *(_QWORD *)(a3 + 24);
      v26 = *(_DWORD *)(*(_QWORD *)(v25 + 8) + v11 + 24);
      if ( (unsigned int)(v26 - 2) <= 1 )
        break;
      if ( (unsigned int)(v26 - 4) <= 1 )
      {
        v47 = 0;
LABEL_23:
        pvData = 1;
        v27 = *(_DWORD *)(v11 + *(_QWORD *)(v25 + 8) + 40);
        goto LABEL_24;
      }
      pvData = 0;
      v27 = 0;
LABEL_24:
      v49 = v27;
      v28 = JetMakeKey(sesid, v5, &pvData, 1u, 0);
      AvailablePolicyCondnId = PolicyMapJetError(v28, "AddConditionEntries:JetMakeKey8");
      if ( AvailablePolicyCondnId )
        return AvailablePolicyCondnId;
      v29 = JetMakeKey(sesid, v5, &v49, 4u, 0);
      AvailablePolicyCondnId = PolicyMapJetError(v29, "AddConditionEntries:JetMakeKey9");
      if ( AvailablePolicyCondnId )
        return AvailablePolicyCondnId;
      v30 = (unsigned int)JetSeek(sesid, v5, 1u);
      AvailablePolicyCondnId = PolicyMapJetError(v30, "AddConditionEntries:JetSeek");
      if ( (_DWORD)v30 )
      {
        if ( (_DWORD)v30 != -1601 )
          return AvailablePolicyCondnId;
        AvailablePolicyCondnId = GetAvailablePolicyCondnId(sesid, (__int64)&v50);
        if ( AvailablePolicyCondnId )
          return AvailablePolicyCondnId;
        v40 = JetBeginTransaction(sesid);
        AvailablePolicyCondnId = PolicyMapJetError(v40, "AddConditionEntries:JetBeginTransaction2");
        if ( AvailablePolicyCondnId )
          return AvailablePolicyCondnId;
        v41 = JetPrepareUpdate(sesid, v5, 0);
        AvailablePolicyCondnId = PolicyMapJetError(v41, "AddConditionEntries:JetPrepareUpdate2");
        if ( AvailablePolicyCondnId )
          goto LABEL_33;
        v42 = *(_QWORD *)(a3 + 24);
        v48 = 1;
        FillCondnSetColumnData(
          v15 + *(_QWORD *)(v42 + 8),
          a3 + 12,
          (unsigned int)&v50,
          v52 + 4 * *(_DWORD *)(*(_QWORD *)(v42 + 8) + v11),
          (__int64)&pvData,
          (__int64)&v49,
          (__int64)&v48,
          (__int64)&psetcolumn);
        v43 = JetSetColumns(sesid, v5, &psetcolumn, 0xCu);
        AvailablePolicyCondnId = PolicyMapJetError(v43, "AddConditionEntries:JetSetColumns2");
        if ( AvailablePolicyCondnId
          || (v44 = JetUpdate(sesid, v5, 0, 0, 0),
              (AvailablePolicyCondnId = PolicyMapJetError(v44, "AddConditionEntries:JetUPdate2")) != 0)
          || (v45 = JetCommitTransaction(sesid, 0),
              (AvailablePolicyCondnId = PolicyMapJetError(v45, "AddConditionEntries:JetCommitTransaction2")) != 0) )
        {
LABEL_33:
          JetRollback(sesid, 0);
          return AvailablePolicyCondnId;
        }
        if ( v49 )
        {
          AvailablePolicyCondnId = AddWildCardLengthToSubnet(v53, *(unsigned int *)(a3 + 12), v49, v47);
          if ( AvailablePolicyCondnId )
            return AvailablePolicyCondnId;
        }
      }
      else
      {
        v31 = JetRetrieveColumn(sesid, v5, dword_1800F9658, &v48, 4u, 0, 1u, 0);
        AvailablePolicyCondnId = PolicyMapJetError(v31, "AddConditionEntries:JetRetrieveColumn");
        if ( AvailablePolicyCondnId )
          return AvailablePolicyCondnId;
        v32 = JetBeginTransaction(sesid);
        AvailablePolicyCondnId = PolicyMapJetError(v32, "AddConditionEntries:JetBeginTransaction1");
        if ( AvailablePolicyCondnId )
          return AvailablePolicyCondnId;
        v33 = JetPrepareUpdate(sesid, v5, 2u);
        AvailablePolicyCondnId = PolicyMapJetError(v33, "AddConditionEntries:JetPrepareUpdate");
        if ( AvailablePolicyCondnId )
          goto LABEL_33;
        psetcolumn.columnid = dword_1800F9670;
        v34 = *(_QWORD *)(a3 + 24);
        *(_QWORD *)&psetcolumn.itagSequence = 0;
        *(_QWORD *)&psetcolumn.grbit = 0;
        v35 = *(unsigned int *)(*(_QWORD *)(v34 + 8) + v11);
        ++v48;
        psetcolumn.cbData = 4;
        v59 = 0;
        v58 = 0;
        v55 = dword_1800F9658;
        psetcolumn.pvData = (const void *)(v52 + 4 * v35);
        v56 = &v48;
        v57 = 4;
        v36 = JetSetColumns(sesid, v5, &psetcolumn, 2u);
        AvailablePolicyCondnId = PolicyMapJetError(v36, "AddConditionEntries:JetSetColumns");
        if ( AvailablePolicyCondnId )
          goto LABEL_33;
        v37 = JetUpdate(sesid, v5, 0, 0, 0);
        AvailablePolicyCondnId = PolicyMapJetError(v37, "AddConditionEntries:JetUpdate");
        if ( AvailablePolicyCondnId )
          goto LABEL_33;
        v38 = JetCommitTransaction(sesid, 0);
        AvailablePolicyCondnId = PolicyMapJetError(v38, "AddConditionEntries:JetCommitTransaction1");
        if ( AvailablePolicyCondnId )
          goto LABEL_33;
      }
      v11 += 48;
      v10 = HIDWORD(v50) + 1;
      HIDWORD(v50) = v10;
      if ( v10 >= v51 )
        return AvailablePolicyCondnId;
    }
    v47 = 1;
    goto LABEL_23;
  }
  return AvailablePolicyCondnId;
}

```

## disassembly

```asm
0x1800b6fc8  mov     [rsp-8+arg_8], rbx
0x1800b6fcd  push    rbp
0x1800b6fce  push    rsi
0x1800b6fcf  push    rdi
0x1800b6fd0  push    r12
0x1800b6fd2  push    r13
0x1800b6fd4  push    r14
0x1800b6fd6  push    r15
0x1800b6fd8  lea     rbp, [rsp-160h]
0x1800b6fe0  sub     rsp, 260h
0x1800b6fe7  mov     rax, cs:__security_cookie
0x1800b6fee  xor     rax, rsp
0x1800b6ff1  mov     [rbp+190h+var_40], rax
0x1800b6ff8  mov     rax, [rbp+190h+arg_20]
0x1800b6fff  xor     r13d, r13d
0x1800b7002  mov     rsi, cs:PolicyConditionTableId
0x1800b7009  mov     r15, r8
0x1800b700c  mov     [rsp+290h+var_230], rax
0x1800b7011  mov     rdi, rcx
0x1800b7014  mov     rax, [r8+18h]
0x1800b7018  mov     ebx, r13d
0x1800b701b  mov     [rsp+290h+var_238], r9
0x1800b7020  mov     r12d, r13d
0x1800b7023  mov     [rsp+290h+var_24F], 1
0x1800b7028  mov     dword ptr [rsp+290h+var_244+4], r13d
0x1800b702d  mov     eax, [rax]
0x1800b702f  mov     [rsp+290h+var_23C], eax
0x1800b7033  mov     [rsp+290h+var_248], r13d
0x1800b7038  mov     [rsp+290h+var_24C], r13d
0x1800b703d  mov     dword ptr [rsp+290h+var_244], r13d
0x1800b7042  mov     [rsp+290h+pvData], r13b
0x1800b7047  test    eax, eax
0x1800b7049  jz      loc_1800B751A
0x1800b704f  mov     r14d, r13d
0x1800b7052  lea     r8, aPolicyconditio_0; "PolicyConditionTable_Index4"
0x1800b7059  mov     rdx, rsi; tableid
0x1800b705c  mov     rcx, rdi; sesid
0x1800b705f  call    cs:__imp_JetSetCurrentIndexA
0x1800b7066  nop     dword ptr [rax+rax+00h]
0x1800b706b  mov     ecx, eax
0x1800b706d  lea     rdx, aAddconditionen_13; "AddConditionEntries:JetSetCurrentIndex"
0x1800b7074  call    PolicyMapJetError
0x1800b7079  mov     ebx, eax
0x1800b707b  test    eax, eax
0x1800b707d  jnz     loc_1800B751A
0x1800b7083  mov     rax, [r15+18h]
0x1800b7087  mov     rcx, [rax+8]
0x1800b708b  cmp     dword ptr [rcx+r14+4], 3
0x1800b7091  jnz     short loc_1800B70AB
0x1800b7093  mov     edx, [rcx+r14+28h]
0x1800b7098  mov     rcx, [rcx+r14+20h]; lpsz
0x1800b709d  shr     edx, 1; cchLength
0x1800b709f  call    cs:__imp_CharLowerBuffW
0x1800b70a6  nop     dword ptr [rax+rax+00h]
0x1800b70ab  lea     r8, [r15+0Ch]; pvData
0x1800b70af  mov     [rsp+290h+grbit], 1; grbit
0x1800b70b7  mov     r9d, 4; cbData
0x1800b70bd  mov     rdx, rsi; tableid
0x1800b70c0  mov     rcx, rdi; sesid
0x1800b70c3  call    cs:__imp_JetMakeKey
0x1800b70ca  nop     dword ptr [rax+rax+00h]
0x1800b70cf  mov     ecx, eax
0x1800b70d1  lea     rdx, aAddconditionen_18; "AddConditionEntries:JetMakeKey1"
0x1800b70d8  call    PolicyMapJetError
0x1800b70dd  mov     ebx, eax
0x1800b70df  test    eax, eax
0x1800b70e1  jnz     loc_1800B751A
0x1800b70e7  mov     eax, r12d
0x1800b70ea  lea     r9d, [rbx+4]; cbData
0x1800b70ee  xor     r12d, r12d
0x1800b70f1  mov     rdx, rsi; tableid
0x1800b70f4  mov     rcx, rdi; sesid
0x1800b70f7  mov     [rsp+290h+grbit], r12d; grbit
0x1800b70fc  lea     r13, [rax+rax*2]
0x1800b7100  mov     rax, [r15+18h]
0x1800b7104  shl     r13, 4
0x1800b7108  mov     r8, [rax+8]
0x1800b710c  add     r8, 4
0x1800b7110  add     r8, r13; pvData
0x1800b7113  call    cs:__imp_JetMakeKey
0x1800b711a  nop     dword ptr [rax+rax+00h]
0x1800b711f  mov     ecx, eax
0x1800b7121  lea     rdx, aAddconditionen_9; "AddConditionEntries:JetMakeKey2"
0x1800b7128  call    PolicyMapJetError
0x1800b712d  mov     ebx, eax
0x1800b712f  test    eax, eax
0x1800b7131  jnz     loc_1800B751A
0x1800b7137  mov     rax, [r15+18h]
0x1800b713b  lea     r9d, [r12+4]; cbData
0x1800b7140  mov     rdx, rsi; tableid
0x1800b7143  mov     [rsp+290h+grbit], r12d; grbit
0x1800b7148  mov     rcx, rdi; sesid
0x1800b714b  mov     r8, [rax+8]
0x1800b714f  add     r8, 8
0x1800b7153  add     r8, r13; pvData
0x1800b7156  call    cs:__imp_JetMakeKey
0x1800b715d  nop     dword ptr [rax+rax+00h]
0x1800b7162  mov     ecx, eax
0x1800b7164  lea     rdx, aAddconditionen_5; "AddConditionEntries:JetMakeKey3"
0x1800b716b  call    PolicyMapJetError
0x1800b7170  mov     ebx, eax
0x1800b7172  test    eax, eax
0x1800b7174  jnz     loc_1800B751A
0x1800b717a  mov     rax, [r15+18h]
0x1800b717e  lea     r9d, [r12+4]; cbData
0x1800b7183  mov     rdx, rsi; tableid
0x1800b7186  mov     [rsp+290h+grbit], r12d; grbit
0x1800b718b  mov     rcx, rdi; sesid
0x1800b718e  mov     r8, [rax+8]
0x1800b7192  add     r8, 0Ch
0x1800b7196  add     r8, r13; pvData
0x1800b7199  call    cs:__imp_JetMakeKey
0x1800b71a0  nop     dword ptr [rax+rax+00h]
0x1800b71a5  mov     ecx, eax
0x1800b71a7  lea     rdx, aAddconditionen_11; "AddConditionEntries:JetMakeKey4"
0x1800b71ae  call    PolicyMapJetError
0x1800b71b3  mov     ebx, eax
0x1800b71b5  test    eax, eax
0x1800b71b7  jnz     loc_1800B751A
0x1800b71bd  mov     rax, [r15+18h]
0x1800b71c1  mov     rcx, [rax+8]
0x1800b71c5  mov     r8, [rcx+r14+10h]; pvData
0x1800b71ca  test    r8, r8
0x1800b71cd  jz      short loc_1800B71E7
0x1800b71cf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b71d3  inc     rax
0x1800b71d6  cmp     [r8+rax*2], r12w
0x1800b71db  jnz     short loc_1800B71D3
0x1800b71dd  lea     r9d, ds:2[rax*2]
0x1800b71e5  jmp     short loc_1800B71EA
0x1800b71e7  mov     r9d, r12d; cbData
0x1800b71ea  mov     rdx, rsi; tableid
0x1800b71ed  mov     [rsp+290h+grbit], r12d; grbit
0x1800b71f2  mov     rcx, rdi; sesid
0x1800b71f5  call    cs:__imp_JetMakeKey
0x1800b71fc  nop     dword ptr [rax+rax+00h]
0x1800b7201  mov     ecx, eax
0x1800b7203  lea     rdx, aAddconditionen_0; "AddConditionEntries:JetMakeKey5"
0x1800b720a  call    PolicyMapJetError
0x1800b720f  mov     ebx, eax
0x1800b7211  test    eax, eax
0x1800b7213  jnz     loc_1800B751A
0x1800b7219  mov     rax, [r15+18h]
0x1800b721d  lea     r9d, [rbx+4]; cbData
0x1800b7221  mov     rdx, rsi; tableid
0x1800b7224  mov     [rsp+290h+grbit], r12d; grbit
0x1800b7229  mov     rcx, rdi; sesid
0x1800b722c  mov     r8, [rax+8]
0x1800b7230  add     r8, 18h
0x1800b7234  add     r8, r13; pvData
0x1800b7237  call    cs:__imp_JetMakeKey
0x1800b723e  nop     dword ptr [rax+rax+00h]
0x1800b7243  mov     ecx, eax
0x1800b7245  lea     rdx, aAddconditionen_20; "AddConditionEntries:JetMakeKey6"
0x1800b724c  call    PolicyMapJetError
0x1800b7251  mov     ebx, eax
0x1800b7253  test    eax, eax
0x1800b7255  jnz     loc_1800B751A
0x1800b725b  mov     rax, [r15+18h]
0x1800b725f  mov     rdx, rsi; tableid
0x1800b7262  mov     rcx, rdi; sesid
0x1800b7265  mov     [rsp+290h+grbit], r12d; grbit
0x1800b726a  mov     r8, [rax+8]
0x1800b726e  mov     r9d, [r8+r14+28h]; cbData
0x1800b7273  mov     r8, [r8+r14+20h]; pvData
0x1800b7278  call    cs:__imp_JetMakeKey
0x1800b727f  nop     dword ptr [rax+rax+00h]
0x1800b7284  mov     ecx, eax
0x1800b7286  lea     rdx, aAddconditionen_1; "AddConditionEntries:JetMakeKey7"
0x1800b728d  call    PolicyMapJetError
0x1800b7292  mov     ebx, eax
0x1800b7294  test    eax, eax
0x1800b7296  jnz     loc_1800B751A
0x1800b729c  mov     rdx, [r15+18h]
0x1800b72a0  mov     rax, [rdx+8]
0x1800b72a4  mov     ecx, [rax+r14+18h]
0x1800b72a9  lea     eax, [rcx-2]
0x1800b72ac  cmp     eax, 1
0x1800b72af  jbe     short loc_1800B72CA
0x1800b72b1  lea     eax, [rcx-4]
0x1800b72b4  cmp     eax, 1
0x1800b72b7  jbe     short loc_1800B72C3
0x1800b72b9  mov     [rsp+290h+pvData], r12b
0x1800b72be  mov     eax, r12d
0x1800b72c1  jmp     short loc_1800B72DD
0x1800b72c3  mov     [rsp+290h+var_24F], r12b
0x1800b72c8  jmp     short loc_1800B72CF
0x1800b72ca  mov     [rsp+290h+var_24F], 1
0x1800b72cf  mov     [rsp+290h+pvData], 1
0x1800b72d4  mov     rax, [rdx+8]
0x1800b72d8  mov     eax, [r14+rax+28h]
0x1800b72dd  mov     r9d, 1; cbData
0x1800b72e3  mov     [rsp+290h+var_248], eax
0x1800b72e7  lea     r8, [rsp+290h+pvData]; pvData
0x1800b72ec  mov     [rsp+290h+grbit], r12d; grbit
0x1800b72f1  mov     rdx, rsi; tableid
0x1800b72f4  mov     rcx, rdi; sesid
0x1800b72f7  call    cs:__imp_JetMakeKey
0x1800b72fe  nop     dword ptr [rax+rax+00h]
0x1800b7303  mov     ecx, eax
0x1800b7305  lea     rdx, aAddconditionen_4; "AddConditionEntries:JetMakeKey8"
0x1800b730c  call    PolicyMapJetError
0x1800b7311  mov     ebx, eax
0x1800b7313  test    eax, eax
0x1800b7315  jnz     loc_1800B751A
0x1800b731b  lea     r9d, [rax+4]; cbData
0x1800b731f  mov     [rsp+290h+grbit], r12d; grbit
0x1800b7324  lea     r8, [rsp+290h+var_248]; pvData
0x1800b7329  mov     rdx, rsi; tableid
0x1800b732c  mov     rcx, rdi; sesid
0x1800b732f  call    cs:__imp_JetMakeKey
0x1800b7336  nop     dword ptr [rax+rax+00h]
0x1800b733b  mov     ecx, eax
0x1800b733d  lea     rdx, aAddconditionen_15; "AddConditionEntries:JetMakeKey9"
0x1800b7344  call    PolicyMapJetError
0x1800b7349  mov     ebx, eax
0x1800b734b  test    eax, eax
0x1800b734d  jnz     loc_1800B751A
0x1800b7353  lea     r8d, [rax+1]; grbit
0x1800b7357  mov     rdx, rsi; tableid
0x1800b735a  mov     rcx, rdi; sesid
0x1800b735d  call    cs:__imp_JetSeek
0x1800b7364  nop     dword ptr [rax+rax+00h]
0x1800b7369  mov     ecx, eax
0x1800b736b  lea     rdx, aAddconditionen_19; "AddConditionEntries:JetSeek"
0x1800b7372  mov     r12d, eax
0x1800b7375  call    PolicyMapJetError
0x1800b737a  mov     ebx, eax
0x1800b737c  test    r12d, r12d
0x1800b737f  jnz     loc_1800B7547
0x1800b7385  mov     r8d, cs:dword_1800F9658; columnid
0x1800b738c  lea     r9, [rsp+290h+var_24C]; pvData
0x1800b7391  xor     r13d, r13d
0x1800b7394  mov     rdx, rsi; tableid
0x1800b7397  mov     [rsp+290h+pretinfo], r13; pretinfo
0x1800b739c  mov     rcx, rdi; sesid
0x1800b739f  mov     [rsp+290h+var_260], 1; grbit
0x1800b73a7  mov     [rsp+290h+pcbActual], r13; pcbActual
0x1800b73ac  lea     r12d, [r13+4]
0x1800b73b0  mov     [rsp+290h+grbit], r12d; cbData
0x1800b73b5  call    cs:__imp_JetRetrieveColumn
0x1800b73bc  nop     dword ptr [rax+rax+00h]
0x1800b73c1  mov     ecx, eax
0x1800b73c3  lea     rdx, aAddconditionen_6; "AddConditionEntries:JetRetrieveColumn"
0x1800b73ca  call    PolicyMapJetError
0x1800b73cf  mov     ebx, eax
0x1800b73d1  test    eax, eax
0x1800b73d3  jnz     loc_1800B751A
0x1800b73d9  mov     rcx, rdi; sesid
0x1800b73dc  call    cs:__imp_JetBeginTransaction
0x1800b73e3  nop     dword ptr [rax+rax+00h]
0x1800b73e8  mov     ecx, eax
0x1800b73ea  lea     rdx, aAddconditionen_17; "AddConditionEntries:JetBeginTransaction"...
0x1800b73f1  call    PolicyMapJetError
0x1800b73f6  mov     ebx, eax
0x1800b73f8  test    eax, eax
0x1800b73fa  jnz     loc_1800B751A
0x1800b7400  lea     r8d, [r13+2]; prep
0x1800b7404  mov     rdx, rsi; tableid
0x1800b7407  mov     rcx, rdi; sesid
0x1800b740a  call    cs:__imp_JetPrepareUpdate
0x1800b7411  nop     dword ptr [rax+rax+00h]
0x1800b7416  mov     ecx, eax
0x1800b7418  lea     rdx, aAddconditionen_2; "AddConditionEntries:JetPrepareUpdate"
0x1800b741f  call    PolicyMapJetError
0x1800b7424  mov     ebx, eax
0x1800b7426  test    eax, eax
0x1800b7428  jnz     loc_1800B7509
0x1800b742e  mov     eax, cs:dword_1800F9670
0x1800b7434  lea     r9d, [r13+2]; csetcolumn
0x1800b7438  mov     [rsp+290h+psetcolumn.columnid], eax
0x1800b743c  lea     r8, [rsp+290h+psetcolumn]; psetcolumn
0x1800b7441  mov     rax, [r15+18h]
0x1800b7445  mov     rdx, rsi; tableid
0x1800b7448  mov     qword ptr [rbp+190h+psetcolumn.itagSequence], r13
0x1800b744c  mov     qword ptr [rbp+190h+psetcolumn.grbit], r13
0x1800b7450  mov     rcx, [rax+8]
0x1800b7454  mov     eax, [rcx+r14]
0x1800b7458  mov     rcx, [rsp+290h+var_238]
0x1800b745d  inc     [rsp+290h+var_24C]
0x1800b7461  mov     [rbp+190h+psetcolumn.cbData], r12d
0x1800b7465  mov     [rbp+190h+var_1DC], r13
0x1800b7469  lea     rcx, [rcx+rax*4]
0x1800b746d  mov     [rbp+190h+var_1E4], r13
0x1800b7471  mov     eax, cs:dword_1800F9658
0x1800b7477  mov     [rbp+190h+var_1F8], eax
0x1800b747a  lea     rax, [rsp+290h+var_24C]
0x1800b747f  mov     [rsp+290h+psetcolumn.pvData], rcx
0x1800b7484  mov     rcx, rdi; sesid
0x1800b7487  mov     [rbp+190h+var_1F0], rax
0x1800b748b  mov     [rbp+190h+var_1E8], r12d
0x1800b748f  call    cs:__imp_JetSetColumns
0x1800b7496  nop     dword ptr [rax+rax+00h]
0x1800b749b  mov     ecx, eax
0x1800b749d  lea     rdx, aAddconditionen_7; "AddConditionEntries:JetSetColumns"
0x1800b74a4  call    PolicyMapJetError
0x1800b74a9  mov     ebx, eax
0x1800b74ab  test    eax, eax
0x1800b74ad  jnz     short loc_1800B7509
0x1800b74af  xor     r9d, r9d; cbBookmark
  ... truncated ...
```
