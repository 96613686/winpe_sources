# SmbCepDereferenceServerTransport

- ea: `0x140008b70`
- end: `0x140008cf0`
- name: `SmbCepDereferenceServerTransport`
- size: `384`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140008840`
- `0x14000c1f0`
- `0x140013700`
- `0x140014c88`
- `0x140014d04`
- `0x14004245c`
- `0x14004dd50`
- `0x14004ee60`
- `0x14004f820`

## callees

- `0x140008b70`
- `0x140014db4`
- `0x140041570`

## import_xrefs

- `ntoskrnl!IoGetCurrentProcess` at `0x140008ca8`
- `ntoskrnl!IoGetCurrentProcess` at `0x140008ca8`
- `ntoskrnl!RtlGetCallersAddress` at `0x140008bca`
- `ntoskrnl!RtlGetCallersAddress` at `0x140008bca`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008c09`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008c31`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008c8d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008c09`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008c31`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008c8d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008b90`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008b90`
- `rdbss!RxGetRDBSSProcess` at `0x140008c99`
- `rdbss!RxGetRDBSSProcess` at `0x140008c99`
- `rdbss!RxDispatchToWorkerThread` at `0x140008cdf`
- `rdbss!RxDispatchToWorkerThread` at `0x140008cdf`
- `mrxsmb!MRxSmbDeviceObject` at `0x140008cc6`

## pseudocode

```c
NTSTATUS __fastcall SmbCepDereferenceServerTransport(_QWORD *a1)
{
  KIRQL v2; // al
  __int64 v3; // rdi
  signed __int32 v4; // esi
  KIRQL v5; // dl
  struct _KPROCESS *RDBSSProcess; // rbx
  PVOID CallersAddress; // [rsp+60h] [rbp+8h] BYREF
  PVOID CallersCaller; // [rsp+68h] [rbp+10h] BYREF

  CallersAddress = 0;
  CallersCaller = 0;
  v2 = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
  v3 = *a1;
  s_SmbCeDbSpinLockSavedIrql = v2;
  if ( v3 )
  {
    v4 = _InterlockedDecrement((volatile signed __int32 *)(v3 + 8));
    RtlGetCallersAddress(&CallersAddress, &CallersCaller);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      WPP_SF_qDDqq(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        (unsigned int)(v4 + 1),
        *a1,
        v4 + 1,
        v4,
        CallersCaller,
        CallersAddress);
    v5 = s_SmbCeDbSpinLockSavedIrql;
    if ( v4 )
    {
      KeReleaseSpinLock(&s_SmbCeDbSpinLock, s_SmbCeDbSpinLockSavedIrql);
      return 0;
    }
    *(_DWORD *)(v3 + 12) = 1;
    *a1 = 0;
    KeReleaseSpinLock(&s_SmbCeDbSpinLock, v5);
    RDBSSProcess = RxGetRDBSSProcess();
    if ( IoGetCurrentProcess() == RDBSSProcess )
    {
      VctTearDownServerTransport((PVOID)v3);
      return 0;
    }
    return RxDispatchToWorkerThread(MRxSmbDeviceObject, NormalWorkQueue, VctTearDownServerTransport, (PVOID)v3);
  }
  else
  {
    KeReleaseSpinLock(&s_SmbCeDbSpinLock, v2);
    return -1073741300;
  }
}

