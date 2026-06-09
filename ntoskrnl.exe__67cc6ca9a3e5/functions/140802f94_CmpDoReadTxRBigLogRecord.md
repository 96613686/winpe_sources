# CmpDoReadTxRBigLogRecord

- ea: `0x140802f94`
- end: `0x1408030f1`
- name: `CmpDoReadTxRBigLogRecord`
- size: `349`
- prototype: `__int64 __fastcall(void *, void *, ULONG, struct _PRIVILEGE_SET **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140803404`

## callees

- `0x14042a7b0`
- `0x140456940`
- `0x1406f4480`
- `0x140802f94`
- `0x140803760`

## import_xrefs

- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadNextLogRecord` at `0x140803089`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadNextLogRecord` at `0x140803089`

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
0x140802f94  mov     [rsp-40h+arg_18], r9
0x140802f99  mov     [rsp-40h+pvReadContext], rcx
0x140802f9e  push    rbp
0x140802f9f  push    rbx
0x140802fa0  push    rsi
0x140802fa1  push    rdi
0x140802fa2  push    r12
0x140802fa4  push    r13
0x140802fa6  push    r14
0x140802fa8  push    r15
0x140802faa  mov     rbp, rsp
0x140802fad  sub     rsp, 78h
0x140802fb1  xor     r14d, r14d
0x140802fb4  mov     [rbp+ppvBuffer], rdx
0x140802fb8  mov     rdi, rdx
0x140802fbb  mov     qword ptr [rbp+var_18], r14
0x140802fbf  mov     rcx, rdi
0x140802fc2  mov     qword ptr [rbp+var_20], r14
0x140802fc6  mov     edx, r8d
0x140802fc9  mov     qword ptr [rbp+var_28], r14
0x140802fcd  mov     [rbp+peRecordType], r14b
0x140802fd1  mov     [rbp+pcbBuffer], r8d
0x140802fd5  call    CmpVerifyBigLogRecordChunk
0x140802fda  mov     ebx, eax
0x140802fdc  test    eax, eax
0x140802fde  js      loc_1408030DD
0x140802fe4  mov     r15d, [rdi+4]
0x140802fe8  mov     ecx, 100h
0x140802fed  mov     eax, [rdi+30h]
0x140802ff0  mov     edx, r15d
0x140802ff3  mov     r8d, 20204D43h
0x140802ff9  mov     [rbp+var_38], eax
0x140802ffc  call    CmpAllocatePool
0x140803001  mov     rsi, rax
0x140803004  test    rax, rax
0x140803007  jnz     short loc_140803013
0x140803009  mov     ebx, 0C000009Ah
0x14080300e  jmp     loc_1408030DD
0x140803013  mov     r12d, r14d
0x140803016  mov     r13, rsi
0x140803019  mov     r14d, r15d
0x14080301c  cmp     [rdi+34h], r12d
0x140803020  jnz     loc_1408030D0
0x140803026  mov     ebx, [rdi+38h]
0x140803029  cmp     ebx, r14d
0x14080302c  ja      loc_1408030D0
0x140803032  lea     rdx, [rdi+40h]; Src
0x140803036  mov     [rbp+var_10], rbx
0x14080303a  mov     r8d, ebx; Size
0x14080303d  mov     rcx, r13; void *
0x140803040  call    memmove
0x140803045  sub     r14d, ebx
0x140803048  inc     r12d
0x14080304b  cmp     r12d, [rbp+var_38]
0x14080304f  jnb     short loc_1408030B9
0x140803051  mov     rcx, [rbp+pvReadContext]; pvReadContext
0x140803055  lea     rax, [rbp+var_28]
0x140803059  mov     [rsp+78h+plsnRecord], rax; plsnRecord
0x14080305e  lea     r9, [rbp+peRecordType]; peRecordType
0x140803062  lea     rax, [rbp+var_20]
0x140803066  mov     [rbp+peRecordType], 1
0x14080306a  mov     [rsp+78h+plsnPrevious], rax; plsnPrevious
0x14080306f  lea     r8, [rbp+pcbBuffer]; pcbBuffer
0x140803073  lea     rax, [rbp+var_18]
0x140803077  mov     [rsp+78h+plsnUndoNext], rax; plsnUndoNext
0x14080307c  lea     rdx, [rbp+ppvBuffer]; ppvBuffer
0x140803080  mov     [rsp+78h+plsnUser], 0; plsnUser
0x140803089  call    cs:__imp_ClfsReadNextLogRecord
0x140803090  nop     dword ptr [rax+rax+00h]
0x140803095  mov     ebx, eax
0x140803097  test    eax, eax
0x140803099  js      short loc_1408030D5
0x14080309b  mov     rdi, [rbp+ppvBuffer]
0x14080309f  mov     edx, [rbp+pcbBuffer]
0x1408030a2  mov     rcx, rdi
0x1408030a5  call    CmpVerifyBigLogRecordChunk
0x1408030aa  mov     ebx, eax
0x1408030ac  test    eax, eax
0x1408030ae  js      short loc_1408030D5
0x1408030b0  add     r13, [rbp+var_10]
0x1408030b4  jmp     loc_14080301C
0x1408030b9  test    r14d, r14d
0x1408030bc  jnz     short loc_1408030D0
0x1408030be  mov     rax, [rbp+arg_18]
0x1408030c2  xor     ebx, ebx
0x1408030c4  mov     [rax], rsi
0x1408030c7  mov     rax, [rbp+arg_20]
0x1408030cb  mov     [rax], r15d
0x1408030ce  jmp     short loc_1408030DD
0x1408030d0  mov     ebx, 0C000003Eh
0x1408030d5  mov     rcx, rsi; Privileges
0x1408030d8  call    CmSiFreeMemory
0x1408030dd  mov     eax, ebx
0x1408030df  add     rsp, 78h
0x1408030e3  pop     r15
0x1408030e5  pop     r14
0x1408030e7  pop     r13
0x1408030e9  pop     r12
0x1408030eb  pop     rdi
0x1408030ec  pop     rsi
0x1408030ed  pop     rbx
0x1408030ee  pop     rbp
0x1408030ef  retn
```
