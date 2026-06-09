# ACCreatePacketCompleted

- ea: `0x1400051d8`
- end: `0x140005336`
- name: `ACCreatePacketCompleted`
- size: `350`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000a3b0`

## callees

- `0x140001c04`
- `0x140003d84`
- `0x1400051d8`
- `0x140009a54`
- `0x14000b8e8`
- `0x140012368`

## pseudocode

```c
__int64 __fastcall ACCreatePacketCompleted(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  char *DeviceExtension; // rsi
  PVOID UserBuffer; // rdi

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 126, &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids);
  }
  DeviceExtension = (char *)a1->DeviceExtension;
  UserBuffer = a2->UserBuffer;
  if ( CPacketHandleToCPacket(
         (struct CDeviceExt *)DeviceExtension,
         a2->Tail.Overlay.CurrentStackLocation->Parameters.CreatePipe.Parameters) )
  {
    if ( !UserBuffer || CPacketHandleToCPacket((struct CDeviceExt *)DeviceExtension, UserBuffer) )
    {
      CCreatePacketComplete::HandleNotification((CCreatePacketComplete *)(DeviceExtension + 432), a1, a2);
      return 259;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 128, &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, 0);
      }
      return 3221225485LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 127, &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, 0);
    }
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x1400051d8  push    rbx
0x1400051da  push    rsi
0x1400051db  push    rdi
0x1400051dc  push    r14
0x1400051de  push    r15
0x1400051e0  sub     rsp, 40h
0x1400051e4  mov     rbx, rdx
0x1400051e7  mov     r14, rcx
0x1400051ea  lea     r15, WPP_GLOBAL_Control
0x1400051f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400051f8  cmp     rcx, r15
0x1400051fb  jz      short loc_140005219
0x1400051fd  mov     eax, [rcx+6Ch]
0x140005200  test    al, 4
0x140005202  jz      short loc_140005219
0x140005204  mov     edx, 7Eh ; '~'
0x140005209  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140005210  mov     rcx, [rcx+58h]
0x140005214  call    WPP_SF_
0x140005219  mov     rsi, [r14+40h]
0x14000521d  mov     rax, [rbx+0B8h]
0x140005224  mov     rdx, [rax+20h]; void *
0x140005228  mov     [rsp+68h+var_30], rdx
0x14000522d  mov     rdi, [rbx+70h]
0x140005231  mov     [rsp+68h+var_38], rdi
0x140005236  mov     rcx, rsi; struct CDeviceExt *
0x140005239  call    ?CPacketHandleToCPacket@@YAPEAVCPacket@@PEAUCDeviceExt@@PEAX@Z; CPacketHandleToCPacket(CDeviceExt *,void *)
0x14000523e  mov     [rsp+68h+var_30], rax
0x140005243  test    rax, rax
0x140005246  jnz     short loc_14000527D
0x140005248  mov     rcx, cs:WPP_GLOBAL_Control
0x14000524f  cmp     rcx, r15
0x140005252  jz      short loc_140005273
0x140005254  mov     eax, [rcx+6Ch]
0x140005257  test    al, 1
0x140005259  jz      short loc_140005273
0x14000525b  mov     edx, 7Fh
0x140005260  xor     r9d, r9d
0x140005263  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x14000526a  mov     rcx, [rcx+58h]
0x14000526e  call    WPP_SF_q
0x140005273  mov     eax, 0C000000Dh
0x140005278  jmp     loc_140005329
0x14000527d  test    rdi, rdi
0x140005280  jz      short loc_1400052C9
0x140005282  mov     rdx, rdi; void *
0x140005285  mov     rcx, rsi; struct CDeviceExt *
0x140005288  call    ?CPacketHandleToCPacket@@YAPEAVCPacket@@PEAUCDeviceExt@@PEAX@Z; CPacketHandleToCPacket(CDeviceExt *,void *)
0x14000528d  mov     [rsp+68h+var_38], rax
0x140005292  test    rax, rax
0x140005295  jnz     short loc_1400052C9
0x140005297  mov     rcx, cs:WPP_GLOBAL_Control
0x14000529e  cmp     rcx, r15
0x1400052a1  jz      short loc_1400052C2
0x1400052a3  mov     eax, [rcx+6Ch]
0x1400052a6  test    al, 1
0x1400052a8  jz      short loc_1400052C2
0x1400052aa  mov     edx, 80h
0x1400052af  xor     r9d, r9d
0x1400052b2  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x1400052b9  mov     rcx, [rcx+58h]
0x1400052bd  call    WPP_SF_q
0x1400052c2  mov     eax, 0C000000Dh
0x1400052c7  jmp     short loc_140005329
0x1400052c9  lea     rcx, [rsi+1B0h]; this
0x1400052d0  mov     r8, rbx; struct _IRP *
0x1400052d3  mov     rdx, r14; struct _DEVICE_OBJECT *
0x1400052d6  call    ?HandleNotification@CCreatePacketComplete@@QEAAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; CCreatePacketComplete::HandleNotification(_DEVICE_OBJECT *,_IRP *)
0x1400052db  mov     eax, 103h
0x1400052e0  jmp     short loc_140005329
0x1400052e2  mov     ebx, eax
0x1400052e4  lea     rax, WPP_GLOBAL_Control
0x1400052eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400052f2  cmp     rcx, rax
0x1400052f5  jz      short loc_140005327
0x1400052f7  mov     edx, [rcx+6Ch]
0x1400052fa  test    dl, 1
0x1400052fd  jz      short loc_140005327
0x1400052ff  mov     edx, 81h
0x140005304  mov     [rsp+68h+var_40], ebx
0x140005308  mov     r8, [rsp+68h+var_38]
0x14000530d  mov     [rsp+68h+var_48], r8
0x140005312  mov     r9, [rsp+68h+var_30]
0x140005317  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x14000531e  mov     rcx, [rcx+58h]
0x140005322  call    WPP_SF_qqD
0x140005327  mov     eax, ebx
0x140005329  add     rsp, 40h
0x14000532d  pop     r15
0x14000532f  pop     r14
0x140005331  pop     rdi
0x140005332  pop     rsi
0x140005333  pop     rbx
0x140005334  retn
```
