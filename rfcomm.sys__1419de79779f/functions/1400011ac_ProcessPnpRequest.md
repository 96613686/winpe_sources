# ProcessPnpRequest

- ea: `0x1400011ac`
- end: `0x140001457`
- name: `ProcessPnpRequest`
- size: `683`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000256c`

## callees

- `0x1400011ac`
- `0x140002ec8`
- `0x1400035cc`
- `0x140003cb4`
- `0x140004364`
- `0x1400051b4`
- `0x14000b318`
- `0x140015904`
- `0x14001bfa8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400012ef`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400013ce`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400012ef`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400013ce`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000131c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400013fb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000131c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400013fb`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14000129b`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14000129b`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000139c`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000139c`
- `ntoskrnl!IofCallDriver` at `0x140001381`
- `ntoskrnl!IofCallDriver` at `0x140001381`

## pseudocode

```c
__int64 __fastcall ProcessPnpRequest(__int64 a1, IRP *a2, int a3, int a4)
{
  __int64 v4; // rdi
  $1F5ECA8CE272DAA79E13C725D2A1A8B9 *v5; // r15
  _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  $1F5ECA8CE272DAA79E13C725D2A1A8B9 *v8; // r14
  NTSTATUS v9; // eax
  int v10; // edx
  __int64 v11; // rbx
  int started; // ebp
  _IO_STACK_LOCATION *v13; // rax
  __int64 v14; // rbx
  void *DeviceExtension; // rbx
  const char *v16; // rax
  int v17; // edx

  v4 = *(_QWORD *)(a1 + 64);
  v5 = &a2->Tail.Overlay.64;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v8 = &a2->Tail.Overlay.64;
  }
  else
  {
    WPP_RECORDER_SF_cq(WPP_GLOBAL_Control->DeviceExtension, (_DWORD)a2, a3, a4);
    v8 = &a2->Tail.Overlay.64;
  }
  if ( CurrentStackLocation->MinorFunction )
  {
    if ( CurrentStackLocation->MinorFunction == 1 )
    {
      TdiShutdown(*(_QWORD *)(*(_QWORD *)(v4 + 96) + 16LL));
      RfcommShutdown(v4);
      *(_DWORD *)(v4 + 112) = 5;
    }
    else
    {
      switch ( CurrentStackLocation->MinorFunction )
      {
        case 2u:
          started = RfcommRemoveDevice(v4, a2);
          *(_DWORD *)(v4 + 112) = 4;
          goto LABEL_27;
        case 3u:
          v11 = *(_QWORD *)(*(_QWORD *)(v4 + 96) + 16LL);
          *(_BYTE *)(v11 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v11 + 48));
          *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v4 + 96) + 16LL) + 128LL) = 0;
          KeReleaseSpinLock(
            (PKSPIN_LOCK)(*(_QWORD *)(*(_QWORD *)(v4 + 96) + 16LL) + 48LL),
            *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v4 + 96) + 16LL) + 56LL));
          *(_DWORD *)(v4 + 112) = 1;
LABEL_24:
          v13 = v8->CurrentStackLocation;
          ++a2->CurrentLocation;
          v5->CurrentStackLocation = v13 + 1;
          started = IofCallDriver(*(PDEVICE_OBJECT *)(v4 + 88), a2);
          IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v4 + 40), a2, 0x20u);
          goto LABEL_27;
        case 4u:
          a2->IoStatus.Status = 0;
          v9 = IoSetDeviceInterfaceState((PUNICODE_STRING)(v4 + 344), 0);
          if ( v9 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_d(
              WPP_GLOBAL_Control->DeviceExtension,
              v10,
              15,
              98,
              (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
              v9);
          *(_DWORD *)(v4 + 112) = 2;
          goto LABEL_24;
      }
      if ( CurrentStackLocation->MinorFunction != 5 )
      {
        if ( CurrentStackLocation->MinorFunction == 6 )
        {
          *(_DWORD *)(v4 + 112) = 1;
        }
        else if ( CurrentStackLocation->MinorFunction == 23 )
        {
          TdiShutdown(*(_QWORD *)(*(_QWORD *)(v4 + 96) + 16LL));
          RfcommShutdown(v4);
          a2->IoStatus.Status = 0;
          *(_DWORD *)(v4 + 112) = 4;
        }
        v8 = v5;
        goto LABEL_24;
      }
      *(_DWORD *)(v4 + 112) = 3;
      v8 = v5;
    }
    a2->IoStatus.Status = 0;
    goto LABEL_24;
  }
  started = RfcommStartDevice(v4, a2);
  *(_DWORD *)(v4 + 112) = 1;
  if ( started >= 0 )
  {
    v14 = *(_QWORD *)(*(_QWORD *)(v4 + 96) + 16LL);
    *(_BYTE *)(v14 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v14 + 48));
    *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v4 + 96) + 16LL) + 128LL) = 0;
    KeReleaseSpinLock(
      (PKSPIN_LOCK)(*(_QWORD *)(*(_QWORD *)(v4 + 96) + 16LL) + 48LL),
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v4 + 96) + 16LL) + 56LL));
  }
