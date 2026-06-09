# DeleteExpressionDBEntries

- ea: `0x1800b976c`
- end: `0x1800b98fb`
- name: `DeleteExpressionDBEntries`
- size: `399`
- prototype: `__int64 __fastcall(JET_SESID sesid)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180088260`
- `0x1800bd190`

## callees

- `0x1800b9508`
- `0x1800b976c`
- `0x1800bc990`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800b9795`
- `ESENT!JetSetCurrentIndexA` at `0x1800b9795`
- `ESENT!JetMakeKey` at `0x1800b97d2`
- `ESENT!JetMakeKey` at `0x1800b97d2`
- `ESENT!JetSeek` at `0x1800b9802`
- `ESENT!JetSeek` at `0x1800b9802`
- `ESENT!JetDelete` at `0x1800b988c`
- `ESENT!JetDelete` at `0x1800b988c`
- `ESENT!JetRetrieveColumn` at `0x1800b9854`
- `ESENT!JetRetrieveColumn` at `0x1800b9854`
- `ESENT!JetMove` at `0x1800b98bb`
- `ESENT!JetMove` at `0x1800b98bb`

## string_xrefs

- `0x1800b9862`: `DeletePolicyDBentry:JetRetrieveColumn`
- `0x1800b989a`: `DeleteExpressionDBEntries:JetMove`
- `0x1800b98c9`: `DeleteExpressionDBEntries:JetMove`
- `0x1800b9810`: `DeleteExpressionDBEntries:JEtSeek`
- `0x1800b97e0`: `DeleteExpressionDBEntries:JEtMakeKey`
- `0x1800b97a3`: `DeleteExpressionDBEntries:JEtSetCUrentIndex`

## pseudocode

```c
__int64 __fastcall DeleteExpressionDBEntries(JET_SESID sesid, int a2)
{
  unsigned int v2; // ebx
  unsigned int v4; // eax
  __int64 result; // rax
  unsigned int Key; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // esi
  unsigned int v11; // eax
  int pvData; // [rsp+58h] [rbp+10h] BYREF
  int v13; // [rsp+60h] [rbp+18h] BYREF

  pvData = a2;
  v2 = 0;
  v13 = 0;
  v4 = JetSetCurrentIndexA(sesid, PolicyExpressionTableId, "PolicyExpressionTable_Index3");
  result = PolicyMapJetError(v4, "DeleteExpressionDBEntries:JEtSetCUrentIndex");
  if ( !(_DWORD)result )
  {
    Key = JetMakeKey(sesid, PolicyExpressionTableId, &pvData, 4u, 1u);
    result = PolicyMapJetError(Key, "DeleteExpressionDBEntries:JEtMakeKey");
    if ( !(_DWORD)result )
    {
      v7 = JetSeek(sesid, PolicyExpressionTableId, 0x21u);
      result = PolicyMapJetError(v7, "DeleteExpressionDBEntries:JEtSeek");
      if ( !(_DWORD)result )
      {
        while ( 1 )
        {
          v8 = JetRetrieveColumn(sesid, PolicyExpressionTableId, dword_1800F9688, &v13, 4u, 0, 1u, 0);
          result = PolicyMapJetError(v8, "DeletePolicyDBentry:JetRetrieveColumn");
          if ( (_DWORD)result )
            break;
          result = DeleteConditionDBEntries(sesid, v13);
          if ( (_DWORD)result )
            break;
          v9 = JetDelete(sesid, PolicyExpressionTableId);
          result = PolicyMapJetError(v9, "DeleteExpressionDBEntries:JetMove");
          if ( (_DWORD)result )
            break;
          v10 = JetMove(sesid, PolicyExpressionTableId, 1, 0);
          v11 = PolicyMapJetError(v10, "DeleteExpressionDBEntries:JetMove");
          if ( v11 )
          {
            if ( v10 != -1603 )
              return v11;
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
0x1800b976c  mov     rax, rsp
0x1800b976f  mov     [rax+8], rbx
0x1800b9773  mov     [rax+20h], rsi
0x1800b9777  mov     [rax+10h], edx
0x1800b977a  push    rdi
0x1800b977b  sub     rsp, 40h
0x1800b977f  mov     rdx, cs:PolicyExpressionTableId; tableid
0x1800b9786  lea     r8, aPolicyexpressi_2; "PolicyExpressionTable_Index3"
0x1800b978d  xor     ebx, ebx
0x1800b978f  mov     rdi, rcx
0x1800b9792  mov     [rax+18h], ebx
0x1800b9795  call    cs:__imp_JetSetCurrentIndexA
0x1800b979c  nop     dword ptr [rax+rax+00h]
0x1800b97a1  mov     ecx, eax
0x1800b97a3  lea     rdx, aDeleteexpressi; "DeleteExpressionDBEntries:JEtSetCUrentI"...
0x1800b97aa  call    PolicyMapJetError
0x1800b97af  test    eax, eax
0x1800b97b1  jnz     loc_1800B98EA
0x1800b97b7  mov     rdx, cs:PolicyExpressionTableId; tableid
0x1800b97be  lea     r9d, [rbx+4]; cbData
0x1800b97c2  lea     r8, [rsp+48h+pvData]; pvData
0x1800b97c7  mov     [rsp+48h+grbit], 1; grbit
0x1800b97cf  mov     rcx, rdi; sesid
0x1800b97d2  call    cs:__imp_JetMakeKey
0x1800b97d9  nop     dword ptr [rax+rax+00h]
0x1800b97de  mov     ecx, eax
0x1800b97e0  lea     rdx, aDeleteexpressi_0; "DeleteExpressionDBEntries:JEtMakeKey"
0x1800b97e7  call    PolicyMapJetError
0x1800b97ec  test    eax, eax
0x1800b97ee  jnz     loc_1800B98EA
0x1800b97f4  mov     rdx, cs:PolicyExpressionTableId; tableid
0x1800b97fb  lea     r8d, [rbx+21h]; grbit
0x1800b97ff  mov     rcx, rdi; sesid
0x1800b9802  call    cs:__imp_JetSeek
0x1800b9809  nop     dword ptr [rax+rax+00h]
0x1800b980e  mov     ecx, eax
0x1800b9810  lea     rdx, aDeleteexpressi_2; "DeleteExpressionDBEntries:JEtSeek"
0x1800b9817  call    PolicyMapJetError
0x1800b981c  test    eax, eax
0x1800b981e  jnz     loc_1800B98EA
0x1800b9824  mov     r8d, cs:dword_1800F9688; columnid
0x1800b982b  lea     r9, [rsp+48h+arg_10]; pvData
0x1800b9830  mov     rdx, cs:PolicyExpressionTableId; tableid
0x1800b9837  mov     rcx, rdi; sesid
0x1800b983a  mov     [rsp+48h+pretinfo], rbx; pretinfo
0x1800b983f  mov     [rsp+48h+var_18], 1; grbit
0x1800b9847  mov     [rsp+48h+pcbActual], rbx; pcbActual
0x1800b984c  mov     [rsp+48h+grbit], 4; cbData
0x1800b9854  call    cs:__imp_JetRetrieveColumn
0x1800b985b  nop     dword ptr [rax+rax+00h]
0x1800b9860  mov     ecx, eax
0x1800b9862  lea     rdx, aDeletepolicydb; "DeletePolicyDBentry:JetRetrieveColumn"
0x1800b9869  call    PolicyMapJetError
0x1800b986e  test    eax, eax
0x1800b9870  jnz     short loc_1800B98EA
0x1800b9872  mov     edx, [rsp+48h+arg_10]
0x1800b9876  mov     rcx, rdi; sesid
0x1800b9879  call    DeleteConditionDBEntries
0x1800b987e  test    eax, eax
0x1800b9880  jnz     short loc_1800B98EA
0x1800b9882  mov     rdx, cs:PolicyExpressionTableId; tableid
0x1800b9889  mov     rcx, rdi; sesid
0x1800b988c  call    cs:__imp_JetDelete
0x1800b9893  nop     dword ptr [rax+rax+00h]
0x1800b9898  mov     ecx, eax
0x1800b989a  lea     rdx, aDeleteexpressi_1; "DeleteExpressionDBEntries:JetMove"
0x1800b98a1  call    PolicyMapJetError
0x1800b98a6  test    eax, eax
0x1800b98a8  jnz     short loc_1800B98EA
0x1800b98aa  mov     rdx, cs:PolicyExpressionTableId; tableid
0x1800b98b1  lea     r8d, [rax+1]; cRow
0x1800b98b5  xor     r9d, r9d; grbit
0x1800b98b8  mov     rcx, rdi; sesid
0x1800b98bb  call    cs:__imp_JetMove
0x1800b98c2  nop     dword ptr [rax+rax+00h]
0x1800b98c7  mov     ecx, eax
0x1800b98c9  lea     rdx, aDeleteexpressi_1; "DeleteExpressionDBEntries:JetMove"
0x1800b98d0  mov     esi, eax
0x1800b98d2  call    PolicyMapJetError
0x1800b98d7  test    eax, eax
0x1800b98d9  jz      loc_1800B9824
0x1800b98df  cmp     esi, 0FFFFF9BDh
0x1800b98e5  cmovnz  ebx, eax
0x1800b98e8  mov     eax, ebx
0x1800b98ea  mov     rbx, [rsp+48h+arg_0]
0x1800b98ef  mov     rsi, [rsp+48h+arg_18]
0x1800b98f4  add     rsp, 40h
0x1800b98f8  pop     rdi
0x1800b98f9  retn
```
