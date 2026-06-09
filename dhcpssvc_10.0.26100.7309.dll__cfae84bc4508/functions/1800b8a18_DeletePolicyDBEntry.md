# DeletePolicyDBEntry

- ea: `0x1800b8a18`
- end: `0x1800b8c96`
- name: `DeletePolicyDBEntry`
- size: `638`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800882b8`

## callees

- `0x18009602c`
- `0x1800b8460`
- `0x1800b8a18`
- `0x1800bb398`
- `0x1800bba04`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800b8a79`
- `ESENT!JetSetCurrentIndexA` at `0x1800b8a79`
- `ESENT!JetRetrieveColumns` at `0x1800b8b8c`
- `ESENT!JetRetrieveColumns` at `0x1800b8c03`
- `ESENT!JetRetrieveColumns` at `0x1800b8b8c`
- `ESENT!JetRetrieveColumns` at `0x1800b8c03`
- `ESENT!JetMakeKey` at `0x1800b8ab8`
- `ESENT!JetMakeKey` at `0x1800b8ab8`
- `ESENT!JetSeek` at `0x1800b8ae7`
- `ESENT!JetSeek` at `0x1800b8ae7`
- `ESENT!JetDelete` at `0x1800b8c32`
- `ESENT!JetDelete` at `0x1800b8c32`
- `ESENT!JetRetrieveColumn` at `0x1800b8b33`
- `ESENT!JetRetrieveColumn` at `0x1800b8b33`

## string_xrefs

