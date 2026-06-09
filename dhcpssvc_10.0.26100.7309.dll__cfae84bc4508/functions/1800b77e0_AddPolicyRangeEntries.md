# AddPolicyRangeEntries

- ea: `0x1800b77e0`
- end: `0x1800b7a53`
- name: `AddPolicyRangeEntries`
- size: `627`
- prototype: `__int64 __fastcall(JET_SESID sesid)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1800876d4`
- `0x1800b7248`
- `0x1800bc1fc`

## callees

- `0x1800b77e0`
- `0x1800ba598`
- `0x1800bba04`
- `0x1800cc9e0`

## import_xrefs

- `ESENT!JetSetColumns` at `0x1800b79c3`
- `ESENT!JetSetColumns` at `0x1800b79c3`
- `ESENT!JetSetCurrentIndex2A` at `0x1800b7844`
- `ESENT!JetSetCurrentIndex2A` at `0x1800b7844`
- `ESENT!JetUpdate` at `0x1800b79f7`
- `ESENT!JetUpdate` at `0x1800b79f7`
- `ESENT!JetPrepareUpdate` at `0x1800b7993`
- `ESENT!JetPrepareUpdate` at `0x1800b7993`
- `ESENT!JetRetrieveColumn` at `0x1800b7898`
- `ESENT!JetRetrieveColumn` at `0x1800b7898`

## string_xrefs

- `0x1800b7a05`: `AddPolicyRangeEntry:JetUPdate`
- `0x1800b79a1`: `AddPolicyRangeEntry:JetPrepareUpdate`

## pseudocode

