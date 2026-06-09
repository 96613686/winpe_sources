# CKsDevice::PostPnpStartWorker(void *)

- ea: `0x18005b610`
- end: `0x18005b7dd`
- name: `?PostPnpStartWorker@CKsDevice@@SAXPEAX@Z`
- size: `461`
- prototype: `void __fastcall(CKsDevice *this)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callees

- `0x18000b7bc`
- `0x18000c4c8`
- `0x18000c630`
- `0x180019cb0`
- `0x18005b610`
- `0x18005b964`
- `0x18005bd44`
- `0x18005c83c`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18005b71f`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18005b71f`

## pseudocode

```c
void __fastcall CKsDevice::PostPnpStartWorker(CKsDevice *this)
{
  unsigned __int8 v2; // di
  struct _KSDEVICE_HEADER_EX *DeviceHeader; // rbp
  int v4; // esi
  const _KSDEVICE_DESCRIPTOR *Descriptor; // rdx
  const _KSDEVICE_DISPATCH *Dispatch; // rdx
  int v7; // edx
  __int64 v8; // rdx
  __int64 (*PostStart)(void); // rax
  int v10; // [rsp+28h] [rbp-40h]

  v2 = 1;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      48,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
  DeviceHeader = CKsDevice::GetDeviceHeaderEx(this->m_Ext.Public.FunctionalDeviceObject);
  this->AcquireDevice(this);
  v4 = 0;
  Descriptor = this->m_Ext.Public.Descriptor;
  if ( Descriptor )
  {
    Dispatch = Descriptor->Dispatch;
    if ( Dispatch )
    {
      PostStart = (__int64 (*)(void))Dispatch->PostStart;
      if ( PostStart )
        v4 = PostStart();
    }
  }
  this->ReleaseDevice(this);
  if ( v4 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_9;
    v10 = v4;
    LOBYTE(v7) = 4;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      1,
      50,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids,
      v10);
  }
  else
  {
    this->m_Ext.Public.Started = 1;
    CKsDevice::ArmForRemoteWakeup(this, 0);
    this->AcquireDevice(this);
    LOBYTE(v8) = 1;
    KspSetDeviceClassesState(this->m_Ext.Public.FunctionalDeviceObject, v8);
    this->ReleaseDevice(this);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      51,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
LABEL_9:
  if ( this->m_Ext.Public.Started )
    this->m_FailCreates = 0;
  else
    v2 = 0;
  this->m_AllowIo = v2;
  CKsDevice::RedispatchPendingCreates(this);
  IoReleaseRemoveLockEx(&DeviceHeader->RemoveLock, CKsDevice::PostPnpStartWorker, 0x20u);
}

