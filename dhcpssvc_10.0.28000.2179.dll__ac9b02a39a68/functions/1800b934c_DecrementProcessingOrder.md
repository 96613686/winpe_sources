# DecrementProcessingOrder

- ea: `0x1800b934c`
- end: `0x1800b9501`
- name: `DecrementProcessingOrder`
- size: `437`
- prototype: `__int64 __fastcall(JET_SESID sesid)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1800b9904`
- `0x1800bd190`

## callees

- `0x1800b934c`
- `0x1800bc990`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800b93b3`
- `ESENT!JetSetCurrentIndexA` at `0x1800b93b3`
- `ESENT!JetSetColumns` at `0x1800b94a3`
- `ESENT!JetSetColumns` at `0x1800b94a3`
- `ESENT!JetUpdate` at `0x1800b94d6`
- `ESENT!JetUpdate` at `0x1800b94d6`
- `ESENT!JetMakeKey` at `0x1800b93ea`
- `ESENT!JetMakeKey` at `0x1800b941d`
- `ESENT!JetMakeKey` at `0x1800b93ea`
- `ESENT!JetMakeKey` at `0x1800b941d`
- `ESENT!JetSeek` at `0x1800b9449`
- `ESENT!JetSeek` at `0x1800b9449`
- `ESENT!JetPrepareUpdate` at `0x1800b9477`
- `ESENT!JetPrepareUpdate` at `0x1800b9477`

## string_xrefs

- `0x1800b9485`: `AddPolicyEntry:JetPrepareUpdate`
- `0x1800b94e4`: `AddPolicyEntry:Jetupdate`

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
  v15 = a4 - 1;
  psetcolumn.columnid = dword_1800F97E8;
  *(_QWORD *)&psetcolumn.cbData = 4;
  *(&psetcolumn.columnid + 1) = 0;
  *(_QWORD *)&psetcolumn.ibLongValue = 0;
  psetcolumn.pvData = &v15;
  *(_QWORD *)&psetcolumn.err = 0;
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
0x1800b934c  mov     rax, rsp
0x1800b934f  mov     [rax+8], rbx
0x1800b9353  mov     [rax+20h], r9d
0x1800b9357  mov     [rax+18h], r8d
0x1800b935b  mov     [rax+10h], rdx
0x1800b935f  push    rbp
0x1800b9360  push    rsi
0x1800b9361  push    rdi
0x1800b9362  mov     rbp, rsp
0x1800b9365  sub     rsp, 60h
0x1800b9369  mov     rsi, cs:PolicyTableId
0x1800b9370  lea     eax, [r9-1]
0x1800b9374  mov     [rbp+arg_8], eax
0x1800b9377  lea     r8, aPolicytableInd_0; "PolicyTable_Index3"
0x1800b937e  mov     eax, cs:dword_1800F97E8
0x1800b9384  mov     ebx, 4
0x1800b9389  mov     [rbp+psetcolumn.columnid], eax
0x1800b938c  mov     rdx, rsi; tableid
0x1800b938f  xor     eax, eax
0x1800b9391  mov     qword ptr [rbp+psetcolumn.cbData], rbx
0x1800b9395  mov     dword ptr [rbp+psetcolumn+4], eax
0x1800b9398  mov     rdi, rcx
0x1800b939b  lea     rax, [rbp+arg_8]
0x1800b939f  mov     qword ptr [rbp+psetcolumn.ibLongValue], 0
0x1800b93a7  mov     [rbp+psetcolumn.pvData], rax
0x1800b93ab  mov     qword ptr [rbp+psetcolumn.err], 0
0x1800b93b3  call    cs:__imp_JetSetCurrentIndexA
0x1800b93ba  nop     dword ptr [rax+rax+00h]
0x1800b93bf  mov     ecx, eax
0x1800b93c1  lea     rdx, aAddpolicyentry_9; "AddPolicyEntry:JetSetCUrrentIndex"
0x1800b93c8  call    PolicyMapJetError
0x1800b93cd  test    eax, eax
0x1800b93cf  jnz     loc_1800B94F0
0x1800b93d5  mov     r9d, ebx; cbData
0x1800b93d8  mov     [rsp+60h+grbit], 1; grbit
0x1800b93e0  lea     r8, [rbp+pvData]; pvData
0x1800b93e4  mov     rdx, rsi; tableid
0x1800b93e7  mov     rcx, rdi; sesid
0x1800b93ea  call    cs:__imp_JetMakeKey
0x1800b93f1  nop     dword ptr [rax+rax+00h]
0x1800b93f6  mov     ecx, eax
0x1800b93f8  lea     rdx, aAddpolicyentry_3; "AddPolicyEntry:JetMakeKey"
0x1800b93ff  call    PolicyMapJetError
0x1800b9404  test    eax, eax
0x1800b9406  jnz     loc_1800B94F0
0x1800b940c  mov     r9d, ebx; cbData
0x1800b940f  mov     [rsp+60h+grbit], eax; grbit
0x1800b9413  lea     r8, [rbp+arg_18]; pvData
0x1800b9417  mov     rdx, rsi; tableid
0x1800b941a  mov     rcx, rdi; sesid
0x1800b941d  call    cs:__imp_JetMakeKey
0x1800b9424  nop     dword ptr [rax+rax+00h]
0x1800b9429  mov     ecx, eax
0x1800b942b  lea     rdx, aAddpolicyentry_2; "AddPolicyEntry:JetMakeKey2"
0x1800b9432  call    PolicyMapJetError
0x1800b9437  test    eax, eax
0x1800b9439  jnz     loc_1800B94F0
0x1800b943f  lea     r8d, [rbx-3]; grbit
0x1800b9443  mov     rdx, rsi; tableid
0x1800b9446  mov     rcx, rdi; sesid
0x1800b9449  call    cs:__imp_JetSeek
0x1800b9450  nop     dword ptr [rax+rax+00h]
0x1800b9455  mov     ecx, eax
0x1800b9457  lea     rdx, aAddpolicyentry_0; "AddPolicyEntry:JetSeek"
0x1800b945e  mov     ebx, eax
0x1800b9460  call    PolicyMapJetError
0x1800b9465  test    ebx, ebx
0x1800b9467  jnz     loc_1800B94F0
0x1800b946d  lea     r8d, [rbx+2]; prep
0x1800b9471  mov     rdx, rsi; tableid
0x1800b9474  mov     rcx, rdi; sesid
0x1800b9477  call    cs:__imp_JetPrepareUpdate
0x1800b947e  nop     dword ptr [rax+rax+00h]
0x1800b9483  mov     ecx, eax
0x1800b9485  lea     rdx, aAddpolicyentry; "AddPolicyEntry:JetPrepareUpdate"
0x1800b948c  call    PolicyMapJetError
0x1800b9491  test    eax, eax
0x1800b9493  jnz     short loc_1800B94F0
0x1800b9495  lea     r9d, [rbx+1]; csetcolumn
0x1800b9499  mov     rdx, rsi; tableid
0x1800b949c  lea     r8, [rbp+psetcolumn]; psetcolumn
0x1800b94a0  mov     rcx, rdi; sesid
0x1800b94a3  call    cs:__imp_JetSetColumns
0x1800b94aa  nop     dword ptr [rax+rax+00h]
0x1800b94af  mov     ecx, eax
0x1800b94b1  lea     rdx, aAddpolicyentry_8; "AddPolicyEntry:JetSetColumns"
0x1800b94b8  call    PolicyMapJetError
0x1800b94bd  test    eax, eax
0x1800b94bf  jnz     short loc_1800B94F0
0x1800b94c1  xor     r9d, r9d; cbBookmark
0x1800b94c4  mov     qword ptr [rsp+60h+grbit], 0; pcbActual
0x1800b94cd  xor     r8d, r8d; pvBookmark
0x1800b94d0  mov     rdx, rsi; tableid
0x1800b94d3  mov     rcx, rdi; sesid
0x1800b94d6  call    cs:__imp_JetUpdate
0x1800b94dd  nop     dword ptr [rax+rax+00h]
0x1800b94e2  mov     ecx, eax
0x1800b94e4  lea     rdx, aAddpolicyentry_1; "AddPolicyEntry:Jetupdate"
0x1800b94eb  call    PolicyMapJetError
0x1800b94f0  mov     rbx, [rsp+60h+arg_0]
0x1800b94f8  add     rsp, 60h
0x1800b94fc  pop     rdi
0x1800b94fd  pop     rsi
0x1800b94fe  pop     rbp
0x1800b94ff  retn
```
