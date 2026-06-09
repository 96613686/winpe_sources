# DecrementProcessingOrder

- ea: `0x1800b8460`
- end: `0x1800b8616`
- name: `DecrementProcessingOrder`
- size: `438`
- prototype: `__int64 __fastcall(JET_SESID sesid)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1800b8a18`
- `0x1800bc1fc`

## callees

- `0x1800b8460`
- `0x1800bba04`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800b84cb`
- `ESENT!JetSetCurrentIndexA` at `0x1800b84cb`
- `ESENT!JetSetColumns` at `0x1800b85bb`
- `ESENT!JetSetColumns` at `0x1800b85bb`
- `ESENT!JetUpdate` at `0x1800b85eb`
- `ESENT!JetUpdate` at `0x1800b85eb`
- `ESENT!JetMakeKey` at `0x1800b8502`
- `ESENT!JetMakeKey` at `0x1800b8535`
- `ESENT!JetMakeKey` at `0x1800b8502`
- `ESENT!JetMakeKey` at `0x1800b8535`
- `ESENT!JetSeek` at `0x1800b8561`
- `ESENT!JetSeek` at `0x1800b8561`
- `ESENT!JetPrepareUpdate` at `0x1800b858f`
- `ESENT!JetPrepareUpdate` at `0x1800b858f`

## string_xrefs

- `0x1800b85f9`: `AddPolicyEntry:Jetupdate`
- `0x1800b859d`: `AddPolicyEntry:JetPrepareUpdate`

## pseudocode

```c
__int64 __fastcall DecrementProcessingOrder(JET_SESID sesid, __int64 a2, int a3, int a4)
{
  JET_TABLEID v4; // rsi
  unsigned int v6; // eax
  __int64 result; // rax
  unsigned int Key; // eax
  unsigned int v9; // eax
  unsigned int v10; // ebx
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  JET_SETCOLUMN psetcolumn; // [rsp+30h] [rbp-30h] BYREF
  int v15; // [rsp+88h] [rbp+28h] BYREF
  int v16; // [rsp+8Ch] [rbp+2Ch]
  int pvData; // [rsp+90h] [rbp+30h] BYREF
  int v18; // [rsp+98h] [rbp+38h] BYREF

  v18 = a4;
  pvData = a3;
  v16 = HIDWORD(a2);
  v4 = PolicyTableId;
  memset(&psetcolumn.grbit, 0, 20);
  v15 = a4 - 1;
  psetcolumn.columnid = dword_1800F7618;
  *(&psetcolumn.columnid + 1) = 0;
  psetcolumn.pvData = &v15;
  psetcolumn.cbData = 4;
  v6 = JetSetCurrentIndexA(sesid, PolicyTableId, "PolicyTable_Index3");
  result = PolicyMapJetError(v6, "AddPolicyEntry:JetSetCUrrentIndex");
  if ( !(_DWORD)result )
  {
    Key = JetMakeKey(sesid, v4, &pvData, 4u, 1u);
    result = PolicyMapJetError(Key, "AddPolicyEntry:JetMakeKey");
    if ( !(_DWORD)result )
    {
      v9 = JetMakeKey(sesid, v4, &v18, 4u, 0);
      result = PolicyMapJetError(v9, "AddPolicyEntry:JetMakeKey2");
      if ( !(_DWORD)result )
      {
        v10 = JetSeek(sesid, v4, 1u);
        result = PolicyMapJetError(v10, "AddPolicyEntry:JetSeek");
        if ( !v10 )
        {
          v11 = JetPrepareUpdate(sesid, v4, 2u);
          result = PolicyMapJetError(v11, "AddPolicyEntry:JetPrepareUpdate");
          if ( !(_DWORD)result )
          {
            v12 = JetSetColumns(sesid, v4, &psetcolumn, 1u);
            result = PolicyMapJetError(v12, "AddPolicyEntry:JetSetColumns");
            if ( !(_DWORD)result )
            {
              v13 = JetUpdate(sesid, v4, 0, 0, 0);
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
0x1800b8460  mov     rax, rsp
0x1800b8463  mov     [rax+8], rbx
0x1800b8467  mov     [rax+20h], r9d
0x1800b846b  mov     [rax+18h], r8d
0x1800b846f  mov     [rax+10h], rdx
0x1800b8473  push    rbp
0x1800b8474  push    rsi
0x1800b8475  push    rdi
0x1800b8476  mov     rbp, rsp
0x1800b8479  sub     rsp, 60h
0x1800b847d  mov     rsi, cs:PolicyTableId
0x1800b8484  lea     eax, [r9-1]
0x1800b8488  and     [rbp+psetcolumn.grbit], 0
0x1800b848c  lea     r8, aPolicytableInd_0; "PolicyTable_Index3"
0x1800b8493  and     [rbp+psetcolumn.ibLongValue], 0
0x1800b8497  mov     ebx, 4
0x1800b849c  and     [rbp+psetcolumn.itagSequence], 0
0x1800b84a0  mov     rdx, rsi; tableid
0x1800b84a3  and     [rbp+psetcolumn.err], 0
0x1800b84a7  mov     rdi, rcx
0x1800b84aa  mov     [rbp+arg_8], eax
0x1800b84ad  mov     eax, cs:dword_1800F7618
0x1800b84b3  mov     [rbp+psetcolumn.columnid], eax
0x1800b84b6  xor     eax, eax
0x1800b84b8  mov     dword ptr [rbp+psetcolumn+4], eax
0x1800b84bb  lea     rax, [rbp+arg_8]
0x1800b84bf  mov     [rbp+psetcolumn.pvData], rax
0x1800b84c3  xor     eax, eax
0x1800b84c5  mov     dword ptr [rbp+psetcolumn+24h], eax
0x1800b84c8  mov     [rbp+psetcolumn.cbData], ebx
0x1800b84cb  call    cs:__imp_JetSetCurrentIndexA
0x1800b84d2  nop     dword ptr [rax+rax+00h]
0x1800b84d7  mov     ecx, eax
0x1800b84d9  lea     rdx, aAddpolicyentry_9; "AddPolicyEntry:JetSetCUrrentIndex"
0x1800b84e0  call    PolicyMapJetError
0x1800b84e5  test    eax, eax
0x1800b84e7  jnz     loc_1800B8605
0x1800b84ed  mov     r9d, ebx; cbData
0x1800b84f0  mov     [rsp+60h+grbit], 1; pcbActual
0x1800b84f8  lea     r8, [rbp+pvData]; pvData
0x1800b84fc  mov     rdx, rsi; tableid
0x1800b84ff  mov     rcx, rdi; sesid
0x1800b8502  call    cs:__imp_JetMakeKey
0x1800b8509  nop     dword ptr [rax+rax+00h]
0x1800b850e  mov     ecx, eax
0x1800b8510  lea     rdx, aAddpolicyentry_3; "AddPolicyEntry:JetMakeKey"
0x1800b8517  call    PolicyMapJetError
0x1800b851c  test    eax, eax
0x1800b851e  jnz     loc_1800B8605
0x1800b8524  and     [rsp+60h+grbit], eax
0x1800b8528  lea     r8, [rbp+arg_18]; pvData
0x1800b852c  mov     r9d, ebx; cbData
0x1800b852f  mov     rdx, rsi; tableid
0x1800b8532  mov     rcx, rdi; sesid
0x1800b8535  call    cs:__imp_JetMakeKey
0x1800b853c  nop     dword ptr [rax+rax+00h]
0x1800b8541  mov     ecx, eax
0x1800b8543  lea     rdx, aAddpolicyentry_2; "AddPolicyEntry:JetMakeKey2"
0x1800b854a  call    PolicyMapJetError
0x1800b854f  test    eax, eax
0x1800b8551  jnz     loc_1800B8605
0x1800b8557  lea     r8d, [rbx-3]; grbit
0x1800b855b  mov     rdx, rsi; tableid
0x1800b855e  mov     rcx, rdi; sesid
0x1800b8561  call    cs:__imp_JetSeek
0x1800b8568  nop     dword ptr [rax+rax+00h]
0x1800b856d  mov     ecx, eax
0x1800b856f  lea     rdx, aAddpolicyentry_0; "AddPolicyEntry:JetSeek"
0x1800b8576  mov     ebx, eax
0x1800b8578  call    PolicyMapJetError
0x1800b857d  test    ebx, ebx
0x1800b857f  jnz     loc_1800B8605
0x1800b8585  lea     r8d, [rbx+2]; prep
0x1800b8589  mov     rdx, rsi; tableid
0x1800b858c  mov     rcx, rdi; sesid
0x1800b858f  call    cs:__imp_JetPrepareUpdate
0x1800b8596  nop     dword ptr [rax+rax+00h]
0x1800b859b  mov     ecx, eax
0x1800b859d  lea     rdx, aAddpolicyentry; "AddPolicyEntry:JetPrepareUpdate"
0x1800b85a4  call    PolicyMapJetError
0x1800b85a9  test    eax, eax
0x1800b85ab  jnz     short loc_1800B8605
0x1800b85ad  lea     r9d, [rbx+1]; csetcolumn
0x1800b85b1  mov     rdx, rsi; tableid
0x1800b85b4  lea     r8, [rbp+psetcolumn]; psetcolumn
0x1800b85b8  mov     rcx, rdi; sesid
0x1800b85bb  call    cs:__imp_JetSetColumns
0x1800b85c2  nop     dword ptr [rax+rax+00h]
0x1800b85c7  mov     ecx, eax
0x1800b85c9  lea     rdx, aAddpolicyentry_8; "AddPolicyEntry:JetSetColumns"
0x1800b85d0  call    PolicyMapJetError
0x1800b85d5  test    eax, eax
0x1800b85d7  jnz     short loc_1800B8605
0x1800b85d9  and     qword ptr [rsp+60h+grbit], 0
0x1800b85df  xor     r9d, r9d; cbBookmark
0x1800b85e2  xor     r8d, r8d; pvBookmark
0x1800b85e5  mov     rdx, rsi; tableid
0x1800b85e8  mov     rcx, rdi; sesid
0x1800b85eb  call    cs:__imp_JetUpdate
0x1800b85f2  nop     dword ptr [rax+rax+00h]
0x1800b85f7  mov     ecx, eax
0x1800b85f9  lea     rdx, aAddpolicyentry_1; "AddPolicyEntry:Jetupdate"
0x1800b8600  call    PolicyMapJetError
0x1800b8605  mov     rbx, [rsp+60h+arg_0]
0x1800b860d  add     rsp, 60h
0x1800b8611  pop     rdi
0x1800b8612  pop     rsi
0x1800b8613  pop     rbp
0x1800b8614  retn
```
