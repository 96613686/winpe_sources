# PcpCollectNetworkAddressList

- ea: `0x140002594`
- end: `0x1400026bd`
- name: `PcpCollectNetworkAddressList`
- size: `297`
- prototype: `__int64 __fastcall(__int64, unsigned int *, _WORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140002500`
- `0x140010360`
- `0x14001f140`

## callees

- `0x140002594`
- `0x140013300`
- `0x140013600`

## import_xrefs

- `NDIS!NdisAcquireRWLockRead` at `0x1400025be`
- `NDIS!NdisAcquireRWLockRead` at `0x1400025be`
- `NDIS!NdisReleaseRWLock` at `0x14000266c`
- `NDIS!NdisReleaseRWLock` at `0x14000268e`
- `NDIS!NdisReleaseRWLock` at `0x14000266c`
- `NDIS!NdisReleaseRWLock` at `0x14000268e`

## pseudocode

```c
__int64 __fastcall PcpCollectNetworkAddressList(__int64 a1, unsigned int *a2, _WORD *a3)
{
  int v6; // edi
  unsigned int v7; // edi
  __int64 v8; // rax
  _DWORD *v9; // rcx
  const void *v10; // rdx
  __int64 result; // rax
  struct _LOCK_STATE_EX LockState; // [rsp+50h] [rbp+8h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(a1 + 16), &LockState, 0);
  if ( *(_QWORD *)(a1 + 320) )
    v6 = *(_DWORD *)(a1 + 312);
  else
    v6 = 6;
  v7 = v6 + 532;
  if ( *a2 < v7 )
  {
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 16), &LockState);
    result = 3221225507LL;
    *a2 = v7;
  }
  else
  {
    memset(a3, 0, *a2);
    memmove(a3 + 1, *(const void **)(a1 + 288), *(unsigned __int16 *)(a1 + 280));
    *a3 = *(_WORD *)(a1 + 280);
    *((_QWORD *)a3 + 65) = *(_QWORD *)(a1 + 296);
    v8 = *(_QWORD *)(a1 + 256);
    if ( v8 )
      LODWORD(v8) = *(_DWORD *)(v8 + 16);
    *((_DWORD *)a3 + 132) = v8;
    v9 = a3 + 266;
    v10 = *(const void **)(a1 + 320);
    if ( v10 )
    {
      memmove(v9, v10, *(unsigned int *)(a1 + 312));
    }
    else
    {
      *v9 = 0;
      a3[268] = 0;
    }
    *a2 = v7;
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 16), &LockState);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140002594  push    rbx
0x140002596  push    rsi
0x140002597  push    rdi
0x140002598  push    r14
0x14000259a  sub     rsp, 28h
0x14000259e  xor     eax, eax
0x1400025a0  mov     r14, r8
0x1400025a3  mov     rsi, rdx
0x1400025a6  mov     word ptr [rsp+48h+LockState.OldIrql], ax
0x1400025ab  mov     rbx, rcx
0x1400025ae  mov     [rsp+48h+LockState.Flags], al
0x1400025b2  mov     rcx, [rcx+10h]; Lock
0x1400025b6  lea     rdx, [rsp+48h+LockState]; LockState
0x1400025bb  xor     r8d, r8d; Flags
0x1400025be  call    cs:__imp_NdisAcquireRWLockRead
0x1400025c5  nop     dword ptr [rax+rax+00h]
0x1400025ca  cmp     qword ptr [rbx+140h], 0
0x1400025d2  jz      loc_1400026A3
0x1400025d8  mov     edi, [rbx+138h]
0x1400025de  mov     eax, [rsi]
0x1400025e0  add     edi, 214h
0x1400025e6  cmp     eax, edi
0x1400025e8  jb      loc_140002685
0x1400025ee  mov     r8d, eax; Size
0x1400025f1  xor     edx, edx; Val
0x1400025f3  mov     rcx, r14; void *
0x1400025f6  call    memset
0x1400025fb  movzx   r8d, word ptr [rbx+118h]; Size
0x140002603  lea     rcx, [r14+2]; void *
0x140002607  mov     rdx, [rbx+120h]; Src
0x14000260e  call    memmove
0x140002613  movzx   eax, word ptr [rbx+118h]
0x14000261a  mov     [r14], ax
0x14000261e  mov     rax, [rbx+128h]
0x140002625  mov     [r14+208h], rax
0x14000262c  mov     rax, [rbx+100h]
0x140002633  test    rax, rax
0x140002636  jz      short loc_1400026AD
0x140002638  mov     eax, [rax+10h]
0x14000263b  mov     [r14+210h], eax
0x140002642  lea     rcx, [r14+214h]; void *
0x140002649  mov     rdx, [rbx+140h]; Src
0x140002650  test    rdx, rdx
0x140002653  jz      short loc_1400026AF
0x140002655  mov     r8d, [rbx+138h]; Size
0x14000265c  call    memmove
0x140002661  mov     [rsi], edi
0x140002663  lea     rdx, [rsp+48h+LockState]; LockState
0x140002668  mov     rcx, [rbx+10h]; Lock
0x14000266c  call    cs:__imp_NdisReleaseRWLock
0x140002673  nop     dword ptr [rax+rax+00h]
0x140002678  xor     eax, eax
0x14000267a  add     rsp, 28h
0x14000267e  pop     r14
0x140002680  pop     rdi
0x140002681  pop     rsi
0x140002682  pop     rbx
0x140002683  retn
0x140002685  mov     rcx, [rbx+10h]; Lock
0x140002689  lea     rdx, [rsp+48h+LockState]; LockState
0x14000268e  call    cs:__imp_NdisReleaseRWLock
0x140002695  nop     dword ptr [rax+rax+00h]
0x14000269a  mov     eax, 0C0000023h
0x14000269f  mov     [rsi], edi
0x1400026a1  jmp     short loc_14000267A
0x1400026a3  mov     edi, 6
0x1400026a8  jmp     loc_1400025DE
0x1400026ad  jmp     short loc_14000263B
0x1400026af  xor     eax, eax
0x1400026b1  mov     dword ptr [rcx], 0
0x1400026b7  mov     [rcx+4], ax
0x1400026bb  jmp     short loc_140002661
```
