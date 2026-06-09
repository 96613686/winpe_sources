# AddPolicyRangeEntries

- ea: `0x1800b86ac`
- end: `0x1800b893a`
- name: `AddPolicyRangeEntries`
- size: `654`
- prototype: `__int64 __fastcall(JET_SESID sesid)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x180087658`
- `0x1800b8118`
- `0x1800bd190`

## callees

- `0x1800b86ac`
- `0x1800bb4b8`
- `0x1800bc990`
- `0x1800cdac0`

## import_xrefs

- `ESENT!JetSetColumns` at `0x1800b889f`
- `ESENT!JetSetColumns` at `0x1800b889f`
- `ESENT!JetSetCurrentIndex2A` at `0x1800b8714`
- `ESENT!JetSetCurrentIndex2A` at `0x1800b8714`
- `ESENT!JetUpdate` at `0x1800b88d2`
- `ESENT!JetUpdate` at `0x1800b88d2`
- `ESENT!JetPrepareUpdate` at `0x1800b886f`
- `ESENT!JetPrepareUpdate` at `0x1800b886f`
- `ESENT!JetRetrieveColumn` at `0x1800b8766`
- `ESENT!JetRetrieveColumn` at `0x1800b8766`

## string_xrefs

- `0x1800b887d`: `AddPolicyRangeEntry:JetPrepareUpdate`
- `0x1800b88e0`: `AddPolicyRangeEntry:JetUPdate`

## pseudocode

```c
__int64 __fastcall AddPolicyRangeEntries(JET_SESID sesid, unsigned int *a2, int *a3)
{
  unsigned int v3; // r13d
  __int64 result; // rax
  unsigned int v7; // r15d
  __int64 v8; // r12
  unsigned int v9; // eax
  unsigned int v10; // ebx
  int v11; // edi
  __int64 v12; // rax
  __int64 v13; // rcx
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  int v17; // [rsp+40h] [rbp-89h] BYREF
  int v18; // [rsp+44h] [rbp-85h] BYREF
  int v19; // [rsp+48h] [rbp-81h] BYREF
  __int64 v20; // [rsp+50h] [rbp-79h] BYREF
  unsigned int *v21; // [rsp+58h] [rbp-71h]
  JET_SETCOLUMN psetcolumn; // [rsp+60h] [rbp-69h] BYREF
  int v23; // [rsp+88h] [rbp-41h]
  __int64 *v24; // [rsp+90h] [rbp-39h]
  __int64 v25; // [rsp+98h] [rbp-31h]
  __int64 v26; // [rsp+A0h] [rbp-29h]
  int v27; // [rsp+A8h] [rbp-21h]
  int v28; // [rsp+B0h] [rbp-19h]
  char *v29; // [rsp+B8h] [rbp-11h]
  __int64 v30; // [rsp+C0h] [rbp-9h]
  __int64 v31; // [rsp+C8h] [rbp-1h]
  int v32; // [rsp+D0h] [rbp+7h]

  v3 = *a2;
  v21 = a2;
  v17 = 0;
  result = 0;
  v7 = 0;
  if ( v3 )
  {
    v8 = 0;
    do
    {
      v18 = 0;
      v9 = JetSetCurrentIndex2A(sesid, PolicyRangeTableId, "PolicyRangeTable_Index1", 0);
      result = PolicyMapJetError(v9, "GetAvailablePolicyRangeId:JetSetCurrentIndex");
      if ( (_DWORD)result )
        break;
      v10 = JetRetrieveColumn(sesid, PolicyRangeTableId, dword_1800F9738, &v18, 4u, 0, 1u, 0);
      result = PolicyMapJetError(v10, "GetAvailablePolicyRangeId:JetRetrieveColumn");
      if ( v10 == -1603 )
      {
        v11 = 1;
        v17 = 1;
      }
      else
      {
        if ( (_DWORD)result )
          return result;
        if ( v18 == -1 )
        {
          result = FindIdFromGaps(sesid, PolicyRangeTableId, dword_1800F9738, "PolicyRangeTable_Index1", (__int64)&v17);
          v11 = v17;
          if ( (_DWORD)result )
            return result;
        }
        else
        {
          v11 = v18 + 1;
          v17 = v18 + 1;
        }
      }
      *(_QWORD *)&psetcolumn.cbData = 4;
      *(_QWORD *)&psetcolumn.ibLongValue = 0;
      v12 = *((_QWORD *)v21 + 1);
      psetcolumn.err = 0;
      v25 = 4;
      v26 = 0;
      v13 = *(_QWORD *)(v8 + v12);
      psetcolumn.columnid = dword_1800F9738;
      psetcolumn.pvData = &v19;
      v23 = dword_1800F9750;
      v24 = &v20;
      v28 = dword_1800F9768;
      v20 = v13;
      v29 = (char *)&v20 + 4;
      v19 = v11;
      v27 = 0;
      v30 = 4;
      v31 = 0;
      v32 = 0;
      v14 = JetPrepareUpdate(sesid, PolicyRangeTableId, 0);
      result = PolicyMapJetError(v14, "AddPolicyRangeEntry:JetPrepareUpdate");
      if ( (_DWORD)result )
        break;
      v15 = JetSetColumns(sesid, PolicyRangeTableId, &psetcolumn, 3u);
      result = PolicyMapJetError(v15, "AddPolicyRangeEntry:JetSetColumns");
      if ( (_DWORD)result )
        break;
      v16 = JetUpdate(sesid, PolicyRangeTableId, 0, 0, 0);
      result = PolicyMapJetError(v16, "AddPolicyRangeEntry:JetUPdate");
      if ( (_DWORD)result )
        break;
      *a3 = v11;
      ++v7;
      ++a3;
      v8 += 8;
    }
    while ( v7 < v3 );
  }
  return result;
}

```

