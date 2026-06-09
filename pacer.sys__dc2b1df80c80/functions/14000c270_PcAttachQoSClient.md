# PcAttachQoSClient

- ea: `0x14000c270`
- end: `0x14000c37a`
- name: `PcAttachQoSClient`
- size: `266`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int16 *, __int64 *, __int64 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x14000c270`
- `0x140013600`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000c297`
- `ntoskrnl!ExAllocatePool2` at `0x14000c297`
- `NDIS!NdisReleaseRWLock` at `0x14000c362`
- `NDIS!NdisReleaseRWLock` at `0x14000c362`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000c31f`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000c31f`

## pseudocode

```c
__int64 __fastcall PcAttachQoSClient(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int16 *a5,
        __int64 *a6,
        __int64 **a7)
{
  void *Pool2; // rax
  __int64 v10; // rbx
  __int64 *v12; // rcx
  __int64 *v13; // rax
  struct _NDIS_RW_LOCK_EX *v14; // rcx
  struct _LOCK_STATE_EX LockState; // [rsp+20h] [rbp-38h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  Pool2 = (void *)ExAllocatePool2(64, 64, 1666412369);
  v10 = (__int64)Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  memset(Pool2, 0, 0x40u);
  *(_QWORD *)(v10 + 24) = a5;
  v12 = &PcpQoSProviderDispatchPrivate;
  *(_QWORD *)(v10 + 16) = a4;
  *(_QWORD *)(v10 + 48) = a1;
  *(_BYTE *)(v10 + 56) = *a5 < 0;
  *a6 = v10;
  if ( !*(_BYTE *)(v10 + 56) )
    v12 = &PcpQoSProviderDispatch;
  *a7 = v12;
  _InterlockedIncrement((volatile signed __int32 *)(v10 + 32));
  NdisAcquireRWLockWrite(PcgQoSClientListLock, &LockState, 0);
  v13 = (__int64 *)qword_140018688;
  if ( *(__int64 **)qword_140018688 != &PcgQoSClientList )
    __fastfail(3u);
  *(_QWORD *)v10 = &PcgQoSClientList;
  v14 = PcgQoSClientListLock;
  *(_QWORD *)(v10 + 8) = v13;
  *v13 = v10;
  qword_140018688 = v10;
  NdisReleaseRWLock(v14, &LockState);
  return 0;
}

```

## disassembly

```asm
0x14000c270  push    rbx
0x14000c272  push    rbp
0x14000c273  push    rsi
0x14000c274  push    rdi
0x14000c275  sub     rsp, 38h
0x14000c279  xor     eax, eax
0x14000c27b  mov     rsi, rcx
0x14000c27e  mov     r8d, 63536F51h
0x14000c284  mov     word ptr [rsp+58h+LockState.OldIrql], ax
0x14000c289  mov     rdi, r9
0x14000c28c  mov     [rsp+58h+LockState.Flags], al
0x14000c290  lea     ebp, [rax+40h]
0x14000c293  mov     edx, ebp
0x14000c295  mov     ecx, ebp
0x14000c297  call    cs:__imp_ExAllocatePool2
0x14000c29e  nop     dword ptr [rax+rax+00h]
0x14000c2a3  mov     rbx, rax
0x14000c2a6  test    rax, rax
0x14000c2a9  jnz     short loc_14000C2B5
0x14000c2ab  mov     eax, 0C000009Ah
0x14000c2b0  jmp     loc_14000C370
0x14000c2b5  mov     r8, rbp; Size
0x14000c2b8  xor     edx, edx; Val
0x14000c2ba  mov     rcx, rbx; void *
0x14000c2bd  call    memset
0x14000c2c2  mov     rax, [rsp+58h+arg_20]
0x14000c2ca  lea     rdx, PcpQoSProviderDispatch
0x14000c2d1  mov     [rbx+18h], rax
0x14000c2d5  lea     rcx, PcpQoSProviderDispatchPrivate
0x14000c2dc  mov     [rbx+10h], rdi
0x14000c2e0  mov     [rbx+30h], rsi
0x14000c2e4  movzx   eax, word ptr [rax]
0x14000c2e7  shr     ax, 0Fh
0x14000c2eb  mov     [rbx+38h], al
0x14000c2ee  mov     rax, [rsp+58h+arg_28]
0x14000c2f6  mov     [rax], rbx
0x14000c2f9  cmp     byte ptr [rbx+38h], 0
0x14000c2fd  mov     rax, [rsp+58h+arg_30]
0x14000c305  cmovz   rcx, rdx
0x14000c309  mov     [rax], rcx
0x14000c30c  lock inc dword ptr [rbx+20h]
0x14000c310  mov     rcx, cs:PcgQoSClientListLock; Lock
0x14000c317  lea     rdx, [rsp+58h+LockState]; LockState
0x14000c31c  xor     r8d, r8d; Flags
0x14000c31f  call    cs:__imp_NdisAcquireRWLockWrite
0x14000c326  nop     dword ptr [rax+rax+00h]
0x14000c32b  mov     rax, cs:qword_140018688
0x14000c332  lea     rcx, PcgQoSClientList
0x14000c339  cmp     [rax], rcx
0x14000c33c  jz      short loc_14000C345
0x14000c33e  mov     ecx, 3
0x14000c343  int     29h; Win8: RtlFailFast(ecx)
0x14000c345  mov     [rbx], rcx
0x14000c348  lea     rdx, [rsp+58h+LockState]; LockState
0x14000c34d  mov     rcx, cs:PcgQoSClientListLock; Lock
0x14000c354  mov     [rbx+8], rax
0x14000c358  mov     [rax], rbx
0x14000c35b  mov     cs:qword_140018688, rbx
0x14000c362  call    cs:__imp_NdisReleaseRWLock
0x14000c369  nop     dword ptr [rax+rax+00h]
0x14000c36e  xor     eax, eax
0x14000c370  add     rsp, 38h
0x14000c374  pop     rdi
0x14000c375  pop     rsi
0x14000c376  pop     rbp
0x14000c377  pop     rbx
0x14000c378  retn
```
