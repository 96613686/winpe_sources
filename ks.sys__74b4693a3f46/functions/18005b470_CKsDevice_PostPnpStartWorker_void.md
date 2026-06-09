# CKsDevice::PostPnpStartWorker(void *)

- ea: `0x18005b470`
- end: `0x18005b63d`
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
- `0x180019c60`
- `0x18005b470`
- `0x18005b7c4`
- `0x18005bba4`
- `0x18005c69c`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18005b57f`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18005b57f`

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
0x18005b470  push    rbx
0x18005b472  push    rbp
0x18005b473  push    rsi
0x18005b474  push    rdi
0x18005b475  push    r12
0x18005b477  push    r14
0x18005b479  push    r15
0x18005b47b  sub     rsp, 30h
0x18005b47f  mov     rbx, rcx
0x18005b482  xor     r14d, r14d
0x18005b485  lea     r15, WPP_RECORDER_INITIALIZED
0x18005b48c  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18005b493  lea     r12, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005b49a  lea     edi, [r14+1]
0x18005b49e  jz      short loc_18005B4B2
0x18005b4a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b4a7  cmp     [rcx+48h], r14w
0x18005b4ac  jnz     loc_18005B5B9
0x18005b4b2  mov     rcx, [rbx+0E0h]; struct _DEVICE_OBJECT *
0x18005b4b9  call    ?GetDeviceHeaderEx@CKsDevice@@SAPEAU_KSDEVICE_HEADER_EX@@PEAU_DEVICE_OBJECT@@@Z; CKsDevice::GetDeviceHeaderEx(_DEVICE_OBJECT *)
0x18005b4be  mov     rcx, [rbx]
0x18005b4c1  mov     rbp, rax
0x18005b4c4  mov     rax, [rcx+28h]
0x18005b4c8  mov     rcx, rbx
0x18005b4cb  call    _guard_dispatch_icall
0x18005b4d0  lea     rcx, [rbx+0C8h]
0x18005b4d7  mov     esi, r14d
0x18005b4da  mov     rdx, [rcx]
0x18005b4dd  test    rdx, rdx
0x18005b4e0  jz      short loc_18005B4EE
0x18005b4e2  mov     rdx, [rdx]
0x18005b4e5  test    rdx, rdx
0x18005b4e8  jnz     loc_18005B5A0
0x18005b4ee  mov     rcx, [rbx]
0x18005b4f1  mov     rax, [rcx+30h]
0x18005b4f5  mov     rcx, rbx
0x18005b4f8  call    _guard_dispatch_icall
0x18005b4fd  test    esi, esi
0x18005b4ff  js      loc_18005B5D7
0x18005b505  xor     edx, edx; unsigned __int8
0x18005b507  mov     [rbx+0F8h], dil
0x18005b50e  mov     rcx, rbx; this
0x18005b511  call    ?ArmForRemoteWakeup@CKsDevice@@AEAAJE@Z; CKsDevice::ArmForRemoteWakeup(uchar)
0x18005b516  mov     rax, [rbx]
0x18005b519  mov     rcx, rbx
0x18005b51c  mov     rax, [rax+28h]
0x18005b520  call    _guard_dispatch_icall
0x18005b525  mov     rcx, [rbx+0E0h]
0x18005b52c  mov     dl, dil
0x18005b52f  call    KspSetDeviceClassesState
0x18005b534  mov     rax, [rbx]
0x18005b537  mov     rcx, rbx
0x18005b53a  mov     rax, [rax+30h]
0x18005b53e  call    _guard_dispatch_icall
0x18005b543  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18005b54a  jnz     loc_18005B60D
0x18005b550  cmp     [rbx+0F8h], r14b
0x18005b557  jz      short loc_18005B59B
0x18005b559  mov     [rbx+314h], r14b
0x18005b560  mov     rcx, rbx; this
0x18005b563  mov     [rbx+313h], dil
0x18005b56a  call    ?RedispatchPendingCreates@CKsDevice@@QEAAXXZ; CKsDevice::RedispatchPendingCreates(void)
0x18005b56f  mov     r8d, 20h ; ' '; RemlockSize
0x18005b575  lea     rdx, ?PostPnpStartWorker@CKsDevice@@SAXPEAX@Z; Tag
0x18005b57c  mov     rcx, rbp; RemoveLock
0x18005b57f  call    cs:__imp_IoReleaseRemoveLockEx
0x18005b586  nop     dword ptr [rax+rax+00h]
0x18005b58b  add     rsp, 30h
0x18005b58f  pop     r15
0x18005b591  pop     r14
0x18005b593  pop     r12
0x18005b595  pop     rdi
0x18005b596  pop     rsi
0x18005b597  pop     rbp
0x18005b598  pop     rbx
0x18005b599  retn
0x18005b59b  mov     dil, r14b
0x18005b59e  jmp     short loc_18005B560
0x18005b5a0  mov     rax, [rdx+10h]
0x18005b5a4  test    rax, rax
0x18005b5a7  jz      loc_18005B4EE
0x18005b5ad  call    _guard_dispatch_icall
0x18005b5b2  mov     esi, eax
0x18005b5b4  jmp     loc_18005B4EE
0x18005b5b9  mov     rcx, [rcx+40h]
0x18005b5bd  mov     r9d, 30h ; '0'
0x18005b5c3  mov     r8d, edi
0x18005b5c6  mov     [rsp+68h+var_48], r12
0x18005b5cb  mov     dl, 5
0x18005b5cd  call    WPP_RECORDER_SF_
0x18005b5d2  jmp     loc_18005B4B2
0x18005b5d7  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18005b5de  jz      loc_18005B550
0x18005b5e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b5eb  mov     r9d, 32h ; '2'
0x18005b5f1  mov     [rsp+68h+var_40], esi
0x18005b5f5  mov     r8d, edi
0x18005b5f8  mov     dl, 4
0x18005b5fa  mov     [rsp+68h+var_48], r12
0x18005b5ff  mov     rcx, [rcx+40h]
0x18005b603  call    WPP_RECORDER_SF_D
0x18005b608  jmp     loc_18005B543
0x18005b60d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b614  cmp     [rcx+48h], r14w
0x18005b619  jz      loc_18005B550
0x18005b61f  mov     rcx, [rcx+40h]
0x18005b623  mov     r9d, 33h ; '3'
0x18005b629  mov     r8d, edi
0x18005b62c  mov     [rsp+68h+var_48], r12
0x18005b631  mov     dl, 5
0x18005b633  call    WPP_RECORDER_SF_
0x18005b638  jmp     loc_18005B550
```
