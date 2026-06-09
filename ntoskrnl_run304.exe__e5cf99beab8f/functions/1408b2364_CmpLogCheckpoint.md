# CmpLogCheckpoint

- ea: `0x1408b2364`
- end: `0x1408b266f`
- name: `CmpLogCheckpoint`
- size: `779`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: ``

## callers

- `0x1408b10a0`
- `0x1408b1e14`
- `0x1408b2200`

## callees

- `0x140224f90`
- `0x14029b7c0`
- `0x1402f8270`
- `0x140307510`
- `0x1404e7c00`
- `0x1406d9d70`
- `0x1406f4880`
- `0x1408b2364`
- `0x140bae410`
- `0x140bae8e0`
- `0x140bf7a50`

## import_xrefs

- `ext-ms-win-fs-clfs-l1-1-0!ClfsWriteRestartArea` at `0x1408b2571`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsWriteRestartArea` at `0x1408b2571`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x1408b240a`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x1408b2448`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x1408b24aa`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x1408b240a`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x1408b2448`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x1408b24aa`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnContainer` at `0x1408b241e`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnContainer` at `0x1408b242f`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnContainer` at `0x1408b241e`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnContainer` at `0x1408b242f`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x1408b2460`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x1408b2460`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x1408b24c8`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x1408b2512`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x1408b25ba`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x1408b24c8`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x1408b2512`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x1408b25ba`

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
  PCLFS_LSN plsnNext; // [rsp+30h] [rbp-D0h]
  ULONG v18[2]; // [rsp+40h] [rbp-C0h] BYREF
  CLFS_LSN plsn; // [rsp+48h] [rbp-B8h] BYREF
  ULONG pcbInfoBuffer; // [rsp+50h] [rbp-B0h] BYREF
  CLFS_LSN pvRestartBuffer; // [rsp+58h] [rbp-A8h] BYREF
  CLFS_LSN v22; // [rsp+60h] [rbp-A0h] BYREF
  CLFS_INFORMATION pinfoBuffer; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v24[32]; // [rsp+F0h] [rbp-10h] BYREF
  ULONG *v25; // [rsp+110h] [rbp+10h]
  __int64 v26; // [rsp+118h] [rbp+18h]

  plsn.ullOffset = CLFS_LSN_INVALID_EXT;
  v22 = *(CLFS_LSN *)&CLFS_LSN_NULL_EXT;
  *(_QWORD *)v18 = 0;
  pvRestartBuffer.ullOffset = 0;
  pcbInfoBuffer = 120;
  memset_0(&pinfoBuffer, 0, sizeof(pinfoBuffer));
  CurrentThread = KeGetCurrentThread();
  --CurrentThread->KernelApcDisable;
  ExAcquireFastMutexUnsafe(&CmpTransactionListLock);
  while ( 1 )
  {
    NextElement = (const CLFS_LSN *)CmListGetNextElement(a1 + 16, v18, 0);
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
  v18[0] = 120;
  Pool2 = (CLFS_INFORMATION *)ExAllocatePool2(256, 120, 538987843);
  v11 = Pool2;
  if ( Pool2 )
  {
    ClfsGetLogFileInformation(*(PLOG_FILE_OBJECT *)(a1 + 88), Pool2, v18);
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
            &v22);
    LogFileInformation = v13;
    if ( a3 )
    {
      if ( v13 >= 0 )
        *(CLFS_LSN *)(a1 + 120) = plsn;
    }
  }
  v18[0] = 120;
  v14 = (CLFS_INFORMATION *)ExAllocatePool2(256, 120, 538987843);
  v15 = v14;
  if ( v14 )
  {
    ClfsGetLogFileInformation(*(PLOG_FILE_OBJECT *)(a1 + 88), v14, v18);
    ExFreePoolWithTag(v15, 0);
  }
  if ( (unsigned int)dword_140E0D678 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_140E0D678, 1) )
    {
      v18[0] = LogFileInformation;
      v25 = v18;
      v26 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140E0D678, word_1400581DA, 0, 0, 3, v24, plsnNext);
    }
  }
  return (unsigned int)LogFileInformation;
}

```

