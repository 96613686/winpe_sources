# SmbCeDecrementTotalVNetRootContextsOnSession

- ea: `0x140005b20`
- end: `0x140005bc0`
- name: `SmbCeDecrementTotalVNetRootContextsOnSession`
- size: `160`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140004990`
- `0x14002e770`
- `0x1400302f0`

## callees

- `0x140005b20`
- `0x140046698`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140005b7b`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140005b7b`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140005b39`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140005b39`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140005b48`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140005b48`
- `rdbss!RxDiagnosticTrace` at `0x140005b9a`
- `rdbss!RxDiagnosticTrace` at `0x140005b9a`

## pseudocode

```c
__int64 __fastcall SmbCeDecrementTotalVNetRootContextsOnSession(__int64 a1)
{
  __int64 v1; // rbp
  KIRQL v3; // di
  int v4; // esi
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 24);
  v3 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v1 + 1920));
  *(_DWORD *)(v1 + 2352) = (unsigned int)PsGetCurrentThreadId();
  v4 = --*(_DWORD *)(a1 + 428);
  *(_DWORD *)(v1 + 2352) = -1;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v1 + 1920), v3);
  result = RxDiagnosticTrace(*(_QWORD *)(a1 + 16), 2, "Total VnrCtxts-- %x", v4);
  if ( !v4 )
    return SmbCeInvalidateSessionEntry(a1);
  return result;
}

```

## disassembly

```asm
0x140005b20  push    rbx
0x140005b22  push    rbp
0x140005b23  push    rsi
0x140005b24  push    rdi
0x140005b25  push    r14
0x140005b27  sub     rsp, 20h
0x140005b2b  mov     rbp, [rcx+18h]
0x140005b2f  mov     rbx, rcx
0x140005b32  lea     rcx, [rbp+780h]; SpinLock
0x140005b39  call    cs:__imp_ExAcquireSpinLockExclusive
0x140005b40  nop     dword ptr [rax+rax+00h]
0x140005b45  movzx   edi, al
0x140005b48  call    cs:__imp_PsGetCurrentThreadId
0x140005b4f  nop     dword ptr [rax+rax+00h]
0x140005b54  mov     [rbp+930h], eax
0x140005b5a  movzx   edx, dil; OldIrql
0x140005b5e  dec     dword ptr [rbx+1ACh]
0x140005b64  lea     rcx, [rbp+780h]; SpinLock
0x140005b6b  mov     esi, [rbx+1ACh]
0x140005b71  mov     dword ptr [rbp+930h], 0FFFFFFFFh
0x140005b7b  call    cs:__imp_ExReleaseSpinLockExclusive
0x140005b82  nop     dword ptr [rax+rax+00h]
0x140005b87  mov     rcx, [rbx+10h]
0x140005b8b  lea     r8, aTotalVnrctxtsX; "Total VnrCtxts-- %x"
0x140005b92  mov     r9d, esi
0x140005b95  mov     edx, 2
0x140005b9a  call    cs:__imp_RxDiagnosticTrace
0x140005ba1  nop     dword ptr [rax+rax+00h]
0x140005ba6  test    esi, esi
0x140005ba8  jz      short loc_140005BB6
0x140005baa  add     rsp, 20h
0x140005bae  pop     r14
0x140005bb0  pop     rdi
0x140005bb1  pop     rsi
0x140005bb2  pop     rbp
0x140005bb3  pop     rbx
0x140005bb4  retn
0x140005bb6  mov     rcx, rbx
0x140005bb9  call    SmbCeInvalidateSessionEntry
0x140005bbe  jmp     short loc_140005BAA
```
