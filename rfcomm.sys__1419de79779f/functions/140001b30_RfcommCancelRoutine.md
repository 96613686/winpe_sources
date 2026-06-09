# RfcommCancelRoutine

- ea: `0x140001b30`
- end: `0x140001c2b`
- name: `RfcommCancelRoutine`
- size: `251`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001b30`
- `0x140004a68`
- `0x14001fc70`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001b99`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001b99`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001bd3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001bd3`
- `ntoskrnl!IofCompleteRequest` at `0x140001c0e`
- `ntoskrnl!IofCompleteRequest` at `0x140001c0e`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140001b89`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140001b89`

## pseudocode

```c
void __fastcall RfcommCancelRoutine(__int64 a1, IRP *a2)
{
  PKSPIN_LOCK *v4; // rdi
  KIRQL v5; // al
  _LIST_ENTRY *p_ListEntry; // rcx
  IRP *Flink; // rdx
  _LIST_ENTRY *Blink; // r8
  void (__fastcall *v9)(__int64, IRP *, __int64); // rax

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      15,
      103,
      (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
      (char)a2);
  v4 = (PKSPIN_LOCK *)a2->Tail.Overlay.DriverContext[3];
  IoReleaseCancelSpinLock(a2->CancelIrql);
  v5 = KeAcquireSpinLockRaiseToDpc(v4[3]);
  p_ListEntry = &a2->Tail.Overlay.ListEntry;
  Flink = (IRP *)a2->Tail.Overlay.ListEntry.Flink;
  if ( Flink != (IRP *)(&a2->Tail.CompletionKey + 6) )
  {
    if ( (_LIST_ENTRY *)Flink->MdlAddress != p_ListEntry
      || (Blink = a2->Tail.Overlay.ListEntry.Blink, Blink->Flink != p_ListEntry) )
    {
      __fastfail(3u);
    }
    Blink->Flink = (_LIST_ENTRY *)Flink;
    Flink->MdlAddress = (_MDL *)Blink;
    --*((_DWORD *)v4 + 8);
  }
  KeReleaseSpinLock(v4[3], v5);
  v9 = (void (__fastcall *)(__int64, IRP *, __int64))v4[6];
  if ( v9 )
  {
    v9(a1, a2, 3221225760LL);
  }
  else
  {
    a2->IoStatus.Status = -1073741536;
    IofCompleteRequest(a2, 0);
  }
}

```

## disassembly

```asm
0x140001b30  mov     r11, rsp
0x140001b33  mov     [r11+8], rbx
0x140001b37  mov     [r11+10h], rsi
0x140001b3b  push    rdi
0x140001b3c  sub     rsp, 30h
0x140001b40  mov     rbx, rdx
0x140001b43  mov     rsi, rcx
0x140001b46  lea     rax, WPP_RECORDER_INITIALIZED
0x140001b4d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140001b54  jz      short loc_140001B7F
0x140001b56  mov     rcx, cs:WPP_GLOBAL_Control
0x140001b5d  lea     rax, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x140001b64  mov     r9d, 67h ; 'g'
0x140001b6a  mov     [r11-10h], rdx
0x140001b6e  mov     [r11-18h], rax
0x140001b72  mov     rcx, [rcx+40h]
0x140001b76  lea     r8d, [r9-58h]
0x140001b7a  call    WPP_RECORDER_SF_q
0x140001b7f  mov     cl, [rbx+45h]; Irql
0x140001b82  mov     rdi, [rbx+90h]
0x140001b89  call    cs:__imp_IoReleaseCancelSpinLock
0x140001b90  nop     dword ptr [rax+rax+00h]
0x140001b95  mov     rcx, [rdi+18h]; SpinLock
0x140001b99  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001ba0  nop     dword ptr [rax+rax+00h]
0x140001ba5  lea     rcx, [rbx+0A8h]
0x140001bac  mov     rdx, [rcx]
0x140001baf  cmp     rdx, rcx
0x140001bb2  jz      short loc_140001BCD
0x140001bb4  cmp     [rdx+8], rcx
0x140001bb8  jnz     short loc_140001BFB
0x140001bba  mov     r8, [rcx+8]
0x140001bbe  cmp     [r8], rcx
0x140001bc1  jnz     short loc_140001BFB
0x140001bc3  mov     [r8], rdx
0x140001bc6  mov     [rdx+8], r8
0x140001bca  dec     dword ptr [rdi+20h]
0x140001bcd  mov     rcx, [rdi+18h]; SpinLock
0x140001bd1  mov     dl, al; NewIrql
0x140001bd3  call    cs:__imp_KeReleaseSpinLock
0x140001bda  nop     dword ptr [rax+rax+00h]
0x140001bdf  mov     rax, [rdi+30h]
0x140001be3  test    rax, rax
0x140001be6  jz      short loc_140001C02
0x140001be8  mov     r8d, 0C0000120h
0x140001bee  mov     rdx, rbx
0x140001bf1  mov     rcx, rsi
0x140001bf4  call    _guard_dispatch_icall
0x140001bf9  jmp     short loc_140001C1A
0x140001bfb  mov     ecx, 3
0x140001c00  int     29h; Win8: RtlFailFast(ecx)
0x140001c02  xor     edx, edx; PriorityBoost
0x140001c04  mov     dword ptr [rbx+30h], 0C0000120h
0x140001c0b  mov     rcx, rbx; Irp
0x140001c0e  call    cs:__imp_IofCompleteRequest
0x140001c15  nop     dword ptr [rax+rax+00h]
0x140001c1a  mov     rbx, [rsp+38h+arg_0]
0x140001c1f  mov     rsi, [rsp+38h+arg_8]
0x140001c24  add     rsp, 30h
0x140001c28  pop     rdi
0x140001c29  retn
```
