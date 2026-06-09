# PcpProcessSettingsChange

- ea: `0x14000b5e0`
- end: `0x14000b85f`
- name: `PcpProcessSettingsChange`
- size: `639`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x14000c218`
- `0x14001fc20`
- `0x14001fd60`

## callees

- `0x1400020f0`
- `0x140003770`
- `0x1400039a0`
- `0x14000b5e0`
- `0x14000b91c`
- `0x14001fee0`

## import_xrefs

- `NDIS!NdisAcquireRWLockRead` at `0x14000b647`
- `NDIS!NdisAcquireRWLockRead` at `0x14000b68b`
- `NDIS!NdisAcquireRWLockRead` at `0x14000b738`
- `NDIS!NdisAcquireRWLockRead` at `0x14000b77d`
- `NDIS!NdisAcquireRWLockRead` at `0x14000b817`
- `NDIS!NdisAcquireRWLockRead` at `0x14000b647`
- `NDIS!NdisAcquireRWLockRead` at `0x14000b68b`
- `NDIS!NdisAcquireRWLockRead` at `0x14000b738`
- `NDIS!NdisAcquireRWLockRead` at `0x14000b77d`
- `NDIS!NdisAcquireRWLockRead` at `0x14000b817`
- `NDIS!NdisReleaseRWLock` at `0x14000b674`
- `NDIS!NdisReleaseRWLock` at `0x14000b6b0`
- `NDIS!NdisReleaseRWLock` at `0x14000b71e`
- `NDIS!NdisReleaseRWLock` at `0x14000b763`
- `NDIS!NdisReleaseRWLock` at `0x14000b7c3`
- `NDIS!NdisReleaseRWLock` at `0x14000b842`
- `NDIS!NdisReleaseRWLock` at `0x14000b674`
- `NDIS!NdisReleaseRWLock` at `0x14000b6b0`
- `NDIS!NdisReleaseRWLock` at `0x14000b71e`
- `NDIS!NdisReleaseRWLock` at `0x14000b763`
- `NDIS!NdisReleaseRWLock` at `0x14000b7c3`
- `NDIS!NdisReleaseRWLock` at `0x14000b842`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000b6d3`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000b6d3`

## pseudocode

```c
void PcpProcessSettingsChange()
{
  __int64 v0; // rsi
  __int64 v1; // r14
  char v2; // di
  void *v3; // rbx
  __int128 v4; // xmm1
  __int128 v5; // xmm0
  __int64 v6; // rdx
  __int64 v7; // r8
  PVOID *v8; // rdi
  PVOID *v9; // rbx
  _OWORD v10[6]; // [rsp+60h] [rbp-9h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+D0h] [rbp+67h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  memset(v10, 0, 44);
  PcpReadSettings(0, (__int64)v10);
  *(_OWORD *)&WPP_MAIN_CB.Reserved = v10[0];
  xmmword_1400187F0 = v10[1];
  *(__int128 *)((char *)&xmmword_1400187F0 + 12) = *(_OWORD *)((char *)&v10[1] + 12);
  NdisAcquireRWLockRead(PcgFilterDriverContext, &LockState, 0);
  v0 = qword_140018828;
  while ( (__int64 *)v0 != &qword_140018828 )
  {
    v1 = v0;
    _InterlockedIncrement((volatile signed __int32 *)(v0 + 100));
    NdisReleaseRWLock(PcgFilterDriverContext, &LockState);
    NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v0 + 32), &LockState, 0);
    if ( *(_DWORD *)(v0 + 24) == 2 )
    {
      v2 = *(_BYTE *)(v0 + 211);
      v3 = *(void **)(v0 + 40);
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v0 + 32), &LockState);
      PcpReadSettings(v3, (__int64)v10);
      NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v0 + 32), &LockState, 0);
      v4 = v10[1];
      *(_OWORD *)(v0 + 168) = v10[0];
      v5 = *(_OWORD *)((char *)&v10[1] + 12);
      *(_OWORD *)(v0 + 184) = v4;
      *(_OWORD *)(v0 + 196) = v5;
      if ( !v2 && *(_BYTE *)(v0 + 211) == 1 )
        PcpFilterEnableIntercept(v0);
    }
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v0 + 32), &LockState);
    NdisAcquireRWLockRead(PcgFilterDriverContext, &LockState, 0);
    v0 = *(_QWORD *)v0;
    PcpFilterDecrementDetachCount(v1, v6, v7);
  }
  NdisReleaseRWLock(PcgFilterDriverContext, &LockState);
  NdisAcquireRWLockRead(PcgLineListLock, &LockState, 0);
  v8 = (PVOID *)PcgLineList;
  while ( v8 != &PcgLineList )
  {
    if ( v8[32] )
    {
      v9 = v8;
      _InterlockedIncrement((volatile signed __int32 *)v8 + 62);
      NdisReleaseRWLock(PcgLineListLock, &LockState);
      PcpLineUpdate(v8, 0, 0, 0, 0, 0, 0);
      NdisAcquireRWLockRead(PcgLineListLock, &LockState, 0);
      v8 = (PVOID *)*v8;
      PcpLineDereference(v9);
    }
    else
    {
      v8 = (PVOID *)*v8;
    }
  }
  NdisReleaseRWLock(PcgLineListLock, &LockState);
}

