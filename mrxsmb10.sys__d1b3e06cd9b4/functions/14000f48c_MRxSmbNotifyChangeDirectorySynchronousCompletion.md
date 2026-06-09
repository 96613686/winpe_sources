# MRxSmbNotifyChangeDirectorySynchronousCompletion

- ea: `0x14000f48c`
- end: `0x14000f56b`
- name: `MRxSmbNotifyChangeDirectorySynchronousCompletion`
- size: `223`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140030bb0`

## callees

- `0x14000f48c`
- `0x140052944`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000f4ea`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f4ea`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f49f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f49f`
- `ntoskrnl!DbgPrint` at `0x14000f542`
- `ntoskrnl!DbgPrint` at `0x14000f542`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f553`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f553`

## string_xrefs

- `0x14000f521`: `MRxSmbNotifyChangeDirectorySynchronousCompletion`

## pseudocode

```c
__int64 __fastcall MRxSmbNotifyChangeDirectorySynchronousCompletion(volatile signed __int32 *P)
{
  char v2; // bp
  __int64 v3; // rax
  unsigned __int8 *v4; // rbx
  unsigned int v5; // esi

  s_SmbCeDbSpinLockSavedIrql = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
  if ( _InterlockedExchangeAdd(P, 0xFFFFFFFF) == 1 )
  {
    v2 = 1;
    v3 = *((_QWORD *)P + 1);
    v4 = *(unsigned __int8 **)(v3 + 224);
    v5 = *(_DWORD *)(v3 + 176);
  }
  else
  {
    v4 = 0;
    v5 = 259;
    v2 = 0;
  }
  KeReleaseSpinLock(&s_SmbCeDbSpinLock, s_SmbCeDbSpinLockSavedIrql);
  if ( v2 )
  {
    if ( v4 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 1, 0xFFFFFFFF) == 1 )
        SmbCeDiscardExchange((char *)v4);
      if ( SmbCeTraceExchangeReferenceCount )
        DbgPrint(
          "Dereference Exchange %p Type(%ld) %s %ld %ld\n",
          v4,
          *v4,
          "MRxSmbNotifyChangeDirectorySynchronousCompletion",
          376,
          *((_DWORD *)v4 + 1));
    }
    ExFreePoolWithTag((PVOID)P, 0);
  }
  return v5;
}

```

## disassembly

```asm
0x14000f48c  push    rbx
0x14000f48e  push    rbp
0x14000f48f  push    rsi
0x14000f490  push    rdi
0x14000f491  sub     rsp, 38h
0x14000f495  mov     rdi, rcx
0x14000f498  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x14000f49f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000f4a6  nop     dword ptr [rax+rax+00h]
0x14000f4ab  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x14000f4b1  or      eax, 0FFFFFFFFh
0x14000f4b4  lock xadd [rdi], eax
0x14000f4b8  cmp     eax, 1
0x14000f4bb  jnz     short loc_14000F4D3
0x14000f4bd  mov     bpl, al
0x14000f4c0  mov     rax, [rdi+8]
0x14000f4c4  mov     rbx, [rax+0E0h]
0x14000f4cb  mov     esi, [rax+0B0h]
0x14000f4d1  jmp     short loc_14000F4DD
0x14000f4d3  xor     ebx, ebx
0x14000f4d5  mov     esi, 103h
0x14000f4da  xor     bpl, bpl
0x14000f4dd  mov     dl, cs:s_SmbCeDbSpinLockSavedIrql; NewIrql
0x14000f4e3  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x14000f4ea  call    cs:__imp_KeReleaseSpinLock
0x14000f4f1  nop     dword ptr [rax+rax+00h]
0x14000f4f6  test    bpl, bpl
0x14000f4f9  jz      short loc_14000F55F
0x14000f4fb  test    rbx, rbx
0x14000f4fe  jz      short loc_14000F54E
0x14000f500  or      eax, 0FFFFFFFFh
0x14000f503  lock xadd [rbx+4], eax
0x14000f508  cmp     eax, 1
0x14000f50b  jnz     short loc_14000F515
0x14000f50d  mov     rcx, rbx; pContext
0x14000f510  call    SmbCeDiscardExchange
0x14000f515  cmp     cs:SmbCeTraceExchangeReferenceCount, 0
0x14000f51c  jz      short loc_14000F54E
0x14000f51e  mov     ecx, [rbx+4]
0x14000f521  lea     r9, aMrxsmbnotifych; "MRxSmbNotifyChangeDirectorySynchronousC"...
0x14000f528  movzx   r8d, byte ptr [rbx]
0x14000f52c  mov     rdx, rbx
0x14000f52f  mov     [rsp+58h+var_30], ecx
0x14000f533  lea     rcx, aDereferenceExc; "Dereference Exchange %p Type(%ld) %s %l"...
0x14000f53a  mov     [rsp+58h+var_38], 178h
0x14000f542  call    cs:__imp_DbgPrint
0x14000f549  nop     dword ptr [rax+rax+00h]
0x14000f54e  xor     edx, edx; Tag
0x14000f550  mov     rcx, rdi; P
0x14000f553  call    cs:__imp_ExFreePoolWithTag
0x14000f55a  nop     dword ptr [rax+rax+00h]
0x14000f55f  mov     eax, esi
0x14000f561  add     rsp, 38h
0x14000f565  pop     rdi
0x14000f566  pop     rsi
0x14000f567  pop     rbp
0x14000f568  pop     rbx
0x14000f569  retn
```
