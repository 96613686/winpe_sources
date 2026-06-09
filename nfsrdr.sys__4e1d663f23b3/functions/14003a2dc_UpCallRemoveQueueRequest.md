# UpCallRemoveQueueRequest

- ea: `0x14003a2dc`
- end: `0x14003a487`
- name: `UpCallRemoveQueueRequest`
- size: `427`
- prototype: `__int64 __fastcall(__int64 SpinLock, _DWORD *, unsigned int *, unsigned int *, __int64, PLIST_ENTRY *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140039010`

## callees

- `0x140014570`
- `0x140039db8`
- `0x14003a134`
- `0x14003a2dc`
- `0x14003a5b8`

## import_xrefs

- `ntoskrnl!ExGetPreviousMode` at `0x14003a2fe`
- `ntoskrnl!ExGetPreviousMode` at `0x14003a2fe`
- `ntoskrnl!MmIsKernelAddress` at `0x14003a331`
- `ntoskrnl!MmIsKernelAddress` at `0x14003a331`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003a3f6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003a3f6`
- `ntoskrnl!KeRemoveQueue` at `0x14003a313`
- `ntoskrnl!KeRemoveQueue` at `0x14003a313`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003a3da`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003a3da`
- `ntoskrnl!DbgPrint` at `0x14003a422`
- `ntoskrnl!DbgPrint` at `0x14003a422`

## string_xrefs

- `0x14003a41b`: `RemoveUpcall failed completing status %x\n`

## pseudocode

```c
__int64 __fastcall UpCallRemoveQueueRequest(
        __int64 SpinLock,
        _DWORD *a2,
        unsigned int *a3,
        unsigned int *a4,
        __int64 a5,
        PLIST_ENTRY *a6)
{
  KPROCESSOR_MODE PreviousMode; // al
  PLIST_ENTRY v11; // rdi
  unsigned int updated; // ebx
  __int64 v13; // rcx
  unsigned int v14; // eax
  KIRQL v15; // al
  _DWORD v17[2]; // [rsp+38h] [rbp-50h] BYREF
  __int64 v18; // [rsp+40h] [rbp-48h]

  while ( 1 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(SpinLock + 104));
    PreviousMode = ExGetPreviousMode();
    v11 = KeRemoveQueue((PRKQUEUE)(SpinLock + 40), PreviousMode, 0);
    _InterlockedDecrement((volatile signed __int32 *)(SpinLock + 104));
    if ( !(unsigned __int8)MmIsKernelAddress(v11) )
      break;
    if ( v11 == (PLIST_ENTRY)(SpinLock + 112) )
      return (unsigned int)-1073741536;
    if ( _InterlockedExchange((volatile __int32 *)&v11[1], 64) != 128 )
    {
      updated = UpdateUserBuffer(SpinLock, (__int64)v11, a3, a4);
      *a2 = v11[10].Flink;
      *a4 = (unsigned int)v11[11].Flink;
      *a6 = v11;
      v14 = UpCallDereferenceQueueRequest(v13, v11);
      if ( v14 )
        updated = v14;
      if ( updated )
      {
        v17[1] = 0;
        v17[0] = updated;
        v18 = 0;
        DbgPrint("RemoveUpcall failed completing status %x\n", updated);
        FinalizeRequest((PKSPIN_LOCK)SpinLock, (volatile __int32 *)v11, (__int64)v17, 0, 0);
      }
      else if ( (HIDWORD(v11[1].Flink) & 1) == 0 )
      {
        v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SpinLock);
        v11->Flink = *(struct _LIST_ENTRY **)(SpinLock + 32);
        *(_QWORD *)(SpinLock + 32) = v11;
        KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v15);
      }
      return updated;
    }
    FreeRequest((PKSPIN_LOCK)SpinLock, v11);
  }
  updated = (unsigned int)v11;
  if ( (_DWORD)v11 != 258 && (_DWORD)v11 != 192 && (_DWORD)v11 != 128 && (int)v11 >= 0 )
    return (unsigned int)-1073740768;
  return updated;
}

