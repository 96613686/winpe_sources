# GetConditionsForExprs

- ea: `0x1800ba840`
- end: `0x1800baa77`
- name: `GetConditionsForExprs`
- size: `567`
- prototype: `__int64 __fastcall(JET_SESID sesid)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180088890`
- `0x1800bb8d8`

## callees

- `0x1800947e4`
- `0x18009602c`
- `0x180096080`
- `0x1800983b4`
- `0x1800ba840`
- `0x1800baa80`
- `0x1800bb890`
- `0x1800bba04`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800ba8ab`
- `ESENT!JetSetCurrentIndexA` at `0x1800ba8ab`
- `ESENT!JetMakeKey` at `0x1800ba8e9`
- `ESENT!JetMakeKey` at `0x1800ba8e9`
- `ESENT!JetSeek` at `0x1800ba91b`
- `ESENT!JetSeek` at `0x1800ba91b`
- `ESENT!JetMove` at `0x1800ba9a6`
- `ESENT!JetMove` at `0x1800ba9a6`

## string_xrefs

- `0x1800ba9b4`: `GetConditionsForExpr:JetMove`

## pseudocode

```c
__int64 __fastcall GetConditionsForExprs(JET_SESID sesid, _DWORD *a2, unsigned int a3, __int64 a4)
{
  int *v5; // rax
  unsigned int v7; // edi
  unsigned int v8; // r12d
  int v9; // eax
  unsigned int v10; // r15d
  _QWORD *v11; // r14
  unsigned int v12; // eax
  unsigned int Key; // eax
  unsigned int v14; // ebx
  unsigned int v15; // eax
  _DWORD *v16; // rbx
  unsigned int v17; // r14d
  __int64 i; // rbx
  __int64 v20; // [rsp+30h] [rbp-10h] BYREF
  _QWORD *v21; // [rsp+38h] [rbp-8h]
  _DWORD *v22; // [rsp+88h] [rbp+48h]
  int pvData; // [rsp+98h] [rbp+58h] BYREF

  v22 = a2;
  v5 = a2;
  v7 = 0;
  if ( a4 )
  {
    *(_QWORD *)a4 = 0;
    *(_QWORD *)(a4 + 8) = 0;
  }
  v8 = 0;
  if ( a3 )
  {
    while ( 1 )
    {
      v9 = *v5;
      v20 = 0;
      v10 = 0;
      pvData = v9;
      v11 = 0;
      v21 = 0;
      v12 = JetSetCurrentIndexA(sesid, PolicyConditionTableId, "PolicyConditionTable_Index5");
      v7 = PolicyMapJetError(v12, "GetConditionsForexpr:JEtSetCUrentIndex");
      if ( v7 )
        break;
      Key = JetMakeKey(sesid, PolicyConditionTableId, &pvData, 4u, 1u);
      v7 = PolicyMapJetError(Key, "GetConditionsForExpr:JEtMakeKey");
      if ( v7 )
        break;
      v14 = JetSeek(sesid, PolicyConditionTableId, 0x21u);
      v15 = PolicyMapJetError(v14, "GetConditionsForExpr:JEtSeek");
      v7 = v15;
      if ( v14 == -1601 )
      {
        v7 = 0;
      }
      else
      {
        if ( v15 )
          break;
        do
        {
          v16 = (_DWORD *)MemAlloc(0x28u);
          if ( !v16 )
          {
            v7 = 8;
            goto LABEL_18;
          }
          v16[9] = pvData;
          if ( (unsigned int)GetCurrentConditionRecord(sesid) )
          {
            MemConditionTableRecordFree(v16);
            v16 = 0;
          }
          else
          {
            v7 = MemArrayAddElement((unsigned int *)&v20, (__int64)v16);
            if ( v7 )
              goto LABEL_18;
          }
          v17 = JetMove(sesid, PolicyConditionTableId, 1, 0);
          v7 = PolicyMapJetError(v17, "GetConditionsForExpr:JetMove");
        }
        while ( !v7 );
        if ( v17 == -1603 )
        {
          v7 = 0;
          goto LABEL_19;
        }
LABEL_18:
        MemConditionTableRecordFree(v16);
        MemArrayFree(&v20, MemConditionTableRecordFree);
LABEL_19:
        v10 = v20;
        v11 = v21;
      }
      if ( v7 )
        break;
      for ( i = 0; (unsigned int)i < v10; i = (unsigned int)(i + 1) )
        MemArrayAddElement((unsigned int *)a4, v11[i]);
      if ( v11 )
        MemFree(v11);
      ++v8;
      v5 = v22 + 1;
      v20 = 0;
      v7 = 0;
      v21 = 0;
      ++v22;
      if ( v8 >= a3 )
        return v7;
    }
    MemArrayFree(a4, MemConditionTableRecordFree);
  }
  return v7;
}

