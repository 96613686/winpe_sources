# FeGetCalloutFlowDelete

- ea: `0x14000bc60`
- end: `0x14000bdc1`
- name: `FeGetCalloutFlowDelete`
- size: `353`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14000ab30`
- `0x14000b550`
- `0x14000b980`

## callees

- `0x14000bc60`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000bcc8`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000bd46`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000bcc8`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000bd46`
- `ntoskrnl!ObfReferenceObject` at `0x14000bda1`
- `ntoskrnl!ObfReferenceObject` at `0x14000bda1`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000bc8d`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000bc8d`
- `NDIS!NdisAcquireRWLockRead` at `0x14000bcab`
- `NDIS!NdisAcquireRWLockRead` at `0x14000bcab`
- `NDIS!NdisReleaseRWLock` at `0x14000bd77`
- `NDIS!NdisReleaseRWLock` at `0x14000bd77`

## pseudocode

```c
void __fastcall FeGetCalloutFlowDelete(unsigned int a1, _QWORD *a2, _QWORD *a3)
{
  PNPAGED_LOOKASIDE_LIST v3; // rdi
  __int64 v6; // rsi
  KIRQL CurrentIrql; // bl
  __int64 v8; // rdx
  _DWORD *v9; // rbx
  PNPAGED_LOOKASIDE_LIST v10; // rbx
  _DWORD *v11; // rdx
  void *v12; // rcx
  struct _LOCK_STATE_EX LockState; // [rsp+40h] [rbp+8h] BYREF

  v3 = gWfpGlobal;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v6 = a1;
  CurrentIrql = KeGetCurrentIrql();
  NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)v3[1].L.ListHead.Alignment, &LockState, 0);
  if ( CurrentIrql != 2 && gWfpPerProContext )
  {
    v8 = *(_QWORD *)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    *(_QWORD *)(v8 + 8) = MEMORY[0xFFFFF78000000008];
    *(_DWORD *)v8 = 4;
  }
  if ( (unsigned int)v6 >= gWfpGlobal[3].L.FreeMisses
    || (v9 = (_DWORD *)(*(_QWORD *)&gWfpGlobal[3].L.Tag + 144 * v6), !v9[1]) )
  {
    v9 = gFeCallout;
  }
  *a2 = *((_QWORD *)v9 + 5);
  if ( a3 )
  {
    v12 = (void *)*((_QWORD *)v9 + 13);
    if ( v12 )
    {
      ObfReferenceObject(v12);
      *a3 = *((_QWORD *)v9 + 13);
    }
  }
  v10 = gWfpGlobal;
  if ( gWfpPerProContext )
  {
    v11 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    if ( *v11 == 4 )
      *v11 = 0;
  }
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v10[1].L.ListHead.Alignment, &LockState);
}

```

## disassembly

```asm
0x14000bc60  mov     [rsp+arg_8], rbx
0x14000bc65  mov     [rsp+arg_10], rsi
0x14000bc6a  push    rdi
0x14000bc6b  push    r14
0x14000bc6d  push    r15
0x14000bc6f  sub     rsp, 20h
0x14000bc73  mov     rdi, cs:gWfpGlobal
0x14000bc7a  xor     eax, eax
0x14000bc7c  mov     word ptr [rsp+38h+LockState.OldIrql], ax
0x14000bc81  mov     r14, r8
0x14000bc84  mov     [rsp+38h+LockState.Flags], al
0x14000bc88  mov     r15, rdx
0x14000bc8b  mov     esi, ecx
0x14000bc8d  call    cs:__imp_KeGetCurrentIrql
0x14000bc94  nop     dword ptr [rax+rax+00h]
0x14000bc99  mov     rcx, [rdi+80h]; Lock
0x14000bca0  lea     rdx, [rsp+38h+LockState]; LockState
0x14000bca5  xor     r8d, r8d; Flags
0x14000bca8  movzx   ebx, al
0x14000bcab  call    cs:__imp_NdisAcquireRWLockRead
0x14000bcb2  nop     dword ptr [rax+rax+00h]
0x14000bcb7  cmp     bl, 2
0x14000bcba  jz      short loc_14000BCFC
0x14000bcbc  cmp     cs:gWfpPerProContext, 0
0x14000bcc4  jz      short loc_14000BCFC
0x14000bcc6  xor     ecx, ecx; ProcNumber
0x14000bcc8  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000bccf  nop     dword ptr [rax+rax+00h]
0x14000bcd4  imul    eax, cs:gWfpPerProContextSize
0x14000bcdb  mov     ecx, eax
0x14000bcdd  mov     rax, cs:gWfpPerProContext
0x14000bce4  mov     rdx, [rcx+rax]
0x14000bce8  mov     rax, ds:0FFFFF78000000008h
0x14000bcf2  mov     [rdx+8], rax
0x14000bcf6  mov     dword ptr [rdx], 4
0x14000bcfc  mov     rdx, cs:gWfpGlobal
0x14000bd03  cmp     esi, [rdx+1A0h]
0x14000bd09  jnb     short loc_14000BD20
0x14000bd0b  lea     rbx, [rsi+rsi*8]
0x14000bd0f  shl     rbx, 4
0x14000bd13  add     rbx, [rdx+1A8h]
0x14000bd1a  cmp     dword ptr [rbx+4], 0
0x14000bd1e  jnz     short loc_14000BD27
0x14000bd20  mov     rbx, cs:gFeCallout
0x14000bd27  mov     rax, [rbx+28h]
0x14000bd2b  mov     [r15], rax
0x14000bd2e  test    r14, r14
0x14000bd31  jnz     short loc_14000BD98
0x14000bd33  cmp     cs:gWfpPerProContext, 0
0x14000bd3b  mov     rbx, cs:gWfpGlobal
0x14000bd42  jz      short loc_14000BD6B
0x14000bd44  xor     ecx, ecx; ProcNumber
0x14000bd46  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000bd4d  nop     dword ptr [rax+rax+00h]
0x14000bd52  imul    eax, cs:gWfpPerProContextSize
0x14000bd59  mov     ecx, eax
0x14000bd5b  mov     rax, cs:gWfpPerProContext
0x14000bd62  mov     rdx, [rcx+rax]
0x14000bd66  cmp     dword ptr [rdx], 4
0x14000bd69  jz      short loc_14000BDB9
0x14000bd6b  mov     rcx, [rbx+80h]; Lock
0x14000bd72  lea     rdx, [rsp+38h+LockState]; LockState
0x14000bd77  call    cs:__imp_NdisReleaseRWLock
0x14000bd7e  nop     dword ptr [rax+rax+00h]
0x14000bd83  mov     rbx, [rsp+38h+arg_8]
0x14000bd88  mov     rsi, [rsp+38h+arg_10]
0x14000bd8d  add     rsp, 20h
0x14000bd91  pop     r15
0x14000bd93  pop     r14
0x14000bd95  pop     rdi
0x14000bd96  retn
0x14000bd98  mov     rcx, [rbx+68h]; Object
0x14000bd9c  test    rcx, rcx
0x14000bd9f  jz      short loc_14000BD33
0x14000bda1  call    cs:__imp_ObfReferenceObject
0x14000bda8  nop     dword ptr [rax+rax+00h]
0x14000bdad  mov     rax, [rbx+68h]
0x14000bdb1  mov     [r14], rax
0x14000bdb4  jmp     loc_14000BD33
0x14000bdb9  mov     dword ptr [rdx], 0
0x14000bdbf  jmp     short loc_14000BD6B
```
