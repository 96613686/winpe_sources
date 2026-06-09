# PcpFilterStatusWanLineUpdate

- ea: `0x14000f1fc`
- end: `0x14000f3d1`
- name: `PcpFilterStatusWanLineUpdate`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14000ee88`

## callees

- `0x1400020f0`
- `0x140003770`
- `0x14000f1fc`
- `0x1400131e0`

## import_xrefs

- `NDIS!NdisFIndicateStatus` at `0x14000f38b`
- `NDIS!NdisFIndicateStatus` at `0x14000f38b`
- `NDIS!NdisAcquireRWLockRead` at `0x14000f246`
- `NDIS!NdisAcquireRWLockRead` at `0x14000f2fa`
- `NDIS!NdisAcquireRWLockRead` at `0x14000f246`
- `NDIS!NdisAcquireRWLockRead` at `0x14000f2fa`
- `NDIS!NdisReleaseRWLock` at `0x14000f27f`
- `NDIS!NdisReleaseRWLock` at `0x14000f2dc`
- `NDIS!NdisReleaseRWLock` at `0x14000f338`
- `NDIS!NdisReleaseRWLock` at `0x14000f3aa`
- `NDIS!NdisReleaseRWLock` at `0x14000f27f`
- `NDIS!NdisReleaseRWLock` at `0x14000f2dc`
- `NDIS!NdisReleaseRWLock` at `0x14000f338`
- `NDIS!NdisReleaseRWLock` at `0x14000f3aa`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000f29a`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000f29a`

## pseudocode

```c
__int64 __fastcall PcpFilterStatusWanLineUpdate(__int64 a1, struct _NDIS_STATUS_INDICATION *a2)
{
  bool v3; // cf
  unsigned int *StatusBuffer; // rbp
  volatile signed __int32 *v7; // rdi
  volatile signed __int32 *v8; // rbx
  int v9; // [rsp+38h] [rbp-40h]
  __int64 v10; // [rsp+40h] [rbp-38h]
  struct _LOCK_STATE_EX LockState; // [rsp+88h] [rbp+10h] BYREF

  v3 = a2->StatusBufferSize < 0x40;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  if ( v3 )
    return 3221225485LL;
  StatusBuffer = (unsigned int *)a2->StatusBuffer;
  NdisAcquireRWLockRead(PcgLineListLock, &LockState, 0);
  v7 = (volatile signed __int32 *)PcgLineList;
  while ( v7 != (volatile signed __int32 *)&PcgLineList )
  {
    _InterlockedIncrement(v7 + 62);
    NdisReleaseRWLock(PcgLineListLock, &LockState);
    NdisAcquireRWLockWrite(*((PNDIS_RW_LOCK_EX *)v7 + 2), &LockState, 0);
    if ( (unsigned int)(*((_DWORD *)v7 + 61) - 1) <= 1
      && !memcmp((const void *)(v7 + 82), (char *)StatusBuffer + 14, 6u) )
    {
      *((_WORD *)StatusBuffer + 7) = *((_WORD *)v7 + 120);
      *((_WORD *)StatusBuffer + 10) = *((_WORD *)v7 + 167);
      NdisReleaseRWLock(*((PNDIS_RW_LOCK_EX *)v7 + 2), &LockState);
      PcpLineUpdate(
        (__int64)v7,
        0,
        0,
        0,
        100 * ((unsigned __int64)*StatusBuffer >> 3),
        0,
        StatusBuffer[1],
        v9,
        v10,
        -1,
        -1);
      NdisFIndicateStatus(*(NDIS_HANDLE *)(a1 + 40), a2);
      PcpLineDereference((PVOID)v7);
      return 0;
    }
    v8 = v7;
    NdisReleaseRWLock(*((PNDIS_RW_LOCK_EX *)v7 + 2), &LockState);
    NdisAcquireRWLockRead(PcgLineListLock, &LockState, 0);
    v7 = *(volatile signed __int32 **)v7;
    PcpLineDereference((PVOID)v8);
  }
  NdisReleaseRWLock(PcgLineListLock, &LockState);
  return 3221225473LL;
}

