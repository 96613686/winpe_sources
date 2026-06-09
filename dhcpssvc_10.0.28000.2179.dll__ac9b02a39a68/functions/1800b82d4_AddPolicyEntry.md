# AddPolicyEntry

- ea: `0x1800b82d4`
- end: `0x1800b86a4`
- name: `AddPolicyEntry`
- size: `976`
- prototype: `__int64 __usercall@<rax>(JET_SESID sesid@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800b8118`

## callees

- `0x1800b82d4`
- `0x1800bb2e4`
- `0x1800bb4b8`
- `0x1800bc314`
- `0x1800bc454`
- `0x1800bc990`
- `0x1800cdac0`

## import_xrefs

- `ESENT!JetSetColumns` at `0x1800b8523`
- `ESENT!JetSetColumns` at `0x1800b859d`
- `ESENT!JetSetColumns` at `0x1800b85f0`
- `ESENT!JetSetColumns` at `0x1800b8523`
- `ESENT!JetSetColumns` at `0x1800b859d`
- `ESENT!JetSetColumns` at `0x1800b85f0`
- `ESENT!JetSetCurrentIndex2A` at `0x1800b835e`
- `ESENT!JetSetCurrentIndex2A` at `0x1800b835e`
- `ESENT!JetUpdate` at `0x1800b8621`
- `ESENT!JetUpdate` at `0x1800b8621`
- `ESENT!JetBeginTransaction` at `0x1800b848c`
- `ESENT!JetBeginTransaction` at `0x1800b848c`
- `ESENT!JetRollback` at `0x1800b866b`
- `ESENT!JetRollback` at `0x1800b866b`
- `ESENT!JetCommitTransaction` at `0x1800b8646`
- `ESENT!JetCommitTransaction` at `0x1800b8646`
- `ESENT!JetPrepareUpdate` at `0x1800b84b9`
- `ESENT!JetPrepareUpdate` at `0x1800b84b9`
- `ESENT!JetRetrieveColumn` at `0x1800b83b2`
- `ESENT!JetRetrieveColumn` at `0x1800b83b2`

## string_xrefs

- `0x1800b84c7`: `AddPolicyEntry:JetPrepareUpdate`
- `0x1800b8654`: `AddPolicyEntry:JetCommitTransaction`
- `0x1800b862f`: `AddPolicyEntry:JetUPdate`

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
  if ( !IdFromGaps )
  {
    v11 = JetRetrieveColumn(sesid, PolicyTableId, dword_1800F9788, &pvData, 4u, 0, 1u, 0);
    v12 = PolicyMapJetError(v11, "GetAvailablePolicyId:JetRetrieveColumn");
    IdFromGaps = v12;
    if ( v11 == -1603 )
    {
      *a6 = 1;
      goto LABEL_8;
    }
    if ( !v12 )
    {
      if ( pvData != -1 )
      {
        *a6 = pvData + 1;
        goto LABEL_8;
      }
      IdFromGaps = FindIdFromGaps(sesid, PolicyTableId, dword_1800F9788, "PolicyTable_Index1", (__int64)a6);
    }
  }
  if ( IdFromGaps )
    return IdFromGaps;
