# BwcDeleteLine

- ea: `0x14001231c`
- end: `0x1400123b4`
- name: `BwcDeleteLine`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140012174`

## callees

- `0x14001231c`
- `0x140012d80`

## import_xrefs

- `NDIS!NdisReleaseRWLock` at `0x140012379`
- `NDIS!NdisReleaseRWLock` at `0x140012399`
- `NDIS!NdisReleaseRWLock` at `0x140012379`
- `NDIS!NdisReleaseRWLock` at `0x140012399`
- `NDIS!NdisAcquireRWLockWrite` at `0x140012343`
- `NDIS!NdisAcquireRWLockWrite` at `0x140012343`

## pseudocode

```c
void __fastcall BwcDeleteLine(__int64 a1)
{
  PNDIS_RW_LOCK_EX *v1; // rbx
  int v2; // eax
  __int64 LockState; // [rsp+30h] [rbp+8h] BYREF

  LockState = a1;
  v1 = (PNDIS_RW_LOCK_EX *)BwcVirtualLine;
  LOWORD(LockState) = 0;
  BYTE2(LockState) = 0;
  NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)BwcVirtualLine, (PLOCK_STATE_EX)&LockState, 0);
  v2 = *((_DWORD *)v1 + 56);
  if ( v2 == 2 )
  {
    *((_DWORD *)v1 + 56) = 0;
    *((_DWORD *)v1 + 54) |= 1u;
  }
  else
  {
    if ( !v2 )
    {
      NdisReleaseRWLock(*v1, (PLOCK_STATE_EX)&LockState);
      return;
    }
    *((_DWORD *)v1 + 56) = 0;
  }
  NdisReleaseRWLock(*v1, (PLOCK_STATE_EX)&LockState);
  BwcLineDereference(v1);
}

```

## disassembly

```asm
0x14001231c  mov     [rsp+LockState], rcx
0x140012321  push    rbx
0x140012322  sub     rsp, 20h
0x140012326  mov     rbx, cs:BwcVirtualLine
0x14001232d  lea     rdx, [rsp+28h+LockState]; LockState
0x140012332  xor     eax, eax
0x140012334  xor     r8d, r8d; Flags
0x140012337  mov     word ptr [rsp+28h+LockState], ax
0x14001233c  mov     byte ptr [rsp+28h+LockState+2], al
0x140012340  mov     rcx, [rbx]; Lock
0x140012343  call    cs:__imp_NdisAcquireRWLockWrite
0x14001234a  nop     dword ptr [rax+rax+00h]
0x14001234f  mov     eax, [rbx+0E0h]
0x140012355  cmp     eax, 2
0x140012358  jnz     short loc_14001236D
0x14001235a  mov     dword ptr [rbx+0E0h], 0
0x140012364  or      dword ptr [rbx+0D8h], 1
0x14001236b  jmp     short loc_140012391
0x14001236d  test    eax, eax
0x14001236f  jnz     short loc_140012387
0x140012371  mov     rcx, [rbx]; Lock
0x140012374  lea     rdx, [rsp+28h+LockState]; LockState
0x140012379  call    cs:__imp_NdisReleaseRWLock
0x140012380  nop     dword ptr [rax+rax+00h]
0x140012385  jmp     short loc_1400123AD
0x140012387  mov     dword ptr [rbx+0E0h], 0
0x140012391  mov     rcx, [rbx]; Lock
0x140012394  lea     rdx, [rsp+28h+LockState]; LockState
0x140012399  call    cs:__imp_NdisReleaseRWLock
0x1400123a0  nop     dword ptr [rax+rax+00h]
0x1400123a5  mov     rcx, rbx; P
0x1400123a8  call    BwcLineDereference
0x1400123ad  add     rsp, 20h
0x1400123b1  pop     rbx
0x1400123b2  retn
```
