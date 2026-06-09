# CKsDevice::RedispatchPendedIrps(uchar)

- ea: `0x18000c1dc`
- end: `0x18000c33c`
- name: `?RedispatchPendedIrps@CKsDevice@@AEAAXE@Z`
- size: `352`
- prototype: `void __fastcall(CKsDevice *this, char)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180048c60`
- `0x18005c570`

## callees

- `0x180006c40`
- `0x18000b7bc`
- `0x18000c1dc`
- `0x1800481d0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000c245`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000c245`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000c298`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000c298`
- `ntoskrnl!IofCompleteRequest` at `0x18000c2fe`
- `ntoskrnl!IofCompleteRequest` at `0x18000c2fe`
- `ntoskrnl!KeSetEvent` at `0x18000c222`
- `ntoskrnl!KeSetEvent` at `0x18000c222`

## pseudocode

```c
void __fastcall CKsDevice::RedispatchPendedIrps(CKsDevice *this, char a2)
{
  PIRP p_m_SxIrp; // rbx
  CKsDevice *p_m_PendedIoRequests; // rdi
  KIRQL v6; // r8
  CKsDevice_vtbl *v7; // rax
  IKsDeviceFunctions_vtbl *v8; // rcx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      156,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
  KeSetEvent(&this->m_BlockPoweredDownEvent, 0, 0);
  p_m_SxIrp = 0;
  p_m_PendedIoRequests = (CKsDevice *)&this->m_PendedIoRequests;
  v6 = KeAcquireSpinLockRaiseToDpc(&this->m_PendedIoRequestsLock);
  while ( 1 )
  {
    p_m_PendedIoRequests = (CKsDevice *)p_m_PendedIoRequests->IKsDevice::IUnknown::__vftable;
    if ( p_m_PendedIoRequests == (CKsDevice *)&this->m_PendedIoRequests )
      break;
    if ( _InterlockedExchange64((volatile __int64 *)&p_m_PendedIoRequests[-1].m_BlockPoweredDownEvent.Header.Lock, 0) )
    {
      v7 = p_m_PendedIoRequests->IKsDevice::IUnknown::__vftable;
      if ( (CKsDevice *)p_m_PendedIoRequests->AddRef != p_m_PendedIoRequests
        || (v8 = p_m_PendedIoRequests->IKsDeviceFunctions::IUnknown::__vftable,
            (CKsDevice *)v8->QueryInterface != p_m_PendedIoRequests) )
      {
        __fastfail(3u);
      }
      v8->QueryInterface = (HRESULT (__fastcall *)(IUnknown *, const _GUID *, void **))v7;
      p_m_SxIrp = (PIRP)&p_m_PendedIoRequests[-1].m_SxIrp;
      v7->AddRef = (unsigned int (__fastcall *)(IUnknown *))v8;
      break;
    }
  }
  KeReleaseSpinLock(&this->m_PendedIoRequestsLock, v6);
  for ( ;
        p_m_SxIrp;
        p_m_SxIrp = KsRemoveIrpFromCancelableQueue(
                      &this->m_PendedIoRequests,
                      &this->m_PendedIoRequestsLock,
                      KsListEntryHead,
                      KsAcquireAndRemove) )
  {
    if ( !a2 || p_m_SxIrp->Tail.Overlay.CurrentStackLocation->MajorFunction == 2 )
    {
      KsDispatchIrp(this->m_Ext.Public.FunctionalDeviceObject, p_m_SxIrp);
    }
    else
    {
      p_m_SxIrp->IoStatus.Status = -2147483631;
      IofCompleteRequest(p_m_SxIrp, 0);
    }
  }
}

