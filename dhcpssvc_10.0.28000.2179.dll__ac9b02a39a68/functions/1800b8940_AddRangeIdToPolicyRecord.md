# AddRangeIdToPolicyRecord

- ea: `0x1800b8940`
- end: `0x1800b8b99`
- name: `AddRangeIdToPolicyRecord`
- size: `601`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180087658`

## callees

- `0x1800b8940`
- `0x1800bc990`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800b8988`
- `ESENT!JetSetCurrentIndexA` at `0x1800b8988`
- `ESENT!JetSetColumns` at `0x1800b8af6`
- `ESENT!JetSetColumns` at `0x1800b8af6`
- `ESENT!JetUpdate` at `0x1800b8b2b`
- `ESENT!JetUpdate` at `0x1800b8b2b`
- `ESENT!JetMakeKey` at `0x1800b89c9`
- `ESENT!JetMakeKey` at `0x1800b8a15`
- `ESENT!JetMakeKey` at `0x1800b89c9`
- `ESENT!JetMakeKey` at `0x1800b8a15`
- `ESENT!JetSeek` at `0x1800b8a47`
- `ESENT!JetSeek` at `0x1800b8a47`
- `ESENT!JetBeginTransaction` at `0x1800b8a6e`
- `ESENT!JetBeginTransaction` at `0x1800b8a6e`
- `ESENT!JetRollback` at `0x1800b8b75`
- `ESENT!JetRollback` at `0x1800b8b75`
- `ESENT!JetCommitTransaction` at `0x1800b8b50`
- `ESENT!JetCommitTransaction` at `0x1800b8b50`
- `ESENT!JetPrepareUpdate` at `0x1800b8aa0`
- `ESENT!JetPrepareUpdate` at `0x1800b8aa0`

## string_xrefs

- `0x1800b8b39`: `AddRangeIdToPolicyRecord:JetUPdate`
- `0x1800b8aae`: `AddRangeIdToPolicyRecord:JetPrepareUpdate`
- `0x1800b8b5e`: `AddRangeIdToPolicyRecord:JetCommitTransaction`

## pseudocode

