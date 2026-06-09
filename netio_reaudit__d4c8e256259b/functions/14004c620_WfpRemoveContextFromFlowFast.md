# WfpRemoveContextFromFlowFast

- ea: `0x14004c620`
- end: `0x14004c800`
- name: `WfpRemoveContextFromFlowFast`
- size: `480`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x140007ad0`
- `0x14001a680`
- `0x14004c620`
- `0x14004efd4`
- `0x140078080`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004c6f6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004c772`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004c6f6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004c772`
- `ntoskrnl!KeGenericCallDpc` at `0x14004c7d0`
- `ntoskrnl!KeGenericCallDpc` at `0x14004c7d0`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004c6b7`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004c6b7`
- `NDIS!NdisReleaseRWLock` at `0x14004c7a9`
- `NDIS!NdisReleaseRWLock` at `0x14004c7a9`
- `NDIS!NdisAcquireRWLockWrite` at `0x14004c6d5`
- `NDIS!NdisAcquireRWLockWrite` at `0x14004c6d5`

## string_xrefs

- `0x14004c669`: `WfpRemoveContextFromFlowFast`

## pseudocode

```c
__int64 __fastcall WfpRemoveContextFromFlowFast(__int64 a1, unsigned int a2)
{
  __int64 v2; // r15
  __int64 v3; // rsi
  __int64 v5; // rbp
  PNPAGED_LOOKASIDE_LIST v6; // rdi
  void (__fastcall *v7)(_QWORD, __int64); // r14
  KIRQL CurrentIrql; // bl
  __int64 v9; // rdx
  PNPAGED_LOOKASIDE_LIST v10; // rbx
  _DWORD *v11; // rdx
  struct _LOCK_STATE_EX LockState; // [rsp+58h] [rbp+10h] BYREF

  v2 = a2;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v3 = KfdAleAcquireEndpointContextFromFlow();
  if ( v3 )
  {
    v5 = 0;
    v6 = gWfpGlobal;
    v7 = 0;
    CurrentIrql = KeGetCurrentIrql();
    NdisAcquireRWLockWrite((PNDIS_RW_LOCK_EX)v6[3].L.AllocateEx, &LockState, 0);
    if ( CurrentIrql != 2 && gWfpPerProContext )
    {
      v9 = *(_QWORD *)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
      *(_QWORD *)(v9 + 8) = MEMORY[0xFFFFF78000000008];
      *(_DWORD *)v9 = 4;
    }
    if ( *(_QWORD *)(v3 + 120) )
    {
      v5 = *(_QWORD *)(v3 + 120);
      v7 = (void (__fastcall *)(_QWORD, __int64))*((_QWORD *)&gWfpGlobal[13].L.LastTotalAllocates + 2 * v2);
      _InterlockedDecrement((volatile signed __int32 *)&gWfpGlobal[13].L.Future[4 * v2]);
      *(_QWORD *)(v3 + 120) = 0;
    }
    v10 = gWfpGlobal;
    if ( gWfpPerProContext )
    {
      v11 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
      if ( *v11 == 4 )
        *v11 = 0;
    }
    NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v10[3].L.AllocateEx, &LockState);
    if ( v5 )
      v7(0, v5);
    KeGenericCallDpc(WfpSyncDpcCallback, 0);
    WfpAleDereferenceEndpoint(v3);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
    {
      WPP_SF_sd(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
        (unsigned int)"WfpRemoveContextFromFlowFast",
        37);
    }
    return 3221226021LL;
  }
}

