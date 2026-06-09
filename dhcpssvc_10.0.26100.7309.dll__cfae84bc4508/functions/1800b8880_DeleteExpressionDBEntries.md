# DeleteExpressionDBEntries

- ea: `0x1800b8880`
- end: `0x1800b8a0f`
- name: `DeleteExpressionDBEntries`
- size: `399`
- prototype: `__int64 __fastcall(JET_SESID sesid)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800882b8`
- `0x1800bc1fc`

## callees

- `0x1800b861c`
- `0x1800b8880`
- `0x1800bba04`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800b88a9`
- `ESENT!JetSetCurrentIndexA` at `0x1800b88a9`
- `ESENT!JetMakeKey` at `0x1800b88e6`
- `ESENT!JetMakeKey` at `0x1800b88e6`
- `ESENT!JetSeek` at `0x1800b8916`
- `ESENT!JetSeek` at `0x1800b8916`
- `ESENT!JetDelete` at `0x1800b89a0`
- `ESENT!JetDelete` at `0x1800b89a0`
- `ESENT!JetRetrieveColumn` at `0x1800b8968`
- `ESENT!JetRetrieveColumn` at `0x1800b8968`
- `ESENT!JetMove` at `0x1800b89cf`
- `ESENT!JetMove` at `0x1800b89cf`

## string_xrefs

- `0x1800b8976`: `DeletePolicyDBentry:JetRetrieveColumn`
- `0x1800b88b7`: `DeleteExpressionDBEntries:JEtSetCUrentIndex`
- `0x1800b88f4`: `DeleteExpressionDBEntries:JEtMakeKey`
- `0x1800b8924`: `DeleteExpressionDBEntries:JEtSeek`
- `0x1800b89ae`: `DeleteExpressionDBEntries:JetMove`
- `0x1800b89dd`: `DeleteExpressionDBEntries:JetMove`

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
          v8 = JetRetrieveColumn(sesid, PolicyExpressionTableId, dword_1800F76A8, &v13, 4u, 0, 1u, 0);
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
0x1800b8880  mov     rax, rsp
0x1800b8883  mov     [rax+8], rbx
0x1800b8887  mov     [rax+20h], rsi
0x1800b888b  mov     [rax+10h], edx
0x1800b888e  push    rdi
0x1800b888f  sub     rsp, 40h
0x1800b8893  mov     rdx, cs:PolicyExpressionTableId; tableid
0x1800b889a  lea     r8, aPolicyexpressi_2; "PolicyExpressionTable_Index3"
0x1800b88a1  xor     ebx, ebx
0x1800b88a3  mov     rdi, rcx
0x1800b88a6  mov     [rax+18h], ebx
0x1800b88a9  call    cs:__imp_JetSetCurrentIndexA
0x1800b88b0  nop     dword ptr [rax+rax+00h]
0x1800b88b5  mov     ecx, eax
0x1800b88b7  lea     rdx, aDeleteexpressi; "DeleteExpressionDBEntries:JEtSetCUrentI"...
0x1800b88be  call    PolicyMapJetError
0x1800b88c3  test    eax, eax
0x1800b88c5  jnz     loc_1800B89FE
0x1800b88cb  mov     rdx, cs:PolicyExpressionTableId; tableid
0x1800b88d2  lea     r9d, [rbx+4]; cbData
0x1800b88d6  lea     r8, [rsp+48h+pvData]; pvData
0x1800b88db  mov     [rsp+48h+grbit], 1; grbit
0x1800b88e3  mov     rcx, rdi; sesid
0x1800b88e6  call    cs:__imp_JetMakeKey
0x1800b88ed  nop     dword ptr [rax+rax+00h]
0x1800b88f2  mov     ecx, eax
0x1800b88f4  lea     rdx, aDeleteexpressi_0; "DeleteExpressionDBEntries:JEtMakeKey"
0x1800b88fb  call    PolicyMapJetError
0x1800b8900  test    eax, eax
0x1800b8902  jnz     loc_1800B89FE
0x1800b8908  mov     rdx, cs:PolicyExpressionTableId; tableid
0x1800b890f  lea     r8d, [rbx+21h]; grbit
0x1800b8913  mov     rcx, rdi; sesid
0x1800b8916  call    cs:__imp_JetSeek
0x1800b891d  nop     dword ptr [rax+rax+00h]
0x1800b8922  mov     ecx, eax
0x1800b8924  lea     rdx, aDeleteexpressi_2; "DeleteExpressionDBEntries:JEtSeek"
0x1800b892b  call    PolicyMapJetError
0x1800b8930  test    eax, eax
0x1800b8932  jnz     loc_1800B89FE
0x1800b8938  mov     r8d, cs:dword_1800F76A8; columnid
0x1800b893f  lea     r9, [rsp+48h+arg_10]; pvData
0x1800b8944  mov     rdx, cs:PolicyExpressionTableId; tableid
0x1800b894b  mov     rcx, rdi; sesid
0x1800b894e  mov     [rsp+48h+pretinfo], rbx; pretinfo
0x1800b8953  mov     [rsp+48h+var_18], 1; grbit
0x1800b895b  mov     [rsp+48h+pcbActual], rbx; pcbActual
0x1800b8960  mov     [rsp+48h+grbit], 4; cbData
0x1800b8968  call    cs:__imp_JetRetrieveColumn
0x1800b896f  nop     dword ptr [rax+rax+00h]
0x1800b8974  mov     ecx, eax
0x1800b8976  lea     rdx, aDeletepolicydb; "DeletePolicyDBentry:JetRetrieveColumn"
0x1800b897d  call    PolicyMapJetError
0x1800b8982  test    eax, eax
0x1800b8984  jnz     short loc_1800B89FE
0x1800b8986  mov     edx, [rsp+48h+arg_10]
0x1800b898a  mov     rcx, rdi; sesid
0x1800b898d  call    DeleteConditionDBEntries
0x1800b8992  test    eax, eax
0x1800b8994  jnz     short loc_1800B89FE
0x1800b8996  mov     rdx, cs:PolicyExpressionTableId; tableid
0x1800b899d  mov     rcx, rdi; sesid
0x1800b89a0  call    cs:__imp_JetDelete
0x1800b89a7  nop     dword ptr [rax+rax+00h]
0x1800b89ac  mov     ecx, eax
0x1800b89ae  lea     rdx, aDeleteexpressi_1; "DeleteExpressionDBEntries:JetMove"
0x1800b89b5  call    PolicyMapJetError
0x1800b89ba  test    eax, eax
0x1800b89bc  jnz     short loc_1800B89FE
0x1800b89be  mov     rdx, cs:PolicyExpressionTableId; tableid
0x1800b89c5  lea     r8d, [rax+1]; cRow
0x1800b89c9  xor     r9d, r9d; grbit
0x1800b89cc  mov     rcx, rdi; sesid
0x1800b89cf  call    cs:__imp_JetMove
0x1800b89d6  nop     dword ptr [rax+rax+00h]
0x1800b89db  mov     ecx, eax
0x1800b89dd  lea     rdx, aDeleteexpressi_1; "DeleteExpressionDBEntries:JetMove"
0x1800b89e4  mov     esi, eax
0x1800b89e6  call    PolicyMapJetError
0x1800b89eb  test    eax, eax
0x1800b89ed  jz      loc_1800B8938
0x1800b89f3  cmp     esi, 0FFFFF9BDh
0x1800b89f9  cmovnz  ebx, eax
0x1800b89fc  mov     eax, ebx
0x1800b89fe  mov     rbx, [rsp+48h+arg_0]
0x1800b8a03  mov     rsi, [rsp+48h+arg_18]
0x1800b8a08  add     rsp, 40h
0x1800b8a0c  pop     rdi
0x1800b8a0d  retn
```
