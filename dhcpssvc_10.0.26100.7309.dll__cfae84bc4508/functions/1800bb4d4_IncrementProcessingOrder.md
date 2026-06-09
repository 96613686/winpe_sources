# IncrementProcessingOrder

- ea: `0x1800bb4d4`
- end: `0x1800bb67f`
- name: `IncrementProcessingOrder`
- size: `427`
- prototype: `__int64 __fastcall(JET_SESID sesid, JET_TABLEID tableid)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1800b7404`
- `0x1800bc1fc`

## callees

- `0x1800bb4d4`
- `0x1800bba04`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800bb534`
- `ESENT!JetSetCurrentIndexA` at `0x1800bb534`
- `ESENT!JetSetColumns` at `0x1800bb624`
- `ESENT!JetSetColumns` at `0x1800bb624`
- `ESENT!JetUpdate` at `0x1800bb654`
- `ESENT!JetUpdate` at `0x1800bb654`
- `ESENT!JetMakeKey` at `0x1800bb56b`
- `ESENT!JetMakeKey` at `0x1800bb59e`
- `ESENT!JetMakeKey` at `0x1800bb56b`
- `ESENT!JetMakeKey` at `0x1800bb59e`
- `ESENT!JetSeek` at `0x1800bb5ca`
- `ESENT!JetSeek` at `0x1800bb5ca`
- `ESENT!JetPrepareUpdate` at `0x1800bb5f8`
- `ESENT!JetPrepareUpdate` at `0x1800bb5f8`

## string_xrefs

- `0x1800bb662`: `AddPolicyEntry:Jetupdate`
- `0x1800bb606`: `AddPolicyEntry:JetPrepareUpdate`

## pseudocode

```c
__int64 __fastcall IncrementProcessingOrder(JET_SESID sesid, JET_TABLEID tableid, int a3, int a4)
{
  unsigned int v6; // eax
  __int64 result; // rax
  unsigned int Key; // eax
  unsigned int v9; // eax
  unsigned int v10; // ebx
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  int v14; // [rsp+30h] [rbp-30h] BYREF
  JET_SETCOLUMN psetcolumn; // [rsp+38h] [rbp-28h] BYREF
  int pvData; // [rsp+90h] [rbp+30h] BYREF
  int v17; // [rsp+98h] [rbp+38h] BYREF

  v17 = a4;
  pvData = a3;
  memset(&psetcolumn.grbit, 0, 20);
  v14 = a4 + 1;
  psetcolumn.columnid = dword_1800F7618;
  *(&psetcolumn.columnid + 1) = 0;
  psetcolumn.pvData = &v14;
  psetcolumn.cbData = 4;
  v6 = JetSetCurrentIndexA(sesid, tableid, "PolicyTable_Index3");
  result = PolicyMapJetError(v6, "AddPolicyEntry:JetSetCUrrentIndex");
  if ( !(_DWORD)result )
  {
    Key = JetMakeKey(sesid, tableid, &pvData, 4u, 1u);
    result = PolicyMapJetError(Key, "AddPolicyEntry:JetMakeKey");
    if ( !(_DWORD)result )
    {
      v9 = JetMakeKey(sesid, tableid, &v17, 4u, 0);
      result = PolicyMapJetError(v9, "AddPolicyEntry:JetMakeKey2");
      if ( !(_DWORD)result )
      {
        v10 = JetSeek(sesid, tableid, 1u);
        result = PolicyMapJetError(v10, "AddPolicyEntry:JetSeek");
        if ( !v10 )
        {
          v11 = JetPrepareUpdate(sesid, tableid, 2u);
          result = PolicyMapJetError(v11, "AddPolicyEntry:JetPrepareUpdate");
          if ( !(_DWORD)result )
          {
            v12 = JetSetColumns(sesid, tableid, &psetcolumn, 1u);
            result = PolicyMapJetError(v12, "AddPolicyEntry:JetSetColumns");
            if ( !(_DWORD)result )
            {
              v13 = JetUpdate(sesid, tableid, 0, 0, 0);
              return PolicyMapJetError(v13, "AddPolicyEntry:Jetupdate");
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800bb4d4  mov     [rsp-18h+arg_0], rbx
0x1800bb4d9  mov     [rsp-18h+arg_18], r9d
0x1800bb4de  mov     [rsp-18h+pvData], r8d
0x1800bb4e3  push    rbp
0x1800bb4e4  push    rsi
0x1800bb4e5  push    rdi
0x1800bb4e6  mov     rbp, rsp
0x1800bb4e9  sub     rsp, 60h
0x1800bb4ed  and     [rbp+psetcolumn.grbit], 0
0x1800bb4f1  lea     eax, [r9+1]
0x1800bb4f5  and     [rbp+psetcolumn.ibLongValue], 0
0x1800bb4f9  lea     r8, aPolicytableInd_0; "PolicyTable_Index3"
0x1800bb500  and     [rbp+psetcolumn.itagSequence], 0
0x1800bb504  mov     ebx, 4
0x1800bb509  and     [rbp+psetcolumn.err], 0
0x1800bb50d  mov     rdi, rdx
0x1800bb510  mov     [rbp+var_30], eax
0x1800bb513  mov     rsi, rcx
0x1800bb516  mov     eax, cs:dword_1800F7618
0x1800bb51c  mov     [rbp+psetcolumn.columnid], eax
0x1800bb51f  xor     eax, eax
0x1800bb521  mov     dword ptr [rbp+psetcolumn+4], eax
0x1800bb524  lea     rax, [rbp+var_30]
0x1800bb528  mov     [rbp+psetcolumn.pvData], rax
0x1800bb52c  xor     eax, eax
0x1800bb52e  mov     dword ptr [rbp+psetcolumn+24h], eax
0x1800bb531  mov     [rbp+psetcolumn.cbData], ebx
0x1800bb534  call    cs:__imp_JetSetCurrentIndexA
0x1800bb53b  nop     dword ptr [rax+rax+00h]
0x1800bb540  mov     ecx, eax
0x1800bb542  lea     rdx, aAddpolicyentry_9; "AddPolicyEntry:JetSetCUrrentIndex"
0x1800bb549  call    PolicyMapJetError
0x1800bb54e  test    eax, eax
0x1800bb550  jnz     loc_1800BB66E
0x1800bb556  mov     r9d, ebx; cbData
0x1800bb559  mov     [rsp+60h+grbit], 1; pcbActual
0x1800bb561  lea     r8, [rbp+pvData]; pvData
0x1800bb565  mov     rdx, rdi; tableid
0x1800bb568  mov     rcx, rsi; sesid
0x1800bb56b  call    cs:__imp_JetMakeKey
0x1800bb572  nop     dword ptr [rax+rax+00h]
0x1800bb577  mov     ecx, eax
0x1800bb579  lea     rdx, aAddpolicyentry_3; "AddPolicyEntry:JetMakeKey"
0x1800bb580  call    PolicyMapJetError
0x1800bb585  test    eax, eax
0x1800bb587  jnz     loc_1800BB66E
0x1800bb58d  and     [rsp+60h+grbit], eax
0x1800bb591  lea     r8, [rbp+arg_18]; pvData
0x1800bb595  mov     r9d, ebx; cbData
0x1800bb598  mov     rdx, rdi; tableid
0x1800bb59b  mov     rcx, rsi; sesid
0x1800bb59e  call    cs:__imp_JetMakeKey
0x1800bb5a5  nop     dword ptr [rax+rax+00h]
0x1800bb5aa  mov     ecx, eax
0x1800bb5ac  lea     rdx, aAddpolicyentry_2; "AddPolicyEntry:JetMakeKey2"
0x1800bb5b3  call    PolicyMapJetError
0x1800bb5b8  test    eax, eax
0x1800bb5ba  jnz     loc_1800BB66E
0x1800bb5c0  lea     r8d, [rbx-3]; grbit
0x1800bb5c4  mov     rdx, rdi; tableid
0x1800bb5c7  mov     rcx, rsi; sesid
0x1800bb5ca  call    cs:__imp_JetSeek
0x1800bb5d1  nop     dword ptr [rax+rax+00h]
0x1800bb5d6  mov     ecx, eax
0x1800bb5d8  lea     rdx, aAddpolicyentry_0; "AddPolicyEntry:JetSeek"
0x1800bb5df  mov     ebx, eax
0x1800bb5e1  call    PolicyMapJetError
0x1800bb5e6  test    ebx, ebx
0x1800bb5e8  jnz     loc_1800BB66E
0x1800bb5ee  lea     r8d, [rbx+2]; prep
0x1800bb5f2  mov     rdx, rdi; tableid
0x1800bb5f5  mov     rcx, rsi; sesid
0x1800bb5f8  call    cs:__imp_JetPrepareUpdate
0x1800bb5ff  nop     dword ptr [rax+rax+00h]
0x1800bb604  mov     ecx, eax
0x1800bb606  lea     rdx, aAddpolicyentry; "AddPolicyEntry:JetPrepareUpdate"
0x1800bb60d  call    PolicyMapJetError
0x1800bb612  test    eax, eax
0x1800bb614  jnz     short loc_1800BB66E
0x1800bb616  lea     r9d, [rbx+1]; csetcolumn
0x1800bb61a  mov     rdx, rdi; tableid
0x1800bb61d  lea     r8, [rbp+psetcolumn]; psetcolumn
0x1800bb621  mov     rcx, rsi; sesid
0x1800bb624  call    cs:__imp_JetSetColumns
0x1800bb62b  nop     dword ptr [rax+rax+00h]
0x1800bb630  mov     ecx, eax
0x1800bb632  lea     rdx, aAddpolicyentry_8; "AddPolicyEntry:JetSetColumns"
0x1800bb639  call    PolicyMapJetError
0x1800bb63e  test    eax, eax
0x1800bb640  jnz     short loc_1800BB66E
0x1800bb642  and     qword ptr [rsp+60h+grbit], 0
0x1800bb648  xor     r9d, r9d; cbBookmark
0x1800bb64b  xor     r8d, r8d; pvBookmark
0x1800bb64e  mov     rdx, rdi; tableid
0x1800bb651  mov     rcx, rsi; sesid
0x1800bb654  call    cs:__imp_JetUpdate
0x1800bb65b  nop     dword ptr [rax+rax+00h]
0x1800bb660  mov     ecx, eax
0x1800bb662  lea     rdx, aAddpolicyentry_1; "AddPolicyEntry:Jetupdate"
0x1800bb669  call    PolicyMapJetError
0x1800bb66e  mov     rbx, [rsp+60h+arg_0]
0x1800bb676  add     rsp, 60h
0x1800bb67a  pop     rdi
0x1800bb67b  pop     rsi
0x1800bb67c  pop     rbp
0x1800bb67d  retn
```
