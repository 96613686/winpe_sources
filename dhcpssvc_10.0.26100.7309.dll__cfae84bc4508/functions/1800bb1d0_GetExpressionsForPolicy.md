# GetExpressionsForPolicy

- ea: `0x1800bb1d0`
- end: `0x1800bb38f`
- name: `GetExpressionsForPolicy`
- size: `447`
- prototype: `__int64 __fastcall(JET_SESID sesid)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180088890`
- `0x1800bb8d8`

## callees

- `0x1800947e4`
- `0x18009602c`
- `0x180096080`
- `0x1800983b4`
- `0x1800bacbc`
- `0x1800bb1d0`
- `0x1800bba04`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800bb1f4`
- `ESENT!JetSetCurrentIndexA` at `0x1800bb1f4`
- `ESENT!JetMakeKey` at `0x1800bb23b`
- `ESENT!JetMakeKey` at `0x1800bb274`
- `ESENT!JetMakeKey` at `0x1800bb23b`
- `ESENT!JetMakeKey` at `0x1800bb274`
- `ESENT!JetSeek` at `0x1800bb2a4`
- `ESENT!JetSeek` at `0x1800bb2a4`
- `ESENT!JetMove` at `0x1800bb311`
- `ESENT!JetMove` at `0x1800bb311`

## string_xrefs

- `0x1800bb31f`: `GetConditionsForExpr:JetMove`

## pseudocode

```c
__int64 __fastcall GetExpressionsForPolicy(JET_SESID sesid, int a2, unsigned int *a3)
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
          MemArrayAddElement(a3, (__int64)v11);
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
0x1800bb1d0  mov     [rsp+arg_0], rbx
0x1800bb1d5  mov     [rsp+pvData], edx
0x1800bb1d9  push    rbp
0x1800bb1da  push    rsi
0x1800bb1db  push    rdi
0x1800bb1dc  sub     rsp, 40h
0x1800bb1e0  mov     rdx, cs:PolicyExpressionTableId; tableid
0x1800bb1e7  mov     rbp, r8
0x1800bb1ea  lea     r8, aPolicyexpressi_1; "PolicyExpressionTable_Index2"
0x1800bb1f1  mov     rsi, rcx
0x1800bb1f4  call    cs:__imp_JetSetCurrentIndexA
0x1800bb1fb  nop     dword ptr [rax+rax+00h]
0x1800bb200  mov     ecx, eax
0x1800bb202  lea     rdx, aGetexpressions_2; "GetExpressionsForPolicy:JEtSetCUrentInd"...
0x1800bb209  call    PolicyMapJetError
0x1800bb20e  test    eax, eax
0x1800bb210  jnz     loc_1800BB381
0x1800bb216  mov     [rsp+58h+arg_18], 1
0x1800bb21e  mov     rdx, cs:PolicyExpressionTableId; tableid
0x1800bb225  lea     r8, [rsp+58h+pvData]; pvData
0x1800bb22a  mov     r9d, 4; cbData
0x1800bb230  mov     [rsp+58h+grbit], 1; grbit
0x1800bb238  mov     rcx, rsi; sesid
0x1800bb23b  call    cs:__imp_JetMakeKey
0x1800bb242  nop     dword ptr [rax+rax+00h]
0x1800bb247  mov     ecx, eax
0x1800bb249  lea     rdx, aGetexpressions_5; "GetExpressionsForPolicy:JEtMakeKey"
0x1800bb250  call    PolicyMapJetError
0x1800bb255  test    eax, eax
0x1800bb257  jnz     loc_1800BB381
0x1800bb25d  mov     rdx, cs:PolicyExpressionTableId; tableid
0x1800bb264  lea     r9d, [rax+4]; cbData
0x1800bb268  and     [rsp+58h+grbit], eax
0x1800bb26c  lea     r8, [rsp+58h+arg_18]; pvData
0x1800bb271  mov     rcx, rsi; sesid
0x1800bb274  call    cs:__imp_JetMakeKey
0x1800bb27b  nop     dword ptr [rax+rax+00h]
0x1800bb280  mov     ecx, eax
0x1800bb282  lea     rdx, aGetexpressions_8; "GetExpressionsForPolicy:JEtMakeKey1"
0x1800bb289  call    PolicyMapJetError
0x1800bb28e  test    eax, eax
0x1800bb290  jnz     loc_1800BB381
0x1800bb296  mov     rdx, cs:PolicyExpressionTableId; tableid
0x1800bb29d  lea     r8d, [rax+21h]; grbit
0x1800bb2a1  mov     rcx, rsi; sesid
0x1800bb2a4  call    cs:__imp_JetSeek
0x1800bb2ab  nop     dword ptr [rax+rax+00h]
0x1800bb2b0  mov     ecx, eax
0x1800bb2b2  lea     rdx, aGetexpressions_10; "GetExpressionsForPolicy:JEtSeek"
0x1800bb2b9  mov     edi, eax
0x1800bb2bb  call    PolicyMapJetError
0x1800bb2c0  mov     ebx, eax
0x1800bb2c2  test    eax, eax
0x1800bb2c4  jnz     loc_1800BB357
0x1800bb2ca  mov     ecx, 18h; dwBytes
0x1800bb2cf  call    MemAlloc
0x1800bb2d4  mov     rbx, rax
0x1800bb2d7  test    rax, rax
0x1800bb2da  jz      short loc_1800BB350
0x1800bb2dc  mov     rdx, rax
0x1800bb2df  mov     rcx, rsi; sesid
0x1800bb2e2  call    GetCurrentExpressionRecord
0x1800bb2e7  test    eax, eax
0x1800bb2e9  jnz     short loc_1800BB2F8
0x1800bb2eb  mov     rdx, rbx
0x1800bb2ee  mov     rcx, rbp
0x1800bb2f1  call    MemArrayAddElement
0x1800bb2f6  jmp     short loc_1800BB300
0x1800bb2f8  mov     rcx, rbx; lpMem
0x1800bb2fb  call    MemFree
0x1800bb300  mov     rdx, cs:PolicyExpressionTableId; tableid
0x1800bb307  xor     r9d, r9d; grbit
0x1800bb30a  mov     rcx, rsi; sesid
0x1800bb30d  lea     r8d, [r9+1]; cRow
0x1800bb311  call    cs:__imp_JetMove
0x1800bb318  nop     dword ptr [rax+rax+00h]
0x1800bb31d  mov     ecx, eax
0x1800bb31f  lea     rdx, aGetconditionsf_2; "GetConditionsForExpr:JetMove"
0x1800bb326  mov     edi, eax
0x1800bb328  call    PolicyMapJetError
0x1800bb32d  test    eax, eax
0x1800bb32f  jz      short loc_1800BB2CA
0x1800bb331  xor     ebx, ebx
0x1800bb333  cmp     edi, 0FFFFF9BDh
0x1800bb339  cmovnz  ebx, eax
0x1800bb33c  mov     eax, [rsp+58h+arg_18]
0x1800bb340  inc     eax
0x1800bb342  mov     [rsp+58h+arg_18], eax
0x1800bb346  test    ebx, ebx
0x1800bb348  jz      loc_1800BB21E
0x1800bb34e  jmp     short loc_1800BB35B
0x1800bb350  mov     ebx, 8
0x1800bb355  jmp     short loc_1800BB370
0x1800bb357  mov     eax, [rsp+58h+arg_18]
0x1800bb35b  cmp     edi, 0FFFFF9BFh
0x1800bb361  jnz     short loc_1800BB370
0x1800bb363  cmp     eax, 1
0x1800bb366  jz      short loc_1800BB36C
0x1800bb368  xor     ebx, ebx
0x1800bb36a  jmp     short loc_1800BB37F
0x1800bb36c  test    ebx, ebx
0x1800bb36e  jz      short loc_1800BB37F
0x1800bb370  lea     rdx, MemFree
0x1800bb377  mov     rcx, rbp
0x1800bb37a  call    MemArrayFree
0x1800bb37f  mov     eax, ebx
0x1800bb381  mov     rbx, [rsp+58h+arg_0]
0x1800bb386  add     rsp, 40h
0x1800bb38a  pop     rdi
0x1800bb38b  pop     rsi
0x1800bb38c  pop     rbp
0x1800bb38d  retn
```