```

## disassembly

```asm
0x1800ba840  mov     [rsp-38h+arg_0], rbx
0x1800ba845  mov     [rsp-38h+arg_10], r8d
0x1800ba84a  mov     [rsp-38h+arg_8], rdx
0x1800ba84f  push    rbp
0x1800ba850  push    rsi
0x1800ba851  push    rdi
0x1800ba852  push    r12
0x1800ba854  push    r13
0x1800ba856  push    r14
0x1800ba858  push    r15
0x1800ba85a  mov     rbp, rsp
0x1800ba85d  sub     rsp, 40h
0x1800ba861  xor     ebx, ebx
0x1800ba863  mov     rsi, r9
0x1800ba866  mov     rax, rdx
0x1800ba869  mov     r13, rcx
0x1800ba86c  mov     edi, ebx
0x1800ba86e  test    r9, r9
0x1800ba871  jz      short loc_1800BA87A
0x1800ba873  mov     [r9], rbx
0x1800ba876  mov     [r9+8], rbx
0x1800ba87a  mov     r12d, ebx
0x1800ba87d  test    r8d, r8d
0x1800ba880  jz      loc_1800BAA5C
0x1800ba886  mov     eax, [rax]
0x1800ba888  lea     r8, aPolicyconditio_6; "PolicyConditionTable_Index5"
0x1800ba88f  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800ba896  mov     rcx, r13; sesid
0x1800ba899  and     [rbp+var_10], 0
0x1800ba89e  mov     r15d, ebx
0x1800ba8a1  mov     [rbp+pvData], eax
0x1800ba8a4  mov     r14, rbx
0x1800ba8a7  mov     [rbp+var_8], rbx
0x1800ba8ab  call    cs:__imp_JetSetCurrentIndexA
0x1800ba8b2  nop     dword ptr [rax+rax+00h]
0x1800ba8b7  mov     ecx, eax
0x1800ba8b9  lea     rdx, aGetconditionsf_0; "GetConditionsForexpr:JEtSetCUrentIndex"
0x1800ba8c0  call    PolicyMapJetError
0x1800ba8c5  mov     edi, eax
0x1800ba8c7  test    eax, eax
0x1800ba8c9  jnz     loc_1800BAA4D
0x1800ba8cf  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800ba8d6  lea     r9d, [rax+4]; cbData
0x1800ba8da  lea     r8, [rbp+pvData]; pvData
0x1800ba8de  mov     [rsp+40h+grbit], 1; grbit
0x1800ba8e6  mov     rcx, r13; sesid
0x1800ba8e9  call    cs:__imp_JetMakeKey
0x1800ba8f0  nop     dword ptr [rax+rax+00h]
0x1800ba8f5  mov     ecx, eax
0x1800ba8f7  lea     rdx, aGetconditionsf_1; "GetConditionsForExpr:JEtMakeKey"
0x1800ba8fe  call    PolicyMapJetError
0x1800ba903  mov     edi, eax
0x1800ba905  test    eax, eax
0x1800ba907  jnz     loc_1800BAA4D
0x1800ba90d  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800ba914  lea     r8d, [rax+21h]; grbit
0x1800ba918  mov     rcx, r13; sesid
0x1800ba91b  call    cs:__imp_JetSeek
0x1800ba922  nop     dword ptr [rax+rax+00h]
0x1800ba927  mov     ecx, eax
0x1800ba929  lea     rdx, aGetconditionsf; "GetConditionsForExpr:JEtSeek"
0x1800ba930  mov     ebx, eax
0x1800ba932  call    PolicyMapJetError
0x1800ba937  mov     edi, eax
0x1800ba939  cmp     ebx, 0FFFFF9BFh
0x1800ba93f  jnz     short loc_1800BA948
0x1800ba941  xor     edi, edi
0x1800ba943  jmp     loc_1800BA9FB
0x1800ba948  test    eax, eax
0x1800ba94a  jnz     loc_1800BAA4D
0x1800ba950  mov     ecx, 28h ; '('; dwBytes
0x1800ba955  call    MemAlloc
0x1800ba95a  mov     rbx, rax
0x1800ba95d  test    rax, rax
0x1800ba960  jz      short loc_1800BA9D6
0x1800ba962  mov     eax, [rbp+pvData]
0x1800ba965  mov     rdx, rbx
0x1800ba968  mov     rcx, r13; sesid
0x1800ba96b  mov     [rbx+24h], eax
0x1800ba96e  call    GetCurrentConditionRecord
0x1800ba973  test    eax, eax
0x1800ba975  jnz     short loc_1800BA98B
0x1800ba977  mov     rdx, rbx
0x1800ba97a  lea     rcx, [rbp+var_10]
0x1800ba97e  call    MemArrayAddElement
0x1800ba983  mov     edi, eax
0x1800ba985  test    eax, eax
0x1800ba987  jnz     short loc_1800BA9DB
0x1800ba989  jmp     short loc_1800BA995
0x1800ba98b  mov     rcx, rbx; lpMem
0x1800ba98e  call    MemConditionTableRecordFree
0x1800ba993  xor     ebx, ebx
0x1800ba995  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800ba99c  xor     r9d, r9d; grbit
0x1800ba99f  mov     rcx, r13; sesid
0x1800ba9a2  lea     r8d, [r9+1]; cRow
0x1800ba9a6  call    cs:__imp_JetMove
0x1800ba9ad  nop     dword ptr [rax+rax+00h]
0x1800ba9b2  mov     ecx, eax
0x1800ba9b4  lea     rdx, aGetconditionsf_2; "GetConditionsForExpr:JetMove"
0x1800ba9bb  mov     r14d, eax
0x1800ba9be  call    PolicyMapJetError
0x1800ba9c3  mov     edi, eax
0x1800ba9c5  test    eax, eax
0x1800ba9c7  jz      short loc_1800BA950
0x1800ba9c9  cmp     r14d, 0FFFFF9BDh
0x1800ba9d0  jnz     short loc_1800BA9DB
0x1800ba9d2  xor     edi, edi
0x1800ba9d4  jmp     short loc_1800BA9F3
0x1800ba9d6  mov     edi, 8
0x1800ba9db  mov     rcx, rbx; lpMem
0x1800ba9de  call    MemConditionTableRecordFree
0x1800ba9e3  lea     rdx, MemConditionTableRecordFree
0x1800ba9ea  lea     rcx, [rbp+var_10]
0x1800ba9ee  call    MemArrayFree
0x1800ba9f3  mov     r15d, dword ptr [rbp+var_10]
0x1800ba9f7  mov     r14, [rbp+var_8]
0x1800ba9fb  test    edi, edi
0x1800ba9fd  jnz     short loc_1800BAA4D
0x1800ba9ff  xor     ebx, ebx
0x1800baa01  test    r15d, r15d
0x1800baa04  jz      short loc_1800BAA19
0x1800baa06  mov     rdx, [r14+rbx*8]
0x1800baa0a  mov     rcx, rsi
0x1800baa0d  call    MemArrayAddElement
0x1800baa12  inc     ebx
0x1800baa14  cmp     ebx, r15d
0x1800baa17  jb      short loc_1800BAA06
0x1800baa19  xor     ebx, ebx
0x1800baa1b  test    r14, r14
0x1800baa1e  jz      short loc_1800BAA28
0x1800baa20  mov     rcx, r14; lpMem
0x1800baa23  call    MemFree
0x1800baa28  mov     rax, [rbp+arg_8]
0x1800baa2c  inc     r12d
0x1800baa2f  add     rax, 4
0x1800baa33  mov     [rbp+var_10], rbx
0x1800baa37  mov     edi, ebx
0x1800baa39  mov     [rbp+var_8], rbx
0x1800baa3d  mov     [rbp+arg_8], rax
0x1800baa41  cmp     r12d, [rbp+arg_10]
0x1800baa45  jb      loc_1800BA886
0x1800baa4b  jmp     short loc_1800BAA5C
0x1800baa4d  lea     rdx, MemConditionTableRecordFree
0x1800baa54  mov     rcx, rsi
0x1800baa57  call    MemArrayFree
0x1800baa5c  mov     rbx, [rsp+40h+arg_0]
0x1800baa64  mov     eax, edi
0x1800baa66  add     rsp, 40h
0x1800baa6a  pop     r15
0x1800baa6c  pop     r14
0x1800baa6e  pop     r13
0x1800baa70  pop     r12
0x1800baa72  pop     rdi
0x1800baa73  pop     rsi
0x1800baa74  pop     rbp
0x1800baa75  retn
```
