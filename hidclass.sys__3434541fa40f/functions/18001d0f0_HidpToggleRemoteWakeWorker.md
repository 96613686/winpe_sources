# HidpToggleRemoteWakeWorker

- ea: `0x18001d0f0`
- end: `0x18001d278`
- name: `HidpToggleRemoteWakeWorker`
- size: `392`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001cfc4`

## callees

- `0x18001d0f0`
- `0x180038090`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x18001d1e1`
- `ntoskrnl!ZwSetValueKey` at `0x18001d1e1`
- `ntoskrnl!ZwClose` at `0x18001d1f5`
- `ntoskrnl!ZwClose` at `0x18001d1f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001d252`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001d252`
- `ntoskrnl!IoFreeWorkItem` at `0x18001d241`
- `ntoskrnl!IoFreeWorkItem` at `0x18001d241`
- `ntoskrnl!KeReleaseSpinLock` at `0x18001d14c`
- `ntoskrnl!KeReleaseSpinLock` at `0x18001d14c`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x18001d194`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x18001d194`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001d1b0`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001d1b0`
- `ntoskrnl!IoCancelIrp` at `0x18001d216`
- `ntoskrnl!IoCancelIrp` at `0x18001d216`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18001d11e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18001d11e`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18001d231`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18001d231`

## pseudocode

```c
void __fastcall HidpToggleRemoteWakeWorker(PDEVICE_OBJECT DeviceObject, PVOID Context)
{
  __int64 v2; // rbx
  IRP *v3; // rdi
  char v4; // r15
  bool v6; // r14
  KIRQL v7; // al
  char v8; // cl
  char v9; // bp
  struct _DEVICE_OBJECT *v10; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF
  BOOL Data; // [rsp+78h] [rbp+10h] BYREF
  void *DeviceRegKey; // [rsp+80h] [rbp+18h] BYREF

  v2 = *((_QWORD *)Context + 1);
  v3 = 0;
  v4 = *((_BYTE *)Context + 24);
  v6 = v4 != 0;
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 88));
  v8 = *(_BYTE *)(v2 + 84);
  if ( (v4 != 0) == v8 )
  {
    v9 = 0;
  }
  else
  {
    v9 = 1;
    if ( v8 )
      v3 = (IRP *)_InterlockedExchange64((volatile __int64 *)(v2 + 96), 0);
    *(_BYTE *)(v2 + 84) = v6;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 88), v7);
  if ( v9 )
  {
    v10 = *(struct _DEVICE_OBJECT **)(v2 + 48);
    Data = v6;
    DeviceRegKey = 0;
    DestinationString = 0;
    if ( IoOpenDeviceRegistryKey(v10, 1u, 0x1F0000u, &DeviceRegKey) >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"RemoteWakeEnabled");
      ZwSetValueKey(DeviceRegKey, &DestinationString, 0, 4u, &Data, 4u);
      ZwClose(DeviceRegKey);
    }
    if ( v4 )
      HidpCreateRemoteWakeIrp((PVOID)v2);
  }
  if ( v3 )
    IoCancelIrp(v3);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v2 + 16), (PVOID)0x54575752, 0x20u);
  IoFreeWorkItem(*((PIO_WORKITEM *)Context + 2));
  ExFreePoolWithTag(Context, 0);
}

```

## disassembly