```c
__int64 __fastcall AddPolicyRangeEntries(JET_SESID sesid, unsigned int *a2, int *a3)
{
  unsigned int v3; // r12d
  __int64 result; // rax
  unsigned int v5; // r14d
  __int64 v9; // r15
  unsigned int v10; // eax
  unsigned int v11; // ebx
  int v12; // ebx
  __int64 v13; // rax
  __int64 v14; // rcx
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  int v18; // [rsp+40h] [rbp-89h] BYREF
  int v19; // [rsp+44h] [rbp-85h] BYREF
  int v20; // [rsp+48h] [rbp-81h] BYREF
  _QWORD v21[2]; // [rsp+50h] [rbp-79h] BYREF
  JET_SETCOLUMN psetcolumn; // [rsp+60h] [rbp-69h] BYREF
  int v23; // [rsp+88h] [rbp-41h]
  _QWORD *v24; // [rsp+90h] [rbp-39h]
  __int64 v25; // [rsp+98h] [rbp-31h]
  __int64 v26; // [rsp+A0h] [rbp-29h]
  int v27; // [rsp+A8h] [rbp-21h]
  int v28; // [rsp+B0h] [rbp-19h]
  char *v29; // [rsp+B8h] [rbp-11h]
  __int64 v30; // [rsp+C0h] [rbp-9h]
  __int64 v31; // [rsp+C8h] [rbp-1h]
  int v32; // [rsp+D0h] [rbp+7h]

  v3 = *a2;
  result = 0;
  v18 = 0;
  v5 = 0;
  if ( v3 )
  {
    v9 = 0;
    while ( 1 )
    {
      v19 = 0;
      v10 = JetSetCurrentIndex2A(sesid, PolicyRangeTableId, "PolicyRangeTable_Index1", 0);
      result = PolicyMapJetError(v10, "GetAvailablePolicyRangeId:JetSetCurrentIndex");
      if ( (_DWORD)result )
        break;
      v11 = JetRetrieveColumn(sesid, PolicyRangeTableId, dword_1800F7568, &v19, 4u, 0, 1u, 0);
      result = PolicyMapJetError(v11, "GetAvailablePolicyRangeId:JetRetrieveColumn");
      if ( v11 == -1603 )
      {
        v12 = 1;
        v18 = 1;
      }
      else
      {
        if ( (_DWORD)result )
          return result;
        if ( v19 == -1 )
        {
          result = FindIdFromGaps(sesid, PolicyRangeTableId, dword_1800F7568, "PolicyRangeTable_Index1", (__int64)&v18);
          v12 = v18;
        }
        else
        {
          v12 = v19 + 1;
          v18 = v19 + 1;
        }
        if ( (_DWORD)result )
          return result;
      }
      v13 = *((_QWORD *)a2 + 1);
      *(_QWORD *)&psetcolumn.cbData = 4;
      v25 = 4;
      v14 = *(_QWORD *)(v9 + v13);
      psetcolumn.columnid = dword_1800F7568;
      psetcolumn.pvData = &v20;
      v23 = dword_1800F7580;
      v24 = v21;
      v21[0] = v14;
      v28 = dword_1800F7598;
      *(_QWORD *)&psetcolumn.ibLongValue = 0;
      psetcolumn.err = 0;
      v26 = 0;
      v27 = 0;
      v31 = 0;
      v32 = 0;
      v29 = (char *)v21 + 4;
      v20 = v12;
      v30 = 4;
      v15 = JetPrepareUpdate(sesid, PolicyRangeTableId, 0);
      result = PolicyMapJetError(v15, "AddPolicyRangeEntry:JetPrepareUpdate");
      if ( !(_DWORD)result )
      {
        v16 = JetSetColumns(sesid, PolicyRangeTableId, &psetcolumn, 3u);
        result = PolicyMapJetError(v16, "AddPolicyRangeEntry:JetSetColumns");
        if ( !(_DWORD)result )
        {
          v17 = JetUpdate(sesid, PolicyRangeTableId, 0, 0, 0);
          result = PolicyMapJetError(v17, "AddPolicyRangeEntry:JetUPdate");
          if ( !(_DWORD)result )
          {
            *a3 = v12;
            ++v5;
            ++a3;
            v9 += 8;
            if ( v5 < v3 )
              continue;
          }
        }
      }
      return result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800b77e0  mov     [rsp-8+arg_18], rbx
0x1800b77e5  push    rbp
0x1800b77e6  push    rsi
0x1800b77e7  push    rdi
0x1800b77e8  push    r12
0x1800b77ea  push    r13
0x1800b77ec  push    r14
0x1800b77ee  push    r15
0x1800b77f0  lea     rbp, [rsp-27h]
0x1800b77f5  sub     rsp, 0F0h
0x1800b77fc  mov     rax, cs:__security_cookie
0x1800b7803  xor     rax, rsp
0x1800b7806  mov     [rbp+57h+var_40], rax
0x1800b780a  mov     r12d, [rdx]
0x1800b780d  xor     eax, eax
0x1800b780f  and     dword ptr [rsp+120h+var_E0], eax
0x1800b7813  xor     r14d, r14d
0x1800b7816  mov     rsi, r8
0x1800b7819  mov     r13, rdx
0x1800b781c  mov     rdi, rcx
0x1800b781f  test    r12d, r12d
0x1800b7822  jz      loc_1800B7A2B
0x1800b7828  xor     r15d, r15d
0x1800b782b  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800b7832  lea     r8, aPolicyrangetab_3; "PolicyRangeTable_Index1"
0x1800b7839  and     dword ptr [rsp+120h+var_E0+4], 0
0x1800b783e  xor     r9d, r9d; grbit
0x1800b7841  mov     rcx, rdi; sesid
0x1800b7844  call    cs:__imp_JetSetCurrentIndex2A
0x1800b784b  nop     dword ptr [rax+rax+00h]
0x1800b7850  mov     ecx, eax
0x1800b7852  lea     rdx, aGetavailablepo_4; "GetAvailablePolicyRangeId:JetSetCurrent"...
0x1800b7859  call    PolicyMapJetError
0x1800b785e  test    eax, eax
0x1800b7860  jnz     loc_1800B7A2B
0x1800b7866  and     [rsp+120h+var_E8], 0
0x1800b786c  lea     r9, [rsp+120h+var_E0+4]; pvData
0x1800b7871  mov     r8d, cs:dword_1800F7568; columnid
0x1800b7878  mov     rcx, rdi; sesid
0x1800b787b  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800b7882  mov     [rsp+120h+grbit], 1; grbit
0x1800b788a  and     [rsp+120h+var_F8], 0
0x1800b7890  mov     [rsp+120h+cbData], 4; pcbActual
0x1800b7898  call    cs:__imp_JetRetrieveColumn
0x1800b789f  nop     dword ptr [rax+rax+00h]
0x1800b78a4  mov     ecx, eax
0x1800b78a6  lea     rdx, aGetavailablepo_2; "GetAvailablePolicyRangeId:JetRetrieveCo"...
0x1800b78ad  mov     ebx, eax
0x1800b78af  call    PolicyMapJetError
0x1800b78b4  cmp     ebx, 0FFFFF9BDh
0x1800b78ba  jnz     short loc_1800B78C7
0x1800b78bc  mov     ebx, 1
0x1800b78c1  mov     dword ptr [rsp+120h+var_E0], ebx
0x1800b78c5  jmp     short loc_1800B7913
0x1800b78c7  test    eax, eax
0x1800b78c9  jnz     loc_1800B7A2B
0x1800b78cf  mov     ebx, dword ptr [rsp+120h+var_E0+4]
0x1800b78d3  cmp     ebx, 0FFFFFFFFh
0x1800b78d6  jnz     short loc_1800B7905
0x1800b78d8  mov     r8d, cs:dword_1800F7568; columnid
0x1800b78df  lea     rax, [rsp+120h+var_E0]
0x1800b78e4  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800b78eb  lea     r9, aPolicyrangetab_3; "PolicyRangeTable_Index1"
0x1800b78f2  mov     rcx, rdi; sesid
0x1800b78f5  mov     qword ptr [rsp+120h+cbData], rax; __int64
0x1800b78fa  call    FindIdFromGaps
0x1800b78ff  mov     ebx, dword ptr [rsp+120h+var_E0]
0x1800b7903  jmp     short loc_1800B790B
0x1800b7905  inc     ebx
0x1800b7907  mov     dword ptr [rsp+120h+var_E0], ebx
0x1800b790b  test    eax, eax
0x1800b790d  jnz     loc_1800B7A2B
0x1800b7913  mov     rax, [r13+8]
0x1800b7917  xor     r8d, r8d; prep
0x1800b791a  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800b7921  mov     qword ptr [rbp+57h+psetcolumn.cbData], 4
0x1800b7929  mov     [rbp+57h+var_88], 4
0x1800b7931  mov     rcx, [r15+rax]
0x1800b7935  mov     eax, cs:dword_1800F7568
0x1800b793b  mov     [rbp+57h+psetcolumn.columnid], eax
0x1800b793e  lea     rax, [rsp+120h+var_D8]
0x1800b7943  mov     [rbp+57h+psetcolumn.pvData], rax
0x1800b7947  mov     eax, cs:dword_1800F7580
0x1800b794d  mov     [rbp+57h+var_98], eax
0x1800b7950  lea     rax, [rbp+57h+var_D0]
0x1800b7954  mov     [rbp+57h+var_90], rax
0x1800b7958  mov     eax, cs:dword_1800F7598
0x1800b795e  mov     [rbp+57h+var_D0], rcx
0x1800b7962  xor     ecx, ecx
0x1800b7964  mov     [rbp+57h+var_70], eax
0x1800b7967  lea     rax, [rbp+57h+var_D0+4]
0x1800b796b  mov     qword ptr [rbp+57h+psetcolumn.ibLongValue], rcx
0x1800b796f  mov     [rbp+57h+psetcolumn.err], ecx
0x1800b7972  mov     [rbp+57h+var_80], rcx
0x1800b7976  mov     [rbp+57h+var_78], ecx
0x1800b7979  mov     [rbp+57h+var_58], rcx
0x1800b797d  mov     [rbp+57h+var_50], ecx
0x1800b7980  mov     rcx, rdi; sesid
0x1800b7983  mov     [rbp+57h+var_68], rax
0x1800b7987  mov     [rsp+120h+var_D8], ebx
0x1800b798b  mov     [rbp+57h+var_60], 4
0x1800b7993  call    cs:__imp_JetPrepareUpdate
0x1800b799a  nop     dword ptr [rax+rax+00h]
0x1800b799f  mov     ecx, eax
0x1800b79a1  lea     rdx, aAddpolicyrange; "AddPolicyRangeEntry:JetPrepareUpdate"
0x1800b79a8  call    PolicyMapJetError
0x1800b79ad  test    eax, eax
0x1800b79af  jnz     short loc_1800B7A2B
0x1800b79b1  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800b79b8  lea     r9d, [rax+3]; csetcolumn
0x1800b79bc  lea     r8, [rbp+57h+psetcolumn]; psetcolumn
0x1800b79c0  mov     rcx, rdi; sesid
0x1800b79c3  call    cs:__imp_JetSetColumns
0x1800b79ca  nop     dword ptr [rax+rax+00h]
0x1800b79cf  mov     ecx, eax
0x1800b79d1  lea     rdx, aAddpolicyrange_1; "AddPolicyRangeEntry:JetSetColumns"
0x1800b79d8  call    PolicyMapJetError
0x1800b79dd  test    eax, eax
0x1800b79df  jnz     short loc_1800B7A2B
0x1800b79e1  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800b79e8  xor     r9d, r9d; cbBookmark
0x1800b79eb  and     qword ptr [rsp+120h+cbData], 0
0x1800b79f1  xor     r8d, r8d; pvBookmark
0x1800b79f4  mov     rcx, rdi; sesid
0x1800b79f7  call    cs:__imp_JetUpdate
0x1800b79fe  nop     dword ptr [rax+rax+00h]
0x1800b7a03  mov     ecx, eax
0x1800b7a05  lea     rdx, aAddpolicyrange_0; "AddPolicyRangeEntry:JetUPdate"
0x1800b7a0c  call    PolicyMapJetError
0x1800b7a11  test    eax, eax
0x1800b7a13  jnz     short loc_1800B7A2B
0x1800b7a15  mov     [rsi], ebx
0x1800b7a17  inc     r14d
0x1800b7a1a  add     rsi, 4
0x1800b7a1e  add     r15, 8
0x1800b7a22  cmp     r14d, r12d
0x1800b7a25  jb      loc_1800B782B
0x1800b7a2b  mov     rcx, [rbp+57h+var_40]
0x1800b7a2f  xor     rcx, rsp; StackCookie
0x1800b7a32  call    __security_check_cookie
0x1800b7a37  mov     rbx, [rsp+120h+arg_18]
0x1800b7a3f  add     rsp, 0F0h
0x1800b7a46  pop     r15
0x1800b7a48  pop     r14
0x1800b7a4a  pop     r13
0x1800b7a4c  pop     r12
0x1800b7a4e  pop     rdi
0x1800b7a4f  pop     rsi
0x1800b7a50  pop     rbp
0x1800b7a51  retn
```
