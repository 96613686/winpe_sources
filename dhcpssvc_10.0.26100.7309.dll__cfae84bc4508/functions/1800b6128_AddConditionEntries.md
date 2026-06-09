# AddConditionEntries

- ea: `0x1800b6128`
- end: `0x1800b6846`
- name: `AddConditionEntries`
- size: `1822`
- prototype: `__int64 __usercall@<rax>(JET_SESID sesid@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800b7248`
- `0x1800bc1fc`

## callees

- `0x1800b6128`
- `0x1800b7cbc`
- `0x1800ba188`
- `0x1800ba740`
- `0x1800bba04`
- `0x1800cc9e0`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800b61bf`
- `ESENT!JetSetCurrentIndexA` at `0x1800b61bf`
- `ESENT!JetSetColumns` at `0x1800b65ef`
- `ESENT!JetSetColumns` at `0x1800b6778`
- `ESENT!JetSetColumns` at `0x1800b65ef`
- `ESENT!JetSetColumns` at `0x1800b6778`
- `ESENT!JetUpdate` at `0x1800b6620`
- `ESENT!JetUpdate` at `0x1800b67b0`
- `ESENT!JetUpdate` at `0x1800b6620`
- `ESENT!JetUpdate` at `0x1800b67b0`
- `ESENT!JetMakeKey` at `0x1800b6223`
- `ESENT!JetMakeKey` at `0x1800b6273`
- `ESENT!JetMakeKey` at `0x1800b62b6`
- `ESENT!JetMakeKey` at `0x1800b62f9`
- `ESENT!JetMakeKey` at `0x1800b6355`
- `ESENT!JetMakeKey` at `0x1800b6397`
- `ESENT!JetMakeKey` at `0x1800b63d8`
- `ESENT!JetMakeKey` at `0x1800b6457`
- `ESENT!JetMakeKey` at `0x1800b648f`
- `ESENT!JetMakeKey` at `0x1800b6223`
- `ESENT!JetMakeKey` at `0x1800b6273`
- `ESENT!JetMakeKey` at `0x1800b62b6`
- `ESENT!JetMakeKey` at `0x1800b62f9`
- `ESENT!JetMakeKey` at `0x1800b6355`
- `ESENT!JetMakeKey` at `0x1800b6397`
- `ESENT!JetMakeKey` at `0x1800b63d8`
- `ESENT!JetMakeKey` at `0x1800b6457`
- `ESENT!JetMakeKey` at `0x1800b648f`
- `ESENT!JetSeek` at `0x1800b64bd`
- `ESENT!JetSeek` at `0x1800b64bd`
- `ESENT!JetBeginTransaction` at `0x1800b653c`
- `ESENT!JetBeginTransaction` at `0x1800b66c6`
- `ESENT!JetBeginTransaction` at `0x1800b653c`
- `ESENT!JetBeginTransaction` at `0x1800b66c6`
- `ESENT!JetRollback` at `0x1800b666e`
- `ESENT!JetRollback` at `0x1800b666e`
- `ESENT!JetCommitTransaction` at `0x1800b6645`
- `ESENT!JetCommitTransaction` at `0x1800b67d9`
- `ESENT!JetCommitTransaction` at `0x1800b6645`
- `ESENT!JetCommitTransaction` at `0x1800b67d9`
- `ESENT!JetPrepareUpdate` at `0x1800b656a`
- `ESENT!JetPrepareUpdate` at `0x1800b66ef`
- `ESENT!JetPrepareUpdate` at `0x1800b656a`
- `ESENT!JetPrepareUpdate` at `0x1800b66ef`
- `ESENT!JetRetrieveColumn` at `0x1800b6515`
- `ESENT!JetRetrieveColumn` at `0x1800b6515`
- `USER32!CharLowerBuffW` at `0x1800b61ff`
- `USER32!CharLowerBuffW` at `0x1800b61ff`

## string_xrefs

- `0x1800b6578`: `AddConditionEntries:JetPrepareUpdate`
- `0x1800b66fd`: `AddConditionEntries:JetPrepareUpdate2`
- `0x1800b662e`: `AddConditionEntries:JetUpdate`
- `0x1800b6653`: `AddConditionEntries:JetCommitTransaction1`
- `0x1800b67e7`: `AddConditionEntries:JetCommitTransaction2`
- `0x1800b67be`: `AddConditionEntries:JetUPdate2`

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
        v31 = JetRetrieveColumn(sesid, v5, dword_1800F7848, &v48, 4u, 0, 1u, 0);
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
        psetcolumn.columnid = dword_1800F7860;
        v34 = *(_QWORD *)(a3 + 24);
        *(_QWORD *)&psetcolumn.itagSequence = 0;
        *(_QWORD *)&psetcolumn.grbit = 0;
        v35 = *(unsigned int *)(*(_QWORD *)(v34 + 8) + v11);
        ++v48;
        psetcolumn.cbData = 4;
        v59 = 0;
        v58 = 0;
        v55 = dword_1800F7848;
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
0x1800b6128  mov     [rsp-8+arg_8], rbx
0x1800b612d  push    rbp
0x1800b612e  push    rsi
0x1800b612f  push    rdi
0x1800b6130  push    r12
0x1800b6132  push    r13
0x1800b6134  push    r14
0x1800b6136  push    r15
0x1800b6138  lea     rbp, [rsp-160h]
0x1800b6140  sub     rsp, 260h
0x1800b6147  mov     rax, cs:__security_cookie
0x1800b614e  xor     rax, rsp
0x1800b6151  mov     [rbp+190h+var_40], rax
0x1800b6158  mov     rax, [rbp+190h+arg_20]
0x1800b615f  xor     r13d, r13d
0x1800b6162  mov     rsi, cs:PolicyConditionTableId
0x1800b6169  mov     r15, r8
0x1800b616c  mov     [rsp+290h+var_230], rax
0x1800b6171  mov     rdi, rcx
0x1800b6174  mov     rax, [r8+18h]
0x1800b6178  mov     ebx, r13d
0x1800b617b  mov     [rsp+290h+var_238], r9
0x1800b6180  mov     r12d, r13d
0x1800b6183  mov     [rsp+290h+var_24F], 1
0x1800b6188  mov     dword ptr [rsp+290h+var_244+4], r13d
0x1800b618d  mov     eax, [rax]
0x1800b618f  mov     [rsp+290h+var_23C], eax
0x1800b6193  mov     [rsp+290h+var_248], r13d
0x1800b6198  mov     [rsp+290h+var_24C], r13d
0x1800b619d  mov     dword ptr [rsp+290h+var_244], r13d
0x1800b61a2  mov     [rsp+290h+pvData], r13b
0x1800b61a7  test    eax, eax
0x1800b61a9  jz      loc_1800B667A
0x1800b61af  mov     r14d, r13d
0x1800b61b2  lea     r8, aPolicyconditio_0; "PolicyConditionTable_Index4"
0x1800b61b9  mov     rdx, rsi; tableid
0x1800b61bc  mov     rcx, rdi; sesid
0x1800b61bf  call    cs:__imp_JetSetCurrentIndexA
0x1800b61c6  nop     dword ptr [rax+rax+00h]
0x1800b61cb  mov     ecx, eax
0x1800b61cd  lea     rdx, aAddconditionen_13; "AddConditionEntries:JetSetCurrentIndex"
0x1800b61d4  call    PolicyMapJetError
0x1800b61d9  mov     ebx, eax
0x1800b61db  test    eax, eax
0x1800b61dd  jnz     loc_1800B667A
0x1800b61e3  mov     rax, [r15+18h]
0x1800b61e7  mov     rcx, [rax+8]
0x1800b61eb  cmp     dword ptr [rcx+r14+4], 3
0x1800b61f1  jnz     short loc_1800B620B
0x1800b61f3  mov     edx, [rcx+r14+28h]
0x1800b61f8  mov     rcx, [rcx+r14+20h]; lpsz
0x1800b61fd  shr     edx, 1; cchLength
0x1800b61ff  call    cs:__imp_CharLowerBuffW
0x1800b6206  nop     dword ptr [rax+rax+00h]
0x1800b620b  lea     r8, [r15+0Ch]; pvData
0x1800b620f  mov     [rsp+290h+grbit], 1; grbit
0x1800b6217  mov     r9d, 4; cbData
0x1800b621d  mov     rdx, rsi; tableid
0x1800b6220  mov     rcx, rdi; sesid
0x1800b6223  call    cs:__imp_JetMakeKey
0x1800b622a  nop     dword ptr [rax+rax+00h]
0x1800b622f  mov     ecx, eax
0x1800b6231  lea     rdx, aAddconditionen_18; "AddConditionEntries:JetMakeKey1"
0x1800b6238  call    PolicyMapJetError
0x1800b623d  mov     ebx, eax
0x1800b623f  test    eax, eax
0x1800b6241  jnz     loc_1800B667A
0x1800b6247  mov     eax, r12d
0x1800b624a  lea     r9d, [rbx+4]; cbData
0x1800b624e  xor     r12d, r12d
0x1800b6251  mov     rdx, rsi; tableid
0x1800b6254  mov     rcx, rdi; sesid
0x1800b6257  mov     [rsp+290h+grbit], r12d; grbit
0x1800b625c  lea     r13, [rax+rax*2]
0x1800b6260  mov     rax, [r15+18h]
0x1800b6264  shl     r13, 4
0x1800b6268  mov     r8, [rax+8]
0x1800b626c  add     r8, 4
0x1800b6270  add     r8, r13; pvData
0x1800b6273  call    cs:__imp_JetMakeKey
0x1800b627a  nop     dword ptr [rax+rax+00h]
0x1800b627f  mov     ecx, eax
0x1800b6281  lea     rdx, aAddconditionen_9; "AddConditionEntries:JetMakeKey2"
0x1800b6288  call    PolicyMapJetError
0x1800b628d  mov     ebx, eax
0x1800b628f  test    eax, eax
0x1800b6291  jnz     loc_1800B667A
0x1800b6297  mov     rax, [r15+18h]
0x1800b629b  lea     r9d, [r12+4]; cbData
0x1800b62a0  mov     rdx, rsi; tableid
0x1800b62a3  mov     [rsp+290h+grbit], r12d; grbit
0x1800b62a8  mov     rcx, rdi; sesid
0x1800b62ab  mov     r8, [rax+8]
0x1800b62af  add     r8, 8
0x1800b62b3  add     r8, r13; pvData
0x1800b62b6  call    cs:__imp_JetMakeKey
0x1800b62bd  nop     dword ptr [rax+rax+00h]
0x1800b62c2  mov     ecx, eax
0x1800b62c4  lea     rdx, aAddconditionen_5; "AddConditionEntries:JetMakeKey3"
0x1800b62cb  call    PolicyMapJetError
0x1800b62d0  mov     ebx, eax
0x1800b62d2  test    eax, eax
0x1800b62d4  jnz     loc_1800B667A
0x1800b62da  mov     rax, [r15+18h]
0x1800b62de  lea     r9d, [r12+4]; cbData
0x1800b62e3  mov     rdx, rsi; tableid
0x1800b62e6  mov     [rsp+290h+grbit], r12d; grbit
0x1800b62eb  mov     rcx, rdi; sesid
0x1800b62ee  mov     r8, [rax+8]
0x1800b62f2  add     r8, 0Ch
0x1800b62f6  add     r8, r13; pvData
0x1800b62f9  call    cs:__imp_JetMakeKey
0x1800b6300  nop     dword ptr [rax+rax+00h]
0x1800b6305  mov     ecx, eax
0x1800b6307  lea     rdx, aAddconditionen_11; "AddConditionEntries:JetMakeKey4"
0x1800b630e  call    PolicyMapJetError
0x1800b6313  mov     ebx, eax
0x1800b6315  test    eax, eax
0x1800b6317  jnz     loc_1800B667A
0x1800b631d  mov     rax, [r15+18h]
0x1800b6321  mov     rcx, [rax+8]
0x1800b6325  mov     r8, [rcx+r14+10h]; pvData
0x1800b632a  test    r8, r8
0x1800b632d  jz      short loc_1800B6347
0x1800b632f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b6333  inc     rax
0x1800b6336  cmp     [r8+rax*2], r12w
0x1800b633b  jnz     short loc_1800B6333
0x1800b633d  lea     r9d, ds:2[rax*2]
0x1800b6345  jmp     short loc_1800B634A
0x1800b6347  mov     r9d, r12d; cbData
0x1800b634a  mov     rdx, rsi; tableid
0x1800b634d  mov     [rsp+290h+grbit], r12d; grbit
0x1800b6352  mov     rcx, rdi; sesid
0x1800b6355  call    cs:__imp_JetMakeKey
0x1800b635c  nop     dword ptr [rax+rax+00h]
0x1800b6361  mov     ecx, eax
0x1800b6363  lea     rdx, aAddconditionen_0; "AddConditionEntries:JetMakeKey5"
0x1800b636a  call    PolicyMapJetError
0x1800b636f  mov     ebx, eax
0x1800b6371  test    eax, eax
0x1800b6373  jnz     loc_1800B667A
0x1800b6379  mov     rax, [r15+18h]
0x1800b637d  lea     r9d, [rbx+4]; cbData
0x1800b6381  mov     rdx, rsi; tableid
0x1800b6384  mov     [rsp+290h+grbit], r12d; grbit
0x1800b6389  mov     rcx, rdi; sesid
0x1800b638c  mov     r8, [rax+8]
0x1800b6390  add     r8, 18h
0x1800b6394  add     r8, r13; pvData
0x1800b6397  call    cs:__imp_JetMakeKey
0x1800b639e  nop     dword ptr [rax+rax+00h]
0x1800b63a3  mov     ecx, eax
0x1800b63a5  lea     rdx, aAddconditionen_20; "AddConditionEntries:JetMakeKey6"
0x1800b63ac  call    PolicyMapJetError
0x1800b63b1  mov     ebx, eax
0x1800b63b3  test    eax, eax
0x1800b63b5  jnz     loc_1800B667A
0x1800b63bb  mov     rax, [r15+18h]
0x1800b63bf  mov     rdx, rsi; tableid
0x1800b63c2  mov     rcx, rdi; sesid
0x1800b63c5  mov     [rsp+290h+grbit], r12d; grbit
0x1800b63ca  mov     r8, [rax+8]
0x1800b63ce  mov     r9d, [r8+r14+28h]; cbData
0x1800b63d3  mov     r8, [r8+r14+20h]; pvData
0x1800b63d8  call    cs:__imp_JetMakeKey
0x1800b63df  nop     dword ptr [rax+rax+00h]
0x1800b63e4  mov     ecx, eax
0x1800b63e6  lea     rdx, aAddconditionen_1; "AddConditionEntries:JetMakeKey7"
0x1800b63ed  call    PolicyMapJetError
0x1800b63f2  mov     ebx, eax
0x1800b63f4  test    eax, eax
0x1800b63f6  jnz     loc_1800B667A
0x1800b63fc  mov     rdx, [r15+18h]
0x1800b6400  mov     rax, [rdx+8]
0x1800b6404  mov     ecx, [rax+r14+18h]
0x1800b6409  lea     eax, [rcx-2]
0x1800b640c  cmp     eax, 1
0x1800b640f  jbe     short loc_1800B642A
0x1800b6411  lea     eax, [rcx-4]
0x1800b6414  cmp     eax, 1
0x1800b6417  jbe     short loc_1800B6423
0x1800b6419  mov     [rsp+290h+pvData], r12b
0x1800b641e  mov     eax, r12d
0x1800b6421  jmp     short loc_1800B643D
0x1800b6423  mov     [rsp+290h+var_24F], r12b
0x1800b6428  jmp     short loc_1800B642F
0x1800b642a  mov     [rsp+290h+var_24F], 1
0x1800b642f  mov     [rsp+290h+pvData], 1
0x1800b6434  mov     rax, [rdx+8]
0x1800b6438  mov     eax, [r14+rax+28h]
0x1800b643d  mov     r9d, 1; cbData
0x1800b6443  mov     [rsp+290h+var_248], eax
0x1800b6447  lea     r8, [rsp+290h+pvData]; pvData
0x1800b644c  mov     [rsp+290h+grbit], r12d; grbit
0x1800b6451  mov     rdx, rsi; tableid
0x1800b6454  mov     rcx, rdi; sesid
0x1800b6457  call    cs:__imp_JetMakeKey
0x1800b645e  nop     dword ptr [rax+rax+00h]
0x1800b6463  mov     ecx, eax
0x1800b6465  lea     rdx, aAddconditionen_4; "AddConditionEntries:JetMakeKey8"
0x1800b646c  call    PolicyMapJetError
0x1800b6471  mov     ebx, eax
0x1800b6473  test    eax, eax
0x1800b6475  jnz     loc_1800B667A
0x1800b647b  lea     r9d, [rax+4]; cbData
0x1800b647f  mov     [rsp+290h+grbit], r12d; grbit
0x1800b6484  lea     r8, [rsp+290h+var_248]; pvData
0x1800b6489  mov     rdx, rsi; tableid
0x1800b648c  mov     rcx, rdi; sesid
0x1800b648f  call    cs:__imp_JetMakeKey
0x1800b6496  nop     dword ptr [rax+rax+00h]
0x1800b649b  mov     ecx, eax
0x1800b649d  lea     rdx, aAddconditionen_15; "AddConditionEntries:JetMakeKey9"
0x1800b64a4  call    PolicyMapJetError
0x1800b64a9  mov     ebx, eax
0x1800b64ab  test    eax, eax
0x1800b64ad  jnz     loc_1800B667A
0x1800b64b3  lea     r8d, [rax+1]; grbit
0x1800b64b7  mov     rdx, rsi; tableid
0x1800b64ba  mov     rcx, rdi; sesid
0x1800b64bd  call    cs:__imp_JetSeek
0x1800b64c4  nop     dword ptr [rax+rax+00h]
0x1800b64c9  mov     ecx, eax
0x1800b64cb  lea     rdx, aAddconditionen_19; "AddConditionEntries:JetSeek"
0x1800b64d2  mov     r12d, eax
0x1800b64d5  call    PolicyMapJetError
0x1800b64da  mov     ebx, eax
0x1800b64dc  test    r12d, r12d
0x1800b64df  jnz     loc_1800B66A7
0x1800b64e5  mov     r8d, cs:dword_1800F7848; columnid
0x1800b64ec  lea     r9, [rsp+290h+var_24C]; pvData
0x1800b64f1  xor     r13d, r13d
0x1800b64f4  mov     rdx, rsi; tableid
0x1800b64f7  mov     [rsp+290h+pretinfo], r13; pretinfo
0x1800b64fc  mov     rcx, rdi; sesid
0x1800b64ff  mov     [rsp+290h+var_260], 1; grbit
0x1800b6507  mov     [rsp+290h+pcbActual], r13; pcbActual
0x1800b650c  lea     r12d, [r13+4]
0x1800b6510  mov     [rsp+290h+grbit], r12d; cbData
0x1800b6515  call    cs:__imp_JetRetrieveColumn
0x1800b651c  nop     dword ptr [rax+rax+00h]
0x1800b6521  mov     ecx, eax
0x1800b6523  lea     rdx, aAddconditionen_6; "AddConditionEntries:JetRetrieveColumn"
0x1800b652a  call    PolicyMapJetError
0x1800b652f  mov     ebx, eax
0x1800b6531  test    eax, eax
0x1800b6533  jnz     loc_1800B667A
0x1800b6539  mov     rcx, rdi; sesid
0x1800b653c  call    cs:__imp_JetBeginTransaction
0x1800b6543  nop     dword ptr [rax+rax+00h]
0x1800b6548  mov     ecx, eax
0x1800b654a  lea     rdx, aAddconditionen_17; "AddConditionEntries:JetBeginTransaction"...
0x1800b6551  call    PolicyMapJetError
0x1800b6556  mov     ebx, eax
0x1800b6558  test    eax, eax
0x1800b655a  jnz     loc_1800B667A
0x1800b6560  lea     r8d, [r13+2]; prep
0x1800b6564  mov     rdx, rsi; tableid
0x1800b6567  mov     rcx, rdi; sesid
0x1800b656a  call    cs:__imp_JetPrepareUpdate
0x1800b6571  nop     dword ptr [rax+rax+00h]
0x1800b6576  mov     ecx, eax
0x1800b6578  lea     rdx, aAddconditionen_2; "AddConditionEntries:JetPrepareUpdate"
0x1800b657f  call    PolicyMapJetError
0x1800b6584  mov     ebx, eax
0x1800b6586  test    eax, eax
0x1800b6588  jnz     loc_1800B6669
0x1800b658e  mov     eax, cs:dword_1800F7860
0x1800b6594  lea     r9d, [r13+2]; csetcolumn
0x1800b6598  mov     [rsp+290h+psetcolumn.columnid], eax
0x1800b659c  lea     r8, [rsp+290h+psetcolumn]; psetcolumn
0x1800b65a1  mov     rax, [r15+18h]
0x1800b65a5  mov     rdx, rsi; tableid
0x1800b65a8  mov     qword ptr [rbp+190h+psetcolumn.itagSequence], r13
0x1800b65ac  mov     qword ptr [rbp+190h+psetcolumn.grbit], r13
0x1800b65b0  mov     rcx, [rax+8]
0x1800b65b4  mov     eax, [rcx+r14]
0x1800b65b8  mov     rcx, [rsp+290h+var_238]
0x1800b65bd  inc     [rsp+290h+var_24C]
0x1800b65c1  mov     [rbp+190h+psetcolumn.cbData], r12d
0x1800b65c5  mov     [rbp+190h+var_1DC], r13
0x1800b65c9  lea     rcx, [rcx+rax*4]
0x1800b65cd  mov     [rbp+190h+var_1E4], r13
0x1800b65d1  mov     eax, cs:dword_1800F7848
0x1800b65d7  mov     [rbp+190h+var_1F8], eax
0x1800b65da  lea     rax, [rsp+290h+var_24C]
0x1800b65df  mov     [rsp+290h+psetcolumn.pvData], rcx
0x1800b65e4  mov     rcx, rdi; sesid
0x1800b65e7  mov     [rbp+190h+var_1F0], rax
0x1800b65eb  mov     [rbp+190h+var_1E8], r12d
0x1800b65ef  call    cs:__imp_JetSetColumns
0x1800b65f6  nop     dword ptr [rax+rax+00h]
0x1800b65fb  mov     ecx, eax
0x1800b65fd  lea     rdx, aAddconditionen_7; "AddConditionEntries:JetSetColumns"
0x1800b6604  call    PolicyMapJetError
0x1800b6609  mov     ebx, eax
0x1800b660b  test    eax, eax
0x1800b660d  jnz     short loc_1800B6669
0x1800b660f  xor     r9d, r9d; cbBookmark
  ... truncated ...
```
