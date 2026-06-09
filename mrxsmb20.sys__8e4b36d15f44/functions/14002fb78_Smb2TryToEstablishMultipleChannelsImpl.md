# Smb2TryToEstablishMultipleChannelsImpl

- ea: `0x14002fb78`
- end: `0x14002fc21`
- name: `Smb2TryToEstablishMultipleChannelsImpl`
- size: `169`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `5`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14001cc00`
- `0x1400509d8`
- `0x1400513a0`
- `0x140055130`
- `0x140055bd0`

## callees

- `0x1400122d0`
- `0x14002fb78`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002fc04`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002fc04`
- `rdbss!RxDispatchToWorkerThread` at `0x14002fbcf`
- `rdbss!RxDispatchToWorkerThread` at `0x14002fbcf`
- `mrxsmb!SmbCeDereferenceSessionEntryEx` at `0x14002fbe4`
- `mrxsmb!SmbCeDereferenceSessionEntryEx` at `0x14002fbe4`
- `mrxsmb!SmbCeEstablishMultipleChannels` at `0x14002fbbd`
- `mrxsmb!SmbCeReferenceSessionEntry` at `0x14002fbb1`
- `mrxsmb!SmbCeReferenceSessionEntry` at `0x14002fbb1`

## pseudocode

```c
void __fastcall Smb2TryToEstablishMultipleChannelsImpl(_QWORD *pContext)
{
  __int64 v2; // rdi
  KIRQL v3; // al
  int v4; // ecx
  KIRQL v5; // si

  v2 = *(_QWORD *)(pContext[48] + 24LL);
  v3 = SmbCeAcquireSpinLock(v2);
  v4 = *((_DWORD *)pContext + 1);
  v5 = v3;
  if ( (v4 & 8) == 0 )
  {
    *((_DWORD *)pContext + 1) = v4 | 8;
    SmbCeReferenceSessionEntry(pContext);
    if ( RxDispatchToWorkerThread((PRDBSS_DEVICE_OBJECT)v2, NormalWorkQueue, SmbCeEstablishMultipleChannels, pContext) )
      SmbCeDereferenceSessionEntryEx(pContext, 0);
  }
  *(_DWORD *)(v2 + 2352) = -1;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v2 + 1920), v5);
}

```

## disassembly

```asm
0x14002fb78  mov     [rsp+arg_0], rbx
0x14002fb7d  mov     [rsp+arg_8], rsi
0x14002fb82  push    rdi
0x14002fb83  sub     rsp, 20h
0x14002fb87  mov     rax, [rcx+180h]
0x14002fb8e  mov     rbx, rcx
0x14002fb91  mov     rdi, [rax+18h]
0x14002fb95  mov     rcx, rdi
0x14002fb98  call    SmbCeAcquireSpinLock
0x14002fb9d  mov     ecx, [rbx+4]
0x14002fba0  mov     sil, al
0x14002fba3  test    cl, 8
0x14002fba6  jnz     short loc_14002FBF0
0x14002fba8  or      ecx, 8
0x14002fbab  mov     [rbx+4], ecx
0x14002fbae  mov     rcx, rbx
0x14002fbb1  call    cs:__imp_SmbCeReferenceSessionEntry
0x14002fbb8  nop     dword ptr [rax+rax+00h]
0x14002fbbd  mov     r8, cs:__imp_SmbCeEstablishMultipleChannels; Routine
0x14002fbc4  mov     r9, rbx; pContext
0x14002fbc7  mov     edx, 3; WorkQueueType
0x14002fbcc  mov     rcx, rdi; pMRxDeviceObject
0x14002fbcf  call    cs:__imp_RxDispatchToWorkerThread
0x14002fbd6  nop     dword ptr [rax+rax+00h]
0x14002fbdb  test    eax, eax
0x14002fbdd  jz      short loc_14002FBF0
0x14002fbdf  xor     edx, edx
0x14002fbe1  mov     rcx, rbx
0x14002fbe4  call    cs:__imp_SmbCeDereferenceSessionEntryEx
0x14002fbeb  nop     dword ptr [rax+rax+00h]
0x14002fbf0  lea     rcx, [rdi+780h]; SpinLock
0x14002fbf7  mov     dword ptr [rdi+930h], 0FFFFFFFFh
0x14002fc01  mov     dl, sil; OldIrql
0x14002fc04  call    cs:__imp_ExReleaseSpinLockExclusive
0x14002fc0b  nop     dword ptr [rax+rax+00h]
0x14002fc10  mov     rbx, [rsp+28h+arg_0]
0x14002fc15  mov     rsi, [rsp+28h+arg_8]
0x14002fc1a  add     rsp, 20h
0x14002fc1e  pop     rdi
0x14002fc1f  retn
```
