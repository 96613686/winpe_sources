# UpCallRemoveQueueRequest

- ea: `0x140015c84`
- end: `0x140015e49`
- name: `UpCallRemoveQueueRequest`
- size: `453`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock, _DWORD *, __int64, _DWORD *, _DWORD *, PLIST_ENTRY *, __int64, PLARGE_INTEGER Timeout)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140086fd8`

## callees

- `0x140013b04`
- `0x140014338`
- `0x1400154b4`
- `0x140015c84`
- `0x140019194`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x140015de4`
- `ntoskrnl!DbgPrint` at `0x140015de4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015db8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015db8`
- `ntoskrnl!KeRemoveQueue` at `0x140015cc0`
- `ntoskrnl!KeRemoveQueue` at `0x140015cc0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015d9c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015d9c`
- `ntoskrnl!ExGetPreviousMode` at `0x140015ca6`
- `ntoskrnl!ExGetPreviousMode` at `0x140015ca6`
- `ntoskrnl!MmIsKernelAddress` at `0x140015cde`
- `ntoskrnl!MmIsKernelAddress` at `0x140015cde`

## string_xrefs

- `0x140015ddd`: `RemoveUpcall failed completing status %x\n`

## pseudocode

```c
__int64 __fastcall UpCallRemoveQueueRequest(
        PKSPIN_LOCK SpinLock,
        _DWORD *a2,
        __int64 a3,
        _DWORD *a4,
        _DWORD *a5,
        PLIST_ENTRY *a6,
        __int64 a7,
        PLARGE_INTEGER Timeout)
{
  KPROCESSOR_MODE PreviousMode; // al
  PLIST_ENTRY v13; // rdi
  unsigned int updated; // ebx
  unsigned int v15; // eax
  KIRQL v16; // al

  while ( 1 )
  {
    _InterlockedIncrement((volatile signed __int32 *)SpinLock + 26);
    PreviousMode = ExGetPreviousMode();
    v13 = KeRemoveQueue((PRKQUEUE)(SpinLock + 5), PreviousMode, Timeout);
    _InterlockedDecrement((volatile signed __int32 *)SpinLock + 26);
    if ( !(unsigned __int8)MmIsKernelAddress(v13) )
      break;
    if ( v13 == (PLIST_ENTRY)(SpinLock + 14) )
      return (unsigned int)-1073741536;
    if ( _InterlockedExchange((volatile __int32 *)&v13[1], 64) != 128 )
    {
      updated = UpdateUserBuffer(SpinLock, v13, a3, a4);
      *a2 = v13[10].Flink;
      *a4 = v13[11].Flink;
      *a6 = v13;
      if ( a5 )
        *a5 = v13[12].Flink;
      v15 = UpCallDereferenceQueueRequest(a5, v13);
      if ( v15 )
        updated = v15;
      if ( updated )
      {
        DbgPrint("RemoveUpcall failed completing status %x\n", updated);
        FinalizeRequest(SpinLock, v13, 0);
      }
      else if ( (HIDWORD(v13[1].Flink) & 1) == 0 )
      {
        v16 = KeAcquireSpinLockRaiseToDpc(SpinLock);
        v13->Flink = (struct _LIST_ENTRY *)SpinLock[4];
        SpinLock[4] = (KSPIN_LOCK)v13;
        KeReleaseSpinLock(SpinLock, v16);
      }
      return updated;
    }
    FreeRequest(SpinLock, v13);
  }
  updated = (unsigned int)v13;
  if ( (_DWORD)v13 != 258 && (_DWORD)v13 != 192 && (_DWORD)v13 != 128 && (int)v13 >= 0 )
    return (unsigned int)-1073740768;
  return updated;
}

```

## disassembly

