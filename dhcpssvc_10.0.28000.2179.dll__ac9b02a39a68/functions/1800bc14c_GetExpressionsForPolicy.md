# GetExpressionsForPolicy

- ea: `0x1800bc14c`
- end: `0x1800bc30b`
- name: `GetExpressionsForPolicy`
- size: `447`
- prototype: `__int64 __fastcall(JET_SESID sesid)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180088864`
- `0x1800bc860`

## callees

- `0x180094a7c`
- `0x180096254`
- `0x1800962b0`
- `0x180098658`
- `0x1800bbc08`
- `0x1800bc14c`
- `0x1800bc990`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800bc170`
- `ESENT!JetSetCurrentIndexA` at `0x1800bc170`
- `ESENT!JetMakeKey` at `0x1800bc1b7`
- `ESENT!JetMakeKey` at `0x1800bc1f0`
- `ESENT!JetMakeKey` at `0x1800bc1b7`
- `ESENT!JetMakeKey` at `0x1800bc1f0`
- `ESENT!JetSeek` at `0x1800bc220`
- `ESENT!JetSeek` at `0x1800bc220`
- `ESENT!JetMove` at `0x1800bc28d`
- `ESENT!JetMove` at `0x1800bc28d`

## string_xrefs

- `0x1800bc29b`: `GetConditionsForExpr:JetMove`

## pseudocode

```c
__int64 __fastcall GetExpressionsForPolicy(JET_SESID sesid, int a2, __int64 a3)
{
  unsigned int v5; // eax
  __int64 result; // rax
  unsigned int Key; // eax
  unsigned int v8; // eax
  unsigned int v9; // edi
  unsigned int v10; // ebx
  void *v11; // rbx
  unsigned int v12; // eax
  int v13; // eax
  int pvData; // [rsp+68h] [rbp+10h] BYREF
  int v15; // [rsp+78h] [rbp+20h] BYREF

  pvData = a2;
  v5 = JetSetCurrentIndexA(sesid, PolicyExpressionTableId, "PolicyExpressionTable_Index2");
  result = PolicyMapJetError(v5, "GetExpressionsForPolicy:JEtSetCUrentIndex");
  if ( !(_DWORD)result )
  {
    v15 = 1;
    while ( 1 )
    {
      Key = JetMakeKey(sesid, PolicyExpressionTableId, &pvData, 4u, 1u);
      result = PolicyMapJetError(Key, "GetExpressionsForPolicy:JEtMakeKey");
      if ( (_DWORD)result )
        return result;
      v8 = JetMakeKey(sesid, PolicyExpressionTableId, &v15, 4u, 0);
      result = PolicyMapJetError(v8, "GetExpressionsForPolicy:JEtMakeKey1");
      if ( (_DWORD)result )
        return result;
      v9 = JetSeek(sesid, PolicyExpressionTableId, 0x21u);
      v10 = PolicyMapJetError(v9, "GetExpressionsForPolicy:JEtSeek");
      if ( v10 )
        break;
      do
      {
        v11 = (void *)MemAlloc(0x18u);
        if ( !v11 )
        {
          v10 = 8;
          goto LABEL_21;
        }
        if ( (unsigned int)GetCurrentExpressionRecord(sesid) )
          MemFree(v11);
        else
          MemArrayAddElement(a3, v11);
        v9 = JetMove(sesid, PolicyExpressionTableId, 1, 0);
        v12 = PolicyMapJetError(v9, "GetConditionsForExpr:JetMove");
      }
      while ( !v12 );
      v10 = 0;
      if ( v9 != -1603 )
        v10 = v12;
      v13 = ++v15;
      if ( v10 )
        goto LABEL_17;
    }
    v13 = v15;
LABEL_17:
    if ( v9 == -1601 )
    {
      if ( v13 != 1 )
        return 0;
      if ( !v10 )
        return v10;
    }
LABEL_21:
    MemArrayFree(a3, MemFree);
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x1800bc14c  mov     [rsp+arg_0], rbx
0x1800bc151  mov     [rsp+pvData], edx
0x1800bc155  push    rbp
0x1800bc156  push    rsi
0x1800bc157  push    rdi
0x1800bc158  sub     rsp, 40h
0x1800bc15c  mov     rdx, cs:PolicyExpressionTableId; tableid
0x1800bc163  mov     rbp, r8
0x1800bc166  lea     r8, aPolicyexpressi_1; "PolicyExpressionTable_Index2"
0x1800bc16d  mov     rsi, rcx
0x1800bc170  call    cs:__imp_JetSetCurrentIndexA
0x1800bc177  nop     dword ptr [rax+rax+00h]
0x1800bc17c  mov     ecx, eax
0x1800bc17e  lea     rdx, aGetexpressions_2; "GetExpressionsForPolicy:JEtSetCUrentInd"...
0x1800bc185  call    PolicyMapJetError
0x1800bc18a  test    eax, eax
0x1800bc18c  jnz     loc_1800BC2FD
0x1800bc192  mov     [rsp+58h+arg_18], 1
0x1800bc19a  mov     rdx, cs:PolicyExpressionTableId; tableid
0x1800bc1a1  lea     r8, [rsp+58h+pvData]; pvData
0x1800bc1a6  mov     r9d, 4; cbData
0x1800bc1ac  mov     [rsp+58h+grbit], 1; grbit
0x1800bc1b4  mov     rcx, rsi; sesid
0x1800bc1b7  call    cs:__imp_JetMakeKey
0x1800bc1be  nop     dword ptr [rax+rax+00h]
0x1800bc1c3  mov     ecx, eax
0x1800bc1c5  lea     rdx, aGetexpressions_5; "GetExpressionsForPolicy:JEtMakeKey"
0x1800bc1cc  call    PolicyMapJetError
0x1800bc1d1  test    eax, eax
0x1800bc1d3  jnz     loc_1800BC2FD
0x1800bc1d9  mov     rdx, cs:PolicyExpressionTableId; tableid
0x1800bc1e0  lea     r9d, [rax+4]; cbData
0x1800bc1e4  lea     r8, [rsp+58h+arg_18]; pvData
0x1800bc1e9  mov     [rsp+58h+grbit], eax; grbit
0x1800bc1ed  mov     rcx, rsi; sesid
0x1800bc1f0  call    cs:__imp_JetMakeKey
0x1800bc1f7  nop     dword ptr [rax+rax+00h]
0x1800bc1fc  mov     ecx, eax
0x1800bc1fe  lea     rdx, aGetexpressions_8; "GetExpressionsForPolicy:JEtMakeKey1"
0x1800bc205  call    PolicyMapJetError
0x1800bc20a  test    eax, eax
0x1800bc20c  jnz     loc_1800BC2FD
0x1800bc212  mov     rdx, cs:PolicyExpressionTableId; tableid
0x1800bc219  lea     r8d, [rax+21h]; grbit
0x1800bc21d  mov     rcx, rsi; sesid
0x1800bc220  call    cs:__imp_JetSeek
0x1800bc227  nop     dword ptr [rax+rax+00h]
0x1800bc22c  mov     ecx, eax
0x1800bc22e  lea     rdx, aGetexpressions_10; "GetExpressionsForPolicy:JEtSeek"
0x1800bc235  mov     edi, eax
0x1800bc237  call    PolicyMapJetError
0x1800bc23c  mov     ebx, eax
0x1800bc23e  test    eax, eax
0x1800bc240  jnz     loc_1800BC2D3
0x1800bc246  mov     ecx, 18h; dwBytes
0x1800bc24b  call    MemAlloc
0x1800bc250  mov     rbx, rax
0x1800bc253  test    rax, rax
0x1800bc256  jz      short loc_1800BC2CC
0x1800bc258  mov     rdx, rax
0x1800bc25b  mov     rcx, rsi; sesid
0x1800bc25e  call    GetCurrentExpressionRecord
0x1800bc263  test    eax, eax
0x1800bc265  jnz     short loc_1800BC274
0x1800bc267  mov     rdx, rbx
0x1800bc26a  mov     rcx, rbp
0x1800bc26d  call    MemArrayAddElement
0x1800bc272  jmp     short loc_1800BC27C
0x1800bc274  mov     rcx, rbx; lpMem
0x1800bc277  call    MemFree
0x1800bc27c  mov     rdx, cs:PolicyExpressionTableId; tableid
0x1800bc283  xor     r9d, r9d; grbit
0x1800bc286  mov     rcx, rsi; sesid
0x1800bc289  lea     r8d, [r9+1]; cRow
0x1800bc28d  call    cs:__imp_JetMove
0x1800bc294  nop     dword ptr [rax+rax+00h]
0x1800bc299  mov     ecx, eax
0x1800bc29b  lea     rdx, aGetconditionsf_2; "GetConditionsForExpr:JetMove"
0x1800bc2a2  mov     edi, eax
0x1800bc2a4  call    PolicyMapJetError
0x1800bc2a9  test    eax, eax
0x1800bc2ab  jz      short loc_1800BC246
0x1800bc2ad  xor     ebx, ebx
0x1800bc2af  cmp     edi, 0FFFFF9BDh
0x1800bc2b5  cmovnz  ebx, eax
0x1800bc2b8  mov     eax, [rsp+58h+arg_18]
0x1800bc2bc  inc     eax
0x1800bc2be  mov     [rsp+58h+arg_18], eax
0x1800bc2c2  test    ebx, ebx
0x1800bc2c4  jz      loc_1800BC19A
0x1800bc2ca  jmp     short loc_1800BC2D7
0x1800bc2cc  mov     ebx, 8
0x1800bc2d1  jmp     short loc_1800BC2EC
0x1800bc2d3  mov     eax, [rsp+58h+arg_18]
0x1800bc2d7  cmp     edi, 0FFFFF9BFh
0x1800bc2dd  jnz     short loc_1800BC2EC
0x1800bc2df  cmp     eax, 1
0x1800bc2e2  jz      short loc_1800BC2E8
0x1800bc2e4  xor     ebx, ebx
0x1800bc2e6  jmp     short loc_1800BC2FB
0x1800bc2e8  test    ebx, ebx
0x1800bc2ea  jz      short loc_1800BC2FB
0x1800bc2ec  lea     rdx, MemFree
0x1800bc2f3  mov     rcx, rbp
0x1800bc2f6  call    MemArrayFree
0x1800bc2fb  mov     eax, ebx
0x1800bc2fd  mov     rbx, [rsp+58h+arg_0]
0x1800bc302  add     rsp, 40h
0x1800bc306  pop     rdi
0x1800bc307  pop     rsi
0x1800bc308  pop     rbp
0x1800bc309  retn
```
