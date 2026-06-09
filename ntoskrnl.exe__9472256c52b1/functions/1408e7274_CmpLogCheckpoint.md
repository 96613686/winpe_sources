# CmpLogCheckpoint

- ea: `0x1408e7274`
- end: `0x1408e757f`
- name: `CmpLogCheckpoint`
- size: `779`
- prototype: `__int64 __fastcall(__int64, __int64, char)`
- caller_count: `3`
- callee_count: `11`
- tags: ``

## callers

- `0x1408e5fb0`
- `0x1408e6d24`
- `0x1408e7110`

## callees

- `0x140214b30`
- `0x140251fe0`
- `0x14025be90`
- `0x14036f270`
- `0x1404f72f0`
- `0x1406dc8c0`
- `0x1406f7380`
- `0x1408e7274`
- `0x140bb1410`
- `0x140bb19f0`
- `0x140bfaa50`

## import_xrefs

- `ext-ms-win-fs-clfs-l1-1-0!ClfsWriteRestartArea` at `0x1408e7481`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsWriteRestartArea` at `0x1408e7481`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x1408e731a`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x1408e7358`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x1408e73ba`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x1408e731a`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x1408e7358`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x1408e73ba`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnContainer` at `0x1408e732e`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnContainer` at `0x1408e733f`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnContainer` at `0x1408e732e`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnContainer` at `0x1408e733f`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x1408e7370`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x1408e7370`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x1408e73d8`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x1408e7422`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x1408e74ca`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x1408e73d8`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x1408e7422`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x1408e74ca`

## pseudocode

```c
__int64 __fastcall CmpLogCheckpoint(__int64 a1, __int64 a2, char a3)
{
  struct _KTHREAD *CurrentThread; // rcx
  const CLFS_LSN *v6; // rsi
  CLFS_CONTAINER_ID v7; // ebx
  const CLFS_LSN *NextElement; // rax
  NTSTATUS LogFileInformation; // ebx
  CLFS_INFORMATION *Pool2; // rax
  CLFS_INFORMATION *v11; // rsi
  void *v12; // rcx
  NTSTATUS v13; // eax
  CLFS_INFORMATION *v14; // rax
  CLFS_INFORMATION *v15; // rsi
  ULONG v17[2]; // [rsp+40h] [rbp-C0h] BYREF
  CLFS_LSN plsn; // [rsp+48h] [rbp-B8h] BYREF
  ULONG pcbInfoBuffer; // [rsp+50h] [rbp-B0h] BYREF
  CLFS_LSN pvRestartBuffer; // [rsp+58h] [rbp-A8h] BYREF
  CLFS_LSN plsnNext; // [rsp+60h] [rbp-A0h] BYREF
  CLFS_INFORMATION pinfoBuffer; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v23[32]; // [rsp+F0h] [rbp-10h] BYREF
  ULONG *v24; // [rsp+110h] [rbp+10h]
  __int64 v25; // [rsp+118h] [rbp+18h]

  plsn.ullOffset = CLFS_LSN_INVALID_EXT;
  plsnNext = *(CLFS_LSN *)&CLFS_LSN_NULL_EXT;
  *(_QWORD *)v17 = 0;
  pvRestartBuffer.ullOffset = 0;
  pcbInfoBuffer = 120;
  memset_0(&pinfoBuffer, 0, sizeof(pinfoBuffer));
  CurrentThread = KeGetCurrentThread();
  --CurrentThread->KernelApcDisable;
  ExAcquireFastMutexUnsafe(&CmpTransactionListLock);
  while ( 1 )
  {
    NextElement = (const CLFS_LSN *)CmListGetNextElement(a1 + 16, v17, 0);
    if ( !NextElement )
      break;
    v6 = NextElement + 13;
    if ( !ClfsLsnInvalid(NextElement + 13) )
    {
      v7 = ClfsLsnContainer((const CLFS_LSN *)(a1 + 120));
      if ( ClfsLsnContainer(v6) == v7 )
      {
        ExReleaseFastMutexUnsafe(&CmpTransactionListLock);
        KeLeaveCriticalRegion();
        return 0;
      }
    }
    if ( ClfsLsnInvalid(&plsn) || ClfsLsnLess(v6, &plsn) )
      plsn = *v6;
  }
  LogFileInformation = 0;
  ExReleaseFastMutexUnsafe(&CmpTransactionListLock);
  KeLeaveCriticalRegion();
  if ( ClfsLsnInvalid(&plsn) )
  {
    LogFileInformation = ClfsGetLogFileInformation(*(PLOG_FILE_OBJECT *)(a1 + 88), &pinfoBuffer, &pcbInfoBuffer);
    if ( LogFileInformation >= 0 )
      plsn = pinfoBuffer.LastLsn;
  }
  v17[0] = 120;
  Pool2 = (CLFS_INFORMATION *)ExAllocatePool2(256, 120, 538987843);
  v11 = Pool2;
  if ( Pool2 )
  {
    ClfsGetLogFileInformation(*(PLOG_FILE_OBJECT *)(a1 + 88), Pool2, v17);
    ExFreePoolWithTag(v11, 0);
  }
  if ( LogFileInformation >= 0 )
  {
    v12 = *(void **)(a1 + 96);
    pvRestartBuffer = plsn;
    v13 = ClfsWriteRestartArea(
            v12,
            &pvRestartBuffer,
            8u,
            (PCLFS_LSN)((unsigned __int64)&plsn & -(__int64)(a3 != 0)),
            0,
            &pcbInfoBuffer,
            &plsnNext);
    LogFileInformation = v13;
    if ( a3 )
    {
      if ( v13 >= 0 )
        *(CLFS_LSN *)(a1 + 120) = plsn;
    }
  }
  v17[0] = 120;
  v14 = (CLFS_INFORMATION *)ExAllocatePool2(256, 120, 538987843);
  v15 = v14;
  if ( v14 )
  {
    ClfsGetLogFileInformation(*(PLOG_FILE_OBJECT *)(a1 + 88), v14, v17);
    ExFreePoolWithTag(v15, 0);
  }
  if ( (unsigned int)dword_140E0D678 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_140E0D678, 1) )
    {
      v17[0] = LogFileInformation;
      v24 = v17;
      v25 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140E0D678, byte_140057E43, 0, 0, 3, v23);
    }
  }
  return (unsigned int)LogFileInformation;
}

