# ProcessIncomingCallConnectedRequest

- ea: `0x140010c58`
- end: `0x140010fce`
- name: `ProcessIncomingCallConnectedRequest`
- size: `886`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140002060`

## callees

- `0x1400018b0`
- `0x140002030`
- `0x140002bd8`
- `0x140002f88`
- `0x140002fc4`
- `0x140005ef0`
- `0x140010c58`
- `0x140019e70`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010cff`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010db2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010e30`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010eb6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010f3d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010cff`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010db2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010e30`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010eb6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010f3d`
- `ntoskrnl!IofCompleteRequest` at `0x140010fb8`
- `ntoskrnl!IofCompleteRequest` at `0x140010fb8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010d45`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010d9e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010dd0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010ed7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010d45`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010d9e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010dd0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010ed7`
- `NETIO!HfGetPointerFromHandle32` at `0x140010d22`
- `NETIO!HfGetPointerFromHandle32` at `0x140010d22`

## pseudocode

```c
__int64 __fastcall ProcessIncomingCallConnectedRequest(PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  NTSTATUS PointerFromHandle32; // ebx
  unsigned int v4; // ebx
  KIRQL v5; // si
  volatile signed __int32 *v6; // rax
  KIRQL v7; // al
  __int64 v8; // r8
  KIRQL v10; // al
  __int64 v11; // r9
  KIRQL v12; // si
  __int64 v13; // r8
  __int64 v14; // [rsp+80h] [rbp+38h] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v14 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x82) == 0x82 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
  if ( CurrentStackLocation->Parameters.Create.Options != 4 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
    }
    PointerFromHandle32 = -1073741811;
    goto LABEL_23;
  }
  v4 = *(_DWORD *)Irp->AssociatedIrp.MasterIrp;
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SstpGlobals + 62);
  PointerFromHandle32 = HfGetPointerFromHandle32(*((_QWORD *)SstpGlobals + 63), v4, &v14);
  if ( PointerFromHandle32 < 0 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 62, v5);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
    }
    PointerFromHandle32 = -1073741275;
    goto LABEL_23;
  }
  v6 = (volatile signed __int32 *)v14;
  Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = (struct _LIST_ENTRY *)v14;
  _InterlockedIncrement(v6);
  KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 62, v5);
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v14 + 32));
  *(_QWORD *)(v14 + 64) = Irp;
  KeReleaseSpinLock((PKSPIN_LOCK)(v14 + 32), v7);
  if ( (unsigned __int8)SetCancelRoutineSafe(Irp, &DispatchIncomingCallConnectedCancelIrp) )
  {
    v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v14 + 32));
    *(_DWORD *)(v14 + 21088) |= 2u;
    KeReleaseSpinLock((PKSPIN_LOCK)(v14 + 32), v10);
    v11 = v14 + 297;
    LOBYTE(v11) = *(_BYTE *)(v14 + 296);
    PointerFromHandle32 = (*((__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, __int64, __int64, __int64))SstpGlobals
                           + 65))(
                            v14,
                            0,
                            1,
                            v11,
                            v14 + 297,
                            v14 + 317,
                            v14 + 484);
    if ( PointerFromHandle32 < 0 )
    {
      v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v14 + 32));
      *(_DWORD *)(v14 + 21088) &= ~2u;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF__guid_D(
          WPP_GLOBAL_Control->AttachedDevice,
          48,
          WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids,
          v14 + 484,
          PointerFromHandle32);
      }
      LOBYTE(v13) = v12;
      InitiateSstpContextCleanup(v14, 4, v13);
      _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, 0);
      Irp->IoStatus.Status = PointerFromHandle32;
      Irp->IoStatus.Information = 0;
      IofCompleteRequest(Irp, 0);
      PointerFromHandle32 = 259;
      goto LABEL_24;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF__guid_(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids, v14 + 484);
    }
    LOBYTE(v8) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v14 + 32));
    *(_QWORD *)(v14 + 64) = 0;
    InitiateSstpContextCleanup(v14, 4, v8);
    DereferenceRefCount(v14);
  }
  if ( PointerFromHandle32 != 259 )
  {
LABEL_23:
    Irp->IoStatus.Information = 0;
    Irp->IoStatus.Status = PointerFromHandle32;
  }
LABEL_24:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x82) == 0x82 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
  return (unsigned int)PointerFromHandle32;
}

```

