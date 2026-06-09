# RfcommRemoveDevice

- ea: `0x140002ec8`
- end: `0x14000306e`
- name: `RfcommRemoveDevice`
- size: `422`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400011ac`

## callees

- `0x140001d24`
- `0x140002ec8`
- `0x1400038fc`
- `0x140004f5c`
- `0x14000e29c`
- `0x140015904`
- `0x14001fc30`
- `0x14001fc70`
- `0x14001fd40`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002f6a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002f6a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002f88`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002f88`
- `ntoskrnl!IofCallDriver` at `0x140002fa6`
- `ntoskrnl!IofCallDriver` at `0x140002fa6`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x140002fff`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x140002fff`

## pseudocode

```c
__int64 __fastcall RfcommRemoveDevice(__int64 a1, IRP *a2)
{
  unsigned int v4; // ebp
  int v5; // r8d
  int v6; // edx
  int v7; // r8d
  _QWORD v9[18]; // [rsp+40h] [rbp-B8h] BYREF

  memset(v9, 0, 0x88u);
  if ( *(_QWORD *)(a1 + 304) )
  {
    (*(void (__fastcall **)(_QWORD *, __int64))(a1 + 328))(v9, 257);
    v9[15] = *(_QWORD *)(a1 + 304);
    v9[14] = 0;
    LOWORD(v9[16]) = 3;
    BrbpCallDriverSync(a1, (unsigned __int64)v9);
    *(_QWORD *)(a1 + 304) = 0;
  }
  RfcommShutdown(a1);
  *(_BYTE *)(a1 + 32) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 24));
  RfcommStopTimerLocked(a1);
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 24), *(_BYTE *)(a1 + 32));
  ++a2->CurrentLocation;
  ++a2->Tail.Overlay.CurrentStackLocation;
  v4 = IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 88), a2);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qqd(WPP_GLOBAL_Control->DeviceExtension, a1 + 40, v5, 100);
  IoReleaseRemoveLockAndWaitEx((PIO_REMOVE_LOCK)(a1 + 40), a2, 0x20u);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qqd(WPP_GLOBAL_Control->DeviceExtension, v6, v7, 101);
  RfcommDeleteDevice((__int64 *)a1);
  return v4;
}

```

## disassembly

```asm
0x140002ec8  mov     [rsp+arg_10], rbx
0x140002ecd  mov     [rsp+arg_18], rbp
0x140002ed2  push    rsi
0x140002ed3  push    rdi
0x140002ed4  push    r14
0x140002ed6  sub     rsp, 0E0h
0x140002edd  mov     rax, cs:__security_cookie
0x140002ee4  xor     rax, rsp
0x140002ee7  mov     [rsp+0F8h+var_28], rax
0x140002eef  mov     rsi, rdx
0x140002ef2  mov     rdi, rcx
0x140002ef5  xor     edx, edx; Val
0x140002ef7  lea     rcx, [rsp+0F8h+var_B8]; void *
0x140002efc  mov     r8d, 88h; Size
0x140002f02  call    memset
0x140002f07  xor     ebx, ebx
0x140002f09  cmp     [rdi+130h], rbx
0x140002f10  jz      short loc_140002F5E
0x140002f12  mov     rax, [rdi+148h]
0x140002f19  lea     rcx, [rsp+0F8h+var_B8]
0x140002f1e  mov     edx, 101h
0x140002f23  call    _guard_dispatch_icall
0x140002f28  mov     rax, [rdi+130h]
0x140002f2f  lea     rdx, [rsp+0F8h+var_B8]
0x140002f34  mov     [rsp+0F8h+var_40], rax
0x140002f3c  mov     rcx, rdi
0x140002f3f  lea     eax, [rbx+3]
0x140002f42  mov     [rsp+0F8h+var_48], rbx
0x140002f4a  mov     [rsp+0F8h+var_38], ax
0x140002f52  call    BrbpCallDriverSync
0x140002f57  mov     [rdi+130h], rbx
0x140002f5e  mov     rcx, rdi
0x140002f61  call    RfcommShutdown
0x140002f66  lea     rcx, [rdi+18h]; SpinLock
0x140002f6a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002f71  nop     dword ptr [rax+rax+00h]
0x140002f76  mov     rcx, rdi
0x140002f79  mov     [rdi+20h], al
0x140002f7c  call    RfcommStopTimerLocked
0x140002f81  mov     dl, [rdi+20h]; NewIrql
0x140002f84  lea     rcx, [rdi+18h]; SpinLock
0x140002f88  call    cs:__imp_KeReleaseSpinLock
0x140002f8f  nop     dword ptr [rax+rax+00h]
0x140002f94  inc     byte ptr [rsi+43h]
0x140002f97  mov     rdx, rsi; Irp
0x140002f9a  add     qword ptr [rsi+0B8h], 48h ; 'H'
0x140002fa2  mov     rcx, [rdi+58h]; DeviceObject
0x140002fa6  call    cs:__imp_IofCallDriver
0x140002fad  nop     dword ptr [rax+rax+00h]
0x140002fb2  mov     ebp, eax
0x140002fb4  lea     r14, WPP_RECORDER_INITIALIZED
0x140002fbb  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140002fc2  jz      short loc_140002FEF
0x140002fc4  mov     ecx, [rdi+2Ch]
0x140002fc7  lea     rdx, [rdi+28h]
0x140002fcb  mov     [rsp+0F8h+var_C0], ecx
0x140002fcf  mov     r9d, 64h ; 'd'
0x140002fd5  mov     rcx, cs:WPP_GLOBAL_Control
0x140002fdc  mov     [rsp+0F8h+var_C8], rsi
0x140002fe1  mov     [rsp+0F8h+var_D0], rdx
0x140002fe6  mov     rcx, [rcx+40h]
0x140002fea  call    WPP_RECORDER_SF_qqd
0x140002fef  lea     rbx, [rdi+28h]
0x140002ff3  mov     r8d, 20h ; ' '; RemlockSize
0x140002ff9  mov     rcx, rbx; RemoveLock
0x140002ffc  mov     rdx, rsi; Tag
0x140002fff  call    cs:__imp_IoReleaseRemoveLockAndWaitEx
0x140003006  nop     dword ptr [rax+rax+00h]
0x14000300b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140003012  jz      short loc_14000303B
0x140003014  mov     rcx, cs:WPP_GLOBAL_Control
0x14000301b  mov     r9d, 65h ; 'e'
0x140003021  mov     eax, [rdi+2Ch]
0x140003024  mov     [rsp+0F8h+var_C0], eax
0x140003028  mov     [rsp+0F8h+var_C8], rsi
0x14000302d  mov     rcx, [rcx+40h]
0x140003031  mov     [rsp+0F8h+var_D0], rbx
0x140003036  call    WPP_RECORDER_SF_qqd
0x14000303b  mov     rcx, rdi
0x14000303e  call    RfcommDeleteDevice
0x140003043  mov     eax, ebp
0x140003045  mov     rcx, [rsp+0F8h+var_28]
0x14000304d  xor     rcx, rsp; StackCookie
0x140003050  call    __security_check_cookie
0x140003055  lea     r11, [rsp+0F8h+var_18]
0x14000305d  mov     rbx, [r11+30h]
0x140003061  mov     rbp, [r11+38h]
0x140003065  mov     rsp, r11
0x140003068  pop     r14
0x14000306a  pop     rdi
0x14000306b  pop     rsi
0x14000306c  retn
```
