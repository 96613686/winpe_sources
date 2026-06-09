# CCreatePacketComplete::CompleteCreatePacket(_DEVICE_OBJECT *)

- ea: `0x1400120e4`
- end: `0x1400121df`
- name: `?CompleteCreatePacket@CCreatePacketComplete@@AEAAXPEAU_DEVICE_OBJECT@@@Z`
- size: `251`
- prototype: `void(CCreatePacketComplete *__hidden this, struct _DEVICE_OBJECT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140012620`

## callees

- `0x140001c04`
- `0x140009adc`
- `0x14001206c`
- `0x1400120e4`
- `0x140012644`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001212b`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001212b`
- `ntoskrnl!IofCompleteRequest` at `0x1400121ba`
- `ntoskrnl!IofCompleteRequest` at `0x1400121ba`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140012105`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140012105`

## pseudocode

```c
void __fastcall CCreatePacketComplete::CompleteCreatePacket(CCreatePacketComplete *this, struct _DEVICE_OBJECT *a2)
{
  __int64 v4; // rax
  IRP *v5; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  ULONG Options; // ebp
  unsigned __int16 SecurityContext; // r14
  struct CPacket *v9; // rax
  int v10; // eax
  KIRQL Irql; // [rsp+40h] [rbp+8h] BYREF

  *((_BYTE *)this + 24) = 0;
  while ( 1 )
  {
    IoAcquireCancelSpinLock(&Irql);
    v4 = XList<_IRP,168>::gethead(this);
    v5 = (IRP *)v4;
    if ( v4 )
      _InterlockedExchange64((volatile __int64 *)(v4 + 104), 0);
    IoReleaseCancelSpinLock(Irql);
    if ( !v5 )
      break;
    CurrentStackLocation = v5->Tail.Overlay.CurrentStackLocation;
    Options = CurrentStackLocation->Parameters.Create.Options;
    SecurityContext = (unsigned __int16)CurrentStackLocation->Parameters.Create.SecurityContext;
    v9 = CPacketHandleToCPacket(a2, (struct CPacket *)CurrentStackLocation->Parameters.CreatePipe.Parameters);
    v5->IoStatus.Information = 0;
    if ( v9 )
    {
      ACpCompleteCreatePacket(a2, v9, Options, SecurityContext);
      v10 = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 16, WPP_f72b4ea4c5c535374694b3572d3977a7_Traceguids);
      }
      v10 = -1073741811;
    }
    v5->IoStatus.Status = v10;
    IofCompleteRequest(v5, 0);
  }
}

```

## disassembly

```asm
0x1400120e4  mov     [rsp+arg_8], rbx
0x1400120e9  mov     [rsp+arg_10], rbp
0x1400120ee  push    rsi
0x1400120ef  push    rdi
0x1400120f0  push    r14
0x1400120f2  sub     rsp, 20h
0x1400120f6  mov     rsi, rdx
0x1400120f9  mov     byte ptr [rcx+18h], 0
0x1400120fd  mov     rdi, rcx
0x140012100  lea     rcx, [rsp+38h+Irql]; Irql
0x140012105  call    cs:__imp_IoAcquireCancelSpinLock
0x14001210c  nop     dword ptr [rax+rax+00h]
0x140012111  mov     rcx, rdi
0x140012114  call    ?gethead@?$XList@U_IRP@@$0KI@@@QEAAPEAU_IRP@@XZ; XList<_IRP,168>::gethead(void)
0x140012119  mov     rbx, rax
0x14001211c  test    rax, rax
0x14001211f  jz      short loc_140012127
0x140012121  xor     ecx, ecx
0x140012123  xchg    rcx, [rax+68h]
0x140012127  mov     cl, [rsp+38h+Irql]; Irql
0x14001212b  call    cs:__imp_IoReleaseCancelSpinLock
0x140012132  nop     dword ptr [rax+rax+00h]
0x140012137  test    rbx, rbx
0x14001213a  jz      loc_1400121CB
0x140012140  mov     rdx, [rbx+0B8h]
0x140012147  mov     rcx, rsi; struct _DEVICE_OBJECT *
0x14001214a  mov     ebp, [rdx+10h]
0x14001214d  movzx   r14d, word ptr [rdx+8]
0x140012152  mov     rdx, [rdx+20h]; struct CPacket *
0x140012156  call    ?CPacketHandleToCPacket@@YAPEAVCPacket@@PEAU_DEVICE_OBJECT@@PEAV1@@Z; CPacketHandleToCPacket(_DEVICE_OBJECT *,CPacket *)
0x14001215b  mov     qword ptr [rbx+38h], 0
0x140012163  test    rax, rax
0x140012166  jz      short loc_14001217E
0x140012168  movzx   r9d, r14w
0x14001216c  mov     r8d, ebp
0x14001216f  mov     rdx, rax
0x140012172  mov     rcx, rsi
0x140012175  call    ACpCompleteCreatePacket
0x14001217a  xor     eax, eax
0x14001217c  jmp     short loc_1400121B2
0x14001217e  mov     rcx, cs:WPP_GLOBAL_Control
0x140012185  lea     rax, WPP_GLOBAL_Control
0x14001218c  cmp     rcx, rax
0x14001218f  jz      short loc_1400121AD
0x140012191  mov     eax, [rcx+6Ch]
0x140012194  test    al, 1
0x140012196  jz      short loc_1400121AD
0x140012198  mov     rcx, [rcx+58h]
0x14001219c  lea     r8, WPP_f72b4ea4c5c535374694b3572d3977a7_Traceguids
0x1400121a3  mov     edx, 10h
0x1400121a8  call    WPP_SF_
0x1400121ad  mov     eax, 0C000000Dh
0x1400121b2  xor     edx, edx; PriorityBoost
0x1400121b4  mov     [rbx+30h], eax
0x1400121b7  mov     rcx, rbx; Irp
0x1400121ba  call    cs:__imp_IofCompleteRequest
0x1400121c1  nop     dword ptr [rax+rax+00h]
0x1400121c6  jmp     loc_140012100
0x1400121cb  mov     rbx, [rsp+38h+arg_8]
0x1400121d0  mov     rbp, [rsp+38h+arg_10]
0x1400121d5  add     rsp, 20h
0x1400121d9  pop     r14
0x1400121db  pop     rdi
0x1400121dc  pop     rsi
0x1400121dd  retn
```
