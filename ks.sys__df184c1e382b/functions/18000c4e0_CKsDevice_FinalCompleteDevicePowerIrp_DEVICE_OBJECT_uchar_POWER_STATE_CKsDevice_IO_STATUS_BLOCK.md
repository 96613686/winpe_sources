# CKsDevice::FinalCompleteDevicePowerIrp(_DEVICE_OBJECT *,uchar,_POWER_STATE,CKsDevice *,_IO_STATUS_BLOCK *)

- ea: `0x18000c4e0`
- end: `0x18000c62a`
- name: `?FinalCompleteDevicePowerIrp@CKsDevice@@CAXPEAU_DEVICE_OBJECT@@ET_POWER_STATE@@PEAV1@PEAU_IO_STATUS_BLOCK@@@Z`
- size: `330`
- prototype: `void __fastcall(PDEVICE_OBJECT DeviceObject, UCHAR MinorFunction, POWER_STATE PowerState, _QWORD *Context, PIO_STATUS_BLOCK IoStatus)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b7bc`
- `0x18000c4e0`
- `0x18000c630`

## import_xrefs

- `ntoskrnl!PoStartNextPowerIrp` at `0x18000c54c`
- `ntoskrnl!PoStartNextPowerIrp` at `0x18000c54c`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18000c583`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18000c583`
- `ntoskrnl!IofCompleteRequest` at `0x18000c55d`
- `ntoskrnl!IofCompleteRequest` at `0x18000c55d`

## pseudocode

```c
void __fastcall CKsDevice::FinalCompleteDevicePowerIrp(
        PDEVICE_OBJECT DeviceObject,
        UCHAR MinorFunction,
        POWER_STATE PowerState,
        _QWORD *Context,
        PIO_STATUS_BLOCK IoStatus)
{
  IRP *v6; // rbx
  __int64 v7; // rbp
  int v8; // edx
  int v9; // edx

  v6 = (IRP *)Context[120];
  v7 = *(_QWORD *)(Context[28] + 64LL);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      136,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
      IoStatus->Status);
  if ( v6 )
  {
    v6->IoStatus.Status = IoStatus->Status;
    Context[120] = 0;
    PoStartNextPowerIrp(v6);
    IofCompleteRequest(v6, 0);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v8) = 5;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v8,
          1,
          137,
          (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
      }
    }
  }
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v7 - 32), CKsDevice::FinalCompleteDevicePowerIrp, 0x20u);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v9) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        1,
        138,
        (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
    }
  }
}

```

## disassembly

```asm
0x18000c4e0  push    rbx
0x18000c4e2  push    rbp
0x18000c4e3  push    rsi
0x18000c4e4  push    rdi
0x18000c4e5  push    r12
0x18000c4e7  push    r13
0x18000c4e9  push    r14
0x18000c4eb  sub     rsp, 30h
0x18000c4ef  mov     rax, [r9+0E0h]
0x18000c4f6  mov     rdi, r9
0x18000c4f9  mov     rbx, [r9+3C0h]
0x18000c500  mov     rbp, [rax+40h]
0x18000c504  mov     rsi, [rsp+68h+IoStatus]
0x18000c50c  lea     r13, WPP_RECORDER_INITIALIZED
0x18000c513  xor     r14d, r14d
0x18000c516  lea     r12, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18000c51d  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000c524  jz      short loc_18000C538
0x18000c526  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c52d  cmp     [rcx+48h], r14w
0x18000c532  jnz     loc_18000C603
0x18000c538  test    rbx, rbx
0x18000c53b  jz      short loc_18000C572
0x18000c53d  mov     eax, [rsi]
0x18000c53f  mov     rcx, rbx; Irp
0x18000c542  mov     [rbx+30h], eax
0x18000c545  mov     [rdi+3C0h], r14
0x18000c54c  call    cs:__imp_PoStartNextPowerIrp
0x18000c553  nop     dword ptr [rax+rax+00h]
0x18000c558  xor     edx, edx; PriorityBoost
0x18000c55a  mov     rcx, rbx; Irp
0x18000c55d  call    cs:__imp_IofCompleteRequest
0x18000c564  nop     dword ptr [rax+rax+00h]
0x18000c569  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000c570  jnz     short loc_18000C5D4
0x18000c572  mov     r8d, 20h ; ' '; RemlockSize
0x18000c578  lea     rdx, ?FinalCompleteDevicePowerIrp@CKsDevice@@CAXPEAU_DEVICE_OBJECT@@ET_POWER_STATE@@PEAV1@PEAU_IO_STATUS_BLOCK@@@Z; Tag
0x18000c57f  lea     rcx, [rbp-20h]; RemoveLock
0x18000c583  call    cs:__imp_IoReleaseRemoveLockEx
0x18000c58a  nop     dword ptr [rax+rax+00h]
0x18000c58f  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000c596  jnz     short loc_18000C5A8
0x18000c598  add     rsp, 30h
0x18000c59c  pop     r14
0x18000c59e  pop     r13
0x18000c5a0  pop     r12
0x18000c5a2  pop     rdi
0x18000c5a3  pop     rsi
0x18000c5a4  pop     rbp
0x18000c5a5  pop     rbx
0x18000c5a6  retn
0x18000c5a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c5af  cmp     [rcx+48h], r14w
0x18000c5b4  jz      short loc_18000C598
0x18000c5b6  mov     rcx, [rcx+40h]
0x18000c5ba  mov     r9d, 8Ah
0x18000c5c0  mov     r8d, 1
0x18000c5c6  mov     [rsp+68h+var_48], r12
0x18000c5cb  mov     dl, 5
0x18000c5cd  call    WPP_RECORDER_SF_
0x18000c5d2  jmp     short loc_18000C598
0x18000c5d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c5db  cmp     [rcx+48h], r14w
0x18000c5e0  jz      short loc_18000C572
0x18000c5e2  mov     rcx, [rcx+40h]
0x18000c5e6  mov     r9d, 89h
0x18000c5ec  mov     r8d, 1
0x18000c5f2  mov     [rsp+68h+var_48], r12
0x18000c5f7  mov     dl, 5
0x18000c5f9  call    WPP_RECORDER_SF_
0x18000c5fe  jmp     loc_18000C572
0x18000c603  mov     eax, [rsi]
0x18000c605  mov     r9d, 88h
0x18000c60b  mov     rcx, [rcx+40h]
0x18000c60f  mov     r8d, 1
0x18000c615  mov     [rsp+68h+var_40], eax
0x18000c619  mov     dl, 5
0x18000c61b  mov     [rsp+68h+var_48], r12
0x18000c620  call    WPP_RECORDER_SF_D
0x18000c625  jmp     loc_18000C538
```