```

## disassembly

```asm
0x140008b70  push    rbx
0x140008b72  push    rdi
0x140008b73  push    r14
0x140008b75  sub     rsp, 40h
0x140008b79  mov     rbx, rcx
0x140008b7c  xor     r14d, r14d
0x140008b7f  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140008b86  mov     [rsp+58h+CallersAddress], r14
0x140008b8b  mov     [rsp+58h+CallersCaller], r14
0x140008b90  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140008b97  nop     dword ptr [rax+rax+00h]
0x140008b9c  mov     rdi, [rbx]
0x140008b9f  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x140008ba5  test    rdi, rdi
0x140008ba8  jz      short loc_140008C27
0x140008baa  mov     [rsp+58h+arg_10], rbp
0x140008baf  mov     [rsp+58h+arg_18], rsi
0x140008bb4  mov     esi, 0FFFFFFFFh
0x140008bb9  lock xadd [rdi+8], esi
0x140008bbe  dec     esi
0x140008bc0  lea     rdx, [rsp+58h+CallersCaller]; CallersCaller
0x140008bc5  lea     rcx, [rsp+58h+CallersAddress]; CallersAddress
0x140008bca  call    cs:__imp_RtlGetCallersAddress
0x140008bd1  nop     dword ptr [rax+rax+00h]
0x140008bd6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140008bdd  lea     rax, WPP_GLOBAL_Control
0x140008be4  cmp     rcx, rax
0x140008be7  jz      short loc_140008BF2
0x140008be9  test    dword ptr [rcx+2Ch], 200h
0x140008bf0  jnz     short loc_140008C4C
0x140008bf2  movzx   edx, cs:s_SmbCeDbSpinLockSavedIrql; NewIrql
0x140008bf9  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140008c00  test    esi, esi
0x140008c02  mov     rsi, [rsp+58h+arg_18]
0x140008c07  jz      short loc_140008C83
0x140008c09  call    cs:__imp_KeReleaseSpinLock
0x140008c10  nop     dword ptr [rax+rax+00h]
0x140008c15  mov     eax, r14d
0x140008c18  mov     rbp, [rsp+58h+arg_10]
0x140008c1d  add     rsp, 40h
0x140008c21  pop     r14
0x140008c23  pop     rdi
0x140008c24  pop     rbx
0x140008c25  retn
0x140008c27  movzx   edx, al; NewIrql
0x140008c2a  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140008c31  call    cs:__imp_KeReleaseSpinLock
0x140008c38  nop     dword ptr [rax+rax+00h]
0x140008c3d  mov     eax, 0C000020Ch
0x140008c42  add     rsp, 40h
0x140008c46  pop     r14
0x140008c48  pop     rdi
0x140008c49  pop     rbx
0x140008c4a  retn
0x140008c4c  mov     rax, [rsp+58h+CallersAddress]
0x140008c51  lea     r8d, [rsi+1]
0x140008c55  mov     r9, [rbx]
0x140008c58  mov     edx, 0Ch
0x140008c5d  mov     rcx, [rcx+18h]
0x140008c61  mov     [rsp+58h+var_20], rax
0x140008c66  mov     rax, [rsp+58h+CallersCaller]
0x140008c6b  mov     [rsp+58h+var_28], rax
0x140008c70  mov     [rsp+58h+var_30], esi
0x140008c74  mov     [rsp+58h+var_38], r8d
0x140008c79  call    WPP_SF_qDDqq
0x140008c7e  jmp     loc_140008BF2
0x140008c83  mov     dword ptr [rdi+0Ch], 1
0x140008c8a  mov     [rbx], r14
0x140008c8d  call    cs:__imp_KeReleaseSpinLock
0x140008c94  nop     dword ptr [rax+rax+00h]
0x140008c99  call    cs:__imp_RxGetRDBSSProcess
0x140008ca0  nop     dword ptr [rax+rax+00h]
0x140008ca5  mov     rbx, rax
0x140008ca8  call    cs:__imp_IoGetCurrentProcess
0x140008caf  nop     dword ptr [rax+rax+00h]
0x140008cb4  cmp     rax, rbx
0x140008cb7  jnz     short loc_140008CC6
0x140008cb9  mov     rcx, rdi; Context
0x140008cbc  call    VctTearDownServerTransport
0x140008cc1  jmp     loc_140008C15
0x140008cc6  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x140008ccd  lea     r8, VctTearDownServerTransport; Routine
0x140008cd4  mov     r9, rdi; pContext
0x140008cd7  mov     edx, 3; WorkQueueType
0x140008cdc  mov     rcx, [rcx]; pMRxDeviceObject
0x140008cdf  call    cs:__imp_RxDispatchToWorkerThread
0x140008ce6  nop     dword ptr [rax+rax+00h]
0x140008ceb  jmp     loc_140008C18
```
