# AddPolicyEntry

- ea: `0x1800b7404`
- end: `0x1800b77d8`
- name: `AddPolicyEntry`
- size: `980`
- prototype: `__int64 __usercall@<rax>(JET_SESID sesid@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800b7248`

## callees

- `0x1800b7404`
- `0x1800ba3cc`
- `0x1800ba598`
- `0x1800bb398`
- `0x1800bb4d4`
- `0x1800bba04`
- `0x1800cc9e0`

## import_xrefs

- `ESENT!JetSetColumns` at `0x1800b7657`
- `ESENT!JetSetColumns` at `0x1800b76d1`
- `ESENT!JetSetColumns` at `0x1800b7724`
- `ESENT!JetSetColumns` at `0x1800b7657`
- `ESENT!JetSetColumns` at `0x1800b76d1`
- `ESENT!JetSetColumns` at `0x1800b7724`
- `ESENT!JetSetCurrentIndex2A` at `0x1800b748e`
- `ESENT!JetSetCurrentIndex2A` at `0x1800b748e`
- `ESENT!JetUpdate` at `0x1800b7755`
- `ESENT!JetUpdate` at `0x1800b7755`
- `ESENT!JetBeginTransaction` at `0x1800b75c0`
- `ESENT!JetBeginTransaction` at `0x1800b75c0`
- `ESENT!JetRollback` at `0x1800b779f`
- `ESENT!JetRollback` at `0x1800b779f`
- `ESENT!JetCommitTransaction` at `0x1800b777a`
- `ESENT!JetCommitTransaction` at `0x1800b777a`
- `ESENT!JetPrepareUpdate` at `0x1800b75ed`
- `ESENT!JetPrepareUpdate` at `0x1800b75ed`
- `ESENT!JetRetrieveColumn` at `0x1800b74e2`
- `ESENT!JetRetrieveColumn` at `0x1800b74e2`

## string_xrefs

- `0x1800b75fb`: `AddPolicyEntry:JetPrepareUpdate`
- `0x1800b7763`: `AddPolicyEntry:JetUPdate`
- `0x1800b7788`: `AddPolicyEntry:JetCommitTransaction`

## pseudocode