```asm
0x140015c84  mov     [rsp+arg_0], rcx
0x140015c89  push    rbx
0x140015c8a  push    rsi
0x140015c8b  push    rdi
0x140015c8c  push    r12
0x140015c8e  push    r14
0x140015c90  push    r15
0x140015c92  sub     rsp, 58h
0x140015c96  mov     r14, r9
0x140015c99  mov     r15, r8
0x140015c9c  mov     r12, rdx
0x140015c9f  mov     rsi, rcx
0x140015ca2  lock inc dword ptr [rsi+68h]
0x140015ca6  call    cs:__imp_ExGetPreviousMode
0x140015cad  nop     dword ptr [rax+rax+00h]
0x140015cb2  mov     dl, al; WaitMode
0x140015cb4  mov     r8, [rsp+88h+Timeout]; Timeout
0x140015cbc  lea     rcx, [rsi+28h]; Queue
0x140015cc0  call    cs:__imp_KeRemoveQueue
0x140015cc7  nop     dword ptr [rax+rax+00h]
0x140015ccc  mov     rdi, rax
0x140015ccf  mov     [rsp+88h+arg_30], rax
0x140015cd7  lock dec dword ptr [rsi+68h]
0x140015cdb  mov     rcx, rax
0x140015cde  call    cs:__imp_MmIsKernelAddress
0x140015ce5  nop     dword ptr [rax+rax+00h]
0x140015cea  test    al, al
0x140015cec  jz      loc_140015E14
0x140015cf2  lea     rcx, [rsi+70h]
0x140015cf6  cmp     rdi, rcx
0x140015cf9  jz      loc_140015E0D
0x140015cff  mov     eax, 40h ; '@'
0x140015d04  xchg    eax, [rdi+10h]
0x140015d07  cmp     eax, 80h
0x140015d0c  jnz     short loc_140015D1B
0x140015d0e  mov     rdx, rdi; P
0x140015d11  mov     rcx, rsi; SpinLock
0x140015d14  call    FreeRequest
0x140015d19  jmp     short loc_140015CA2
0x140015d1b  mov     r9, r14
0x140015d1e  mov     r8, r15
0x140015d21  mov     rdx, rdi
0x140015d24  mov     rcx, rsi
0x140015d27  call    UpdateUserBuffer
0x140015d2c  mov     ebx, eax
0x140015d2e  mov     [rsp+88h+var_58], eax
0x140015d32  mov     eax, [rdi+0A0h]
0x140015d38  mov     [r12], eax
0x140015d3c  mov     eax, [rdi+0B0h]
0x140015d42  mov     [r14], eax
0x140015d45  mov     rax, [rsp+88h+arg_28]
0x140015d4d  mov     [rax], rdi
0x140015d50  mov     rcx, [rsp+88h+arg_20]
0x140015d58  test    rcx, rcx
0x140015d5b  jz      short loc_140015D65
0x140015d5d  mov     eax, [rdi+0C0h]
0x140015d63  mov     [rcx], eax
0x140015d65  jmp     short loc_140015D7D
0x140015d67  mov     ebx, eax
0x140015d69  mov     [rsp+88h+var_58], eax
0x140015d6d  mov     rsi, [rsp+88h+arg_0]
0x140015d75  mov     rdi, [rsp+88h+arg_30]
0x140015d7d  mov     rdx, rdi
0x140015d80  call    UpCallDereferenceQueueRequest
0x140015d85  test    eax, eax
0x140015d87  cmovnz  ebx, eax
0x140015d8a  test    ebx, ebx
0x140015d8c  jnz     short loc_140015DC6
0x140015d8e  mov     eax, [rdi+14h]
0x140015d91  test    al, 1
0x140015d93  jnz     loc_140015E38
0x140015d99  mov     rcx, rsi; SpinLock
0x140015d9c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015da3  nop     dword ptr [rax+rax+00h]
0x140015da8  mov     rcx, [rsi+20h]
0x140015dac  mov     [rdi], rcx
0x140015daf  mov     [rsi+20h], rdi
0x140015db3  mov     dl, al; NewIrql
0x140015db5  mov     rcx, rsi; SpinLock
0x140015db8  call    cs:__imp_KeReleaseSpinLock
0x140015dbf  nop     dword ptr [rax+rax+00h]
0x140015dc4  jmp     short loc_140015E38
0x140015dc6  mov     [rsp+88h+var_4C], 0
0x140015dce  mov     [rsp+88h+var_50], ebx
0x140015dd2  mov     [rsp+88h+var_48], 0
0x140015ddb  mov     edx, ebx
0x140015ddd  lea     rcx, Format; "RemoveUpcall failed completing status %"...
0x140015de4  call    cs:__imp_DbgPrint
0x140015deb  nop     dword ptr [rax+rax+00h]
0x140015df0  mov     [rsp+88h+var_68], 0; int
0x140015df8  xor     r9d, r9d
0x140015dfb  lea     r8, [rsp+88h+var_50]
0x140015e00  mov     rdx, rdi; P
0x140015e03  mov     rcx, rsi; SpinLock
0x140015e06  call    FinalizeRequest
0x140015e0b  jmp     short loc_140015E38
0x140015e0d  mov     ebx, 0C0000120h
0x140015e12  jmp     short loc_140015E38
0x140015e14  mov     ebx, edi
0x140015e16  cmp     edi, 102h
0x140015e1c  jz      short loc_140015E38
0x140015e1e  cmp     ebx, 0C0h
0x140015e24  jz      short loc_140015E38
0x140015e26  cmp     ebx, 80h
0x140015e2c  jz      short loc_140015E38
0x140015e2e  mov     eax, 0C0000420h
0x140015e33  test    ebx, ebx
0x140015e35  cmovns  ebx, eax
0x140015e38  mov     eax, ebx
0x140015e3a  add     rsp, 58h
0x140015e3e  pop     r15
0x140015e40  pop     r14
0x140015e42  pop     r12
0x140015e44  pop     rdi
0x140015e45  pop     rsi
0x140015e46  pop     rbx
0x140015e47  retn
```
