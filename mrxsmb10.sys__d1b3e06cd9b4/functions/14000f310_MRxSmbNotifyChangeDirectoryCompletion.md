# MRxSmbNotifyChangeDirectoryCompletion

- ea: `0x14000f310`
- end: `0x14000f483`
- name: `MRxSmbNotifyChangeDirectoryCompletion`
- size: `371`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14000f310`
- `0x140028520`
- `0x14004ab70`
- `0x14004b1b0`
- `0x140052944`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000f3ee`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f3ee`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f346`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f346`
- `ntoskrnl!DbgPrint` at `0x14000f45a`
- `ntoskrnl!DbgPrint` at `0x14000f45a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f46b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f46b`
- `rdbss!RxLowIoCompletion` at `0x14000f407`
- `rdbss!RxLowIoCompletion` at `0x14000f407`
- `mrxsmb!FsRtlValidateChangeNotifyBuffer` at `0x14000f3a3`
- `mrxsmb!FsRtlValidateChangeNotifyBuffer` at `0x14000f3a3`

## string_xrefs

- `0x14000f439`: `MRxSmbNotifyChangeDirectoryCompletion`

## pseudocode

```c
void __fastcall MRxSmbNotifyChangeDirectoryCompletion(_QWORD *P)
{
  __int64 v1; // rdi
  unsigned __int8 *v3; // rbx
  __int64 v4; // rcx
  bool v5; // r14
  int *v6; // rsi
  int v7; // eax
  __int64 v8; // rax
  int v9; // edx

  v1 = P[1];
  v3 = 0;
  if ( (unsigned __int8)MRxSmbNonTrivialFileName(v1) )
  {
    MRxSmbInvalidateFullDirectoryCache(v4);
    MRxSmbInvalidateFullDirectoryCacheParent(v1, 0);
  }
  s_SmbCeDbSpinLockSavedIrql = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
  v5 = _InterlockedAdd((volatile signed __int32 *)P, 0xFFFFFFFF) == 0;
  if ( v1 )
  {
    v3 = *(unsigned __int8 **)(v1 + 224);
    v6 = (int *)P + 29;
    if ( !v3 )
      goto LABEL_11;
    if ( *v6 == -1073741637 || *v6 == -1073741822 )
      *(_BYTE *)(*((_QWORD *)v3 + 10) + 508LL) = 1;
    if ( *v6
      || (v7 = FsRtlValidateChangeNotifyBuffer(*(_QWORD *)(v1 + 552), *((unsigned int *)v3 + 109)), (*v6 = v7) != 0) )
    {
LABEL_11:
      v8 = 0;
    }
    else
    {
      v8 = *((unsigned int *)v3 + 109);
    }
    *(_QWORD *)(v1 + 184) = v8;
    v9 = *v6;
    *(_DWORD *)(v1 + 176) = *v6;
    if ( !v8 && !v9 )
      *(_DWORD *)(v1 + 176) = 268;
  }
  KeReleaseSpinLock(&s_SmbCeDbSpinLock, s_SmbCeDbSpinLockSavedIrql);
  if ( v5 )
  {
    if ( v1 )
      RxLowIoCompletion((PRX_CONTEXT)v1);
    if ( v3 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v3 + 1, 0xFFFFFFFF) == 1 )
        SmbCeDiscardExchange(v3);
      if ( SmbCeTraceExchangeReferenceCount )
        DbgPrint(
          "Dereference Exchange %p Type(%ld) %s %ld %ld\n",
          v3,
          *v3,
          "MRxSmbNotifyChangeDirectoryCompletion",
          497,
          *((_DWORD *)v3 + 1));
    }
    ExFreePoolWithTag(P, 0);
  }
}