- `0x1800b8a87`: `DeletePolicyDBEntry:JetSetCurrentIndex`
- `0x1800b8b41`: `DeletePolicyDBentry:JetRetrieveColumn`
- `0x1800b8b9a`: `DeletePolicyDBentry:JetRetrieveColumns1`
- `0x1800b8ac6`: `DeletePolicyDBEntry:JetMakeKey`
- `0x1800b8af5`: `DeletePolicyDBEntry:JetSeek`
- `0x1800b8c11`: `DeletePolicyDBentry:JetRetrieveColumns2`
- `0x1800b8c40`: `DeletePolicyDBentry:JetDelete`

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
          v11 = JetRetrieveColumn(v5, PolicyTableId, dword_1800F7618, &v21, 4u, 0, 1u, 0);
          result = PolicyMapJetError(v11, "DeletePolicyDBentry:JetRetrieveColumn");
          if ( !(_DWORD)result )
          {
            pretrievecolumn.columnidNextTagged = 0;
            pretrievecolumn.ibLongValue = 0;
            pretrievecolumn.err = 0;
            pretrievecolumn.cbActual = 0;
            pretrievecolumn.itagSequence = 0;
            pretrievecolumn.pvData = 0;
            pretrievecolumn.cbData = 0;
            pretrievecolumn.columnid = dword_1800F7660;
            pretrievecolumn.grbit = 1;
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
0x1800b8a18  mov     rax, rsp
0x1800b8a1b  mov     [rax+18h], rbx
0x1800b8a1f  mov     [rax+20h], rsi
0x1800b8a23  mov     [rax+10h], edx
0x1800b8a26  mov     [rax+8], rcx
0x1800b8a2a  push    rbp
0x1800b8a2b  push    rdi
0x1800b8a2c  push    r13
0x1800b8a2e  push    r14
0x1800b8a30  push    r15
0x1800b8a32  mov     rbp, rsp
0x1800b8a35  sub     rsp, 80h
0x1800b8a3c  mov     rdi, cs:DhcpGlobalJetServerSession
0x1800b8a43  mov     r14d, r8d
0x1800b8a46  and     [rbp+arg_0], 0
0x1800b8a4a  lea     r8, [rbp+var_40]
0x1800b8a4e  and     [rbp+var_40], 0
0x1800b8a52  mov     edx, r14d
0x1800b8a55  mov     rcx, rdi; sesid
0x1800b8a58  mov     r15, r9
0x1800b8a5b  call    GetMaxProcessingOrderForSubnet
0x1800b8a60  test    eax, eax
0x1800b8a62  jnz     loc_1800B8C79
0x1800b8a68  mov     rdx, cs:PolicyTableId; tableid
0x1800b8a6f  lea     r8, aPolicytableInd_1; "PolicyTable_Index1"
0x1800b8a76  mov     rcx, rdi; sesid
0x1800b8a79  call    cs:__imp_JetSetCurrentIndexA
0x1800b8a80  nop     dword ptr [rax+rax+00h]
0x1800b8a85  mov     ecx, eax
0x1800b8a87  lea     rdx, aDeletepolicydb_4; "DeletePolicyDBEntry:JetSetCurrentIndex"
0x1800b8a8e  call    PolicyMapJetError
0x1800b8a93  test    eax, eax
0x1800b8a95  jnz     loc_1800B8C79
0x1800b8a9b  mov     rdx, cs:PolicyTableId; tableid
0x1800b8aa2  lea     ebx, [rax+4]
0x1800b8aa5  lea     r13d, [rax+1]
0x1800b8aa9  mov     r9d, ebx; cbData
0x1800b8aac  lea     r8, [rbp+pvData]; pvData
0x1800b8ab0  mov     [rsp+80h+grbit], r13d; grbit
0x1800b8ab5  mov     rcx, rdi; sesid
0x1800b8ab8  call    cs:__imp_JetMakeKey
0x1800b8abf  nop     dword ptr [rax+rax+00h]
0x1800b8ac4  mov     ecx, eax
0x1800b8ac6  lea     rdx, aDeletepolicydb_3; "DeletePolicyDBEntry:JetMakeKey"
0x1800b8acd  call    PolicyMapJetError
0x1800b8ad2  test    eax, eax
0x1800b8ad4  jnz     loc_1800B8C79
0x1800b8ada  mov     rdx, cs:PolicyTableId; tableid
0x1800b8ae1  mov     r8d, r13d; grbit
0x1800b8ae4  mov     rcx, rdi; sesid
0x1800b8ae7  call    cs:__imp_JetSeek
0x1800b8aee  nop     dword ptr [rax+rax+00h]
0x1800b8af3  mov     ecx, eax
0x1800b8af5  lea     rdx, aDeletepolicydb_5; "DeletePolicyDBEntry:JetSeek"
0x1800b8afc  call    PolicyMapJetError
0x1800b8b01  test    eax, eax
0x1800b8b03  jnz     loc_1800B8C79
0x1800b8b09  and     [rsp+80h+var_48], 0
0x1800b8b0f  lea     r9, [rbp+arg_0]; pvData
0x1800b8b13  mov     r8d, cs:dword_1800F7618; columnid
0x1800b8b1a  mov     rcx, rdi; sesid
0x1800b8b1d  mov     rdx, cs:PolicyTableId; tableid
0x1800b8b24  mov     [rsp+80h+var_50], r13d; grbit
0x1800b8b29  and     [rsp+80h+var_58], 0
0x1800b8b2f  mov     [rsp+80h+grbit], ebx; cbData
0x1800b8b33  call    cs:__imp_JetRetrieveColumn
0x1800b8b3a  nop     dword ptr [rax+rax+00h]
0x1800b8b3f  mov     ecx, eax
0x1800b8b41  lea     rdx, aDeletepolicydb; "DeletePolicyDBentry:JetRetrieveColumn"
0x1800b8b48  call    PolicyMapJetError
0x1800b8b4d  test    eax, eax
0x1800b8b4f  jnz     loc_1800B8C79
0x1800b8b55  and     [rbp+pretrievecolumn.columnidNextTagged], eax
0x1800b8b58  lea     r8, [rbp+pretrievecolumn]; pretrievecolumn
0x1800b8b5c  and     [rbp+pretrievecolumn.ibLongValue], eax
0x1800b8b5f  mov     r9d, r13d; cretrievecolumn
0x1800b8b62  and     [rbp+pretrievecolumn.err], eax
0x1800b8b65  mov     rcx, rdi; sesid
0x1800b8b68  and     [rbp+pretrievecolumn.cbActual], eax
0x1800b8b6b  mov     eax, cs:dword_1800F7660
0x1800b8b71  mov     rdx, cs:PolicyTableId; tableid
0x1800b8b78  and     [rbp+pretrievecolumn.itagSequence], 0
0x1800b8b7c  and     [rbp+pretrievecolumn.pvData], 0
0x1800b8b81  and     [rbp+pretrievecolumn.cbData], 0
0x1800b8b85  mov     [rbp+pretrievecolumn.columnid], eax
0x1800b8b88  mov     [rbp+pretrievecolumn.grbit], r13d
0x1800b8b8c  call    cs:__imp_JetRetrieveColumns
0x1800b8b93  nop     dword ptr [rax+rax+00h]
0x1800b8b98  mov     ecx, eax
0x1800b8b9a  lea     rdx, aDeletepolicydb_0; "DeletePolicyDBentry:JetRetrieveColumns1"
0x1800b8ba1  call    PolicyMapJetError
0x1800b8ba6  test    eax, eax
0x1800b8ba8  jnz     loc_1800B8C79
0x1800b8bae  mov     esi, [rbp+pretrievecolumn.itagSequence]
0x1800b8bb1  mov     rax, [rbp+arg_20]
0x1800b8bb5  mov     ecx, esi
0x1800b8bb7  shl     rcx, 2; dwBytes
0x1800b8bbb  mov     [rax], esi
0x1800b8bbd  call    MemAlloc
0x1800b8bc2  mov     [r15], rax
0x1800b8bc5  test    rax, rax
0x1800b8bc8  jnz     short loc_1800B8BD2
0x1800b8bca  lea     eax, [rbx+4]
0x1800b8bcd  jmp     loc_1800B8C79
0x1800b8bd2  mov     ebx, r13d
0x1800b8bd5  cmp     esi, r13d
0x1800b8bd8  jb      short loc_1800B8C28
0x1800b8bda  mov     rax, [r15]
0x1800b8bdd  lea     ecx, [rbx-1]
0x1800b8be0  mov     rdx, cs:PolicyTableId; tableid
0x1800b8be7  lea     r8, [rbp+pretrievecolumn]; pretrievecolumn
0x1800b8beb  mov     r9d, r13d; cretrievecolumn
0x1800b8bee  mov     [rbp+pretrievecolumn.itagSequence], ebx
0x1800b8bf1  mov     [rbp+pretrievecolumn.cbData], 4
0x1800b8bf8  lea     rcx, [rax+rcx*4]
0x1800b8bfc  mov     [rbp+pretrievecolumn.pvData], rcx
0x1800b8c00  mov     rcx, rdi; sesid
0x1800b8c03  call    cs:__imp_JetRetrieveColumns
0x1800b8c0a  nop     dword ptr [rax+rax+00h]
0x1800b8c0f  mov     ecx, eax
0x1800b8c11  lea     rdx, aDeletepolicydb_1; "DeletePolicyDBentry:JetRetrieveColumns2"
0x1800b8c18  call    PolicyMapJetError
0x1800b8c1d  test    eax, eax
0x1800b8c1f  jnz     short loc_1800B8C79
0x1800b8c21  add     ebx, r13d
0x1800b8c24  cmp     ebx, esi
0x1800b8c26  jbe     short loc_1800B8BDA
0x1800b8c28  mov     rdx, cs:PolicyTableId; tableid
0x1800b8c2f  mov     rcx, rdi; sesid
0x1800b8c32  call    cs:__imp_JetDelete
0x1800b8c39  nop     dword ptr [rax+rax+00h]
0x1800b8c3e  mov     ecx, eax
0x1800b8c40  lea     rdx, aDeletepolicydb_2; "DeletePolicyDBentry:JetDelete"
0x1800b8c47  call    PolicyMapJetError
0x1800b8c4c  test    eax, eax
0x1800b8c4e  jnz     short loc_1800B8C79
0x1800b8c50  mov     ebx, [rbp+arg_0]
0x1800b8c53  mov     esi, [rbp+var_40]
0x1800b8c56  cmp     ebx, esi
0x1800b8c58  jnb     short loc_1800B8C77
0x1800b8c5a  inc     ebx
0x1800b8c5c  jmp     short loc_1800B8C73
0x1800b8c5e  mov     r9d, ebx
0x1800b8c61  mov     r8d, r14d
0x1800b8c64  mov     rcx, rdi; sesid
0x1800b8c67  call    DecrementProcessingOrder
0x1800b8c6c  test    eax, eax
0x1800b8c6e  jnz     short loc_1800B8C79
0x1800b8c70  add     ebx, r13d
0x1800b8c73  cmp     ebx, esi
0x1800b8c75  jbe     short loc_1800B8C5E
0x1800b8c77  xor     eax, eax
0x1800b8c79  lea     r11, [rsp+80h+var_s0]
0x1800b8c81  mov     rbx, [r11+40h]
0x1800b8c85  mov     rsi, [r11+48h]
0x1800b8c89  mov     rsp, r11
0x1800b8c8c  pop     r15
0x1800b8c8e  pop     r14
0x1800b8c90  pop     r13
0x1800b8c92  pop     rdi
0x1800b8c93  pop     rbp
0x1800b8c94  retn
```