## disassembly

```asm
0x1408b2364  mov     [rsp-8+arg_8], rbx
0x1408b2369  mov     [rsp-8+arg_10], rsi
0x1408b236e  push    rbp
0x1408b236f  push    rdi
0x1408b2370  push    r13
0x1408b2372  push    r14
0x1408b2374  push    r15
0x1408b2376  lea     rbp, [rsp-30h]
0x1408b237b  sub     rsp, 130h
0x1408b2382  mov     rax, cs:__security_cookie
0x1408b2389  xor     rax, rsp
0x1408b238c  mov     [rbp+50h+var_30], rax
0x1408b2390  mov     rax, cs:CLFS_LSN_INVALID_EXT
0x1408b2397  mov     r13d, 78h ; 'x'
0x1408b239d  mov     qword ptr [rsp+150h+plsn], rax
0x1408b23a2  mov     r15b, r8b
0x1408b23a5  mov     rax, cs:CLFS_LSN_NULL_EXT
0x1408b23ac  mov     rdi, rcx
0x1408b23af  mov     r8d, r13d; Size
0x1408b23b2  mov     qword ptr [rsp+150h+var_F0], rax
0x1408b23b7  xor     edx, edx; Val
0x1408b23b9  mov     qword ptr [rsp+150h+var_110], 0
0x1408b23c2  lea     rcx, [rsp+150h+pinfoBuffer]; void *
0x1408b23c7  mov     [rsp+150h+pvRestartBuffer], 0
0x1408b23d0  mov     [rsp+150h+pcbInfoBuffer], r13d
0x1408b23d5  call    memset_0
0x1408b23da  mov     rcx, gs:188h
0x1408b23e3  movzx   eax, word ptr [rcx+1E4h]
0x1408b23ea  dec     ax
0x1408b23ed  mov     [rcx+1E4h], ax
0x1408b23f4  lea     rcx, CmpTransactionListLock; FastMutex
0x1408b23fb  nop
0x1408b23fc  call    ExAcquireFastMutexUnsafe
0x1408b2401  jmp     short loc_1408B2478
0x1408b2403  lea     rsi, [rax+68h]
0x1408b2407  mov     rcx, rsi; plsn
0x1408b240a  call    cs:__imp_ClfsLsnInvalid
0x1408b2411  nop     dword ptr [rax+rax+00h]
0x1408b2416  test    al, al
0x1408b2418  jnz     short loc_1408B2443
0x1408b241a  lea     rcx, [rdi+78h]; plsn
0x1408b241e  call    cs:__imp_ClfsLsnContainer
0x1408b2425  nop     dword ptr [rax+rax+00h]
0x1408b242a  mov     rcx, rsi; plsn
0x1408b242d  mov     ebx, eax
0x1408b242f  call    cs:__imp_ClfsLsnContainer
0x1408b2436  nop     dword ptr [rax+rax+00h]
0x1408b243b  cmp     eax, ebx
0x1408b243d  jz      loc_1408B265A
0x1408b2443  lea     rcx, [rsp+150h+plsn]; plsn
0x1408b2448  call    cs:__imp_ClfsLsnInvalid
0x1408b244f  nop     dword ptr [rax+rax+00h]
0x1408b2454  test    al, al
0x1408b2456  jnz     short loc_1408B2470
0x1408b2458  lea     rdx, [rsp+150h+plsn]; plsn2
0x1408b245d  mov     rcx, rsi; plsn1
0x1408b2460  call    cs:__imp_ClfsLsnLess
0x1408b2467  nop     dword ptr [rax+rax+00h]
0x1408b246c  test    al, al
0x1408b246e  jz      short loc_1408B2478
0x1408b2470  mov     rax, [rsi]
0x1408b2473  mov     qword ptr [rsp+150h+plsn], rax
0x1408b2478  xor     r8d, r8d
0x1408b247b  lea     rdx, [rsp+150h+var_110]
0x1408b2480  lea     rcx, [rdi+10h]
0x1408b2484  call    CmListGetNextElement
0x1408b2489  test    rax, rax
0x1408b248c  jnz     loc_1408B2403
0x1408b2492  lea     rcx, CmpTransactionListLock; FastMutex
0x1408b2499  xor     ebx, ebx
0x1408b249b  call    ExReleaseFastMutexUnsafe
0x1408b24a0  call    KeLeaveCriticalRegion
0x1408b24a5  lea     rcx, [rsp+150h+plsn]; plsn
0x1408b24aa  call    cs:__imp_ClfsLsnInvalid
0x1408b24b1  nop     dword ptr [rax+rax+00h]
0x1408b24b6  test    al, al
0x1408b24b8  jz      short loc_1408B24E3
0x1408b24ba  mov     rcx, [rdi+58h]; plfoLog
0x1408b24be  lea     r8, [rsp+150h+pcbInfoBuffer]; pcbInfoBuffer
0x1408b24c3  lea     rdx, [rsp+150h+pinfoBuffer]; pinfoBuffer
0x1408b24c8  call    cs:__imp_ClfsGetLogFileInformation
0x1408b24cf  nop     dword ptr [rax+rax+00h]
0x1408b24d4  mov     ebx, eax
0x1408b24d6  test    eax, eax
0x1408b24d8  js      short loc_1408B24E3
0x1408b24da  mov     rcx, qword ptr [rbp+50h+pinfoBuffer.LastLsn]
0x1408b24de  mov     qword ptr [rsp+150h+plsn], rcx
0x1408b24e3  mov     r14d, 20204D43h
0x1408b24e9  mov     [rsp+150h+var_110], r13d
0x1408b24ee  mov     r8d, r14d
0x1408b24f1  mov     rdx, r13
0x1408b24f4  mov     ecx, 100h
0x1408b24f9  call    ExAllocatePool2
0x1408b24fe  mov     rsi, rax
0x1408b2501  test    rax, rax
0x1408b2504  jz      short loc_1408B2528
0x1408b2506  mov     rcx, [rdi+58h]; plfoLog
0x1408b250a  lea     r8, [rsp+150h+var_110]; pcbInfoBuffer
0x1408b250f  mov     rdx, rax; pinfoBuffer
0x1408b2512  call    cs:__imp_ClfsGetLogFileInformation
0x1408b2519  nop     dword ptr [rax+rax+00h]
0x1408b251e  xor     edx, edx; Tag
0x1408b2520  mov     rcx, rsi; P
0x1408b2523  call    ExFreePoolWithTag
0x1408b2528  test    ebx, ebx
0x1408b252a  js      short loc_1408B2591
0x1408b252c  mov     rax, qword ptr [rsp+150h+plsn]
0x1408b2531  lea     rdx, [rsp+150h+pvRestartBuffer]; pvRestartBuffer
0x1408b2536  mov     rcx, [rdi+60h]; pvMarshalContext
0x1408b253a  mov     r8d, 8; cbRestartBuffer
0x1408b2540  mov     [rsp+150h+pvRestartBuffer], rax
0x1408b2545  mov     al, r15b
0x1408b2548  neg     al
0x1408b254a  lea     rax, [rsp+150h+plsn]
0x1408b254f  sbb     r9, r9
0x1408b2552  and     r9, rax; plsnBase
0x1408b2555  lea     rax, [rsp+150h+var_F0]
0x1408b255a  mov     [rsp+150h+plsnNext], rax; plsnNext
0x1408b255f  lea     rax, [rsp+150h+pcbInfoBuffer]
0x1408b2564  mov     [rsp+150h+pcbWritten], rax; pcbWritten
0x1408b2569  mov     [rsp+150h+fFlags], 0; fFlags
0x1408b2571  call    cs:__imp_ClfsWriteRestartArea
0x1408b2578  nop     dword ptr [rax+rax+00h]
0x1408b257d  mov     ebx, eax
0x1408b257f  test    r15b, r15b
0x1408b2582  jz      short loc_1408B2591
0x1408b2584  test    eax, eax
0x1408b2586  js      short loc_1408B2591
0x1408b2588  mov     rax, qword ptr [rsp+150h+plsn]
0x1408b258d  mov     [rdi+78h], rax
0x1408b2591  mov     r8d, r14d
0x1408b2594  mov     [rsp+150h+var_110], r13d
0x1408b2599  mov     rdx, r13
0x1408b259c  mov     ecx, 100h
0x1408b25a1  call    ExAllocatePool2
0x1408b25a6  mov     rsi, rax
0x1408b25a9  test    rax, rax
0x1408b25ac  jz      short loc_1408B25D0
0x1408b25ae  mov     rcx, [rdi+58h]; plfoLog
0x1408b25b2  lea     r8, [rsp+150h+var_110]; pcbInfoBuffer
0x1408b25b7  mov     rdx, rax; pinfoBuffer
0x1408b25ba  call    cs:__imp_ClfsGetLogFileInformation
0x1408b25c1  nop     dword ptr [rax+rax+00h]
0x1408b25c6  xor     edx, edx; Tag
0x1408b25c8  mov     rcx, rsi; P
0x1408b25cb  call    ExFreePoolWithTag
0x1408b25d0  mov     eax, cs:dword_140E0D678
0x1408b25d6  cmp     eax, 5
0x1408b25d9  jbe     short loc_1408B262F
0x1408b25db  mov     edx, 1
0x1408b25e0  lea     rcx, dword_140E0D678
0x1408b25e7  call    _tlgKeywordOn
0x1408b25ec  test    al, al
0x1408b25ee  jz      short loc_1408B262F
0x1408b25f0  lea     rax, [rsp+150h+var_110]
0x1408b25f5  mov     [rsp+150h+var_110], ebx
0x1408b25f9  mov     [rbp+50h+var_40], rax
0x1408b25fd  lea     rdx, word_1400581DA
0x1408b2604  lea     rax, [rbp+50h+var_60]
0x1408b2608  mov     [rbp+50h+var_38], 4
0x1408b2610  mov     [rsp+150h+pcbWritten], rax
0x1408b2615  lea     rcx, dword_140E0D678
0x1408b261c  xor     r9d, r9d
0x1408b261f  mov     [rsp+150h+fFlags], 3
0x1408b2627  xor     r8d, r8d
0x1408b262a  call    _tlgWriteTransfer_EtwWriteTransfer
0x1408b262f  mov     eax, ebx
0x1408b2631  mov     rcx, [rbp+50h+var_30]
0x1408b2635  xor     rcx, rsp; StackCookie
0x1408b2638  call    __security_check_cookie
0x1408b263d  lea     r11, [rsp+150h+var_20]
0x1408b2645  mov     rbx, [r11+38h]
0x1408b2649  mov     rsi, [r11+40h]
0x1408b264d  mov     rsp, r11
0x1408b2650  pop     r15
0x1408b2652  pop     r14
0x1408b2654  pop     r13
0x1408b2656  pop     rdi
0x1408b2657  pop     rbp
0x1408b2658  retn
0x1408b265a  lea     rcx, CmpTransactionListLock; FastMutex
0x1408b2661  call    ExReleaseFastMutexUnsafe
0x1408b2666  call    KeLeaveCriticalRegion
0x1408b266b  xor     eax, eax
0x1408b266d  jmp     short loc_1408B2631
```
