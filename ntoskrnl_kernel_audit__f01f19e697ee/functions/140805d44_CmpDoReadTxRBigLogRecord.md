# CmpDoReadTxRBigLogRecord

- ea: `0x140805d44`
- end: `0x140805ea1`
- name: `CmpDoReadTxRBigLogRecord`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1408061b4`

## callees

- `0x14043e7e0`
- `0x140468330`
- `0x1406f6f80`
- `0x140805d44`
- `0x140806510`

## import_xrefs

- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadNextLogRecord` at `0x140805e39`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadNextLogRecord` at `0x140805e39`

## pseudocode

```c
__int64 __fastcall CmpDoReadTxRBigLogRecord(void *a1, void *a2, ULONG a3, struct _PRIVILEGE_SET **a4, unsigned int *a5)
{
  _DWORD *v5; // rdi
  NTSTATUS v6; // ebx
  unsigned int v7; // r15d
  __int64 Pool; // rax
  struct _PRIVILEGE_SET *v9; // rsi
  int v10; // r12d
  char *v11; // r13
  unsigned int v12; // r14d
  unsigned int v13; // ebx
  unsigned int v15; // [rsp+40h] [rbp-38h]
  PVOID ppvBuffer; // [rsp+48h] [rbp-30h] BYREF
  CLFS_LSN plsnRecord; // [rsp+50h] [rbp-28h] BYREF
  CLFS_LSN plsnPrevious; // [rsp+58h] [rbp-20h] BYREF
  CLFS_LSN plsnUndoNext; // [rsp+60h] [rbp-18h] BYREF
  __int64 v20; // [rsp+68h] [rbp-10h]
  ULONG pcbBuffer; // [rsp+C8h] [rbp+50h] BYREF
  CLS_RECORD_TYPE peRecordType; // [rsp+D0h] [rbp+58h] BYREF
  struct _PRIVILEGE_SET **v24; // [rsp+D8h] [rbp+60h]

  v24 = a4;
  ppvBuffer = a2;
  v5 = a2;
  plsnUndoNext.ullOffset = 0;
  plsnPrevious.ullOffset = 0;
  plsnRecord.ullOffset = 0;
  peRecordType = 0;
  pcbBuffer = a3;
  v6 = CmpVerifyBigLogRecordChunk(a2, a3);
  if ( v6 >= 0 )
  {
    v7 = v5[1];
    v15 = v5[12];
    Pool = CmpAllocatePool(256, v7, 538987843);
    v9 = (struct _PRIVILEGE_SET *)Pool;
    if ( Pool )
    {
      v10 = 0;
      v11 = (char *)Pool;
      v12 = v7;
      while ( v5[13] == v10 )
      {
        v13 = v5[14];
        if ( v13 > v12 )
          break;
        v20 = (unsigned int)v5[14];
        memmove(v11, v5 + 16, v13);
        v12 -= v13;
        if ( ++v10 >= v15 )
        {
          if ( !v12 )
          {
            v6 = 0;
            *v24 = v9;
            *a5 = v7;
            return (unsigned int)v6;
          }
          break;
        }
        peRecordType = 1;
        v6 = ClfsReadNextLogRecord(
               a1,
               &ppvBuffer,
               &pcbBuffer,
               &peRecordType,
               0,
               &plsnUndoNext,
               &plsnPrevious,
               &plsnRecord);
        if ( v6 < 0 )
          goto LABEL_14;
        v5 = ppvBuffer;
        v6 = CmpVerifyBigLogRecordChunk(ppvBuffer, pcbBuffer);
        if ( v6 < 0 )
          goto LABEL_14;
        v11 += v20;
      }
      v6 = -1073741762;
LABEL_14:
      CmSiFreeMemory(v9);
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140805d44  mov     [rsp-40h+arg_18], r9
0x140805d49  mov     [rsp-40h+pvReadContext], rcx
0x140805d4e  push    rbp
0x140805d4f  push    rbx
0x140805d50  push    rsi
0x140805d51  push    rdi
0x140805d52  push    r12
0x140805d54  push    r13
0x140805d56  push    r14
0x140805d58  push    r15
0x140805d5a  mov     rbp, rsp
0x140805d5d  sub     rsp, 78h
0x140805d61  xor     r14d, r14d
0x140805d64  mov     [rbp+ppvBuffer], rdx
0x140805d68  mov     rdi, rdx
0x140805d6b  mov     qword ptr [rbp+var_18], r14
0x140805d6f  mov     rcx, rdi
0x140805d72  mov     qword ptr [rbp+var_20], r14
0x140805d76  mov     edx, r8d
0x140805d79  mov     qword ptr [rbp+var_28], r14
0x140805d7d  mov     [rbp+peRecordType], r14b
0x140805d81  mov     [rbp+pcbBuffer], r8d
0x140805d85  call    CmpVerifyBigLogRecordChunk
0x140805d8a  mov     ebx, eax
0x140805d8c  test    eax, eax
0x140805d8e  js      loc_140805E8D
0x140805d94  mov     r15d, [rdi+4]
0x140805d98  mov     ecx, 100h
0x140805d9d  mov     eax, [rdi+30h]
0x140805da0  mov     edx, r15d
0x140805da3  mov     r8d, 20204D43h
0x140805da9  mov     [rbp+var_38], eax
0x140805dac  call    CmpAllocatePool
0x140805db1  mov     rsi, rax
0x140805db4  test    rax, rax
0x140805db7  jnz     short loc_140805DC3
0x140805db9  mov     ebx, 0C000009Ah
0x140805dbe  jmp     loc_140805E8D
0x140805dc3  mov     r12d, r14d
0x140805dc6  mov     r13, rsi
0x140805dc9  mov     r14d, r15d
0x140805dcc  cmp     [rdi+34h], r12d
0x140805dd0  jnz     loc_140805E80
0x140805dd6  mov     ebx, [rdi+38h]
0x140805dd9  cmp     ebx, r14d
0x140805ddc  ja      loc_140805E80
0x140805de2  lea     rdx, [rdi+40h]; Src
0x140805de6  mov     [rbp+var_10], rbx
0x140805dea  mov     r8d, ebx; Size
0x140805ded  mov     rcx, r13; void *
0x140805df0  call    memmove
0x140805df5  sub     r14d, ebx
0x140805df8  inc     r12d
0x140805dfb  cmp     r12d, [rbp+var_38]
0x140805dff  jnb     short loc_140805E69
0x140805e01  mov     rcx, [rbp+pvReadContext]; pvReadContext
0x140805e05  lea     rax, [rbp+var_28]
0x140805e09  mov     [rsp+78h+plsnRecord], rax; plsnRecord
0x140805e0e  lea     r9, [rbp+peRecordType]; peRecordType
0x140805e12  lea     rax, [rbp+var_20]
0x140805e16  mov     [rbp+peRecordType], 1
0x140805e1a  mov     [rsp+78h+plsnPrevious], rax; plsnPrevious
0x140805e1f  lea     r8, [rbp+pcbBuffer]; pcbBuffer
0x140805e23  lea     rax, [rbp+var_18]
0x140805e27  mov     [rsp+78h+plsnUndoNext], rax; plsnUndoNext
0x140805e2c  lea     rdx, [rbp+ppvBuffer]; ppvBuffer
0x140805e30  mov     [rsp+78h+plsnUser], 0; plsnUser
0x140805e39  call    cs:__imp_ClfsReadNextLogRecord
0x140805e40  nop     dword ptr [rax+rax+00h]
0x140805e45  mov     ebx, eax
0x140805e47  test    eax, eax
0x140805e49  js      short loc_140805E85
0x140805e4b  mov     rdi, [rbp+ppvBuffer]
0x140805e4f  mov     edx, [rbp+pcbBuffer]
0x140805e52  mov     rcx, rdi
0x140805e55  call    CmpVerifyBigLogRecordChunk
0x140805e5a  mov     ebx, eax
0x140805e5c  test    eax, eax
0x140805e5e  js      short loc_140805E85
0x140805e60  add     r13, [rbp+var_10]
0x140805e64  jmp     loc_140805DCC
0x140805e69  test    r14d, r14d
0x140805e6c  jnz     short loc_140805E80
0x140805e6e  mov     rax, [rbp+arg_18]
0x140805e72  xor     ebx, ebx
0x140805e74  mov     [rax], rsi
0x140805e77  mov     rax, [rbp+arg_20]
0x140805e7b  mov     [rax], r15d
0x140805e7e  jmp     short loc_140805E8D
0x140805e80  mov     ebx, 0C000003Eh
0x140805e85  mov     rcx, rsi; Privileges
0x140805e88  call    CmSiFreeMemory
0x140805e8d  mov     eax, ebx
0x140805e8f  add     rsp, 78h
0x140805e93  pop     r15
0x140805e95  pop     r14
0x140805e97  pop     r13
0x140805e99  pop     r12
0x140805e9b  pop     rdi
0x140805e9c  pop     rsi
0x140805e9d  pop     rbx
0x140805e9e  pop     rbp
0x140805e9f  retn
```
