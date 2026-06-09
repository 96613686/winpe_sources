# GetExprsForMatchingConditions

- ea: `0x1800cc14c`
- end: `0x1800cc4b0`
- name: `GetExprsForMatchingConditions`
- size: `868`
- prototype: `__int64 __fastcall(JET_SESID sesid, __int64, __int64, __int64, int, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800c6934`
- `0x1800c7a84`

## callees

- `0x1800bba04`
- `0x1800cbee4`
- `0x1800cc14c`
- `0x1800cc560`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800cc1e9`
- `ESENT!JetSetCurrentIndexA` at `0x1800cc2a6`
- `ESENT!JetSetCurrentIndexA` at `0x1800cc1e9`
- `ESENT!JetSetCurrentIndexA` at `0x1800cc2a6`
- `ESENT!JetSeek` at `0x1800cc25b`
- `ESENT!JetSeek` at `0x1800cc325`
- `ESENT!JetSeek` at `0x1800cc25b`
- `ESENT!JetSeek` at `0x1800cc325`
- `ESENT!JetRetrieveColumn` at `0x1800cc386`
- `ESENT!JetRetrieveColumn` at `0x1800cc413`
- `ESENT!JetRetrieveColumn` at `0x1800cc386`
- `ESENT!JetRetrieveColumn` at `0x1800cc413`
- `ESENT!JetMove` at `0x1800cc46c`
- `ESENT!JetMove` at `0x1800cc46c`

## string_xrefs

- `0x1800cc47a`: `GetExpressionsForMatchingConditions:JetMove`

## pseudocode

```c
__int64 __fastcall GetExprsForMatchingConditions(
        JET_SESID sesid,
        __int64 a2,
        int a3,
        __int64 a4,
        int a5,
        unsigned int a6)
{
  const char *v6; // r12
  __int64 v8; // rbx
  int v10; // r14d
  int v11; // r15d
  __int64 result; // rax
  int v13; // edi
  unsigned int v14; // eax
  unsigned int v15; // ebx
  unsigned int v16; // eax
  unsigned int v17; // ebx
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // [rsp+50h] [rbp-10h] BYREF
  int v22; // [rsp+54h] [rbp-Ch] BYREF
  int pvData; // [rsp+58h] [rbp-8h] BYREF
  int v25; // [rsp+B0h] [rbp+50h] BYREF

  v25 = a3;
  v6 = "PolicyConditionTable_Index4";
  v8 = a2;
  pvData = 0;
  v10 = 0;
  v22 = 0;
  v11 = 1;
  if ( !a5 )
  {
    v13 = 1;
    LOBYTE(v21) = 0;
    goto LABEL_19;
  }
  if ( a5 != 1 )
  {
    if ( a5 != 2 )
    {
      if ( a5 == 3 )
      {
LABEL_9:
        LOBYTE(v21) = 1;
        goto LABEL_13;
      }
      if ( a5 != 4 )
      {
        if ( a5 != 5 )
          return 87;
        v11 = 0;
        goto LABEL_9;
      }
      v11 = 0;
    }
    v13 = 1;
    LOBYTE(v21) = 1;
    goto LABEL_19;
  }
  LOBYTE(v21) = 0;
LABEL_13:
  v13 = 0;
  if ( a6 <= *(_DWORD *)(a4 + 8) )
  {
    v14 = JetSetCurrentIndexA(sesid, PolicyConditionTableId, "PolicyConditionTable_Index4");
    result = PolicyMapJetError(v14, "GetExpressionsForMatchingConditions:JetSetCurrentIndex1");
    if ( (_DWORD)result )
      return result;
    v10 = 1;
    result = JetMakeKeyForPolicyField(sesid, v8, &v25, a4, &a5, &v21, &a6, 1, v11);
    if ( (_DWORD)result )
      return result;
    v15 = JetSeek(sesid, PolicyConditionTableId, 1u);
    result = PolicyMapJetError(v15, "GetExpressionsforMatchingConditions:JetSeek1");
    if ( v15 == -1601 )
    {
      v10 = 0;
    }
    else
    {
      if ( (_DWORD)result )
        return result;
      v18 = JetRetrieveColumn(sesid, PolicyConditionTableId, dword_1800F7758, &pvData, 4u, 0, 1u, 0);
      result = PolicyMapJetError(v18, "GetExpressionsforMatchingConditions:JetRetrieveColumn");
      if ( (_DWORD)result )
        return result;
    }
    v8 = a2;
  }
LABEL_19:
  if ( !v13 )
    v6 = "PolicyConditionTable_Index6";
  v16 = JetSetCurrentIndexA(sesid, PolicyConditionTableId, v6);
  result = PolicyMapJetError(v16, "GetExpressionsForMatchingConditions:JetSetCurrentIndex");
  if ( !(_DWORD)result )
  {
    result = JetMakeKeyForPolicyField(sesid, v8, &v25, a4, &a5, &v21, &a6, v13, v11);
    if ( !(_DWORD)result )
    {
      v17 = JetSeek(sesid, PolicyConditionTableId, (32 * (v13 ^ 1)) | 1);
      result = PolicyMapJetError(v17, "GetExpressionsforMatchingConditions:JetSeek");
      if ( v17 == -1601 )
      {
        return 0;
      }
      else if ( !(_DWORD)result )
      {
        if ( v13 )
        {
          return GetContainerExprIds(sesid, PolicyConditionTableId, dword_1800F7860);
        }
        else
        {
          do
          {
            if ( !v10 )
              goto LABEL_36;
            v19 = JetRetrieveColumn(sesid, PolicyConditionTableId, dword_1800F7758, &v22, 4u, 0, 1u, 0);
            result = PolicyMapJetError(v19, "GetExpressionsforMatchingConditions:JetRetrieveColumn1");
            if ( (_DWORD)result )
              return result;
            if ( pvData == v22 )
            {
              v10 = 0;
            }
            else
            {
LABEL_36:
              result = GetContainerExprIds(sesid, PolicyConditionTableId, dword_1800F7860);
              if ( (_DWORD)result )
                return result;
            }
            v20 = JetMove(sesid, PolicyConditionTableId, 1, 0);
            result = PolicyMapJetError(v20, "GetExpressionsForMatchingConditions:JetMove");
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
0x1800cc14c  mov     [rsp-38h+arg_0], rbx
0x1800cc151  mov     [rsp-38h+arg_10], r8d
0x1800cc156  mov     [rsp-38h+arg_8], rdx
0x1800cc15b  push    rbp
0x1800cc15c  push    rsi
0x1800cc15d  push    rdi
0x1800cc15e  push    r12
0x1800cc160  push    r13
0x1800cc162  push    r14
0x1800cc164  push    r15
0x1800cc166  mov     rbp, rsp
0x1800cc169  sub     rsp, 60h
0x1800cc16d  mov     eax, [rbp+arg_20]
0x1800cc170  lea     r12, aPolicyconditio_0; "PolicyConditionTable_Index4"
0x1800cc177  mov     rsi, rcx
0x1800cc17a  mov     rbx, rdx
0x1800cc17d  xor     ecx, ecx
0x1800cc17f  mov     r13, r9
0x1800cc182  mov     [rbp+pvData], ecx
0x1800cc185  mov     r14d, ecx
0x1800cc188  mov     [rbp+var_C], ecx
0x1800cc18b  lea     edx, [rcx+1]
0x1800cc18e  mov     r15d, edx
0x1800cc191  test    eax, eax
0x1800cc193  jz      loc_1800CC3AD
0x1800cc199  sub     eax, edx
0x1800cc19b  jz      short loc_1800CC1CA
0x1800cc19d  sub     eax, edx
0x1800cc19f  jz      short loc_1800CC1C0
0x1800cc1a1  sub     eax, edx
0x1800cc1a3  jz      short loc_1800CC1B8
0x1800cc1a5  sub     eax, edx
0x1800cc1a7  jz      short loc_1800CC1BD
0x1800cc1a9  cmp     eax, edx
0x1800cc1ab  jz      short loc_1800CC1B5
0x1800cc1ad  lea     eax, [rcx+57h]
0x1800cc1b0  jmp     loc_1800CC497
0x1800cc1b5  mov     r15d, ecx
0x1800cc1b8  mov     byte ptr [rbp+var_10], dl
0x1800cc1bb  jmp     short loc_1800CC1CD
0x1800cc1bd  mov     r15d, ecx
0x1800cc1c0  mov     edi, edx
0x1800cc1c2  mov     byte ptr [rbp+var_10], dl
0x1800cc1c5  jmp     loc_1800CC28C
0x1800cc1ca  mov     byte ptr [rbp+var_10], cl
0x1800cc1cd  mov     eax, [r9+8]
0x1800cc1d1  mov     edi, ecx
0x1800cc1d3  cmp     [rbp+arg_28], eax
0x1800cc1d6  ja      loc_1800CC28C
0x1800cc1dc  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800cc1e3  mov     r8, r12; szIndexName
0x1800cc1e6  mov     rcx, rsi; sesid
0x1800cc1e9  call    cs:__imp_JetSetCurrentIndexA
0x1800cc1f0  nop     dword ptr [rax+rax+00h]
0x1800cc1f5  mov     ecx, eax
0x1800cc1f7  lea     rdx, aGetexpressions_0; "GetExpressionsForMatchingConditions:Jet"...
0x1800cc1fe  call    PolicyMapJetError
0x1800cc203  test    eax, eax
0x1800cc205  jnz     loc_1800CC497
0x1800cc20b  lea     r14d, [rax+1]
0x1800cc20f  mov     [rsp+60h+var_20], r15d; int
0x1800cc214  mov     dword ptr [rsp+60h+pretinfo], r14d; int
0x1800cc219  lea     rax, [rbp+arg_28]
0x1800cc21d  mov     qword ptr [rsp+60h+grbit], rax; void *
0x1800cc222  lea     r8, [rbp+arg_10]
0x1800cc226  lea     rax, [rbp+var_10]
0x1800cc22a  mov     r9, r13
0x1800cc22d  mov     [rsp+60h+pcbActual], rax; void *
0x1800cc232  mov     rdx, rbx
0x1800cc235  lea     rax, [rbp+arg_20]
0x1800cc239  mov     rcx, rsi; sesid
0x1800cc23c  mov     qword ptr [rsp+60h+cbData], rax; pvData
0x1800cc241  call    JetMakeKeyForPolicyField
0x1800cc246  test    eax, eax
0x1800cc248  jnz     loc_1800CC497
0x1800cc24e  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800cc255  mov     r8d, r14d; grbit
0x1800cc258  mov     rcx, rsi; sesid
0x1800cc25b  call    cs:__imp_JetSeek
0x1800cc262  nop     dword ptr [rax+rax+00h]
0x1800cc267  mov     ecx, eax
0x1800cc269  lea     rdx, aGetexpressions; "GetExpressionsforMatchingConditions:Jet"...
0x1800cc270  mov     ebx, eax
0x1800cc272  call    PolicyMapJetError
0x1800cc277  cmp     ebx, 0FFFFF9BFh
0x1800cc27d  jnz     loc_1800CC350
0x1800cc283  xor     ecx, ecx
0x1800cc285  mov     r14d, ecx
0x1800cc288  mov     rbx, [rbp+arg_8]
0x1800cc28c  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800cc293  lea     rax, aPolicyconditio; "PolicyConditionTable_Index6"
0x1800cc29a  test    edi, edi
0x1800cc29c  mov     rcx, rsi; sesid
0x1800cc29f  cmovz   r12, rax
0x1800cc2a3  mov     r8, r12; szIndexName
0x1800cc2a6  call    cs:__imp_JetSetCurrentIndexA
0x1800cc2ad  nop     dword ptr [rax+rax+00h]
0x1800cc2b2  mov     ecx, eax
0x1800cc2b4  lea     rdx, aGetexpressions_7; "GetExpressionsForMatchingConditions:Jet"...
0x1800cc2bb  call    PolicyMapJetError
0x1800cc2c0  xor     r12d, r12d
0x1800cc2c3  test    eax, eax
0x1800cc2c5  jnz     loc_1800CC497
0x1800cc2cb  mov     [rsp+60h+var_20], r15d; int
0x1800cc2d0  lea     rax, [rbp+arg_28]
0x1800cc2d4  mov     dword ptr [rsp+60h+pretinfo], edi; int
0x1800cc2d8  lea     r8, [rbp+arg_10]
0x1800cc2dc  mov     qword ptr [rsp+60h+grbit], rax; void *
0x1800cc2e1  mov     r9, r13
0x1800cc2e4  lea     rax, [rbp+var_10]
0x1800cc2e8  mov     rdx, rbx
0x1800cc2eb  mov     [rsp+60h+pcbActual], rax; void *
0x1800cc2f0  mov     rcx, rsi; sesid
0x1800cc2f3  lea     rax, [rbp+arg_20]
0x1800cc2f7  mov     qword ptr [rsp+60h+cbData], rax; pvData
0x1800cc2fc  call    JetMakeKeyForPolicyField
0x1800cc301  test    eax, eax
0x1800cc303  jnz     loc_1800CC497
0x1800cc309  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800cc310  lea     r15d, [r12+1]
0x1800cc315  mov     r8d, edi
0x1800cc318  mov     rcx, rsi; sesid
0x1800cc31b  xor     r8d, r15d
0x1800cc31e  shl     r8d, 5
0x1800cc322  or      r8d, r15d; grbit
0x1800cc325  call    cs:__imp_JetSeek
0x1800cc32c  nop     dword ptr [rax+rax+00h]
0x1800cc331  mov     ecx, eax
0x1800cc333  lea     rdx, aGetexpressions_4; "GetExpressionsforMatchingConditions:Jet"...
0x1800cc33a  mov     ebx, eax
0x1800cc33c  call    PolicyMapJetError
0x1800cc341  cmp     ebx, 0FFFFF9BFh
0x1800cc347  jnz     short loc_1800CC3B7
0x1800cc349  xor     eax, eax
0x1800cc34b  jmp     loc_1800CC497
0x1800cc350  test    eax, eax
0x1800cc352  jnz     loc_1800CC497
0x1800cc358  and     [rsp+60h+pretinfo], 0
0x1800cc35e  lea     r9, [rbp+pvData]; pvData
0x1800cc362  mov     r8d, cs:dword_1800F7758; columnid
0x1800cc369  mov     rcx, rsi; sesid
0x1800cc36c  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800cc373  mov     [rsp+60h+grbit], r14d; grbit
0x1800cc378  and     [rsp+60h+pcbActual], 0
0x1800cc37e  mov     [rsp+60h+cbData], 4; cbData
0x1800cc386  call    cs:__imp_JetRetrieveColumn
0x1800cc38d  nop     dword ptr [rax+rax+00h]
0x1800cc392  mov     ecx, eax
0x1800cc394  lea     rdx, aGetexpressions_6; "GetExpressionsforMatchingConditions:Jet"...
0x1800cc39b  call    PolicyMapJetError
0x1800cc3a0  test    eax, eax
0x1800cc3a2  jz      loc_1800CC288
0x1800cc3a8  jmp     loc_1800CC497
0x1800cc3ad  mov     edi, edx
0x1800cc3af  mov     byte ptr [rbp+var_10], cl
0x1800cc3b2  jmp     loc_1800CC28C
0x1800cc3b7  test    eax, eax
0x1800cc3b9  jnz     loc_1800CC497
0x1800cc3bf  test    edi, edi
0x1800cc3c1  jz      short loc_1800CC3E2
0x1800cc3c3  mov     r9, [rbp+arg_30]
0x1800cc3c7  mov     rcx, rsi; sesid
0x1800cc3ca  mov     r8d, cs:dword_1800F7860; columnid
0x1800cc3d1  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800cc3d8  call    GetContainerExprIds
0x1800cc3dd  jmp     loc_1800CC497
0x1800cc3e2  test    r14d, r14d
0x1800cc3e5  jz      short loc_1800CC43E
0x1800cc3e7  mov     r8d, cs:dword_1800F7758; columnid
0x1800cc3ee  lea     r9, [rbp+var_C]; pvData
0x1800cc3f2  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800cc3f9  mov     rcx, rsi; sesid
0x1800cc3fc  mov     [rsp+60h+pretinfo], r12; pretinfo
0x1800cc401  mov     [rsp+60h+grbit], r15d; grbit
0x1800cc406  mov     [rsp+60h+pcbActual], r12; pcbActual
0x1800cc40b  mov     [rsp+60h+cbData], 4; cbData
0x1800cc413  call    cs:__imp_JetRetrieveColumn
0x1800cc41a  nop     dword ptr [rax+rax+00h]
0x1800cc41f  mov     ecx, eax
0x1800cc421  lea     rdx, aGetexpressions_9; "GetExpressionsforMatchingConditions:Jet"...
0x1800cc428  call    PolicyMapJetError
0x1800cc42d  test    eax, eax
0x1800cc42f  jnz     short loc_1800CC497
0x1800cc431  mov     eax, [rbp+var_C]
0x1800cc434  cmp     [rbp+pvData], eax
0x1800cc437  jnz     short loc_1800CC43E
0x1800cc439  mov     r14d, r12d
0x1800cc43c  jmp     short loc_1800CC45C
0x1800cc43e  mov     r9, [rbp+arg_30]
0x1800cc442  mov     rcx, rsi; sesid
0x1800cc445  mov     r8d, cs:dword_1800F7860; columnid
0x1800cc44c  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800cc453  call    GetContainerExprIds
0x1800cc458  test    eax, eax
0x1800cc45a  jnz     short loc_1800CC497
0x1800cc45c  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800cc463  xor     r9d, r9d; grbit
0x1800cc466  mov     r8d, r15d; cRow
0x1800cc469  mov     rcx, rsi; sesid
0x1800cc46c  call    cs:__imp_JetMove
0x1800cc473  nop     dword ptr [rax+rax+00h]
0x1800cc478  mov     ecx, eax
0x1800cc47a  lea     rdx, aGetexpressions_1; "GetExpressionsForMatchingConditions:Jet"...
0x1800cc481  call    PolicyMapJetError
0x1800cc486  test    eax, eax
0x1800cc488  jz      loc_1800CC3E2
0x1800cc48e  cmp     eax, 103h
0x1800cc493  cmovz   eax, r12d
0x1800cc497  mov     rbx, [rsp+60h+arg_0]
0x1800cc49f  add     rsp, 60h
0x1800cc4a3  pop     r15
0x1800cc4a5  pop     r14
0x1800cc4a7  pop     r13
0x1800cc4a9  pop     r12
0x1800cc4ab  pop     rdi
0x1800cc4ac  pop     rsi
0x1800cc4ad  pop     rbp
0x1800cc4ae  retn
```
