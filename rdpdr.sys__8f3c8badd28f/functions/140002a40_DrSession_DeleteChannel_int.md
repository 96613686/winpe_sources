# DrSession::DeleteChannel(int)

- ea: `0x140002a40`
- end: `0x140002b1d`
- name: `?DeleteChannel@DrSession@@AEAAXH@Z`
- size: `221`
- prototype: `void __fastcall(DrSession *__hidden this, int)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x1400111d0`
- `0x14001bf2c`
- `0x14001c6e0`
- `0x140024360`

## callees

- `0x140001660`
- `0x140001830`
- `0x140002a40`
- `0x14001b608`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002a55`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002a55`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002a96`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002a96`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002ae2`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002ae2`
- `ntoskrnl!KeResetEvent` at `0x140002af5`
- `ntoskrnl!KeResetEvent` at `0x140002af5`

## pseudocode

```c
void __fastcall DrSession::DeleteChannel(DrSession *this, int a2)
{
  KIRQL v4; // al
  volatile signed __int32 *v5; // rbx
  KIRQL v6; // si
  RefCount *v7; // rcx
  int v8; // ebx
  RefCount *v9; // [rsp+60h] [rbp+8h] BYREF

  v4 = KeAcquireSpinLockRaiseToDpc(&DrSpinLock);
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 5);
  v6 = v4;
  v9 = (RefCount *)v5;
  if ( v5 )
    _InterlockedIncrement(v5 + 4);
  v7 = (RefCount *)*((_QWORD *)this + 5);
  if ( v7 )
    RefCount::Release(v7);
  *((_QWORD *)this + 5) = 0;
  KeReleaseSpinLock(&DrSpinLock, v6);
  if ( v5 )
  {
    v8 = VirtualChannel::SubmitClose((VirtualChannel *)v5);
    SmartPtr<VirtualChannel>::operator=(&v9, 0);
    if ( a2 && !v8 )
    {
      while ( KeWaitForSingleObject((char *)this + 640, UserRequest, 0, 1u, 0) )
        ;
      KeResetEvent((PRKEVENT)((char *)this + 640));
    }
    if ( v9 )
      RefCount::Release(v9);
  }
}

```

## disassembly

```asm
0x140002a40  push    rbx
0x140002a42  push    rbp
0x140002a43  push    rsi
0x140002a44  push    rdi
0x140002a45  sub     rsp, 38h
0x140002a49  mov     rdi, rcx
0x140002a4c  mov     ebp, edx
0x140002a4e  lea     rcx, ?DrSpinLock@@3_KA; SpinLock
0x140002a55  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002a5c  nop     dword ptr [rax+rax+00h]
0x140002a61  mov     rbx, [rdi+28h]
0x140002a65  mov     sil, al
0x140002a68  mov     [rsp+58h+arg_0], rbx
0x140002a6d  test    rbx, rbx
0x140002a70  jz      short loc_140002A76
0x140002a72  lock inc dword ptr [rbx+10h]
0x140002a76  mov     rcx, [rdi+28h]; this
0x140002a7a  test    rcx, rcx
0x140002a7d  jz      short loc_140002A84
0x140002a7f  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x140002a84  mov     dl, sil; NewIrql
0x140002a87  mov     qword ptr [rdi+28h], 0
0x140002a8f  lea     rcx, ?DrSpinLock@@3_KA; SpinLock
0x140002a96  call    cs:__imp_KeReleaseSpinLock
0x140002a9d  nop     dword ptr [rax+rax+00h]
0x140002aa2  test    rbx, rbx
0x140002aa5  jz      short loc_140002B13
0x140002aa7  mov     rcx, rbx; this
0x140002aaa  call    ?SubmitClose@VirtualChannel@@QEAAJXZ; VirtualChannel::SubmitClose(void)
0x140002aaf  xor     edx, edx
0x140002ab1  lea     rcx, [rsp+58h+arg_0]
0x140002ab6  mov     ebx, eax
0x140002ab8  call    ??4?$SmartPtr@VVirtualChannel@@@@QEAAAEAV0@PEAVVirtualChannel@@@Z; SmartPtr<VirtualChannel>::operator=(VirtualChannel *)
0x140002abd  test    ebp, ebp
0x140002abf  jz      short loc_140002B01
0x140002ac1  test    ebx, ebx
0x140002ac3  jnz     short loc_140002B01
0x140002ac5  lea     rbx, [rdi+280h]
0x140002acc  xor     r8d, r8d; WaitMode
0x140002acf  mov     [rsp+58h+Timeout], 0; Timeout
0x140002ad8  mov     r9b, 1; Alertable
0x140002adb  mov     rcx, rbx; Object
0x140002ade  lea     edx, [r8+6]; WaitReason
0x140002ae2  call    cs:__imp_KeWaitForSingleObject
0x140002ae9  nop     dword ptr [rax+rax+00h]
0x140002aee  test    eax, eax
0x140002af0  jnz     short loc_140002ACC
0x140002af2  mov     rcx, rbx; Event
0x140002af5  call    cs:__imp_KeResetEvent
0x140002afc  nop     dword ptr [rax+rax+00h]
0x140002b01  mov     rbx, [rsp+58h+arg_0]
0x140002b06  test    rbx, rbx
0x140002b09  jz      short loc_140002B13
0x140002b0b  mov     rcx, rbx; this
0x140002b0e  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x140002b13  add     rsp, 38h
0x140002b17  pop     rdi
0x140002b18  pop     rsi
0x140002b19  pop     rbp
0x140002b1a  pop     rbx
0x140002b1b  retn
```
