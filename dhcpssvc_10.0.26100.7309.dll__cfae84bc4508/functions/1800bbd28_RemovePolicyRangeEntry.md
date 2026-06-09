# RemovePolicyRangeEntry

- ea: `0x1800bbd28`
- end: `0x1800bc0db`
- name: `RemovePolicyRangeEntry`
- size: `947`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1800897ac`

## callees

- `0x1800bba04`
- `0x1800bbd28`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800bbd7e`
- `ESENT!JetSetCurrentIndexA` at `0x1800bbed6`
- `ESENT!JetSetCurrentIndexA` at `0x1800bbd7e`
- `ESENT!JetSetCurrentIndexA` at `0x1800bbed6`
- `ESENT!JetRetrieveColumns` at `0x1800bbe77`
- `ESENT!JetRetrieveColumns` at `0x1800bbf85`
- `ESENT!JetRetrieveColumns` at `0x1800bbfd2`
- `ESENT!JetRetrieveColumns` at `0x1800bbe77`
- `ESENT!JetRetrieveColumns` at `0x1800bbf85`
- `ESENT!JetRetrieveColumns` at `0x1800bbfd2`
- `ESENT!JetSetColumns` at `0x1800bc074`
- `ESENT!JetSetColumns` at `0x1800bc074`
- `ESENT!JetUpdate` at `0x1800bc0a7`
- `ESENT!JetUpdate` at `0x1800bc0a7`
- `ESENT!JetMakeKey` at `0x1800bbdbd`
- `ESENT!JetMakeKey` at `0x1800bbdf8`
- `ESENT!JetMakeKey` at `0x1800bbf0e`
- `ESENT!JetMakeKey` at `0x1800bbdbd`
- `ESENT!JetMakeKey` at `0x1800bbdf8`
- `ESENT!JetMakeKey` at `0x1800bbf0e`
- `ESENT!JetSeek` at `0x1800bbe23`
- `ESENT!JetSeek` at `0x1800bbf39`
- `ESENT!JetSeek` at `0x1800bbe23`
- `ESENT!JetSeek` at `0x1800bbf39`
- `ESENT!JetDelete` at `0x1800bbea3`
- `ESENT!JetDelete` at `0x1800bbea3`
- `ESENT!JetPrepareUpdate` at `0x1800bc025`
- `ESENT!JetPrepareUpdate` at `0x1800bc025`

## string_xrefs

- `0x1800bbdc9`: `RemovePolicyRangeEntry:JetMakeKey`
- `0x1800bbe31`: `RemovePolicyRangeEntry:JetSeek`
- `0x1800bbf47`: `RemovePolicyRangeEntry:JetSeek`
- `0x1800bbd8c`: `RemovePolicyRangeEntry:JetSetCurrentIndex`
- `0x1800bbee4`: `RemovePolicyRangeEntry:JetSetCurrentIndex`
- `0x1800bbfe0`: `RemovePolicyRangeEntry:JetRetrieveColumns2`
- `0x1800bc033`: `RemovePolicyRangeEntry:JetPrepareUpdate`
- `0x1800bbe85`: `RemovePolicyRangeEntry:JetRetrieveColumns1`
- `0x1800bbf93`: `RemovePolicyRangeEntry:JetRetrieveColumns1`
- `0x1800bbeb1`: `RemovePolicyRangeEntry:JetDelete`
- `0x1800bc082`: `RemovePolicyRangeEntry:JetSetColumns`
- `0x1800bc0b5`: `RemovePolicyRangeEntry:Jetupdate`

## pseudocode