```asm
0x18001d0f0  mov     [rsp+arg_0], rbx
0x18001d0f5  mov     [rsp+arg_18], rbp
0x18001d0fa  push    rsi
0x18001d0fb  push    rdi
0x18001d0fc  push    r12
0x18001d0fe  push    r14
0x18001d100  push    r15
0x18001d102  sub     rsp, 40h
0x18001d106  mov     rbx, [rdx+8]
0x18001d10a  xor     edi, edi
0x18001d10c  mov     r15b, [rdx+18h]
0x18001d110  mov     rsi, rdx
0x18001d113  test    r15b, r15b
0x18001d116  lea     rcx, [rbx+58h]; SpinLock
0x18001d11a  setnz   r14b
0x18001d11e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18001d125  nop     dword ptr [rax+rax+00h]
0x18001d12a  mov     cl, [rbx+54h]
0x18001d12d  cmp     r14b, cl
0x18001d130  jz      short loc_18001D143
0x18001d132  mov     bpl, 1
0x18001d135  test    cl, cl
0x18001d137  jz      short loc_18001D13D
0x18001d139  xchg    rdi, [rbx+60h]
0x18001d13d  mov     [rbx+54h], r14b
0x18001d141  jmp     short loc_18001D146
0x18001d143  xor     bpl, bpl
0x18001d146  mov     dl, al; NewIrql
0x18001d148  lea     rcx, [rbx+58h]; SpinLock
0x18001d14c  call    cs:__imp_KeReleaseSpinLock
0x18001d153  nop     dword ptr [rax+rax+00h]
0x18001d158  test    bpl, bpl
0x18001d15b  jz      loc_18001D20E
0x18001d161  mov     rcx, [rbx+30h]; DeviceObject
0x18001d165  lea     r9, [rsp+68h+DeviceRegKey]; DeviceRegKey
0x18001d16d  xorps   xmm0, xmm0
0x18001d170  movzx   eax, r14b
0x18001d174  mov     edx, 1; DevInstKeyType
0x18001d179  mov     [rsp+68h+arg_8], eax
0x18001d17d  mov     r8d, 1F0000h; DesiredAccess
0x18001d183  mov     [rsp+68h+DeviceRegKey], 0
0x18001d18f  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x18001d194  call    cs:__imp_IoOpenDeviceRegistryKey
0x18001d19b  nop     dword ptr [rax+rax+00h]
0x18001d1a0  test    eax, eax
0x18001d1a2  js      short loc_18001D201
0x18001d1a4  lea     rdx, aRemotewakeenab; "RemoteWakeEnabled"
0x18001d1ab  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x18001d1b0  call    cs:__imp_RtlInitUnicodeString
0x18001d1b7  nop     dword ptr [rax+rax+00h]
0x18001d1bc  mov     rcx, [rsp+68h+DeviceRegKey]; KeyHandle
0x18001d1c4  lea     rax, [rsp+68h+arg_8]
0x18001d1c9  mov     r9d, 4; Type
0x18001d1cf  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x18001d1d4  mov     [rsp+68h+DataSize], r9d; DataSize
0x18001d1d9  xor     r8d, r8d; TitleIndex
0x18001d1dc  mov     [rsp+68h+Data], rax; Data
0x18001d1e1  call    cs:__imp_ZwSetValueKey
0x18001d1e8  nop     dword ptr [rax+rax+00h]
0x18001d1ed  mov     rcx, [rsp+68h+DeviceRegKey]; Handle
0x18001d1f5  call    cs:__imp_ZwClose
0x18001d1fc  nop     dword ptr [rax+rax+00h]
0x18001d201  test    r15b, r15b
0x18001d204  jz      short loc_18001D20E
0x18001d206  mov     rcx, rbx; Context
0x18001d209  call    HidpCreateRemoteWakeIrp
0x18001d20e  test    rdi, rdi
0x18001d211  jz      short loc_18001D222
0x18001d213  mov     rcx, rdi; Irp
0x18001d216  call    cs:__imp_IoCancelIrp
0x18001d21d  nop     dword ptr [rax+rax+00h]
0x18001d222  lea     rcx, [rbx+10h]; RemoveLock
0x18001d226  mov     edx, 54575752h; Tag
0x18001d22b  mov     r8d, 20h ; ' '; RemlockSize
0x18001d231  call    cs:__imp_IoReleaseRemoveLockEx
0x18001d238  nop     dword ptr [rax+rax+00h]
0x18001d23d  mov     rcx, [rsi+10h]; IoWorkItem
0x18001d241  call    cs:__imp_IoFreeWorkItem
0x18001d248  nop     dword ptr [rax+rax+00h]
0x18001d24d  xor     edx, edx; Tag
0x18001d24f  mov     rcx, rsi; P
0x18001d252  call    cs:__imp_ExFreePoolWithTag
0x18001d259  nop     dword ptr [rax+rax+00h]
0x18001d25e  lea     r11, [rsp+68h+var_28]
0x18001d263  mov     rbx, [r11+30h]
0x18001d267  mov     rbp, [r11+48h]
0x18001d26b  mov     rsp, r11
0x18001d26e  pop     r15
0x18001d270  pop     r14
0x18001d272  pop     r12
0x18001d274  pop     rdi
0x18001d275  pop     rsi
0x18001d276  retn
```