```

## disassembly

```asm
0x14003a2dc  mov     [rsp+arg_0], rcx
0x14003a2e1  push    rbx
0x14003a2e2  push    rsi
0x14003a2e3  push    rdi
0x14003a2e4  push    r12
0x14003a2e6  push    r14
0x14003a2e8  push    r15
0x14003a2ea  sub     rsp, 58h
0x14003a2ee  mov     r14, r9
0x14003a2f1  mov     r15, r8
0x14003a2f4  mov     r12, rdx
0x14003a2f7  mov     rsi, rcx
0x14003a2fa  lock inc dword ptr [rsi+68h]
0x14003a2fe  call    cs:__imp_ExGetPreviousMode
0x14003a305  nop     dword ptr [rax+rax+00h]
0x14003a30a  mov     dl, al; WaitMode
0x14003a30c  xor     r8d, r8d; Timeout
0x14003a30f  lea     rcx, [rsi+28h]; Queue
0x14003a313  call    cs:__imp_KeRemoveQueue
0x14003a31a  nop     dword ptr [rax+rax+00h]
0x14003a31f  mov     rdi, rax
0x14003a322  mov     [rsp+88h+arg_20], rax
0x14003a32a  lock dec dword ptr [rsi+68h]
0x14003a32e  mov     rcx, rax
0x14003a331  call    cs:__imp_MmIsKernelAddress
0x14003a338  nop     dword ptr [rax+rax+00h]
0x14003a33d  test    al, al
0x14003a33f  jz      loc_14003A452
0x14003a345  lea     rcx, [rsi+70h]
0x14003a349  cmp     rdi, rcx
0x14003a34c  jz      loc_14003A44B
0x14003a352  mov     eax, 40h ; '@'
0x14003a357  xchg    eax, [rdi+10h]
0x14003a35a  cmp     eax, 80h
0x14003a35f  jnz     short loc_14003A36E
0x14003a361  mov     rdx, rdi; P
0x14003a364  mov     rcx, rsi; SpinLock
0x14003a367  call    FreeRequest
0x14003a36c  jmp     short loc_14003A2FA
0x14003a36e  mov     r9, r14
0x14003a371  mov     r8, r15
0x14003a374  mov     rdx, rdi
0x14003a377  mov     rcx, rsi
0x14003a37a  call    UpdateUserBuffer
0x14003a37f  mov     ebx, eax
0x14003a381  mov     [rsp+88h+var_58], eax
0x14003a385  mov     eax, [rdi+0A0h]
0x14003a38b  mov     [r12], eax
0x14003a38f  mov     eax, [rdi+0B0h]
0x14003a395  mov     [r14], eax
0x14003a398  mov     rax, [rsp+88h+arg_28]
0x14003a3a0  mov     [rax], rdi
0x14003a3a3  jmp     short loc_14003A3BB
0x14003a3a5  mov     ebx, eax
0x14003a3a7  mov     [rsp+88h+var_58], eax
0x14003a3ab  mov     rsi, [rsp+88h+arg_0]
0x14003a3b3  mov     rdi, [rsp+88h+arg_20]
0x14003a3bb  mov     rdx, rdi
0x14003a3be  call    UpCallDereferenceQueueRequest
0x14003a3c3  test    eax, eax
0x14003a3c5  cmovnz  ebx, eax
0x14003a3c8  test    ebx, ebx
0x14003a3ca  jnz     short loc_14003A404
0x14003a3cc  mov     eax, [rdi+14h]
0x14003a3cf  test    al, 1
0x14003a3d1  jnz     loc_14003A476
0x14003a3d7  mov     rcx, rsi; SpinLock
0x14003a3da  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003a3e1  nop     dword ptr [rax+rax+00h]
0x14003a3e6  mov     rcx, [rsi+20h]
0x14003a3ea  mov     [rdi], rcx
0x14003a3ed  mov     [rsi+20h], rdi
0x14003a3f1  mov     dl, al; NewIrql
0x14003a3f3  mov     rcx, rsi; SpinLock
0x14003a3f6  call    cs:__imp_KeReleaseSpinLock
0x14003a3fd  nop     dword ptr [rax+rax+00h]
0x14003a402  jmp     short loc_14003A476
0x14003a404  mov     [rsp+88h+var_4C], 0
0x14003a40c  mov     [rsp+88h+var_50], ebx
0x14003a410  mov     [rsp+88h+var_48], 0
0x14003a419  mov     edx, ebx
0x14003a41b  lea     rcx, Format; "RemoveUpcall failed completing status %"...
0x14003a422  call    cs:__imp_DbgPrint
0x14003a429  nop     dword ptr [rax+rax+00h]
0x14003a42e  mov     [rsp+88h+var_68], 0; int
0x14003a436  xor     r9d, r9d
0x14003a439  lea     r8, [rsp+88h+var_50]
0x14003a43e  mov     rdx, rdi; P
0x14003a441  mov     rcx, rsi; SpinLock
0x14003a444  call    FinalizeRequest
0x14003a449  jmp     short loc_14003A476
0x14003a44b  mov     ebx, 0C0000120h
0x14003a450  jmp     short loc_14003A476
0x14003a452  mov     ebx, edi
0x14003a454  cmp     edi, 102h
0x14003a45a  jz      short loc_14003A476
0x14003a45c  cmp     ebx, 0C0h
0x14003a462  jz      short loc_14003A476
0x14003a464  cmp     ebx, 80h
0x14003a46a  jz      short loc_14003A476
0x14003a46c  mov     eax, 0C0000420h
0x14003a471  test    ebx, ebx
0x14003a473  cmovns  ebx, eax
0x14003a476  mov     eax, ebx
0x14003a478  add     rsp, 58h
0x14003a47c  pop     r15
0x14003a47e  pop     r14
0x14003a480  pop     r12
0x14003a482  pop     rdi
0x14003a483  pop     rsi
0x14003a484  pop     rbx
0x14003a485  retn
```