```c
__int64 __fastcall RemovePolicyRangeEntry(__int64 a1, __int64 a2, int a3)
{
  JET_SESID v3; // rbx
  unsigned int v5; // eax
  __int64 result; // rax
  unsigned int Key; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int itagSequence; // esi
  unsigned int v17; // edi
  unsigned int v18; // eax
  int v19; // eax
  int v20; // ecx
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  JET_SETCOLUMN psetcolumn; // [rsp+30h] [rbp-39h] BYREF
  JET_RETRIEVECOLUMN pretrievecolumn; // [rsp+58h] [rbp-11h] BYREF
  int v26; // [rsp+D0h] [rbp+67h] BYREF
  int v27; // [rsp+D4h] [rbp+6Bh]
  int pvData; // [rsp+E0h] [rbp+77h] BYREF
  int v29; // [rsp+E8h] [rbp+7Fh] BYREF

  pvData = a3;
  v27 = HIDWORD(a1);
  v3 = DhcpGlobalJetServerSession;
  v26 = 0;
  v29 = 0;
  memset(&psetcolumn, 0, 36);
  v5 = JetSetCurrentIndexA(DhcpGlobalJetServerSession, PolicyRangeTableId, "PolicyRangeTable_Index2");
  result = PolicyMapJetError(v5, "RemovePolicyRangeEntry:JetSetCurrentIndex");
  if ( (_DWORD)result )
    return result;
  Key = JetMakeKey(v3, PolicyRangeTableId, (const void *)a2, 4u, 1u);
  result = PolicyMapJetError(Key, "RemovePolicyRangeEntry:JetMakeKey");
  if ( (_DWORD)result )
    return result;
  v8 = JetMakeKey(v3, PolicyRangeTableId, (const void *)(a2 + 4), 4u, 0);
  result = PolicyMapJetError(v8, "RemovePolicyRangeEntry:JetMakeKey");
  if ( (_DWORD)result )
    return result;
  v9 = JetSeek(v3, PolicyRangeTableId, 1u);
  if ( (unsigned int)PolicyMapJetError(v9, "RemovePolicyRangeEntry:JetSeek") )
    return 20107;
  pretrievecolumn.columnid = dword_1800F7568;
  pretrievecolumn.err = 0;
  pretrievecolumn.pvData = &v26;
  *(_QWORD *)&pretrievecolumn.grbit = 1;
  *(_QWORD *)&pretrievecolumn.cbData = 4;
  *(_QWORD *)&pretrievecolumn.itagSequence = 1;
  v10 = JetRetrieveColumns(v3, PolicyRangeTableId, &pretrievecolumn, 1u);
  result = PolicyMapJetError(v10, "RemovePolicyRangeEntry:JetRetrieveColumns1");
  if ( (_DWORD)result )
    return result;
  v11 = JetDelete(v3, PolicyRangeTableId);
  result = PolicyMapJetError(v11, "RemovePolicyRangeEntry:JetDelete");
  if ( (_DWORD)result )
    return result;
  v12 = JetSetCurrentIndexA(v3, PolicyTableId, "PolicyTable_Index1");
  result = PolicyMapJetError(v12, "RemovePolicyRangeEntry:JetSetCurrentIndex");
  if ( (_DWORD)result )
    return result;
  v13 = JetMakeKey(v3, PolicyTableId, &pvData, 4u, 1u);
  result = PolicyMapJetError(v13, "RemovePolicyRangeEntry:JetMakeKey");
  if ( (_DWORD)result )
    return result;
  v14 = JetSeek(v3, PolicyTableId, 1u);
  result = PolicyMapJetError(v14, "RemovePolicyRangeEntry:JetSeek");
  if ( (_DWORD)result )
    return result;
  pretrievecolumn.columnid = dword_1800F7660;
  pretrievecolumn.grbit = 1;
  pretrievecolumn.itagSequence = 0;
  pretrievecolumn.pvData = 0;
  pretrievecolumn.cbData = 0;
  v15 = JetRetrieveColumns(v3, PolicyTableId, &pretrievecolumn, 1u);
  result = PolicyMapJetError(v15, "RemovePolicyRangeEntry:JetRetrieveColumns1");
  if ( (_DWORD)result )
    return result;
  itagSequence = pretrievecolumn.itagSequence;
  v17 = 1;
  if ( !pretrievecolumn.itagSequence )
  {
    v20 = v26;
    v19 = v29;
LABEL_17:
    if ( v19 == v20 )
    {
LABEL_18:
      v21 = JetPrepareUpdate(v3, PolicyTableId, 2u);
      result = PolicyMapJetError(v21, "RemovePolicyRangeEntry:JetPrepareUpdate");
      if ( !(_DWORD)result )
      {
        psetcolumn.columnid = dword_1800F7660;
        psetcolumn.err = 0;
        psetcolumn.itagSequence = v17;
        memset(&psetcolumn.pvData, 0, 20);
        v22 = JetSetColumns(v3, PolicyTableId, &psetcolumn, 1u);
        result = PolicyMapJetError(v22, "RemovePolicyRangeEntry:JetSetColumns");
        if ( !(_DWORD)result )
        {
          v23 = JetUpdate(v3, PolicyTableId, 0, 0, 0);
          return PolicyMapJetError(v23, "RemovePolicyRangeEntry:Jetupdate");
        }
      }
      return result;
    }
    return 20107;
  }
  while ( 1 )
  {
    pretrievecolumn.pvData = &v29;
    pretrievecolumn.itagSequence = v17;
    pretrievecolumn.cbData = 4;
    v18 = JetRetrieveColumns(v3, PolicyTableId, &pretrievecolumn, 1u);
    result = PolicyMapJetError(v18, "RemovePolicyRangeEntry:JetRetrieveColumns2");
    if ( (_DWORD)result )
      return result;
    v19 = v29;
    v20 = v26;
    if ( v29 == v26 )
      goto LABEL_18;
    if ( ++v17 > itagSequence )
      goto LABEL_17;
  }
}

```

