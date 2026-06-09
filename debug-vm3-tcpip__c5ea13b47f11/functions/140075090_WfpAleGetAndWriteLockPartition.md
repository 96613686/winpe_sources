# WfpAleGetAndWriteLockPartition

- ea: `0x140075090`
- end: `0x140075224`
- name: `WfpAleGetAndWriteLockPartition`
- size: `404`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140074c50`
- `0x140075490`
- `0x140078c28`
- `0x140151464`
- `0x1401542e0`

## callees

- `0x140075090`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400750f2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140075153`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400751dd`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400750f2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140075153`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400751dd`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400750bb`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400751a6`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400750bb`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400751a6`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400750d4`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400751bf`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400750d4`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400751bf`
- `NDIS!NdisReleaseRWLock` at `0x140075182`
- `NDIS!NdisReleaseRWLock` at `0x140075182`

## pseudocode

```c
__int64 __fastcall WfpAleGetAndWriteLockPartition(unsigned int a1, struct _LOCK_STATE_EX *a2)
{
  int v4; // ebp
  __int64 v5; // rbx
  __int64 v6; // rdi
  KIRQL CurrentIrql; // si
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v11; // rbx
  _DWORD *v12; // rdx
  int v13; // ebp
  __int64 v14; // rdi
  KIRQL v15; // si
  __int64 v16; // r8

  v4 = *(_DWORD *)(pRemoteEndpointTable + 8);
  v5 = v4 & a1;
  v6 = pRemoteEndpointTable + (v5 << 7);
  CurrentIrql = KeGetCurrentIrql();
  NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v6 + 64), a2, 0);
  if ( CurrentIrql != 2 && gWfpPerProContext )
  {
    v8 = *(_QWORD *)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    *(_QWORD *)(v8 + 8) = MEMORY[0xFFFFF78000000008];
    *(_DWORD *)v8 = 4;
  }
  v9 = pRemoteEndpointTable;
  if ( v4 != *(_DWORD *)(pRemoteEndpointTable + 8) )
  {
    do
    {
      v11 = v9 + (v5 << 7);
      if ( gWfpPerProContext )
      {
        v12 = *(_DWORD **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
        if ( *v12 == 4 )
          *v12 = 0;
      }
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v11 + 64), a2);
      v13 = *(_DWORD *)(pRemoteEndpointTable + 8);
      v5 = v13 & a1;
      v14 = pRemoteEndpointTable + (v5 << 7);
      v15 = KeGetCurrentIrql();
      NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v14 + 64), a2, 0);
      if ( v15 != 2 && gWfpPerProContext )
      {
        v16 = *(_QWORD *)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
        *(_QWORD *)(v16 + 8) = MEMORY[0xFFFFF78000000008];
        *(_DWORD *)v16 = 4;
      }
      v9 = pRemoteEndpointTable;
    }
    while ( v13 != *(_DWORD *)(pRemoteEndpointTable + 8) );
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140075090  push    rbx
0x140075092  push    rbp
0x140075093  push    rsi
0x140075094  push    rdi
0x140075095  push    r14
0x140075097  push    r15
0x140075099  sub     rsp, 28h
0x14007509d  mov     r8, cs:pRemoteEndpointTable
0x1400750a4  mov     ebx, ecx
0x1400750a6  mov     r14, rdx
0x1400750a9  mov     r15, rcx
0x1400750ac  mov     ebp, [r8+8]
0x1400750b0  and     ebx, ebp
0x1400750b2  mov     edi, ebx
0x1400750b4  shl     rdi, 7
0x1400750b8  add     rdi, r8
0x1400750bb  call    cs:__imp_KeGetCurrentIrql
0x1400750c2  nop     dword ptr [rax+rax+00h]
0x1400750c7  mov     rcx, [rdi+40h]; Lock
0x1400750cb  xor     r8d, r8d; Flags
0x1400750ce  mov     rdx, r14; LockState
0x1400750d1  movzx   esi, al
0x1400750d4  call    cs:__imp_NdisAcquireRWLockWrite
0x1400750db  nop     dword ptr [rax+rax+00h]
0x1400750e0  cmp     sil, 2
0x1400750e4  jz      short loc_140075123
0x1400750e6  cmp     cs:gWfpPerProContext, 0
0x1400750ee  jz      short loc_140075123
0x1400750f0  xor     ecx, ecx; ProcNumber
0x1400750f2  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400750f9  nop     dword ptr [rax+rax+00h]
0x1400750fe  lea     ecx, [rax+rax*8]
0x140075101  mov     rax, cs:gWfpPerProContext
0x140075108  shl     ecx, 3
0x14007510b  mov     rcx, [rcx+rax]
0x14007510f  mov     rax, ds:0FFFFF78000000008h
0x140075119  mov     [rcx+8], rax
0x14007511d  mov     dword ptr [rcx], 4
0x140075123  mov     rcx, cs:pRemoteEndpointTable
0x14007512a  cmp     ebp, [rcx+8]
0x14007512d  jnz     short loc_140075140
0x14007512f  mov     eax, ebx
0x140075131  add     rsp, 28h
0x140075135  pop     r15
0x140075137  pop     r14
0x140075139  pop     rdi
0x14007513a  pop     rsi
0x14007513b  pop     rbp
0x14007513c  pop     rbx
0x14007513d  retn
0x140075140  shl     rbx, 7
0x140075144  add     rbx, rcx
0x140075147  cmp     cs:gWfpPerProContext, 0
0x14007514f  jz      short loc_14007517B
0x140075151  xor     ecx, ecx; ProcNumber
0x140075153  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14007515a  nop     dword ptr [rax+rax+00h]
0x14007515f  lea     edx, [rax+rax*8]
0x140075162  mov     rax, cs:gWfpPerProContext
0x140075169  shl     edx, 3
0x14007516c  mov     rdx, [rdx+rax]
0x140075170  cmp     dword ptr [rdx], 4
0x140075173  jnz     short loc_14007517B
0x140075175  mov     dword ptr [rdx], 0
0x14007517b  mov     rcx, [rbx+40h]; Lock
0x14007517f  mov     rdx, r14; LockState
0x140075182  call    cs:__imp_NdisReleaseRWLock
0x140075189  nop     dword ptr [rax+rax+00h]
0x14007518e  mov     rcx, cs:pRemoteEndpointTable
0x140075195  mov     ebx, r15d
0x140075198  mov     ebp, [rcx+8]
0x14007519b  and     ebx, ebp
0x14007519d  mov     edi, ebx
0x14007519f  shl     rdi, 7
0x1400751a3  add     rdi, rcx
0x1400751a6  call    cs:__imp_KeGetCurrentIrql
0x1400751ad  nop     dword ptr [rax+rax+00h]
0x1400751b2  mov     rcx, [rdi+40h]; Lock
0x1400751b6  xor     r8d, r8d; Flags
0x1400751b9  mov     rdx, r14; LockState
0x1400751bc  movzx   esi, al
0x1400751bf  call    cs:__imp_NdisAcquireRWLockWrite
0x1400751c6  nop     dword ptr [rax+rax+00h]
0x1400751cb  cmp     sil, 2
0x1400751cf  jz      short loc_14007520F
0x1400751d1  cmp     cs:gWfpPerProContext, 0
0x1400751d9  jz      short loc_14007520F
0x1400751db  xor     ecx, ecx; ProcNumber
0x1400751dd  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400751e4  nop     dword ptr [rax+rax+00h]
0x1400751e9  mov     rcx, cs:gWfpPerProContext
0x1400751f0  lea     edx, [rax+rax*8]
0x1400751f3  mov     rax, ds:0FFFFF78000000008h
0x1400751fd  shl     edx, 3
0x140075200  mov     r8, [rdx+rcx]
0x140075204  mov     [r8+8], rax
0x140075208  mov     dword ptr [r8], 4
0x14007520f  mov     rcx, cs:pRemoteEndpointTable
0x140075216  cmp     ebp, [rcx+8]
0x140075219  jz      loc_14007512F
0x14007521f  jmp     loc_140075140
```