```

## disassembly

```asm
0x14000f1fc  mov     r11, rsp
0x14000f1ff  mov     [r11+8], rbx
0x14000f203  mov     [r11+18h], rbp
0x14000f207  push    rsi
0x14000f208  push    rdi
0x14000f209  push    r14
0x14000f20b  sub     rsp, 60h
0x14000f20f  xor     eax, eax
0x14000f211  mov     rsi, rdx
0x14000f214  cmp     dword ptr [rdx+38h], 40h ; '@'
0x14000f218  mov     r14, rcx
0x14000f21b  mov     [r11+10h], ax
0x14000f220  mov     [r11+12h], al
0x14000f224  jnb     short loc_14000F230
0x14000f226  mov     eax, 0C000000Dh
0x14000f22b  jmp     loc_14000F3BB
0x14000f230  mov     rbp, [rdx+30h]
0x14000f234  xor     r8d, r8d; Flags
0x14000f237  mov     rcx, cs:PcgLineListLock; Lock
0x14000f23e  lea     rdx, [rsp+78h+LockState]; LockState
0x14000f246  call    cs:__imp_NdisAcquireRWLockRead
0x14000f24d  nop     dword ptr [rax+rax+00h]
0x14000f252  mov     rdi, cs:PcgLineList
0x14000f259  lea     rax, PcgLineList
0x14000f260  lea     rdx, [rsp+78h+LockState]; LockState
0x14000f268  cmp     rdi, rax
0x14000f26b  jz      loc_14000F3A3
0x14000f271  lock inc dword ptr [rdi+0F8h]
0x14000f278  mov     rcx, cs:PcgLineListLock; Lock
0x14000f27f  call    cs:__imp_NdisReleaseRWLock
0x14000f286  nop     dword ptr [rax+rax+00h]
0x14000f28b  mov     rcx, [rdi+10h]; Lock
0x14000f28f  lea     rdx, [rsp+78h+LockState]; LockState
0x14000f297  xor     r8d, r8d; Flags
0x14000f29a  call    cs:__imp_NdisAcquireRWLockWrite
0x14000f2a1  nop     dword ptr [rax+rax+00h]
0x14000f2a6  mov     eax, [rdi+0F4h]
0x14000f2ac  dec     eax
0x14000f2ae  cmp     eax, 1
0x14000f2b1  ja      short loc_14000F2CD
0x14000f2b3  lea     rcx, [rdi+148h]; Buf1
0x14000f2ba  mov     r8d, 6; Size
0x14000f2c0  lea     rdx, [rbp+0Eh]; Buf2
0x14000f2c4  call    memcmp
0x14000f2c9  test    eax, eax
0x14000f2cb  jz      short loc_14000F316
0x14000f2cd  mov     rcx, [rdi+10h]; Lock
0x14000f2d1  lea     rdx, [rsp+78h+LockState]; LockState
0x14000f2d9  mov     rbx, rdi
0x14000f2dc  call    cs:__imp_NdisReleaseRWLock
0x14000f2e3  nop     dword ptr [rax+rax+00h]
0x14000f2e8  mov     rcx, cs:PcgLineListLock; Lock
0x14000f2ef  lea     rdx, [rsp+78h+LockState]; LockState
0x14000f2f7  xor     r8d, r8d; Flags
0x14000f2fa  call    cs:__imp_NdisAcquireRWLockRead
0x14000f301  nop     dword ptr [rax+rax+00h]
0x14000f306  mov     rdi, [rdi]
0x14000f309  mov     rcx, rbx; P
0x14000f30c  call    PcpLineDereference
0x14000f311  jmp     loc_14000F259
0x14000f316  movzx   eax, word ptr [rdi+0F0h]
0x14000f31d  lea     rdx, [rsp+78h+LockState]; LockState
0x14000f325  mov     [rbp+0Eh], ax
0x14000f329  movzx   eax, word ptr [rdi+14Eh]
0x14000f330  mov     [rbp+14h], ax
0x14000f334  mov     rcx, [rdi+10h]; Lock
0x14000f338  call    cs:__imp_NdisReleaseRWLock
0x14000f33f  nop     dword ptr [rax+rax+00h]
0x14000f344  mov     eax, [rbp+0]
0x14000f347  xor     r9d, r9d
0x14000f34a  mov     [rsp+78h+var_28], 0FFFFFFFFh
0x14000f352  xor     r8d, r8d
0x14000f355  shr     rax, 3
0x14000f359  mov     rcx, rdi
0x14000f35c  imul    rdx, rax, 64h ; 'd'
0x14000f360  mov     eax, [rbp+4]
0x14000f363  mov     [rsp+78h+var_30], 0FFFFFFFFFFFFFFFFh
0x14000f36c  mov     [rsp+78h+var_48], eax
0x14000f370  mov     [rsp+78h+var_50], 0
0x14000f378  mov     [rsp+78h+var_58], rdx
0x14000f37d  xor     edx, edx
0x14000f37f  call    PcpLineUpdate
0x14000f384  mov     rcx, [r14+28h]; NdisFilterHandle
0x14000f388  mov     rdx, rsi; StatusIndication
0x14000f38b  call    cs:__imp_NdisFIndicateStatus
0x14000f392  nop     dword ptr [rax+rax+00h]
0x14000f397  mov     rcx, rdi; P
0x14000f39a  call    PcpLineDereference
0x14000f39f  xor     eax, eax
0x14000f3a1  jmp     short loc_14000F3BB
0x14000f3a3  mov     rcx, cs:PcgLineListLock; Lock
0x14000f3aa  call    cs:__imp_NdisReleaseRWLock
0x14000f3b1  nop     dword ptr [rax+rax+00h]
0x14000f3b6  mov     eax, 0C0000001h
0x14000f3bb  lea     r11, [rsp+78h+var_18]
0x14000f3c0  mov     rbx, [r11+20h]
0x14000f3c4  mov     rbp, [r11+30h]
0x14000f3c8  mov     rsp, r11
0x14000f3cb  pop     r14
0x14000f3cd  pop     rdi
0x14000f3ce  pop     rsi
0x14000f3cf  retn
```
