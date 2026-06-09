# PxCancelGetEvents

- ea: `0x140010b60`
- end: `0x140010c1b`
- name: `PxCancelGetEvents`
- size: `187`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001bc8`
- `0x140010b60`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010bb0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010bb0`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140010b9d`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140010b9d`
- `ntoskrnl!IofCompleteRequest` at `0x140010c08`
- `ntoskrnl!IofCompleteRequest` at `0x140010c08`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010bdd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010bdd`

## pseudocode

```c
void __fastcall PxCancelGetEvents(__int64 a1, __int64 a2)
{
  KIRQL v3; // al
  struct _LIST_ENTRY *Blink; // rbx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_713d02be0a463cb5141fa39da77025f3_Traceguids, a2);
  IoReleaseCancelSpinLock(*(_BYTE *)(a2 + 69));
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels);
  Blink = WPP_MAIN_CB.Queue.ListEntry.Blink;
  LOBYTE(WPP_MAIN_CB.Queue.Wcb.DeviceRoutine) = v3;
  WPP_MAIN_CB.Queue.ListEntry.Blink = 0;
  KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels, v3);
  if ( Blink )
  {
    _InterlockedExchange64((volatile __int64 *)&Blink[6].Blink, 0);
    LODWORD(Blink[3].Flink) = -1073741536;
    Blink[3].Blink = 0;
    IofCompleteRequest((PIRP)Blink, 0);
  }
}

```

## disassembly

```asm
0x140010b60  push    rbx
0x140010b62  sub     rsp, 20h
0x140010b66  mov     rbx, rdx
0x140010b69  mov     rcx, cs:WPP_GLOBAL_Control
0x140010b70  lea     rax, WPP_GLOBAL_Control
0x140010b77  cmp     rcx, rax
0x140010b7a  jz      short loc_140010B9A
0x140010b7c  cmp     byte ptr [rcx+29h], 5
0x140010b80  jb      short loc_140010B9A
0x140010b82  mov     rcx, [rcx+18h]
0x140010b86  lea     r8, WPP_713d02be0a463cb5141fa39da77025f3_Traceguids
0x140010b8d  mov     edx, 2Ah ; '*'
0x140010b92  mov     r9, rbx
0x140010b95  call    WPP_SF_q
0x140010b9a  mov     cl, [rbx+45h]; Irql
0x140010b9d  call    cs:__imp_IoReleaseCancelSpinLock
0x140010ba4  nop     dword ptr [rax+rax+00h]
0x140010ba9  lea     rcx, WPP_MAIN_CB.Queue+10h; SpinLock
0x140010bb0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010bb7  nop     dword ptr [rax+rax+00h]
0x140010bbc  mov     rbx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140010bc3  lea     rcx, WPP_MAIN_CB.Queue+10h; SpinLock
0x140010bca  mov     dl, al; NewIrql
0x140010bcc  mov     byte ptr cs:WPP_MAIN_CB.Queue+18h, al
0x140010bd2  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, 0
0x140010bdd  call    cs:__imp_KeReleaseSpinLock
0x140010be4  nop     dword ptr [rax+rax+00h]
0x140010be9  test    rbx, rbx
0x140010bec  jz      short loc_140010C14
0x140010bee  xor     eax, eax
0x140010bf0  xor     edx, edx; PriorityBoost
0x140010bf2  xchg    rax, [rbx+68h]
0x140010bf6  mov     rcx, rbx; Irp
0x140010bf9  mov     dword ptr [rbx+30h], 0C0000120h
0x140010c00  mov     qword ptr [rbx+38h], 0
0x140010c08  call    cs:__imp_IofCompleteRequest
0x140010c0f  nop     dword ptr [rax+rax+00h]
0x140010c14  add     rsp, 20h
0x140010c18  pop     rbx
0x140010c19  retn
```