## disassembly

```asm
0x1800b86ac  mov     [rsp-8+arg_18], rbx
0x1800b86b1  push    rbp
0x1800b86b2  push    rsi
0x1800b86b3  push    rdi
0x1800b86b4  push    r12
0x1800b86b6  push    r13
0x1800b86b8  push    r14
0x1800b86ba  push    r15
0x1800b86bc  lea     rbp, [rsp-27h]
0x1800b86c1  sub     rsp, 0F0h
0x1800b86c8  mov     rax, cs:__security_cookie
0x1800b86cf  xor     rax, rsp
0x1800b86d2  mov     [rbp+57h+var_40], rax
0x1800b86d6  mov     r13d, [rdx]
0x1800b86d9  xor     ebx, ebx
0x1800b86db  mov     [rbp+57h+var_C8], rdx
0x1800b86df  mov     r14, r8
0x1800b86e2  mov     dword ptr [rsp+120h+var_E0], ebx
0x1800b86e6  mov     rsi, rcx
0x1800b86e9  mov     eax, ebx
0x1800b86eb  mov     edi, ebx
0x1800b86ed  mov     r15d, ebx
0x1800b86f0  test    r13d, r13d
0x1800b86f3  jz      loc_1800B8907
0x1800b86f9  mov     r12d, ebx
0x1800b86fc  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800b8703  lea     r8, aPolicyrangetab_3; "PolicyRangeTable_Index1"
0x1800b870a  xor     r9d, r9d; grbit
0x1800b870d  mov     dword ptr [rsp+120h+var_E0+4], ebx
0x1800b8711  mov     rcx, rsi; sesid
0x1800b8714  call    cs:__imp_JetSetCurrentIndex2A
0x1800b871b  nop     dword ptr [rax+rax+00h]
0x1800b8720  mov     ecx, eax
0x1800b8722  lea     rdx, aGetavailablepo_4; "GetAvailablePolicyRangeId:JetSetCurrent"...
0x1800b8729  call    PolicyMapJetError
0x1800b872e  test    eax, eax
0x1800b8730  jnz     loc_1800B8907
0x1800b8736  mov     r8d, cs:dword_1800F9738; columnid
0x1800b873d  lea     r9, [rsp+120h+var_E0+4]; pvData
0x1800b8742  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800b8749  mov     rcx, rsi; sesid
0x1800b874c  mov     [rsp+120h+pretinfo], rbx; pretinfo
0x1800b8751  mov     [rsp+120h+grbit], 1; grbit
0x1800b8759  mov     [rsp+120h+pcbActual], rbx; pcbActual
0x1800b875e  mov     [rsp+120h+cbData], 4; cbData
0x1800b8766  call    cs:__imp_JetRetrieveColumn
0x1800b876d  nop     dword ptr [rax+rax+00h]
0x1800b8772  mov     ecx, eax
0x1800b8774  lea     rdx, aGetavailablepo_2; "GetAvailablePolicyRangeId:JetRetrieveCo"...
0x1800b877b  mov     ebx, eax
0x1800b877d  call    PolicyMapJetError
0x1800b8782  cmp     ebx, 0FFFFF9BDh
0x1800b8788  jnz     short loc_1800B8797
0x1800b878a  mov     edi, 1
0x1800b878f  xor     ebx, ebx
0x1800b8791  mov     dword ptr [rsp+120h+var_E0], edi
0x1800b8795  jmp     short loc_1800B87E1
0x1800b8797  xor     ebx, ebx
0x1800b8799  test    eax, eax
0x1800b879b  jnz     loc_1800B8907
0x1800b87a1  mov     edi, dword ptr [rsp+120h+var_E0+4]
0x1800b87a5  cmp     edi, 0FFFFFFFFh
0x1800b87a8  jnz     loc_1800B892F
0x1800b87ae  mov     r8d, cs:dword_1800F9738; columnid
0x1800b87b5  lea     rax, [rsp+120h+var_E0]
0x1800b87ba  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800b87c1  lea     r9, aPolicyrangetab_3; "PolicyRangeTable_Index1"
0x1800b87c8  mov     rcx, rsi; sesid
0x1800b87cb  mov     qword ptr [rsp+120h+cbData], rax; __int64
0x1800b87d0  call    FindIdFromGaps
0x1800b87d5  mov     edi, dword ptr [rsp+120h+var_E0]
0x1800b87d9  test    eax, eax
0x1800b87db  jnz     loc_1800B8907
0x1800b87e1  mov     rax, [rbp+57h+var_C8]
0x1800b87e5  xor     r8d, r8d; prep
0x1800b87e8  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800b87ef  mov     qword ptr [rbp+57h+psetcolumn.cbData], 4
0x1800b87f7  mov     qword ptr [rbp+57h+psetcolumn.ibLongValue], 0
0x1800b87ff  mov     rax, [rax+8]
0x1800b8803  mov     [rbp+57h+psetcolumn.err], ebx
0x1800b8806  mov     [rbp+57h+var_88], 4
0x1800b880e  mov     [rbp+57h+var_80], 0
0x1800b8816  mov     rcx, [r12+rax]
0x1800b881a  mov     eax, cs:dword_1800F9738
0x1800b8820  mov     [rbp+57h+psetcolumn.columnid], eax
0x1800b8823  lea     rax, [rsp+120h+var_D8]
0x1800b8828  mov     [rbp+57h+psetcolumn.pvData], rax
0x1800b882c  mov     eax, cs:dword_1800F9750
0x1800b8832  mov     [rbp+57h+var_98], eax
0x1800b8835  lea     rax, [rbp+57h+var_D0]
0x1800b8839  mov     [rbp+57h+var_90], rax
0x1800b883d  mov     eax, cs:dword_1800F9768
0x1800b8843  mov     [rbp+57h+var_70], eax
0x1800b8846  lea     rax, [rbp+57h+var_D0+4]
0x1800b884a  mov     [rbp+57h+var_D0], rcx
0x1800b884e  mov     rcx, rsi; sesid
0x1800b8851  mov     [rbp+57h+var_68], rax
0x1800b8855  mov     [rsp+120h+var_D8], edi
0x1800b8859  mov     [rbp+57h+var_78], ebx
0x1800b885c  mov     [rbp+57h+var_60], 4
0x1800b8864  mov     [rbp+57h+var_58], 0
0x1800b886c  mov     [rbp+57h+var_50], ebx
0x1800b886f  call    cs:__imp_JetPrepareUpdate
0x1800b8876  nop     dword ptr [rax+rax+00h]
0x1800b887b  mov     ecx, eax
0x1800b887d  lea     rdx, aAddpolicyrange; "AddPolicyRangeEntry:JetPrepareUpdate"
0x1800b8884  call    PolicyMapJetError
0x1800b8889  test    eax, eax
0x1800b888b  jnz     short loc_1800B8907
0x1800b888d  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800b8894  lea     r9d, [rax+3]; csetcolumn
0x1800b8898  lea     r8, [rbp+57h+psetcolumn]; psetcolumn
0x1800b889c  mov     rcx, rsi; sesid
0x1800b889f  call    cs:__imp_JetSetColumns
0x1800b88a6  nop     dword ptr [rax+rax+00h]
0x1800b88ab  mov     ecx, eax
0x1800b88ad  lea     rdx, aAddpolicyrange_1; "AddPolicyRangeEntry:JetSetColumns"
0x1800b88b4  call    PolicyMapJetError
0x1800b88b9  test    eax, eax
0x1800b88bb  jnz     short loc_1800B8907
0x1800b88bd  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800b88c4  xor     r9d, r9d; cbBookmark
0x1800b88c7  xor     r8d, r8d; pvBookmark
0x1800b88ca  mov     qword ptr [rsp+120h+cbData], rbx; pcbActual
0x1800b88cf  mov     rcx, rsi; sesid
0x1800b88d2  call    cs:__imp_JetUpdate
0x1800b88d9  nop     dword ptr [rax+rax+00h]
0x1800b88de  mov     ecx, eax
0x1800b88e0  lea     rdx, aAddpolicyrange_0; "AddPolicyRangeEntry:JetUPdate"
0x1800b88e7  call    PolicyMapJetError
0x1800b88ec  test    eax, eax
0x1800b88ee  jnz     short loc_1800B8907
0x1800b88f0  mov     [r14], edi
0x1800b88f3  inc     r15d
0x1800b88f6  add     r14, 4
0x1800b88fa  add     r12, 8
0x1800b88fe  cmp     r15d, r13d
0x1800b8901  jb      loc_1800B86FC
0x1800b8907  mov     rcx, [rbp+57h+var_40]
0x1800b890b  xor     rcx, rsp; StackCookie
0x1800b890e  call    __security_check_cookie
0x1800b8913  mov     rbx, [rsp+120h+arg_18]
0x1800b891b  add     rsp, 0F0h
0x1800b8922  pop     r15
0x1800b8924  pop     r14
0x1800b8926  pop     r13
0x1800b8928  pop     r12
0x1800b892a  pop     rdi
0x1800b892b  pop     rsi
0x1800b892c  pop     rbp
0x1800b892d  retn
0x1800b892f  inc     edi
0x1800b8931  mov     dword ptr [rsp+120h+var_E0], edi
0x1800b8935  jmp     loc_1800B87E1
```
