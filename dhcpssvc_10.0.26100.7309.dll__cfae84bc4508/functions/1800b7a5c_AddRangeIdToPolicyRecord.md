# AddRangeIdToPolicyRecord

- ea: `0x1800b7a5c`
- end: `0x1800b7cb5`
- name: `AddRangeIdToPolicyRecord`
- size: `601`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800876d4`

## callees

- `0x1800b7a5c`
- `0x1800bba04`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800b7aa4`
- `ESENT!JetSetCurrentIndexA` at `0x1800b7aa4`
- `ESENT!JetSetColumns` at `0x1800b7c12`
- `ESENT!JetSetColumns` at `0x1800b7c12`
- `ESENT!JetUpdate` at `0x1800b7c47`
- `ESENT!JetUpdate` at `0x1800b7c47`
- `ESENT!JetMakeKey` at `0x1800b7ae5`
- `ESENT!JetMakeKey` at `0x1800b7b31`
- `ESENT!JetMakeKey` at `0x1800b7ae5`
- `ESENT!JetMakeKey` at `0x1800b7b31`
- `ESENT!JetSeek` at `0x1800b7b63`
- `ESENT!JetSeek` at `0x1800b7b63`
- `ESENT!JetBeginTransaction` at `0x1800b7b8a`
- `ESENT!JetBeginTransaction` at `0x1800b7b8a`
- `ESENT!JetRollback` at `0x1800b7c91`
- `ESENT!JetRollback` at `0x1800b7c91`
- `ESENT!JetCommitTransaction` at `0x1800b7c6c`
- `ESENT!JetCommitTransaction` at `0x1800b7c6c`
- `ESENT!JetPrepareUpdate` at `0x1800b7bbc`
- `ESENT!JetPrepareUpdate` at `0x1800b7bbc`

## string_xrefs