```c
__int64 __fastcall AddPolicyEntry(JET_SESID sesid, __int64 a2, __int64 a3, __int64 a4, __int64 a5, _DWORD *a6)
{
  JET_TABLEID v6; // r15
  unsigned int v9; // eax
  unsigned int IdFromGaps; // edi
  unsigned int v11; // ebx
  unsigned int v12; // eax
  unsigned int v13; // ebx
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // ebx
  _DWORD *v19; // rax
  __int64 v20; // r12
  unsigned int v21; // eax
  unsigned int v22; // ecx
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  bool v27; // [rsp+40h] [rbp-C0h] BYREF
  bool v28[3]; // [rsp+41h] [rbp-BFh] BYREF
  int pvData; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v30; // [rsp+48h] [rbp-B8h]
  JET_SETCOLUMN v31; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+78h] [rbp-88h]
  JET_SETCOLUMN psetcolumn; // [rsp+80h] [rbp-80h] BYREF

  v6 = PolicyTableId;
  v32 = a4;
  v30 = 0;
  *a6 = 0;
  memset(&v31, 0, 36);
  v28[0] = 0;
  v27 = 0;
  pvData = 0;
  v9 = JetSetCurrentIndex2A(sesid, PolicyTableId, "PolicyTable_Index1", 0);
  IdFromGaps = PolicyMapJetError(v9, "GetAvailablePolicyId:JetSetCurrentIndex");
  if ( IdFromGaps )
    return IdFromGaps;
  v11 = JetRetrieveColumn(sesid, PolicyTableId, dword_1800F75B8, &pvData, 4u, 0, 1u, 0);
  v12 = PolicyMapJetError(v11, "GetAvailablePolicyId:JetRetrieveColumn");
  IdFromGaps = v12;
  if ( v11 == -1603 )
  {
    *a6 = 1;
  }
  else
  {
    if ( v12 )
      return IdFromGaps;
    if ( pvData == -1 )
      IdFromGaps = FindIdFromGaps(sesid, PolicyTableId, dword_1800F75B8, "PolicyTable_Index1", (__int64)a6);
    else
      *a6 = pvData + 1;
    if ( IdFromGaps )
      return IdFromGaps;
  }
  IdFromGaps = GetMaxProcessingOrderForSubnet(sesid);
  if ( IdFromGaps )
    return IdFromGaps;
  v13 = v30;
  v14 = *(_DWORD *)(a3 + 16);
  if ( v14 > v30 + 1 )
    return 20110;
  if ( v14 )
  {
    if ( v30 >= v14 )
    {
      do
      {
        IdFromGaps = IncrementProcessingOrder(sesid, v6);
        if ( IdFromGaps )
          return IdFromGaps;
      }
      while ( --v13 >= *(_DWORD *)(a3 + 16) );
    }
  }
  else
  {
    *(_DWORD *)(a3 + 16) = v30 + 1;
  }
  v15 = JetBeginTransaction(sesid);
  IdFromGaps = PolicyMapJetError(v15, "AddPolicyEntry:JetBeginTransaction");
  if ( IdFromGaps )
    return IdFromGaps;
  v16 = JetPrepareUpdate(sesid, v6, 0);
  IdFromGaps = PolicyMapJetError(v16, "AddPolicyEntry:JetPrepareUpdate");
  if ( IdFromGaps )
    goto LABEL_28;
  v28[0] = *(_DWORD *)(a3 + 56) == 0;
  v27 = *(_DWORD *)(a3 + 8) != 0;
  FillPolicySetColumnsData((unsigned int)&psetcolumn, a3, a5, (_DWORD)a6, (__int64)v28, (__int64)&v27);
  v17 = JetSetColumns(sesid, v6, &psetcolumn, 9u);
  IdFromGaps = PolicyMapJetError(v17, "AddPolicyEntry:JetSetColumns");
  if ( IdFromGaps )
    goto LABEL_28;
  v18 = 0;
  v31.columnid = dword_1800F7660;
  v19 = *(_DWORD **)(a3 + 40);
  v31.err = 0;
  *(_QWORD *)&v31.grbit = 0;
  v31.cbData = 4;
  if ( *v19 )
  {
    v20 = v32;
    while ( 1 )
    {
      v31.pvData = (const void *)(v20 + 4LL * v18);
      v31.itagSequence = ++v18;
      v21 = JetSetColumns(sesid, v6, &v31, 1u);
      IdFromGaps = PolicyMapJetError(v21, "AddPolicyEntry:JetSetColumns2");
      if ( IdFromGaps )
        goto LABEL_28;
      v22 = **(_DWORD **)(a3 + 40);
      if ( v18 >= v22 )
      {
        if ( v22 )
          goto LABEL_26;
        break;
      }
    }
  }
  v31.pvData = 0;
  v31.cbData = 0;
  v31.itagSequence = 1;
  v23 = JetSetColumns(sesid, v6, &v31, 1u);
  IdFromGaps = PolicyMapJetError(v23, "AddPolicyEntry:JetSetColumns2");
  if ( IdFromGaps )
  {
LABEL_28:
    JetRollback(sesid, 0);
    return IdFromGaps;
  }
LABEL_26:
  v24 = JetUpdate(sesid, v6, 0, 0, 0);
  IdFromGaps = PolicyMapJetError(v24, "AddPolicyEntry:JetUPdate");
  if ( IdFromGaps )
    goto LABEL_28;
  v25 = JetCommitTransaction(sesid, 0);
  IdFromGaps = PolicyMapJetError(v25, "AddPolicyEntry:JetCommitTransaction");
  if ( IdFromGaps )
    goto LABEL_28;
  return IdFromGaps;
}

```

## disassembly