## disassembly

```asm
0x1800bbd28  mov     [rsp-8+pvData], r8d
0x1800bbd2d  mov     [rsp-8+arg_0], rcx
0x1800bbd32  push    rbp
0x1800bbd33  push    rbx
0x1800bbd34  push    rsi
0x1800bbd35  push    rdi
0x1800bbd36  push    r12
0x1800bbd38  push    r14
0x1800bbd3a  push    r15
0x1800bbd3c  lea     rbp, [rsp-27h]
0x1800bbd41  sub     rsp, 90h
0x1800bbd48  mov     rbx, cs:DhcpGlobalJetServerSession
0x1800bbd4f  lea     r8, aPolicyrangetab_1; "PolicyRangeTable_Index2"
0x1800bbd56  xorps   xmm0, xmm0
0x1800bbd59  mov     rdi, rdx
0x1800bbd5c  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800bbd63  xor     r14d, r14d
0x1800bbd66  xor     eax, eax
0x1800bbd68  mov     dword ptr [rbp+57h+arg_0], r14d
0x1800bbd6c  mov     rcx, rbx; sesid
0x1800bbd6f  mov     [rbp+57h+arg_18], r14d
0x1800bbd73  movups  xmmword ptr [rbp+57h+psetcolumn.columnid], xmm0
0x1800bbd77  mov     [rbp+57h+psetcolumn.err], eax
0x1800bbd7a  movups  xmmword ptr [rbp+57h+psetcolumn.cbData], xmm0
0x1800bbd7e  call    cs:__imp_JetSetCurrentIndexA
0x1800bbd85  nop     dword ptr [rax+rax+00h]
0x1800bbd8a  mov     ecx, eax
0x1800bbd8c  lea     rdx, aRemovepolicyra_3; "RemovePolicyRangeEntry:JetSetCurrentInd"...
0x1800bbd93  call    PolicyMapJetError
0x1800bbd98  test    eax, eax
0x1800bbd9a  jnz     loc_1800BC0C8
0x1800bbda0  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800bbda7  lea     r12d, [r14+4]
0x1800bbdab  lea     r15d, [r14+1]
0x1800bbdaf  mov     r9d, r12d; cbData
0x1800bbdb2  mov     r8, rdi; pvData
0x1800bbdb5  mov     [rsp+0C0h+grbit], r15d; grbit
0x1800bbdba  mov     rcx, rbx; sesid
0x1800bbdbd  call    cs:__imp_JetMakeKey
0x1800bbdc4  nop     dword ptr [rax+rax+00h]
0x1800bbdc9  lea     rsi, aRemovepolicyra; "RemovePolicyRangeEntry:JetMakeKey"
0x1800bbdd0  mov     ecx, eax
0x1800bbdd2  mov     rdx, rsi
0x1800bbdd5  call    PolicyMapJetError
0x1800bbdda  test    eax, eax
0x1800bbddc  jnz     loc_1800BC0C8
0x1800bbde2  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800bbde9  lea     r8, [rdi+4]; pvData
0x1800bbded  mov     r9d, r12d; cbData
0x1800bbdf0  mov     [rsp+0C0h+grbit], r14d; grbit
0x1800bbdf5  mov     rcx, rbx; sesid
0x1800bbdf8  call    cs:__imp_JetMakeKey
0x1800bbdff  nop     dword ptr [rax+rax+00h]
0x1800bbe04  mov     ecx, eax
0x1800bbe06  mov     rdx, rsi
0x1800bbe09  call    PolicyMapJetError
0x1800bbe0e  test    eax, eax
0x1800bbe10  jnz     loc_1800BC0C8
0x1800bbe16  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800bbe1d  mov     r8d, r15d; grbit
0x1800bbe20  mov     rcx, rbx; sesid
0x1800bbe23  call    cs:__imp_JetSeek
0x1800bbe2a  nop     dword ptr [rax+rax+00h]
0x1800bbe2f  mov     ecx, eax
0x1800bbe31  lea     rdx, aRemovepolicyra_6; "RemovePolicyRangeEntry:JetSeek"
0x1800bbe38  call    PolicyMapJetError
0x1800bbe3d  test    eax, eax
0x1800bbe3f  jnz     loc_1800BC0C3
0x1800bbe45  mov     eax, cs:dword_1800F7568
0x1800bbe4b  lea     r8, [rbp+57h+pretrievecolumn]; pretrievecolumn
0x1800bbe4f  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800bbe56  mov     r9d, r15d; cretrievecolumn
0x1800bbe59  mov     [rbp+57h+pretrievecolumn.columnid], eax
0x1800bbe5c  mov     rcx, rbx; sesid
0x1800bbe5f  lea     rax, [rbp+57h+arg_0]
0x1800bbe63  mov     qword ptr [rbp+57h+pretrievecolumn.columnidNextTagged], r14
0x1800bbe67  mov     [rbp+57h+pretrievecolumn.pvData], rax
0x1800bbe6b  mov     qword ptr [rbp+57h+pretrievecolumn.grbit], r15
0x1800bbe6f  mov     qword ptr [rbp+57h+pretrievecolumn.cbData], r12
0x1800bbe73  mov     [rbp+57h+pretrievecolumn.itagSequence], r15d
0x1800bbe77  call    cs:__imp_JetRetrieveColumns
0x1800bbe7e  nop     dword ptr [rax+rax+00h]
0x1800bbe83  mov     ecx, eax
0x1800bbe85  lea     rdx, aRemovepolicyra_5; "RemovePolicyRangeEntry:JetRetrieveColum"...
0x1800bbe8c  call    PolicyMapJetError
0x1800bbe91  test    eax, eax
0x1800bbe93  jnz     loc_1800BC0C8
0x1800bbe99  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800bbea0  mov     rcx, rbx; sesid
0x1800bbea3  call    cs:__imp_JetDelete
0x1800bbeaa  nop     dword ptr [rax+rax+00h]
0x1800bbeaf  mov     ecx, eax
0x1800bbeb1  lea     rdx, aRemovepolicyra_1; "RemovePolicyRangeEntry:JetDelete"
0x1800bbeb8  call    PolicyMapJetError
0x1800bbebd  test    eax, eax
0x1800bbebf  jnz     loc_1800BC0C8
0x1800bbec5  mov     rdx, cs:PolicyTableId; tableid
0x1800bbecc  lea     r8, aPolicytableInd_1; "PolicyTable_Index1"
0x1800bbed3  mov     rcx, rbx; sesid
0x1800bbed6  call    cs:__imp_JetSetCurrentIndexA
0x1800bbedd  nop     dword ptr [rax+rax+00h]
0x1800bbee2  mov     ecx, eax
0x1800bbee4  lea     rdx, aRemovepolicyra_3; "RemovePolicyRangeEntry:JetSetCurrentInd"...
0x1800bbeeb  call    PolicyMapJetError
0x1800bbef0  test    eax, eax
0x1800bbef2  jnz     loc_1800BC0C8
0x1800bbef8  mov     rdx, cs:PolicyTableId; tableid
0x1800bbeff  lea     r8, [rbp+57h+pvData]; pvData
0x1800bbf03  mov     r9d, r12d; cbData
0x1800bbf06  mov     [rsp+0C0h+grbit], r15d; grbit
0x1800bbf0b  mov     rcx, rbx; sesid
0x1800bbf0e  call    cs:__imp_JetMakeKey
0x1800bbf15  nop     dword ptr [rax+rax+00h]
0x1800bbf1a  mov     ecx, eax
0x1800bbf1c  mov     rdx, rsi
0x1800bbf1f  call    PolicyMapJetError
0x1800bbf24  test    eax, eax
0x1800bbf26  jnz     loc_1800BC0C8
0x1800bbf2c  mov     rdx, cs:PolicyTableId; tableid
0x1800bbf33  mov     r8d, r15d; grbit
0x1800bbf36  mov     rcx, rbx; sesid
0x1800bbf39  call    cs:__imp_JetSeek
0x1800bbf40  nop     dword ptr [rax+rax+00h]
0x1800bbf45  mov     ecx, eax
0x1800bbf47  lea     rdx, aRemovepolicyra_6; "RemovePolicyRangeEntry:JetSeek"
0x1800bbf4e  call    PolicyMapJetError
0x1800bbf53  test    eax, eax
0x1800bbf55  jnz     loc_1800BC0C8
0x1800bbf5b  mov     eax, cs:dword_1800F7660
0x1800bbf61  lea     r8, [rbp+57h+pretrievecolumn]; pretrievecolumn
0x1800bbf65  mov     rdx, cs:PolicyTableId; tableid
0x1800bbf6c  mov     r9d, r15d; cretrievecolumn
0x1800bbf6f  mov     rcx, rbx; sesid
0x1800bbf72  mov     [rbp+57h+pretrievecolumn.columnid], eax
0x1800bbf75  mov     [rbp+57h+pretrievecolumn.grbit], r15d
0x1800bbf79  mov     [rbp+57h+pretrievecolumn.itagSequence], r14d
0x1800bbf7d  mov     [rbp+57h+pretrievecolumn.pvData], r14
0x1800bbf81  mov     [rbp+57h+pretrievecolumn.cbData], r14d
0x1800bbf85  call    cs:__imp_JetRetrieveColumns
0x1800bbf8c  nop     dword ptr [rax+rax+00h]
0x1800bbf91  mov     ecx, eax
0x1800bbf93  lea     rdx, aRemovepolicyra_5; "RemovePolicyRangeEntry:JetRetrieveColum"...
0x1800bbf9a  call    PolicyMapJetError
0x1800bbf9f  test    eax, eax
0x1800bbfa1  jnz     loc_1800BC0C8
0x1800bbfa7  mov     esi, [rbp+57h+pretrievecolumn.itagSequence]
0x1800bbfaa  mov     edi, r15d
0x1800bbfad  cmp     esi, r15d
0x1800bbfb0  jb      short loc_1800BC007
0x1800bbfb2  mov     rdx, cs:PolicyTableId; tableid
0x1800bbfb9  lea     rax, [rbp+57h+arg_18]
0x1800bbfbd  mov     r9d, r15d; cretrievecolumn
0x1800bbfc0  mov     [rbp+57h+pretrievecolumn.pvData], rax
0x1800bbfc4  lea     r8, [rbp+57h+pretrievecolumn]; pretrievecolumn
0x1800bbfc8  mov     [rbp+57h+pretrievecolumn.itagSequence], edi
0x1800bbfcb  mov     rcx, rbx; sesid
0x1800bbfce  mov     [rbp+57h+pretrievecolumn.cbData], r12d
0x1800bbfd2  call    cs:__imp_JetRetrieveColumns
0x1800bbfd9  nop     dword ptr [rax+rax+00h]
0x1800bbfde  mov     ecx, eax
0x1800bbfe0  lea     rdx, aRemovepolicyra_7; "RemovePolicyRangeEntry:JetRetrieveColum"...
0x1800bbfe7  call    PolicyMapJetError
0x1800bbfec  test    eax, eax
0x1800bbfee  jnz     loc_1800BC0C8
0x1800bbff4  mov     eax, [rbp+57h+arg_18]
0x1800bbff7  mov     ecx, dword ptr [rbp+57h+arg_0]
0x1800bbffa  cmp     eax, ecx
0x1800bbffc  jz      short loc_1800BC015
0x1800bbffe  add     edi, r15d
0x1800bc001  cmp     edi, esi
0x1800bc003  jbe     short loc_1800BBFB2
0x1800bc005  jmp     short loc_1800BC00D
0x1800bc007  mov     ecx, dword ptr [rbp+57h+arg_0]
0x1800bc00a  mov     eax, [rbp+57h+arg_18]
0x1800bc00d  cmp     eax, ecx
0x1800bc00f  jnz     loc_1800BC0C3
0x1800bc015  mov     rdx, cs:PolicyTableId; tableid
0x1800bc01c  mov     r8d, 2; prep
0x1800bc022  mov     rcx, rbx; sesid
0x1800bc025  call    cs:__imp_JetPrepareUpdate
0x1800bc02c  nop     dword ptr [rax+rax+00h]
0x1800bc031  mov     ecx, eax
0x1800bc033  lea     rdx, aRemovepolicyra_0; "RemovePolicyRangeEntry:JetPrepareUpdate"
0x1800bc03a  call    PolicyMapJetError
0x1800bc03f  test    eax, eax
0x1800bc041  jnz     loc_1800BC0C8
0x1800bc047  mov     eax, cs:dword_1800F7660
0x1800bc04d  lea     r8, [rbp+57h+psetcolumn]; psetcolumn
0x1800bc051  mov     rdx, cs:PolicyTableId; tableid
0x1800bc058  mov     r9d, r15d; csetcolumn
0x1800bc05b  mov     rcx, rbx; sesid
0x1800bc05e  mov     [rbp+57h+psetcolumn.columnid], eax
0x1800bc061  mov     [rbp+57h+psetcolumn.err], r14d
0x1800bc065  mov     qword ptr [rbp+57h+psetcolumn.grbit], r14
0x1800bc069  mov     [rbp+57h+psetcolumn.itagSequence], edi
0x1800bc06c  mov     [rbp+57h+psetcolumn.pvData], r14
0x1800bc070  mov     [rbp+57h+psetcolumn.cbData], r14d
0x1800bc074  call    cs:__imp_JetSetColumns
0x1800bc07b  nop     dword ptr [rax+rax+00h]
0x1800bc080  mov     ecx, eax
0x1800bc082  lea     rdx, aRemovepolicyra_4; "RemovePolicyRangeEntry:JetSetColumns"
0x1800bc089  call    PolicyMapJetError
0x1800bc08e  test    eax, eax
0x1800bc090  jnz     short loc_1800BC0C8
0x1800bc092  mov     rdx, cs:PolicyTableId; tableid
0x1800bc099  xor     r9d, r9d; cbBookmark
0x1800bc09c  xor     r8d, r8d; pvBookmark
0x1800bc09f  mov     qword ptr [rsp+0C0h+grbit], r14; pcbActual
0x1800bc0a4  mov     rcx, rbx; sesid
0x1800bc0a7  call    cs:__imp_JetUpdate
0x1800bc0ae  nop     dword ptr [rax+rax+00h]
0x1800bc0b3  mov     ecx, eax
0x1800bc0b5  lea     rdx, aRemovepolicyra_2; "RemovePolicyRangeEntry:Jetupdate"
0x1800bc0bc  call    PolicyMapJetError
0x1800bc0c1  jmp     short loc_1800BC0C8
0x1800bc0c3  mov     eax, 4E8Bh
0x1800bc0c8  add     rsp, 90h
0x1800bc0cf  pop     r15
0x1800bc0d1  pop     r14
0x1800bc0d3  pop     r12
0x1800bc0d5  pop     rdi
0x1800bc0d6  pop     rsi
0x1800bc0d7  pop     rbx
0x1800bc0d8  pop     rbp
0x1800bc0d9  retn
```
