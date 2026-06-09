# MRxSmbNamedPipeFsControlCompletion

- ea: `0x14000f1d0`
- end: `0x14000f304`
- name: `MRxSmbNamedPipeFsControlCompletion`
- size: `308`
- prototype: `void __fastcall(volatile signed __int32 *P)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14003021c`

## callees

- `0x14000f1d0`
- `0x140052944`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000f22a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f22a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f1e5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f1e5`
- `ntoskrnl!DbgPrint` at `0x14000f2be`
- `ntoskrnl!DbgPrint` at `0x14000f2be`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f2d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f2ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f2d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f2ee`
- `rdbss!RxLowIoCompletion` at `0x14000f26b`
- `rdbss!RxLowIoCompletion` at `0x14000f26b`

## string_xrefs

- `0x14000f29d`: `MRxSmbNamedPipeFsControlCompletion`

## pseudocode

```c
void __fastcall MRxSmbNamedPipeFsControlCompletion(volatile signed __int32 *P)
{
  volatile signed __int32 *WriteOnlyOpenRetryContext; // rsi
  struct _RX_CONTEXT *v3; // rbx
  char v4; // bp
  NTSTATUS v5; // eax
  void *v6; // rcx

  WriteOnlyOpenRetryContext = 0;
  s_SmbCeDbSpinLockSavedIrql = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
  if ( _InterlockedExchangeAdd(P, 0xFFFFFFFF) == 1 )
  {
    v3 = (struct _RX_CONTEXT *)*((_QWORD *)P + 1);
    v4 = 1;
    if ( v3 )
      WriteOnlyOpenRetryContext = (volatile signed __int32 *)v3->WriteOnlyOpenRetryContext;
  }
  else
  {
    v3 = 0;
    v4 = 0;
  }
  KeReleaseSpinLock(&s_SmbCeDbSpinLock, s_SmbCeDbSpinLockSavedIrql);
  if ( v4 )
  {
    if ( v3 )
    {
      v5 = *((_DWORD *)P + 29);
      v3->StoredStatus = v5;
      if ( v5 == -1073741816 )
        v3->StoredStatus = -1073741629;
      v3->InformationToReturn = *((unsigned int *)P + 27);
      RxLowIoCompletion(v3);
    }
    if ( WriteOnlyOpenRetryContext )
    {
      if ( _InterlockedExchangeAdd(WriteOnlyOpenRetryContext + 1, 0xFFFFFFFF) == 1 )
        SmbCeDiscardExchange((PVOID)WriteOnlyOpenRetryContext);
      if ( SmbCeTraceExchangeReferenceCount )
        DbgPrint(
          "Dereference Exchange %p Type(%ld) %s %ld %ld\n",
          (const void *)WriteOnlyOpenRetryContext,
          *(unsigned __int8 *)WriteOnlyOpenRetryContext,
          "MRxSmbNamedPipeFsControlCompletion",
          738,
          *((_DWORD *)WriteOnlyOpenRetryContext + 1));
    }
    v6 = (void *)*((_QWORD *)P + 2);
    if ( v6 )
    {
      ExFreePoolWithTag(v6, 0);
      *((_QWORD *)P + 2) = 0;
    }
    ExFreePoolWithTag((PVOID)P, 0);
  }
}

```

## disassembly

```asm
0x14000f1d0  push    rbx
0x14000f1d2  push    rbp
0x14000f1d3  push    rsi
0x14000f1d4  push    rdi
0x14000f1d5  sub     rsp, 38h
0x14000f1d9  mov     rdi, rcx
0x14000f1dc  xor     esi, esi
0x14000f1de  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x14000f1e5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000f1ec  nop     dword ptr [rax+rax+00h]
0x14000f1f1  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x14000f1f7  or      eax, 0FFFFFFFFh
0x14000f1fa  lock xadd [rdi], eax
0x14000f1fe  cmp     eax, 1
0x14000f201  jnz     short loc_14000F218
0x14000f203  mov     rbx, [rdi+8]
0x14000f207  mov     bpl, al
0x14000f20a  test    rbx, rbx
0x14000f20d  jz      short loc_14000F21D
0x14000f20f  mov     rsi, [rbx+0E0h]
0x14000f216  jmp     short loc_14000F21D
0x14000f218  xor     ebx, ebx
0x14000f21a  xor     bpl, bpl
0x14000f21d  mov     dl, cs:s_SmbCeDbSpinLockSavedIrql; NewIrql
0x14000f223  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x14000f22a  call    cs:__imp_KeReleaseSpinLock
0x14000f231  nop     dword ptr [rax+rax+00h]
0x14000f236  test    bpl, bpl
0x14000f239  jz      loc_14000F2FA
0x14000f23f  test    rbx, rbx
0x14000f242  jz      short loc_14000F277
0x14000f244  mov     eax, [rdi+74h]
0x14000f247  mov     [rbx+0B0h], eax
0x14000f24d  cmp     eax, 0C0000008h
0x14000f252  jnz     short loc_14000F25E
0x14000f254  mov     dword ptr [rbx+0B0h], 0C00000C3h
0x14000f25e  mov     eax, [rdi+6Ch]
0x14000f261  mov     rcx, rbx; RxContext
0x14000f264  mov     [rbx+0B8h], rax
0x14000f26b  call    cs:__imp_RxLowIoCompletion
0x14000f272  nop     dword ptr [rax+rax+00h]
0x14000f277  test    rsi, rsi
0x14000f27a  jz      short loc_14000F2CA
0x14000f27c  or      eax, 0FFFFFFFFh
0x14000f27f  lock xadd [rsi+4], eax
0x14000f284  cmp     eax, 1
0x14000f287  jnz     short loc_14000F291
0x14000f289  mov     rcx, rsi; pContext
0x14000f28c  call    SmbCeDiscardExchange
0x14000f291  cmp     cs:SmbCeTraceExchangeReferenceCount, 0
0x14000f298  jz      short loc_14000F2CA
0x14000f29a  mov     eax, [rsi+4]
0x14000f29d  lea     r9, aMrxsmbnamedpip; "MRxSmbNamedPipeFsControlCompletion"
0x14000f2a4  movzx   r8d, byte ptr [rsi]
0x14000f2a8  lea     rcx, aDereferenceExc; "Dereference Exchange %p Type(%ld) %s %l"...
0x14000f2af  mov     [rsp+58h+var_30], eax
0x14000f2b3  mov     rdx, rsi
0x14000f2b6  mov     [rsp+58h+var_38], 2E2h
0x14000f2be  call    cs:__imp_DbgPrint
0x14000f2c5  nop     dword ptr [rax+rax+00h]
0x14000f2ca  mov     rcx, [rdi+10h]; P
0x14000f2ce  test    rcx, rcx
0x14000f2d1  jz      short loc_14000F2E9
0x14000f2d3  xor     edx, edx; Tag
0x14000f2d5  call    cs:__imp_ExFreePoolWithTag
0x14000f2dc  nop     dword ptr [rax+rax+00h]
0x14000f2e1  mov     qword ptr [rdi+10h], 0
0x14000f2e9  xor     edx, edx; Tag
0x14000f2eb  mov     rcx, rdi; P
0x14000f2ee  call    cs:__imp_ExFreePoolWithTag
0x14000f2f5  nop     dword ptr [rax+rax+00h]
0x14000f2fa  add     rsp, 38h
0x14000f2fe  pop     rdi
0x14000f2ff  pop     rsi
0x14000f300  pop     rbp
0x14000f301  pop     rbx
0x14000f302  retn
```