```asm
0x1800b7404  mov     [rsp-8+arg_8], rbx
0x1800b7409  push    rbp
0x1800b740a  push    rsi
0x1800b740b  push    rdi
0x1800b740c  push    r12
0x1800b740e  push    r13
0x1800b7410  push    r14
0x1800b7412  push    r15
0x1800b7414  lea     rbp, [rsp-100h]
0x1800b741c  sub     rsp, 200h
0x1800b7423  mov     rax, cs:__security_cookie
0x1800b742a  xor     rax, rsp
0x1800b742d  mov     [rbp+130h+var_40], rax
0x1800b7434  mov     r15, cs:PolicyTableId
0x1800b743b  xor     ebx, ebx
0x1800b743d  mov     r12, [rbp+130h+arg_28]
0x1800b7444  xorps   xmm0, xmm0
0x1800b7447  mov     r13, [rbp+130h+arg_20]
0x1800b744e  mov     r14, r8
0x1800b7451  mov     [rsp+230h+var_1B8], r9
0x1800b7456  lea     r8, aPolicytableInd_1; "PolicyTable_Index1"
0x1800b745d  xor     eax, eax
0x1800b745f  mov     [rsp+230h+var_1E8], ebx
0x1800b7463  mov     [r12], ebx
0x1800b7467  xor     r9d, r9d; grbit
0x1800b746a  mov     rdx, cs:PolicyTableId; tableid
0x1800b7471  mov     rsi, rcx
0x1800b7474  movups  xmmword ptr [rsp+230h+var_1E0.columnid], xmm0
0x1800b7479  mov     [rsp+230h+var_1E0.err], eax
0x1800b747d  movups  xmmword ptr [rsp+230h+var_1E0.cbData], xmm0
0x1800b7482  mov     [rsp+230h+var_1EF], bl
0x1800b7486  mov     [rsp+230h+var_1F0], bl
0x1800b748a  mov     [rsp+230h+pvData], ebx
0x1800b748e  call    cs:__imp_JetSetCurrentIndex2A
0x1800b7495  nop     dword ptr [rax+rax+00h]
0x1800b749a  mov     ecx, eax
0x1800b749c  lea     rdx, aGetavailablepo_3; "GetAvailablePolicyId:JetSetCurrentIndex"
0x1800b74a3  call    PolicyMapJetError
0x1800b74a8  mov     edi, eax
0x1800b74aa  test    eax, eax
0x1800b74ac  jnz     loc_1800B77AB
0x1800b74b2  mov     r8d, cs:dword_1800F75B8; columnid
0x1800b74b9  lea     r9, [rsp+230h+pvData]; pvData
0x1800b74be  mov     rdx, cs:PolicyTableId; tableid
0x1800b74c5  mov     rcx, rsi; sesid
0x1800b74c8  mov     [rsp+230h+pretinfo], rbx; pretinfo
0x1800b74cd  mov     [rsp+230h+grbit], 1; grbit
0x1800b74d5  mov     [rsp+230h+pcbActual], rbx; pcbActual
0x1800b74da  mov     [rsp+230h+cbData], 4; cbData
0x1800b74e2  call    cs:__imp_JetRetrieveColumn
0x1800b74e9  nop     dword ptr [rax+rax+00h]
0x1800b74ee  mov     ecx, eax
0x1800b74f0  lea     rdx, aGetavailablepo_0; "GetAvailablePolicyId:JetRetrieveColumn"
0x1800b74f7  mov     ebx, eax
0x1800b74f9  call    PolicyMapJetError
0x1800b74fe  mov     edi, eax
0x1800b7500  cmp     ebx, 0FFFFF9BDh
0x1800b7506  jnz     short loc_1800B7512
0x1800b7508  mov     dword ptr [r12], 1
0x1800b7510  jmp     short loc_1800B7557
0x1800b7512  test    eax, eax
0x1800b7514  jnz     loc_1800B77AB
0x1800b751a  mov     eax, [rsp+230h+pvData]
0x1800b751e  cmp     eax, 0FFFFFFFFh
0x1800b7521  jnz     short loc_1800B7549
0x1800b7523  mov     r8d, cs:dword_1800F75B8; columnid
0x1800b752a  lea     r9, aPolicytableInd_1; "PolicyTable_Index1"
0x1800b7531  mov     rdx, cs:PolicyTableId; tableid
0x1800b7538  mov     rcx, rsi; sesid
0x1800b753b  mov     qword ptr [rsp+230h+cbData], r12; __int64
0x1800b7540  call    FindIdFromGaps
0x1800b7545  mov     edi, eax
0x1800b7547  jmp     short loc_1800B754F
0x1800b7549  inc     eax
0x1800b754b  mov     [r12], eax
0x1800b754f  test    edi, edi
0x1800b7551  jnz     loc_1800B77AB
0x1800b7557  mov     edx, [r14+0Ch]
0x1800b755b  lea     r8, [rsp+230h+var_1E8]
0x1800b7560  mov     rcx, rsi; sesid
0x1800b7563  call    GetMaxProcessingOrderForSubnet
0x1800b7568  mov     edi, eax
0x1800b756a  test    eax, eax
0x1800b756c  jnz     loc_1800B77AB
0x1800b7572  mov     ebx, [rsp+230h+var_1E8]
0x1800b7576  mov     eax, [r14+10h]
0x1800b757a  lea     ecx, [rbx+1]
0x1800b757d  cmp     eax, ecx
0x1800b757f  jbe     short loc_1800B758B
0x1800b7581  mov     edi, 4E8Eh
0x1800b7586  jmp     loc_1800B77AB
0x1800b758b  test    eax, eax
0x1800b758d  jnz     short loc_1800B7595
0x1800b758f  mov     [r14+10h], ecx
0x1800b7593  jmp     short loc_1800B75BD
0x1800b7595  cmp     ebx, eax
0x1800b7597  jb      short loc_1800B75BD
0x1800b7599  mov     r8d, [r14+0Ch]
0x1800b759d  mov     r9d, ebx
0x1800b75a0  mov     rdx, r15; tableid
0x1800b75a3  mov     rcx, rsi; sesid
0x1800b75a6  call    IncrementProcessingOrder
0x1800b75ab  mov     edi, eax
0x1800b75ad  test    eax, eax
0x1800b75af  jnz     loc_1800B77AB
0x1800b75b5  dec     ebx
0x1800b75b7  cmp     ebx, [r14+10h]
0x1800b75bb  jnb     short loc_1800B7599
0x1800b75bd  mov     rcx, rsi; sesid
0x1800b75c0  call    cs:__imp_JetBeginTransaction
0x1800b75c7  nop     dword ptr [rax+rax+00h]
0x1800b75cc  mov     ecx, eax
0x1800b75ce  lea     rdx, aAddpolicyentry_4; "AddPolicyEntry:JetBeginTransaction"
0x1800b75d5  call    PolicyMapJetError
0x1800b75da  mov     edi, eax
0x1800b75dc  test    eax, eax
0x1800b75de  jnz     loc_1800B77AB
0x1800b75e4  xor     r8d, r8d; prep
0x1800b75e7  mov     rdx, r15; tableid
0x1800b75ea  mov     rcx, rsi; sesid
0x1800b75ed  call    cs:__imp_JetPrepareUpdate
0x1800b75f4  nop     dword ptr [rax+rax+00h]
0x1800b75f9  mov     ecx, eax
0x1800b75fb  lea     rdx, aAddpolicyentry; "AddPolicyEntry:JetPrepareUpdate"
0x1800b7602  call    PolicyMapJetError
0x1800b7607  mov     edi, eax
0x1800b7609  test    eax, eax
0x1800b760b  jnz     loc_1800B779A
0x1800b7611  cmp     [r14+38h], eax
0x1800b7615  lea     rcx, [rbp+130h+psetcolumn]
0x1800b7619  mov     r9, r12
0x1800b761c  mov     r8, r13
0x1800b761f  setz    [rsp+230h+var_1EF]
0x1800b7624  mov     rdx, r14
0x1800b7627  cmp     [r14+8], eax
0x1800b762b  lea     rax, [rsp+230h+var_1F0]
0x1800b7630  mov     [rsp+230h+pcbActual], rax
0x1800b7635  lea     rax, [rsp+230h+var_1EF]
0x1800b763a  mov     qword ptr [rsp+230h+cbData], rax
0x1800b763f  setnz   [rsp+230h+var_1F0]
0x1800b7644  call    FillPolicySetColumnsData
0x1800b7649  lea     r9d, [rdi+9]; csetcolumn
0x1800b764d  mov     rdx, r15; tableid
0x1800b7650  lea     r8, [rbp+130h+psetcolumn]; psetcolumn
0x1800b7654  mov     rcx, rsi; sesid
0x1800b7657  call    cs:__imp_JetSetColumns
0x1800b765e  nop     dword ptr [rax+rax+00h]
0x1800b7663  mov     ecx, eax
0x1800b7665  lea     rdx, aAddpolicyentry_8; "AddPolicyEntry:JetSetColumns"
0x1800b766c  call    PolicyMapJetError
0x1800b7671  xor     r13d, r13d
0x1800b7674  mov     edi, eax
0x1800b7676  test    eax, eax
0x1800b7678  jnz     loc_1800B779A
0x1800b767e  mov     eax, cs:dword_1800F7660
0x1800b7684  mov     ebx, r13d
0x1800b7687  mov     [rsp+230h+var_1E0.columnid], eax
0x1800b768b  mov     rax, [r14+28h]
0x1800b768f  mov     [rsp+230h+var_1E0.err], r13d
0x1800b7694  mov     qword ptr [rsp+230h+var_1E0.grbit], r13
0x1800b7699  mov     [rsp+230h+var_1E0.cbData], 4
0x1800b76a1  mov     ecx, [rax]
0x1800b76a3  test    ecx, ecx
0x1800b76a5  jz      short loc_1800B7703
0x1800b76a7  mov     r12, [rsp+230h+var_1B8]
0x1800b76ac  mov     eax, ebx
0x1800b76ae  lea     r8, [rsp+230h+var_1E0]; psetcolumn
0x1800b76b3  mov     r9d, 1; csetcolumn
0x1800b76b9  mov     rdx, r15; tableid
0x1800b76bc  lea     rcx, [r12+rax*4]
0x1800b76c0  lea     eax, [rbx+1]
0x1800b76c3  mov     [rsp+230h+var_1E0.pvData], rcx
0x1800b76c8  mov     rcx, rsi; sesid
0x1800b76cb  mov     [rsp+230h+var_1E0.itagSequence], eax
0x1800b76cf  mov     ebx, eax
0x1800b76d1  call    cs:__imp_JetSetColumns
0x1800b76d8  nop     dword ptr [rax+rax+00h]
0x1800b76dd  mov     ecx, eax
0x1800b76df  lea     rdx, aAddpolicyentry_6; "AddPolicyEntry:JetSetColumns2"
0x1800b76e6  call    PolicyMapJetError
0x1800b76eb  mov     edi, eax
0x1800b76ed  test    eax, eax
0x1800b76ef  jnz     loc_1800B779A
0x1800b76f5  mov     rax, [r14+28h]
0x1800b76f9  mov     ecx, [rax]
0x1800b76fb  cmp     ebx, ecx
0x1800b76fd  jb      short loc_1800B76AC
0x1800b76ff  test    ecx, ecx
0x1800b7701  jnz     short loc_1800B7744
0x1800b7703  mov     eax, 1
0x1800b7708  mov     [rsp+230h+var_1E0.pvData], r13
0x1800b770d  mov     r9d, eax; csetcolumn
0x1800b7710  mov     [rsp+230h+var_1E0.cbData], r13d
0x1800b7715  lea     r8, [rsp+230h+var_1E0]; psetcolumn
0x1800b771a  mov     [rsp+230h+var_1E0.itagSequence], eax
0x1800b771e  mov     rdx, r15; tableid
0x1800b7721  mov     rcx, rsi; sesid
0x1800b7724  call    cs:__imp_JetSetColumns
0x1800b772b  nop     dword ptr [rax+rax+00h]
0x1800b7730  mov     ecx, eax
0x1800b7732  lea     rdx, aAddpolicyentry_6; "AddPolicyEntry:JetSetColumns2"
0x1800b7739  call    PolicyMapJetError
0x1800b773e  mov     edi, eax
0x1800b7740  test    eax, eax
0x1800b7742  jnz     short loc_1800B779A
0x1800b7744  xor     r9d, r9d; cbBookmark
0x1800b7747  mov     qword ptr [rsp+230h+cbData], r13; pcbActual
0x1800b774c  xor     r8d, r8d; pvBookmark
0x1800b774f  mov     rdx, r15; tableid
0x1800b7752  mov     rcx, rsi; sesid
0x1800b7755  call    cs:__imp_JetUpdate
0x1800b775c  nop     dword ptr [rax+rax+00h]
0x1800b7761  mov     ecx, eax
0x1800b7763  lea     rdx, aAddpolicyentry_5; "AddPolicyEntry:JetUPdate"
0x1800b776a  call    PolicyMapJetError
0x1800b776f  mov     edi, eax
0x1800b7771  test    eax, eax
0x1800b7773  jnz     short loc_1800B779A
0x1800b7775  xor     edx, edx; grbit
0x1800b7777  mov     rcx, rsi; sesid
0x1800b777a  call    cs:__imp_JetCommitTransaction
0x1800b7781  nop     dword ptr [rax+rax+00h]
0x1800b7786  mov     ecx, eax
0x1800b7788  lea     rdx, aAddpolicyentry_7; "AddPolicyEntry:JetCommitTransaction"
0x1800b778f  call    PolicyMapJetError
0x1800b7794  mov     edi, eax
0x1800b7796  test    eax, eax
0x1800b7798  jz      short loc_1800B77AB
0x1800b779a  xor     edx, edx; grbit
0x1800b779c  mov     rcx, rsi; sesid
0x1800b779f  call    cs:__imp_JetRollback
0x1800b77a6  nop     dword ptr [rax+rax+00h]
0x1800b77ab  mov     eax, edi
0x1800b77ad  mov     rcx, [rbp+130h+var_40]
0x1800b77b4  xor     rcx, rsp; StackCookie
0x1800b77b7  call    __security_check_cookie
0x1800b77bc  mov     rbx, [rsp+230h+arg_8]
0x1800b77c4  add     rsp, 200h
0x1800b77cb  pop     r15
0x1800b77cd  pop     r14
0x1800b77cf  pop     r13
0x1800b77d1  pop     r12
0x1800b77d3  pop     rdi
0x1800b77d4  pop     rsi
0x1800b77d5  pop     rbp
0x1800b77d6  retn
```