LABEL_8:
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
  v31.columnid = dword_1800F9830;
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
0x1800b82d4  mov     [rsp-8+arg_8], rbx
0x1800b82d9  push    rbp
0x1800b82da  push    rsi
0x1800b82db  push    rdi
0x1800b82dc  push    r12
0x1800b82de  push    r13
0x1800b82e0  push    r14
0x1800b82e2  push    r15
0x1800b82e4  lea     rbp, [rsp-100h]
0x1800b82ec  sub     rsp, 200h
0x1800b82f3  mov     rax, cs:__security_cookie
0x1800b82fa  xor     rax, rsp
0x1800b82fd  mov     [rbp+130h+var_40], rax
0x1800b8304  mov     r15, cs:PolicyTableId
0x1800b830b  xor     ebx, ebx
0x1800b830d  mov     r12, [rbp+130h+arg_28]
0x1800b8314  xorps   xmm0, xmm0
0x1800b8317  mov     r13, [rbp+130h+arg_20]
0x1800b831e  mov     r14, r8
0x1800b8321  mov     [rsp+230h+var_1B8], r9
0x1800b8326  lea     r8, aPolicytableInd_1; "PolicyTable_Index1"
0x1800b832d  xor     eax, eax
0x1800b832f  mov     [rsp+230h+var_1E8], ebx
0x1800b8333  mov     [r12], ebx
0x1800b8337  xor     r9d, r9d; grbit
0x1800b833a  mov     rdx, cs:PolicyTableId; tableid
0x1800b8341  mov     rsi, rcx
0x1800b8344  movups  xmmword ptr [rsp+230h+var_1E0.columnid], xmm0
0x1800b8349  mov     [rsp+230h+var_1E0.err], eax
0x1800b834d  movups  xmmword ptr [rsp+230h+var_1E0.cbData], xmm0
0x1800b8352  mov     [rsp+230h+var_1EF], bl
0x1800b8356  mov     [rsp+230h+var_1F0], bl
0x1800b835a  mov     [rsp+230h+pvData], ebx
0x1800b835e  call    cs:__imp_JetSetCurrentIndex2A
0x1800b8365  nop     dword ptr [rax+rax+00h]
0x1800b836a  mov     ecx, eax
0x1800b836c  lea     rdx, aGetavailablepo_3; "GetAvailablePolicyId:JetSetCurrentIndex"
0x1800b8373  call    PolicyMapJetError
0x1800b8378  mov     edi, eax
0x1800b837a  test    eax, eax
0x1800b837c  jnz     loc_1800B8413
0x1800b8382  mov     r8d, cs:dword_1800F9788; columnid
0x1800b8389  lea     r9, [rsp+230h+pvData]; pvData
0x1800b838e  mov     rdx, cs:PolicyTableId; tableid
0x1800b8395  mov     rcx, rsi; sesid
0x1800b8398  mov     [rsp+230h+pretinfo], rbx; pretinfo
0x1800b839d  mov     [rsp+230h+grbit], 1; grbit
0x1800b83a5  mov     [rsp+230h+pcbActual], rbx; pcbActual
0x1800b83aa  mov     [rsp+230h+cbData], 4; cbData
0x1800b83b2  call    cs:__imp_JetRetrieveColumn
0x1800b83b9  nop     dword ptr [rax+rax+00h]
0x1800b83be  mov     ecx, eax
0x1800b83c0  lea     rdx, aGetavailablepo_0; "GetAvailablePolicyId:JetRetrieveColumn"
0x1800b83c7  mov     ebx, eax
0x1800b83c9  call    PolicyMapJetError
0x1800b83ce  mov     edi, eax
0x1800b83d0  cmp     ebx, 0FFFFF9BDh
0x1800b83d6  jnz     short loc_1800B83E2
0x1800b83d8  mov     dword ptr [r12], 1
0x1800b83e0  jmp     short loc_1800B841B
0x1800b83e2  test    eax, eax
0x1800b83e4  jnz     short loc_1800B8413
0x1800b83e6  mov     eax, [rsp+230h+pvData]
0x1800b83ea  cmp     eax, 0FFFFFFFFh
0x1800b83ed  jnz     short loc_1800B844F
0x1800b83ef  mov     r8d, cs:dword_1800F9788; columnid
0x1800b83f6  lea     r9, aPolicytableInd_1; "PolicyTable_Index1"
0x1800b83fd  mov     rdx, cs:PolicyTableId; tableid
0x1800b8404  mov     rcx, rsi; sesid
0x1800b8407  mov     qword ptr [rsp+230h+cbData], r12; __int64
0x1800b840c  call    FindIdFromGaps
0x1800b8411  mov     edi, eax
0x1800b8413  test    edi, edi
0x1800b8415  jnz     loc_1800B8677
0x1800b841b  mov     edx, [r14+0Ch]
0x1800b841f  lea     r8, [rsp+230h+var_1E8]
0x1800b8424  mov     rcx, rsi; sesid
0x1800b8427  call    GetMaxProcessingOrderForSubnet
0x1800b842c  mov     edi, eax
0x1800b842e  test    eax, eax
0x1800b8430  jnz     loc_1800B8677
0x1800b8436  mov     ebx, [rsp+230h+var_1E8]
0x1800b843a  mov     eax, [r14+10h]
0x1800b843e  lea     ecx, [rbx+1]
0x1800b8441  cmp     eax, ecx
0x1800b8443  jbe     short loc_1800B8457
0x1800b8445  mov     edi, 4E8Eh
0x1800b844a  jmp     loc_1800B8677
0x1800b844f  inc     eax
0x1800b8451  mov     [r12], eax
0x1800b8455  jmp     short loc_1800B841B
0x1800b8457  test    eax, eax
0x1800b8459  jnz     short loc_1800B8461
0x1800b845b  mov     [r14+10h], ecx
0x1800b845f  jmp     short loc_1800B8489
0x1800b8461  cmp     ebx, eax
0x1800b8463  jb      short loc_1800B8489
0x1800b8465  mov     r8d, [r14+0Ch]
0x1800b8469  mov     r9d, ebx
0x1800b846c  mov     rdx, r15; tableid
0x1800b846f  mov     rcx, rsi; sesid
0x1800b8472  call    IncrementProcessingOrder
0x1800b8477  mov     edi, eax
0x1800b8479  test    eax, eax
0x1800b847b  jnz     loc_1800B8677
0x1800b8481  dec     ebx
0x1800b8483  cmp     ebx, [r14+10h]
0x1800b8487  jnb     short loc_1800B8465
0x1800b8489  mov     rcx, rsi; sesid
0x1800b848c  call    cs:__imp_JetBeginTransaction
0x1800b8493  nop     dword ptr [rax+rax+00h]
0x1800b8498  mov     ecx, eax
0x1800b849a  lea     rdx, aAddpolicyentry_4; "AddPolicyEntry:JetBeginTransaction"
0x1800b84a1  call    PolicyMapJetError
0x1800b84a6  mov     edi, eax
0x1800b84a8  test    eax, eax
0x1800b84aa  jnz     loc_1800B8677
0x1800b84b0  xor     r8d, r8d; prep
0x1800b84b3  mov     rdx, r15; tableid
0x1800b84b6  mov     rcx, rsi; sesid
0x1800b84b9  call    cs:__imp_JetPrepareUpdate
0x1800b84c0  nop     dword ptr [rax+rax+00h]
0x1800b84c5  mov     ecx, eax
0x1800b84c7  lea     rdx, aAddpolicyentry; "AddPolicyEntry:JetPrepareUpdate"
0x1800b84ce  call    PolicyMapJetError
0x1800b84d3  mov     edi, eax
0x1800b84d5  test    eax, eax
0x1800b84d7  jnz     loc_1800B8666
0x1800b84dd  cmp     [r14+38h], eax
0x1800b84e1  lea     rcx, [rbp+130h+psetcolumn]
0x1800b84e5  mov     r9, r12
0x1800b84e8  mov     r8, r13
0x1800b84eb  setz    [rsp+230h+var_1EF]
0x1800b84f0  mov     rdx, r14
0x1800b84f3  cmp     [r14+8], eax
0x1800b84f7  lea     rax, [rsp+230h+var_1F0]
0x1800b84fc  mov     [rsp+230h+pcbActual], rax
0x1800b8501  lea     rax, [rsp+230h+var_1EF]
0x1800b8506  mov     qword ptr [rsp+230h+cbData], rax
0x1800b850b  setnz   [rsp+230h+var_1F0]
0x1800b8510  call    FillPolicySetColumnsData
0x1800b8515  lea     r9d, [rdi+9]; csetcolumn
0x1800b8519  mov     rdx, r15; tableid
0x1800b851c  lea     r8, [rbp+130h+psetcolumn]; psetcolumn
0x1800b8520  mov     rcx, rsi; sesid
0x1800b8523  call    cs:__imp_JetSetColumns
0x1800b852a  nop     dword ptr [rax+rax+00h]
0x1800b852f  mov     ecx, eax
0x1800b8531  lea     rdx, aAddpolicyentry_8; "AddPolicyEntry:JetSetColumns"
0x1800b8538  call    PolicyMapJetError
0x1800b853d  xor     r13d, r13d
0x1800b8540  mov     edi, eax
0x1800b8542  test    eax, eax
0x1800b8544  jnz     loc_1800B8666
0x1800b854a  mov     eax, cs:dword_1800F9830
0x1800b8550  mov     ebx, r13d
0x1800b8553  mov     [rsp+230h+var_1E0.columnid], eax
0x1800b8557  mov     rax, [r14+28h]
0x1800b855b  mov     [rsp+230h+var_1E0.err], r13d
0x1800b8560  mov     qword ptr [rsp+230h+var_1E0.grbit], r13
0x1800b8565  mov     [rsp+230h+var_1E0.cbData], 4
0x1800b856d  mov     ecx, [rax]
0x1800b856f  test    ecx, ecx
0x1800b8571  jz      short loc_1800B85CF
0x1800b8573  mov     r12, [rsp+230h+var_1B8]
0x1800b8578  mov     eax, ebx
0x1800b857a  lea     r8, [rsp+230h+var_1E0]; psetcolumn
0x1800b857f  mov     r9d, 1; csetcolumn
0x1800b8585  mov     rdx, r15; tableid
0x1800b8588  lea     rcx, [r12+rax*4]
0x1800b858c  lea     eax, [rbx+1]
0x1800b858f  mov     [rsp+230h+var_1E0.pvData], rcx
0x1800b8594  mov     rcx, rsi; sesid
0x1800b8597  mov     [rsp+230h+var_1E0.itagSequence], eax
0x1800b859b  mov     ebx, eax
0x1800b859d  call    cs:__imp_JetSetColumns
0x1800b85a4  nop     dword ptr [rax+rax+00h]
0x1800b85a9  mov     ecx, eax
0x1800b85ab  lea     rdx, aAddpolicyentry_6; "AddPolicyEntry:JetSetColumns2"
0x1800b85b2  call    PolicyMapJetError
0x1800b85b7  mov     edi, eax
0x1800b85b9  test    eax, eax
0x1800b85bb  jnz     loc_1800B8666
0x1800b85c1  mov     rax, [r14+28h]
0x1800b85c5  mov     ecx, [rax]
0x1800b85c7  cmp     ebx, ecx
0x1800b85c9  jb      short loc_1800B8578
0x1800b85cb  test    ecx, ecx
0x1800b85cd  jnz     short loc_1800B8610
0x1800b85cf  mov     eax, 1
0x1800b85d4  mov     [rsp+230h+var_1E0.pvData], r13
0x1800b85d9  mov     r9d, eax; csetcolumn
0x1800b85dc  mov     [rsp+230h+var_1E0.cbData], r13d
0x1800b85e1  lea     r8, [rsp+230h+var_1E0]; psetcolumn
0x1800b85e6  mov     [rsp+230h+var_1E0.itagSequence], eax
0x1800b85ea  mov     rdx, r15; tableid
0x1800b85ed  mov     rcx, rsi; sesid
0x1800b85f0  call    cs:__imp_JetSetColumns
0x1800b85f7  nop     dword ptr [rax+rax+00h]
0x1800b85fc  mov     ecx, eax
0x1800b85fe  lea     rdx, aAddpolicyentry_6; "AddPolicyEntry:JetSetColumns2"
0x1800b8605  call    PolicyMapJetError
0x1800b860a  mov     edi, eax
0x1800b860c  test    eax, eax
0x1800b860e  jnz     short loc_1800B8666
0x1800b8610  xor     r9d, r9d; cbBookmark
0x1800b8613  mov     qword ptr [rsp+230h+cbData], r13; pcbActual
0x1800b8618  xor     r8d, r8d; pvBookmark
0x1800b861b  mov     rdx, r15; tableid
0x1800b861e  mov     rcx, rsi; sesid
0x1800b8621  call    cs:__imp_JetUpdate
0x1800b8628  nop     dword ptr [rax+rax+00h]
0x1800b862d  mov     ecx, eax
0x1800b862f  lea     rdx, aAddpolicyentry_5; "AddPolicyEntry:JetUPdate"
0x1800b8636  call    PolicyMapJetError
0x1800b863b  mov     edi, eax
0x1800b863d  test    eax, eax
0x1800b863f  jnz     short loc_1800B8666
0x1800b8641  xor     edx, edx; grbit
0x1800b8643  mov     rcx, rsi; sesid
0x1800b8646  call    cs:__imp_JetCommitTransaction
0x1800b864d  nop     dword ptr [rax+rax+00h]
0x1800b8652  mov     ecx, eax
0x1800b8654  lea     rdx, aAddpolicyentry_7; "AddPolicyEntry:JetCommitTransaction"
0x1800b865b  call    PolicyMapJetError
0x1800b8660  mov     edi, eax
0x1800b8662  test    eax, eax
0x1800b8664  jz      short loc_1800B8677
0x1800b8666  xor     edx, edx; grbit
0x1800b8668  mov     rcx, rsi; sesid
0x1800b866b  call    cs:__imp_JetRollback
0x1800b8672  nop     dword ptr [rax+rax+00h]
0x1800b8677  mov     eax, edi
0x1800b8679  mov     rcx, [rbp+130h+var_40]
0x1800b8680  xor     rcx, rsp; StackCookie
0x1800b8683  call    __security_check_cookie
0x1800b8688  mov     rbx, [rsp+230h+arg_8]
0x1800b8690  add     rsp, 200h
0x1800b8697  pop     r15
0x1800b8699  pop     r14
0x1800b869b  pop     r13
0x1800b869d  pop     r12
0x1800b869f  pop     rdi
0x1800b86a0  pop     rsi
0x1800b86a1  pop     rbp
0x1800b86a2  retn
```
