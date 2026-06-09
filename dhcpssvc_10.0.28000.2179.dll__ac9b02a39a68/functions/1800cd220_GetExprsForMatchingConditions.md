# GetExprsForMatchingConditions

- ea: `0x1800cd220`
- end: `0x1800cd58a`
- name: `GetExprsForMatchingConditions`
- size: `874`
- prototype: `__int64 __usercall@<rax>(JET_SESID sesid@<rcx>, int, int, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800c795c`
- `0x1800c8aac`

## callees

- `0x1800bc990`
- `0x1800ccfa8`
- `0x1800cd220`
- `0x1800cd638`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800cd2bd`
- `ESENT!JetSetCurrentIndexA` at `0x1800cd37a`
- `ESENT!JetSetCurrentIndexA` at `0x1800cd2bd`
- `ESENT!JetSetCurrentIndexA` at `0x1800cd37a`
- `ESENT!JetSeek` at `0x1800cd32f`
- `ESENT!JetSeek` at `0x1800cd3f9`
- `ESENT!JetSeek` at `0x1800cd32f`
- `ESENT!JetSeek` at `0x1800cd3f9`
- `ESENT!JetRetrieveColumn` at `0x1800cd460`
- `ESENT!JetRetrieveColumn` at `0x1800cd4ed`
- `ESENT!JetRetrieveColumn` at `0x1800cd460`
- `ESENT!JetRetrieveColumn` at `0x1800cd4ed`
- `ESENT!JetMove` at `0x1800cd546`
- `ESENT!JetMove` at `0x1800cd546`

## string_xrefs

- `0x1800cd554`: `GetExpressionsForMatchingConditions:JetMove`

## pseudocode

```c
__int64 __fastcall GetExprsForMatchingConditions(
        JET_SESID sesid,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        unsigned int a6)
{
  const char *v6; // r12
  int v8; // r14d
  int v9; // r15d
  __int64 result; // rax
  int v11; // edi
  unsigned int v12; // eax
  unsigned int v13; // ebx
  unsigned int v14; // eax
  unsigned int v15; // ebx
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  _BYTE v19[4]; // [rsp+50h] [rbp-10h] BYREF
  int v20; // [rsp+54h] [rbp-Ch] BYREF
  int pvData; // [rsp+58h] [rbp-8h] BYREF

  v6 = "PolicyConditionTable_Index4";
  pvData = 0;
  v8 = 0;
  v20 = 0;
  v9 = 1;
  if ( !a5 )
  {
    v11 = 1;
    v19[0] = 0;
    goto LABEL_18;
  }
  if ( a5 != 1 )
  {
    if ( a5 != 2 )
    {
      if ( a5 == 3 )
      {
LABEL_9:
        v19[0] = 1;
        goto LABEL_13;
      }
      if ( a5 != 4 )
      {
        if ( a5 != 5 )
          return 87;
        v9 = 0;
        goto LABEL_9;
      }
      v9 = 0;
    }
    v11 = 1;
    v19[0] = 1;
    goto LABEL_18;
  }
  v19[0] = 0;
LABEL_13:
  v11 = 0;
  if ( a6 <= *(_DWORD *)(a4 + 8) )
  {
    v12 = JetSetCurrentIndexA(sesid, PolicyConditionTableId, "PolicyConditionTable_Index4");
    result = PolicyMapJetError(v12, "GetExpressionsForMatchingConditions:JetSetCurrentIndex1");
    if ( (_DWORD)result )
      return result;
    v8 = 1;
    result = JetMakeKeyForPolicyField(sesid, &a5, v19, &a6, 1, v9);
    if ( (_DWORD)result )
      return result;
    v13 = JetSeek(sesid, PolicyConditionTableId, 1u);
    result = PolicyMapJetError(v13, "GetExpressionsforMatchingConditions:JetSeek1");
    if ( v13 == -1601 )
    {
      v8 = 0;
    }
    else
    {
      if ( (_DWORD)result )
        return result;
      v16 = JetRetrieveColumn(sesid, PolicyConditionTableId, dword_1800F9568, &pvData, 4u, 0, 1u, 0);
      result = PolicyMapJetError(v16, "GetExpressionsforMatchingConditions:JetRetrieveColumn");
      if ( (_DWORD)result )
        return result;
    }
  }
LABEL_18:
  if ( !v11 )
    v6 = "PolicyConditionTable_Index6";
  v14 = JetSetCurrentIndexA(sesid, PolicyConditionTableId, v6);
  result = PolicyMapJetError(v14, "GetExpressionsForMatchingConditions:JetSetCurrentIndex");
  if ( !(_DWORD)result )
  {
    result = JetMakeKeyForPolicyField(sesid, &a5, v19, &a6, v11, v9);
    if ( !(_DWORD)result )
    {
      v15 = JetSeek(sesid, PolicyConditionTableId, (32 * (v11 ^ 1)) | 1);
      result = PolicyMapJetError(v15, "GetExpressionsforMatchingConditions:JetSeek");
      if ( v15 == -1601 )
      {
        return 0;
      }
      else if ( !(_DWORD)result )
      {
        if ( v11 )
        {
          return GetContainerExprIds(sesid, PolicyConditionTableId, dword_1800F9670);
        }
        else
        {
          do
          {
            if ( !v8 )
              goto LABEL_35;
            v17 = JetRetrieveColumn(sesid, PolicyConditionTableId, dword_1800F9568, &v20, 4u, 0, 1u, 0);
            result = PolicyMapJetError(v17, "GetExpressionsforMatchingConditions:JetRetrieveColumn1");
            if ( (_DWORD)result )
              return result;
            if ( pvData == v20 )
            {
              v8 = 0;
            }
            else
            {
LABEL_35:
              result = GetContainerExprIds(sesid, PolicyConditionTableId, dword_1800F9670);
              if ( (_DWORD)result )
                return result;
            }
            v18 = JetMove(sesid, PolicyConditionTableId, 1, 0);
            result = PolicyMapJetError(v18, "GetExpressionsForMatchingConditions:JetMove");
          }
          while ( !(_DWORD)result );
          if ( (_DWORD)result == 259 )
            return 0;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800cd220  mov     [rsp-38h+arg_0], rbx
0x1800cd225  mov     [rsp-38h+arg_10], r8d
0x1800cd22a  mov     [rsp-38h+arg_8], rdx
0x1800cd22f  push    rbp
0x1800cd230  push    rsi
0x1800cd231  push    rdi
0x1800cd232  push    r12
0x1800cd234  push    r13
0x1800cd236  push    r14
0x1800cd238  push    r15
0x1800cd23a  mov     rbp, rsp
0x1800cd23d  sub     rsp, 60h
0x1800cd241  mov     eax, [rbp+arg_20]
0x1800cd244  lea     r12, aPolicyconditio_0; "PolicyConditionTable_Index4"
0x1800cd24b  mov     rsi, rcx
0x1800cd24e  mov     rbx, rdx
0x1800cd251  xor     ecx, ecx
0x1800cd253  mov     r13, r9
0x1800cd256  mov     [rbp+pvData], ecx
0x1800cd259  mov     r14d, ecx
0x1800cd25c  mov     [rbp+var_C], ecx
0x1800cd25f  lea     edx, [rcx+1]
0x1800cd262  mov     r15d, edx
0x1800cd265  test    eax, eax
0x1800cd267  jz      loc_1800CD487
0x1800cd26d  sub     eax, edx
0x1800cd26f  jz      short loc_1800CD29E
0x1800cd271  sub     eax, edx
0x1800cd273  jz      short loc_1800CD294
0x1800cd275  sub     eax, edx
0x1800cd277  jz      short loc_1800CD28C
0x1800cd279  sub     eax, edx
0x1800cd27b  jz      short loc_1800CD291
0x1800cd27d  cmp     eax, edx
0x1800cd27f  jz      short loc_1800CD289
0x1800cd281  lea     eax, [rcx+57h]
0x1800cd284  jmp     loc_1800CD571
0x1800cd289  mov     r15d, ecx
0x1800cd28c  mov     [rbp+var_10], dl
0x1800cd28f  jmp     short loc_1800CD2A1
0x1800cd291  mov     r15d, ecx
0x1800cd294  mov     edi, edx
0x1800cd296  mov     [rbp+var_10], dl
0x1800cd299  jmp     loc_1800CD360
0x1800cd29e  mov     [rbp+var_10], cl
0x1800cd2a1  mov     eax, [r9+8]
0x1800cd2a5  mov     edi, ecx
0x1800cd2a7  cmp     [rbp+arg_28], eax
0x1800cd2aa  ja      loc_1800CD360
0x1800cd2b0  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800cd2b7  mov     r8, r12; szIndexName
0x1800cd2ba  mov     rcx, rsi; sesid
0x1800cd2bd  call    cs:__imp_JetSetCurrentIndexA
0x1800cd2c4  nop     dword ptr [rax+rax+00h]
0x1800cd2c9  mov     ecx, eax
0x1800cd2cb  lea     rdx, aGetexpressions_0; "GetExpressionsForMatchingConditions:Jet"...
0x1800cd2d2  call    PolicyMapJetError
0x1800cd2d7  test    eax, eax
0x1800cd2d9  jnz     loc_1800CD571
0x1800cd2df  lea     r14d, [rax+1]
0x1800cd2e3  mov     [rsp+60h+var_20], r15d; int
0x1800cd2e8  mov     dword ptr [rsp+60h+pretinfo], r14d; int
0x1800cd2ed  lea     rax, [rbp+arg_28]
0x1800cd2f1  mov     qword ptr [rsp+60h+grbit], rax; void *
0x1800cd2f6  lea     r8, [rbp+arg_10]
0x1800cd2fa  lea     rax, [rbp+var_10]
0x1800cd2fe  mov     r9, r13
0x1800cd301  mov     [rsp+60h+pcbActual], rax; void *
0x1800cd306  mov     rdx, rbx
0x1800cd309  lea     rax, [rbp+arg_20]
0x1800cd30d  mov     rcx, rsi; sesid
0x1800cd310  mov     qword ptr [rsp+60h+cbData], rax; pvData
0x1800cd315  call    JetMakeKeyForPolicyField
0x1800cd31a  test    eax, eax
0x1800cd31c  jnz     loc_1800CD571
0x1800cd322  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800cd329  mov     r8d, r14d; grbit
0x1800cd32c  mov     rcx, rsi; sesid
0x1800cd32f  call    cs:__imp_JetSeek
0x1800cd336  nop     dword ptr [rax+rax+00h]
0x1800cd33b  mov     ecx, eax
0x1800cd33d  lea     rdx, aGetexpressions; "GetExpressionsforMatchingConditions:Jet"...
0x1800cd344  mov     ebx, eax
0x1800cd346  call    PolicyMapJetError
0x1800cd34b  cmp     ebx, 0FFFFF9BFh
0x1800cd351  jnz     loc_1800CD424
0x1800cd357  xor     ecx, ecx
0x1800cd359  mov     r14d, ecx
0x1800cd35c  mov     rbx, [rbp+arg_8]
0x1800cd360  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800cd367  lea     rax, aPolicyconditio; "PolicyConditionTable_Index6"
0x1800cd36e  test    edi, edi
0x1800cd370  mov     rcx, rsi; sesid
0x1800cd373  cmovz   r12, rax
0x1800cd377  mov     r8, r12; szIndexName
0x1800cd37a  call    cs:__imp_JetSetCurrentIndexA
0x1800cd381  nop     dword ptr [rax+rax+00h]
0x1800cd386  mov     ecx, eax
0x1800cd388  lea     rdx, aGetexpressions_7; "GetExpressionsForMatchingConditions:Jet"...
0x1800cd38f  call    PolicyMapJetError
0x1800cd394  xor     r12d, r12d
0x1800cd397  test    eax, eax
0x1800cd399  jnz     loc_1800CD571
0x1800cd39f  mov     [rsp+60h+var_20], r15d; int
0x1800cd3a4  lea     rax, [rbp+arg_28]
0x1800cd3a8  mov     dword ptr [rsp+60h+pretinfo], edi; int
0x1800cd3ac  lea     r8, [rbp+arg_10]
0x1800cd3b0  mov     qword ptr [rsp+60h+grbit], rax; void *
0x1800cd3b5  mov     r9, r13
0x1800cd3b8  lea     rax, [rbp+var_10]
0x1800cd3bc  mov     rdx, rbx
0x1800cd3bf  mov     [rsp+60h+pcbActual], rax; void *
0x1800cd3c4  mov     rcx, rsi; sesid
0x1800cd3c7  lea     rax, [rbp+arg_20]
0x1800cd3cb  mov     qword ptr [rsp+60h+cbData], rax; pvData
0x1800cd3d0  call    JetMakeKeyForPolicyField
0x1800cd3d5  test    eax, eax
0x1800cd3d7  jnz     loc_1800CD571
0x1800cd3dd  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800cd3e4  lea     r15d, [r12+1]
0x1800cd3e9  mov     r8d, edi
0x1800cd3ec  mov     rcx, rsi; sesid
0x1800cd3ef  xor     r8d, r15d
0x1800cd3f2  shl     r8d, 5
0x1800cd3f6  or      r8d, r15d; grbit
0x1800cd3f9  call    cs:__imp_JetSeek
0x1800cd400  nop     dword ptr [rax+rax+00h]
0x1800cd405  mov     ecx, eax
0x1800cd407  lea     rdx, aGetexpressions_4; "GetExpressionsforMatchingConditions:Jet"...
0x1800cd40e  mov     ebx, eax
0x1800cd410  call    PolicyMapJetError
0x1800cd415  cmp     ebx, 0FFFFF9BFh
0x1800cd41b  jnz     short loc_1800CD491
0x1800cd41d  xor     eax, eax
0x1800cd41f  jmp     loc_1800CD571
0x1800cd424  test    eax, eax
0x1800cd426  jnz     loc_1800CD571
0x1800cd42c  mov     r8d, cs:dword_1800F9568; columnid
0x1800cd433  lea     r9, [rbp+pvData]; pvData
0x1800cd437  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800cd43e  mov     rcx, rsi; sesid
0x1800cd441  mov     [rsp+60h+pretinfo], 0; pretinfo
0x1800cd44a  mov     [rsp+60h+grbit], r14d; grbit
0x1800cd44f  mov     [rsp+60h+pcbActual], 0; pcbActual
0x1800cd458  mov     [rsp+60h+cbData], 4; cbData
0x1800cd460  call    cs:__imp_JetRetrieveColumn
0x1800cd467  nop     dword ptr [rax+rax+00h]
0x1800cd46c  mov     ecx, eax
0x1800cd46e  lea     rdx, aGetexpressions_6; "GetExpressionsforMatchingConditions:Jet"...
0x1800cd475  call    PolicyMapJetError
0x1800cd47a  test    eax, eax
0x1800cd47c  jz      loc_1800CD35C
0x1800cd482  jmp     loc_1800CD571
0x1800cd487  mov     edi, edx
0x1800cd489  mov     [rbp+var_10], cl
0x1800cd48c  jmp     loc_1800CD360
0x1800cd491  test    eax, eax
0x1800cd493  jnz     loc_1800CD571
0x1800cd499  test    edi, edi
0x1800cd49b  jz      short loc_1800CD4BC
0x1800cd49d  mov     r9, [rbp+arg_30]
0x1800cd4a1  mov     rcx, rsi; sesid
0x1800cd4a4  mov     r8d, cs:dword_1800F9670; columnid
0x1800cd4ab  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800cd4b2  call    GetContainerExprIds
0x1800cd4b7  jmp     loc_1800CD571
0x1800cd4bc  test    r14d, r14d
0x1800cd4bf  jz      short loc_1800CD518
0x1800cd4c1  mov     r8d, cs:dword_1800F9568; columnid
0x1800cd4c8  lea     r9, [rbp+var_C]; pvData
0x1800cd4cc  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800cd4d3  mov     rcx, rsi; sesid
0x1800cd4d6  mov     [rsp+60h+pretinfo], r12; pretinfo
0x1800cd4db  mov     [rsp+60h+grbit], r15d; grbit
0x1800cd4e0  mov     [rsp+60h+pcbActual], r12; pcbActual
0x1800cd4e5  mov     [rsp+60h+cbData], 4; cbData
0x1800cd4ed  call    cs:__imp_JetRetrieveColumn
0x1800cd4f4  nop     dword ptr [rax+rax+00h]
0x1800cd4f9  mov     ecx, eax
0x1800cd4fb  lea     rdx, aGetexpressions_9; "GetExpressionsforMatchingConditions:Jet"...
0x1800cd502  call    PolicyMapJetError
0x1800cd507  test    eax, eax
0x1800cd509  jnz     short loc_1800CD571
0x1800cd50b  mov     eax, [rbp+var_C]
0x1800cd50e  cmp     [rbp+pvData], eax
0x1800cd511  jnz     short loc_1800CD518
0x1800cd513  mov     r14d, r12d
0x1800cd516  jmp     short loc_1800CD536
0x1800cd518  mov     r9, [rbp+arg_30]
0x1800cd51c  mov     rcx, rsi; sesid
0x1800cd51f  mov     r8d, cs:dword_1800F9670; columnid
0x1800cd526  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800cd52d  call    GetContainerExprIds
0x1800cd532  test    eax, eax
0x1800cd534  jnz     short loc_1800CD571
0x1800cd536  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800cd53d  xor     r9d, r9d; grbit
0x1800cd540  mov     r8d, r15d; cRow
0x1800cd543  mov     rcx, rsi; sesid
0x1800cd546  call    cs:__imp_JetMove
0x1800cd54d  nop     dword ptr [rax+rax+00h]
0x1800cd552  mov     ecx, eax
0x1800cd554  lea     rdx, aGetexpressions_1; "GetExpressionsForMatchingConditions:Jet"...
0x1800cd55b  call    PolicyMapJetError
0x1800cd560  test    eax, eax
0x1800cd562  jz      loc_1800CD4BC
0x1800cd568  cmp     eax, 103h
0x1800cd56d  cmovz   eax, r12d
0x1800cd571  mov     rbx, [rsp+60h+arg_0]
0x1800cd579  add     rsp, 60h
0x1800cd57d  pop     r15
0x1800cd57f  pop     r14
0x1800cd581  pop     r13
0x1800cd583  pop     r12
0x1800cd585  pop     rdi
0x1800cd586  pop     rsi
0x1800cd587  pop     rbp
0x1800cd588  retn
```