```

## disassembly

```asm
0x18005b610  push    rbx
0x18005b612  push    rbp
0x18005b613  push    rsi
0x18005b614  push    rdi
0x18005b615  push    r12
0x18005b617  push    r14
0x18005b619  push    r15
0x18005b61b  sub     rsp, 30h
0x18005b61f  mov     rbx, rcx
0x18005b622  xor     r14d, r14d
0x18005b625  lea     r15, WPP_RECORDER_INITIALIZED
0x18005b62c  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18005b633  lea     r12, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005b63a  lea     edi, [r14+1]
0x18005b63e  jz      short loc_18005B652
0x18005b640  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b647  cmp     [rcx+48h], r14w
0x18005b64c  jnz     loc_18005B759
0x18005b652  mov     rcx, [rbx+0E0h]; struct _DEVICE_OBJECT *
0x18005b659  call    ?GetDeviceHeaderEx@CKsDevice@@SAPEAU_KSDEVICE_HEADER_EX@@PEAU_DEVICE_OBJECT@@@Z; CKsDevice::GetDeviceHeaderEx(_DEVICE_OBJECT *)
0x18005b65e  mov     rcx, [rbx]
0x18005b661  mov     rbp, rax
0x18005b664  mov     rax, [rcx+28h]
0x18005b668  mov     rcx, rbx
0x18005b66b  call    _guard_dispatch_icall
0x18005b670  lea     rcx, [rbx+0C8h]
0x18005b677  mov     esi, r14d
0x18005b67a  mov     rdx, [rcx]
0x18005b67d  test    rdx, rdx
0x18005b680  jz      short loc_18005B68E
0x18005b682  mov     rdx, [rdx]
0x18005b685  test    rdx, rdx
0x18005b688  jnz     loc_18005B740
0x18005b68e  mov     rcx, [rbx]
0x18005b691  mov     rax, [rcx+30h]
0x18005b695  mov     rcx, rbx
0x18005b698  call    _guard_dispatch_icall
0x18005b69d  test    esi, esi
0x18005b69f  js      loc_18005B777
0x18005b6a5  xor     edx, edx; unsigned __int8
0x18005b6a7  mov     [rbx+0F8h], dil
0x18005b6ae  mov     rcx, rbx; this
0x18005b6b1  call    ?ArmForRemoteWakeup@CKsDevice@@AEAAJE@Z; CKsDevice::ArmForRemoteWakeup(uchar)
0x18005b6b6  mov     rax, [rbx]
0x18005b6b9  mov     rcx, rbx
0x18005b6bc  mov     rax, [rax+28h]
0x18005b6c0  call    _guard_dispatch_icall
0x18005b6c5  mov     rcx, [rbx+0E0h]
0x18005b6cc  mov     dl, dil
0x18005b6cf  call    KspSetDeviceClassesState
0x18005b6d4  mov     rax, [rbx]
0x18005b6d7  mov     rcx, rbx
0x18005b6da  mov     rax, [rax+30h]
0x18005b6de  call    _guard_dispatch_icall
0x18005b6e3  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18005b6ea  jnz     loc_18005B7AD
0x18005b6f0  cmp     [rbx+0F8h], r14b
0x18005b6f7  jz      short loc_18005B73B
0x18005b6f9  mov     [rbx+314h], r14b
0x18005b700  mov     rcx, rbx; this
0x18005b703  mov     [rbx+313h], dil
0x18005b70a  call    ?RedispatchPendingCreates@CKsDevice@@QEAAXXZ; CKsDevice::RedispatchPendingCreates(void)
0x18005b70f  mov     r8d, 20h ; ' '; RemlockSize
0x18005b715  lea     rdx, ?PostPnpStartWorker@CKsDevice@@SAXPEAX@Z; Tag
0x18005b71c  mov     rcx, rbp; RemoveLock
0x18005b71f  call    cs:__imp_IoReleaseRemoveLockEx
0x18005b726  nop     dword ptr [rax+rax+00h]
0x18005b72b  add     rsp, 30h
0x18005b72f  pop     r15
0x18005b731  pop     r14
0x18005b733  pop     r12
0x18005b735  pop     rdi
0x18005b736  pop     rsi
0x18005b737  pop     rbp
0x18005b738  pop     rbx
0x18005b739  retn
0x18005b73b  mov     dil, r14b
0x18005b73e  jmp     short loc_18005B700
0x18005b740  mov     rax, [rdx+10h]
0x18005b744  test    rax, rax
0x18005b747  jz      loc_18005B68E
0x18005b74d  call    _guard_dispatch_icall
0x18005b752  mov     esi, eax
0x18005b754  jmp     loc_18005B68E
0x18005b759  mov     rcx, [rcx+40h]
0x18005b75d  mov     r9d, 30h ; '0'
0x18005b763  mov     r8d, edi
0x18005b766  mov     [rsp+68h+var_48], r12
0x18005b76b  mov     dl, 5
0x18005b76d  call    WPP_RECORDER_SF_
0x18005b772  jmp     loc_18005B652
0x18005b777  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18005b77e  jz      loc_18005B6F0
0x18005b784  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b78b  mov     r9d, 32h ; '2'
0x18005b791  mov     [rsp+68h+var_40], esi
0x18005b795  mov     r8d, edi
0x18005b798  mov     dl, 4
0x18005b79a  mov     [rsp+68h+var_48], r12
0x18005b79f  mov     rcx, [rcx+40h]
0x18005b7a3  call    WPP_RECORDER_SF_D
0x18005b7a8  jmp     loc_18005B6E3
0x18005b7ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b7b4  cmp     [rcx+48h], r14w
0x18005b7b9  jz      loc_18005B6F0
0x18005b7bf  mov     rcx, [rcx+40h]
0x18005b7c3  mov     r9d, 33h ; '3'
0x18005b7c9  mov     r8d, edi
0x18005b7cc  mov     [rsp+68h+var_48], r12
0x18005b7d1  mov     dl, 5
0x18005b7d3  call    WPP_RECORDER_SF_
0x18005b7d8  jmp     loc_18005B6F0
```
