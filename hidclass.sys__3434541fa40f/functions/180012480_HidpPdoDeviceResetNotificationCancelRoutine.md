# HidpPdoDeviceResetNotificationCancelRoutine

- ea: `0x180012480`
- end: `0x1800125bb`
- name: `HidpPdoDeviceResetNotificationCancelRoutine`
- size: `315`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180012480`
- `0x1800127d0`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x180012492`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x180012492`
- `ntoskrnl!IofCompleteRequest` at `0x18001259e`
- `ntoskrnl!IofCompleteRequest` at `0x18001259e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800124e9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800124e9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1800124b0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1800124b0`

## pseudocode

```c
void __fastcall HidpPdoDeviceResetNotificationCancelRoutine(__int64 a1, IRP *a2)
{
  __int64 v4; // rsi
  __int64 v5; // rbp
  KIRQL v6; // al
  _LIST_ENTRY *Flink; // r9
  _LIST_ENTRY *Blink; // rdx
  int v9; // edx
  int v10; // r8d

  IoReleaseCancelSpinLock(a2->CancelIrql);
  v4 = *(_QWORD *)(a1 + 64);
  v5 = *(_QWORD *)(v4 + 96);
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 1928));
  Flink = a2->Tail.Overlay.ListEntry.Flink;
  if ( (void **)Flink->Blink != &a2->Tail.CompletionKey + 6
    || (Blink = a2->Tail.Overlay.ListEntry.Blink, (void **)Blink->Flink != &a2->Tail.CompletionKey + 6) )
  {
    __fastfail(3u);
  }
  Blink->Flink = Flink;
  Flink->Blink = Blink;
  KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 1928), v6);
  a2->IoStatus.Status = -1073741536;
  LOBYTE(v9) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_qdqqd(
      WPP_GLOBAL_Control->AttachedDevice,
      v9,
      v10,
      *(_QWORD *)(v5 + 704),
      4,
      10,
      13,
      (__int64)WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids,
      *(_QWORD *)(*(_QWORD *)(v4 + 96) + 32LL),
      *(_DWORD *)(v4 + 40),
      *(_QWORD *)(v4 + 80),
      (char)a2,
      -1073741536);
  }
  IofCompleteRequest(a2, 0);
}

```

## disassembly

```asm
0x180012480  push    rbx
0x180012482  push    rbp
0x180012483  push    rsi
0x180012484  push    rdi
0x180012485  sub     rsp, 78h
0x180012489  mov     rbx, rcx
0x18001248c  mov     rdi, rdx
0x18001248f  mov     cl, [rdx+45h]; Irql
0x180012492  call    cs:__imp_IoReleaseCancelSpinLock
0x180012499  nop     dword ptr [rax+rax+00h]
0x18001249e  mov     rsi, [rbx+40h]
0x1800124a2  mov     rbp, [rsi+60h]
0x1800124a6  lea     rbx, [rbp+788h]
0x1800124ad  mov     rcx, rbx; SpinLock
0x1800124b0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1800124b7  nop     dword ptr [rax+rax+00h]
0x1800124bc  lea     r8, [rdi+0A8h]
0x1800124c3  mov     r9, [r8]
0x1800124c6  cmp     [r9+8], r8
0x1800124ca  jnz     loc_1800125B4
0x1800124d0  mov     rdx, [r8+8]
0x1800124d4  cmp     [rdx], r8
0x1800124d7  jnz     loc_1800125B4
0x1800124dd  mov     [rdx], r9
0x1800124e0  mov     rcx, rbx; SpinLock
0x1800124e3  mov     [r9+8], rdx
0x1800124e7  mov     dl, al; NewIrql
0x1800124e9  call    cs:__imp_KeReleaseSpinLock
0x1800124f0  nop     dword ptr [rax+rax+00h]
0x1800124f5  mov     r11d, 0C0000120h
0x1800124fb  mov     [rdi+30h], r11d
0x1800124ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180012506  lea     rax, WPP_GLOBAL_Control
0x18001250d  cmp     rcx, rax
0x180012510  jz      short loc_180012525
0x180012512  test    dword ptr [rcx+2Ch], 200h
0x180012519  jz      short loc_180012525
0x18001251b  cmp     byte ptr [rcx+29h], 4
0x18001251f  jb      short loc_180012525
0x180012521  mov     dl, 1
0x180012523  jmp     short loc_180012527
0x180012525  xor     dl, dl
0x180012527  lea     rax, WPP_RECORDER_INITIALIZED
0x18001252e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180012535  setnz   r8b
0x180012539  test    dl, dl
0x18001253b  jnz     short loc_180012542
0x18001253d  test    r8b, r8b
0x180012540  jz      short loc_180012599
0x180012542  mov     rax, [rsi+50h]
0x180012546  mov     r10, [rsi+60h]
0x18001254a  mov     r9, [rbp+2C0h]
0x180012551  mov     rcx, [rcx+18h]
0x180012555  mov     [rsp+98h+var_38], r11d
0x18001255a  mov     [rsp+98h+var_40], rdi
0x18001255f  mov     [rsp+98h+var_48], rax
0x180012564  mov     eax, [rsi+28h]
0x180012567  mov     [rsp+98h+var_50], eax
0x18001256b  mov     rax, [r10+20h]
0x18001256f  mov     [rsp+98h+var_58], rax
0x180012574  lea     rax, WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids
0x18001257b  mov     [rsp+98h+var_60], rax
0x180012580  mov     [rsp+98h+var_68], 0Dh
0x180012587  mov     [rsp+98h+var_70], 0Ah
0x18001258f  mov     [rsp+98h+var_78], 4
0x180012594  call    WPP_RECORDER_AND_TRACE_SF_qdqqd
0x180012599  xor     edx, edx; PriorityBoost
0x18001259b  mov     rcx, rdi; Irp
0x18001259e  call    cs:__imp_IofCompleteRequest
0x1800125a5  nop     dword ptr [rax+rax+00h]
0x1800125aa  add     rsp, 78h
0x1800125ae  pop     rdi
0x1800125af  pop     rsi
0x1800125b0  pop     rbp
0x1800125b1  pop     rbx
0x1800125b2  retn
0x1800125b4  mov     ecx, 3
0x1800125b9  int     29h; Win8: RtlFailFast(ecx)
```
