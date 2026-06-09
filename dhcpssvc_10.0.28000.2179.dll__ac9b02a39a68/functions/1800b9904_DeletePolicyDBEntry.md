# DeletePolicyDBEntry

- ea: `0x1800b9904`
- end: `0x1800b9b94`
- name: `DeletePolicyDBEntry`
- size: `656`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180088260`

## callees

- `0x180096254`
- `0x1800b934c`
- `0x1800b9904`
- `0x1800bc314`
- `0x1800bc990`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800b996b`
- `ESENT!JetSetCurrentIndexA` at `0x1800b996b`
- `ESENT!JetRetrieveColumns` at `0x1800b9a8a`
- `ESENT!JetRetrieveColumns` at `0x1800b9b01`
- `ESENT!JetRetrieveColumns` at `0x1800b9a8a`
- `ESENT!JetRetrieveColumns` at `0x1800b9b01`
- `ESENT!JetMakeKey` at `0x1800b99aa`
- `ESENT!JetMakeKey` at `0x1800b99aa`
- `ESENT!JetSeek` at `0x1800b99d9`
- `ESENT!JetSeek` at `0x1800b99d9`
- `ESENT!JetDelete` at `0x1800b9b30`
- `ESENT!JetDelete` at `0x1800b9b30`
- `ESENT!JetRetrieveColumn` at `0x1800b9a2b`
- `ESENT!JetRetrieveColumn` at `0x1800b9a2b`

## string_xrefs

- `0x1800b99e7`: `DeletePolicyDBEntry:JetSeek`
- `0x1800b99b8`: `DeletePolicyDBEntry:JetMakeKey`
- `0x1800b9979`: `DeletePolicyDBEntry:JetSetCurrentIndex`
- `0x1800b9b3e`: `DeletePolicyDBentry:JetDelete`
- `0x1800b9b0f`: `DeletePolicyDBentry:JetRetrieveColumns2`
- `0x1800b9a98`: `DeletePolicyDBentry:JetRetrieveColumns1`
- `0x1800b9a39`: `DeletePolicyDBentry:JetRetrieveColumn`

## pseudocode

