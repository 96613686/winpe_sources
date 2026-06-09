# NbtCancelDisconnectWait

- ea: `0x14002de10`
- end: `0x14002dee2`
- name: `NbtCancelDisconnectWait`
- size: `210`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14002de10`
- `0x140040294`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14002dec5`
- `ntoskrnl!IofCompleteRequest` at `0x14002dec5`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002de53`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002de53`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002de69`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002de69`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002deb4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002deb4`

## pseudocode

```c
void __fastcall NbtCancelDisconnectWait(__int64 a1, IRP *a2)
{
  KSPIN_LOCK *FsContext; // rdi
  KIRQL v4; // al

  if ( (BYTE3(xmmword_140038420) & 2) != 0 )
    WPP_SF_(1049, 90, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids);
  FsContext = (KSPIN_LOCK *)a2->Tail.Overlay.CurrentStackLocation->FileObject->FsContext;
  IoReleaseCancelSpinLock(a2->CancelIrql);
  v4 = KeAcquireSpinLockRaiseToDpc(FsContext + 31);
  if ( !FsContext || ((*((_DWORD *)FsContext + 4) - 829321027) & 0xFEFFFFFF) != 0 )
  {
    a2->IoStatus.Status = -1073741816;
  }
  else if ( (IRP *)FsContext[21] == a2 )
  {
    FsContext[21] = 0;
    a2->IoStatus.Status = -1073741536;
  }
  KeReleaseSpinLock(FsContext + 31, v4);
  IofCompleteRequest(a2, 2);
}

```

## disassembly

```asm
0x14002de10  mov     [rsp+arg_0], rbx
0x14002de15  mov     [rsp+arg_8], rsi
0x14002de1a  push    rdi
0x14002de1b  sub     rsp, 20h
0x14002de1f  mov     rbx, rdx
0x14002de22  test    byte ptr cs:xmmword_140038420+3, 2
0x14002de29  jz      short loc_14002DE41
0x14002de2b  mov     edx, 5Ah ; 'Z'
0x14002de30  lea     r8, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids
0x14002de37  mov     ecx, 419h
0x14002de3c  call    WPP_SF_
0x14002de41  mov     rax, [rbx+0B8h]
0x14002de48  mov     rcx, [rax+30h]
0x14002de4c  mov     rdi, [rcx+18h]
0x14002de50  mov     cl, [rbx+45h]; Irql
0x14002de53  call    cs:__imp_IoReleaseCancelSpinLock
0x14002de5a  nop     dword ptr [rax+rax+00h]
0x14002de5f  lea     rsi, [rdi+0F8h]
0x14002de66  mov     rcx, rsi; SpinLock
0x14002de69  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002de70  nop     dword ptr [rax+rax+00h]
0x14002de75  test    rdi, rdi
0x14002de78  jz      short loc_14002DEA8
0x14002de7a  mov     ecx, [rdi+10h]
0x14002de7d  sub     ecx, 316E6F43h
0x14002de83  test    ecx, 0FEFFFFFFh
0x14002de89  jnz     short loc_14002DEA8
0x14002de8b  cmp     [rdi+0A8h], rbx
0x14002de92  jnz     short loc_14002DEAF
0x14002de94  mov     qword ptr [rdi+0A8h], 0
0x14002de9f  mov     dword ptr [rbx+30h], 0C0000120h
0x14002dea6  jmp     short loc_14002DEAF
0x14002dea8  mov     dword ptr [rbx+30h], 0C0000008h
0x14002deaf  mov     dl, al; NewIrql
0x14002deb1  mov     rcx, rsi; SpinLock
0x14002deb4  call    cs:__imp_KeReleaseSpinLock
0x14002debb  nop     dword ptr [rax+rax+00h]
0x14002dec0  mov     dl, 2; PriorityBoost
0x14002dec2  mov     rcx, rbx; Irp
0x14002dec5  call    cs:__imp_IofCompleteRequest
0x14002decc  nop     dword ptr [rax+rax+00h]
0x14002ded1  mov     rbx, [rsp+28h+arg_0]
0x14002ded6  mov     rsi, [rsp+28h+arg_8]
0x14002dedb  add     rsp, 20h
0x14002dedf  pop     rdi
0x14002dee0  retn
```