## disassembly

```asm
0x140010c58  push    rbp
0x140010c5a  push    rbx
0x140010c5b  push    rsi
0x140010c5c  push    rdi
0x140010c5d  push    r12
0x140010c5f  push    r15
0x140010c61  mov     rbp, rsp
0x140010c64  sub     rsp, 48h
0x140010c68  mov     rbx, [rcx+0B8h]
0x140010c6f  mov     rdi, rcx
0x140010c72  mov     [rbp+arg_0], 0
0x140010c7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140010c81  lea     r15, WPP_GLOBAL_Control
0x140010c88  lea     r12, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140010c8f  cmp     rcx, r15
0x140010c92  jz      short loc_140010CB1
0x140010c94  mov     eax, [rcx+2Ch]
0x140010c97  and     eax, 82h
0x140010c9c  cmp     al, 82h
0x140010c9e  jnz     short loc_140010CB1
0x140010ca0  mov     rcx, [rcx+18h]
0x140010ca4  mov     edx, 2Ch ; ','
0x140010ca9  mov     r8, r12
0x140010cac  call    WPP_SF_
0x140010cb1  cmp     dword ptr [rbx+10h], 4
0x140010cb5  jz      short loc_140010CEB
0x140010cb7  mov     rcx, cs:WPP_GLOBAL_Control
0x140010cbe  cmp     rcx, r15
0x140010cc1  jz      short loc_140010CE1
0x140010cc3  mov     eax, [rcx+2Ch]
0x140010cc6  test    al, 2
0x140010cc8  jz      short loc_140010CE1
0x140010cca  cmp     byte ptr [rcx+29h], 1
0x140010cce  jb      short loc_140010CE1
0x140010cd0  mov     rcx, [rcx+18h]
0x140010cd4  mov     edx, 2Dh ; '-'
0x140010cd9  mov     r8, r12
0x140010cdc  call    WPP_SF_
0x140010ce1  mov     ebx, 0C000000Dh
0x140010ce6  jmp     loc_140010E6A
0x140010ceb  mov     rax, [rdi+18h]
0x140010cef  mov     rcx, cs:SstpGlobals
0x140010cf6  add     rcx, 1F0h; SpinLock
0x140010cfd  mov     ebx, [rax]
0x140010cff  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010d06  nop     dword ptr [rax+rax+00h]
0x140010d0b  mov     rcx, cs:SstpGlobals
0x140010d12  lea     r8, [rbp+arg_0]
0x140010d16  mov     edx, ebx
0x140010d18  mov     sil, al
0x140010d1b  mov     rcx, [rcx+1F8h]
0x140010d22  call    cs:__imp_HfGetPointerFromHandle32
0x140010d29  nop     dword ptr [rax+rax+00h]
0x140010d2e  mov     ebx, eax
0x140010d30  mov     dl, sil; NewIrql
0x140010d33  test    eax, eax
0x140010d35  jns     short loc_140010D85
0x140010d37  mov     rcx, cs:SstpGlobals
0x140010d3e  add     rcx, 1F0h; SpinLock
0x140010d45  call    cs:__imp_KeReleaseSpinLock
0x140010d4c  nop     dword ptr [rax+rax+00h]
0x140010d51  mov     rcx, cs:WPP_GLOBAL_Control
0x140010d58  cmp     rcx, r15
0x140010d5b  jz      short loc_140010D7B
0x140010d5d  mov     eax, [rcx+2Ch]
0x140010d60  test    al, 2
0x140010d62  jz      short loc_140010D7B
0x140010d64  cmp     byte ptr [rcx+29h], 1
0x140010d68  jb      short loc_140010D7B
0x140010d6a  mov     rcx, [rcx+18h]
0x140010d6e  mov     edx, 2Eh ; '.'
0x140010d73  mov     r8, r12
0x140010d76  call    WPP_SF_
0x140010d7b  mov     ebx, 0C0000225h
0x140010d80  jmp     loc_140010E6A
0x140010d85  mov     rax, [rbp+arg_0]
0x140010d89  mov     [rdi+78h], rax
0x140010d8d  lock inc dword ptr [rax]
0x140010d90  mov     rcx, cs:SstpGlobals
0x140010d97  add     rcx, 1F0h; SpinLock
0x140010d9e  call    cs:__imp_KeReleaseSpinLock
0x140010da5  nop     dword ptr [rax+rax+00h]
0x140010daa  mov     rcx, [rbp+arg_0]
0x140010dae  add     rcx, 20h ; ' '; SpinLock
0x140010db2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010db9  nop     dword ptr [rax+rax+00h]
0x140010dbe  mov     rcx, [rbp+arg_0]
0x140010dc2  mov     dl, al; NewIrql
0x140010dc4  mov     [rcx+40h], rdi
0x140010dc8  mov     rcx, [rbp+arg_0]
0x140010dcc  add     rcx, 20h ; ' '; SpinLock
0x140010dd0  call    cs:__imp_KeReleaseSpinLock
0x140010dd7  nop     dword ptr [rax+rax+00h]
0x140010ddc  lea     rdx, DispatchIncomingCallConnectedCancelIrp
0x140010de3  mov     rcx, rdi
0x140010de6  call    SetCancelRoutineSafe
0x140010deb  test    al, al
0x140010ded  jnz     loc_140010EAE
0x140010df3  mov     rcx, cs:WPP_GLOBAL_Control
0x140010dfa  cmp     rcx, r15
0x140010dfd  jz      short loc_140010E28
0x140010dff  mov     eax, [rcx+2Ch]
0x140010e02  test    al, 2
0x140010e04  jz      short loc_140010E28
0x140010e06  cmp     byte ptr [rcx+29h], 1
0x140010e0a  jb      short loc_140010E28
0x140010e0c  mov     r9, [rbp+arg_0]
0x140010e10  mov     edx, 2Fh ; '/'
0x140010e15  mov     rcx, [rcx+18h]
0x140010e19  add     r9, 1E4h
0x140010e20  mov     r8, r12
0x140010e23  call    WPP_SF__guid_
0x140010e28  mov     rcx, [rbp+arg_0]
0x140010e2c  add     rcx, 20h ; ' '; SpinLock
0x140010e30  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010e37  nop     dword ptr [rax+rax+00h]
0x140010e3c  mov     rcx, [rbp+arg_0]
0x140010e40  mov     edx, 4
0x140010e45  mov     r8b, al
0x140010e48  mov     qword ptr [rcx+40h], 0
0x140010e50  mov     rcx, [rbp+arg_0]
0x140010e54  call    InitiateSstpContextCleanup
0x140010e59  mov     rcx, [rbp+arg_0]
0x140010e5d  call    DereferenceRefCount
0x140010e62  cmp     ebx, 103h
0x140010e68  jz      short loc_140010E75
0x140010e6a  mov     qword ptr [rdi+38h], 0
0x140010e72  mov     [rdi+30h], ebx
0x140010e75  mov     rcx, cs:WPP_GLOBAL_Control
0x140010e7c  cmp     rcx, r15
0x140010e7f  jz      short loc_140010E9E
0x140010e81  mov     eax, [rcx+2Ch]
0x140010e84  and     eax, 82h
0x140010e89  cmp     al, 82h
0x140010e8b  jnz     short loc_140010E9E
0x140010e8d  mov     rcx, [rcx+18h]
0x140010e91  mov     edx, 31h ; '1'
0x140010e96  mov     r8, r12
0x140010e99  call    WPP_SF_
0x140010e9e  mov     eax, ebx
0x140010ea0  add     rsp, 48h
0x140010ea4  pop     r15
0x140010ea6  pop     r12
0x140010ea8  pop     rdi
0x140010ea9  pop     rsi
0x140010eaa  pop     rbx
0x140010eab  pop     rbp
0x140010eac  retn
0x140010eae  mov     rcx, [rbp+arg_0]
0x140010eb2  add     rcx, 20h ; ' '; SpinLock
0x140010eb6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010ebd  nop     dword ptr [rax+rax+00h]
0x140010ec2  mov     rcx, [rbp+arg_0]
0x140010ec6  mov     dl, al; NewIrql
0x140010ec8  or      dword ptr [rcx+5260h], 2
0x140010ecf  mov     rcx, [rbp+arg_0]
0x140010ed3  add     rcx, 20h ; ' '; SpinLock
0x140010ed7  call    cs:__imp_KeReleaseSpinLock
0x140010ede  nop     dword ptr [rax+rax+00h]
0x140010ee3  mov     rcx, [rbp+arg_0]
0x140010ee7  mov     rax, cs:SstpGlobals
0x140010eee  lea     rdx, [rcx+1E4h]
0x140010ef5  mov     rax, [rax+208h]
0x140010efc  lea     r8, [rcx+13Dh]
0x140010f03  mov     [rsp+48h+var_18], rdx
0x140010f08  lea     r9, [rcx+129h]
0x140010f0f  mov     [rsp+48h+var_20], r8
0x140010f14  xor     edx, edx
0x140010f16  mov     [rsp+48h+var_28], r9
0x140010f1b  mov     r9b, [rcx+128h]
0x140010f22  lea     r8d, [rdx+1]
0x140010f26  call    _guard_dispatch_icall
0x140010f2b  mov     ebx, eax
0x140010f2d  test    eax, eax
0x140010f2f  jns     loc_140010E62
0x140010f35  mov     rcx, [rbp+arg_0]
0x140010f39  add     rcx, 20h ; ' '; SpinLock
0x140010f3d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010f44  nop     dword ptr [rax+rax+00h]
0x140010f49  mov     rcx, [rbp+arg_0]
0x140010f4d  mov     sil, al
0x140010f50  and     dword ptr [rcx+5260h], 0FFFFFFFDh
0x140010f57  mov     rcx, cs:WPP_GLOBAL_Control
0x140010f5e  cmp     rcx, r15
0x140010f61  jz      short loc_140010F91
0x140010f63  mov     edx, [rcx+2Ch]
0x140010f66  test    dl, 2
0x140010f69  jz      short loc_140010F91
0x140010f6b  cmp     byte ptr [rcx+29h], 1
0x140010f6f  jb      short loc_140010F91
0x140010f71  mov     r9, [rbp+arg_0]
0x140010f75  mov     edx, 30h ; '0'
0x140010f7a  mov     rcx, [rcx+18h]
0x140010f7e  add     r9, 1E4h
0x140010f85  mov     r8, r12
0x140010f88  mov     dword ptr [rsp+48h+var_28], ebx
0x140010f8c  call    WPP_SF__guid_D
0x140010f91  mov     rcx, [rbp+arg_0]
0x140010f95  mov     r8b, sil
0x140010f98  mov     edx, 4
0x140010f9d  call    InitiateSstpContextCleanup
0x140010fa2  xor     eax, eax
0x140010fa4  xor     edx, edx; PriorityBoost
0x140010fa6  xchg    rax, [rdi+68h]
0x140010faa  mov     rcx, rdi; Irp
0x140010fad  mov     [rdi+30h], ebx
0x140010fb0  mov     qword ptr [rdi+38h], 0
0x140010fb8  call    cs:__imp_IofCompleteRequest
0x140010fbf  nop     dword ptr [rax+rax+00h]
0x140010fc4  mov     ebx, 103h
0x140010fc9  jmp     loc_140010E75
```