```c
__int64 __fastcall AddRangeIdToPolicyRecord(__int64 a1, int a2, _WORD *a3, int a4)
{
  JET_SESID v4; // rdi
  unsigned int v6; // eax
  unsigned int v7; // ebx
  unsigned int Key; // eax
  __int64 v9; // r9
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  JET_SETCOLUMN psetcolumn; // [rsp+30h] [rbp-30h] BYREF
  int v19; // [rsp+88h] [rbp+28h] BYREF
  int pvData; // [rsp+98h] [rbp+38h] BYREF

  pvData = a4;
  v19 = a2;
  v4 = DhcpGlobalJetServerSession;
  memset(&psetcolumn, 0, 36);
  v6 = JetSetCurrentIndexA(DhcpGlobalJetServerSession, PolicyTableId, "PolicyTable_Index2");
  v7 = PolicyMapJetError(v6, "AddRangeIdToPolicyRecord:SetCurrentIndex");
  if ( !v7 )
  {
    Key = JetMakeKey(v4, PolicyTableId, &pvData, 4u, 1u);
    v7 = PolicyMapJetError(Key, "AddRangeIdToPolicyRecord:JetMakeKey1");
    if ( !v7 )
    {
      v9 = -1;
      do
        ++v9;
      while ( a3[v9] );
      v10 = JetMakeKey(v4, PolicyTableId, a3, 2 * v9 + 2, 0);
      v7 = PolicyMapJetError(v10, "AddRangeIdToPolicyRecord:JetMakeKey2");
      if ( !v7 )
      {
        v11 = JetSeek(v4, PolicyTableId, 1u);
        v7 = PolicyMapJetError(v11, "AddRangeIdToPolicyRecord:JetSeek");
        if ( !v7 )
        {
          v12 = JetBeginTransaction(v4);
          v7 = PolicyMapJetError(v12, "AddRangeIdToPolicyRecord:JetBeginTransaction");
          if ( !v7 )
          {
            v13 = JetPrepareUpdate(v4, PolicyTableId, 2u);
            v7 = PolicyMapJetError(v13, "AddRangeIdToPolicyRecord:JetPrepareUpdate");
            if ( v7 )
              goto LABEL_12;
            psetcolumn.columnid = dword_1800F9830;
            *(_QWORD *)&psetcolumn.itagSequence = 0;
            psetcolumn.pvData = &v19;
            *(_QWORD *)&psetcolumn.grbit = 0;
            psetcolumn.cbData = 4;
            v14 = JetSetColumns(v4, PolicyTableId, &psetcolumn, 1u);
            v7 = PolicyMapJetError(v14, "AddRangeIdToPolicyRecord:JetSetColumns");
            if ( v7
              || (v15 = JetUpdate(v4, PolicyTableId, 0, 0, 0),
                  (v7 = PolicyMapJetError(v15, "AddRangeIdToPolicyRecord:JetUPdate")) != 0)
              || (v16 = JetCommitTransaction(v4, 0),
                  (v7 = PolicyMapJetError(v16, "AddRangeIdToPolicyRecord:JetCommitTransaction")) != 0) )
            {
LABEL_12:
              JetRollback(v4, 0);
            }
          }
        }
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1800b8940  mov     rax, rsp
0x1800b8943  mov     [rax+8], rbx
0x1800b8947  mov     [rax+18h], rsi
0x1800b894b  mov     [rax+20h], r9d
0x1800b894f  mov     [rax+10h], edx
0x1800b8952  push    rbp
0x1800b8953  push    rdi
0x1800b8954  push    r14
0x1800b8956  mov     rbp, rsp
0x1800b8959  sub     rsp, 60h
0x1800b895d  mov     rdi, cs:DhcpGlobalJetServerSession
0x1800b8964  xorps   xmm0, xmm0
0x1800b8967  mov     rdx, cs:PolicyTableId; tableid
0x1800b896e  mov     rsi, r8
0x1800b8971  xor     eax, eax
0x1800b8973  lea     r8, aPolicytableInd; "PolicyTable_Index2"
0x1800b897a  mov     rcx, rdi; sesid
0x1800b897d  mov     [rbp+psetcolumn.err], eax
0x1800b8980  movups  xmmword ptr [rbp+psetcolumn.columnid], xmm0
0x1800b8984  movups  xmmword ptr [rbp+psetcolumn.cbData], xmm0
0x1800b8988  call    cs:__imp_JetSetCurrentIndexA
0x1800b898f  nop     dword ptr [rax+rax+00h]
0x1800b8994  mov     ecx, eax
0x1800b8996  lea     rdx, aAddrangeidtopo_1; "AddRangeIdToPolicyRecord:SetCurrentInde"...
0x1800b899d  call    PolicyMapJetError
0x1800b89a2  xor     r14d, r14d
0x1800b89a5  mov     ebx, eax
0x1800b89a7  test    eax, eax
0x1800b89a9  jnz     loc_1800B8B81
0x1800b89af  mov     rdx, cs:PolicyTableId; tableid
0x1800b89b6  lea     r9d, [rax+4]; cbData
0x1800b89ba  lea     r8, [rbp+pvData]; pvData
0x1800b89be  mov     [rsp+60h+grbit], 1; grbit
0x1800b89c6  mov     rcx, rdi; sesid
0x1800b89c9  call    cs:__imp_JetMakeKey
0x1800b89d0  nop     dword ptr [rax+rax+00h]
0x1800b89d5  mov     ecx, eax
0x1800b89d7  lea     rdx, aAddrangeidtopo_6; "AddRangeIdToPolicyRecord:JetMakeKey1"
0x1800b89de  call    PolicyMapJetError
0x1800b89e3  mov     ebx, eax
0x1800b89e5  test    eax, eax
0x1800b89e7  jnz     loc_1800B8B81
0x1800b89ed  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800b89f1  inc     r9
0x1800b89f4  cmp     [rsi+r9*2], r14w
0x1800b89f9  jnz     short loc_1800B89F1
0x1800b89fb  mov     rdx, cs:PolicyTableId; tableid
0x1800b8a02  lea     r9d, ds:2[r9*2]; cbData
0x1800b8a0a  mov     r8, rsi; pvData
0x1800b8a0d  mov     [rsp+60h+grbit], r14d; grbit
0x1800b8a12  mov     rcx, rdi; sesid
0x1800b8a15  call    cs:__imp_JetMakeKey
0x1800b8a1c  nop     dword ptr [rax+rax+00h]
0x1800b8a21  mov     ecx, eax
0x1800b8a23  lea     rdx, aAddrangeidtopo_7; "AddRangeIdToPolicyRecord:JetMakeKey2"
0x1800b8a2a  call    PolicyMapJetError
0x1800b8a2f  mov     ebx, eax
0x1800b8a31  test    eax, eax
0x1800b8a33  jnz     loc_1800B8B81
0x1800b8a39  mov     rdx, cs:PolicyTableId; tableid
0x1800b8a40  lea     r8d, [rax+1]; grbit
0x1800b8a44  mov     rcx, rdi; sesid
0x1800b8a47  call    cs:__imp_JetSeek
0x1800b8a4e  nop     dword ptr [rax+rax+00h]
0x1800b8a53  mov     ecx, eax
0x1800b8a55  lea     rdx, aAddrangeidtopo_5; "AddRangeIdToPolicyRecord:JetSeek"
0x1800b8a5c  call    PolicyMapJetError
0x1800b8a61  mov     ebx, eax
0x1800b8a63  test    eax, eax
0x1800b8a65  jnz     loc_1800B8B81
0x1800b8a6b  mov     rcx, rdi; sesid
0x1800b8a6e  call    cs:__imp_JetBeginTransaction
0x1800b8a75  nop     dword ptr [rax+rax+00h]
0x1800b8a7a  mov     ecx, eax
0x1800b8a7c  lea     rdx, aAddrangeidtopo_4; "AddRangeIdToPolicyRecord:JetBeginTransa"...
0x1800b8a83  call    PolicyMapJetError
0x1800b8a88  mov     ebx, eax
0x1800b8a8a  test    eax, eax
0x1800b8a8c  jnz     loc_1800B8B81
0x1800b8a92  mov     rdx, cs:PolicyTableId; tableid
0x1800b8a99  lea     r8d, [rax+2]; prep
0x1800b8a9d  mov     rcx, rdi; sesid
0x1800b8aa0  call    cs:__imp_JetPrepareUpdate
0x1800b8aa7  nop     dword ptr [rax+rax+00h]
0x1800b8aac  mov     ecx, eax
0x1800b8aae  lea     rdx, aAddrangeidtopo; "AddRangeIdToPolicyRecord:JetPrepareUpda"...
0x1800b8ab5  call    PolicyMapJetError
0x1800b8aba  mov     ebx, eax
0x1800b8abc  test    eax, eax
0x1800b8abe  jnz     loc_1800B8B70
0x1800b8ac4  mov     eax, cs:dword_1800F9830
0x1800b8aca  lea     r9d, [rbx+1]; csetcolumn
0x1800b8ace  mov     rdx, cs:PolicyTableId; tableid
0x1800b8ad5  lea     r8, [rbp+psetcolumn]; psetcolumn
0x1800b8ad9  mov     [rbp+psetcolumn.columnid], eax
0x1800b8adc  mov     rcx, rdi; sesid
0x1800b8adf  lea     rax, [rbp+arg_8]
0x1800b8ae3  mov     qword ptr [rbp+psetcolumn.itagSequence], r14
0x1800b8ae7  mov     [rbp+psetcolumn.pvData], rax
0x1800b8aeb  mov     qword ptr [rbp+psetcolumn.grbit], r14
0x1800b8aef  mov     [rbp+psetcolumn.cbData], 4
0x1800b8af6  call    cs:__imp_JetSetColumns
0x1800b8afd  nop     dword ptr [rax+rax+00h]
0x1800b8b02  mov     ecx, eax
0x1800b8b04  lea     rdx, aAddrangeidtopo_3; "AddRangeIdToPolicyRecord:JetSetColumns"
0x1800b8b0b  call    PolicyMapJetError
0x1800b8b10  mov     ebx, eax
0x1800b8b12  test    eax, eax
0x1800b8b14  jnz     short loc_1800B8B70
0x1800b8b16  mov     rdx, cs:PolicyTableId; tableid
0x1800b8b1d  xor     r9d, r9d; cbBookmark
0x1800b8b20  xor     r8d, r8d; pvBookmark
0x1800b8b23  mov     qword ptr [rsp+60h+grbit], r14; pcbActual
0x1800b8b28  mov     rcx, rdi; sesid
0x1800b8b2b  call    cs:__imp_JetUpdate
0x1800b8b32  nop     dword ptr [rax+rax+00h]
0x1800b8b37  mov     ecx, eax
0x1800b8b39  lea     rdx, aAddrangeidtopo_2; "AddRangeIdToPolicyRecord:JetUPdate"
0x1800b8b40  call    PolicyMapJetError
0x1800b8b45  mov     ebx, eax
0x1800b8b47  test    eax, eax
0x1800b8b49  jnz     short loc_1800B8B70
0x1800b8b4b  xor     edx, edx; grbit
0x1800b8b4d  mov     rcx, rdi; sesid
0x1800b8b50  call    cs:__imp_JetCommitTransaction
0x1800b8b57  nop     dword ptr [rax+rax+00h]
0x1800b8b5c  mov     ecx, eax
0x1800b8b5e  lea     rdx, aAddrangeidtopo_0; "AddRangeIdToPolicyRecord:JetCommitTrans"...
0x1800b8b65  call    PolicyMapJetError
0x1800b8b6a  mov     ebx, eax
0x1800b8b6c  test    eax, eax
0x1800b8b6e  jz      short loc_1800B8B81
0x1800b8b70  xor     edx, edx; grbit
0x1800b8b72  mov     rcx, rdi; sesid
0x1800b8b75  call    cs:__imp_JetRollback
0x1800b8b7c  nop     dword ptr [rax+rax+00h]
0x1800b8b81  lea     r11, [rsp+60h+var_s0]
0x1800b8b86  mov     eax, ebx
0x1800b8b88  mov     rbx, [r11+20h]
0x1800b8b8c  mov     rsi, [r11+30h]
0x1800b8b90  mov     rsp, r11
0x1800b8b93  pop     r14
0x1800b8b95  pop     rdi
0x1800b8b96  pop     rbp
0x1800b8b97  retn
```
