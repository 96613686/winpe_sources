# SmbCeDecrementActiveVNetRootsOnVNetRootContext

- ea: `0x1400189c0`
- end: `0x140018ab3`
- name: `SmbCeDecrementActiveVNetRootsOnVNetRootContext`
- size: `243`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140017e60`
- `0x140028450`
- `0x14002f7a8`
- `0x1400302f0`

## callees

- `0x140004990`
- `0x1400189c0`
- `0x140018abc`
- `0x140059ea0`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140018a23`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140018a23`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400189de`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400189de`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400189ed`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400189ed`
- `rdbss!RxDiagnosticTrace` at `0x140018a47`
- `rdbss!RxDiagnosticTrace` at `0x140018a47`

## pseudocode

```c
__int64 __fastcall SmbCeDecrementActiveVNetRootsOnVNetRootContext(__int64 a1, const void *a2)
{
  __int64 v2; // rsi
  KIRQL v5; // di
  signed __int32 v6; // ebp
  __int64 v7; // rcx
  __int64 v8; // rdi

  v2 = *(_QWORD *)(a1 + 24);
  v5 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v2 + 1920));
  *(_DWORD *)(v2 + 2352) = (unsigned int)PsGetCurrentThreadId();
  v6 = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 432), 0xFFFFFFFF);
  *(_DWORD *)(v2 + 2352) = -1;
  --v6;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v2 + 1920), v5);
  RxDiagnosticTrace(*(_QWORD *)(a1 + 16), 2, "Active VnetRoots-- %x VNetRoot %p", v6, a2);
  if ( !v6 )
  {
    v7 = *(_QWORD *)(a1 + 416);
    *(_QWORD *)(a1 + 480) = 0;
    v8 = *(_QWORD *)(v7 + 384);
    SmbCeDecrementActiveVNetRootContextsOnSession(v7);
    if ( (*(unsigned int (__fastcall **)(__int64, void (__fastcall *)(unsigned __int16 *), __int64))(*(_QWORD *)(v8 + 56) + 832LL))(
           a1,
           SmbCeCompleteVNetRootContextInvalidation,
           a1) != 259 )
      SmbCeCompleteVNetRootContextInvalidation((unsigned __int16 *)a1);
  }
  return 0;
}

```

## disassembly

```asm
0x1400189c0  push    rbx
0x1400189c2  push    rbp
0x1400189c3  push    rsi
0x1400189c4  push    rdi
0x1400189c5  push    r14
0x1400189c7  push    r15
0x1400189c9  sub     rsp, 38h
0x1400189cd  mov     rsi, [rcx+18h]
0x1400189d1  mov     rbx, rcx
0x1400189d4  mov     r15, rdx
0x1400189d7  lea     rcx, [rsi+780h]; SpinLock
0x1400189de  call    cs:__imp_ExAcquireSpinLockExclusive
0x1400189e5  nop     dword ptr [rax+rax+00h]
0x1400189ea  movzx   edi, al
0x1400189ed  call    cs:__imp_PsGetCurrentThreadId
0x1400189f4  nop     dword ptr [rax+rax+00h]
0x1400189f9  mov     [rsi+930h], eax
0x1400189ff  mov     ebp, 0FFFFFFFFh
0x140018a04  lock xadd [rbx+1B0h], ebp
0x140018a0c  movzx   edx, dil; OldIrql
0x140018a10  mov     dword ptr [rsi+930h], 0FFFFFFFFh
0x140018a1a  lea     rcx, [rsi+780h]; SpinLock
0x140018a21  dec     ebp
0x140018a23  call    cs:__imp_ExReleaseSpinLockExclusive
0x140018a2a  nop     dword ptr [rax+rax+00h]
0x140018a2f  mov     rcx, [rbx+10h]
0x140018a33  lea     r8, aActiveVnetroot_0; "Active VnetRoots-- %x VNetRoot %p"
0x140018a3a  mov     r9d, ebp
0x140018a3d  mov     [rsp+68h+var_48], r15
0x140018a42  mov     edx, 2
0x140018a47  call    cs:__imp_RxDiagnosticTrace
0x140018a4e  nop     dword ptr [rax+rax+00h]
0x140018a53  test    ebp, ebp
0x140018a55  jnz     short loc_140018A99
0x140018a57  mov     rcx, [rbx+1A0h]
0x140018a5e  mov     qword ptr [rbx+1E0h], 0
0x140018a69  mov     rdi, [rcx+180h]
0x140018a70  call    SmbCeDecrementActiveVNetRootContextsOnSession
0x140018a75  mov     rax, [rdi+38h]
0x140018a79  lea     rdx, SmbCeCompleteVNetRootContextInvalidation
0x140018a80  mov     r8, rbx
0x140018a83  mov     rcx, rbx
0x140018a86  mov     rax, [rax+340h]
0x140018a8d  call    _guard_dispatch_icall
0x140018a92  cmp     eax, 103h
0x140018a97  jnz     short loc_140018AA9
0x140018a99  xor     eax, eax
0x140018a9b  add     rsp, 38h
0x140018a9f  pop     r15
0x140018aa1  pop     r14
0x140018aa3  pop     rdi
0x140018aa4  pop     rsi
0x140018aa5  pop     rbp
0x140018aa6  pop     rbx
0x140018aa7  retn
0x140018aa9  mov     rcx, rbx
0x140018aac  call    SmbCeCompleteVNetRootContextInvalidation
0x140018ab1  jmp     short loc_140018A99
```
