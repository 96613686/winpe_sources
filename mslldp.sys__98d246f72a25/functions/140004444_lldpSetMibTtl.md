# lldpSetMibTtl

- ea: `0x140004444`
- end: `0x1400044ee`
- name: `lldpSetMibTtl`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140011a40`

## import_xrefs

- `NDIS!NdisReleaseRWLock` at `0x1400044d6`
- `NDIS!NdisReleaseRWLock` at `0x1400044d6`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000446e`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000446e`

## pseudocode

```c
void __fastcall lldpSetMibTtl(__int64 a1, __int16 a2)
{
  struct _NDIS_RW_LOCK_EX *v4; // rcx
  __int64 v5; // r8
  __int16 v6; // ax
  struct _NDIS_RW_LOCK_EX *v7; // rcx
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp+8h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  v4 = *(struct _NDIS_RW_LOCK_EX **)(a1 + 976);
  LockState.Flags = 0;
  NdisAcquireRWLockWrite(v4, &LockState, 0);
  v5 = *(unsigned int *)(a1 + 984);
  v6 = *(_WORD *)(v5 + a1 + 996) & 0xFF07;
  *(_WORD *)(v5 + a1 + 998) = __ROR2__(a2, 8);
  *(_WORD *)(v5 + a1 + 996) = v6 | 6;
  *(_BYTE *)(v5 + a1 + 997) = 2;
  *(_WORD *)(v5 + a1 + 996) &= ~1u;
  v7 = *(struct _NDIS_RW_LOCK_EX **)(a1 + 976);
  *(_BYTE *)(a1 + 151) = 1;
  NdisReleaseRWLock(v7, &LockState);
}

```

## disassembly

```asm
0x140004444  mov     [rsp+arg_8], rbx
0x140004449  push    rdi
0x14000444a  sub     rsp, 20h
0x14000444e  xor     eax, eax
0x140004450  movzx   ebx, dx
0x140004453  mov     rdi, rcx
0x140004456  mov     word ptr [rsp+28h+LockState.OldIrql], ax
0x14000445b  mov     rcx, [rcx+3D0h]; Lock
0x140004462  lea     rdx, [rsp+28h+LockState]; LockState
0x140004467  xor     r8d, r8d; Flags
0x14000446a  mov     [rsp+28h+LockState.Flags], al
0x14000446e  call    cs:__imp_NdisAcquireRWLockWrite
0x140004475  nop     dword ptr [rax+rax+00h]
0x14000447a  mov     r8d, [rdi+3D8h]
0x140004481  lea     rdx, [rsp+28h+LockState]; LockState
0x140004486  mov     ecx, 0FF07h
0x14000448b  ror     bx, 8
0x14000448f  movzx   eax, word ptr [r8+rdi+3E4h]
0x140004498  and     ax, cx
0x14000449b  mov     [r8+rdi+3E6h], bx
0x1400044a4  or      ax, 6
0x1400044a8  mov     [r8+rdi+3E4h], ax
0x1400044b1  mov     eax, 0FFFEh
0x1400044b6  mov     byte ptr [r8+rdi+3E5h], 2
0x1400044bf  and     [r8+rdi+3E4h], ax
0x1400044c8  mov     rcx, [rdi+3D0h]; Lock
0x1400044cf  mov     byte ptr [rdi+97h], 1
0x1400044d6  call    cs:__imp_NdisReleaseRWLock
0x1400044dd  nop     dword ptr [rax+rax+00h]
0x1400044e2  mov     rbx, [rsp+28h+arg_8]
0x1400044e7  add     rsp, 20h
0x1400044eb  pop     rdi
0x1400044ec  retn
```
