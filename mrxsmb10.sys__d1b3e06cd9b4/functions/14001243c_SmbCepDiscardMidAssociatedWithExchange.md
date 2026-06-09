# SmbCepDiscardMidAssociatedWithExchange

- ea: `0x14001243c`
- end: `0x140012540`
- name: `SmbCepDiscardMidAssociatedWithExchange`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140012940`

## callees

- `0x140001e40`
- `0x140002470`
- `0x14000b960`
- `0x14000be44`
- `0x14001243c`

## import_xrefs

- `rdbss!RxDispatchToWorkerThread` at `0x140012511`
- `rdbss!RxDispatchToWorkerThread` at `0x140012511`
- `mrxsmb!MRxSmbDeviceObject` at `0x1400124fa`

## pseudocode

```c
__int64 __fastcall SmbCepDiscardMidAssociatedWithExchange(__int64 a1)
{
  unsigned int v1; // r8d
  __int64 v3; // rbx
  unsigned __int16 Mid; // ax
  __int64 v5; // r9

  v1 = 0;
  if ( (*(_DWORD *)(a1 + 72) & 1) != 0 && *(_WORD *)(a1 + 64) <= 0xFFFDu )
  {
    v3 = *(_QWORD *)(a1 + 80);
    if ( v3 && *(_QWORD *)(v3 + 384) )
    {
      Mid = SmbCeExtractMid(*(_QWORD *)(a1 + 80));
      v1 = FsRtlReassociateMid(v5, Mid, 0);
      if ( !v1 && ++*(_WORD *)(*(_QWORD *)(v3 + 384) + 6LL) == **(_WORD **)(v3 + 384) )
      {
        MRxSmbTrackRefCount(v3, "SmbCepDiscardMidAssociatedWithExchange", 493);
        SmbReferenceRecord(v3 + 792, "SmbCepDiscardMidAssociatedWithExchange", 493);
        _InterlockedAdd((volatile signed __int32 *)(v3 + 8), 1u);
        v1 = RxDispatchToWorkerThread(MRxSmbDeviceObject, NormalWorkQueue, SmbCeDiscardMidAssignmentRequests, (PVOID)v3);
      }
      *(_DWORD *)(a1 + 72) &= ~1u;
    }
    else
    {
      return (unsigned int)-1073741811;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x14001243c  mov     [rsp+arg_0], rbx
0x140012441  mov     [rsp+arg_8], rbp
0x140012446  push    rdi
0x140012447  sub     rsp, 20h
0x14001244b  mov     eax, [rcx+48h]
0x14001244e  xor     r8d, r8d
0x140012451  mov     rdi, rcx
0x140012454  lea     ebp, [r8+1]
0x140012458  test    bpl, al
0x14001245b  jz      loc_14001252C
0x140012461  movzx   edx, word ptr [rcx+40h]
0x140012465  mov     eax, 0FFFDh
0x14001246a  cmp     dx, ax
0x14001246d  ja      loc_14001252C
0x140012473  mov     rbx, [rcx+50h]
0x140012477  test    rbx, rbx
0x14001247a  jz      loc_140012526
0x140012480  mov     r9, [rbx+180h]
0x140012487  test    r9, r9
0x14001248a  jz      loc_140012526
0x140012490  mov     rcx, rbx
0x140012493  call    SmbCeExtractMid
0x140012498  xor     r8d, r8d
0x14001249b  movzx   edx, ax
0x14001249e  mov     rcx, r9
0x1400124a1  call    FsRtlReassociateMid
0x1400124a6  mov     r8d, eax
0x1400124a9  test    eax, eax
0x1400124ab  jnz     short loc_140012520
0x1400124ad  mov     rcx, [rbx+180h]
0x1400124b4  add     [rcx+6], bp
0x1400124b8  mov     rdx, [rbx+180h]
0x1400124bf  movzx   ecx, word ptr [rdx]
0x1400124c2  cmp     [rdx+6], cx
0x1400124c6  jnz     short loc_140012520
0x1400124c8  mov     r8d, 1EDh
0x1400124ce  lea     rdx, aSmbcepdiscardm; "SmbCepDiscardMidAssociatedWithExchange"
0x1400124d5  mov     rcx, rbx
0x1400124d8  call    MRxSmbTrackRefCount
0x1400124dd  lea     rcx, [rbx+318h]
0x1400124e4  mov     r8d, 1EDh
0x1400124ea  lea     rdx, aSmbcepdiscardm; "SmbCepDiscardMidAssociatedWithExchange"
0x1400124f1  call    SmbReferenceRecord
0x1400124f6  lock add [rbx+8], ebp
0x1400124fa  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x140012501  lea     r8, SmbCeDiscardMidAssignmentRequests; Routine
0x140012508  mov     r9, rbx; pContext
0x14001250b  lea     edx, [rbp+2]; WorkQueueType
0x14001250e  mov     rcx, [rcx]; pMRxDeviceObject
0x140012511  call    cs:__imp_RxDispatchToWorkerThread
0x140012518  nop     dword ptr [rax+rax+00h]
0x14001251d  mov     r8d, eax
0x140012520  and     dword ptr [rdi+48h], 0FFFFFFFEh
0x140012524  jmp     short loc_14001252C
0x140012526  mov     r8d, 0C000000Dh
0x14001252c  mov     rbx, [rsp+28h+arg_0]
0x140012531  mov     eax, r8d
0x140012534  mov     rbp, [rsp+28h+arg_8]
0x140012539  add     rsp, 20h
0x14001253d  pop     rdi
0x14001253e  retn
```
