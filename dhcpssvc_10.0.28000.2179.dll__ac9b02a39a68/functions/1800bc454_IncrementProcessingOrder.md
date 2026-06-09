# IncrementProcessingOrder

- ea: `0x1800bc454`
- end: `0x1800bc5fe`
- name: `IncrementProcessingOrder`
- size: `426`
- prototype: `__int64 __fastcall(JET_SESID sesid, JET_TABLEID tableid)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1800b82d4`
- `0x1800bd190`

## callees

- `0x1800bc454`
- `0x1800bc990`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800bc4b0`
- `ESENT!JetSetCurrentIndexA` at `0x1800bc4b0`
- `ESENT!JetSetColumns` at `0x1800bc5a0`
- `ESENT!JetSetColumns` at `0x1800bc5a0`
- `ESENT!JetUpdate` at `0x1800bc5d3`
- `ESENT!JetUpdate` at `0x1800bc5d3`
- `ESENT!JetMakeKey` at `0x1800bc4e7`
- `ESENT!JetMakeKey` at `0x1800bc51a`
- `ESENT!JetMakeKey` at `0x1800bc4e7`
- `ESENT!JetMakeKey` at `0x1800bc51a`
- `ESENT!JetSeek` at `0x1800bc546`
- `ESENT!JetSeek` at `0x1800bc546`
- `ESENT!JetPrepareUpdate` at `0x1800bc574`
- `ESENT!JetPrepareUpdate` at `0x1800bc574`

## string_xrefs

- `0x1800bc582`: `AddPolicyEntry:JetPrepareUpdate`
- `0x1800bc5e1`: `AddPolicyEntry:Jetupdate`

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
  *(_QWORD *)&psetcolumn.ibLongValue = 0;
  v14 = a4 + 1;
  psetcolumn.columnid = dword_1800F97E8;
  *(_QWORD *)&psetcolumn.cbData = 4;
  *(&psetcolumn.columnid + 1) = 0;
  *(_QWORD *)&psetcolumn.err = 0;
  psetcolumn.pvData = &v14;
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
0x1800bc454  mov     [rsp-18h+arg_0], rbx
0x1800bc459  mov     [rsp-18h+arg_18], r9d
0x1800bc45e  mov     [rsp-18h+pvData], r8d
0x1800bc463  push    rbp
0x1800bc464  push    rsi
0x1800bc465  push    rdi
0x1800bc466  mov     rbp, rsp
0x1800bc469  sub     rsp, 60h
0x1800bc46d  lea     eax, [r9+1]
0x1800bc471  mov     qword ptr [rbp+psetcolumn.ibLongValue], 0
0x1800bc479  mov     [rbp+var_30], eax
0x1800bc47c  lea     r8, aPolicytableInd_0; "PolicyTable_Index3"
0x1800bc483  mov     eax, cs:dword_1800F97E8
0x1800bc489  mov     ebx, 4
0x1800bc48e  mov     [rbp+psetcolumn.columnid], eax
0x1800bc491  mov     rdi, rdx
0x1800bc494  xor     eax, eax
0x1800bc496  mov     qword ptr [rbp+psetcolumn.cbData], rbx
0x1800bc49a  mov     dword ptr [rbp+psetcolumn+4], eax
0x1800bc49d  mov     rsi, rcx
0x1800bc4a0  lea     rax, [rbp+var_30]
0x1800bc4a4  mov     qword ptr [rbp+psetcolumn.err], 0
0x1800bc4ac  mov     [rbp+psetcolumn.pvData], rax
0x1800bc4b0  call    cs:__imp_JetSetCurrentIndexA
0x1800bc4b7  nop     dword ptr [rax+rax+00h]
0x1800bc4bc  mov     ecx, eax
0x1800bc4be  lea     rdx, aAddpolicyentry_9; "AddPolicyEntry:JetSetCUrrentIndex"
0x1800bc4c5  call    PolicyMapJetError
0x1800bc4ca  test    eax, eax
0x1800bc4cc  jnz     loc_1800BC5ED
0x1800bc4d2  mov     r9d, ebx; cbData
0x1800bc4d5  mov     [rsp+60h+grbit], 1; grbit
0x1800bc4dd  lea     r8, [rbp+pvData]; pvData
0x1800bc4e1  mov     rdx, rdi; tableid
0x1800bc4e4  mov     rcx, rsi; sesid
0x1800bc4e7  call    cs:__imp_JetMakeKey
0x1800bc4ee  nop     dword ptr [rax+rax+00h]
0x1800bc4f3  mov     ecx, eax
0x1800bc4f5  lea     rdx, aAddpolicyentry_3; "AddPolicyEntry:JetMakeKey"
0x1800bc4fc  call    PolicyMapJetError
0x1800bc501  test    eax, eax
0x1800bc503  jnz     loc_1800BC5ED
0x1800bc509  mov     r9d, ebx; cbData
0x1800bc50c  mov     [rsp+60h+grbit], eax; grbit
0x1800bc510  lea     r8, [rbp+arg_18]; pvData
0x1800bc514  mov     rdx, rdi; tableid
0x1800bc517  mov     rcx, rsi; sesid
0x1800bc51a  call    cs:__imp_JetMakeKey
0x1800bc521  nop     dword ptr [rax+rax+00h]
0x1800bc526  mov     ecx, eax
0x1800bc528  lea     rdx, aAddpolicyentry_2; "AddPolicyEntry:JetMakeKey2"
0x1800bc52f  call    PolicyMapJetError
0x1800bc534  test    eax, eax
0x1800bc536  jnz     loc_1800BC5ED
0x1800bc53c  lea     r8d, [rbx-3]; grbit
0x1800bc540  mov     rdx, rdi; tableid
0x1800bc543  mov     rcx, rsi; sesid
0x1800bc546  call    cs:__imp_JetSeek
0x1800bc54d  nop     dword ptr [rax+rax+00h]
0x1800bc552  mov     ecx, eax
0x1800bc554  lea     rdx, aAddpolicyentry_0; "AddPolicyEntry:JetSeek"
0x1800bc55b  mov     ebx, eax
0x1800bc55d  call    PolicyMapJetError
0x1800bc562  test    ebx, ebx
0x1800bc564  jnz     loc_1800BC5ED
0x1800bc56a  lea     r8d, [rbx+2]; prep
0x1800bc56e  mov     rdx, rdi; tableid
0x1800bc571  mov     rcx, rsi; sesid
0x1800bc574  call    cs:__imp_JetPrepareUpdate
0x1800bc57b  nop     dword ptr [rax+rax+00h]
0x1800bc580  mov     ecx, eax
0x1800bc582  lea     rdx, aAddpolicyentry; "AddPolicyEntry:JetPrepareUpdate"
0x1800bc589  call    PolicyMapJetError
0x1800bc58e  test    eax, eax
0x1800bc590  jnz     short loc_1800BC5ED
0x1800bc592  lea     r9d, [rbx+1]; csetcolumn
0x1800bc596  mov     rdx, rdi; tableid
0x1800bc599  lea     r8, [rbp+psetcolumn]; psetcolumn
0x1800bc59d  mov     rcx, rsi; sesid
0x1800bc5a0  call    cs:__imp_JetSetColumns
0x1800bc5a7  nop     dword ptr [rax+rax+00h]
0x1800bc5ac  mov     ecx, eax
0x1800bc5ae  lea     rdx, aAddpolicyentry_8; "AddPolicyEntry:JetSetColumns"
0x1800bc5b5  call    PolicyMapJetError
0x1800bc5ba  test    eax, eax
0x1800bc5bc  jnz     short loc_1800BC5ED
0x1800bc5be  xor     r9d, r9d; cbBookmark
0x1800bc5c1  mov     qword ptr [rsp+60h+grbit], 0; pcbActual
0x1800bc5ca  xor     r8d, r8d; pvBookmark
0x1800bc5cd  mov     rdx, rdi; tableid
0x1800bc5d0  mov     rcx, rsi; sesid
0x1800bc5d3  call    cs:__imp_JetUpdate
0x1800bc5da  nop     dword ptr [rax+rax+00h]
0x1800bc5df  mov     ecx, eax
0x1800bc5e1  lea     rdx, aAddpolicyentry_1; "AddPolicyEntry:Jetupdate"
0x1800bc5e8  call    PolicyMapJetError
0x1800bc5ed  mov     rbx, [rsp+60h+arg_0]
0x1800bc5f5  add     rsp, 60h
0x1800bc5f9  pop     rdi
0x1800bc5fa  pop     rsi
0x1800bc5fb  pop     rbp
0x1800bc5fc  retn
```