```c
__int64 __fastcall DeletePolicyDBEntry(__int64 a1, int a2, __int64 a3, __int64 *a4, unsigned int *a5)
{
  JET_SESID v5; // rdi
  __int64 result; // rax
  unsigned int v8; // eax
  unsigned int Key; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int itagSequence; // esi
  SIZE_T v14; // rcx
  __int64 v15; // rax
  unsigned int v16; // ebx
  __int64 v17; // rax
  unsigned int v18; // eax
  unsigned int v19; // eax
  JET_RETRIEVECOLUMN pretrievecolumn; // [rsp+48h] [rbp-38h] BYREF
  int v21; // [rsp+B0h] [rbp+30h] BYREF
  int v22; // [rsp+B4h] [rbp+34h]
  int pvData; // [rsp+B8h] [rbp+38h] BYREF

  pvData = a2;
  v22 = HIDWORD(a1);
  v5 = DhcpGlobalJetServerSession;
  v21 = 0;
  result = GetMaxProcessingOrderForSubnet(DhcpGlobalJetServerSession);
  if ( !(_DWORD)result )
  {
    v8 = JetSetCurrentIndexA(v5, PolicyTableId, "PolicyTable_Index1");
    result = PolicyMapJetError(v8, "DeletePolicyDBEntry:JetSetCurrentIndex");
    if ( !(_DWORD)result )
    {
      Key = JetMakeKey(v5, PolicyTableId, &pvData, 4u, 1u);
      result = PolicyMapJetError(Key, "DeletePolicyDBEntry:JetMakeKey");
      if ( !(_DWORD)result )
      {
        v10 = JetSeek(v5, PolicyTableId, 1u);
        result = PolicyMapJetError(v10, "DeletePolicyDBEntry:JetSeek");
        if ( !(_DWORD)result )
        {
          v11 = JetRetrieveColumn(v5, PolicyTableId, dword_1800F97E8, &v21, 4u, 0, 1u, 0);
          result = PolicyMapJetError(v11, "DeletePolicyDBentry:JetRetrieveColumn");
          if ( !(_DWORD)result )
          {
            pretrievecolumn.columnid = dword_1800F9830;
            *(_QWORD *)&pretrievecolumn.columnidNextTagged = 0;
            *(_QWORD *)&pretrievecolumn.grbit = 1;
            *(_QWORD *)&pretrievecolumn.cbData = 0;
            pretrievecolumn.itagSequence = 0;
            pretrievecolumn.pvData = 0;
            v12 = JetRetrieveColumns(v5, PolicyTableId, &pretrievecolumn, 1u);
            result = PolicyMapJetError(v12, "DeletePolicyDBentry:JetRetrieveColumns1");
            if ( !(_DWORD)result )
            {
              itagSequence = pretrievecolumn.itagSequence;
              v14 = 4LL * pretrievecolumn.itagSequence;
              *a5 = pretrievecolumn.itagSequence;
              v15 = MemAlloc(v14);
              *a4 = v15;
              if ( v15 )
              {
                v16 = 1;
                if ( itagSequence )
                {
                  while ( 1 )
                  {
                    v17 = *a4;
                    pretrievecolumn.itagSequence = v16;
                    pretrievecolumn.cbData = 4;
                    pretrievecolumn.pvData = (void *)(v17 + 4LL * (v16 - 1));
                    v18 = JetRetrieveColumns(v5, PolicyTableId, &pretrievecolumn, 1u);
                    result = PolicyMapJetError(v18, "DeletePolicyDBentry:JetRetrieveColumns2");
                    if ( (_DWORD)result )
                      break;
                    if ( ++v16 > itagSequence )
                      goto LABEL_12;
                  }
                }
                else
                {
LABEL_12:
                  v19 = JetDelete(v5, PolicyTableId);
                  result = PolicyMapJetError(v19, "DeletePolicyDBentry:JetDelete");
                  if ( !(_DWORD)result )
                    return 0;
                }
              }
              else
              {
                return 8;
              }
            }
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
0x1800b9904  mov     rax, rsp
0x1800b9907  mov     [rax+18h], rbx
0x1800b990b  mov     [rax+20h], rsi
0x1800b990f  mov     [rax+10h], edx
0x1800b9912  mov     [rax+8], rcx
0x1800b9916  push    rbp
0x1800b9917  push    rdi
0x1800b9918  push    r13
0x1800b991a  push    r14
0x1800b991c  push    r15
0x1800b991e  mov     rbp, rsp
0x1800b9921  sub     rsp, 80h
0x1800b9928  mov     rdi, cs:DhcpGlobalJetServerSession
0x1800b992f  mov     r14d, r8d
0x1800b9932  mov     edx, r14d
0x1800b9935  mov     [rbp+arg_0], 0
0x1800b993c  mov     rcx, rdi; sesid
0x1800b993f  mov     [rbp+var_40], 0
0x1800b9946  lea     r8, [rbp+var_40]
0x1800b994a  mov     r15, r9
0x1800b994d  call    GetMaxProcessingOrderForSubnet
0x1800b9952  test    eax, eax
0x1800b9954  jnz     loc_1800B9B77
0x1800b995a  mov     rdx, cs:PolicyTableId; tableid
0x1800b9961  lea     r8, aPolicytableInd_1; "PolicyTable_Index1"
0x1800b9968  mov     rcx, rdi; sesid
0x1800b996b  call    cs:__imp_JetSetCurrentIndexA
0x1800b9972  nop     dword ptr [rax+rax+00h]
0x1800b9977  mov     ecx, eax
0x1800b9979  lea     rdx, aDeletepolicydb_4; "DeletePolicyDBEntry:JetSetCurrentIndex"
0x1800b9980  call    PolicyMapJetError
0x1800b9985  test    eax, eax
0x1800b9987  jnz     loc_1800B9B77
0x1800b998d  mov     rdx, cs:PolicyTableId; tableid
0x1800b9994  lea     ebx, [rax+4]
0x1800b9997  lea     r13d, [rax+1]
0x1800b999b  mov     r9d, ebx; cbData
0x1800b999e  lea     r8, [rbp+pvData]; pvData
0x1800b99a2  mov     [rsp+80h+grbit], r13d; grbit
0x1800b99a7  mov     rcx, rdi; sesid
0x1800b99aa  call    cs:__imp_JetMakeKey
0x1800b99b1  nop     dword ptr [rax+rax+00h]
0x1800b99b6  mov     ecx, eax
0x1800b99b8  lea     rdx, aDeletepolicydb_3; "DeletePolicyDBEntry:JetMakeKey"
0x1800b99bf  call    PolicyMapJetError
0x1800b99c4  test    eax, eax
0x1800b99c6  jnz     loc_1800B9B77
0x1800b99cc  mov     rdx, cs:PolicyTableId; tableid
0x1800b99d3  mov     r8d, r13d; grbit
0x1800b99d6  mov     rcx, rdi; sesid
0x1800b99d9  call    cs:__imp_JetSeek
0x1800b99e0  nop     dword ptr [rax+rax+00h]
0x1800b99e5  mov     ecx, eax
0x1800b99e7  lea     rdx, aDeletepolicydb_5; "DeletePolicyDBEntry:JetSeek"
0x1800b99ee  call    PolicyMapJetError
0x1800b99f3  test    eax, eax
0x1800b99f5  jnz     loc_1800B9B77
0x1800b99fb  mov     r8d, cs:dword_1800F97E8; columnid
0x1800b9a02  lea     r9, [rbp+arg_0]; pvData
0x1800b9a06  mov     rdx, cs:PolicyTableId; tableid
0x1800b9a0d  mov     rcx, rdi; sesid
0x1800b9a10  mov     [rsp+80h+pretinfo], 0; pretinfo
0x1800b9a19  mov     [rsp+80h+var_50], r13d; grbit
0x1800b9a1e  mov     [rsp+80h+pcbActual], 0; pcbActual
0x1800b9a27  mov     [rsp+80h+grbit], ebx; cbData
0x1800b9a2b  call    cs:__imp_JetRetrieveColumn
0x1800b9a32  nop     dword ptr [rax+rax+00h]
0x1800b9a37  mov     ecx, eax
0x1800b9a39  lea     rdx, aDeletepolicydb; "DeletePolicyDBentry:JetRetrieveColumn"
0x1800b9a40  call    PolicyMapJetError
0x1800b9a45  test    eax, eax
0x1800b9a47  jnz     loc_1800B9B77
0x1800b9a4d  mov     eax, cs:dword_1800F9830
0x1800b9a53  lea     r8, [rbp+pretrievecolumn]; pretrievecolumn
0x1800b9a57  mov     rdx, cs:PolicyTableId; tableid
0x1800b9a5e  mov     r9d, r13d; cretrievecolumn
0x1800b9a61  mov     rcx, rdi; sesid
0x1800b9a64  mov     [rbp+pretrievecolumn.columnid], eax
0x1800b9a67  mov     qword ptr [rbp+pretrievecolumn.columnidNextTagged], 0
0x1800b9a6f  mov     qword ptr [rbp+pretrievecolumn.grbit], r13
0x1800b9a73  mov     qword ptr [rbp+pretrievecolumn.cbData], 0
0x1800b9a7b  mov     [rbp+pretrievecolumn.itagSequence], 0
0x1800b9a82  mov     [rbp+pretrievecolumn.pvData], 0
0x1800b9a8a  call    cs:__imp_JetRetrieveColumns
0x1800b9a91  nop     dword ptr [rax+rax+00h]
0x1800b9a96  mov     ecx, eax
0x1800b9a98  lea     rdx, aDeletepolicydb_0; "DeletePolicyDBentry:JetRetrieveColumns1"
0x1800b9a9f  call    PolicyMapJetError
0x1800b9aa4  test    eax, eax
0x1800b9aa6  jnz     loc_1800B9B77
0x1800b9aac  mov     esi, [rbp+pretrievecolumn.itagSequence]
0x1800b9aaf  mov     rax, [rbp+arg_20]
0x1800b9ab3  mov     ecx, esi
0x1800b9ab5  shl     rcx, 2; dwBytes
0x1800b9ab9  mov     [rax], esi
0x1800b9abb  call    MemAlloc
0x1800b9ac0  mov     [r15], rax
0x1800b9ac3  test    rax, rax
0x1800b9ac6  jnz     short loc_1800B9AD0
0x1800b9ac8  lea     eax, [rbx+4]
0x1800b9acb  jmp     loc_1800B9B77
0x1800b9ad0  mov     ebx, r13d
0x1800b9ad3  cmp     esi, r13d
0x1800b9ad6  jb      short loc_1800B9B26
0x1800b9ad8  mov     rax, [r15]
0x1800b9adb  lea     ecx, [rbx-1]
0x1800b9ade  mov     rdx, cs:PolicyTableId; tableid
0x1800b9ae5  lea     r8, [rbp+pretrievecolumn]; pretrievecolumn
0x1800b9ae9  mov     r9d, r13d; cretrievecolumn
0x1800b9aec  mov     [rbp+pretrievecolumn.itagSequence], ebx
0x1800b9aef  mov     [rbp+pretrievecolumn.cbData], 4
0x1800b9af6  lea     rcx, [rax+rcx*4]
0x1800b9afa  mov     [rbp+pretrievecolumn.pvData], rcx
0x1800b9afe  mov     rcx, rdi; sesid
0x1800b9b01  call    cs:__imp_JetRetrieveColumns
0x1800b9b08  nop     dword ptr [rax+rax+00h]
0x1800b9b0d  mov     ecx, eax
0x1800b9b0f  lea     rdx, aDeletepolicydb_1; "DeletePolicyDBentry:JetRetrieveColumns2"
0x1800b9b16  call    PolicyMapJetError
0x1800b9b1b  test    eax, eax
0x1800b9b1d  jnz     short loc_1800B9B77
0x1800b9b1f  add     ebx, r13d
0x1800b9b22  cmp     ebx, esi
0x1800b9b24  jbe     short loc_1800B9AD8
0x1800b9b26  mov     rdx, cs:PolicyTableId; tableid
0x1800b9b2d  mov     rcx, rdi; sesid
0x1800b9b30  call    cs:__imp_JetDelete
0x1800b9b37  nop     dword ptr [rax+rax+00h]
0x1800b9b3c  mov     ecx, eax
0x1800b9b3e  lea     rdx, aDeletepolicydb_2; "DeletePolicyDBentry:JetDelete"
0x1800b9b45  call    PolicyMapJetError
0x1800b9b4a  test    eax, eax
0x1800b9b4c  jnz     short loc_1800B9B77
0x1800b9b4e  mov     ebx, [rbp+arg_0]
0x1800b9b51  mov     esi, [rbp+var_40]
0x1800b9b54  cmp     ebx, esi
0x1800b9b56  jnb     short loc_1800B9B75
0x1800b9b58  inc     ebx
0x1800b9b5a  jmp     short loc_1800B9B71
0x1800b9b5c  mov     r9d, ebx
0x1800b9b5f  mov     r8d, r14d
0x1800b9b62  mov     rcx, rdi; sesid
0x1800b9b65  call    DecrementProcessingOrder
0x1800b9b6a  test    eax, eax
0x1800b9b6c  jnz     short loc_1800B9B77
0x1800b9b6e  add     ebx, r13d
0x1800b9b71  cmp     ebx, esi
0x1800b9b73  jbe     short loc_1800B9B5C
0x1800b9b75  xor     eax, eax
0x1800b9b77  lea     r11, [rsp+80h+var_s0]
0x1800b9b7f  mov     rbx, [r11+40h]
0x1800b9b83  mov     rsi, [r11+48h]
0x1800b9b87  mov     rsp, r11
0x1800b9b8a  pop     r15
0x1800b9b8c  pop     r14
0x1800b9b8e  pop     r13
0x1800b9b90  pop     rdi
0x1800b9b91  pop     rbp
0x1800b9b92  retn
```
