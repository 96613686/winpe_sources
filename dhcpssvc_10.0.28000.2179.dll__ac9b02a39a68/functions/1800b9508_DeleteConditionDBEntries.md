# DeleteConditionDBEntries

- ea: `0x1800b9508`
- end: `0x1800b9766`
- name: `DeleteConditionDBEntries`
- size: `606`
- prototype: `__int64 __fastcall(JET_SESID sesid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1800b976c`

## callees

- `0x1800b9508`
- `0x1800bc990`
- `0x1800bcae8`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800b9534`
- `ESENT!JetSetCurrentIndexA` at `0x1800b9534`
- `ESENT!JetSetColumns` at `0x1800b96c4`
- `ESENT!JetSetColumns` at `0x1800b96c4`
- `ESENT!JetUpdate` at `0x1800b96f7`
- `ESENT!JetUpdate` at `0x1800b96f7`
- `ESENT!JetMakeKey` at `0x1800b9570`
- `ESENT!JetMakeKey` at `0x1800b9570`
- `ESENT!JetSeek` at `0x1800b95a0`
- `ESENT!JetSeek` at `0x1800b95a0`
- `ESENT!JetDelete` at `0x1800b9650`
- `ESENT!JetDelete` at `0x1800b9650`
- `ESENT!JetPrepareUpdate` at `0x1800b966e`
- `ESENT!JetPrepareUpdate` at `0x1800b966e`
- `ESENT!JetRetrieveColumn` at `0x1800b9602`
- `ESENT!JetRetrieveColumn` at `0x1800b9602`
- `ESENT!JetMove` at `0x1800b9726`
- `ESENT!JetMove` at `0x1800b9726`

## string_xrefs

- `0x1800b9610`: `DeleteConditionDBEntries:JetRetrieveColumn`
- `0x1800b95ae`: `DeleteConditionDBEntries:JEtSeek`
- `0x1800b957e`: `DeleteConditionDBEntries:JEtMakeKey`
- `0x1800b9542`: `DeleteConditionDBEntries:JEtSetCUrentIndex`
- `0x1800b9703`: `DeleteConditionDBEntries:JetUPdate`
- `0x1800b96d2`: `DeleteConditionDBEntries:JetSetColumns1`
- `0x1800b967c`: `DeleteConditionDBEntries:JetPrepareUpdate`
- `0x1800b965c`: `DeleteConditionDBEntries:JetDelete`
- `0x1800b9734`: `DeleteConditionDBEntries:JetMove`

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
  JET_SETCOLUMN psetcolumn; // [rsp+48h] [rbp-28h] BYREF
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
          v8 = JetRetrieveColumn(sesid, PolicyConditionTableId, dword_1800F9658, &v17, 4u, 0, 1u, 0);
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
            psetcolumn.columnid = dword_1800F9658;
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
0x1800b9508  mov     [rsp-18h+arg_0], rbx
0x1800b950d  mov     [rsp-18h+pvData], edx
0x1800b9511  push    rbp
0x1800b9512  push    rsi
0x1800b9513  push    rdi
0x1800b9514  mov     rbp, rsp
0x1800b9517  sub     rsp, 70h
0x1800b951b  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800b9522  lea     r8, aPolicyconditio_6; "PolicyConditionTable_Index5"
0x1800b9529  xor     edi, edi
0x1800b952b  mov     rsi, rcx
0x1800b952e  mov     [rbp+arg_10], edi
0x1800b9531  mov     [rbp+arg_18], edi
0x1800b9534  call    cs:__imp_JetSetCurrentIndexA
0x1800b953b  nop     dword ptr [rax+rax+00h]
0x1800b9540  mov     ecx, eax
0x1800b9542  lea     rdx, aDeleteconditio_3; "DeleteConditionDBEntries:JEtSetCUrentIn"...
0x1800b9549  call    PolicyMapJetError
0x1800b954e  test    eax, eax
0x1800b9550  jnz     loc_1800B9755
0x1800b9556  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800b955d  lea     r9d, [rdi+4]; cbData
0x1800b9561  lea     r8, [rbp+pvData]; pvData
0x1800b9565  mov     [rsp+70h+grbit], 1; grbit
0x1800b956d  mov     rcx, rsi; sesid
0x1800b9570  call    cs:__imp_JetMakeKey
0x1800b9577  nop     dword ptr [rax+rax+00h]
0x1800b957c  mov     ecx, eax
0x1800b957e  lea     rdx, aDeleteconditio; "DeleteConditionDBEntries:JEtMakeKey"
0x1800b9585  call    PolicyMapJetError
0x1800b958a  test    eax, eax
0x1800b958c  jnz     loc_1800B9755
0x1800b9592  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800b9599  lea     r8d, [rdi+21h]; grbit
0x1800b959d  mov     rcx, rsi; sesid
0x1800b95a0  call    cs:__imp_JetSeek
0x1800b95a7  nop     dword ptr [rax+rax+00h]
0x1800b95ac  mov     ecx, eax
0x1800b95ae  lea     rdx, aDeleteconditio_0; "DeleteConditionDBEntries:JEtSeek"
0x1800b95b5  mov     ebx, eax
0x1800b95b7  call    PolicyMapJetError
0x1800b95bc  cmp     ebx, 0FFFFF9BFh
0x1800b95c2  jnz     short loc_1800B95CB
0x1800b95c4  xor     eax, eax
0x1800b95c6  jmp     loc_1800B9755
0x1800b95cb  test    eax, eax
0x1800b95cd  jnz     loc_1800B9755
0x1800b95d3  mov     r8d, cs:dword_1800F9658; columnid
0x1800b95da  lea     r9, [rbp+arg_10]; pvData
0x1800b95de  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800b95e5  mov     rcx, rsi; sesid
0x1800b95e8  mov     [rsp+70h+pretinfo], rdi; pretinfo
0x1800b95ed  mov     [rsp+70h+var_40], 1; grbit
0x1800b95f5  mov     [rsp+70h+pcbActual], rdi; pcbActual
0x1800b95fa  mov     [rsp+70h+grbit], 4; cbData
0x1800b9602  call    cs:__imp_JetRetrieveColumn
0x1800b9609  nop     dword ptr [rax+rax+00h]
0x1800b960e  mov     ecx, eax
0x1800b9610  lea     rdx, aDeleteconditio_5; "DeleteConditionDBEntries:JetRetrieveCol"...
0x1800b9617  call    PolicyMapJetError
0x1800b961c  test    eax, eax
0x1800b961e  jnz     loc_1800B9755
0x1800b9624  mov     edx, [rbp+pvData]
0x1800b9627  lea     r8, [rbp+arg_18]
0x1800b962b  mov     rcx, rsi; sesid
0x1800b962e  call    RemoveExprIdFromContainerList
0x1800b9633  test    eax, eax
0x1800b9635  jnz     loc_1800B9755
0x1800b963b  mov     eax, [rbp+arg_10]
0x1800b963e  mov     rcx, rsi; sesid
0x1800b9641  sub     eax, [rbp+arg_18]
0x1800b9644  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800b964b  mov     [rbp+arg_10], eax
0x1800b964e  jnz     short loc_1800B9668
0x1800b9650  call    cs:__imp_JetDelete
0x1800b9657  nop     dword ptr [rax+rax+00h]
0x1800b965c  lea     rdx, aDeleteconditio_1; "DeleteConditionDBEntries:JetDelete"
0x1800b9663  jmp     loc_1800B970A
0x1800b9668  mov     r8d, 2; prep
0x1800b966e  call    cs:__imp_JetPrepareUpdate
0x1800b9675  nop     dword ptr [rax+rax+00h]
0x1800b967a  mov     ecx, eax
0x1800b967c  lea     rdx, aDeleteconditio_2; "DeleteConditionDBEntries:JetPrepareUpda"...
0x1800b9683  call    PolicyMapJetError
0x1800b9688  test    eax, eax
0x1800b968a  jnz     loc_1800B9755
0x1800b9690  mov     eax, cs:dword_1800F9658
0x1800b9696  lea     r8, [rbp+psetcolumn]; psetcolumn
0x1800b969a  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800b96a1  mov     r9d, 1; csetcolumn
0x1800b96a7  mov     [rbp+psetcolumn.columnid], eax
0x1800b96aa  mov     rcx, rsi; sesid
0x1800b96ad  lea     rax, [rbp+arg_10]
0x1800b96b1  mov     qword ptr [rbp+psetcolumn.itagSequence], rdi
0x1800b96b5  mov     [rbp+psetcolumn.pvData], rax
0x1800b96b9  mov     qword ptr [rbp+psetcolumn.grbit], rdi
0x1800b96bd  mov     [rbp+psetcolumn.cbData], 4
0x1800b96c4  call    cs:__imp_JetSetColumns
0x1800b96cb  nop     dword ptr [rax+rax+00h]
0x1800b96d0  mov     ecx, eax
0x1800b96d2  lea     rdx, aDeleteconditio_6; "DeleteConditionDBEntries:JetSetColumns1"
0x1800b96d9  call    PolicyMapJetError
0x1800b96de  test    eax, eax
0x1800b96e0  jnz     short loc_1800B9755
0x1800b96e2  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800b96e9  xor     r9d, r9d; cbBookmark
0x1800b96ec  xor     r8d, r8d; pvBookmark
0x1800b96ef  mov     qword ptr [rsp+70h+grbit], rdi; pcbActual
0x1800b96f4  mov     rcx, rsi; sesid
0x1800b96f7  call    cs:__imp_JetUpdate
0x1800b96fe  nop     dword ptr [rax+rax+00h]
0x1800b9703  lea     rdx, aDeleteconditio_7; "DeleteConditionDBEntries:JetUPdate"
0x1800b970a  mov     ecx, eax
0x1800b970c  call    PolicyMapJetError
0x1800b9711  test    eax, eax
0x1800b9713  jnz     short loc_1800B9755
0x1800b9715  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800b971c  lea     r8d, [rax+1]; cRow
0x1800b9720  xor     r9d, r9d; grbit
0x1800b9723  mov     rcx, rsi; sesid
0x1800b9726  call    cs:__imp_JetMove
0x1800b972d  nop     dword ptr [rax+rax+00h]
0x1800b9732  mov     ecx, eax
0x1800b9734  lea     rdx, aDeleteconditio_4; "DeleteConditionDBEntries:JetMove"
0x1800b973b  mov     ebx, eax
0x1800b973d  call    PolicyMapJetError
0x1800b9742  test    eax, eax
0x1800b9744  jz      loc_1800B95D3
0x1800b974a  cmp     ebx, 0FFFFF9BDh
0x1800b9750  cmovnz  edi, eax
0x1800b9753  mov     eax, edi
0x1800b9755  mov     rbx, [rsp+70h+arg_0]
0x1800b975d  add     rsp, 70h
0x1800b9761  pop     rdi
0x1800b9762  pop     rsi
0x1800b9763  pop     rbp
0x1800b9764  retn
```