LABEL_27:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
    v16 = NtStatusTxt(started);
    WPP_RECORDER_SF_s(
      (_DWORD)DeviceExtension,
      v17,
      3,
      99,
      (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
      (__int64)v16);
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1400011ac  push    rbx
0x1400011ae  push    rbp
0x1400011af  push    rsi
0x1400011b0  push    rdi
0x1400011b1  push    r13
0x1400011b3  push    r14
0x1400011b5  push    r15
0x1400011b7  sub     rsp, 40h
0x1400011bb  mov     rdi, [rcx+40h]
0x1400011bf  lea     r15, [rdx+0B8h]
0x1400011c6  mov     rsi, rdx
0x1400011c9  mov     rbx, [r15]
0x1400011cc  lea     r13, WPP_RECORDER_INITIALIZED
0x1400011d3  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400011da  jz      short loc_140001201
0x1400011dc  mov     al, [rbx+1]
0x1400011df  mov     [rsp+78h+var_48], rcx
0x1400011e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400011eb  mov     byte ptr [rsp+78h+var_50], al
0x1400011ef  mov     rcx, [rcx+40h]
0x1400011f3  call    WPP_RECORDER_SF_cq
0x1400011f8  lea     r14, [rsi+0B8h]
0x1400011ff  jmp     short loc_140001204
0x140001201  mov     r14, r15
0x140001204  movzx   ecx, byte ptr [rbx+1]
0x140001208  lea     rbx, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x14000120f  test    ecx, ecx
0x140001211  jz      loc_1400013AA
0x140001217  sub     ecx, 1
0x14000121a  jz      loc_14000134A
0x140001220  sub     ecx, 1
0x140001223  jz      loc_140001331
0x140001229  sub     ecx, 1
0x14000122c  jz      loc_1400012E3
0x140001232  sub     ecx, 1
0x140001235  jz      short loc_14000128B
0x140001237  sub     ecx, 1
0x14000123a  jz      short loc_14000127C
0x14000123c  sub     ecx, 1
0x14000123f  jz      short loc_140001273
0x140001241  cmp     ecx, 11h
0x140001244  jz      short loc_14000124E
0x140001246  mov     r14, r15
0x140001249  jmp     loc_14000136D
0x14000124e  mov     rcx, [rdi+60h]
0x140001252  mov     rcx, [rcx+10h]
0x140001256  call    TdiShutdown
0x14000125b  mov     rcx, rdi
0x14000125e  call    RfcommShutdown
0x140001263  mov     dword ptr [rsi+30h], 0
0x14000126a  mov     dword ptr [rdi+70h], 4
0x140001271  jmp     short loc_140001246
0x140001273  mov     dword ptr [rdi+70h], 1
0x14000127a  jmp     short loc_140001246
0x14000127c  mov     dword ptr [rdi+70h], 3
0x140001283  mov     r14, r15
0x140001286  jmp     loc_140001366
0x14000128b  lea     rcx, [rdi+158h]; SymbolicLinkName
0x140001292  mov     dword ptr [rsi+30h], 0
0x140001299  xor     edx, edx; Enable
0x14000129b  call    cs:__imp_IoSetDeviceInterfaceState
0x1400012a2  nop     dword ptr [rax+rax+00h]
0x1400012a7  test    eax, eax
0x1400012a9  jns     short loc_1400012D7
0x1400012ab  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400012b2  jz      short loc_1400012D7
0x1400012b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400012bb  mov     r9d, 62h ; 'b'
0x1400012c1  mov     dword ptr [rsp+78h+var_50], eax
0x1400012c5  mov     [rsp+78h+var_58], rbx
0x1400012ca  mov     rcx, [rcx+40h]
0x1400012ce  lea     r8d, [r9-53h]
0x1400012d2  call    WPP_RECORDER_SF_d
0x1400012d7  mov     dword ptr [rdi+70h], 2
0x1400012de  jmp     loc_14000136D
0x1400012e3  mov     rax, [rdi+60h]
0x1400012e7  mov     rbx, [rax+10h]
0x1400012eb  lea     rcx, [rbx+30h]; SpinLock
0x1400012ef  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400012f6  nop     dword ptr [rax+rax+00h]
0x1400012fb  mov     [rbx+38h], al
0x1400012fe  mov     rax, [rdi+60h]
0x140001302  mov     rcx, [rax+10h]
0x140001306  mov     byte ptr [rcx+80h], 0
0x14000130d  mov     rax, [rdi+60h]
0x140001311  mov     rdx, [rax+10h]
0x140001315  lea     rcx, [rdx+30h]; SpinLock
0x140001319  mov     dl, [rdx+38h]; NewIrql
0x14000131c  call    cs:__imp_KeReleaseSpinLock
0x140001323  nop     dword ptr [rax+rax+00h]
0x140001328  mov     dword ptr [rdi+70h], 1
0x14000132f  jmp     short loc_14000136D
0x140001331  mov     rdx, rsi
0x140001334  mov     rcx, rdi
0x140001337  call    RfcommRemoveDevice
0x14000133c  mov     ebp, eax
0x14000133e  mov     dword ptr [rdi+70h], 4
0x140001345  jmp     loc_140001407
0x14000134a  mov     rcx, [rdi+60h]
0x14000134e  mov     rcx, [rcx+10h]
0x140001352  call    TdiShutdown
0x140001357  mov     rcx, rdi
0x14000135a  call    RfcommShutdown
0x14000135f  mov     dword ptr [rdi+70h], 5
0x140001366  mov     dword ptr [rsi+30h], 0
0x14000136d  mov     rax, [r14]
0x140001370  mov     rdx, rsi; Irp
0x140001373  inc     byte ptr [rsi+43h]
0x140001376  add     rax, 48h ; 'H'
0x14000137a  mov     [r15], rax
0x14000137d  mov     rcx, [rdi+58h]; DeviceObject
0x140001381  call    cs:__imp_IofCallDriver
0x140001388  nop     dword ptr [rax+rax+00h]
0x14000138d  lea     rcx, [rdi+28h]; RemoveLock
0x140001391  mov     r8d, 20h ; ' '; RemlockSize
0x140001397  mov     rdx, rsi; Tag
0x14000139a  mov     ebp, eax
0x14000139c  call    cs:__imp_IoReleaseRemoveLockEx
0x1400013a3  nop     dword ptr [rax+rax+00h]
0x1400013a8  jmp     short loc_140001407
0x1400013aa  mov     rdx, rsi
0x1400013ad  mov     rcx, rdi
0x1400013b0  call    RfcommStartDevice
0x1400013b5  mov     ebp, eax
0x1400013b7  mov     dword ptr [rdi+70h], 1
0x1400013be  test    eax, eax
0x1400013c0  js      short loc_140001407
0x1400013c2  mov     rax, [rdi+60h]
0x1400013c6  mov     rbx, [rax+10h]
0x1400013ca  lea     rcx, [rbx+30h]; SpinLock
0x1400013ce  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400013d5  nop     dword ptr [rax+rax+00h]
0x1400013da  mov     [rbx+38h], al
0x1400013dd  mov     rax, [rdi+60h]
0x1400013e1  mov     rcx, [rax+10h]
0x1400013e5  mov     byte ptr [rcx+80h], 0
0x1400013ec  mov     rax, [rdi+60h]
0x1400013f0  mov     rdx, [rax+10h]
0x1400013f4  lea     rcx, [rdx+30h]; SpinLock
0x1400013f8  mov     dl, [rdx+38h]; NewIrql
0x1400013fb  call    cs:__imp_KeReleaseSpinLock
0x140001402  nop     dword ptr [rax+rax+00h]
0x140001407  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14000140e  jz      short loc_140001445
0x140001410  mov     rax, cs:WPP_GLOBAL_Control
0x140001417  mov     ecx, ebp
0x140001419  mov     rbx, [rax+40h]
0x14000141d  call    NtStatusTxt
0x140001422  mov     [rsp+78h+var_50], rax
0x140001427  mov     r9d, 63h ; 'c'
0x14000142d  lea     rax, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x140001434  mov     rcx, rbx
0x140001437  mov     [rsp+78h+var_58], rax
0x14000143c  lea     r8d, [r9-60h]
0x140001440  call    WPP_RECORDER_SF_s
0x140001445  mov     eax, ebp
0x140001447  add     rsp, 40h
0x14000144b  pop     r15
0x14000144d  pop     r14
0x14000144f  pop     r13
0x140001451  pop     rdi
0x140001452  pop     rsi
0x140001453  pop     rbp
0x140001454  pop     rbx
0x140001455  retn
```