```

## disassembly

```asm
0x14004c620  push    rsi
0x14004c622  push    r15
0x14004c624  sub     rsp, 38h
0x14004c628  xor     eax, eax
0x14004c62a  mov     r15d, edx
0x14004c62d  mov     word ptr [rsp+48h+LockState.OldIrql], ax
0x14004c632  mov     [rsp+48h+LockState.Flags], al
0x14004c636  call    KfdAleAcquireEndpointContextFromFlow
0x14004c63b  mov     rsi, rax
0x14004c63e  test    rax, rax
0x14004c641  jnz     short loc_14004C697
0x14004c643  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c64a  lea     rax, WPP_GLOBAL_Control
0x14004c651  cmp     rcx, rax
0x14004c654  jz      short loc_14004C689
0x14004c656  cmp     byte ptr [rcx+29h], 2
0x14004c65a  jb      short loc_14004C689
0x14004c65c  test    dword ptr [rcx+2Ch], 1000h
0x14004c663  jz      short loc_14004C689
0x14004c665  mov     rcx, [rcx+18h]
0x14004c669  lea     r9, aWfpremoveconte; "WfpRemoveContextFromFlowFast"
0x14004c670  mov     edx, 0Ah
0x14004c675  mov     [rsp+48h+var_28], 0C0000225h
0x14004c67d  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14004c684  call    WPP_SF_sd
0x14004c689  mov     eax, 0C0000225h
0x14004c68e  add     rsp, 38h
0x14004c692  pop     r15
0x14004c694  pop     rsi
0x14004c695  retn
0x14004c697  mov     [rsp+48h+arg_0], rbx
0x14004c69c  mov     [rsp+48h+arg_10], rbp
0x14004c6a1  xor     ebp, ebp
0x14004c6a3  mov     [rsp+48h+arg_18], rdi
0x14004c6a8  mov     rdi, cs:gWfpGlobal
0x14004c6af  mov     [rsp+48h+var_18], r14
0x14004c6b4  xor     r14d, r14d
0x14004c6b7  call    cs:__imp_KeGetCurrentIrql
0x14004c6be  nop     dword ptr [rax+rax+00h]
0x14004c6c3  mov     rcx, [rdi+1B0h]; Lock
0x14004c6ca  lea     rdx, [rsp+48h+LockState]; LockState
0x14004c6cf  xor     r8d, r8d; Flags
0x14004c6d2  movzx   ebx, al
0x14004c6d5  call    cs:__imp_NdisAcquireRWLockWrite
0x14004c6dc  nop     dword ptr [rax+rax+00h]
0x14004c6e1  mov     rdi, [rsp+48h+arg_18]
0x14004c6e6  cmp     bl, 2
0x14004c6e9  jz      short loc_14004C72A
0x14004c6eb  cmp     cs:gWfpPerProContext, rbp
0x14004c6f2  jz      short loc_14004C72A
0x14004c6f4  xor     ecx, ecx; ProcNumber
0x14004c6f6  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14004c6fd  nop     dword ptr [rax+rax+00h]
0x14004c702  imul    eax, cs:gWfpPerProContextSize
0x14004c709  mov     ecx, eax
0x14004c70b  mov     rax, cs:gWfpPerProContext
0x14004c712  mov     rdx, [rcx+rax]
0x14004c716  mov     rax, ds:0FFFFF78000000008h
0x14004c720  mov     [rdx+8], rax
0x14004c724  mov     dword ptr [rdx], 4
0x14004c72a  mov     rax, [rsi+78h]
0x14004c72e  test    rax, rax
0x14004c731  jz      short loc_14004C75F
0x14004c733  mov     rcx, cs:gWfpGlobal
0x14004c73a  mov     rbp, rax
0x14004c73d  lea     rax, [r15+6Dh]
0x14004c741  mov     rdx, r15
0x14004c744  add     rax, rax
0x14004c747  shl     rdx, 4
0x14004c74b  mov     r14, [rcx+rax*8]
0x14004c74f  lock dec dword ptr [rdx+rcx+6D8h]
0x14004c757  mov     qword ptr [rsi+78h], 0
0x14004c75f  cmp     cs:gWfpPerProContext, 0
0x14004c767  mov     rbx, cs:gWfpGlobal
0x14004c76e  jz      short loc_14004C79D
0x14004c770  xor     ecx, ecx; ProcNumber
0x14004c772  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14004c779  nop     dword ptr [rax+rax+00h]
0x14004c77e  imul    eax, cs:gWfpPerProContextSize
0x14004c785  mov     ecx, eax
0x14004c787  mov     rax, cs:gWfpPerProContext
0x14004c78e  mov     rdx, [rcx+rax]
0x14004c792  cmp     dword ptr [rdx], 4
0x14004c795  jnz     short loc_14004C79D
0x14004c797  mov     dword ptr [rdx], 0
0x14004c79d  mov     rcx, [rbx+1B0h]; Lock
0x14004c7a4  lea     rdx, [rsp+48h+LockState]; LockState
0x14004c7a9  call    cs:__imp_NdisReleaseRWLock
0x14004c7b0  nop     dword ptr [rax+rax+00h]
0x14004c7b5  test    rbp, rbp
0x14004c7b8  jz      short loc_14004C7C7
0x14004c7ba  mov     rdx, rbp
0x14004c7bd  xor     ecx, ecx
0x14004c7bf  mov     rax, r14
0x14004c7c2  call    _guard_dispatch_icall
0x14004c7c7  xor     edx, edx
0x14004c7c9  lea     rcx, WfpSyncDpcCallback
0x14004c7d0  call    cs:__imp_KeGenericCallDpc
0x14004c7d7  nop     dword ptr [rax+rax+00h]
0x14004c7dc  xor     ebx, ebx
0x14004c7de  mov     rcx, rsi
0x14004c7e1  call    WfpAleDereferenceEndpoint
0x14004c7e6  mov     r14, [rsp+48h+var_18]
0x14004c7eb  mov     eax, ebx
0x14004c7ed  mov     rbx, [rsp+48h+arg_0]
0x14004c7f2  mov     rbp, [rsp+48h+arg_10]
0x14004c7f7  add     rsp, 38h
0x14004c7fb  pop     r15
0x14004c7fd  pop     rsi
0x14004c7fe  retn
```