```

## disassembly

```asm
0x14000b5e0  push    rbp
0x14000b5e2  push    rbx
0x14000b5e3  push    rsi
0x14000b5e4  push    rdi
0x14000b5e5  push    r12
0x14000b5e7  push    r14
0x14000b5e9  lea     rbp, [rsp-2Fh]
0x14000b5ee  sub     rsp, 98h
0x14000b5f5  xorps   xmm0, xmm0
0x14000b5f8  lea     rdx, [rbp+57h+var_60]
0x14000b5fc  xor     eax, eax
0x14000b5fe  xor     ecx, ecx
0x14000b600  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x14000b604  mov     word ptr [rbp+57h+LockState.OldIrql], ax
0x14000b608  movups  xmmword ptr [rbp+57h+var_50+0Ch], xmm0
0x14000b60c  mov     [rbp+57h+LockState.Flags], al
0x14000b60f  movups  [rbp+57h+var_60], xmm0
0x14000b613  call    PcpReadSettings
0x14000b618  movups  xmm0, [rbp+57h+var_60]
0x14000b61c  mov     rcx, cs:PcgFilterDriverContext; Lock
0x14000b623  xor     r8d, r8d; Flags
0x14000b626  movups  xmm1, xmmword ptr [rbp+57h+var_50]
0x14000b62a  lea     rdx, [rbp+57h+LockState]; LockState
0x14000b62e  movups  xmmword ptr cs:WPP_MAIN_CB.Reserved, xmm0
0x14000b635  movups  xmm0, xmmword ptr [rbp+57h+var_50+0Ch]
0x14000b639  movups  cs:xmmword_1400187F0, xmm1
0x14000b640  movups  cs:xmmword_1400187F0+0Ch, xmm0
0x14000b647  call    cs:__imp_NdisAcquireRWLockRead
0x14000b64e  nop     dword ptr [rax+rax+00h]
0x14000b653  mov     rsi, cs:qword_140018828
0x14000b65a  lea     r12, qword_140018828
0x14000b661  jmp     loc_14000B74F
0x14000b666  mov     r14, rsi
0x14000b669  lock inc dword ptr [rsi+64h]
0x14000b66d  mov     rcx, cs:PcgFilterDriverContext; Lock
0x14000b674  call    cs:__imp_NdisReleaseRWLock
0x14000b67b  nop     dword ptr [rax+rax+00h]
0x14000b680  mov     rcx, [rsi+20h]; Lock
0x14000b684  lea     rdx, [rbp+57h+LockState]; LockState
0x14000b688  xor     r8d, r8d; Flags
0x14000b68b  call    cs:__imp_NdisAcquireRWLockRead
0x14000b692  nop     dword ptr [rax+rax+00h]
0x14000b697  cmp     dword ptr [rsi+18h], 2
0x14000b69b  jnz     short loc_14000B716
0x14000b69d  mov     rcx, [rsi+20h]; Lock
0x14000b6a1  lea     rdx, [rbp+57h+LockState]; LockState
0x14000b6a5  mov     dil, [rsi+0D3h]
0x14000b6ac  mov     rbx, [rsi+28h]
0x14000b6b0  call    cs:__imp_NdisReleaseRWLock
0x14000b6b7  nop     dword ptr [rax+rax+00h]
0x14000b6bc  lea     rdx, [rbp+57h+var_60]
0x14000b6c0  mov     rcx, rbx
0x14000b6c3  call    PcpReadSettings
0x14000b6c8  mov     rcx, [rsi+20h]; Lock
0x14000b6cc  lea     rdx, [rbp+57h+LockState]; LockState
0x14000b6d0  xor     r8d, r8d; Flags
0x14000b6d3  call    cs:__imp_NdisAcquireRWLockWrite
0x14000b6da  nop     dword ptr [rax+rax+00h]
0x14000b6df  movups  xmm0, [rbp+57h+var_60]
0x14000b6e3  movups  xmm1, xmmword ptr [rbp+57h+var_50]
0x14000b6e7  movups  xmmword ptr [rsi+0A8h], xmm0
0x14000b6ee  movups  xmm0, xmmword ptr [rbp+57h+var_50+0Ch]
0x14000b6f2  movups  xmmword ptr [rsi+0B8h], xmm1
0x14000b6f9  movups  xmmword ptr [rsi+0C4h], xmm0
0x14000b700  test    dil, dil
0x14000b703  jnz     short loc_14000B716
0x14000b705  cmp     byte ptr [rsi+0D3h], 1
0x14000b70c  jnz     short loc_14000B716
0x14000b70e  mov     rcx, rsi
0x14000b711  call    PcpFilterEnableIntercept
0x14000b716  mov     rcx, [rsi+20h]; Lock
0x14000b71a  lea     rdx, [rbp+57h+LockState]; LockState
0x14000b71e  call    cs:__imp_NdisReleaseRWLock
0x14000b725  nop     dword ptr [rax+rax+00h]
0x14000b72a  mov     rcx, cs:PcgFilterDriverContext; Lock
0x14000b731  lea     rdx, [rbp+57h+LockState]; LockState
0x14000b735  xor     r8d, r8d; Flags
0x14000b738  call    cs:__imp_NdisAcquireRWLockRead
0x14000b73f  nop     dword ptr [rax+rax+00h]
0x14000b744  mov     rsi, [rsi]
0x14000b747  mov     rcx, r14
0x14000b74a  call    PcpFilterDecrementDetachCount
0x14000b74f  lea     rdx, [rbp+57h+LockState]; LockState
0x14000b753  cmp     rsi, r12
0x14000b756  jnz     loc_14000B666
0x14000b75c  mov     rcx, cs:PcgFilterDriverContext; Lock
0x14000b763  call    cs:__imp_NdisReleaseRWLock
0x14000b76a  nop     dword ptr [rax+rax+00h]
0x14000b76f  mov     rcx, cs:PcgLineListLock; Lock
0x14000b776  lea     rdx, [rbp+57h+LockState]; LockState
0x14000b77a  xor     r8d, r8d; Flags
0x14000b77d  call    cs:__imp_NdisAcquireRWLockRead
0x14000b784  nop     dword ptr [rax+rax+00h]
0x14000b789  mov     rdi, cs:PcgLineList
0x14000b790  lea     rsi, PcgLineList
0x14000b797  jmp     loc_14000B82E
0x14000b79c  cmp     qword ptr [rdi+100h], 0
0x14000b7a4  jnz     short loc_14000B7AE
0x14000b7a6  mov     rdi, [rdi]
0x14000b7a9  jmp     loc_14000B82E
0x14000b7ae  mov     rbx, rdi
0x14000b7b1  lock inc dword ptr [rdi+0F8h]
0x14000b7b8  mov     rcx, cs:PcgLineListLock; Lock
0x14000b7bf  lea     rdx, [rbp+57h+LockState]; LockState
0x14000b7c3  call    cs:__imp_NdisReleaseRWLock
0x14000b7ca  nop     dword ptr [rax+rax+00h]
0x14000b7cf  mov     [rsp+0C0h+var_70], 0FFFFFFFFh
0x14000b7d7  xor     r9d, r9d
0x14000b7da  mov     [rsp+0C0h+var_78], 0FFFFFFFFFFFFFFFFh
0x14000b7e3  xor     r8d, r8d
0x14000b7e6  mov     [rsp+0C0h+var_90], 0
0x14000b7ee  xor     edx, edx
0x14000b7f0  mov     [rsp+0C0h+var_98], 0
0x14000b7f8  mov     rcx, rdi
0x14000b7fb  mov     [rsp+0C0h+var_A0], 0
0x14000b804  call    PcpLineUpdate
0x14000b809  mov     rcx, cs:PcgLineListLock; Lock
0x14000b810  lea     rdx, [rbp+57h+LockState]; LockState
0x14000b814  xor     r8d, r8d; Flags
0x14000b817  call    cs:__imp_NdisAcquireRWLockRead
0x14000b81e  nop     dword ptr [rax+rax+00h]
0x14000b823  mov     rdi, [rdi]
0x14000b826  mov     rcx, rbx; P
0x14000b829  call    PcpLineDereference
0x14000b82e  cmp     rdi, rsi
0x14000b831  jnz     loc_14000B79C
0x14000b837  mov     rcx, cs:PcgLineListLock; Lock
0x14000b83e  lea     rdx, [rbp+57h+LockState]; LockState
0x14000b842  call    cs:__imp_NdisReleaseRWLock
0x14000b849  nop     dword ptr [rax+rax+00h]
0x14000b84e  add     rsp, 98h
0x14000b855  pop     r14
0x14000b857  pop     r12
0x14000b859  pop     rdi
0x14000b85a  pop     rsi
0x14000b85b  pop     rbx
0x14000b85c  pop     rbp
0x14000b85d  retn
```