```

## disassembly

```asm
0x14000f310  push    rbx
0x14000f312  push    rbp
0x14000f313  push    rsi
0x14000f314  push    rdi
0x14000f315  push    r14
0x14000f317  sub     rsp, 30h
0x14000f31b  mov     rdi, [rcx+8]
0x14000f31f  mov     rbp, rcx
0x14000f322  mov     rcx, rdi
0x14000f325  xor     ebx, ebx
0x14000f327  call    MRxSmbNonTrivialFileName
0x14000f32c  test    al, al
0x14000f32e  jz      short loc_14000F33F
0x14000f330  call    MRxSmbInvalidateFullDirectoryCache
0x14000f335  xor     edx, edx
0x14000f337  mov     rcx, rdi
0x14000f33a  call    MRxSmbInvalidateFullDirectoryCacheParent
0x14000f33f  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x14000f346  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000f34d  nop     dword ptr [rax+rax+00h]
0x14000f352  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x14000f358  lock add dword ptr [rbp+0], 0FFFFFFFFh
0x14000f35d  setz    r14b
0x14000f361  test    rdi, rdi
0x14000f364  jz      short loc_14000F3E1
0x14000f366  mov     rbx, [rdi+0E0h]
0x14000f36d  lea     rsi, [rbp+74h]
0x14000f371  test    rbx, rbx
0x14000f374  jz      short loc_14000F3BD
0x14000f376  mov     eax, [rsi]
0x14000f378  cmp     eax, 0C00000BBh
0x14000f37d  jz      short loc_14000F386
0x14000f37f  cmp     eax, 0C0000002h
0x14000f384  jnz     short loc_14000F391
0x14000f386  mov     rax, [rbx+50h]
0x14000f38a  mov     byte ptr [rax+1FCh], 1
0x14000f391  cmp     dword ptr [rsi], 0
0x14000f394  jnz     short loc_14000F3BD
0x14000f396  mov     edx, [rbx+1B4h]
0x14000f39c  mov     rcx, [rdi+228h]
0x14000f3a3  call    cs:__imp_FsRtlValidateChangeNotifyBuffer
0x14000f3aa  nop     dword ptr [rax+rax+00h]
0x14000f3af  mov     [rsi], eax
0x14000f3b1  test    eax, eax
0x14000f3b3  jnz     short loc_14000F3BD
0x14000f3b5  mov     eax, [rbx+1B4h]
0x14000f3bb  jmp     short loc_14000F3BF
0x14000f3bd  xor     eax, eax
0x14000f3bf  mov     [rdi+0B8h], rax
0x14000f3c6  mov     edx, [rsi]
0x14000f3c8  mov     [rdi+0B0h], edx
0x14000f3ce  test    rax, rax
0x14000f3d1  jnz     short loc_14000F3E1
0x14000f3d3  test    edx, edx
0x14000f3d5  jnz     short loc_14000F3E1
0x14000f3d7  mov     dword ptr [rdi+0B0h], 10Ch
0x14000f3e1  mov     dl, cs:s_SmbCeDbSpinLockSavedIrql; NewIrql
0x14000f3e7  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x14000f3ee  call    cs:__imp_KeReleaseSpinLock
0x14000f3f5  nop     dword ptr [rax+rax+00h]
0x14000f3fa  test    r14b, r14b
0x14000f3fd  jz      short loc_14000F477
0x14000f3ff  test    rdi, rdi
0x14000f402  jz      short loc_14000F413
0x14000f404  mov     rcx, rdi; RxContext
0x14000f407  call    cs:__imp_RxLowIoCompletion
0x14000f40e  nop     dword ptr [rax+rax+00h]
0x14000f413  test    rbx, rbx
0x14000f416  jz      short loc_14000F466
0x14000f418  or      eax, 0FFFFFFFFh
0x14000f41b  lock xadd [rbx+4], eax
0x14000f420  cmp     eax, 1
0x14000f423  jnz     short loc_14000F42D
0x14000f425  mov     rcx, rbx; pContext
0x14000f428  call    SmbCeDiscardExchange
0x14000f42d  cmp     cs:SmbCeTraceExchangeReferenceCount, 0
0x14000f434  jz      short loc_14000F466
0x14000f436  mov     eax, [rbx+4]
0x14000f439  lea     r9, aMrxsmbnotifych_0; "MRxSmbNotifyChangeDirectoryCompletion"
0x14000f440  movzx   r8d, byte ptr [rbx]
0x14000f444  lea     rcx, aDereferenceExc; "Dereference Exchange %p Type(%ld) %s %l"...
0x14000f44b  mov     [rsp+58h+var_30], eax
0x14000f44f  mov     rdx, rbx
0x14000f452  mov     [rsp+58h+var_38], 1F1h
0x14000f45a  call    cs:__imp_DbgPrint
0x14000f461  nop     dword ptr [rax+rax+00h]
0x14000f466  xor     edx, edx; Tag
0x14000f468  mov     rcx, rbp; P
0x14000f46b  call    cs:__imp_ExFreePoolWithTag
0x14000f472  nop     dword ptr [rax+rax+00h]
0x14000f477  add     rsp, 30h
0x14000f47b  pop     r14
0x14000f47d  pop     rdi
0x14000f47e  pop     rsi
0x14000f47f  pop     rbp
0x14000f480  pop     rbx
0x14000f481  retn
```
