# lldpRemovePortFromDriver

- ea: `0x140004510`
- end: `0x140004583`
- name: `lldpRemovePortFromDriver`
- size: `115`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140010aec`
- `0x140012640`

## callees

- `0x140004510`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004520`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004520`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004570`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004570`

## pseudocode

```c
void __fastcall lldpRemovePortFromDriver(struct _LIST_ENTRY *a1)
{
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *v3; // rcx

  LOBYTE(WPP_MAIN_CB.DeviceQueue.Type) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.AlignmentRequirement);
  Flink = WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink;
  if ( WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink == a1 )
  {
    WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink = a1[2].Flink;
  }
  else
  {
    while ( Flink )
    {
      v3 = Flink + 2;
      Flink = Flink[2].Flink;
      if ( Flink == a1 )
      {
        v3->Flink = a1[2].Flink;
        break;
      }
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.AlignmentRequirement, WPP_MAIN_CB.DeviceQueue.Type);
}

```

## disassembly

```asm
0x140004510  push    rbx
0x140004512  sub     rsp, 20h
0x140004516  mov     rbx, rcx
0x140004519  lea     rcx, WPP_MAIN_CB.AlignmentRequirement; SpinLock
0x140004520  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004527  nop     dword ptr [rax+rax+00h]
0x14000452c  mov     byte ptr cs:WPP_MAIN_CB.DeviceQueue.Type, al
0x140004532  mov     rax, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink
0x140004539  cmp     rax, rbx
0x14000453c  jnz     short loc_14000454B
0x14000453e  mov     rax, [rbx+20h]
0x140004542  mov     cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink, rax
0x140004549  jmp     short loc_140004563
0x14000454b  test    rax, rax
0x14000454e  jz      short loc_140004563
0x140004550  lea     rcx, [rax+20h]
0x140004554  mov     rax, [rcx]
0x140004557  cmp     rax, rbx
0x14000455a  jnz     short loc_14000454B
0x14000455c  mov     rax, [rbx+20h]
0x140004560  mov     [rcx], rax
0x140004563  mov     dl, byte ptr cs:WPP_MAIN_CB.DeviceQueue.Type; NewIrql
0x140004569  lea     rcx, WPP_MAIN_CB.AlignmentRequirement; SpinLock
0x140004570  call    cs:__imp_KeReleaseSpinLock
0x140004577  nop     dword ptr [rax+rax+00h]
0x14000457c  add     rsp, 20h
0x140004580  pop     rbx
0x140004581  retn
```