```

## disassembly

```asm
0x1408e7274  mov     [rsp-8+arg_8], rbx
0x1408e7279  mov     [rsp-8+arg_10], rsi
0x1408e727e  push    rbp
0x1408e727f  push    rdi
0x1408e7280  push    r13
0x1408e7282  push    r14
0x1408e7284  push    r15
0x1408e7286  lea     rbp, [rsp-30h]
0x1408e728b  sub     rsp, 130h
0x1408e7292  mov     rax, cs:__security_cookie
0x1408e7299  xor     rax, rsp
0x1408e729c  mov     [rbp+50h+var_30], rax
0x1408e72a0  mov     rax, cs:CLFS_LSN_INVALID_EXT
0x1408e72a7  mov     r13d, 78h ; 'x'
0x1408e72ad  mov     qword ptr [rsp+150h+plsn], rax
0x1408e72b2  mov     r15b, r8b
0x1408e72b5  mov     rax, cs:CLFS_LSN_NULL_EXT
0x1408e72bc  mov     rdi, rcx
0x1408e72bf  mov     r8d, r13d; Size
0x1408e72c2  mov     qword ptr [rsp+150h+var_F0], rax
0x1408e72c7  xor     edx, edx; Val
0x1408e72c9  mov     qword ptr [rsp+150h+var_110], 0
0x1408e72d2  lea     rcx, [rsp+150h+pinfoBuffer]; void *
0x1408e72d7  mov     [rsp+150h+pvRestartBuffer], 0
0x1408e72e0  mov     [rsp+150h+pcbInfoBuffer], r13d
0x1408e72e5  call    memset_0
0x1408e72ea  mov     rcx, gs:188h
0x1408e72f3  movzx   eax, word ptr [rcx+1E4h]
0x1408e72fa  dec     ax
0x1408e72fd  mov     [rcx+1E4h], ax
0x1408e7304  lea     rcx, CmpTransactionListLock; FastMutex
0x1408e730b  nop
0x1408e730c  call    ExAcquireFastMutexUnsafe
0x1408e7311  jmp     short loc_1408E7388
0x1408e7313  lea     rsi, [rax+68h]
0x1408e7317  mov     rcx, rsi; plsn
0x1408e731a  call    cs:__imp_ClfsLsnInvalid
0x1408e7321  nop     dword ptr [rax+rax+00h]
0x1408e7326  test    al, al
0x1408e7328  jnz     short loc_1408E7353
0x1408e732a  lea     rcx, [rdi+78h]; plsn
0x1408e732e  call    cs:__imp_ClfsLsnContainer
0x1408e7335  nop     dword ptr [rax+rax+00h]
0x1408e733a  mov     rcx, rsi; plsn
0x1408e733d  mov     ebx, eax
0x1408e733f  call    cs:__imp_ClfsLsnContainer
0x1408e7346  nop     dword ptr [rax+rax+00h]
0x1408e734b  cmp     eax, ebx
0x1408e734d  jz      loc_1408E756A
0x1408e7353  lea     rcx, [rsp+150h+plsn]; plsn
0x1408e7358  call    cs:__imp_ClfsLsnInvalid
0x1408e735f  nop     dword ptr [rax+rax+00h]
0x1408e7364  test    al, al
0x1408e7366  jnz     short loc_1408E7380
0x1408e7368  lea     rdx, [rsp+150h+plsn]; plsn2
0x1408e736d  mov     rcx, rsi; plsn1
0x1408e7370  call    cs:__imp_ClfsLsnLess
0x1408e7377  nop     dword ptr [rax+rax+00h]
0x1408e737c  test    al, al
0x1408e737e  jz      short loc_1408E7388
0x1408e7380  mov     rax, [rsi]
0x1408e7383  mov     qword ptr [rsp+150h+plsn], rax
0x1408e7388  xor     r8d, r8d
0x1408e738b  lea     rdx, [rsp+150h+var_110]
0x1408e7390  lea     rcx, [rdi+10h]
0x1408e7394  call    CmListGetNextElement
0x1408e7399  test    rax, rax
0x1408e739c  jnz     loc_1408E7313
0x1408e73a2  lea     rcx, CmpTransactionListLock; FastMutex
0x1408e73a9  xor     ebx, ebx
0x1408e73ab  call    ExReleaseFastMutexUnsafe
0x1408e73b0  call    KeLeaveCriticalRegion
0x1408e73b5  lea     rcx, [rsp+150h+plsn]; plsn
0x1408e73ba  call    cs:__imp_ClfsLsnInvalid
0x1408e73c1  nop     dword ptr [rax+rax+00h]
0x1408e73c6  test    al, al
0x1408e73c8  jz      short loc_1408E73F3
0x1408e73ca  mov     rcx, [rdi+58h]; plfoLog
0x1408e73ce  lea     r8, [rsp+150h+pcbInfoBuffer]; pcbInfoBuffer
0x1408e73d3  lea     rdx, [rsp+150h+pinfoBuffer]; pinfoBuffer
0x1408e73d8  call    cs:__imp_ClfsGetLogFileInformation
0x1408e73df  nop     dword ptr [rax+rax+00h]
0x1408e73e4  mov     ebx, eax
0x1408e73e6  test    eax, eax
0x1408e73e8  js      short loc_1408E73F3
0x1408e73ea  mov     rcx, qword ptr [rbp+50h+pinfoBuffer.LastLsn]
0x1408e73ee  mov     qword ptr [rsp+150h+plsn], rcx
0x1408e73f3  mov     r14d, 20204D43h
0x1408e73f9  mov     [rsp+150h+var_110], r13d
0x1408e73fe  mov     r8d, r14d
0x1408e7401  mov     rdx, r13
0x1408e7404  mov     ecx, 100h
0x1408e7409  call    ExAllocatePool2
0x1408e740e  mov     rsi, rax
0x1408e7411  test    rax, rax
0x1408e7414  jz      short loc_1408E7438
0x1408e7416  mov     rcx, [rdi+58h]; plfoLog
0x1408e741a  lea     r8, [rsp+150h+var_110]; pcbInfoBuffer
0x1408e741f  mov     rdx, rax; pinfoBuffer
0x1408e7422  call    cs:__imp_ClfsGetLogFileInformation
0x1408e7429  nop     dword ptr [rax+rax+00h]
0x1408e742e  xor     edx, edx; Tag
0x1408e7430  mov     rcx, rsi; P
0x1408e7433  call    ExFreePoolWithTag
0x1408e7438  test    ebx, ebx
0x1408e743a  js      short loc_1408E74A1
0x1408e743c  mov     rax, qword ptr [rsp+150h+plsn]
0x1408e7441  lea     rdx, [rsp+150h+pvRestartBuffer]; pvRestartBuffer
0x1408e7446  mov     rcx, [rdi+60h]; pvMarshalContext
0x1408e744a  mov     r8d, 8; cbRestartBuffer
0x1408e7450  mov     [rsp+150h+pvRestartBuffer], rax
0x1408e7455  mov     al, r15b
0x1408e7458  neg     al
0x1408e745a  lea     rax, [rsp+150h+plsn]
0x1408e745f  sbb     r9, r9
0x1408e7462  and     r9, rax; plsnBase
0x1408e7465  lea     rax, [rsp+150h+var_F0]
0x1408e746a  mov     [rsp+150h+plsnNext], rax; plsnNext
0x1408e746f  lea     rax, [rsp+150h+pcbInfoBuffer]
0x1408e7474  mov     [rsp+150h+pcbWritten], rax; pcbWritten
0x1408e7479  mov     [rsp+150h+fFlags], 0; fFlags
0x1408e7481  call    cs:__imp_ClfsWriteRestartArea
0x1408e7488  nop     dword ptr [rax+rax+00h]
0x1408e748d  mov     ebx, eax
0x1408e748f  test    r15b, r15b
0x1408e7492  jz      short loc_1408E74A1
0x1408e7494  test    eax, eax
0x1408e7496  js      short loc_1408E74A1
0x1408e7498  mov     rax, qword ptr [rsp+150h+plsn]
0x1408e749d  mov     [rdi+78h], rax
0x1408e74a1  mov     r8d, r14d
0x1408e74a4  mov     [rsp+150h+var_110], r13d
0x1408e74a9  mov     rdx, r13
0x1408e74ac  mov     ecx, 100h
0x1408e74b1  call    ExAllocatePool2
0x1408e74b6  mov     rsi, rax
0x1408e74b9  test    rax, rax
0x1408e74bc  jz      short loc_1408E74E0
0x1408e74be  mov     rcx, [rdi+58h]; plfoLog
0x1408e74c2  lea     r8, [rsp+150h+var_110]; pcbInfoBuffer
0x1408e74c7  mov     rdx, rax; pinfoBuffer
0x1408e74ca  call    cs:__imp_ClfsGetLogFileInformation
0x1408e74d1  nop     dword ptr [rax+rax+00h]
0x1408e74d6  xor     edx, edx; Tag
0x1408e74d8  mov     rcx, rsi; P
0x1408e74db  call    ExFreePoolWithTag
0x1408e74e0  mov     eax, cs:dword_140E0D678
0x1408e74e6  cmp     eax, 5
0x1408e74e9  jbe     short loc_1408E753F
0x1408e74eb  mov     edx, 1
0x1408e74f0  lea     rcx, dword_140E0D678
0x1408e74f7  call    _tlgKeywordOn
0x1408e74fc  test    al, al
0x1408e74fe  jz      short loc_1408E753F
0x1408e7500  lea     rax, [rsp+150h+var_110]
0x1408e7505  mov     [rsp+150h+var_110], ebx
0x1408e7509  mov     [rbp+50h+var_40], rax
0x1408e750d  lea     rdx, byte_140057E43
0x1408e7514  lea     rax, [rbp+50h+var_60]
0x1408e7518  mov     [rbp+50h+var_38], 4
0x1408e7520  mov     [rsp+150h+pcbWritten], rax
0x1408e7525  lea     rcx, dword_140E0D678
0x1408e752c  xor     r9d, r9d
0x1408e752f  mov     [rsp+150h+fFlags], 3
0x1408e7537  xor     r8d, r8d
0x1408e753a  call    _tlgWriteTransfer_EtwWriteTransfer
0x1408e753f  mov     eax, ebx
0x1408e7541  mov     rcx, [rbp+50h+var_30]
0x1408e7545  xor     rcx, rsp; StackCookie
0x1408e7548  call    __security_check_cookie
0x1408e754d  lea     r11, [rsp+150h+var_20]
0x1408e7555  mov     rbx, [r11+38h]
0x1408e7559  mov     rsi, [r11+40h]
0x1408e755d  mov     rsp, r11
0x1408e7560  pop     r15
0x1408e7562  pop     r14
0x1408e7564  pop     r13
0x1408e7566  pop     rdi
0x1408e7567  pop     rbp
0x1408e7568  retn
0x1408e756a  lea     rcx, CmpTransactionListLock; FastMutex
0x1408e7571  call    ExReleaseFastMutexUnsafe
0x1408e7576  call    KeLeaveCriticalRegion
0x1408e757b  xor     eax, eax
0x1408e757d  jmp     short loc_1408E7541
```
