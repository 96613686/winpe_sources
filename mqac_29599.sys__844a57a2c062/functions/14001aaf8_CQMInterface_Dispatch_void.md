# CQMInterface::Dispatch(void)

- ea: `0x14001aaf8`
- end: `0x14001abc6`
- name: `?Dispatch@CQMInterface@@AEAAXXZ`
- size: `206`
- prototype: `void __fastcall(CQMInterface *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x14001b114`
- `0x14001b4f0`

## callees

- `0x140003d84`
- `0x140012644`
- `0x14001aaf8`
- `0x14001abcc`
- `0x14001ad2c`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001ab30`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001ab30`
- `ntoskrnl!IofCompleteRequest` at `0x14001aba0`
- `ntoskrnl!IofCompleteRequest` at `0x14001aba0`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14001ab09`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14001ab09`

## pseudocode

```c
void __fastcall CQMInterface::Dispatch(CQMInterface *this)
{
  __int64 v2; // rax
  IRP *v3; // rbx
  struct CACRequest *Request; // rsi
  KIRQL Irql; // [rsp+50h] [rbp+8h] BYREF

  while ( 1 )
  {
    IoAcquireCancelSpinLock(&Irql);
    v2 = XList<_IRP,168>::gethead((char *)this + 40);
    v3 = (IRP *)v2;
    if ( v2 )
      _InterlockedExchange64((volatile __int64 *)(v2 + 104), 0);
    IoReleaseCancelSpinLock(Irql);
    if ( !v3 )
      break;
    Request = CQMInterface::GetRequest(this);
    if ( !Request )
    {
      CQMInterface::HoldService(this, v3);
      return;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 21, &WPP_bbff1b0e8ef6334436de7c5c17c85fe3_Traceguids, v3);
    }
    v3->Flags |= 0x70u;
    v3->AssociatedIrp.MasterIrp = (struct _IRP *)Request;
    v3->IoStatus.Information = 232;
    v3->IoStatus.Status = 0;
    IofCompleteRequest(v3, 2);
  }
}

```

## disassembly

```asm
0x14001aaf8  push    rbx
0x14001aafa  push    rbp
0x14001aafb  push    rsi
0x14001aafc  push    rdi
0x14001aafd  sub     rsp, 28h
0x14001ab01  mov     rdi, rcx
0x14001ab04  lea     rcx, [rsp+48h+Irql]; Irql
0x14001ab09  call    cs:__imp_IoAcquireCancelSpinLock
0x14001ab10  nop     dword ptr [rax+rax+00h]
0x14001ab15  lea     rcx, [rdi+28h]
0x14001ab19  call    ?gethead@?$XList@U_IRP@@$0KI@@@QEAAPEAU_IRP@@XZ; XList<_IRP,168>::gethead(void)
0x14001ab1e  mov     rbx, rax
0x14001ab21  test    rax, rax
0x14001ab24  jz      short loc_14001AB2C
0x14001ab26  xor     ecx, ecx
0x14001ab28  xchg    rcx, [rax+68h]
0x14001ab2c  mov     cl, [rsp+48h+Irql]; Irql
0x14001ab30  call    cs:__imp_IoReleaseCancelSpinLock
0x14001ab37  nop     dword ptr [rax+rax+00h]
0x14001ab3c  test    rbx, rbx
0x14001ab3f  jz      short loc_14001ABBC
0x14001ab41  mov     rcx, rdi; this
0x14001ab44  call    ?GetRequest@CQMInterface@@AEAAPEAVCACRequest@@XZ; CQMInterface::GetRequest(void)
0x14001ab49  mov     rsi, rax
0x14001ab4c  test    rax, rax
0x14001ab4f  jz      short loc_14001ABB1
0x14001ab51  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ab58  lea     rax, WPP_GLOBAL_Control
0x14001ab5f  cmp     rcx, rax
0x14001ab62  jz      short loc_14001AB84
0x14001ab64  mov     edx, [rcx+6Ch]
0x14001ab67  test    dl, 4
0x14001ab6a  jz      short loc_14001AB84
0x14001ab6c  mov     rcx, [rcx+58h]
0x14001ab70  lea     r8, WPP_bbff1b0e8ef6334436de7c5c17c85fe3_Traceguids
0x14001ab77  mov     edx, 15h
0x14001ab7c  mov     r9, rbx
0x14001ab7f  call    WPP_SF_q
0x14001ab84  or      dword ptr [rbx+10h], 70h
0x14001ab88  mov     dl, 2; PriorityBoost
0x14001ab8a  mov     rcx, rbx; Irp
0x14001ab8d  mov     [rbx+18h], rsi
0x14001ab91  mov     qword ptr [rbx+38h], 0E8h
0x14001ab99  mov     dword ptr [rbx+30h], 0
0x14001aba0  call    cs:__imp_IofCompleteRequest
0x14001aba7  nop     dword ptr [rax+rax+00h]
0x14001abac  jmp     loc_14001AB04
0x14001abb1  mov     rdx, rbx; struct _IRP *
0x14001abb4  mov     rcx, rdi; this
0x14001abb7  call    ?HoldService@CQMInterface@@AEAAXPEAU_IRP@@@Z; CQMInterface::HoldService(_IRP *)
0x14001abbc  add     rsp, 28h
0x14001abc0  pop     rdi
0x14001abc1  pop     rsi
0x14001abc2  pop     rbp
0x14001abc3  pop     rbx
0x14001abc4  retn
```
