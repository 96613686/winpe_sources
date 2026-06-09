# lldpRemoveBindingFromDriver

- ea: `0x1400046a4`
- end: `0x140004717`
- name: `lldpRemoveBindingFromDriver`
- size: `115`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140012000`
- `0x140012730`

## callees

- `0x1400046a4`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400046b4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400046b4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004704`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004704`

## pseudocode

```c
void __fastcall lldpRemoveBindingFromDriver(PVOID *a1)
{
  PVOID *DeviceContext; // rax
  _QWORD *v3; // rcx

  LOBYTE(WPP_MAIN_CB.Queue.Wcb.DeviceRoutine) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels);
  DeviceContext = (PVOID *)WPP_MAIN_CB.Queue.Wcb.DeviceContext;
  if ( WPP_MAIN_CB.Queue.Wcb.DeviceContext == a1 )
  {
    WPP_MAIN_CB.Queue.Wcb.DeviceContext = a1[3];
  }
  else
  {
    while ( DeviceContext )
    {
      v3 = DeviceContext + 3;
      DeviceContext = (PVOID *)DeviceContext[3];
      if ( DeviceContext == a1 )
      {
        *v3 = a1[3];
        break;
      }
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels, (KIRQL)WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
}

```

## disassembly

```asm
0x1400046a4  push    rbx
0x1400046a6  sub     rsp, 20h
0x1400046aa  mov     rbx, rcx
0x1400046ad  lea     rcx, WPP_MAIN_CB.Queue+10h; SpinLock
0x1400046b4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400046bb  nop     dword ptr [rax+rax+00h]
0x1400046c0  mov     byte ptr cs:WPP_MAIN_CB.Queue+18h, al
0x1400046c6  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+20h
0x1400046cd  cmp     rax, rbx
0x1400046d0  jnz     short loc_1400046DF
0x1400046d2  mov     rax, [rbx+18h]
0x1400046d6  mov     qword ptr cs:WPP_MAIN_CB.Queue+20h, rax
0x1400046dd  jmp     short loc_1400046F7
0x1400046df  test    rax, rax
0x1400046e2  jz      short loc_1400046F7
0x1400046e4  lea     rcx, [rax+18h]
0x1400046e8  mov     rax, [rcx]
0x1400046eb  cmp     rax, rbx
0x1400046ee  jnz     short loc_1400046DF
0x1400046f0  mov     rax, [rbx+18h]
0x1400046f4  mov     [rcx], rax
0x1400046f7  mov     dl, byte ptr cs:WPP_MAIN_CB.Queue+18h; NewIrql
0x1400046fd  lea     rcx, WPP_MAIN_CB.Queue+10h; SpinLock
0x140004704  call    cs:__imp_KeReleaseSpinLock
0x14000470b  nop     dword ptr [rax+rax+00h]
0x140004710  add     rsp, 20h
0x140004714  pop     rbx
0x140004715  retn
```