- `0x1800b7bca`: `AddRangeIdToPolicyRecord:JetPrepareUpdate`
- `0x1800b7c7a`: `AddRangeIdToPolicyRecord:JetCommitTransaction`
- `0x1800b7c55`: `AddRangeIdToPolicyRecord:JetUPdate`

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
            psetcolumn.columnid = dword_1800F7660;
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
0x1800b7a5c  mov     rax, rsp
0x1800b7a5f  mov     [rax+8], rbx
0x1800b7a63  mov     [rax+18h], rsi
0x1800b7a67  mov     [rax+20h], r9d
0x1800b7a6b  mov     [rax+10h], edx
0x1800b7a6e  push    rbp
0x1800b7a6f  push    rdi
0x1800b7a70  push    r14
0x1800b7a72  mov     rbp, rsp
0x1800b7a75  sub     rsp, 60h
0x1800b7a79  mov     rdi, cs:DhcpGlobalJetServerSession
0x1800b7a80  xorps   xmm0, xmm0
0x1800b7a83  mov     rdx, cs:PolicyTableId; tableid
0x1800b7a8a  mov     rsi, r8
0x1800b7a8d  xor     eax, eax
0x1800b7a8f  lea     r8, aPolicytableInd; "PolicyTable_Index2"
0x1800b7a96  mov     rcx, rdi; sesid
0x1800b7a99  mov     [rbp+psetcolumn.err], eax
0x1800b7a9c  movups  xmmword ptr [rbp+psetcolumn.columnid], xmm0
0x1800b7aa0  movups  xmmword ptr [rbp+psetcolumn.cbData], xmm0
0x1800b7aa4  call    cs:__imp_JetSetCurrentIndexA
0x1800b7aab  nop     dword ptr [rax+rax+00h]
0x1800b7ab0  mov     ecx, eax
0x1800b7ab2  lea     rdx, aAddrangeidtopo_1; "AddRangeIdToPolicyRecord:SetCurrentInde"...
0x1800b7ab9  call    PolicyMapJetError
0x1800b7abe  xor     r14d, r14d
0x1800b7ac1  mov     ebx, eax
0x1800b7ac3  test    eax, eax
0x1800b7ac5  jnz     loc_1800B7C9D
0x1800b7acb  mov     rdx, cs:PolicyTableId; tableid
0x1800b7ad2  lea     r9d, [rax+4]; cbData
0x1800b7ad6  lea     r8, [rbp+pvData]; pvData
0x1800b7ada  mov     [rsp+60h+grbit], 1; grbit
0x1800b7ae2  mov     rcx, rdi; sesid
0x1800b7ae5  call    cs:__imp_JetMakeKey
0x1800b7aec  nop     dword ptr [rax+rax+00h]
0x1800b7af1  mov     ecx, eax
0x1800b7af3  lea     rdx, aAddrangeidtopo_6; "AddRangeIdToPolicyRecord:JetMakeKey1"
0x1800b7afa  call    PolicyMapJetError
0x1800b7aff  mov     ebx, eax
0x1800b7b01  test    eax, eax
0x1800b7b03  jnz     loc_1800B7C9D
0x1800b7b09  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800b7b0d  inc     r9
0x1800b7b10  cmp     [rsi+r9*2], r14w
0x1800b7b15  jnz     short loc_1800B7B0D
0x1800b7b17  mov     rdx, cs:PolicyTableId; tableid
0x1800b7b1e  lea     r9d, ds:2[r9*2]; cbData
0x1800b7b26  mov     r8, rsi; pvData
0x1800b7b29  mov     [rsp+60h+grbit], r14d; grbit
0x1800b7b2e  mov     rcx, rdi; sesid
0x1800b7b31  call    cs:__imp_JetMakeKey
0x1800b7b38  nop     dword ptr [rax+rax+00h]
0x1800b7b3d  mov     ecx, eax
0x1800b7b3f  lea     rdx, aAddrangeidtopo_7; "AddRangeIdToPolicyRecord:JetMakeKey2"
0x1800b7b46  call    PolicyMapJetError
0x1800b7b4b  mov     ebx, eax
0x1800b7b4d  test    eax, eax
0x1800b7b4f  jnz     loc_1800B7C9D
0x1800b7b55  mov     rdx, cs:PolicyTableId; tableid
0x1800b7b5c  lea     r8d, [rax+1]; grbit
0x1800b7b60  mov     rcx, rdi; sesid
0x1800b7b63  call    cs:__imp_JetSeek
0x1800b7b6a  nop     dword ptr [rax+rax+00h]
0x1800b7b6f  mov     ecx, eax
0x1800b7b71  lea     rdx, aAddrangeidtopo_5; "AddRangeIdToPolicyRecord:JetSeek"
0x1800b7b78  call    PolicyMapJetError
0x1800b7b7d  mov     ebx, eax
0x1800b7b7f  test    eax, eax
0x1800b7b81  jnz     loc_1800B7C9D
0x1800b7b87  mov     rcx, rdi; sesid
0x1800b7b8a  call    cs:__imp_JetBeginTransaction
0x1800b7b91  nop     dword ptr [rax+rax+00h]
0x1800b7b96  mov     ecx, eax
0x1800b7b98  lea     rdx, aAddrangeidtopo_4; "AddRangeIdToPolicyRecord:JetBeginTransa"...
0x1800b7b9f  call    PolicyMapJetError
0x1800b7ba4  mov     ebx, eax
0x1800b7ba6  test    eax, eax
0x1800b7ba8  jnz     loc_1800B7C9D
0x1800b7bae  mov     rdx, cs:PolicyTableId; tableid
0x1800b7bb5  lea     r8d, [rax+2]; prep
0x1800b7bb9  mov     rcx, rdi; sesid
0x1800b7bbc  call    cs:__imp_JetPrepareUpdate
0x1800b7bc3  nop     dword ptr [rax+rax+00h]
0x1800b7bc8  mov     ecx, eax
0x1800b7bca  lea     rdx, aAddrangeidtopo; "AddRangeIdToPolicyRecord:JetPrepareUpda"...
0x1800b7bd1  call    PolicyMapJetError
0x1800b7bd6  mov     ebx, eax
0x1800b7bd8  test    eax, eax
0x1800b7bda  jnz     loc_1800B7C8C
0x1800b7be0  mov     eax, cs:dword_1800F7660
0x1800b7be6  lea     r9d, [rbx+1]; csetcolumn
0x1800b7bea  mov     rdx, cs:PolicyTableId; tableid
0x1800b7bf1  lea     r8, [rbp+psetcolumn]; psetcolumn
0x1800b7bf5  mov     [rbp+psetcolumn.columnid], eax
0x1800b7bf8  mov     rcx, rdi; sesid
0x1800b7bfb  lea     rax, [rbp+arg_8]
0x1800b7bff  mov     qword ptr [rbp+psetcolumn.itagSequence], r14
0x1800b7c03  mov     [rbp+psetcolumn.pvData], rax
0x1800b7c07  mov     qword ptr [rbp+psetcolumn.grbit], r14
0x1800b7c0b  mov     [rbp+psetcolumn.cbData], 4
0x1800b7c12  call    cs:__imp_JetSetColumns
0x1800b7c19  nop     dword ptr [rax+rax+00h]
0x1800b7c1e  mov     ecx, eax
0x1800b7c20  lea     rdx, aAddrangeidtopo_3; "AddRangeIdToPolicyRecord:JetSetColumns"
0x1800b7c27  call    PolicyMapJetError
0x1800b7c2c  mov     ebx, eax
0x1800b7c2e  test    eax, eax
0x1800b7c30  jnz     short loc_1800B7C8C
0x1800b7c32  mov     rdx, cs:PolicyTableId; tableid
0x1800b7c39  xor     r9d, r9d; cbBookmark
0x1800b7c3c  xor     r8d, r8d; pvBookmark
0x1800b7c3f  mov     qword ptr [rsp+60h+grbit], r14; pcbActual
0x1800b7c44  mov     rcx, rdi; sesid
0x1800b7c47  call    cs:__imp_JetUpdate
0x1800b7c4e  nop     dword ptr [rax+rax+00h]
0x1800b7c53  mov     ecx, eax
0x1800b7c55  lea     rdx, aAddrangeidtopo_2; "AddRangeIdToPolicyRecord:JetUPdate"
0x1800b7c5c  call    PolicyMapJetError
0x1800b7c61  mov     ebx, eax
0x1800b7c63  test    eax, eax
0x1800b7c65  jnz     short loc_1800B7C8C
0x1800b7c67  xor     edx, edx; grbit
0x1800b7c69  mov     rcx, rdi; sesid
0x1800b7c6c  call    cs:__imp_JetCommitTransaction
0x1800b7c73  nop     dword ptr [rax+rax+00h]
0x1800b7c78  mov     ecx, eax
0x1800b7c7a  lea     rdx, aAddrangeidtopo_0; "AddRangeIdToPolicyRecord:JetCommitTrans"...
0x1800b7c81  call    PolicyMapJetError
0x1800b7c86  mov     ebx, eax
0x1800b7c88  test    eax, eax
0x1800b7c8a  jz      short loc_1800B7C9D
0x1800b7c8c  xor     edx, edx; grbit
0x1800b7c8e  mov     rcx, rdi; sesid
0x1800b7c91  call    cs:__imp_JetRollback
0x1800b7c98  nop     dword ptr [rax+rax+00h]
0x1800b7c9d  lea     r11, [rsp+60h+var_s0]
0x1800b7ca2  mov     eax, ebx
0x1800b7ca4  mov     rbx, [r11+20h]
0x1800b7ca8  mov     rsi, [r11+30h]
0x1800b7cac  mov     rsp, r11
0x1800b7caf  pop     r14
0x1800b7cb1  pop     rdi
0x1800b7cb2  pop     rbp
0x1800b7cb3  retn
```
