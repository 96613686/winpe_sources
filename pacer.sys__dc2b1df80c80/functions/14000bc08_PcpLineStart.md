# PcpLineStart

- ea: `0x14000bc08`
- end: `0x14000bc7e`
- name: `PcpLineStart`
- size: `118`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400010e0`
- `0x14000d8b8`
- `0x14000ee88`

## callees

- `0x140002500`
- `0x14000bc08`

## import_xrefs

- `NDIS!NdisReleaseRWLock` at `0x14000bc46`
- `NDIS!NdisReleaseRWLock` at `0x14000bc5e`
- `NDIS!NdisReleaseRWLock` at `0x14000bc46`
- `NDIS!NdisReleaseRWLock` at `0x14000bc5e`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000bc28`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000bc28`

## pseudocode

```c
void __fastcall PcpLineStart(__int64 a1)
{
  struct _NDIS_RW_LOCK_EX *v2; // rcx
  struct _NDIS_RW_LOCK_EX *v3; // rcx
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp+8h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  v2 = *(struct _NDIS_RW_LOCK_EX **)(a1 + 16);
  LockState.Flags = 0;
  NdisAcquireRWLockWrite(v2, &LockState, 0);
  v3 = *(struct _NDIS_RW_LOCK_EX **)(a1 + 16);
  if ( *(_DWORD *)(a1 + 244) == 1 )
  {
    *(_DWORD *)(a1 + 244) = 2;
    NdisReleaseRWLock(v3, &LockState);
    PcpTcIndicateInterfaceChange(a1, 1073807375);
  }
  else
  {
    NdisReleaseRWLock(v3, &LockState);
  }
}

```

## disassembly

```asm
0x14000bc08  push    rbx
0x14000bc0a  sub     rsp, 20h
0x14000bc0e  xor     eax, eax
0x14000bc10  lea     rdx, [rsp+28h+LockState]; LockState
0x14000bc15  mov     rbx, rcx
0x14000bc18  mov     word ptr [rsp+28h+LockState.OldIrql], ax
0x14000bc1d  mov     rcx, [rcx+10h]; Lock
0x14000bc21  xor     r8d, r8d; Flags
0x14000bc24  mov     [rsp+28h+LockState.Flags], al
0x14000bc28  call    cs:__imp_NdisAcquireRWLockWrite
0x14000bc2f  nop     dword ptr [rax+rax+00h]
0x14000bc34  cmp     dword ptr [rbx+0F4h], 1
0x14000bc3b  lea     rdx, [rsp+28h+LockState]; LockState
0x14000bc40  mov     rcx, [rbx+10h]; Lock
0x14000bc44  jz      short loc_14000BC54
0x14000bc46  call    cs:__imp_NdisReleaseRWLock
0x14000bc4d  nop     dword ptr [rax+rax+00h]
0x14000bc52  jmp     short loc_14000BC77
0x14000bc54  mov     dword ptr [rbx+0F4h], 2
0x14000bc5e  call    cs:__imp_NdisReleaseRWLock
0x14000bc65  nop     dword ptr [rax+rax+00h]
0x14000bc6a  mov     edx, 4001000Fh
0x14000bc6f  mov     rcx, rbx
0x14000bc72  call    PcpTcIndicateInterfaceChange
0x14000bc77  add     rsp, 20h
0x14000bc7b  pop     rbx
0x14000bc7c  retn
```
