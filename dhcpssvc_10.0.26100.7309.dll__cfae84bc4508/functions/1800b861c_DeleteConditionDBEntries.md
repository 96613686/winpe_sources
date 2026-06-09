# DeleteConditionDBEntries

- ea: `0x1800b861c`
- end: `0x1800b8877`
- name: `DeleteConditionDBEntries`
- size: `603`
- prototype: `__int64 __fastcall(JET_SESID sesid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1800b8880`

## callees

- `0x1800b861c`
- `0x1800bba04`
- `0x1800bbb5c`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800b8648`
- `ESENT!JetSetCurrentIndexA` at `0x1800b8648`
- `ESENT!JetSetColumns` at `0x1800b87d5`
- `ESENT!JetSetColumns` at `0x1800b87d5`
- `ESENT!JetUpdate` at `0x1800b8808`
- `ESENT!JetUpdate` at `0x1800b8808`
- `ESENT!JetMakeKey` at `0x1800b8684`
- `ESENT!JetMakeKey` at `0x1800b8684`
- `ESENT!JetSeek` at `0x1800b86b4`
- `ESENT!JetSeek` at `0x1800b86b4`
- `ESENT!JetDelete` at `0x1800b8761`
- `ESENT!JetDelete` at `0x1800b8761`
- `ESENT!JetPrepareUpdate` at `0x1800b877f`
- `ESENT!JetPrepareUpdate` at `0x1800b877f`
- `ESENT!JetRetrieveColumn` at `0x1800b8716`
- `ESENT!JetRetrieveColumn` at `0x1800b8716`
- `ESENT!JetMove` at `0x1800b8837`
- `ESENT!JetMove` at `0x1800b8837`

## string_xrefs

- `0x1800b8656`: `DeleteConditionDBEntries:JEtSetCUrentIndex`
- `0x1800b8692`: `DeleteConditionDBEntries:JEtMakeKey`
- `0x1800b876d`: `DeleteConditionDBEntries:JetDelete`
- `0x1800b878d`: `DeleteConditionDBEntries:JetPrepareUpdate`
- `0x1800b86c2`: `DeleteConditionDBEntries:JEtSeek`
- `0x1800b8724`: `DeleteConditionDBEntries:JetRetrieveColumn`
- `0x1800b8845`: `DeleteConditionDBEntries:JetMove`
- `0x1800b87e3`: `DeleteConditionDBEntries:JetSetColumns1`
- `0x1800b8814`: `DeleteConditionDBEntries:JetUPdate`

## pseudocode

```c
__int64 __fastcall DeleteConditionDBEntries(JET_SESID sesid, int a2)
{
  unsigned int v2; // edi
  unsigned int v4; // eax
  __int64 result; // rax
  unsigned int Key; // eax
  unsigned int v7; // ebx
  unsigned int v8; // eax
  unsigned int v9; // eax
  const char *v10; // rdx
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // ebx
  unsigned int v14; // eax
  JET_SETCOLUMN psetcolumn; // [rsp+40h] [rbp-30h] BYREF
  int pvData; // [rsp+98h] [rbp+28h] BYREF
  int v17; // [rsp+A0h] [rbp+30h] BYREF
  int v18; // [rsp+A8h] [rbp+38h]

  pvData = a2;
  v2 = 0;
  v17 = 0;
  v18 = 0;
  v4 = JetSetCurrentIndexA(sesid, PolicyConditionTableId, "PolicyConditionTable_Index5");
  result = PolicyMapJetError(v4, "DeleteConditionDBEntries:JEtSetCUrentIndex");
  if ( !(_DWORD)result )
  {
    Key = JetMakeKey(sesid, PolicyConditionTableId, &pvData, 4u, 1u);
    result = PolicyMapJetError(Key, "DeleteConditionDBEntries:JEtMakeKey");
    if ( !(_DWORD)result )
    {
      v7 = JetSeek(sesid, PolicyConditionTableId, 0x21u);
      result = PolicyMapJetError(v7, "DeleteConditionDBEntries:JEtSeek");
      if ( v7 == -1601 )
      {
        return 0;
      }
      else if ( !(_DWORD)result )
      {
        while ( 1 )
        {
          v8 = JetRetrieveColumn(sesid, PolicyConditionTableId, dword_1800F7848, &v17, 4u, 0, 1u, 0);
          result = PolicyMapJetError(v8, "DeleteConditionDBEntries:JetRetrieveColumn");
          if ( (_DWORD)result )
            break;
          result = RemoveExprIdFromContainerList(sesid);
          if ( (_DWORD)result )
            break;
          v17 -= v18;
          if ( v17 )
          {
            v11 = JetPrepareUpdate(sesid, PolicyConditionTableId, 2u);
            result = PolicyMapJetError(v11, "DeleteConditionDBEntries:JetPrepareUpdate");
            if ( (_DWORD)result )
              return result;
            psetcolumn.columnid = dword_1800F7848;
            *(_QWORD *)&psetcolumn.itagSequence = 0;
            psetcolumn.pvData = &v17;
            *(_QWORD *)&psetcolumn.grbit = 0;
            psetcolumn.cbData = 4;
            v12 = JetSetColumns(sesid, PolicyConditionTableId, &psetcolumn, 1u);
            result = PolicyMapJetError(v12, "DeleteConditionDBEntries:JetSetColumns1");
            if ( (_DWORD)result )
              return result;
            v9 = JetUpdate(sesid, PolicyConditionTableId, 0, 0, 0);
            v10 = "DeleteConditionDBEntries:JetUPdate";
          }
          else
          {
            v9 = JetDelete(sesid, PolicyConditionTableId);
            v10 = "DeleteConditionDBEntries:JetDelete";
          }
          result = PolicyMapJetError(v9, v10);
          if ( (_DWORD)result )
            return result;
          v13 = JetMove(sesid, PolicyConditionTableId, 1, 0);
          v14 = PolicyMapJetError(v13, "DeleteConditionDBEntries:JetMove");
          if ( v14 )
          {
            if ( v13 != -1603 )
              return v14;
            return v2;
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
0x1800b861c  mov     [rsp-18h+arg_0], rbx
0x1800b8621  mov     [rsp-18h+pvData], edx
0x1800b8625  push    rbp
0x1800b8626  push    rsi
0x1800b8627  push    rdi
0x1800b8628  mov     rbp, rsp
0x1800b862b  sub     rsp, 70h
0x1800b862f  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800b8636  lea     r8, aPolicyconditio_6; "PolicyConditionTable_Index5"
0x1800b863d  xor     edi, edi
0x1800b863f  mov     rsi, rcx
0x1800b8642  mov     [rbp+arg_10], edi
0x1800b8645  mov     [rbp+arg_18], edi
0x1800b8648  call    cs:__imp_JetSetCurrentIndexA
0x1800b864f  nop     dword ptr [rax+rax+00h]
0x1800b8654  mov     ecx, eax
0x1800b8656  lea     rdx, aDeleteconditio_3; "DeleteConditionDBEntries:JEtSetCUrentIn"...
0x1800b865d  call    PolicyMapJetError
0x1800b8662  test    eax, eax
0x1800b8664  jnz     loc_1800B8866
0x1800b866a  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800b8671  lea     r9d, [rdi+4]; cbData
0x1800b8675  lea     r8, [rbp+pvData]; pvData
0x1800b8679  mov     [rsp+70h+grbit], 1; grbit
0x1800b8681  mov     rcx, rsi; sesid
0x1800b8684  call    cs:__imp_JetMakeKey
0x1800b868b  nop     dword ptr [rax+rax+00h]
0x1800b8690  mov     ecx, eax
0x1800b8692  lea     rdx, aDeleteconditio; "DeleteConditionDBEntries:JEtMakeKey"
0x1800b8699  call    PolicyMapJetError
0x1800b869e  test    eax, eax
0x1800b86a0  jnz     loc_1800B8866
0x1800b86a6  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800b86ad  lea     r8d, [rdi+21h]; grbit
0x1800b86b1  mov     rcx, rsi; sesid
0x1800b86b4  call    cs:__imp_JetSeek
0x1800b86bb  nop     dword ptr [rax+rax+00h]
0x1800b86c0  mov     ecx, eax
0x1800b86c2  lea     rdx, aDeleteconditio_0; "DeleteConditionDBEntries:JEtSeek"
0x1800b86c9  mov     ebx, eax
0x1800b86cb  call    PolicyMapJetError
0x1800b86d0  cmp     ebx, 0FFFFF9BFh
0x1800b86d6  jnz     short loc_1800B86DF
0x1800b86d8  xor     eax, eax
0x1800b86da  jmp     loc_1800B8866
0x1800b86df  test    eax, eax
0x1800b86e1  jnz     loc_1800B8866
0x1800b86e7  mov     r8d, cs:dword_1800F7848; columnid
0x1800b86ee  lea     r9, [rbp+arg_10]; pvData
0x1800b86f2  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800b86f9  mov     rcx, rsi; sesid
0x1800b86fc  mov     [rsp+70h+pretinfo], rdi; pretinfo
0x1800b8701  mov     [rsp+70h+var_40], 1; grbit
0x1800b8709  mov     [rsp+70h+pcbActual], rdi; pcbActual
0x1800b870e  mov     [rsp+70h+grbit], 4; cbData
0x1800b8716  call    cs:__imp_JetRetrieveColumn
0x1800b871d  nop     dword ptr [rax+rax+00h]
0x1800b8722  mov     ecx, eax
0x1800b8724  lea     rdx, aDeleteconditio_5; "DeleteConditionDBEntries:JetRetrieveCol"...
0x1800b872b  call    PolicyMapJetError
0x1800b8730  test    eax, eax
0x1800b8732  jnz     loc_1800B8866
0x1800b8738  mov     edx, [rbp+pvData]
0x1800b873b  lea     r8, [rbp+arg_18]
0x1800b873f  mov     rcx, rsi; sesid
0x1800b8742  call    RemoveExprIdFromContainerList
0x1800b8747  test    eax, eax
0x1800b8749  jnz     loc_1800B8866
0x1800b874f  mov     eax, [rbp+arg_18]
0x1800b8752  mov     rcx, rsi; sesid
0x1800b8755  sub     [rbp+arg_10], eax
0x1800b8758  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800b875f  jnz     short loc_1800B8779
0x1800b8761  call    cs:__imp_JetDelete
0x1800b8768  nop     dword ptr [rax+rax+00h]
0x1800b876d  lea     rdx, aDeleteconditio_1; "DeleteConditionDBEntries:JetDelete"
0x1800b8774  jmp     loc_1800B881B
0x1800b8779  mov     r8d, 2; prep
0x1800b877f  call    cs:__imp_JetPrepareUpdate
0x1800b8786  nop     dword ptr [rax+rax+00h]
0x1800b878b  mov     ecx, eax
0x1800b878d  lea     rdx, aDeleteconditio_2; "DeleteConditionDBEntries:JetPrepareUpda"...
0x1800b8794  call    PolicyMapJetError
0x1800b8799  test    eax, eax
0x1800b879b  jnz     loc_1800B8866
0x1800b87a1  mov     eax, cs:dword_1800F7848
0x1800b87a7  lea     r8, [rbp+psetcolumn]; psetcolumn
0x1800b87ab  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800b87b2  mov     r9d, 1; csetcolumn
0x1800b87b8  mov     [rbp+psetcolumn.columnid], eax
0x1800b87bb  mov     rcx, rsi; sesid
0x1800b87be  lea     rax, [rbp+arg_10]
0x1800b87c2  mov     qword ptr [rbp+psetcolumn.itagSequence], rdi
0x1800b87c6  mov     [rbp+psetcolumn.pvData], rax
0x1800b87ca  mov     qword ptr [rbp+psetcolumn.grbit], rdi
0x1800b87ce  mov     [rbp+psetcolumn.cbData], 4
0x1800b87d5  call    cs:__imp_JetSetColumns
0x1800b87dc  nop     dword ptr [rax+rax+00h]
0x1800b87e1  mov     ecx, eax
0x1800b87e3  lea     rdx, aDeleteconditio_6; "DeleteConditionDBEntries:JetSetColumns1"
0x1800b87ea  call    PolicyMapJetError
0x1800b87ef  test    eax, eax
0x1800b87f1  jnz     short loc_1800B8866
0x1800b87f3  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800b87fa  xor     r9d, r9d; cbBookmark
0x1800b87fd  xor     r8d, r8d; pvBookmark
0x1800b8800  mov     qword ptr [rsp+70h+grbit], rdi; pcbActual
0x1800b8805  mov     rcx, rsi; sesid
0x1800b8808  call    cs:__imp_JetUpdate
0x1800b880f  nop     dword ptr [rax+rax+00h]
0x1800b8814  lea     rdx, aDeleteconditio_7; "DeleteConditionDBEntries:JetUPdate"
0x1800b881b  mov     ecx, eax
0x1800b881d  call    PolicyMapJetError
0x1800b8822  test    eax, eax
0x1800b8824  jnz     short loc_1800B8866
0x1800b8826  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800b882d  lea     r8d, [rax+1]; cRow
0x1800b8831  xor     r9d, r9d; grbit
0x1800b8834  mov     rcx, rsi; sesid
0x1800b8837  call    cs:__imp_JetMove
0x1800b883e  nop     dword ptr [rax+rax+00h]
0x1800b8843  mov     ecx, eax
0x1800b8845  lea     rdx, aDeleteconditio_4; "DeleteConditionDBEntries:JetMove"
0x1800b884c  mov     ebx, eax
0x1800b884e  call    PolicyMapJetError
0x1800b8853  test    eax, eax
0x1800b8855  jz      loc_1800B86E7
0x1800b885b  cmp     ebx, 0FFFFF9BDh
0x1800b8861  cmovnz  edi, eax
0x1800b8864  mov     eax, edi
0x1800b8866  mov     rbx, [rsp+70h+arg_0]
0x1800b886e  add     rsp, 70h
0x1800b8872  pop     rdi
0x1800b8873  pop     rsi
0x1800b8874  pop     rbp
0x1800b8875  retn
```
