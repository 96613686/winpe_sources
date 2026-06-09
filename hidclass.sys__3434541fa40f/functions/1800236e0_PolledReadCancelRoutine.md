# PolledReadCancelRoutine

- ea: `0x1800236e0`
- end: `0x18002382d`
- name: `PolledReadCancelRoutine`
- size: `333`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000a15c`
- `0x1800236e0`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1800236f5`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1800236f5`
- `ntoskrnl!IofCompleteRequest` at `0x18002380e`
- `ntoskrnl!IofCompleteRequest` at `0x18002380e`
- `ntoskrnl!KeReleaseSpinLock` at `0x180023763`
- `ntoskrnl!KeReleaseSpinLock` at `0x180023763`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180023721`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180023721`

## pseudocode

```c
void __fastcall PolledReadCancelRoutine(__int64 a1, IRP *a2)
{
  __int64 v2; // rbx
  _QWORD *v4; // r14
  __int64 v5; // rbx
  __int64 v6; // rsi
  KIRQL v7; // al
  _LIST_ENTRY *Flink; // r9
  _LIST_ENTRY *Blink; // r8
  int v10; // edx
  int v11; // r8d

  v2 = *(_QWORD *)(a1 + 64);
  IoReleaseCancelSpinLock(a2->CancelIrql);
  v4 = *(_QWORD **)(v2 + 96);
  v5 = 424LL * *(unsigned int *)(v2 + 44);
  v6 = v4[23];
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + v6 + 232));
  Flink = a2->Tail.Overlay.ListEntry.Flink;
  if ( (void **)Flink->Blink != &a2->Tail.CompletionKey + 6
    || (Blink = a2->Tail.Overlay.ListEntry.Blink, (void **)Blink->Flink != &a2->Tail.CompletionKey + 6) )
  {
    __fastfail(3u);
  }
  Blink->Flink = Flink;
  Flink->Blink = Blink;
  _InterlockedDecrement((volatile signed __int32 *)(v5 + v6 + 16));
  KeReleaseSpinLock((PKSPIN_LOCK)(v5 + v6 + 232), v7);
  a2->IoStatus.Status = -1073741536;
  LOBYTE(v11) = 1;
  LOBYTE(v10) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !LOWORD(WPP_GLOBAL_Control->DeviceType) )
    LOBYTE(v11) = 0;
  if ( (_BYTE)v10 || (_BYTE)v11 )
    WPP_RECORDER_AND_TRACE_SF_qqd(
      WPP_GLOBAL_Control->AttachedDevice,
      v10,
      v11,
      v4[88],
      5,
      5,
      12,
      (__int64)WPP_c51b90a246f13983ca6b2f698eaa9bea_Traceguids,
      v4[4],
      (char)a2,
      32);
  IofCompleteRequest(a2, 0);
}

```

## disassembly

```asm
0x1800236e0  push    rbx
0x1800236e2  push    rbp
0x1800236e3  push    rsi
0x1800236e4  push    rdi
0x1800236e5  push    r14
0x1800236e7  sub     rsp, 60h
0x1800236eb  mov     rbx, [rcx+40h]
0x1800236ef  mov     rdi, rdx
0x1800236f2  mov     cl, [rdx+45h]; Irql
0x1800236f5  call    cs:__imp_IoReleaseCancelSpinLock
0x1800236fc  nop     dword ptr [rax+rax+00h]
0x180023701  mov     r14, [rbx+60h]
0x180023705  mov     eax, [rbx+2Ch]
0x180023708  imul    rbx, rax, 1A8h
0x18002370f  mov     rsi, [r14+0B8h]
0x180023716  lea     rbp, [rbx+rsi]
0x18002371a  lea     rcx, [rbp+0E8h]; SpinLock
0x180023721  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180023728  nop     dword ptr [rax+rax+00h]
0x18002372d  lea     rdx, [rdi+0A8h]
0x180023734  mov     r9, [rdx]
0x180023737  cmp     [r9+8], rdx
0x18002373b  jnz     loc_180023826
0x180023741  mov     r8, [rdx+8]
0x180023745  cmp     [r8], rdx
0x180023748  jnz     loc_180023826
0x18002374e  mov     [r8], r9
0x180023751  lea     rcx, [rbp+0E8h]; SpinLock
0x180023758  mov     [r9+8], r8
0x18002375c  mov     dl, al; NewIrql
0x18002375e  lock dec dword ptr [rbx+rsi+10h]
0x180023763  call    cs:__imp_KeReleaseSpinLock
0x18002376a  nop     dword ptr [rax+rax+00h]
0x18002376f  mov     r10d, 0C0000120h
0x180023775  mov     [rdi+30h], r10d
0x180023779  mov     rcx, cs:WPP_GLOBAL_Control
0x180023780  lea     rax, WPP_GLOBAL_Control
0x180023787  mov     r8b, 1
0x18002378a  cmp     rcx, rax
0x18002378d  jz      short loc_1800237A1
0x18002378f  mov     eax, [rcx+2Ch]
0x180023792  test    al, 10h
0x180023794  jz      short loc_1800237A1
0x180023796  cmp     byte ptr [rcx+29h], 5
0x18002379a  jb      short loc_1800237A1
0x18002379c  mov     dl, r8b
0x18002379f  jmp     short loc_1800237A3
0x1800237a1  xor     dl, dl
0x1800237a3  lea     rax, WPP_RECORDER_INITIALIZED
0x1800237aa  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800237b1  jz      short loc_1800237BA
0x1800237b3  cmp     word ptr [rcx+48h], 0
0x1800237b8  jnz     short loc_1800237BD
0x1800237ba  xor     r8b, r8b
0x1800237bd  test    dl, dl
0x1800237bf  jnz     short loc_1800237C6
0x1800237c1  test    r8b, r8b
0x1800237c4  jz      short loc_180023809
0x1800237c6  mov     rax, [r14+20h]
0x1800237ca  mov     r9, [r14+2C0h]
0x1800237d1  mov     rcx, [rcx+18h]
0x1800237d5  mov     [rsp+88h+var_38], r10d
0x1800237da  mov     [rsp+88h+var_40], rdi
0x1800237df  mov     [rsp+88h+var_48], rax
0x1800237e4  lea     rax, WPP_c51b90a246f13983ca6b2f698eaa9bea_Traceguids
0x1800237eb  mov     [rsp+88h+var_50], rax
0x1800237f0  mov     [rsp+88h+var_58], 0Ch
0x1800237f7  mov     [rsp+88h+var_60], 5
0x1800237ff  mov     [rsp+88h+var_68], 5
0x180023804  call    WPP_RECORDER_AND_TRACE_SF_qqd
0x180023809  xor     edx, edx; PriorityBoost
0x18002380b  mov     rcx, rdi; Irp
0x18002380e  call    cs:__imp_IofCompleteRequest
0x180023815  nop     dword ptr [rax+rax+00h]
0x18002381a  add     rsp, 60h
0x18002381e  pop     r14
0x180023820  pop     rdi
0x180023821  pop     rsi
0x180023822  pop     rbp
0x180023823  pop     rbx
0x180023824  retn
0x180023826  mov     ecx, 3
0x18002382b  int     29h; Win8: RtlFailFast(ecx)
```
