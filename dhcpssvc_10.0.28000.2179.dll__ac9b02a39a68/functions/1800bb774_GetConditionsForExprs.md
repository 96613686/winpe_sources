# GetConditionsForExprs

- ea: `0x1800bb774`
- end: `0x1800bb9ac`
- name: `GetConditionsForExprs`
- size: `568`
- prototype: `__int64 __fastcall(JET_SESID sesid)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180088864`
- `0x1800bc860`

## callees

- `0x180094a7c`
- `0x180096254`
- `0x1800962b0`
- `0x180098658`
- `0x1800bb774`
- `0x1800bb9b4`
- `0x1800bc810`
- `0x1800bc990`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800bb7e0`
- `ESENT!JetSetCurrentIndexA` at `0x1800bb7e0`
- `ESENT!JetMakeKey` at `0x1800bb81e`
- `ESENT!JetMakeKey` at `0x1800bb81e`
- `ESENT!JetSeek` at `0x1800bb850`
- `ESENT!JetSeek` at `0x1800bb850`
- `ESENT!JetMove` at `0x1800bb8dd`
- `ESENT!JetMove` at `0x1800bb8dd`

## string_xrefs

- `0x1800bb8eb`: `GetConditionsForExpr:JetMove`

## pseudocode

```c
__int64 __fastcall GetConditionsForExprs(JET_SESID sesid, __int64 a2, unsigned int a3, _QWORD *a4)
{
  unsigned int v4; // edi
  JET_SESID v6; // rbx
  unsigned int i; // r13d
  unsigned int v8; // r12d
  _QWORD *v9; // r15
  unsigned int v10; // eax
  unsigned int v11; // esi
  unsigned int Key; // eax
  unsigned int v13; // ebx
  unsigned int v14; // eax
  _DWORD *v15; // rbx
  unsigned int v16; // r15d
  unsigned int j; // ebx
  __int64 v19; // [rsp+30h] [rbp-18h] BYREF
  _QWORD *v20; // [rsp+38h] [rbp-10h]
  __int64 v22; // [rsp+98h] [rbp+50h]
  int pvData; // [rsp+A8h] [rbp+60h] BYREF

  v22 = a2;
  v4 = 0;
  v6 = sesid;
  if ( a4 )
  {
    *a4 = 0;
    a4[1] = 0;
  }
  for ( i = 0; i < a3; v20 = 0 )
  {
    v19 = 0;
    v8 = 0;
    v9 = 0;
    v20 = 0;
    pvData = *(_DWORD *)(a2 + 4LL * i);
    v10 = JetSetCurrentIndexA(v6, PolicyConditionTableId, "PolicyConditionTable_Index5");
    v11 = PolicyMapJetError(v10, "GetConditionsForexpr:JEtSetCUrentIndex");
    if ( !v11 )
    {
      Key = JetMakeKey(v6, PolicyConditionTableId, &pvData, 4u, 1u);
      v11 = PolicyMapJetError(Key, "GetConditionsForExpr:JEtMakeKey");
      if ( !v11 )
      {
        v13 = JetSeek(v6, PolicyConditionTableId, 0x21u);
        v14 = PolicyMapJetError(v13, "GetConditionsForExpr:JEtSeek");
        v11 = v14;
        if ( v13 == -1601 )
          goto LABEL_19;
        if ( !v14 )
        {
          do
          {
            v15 = (_DWORD *)MemAlloc(0x28u);
            if ( !v15 )
            {
              v11 = 8;
              goto LABEL_17;
            }
            v15[9] = pvData;
            if ( (unsigned int)GetCurrentConditionRecord(sesid) )
            {
              MemConditionTableRecordFree(v15);
              v15 = 0;
            }
            else
            {
              v11 = MemArrayAddElement(&v19, v15);
              if ( v11 )
                goto LABEL_17;
            }
            v16 = JetMove(sesid, PolicyConditionTableId, 1, 0);
            v11 = PolicyMapJetError(v16, "GetConditionsForExpr:JetMove");
          }
          while ( !v11 );
          if ( v16 == -1603 )
          {
            v9 = v20;
            v8 = v19;
            goto LABEL_19;
          }
LABEL_17:
          MemConditionTableRecordFree(v15);
          MemArrayFree(&v19, MemConditionTableRecordFree);
          v9 = v20;
          v8 = v19;
        }
      }
    }
    if ( v11 )
    {
      MemArrayFree(a4, MemConditionTableRecordFree);
      return v11;
    }
LABEL_19:
    for ( j = 0; j < v8; ++j )
      MemArrayAddElement(a4, v9[j]);
    if ( v9 )
      MemFree(v9);
    v6 = sesid;
    ++i;
    a2 = v22;
    v19 = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x1800bb774  mov     [rsp-40h+arg_10], r8d
0x1800bb779  mov     [rsp-40h+arg_8], rdx
0x1800bb77e  mov     [rsp-40h+sesid], rcx
0x1800bb783  push    rbp
0x1800bb784  push    rbx
0x1800bb785  push    rsi
0x1800bb786  push    rdi
0x1800bb787  push    r12
0x1800bb789  push    r13
0x1800bb78b  push    r14
0x1800bb78d  push    r15
0x1800bb78f  mov     rbp, rsp
0x1800bb792  sub     rsp, 48h
0x1800bb796  xor     edi, edi
0x1800bb798  mov     r14, r9
0x1800bb79b  mov     eax, r8d
0x1800bb79e  mov     rbx, rcx
0x1800bb7a1  test    r9, r9
0x1800bb7a4  jz      short loc_1800BB7AD
0x1800bb7a6  mov     [r9], rdi
0x1800bb7a9  mov     [r9+8], rdi
0x1800bb7ad  mov     r13d, edi
0x1800bb7b0  test    eax, eax
0x1800bb7b2  jz      loc_1800BB998
0x1800bb7b8  mov     eax, r13d
0x1800bb7bb  lea     r8, aPolicyconditio_6; "PolicyConditionTable_Index5"
0x1800bb7c2  mov     [rbp+var_18], rdi
0x1800bb7c6  mov     r12d, edi
0x1800bb7c9  mov     r15, rdi
0x1800bb7cc  mov     [rbp+var_10], rdi
0x1800bb7d0  mov     ecx, [rdx+rax*4]
0x1800bb7d3  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800bb7da  mov     [rbp+pvData], ecx
0x1800bb7dd  mov     rcx, rbx; sesid
0x1800bb7e0  call    cs:__imp_JetSetCurrentIndexA
0x1800bb7e7  nop     dword ptr [rax+rax+00h]
0x1800bb7ec  mov     ecx, eax
0x1800bb7ee  lea     rdx, aGetconditionsf_0; "GetConditionsForexpr:JEtSetCUrentIndex"
0x1800bb7f5  call    PolicyMapJetError
0x1800bb7fa  mov     esi, eax
0x1800bb7fc  test    eax, eax
0x1800bb7fe  jnz     loc_1800BB938
0x1800bb804  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800bb80b  lea     r9d, [rax+4]; cbData
0x1800bb80f  lea     r8, [rbp+pvData]; pvData
0x1800bb813  mov     [rsp+48h+grbit], 1; grbit
0x1800bb81b  mov     rcx, rbx; sesid
0x1800bb81e  call    cs:__imp_JetMakeKey
0x1800bb825  nop     dword ptr [rax+rax+00h]
0x1800bb82a  mov     ecx, eax
0x1800bb82c  lea     rdx, aGetconditionsf_1; "GetConditionsForExpr:JEtMakeKey"
0x1800bb833  call    PolicyMapJetError
0x1800bb838  mov     esi, eax
0x1800bb83a  test    eax, eax
0x1800bb83c  jnz     loc_1800BB938
0x1800bb842  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800bb849  lea     r8d, [rax+21h]; grbit
0x1800bb84d  mov     rcx, rbx; sesid
0x1800bb850  call    cs:__imp_JetSeek
0x1800bb857  nop     dword ptr [rax+rax+00h]
0x1800bb85c  mov     ecx, eax
0x1800bb85e  lea     rdx, aGetconditionsf; "GetConditionsForExpr:JEtSeek"
0x1800bb865  mov     ebx, eax
0x1800bb867  call    PolicyMapJetError
0x1800bb86c  mov     esi, eax
0x1800bb86e  cmp     ebx, 0FFFFF9BFh
0x1800bb874  jz      loc_1800BB93C
0x1800bb87a  test    eax, eax
0x1800bb87c  jnz     loc_1800BB938
0x1800bb882  mov     r12, [rbp+sesid]
0x1800bb886  mov     ecx, 28h ; '('; dwBytes
0x1800bb88b  call    MemAlloc
0x1800bb890  mov     rbx, rax
0x1800bb893  test    rax, rax
0x1800bb896  jz      short loc_1800BB913
0x1800bb898  mov     eax, [rbp+pvData]
0x1800bb89b  mov     rdx, rbx
0x1800bb89e  mov     rcx, r12; sesid
0x1800bb8a1  mov     [rbx+24h], eax
0x1800bb8a4  call    GetCurrentConditionRecord
0x1800bb8a9  test    eax, eax
0x1800bb8ab  jnz     short loc_1800BB8C1
0x1800bb8ad  mov     rdx, rbx
0x1800bb8b0  lea     rcx, [rbp+var_18]
0x1800bb8b4  call    MemArrayAddElement
0x1800bb8b9  mov     esi, eax
0x1800bb8bb  test    eax, eax
0x1800bb8bd  jnz     short loc_1800BB918
0x1800bb8bf  jmp     short loc_1800BB8CC
0x1800bb8c1  mov     rcx, rbx; lpMem
0x1800bb8c4  call    MemConditionTableRecordFree
0x1800bb8c9  mov     rbx, rdi
0x1800bb8cc  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800bb8d3  xor     r9d, r9d; grbit
0x1800bb8d6  mov     rcx, r12; sesid
0x1800bb8d9  lea     r8d, [r9+1]; cRow
0x1800bb8dd  call    cs:__imp_JetMove
0x1800bb8e4  nop     dword ptr [rax+rax+00h]
0x1800bb8e9  mov     ecx, eax
0x1800bb8eb  lea     rdx, aGetconditionsf_2; "GetConditionsForExpr:JetMove"
0x1800bb8f2  mov     r15d, eax
0x1800bb8f5  call    PolicyMapJetError
0x1800bb8fa  mov     esi, eax
0x1800bb8fc  test    eax, eax
0x1800bb8fe  jz      short loc_1800BB886
0x1800bb900  cmp     r15d, 0FFFFF9BDh
0x1800bb907  jnz     short loc_1800BB918
0x1800bb909  mov     r15, [rbp+var_10]
0x1800bb90d  mov     r12d, dword ptr [rbp+var_18]
0x1800bb911  jmp     short loc_1800BB93C
0x1800bb913  mov     esi, 8
0x1800bb918  mov     rcx, rbx; lpMem
0x1800bb91b  call    MemConditionTableRecordFree
0x1800bb920  lea     rdx, MemConditionTableRecordFree
0x1800bb927  lea     rcx, [rbp+var_18]
0x1800bb92b  call    MemArrayFree
0x1800bb930  mov     r15, [rbp+var_10]
0x1800bb934  mov     r12d, dword ptr [rbp+var_18]
0x1800bb938  test    esi, esi
0x1800bb93a  jnz     short loc_1800BB987
0x1800bb93c  mov     ebx, edi
0x1800bb93e  test    r12d, r12d
0x1800bb941  jz      short loc_1800BB95B
0x1800bb943  mov     edx, ebx
0x1800bb945  mov     rcx, r14
0x1800bb948  mov     rdx, [r15+rdx*8]
0x1800bb94c  call    MemArrayAddElement
0x1800bb951  lea     eax, [rbx+1]
0x1800bb954  mov     ebx, eax
0x1800bb956  cmp     eax, r12d
0x1800bb959  jb      short loc_1800BB943
0x1800bb95b  test    r15, r15
0x1800bb95e  jz      short loc_1800BB968
0x1800bb960  mov     rcx, r15; lpMem
0x1800bb963  call    MemFree
0x1800bb968  mov     rbx, [rbp+sesid]
0x1800bb96c  inc     r13d
0x1800bb96f  mov     rdx, [rbp+arg_8]
0x1800bb973  mov     [rbp+var_18], rdi
0x1800bb977  mov     [rbp+var_10], rdi
0x1800bb97b  cmp     r13d, [rbp+arg_10]
0x1800bb97f  jb      loc_1800BB7B8
0x1800bb985  jmp     short loc_1800BB998
0x1800bb987  lea     rdx, MemConditionTableRecordFree
0x1800bb98e  mov     rcx, r14
0x1800bb991  call    MemArrayFree
0x1800bb996  mov     edi, esi
0x1800bb998  mov     eax, edi
0x1800bb99a  add     rsp, 48h
0x1800bb99e  pop     r15
0x1800bb9a0  pop     r14
0x1800bb9a2  pop     r13
0x1800bb9a4  pop     r12
0x1800bb9a6  pop     rdi
0x1800bb9a7  pop     rsi
0x1800bb9a8  pop     rbx
0x1800bb9a9  pop     rbp
0x1800bb9aa  retn
```