```

## disassembly

```asm
0x18000c1dc  push    rbx
0x18000c1de  push    rbp
0x18000c1df  push    rsi
0x18000c1e0  push    rdi
0x18000c1e1  push    r12
0x18000c1e3  push    r14
0x18000c1e5  push    r15
0x18000c1e7  sub     rsp, 30h
0x18000c1eb  mov     r15b, dl
0x18000c1ee  mov     rsi, rcx
0x18000c1f1  lea     rax, WPP_RECORDER_INITIALIZED
0x18000c1f8  xor     r12d, r12d
0x18000c1fb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000c202  jz      short loc_18000C216
0x18000c204  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c20b  cmp     [rcx+48h], r12w
0x18000c210  jnz     loc_18000C2B9
0x18000c216  lea     rcx, [rsi+428h]; Event
0x18000c21d  xor     r8d, r8d; Wait
0x18000c220  xor     edx, edx; Increment
0x18000c222  call    cs:__imp_KeSetEvent
0x18000c229  nop     dword ptr [rax+rax+00h]
0x18000c22e  lea     r14, [rsi+420h]
0x18000c235  mov     rbx, r12
0x18000c238  lea     rbp, [rsi+410h]
0x18000c23f  mov     rcx, r14; SpinLock
0x18000c242  mov     rdi, rbp
0x18000c245  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18000c24c  nop     dword ptr [rax+rax+00h]
0x18000c251  mov     r8b, al
0x18000c254  mov     rdi, [rdi]
0x18000c257  cmp     rdi, rbp
0x18000c25a  jz      short loc_18000C292
0x18000c25c  lea     rdx, [rdi-0A8h]
0x18000c263  mov     rcx, r12
0x18000c266  xchg    rcx, [rdx+68h]
0x18000c26a  test    rcx, rcx
0x18000c26d  jz      short loc_18000C254
0x18000c26f  mov     rax, [rdi]
0x18000c272  cmp     [rax+8], rdi
0x18000c276  jnz     short loc_18000C281
0x18000c278  mov     rcx, [rdi+8]
0x18000c27c  cmp     [rcx], rdi
0x18000c27f  jz      short loc_18000C288
0x18000c281  mov     ecx, 3
0x18000c286  int     29h; Win8: RtlFailFast(ecx)
0x18000c288  mov     [rcx], rax
0x18000c28b  mov     rbx, rdx
0x18000c28e  mov     [rax+8], rcx
0x18000c292  mov     dl, r8b; NewIrql
0x18000c295  mov     rcx, r14; SpinLock
0x18000c298  call    cs:__imp_KeReleaseSpinLock
0x18000c29f  nop     dword ptr [rax+rax+00h]
0x18000c2a4  test    rbx, rbx
0x18000c2a7  jnz     short loc_18000C2E1
0x18000c2a9  add     rsp, 30h
0x18000c2ad  pop     r15
0x18000c2af  pop     r14
0x18000c2b1  pop     r12
0x18000c2b3  pop     rdi
0x18000c2b4  pop     rsi
0x18000c2b5  pop     rbp
0x18000c2b6  pop     rbx
0x18000c2b7  retn
0x18000c2b9  mov     rcx, [rcx+40h]
0x18000c2bd  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18000c2c4  mov     r9d, 9Ch
0x18000c2ca  mov     [rsp+68h+var_48], rax
0x18000c2cf  mov     r8d, 1
0x18000c2d5  mov     dl, 5
0x18000c2d7  call    WPP_RECORDER_SF_
0x18000c2dc  jmp     loc_18000C216
0x18000c2e1  test    r15b, r15b
0x18000c2e4  jz      short loc_18000C30C
0x18000c2e6  mov     rax, [rbx+0B8h]
0x18000c2ed  cmp     byte ptr [rax], 2
0x18000c2f0  jz      short loc_18000C30C
0x18000c2f2  xor     edx, edx; PriorityBoost
0x18000c2f4  mov     dword ptr [rbx+30h], 80000011h
0x18000c2fb  mov     rcx, rbx; Irp
0x18000c2fe  call    cs:__imp_IofCompleteRequest
0x18000c305  nop     dword ptr [rax+rax+00h]
0x18000c30a  jmp     short loc_18000C31B
0x18000c30c  mov     rcx, [rsi+0E0h]; DeviceObject
0x18000c313  mov     rdx, rbx; Irp
0x18000c316  call    KsDispatchIrp
0x18000c31b  mov     r9d, 1; RemovalOperation
0x18000c321  mov     rdx, r14; SpinLock
0x18000c324  mov     r8d, r9d; ListLocation
0x18000c327  mov     rcx, rbp; QueueHead
0x18000c32a  call    KsRemoveIrpFromCancelableQueue
0x18000c32f  mov     rbx, rax
0x18000c332  test    rax, rax
0x18000c335  jnz     short loc_18000C2E1
0x18000c337  jmp     loc_18000C2A9
```
