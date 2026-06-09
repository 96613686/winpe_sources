# CQMInterface::ProcessService(_IRP *)

- ea: `0x14001b270`
- end: `0x14001b2f9`
- name: `?ProcessService@CQMInterface@@QEAAJPEAU_IRP@@@Z`
- size: `137`
- prototype: `__int64 __fastcall(CQMInterface *__hidden this, struct _IRP *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14000a3b0`

## callees

- `0x140003d84`
- `0x14001abcc`
- `0x14001ad2c`
- `0x14001b270`

## pseudocode

```c
__int64 __fastcall CQMInterface::ProcessService(CQMInterface *this, struct _IRP *a2)
{
  struct _IRP *Request; // rsi
  __int64 result; // rax

  Request = (struct _IRP *)CQMInterface::GetRequest(this);
  if ( Request )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 19, WPP_bbff1b0e8ef6334436de7c5c17c85fe3_Traceguids, a2);
    }
    a2->Flags |= 0x70u;
    result = 0;
    a2->AssociatedIrp.MasterIrp = Request;
    a2->IoStatus.Information = 232;
  }
  else
  {
    CQMInterface::HoldService(this, a2);
    return 259;
  }
  return result;
}

```

## disassembly

```asm
0x14001b270  mov     [rsp+arg_0], rbx
0x14001b275  mov     [rsp+arg_8], rsi
0x14001b27a  push    rdi
0x14001b27b  sub     rsp, 20h
0x14001b27f  mov     rbx, rdx
0x14001b282  mov     rdi, rcx
0x14001b285  call    ?GetRequest@CQMInterface@@AEAAPEAVCACRequest@@XZ; CQMInterface::GetRequest(void)
0x14001b28a  mov     rsi, rax
0x14001b28d  test    rax, rax
0x14001b290  jnz     short loc_14001B2A4
0x14001b292  mov     rdx, rbx; struct _IRP *
0x14001b295  mov     rcx, rdi; this
0x14001b298  call    ?HoldService@CQMInterface@@AEAAXPEAU_IRP@@@Z; CQMInterface::HoldService(_IRP *)
0x14001b29d  mov     eax, 103h
0x14001b2a2  jmp     short loc_14001B2E8
0x14001b2a4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b2ab  lea     rax, WPP_GLOBAL_Control
0x14001b2b2  cmp     rcx, rax
0x14001b2b5  jz      short loc_14001B2D6
0x14001b2b7  mov     eax, [rcx+6Ch]
0x14001b2ba  test    al, 4
0x14001b2bc  jz      short loc_14001B2D6
0x14001b2be  mov     rcx, [rcx+58h]
0x14001b2c2  lea     r8, WPP_bbff1b0e8ef6334436de7c5c17c85fe3_Traceguids
0x14001b2c9  mov     edx, 13h
0x14001b2ce  mov     r9, rbx
0x14001b2d1  call    WPP_SF_q
0x14001b2d6  or      dword ptr [rbx+10h], 70h
0x14001b2da  xor     eax, eax
0x14001b2dc  mov     [rbx+18h], rsi
0x14001b2e0  mov     qword ptr [rbx+38h], 0E8h
0x14001b2e8  mov     rbx, [rsp+28h+arg_0]
0x14001b2ed  mov     rsi, [rsp+28h+arg_8]
0x14001b2f2  add     rsp, 20h
0x14001b2f6  pop     rdi
0x14001b2f7  retn
```
